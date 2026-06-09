# McGenEventWrite_EventWriteTransfer

- ea: `0x18000f698`
- end: `0x18000f6ea`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f148`
- `0x18000f7b0`
- `0x18000f8b8`
- `0x180016c78`
- `0x180016dbc`
- `0x18001b808`
- `0x18001b8b8`
- `0x18001e8e8`

## callees

- `0x18000f698`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f6d1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f6d1`

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

  v5 = (unsigned __int16 *)qword_18002A018;
  if ( qword_18002A018 )
  {
    UserData->Ptr = qword_18002A018;
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
  return EventWriteTransfer(ETW_LOG_NCRYPT_PROVIDER_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000f698  sub     rsp, 38h
0x18000f69c  mov     rcx, cs:qword_18002A018
0x18000f6a3  mov     rax, [rsp+38h+arg_20]
0x18000f6a8  test    rcx, rcx
0x18000f6ab  jnz     short loc_18000F6DC
0x18000f6ad  mov     [rax], rcx
0x18000f6b0  xor     r8d, r8d
0x18000f6b3  mov     [rax+8], ecx
0x18000f6b6  mov     [rax+0Ch], r8d
0x18000f6ba  xor     r8d, r8d; ActivityId
0x18000f6bd  mov     rcx, cs:ETW_LOG_NCRYPT_PROVIDER_Context; RegHandle
0x18000f6c4  mov     [rsp+38h+UserData], rax; UserData
0x18000f6c9  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000f6ce  xor     r9d, r9d; RelatedActivityId
0x18000f6d1  call    cs:__imp_EventWriteTransfer
0x18000f6d7  add     rsp, 38h
0x18000f6db  retn
0x18000f6dc  mov     [rax], rcx
0x18000f6df  mov     r8d, 2
0x18000f6e5  movzx   ecx, word ptr [rcx]
0x18000f6e8  jmp     short loc_18000F6B3
```
