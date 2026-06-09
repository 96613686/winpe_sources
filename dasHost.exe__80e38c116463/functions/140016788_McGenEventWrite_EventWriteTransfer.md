# McGenEventWrite_EventWriteTransfer

- ea: `0x140016788`
- end: `0x1400167dd`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, __int64, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400167e4`

## callees

- `0x140016788`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400167d2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400167d2`

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

  v5 = (unsigned __int16 *)qword_140029008;
  if ( qword_140029008 )
  {
    UserData->Ptr = qword_140029008;
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
  return EventWriteTransfer(das_Context, a2, 0, 0, 3u, UserData);
}

```

## disassembly

```asm
0x140016788  sub     rsp, 38h
0x14001678c  mov     rcx, cs:qword_140029008
0x140016793  mov     rax, [rsp+38h+arg_20]
0x140016798  test    rcx, rcx
0x14001679b  jnz     short loc_1400167A5
0x14001679d  mov     [rax], rcx
0x1400167a0  xor     r8d, r8d
0x1400167a3  jmp     short loc_1400167B1
0x1400167a5  mov     [rax], rcx
0x1400167a8  mov     r8d, 2
0x1400167ae  movzx   ecx, word ptr [rcx]
0x1400167b1  mov     [rax+8], ecx
0x1400167b4  xor     r9d, r9d; RelatedActivityId
0x1400167b7  mov     [rax+0Ch], r8d
0x1400167bb  xor     r8d, r8d; ActivityId
0x1400167be  mov     rcx, cs:das_Context; RegHandle
0x1400167c5  mov     [rsp+38h+UserData], rax; UserData
0x1400167ca  mov     [rsp+38h+UserDataCount], 3; UserDataCount
0x1400167d2  call    cs:__imp_EventWriteTransfer
0x1400167d8  add     rsp, 38h
0x1400167dc  retn
```
