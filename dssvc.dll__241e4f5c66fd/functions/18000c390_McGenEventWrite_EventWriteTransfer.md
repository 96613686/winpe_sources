# McGenEventWrite_EventWriteTransfer

- ea: `0x18000c390`
- end: `0x18000c3dd`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c3e4`
- `0x18000c46c`
- `0x1800184ec`

## callees

- `0x18000c390`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c3d2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c3d2`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
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
  return EventWriteTransfer(*a1, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000c390  sub     rsp, 38h
0x18000c394  mov     r8, [rcx+8]
0x18000c398  mov     rax, [rsp+38h+arg_20]
0x18000c39d  test    r8, r8
0x18000c3a0  jnz     short loc_18000C3AA
0x18000c3a2  mov     [rax], r8
0x18000c3a5  xor     r10d, r10d
0x18000c3a8  jmp     short loc_18000C3B7
0x18000c3aa  mov     [rax], r8
0x18000c3ad  mov     r10d, 2
0x18000c3b3  movzx   r8d, word ptr [r8]
0x18000c3b7  mov     [rax+8], r8d
0x18000c3bb  xor     r8d, r8d; ActivityId
0x18000c3be  mov     [rsp+38h+UserData], rax; UserData
0x18000c3c3  mov     [rax+0Ch], r10d
0x18000c3c7  mov     rcx, [rcx]; RegHandle
0x18000c3ca  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000c3cf  xor     r9d, r9d; RelatedActivityId
0x18000c3d2  call    cs:__imp_EventWriteTransfer
0x18000c3d8  add     rsp, 38h
0x18000c3dc  retn
```
