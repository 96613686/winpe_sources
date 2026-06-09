# CASFReader::GetScriptCount(ushort *)

- ea: `0x18000a430`
- end: `0x18000a44e`
- name: `?GetScriptCount@CASFReader@@EEAAJPEAG@Z`
- size: `30`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000a430`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::GetScriptCount(CASFReader *this, unsigned __int16 *a2)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 29);
  if ( v2 )
    return (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v2 + 88LL))(v2, a2);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18000a430  mov     rcx, [rcx+0E8h]
0x18000a437  test    rcx, rcx
0x18000a43a  jnz     short loc_18000A442
0x18000a43c  mov     eax, 80004005h
0x18000a441  retn
0x18000a442  mov     rax, [rcx]
0x18000a445  mov     rax, [rax+58h]
0x18000a449  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
