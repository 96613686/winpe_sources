# OobeDevicePairingElevatedManager::CreateElevatedHIDPairingPlugin(_GUID const &,void * *,int *)

- ea: `0x1800589e0`
- end: `0x180058be0`
- name: `?CreateElevatedHIDPairingPlugin@OobeDevicePairingElevatedManager@@UEAAJAEBU_GUID@@PEAPEAXPEAH@Z`
- size: `512`
- prototype: `__int64 __fastcall(OobeDevicePairingElevatedManager *__hidden this, const struct _GUID *, void **, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001ad08`
- `0x18003e478`
- `0x180058550`
- `0x180058700`
- `0x1800589e0`
- `0x1800b3c08`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180058a2b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180058a2b`

## string_xrefs

- `0x180058a3d`: `shell\oobe\machine\plugins\adapters\com\oobedevicepairing.cpp`
- `0x180058a6e`: `shell\oobe\machine\plugins\adapters\com\oobedevicepairing.cpp`
- `0x180058aa3`: `shell\oobe\machine\plugins\adapters\com\oobedevicepairing.cpp`
- `0x180058ade`: `shell\oobe\machine\plugins\adapters\com\oobedevicepairing.cpp`
- `0x180058b0f`: `shell\oobe\machine\plugins\adapters\com\oobedevicepairing.cpp`
- `0x180058b52`: `shell\oobe\machine\plugins\adapters\com\oobedevicepairing.cpp`
- `0x180058b85`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OobeDevicePairingElevatedManager::CreateElevatedHIDPairingPlugin(
        OobeDevicePairingElevatedManager *this,
        const struct _GUID *a2,
        void **a3,
        int *a4)
{
  HRESULT v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // eax
  int v14; // eax
  int v15; // eax
  const char *v16; // r9
  __int64 result; // rax
  int v18; // [rsp+20h] [rbp-38h]
  __int64 v19; // [rsp+30h] [rbp-28h] BYREF
  __int64 v20; // [rsp+38h] [rbp-20h] BYREF
  _QWORD v21[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v23; // [rsp+70h] [rbp+18h] BYREF
  LPVOID v24; // [rsp+78h] [rbp+20h] BYREF

  *a4 = 0;
  *a3 = 0;
  v24 = 0;
  v7 = CoCreateInstance(&CLSID_HidPairingPlugin, 0, 1u, &GUID_f5858211_90ae_4b01_bb4c_43a5efd959b6, &v24);
  try
  {
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobedevicepairing.cpp",
        (const char *)(unsigned int)v7,
        v18);
    v20 = 0;
    v8 = Microsoft::WRL::Details::MakeAndInitialize<DevicePairingImplOOBEHost,IOOBEHost,>(&v20);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x3D,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobedevicepairing.cpp",
        (const char *)(unsigned int)v8,
        v18);
    v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)v24 + 40LL))(v24, 0, v20);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x3E,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobedevicepairing.cpp",
        (const char *)(unsigned int)v9,
        v18);
    v23 = 0;
    v10 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v24 + 24LL))(v24, &v23);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobedevicepairing.cpp",
        (const char *)(unsigned int)v10,
        v18);
    v19 = 0;
    v13 = COOBESettingsStore_CreateInstance(retaddr, v11, v12, &v19);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobedevicepairing.cpp",
        (const char *)(unsigned int)v13,
        v18);
    wil::com_ptr_t<IOOBEPlugin,wil::err_exception_policy>::query<IOOBESettingsParser>(&v24, v21);
    v14 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v21[0] + 24LL))(v21[0], v19);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobedevicepairing.cpp",
        (const char *)(unsigned int)v14,
        v18);
    v15 = (**(__int64 (__fastcall ***)(LPVOID, const struct _GUID *, void **))v24)(v24, a2, a3);
    if ( v15 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v15,
        v18);
    *a4 = v23;
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(v21);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v19);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v20);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v24);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4D,
                           (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobedevicepairing.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x1800589e0  mov     r11, rsp
0x1800589e3  mov     [r11+8], rbx
0x1800589e7  mov     [r11+10h], rsi
0x1800589eb  push    rdi
0x1800589ec  sub     rsp, 50h
0x1800589f0  mov     rbx, r9
0x1800589f3  mov     rdi, r8
0x1800589f6  mov     rsi, rdx
0x1800589f9  mov     dword ptr [r9], 0
0x180058a00  mov     qword ptr [r8], 0
0x180058a07  mov     qword ptr [r11+20h], 0
0x180058a0f  lea     rax, [r11+20h]
0x180058a13  mov     [r11-38h], rax
0x180058a17  lea     r9, _GUID_f5858211_90ae_4b01_bb4c_43a5efd959b6; riid
0x180058a1e  xor     edx, edx; pUnkOuter
0x180058a20  lea     r8d, [rdx+1]; dwClsContext
0x180058a24  lea     rcx, CLSID_HidPairingPlugin; rclsid
0x180058a2b  call    cs:__imp_CoCreateInstance
0x180058a31  mov     rcx, [rsp+58h]; this
0x180058a36  test    eax, eax
0x180058a38  jns     short loc_180058A4F
0x180058a3a  mov     r9d, eax; char *
0x180058a3d  lea     r8, aShellOobeMachi_26; "shell\\oobe\\machine\\plugins\\adapters"...
0x180058a44  mov     edx, 3Ah ; ':'; void *
0x180058a49  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180058a4f  mov     [rsp+58h+var_20], 0
0x180058a58  lea     rcx, [rsp+58h+var_20]
0x180058a5d  call    ??$MakeAndInitialize@VDevicePairingImplOOBEHost@@UIOOBEHost@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIOOBEHost@@@Z; Microsoft::WRL::Details::MakeAndInitialize<DevicePairingImplOOBEHost,IOOBEHost,>(IOOBEHost * *)
0x180058a62  mov     rcx, [rsp+58h]; this
0x180058a67  test    eax, eax
0x180058a69  jns     short loc_180058A7F
0x180058a6b  mov     r9d, eax; char *
0x180058a6e  lea     r8, aShellOobeMachi_26; "shell\\oobe\\machine\\plugins\\adapters"...
0x180058a75  mov     edx, 3Dh ; '='; void *
0x180058a7a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180058a7f  mov     rcx, [rsp+58h+arg_18]
0x180058a84  mov     rax, [rcx]
0x180058a87  mov     r8, [rsp+58h+var_20]
0x180058a8c  xor     edx, edx
0x180058a8e  mov     rax, [rax+28h]
0x180058a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058a97  mov     rcx, [rsp+58h]; this
0x180058a9c  test    eax, eax
0x180058a9e  jns     short loc_180058AB4
0x180058aa0  mov     r9d, eax; char *
0x180058aa3  lea     r8, aShellOobeMachi_26; "shell\\oobe\\machine\\plugins\\adapters"...
0x180058aaa  mov     edx, 3Eh ; '>'; void *
0x180058aaf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180058ab4  mov     [rsp+58h+arg_10], 0
0x180058abc  mov     rcx, [rsp+58h+arg_18]
0x180058ac1  mov     rax, [rcx]
0x180058ac4  lea     rdx, [rsp+58h+arg_10]
0x180058ac9  mov     rax, [rax+18h]
0x180058acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058ad2  mov     rcx, [rsp+58h]; this
0x180058ad7  test    eax, eax
0x180058ad9  jns     short loc_180058AF0
0x180058adb  mov     r9d, eax; char *
0x180058ade  lea     r8, aShellOobeMachi_26; "shell\\oobe\\machine\\plugins\\adapters"...
0x180058ae5  mov     edx, 40h ; '@'; void *
0x180058aea  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180058af0  mov     [rsp+58h+var_28], 0
0x180058af9  lea     r9, [rsp+58h+var_28]
0x180058afe  call    COOBESettingsStore_CreateInstance
0x180058b03  mov     rcx, [rsp+58h]; this
0x180058b08  test    eax, eax
0x180058b0a  jns     short loc_180058B20
0x180058b0c  mov     r9d, eax; char *
0x180058b0f  lea     r8, aShellOobeMachi_26; "shell\\oobe\\machine\\plugins\\adapters"...
0x180058b16  mov     edx, 44h ; 'D'; void *
0x180058b1b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180058b20  lea     rdx, [rsp+58h+var_18]
0x180058b25  lea     rcx, [rsp+58h+arg_18]
0x180058b2a  call    ??$query@UIOOBESettingsParser@@@?$com_ptr_t@UIOOBEPlugin@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIOOBESettingsParser@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IOOBEPlugin,wil::err_exception_policy>::query<IOOBESettingsParser>(void)
0x180058b2f  nop
0x180058b30  mov     rcx, [rsp+58h+var_18]
0x180058b35  mov     rax, [rcx]
0x180058b38  mov     rdx, [rsp+58h+var_28]
0x180058b3d  mov     rax, [rax+18h]
0x180058b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b46  mov     rcx, [rsp+58h]; this
0x180058b4b  test    eax, eax
0x180058b4d  jns     short loc_180058B63
0x180058b4f  mov     r9d, eax; char *
0x180058b52  lea     r8, aShellOobeMachi_26; "shell\\oobe\\machine\\plugins\\adapters"...
0x180058b59  mov     edx, 48h ; 'H'; void *
0x180058b5e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180058b63  mov     rcx, [rsp+58h+arg_18]
0x180058b68  mov     rax, [rcx]
0x180058b6b  mov     r8, rdi
0x180058b6e  mov     rdx, rsi
0x180058b71  mov     rax, [rax]
0x180058b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b79  mov     rcx, [rsp+58h]; this
0x180058b7e  test    eax, eax
0x180058b80  jns     short loc_180058B96
0x180058b82  mov     r9d, eax; char *
0x180058b85  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180058b8c  mov     edx, 1CBEh; void *
0x180058b91  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180058b96  mov     eax, [rsp+58h+arg_10]
0x180058b9a  mov     [rbx], eax
0x180058b9c  lea     rcx, [rsp+58h+var_18]
0x180058ba1  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180058ba6  nop
0x180058ba7  lea     rcx, [rsp+58h+var_28]
0x180058bac  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180058bb1  nop
0x180058bb2  lea     rcx, [rsp+58h+var_20]
0x180058bb7  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180058bbc  nop
0x180058bbd  lea     rcx, [rsp+58h+arg_18]
0x180058bc2  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180058bc7  nop
0x180058bc8  xor     eax, eax
0x180058bca  jmp     short loc_180058BD0
0x180058bcc  mov     eax, [rsp+58h+arg_10]
0x180058bd0  mov     rbx, [rsp+58h+arg_0]
0x180058bd5  mov     rsi, [rsp+58h+arg_8]
0x180058bda  add     rsp, 50h
0x180058bde  pop     rdi
0x180058bdf  retn
```
