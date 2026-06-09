# CDriverPackage::ParseCatFile(ushort const *)

- ea: `0x18004ce48`
- end: `0x18004cf11`
- name: `?ParseCatFile@CDriverPackage@@AEAAHPEBG@Z`
- size: `201`
- prototype: `int(CDriverPackage *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004f594`
- `0x180052200`

## callees

- `0x18004ce48`
- `0x18005e328`
- `0x18010d8dc`

## import_xrefs

- `WINTRUST!CryptCATClose` at `0x18004ceee`
- `WINTRUST!CryptCATClose` at `0x18004ceee`
- `WINTRUST!CryptCATOpen` at `0x18004ce99`
- `WINTRUST!CryptCATOpen` at `0x18004ce99`
- `WINTRUST!CryptCATEnumerateCatAttr` at `0x18004cec9`
- `WINTRUST!CryptCATEnumerateCatAttr` at `0x18004cec9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18004ce78`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18004ce78`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18004cf00`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18004cf00`

## pseudocode

```c
__int64 __fastcall CDriverPackage::ParseCatFile(CDriverPackage *this, WCHAR *a2)
{
  unsigned int v4; // edi
  HANDLE v5; // rsi
  CRYPTCATATTRIBUTE *i; // rdx
  CRYPTCATATTRIBUTE *v7; // rax
  CRYPTCATATTRIBUTE *v8; // rbx
  HCRYPTPROV phProv; // [rsp+70h] [rbp+18h] BYREF

  phProv = 0;
  v4 = CryptAcquireContextW(&phProv, 0, 0, 1u, 0xF0000000);
  if ( v4 )
  {
    v5 = CryptCATOpen(a2, 0, phProv, 0, 0);
    if ( v5 )
    {
      for ( i = 0; ; i = v8 )
      {
        v7 = CryptCATEnumerateCatAttr(v5, i);
        v8 = v7;
        if ( !v7 )
          break;
        if ( !wcscmp_0(v7->pwszReferenceTag, L"Submission ID") )
        {
          v4 = PwstrToWstring(v8->pbValue, (char *)this + 224);
          break;
        }
      }
      CryptCATClose(v5);
    }
    else
    {
      v4 = 0;
    }
  }
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  return v4;
}

```

## disassembly

```asm
0x18004ce48  push    rbx
0x18004ce4a  push    rbp
0x18004ce4b  push    rsi
0x18004ce4c  push    rdi
0x18004ce4d  sub     rsp, 38h
0x18004ce51  mov     rbx, rdx
0x18004ce54  mov     [rsp+58h+phProv], 0
0x18004ce5d  mov     rbp, rcx
0x18004ce60  mov     [rsp+58h+dwFlags], 0F0000000h; dwFlags
0x18004ce68  xor     edx, edx; szContainer
0x18004ce6a  lea     rcx, [rsp+58h+phProv]; phProv
0x18004ce6f  mov     r9d, 1; dwProvType
0x18004ce75  xor     r8d, r8d; szProvider
0x18004ce78  call    cs:__imp_CryptAcquireContextW
0x18004ce7e  mov     edi, eax
0x18004ce80  test    eax, eax
0x18004ce82  jz      short loc_18004CEF4
0x18004ce84  mov     r8, [rsp+58h+phProv]; hProv
0x18004ce89  xor     r9d, r9d; dwPublicVersion
0x18004ce8c  xor     edx, edx; fdwOpenFlags
0x18004ce8e  mov     [rsp+58h+dwFlags], 0; dwEncodingType
0x18004ce96  mov     rcx, rbx; pwszFileName
0x18004ce99  call    cs:__imp_CryptCATOpen
0x18004ce9f  mov     rsi, rax
0x18004cea2  test    rax, rax
0x18004cea5  jnz     short loc_18004CEAB
0x18004cea7  xor     edi, edi
0x18004cea9  jmp     short loc_18004CEF4
0x18004ceab  xor     edx, edx
0x18004cead  jmp     short loc_18004CEC6
0x18004ceaf  mov     rcx, [rbx+8]; String1
0x18004ceb3  lea     rdx, aSubmissionId; "Submission ID"
0x18004ceba  call    wcscmp_0
0x18004cebf  test    eax, eax
0x18004cec1  jz      short loc_18004CED9
0x18004cec3  mov     rdx, rbx; pPrevAttr
0x18004cec6  mov     rcx, rsi; hCatalog
0x18004cec9  call    cs:__imp_CryptCATEnumerateCatAttr
0x18004cecf  mov     rbx, rax
0x18004ced2  test    rax, rax
0x18004ced5  jnz     short loc_18004CEAF
0x18004ced7  jmp     short loc_18004CEEB
0x18004ced9  mov     rcx, [rbx+18h]
0x18004cedd  lea     rdx, [rbp+0E0h]
0x18004cee4  call    ?PwstrToWstring@@YAKPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PwstrToWstring(ushort const *,std::wstring &)
0x18004cee9  mov     edi, eax
0x18004ceeb  mov     rcx, rsi; hCatalog
0x18004ceee  call    cs:__imp_CryptCATClose
0x18004cef4  mov     rcx, [rsp+58h+phProv]; hProv
0x18004cef9  test    rcx, rcx
0x18004cefc  jz      short loc_18004CF06
0x18004cefe  xor     edx, edx; dwFlags
0x18004cf00  call    cs:__imp_CryptReleaseContext
0x18004cf06  mov     eax, edi
0x18004cf08  add     rsp, 38h
0x18004cf0c  pop     rdi
0x18004cf0d  pop     rsi
0x18004cf0e  pop     rbp
0x18004cf0f  pop     rbx
0x18004cf10  retn
```
