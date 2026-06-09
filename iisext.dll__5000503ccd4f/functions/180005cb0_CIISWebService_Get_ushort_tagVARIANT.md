# CIISWebService::Get(ushort *,tagVARIANT *)

- ea: `0x180005cb0`
- end: `0x180005cd0`
- name: `?Get@CIISWebService@@UEAAJPEAGPEAUtagVARIANT@@@Z`
- size: `32`
- prototype: `__int64 __fastcall(CIISWebService *__hidden this, unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180005cb0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISWebService::Get(CIISWebService *this, unsigned __int16 *a2, struct tagVARIANT *a3)
{
  if ( a2 && a3 )
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 120LL))(*((_QWORD *)this + 7));
  else
    return 2147500035LL;
}

```

## disassembly

```asm
0x180005cb0  test    rdx, rdx
0x180005cb3  jz      short loc_180005CCA
0x180005cb5  test    r8, r8
0x180005cb8  jz      short loc_180005CCA
0x180005cba  mov     rcx, [rcx+38h]
0x180005cbe  mov     rax, [rcx]
0x180005cc1  mov     rax, [rax+78h]
0x180005cc5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180005cca  mov     eax, 80004003h
0x180005ccf  retn
```
