# McGenEventWrite_EventWriteTransfer

- ea: `0x18000eb28`
- end: `0x18000eb7a`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000eb80`
- `0x18000ebf8`

## callees

- `0x18000eb28`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000eb6f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000eb6f`

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

  v5 = (unsigned __int16 *)qword_180033018;
  if ( qword_180033018 )
  {
    UserData->Ptr = qword_180033018;
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
  return EventWriteTransfer(Microsoft_Windows_MediaFoundation_Performance_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000eb28  sub     rsp, 38h
0x18000eb2c  mov     rcx, cs:qword_180033018
0x18000eb33  mov     rax, [rsp+38h+arg_20]
0x18000eb38  test    rcx, rcx
0x18000eb3b  jnz     short loc_18000EB45
0x18000eb3d  mov     [rax], rcx
0x18000eb40  xor     r8d, r8d
0x18000eb43  jmp     short loc_18000EB51
0x18000eb45  mov     [rax], rcx
0x18000eb48  mov     r8d, 2
0x18000eb4e  movzx   ecx, word ptr [rcx]
0x18000eb51  mov     [rax+8], ecx
0x18000eb54  mov     [rax+0Ch], r8d
0x18000eb58  xor     r8d, r8d; ActivityId
0x18000eb5b  mov     rcx, cs:Microsoft_Windows_MediaFoundation_Performance_Context; RegHandle
0x18000eb62  mov     [rsp+38h+UserData], rax; UserData
0x18000eb67  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000eb6c  xor     r9d, r9d; RelatedActivityId
0x18000eb6f  call    cs:__imp_EventWriteTransfer
0x18000eb75  add     rsp, 38h
0x18000eb79  retn
```
