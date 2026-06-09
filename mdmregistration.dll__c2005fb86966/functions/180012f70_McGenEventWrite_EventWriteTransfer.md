# McGenEventWrite_EventWriteTransfer

- ea: `0x180012f70`
- end: `0x180012fc4`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `84`
- prototype: ``
- caller_count: `46`
- callee_count: `1`
- tags: ``

## callers

- `0x180012fcc`
- `0x1800141b0`
- `0x18001436c`
- `0x180019ec0`
- `0x180019f44`
- `0x18001ed6c`
- `0x1800200b0`
- `0x180020844`
- `0x180020ccc`
- `0x180021458`
- `0x180021e6c`
- `0x180028728`
- `0x180028ee8`
- `0x18002d008`
- `0x18002d0c4`
- `0x18002d464`
- `0x18002eb4c`
- `0x18002f1c4`
- `0x18002f6bc`
- `0x180037174`
- `0x180037b18`
- `0x18003b55c`
- `0x1800416a0`
- `0x18004178c`
- `0x1800418cc`
- `0x1800419b8`
- `0x180041aa4`
- `0x180041b90`
- `0x180041e10`
- `0x180041fb4`
- `0x1800420a0`
- `0x18004218c`
- `0x18004239c`
- `0x180042a5c`
- `0x180042b48`
- `0x180042c34`
- `0x180042ed4`
- `0x1800431d8`
- `0x1800432c4`
- `0x18004342c`
- `0x180043518`
- `0x1800435d0`
- `0x180043f98`
- `0x1800448c4`
- `0x1800449c0`
- `0x180045358`

## callees

- `0x180012f70`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012fb2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012fb2`

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
0x180012f70  sub     rsp, 38h
0x180012f74  mov     r8, [rcx+8]
0x180012f78  mov     rax, [rsp+38h+arg_20]
0x180012f7d  test    r8, r8
0x180012f80  jnz     short loc_180012F8A
0x180012f82  mov     [rax], r8
0x180012f85  xor     r10d, r10d
0x180012f88  jmp     short loc_180012F97
0x180012f8a  mov     [rax], r8
0x180012f8d  mov     r10d, 2
0x180012f93  movzx   r8d, word ptr [r8]
0x180012f97  mov     [rax+8], r8d
0x180012f9b  xor     r8d, r8d; ActivityId
0x180012f9e  mov     [rsp+38h+UserData], rax; UserData
0x180012fa3  mov     [rax+0Ch], r10d
0x180012fa7  mov     rcx, [rcx]; RegHandle
0x180012faa  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180012faf  xor     r9d, r9d; RelatedActivityId
0x180012fb2  call    cs:__imp_EventWriteTransfer
0x180012fb9  nop     dword ptr [rax+rax+00h]
0x180012fbe  add     rsp, 38h
0x180012fc2  retn
```
