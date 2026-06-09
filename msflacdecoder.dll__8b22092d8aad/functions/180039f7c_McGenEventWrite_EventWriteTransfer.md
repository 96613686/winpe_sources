# McGenEventWrite_EventWriteTransfer

- ea: `0x180039f7c`
- end: `0x180039fc9`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180039fd0`
- `0x18003f2f4`
- `0x18003f36c`
- `0x1800504d4`
- `0x180050544`

## callees

- `0x180039f7c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180039fbe`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180039fbe`

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
0x180039f7c  sub     rsp, 38h
0x180039f80  mov     r8, [rcx+8]
0x180039f84  mov     rax, [rsp+38h+arg_20]
0x180039f89  test    r8, r8
0x180039f8c  jnz     short loc_180039F96
0x180039f8e  mov     [rax], r8
0x180039f91  xor     r10d, r10d
0x180039f94  jmp     short loc_180039FA3
0x180039f96  mov     [rax], r8
0x180039f99  mov     r10d, 2
0x180039f9f  movzx   r8d, word ptr [r8]
0x180039fa3  mov     [rax+8], r8d
0x180039fa7  xor     r8d, r8d; ActivityId
0x180039faa  mov     [rsp+38h+UserData], rax; UserData
0x180039faf  mov     [rax+0Ch], r10d
0x180039fb3  mov     rcx, [rcx]; RegHandle
0x180039fb6  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180039fbb  xor     r9d, r9d; RelatedActivityId
0x180039fbe  call    cs:__imp_EventWriteTransfer
0x180039fc4  add     rsp, 38h
0x180039fc8  retn
```
