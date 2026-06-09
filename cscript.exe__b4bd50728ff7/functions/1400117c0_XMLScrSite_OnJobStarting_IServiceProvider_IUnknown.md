# XMLScrSite::OnJobStarting(IServiceProvider *,IUnknown *)

- ea: `0x1400117c0`
- end: `0x140011821`
- name: `?OnJobStarting@XMLScrSite@@UEAAJPEAUIServiceProvider@@PEAUIUnknown@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, struct IServiceProvider *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x14000977c`
- `0x1400117c0`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall XMLScrSite::OnJobStarting(CHost **this, struct IServiceProvider *a2, struct IUnknown *a3)
{
  struct IUnknownVtbl *lpVtbl; // rax
  struct IDispatch *v6; // [rsp+40h] [rbp+18h] BYREF

  lpVtbl = a3->lpVtbl;
  v6 = 0;
  if ( ((int (__fastcall *)(struct IUnknown *, GUID *, struct IDispatch **))lpVtbl->QueryInterface)(
         a3,
         &IID_IDispatch,
         &v6) < 0 )
    return 2147500037LL;
  CHost::SetScriptDispatch(this[2], v6);
  ((void (__fastcall *)(struct IDispatch *))v6->lpVtbl->Release)(v6);
  return 0;
}

```

## disassembly

```asm
0x1400117c0  push    rbx
0x1400117c2  sub     rsp, 20h
0x1400117c6  mov     rax, [r8]
0x1400117c9  lea     rdx, IID_IDispatch
0x1400117d0  mov     r9, r8
0x1400117d3  mov     [rsp+28h+arg_10], 0
0x1400117dc  mov     rbx, rcx
0x1400117df  lea     r8, [rsp+28h+arg_10]
0x1400117e4  mov     rcx, r9
0x1400117e7  mov     rax, [rax]
0x1400117ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400117ef  test    eax, eax
0x1400117f1  jns     short loc_1400117FA
0x1400117f3  mov     eax, 80004005h
0x1400117f8  jmp     short loc_14001181B
0x1400117fa  mov     rdx, [rsp+28h+arg_10]; struct IDispatch *
0x1400117ff  mov     rcx, [rbx+10h]; this
0x140011803  call    ?SetScriptDispatch@CHost@@QEAAXPEAUIDispatch@@@Z; CHost::SetScriptDispatch(IDispatch *)
0x140011808  mov     rcx, [rsp+28h+arg_10]
0x14001180d  mov     rax, [rcx]
0x140011810  mov     rax, [rax+10h]
0x140011814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011819  xor     eax, eax
0x14001181b  add     rsp, 20h
0x14001181f  pop     rbx
0x140011820  retn
```
