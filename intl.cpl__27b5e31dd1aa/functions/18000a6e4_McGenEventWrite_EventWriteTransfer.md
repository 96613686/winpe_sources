# McGenEventWrite_EventWriteTransfer

- ea: `0x18000a6e4`
- end: `0x18000a736`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800096fc`
- `0x18000a73c`
- `0x180027958`
- `0x180029328`

## callees

- `0x18000a6e4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a72b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a72b`

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

  v5 = (unsigned __int16 *)qword_18003A098;
  if ( qword_18003A098 )
  {
    UserData->Ptr = qword_18003A098;
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
  return EventWriteTransfer(RLOUI_ETW_PROVIDER_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000a6e4  sub     rsp, 38h
0x18000a6e8  mov     rcx, cs:qword_18003A098
0x18000a6ef  mov     rax, [rsp+38h+arg_20]
0x18000a6f4  test    rcx, rcx
0x18000a6f7  jnz     short loc_18000A701
0x18000a6f9  mov     [rax], rcx
0x18000a6fc  xor     r8d, r8d
0x18000a6ff  jmp     short loc_18000A70D
0x18000a701  mov     [rax], rcx
0x18000a704  mov     r8d, 2
0x18000a70a  movzx   ecx, word ptr [rcx]
0x18000a70d  mov     [rax+8], ecx
0x18000a710  mov     [rax+0Ch], r8d
0x18000a714  xor     r8d, r8d; ActivityId
0x18000a717  mov     rcx, cs:RLOUI_ETW_PROVIDER_Context; RegHandle
0x18000a71e  mov     [rsp+38h+UserData], rax; UserData
0x18000a723  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000a728  xor     r9d, r9d; RelatedActivityId
0x18000a72b  call    cs:__imp_EventWriteTransfer
0x18000a731  add     rsp, 38h
0x18000a735  retn
```
