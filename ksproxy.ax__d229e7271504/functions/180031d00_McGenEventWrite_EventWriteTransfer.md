# McGenEventWrite_EventWriteTransfer

- ea: `0x180031d00`
- end: `0x180031d54`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `84`
- prototype: `ULONG __fastcall(REGHANDLE *, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18002cac4`
- `0x180031360`
- `0x1800315e0`
- `0x180031d5c`

## callees

- `0x180031d00`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180031d42`
- `ADVAPI32!EventWriteTransfer` at `0x180031d42`

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
0x180031d00  sub     rsp, 38h
0x180031d04  mov     r8, [rcx+8]
0x180031d08  mov     rax, [rsp+38h+arg_20]
0x180031d0d  test    r8, r8
0x180031d10  jnz     short loc_180031D1A
0x180031d12  mov     [rax], r8
0x180031d15  xor     r10d, r10d
0x180031d18  jmp     short loc_180031D27
0x180031d1a  mov     [rax], r8
0x180031d1d  mov     r10d, 2
0x180031d23  movzx   r8d, word ptr [r8]
0x180031d27  mov     [rax+8], r8d
0x180031d2b  xor     r8d, r8d; ActivityId
0x180031d2e  mov     [rsp+38h+UserData], rax; UserData
0x180031d33  mov     [rax+0Ch], r10d
0x180031d37  mov     rcx, [rcx]; RegHandle
0x180031d3a  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180031d3f  xor     r9d, r9d; RelatedActivityId
0x180031d42  call    cs:__imp_EventWriteTransfer
0x180031d49  nop     dword ptr [rax+rax+00h]
0x180031d4e  add     rsp, 38h
0x180031d52  retn
```
