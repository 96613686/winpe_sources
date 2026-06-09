# GetCStatusBarFromDefViewSite(IUnknown *)

- ea: `0x180025bac`
- end: `0x180025c2b`
- name: `?GetCStatusBarFromDefViewSite@@YAPEAVCStatusBar@@PEAUIUnknown@@@Z`
- size: `127`
- prototype: `struct CStatusBar *__fastcall(struct IUnknown *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000f694`
- `0x1800158e8`

## callees

- `0x180025bac`
- `0x180028010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180025bd1`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180025bd1`

## pseudocode

```c
struct CStatusBar *__fastcall GetCStatusBarFromDefViewSite(struct IUnknown *a1)
{
  __int64 v1; // rbx
  void *ppvOut; // [rsp+38h] [rbp+10h] BYREF
  _QWORD *v4; // [rsp+40h] [rbp+18h] BYREF

  v1 = 0;
  v4 = 0;
  ppvOut = 0;
  if ( IUnknown_QueryService(a1, &IID_IShellFolderViewCB, &GUID_2047e320_f2a9_11ce_ae65_08002b2e1262, &ppvOut) >= 0 )
  {
    (**(void (__fastcall ***)(void *, __int64 *, _QWORD **))ppvOut)(ppvOut, &qword_18002C008, &v4);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
  if ( v4 )
  {
    v1 = v4[10];
    (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
  }
  return (struct CStatusBar *)v1;
}

```

## disassembly

```asm
0x180025bac  push    rbx
0x180025bae  sub     rsp, 20h
0x180025bb2  xor     ebx, ebx
0x180025bb4  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x180025bb9  lea     r8, _GUID_2047e320_f2a9_11ce_ae65_08002b2e1262; riid
0x180025bc0  mov     [rsp+28h+arg_10], rbx
0x180025bc5  lea     rdx, IID_IShellFolderViewCB; guidService
0x180025bcc  mov     [rsp+28h+ppvOut], rbx
0x180025bd1  call    cs:__imp_IUnknown_QueryService
0x180025bd7  test    eax, eax
0x180025bd9  js      short loc_180025C08
0x180025bdb  mov     rcx, [rsp+28h+ppvOut]
0x180025be0  lea     r8, [rsp+28h+arg_10]
0x180025be5  lea     rdx, qword_18002C008
0x180025bec  mov     rax, [rcx]
0x180025bef  mov     rax, [rax]
0x180025bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bf7  mov     rcx, [rsp+28h+ppvOut]
0x180025bfc  mov     rax, [rcx]
0x180025bff  mov     rax, [rax+10h]
0x180025c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c08  mov     rcx, [rsp+28h+arg_10]
0x180025c0d  test    rcx, rcx
0x180025c10  jz      short loc_180025C22
0x180025c12  mov     rdx, [rcx]
0x180025c15  mov     rbx, [rcx+50h]
0x180025c19  mov     rax, [rdx+10h]
0x180025c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c22  mov     rax, rbx
0x180025c25  add     rsp, 20h
0x180025c29  pop     rbx
0x180025c2a  retn
```
