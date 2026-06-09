# CDriverPackageDetailed::ParseCatFile(ushort const *)

- ea: `0x18004e0ec`
- end: `0x18004e1b5`
- name: `?ParseCatFile@CDriverPackageDetailed@@AEAAHPEBG@Z`
- size: `201`
- prototype: `int(CDriverPackageDetailed *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004eed0`

## callees

- `0x18004e0ec`
- `0x18005e328`
- `0x18010d8dc`

## import_xrefs

- `WINTRUST!CryptCATClose` at `0x18004e192`
- `WINTRUST!CryptCATClose` at `0x18004e192`
- `WINTRUST!CryptCATOpen` at `0x18004e13d`
- `WINTRUST!CryptCATOpen` at `0x18004e13d`
- `WINTRUST!CryptCATEnumerateCatAttr` at `0x18004e16d`
- `WINTRUST!CryptCATEnumerateCatAttr` at `0x18004e16d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18004e11c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18004e11c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18004e1a4`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18004e1a4`

## pseudocode

```c
__int64 __fastcall CDriverPackageDetailed::ParseCatFile(CDriverPackageDetailed *this, WCHAR *a2)
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
          v4 = PwstrToWstring(v8->pbValue, (char *)this + 216);
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
0x18004e0ec  push    rbx
0x18004e0ee  push    rbp
0x18004e0ef  push    rsi
0x18004e0f0  push    rdi
0x18004e0f1  sub     rsp, 38h
0x18004e0f5  mov     rbx, rdx
0x18004e0f8  mov     [rsp+58h+phProv], 0
0x18004e101  mov     rbp, rcx
0x18004e104  mov     [rsp+58h+dwFlags], 0F0000000h; dwFlags
0x18004e10c  xor     edx, edx; szContainer
0x18004e10e  lea     rcx, [rsp+58h+phProv]; phProv
0x18004e113  mov     r9d, 1; dwProvType
0x18004e119  xor     r8d, r8d; szProvider
0x18004e11c  call    cs:__imp_CryptAcquireContextW
0x18004e122  mov     edi, eax
0x18004e124  test    eax, eax
0x18004e126  jz      short loc_18004E198
0x18004e128  mov     r8, [rsp+58h+phProv]; hProv
0x18004e12d  xor     r9d, r9d; dwPublicVersion
0x18004e130  xor     edx, edx; fdwOpenFlags
0x18004e132  mov     [rsp+58h+dwFlags], 0; dwEncodingType
0x18004e13a  mov     rcx, rbx; pwszFileName
0x18004e13d  call    cs:__imp_CryptCATOpen
0x18004e143  mov     rsi, rax
0x18004e146  test    rax, rax
0x18004e149  jnz     short loc_18004E14F
0x18004e14b  xor     edi, edi
0x18004e14d  jmp     short loc_18004E198
0x18004e14f  xor     edx, edx
0x18004e151  jmp     short loc_18004E16A
0x18004e153  mov     rcx, [rbx+8]; String1
0x18004e157  lea     rdx, aSubmissionId; "Submission ID"
0x18004e15e  call    wcscmp_0
0x18004e163  test    eax, eax
0x18004e165  jz      short loc_18004E17D
0x18004e167  mov     rdx, rbx; pPrevAttr
0x18004e16a  mov     rcx, rsi; hCatalog
0x18004e16d  call    cs:__imp_CryptCATEnumerateCatAttr
0x18004e173  mov     rbx, rax
0x18004e176  test    rax, rax
0x18004e179  jnz     short loc_18004E153
0x18004e17b  jmp     short loc_18004E18F
0x18004e17d  mov     rcx, [rbx+18h]
0x18004e181  lea     rdx, [rbp+0D8h]
0x18004e188  call    ?PwstrToWstring@@YAKPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PwstrToWstring(ushort const *,std::wstring &)
0x18004e18d  mov     edi, eax
0x18004e18f  mov     rcx, rsi; hCatalog
0x18004e192  call    cs:__imp_CryptCATClose
0x18004e198  mov     rcx, [rsp+58h+phProv]; hProv
0x18004e19d  test    rcx, rcx
0x18004e1a0  jz      short loc_18004E1AA
0x18004e1a2  xor     edx, edx; dwFlags
0x18004e1a4  call    cs:__imp_CryptReleaseContext
0x18004e1aa  mov     eax, edi
0x18004e1ac  add     rsp, 38h
0x18004e1b0  pop     rdi
0x18004e1b1  pop     rsi
0x18004e1b2  pop     rbp
0x18004e1b3  pop     rbx
0x18004e1b4  retn
```
