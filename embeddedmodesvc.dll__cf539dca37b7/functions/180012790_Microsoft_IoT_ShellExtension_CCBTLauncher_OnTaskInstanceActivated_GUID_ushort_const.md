# Microsoft::IoT::ShellExtension::CCBTLauncher::OnTaskInstanceActivated(_GUID,ushort const *)

- ea: `0x180012790`
- end: `0x18001297d`
- name: `?OnTaskInstanceActivated@CCBTLauncher@ShellExtension@IoT@Microsoft@@UEAAXU_GUID@@PEBG@Z`
- size: `493`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CCBTLauncher *__hidden this, struct _GUID *__struct_ptr, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012760`

## callees

- `0x180002b10`
- `0x180008358`
- `0x180008378`
- `0x18000854c`
- `0x1800091c4`
- `0x18000a2ac`
- `0x18000ab5c`
- `0x18000d410`
- `0x18000ec88`
- `0x18000fe60`
- `0x18001064c`
- `0x18001091c`
- `0x180010980`
- `0x180011134`
- `0x180012790`
- `0x1800138b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800127fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800127fe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800128f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800128f5`

## string_xrefs

- `0x1800127c0`: `BackgroundTaskInstanceActivation`
- `0x180012844`: `UnknownTaskInstanceActivated`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::IoT::ShellExtension::CCBTLauncher::OnTaskInstanceActivated(
        Microsoft::IoT::ShellExtension::CCBTLauncher *this,
        struct _GUID *a2,
        const unsigned __int16 *a3)
{
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 *v7; // rax
  __int64 v8; // rcx
  const char *v9; // r9
  char *v10[2]; // [rsp+20h] [rbp-338h] BYREF
  __int128 v11; // [rsp+30h] [rbp-328h] BYREF
  const unsigned __int16 *v12; // [rsp+40h] [rbp-318h] BYREF
  struct _RTL_CRITICAL_SECTION *v13; // [rsp+48h] [rbp-310h] BYREF
  wil::ResultException *v14[2]; // [rsp+50h] [rbp-308h] BYREF
  char v15; // [rsp+60h] [rbp-2F8h]
  _QWORD v16[42]; // [rsp+70h] [rbp-2E8h] BYREF
  _QWORD v17[42]; // [rsp+1C0h] [rbp-198h] BYREF
  std::bad_alloc *v18; // [rsp+310h] [rbp-48h] BYREF
  std::invalid_argument *v19; // [rsp+318h] [rbp-40h] BYREF
  std::range_error *v20; // [rsp+320h] [rbp-38h] BYREF
  std::runtime_error *v21; // [rsp+328h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+0h]

  v12 = a3;
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v16,
    (__int64)"BackgroundTaskInstanceActivation");
  v16[0] = &Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskInstanceActivation::`vftable';
  Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskInstanceActivation::StartActivity((Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskInstanceActivation *)v16);
  v14[1] = (wil::ResultException *)v16;
  v15 = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v13 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  v5 = *((_QWORD *)this + 16);
  v11 = (__int128)*a2;
  while ( 1 )
  {
    if ( v5 == *((_QWORD *)this + 17) )
    {
      wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
        (__int64)v17,
        (__int64)"UnknownTaskInstanceActivated");
      v17[0] = &Microsoft::IoT::ShellExtension::CTelemetryProvider::UnknownTaskInstanceActivated::`vftable';
      Microsoft::IoT::ShellExtension::CTelemetryProvider::UnknownTaskInstanceActivated::~UnknownTaskInstanceActivated((Microsoft::IoT::ShellExtension::CTelemetryProvider::UnknownTaskInstanceActivated *)v17);
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0xC8,
        (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
        (const char *)0x8000FFFFLL,
        (int)v10[0]);
    }
    v6 = v11 - *(_QWORD *)(v5 + 60);
    if ( (_QWORD)v11 == *(_QWORD *)(v5 + 60) )
      v6 = *((_QWORD *)&v11 + 1) - *(_QWORD *)(v5 + 68);
    if ( !v6 )
      break;
    v5 += 88;
  }
  v10[0] = *(char **)(v5 + 40);
  v7 = *(__int64 **)(v5 + 16);
  if ( v7 )
    v8 = *v7;
  else
    v8 = 0;
  *(_QWORD *)&v11 = v8;
  Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivated<unsigned short *,unsigned short *,_GUID &,unsigned short const * &>(
    (__int64 *)&v11,
    (__int64 *)v10,
    (__int128 *)a2,
    (__int64 *)&v12);
  try
  {
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v10);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      (_QWORD *)(v5 + 48),
      v10);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)v10);
    *(_DWORD *)(v5 + 56) = 0;
    *(_QWORD *)(v5 + 8) = GetTickCount64();
    Microsoft::IoT::ShellExtension::CCBTLauncher::CheckForPendingTasks((Microsoft::IoT::ShellExtension::CCBTLauncher *)((char *)this - 32));
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v13);
  }
  catch ( wil::ResultException *v14 )
  {
    LODWORD(v10[0]) = *((_DWORD *)v14[0] + 8);
    if ( SLODWORD(v10[0]) < 0 )
LABEL_13:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD2,
        (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
        (const char *)LODWORD(v10[0]));
  }
  catch ( std::bad_alloc *v18 )
  {
    LODWORD(v10[0]) = -2147024882;
    goto LABEL_13;
  }
  catch ( std::invalid_argument *v19 )
  {
    LODWORD(v10[0]) = -2147024809;
    goto LABEL_13;
  }
  catch ( std::range_error *v20 )
  {
    LODWORD(v10[0]) = -2147483637;
    goto LABEL_13;
  }
  catch ( std::runtime_error *v21 )
  {
    LODWORD(v10[0]) = -2147467259;
    goto LABEL_13;
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(
      retaddr,
      (void *)0xD2,
      (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
      v9);
  }
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v16);
  Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskInstanceActivation::~BackgroundTaskInstanceActivation((Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskInstanceActivation *)v16);
}

```

## disassembly

```asm
0x180012790  mov     [rsp+arg_18], rbx
0x180012795  push    rsi
0x180012796  push    rdi
0x180012797  push    r14
0x180012799  sub     rsp, 340h
0x1800127a0  mov     rax, cs:__security_cookie
0x1800127a7  xor     rax, rsp
0x1800127aa  mov     [rsp+358h+var_28], rax
0x1800127b2  mov     r14, r8
0x1800127b5  mov     rsi, rdx
0x1800127b8  mov     rdi, rcx
0x1800127bb  mov     [rsp+358h+var_318], r8
0x1800127c0  lea     rdx, aBackgroundtask_2; "BackgroundTaskInstanceActivation"
0x1800127c7  lea     rcx, [rsp+358h+var_2E8]
0x1800127cc  call    ??0?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800127d1  lea     rax, ??_7BackgroundTaskInstanceActivation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@6B@; const Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskInstanceActivation::`vftable'
0x1800127d8  mov     [rsp+358h+var_2E8], rax
0x1800127dd  lea     rcx, [rsp+358h+var_2E8]; this
0x1800127e2  call    ?StartActivity@BackgroundTaskInstanceActivation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAAXXZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskInstanceActivation::StartActivity(void)
0x1800127e7  nop
0x1800127e8  lea     rax, [rsp+358h+var_2E8]
0x1800127ed  mov     [rsp+358h+var_300], rax
0x1800127f2  mov     [rsp+358h+var_2F8], 1
0x1800127f7  lea     rbx, [rdi+40h]
0x1800127fb  mov     rcx, rbx; lpCriticalSection
0x1800127fe  call    cs:__imp_EnterCriticalSection
0x180012804  mov     [rsp+358h+var_310], rbx
0x180012809  mov     rbx, [rdi+80h]
0x180012810  movups  xmm0, xmmword ptr [rsi]
0x180012813  movdqu  [rsp+358h+var_328], xmm0
0x180012819  mov     rcx, [rdi+88h]
0x180012820  jmp     short loc_18001283F
0x180012822  mov     rax, qword ptr [rsp+358h+var_328]
0x180012827  sub     rax, [rbx+3Ch]
0x18001282b  jnz     short loc_180012836
0x18001282d  mov     rax, qword ptr [rsp+358h+var_328+8]
0x180012832  sub     rax, [rbx+44h]
0x180012836  test    rax, rax
0x180012839  jz      short loc_180012894
0x18001283b  add     rbx, 58h ; 'X'
0x18001283f  cmp     rbx, rcx
0x180012842  jnz     short loc_180012822
0x180012844  lea     rdx, aUnknowntaskins; "UnknownTaskInstanceActivated"
0x18001284b  lea     rcx, [rsp+358h+var_198]
0x180012853  call    ??0?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180012858  lea     rax, ??_7UnknownTaskInstanceActivated@CTelemetryProvider@ShellExtension@IoT@Microsoft@@6B@; const Microsoft::IoT::ShellExtension::CTelemetryProvider::UnknownTaskInstanceActivated::`vftable'
0x18001285f  mov     [rsp+358h+var_198], rax
0x180012867  lea     rcx, [rsp+358h+var_198]; this
0x18001286f  call    ??1UnknownTaskInstanceActivated@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::UnknownTaskInstanceActivated::~UnknownTaskInstanceActivated(void)
0x180012874  mov     rcx, [rsp+358h]; this
0x18001287c  mov     r9d, 8000FFFFh; char *
0x180012882  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180012889  mov     edx, 0C8h; void *
0x18001288e  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180012894  mov     rax, [rbx+28h]
0x180012898  mov     [rsp+358h+var_338], rax
0x18001289d  mov     rax, [rbx+10h]
0x1800128a1  test    rax, rax
0x1800128a4  jz      short loc_1800128AB
0x1800128a6  mov     rcx, [rax]
0x1800128a9  jmp     short loc_1800128AD
0x1800128ab  xor     ecx, ecx
0x1800128ad  mov     qword ptr [rsp+358h+var_328], rcx
0x1800128b2  lea     r9, [rsp+358h+var_318]
0x1800128b7  mov     r8, rsi
0x1800128ba  lea     rdx, [rsp+358h+var_338]
0x1800128bf  lea     rcx, [rsp+358h+var_328]
0x1800128c4  call    ??$BackgroundTaskActivated@PEAGPEAGAEAU_GUID@@AEAPEBG@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAX$$QEAPEAG0AEAU_GUID@@AEAPEBG@Z; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivated<ushort *,ushort *,_GUID &,ushort const * &>(ushort * &&,ushort * &&,_GUID &,ushort const * &)
0x1800128c9  mov     rdx, r14
0x1800128cc  lea     rcx, [rsp+358h+var_338]
0x1800128d1  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800128d6  lea     rcx, [rbx+30h]
0x1800128da  lea     rdx, [rsp+358h+var_338]
0x1800128df  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800128e4  lea     rcx, [rsp+358h+var_338]
0x1800128e9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800128ee  mov     dword ptr [rbx+38h], 0
0x1800128f5  call    cs:__imp_GetTickCount64
0x1800128fb  mov     [rbx+8], rax
0x1800128ff  lea     rcx, [rdi-20h]; this
0x180012903  call    ?CheckForPendingTasks@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAXXZ; Microsoft::IoT::ShellExtension::CCBTLauncher::CheckForPendingTasks(void)
0x180012908  nop
0x180012909  lea     rcx, [rsp+358h+var_310]
0x18001290e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180012913  nop
0x180012914  jmp     short loc_180012944
0x180012916  cmp     dword ptr [rsp+358h+var_338], 0
0x18001291b  jge     short loc_180012944
0x18001291d  jmp     short loc_180012925
0x18001291f  jmp     short loc_180012925
0x180012921  jmp     short loc_180012925
0x180012923  jmp     short $+2
0x180012925  mov     rcx, [rsp+358h]; this
0x18001292d  mov     r9d, dword ptr [rsp+358h+var_338]; char *
0x180012932  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180012939  mov     edx, 0D2h; void *
0x18001293e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012943  nop
0x180012944  lea     rcx, [rsp+358h+var_2E8]
0x180012949  call    ?Stop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001294e  nop
0x18001294f  lea     rcx, [rsp+358h+var_2E8]; this
0x180012954  call    ??1BackgroundTaskInstanceActivation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskInstanceActivation::~BackgroundTaskInstanceActivation(void)
0x180012959  mov     rcx, [rsp+358h+var_28]
0x180012961  xor     rcx, rsp; StackCookie
0x180012964  call    __security_check_cookie
0x180012969  mov     rbx, [rsp+358h+arg_18]
0x180012971  add     rsp, 340h
0x180012978  pop     r14
0x18001297a  pop     rdi
0x18001297b  pop     rsi
0x18001297c  retn
```
