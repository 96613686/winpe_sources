# McGenEventWrite_EventWriteTransfer

- ea: `0x180018d08`
- end: `0x180018d5d`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ac80`
- `0x18000adb0`
- `0x18000ae80`
- `0x180018d70`
- `0x180018f10`
- `0x180019050`
- `0x1800191a0`
- `0x180019300`
- `0x1800194e0`
- `0x1800196c0`

## callees

- `0x180018d08`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180018d52`
- `ADVAPI32!EventWriteTransfer` at `0x180018d52`

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

  v5 = (unsigned __int16 *)qword_180030178;
  if ( qword_180030178 )
  {
    UserData->Ptr = qword_180030178;
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
  return EventWriteTransfer(DOCUMENTS_PERFORMANCE_ETW_CONTROL_GUID_Context, a2, 0, 0, 1u, UserData);
}

```

## disassembly

```asm
0x180018d08  sub     rsp, 38h
0x180018d0c  mov     rcx, cs:qword_180030178
0x180018d13  mov     rax, [rsp+38h+arg_20]
0x180018d18  test    rcx, rcx
0x180018d1b  jnz     short loc_180018D25
0x180018d1d  mov     [rax], rcx
0x180018d20  xor     r8d, r8d
0x180018d23  jmp     short loc_180018D31
0x180018d25  mov     [rax], rcx
0x180018d28  mov     r8d, 2
0x180018d2e  movzx   ecx, word ptr [rcx]
0x180018d31  mov     [rax+8], ecx
0x180018d34  xor     r9d, r9d; RelatedActivityId
0x180018d37  mov     [rax+0Ch], r8d
0x180018d3b  xor     r8d, r8d; ActivityId
0x180018d3e  mov     rcx, cs:DOCUMENTS_PERFORMANCE_ETW_CONTROL_GUID_Context; RegHandle
0x180018d45  mov     [rsp+38h+UserData], rax; UserData
0x180018d4a  mov     [rsp+38h+UserDataCount], 1; UserDataCount
0x180018d52  call    cs:__imp_EventWriteTransfer
0x180018d58  add     rsp, 38h
0x180018d5c  retn
```
