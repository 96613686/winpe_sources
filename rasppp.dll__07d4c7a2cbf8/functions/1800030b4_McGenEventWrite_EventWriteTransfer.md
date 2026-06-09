# McGenEventWrite_EventWriteTransfer

- ea: `0x1800030b4`
- end: `0x180003101`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003110`
- `0x180012d20`

## callees

- `0x1800030b4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800030f6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800030f6`

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
0x1800030b4  sub     rsp, 38h
0x1800030b8  mov     r8, [rcx+8]
0x1800030bc  mov     rax, [rsp+38h+arg_20]
0x1800030c1  test    r8, r8
0x1800030c4  jnz     short loc_1800030CE
0x1800030c6  mov     [rax], r8
0x1800030c9  xor     r10d, r10d
0x1800030cc  jmp     short loc_1800030DB
0x1800030ce  mov     [rax], r8
0x1800030d1  mov     r10d, 2
0x1800030d7  movzx   r8d, word ptr [r8]
0x1800030db  mov     [rax+8], r8d
0x1800030df  xor     r8d, r8d; ActivityId
0x1800030e2  mov     [rsp+38h+UserData], rax; UserData
0x1800030e7  mov     [rax+0Ch], r10d
0x1800030eb  mov     rcx, [rcx]; RegHandle
0x1800030ee  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800030f3  xor     r9d, r9d; RelatedActivityId
0x1800030f6  call    cs:__imp_EventWriteTransfer
0x1800030fc  add     rsp, 38h
0x180003100  retn
```
