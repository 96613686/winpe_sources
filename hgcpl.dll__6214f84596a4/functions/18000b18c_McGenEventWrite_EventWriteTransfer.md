# McGenEventWrite_EventWriteTransfer

- ea: `0x18000b18c`
- end: `0x18000b1de`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800076f0`
- `0x18000a9c0`
- `0x18000abc8`
- `0x18000b1e4`
- `0x18000b47c`
- `0x18000eca0`
- `0x180015db8`
- `0x180015e38`

## callees

- `0x18000b18c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b1d3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b1d3`

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

  v5 = (unsigned __int16 *)qword_180029008;
  if ( qword_180029008 )
  {
    UserData->Ptr = qword_180029008;
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
  return EventWriteTransfer(Microsoft_Windows_HomeGroup_ControlPanel_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000b18c  sub     rsp, 38h
0x18000b190  mov     rcx, cs:qword_180029008
0x18000b197  mov     rax, [rsp+38h+arg_20]
0x18000b19c  test    rcx, rcx
0x18000b19f  jnz     short loc_18000B1A9
0x18000b1a1  mov     [rax], rcx
0x18000b1a4  xor     r8d, r8d
0x18000b1a7  jmp     short loc_18000B1B5
0x18000b1a9  mov     [rax], rcx
0x18000b1ac  mov     r8d, 2
0x18000b1b2  movzx   ecx, word ptr [rcx]
0x18000b1b5  mov     [rax+8], ecx
0x18000b1b8  mov     [rax+0Ch], r8d
0x18000b1bc  xor     r8d, r8d; ActivityId
0x18000b1bf  mov     rcx, cs:Microsoft_Windows_HomeGroup_ControlPanel_Context; RegHandle
0x18000b1c6  mov     [rsp+38h+UserData], rax; UserData
0x18000b1cb  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000b1d0  xor     r9d, r9d; RelatedActivityId
0x18000b1d3  call    cs:__imp_EventWriteTransfer
0x18000b1d9  add     rsp, 38h
0x18000b1dd  retn
```
