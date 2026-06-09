# Rdp::Stack::Shim::CAdapterShim::StartProcessor(uint)

- ea: `0x18001a2a0`
- end: `0x18001a50e`
- name: `?StartProcessor@CAdapterShim@Shim@Stack@Rdp@@AEAAXI@Z`
- size: `622`
- prototype: `void __fastcall(Rdp::Stack::Shim::CAdapterShim *this, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180019f08`

## callees

- `0x180007b28`
- `0x18000af58`
- `0x18000b130`
- `0x18000cea4`
- `0x18000cf28`
- `0x18000db64`
- `0x18000ed34`
- `0x180017cfc`
- `0x18001938c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a2fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a2fd`

## string_xrefs

- `0x18001a2c5`: `Encoding processor has already been started`
- `0x18001a349`: `Failed to retrieve PKEY_InProcEncodingProcessorClsid property`

## pseudocode

```c
void __fastcall Rdp::Stack::Shim::CAdapterShim::StartProcessor(Rdp::Stack::Shim::CAdapterShim *this, unsigned int a2)
{
  _QWORD *v4; // r15
  FARPROC ProcAddress; // rdi
  struct _GUID *v6; // r9
  unsigned int Guid; // eax
  unsigned int v8; // eax
  struct IPropertyStore *v9; // rdx
  const struct _tagpropertykey *v10; // r8
  const struct _LUID *v11; // r9
  unsigned int v12; // eax
  unsigned int v13; // r9d
  unsigned int v14; // eax
  bool v15; // r9
  unsigned int v16; // eax
  const struct _tagpropertykey *v17; // r8
  bool v18; // r9
  unsigned int v19; // eax
  __int64 (__fastcall **v20)(Rdp::Stack::Shim::CAdapterShim *, GUID *, __int64 *); // rax
  unsigned int v21; // eax
  unsigned int v22; // eax
  char *v23; // [rsp+28h] [rbp-40h]
  char *v24; // [rsp+28h] [rbp-40h]
  char *v25; // [rsp+28h] [rbp-40h]
  char *v26; // [rsp+28h] [rbp-40h]
  char *v27; // [rsp+28h] [rbp-40h]
  char *v28; // [rsp+28h] [rbp-40h]
  char *v29; // [rsp+28h] [rbp-40h]
  char *v30; // [rsp+28h] [rbp-40h]
  const char *v31; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v33; // [rsp+70h] [rbp+8h] BYREF

  v4 = (_QWORD *)((char *)this + 344);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x132,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    (const char *)0x80070057LL,
    *((_QWORD *)this + 43) != 0,
    (bool)"Encoding processor has already been started",
    v31);
  ProcAddress = GetProcAddress(*((HMODULE *)this + 17), "ClassFactoryEx");
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<long (*)(Rdp::Avenc::AVENC_VERSION_INFO const *,Rdp::Avenc::AVENC_VERSION_INFO *,Rdp::Avenc::AVENC_VERSION_INFO *),0>(
    retaddr,
    311,
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    ProcAddress,
    "Failed to load address of ClassFactoryEx");
  Guid = Rdp::Utils::Props::IPropertyStore_GetGuid(
           *((Rdp::Utils::Props **)this + 18),
           (struct IPropertyStore *)&PKEY_InProcEncodingProcessorClsid,
           (const struct _tagpropertykey *)((char *)this + 216),
           v6);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x141,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    (const char *)Guid,
    (int)"Failed to retrieve PKEY_InProcEncodingProcessorClsid property",
    v23);
  wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(v4);
  v8 = ((__int64 (__fastcall *)(char *, GUID *, _QWORD, _QWORD *))ProcAddress)(
         (char *)this + 216,
         &GUID_adddf56d_f95b_444f_bfb5_db18b475f325,
         *((_QWORD *)this + 18),
         v4);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x14C,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    (const char *)v8,
    (int)"Failed to instantiate video encoder processor",
    v24);
  v12 = Rdp::Utils::Props::IPropertyStore_SetLuid(*((Rdp::Utils::Props **)this + 18), v9, v10, v11);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x156,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    (const char *)v12,
    (int)"Failed to set PKEY_Terminal_Luid property",
    v25);
  v14 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          *((Rdp::Utils::Props **)this + 18),
          (struct IPropertyStore *)&PKEY_Capture_Process_Pid,
          (const struct _tagpropertykey *)a2,
          v13);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x160,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    (const char *)v14,
    (int)"Failed to set PKEY_Capture_Process_Pid property",
    v26);
  v16 = Rdp::Utils::Props::IPropertyStore_SetBool(
          *((Rdp::Utils::Props **)this + 18),
          (struct IPropertyStore *)&PKEY_Console_Mode_Enabled,
          0,
          v15);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x16A,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    (const char *)v16,
    (int)"Failed to set PKEY_Console_Mode_Enabled property",
    v27);
  LOBYTE(v17) = 1;
  v19 = Rdp::Utils::Props::IPropertyStore_SetBool(
          *((Rdp::Utils::Props **)this + 18),
          (struct IPropertyStore *)&PKEY_Large_Cursor_Enabled,
          v17,
          v18);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x174,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    (const char *)v19,
    (int)"Failed to set PKEY_Large_Cursor_Enabled property",
    v28);
  v20 = *(__int64 (__fastcall ***)(Rdp::Stack::Shim::CAdapterShim *, GUID *, __int64 *))this;
  v33 = 0;
  v21 = (*v20)(this, &IID_IUnknown, &v33);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x17B,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    (const char *)v21,
    (int)"Failed to QI IUnknown",
    v29);
  v22 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v4 + 32LL))(*v4, v33);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x17E,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    (const char *)v22,
    (int)"Failed to start encoding processor",
    v30);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v33);
}

```

## disassembly

```asm
0x18001a2a0  push    rbx
0x18001a2a2  push    rbp
0x18001a2a3  push    rsi
0x18001a2a4  push    rdi
0x18001a2a5  push    r14
0x18001a2a7  push    r15
0x18001a2a9  sub     rsp, 38h
0x18001a2ad  mov     esi, edx
0x18001a2af  mov     r14, rcx
0x18001a2b2  lea     r15, [rcx+158h]
0x18001a2b9  cmp     qword ptr [r15], 0
0x18001a2bd  setnz   al
0x18001a2c0  mov     rcx, [rsp+68h]; this
0x18001a2c5  lea     rdx, aEncodingProces_1; "Encoding processor has already been sta"...
0x18001a2cc  mov     [rsp+68h+var_40], rdx; char *
0x18001a2d1  mov     [rsp+68h+var_48], al; char
0x18001a2d5  mov     r9d, 80070057h; char *
0x18001a2db  lea     rbp, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001a2e2  mov     r8, rbp; unsigned int
0x18001a2e5  mov     edx, 132h; void *
0x18001a2ea  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001a2ef  lea     rdx, aClassfactoryex; "ClassFactoryEx"
0x18001a2f6  mov     rcx, [r14+88h]; hModule
0x18001a2fd  call    cs:__imp_GetProcAddress
0x18001a303  mov     rdi, rax
0x18001a306  mov     rcx, [rsp+68h]
0x18001a30b  lea     rax, aFailedToLoadAd_0; "Failed to load address of ClassFactoryE"...
0x18001a312  mov     qword ptr [rsp+68h+var_48], rax
0x18001a317  mov     r9, rdi
0x18001a31a  mov     r8, rbp
0x18001a31d  mov     edx, 137h
0x18001a322  call    ??$Throw_GetLastErrorIfNullMsg@P6AJPEBUAVENC_VERSION_INFO@Avenc@Rdp@@PEAU123@1@Z$0A@@in1diag3@details@wil@@YAP6AJPEBUAVENC_VERSION_INFO@Avenc@Rdp@@PEAU345@1@ZPEAXIPEBDP6AJ011@Z3ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<long (*)(Rdp::Avenc::AVENC_VERSION_INFO const *,Rdp::Avenc::AVENC_VERSION_INFO *,Rdp::Avenc::AVENC_VERSION_INFO *),0>(void *,uint,char const *,long (*)(Rdp::Avenc::AVENC_VERSION_INFO const *,Rdp::Avenc::AVENC_VERSION_INFO *,Rdp::Avenc::AVENC_VERSION_INFO *),char const *,...)
0x18001a327  lea     rbx, [r14+0D8h]
0x18001a32e  mov     r8, rbx; struct _tagpropertykey *
0x18001a331  lea     rdx, PKEY_InProcEncodingProcessorClsid; struct IPropertyStore *
0x18001a338  mov     rcx, [r14+90h]; this
0x18001a33f  call    ?IPropertyStore_GetGuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetGuid(IPropertyStore *,_tagpropertykey const &,_GUID *)
0x18001a344  mov     rcx, [rsp+68h]; this
0x18001a349  lea     rdx, aFailedToRetrie_18; "Failed to retrieve PKEY_InProcEncodingP"...
0x18001a350  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18001a355  mov     r9d, eax; char *
0x18001a358  mov     r8, rbp; unsigned int
0x18001a35b  mov     edx, 141h; void *
0x18001a360  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001a365  mov     rcx, r15
0x18001a368  call    ?reset@?$com_ptr_t@UIRDPCoreChannelManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(void)
0x18001a36d  mov     r9, r15
0x18001a370  mov     r8, [r14+90h]
0x18001a377  lea     rdx, _GUID_adddf56d_f95b_444f_bfb5_db18b475f325
0x18001a37e  mov     rcx, rbx
0x18001a381  mov     rax, rdi
0x18001a384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a389  mov     rcx, [rsp+68h]; this
0x18001a38e  lea     rdx, aFailedToInstan; "Failed to instantiate video encoder pro"...
0x18001a395  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18001a39a  mov     r9d, eax; char *
0x18001a39d  mov     r8, rbp; unsigned int
0x18001a3a0  mov     edx, 14Ch; void *
0x18001a3a5  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001a3aa  mov     rcx, [r14+90h]; this
0x18001a3b1  call    ?IPropertyStore_SetLuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEBU_LUID@@@Z; Rdp::Utils::Props::IPropertyStore_SetLuid(IPropertyStore *,_tagpropertykey const &,_LUID const &)
0x18001a3b6  mov     rcx, [rsp+68h]; this
0x18001a3bb  lea     rdx, aFailedToSetPke_6; "Failed to set PKEY_Terminal_Luid proper"...
0x18001a3c2  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18001a3c7  mov     r9d, eax; char *
0x18001a3ca  mov     r8, rbp; unsigned int
0x18001a3cd  mov     edx, 156h; void *
0x18001a3d2  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001a3d7  mov     r8d, esi; struct _tagpropertykey *
0x18001a3da  lea     rdx, PKEY_Capture_Process_Pid; struct IPropertyStore *
0x18001a3e1  mov     rcx, [r14+90h]; this
0x18001a3e8  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18001a3ed  mov     rcx, [rsp+68h]; this
0x18001a3f2  lea     rdx, aFailedToSetPke_18; "Failed to set PKEY_Capture_Process_Pid "...
0x18001a3f9  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18001a3fe  mov     r9d, eax; char *
0x18001a401  mov     r8, rbp; unsigned int
0x18001a404  mov     edx, 160h; void *
0x18001a409  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001a40e  xor     r8d, r8d; struct _tagpropertykey *
0x18001a411  lea     rdx, PKEY_Console_Mode_Enabled; struct IPropertyStore *
0x18001a418  mov     rcx, [r14+90h]; this
0x18001a41f  call    ?IPropertyStore_SetBool@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@_N@Z; Rdp::Utils::Props::IPropertyStore_SetBool(IPropertyStore *,_tagpropertykey const &,bool)
0x18001a424  mov     rcx, [rsp+68h]; this
0x18001a429  lea     rdx, aFailedToSetPke_15; "Failed to set PKEY_Console_Mode_Enabled"...
0x18001a430  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18001a435  mov     r9d, eax; char *
0x18001a438  mov     r8, rbp; unsigned int
0x18001a43b  mov     edx, 16Ah; void *
0x18001a440  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001a445  mov     r8b, 1; struct _tagpropertykey *
0x18001a448  lea     rdx, PKEY_Large_Cursor_Enabled; struct IPropertyStore *
0x18001a44f  mov     rcx, [r14+90h]; this
0x18001a456  call    ?IPropertyStore_SetBool@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@_N@Z; Rdp::Utils::Props::IPropertyStore_SetBool(IPropertyStore *,_tagpropertykey const &,bool)
0x18001a45b  mov     rcx, [rsp+68h]; this
0x18001a460  lea     rdx, aFailedToSetPke_41; "Failed to set PKEY_Large_Cursor_Enabled"...
0x18001a467  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18001a46c  mov     r9d, eax; char *
0x18001a46f  mov     r8, rbp; unsigned int
0x18001a472  mov     edx, 174h; void *
0x18001a477  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001a47c  nop
0x18001a47d  mov     rax, [r14]
0x18001a480  mov     [rsp+68h+arg_0], 0
0x18001a489  lea     r8, [rsp+68h+arg_0]
0x18001a48e  lea     rdx, IID_IUnknown
0x18001a495  mov     rcx, r14
0x18001a498  mov     rax, [rax]
0x18001a49b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4a0  mov     rcx, [rsp+68h]; this
0x18001a4a5  lea     rdx, aFailedToQiIunk; "Failed to QI IUnknown"
0x18001a4ac  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18001a4b1  mov     r9d, eax; char *
0x18001a4b4  mov     r8, rbp; unsigned int
0x18001a4b7  mov     edx, 17Bh; void *
0x18001a4bc  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001a4c1  mov     rcx, [r15]
0x18001a4c4  mov     rax, [rcx]
0x18001a4c7  mov     rdx, [rsp+68h+arg_0]
0x18001a4cc  mov     rax, [rax+20h]
0x18001a4d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4d5  mov     rcx, [rsp+68h]; this
0x18001a4da  lea     rdx, aFailedToStartE; "Failed to start encoding processor"
0x18001a4e1  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18001a4e6  mov     r9d, eax; char *
0x18001a4e9  mov     r8, rbp; unsigned int
0x18001a4ec  mov     edx, 17Eh; void *
0x18001a4f1  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001a4f6  nop
0x18001a4f7  lea     rcx, [rsp+68h+arg_0]
0x18001a4fc  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x18001a501  add     rsp, 38h
0x18001a505  pop     r15
0x18001a507  pop     r14
0x18001a509  pop     rdi
0x18001a50a  pop     rsi
0x18001a50b  pop     rbp
0x18001a50c  pop     rbx
0x18001a50d  retn
```
