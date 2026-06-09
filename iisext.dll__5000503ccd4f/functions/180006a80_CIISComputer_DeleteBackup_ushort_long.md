# CIISComputer::DeleteBackup(ushort *,long)

- ea: `0x180006a80`
- end: `0x180006a9e`
- name: `?DeleteBackup@CIISComputer@@UEAAJPEAGJ@Z`
- size: `30`
- prototype: `__int64 __fastcall(CIISComputer *this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006a80`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISComputer::DeleteBackup(CIISComputer *this, unsigned __int16 *a2)
{
  if ( a2 )
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 248LL))(*((_QWORD *)this + 15));
  else
    return 2147500035LL;
}

```

## disassembly

```asm
0x180006a80  test    rdx, rdx
0x180006a83  jnz     short loc_180006A8B
0x180006a85  mov     eax, 80004003h
0x180006a8a  retn
0x180006a8b  mov     rcx, [rcx+78h]
0x180006a8f  mov     rax, [rcx]
0x180006a92  mov     rax, [rax+0F8h]
0x180006a99  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
