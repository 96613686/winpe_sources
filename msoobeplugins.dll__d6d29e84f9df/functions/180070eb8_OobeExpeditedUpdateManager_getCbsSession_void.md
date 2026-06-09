# OobeExpeditedUpdateManager::_getCbsSession(void)

- ea: `0x180070eb8`
- end: `0x180071048`
- name: `?_getCbsSession@OobeExpeditedUpdateManager@@AEAA?AV?$com_ptr_t@UICbsSession9@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `400`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180066350`
- `0x18006aba0`

## callees

- `0x180003470`
- `0x18001ad08`
- `0x1800230b0`
- `0x180038ac4`
- `0x180063a88`
- `0x180070eb8`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180070f1b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180070f1b`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180070f68`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180070f68`

## string_xrefs

- `0x180070f2c`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x180070f79`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x180070fbd`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall OobeExpeditedUpdateManager::_getCbsSession(__int64 a1, __int64 *a2)
{
  __int64 *v3; // rbx
  HRESULT Instance; // eax
  HRESULT v5; // eax
  int v6; // eax
  __int64 v7; // rax
  __int64 v8; // rcx
  int ppv; // [rsp+20h] [rbp-40h]
  int ppva; // [rsp+20h] [rbp-40h]
  _QWORD v12[2]; // [rsp+40h] [rbp-20h] BYREF
  IUnknown *pProxy; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v12[0] = a2;
  v3 = (__int64 *)(a1 + 96);
  if ( !*(_QWORD *)(a1 + 96) )
  {
    pProxy = 0;
    wil::com_ptr_t<COOBEExpeditedUpdateUSOCallback,wil::err_returncode_policy>::reset(&pProxy);
    Instance = CoCreateInstance(
                 &GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed,
                 0,
                 0x15u,
                 &GUID_9c7e3cf3_4c97_4d36_bdeb_e3093c228c22,
                 (LPVOID *)&pProxy);
    if ( Instance < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x412,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
        (const char *)(unsigned int)Instance,
        ppv);
    v5 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 3u, 3u, 0, 0);
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x413,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
        (const char *)(unsigned int)v5,
        ppva);
    v6 = ((__int64 (__fastcall *)(IUnknown *, __int64, const wchar_t *, _QWORD))pProxy->lpVtbl[1].QueryInterface)(
           pProxy,
           1073741872,
           L"NDUP",
           0);
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x414,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
        (const char *)(unsigned int)v6,
        0);
    if ( pProxy )
    {
      v7 = *v3;
      *v3 = 0;
      v12[0] = v7;
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeZdpManager,wil::err_exception_policy>::operator=(v3, &pProxy);
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeZdpManager,wil::err_exception_policy>::operator=(&pProxy, v12);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(v12);
    }
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&pProxy);
  }
  v8 = *v3;
  *a2 = *v3;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  return a2;
}

```

## disassembly

```asm
0x180070eb8  mov     [rsp-8+arg_10], rbx
0x180070ebd  mov     [rsp-8+arg_18], rdi
0x180070ec2  push    rbp
0x180070ec3  mov     rbp, rsp
0x180070ec6  sub     rsp, 60h
0x180070eca  mov     rax, cs:__security_cookie
0x180070ed1  xor     rax, rsp
0x180070ed4  mov     [rbp+var_8], rax
0x180070ed8  mov     rdi, rdx
0x180070edb  mov     [rbp+var_20], rdx
0x180070edf  lea     rbx, [rcx+60h]
0x180070ee3  cmp     qword ptr [rbx], 0
0x180070ee7  jnz     loc_18007100F
0x180070eed  mov     [rbp+pProxy], 0
0x180070ef5  lea     rcx, [rbp+pProxy]
0x180070ef9  call    ?reset@?$com_ptr_t@VCOOBEExpeditedUpdateUSOCallback@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<COOBEExpeditedUpdateUSOCallback,wil::err_returncode_policy>::reset(void)
0x180070efe  lea     rax, [rbp+pProxy]
0x180070f02  mov     [rsp+60h+ppv], rax; int
0x180070f07  lea     r9, _GUID_9c7e3cf3_4c97_4d36_bdeb_e3093c228c22; riid
0x180070f0e  xor     edx, edx; pUnkOuter
0x180070f10  lea     r8d, [rdx+15h]; dwClsContext
0x180070f14  lea     rcx, _GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed; rclsid
0x180070f1b  call    cs:__imp_CoCreateInstance
0x180070f21  mov     rcx, [rbp+8]; this
0x180070f25  test    eax, eax
0x180070f27  jns     short loc_180070F3D
0x180070f29  mov     r9d, eax; char *
0x180070f2c  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x180070f33  mov     edx, 412h; void *
0x180070f38  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180070f3d  mov     [rsp+60h+dwCapabilities], 0; dwCapabilities
0x180070f45  mov     [rsp+60h+pAuthInfo], 0; pAuthInfo
0x180070f4e  mov     eax, 3
0x180070f53  mov     [rsp+60h+dwImpLevel], eax; dwImpLevel
0x180070f57  mov     dword ptr [rsp+60h+ppv], eax; int
0x180070f5b  xor     r9d, r9d; pServerPrincName
0x180070f5e  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180070f61  mov     r8d, edx; dwAuthzSvc
0x180070f64  mov     rcx, [rbp+pProxy]; pProxy
0x180070f68  call    cs:__imp_CoSetProxyBlanket
0x180070f6e  mov     rcx, [rbp+8]; this
0x180070f72  test    eax, eax
0x180070f74  jns     short loc_180070F8A
0x180070f76  mov     r9d, eax; char *
0x180070f79  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x180070f80  mov     edx, 413h; void *
0x180070f85  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180070f8a  mov     rcx, [rbp+pProxy]
0x180070f8e  mov     rax, [rcx]
0x180070f91  mov     [rsp+60h+ppv], 0; int
0x180070f9a  xor     r9d, r9d
0x180070f9d  lea     r8, aNdup; "NDUP"
0x180070fa4  mov     edx, 40000030h
0x180070fa9  mov     rax, [rax+18h]
0x180070fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070fb2  mov     rcx, [rbp+8]; this
0x180070fb6  test    eax, eax
0x180070fb8  jns     short loc_180070FCE
0x180070fba  mov     r9d, eax; char *
0x180070fbd  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x180070fc4  mov     edx, 414h; void *
0x180070fc9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180070fce  cmp     [rbp+pProxy], 0
0x180070fd3  jz      short loc_180071006
0x180070fd5  mov     rax, [rbx]
0x180070fd8  mov     qword ptr [rbx], 0
0x180070fdf  mov     [rbp+var_20], rax
0x180070fe3  lea     rdx, [rbp+pProxy]
0x180070fe7  mov     rcx, rbx
0x180070fea  call    ??4?$com_ptr_t@UIOobeZdpManager@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<CloudExperienceHostAPI::IOobeZdpManager,wil::err_exception_policy>::operator=(wil::com_ptr_t<CloudExperienceHostAPI::IOobeZdpManager,wil::err_exception_policy> &&)
0x180070fef  lea     rdx, [rbp+var_20]
0x180070ff3  lea     rcx, [rbp+pProxy]
0x180070ff7  call    ??4?$com_ptr_t@UIOobeZdpManager@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<CloudExperienceHostAPI::IOobeZdpManager,wil::err_exception_policy>::operator=(wil::com_ptr_t<CloudExperienceHostAPI::IOobeZdpManager,wil::err_exception_policy> &&)
0x180070ffc  lea     rcx, [rbp+var_20]
0x180071000  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180071005  nop
0x180071006  lea     rcx, [rbp+pProxy]
0x18007100a  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007100f  mov     rcx, [rbx]
0x180071012  mov     [rdi], rcx
0x180071015  test    rcx, rcx
0x180071018  jz      short loc_180071027
0x18007101a  mov     rdx, [rcx]
0x18007101d  mov     rax, [rdx+8]
0x180071021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071026  nop
0x180071027  mov     rax, rdi
0x18007102a  mov     rcx, [rbp+var_8]
0x18007102e  xor     rcx, rsp; StackCookie
0x180071031  call    __security_check_cookie
0x180071036  lea     r11, [rsp+60h+var_s0]
0x18007103b  mov     rbx, [r11+20h]
0x18007103f  mov     rdi, [r11+28h]
0x180071043  mov     rsp, r11
0x180071046  pop     rbp
0x180071047  retn
```
