# shared::UserActivitySettingslet::UserActivitySettingslet(unsigned __int64)

- ea: `0x18015e950`
- end: `0x18015eb39`
- name: `??0UserActivitySettingslet@shared@@QEAA@_K@Z`
- size: `489`
- prototype: `__int64 __fastcall(shared::UserActivitySettingslet *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800eebf0`

## callees

- `0x18001ce80`
- `0x18002bbe8`
- `0x1800374e4`
- `0x1800624cc`
- `0x180093e18`
- `0x180114c58`
- `0x18011d8c4`
- `0x18015e950`
- `0x180178310`
- `0x1802e5400`

## import_xrefs

- `combase!__imp_CoCreateInstanceAsUser` at `0x18015ea4e`
- `combase!__imp_CoCreateInstanceAsUser` at `0x18015ea4e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18015ea39`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18015ea39`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18015eab4`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18015eab4`

## string_xrefs

- `0x18015ead3`: `Failed to store CDPComAFSUserSettings in global interface table`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
shared::UserActivitySettingslet *__fastcall shared::UserActivitySettingslet::UserActivitySettingslet(
        shared::UserActivitySettingslet *this,
        __int64 a2)
{
  shared *v4; // rcx
  HRESULT v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rax
  LPVOID v8; // r14
  shared::UserActivitySettingslet **v9; // rax
  shared::UserActivitySettingslet **v10; // rdi
  int AgileReference; // eax
  __int64 v12; // rax
  const char *v14; // [rsp+30h] [rbp-50h] BYREF
  int v15; // [rsp+38h] [rbp-48h]
  _BYTE v16[64]; // [rsp+40h] [rbp-40h] BYREF
  shared::UserActivitySettingslet *v17; // [rsp+B0h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+B8h] [rbp+38h] BYREF
  char *v19; // [rsp+C0h] [rbp+40h] BYREF

  v17 = this;
  cdp::unknown<ICDPUserActivitySettings,>::unknown<ICDPUserActivitySettings,>();
  *(_QWORD *)this = &shared::UserActivitySettingslet::`vftable';
  std::map<enum ActivityFeedOperationScope,enum ActivityFeedOperationState>::map<enum ActivityFeedOperationScope,enum ActivityFeedOperationState>((char *)this + 32);
  shared::CallbackInvocationGroup<ICDPUserActivitySettingsCallback>::CallbackInvocationGroup<ICDPUserActivitySettingsCallback>((char *)this + 48);
  *((_QWORD *)this + 25) = 0;
  *(_OWORD *)((char *)this + 232) = 0;
  *(_OWORD *)((char *)this + 248) = 0;
  *(_OWORD *)((char *)this + 264) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_DWORD *)this + 70) = -1;
  *((_DWORD *)this + 52) = 2;
  *((_DWORD *)this + 71) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = a2;
  ppv = 0;
  if ( shared::IsRunningInContainerOS(v4) )
    v5 = CoCreateInstance(
           &GUID_ac36a05c_fb95_4c7a_868c_a43cc8d2d926,
           0,
           0x100004u,
           &GUID_8255a6da_c295_48c3_a4da_dae510b5c193,
           &ppv);
  else
    v5 = CoCreateInstanceAsUser(
           &GUID_ac36a05c_fb95_4c7a_868c_a43cc8d2d926,
           0,
           1048580,
           a2,
           &GUID_8255a6da_c295_48c3_a4da_dae510b5c193,
           &ppv);
  if ( v5 < 0 )
  {
    v14 = ".\\useractivitysettingslet.cpp";
    v15 = 16;
    v7 = cdp::MakeException<cdp::hresult_exception>(v16, &v14, (unsigned int)v5);
    cdp::CdpThrow<cdp::hresult_exception>(&v14, v7);
  }
  v8 = ppv;
  v19 = (char *)this + 200;
  v9 = (shared::UserActivitySettingslet **)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(
                                             &v19,
                                             v6,
                                             (unsigned int)v5);
  v10 = v9;
  if ( v8 )
  {
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v9);
    AgileReference = RoGetAgileReference(0, &GUID_8255a6da_c295_48c3_a4da_dae510b5c193, v8, v10);
    if ( AgileReference < 0 )
    {
      v14 = ".\\useractivitysettingslet.cpp";
      v15 = 17;
      v12 = cdp::MakeException<cdp::hresult_exception,>(
              v16,
              &v14,
              (unsigned int)AgileReference,
              "Failed to store CDPComAFSUserSettings in global interface table");
      cdp::CdpThrow<cdp::hresult_exception>(&v14, v12);
    }
  }
  else
  {
    v19 = 0;
    v17 = *v9;
    *v9 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v19);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
  return this;
}

```

## disassembly

```asm
0x18015e950  mov     [rsp-28h+arg_0], rcx
0x18015e955  push    rbp
0x18015e956  push    rbx
0x18015e957  push    rsi
0x18015e958  push    rdi
0x18015e959  push    r14
0x18015e95b  mov     rbp, rsp
0x18015e95e  sub     rsp, 80h
0x18015e965  mov     r14, rdx
0x18015e968  mov     rbx, rcx
0x18015e96b  call    ??0?$unknown@VICDPUserActivitySettings@@$$V@cdp@@QEAA@XZ; cdp::unknown<ICDPUserActivitySettings,>::unknown<ICDPUserActivitySettings,>(void)
0x18015e970  nop
0x18015e971  lea     rax, ??_7UserActivitySettingslet@shared@@6B@; const shared::UserActivitySettingslet::`vftable'
0x18015e978  mov     [rbx], rax
0x18015e97b  lea     rcx, [rbx+20h]
0x18015e97f  call    ??0?$map@W4ActivityFeedOperationScope@@W4ActivityFeedOperationState@@U?$less@W4ActivityFeedOperationScope@@@std@@V?$allocator@U?$pair@$$CBW4ActivityFeedOperationScope@@W4ActivityFeedOperationState@@@std@@@4@@std@@QEAA@XZ; std::map<ActivityFeedOperationScope,ActivityFeedOperationState>::map<ActivityFeedOperationScope,ActivityFeedOperationState>(void)
0x18015e984  nop
0x18015e985  lea     rcx, [rbx+30h]
0x18015e989  call    ??0?$CallbackInvocationGroup@VICDPUserActivitySettingsCallback@@@shared@@QEAA@XZ; shared::CallbackInvocationGroup<ICDPUserActivitySettingsCallback>::CallbackInvocationGroup<ICDPUserActivitySettingsCallback>(void)
0x18015e98e  nop
0x18015e98f  lea     rdi, [rbx+0C8h]
0x18015e996  mov     qword ptr [rdi], 0
0x18015e99d  xorps   xmm0, xmm0
0x18015e9a0  movups  xmmword ptr [rbx+0E8h], xmm0
0x18015e9a7  movups  xmmword ptr [rbx+0F8h], xmm0
0x18015e9ae  movups  xmmword ptr [rbx+108h], xmm0
0x18015e9b5  mov     qword ptr [rbx+0D8h], 0
0x18015e9c0  mov     qword ptr [rbx+0E0h], 0
0x18015e9cb  mov     dword ptr [rbx+118h], 0FFFFFFFFh
0x18015e9d5  mov     dword ptr [rbx+0D0h], 2
0x18015e9df  mov     dword ptr [rbx+11Ch], 0
0x18015e9e9  mov     qword ptr [rbx+120h], 0
0x18015e9f4  mov     qword ptr [rbx+128h], 0
0x18015e9ff  mov     [rbx+130h], r14
0x18015ea06  mov     [rbp+arg_8], 0
0x18015ea0e  call    ?IsRunningInContainerOS@shared@@YA_NXZ; shared::IsRunningInContainerOS(void)
0x18015ea13  lea     rsi, _GUID_8255a6da_c295_48c3_a4da_dae510b5c193
0x18015ea1a  xor     edx, edx; pUnkOuter
0x18015ea1c  mov     r8d, 100004h; dwClsContext
0x18015ea22  lea     rcx, _GUID_ac36a05c_fb95_4c7a_868c_a43cc8d2d926; rclsid
0x18015ea29  test    al, al
0x18015ea2b  lea     rax, [rbp+arg_8]
0x18015ea2f  jz      short loc_18015EA41
0x18015ea31  mov     [rsp+80h+ppv], rax; ppv
0x18015ea36  mov     r9, rsi; riid
0x18015ea39  call    cs:__imp_CoCreateInstance
0x18015ea3f  jmp     short loc_18015EA54
0x18015ea41  mov     [rsp+80h+var_58], rax
0x18015ea46  mov     [rsp+80h+ppv], rsi
0x18015ea4b  mov     r9, r14
0x18015ea4e  call    cs:__imp_CoCreateInstanceAsUser
0x18015ea54  mov     r8d, eax
0x18015ea57  test    eax, eax
0x18015ea59  jns     short loc_18015EA88
0x18015ea5b  lea     rax, aUseractivityse; ".\\useractivitysettingslet.cpp"
0x18015ea62  mov     [rbp+var_50], rax
0x18015ea66  mov     [rbp+var_48], 10h
0x18015ea6d  lea     rdx, [rbp+var_50]
0x18015ea71  lea     rcx, [rbp+var_40]
0x18015ea75  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18015ea7a  nop
0x18015ea7b  mov     rdx, rax
0x18015ea7e  lea     rcx, [rbp+var_50]
0x18015ea82  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18015ea88  mov     r14, [rbp+arg_8]
0x18015ea8c  mov     [rbp+arg_10], rdi
0x18015ea90  lea     rcx, [rbp+arg_10]
0x18015ea94  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x18015ea99  mov     rdi, rax
0x18015ea9c  test    r14, r14
0x18015ea9f  jz      short loc_18015EAF5
0x18015eaa1  mov     rcx, rax
0x18015eaa4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18015eaa9  mov     r9, rdi
0x18015eaac  mov     r8, r14
0x18015eaaf  mov     rdx, rsi
0x18015eab2  xor     ecx, ecx
0x18015eab4  call    cs:__imp_RoGetAgileReference
0x18015eaba  mov     r8d, eax
0x18015eabd  test    eax, eax
0x18015eabf  jns     short loc_18015EB1E
0x18015eac1  lea     rax, aUseractivityse; ".\\useractivitysettingslet.cpp"
0x18015eac8  mov     [rbp+var_50], rax
0x18015eacc  mov     [rbp+var_48], 11h
0x18015ead3  lea     r9, aFailedToStoreC_1; "Failed to store CDPComAFSUserSettings i"...
0x18015eada  lea     rdx, [rbp+var_50]
0x18015eade  lea     rcx, [rbp+var_40]
0x18015eae2  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x18015eae7  nop
0x18015eae8  mov     rdx, rax
0x18015eaeb  lea     rcx, [rbp+var_50]
0x18015eaef  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18015eaf5  mov     [rbp+arg_10], 0
0x18015eafd  mov     rax, [rax]
0x18015eb00  mov     [rbp+arg_0], rax
0x18015eb04  mov     qword ptr [rdi], 0
0x18015eb0b  lea     rcx, [rbp+arg_0]
0x18015eb0f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18015eb14  lea     rcx, [rbp+arg_10]
0x18015eb18  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18015eb1d  nop
0x18015eb1e  lea     rcx, [rbp+arg_8]
0x18015eb22  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18015eb27  nop
0x18015eb28  mov     rax, rbx
0x18015eb2b  add     rsp, 80h
0x18015eb32  pop     r14
0x18015eb34  pop     rdi
0x18015eb35  pop     rsi
0x18015eb36  pop     rbx
0x18015eb37  pop     rbp
0x18015eb38  retn
```
