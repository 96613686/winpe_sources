# DiscoveryResponse::OnSuccess(std::unique_ptr<std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>,std::default_delete<std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x140024cc0`
- end: `0x140024e3f`
- name: `?OnSuccess@DiscoveryResponse@@UEAAXAEBV?$unique_ptr@V?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@U?$default_delete@V?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@@2@@std@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `383`
- prototype: `void __fastcall(__int64, __int64, _WORD **)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callees

- `0x140001b60`
- `0x1400028ac`
- `0x140003044`
- `0x1400032ec`
- `0x1400061dc`
- `0x14000df44`
- `0x14001cf60`
- `0x1400234fc`
- `0x1400239a4`
- `0x140024cc0`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall DiscoveryResponse::OnSuccess(__int64 a1, __int64 a2, _WORD **a3)
{
  __int64 v5; // rbx
  __m128i *JsonDataAsString; // rax
  __int64 v7; // rdi
  __int64 v8; // r8
  __m128i *v9; // rax
  void *v10; // rcx
  void *Block[7]; // [rsp+28h] [rbp-51h] BYREF
  __m128i v12[2]; // [rsp+60h] [rbp-19h] BYREF
  char *v13[4]; // [rsp+80h] [rbp+7h] BYREF

  if ( *((_DWORD *)*a3 - 4) )
  {
    JsonReader::JsonReader((JsonReader *)Block);
    std::wstring::wstring(v13, *a3);
    v5 = JsonReader::Parse((JsonReader *)Block);
    std::wstring::~wstring(v13);
    if ( v5 && *(_DWORD *)(v5 + 8) == 1 )
    {
      JsonDataAsString = JsonObject::GetJsonDataAsString(v5, v12, L"tenant_discovery_endpoint");
      if ( JsonDataAsString[1].m128i_i64[1] > 7uLL )
        JsonDataAsString = (__m128i *)JsonDataAsString->m128i_i64[0];
      v7 = -1;
      if ( JsonDataAsString )
      {
        v8 = -1;
        do
          ++v8;
        while ( JsonDataAsString->m128i_i16[v8] );
      }
      else
      {
        v8 = 0;
      }
      ATL::CSimpleStringT<unsigned short,0>::SetString(a1 + 8, JsonDataAsString, v8);
      std::wstring::~wstring((char **)v12);
      if ( !*(_DWORD *)(*(_QWORD *)(a1 + 8) - 16LL) )
      {
        v9 = JsonObject::GetJsonDataAsString(v5, v12, L"failure_reason");
        if ( v9[1].m128i_i64[1] > 7uLL )
          v9 = (__m128i *)v9->m128i_i64[0];
        if ( v9 )
        {
          do
            ++v7;
          while ( v9->m128i_i16[v7] );
        }
        else
        {
          LODWORD(v7) = 0;
        }
        ATL::CSimpleStringT<unsigned short,0>::SetString(a1 + 24, v9, (unsigned int)v7);
        std::wstring::~wstring((char **)v12);
      }
    }
    if ( v5 )
      (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
    std::deque<JsonValue *>::_Tidy(Block);
    v10 = Block[0];
    Block[0] = 0;
    operator delete(v10);
  }
}

```

## disassembly

```asm
0x140024cc0  mov     [rsp-8+arg_8], rbx
0x140024cc5  push    rbp
0x140024cc6  push    rsi
0x140024cc7  push    rdi
0x140024cc8  push    r14
0x140024cca  push    r15
0x140024ccc  lea     rbp, [rsp-37h]
0x140024cd1  sub     rsp, 0B0h
0x140024cd8  mov     rax, cs:__security_cookie
0x140024cdf  xor     rax, rsp
0x140024ce2  mov     [rbp+57h+var_30], rax
0x140024ce6  mov     rbx, r8
0x140024ce9  mov     rsi, rcx
0x140024cec  mov     rax, [r8]
0x140024cef  xor     r15d, r15d
0x140024cf2  cmp     [rax-10h], r15d
0x140024cf6  jz      loc_140024E1C
0x140024cfc  lea     rcx, [rbp+57h+Block]; this
0x140024d00  call    ??0JsonReader@@QEAA@XZ; JsonReader::JsonReader(void)
0x140024d05  nop
0x140024d06  mov     rdx, [rbx]
0x140024d09  lea     rcx, [rbp+57h+var_50]
0x140024d0d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140024d12  nop
0x140024d13  lea     rdx, [rbp+57h+var_50]
0x140024d17  lea     rcx, [rbp+57h+Block]; this
0x140024d1b  call    ?Parse@JsonReader@@QEAAPEAVJsonValue@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; JsonReader::Parse(std::wstring const &)
0x140024d20  mov     rbx, rax
0x140024d23  mov     [rbp+57h+var_B0], rax
0x140024d27  lea     rcx, [rbp+57h+var_50]
0x140024d2b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140024d30  test    rbx, rbx
0x140024d33  jz      loc_140024DE8
0x140024d39  cmp     dword ptr [rbx+8], 1
0x140024d3d  jnz     loc_140024DE8
0x140024d43  lea     r8, aTenantDiscover; "tenant_discovery_endpoint"
0x140024d4a  lea     rdx, [rbp+57h+var_70]
0x140024d4e  mov     rcx, rbx
0x140024d51  call    ?GetJsonDataAsString@JsonObject@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; JsonObject::GetJsonDataAsString(ushort const *)
0x140024d56  nop
0x140024d57  cmp     qword ptr [rax+18h], 7
0x140024d5c  jbe     short loc_140024D61
0x140024d5e  mov     rax, [rax]
0x140024d61  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140024d65  test    rax, rax
0x140024d68  jnz     short loc_140024D6F
0x140024d6a  mov     r8d, r15d
0x140024d6d  jmp     short loc_140024D7C
0x140024d6f  mov     r8, rdi
0x140024d72  inc     r8
0x140024d75  cmp     [rax+r8*2], r15w
0x140024d7a  jnz     short loc_140024D72
0x140024d7c  mov     rdx, rax
0x140024d7f  lea     rcx, [rsi+8]
0x140024d83  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140024d88  nop
0x140024d89  lea     rcx, [rbp+57h+var_70]
0x140024d8d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140024d92  mov     rax, [rsi+8]
0x140024d96  cmp     [rax-10h], r15d
0x140024d9a  jnz     short loc_140024DE8
0x140024d9c  lea     r8, aFailureReason; "failure_reason"
0x140024da3  lea     rdx, [rbp+57h+var_70]
0x140024da7  mov     rcx, rbx
0x140024daa  call    ?GetJsonDataAsString@JsonObject@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; JsonObject::GetJsonDataAsString(ushort const *)
0x140024daf  nop
0x140024db0  cmp     qword ptr [rax+18h], 7
0x140024db5  jbe     short loc_140024DBA
0x140024db7  mov     rax, [rax]
0x140024dba  lea     rcx, [rsi+18h]
0x140024dbe  test    rax, rax
0x140024dc1  jnz     short loc_140024DC8
0x140024dc3  mov     edi, r15d
0x140024dc6  jmp     short loc_140024DD2
0x140024dc8  inc     rdi
0x140024dcb  cmp     [rax+rdi*2], r15w
0x140024dd0  jnz     short loc_140024DC8
0x140024dd2  mov     r8d, edi
0x140024dd5  mov     rdx, rax
0x140024dd8  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140024ddd  nop
0x140024dde  lea     rcx, [rbp+57h+var_70]
0x140024de2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140024de7  nop
0x140024de8  test    rbx, rbx
0x140024deb  jz      short loc_140024E01
0x140024ded  mov     rax, [rbx]
0x140024df0  mov     edx, 1
0x140024df5  mov     rcx, rbx
0x140024df8  mov     rax, [rax]
0x140024dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024e00  nop
0x140024e01  lea     rcx, [rbp+57h+Block]
0x140024e05  call    ?_Tidy@?$deque@PEAVJsonValue@@V?$allocator@PEAVJsonValue@@@std@@@std@@AEAAXXZ; std::deque<JsonValue *>::_Tidy(void)
0x140024e0a  mov     rcx, [rbp+57h+Block]; Block
0x140024e0e  mov     [rbp+57h+Block], r15
0x140024e12  mov     edx, 10h
0x140024e17  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x140024e1c  mov     rcx, [rbp+57h+var_30]
0x140024e20  xor     rcx, rsp; StackCookie
0x140024e23  call    __security_check_cookie
0x140024e28  mov     rbx, [rsp+0D0h+arg_8]
0x140024e30  add     rsp, 0B0h
0x140024e37  pop     r15
0x140024e39  pop     r14
0x140024e3b  pop     rdi
0x140024e3c  pop     rsi
0x140024e3d  pop     rbp
0x140024e3e  retn
```
