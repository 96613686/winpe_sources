# McGenEventWrite_EventWriteTransfer

- ea: `0x18000db94`
- end: `0x18000dbee`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `90`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ad3c`

## callees

- `0x18000db94`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000dbe3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000dbe3`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  ULONG v6; // edx

  v5 = (unsigned __int16 *)qword_18003C008;
  if ( qword_18003C008 )
  {
    UserData->Ptr = qword_18003C008;
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
  return EventWriteTransfer(RdpLite_Context, &RdpLite_Event_Fallback, 0, 0, 2u, UserData);
}

```

## disassembly

```asm
0x18000db94  sub     rsp, 38h
0x18000db98  mov     rcx, cs:qword_18003C008
0x18000db9f  mov     r8d, 2
0x18000dba5  mov     rax, [rsp+38h+arg_20]
0x18000dbaa  test    rcx, rcx
0x18000dbad  jnz     short loc_18000DBB6
0x18000dbaf  mov     [rax], rcx
0x18000dbb2  xor     edx, edx
0x18000dbb4  jmp     short loc_18000DBBF
0x18000dbb6  mov     [rax], rcx
0x18000dbb9  mov     edx, r8d
0x18000dbbc  movzx   ecx, word ptr [rcx]
0x18000dbbf  mov     [rax+8], ecx
0x18000dbc2  xor     r9d, r9d; RelatedActivityId
0x18000dbc5  mov     [rax+0Ch], edx
0x18000dbc8  lea     rdx, RdpLite_Event_Fallback; EventDescriptor
0x18000dbcf  mov     rcx, cs:RdpLite_Context; RegHandle
0x18000dbd6  mov     [rsp+38h+UserData], rax; UserData
0x18000dbdb  mov     [rsp+38h+UserDataCount], r8d; UserDataCount
0x18000dbe0  xor     r8d, r8d; ActivityId
0x18000dbe3  call    cs:__imp_EventWriteTransfer
0x18000dbe9  add     rsp, 38h
0x18000dbed  retn
```
