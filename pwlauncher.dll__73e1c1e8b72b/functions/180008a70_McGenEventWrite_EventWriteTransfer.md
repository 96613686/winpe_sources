# McGenEventWrite_EventWriteTransfer

- ea: `0x180008a70`
- end: `0x180008ac2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005a68`
- `0x180005c98`
- `0x180008720`

## callees

- `0x180008a70`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180008ab7`
- `ADVAPI32!EventWriteTransfer` at `0x180008ab7`

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

  v5 = (unsigned __int16 *)qword_180019058;
  if ( qword_180019058 )
  {
    UserData->Ptr = qword_180019058;
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
  return EventWriteTransfer(PORTABLEWORKSPACE_LAUNCHER_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180008a70  sub     rsp, 38h
0x180008a74  mov     rcx, cs:qword_180019058
0x180008a7b  mov     rax, [rsp+38h+arg_20]
0x180008a80  test    rcx, rcx
0x180008a83  jnz     short loc_180008A8D
0x180008a85  mov     [rax], rcx
0x180008a88  xor     r8d, r8d
0x180008a8b  jmp     short loc_180008A99
0x180008a8d  mov     [rax], rcx
0x180008a90  mov     r8d, 2
0x180008a96  movzx   ecx, word ptr [rcx]
0x180008a99  mov     [rax+8], ecx
0x180008a9c  mov     [rax+0Ch], r8d
0x180008aa0  xor     r8d, r8d; ActivityId
0x180008aa3  mov     rcx, cs:PORTABLEWORKSPACE_LAUNCHER_Context; RegHandle
0x180008aaa  mov     [rsp+38h+UserData], rax; UserData
0x180008aaf  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180008ab4  xor     r9d, r9d; RelatedActivityId
0x180008ab7  call    cs:__imp_EventWriteTransfer
0x180008abd  add     rsp, 38h
0x180008ac1  retn
```
