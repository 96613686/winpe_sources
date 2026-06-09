# McGenEventWrite_EventWriteTransfer

- ea: `0x180018098`
- end: `0x1800180e5`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180016508`
- `0x180016810`
- `0x180038474`

## callees

- `0x180018098`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800180da`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800180da`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r8
  int v6; // r10d

  v5 = (unsigned __int16 *)a1[1];
  if ( v5 )
  {
    UserData->Ptr = (ULONGLONG)v5;
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
  return EventWriteTransfer(*a1, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180018098  sub     rsp, 38h
0x18001809c  mov     r8, [rcx+8]
0x1800180a0  mov     rax, [rsp+38h+arg_20]
0x1800180a5  test    r8, r8
0x1800180a8  jnz     short loc_1800180B2
0x1800180aa  mov     [rax], r8
0x1800180ad  xor     r10d, r10d
0x1800180b0  jmp     short loc_1800180BF
0x1800180b2  mov     [rax], r8
0x1800180b5  mov     r10d, 2
0x1800180bb  movzx   r8d, word ptr [r8]
0x1800180bf  mov     [rax+8], r8d
0x1800180c3  xor     r8d, r8d; ActivityId
0x1800180c6  mov     [rsp+38h+UserData], rax; UserData
0x1800180cb  mov     [rax+0Ch], r10d
0x1800180cf  mov     rcx, [rcx]; RegHandle
0x1800180d2  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800180d7  xor     r9d, r9d; RelatedActivityId
0x1800180da  call    cs:__imp_EventWriteTransfer
0x1800180e0  add     rsp, 38h
0x1800180e4  retn
```
