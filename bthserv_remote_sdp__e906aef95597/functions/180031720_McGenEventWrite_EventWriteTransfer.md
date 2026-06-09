# McGenEventWrite_EventWriteTransfer

- ea: `0x180031720`
- end: `0x180031781`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `97`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002e418`

## callees

- `0x180031720`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003176f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003176f`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rdx
  ULONG v6; // eax
  ULONG v7; // edx

  v5 = (unsigned __int16 *)qword_180046018;
  v6 = 0;
  if ( qword_180046018 )
  {
    UserData->Ptr = qword_180046018;
    v6 = 2;
    v7 = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v7 = 0;
  }
  UserData->Size = v7;
  UserData->Reserved = v6;
  return EventWriteTransfer(BTHLEPREPAIRING_EVENT_PROVIDER_Context, &BthLEPrepairing_Complete, 0, 0, 2u, UserData);
}

```

## disassembly

```asm
0x180031720  sub     rsp, 38h
0x180031724  mov     rdx, cs:qword_180046018
0x18003172b  xor     eax, eax
0x18003172d  mov     rcx, [rsp+38h+arg_20]
0x180031732  lea     r8d, [rax+2]
0x180031736  test    rdx, rdx
0x180031739  jnz     short loc_180031742
0x18003173b  mov     [rcx], rax
0x18003173e  mov     edx, eax
0x180031740  jmp     short loc_18003174B
0x180031742  mov     [rcx], rdx
0x180031745  mov     eax, r8d
0x180031748  movzx   edx, word ptr [rdx]
0x18003174b  mov     [rcx+8], edx
0x18003174e  xor     r9d, r9d; RelatedActivityId
0x180031751  mov     [rsp+38h+UserData], rcx; UserData
0x180031756  lea     rdx, BthLEPrepairing_Complete; EventDescriptor
0x18003175d  mov     [rcx+0Ch], eax
0x180031760  mov     rcx, cs:BTHLEPREPAIRING_EVENT_PROVIDER_Context; RegHandle
0x180031767  mov     [rsp+38h+UserDataCount], r8d; UserDataCount
0x18003176c  xor     r8d, r8d; ActivityId
0x18003176f  call    cs:__imp_EventWriteTransfer
0x180031776  nop     dword ptr [rax+rax+00h]
0x18003177b  add     rsp, 38h
0x18003177f  retn
```
