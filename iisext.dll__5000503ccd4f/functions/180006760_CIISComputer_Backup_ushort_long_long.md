# CIISComputer::Backup(ushort *,long,long)

- ea: `0x180006760`
- end: `0x180006788`
- name: `?Backup@CIISComputer@@UEAAJPEAGJJ@Z`
- size: `40`
- prototype: `__int64 __fastcall(CIISComputer *this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006760`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISComputer::Backup(CIISComputer *this, unsigned __int16 *a2)
{
  if ( a2 )
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 224LL))(*((_QWORD *)this + 15));
  else
    return 2147500035LL;
}

```

## disassembly

```asm
0x180006760  sub     rsp, 38h
0x180006764  test    rdx, rdx
0x180006767  jnz     short loc_180006770
0x180006769  mov     eax, 80004003h
0x18000676e  jmp     short loc_180006783
0x180006770  mov     rcx, [rcx+78h]
0x180006774  mov     rax, [rcx]
0x180006777  mov     rax, [rax+0E0h]
0x18000677e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006783  add     rsp, 38h
0x180006787  retn
```
