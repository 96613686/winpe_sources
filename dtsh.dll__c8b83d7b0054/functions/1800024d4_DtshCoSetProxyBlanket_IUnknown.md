# DtshCoSetProxyBlanket(IUnknown *)

- ea: `0x1800024d4`
- end: `0x180002599`
- name: `?DtshCoSetProxyBlanket@@YAJPEAUIUnknown@@@Z`
- size: `197`
- prototype: `__int64 __fastcall(struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003b00`

## callees

- `0x1800024d4`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000250a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180002573`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000250a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180002573`

## pseudocode

```c
__int64 __fastcall DtshCoSetProxyBlanket(struct IUnknown *a1)
{
  HRESULT v2; // ebx
  struct IUnknownVtbl *lpVtbl; // rax
  IUnknown *pProxy; // [rsp+58h] [rbp+10h] BYREF

  v2 = CoSetProxyBlanket(a1, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 3u, 3u, 0, 0x20u);
  if ( v2 >= 0 )
  {
    lpVtbl = a1->lpVtbl;
    pProxy = 0;
    v2 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, IUnknown **))lpVtbl->QueryInterface)(
           a1,
           &GUID_00000000_0000_0000_c000_000000000046,
           &pProxy);
    if ( v2 >= 0 )
    {
      if ( pProxy )
      {
        v2 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0, 0, 3u, 3u, 0, 0x20u);
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800024d4  mov     rax, rsp
0x1800024d7  mov     [rax+8], rbx
0x1800024db  push    rdi
0x1800024dc  sub     rsp, 40h
0x1800024e0  mov     dword ptr [rax-10h], 20h ; ' '
0x1800024e7  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800024eb  mov     qword ptr [rax-18h], 0
0x1800024f3  xor     r8d, r8d; dwAuthzSvc
0x1800024f6  mov     dword ptr [rax-20h], 3
0x1800024fd  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180002500  mov     dword ptr [rax-28h], 3
0x180002507  mov     rdi, rcx
0x18000250a  call    cs:__imp_CoSetProxyBlanket
0x180002510  mov     ebx, eax
0x180002512  test    eax, eax
0x180002514  js      short loc_18000258C
0x180002516  mov     rax, [rdi]
0x180002519  lea     r8, [rsp+48h+pProxy]
0x18000251e  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180002525  mov     [rsp+48h+pProxy], 0
0x18000252e  mov     rcx, rdi
0x180002531  mov     rax, [rax]
0x180002534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002539  mov     ebx, eax
0x18000253b  test    eax, eax
0x18000253d  js      short loc_18000258C
0x18000253f  mov     rcx, [rsp+48h+pProxy]; pProxy
0x180002544  test    rcx, rcx
0x180002547  jz      short loc_18000258C
0x180002549  mov     [rsp+48h+dwCapabilities], 20h ; ' '; dwCapabilities
0x180002551  xor     r9d, r9d; pServerPrincName
0x180002554  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x18000255d  xor     r8d, r8d; dwAuthzSvc
0x180002560  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x180002568  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000256b  mov     [rsp+48h+dwAuthnLevel], 3; dwAuthnLevel
0x180002573  call    cs:__imp_CoSetProxyBlanket
0x180002579  mov     rcx, [rsp+48h+pProxy]
0x18000257e  mov     ebx, eax
0x180002580  mov     rax, [rcx]
0x180002583  mov     rax, [rax+10h]
0x180002587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000258c  mov     eax, ebx
0x18000258e  mov     rbx, [rsp+48h+arg_0]
0x180002593  add     rsp, 40h
0x180002597  pop     rdi
0x180002598  retn
```
