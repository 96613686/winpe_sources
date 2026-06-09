# SetSinkCallbackSecurityBlanket(IUnknown *)

- ea: `0x18000d5e0`
- end: `0x18000d672`
- name: `?SetSinkCallbackSecurityBlanket@@YAJPEAUIUnknown@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(struct IUnknown *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800078ac`
- `0x18000c6e0`
- `0x18000cdd8`
- `0x18000cfd4`

## callees

- `0x18000d5e0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall SetSinkCallbackSecurityBlanket(struct IUnknown *a1)
{
  struct IUnknownVtbl *lpVtbl; // rax
  unsigned int v3; // ebx
  __int64 v5; // [rsp+60h] [rbp+8h] BYREF

  lpVtbl = a1->lpVtbl;
  v5 = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a1,
         &IID_IClientSecurity,
         &v5) >= 0
    && v5 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, __int64, __int64, __int64, _DWORD, int, __int64, int))(*(_QWORD *)v5 + 32LL))(
           v5,
           a1,
           0xFFFFFFFFLL,
           0xFFFFFFFFLL,
           -1,
           0,
           2,
           -1,
           2048);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  else
  {
    return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x18000d5e0  push    rbx
0x18000d5e2  sub     rsp, 50h
0x18000d5e6  mov     rax, [rcx]
0x18000d5e9  lea     r8, [rsp+58h+arg_0]
0x18000d5ee  lea     rdx, IID_IClientSecurity
0x18000d5f5  mov     [rsp+58h+arg_0], 0
0x18000d5fe  mov     rbx, rcx
0x18000d601  mov     rax, [rax]
0x18000d604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d609  test    eax, eax
0x18000d60b  js      short loc_18000D668
0x18000d60d  mov     rcx, [rsp+58h+arg_0]
0x18000d612  test    rcx, rcx
0x18000d615  jz      short loc_18000D668
0x18000d617  mov     rax, [rcx]
0x18000d61a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000d61e  mov     [rsp+58h+var_18], 800h
0x18000d626  or      r8d, 0FFFFFFFFh
0x18000d62a  mov     [rsp+58h+var_20], rdx
0x18000d62f  mov     r9d, r8d
0x18000d632  mov     [rsp+58h+var_28], 2
0x18000d63a  mov     rax, [rax+20h]
0x18000d63e  mov     [rsp+58h+var_30], 0
0x18000d646  mov     [rsp+58h+var_38], rdx
0x18000d64b  mov     rdx, rbx
0x18000d64e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d653  mov     rcx, [rsp+58h+arg_0]
0x18000d658  mov     ebx, eax
0x18000d65a  mov     rdx, [rcx]
0x18000d65d  mov     rax, [rdx+10h]
0x18000d661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d666  jmp     short loc_18000D66A
0x18000d668  xor     ebx, ebx
0x18000d66a  mov     eax, ebx
0x18000d66c  add     rsp, 50h
0x18000d670  pop     rbx
0x18000d671  retn
```
