# Shell3DPrintClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002df0`
- end: `0x180002e6b`
- name: `?CreateInstance@Shell3DPrintClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `123`
- prototype: `__int64 __fastcall(Shell3DPrintClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800033f0`

## callees

- `0x1800029cc`
- `0x180002df0`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Shell3DPrintClassFactory::CreateInstance(
        Shell3DPrintClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v7; // edi
  __int64 (__fastcall ***v8)(_QWORD, const struct _GUID *, void **); // rbx
  __int64 (__fastcall ***v9)(_QWORD, const struct _GUID *, void **); // [rsp+68h] [rbp+20h] BYREF

  if ( !a4 )
    return 2147500035LL;
  v7 = -2147221232;
  *a4 = 0;
  if ( !a2 )
  {
    v7 = -2147024882;
    Microsoft::WRL::Details::Make<C3DPrintShellExtension,>(&v9);
    v8 = v9;
    if ( v9 )
      v7 = (**v9)(v9, a3, a4);
    if ( v8 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v8)[2])(v8);
  }
  return v7;
}

```

## disassembly

```asm
0x180002df0  push    rbx
0x180002df2  push    rbp
0x180002df3  push    rsi
0x180002df4  push    rdi
0x180002df5  sub     rsp, 28h
0x180002df9  mov     rsi, r9
0x180002dfc  mov     rbp, r8
0x180002dff  test    r9, r9
0x180002e02  jnz     short loc_180002E0B
0x180002e04  mov     eax, 80004003h
0x180002e09  jmp     short loc_180002E62
0x180002e0b  mov     edi, 80040110h
0x180002e10  mov     qword ptr [r9], 0
0x180002e17  test    rdx, rdx
0x180002e1a  jnz     short loc_180002E60
0x180002e1c  mov     edi, 8007000Eh
0x180002e21  lea     rcx, [rsp+48h+arg_18]
0x180002e26  call    ??$Make@VC3DPrintShellExtension@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VC3DPrintShellExtension@@@12@XZ; Microsoft::WRL::Details::Make<C3DPrintShellExtension,>(void)
0x180002e2b  mov     rbx, [rsp+48h+arg_18]
0x180002e30  test    rbx, rbx
0x180002e33  jz      short loc_180002E4B
0x180002e35  mov     rax, [rbx]
0x180002e38  mov     r8, rsi
0x180002e3b  mov     rdx, rbp
0x180002e3e  mov     rcx, rbx
0x180002e41  mov     rax, [rax]
0x180002e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e49  mov     edi, eax
0x180002e4b  test    rbx, rbx
0x180002e4e  jz      short loc_180002E60
0x180002e50  mov     rdx, [rbx]
0x180002e53  mov     rcx, rbx
0x180002e56  mov     rax, [rdx+10h]
0x180002e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e5f  nop
0x180002e60  mov     eax, edi
0x180002e62  add     rsp, 28h
0x180002e66  pop     rdi
0x180002e67  pop     rsi
0x180002e68  pop     rbp
0x180002e69  pop     rbx
0x180002e6a  retn
```
