# StartNspRpc(void)

- ea: `0x1800a13e8`
- end: `0x1800a166d`
- name: `?StartNspRpc@@YAJXZ`
- size: `645`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800bba00`

## callees

- `0x18000fab0`
- `0x180013748`
- `0x18004faf4`
- `0x18005085c`
- `0x1800a13e8`
- `0x1800a1724`
- `0x1800a88a0`
- `0x1800baf04`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a163d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a163d`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x1800a148d`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x1800a148d`
- `RPCRT4!RpcEpRegisterW` at `0x1800a15da`
- `RPCRT4!RpcEpRegisterW` at `0x1800a15da`
- `RPCRT4!RpcServerInqBindings` at `0x1800a159e`
- `RPCRT4!RpcServerInqBindings` at `0x1800a159e`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800a1569`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800a1569`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800a14cd`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800a14cd`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800a143c`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800a143c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a1510`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a1510`

## string_xrefs

- `0x1800a1451`: `onecore\net\netprofiles\service\src\nsprpc\lib\nsprpc.cpp`
- `0x1800a14a2`: `onecore\net\netprofiles\service\src\nsprpc\lib\nsprpc.cpp`
- `0x1800a14e2`: `onecore\net\netprofiles\service\src\nsprpc\lib\nsprpc.cpp`
- `0x1800a1522`: `onecore\net\netprofiles\service\src\nsprpc\lib\nsprpc.cpp`
- `0x1800a157e`: `onecore\net\netprofiles\service\src\nsprpc\lib\nsprpc.cpp`
- `0x1800a15b3`: `onecore\net\netprofiles\service\src\nsprpc\lib\nsprpc.cpp`
- `0x1800a15ef`: `onecore\net\netprofiles\service\src\nsprpc\lib\nsprpc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 StartNspRpc(void)
{
  unsigned int v0; // eax
  unsigned int v1; // eax
  unsigned int v2; // eax
  const char *v3; // r9
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v8; // [rsp+20h] [rbp-68h]
  RPC_WSTR *p_ServerPrincName; // [rsp+40h] [rbp-48h] BYREF
  RPC_WSTR PrincName; // [rsp+48h] [rbp-40h] BYREF
  char v11; // [rsp+50h] [rbp-38h]
  RPC_BINDING_VECTOR *BindingVector; // [rsp+58h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-28h] BYREF
  RPC_WSTR ServerPrincName; // [rsp+68h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5acd775e932b3e3b9550f10a64950dae_Traceguids);
  v0 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, 0);
  if ( v0 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\nsprpc\\lib\\nsprpc.cpp",
      (const char *)v0,
      v8);
  ServerPrincName = 0;
  p_ServerPrincName = &ServerPrincName;
  PrincName = 0;
  v11 = 1;
  v1 = RpcServerInqDefaultPrincNameW(0xAu, &PrincName);
  if ( v1 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\nsprpc\\lib\\nsprpc.cpp",
      (const char *)v1,
      v8);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_ServerPrincName);
  v2 = RpcServerRegisterAuthInfoW(ServerPrincName, 0xAu, 0, 0);
  if ( v2 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\nsprpc\\lib\\nsprpc.cpp",
      (const char *)v2,
      v8);
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GA;;;AC)(A;;GA;;;S-1-15-3-1)(A;;GA;;;S-1-15-3-2)"
           "(A;;GA;;;S-1-15-3-3)S:(ML;;NW;;;LW)",
          1u,
          &SecurityDescriptor,
          0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\nsprpc\\lib\\nsprpc.cpp",
      v3);
  v4 = RpcServerRegisterIf3(qword_18014F1B0, 0, 0, 41);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\nsprpc\\lib\\nsprpc.cpp",
      (const char *)v4,
      0x4D2u);
  BindingVector = 0;
  v5 = RpcServerInqBindings(&BindingVector);
  if ( v5 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\nsprpc\\lib\\nsprpc.cpp",
      (const char *)v5,
      0x4D2u);
  v6 = RpcEpRegisterW(qword_18014F1B0, BindingVector, 0, (RPC_WSTR)L"NSP Rpc Interface");
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\nsprpc\\lib\\nsprpc.cpp",
      (const char *)v6,
      0x4D2u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_5acd775e932b3e3b9550f10a64950dae_Traceguids);
  wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>(&BindingVector);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ServerPrincName);
  return 0;
}

```

## disassembly

```asm
0x1800a13e8  push    rdi
0x1800a13ea  sub     rsp, 80h
0x1800a13f1  mov     rax, cs:__security_cookie
0x1800a13f8  xor     rax, rsp
0x1800a13fb  mov     [rsp+88h+var_18], rax
0x1800a1400  lea     rdi, WPP_GLOBAL_Control
0x1800a1407  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a140e  cmp     rcx, rdi
0x1800a1411  jz      short loc_1800A142E
0x1800a1413  test    byte ptr [rcx+1Ch], 4
0x1800a1417  jz      short loc_1800A142E
0x1800a1419  mov     edx, 0Ah
0x1800a141e  lea     r8, WPP_5acd775e932b3e3b9550f10a64950dae_Traceguids
0x1800a1425  mov     rcx, [rcx+10h]
0x1800a1429  call    WPP_SF_
0x1800a142e  xor     r8d, r8d; SecurityDescriptor
0x1800a1431  lea     edx, [r8+0Ah]; MaxCalls
0x1800a1435  mov     rcx, cs:off_18014BD20; Protseq
0x1800a143c  call    cs:__imp_RpcServerUseProtseqW
0x1800a1442  mov     rcx, [rsp+88h]; this
0x1800a144a  test    eax, eax
0x1800a144c  jz      short loc_1800A1462
0x1800a144e  mov     r9d, eax; char *
0x1800a1451  lea     r8, aOnecoreNetNetp_35; "onecore\\net\\netprofiles\\service\\src"...
0x1800a1458  mov     edx, 42h ; 'B'; void *
0x1800a145d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800a1462  mov     [rsp+88h+ServerPrincName], 0
0x1800a146b  lea     rax, [rsp+88h+ServerPrincName]
0x1800a1470  mov     [rsp+88h+var_48], rax
0x1800a1475  mov     [rsp+88h+PrincName], 0
0x1800a147e  mov     [rsp+88h+var_38], 1
0x1800a1483  lea     rdx, [rsp+88h+PrincName]; PrincName
0x1800a1488  mov     ecx, 0Ah; AuthnSvc
0x1800a148d  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x1800a1493  mov     rcx, [rsp+88h]; this
0x1800a149b  test    eax, eax
0x1800a149d  jz      short loc_1800A14B4
0x1800a149f  mov     r9d, eax; char *
0x1800a14a2  lea     r8, aOnecoreNetNetp_35; "onecore\\net\\netprofiles\\service\\src"...
0x1800a14a9  mov     edx, 46h ; 'F'; void *
0x1800a14ae  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800a14b4  lea     rcx, [rsp+88h+var_48]
0x1800a14b9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800a14be  xor     r9d, r9d; Arg
0x1800a14c1  xor     r8d, r8d; GetKeyFn
0x1800a14c4  lea     edx, [r9+0Ah]; AuthnSvc
0x1800a14c8  mov     rcx, [rsp+88h+ServerPrincName]; ServerPrincName
0x1800a14cd  call    cs:__imp_RpcServerRegisterAuthInfoW
0x1800a14d3  mov     rcx, [rsp+88h]; this
0x1800a14db  test    eax, eax
0x1800a14dd  jz      short loc_1800A14F4
0x1800a14df  mov     r9d, eax; char *
0x1800a14e2  lea     r8, aOnecoreNetNetp_35; "onecore\\net\\netprofiles\\service\\src"...
0x1800a14e9  mov     edx, 47h ; 'G'; void *
0x1800a14ee  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800a14f4  mov     [rsp+88h+SecurityDescriptor], 0
0x1800a14fd  xor     r9d, r9d; SecurityDescriptorSize
0x1800a1500  lea     r8, [rsp+88h+SecurityDescriptor]; SecurityDescriptor
0x1800a1505  lea     edx, [r9+1]; StringSDRevision
0x1800a1509  lea     rcx, aDAGrgwgxWdAGrg_1; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x1800a1510  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800a1516  mov     rcx, [rsp+88h]; this
0x1800a151e  test    eax, eax
0x1800a1520  jnz     short loc_1800A1531
0x1800a1522  lea     r8, aOnecoreNetNetp_35; "onecore\\net\\netprofiles\\service\\src"...
0x1800a1529  lea     edx, [rax+56h]; void *
0x1800a152c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800a1531  mov     rax, [rsp+88h+SecurityDescriptor]
0x1800a1536  mov     [rsp+88h+var_50], rax
0x1800a153b  lea     rax, ?SecurityCallBack@@YAJPEAX0@Z; SecurityCallBack(void *,void *)
0x1800a1542  mov     [rsp+88h+var_58], rax
0x1800a1547  mov     [rsp+88h+var_60], 0
0x1800a154f  mov     [rsp+88h+var_68], 4D2h; unsigned int
0x1800a1557  mov     r9d, 29h ; ')'
0x1800a155d  xor     r8d, r8d
0x1800a1560  xor     edx, edx
0x1800a1562  lea     rcx, qword_18014F1B0
0x1800a1569  call    cs:__imp_RpcServerRegisterIf3
0x1800a156f  mov     rcx, [rsp+88h]; this
0x1800a1577  test    eax, eax
0x1800a1579  jz      short loc_1800A1590
0x1800a157b  mov     r9d, eax; char *
0x1800a157e  lea     r8, aOnecoreNetNetp_35; "onecore\\net\\netprofiles\\service\\src"...
0x1800a1585  mov     edx, 62h ; 'b'; void *
0x1800a158a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800a1590  mov     [rsp+88h+BindingVector], 0
0x1800a1599  lea     rcx, [rsp+88h+BindingVector]; BindingVector
0x1800a159e  call    cs:__imp_RpcServerInqBindings
0x1800a15a4  mov     rcx, [rsp+88h]; this
0x1800a15ac  test    eax, eax
0x1800a15ae  jz      short loc_1800A15C4
0x1800a15b0  mov     r9d, eax; char *
0x1800a15b3  lea     r8, aOnecoreNetNetp_35; "onecore\\net\\netprofiles\\service\\src"...
0x1800a15ba  mov     edx, 65h ; 'e'; void *
0x1800a15bf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800a15c4  lea     r9, Annotation; "NSP Rpc Interface"
0x1800a15cb  xor     r8d, r8d; UuidVector
0x1800a15ce  mov     rdx, [rsp+88h+BindingVector]; BindingVector
0x1800a15d3  lea     rcx, qword_18014F1B0; IfSpec
0x1800a15da  call    cs:__imp_RpcEpRegisterW
0x1800a15e0  mov     rcx, [rsp+88h]; this
0x1800a15e8  test    eax, eax
0x1800a15ea  jz      short loc_1800A1600
0x1800a15ec  mov     r9d, eax; char *
0x1800a15ef  lea     r8, aOnecoreNetNetp_35; "onecore\\net\\netprofiles\\service\\src"...
0x1800a15f6  mov     edx, 68h ; 'h'; void *
0x1800a15fb  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800a1600  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1607  cmp     rcx, rdi
0x1800a160a  jz      short loc_1800A1628
0x1800a160c  test    byte ptr [rcx+1Ch], 4
0x1800a1610  jz      short loc_1800A1628
0x1800a1612  mov     edx, 0Bh
0x1800a1617  lea     r8, WPP_5acd775e932b3e3b9550f10a64950dae_Traceguids
0x1800a161e  mov     rcx, [rcx+10h]
0x1800a1622  call    WPP_SF_
0x1800a1627  nop
0x1800a1628  lea     rcx, [rsp+88h+BindingVector]
0x1800a162d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RPC_BINDING_VECTOR@@P6AXPEAU1@@Z$1?WpRpcBindingVectorFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>(void)
0x1800a1632  nop
0x1800a1633  mov     rcx, [rsp+88h+SecurityDescriptor]; hMem
0x1800a1638  test    rcx, rcx
0x1800a163b  jz      short loc_1800A1644
0x1800a163d  call    cs:__imp_LocalFree
0x1800a1643  nop
0x1800a1644  lea     rcx, [rsp+88h+ServerPrincName]
0x1800a1649  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a164e  xor     eax, eax
0x1800a1650  jmp     short loc_1800A1656
0x1800a1652  mov     eax, dword ptr [rsp+88h+BindingVector]
0x1800a1656  mov     rcx, [rsp+88h+var_18]
0x1800a165b  xor     rcx, rsp; StackCookie
0x1800a165e  call    __security_check_cookie
0x1800a1663  add     rsp, 80h
0x1800a166a  pop     rdi
0x1800a166b  retn
```
