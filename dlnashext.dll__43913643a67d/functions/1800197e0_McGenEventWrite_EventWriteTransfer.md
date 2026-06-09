# McGenEventWrite_EventWriteTransfer

- ea: `0x1800197e0`
- end: `0x180019832`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180019838`
- `0x18001e220`
- `0x18002833c`

## callees

- `0x1800197e0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019827`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019827`

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

  v5 = (unsigned __int16 *)qword_180048008;
  if ( qword_180048008 )
  {
    UserData->Ptr = qword_180048008;
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
  return EventWriteTransfer(Microsoft_Windows_DLNA_Namespace_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1800197e0  sub     rsp, 38h
0x1800197e4  mov     rcx, cs:qword_180048008
0x1800197eb  mov     rax, [rsp+38h+arg_20]
0x1800197f0  test    rcx, rcx
0x1800197f3  jnz     short loc_1800197FD
0x1800197f5  mov     [rax], rcx
0x1800197f8  xor     r8d, r8d
0x1800197fb  jmp     short loc_180019809
0x1800197fd  mov     [rax], rcx
0x180019800  mov     r8d, 2
0x180019806  movzx   ecx, word ptr [rcx]
0x180019809  mov     [rax+8], ecx
0x18001980c  mov     [rax+0Ch], r8d
0x180019810  xor     r8d, r8d; ActivityId
0x180019813  mov     rcx, cs:Microsoft_Windows_DLNA_Namespace_Context; RegHandle
0x18001981a  mov     [rsp+38h+UserData], rax; UserData
0x18001981f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180019824  xor     r9d, r9d; RelatedActivityId
0x180019827  call    cs:__imp_EventWriteTransfer
0x18001982d  add     rsp, 38h
0x180019831  retn
```
