# McGenEventWrite_EventWriteTransfer

- ea: `0x180014218`
- end: `0x18001426d`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a330`
- `0x18000bd00`
- `0x18000bf2c`
- `0x18000d2e4`
- `0x18000f85c`

## callees

- `0x180014218`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180014262`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180014262`

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

  v5 = (unsigned __int16 *)qword_180032008;
  if ( qword_180032008 )
  {
    UserData->Ptr = qword_180032008;
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
  return EventWriteTransfer(Microsoft_Windows_Network_and_Sharing_center_Context, a2, 0, 0, 1u, UserData);
}

```

## disassembly

```asm
0x180014218  sub     rsp, 38h
0x18001421c  mov     rcx, cs:qword_180032008
0x180014223  mov     rax, [rsp+38h+arg_20]
0x180014228  test    rcx, rcx
0x18001422b  jnz     short loc_180014235
0x18001422d  mov     [rax], rcx
0x180014230  xor     r8d, r8d
0x180014233  jmp     short loc_180014241
0x180014235  mov     [rax], rcx
0x180014238  mov     r8d, 2
0x18001423e  movzx   ecx, word ptr [rcx]
0x180014241  mov     [rax+8], ecx
0x180014244  xor     r9d, r9d; RelatedActivityId
0x180014247  mov     [rax+0Ch], r8d
0x18001424b  xor     r8d, r8d; ActivityId
0x18001424e  mov     rcx, cs:Microsoft_Windows_Network_and_Sharing_center_Context; RegHandle
0x180014255  mov     [rsp+38h+UserData], rax; UserData
0x18001425a  mov     [rsp+38h+UserDataCount], 1; UserDataCount
0x180014262  call    cs:__imp_EventWriteTransfer
0x180014268  add     rsp, 38h
0x18001426c  retn
```
