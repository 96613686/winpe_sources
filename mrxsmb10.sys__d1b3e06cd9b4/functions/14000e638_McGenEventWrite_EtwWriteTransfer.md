# McGenEventWrite_EtwWriteTransfer

- ea: `0x14000e638`
- end: `0x14000e68e`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `86`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e694`
- `0x14000e708`
- `0x14000fa8c`

## callees

- `0x14000e638`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000e67c`
- `ntoskrnl!EtwWriteTransfer` at `0x14000e67c`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const GUID *a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r10d

  v5 = (unsigned __int16 *)qword_14001F038;
  if ( qword_14001F038 )
  {
    UserData->Ptr = qword_14001F038;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v6 = 0;
  }
  UserData->Size = (unsigned int)v5;
  UserData->Reserved = v6;
  return EtwWriteTransfer(REMOTEFS_SMB_Context, a2, a3, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x14000e638  sub     rsp, 38h
0x14000e63c  mov     rcx, cs:qword_14001F038
0x14000e643  mov     rax, [rsp+38h+arg_20]
0x14000e648  test    rcx, rcx
0x14000e64b  jnz     short loc_14000E655
0x14000e64d  mov     [rax], rcx
0x14000e650  xor     r10d, r10d
0x14000e653  jmp     short loc_14000E661
0x14000e655  mov     [rax], rcx
0x14000e658  mov     r10d, 2
0x14000e65e  movzx   ecx, word ptr [rcx]
0x14000e661  mov     [rax+8], ecx
0x14000e664  mov     [rsp+38h+UserData], rax; UserData
0x14000e669  mov     [rax+0Ch], r10d
0x14000e66d  mov     rcx, cs:REMOTEFS_SMB_Context; RegHandle
0x14000e674  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14000e679  xor     r9d, r9d; RelatedActivityId
0x14000e67c  call    cs:__imp_EtwWriteTransfer
0x14000e683  nop     dword ptr [rax+rax+00h]
0x14000e688  add     rsp, 38h
0x14000e68c  retn
```
