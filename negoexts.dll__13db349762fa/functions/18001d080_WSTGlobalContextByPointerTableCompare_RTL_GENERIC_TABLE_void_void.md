# WSTGlobalContextByPointerTableCompare(_RTL_GENERIC_TABLE *,void *,void *)

- ea: `0x18001d080`
- end: `0x18001d096`
- name: `?WSTGlobalContextByPointerTableCompare@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_GENERIC_TABLE@@PEAX1@Z`
- size: `22`
- prototype: `RTL_GENERIC_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001d080`

## pseudocode

```c
__int64 __fastcall WSTGlobalContextByPointerTableCompare(
        struct _RTL_GENERIC_TABLE *Table,
        _QWORD *FirstStruct,
        _QWORD *SecondStruct)
{
  if ( *FirstStruct <= *SecondStruct )
    return *FirstStruct < *SecondStruct ? 0 : 2;
  else
    return 1;
}

```

## disassembly

```asm
0x18001d080  mov     rax, [rdx]
0x18001d083  cmp     rax, [r8]
0x18001d086  jbe     short loc_18001D08E
0x18001d088  mov     eax, 1
0x18001d08d  retn
0x18001d08e  sbb     eax, eax
0x18001d090  not     eax
0x18001d092  and     eax, 2
0x18001d095  retn
```
