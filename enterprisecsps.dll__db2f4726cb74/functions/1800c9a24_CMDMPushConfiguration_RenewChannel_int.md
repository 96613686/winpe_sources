# CMDMPushConfiguration::RenewChannel(int *)

- ea: `0x1800c9a24`
- end: `0x1800c9dcd`
- name: `?RenewChannel@CMDMPushConfiguration@@QEAAJPEAH@Z`
- size: `937`
- prototype: `__int64 __fastcall(CMDMPushConfiguration *__hidden this, int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e0b0`

## callees

- `0x180008de0`
- `0x18000b744`
- `0x18000b9ec`
- `0x18000caf4`
- `0x18000d4d4`
- `0x180025a9c`
- `0x18002dc94`
- `0x1800bef00`
- `0x1800c14c0`
- `0x1800c1780`
- `0x1800c1c90`
- `0x1800c1e64`
- `0x1800c7580`
- `0x1800c7f18`
- `0x1800c82d8`
- `0x1800c8730`
- `0x1800c9550`
- `0x1800c9a24`
- `0x1800ca028`
- `0x1800ca128`
- `0x1800ca45c`
- `0x1800cad44`
- `0x1800cb5a0`
- `0x180107010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800c9cd8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800c9cd8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c9c39`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c9c39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9c2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9c2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9bb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9bb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CMDMPushConfiguration::RenewChannel(CMDMPushConfiguration *this, int *a2)
{
  int v3; // ebx
  int LastRenewalTime; // eax
  __int64 v5; // rdx
  unsigned __int64 v6; // r9
  int ChannelObject; // eax
  __int64 (__fastcall *v8)(struct Windows::Networking::PushNotifications::IPushNotificationChannel *, HSTRING *); // r14
  int v9; // eax
  int v10; // eax
  const OLECHAR *StringRawBuffer; // rax
  BSTR v12; // rax
  unsigned __int64 v13; // rsi
  CMDMPushConfiguration *v14; // rcx
  int TestHookUri; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  unsigned __int64 v19; // rdx
  int v21[2]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 *v22; // [rsp+28h] [rbp-D8h] BYREF
  OLECHAR *psz; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  struct Windows::Networking::PushNotifications::IPushNotificationChannel *v25; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v27[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v28; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v29; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v30[42]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  *(_OWORD *)v27 = 0;
  v28 = 0;
  CMDMPushConfiguration::Populate<MDMPushProvider::TelemetryData>(this);
  wil::ActivityBase<MDMPushProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MDMPushProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v30);
  v30[0] = &MDMPushProvider::InternalRenewActivity::`vftable';
  MDMPushProvider::InternalRenewActivity::StartActivity(
    (MDMPushProvider::InternalRenewActivity *)v30,
    (const struct MDMPushProvider::TelemetryData *)v27);
  psz = 0;
  v22 = 0;
  v25 = 0;
  string = 0;
  v26 = 0;
  if ( *(_DWORD *)this )
  {
    CMDMPushConfiguration::SaveStatus(this, 4u);
    *(_QWORD *)v21 = this;
    LastRenewalTime = CMDMPushConfiguration::GetLastRenewalTime(this, &v29);
    v3 = 0;
    if ( LastRenewalTime != -2147024894 )
      v3 = LastRenewalTime;
    if ( v3 < 0 )
    {
      v5 = 537;
LABEL_7:
      v6 = (unsigned int)v3;
      goto LABEL_8;
    }
    if ( *((_DWORD *)this + 5) )
    {
      v27[2] = 1;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &psz,
        0);
      TestHookUri = CMDMPushConfiguration::GetTestHookUri(v14, &psz, (unsigned __int64 *)&v22);
      v3 = TestHookUri;
      if ( TestHookUri < 0 )
      {
        v6 = (unsigned int)TestHookUri;
        v5 = 563;
        goto LABEL_8;
      }
      v13 = (unsigned __int64)v22;
    }
    else
    {
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v25);
      ChannelObject = CMDMPushConfiguration::GetChannelObject(this, &v25, &v27[3]);
      v3 = ChannelObject;
      if ( ChannelObject < 0 )
      {
        if ( (unsigned int)(ChannelObject + 2147023674) <= 1
          || ChannelObject == -2147418110
          || ChannelObject == -2147023436 )
        {
          goto LABEL_9;
        }
        v6 = (unsigned int)ChannelObject;
        v5 = 546;
LABEL_8:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v5,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
          (const char *)v6,
          v21[0]);
LABEL_9:
        wil::details::unique_storage_wil::details::resource_policy_CMDMPushConfiguration___long____cdecl___CMDMPushConfiguration______anonymous_namespace_::Details::FixPushStatus_wistd::integral_constant_unsigned___int64_0__CMDMPushConfiguration___CMDMPushConfiguration___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_CMDMPushConfiguration___long____cdecl___CMDMPushConfiguration______anonymous_namespace_::Details::FixPushStatus_wistd::integral_constant_unsigned___int64_0__CMDMPushConfiguration___CMDMPushConfiguration___0_std::nullptr_t___(v21);
        goto LABEL_35;
      }
      v8 = *(__int64 (__fastcall **)(struct Windows::Networking::PushNotifications::IPushNotificationChannel *, HSTRING *))(*(_QWORD *)v25 + 48LL);
      string = 0;
      v9 = v8(v25, &string);
      v3 = v9;
      if ( v9 < 0 )
      {
        v6 = (unsigned int)v9;
        v5 = 548;
        goto LABEL_8;
      }
      v10 = (*(__int64 (__fastcall **)(struct Windows::Networking::PushNotifications::IPushNotificationChannel *, unsigned __int64 *))(*(_QWORD *)v25 + 56LL))(
              v25,
              &v26);
      v3 = v10;
      if ( v10 < 0 )
      {
        v6 = (unsigned int)v10;
        v5 = 550;
        goto LABEL_8;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v12 = SysAllocString(StringRawBuffer);
      if ( !v12 )
      {
        v3 = -2147024882;
        v5 = 554;
        goto LABEL_7;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &psz,
        v12);
      v13 = v26;
    }
    v22 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v22,
      0);
    if ( (int)CMDMPushConfiguration::GetCurrentChannel(this, &v22) >= 0 )
      _o__wcsicmp(psz, v22);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
    v16 = CMDMPushConfiguration::SaveChannelURI(this, psz);
    v3 = v16;
    if ( v16 >= 0 )
    {
      v17 = CMDMPushConfiguration::SaveExpiryTime(this, v13);
      v3 = v17;
      if ( v17 >= 0 )
      {
        v18 = CMDMPushConfiguration::SaveStatus(this, 0);
        v3 = v18;
        if ( v18 >= 0 )
        {
          CMDMPushConfiguration::RecordRenewalDuration(this, v19);
          CMDMPushConfiguration::Populate<MDMPushProvider::TelemetryData>(this);
          MDMPushProvider::InternalRenewActivity::Stop(
            (MDMPushProvider::InternalRenewActivity *)v30,
            (const struct MDMPushProvider::TelemetryData *)v27);
          wil::details::unique_storage_wil::details::resource_policy_CMDMPushConfiguration___long____cdecl___CMDMPushConfiguration______anonymous_namespace_::Details::FixPushStatus_wistd::integral_constant_unsigned___int64_0__CMDMPushConfiguration___CMDMPushConfiguration___0_std::nullptr_t___::_unique_storage_wil::details::resource_policy_CMDMPushConfiguration___long____cdecl___CMDMPushConfiguration______anonymous_namespace_::Details::FixPushStatus_wistd::integral_constant_unsigned___int64_0__CMDMPushConfiguration___CMDMPushConfiguration___0_std::nullptr_t___(v21);
          v3 = 0;
          goto LABEL_35;
        }
        v6 = (unsigned int)v18;
        v5 = 592;
      }
      else
      {
        v6 = (unsigned int)v17;
        v5 = 590;
      }
    }
    else
    {
      v6 = (unsigned int)v16;
      v5 = 588;
    }
    goto LABEL_8;
  }
  v3 = -2147483634;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x20A,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
    (const char *)0x8000000ELL,
    v21[0]);
LABEL_35:
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v25);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
  MDMPushProvider::InternalRenewActivity::~InternalRenewActivity((MDMPushProvider::InternalRenewActivity *)v30);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800c9a24  mov     [rsp-8+arg_8], rbx
0x1800c9a29  mov     [rsp-8+arg_10], rsi
0x1800c9a2e  push    rbp
0x1800c9a2f  push    rdi
0x1800c9a30  push    r14
0x1800c9a32  lea     rbp, [rsp-0E0h]
0x1800c9a3a  sub     rsp, 1E0h
0x1800c9a41  mov     rax, cs:__security_cookie
0x1800c9a48  xor     rax, rsp
0x1800c9a4b  mov     [rbp+0F0h+var_20], rax
0x1800c9a52  mov     rdi, rcx
0x1800c9a55  xorps   xmm0, xmm0
0x1800c9a58  movups  xmmword ptr [rsp+1F0h+var_1A0], xmm0
0x1800c9a5d  movups  [rsp+1F0h+var_190], xmm0
0x1800c9a62  lea     rdx, [rsp+1F0h+var_1A0]
0x1800c9a67  call    ??$Populate@UTelemetryData@MDMPushProvider@@@CMDMPushConfiguration@@AEAAXPEAUTelemetryData@MDMPushProvider@@@Z; CMDMPushConfiguration::Populate<MDMPushProvider::TelemetryData>(MDMPushProvider::TelemetryData *)
0x1800c9a6c  nop
0x1800c9a6d  lea     rdx, aInternalrenewa; "InternalRenewActivity"
0x1800c9a74  lea     rcx, [rbp+0F0h+var_170]; struct wil::details::IFailureCallback *
0x1800c9a78  call    ??0?$ActivityBase@VMDMPushProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MDMPushProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MDMPushProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800c9a7d  lea     rax, ??_7InternalRenewActivity@MDMPushProvider@@6B@; const MDMPushProvider::InternalRenewActivity::`vftable'
0x1800c9a84  mov     [rbp+0F0h+var_170], rax
0x1800c9a88  lea     rdx, [rsp+1F0h+var_1A0]; struct MDMPushProvider::TelemetryData *
0x1800c9a8d  lea     rcx, [rbp+0F0h+var_170]; this
0x1800c9a91  call    ?StartActivity@InternalRenewActivity@MDMPushProvider@@QEAAXAEBUTelemetryData@2@@Z; MDMPushProvider::InternalRenewActivity::StartActivity(MDMPushProvider::TelemetryData const &)
0x1800c9a96  nop
0x1800c9a97  mov     [rsp+1F0h+psz], 0
0x1800c9aa0  mov     [rsp+1F0h+var_1C8], 0
0x1800c9aa9  mov     [rsp+1F0h+var_1B0], 0
0x1800c9ab2  mov     [rsp+1F0h+string], 0
0x1800c9abb  mov     [rsp+1F0h+var_1A8], 0
0x1800c9ac4  cmp     dword ptr [rdi], 0
0x1800c9ac7  jnz     short loc_1800C9AEE
0x1800c9ac9  mov     rcx, [rbp+0F8h]; this
0x1800c9ad0  mov     ebx, 8000000Eh
0x1800c9ad5  mov     r9d, ebx; char *
0x1800c9ad8  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x1800c9adf  mov     edx, 20Ah; void *
0x1800c9ae4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9ae9  jmp     loc_1800C9D79
0x1800c9aee  mov     edx, 4; unsigned int
0x1800c9af3  mov     rcx, rdi; this
0x1800c9af6  call    ?SaveStatus@CMDMPushConfiguration@@QEAAJK@Z; CMDMPushConfiguration::SaveStatus(ulong)
0x1800c9afb  mov     qword ptr [rsp+1F0h+var_1D0], rdi; int
0x1800c9b00  lea     rdx, [rsp+1F0h+var_180]; unsigned __int64 *
0x1800c9b05  mov     rcx, rdi; this
0x1800c9b08  call    ?GetLastRenewalTime@CMDMPushConfiguration@@QEAAJPEA_K@Z; CMDMPushConfiguration::GetLastRenewalTime(unsigned __int64 *)
0x1800c9b0d  xor     ebx, ebx
0x1800c9b0f  cmp     eax, 80070002h
0x1800c9b14  cmovnz  ebx, eax
0x1800c9b17  test    ebx, ebx
0x1800c9b19  jns     short loc_1800C9B46
0x1800c9b1b  mov     edx, 219h; void *
0x1800c9b20  mov     r9d, ebx; char *
0x1800c9b23  mov     rcx, [rbp+0F8h]; this
0x1800c9b2a  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x1800c9b31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9b36  nop
0x1800c9b37  lea     rcx, [rsp+1F0h+var_1D0]
0x1800c9b3c  call    wil__details__unique_storage_wil__details__resource_policy_CMDMPushConfiguration___long____cdecl___CMDMPushConfiguration______anonymous_namespace___Details__FixPushStatus_wistd__integral_constant_unsigned___int64_0__CMDMPushConfiguration___CMDMPushConfiguration___0_std__nullptr_t______unique_storage_wil__details__resource_policy_CMDMPushConfiguration___long____cdecl___CMDMPushConfiguration______anonymous_namespace___Details__FixPushStatus_wistd__integral_constant_unsigned___int64_0__CMDMPushConfiguration___CMDMPushConfiguration___0_std__nullptr_t___
0x1800c9b41  jmp     loc_1800C9D79
0x1800c9b46  cmp     dword ptr [rdi+14h], 0
0x1800c9b4a  jnz     loc_1800C9C6D
0x1800c9b50  lea     rcx, [rsp+1F0h+var_1B0]
0x1800c9b55  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c9b5a  lea     r8, [rsp+1F0h+var_1A0+0Ch]; unsigned int *
0x1800c9b5f  lea     rdx, [rsp+1F0h+var_1B0]; struct Windows::Networking::PushNotifications::IPushNotificationChannel **
0x1800c9b64  mov     rcx, rdi; this
0x1800c9b67  call    ?GetChannelObject@CMDMPushConfiguration@@AEAAJPEAPEAUIPushNotificationChannel@PushNotifications@Networking@Windows@@PEAI@Z; CMDMPushConfiguration::GetChannelObject(Windows::Networking::PushNotifications::IPushNotificationChannel * *,uint *)
0x1800c9b6c  mov     ebx, eax
0x1800c9b6e  test    eax, eax
0x1800c9b70  jns     short loc_1800C9B95
0x1800c9b72  lea     ecx, [rax+7FF8FB3Ah]
0x1800c9b78  cmp     ecx, 1
0x1800c9b7b  jbe     short loc_1800C9B37
0x1800c9b7d  cmp     eax, 80010002h
0x1800c9b82  jz      short loc_1800C9B37
0x1800c9b84  cmp     eax, 800705B4h
0x1800c9b89  jz      short loc_1800C9B37
0x1800c9b8b  mov     r9d, eax
0x1800c9b8e  mov     edx, 222h
0x1800c9b93  jmp     short loc_1800C9B23
0x1800c9b95  mov     rsi, [rsp+1F0h+var_1B0]
0x1800c9b9a  mov     rax, [rsi]
0x1800c9b9d  mov     r14, [rax+30h]
0x1800c9ba1  mov     rbx, [rsp+1F0h+string]
0x1800c9ba6  test    rbx, rbx
0x1800c9ba9  jz      short loc_1800C9BCE
0x1800c9bab  lea     rcx, [rsp+1F0h+var_1C8]; this
0x1800c9bb0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800c9bb5  mov     rcx, rbx; string
0x1800c9bb8  call    cs:__imp_WindowsDeleteString
0x1800c9bbf  nop     dword ptr [rax+rax+00h]
0x1800c9bc4  lea     rcx, [rsp+1F0h+var_1C8]; this
0x1800c9bc9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800c9bce  mov     [rsp+1F0h+string], 0
0x1800c9bd7  lea     rdx, [rsp+1F0h+string]
0x1800c9bdc  mov     rcx, rsi
0x1800c9bdf  mov     rax, r14
0x1800c9be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9be7  mov     ebx, eax
0x1800c9be9  test    eax, eax
0x1800c9beb  jns     short loc_1800C9BFA
0x1800c9bed  mov     r9d, eax
0x1800c9bf0  mov     edx, 224h
0x1800c9bf5  jmp     loc_1800C9B23
0x1800c9bfa  mov     rcx, [rsp+1F0h+var_1B0]
0x1800c9bff  mov     rax, [rcx]
0x1800c9c02  lea     rdx, [rsp+1F0h+var_1A8]
0x1800c9c07  mov     rax, [rax+38h]
0x1800c9c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9c10  mov     ebx, eax
0x1800c9c12  test    eax, eax
0x1800c9c14  jns     short loc_1800C9C23
0x1800c9c16  mov     r9d, eax
0x1800c9c19  mov     edx, 226h
0x1800c9c1e  jmp     loc_1800C9B23
0x1800c9c23  xor     edx, edx; length
0x1800c9c25  mov     rcx, [rsp+1F0h+string]; string
0x1800c9c2a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c9c31  nop     dword ptr [rax+rax+00h]
0x1800c9c36  mov     rcx, rax; psz
0x1800c9c39  call    cs:__imp_SysAllocString
0x1800c9c40  nop     dword ptr [rax+rax+00h]
0x1800c9c45  test    rax, rax
0x1800c9c48  jnz     short loc_1800C9C59
0x1800c9c4a  mov     ebx, 8007000Eh
0x1800c9c4f  mov     edx, 22Ah
0x1800c9c54  jmp     loc_1800C9B20
0x1800c9c59  mov     rdx, rax
0x1800c9c5c  lea     rcx, [rsp+1F0h+psz]
0x1800c9c61  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c9c66  mov     rsi, [rsp+1F0h+var_1A8]
0x1800c9c6b  jmp     short loc_1800C9CA8
0x1800c9c6d  mov     [rsp+1F0h+var_1A0+8], 1
0x1800c9c75  xor     edx, edx
0x1800c9c77  lea     rcx, [rsp+1F0h+psz]
0x1800c9c7c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c9c81  lea     r8, [rsp+1F0h+var_1C8]; unsigned __int64 *
0x1800c9c86  lea     rdx, [rsp+1F0h+psz]; unsigned __int16 **
0x1800c9c8b  call    ?GetTestHookUri@CMDMPushConfiguration@@AEAAJPEAPEAGPEA_K@Z; CMDMPushConfiguration::GetTestHookUri(ushort * *,unsigned __int64 *)
0x1800c9c90  mov     ebx, eax
0x1800c9c92  test    eax, eax
0x1800c9c94  jns     short loc_1800C9CA3
0x1800c9c96  mov     r9d, eax
0x1800c9c99  mov     edx, 233h
0x1800c9c9e  jmp     loc_1800C9B23
0x1800c9ca3  mov     rsi, [rsp+1F0h+var_1C8]
0x1800c9ca8  mov     [rsp+1F0h+var_1C8], 0
0x1800c9cb1  xor     edx, edx
0x1800c9cb3  lea     rcx, [rsp+1F0h+var_1C8]
0x1800c9cb8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c9cbd  lea     rdx, [rsp+1F0h+var_1C8]; unsigned __int16 **
0x1800c9cc2  mov     rcx, rdi; this
0x1800c9cc5  call    ?GetCurrentChannel@CMDMPushConfiguration@@QEAAJPEAPEAG@Z; CMDMPushConfiguration::GetCurrentChannel(ushort * *)
0x1800c9cca  test    eax, eax
0x1800c9ccc  js      short loc_1800C9CE4
0x1800c9cce  mov     rdx, [rsp+1F0h+var_1C8]
0x1800c9cd3  mov     rcx, [rsp+1F0h+psz]
0x1800c9cd8  call    cs:__imp__o__wcsicmp
0x1800c9cdf  nop     dword ptr [rax+rax+00h]
0x1800c9ce4  lea     rcx, [rsp+1F0h+var_1C8]
0x1800c9ce9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c9cee  mov     rdx, [rsp+1F0h+psz]; psz
0x1800c9cf3  mov     rcx, rdi; this
0x1800c9cf6  call    ?SaveChannelURI@CMDMPushConfiguration@@AEAAJPEBG@Z; CMDMPushConfiguration::SaveChannelURI(ushort const *)
0x1800c9cfb  mov     ebx, eax
0x1800c9cfd  test    eax, eax
0x1800c9cff  jns     short loc_1800C9D0E
0x1800c9d01  mov     r9d, eax
0x1800c9d04  mov     edx, 24Ch
0x1800c9d09  jmp     loc_1800C9B23
0x1800c9d0e  mov     rdx, rsi; unsigned __int64
0x1800c9d11  mov     rcx, rdi; this
0x1800c9d14  call    ?SaveExpiryTime@CMDMPushConfiguration@@AEAAJ_K@Z; CMDMPushConfiguration::SaveExpiryTime(unsigned __int64)
0x1800c9d19  mov     ebx, eax
0x1800c9d1b  test    eax, eax
0x1800c9d1d  jns     short loc_1800C9D2C
0x1800c9d1f  mov     r9d, eax
0x1800c9d22  mov     edx, 24Eh
0x1800c9d27  jmp     loc_1800C9B23
0x1800c9d2c  xor     edx, edx; unsigned int
0x1800c9d2e  mov     rcx, rdi; this
0x1800c9d31  call    ?SaveStatus@CMDMPushConfiguration@@QEAAJK@Z; CMDMPushConfiguration::SaveStatus(ulong)
0x1800c9d36  mov     ebx, eax
0x1800c9d38  test    eax, eax
0x1800c9d3a  jns     short loc_1800C9D49
0x1800c9d3c  mov     r9d, eax
0x1800c9d3f  mov     edx, 250h
0x1800c9d44  jmp     loc_1800C9B23
0x1800c9d49  mov     rcx, rdi; this
0x1800c9d4c  call    ?RecordRenewalDuration@CMDMPushConfiguration@@AEAAX_K@Z; CMDMPushConfiguration::RecordRenewalDuration(unsigned __int64)
0x1800c9d51  lea     rdx, [rsp+1F0h+var_1A0]
0x1800c9d56  mov     rcx, rdi; this
0x1800c9d59  call    ??$Populate@UTelemetryData@MDMPushProvider@@@CMDMPushConfiguration@@AEAAXPEAUTelemetryData@MDMPushProvider@@@Z; CMDMPushConfiguration::Populate<MDMPushProvider::TelemetryData>(MDMPushProvider::TelemetryData *)
0x1800c9d5e  lea     rdx, [rsp+1F0h+var_1A0]; struct MDMPushProvider::TelemetryData *
0x1800c9d63  lea     rcx, [rbp+0F0h+var_170]; this
0x1800c9d67  call    ?Stop@InternalRenewActivity@MDMPushProvider@@QEAAXAEBUTelemetryData@2@@Z; MDMPushProvider::InternalRenewActivity::Stop(MDMPushProvider::TelemetryData const &)
0x1800c9d6c  nop
0x1800c9d6d  lea     rcx, [rsp+1F0h+var_1D0]
0x1800c9d72  call    wil__details__unique_storage_wil__details__resource_policy_CMDMPushConfiguration___long____cdecl___CMDMPushConfiguration______anonymous_namespace___Details__FixPushStatus_wistd__integral_constant_unsigned___int64_0__CMDMPushConfiguration___CMDMPushConfiguration___0_std__nullptr_t______unique_storage_wil__details__resource_policy_CMDMPushConfiguration___long____cdecl___CMDMPushConfiguration______anonymous_namespace___Details__FixPushStatus_wistd__integral_constant_unsigned___int64_0__CMDMPushConfiguration___CMDMPushConfiguration___0_std__nullptr_t___
0x1800c9d77  xor     ebx, ebx
0x1800c9d79  lea     rcx, [rsp+1F0h+string]; this
0x1800c9d7e  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800c9d83  nop
0x1800c9d84  lea     rcx, [rsp+1F0h+var_1B0]
0x1800c9d89  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800c9d8e  nop
0x1800c9d8f  lea     rcx, [rsp+1F0h+psz]
0x1800c9d94  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c9d99  nop
0x1800c9d9a  lea     rcx, [rbp+0F0h+var_170]; this
0x1800c9d9e  call    ??1InternalRenewActivity@MDMPushProvider@@QEAA@XZ; MDMPushProvider::InternalRenewActivity::~InternalRenewActivity(void)
0x1800c9da3  mov     eax, ebx
0x1800c9da5  mov     rcx, [rbp+0F0h+var_20]
0x1800c9dac  xor     rcx, rsp; StackCookie
0x1800c9daf  call    __security_check_cookie
0x1800c9db4  lea     r11, [rsp+1F0h+var_10]
0x1800c9dbc  mov     rbx, [r11+28h]
0x1800c9dc0  mov     rsi, [r11+30h]
0x1800c9dc4  mov     rsp, r11
0x1800c9dc7  pop     r14
0x1800c9dc9  pop     rdi
0x1800c9dca  pop     rbp
0x1800c9dcb  retn
```
