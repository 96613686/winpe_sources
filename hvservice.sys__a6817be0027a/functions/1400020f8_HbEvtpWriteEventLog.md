# HbEvtpWriteEventLog

- ea: `0x1400020f8`
- end: `0x14000212b`
- name: `HbEvtpWriteEventLog`
- size: `51`
- prototype: `NTSTATUS __fastcall(PCEVENT_DESCRIPTOR EventDescriptor, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140010a78`
- `0x140010c0c`
- `0x1400115a0`
- `0x140012170`
- `0x140012524`
- `0x14001396c`
- `0x140013b34`
- `0x140014810`

## callees

- `0x1400020f8`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140002119`
- `ntoskrnl!EtwWrite` at `0x140002119`

## pseudocode

```c
NTSTATUS __fastcall HbEvtpWriteEventLog(
        PCEVENT_DESCRIPTOR EventDescriptor,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  NTSTATUS result; // eax

  result = (int)EventDescriptor;
  if ( HvBootDriverControlGuid_Context )
    return EtwWrite(HvBootDriverControlGuid_Context, EventDescriptor, 0, UserDataCount, UserData);
  return result;
}

```

## disassembly

```asm
0x1400020f8  sub     rsp, 38h
0x1400020fc  mov     rax, rcx
0x1400020ff  mov     rcx, cs:HvBootDriverControlGuid_Context; RegHandle
0x140002106  test    rcx, rcx
0x140002109  jz      short loc_140002125
0x14000210b  mov     [rsp+38h+UserData], r8; UserData
0x140002110  mov     r9d, edx; UserDataCount
0x140002113  xor     r8d, r8d; ActivityId
0x140002116  mov     rdx, rax; EventDescriptor
0x140002119  call    cs:__imp_EtwWrite
0x140002120  nop     dword ptr [rax+rax+00h]
0x140002125  add     rsp, 38h
0x140002129  retn
```
