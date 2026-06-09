# AntivirusCspNode::GetStatus(ulong *)

- ea: `0x1800a27c0`
- end: `0x1800a2ab6`
- name: `?GetStatus@AntivirusCspNode@@AEAAJPEAK@Z`
- size: `758`
- prototype: `__int64 __fastcall(AntivirusCspNode *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a2ac0`

## callees

- `0x18000caf4`
- `0x18000d4d4`
- `0x1800a27c0`
- `0x1800a2cb0`
- `0x1800a2d40`
- `0x1800dadec`
- `0x180107010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a280d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a280d`
- `OLEAUT32!__imp_VariantInit` at `0x1800a28af`
- `OLEAUT32!__imp_VariantInit` at `0x1800a28af`
- `OLEAUT32!__imp_VariantClear` at `0x1800a2906`
- `OLEAUT32!__imp_VariantClear` at `0x1800a2966`
- `OLEAUT32!__imp_VariantClear` at `0x1800a29da`
- `OLEAUT32!__imp_VariantClear` at `0x1800a2a3c`
- `OLEAUT32!__imp_VariantClear` at `0x1800a2a5c`
- `OLEAUT32!__imp_VariantClear` at `0x1800a2906`
- `OLEAUT32!__imp_VariantClear` at `0x1800a2966`
- `OLEAUT32!__imp_VariantClear` at `0x1800a29da`
- `OLEAUT32!__imp_VariantClear` at `0x1800a2a3c`
- `OLEAUT32!__imp_VariantClear` at `0x1800a2a5c`
- `DMCmnUtils!DmEnableTask` at `0x1800a2997`
- `DMCmnUtils!DmEnableTask` at `0x1800a2a0b`
- `DMCmnUtils!DmEnableTask` at `0x1800a2997`
- `DMCmnUtils!DmEnableTask` at `0x1800a2a0b`

## string_xrefs

- `0x1800a2984`: `Wsc Startup event listener created by enrollment client`
- `0x1800a29f8`: `Wsc Startup event listener created by enrollment client`
- `0x1800a287a`: `WSC_SECURITY_PROVIDER_ANTIVIRUS`
- `0x1800a2806`: `WscGetSecurityProviderHealth`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AntivirusCspNode::GetStatus(AntivirusCspNode *this, unsigned int *a2)
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
      (void *)0x58,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\antiviruscspnode.cpp",
      (const char *)0x86000011LL,
      v21);
    return 2248146961LL;
  }
  ProcAddress = GetProcAddress(v4, "WscGetSecurityProviderHealth");
  if ( !ProcAddress )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\antiviruscspnode.cpp",
      (const char *)0x86000011LL,
      v21);
    return 2248146961LL;
  }
  try
  {
    v9 = ProcAddress();
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x4000) != 0 )
      McTemplateU0zdd_EventWriteTransfer(v8, v7, (unsigned int)L"WSC_SECURITY_PROVIDER_ANTIVIRUS", -1, v9);
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
          (void *)0x6D,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\antiviruscspnode.cpp",
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
          (void *)0x6E,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\antiviruscspnode.cpp",
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
          (void *)0x72,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\antiviruscspnode.cpp",
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
          (void *)0x73,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\antiviruscspnode.cpp",
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
        (void *)0x78,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\antiviruscspnode.cpp",
        (const char *)(unsigned int)v9,
        v21);
      result = (unsigned int)v9;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x7C,
                           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\antiviruscspnode.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1800a27c0  mov     [rsp+arg_8], rbx
0x1800a27c5  mov     [rsp+arg_18], rsi
0x1800a27ca  push    rdi
0x1800a27cb  sub     rsp, 50h
0x1800a27cf  mov     rsi, rdx
0x1800a27d2  mov     rdi, rcx
0x1800a27d5  mov     rcx, [rcx+80h]; hModule
0x1800a27dc  test    rcx, rcx
0x1800a27df  jnz     short loc_1800A2806
0x1800a27e1  mov     rcx, [rsp+58h]; this
0x1800a27e6  mov     ebx, 86000011h
0x1800a27eb  mov     r9d, ebx; char *
0x1800a27ee  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800a27f5  mov     edx, 58h ; 'X'; void *
0x1800a27fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a27ff  mov     eax, ebx
0x1800a2801  jmp     loc_1800A2AA5
0x1800a2806  lea     rdx, aWscgetsecurity; "WscGetSecurityProviderHealth"
0x1800a280d  call    cs:__imp_GetProcAddress
0x1800a2814  nop     dword ptr [rax+rax+00h]
0x1800a2819  test    rax, rax
0x1800a281c  jnz     short loc_1800A2841
0x1800a281e  mov     rcx, [rsp+58h]; this
0x1800a2823  mov     ebx, 86000011h
0x1800a2828  mov     r9d, ebx; char *
0x1800a282b  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800a2832  lea     edx, [rax+5Dh]; void *
0x1800a2835  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a283a  mov     eax, ebx
0x1800a283c  jmp     loc_1800A2AA5
0x1800a2841  mov     [rsp+58h+arg_0], 0FFFFFFFFh
0x1800a2849  lea     rdx, [rsp+58h+arg_0]
0x1800a284e  mov     ecx, 4
0x1800a2853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2858  mov     ebx, eax
0x1800a285a  mov     eax, [rsp+58h+arg_0]
0x1800a285e  test    ebx, ebx
0x1800a2860  jnz     short loc_1800A286A
0x1800a2862  test    eax, eax
0x1800a2864  jz      loc_1800A2A9B
0x1800a286a  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits+1, 40h
0x1800a2871  jz      short loc_1800A288A
0x1800a2873  mov     [rsp+58h+var_38], ebx; int
0x1800a2877  mov     r9d, eax
0x1800a287a  lea     r8, aWscSecurityPro_2; "WSC_SECURITY_PROVIDER_ANTIVIRUS"
0x1800a2881  call    McTemplateU0zdd_EventWriteTransfer
0x1800a2886  mov     eax, [rsp+58h+arg_0]
0x1800a288a  cmp     ebx, 1
0x1800a288d  jnz     loc_1800A2A7A
0x1800a2893  mov     dl, bl
0x1800a2895  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WscStartupTask@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WscStartupTask@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WscStartupTask> `wil::Feature<__WilFeatureTraits_Feature_WscStartupTask>::GetImpl(void)'::`2'::impl
0x1800a289c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WscStartupTask@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WscStartupTask>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800a28a1  mov     [rsp+58h+arg_10], 0
0x1800a28aa  lea     rcx, [rsp+58h+pvarg]; pvarg
0x1800a28af  call    cs:__imp_VariantInit
0x1800a28b6  nop     dword ptr [rax+rax+00h]
0x1800a28bb  nop
0x1800a28bc  mov     rdi, [rdi+10h]
0x1800a28c0  mov     rax, [rdi]
0x1800a28c3  mov     rbx, [rax+30h]
0x1800a28c7  lea     rcx, [rsp+58h+arg_10]
0x1800a28cc  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800a28d1  lea     rdx, [rsp+58h+arg_10]
0x1800a28d6  mov     rcx, rdi
0x1800a28d9  mov     rax, rbx
0x1800a28dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a28e1  mov     ebx, eax
0x1800a28e3  test    eax, eax
0x1800a28e5  jns     short loc_1800A2924
0x1800a28e7  mov     rcx, [rsp+58h]; this
0x1800a28ec  mov     r9d, eax; char *
0x1800a28ef  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800a28f6  mov     edx, 6Dh ; 'm'; void *
0x1800a28fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2900  nop
0x1800a2901  lea     rcx, [rsp+58h+pvarg]; pvarg
0x1800a2906  call    cs:__imp_VariantClear
0x1800a290d  nop     dword ptr [rax+rax+00h]
0x1800a2912  nop
0x1800a2913  lea     rcx, [rsp+58h+arg_10]
0x1800a2918  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800a291d  mov     eax, ebx
0x1800a291f  jmp     loc_1800A2AA5
0x1800a2924  mov     rcx, [rsp+58h+arg_10]
0x1800a2929  mov     rax, [rcx]
0x1800a292c  lea     r8, [rsp+58h+pvarg]
0x1800a2931  lea     rdx, aOmadmAccountid_0; "OMADM::AccountID"
0x1800a2938  mov     rax, [rax+20h]
0x1800a293c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2941  mov     ebx, eax
0x1800a2943  test    eax, eax
0x1800a2945  jns     short loc_1800A2984
0x1800a2947  mov     rcx, [rsp+58h]; this
0x1800a294c  mov     r9d, eax; char *
0x1800a294f  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800a2956  mov     edx, 6Eh ; 'n'; void *
0x1800a295b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2960  nop
0x1800a2961  lea     rcx, [rsp+58h+pvarg]; pvarg
0x1800a2966  call    cs:__imp_VariantClear
0x1800a296d  nop     dword ptr [rax+rax+00h]
0x1800a2972  nop
0x1800a2973  lea     rcx, [rsp+58h+arg_10]
0x1800a2978  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800a297d  mov     eax, ebx
0x1800a297f  jmp     loc_1800A2AA5
0x1800a2984  lea     r8, aWscStartupEven; "Wsc Startup event listener created by e"...
0x1800a298b  mov     rdx, qword ptr [rsp+58h+pvarg+8]
0x1800a2990  lea     rcx, aMicrosoftWindo_3; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x1800a2997  call    cs:__imp_?DmEnableTask@@YAJPEBG00@Z; DmEnableTask(ushort const *,ushort const *,ushort const *)
0x1800a299e  nop     dword ptr [rax+rax+00h]
0x1800a29a3  test    eax, eax
0x1800a29a5  jns     loc_1800A2A57
0x1800a29ab  mov     rcx, qword ptr [rsp+58h+pvarg+8]
0x1800a29b0  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x1800a29b5  mov     ebx, eax
0x1800a29b7  test    eax, eax
0x1800a29b9  jns     short loc_1800A29F8
0x1800a29bb  mov     rcx, [rsp+58h]; this
0x1800a29c0  mov     r9d, eax; char *
0x1800a29c3  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800a29ca  mov     edx, 72h ; 'r'; void *
0x1800a29cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a29d4  nop
0x1800a29d5  lea     rcx, [rsp+58h+pvarg]; pvarg
0x1800a29da  call    cs:__imp_VariantClear
0x1800a29e1  nop     dword ptr [rax+rax+00h]
0x1800a29e6  nop
0x1800a29e7  lea     rcx, [rsp+58h+arg_10]
0x1800a29ec  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800a29f1  mov     eax, ebx
0x1800a29f3  jmp     loc_1800A2AA5
0x1800a29f8  lea     r8, aWscStartupEven; "Wsc Startup event listener created by e"...
0x1800a29ff  mov     rdx, qword ptr [rsp+58h+pvarg+8]
0x1800a2a04  lea     rcx, aMicrosoftWindo_3; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x1800a2a0b  call    cs:__imp_?DmEnableTask@@YAJPEBG00@Z; DmEnableTask(ushort const *,ushort const *,ushort const *)
0x1800a2a12  nop     dword ptr [rax+rax+00h]
0x1800a2a17  mov     ebx, eax
0x1800a2a19  test    eax, eax
0x1800a2a1b  jns     short loc_1800A2A57
0x1800a2a1d  mov     rcx, [rsp+58h]; this
0x1800a2a22  mov     r9d, eax; char *
0x1800a2a25  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800a2a2c  mov     edx, 73h ; 's'; void *
0x1800a2a31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2a36  nop
0x1800a2a37  lea     rcx, [rsp+58h+pvarg]; pvarg
0x1800a2a3c  call    cs:__imp_VariantClear
0x1800a2a43  nop     dword ptr [rax+rax+00h]
0x1800a2a48  nop
0x1800a2a49  lea     rcx, [rsp+58h+arg_10]
0x1800a2a4e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800a2a53  mov     eax, ebx
0x1800a2a55  jmp     short loc_1800A2AA5
0x1800a2a57  lea     rcx, [rsp+58h+pvarg]; pvarg
0x1800a2a5c  call    cs:__imp_VariantClear
0x1800a2a63  nop     dword ptr [rax+rax+00h]
0x1800a2a68  nop
0x1800a2a69  lea     rcx, [rsp+58h+arg_10]
0x1800a2a6e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800a2a73  mov     eax, 80070426h
0x1800a2a78  jmp     short loc_1800A2AA5
0x1800a2a7a  test    ebx, ebx
0x1800a2a7c  jns     short loc_1800A2A9B
0x1800a2a7e  mov     rcx, [rsp+58h]; this
0x1800a2a83  mov     r9d, ebx; char *
0x1800a2a86  lea     r8, aOnecoreuapAdmi_75; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800a2a8d  mov     edx, 78h ; 'x'; void *
0x1800a2a92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2a97  mov     eax, ebx
0x1800a2a99  jmp     short loc_1800A2AA5
0x1800a2a9b  mov     [rsi], eax
0x1800a2a9d  xor     eax, eax
0x1800a2a9f  jmp     short loc_1800A2AA5
0x1800a2aa1  mov     eax, [rsp+58h+arg_0]
0x1800a2aa5  mov     rbx, [rsp+58h+arg_8]
0x1800a2aaa  mov     rsi, [rsp+58h+arg_18]
0x1800a2aaf  add     rsp, 50h
0x1800a2ab3  pop     rdi
0x1800a2ab4  retn
```
