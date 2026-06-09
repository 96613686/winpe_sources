# ClasspGenerateMD5BasedGuid

- ea: `0x140059408`
- end: `0x1400594f8`
- name: `ClasspGenerateMD5BasedGuid`
- size: `240`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14005923c`

## callees

- `0x14003e430`
- `0x140059408`

## import_xrefs

- `ksecdd!BCryptHashData` at `0x14005947b`
- `ksecdd!BCryptHashData` at `0x14005947b`
- `ksecdd!BCryptDestroyHash` at `0x1400594bb`
- `ksecdd!BCryptDestroyHash` at `0x1400594bb`
- `ksecdd!BCryptFinishHash` at `0x1400594a1`
- `ksecdd!BCryptFinishHash` at `0x1400594a1`
- `ksecdd!BCryptCreateHash` at `0x140059454`
- `ksecdd!BCryptCreateHash` at `0x140059454`

## pseudocode

```c
__int64 __fastcall ClasspGenerateMD5BasedGuid(PUCHAR pbInput, ULONG cbInput, __int64 a3)
{
  BCRYPT_HASH_HANDLE hHash[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v8; // [rsp+50h] [rbp-28h]

  *(_OWORD *)hHash = 0;
  v8 = 0;
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, hHash, 0, 0, 0, 0, 0) < 0 )
    __fastfail(7u);
  if ( BCryptHashData(hHash[0], pbInput, cbInput, 0) < 0 )
    __fastfail(7u);
  if ( BCryptFinishHash(hHash[0], (PUCHAR)&hHash[1], 0x10u, 0) < 0 )
    __fastfail(7u);
  BCryptDestroyHash(hHash[0]);
  *(BCRYPT_HASH_HANDLE *)a3 = hHash[1];
  *(_QWORD *)(a3 + 8) = v8;
  return 0;
}

```

## disassembly

```asm
0x140059408  mov     r11, rsp
0x14005940b  mov     [r11+20h], rbx
0x14005940f  push    rbp
0x140059410  push    rsi
0x140059411  push    rdi
0x140059412  sub     rsp, 60h
0x140059416  mov     rax, cs:__security_cookie
0x14005941d  xor     rax, rsp
0x140059420  mov     [rsp+78h+var_20], rax
0x140059425  xor     eax, eax
0x140059427  xorps   xmm0, xmm0
0x14005942a  mov     [rsp+78h+dwFlags], eax; dwFlags
0x14005942e  mov     rbx, r8
0x140059431  mov     esi, edx
0x140059433  mov     [rsp+78h+cbSecret], eax; cbSecret
0x140059437  mov     rdi, rcx
0x14005943a  mov     [r11-58h], rax
0x14005943e  movups  xmmword ptr [rsp+78h+hHash], xmm0
0x140059443  lea     ecx, [rax+21h]; hAlgorithm
0x140059446  mov     [r11-28h], rax
0x14005944a  xor     r9d, r9d; cbHashObject
0x14005944d  lea     rdx, [r11-38h]; phHash
0x140059451  xor     r8d, r8d; pbHashObject
0x140059454  call    cs:__imp_BCryptCreateHash
0x14005945b  nop     dword ptr [rax+rax+00h]
0x140059460  mov     ebp, 7
0x140059465  test    eax, eax
0x140059467  jns     short loc_14005946D
0x140059469  mov     ecx, ebp
0x14005946b  int     29h; Win8: RtlFailFast(ecx)
0x14005946d  mov     rcx, [rsp+78h+hHash]; hHash
0x140059472  xor     r9d, r9d; dwFlags
0x140059475  mov     r8d, esi; cbInput
0x140059478  mov     rdx, rdi; pbInput
0x14005947b  call    cs:__imp_BCryptHashData
0x140059482  nop     dword ptr [rax+rax+00h]
0x140059487  test    eax, eax
0x140059489  jns     short loc_140059490
0x14005948b  mov     rcx, rbp
0x14005948e  int     29h; Win8: RtlFailFast(ecx)
0x140059490  mov     rcx, [rsp+78h+hHash]; hHash
0x140059495  lea     rdx, [rsp+78h+hHash+8]; pbOutput
0x14005949a  xor     r9d, r9d; dwFlags
0x14005949d  lea     r8d, [r9+10h]; cbOutput
0x1400594a1  call    cs:__imp_BCryptFinishHash
0x1400594a8  nop     dword ptr [rax+rax+00h]
0x1400594ad  test    eax, eax
0x1400594af  jns     short loc_1400594B6
0x1400594b1  mov     rcx, rbp
0x1400594b4  int     29h; Win8: RtlFailFast(ecx)
0x1400594b6  mov     rcx, [rsp+78h+hHash]; hHash
0x1400594bb  call    cs:__imp_BCryptDestroyHash
0x1400594c2  nop     dword ptr [rax+rax+00h]
0x1400594c7  mov     rax, [rsp+78h+hHash+8]
0x1400594cc  mov     [rbx], rax
0x1400594cf  mov     rax, [rsp+78h+var_28]
0x1400594d4  mov     [rbx+8], rax
0x1400594d8  xor     eax, eax
0x1400594da  mov     rcx, [rsp+78h+var_20]
0x1400594df  xor     rcx, rsp; StackCookie
0x1400594e2  call    __security_check_cookie
0x1400594e7  mov     rbx, [rsp+78h+arg_18]
0x1400594ef  add     rsp, 60h
0x1400594f3  pop     rdi
0x1400594f4  pop     rsi
0x1400594f5  pop     rbp
0x1400594f6  retn
```
