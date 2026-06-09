# IdToken::ParseIdTokenPayload(void)

- ea: `0x14000ea0c`
- end: `0x14000f025`
- name: `?ParseIdTokenPayload@IdToken@@AEAAXXZ`
- size: `1561`
- prototype: `void __fastcall(IdToken *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x14000e328`

## callees

- `0x1400017d4`
- `0x140001b60`
- `0x1400028ac`
- `0x140003044`
- `0x1400032ec`
- `0x140005c80`
- `0x1400061dc`
- `0x140007bf8`
- `0x14000baf8`
- `0x14000df44`
- `0x14000e684`
- `0x14000ea0c`
- `0x1400234fc`
- `0x1400239a4`
- `0x14002c3e8`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall IdToken::ParseIdTokenPayload(IdToken *this)
{
  _QWORD *v2; // rax
  JsonObject *v3; // rbx
  _DWORD *v4; // rax
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rbx
  _QWORD *JsonDataAsString; // rax
  _QWORD *v8; // rdx
  volatile signed __int32 *v9; // rdx
  _QWORD *v10; // rax
  _QWORD *v11; // rdx
  volatile signed __int32 *v12; // rdx
  _QWORD *v13; // rax
  _QWORD *v14; // rdx
  volatile signed __int32 *v15; // rdx
  _QWORD *v16; // rax
  _QWORD *v17; // rdx
  volatile signed __int32 *v18; // rdx
  _QWORD *v19; // rax
  _QWORD *v20; // rdx
  volatile signed __int32 *v21; // rdx
  _QWORD *v22; // rax
  _QWORD *v23; // rdx
  volatile signed __int32 *v24; // rdx
  _QWORD *v25; // rax
  _QWORD *v26; // rdx
  volatile signed __int32 *v27; // rdx
  void *v28; // rcx
  volatile signed __int32 *v29; // [rsp+20h] [rbp-39h] BYREF
  __int128 pExceptionObject; // [rsp+28h] [rbp-31h] BYREF
  void *Block[7]; // [rsp+38h] [rbp-21h] BYREF
  char *v32[4]; // [rsp+70h] [rbp+17h] BYREF

  JsonReader::JsonReader((JsonReader *)Block);
  v2 = std::wstring::wstring(v32, *(_WORD **)this);
  v3 = JsonReader::Parse(Block, v2);
  v4 = operator new(0x18u);
  *(_QWORD *)&pExceptionObject = v4;
  if ( v4 )
  {
    *(_OWORD *)v4 = 0;
    v4[2] = 1;
    v4[3] = 1;
    *(_QWORD *)v4 = &std::_Ref_count<JsonValue>::`vftable';
    *((_QWORD *)v4 + 2) = v3;
  }
  *((_QWORD *)this + 1) = v3;
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = v4;
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  std::wstring::~wstring(v32);
  v6 = *((_QWORD *)this + 1);
  if ( !v6 || *(_DWORD *)(v6 + 8) != 1 )
  {
    pExceptionObject = 0;
    IdToken::IdTokenParseException::IdTokenParseException((IdToken::IdTokenParseException *)&pExceptionObject);
    throw (IdToken::IdTokenParseException *)&pExceptionObject;
  }
  v29 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v29,
          (__int64)L"sub") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v29, L"sub", 3);
  JsonDataAsString = Utils::GetJsonDataAsString(&pExceptionObject, v6, (_WORD **)&v29);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)this + 3,
    JsonDataAsString);
  v8 = (_QWORD *)(pExceptionObject - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(pExceptionObject - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
  v9 = v29 - 6;
  if ( _InterlockedDecrement(v29 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v9 + 8LL))(*(_QWORD *)v9);
  v29 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v29,
          (__int64)L"tid") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v29, L"tid", 3);
  v10 = Utils::GetJsonDataAsString(&pExceptionObject, v6, (_WORD **)&v29);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)this + 4,
    v10);
  v11 = (_QWORD *)(pExceptionObject - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(pExceptionObject - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
  v12 = v29 - 6;
  if ( _InterlockedDecrement(v29 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v12 + 8LL))(*(_QWORD *)v12);
  v29 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v29,
          (__int64)L"upn") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v29, L"upn", 3);
  v13 = Utils::GetJsonDataAsString(&pExceptionObject, v6, (_WORD **)&v29);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)this + 5,
    v13);
  v14 = (_QWORD *)(pExceptionObject - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(pExceptionObject - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 8LL))(*v14);
  v15 = v29 - 6;
  if ( _InterlockedDecrement(v29 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 8LL))(*(_QWORD *)v15);
  v29 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v29,
          (__int64)L"unique_name") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v29, L"unique_name", 11);
  v16 = Utils::GetJsonDataAsString(&pExceptionObject, v6, (_WORD **)&v29);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)this + 6,
    v16);
  v17 = (_QWORD *)(pExceptionObject - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(pExceptionObject - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v17 + 8LL))(*v17);
  v18 = v29 - 6;
  if ( _InterlockedDecrement(v29 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 8LL))(*(_QWORD *)v18);
  v29 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v29,
          (__int64)L"given_name") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v29, L"given_name", 10);
  v19 = Utils::GetJsonDataAsString(&pExceptionObject, v6, (_WORD **)&v29);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)this + 7,
    v19);
  v20 = (_QWORD *)(pExceptionObject - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(pExceptionObject - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 8LL))(*v20);
  v21 = v29 - 6;
  if ( _InterlockedDecrement(v29 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v21 + 8LL))(*(_QWORD *)v21);
  v29 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v29,
          (__int64)L"family_name") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v29, L"family_name", 11);
  v22 = Utils::GetJsonDataAsString(&pExceptionObject, v6, (_WORD **)&v29);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)this + 8,
    v22);
  v23 = (_QWORD *)(pExceptionObject - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(pExceptionObject - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 8LL))(*v23);
  v24 = v29 - 6;
  if ( _InterlockedDecrement(v29 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v24 + 8LL))(*(_QWORD *)v24);
  v29 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (void *const *)&v29,
          (__int64)L"email") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v29, L"email", 5);
  v25 = Utils::GetJsonDataAsString(&pExceptionObject, v6, (_WORD **)&v29);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)this + 9,
    v25);
  v26 = (_QWORD *)(pExceptionObject - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(pExceptionObject - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 8LL))(*v26);
  v27 = v29 - 6;
  if ( _InterlockedDecrement(v29 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 8LL))(*(_QWORD *)v27);
  std::deque<JsonValue *>::_Tidy(Block);
  v28 = Block[0];
  Block[0] = 0;
  operator delete(v28);
}

```

## disassembly

```asm
0x14000ea0c  mov     [rsp-8+arg_8], rbx
0x14000ea11  mov     [rsp-8+arg_10], rsi
0x14000ea16  push    rbp
0x14000ea17  push    rdi
0x14000ea18  push    r15
0x14000ea1a  lea     rbp, [rsp-47h]
0x14000ea1f  sub     rsp, 0A0h
0x14000ea26  mov     rax, cs:__security_cookie
0x14000ea2d  xor     rax, rsp
0x14000ea30  mov     [rbp+57h+var_20], rax
0x14000ea34  mov     rdi, rcx
0x14000ea37  lea     rcx, [rbp+57h+Block]; this
0x14000ea3b  call    ??0JsonReader@@QEAA@XZ; JsonReader::JsonReader(void)
0x14000ea40  nop
0x14000ea41  mov     rdx, [rdi]
0x14000ea44  lea     rcx, [rbp+57h+var_40]
0x14000ea48  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14000ea4d  nop
0x14000ea4e  mov     rdx, rax
0x14000ea51  lea     rcx, [rbp+57h+Block]; this
0x14000ea55  call    ?Parse@JsonReader@@QEAAPEAVJsonValue@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; JsonReader::Parse(std::wstring const &)
0x14000ea5a  mov     rbx, rax
0x14000ea5d  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x14000ea61  mov     ecx, 18h; Size
0x14000ea66  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ea6b  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x14000ea6f  test    rax, rax
0x14000ea72  jz      short loc_14000EA96
0x14000ea74  xorps   xmm0, xmm0
0x14000ea77  movups  xmmword ptr [rax], xmm0
0x14000ea7a  mov     dword ptr [rax+8], 1
0x14000ea81  mov     dword ptr [rax+0Ch], 1
0x14000ea88  lea     rcx, ??_7?$_Ref_count@VJsonValue@@@std@@6B@; const std::_Ref_count<JsonValue>::`vftable'
0x14000ea8f  mov     [rax], rcx
0x14000ea92  mov     [rax+10h], rbx
0x14000ea96  mov     [rdi+8], rbx
0x14000ea9a  mov     rbx, [rdi+10h]
0x14000ea9e  mov     [rdi+10h], rax
0x14000eaa2  or      esi, 0FFFFFFFFh
0x14000eaa5  test    rbx, rbx
0x14000eaa8  jz      short loc_14000EADE
0x14000eaaa  mov     eax, esi
0x14000eaac  lock xadd [rbx+8], eax
0x14000eab1  add     eax, esi
0x14000eab3  jnz     short loc_14000EADE
0x14000eab5  mov     rax, [rbx]
0x14000eab8  mov     rcx, rbx
0x14000eabb  mov     rax, [rax]
0x14000eabe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eac3  mov     eax, esi
0x14000eac5  lock xadd [rbx+0Ch], eax
0x14000eaca  add     eax, esi
0x14000eacc  jnz     short loc_14000EADE
0x14000eace  mov     rax, [rbx]
0x14000ead1  mov     rcx, rbx
0x14000ead4  mov     rax, [rax+8]
0x14000ead8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eadd  nop
0x14000eade  lea     rcx, [rbp+57h+var_40]
0x14000eae2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000eae7  mov     rbx, [rdi+8]
0x14000eaeb  test    rbx, rbx
0x14000eaee  jz      loc_14000F004
0x14000eaf4  cmp     dword ptr [rbx+8], 1
0x14000eaf8  jnz     loc_14000F004
0x14000eafe  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000eb05  lea     r15, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000eb0c  mov     rcx, r15
0x14000eb0f  mov     rax, [rax+18h]
0x14000eb13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb18  add     rax, 18h
0x14000eb1c  mov     [rbp+57h+var_90], rax
0x14000eb20  lea     rdx, aSub; "sub"
0x14000eb27  lea     rcx, [rbp+57h+var_90]
0x14000eb2b  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14000eb30  test    al, al
0x14000eb32  jnz     short loc_14000EB4B
0x14000eb34  mov     r8d, 3
0x14000eb3a  lea     rdx, aSub; "sub"
0x14000eb41  lea     rcx, [rbp+57h+var_90]
0x14000eb45  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000eb4a  nop
0x14000eb4b  lea     r8, [rbp+57h+var_90]
0x14000eb4f  mov     rdx, rbx
0x14000eb52  lea     rcx, [rbp+57h+pExceptionObject]
0x14000eb56  call    ?GetJsonDataAsString@Utils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVJsonObject@@AEBV23@@Z; Utils::GetJsonDataAsString(JsonObject const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000eb5b  nop
0x14000eb5c  lea     rcx, [rdi+18h]
0x14000eb60  mov     rdx, rax
0x14000eb63  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000eb68  nop
0x14000eb69  mov     rdx, qword ptr [rbp+57h+pExceptionObject]
0x14000eb6d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000eb71  mov     eax, esi
0x14000eb73  lock xadd [rdx+10h], eax
0x14000eb78  add     eax, esi
0x14000eb7a  test    eax, eax
0x14000eb7c  jg      short loc_14000EB8E
0x14000eb7e  mov     rcx, [rdx]
0x14000eb81  mov     rax, [rcx]
0x14000eb84  mov     rax, [rax+8]
0x14000eb88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb8d  nop
0x14000eb8e  mov     rdx, [rbp+57h+var_90]
0x14000eb92  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000eb96  mov     eax, esi
0x14000eb98  lock xadd [rdx+10h], eax
0x14000eb9d  add     eax, esi
0x14000eb9f  test    eax, eax
0x14000eba1  jg      short loc_14000EBB2
0x14000eba3  mov     rcx, [rdx]
0x14000eba6  mov     rax, [rcx]
0x14000eba9  mov     rax, [rax+8]
0x14000ebad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ebb2  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000ebb9  mov     rcx, r15
0x14000ebbc  mov     rax, [rax+18h]
0x14000ebc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ebc5  add     rax, 18h
0x14000ebc9  mov     [rbp+57h+var_90], rax
0x14000ebcd  lea     rdx, aTid; "tid"
0x14000ebd4  lea     rcx, [rbp+57h+var_90]
0x14000ebd8  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14000ebdd  test    al, al
0x14000ebdf  jnz     short loc_14000EBF8
0x14000ebe1  mov     r8d, 3
0x14000ebe7  lea     rdx, aTid; "tid"
0x14000ebee  lea     rcx, [rbp+57h+var_90]
0x14000ebf2  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000ebf7  nop
0x14000ebf8  lea     r8, [rbp+57h+var_90]
0x14000ebfc  mov     rdx, rbx
0x14000ebff  lea     rcx, [rbp+57h+pExceptionObject]
0x14000ec03  call    ?GetJsonDataAsString@Utils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVJsonObject@@AEBV23@@Z; Utils::GetJsonDataAsString(JsonObject const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000ec08  nop
0x14000ec09  lea     rcx, [rdi+20h]
0x14000ec0d  mov     rdx, rax
0x14000ec10  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000ec15  nop
0x14000ec16  mov     rdx, qword ptr [rbp+57h+pExceptionObject]
0x14000ec1a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000ec1e  mov     eax, esi
0x14000ec20  lock xadd [rdx+10h], eax
0x14000ec25  add     eax, esi
0x14000ec27  test    eax, eax
0x14000ec29  jg      short loc_14000EC3B
0x14000ec2b  mov     rcx, [rdx]
0x14000ec2e  mov     rax, [rcx]
0x14000ec31  mov     rax, [rax+8]
0x14000ec35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec3a  nop
0x14000ec3b  mov     rdx, [rbp+57h+var_90]
0x14000ec3f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000ec43  mov     eax, esi
0x14000ec45  lock xadd [rdx+10h], eax
0x14000ec4a  add     eax, esi
0x14000ec4c  test    eax, eax
0x14000ec4e  jg      short loc_14000EC5F
0x14000ec50  mov     rcx, [rdx]
0x14000ec53  mov     rax, [rcx]
0x14000ec56  mov     rax, [rax+8]
0x14000ec5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec5f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000ec66  mov     rcx, r15
0x14000ec69  mov     rax, [rax+18h]
0x14000ec6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec72  add     rax, 18h
0x14000ec76  mov     [rbp+57h+var_90], rax
0x14000ec7a  lea     rdx, aUpn; "upn"
0x14000ec81  lea     rcx, [rbp+57h+var_90]
0x14000ec85  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14000ec8a  test    al, al
0x14000ec8c  jnz     short loc_14000ECA5
0x14000ec8e  mov     r8d, 3
0x14000ec94  lea     rdx, aUpn; "upn"
0x14000ec9b  lea     rcx, [rbp+57h+var_90]
0x14000ec9f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000eca4  nop
0x14000eca5  lea     r8, [rbp+57h+var_90]
0x14000eca9  mov     rdx, rbx
0x14000ecac  lea     rcx, [rbp+57h+pExceptionObject]
0x14000ecb0  call    ?GetJsonDataAsString@Utils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVJsonObject@@AEBV23@@Z; Utils::GetJsonDataAsString(JsonObject const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000ecb5  nop
0x14000ecb6  lea     rcx, [rdi+28h]
0x14000ecba  mov     rdx, rax
0x14000ecbd  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000ecc2  nop
0x14000ecc3  mov     rdx, qword ptr [rbp+57h+pExceptionObject]
0x14000ecc7  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000eccb  mov     eax, esi
0x14000eccd  lock xadd [rdx+10h], eax
0x14000ecd2  add     eax, esi
0x14000ecd4  test    eax, eax
0x14000ecd6  jg      short loc_14000ECE8
0x14000ecd8  mov     rcx, [rdx]
0x14000ecdb  mov     rax, [rcx]
0x14000ecde  mov     rax, [rax+8]
0x14000ece2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ece7  nop
0x14000ece8  mov     rdx, [rbp+57h+var_90]
0x14000ecec  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000ecf0  mov     eax, esi
0x14000ecf2  lock xadd [rdx+10h], eax
0x14000ecf7  add     eax, esi
0x14000ecf9  test    eax, eax
0x14000ecfb  jg      short loc_14000ED0C
0x14000ecfd  mov     rcx, [rdx]
0x14000ed00  mov     rax, [rcx]
0x14000ed03  mov     rax, [rax+8]
0x14000ed07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ed0c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000ed13  mov     rcx, r15
0x14000ed16  mov     rax, [rax+18h]
0x14000ed1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ed1f  add     rax, 18h
0x14000ed23  mov     [rbp+57h+var_90], rax
0x14000ed27  lea     rdx, aUniqueName; "unique_name"
0x14000ed2e  lea     rcx, [rbp+57h+var_90]
0x14000ed32  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14000ed37  test    al, al
0x14000ed39  jnz     short loc_14000ED52
0x14000ed3b  mov     r8d, 0Bh
0x14000ed41  lea     rdx, aUniqueName; "unique_name"
0x14000ed48  lea     rcx, [rbp+57h+var_90]
0x14000ed4c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000ed51  nop
0x14000ed52  lea     r8, [rbp+57h+var_90]
0x14000ed56  mov     rdx, rbx
0x14000ed59  lea     rcx, [rbp+57h+pExceptionObject]
0x14000ed5d  call    ?GetJsonDataAsString@Utils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVJsonObject@@AEBV23@@Z; Utils::GetJsonDataAsString(JsonObject const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000ed62  nop
0x14000ed63  lea     rcx, [rdi+30h]
0x14000ed67  mov     rdx, rax
0x14000ed6a  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000ed6f  nop
0x14000ed70  mov     rdx, qword ptr [rbp+57h+pExceptionObject]
0x14000ed74  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000ed78  mov     eax, esi
0x14000ed7a  lock xadd [rdx+10h], eax
0x14000ed7f  add     eax, esi
0x14000ed81  test    eax, eax
0x14000ed83  jg      short loc_14000ED95
0x14000ed85  mov     rcx, [rdx]
0x14000ed88  mov     rax, [rcx]
0x14000ed8b  mov     rax, [rax+8]
0x14000ed8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ed94  nop
0x14000ed95  mov     rdx, [rbp+57h+var_90]
0x14000ed99  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000ed9d  mov     eax, esi
0x14000ed9f  lock xadd [rdx+10h], eax
0x14000eda4  add     eax, esi
0x14000eda6  test    eax, eax
0x14000eda8  jg      short loc_14000EDB9
0x14000edaa  mov     rcx, [rdx]
0x14000edad  mov     rax, [rcx]
0x14000edb0  mov     rax, [rax+8]
0x14000edb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000edb9  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000edc0  mov     rcx, r15
0x14000edc3  mov     rax, [rax+18h]
0x14000edc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000edcc  add     rax, 18h
0x14000edd0  mov     [rbp+57h+var_90], rax
0x14000edd4  lea     rdx, aGivenName; "given_name"
0x14000eddb  lea     rcx, [rbp+57h+var_90]
0x14000eddf  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x14000ede4  test    al, al
0x14000ede6  jnz     short loc_14000EDFF
0x14000ede8  mov     r8d, 0Ah
0x14000edee  lea     rdx, aGivenName; "given_name"
0x14000edf5  lea     rcx, [rbp+57h+var_90]
0x14000edf9  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000edfe  nop
0x14000edff  lea     r8, [rbp+57h+var_90]
0x14000ee03  mov     rdx, rbx
0x14000ee06  lea     rcx, [rbp+57h+pExceptionObject]
0x14000ee0a  call    ?GetJsonDataAsString@Utils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVJsonObject@@AEBV23@@Z; Utils::GetJsonDataAsString(JsonObject const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000ee0f  nop
0x14000ee10  lea     rcx, [rdi+38h]
0x14000ee14  mov     rdx, rax
0x14000ee17  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000ee1c  nop
0x14000ee1d  mov     rdx, qword ptr [rbp+57h+pExceptionObject]
0x14000ee21  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000ee25  mov     eax, esi
0x14000ee27  lock xadd [rdx+10h], eax
0x14000ee2c  add     eax, esi
0x14000ee2e  test    eax, eax
0x14000ee30  jg      short loc_14000EE42
0x14000ee32  mov     rcx, [rdx]
0x14000ee35  mov     rax, [rcx]
0x14000ee38  mov     rax, [rax+8]
0x14000ee3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ee41  nop
0x14000ee42  mov     rdx, [rbp+57h+var_90]
0x14000ee46  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000ee4a  mov     eax, esi
0x14000ee4c  lock xadd [rdx+10h], eax
0x14000ee51  add     eax, esi
  ... truncated ...
```
