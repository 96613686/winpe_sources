# CSteelhead::HrPassToAddInterfaces(void)

- ea: `0x180036660`
- end: `0x18003686a`
- name: `?HrPassToAddInterfaces@CSteelhead@@IEAAJXZ`
- size: `522`
- prototype: `__int64 __fastcall(struct INetCfg **this, __int64, const struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180036c94`

## callees

- `0x180035948`
- `0x180035a78`
- `0x180035f84`
- `0x180036564`
- `0x180036660`
- `0x180036b84`
- `0x180036e4c`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800367f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800367f9`
- `rtutils!TracePrintfW` at `0x18003684d`
- `rtutils!TracePrintfW` at `0x18003684d`

## pseudocode

```c
__int64 __fastcall CSteelhead::HrPassToAddInterfaces(struct INetCfg **this, __int64 a2, const struct _GUID *a3)
{
  int ShouldRouteOverAdapter; // ebx
  struct INetCfgComponent *v5; // r14
  struct INetCfgComponent *v6; // rcx
  struct INetCfg *v7; // r9
  _DWORD *v8; // rsi
  unsigned int v9; // r8d
  unsigned int v10; // r8d
  int v11; // edi
  const WCHAR *v12; // rdx
  _QWORD v14[6]; // [rsp+30h] [rbp-30h] BYREF
  struct INetCfgComponent *v15; // [rsp+90h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+38h] BYREF
  __int64 v17; // [rsp+A0h] [rbp+40h] BYREF

  CIterNetCfgComponent::CIterNetCfgComponent((CIterNetCfgComponent *)v14, this[1], a3);
  v15 = 0;
  do
  {
    ShouldRouteOverAdapter = CIEnumIter<IEnumNetCfgComponent,INetCfgComponent *>::HrNext(v14, (__int64 *)&v15);
    if ( ShouldRouteOverAdapter )
      break;
    pv = 0;
    v5 = v15;
    ShouldRouteOverAdapter = HrShouldRouteOverAdapter(v15, (unsigned __int16 **)&pv);
    if ( !ShouldRouteOverAdapter )
    {
      v6 = 0;
      v15 = 0;
      v7 = this[5];
      v8 = this + 142;
      if ( v7 && *v8 )
      {
        ShouldRouteOverAdapter = ((__int64 (__fastcall *)(struct INetCfg *, GUID *, struct INetCfgComponent **))v7->lpVtbl->QueryInterface)(
                                   this[5],
                                   &IID_INetCfgComponentBindings,
                                   &v15);
        v6 = v15;
      }
      if ( this[5] && *v8 && ShouldRouteOverAdapter >= 0 )
      {
        ShouldRouteOverAdapter = ((__int64 (__fastcall *)(struct INetCfgComponent *, struct INetCfgComponent *))v6->lpVtbl->GetId)(
                                   v6,
                                   v5);
        if ( !ShouldRouteOverAdapter )
          ShouldRouteOverAdapter = CSteelhead::HrEnsureRouterInterfaceForAdapter(
                                     (CSteelhead *)this,
                                     ROUTER_IF_TYPE_DEDICATED,
                                     v9,
                                     (const unsigned __int16 *)pv,
                                     (const unsigned __int16 *)pv,
                                     (const struct ROUTER_MANAGER_INFO *)&qword_1800540F8);
        v6 = v15;
      }
      if ( v6 )
        ((void (__fastcall *)(struct INetCfgComponent *))v6->lpVtbl->Release)(v6);
      v15 = 0;
      v17 = 0;
      if ( (unsigned int)CSteelhead::IsIpv6TransportInstalled((CSteelhead *)this) )
        ShouldRouteOverAdapter = ((__int64 (__fastcall *)(struct INetCfg *, GUID *, __int64 *))this[11]->lpVtbl->QueryInterface)(
                                   this[11],
                                   &IID_INetCfgComponentBindings,
                                   &v17);
      if ( (unsigned int)CSteelhead::IsIpv6TransportInstalled((CSteelhead *)this) )
      {
        if ( ShouldRouteOverAdapter >= 0 )
        {
          ShouldRouteOverAdapter = (*(__int64 (__fastcall **)(__int64, struct INetCfgComponent *))(*(_QWORD *)v17 + 48LL))(
                                     v17,
                                     v5);
          if ( !ShouldRouteOverAdapter )
            ShouldRouteOverAdapter = CSteelhead::HrEnsureRouterInterfaceForAdapter(
                                       (CSteelhead *)this,
                                       ROUTER_IF_TYPE_DEDICATED,
                                       v10,
                                       (const unsigned __int16 *)pv,
                                       (const unsigned __int16 *)pv,
                                       (const struct ROUTER_MANAGER_INFO *)&qword_1800540C8);
        }
      }
      if ( v15 )
        ((void (__fastcall *)(struct INetCfgComponent *))v15->lpVtbl->Release)(v15);
      v17 = 0;
      CoTaskMemFree(pv);
    }
    if ( v5 )
      ((void (__fastcall *)(struct INetCfgComponent *))v5->lpVtbl->Release)(v5);
    v15 = 0;
  }
  while ( ShouldRouteOverAdapter >= 0 );
  v11 = 0;
  if ( ShouldRouteOverAdapter != 1 )
    v11 = ShouldRouteOverAdapter;
  v12 = L"%hs succeeded : hr = %08lx";
  if ( v11 < 0 )
    v12 = L"%hs failed : hr = %08lx";
  TracePrintfW(g_dwTraceHandle, v12, "CSteelhead::HrPassToAddInterfaces", (unsigned int)v11);
  CIterNetCfgComponent::~CIterNetCfgComponent((CIterNetCfgComponent *)v14);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180036660  push    rbp
0x180036662  push    rbx
0x180036663  push    rsi
0x180036664  push    rdi
0x180036665  push    r14
0x180036667  mov     rbp, rsp
0x18003666a  sub     rsp, 60h
0x18003666e  mov     rdi, rcx
0x180036671  mov     rdx, [rcx+8]; struct INetCfg *
0x180036675  lea     rcx, [rbp+var_30]; this
0x180036679  call    ??0CIterNetCfgComponent@@QEAA@PEAUINetCfg@@PEBU_GUID@@@Z; CIterNetCfgComponent::CIterNetCfgComponent(INetCfg *,_GUID const *)
0x18003667e  nop
0x18003667f  mov     [rbp+arg_0], 0
0x180036687  lea     rdx, [rbp+arg_0]
0x18003668b  lea     rcx, [rbp+var_30]
0x18003668f  call    ?HrNext@?$CIEnumIter@UIEnumNetCfgComponent@@PEAUINetCfgComponent@@@@QEAAJPEAPEAUINetCfgComponent@@@Z; CIEnumIter<IEnumNetCfgComponent,INetCfgComponent *>::HrNext(INetCfgComponent * *)
0x180036694  mov     ebx, eax
0x180036696  test    eax, eax
0x180036698  jnz     loc_180036823
0x18003669e  mov     [rbp+pv], 0
0x1800366a6  lea     rdx, [rbp+pv]; unsigned __int16 **
0x1800366aa  mov     r14, [rbp+arg_0]
0x1800366ae  mov     rcx, r14; struct INetCfgComponent *
0x1800366b1  call    ?HrShouldRouteOverAdapter@@YAJPEAUINetCfgComponent@@PEAPEAG@Z; HrShouldRouteOverAdapter(INetCfgComponent *,ushort * *)
0x1800366b6  mov     ebx, eax
0x1800366b8  test    eax, eax
0x1800366ba  jnz     loc_1800367FF
0x1800366c0  xor     ecx, ecx
0x1800366c2  mov     [rbp+arg_0], rcx
0x1800366c6  mov     r9, [rdi+28h]
0x1800366ca  lea     rsi, [rdi+470h]
0x1800366d1  test    r9, r9
0x1800366d4  jz      short loc_1800366F9
0x1800366d6  cmp     [rsi], ecx
0x1800366d8  jz      short loc_1800366F9
0x1800366da  mov     rax, [r9]
0x1800366dd  lea     r8, [rbp+arg_0]
0x1800366e1  lea     rdx, IID_INetCfgComponentBindings
0x1800366e8  mov     rcx, r9
0x1800366eb  mov     rax, [rax]
0x1800366ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800366f3  mov     ebx, eax
0x1800366f5  mov     rcx, [rbp+arg_0]
0x1800366f9  cmp     qword ptr [rdi+28h], 0
0x1800366fe  jz      short loc_180036744
0x180036700  cmp     dword ptr [rsi], 0
0x180036703  jz      short loc_180036744
0x180036705  test    ebx, ebx
0x180036707  js      short loc_180036744
0x180036709  mov     rax, [rcx]
0x18003670c  mov     rdx, r14
0x18003670f  mov     rax, [rax+30h]
0x180036713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036718  mov     ebx, eax
0x18003671a  test    eax, eax
0x18003671c  jnz     short loc_180036740
0x18003671e  lea     rax, qword_1800540F8
0x180036725  mov     [rsp+60h+var_38], rax; struct ROUTER_MANAGER_INFO *
0x18003672a  mov     r9, [rbp+pv]; unsigned __int16 *
0x18003672e  mov     [rsp+60h+var_40], r9; unsigned __int16 *
0x180036733  lea     edx, [rbx+3]; enum _ROUTER_INTERFACE_TYPE
0x180036736  mov     rcx, rdi; this
0x180036739  call    ?HrEnsureRouterInterfaceForAdapter@CSteelhead@@IEAAJW4_ROUTER_INTERFACE_TYPE@@KPEBG1AEBUROUTER_MANAGER_INFO@@@Z; CSteelhead::HrEnsureRouterInterfaceForAdapter(_ROUTER_INTERFACE_TYPE,ulong,ushort const *,ushort const *,ROUTER_MANAGER_INFO const &)
0x18003673e  mov     ebx, eax
0x180036740  mov     rcx, [rbp+arg_0]
0x180036744  test    rcx, rcx
0x180036747  jz      short loc_180036755
0x180036749  mov     rax, [rcx]
0x18003674c  mov     rax, [rax+10h]
0x180036750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036755  mov     [rbp+arg_0], 0
0x18003675d  mov     [rbp+arg_10], 0
0x180036765  mov     rcx, rdi; this
0x180036768  call    ?IsIpv6TransportInstalled@CSteelhead@@AEAAHXZ; CSteelhead::IsIpv6TransportInstalled(void)
0x18003676d  test    eax, eax
0x18003676f  jz      short loc_18003678D
0x180036771  mov     rcx, [rdi+58h]
0x180036775  mov     rax, [rcx]
0x180036778  lea     r8, [rbp+arg_10]
0x18003677c  lea     rdx, IID_INetCfgComponentBindings
0x180036783  mov     rax, [rax]
0x180036786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003678b  mov     ebx, eax
0x18003678d  mov     rcx, rdi; this
0x180036790  call    ?IsIpv6TransportInstalled@CSteelhead@@AEAAHXZ; CSteelhead::IsIpv6TransportInstalled(void)
0x180036795  test    eax, eax
0x180036797  jz      short loc_1800367D8
0x180036799  test    ebx, ebx
0x18003679b  js      short loc_1800367D8
0x18003679d  mov     rcx, [rbp+arg_10]
0x1800367a1  mov     rax, [rcx]
0x1800367a4  mov     rdx, r14
0x1800367a7  mov     rax, [rax+30h]
0x1800367ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367b0  mov     ebx, eax
0x1800367b2  test    eax, eax
0x1800367b4  jnz     short loc_1800367D8
0x1800367b6  lea     rax, qword_1800540C8
0x1800367bd  mov     [rsp+60h+var_38], rax; struct ROUTER_MANAGER_INFO *
0x1800367c2  mov     r9, [rbp+pv]; unsigned __int16 *
0x1800367c6  mov     [rsp+60h+var_40], r9; unsigned __int16 *
0x1800367cb  lea     edx, [rbx+3]; enum _ROUTER_INTERFACE_TYPE
0x1800367ce  mov     rcx, rdi; this
0x1800367d1  call    ?HrEnsureRouterInterfaceForAdapter@CSteelhead@@IEAAJW4_ROUTER_INTERFACE_TYPE@@KPEBG1AEBUROUTER_MANAGER_INFO@@@Z; CSteelhead::HrEnsureRouterInterfaceForAdapter(_ROUTER_INTERFACE_TYPE,ulong,ushort const *,ushort const *,ROUTER_MANAGER_INFO const &)
0x1800367d6  mov     ebx, eax
0x1800367d8  mov     rcx, [rbp+arg_0]
0x1800367dc  test    rcx, rcx
0x1800367df  jz      short loc_1800367ED
0x1800367e1  mov     rax, [rcx]
0x1800367e4  mov     rax, [rax+10h]
0x1800367e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367ed  mov     [rbp+arg_10], 0
0x1800367f5  mov     rcx, [rbp+pv]; pv
0x1800367f9  call    cs:__imp_CoTaskMemFree
0x1800367ff  test    r14, r14
0x180036802  jz      short loc_180036813
0x180036804  mov     rax, [r14]
0x180036807  mov     rcx, r14
0x18003680a  mov     rax, [rax+10h]
0x18003680e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036813  mov     [rbp+arg_0], 0
0x18003681b  test    ebx, ebx
0x18003681d  jns     loc_180036687
0x180036823  xor     edi, edi
0x180036825  cmp     ebx, 1
0x180036828  cmovnz  edi, ebx
0x18003682b  mov     r9d, edi
0x18003682e  lea     r8, aCsteelheadHrpa_0; "CSteelhead::HrPassToAddInterfaces"
0x180036835  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x18003683b  test    edi, edi
0x18003683d  lea     rdx, szFormat; "%hs succeeded : hr = %08lx"
0x180036844  jns     short loc_18003684D
0x180036846  lea     rdx, aHsFailedHr08lx; "%hs failed : hr = %08lx"
0x18003684d  call    cs:__imp_TracePrintfW
0x180036853  nop
0x180036854  lea     rcx, [rbp+var_30]; this
0x180036858  call    ??1CIterNetCfgComponent@@QEAA@XZ; CIterNetCfgComponent::~CIterNetCfgComponent(void)
0x18003685d  mov     eax, edi
0x18003685f  add     rsp, 60h
0x180036863  pop     r14
0x180036865  pop     rdi
0x180036866  pop     rsi
0x180036867  pop     rbx
0x180036868  pop     rbp
0x180036869  retn
```
