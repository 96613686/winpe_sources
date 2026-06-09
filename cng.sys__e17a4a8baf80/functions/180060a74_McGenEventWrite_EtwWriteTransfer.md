# McGenEventWrite_EtwWriteTransfer

- ea: `0x180060a74`
- end: `0x180060ac8`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `84`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180060ad0`
- `0x180060b58`
- `0x180060c14`
- `0x180060cc4`
- `0x180064988`
- `0x180067f24`

## callees

- `0x180060a74`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x180060ab6`
- `ntoskrnl!EtwWriteTransfer` at `0x180060ab6`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r8
  int v6; // r10d

  v5 = (unsigned __int16 *)a1[1];
  if ( v5 )
  {
    UserData->Ptr = (ULONGLONG)v5;
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
  return EtwWriteTransfer(*a1, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180060a74  sub     rsp, 38h
0x180060a78  mov     r8, [rcx+8]
0x180060a7c  mov     rax, [rsp+38h+arg_20]
0x180060a81  test    r8, r8
0x180060a84  jnz     short loc_180060A8E
0x180060a86  mov     [rax], r8
0x180060a89  xor     r10d, r10d
0x180060a8c  jmp     short loc_180060A9B
0x180060a8e  mov     [rax], r8
0x180060a91  mov     r10d, 2
0x180060a97  movzx   r8d, word ptr [r8]
0x180060a9b  mov     [rax+8], r8d
0x180060a9f  xor     r8d, r8d; ActivityId
0x180060aa2  mov     [rsp+38h+UserData], rax; UserData
0x180060aa7  mov     [rax+0Ch], r10d
0x180060aab  mov     rcx, [rcx]; RegHandle
0x180060aae  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180060ab3  xor     r9d, r9d; RelatedActivityId
0x180060ab6  call    cs:__imp_EtwWriteTransfer
0x180060abd  nop     dword ptr [rax+rax+00h]
0x180060ac2  add     rsp, 38h
0x180060ac6  retn
```
