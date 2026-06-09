# HcsExportLegacyWritableLayer

- ea: `0x180014a00`
- end: `0x180014c19`
- name: `HcsExportLegacyWritableLayer`
- size: `537`
- prototype: `HRESULT __stdcall(PCWSTR writableLayerMountPath, PCWSTR writableLayerFolderPath, PCWSTR exportFolderPath, PCWSTR layerData)`
- caller_count: `0`
- callee_count: `16`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002690`
- `0x1800032b8`
- `0x180004aac`
- `0x1800084c0`
- `0x180008a8c`
- `0x180008ce8`
- `0x1800092d8`
- `0x18000971c`
- `0x18000a964`
- `0x18000f968`
- `0x18000ffd4`
- `0x1800127bc`
- `0x180012838`
- `0x1800137fc`
- `0x180014a00`
- `0x18001a538`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180014a6f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180014a6f`
- `wc_storage!WcExportLayerEx` at `0x180014b50`
- `wc_storage!WcExportLayerEx` at `0x180014b50`

## string_xrefs

- `0x180014a48`: `ComputeStorage_HcsExportLegacyWritableLayer`
- `0x180014bd9`: `onecore\vm\compute\dll\storage\src\layer.cpp`
- `0x180014c07`: `onecore\vm\compute\dll\storage\src\layer.cpp`

## pseudocode

```c
HRESULT __stdcall HcsExportLegacyWritableLayer(
        PCWSTR writableLayerMountPath,
        PCWSTR writableLayerFolderPath,
        PCWSTR exportFolderPath,
        PCWSTR layerData)
{
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  const char *v12; // r9
  __int64 v13; // rdx
  __int64 v14; // r8
  const char *v15; // r9
  __int64 v16; // rdx
  __int64 v17; // r8
  const char *v18; // r9
  int v20; // [rsp+20h] [rbp-E0h]
  const char *v21; // [rsp+28h] [rbp-D8h]
  __int128 v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h]
  __int128 v24; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v26; // [rsp+68h] [rbp-98h] BYREF
  __int64 v27; // [rsp+78h] [rbp-88h]
  int v28; // [rsp+80h] [rbp-80h]
  __int128 v29; // [rsp+88h] [rbp-78h] BYREF
  __int64 v30; // [rsp+98h] [rbp-68h]
  __int128 v31; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v32; // [rsp+B0h] [rbp-50h]
  __int128 v33; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v34; // [rsp+C8h] [rbp-38h]
  _QWORD v35[42]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  memset_0(v35, 0, sizeof(v35));
  wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v35,
    (__int64)"ComputeStorage_HcsExportLegacyWritableLayer");
  v35[0] = &ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLegacyWritableLayer::`vftable';
  ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLegacyWritableLayer::StartActivity((ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLegacyWritableLayer *)v35);
  if ( !PathFileExistsW(exportFolderPath) )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
      (const char *)2,
      (unsigned int)"Failed to export layer: Export folder doesn't exist!.",
      v21);
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v8 = -1;
  v28 = 0;
  do
    ++v8;
  while ( layerData[v8] );
  *(_QWORD *)&v24 = layerData;
  *((_QWORD *)&v24 + 1) = v8;
  ComputeService::MarshalUtilities::FromJsonStrictThrow<Schema::LayerManagement::LayerData,>(&v24, (__int64)&v25);
  v34 = 0;
  v33 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v33, 17);
  v32 = 0;
  v31 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v31, 18);
  v30 = 0;
  v29 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v29, 8);
  v22 = 0;
  v23 = 0;
  ComputeStorageInternal::ConvertLayerDescriptors(&v22, (__int128 **)&v26);
  v20 = (__int64)(*((_QWORD *)&v22 + 1) - v22) >> 5;
  v9 = WcExportLayerEx(writableLayerFolderPath, writableLayerMountPath, exportFolderPath);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9A,
      (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
      (const char *)(unsigned int)v9,
      v20);
  wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v35);
  std::vector<_WC_LAYER_DESCRIPTOR>::~vector<_WC_LAYER_DESCRIPTOR>((char **)&v22);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((const struct _LUID *)&v29, v10, v11, v12);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((const struct _LUID *)&v31, v13, v14, v15);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((const struct _LUID *)&v33, v16, v17, v18);
  std::vector<Schema::Common::Resources::Layer>::_Tidy((char ***)&v26);
  v35[0] = &ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLegacyWritableLayer::`vftable';
  wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v35);
  wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v35);
  return 0;
}

```

## disassembly

```asm
0x180014a00  push    rbp
0x180014a02  push    rbx
0x180014a03  push    rsi
0x180014a04  push    rdi
0x180014a05  push    r12
0x180014a07  push    r14
0x180014a09  push    r15
0x180014a0b  lea     rbp, [rsp-130h]
0x180014a13  sub     rsp, 230h
0x180014a1a  mov     rax, cs:__security_cookie
0x180014a21  xor     rax, rsp
0x180014a24  mov     [rbp+160h+var_40], rax
0x180014a2b  mov     rdi, r8
0x180014a2e  mov     r14, rdx
0x180014a31  mov     rsi, rcx
0x180014a34  xor     edx, edx; Val
0x180014a36  mov     r8d, 150h; Size
0x180014a3c  lea     rcx, [rbp+160h+var_190]; void *
0x180014a40  mov     rbx, r9
0x180014a43  call    memset_0
0x180014a48  lea     rdx, aComputestorage_10; "ComputeStorage_HcsExportLegacyWritableL"...
0x180014a4f  lea     rcx, [rbp+160h+var_190]
0x180014a53  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180014a58  lea     r12, ??_7ComputeStorage_HcsExportLegacyWritableLayer@TraceProvider@Diagnostics@ComputeStorage@@6B@; const ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLegacyWritableLayer::`vftable'
0x180014a5f  lea     rcx, [rbp+160h+var_190]; this
0x180014a63  mov     [rbp+160h+var_190], r12
0x180014a67  call    ?StartActivity@ComputeStorage_HcsExportLegacyWritableLayer@TraceProvider@Diagnostics@ComputeStorage@@QEAAXXZ; ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLegacyWritableLayer::StartActivity(void)
0x180014a6c  mov     rcx, rdi; pszPath
0x180014a6f  call    cs:__imp_PathFileExistsW
0x180014a76  nop     dword ptr [rax+rax+00h]
0x180014a7b  xor     r15d, r15d
0x180014a7e  test    eax, eax
0x180014a80  jz      loc_180014BEE
0x180014a86  xorps   xmm0, xmm0
0x180014a89  mov     [rsp+260h+var_200], r15
0x180014a8e  movdqu  [rsp+260h+var_1F8], xmm0
0x180014a94  mov     [rsp+260h+var_1E8], r15
0x180014a99  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014a9d  mov     [rbp+160h+var_1E0], r15d
0x180014aa1  inc     rax
0x180014aa4  cmp     [rbx+rax*2], r15w
0x180014aa9  jnz     short loc_180014AA1
0x180014aab  lea     rdx, [rsp+260h+var_200]
0x180014ab0  mov     [rsp+260h+var_210], rbx
0x180014ab5  lea     rcx, [rsp+260h+var_210]
0x180014aba  mov     [rsp+260h+var_208], rax
0x180014abf  call    ??$FromJsonStrictThrow@ULayerData@LayerManagement@Schema@@$$V@MarshalUtilities@ComputeService@@YAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAULayerData@LayerManagement@Schema@@W4UnmarshalFlags@Marshal@@@Z; ComputeService::MarshalUtilities::FromJsonStrictThrow<Schema::LayerManagement::LayerData,>(std::basic_string_view<ushort>,Schema::LayerManagement::LayerData *,Marshal::UnmarshalFlags)
0x180014ac4  xor     eax, eax
0x180014ac6  lea     rcx, [rbp+160h+var_1A8]; this
0x180014aca  xorps   xmm0, xmm0
0x180014acd  mov     [rbp+160h+var_198], rax
0x180014ad1  movups  [rbp+160h+var_1A8], xmm0
0x180014ad5  lea     edx, [rax+11h]; int
0x180014ad8  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x180014add  xor     eax, eax
0x180014adf  lea     rcx, [rbp+160h+var_1C0]; this
0x180014ae3  xorps   xmm0, xmm0
0x180014ae6  mov     [rbp+160h+var_1B0], rax
0x180014aea  movups  [rbp+160h+var_1C0], xmm0
0x180014aee  lea     edx, [rax+12h]; int
0x180014af1  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x180014af6  xor     eax, eax
0x180014af8  lea     rcx, [rbp+160h+var_1D8]; this
0x180014afc  xorps   xmm0, xmm0
0x180014aff  mov     [rbp+160h+var_1C8], rax
0x180014b03  movups  [rbp+160h+var_1D8], xmm0
0x180014b07  lea     edx, [rax+8]; int
0x180014b0a  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x180014b0f  xorps   xmm0, xmm0
0x180014b12  lea     rdx, [rsp+260h+var_1F8]
0x180014b17  xor     eax, eax
0x180014b19  lea     rcx, [rsp+260h+var_230]
0x180014b1e  movups  [rsp+260h+var_230], xmm0
0x180014b23  mov     [rsp+260h+var_220], rax
0x180014b28  call    ?ConvertLayerDescriptors@ComputeStorageInternal@@YA?AV?$vector@U_WC_LAYER_DESCRIPTOR@@V?$allocator@U_WC_LAYER_DESCRIPTOR@@@std@@@std@@AEBV?$vector@ULayer@Resources@Common@Schema@@V?$allocator@ULayer@Resources@Common@Schema@@@std@@@3@@Z; ComputeStorageInternal::ConvertLayerDescriptors(std::vector<Schema::Common::Resources::Layer> const &)
0x180014b2d  mov     r9, qword ptr [rsp+260h+var_230]
0x180014b32  mov     r8, rdi
0x180014b35  mov     rax, qword ptr [rsp+260h+var_230+8]
0x180014b3a  mov     rdx, rsi
0x180014b3d  sub     rax, r9
0x180014b40  mov     dword ptr [rsp+260h+var_238], r15d
0x180014b45  sar     rax, 5
0x180014b49  mov     rcx, r14
0x180014b4c  mov     [rsp+260h+var_240], eax; int
0x180014b50  call    cs:__imp_WcExportLayerEx
0x180014b57  nop     dword ptr [rax+rax+00h]
0x180014b5c  test    eax, eax
0x180014b5e  js      short loc_180014BD2
0x180014b60  lea     rcx, [rbp+160h+var_190]
0x180014b64  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180014b69  lea     rcx, [rsp+260h+var_230]
0x180014b6e  call    ??1?$vector@U_WC_LAYER_DESCRIPTOR@@V?$allocator@U_WC_LAYER_DESCRIPTOR@@@std@@@std@@QEAA@XZ; std::vector<_WC_LAYER_DESCRIPTOR>::~vector<_WC_LAYER_DESCRIPTOR>(void)
0x180014b73  lea     rcx, [rbp+160h+var_1D8]; this
0x180014b77  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x180014b7c  lea     rcx, [rbp+160h+var_1C0]; this
0x180014b80  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x180014b85  lea     rcx, [rbp+160h+var_1A8]; this
0x180014b89  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x180014b8e  lea     rcx, [rsp+260h+var_1F8]
0x180014b93  call    ?_Tidy@?$vector@ULayer@Resources@Common@Schema@@V?$allocator@ULayer@Resources@Common@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Common::Resources::Layer>::_Tidy(void)
0x180014b98  lea     rcx, [rbp+160h+var_190]
0x180014b9c  mov     [rbp+160h+var_190], r12
0x180014ba0  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180014ba5  lea     rcx, [rbp+160h+var_190]
0x180014ba9  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180014bae  xor     eax, eax
0x180014bb0  mov     rcx, [rbp+160h+var_40]
0x180014bb7  xor     rcx, rsp; StackCookie
0x180014bba  call    __security_check_cookie
0x180014bbf  add     rsp, 230h
0x180014bc6  pop     r15
0x180014bc8  pop     r14
0x180014bca  pop     r12
0x180014bcc  pop     rdi
0x180014bcd  pop     rsi
0x180014bce  pop     rbx
0x180014bcf  pop     rbp
0x180014bd0  retn
0x180014bd2  mov     rcx, [rbp+168h]; this
0x180014bd9  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\dll\\storage\\src"...
0x180014be0  mov     r9d, eax; char *
0x180014be3  mov     edx, 9Ah; void *
0x180014be8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180014bee  mov     rcx, [rbp+168h]; this
0x180014bf5  lea     rax, aFailedToExport; "Failed to export layer: Export folder d"...
0x180014bfc  mov     r9d, 2; char *
0x180014c02  mov     qword ptr [rsp+260h+var_240], rax; unsigned int
0x180014c07  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\dll\\storage\\src"...
0x180014c0e  mov     edx, 87h; void *
0x180014c13  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
