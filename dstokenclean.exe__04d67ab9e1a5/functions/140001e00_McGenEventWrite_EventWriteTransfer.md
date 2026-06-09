# McGenEventWrite_EventWriteTransfer

- ea: `0x140001e00`
- end: `0x140001e55`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, __int64, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001e5c`

## callees

- `0x140001e00`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001e4a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001e4a`

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

  v5 = (unsigned __int16 *)qword_140005008;
  if ( qword_140005008 )
  {
    UserData->Ptr = qword_140005008;
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
  return EventWriteTransfer(MICROSOFT_WINDOWSPHONE_DATASHARING_Context, a2, 0, 0, 5u, UserData);
}

```

## disassembly

```asm
0x140001e00  sub     rsp, 38h
0x140001e04  mov     rcx, cs:qword_140005008
0x140001e0b  mov     rax, [rsp+38h+arg_20]
0x140001e10  test    rcx, rcx
0x140001e13  jnz     short loc_140001E1D
0x140001e15  mov     [rax], rcx
0x140001e18  xor     r8d, r8d
0x140001e1b  jmp     short loc_140001E29
0x140001e1d  mov     [rax], rcx
0x140001e20  mov     r8d, 2
0x140001e26  movzx   ecx, word ptr [rcx]
0x140001e29  mov     [rax+8], ecx
0x140001e2c  xor     r9d, r9d; RelatedActivityId
0x140001e2f  mov     [rax+0Ch], r8d
0x140001e33  xor     r8d, r8d; ActivityId
0x140001e36  mov     rcx, cs:MICROSOFT_WINDOWSPHONE_DATASHARING_Context; RegHandle
0x140001e3d  mov     [rsp+38h+UserData], rax; UserData
0x140001e42  mov     [rsp+38h+UserDataCount], 5; UserDataCount
0x140001e4a  call    cs:__imp_EventWriteTransfer
0x140001e50  add     rsp, 38h
0x140001e54  retn
```
