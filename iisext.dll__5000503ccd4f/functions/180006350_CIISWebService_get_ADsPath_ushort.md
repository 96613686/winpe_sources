# CIISWebService::get_ADsPath(ushort * *)

- ea: `0x180006350`
- end: `0x18000636b`
- name: `?get_ADsPath@CIISWebService@@UEAAJPEAPEAG@Z`
- size: `27`
- prototype: `__int64 __fastcall(CIISWebService *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180006350`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISWebService::get_ADsPath(CIISWebService *this, unsigned __int16 **a2)
{
  if ( a2 )
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 80LL))(*((_QWORD *)this + 7));
  else
    return 2147500035LL;
}

```

## disassembly

```asm
0x180006350  test    rdx, rdx
0x180006353  jnz     short loc_18000635B
0x180006355  mov     eax, 80004003h
0x18000635a  retn
0x18000635b  mov     rcx, [rcx+38h]
0x18000635f  mov     rax, [rcx]
0x180006362  mov     rax, [rax+50h]
0x180006366  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
