# McGenEventWrite_EventWriteTransfer

- ea: `0x180009370`
- end: `0x1800093c2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800075c4`
- `0x180007ba0`
- `0x1800093c8`

## callees

- `0x180009370`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x1800093b7`
- `ADVAPI32!EventWriteTransfer` at `0x1800093b7`

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

  v5 = (unsigned __int16 *)qword_1800100A8;
  if ( qword_1800100A8 )
  {
    UserData->Ptr = qword_1800100A8;
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
  return EventWriteTransfer(FH_CORE_PROVIDER_GUID_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180009370  sub     rsp, 38h
0x180009374  mov     rcx, cs:qword_1800100A8
0x18000937b  mov     rax, [rsp+38h+arg_20]
0x180009380  test    rcx, rcx
0x180009383  jnz     short loc_18000938D
0x180009385  mov     [rax], rcx
0x180009388  xor     r8d, r8d
0x18000938b  jmp     short loc_180009399
0x18000938d  mov     [rax], rcx
0x180009390  mov     r8d, 2
0x180009396  movzx   ecx, word ptr [rcx]
0x180009399  mov     [rax+8], ecx
0x18000939c  mov     [rax+0Ch], r8d
0x1800093a0  xor     r8d, r8d; ActivityId
0x1800093a3  mov     rcx, cs:FH_CORE_PROVIDER_GUID_Context; RegHandle
0x1800093aa  mov     [rsp+38h+UserData], rax; UserData
0x1800093af  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800093b4  xor     r9d, r9d; RelatedActivityId
0x1800093b7  call    cs:__imp_EventWriteTransfer
0x1800093bd  add     rsp, 38h
0x1800093c1  retn
```
