# McGenEventWrite_EventWriteTransfer

- ea: `0x18000f9e8`
- end: `0x18000fa3d`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, __int64, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000df40`
- `0x180010710`

## callees

- `0x18000f9e8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fa32`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fa32`

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

  v5 = (unsigned __int16 *)qword_18001E008;
  if ( qword_18001E008 )
  {
    UserData->Ptr = qword_18001E008;
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
  return EventWriteTransfer(MICROSOFT_WINDOWS_HOTPATCH_MONITOR_Context, a2, 0, 0, 5u, UserData);
}

```

## disassembly

```asm
0x18000f9e8  sub     rsp, 38h
0x18000f9ec  mov     rcx, cs:qword_18001E008
0x18000f9f3  mov     rax, [rsp+38h+arg_20]
0x18000f9f8  test    rcx, rcx
0x18000f9fb  jnz     short loc_18000FA05
0x18000f9fd  mov     [rax], rcx
0x18000fa00  xor     r8d, r8d
0x18000fa03  jmp     short loc_18000FA11
0x18000fa05  mov     [rax], rcx
0x18000fa08  mov     r8d, 2
0x18000fa0e  movzx   ecx, word ptr [rcx]
0x18000fa11  mov     [rax+8], ecx
0x18000fa14  xor     r9d, r9d; RelatedActivityId
0x18000fa17  mov     [rax+0Ch], r8d
0x18000fa1b  xor     r8d, r8d; ActivityId
0x18000fa1e  mov     rcx, cs:MICROSOFT_WINDOWS_HOTPATCH_MONITOR_Context; RegHandle
0x18000fa25  mov     [rsp+38h+UserData], rax; UserData
0x18000fa2a  mov     [rsp+38h+UserDataCount], 5; UserDataCount
0x18000fa32  call    cs:__imp_EventWriteTransfer
0x18000fa38  add     rsp, 38h
0x18000fa3c  retn
```
