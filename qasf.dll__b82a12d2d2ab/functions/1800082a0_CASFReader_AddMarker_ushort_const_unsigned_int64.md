# CASFReader::AddMarker(ushort const *,unsigned __int64)

- ea: `0x1800082a0`
- end: `0x1800082be`
- name: `?AddMarker@CASFReader@@EEAAJPEBG_K@Z`
- size: `30`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800082a0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::AddMarker(CASFReader *this, const unsigned __int16 *a2)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 29);
  if ( v2 )
    return (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v2 + 72LL))(v2, a2);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x1800082a0  mov     rcx, [rcx+0E8h]
0x1800082a7  test    rcx, rcx
0x1800082aa  jnz     short loc_1800082B2
0x1800082ac  mov     eax, 80004005h
0x1800082b1  retn
0x1800082b2  mov     rax, [rcx]
0x1800082b5  mov     rax, [rax+48h]
0x1800082b9  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
