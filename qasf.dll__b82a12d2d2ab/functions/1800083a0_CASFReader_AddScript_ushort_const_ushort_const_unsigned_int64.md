# CASFReader::AddScript(ushort const *,ushort const *,unsigned __int64)

- ea: `0x1800083a0`
- end: `0x1800083c8`
- name: `?AddScript@CASFReader@@EEAAJPEBG0_K@Z`
- size: `40`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800083a0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::AddScript(CASFReader *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 v3; // rcx

  v3 = *((_QWORD *)this + 29);
  if ( v3 )
    return (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)v3 + 104LL))(
             v3,
             a2,
             a3);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x1800083a0  sub     rsp, 38h
0x1800083a4  mov     rcx, [rcx+0E8h]
0x1800083ab  test    rcx, rcx
0x1800083ae  jnz     short loc_1800083B7
0x1800083b0  mov     eax, 80004005h
0x1800083b5  jmp     short loc_1800083C3
0x1800083b7  mov     rax, [rcx]
0x1800083ba  mov     rax, [rax+68h]
0x1800083be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083c3  add     rsp, 38h
0x1800083c7  retn
```
