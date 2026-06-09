# OsImageUtilities::ProcessOsLayer(ushort const *,PartitionInfo const &,Schema::Options::OsLayerOptions const &)

- ea: `0x18001ea88`
- end: `0x18001f062`
- name: `?ProcessOsLayer@OsImageUtilities@@YAXPEBGAEBUPartitionInfo@@AEBUOsLayerOptions@Options@Schema@@@Z`
- size: `1498`
- prototype: `void __fastcall(PCWSTR pszPathIn, const WCHAR *, const struct PartitionInfo *, const struct Schema::Options::OsLayerOptions *)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180015670`
- `0x180015910`

## callees

- `0x180002690`
- `0x1800032b8`
- `0x1800084b4`
- `0x180008a8c`
- `0x180008fac`
- `0x1800092d8`
- `0x18000971c`
- `0x18000a578`
- `0x18000cab0`
- `0x1800127bc`
- `0x1800127dc`
- `0x1800136f8`
- `0x18001a398`
- `0x18001a9c8`
- `0x18001bfa0`
- `0x18001c3d0`
- `0x18001c5d4`
- `0x18001db70`
- `0x18001ddc0`
- `0x18001dfe4`
- `0x18001e844`
- `0x18001ea88`
- `0x1800203a8`
- `0x180020880`
- `0x180020b40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ece4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ece4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001ed49`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001ed49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ed71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ed71`

## string_xrefs

- `0x18001eb97`: `ComputeStorage_ProcessOsLayer`
- `0x18001eff6`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18001f02c`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18001f03e`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18001f050`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall OsImageUtilities::ProcessOsLayer(
        PCWSTR pszPathIn,
        const WCHAR *a2,
        const struct PartitionInfo *a3,
        const struct Schema::Options::OsLayerOptions *a4)
{
  __m256i *v7; // rax
  const unsigned __int16 *v8; // rdx
  OsImageUtilities::Helpers *v9; // rax
  const unsigned __int16 *v10; // rdx
  __int64 v11; // rax
  char *FileW; // rbx
  const char *v13; // r9
  LPCVOID *v14; // rdx
  const char *v15; // r9
  OsImageUtilities::Helpers *v16; // rcx
  const unsigned __int16 *v17; // rdx
  BOOL v18; // r15d
  wchar_t **v19; // rcx
  _OWORD *v20; // xmm1_8
  __int128 *v21; // r14
  __int128 *i; // rbx
  __int128 v23; // xmm1
  _QWORD *v24; // rax
  __int64 v25; // rdx
  const WCHAR *v26; // rdx
  PCWSTR *v27; // rdx
  _QWORD *v28; // rcx
  const unsigned __int16 *v29; // rdx
  const WCHAR *v30; // rcx
  const struct PartitionInfo *v31; // r8
  const WCHAR *v32; // rcx
  unsigned int v33; // eax
  unsigned int v34; // eax
  int v35; // edx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  __m256i v38; // [rsp+40h] [rbp-C0h] BYREF
  char *v39; // [rsp+60h] [rbp-A0h]
  __int128 v40; // [rsp+68h] [rbp-98h] BYREF
  __int128 v41; // [rsp+78h] [rbp-88h] BYREF
  __int64 v42; // [rsp+88h] [rbp-78h]
  __int128 v43; // [rsp+90h] [rbp-70h]
  DWORD NumberOfBytesWritten[4]; // [rsp+A0h] [rbp-60h] BYREF
  PCWSTR pszPathIna[3]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v46; // [rsp+C8h] [rbp-38h]
  __int128 Src; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v48; // [rsp+E0h] [rbp-20h]
  __int128 v49; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v50; // [rsp+100h] [rbp+0h]
  _QWORD v51[4]; // [rsp+110h] [rbp+10h] BYREF
  void **v52; // [rsp+130h] [rbp+30h] BYREF
  int v53; // [rsp+138h] [rbp+38h] BYREF
  char v54; // [rsp+13Ch] [rbp+3Ch]
  int v55; // [rsp+160h] [rbp+60h] BYREF
  const char *v56; // [rsp+168h] [rbp+68h]
  __int64 v57; // [rsp+170h] [rbp+70h]
  char v58; // [rsp+178h] [rbp+78h]
  int v59; // [rsp+180h] [rbp+80h]
  _BYTE v60[152]; // [rsp+188h] [rbp+88h] BYREF
  __int128 v61; // [rsp+220h] [rbp+120h]
  int v62; // [rsp+230h] [rbp+130h]
  __int64 v63; // [rsp+238h] [rbp+138h]
  int *v64; // [rsp+240h] [rbp+140h]
  __int64 v65; // [rsp+248h] [rbp+148h]
  __int64 v66; // [rsp+250h] [rbp+150h]
  void ***v67; // [rsp+258h] [rbp+158h]
  __int64 v68; // [rsp+260h] [rbp+160h]
  int v69; // [rsp+268h] [rbp+168h]
  int *v70; // [rsp+270h] [rbp+170h]
  char v71; // [rsp+278h] [rbp+178h]
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  memset_0(&v52, 0, 0x150u);
  NumberOfBytesWritten[0] = 0;
  *(_OWORD *)v38.m256i_i8 = 0;
  *(__m128i *)&v38.m256i_u64[2] = _mm_load_si128((const __m128i *)&_xmm);
  v38.m256i_i16[0] = 0;
  LODWORD(v39) = 1;
  *(_QWORD *)&Src = &v38;
  BYTE8(Src) = 0;
  v51[0] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<enum Schema::Options::OsLayerType,bool,bool,bool,bool,Marshal::ModifiedType<std::vector<Schema::Common::Resources::Layer>,Marshal::ModifierList<>>,_GUID>,Marshal::Details::JsonTypeData,Marshal::Details::JsonTypeInfo>::Value;
  v51[1] = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<bool>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  pszPathIna[0] = (PCWSTR)Marshal::Details::ObjectTypeInfo<Marshal::TypeList<enum Schema::Options::OsLayerType,bool,bool,bool,bool,Marshal::ModifiedType<std::vector<Schema::Common::Resources::Layer>,Marshal::ModifierList<>>,_GUID>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
  pszPathIna[1] = (PCWSTR)Marshal::Details::ObjectTypeInfo<Marshal::TypeList<unsigned int,unsigned int>,Marshal::Details::JsonTypeData,Marshal::Details::JsonTypeInfo>::Value;
  *(_QWORD *)&v49 = Schema::Options::OsLayerOptions_ClassData;
  *((_QWORD *)&v49 + 1) = Schema::Options::OsLayerOptions_ClassData + 224LL;
  Marshal::Details::ObjectToJson(
    (unsigned int)&Src,
    (_DWORD)a3,
    (unsigned int)NumberOfBytesWritten,
    (unsigned int)&v49,
    (__int64)pszPathIna,
    (__int64)v51);
  v7 = &v38;
  if ( v38.m256i_i64[3] > 7uLL )
    v7 = (__m256i *)v38.m256i_i64[0];
  *(_QWORD *)NumberOfBytesWritten = v7;
  v53 = 0;
  v54 = 0;
  v58 = 0;
  v55 = 0;
  v56 = "ComputeStorage_ProcessOsLayer";
  v57 = 0;
  v59 = 0;
  v61 = 0;
  memset_0(v60, 0, sizeof(v60));
  v62 = 1;
  v63 = 0;
  v64 = &v53;
  v65 = 0;
  v66 = 0;
  v67 = &v52;
  v68 = 0;
  v69 = 0;
  v70 = &v55;
  v71 = 0;
  v52 = &ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer::`vftable';
  ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer::StartActivity<unsigned short const *>(
    &v52,
    NumberOfBytesWritten);
  std::wstring::~wstring(&v38);
  v8 = (const unsigned __int16 *)*(unsigned int *)a3;
  if ( (unsigned int)v8 > 1 )
  {
    v34 = wil::verify_hresult<long>(2147942487LL);
    LODWORD(dwFlagsAndAttributes) = v35;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x1D4,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)v34,
      (int)"Invalid LayerType: %x",
      dwFlagsAndAttributes);
  }
  if ( !*((_BYTE *)a3 + 4) )
  {
    v9 = (OsImageUtilities::Helpers *)Vml::CombineFilePath(&Src, pszPathIn, L"Files");
    if ( *((_QWORD *)v9 + 3) > 7u )
      v9 = *(OsImageUtilities::Helpers **)v9;
    OsImageUtilities::Helpers::OptimizeCiCache(v9, v10);
    std::wstring::~wstring(&Src);
  }
  if ( !*(_DWORD *)a3 )
    goto LABEL_11;
  if ( *(_DWORD *)a3 != 1 )
    goto LABEL_53;
  if ( *((_BYTE *)a3 + 6) )
  {
LABEL_11:
    OsImageUtilities::Helpers::CreateBaseHives(pszPathIn, v8);
    v11 = Vml::CombineFilePath(&Src, pszPathIn, L"layout");
    if ( *(_QWORD *)(v11 + 24) > 7u )
      v11 = *(_QWORD *)v11;
    FileW = (char *)CreateFileW((LPCWSTR)v11, 0x40000000u, 0, 0, 1u, 0, 0);
    v39 = FileW;
    std::wstring::~wstring(&Src);
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1EB,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
        v13);
    NumberOfBytesWritten[0] = 0;
    v14 = &lpBuffer;
    if ( (unsigned __int64)qword_18005FFB8 > 0xF )
      v14 = (LPCVOID *)lpBuffer;
    if ( !WriteFile(FileW, v14, nNumberOfBytesToWrite, NumberOfBytesWritten, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1EE,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
        v15);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
  }
  if ( *(_DWORD *)a3 == 1 )
  {
    Vml::CombineFilePath(pszPathIna, pszPathIn, L"Files");
    if ( !OsImageUtilities::Helpers::IsHostPreReleaseImageCapable(v16)
      && OsImageUtilities::Helpers::IsPreReleaseImage(pszPathIn, v17) )
    {
      v33 = wil::verify_hresult<long>(2151088403LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F9,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
        (const char *)v33,
        dwCreationDisposition);
    }
    v18 = !OsImageUtilities::Helpers::UseLegacyFilter(pszPathIn, v17);
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v38.m256i_i64[2] = 0;
    *(_OWORD *)v38.m256i_i8 = UTILITY_VM_LAYER_ID;
    if ( !*((_BYTE *)a3 + 7) )
    {
      if ( *((_BYTE *)a3 + 6) )
      {
        v38.m256i_i32[4] = 4;
        v19 = &off_18004ADF0;
        *(_QWORD *)&v40 = 2;
      }
      else
      {
        v19 = &off_18004AD40;
        *(_QWORD *)&v40 = 11;
      }
      *((_QWORD *)&v40 + 1) = v19;
    }
    v38.m256i_i64[3] = (__int64)pszPathIn;
    v20 = (_OWORD *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( v20 )
    {
      *v20 = UTILITY_VM_LAYER_ID;
      v20[1] = *(_OWORD *)&v38.m256i_u64[2];
      *((_QWORD *)&v41 + 1) += 32LL;
    }
    else
    {
      std::vector<_WC_LAYER_DESCRIPTOR>::_Emplace_reallocate<_WC_LAYER_DESCRIPTOR>(&v41, 0, &v38);
    }
    v21 = (__int128 *)*((_QWORD *)a3 + 2);
    for ( i = (__int128 *)*((_QWORD *)a3 + 1); i != v21; i = (__int128 *)((char *)i + 56) )
    {
      *(_OWORD *)&v38.m256i_u64[1] = 0;
      v23 = *i;
      *(_OWORD *)v38.m256i_i8 = *i;
      v24 = i + 1;
      if ( *((_QWORD *)i + 5) > 7u )
        v24 = (_QWORD *)*v24;
      v38.m256i_i64[3] = (__int64)v24;
      v25 = *((_QWORD *)&v41 + 1);
      if ( *((_QWORD *)&v41 + 1) == v42 )
      {
        std::vector<_WC_LAYER_DESCRIPTOR>::_Emplace_reallocate<_WC_LAYER_DESCRIPTOR>(&v41, *((_QWORD *)&v41 + 1), &v38);
      }
      else
      {
        **((_OWORD **)&v41 + 1) = v23;
        *(_OWORD *)(v25 + 16) = *(_OWORD *)&v38.m256i_u64[2];
        *((_QWORD *)&v41 + 1) += 32LL;
      }
    }
    v43 = *((_OWORD *)a3 + 2);
    v49 = 0;
    v50 = 0;
    Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v49, 17);
    Src = 0;
    v48 = 0;
    Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&Src, 18);
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v26 = a2;
    else
      v26 = *(const WCHAR **)a2;
    Vml::CombineFilePath(v51, v26, L"\\");
    v27 = pszPathIna;
    if ( v46 > 7 )
      v27 = (PCWSTR *)pszPathIna[0];
    v28 = v51;
    if ( v51[3] > 7u )
      v28 = (_QWORD *)v51[0];
    OsImageUtilities::Helpers::InitializeAndPopulateSandbox(v28, v27, &v40, v18);
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v30 = a2;
    else
      v30 = *(const WCHAR **)a2;
    OsImageUtilities::Helpers::CreateSandboxStateDirectory(v30, v29);
    if ( !*((_BYTE *)a3 + 5) )
    {
      v32 = (const WCHAR *)pszPathIna;
      if ( v46 > 7 )
        v32 = pszPathIna[0];
      OsImageUtilities::Helpers::UpdateBcdStore(v32, a2, v31);
    }
    std::wstring::~wstring(v51);
    Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)&Src);
    Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)&v49);
    std::vector<_WC_LAYER_DESCRIPTOR>::~vector<_WC_LAYER_DESCRIPTOR>(&v41);
    std::wstring::~wstring(pszPathIna);
  }
LABEL_53:
  wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,1,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v52);
  ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer::~ComputeStorage_ProcessOsLayer((ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer *)&v52);
}

```

## disassembly

```asm
0x18001ea88  push    rbp
0x18001ea8a  push    rbx
0x18001ea8b  push    rsi
0x18001ea8c  push    rdi
0x18001ea8d  push    r12
0x18001ea8f  push    r14
0x18001ea91  push    r15
0x18001ea93  lea     rbp, [rsp-190h]
0x18001ea9b  sub     rsp, 290h
0x18001eaa2  mov     rax, cs:__security_cookie
0x18001eaa9  xor     rax, rsp
0x18001eaac  mov     [rbp+1C0h+var_40], rax
0x18001eab3  mov     rdi, r8
0x18001eab6  mov     rsi, rdx
0x18001eab9  mov     r14, rcx
0x18001eabc  xor     r12d, r12d
0x18001eabf  mov     dword ptr [rsp+2C0h+var_260], r12d
0x18001eac4  xor     edx, edx; Val
0x18001eac6  mov     r8d, 150h; Size
0x18001eacc  lea     rcx, [rbp+1C0h+var_190]; void *
0x18001ead0  call    memset_0
0x18001ead5  nop
0x18001ead6  mov     [rbp+1C0h+NumberOfBytesWritten], r12d
0x18001eada  xorps   xmm0, xmm0
0x18001eadd  movups  [rsp+2C0h+var_280], xmm0
0x18001eae2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001eaea  movdqu  [rsp+2C0h+var_270], xmm1
0x18001eaf0  mov     word ptr [rsp+2C0h+var_280], r12w
0x18001eaf6  mov     dword ptr [rsp+2C0h+var_260], 1
0x18001eafe  lea     rax, [rsp+2C0h+var_280]
0x18001eb03  mov     qword ptr [rbp+1C0h+Src], rax
0x18001eb07  mov     byte ptr [rbp+1C0h+Src+8], r12b
0x18001eb0b  mov     rax, cs:?OsLayerOptions_ClassData@Options@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Options::OsLayerOptions_ClassData
0x18001eb12  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@W4OsLayerType@Options@Schema@@_N_N_N_NU?$ModifiedType@V?$vector@ULayer@Resources@Common@Schema@@V?$allocator@ULayer@Resources@Common@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U_GUID@@@Marshal@@UJsonTypeData@Details@2@UJsonTypeInfo@42@@Details@Marshal@@2V?$array@PEBUJsonTypeData@Details@Marshal@@$06@std@@A; std::array<Marshal::Details::JsonTypeData const *,7> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Options::OsLayerType,bool,bool,bool,bool,Marshal::ModifiedType<std::vector<Schema::Common::Resources::Layer>,Marshal::ModifierList<>>,_GUID>,Marshal::Details::JsonTypeData,Marshal::Details::JsonTypeInfo>::Value
0x18001eb19  mov     [rbp+1C0h+var_1B0], rcx
0x18001eb1d  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@_N@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::BaseTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<bool>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x18001eb24  mov     [rbp+1C0h+var_1A8], rcx
0x18001eb28  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@W4OsLayerType@Options@Schema@@_N_N_N_NU?$ModifiedType@V?$vector@ULayer@Resources@Common@Schema@@V?$allocator@ULayer@Resources@Common@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U_GUID@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$06@std@@A; std::array<Marshal::Details::BaseTypeData const *,7> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Options::OsLayerType,bool,bool,bool,bool,Marshal::ModifiedType<std::vector<Schema::Common::Resources::Layer>,Marshal::ModifierList<>>,_GUID>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x18001eb2f  mov     [rbp+1C0h+pszPathIn], rcx
0x18001eb33  lea     rcx, ?Value@?$ObjectTypeInfo@U?$TypeList@II@Marshal@@UJsonTypeData@Details@2@UJsonTypeInfo@42@@Details@Marshal@@2V?$array@PEBUJsonTypeData@Details@Marshal@@$01@std@@A; std::array<Marshal::Details::JsonTypeData const *,2> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<uint,uint>,Marshal::Details::JsonTypeData,Marshal::Details::JsonTypeInfo>::Value
0x18001eb3a  mov     [rbp+1C0h+var_208], rcx
0x18001eb3e  mov     qword ptr [rbp+1C0h+var_1D0], rax
0x18001eb42  add     rax, 0E0h
0x18001eb48  mov     qword ptr [rbp+1C0h+var_1D0+8], rax
0x18001eb4c  lea     rax, [rbp+1C0h+var_1B0]
0x18001eb50  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], rax
0x18001eb55  lea     rax, [rbp+1C0h+pszPathIn]
0x18001eb59  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rax
0x18001eb5e  lea     r9, [rbp+1C0h+var_1D0]
0x18001eb62  lea     r8, [rbp+1C0h+NumberOfBytesWritten]
0x18001eb66  mov     rdx, rdi
0x18001eb69  lea     rcx, [rbp+1C0h+Src]
0x18001eb6d  call    ?ObjectToJson@Details@Marshal@@YA_NAEAVJsonWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUJsonTypeData@Details@Marshal@@@12@@Z; Marshal::Details::ObjectToJson(Marshal::JsonWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::JsonTypeData const *>)
0x18001eb72  lea     rax, [rsp+2C0h+var_280]
0x18001eb77  cmp     qword ptr [rsp+2C0h+var_270+8], 7
0x18001eb7d  cmova   rax, qword ptr [rsp+2C0h+var_280]
0x18001eb83  mov     qword ptr [rbp+1C0h+NumberOfBytesWritten], rax
0x18001eb87  mov     [rbp+1C0h+var_188], r12d
0x18001eb8b  mov     [rbp+1C0h+var_184], r12b
0x18001eb8f  mov     [rbp+1C0h+var_148], r12b
0x18001eb93  mov     [rbp+1C0h+var_160], r12d
0x18001eb97  lea     rax, aComputestorage_1; "ComputeStorage_ProcessOsLayer"
0x18001eb9e  mov     [rbp+1C0h+var_158], rax
0x18001eba2  mov     [rbp+1C0h+var_150], r12
0x18001eba6  mov     [rbp+1C0h+var_140], r12d
0x18001ebad  xorps   xmm0, xmm0
0x18001ebb0  movdqa  [rbp+1C0h+var_A0], xmm0
0x18001ebb8  xor     edx, edx; Val
0x18001ebba  mov     r8d, 98h; Size
0x18001ebc0  lea     rcx, [rbp+1C0h+var_138]; void *
0x18001ebc7  call    memset_0
0x18001ebcc  mov     [rbp+1C0h+var_90], 1
0x18001ebd6  xor     eax, eax
0x18001ebd8  mov     [rbp+1C0h+var_88], rax
0x18001ebdf  lea     rax, [rbp+1C0h+var_188]
0x18001ebe3  mov     [rbp+1C0h+var_80], rax
0x18001ebea  mov     [rbp+1C0h+var_78], r12
0x18001ebf1  mov     [rbp+1C0h+var_70], r12
0x18001ebf8  lea     rax, [rbp+1C0h+var_190]
0x18001ebfc  mov     [rbp+1C0h+var_68], rax
0x18001ec03  mov     [rbp+1C0h+var_60], r12
0x18001ec0a  mov     [rbp+1C0h+var_58], r12d
0x18001ec11  lea     rax, [rbp+1C0h+var_160]
0x18001ec15  mov     [rbp+1C0h+var_50], rax
0x18001ec1c  mov     [rbp+1C0h+var_48], r12b
0x18001ec23  lea     rax, ??_7ComputeStorage_ProcessOsLayer@TraceProvider@Diagnostics@ComputeLib@@6B@; const ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer::`vftable'
0x18001ec2a  mov     [rbp+1C0h+var_190], rax
0x18001ec2e  lea     rdx, [rbp+1C0h+NumberOfBytesWritten]
0x18001ec32  lea     rcx, [rbp+1C0h+var_190]
0x18001ec36  call    ??$StartActivity@PEBG@ComputeStorage_ProcessOsLayer@TraceProvider@Diagnostics@ComputeLib@@QEAAX$$QEAPEBG@Z; ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer::StartActivity<ushort const *>(ushort const * &&)
0x18001ec3b  nop
0x18001ec3c  lea     rcx, [rsp+2C0h+var_280]
0x18001ec41  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ec46  mov     edx, [rdi]
0x18001ec48  cmp     edx, 1
0x18001ec4b  ja      loc_18001F008
0x18001ec51  cmp     [rdi+4], r12b
0x18001ec55  jnz     short loc_18001EC87
0x18001ec57  lea     r8, aFiles; "Files"
0x18001ec5e  mov     rdx, r14; pszPathIn
0x18001ec61  lea     rcx, [rbp+1C0h+Src]; Src
0x18001ec65  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18001ec6a  nop
0x18001ec6b  cmp     qword ptr [rax+18h], 7
0x18001ec70  jbe     short loc_18001EC75
0x18001ec72  mov     rax, [rax]
0x18001ec75  mov     rcx, rax; this
0x18001ec78  call    ?OptimizeCiCache@Helpers@OsImageUtilities@@YAXPEBG@Z; OsImageUtilities::Helpers::OptimizeCiCache(ushort const *)
0x18001ec7d  nop
0x18001ec7e  lea     rcx, [rbp+1C0h+Src]
0x18001ec82  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ec87  cmp     [rdi], r12d
0x18001ec8a  jz      short loc_18001EC9F
0x18001ec8c  cmp     dword ptr [rdi], 1
0x18001ec8f  jnz     loc_18001EFAD
0x18001ec95  cmp     [rdi+6], r12b
0x18001ec99  jz      loc_18001ED7D
0x18001ec9f  mov     rcx, r14; pszPathIn
0x18001eca2  call    ?CreateBaseHives@Helpers@OsImageUtilities@@YAXPEBG@Z; OsImageUtilities::Helpers::CreateBaseHives(ushort const *)
0x18001eca7  lea     r8, aLayout; "layout"
0x18001ecae  mov     rdx, r14; pszPathIn
0x18001ecb1  lea     rcx, [rbp+1C0h+Src]; Src
0x18001ecb5  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18001ecba  cmp     qword ptr [rax+18h], 7
0x18001ecbf  jbe     short loc_18001ECC4
0x18001ecc1  mov     rax, [rax]
0x18001ecc4  mov     [rsp+2C0h+hTemplateFile], r12; hTemplateFile
0x18001ecc9  mov     [rsp+2C0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18001ecce  mov     [rsp+2C0h+dwCreationDisposition], 1; dwCreationDisposition
0x18001ecd6  xor     r9d, r9d; lpSecurityAttributes
0x18001ecd9  xor     r8d, r8d; dwShareMode
0x18001ecdc  mov     edx, 40000000h; dwDesiredAccess
0x18001ece1  mov     rcx, rax; lpFileName
0x18001ece4  call    cs:__imp_CreateFileW
0x18001eceb  nop     dword ptr [rax+rax+00h]
0x18001ecf0  mov     rbx, rax
0x18001ecf3  mov     [rsp+2C0h+var_260], rax
0x18001ecf8  lea     rcx, [rbp+1C0h+Src]
0x18001ecfc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ed01  lea     rax, [rbx-1]
0x18001ed05  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ed09  setnbe  al
0x18001ed0c  mov     rcx, [rbp+1C8h]; this
0x18001ed13  test    al, al
0x18001ed15  jnz     loc_18001F03E
0x18001ed1b  mov     [rbp+1C0h+NumberOfBytesWritten], r12d
0x18001ed1f  lea     rdx, lpBuffer
0x18001ed26  cmp     cs:qword_18005FFB8, 0Fh
0x18001ed2e  cmova   rdx, cs:lpBuffer; lpBuffer
0x18001ed36  mov     qword ptr [rsp+2C0h+dwCreationDisposition], r12; int
0x18001ed3b  lea     r9, [rbp+1C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001ed3f  mov     r8d, cs:nNumberOfBytesToWrite; nNumberOfBytesToWrite
0x18001ed46  mov     rcx, rbx; hFile
0x18001ed49  call    cs:__imp_WriteFile
0x18001ed50  nop     dword ptr [rax+rax+00h]
0x18001ed55  mov     rcx, [rbp+1C8h]; this
0x18001ed5c  test    eax, eax
0x18001ed5e  jz      loc_18001F050
0x18001ed64  lea     rax, [rbx-1]
0x18001ed68  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ed6c  ja      short loc_18001ED7D
0x18001ed6e  mov     rcx, rbx; hObject
0x18001ed71  call    cs:__imp_CloseHandle
0x18001ed78  nop     dword ptr [rax+rax+00h]
0x18001ed7d  cmp     dword ptr [rdi], 1
0x18001ed80  jnz     loc_18001EFAD
0x18001ed86  lea     r8, aFiles; "Files"
0x18001ed8d  mov     rdx, r14; pszPathIn
0x18001ed90  lea     rcx, [rbp+1C0h+pszPathIn]; Src
0x18001ed94  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18001ed99  nop
0x18001ed9a  call    ?IsHostPreReleaseImageCapable@Helpers@OsImageUtilities@@YA_NXZ; OsImageUtilities::Helpers::IsHostPreReleaseImageCapable(void)
0x18001ed9f  test    al, al
0x18001eda1  jnz     short loc_18001EDB3
0x18001eda3  mov     rcx, r14; pszPathIn
0x18001eda6  call    ?IsPreReleaseImage@Helpers@OsImageUtilities@@YA_NPEBG@Z; OsImageUtilities::Helpers::IsPreReleaseImage(ushort const *)
0x18001edab  test    al, al
0x18001edad  jnz     loc_18001EFE2
0x18001edb3  mov     rcx, r14; pszPathIn
0x18001edb6  call    ?UseLegacyFilter@Helpers@OsImageUtilities@@YA_NPEBG@Z; OsImageUtilities::Helpers::UseLegacyFilter(ushort const *)
0x18001edbb  movzx   r15d, al
0x18001edbf  xor     r15d, 1
0x18001edc3  xorps   xmm0, xmm0
0x18001edc6  movups  [rsp+2C0h+var_258], xmm0
0x18001edcb  xorps   xmm1, xmm1
0x18001edce  movdqu  [rsp+2C0h+var_248], xmm1
0x18001edd4  mov     rax, r12
0x18001edd7  mov     [rbp+1C0h+var_238], rax
0x18001eddb  movups  [rbp+1C0h+var_230], xmm0
0x18001eddf  mov     qword ptr [rsp+2C0h+var_270], r12
0x18001ede4  movups  xmm2, cs:UTILITY_VM_LAYER_ID
0x18001edeb  movups  [rsp+2C0h+var_280], xmm2
0x18001edf0  cmp     [rdi+7], r12b
0x18001edf4  jnz     short loc_18001EE2B
0x18001edf6  cmp     [rdi+6], r12b
0x18001edfa  jz      short loc_18001EE16
0x18001edfc  mov     dword ptr [rsp+2C0h+var_270], 4
0x18001ee04  lea     rcx, off_18004ADF0; "Windows"
0x18001ee0b  mov     qword ptr [rsp+2C0h+var_258], 2
0x18001ee14  jmp     short loc_18001EE26
0x18001ee16  lea     rcx, off_18004AD40; "Windows"
0x18001ee1d  mov     qword ptr [rsp+2C0h+var_258], 0Bh
0x18001ee26  mov     qword ptr [rsp+2C0h+var_258+8], rcx
0x18001ee2b  mov     qword ptr [rsp+2C0h+var_270+8], r14
0x18001ee30  psrldq  xmm1, 8
0x18001ee35  movq    rdx, xmm1
0x18001ee3a  cmp     rdx, rax
0x18001ee3d  jz      short loc_18001EE52
0x18001ee3f  movups  xmmword ptr [rdx], xmm2
0x18001ee42  movups  xmm0, [rsp+2C0h+var_270]
0x18001ee47  movups  xmmword ptr [rdx+10h], xmm0
0x18001ee4b  add     qword ptr [rbp+1C0h+var_248+8], 20h ; ' '
0x18001ee50  jmp     short loc_18001EE61
0x18001ee52  lea     r8, [rsp+2C0h+var_280]
0x18001ee57  lea     rcx, [rsp+2C0h+var_248]
0x18001ee5c  call    ??$_Emplace_reallocate@U_WC_LAYER_DESCRIPTOR@@@?$vector@U_WC_LAYER_DESCRIPTOR@@V?$allocator@U_WC_LAYER_DESCRIPTOR@@@std@@@std@@AEAAPEAU_WC_LAYER_DESCRIPTOR@@QEAU2@$$QEAU2@@Z; std::vector<_WC_LAYER_DESCRIPTOR>::_Emplace_reallocate<_WC_LAYER_DESCRIPTOR>(_WC_LAYER_DESCRIPTOR * const,_WC_LAYER_DESCRIPTOR &&)
0x18001ee61  mov     r14, [rdi+10h]
0x18001ee65  mov     rbx, [rdi+8]
0x18001ee69  jmp     short loc_18001EEBF
0x18001ee6b  xorps   xmm0, xmm0
0x18001ee6e  movdqu  [rsp+2C0h+var_280+8], xmm0
0x18001ee74  movups  xmm1, xmmword ptr [rbx]
0x18001ee77  movups  [rsp+2C0h+var_280], xmm1
0x18001ee7c  lea     rax, [rbx+10h]
0x18001ee80  cmp     qword ptr [rbx+28h], 7
0x18001ee85  jbe     short loc_18001EE8A
0x18001ee87  mov     rax, [rax]
0x18001ee8a  mov     qword ptr [rsp+2C0h+var_270+8], rax
0x18001ee8f  mov     rdx, qword ptr [rbp+1C0h+var_248+8]
0x18001ee93  cmp     rdx, [rbp+1C0h+var_238]
0x18001ee97  jz      short loc_18001EEAC
0x18001ee99  movups  xmmword ptr [rdx], xmm1
0x18001ee9c  movups  xmm0, [rsp+2C0h+var_270]
0x18001eea1  movups  xmmword ptr [rdx+10h], xmm0
0x18001eea5  add     qword ptr [rbp+1C0h+var_248+8], 20h ; ' '
0x18001eeaa  jmp     short loc_18001EEBB
0x18001eeac  lea     r8, [rsp+2C0h+var_280]
0x18001eeb1  lea     rcx, [rsp+2C0h+var_248]
0x18001eeb6  call    ??$_Emplace_reallocate@U_WC_LAYER_DESCRIPTOR@@@?$vector@U_WC_LAYER_DESCRIPTOR@@V?$allocator@U_WC_LAYER_DESCRIPTOR@@@std@@@std@@AEAAPEAU_WC_LAYER_DESCRIPTOR@@QEAU2@$$QEAU2@@Z; std::vector<_WC_LAYER_DESCRIPTOR>::_Emplace_reallocate<_WC_LAYER_DESCRIPTOR>(_WC_LAYER_DESCRIPTOR * const,_WC_LAYER_DESCRIPTOR &&)
0x18001eebb  add     rbx, 38h ; '8'
0x18001eebf  cmp     rbx, r14
0x18001eec2  jnz     short loc_18001EE6B
0x18001eec4  movups  xmm0, xmmword ptr [rdi+20h]
0x18001eec8  movdqu  [rbp+1C0h+var_230], xmm0
0x18001eecd  xorps   xmm1, xmm1
0x18001eed0  xor     eax, eax
0x18001eed2  movups  [rbp+1C0h+var_1D0], xmm1
0x18001eed6  mov     [rbp+1C0h+var_1C0], rax
0x18001eeda  lea     edx, [rax+11h]; int
0x18001eedd  lea     rcx, [rbp+1C0h+var_1D0]; this
0x18001eee1  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x18001eee6  nop
0x18001eee7  xorps   xmm0, xmm0
0x18001eeea  xor     eax, eax
0x18001eeec  movups  [rbp+1C0h+Src], xmm0
0x18001eef0  mov     [rbp+1C0h+var_1E0], rax
0x18001eef4  lea     edx, [rax+12h]; int
0x18001eef7  lea     rcx, [rbp+1C0h+Src]; this
0x18001eefb  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x18001ef00  nop
0x18001ef01  cmp     qword ptr [rsi+18h], 7
0x18001ef06  jbe     short loc_18001EF0D
0x18001ef08  mov     rdx, [rsi]
0x18001ef0b  jmp     short loc_18001EF10
0x18001ef0d  mov     rdx, rsi; pszPathIn
0x18001ef10  lea     r8, asc_18004C49C; "\\"
0x18001ef17  lea     rcx, [rbp+1C0h+var_1B0]; Src
0x18001ef1b  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18001ef20  nop
0x18001ef21  lea     rdx, [rbp+1C0h+pszPathIn]
0x18001ef25  cmp     [rbp+1C0h+var_1F8], 7
0x18001ef2a  cmova   rdx, [rbp+1C0h+pszPathIn]
0x18001ef2f  lea     rcx, [rbp+1C0h+var_1B0]
0x18001ef33  cmp     [rbp+1C0h+var_198], 7
0x18001ef38  cmova   rcx, [rbp+1C0h+var_1B0]
0x18001ef3d  mov     r9d, r15d
0x18001ef40  lea     r8, [rsp+2C0h+var_258]
0x18001ef45  call    ?InitializeAndPopulateSandbox@Helpers@OsImageUtilities@@YAXPEBG0AEBUSandboxOptions@12@W4_WC_NESTING_MODE@@@Z; OsImageUtilities::Helpers::InitializeAndPopulateSandbox(ushort const *,ushort const *,OsImageUtilities::Helpers::SandboxOptions const &,_WC_NESTING_MODE)
0x18001ef4a  cmp     qword ptr [rsi+18h], 7
0x18001ef4f  jbe     short loc_18001EF56
0x18001ef51  mov     rcx, [rsi]
0x18001ef54  jmp     short loc_18001EF59
0x18001ef56  mov     rcx, rsi; pszPathIn
0x18001ef59  call    ?CreateSandboxStateDirectory@Helpers@OsImageUtilities@@YAXPEBG@Z; OsImageUtilities::Helpers::CreateSandboxStateDirectory(ushort const *)
0x18001ef5e  cmp     [rdi+5], r12b
0x18001ef62  jnz     short loc_18001EF7B
0x18001ef64  lea     rcx, [rbp+1C0h+pszPathIn]
0x18001ef68  cmp     [rbp+1C0h+var_1F8], 7
0x18001ef6d  cmova   rcx, [rbp+1C0h+pszPathIn]; pszPathIn
0x18001ef72  mov     rdx, rsi; unsigned __int16 *
0x18001ef75  call    ?UpdateBcdStore@Helpers@OsImageUtilities@@YAXPEBGAEBUPartitionInfo@@@Z; OsImageUtilities::Helpers::UpdateBcdStore(ushort const *,PartitionInfo const &)
0x18001ef7a  nop
0x18001ef7b  lea     rcx, [rbp+1C0h+var_1B0]
0x18001ef7f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ef84  nop
0x18001ef85  lea     rcx, [rbp+1C0h+Src]; this
0x18001ef89  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x18001ef8e  nop
0x18001ef8f  lea     rcx, [rbp+1C0h+var_1D0]; this
0x18001ef93  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
  ... truncated ...
```
