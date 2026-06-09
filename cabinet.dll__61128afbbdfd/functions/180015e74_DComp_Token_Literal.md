# DComp_Token_Literal

- ea: `0x180015e74`
- end: `0x180015ec5`
- name: `DComp_Token_Literal`
- size: `81`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016288`

## callees

- `0x180015e74`

## pseudocode

```c
__int64 __fastcall DComp_Token_Literal(__int64 a1, char a2)
{
  _BYTE *v2; // rax
  __int64 result; // rax

  ++*(_DWORD *)(a1 + 368);
  --*(_WORD *)(a1 + 380);
  **(_BYTE **)(a1 + 384) = a2;
  v2 = *(_BYTE **)(a1 + 360);
  ++*(_QWORD *)(a1 + 384);
  *v2 = a2;
  result = ++*(_QWORD *)(a1 + 360);
  if ( result == *(_QWORD *)(a1 + 352) )
  {
    result = *(_QWORD *)(a1 + 344);
    *(_QWORD *)(a1 + 360) = result;
  }
  return result;
}

```

## disassembly

```asm
0x180015e74  inc     dword ptr [rcx+170h]
0x180015e7a  mov     eax, 0FFFFh
0x180015e7f  add     [rcx+17Ch], ax
0x180015e86  mov     rax, [rcx+180h]
0x180015e8d  mov     [rax], dl
0x180015e8f  mov     rax, [rcx+168h]
0x180015e96  inc     qword ptr [rcx+180h]
0x180015e9d  mov     [rax], dl
0x180015e9f  inc     qword ptr [rcx+168h]
0x180015ea6  mov     rax, [rcx+168h]
0x180015ead  cmp     rax, [rcx+160h]
0x180015eb4  jnz     short locret_180015EC4
0x180015eb6  mov     rax, [rcx+158h]
0x180015ebd  mov     [rcx+168h], rax
0x180015ec4  retn
```
