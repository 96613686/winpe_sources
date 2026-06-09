# PrintNetworkConnectionCost(wil::com_ptr_t<INetworkConnectionCost,wil::err_exception_policy> const &)

- ea: `0x18000c990`
- end: `0x18000ca92`
- name: `?PrintNetworkConnectionCost@@YAXAEBV?$com_ptr_t@UINetworkConnectionCost@@Uerr_exception_policy@wil@@@wil@@@Z`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002b9d0`

## callees

- `0x18000c990`
- `0x18000cc40`
- `0x18000ce70`
- `0x1800120d0`
- `0x18002a928`
- `0x180043010`

## string_xrefs

- `0x18000c9d4`: `onecore\net\netprofiles\service\src\public\lib\netshhelperhandlers.cpp`
- `0x18000ca23`: `onecore\net\netprofiles\service\src\public\lib\netshhelperhandlers.cpp`

## pseudocode

```c
void __fastcall PrintNetworkConnectionCost(_QWORD *a1)
{
  int v2; // eax
  enum NLM_CONNECTION_COST v3; // edi
  int v4; // eax
  NLM_CONNECTION_COST v5; // [rsp+20h] [rbp-58h] BYREF
  GUID rguid; // [rsp+28h] [rbp-50h] BYREF
  __int128 v7; // [rsp+38h] [rbp-40h]
  __int128 v8; // [rsp+48h] [rbp-30h]
  __int64 v9; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v5 = NLM_CONNECTION_COST_UNKNOWN;
  v2 = (*(__int64 (__fastcall **)(_QWORD, NLM_CONNECTION_COST *))(*(_QWORD *)*a1 + 24LL))(*a1, &v5);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A7,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\netshhelperhandlers.cpp",
      (const char *)(unsigned int)v2,
      v5);
  v3 = v5;
  rguid = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, GUID *))(*(_QWORD *)*a1 + 32LL))(*a1, &rguid);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AB,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\netshhelperhandlers.cpp",
      (const char *)(unsigned int)v4,
      v5);
  g_netshPrintMessageFromModule(g_moduleHandle, 6002u);
  PrintConnectionCost(v3);
  g_netshPrintMessageFromModule(g_moduleHandle, 4001u);
  PrintDataPlanStatus(&rguid);
}

```

## disassembly

```asm
0x18000c990  mov     [rsp+arg_8], rbx
0x18000c995  push    rdi
0x18000c996  sub     rsp, 70h
0x18000c99a  mov     rax, cs:__security_cookie
0x18000c9a1  xor     rax, rsp
0x18000c9a4  mov     [rsp+78h+var_18], rax
0x18000c9a9  mov     rbx, rcx
0x18000c9ac  mov     [rsp+78h+var_58], 0; int
0x18000c9b4  mov     rcx, [rcx]
0x18000c9b7  mov     rax, [rcx]
0x18000c9ba  lea     rdx, [rsp+78h+var_58]
0x18000c9bf  mov     rax, [rax+18h]
0x18000c9c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9c8  test    eax, eax
0x18000c9ca  jns     short loc_18000C9E6
0x18000c9cc  mov     rcx, [rsp+78h]; this
0x18000c9d1  mov     r9d, eax; char *
0x18000c9d4  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x18000c9db  mov     edx, 1A7h; void *
0x18000c9e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000c9e6  mov     edi, [rsp+78h+var_58]
0x18000c9ea  xorps   xmm0, xmm0
0x18000c9ed  xor     eax, eax
0x18000c9ef  movups  xmmword ptr [rsp+78h+rguid.Data1], xmm0
0x18000c9f4  movups  [rsp+78h+var_40], xmm0
0x18000c9f9  movups  [rsp+78h+var_30], xmm0
0x18000c9fe  mov     [rsp+78h+var_20], rax
0x18000ca03  mov     rcx, [rbx]
0x18000ca06  mov     rax, [rcx]
0x18000ca09  lea     rdx, [rsp+78h+rguid]
0x18000ca0e  mov     rax, [rax+20h]
0x18000ca12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca17  test    eax, eax
0x18000ca19  jns     short loc_18000CA35
0x18000ca1b  mov     rcx, [rsp+78h]; this
0x18000ca20  mov     r9d, eax; char *
0x18000ca23  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x18000ca2a  mov     edx, 1ABh; void *
0x18000ca2f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000ca35  mov     edx, 1772h
0x18000ca3a  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x18000ca41  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x18000ca48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca4d  mov     ecx, edi; enum NLM_CONNECTION_COST
0x18000ca4f  call    ?PrintConnectionCost@@YAXW4NLM_CONNECTION_COST@@@Z; PrintConnectionCost(NLM_CONNECTION_COST)
0x18000ca54  mov     edx, 0FA1h
0x18000ca59  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x18000ca60  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x18000ca67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca6c  lea     rcx, [rsp+78h+rguid]; rguid
0x18000ca71  call    ?PrintDataPlanStatus@@YAXAEBUNLM_DATAPLAN_STATUS@@@Z; PrintDataPlanStatus(NLM_DATAPLAN_STATUS const &)
0x18000ca76  nop
0x18000ca77  mov     rcx, [rsp+78h+var_18]
0x18000ca7c  xor     rcx, rsp; StackCookie
0x18000ca7f  call    __security_check_cookie
0x18000ca84  mov     rbx, [rsp+78h+arg_8]
0x18000ca8c  add     rsp, 70h
0x18000ca90  pop     rdi
0x18000ca91  retn
```
