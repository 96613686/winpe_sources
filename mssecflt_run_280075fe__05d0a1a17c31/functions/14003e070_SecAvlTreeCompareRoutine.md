# SecAvlTreeCompareRoutine

- ea: `0x14003e070`
- end: `0x14003e0a6`
- name: `SecAvlTreeCompareRoutine`
- size: `54`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14003e070`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14003e084`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14003e084`

## pseudocode

```c
char __fastcall SecAvlTreeCompareRoutine(
        struct _RTL_AVL_TABLE *Table,
        const UNICODE_STRING *FirstStruct,
        const UNICODE_STRING *SecondStruct)
{
  LONG v3; // ecx

  v3 = RtlCompareUnicodeString(FirstStruct, SecondStruct, (BOOLEAN)Table[1].BalancedRoot.Parent);
  if ( v3 )
    return v3 > 0;
  else
    return 2;
}

```

## disassembly

```asm
0x14003e070  sub     rsp, 28h
0x14003e074  mov     rax, r8
0x14003e077  mov     r9, rdx
0x14003e07a  mov     r8b, [rcx+68h]; CaseInSensitive
0x14003e07e  mov     rdx, rax; String2
0x14003e081  mov     rcx, r9; String1
0x14003e084  call    cs:__imp_RtlCompareUnicodeString
0x14003e08b  nop     dword ptr [rax+rax+00h]
0x14003e090  mov     ecx, eax
0x14003e092  xor     eax, eax
0x14003e094  test    ecx, ecx
0x14003e096  jnz     short loc_14003E09D
0x14003e098  lea     eax, [rcx+2]
0x14003e09b  jmp     short loc_14003E0A0
0x14003e09d  setnle  al
0x14003e0a0  add     rsp, 28h
0x14003e0a4  retn
```
