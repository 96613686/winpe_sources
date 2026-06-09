# McGenEventWrite_EventWriteTransfer

- ea: `0x18000b838`
- end: `0x18000b885`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: `ULONG __fastcall(REGHANDLE *, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180004e80`
- `0x1800100b8`
- `0x180010158`
- `0x1800101e0`
- `0x180010b08`
- `0x180010bac`
- `0x180010c84`
- `0x180010d28`

## callees

- `0x18000b838`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x18000b87a`
- `ADVAPI32!EventWriteTransfer` at `0x18000b87a`

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
0x18000b838  sub     rsp, 38h
0x18000b83c  mov     r8, [rcx+8]
0x18000b840  mov     rax, [rsp+38h+arg_20]
0x18000b845  test    r8, r8
0x18000b848  jnz     short loc_18000B852
0x18000b84a  mov     [rax], r8
0x18000b84d  xor     r10d, r10d
0x18000b850  jmp     short loc_18000B85F
0x18000b852  mov     [rax], r8
0x18000b855  mov     r10d, 2
0x18000b85b  movzx   r8d, word ptr [r8]
0x18000b85f  mov     [rax+8], r8d
0x18000b863  xor     r8d, r8d; ActivityId
0x18000b866  mov     [rsp+38h+UserData], rax; UserData
0x18000b86b  mov     [rax+0Ch], r10d
0x18000b86f  mov     rcx, [rcx]; RegHandle
0x18000b872  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000b877  xor     r9d, r9d; RelatedActivityId
0x18000b87a  call    cs:__imp_EventWriteTransfer
0x18000b880  add     rsp, 38h
0x18000b884  retn
```
