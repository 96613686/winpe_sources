# McGenEventWrite_EventWriteTransfer

- ea: `0x180004968`
- end: `0x1800049ba`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ae0`
- `0x1800049c0`
- `0x180004a18`
- `0x180005bec`
- `0x180005d00`
- `0x180006240`
- `0x18000650c`
- `0x1800067a0`

## callees

- `0x180004968`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800049af`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800049af`

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

  v5 = (unsigned __int16 *)qword_18001C008;
  if ( qword_18001C008 )
  {
    UserData->Ptr = qword_18001C008;
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
  return EventWriteTransfer(MDM_PUSHROUTER_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180004968  sub     rsp, 38h
0x18000496c  mov     rcx, cs:qword_18001C008
0x180004973  mov     rax, [rsp+38h+arg_20]
0x180004978  test    rcx, rcx
0x18000497b  jnz     short loc_180004985
0x18000497d  mov     [rax], rcx
0x180004980  xor     r8d, r8d
0x180004983  jmp     short loc_180004991
0x180004985  mov     [rax], rcx
0x180004988  mov     r8d, 2
0x18000498e  movzx   ecx, word ptr [rcx]
0x180004991  mov     [rax+8], ecx
0x180004994  mov     [rax+0Ch], r8d
0x180004998  xor     r8d, r8d; ActivityId
0x18000499b  mov     rcx, cs:MDM_PUSHROUTER_Context; RegHandle
0x1800049a2  mov     [rsp+38h+UserData], rax; UserData
0x1800049a7  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800049ac  xor     r9d, r9d; RelatedActivityId
0x1800049af  call    cs:__imp_EventWriteTransfer
0x1800049b5  add     rsp, 38h
0x1800049b9  retn
```
