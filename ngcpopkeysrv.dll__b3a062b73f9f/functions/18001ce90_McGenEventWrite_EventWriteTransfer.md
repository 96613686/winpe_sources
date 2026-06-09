# McGenEventWrite_EventWriteTransfer

- ea: `0x18001ce90`
- end: `0x18001cedd`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18001a170`
- `0x18001c8d4`
- `0x18001cee4`
- `0x180020c64`
- `0x180020ce0`
- `0x180020d5c`
- `0x180020dd8`

## callees

- `0x18001ce90`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ced2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ced2`

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
0x18001ce90  sub     rsp, 38h
0x18001ce94  mov     r8, [rcx+8]
0x18001ce98  mov     rax, [rsp+38h+arg_20]
0x18001ce9d  test    r8, r8
0x18001cea0  jnz     short loc_18001CEAA
0x18001cea2  mov     [rax], r8
0x18001cea5  xor     r10d, r10d
0x18001cea8  jmp     short loc_18001CEB7
0x18001ceaa  mov     [rax], r8
0x18001cead  mov     r10d, 2
0x18001ceb3  movzx   r8d, word ptr [r8]
0x18001ceb7  mov     [rax+8], r8d
0x18001cebb  xor     r8d, r8d; ActivityId
0x18001cebe  mov     [rsp+38h+UserData], rax; UserData
0x18001cec3  mov     [rax+0Ch], r10d
0x18001cec7  mov     rcx, [rcx]; RegHandle
0x18001ceca  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18001cecf  xor     r9d, r9d; RelatedActivityId
0x18001ced2  call    cs:__imp_EventWriteTransfer
0x18001ced8  add     rsp, 38h
0x18001cedc  retn
```
