# _lambda_22e93fbf5b9657922db99cb09b256456_::operator()(Windows::Internal::CNoResult &)

- ea: `0x18004e0d0`
- end: `0x18004e327`
- name: `??R_lambda_22e93fbf5b9657922db99cb09b256456_@@QEBAJAEAVCNoResult@Internal@Windows@@@Z`
- size: `599`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800531b0`

## callees

- `0x180002b60`
- `0x1800076d4`
- `0x180009760`
- `0x18000b098`
- `0x1800266f8`
- `0x180046e48`
- `0x18004e080`
- `0x18004e0d0`
- `0x1800539f0`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e255`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e255`

## string_xrefs

- `0x18004e191`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`
- `0x18004e21a`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`
- `0x18004e2ae`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`
- `0x18004e2eb`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall _lambda_22e93fbf5b9657922db99cb09b256456_::operator()(__int64 a1)
{
  __int64 v2; // r8
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  void *v6; // rcx
  const struct _GUID *v7; // rdx
  struct _GUID *v8; // rcx
  int v9; // eax
  HRESULT Instance; // eax
  __int64 v11; // rdx
  int v12; // eax
  int *ppv; // [rsp+20h] [rbp-50h]
  int *ppva; // [rsp+20h] [rbp-50h]
  struct _GUID *v16; // [rsp+40h] [rbp-30h] BYREF
  bool v17; // [rsp+48h] [rbp-28h] BYREF
  void *v18; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v19[8]; // [rsp+58h] [rbp-18h] BYREF
  _BYTE v20[8]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v2 = 0;
  do
  {
    v20[v2] = (*(_DWORD *)(a1 + 8) & (1 << v2)) == 1 << v2;
    v19[v2] = (*(_DWORD *)(a1 + 12) & (1 << v2)) == 1 << v2;
    v2 = (unsigned int)(v2 + 1);
  }
  while ( (unsigned int)v2 < 8 );
  if ( !*(_BYTE *)(a1 + 17) )
  {
LABEL_12:
    wil::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>(
      &v16,
      *(_QWORD *)a1 + 96LL);
    v8 = v16;
    if ( v16 )
      goto LABEL_19;
    v16 = 0;
    v9 = TryCloudExperienceHostCreateOOBEUserObject(0, v7, (void **)&v16, &v17);
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x235,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
        (const char *)(unsigned int)v9,
        (int)ppv);
    v8 = v16;
    if ( v16 )
      goto LABEL_19;
    v16 = 0;
    Instance = CoCreateInstance(
                 &GUID_9dea6e0b_8856_45d8_a424_57244aef1e3c,
                 0,
                 1u,
                 &GUID_8abfcb3d_15fe_49b6_b193_d64f14f5d31b,
                 (LPVOID *)&v16);
    v4 = Instance;
    if ( Instance < 0 )
    {
      v11 = 570;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
        (const char *)(unsigned int)Instance,
        (int)ppva);
LABEL_25:
      v6 = &v16;
      goto LABEL_26;
    }
    v8 = v16;
    if ( v16 )
    {
LABEL_19:
      ppva = (int *)v19;
      Instance = (*(__int64 (__fastcall **)(struct _GUID *, __int64, _BYTE *))(*(_QWORD *)&v8->Data1 + 48LL))(
                   v8,
                   8,
                   v20);
      v4 = Instance;
      if ( Instance < 0 )
      {
        v11 = 577;
        goto LABEL_21;
      }
      v12 = (*(__int64 (__fastcall **)(struct _GUID *, _QWORD, __int64, _QWORD))(*(_QWORD *)&v16->Data1 + 56LL))(
              v16,
              *(unsigned int *)(a1 + 20),
              5,
              *(unsigned int *)(a1 + 12));
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x242,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
          (const char *)(unsigned int)v12,
          (int)v19);
    }
    v4 = 0;
    goto LABEL_25;
  }
  v18 = 0;
  if ( *(_QWORD *)(*(_QWORD *)a1 + 96LL) )
  {
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeSettingsElevatedManagerCore,wil::err_exception_policy>::operator=(&v18);
  }
  else
  {
    v18 = 0;
    v3 = CloudExperienceHostCreateElevatedObject(
           &GUID_9dea6e0b_8856_45d8_a424_57244aef1e3c,
           &GUID_8abfcb3d_15fe_49b6_b193_d64f14f5d31b,
           &v18);
    v4 = v3;
    if ( v3 < 0 )
    {
      v5 = 553;
      goto LABEL_8;
    }
  }
  ppv = (int *)v19;
  v3 = (*(__int64 (__fastcall **)(void *, __int64, _BYTE *))(*(_QWORD *)v18 + 48LL))(v18, 8, v20);
  v4 = v3;
  if ( v3 >= 0 )
  {
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v18);
    goto LABEL_12;
  }
  v5 = 556;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
    (const char *)(unsigned int)v3,
    (int)ppv);
  v6 = &v18;
LABEL_26:
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(v6);
  return v4;
}

```

## disassembly

```asm
0x18004e0d0  mov     [rsp-8+arg_8], rbx
0x18004e0d5  mov     [rsp-8+arg_10], rdi
0x18004e0da  push    rbp
0x18004e0db  mov     rbp, rsp
0x18004e0de  sub     rsp, 70h
0x18004e0e2  mov     rax, cs:__security_cookie
0x18004e0e9  xor     rax, rsp
0x18004e0ec  mov     [rbp+var_8], rax
0x18004e0f0  mov     rdi, rcx
0x18004e0f3  xor     r8d, r8d
0x18004e0f6  mov     ecx, r8d
0x18004e0f9  mov     edx, 1
0x18004e0fe  shl     edx, cl
0x18004e100  mov     eax, edx
0x18004e102  and     eax, [rdi+8]
0x18004e105  cmp     eax, edx
0x18004e107  setz    al
0x18004e10a  mov     [rbp+r8+var_10], al
0x18004e10f  mov     eax, edx
0x18004e111  and     eax, [rdi+0Ch]
0x18004e114  cmp     eax, edx
0x18004e116  setz    al
0x18004e119  mov     [rbp+r8+var_18], al
0x18004e11e  inc     r8d
0x18004e121  cmp     r8d, 8
0x18004e125  jb      short loc_18004E0F6
0x18004e127  cmp     byte ptr [rdi+11h], 0
0x18004e12b  jz      loc_18004E1E4
0x18004e131  mov     [rbp+var_20], 0
0x18004e139  mov     rax, [rdi]
0x18004e13c  mov     rdx, [rax+60h]
0x18004e140  test    rdx, rdx
0x18004e143  jz      short loc_18004E1AB
0x18004e145  lea     rcx, [rbp+var_20]
0x18004e149  call    ??4?$com_ptr_t@UIOobeSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAUIOobeSettingsElevatedManagerCore@CloudExperienceHostAPI@@@Z; wil::com_ptr_t<CloudExperienceHostAPI::IOobeSettingsElevatedManagerCore,wil::err_exception_policy>::operator=(CloudExperienceHostAPI::IOobeSettingsElevatedManagerCore *)
0x18004e14e  mov     r10, [rbp+var_20]
0x18004e152  mov     rax, [r10]
0x18004e155  mov     [rsp+70h+var_40], 1
0x18004e15a  mov     cl, [rdi+10h]
0x18004e15d  mov     [rsp+70h+var_48], cl
0x18004e161  lea     rcx, [rbp+var_18]
0x18004e165  mov     [rsp+70h+ppv], rcx; int
0x18004e16a  mov     r9d, 8
0x18004e170  lea     r8, [rbp+var_10]
0x18004e174  mov     edx, r9d
0x18004e177  mov     rcx, r10
0x18004e17a  mov     rax, [rax+30h]
0x18004e17e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e183  mov     ebx, eax
0x18004e185  test    eax, eax
0x18004e187  jns     short loc_18004E1DB
0x18004e189  mov     edx, 22Ch; void *
0x18004e18e  mov     r9d, eax; char *
0x18004e191  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004e198  mov     rcx, [rbp+8]; this
0x18004e19c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e1a1  nop
0x18004e1a2  lea     rcx, [rbp+var_20]
0x18004e1a6  jmp     loc_18004E302
0x18004e1ab  mov     [rbp+var_20], 0
0x18004e1b3  lea     r8, [rbp+var_20]; void **
0x18004e1b7  lea     rdx, _GUID_8abfcb3d_15fe_49b6_b193_d64f14f5d31b; struct _GUID *
0x18004e1be  lea     rcx, _GUID_9dea6e0b_8856_45d8_a424_57244aef1e3c; struct _GUID *
0x18004e1c5  call    ?CloudExperienceHostCreateElevatedObject@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateElevatedObject(_GUID const &,_GUID const &,void * *)
0x18004e1ca  mov     ebx, eax
0x18004e1cc  test    eax, eax
0x18004e1ce  jns     loc_18004E14E
0x18004e1d4  mov     edx, 229h
0x18004e1d9  jmp     short loc_18004E18E
0x18004e1db  lea     rcx, [rbp+var_20]
0x18004e1df  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004e1e4  mov     rdx, [rdi]
0x18004e1e7  add     rdx, 60h ; '`'
0x18004e1eb  lea     rcx, [rbp+var_30]
0x18004e1ef  call    ??0?$com_ptr_t@UICoreKeyboardInputProfileManager@Core@Text@Internal@UI@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy>(wil::com_ptr_t<Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager,wil::err_exception_policy> const &)
0x18004e1f4  nop
0x18004e1f5  mov     rcx, [rbp+var_30]; struct _GUID *
0x18004e1f9  test    rcx, rcx
0x18004e1fc  jnz     short loc_18004E275
0x18004e1fe  mov     [rbp+var_30], rcx
0x18004e202  lea     r9, [rbp+var_28]; bool *
0x18004e206  lea     r8, [rbp+var_30]; void **
0x18004e20a  call    ?TryCloudExperienceHostCreateOOBEUserObject@@YAJAEBU_GUID@@0PEAPEAXPEA_N@Z; TryCloudExperienceHostCreateOOBEUserObject(_GUID const &,_GUID const &,void * *,bool *)
0x18004e20f  mov     rcx, [rbp+8]; this
0x18004e213  test    eax, eax
0x18004e215  jns     short loc_18004E22B
0x18004e217  mov     r9d, eax; char *
0x18004e21a  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004e221  mov     edx, 235h; void *
0x18004e226  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e22b  mov     rcx, [rbp+var_30]
0x18004e22f  test    rcx, rcx
0x18004e232  jnz     short loc_18004E275
0x18004e234  mov     [rbp+var_30], rcx
0x18004e238  lea     rax, [rbp+var_30]
0x18004e23c  mov     [rsp+70h+ppv], rax; ppv
0x18004e241  lea     r9, _GUID_8abfcb3d_15fe_49b6_b193_d64f14f5d31b; riid
0x18004e248  xor     edx, edx; pUnkOuter
0x18004e24a  lea     r8d, [rcx+1]; dwClsContext
0x18004e24e  lea     rcx, _GUID_9dea6e0b_8856_45d8_a424_57244aef1e3c; rclsid
0x18004e255  call    cs:__imp_CoCreateInstance
0x18004e25b  mov     ebx, eax
0x18004e25d  test    eax, eax
0x18004e25f  jns     short loc_18004E268
0x18004e261  mov     edx, 23Ah
0x18004e266  jmp     short loc_18004E2AE
0x18004e268  mov     rcx, [rbp+var_30]
0x18004e26c  test    rcx, rcx
0x18004e26f  jz      loc_18004E2FC
0x18004e275  mov     rax, [rcx]
0x18004e278  mov     [rsp+70h+var_40], 0
0x18004e27d  mov     dl, [rdi+10h]
0x18004e280  mov     [rsp+70h+var_48], dl
0x18004e284  lea     rdx, [rbp+var_18]
0x18004e288  mov     [rsp+70h+ppv], rdx; int
0x18004e28d  mov     r9d, 8
0x18004e293  lea     r8, [rbp+var_10]
0x18004e297  mov     edx, r9d
0x18004e29a  mov     rax, [rax+30h]
0x18004e29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2a3  mov     ebx, eax
0x18004e2a5  test    eax, eax
0x18004e2a7  jns     short loc_18004E2C3
0x18004e2a9  mov     edx, 241h; void *
0x18004e2ae  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004e2b5  mov     r9d, eax; char *
0x18004e2b8  mov     rcx, [rbp+8]; this
0x18004e2bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e2c1  jmp     short loc_18004E2FE
0x18004e2c3  mov     rcx, [rbp+var_30]
0x18004e2c7  mov     rax, [rcx]
0x18004e2ca  mov     r9d, [rdi+0Ch]
0x18004e2ce  mov     r8d, 5
0x18004e2d4  mov     edx, [rdi+14h]
0x18004e2d7  mov     rax, [rax+38h]
0x18004e2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2e0  mov     rcx, [rbp+8]; this
0x18004e2e4  test    eax, eax
0x18004e2e6  jns     short loc_18004E2FC
0x18004e2e8  mov     r9d, eax; char *
0x18004e2eb  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004e2f2  mov     edx, 242h; void *
0x18004e2f7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e2fc  xor     ebx, ebx
0x18004e2fe  lea     rcx, [rbp+var_30]
0x18004e302  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004e307  mov     eax, ebx
0x18004e309  mov     rcx, [rbp+var_8]
0x18004e30d  xor     rcx, rsp; StackCookie
0x18004e310  call    __security_check_cookie
0x18004e315  lea     r11, [rsp+70h+var_s0]
0x18004e31a  mov     rbx, [r11+18h]
0x18004e31e  mov     rdi, [r11+20h]
0x18004e322  mov     rsp, r11
0x18004e325  pop     rbp
0x18004e326  retn
```
