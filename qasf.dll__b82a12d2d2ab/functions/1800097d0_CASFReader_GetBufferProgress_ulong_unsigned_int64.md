# CASFReader::GetBufferProgress(ulong *,unsigned __int64 *)

- ea: `0x1800097d0`
- end: `0x1800097f1`
- name: `?GetBufferProgress@CASFReader@@EEAAJPEAKPEA_K@Z`
- size: `33`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, unsigned int *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800097d0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::GetBufferProgress(CASFReader *this, unsigned int *a2, unsigned __int64 *a3)
{
  __int64 v3; // rcx

  v3 = *((_QWORD *)this + 27);
  if ( v3 )
    return (*(__int64 (__fastcall **)(__int64, unsigned int *, unsigned __int64 *))(*(_QWORD *)v3 + 200LL))(v3, a2, a3);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x1800097d0  mov     rcx, [rcx+0D8h]
0x1800097d7  test    rcx, rcx
0x1800097da  jnz     short loc_1800097E2
0x1800097dc  mov     eax, 80004005h
0x1800097e1  retn
0x1800097e2  mov     rax, [rcx]
0x1800097e5  mov     rax, [rax+0C8h]
0x1800097ec  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
