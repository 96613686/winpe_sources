# McGenEventWrite_EventWriteTransfer

- ea: `0x180014420`
- end: `0x18001447a`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `90`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, __int64, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800140d8`

## callees

- `0x180014420`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001446f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001446f`

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

  v5 = (unsigned __int16 *)qword_1800210E8;
  if ( qword_1800210E8 )
  {
    UserData->Ptr = qword_1800210E8;
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
  return EventWriteTransfer(Microsoft_Windows_Search_Core_Context, &MSSearchTraceId_ETWLogging, 0, 0, 2u, UserData);
}

```

## disassembly

```asm
0x180014420  sub     rsp, 38h
0x180014424  mov     rcx, cs:qword_1800210E8
0x18001442b  mov     r8d, 2
0x180014431  mov     rax, [rsp+38h+arg_20]
0x180014436  test    rcx, rcx
0x180014439  jnz     short loc_180014442
0x18001443b  mov     [rax], rcx
0x18001443e  xor     edx, edx
0x180014440  jmp     short loc_18001444B
0x180014442  mov     [rax], rcx
0x180014445  mov     edx, r8d
0x180014448  movzx   ecx, word ptr [rcx]
0x18001444b  mov     [rax+8], ecx
0x18001444e  xor     r9d, r9d; RelatedActivityId
0x180014451  mov     [rax+0Ch], edx
0x180014454  lea     rdx, MSSearchTraceId_ETWLogging; EventDescriptor
0x18001445b  mov     rcx, cs:Microsoft_Windows_Search_Core_Context; RegHandle
0x180014462  mov     [rsp+38h+UserData], rax; UserData
0x180014467  mov     [rsp+38h+UserDataCount], r8d; UserDataCount
0x18001446c  xor     r8d, r8d; ActivityId
0x18001446f  call    cs:__imp_EventWriteTransfer
0x180014475  add     rsp, 38h
0x180014479  retn
```
