# ReadBufferRelease(x)

- ea: `0x100169f0`
- end: `0x10016a0a`
- name: `_ReadBufferRelease@4`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10012e70`

## callees

- `0x1001f090`

## pseudocode

```c
int __stdcall ReadBufferRelease(int a1)
{
  TextDestroyDataList(*(_DWORD *)(a1 + 72));
  *(_DWORD *)(a1 + 72) = 0;
  return 0;
}

```

## disassembly

```asm
0x100169f0  push    esi
0x100169f1  mov     esi, [esp+4+arg_0]
0x100169f5  push    dword ptr [esi+48h]
0x100169f8  call    _TextDestroyDataList@4; TextDestroyDataList(x)
0x100169fd  mov     dword ptr [esi+48h], 0
0x10016a04  xor     eax, eax
0x10016a06  pop     esi
0x10016a07  retn    4
```
