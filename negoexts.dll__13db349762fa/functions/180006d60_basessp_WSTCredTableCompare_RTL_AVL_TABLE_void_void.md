# basessp::WSTCredTableCompare(_RTL_AVL_TABLE *,void *,void *)

- ea: `0x180006d60`
- end: `0x180006d9c`
- name: `?WSTCredTableCompare@basessp@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z`
- size: `60`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006d60`
- `0x180006db0`

## pseudocode

```c
__int64 __fastcall basessp::WSTCredTableCompare(
        struct _RTL_AVL_TABLE *Table,
        basessp **FirstStruct,
        struct basessp::_WST_CREDENTIAL **SecondStruct)
{
  int v3; // eax
  unsigned int v5; // ecx

  if ( *FirstStruct == *SecondStruct )
    return 2;
  v3 = basessp::WSTCompareCreds(*FirstStruct, *SecondStruct, (struct basessp::_WST_CREDENTIAL *)SecondStruct);
  if ( v3 > 0 )
    return 1;
  v5 = 2;
  if ( v3 < 0 )
    return 0;
  return v5;
}

```

## disassembly

```asm
0x180006d60  sub     rsp, 28h
0x180006d64  mov     rax, [r8]
0x180006d67  mov     rcx, [rdx]; this
0x180006d6a  cmp     rcx, rax
0x180006d6d  jz      short loc_180006D85
0x180006d6f  mov     rdx, rax; struct basessp::_WST_CREDENTIAL *
0x180006d72  call    ?WSTCompareCreds@basessp@@YAHPEAU_WST_CREDENTIAL@1@0@Z; basessp::WSTCompareCreds(basessp::_WST_CREDENTIAL *,basessp::_WST_CREDENTIAL *)
0x180006d77  test    eax, eax
0x180006d79  jle     short loc_180006D8C
0x180006d7b  mov     eax, 1
0x180006d80  add     rsp, 28h
0x180006d84  retn
0x180006d85  mov     eax, 2
0x180006d8a  jmp     short loc_180006D80
0x180006d8c  xor     edx, edx
0x180006d8e  mov     ecx, 2
0x180006d93  test    eax, eax
0x180006d95  cmovs   ecx, edx
0x180006d98  mov     eax, ecx
0x180006d9a  jmp     short loc_180006D80
```
