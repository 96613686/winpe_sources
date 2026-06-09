# Etw_Trace1_int

- ea: `0x18000ac44`
- end: `0x18000aca5`
- name: `Etw_Trace1_int`
- size: `97`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b258`
- `0x18000b2a8`
- `0x18001a020`
- `0x18001c950`
- `0x18001ca60`
- `0x18001cde0`
- `0x18001ced0`
- `0x18001d074`
- `0x18001d2b0`
- `0x180028858`
- `0x18002906c`
- `0x18002a9c0`
- `0x18002b2a0`
- `0x18002b490`
- `0x18002b810`

## callees

- `0x18000babc`
- `0x180044880`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000ac8c`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000ac8c`

## pseudocode

```c
ULONG __fastcall Etw_Trace1_int(PCEVENT_DESCRIPTOR EventDescriptor, int a2)
{
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-28h] BYREF
  int v5; // [rsp+58h] [rbp+10h] BYREF

  v5 = a2;
  EtwInitProvider();
  UserData.Ptr = (ULONGLONG)&v5;
  *(_QWORD *)&UserData.Size = 4;
  return EventWrite(RegistrationHandle, EventDescriptor, 1u, &UserData);
}

```

## disassembly

```asm
0x18000ac44  mov     [rsp+arg_8], edx
0x18000ac48  push    rbx
0x18000ac49  sub     rsp, 40h
0x18000ac4d  mov     rax, cs:__security_cookie
0x18000ac54  xor     rax, rsp
0x18000ac57  mov     [rsp+48h+var_18], rax
0x18000ac5c  mov     rbx, rcx
0x18000ac5f  call    EtwInitProvider
0x18000ac64  mov     rcx, cs:RegistrationHandle; RegHandle
0x18000ac6b  lea     rax, [rsp+48h+arg_8]
0x18000ac70  lea     r9, [rsp+48h+UserData]; UserData
0x18000ac75  mov     [rsp+48h+UserData.Ptr], rax
0x18000ac7a  mov     r8d, 1; UserDataCount
0x18000ac80  mov     qword ptr [rsp+48h+UserData.Size], 4
0x18000ac89  mov     rdx, rbx; EventDescriptor
0x18000ac8c  call    cs:__imp_EventWrite
0x18000ac92  mov     rcx, [rsp+48h+var_18]
0x18000ac97  xor     rcx, rsp; StackCookie
0x18000ac9a  call    __security_check_cookie
0x18000ac9f  add     rsp, 40h
0x18000aca3  pop     rbx
0x18000aca4  retn
```
