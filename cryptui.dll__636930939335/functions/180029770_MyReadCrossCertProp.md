# _MyReadCrossCertProp

- ea: `0x180029770`
- end: `0x180029993`
- name: `_MyReadCrossCertProp`
- size: `547`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180029770`

## import_xrefs

- `msvcrt!_wcsdup` at `0x180029925`
- `msvcrt!_wcsdup` at `0x180029925`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800297e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029876`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800298f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800297e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029876`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800298f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800298c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029948`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029955`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002995e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029967`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029972`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800298c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029948`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029955`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002995e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029967`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029972`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002981d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002981d`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800297a8`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180029813`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800297a8`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180029813`
- `CRYPT32!CryptDecodeObject` at `0x180029866`
- `CRYPT32!CryptDecodeObject` at `0x1800298ae`
- `CRYPT32!CryptDecodeObject` at `0x180029866`
- `CRYPT32!CryptDecodeObject` at `0x1800298ae`

## pseudocode

```c
__int64 __fastcall MyReadCrossCertProp(PCCERT_CONTEXT pCertContext, _QWORD *a2, _DWORD *a3)
{
  unsigned int v3; // r15d
  _DWORD *pvStructInfo; // r14
  unsigned int v8; // ebx
  signed int LastError; // eax
  void *v10; // rbp
  HLOCAL v11; // rax
  _QWORD *v12; // rsi
  __int64 v13; // rdi
  unsigned int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  wchar_t *v17; // rax
  DWORD pcbStructInfo[22]; // [rsp+40h] [rbp-58h] BYREF
  SIZE_T uBytes; // [rsp+B8h] [rbp+20h] BYREF

  v3 = 0;
  pcbStructInfo[0] = 0;
  LODWORD(uBytes) = 0;
  pvStructInfo = 0;
  v8 = 0;
  if ( CertGetCertificateContextProperty(pCertContext, 0x17u, 0, (DWORD *)&uBytes) )
  {
    v11 = LocalAlloc(0x40u, (unsigned int)uBytes);
    v10 = v11;
    if ( !v11 )
    {
LABEL_7:
      v8 = -2147024882;
      goto LABEL_27;
    }
    if ( CertGetCertificateContextProperty(pCertContext, 0x17u, v11, (DWORD *)&uBytes)
      && CryptDecodeObject(0x10001u, (LPCSTR)0x3A, (const BYTE *)v10, uBytes, 0, 0, pcbStructInfo) )
    {
      pvStructInfo = LocalAlloc(0x40u, pcbStructInfo[0]);
      if ( !pvStructInfo )
        goto LABEL_7;
      if ( CryptDecodeObject(0x10001u, (LPCSTR)0x3A, (const BYTE *)v10, uBytes, 0, pvStructInfo, pcbStructInfo) )
      {
        v12 = 0;
        v13 = 0;
        LocalFree(v10);
        v14 = pvStructInfo[1];
        if ( v14 )
        {
          v10 = 0;
          if ( v14 >= 0x1FFFFFFF )
            goto LABEL_7;
          v12 = LocalAlloc(0x40u, 8LL * v14);
          if ( !v12 )
            goto LABEL_7;
          while ( v3 < pvStructInfo[1] )
          {
            v15 = *((_QWORD *)pvStructInfo + 1);
            if ( *(_DWORD *)(v15 + 16LL * v3) )
            {
              v16 = *(_QWORD *)(v15 + 16LL * v3 + 8);
              if ( *(_DWORD *)v16 == 7 )
              {
                v17 = _wcsdup(*(const wchar_t **)(v16 + 8));
                v12[v13] = v17;
                if ( !v17 )
                {
                  v8 = -2147024882;
                  while ( (_DWORD)v13 )
                  {
                    LODWORD(v13) = v13 - 1;
                    LocalFree((HLOCAL)v12[(unsigned int)v13]);
                  }
                  LocalFree(v12);
                  goto LABEL_27;
                }
                v13 = (unsigned int)(v13 + 1);
              }
            }
            ++v3;
          }
        }
        LocalFree(pvStructInfo);
        *a2 = v12;
        *a3 = v13;
        return v8;
      }
    }
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError <= 0 )
      goto LABEL_27;
    goto LABEL_10;
  }
  LastError = GetLastError();
  if ( LastError != -2146885628 )
  {
    v10 = 0;
    if ( LastError <= 0 )
    {
      v8 = LastError;
LABEL_27:
      LocalFree(pvStructInfo);
      LocalFree(v10);
      return v8;
    }
LABEL_10:
    v8 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_27;
  }
  *a2 = 0;
  *a3 = 0;
  return v8;
}

```

## disassembly

```asm
0x180029770  mov     rax, rsp
0x180029773  push    rbx
0x180029774  push    rbp
0x180029775  push    rsi
0x180029776  push    rdi
0x180029777  push    r12
0x180029779  push    r13
0x18002977b  push    r14
0x18002977d  push    r15
0x18002977f  sub     rsp, 58h
0x180029783  xor     r15d, r15d
0x180029786  lea     r9, [rax+20h]; pcbData
0x18002978a  mov     r12, r8
0x18002978d  mov     [rax-58h], r15d
0x180029791  mov     r13, rdx
0x180029794  mov     [rax+20h], r15d
0x180029798  xor     r8d, r8d; pvData
0x18002979b  mov     rdi, rcx
0x18002979e  lea     edx, [r15+17h]; dwPropId
0x1800297a2  mov     r14d, r15d
0x1800297a5  mov     ebx, r15d
0x1800297a8  call    cs:__imp_CertGetCertificateContextProperty
0x1800297ae  test    eax, eax
0x1800297b0  jnz     short loc_1800297DA
0x1800297b2  call    cs:__imp_GetLastError
0x1800297b8  cmp     eax, 80092004h
0x1800297bd  jnz     short loc_1800297CC
0x1800297bf  mov     [r13+0], r15
0x1800297c3  mov     [r12], r15d
0x1800297c7  jmp     loc_180029980
0x1800297cc  mov     rbp, r15
0x1800297cf  test    eax, eax
0x1800297d1  jg      short loc_18002982D
0x1800297d3  mov     ebx, eax
0x1800297d5  jmp     loc_18002995B
0x1800297da  mov     edx, dword ptr [rsp+98h+uBytes]; uBytes
0x1800297e1  mov     esi, 40h ; '@'
0x1800297e6  mov     ecx, esi; uFlags
0x1800297e8  call    cs:__imp_LocalAlloc
0x1800297ee  mov     rbp, rax
0x1800297f1  test    rax, rax
0x1800297f4  jnz     short loc_180029800
0x1800297f6  mov     ebx, 8007000Eh
0x1800297fb  jmp     loc_18002995B
0x180029800  lea     r9, [rsp+98h+uBytes]; pcbData
0x180029808  mov     r8, rbp; pvData
0x18002980b  mov     edx, 17h; dwPropId
0x180029810  mov     rcx, rdi; pCertContext
0x180029813  call    cs:__imp_CertGetCertificateContextProperty
0x180029819  test    eax, eax
0x18002981b  jnz     short loc_18002983B
0x18002981d  call    cs:__imp_GetLastError
0x180029823  mov     ebx, eax
0x180029825  test    eax, eax
0x180029827  jle     loc_18002995B
0x18002982d  movzx   ebx, ax
0x180029830  or      ebx, 80070000h
0x180029836  jmp     loc_18002995B
0x18002983b  mov     r9d, dword ptr [rsp+98h+uBytes]; cbEncoded
0x180029843  lea     rax, [rsp+98h+var_58]
0x180029848  mov     [rsp+98h+pcbStructInfo], rax; pcbStructInfo
0x18002984d  mov     edi, 3Ah ; ':'
0x180029852  mov     [rsp+98h+pvStructInfo], r15; pvStructInfo
0x180029857  mov     r8, rbp; pbEncoded
0x18002985a  mov     edx, edi; lpszStructType
0x18002985c  mov     [rsp+98h+dwFlags], r15d; dwFlags
0x180029861  mov     ecx, 10001h; dwCertEncodingType
0x180029866  call    cs:__imp_CryptDecodeObject
0x18002986c  test    eax, eax
0x18002986e  jz      short loc_18002981D
0x180029870  mov     edx, [rsp+98h+var_58]; uBytes
0x180029874  mov     ecx, esi; uFlags
0x180029876  call    cs:__imp_LocalAlloc
0x18002987c  mov     r14, rax
0x18002987f  test    rax, rax
0x180029882  jz      loc_1800297F6
0x180029888  mov     r9d, dword ptr [rsp+98h+uBytes]; cbEncoded
0x180029890  lea     rax, [rsp+98h+var_58]
0x180029895  mov     [rsp+98h+pcbStructInfo], rax; pcbStructInfo
0x18002989a  mov     r8, rbp; pbEncoded
0x18002989d  mov     [rsp+98h+pvStructInfo], r14; pvStructInfo
0x1800298a2  mov     edx, edi; lpszStructType
0x1800298a4  mov     ecx, 10001h; dwCertEncodingType
0x1800298a9  mov     [rsp+98h+dwFlags], r15d; dwFlags
0x1800298ae  call    cs:__imp_CryptDecodeObject
0x1800298b4  test    eax, eax
0x1800298b6  jz      loc_18002981D
0x1800298bc  mov     rcx, rbp; hMem
0x1800298bf  mov     rsi, r15
0x1800298c2  mov     edi, r15d
0x1800298c5  call    cs:__imp_LocalFree
0x1800298cb  mov     eax, [r14+4]
0x1800298cf  test    eax, eax
0x1800298d1  jz      loc_18002996F
0x1800298d7  mov     rbp, r15
0x1800298da  cmp     eax, 1FFFFFFFh
0x1800298df  jnb     loc_1800297F6
0x1800298e5  mov     edx, eax
0x1800298e7  mov     ecx, 40h ; '@'; uFlags
0x1800298ec  shl     rdx, 3; uBytes
0x1800298f0  call    cs:__imp_LocalAlloc
0x1800298f6  mov     rsi, rax
0x1800298f9  test    rax, rax
0x1800298fc  jz      loc_1800297F6
0x180029902  cmp     r15d, [r14+4]
0x180029906  jnb     short loc_18002996F
0x180029908  mov     rcx, [r14+8]
0x18002990c  mov     eax, r15d
0x18002990f  add     rax, rax
0x180029912  cmp     [rcx+rax*8], ebx
0x180029915  jz      short loc_180029936
0x180029917  mov     rcx, [rcx+rax*8+8]
0x18002991c  cmp     dword ptr [rcx], 7
0x18002991f  jnz     short loc_180029936
0x180029921  mov     rcx, [rcx+8]; String
0x180029925  call    cs:__imp__wcsdup
0x18002992b  mov     [rsi+rdi*8], rax
0x18002992f  test    rax, rax
0x180029932  jz      short loc_18002993B
0x180029934  inc     edi
0x180029936  inc     r15d
0x180029939  jmp     short loc_180029902
0x18002993b  mov     ebx, 8007000Eh
0x180029940  jmp     short loc_18002994E
0x180029942  dec     edi
0x180029944  mov     rcx, [rsi+rdi*8]; hMem
0x180029948  call    cs:__imp_LocalFree
0x18002994e  test    edi, edi
0x180029950  jnz     short loc_180029942
0x180029952  mov     rcx, rsi; hMem
0x180029955  call    cs:__imp_LocalFree
0x18002995b  mov     rcx, r14; hMem
0x18002995e  call    cs:__imp_LocalFree
0x180029964  mov     rcx, rbp; hMem
0x180029967  call    cs:__imp_LocalFree
0x18002996d  jmp     short loc_180029980
0x18002996f  mov     rcx, r14; hMem
0x180029972  call    cs:__imp_LocalFree
0x180029978  mov     [r13+0], rsi
0x18002997c  mov     [r12], edi
0x180029980  mov     eax, ebx
0x180029982  add     rsp, 58h
0x180029986  pop     r15
0x180029988  pop     r14
0x18002998a  pop     r13
0x18002998c  pop     r12
0x18002998e  pop     rdi
0x18002998f  pop     rsi
0x180029990  pop     rbp
0x180029991  pop     rbx
0x180029992  retn
```
