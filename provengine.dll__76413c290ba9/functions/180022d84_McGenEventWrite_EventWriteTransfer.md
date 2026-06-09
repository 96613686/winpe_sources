# McGenEventWrite_EventWriteTransfer

- ea: `0x180022d84`
- end: `0x180022dd6`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18001240c`
- `0x180018f74`
- `0x18001b700`
- `0x180022ddc`
- `0x180022e78`
- `0x180039828`

## callees

- `0x180022d84`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180022dcb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180022dcb`

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

  v5 = (unsigned __int16 *)qword_18005A048;
  if ( qword_18005A048 )
  {
    UserData->Ptr = qword_18005A048;
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
  return EventWriteTransfer(PROVISIONING_DIAGNOSTICS_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180022d84  sub     rsp, 38h
0x180022d88  mov     rcx, cs:qword_18005A048
0x180022d8f  mov     rax, [rsp+38h+arg_20]
0x180022d94  test    rcx, rcx
0x180022d97  jnz     short loc_180022DA1
0x180022d99  mov     [rax], rcx
0x180022d9c  xor     r8d, r8d
0x180022d9f  jmp     short loc_180022DAD
0x180022da1  mov     [rax], rcx
0x180022da4  mov     r8d, 2
0x180022daa  movzx   ecx, word ptr [rcx]
0x180022dad  mov     [rax+8], ecx
0x180022db0  mov     [rax+0Ch], r8d
0x180022db4  xor     r8d, r8d; ActivityId
0x180022db7  mov     rcx, cs:PROVISIONING_DIAGNOSTICS_Context; RegHandle
0x180022dbe  mov     [rsp+38h+UserData], rax; UserData
0x180022dc3  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180022dc8  xor     r9d, r9d; RelatedActivityId
0x180022dcb  call    cs:__imp_EventWriteTransfer
0x180022dd1  add     rsp, 38h
0x180022dd5  retn
```
