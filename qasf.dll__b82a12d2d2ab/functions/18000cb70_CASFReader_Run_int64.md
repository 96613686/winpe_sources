# CASFReader::Run(__int64)

- ea: `0x18000cb70`
- end: `0x18000cba0`
- name: `?Run@CASFReader@@UEAAJ_J@Z`
- size: `48`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800063a0`
- `0x18000cb70`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::Run(CASFReader *this, __int64 a2)
{
  __int64 v2; // r8

  v2 = *((_QWORD *)this + 55);
  if ( v2 )
    return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v2 + 48LL))(*((_QWORD *)this + 55));
  if ( *((_QWORD *)this + 40) )
    return CBaseFilter::Run(this, a2);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18000cb70  mov     r8, [rcx+1B8h]
0x18000cb77  test    r8, r8
0x18000cb7a  jz      short loc_18000CB8B
0x18000cb7c  mov     rax, [r8]
0x18000cb7f  mov     rcx, r8; this
0x18000cb82  mov     rax, [rax+30h]
0x18000cb86  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb8b  cmp     qword ptr [rcx+140h], 0
0x18000cb93  jnz     short loc_18000CB9B
0x18000cb95  mov     eax, 80004005h
0x18000cb9a  retn
0x18000cb9b  jmp     ?Run@CBaseFilter@@UEAAJ_J@Z; CBaseFilter::Run(__int64)
```
