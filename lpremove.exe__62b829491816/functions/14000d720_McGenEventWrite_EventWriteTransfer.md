# McGenEventWrite_EventWriteTransfer

- ea: `0x14000d720`
- end: `0x14000d772`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400081a8`
- `0x14000a440`
- `0x14000d8b8`

## callees

- `0x14000d720`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x14000d767`
- `ADVAPI32!EventWriteTransfer` at `0x14000d767`

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

  v5 = (unsigned __int16 *)qword_140018048;
  if ( qword_140018048 )
  {
    UserData->Ptr = qword_140018048;
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
  return EventWriteTransfer(MUISETUP_ETW_PROVIDER_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x14000d720  sub     rsp, 38h
0x14000d724  mov     rcx, cs:qword_140018048
0x14000d72b  mov     rax, [rsp+38h+arg_20]
0x14000d730  test    rcx, rcx
0x14000d733  jnz     short loc_14000D73D
0x14000d735  mov     [rax], rcx
0x14000d738  xor     r8d, r8d
0x14000d73b  jmp     short loc_14000D749
0x14000d73d  mov     [rax], rcx
0x14000d740  mov     r8d, 2
0x14000d746  movzx   ecx, word ptr [rcx]
0x14000d749  mov     [rax+8], ecx
0x14000d74c  mov     [rax+0Ch], r8d
0x14000d750  xor     r8d, r8d; ActivityId
0x14000d753  mov     rcx, cs:MUISETUP_ETW_PROVIDER_Context; RegHandle
0x14000d75a  mov     [rsp+38h+UserData], rax; UserData
0x14000d75f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14000d764  xor     r9d, r9d; RelatedActivityId
0x14000d767  call    cs:__imp_EventWriteTransfer
0x14000d76d  add     rsp, 38h
0x14000d771  retn
```
