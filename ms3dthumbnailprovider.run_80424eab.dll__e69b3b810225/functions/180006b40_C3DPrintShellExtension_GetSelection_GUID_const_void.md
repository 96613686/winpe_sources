# C3DPrintShellExtension::GetSelection(_GUID const &,void * *)

- ea: `0x180006b40`
- end: `0x180006b61`
- name: `?GetSelection@C3DPrintShellExtension@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `33`
- prototype: `__int64 __fastcall(C3DPrintShellExtension *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006b40`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall C3DPrintShellExtension::GetSelection(
        C3DPrintShellExtension *this,
        const struct _GUID *a2,
        void **a3)
{
  __int64 (__fastcall ***v3)(_QWORD, const struct _GUID *, void **); // rcx

  v3 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*((_QWORD *)this + 2);
  if ( v3 )
    return (**v3)(v3, a2, a3);
  *a3 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x180006b40  mov     rcx, [rcx+10h]
0x180006b44  test    rcx, rcx
0x180006b47  jz      short loc_180006B54
0x180006b49  mov     rax, [rcx]
0x180006b4c  mov     rax, [rax]
0x180006b4f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180006b54  mov     qword ptr [r8], 0
0x180006b5b  mov     eax, 80004002h
0x180006b60  retn
```
