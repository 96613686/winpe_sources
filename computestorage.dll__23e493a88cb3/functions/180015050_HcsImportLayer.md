# HcsImportLayer

- ea: `0x180015050`
- end: `0x1800152c3`
- name: `HcsImportLayer`
- size: `627`
- prototype: `HRESULT __stdcall(PCWSTR layerPath, PCWSTR sourceFolderPath, PCWSTR layerData)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002690`
- `0x1800032b8`
- `0x180004aac`
- `0x1800084b4`
- `0x1800084c0`
- `0x180008a8c`
- `0x180008ce8`
- `0x1800092d8`
- `0x18000971c`
- `0x18000a678`
- `0x18000a964`
- `0x18000fbc8`
- `0x18000ffd4`
- `0x1800127bc`
- `0x180012818`
- `0x1800137fc`
- `0x180015050`
- `0x18001a538`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800150ca`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800150ca`
- `wc_storage!WcImportLayerEx` at `0x1800151bf`
- `wc_storage!WcImportLayerEx` at `0x1800151bf`

## string_xrefs

- `0x180015096`: `ComputeStorage_HcsImportLayer`
- `0x18001527a`: `onecore\vm\compute\dll\storage\src\layer.cpp`
- `0x18001529b`: `onecore\vm\compute\dll\storage\src\layer.cpp`
- `0x1800152b0`: `onecore\vm\compute\dll\storage\src\layer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
HRESULT __stdcall HcsImportLayer(PCWSTR layerPath, PCWSTR sourceFolderPath, PCWSTR layerData)
{
  BOOL v6; // eax
  const unsigned __int16 *v7; // rdx
  signed int DirectoryW; // eax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  const char *v13; // r9
  __int64 v14; // rdx
  __int64 v15; // r8
  const char *v16; // r9
  const char *v17; // r9
  HRESULT result; // eax
  unsigned int v19; // eax
  int v20; // [rsp+20h] [rbp-218h]
  __int128 v21; // [rsp+40h] [rbp-1F8h] BYREF
  __int64 v22; // [rsp+50h] [rbp-1E8h]
  __int64 v23; // [rsp+60h] [rbp-1D8h] BYREF
  __int128 v24; // [rsp+68h] [rbp-1D0h] BYREF
  __int64 v25; // [rsp+78h] [rbp-1C0h]
  int v26; // [rsp+80h] [rbp-1B8h]
  __int128 v27; // [rsp+88h] [rbp-1B0h] BYREF
  __int64 v28; // [rsp+98h] [rbp-1A0h]
  __int128 v29; // [rsp+A0h] [rbp-198h] BYREF
  __int64 v30; // [rsp+B0h] [rbp-188h]
  _QWORD v31[42]; // [rsp+C0h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  memset_0(v31, 0, sizeof(v31));
  wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v31,
    (__int64)"ComputeStorage_HcsImportLayer");
  v31[0] = &ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsImportLayer::`vftable';
  ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsImportLayer::StartActivity((ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsImportLayer *)v31);
  v6 = PathFileExistsW(sourceFolderPath);
  try
  {
    if ( !v6 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x29,
        (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
        (const char *)2,
        v20);
    DirectoryW = Vml::CreateDirectoryW(layerPath, v7);
    if ( DirectoryW < 0 )
    {
      v19 = wil::verify_hresult<long>(DirectoryW);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x31,
        (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
        (const char *)v19,
        v20);
    }
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v9 = -1;
    do
      ++v9;
    while ( layerData[v9] );
    *(_QWORD *)&v21 = layerData;
    *((_QWORD *)&v21 + 1) = v9;
    ComputeService::MarshalUtilities::FromJsonStrictThrow<Schema::LayerManagement::LayerData,>(&v21, (__int64)&v23);
    v21 = 0;
    v22 = 0;
    ComputeStorageInternal::ConvertLayerDescriptors(&v21, (__int128 **)&v24);
    v29 = 0;
    v30 = 0;
    Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v29, 17);
    v27 = 0;
    v28 = 0;
    Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v27, 18);
    v10 = WcImportLayerEx(sourceFolderPath, layerPath, v21, (__int64)(*((_QWORD *)&v21 + 1) - v21) >> 5);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
        (const char *)(unsigned int)v10,
        0);
    Vml::TemporaryPrivilege::~TemporaryPrivilege((const struct _LUID *)&v27, v11, v12, v13);
    Vml::TemporaryPrivilege::~TemporaryPrivilege((const struct _LUID *)&v29, v14, v15, v16);
    std::vector<_WC_LAYER_DESCRIPTOR>::~vector<_WC_LAYER_DESCRIPTOR>((char **)&v21);
    wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v31);
    std::vector<Schema::Common::Resources::Layer>::_Tidy((char ***)&v24);
    v31[0] = &ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsImportLayer::`vftable';
    wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v31);
    wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v31);
    result = 0;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x48,
             (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
             v17);
  }
  return result;
}

```

## disassembly

```asm
0x180015050  mov     [rsp+arg_10], rbx
0x180015055  mov     [rsp+arg_18], rsi
0x18001505a  push    rdi
0x18001505b  push    r14
0x18001505d  push    r15
0x18001505f  sub     rsp, 220h
0x180015066  mov     rax, cs:__security_cookie
0x18001506d  xor     rax, rsp
0x180015070  mov     [rsp+238h+var_28], rax
0x180015078  mov     rbx, r8
0x18001507b  mov     rsi, rdx
0x18001507e  mov     rdi, rcx
0x180015081  xor     edx, edx; Val
0x180015083  mov     r8d, 150h; Size
0x180015089  lea     rcx, [rsp+238h+var_178]; void *
0x180015091  call    memset_0
0x180015096  lea     rdx, aComputestorage_7; "ComputeStorage_HcsImportLayer"
0x18001509d  lea     rcx, [rsp+238h+var_178]
0x1800150a5  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800150aa  lea     r15, ??_7ComputeStorage_HcsImportLayer@TraceProvider@Diagnostics@ComputeStorage@@6B@; const ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsImportLayer::`vftable'
0x1800150b1  mov     [rsp+238h+var_178], r15
0x1800150b9  lea     rcx, [rsp+238h+var_178]; this
0x1800150c1  call    ?StartActivity@ComputeStorage_HcsImportLayer@TraceProvider@Diagnostics@ComputeStorage@@QEAAXXZ; ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsImportLayer::StartActivity(void)
0x1800150c6  nop
0x1800150c7  mov     rcx, rsi; pszPath
0x1800150ca  call    cs:__imp_PathFileExistsW
0x1800150d1  nop     dword ptr [rax+rax+00h]
0x1800150d6  xor     r14d, r14d
0x1800150d9  test    eax, eax
0x1800150db  jz      loc_18001526E
0x1800150e1  mov     rcx, rdi; lpPathName
0x1800150e4  call    ?CreateDirectoryW@Vml@@YAKPEBG@Z; Vml::CreateDirectoryW(ushort const *)
0x1800150e9  test    eax, eax
0x1800150eb  js      loc_180015289
0x1800150f1  mov     [rsp+238h+var_1D8], r14
0x1800150f6  xorps   xmm0, xmm0
0x1800150f9  movdqu  [rsp+238h+var_1D0], xmm0
0x1800150ff  mov     [rsp+238h+var_1C0], r14
0x180015104  mov     [rsp+238h+var_1B8], r14d
0x18001510c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015110  inc     rax
0x180015113  cmp     [rbx+rax*2], r14w
0x180015118  jnz     short loc_180015110
0x18001511a  mov     qword ptr [rsp+238h+var_1F8], rbx
0x18001511f  mov     qword ptr [rsp+238h+var_1F8+8], rax
0x180015124  lea     rdx, [rsp+238h+var_1D8]
0x180015129  lea     rcx, [rsp+238h+var_1F8]
0x18001512e  call    ??$FromJsonStrictThrow@ULayerData@LayerManagement@Schema@@$$V@MarshalUtilities@ComputeService@@YAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAULayerData@LayerManagement@Schema@@W4UnmarshalFlags@Marshal@@@Z; ComputeService::MarshalUtilities::FromJsonStrictThrow<Schema::LayerManagement::LayerData,>(std::basic_string_view<ushort>,Schema::LayerManagement::LayerData *,Marshal::UnmarshalFlags)
0x180015133  xorps   xmm0, xmm0
0x180015136  xor     eax, eax
0x180015138  movups  [rsp+238h+var_1F8], xmm0
0x18001513d  mov     [rsp+238h+var_1E8], rax
0x180015142  lea     rdx, [rsp+238h+var_1D0]
0x180015147  lea     rcx, [rsp+238h+var_1F8]
0x18001514c  call    ?ConvertLayerDescriptors@ComputeStorageInternal@@YA?AV?$vector@U_WC_LAYER_DESCRIPTOR@@V?$allocator@U_WC_LAYER_DESCRIPTOR@@@std@@@std@@AEBV?$vector@ULayer@Resources@Common@Schema@@V?$allocator@ULayer@Resources@Common@Schema@@@std@@@3@@Z; ComputeStorageInternal::ConvertLayerDescriptors(std::vector<Schema::Common::Resources::Layer> const &)
0x180015151  nop
0x180015152  xorps   xmm0, xmm0
0x180015155  xor     eax, eax
0x180015157  movups  [rsp+238h+var_198], xmm0
0x18001515f  mov     [rsp+238h+var_188], rax
0x180015167  lea     edx, [rax+11h]; int
0x18001516a  lea     rcx, [rsp+238h+var_198]; this
0x180015172  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x180015177  nop
0x180015178  xorps   xmm0, xmm0
0x18001517b  xor     eax, eax
0x18001517d  movups  [rsp+238h+var_1B0], xmm0
0x180015185  mov     [rsp+238h+var_1A0], rax
0x18001518d  lea     edx, [rax+12h]; int
0x180015190  lea     rcx, [rsp+238h+var_1B0]; this
0x180015198  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x18001519d  nop
0x18001519e  mov     r8, qword ptr [rsp+238h+var_1F8]
0x1800151a3  mov     r9, qword ptr [rsp+238h+var_1F8+8]
0x1800151a8  sub     r9, r8
0x1800151ab  sar     r9, 5
0x1800151af  mov     [rsp+238h+var_210], r14d
0x1800151b4  mov     [rsp+238h+var_218], r14d; int
0x1800151b9  mov     rdx, rdi
0x1800151bc  mov     rcx, rsi
0x1800151bf  call    cs:__imp_WcImportLayerEx
0x1800151c6  nop     dword ptr [rax+rax+00h]
0x1800151cb  mov     rcx, [rsp+238h]; this
0x1800151d3  test    eax, eax
0x1800151d5  js      loc_1800152AD
0x1800151db  lea     rcx, [rsp+238h+var_1B0]; this
0x1800151e3  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x1800151e8  nop
0x1800151e9  lea     rcx, [rsp+238h+var_198]; this
0x1800151f1  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x1800151f6  nop
0x1800151f7  lea     rcx, [rsp+238h+var_1F8]
0x1800151fc  call    ??1?$vector@U_WC_LAYER_DESCRIPTOR@@V?$allocator@U_WC_LAYER_DESCRIPTOR@@@std@@@std@@QEAA@XZ; std::vector<_WC_LAYER_DESCRIPTOR>::~vector<_WC_LAYER_DESCRIPTOR>(void)
0x180015201  lea     rcx, [rsp+238h+var_178]
0x180015209  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001520e  nop
0x18001520f  lea     rcx, [rsp+238h+var_1D0]
0x180015214  call    ?_Tidy@?$vector@ULayer@Resources@Common@Schema@@V?$allocator@ULayer@Resources@Common@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Common::Resources::Layer>::_Tidy(void)
0x180015219  nop
0x18001521a  mov     [rsp+238h+var_178], r15
0x180015222  lea     rcx, [rsp+238h+var_178]
0x18001522a  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001522f  lea     rcx, [rsp+238h+var_178]
0x180015237  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001523c  xor     eax, eax
0x18001523e  jmp     short loc_180015244
0x180015240  mov     eax, [rsp+238h+var_208]
0x180015244  mov     rcx, [rsp+238h+var_28]
0x18001524c  xor     rcx, rsp; StackCookie
0x18001524f  call    __security_check_cookie
0x180015254  lea     r11, [rsp+238h+var_18]
0x18001525c  mov     rbx, [r11+30h]
0x180015260  mov     rsi, [r11+38h]
0x180015264  mov     rsp, r11
0x180015267  pop     r15
0x180015269  pop     r14
0x18001526b  pop     rdi
0x18001526c  retn
0x18001526e  mov     rcx, [rsp+238h]; this
0x180015276  lea     r9d, [r14+2]; char *
0x18001527a  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\dll\\storage\\src"...
0x180015281  lea     edx, [rax+29h]; void *
0x180015284  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180015289  mov     ecx, eax
0x18001528b  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180015290  mov     r9d, eax; char *
0x180015293  mov     rcx, [rsp+238h]; this
0x18001529b  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\dll\\storage\\src"...
0x1800152a2  mov     edx, 31h ; '1'; void *
0x1800152a7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800152ad  mov     r9d, eax; char *
0x1800152b0  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\dll\\storage\\src"...
0x1800152b7  mov     edx, 42h ; 'B'; void *
0x1800152bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
