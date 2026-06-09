# McGenEventWrite_EventWriteTransfer

- ea: `0x18000488c`
- end: `0x1800048e5`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800048ec`

## callees

- `0x18000488c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800048da`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800048da`

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

  v5 = (unsigned __int16 *)qword_18000A018;
  if ( qword_18000A018 )
  {
    UserData->Ptr = qword_18000A018;
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
  return EventWriteTransfer(
           Microsoft_Windows_MediaFoundation_Platform_Context,
           &Platform_TraceFailure,
           0,
           0,
           5u,
           UserData);
}

```

## disassembly

```asm
0x18000488c  sub     rsp, 38h
0x180004890  mov     rcx, cs:qword_18000A018
0x180004897  mov     rax, [rsp+38h+arg_20]
0x18000489c  test    rcx, rcx
0x18000489f  jnz     short loc_1800048A8
0x1800048a1  mov     [rax], rcx
0x1800048a4  xor     edx, edx
0x1800048a6  jmp     short loc_1800048B3
0x1800048a8  mov     [rax], rcx
0x1800048ab  mov     edx, 2
0x1800048b0  movzx   ecx, word ptr [rcx]
0x1800048b3  mov     [rax+8], ecx
0x1800048b6  xor     r9d, r9d; RelatedActivityId
0x1800048b9  mov     [rax+0Ch], edx
0x1800048bc  xor     r8d, r8d; ActivityId
0x1800048bf  mov     rcx, cs:Microsoft_Windows_MediaFoundation_Platform_Context; RegHandle
0x1800048c6  lea     rdx, Platform_TraceFailure; EventDescriptor
0x1800048cd  mov     [rsp+38h+UserData], rax; UserData
0x1800048d2  mov     [rsp+38h+UserDataCount], 5; UserDataCount
0x1800048da  call    cs:__imp_EventWriteTransfer
0x1800048e0  add     rsp, 38h
0x1800048e4  retn
```
