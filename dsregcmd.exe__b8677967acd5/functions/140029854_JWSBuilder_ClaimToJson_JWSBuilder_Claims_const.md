# JWSBuilder::ClaimToJson(JWSBuilder::Claims const &)

- ea: `0x140029854`
- end: `0x140029c4a`
- name: `?ClaimToJson@JWSBuilder@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBVClaims@1@@Z`
- size: `1014`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x140029d48`

## callees

- `0x140001b60`
- `0x140003044`
- `0x1400032ec`
- `0x1400054e8`
- `0x140007bf8`
- `0x1400081d8`
- `0x140009398`
- `0x140009470`
- `0x14001c7ac`
- `0x14001c95c`
- `0x14001ce04`
- `0x14001d6d0`
- `0x140029854`
- `0x140029c50`
- `0x140030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140029b8d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140029b8d`

## pseudocode

```c
_QWORD *__fastcall JWSBuilder::ClaimToJson(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v5; // rax
  _WORD **v6; // rax
  _QWORD *v7; // rbx
  _QWORD *v8; // rbx
  _WORD *v9; // rdx
  _QWORD *v10; // rbx
  _WORD *v11; // rdx
  _QWORD *v12; // rbx
  _WORD *v13; // rdx
  _QWORD *v14; // rbx
  _QWORD *v15; // rbx
  _WORD *v16; // rdx
  _QWORD *v17; // rbx
  _WORD *v18; // rdx
  _QWORD *v19; // rbx
  void *v20; // rbx
  __int64 v21; // rcx
  _QWORD *v22; // rax
  _QWORD *v23; // rdx
  _QWORD *v24; // rdx
  _QWORD *v25; // rdx
  void *Block; // [rsp+20h] [rbp-49h] BYREF
  int v28; // [rsp+28h] [rbp-41h]
  __int64 v29; // [rsp+30h] [rbp-39h] BYREF
  __int64 v30; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v31[32]; // [rsp+40h] [rbp-29h] BYREF
  _QWORD *v32; // [rsp+60h] [rbp-9h]
  char *v33[4]; // [rsp+68h] [rbp-1h] BYREF
  char *v34[4]; // [rsp+88h] [rbp+1Fh] BYREF

  v32 = a2;
  v28 = 0;
  JsonObject::JsonObject((JsonObject *)v31);
  v29 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &v29,
    L"%lld",
    *(_QWORD *)(a3 + 16));
  v30 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &v30,
    L"%lld",
    *(_QWORD *)(a3 + 16) + 600LL);
  v5 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimRight(&v29);
  v6 = (_WORD **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimLeft(v5);
  v7 = std::wstring::wstring(v34, *v6);
  std::wstring::wstring(v33, L"iat");
  JsonObject::AddNameToValueMapping((__int64)v31, (__int64)v33, (__int64)v7);
  std::wstring::~wstring(v33);
  std::wstring::~wstring(v34);
  v8 = std::wstring::wstring(v34, *(_WORD **)(a3 + 40));
  std::wstring::wstring(v33, L"nonce");
  JsonObject::AddNameToValueMapping((__int64)v31, (__int64)v33, (__int64)v8);
  std::wstring::~wstring(v33);
  std::wstring::~wstring(v34);
  v9 = *(_WORD **)(a3 + 32);
  if ( *((_DWORD *)v9 - 4) )
  {
    v10 = std::wstring::wstring(v34, v9);
    std::wstring::wstring(v33, L"jti");
    JsonObject::AddNameToValueMapping((__int64)v31, (__int64)v33, (__int64)v10);
    std::wstring::~wstring(v33);
    std::wstring::~wstring(v34);
  }
  v11 = *(_WORD **)(a3 + 48);
  if ( *((_DWORD *)v11 - 4) )
  {
    v12 = std::wstring::wstring(v34, v11);
    std::wstring::wstring(v33, L"nbf");
    JsonObject::AddNameToValueMapping((__int64)v31, (__int64)v33, (__int64)v12);
    std::wstring::~wstring(v33);
    std::wstring::~wstring(v34);
  }
  v13 = *(_WORD **)(a3 + 56);
  if ( *((_DWORD *)v13 - 4) )
  {
    v14 = std::wstring::wstring(v34, v13);
    std::wstring::wstring(v33, L"exp");
    JsonObject::AddNameToValueMapping((__int64)v31, (__int64)v33, (__int64)v14);
    std::wstring::~wstring(v33);
    std::wstring::~wstring(v34);
  }
  if ( *(_DWORD *)(*(_QWORD *)a3 - 16LL) )
  {
    v15 = std::wstring::wstring(v34, *(_WORD **)a3);
    std::wstring::wstring(v33, L"aud");
    JsonObject::AddNameToValueMapping((__int64)v31, (__int64)v33, (__int64)v15);
    std::wstring::~wstring(v33);
    std::wstring::~wstring(v34);
  }
  v16 = *(_WORD **)(a3 + 8);
  if ( *((_DWORD *)v16 - 4) )
  {
    v17 = std::wstring::wstring(v34, v16);
    std::wstring::wstring(v33, L"iss");
    JsonObject::AddNameToValueMapping((__int64)v31, (__int64)v33, (__int64)v17);
    std::wstring::~wstring(v33);
    std::wstring::~wstring(v34);
  }
  v18 = *(_WORD **)(a3 + 24);
  if ( *((_DWORD *)v18 - 4) )
  {
    v19 = std::wstring::wstring(v34, v18);
    std::wstring::wstring(v33, L"sub");
    JsonObject::AddNameToValueMapping((__int64)v31, (__int64)v33, (__int64)v19);
    std::wstring::~wstring(v33);
    std::wstring::~wstring(v34);
  }
  Block = 0;
  JsonObject::ToJsonString((JsonObject *)v31, (unsigned __int16 **)&Block);
  v20 = Block;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    a2,
    (__int64)Block);
  v28 = 1;
  if ( v20 )
    free(v20);
  v22 = (_QWORD *)JWSBuilder::EncodeJsonString(v21, &Block, a2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(a2, v22);
  v23 = (char *)Block - 24;
  if ( _InterlockedDecrement((volatile signed __int32 *)Block - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 8LL))(*v23);
  v24 = (_QWORD *)(v30 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v30 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v24 + 8LL))(*v24);
  v25 = (_QWORD *)(v29 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v29 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 8LL))(*v25);
  JsonObject::~JsonObject((JsonObject *)v31);
  return a2;
}

```

## disassembly

```asm
0x140029854  mov     [rsp-8+arg_0], rbx
0x140029859  push    rbp
0x14002985a  push    rsi
0x14002985b  push    rdi
0x14002985c  lea     rbp, [rsp-47h]
0x140029861  sub     rsp, 0B0h
0x140029868  mov     rax, cs:__security_cookie
0x14002986f  xor     rax, rsp
0x140029872  mov     [rbp+57h+var_18], rax
0x140029876  mov     rdi, r8
0x140029879  mov     rsi, rdx
0x14002987c  mov     [rbp+57h+var_60], rdx
0x140029880  mov     [rbp+57h+var_98], 0
0x140029887  lea     rcx, [rbp+57h+var_80]; this
0x14002988b  call    ??0JsonObject@@QEAA@XZ; JsonObject::JsonObject(void)
0x140029890  nop
0x140029891  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140029898  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002989f  mov     rax, [rax+18h]
0x1400298a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400298a8  add     rax, 18h
0x1400298ac  mov     [rbp+57h+var_90], rax
0x1400298b0  mov     r8, [rdi+10h]
0x1400298b4  lea     rdx, aLld; "%lld"
0x1400298bb  lea     rcx, [rbp+57h+var_90]
0x1400298bf  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1400298c4  nop
0x1400298c5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400298cc  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400298d3  mov     rax, [rax+18h]
0x1400298d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400298dc  add     rax, 18h
0x1400298e0  mov     [rbp+57h+var_88], rax
0x1400298e4  mov     r8, [rdi+10h]
0x1400298e8  add     r8, 258h
0x1400298ef  lea     rdx, aLld; "%lld"
0x1400298f6  lea     rcx, [rbp+57h+var_88]
0x1400298fa  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1400298ff  lea     rcx, [rbp+57h+var_90]
0x140029903  call    ?TrimRight@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimRight(void)
0x140029908  mov     rcx, rax
0x14002990b  call    ?TrimLeft@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimLeft(void)
0x140029910  mov     rdx, [rax]
0x140029913  lea     rcx, [rbp+57h+var_38]
0x140029917  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14002991c  mov     rbx, rax
0x14002991f  lea     rdx, aIat; "iat"
0x140029926  lea     rcx, [rbp+57h+var_58]
0x14002992a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14002992f  nop
0x140029930  mov     r8, rbx
0x140029933  lea     rdx, [rbp+57h+var_58]
0x140029937  lea     rcx, [rbp+57h+var_80]
0x14002993b  call    ?AddNameToValueMapping@JsonObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; JsonObject::AddNameToValueMapping(std::wstring const &,std::wstring const &)
0x140029940  nop
0x140029941  lea     rcx, [rbp+57h+var_58]
0x140029945  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002994a  nop
0x14002994b  lea     rcx, [rbp+57h+var_38]
0x14002994f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140029954  mov     rdx, [rdi+28h]
0x140029958  lea     rcx, [rbp+57h+var_38]
0x14002995c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140029961  mov     rbx, rax
0x140029964  lea     rdx, aNonce; "nonce"
0x14002996b  lea     rcx, [rbp+57h+var_58]
0x14002996f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140029974  nop
0x140029975  mov     r8, rbx
0x140029978  lea     rdx, [rbp+57h+var_58]
0x14002997c  lea     rcx, [rbp+57h+var_80]
0x140029980  call    ?AddNameToValueMapping@JsonObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; JsonObject::AddNameToValueMapping(std::wstring const &,std::wstring const &)
0x140029985  nop
0x140029986  lea     rcx, [rbp+57h+var_58]
0x14002998a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002998f  nop
0x140029990  lea     rcx, [rbp+57h+var_38]
0x140029994  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140029999  mov     rdx, [rdi+20h]
0x14002999d  cmp     dword ptr [rdx-10h], 0
0x1400299a1  jz      short loc_1400299E4
0x1400299a3  lea     rcx, [rbp+57h+var_38]
0x1400299a7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400299ac  mov     rbx, rax
0x1400299af  lea     rdx, aJti; "jti"
0x1400299b6  lea     rcx, [rbp+57h+var_58]
0x1400299ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400299bf  nop
0x1400299c0  mov     r8, rbx
0x1400299c3  lea     rdx, [rbp+57h+var_58]
0x1400299c7  lea     rcx, [rbp+57h+var_80]
0x1400299cb  call    ?AddNameToValueMapping@JsonObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; JsonObject::AddNameToValueMapping(std::wstring const &,std::wstring const &)
0x1400299d0  nop
0x1400299d1  lea     rcx, [rbp+57h+var_58]
0x1400299d5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400299da  nop
0x1400299db  lea     rcx, [rbp+57h+var_38]
0x1400299df  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400299e4  mov     rdx, [rdi+30h]
0x1400299e8  cmp     dword ptr [rdx-10h], 0
0x1400299ec  jz      short loc_140029A2F
0x1400299ee  lea     rcx, [rbp+57h+var_38]
0x1400299f2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400299f7  mov     rbx, rax
0x1400299fa  lea     rdx, aNbf; "nbf"
0x140029a01  lea     rcx, [rbp+57h+var_58]
0x140029a05  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140029a0a  nop
0x140029a0b  mov     r8, rbx
0x140029a0e  lea     rdx, [rbp+57h+var_58]
0x140029a12  lea     rcx, [rbp+57h+var_80]
0x140029a16  call    ?AddNameToValueMapping@JsonObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; JsonObject::AddNameToValueMapping(std::wstring const &,std::wstring const &)
0x140029a1b  nop
0x140029a1c  lea     rcx, [rbp+57h+var_58]
0x140029a20  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140029a25  nop
0x140029a26  lea     rcx, [rbp+57h+var_38]
0x140029a2a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140029a2f  mov     rdx, [rdi+38h]
0x140029a33  cmp     dword ptr [rdx-10h], 0
0x140029a37  jz      short loc_140029A7A
0x140029a39  lea     rcx, [rbp+57h+var_38]
0x140029a3d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140029a42  mov     rbx, rax
0x140029a45  lea     rdx, aExp; "exp"
0x140029a4c  lea     rcx, [rbp+57h+var_58]
0x140029a50  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140029a55  nop
0x140029a56  mov     r8, rbx
0x140029a59  lea     rdx, [rbp+57h+var_58]
0x140029a5d  lea     rcx, [rbp+57h+var_80]
0x140029a61  call    ?AddNameToValueMapping@JsonObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; JsonObject::AddNameToValueMapping(std::wstring const &,std::wstring const &)
0x140029a66  nop
0x140029a67  lea     rcx, [rbp+57h+var_58]
0x140029a6b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140029a70  nop
0x140029a71  lea     rcx, [rbp+57h+var_38]
0x140029a75  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140029a7a  mov     rdx, [rdi]
0x140029a7d  cmp     dword ptr [rdx-10h], 0
0x140029a81  jz      short loc_140029AC4
0x140029a83  lea     rcx, [rbp+57h+var_38]
0x140029a87  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140029a8c  mov     rbx, rax
0x140029a8f  lea     rdx, aAud; "aud"
0x140029a96  lea     rcx, [rbp+57h+var_58]
0x140029a9a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140029a9f  nop
0x140029aa0  mov     r8, rbx
0x140029aa3  lea     rdx, [rbp+57h+var_58]
0x140029aa7  lea     rcx, [rbp+57h+var_80]
0x140029aab  call    ?AddNameToValueMapping@JsonObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; JsonObject::AddNameToValueMapping(std::wstring const &,std::wstring const &)
0x140029ab0  nop
0x140029ab1  lea     rcx, [rbp+57h+var_58]
0x140029ab5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140029aba  nop
0x140029abb  lea     rcx, [rbp+57h+var_38]
0x140029abf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140029ac4  mov     rdx, [rdi+8]
0x140029ac8  cmp     dword ptr [rdx-10h], 0
0x140029acc  jz      short loc_140029B0F
0x140029ace  lea     rcx, [rbp+57h+var_38]
0x140029ad2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140029ad7  mov     rbx, rax
0x140029ada  lea     rdx, aIss; "iss"
0x140029ae1  lea     rcx, [rbp+57h+var_58]
0x140029ae5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140029aea  nop
0x140029aeb  mov     r8, rbx
0x140029aee  lea     rdx, [rbp+57h+var_58]
0x140029af2  lea     rcx, [rbp+57h+var_80]
0x140029af6  call    ?AddNameToValueMapping@JsonObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; JsonObject::AddNameToValueMapping(std::wstring const &,std::wstring const &)
0x140029afb  nop
0x140029afc  lea     rcx, [rbp+57h+var_58]
0x140029b00  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140029b05  nop
0x140029b06  lea     rcx, [rbp+57h+var_38]
0x140029b0a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140029b0f  mov     rdx, [rdi+18h]
0x140029b13  cmp     dword ptr [rdx-10h], 0
0x140029b17  jz      short loc_140029B5A
0x140029b19  lea     rcx, [rbp+57h+var_38]
0x140029b1d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140029b22  mov     rbx, rax
0x140029b25  lea     rdx, aSub; "sub"
0x140029b2c  lea     rcx, [rbp+57h+var_58]
0x140029b30  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140029b35  nop
0x140029b36  mov     r8, rbx
0x140029b39  lea     rdx, [rbp+57h+var_58]
0x140029b3d  lea     rcx, [rbp+57h+var_80]
0x140029b41  call    ?AddNameToValueMapping@JsonObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; JsonObject::AddNameToValueMapping(std::wstring const &,std::wstring const &)
0x140029b46  nop
0x140029b47  lea     rcx, [rbp+57h+var_58]
0x140029b4b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140029b50  nop
0x140029b51  lea     rcx, [rbp+57h+var_38]
0x140029b55  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140029b5a  mov     [rbp+57h+Block], 0
0x140029b62  lea     rdx, [rbp+57h+Block]; unsigned __int16 **
0x140029b66  lea     rcx, [rbp+57h+var_80]; this
0x140029b6a  call    ?ToJsonString@JsonObject@@UEBAKPEAPEAG@Z; JsonObject::ToJsonString(ushort * *)
0x140029b6f  mov     rbx, [rbp+57h+Block]
0x140029b73  mov     rdx, rbx
0x140029b76  mov     rcx, rsi
0x140029b79  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140029b7e  mov     [rbp+57h+var_98], 1
0x140029b85  test    rbx, rbx
0x140029b88  jz      short loc_140029B93
0x140029b8a  mov     rcx, rbx; Block
0x140029b8d  call    cs:__imp_free
0x140029b93  mov     r8, rsi
0x140029b96  lea     rdx, [rbp+57h+Block]
0x140029b9a  call    ?EncodeJsonString@JWSBuilder@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@@Z; JWSBuilder::EncodeJsonString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140029b9f  nop
0x140029ba0  mov     rdx, rax
0x140029ba3  mov     rcx, rsi
0x140029ba6  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140029bab  nop
0x140029bac  mov     rdx, [rbp+57h+Block]
0x140029bb0  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140029bb4  or      ebx, 0FFFFFFFFh
0x140029bb7  mov     eax, ebx
0x140029bb9  lock xadd [rdx+10h], eax
0x140029bbe  add     eax, ebx
0x140029bc0  test    eax, eax
0x140029bc2  jg      short loc_140029BD4
0x140029bc4  mov     rcx, [rdx]
0x140029bc7  mov     rax, [rcx]
0x140029bca  mov     rax, [rax+8]
0x140029bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029bd3  nop
0x140029bd4  mov     rdx, [rbp+57h+var_88]
0x140029bd8  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140029bdc  mov     eax, ebx
0x140029bde  lock xadd [rdx+10h], eax
0x140029be3  add     eax, ebx
0x140029be5  test    eax, eax
0x140029be7  jg      short loc_140029BF9
0x140029be9  mov     rcx, [rdx]
0x140029bec  mov     rax, [rcx]
0x140029bef  mov     rax, [rax+8]
0x140029bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029bf8  nop
0x140029bf9  mov     rdx, [rbp+57h+var_90]
0x140029bfd  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140029c01  mov     eax, ebx
0x140029c03  lock xadd [rdx+10h], eax
0x140029c08  add     eax, ebx
0x140029c0a  test    eax, eax
0x140029c0c  jg      short loc_140029C1E
0x140029c0e  mov     rcx, [rdx]
0x140029c11  mov     r8, [rcx]
0x140029c14  mov     rax, [r8+8]
0x140029c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029c1d  nop
0x140029c1e  lea     rcx, [rbp+57h+var_80]; this
0x140029c22  call    ??1JsonObject@@UEAA@XZ; JsonObject::~JsonObject(void)
0x140029c27  mov     rax, rsi
0x140029c2a  mov     rcx, [rbp+57h+var_18]
0x140029c2e  xor     rcx, rsp; StackCookie
0x140029c31  call    __security_check_cookie
0x140029c36  mov     rbx, [rsp+0C0h+arg_0]
0x140029c3e  add     rsp, 0B0h
0x140029c45  pop     rdi
0x140029c46  pop     rsi
0x140029c47  pop     rbp
0x140029c48  retn
```
