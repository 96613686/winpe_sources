# CheckCertSAN

- ea: `0x18001e494`
- end: `0x18001e6a0`
- name: `CheckCertSAN`
- size: `524`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800200b0`
- `0x180020ccc`

## callees

- `0x18001e494`
- `0x18004b970`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001e5e6`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001e5e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e579`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e579`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e62f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e679`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e62f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e679`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e565`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e61b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e665`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e565`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e61b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4d1`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e4f6`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e54b`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e597`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e646`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e690`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e4f6`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e54b`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e597`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e646`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e690`
- `CRYPT32!CertGetNameStringW` at `0x18001e52c`
- `CRYPT32!CertGetNameStringW` at `0x18001e5c5`
- `CRYPT32!CertGetNameStringW` at `0x18001e52c`
- `CRYPT32!CertGetNameStringW` at `0x18001e5c5`
- `WINHTTP!WinHttpQueryOption` at `0x18001e4c1`
- `WINHTTP!WinHttpQueryOption` at `0x18001e4c1`

## string_xrefs

- `0x18001e606`: `manage.microsoft.com`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CheckCertSAN(void *a1, __int64 a2)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  DWORD NameStringW; // eax
  __int64 cchNameString; // rdi
  HANDLE ProcessHeap; // rax
  WCHAR *pszNameString; // rax
  WCHAR *v9; // rbx
  DWORD v10; // eax
  size_t v11; // rdi
  size_t v12; // rsi
  const wchar_t *v13; // rbp
  size_t v14; // rax
  HANDLE v15; // rax
  HANDLE v16; // rax
  DWORD v17; // [rsp+68h] [rbp+10h] BYREF
  int v18; // [rsp+6Ch] [rbp+14h]
  PCCERT_CONTEXT pCertContext; // [rsp+70h] [rbp+18h] BYREF

  v18 = HIDWORD(a2);
  v17 = 8;
  pCertContext = 0;
  if ( WinHttpQueryOption(a1, 0x4Eu, &pCertContext, &v17) )
  {
    NameStringW = CertGetNameStringW(pCertContext, 6u, 2u, 0, 0, 0);
    cchNameString = NameStringW;
    if ( NameStringW <= 0x3FFFFFFF )
    {
      ProcessHeap = GetProcessHeap();
      pszNameString = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2 * cchNameString);
      v9 = pszNameString;
      if ( pszNameString )
      {
        v10 = CertGetNameStringW(pCertContext, 6u, 2u, 0, pszNameString, cchNameString);
        v11 = 0;
        v12 = v10;
        while ( v11 < v12 )
        {
          v13 = &v9[v11];
          v14 = wcsnlen(v13, v12 - v11);
          v11 = v14;
          if ( !v14 )
            break;
          if ( v14 == 20 && !wcsncmp_0(L"manage.microsoft.com", v13, 0x14u) )
          {
            v16 = GetProcessHeap();
            HeapFree(v16, 0, v9);
            if ( pCertContext )
              CertFreeCertificateContext(pCertContext);
            return 0;
          }
        }
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v9);
        if ( pCertContext )
          CertFreeCertificateContext(pCertContext);
        return 2147500037LL;
      }
      else
      {
        if ( pCertContext )
          CertFreeCertificateContext(pCertContext);
        return 2147942414LL;
      }
    }
    else
    {
      if ( pCertContext )
        CertFreeCertificateContext(pCertContext);
      return 2147942487LL;
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( pCertContext )
      CertFreeCertificateContext(pCertContext);
    return v3;
  }
}

```

## disassembly

```asm
0x18001e494  mov     rax, rsp
0x18001e497  mov     [rax+8], rbx
0x18001e49b  mov     [rax+10h], rdx
0x18001e49f  push    rbp
0x18001e4a0  push    rsi
0x18001e4a1  push    rdi
0x18001e4a2  sub     rsp, 40h
0x18001e4a6  mov     esi, 8
0x18001e4ab  mov     [rax+10h], esi
0x18001e4ae  mov     qword ptr [rax+18h], 0
0x18001e4b6  lea     r9, [rax+10h]; lpdwBufferLength
0x18001e4ba  lea     r8, [rax+18h]; lpBuffer
0x18001e4be  lea     edx, [rsi+46h]; dwOption
0x18001e4c1  call    cs:__imp_WinHttpQueryOption
0x18001e4c8  nop     dword ptr [rax+rax+00h]
0x18001e4cd  test    eax, eax
0x18001e4cf  jnz     short loc_18001E509
0x18001e4d1  call    cs:__imp_GetLastError
0x18001e4d8  nop     dword ptr [rax+rax+00h]
0x18001e4dd  mov     ebx, eax
0x18001e4df  test    eax, eax
0x18001e4e1  jle     short loc_18001E4EC
0x18001e4e3  movzx   ebx, ax
0x18001e4e6  or      ebx, 80070000h
0x18001e4ec  mov     rcx, [rsp+58h+pCertContext]; pCertContext
0x18001e4f1  test    rcx, rcx
0x18001e4f4  jz      short loc_18001E502
0x18001e4f6  call    cs:__imp_CertFreeCertificateContext
0x18001e4fd  nop     dword ptr [rax+rax+00h]
0x18001e502  mov     eax, ebx
0x18001e504  jmp     loc_18001E657
0x18001e509  mov     [rsp+58h+cchNameString], 0; cchNameString
0x18001e511  mov     [rsp+58h+pszNameString], 0; pszNameString
0x18001e51a  xor     r9d, r9d; pvTypePara
0x18001e51d  lea     ebp, [r9+2]
0x18001e521  mov     r8d, ebp; dwFlags
0x18001e524  lea     edx, [rbp+4]; dwType
0x18001e527  mov     rcx, [rsp+58h+pCertContext]; pCertContext
0x18001e52c  call    cs:__imp_CertGetNameStringW
0x18001e533  nop     dword ptr [rax+rax+00h]
0x18001e538  mov     edi, eax
0x18001e53a  cmp     eax, 3FFFFFFFh
0x18001e53f  jbe     short loc_18001E561
0x18001e541  mov     rcx, [rsp+58h+pCertContext]; pCertContext
0x18001e546  test    rcx, rcx
0x18001e549  jz      short loc_18001E557
0x18001e54b  call    cs:__imp_CertFreeCertificateContext
0x18001e552  nop     dword ptr [rax+rax+00h]
0x18001e557  mov     eax, 80070057h
0x18001e55c  jmp     loc_18001E657
0x18001e561  lea     rbx, [rdi+rdi]
0x18001e565  call    cs:__imp_GetProcessHeap
0x18001e56c  nop     dword ptr [rax+rax+00h]
0x18001e571  mov     rcx, rax; hHeap
0x18001e574  mov     r8, rbx; dwBytes
0x18001e577  mov     edx, esi; dwFlags
0x18001e579  call    cs:__imp_HeapAlloc
0x18001e580  nop     dword ptr [rax+rax+00h]
0x18001e585  mov     rbx, rax
0x18001e588  test    rax, rax
0x18001e58b  jnz     short loc_18001E5AD
0x18001e58d  mov     rcx, [rsp+58h+pCertContext]; pCertContext
0x18001e592  test    rcx, rcx
0x18001e595  jz      short loc_18001E5A3
0x18001e597  call    cs:__imp_CertFreeCertificateContext
0x18001e59e  nop     dword ptr [rax+rax+00h]
0x18001e5a3  mov     eax, 8007000Eh
0x18001e5a8  jmp     loc_18001E657
0x18001e5ad  mov     [rsp+58h+cchNameString], edi; cchNameString
0x18001e5b1  mov     [rsp+58h+pszNameString], rbx; pszNameString
0x18001e5b6  xor     r9d, r9d; pvTypePara
0x18001e5b9  mov     r8d, ebp; dwFlags
0x18001e5bc  lea     edx, [r9+6]; dwType
0x18001e5c0  mov     rcx, [rsp+58h+pCertContext]; pCertContext
0x18001e5c5  call    cs:__imp_CertGetNameStringW
0x18001e5cc  nop     dword ptr [rax+rax+00h]
0x18001e5d1  xor     edi, edi
0x18001e5d3  mov     esi, eax
0x18001e5d5  test    eax, eax
0x18001e5d7  jz      short loc_18001E61B
0x18001e5d9  lea     rbp, [rbx+rdi*2]
0x18001e5dd  mov     rdx, rsi
0x18001e5e0  sub     rdx, rdi; MaxCount
0x18001e5e3  mov     rcx, rbp; Source
0x18001e5e6  call    cs:__imp_wcsnlen
0x18001e5ed  nop     dword ptr [rax+rax+00h]
0x18001e5f2  mov     rdi, rax
0x18001e5f5  test    rax, rax
0x18001e5f8  jz      short loc_18001E61B
0x18001e5fa  cmp     rax, 14h
0x18001e5fe  jnz     short loc_18001E616
0x18001e600  mov     r8d, edi; MaxCount
0x18001e603  mov     rdx, rbp; String2
0x18001e606  lea     rcx, aManageMicrosof; "manage.microsoft.com"
0x18001e60d  call    wcsncmp_0
0x18001e612  test    eax, eax
0x18001e614  jz      short loc_18001E665
0x18001e616  cmp     rdi, rsi
0x18001e619  jb      short loc_18001E5D9
0x18001e61b  call    cs:__imp_GetProcessHeap
0x18001e622  nop     dword ptr [rax+rax+00h]
0x18001e627  mov     rcx, rax; hHeap
0x18001e62a  mov     r8, rbx; lpMem
0x18001e62d  xor     edx, edx; dwFlags
0x18001e62f  call    cs:__imp_HeapFree
0x18001e636  nop     dword ptr [rax+rax+00h]
0x18001e63b  nop
0x18001e63c  mov     rcx, [rsp+58h+pCertContext]; pCertContext
0x18001e641  test    rcx, rcx
0x18001e644  jz      short loc_18001E652
0x18001e646  call    cs:__imp_CertFreeCertificateContext
0x18001e64d  nop     dword ptr [rax+rax+00h]
0x18001e652  mov     eax, 80004005h
0x18001e657  mov     rbx, [rsp+58h+arg_0]
0x18001e65c  add     rsp, 40h
0x18001e660  pop     rdi
0x18001e661  pop     rsi
0x18001e662  pop     rbp
0x18001e663  retn
0x18001e665  call    cs:__imp_GetProcessHeap
0x18001e66c  nop     dword ptr [rax+rax+00h]
0x18001e671  mov     rcx, rax; hHeap
0x18001e674  mov     r8, rbx; lpMem
0x18001e677  xor     edx, edx; dwFlags
0x18001e679  call    cs:__imp_HeapFree
0x18001e680  nop     dword ptr [rax+rax+00h]
0x18001e685  nop
0x18001e686  mov     rcx, [rsp+58h+pCertContext]; pCertContext
0x18001e68b  test    rcx, rcx
0x18001e68e  jz      short loc_18001E69C
0x18001e690  call    cs:__imp_CertFreeCertificateContext
0x18001e697  nop     dword ptr [rax+rax+00h]
0x18001e69c  xor     eax, eax
0x18001e69e  jmp     short loc_18001E657
```
