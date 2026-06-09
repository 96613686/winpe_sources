# HcsExportLayer

- ea: `0x1800146e0`
- end: `0x1800149f3`
- name: `HcsExportLayer`
- size: `787`
- prototype: `HRESULT __stdcall(PCWSTR layerPath, PCWSTR exportFolderPath, PCWSTR layerData, PCWSTR options)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002690`
- `0x1800032b8`
- `0x1800049a4`
- `0x180004aac`
- `0x1800084c0`
- `0x180008a8c`
- `0x180008ce8`
- `0x180008fac`
- `0x1800092d8`
- `0x18000971c`
- `0x18000a578`
- `0x18000a964`
- `0x18000f838`
- `0x18000ffd4`
- `0x1800127bc`
- `0x180012838`
- `0x1800137fc`
- `0x1800146e0`
- `0x18001a538`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180014761`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180014761`
- `wc_storage!WcExportLayerEx` at `0x1800148e2`
- `wc_storage!WcExportLayerEx` at `0x1800148e2`

## string_xrefs

- `0x18001472d`: `ComputeStorage_HcsExportLayer`
- `0x1800149cb`: `onecore\vm\compute\dll\storage\src\layer.cpp`
- `0x1800149e0`: `onecore\vm\compute\dll\storage\src\layer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
HRESULT __stdcall HcsExportLayer(PCWSTR layerPath, PCWSTR exportFolderPath, PCWSTR layerData, PCWSTR options)
{
  BOOL v8; // eax
  __int64 v9; // rbx
  __int64 v10; // rax
  PCWSTR v11; // rcx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  const char *v15; // r9
  __int64 v16; // rdx
  __int64 v17; // r8
  const char *v18; // r9
  __int64 v19; // rdx
  __int64 v20; // r8
  const char *v21; // r9
  const char *v22; // r9
  HRESULT result; // eax
  int v24; // [rsp+20h] [rbp-268h]
  const char *v25; // [rsp+28h] [rbp-260h]
  __int128 v26; // [rsp+40h] [rbp-248h] BYREF
  __int128 v27; // [rsp+50h] [rbp-238h] BYREF
  __int64 v28; // [rsp+60h] [rbp-228h]
  _BYTE v29[8]; // [rsp+68h] [rbp-220h] BYREF
  __int64 v30; // [rsp+70h] [rbp-218h] BYREF
  __int128 v31; // [rsp+78h] [rbp-210h] BYREF
  __int64 v32; // [rsp+88h] [rbp-200h]
  int v33; // [rsp+90h] [rbp-1F8h]
  __int128 v34; // [rsp+98h] [rbp-1F0h] BYREF
  __int64 v35; // [rsp+A8h] [rbp-1E0h]
  __int128 v36; // [rsp+B0h] [rbp-1D8h] BYREF
  __int64 v37; // [rsp+C0h] [rbp-1C8h]
  __int128 v38; // [rsp+C8h] [rbp-1C0h] BYREF
  __int64 v39; // [rsp+D8h] [rbp-1B0h]
  char *Src[4]; // [rsp+E0h] [rbp-1A8h] BYREF
  _QWORD v41[42]; // [rsp+100h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  memset_0(v41, 0, sizeof(v41));
  wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v41,
    (__int64)"ComputeStorage_HcsExportLayer");
  v41[0] = &ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLayer::`vftable';
  ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLayer::StartActivity((ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLayer *)v41);
  v8 = PathFileExistsW(exportFolderPath);
  try
  {
    if ( !v8 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
        (const char *)2,
        (unsigned int)"Failed to export layer: Export folder doesn't exist!.",
        v25);
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( layerData[v10] );
    *(_QWORD *)&v26 = layerData;
    *((_QWORD *)&v26 + 1) = v10;
    ComputeService::MarshalUtilities::FromJsonStrictThrow<Schema::LayerManagement::LayerData,>(&v26, (__int64)&v30);
    v29[0] = 0;
    do
      ++v9;
    while ( options[v9] );
    *(_QWORD *)&v26 = options;
    *((_QWORD *)&v26 + 1) = v9;
    ComputeService::MarshalUtilities::FromJsonStrictThrow<Schema::Options::ExportLayerOptions,>(&v26, (__int64)v29);
    v38 = 0;
    v39 = 0;
    Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v38, 17);
    v36 = 0;
    v37 = 0;
    Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v36, 18);
    v34 = 0;
    v35 = 0;
    Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v34, 8);
    Vml::CombineFilePath(Src, layerPath, L"WcSandboxState");
    v27 = 0;
    v28 = 0;
    ComputeStorageInternal::ConvertLayerDescriptors(&v27, (__int128 **)&v31);
    if ( v29[0] )
    {
      v11 = (PCWSTR)Src;
      if ( Src[3] > (char *)7 )
        v11 = (PCWSTR)Src[0];
    }
    else
    {
      v11 = layerPath;
    }
    v24 = (__int64)(*((_QWORD *)&v27 + 1) - v27) >> 5;
    v12 = WcExportLayerEx(v11, (unsigned __int64)layerPath & -(__int64)(v29[0] != 0), exportFolderPath);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
        (const char *)(unsigned int)v12,
        v24);
    wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v41);
    std::vector<_WC_LAYER_DESCRIPTOR>::~vector<_WC_LAYER_DESCRIPTOR>((char **)&v27);
    std::wstring::~wstring(Src);
    Vml::TemporaryPrivilege::~TemporaryPrivilege((const struct _LUID *)&v34, v13, v14, v15);
    Vml::TemporaryPrivilege::~TemporaryPrivilege((const struct _LUID *)&v36, v16, v17, v18);
    Vml::TemporaryPrivilege::~TemporaryPrivilege((const struct _LUID *)&v38, v19, v20, v21);
    std::vector<Schema::Common::Resources::Layer>::_Tidy((char ***)&v31);
    v41[0] = &ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLayer::`vftable';
    wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v41);
    wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v41);
    result = 0;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x76,
             (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
             v22);
  }
  return result;
}

```

## disassembly

```asm
0x1800146e0  mov     [rsp+arg_10], rbx
0x1800146e5  mov     [rsp+arg_18], rsi
0x1800146ea  push    rdi
0x1800146eb  push    r12
0x1800146ed  push    r13
0x1800146ef  push    r14
0x1800146f1  push    r15
0x1800146f3  sub     rsp, 260h
0x1800146fa  mov     rax, cs:__security_cookie
0x180014701  xor     rax, rsp
0x180014704  mov     [rsp+288h+var_38], rax
0x18001470c  mov     r14, r9
0x18001470f  mov     rsi, r8
0x180014712  mov     r15, rdx
0x180014715  mov     rdi, rcx
0x180014718  xor     edx, edx; Val
0x18001471a  mov     r8d, 150h; Size
0x180014720  lea     rcx, [rsp+288h+var_188]; void *
0x180014728  call    memset_0
0x18001472d  lea     rdx, aComputestorage_8; "ComputeStorage_HcsExportLayer"
0x180014734  lea     rcx, [rsp+288h+var_188]
0x18001473c  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180014741  lea     r13, ??_7ComputeStorage_HcsExportLayer@TraceProvider@Diagnostics@ComputeStorage@@6B@; const ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLayer::`vftable'
0x180014748  mov     [rsp+288h+var_188], r13
0x180014750  lea     rcx, [rsp+288h+var_188]; this
0x180014758  call    ?StartActivity@ComputeStorage_HcsExportLayer@TraceProvider@Diagnostics@ComputeStorage@@QEAAXXZ; ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLayer::StartActivity(void)
0x18001475d  nop
0x18001475e  mov     rcx, r15; pszPath
0x180014761  call    cs:__imp_PathFileExistsW
0x180014768  nop     dword ptr [rax+rax+00h]
0x18001476d  xor     r12d, r12d
0x180014770  test    eax, eax
0x180014772  jz      loc_1800149B2
0x180014778  mov     [rsp+288h+var_218], r12
0x18001477d  xorps   xmm0, xmm0
0x180014780  movdqu  [rsp+288h+var_210], xmm0
0x180014786  mov     [rsp+288h+var_200], r12
0x18001478e  mov     [rsp+288h+var_1F8], r12d
0x180014796  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001479a  mov     rax, rbx
0x18001479d  inc     rax
0x1800147a0  cmp     [rsi+rax*2], r12w
0x1800147a5  jnz     short loc_18001479D
0x1800147a7  mov     [rsp+288h+var_248], rsi
0x1800147ac  mov     [rsp+288h+var_240], rax
0x1800147b1  lea     rdx, [rsp+288h+var_218]
0x1800147b6  lea     rcx, [rsp+288h+var_248]
0x1800147bb  call    ??$FromJsonStrictThrow@ULayerData@LayerManagement@Schema@@$$V@MarshalUtilities@ComputeService@@YAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAULayerData@LayerManagement@Schema@@W4UnmarshalFlags@Marshal@@@Z; ComputeService::MarshalUtilities::FromJsonStrictThrow<Schema::LayerManagement::LayerData,>(std::basic_string_view<ushort>,Schema::LayerManagement::LayerData *,Marshal::UnmarshalFlags)
0x1800147c0  mov     [rsp+288h+var_220], r12b
0x1800147c5  inc     rbx
0x1800147c8  cmp     [r14+rbx*2], r12w
0x1800147cd  jnz     short loc_1800147C5
0x1800147cf  mov     [rsp+288h+var_248], r14
0x1800147d4  mov     [rsp+288h+var_240], rbx
0x1800147d9  lea     rdx, [rsp+288h+var_220]
0x1800147de  lea     rcx, [rsp+288h+var_248]
0x1800147e3  call    ??$FromJsonStrictThrow@UExportLayerOptions@Options@Schema@@$$V@MarshalUtilities@ComputeService@@YAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAUExportLayerOptions@Options@Schema@@W4UnmarshalFlags@Marshal@@@Z; ComputeService::MarshalUtilities::FromJsonStrictThrow<Schema::Options::ExportLayerOptions,>(std::basic_string_view<ushort>,Schema::Options::ExportLayerOptions *,Marshal::UnmarshalFlags)
0x1800147e8  xorps   xmm0, xmm0
0x1800147eb  xor     eax, eax
0x1800147ed  movups  [rsp+288h+var_1C0], xmm0
0x1800147f5  mov     [rsp+288h+var_1B0], rax
0x1800147fd  lea     edx, [rax+11h]; int
0x180014800  lea     rcx, [rsp+288h+var_1C0]; this
0x180014808  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x18001480d  nop
0x18001480e  xorps   xmm0, xmm0
0x180014811  xor     eax, eax
0x180014813  movups  [rsp+288h+var_1D8], xmm0
0x18001481b  mov     [rsp+288h+var_1C8], rax
0x180014823  lea     edx, [rax+12h]; int
0x180014826  lea     rcx, [rsp+288h+var_1D8]; this
0x18001482e  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x180014833  nop
0x180014834  xorps   xmm0, xmm0
0x180014837  xor     eax, eax
0x180014839  movups  [rsp+288h+var_1F0], xmm0
0x180014841  mov     [rsp+288h+var_1E0], rax
0x180014849  lea     edx, [rax+8]; int
0x18001484c  lea     rcx, [rsp+288h+var_1F0]; this
0x180014854  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x180014859  nop
0x18001485a  lea     r8, aWcsandboxstate; "WcSandboxState"
0x180014861  mov     rdx, rdi; pszPathIn
0x180014864  lea     rcx, [rsp+288h+Src]; Src
0x18001486c  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x180014871  nop
0x180014872  xorps   xmm0, xmm0
0x180014875  xor     eax, eax
0x180014877  movups  [rsp+288h+var_238], xmm0
0x18001487c  mov     [rsp+288h+var_228], rax
0x180014881  lea     rdx, [rsp+288h+var_210]
0x180014886  lea     rcx, [rsp+288h+var_238]
0x18001488b  call    ?ConvertLayerDescriptors@ComputeStorageInternal@@YA?AV?$vector@U_WC_LAYER_DESCRIPTOR@@V?$allocator@U_WC_LAYER_DESCRIPTOR@@@std@@@std@@AEBV?$vector@ULayer@Resources@Common@Schema@@V?$allocator@ULayer@Resources@Common@Schema@@@std@@@3@@Z; ComputeStorageInternal::ConvertLayerDescriptors(std::vector<Schema::Common::Resources::Layer> const &)
0x180014890  nop
0x180014891  mov     r9, qword ptr [rsp+288h+var_238]
0x180014896  mov     rdx, qword ptr [rsp+288h+var_238+8]
0x18001489b  sub     rdx, r9
0x18001489e  sar     rdx, 5
0x1800148a2  mov     al, [rsp+288h+var_220]
0x1800148a6  mov     cl, al
0x1800148a8  neg     cl
0x1800148aa  sbb     r10, r10
0x1800148ad  and     r10, rdi
0x1800148b0  test    al, al
0x1800148b2  jz      short loc_1800148D0
0x1800148b4  lea     rcx, [rsp+288h+Src]
0x1800148bc  cmp     [rsp+288h+var_190], 7
0x1800148c5  cmova   rcx, [rsp+288h+Src]
0x1800148ce  jmp     short loc_1800148D3
0x1800148d0  mov     rcx, rdi
0x1800148d3  mov     dword ptr [rsp+288h+var_260], r12d
0x1800148d8  mov     [rsp+288h+var_268], edx; int
0x1800148dc  mov     r8, r15
0x1800148df  mov     rdx, r10
0x1800148e2  call    cs:__imp_WcExportLayerEx
0x1800148e9  nop     dword ptr [rax+rax+00h]
0x1800148ee  mov     rcx, [rsp+288h]; this
0x1800148f6  test    eax, eax
0x1800148f8  js      loc_1800149DD
0x1800148fe  lea     rcx, [rsp+288h+var_188]
0x180014906  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001490b  nop
0x18001490c  lea     rcx, [rsp+288h+var_238]
0x180014911  call    ??1?$vector@U_WC_LAYER_DESCRIPTOR@@V?$allocator@U_WC_LAYER_DESCRIPTOR@@@std@@@std@@QEAA@XZ; std::vector<_WC_LAYER_DESCRIPTOR>::~vector<_WC_LAYER_DESCRIPTOR>(void)
0x180014916  nop
0x180014917  lea     rcx, [rsp+288h+Src]
0x18001491f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014924  nop
0x180014925  lea     rcx, [rsp+288h+var_1F0]; this
0x18001492d  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x180014932  nop
0x180014933  lea     rcx, [rsp+288h+var_1D8]; this
0x18001493b  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x180014940  nop
0x180014941  lea     rcx, [rsp+288h+var_1C0]; this
0x180014949  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x18001494e  nop
0x18001494f  lea     rcx, [rsp+288h+var_210]
0x180014954  call    ?_Tidy@?$vector@ULayer@Resources@Common@Schema@@V?$allocator@ULayer@Resources@Common@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Common::Resources::Layer>::_Tidy(void)
0x180014959  nop
0x18001495a  mov     [rsp+288h+var_188], r13
0x180014962  lea     rcx, [rsp+288h+var_188]
0x18001496a  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001496f  lea     rcx, [rsp+288h+var_188]
0x180014977  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001497c  xor     eax, eax
0x18001497e  jmp     short loc_180014984
0x180014980  mov     eax, [rsp+288h+var_258]
0x180014984  mov     rcx, [rsp+288h+var_38]
0x18001498c  xor     rcx, rsp; StackCookie
0x18001498f  call    __security_check_cookie
0x180014994  lea     r11, [rsp+288h+var_28]
0x18001499c  mov     rbx, [r11+40h]
0x1800149a0  mov     rsi, [r11+48h]
0x1800149a4  mov     rsp, r11
0x1800149a7  pop     r15
0x1800149a9  pop     r14
0x1800149ab  pop     r13
0x1800149ad  pop     r12
0x1800149af  pop     rdi
0x1800149b0  retn
0x1800149b2  mov     rcx, [rsp+288h]; this
0x1800149ba  lea     rax, aFailedToExport; "Failed to export layer: Export folder d"...
0x1800149c1  mov     qword ptr [rsp+288h+var_268], rax; unsigned int
0x1800149c6  lea     r9d, [r12+2]; char *
0x1800149cb  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\dll\\storage\\src"...
0x1800149d2  lea     edx, [r12+59h]; void *
0x1800149d7  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800149dd  mov     r9d, eax; char *
0x1800149e0  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\dll\\storage\\src"...
0x1800149e7  mov     edx, 71h ; 'q'; void *
0x1800149ec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
