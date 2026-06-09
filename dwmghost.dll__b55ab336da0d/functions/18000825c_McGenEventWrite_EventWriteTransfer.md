# McGenEventWrite_EventWriteTransfer

- ea: `0x18000825c`
- end: `0x1800082b5`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007e64`

## callees

- `0x18000825c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800082aa`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800082aa`

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

  v5 = (unsigned __int16 *)qword_180012008;
  if ( qword_180012008 )
  {
    UserData->Ptr = qword_180012008;
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
  return EventWriteTransfer(WERSVC_TRIGGER_PROVIDER_GUID_Context, &StartTrigger, 0, 0, 1u, UserData);
}

```

## disassembly

```asm
0x18000825c  sub     rsp, 38h
0x180008260  mov     rcx, cs:qword_180012008
0x180008267  mov     rax, [rsp+38h+arg_20]
0x18000826c  test    rcx, rcx
0x18000826f  jnz     short loc_180008278
0x180008271  mov     [rax], rcx
0x180008274  xor     edx, edx
0x180008276  jmp     short loc_180008283
0x180008278  mov     [rax], rcx
0x18000827b  mov     edx, 2
0x180008280  movzx   ecx, word ptr [rcx]
0x180008283  mov     [rax+8], ecx
0x180008286  xor     r9d, r9d; RelatedActivityId
0x180008289  mov     [rax+0Ch], edx
0x18000828c  xor     r8d, r8d; ActivityId
0x18000828f  mov     rcx, cs:WERSVC_TRIGGER_PROVIDER_GUID_Context; RegHandle
0x180008296  lea     rdx, StartTrigger; EventDescriptor
0x18000829d  mov     [rsp+38h+UserData], rax; UserData
0x1800082a2  mov     [rsp+38h+UserDataCount], 1; UserDataCount
0x1800082aa  call    cs:__imp_EventWriteTransfer
0x1800082b0  add     rsp, 38h
0x1800082b4  retn
```
