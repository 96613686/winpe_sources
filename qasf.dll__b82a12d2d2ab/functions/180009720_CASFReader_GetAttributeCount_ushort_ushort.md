# CASFReader::GetAttributeCount(ushort,ushort *)

- ea: `0x180009720`
- end: `0x18000973e`
- name: `?GetAttributeCount@CASFReader@@EEAAJGPEAG@Z`
- size: `30`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, unsigned __int16, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009720`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::GetAttributeCount(CASFReader *this, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // rcx

  v3 = *((_QWORD *)this + 29);
  if ( v3 )
    return (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v3 + 24LL))(v3, a2, a3);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x180009720  mov     rcx, [rcx+0E8h]
0x180009727  test    rcx, rcx
0x18000972a  jnz     short loc_180009732
0x18000972c  mov     eax, 80004005h
0x180009731  retn
0x180009732  mov     rax, [rcx]
0x180009735  mov     rax, [rax+18h]
0x180009739  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
