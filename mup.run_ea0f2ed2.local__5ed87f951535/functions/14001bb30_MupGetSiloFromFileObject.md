# MupGetSiloFromFileObject

- ea: `0x14001bb30`
- end: `0x14001bb51`
- name: `MupGetSiloFromFileObject`
- size: `33`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140019944`
- `0x140019cc0`
- `0x140019f60`
- `0x14001a370`
- `0x14001a760`
- `0x14001b860`
- `0x14001ce20`
- `0x14001cff0`
- `0x14001d364`

## callees

- `0x14001bb30`

## import_xrefs

- `ntoskrnl!IoGetSiloParameters` at `0x14001bb34`
- `ntoskrnl!IoGetSiloParameters` at `0x14001bb34`

## pseudocode

```c
__int64 MupGetSiloFromFileObject()
{
  __int64 result; // rax

  result = IoGetSiloParameters();
  if ( result )
    return *(_QWORD *)(result + 8);
  return result;
}

```

## disassembly

```asm
0x14001bb30  sub     rsp, 28h
0x14001bb34  call    cs:__imp_IoGetSiloParameters
0x14001bb3b  nop     dword ptr [rax+rax+00h]
0x14001bb40  test    rax, rax
0x14001bb43  jnz     short loc_14001BB4B
0x14001bb45  add     rsp, 28h
0x14001bb49  retn
0x14001bb4b  mov     rax, [rax+8]
0x14001bb4f  jmp     short loc_14001BB45
```
