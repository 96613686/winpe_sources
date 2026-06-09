# CMapiSupport::GetDllDetailsFromPath(wchar_t *,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)

- ea: `0x18002f524`
- end: `0x18002f6ca`
- name: `?GetDllDetailsFromPath@CMapiSupport@@CAJPEA_WAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@1@Z`
- size: `422`
- prototype: `__int64 __fastcall(LPCWSTR lpwstrFilename)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002f1d8`

## callees

- `0x1800031c0`
- `0x180004058`
- `0x180004850`
- `0x1800048c0`
- `0x180006640`
- `0x1800070ec`
- `0x18002922c`
- `0x18002e9d4`
- `0x18002f524`

## import_xrefs

- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18002f55b`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18002f55b`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18002f597`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18002f597`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18002f5c6`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18002f621`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18002f671`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18002f5c6`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18002f621`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18002f671`

## string_xrefs

- `0x18002f64f`: `CompanyName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMapiSupport::GetDllDetailsFromPath(LPCWSTR lpwstrFilename, __int64 a2, __int64 a3)
{
  unsigned int v6; // esi
  DWORD FileVersionInfoSize; // eax
  DWORD v8; // ebx
  void *lpData; // rax
  void *v10; // rdi
  const struct std::nothrow_t *v11; // rdx
  unsigned int v12; // ebx
  LPCWSTR *v13; // rax
  BOOL v14; // ebx
  unsigned int v15; // eax
  __int64 v16; // rcx
  LPCWSTR *v17; // rax
  BOOL v18; // ebx
  unsigned int v19; // eax
  __int64 v20; // rcx
  DWORD dwHandle; // [rsp+30h] [rbp-20h] BYREF
  LPVOID lpBuffer; // [rsp+38h] [rbp-18h] BYREF
  _BYTE v24[8]; // [rsp+40h] [rbp-10h] BYREF
  _BYTE v25[8]; // [rsp+48h] [rbp-8h] BYREF
  unsigned int puLen; // [rsp+98h] [rbp+48h] BYREF

  v6 = 1;
  dwHandle = 0;
  FileVersionInfoSize = GetFileVersionInfoSizeExW(1u, lpwstrFilename, &dwHandle);
  v8 = FileVersionInfoSize;
  if ( FileVersionInfoSize )
  {
    lpData = operator new[](FileVersionInfoSize, (const struct std::nothrow_t *)std::nothrow);
    v10 = lpData;
    if ( lpData )
    {
      if ( GetFileVersionInfoExW(3u, lpwstrFilename, dwHandle, v8, lpData) )
      {
        lpBuffer = 0;
        puLen = 0;
        if ( VerQueryValueW(v10, L"\\VarFileInfo\\Translation", &lpBuffer, &puLen) )
        {
          v12 = *(_DWORD *)lpBuffer;
          ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(v24);
          ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(
            v24,
            L"\\StringFileInfo\\%04X%04X\\",
            (unsigned __int16)v12,
            HIWORD(v12));
          v13 = (LPCWSTR *)ATL::operator+(v25, v24, L"FileVersion");
          v14 = VerQueryValueW(v10, *v13, &lpBuffer, &puLen);
          ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(v25);
          if ( v14 )
          {
            v15 = ocslen((const wchar_t *)lpBuffer);
            ATL::CSimpleStringT<wchar_t,0>::SetString(a2, v16, v15);
            v6 = 0;
            v17 = (LPCWSTR *)ATL::operator+(v25, v24, L"CompanyName");
            v18 = VerQueryValueW(v10, *v17, &lpBuffer, &puLen);
            ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(v25);
            if ( v18 )
            {
              v19 = ocslen((const wchar_t *)lpBuffer);
              ATL::CSimpleStringT<wchar_t,0>::SetString(a3, v20, v19);
            }
          }
          ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(v24);
        }
      }
      operator delete(v10, v11);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18002f524  mov     [rsp-28h+arg_0], rbx
0x18002f529  mov     [rsp-28h+arg_8], rsi
0x18002f52e  push    rbp
0x18002f52f  push    rdi
0x18002f530  push    r12
0x18002f532  push    r14
0x18002f534  push    r15
0x18002f536  mov     rbp, rsp
0x18002f539  sub     rsp, 50h
0x18002f53d  mov     r15, r8
0x18002f540  mov     r12, rdx
0x18002f543  mov     r14, rcx
0x18002f546  mov     esi, 1
0x18002f54b  mov     [rbp+dwHandle], 0
0x18002f552  lea     r8, [rbp+dwHandle]; lpdwHandle
0x18002f556  mov     rdx, rcx; lpwstrFilename
0x18002f559  mov     ecx, esi; dwFlags
0x18002f55b  call    cs:__imp_GetFileVersionInfoSizeExW
0x18002f561  mov     ebx, eax
0x18002f563  test    eax, eax
0x18002f565  jz      loc_18002F6AF
0x18002f56b  mov     ecx, ebx; unsigned __int64
0x18002f56d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002f574  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002f579  mov     rdi, rax
0x18002f57c  test    rax, rax
0x18002f57f  jz      loc_18002F6AF
0x18002f585  mov     [rsp+50h+lpData], rax; lpData
0x18002f58a  mov     r9d, ebx; dwLen
0x18002f58d  mov     r8d, [rbp+dwHandle]; dwHandle
0x18002f591  mov     rdx, r14; lpwstrFilename
0x18002f594  lea     ecx, [rsi+2]; dwFlags
0x18002f597  call    cs:__imp_GetFileVersionInfoExW
0x18002f59d  test    eax, eax
0x18002f59f  jz      loc_18002F6A7
0x18002f5a5  mov     [rbp+lpBuffer], 0
0x18002f5ad  mov     [rbp+puLen], 0
0x18002f5b4  lea     r9, [rbp+puLen]; puLen
0x18002f5b8  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x18002f5bc  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x18002f5c3  mov     rcx, rdi; pBlock
0x18002f5c6  call    cs:__imp_VerQueryValueW
0x18002f5cc  test    eax, eax
0x18002f5ce  jz      loc_18002F6A7
0x18002f5d4  mov     rax, [rbp+lpBuffer]
0x18002f5d8  mov     ebx, [rax]
0x18002f5da  lea     rcx, [rbp+var_10]
0x18002f5de  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002f5e3  nop
0x18002f5e4  mov     r9d, ebx
0x18002f5e7  shr     r9d, 10h
0x18002f5eb  movzx   r8d, bx
0x18002f5ef  lea     rdx, aStringfileinfo; "\\StringFileInfo\\%04X%04X\\"
0x18002f5f6  lea     rcx, [rbp+var_10]
0x18002f5fa  call    ?Format@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAXPEB_WZZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(wchar_t const *,...)
0x18002f5ff  lea     r8, aFileversion; "FileVersion"
0x18002f606  lea     rdx, [rbp+var_10]
0x18002f60a  lea     rcx, [rbp+var_8]
0x18002f60e  call    ??HATL@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@0@AEBV10@PEB_W@Z; ATL::operator+(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &,wchar_t const *)
0x18002f613  lea     r9, [rbp+puLen]; puLen
0x18002f617  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x18002f61b  mov     rdx, [rax]; lpSubBlock
0x18002f61e  mov     rcx, rdi; pBlock
0x18002f621  call    cs:__imp_VerQueryValueW
0x18002f627  mov     ebx, eax
0x18002f629  lea     rcx, [rbp+var_8]
0x18002f62d  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002f632  test    ebx, ebx
0x18002f634  jz      short loc_18002F69E
0x18002f636  mov     rcx, [rbp+lpBuffer]; wchar_t *
0x18002f63a  call    ?ocslen@@YAHPEB_W@Z; ocslen(wchar_t const *)
0x18002f63f  mov     r8d, eax
0x18002f642  mov     rdx, rcx
0x18002f645  mov     rcx, r12
0x18002f648  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18002f64d  xor     esi, esi
0x18002f64f  lea     r8, aCompanyname; "CompanyName"
0x18002f656  lea     rdx, [rbp+var_10]
0x18002f65a  lea     rcx, [rbp+var_8]
0x18002f65e  call    ??HATL@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@0@AEBV10@PEB_W@Z; ATL::operator+(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &,wchar_t const *)
0x18002f663  lea     r9, [rbp+puLen]; puLen
0x18002f667  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x18002f66b  mov     rdx, [rax]; lpSubBlock
0x18002f66e  mov     rcx, rdi; pBlock
0x18002f671  call    cs:__imp_VerQueryValueW
0x18002f677  mov     ebx, eax
0x18002f679  lea     rcx, [rbp+var_8]
0x18002f67d  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002f682  test    ebx, ebx
0x18002f684  jz      short loc_18002F69E
0x18002f686  mov     rcx, [rbp+lpBuffer]; wchar_t *
0x18002f68a  call    ?ocslen@@YAHPEB_W@Z; ocslen(wchar_t const *)
0x18002f68f  mov     r8d, eax
0x18002f692  mov     rdx, rcx
0x18002f695  mov     rcx, r15
0x18002f698  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18002f69d  nop
0x18002f69e  lea     rcx, [rbp+var_10]
0x18002f6a2  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002f6a7  mov     rcx, rdi; void *
0x18002f6aa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002f6af  mov     eax, esi
0x18002f6b1  lea     r11, [rsp+50h+var_s0]
0x18002f6b6  mov     rbx, [r11+30h]
0x18002f6ba  mov     rsi, [r11+38h]
0x18002f6be  mov     rsp, r11
0x18002f6c1  pop     r15
0x18002f6c3  pop     r14
0x18002f6c5  pop     r12
0x18002f6c7  pop     rdi
0x18002f6c8  pop     rbp
0x18002f6c9  retn
```
