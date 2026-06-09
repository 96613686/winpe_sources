# EfsInitDes

- ea: `0x140009fac`
- end: `0x14000a170`
- name: `EfsInitDes`
- size: `452`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14004da14`

## callees

- `0x140009fac`

## import_xrefs

- `ksecdd!BCryptSetProperty` at `0x14000a034`
- `ksecdd!BCryptSetProperty` at `0x14000a0cd`
- `ksecdd!BCryptSetProperty` at `0x14000a034`
- `ksecdd!BCryptSetProperty` at `0x14000a0cd`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140009ffe`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14000a097`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140009ffe`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14000a097`
- `ksecdd!BCryptGetProperty` at `0x14000a070`
- `ksecdd!BCryptGetProperty` at `0x14000a105`
- `ksecdd!BCryptGetProperty` at `0x14000a070`
- `ksecdd!BCryptGetProperty` at `0x14000a105`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000a13d`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000a154`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000a13d`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000a154`

## pseudocode

```c
__int64 __fastcall EfsInitDes(BCRYPT_ALG_HANDLE *a1, _DWORD *a2, BCRYPT_ALG_HANDLE *a3, _DWORD *a4)
{
  NTSTATUS Property; // ebx
  ULONG pcbResult; // [rsp+30h] [rbp-28h] BYREF
  UCHAR pbOutput[4]; // [rsp+34h] [rbp-24h] BYREF
  UCHAR v12[8]; // [rsp+38h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-18h] BYREF
  BCRYPT_ALG_HANDLE hObject; // [rsp+48h] [rbp-10h] BYREF

  phAlgorithm = 0;
  *(_DWORD *)pbOutput = 0;
  hObject = 0;
  *(_DWORD *)v12 = 0;
  pcbResult = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"DES", 0, 0);
  if ( Property < 0
    || (Property = BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeECB", 0x20u, 0), Property < 0)
    || (Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0), Property < 0)
    || (Property = BCryptOpenAlgorithmProvider(&hObject, L"DESX", 0, 0), Property < 0)
    || (Property = BCryptSetProperty(hObject, L"ChainingMode", (PUCHAR)L"ChainingModeECB", 0x20u, 0), Property < 0)
    || (Property = BCryptGetProperty(hObject, L"ObjectLength", v12, 4u, &pcbResult, 0), Property < 0) )
  {
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    if ( hObject )
      BCryptCloseAlgorithmProvider(hObject, 0);
  }
  else
  {
    *a1 = phAlgorithm;
    *a2 = *(_DWORD *)pbOutput;
    *a3 = hObject;
    *a4 = *(_DWORD *)v12;
  }
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x140009fac  push    rbp
0x140009fae  push    rbx
0x140009faf  push    rsi
0x140009fb0  push    rdi
0x140009fb1  push    r14
0x140009fb3  push    r15
0x140009fb5  mov     rbp, rsp
0x140009fb8  sub     rsp, 58h
0x140009fbc  mov     rdi, r9
0x140009fbf  mov     [rbp+phAlgorithm], 0
0x140009fc7  mov     rsi, r8
0x140009fca  mov     dword ptr [rbp+pbOutput], 0
0x140009fd1  mov     r14, rdx
0x140009fd4  mov     [rbp+hObject], 0
0x140009fdc  mov     r15, rcx
0x140009fdf  mov     dword ptr [rbp+var_20], 0
0x140009fe6  xor     r9d, r9d; dwFlags
0x140009fe9  mov     [rbp+pcbResult], 0
0x140009ff0  xor     r8d, r8d; pszImplementation
0x140009ff3  lea     rdx, aDes; "DES"
0x140009ffa  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140009ffe  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14000a005  nop     dword ptr [rax+rax+00h]
0x14000a00a  mov     ebx, eax
0x14000a00c  test    eax, eax
0x14000a00e  js      loc_14000A132
0x14000a014  mov     rcx, [rbp+phAlgorithm]; hObject
0x14000a018  lea     r8, aChainingmodeec; "ChainingModeECB"
0x14000a01f  mov     r9d, 20h ; ' '; cbInput
0x14000a025  mov     [rsp+58h+dwFlags], 0; dwFlags
0x14000a02d  lea     rdx, aChainingmode; "ChainingMode"
0x14000a034  call    cs:__imp_BCryptSetProperty
0x14000a03b  nop     dword ptr [rax+rax+00h]
0x14000a040  mov     ebx, eax
0x14000a042  test    eax, eax
0x14000a044  js      loc_14000A132
0x14000a04a  mov     rcx, [rbp+phAlgorithm]; hObject
0x14000a04e  lea     rax, [rbp+pcbResult]
0x14000a052  mov     [rsp+58h+var_30], 0; dwFlags
0x14000a05a  lea     r8, [rbp+pbOutput]; pbOutput
0x14000a05e  mov     r9d, 4; cbOutput
0x14000a064  mov     qword ptr [rsp+58h+dwFlags], rax; pcbResult
0x14000a069  lea     rdx, aObjectlength; "ObjectLength"
0x14000a070  call    cs:__imp_BCryptGetProperty
0x14000a077  nop     dword ptr [rax+rax+00h]
0x14000a07c  mov     ebx, eax
0x14000a07e  test    eax, eax
0x14000a080  js      loc_14000A132
0x14000a086  xor     r9d, r9d; dwFlags
0x14000a089  lea     rdx, aDesx; "DESX"
0x14000a090  xor     r8d, r8d; pszImplementation
0x14000a093  lea     rcx, [rbp+hObject]; phAlgorithm
0x14000a097  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14000a09e  nop     dword ptr [rax+rax+00h]
0x14000a0a3  mov     ebx, eax
0x14000a0a5  test    eax, eax
0x14000a0a7  js      loc_14000A132
0x14000a0ad  mov     rcx, [rbp+hObject]; hObject
0x14000a0b1  lea     r8, aChainingmodeec; "ChainingModeECB"
0x14000a0b8  mov     r9d, 20h ; ' '; cbInput
0x14000a0be  mov     [rsp+58h+dwFlags], 0; dwFlags
0x14000a0c6  lea     rdx, aChainingmode; "ChainingMode"
0x14000a0cd  call    cs:__imp_BCryptSetProperty
0x14000a0d4  nop     dword ptr [rax+rax+00h]
0x14000a0d9  mov     ebx, eax
0x14000a0db  test    eax, eax
0x14000a0dd  js      short loc_14000A132
0x14000a0df  mov     rcx, [rbp+hObject]; hObject
0x14000a0e3  lea     rax, [rbp+pcbResult]
0x14000a0e7  mov     [rsp+58h+var_30], 0; dwFlags
0x14000a0ef  lea     r8, [rbp+var_20]; pbOutput
0x14000a0f3  mov     r9d, 4; cbOutput
0x14000a0f9  mov     qword ptr [rsp+58h+dwFlags], rax; pcbResult
0x14000a0fe  lea     rdx, aObjectlength; "ObjectLength"
0x14000a105  call    cs:__imp_BCryptGetProperty
0x14000a10c  nop     dword ptr [rax+rax+00h]
0x14000a111  mov     ebx, eax
0x14000a113  test    eax, eax
0x14000a115  js      short loc_14000A132
0x14000a117  mov     rax, [rbp+phAlgorithm]
0x14000a11b  mov     [r15], rax
0x14000a11e  mov     eax, dword ptr [rbp+pbOutput]
0x14000a121  mov     [r14], eax
0x14000a124  mov     rax, [rbp+hObject]
0x14000a128  mov     [rsi], rax
0x14000a12b  mov     eax, dword ptr [rbp+var_20]
0x14000a12e  mov     [rdi], eax
0x14000a130  jmp     short loc_14000A160
0x14000a132  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x14000a136  test    rcx, rcx
0x14000a139  jz      short loc_14000A149
0x14000a13b  xor     edx, edx; dwFlags
0x14000a13d  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000a144  nop     dword ptr [rax+rax+00h]
0x14000a149  mov     rcx, [rbp+hObject]; hAlgorithm
0x14000a14d  test    rcx, rcx
0x14000a150  jz      short loc_14000A160
0x14000a152  xor     edx, edx; dwFlags
0x14000a154  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000a15b  nop     dword ptr [rax+rax+00h]
0x14000a160  mov     eax, ebx
0x14000a162  add     rsp, 58h
0x14000a166  pop     r15
0x14000a168  pop     r14
0x14000a16a  pop     rdi
0x14000a16b  pop     rsi
0x14000a16c  pop     rbx
0x14000a16d  pop     rbp
0x14000a16e  retn
```
