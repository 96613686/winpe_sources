# Marshal::FromXmlString<Schema::Containers::Definition::Container,>(std::basic_string_view<ushort,std::char_traits<ushort>>,ushort const *,bool,Schema::Containers::Definition::Container *,Marshal::UnmarshalFlags)

- ea: `0x1800130d8`
- end: `0x18001344f`
- name: `??$FromXmlString@UContainer@Definition@Containers@Schema@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@PEBG_NPEAUContainer@Definition@Containers@Schema@@W4UnmarshalFlags@0@@Z`
- size: `887`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180022580`

## callees

- `0x180002ad0`
- `0x1800051b0`
- `0x1800130d8`
- `0x180013784`
- `0x18001e7bc`
- `0x18001ff3c`
- `0x180020ccc`
- `0x1800215cc`
- `0x18002207c`
- `0x180034010`

## import_xrefs

- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x1800131ab`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x1800131ab`
- `XmlLite!CreateXmlReader` at `0x1800131df`
- `XmlLite!CreateXmlReader` at `0x1800131df`

## string_xrefs

- `0x1800133f8`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180013413`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180013428`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x18001343d`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
IXmlReaderInput *__fastcall Marshal::FromXmlString<Schema::Containers::Definition::Container,>(
        IXmlReaderInput *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  IXmlReaderInput *v6; // rbx
  unsigned __int64 v7; // rax
  IXmlReaderInput *v8; // rax
  HRESULT v9; // eax
  wil::details::in1diag3 *v10; // rcx
  HRESULT v11; // eax
  int v12; // eax
  int v13; // eax
  struct Marshal::XmlReader *v14; // rdx
  const struct Marshal::UnmarshalContext *v15; // r9
  bool v16; // r8
  struct IUnknownVtbl *v17; // rdx
  struct IUnknownVtbl *v18; // rcx
  struct IUnknownVtbl *v19; // rax
  IUnknown *v20; // rax
  IUnknown *v21; // rcx
  int pwszBaseUri; // [rsp+20h] [rbp-E0h]
  void *ppvObject; // [rsp+40h] [rbp-C0h] BYREF
  IUnknown *pInputStream; // [rsp+48h] [rbp-B8h] BYREF
  IXmlReaderInput *ppInput; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v27)(); // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  __int128 v29; // [rsp+68h] [rbp-98h] BYREF
  struct IUnknownVtbl *v30; // [rsp+78h] [rbp-88h]
  int v31; // [rsp+80h] [rbp-80h]
  void **v32; // [rsp+88h] [rbp-78h] BYREF
  __int128 *v33; // [rsp+90h] [rbp-70h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  unsigned __int16 v35[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 (__fastcall ***v36)(int, int, int, int, __int64); // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  IUnknown **p_pInputStream; // [rsp+C0h] [rbp-40h]
  char v39; // [rsp+C8h] [rbp-38h]
  void *v40; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v41[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v42; // [rsp+F8h] [rbp-8h]
  char v43; // [rsp+100h] [rbp+0h]
  int v44; // [rsp+101h] [rbp+1h]
  __int16 v45; // [rsp+105h] [rbp+5h]
  char v46; // [rsp+107h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v6 = a1;
  ppInput = a1;
  v28 = 0;
  v7 = *(_QWORD *)(a2 + 8);
  if ( v7 == -1 )
    goto LABEL_22;
  a1 = *(IXmlReaderInput **)a2;
  if ( !*(_QWORD *)a2 )
  {
    if ( !v7 )
      goto LABEL_6;
LABEL_22:
    gsl::details::terminate((gsl::details *)a1);
LABEL_23:
    wil::details::in1diag3::_Throw_Hr(
      v10,
      (void *)0x43E,
      (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v9,
      pwszBaseUri);
  }
  if ( v7 >= 0x7FFFFFFFFFFFFFFFLL )
    goto LABEL_22;
LABEL_6:
  v8 = (IXmlReaderInput *)(2 * v7);
  ppInput = v8;
  v27 = (__int64 (__fastcall ***)())a1;
  if ( !a1 && v8 )
    goto LABEL_22;
  wil::MakeOrThrow<Marshal::Details::ByteArrayReader,gsl::span<enum gsl::byte const,-1>>(&pInputStream, &ppInput);
  p_pInputStream = &pInputStream;
  v39 = 1;
  ppInput = 0;
  v9 = CreateXmlReaderInputWithEncodingName(pInputStream, 0, L"UTF-16", 1, &::pwszBaseUri, &ppInput);
  v10 = retaddr;
  if ( v9 < 0 )
    goto LABEL_23;
  v28 = 4;
  ppvObject = 0;
  v11 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x441,
      (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v11,
      pwszBaseUri);
  v12 = (*(__int64 (__fastcall **)(void *, IXmlReaderInput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppInput);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x442,
      (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v12,
      pwszBaseUri);
  v13 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 1, 1);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x444,
      (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v13,
      pwszBaseUri);
  if ( ppInput )
    ((void (__fastcall *)(IXmlReaderInput *))ppInput->lpVtbl->Release)(ppInput);
  v40 = ppvObject;
  v41[0] = 0;
  v41[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v41[0]) = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v29 = 0;
  v30 = 0;
  v31 = a6;
  *(_QWORD *)v35 = &Marshal::UnmarshalContext::`vftable';
  v36 = (__int64 (__fastcall ***)(int, int, int, int, __int64))&v29;
  v37 = 0;
  v16 = Marshal::Details::StartRead((Marshal::Details *)&v40, v14, v35, v15);
  if ( v16 )
  {
    v32 = &Marshal::UnmarshalContext::`vftable';
    v33 = &v29;
    v34 = 0;
    ppInput = (IXmlReaderInput *)&Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::Namespace>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
    v27 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,enum Schema::Containers::Definition::FilesystemIsolationMode,enum Schema::Containers::Definition::FilesystemNestingMode,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::FilesystemLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::BatchedBinding>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
    *(_QWORD *)v35 = &Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::Namespace>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value;
    v36 = Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistrySymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryRedirectionNode>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryHiveStack>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value;
    v16 = (unsigned __int8)Marshal::Details::ReadObjectXml(
                             (Marshal::Details *)&v40,
                             (__int64)&Schema::Containers::Definition::Container_ClassData,
                             (__int64)v35,
                             (__int64)&ppInput) != 0;
  }
  v17 = v30;
  v30 = 0;
  v18 = (struct IUnknownVtbl *)*((_QWORD *)&v29 + 1);
  v19 = (struct IUnknownVtbl *)v29;
  v29 = 0u;
  LOBYTE(v6->lpVtbl) = v16;
  v34 = 0;
  v33 = 0;
  v32 = 0;
  v6[1].lpVtbl = v19;
  v6[2].lpVtbl = v18;
  v6[3].lpVtbl = v17;
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::~vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>(&v32);
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::~vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>(&v29);
  std::wstring::~wstring(v41);
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  v20 = pInputStream;
  pInputStream[2].lpVtbl = 0;
  v20[3].lpVtbl = 0;
  v21 = pInputStream;
  if ( pInputStream )
  {
    pInputStream = 0;
    ((void (__fastcall *)(IUnknown *))v21->lpVtbl->Release)(v21);
  }
  return v6;
}

```

## disassembly

```asm
0x1800130d8  push    rbp
0x1800130da  push    rbx
0x1800130db  push    rsi
0x1800130dc  push    rdi
0x1800130dd  push    r14
0x1800130df  push    r15
0x1800130e1  lea     rbp, [rsp-18h]
0x1800130e6  sub     rsp, 118h
0x1800130ed  mov     rax, cs:__security_cookie
0x1800130f4  xor     rax, rsp
0x1800130f7  mov     [rbp+40h+var_38], rax
0x1800130fb  mov     rbx, rcx
0x1800130fe  mov     [rsp+140h+var_F0], rcx
0x180013103  mov     rdi, [rbp+40h+arg_20]
0x180013107  xor     esi, esi
0x180013109  mov     [rsp+140h+var_E0], esi
0x18001310d  mov     rax, [rdx+8]
0x180013111  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013115  jz      loc_18001340A
0x18001311b  mov     rcx, [rdx]
0x18001311e  test    rcx, rcx
0x180013121  jnz     short loc_18001312E
0x180013123  test    rax, rax
0x180013126  jnz     loc_18001340A
0x18001312c  jmp     short loc_180013141
0x18001312e  mov     rdx, 7FFFFFFFFFFFFFFFh
0x180013138  cmp     rax, rdx
0x18001313b  jnb     loc_18001340A
0x180013141  add     rax, rax
0x180013144  mov     [rsp+140h+var_F0], rax
0x180013149  mov     [rsp+140h+var_E8], rcx
0x18001314e  test    rcx, rcx
0x180013151  jnz     short loc_18001315C
0x180013153  test    rax, rax
0x180013156  jnz     loc_18001340A
0x18001315c  lea     rdx, [rsp+140h+var_F0]
0x180013161  lea     rcx, [rsp+140h+pInputStream]
0x180013166  call    ??$MakeOrThrow@VByteArrayReader@Details@Marshal@@V?$span@$$CBW4byte@gsl@@$0?0@gsl@@@wil@@YA?AV?$ComPtr@VByteArrayReader@Details@Marshal@@@WRL@Microsoft@@$$QEAV?$span@$$CBW4byte@gsl@@$0?0@gsl@@@Z; wil::MakeOrThrow<Marshal::Details::ByteArrayReader,gsl::span<gsl::byte const,-1>>(gsl::span<gsl::byte const,-1> &&)
0x18001316b  nop
0x18001316c  lea     rax, [rsp+140h+pInputStream]
0x180013171  mov     [rbp+40h+var_80], rax
0x180013175  mov     r14d, 1
0x18001317b  mov     [rbp+40h+var_78], r14b
0x18001317f  mov     [rsp+140h+var_F0], rsi
0x180013184  lea     rax, [rsp+140h+var_F0]
0x180013189  mov     [rsp+140h+ppInput], rax; ppInput
0x18001318e  lea     rax, pwszBaseUri
0x180013195  mov     [rsp+140h+pwszBaseUri], rax; int
0x18001319a  mov     r9d, r14d; fEncodingHint
0x18001319d  lea     r8, pwszEncodingName; "UTF-16"
0x1800131a4  xor     edx, edx; pMalloc
0x1800131a6  mov     rcx, [rsp+140h+pInputStream]; pInputStream
0x1800131ab  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x1800131b2  nop     dword ptr [rax+rax+00h]
0x1800131b7  mov     rcx, [rbp+48h]
0x1800131bb  test    eax, eax
0x1800131bd  js      loc_180013410
0x1800131c3  mov     [rsp+140h+var_E0], 4
0x1800131cb  mov     [rsp+140h+ppvObject], rsi
0x1800131d0  xor     r8d, r8d; pMalloc
0x1800131d3  lea     rdx, [rsp+140h+ppvObject]; ppvObject
0x1800131d8  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800131df  call    cs:__imp_CreateXmlReader
0x1800131e6  nop     dword ptr [rax+rax+00h]
0x1800131eb  mov     rcx, [rbp+48h]; this
0x1800131ef  test    eax, eax
0x1800131f1  js      loc_180013425
0x1800131f7  mov     rcx, [rsp+140h+ppvObject]
0x1800131fc  mov     rax, [rcx]
0x1800131ff  mov     rdx, [rsp+140h+var_F0]
0x180013204  mov     rax, [rax+18h]
0x180013208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001320d  mov     rcx, [rbp+48h]; this
0x180013211  test    eax, eax
0x180013213  js      loc_18001343A
0x180013219  mov     rcx, [rsp+140h+ppvObject]
0x18001321e  mov     rax, [rcx]
0x180013221  mov     r8d, r14d
0x180013224  mov     edx, r14d
0x180013227  mov     rax, [rax+28h]
0x18001322b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013230  mov     rcx, [rbp+48h]; this
0x180013234  test    eax, eax
0x180013236  js      loc_1800133F5
0x18001323c  mov     rcx, [rsp+140h+var_F0]
0x180013241  test    rcx, rcx
0x180013244  jz      short loc_180013253
0x180013246  mov     rax, [rcx]
0x180013249  mov     rax, [rax+10h]
0x18001324d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013252  nop
0x180013253  mov     rax, [rsp+140h+ppvObject]
0x180013258  mov     [rbp+40h+var_70], rax
0x18001325c  xorps   xmm0, xmm0
0x18001325f  movups  [rbp+40h+var_68], xmm0
0x180013263  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001326b  movdqu  [rbp+40h+var_58], xmm1
0x180013270  mov     word ptr [rbp+40h+var_68], si
0x180013274  mov     [rbp+40h+var_48], rsi
0x180013278  mov     [rbp+40h+var_40], sil
0x18001327c  xor     eax, eax
0x18001327e  mov     [rbp+40h+var_3F], eax
0x180013281  mov     [rbp+40h+var_3B], ax
0x180013285  mov     [rbp+40h+var_39], al
0x180013288  movdqu  [rsp+140h+var_D8], xmm0
0x18001328e  mov     [rsp+140h+var_C8], rsi
0x180013293  mov     eax, [rbp+40h+arg_28]
0x180013296  mov     [rbp+40h+var_C0], eax
0x180013299  lea     r15, ??_7UnmarshalContext@Marshal@@6B@; const Marshal::UnmarshalContext::`vftable'
0x1800132a0  mov     qword ptr [rbp+40h+var_A0], r15
0x1800132a4  lea     rax, [rsp+140h+var_D8]
0x1800132a9  mov     [rbp+40h+var_98], rax
0x1800132ad  mov     [rbp+40h+var_90], rsi
0x1800132b1  lea     r8, [rbp+40h+var_A0]; unsigned __int16 *
0x1800132b5  lea     rcx, [rbp+40h+var_70]; this
0x1800132b9  call    ?StartRead@Details@Marshal@@YA_NAEAUXmlReader@2@PEBGAEBVUnmarshalContext@2@@Z; Marshal::Details::StartRead(Marshal::XmlReader &,ushort const *,Marshal::UnmarshalContext const &)
0x1800132be  mov     r8b, al
0x1800132c1  test    al, al
0x1800132c3  jz      short loc_18001333D
0x1800132c5  mov     [rbp+40h+var_B8], r15
0x1800132c9  lea     rax, [rsp+140h+var_D8]
0x1800132ce  mov     [rbp+40h+var_B0], rax
0x1800132d2  mov     [rbp+40h+var_A8], rsi
0x1800132d6  lea     rax, ?Value@?$ObjectTypeInfo@U?$TypeList@UNamespace@Definition@Containers@Schema@@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::XmlTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::Namespace>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x1800132dd  mov     [rsp+140h+var_F0], rax
0x1800132e2  lea     rax, ?Value@?$ObjectTypeInfo@U?$TypeList@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FilesystemIsolationMode@Definition@Containers@Schema@@W4FilesystemNestingMode@456@U?$ModifiedType@V?$vector@UFilesystemLayer@Definition@Containers@Schema@@V?$allocator@UFilesystemLayer@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@UBatchedBinding@Definition@Containers@Schema@@V?$allocator@UBatchedBinding@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@9@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$04@std@@A; std::array<Marshal::Details::BaseTypeData const *,5> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<std::wstring,Schema::Containers::Definition::FilesystemIsolationMode,Schema::Containers::Definition::FilesystemNestingMode,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::FilesystemLayer>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::BatchedBinding>,Marshal::ModifierList<>>>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x1800132e9  mov     [rsp+140h+var_E8], rax
0x1800132ee  lea     rax, ?Value@?$ObjectTypeInfo@U?$TypeList@UNamespace@Definition@Containers@Schema@@@Marshal@@UBaseTypeData@Details@2@UBaseTypeInfo@42@@Details@Marshal@@2V?$array@PEBUBaseTypeData@Details@Marshal@@$00@std@@A; std::array<Marshal::Details::BaseTypeData const *,1> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Schema::Containers::Definition::Namespace>,Marshal::Details::BaseTypeData,Marshal::Details::BaseTypeInfo>::Value
0x1800132f5  mov     qword ptr [rbp+40h+var_A0], rax
0x1800132f9  lea     rax, ?Value@?$ObjectTypeInfo@U?$TypeList@U?$ModifiedType@V?$vector@URegistrySymlink@Definition@Containers@Schema@@V?$allocator@URegistrySymlink@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@Marshal@@U?$ModifiedType@V?$vector@URegistryRedirectionNode@Definition@Containers@Schema@@V?$allocator@URegistryRedirectionNode@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@2@U?$ModifiedType@V?$vector@URegistryHiveStack@Definition@Containers@Schema@@V?$allocator@URegistryHiveStack@Definition@Containers@Schema@@@std@@@std@@U?$ModifierList@$$V@Marshal@@@2@@Marshal@@UXmlTypeData@Details@2@UXmlTypeInfo@42@@Details@Marshal@@2V?$array@PEBUXmlTypeData@Details@Marshal@@$02@std@@A; std::array<Marshal::Details::XmlTypeData const *,3> Marshal::Details::ObjectTypeInfo<Marshal::TypeList<Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistrySymlink>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryRedirectionNode>,Marshal::ModifierList<>>,Marshal::ModifiedType<std::vector<Schema::Containers::Definition::RegistryHiveStack>,Marshal::ModifierList<>>>,Marshal::Details::XmlTypeData,Marshal::Details::XmlTypeInfo>::Value
0x180013300  mov     [rbp+40h+var_98], rax
0x180013304  lea     rax, [rsp+140h+var_F0]
0x180013309  mov     [rsp+140h+var_110], rax; __int64
0x18001330e  lea     rax, [rbp+40h+var_A0]
0x180013312  mov     [rsp+140h+ppInput], rax; __int64
0x180013317  lea     rax, ?Container_ClassData@Definition@Containers@Schema@@3UClassData@Marshal@@B; Marshal::ClassData const Schema::Containers::Definition::Container_ClassData
0x18001331e  mov     [rsp+140h+pwszBaseUri], rax; __int64
0x180013323  lea     r9, [rbp+40h+var_B8]
0x180013327  mov     r8, rdi
0x18001332a  lea     rcx, [rbp+40h+var_70]; this
0x18001332e  call    ?ReadObjectXml@Details@Marshal@@YA_NAEAUXmlReader@2@HPEAXAEBVUnmarshalContext@2@AEBUClassData@2@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::ReadObjectXml(Marshal::XmlReader &,int,void *,Marshal::UnmarshalContext const &,Marshal::ClassData const &,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x180013333  movzx   r8d, al
0x180013337  test    al, al
0x180013339  cmovnz  r8d, r14d
0x18001333d  mov     rdx, [rsp+140h+var_C8]
0x180013342  mov     [rsp+140h+var_C8], rsi
0x180013347  mov     rcx, qword ptr [rsp+140h+var_D8+8]
0x18001334c  mov     qword ptr [rsp+140h+var_D8+8], rsi
0x180013351  mov     rax, qword ptr [rsp+140h+var_D8]
0x180013356  mov     qword ptr [rsp+140h+var_D8], rsi
0x18001335b  mov     [rbx], r8b
0x18001335e  mov     [rbp+40h+var_A8], rsi
0x180013362  mov     [rbp+40h+var_B0], rsi
0x180013366  mov     [rbp+40h+var_B8], rsi
0x18001336a  mov     [rbx+8], rax
0x18001336e  mov     [rbx+10h], rcx
0x180013372  mov     [rbx+18h], rdx
0x180013376  lea     rcx, [rbp+40h+var_B8]
0x18001337a  call    ??1?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::~vector<std::pair<std::wstring,Marshal::UnmarshalError>>(void)
0x18001337f  nop
0x180013380  lea     rcx, [rsp+140h+var_D8]
0x180013385  call    ??1?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::~vector<std::pair<std::wstring,Marshal::UnmarshalError>>(void)
0x18001338a  nop
0x18001338b  lea     rcx, [rbp+40h+var_68]
0x18001338f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013394  nop
0x180013395  mov     rcx, [rsp+140h+ppvObject]
0x18001339a  test    rcx, rcx
0x18001339d  jz      short loc_1800133AC
0x18001339f  mov     rax, [rcx]
0x1800133a2  mov     rax, [rax+10h]
0x1800133a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133ab  nop
0x1800133ac  mov     rax, [rsp+140h+pInputStream]
0x1800133b1  mov     [rax+10h], rsi
0x1800133b5  mov     [rax+18h], rsi
0x1800133b9  mov     rcx, [rsp+140h+pInputStream]
0x1800133be  test    rcx, rcx
0x1800133c1  jz      short loc_1800133D5
0x1800133c3  mov     [rsp+140h+pInputStream], rsi
0x1800133c8  mov     rdx, [rcx]
0x1800133cb  mov     rax, [rdx+10h]
0x1800133cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133d4  nop
0x1800133d5  mov     rax, rbx
0x1800133d8  mov     rcx, [rbp+40h+var_38]
0x1800133dc  xor     rcx, rsp; StackCookie
0x1800133df  call    __security_check_cookie
0x1800133e4  add     rsp, 118h
0x1800133eb  pop     r15
0x1800133ed  pop     r14
0x1800133ef  pop     rdi
0x1800133f0  pop     rsi
0x1800133f1  pop     rbx
0x1800133f2  pop     rbp
0x1800133f3  retn
0x1800133f5  mov     r9d, eax; char *
0x1800133f8  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x1800133ff  mov     edx, 444h; void *
0x180013404  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001340a  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x18001340f  nop
0x180013410  mov     r9d, eax; char *
0x180013413  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18001341a  mov     edx, 43Eh; void *
0x18001341f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180013425  mov     r9d, eax; char *
0x180013428  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18001342f  mov     edx, 441h; void *
0x180013434  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001343a  mov     r9d, eax; char *
0x18001343d  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180013444  mov     edx, 442h; void *
0x180013449  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
