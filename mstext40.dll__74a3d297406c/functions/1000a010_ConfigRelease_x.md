# ConfigRelease(x)

- ea: `0x1000a010`
- end: `0x1000a039`
- name: `_ConfigRelease@4`
- size: `41`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x100148d0`
- `0x10015100`
- `0x100151e0`

## callees

- `0x1000a010`
- `0x1000b200`

## pseudocode

```c
int __stdcall ConfigRelease(_DWORD **a1)
{
  _DWORD *v1; // eax
  _DWORD *v2; // esi

  v1 = *a1;
  if ( *a1 )
  {
    do
    {
      v2 = (_DWORD *)*v1;
      MemFree(v1);
      v1 = v2;
    }
    while ( v2 );
  }
  return MemFree(a1);
}

```

## disassembly

```asm
0x1000a010  push    edi
0x1000a011  mov     edi, [esp+4+arg_0]
0x1000a015  mov     eax, [edi]
0x1000a017  test    eax, eax
0x1000a019  jz      short loc_1000A02F
0x1000a01b  push    esi
0x1000a01c  lea     esp, [esp+0]
0x1000a020  mov     esi, [eax]
0x1000a022  push    eax
0x1000a023  call    _MemFree@4; MemFree(x)
0x1000a028  mov     eax, esi
0x1000a02a  test    esi, esi
0x1000a02c  jnz     short loc_1000A020
0x1000a02e  pop     esi
0x1000a02f  push    edi
0x1000a030  call    _MemFree@4; MemFree(x)
0x1000a035  pop     edi
0x1000a036  retn    4
```
