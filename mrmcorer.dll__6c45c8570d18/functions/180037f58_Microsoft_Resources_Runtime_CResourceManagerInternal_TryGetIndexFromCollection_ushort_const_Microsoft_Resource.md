# Microsoft::Resources::Runtime::CResourceManagerInternal::_TryGetIndexFromCollection(ushort const *,Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo * *)

- ea: `0x180037f58`
- end: `0x18003809f`
- name: `?_TryGetIndexFromCollection@CResourceManagerInternal@Runtime@Resources@Microsoft@@AEAA_NPEBGPEAPEAVCSchemaPriIndexInfo@1234@@Z`
- size: `327`
- prototype: `bool(Microsoft::Resources::Runtime::CResourceManagerInternal *__hidden this, const unsigned __int16 *, struct Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo **)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002fe24`
- `0x180032148`
- `0x18003760c`
- `0x180037a7c`
- `0x1800a90b4`
- `0x1800a91c8`

## callees

- `0x180037f58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180037f82`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180037ff9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180037f82`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180037ff9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180037fe0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038046`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180037fe0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038046`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180037fbe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003802a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180037fbe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003802a`

## pseudocode

```c
bool __fastcall Microsoft::Resources::Runtime::CResourceManagerInternal::_TryGetIndexFromCollection(
        RTL_SRWLOCK *this,
        const unsigned __int16 *a2,
        struct Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo **a3)
{
  RTL_SRWLOCK *v3; // r13
  const unsigned __int16 *v6; // r14
  int v7; // ebx
  void *v8; // rsi
  int v9; // r15d
  void *i; // rsi

  v3 = this + 21;
  v6 = 0;
  AcquireSRWLockShared(this + 21);
  v7 = -2147023728;
  v8 = 0;
  v9 = -2147023728;
  while ( v8 < this[20].Ptr )
  {
    if ( CompareStringOrdinal(*((LPCWCH *)this[17].Ptr + 2 * (_QWORD)v8), -1, a2, -1, 1) == 2 )
    {
      if ( v8 < this[20].Ptr )
      {
        v9 = 0;
        v6 = (const unsigned __int16 *)*((_QWORD *)this[17].Ptr + 2 * (_QWORD)v8 + 1);
      }
      break;
    }
    v8 = (char *)v8 + 1;
  }
  ReleaseSRWLockShared(v3);
  if ( v9 >= 0 )
    a2 = v6;
  AcquireSRWLockShared(this + 16);
  for ( i = 0; i < this[15].Ptr; i = (char *)i + 1 )
  {
    if ( CompareStringOrdinal(*((LPCWCH *)this[12].Ptr + 2 * (_QWORD)i), -1, a2, -1, 1) == 2 )
    {
      if ( i < this[15].Ptr )
      {
        v7 = 0;
        *a3 = (struct Microsoft::Resources::Runtime::CResourceManagerInternal::CSchemaPriIndexInfo *)*((_QWORD *)this[12].Ptr + 2 * (_QWORD)i + 1);
      }
      break;
    }
  }
  ReleaseSRWLockShared(this + 16);
  return v7 >= 0;
}

```

## disassembly

```asm
0x180037f58  mov     [rsp+arg_10], r8
0x180037f5d  push    rbx
0x180037f5e  push    rbp
0x180037f5f  push    rsi
0x180037f60  push    rdi
0x180037f61  push    r12
0x180037f63  push    r13
0x180037f65  push    r14
0x180037f67  push    r15
0x180037f69  sub     rsp, 38h
0x180037f6d  lea     r13, [rcx+0A8h]
0x180037f74  mov     rdi, rcx
0x180037f77  mov     rcx, r13; SRWLock
0x180037f7a  mov     r12, rdx
0x180037f7d  xor     r14d, r14d
0x180037f80  xor     ebp, ebp
0x180037f82  call    cs:__imp_AcquireSRWLockShared
0x180037f88  mov     ebx, 80070490h
0x180037f8d  xor     esi, esi
0x180037f8f  mov     r15d, ebx
0x180037f92  cmp     rsi, [rdi+0A0h]
0x180037f99  jnb     short loc_180037FDD
0x180037f9b  mov     rcx, [rdi+88h]
0x180037fa2  or      r9d, 0FFFFFFFFh; cchCount2
0x180037fa6  mov     rax, rsi
0x180037fa9  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x180037fb1  add     rax, rax
0x180037fb4  mov     r8, r12; lpString2
0x180037fb7  or      edx, r9d; cchCount1
0x180037fba  mov     rcx, [rcx+rax*8]; lpString1
0x180037fbe  call    cs:__imp_CompareStringOrdinal
0x180037fc4  cmp     eax, 2
0x180037fc7  jnz     loc_180038065
0x180037fcd  mov     rbp, rsi
0x180037fd0  cmp     rsi, [rdi+0A0h]
0x180037fd7  jb      loc_18003806D
0x180037fdd  mov     rcx, r13; SRWLock
0x180037fe0  call    cs:__imp_ReleaseSRWLockShared
0x180037fe6  test    r15d, r15d
0x180037fe9  cmovns  r12, r14
0x180037fed  lea     r14, [rdi+80h]
0x180037ff4  mov     rcx, r14; SRWLock
0x180037ff7  xor     ebp, ebp
0x180037ff9  call    cs:__imp_AcquireSRWLockShared
0x180037fff  xor     esi, esi
0x180038001  or      r15d, 0FFFFFFFFh
0x180038005  cmp     rsi, [rdi+78h]
0x180038009  jnb     short loc_180038043
0x18003800b  mov     rcx, [rdi+60h]
0x18003800f  mov     rax, rsi
0x180038012  add     rax, rax
0x180038015  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18003801d  mov     r9d, r15d; cchCount2
0x180038020  mov     r8, r12; lpString2
0x180038023  mov     edx, r15d; cchCount1
0x180038026  mov     rcx, [rcx+rax*8]; lpString1
0x18003802a  call    cs:__imp_CompareStringOrdinal
0x180038030  cmp     eax, 2
0x180038033  jz      short loc_18003803A
0x180038035  inc     rsi
0x180038038  jmp     short loc_180038005
0x18003803a  mov     rbp, rsi
0x18003803d  cmp     rsi, [rdi+78h]
0x180038041  jb      short loc_180038084
0x180038043  mov     rcx, r14; SRWLock
0x180038046  call    cs:__imp_ReleaseSRWLockShared
0x18003804c  shr     ebx, 1Fh
0x18003804f  xor     bl, 1
0x180038052  mov     al, bl
0x180038054  add     rsp, 38h
0x180038058  pop     r15
0x18003805a  pop     r14
0x18003805c  pop     r13
0x18003805e  pop     r12
0x180038060  pop     rdi
0x180038061  pop     rsi
0x180038062  pop     rbp
0x180038063  pop     rbx
0x180038064  retn
0x180038065  inc     rsi
0x180038068  jmp     loc_180037F92
0x18003806d  mov     rax, [rdi+88h]
0x180038074  xor     r15d, r15d
0x180038077  add     rbp, rbp
0x18003807a  mov     r14, [rax+rbp*8+8]
0x18003807f  jmp     loc_180037FDD
0x180038084  mov     rdx, [rdi+60h]
0x180038088  xor     ebx, ebx
0x18003808a  mov     rax, [rsp+78h+arg_10]
0x180038092  add     rbp, rbp
0x180038095  mov     r8, [rdx+rbp*8+8]
0x18003809a  mov     [rax], r8
0x18003809d  jmp     short loc_180038043
```
