# LsaDbpDsTruncateNameToFitCN(_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x180020398`
- end: `0x180020513`
- name: `?LsaDbpDsTruncateNameToFitCN@@YAJPEAU_UNICODE_STRING@@0@Z`
- size: `379`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180014358`
- `0x18001f890`

## callees

- `0x180001670`
- `0x180020398`
- `0x18003ad30`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180020436`
- `bcrypt!BCryptCreateHash` at `0x180020436`
- `bcrypt!BCryptHashData` at `0x18002045b`
- `bcrypt!BCryptHashData` at `0x18002045b`
- `bcrypt!BCryptFinishHash` at `0x18002047b`
- `bcrypt!BCryptFinishHash` at `0x18002047b`
- `bcrypt!BCryptDestroyHash` at `0x18002048f`
- `bcrypt!BCryptDestroyHash` at `0x18002048f`
- `LSASRV!LsapAllocateLsaHeap` at `0x1800203cc`
- `LSASRV!LsapAllocateLsaHeap` at `0x1800203cc`

## pseudocode

```c
__int64 __fastcall LsaDbpDsTruncateNameToFitCN(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2)
{
  __int64 Length; // rcx
  WCHAR *LsaHeap; // rax
  USHORT v7; // ax
  size_t v8; // r8
  PWSTR Buffer; // rdx
  PWSTR v10; // rcx
  __int64 v11; // r8
  __int16 v12; // ax
  __int64 v13; // rcx
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v15; // [rsp+50h] [rbp-28h]

  Length = a1->Length;
  *(_OWORD *)phHash = 0;
  v15 = 0;
  LsaHeap = (WCHAR *)LsapAllocateLsaHeap(Length);
  a2->Buffer = LsaHeap;
  if ( !LsaHeap )
    return 3221225626LL;
  if ( a1->Length > 0x80u )
  {
    if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0) < 0 )
      __fastfail(7u);
    if ( BCryptHashData(phHash[0], (PUCHAR)a1->Buffer, a1->Length, 0) < 0 )
      __fastfail(7u);
    if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
      __fastfail(7u);
    BCryptDestroyHash(phHash[0]);
    v8 = a1->Length;
    Buffer = a1->Buffer;
    v10 = a2->Buffer;
    phHash[0] = 0;
    memcpy_0(v10, Buffer, v8);
    v11 = 0;
    a2->Buffer[46] = 45;
    do
    {
      v12 = *((_BYTE *)&phHash[1] + v11) & 0xF;
      v13 = (unsigned int)(v11 + 47);
      v11 = (unsigned int)(v11 + 1);
      a2->Buffer[v13] = v12 + 55 + ((unsigned __int8)v12 < 0xAu ? 0xFFF9 : 0);
    }
    while ( (unsigned int)v11 < 0x10 );
    *(_DWORD *)&a2->Length = 8388736;
  }
  else
  {
    memcpy_0(LsaHeap, a1->Buffer, a1->Length);
    v7 = a1->Length;
    a2->MaximumLength = a1->Length;
    a2->Length = v7;
  }
  return 0;
}

```

## disassembly

```asm
0x180020398  mov     [rsp+arg_10], rbx
0x18002039d  push    rbp
0x18002039e  push    rdi
0x18002039f  push    r14
0x1800203a1  sub     rsp, 60h
0x1800203a5  mov     rax, cs:__security_cookie
0x1800203ac  xor     rax, rsp
0x1800203af  mov     [rsp+78h+var_20], rax
0x1800203b4  mov     rdi, rcx
0x1800203b7  xorps   xmm0, xmm0
0x1800203ba  movzx   ecx, word ptr [rcx]
0x1800203bd  xor     eax, eax
0x1800203bf  movups  xmmword ptr [rsp+78h+phHash], xmm0
0x1800203c4  mov     [rsp+78h+var_28], rax
0x1800203c9  mov     rbx, rdx
0x1800203cc  call    cs:__imp_LsapAllocateLsaHeap
0x1800203d2  mov     [rbx+8], rax
0x1800203d6  test    rax, rax
0x1800203d9  jnz     short loc_1800203E5
0x1800203db  mov     eax, 0C000009Ah
0x1800203e0  jmp     loc_1800204F5
0x1800203e5  mov     ebp, 80h
0x1800203ea  cmp     [rdi], bp
0x1800203ed  ja      short loc_18002040E
0x1800203ef  movzx   r8d, word ptr [rdi]; Size
0x1800203f3  mov     rcx, rax; void *
0x1800203f6  mov     rdx, [rdi+8]; Src
0x1800203fa  call    memcpy_0
0x1800203ff  movzx   eax, word ptr [rdi]
0x180020402  mov     [rbx+2], ax
0x180020406  mov     [rbx], ax
0x180020409  jmp     loc_1800204F3
0x18002040e  xor     r9d, r9d; cbHashObject
0x180020411  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180020419  mov     [rsp+78h+cbSecret], 0; cbSecret
0x180020421  lea     rdx, [rsp+78h+phHash]; phHash
0x180020426  xor     r8d, r8d; pbHashObject
0x180020429  mov     [rsp+78h+pbSecret], 0; pbSecret
0x180020432  lea     ecx, [r9+21h]; hAlgorithm
0x180020436  call    cs:__imp_BCryptCreateHash
0x18002043c  mov     r14d, 7
0x180020442  test    eax, eax
0x180020444  jns     short loc_18002044B
0x180020446  mov     ecx, r14d
0x180020449  int     29h; Win8: RtlFailFast(ecx)
0x18002044b  movzx   r8d, word ptr [rdi]; cbInput
0x18002044f  xor     r9d, r9d; dwFlags
0x180020452  mov     rdx, [rdi+8]; pbInput
0x180020456  mov     rcx, [rsp+78h+phHash]; hHash
0x18002045b  call    cs:__imp_BCryptHashData
0x180020461  test    eax, eax
0x180020463  jns     short loc_18002046A
0x180020465  mov     rcx, r14
0x180020468  int     29h; Win8: RtlFailFast(ecx)
0x18002046a  mov     rcx, [rsp+78h+phHash]; hHash
0x18002046f  lea     rdx, [rsp+78h+phHash+8]; pbOutput
0x180020474  xor     r9d, r9d; dwFlags
0x180020477  lea     r8d, [r9+10h]; cbOutput
0x18002047b  call    cs:__imp_BCryptFinishHash
0x180020481  test    eax, eax
0x180020483  jns     short loc_18002048A
0x180020485  mov     rcx, r14
0x180020488  int     29h; Win8: RtlFailFast(ecx)
0x18002048a  mov     rcx, [rsp+78h+phHash]; hHash
0x18002048f  call    cs:__imp_BCryptDestroyHash
0x180020495  movzx   r8d, word ptr [rdi]; Size
0x180020499  mov     rdx, [rdi+8]; Src
0x18002049d  mov     rcx, [rbx+8]; void *
0x1800204a1  mov     [rsp+78h+phHash], 0
0x1800204aa  call    memcpy_0
0x1800204af  mov     rax, [rbx+8]
0x1800204b3  xor     r8d, r8d
0x1800204b6  mov     word ptr [rax+5Ch], 2Dh ; '-'
0x1800204bc  mov     cl, byte ptr [rsp+r8+78h+phHash+8]
0x1800204c1  and     cl, 0Fh
0x1800204c4  movzx   eax, cl
0x1800204c7  lea     ecx, [r8+2Fh]
0x1800204cb  cmp     al, 0Ah
0x1800204cd  sbb     dx, dx
0x1800204d0  add     ax, 37h ; '7'
0x1800204d4  and     dx, 0FFF9h
0x1800204d9  inc     r8d
0x1800204dc  add     dx, ax
0x1800204df  mov     rax, [rbx+8]
0x1800204e3  mov     [rax+rcx*2], dx
0x1800204e7  cmp     r8d, 10h
0x1800204eb  jb      short loc_1800204BC
0x1800204ed  mov     dword ptr [rbx], 800080h
0x1800204f3  xor     eax, eax
0x1800204f5  mov     rcx, [rsp+78h+var_20]
0x1800204fa  xor     rcx, rsp; StackCookie
0x1800204fd  call    __security_check_cookie
0x180020502  mov     rbx, [rsp+78h+arg_10]
0x18002050a  add     rsp, 60h
0x18002050e  pop     r14
0x180020510  pop     rdi
0x180020511  pop     rbp
0x180020512  retn
```
