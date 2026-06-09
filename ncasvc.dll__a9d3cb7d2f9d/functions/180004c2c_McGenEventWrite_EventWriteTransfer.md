# McGenEventWrite_EventWriteTransfer

- ea: `0x180004c2c`
- end: `0x180004c85`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180004c8c`
- `0x180006544`
- `0x1800065c8`
- `0x18000e7a4`
- `0x180012614`
- `0x1800126a0`
- `0x180012740`
- `0x180015f20`
- `0x1800163cc`
- `0x180018ab0`

## callees

- `0x180004c2c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004c73`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004c73`

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

  v5 = (unsigned __int16 *)qword_180028008;
  if ( qword_180028008 )
  {
    UserData->Ptr = qword_180028008;
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
  return EventWriteTransfer(MS_NCASVC_ETW_PROVIDER_ID_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180004c2c  sub     rsp, 38h
0x180004c30  mov     rcx, cs:qword_180028008
0x180004c37  mov     rax, [rsp+38h+arg_20]
0x180004c3c  test    rcx, rcx
0x180004c3f  jnz     short loc_180004C49
0x180004c41  mov     [rax], rcx
0x180004c44  xor     r8d, r8d
0x180004c47  jmp     short loc_180004C55
0x180004c49  mov     [rax], rcx
0x180004c4c  mov     r8d, 2
0x180004c52  movzx   ecx, word ptr [rcx]
0x180004c55  mov     [rax+8], ecx
0x180004c58  mov     [rax+0Ch], r8d
0x180004c5c  xor     r8d, r8d; ActivityId
0x180004c5f  mov     rcx, cs:MS_NCASVC_ETW_PROVIDER_ID_Context; RegHandle
0x180004c66  mov     [rsp+38h+UserData], rax; UserData
0x180004c6b  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180004c70  xor     r9d, r9d; RelatedActivityId
0x180004c73  call    cs:__imp_EventWriteTransfer
0x180004c7a  nop     dword ptr [rax+rax+00h]
0x180004c7f  add     rsp, 38h
0x180004c83  retn
```
