# McGenEventWrite_EventWriteTransfer

- ea: `0x180058578`
- end: `0x1800585c5`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800585cc`
- `0x180058628`
- `0x1800586a8`
- `0x18006538c`
- `0x180066a34`
- `0x18006dd84`

## callees

- `0x180058578`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800585ba`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800585ba`

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
0x180058578  sub     rsp, 38h
0x18005857c  mov     r8, [rcx+8]
0x180058580  mov     rax, [rsp+38h+arg_20]
0x180058585  test    r8, r8
0x180058588  jnz     short loc_180058592
0x18005858a  mov     [rax], r8
0x18005858d  xor     r10d, r10d
0x180058590  jmp     short loc_18005859F
0x180058592  mov     [rax], r8
0x180058595  mov     r10d, 2
0x18005859b  movzx   r8d, word ptr [r8]
0x18005859f  mov     [rax+8], r8d
0x1800585a3  xor     r8d, r8d; ActivityId
0x1800585a6  mov     [rsp+38h+UserData], rax; UserData
0x1800585ab  mov     [rax+0Ch], r10d
0x1800585af  mov     rcx, [rcx]; RegHandle
0x1800585b2  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800585b7  xor     r9d, r9d; RelatedActivityId
0x1800585ba  call    cs:__imp_EventWriteTransfer
0x1800585c0  add     rsp, 38h
0x1800585c4  retn
```
