# McGenEventWrite_EventWriteTransfer

- ea: `0x18000a850`
- end: `0x18000a8a2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800060b0`
- `0x180007b9c`
- `0x1800082c0`
- `0x180008390`
- `0x18000947c`
- `0x18000993c`

## callees

- `0x18000a850`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a897`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a897`

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

  v5 = (unsigned __int16 *)qword_18001B0A8;
  if ( qword_18001B0A8 )
  {
    UserData->Ptr = qword_18001B0A8;
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
  return EventWriteTransfer(MDM_ENTERPRISE_DIAGNOSTICS_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000a850  sub     rsp, 38h
0x18000a854  mov     rcx, cs:qword_18001B0A8
0x18000a85b  mov     rax, [rsp+38h+arg_20]
0x18000a860  test    rcx, rcx
0x18000a863  jnz     short loc_18000A86D
0x18000a865  mov     [rax], rcx
0x18000a868  xor     r8d, r8d
0x18000a86b  jmp     short loc_18000A879
0x18000a86d  mov     [rax], rcx
0x18000a870  mov     r8d, 2
0x18000a876  movzx   ecx, word ptr [rcx]
0x18000a879  mov     [rax+8], ecx
0x18000a87c  mov     [rax+0Ch], r8d
0x18000a880  xor     r8d, r8d; ActivityId
0x18000a883  mov     rcx, cs:MDM_ENTERPRISE_DIAGNOSTICS_Context; RegHandle
0x18000a88a  mov     [rsp+38h+UserData], rax; UserData
0x18000a88f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000a894  xor     r9d, r9d; RelatedActivityId
0x18000a897  call    cs:__imp_EventWriteTransfer
0x18000a89d  add     rsp, 38h
0x18000a8a1  retn
```
