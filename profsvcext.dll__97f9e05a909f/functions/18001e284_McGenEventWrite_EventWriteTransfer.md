# McGenEventWrite_EventWriteTransfer

- ea: `0x18001e284`
- end: `0x18001e2d6`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001e2dc`
- `0x18001e364`

## callees

- `0x18001e284`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e2cb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e2cb`

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

  v5 = (unsigned __int16 *)qword_18002B098;
  if ( qword_18002B098 )
  {
    UserData->Ptr = qword_18002B098;
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
  return EventWriteTransfer(S_Microsoft_Windows_Userenv_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18001e284  sub     rsp, 38h
0x18001e288  mov     rcx, cs:qword_18002B098
0x18001e28f  mov     rax, [rsp+38h+arg_20]
0x18001e294  test    rcx, rcx
0x18001e297  jnz     short loc_18001E2A1
0x18001e299  mov     [rax], rcx
0x18001e29c  xor     r8d, r8d
0x18001e29f  jmp     short loc_18001E2AD
0x18001e2a1  mov     [rax], rcx
0x18001e2a4  mov     r8d, 2
0x18001e2aa  movzx   ecx, word ptr [rcx]
0x18001e2ad  mov     [rax+8], ecx
0x18001e2b0  mov     [rax+0Ch], r8d
0x18001e2b4  xor     r8d, r8d; ActivityId
0x18001e2b7  mov     rcx, cs:S_Microsoft_Windows_Userenv_Context; RegHandle
0x18001e2be  mov     [rsp+38h+UserData], rax; UserData
0x18001e2c3  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18001e2c8  xor     r9d, r9d; RelatedActivityId
0x18001e2cb  call    cs:__imp_EventWriteTransfer
0x18001e2d1  add     rsp, 38h
0x18001e2d5  retn
```
