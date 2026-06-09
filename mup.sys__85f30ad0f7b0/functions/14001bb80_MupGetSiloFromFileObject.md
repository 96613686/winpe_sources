# MupGetSiloFromFileObject

- ea: `0x14001bb80`
- end: `0x14001bba1`
- name: `MupGetSiloFromFileObject`
- size: `33`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140019994`
- `0x140019d10`
- `0x140019fb0`
- `0x14001a3c0`
- `0x14001a7b0`
- `0x14001b8b0`
- `0x14001ce70`
- `0x14001d040`
- `0x14001d3b4`

## callees

- `0x14001bb80`

## import_xrefs

- `ntoskrnl!IoGetSiloParameters` at `0x14001bb84`
- `ntoskrnl!IoGetSiloParameters` at `0x14001bb84`

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
0x14001bb80  sub     rsp, 28h
0x14001bb84  call    cs:__imp_IoGetSiloParameters
0x14001bb8b  nop     dword ptr [rax+rax+00h]
0x14001bb90  test    rax, rax
0x14001bb93  jnz     short loc_14001BB9B
0x14001bb95  add     rsp, 28h
0x14001bb99  retn
0x14001bb9b  mov     rax, [rax+8]
0x14001bb9f  jmp     short loc_14001BB95
```
