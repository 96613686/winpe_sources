# WfpHashtableDestroy

- ea: `0x1801129f0`
- end: `0x180112a6f`
- name: `WfpHashtableDestroy`
- size: `127`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180058100`
- `0x180064fa0`
- `0x1800842b0`

## callees

- `0x180020c2c`
- `0x1801129f0`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x180112a5e`
- `ntdll!RtlDeleteHashTable` at `0x180112a5e`
- `ntdll!RtlRemoveEntryHashTable` at `0x180112a36`
- `ntdll!RtlRemoveEntryHashTable` at `0x180112a36`
- `ntdll!RtlInitEnumerationHashTable` at `0x180112a20`
- `ntdll!RtlInitEnumerationHashTable` at `0x180112a20`
- `ntdll!RtlEndEnumerationHashTable` at `0x180112a55`
- `ntdll!RtlEndEnumerationHashTable` at `0x180112a55`

## pseudocode

```c
__int64 __fastcall WfpHashtableDestroy(__int64 a1)
{
  _OWORD v3[3]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v4; // [rsp+68h] [rbp+18h] BYREF

  v4 = 0;
  memset(v3, 0, sizeof(v3));
  RtlInitEnumerationHashTable(a1, (char *)v3 + 8);
  *(_QWORD *)&v3[0] = a1;
  while ( (unsigned int)WfpHashtableIteratorGetNext(v3, &v4) )
    RtlRemoveEntryHashTable(a1, v4, 0);
  RtlEndEnumerationHashTable(*(_QWORD *)&v3[0], (char *)v3 + 8);
  return RtlDeleteHashTable(a1);
}

```

## disassembly

```asm
0x1801129f0  mov     [rsp-8+arg_0], rbx
0x1801129f5  mov     [rsp-8+arg_8], rdx
0x1801129fa  push    rbp
0x1801129fb  mov     rbp, rsp
0x1801129fe  sub     rsp, 50h
0x180112a02  xorps   xmm0, xmm0
0x180112a05  mov     [rbp+arg_8], 0
0x180112a0d  lea     rdx, [rbp+var_28]
0x180112a11  mov     rbx, rcx
0x180112a14  movups  xmmword ptr [rbp-30h], xmm0
0x180112a18  movups  [rbp+var_20], xmm0
0x180112a1c  movups  [rbp+var_10], xmm0
0x180112a20  call    cs:__imp_RtlInitEnumerationHashTable
0x180112a26  mov     [rbp+var_30], rbx
0x180112a2a  jmp     short loc_180112A3C
0x180112a2c  mov     rdx, [rbp+arg_8]
0x180112a30  xor     r8d, r8d
0x180112a33  mov     rcx, rbx
0x180112a36  call    cs:__imp_RtlRemoveEntryHashTable
0x180112a3c  lea     rdx, [rbp+arg_8]
0x180112a40  lea     rcx, [rbp+var_30]
0x180112a44  call    WfpHashtableIteratorGetNext
0x180112a49  test    eax, eax
0x180112a4b  jnz     short loc_180112A2C
0x180112a4d  mov     rcx, [rbp+var_30]
0x180112a51  lea     rdx, [rbp+var_28]
0x180112a55  call    cs:__imp_RtlEndEnumerationHashTable
0x180112a5b  mov     rcx, rbx
0x180112a5e  call    cs:__imp_RtlDeleteHashTable
0x180112a64  mov     rbx, [rsp+50h+arg_0]
0x180112a69  add     rsp, 50h
0x180112a6d  pop     rbp
0x180112a6e  retn
```
