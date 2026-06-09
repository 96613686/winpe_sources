# ExpeditedUpdateWUTask::_FilterUpdates(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *,IUpdateCollection * *)

- ea: `0x1800773a8`
- end: `0x1800776ae`
- name: `?_FilterUpdates@ExpeditedUpdateWUTask@@AEAAJPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@PEAPEAUIUpdateCollection@@@Z`
- size: `774`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180073eb0`
- `0x180074290`
- `0x180074d30`

## callees

- `0x180008544`
- `0x18001ad08`
- `0x18002f39c`
- `0x1800418d8`
- `0x180043c58`
- `0x1800773a8`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007750e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007750e`
- `OLEAUT32!__imp_SysStringLen` at `0x1800774fe`
- `OLEAUT32!__imp_SysStringLen` at `0x1800774fe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180077401`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180077401`

## string_xrefs

- `0x180077441`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x1800775dd`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180077603`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180077627`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x18007764b`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x1800773d0`: `ExpeditedUpdateWUTask Filtering Expedited Update collection`
- `0x180077456`: `ExpeditedUpdateWUTask updates count %ld`
- `0x180077547`: `ExpeditedUpdateWUTask Update added: %s`
- `0x18007766e`: `ExpeditedUpdateWUTask updates count after filtering %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ExpeditedUpdateWUTask::_FilterUpdates(__int64 a1, __int64 a2, _QWORD *a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  unsigned int v9; // ebx
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  HRESULT v13; // edi
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  UINT v18; // eax
  __int64 v19; // rdx
  LPVOID v20; // rax
  int ppv; // [rsp+20h] [rbp-40h]
  int v23; // [rsp+30h] [rbp-30h] BYREF
  __int64 *v24; // [rsp+38h] [rbp-28h] BYREF
  BSTR pbstr; // [rsp+40h] [rbp-20h] BYREF
  __int64 *v26; // [rsp+48h] [rbp-18h] BYREF
  HSTRING string; // [rsp+50h] [rbp-10h] BYREF
  LPVOID v28; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  char v30; // [rsp+A0h] [rbp+40h] BYREF
  int v31; // [rsp+A8h] [rbp+48h] BYREF

  *a3 = 0;
  UnattendLogW(0, L"ExpeditedUpdateWUTask Filtering Expedited Update collection");
  v28 = 0;
  v6 = CoCreateInstance(
         &GUID_13639463_00db_4646_803d_528026140d88,
         0,
         1u,
         &GUID_07f7438c_7709_4ca5_b518_91279288134e,
         &v28);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 536;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
      (const char *)(unsigned int)v6,
      ppv);
    goto LABEL_27;
  }
  v31 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)(a1 + 616) + 80LL))(*(_QWORD *)(a1 + 616), &v31);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 539;
    goto LABEL_5;
  }
  UnattendLogW(0, L"ExpeditedUpdateWUTask updates count %ld", (unsigned int)v31);
  v9 = 0;
  if ( v31 <= 0 )
  {
LABEL_15:
    v6 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v28 + 80LL))(v28, &v31);
    v7 = v6;
    if ( v6 >= 0 )
    {
      UnattendLogW(0, L"ExpeditedUpdateWUTask updates count after filtering %d", (unsigned int)v31);
      v20 = v28;
      v28 = 0;
      *a3 = v20;
      v7 = 0;
      goto LABEL_27;
    }
    v8 = 559;
    goto LABEL_5;
  }
  while ( 1 )
  {
    v24 = 0;
    v10 = *(__int64 **)(a1 + 616);
    v11 = *v10;
    v24 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v11 + 56))(v10, v9, &v24);
    v13 = v12;
    if ( v12 < 0 )
      break;
    v26 = 0;
    v14 = *v24;
    v26 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v14 + 152))(v24, &v26);
    v13 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x222,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
        (const char *)(unsigned int)v15,
        ppv);
      goto LABEL_23;
    }
    pbstr = 0;
    v16 = *v26;
    pbstr = 0;
    v17 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v16 + 64))(v26, &pbstr);
    v13 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x224,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
        (const char *)(unsigned int)v17,
        ppv);
      goto LABEL_21;
    }
    string = 0;
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &string,
      0);
    v18 = SysStringLen(pbstr);
    v13 = WindowsCreateString(pbstr, v18, &string);
    if ( v13 < 0 )
    {
      v19 = 550;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
        (const char *)(unsigned int)v13,
        ppv);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
LABEL_21:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pbstr);
LABEL_23:
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v26);
      goto LABEL_25;
    }
    v30 = 0;
    if ( (*(int (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)a2 + 64LL))(a2, string, &v30) >= 0 )
    {
      if ( v30 )
      {
        UnattendLogW(0, L"ExpeditedUpdateWUTask Update added: %s", pbstr);
        v23 = 0;
        v13 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, int *))(*(_QWORD *)v28 + 96LL))(v28, v24, &v23);
        if ( v13 < 0 )
        {
          v19 = 556;
          goto LABEL_19;
        }
      }
    }
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pbstr);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v26);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v24);
    if ( (int)++v9 >= v31 )
      goto LABEL_15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x220,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
    (const char *)(unsigned int)v12,
    ppv);
LABEL_25:
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v24);
  v7 = v13;
LABEL_27:
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v28);
  return v7;
}

```

## disassembly

```asm
0x1800773a8  mov     [rsp-28h+arg_0], rbx
0x1800773ad  mov     [rsp-28h+arg_8], rsi
0x1800773b2  push    rbp
0x1800773b3  push    rdi
0x1800773b4  push    r12
0x1800773b6  push    r14
0x1800773b8  push    r15
0x1800773ba  mov     rbp, rsp
0x1800773bd  sub     rsp, 60h
0x1800773c1  mov     rsi, r8
0x1800773c4  mov     r15, rdx
0x1800773c7  mov     r14, rcx
0x1800773ca  xor     r12d, r12d
0x1800773cd  mov     [r8], r12
0x1800773d0  lea     rdx, aExpeditedupdat_70; "ExpeditedUpdateWUTask Filtering Expedit"...
0x1800773d7  xor     ecx, ecx
0x1800773d9  call    UnattendLogW
0x1800773de  nop
0x1800773df  mov     [rbp+var_8], r12
0x1800773e3  lea     rax, [rbp+var_8]
0x1800773e7  mov     qword ptr [rsp+60h+ppv], rax; int
0x1800773ec  lea     r9, _GUID_07f7438c_7709_4ca5_b518_91279288134e; riid
0x1800773f3  xor     edx, edx; pUnkOuter
0x1800773f5  lea     r8d, [r12+1]; dwClsContext
0x1800773fa  lea     rcx, _GUID_13639463_00db_4646_803d_528026140d88; rclsid
0x180077401  call    cs:__imp_CoCreateInstance
0x180077407  mov     ebx, eax
0x180077409  test    eax, eax
0x18007740b  jns     short loc_180077414
0x18007740d  mov     edx, 218h
0x180077412  jmp     short loc_18007743A
0x180077414  mov     [rbp+arg_18], r12d
0x180077418  mov     rcx, [r14+268h]
0x18007741f  mov     rax, [rcx]
0x180077422  lea     rdx, [rbp+arg_18]
0x180077426  mov     rax, [rax+50h]
0x18007742a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007742f  mov     ebx, eax
0x180077431  test    eax, eax
0x180077433  jns     short loc_180077452
0x180077435  mov     edx, 21Bh; void *
0x18007743a  mov     rcx, [rbp+28h]; this
0x18007743e  mov     r9d, eax; char *
0x180077441  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180077448  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007744d  jmp     loc_18007768A
0x180077452  mov     r8d, [rbp+arg_18]
0x180077456  lea     rdx, aExpeditedupdat_62; "ExpeditedUpdateWUTask updates count %ld"
0x18007745d  xor     ecx, ecx
0x18007745f  call    UnattendLogW
0x180077464  mov     ebx, r12d
0x180077467  cmp     [rbp+arg_18], r12d
0x18007746b  jle     loc_1800775A9
0x180077471  mov     [rbp+var_28], r12
0x180077475  mov     rcx, [r14+268h]
0x18007747c  mov     rax, [rcx]
0x18007747f  mov     [rbp+var_28], r12
0x180077483  lea     r8, [rbp+var_28]
0x180077487  mov     edx, ebx
0x180077489  mov     rax, [rax+38h]
0x18007748d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077492  mov     edi, eax
0x180077494  test    eax, eax
0x180077496  js      loc_180077644
0x18007749c  mov     [rbp+var_18], r12
0x1800774a0  mov     rcx, [rbp+var_28]
0x1800774a4  mov     rax, [rcx]
0x1800774a7  mov     [rbp+var_18], r12
0x1800774ab  lea     rdx, [rbp+var_18]
0x1800774af  mov     rax, [rax+98h]
0x1800774b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800774bb  mov     edi, eax
0x1800774bd  test    eax, eax
0x1800774bf  js      loc_180077620
0x1800774c5  mov     [rbp+pbstr], r12
0x1800774c9  mov     rcx, [rbp+var_18]
0x1800774cd  mov     rax, [rcx]
0x1800774d0  mov     [rbp+pbstr], r12
0x1800774d4  lea     rdx, [rbp+pbstr]
0x1800774d8  mov     rax, [rax+40h]
0x1800774dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800774e1  mov     edi, eax
0x1800774e3  test    eax, eax
0x1800774e5  js      loc_1800775FC
0x1800774eb  mov     [rbp+string], r12
0x1800774ef  xor     edx, edx
0x1800774f1  lea     rcx, [rbp+string]
0x1800774f5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800774fa  mov     rcx, [rbp+pbstr]; pbstr
0x1800774fe  call    cs:__imp_SysStringLen
0x180077504  lea     r8, [rbp+string]; string
0x180077508  mov     edx, eax; length
0x18007750a  mov     rcx, [rbp+pbstr]; sourceString
0x18007750e  call    cs:__imp_WindowsCreateString
0x180077514  mov     edi, eax
0x180077516  test    eax, eax
0x180077518  js      loc_1800775D8
0x18007751e  mov     [rbp+arg_10], r12b
0x180077522  mov     rax, [r15]
0x180077525  lea     r8, [rbp+arg_10]
0x180077529  mov     rdx, [rbp+string]
0x18007752d  mov     rcx, r15
0x180077530  mov     rax, [rax+40h]
0x180077534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077539  test    eax, eax
0x18007753b  js      short loc_180077577
0x18007753d  cmp     [rbp+arg_10], r12b
0x180077541  jz      short loc_180077577
0x180077543  mov     r8, [rbp+pbstr]
0x180077547  lea     rdx, aExpeditedupdat_25; "ExpeditedUpdateWUTask Update added: %s"
0x18007754e  xor     ecx, ecx
0x180077550  call    UnattendLogW
0x180077555  mov     [rbp+var_30], r12d
0x180077559  mov     rcx, [rbp+var_8]
0x18007755d  mov     rax, [rcx]
0x180077560  lea     r8, [rbp+var_30]
0x180077564  mov     rdx, [rbp+var_28]
0x180077568  mov     rax, [rax+60h]
0x18007756c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077571  mov     edi, eax
0x180077573  test    eax, eax
0x180077575  js      short loc_1800775D1
0x180077577  lea     rcx, [rbp+string]; this
0x18007757b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180077580  nop
0x180077581  lea     rcx, [rbp+pbstr]
0x180077585  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007758a  nop
0x18007758b  lea     rcx, [rbp+var_18]
0x18007758f  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180077594  nop
0x180077595  lea     rcx, [rbp+var_28]
0x180077599  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007759e  inc     ebx
0x1800775a0  cmp     ebx, [rbp+arg_18]
0x1800775a3  jl      loc_180077471
0x1800775a9  mov     rcx, [rbp+var_8]
0x1800775ad  mov     rax, [rcx]
0x1800775b0  lea     rdx, [rbp+arg_18]
0x1800775b4  mov     rax, [rax+50h]
0x1800775b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800775bd  mov     ebx, eax
0x1800775bf  test    eax, eax
0x1800775c1  jns     loc_18007766A
0x1800775c7  mov     edx, 22Fh
0x1800775cc  jmp     loc_18007743A
0x1800775d1  mov     edx, 22Ch
0x1800775d6  jmp     short loc_1800775DD
0x1800775d8  mov     edx, 226h; void *
0x1800775dd  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800775e4  mov     r9d, edi; char *
0x1800775e7  mov     rcx, [rbp+28h]; this
0x1800775eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800775f0  nop
0x1800775f1  lea     rcx, [rbp+string]; this
0x1800775f5  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800775fa  jmp     short loc_180077615
0x1800775fc  mov     rcx, [rbp+28h]; this
0x180077600  mov     r9d, edi; char *
0x180077603  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007760a  mov     edx, 224h; void *
0x18007760f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077614  nop
0x180077615  lea     rcx, [rbp+pbstr]
0x180077619  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007761e  jmp     short loc_180077639
0x180077620  mov     rcx, [rbp+28h]; this
0x180077624  mov     r9d, edi; char *
0x180077627  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007762e  mov     edx, 222h; void *
0x180077633  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077638  nop
0x180077639  lea     rcx, [rbp+var_18]
0x18007763d  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180077642  jmp     short loc_18007765D
0x180077644  mov     rcx, [rbp+28h]; this
0x180077648  mov     r9d, edi; char *
0x18007764b  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180077652  mov     edx, 220h; void *
0x180077657  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007765c  nop
0x18007765d  lea     rcx, [rbp+var_28]
0x180077661  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180077666  mov     ebx, edi
0x180077668  jmp     short loc_18007768A
0x18007766a  mov     r8d, [rbp+arg_18]
0x18007766e  lea     rdx, aExpeditedupdat_54; "ExpeditedUpdateWUTask updates count aft"...
0x180077675  xor     ecx, ecx
0x180077677  call    UnattendLogW
0x18007767c  mov     rax, [rbp+var_8]
0x180077680  mov     [rbp+var_8], r12
0x180077684  mov     [rsi], rax
0x180077687  mov     ebx, r12d
0x18007768a  lea     rcx, [rbp+var_8]
0x18007768e  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180077693  mov     eax, ebx
0x180077695  lea     r11, [rsp+60h+var_s0]
0x18007769a  mov     rbx, [r11+30h]
0x18007769e  mov     rsi, [r11+38h]
0x1800776a2  mov     rsp, r11
0x1800776a5  pop     r15
0x1800776a7  pop     r14
0x1800776a9  pop     r12
0x1800776ab  pop     rdi
0x1800776ac  pop     rbp
0x1800776ad  retn
```
