# HandleShowNetworkConnectivity(wchar_t const *,wchar_t * *,ulong,ulong,ulong,void const *,int *)

- ea: `0x1800118c0`
- end: `0x180011ae2`
- name: `?HandleShowNetworkConnectivity@@YAKPEB_WPEAPEA_WKKKPEBXPEAH@Z`
- size: `546`
- prototype: `unsigned int __fastcall(const wchar_t *, wchar_t **, unsigned int, unsigned int, unsigned int, const void *, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800086b0`
- `0x1800118c0`
- `0x180011ae8`
- `0x1800120d0`
- `0x18002a928`
- `0x18002b1b8`
- `0x18002c370`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180011ac1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180011ac1`

## string_xrefs

- `0x18001192a`: `onecore\net\netprofiles\service\src\public\lib\netshhelperhandlers.cpp`
- `0x180011964`: `onecore\net\netprofiles\service\src\public\lib\netshhelperhandlers.cpp`
- `0x18001199e`: `onecore\net\netprofiles\service\src\public\lib\netshhelperhandlers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall HandleShowNetworkConnectivity(
        const wchar_t *a1,
        wchar_t **a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        const void *a6,
        int *a7)
{
  int v7; // eax
  int v8; // eax
  int v9; // eax
  char v10; // al
  int v12; // [rsp+20h] [rbp-28h] BYREF
  __int16 v13; // [rsp+24h] [rbp-24h] BYREF
  _WORD v14[2]; // [rsp+28h] [rbp-20h] BYREF
  enum NLM_CONNECTIVITY v15; // [rsp+2Ch] [rbp-1Ch] BYREF
  LPVOID v16; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a7 = 0;
  SafeCoInit(&v12);
  v16 = 0;
  wil::CoCreateInstance<NetworkListManager,INetworkListManager,wil::err_exception_policy>(&v16);
  v15 = NLM_CONNECTIVITY_DISCONNECTED;
  v7 = (*(__int64 (__fastcall **)(LPVOID, enum NLM_CONNECTIVITY *))(*(_QWORD *)v16 + 104LL))(v16, &v15);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\netshhelperhandlers.cpp",
      (const char *)(unsigned int)v7,
      v12);
  v13 = 0;
  v8 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)v16 + 96LL))(v16, &v13);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\netshhelperhandlers.cpp",
      (const char *)(unsigned int)v8,
      v12);
  v14[0] = 0;
  v9 = (*(__int64 (__fastcall **)(LPVOID, _WORD *))(*(_QWORD *)v16 + 88LL))(v16, v14);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\netshhelperhandlers.cpp",
      (const char *)(unsigned int)v9,
      v12);
  g_netshPrintMessageFromModule(g_moduleHandle, 5000u);
  g_netshPrintMessageFromModule(g_moduleHandle, 5001u);
  PrintNetworkConnectivity(v15);
  g_netshPrintMessageFromModule(g_moduleHandle, 4001u);
  g_netshPrintMessageFromModule(g_moduleHandle, 5002u);
  g_netshPrintMessageFromModule(g_moduleHandle, (v13 != -1) + 4002);
  g_netshPrintMessageFromModule(g_moduleHandle, 4001u);
  g_netshPrintMessageFromModule(g_moduleHandle, 5003u);
  g_netshPrintMessageFromModule(g_moduleHandle, (v14[0] != 0xFFFF) + 4002);
  g_netshPrintMessageFromModule(g_moduleHandle, 4001u);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v16);
  v10 = v12;
  LOBYTE(v12) = 0;
  if ( v10 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x1800118c0  sub     rsp, 48h
0x1800118c4  mov     rax, cs:__security_cookie
0x1800118cb  xor     rax, rsp
0x1800118ce  mov     [rsp+48h+var_10], rax
0x1800118d3  mov     rax, [rsp+48h+arg_30]
0x1800118db  mov     dword ptr [rax], 0
0x1800118e1  lea     rcx, [rsp+48h+var_28]
0x1800118e6  call    ?SafeCoInit@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@wil@@XZ; SafeCoInit(void)
0x1800118eb  nop
0x1800118ec  mov     [rsp+48h+var_18], 0
0x1800118f5  lea     rcx, [rsp+48h+var_18]
0x1800118fa  call    ??$CoCreateInstance@VNetworkListManager@@UINetworkListManager@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UINetworkListManager@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<NetworkListManager,INetworkListManager,wil::err_exception_policy>(ulong)
0x1800118ff  nop
0x180011900  mov     [rsp+48h+var_1C], 0
0x180011908  mov     rcx, [rsp+48h+var_18]
0x18001190d  mov     rax, [rcx]
0x180011910  lea     rdx, [rsp+48h+var_1C]
0x180011915  mov     rax, [rax+68h]
0x180011919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001191e  mov     rcx, [rsp+48h]; this
0x180011923  test    eax, eax
0x180011925  jns     short loc_18001193B
0x180011927  mov     r9d, eax; char *
0x18001192a  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x180011931  mov     edx, 60h ; '`'; void *
0x180011936  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001193b  xor     eax, eax
0x18001193d  mov     [rsp+48h+var_24], ax
0x180011942  mov     rcx, [rsp+48h+var_18]
0x180011947  mov     rax, [rcx]
0x18001194a  lea     rdx, [rsp+48h+var_24]
0x18001194f  mov     rax, [rax+60h]
0x180011953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011958  mov     rcx, [rsp+48h]; this
0x18001195d  test    eax, eax
0x18001195f  jns     short loc_180011975
0x180011961  mov     r9d, eax; char *
0x180011964  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x18001196b  mov     edx, 63h ; 'c'; void *
0x180011970  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011975  xor     eax, eax
0x180011977  mov     [rsp+48h+var_20], ax
0x18001197c  mov     rcx, [rsp+48h+var_18]
0x180011981  mov     rax, [rcx]
0x180011984  lea     rdx, [rsp+48h+var_20]
0x180011989  mov     rax, [rax+58h]
0x18001198d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011992  mov     rcx, [rsp+48h]; this
0x180011997  test    eax, eax
0x180011999  jns     short loc_1800119AF
0x18001199b  mov     r9d, eax; char *
0x18001199e  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x1800119a5  mov     edx, 66h ; 'f'; void *
0x1800119aa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800119af  mov     edx, 1388h
0x1800119b4  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x1800119bb  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x1800119c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119c7  mov     edx, 1389h
0x1800119cc  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x1800119d3  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x1800119da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119df  mov     ecx, [rsp+48h+var_1C]; enum NLM_CONNECTIVITY
0x1800119e3  call    ?PrintNetworkConnectivity@@YAXW4NLM_CONNECTIVITY@@@Z; PrintNetworkConnectivity(NLM_CONNECTIVITY)
0x1800119e8  mov     edx, 0FA1h
0x1800119ed  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x1800119f4  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x1800119fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a00  mov     edx, 138Ah
0x180011a05  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x180011a0c  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x180011a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a18  xor     edx, edx
0x180011a1a  cmp     [rsp+48h+var_24], 0FFFFh
0x180011a20  setnz   dl
0x180011a23  add     edx, 0FA2h
0x180011a29  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x180011a30  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x180011a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a3c  mov     edx, 0FA1h
0x180011a41  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x180011a48  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x180011a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a54  mov     edx, 138Bh
0x180011a59  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x180011a60  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x180011a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a6c  xor     edx, edx
0x180011a6e  cmp     [rsp+48h+var_20], 0FFFFh
0x180011a74  setnz   dl
0x180011a77  add     edx, 0FA2h
0x180011a7d  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x180011a84  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x180011a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a90  mov     edx, 0FA1h
0x180011a95  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_moduleHandle
0x180011a9c  mov     rax, cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x180011aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011aa8  nop
0x180011aa9  lea     rcx, [rsp+48h+var_18]
0x180011aae  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180011ab3  nop
0x180011ab4  mov     al, byte ptr [rsp+48h+var_28]
0x180011ab8  mov     byte ptr [rsp+48h+var_28], 0
0x180011abd  test    al, al
0x180011abf  jz      short loc_180011AC7
0x180011ac1  call    cs:__imp_CoUninitialize
0x180011ac7  xor     eax, eax
0x180011ac9  jmp     short loc_180011ACF
0x180011acb  mov     eax, [rsp+48h+var_1C]
0x180011acf  mov     rcx, [rsp+48h+var_10]
0x180011ad4  xor     rcx, rsp; StackCookie
0x180011ad7  call    __security_check_cookie
0x180011adc  add     rsp, 48h
0x180011ae0  retn
```
