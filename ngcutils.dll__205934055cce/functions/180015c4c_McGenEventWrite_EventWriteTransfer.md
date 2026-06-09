# McGenEventWrite_EventWriteTransfer

- ea: `0x180015c4c`
- end: `0x180015c9e`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800158c4`
- `0x180017718`
- `0x18001b010`
- `0x18001b090`
- `0x18001b18c`

## callees

- `0x180015c4c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180015c93`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180015c93`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_180075048;
  if ( qword_180075048 )
  {
    UserData->Ptr = qword_180075048;
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
  return EventWriteTransfer(MS_PROVIDER_HFB_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180015c4c  sub     rsp, 38h
0x180015c50  mov     rcx, cs:qword_180075048
0x180015c57  mov     rax, [rsp+38h+arg_20]
0x180015c5c  test    rcx, rcx
0x180015c5f  jnz     short loc_180015C69
0x180015c61  mov     [rax], rcx
0x180015c64  xor     r8d, r8d
0x180015c67  jmp     short loc_180015C75
0x180015c69  mov     [rax], rcx
0x180015c6c  mov     r8d, 2
0x180015c72  movzx   ecx, word ptr [rcx]
0x180015c75  mov     [rax+8], ecx
0x180015c78  mov     [rax+0Ch], r8d
0x180015c7c  xor     r8d, r8d; ActivityId
0x180015c7f  mov     rcx, cs:MS_PROVIDER_HFB_Context; RegHandle
0x180015c86  mov     [rsp+38h+UserData], rax; UserData
0x180015c8b  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180015c90  xor     r9d, r9d; RelatedActivityId
0x180015c93  call    cs:__imp_EventWriteTransfer
0x180015c99  add     rsp, 38h
0x180015c9d  retn
```
