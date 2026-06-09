# McGenEventWrite_EventWriteTransfer

- ea: `0x14000a514`
- end: `0x14000a569`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140009e64`
- `0x14000ad38`

## callees

- `0x14000a514`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x14000a55e`
- `ADVAPI32!EventWriteTransfer` at `0x14000a55e`

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

  v5 = (unsigned __int16 *)qword_140016008;
  if ( qword_140016008 )
  {
    UserData->Ptr = qword_140016008;
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
  return EventWriteTransfer(Microsoft_Windows_Shell_Core_Provider_Context, a2, 0, 0, 1u, UserData);
}

```

## disassembly

```asm
0x14000a514  sub     rsp, 38h
0x14000a518  mov     rcx, cs:qword_140016008
0x14000a51f  mov     rax, [rsp+38h+arg_20]
0x14000a524  test    rcx, rcx
0x14000a527  jnz     short loc_14000A531
0x14000a529  mov     [rax], rcx
0x14000a52c  xor     r8d, r8d
0x14000a52f  jmp     short loc_14000A53D
0x14000a531  mov     [rax], rcx
0x14000a534  mov     r8d, 2
0x14000a53a  movzx   ecx, word ptr [rcx]
0x14000a53d  mov     [rax+8], ecx
0x14000a540  xor     r9d, r9d; RelatedActivityId
0x14000a543  mov     [rax+0Ch], r8d
0x14000a547  xor     r8d, r8d; ActivityId
0x14000a54a  mov     rcx, cs:Microsoft_Windows_Shell_Core_Provider_Context; RegHandle
0x14000a551  mov     [rsp+38h+UserData], rax; UserData
0x14000a556  mov     [rsp+38h+UserDataCount], 1; UserDataCount
0x14000a55e  call    cs:__imp_EventWriteTransfer
0x14000a564  add     rsp, 38h
0x14000a568  retn
```
