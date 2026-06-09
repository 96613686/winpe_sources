# FwHashtableInsert

- ea: `0x180012220`
- end: `0x180012281`
- name: `FwHashtableInsert`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180004750`
- `0x1800047e0`
- `0x180012220`

## import_xrefs

- `ntdll!RtlInsertEntryHashTable` at `0x180012234`
- `ntdll!RtlInsertEntryHashTable` at `0x180012234`

## string_xrefs

- `0x180012256`: `RtlCreateHashTable`

## pseudocode

```c
__int64 __fastcall FwHashtableInsert(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  unsigned int v3; // ebx
  int v5; // eax
  int v6; // r8d

  v2 = *(_QWORD *)(a2 + 16);
  v3 = 0;
  if ( !v2 )
  {
    v2 = -1;
    *(_QWORD *)(a2 + 16) = -1;
  }
  if ( !(unsigned __int8)RtlInsertEntryHashTable(a1, a2, v2, 0) )
  {
    v5 = FwReportErrorAsWinError((int)"FwHashtableInsert", (__int64)"RtlCreateHashTable", 8);
    v3 = v5;
    if ( v5 < 0 )
      return (unsigned int)FwReportReturnError((int)"FwHashtableInsert", (unsigned int)v5, v6);
  }
  return v3;
}

```

## disassembly

```asm
0x180012220  push    rbx
0x180012222  sub     rsp, 20h
0x180012226  mov     r8, [rdx+10h]
0x18001222a  xor     ebx, ebx
0x18001222c  test    r8, r8
0x18001222f  jz      short loc_180012246
0x180012231  xor     r9d, r9d
0x180012234  call    cs:__imp_RtlInsertEntryHashTable
0x18001223a  test    al, al
0x18001223c  jz      short loc_180012250
0x18001223e  mov     eax, ebx
0x180012240  add     rsp, 20h
0x180012244  pop     rbx
0x180012245  retn
0x180012246  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001224a  mov     [rdx+10h], r8
0x18001224e  jmp     short loc_180012231
0x180012250  mov     r8d, 8
0x180012256  lea     rdx, aRtlcreatehasht; "RtlCreateHashTable"
0x18001225d  lea     rcx, aFwhashtableins_0; "FwHashtableInsert"
0x180012264  call    FwReportErrorAsWinError
0x180012269  mov     ebx, eax
0x18001226b  test    eax, eax
0x18001226d  jns     short loc_18001223E
0x18001226f  mov     edx, eax
0x180012271  lea     rcx, aFwhashtableins_0; "FwHashtableInsert"
0x180012278  call    FwReportReturnError
0x18001227d  mov     ebx, eax
0x18001227f  jmp     short loc_18001223E
```
