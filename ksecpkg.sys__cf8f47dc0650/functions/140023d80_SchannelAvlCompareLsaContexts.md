# SchannelAvlCompareLsaContexts

- ea: `0x140023d80`
- end: `0x140023da6`
- name: `SchannelAvlCompareLsaContexts`
- size: `38`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140023d80`

## pseudocode

```c
__int64 __fastcall SchannelAvlCompareLsaContexts(
        struct _RTL_AVL_TABLE *Table,
        _DWORD *FirstStruct,
        _DWORD *SecondStruct)
{
  unsigned int v3; // eax
  unsigned int v4; // ecx

  if ( *(_QWORD *)FirstStruct >= *(_QWORD *)SecondStruct )
  {
    if ( *(_QWORD *)FirstStruct > *(_QWORD *)SecondStruct )
      return 1;
    v3 = SecondStruct[4];
    v4 = FirstStruct[4];
    if ( v3 <= v4 )
      return 2 - (unsigned int)(v3 < v4);
  }
  return 0;
}

```

## disassembly

```asm
0x140023d80  mov     rax, [r8]
0x140023d83  cmp     [rdx], rax
0x140023d86  jb      short loc_140023DA3
0x140023d88  ja      short loc_140023D9C
0x140023d8a  mov     eax, [r8+10h]
0x140023d8e  mov     ecx, [rdx+10h]
0x140023d91  cmp     eax, ecx
0x140023d93  ja      short loc_140023DA3
0x140023d95  sbb     eax, eax
0x140023d97  add     eax, 2
0x140023d9a  retn
0x140023d9c  mov     eax, 1
0x140023da1  retn
0x140023da3  xor     eax, eax
0x140023da5  retn
```
