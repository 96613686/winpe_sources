# McGenEventWrite_EventWriteTransfer

- ea: `0x18000310c`
- end: `0x180003160`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003170`
- `0x1800133e0`

## callees

- `0x18000310c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000314e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000314e`

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
0x18000310c  sub     rsp, 38h
0x180003110  mov     r8, [rcx+8]
0x180003114  mov     rax, [rsp+38h+arg_20]
0x180003119  test    r8, r8
0x18000311c  jnz     short loc_180003126
0x18000311e  mov     [rax], r8
0x180003121  xor     r10d, r10d
0x180003124  jmp     short loc_180003133
0x180003126  mov     [rax], r8
0x180003129  mov     r10d, 2
0x18000312f  movzx   r8d, word ptr [r8]
0x180003133  mov     [rax+8], r8d
0x180003137  xor     r8d, r8d; ActivityId
0x18000313a  mov     [rsp+38h+UserData], rax; UserData
0x18000313f  mov     [rax+0Ch], r10d
0x180003143  mov     rcx, [rcx]; RegHandle
0x180003146  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000314b  xor     r9d, r9d; RelatedActivityId
0x18000314e  call    cs:__imp_EventWriteTransfer
0x180003155  nop     dword ptr [rax+rax+00h]
0x18000315a  add     rsp, 38h
0x18000315e  retn
```
