# JWSBuilder::JwsHeaderToJson(JWSBuilder::JwsHeader const &)

- ea: `0x14002a154`
- end: `0x14002a4a8`
- name: `?JwsHeaderToJson@JWSBuilder@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVJwsHeader@1@@Z`
- size: `852`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140029d48`

## callees

- `0x140001814`
- `0x140001b60`
- `0x140003044`
- `0x1400032ec`
- `0x1400054e8`
- `0x140007bf8`
- `0x14000e6a0`
- `0x1400129ec`
- `0x14001340c`
- `0x14001c7ac`
- `0x14001c95c`
- `0x14001cda4`
- `0x14001ce04`
- `0x14001ce88`
- `0x14001d6d0`
- `0x140029c50`
- `0x14002a154`
- `0x140030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14002a434`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14002a434`

## string_xrefs

- `0x14002a33d`: `onecore\ds\security\dsreg\win32\adal.native\jwsbuilder.cpp`
- `0x14002a384`: `onecore\ds\security\dsreg\win32\adal.native\jwsbuilder.cpp`

## pseudocode

```c
_QWORD *__fastcall JWSBuilder::JwsHeaderToJson(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v5; // rbx
  _WORD *v6; // rdx
  _QWORD *v7; // rbx
  _QWORD *v8; // rax
  _QWORD *v9; // rdx
  volatile signed __int32 *v10; // rbx
  _QWORD *v11; // rdi
  JsonArray *v12; // rax
  JsonArray *v13; // rbx
  const struct JsonValue *v14; // rax
  const struct JsonValue *v15; // rdi
  _WORD *v16; // rdx
  void *v17; // rbx
  __int64 v18; // rcx
  _QWORD *v19; // rax
  _QWORD *v20; // rdx
  void *Block; // [rsp+20h] [rbp-79h] BYREF
  const struct JsonValue *v23; // [rsp+28h] [rbp-71h] BYREF
  int v24; // [rsp+30h] [rbp-69h]
  _BYTE v25[32]; // [rsp+38h] [rbp-61h] BYREF
  _QWORD *v26; // [rsp+58h] [rbp-41h]
  __int128 v27; // [rsp+60h] [rbp-39h] BYREF
  __int64 v28; // [rsp+70h] [rbp-29h]
  char *v29[4]; // [rsp+80h] [rbp-19h] BYREF
  char *v30[4]; // [rsp+A0h] [rbp+7h] BYREF

  v26 = a2;
  v24 = 0;
  JsonObject::JsonObject((JsonObject *)v25);
  if ( *(_DWORD *)(*(_QWORD *)a3 - 16LL) )
  {
    v5 = std::wstring::wstring(v29, *(_WORD **)a3);
    std::wstring::wstring(&v27, L"alg");
    JsonObject::AddNameToValueMapping((__int64)v25, (__int64)&v27, (__int64)v5);
    std::wstring::~wstring((char **)&v27);
    std::wstring::~wstring(v29);
  }
  v6 = *(_WORD **)(a3 + 8);
  if ( *((_DWORD *)v6 - 4) )
  {
    v7 = std::wstring::wstring(v29, v6);
    std::wstring::wstring(&v27, L"typ");
    JsonObject::AddNameToValueMapping((__int64)v25, (__int64)&v27, (__int64)v7);
    std::wstring::~wstring((char **)&v27);
    std::wstring::~wstring(v29);
  }
  if ( *(_DWORD *)(*(_QWORD *)(a3 + 24) - 16LL) )
  {
    v27 = 0;
    v28 = 0;
    StringUtility::GetCertificateHashBytes(a3 + 24, &v27);
    Block = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    v8 = (_QWORD *)StringUtility::Base64UrlEncode(&v23, v27, (unsigned int)(DWORD2(v27) - v27));
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      &Block,
      v8);
    v9 = (_QWORD *)((char *)v23 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v23 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
    v10 = (volatile signed __int32 *)Block;
    v11 = std::wstring::wstring(v30, Block);
    std::wstring::wstring(v29, L"x5t");
    JsonObject::AddNameToValueMapping((__int64)v25, (__int64)v29, (__int64)v11);
    std::wstring::~wstring(v29);
    std::wstring::~wstring(v30);
    if ( _InterlockedExchangeAdd(v10 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 - 3) + 8LL))(*((_QWORD *)v10 - 3));
    std::vector<unsigned char>::~vector<unsigned char>((char **)&v27);
  }
  if ( *(_DWORD *)(*(_QWORD *)(a3 + 16) - 16LL) )
  {
    v12 = (JsonArray *)operator new(0x28u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\jwsbuilder.cpp");
    v13 = v12;
    v23 = v12;
    if ( v12 )
    {
      *((_DWORD *)v12 + 2) = 2;
      *(_QWORD *)v12 = &JsonArray::`vftable';
      *((_QWORD *)v12 + 2) = 0;
      *((_QWORD *)v12 + 3) = 0;
      *((_QWORD *)v12 + 4) = 0;
    }
    else
    {
      v13 = 0;
    }
    v14 = (const struct JsonValue *)operator new(
                                      0x40u,
                                      1,
                                      "onecore\\ds\\security\\dsreg\\win32\\adal.native\\jwsbuilder.cpp");
    v15 = v14;
    v23 = v14;
    if ( v14 )
    {
      v16 = *(_WORD **)(a3 + 16);
      *((_DWORD *)v14 + 2) = 3;
      *(_QWORD *)v14 = &JsonPrimitive::`vftable';
      *((_BYTE *)v14 + 16) = 0;
      *((_QWORD *)v14 + 3) = 0;
      std::wstring::wstring((_QWORD *)v14 + 4, v16);
    }
    else
    {
      v15 = 0;
    }
    JsonArray::Add(v13, v15);
    std::wstring::wstring(v29, L"x5c");
    JsonObject::AddNameToValueMapping((__int64)v25, (__int64)v29, (__int64)v13);
    std::wstring::~wstring(v29);
  }
  Block = 0;
  JsonObject::ToJsonString((JsonObject *)v25, (unsigned __int16 **)&Block);
  v17 = Block;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    a2,
    (__int64)Block);
  v24 = 1;
  if ( v17 )
    free(v17);
  v19 = JWSBuilder::EncodeJsonString(v18, &v23, (__int64)a2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(a2, v19);
  v20 = (_QWORD *)((char *)v23 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v23 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 8LL))(*v20);
  JsonObject::~JsonObject((JsonObject *)v25);
  return a2;
}

```

## disassembly

```asm
0x14002a154  mov     [rsp-8+arg_0], rbx
0x14002a159  push    rbp
0x14002a15a  push    rsi
0x14002a15b  push    rdi
0x14002a15c  push    r14
0x14002a15e  push    r15
0x14002a160  lea     rbp, [rsp-37h]
0x14002a165  sub     rsp, 0D0h
0x14002a16c  mov     rax, cs:__security_cookie
0x14002a173  xor     rax, rsp
0x14002a176  mov     [rbp+57h+var_30], rax
0x14002a17a  mov     r14, r8
0x14002a17d  mov     rsi, rdx
0x14002a180  mov     [rbp+57h+var_98], rdx
0x14002a184  xor     r15d, r15d
0x14002a187  mov     [rbp+57h+var_C0], r15d
0x14002a18b  lea     rcx, [rbp+57h+var_B8]; this
0x14002a18f  call    ??0JsonObject@@QEAA@XZ; JsonObject::JsonObject(void)
0x14002a194  nop
0x14002a195  mov     rdx, [r14]
0x14002a198  cmp     [rdx-10h], r15d
0x14002a19c  jz      short loc_14002A1DF
0x14002a19e  lea     rcx, [rbp+57h+var_70]
0x14002a1a2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14002a1a7  mov     rbx, rax
0x14002a1aa  lea     rdx, aAlg; "alg"
0x14002a1b1  lea     rcx, [rbp+57h+var_90]
0x14002a1b5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14002a1ba  nop
0x14002a1bb  mov     r8, rbx
0x14002a1be  lea     rdx, [rbp+57h+var_90]
0x14002a1c2  lea     rcx, [rbp+57h+var_B8]
0x14002a1c6  call    ?AddNameToValueMapping@JsonObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; JsonObject::AddNameToValueMapping(std::wstring const &,std::wstring const &)
0x14002a1cb  nop
0x14002a1cc  lea     rcx, [rbp+57h+var_90]
0x14002a1d0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002a1d5  nop
0x14002a1d6  lea     rcx, [rbp+57h+var_70]
0x14002a1da  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002a1df  mov     rdx, [r14+8]
0x14002a1e3  cmp     [rdx-10h], r15d
0x14002a1e7  jz      short loc_14002A22A
0x14002a1e9  lea     rcx, [rbp+57h+var_70]
0x14002a1ed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14002a1f2  mov     rbx, rax
0x14002a1f5  lea     rdx, aTyp; "typ"
0x14002a1fc  lea     rcx, [rbp+57h+var_90]
0x14002a200  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14002a205  nop
0x14002a206  mov     r8, rbx
0x14002a209  lea     rdx, [rbp+57h+var_90]
0x14002a20d  lea     rcx, [rbp+57h+var_B8]
0x14002a211  call    ?AddNameToValueMapping@JsonObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; JsonObject::AddNameToValueMapping(std::wstring const &,std::wstring const &)
0x14002a216  nop
0x14002a217  lea     rcx, [rbp+57h+var_90]
0x14002a21b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002a220  nop
0x14002a221  lea     rcx, [rbp+57h+var_70]
0x14002a225  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002a22a  lea     rcx, [r14+18h]
0x14002a22e  mov     rax, [rcx]
0x14002a231  cmp     [rax-10h], r15d
0x14002a235  jz      loc_14002A329
0x14002a23b  xorps   xmm0, xmm0
0x14002a23e  movdqu  [rbp+57h+var_90], xmm0
0x14002a243  mov     [rbp+57h+var_80], r15
0x14002a247  lea     rdx, [rbp+57h+var_90]
0x14002a24b  call    ?GetCertificateHashBytes@StringUtility@@SAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; StringUtility::GetCertificateHashBytes(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,std::vector<uchar> &)
0x14002a250  nop
0x14002a251  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002a258  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002a25f  mov     rax, [rax+18h]
0x14002a263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a268  add     rax, 18h
0x14002a26c  mov     [rbp+57h+Block], rax
0x14002a270  mov     rdx, qword ptr [rbp+57h+var_90]
0x14002a274  mov     r8d, dword ptr [rbp+57h+var_90+8]
0x14002a278  sub     r8d, edx
0x14002a27b  lea     rcx, [rbp+57h+var_C8]
0x14002a27f  call    ?Base64UrlEncode@StringUtility@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBEH@Z; StringUtility::Base64UrlEncode(uchar const *,int)
0x14002a284  nop
0x14002a285  mov     rdx, rax
0x14002a288  lea     rcx, [rbp+57h+Block]
0x14002a28c  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14002a291  nop
0x14002a292  mov     rdx, [rbp+57h+var_C8]
0x14002a296  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002a29a  or      eax, 0FFFFFFFFh
0x14002a29d  lock xadd [rdx+10h], eax
0x14002a2a2  sub     eax, 1
0x14002a2a5  jg      short loc_14002A2B6
0x14002a2a7  mov     rcx, [rdx]
0x14002a2aa  mov     rax, [rcx]
0x14002a2ad  mov     rax, [rax+8]
0x14002a2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a2b6  mov     rbx, [rbp+57h+Block]
0x14002a2ba  mov     rdx, rbx
0x14002a2bd  lea     rcx, [rbp+57h+var_50]
0x14002a2c1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14002a2c6  mov     rdi, rax
0x14002a2c9  lea     rdx, aX5t; "x5t"
0x14002a2d0  lea     rcx, [rbp+57h+var_70]
0x14002a2d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14002a2d9  nop
0x14002a2da  mov     r8, rdi
0x14002a2dd  lea     rdx, [rbp+57h+var_70]
0x14002a2e1  lea     rcx, [rbp+57h+var_B8]
0x14002a2e5  call    ?AddNameToValueMapping@JsonObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; JsonObject::AddNameToValueMapping(std::wstring const &,std::wstring const &)
0x14002a2ea  nop
0x14002a2eb  lea     rcx, [rbp+57h+var_70]
0x14002a2ef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002a2f4  nop
0x14002a2f5  lea     rcx, [rbp+57h+var_50]
0x14002a2f9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002a2fe  nop
0x14002a2ff  lea     rdx, [rbx-18h]
0x14002a303  or      eax, 0FFFFFFFFh
0x14002a306  lock xadd [rdx+10h], eax
0x14002a30b  sub     eax, 1
0x14002a30e  jg      short loc_14002A320
0x14002a310  mov     rcx, [rdx]
0x14002a313  mov     rax, [rcx]
0x14002a316  mov     rax, [rax+8]
0x14002a31a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a31f  nop
0x14002a320  lea     rcx, [rbp+57h+var_90]
0x14002a324  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x14002a329  mov     rax, [r14+10h]
0x14002a32d  cmp     [rax-10h], r15d
0x14002a331  jz      loc_14002A405
0x14002a337  mov     r9d, 3Eh ; '>'; int
0x14002a33d  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002a344  lea     edx, [r9-3Dh]; int
0x14002a348  lea     ecx, [rdx+27h]; unsigned __int64
0x14002a34b  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x14002a350  mov     rbx, rax
0x14002a353  mov     [rbp+57h+var_C8], rax
0x14002a357  test    rax, rax
0x14002a35a  jz      short loc_14002A37B
0x14002a35c  mov     dword ptr [rax+8], 2
0x14002a363  lea     rax, ??_7JsonArray@@6B@; const JsonArray::`vftable'
0x14002a36a  mov     [rbx], rax
0x14002a36d  mov     [rbx+10h], r15
0x14002a371  mov     [rbx+18h], r15
0x14002a375  mov     [rbx+20h], r15
0x14002a379  jmp     short loc_14002A37E
0x14002a37b  mov     rbx, r15
0x14002a37e  mov     r9d, 3Fh ; '?'; int
0x14002a384  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002a38b  lea     edx, [r9-3Eh]; int
0x14002a38f  lea     ecx, [rdx+3Fh]; unsigned __int64
0x14002a392  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x14002a397  mov     rdi, rax
0x14002a39a  mov     [rbp+57h+var_C8], rax
0x14002a39e  test    rax, rax
0x14002a3a1  jz      short loc_14002A3CC
0x14002a3a3  mov     rdx, [r14+10h]
0x14002a3a7  mov     dword ptr [rax+8], 3
0x14002a3ae  lea     rax, ??_7JsonPrimitive@@6B@; const JsonPrimitive::`vftable'
0x14002a3b5  mov     [rdi], rax
0x14002a3b8  mov     [rdi+10h], r15b
0x14002a3bc  mov     [rdi+18h], r15
0x14002a3c0  lea     rcx, [rdi+20h]
0x14002a3c4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14002a3c9  nop
0x14002a3ca  jmp     short loc_14002A3CF
0x14002a3cc  mov     rdi, r15
0x14002a3cf  mov     rdx, rdi; struct JsonValue *
0x14002a3d2  mov     rcx, rbx; this
0x14002a3d5  call    ?Add@JsonArray@@QEAAXPEBVJsonValue@@@Z; JsonArray::Add(JsonValue const *)
0x14002a3da  lea     rdx, aX5c; "x5c"
0x14002a3e1  lea     rcx, [rbp+57h+var_70]
0x14002a3e5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14002a3ea  nop
0x14002a3eb  mov     r8, rbx
0x14002a3ee  lea     rdx, [rbp+57h+var_70]
0x14002a3f2  lea     rcx, [rbp+57h+var_B8]
0x14002a3f6  call    ?AddNameToValueMapping@JsonObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@Z; JsonObject::AddNameToValueMapping(std::wstring const &,JsonValue const *)
0x14002a3fb  nop
0x14002a3fc  lea     rcx, [rbp+57h+var_70]
0x14002a400  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002a405  mov     [rbp+57h+Block], r15
0x14002a409  lea     rdx, [rbp+57h+Block]; unsigned __int16 **
0x14002a40d  lea     rcx, [rbp+57h+var_B8]; this
0x14002a411  call    ?ToJsonString@JsonObject@@UEBAKPEAPEAG@Z; JsonObject::ToJsonString(ushort * *)
0x14002a416  mov     rbx, [rbp+57h+Block]
0x14002a41a  mov     rdx, rbx
0x14002a41d  mov     rcx, rsi
0x14002a420  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002a425  mov     [rbp+57h+var_C0], 1
0x14002a42c  test    rbx, rbx
0x14002a42f  jz      short loc_14002A43A
0x14002a431  mov     rcx, rbx; Block
0x14002a434  call    cs:__imp_free
0x14002a43a  mov     r8, rsi
0x14002a43d  lea     rdx, [rbp+57h+var_C8]
0x14002a441  call    ?EncodeJsonString@JWSBuilder@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@@Z; JWSBuilder::EncodeJsonString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14002a446  nop
0x14002a447  mov     rdx, rax
0x14002a44a  mov     rcx, rsi
0x14002a44d  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14002a452  nop
0x14002a453  mov     rdx, [rbp+57h+var_C8]
0x14002a457  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002a45b  or      eax, 0FFFFFFFFh
0x14002a45e  lock xadd [rdx+10h], eax
0x14002a463  sub     eax, 1
0x14002a466  jg      short loc_14002A478
0x14002a468  mov     rcx, [rdx]
0x14002a46b  mov     r8, [rcx]
0x14002a46e  mov     rax, [r8+8]
0x14002a472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a477  nop
0x14002a478  lea     rcx, [rbp+57h+var_B8]; this
0x14002a47c  call    ??1JsonObject@@UEAA@XZ; JsonObject::~JsonObject(void)
0x14002a481  mov     rax, rsi
0x14002a484  mov     rcx, [rbp+57h+var_30]
0x14002a488  xor     rcx, rsp; StackCookie
0x14002a48b  call    __security_check_cookie
0x14002a490  mov     rbx, [rsp+0F0h+arg_0]
0x14002a498  add     rsp, 0D0h
0x14002a49f  pop     r15
0x14002a4a1  pop     r14
0x14002a4a3  pop     rdi
0x14002a4a4  pop     rsi
0x14002a4a5  pop     rbp
0x14002a4a6  retn
```
