# McGenEventWrite_EventWriteTransfer

- ea: `0x18002204c`
- end: `0x18002209e`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180012b44`
- `0x180018ee0`
- `0x18001fee4`
- `0x180021240`
- `0x180021bc0`
- `0x1800220a4`
- `0x180022124`
- `0x1800221c0`
- `0x180023330`

## callees

- `0x18002204c`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180022093`
- `ADVAPI32!EventWriteTransfer` at `0x180022093`

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

  v5 = (unsigned __int16 *)qword_1800400F8;
  if ( qword_1800400F8 )
  {
    UserData->Ptr = qword_1800400F8;
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
  return EventWriteTransfer(FH_ENGINE_PROVIDER_GUID_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18002204c  sub     rsp, 38h
0x180022050  mov     rcx, cs:qword_1800400F8
0x180022057  mov     rax, [rsp+38h+arg_20]
0x18002205c  test    rcx, rcx
0x18002205f  jnz     short loc_180022069
0x180022061  mov     [rax], rcx
0x180022064  xor     r8d, r8d
0x180022067  jmp     short loc_180022075
0x180022069  mov     [rax], rcx
0x18002206c  mov     r8d, 2
0x180022072  movzx   ecx, word ptr [rcx]
0x180022075  mov     [rax+8], ecx
0x180022078  mov     [rax+0Ch], r8d
0x18002207c  xor     r8d, r8d; ActivityId
0x18002207f  mov     rcx, cs:FH_ENGINE_PROVIDER_GUID_Context; RegHandle
0x180022086  mov     [rsp+38h+UserData], rax; UserData
0x18002208b  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180022090  xor     r9d, r9d; RelatedActivityId
0x180022093  call    cs:__imp_EventWriteTransfer
0x180022099  add     rsp, 38h
0x18002209d  retn
```
