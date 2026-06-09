# CscStringTablepDeleteTable

- ea: `0x140020c7c`
- end: `0x140020cc4`
- name: `CscStringTablepDeleteTable`
- size: `72`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140051df8`
- `0x14008e628`

## callees

- `0x140020c7c`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140020c9e`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140020c9e`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140020c8c`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140020c8c`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x140020cad`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x140020cad`

## pseudocode

```c
BOOLEAN __fastcall CscStringTablepDeleteTable(PRTL_AVL_TABLE Table)
{
  struct _RTL_AVL_TABLE *i; // rbx
  PVOID v2; // rax
  BOOLEAN result; // al

  for ( i = Table; ; Table = i )
  {
    result = RtlIsGenericTableEmptyAvl(Table);
    if ( result )
      break;
    v2 = RtlEnumerateGenericTableAvl(i, 1u);
    RtlDeleteElementGenericTableAvl(i, v2);
  }
  return result;
}

```

## disassembly

```asm
0x140020c7c  push    rbx
0x140020c7e  sub     rsp, 20h
0x140020c82  mov     rbx, rcx
0x140020c85  jmp     short loc_140020CAD
0x140020c87  mov     dl, 1; Restart
0x140020c89  mov     rcx, rbx; Table
0x140020c8c  call    cs:__imp_RtlEnumerateGenericTableAvl
0x140020c93  nop     dword ptr [rax+rax+00h]
0x140020c98  mov     rdx, rax; Buffer
0x140020c9b  mov     rcx, rbx; Table
0x140020c9e  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140020ca5  nop     dword ptr [rax+rax+00h]
0x140020caa  mov     rcx, rbx; Table
0x140020cad  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x140020cb4  nop     dword ptr [rax+rax+00h]
0x140020cb9  test    al, al
0x140020cbb  jz      short loc_140020C87
0x140020cbd  add     rsp, 20h
0x140020cc1  pop     rbx
0x140020cc2  retn
```
