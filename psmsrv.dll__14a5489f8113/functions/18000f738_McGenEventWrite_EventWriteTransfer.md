# McGenEventWrite_EventWriteTransfer

- ea: `0x18000f738`
- end: `0x18000f78a`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800017f8`
- `0x18000f2a4`
- `0x18000f580`
- `0x18000f65c`
- `0x1800251f8`

## callees

- `0x18000f738`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f771`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f771`

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

  v5 = (unsigned __int16 *)qword_18003F008;
  if ( qword_18003F008 )
  {
    UserData->Ptr = qword_18003F008;
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
  return EventWriteTransfer(PsmTraceProvider_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000f738  sub     rsp, 38h
0x18000f73c  mov     rcx, cs:qword_18003F008
0x18000f743  mov     rax, [rsp+38h+arg_20]
0x18000f748  test    rcx, rcx
0x18000f74b  jnz     short loc_18000F77C
0x18000f74d  mov     [rax], rcx
0x18000f750  xor     r8d, r8d
0x18000f753  mov     [rax+8], ecx
0x18000f756  mov     [rax+0Ch], r8d
0x18000f75a  xor     r8d, r8d; ActivityId
0x18000f75d  mov     rcx, cs:PsmTraceProvider_Context; RegHandle
0x18000f764  mov     [rsp+38h+UserData], rax; UserData
0x18000f769  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000f76e  xor     r9d, r9d; RelatedActivityId
0x18000f771  call    cs:__imp_EventWriteTransfer
0x18000f777  add     rsp, 38h
0x18000f77b  retn
0x18000f77c  mov     [rax], rcx
0x18000f77f  mov     r8d, 2
0x18000f785  movzx   ecx, word ptr [rcx]
0x18000f788  jmp     short loc_18000F753
```
