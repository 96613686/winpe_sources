# McGenEventWrite_EventWriteTransfer

- ea: `0x1800077a0`
- end: `0x1800077f2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `26`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800077f8`
- `0x180007878`
- `0x180007920`
- `0x180009300`
- `0x1800097f8`
- `0x180009f30`
- `0x18000a068`
- `0x18000a4b8`
- `0x18000b3b0`
- `0x18000c574`
- `0x18000c8ec`
- `0x18000d4d8`
- `0x18000e100`
- `0x1800125f4`
- `0x180012770`
- `0x180012890`
- `0x180012b44`
- `0x180012e44`
- `0x180013220`
- `0x180013438`
- `0x180013954`
- `0x180013a88`
- `0x180013c00`
- `0x1800156f5`
- `0x180015802`
- `0x1800160d0`

## callees

- `0x1800077a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800077e7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800077e7`

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

  v5 = (unsigned __int16 *)qword_180020008;
  if ( qword_180020008 )
  {
    UserData->Ptr = qword_180020008;
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
  return EventWriteTransfer(HostGuardianClientServiceProvider_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1800077a0  sub     rsp, 38h
0x1800077a4  mov     rcx, cs:qword_180020008
0x1800077ab  mov     rax, [rsp+38h+arg_20]
0x1800077b0  test    rcx, rcx
0x1800077b3  jnz     short loc_1800077BD
0x1800077b5  mov     [rax], rcx
0x1800077b8  xor     r8d, r8d
0x1800077bb  jmp     short loc_1800077C9
0x1800077bd  mov     [rax], rcx
0x1800077c0  mov     r8d, 2
0x1800077c6  movzx   ecx, word ptr [rcx]
0x1800077c9  mov     [rax+8], ecx
0x1800077cc  mov     [rax+0Ch], r8d
0x1800077d0  xor     r8d, r8d; ActivityId
0x1800077d3  mov     rcx, cs:HostGuardianClientServiceProvider_Context; RegHandle
0x1800077da  mov     [rsp+38h+UserData], rax; UserData
0x1800077df  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800077e4  xor     r9d, r9d; RelatedActivityId
0x1800077e7  call    cs:__imp_EventWriteTransfer
0x1800077ed  add     rsp, 38h
0x1800077f1  retn
```
