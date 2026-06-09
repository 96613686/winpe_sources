# NetpAvlTableFreeAllElements

- ea: `0x180037b0c`
- end: `0x180037b39`
- name: `NetpAvlTableFreeAllElements`
- size: `45`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800399dc`
- `0x18003a8f4`

## callees

- `0x180037b0c`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableAvl` at `0x180037b1a`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180037b1a`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180037b2b`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180037b2b`

## pseudocode

```c
PVOID __fastcall NetpAvlTableFreeAllElements(PRTL_AVL_TABLE Table)
{
  PVOID result; // rax

  while ( 1 )
  {
    result = RtlEnumerateGenericTableAvl(Table, 1u);
    if ( !result )
      break;
    RtlDeleteElementGenericTableAvl(Table, result);
  }
  return result;
}

```

## disassembly

```asm
0x180037b0c  push    rbx
0x180037b0e  sub     rsp, 20h
0x180037b12  mov     rbx, rcx
0x180037b15  mov     dl, 1; Restart
0x180037b17  mov     rcx, rbx; Table
0x180037b1a  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180037b20  test    rax, rax
0x180037b23  jz      short loc_180037B33
0x180037b25  mov     rdx, rax; Buffer
0x180037b28  mov     rcx, rbx; Table
0x180037b2b  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180037b31  jmp     short loc_180037B15
0x180037b33  add     rsp, 20h
0x180037b37  pop     rbx
0x180037b38  retn
```
