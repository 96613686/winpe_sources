# Microsoft::IoT::ShellExtension::CCBTLauncher::OnTaskInstanceCanceled(_GUID)

- ea: `0x1800129c0`
- end: `0x180012bc2`
- name: `?OnTaskInstanceCanceled@CCBTLauncher@ShellExtension@IoT@Microsoft@@UEAAXU_GUID@@@Z`
- size: `514`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CCBTLauncher *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012990`

## callees

- `0x180002b10`
- `0x180008358`
- `0x180008378`
- `0x18000854c`
- `0x1800091c4`
- `0x18000d410`
- `0x18000ede0`
- `0x18000ee44`
- `0x1800105f4`
- `0x180011134`
- `0x1800129c0`
- `0x180013778`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012a30`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012a30`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012ad6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012b12`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012ad6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012b12`

## string_xrefs

- `0x1800129f2`: `BackgroundTaskCancelled`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::IoT::ShellExtension::CCBTLauncher::OnTaskInstanceCanceled(
        Microsoft::IoT::ShellExtension::CCBTLauncher *this,
        struct _GUID *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  const char *v8; // r9
  int v9; // [rsp+20h] [rbp-1C8h]
  __int128 v10; // [rsp+30h] [rbp-1B8h] BYREF
  _QWORD *v11; // [rsp+40h] [rbp-1A8h] BYREF
  char v12; // [rsp+48h] [rbp-1A0h]
  struct _RTL_CRITICAL_SECTION *v13; // [rsp+50h] [rbp-198h] BYREF
  wil::ResultException *v14; // [rsp+58h] [rbp-190h] BYREF
  _QWORD v15[42]; // [rsp+60h] [rbp-188h] BYREF
  std::bad_alloc *v16; // [rsp+1B0h] [rbp-38h] BYREF
  std::invalid_argument *v17; // [rsp+1B8h] [rbp-30h] BYREF
  std::range_error *v18; // [rsp+1C0h] [rbp-28h] BYREF
  std::runtime_error *v19; // [rsp+1C8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  v9 = 0;
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v15,
    (__int64)"BackgroundTaskCancelled");
  v15[0] = &Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCancelled::`vftable';
  Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCancelled::StartActivity((Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCancelled *)v15);
  v11 = v15;
  v12 = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v13 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  v4 = *((_QWORD *)this + 16);
  v10 = (__int128)*a2;
  while ( 1 )
  {
    if ( v4 == *((_QWORD *)this + 17) )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x131,
        (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
        (const char *)0x8000FFFFLL,
        0);
    v5 = v10 - *(_QWORD *)(v4 + 60);
    if ( (_QWORD)v10 == *(_QWORD *)(v4 + 60) )
      v5 = *((_QWORD *)&v10 + 1) - *(_QWORD *)(v4 + 68);
    if ( !v5 )
      break;
    v4 += 88;
  }
  try
  {
    if ( *(_BYTE *)(v4 + 78) || *(_BYTE *)(v4 + 79) )
    {
      *(_DWORD *)(v4 + 56) = -2147024186;
      *(_QWORD *)(v4 + 8) = GetTickCount64();
      *(_QWORD *)&v10 = *(_QWORD *)(v4 + 40);
      v7 = *(_QWORD **)(v4 + 16);
      if ( v7 )
        v7 = (_QWORD *)*v7;
      v11 = v7;
      Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCanceledDone<unsigned short *,unsigned short *>(
        (__int64 *)&v11,
        (__int64 *)&v10);
    }
    else
    {
      if ( *(_DWORD *)(v4 + 56) == -2147483638
        || !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2)) )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 40LL))(*((_QWORD *)this + 2));
      }
      *(_DWORD *)(v4 + 56) = -2147467260;
      *(_QWORD *)(v4 + 8) = GetTickCount64();
      v11 = *(_QWORD **)(v4 + 40);
      v6 = *(_QWORD **)(v4 + 16);
      if ( v6 )
        v6 = (_QWORD *)*v6;
      *(_QWORD *)&v10 = v6;
      Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCanceledAborted<unsigned short *,unsigned short *>(
        (__int64 *)&v10,
        (__int64 *)&v11);
    }
    Microsoft::IoT::ShellExtension::CCBTLauncher::CheckForPendingTasks((Microsoft::IoT::ShellExtension::CCBTLauncher *)((char *)this - 32));
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v13);
  }
  catch ( wil::ResultException *v14 )
  {
    v9 = *((_DWORD *)v14 + 8);
  }
  catch ( std::bad_alloc *v16 )
  {
    v9 = -2147024882;
  }
  catch ( std::invalid_argument *v17 )
  {
    v9 = -2147024809;
  }
  catch ( std::range_error *v18 )
  {
    v9 = -2147483637;
  }
  catch ( std::runtime_error *v19 )
  {
    v9 = -2147467259;
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(
      retaddr,
      (void *)0x14A,
      (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
      v8);
  }
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x14A,
      (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
      (const char *)(unsigned int)v9);
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v15);
  Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCancelled::~BackgroundTaskCancelled((Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCancelled *)v15);
}

```

## disassembly

```asm
0x1800129c0  mov     [rsp+arg_8], rbx
0x1800129c5  mov     [rsp+arg_10], rsi
0x1800129ca  push    rdi
0x1800129cb  sub     rsp, 1E0h
0x1800129d2  mov     rax, cs:__security_cookie
0x1800129d9  xor     rax, rsp
0x1800129dc  mov     [rsp+1E8h+var_18], rax
0x1800129e4  mov     rsi, rdx
0x1800129e7  mov     rdi, rcx
0x1800129ea  mov     [rsp+1E8h+var_1C8], 0
0x1800129f2  lea     rdx, aBackgroundtask_0; "BackgroundTaskCancelled"
0x1800129f9  lea     rcx, [rsp+1E8h+var_188]
0x1800129fe  call    ??0?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180012a03  lea     rax, ??_7BackgroundTaskCancelled@CTelemetryProvider@ShellExtension@IoT@Microsoft@@6B@; const Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCancelled::`vftable'
0x180012a0a  mov     [rsp+1E8h+var_188], rax
0x180012a0f  lea     rcx, [rsp+1E8h+var_188]; this
0x180012a14  call    ?StartActivity@BackgroundTaskCancelled@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAAXXZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCancelled::StartActivity(void)
0x180012a19  nop
0x180012a1a  lea     rax, [rsp+1E8h+var_188]
0x180012a1f  mov     [rsp+1E8h+var_1A8], rax
0x180012a24  mov     [rsp+1E8h+var_1A0], 1
0x180012a29  lea     rbx, [rdi+40h]
0x180012a2d  mov     rcx, rbx; lpCriticalSection
0x180012a30  call    cs:__imp_EnterCriticalSection
0x180012a36  mov     [rsp+1E8h+var_198], rbx
0x180012a3b  mov     rbx, [rdi+80h]
0x180012a42  movups  xmm0, xmmword ptr [rsi]
0x180012a45  movdqu  [rsp+1E8h+var_1B8], xmm0
0x180012a4b  mov     rcx, [rdi+88h]
0x180012a52  jmp     short loc_180012A71
0x180012a54  mov     rax, qword ptr [rsp+1E8h+var_1B8]
0x180012a59  sub     rax, [rbx+3Ch]
0x180012a5d  jnz     short loc_180012A68
0x180012a5f  mov     rax, qword ptr [rsp+1E8h+var_1B8+8]
0x180012a64  sub     rax, [rbx+44h]
0x180012a68  test    rax, rax
0x180012a6b  jz      short loc_180012A96
0x180012a6d  add     rbx, 58h ; 'X'
0x180012a71  cmp     rbx, rcx
0x180012a74  jnz     short loc_180012A54
0x180012a76  mov     rcx, [rsp+1E8h]; this
0x180012a7e  mov     r9d, 8000FFFFh; char *
0x180012a84  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180012a8b  mov     edx, 131h; void *
0x180012a90  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180012a96  cmp     byte ptr [rbx+4Eh], 0
0x180012a9a  jnz     short loc_180012B0B
0x180012a9c  cmp     byte ptr [rbx+4Fh], 0
0x180012aa0  jnz     short loc_180012B0B
0x180012aa2  cmp     dword ptr [rbx+38h], 8000000Ah
0x180012aa9  jz      short loc_180012ABF
0x180012aab  mov     rcx, [rdi+10h]
0x180012aaf  mov     rax, [rcx]
0x180012ab2  mov     rax, [rax+18h]
0x180012ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012abb  test    al, al
0x180012abd  jnz     short loc_180012ACF
0x180012abf  mov     rcx, [rdi+10h]
0x180012ac3  mov     rax, [rcx]
0x180012ac6  mov     rax, [rax+28h]
0x180012aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012acf  mov     dword ptr [rbx+38h], 80004004h
0x180012ad6  call    cs:__imp_GetTickCount64
0x180012adc  mov     [rbx+8], rax
0x180012ae0  mov     rax, [rbx+28h]
0x180012ae4  mov     [rsp+1E8h+var_1A8], rax
0x180012ae9  mov     rax, [rbx+10h]
0x180012aed  test    rax, rax
0x180012af0  jz      short loc_180012AF5
0x180012af2  mov     rax, [rax]
0x180012af5  mov     qword ptr [rsp+1E8h+var_1B8], rax
0x180012afa  lea     rdx, [rsp+1E8h+var_1A8]
0x180012aff  lea     rcx, [rsp+1E8h+var_1B8]
0x180012b04  call    ??$BackgroundTaskCanceledAborted@PEAGPEAG@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAX$$QEAPEAG0@Z; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCanceledAborted<ushort *,ushort *>(ushort * &&,ushort * &&)
0x180012b09  jmp     short loc_180012B45
0x180012b0b  mov     dword ptr [rbx+38h], 800702C6h
0x180012b12  call    cs:__imp_GetTickCount64
0x180012b18  mov     [rbx+8], rax
0x180012b1c  mov     rax, [rbx+28h]
0x180012b20  mov     qword ptr [rsp+1E8h+var_1B8], rax
0x180012b25  mov     rax, [rbx+10h]
0x180012b29  test    rax, rax
0x180012b2c  jz      short loc_180012B31
0x180012b2e  mov     rax, [rax]
0x180012b31  mov     [rsp+1E8h+var_1A8], rax
0x180012b36  lea     rdx, [rsp+1E8h+var_1B8]
0x180012b3b  lea     rcx, [rsp+1E8h+var_1A8]
0x180012b40  call    ??$BackgroundTaskCanceledDone@PEAGPEAG@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAX$$QEAPEAG0@Z; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCanceledDone<ushort *,ushort *>(ushort * &&,ushort * &&)
0x180012b45  lea     rcx, [rdi-20h]; this
0x180012b49  call    ?CheckForPendingTasks@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAXXZ; Microsoft::IoT::ShellExtension::CCBTLauncher::CheckForPendingTasks(void)
0x180012b4e  nop
0x180012b4f  lea     rcx, [rsp+1E8h+var_198]
0x180012b54  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180012b59  nop
0x180012b5a  jmp     short loc_180012B64
0x180012b5c  jmp     short loc_180012B64
0x180012b5e  jmp     short loc_180012B64
0x180012b60  jmp     short loc_180012B64
0x180012b62  jmp     short $+2
0x180012b64  mov     rcx, [rsp+1E8h]; this
0x180012b6c  mov     r9d, [rsp+1E8h+var_1C8]; char *
0x180012b71  test    r9d, r9d
0x180012b74  jns     short loc_180012B88
0x180012b76  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180012b7d  mov     edx, 14Ah; void *
0x180012b82  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012b87  nop
0x180012b88  lea     rcx, [rsp+1E8h+var_188]
0x180012b8d  call    ?Stop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180012b92  nop
0x180012b93  lea     rcx, [rsp+1E8h+var_188]; this
0x180012b98  call    ??1BackgroundTaskCancelled@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskCancelled::~BackgroundTaskCancelled(void)
0x180012b9d  mov     rcx, [rsp+1E8h+var_18]
0x180012ba5  xor     rcx, rsp; StackCookie
0x180012ba8  call    __security_check_cookie
0x180012bad  lea     r11, [rsp+1E8h+var_8]
0x180012bb5  mov     rbx, [r11+18h]
0x180012bb9  mov     rsi, [r11+20h]
0x180012bbd  mov     rsp, r11
0x180012bc0  pop     rdi
0x180012bc1  retn
```
