# ExpeditedUpdateWUTask::BeginAsyncExpeditedUpdateSearch(IUpdateSearcher *,void *,ISearchJob * *)

- ea: `0x180073adc`
- end: `0x180073d12`
- name: `?BeginAsyncExpeditedUpdateSearch@ExpeditedUpdateWUTask@@AEAAJPEAUIUpdateSearcher@@PEAXPEAPEAUISearchJob@@@Z`
- size: `566`
- prototype: `int(ExpeditedUpdateWUTask *__hidden this, struct IUpdateSearcher *, void *, struct ISearchJob **)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180072ef0`

## callees

- `0x180007bbc`
- `0x180008544`
- `0x18001ea00`
- `0x1800235c8`
- `0x18002f39c`
- `0x180046c9c`
- `0x180072a30`
- `0x180073adc`
- `0x180073d68`
- `0x1800759a0`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073bf0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073bf0`
- `OLEAUT32!__imp_VariantInit` at `0x180073c6a`
- `OLEAUT32!__imp_VariantInit` at `0x180073c6a`
- `OLEAUT32!__imp_VariantClear` at `0x180073cd3`
- `OLEAUT32!__imp_VariantClear` at `0x180073ce2`
- `OLEAUT32!__imp_VariantClear` at `0x180073cd3`
- `OLEAUT32!__imp_VariantClear` at `0x180073ce2`

## string_xrefs

- `0x180073c70`: `ExpeditedUpdateWUTask scanning.`
- `0x180073b3c`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180073b70`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180073c11`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180073cbd`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180073c35`: `OOBEUpdateStarted`
- `0x180073be2`: `SOFTWARE\Microsoft\Windows\CurrentVersion\OOBE\Updates`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ExpeditedUpdateWUTask::BeginAsyncExpeditedUpdateSearch(
        ExpeditedUpdateWUTask *this,
        struct IUpdateSearcher *a2,
        void *a3,
        struct ISearchJob **a4)
{
  int v4; // edi
  int updated; // eax
  ExpeditedUpdateWUTask *v7; // rcx
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // rdx
  LSTATUS v11; // eax
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  int v15; // eax
  int dwOptions; // [rsp+20h] [rbp-29h]
  int dwOptionsa; // [rsp+20h] [rbp-29h]
  __int64 v19; // [rsp+50h] [rbp+7h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp+Fh] BYREF
  VARIANTARG v21; // [rsp+70h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  unsigned __int16 *v23; // [rsp+B0h] [rbp+67h] BYREF
  void *v24; // [rsp+C0h] [rbp+77h] BYREF
  HKEY phkResult; // [rsp+C8h] [rbp+7Fh] BYREF

  v24 = a3;
  v4 = (int)a4;
  *a4 = 0;
  v19 = 0;
  v23 = (unsigned __int16 *)*((_QWORD *)this + 74);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  updated = Microsoft::WRL::Details::MakeAndInitialize<COOBEExpeditedUpdateWUCompletionCallback,ISearchCompletedCallback,void * &,INamedPropertyStore *>(
              &v19,
              &v24,
              (struct INamedPropertyStore **)&v23);
  v8 = updated;
  if ( updated >= 0 )
  {
    v23 = 0;
    v9 = ExpeditedUpdateWUTask::CreateExpeditedUpdateSearchCriteria(v7, &v23);
    v8 = v9;
    if ( v9 >= 0 )
    {
      LOBYTE(v10) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NDUPOobeSeekerLifeSpan>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_Servicing_NDUPOobeSeekerLifeSpan>::GetImpl'::`2'::impl,
        v10);
      phkResult = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &phkResult,
        0);
      v11 = RegCreateKeyExW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Updates",
              0,
              0,
              1u,
              0xF003Fu,
              0,
              &phkResult,
              0);
      v8 = v11;
      if ( v11 > 0 )
        v8 = (unsigned __int16)v11 | 0x80070000;
      if ( (v8 & 0x80000000) == 0 )
      {
        v14 = SHRegSetDWORD(phkResult, 0, L"OOBEUpdateStarted", 1u);
        v8 = v14;
        if ( v14 >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
          pvarg.vt = 0;
          VariantInit(&pvarg);
          UnattendLogW(0, L"ExpeditedUpdateWUTask scanning.");
          v21 = pvarg;
          v15 = ((__int64 (__fastcall *)(struct IUpdateSearcher *, unsigned __int16 *, __int64, VARIANTARG *))a2->lpVtbl->BeginSearch)(
                  a2,
                  v23,
                  v19,
                  &v21);
          v8 = v15;
          if ( v15 >= 0 )
          {
            VariantClear(&pvarg);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
            v8 = 0;
            goto LABEL_16;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9D,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
            (const char *)(unsigned int)v15,
            v4);
          VariantClear(&pvarg);
          goto LABEL_5;
        }
        v12 = (unsigned int)v14;
        v13 = 147;
      }
      else
      {
        v12 = v8;
        v13 = 146;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
        (const char *)v12,
        dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8A,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
        (const char *)(unsigned int)v9,
        dwOptions);
    }
LABEL_5:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x87,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
    (const char *)(unsigned int)updated,
    dwOptions);
LABEL_16:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  return v8;
}

```

## disassembly

```asm
0x180073adc  mov     [rsp-8+arg_8], rbx
0x180073ae1  mov     [rsp-8+arg_10], r8
0x180073ae6  push    rbp
0x180073ae7  push    rsi
0x180073ae8  push    rdi
0x180073ae9  lea     rbp, [rsp-47h]
0x180073aee  sub     rsp, 90h
0x180073af5  mov     rdi, r9
0x180073af8  mov     rsi, rdx
0x180073afb  mov     qword ptr [r9], 0
0x180073b02  mov     [rbp+57h+var_50], 0
0x180073b0a  mov     rax, [rcx+250h]
0x180073b11  mov     [rbp+57h+arg_0], rax
0x180073b15  lea     rcx, [rbp+57h+var_50]
0x180073b19  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180073b1e  lea     r8, [rbp+57h+arg_0]
0x180073b22  lea     rdx, [rbp+57h+arg_10]
0x180073b26  lea     rcx, [rbp+57h+var_50]
0x180073b2a  call    ??$MakeAndInitialize@VCOOBEExpeditedUpdateWUCompletionCallback@@UISearchCompletedCallback@@AEAPEAXPEAUINamedPropertyStore@@@Details@WRL@Microsoft@@YAJPEAPEAUISearchCompletedCallback@@AEAPEAX$$QEAPEAUINamedPropertyStore@@@Z; Microsoft::WRL::Details::MakeAndInitialize<COOBEExpeditedUpdateWUCompletionCallback,ISearchCompletedCallback,void * &,INamedPropertyStore *>(ISearchCompletedCallback * *,void * &,INamedPropertyStore * &&)
0x180073b2f  mov     ebx, eax
0x180073b31  test    eax, eax
0x180073b33  jns     short loc_180073B52
0x180073b35  mov     rcx, [rbp+5Fh]; this
0x180073b39  mov     r9d, eax; char *
0x180073b3c  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180073b43  mov     edx, 87h; void *
0x180073b48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073b4d  jmp     loc_180073CF4
0x180073b52  mov     [rbp+57h+arg_0], 0
0x180073b5a  lea     rdx, [rbp+57h+arg_0]; unsigned __int16 **
0x180073b5e  call    ?CreateExpeditedUpdateSearchCriteria@ExpeditedUpdateWUTask@@AEAAJPEAPEAG@Z; ExpeditedUpdateWUTask::CreateExpeditedUpdateSearchCriteria(ushort * *)
0x180073b63  mov     ebx, eax
0x180073b65  test    eax, eax
0x180073b67  jns     short loc_180073B90
0x180073b69  mov     rcx, [rbp+5Fh]; this
0x180073b6d  mov     r9d, eax; char *
0x180073b70  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180073b77  mov     edx, 8Ah; void *
0x180073b7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073b81  nop
0x180073b82  lea     rcx, [rbp+57h+arg_0]
0x180073b86  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180073b8b  jmp     loc_180073CF4
0x180073b90  mov     dl, 1
0x180073b92  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NDUPOobeSeekerLifeSpan@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NDUPOobeSeekerLifeSpan@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NDUPOobeSeekerLifeSpan> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NDUPOobeSeekerLifeSpan>::GetImpl(void)'::`2'::impl
0x180073b99  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NDUPOobeSeekerLifeSpan@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NDUPOobeSeekerLifeSpan>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180073b9e  mov     [rbp+57h+arg_18], 0
0x180073ba6  xor     edx, edx
0x180073ba8  lea     rcx, [rbp+57h+arg_18]
0x180073bac  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180073bb1  mov     [rsp+0A0h+lpdwDisposition], 0; lpdwDisposition
0x180073bba  lea     rax, [rbp+57h+arg_18]
0x180073bbe  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180073bc3  mov     [rsp+0A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180073bcc  mov     [rsp+0A0h+samDesired], 0F003Fh; samDesired
0x180073bd4  mov     [rsp+0A0h+dwOptions], 1; int
0x180073bdc  xor     r9d, r9d; lpClass
0x180073bdf  xor     r8d, r8d; Reserved
0x180073be2  lea     rdx, aSoftwareMicros_35; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180073be9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180073bf0  call    cs:__imp_RegCreateKeyExW
0x180073bf6  mov     ebx, eax
0x180073bf8  test    eax, eax
0x180073bfa  jle     short loc_180073C05
0x180073bfc  movzx   ebx, ax
0x180073bff  or      ebx, 80070000h
0x180073c05  test    ebx, ebx
0x180073c07  jns     short loc_180073C2F
0x180073c09  mov     r9d, ebx; char *
0x180073c0c  mov     edx, 92h; void *
0x180073c11  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180073c18  mov     rcx, [rbp+5Fh]; this
0x180073c1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073c21  lea     rcx, [rbp+57h+arg_18]
0x180073c25  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180073c2a  jmp     loc_180073B82
0x180073c2f  mov     r9d, 1; unsigned int
0x180073c35  lea     r8, aOobeupdatestar; "OOBEUpdateStarted"
0x180073c3c  xor     edx, edx; unsigned __int16 *
0x180073c3e  mov     rcx, [rbp+57h+arg_18]; HKEY
0x180073c42  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180073c47  mov     ebx, eax
0x180073c49  test    eax, eax
0x180073c4b  jns     short loc_180073C57
0x180073c4d  mov     r9d, eax
0x180073c50  mov     edx, 93h
0x180073c55  jmp     short loc_180073C11
0x180073c57  lea     rcx, [rbp+57h+arg_18]
0x180073c5b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180073c60  xor     eax, eax
0x180073c62  mov     word ptr [rbp+57h+pvarg], ax
0x180073c66  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180073c6a  call    cs:__imp_VariantInit
0x180073c70  lea     rdx, aExpeditedupdat_16; "ExpeditedUpdateWUTask scanning."
0x180073c77  xor     ecx, ecx
0x180073c79  call    UnattendLogW
0x180073c7e  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180073c82  movaps  [rbp+57h+var_30], xmm0
0x180073c86  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180073c8b  movsd   [rbp+57h+var_20], xmm1
0x180073c90  mov     rax, [rsi]
0x180073c93  mov     qword ptr [rsp+0A0h+dwOptions], rdi; int
0x180073c98  lea     r9, [rbp+57h+var_30]
0x180073c9c  mov     r8, [rbp+57h+var_50]
0x180073ca0  mov     rdx, [rbp+57h+arg_0]
0x180073ca4  mov     rcx, rsi
0x180073ca7  mov     rax, [rax+78h]
0x180073cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073cb0  mov     ebx, eax
0x180073cb2  test    eax, eax
0x180073cb4  jns     short loc_180073CDE
0x180073cb6  mov     rcx, [rbp+5Fh]; this
0x180073cba  mov     r9d, eax; char *
0x180073cbd  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180073cc4  mov     edx, 9Dh; void *
0x180073cc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073cce  nop
0x180073ccf  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180073cd3  call    cs:__imp_VariantClear
0x180073cd9  jmp     loc_180073B82
0x180073cde  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180073ce2  call    cs:__imp_VariantClear
0x180073ce8  nop
0x180073ce9  lea     rcx, [rbp+57h+arg_0]
0x180073ced  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180073cf2  xor     ebx, ebx
0x180073cf4  lea     rcx, [rbp+57h+var_50]
0x180073cf8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180073cfd  mov     eax, ebx
0x180073cff  mov     rbx, [rsp+0A0h+arg_8]
0x180073d07  add     rsp, 90h
0x180073d0e  pop     rdi
0x180073d0f  pop     rsi
0x180073d10  pop     rbp
0x180073d11  retn
```
