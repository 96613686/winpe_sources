# CASFReader::GetMarkerCount(ushort *)

- ea: `0x180009b10`
- end: `0x180009b2e`
- name: `?GetMarkerCount@CASFReader@@EEAAJPEAG@Z`
- size: `30`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009b10`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::GetMarkerCount(CASFReader *this, unsigned __int16 *a2)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 29);
  if ( v2 )
    return (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v2 + 56LL))(v2, a2);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x180009b10  mov     rcx, [rcx+0E8h]
0x180009b17  test    rcx, rcx
0x180009b1a  jnz     short loc_180009B22
0x180009b1c  mov     eax, 80004005h
0x180009b21  retn
0x180009b22  mov     rax, [rcx]
0x180009b25  mov     rax, [rax+38h]
0x180009b29  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
