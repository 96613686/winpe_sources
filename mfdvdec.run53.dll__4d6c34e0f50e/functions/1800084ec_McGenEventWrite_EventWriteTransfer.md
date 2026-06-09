# McGenEventWrite_EventWriteTransfer

- ea: `0x1800084ec`
- end: `0x180008545`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008358`

## callees

- `0x1800084ec`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000853a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000853a`

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

  v5 = (unsigned __int16 *)qword_180022038;
  if ( qword_180022038 )
  {
    UserData->Ptr = qword_180022038;
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
0x1800084ec  sub     rsp, 38h
0x1800084f0  mov     rcx, cs:qword_180022038
0x1800084f7  mov     rax, [rsp+38h+arg_20]
0x1800084fc  test    rcx, rcx
0x1800084ff  jnz     short loc_180008508
0x180008501  mov     [rax], rcx
0x180008504  xor     edx, edx
0x180008506  jmp     short loc_180008513
0x180008508  mov     [rax], rcx
0x18000850b  mov     edx, 2
0x180008510  movzx   ecx, word ptr [rcx]
0x180008513  mov     [rax+8], ecx
0x180008516  xor     r9d, r9d; RelatedActivityId
0x180008519  mov     [rax+0Ch], edx
0x18000851c  xor     r8d, r8d; ActivityId
0x18000851f  mov     rcx, cs:Microsoft_Windows_MediaFoundation_Platform_Context; RegHandle
0x180008526  lea     rdx, Platform_TraceFailure; EventDescriptor
0x18000852d  mov     [rsp+38h+UserData], rax; UserData
0x180008532  mov     [rsp+38h+UserDataCount], 5; UserDataCount
0x18000853a  call    cs:__imp_EventWriteTransfer
0x180008540  add     rsp, 38h
0x180008544  retn
```
