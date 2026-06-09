# CWin32NetCli::GetNTObject(CInstance *,long)

- ea: `0x1800bb97c`
- end: `0x1800bbd90`
- name: `?GetNTObject@CWin32NetCli@@AEAAJPEAVCInstance@@J@Z`
- size: `1044`
- prototype: `int(CWin32NetCli *__hidden this, struct CInstance *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800bbda0`

## callees

- `0x180021d4c`
- `0x180063df8`
- `0x180065ab0`
- `0x18007c118`
- `0x1800bb914`
- `0x1800bb97c`
- `0x1800fc980`
- `0x180110010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bba2f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bba2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbb73`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800bb9b4`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800bb9c0`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800bb9cc`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800bb9d8`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800bb9e4`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800bb9b4`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800bb9c0`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800bb9cc`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800bb9d8`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800bb9e4`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800bb9fa`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800bb9fa`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800bbc41`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800bbc41`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800bbbe6`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800bbbe6`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x1800bb9a8`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x1800bb9a8`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800bba86`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800bbd6d`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800bba86`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800bbd6d`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800bbb8d`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800bbb9f`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800bbbb3`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800bbb8d`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800bbb9f`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800bbbb3`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x1800bbbc6`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x1800bbbd7`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x1800bbbc6`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x1800bbbd7`
- `framedynos!?OpenLocalMachineKeyAndReadValue@CRegistry@@QEAAJPEBG0AEAVCHString@@@Z` at `0x1800bbc2d`
- `framedynos!?OpenLocalMachineKeyAndReadValue@CRegistry@@QEAAJPEBG0AEAVCHString@@@Z` at `0x1800bbc2d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bba4b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bba57`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bba63`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bba6f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bba7b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbbf1`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbbfc`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbc07`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbc12`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbc50`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbc84`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbd32`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbd3e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbd4a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbd56`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbd62`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bba4b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bba57`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bba63`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bba6f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bba7b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbbf1`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbbfc`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbc07`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbc12`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbc50`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbc84`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbd32`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbd3e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbd4a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbd56`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bbd62`

## string_xrefs

- `0x1800bbba8`: `SYSTEM\CurrentControlSet\Services\`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall CWin32NetCli::GetNTObject(CWin32NetCli *this, struct CInstance *a2)
{
  HRESULT v3; // ebx
  LPVOID v5; // rbx
  int v6; // edi
  int v7; // eax
  CHString *v8; // rdi
  CHString *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  CWin32NetCli *v12; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v16[8]; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v17; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v18; // [rsp+58h] [rbp-A8h] BYREF
  int v19; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[8]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v21[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v22[8]; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 *v23[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v24[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v25[8]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v26[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v27[8]; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID v28; // [rsp+B0h] [rbp-50h]
  _BYTE v29[24]; // [rsp+B8h] [rbp-48h] BYREF
  GUID v30; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v31[608]; // [rsp+E0h] [rbp-20h] BYREF

  CRegistry::CRegistry((CRegistry *)v31);
  CHString::CHString((CHString *)v22);
  CHString::CHString((CHString *)&v18);
  CHString::CHString((CHString *)v21);
  CHString::CHString((CHString *)&v17);
  CHString::CHString((CHString *)v16);
  if ( CInstance::GetCHString(a2, L"Name", (struct CHString *)v16) )
  {
    ppv = 0;
    v3 = CoCreateInstance(&CLSID_CNetCfg, 0, 0x15u, &IID_INetCfg, &ppv);
    if ( v3 < 0 || (v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0), v3 < 0) )
    {
      _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>((__int64 *)&ppv);
      CHString::~CHString((CHString *)v16);
      CHString::~CHString((CHString *)&v17);
      CHString::~CHString((CHString *)v21);
      CHString::~CHString((CHString *)&v18);
      CHString::~CHString((CHString *)v22);
      CRegistry::~CRegistry((CRegistry *)v31);
      return (unsigned int)v3;
    }
    v5 = ppv;
    v28 = ppv;
    v15 = 0;
    v30 = GUID_DEVCLASS_NETCLIENT;
    v6 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, &v30, &v15);
    if ( v6 >= 0 )
    {
      while ( 1 )
      {
        v19 = 1;
        v14 = 0;
        v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v15 + 24LL))(v15, 1, &v14, &v19);
        v6 = v7;
        if ( v7 < 0 )
          break;
        if ( v7 == 1 )
        {
          _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(&v14);
          _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(&v15);
           INetCfg::`vcall'{32,{flat}}(v5);
          v6 = -2147217406;
          goto LABEL_17;
        }
        v23[0] = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 **))(*(_QWORD *)v14 + 88LL))(v14, v23);
        if ( v6 < 0 )
          break;
        MakeGuard<void (*)(void *),RefHolder<unsigned short *>>(v29, CoTaskMemFree, v23);
        CHString::CHString((CHString *)v20, v23[0]);
        v8 = CHString::CHString((CHString *)v27, L"\\NetworkProvider");
        v9 = CHString::CHString((CHString *)v26, L"SYSTEM\\CurrentControlSet\\Services\\");
        v10 = operator+(v25, v9, v20);
        v11 = operator+(v24, v10, v8);
        CHString::operator=(&v17, v11);
        CHString::~CHString((CHString *)v24);
        CHString::~CHString((CHString *)v25);
        CHString::~CHString((CHString *)v26);
        CHString::~CHString((CHString *)v27);
        if ( !CRegistry::OpenLocalMachineKeyAndReadValue((CRegistry *)v31, v17, L"Name", (struct CHString *)&v18)
          && !CHString::CompareNoCase((CHString *)v16, v18) )
        {
          v6 = CWin32NetCli::FillNTInstance(v12, a2, (struct CHString *)v20);
          CHString::~CHString((CHString *)v20);
          ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>::~ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>((__int64)v29);
          _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(&v14);
          _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(&v15);
           INetCfg::`vcall'{32,{flat}}(v5);
          goto LABEL_17;
        }
        CHString::~CHString((CHString *)v20);
        ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>::~ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>((__int64)v29);
        _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(&v14);
      }
      _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(&v14);
      _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(&v15);
       INetCfg::`vcall'{32,{flat}}(v5);
    }
    else
    {
      _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(&v15);
       INetCfg::`vcall'{32,{flat}}(v5);
    }
LABEL_17:
    _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>((__int64 *)&ppv);
  }
  else
  {
    v6 = -2147217400;
  }
  CHString::~CHString((CHString *)v16);
  CHString::~CHString((CHString *)&v17);
  CHString::~CHString((CHString *)v21);
  CHString::~CHString((CHString *)&v18);
  CHString::~CHString((CHString *)v22);
  CRegistry::~CRegistry((CRegistry *)v31);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800bb97c  push    rbp
0x1800bb97e  push    rbx
0x1800bb97f  push    rsi
0x1800bb980  push    rdi
0x1800bb981  lea     rbp, [rsp-258h]
0x1800bb989  sub     rsp, 358h
0x1800bb990  mov     rax, cs:__security_cookie
0x1800bb997  xor     rax, rsp
0x1800bb99a  mov     [rbp+270h+var_30], rax
0x1800bb9a1  mov     rsi, rdx
0x1800bb9a4  lea     rcx, [rbp+270h+var_290]
0x1800bb9a8  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x1800bb9ae  nop
0x1800bb9af  lea     rcx, [rsp+370h+var_2F8]
0x1800bb9b4  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800bb9ba  nop
0x1800bb9bb  lea     rcx, [rsp+370h+var_318]
0x1800bb9c0  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800bb9c6  nop
0x1800bb9c7  lea     rcx, [rsp+370h+var_300]
0x1800bb9cc  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800bb9d2  nop
0x1800bb9d3  lea     rcx, [rsp+370h+var_320]
0x1800bb9d8  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800bb9de  nop
0x1800bb9df  lea     rcx, [rsp+370h+var_328]
0x1800bb9e4  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800bb9ea  nop
0x1800bb9eb  lea     r8, [rsp+370h+var_328]
0x1800bb9f0  lea     rdx, aName; "Name"
0x1800bb9f7  mov     rcx, rsi
0x1800bb9fa  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x1800bba00  test    al, al
0x1800bba02  jz      loc_1800BBD28
0x1800bba08  mov     [rsp+370h+var_340], 0
0x1800bba11  lea     rax, [rsp+370h+var_340]
0x1800bba16  mov     [rsp+370h+ppv], rax; ppv
0x1800bba1b  lea     r9, IID_INetCfg; riid
0x1800bba22  xor     edx, edx; pUnkOuter
0x1800bba24  lea     r8d, [rdx+15h]; dwClsContext
0x1800bba28  lea     rcx, CLSID_CNetCfg; rclsid
0x1800bba2f  call    cs:__imp_CoCreateInstance
0x1800bba35  mov     ebx, eax
0x1800bba37  test    eax, eax
0x1800bba39  jns     short loc_1800BBA93
0x1800bba3b  lea     rcx, [rsp+370h+var_340]
0x1800bba40  call    ??1?$_com_ptr_t@V?$_com_IIID@UIWbemObjectSink@@$1?_GUID_7c857801_7381_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(void)
0x1800bba45  nop
0x1800bba46  lea     rcx, [rsp+370h+var_328]
0x1800bba4b  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800bba51  nop
0x1800bba52  lea     rcx, [rsp+370h+var_320]
0x1800bba57  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800bba5d  nop
0x1800bba5e  lea     rcx, [rsp+370h+var_300]
0x1800bba63  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800bba69  nop
0x1800bba6a  lea     rcx, [rsp+370h+var_318]
0x1800bba6f  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800bba75  nop
0x1800bba76  lea     rcx, [rsp+370h+var_2F8]
0x1800bba7b  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800bba81  nop
0x1800bba82  lea     rcx, [rbp+270h+var_290]
0x1800bba86  call    cs:__imp_??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x1800bba8c  mov     eax, ebx
0x1800bba8e  jmp     loc_1800BBD75
0x1800bba93  mov     rcx, [rsp+370h+var_340]
0x1800bba98  mov     rax, [rcx]
0x1800bba9b  xor     edx, edx
0x1800bba9d  mov     rax, [rax+18h]
0x1800bbaa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbaa6  mov     ebx, eax
0x1800bbaa8  test    eax, eax
0x1800bbaaa  jns     short loc_1800BBAAE
0x1800bbaac  jmp     short loc_1800BBA3B
0x1800bbaae  mov     rbx, [rsp+370h+var_340]
0x1800bbab3  mov     [rbp+270h+var_2C0], rbx
0x1800bbab7  mov     [rsp+370h+var_330], 0
0x1800bbac0  movups  xmm0, xmmword ptr cs:GUID_DEVCLASS_NETCLIENT.Data1
0x1800bbac7  movdqu  [rbp+270h+var_2A0], xmm0
0x1800bbacc  mov     rcx, [rsp+370h+var_340]
0x1800bbad1  mov     rax, [rcx]
0x1800bbad4  lea     r8, [rsp+370h+var_330]
0x1800bbad9  lea     rdx, [rbp+270h+var_2A0]
0x1800bbadd  mov     rax, [rax+38h]
0x1800bbae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbae6  mov     edi, eax
0x1800bbae8  test    eax, eax
0x1800bbaea  jns     short loc_1800BBB05
0x1800bbaec  lea     rcx, [rsp+370h+var_330]
0x1800bbaf1  call    ??1?$_com_ptr_t@V?$_com_IIID@UIWbemObjectSink@@$1?_GUID_7c857801_7381_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(void)
0x1800bbaf6  nop
0x1800bbaf7  mov     rcx, rbx
0x1800bbafa  call    ??_9INetCfg@@$BCA@AA; [thunk]: INetCfg::`vcall'{32,{flat}}
0x1800bbaff  nop
0x1800bbb00  jmp     loc_1800BBD1C
0x1800bbb05  mov     [rsp+370h+var_310], 1
0x1800bbb0d  mov     [rsp+370h+var_338], 0
0x1800bbb16  mov     rcx, [rsp+370h+var_330]
0x1800bbb1b  mov     rax, [rcx]
0x1800bbb1e  lea     r9, [rsp+370h+var_310]
0x1800bbb23  lea     r8, [rsp+370h+var_338]
0x1800bbb28  mov     edx, [rsp+370h+var_310]
0x1800bbb2c  mov     rax, [rax+18h]
0x1800bbb30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbb35  mov     edi, eax
0x1800bbb37  test    eax, eax
0x1800bbb39  js      loc_1800BBCFD
0x1800bbb3f  cmp     eax, 1
0x1800bbb42  jz      loc_1800BBCD7
0x1800bbb48  mov     [rbp+270h+var_2F0], 0
0x1800bbb50  mov     rcx, [rsp+370h+var_338]
0x1800bbb55  mov     rax, [rcx]
0x1800bbb58  lea     rdx, [rbp+270h+var_2F0]
0x1800bbb5c  mov     rax, [rax+58h]
0x1800bbb60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbb65  mov     edi, eax
0x1800bbb67  test    eax, eax
0x1800bbb69  js      loc_1800BBCB6
0x1800bbb6f  lea     r8, [rbp+270h+var_2F0]
0x1800bbb73  mov     rdx, cs:__imp_CoTaskMemFree
0x1800bbb7a  lea     rcx, [rbp+270h+var_2B8]
0x1800bbb7e  call    ??$MakeGuard@P6AXPEAX@ZV?$RefHolder@PEAG@@@@YA?AV?$ScopeGuardImpl1@P6AXPEAX@ZV?$RefHolder@PEAG@@@@P6AXPEAX@ZV?$RefHolder@PEAG@@@Z; MakeGuard<void (*)(void *),RefHolder<ushort *>>(void (*)(void *),RefHolder<ushort *>)
0x1800bbb83  nop
0x1800bbb84  mov     rdx, [rbp+270h+var_2F0]
0x1800bbb88  lea     rcx, [rsp+370h+var_308]
0x1800bbb8d  call    cs:__imp_??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x1800bbb93  nop
0x1800bbb94  lea     rdx, aNetworkprovide; "\\NetworkProvider"
0x1800bbb9b  lea     rcx, [rbp+270h+var_2C8]
0x1800bbb9f  call    cs:__imp_??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x1800bbba5  mov     rdi, rax
0x1800bbba8  lea     rdx, aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Services\\"
0x1800bbbaf  lea     rcx, [rbp+270h+var_2D0]
0x1800bbbb3  call    cs:__imp_??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x1800bbbb9  nop
0x1800bbbba  lea     r8, [rsp+370h+var_308]
0x1800bbbbf  mov     rdx, rax
0x1800bbbc2  lea     rcx, [rbp+270h+var_2D8]
0x1800bbbc6  call    cs:__imp_??H@YA?AVCHString@@AEBV0@0@Z; operator+(CHString const &,CHString const &)
0x1800bbbcc  nop
0x1800bbbcd  mov     r8, rdi
0x1800bbbd0  mov     rdx, rax
0x1800bbbd3  lea     rcx, [rbp+270h+var_2E0]
0x1800bbbd7  call    cs:__imp_??H@YA?AVCHString@@AEBV0@0@Z; operator+(CHString const &,CHString const &)
0x1800bbbdd  nop
0x1800bbbde  mov     rdx, rax
0x1800bbbe1  lea     rcx, [rsp+370h+var_320]
0x1800bbbe6  call    cs:__imp_??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x1800bbbec  nop
0x1800bbbed  lea     rcx, [rbp+270h+var_2E0]
0x1800bbbf1  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800bbbf7  nop
0x1800bbbf8  lea     rcx, [rbp+270h+var_2D8]
0x1800bbbfc  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800bbc02  nop
0x1800bbc03  lea     rcx, [rbp+270h+var_2D0]
0x1800bbc07  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800bbc0d  nop
0x1800bbc0e  lea     rcx, [rbp+270h+var_2C8]
0x1800bbc12  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800bbc18  lea     r9, [rsp+370h+var_318]
0x1800bbc1d  lea     r8, aName; "Name"
0x1800bbc24  mov     rdx, [rsp+370h+var_320]
0x1800bbc29  lea     rcx, [rbp+270h+var_290]
0x1800bbc2d  call    cs:__imp_?OpenLocalMachineKeyAndReadValue@CRegistry@@QEAAJPEBG0AEAVCHString@@@Z; CRegistry::OpenLocalMachineKeyAndReadValue(ushort const *,ushort const *,CHString &)
0x1800bbc33  test    eax, eax
0x1800bbc35  jnz     short loc_1800BBC4B
0x1800bbc37  mov     rdx, [rsp+370h+var_318]
0x1800bbc3c  lea     rcx, [rsp+370h+var_328]
0x1800bbc41  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x1800bbc47  test    eax, eax
0x1800bbc49  jz      short loc_1800BBC70
0x1800bbc4b  lea     rcx, [rsp+370h+var_308]
0x1800bbc50  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800bbc56  nop
0x1800bbc57  lea     rcx, [rbp+270h+var_2B8]
0x1800bbc5b  call    ??1?$ScopeGuardImpl1@P6AXPEAE@ZV?$RefHolder@PEAE@@@@QEAA@XZ; ScopeGuardImpl1<void (*)(uchar *),RefHolder<uchar *>>::~ScopeGuardImpl1<void (*)(uchar *),RefHolder<uchar *>>(void)
0x1800bbc60  nop
0x1800bbc61  lea     rcx, [rsp+370h+var_338]
0x1800bbc66  call    ??1?$_com_ptr_t@V?$_com_IIID@UIWbemObjectSink@@$1?_GUID_7c857801_7381_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(void)
0x1800bbc6b  jmp     loc_1800BBB05
0x1800bbc70  lea     r8, [rsp+370h+var_308]; struct CHString *
0x1800bbc75  mov     rdx, rsi; struct CInstance *
0x1800bbc78  call    ?FillNTInstance@CWin32NetCli@@AEAAJPEAVCInstance@@AEAVCHString@@@Z; CWin32NetCli::FillNTInstance(CInstance *,CHString &)
0x1800bbc7d  mov     edi, eax
0x1800bbc7f  lea     rcx, [rsp+370h+var_308]
0x1800bbc84  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800bbc8a  nop
0x1800bbc8b  lea     rcx, [rbp+270h+var_2B8]
0x1800bbc8f  call    ??1?$ScopeGuardImpl1@P6AXPEAE@ZV?$RefHolder@PEAE@@@@QEAA@XZ; ScopeGuardImpl1<void (*)(uchar *),RefHolder<uchar *>>::~ScopeGuardImpl1<void (*)(uchar *),RefHolder<uchar *>>(void)
0x1800bbc94  nop
0x1800bbc95  lea     rcx, [rsp+370h+var_338]
0x1800bbc9a  call    ??1?$_com_ptr_t@V?$_com_IIID@UIWbemObjectSink@@$1?_GUID_7c857801_7381_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(void)
0x1800bbc9f  nop
0x1800bbca0  lea     rcx, [rsp+370h+var_330]
0x1800bbca5  call    ??1?$_com_ptr_t@V?$_com_IIID@UIWbemObjectSink@@$1?_GUID_7c857801_7381_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(void)
0x1800bbcaa  nop
0x1800bbcab  mov     rcx, rbx
0x1800bbcae  call    ??_9INetCfg@@$BCA@AA; [thunk]: INetCfg::`vcall'{32,{flat}}
0x1800bbcb3  nop
0x1800bbcb4  jmp     short loc_1800BBD1C
0x1800bbcb6  lea     rcx, [rsp+370h+var_338]
0x1800bbcbb  call    ??1?$_com_ptr_t@V?$_com_IIID@UIWbemObjectSink@@$1?_GUID_7c857801_7381_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(void)
0x1800bbcc0  nop
0x1800bbcc1  lea     rcx, [rsp+370h+var_330]
0x1800bbcc6  call    ??1?$_com_ptr_t@V?$_com_IIID@UIWbemObjectSink@@$1?_GUID_7c857801_7381_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(void)
0x1800bbccb  nop
0x1800bbccc  mov     rcx, rbx
0x1800bbccf  call    ??_9INetCfg@@$BCA@AA; [thunk]: INetCfg::`vcall'{32,{flat}}
0x1800bbcd4  nop
0x1800bbcd5  jmp     short loc_1800BBD1C
0x1800bbcd7  lea     rcx, [rsp+370h+var_338]
0x1800bbcdc  call    ??1?$_com_ptr_t@V?$_com_IIID@UIWbemObjectSink@@$1?_GUID_7c857801_7381_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(void)
0x1800bbce1  nop
0x1800bbce2  lea     rcx, [rsp+370h+var_330]
0x1800bbce7  call    ??1?$_com_ptr_t@V?$_com_IIID@UIWbemObjectSink@@$1?_GUID_7c857801_7381_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(void)
0x1800bbcec  nop
0x1800bbced  mov     rcx, rbx
0x1800bbcf0  call    ??_9INetCfg@@$BCA@AA; [thunk]: INetCfg::`vcall'{32,{flat}}
0x1800bbcf5  nop
0x1800bbcf6  mov     edi, 80041002h
0x1800bbcfb  jmp     short loc_1800BBD1C
0x1800bbcfd  lea     rcx, [rsp+370h+var_338]
0x1800bbd02  call    ??1?$_com_ptr_t@V?$_com_IIID@UIWbemObjectSink@@$1?_GUID_7c857801_7381_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(void)
0x1800bbd07  nop
0x1800bbd08  lea     rcx, [rsp+370h+var_330]
0x1800bbd0d  call    ??1?$_com_ptr_t@V?$_com_IIID@UIWbemObjectSink@@$1?_GUID_7c857801_7381_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(void)
0x1800bbd12  nop
0x1800bbd13  mov     rcx, rbx
0x1800bbd16  call    ??_9INetCfg@@$BCA@AA; [thunk]: INetCfg::`vcall'{32,{flat}}
0x1800bbd1b  nop
0x1800bbd1c  lea     rcx, [rsp+370h+var_340]
0x1800bbd21  call    ??1?$_com_ptr_t@V?$_com_IIID@UIWbemObjectSink@@$1?_GUID_7c857801_7381_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>::~_com_ptr_t<_com_IIID<IWbemObjectSink,&__s_GUID const _GUID_7c857801_7381_11cf_884d_00aa004b2e24>>(void)
0x1800bbd26  jmp     short loc_1800BBD2D
0x1800bbd28  mov     edi, 80041008h
0x1800bbd2d  lea     rcx, [rsp+370h+var_328]
0x1800bbd32  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800bbd38  nop
0x1800bbd39  lea     rcx, [rsp+370h+var_320]
0x1800bbd3e  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800bbd44  nop
0x1800bbd45  lea     rcx, [rsp+370h+var_300]
0x1800bbd4a  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800bbd50  nop
0x1800bbd51  lea     rcx, [rsp+370h+var_318]
0x1800bbd56  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800bbd5c  nop
0x1800bbd5d  lea     rcx, [rsp+370h+var_2F8]
0x1800bbd62  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800bbd68  nop
0x1800bbd69  lea     rcx, [rbp+270h+var_290]
0x1800bbd6d  call    cs:__imp_??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x1800bbd73  mov     eax, edi
0x1800bbd75  mov     rcx, [rbp+270h+var_30]
0x1800bbd7c  xor     rcx, rsp; StackCookie
0x1800bbd7f  call    __security_check_cookie
0x1800bbd84  add     rsp, 358h
0x1800bbd8b  pop     rdi
0x1800bbd8c  pop     rsi
0x1800bbd8d  pop     rbx
0x1800bbd8e  pop     rbp
0x1800bbd8f  retn
```
