# FirewallCspNode::GetStatus(ulong *)

- ea: `0x1800a3bc0`
- end: `0x1800a3eb6`
- name: `?GetStatus@FirewallCspNode@@AEAAJPEAK@Z`
- size: `758`
- prototype: `__int64 __fastcall(FirewallCspNode *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a3ec0`

## callees

- `0x18000caf4`
- `0x18000d4d4`
- `0x1800a2cb0`
- `0x1800a2d40`
- `0x1800a3bc0`
- `0x1800dadec`
- `0x180107010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a3c0d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a3c0d`
- `OLEAUT32!__imp_VariantInit` at `0x1800a3caf`
- `OLEAUT32!__imp_VariantInit` at `0x1800a3caf`
- `OLEAUT32!__imp_VariantClear` at `0x1800a3d06`
- `OLEAUT32!__imp_VariantClear` at `0x1800a3d66`
- `OLEAUT32!__imp_VariantClear` at `0x1800a3dda`
- `OLEAUT32!__imp_VariantClear` at `0x1800a3e3c`
- `OLEAUT32!__imp_VariantClear` at `0x1800a3e5c`
- `OLEAUT32!__imp_VariantClear` at `0x1800a3d06`
- `OLEAUT32!__imp_VariantClear` at `0x1800a3d66`
- `OLEAUT32!__imp_VariantClear` at `0x1800a3dda`
- `OLEAUT32!__imp_VariantClear` at `0x1800a3e3c`
- `OLEAUT32!__imp_VariantClear` at `0x1800a3e5c`
- `DMCmnUtils!DmEnableTask` at `0x1800a3d97`
- `DMCmnUtils!DmEnableTask` at `0x1800a3e0b`
- `DMCmnUtils!DmEnableTask` at `0x1800a3d97`
- `DMCmnUtils!DmEnableTask` at `0x1800a3e0b`

## string_xrefs

- `0x1800a3d84`: `Wsc Startup event listener created by enrollment client`
- `0x1800a3df8`: `Wsc Startup event listener created by enrollment client`
- `0x1800a3c06`: `WscGetSecurityProviderHealth`
- `0x1800a3c7a`: `WSC_SECURITY_PROVIDER_FIREWALL`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FirewallCspNode::GetStatus(FirewallCspNode *this, unsigned int *a2)
{
  HMODULE v4; // rcx
  __int64 result; // rax
  __int64 (*ProcAddress)(void); // rax
  __int64 v7; // rdx
  int v8; // ecx
  int v9; // ebx
  const char *v10; // r9
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // eax
  unsigned int v20; // ebx
  int v21; // [rsp+20h] [rbp-38h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v24; // [rsp+70h] [rbp+18h] BYREF

  v4 = (HMODULE)*((_QWORD *)this + 16);
  if ( !v4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\firewallcspnode.cpp",
      (const char *)0x86000011LL,
      v21);
    return 2248146961LL;
  }
  ProcAddress = GetProcAddress(v4, "WscGetSecurityProviderHealth");
  if ( !ProcAddress )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\firewallcspnode.cpp",
      (const char *)0x86000011LL,
      v21);
    return 2248146961LL;
  }
  try
  {
    v9 = ProcAddress();
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x4000) != 0 )
      McTemplateU0zdd_EventWriteTransfer(v8, v7, (unsigned int)L"WSC_SECURITY_PROVIDER_FIREWALL", -1, v9);
    if ( v9 == 1 )
    {
      LOBYTE(v7) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_WscStartupTask>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_WscStartupTask>::GetImpl'::`2'::impl,
        v7);
      v24 = 0;
      VariantInit(&pvarg);
      v11 = *((_QWORD *)this + 2);
      v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 48LL);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v24);
      v13 = v12(v11, &v24);
      v14 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6B,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\firewallcspnode.cpp",
          (const char *)(unsigned int)v13,
          v21);
        VariantClear(&pvarg);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v24);
        return v14;
      }
      v15 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, VARIANTARG *))(*(_QWORD *)v24 + 32LL))(
              v24,
              L"OMADM::AccountID",
              &pvarg);
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6C,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\firewallcspnode.cpp",
          (const char *)(unsigned int)v15,
          v21);
        VariantClear(&pvarg);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v24);
        return v16;
      }
      if ( (int)DmEnableTask(
                  L"\\Microsoft\\Windows\\EnterpriseMgmt",
                  pvarg.bstrVal,
                  L"Wsc Startup event listener created by enrollment client") >= 0 )
        goto LABEL_17;
      v17 = ScheduleAlertTask(pvarg.llVal);
      v18 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x70,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\firewallcspnode.cpp",
          (const char *)(unsigned int)v17,
          v21);
        VariantClear(&pvarg);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v24);
        return v18;
      }
      v19 = DmEnableTask(
              L"\\Microsoft\\Windows\\EnterpriseMgmt",
              pvarg.bstrVal,
              L"Wsc Startup event listener created by enrollment client");
      v20 = v19;
      if ( v19 >= 0 )
      {
LABEL_17:
        VariantClear(&pvarg);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v24);
        result = 2147943462LL;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x71,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\firewallcspnode.cpp",
          (const char *)(unsigned int)v19,
          v21);
        VariantClear(&pvarg);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v24);
        result = v20;
      }
    }
    else if ( v9 >= 0 )
    {
      *a2 = -1;
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\firewallcspnode.cpp",
        (const char *)(unsigned int)v9,
        v21);
      result = (unsigned int)v9;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x7A,
                           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\firewallcspnode.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1800a3bc0  mov     [rsp+arg_8], rbx
0x1800a3bc5  mov     [rsp+arg_18], rsi
0x1800a3bca  push    rdi
0x1800a3bcb  sub     rsp, 50h
0x1800a3bcf  mov     rsi, rdx
0x1800a3bd2  mov     rdi, rcx
0x1800a3bd5  mov     rcx, [rcx+80h]; hModule
0x1800a3bdc  test    rcx, rcx
0x1800a3bdf  jnz     short loc_1800A3C06
0x1800a3be1  mov     rcx, [rsp+58h]; this
0x1800a3be6  mov     ebx, 86000011h
0x1800a3beb  mov     r9d, ebx; char *
0x1800a3bee  lea     r8, aOnecoreuapAdmi_106; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800a3bf5  mov     edx, 56h ; 'V'; void *
0x1800a3bfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3bff  mov     eax, ebx
0x1800a3c01  jmp     loc_1800A3EA5
0x1800a3c06  lea     rdx, aWscgetsecurity; "WscGetSecurityProviderHealth"
0x1800a3c0d  call    cs:__imp_GetProcAddress
0x1800a3c14  nop     dword ptr [rax+rax+00h]
0x1800a3c19  test    rax, rax
0x1800a3c1c  jnz     short loc_1800A3C41
0x1800a3c1e  mov     rcx, [rsp+58h]; this
0x1800a3c23  mov     ebx, 86000011h
0x1800a3c28  mov     r9d, ebx; char *
0x1800a3c2b  lea     r8, aOnecoreuapAdmi_106; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800a3c32  lea     edx, [rax+5Bh]; void *
0x1800a3c35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3c3a  mov     eax, ebx
0x1800a3c3c  jmp     loc_1800A3EA5
0x1800a3c41  mov     [rsp+58h+arg_0], 0FFFFFFFFh
0x1800a3c49  lea     rdx, [rsp+58h+arg_0]
0x1800a3c4e  mov     ecx, 1
0x1800a3c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3c58  mov     ebx, eax
0x1800a3c5a  mov     eax, [rsp+58h+arg_0]
0x1800a3c5e  test    ebx, ebx
0x1800a3c60  jnz     short loc_1800A3C6A
0x1800a3c62  test    eax, eax
0x1800a3c64  jz      loc_1800A3E9B
0x1800a3c6a  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits+1, 40h
0x1800a3c71  jz      short loc_1800A3C8A
0x1800a3c73  mov     [rsp+58h+var_38], ebx; int
0x1800a3c77  mov     r9d, eax
0x1800a3c7a  lea     r8, aWscSecurityPro_0; "WSC_SECURITY_PROVIDER_FIREWALL"
0x1800a3c81  call    McTemplateU0zdd_EventWriteTransfer
0x1800a3c86  mov     eax, [rsp+58h+arg_0]
0x1800a3c8a  cmp     ebx, 1
0x1800a3c8d  jnz     loc_1800A3E7A
0x1800a3c93  mov     dl, bl
0x1800a3c95  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WscStartupTask@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WscStartupTask@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WscStartupTask> `wil::Feature<__WilFeatureTraits_Feature_WscStartupTask>::GetImpl(void)'::`2'::impl
0x1800a3c9c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WscStartupTask@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WscStartupTask>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800a3ca1  mov     [rsp+58h+arg_10], 0
0x1800a3caa  lea     rcx, [rsp+58h+pvarg]; pvarg
0x1800a3caf  call    cs:__imp_VariantInit
0x1800a3cb6  nop     dword ptr [rax+rax+00h]
0x1800a3cbb  nop
0x1800a3cbc  mov     rdi, [rdi+10h]
0x1800a3cc0  mov     rax, [rdi]
0x1800a3cc3  mov     rbx, [rax+30h]
0x1800a3cc7  lea     rcx, [rsp+58h+arg_10]
0x1800a3ccc  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800a3cd1  lea     rdx, [rsp+58h+arg_10]
0x1800a3cd6  mov     rcx, rdi
0x1800a3cd9  mov     rax, rbx
0x1800a3cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3ce1  mov     ebx, eax
0x1800a3ce3  test    eax, eax
0x1800a3ce5  jns     short loc_1800A3D24
0x1800a3ce7  mov     rcx, [rsp+58h]; this
0x1800a3cec  mov     r9d, eax; char *
0x1800a3cef  lea     r8, aOnecoreuapAdmi_106; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800a3cf6  mov     edx, 6Bh ; 'k'; void *
0x1800a3cfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3d00  nop
0x1800a3d01  lea     rcx, [rsp+58h+pvarg]; pvarg
0x1800a3d06  call    cs:__imp_VariantClear
0x1800a3d0d  nop     dword ptr [rax+rax+00h]
0x1800a3d12  nop
0x1800a3d13  lea     rcx, [rsp+58h+arg_10]
0x1800a3d18  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800a3d1d  mov     eax, ebx
0x1800a3d1f  jmp     loc_1800A3EA5
0x1800a3d24  mov     rcx, [rsp+58h+arg_10]
0x1800a3d29  mov     rax, [rcx]
0x1800a3d2c  lea     r8, [rsp+58h+pvarg]
0x1800a3d31  lea     rdx, aOmadmAccountid_0; "OMADM::AccountID"
0x1800a3d38  mov     rax, [rax+20h]
0x1800a3d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3d41  mov     ebx, eax
0x1800a3d43  test    eax, eax
0x1800a3d45  jns     short loc_1800A3D84
0x1800a3d47  mov     rcx, [rsp+58h]; this
0x1800a3d4c  mov     r9d, eax; char *
0x1800a3d4f  lea     r8, aOnecoreuapAdmi_106; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800a3d56  mov     edx, 6Ch ; 'l'; void *
0x1800a3d5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3d60  nop
0x1800a3d61  lea     rcx, [rsp+58h+pvarg]; pvarg
0x1800a3d66  call    cs:__imp_VariantClear
0x1800a3d6d  nop     dword ptr [rax+rax+00h]
0x1800a3d72  nop
0x1800a3d73  lea     rcx, [rsp+58h+arg_10]
0x1800a3d78  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800a3d7d  mov     eax, ebx
0x1800a3d7f  jmp     loc_1800A3EA5
0x1800a3d84  lea     r8, aWscStartupEven; "Wsc Startup event listener created by e"...
0x1800a3d8b  mov     rdx, qword ptr [rsp+58h+pvarg+8]
0x1800a3d90  lea     rcx, aMicrosoftWindo_3; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x1800a3d97  call    cs:__imp_?DmEnableTask@@YAJPEBG00@Z; DmEnableTask(ushort const *,ushort const *,ushort const *)
0x1800a3d9e  nop     dword ptr [rax+rax+00h]
0x1800a3da3  test    eax, eax
0x1800a3da5  jns     loc_1800A3E57
0x1800a3dab  mov     rcx, qword ptr [rsp+58h+pvarg+8]
0x1800a3db0  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x1800a3db5  mov     ebx, eax
0x1800a3db7  test    eax, eax
0x1800a3db9  jns     short loc_1800A3DF8
0x1800a3dbb  mov     rcx, [rsp+58h]; this
0x1800a3dc0  mov     r9d, eax; char *
0x1800a3dc3  lea     r8, aOnecoreuapAdmi_106; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800a3dca  mov     edx, 70h ; 'p'; void *
0x1800a3dcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3dd4  nop
0x1800a3dd5  lea     rcx, [rsp+58h+pvarg]; pvarg
0x1800a3dda  call    cs:__imp_VariantClear
0x1800a3de1  nop     dword ptr [rax+rax+00h]
0x1800a3de6  nop
0x1800a3de7  lea     rcx, [rsp+58h+arg_10]
0x1800a3dec  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800a3df1  mov     eax, ebx
0x1800a3df3  jmp     loc_1800A3EA5
0x1800a3df8  lea     r8, aWscStartupEven; "Wsc Startup event listener created by e"...
0x1800a3dff  mov     rdx, qword ptr [rsp+58h+pvarg+8]
0x1800a3e04  lea     rcx, aMicrosoftWindo_3; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x1800a3e0b  call    cs:__imp_?DmEnableTask@@YAJPEBG00@Z; DmEnableTask(ushort const *,ushort const *,ushort const *)
0x1800a3e12  nop     dword ptr [rax+rax+00h]
0x1800a3e17  mov     ebx, eax
0x1800a3e19  test    eax, eax
0x1800a3e1b  jns     short loc_1800A3E57
0x1800a3e1d  mov     rcx, [rsp+58h]; this
0x1800a3e22  mov     r9d, eax; char *
0x1800a3e25  lea     r8, aOnecoreuapAdmi_106; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800a3e2c  mov     edx, 71h ; 'q'; void *
0x1800a3e31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3e36  nop
0x1800a3e37  lea     rcx, [rsp+58h+pvarg]; pvarg
0x1800a3e3c  call    cs:__imp_VariantClear
0x1800a3e43  nop     dword ptr [rax+rax+00h]
0x1800a3e48  nop
0x1800a3e49  lea     rcx, [rsp+58h+arg_10]
0x1800a3e4e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800a3e53  mov     eax, ebx
0x1800a3e55  jmp     short loc_1800A3EA5
0x1800a3e57  lea     rcx, [rsp+58h+pvarg]; pvarg
0x1800a3e5c  call    cs:__imp_VariantClear
0x1800a3e63  nop     dword ptr [rax+rax+00h]
0x1800a3e68  nop
0x1800a3e69  lea     rcx, [rsp+58h+arg_10]
0x1800a3e6e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800a3e73  mov     eax, 80070426h
0x1800a3e78  jmp     short loc_1800A3EA5
0x1800a3e7a  test    ebx, ebx
0x1800a3e7c  jns     short loc_1800A3E9B
0x1800a3e7e  mov     rcx, [rsp+58h]; this
0x1800a3e83  mov     r9d, ebx; char *
0x1800a3e86  lea     r8, aOnecoreuapAdmi_106; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800a3e8d  mov     edx, 77h ; 'w'; void *
0x1800a3e92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3e97  mov     eax, ebx
0x1800a3e99  jmp     short loc_1800A3EA5
0x1800a3e9b  mov     [rsi], eax
0x1800a3e9d  xor     eax, eax
0x1800a3e9f  jmp     short loc_1800A3EA5
0x1800a3ea1  mov     eax, [rsp+58h+arg_0]
0x1800a3ea5  mov     rbx, [rsp+58h+arg_8]
0x1800a3eaa  mov     rsi, [rsp+58h+arg_18]
0x1800a3eaf  add     rsp, 50h
0x1800a3eb3  pop     rdi
0x1800a3eb4  retn
```
