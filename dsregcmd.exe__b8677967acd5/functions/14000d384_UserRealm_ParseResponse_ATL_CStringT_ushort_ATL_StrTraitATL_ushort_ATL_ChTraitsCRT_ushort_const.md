# UserRealm::ParseResponse(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x14000d384`
- end: `0x14000d7a0`
- name: `?ParseResponse@UserRealm@@AEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1052`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14000d134`

## callees

- `0x140001b60`
- `0x1400028ac`
- `0x140003044`
- `0x1400032ec`
- `0x1400054e8`
- `0x1400061dc`
- `0x140007bf8`
- `0x14000caac`
- `0x14000d310`
- `0x14000d384`
- `0x14000df44`
- `0x14001cf60`
- `0x1400234fc`
- `0x1400239a4`
- `0x140024894`
- `0x14002c3d0`
- `0x14002c3e8`
- `0x140030010`

## string_xrefs

- `0x14000d4b4`: `federation_protocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall UserRealm::ParseResponse(__int64 a1, __int64 *a2)
{
  JsonObject *v4; // rdi
  __m128i *JsonDataAsString; // rax
  _QWORD *Lower; // rax
  const wchar_t *v7; // rbx
  __m128i *v8; // rax
  _QWORD *v9; // rax
  int v10; // eax
  __m128i *v11; // rax
  __int64 v12; // r8
  __m128i *v13; // rax
  __int64 v14; // r8
  wchar_t *v15; // rdx
  __m128i *v16; // rax
  __int64 v17; // r8
  wchar_t *v18; // rdx
  void *v19; // rcx
  wchar_t *v20; // [rsp+20h] [rbp-99h] BYREF
  wchar_t *String1[2]; // [rsp+28h] [rbp-91h] BYREF
  void *Block[7]; // [rsp+38h] [rbp-81h] BYREF
  __m128i pExceptionObject[2]; // [rsp+70h] [rbp-49h] BYREF
  __m128i v24[2]; // [rsp+90h] [rbp-29h] BYREF
  __m128i v25[2]; // [rsp+B0h] [rbp-9h] BYREF

  if ( *(_DWORD *)(*a2 - 16) )
  {
    JsonReader::JsonReader((JsonReader *)Block);
    std::wstring::wstring(v24, (_WORD *)*a2);
    v4 = JsonReader::Parse(Block, v24);
    String1[1] = (wchar_t *)v4;
    std::wstring::~wstring((char **)v24);
    if ( !v4 || *((_DWORD *)v4 + 2) != 1 )
    {
      Exception::Exception((Exception *)pExceptionObject, -894894053);
      throw (Exception *)pExceptionObject;
    }
    JsonDataAsString = JsonObject::GetJsonDataAsString((__int64)v4, v25, L"account_type");
    if ( JsonDataAsString[1].m128i_i64[1] > 7uLL )
      JsonDataAsString = (__m128i *)JsonDataAsString->m128i_i64[0];
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      String1,
      (__int64)JsonDataAsString);
    std::wstring::~wstring((char **)v25);
    Lower = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(String1);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      String1,
      Lower);
    v7 = String1[0];
    if ( !*((_DWORD *)String1[0] - 4) )
    {
      ServiceException::ServiceException((__int64)pExceptionObject, -894894050, a2);
      throw (ServiceException *)pExceptionObject;
    }
    *(_DWORD *)(a1 + 44) = 2;
    *(_DWORD *)(a1 + 48) = 2;
    if ( !wcscmp_0(v7, L"managed") )
    {
      *(_DWORD *)(a1 + 44) = 1;
    }
    else if ( !wcscmp_0(v7, L"federated") )
    {
      *(_DWORD *)(a1 + 44) = 0;
      v8 = JsonObject::GetJsonDataAsString((__int64)v4, v24, L"federation_protocol");
      if ( v8[1].m128i_i64[1] > 7uLL )
        v8 = (__m128i *)v8->m128i_i64[0];
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v20,
        (__int64)v8);
      std::wstring::~wstring((char **)v24);
      v9 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&v20);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        &v20,
        v9);
      if ( !wcscmp_0(v20, L"wstrust") )
      {
        v10 = 0;
      }
      else
      {
        if ( wcscmp_0(v20, L"saml20") )
        {
          Exception::Exception((Exception *)pExceptionObject, -894894052);
          throw (Exception *)pExceptionObject;
        }
        v10 = 1;
      }
      *(_DWORD *)(a1 + 48) = v10;
      v11 = JsonObject::GetJsonDataAsString((__int64)v4, pExceptionObject, L"federation_metadata_url");
      if ( v11[1].m128i_i64[1] > 7uLL )
        v11 = (__m128i *)v11->m128i_i64[0];
      if ( v11 )
      {
        v12 = -1;
        do
          ++v12;
        while ( v11->m128i_i16[v12] );
      }
      else
      {
        v12 = 0;
      }
      ATL::CSimpleStringT<unsigned short,0>::SetString(a1 + 56, v11, v12);
      std::wstring::~wstring((char **)pExceptionObject);
      v13 = JsonObject::GetJsonDataAsString((__int64)v4, pExceptionObject, L"federation_active_auth_url");
      if ( v13[1].m128i_i64[1] > 7uLL )
        v13 = (__m128i *)v13->m128i_i64[0];
      if ( v13 )
      {
        v14 = -1;
        do
          ++v14;
        while ( v13->m128i_i16[v14] );
      }
      else
      {
        v14 = 0;
      }
      ATL::CSimpleStringT<unsigned short,0>::SetString(a1 + 64, v13, v14);
      std::wstring::~wstring((char **)pExceptionObject);
      if ( !*(_DWORD *)(*(_QWORD *)(a1 + 56) - 16LL) && !*(_DWORD *)(*(_QWORD *)(a1 + 64) - 16LL) )
      {
        ServiceException::ServiceException((__int64)pExceptionObject, -894894054, a2);
        throw (ServiceException *)pExceptionObject;
      }
      v15 = v20 - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)v20 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 8LL))(*(_QWORD *)v15);
    }
    else if ( wcscmp_0(v7, L"unknown") )
    {
      Exception::Exception((Exception *)pExceptionObject, -894894051);
      throw (Exception *)pExceptionObject;
    }
    v16 = JsonObject::GetJsonDataAsString((__int64)v4, v24, L"ver");
    if ( v16[1].m128i_i64[1] > 7uLL )
      v16 = (__m128i *)v16->m128i_i64[0];
    if ( v16 )
    {
      v17 = -1;
      do
        ++v17;
      while ( v16->m128i_i16[v17] );
    }
    else
    {
      v17 = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(a1 + 8, v16, v17);
    std::wstring::~wstring((char **)v24);
    v18 = String1[0] - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)String1[0] - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 8LL))(*(_QWORD *)v18);
    (**(void (__fastcall ***)(JsonObject *, __int64))v4)(v4, 1);
    std::deque<JsonValue *>::_Tidy(Block);
    v19 = Block[0];
    Block[0] = 0;
    operator delete(v19);
  }
}

```

## disassembly

```asm
0x14000d384  mov     [rsp-8+arg_10], rbx
0x14000d389  push    rbp
0x14000d38a  push    rsi
0x14000d38b  push    rdi
0x14000d38c  push    r12
0x14000d38e  push    r13
0x14000d390  push    r14
0x14000d392  push    r15
0x14000d394  lea     rbp, [rsp-27h]
0x14000d399  sub     rsp, 0E0h
0x14000d3a0  mov     rax, cs:__security_cookie
0x14000d3a7  xor     rax, rsp
0x14000d3aa  mov     [rbp+57h+var_40], rax
0x14000d3ae  mov     r14, rdx
0x14000d3b1  mov     rsi, rcx
0x14000d3b4  mov     rax, [rdx]
0x14000d3b7  xor     r12d, r12d
0x14000d3ba  cmp     [rax-10h], r12d
0x14000d3be  jz      loc_14000D6D8
0x14000d3c4  lea     rcx, [rsp+110h+Block]; this
0x14000d3c9  call    ??0JsonReader@@QEAA@XZ; JsonReader::JsonReader(void)
0x14000d3ce  nop
0x14000d3cf  mov     rdx, [r14]
0x14000d3d2  lea     rcx, [rbp+57h+var_80]
0x14000d3d6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14000d3db  nop
0x14000d3dc  lea     rdx, [rbp+57h+var_80]
0x14000d3e0  lea     rcx, [rsp+110h+Block]; this
0x14000d3e5  call    ?Parse@JsonReader@@QEAAPEAVJsonValue@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; JsonReader::Parse(std::wstring const &)
0x14000d3ea  mov     rdi, rax
0x14000d3ed  mov     [rsp+110h+var_E0], rax
0x14000d3f2  lea     rcx, [rbp+57h+var_80]
0x14000d3f6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000d3fb  test    rdi, rdi
0x14000d3fe  jz      loc_14000D721
0x14000d404  cmp     dword ptr [rdi+8], 1
0x14000d408  jnz     loc_14000D721
0x14000d40e  lea     r8, aAccountType; "account_type"
0x14000d415  lea     rdx, [rbp+57h+var_60]
0x14000d419  mov     rcx, rdi
0x14000d41c  call    ?GetJsonDataAsString@JsonObject@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; JsonObject::GetJsonDataAsString(ushort const *)
0x14000d421  nop
0x14000d422  cmp     qword ptr [rax+18h], 7
0x14000d427  jbe     short loc_14000D42C
0x14000d429  mov     rax, [rax]
0x14000d42c  mov     rdx, rax
0x14000d42f  lea     rcx, [rsp+110h+String1]
0x14000d434  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000d439  nop
0x14000d43a  lea     rcx, [rbp+57h+var_60]
0x14000d43e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000d443  lea     rcx, [rsp+110h+String1]
0x14000d448  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x14000d44d  mov     rdx, rax
0x14000d450  lea     rcx, [rsp+110h+String1]
0x14000d455  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000d45a  mov     rbx, [rsp+110h+String1]
0x14000d45f  cmp     [rbx-10h], r12d
0x14000d463  jz      loc_14000D6FF
0x14000d469  mov     eax, 2
0x14000d46e  mov     [rsi+2Ch], eax
0x14000d471  mov     [rsi+30h], eax
0x14000d474  lea     rdx, aManaged; "managed"
0x14000d47b  mov     rcx, rbx; String1
0x14000d47e  call    wcscmp_0
0x14000d483  nop
0x14000d484  or      r13, 0FFFFFFFFFFFFFFFFh
0x14000d488  test    eax, eax
0x14000d48a  jnz     short loc_14000D498
0x14000d48c  mov     dword ptr [rsi+2Ch], 1
0x14000d493  jmp     loc_14000D62D
0x14000d498  lea     rdx, aFederated; "federated"
0x14000d49f  mov     rcx, rbx; String1
0x14000d4a2  call    wcscmp_0
0x14000d4a7  nop
0x14000d4a8  test    eax, eax
0x14000d4aa  jnz     loc_14000D615
0x14000d4b0  mov     [rsi+2Ch], r12d
0x14000d4b4  lea     r8, aFederationProt; "federation_protocol"
0x14000d4bb  lea     rdx, [rbp+57h+var_80]
0x14000d4bf  mov     rcx, rdi
0x14000d4c2  call    ?GetJsonDataAsString@JsonObject@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; JsonObject::GetJsonDataAsString(ushort const *)
0x14000d4c7  nop
0x14000d4c8  cmp     qword ptr [rax+18h], 7
0x14000d4cd  jbe     short loc_14000D4D2
0x14000d4cf  mov     rax, [rax]
0x14000d4d2  mov     rdx, rax
0x14000d4d5  lea     rcx, [rsp+110h+var_F0]
0x14000d4da  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000d4df  nop
0x14000d4e0  lea     rcx, [rbp+57h+var_80]
0x14000d4e4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000d4e9  lea     rcx, [rsp+110h+var_F0]
0x14000d4ee  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x14000d4f3  mov     rdx, rax
0x14000d4f6  lea     rcx, [rsp+110h+var_F0]
0x14000d4fb  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000d500  nop
0x14000d501  lea     rdx, aWstrust; "wstrust"
0x14000d508  mov     rcx, [rsp+110h+var_F0]; String1
0x14000d50d  call    wcscmp_0
0x14000d512  nop
0x14000d513  test    eax, eax
0x14000d515  jnz     short loc_14000D51C
0x14000d517  mov     eax, r12d
0x14000d51a  jmp     short loc_14000D53B
0x14000d51c  lea     rdx, aSaml20; "saml20"
0x14000d523  mov     rcx, [rsp+110h+var_F0]; String1
0x14000d528  call    wcscmp_0
0x14000d52d  nop
0x14000d52e  test    eax, eax
0x14000d530  jnz     loc_14000D762
0x14000d536  mov     eax, 1
0x14000d53b  mov     [rsi+30h], eax
0x14000d53e  lea     r8, aFederationMeta; "federation_metadata_url"
0x14000d545  lea     rdx, [rbp+57h+pExceptionObject]
0x14000d549  mov     rcx, rdi
0x14000d54c  call    ?GetJsonDataAsString@JsonObject@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; JsonObject::GetJsonDataAsString(ushort const *)
0x14000d551  nop
0x14000d552  cmp     qword ptr [rax+18h], 7
0x14000d557  jbe     short loc_14000D55C
0x14000d559  mov     rax, [rax]
0x14000d55c  test    rax, rax
0x14000d55f  jnz     short loc_14000D566
0x14000d561  mov     r8d, r12d
0x14000d564  jmp     short loc_14000D573
0x14000d566  mov     r8, r13
0x14000d569  inc     r8
0x14000d56c  cmp     [rax+r8*2], r12w
0x14000d571  jnz     short loc_14000D569
0x14000d573  mov     rdx, rax
0x14000d576  lea     rcx, [rsi+38h]
0x14000d57a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000d57f  nop
0x14000d580  lea     rcx, [rbp+57h+pExceptionObject]
0x14000d584  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000d589  lea     r8, aFederationActi; "federation_active_auth_url"
0x14000d590  lea     rdx, [rbp+57h+pExceptionObject]
0x14000d594  mov     rcx, rdi
0x14000d597  call    ?GetJsonDataAsString@JsonObject@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; JsonObject::GetJsonDataAsString(ushort const *)
0x14000d59c  nop
0x14000d59d  cmp     qword ptr [rax+18h], 7
0x14000d5a2  jbe     short loc_14000D5A7
0x14000d5a4  mov     rax, [rax]
0x14000d5a7  test    rax, rax
0x14000d5aa  jnz     short loc_14000D5B1
0x14000d5ac  mov     r8d, r12d
0x14000d5af  jmp     short loc_14000D5BE
0x14000d5b1  mov     r8, r13
0x14000d5b4  inc     r8
0x14000d5b7  cmp     [rax+r8*2], r12w
0x14000d5bc  jnz     short loc_14000D5B4
0x14000d5be  mov     rdx, rax
0x14000d5c1  lea     rcx, [rsi+40h]
0x14000d5c5  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000d5ca  nop
0x14000d5cb  lea     rcx, [rbp+57h+pExceptionObject]
0x14000d5cf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000d5d4  mov     rax, [rsi+38h]
0x14000d5d8  cmp     [rax-10h], r12d
0x14000d5dc  jnz     short loc_14000D5EC
0x14000d5de  mov     rax, [rsi+40h]
0x14000d5e2  cmp     [rax-10h], r12d
0x14000d5e6  jz      loc_14000D740
0x14000d5ec  mov     rdx, [rsp+110h+var_F0]
0x14000d5f1  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000d5f5  mov     eax, r13d
0x14000d5f8  lock xadd [rdx+10h], eax
0x14000d5fd  add     eax, r13d
0x14000d600  test    eax, eax
0x14000d602  jg      short loc_14000D62D
0x14000d604  mov     rcx, [rdx]
0x14000d607  mov     rax, [rcx]
0x14000d60a  mov     rax, [rax+8]
0x14000d60e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d613  jmp     short loc_14000D62D
0x14000d615  lea     rdx, aUnknown; "unknown"
0x14000d61c  mov     rcx, rbx; String1
0x14000d61f  call    wcscmp_0
0x14000d624  nop
0x14000d625  test    eax, eax
0x14000d627  jnz     loc_14000D781
0x14000d62d  lea     r8, aVer; "ver"
0x14000d634  lea     rdx, [rbp+57h+var_80]
0x14000d638  mov     rcx, rdi
0x14000d63b  call    ?GetJsonDataAsString@JsonObject@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; JsonObject::GetJsonDataAsString(ushort const *)
0x14000d640  nop
0x14000d641  cmp     qword ptr [rax+18h], 7
0x14000d646  jbe     short loc_14000D64B
0x14000d648  mov     rax, [rax]
0x14000d64b  lea     rcx, [rsi+8]
0x14000d64f  test    rax, rax
0x14000d652  jnz     short loc_14000D659
0x14000d654  mov     r8d, r12d
0x14000d657  jmp     short loc_14000D666
0x14000d659  mov     r8, r13
0x14000d65c  inc     r8
0x14000d65f  cmp     [rax+r8*2], r12w
0x14000d664  jnz     short loc_14000D65C
0x14000d666  mov     rdx, rax
0x14000d669  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000d66e  nop
0x14000d66f  lea     rcx, [rbp+57h+var_80]
0x14000d673  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000d678  nop
0x14000d679  mov     rdx, [rsp+110h+String1]
0x14000d67e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000d682  mov     eax, r13d
0x14000d685  lock xadd [rdx+10h], eax
0x14000d68a  add     eax, r13d
0x14000d68d  test    eax, eax
0x14000d68f  jg      short loc_14000D6A1
0x14000d691  mov     rcx, [rdx]
0x14000d694  mov     rax, [rcx]
0x14000d697  mov     rax, [rax+8]
0x14000d69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d6a0  nop
0x14000d6a1  test    rdi, rdi
0x14000d6a4  jz      short loc_14000D6BA
0x14000d6a6  mov     rax, [rdi]
0x14000d6a9  mov     edx, 1
0x14000d6ae  mov     rcx, rdi
0x14000d6b1  mov     rax, [rax]
0x14000d6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d6b9  nop
0x14000d6ba  lea     rcx, [rsp+110h+Block]
0x14000d6bf  call    ?_Tidy@?$deque@PEAVJsonValue@@V?$allocator@PEAVJsonValue@@@std@@@std@@AEAAXXZ; std::deque<JsonValue *>::_Tidy(void)
0x14000d6c4  mov     rcx, [rsp+110h+Block]; Block
0x14000d6c9  mov     [rsp+110h+Block], r12
0x14000d6ce  mov     edx, 10h
0x14000d6d3  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14000d6d8  mov     rcx, [rbp+57h+var_40]
0x14000d6dc  xor     rcx, rsp; StackCookie
0x14000d6df  call    __security_check_cookie
0x14000d6e4  mov     rbx, [rsp+110h+arg_10]
0x14000d6ec  add     rsp, 0E0h
0x14000d6f3  pop     r15
0x14000d6f5  pop     r14
0x14000d6f7  pop     r13
0x14000d6f9  pop     r12
0x14000d6fb  pop     rdi
0x14000d6fc  pop     rsi
0x14000d6fd  pop     rbp
0x14000d6fe  retn
0x14000d6ff  mov     r8, r14
0x14000d702  mov     edx, 0CAA9001Eh
0x14000d707  lea     rcx, [rbp+57h+pExceptionObject]
0x14000d70b  call    ??0ServiceException@@QEAA@KAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; ServiceException::ServiceException(ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000d710  lea     rdx, _TI2?AVServiceException@@; pThrowInfo
0x14000d717  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000d71b  call    _CxxThrowException_0
0x14000d721  mov     edx, 0CAA9001Bh; unsigned int
0x14000d726  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14000d72a  call    ??0Exception@@QEAA@K@Z; Exception::Exception(ulong)
0x14000d72f  lea     rdx, _TI1?AVException@@; pThrowInfo
0x14000d736  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000d73a  call    _CxxThrowException_0
0x14000d740  mov     r8, r14
0x14000d743  mov     edx, 0CAA9001Ah
0x14000d748  lea     rcx, [rbp+57h+pExceptionObject]
0x14000d74c  call    ??0ServiceException@@QEAA@KAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; ServiceException::ServiceException(ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000d751  lea     rdx, _TI2?AVServiceException@@; pThrowInfo
0x14000d758  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000d75c  call    _CxxThrowException_0
0x14000d762  mov     edx, 0CAA9001Ch; unsigned int
0x14000d767  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14000d76b  call    ??0Exception@@QEAA@K@Z; Exception::Exception(ulong)
0x14000d770  lea     rdx, _TI1?AVException@@; pThrowInfo
0x14000d777  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000d77b  call    _CxxThrowException_0
0x14000d781  mov     edx, 0CAA9001Dh; unsigned int
0x14000d786  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14000d78a  call    ??0Exception@@QEAA@K@Z; Exception::Exception(ulong)
0x14000d78f  lea     rdx, _TI1?AVException@@; pThrowInfo
0x14000d796  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000d79a  call    _CxxThrowException_0
```
