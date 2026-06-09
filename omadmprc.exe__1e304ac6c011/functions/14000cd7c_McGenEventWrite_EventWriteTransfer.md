# McGenEventWrite_EventWriteTransfer

- ea: `0x14000cd7c`
- end: `0x14000cdd5`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b860`
- `0x14000c718`
- `0x14000cbf8`
- `0x14000cddc`
- `0x14000ce84`
- `0x14000cf44`
- `0x14000d024`
- `0x14000d108`
- `0x14000d238`
- `0x14000d380`
- `0x14000d4e8`
- `0x140012604`
- `0x1400141a0`

## callees

- `0x14000cd7c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000cdc3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000cdc3`

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

  v5 = (unsigned __int16 *)qword_140023128;
  if ( qword_140023128 )
  {
    UserData->Ptr = qword_140023128;
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
0x14000cd7c  sub     rsp, 38h
0x14000cd80  mov     rcx, cs:qword_140023128
0x14000cd87  mov     rax, [rsp+38h+arg_20]
0x14000cd8c  test    rcx, rcx
0x14000cd8f  jnz     short loc_14000CD99
0x14000cd91  mov     [rax], rcx
0x14000cd94  xor     r8d, r8d
0x14000cd97  jmp     short loc_14000CDA5
0x14000cd99  mov     [rax], rcx
0x14000cd9c  mov     r8d, 2
0x14000cda2  movzx   ecx, word ptr [rcx]
0x14000cda5  mov     [rax+8], ecx
0x14000cda8  mov     [rax+0Ch], r8d
0x14000cdac  xor     r8d, r8d; ActivityId
0x14000cdaf  mov     rcx, cs:MDM_ENTERPRISE_DIAGNOSTICS_Context; RegHandle
0x14000cdb6  mov     [rsp+38h+UserData], rax; UserData
0x14000cdbb  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14000cdc0  xor     r9d, r9d; RelatedActivityId
0x14000cdc3  call    cs:__imp_EventWriteTransfer
0x14000cdca  nop     dword ptr [rax+rax+00h]
0x14000cdcf  add     rsp, 38h
0x14000cdd3  retn
```
