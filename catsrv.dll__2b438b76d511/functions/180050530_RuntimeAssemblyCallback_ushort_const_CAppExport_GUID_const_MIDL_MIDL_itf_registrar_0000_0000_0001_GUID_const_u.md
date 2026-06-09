# RuntimeAssemblyCallback(ushort const *,CAppExport *,_GUID const &,__MIDL___MIDL_itf_registrar_0000_0000_0001,_GUID const &,ushort * *,EFileType *)

- ea: `0x180050530`
- end: `0x180050b23`
- name: `?RuntimeAssemblyCallback@@YAJPEBGPEAVCAppExport@@AEBU_GUID@@W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@2PEAPEAGPEAW4EFileType@@@Z`
- size: `1523`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000e7e0`
- `0x180011aec`
- `0x1800241bc`
- `0x180049db8`
- `0x180050338`
- `0x180050530`
- `0x180050b2c`
- `0x180052ee8`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `CLBCatQ!ServerGetApplicationType` at `0x1800505dd`
- `CLBCatQ!ServerGetApplicationType` at `0x1800505dd`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800506da`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800506e6`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800506f1`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x180050880`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18005088b`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x180050896`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800506da`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800506e6`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800506f1`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x180050880`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18005088b`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x180050896`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x180050693`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x1800506a5`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x18005083a`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x18005084b`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x180050693`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x1800506a5`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x18005083a`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x18005084b`
- `MfcSubs!??H@YA?AVCString@@AEBV0@0@Z` at `0x1800506b6`
- `MfcSubs!??H@YA?AVCString@@AEBV0@0@Z` at `0x18005085c`
- `MfcSubs!??H@YA?AVCString@@AEBV0@0@Z` at `0x1800506b6`
- `MfcSubs!??H@YA?AVCString@@AEBV0@0@Z` at `0x18005085c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800509c7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800509c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050a89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050a99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050aaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ac4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ad7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ae6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050af4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050a89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050a99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050aaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ac4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ad7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ae6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050af4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800508f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800508f5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180050614`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180050614`

## string_xrefs

- `0x1800505f4`: `SOFTWARE\Classes\CLSID`
- `0x1800505ed`: `SOFTWARE\Classes\Wow6432Node\CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall RuntimeAssemblyCallback(
        __int64 a1,
        __int64 a2,
        GUID *a3,
        __int64 a4,
        struct _GUID *a5,
        LPVOID *a6,
        _DWORD *a7)
{
  void *v7; // r13
  unsigned __int16 *v8; // rsi
  wchar_t *v9; // r12
  unsigned __int16 **v10; // r14
  unsigned int v11; // r15d
  int ApplicationType; // ebx
  const wchar_t *v13; // rdi
  SIZE_T v14; // r12
  __int64 (__fastcall *v15)(__int64, _QWORD, const wchar_t *); // rdi
  CString *v16; // rbx
  CString *v17; // rax
  _QWORD *v18; // rax
  unsigned __int64 v19; // rcx
  LPVOID v20; // rax
  __int64 (__fastcall *v21)(__int64, _QWORD, const wchar_t *); // rdi
  CString *v22; // rbx
  CString *v23; // rax
  _QWORD *v24; // rax
  wchar_t *v25; // rdi
  int AppDirFromCodeBase; // eax
  int v27; // eax
  unsigned int i; // edi
  unsigned int j; // edi
  LPVOID *v30; // rbx
  __int64 v32; // [rsp+38h] [rbp-C8h]
  unsigned int v33; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v34; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v35; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  int v38; // [rsp+60h] [rbp-A0h] BYREF
  SIZE_T cb; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v40; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 **v41; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v42; // [rsp+80h] [rbp-80h]
  LPVOID pv; // [rsp+88h] [rbp-78h] BYREF
  GUID *rguid; // [rsp+90h] [rbp-70h] BYREF
  _DWORD *v45; // [rsp+98h] [rbp-68h] BYREF
  struct _GUID *v46; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-58h]
  LPVOID *v48; // [rsp+B0h] [rbp-50h]
  char v49[8]; // [rsp+B8h] [rbp-48h] BYREF
  GUID pguid; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[40]; // [rsp+D0h] [rbp-30h] BYREF

  rguid = a3;
  v47 = a2;
  v46 = a5;
  v48 = a6;
  v45 = a7;
  cb = 0;
  v36 = 0;
  v37 = 0;
  v7 = 0;
  pv = 0;
  v8 = 0;
  v40 = 0;
  v9 = 0;
  v42 = 0;
  v10 = 0;
  v41 = 0;
  v11 = 0;
  v35 = 0;
  v34 = 0;
  v33 = 0;
  v38 = 1;
  ApplicationType = ServerGetApplicationType(0, a5, &v38);
  if ( ApplicationType >= 0 )
  {
    v13 = L"SOFTWARE\\Classes\\Wow6432Node\\CLSID";
    if ( v38 != 1 )
      v13 = L"SOFTWARE\\Classes\\CLSID";
    *(_QWORD *)&pguid.Data1 = v13;
    StringFromGUID2(rguid, sz, 39);
    ApplicationType = GetRegNodeDispenser((struct IRegNodeDispenser **)&cb);
    v14 = cb;
    if ( ApplicationType >= 0 )
    {
      ApplicationType = (*(__int64 (__fastcall **)(SIZE_T, const wchar_t *, __int64, const wchar_t *, const WCHAR *, int, __int64 *))(*(_QWORD *)cb + 24LL))(
                          cb,
                          L"?",
                          -2147483646,
                          v13,
                          L"\\",
                          131097,
                          &v36);
      if ( ApplicationType >= 0 )
      {
        v15 = *(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *))(*(_QWORD *)v36 + 112LL);
        v16 = CString::CString((CString *)v49, L"\\InprocServer32");
        v17 = CString::CString((CString *)&cb, sz);
        v18 = (_QWORD *)operator+(&rguid, v17, v16);
        ApplicationType = v15(v36, *v18, L"Assembly");
        CString::~CString((CString *)&rguid);
        CString::~CString((CString *)&cb);
        CString::~CString((CString *)v49);
        if ( ApplicationType >= 0 && ApplicationType != 1 )
        {
          (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v36 + 64LL))(v36, &v34);
          (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v36 + 72LL))(v36, &v33);
          v19 = v33 + 1LL;
          if ( v19 < v33 )
          {
            ApplicationType = -2147024362;
          }
          else
          {
            cb = v33 + 1LL;
            ApplicationType = ULongLongMult(v19, 2u, &cb);
            if ( ApplicationType >= 0 )
            {
              v20 = CoTaskMemAlloc(cb);
              v7 = v20;
              if ( v20 )
              {
                ApplicationType = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, LPVOID))(*(_QWORD *)v36 + 80LL))(
                                    v36,
                                    v34,
                                    v33,
                                    v20);
                if ( ApplicationType >= 0 )
                {
                  *v45 = 7;
                  ApplicationType = ServerGetAppInfo(v46, &v40, (unsigned __int16 **)&pv);
                  v8 = v40;
                  if ( ApplicationType >= 0 )
                  {
                    if ( v40 )
                      goto LABEL_21;
                    ApplicationType = (*(__int64 (__fastcall **)(SIZE_T, const wchar_t *, __int64, _QWORD, const WCHAR *, int, __int64 *))(*(_QWORD *)v14 + 24LL))(
                                        v14,
                                        L"?",
                                        -2147483646,
                                        *(_QWORD *)&pguid.Data1,
                                        L"\\",
                                        131097,
                                        &v37);
                    if ( ApplicationType >= 0 )
                    {
                      v21 = *(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *))(*(_QWORD *)v37 + 112LL);
                      v22 = CString::CString((CString *)&v45, L"\\InprocServer32");
                      v23 = CString::CString((CString *)&v46, sz);
                      v24 = (_QWORD *)operator+(&pguid, v23, v22);
                      ApplicationType = v21(v37, *v24, L"CodeBase");
                      CString::~CString((CString *)&pguid);
                      CString::~CString((CString *)&v46);
                      CString::~CString((CString *)&v45);
                      if ( ApplicationType >= 0 )
                      {
                        if ( ApplicationType == 1
                          || ((*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v37 + 64LL))(v37, &v34),
                              (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v37 + 72LL))(v37, &v33),
                              v25 = (wchar_t *)CoTaskMemAlloc(saturated_mul(((unsigned __int64)v33 >> 1) + 2, 2u)),
                              (v42 = v25) != 0)
                          && (ApplicationType = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, wchar_t *))(*(_QWORD *)v37 + 80LL))(
                                                  v37,
                                                  v34,
                                                  v33,
                                                  v25),
                              ApplicationType >= 0)
                          && (AppDirFromCodeBase = GetAppDirFromCodeBase(v25, &v40), v8 = v40, AppDirFromCodeBase) )
                        {
LABEL_21:
                          ApplicationType = GetModules(
                                              v38,
                                              (__int64)pv,
                                              (__int64)v8,
                                              (__int64)v7,
                                              (unsigned __int16 ***)&v41,
                                              &v35);
                          v10 = (unsigned __int16 **)v41;
                          if ( ApplicationType < 0 )
                          {
                            v11 = v35;
                          }
                          else
                          {
                            v27 = CAppExport::AddDllNameInternal(v47, *v41, 7);
                            ApplicationType = v27;
                            v11 = v35;
                            if ( v27 >= 0 )
                            {
                              if ( v27 == 1 )
                              {
                                ApplicationType = 0;
                              }
                              else
                              {
                                for ( i = 1; i < v11; ++i )
                                {
                                  pguid = 0;
                                  ApplicationType = CoCreateGuid(&pguid);
                                  if ( ApplicationType < 0 )
                                    goto LABEL_33;
                                  LODWORD(v32) = 9;
                                  ApplicationType = CAppExport::AddClassInfo(
                                                      v47,
                                                      v10[i],
                                                      &pguid,
                                                      (unsigned __int16 *)&word_18005C890,
                                                      &word_18005C890,
                                                      &word_18005C890,
                                                      &word_18005C890,
                                                      v32);
                                  if ( ApplicationType < 0 )
                                    goto LABEL_33;
                                }
                              }
                              *v48 = *v10;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
              else
              {
                ApplicationType = -2147024882;
              }
            }
          }
        }
      }
    }
LABEL_33:
    if ( v14 )
      (*(void (__fastcall **)(SIZE_T))(*(_QWORD *)v14 + 16LL))(v14);
    v9 = v42;
  }
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  if ( v10 )
  {
    for ( j = 1; j < v11; ++j )
      CoTaskMemFree(v10[j]);
    CoTaskMemFree(v10);
  }
  if ( ApplicationType < 0 )
  {
    v30 = v48;
    if ( *v48 )
    {
      CoTaskMemFree(*v48);
      *v30 = 0;
    }
    if ( v7 )
      CoTaskMemFree(v7);
    ApplicationType = 1;
  }
  if ( v8 )
    CoTaskMemFree(v8);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v9 )
    CoTaskMemFree(v9);
  return (unsigned int)ApplicationType;
}

```

## disassembly

```asm
0x180050530  mov     [rsp-8+arg_0], rbx
0x180050535  push    rbp
0x180050536  push    rsi
0x180050537  push    rdi
0x180050538  push    r12
0x18005053a  push    r13
0x18005053c  push    r14
0x18005053e  push    r15
0x180050540  lea     rbp, [rsp-30h]
0x180050545  sub     rsp, 130h
0x18005054c  mov     rax, cs:__security_cookie
0x180050553  xor     rax, rsp
0x180050556  mov     [rbp+60h+var_40], rax
0x18005055a  mov     [rbp+60h+rguid], r8
0x18005055e  mov     [rbp+60h+var_B8], rdx
0x180050562  mov     rcx, [rbp+60h+arg_20]
0x180050569  mov     [rbp+60h+var_C0], rcx
0x18005056d  mov     rax, [rbp+60h+arg_28]
0x180050574  mov     [rbp+60h+var_B0], rax
0x180050578  mov     rax, [rbp+60h+arg_30]
0x18005057f  mov     [rbp+60h+var_C8], rax
0x180050583  mov     [rsp+160h+cb], 0
0x18005058c  mov     [rsp+160h+var_110], 0
0x180050595  mov     [rsp+160h+var_108], 0
0x18005059e  xor     r13d, r13d
0x1800505a1  mov     [rbp+60h+pv], r13
0x1800505a5  xor     esi, esi
0x1800505a7  mov     [rsp+160h+var_F0], rsi
0x1800505ac  xor     r12d, r12d
0x1800505af  mov     [rbp+60h+var_E0], r12
0x1800505b3  xor     r14d, r14d
0x1800505b6  mov     [rsp+160h+var_E8], r14
0x1800505bb  xor     r15d, r15d
0x1800505be  mov     [rsp+160h+var_118], r15d
0x1800505c3  mov     [rsp+160h+var_11C], esi
0x1800505c7  mov     [rsp+160h+var_120], esi
0x1800505cb  mov     [rsp+160h+var_100], 1
0x1800505d3  lea     r8, [rsp+160h+var_100]
0x1800505d8  mov     rdx, rcx
0x1800505db  xor     ecx, ecx
0x1800505dd  call    cs:__imp_ServerGetApplicationType
0x1800505e3  mov     ebx, eax
0x1800505e5  test    eax, eax
0x1800505e7  js      loc_180050A36
0x1800505ed  lea     rdi, aSoftwareClasse_1; "SOFTWARE\\Classes\\Wow6432Node\\CLSID"
0x1800505f4  lea     rax, aSoftwareClasse; "SOFTWARE\\Classes\\CLSID"
0x1800505fb  cmp     [rsp+160h+var_100], 1
0x180050600  cmovnz  rdi, rax
0x180050604  mov     qword ptr [rbp+60h+pguid.Data1], rdi
0x180050608  lea     r8d, [r13+27h]; cchMax
0x18005060c  lea     rdx, [rbp+60h+sz]; lpsz
0x180050610  mov     rcx, [rbp+60h+rguid]; rguid
0x180050614  call    cs:__imp_StringFromGUID2
0x18005061a  lea     rcx, [rsp+160h+cb]; struct IRegNodeDispenser **
0x18005061f  call    ?GetRegNodeDispenser@@YAJPEAPEAUIRegNodeDispenser@@@Z; GetRegNodeDispenser(IRegNodeDispenser * *)
0x180050624  mov     ebx, eax
0x180050626  mov     r12, [rsp+160h+cb]
0x18005062b  test    eax, eax
0x18005062d  js      loc_180050A1D
0x180050633  mov     rax, [r12]
0x180050637  lea     rcx, [rsp+160h+var_110]
0x18005063c  mov     [rsp+160h+var_130], rcx
0x180050641  mov     dword ptr [rsp+160h+var_138], 20019h
0x180050649  lea     rcx, asc_18005D30C; "\\"
0x180050650  mov     [rsp+160h+var_140], rcx
0x180050655  mov     r9, rdi
0x180050658  mov     r8, 0FFFFFFFF80000002h
0x18005065f  lea     rdx, asc_1800681B8; "?"
0x180050666  mov     rcx, r12
0x180050669  mov     rax, [rax+18h]
0x18005066d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050672  mov     ebx, eax
0x180050674  test    eax, eax
0x180050676  js      loc_180050A1D
0x18005067c  mov     rax, [rsp+160h+var_110]
0x180050681  mov     rcx, [rax]
0x180050684  mov     rdi, [rcx+70h]
0x180050688  lea     rdx, aInprocserver32; "\\InprocServer32"
0x18005068f  lea     rcx, [rbp+60h+var_A8]
0x180050693  call    cs:__imp_??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x180050699  mov     rbx, rax
0x18005069c  lea     rdx, [rbp+60h+sz]
0x1800506a0  lea     rcx, [rsp+160h+cb]
0x1800506a5  call    cs:__imp_??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x1800506ab  nop
0x1800506ac  mov     r8, rbx
0x1800506af  mov     rdx, rax
0x1800506b2  lea     rcx, [rbp+60h+rguid]
0x1800506b6  call    cs:__imp_??H@YA?AVCString@@AEBV0@0@Z; operator+(CString const &,CString const &)
0x1800506bc  nop
0x1800506bd  lea     r8, aAssembly; "Assembly"
0x1800506c4  mov     rdx, [rax]
0x1800506c7  mov     rcx, [rsp+160h+var_110]
0x1800506cc  mov     rax, rdi
0x1800506cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800506d4  mov     ebx, eax
0x1800506d6  lea     rcx, [rbp+60h+rguid]
0x1800506da  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x1800506e0  nop
0x1800506e1  lea     rcx, [rsp+160h+cb]
0x1800506e6  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x1800506ec  nop
0x1800506ed  lea     rcx, [rbp+60h+var_A8]
0x1800506f1  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x1800506f7  test    ebx, ebx
0x1800506f9  js      loc_180050A1D
0x1800506ff  cmp     ebx, 1
0x180050702  jz      loc_180050A1D
0x180050708  mov     rcx, [rsp+160h+var_110]
0x18005070d  mov     rax, [rcx]
0x180050710  lea     rdx, [rsp+160h+var_11C]
0x180050715  mov     rax, [rax+40h]
0x180050719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005071e  mov     rcx, [rsp+160h+var_110]
0x180050723  mov     rax, [rcx]
0x180050726  lea     rdx, [rsp+160h+var_120]
0x18005072b  mov     rax, [rax+48h]
0x18005072f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050734  mov     eax, [rsp+160h+var_120]
0x180050738  lea     rcx, [rax+1]; unsigned __int64
0x18005073c  cmp     rcx, rax
0x18005073f  jb      loc_180050A18
0x180050745  mov     [rsp+160h+cb], rcx
0x18005074a  lea     r8, [rsp+160h+cb]; unsigned __int64 *
0x18005074f  lea     edx, [rsi+2]; unsigned __int64
0x180050752  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180050757  mov     ebx, eax
0x180050759  test    eax, eax
0x18005075b  js      loc_180050A1D
0x180050761  mov     rcx, [rsp+160h+cb]; cb
0x180050766  call    cs:__imp_CoTaskMemAlloc
0x18005076c  mov     r13, rax
0x18005076f  test    rax, rax
0x180050772  jnz     short loc_18005077E
0x180050774  mov     ebx, 8007000Eh
0x180050779  jmp     loc_180050A1D
0x18005077e  mov     rcx, [rsp+160h+var_110]
0x180050783  mov     rax, [rcx]
0x180050786  mov     r9, r13
0x180050789  mov     r8d, [rsp+160h+var_120]
0x18005078e  mov     edx, [rsp+160h+var_11C]
0x180050792  mov     rax, [rax+50h]
0x180050796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005079b  mov     ebx, eax
0x18005079d  test    eax, eax
0x18005079f  js      loc_180050A1D
0x1800507a5  mov     rax, [rbp+60h+var_C8]
0x1800507a9  mov     dword ptr [rax], 7
0x1800507af  lea     r8, [rbp+60h+pv]; unsigned __int16 **
0x1800507b3  lea     rdx, [rsp+160h+var_F0]; unsigned __int16 **
0x1800507b8  mov     rcx, [rbp+60h+var_C0]; struct _GUID *
0x1800507bc  call    ?ServerGetAppInfo@@YAJAEBU_GUID@@PEAPEAG1@Z; ServerGetAppInfo(_GUID const &,ushort * *,ushort * *)
0x1800507c1  mov     ebx, eax
0x1800507c3  mov     rsi, [rsp+160h+var_F0]
0x1800507c8  test    eax, eax
0x1800507ca  js      loc_180050A1D
0x1800507d0  test    rsi, rsi
0x1800507d3  jnz     loc_18005094C
0x1800507d9  mov     rax, [r12]
0x1800507dd  lea     rcx, [rsp+160h+var_108]
0x1800507e2  mov     [rsp+160h+var_130], rcx
0x1800507e7  mov     dword ptr [rsp+160h+var_138], 20019h
0x1800507ef  lea     rcx, asc_18005D30C; "\\"
0x1800507f6  mov     [rsp+160h+var_140], rcx
0x1800507fb  mov     r9, qword ptr [rbp+60h+pguid.Data1]
0x1800507ff  mov     r8, 0FFFFFFFF80000002h
0x180050806  lea     rdx, asc_1800681B8; "?"
0x18005080d  mov     rcx, r12
0x180050810  mov     rax, [rax+18h]
0x180050814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050819  mov     ebx, eax
0x18005081b  test    eax, eax
0x18005081d  js      loc_180050A1D
0x180050823  mov     rax, [rsp+160h+var_108]
0x180050828  mov     rcx, [rax]
0x18005082b  mov     rdi, [rcx+70h]
0x18005082f  lea     rdx, aInprocserver32; "\\InprocServer32"
0x180050836  lea     rcx, [rbp+60h+var_C8]
0x18005083a  call    cs:__imp_??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x180050840  mov     rbx, rax
0x180050843  lea     rdx, [rbp+60h+sz]
0x180050847  lea     rcx, [rbp+60h+var_C0]
0x18005084b  call    cs:__imp_??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x180050851  nop
0x180050852  mov     r8, rbx
0x180050855  mov     rdx, rax
0x180050858  lea     rcx, [rbp+60h+pguid]
0x18005085c  call    cs:__imp_??H@YA?AVCString@@AEBV0@0@Z; operator+(CString const &,CString const &)
0x180050862  nop
0x180050863  lea     r8, aCodebase; "CodeBase"
0x18005086a  mov     rdx, [rax]
0x18005086d  mov     rcx, [rsp+160h+var_108]
0x180050872  mov     rax, rdi
0x180050875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005087a  mov     ebx, eax
0x18005087c  lea     rcx, [rbp+60h+pguid]
0x180050880  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x180050886  nop
0x180050887  lea     rcx, [rbp+60h+var_C0]
0x18005088b  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x180050891  nop
0x180050892  lea     rcx, [rbp+60h+var_C8]
0x180050896  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18005089c  test    ebx, ebx
0x18005089e  js      loc_180050A1D
0x1800508a4  cmp     ebx, 1
0x1800508a7  jz      loc_18005094C
0x1800508ad  mov     rcx, [rsp+160h+var_108]
0x1800508b2  mov     rax, [rcx]
0x1800508b5  lea     rdx, [rsp+160h+var_11C]
0x1800508ba  mov     rax, [rax+40h]
0x1800508be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800508c3  mov     rcx, [rsp+160h+var_108]
0x1800508c8  mov     rdx, [rcx]
0x1800508cb  mov     rax, [rdx+48h]
0x1800508cf  lea     rdx, [rsp+160h+var_120]
0x1800508d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800508d9  mov     ecx, [rsp+160h+var_120]
0x1800508dd  shr     rcx, 1
0x1800508e0  add     rcx, 2
0x1800508e4  lea     eax, [rsi+2]
0x1800508e7  mul     rcx
0x1800508ea  lea     rcx, [rsi-1]
0x1800508ee  cmovb   rax, rcx
0x1800508f2  mov     rcx, rax; cb
0x1800508f5  call    cs:__imp_CoTaskMemAlloc
0x1800508fb  mov     rdi, rax
0x1800508fe  mov     [rbp+60h+var_E0], rax
0x180050902  test    rax, rax
0x180050905  jz      loc_180050A1D
0x18005090b  mov     rcx, [rsp+160h+var_108]
0x180050910  mov     rdx, [rcx]
0x180050913  mov     rax, [rdx+50h]
0x180050917  mov     r9, rdi
0x18005091a  mov     r8d, [rsp+160h+var_120]
0x18005091f  mov     edx, [rsp+160h+var_11C]
0x180050923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050928  mov     ebx, eax
0x18005092a  test    eax, eax
0x18005092c  js      loc_180050A1D
0x180050932  lea     rdx, [rsp+160h+var_F0]; unsigned __int16 **
0x180050937  mov     rcx, rdi; String2
0x18005093a  call    ?GetAppDirFromCodeBase@@YAHPEBGPEAPEAG@Z; GetAppDirFromCodeBase(ushort const *,ushort * *)
0x18005093f  mov     rsi, [rsp+160h+var_F0]
0x180050944  test    eax, eax
0x180050946  jz      loc_180050A1D
0x18005094c  lea     rax, [rsp+160h+var_118]
0x180050951  mov     [rsp+160h+var_138], rax
0x180050956  lea     rax, [rsp+160h+var_E8]
0x18005095b  mov     [rsp+160h+var_140], rax
0x180050960  mov     r9, r13
0x180050963  mov     r8, rsi
0x180050966  mov     rdx, [rbp+60h+pv]
0x18005096a  mov     ecx, [rsp+160h+var_100]
0x18005096e  call    ?GetModules@@YAJW4__MIDL___MIDL_itf_registrar_0000_0000_0001@@PEAG11PEAPEAPEAGPEAK@Z; GetModules(__MIDL___MIDL_itf_registrar_0000_0000_0001,ushort *,ushort *,ushort *,ushort * * *,ulong *)
0x180050973  mov     ebx, eax
0x180050975  mov     r14, [rsp+160h+var_E8]
0x18005097a  test    eax, eax
0x18005097c  js      loc_180050A11
0x180050982  mov     r8d, 7
0x180050988  mov     rdx, [r14]
0x18005098b  mov     rcx, [rbp+60h+var_B8]
0x18005098f  call    ?AddDllNameInternal@CAppExport@@AEAAJPEBGW4EFileType@@@Z; CAppExport::AddDllNameInternal(ushort const *,EFileType)
0x180050994  mov     ebx, eax
0x180050996  mov     r15d, [rsp+160h+var_118]
0x18005099b  test    eax, eax
0x18005099d  js      short loc_180050A1D
0x18005099f  cmp     eax, 1
0x1800509a2  jnz     short loc_1800509B2
0x1800509a4  xor     ebx, ebx
0x1800509a6  mov     rax, [r14]
0x1800509a9  mov     rcx, [rbp+60h+var_B0]
0x1800509ad  mov     [rcx], rax
0x1800509b0  jmp     short loc_180050A1D
0x1800509b2  mov     edi, 1
0x1800509b7  cmp     edi, r15d
0x1800509ba  jnb     short loc_1800509A6
0x1800509bc  xorps   xmm0, xmm0
0x1800509bf  movups  xmmword ptr [rbp+60h+pguid.Data1], xmm0
0x1800509c3  lea     rcx, [rbp+60h+pguid]; pguid
0x1800509c7  call    cs:__imp_CoCreateGuid
0x1800509cd  mov     ebx, eax
0x1800509cf  test    eax, eax
0x1800509d1  js      short loc_180050A1D
0x1800509d3  mov     edx, edi
0x1800509d5  mov     dword ptr [rsp+160h+var_128], 9
0x1800509dd  lea     rax, word_18005C890
0x1800509e4  mov     [rsp+160h+var_130], rax
0x1800509e9  mov     [rsp+160h+var_138], rax
0x1800509ee  mov     [rsp+160h+var_140], rax
0x1800509f3  mov     r9, rax
0x1800509f6  lea     r8, [rbp+60h+pguid]
0x1800509fa  mov     rdx, [r14+rdx*8]
0x1800509fe  mov     rcx, [rbp+60h+var_B8]
0x180050a02  call    ?AddClassInfo@CAppExport@@AEAAJPEBGAEAU_GUID@@0000W4EFileType@@@Z; CAppExport::AddClassInfo(ushort const *,_GUID &,ushort const *,ushort const *,ushort const *,ushort const *,EFileType)
0x180050a07  mov     ebx, eax
0x180050a09  test    eax, eax
0x180050a0b  js      short loc_180050A1D
0x180050a0d  inc     edi
0x180050a0f  jmp     short loc_1800509B7
  ... truncated ...
```
