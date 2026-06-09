# PublicNetworkListManager::PublicNetworkListManager(void)

- ea: `0x180015190`
- end: `0x180015443`
- name: `??0PublicNetworkListManager@@QEAA@XZ`
- size: `691`
- prototype: `PublicNetworkListManager *__fastcall(PublicNetworkListManager *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180014df8`
- `0x180014f9c`

## callees

- `0x180007220`
- `0x180009634`
- `0x18000a810`
- `0x180014cfc`
- `0x180015190`
- `0x18001cb98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800153b7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800153b7`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180015405`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180015405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015413`

## pseudocode

```c
PublicNetworkListManager *__fastcall PublicNetworkListManager::PublicNetworkListManager(PublicNetworkListManager *this)
{
  size_t size_of; // rax
  _QWORD *v3; // rax
  size_t v4; // rax
  _QWORD *v5; // rax
  void *v6; // rdx
  HANDLE Event; // rsi
  unsigned int v8; // r8d
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *((_DWORD *)this + 36) = 0;
  *(_OWORD *)((char *)this + 152) = 0;
  *(_OWORD *)((char *)this + 168) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_BYTE *)this + 192) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 1) = &ProxyNetworkEventsSink<PublicNetworkListManager>::`vftable';
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 4) = &ProxyNetworkConnectionEventsSink<PublicNetworkListManager>::`vftable';
  *((_DWORD *)this + 18) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 7) = &ProxyNetworkConnectionCostEventsSink<PublicNetworkListManager>::`vftable';
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 10) = &ProxyNetworkListManagerEventsSink<PublicNetworkListManager>::`vftable';
  *((_DWORD *)this + 30) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 13) = &ProxyNetworkCostManagerEventsSink<PublicNetworkListManager>::`vftable';
  *((_QWORD *)this + 25) = 0;
  *((_BYTE *)this + 208) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *(_OWORD *)((char *)this + 232) = 0;
  *(_OWORD *)((char *)this + 248) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_DWORD *)this + 68) = -1;
  *((_BYTE *)this + 276) = 0;
  *(_OWORD *)((char *)this + 280) = 0;
  *(_OWORD *)((char *)this + 296) = 0;
  *((_QWORD *)this + 39) = 0;
  std::map<unsigned long,CLIENT_CALLBACK_INTERFACE>::map<unsigned long,CLIENT_CALLBACK_INTERFACE>((char *)this + 320);
  *((_OWORD *)this + 21) = 0;
  *((_OWORD *)this + 22) = 0;
  *((_QWORD *)this + 46) = 0;
  std::map<unsigned long,CLIENT_CALLBACK_INTERFACE>::map<unsigned long,CLIENT_CALLBACK_INTERFACE>((char *)this + 376);
  *(_OWORD *)((char *)this + 392) = 0;
  *(_OWORD *)((char *)this + 408) = 0;
  *((_QWORD *)this + 53) = 0;
  std::map<unsigned long,CLIENT_CALLBACK_INTERFACE>::map<unsigned long,CLIENT_CALLBACK_INTERFACE>((char *)this + 432);
  *((_OWORD *)this + 28) = 0;
  *((_OWORD *)this + 29) = 0;
  *((_QWORD *)this + 60) = 0;
  std::map<unsigned long,CLIENT_CALLBACK_INTERFACE>::map<unsigned long,CLIENT_CALLBACK_INTERFACE>((char *)this + 488);
  *(_OWORD *)((char *)this + 504) = 0;
  *(_OWORD *)((char *)this + 520) = 0;
  *((_QWORD *)this + 67) = 0;
  std::map<unsigned long,CLIENT_CALLBACK_INTERFACE>::map<unsigned long,CLIENT_CALLBACK_INTERFACE>((char *)this + 544);
  *((_OWORD *)this + 35) = 0;
  *((_OWORD *)this + 36) = 0;
  *((_QWORD *)this + 74) = 0;
  *((_QWORD *)this + 75) = 0;
  *((_QWORD *)this + 76) = 0;
  size_of = std::_Get_size_of_n<24>(1);
  v3 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  *v3 = v3;
  v3[1] = v3;
  *((_QWORD *)this + 75) = v3;
  *(_OWORD *)((char *)this + 616) = 0;
  *(_OWORD *)((char *)this + 632) = 0;
  *((_QWORD *)this + 81) = 0;
  *((_QWORD *)this + 82) = 0;
  *(_OWORD *)((char *)this + 664) = 0;
  *(_OWORD *)((char *)this + 680) = 0;
  *((_QWORD *)this + 87) = 0;
  *((_QWORD *)this + 88) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 712), 0, 0);
  *((_QWORD *)this + 94) = 0;
  *((_QWORD *)this + 95) = 0;
  v4 = std::_Get_size_of_n<24>(1);
  v5 = std::_Allocate<16,std::_Default_allocate_traits>(v4);
  *v5 = v5;
  v5[1] = v5;
  *((_QWORD *)this + 94) = v5;
  *((_QWORD *)this + 96) = 0;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v6, v8, v9);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    (char *)this + 768,
    Event);
  *((_QWORD *)this + 97) = 0;
  return this;
}

```

## disassembly

```asm
0x180015190  push    rbx
0x180015192  push    rbp
0x180015193  push    rsi
0x180015194  push    rdi
0x180015195  sub     rsp, 38h
0x180015199  mov     rbx, rcx
0x18001519c  mov     [rsp+58h+var_38], rcx
0x1800151a1  xor     ebp, ebp
0x1800151a3  mov     [rcx+90h], ebp
0x1800151a9  xorps   xmm0, xmm0
0x1800151ac  xor     eax, eax
0x1800151ae  movups  xmmword ptr [rcx+98h], xmm0
0x1800151b5  movups  xmmword ptr [rcx+0A8h], xmm0
0x1800151bc  mov     [rcx+0B8h], rax
0x1800151c3  mov     [rcx+0C0h], bpl
0x1800151ca  mov     [rcx+18h], ebp
0x1800151cd  mov     [rcx+10h], rbp
0x1800151d1  lea     rax, ??_7?$ProxyNetworkEventsSink@VPublicNetworkListManager@@@@6B@; const ProxyNetworkEventsSink<PublicNetworkListManager>::`vftable'
0x1800151d8  mov     [rcx+8], rax
0x1800151dc  mov     [rcx+30h], ebp
0x1800151df  mov     [rcx+28h], rbp
0x1800151e3  lea     rax, ??_7?$ProxyNetworkConnectionEventsSink@VPublicNetworkListManager@@@@6B@; const ProxyNetworkConnectionEventsSink<PublicNetworkListManager>::`vftable'
0x1800151ea  mov     [rcx+20h], rax
0x1800151ee  mov     [rcx+48h], ebp
0x1800151f1  mov     [rcx+40h], rbp
0x1800151f5  lea     rax, ??_7?$ProxyNetworkConnectionCostEventsSink@VPublicNetworkListManager@@@@6B@; const ProxyNetworkConnectionCostEventsSink<PublicNetworkListManager>::`vftable'
0x1800151fc  mov     [rcx+38h], rax
0x180015200  mov     [rcx+60h], ebp
0x180015203  mov     [rcx+58h], rbp
0x180015207  lea     rax, ??_7?$ProxyNetworkListManagerEventsSink@VPublicNetworkListManager@@@@6B@; const ProxyNetworkListManagerEventsSink<PublicNetworkListManager>::`vftable'
0x18001520e  mov     [rcx+50h], rax
0x180015212  mov     [rcx+78h], ebp
0x180015215  mov     [rcx+70h], rbp
0x180015219  lea     rax, ??_7?$ProxyNetworkCostManagerEventsSink@VPublicNetworkListManager@@@@6B@; const ProxyNetworkCostManagerEventsSink<PublicNetworkListManager>::`vftable'
0x180015220  mov     [rcx+68h], rax
0x180015224  mov     [rcx+0C8h], rbp
0x18001522b  mov     [rcx+0D0h], bpl
0x180015232  mov     [rcx+0D8h], rbp
0x180015239  mov     [rcx+0E0h], rbp
0x180015240  xor     eax, eax
0x180015242  movups  xmmword ptr [rcx+0E8h], xmm0
0x180015249  movups  xmmword ptr [rcx+0F8h], xmm0
0x180015250  mov     [rcx+108h], rax
0x180015257  mov     dword ptr [rcx+110h], 0FFFFFFFFh
0x180015261  mov     [rcx+114h], bpl
0x180015268  movups  xmmword ptr [rcx+118h], xmm0
0x18001526f  movups  xmmword ptr [rcx+128h], xmm0
0x180015276  mov     [rcx+138h], rax
0x18001527d  add     rcx, 140h
0x180015284  call    ??0?$map@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@@std@@QEAA@XZ; std::map<ulong,CLIENT_CALLBACK_INTERFACE>::map<ulong,CLIENT_CALLBACK_INTERFACE>(void)
0x180015289  nop
0x18001528a  xorps   xmm0, xmm0
0x18001528d  xor     eax, eax
0x18001528f  movups  xmmword ptr [rbx+150h], xmm0
0x180015296  movups  xmmword ptr [rbx+160h], xmm0
0x18001529d  mov     [rbx+170h], rax
0x1800152a4  lea     rcx, [rbx+178h]
0x1800152ab  call    ??0?$map@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@@std@@QEAA@XZ; std::map<ulong,CLIENT_CALLBACK_INTERFACE>::map<ulong,CLIENT_CALLBACK_INTERFACE>(void)
0x1800152b0  nop
0x1800152b1  xorps   xmm0, xmm0
0x1800152b4  xor     eax, eax
0x1800152b6  movups  xmmword ptr [rbx+188h], xmm0
0x1800152bd  movups  xmmword ptr [rbx+198h], xmm0
0x1800152c4  mov     [rbx+1A8h], rax
0x1800152cb  lea     rcx, [rbx+1B0h]
0x1800152d2  call    ??0?$map@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@@std@@QEAA@XZ; std::map<ulong,CLIENT_CALLBACK_INTERFACE>::map<ulong,CLIENT_CALLBACK_INTERFACE>(void)
0x1800152d7  nop
0x1800152d8  xorps   xmm0, xmm0
0x1800152db  xor     eax, eax
0x1800152dd  movups  xmmword ptr [rbx+1C0h], xmm0
0x1800152e4  movups  xmmword ptr [rbx+1D0h], xmm0
0x1800152eb  mov     [rbx+1E0h], rax
0x1800152f2  lea     rcx, [rbx+1E8h]
0x1800152f9  call    ??0?$map@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@@std@@QEAA@XZ; std::map<ulong,CLIENT_CALLBACK_INTERFACE>::map<ulong,CLIENT_CALLBACK_INTERFACE>(void)
0x1800152fe  nop
0x1800152ff  xorps   xmm0, xmm0
0x180015302  xor     eax, eax
0x180015304  movups  xmmword ptr [rbx+1F8h], xmm0
0x18001530b  movups  xmmword ptr [rbx+208h], xmm0
0x180015312  mov     [rbx+218h], rax
0x180015319  lea     rcx, [rbx+220h]
0x180015320  call    ??0?$map@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@@std@@QEAA@XZ; std::map<ulong,CLIENT_CALLBACK_INTERFACE>::map<ulong,CLIENT_CALLBACK_INTERFACE>(void)
0x180015325  nop
0x180015326  xorps   xmm0, xmm0
0x180015329  xor     eax, eax
0x18001532b  movups  xmmword ptr [rbx+230h], xmm0
0x180015332  movups  xmmword ptr [rbx+240h], xmm0
0x180015339  mov     [rbx+250h], rax
0x180015340  mov     [rbx+258h], rbp
0x180015347  mov     [rbx+260h], rbp
0x18001534e  lea     esi, [rbp+1]
0x180015351  mov     ecx, esi
0x180015353  call    ??$_Get_size_of_n@$0BI@@std@@YA_K_K@Z; std::_Get_size_of_n<24>(unsigned __int64)
0x180015358  mov     rcx, rax
0x18001535b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180015360  mov     [rax], rax
0x180015363  mov     [rax+8], rax
0x180015367  mov     [rbx+258h], rax
0x18001536e  xorps   xmm0, xmm0
0x180015371  xor     eax, eax
0x180015373  movups  xmmword ptr [rbx+268h], xmm0
0x18001537a  movups  xmmword ptr [rbx+278h], xmm0
0x180015381  mov     [rbx+288h], rax
0x180015388  mov     [rbx+290h], rbp
0x18001538f  movups  xmmword ptr [rbx+298h], xmm0
0x180015396  movups  xmmword ptr [rbx+2A8h], xmm0
0x18001539d  mov     [rbx+2B8h], rax
0x1800153a4  mov     [rbx+2C0h], rbp
0x1800153ab  lea     rcx, [rbx+2C8h]; lpCriticalSection
0x1800153b2  xor     r8d, r8d; Flags
0x1800153b5  xor     edx, edx; dwSpinCount
0x1800153b7  call    cs:__imp_InitializeCriticalSectionEx
0x1800153bd  nop
0x1800153be  mov     [rbx+2F0h], rbp
0x1800153c5  mov     [rbx+2F8h], rbp
0x1800153cc  mov     ecx, esi
0x1800153ce  call    ??$_Get_size_of_n@$0BI@@std@@YA_K_K@Z; std::_Get_size_of_n<24>(unsigned __int64)
0x1800153d3  mov     rcx, rax
0x1800153d6  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800153db  mov     [rax], rax
0x1800153de  mov     [rax+8], rax
0x1800153e2  mov     [rbx+2F0h], rax
0x1800153e9  lea     rdi, [rbx+300h]
0x1800153f0  mov     [rsp+58h+var_30], rdi
0x1800153f5  mov     [rdi], rbp
0x1800153f8  mov     r9d, 1F0003h; dwDesiredAccess
0x1800153fe  mov     r8d, esi; dwFlags
0x180015401  xor     edx, edx; lpName
0x180015403  xor     ecx, ecx; lpEventAttributes
0x180015405  call    cs:__imp_CreateEventExW
0x18001540b  mov     rsi, rax
0x18001540e  test    rax, rax
0x180015411  jz      short loc_180015438
0x180015413  call    cs:__imp_GetLastError
0x180015419  mov     rdx, rsi
0x18001541c  mov     rcx, rdi
0x18001541f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180015424  nop
0x180015425  mov     [rbx+308h], rbp
0x18001542c  mov     rax, rbx
0x18001542f  add     rsp, 38h
0x180015433  pop     rdi
0x180015434  pop     rsi
0x180015435  pop     rbp
0x180015436  pop     rbx
0x180015437  retn
0x180015438  mov     rcx, [rsp+58h]; this
0x18001543d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
