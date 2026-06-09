# GetAlgorithmHandle

- ea: `0x180001de8`
- end: `0x180001eef`
- name: `GetAlgorithmHandle`
- size: `263`
- prototype: `__int64 __fastcall(LPCWSTR pszAlgId)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001690`
- `0x180001acc`
- `0x180003050`

## callees

- `0x180001de8`
- `0x18000b594`
- `0x18000b654`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180001e17`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180001e17`
- `bcrypt!BCryptGetProperty` at `0x180001e4a`
- `bcrypt!BCryptGetProperty` at `0x180001e4a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180001ee7`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180001ee7`

## string_xrefs

- `0x180001ea2`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180001ece`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall GetAlgorithmHandle(LPCWSTR pszAlgId, BCRYPT_HANDLE *a2, UCHAR *a3, ULONG a4)
{
  int v6; // edx
  NTSTATUS v7; // ebx
  NTSTATUS Property; // eax
  ULONG pcbResult; // [rsp+40h] [rbp-18h] BYREF
  BCRYPT_HANDLE hObject; // [rsp+48h] [rbp-10h] BYREF

  hObject = 0;
  pcbResult = 0;
  v7 = BCryptOpenAlgorithmProvider(&hObject, pszAlgId, 0, a4);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        (unsigned int)"Status",
        v7,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        49);
  }
  else
  {
    Property = BCryptGetProperty(hObject, L"ObjectLength", a3, 4u, &pcbResult, 0);
    v7 = Property;
    if ( Property < 0 )
    {
      DebugTraceError(
        (unsigned int)Property,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        4671);
    }
    else
    {
      v7 = 0;
      *a2 = hObject;
      hObject = 0;
    }
  }
  if ( hObject )
    BCryptCloseAlgorithmProvider(hObject, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180001de8  mov     rax, rsp
0x180001deb  mov     [rax+8], rbx
0x180001def  mov     [rax+10h], rsi
0x180001df3  push    rdi
0x180001df4  sub     rsp, 50h
0x180001df8  mov     rdi, rdx
0x180001dfb  mov     qword ptr [rax-10h], 0
0x180001e03  mov     rdx, rcx; pszAlgId
0x180001e06  mov     dword ptr [rax-18h], 0
0x180001e0d  mov     rsi, r8
0x180001e10  lea     rcx, [rax-10h]; phAlgorithm
0x180001e14  xor     r8d, r8d; pszImplementation
0x180001e17  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180001e1d  mov     ebx, eax
0x180001e1f  test    eax, eax
0x180001e21  js      short loc_180001E85
0x180001e23  mov     rcx, [rsp+58h+hObject]; hObject
0x180001e28  lea     rax, [rsp+58h+var_18]
0x180001e2d  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180001e35  lea     rdx, aObjectlength; "ObjectLength"
0x180001e3c  mov     r9d, 4; cbOutput
0x180001e42  mov     [rsp+58h+pcbResult], rax; pcbResult
0x180001e47  mov     r8, rsi; pbOutput
0x180001e4a  call    cs:__imp_BCryptGetProperty
0x180001e50  mov     ebx, eax
0x180001e52  test    eax, eax
0x180001e54  js      short loc_180001EC8
0x180001e56  mov     rax, [rsp+58h+hObject]
0x180001e5b  xor     ebx, ebx
0x180001e5d  mov     [rdi], rax
0x180001e60  mov     [rsp+58h+hObject], 0
0x180001e69  mov     rcx, [rsp+58h+hObject]; hAlgorithm
0x180001e6e  test    rcx, rcx
0x180001e71  jnz     short loc_180001EE5
0x180001e73  mov     rsi, [rsp+58h+arg_8]
0x180001e78  mov     eax, ebx
0x180001e7a  mov     rbx, [rsp+58h+arg_0]
0x180001e7f  add     rsp, 50h
0x180001e83  pop     rdi
0x180001e84  retn
0x180001e85  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e8c  lea     rax, WPP_GLOBAL_Control
0x180001e93  cmp     rcx, rax
0x180001e96  jz      short loc_180001E69
0x180001e98  test    byte ptr [rcx+1Ch], 1
0x180001e9c  jz      short loc_180001E69
0x180001e9e  mov     rcx, [rcx+10h]
0x180001ea2  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001ea9  mov     [rsp+58h+var_28], 1231h
0x180001eb1  lea     r9, aStatus; "Status"
0x180001eb8  mov     qword ptr [rsp+58h+dwFlags], r8
0x180001ebd  mov     dword ptr [rsp+58h+pcbResult], ebx
0x180001ec1  call    WPP_SF_sDsd
0x180001ec6  jmp     short loc_180001E69
0x180001ec8  mov     r9d, 123Fh
0x180001ece  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001ed5  lea     rdx, aStatus; "Status"
0x180001edc  mov     ecx, eax
0x180001ede  call    DebugTraceError
0x180001ee3  jmp     short loc_180001E69
0x180001ee5  xor     edx, edx; dwFlags
0x180001ee7  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180001eed  jmp     short loc_180001E73
```
