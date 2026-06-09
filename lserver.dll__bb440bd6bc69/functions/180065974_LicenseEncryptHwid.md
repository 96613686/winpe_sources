# LicenseEncryptHwid

- ea: `0x180065974`
- end: `0x180065ae9`
- name: `LicenseEncryptHwid`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003a5a4`

## callees

- `0x180065974`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x180065a24`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180065a24`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180065ac6`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180065ac6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800659eb`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800659eb`
- `bcrypt!BCryptDestroyKey` at `0x180065aaa`
- `bcrypt!BCryptDestroyKey` at `0x180065aaa`
- `bcrypt!BCryptEncrypt` at `0x180065a73`
- `bcrypt!BCryptEncrypt` at `0x180065a73`

## pseudocode

```c
__int64 __fastcall LicenseEncryptHwid(__int64 a1, _DWORD *a2, __int64 a3, __int64 a4, BCRYPT_ALG_HANDLE phAlgorithm)
{
  UCHAR *pbSecret; // r14
  unsigned int v6; // ebx
  BCRYPT_KEY_HANDLE v10; // rcx
  BCRYPT_KEY_HANDLE phKey; // [rsp+80h] [rbp+30h] BYREF
  ULONG pcbResult; // [rsp+98h] [rbp+48h] BYREF

  pbSecret = (UCHAR *)g_pbSecretKey;
  v6 = 0;
  phAlgorithm = 0;
  phKey = 0;
  pcbResult = 0;
  if ( a1 && *a2 >= 0x14u && a3 && (_DWORD)g_cbSecretKey == 16 && g_pbSecretKey )
  {
    if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"RC4", 0, 0) < 0
      || BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, pbSecret, 0x10u, 0) < 0
      || (v10 = phKey,
          *(_OWORD *)a3 = *(_OWORD *)a1,
          *(_DWORD *)(a3 + 16) = *(_DWORD *)(a1 + 16),
          BCryptEncrypt(v10, (PUCHAR)a3, 0x14u, 0, 0, 0, (PUCHAR)a3, 0x14u, &pcbResult, 0) < 0) )
    {
      v6 = 5;
    }
    else if ( pcbResult == 20 )
    {
      *a2 = 20;
    }
    else
    {
      v6 = 37;
    }
  }
  else
  {
    v6 = 3;
  }
  if ( phKey )
  {
    BCryptDestroyKey(phKey);
    phKey = 0;
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v6;
}

```

## disassembly

```asm
0x180065974  mov     [rsp-28h+arg_8], rbx
0x180065979  mov     [rsp-28h+arg_18], r9d
0x18006597e  push    rbp
0x18006597f  push    rsi
0x180065980  push    rdi
0x180065981  push    r14
0x180065983  push    r15
0x180065985  mov     rbp, rsp
0x180065988  sub     rsp, 50h
0x18006598c  mov     r14, cs:?g_pbSecretKey@@3PEAEEA; uchar * g_pbSecretKey
0x180065993  xor     ebx, ebx
0x180065995  and     [rbp+phAlgorithm], rbx
0x180065999  mov     rdi, r8
0x18006599c  and     [rbp+phKey], rbx
0x1800659a0  mov     rsi, rdx
0x1800659a3  and     [rbp+arg_18], ebx
0x1800659a6  mov     r15, rcx
0x1800659a9  test    rcx, rcx
0x1800659ac  jz      loc_180065A9C
0x1800659b2  cmp     dword ptr [rdx], 14h
0x1800659b5  jb      loc_180065A9C
0x1800659bb  test    r8, r8
0x1800659be  jz      loc_180065A9C
0x1800659c4  cmp     cs:?g_cbSecretKey@@3KA, 10h; ulong g_cbSecretKey
0x1800659cb  jnz     loc_180065A9C
0x1800659d1  test    r14, r14
0x1800659d4  jz      loc_180065A9C
0x1800659da  xor     r9d, r9d; dwFlags
0x1800659dd  lea     rdx, pszAlgId; "RC4"
0x1800659e4  xor     r8d, r8d; pszImplementation
0x1800659e7  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800659eb  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800659f2  nop     dword ptr [rax+rax+00h]
0x1800659f7  test    eax, eax
0x1800659f9  jns     short loc_180065A05
0x1800659fb  mov     ebx, 5
0x180065a00  jmp     loc_180065AA1
0x180065a05  and     dword ptr [rsp+50h+pbOutput], ebx
0x180065a09  lea     rdx, [rbp+phKey]; phKey
0x180065a0d  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180065a11  xor     r9d, r9d; cbKeyObject
0x180065a14  mov     [rsp+50h+cbSecret], 10h; cbIV
0x180065a1c  xor     r8d, r8d; pbKeyObject
0x180065a1f  mov     [rsp+50h+pbSecret], r14; pbIV
0x180065a24  call    cs:__imp_BCryptGenerateSymmetricKey
0x180065a2b  nop     dword ptr [rax+rax+00h]
0x180065a30  test    eax, eax
0x180065a32  js      short loc_1800659FB
0x180065a34  and     [rsp+50h+var_8], ebx
0x180065a38  xor     r9d, r9d; pPaddingInfo
0x180065a3b  movups  xmm0, xmmword ptr [r15]
0x180065a3f  mov     rcx, [rbp+phKey]; hKey
0x180065a43  mov     rdx, rdi; pbInput
0x180065a46  movups  xmmword ptr [rdi], xmm0
0x180065a49  mov     eax, [r15+10h]
0x180065a4d  lea     r8d, [r9+14h]; cbInput
0x180065a51  mov     [rdi+10h], eax
0x180065a54  lea     rax, [rbp+arg_18]
0x180065a58  mov     [rsp+50h+pcbResult], rax; pcbResult
0x180065a5d  mov     [rsp+50h+cbOutput], 14h; cbOutput
0x180065a65  mov     [rsp+50h+pbOutput], rdi; pbOutput
0x180065a6a  and     [rsp+50h+cbSecret], ebx
0x180065a6e  and     [rsp+50h+pbSecret], rbx
0x180065a73  call    cs:__imp_BCryptEncrypt
0x180065a7a  nop     dword ptr [rax+rax+00h]
0x180065a7f  test    eax, eax
0x180065a81  js      loc_1800659FB
0x180065a87  cmp     [rbp+arg_18], 14h
0x180065a8b  jz      short loc_180065A94
0x180065a8d  mov     ebx, 25h ; '%'
0x180065a92  jmp     short loc_180065AA1
0x180065a94  mov     dword ptr [rsi], 14h
0x180065a9a  jmp     short loc_180065AA1
0x180065a9c  mov     ebx, 3
0x180065aa1  mov     rcx, [rbp+phKey]; hKey
0x180065aa5  test    rcx, rcx
0x180065aa8  jz      short loc_180065ABB
0x180065aaa  call    cs:__imp_BCryptDestroyKey
0x180065ab1  nop     dword ptr [rax+rax+00h]
0x180065ab6  and     [rbp+phKey], 0
0x180065abb  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180065abf  test    rcx, rcx
0x180065ac2  jz      short loc_180065AD2
0x180065ac4  xor     edx, edx; dwFlags
0x180065ac6  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180065acd  nop     dword ptr [rax+rax+00h]
0x180065ad2  mov     eax, ebx
0x180065ad4  mov     rbx, [rsp+50h+arg_8]
0x180065adc  add     rsp, 50h
0x180065ae0  pop     r15
0x180065ae2  pop     r14
0x180065ae4  pop     rdi
0x180065ae5  pop     rsi
0x180065ae6  pop     rbp
0x180065ae7  retn
```
