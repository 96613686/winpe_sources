# McGenEventWrite_EventWriteTransfer

- ea: `0x18000b06c`
- end: `0x18000b0c5`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b0cc`
- `0x18000b17c`
- `0x18000b200`
- `0x180011920`

## callees

- `0x18000b06c`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x18000b0b3`
- `ADVAPI32!EventWriteTransfer` at `0x18000b0b3`

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

  v5 = (unsigned __int16 *)qword_18001D058;
  if ( qword_18001D058 )
  {
    UserData->Ptr = qword_18001D058;
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
  return EventWriteTransfer(NDFHCDISC_EVT_GUID_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000b06c  sub     rsp, 38h
0x18000b070  mov     rcx, cs:qword_18001D058
0x18000b077  mov     rax, [rsp+38h+arg_20]
0x18000b07c  test    rcx, rcx
0x18000b07f  jnz     short loc_18000B089
0x18000b081  mov     [rax], rcx
0x18000b084  xor     r8d, r8d
0x18000b087  jmp     short loc_18000B095
0x18000b089  mov     [rax], rcx
0x18000b08c  mov     r8d, 2
0x18000b092  movzx   ecx, word ptr [rcx]
0x18000b095  mov     [rax+8], ecx
0x18000b098  mov     [rax+0Ch], r8d
0x18000b09c  xor     r8d, r8d; ActivityId
0x18000b09f  mov     rcx, cs:NDFHCDISC_EVT_GUID_Context; RegHandle
0x18000b0a6  mov     [rsp+38h+UserData], rax; UserData
0x18000b0ab  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000b0b0  xor     r9d, r9d; RelatedActivityId
0x18000b0b3  call    cs:__imp_EventWriteTransfer
0x18000b0ba  nop     dword ptr [rax+rax+00h]
0x18000b0bf  add     rsp, 38h
0x18000b0c3  retn
```
