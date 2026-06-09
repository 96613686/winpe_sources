# OobeZdpElevatedManagerCore::IsCurrentNetworkMetered(void)

- ea: `0x18000f5cc`
- end: `0x18000f692`
- name: `?IsCurrentNetworkMetered@OobeZdpElevatedManagerCore@@AEAA_NXZ`
- size: `198`
- prototype: `bool __fastcall(OobeZdpElevatedManagerCore *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000ebd0`

## callees

- `0x180009760`
- `0x18000b098`
- `0x18000f5cc`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f600`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f600`

## string_xrefs

- `0x18000f612`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18000f65f`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall OobeZdpElevatedManagerCore::IsCurrentNetworkMetered(OobeZdpElevatedManagerCore *this)
{
  char v1; // bl
  HRESULT v2; // eax
  int v4; // eax
  int v5; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  OobeZdpElevatedManagerCore *v7; // [rsp+40h] [rbp+8h] BYREF
  LPVOID v8; // [rsp+48h] [rbp+10h] BYREF

  v7 = this;
  v8 = 0;
  v1 = 1;
  v2 = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &GUID_dcb00008_570f_4a9b_8d69_199fdba5723b, &v8);
  if ( v2 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
      (const char *)(unsigned int)v2,
      v5);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v8);
    return 0;
  }
  LODWORD(v7) = 0;
  v4 = (*(__int64 (__fastcall **)(LPVOID, OobeZdpElevatedManagerCore **, _QWORD))(*(_QWORD *)v8 + 24LL))(v8, &v7, 0);
  if ( v4 >= 0 )
  {
    if ( (_DWORD)v7 && ((unsigned __int8)v7 & 1) == 0 )
      goto LABEL_8;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
      (const char *)(unsigned int)v4,
      v5);
  }
  v1 = 0;
LABEL_8:
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v8);
  return v1;
}

```

## disassembly

```asm
0x18000f5cc  mov     r11, rsp
0x18000f5cf  mov     [r11+8], rcx
0x18000f5d3  push    rbx
0x18000f5d4  sub     rsp, 30h
0x18000f5d8  mov     qword ptr [r11+10h], 0
0x18000f5e0  lea     rax, [r11+10h]
0x18000f5e4  mov     [r11-18h], rax
0x18000f5e8  lea     r9, _GUID_dcb00008_570f_4a9b_8d69_199fdba5723b; riid
0x18000f5ef  mov     ebx, 1
0x18000f5f4  mov     r8d, ebx; dwClsContext
0x18000f5f7  xor     edx, edx; pUnkOuter
0x18000f5f9  lea     rcx, CLSID_NetworkListManager; rclsid
0x18000f600  call    cs:__imp_CoCreateInstance
0x18000f606  mov     rcx, [rsp+38h]; this
0x18000f60b  test    eax, eax
0x18000f60d  jns     short loc_18000F632
0x18000f60f  mov     r9d, eax; char *
0x18000f612  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000f619  mov     edx, 92h; void *
0x18000f61e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f623  nop
0x18000f624  lea     rcx, [rsp+38h+arg_8]
0x18000f629  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000f62e  xor     al, al
0x18000f630  jmp     short loc_18000F68C
0x18000f632  mov     dword ptr [rsp+38h+arg_0], 0
0x18000f63a  mov     rcx, [rsp+38h+arg_8]
0x18000f63f  mov     rax, [rcx]
0x18000f642  xor     r8d, r8d
0x18000f645  lea     rdx, [rsp+38h+arg_0]
0x18000f64a  mov     rax, [rax+18h]
0x18000f64e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f653  mov     rcx, [rsp+38h]; this
0x18000f658  test    eax, eax
0x18000f65a  jns     short loc_18000F672
0x18000f65c  mov     r9d, eax; char *
0x18000f65f  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000f666  mov     edx, 98h; void *
0x18000f66b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f670  jmp     short loc_18000F67E
0x18000f672  mov     eax, dword ptr [rsp+38h+arg_0]
0x18000f676  test    eax, eax
0x18000f678  jz      short loc_18000F67E
0x18000f67a  test    bl, al
0x18000f67c  jz      short loc_18000F680
0x18000f67e  xor     bl, bl
0x18000f680  lea     rcx, [rsp+38h+arg_8]
0x18000f685  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000f68a  mov     al, bl
0x18000f68c  add     rsp, 30h
0x18000f690  pop     rbx
0x18000f691  retn
```
