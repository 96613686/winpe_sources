# OneCopilotRemediator::DeleteOneCopilotTaskFromScheduler(void)

- ea: `0x180051a3c`
- end: `0x180051d3a`
- name: `?DeleteOneCopilotTaskFromScheduler@OneCopilotRemediator@@AEAAJXZ`
- size: `766`
- prototype: `__int64 __fastcall(OneCopilotRemediator *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180052a88`

## callees

- `0x180016148`
- `0x180017988`
- `0x180020d88`
- `0x1800516d4`
- `0x180051a3c`
- `0x180053898`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180051a8a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180051a8a`
- `OLEAUT32!__imp_VariantInit` at `0x180051a53`
- `OLEAUT32!__imp_VariantInit` at `0x180051a53`
- `OLEAUT32!__imp_VariantClear` at `0x180051cc8`
- `OLEAUT32!__imp_VariantClear` at `0x180051d02`
- `OLEAUT32!__imp_VariantClear` at `0x180051d24`
- `OLEAUT32!__imp_VariantClear` at `0x180051cc8`
- `OLEAUT32!__imp_VariantClear` at `0x180051d02`
- `OLEAUT32!__imp_VariantClear` at `0x180051d24`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall OneCopilotRemediator::DeleteOneCopilotTaskFromScheduler(OneCopilotRemediator *this)
{
  __int64 v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // r9
  __int64 v5; // rdx
  int v6; // eax
  __int64 *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // eax
  __int64 *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rdx
  LPVOID *ppv; // [rsp+20h] [rbp-79h]
  __int64 v17; // [rsp+30h] [rbp-69h] BYREF
  LPVOID v18; // [rsp+38h] [rbp-61h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-59h] BYREF
  VARIANTARG v20; // [rsp+60h] [rbp-39h] BYREF
  VARIANTARG v21; // [rsp+80h] [rbp-19h] BYREF
  VARIANTARG v22; // [rsp+A0h] [rbp+7h] BYREF
  VARIANTARG v23; // [rsp+C0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  __int64 *v25; // [rsp+100h] [rbp+67h] BYREF
  __int64 v26; // [rsp+108h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+110h] [rbp+77h] BYREF
  __int64 v28; // [rsp+118h] [rbp+7Fh] BYREF

  VariantInit(&pvarg);
  if ( !*((_QWORD *)this + 9) )
  {
    v18 = 0;
    CoCreateInstance(
      &GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd,
      0,
      1u,
      &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
      &v18);
    wil::com_ptr_t<ITaskService,wil::err_returncode_policy>::operator=((char *)this + 72, &v18);
    wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v18);
    v2 = *((_QWORD *)this + 9);
    if ( !v2 )
    {
      v3 = -2147024882;
      v4 = 2147942414LL;
      v5 = 452;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (unsigned int)"shell\\onecore\\desktopshellext\\lib\\onecopilotremediator.cpp",
        (const char *)v4,
        (int)ppv);
LABEL_20:
      VariantClear(&pvarg);
      return v3;
    }
    v20 = pvarg;
    v21 = pvarg;
    v22 = pvarg;
    v23 = pvarg;
    ppv = (LPVOID *)&v20;
    v6 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v2 + 80LL))(
           v2,
           &v23,
           &v22,
           &v21);
    v3 = v6;
    if ( v6 < 0 )
    {
      v4 = (unsigned int)v6;
      v5 = 453;
      goto LABEL_6;
    }
  }
  wil::make_bstr(&v26, L"\\OneCopilot");
  v25 = 0;
  v7 = (__int64 *)*((_QWORD *)this + 9);
  v8 = *v7;
  v25 = 0;
  if ( (*(int (__fastcall **)(__int64 *, __int64, __int64 **))(v8 + 56))(v7, v26, &v25) >= 0 && v25 )
  {
    wil::make_bstr(&v28, L"\\RemediateCopilot");
    v27 = 0;
    v9 = *v25;
    v27 = 0;
    if ( (*(int (__fastcall **)(__int64 *, __int64, __int64 *))(v9 + 104))(v25, v28, &v27) < 0 )
    {
      wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v27);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
      wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v25);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
      v3 = 1;
    }
    else
    {
      v10 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(*v25 + 120))(v25, v28, 0);
      v3 = v10;
      if ( v10 >= 0 )
      {
        v17 = 0;
        v11 = (__int64 *)*((_QWORD *)this + 9);
        v12 = *v11;
        v17 = 0;
        v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v12 + 56))(v11, 0, &v17);
        v3 = v13;
        if ( v13 >= 0 )
        {
          v13 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v17 + 96LL))(v17, v26, 0);
          v3 = v13;
          if ( v13 >= 0 )
          {
            wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v17);
            wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v27);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
            wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v25);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
            VariantClear(&pvarg);
            return 0;
          }
          v14 = 479;
        }
        else
        {
          v14 = 478;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"shell\\onecore\\desktopshellext\\lib\\onecopilotremediator.cpp",
          (const char *)(unsigned int)v13,
          (int)ppv);
        wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v17);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D4,
          (unsigned int)"shell\\onecore\\desktopshellext\\lib\\onecopilotremediator.cpp",
          (const char *)(unsigned int)v10,
          (int)ppv);
      }
      wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v27);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
      wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v25);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
    }
    goto LABEL_20;
  }
  wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v25);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
  VariantClear(&pvarg);
  return 1;
}

```

## disassembly

```asm
0x180051a3c  push    rbp
0x180051a3e  push    rbx
0x180051a3f  push    rdi
0x180051a40  lea     rbp, [rsp-47h]
0x180051a45  sub     rsp, 0E0h
0x180051a4c  mov     rdi, rcx
0x180051a4f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180051a53  call    cs:__imp_VariantInit
0x180051a59  nop
0x180051a5a  cmp     qword ptr [rdi+48h], 0
0x180051a5f  jnz     loc_180051B2F
0x180051a65  mov     [rbp+57h+var_B8], 0
0x180051a6d  lea     rax, [rbp+57h+var_B8]
0x180051a71  mov     [rsp+0F0h+ppv], rax; ppv
0x180051a76  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180051a7d  xor     edx, edx; pUnkOuter
0x180051a7f  lea     r8d, [rdx+1]; dwClsContext
0x180051a83  lea     rcx, _GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd; rclsid
0x180051a8a  call    cs:__imp_CoCreateInstance
0x180051a90  lea     rdx, [rbp+57h+var_B8]
0x180051a94  lea     rcx, [rdi+48h]
0x180051a98  call    ??4?$com_ptr_t@UITaskService@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<ITaskService,wil::err_returncode_policy>::operator=(wil::com_ptr_t<ITaskService,wil::err_returncode_policy> &&)
0x180051a9d  lea     rcx, [rbp+57h+var_B8]
0x180051aa1  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180051aa6  mov     rcx, [rdi+48h]
0x180051aaa  test    rcx, rcx
0x180051aad  jnz     short loc_180051ABE
0x180051aaf  mov     ebx, 8007000Eh
0x180051ab4  mov     r9d, ebx
0x180051ab7  mov     edx, 1C4h
0x180051abc  jmp     short loc_180051B1A
0x180051abe  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x180051ac2  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x180051ac7  movaps  xmmword ptr [rbp+57h+var_90], xmm1
0x180051acb  movsd   [rbp+57h+var_80], xmm0
0x180051ad0  movaps  [rbp+57h+var_70], xmm1
0x180051ad4  movsd   [rbp+57h+var_60], xmm0
0x180051ad9  movaps  [rbp+57h+var_50], xmm1
0x180051add  movsd   [rbp+57h+var_40], xmm0
0x180051ae2  movaps  [rbp+57h+var_30], xmm1
0x180051ae6  movsd   [rbp+57h+var_20], xmm0
0x180051aeb  mov     rax, [rcx]
0x180051aee  lea     rdx, [rbp+57h+var_90]
0x180051af2  mov     [rsp+0F0h+ppv], rdx; int
0x180051af7  lea     r9, [rbp+57h+var_70]
0x180051afb  lea     r8, [rbp+57h+var_50]
0x180051aff  lea     rdx, [rbp+57h+var_30]
0x180051b03  mov     rax, [rax+50h]
0x180051b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051b0c  mov     ebx, eax
0x180051b0e  test    eax, eax
0x180051b10  jns     short loc_180051B2F
0x180051b12  mov     r9d, eax; char *
0x180051b15  mov     edx, 1C5h; void *
0x180051b1a  lea     r8, aShellOnecoreDe_5; "shell\\onecore\\desktopshellext\\lib\\o"...
0x180051b21  mov     rcx, [rbp+5Fh]; this
0x180051b25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051b2a  jmp     loc_180051CFE
0x180051b2f  lea     rdx, aOnecopilot; "\\OneCopilot"
0x180051b36  lea     rcx, [rbp+57h+arg_8]
0x180051b3a  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180051b3f  nop
0x180051b40  mov     [rbp+57h+arg_0], 0
0x180051b48  mov     rcx, [rdi+48h]
0x180051b4c  mov     rax, [rcx]
0x180051b4f  mov     [rbp+57h+arg_0], 0
0x180051b57  lea     r8, [rbp+57h+arg_0]
0x180051b5b  mov     rdx, [rbp+57h+arg_8]
0x180051b5f  mov     rax, [rax+38h]
0x180051b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051b68  test    eax, eax
0x180051b6a  js      loc_180051D0C
0x180051b70  cmp     [rbp+57h+arg_0], 0
0x180051b75  jz      loc_180051D0C
0x180051b7b  lea     rdx, aRemediatecopil; "\\RemediateCopilot"
0x180051b82  lea     rcx, [rbp+57h+arg_18]
0x180051b86  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180051b8b  nop
0x180051b8c  mov     [rbp+57h+arg_10], 0
0x180051b94  mov     rcx, [rbp+57h+arg_0]
0x180051b98  mov     rax, [rcx]
0x180051b9b  mov     [rbp+57h+arg_10], 0
0x180051ba3  lea     r8, [rbp+57h+arg_10]
0x180051ba7  mov     rdx, [rbp+57h+arg_18]
0x180051bab  mov     rax, [rax+68h]
0x180051baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051bb4  test    eax, eax
0x180051bb6  js      loc_180051CD2
0x180051bbc  mov     rcx, [rbp+57h+arg_0]
0x180051bc0  mov     rax, [rcx]
0x180051bc3  xor     r8d, r8d
0x180051bc6  mov     rdx, [rbp+57h+arg_18]
0x180051bca  mov     rax, [rax+78h]
0x180051bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051bd3  mov     ebx, eax
0x180051bd5  test    eax, eax
0x180051bd7  jns     short loc_180051C1E
0x180051bd9  mov     rcx, [rbp+5Fh]; this
0x180051bdd  mov     r9d, eax; char *
0x180051be0  lea     r8, aShellOnecoreDe_5; "shell\\onecore\\desktopshellext\\lib\\o"...
0x180051be7  mov     edx, 1D4h; void *
0x180051bec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051bf1  nop
0x180051bf2  lea     rcx, [rbp+57h+arg_10]
0x180051bf6  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180051bfb  nop
0x180051bfc  lea     rcx, [rbp+57h+arg_18]
0x180051c00  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180051c05  nop
0x180051c06  lea     rcx, [rbp+57h+arg_0]
0x180051c0a  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180051c0f  nop
0x180051c10  lea     rcx, [rbp+57h+arg_8]
0x180051c14  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180051c19  jmp     loc_180051CFE
0x180051c1e  mov     [rbp+57h+var_C0], 0
0x180051c26  mov     rcx, [rdi+48h]
0x180051c2a  mov     rax, [rcx]
0x180051c2d  mov     [rbp+57h+var_C0], 0
0x180051c35  lea     r8, [rbp+57h+var_C0]
0x180051c39  xor     edx, edx
0x180051c3b  mov     rax, [rax+38h]
0x180051c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c44  mov     ebx, eax
0x180051c46  test    eax, eax
0x180051c48  jns     short loc_180051C6E
0x180051c4a  mov     edx, 1DEh; void *
0x180051c4f  lea     r8, aShellOnecoreDe_5; "shell\\onecore\\desktopshellext\\lib\\o"...
0x180051c56  mov     r9d, eax; char *
0x180051c59  mov     rcx, [rbp+5Fh]; this
0x180051c5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051c62  nop
0x180051c63  lea     rcx, [rbp+57h+var_C0]
0x180051c67  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180051c6c  jmp     short loc_180051BF2
0x180051c6e  mov     rcx, [rbp+57h+var_C0]
0x180051c72  mov     rax, [rcx]
0x180051c75  xor     r8d, r8d
0x180051c78  mov     rdx, [rbp+57h+arg_8]
0x180051c7c  mov     rax, [rax+60h]
0x180051c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c85  mov     ebx, eax
0x180051c87  test    eax, eax
0x180051c89  jns     short loc_180051C92
0x180051c8b  mov     edx, 1DFh
0x180051c90  jmp     short loc_180051C4F
0x180051c92  lea     rcx, [rbp+57h+var_C0]
0x180051c96  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180051c9b  nop
0x180051c9c  lea     rcx, [rbp+57h+arg_10]
0x180051ca0  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180051ca5  nop
0x180051ca6  lea     rcx, [rbp+57h+arg_18]
0x180051caa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180051caf  nop
0x180051cb0  lea     rcx, [rbp+57h+arg_0]
0x180051cb4  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180051cb9  nop
0x180051cba  lea     rcx, [rbp+57h+arg_8]
0x180051cbe  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180051cc3  nop
0x180051cc4  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180051cc8  call    cs:__imp_VariantClear
0x180051cce  xor     eax, eax
0x180051cd0  jmp     short loc_180051D2F
0x180051cd2  lea     rcx, [rbp+57h+arg_10]
0x180051cd6  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180051cdb  nop
0x180051cdc  lea     rcx, [rbp+57h+arg_18]
0x180051ce0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180051ce5  nop
0x180051ce6  lea     rcx, [rbp+57h+arg_0]
0x180051cea  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180051cef  nop
0x180051cf0  lea     rcx, [rbp+57h+arg_8]
0x180051cf4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180051cf9  mov     ebx, 1
0x180051cfe  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180051d02  call    cs:__imp_VariantClear
0x180051d08  mov     eax, ebx
0x180051d0a  jmp     short loc_180051D2F
0x180051d0c  lea     rcx, [rbp+57h+arg_0]
0x180051d10  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180051d15  nop
0x180051d16  lea     rcx, [rbp+57h+arg_8]
0x180051d1a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180051d1f  nop
0x180051d20  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180051d24  call    cs:__imp_VariantClear
0x180051d2a  mov     eax, 1
0x180051d2f  add     rsp, 0E0h
0x180051d36  pop     rdi
0x180051d37  pop     rbx
0x180051d38  pop     rbp
0x180051d39  retn
```
