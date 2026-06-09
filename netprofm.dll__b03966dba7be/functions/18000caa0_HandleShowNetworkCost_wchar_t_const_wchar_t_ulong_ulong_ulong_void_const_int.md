# HandleShowNetworkCost(wchar_t const *,wchar_t * *,ulong,ulong,ulong,void const *,int *)

- ea: `0x18000caa0`
- end: `0x18000cc37`
- name: `?HandleShowNetworkCost@@YAKPEB_WPEAPEA_WKKKPEBXPEAH@Z`
- size: `407`
- prototype: `unsigned int __fastcall(const wchar_t *, wchar_t **, unsigned int, unsigned int, unsigned int, const void *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800086b0`
- `0x18000caa0`
- `0x18000cc40`
- `0x18000ce70`
- `0x18000d014`
- `0x1800120d0`
- `0x18002a928`
- `0x18002b1b8`
- `0x18002c370`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000cc12`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000cc12`

## string_xrefs

- `0x18000cb2e`: `onecore\net\netprofiles\service\src\public\lib\netshhelperhandlers.cpp`
- `0x18000cb84`: `onecore\net\netprofiles\service\src\public\lib\netshhelperhandlers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall HandleShowNetworkCost(
        const wchar_t *a1,
        wchar_t **a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        const void *a6,
        int *a7)
{
  int v7; // eax
  enum NLM_CONNECTION_COST v8; // ebx
  int v9; // eax
  char v10; // al
  int v12; // [rsp+20h] [rbp-68h] BYREF
  enum NLM_CONNECTION_COST v13; // [rsp+24h] [rbp-64h] BYREF
  __int64 v14; // [rsp+28h] [rbp-60h] BYREF
  __int64 (__fastcall ***v15)(_QWORD, GUID *, _QWORD *); // [rsp+30h] [rbp-58h] BYREF
  GUID rguid; // [rsp+38h] [rbp-50h] BYREF
  __int128 v17; // [rsp+48h] [rbp-40h]
  __int128 v18; // [rsp+58h] [rbp-30h]
  __int64 v19; // [rsp+68h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *a7 = 0;
  SafeCoInit(&v12);
  v15 = 0;
  wil::CoCreateInstance<NetworkListManager,INetworkListManager,wil::err_exception_policy>((LPVOID *)&v15);
  v14 = 0;
  wil::com_ptr_t<INetworkListManager,wil::err_exception_policy>::query<INetworkCostManager>(&v15, &v14);
  v13 = NLM_CONNECTION_COST_UNKNOWN;
  v7 = (*(__int64 (__fastcall **)(__int64, enum NLM_CONNECTION_COST *, _QWORD))(*(_QWORD *)v14 + 24LL))(v14, &v13, 0);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\netshhelperhandlers.cpp",
      (const char *)(unsigned int)v7,
      v12);
  v8 = v13;
  rguid = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD))(*(_QWORD *)v14 + 32LL))(v14, &rguid, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\netshhelperhandlers.cpp",
      (const char *)(unsigned int)v9,
      v12);
  g_netshPrintMessageFromModule(g_moduleHandle, 6000u);
  g_netshPrintMessageFromModule(g_moduleHandle, 6002u);
  PrintConnectionCost(v8);
  g_netshPrintMessageFromModule(g_moduleHandle, 4001u);
  PrintDataPlanStatus(&rguid);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v15);
  v10 = v12;
  LOBYTE(v12) = 0;
  if ( v10 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18000caa0  push    rbx
0x18000caa2  sub     rsp, 80h
0x18000caa9  mov     rax, cs:__security_cookie
0x18000cab0  xor     rax, rsp
0x18000cab3  mov     [rsp+88h+var_18], rax
0x18000cab8  mov     rax, [rsp+88h+arg_30]
0x18000cac0  mov     dword ptr [rax], 0
0x18000cac6  lea     rcx, [rsp+88h+var_68]
0x18000cacb  call    ?SafeCoInit@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@wil@@XZ; SafeCoInit(void)
0x18000cad0  nop
0x18000cad1  mov     [rsp+88h+var_58], 0
0x18000cada  lea     rcx, [rsp+88h+var_58]
0x18000cadf  call    ??$CoCreateInstance@VNetworkListManager@@UINetworkListManager@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UINetworkListManager@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<NetworkListManager,INetworkListManager,wil::err_exception_policy>(ulong)
0x18000cae4  nop
0x18000cae5  mov     [rsp+88h+var_60], 0
0x18000caee  lea     rdx, [rsp+88h+var_60]
0x18000caf3  lea     rcx, [rsp+88h+var_58]
0x18000caf8  call    ??$query@UINetworkCostManager@@@?$com_ptr_t@UINetworkListManager@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UINetworkCostManager@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<INetworkListManager,wil::err_exception_policy>::query<INetworkCostManager>(void)
0x18000cafd  nop
0x18000cafe  mov     [rsp+88h+var_64], 0
0x18000cb06  mov     rcx, [rsp+88h+var_60]
0x18000cb0b  mov     rax, [rcx]
0x18000cb0e  xor     r8d, r8d
0x18000cb11  lea     rdx, [rsp+88h+var_64]
0x18000cb16  mov     rax, [rax+18h]
0x18000cb1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb1f  mov     rcx, [rsp+88h]; this
0x18000cb27  test    eax, eax
0x18000cb29  jns     short loc_18000CB3F
0x18000cb2b  mov     r9d, eax; char *
0x18000cb2e  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x18000cb35  mov     edx, 92h; void *
0x18000cb3a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cb3f  mov     ebx, [rsp+88h+var_64]
0x18000cb43  xorps   xmm0, xmm0
0x18000cb46  xor     eax, eax
0x18000cb48  movups  xmmword ptr [rsp+88h+rguid.Data1], xmm0
0x18000cb4d  movups  [rsp+88h+var_40], xmm0
0x18000cb52  movups  [rsp+88h+var_30], xmm0
0x18000cb57  mov     [rsp+88h+var_20], rax
0x18000cb5c  mov     rcx, [rsp+88h+var_60]
0x18000cb61  mov     rax, [rcx]
0x18000cb64  xor     r8d, r8d
0x18000cb67  lea     rdx, [rsp+88h+rguid]
0x18000cb6c  mov     rax, [rax+20h]
0x18000cb70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb75  mov     rcx, [rsp+88h]; this
0x18000cb7d  test    eax, eax
0x18000cb7f  jns     short loc_18000CB95
0x18000cb81  mov     r9d, eax; char *
0x18000cb84  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x18000cb8b  mov     edx, 96h; void *
0x18000cb90  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cb95  mov     edx, 1770h
0x18000cb9a  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x18000cba1  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x18000cba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbad  mov     edx, 1772h
0x18000cbb2  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x18000cbb9  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x18000cbc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbc5  mov     ecx, ebx; enum NLM_CONNECTION_COST
0x18000cbc7  call    ?PrintConnectionCost@@YAXW4NLM_CONNECTION_COST@@@Z; PrintConnectionCost(NLM_CONNECTION_COST)
0x18000cbcc  mov     edx, 0FA1h
0x18000cbd1  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x18000cbd8  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x18000cbdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbe4  lea     rcx, [rsp+88h+rguid]; rguid
0x18000cbe9  call    ?PrintDataPlanStatus@@YAXAEBUNLM_DATAPLAN_STATUS@@@Z; PrintDataPlanStatus(NLM_DATAPLAN_STATUS const &)
0x18000cbee  nop
0x18000cbef  lea     rcx, [rsp+88h+var_60]
0x18000cbf4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000cbf9  nop
0x18000cbfa  lea     rcx, [rsp+88h+var_58]
0x18000cbff  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000cc04  nop
0x18000cc05  mov     al, byte ptr [rsp+88h+var_68]
0x18000cc09  mov     byte ptr [rsp+88h+var_68], 0
0x18000cc0e  test    al, al
0x18000cc10  jz      short loc_18000CC18
0x18000cc12  call    cs:__imp_CoUninitialize
0x18000cc18  xor     eax, eax
0x18000cc1a  jmp     short loc_18000CC20
0x18000cc1c  mov     eax, [rsp+88h+var_64]
0x18000cc20  mov     rcx, [rsp+88h+var_18]
0x18000cc25  xor     rcx, rsp; StackCookie
0x18000cc28  call    __security_check_cookie
0x18000cc2d  add     rsp, 80h
0x18000cc34  pop     rbx
0x18000cc35  retn
```
