# SecRemoveAllElementsFromAvlTree

- ea: `0x14003e3a4`
- end: `0x14003e3e4`
- name: `SecRemoveAllElementsFromAvlTree`
- size: `64`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140009b8c`

## callees

- `0x14003e3a4`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14003e3bb`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14003e3bb`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14003e3cc`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14003e3cc`

## pseudocode

```c
void __fastcall SecRemoveAllElementsFromAvlTree(PRTL_AVL_TABLE Table)
{
  struct _RTL_AVL_TABLE *v1; // rbx
  BOOLEAN i; // dl
  PVOID v3; // rax

  if ( Table )
  {
    v1 = Table;
    for ( i = 1; ; i = 0 )
    {
      v3 = RtlEnumerateGenericTableAvl(Table, i);
      if ( !v3 )
        break;
      RtlDeleteElementGenericTableAvl(v1, v3);
      Table = v1;
    }
  }
}

```

## disassembly

```asm
0x14003e3a4  test    rcx, rcx
0x14003e3a7  jz      short locret_14003E3E2
0x14003e3a9  push    rbx
0x14003e3aa  sub     rsp, 20h
0x14003e3ae  mov     rbx, rcx
0x14003e3b1  mov     dl, 1
0x14003e3b3  jmp     short loc_14003E3CC
0x14003e3b5  mov     rdx, rax; Buffer
0x14003e3b8  mov     rcx, rbx; Table
0x14003e3bb  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14003e3c2  nop     dword ptr [rax+rax+00h]
0x14003e3c7  xor     edx, edx; Restart
0x14003e3c9  mov     rcx, rbx; Table
0x14003e3cc  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14003e3d3  nop     dword ptr [rax+rax+00h]
0x14003e3d8  test    rax, rax
0x14003e3db  jnz     short loc_14003E3B5
0x14003e3dd  add     rsp, 20h
0x14003e3e1  pop     rbx
0x14003e3e2  retn
```
