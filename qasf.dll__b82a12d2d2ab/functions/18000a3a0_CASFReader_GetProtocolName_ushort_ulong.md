# CASFReader::GetProtocolName(ushort *,ulong *)

- ea: `0x18000a3a0`
- end: `0x18000a3c1`
- name: `?GetProtocolName@CASFReader@@EEAAJPEAGPEAK@Z`
- size: `33`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000a3a0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::GetProtocolName(CASFReader *this, unsigned __int16 *a2, unsigned int *a3)
{
  __int64 v3; // rcx

  v3 = *((_QWORD *)this + 27);
  if ( v3 )
    return (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned int *))(*(_QWORD *)v3 + 232LL))(v3, a2, a3);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18000a3a0  mov     rcx, [rcx+0D8h]
0x18000a3a7  test    rcx, rcx
0x18000a3aa  jnz     short loc_18000A3B2
0x18000a3ac  mov     eax, 80004005h
0x18000a3b1  retn
0x18000a3b2  mov     rax, [rcx]
0x18000a3b5  mov     rax, [rax+0E8h]
0x18000a3bc  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
