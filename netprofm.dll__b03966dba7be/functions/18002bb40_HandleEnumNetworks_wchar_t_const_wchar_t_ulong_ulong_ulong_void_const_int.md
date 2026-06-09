# HandleEnumNetworks(wchar_t const *,wchar_t * *,ulong,ulong,ulong,void const *,int *)

- ea: `0x18002bb40`
- end: `0x18002bc77`
- name: `?HandleEnumNetworks@@YAKPEB_WPEAPEA_WKKKPEBXPEAH@Z`
- size: `311`
- prototype: `unsigned int __fastcall(const wchar_t *, wchar_t **, unsigned int, unsigned int, unsigned int, const void *, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800086b0`
- `0x18000e33c`
- `0x1800120d0`
- `0x18002a928`
- `0x18002b1b8`
- `0x18002bb40`
- `0x18002c370`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002bc55`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002bc55`

## string_xrefs

- `0x18002bbb2`: `onecore\net\netprofiles\service\src\public\lib\netshhelperhandlers.cpp`
- `0x18002bc02`: `onecore\net\netprofiles\service\src\public\lib\netshhelperhandlers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall HandleEnumNetworks(
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
  __int64 *v15; // [rsp+38h] [rbp-30h] BYREF
  __int64 v16; // [rsp+40h] [rbp-28h] BYREF
  LPVOID v17; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a7 = 0;
  SafeCoInit(v13);
  v17 = 0;
  wil::CoCreateInstance<NetworkListManager,INetworkListManager,wil::err_exception_policy>(&v17);
  v16 = 0;
  v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v17 + 56LL))(v17, 1, &v16);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE4,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\netshhelperhandlers.cpp",
      (const char *)(unsigned int)v7,
      v12);
  v8 = 0;
  while ( !v8 )
  {
    v14 = 0;
    v15 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 **, int *))(*(_QWORD *)v16 + 64LL))(v16, 1, &v15, &v14);
    v8 = v9;
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xEC,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\netshhelperhandlers.cpp",
        (const char *)(unsigned int)v9,
        v12);
    if ( v15 )
      PrintNetworkInstance(&v15);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v15);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
  v10 = v13[0];
  v13[0] = 0;
  if ( v10 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18002bb40  push    rbx
0x18002bb42  sub     rsp, 60h
0x18002bb46  mov     rax, cs:__security_cookie
0x18002bb4d  xor     rax, rsp
0x18002bb50  mov     [rsp+68h+var_18], rax
0x18002bb55  mov     rax, [rsp+68h+arg_30]
0x18002bb5d  mov     dword ptr [rax], 0
0x18002bb63  lea     rcx, [rsp+68h+var_38]
0x18002bb68  call    ?SafeCoInit@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@wil@@XZ; SafeCoInit(void)
0x18002bb6d  nop
0x18002bb6e  mov     [rsp+68h+var_20], 0
0x18002bb77  lea     rcx, [rsp+68h+var_20]
0x18002bb7c  call    ??$CoCreateInstance@VNetworkListManager@@UINetworkListManager@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UINetworkListManager@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<NetworkListManager,INetworkListManager,wil::err_exception_policy>(ulong)
0x18002bb81  nop
0x18002bb82  mov     [rsp+68h+var_28], 0
0x18002bb8b  mov     rcx, [rsp+68h+var_20]
0x18002bb90  mov     rax, [rcx]
0x18002bb93  lea     r8, [rsp+68h+var_28]
0x18002bb98  mov     edx, 1
0x18002bb9d  mov     rax, [rax+38h]
0x18002bba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bba6  mov     rcx, [rsp+68h]; this
0x18002bbab  test    eax, eax
0x18002bbad  jns     short loc_18002BBC3
0x18002bbaf  mov     r9d, eax; char *
0x18002bbb2  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x18002bbb9  mov     edx, 0E4h; void *
0x18002bbbe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002bbc3  xor     ebx, ebx
0x18002bbc5  test    ebx, ebx
0x18002bbc7  jnz     short loc_18002BC32
0x18002bbc9  mov     [rsp+68h+var_34], ebx
0x18002bbcd  mov     [rsp+68h+var_30], 0
0x18002bbd6  mov     rcx, [rsp+68h+var_28]
0x18002bbdb  mov     rax, [rcx]
0x18002bbde  lea     r9, [rsp+68h+var_34]
0x18002bbe3  lea     r8, [rsp+68h+var_30]
0x18002bbe8  lea     edx, [rbx+1]
0x18002bbeb  mov     rax, [rax+40h]
0x18002bbef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbf4  mov     ebx, eax
0x18002bbf6  mov     rcx, [rsp+68h]; this
0x18002bbfb  test    eax, eax
0x18002bbfd  jns     short loc_18002BC13
0x18002bbff  mov     r9d, eax; char *
0x18002bc02  lea     r8, aOnecoreNetNetp; "onecore\\net\\netprofiles\\service\\src"...
0x18002bc09  mov     edx, 0ECh; void *
0x18002bc0e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002bc13  cmp     [rsp+68h+var_30], 0
0x18002bc19  jz      short loc_18002BC26
0x18002bc1b  lea     rcx, [rsp+68h+var_30]
0x18002bc20  call    ?PrintNetworkInstance@@YAXAEBV?$com_ptr_t@UINetwork@@Uerr_exception_policy@wil@@@wil@@@Z; PrintNetworkInstance(wil::com_ptr_t<INetwork,wil::err_exception_policy> const &)
0x18002bc25  nop
0x18002bc26  lea     rcx, [rsp+68h+var_30]
0x18002bc2b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002bc30  jmp     short loc_18002BBC5
0x18002bc32  lea     rcx, [rsp+68h+var_28]
0x18002bc37  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002bc3c  nop
0x18002bc3d  lea     rcx, [rsp+68h+var_20]
0x18002bc42  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002bc47  nop
0x18002bc48  mov     al, [rsp+68h+var_38]
0x18002bc4c  mov     [rsp+68h+var_38], 0
0x18002bc51  test    al, al
0x18002bc53  jz      short loc_18002BC5B
0x18002bc55  call    cs:__imp_CoUninitialize
0x18002bc5b  xor     eax, eax
0x18002bc5d  jmp     short loc_18002BC63
0x18002bc5f  mov     eax, [rsp+68h+var_34]
0x18002bc63  mov     rcx, [rsp+68h+var_18]
0x18002bc68  xor     rcx, rsp; StackCookie
0x18002bc6b  call    __security_check_cookie
0x18002bc70  add     rsp, 60h
0x18002bc74  pop     rbx
0x18002bc75  retn
```
