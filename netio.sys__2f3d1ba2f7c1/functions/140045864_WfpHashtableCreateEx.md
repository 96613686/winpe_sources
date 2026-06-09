# WfpHashtableCreateEx

- ea: `0x140045864`
- end: `0x1400458c1`
- name: `WfpHashtableCreateEx`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14004582c`

## callees

- `0x140009520`
- `0x140009e00`
- `0x140045864`

## import_xrefs

- `ntoskrnl!RtlCreateHashTable` at `0x14004587a`
- `ntoskrnl!RtlCreateHashTable` at `0x14004587a`

## string_xrefs

- `0x140045894`: `RtlCreateHashTable`
- `0x1400458a8`: `WfpHashtableCreateEx`

## pseudocode

```c
__int64 __fastcall WfpHashtableCreateEx(__int64 a1, struct _RTL_DYNAMIC_HASH_TABLE *a2)
{
  __int64 v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // rax
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+38h] [rbp+10h] BYREF

  HashTable = a2;
  v2 = 0;
  if ( !RtlCreateHashTable(&HashTable, 0, 0) )
  {
    v4 = WfpReportSysErrorAsNtStatus(v3, "RtlCreateHashTable", 3221225495LL, 1);
    v2 = v4;
    if ( v4 )
      WfpReportError(v4, "WfpHashtableCreateEx");
  }
  return v2;
}

```

## disassembly

```asm
0x140045864  mov     [rsp+HashTable], rdx
0x140045869  push    rbx
0x14004586a  sub     rsp, 20h
0x14004586e  xor     r8d, r8d; Flags
0x140045871  lea     rcx, [rsp+28h+HashTable]; HashTable
0x140045876  xor     edx, edx; Shift
0x140045878  xor     ebx, ebx
0x14004587a  call    cs:__imp_RtlCreateHashTable
0x140045881  nop     dword ptr [rax+rax+00h]
0x140045886  test    al, al
0x140045888  jnz     short loc_1400458B7
0x14004588a  lea     r9d, [rbx+1]
0x14004588e  mov     r8d, 0C0000017h
0x140045894  lea     rdx, aRtlcreatehasht; "RtlCreateHashTable"
0x14004589b  call    WfpReportSysErrorAsNtStatus
0x1400458a0  mov     rbx, rax
0x1400458a3  test    rax, rax
0x1400458a6  jz      short loc_1400458B7
0x1400458a8  lea     rdx, aWfphashtablecr_0; "WfpHashtableCreateEx"
0x1400458af  mov     rcx, rax
0x1400458b2  call    WfpReportError
0x1400458b7  mov     rax, rbx
0x1400458ba  add     rsp, 20h
0x1400458be  pop     rbx
0x1400458bf  retn
```
