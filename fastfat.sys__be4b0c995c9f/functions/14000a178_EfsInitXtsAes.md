# EfsInitXtsAes

- ea: `0x14000a178`
- end: `0x14000a26d`
- name: `EfsInitXtsAes`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14004da14`

## callees

- `0x14000a178`

## import_xrefs

- `ksecdd!BCryptSetProperty` at `0x14000a1e6`
- `ksecdd!BCryptSetProperty` at `0x14000a1e6`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14000a1b5`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14000a1b5`
- `ksecdd!BCryptGetProperty` at `0x14000a21f`
- `ksecdd!BCryptGetProperty` at `0x14000a21f`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000a24e`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000a24e`

## pseudocode

```c
__int64 __fastcall EfsInitXtsAes(BCRYPT_HANDLE *a1, UCHAR *a2)
{
  NTSTATUS Property; // ebx
  BCRYPT_HANDLE v5; // rcx
  BCRYPT_HANDLE hObject; // [rsp+30h] [rbp-18h] BYREF
  int pbInput; // [rsp+60h] [rbp+18h] BYREF
  ULONG pcbResult; // [rsp+68h] [rbp+20h] BYREF

  hObject = 0;
  pbInput = 512;
  pcbResult = 0;
  Property = BCryptOpenAlgorithmProvider(&hObject, L"XTS-AES", 0, 0);
  if ( Property < 0
    || (Property = BCryptSetProperty(hObject, L"MessageBlockLength", (PUCHAR)&pbInput, 4u, 0), Property < 0)
    || (Property = BCryptGetProperty(hObject, L"ObjectLength", a2, 4u, &pcbResult, 0), Property < 0) )
  {
    v5 = hObject;
  }
  else
  {
    v5 = 0;
    *a1 = hObject;
    hObject = 0;
  }
  if ( v5 )
    BCryptCloseAlgorithmProvider(v5, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x14000a178  mov     rax, rsp
0x14000a17b  mov     [rax+8], rbx
0x14000a17f  mov     [rax+10h], rsi
0x14000a183  push    rdi
0x14000a184  sub     rsp, 40h
0x14000a188  mov     rsi, rdx
0x14000a18b  mov     qword ptr [rax-18h], 0
0x14000a193  mov     rdi, rcx
0x14000a196  mov     dword ptr [rax+18h], 200h
0x14000a19d  lea     rdx, aXtsAes; "XTS-AES"
0x14000a1a4  mov     dword ptr [rax+20h], 0
0x14000a1ab  lea     rcx, [rax-18h]; phAlgorithm
0x14000a1af  xor     r9d, r9d; dwFlags
0x14000a1b2  xor     r8d, r8d; pszImplementation
0x14000a1b5  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14000a1bc  nop     dword ptr [rax+rax+00h]
0x14000a1c1  mov     ebx, eax
0x14000a1c3  test    eax, eax
0x14000a1c5  js      short loc_14000A242
0x14000a1c7  mov     rcx, [rsp+48h+hObject]; hObject
0x14000a1cc  lea     r8, [rsp+48h+pbInput]; pbInput
0x14000a1d1  mov     r9d, 4; cbInput
0x14000a1d7  mov     [rsp+48h+dwFlags], 0; dwFlags
0x14000a1df  lea     rdx, aMessageblockle; "MessageBlockLength"
0x14000a1e6  call    cs:__imp_BCryptSetProperty
0x14000a1ed  nop     dword ptr [rax+rax+00h]
0x14000a1f2  mov     ebx, eax
0x14000a1f4  test    eax, eax
0x14000a1f6  js      short loc_14000A242
0x14000a1f8  mov     rcx, [rsp+48h+hObject]; hObject
0x14000a1fd  lea     rax, [rsp+48h+pcbResult]
0x14000a202  mov     [rsp+48h+var_20], 0; dwFlags
0x14000a20a  lea     rdx, aObjectlength; "ObjectLength"
0x14000a211  mov     r9d, 4; cbOutput
0x14000a217  mov     qword ptr [rsp+48h+dwFlags], rax; pcbResult
0x14000a21c  mov     r8, rsi; pbOutput
0x14000a21f  call    cs:__imp_BCryptGetProperty
0x14000a226  nop     dword ptr [rax+rax+00h]
0x14000a22b  mov     ebx, eax
0x14000a22d  test    eax, eax
0x14000a22f  js      short loc_14000A242
0x14000a231  mov     rax, [rsp+48h+hObject]
0x14000a236  xor     ecx, ecx
0x14000a238  mov     [rdi], rax
0x14000a23b  mov     [rsp+48h+hObject], rcx
0x14000a240  jmp     short loc_14000A247
0x14000a242  mov     rcx, [rsp+48h+hObject]; hAlgorithm
0x14000a247  test    rcx, rcx
0x14000a24a  jz      short loc_14000A25A
0x14000a24c  xor     edx, edx; dwFlags
0x14000a24e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000a255  nop     dword ptr [rax+rax+00h]
0x14000a25a  mov     rsi, [rsp+48h+arg_8]
0x14000a25f  mov     eax, ebx
0x14000a261  mov     rbx, [rsp+48h+arg_0]
0x14000a266  add     rsp, 40h
0x14000a26a  pop     rdi
0x14000a26b  retn
```
