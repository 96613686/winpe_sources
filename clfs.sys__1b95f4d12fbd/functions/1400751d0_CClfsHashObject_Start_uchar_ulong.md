# CClfsHashObject::Start(uchar *,ulong)

- ea: `0x1400751d0`
- end: `0x1400752f9`
- name: `?Start@CClfsHashObject@@QEAAJPEAEK@Z`
- size: `297`
- prototype: `__int64 __fastcall(CClfsHashObject *__hidden this, PUCHAR pbSecret, ULONG cbSecret)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14003b49c`
- `0x14003ccec`
- `0x14003d11c`
- `0x14003f568`
- `0x14004f3d4`
- `0x140075070`
- `0x1400786b8`

## callees

- `0x1400751d0`
- `0x140078688`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140075219`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140075219`
- `cng!BCryptCreateHash` at `0x140075261`
- `cng!BCryptCreateHash` at `0x140075296`
- `cng!BCryptCreateHash` at `0x140075261`
- `cng!BCryptCreateHash` at `0x140075296`
- `cng!BCryptDestroyHash` at `0x1400752b9`
- `cng!BCryptDestroyHash` at `0x1400752b9`

## pseudocode

```c
__int64 __fastcall CClfsHashObject::Start(CClfsHashObject *this, PUCHAR pbSecret, ULONG cbSecret)
{
  BCRYPT_ALG_HANDLE v4; // r12
  UCHAR *v5; // rax
  ULONG v7; // r13d
  ULONG dwFlags; // ebp
  NTSTATUS Hash; // esi
  BCRYPT_HASH_HANDLE *v12; // rdi
  void *v13; // rdx

  v4 = CClfsHashObject::m_hSha256Algorithm;
  v5 = (UCHAR *)*((_QWORD *)this + 1);
  v7 = *(_DWORD *)&CClfsHashObject::m_cbSha256HashObject;
  dwFlags = CClfsHashObject::m_fReusableHash != 0 ? 0x20 : 0;
  if ( !v5 )
  {
    if ( !*(_DWORD *)this )
      v5 = (UCHAR *)ExAllocateFromPagedLookasideList(&CClfsHashObject::m_laSha256ObjectList);
    *((_QWORD *)this + 1) = v5;
    if ( !v5 )
      return 3221225626LL;
  }
  Hash = 0;
  v12 = (BCRYPT_HASH_HANDLE *)((char *)this + 16);
  if ( !*((_QWORD *)this + 2) )
  {
    Hash = BCryptCreateHash(v4, (BCRYPT_HASH_HANDLE *)this + 2, v5, v7, pbSecret, cbSecret, dwFlags);
    if ( Hash < 0 )
    {
      if ( dwFlags
        && (Hash = BCryptCreateHash(
                     v4,
                     (BCRYPT_HASH_HANDLE *)this + 2,
                     *((PUCHAR *)this + 1),
                     v7,
                     pbSecret,
                     cbSecret,
                     0),
            Hash >= 0) )
      {
        CClfsHashObject::m_fReusableHash = 0;
      }
      else
      {
        if ( *v12 )
        {
          BCryptDestroyHash(*v12);
          *v12 = 0;
        }
        v13 = (void *)*((_QWORD *)this + 1);
        if ( v13 )
        {
          CClfsHashObject::BCryptObjectFree(this, v13);
          *((_QWORD *)this + 1) = 0;
        }
      }
    }
  }
  return (unsigned int)Hash;
}

```

## disassembly

```asm
0x1400751d0  push    rbx
0x1400751d2  push    rbp
0x1400751d3  push    rsi
0x1400751d4  push    rdi
0x1400751d5  push    r12
0x1400751d7  push    r13
0x1400751d9  push    r14
0x1400751db  push    r15
0x1400751dd  sub     rsp, 48h
0x1400751e1  mov     al, cs:?m_fReusableHash@CClfsHashObject@@0EA; uchar CClfsHashObject::m_fReusableHash
0x1400751e7  mov     r14d, r8d
0x1400751ea  mov     r12, cs:?m_hSha256Algorithm@CClfsHashObject@@0PEAXEA; void * CClfsHashObject::m_hSha256Algorithm
0x1400751f1  neg     al
0x1400751f3  mov     rax, [rcx+8]
0x1400751f7  mov     r15, rdx
0x1400751fa  mov     r13d, cs:?m_cbSha256HashObject@CClfsHashObject@@0KA; ulong CClfsHashObject::m_cbSha256HashObject
0x140075201  sbb     ebp, ebp
0x140075203  and     ebp, 20h
0x140075206  mov     rbx, rcx
0x140075209  test    rax, rax
0x14007520c  jnz     short loc_140075238
0x14007520e  cmp     [rcx], eax
0x140075210  jnz     short loc_140075225
0x140075212  lea     rcx, ?m_laSha256ObjectList@CClfsHashObject@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140075219  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140075220  nop     dword ptr [rax+rax+00h]
0x140075225  mov     [rbx+8], rax
0x140075229  test    rax, rax
0x14007522c  jnz     short loc_140075238
0x14007522e  mov     eax, 0C000009Ah
0x140075233  jmp     loc_1400752E7
0x140075238  xor     esi, esi
0x14007523a  lea     rdi, [rbx+10h]
0x14007523e  cmp     [rdi], rsi
0x140075241  jnz     loc_1400752E5
0x140075247  mov     [rsp+88h+dwFlags], ebp; dwFlags
0x14007524b  mov     r9d, r13d; cbHashObject
0x14007524e  mov     [rsp+88h+cbSecret], r14d; cbSecret
0x140075253  mov     r8, rax; pbHashObject
0x140075256  mov     rdx, rdi; phHash
0x140075259  mov     [rsp+88h+pbSecret], r15; pbSecret
0x14007525e  mov     rcx, r12; hAlgorithm
0x140075261  call    cs:__imp_BCryptCreateHash
0x140075268  nop     dword ptr [rax+rax+00h]
0x14007526d  mov     esi, eax
0x14007526f  test    eax, eax
0x140075271  jns     short loc_1400752E5
0x140075273  test    ebp, ebp
0x140075275  jz      short loc_1400752B1
0x140075277  mov     r8, [rbx+8]; pbHashObject
0x14007527b  mov     r9d, r13d; cbHashObject
0x14007527e  mov     [rsp+88h+dwFlags], 0; dwFlags
0x140075286  mov     rdx, rdi; phHash
0x140075289  mov     [rsp+88h+cbSecret], r14d; cbSecret
0x14007528e  mov     rcx, r12; hAlgorithm
0x140075291  mov     [rsp+88h+pbSecret], r15; pbSecret
0x140075296  call    cs:__imp_BCryptCreateHash
0x14007529d  nop     dword ptr [rax+rax+00h]
0x1400752a2  mov     esi, eax
0x1400752a4  test    eax, eax
0x1400752a6  js      short loc_1400752B1
0x1400752a8  mov     cs:?m_fReusableHash@CClfsHashObject@@0EA, 0; uchar CClfsHashObject::m_fReusableHash
0x1400752af  jmp     short loc_1400752E5
0x1400752b1  mov     rcx, [rdi]; hHash
0x1400752b4  test    rcx, rcx
0x1400752b7  jz      short loc_1400752CC
0x1400752b9  call    cs:__imp_BCryptDestroyHash
0x1400752c0  nop     dword ptr [rax+rax+00h]
0x1400752c5  mov     qword ptr [rdi], 0
0x1400752cc  mov     rdx, [rbx+8]; void *
0x1400752d0  test    rdx, rdx
0x1400752d3  jz      short loc_1400752E5
0x1400752d5  mov     rcx, rbx; this
0x1400752d8  call    ?BCryptObjectFree@CClfsHashObject@@AEAAXPEAX@Z; CClfsHashObject::BCryptObjectFree(void *)
0x1400752dd  mov     qword ptr [rbx+8], 0
0x1400752e5  mov     eax, esi
0x1400752e7  add     rsp, 48h
0x1400752eb  pop     r15
0x1400752ed  pop     r14
0x1400752ef  pop     r13
0x1400752f1  pop     r12
0x1400752f3  pop     rdi
0x1400752f4  pop     rsi
0x1400752f5  pop     rbp
0x1400752f6  pop     rbx
0x1400752f7  retn
```
