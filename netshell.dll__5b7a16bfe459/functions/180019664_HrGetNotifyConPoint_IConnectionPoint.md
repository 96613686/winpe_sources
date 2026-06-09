# HrGetNotifyConPoint(IConnectionPoint * *)

- ea: `0x180019664`
- end: `0x18001978d`
- name: `?HrGetNotifyConPoint@@YAJPEAPEAUIConnectionPoint@@@Z`
- size: `297`
- prototype: `__int64 __fastcall(struct IConnectionPoint **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009d4c`
- `0x180041e70`

## callees

- `0x180018d74`
- `0x180019664`
- `0x180034c18`
- `0x180065010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180019699`
- `ole32!CoCreateInstance` at `0x180019699`
- `ole32!CoSetProxyBlanket` at `0x1800196e3`
- `ole32!CoSetProxyBlanket` at `0x18001974f`
- `ole32!CoSetProxyBlanket` at `0x1800196e3`
- `ole32!CoSetProxyBlanket` at `0x18001974f`

## pseudocode

```c
__int64 __fastcall HrGetNotifyConPoint(IUnknown **a1)
{
  HRESULT Instance; // ebx
  IUnknown *pProxy; // [rsp+58h] [rbp+10h] BYREF
  IUnknown *v5; // [rsp+60h] [rbp+18h] BYREF

  pProxy = 0;
  Instance = CoCreateInstance(
               &CLSID_ConnectionManager,
               0,
               0x404u,
               &GUID_b196b284_bab4_101a_b69c_00aa00341d07,
               (LPVOID *)&pProxy);
  if ( Instance >= 0 )
  {
    NcSetProxyBlanket(pProxy);
    Instance = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
    if ( Instance >= 0 )
    {
      v5 = 0;
      Instance = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))pProxy->lpVtbl[1].AddRef)(
                   pProxy,
                   &IID_INetConnectionNotifySink,
                   &v5);
      if ( Instance >= 0 )
      {
        Instance = CoSetProxyBlanket(v5, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
        if ( Instance < 0 )
          ((void (__fastcall *)(IUnknown *))v5->lpVtbl->Release)(v5);
        else
          *a1 = v5;
      }
    }
    ReleaseObj(pProxy);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180019664  mov     r11, rsp
0x180019667  mov     [r11+8], rbx
0x18001966b  push    rdi
0x18001966c  sub     rsp, 40h
0x180019670  mov     rdi, rcx
0x180019673  mov     qword ptr [r11+10h], 0
0x18001967b  lea     rax, [r11+10h]
0x18001967f  xor     edx, edx; pUnkOuter
0x180019681  lea     rcx, CLSID_ConnectionManager; rclsid
0x180019688  mov     [r11-28h], rax
0x18001968c  lea     r9, _GUID_b196b284_bab4_101a_b69c_00aa00341d07; riid
0x180019693  mov     r8d, 404h; dwClsContext
0x180019699  call    cs:__imp_CoCreateInstance
0x18001969f  mov     ebx, eax
0x1800196a1  test    eax, eax
0x1800196a3  js      loc_180019780
0x1800196a9  mov     rcx, [rsp+48h+pProxy]; pProxy
0x1800196ae  call    ?NcSetProxyBlanket@@YAXPEAUIUnknown@@@Z; NcSetProxyBlanket(IUnknown *)
0x1800196b3  mov     rcx, [rsp+48h+pProxy]; pProxy
0x1800196b8  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800196bc  mov     [rsp+48h+dwCapabilities], 20h ; ' '; dwCapabilities
0x1800196c4  xor     r8d, r8d; dwAuthzSvc
0x1800196c7  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x1800196d0  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1800196d3  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x1800196db  mov     [rsp+48h+dwAuthnLevel], 0; dwAuthnLevel
0x1800196e3  call    cs:__imp_CoSetProxyBlanket
0x1800196e9  mov     ebx, eax
0x1800196eb  test    eax, eax
0x1800196ed  js      loc_180019776
0x1800196f3  mov     rcx, [rsp+48h+pProxy]
0x1800196f8  lea     r8, [rsp+48h+arg_10]
0x1800196fd  mov     [rsp+48h+arg_10], 0
0x180019706  lea     rdx, IID_INetConnectionNotifySink
0x18001970d  mov     rax, [rcx]
0x180019710  mov     rax, [rax+20h]
0x180019714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019719  mov     ebx, eax
0x18001971b  test    eax, eax
0x18001971d  js      short loc_180019776
0x18001971f  mov     rcx, [rsp+48h+arg_10]; pProxy
0x180019724  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180019728  mov     [rsp+48h+dwCapabilities], 20h ; ' '; dwCapabilities
0x180019730  xor     r8d, r8d; dwAuthzSvc
0x180019733  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x18001973c  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001973f  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x180019747  mov     [rsp+48h+dwAuthnLevel], 0; dwAuthnLevel
0x18001974f  call    cs:__imp_CoSetProxyBlanket
0x180019755  mov     ebx, eax
0x180019757  test    eax, eax
0x180019759  js      short loc_180019765
0x18001975b  mov     rax, [rsp+48h+arg_10]
0x180019760  mov     [rdi], rax
0x180019763  jmp     short loc_180019776
0x180019765  mov     rcx, [rsp+48h+arg_10]
0x18001976a  mov     rax, [rcx]
0x18001976d  mov     rax, [rax+10h]
0x180019771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019776  mov     rcx, [rsp+48h+pProxy]; struct IUnknown *
0x18001977b  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180019780  mov     eax, ebx
0x180019782  mov     rbx, [rsp+48h+arg_0]
0x180019787  add     rsp, 40h
0x18001978b  pop     rdi
0x18001978c  retn
```
