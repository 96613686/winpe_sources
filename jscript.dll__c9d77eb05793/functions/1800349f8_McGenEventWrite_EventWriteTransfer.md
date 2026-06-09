# McGenEventWrite_EventWriteTransfer

- ea: `0x1800349f8`
- end: `0x180034a4d`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180034990`

## callees

- `0x1800349f8`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180034a42`
- `ADVAPI32!EventWriteTransfer` at `0x180034a42`

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

  v5 = (unsigned __int16 *)qword_1800B1F28;
  if ( qword_1800B1F28 )
  {
    UserData->Ptr = qword_1800B1F28;
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
  return EventWriteTransfer(BERP_IE_Context, a2, 0, 0, 3u, UserData);
}

```

## disassembly

```asm
0x1800349f8  sub     rsp, 38h
0x1800349fc  mov     rcx, cs:qword_1800B1F28
0x180034a03  mov     rax, [rsp+38h+arg_20]
0x180034a08  test    rcx, rcx
0x180034a0b  jnz     short loc_180034A15
0x180034a0d  mov     [rax], rcx
0x180034a10  xor     r8d, r8d
0x180034a13  jmp     short loc_180034A21
0x180034a15  mov     [rax], rcx
0x180034a18  mov     r8d, 2
0x180034a1e  movzx   ecx, word ptr [rcx]
0x180034a21  mov     [rax+8], ecx
0x180034a24  xor     r9d, r9d; RelatedActivityId
0x180034a27  mov     [rax+0Ch], r8d
0x180034a2b  xor     r8d, r8d; ActivityId
0x180034a2e  mov     rcx, cs:BERP_IE_Context; RegHandle
0x180034a35  mov     [rsp+38h+UserData], rax; UserData
0x180034a3a  mov     [rsp+38h+UserDataCount], 3; UserDataCount
0x180034a42  call    cs:__imp_EventWriteTransfer
0x180034a48  add     rsp, 38h
0x180034a4c  retn
```
