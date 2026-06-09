# _lambda_88033ccf0c41991f05909b2ca21328b6_::operator()(Windows::Internal::CBasicResult<uint,0> &)

- ea: `0x18004e330`
- end: `0x18004e3f3`
- name: `??R_lambda_88033ccf0c41991f05909b2ca21328b6_@@QEBAJAEAV?$CBasicResult@I$0A@@Internal@Windows@@@Z`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800531f0`

## callees

- `0x1800076d4`
- `0x180009760`
- `0x180046e48`
- `0x18004e330`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e37c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e37c`

## string_xrefs

- `0x18004e3bd`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _lambda_88033ccf0c41991f05909b2ca21328b6_::operator()(_QWORD *a1, __int64 a2)
{
  LPVOID v3; // rcx
  HRESULT v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v10; // [rsp+40h] [rbp+8h] BYREF
  LPVOID v11; // [rsp+50h] [rbp+18h] BYREF

  wil::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>(
    &v11,
    *a1 + 96LL);
  v3 = v11;
  if ( v11 )
  {
LABEL_5:
    v10 = 0;
    v4 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v3 + 72LL))(v3, &v10);
    v5 = v4;
    if ( v4 < 0 )
    {
      v6 = 628;
      goto LABEL_7;
    }
    *(_DWORD *)(a2 + 16) = v10;
LABEL_9:
    v5 = 0;
    goto LABEL_10;
  }
  v11 = 0;
  v4 = CoCreateInstance(
         &GUID_9dea6e0b_8856_45d8_a424_57244aef1e3c,
         0,
         1u,
         &GUID_8abfcb3d_15fe_49b6_b193_d64f14f5d31b,
         &v11);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v3 = v11;
    if ( !v11 )
      goto LABEL_9;
    goto LABEL_5;
  }
  v6 = 622;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
    (const char *)(unsigned int)v4,
    ppv);
LABEL_10:
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v11);
  return v5;
}

```

## disassembly

```asm
0x18004e330  mov     [rsp+arg_8], rbx
0x18004e335  push    rdi
0x18004e336  sub     rsp, 30h
0x18004e33a  mov     rdi, rdx
0x18004e33d  mov     rdx, [rcx]
0x18004e340  add     rdx, 60h ; '`'
0x18004e344  lea     rcx, [rsp+38h+arg_10]
0x18004e349  call    ??0?$com_ptr_t@UICoreKeyboardInputProfileManager@Core@Text@Internal@UI@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>(wil::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy> const &)
0x18004e34e  nop
0x18004e34f  mov     rcx, [rsp+38h+arg_10]
0x18004e354  test    rcx, rcx
0x18004e357  jnz     short loc_18004E399
0x18004e359  mov     [rsp+38h+arg_10], rcx
0x18004e35e  lea     rax, [rsp+38h+arg_10]
0x18004e363  mov     qword ptr [rsp+38h+ppv], rax; int
0x18004e368  lea     r9, _GUID_8abfcb3d_15fe_49b6_b193_d64f14f5d31b; riid
0x18004e36f  xor     edx, edx; pUnkOuter
0x18004e371  lea     r8d, [rcx+1]; dwClsContext
0x18004e375  lea     rcx, _GUID_9dea6e0b_8856_45d8_a424_57244aef1e3c; rclsid
0x18004e37c  call    cs:__imp_CoCreateInstance
0x18004e382  mov     ebx, eax
0x18004e384  test    eax, eax
0x18004e386  jns     short loc_18004E38F
0x18004e388  mov     edx, 26Eh
0x18004e38d  jmp     short loc_18004E3BD
0x18004e38f  mov     rcx, [rsp+38h+arg_10]
0x18004e394  test    rcx, rcx
0x18004e397  jz      short loc_18004E3DA
0x18004e399  mov     [rsp+38h+arg_0], 0
0x18004e3a1  mov     rax, [rcx]
0x18004e3a4  lea     rdx, [rsp+38h+arg_0]
0x18004e3a9  mov     rax, [rax+48h]
0x18004e3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3b2  mov     ebx, eax
0x18004e3b4  test    eax, eax
0x18004e3b6  jns     short loc_18004E3D3
0x18004e3b8  mov     edx, 274h; void *
0x18004e3bd  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004e3c4  mov     r9d, eax; char *
0x18004e3c7  mov     rcx, [rsp+38h]; this
0x18004e3cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e3d1  jmp     short loc_18004E3DC
0x18004e3d3  mov     eax, [rsp+38h+arg_0]
0x18004e3d7  mov     [rdi+10h], eax
0x18004e3da  xor     ebx, ebx
0x18004e3dc  lea     rcx, [rsp+38h+arg_10]
0x18004e3e1  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004e3e6  mov     eax, ebx
0x18004e3e8  mov     rbx, [rsp+38h+arg_8]
0x18004e3ed  add     rsp, 30h
0x18004e3f1  pop     rdi
0x18004e3f2  retn
```
