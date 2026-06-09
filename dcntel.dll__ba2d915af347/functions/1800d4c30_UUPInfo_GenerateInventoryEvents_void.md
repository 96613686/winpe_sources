# UUPInfo::GenerateInventoryEvents(void)

- ea: `0x1800d4c30`
- end: `0x1800d573f`
- name: `?GenerateInventoryEvents@UUPInfo@@UEAAJXZ`
- size: `2831`
- prototype: `__int64 __fastcall(UUPInfo *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180008dc0`
- `0x18000929c`
- `0x180009f08`
- `0x180009f14`
- `0x180011ce4`
- `0x1800157b8`
- `0x180016748`
- `0x18001daf0`
- `0x18001dcc8`
- `0x180040f34`
- `0x180041530`
- `0x180041db8`
- `0x180041fcc`
- `0x1800472dc`
- `0x1800d47a8`
- `0x1800d4c30`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d4cb8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d4cb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d4ce2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d4ce2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d56a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d56bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d56d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d56f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d570b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5725`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d56a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d56bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d56d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d56f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d570b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5725`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d51a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d5314`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d53dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d54a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d556f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d558c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d51a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d5314`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d53dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d54a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d556f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d558c`

## string_xrefs

- `0x1800d4cb1`: `ProductEnumerator.dll`
- `0x1800d4cd8`: `PE_CreateProductEnumerator`
- `0x1800d4d1a`: `onecore\base\appcompat\programs\devicecensus\dlls\uupinfo.cpp`
- `0x1800d4da7`: `onecore\base\appcompat\programs\devicecensus\dlls\uupinfo.cpp`
- `0x1800d4e5b`: `onecore\base\appcompat\programs\devicecensus\dlls\uupinfo.cpp`
- `0x1800d4ee9`: `onecore\base\appcompat\programs\devicecensus\dlls\uupinfo.cpp`
- `0x1800d4f7f`: `onecore\base\appcompat\programs\devicecensus\dlls\uupinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall UUPInfo::GenerateInventoryEvents(UUPInfo *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  UUPInfo *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned int v20; // esi
  __int64 v21; // rbx
  int (__fastcall *v22)(__int64, _QWORD, __int64 **); // rdi
  __int64 *v23; // rcx
  _QWORD *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // r8
  _QWORD *v27; // rcx
  unsigned __int64 v28; // rdx
  void **v29; // rdi
  __int64 v30; // rbx
  __int64 *v31; // rbx
  int (__fastcall *v32)(__int64 *, const wchar_t *, _QWORD **); // rdi
  _QWORD *v33; // rcx
  _QWORD *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // r8
  unsigned __int64 v37; // rdx
  void **v38; // rdi
  __int64 v39; // rbx
  __int64 *v40; // rbx
  int (__fastcall *v41)(__int64 *, const wchar_t *, _QWORD **); // rdi
  _QWORD *v42; // rcx
  __int64 v43; // rax
  __int64 v44; // r8
  unsigned __int64 v45; // rdx
  void **v46; // rdi
  __int64 v47; // rbx
  __int64 *v48; // rbx
  int (__fastcall *v49)(__int64 *, const wchar_t *, _QWORD **); // rdi
  _QWORD *v50; // rcx
  __int64 v51; // rax
  __int64 v52; // r8
  unsigned __int64 v53; // rdx
  void **v54; // rdi
  __int64 v55; // rbx
  __int64 *v56; // rbx
  int (__fastcall *v57)(__int64 *, const wchar_t *, _QWORD **); // rdi
  __int64 v58; // rax
  __int64 v59; // r8
  unsigned __int64 v60; // rdx
  void **v61; // rdi
  __int64 v62; // rbx
  _QWORD *v63; // rcx
  __int64 *v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rcx
  signed int v67; // eax
  int v68; // edx
  unsigned int v69; // r8d
  signed int LastError; // eax
  int v71; // edx
  unsigned int v72; // r8d
  signed int v73; // eax
  int v74; // edx
  unsigned int v75; // r8d
  signed int v76; // eax
  int v77; // edx
  unsigned int v78; // r8d
  signed int v79; // eax
  int v80; // edx
  unsigned int v81; // r8d
  signed int v82; // eax
  int v83; // edx
  unsigned int v84; // r8d
  int v85; // [rsp+20h] [rbp-E0h]
  _QWORD *v86; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v87; // [rsp+48h] [rbp-B8h] BYREF
  void *Src; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v89; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v90; // [rsp+60h] [rbp-A0h] BYREF
  const int *v91; // [rsp+68h] [rbp-98h] BYREF
  HMODULE v92; // [rsp+70h] [rbp-90h]
  unsigned int v93; // [rsp+78h] [rbp-88h] BYREF
  LPVOID pv[2]; // [rsp+80h] [rbp-80h] BYREF
  void **v95; // [rsp+90h] [rbp-70h] BYREF
  void *v96[3]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v97; // [rsp+B0h] [rbp-50h]
  void *v98[3]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v99; // [rsp+D0h] [rbp-30h]
  void *v100[3]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v101; // [rsp+F0h] [rbp-10h]
  void *v102[3]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int64 v103; // [rsp+110h] [rbp+10h]
  void *v104[3]; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int64 v105; // [rsp+130h] [rbp+30h]
  __int64 v106; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v107[80]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v108; // [rsp+198h] [rbp+98h]
  __int16 v109; // [rsp+1A0h] [rbp+A0h]
  __int64 v110; // [rsp+1A8h] [rbp+A8h]
  __int128 v111; // [rsp+1B0h] [rbp+B0h]
  __int64 v112; // [rsp+1C0h] [rbp+C0h]
  int v113; // [rsp+1C8h] [rbp+C8h]
  char v114; // [rsp+1CCh] [rbp+CCh]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  memset_0(v107, 0, 0x4Eu);
  v109 = 0;
  v110 = 0;
  v111 = 0;
  v112 = 0;
  v113 = 0;
  v114 = 0;
  v108 = 0;
  v106 = 0;
  Library = LoadLibraryExW(L"ProductEnumerator.dll", 0, 0x800u);
  v91 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v92 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "PE_CreateProductEnumerator");
    if ( ProcAddress )
    {
      v89 = 0;
      v87 = 0;
      v93 = 0;
      v3 = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v89);
      v4 = v3;
      if ( v3 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3A,
          (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\uupinfo.cpp",
          (const char *)(unsigned int)v3,
          v85);
        v5 = v89;
        if ( v89 )
        {
          v89 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        }
        v91 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
        if ( !v92 )
          goto LABEL_39;
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v91) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v71, v72);
          __debugbreak();
        }
LABEL_38:
        v92 = 0;
LABEL_39:
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v106);
        return v4;
      }
      if ( !v89 )
      {
        v4 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3B,
          (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\uupinfo.cpp",
          (const char *)0x8007000ELL,
          v85);
        v6 = v89;
        if ( v89 )
        {
          v89 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        }
        v91 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
        if ( !v92 )
          goto LABEL_39;
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v91) )
        {
          v73 = GetLastError();
          if ( v73 > 0 )
            v73 = (unsigned __int16)v73 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v73, v74, v75);
          __debugbreak();
        }
        goto LABEL_38;
      }
      v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v89 + 24LL))(v89, &v87);
      v4 = v7;
      if ( v7 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3C,
          (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\uupinfo.cpp",
          (const char *)(unsigned int)v7,
          v85);
        v8 = v87;
        if ( v87 )
        {
          v87 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        }
        v9 = v89;
        if ( v89 )
        {
          v89 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
        v91 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
        if ( !v92 )
          goto LABEL_39;
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v91) )
        {
          v76 = GetLastError();
          if ( v76 > 0 )
            v76 = (unsigned __int16)v76 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v76, v77, v78);
          __debugbreak();
        }
        goto LABEL_38;
      }
      if ( !v87 )
      {
        v4 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3D,
          (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\uupinfo.cpp",
          (const char *)0x8007000ELL,
          v85);
        v10 = v87;
        if ( v87 )
        {
          v87 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        }
        v11 = v89;
        if ( v89 )
        {
          v89 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
        v91 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
        if ( !v92 )
          goto LABEL_39;
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v91) )
        {
          v79 = GetLastError();
          if ( v79 > 0 )
            v79 = (unsigned __int16)v79 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v79, v80, v81);
          __debugbreak();
        }
        goto LABEL_38;
      }
      v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v87 + 24LL))(v87, &v93);
      v4 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3E,
          (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\uupinfo.cpp",
          (const char *)(unsigned int)v12,
          v85);
        v13 = v87;
        if ( v87 )
        {
          v87 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
        v14 = v89;
        if ( v89 )
        {
          v89 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
        v91 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
        if ( !v92 )
          goto LABEL_39;
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v91) )
        {
          v82 = GetLastError();
          if ( v82 > 0 )
            v82 = (unsigned __int16)v82 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v82, v83, v84);
          JUMPOUT(0x1800D573ELL);
        }
        goto LABEL_38;
      }
      Src = operator new(0xA8u);
      v16 = UUPInfo::UUPInfo((UUPInfo *)Src);
      if ( (int)TelCacheProvider::Initialize(&v106, L"InventoryMiscellaneousUUPInfo", (__int64)v16, 0, 1u, 3) < 0 )
      {
        v17 = v87;
        if ( v87 )
        {
          v87 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
LABEL_47:
        v19 = v89;
        if ( v89 )
        {
          v89 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        goto LABEL_138;
      }
      if ( (int)TelCacheProvider::BatchBegin((TelCacheProvider *)&v106) < 0 )
      {
        v18 = v87;
        if ( v87 )
        {
          v87 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
        goto LABEL_47;
      }
      v20 = 0;
      if ( !v93 )
      {
LABEL_133:
        v65 = v87;
        if ( v87 )
        {
          v87 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
        }
        v66 = v89;
        if ( v89 )
        {
          v89 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
        }
        TelCacheProvider::BatchEnd((TelCacheProvider *)&v106);
        goto LABEL_138;
      }
      while ( 1 )
      {
        v90 = 0;
        v86 = 0;
        UUPInfo::UUPInfo((UUPInfo *)&v95);
        v21 = v87;
        v22 = *(int (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v87 + 32LL);
        v23 = v90;
        if ( v90 )
        {
          v90 = 0;
          (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
        }
        if ( v22(v21, v20, &v90) < 0 )
          goto LABEL_128;
        if ( v90 )
        {
          pv[0] = 0;
          v25 = *v90;
          pv[0] = 0;
          if ( (*(int (__fastcall **)(__int64 *, LPVOID *))(v25 + 24))(v90, pv) >= 0 )
          {
            v28 = -1;
            do
              ++v28;
            while ( *((_WORD *)pv[0] + v28) );
            if ( v28 > v97 )
            {
              std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                (char **)v96,
                v28,
                v26,
                pv[0]);
            }
            else
            {
              v29 = v96;
              if ( v97 > 7 )
                v29 = (void **)v96[0];
              v96[2] = (void *)v28;
              v30 = 2 * v28;
              memmove_0(v29, pv[0], 2 * v28);
              *(_WORD *)((char *)v29 + v30) = 0;
            }
            v31 = v90;
            v32 = *(int (__fastcall **)(__int64 *, const wchar_t *, _QWORD **))(*v90 + 40);
            v33 = v86;
            if ( v86 )
            {
              v86 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v33 + 16LL))(v33);
            }
            if ( v32(v31, L"Version", &v86) < 0 )
            {
LABEL_84:
              v34 = v86;
            }
            else
            {
              v34 = v86;
              if ( v86 )
              {
                Src = 0;
                v35 = *v86;
                Src = 0;
                (*(void (__fastcall **)(_QWORD *, void **))(v35 + 32))(v86, &Src);
                v37 = -1;
                do
                  ++v37;
                while ( *((_WORD *)Src + v37) );
                if ( v37 > v99 )
                {
                  std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                    (char **)v98,
                    v37,
                    v36,
                    Src);
                }
                else
                {
                  v38 = v98;
                  if ( v99 > 7 )
                    v38 = (void **)v98[0];
                  v98[2] = (void *)v37;
                  v39 = 2 * v37;
                  memmove_0(v38, Src, 2 * v37);
                  *(_WORD *)((char *)v38 + v39) = 0;
                }
                if ( Src )
                  CoTaskMemFree(Src);
                goto LABEL_84;
              }
            }
            v40 = v90;
            v41 = *(int (__fastcall **)(__int64 *, const wchar_t *, _QWORD **))(*v90 + 40);
            if ( v34 )
            {
              v86 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v34 + 16LL))(v34);
            }
            if ( v41(v40, L"Source", &v86) < 0 )
            {
LABEL_98:
              v42 = v86;
            }
            else
            {
              v42 = v86;
              if ( v86 )
              {
                Src = 0;
                v43 = *v86;
                Src = 0;
                (*(void (__fastcall **)(_QWORD *, void **))(v43 + 32))(v86, &Src);
                v45 = -1;
                do
                  ++v45;
                while ( *((_WORD *)Src + v45) );
                if ( v45 > v101 )
                {
                  std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                    (char **)v100,
                    v45,
                    v44,
                    Src);
                }
                else
                {
                  v46 = v100;
                  if ( v101 > 7 )
                    v46 = (void **)v100[0];
                  v100[2] = (void *)v45;
                  v47 = 2 * v45;
                  memmove_0(v46, Src, 2 * v45);
                  *(_WORD *)((char *)v46 + v47) = 0;
                }
                if ( Src )
                  CoTaskMemFree(Src);
                goto LABEL_98;
              }
            }
            v48 = v90;
            v49 = *(int (__fastcall **)(__int64 *, const wchar_t *, _QWORD **))(*v90 + 40);
            if ( v42 )
            {
              v86 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v42 + 16LL))(v42);
            }
            if ( v49(v48, L"PreviousVersion", &v86) < 0 )
            {
LABEL_112:
              v50 = v86;
            }
            else
            {
              v50 = v86;
              if ( v86 )
              {
                Src = 0;
                v51 = *v86;
                Src = 0;
                (*(void (__fastcall **)(_QWORD *, void **))(v51 + 32))(v86, &Src);
                v53 = -1;
                do
                  ++v53;
                while ( *((_WORD *)Src + v53) );
                if ( v53 > v103 )
                {
                  std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                    (char **)v102,
                    v53,
                    v52,
                    Src);
                }
                else
                {
                  v54 = v102;
                  if ( v103 > 7 )
                    v54 = (void **)v102[0];
                  v102[2] = (void *)v53;
                  v55 = 2 * v53;
                  memmove_0(v54, Src, 2 * v53);
                  *(_WORD *)((char *)v54 + v55) = 0;
                }
                if ( Src )
                  CoTaskMemFree(Src);
                goto LABEL_112;
              }
            }
            v56 = v90;
            v57 = *(int (__fastcall **)(__int64 *, const wchar_t *, _QWORD **))(*v90 + 40);
            if ( v50 )
            {
              v86 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v50 + 16LL))(v50);
            }
            if ( v57(v56, L"LastActivatedVersion", &v86) >= 0 && v86 )
            {
              Src = 0;
              v58 = *v86;
              Src = 0;
              (*(void (__fastcall **)(_QWORD *, void **))(v58 + 32))(v86, &Src);
              v60 = -1;
              do
                ++v60;
              while ( *((_WORD *)Src + v60) );
              if ( v60 > v105 )
              {
                std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                  (char **)v104,
                  v60,
                  v59,
                  Src);
              }
              else
              {
                v61 = v104;
                if ( v105 > 7 )
                  v61 = (void **)v104[0];
                v104[2] = (void *)v60;
                v62 = 2 * v60;
                memmove_0(v61, Src, 2 * v60);
                *(_WORD *)((char *)v61 + v62) = 0;
              }
              if ( Src )
                CoTaskMemFree(Src);
            }
            TelCacheProvider::AddItem((TelCacheProvider *)&v106, (struct IAmiInventoryItem *)&v95);
            if ( pv[0] )
              CoTaskMemFree(pv[0]);
LABEL_128:
            v95 = &UUPInfo::`vftable';
            std::wstring::~wstring((char **)v104);
            std::wstring::~wstring((char **)v102);
            std::wstring::~wstring((char **)v100);
            std::wstring::~wstring((char **)v98);
            std::wstring::~wstring((char **)v96);
            v95 = &IAmiInventoryItem::`vftable';
            v63 = v86;
            if ( v86 )
            {
              v86 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v63 + 16LL))(v63);
            }
            goto LABEL_130;
          }
          if ( pv[0] )
            CoTaskMemFree(pv[0]);
          v95 = &UUPInfo::`vftable';
          std::wstring::~wstring((char **)v104);
          std::wstring::~wstring((char **)v102);
          std::wstring::~wstring((char **)v100);
          std::wstring::~wstring((char **)v98);
          std::wstring::~wstring((char **)v96);
          v95 = &IAmiInventoryItem::`vftable';
          v27 = v86;
          if ( v86 )
          {
            v86 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v27 + 16LL))(v27);
          }
        }
        else
        {
          v95 = &UUPInfo::`vftable';
          std::wstring::~wstring((char **)v104);
          std::wstring::~wstring((char **)v102);
          std::wstring::~wstring((char **)v100);
          std::wstring::~wstring((char **)v98);
          std::wstring::~wstring((char **)v96);
          v95 = &IAmiInventoryItem::`vftable';
          v24 = v86;
          if ( v86 )
          {
            v86 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
          }
        }
LABEL_130:
        v64 = v90;
        if ( v90 )
        {
          v90 = 0;
          (*(void (__fastcall **)(__int64 *))(*v64 + 16))(v64);
        }
        if ( ++v20 >= v93 )
          goto LABEL_133;
      }
    }
  }
LABEL_138:
  v91 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( v92 )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v91) )
    {
      v67 = GetLastError();
      if ( v67 > 0 )
        v67 = (unsigned __int16)v67 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v67, v68, v69);
      __debugbreak();
    }
    v92 = 0;
  }
  TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v106);
  return 0;
}

```

## disassembly

```asm
0x1800d4c30  push    rbp
0x1800d4c32  push    rbx
0x1800d4c33  push    rsi
0x1800d4c34  push    rdi
0x1800d4c35  push    r12
0x1800d4c37  push    r13
0x1800d4c39  push    r14
0x1800d4c3b  push    r15
0x1800d4c3d  lea     rbp, [rsp-0E8h]
0x1800d4c45  sub     rsp, 1E8h
0x1800d4c4c  mov     rax, cs:__security_cookie
0x1800d4c53  xor     rax, rsp
0x1800d4c56  mov     [rbp+120h+var_50], rax
0x1800d4c5d  xor     edx, edx; Val
0x1800d4c5f  lea     r8d, [rdx+4Eh]; Size
0x1800d4c63  lea     rcx, [rbp+120h+var_D8]; void *
0x1800d4c67  call    memset_0
0x1800d4c6c  xor     r14d, r14d
0x1800d4c6f  mov     [rbp+120h+var_80], r14w
0x1800d4c77  mov     [rbp+120h+var_78], r14
0x1800d4c7e  xorps   xmm0, xmm0
0x1800d4c81  movdqa  [rbp+120h+var_70], xmm0
0x1800d4c89  mov     [rbp+120h+var_60], r14
0x1800d4c90  mov     [rbp+120h+var_58], r14d
0x1800d4c97  mov     [rbp+120h+var_54], r14b
0x1800d4c9e  mov     [rbp+120h+var_88], r14
0x1800d4ca5  mov     [rbp+120h+var_E0], r14
0x1800d4ca9  xor     edx, edx; hFile
0x1800d4cab  mov     r8d, 800h; dwFlags
0x1800d4cb1  lea     rcx, aProductenumera; "ProductEnumerator.dll"
0x1800d4cb8  call    cs:__imp_LoadLibraryExW
0x1800d4cbe  lea     r15, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800d4cc5  mov     [rsp+220h+var_1B8], r15
0x1800d4cca  mov     [rsp+220h+var_1B0], rax
0x1800d4ccf  test    rax, rax
0x1800d4cd2  jz      loc_1800D5655
0x1800d4cd8  lea     rdx, aPeCreateproduc; "PE_CreateProductEnumerator"
0x1800d4cdf  mov     rcx, rax; hModule
0x1800d4ce2  call    cs:__imp_GetProcAddress
0x1800d4ce8  test    rax, rax
0x1800d4ceb  jz      loc_1800D5655
0x1800d4cf1  mov     [rsp+220h+var_1C8], r14
0x1800d4cf6  mov     [rsp+220h+var_1D8], r14
0x1800d4cfb  mov     [rsp+220h+var_1A8], r14d
0x1800d4d00  lea     rcx, [rsp+220h+var_1C8]
0x1800d4d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4d0a  mov     ebx, eax
0x1800d4d0c  test    eax, eax
0x1800d4d0e  jns     short loc_1800D4D8A
0x1800d4d10  mov     rcx, [rbp+128h]; this
0x1800d4d17  mov     r9d, eax; char *
0x1800d4d1a  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\programs\\dev"...
0x1800d4d21  lea     edx, [r14+3Ah]; void *
0x1800d4d25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4d2a  nop
0x1800d4d2b  mov     rcx, [rsp+220h+var_1D8]
0x1800d4d30  test    rcx, rcx
0x1800d4d33  jz      short loc_1800D4D47
0x1800d4d35  mov     [rsp+220h+var_1D8], r14
0x1800d4d3a  mov     rax, [rcx]
0x1800d4d3d  mov     rax, [rax+10h]
0x1800d4d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4d46  nop
0x1800d4d47  mov     rcx, [rsp+220h+var_1C8]
0x1800d4d4c  test    rcx, rcx
0x1800d4d4f  jz      short loc_1800D4D63
0x1800d4d51  mov     [rsp+220h+var_1C8], r14
0x1800d4d56  mov     rax, [rcx]
0x1800d4d59  mov     rax, [rax+10h]
0x1800d4d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4d62  nop
0x1800d4d63  mov     [rsp+220h+var_1B8], r15
0x1800d4d68  cmp     [rsp+220h+var_1B0], r14
0x1800d4d6d  jz      loc_1800D4FEC
0x1800d4d73  lea     rcx, [rsp+220h+var_1B8]
0x1800d4d78  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800d4d7d  test    al, al
0x1800d4d7f  jz      loc_1800D56BD
0x1800d4d85  jmp     loc_1800D4FE7
0x1800d4d8a  mov     rbx, [rsp+220h+var_1C8]
0x1800d4d8f  test    rbx, rbx
0x1800d4d92  jnz     loc_1800D4E18
0x1800d4d98  mov     rcx, [rbp+128h]; this
0x1800d4d9f  mov     ebx, 8007000Eh
0x1800d4da4  mov     r9d, ebx; char *
0x1800d4da7  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\programs\\dev"...
0x1800d4dae  mov     edx, 3Bh ; ';'; void *
0x1800d4db3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4db8  nop
0x1800d4db9  mov     rcx, [rsp+220h+var_1D8]
0x1800d4dbe  test    rcx, rcx
0x1800d4dc1  jz      short loc_1800D4DD5
0x1800d4dc3  mov     [rsp+220h+var_1D8], r14
0x1800d4dc8  mov     rax, [rcx]
0x1800d4dcb  mov     rax, [rax+10h]
0x1800d4dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4dd4  nop
0x1800d4dd5  mov     rcx, [rsp+220h+var_1C8]
0x1800d4dda  test    rcx, rcx
0x1800d4ddd  jz      short loc_1800D4DF1
0x1800d4ddf  mov     [rsp+220h+var_1C8], r14
0x1800d4de4  mov     rax, [rcx]
0x1800d4de7  mov     rax, [rax+10h]
0x1800d4deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4df0  nop
0x1800d4df1  mov     [rsp+220h+var_1B8], r15
0x1800d4df6  cmp     [rsp+220h+var_1B0], r14
0x1800d4dfb  jz      loc_1800D4FEC
0x1800d4e01  lea     rcx, [rsp+220h+var_1B8]
0x1800d4e06  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800d4e0b  test    al, al
0x1800d4e0d  jz      loc_1800D56D7
0x1800d4e13  jmp     loc_1800D4FE7
0x1800d4e18  mov     rax, [rbx]
0x1800d4e1b  mov     rdi, [rax+18h]
0x1800d4e1f  mov     rcx, [rsp+220h+var_1D8]
0x1800d4e24  test    rcx, rcx
0x1800d4e27  jz      short loc_1800D4E3B
0x1800d4e29  mov     [rsp+220h+var_1D8], r14
0x1800d4e2e  mov     rdx, [rcx]
0x1800d4e31  mov     rax, [rdx+10h]
0x1800d4e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4e3a  nop
0x1800d4e3b  lea     rdx, [rsp+220h+var_1D8]
0x1800d4e40  mov     rcx, rbx
0x1800d4e43  mov     rax, rdi
0x1800d4e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4e4b  mov     ebx, eax
0x1800d4e4d  test    eax, eax
0x1800d4e4f  jns     short loc_1800D4ECC
0x1800d4e51  mov     rcx, [rbp+128h]; this
0x1800d4e58  mov     r9d, eax; char *
0x1800d4e5b  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\programs\\dev"...
0x1800d4e62  mov     edx, 3Ch ; '<'; void *
0x1800d4e67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4e6c  nop
0x1800d4e6d  mov     rcx, [rsp+220h+var_1D8]
0x1800d4e72  test    rcx, rcx
0x1800d4e75  jz      short loc_1800D4E89
0x1800d4e77  mov     [rsp+220h+var_1D8], r14
0x1800d4e7c  mov     rax, [rcx]
0x1800d4e7f  mov     rax, [rax+10h]
0x1800d4e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4e88  nop
0x1800d4e89  mov     rcx, [rsp+220h+var_1C8]
0x1800d4e8e  test    rcx, rcx
0x1800d4e91  jz      short loc_1800D4EA5
0x1800d4e93  mov     [rsp+220h+var_1C8], r14
0x1800d4e98  mov     rax, [rcx]
0x1800d4e9b  mov     rax, [rax+10h]
0x1800d4e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4ea4  nop
0x1800d4ea5  mov     [rsp+220h+var_1B8], r15
0x1800d4eaa  cmp     [rsp+220h+var_1B0], r14
0x1800d4eaf  jz      loc_1800D4FEC
0x1800d4eb5  lea     rcx, [rsp+220h+var_1B8]
0x1800d4eba  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800d4ebf  test    al, al
0x1800d4ec1  jz      loc_1800D56F1
0x1800d4ec7  jmp     loc_1800D4FE7
0x1800d4ecc  mov     rcx, [rsp+220h+var_1D8]
0x1800d4ed1  test    rcx, rcx
0x1800d4ed4  jnz     loc_1800D4F5A
0x1800d4eda  mov     rcx, [rbp+128h]; this
0x1800d4ee1  mov     ebx, 8007000Eh
0x1800d4ee6  mov     r9d, ebx; char *
0x1800d4ee9  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\programs\\dev"...
0x1800d4ef0  mov     edx, 3Dh ; '='; void *
0x1800d4ef5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4efa  nop
0x1800d4efb  mov     rcx, [rsp+220h+var_1D8]
0x1800d4f00  test    rcx, rcx
0x1800d4f03  jz      short loc_1800D4F17
0x1800d4f05  mov     [rsp+220h+var_1D8], r14
0x1800d4f0a  mov     rax, [rcx]
0x1800d4f0d  mov     rax, [rax+10h]
0x1800d4f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4f16  nop
0x1800d4f17  mov     rcx, [rsp+220h+var_1C8]
0x1800d4f1c  test    rcx, rcx
0x1800d4f1f  jz      short loc_1800D4F33
0x1800d4f21  mov     [rsp+220h+var_1C8], r14
0x1800d4f26  mov     rax, [rcx]
0x1800d4f29  mov     rax, [rax+10h]
0x1800d4f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4f32  nop
0x1800d4f33  mov     [rsp+220h+var_1B8], r15
0x1800d4f38  cmp     [rsp+220h+var_1B0], r14
0x1800d4f3d  jz      loc_1800D4FEC
0x1800d4f43  lea     rcx, [rsp+220h+var_1B8]
0x1800d4f48  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800d4f4d  test    al, al
0x1800d4f4f  jz      loc_1800D570B
0x1800d4f55  jmp     loc_1800D4FE7
0x1800d4f5a  mov     rax, [rcx]
0x1800d4f5d  lea     rdx, [rsp+220h+var_1A8]
0x1800d4f62  mov     rax, [rax+18h]
0x1800d4f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4f6b  mov     ebx, eax
0x1800d4f6d  test    eax, eax
0x1800d4f6f  jns     loc_1800D4FFC
0x1800d4f75  mov     rcx, [rbp+128h]; this
0x1800d4f7c  mov     r9d, eax; char *
0x1800d4f7f  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\programs\\dev"...
0x1800d4f86  mov     edx, 3Eh ; '>'; void *
0x1800d4f8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4f90  nop
0x1800d4f91  mov     rcx, [rsp+220h+var_1D8]
0x1800d4f96  test    rcx, rcx
0x1800d4f99  jz      short loc_1800D4FAD
0x1800d4f9b  mov     [rsp+220h+var_1D8], r14
0x1800d4fa0  mov     rax, [rcx]
0x1800d4fa3  mov     rax, [rax+10h]
0x1800d4fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4fac  nop
0x1800d4fad  mov     rcx, [rsp+220h+var_1C8]
0x1800d4fb2  test    rcx, rcx
0x1800d4fb5  jz      short loc_1800D4FC9
0x1800d4fb7  mov     [rsp+220h+var_1C8], r14
0x1800d4fbc  mov     rax, [rcx]
0x1800d4fbf  mov     rax, [rax+10h]
0x1800d4fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4fc8  nop
0x1800d4fc9  mov     [rsp+220h+var_1B8], r15
0x1800d4fce  cmp     [rsp+220h+var_1B0], r14
0x1800d4fd3  jz      short loc_1800D4FEC
0x1800d4fd5  lea     rcx, [rsp+220h+var_1B8]
0x1800d4fda  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800d4fdf  test    al, al
0x1800d4fe1  jz      loc_1800D5725
0x1800d4fe7  mov     [rsp+220h+var_1B0], r14
0x1800d4fec  lea     rcx, [rbp+120h+var_E0]; this
0x1800d4ff0  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x1800d4ff5  mov     eax, ebx
0x1800d4ff7  jmp     loc_1800D567F
0x1800d4ffc  mov     ecx, 0A8h; Size
0x1800d5001  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d5006  mov     [rsp+220h+Src], rax
0x1800d500b  mov     rcx, rax; this
0x1800d500e  call    ??0UUPInfo@@QEAA@XZ; UUPInfo::UUPInfo(void)
0x1800d5013  nop
0x1800d5014  mov     [rsp+220h+var_1F0], 64h ; 'd'
0x1800d501c  mov     [rsp+220h+var_1F8], 3
0x1800d5024  mov     [rsp+220h+var_200], 1
0x1800d502c  xor     r9d, r9d
0x1800d502f  mov     r8, rax
0x1800d5032  lea     rdx, aInventorymisce_0; "InventoryMiscellaneousUUPInfo"
0x1800d5039  lea     rcx, [rbp+120h+var_E0]
0x1800d503d  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x1800d5042  test    eax, eax
0x1800d5044  jns     short loc_1800D5064
0x1800d5046  mov     rcx, [rsp+220h+var_1D8]
0x1800d504b  test    rcx, rcx
0x1800d504e  jz      short loc_1800D5062
0x1800d5050  mov     [rsp+220h+var_1D8], r14
0x1800d5055  mov     rax, [rcx]
0x1800d5058  mov     rax, [rax+10h]
0x1800d505c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5061  nop
0x1800d5062  jmp     short loc_1800D508D
0x1800d5064  lea     rcx, [rbp+120h+var_E0]; this
0x1800d5068  call    ?BatchBegin@TelCacheProvider@@QEAAJXZ; TelCacheProvider::BatchBegin(void)
0x1800d506d  test    eax, eax
0x1800d506f  jns     short loc_1800D50AE
0x1800d5071  mov     rcx, [rsp+220h+var_1D8]
0x1800d5076  test    rcx, rcx
0x1800d5079  jz      short loc_1800D508D
0x1800d507b  mov     [rsp+220h+var_1D8], r14
0x1800d5080  mov     rax, [rcx]
0x1800d5083  mov     rax, [rax+10h]
0x1800d5087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d508c  nop
0x1800d508d  mov     rcx, [rsp+220h+var_1C8]
0x1800d5092  test    rcx, rcx
0x1800d5095  jz      short loc_1800D50A9
0x1800d5097  mov     [rsp+220h+var_1C8], r14
0x1800d509c  mov     rax, [rcx]
0x1800d509f  mov     rax, [rax+10h]
0x1800d50a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d50a8  nop
0x1800d50a9  jmp     loc_1800D5655
0x1800d50ae  mov     esi, r14d
0x1800d50b1  cmp     [rsp+220h+var_1A8], r14d
0x1800d50b6  jbe     loc_1800D5613
0x1800d50bc  lea     r13, ??_7UUPInfo@@6B@; const UUPInfo::`vftable'
0x1800d50c3  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800d50c7  lea     r15, ??_7IAmiInventoryItem@@6B@; const IAmiInventoryItem::`vftable'
0x1800d50ce  mov     [rsp+220h+var_1C0], r14
0x1800d50d3  mov     [rsp+220h+var_1E0], r14
0x1800d50d8  lea     rcx, [rbp+120h+var_190]; this
0x1800d50dc  call    ??0UUPInfo@@QEAA@XZ; UUPInfo::UUPInfo(void)
0x1800d50e1  nop
0x1800d50e2  mov     rbx, [rsp+220h+var_1D8]
0x1800d50e7  mov     rax, [rbx]
0x1800d50ea  mov     rdi, [rax+20h]
0x1800d50ee  mov     rcx, [rsp+220h+var_1C0]
0x1800d50f3  test    rcx, rcx
0x1800d50f6  jz      short loc_1800D510A
0x1800d50f8  mov     [rsp+220h+var_1C0], r14
0x1800d50fd  mov     rdx, [rcx]
  ... truncated ...
```
