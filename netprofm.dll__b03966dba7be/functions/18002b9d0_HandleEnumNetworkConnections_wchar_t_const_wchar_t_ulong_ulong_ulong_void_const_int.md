# HandleEnumNetworkConnections(wchar_t const *,wchar_t * *,ulong,ulong,ulong,void const *,int *)

- ea: `0x18002b9d0`
- end: `0x18002bb35`
- name: `?HandleEnumNetworkConnections@@YAKPEB_WPEAPEA_WKKKPEBXPEAH@Z`
- size: `357`
- prototype: `unsigned int __fastcall(const wchar_t *, wchar_t **, unsigned int, unsigned int, unsigned int, const void *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800086b0`
- `0x18000c990`
- `0x18000d58c`
- `0x180011634`
- `0x1800120d0`
- `0x18002a928`
- `0x18002b1b8`
- `0x18002b9d0`
- `0x18002c370`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002bb13`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002bb13`

## string_xrefs

- `0x18002ba3d`: `onecore\net\netprofiles\service\src\public\lib\netshhelperhandlers.cpp`
- `0x18002ba91`: `onecore\net\netprofiles\service\src\public\lib\netshhelperhandlers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall HandleEnumNetworkConnections(
        const wchar_t *a1,
        wchar_t **a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        const void *a6,
        int *a7)
{
  int v7; // eax
  int v8; // ebx
  int v9; // eax
  char v10; // al
  int v12; // [rsp+20h] [rbp-48h]
  _BYTE v13[4]; // [rsp+30h] [rbp-38h] BYREF
  int v14; // [rsp+34h] [rbp-34h] BYREF
  __int64 (__fastcall ***v15)(_QWORD, GUID *, _QWORD *); // [rsp+38h] [rbp-30h] BYREF
  __int64 v16; // [rsp+40h] [rbp-28h] BYREF
  __int64 v17; // [rsp+48h] [rbp-20h] BYREF
  LPVOID v18; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a7 = 0;
  SafeCoInit(v13);
  v18 = 0;
  wil::CoCreateInstance<NetworkListManager,INetworkListManager,wil::err_exception_policy>(&v18);
  v17 = 0;
  v7 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v18 + 72LL))(v18, &v17);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\netshhelperhandlers.cpp",
      (const char *)(unsigned int)v7,
      v12);
  v8 = 0;
  while ( !v8 )
  {
    v14 = 0;
    v15 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *), int *))(*(_QWORD *)v17 + 64LL))(
           v17,
           1,
           &v15,
           &v14);
    v8 = v9;
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC2,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\netshhelperhandlers.cpp",
        (const char *)(unsigned int)v9,
        v12);
    if ( v15 )
    {
      v16 = 0;
      wil::com_ptr_t<INetworkConnection,wil::err_exception_policy>::query<INetworkConnectionCost>(&v15, &v16);
      PrintNetworkConnection(&v15);
      PrintNetworkConnectionCost(&v16);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v15);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v18);
  v10 = v13[0];
  v13[0] = 0;
  if ( v10 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18002b9d0  push    rbx
0x18002b9d2  sub     rsp, 60h
0x18002b9d6  mov     rax, cs:__security_cookie
0x18002b9dd  xor     rax, rsp
0x18002b9e0  mov     [rsp+68h+var_10], rax
0x18002b9e5  mov     rax, [rsp+68h+arg_30]
0x18002b9ed  mov     dword ptr [rax], 0
0x18002b9f3  lea     rcx, [rsp+68h+var_38]
0x18002b9f8  call    ?SafeCoInit@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@wil@@XZ; SafeCoInit(void)
0x18002b9fd  nop
0x18002b9fe  mov     [rsp+68h+var_18], 0
0x18002ba07  lea     rcx, [rsp+68h+var_18]
0x18002ba0c  call    ??$CoCreateInstance@VNetworkListManager@@UINetworkListManager@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UINetworkListManager@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<NetworkListManager,INetworkListManager,wil::err_exception_policy>(ulong)
0x18002ba11  nop
0x18002ba12  mov     [rsp+68h+var_20], 0
0x18002ba1b  mov     rcx, [rsp+68h+var_18]
0x18002ba20  mov     rax, [rcx]
0x18002ba23  lea     rdx, [rsp+68h+var_20]
0x18002ba28  mov     rax, [rax+48h]
0x18002ba2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba31  mov     rcx, [rsp+68h]; this
0x18002ba36  test    eax, eax
0x18002ba38  jns     short loc_18002BA4E
0x18002ba3a  mov     r9d, eax; char *
0x18002ba3d  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x18002ba44  mov     edx, 0BAh; void *
0x18002ba49  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ba4e  xor     ebx, ebx
0x18002ba50  test    ebx, ebx
0x18002ba52  jnz     loc_18002BAF0
0x18002ba58  mov     [rsp+68h+var_34], ebx
0x18002ba5c  mov     [rsp+68h+var_30], 0
0x18002ba65  mov     rcx, [rsp+68h+var_20]
0x18002ba6a  mov     rax, [rcx]
0x18002ba6d  lea     r9, [rsp+68h+var_34]
0x18002ba72  lea     r8, [rsp+68h+var_30]
0x18002ba77  lea     edx, [rbx+1]
0x18002ba7a  mov     rax, [rax+40h]
0x18002ba7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba83  mov     ebx, eax
0x18002ba85  mov     rcx, [rsp+68h]; this
0x18002ba8a  test    eax, eax
0x18002ba8c  jns     short loc_18002BAA2
0x18002ba8e  mov     r9d, eax; char *
0x18002ba91  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x18002ba98  mov     edx, 0C2h; void *
0x18002ba9d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002baa2  cmp     [rsp+68h+var_30], 0
0x18002baa8  jz      short loc_18002BAE1
0x18002baaa  mov     [rsp+68h+var_28], 0
0x18002bab3  lea     rdx, [rsp+68h+var_28]
0x18002bab8  lea     rcx, [rsp+68h+var_30]
0x18002babd  call    ??$query@UINetworkConnectionCost@@@?$com_ptr_t@UINetworkConnection@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UINetworkConnectionCost@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<INetworkConnection,wil::err_exception_policy>::query<INetworkConnectionCost>(void)
0x18002bac2  lea     rcx, [rsp+68h+var_30]
0x18002bac7  call    ?PrintNetworkConnection@@YAXAEBV?$com_ptr_t@UINetworkConnection@@Uerr_exception_policy@wil@@@wil@@@Z; PrintNetworkConnection(wil::com_ptr_t<INetworkConnection,wil::err_exception_policy> const &)
0x18002bacc  lea     rcx, [rsp+68h+var_28]
0x18002bad1  call    ?PrintNetworkConnectionCost@@YAXAEBV?$com_ptr_t@UINetworkConnectionCost@@Uerr_exception_policy@wil@@@wil@@@Z; PrintNetworkConnectionCost(wil::com_ptr_t<INetworkConnectionCost,wil::err_exception_policy> const &)
0x18002bad6  lea     rcx, [rsp+68h+var_28]
0x18002badb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002bae0  nop
0x18002bae1  lea     rcx, [rsp+68h+var_30]
0x18002bae6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002baeb  jmp     loc_18002BA50
0x18002baf0  lea     rcx, [rsp+68h+var_20]
0x18002baf5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002bafa  nop
0x18002bafb  lea     rcx, [rsp+68h+var_18]
0x18002bb00  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002bb05  nop
0x18002bb06  mov     al, [rsp+68h+var_38]
0x18002bb0a  mov     [rsp+68h+var_38], 0
0x18002bb0f  test    al, al
0x18002bb11  jz      short loc_18002BB19
0x18002bb13  call    cs:__imp_CoUninitialize
0x18002bb19  xor     eax, eax
0x18002bb1b  jmp     short loc_18002BB21
0x18002bb1d  mov     eax, [rsp+68h+var_34]
0x18002bb21  mov     rcx, [rsp+68h+var_10]
0x18002bb26  xor     rcx, rsp; StackCookie
0x18002bb29  call    __security_check_cookie
0x18002bb2e  add     rsp, 60h
0x18002bb32  pop     rbx
0x18002bb33  retn
```
