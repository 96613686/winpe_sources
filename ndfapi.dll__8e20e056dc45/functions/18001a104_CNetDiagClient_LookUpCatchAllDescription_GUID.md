# CNetDiagClient::LookUpCatchAllDescription(_GUID)

- ea: `0x18001a104`
- end: `0x18001a608`
- name: `?LookUpCatchAllDescription@CNetDiagClient@@IEAAJU_GUID@@@Z`
- size: `1284`
- prototype: `__int64 __fastcall(CNetDiagClient *this, struct _GUID *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a884`

## callees

- `0x180003d50`
- `0x180005688`
- `0x180018a9c`
- `0x180018b40`
- `0x180018da4`
- `0x18001a104`
- `0x18001a7d4`
- `0x18001afe8`
- `0x18001b0f8`
- `0x18001f652`
- `0x18001f690`
- `0x180021010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001a4d2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a5db`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a4d2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a5db`
- `KERNEL32!SetDllDirectoryW` at `0x18001a273`
- `KERNEL32!SetDllDirectoryW` at `0x18001a4b9`
- `KERNEL32!SetDllDirectoryW` at `0x18001a273`
- `KERNEL32!SetDllDirectoryW` at `0x18001a4b9`
- `ole32!StringFromGUID2` at `0x18001a1e2`
- `ole32!StringFromGUID2` at `0x18001a1e2`
- `ole32!CoCreateInstance` at `0x18001a214`
- `ole32!CoCreateInstance` at `0x18001a214`
- `SHELL32!SHGetFolderPathW` at `0x18001a23d`
- `SHELL32!SHGetFolderPathW` at `0x18001a23d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a2b4`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a2b4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a4f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a505`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a4f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a505`
- `OLEAUT32!__imp_VariantInit` at `0x18001a180`
- `OLEAUT32!__imp_VariantInit` at `0x18001a18c`
- `OLEAUT32!__imp_VariantInit` at `0x18001a180`
- `OLEAUT32!__imp_VariantInit` at `0x18001a18c`
- `OLEAUT32!__imp_VariantClear` at `0x18001a29c`
- `OLEAUT32!__imp_VariantClear` at `0x18001a511`
- `OLEAUT32!__imp_VariantClear` at `0x18001a51d`
- `OLEAUT32!__imp_VariantClear` at `0x18001a29c`
- `OLEAUT32!__imp_VariantClear` at `0x18001a511`
- `OLEAUT32!__imp_VariantClear` at `0x18001a51d`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001a413`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001a413`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001a423`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001a423`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x18001a457`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x18001a457`

## pseudocode

```c
__int64 __fastcall CNetDiagClient::LookUpCatchAllDescription(CNetDiagClient *this, struct _GUID *a2)
{
  signed int v4; // ebx
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // rdx
  int v7; // eax
  UINT v8; // eax
  OLECHAR *v9; // rax
  void **v10; // rax
  void *v12; // rax
  int v13; // [rsp+30h] [rbp-C88h]
  __int16 v14; // [rsp+34h] [rbp-C84h] BYREF
  int v15; // [rsp+38h] [rbp-C80h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C78h] BYREF
  __int64 v17; // [rsp+48h] [rbp-C70h] BYREF
  BSTR v18; // [rsp+50h] [rbp-C68h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-C60h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-C48h]
  VARIANTARG v21; // [rsp+78h] [rbp-C40h] BYREF
  const ATL::CAtlException *v22; // [rsp+90h] [rbp-C28h] BYREF
  void *v23[2]; // [rsp+98h] [rbp-C20h] BYREF
  __int64 v24; // [rsp+A8h] [rbp-C10h]
  unsigned __int64 v25; // [rsp+B0h] [rbp-C08h]
  VARIANTARG Src; // [rsp+C0h] [rbp-BF8h] BYREF
  unsigned __int64 v27; // [rsp+D8h] [rbp-BE0h]
  OLECHAR sz[40]; // [rsp+E0h] [rbp-BD8h] BYREF
  WCHAR pszPath[264]; // [rsp+130h] [rbp-B88h] BYREF
  unsigned __int16 v30[168]; // [rsp+340h] [rbp-978h] BYREF
  WCHAR pszOutBuf[1024]; // [rsp+490h] [rbp-828h] BYREF

  memset_0(sz, 0, 0x4Eu);
  memset_0(v30, 0, 0x14Cu);
  memset_0(pszPath, 0, 0x20Au);
  ppv = 0;
  v17 = 0;
  VariantInit(&pvarg);
  VariantInit(&v21);
  v14 = 0;
  v18 = 0;
  bstrString = 0;
  memset_0(pszOutBuf, 0, sizeof(pszOutBuf));
  v25 = 7;
  v24 = 0;
  LOWORD(v23[0]) = 0;
  if ( !StringFromGUID2(a2, sz, 39) )
  {
    v4 = -2147467259;
    goto LABEL_26;
  }
  v4 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60, &ppv);
  if ( v4 >= 0 )
  {
    v4 = SHGetFolderPathW(0, 36, 0, 0, pszPath);
    if ( v4 >= 0 )
    {
      v4 = StringCchCatW(pszPath, v5, L"\\diagnostics\\system\\Networking");
      if ( v4 >= 0 )
      {
        SetDllDirectoryW(pszPath);
        v4 = StringCchCatW(pszPath, v6, L"\\DiagPackage.diagpkg");
        if ( v4 >= 0 )
        {
          VariantClear(&pvarg);
          pvarg.vt = 8;
          pvarg.llVal = (LONGLONG)SysAllocString(pszPath);
          if ( !pvarg.llVal )
          {
            if ( __eh34_try(-1, 0) )
            {
              __eh34_scope_strut(0);
              pvarg.vt = 10;
              pvarg.lVal = -2147024882;
              ATL::AtlThrowImpl(-2147024882);
            }
            if ( __eh34_catch(0) )
            {
              if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v22) )
              {
                v13 = *(_DWORD *)v22;
                v4 = v13;
                __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18001A4AC);
                goto LABEL_26;
              }
            }
          }
          Src = pvarg;
          v4 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(*(_QWORD *)ppv + 464LL))(ppv, &Src, &v14);
          if ( v4 < 0 )
            goto LABEL_26;
          if ( !v14 )
          {
            v4 = -2147023728;
            goto LABEL_26;
          }
          v4 = StringCchPrintfW(
                 v30,
                 0xA6u,
                 L"//Rootcause/ID[translate(text(), 'abcdef', 'ABCDEF') = translate(\"%ws\", 'abcdef', 'ABCDEF')]/../Displ"
                  "ayInformation/Name/text()",
                 sz);
          if ( v4 >= 0 )
          {
            v4 = ATL::CComBSTR::Append((const void **)&v18, v30);
            if ( v4 >= 0 )
            {
              v7 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)ppv + 296LL))(ppv, v18, &v17);
              v4 = v7;
              if ( v7 >= 0 )
              {
                if ( v7 == 1 || !v17 )
                {
                  if ( __eh34_try(-1, 2) )
                  {
                    __eh34_scope_strut(2);
                    v27 = 7;
                    Src.pRecInfo = 0;
                    Src.vt = 0;
                    std::wstring::assign(&Src, &qword_180026B78);
                    v12 = (void *)std::map<_GUID,std::wstring,GuidLessThan,std::allocator<std::pair<_GUID const,std::wstring>>>::operator[](
                                    (char *)this + 80,
                                    a2);
                    std::wstring::operator=(v12, &Src);
                    if ( v27 >= 8 )
                      operator delete(*(void **)&Src.vt);
                    v4 = 1;
                  }
                  if ( __eh34_catch(2) )
                  {
                    if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
                    {
                      v13 = -2147024882;
                      v4 = -2147024882;
                      __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_18001A4AC);
                      goto LABEL_26;
                    }
                    if ( __eh34_catch_type(2, &exception `RTTI Type Descriptor', 0) )
                    {
                      v13 = -2147467259;
                      v4 = -2147467259;
                      __eh34_try_continuation(2, &exception `RTTI Type Descriptor', &loc_18001A4AC);
                    }
                  }
                }
                else
                {
                  v15 = 0;
                  v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 80LL))(v17, &v15);
                  if ( v4 < 0 )
                    goto LABEL_26;
                  if ( v15 != 3 )
                  {
                    v4 = -2147418113;
                    goto LABEL_26;
                  }
                  v4 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v17 + 64LL))(v17, &v21);
                  if ( v4 >= 0 )
                  {
                    if ( v21.vt != 8 )
                    {
                      v4 = -2147352571;
                      goto LABEL_26;
                    }
                    v8 = SysStringByteLen(v21.bstrVal);
                    v9 = SysAllocStringByteLen(v21.pcVal, v8);
                    bstrString = v9;
                    v4 = v9 == 0 ? 0x8007000E : 0;
                    if ( v9 )
                    {
                      v4 = SHLoadIndirectString(v9, pszOutBuf, 0x400u, 0);
                      if ( v4 >= 0 )
                      {
                        if ( __eh34_try(-1, 4) )
                        {
                          __eh34_scope_strut(4);
                          std::wstring::assign(v23, pszOutBuf);
                        }
                        if ( __eh34_catch(4) )
                        {
                          if ( __eh34_catch_type(4, &std::bad_alloc `RTTI Type Descriptor', 0) )
                          {
                            v13 = -2147024882;
                            v4 = -2147024882;
                            __eh34_try_continuation(4, &std::bad_alloc `RTTI Type Descriptor', &loc_18001A4AC);
                            goto LABEL_26;
                          }
                          if ( __eh34_catch_type(4, &exception `RTTI Type Descriptor', 0) )
                          {
                            v13 = -2147467259;
                            v4 = -2147467259;
                            __eh34_try_continuation(4, &exception `RTTI Type Descriptor', &loc_18001A4AC);
                            goto LABEL_26;
                          }
                        }
                        if ( __eh34_try(-1, 6) )
                        {
                          __eh34_scope_strut(6);
                          v10 = (void **)std::map<_GUID,std::wstring,GuidLessThan,std::allocator<std::pair<_GUID const,std::wstring>>>::operator[](
                                           (char *)this + 80,
                                           a2);
                          if ( v10 != v23 )
                            std::wstring::assign(v10);
                        }
                        if ( __eh34_catch(6) )
                        {
                          if ( __eh34_catch_type(6, &std::bad_alloc `RTTI Type Descriptor', 0) )
                          {
                            v13 = -2147024882;
                            v4 = -2147024882;
                            __eh34_try_continuation(6, &std::bad_alloc `RTTI Type Descriptor', &loc_18001A4AC);
                            goto LABEL_26;
                          }
                          if ( __eh34_catch_type(6, &exception `RTTI Type Descriptor', 0) )
                          {
                            v13 = -2147467259;
                            v4 = -2147467259;
                            __eh34_try_continuation(6, &exception `RTTI Type Descriptor', &loc_18001A4AC);
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_26:
  SetDllDirectoryW(0);
  if ( v25 >= 8 )
    operator delete(v23[0]);
  v25 = 7;
  v24 = 0;
  LOWORD(v23[0]) = 0;
  SysFreeString(bstrString);
  SysFreeString(v18);
  VariantClear(&v21);
  VariantClear(&pvarg);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001a104  mov     [rsp+arg_10], rbx
0x18001a109  mov     [rsp+arg_18], rsi
0x18001a10e  push    rdi
0x18001a10f  push    r14
0x18001a111  push    r15
0x18001a113  sub     rsp, 0CA0h
0x18001a11a  mov     rax, cs:__security_cookie
0x18001a121  xor     rax, rsp
0x18001a124  mov     [rsp+0CB8h+var_28], rax
0x18001a12c  mov     r14, rdx
0x18001a12f  mov     r15, rcx
0x18001a132  xor     edx, edx; Val
0x18001a134  lea     r8d, [rdx+4Eh]; Size
0x18001a138  lea     rcx, [rsp+0CB8h+sz]; void *
0x18001a140  call    memset_0
0x18001a145  xor     edx, edx; Val
0x18001a147  mov     r8d, 14Ch; Size
0x18001a14d  lea     rcx, [rsp+0CB8h+var_978]; void *
0x18001a155  call    memset_0
0x18001a15a  xor     edx, edx; Val
0x18001a15c  mov     r8d, 20Ah; Size
0x18001a162  lea     rcx, [rsp+0CB8h+pszPath]; void *
0x18001a16a  call    memset_0
0x18001a16f  xor     edi, edi
0x18001a171  mov     [rsp+0CB8h+var_C78], rdi
0x18001a176  mov     [rsp+0CB8h+var_C70], rdi
0x18001a17b  lea     rcx, [rsp+0CB8h+pvarg]; pvarg
0x18001a180  call    cs:__imp_VariantInit
0x18001a186  nop
0x18001a187  lea     rcx, [rsp+0CB8h+var_C40]; pvarg
0x18001a18c  call    cs:__imp_VariantInit
0x18001a192  nop
0x18001a193  mov     [rsp+0CB8h+var_C84], di
0x18001a198  mov     [rsp+0CB8h+var_C68], rdi
0x18001a19d  mov     [rsp+0CB8h+bstrString], rdi
0x18001a1a2  xor     edx, edx; Val
0x18001a1a4  mov     r8d, 800h; Size
0x18001a1aa  lea     rcx, [rsp+0CB8h+pszOutBuf]; void *
0x18001a1b2  call    memset_0
0x18001a1b7  mov     [rsp+0CB8h+var_C08], 7
0x18001a1c3  mov     [rsp+0CB8h+var_C10], rdi
0x18001a1cb  mov     word ptr [rsp+0CB8h+var_C20], di
0x18001a1d3  lea     r8d, [rdi+27h]; cchMax
0x18001a1d7  lea     rdx, [rsp+0CB8h+sz]; lpsz
0x18001a1df  mov     rcx, r14; rguid
0x18001a1e2  call    cs:__imp_StringFromGUID2
0x18001a1e8  test    eax, eax
0x18001a1ea  jnz     short loc_18001A1F6
0x18001a1ec  mov     ebx, 80004005h
0x18001a1f1  jmp     loc_18001A4B2
0x18001a1f6  lea     rax, [rsp+0CB8h+var_C78]
0x18001a1fb  mov     [rsp+0CB8h+ppv], rax; ppv
0x18001a200  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x18001a207  xor     edx, edx; pUnkOuter
0x18001a209  lea     r8d, [rdx+1]; dwClsContext
0x18001a20d  lea     rcx, CLSID_DOMDocument60; rclsid
0x18001a214  call    cs:__imp_CoCreateInstance
0x18001a21a  mov     ebx, eax
0x18001a21c  test    eax, eax
0x18001a21e  js      loc_18001A4B2
0x18001a224  lea     rax, [rsp+0CB8h+pszPath]
0x18001a22c  mov     [rsp+0CB8h+ppv], rax; pszPath
0x18001a231  xor     r9d, r9d; dwFlags
0x18001a234  xor     r8d, r8d; hToken
0x18001a237  lea     edx, [r9+24h]; csidl
0x18001a23b  xor     ecx, ecx; hwnd
0x18001a23d  call    cs:__imp_SHGetFolderPathW
0x18001a243  mov     ebx, eax
0x18001a245  test    eax, eax
0x18001a247  js      loc_18001A4B2
0x18001a24d  lea     r8, aDiagnosticsSys_0; "\\diagnostics\\system\\Networking"
0x18001a254  lea     rcx, [rsp+0CB8h+pszPath]; unsigned __int16 *
0x18001a25c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001a261  mov     ebx, eax
0x18001a263  test    eax, eax
0x18001a265  js      loc_18001A4B2
0x18001a26b  lea     rcx, [rsp+0CB8h+pszPath]; lpPathName
0x18001a273  call    cs:__imp_SetDllDirectoryW
0x18001a279  lea     r8, aDiagpackageDia; "\\DiagPackage.diagpkg"
0x18001a280  lea     rcx, [rsp+0CB8h+pszPath]; unsigned __int16 *
0x18001a288  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001a28d  mov     ebx, eax
0x18001a28f  test    eax, eax
0x18001a291  js      loc_18001A4B2
0x18001a297  lea     rcx, [rsp+0CB8h+pvarg]; pvarg
0x18001a29c  call    cs:__imp_VariantClear
0x18001a2a2  mov     esi, 8
0x18001a2a7  mov     word ptr [rsp+0CB8h+pvarg], si
0x18001a2ac  lea     rcx, [rsp+0CB8h+pszPath]; psz
0x18001a2b4  call    cs:__imp_SysAllocString
0x18001a2ba  mov     dword ptr [rsp+0CB8h+pvarg+8], eax
0x18001a2be  mov     rcx, rax
0x18001a2c1  sar     rcx, 20h
0x18001a2c5  mov     dword ptr [rsp+0CB8h+pvarg+0Ch], ecx
0x18001a2c9  test    rax, rax
0x18001a2cc  jz      loc_18001A5EC
0x18001a2d2  mov     rcx, [rsp+0CB8h+var_C78]
0x18001a2d7  movups  xmm0, xmmword ptr [rsp+0CB8h+pvarg]
0x18001a2dc  movaps  [rsp+0CB8h+Src], xmm0
0x18001a2e4  movsd   xmm1, qword ptr [rsp+0CB8h+pvarg+10h]
0x18001a2ea  movsd   [rsp+0CB8h+var_BE8], xmm1
0x18001a2f3  mov     rax, [rcx]
0x18001a2f6  lea     r8, [rsp+0CB8h+var_C84]
0x18001a2fb  lea     rdx, [rsp+0CB8h+Src]
0x18001a303  mov     rax, [rax+1D0h]
0x18001a30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a30f  mov     ebx, eax
0x18001a311  test    eax, eax
0x18001a313  js      loc_18001A4B7
0x18001a319  cmp     [rsp+0CB8h+var_C84], di
0x18001a31e  jnz     short loc_18001A32A
0x18001a320  mov     ebx, 80070490h
0x18001a325  jmp     loc_18001A4B7
0x18001a32a  lea     r9, [rsp+0CB8h+sz]
0x18001a332  lea     r8, aRootcauseIdTra; "//Rootcause/ID[translate(text(), 'abcde"...
0x18001a339  mov     edx, 0A6h; unsigned __int64
0x18001a33e  lea     rcx, [rsp+0CB8h+var_978]; unsigned __int16 *
0x18001a346  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a34b  mov     ebx, eax
0x18001a34d  test    eax, eax
0x18001a34f  js      loc_18001A4B7
0x18001a355  lea     rdx, [rsp+0CB8h+var_978]; unsigned __int16 *
0x18001a35d  lea     rcx, [rsp+0CB8h+var_C68]; this
0x18001a362  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18001a367  mov     ebx, eax
0x18001a369  test    eax, eax
0x18001a36b  js      loc_18001A4B7
0x18001a371  mov     rcx, [rsp+0CB8h+var_C78]
0x18001a376  mov     rax, [rcx]
0x18001a379  lea     r8, [rsp+0CB8h+var_C70]
0x18001a37e  mov     rdx, [rsp+0CB8h+var_C68]
0x18001a383  mov     rax, [rax+128h]
0x18001a38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a38f  mov     ebx, eax
0x18001a391  test    eax, eax
0x18001a393  js      loc_18001A4B7
0x18001a399  cmp     eax, 1
0x18001a39c  jz      loc_18001A57B
0x18001a3a2  mov     rcx, [rsp+0CB8h+var_C70]
0x18001a3a7  test    rcx, rcx
0x18001a3aa  jz      loc_18001A57B
0x18001a3b0  mov     [rsp+0CB8h+var_C80], edi
0x18001a3b4  mov     rax, [rcx]
0x18001a3b7  lea     rdx, [rsp+0CB8h+var_C80]
0x18001a3bc  mov     rax, [rax+50h]
0x18001a3c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3c5  mov     ebx, eax
0x18001a3c7  test    eax, eax
0x18001a3c9  js      loc_18001A4B7
0x18001a3cf  cmp     [rsp+0CB8h+var_C80], 3
0x18001a3d4  jz      short loc_18001A3E0
0x18001a3d6  mov     ebx, 8000FFFFh
0x18001a3db  jmp     loc_18001A4B7
0x18001a3e0  mov     rcx, [rsp+0CB8h+var_C70]
0x18001a3e5  mov     rax, [rcx]
0x18001a3e8  lea     rdx, [rsp+0CB8h+var_C40]
0x18001a3ed  mov     rax, [rax+40h]
0x18001a3f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3f6  mov     ebx, eax
0x18001a3f8  test    eax, eax
0x18001a3fa  js      loc_18001A4B7
0x18001a400  cmp     word ptr [rsp+0CB8h+var_C40], si
0x18001a405  jnz     loc_18001A566
0x18001a40b  mov     rcx, qword ptr [rsp+0CB8h+var_C40+8]; bstr
0x18001a413  call    cs:__imp_SysStringByteLen
0x18001a419  mov     edx, eax; len
0x18001a41b  mov     rcx, qword ptr [rsp+0CB8h+var_C40+8]; psz
0x18001a423  call    cs:__imp_SysAllocStringByteLen
0x18001a429  mov     [rsp+0CB8h+bstrString], rax
0x18001a42e  mov     rcx, rax
0x18001a431  neg     rcx
0x18001a434  sbb     ebx, ebx
0x18001a436  not     ebx
0x18001a438  and     ebx, 8007000Eh
0x18001a43e  test    rax, rax
0x18001a441  jz      short loc_18001A4B7
0x18001a443  xor     r9d, r9d; ppvReserved
0x18001a446  mov     r8d, 400h; cchOutBuf
0x18001a44c  lea     rdx, [rsp+0CB8h+pszOutBuf]; pszOutBuf
0x18001a454  mov     rcx, rax; pszSource
0x18001a457  call    cs:__imp_SHLoadIndirectString
0x18001a45d  mov     ebx, eax
0x18001a45f  test    eax, eax
0x18001a461  js      short loc_18001A4B7
0x18001a463  lea     rdx, [rsp+0CB8h+pszOutBuf]; Src
0x18001a46b  lea     rcx, [rsp+0CB8h+var_C20]; void *
0x18001a473  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001a478  nop
0x18001a479  lea     rcx, [r15+50h]
0x18001a47d  mov     rdx, r14
0x18001a480  call    ??A?$map@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UGuidLessThan@@V?$allocator@U?$pair@$$CBU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@3@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBU_GUID@@@Z; std::map<_GUID,std::wstring,GuidLessThan,std::allocator<std::pair<_GUID const,std::wstring>>>::operator[](_GUID const &)
0x18001a485  lea     rcx, [rsp+0CB8h+var_C20]
0x18001a48d  cmp     rax, rcx
0x18001a490  jz      short loc_18001A4AA
0x18001a492  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001a496  xor     r8d, r8d
0x18001a499  lea     rdx, [rsp+0CB8h+var_C20]
0x18001a4a1  mov     rcx, rax; void *
0x18001a4a4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001a4a9  nop
0x18001a4aa  jmp     short loc_18001A4B7
0x18001a4ac  mov     ebx, [rsp+0CB8h+var_C88]
0x18001a4b0  xor     edi, edi
0x18001a4b2  mov     esi, 8
0x18001a4b7  xor     ecx, ecx; lpPathName
0x18001a4b9  call    cs:__imp_SetDllDirectoryW
0x18001a4bf  nop
0x18001a4c0  cmp     [rsp+0CB8h+var_C08], rsi
0x18001a4c8  jb      short loc_18001A4D8
0x18001a4ca  mov     rcx, [rsp+0CB8h+var_C20]
0x18001a4d2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a4d8  mov     [rsp+0CB8h+var_C08], 7
0x18001a4e4  mov     [rsp+0CB8h+var_C10], rdi
0x18001a4ec  mov     word ptr [rsp+0CB8h+var_C20], di
0x18001a4f4  mov     rcx, [rsp+0CB8h+bstrString]; bstrString
0x18001a4f9  call    cs:__imp_SysFreeString
0x18001a4ff  nop
0x18001a500  mov     rcx, [rsp+0CB8h+var_C68]; bstrString
0x18001a505  call    cs:__imp_SysFreeString
0x18001a50b  nop
0x18001a50c  lea     rcx, [rsp+0CB8h+var_C40]; pvarg
0x18001a511  call    cs:__imp_VariantClear
0x18001a517  nop
0x18001a518  lea     rcx, [rsp+0CB8h+pvarg]; pvarg
0x18001a51d  call    cs:__imp_VariantClear
0x18001a523  nop
0x18001a524  mov     rcx, [rsp+0CB8h+var_C78]
0x18001a529  test    rcx, rcx
0x18001a52c  jz      short loc_18001A53B
0x18001a52e  mov     rax, [rcx]
0x18001a531  mov     rax, [rax+10h]
0x18001a535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a53a  nop
0x18001a53b  mov     eax, ebx
0x18001a53d  mov     rcx, [rsp+0CB8h+var_28]
0x18001a545  xor     rcx, rsp; StackCookie
0x18001a548  call    __security_check_cookie
0x18001a54d  lea     r11, [rsp+0CB8h+var_18]
0x18001a555  mov     rbx, [r11+30h]
0x18001a559  mov     rsi, [r11+38h]
0x18001a55d  mov     rsp, r11
0x18001a560  pop     r15
0x18001a562  pop     r14
0x18001a564  pop     rdi
0x18001a565  retn
0x18001a566  mov     ebx, 80004003h
0x18001a56b  jz      loc_18001A4B7
0x18001a571  mov     ebx, 80020005h
0x18001a576  jmp     loc_18001A4B7
0x18001a57b  mov     [rsp+0CB8h+var_BE0], 7
0x18001a587  mov     [rsp+0CB8h+var_BE8], rdi
0x18001a58f  mov     word ptr [rsp+0CB8h+Src], di
0x18001a597  lea     rdx, qword_180026B78; Src
0x18001a59e  lea     rcx, [rsp+0CB8h+Src]; void *
0x18001a5a6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001a5ab  nop
0x18001a5ac  lea     rcx, [r15+50h]
0x18001a5b0  mov     rdx, r14
0x18001a5b3  call    ??A?$map@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UGuidLessThan@@V?$allocator@U?$pair@$$CBU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@3@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBU_GUID@@@Z; std::map<_GUID,std::wstring,GuidLessThan,std::allocator<std::pair<_GUID const,std::wstring>>>::operator[](_GUID const &)
0x18001a5b8  lea     rdx, [rsp+0CB8h+Src]; Src
0x18001a5c0  mov     rcx, rax; void *
0x18001a5c3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001a5c8  nop
0x18001a5c9  cmp     [rsp+0CB8h+var_BE0], rsi
0x18001a5d1  jb      short loc_18001A5E2
0x18001a5d3  mov     rcx, qword ptr [rsp+0CB8h+Src]
0x18001a5db  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a5e1  nop
0x18001a5e2  mov     ebx, 1
0x18001a5e7  jmp     loc_18001A4B7
0x18001a5ec  lea     eax, [rsi+2]
0x18001a5ef  mov     word ptr [rsp+0CB8h+pvarg], ax
0x18001a5f4  mov     dword ptr [rsp+0CB8h+pvarg+8], 8007000Eh
0x18001a5fc  mov     ecx, 8007000Eh; int
0x18001a601  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
