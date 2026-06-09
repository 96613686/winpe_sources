# shared::WNSNotificationProvider::CreateWpnPlatform(void)

- ea: `0x18005a380`
- end: `0x18005a4ed`
- name: `?CreateWpnPlatform@WNSNotificationProvider@shared@@SA?AV?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@XZ`
- size: `365`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ed6c`
- `0x180057d44`
- `0x1801e0240`

## callees

- `0x18001ce80`
- `0x1800426fc`
- `0x18005a380`
- `0x1800624cc`
- `0x180114c58`

## import_xrefs

- `combase!__imp_CoCreateInstanceAsUser` at `0x18005a431`
- `combase!__imp_CoCreateInstanceAsUser` at `0x18005a431`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18005a3ad`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18005a3ad`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005a497`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005a497`

## string_xrefs

- `0x18005a3e2`: `Could not get the UserContextToken for the caller`
- `0x18005a451`: `Could not create push notification platform`
- `0x18005a4b3`: `Could not create push notification platform`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID *__fastcall shared::WNSNotificationProvider::CreateWpnPlatform(LPVOID *ppv)
{
  unsigned __int64 *v2; // rdx
  int CallerUserContextToken; // eax
  __int64 v4; // rax
  int InstanceAsUser; // eax
  __int64 v6; // rax
  HRESULT Instance; // eax
  __int64 v8; // rax
  const char *v10; // [rsp+38h] [rbp-48h] BYREF
  int v11; // [rsp+40h] [rbp-40h]
  _BYTE v12[56]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v13; // [rsp+98h] [rbp+18h] BYREF

  *ppv = 0;
  if ( (unsigned __int8)RtlIsMultiUsersInSessionSku() )
  {
    v13 = 0;
    CallerUserContextToken = cdp::GetCallerUserContextToken((cdp *)&v13, v2);
    if ( CallerUserContextToken < 0 )
    {
      v10 = ".\\wnsnotificationprovider.cpp";
      v11 = 419;
      v4 = cdp::MakeException<cdp::hresult_exception,>(
             v12,
             &v10,
             (unsigned int)CallerUserContextToken,
             "Could not get the UserContextToken for the caller");
      cdp::CdpThrow<cdp::hresult_exception>(&v10, v4);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(ppv);
    InstanceAsUser = CoCreateInstanceAsUser(
                       &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
                       0,
                       4,
                       v13,
                       &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
                       ppv);
    if ( InstanceAsUser < 0 )
    {
      v10 = ".\\wnsnotificationprovider.cpp";
      v11 = 423;
      v6 = cdp::MakeException<cdp::hresult_exception,>(
             v12,
             &v10,
             (unsigned int)InstanceAsUser,
             "Could not create push notification platform");
      cdp::CdpThrow<cdp::hresult_exception>(&v10, v6);
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(ppv);
    Instance = CoCreateInstance(
                 &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
                 0,
                 4u,
                 &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
                 ppv);
    if ( Instance < 0 )
    {
      v10 = ".\\wnsnotificationprovider.cpp";
      v11 = 429;
      v8 = cdp::MakeException<cdp::hresult_exception,>(
             v12,
             &v10,
             (unsigned int)Instance,
             "Could not create push notification platform");
      cdp::CdpThrow<cdp::hresult_exception>(&v10, v8);
    }
  }
  return ppv;
}

```

## disassembly

```asm
0x18005a380  mov     [rsp-8+arg_10], rbx
0x18005a385  mov     [rsp-8+arg_0], rcx
0x18005a38a  push    rbp
0x18005a38b  mov     rbp, rsp
0x18005a38e  sub     rsp, 80h
0x18005a395  mov     rbx, rcx
0x18005a398  mov     [rbp+var_50], 0
0x18005a39f  mov     qword ptr [rcx], 0
0x18005a3a6  mov     [rbp+var_50], 1
0x18005a3ad  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18005a3b3  test    al, al
0x18005a3b5  jz      loc_18005A476
0x18005a3bb  mov     [rbp+arg_8], 0
0x18005a3c3  lea     rcx, [rbp+arg_8]; this
0x18005a3c7  call    ?GetCallerUserContextToken@cdp@@YAJAEA_K@Z; cdp::GetCallerUserContextToken(unsigned __int64 &)
0x18005a3cc  test    eax, eax
0x18005a3ce  jns     short loc_18005A407
0x18005a3d0  lea     rcx, aWnsnotificatio_0; ".\\wnsnotificationprovider.cpp"
0x18005a3d7  mov     [rbp+var_48], rcx
0x18005a3db  mov     [rbp+var_40], 1A3h
0x18005a3e2  lea     r9, aCouldNotGetThe; "Could not get the UserContextToken for "...
0x18005a3e9  mov     r8d, eax
0x18005a3ec  lea     rdx, [rbp+var_48]
0x18005a3f0  lea     rcx, [rbp+var_38]
0x18005a3f4  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x18005a3f9  nop
0x18005a3fa  mov     rdx, rax
0x18005a3fd  lea     rcx, [rbp+var_48]
0x18005a401  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18005a407  mov     rcx, rbx
0x18005a40a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005a40f  mov     [rsp+80h+var_58], rbx
0x18005a414  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x18005a41b  mov     [rsp+80h+ppv], r9
0x18005a420  mov     r9, [rbp+arg_8]
0x18005a424  xor     edx, edx
0x18005a426  lea     r8d, [rdx+4]
0x18005a42a  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c
0x18005a431  call    cs:__imp_CoCreateInstanceAsUser
0x18005a437  test    eax, eax
0x18005a439  jns     loc_18005A4D8
0x18005a43f  lea     rcx, aWnsnotificatio_0; ".\\wnsnotificationprovider.cpp"
0x18005a446  mov     [rbp+var_48], rcx
0x18005a44a  mov     [rbp+var_40], 1A7h
0x18005a451  lea     r9, aCouldNotCreate_0; "Could not create push notification plat"...
0x18005a458  mov     r8d, eax
0x18005a45b  lea     rdx, [rbp+var_48]
0x18005a45f  lea     rcx, [rbp+var_38]
0x18005a463  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x18005a468  nop
0x18005a469  mov     rdx, rax
0x18005a46c  lea     rcx, [rbp+var_48]
0x18005a470  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18005a476  mov     rcx, rbx
0x18005a479  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005a47e  mov     [rsp+80h+ppv], rbx; ppv
0x18005a483  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x18005a48a  xor     edx, edx; pUnkOuter
0x18005a48c  lea     r8d, [rdx+4]; dwClsContext
0x18005a490  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x18005a497  call    cs:__imp_CoCreateInstance
0x18005a49d  test    eax, eax
0x18005a49f  jns     short loc_18005A4D8
0x18005a4a1  lea     rcx, aWnsnotificatio_0; ".\\wnsnotificationprovider.cpp"
0x18005a4a8  mov     [rbp+var_48], rcx
0x18005a4ac  mov     [rbp+var_40], 1ADh
0x18005a4b3  lea     r9, aCouldNotCreate_0; "Could not create push notification plat"...
0x18005a4ba  mov     r8d, eax
0x18005a4bd  lea     rdx, [rbp+var_48]
0x18005a4c1  lea     rcx, [rbp+var_38]
0x18005a4c5  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x18005a4ca  nop
0x18005a4cb  mov     rdx, rax
0x18005a4ce  lea     rcx, [rbp+var_48]
0x18005a4d2  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18005a4d8  mov     rax, rbx
0x18005a4db  mov     rbx, [rsp+80h+arg_10]
0x18005a4e3  add     rsp, 80h
0x18005a4ea  pop     rbp
0x18005a4eb  retn
```
