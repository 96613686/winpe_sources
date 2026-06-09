# cdp::ActivityStoreInfoWatcherLet::ActivityStoreInfoWatcherLet(unsigned __int64)

- ea: `0x1803048d0`
- end: `0x180304ab3`
- name: `??0ActivityStoreInfoWatcherLet@cdp@@QEAA@_K@Z`
- size: `483`
- prototype: `__int64 __fastcall(cdp::ActivityStoreInfoWatcherLet *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802fe430`

## callees

- `0x18001ce80`
- `0x18002bbe8`
- `0x1800624cc`
- `0x180093e18`
- `0x180114c58`
- `0x180178310`
- `0x180197f04`
- `0x1803048d0`

## import_xrefs

- `combase!__imp_CoCreateInstanceAsUser` at `0x1803049c1`
- `combase!__imp_CoCreateInstanceAsUser` at `0x1803049c1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1803049ac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1803049ac`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180304a2e`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180304a2e`

## string_xrefs

- `0x180304a4d`: `Failed to store CDPComActivityStoreInfoWatcher in AgileRef`
- `0x1803049e0`: `Failed to CoCreateAsUser CDPComActivityStoreInfoWatcher`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
cdp::ActivityStoreInfoWatcherLet *__fastcall cdp::ActivityStoreInfoWatcherLet::ActivityStoreInfoWatcherLet(
        cdp::ActivityStoreInfoWatcherLet *this,
        __int64 a2)
{
  shared *v4; // rcx
  HRESULT v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rax
  cdp::ActivityStoreInfoWatcherLet **v8; // rax
  cdp::ActivityStoreInfoWatcherLet **v9; // rdi
  LPVOID v10; // rsi
  int AgileReference; // eax
  __int64 v12; // rax
  const char *v14; // [rsp+30h] [rbp-50h] BYREF
  int v15; // [rsp+38h] [rbp-48h]
  _BYTE v16[64]; // [rsp+40h] [rbp-40h] BYREF
  cdp::ActivityStoreInfoWatcherLet *v17; // [rsp+B0h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+B8h] [rbp+38h] BYREF
  char *v19; // [rsp+C0h] [rbp+40h] BYREF

  v17 = this;
  cdp::unknown<ICDPActivityStoreInfoWatcher,>::unknown<ICDPActivityStoreInfoWatcher,>();
  *(_QWORD *)this = &cdp::ActivityStoreInfoWatcherLet::`vftable';
  *((_QWORD *)this + 4) = 0;
  shared::CallbackInvocationGroup<ICDPUserActivitySettingsCallback>::CallbackInvocationGroup<ICDPUserActivitySettingsCallback>((char *)this + 40);
  *(_OWORD *)((char *)this + 216) = 0;
  *(_OWORD *)((char *)this + 232) = 0;
  *(_OWORD *)((char *)this + 248) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_DWORD *)this + 66) = -1;
  *((_DWORD *)this + 48) = 2;
  *((_DWORD *)this + 67) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = a2;
  ppv = 0;
  if ( shared::IsRunningInContainerOS(v4) )
    v5 = CoCreateInstance(
           &GUID_f83e1fe0_be37_4462_a7e9_ec05d25a9bd4,
           0,
           0x100004u,
           &GUID_6f4670bb_cdf1_4fb7_8d5c_46c9200dfbf3,
           &ppv);
  else
    v5 = CoCreateInstanceAsUser(
           &GUID_f83e1fe0_be37_4462_a7e9_ec05d25a9bd4,
           0,
           1048580,
           a2,
           &GUID_6f4670bb_cdf1_4fb7_8d5c_46c9200dfbf3,
           &ppv);
  if ( v5 < 0 )
  {
    v14 = ".\\activitystoreinfowatcherlet.cpp";
    v15 = 23;
    v7 = cdp::MakeException<cdp::hresult_exception,>(
           v16,
           &v14,
           (unsigned int)v5,
           "Failed to CoCreateAsUser CDPComActivityStoreInfoWatcher");
    cdp::CdpThrow<cdp::hresult_exception>(&v14, v7);
  }
  v19 = (char *)this + 32;
  v8 = (cdp::ActivityStoreInfoWatcherLet **)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(
                                              &v19,
                                              v6,
                                              (unsigned int)v5);
  v9 = v8;
  v10 = ppv;
  if ( ppv )
  {
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v8);
    AgileReference = RoGetAgileReference(0, &GUID_6f4670bb_cdf1_4fb7_8d5c_46c9200dfbf3, v10, v9);
    if ( AgileReference < 0 )
    {
      v14 = ".\\activitystoreinfowatcherlet.cpp";
      v15 = 25;
      v12 = cdp::MakeException<cdp::hresult_exception,>(
              v16,
              &v14,
              (unsigned int)AgileReference,
              "Failed to store CDPComActivityStoreInfoWatcher in AgileRef");
      cdp::CdpThrow<cdp::hresult_exception>(&v14, v12);
    }
  }
  else
  {
    v19 = 0;
    v17 = *v8;
    *v8 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v19);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
  return this;
}

```

## disassembly

```asm
0x1803048d0  mov     [rsp-28h+arg_0], rcx
0x1803048d5  push    rbp
0x1803048d6  push    rbx
0x1803048d7  push    rsi
0x1803048d8  push    rdi
0x1803048d9  push    r14
0x1803048db  mov     rbp, rsp
0x1803048de  sub     rsp, 80h
0x1803048e5  mov     rsi, rdx
0x1803048e8  mov     rbx, rcx
0x1803048eb  call    ??0?$unknown@VICDPActivityStoreInfoWatcher@@$$V@cdp@@QEAA@XZ; cdp::unknown<ICDPActivityStoreInfoWatcher,>::unknown<ICDPActivityStoreInfoWatcher,>(void)
0x1803048f0  nop
0x1803048f1  lea     rax, ??_7ActivityStoreInfoWatcherLet@cdp@@6B@; const cdp::ActivityStoreInfoWatcherLet::`vftable'
0x1803048f8  mov     [rbx], rax
0x1803048fb  lea     rdi, [rbx+20h]
0x1803048ff  mov     qword ptr [rdi], 0
0x180304906  lea     rcx, [rbx+28h]
0x18030490a  call    ??0?$CallbackInvocationGroup@VICDPUserActivitySettingsCallback@@@shared@@QEAA@XZ; shared::CallbackInvocationGroup<ICDPUserActivitySettingsCallback>::CallbackInvocationGroup<ICDPUserActivitySettingsCallback>(void)
0x18030490f  nop
0x180304910  xorps   xmm0, xmm0
0x180304913  movups  xmmword ptr [rbx+0D8h], xmm0
0x18030491a  movups  xmmword ptr [rbx+0E8h], xmm0
0x180304921  movups  xmmword ptr [rbx+0F8h], xmm0
0x180304928  mov     qword ptr [rbx+0C8h], 0
0x180304933  mov     qword ptr [rbx+0D0h], 0
0x18030493e  mov     dword ptr [rbx+108h], 0FFFFFFFFh
0x180304948  mov     dword ptr [rbx+0C0h], 2
0x180304952  mov     dword ptr [rbx+10Ch], 0
0x18030495c  mov     qword ptr [rbx+110h], 0
0x180304967  mov     qword ptr [rbx+118h], 0
0x180304972  mov     [rbx+120h], rsi
0x180304979  mov     [rbp+arg_8], 0
0x180304981  call    ?IsRunningInContainerOS@shared@@YA_NXZ; shared::IsRunningInContainerOS(void)
0x180304986  lea     r14, _GUID_6f4670bb_cdf1_4fb7_8d5c_46c9200dfbf3
0x18030498d  xor     edx, edx; pUnkOuter
0x18030498f  mov     r8d, 100004h; dwClsContext
0x180304995  lea     rcx, _GUID_f83e1fe0_be37_4462_a7e9_ec05d25a9bd4; rclsid
0x18030499c  test    al, al
0x18030499e  lea     rax, [rbp+arg_8]
0x1803049a2  jz      short loc_1803049B4
0x1803049a4  mov     [rsp+80h+ppv], rax; ppv
0x1803049a9  mov     r9, r14; riid
0x1803049ac  call    cs:__imp_CoCreateInstance
0x1803049b2  jmp     short loc_1803049C7
0x1803049b4  mov     [rsp+80h+var_58], rax
0x1803049b9  mov     [rsp+80h+ppv], r14
0x1803049be  mov     r9, rsi
0x1803049c1  call    cs:__imp_CoCreateInstanceAsUser
0x1803049c7  mov     r8d, eax
0x1803049ca  test    eax, eax
0x1803049cc  jns     short loc_180304A02
0x1803049ce  lea     rax, aActivitystorei_1; ".\\activitystoreinfowatcherlet.cpp"
0x1803049d5  mov     [rbp+var_50], rax
0x1803049d9  mov     [rbp+var_48], 17h
0x1803049e0  lea     r9, aFailedToCocrea_7; "Failed to CoCreateAsUser CDPComActivity"...
0x1803049e7  lea     rdx, [rbp+var_50]
0x1803049eb  lea     rcx, [rbp+var_40]
0x1803049ef  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1803049f4  nop
0x1803049f5  mov     rdx, rax
0x1803049f8  lea     rcx, [rbp+var_50]
0x1803049fc  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x180304a02  mov     [rbp+arg_10], rdi
0x180304a06  lea     rcx, [rbp+arg_10]
0x180304a0a  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x180304a0f  mov     rdi, rax
0x180304a12  mov     rsi, [rbp+arg_8]
0x180304a16  test    rsi, rsi
0x180304a19  jz      short loc_180304A6F
0x180304a1b  mov     rcx, rax
0x180304a1e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180304a23  mov     r9, rdi
0x180304a26  mov     r8, rsi
0x180304a29  mov     rdx, r14
0x180304a2c  xor     ecx, ecx
0x180304a2e  call    cs:__imp_RoGetAgileReference
0x180304a34  mov     r8d, eax
0x180304a37  test    eax, eax
0x180304a39  jns     short loc_180304A98
0x180304a3b  lea     rax, aActivitystorei_1; ".\\activitystoreinfowatcherlet.cpp"
0x180304a42  mov     [rbp+var_50], rax
0x180304a46  mov     [rbp+var_48], 19h
0x180304a4d  lea     r9, aFailedToStoreC; "Failed to store CDPComActivityStoreInfo"...
0x180304a54  lea     rdx, [rbp+var_50]
0x180304a58  lea     rcx, [rbp+var_40]
0x180304a5c  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x180304a61  nop
0x180304a62  mov     rdx, rax
0x180304a65  lea     rcx, [rbp+var_50]
0x180304a69  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x180304a6f  mov     [rbp+arg_10], 0
0x180304a77  mov     rax, [rax]
0x180304a7a  mov     [rbp+arg_0], rax
0x180304a7e  mov     qword ptr [rdi], 0
0x180304a85  lea     rcx, [rbp+arg_0]
0x180304a89  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180304a8e  lea     rcx, [rbp+arg_10]
0x180304a92  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180304a97  nop
0x180304a98  lea     rcx, [rbp+arg_8]
0x180304a9c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180304aa1  nop
0x180304aa2  mov     rax, rbx
0x180304aa5  add     rsp, 80h
0x180304aac  pop     r14
0x180304aae  pop     rdi
0x180304aaf  pop     rsi
0x180304ab0  pop     rbx
0x180304ab1  pop     rbp
0x180304ab2  retn
```
