# CSharingConfiguration::SharePrinters(void)

- ea: `0x180054900`
- end: `0x180054bbf`
- name: `?SharePrinters@CSharingConfiguration@@UEAAJXZ`
- size: `703`
- prototype: `__int64 __fastcall(CSharingConfiguration *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800098dc`
- `0x1800254e0`
- `0x18002af04`
- `0x180054900`
- `0x180055628`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180054a1c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180054afc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180054a1c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180054afc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054b7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054b99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054b7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054b99`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005495e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005495e`
- `SHCORE!IsOS` at `0x18005492a`
- `SHCORE!IsOS` at `0x18005492a`
- `WINSPOOL!SetPrinterW` at `0x180054b75`
- `WINSPOOL!SetPrinterW` at `0x180054b75`
- `WINSPOOL!GetPrinterW` at `0x180054aed`
- `WINSPOOL!GetPrinterW` at `0x180054b24`
- `WINSPOOL!GetPrinterW` at `0x180054aed`
- `WINSPOOL!GetPrinterW` at `0x180054b24`
- `WINSPOOL!OpenPrinterW` at `0x180054ac2`
- `WINSPOOL!OpenPrinterW` at `0x180054ac2`
- `WINSPOOL!ClosePrinter` at `0x180054b89`
- `WINSPOOL!ClosePrinter` at `0x180054b89`
- `WINSPOOL!EnumPrintersW` at `0x180054a0a`
- `WINSPOOL!EnumPrintersW` at `0x180054a55`
- `WINSPOOL!EnumPrintersW` at `0x180054a0a`
- `WINSPOOL!EnumPrintersW` at `0x180054a55`

## pseudocode

```c
__int64 __fastcall CSharingConfiguration::SharePrinters(CSharingConfiguration *this)
{
  HRESULT Error; // ebx
  BYTE *v2; // rax
  struct _PRINTER_INFO_5W *v3; // r14
  CSharingConfiguration *v4; // rcx
  DWORD i; // esi
  WCHAR *pPrinterName; // rcx
  HLOCAL v7; // rdi
  CShareName *v8; // rcx
  unsigned int v9; // r9d
  int v10; // eax
  _WORD *v11; // rax
  DWORD pcReturned; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE phPrinter; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbBuf; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v16; // [rsp+54h] [rbp-ACh] BYREF
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v18[88]; // [rsp+70h] [rbp-90h] BYREF

  if ( IsOS(0x1Cu) )
    goto LABEL_29;
  phPrinter = 0;
  Error = CoCreateInstance(
            &GUID_1fda955b_61ff_11da_978c_0008744faab7,
            0,
            1u,
            &GUID_1fda955c_61ff_11da_978c_0008744faab7,
            &phPrinter);
  if ( Error >= 0 )
  {
    pcReturned = 0;
    Error = (*(__int64 (__fastcall **)(HANDLE, __int64, DWORD *, _QWORD))(*(_QWORD *)phPrinter + 24LL))(
              phPrinter,
              3,
              &pcReturned,
              0);
    if ( Error >= 0 && pcReturned != 1 )
      Error = (*(__int64 (__fastcall **)(HANDLE, _QWORD, __int64, __int64))(*(_QWORD *)phPrinter + 32LL))(
                phPrinter,
                0,
                3,
                1);
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)phPrinter + 16LL))(phPrinter);
    if ( Error >= 0 )
    {
LABEL_29:
      cbBuf = 0;
      pcReturned = 0;
      EnumPrintersW(2u, 0, 5u, 0, 0, &cbBuf, &pcReturned);
      Error = -2147024882;
      v2 = (BYTE *)LocalAlloc(0x40u, cbBuf);
      v3 = (struct _PRINTER_INFO_5W *)v2;
      if ( v2 )
      {
        if ( EnumPrintersW(2u, 0, 5u, v2, cbBuf, &cbBuf, &pcReturned) )
        {
          Error = 0;
        }
        else
        {
          Error = ResultFromKnownLastError();
          if ( Error < 0 )
          {
LABEL_25:
            LocalFree(v3);
            return (unsigned int)Error;
          }
        }
        for ( i = 0; i < pcReturned; ++i )
        {
          if ( (unsigned int)CSharingConfiguration::_ShouldIncludePrinter(v4, &v3[i]) )
          {
            pPrinterName = v3[i].pPrinterName;
            phPrinter = 0;
            *(&pDefault.DesiredAccess + 1) = 0;
            pDefault.DesiredAccess = 983052;
            *(_OWORD *)&pDefault.pDatatype = 0;
            if ( OpenPrinterW(pPrinterName, &phPrinter, &pDefault) )
            {
              v16 = 0;
              GetPrinterW(phPrinter, 2u, 0, 0, &v16);
              v7 = LocalAlloc(0x40u, v16);
              if ( v7 )
              {
                if ( GetPrinterW(phPrinter, 2u, (LPBYTE)v7, v16, &v16) )
                {
                  v10 = *((_DWORD *)v7 + 26);
                  if ( (v10 & 8) == 0 )
                  {
                    v18[0] = 0;
                    *((_DWORD *)v7 + 26) = v10 | 8;
                    v11 = (_WORD *)*((_QWORD *)v7 + 2);
                    if ( !v11 || !*v11 )
                    {
                      CShareName::Generate(v8, *((const unsigned __int16 **)v7 + 1), v18, v9);
                      *((_QWORD *)v7 + 2) = v18;
                    }
                    SetPrinterW(phPrinter, 2u, (LPBYTE)v7, 0);
                  }
                }
                LocalFree(v7);
              }
              ClosePrinter(phPrinter);
            }
          }
        }
        goto LABEL_25;
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180054900  push    rbp
0x180054902  push    rbx
0x180054903  push    rsi
0x180054904  push    rdi
0x180054905  push    r13
0x180054907  push    r14
0x180054909  push    r15
0x18005490b  lea     rbp, [rsp-30h]
0x180054910  sub     rsp, 130h
0x180054917  mov     rax, cs:__security_cookie
0x18005491e  xor     rax, rsp
0x180054921  mov     [rbp+60h+var_40], rax
0x180054925  mov     ecx, 1Ch; dwOS
0x18005492a  call    cs:__imp_IsOS
0x180054930  xor     r15d, r15d
0x180054933  test    eax, eax
0x180054935  jnz     loc_1800549D4
0x18005493b  lea     rax, [rsp+160h+phPrinter]
0x180054940  mov     [rsp+160h+phPrinter], r15
0x180054945  lea     r9, _GUID_1fda955c_61ff_11da_978c_0008744faab7; riid
0x18005494c  mov     [rsp+160h+ppv], rax; ppv
0x180054951  xor     edx, edx; pUnkOuter
0x180054953  lea     r8d, [r15+1]; dwClsContext
0x180054957  lea     rcx, _GUID_1fda955b_61ff_11da_978c_0008744faab7; rclsid
0x18005495e  call    cs:__imp_CoCreateInstance
0x180054964  mov     ebx, eax
0x180054966  test    eax, eax
0x180054968  js      loc_180054B9F
0x18005496e  mov     rcx, [rsp+160h+phPrinter]
0x180054973  lea     edi, [r15+3]
0x180054977  mov     [rsp+160h+var_120], r15d
0x18005497c  lea     r8, [rsp+160h+var_120]
0x180054981  xor     r9d, r9d
0x180054984  mov     edx, edi
0x180054986  mov     rax, [rcx]
0x180054989  mov     rax, [rax+18h]
0x18005498d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054992  mov     ebx, eax
0x180054994  test    eax, eax
0x180054996  js      short loc_1800549BB
0x180054998  cmp     [rsp+160h+var_120], 1
0x18005499d  jz      short loc_1800549BB
0x18005499f  mov     rcx, [rsp+160h+phPrinter]
0x1800549a4  lea     r9d, [r15+1]
0x1800549a8  mov     r8d, edi
0x1800549ab  xor     edx, edx
0x1800549ad  mov     rax, [rcx]
0x1800549b0  mov     rax, [rax+20h]
0x1800549b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549b9  mov     ebx, eax
0x1800549bb  mov     rcx, [rsp+160h+phPrinter]
0x1800549c0  mov     rax, [rcx]
0x1800549c3  mov     rax, [rax+10h]
0x1800549c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549cc  test    ebx, ebx
0x1800549ce  js      loc_180054B9F
0x1800549d4  xor     r9d, r9d; pPrinterEnum
0x1800549d7  mov     [rsp+160h+cbBuf], r15d
0x1800549dc  lea     rax, [rsp+160h+var_120]
0x1800549e1  mov     [rsp+160h+var_120], r15d
0x1800549e6  mov     [rsp+160h+pcReturned], rax; pcReturned
0x1800549eb  xor     edx, edx; Name
0x1800549ed  lea     rax, [rsp+160h+cbBuf]
0x1800549f2  lea     edi, [r9+5]
0x1800549f6  mov     [rsp+160h+pcbNeeded], rax; pcbNeeded
0x1800549fb  lea     r13d, [r9+2]
0x1800549ff  mov     dword ptr [rsp+160h+ppv], r15d; cbBuf
0x180054a04  mov     r8d, edi; Level
0x180054a07  mov     ecx, r13d; Flags
0x180054a0a  call    cs:__imp_EnumPrintersW
0x180054a10  mov     edx, [rsp+160h+cbBuf]; uBytes
0x180054a14  lea     ecx, [rdi+3Bh]; uFlags
0x180054a17  mov     ebx, 8007000Eh
0x180054a1c  call    cs:__imp_LocalAlloc
0x180054a22  mov     r14, rax
0x180054a25  test    rax, rax
0x180054a28  jz      loc_180054B9F
0x180054a2e  mov     ecx, [rsp+160h+cbBuf]
0x180054a32  lea     rax, [rsp+160h+var_120]
0x180054a37  mov     [rsp+160h+pcReturned], rax; pcReturned
0x180054a3c  mov     r9, r14; pPrinterEnum
0x180054a3f  lea     rax, [rsp+160h+cbBuf]
0x180054a44  mov     r8d, edi; Level
0x180054a47  mov     [rsp+160h+pcbNeeded], rax; pcbNeeded
0x180054a4c  xor     edx, edx; Name
0x180054a4e  mov     dword ptr [rsp+160h+ppv], ecx; cbBuf
0x180054a52  mov     ecx, r13d; Flags
0x180054a55  call    cs:__imp_EnumPrintersW
0x180054a5b  test    eax, eax
0x180054a5d  jz      short loc_180054A64
0x180054a5f  mov     ebx, r15d
0x180054a62  jmp     short loc_180054A73
0x180054a64  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180054a69  mov     ebx, eax
0x180054a6b  test    eax, eax
0x180054a6d  js      loc_180054B96
0x180054a73  mov     esi, r15d
0x180054a76  cmp     esi, [rsp+160h+var_120]
0x180054a7a  jnb     loc_180054B96
0x180054a80  mov     edi, esi
0x180054a82  shl     rdi, 5
0x180054a86  add     rdi, r14
0x180054a89  mov     rdx, rdi; struct _PRINTER_INFO_5W *
0x180054a8c  call    ?_ShouldIncludePrinter@CSharingConfiguration@@AEAAHPEAU_PRINTER_INFO_5W@@@Z; CSharingConfiguration::_ShouldIncludePrinter(_PRINTER_INFO_5W *)
0x180054a91  test    eax, eax
0x180054a93  jz      loc_180054B8F
0x180054a99  mov     rcx, [rdi]; pPrinterName
0x180054a9c  lea     r8, [rsp+160h+pDefault]; pDefault
0x180054aa1  xor     eax, eax
0x180054aa3  mov     [rsp+160h+phPrinter], r15
0x180054aa8  xorps   xmm0, xmm0
0x180054aab  mov     qword ptr [rsp+160h+pDefault.DesiredAccess], rax
0x180054ab0  lea     rdx, [rsp+160h+phPrinter]; phPrinter
0x180054ab5  mov     [rsp+160h+pDefault.DesiredAccess], 0F000Ch
0x180054abd  movups  xmmword ptr [rsp+160h+pDefault.pDatatype], xmm0
0x180054ac2  call    cs:__imp_OpenPrinterW
0x180054ac8  test    eax, eax
0x180054aca  jz      loc_180054B8F
0x180054ad0  mov     rcx, [rsp+160h+phPrinter]; hPrinter
0x180054ad5  lea     rax, [rsp+160h+var_10C]
0x180054ada  xor     r9d, r9d; cbBuf
0x180054add  mov     [rsp+160h+ppv], rax; pcbNeeded
0x180054ae2  xor     r8d, r8d; pPrinter
0x180054ae5  mov     [rsp+160h+var_10C], r15d
0x180054aea  mov     edx, r13d; Level
0x180054aed  call    cs:__imp_GetPrinterW
0x180054af3  mov     edx, [rsp+160h+var_10C]; uBytes
0x180054af7  mov     ecx, 40h ; '@'; uFlags
0x180054afc  call    cs:__imp_LocalAlloc
0x180054b02  mov     rdi, rax
0x180054b05  test    rax, rax
0x180054b08  jz      short loc_180054B84
0x180054b0a  mov     r9d, [rsp+160h+var_10C]; cbBuf
0x180054b0f  lea     rax, [rsp+160h+var_10C]
0x180054b14  mov     rcx, [rsp+160h+phPrinter]; hPrinter
0x180054b19  mov     r8, rdi; pPrinter
0x180054b1c  mov     edx, r13d; Level
0x180054b1f  mov     [rsp+160h+ppv], rax; pcbNeeded
0x180054b24  call    cs:__imp_GetPrinterW
0x180054b2a  test    eax, eax
0x180054b2c  jz      short loc_180054B7B
0x180054b2e  mov     eax, [rdi+68h]
0x180054b31  test    al, 8
0x180054b33  jnz     short loc_180054B7B
0x180054b35  or      eax, 8
0x180054b38  mov     [rsp+160h+var_F0], r15w
0x180054b3e  mov     [rdi+68h], eax
0x180054b41  mov     rax, [rdi+10h]
0x180054b45  test    rax, rax
0x180054b48  jz      short loc_180054B50
0x180054b4a  cmp     [rax], r15w
0x180054b4e  jnz     short loc_180054B67
0x180054b50  mov     rdx, [rdi+8]; unsigned __int16 *
0x180054b54  lea     r8, [rsp+160h+var_F0]; unsigned __int16 *
0x180054b59  call    ?Generate@CShareName@@QEAAJPEBGPEAGK@Z; CShareName::Generate(ushort const *,ushort *,ulong)
0x180054b5e  lea     rax, [rsp+160h+var_F0]
0x180054b63  mov     [rdi+10h], rax
0x180054b67  mov     rcx, [rsp+160h+phPrinter]; hPrinter
0x180054b6c  xor     r9d, r9d; Command
0x180054b6f  mov     r8, rdi; pPrinter
0x180054b72  mov     edx, r13d; Level
0x180054b75  call    cs:__imp_SetPrinterW
0x180054b7b  mov     rcx, rdi; hMem
0x180054b7e  call    cs:__imp_LocalFree
0x180054b84  mov     rcx, [rsp+160h+phPrinter]; hPrinter
0x180054b89  call    cs:__imp_ClosePrinter
0x180054b8f  inc     esi
0x180054b91  jmp     loc_180054A76
0x180054b96  mov     rcx, r14; hMem
0x180054b99  call    cs:__imp_LocalFree
0x180054b9f  mov     eax, ebx
0x180054ba1  mov     rcx, [rbp+60h+var_40]
0x180054ba5  xor     rcx, rsp; StackCookie
0x180054ba8  call    __security_check_cookie
0x180054bad  add     rsp, 130h
0x180054bb4  pop     r15
0x180054bb6  pop     r14
0x180054bb8  pop     r13
0x180054bba  pop     rdi
0x180054bbb  pop     rsi
0x180054bbc  pop     rbx
0x180054bbd  pop     rbp
0x180054bbe  retn
```
