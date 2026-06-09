# McGenEventWrite_EventWriteTransfer

- ea: `0x180006d00`
- end: `0x180006d55`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, __int64, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800068ec`
- `0x1800069fc`
- `0x180006b00`
- `0x180006e90`

## callees

- `0x180006d00`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006d4a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006d4a`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  ULONG v6; // r8d

  v5 = (unsigned __int16 *)qword_180011008;
  if ( qword_180011008 )
  {
    UserData->Ptr = qword_180011008;
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
  return EventWriteTransfer(HostGuardianServiceClientEventSource_Context, a2, 0, 0, 2u, UserData);
}

```

## disassembly

```asm
0x180006d00  sub     rsp, 38h
0x180006d04  mov     rcx, cs:qword_180011008
0x180006d0b  mov     r9d, 2
0x180006d11  mov     rax, [rsp+38h+arg_20]
0x180006d16  test    rcx, rcx
0x180006d19  jnz     short loc_180006D23
0x180006d1b  mov     [rax], rcx
0x180006d1e  xor     r8d, r8d
0x180006d21  jmp     short loc_180006D2C
0x180006d23  mov     [rax], rcx
0x180006d26  mov     r8d, r9d
0x180006d29  movzx   ecx, word ptr [rcx]
0x180006d2c  mov     [rax+8], ecx
0x180006d2f  mov     [rax+0Ch], r8d
0x180006d33  xor     r8d, r8d; ActivityId
0x180006d36  mov     rcx, cs:HostGuardianServiceClientEventSource_Context; RegHandle
0x180006d3d  mov     [rsp+38h+UserData], rax; UserData
0x180006d42  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180006d47  xor     r9d, r9d; RelatedActivityId
0x180006d4a  call    cs:__imp_EventWriteTransfer
0x180006d50  add     rsp, 38h
0x180006d54  retn
```
