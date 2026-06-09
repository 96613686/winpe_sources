# McGenEventWrite_EventWriteTransfer

- ea: `0x18001b0cc`
- end: `0x18001b125`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001a090`
- `0x18001a5d0`
- `0x18001b12c`
- `0x18001b184`
- `0x18001b208`
- `0x18001b2ac`
- `0x18001b364`

## callees

- `0x18001b0cc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001b113`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001b113`

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

  v5 = (unsigned __int16 *)qword_180034888;
  if ( qword_180034888 )
  {
    UserData->Ptr = qword_180034888;
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
  return EventWriteTransfer(Microsoft_Windows_XPerfCore_ETWProvider_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18001b0cc  sub     rsp, 38h
0x18001b0d0  mov     rcx, cs:qword_180034888
0x18001b0d7  mov     rax, [rsp+38h+arg_20]
0x18001b0dc  test    rcx, rcx
0x18001b0df  jnz     short loc_18001B0E9
0x18001b0e1  mov     [rax], rcx
0x18001b0e4  xor     r8d, r8d
0x18001b0e7  jmp     short loc_18001B0F5
0x18001b0e9  mov     [rax], rcx
0x18001b0ec  mov     r8d, 2
0x18001b0f2  movzx   ecx, word ptr [rcx]
0x18001b0f5  mov     [rax+8], ecx
0x18001b0f8  mov     [rax+0Ch], r8d
0x18001b0fc  xor     r8d, r8d; ActivityId
0x18001b0ff  mov     rcx, cs:Microsoft_Windows_XPerfCore_ETWProvider_Context; RegHandle
0x18001b106  mov     [rsp+38h+UserData], rax; UserData
0x18001b10b  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18001b110  xor     r9d, r9d; RelatedActivityId
0x18001b113  call    cs:__imp_EventWriteTransfer
0x18001b11a  nop     dword ptr [rax+rax+00h]
0x18001b11f  add     rsp, 38h
0x18001b123  retn
```
