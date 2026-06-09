# trace_EH_Check

- ea: `0x18000b12c`
- end: `0x18000b1b1`
- name: `trace_EH_Check`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18002b490`
- `0x18002bda0`

## callees

- `0x18000babc`
- `0x180044880`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000b199`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000b199`

## pseudocode

```c
ULONG __fastcall trace_EH_Check(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // [rsp+20h] [rbp-40h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+28h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-28h] BYREF
  int *v7; // [rsp+48h] [rbp-18h]
  __int64 v8; // [rsp+50h] [rbp-10h]

  *(_DWORD *)&EventDescriptor.Id = 301;
  *(_DWORD *)&EventDescriptor.Level = 4;
  EventDescriptor.Keyword = 1;
  v4 = a2;
  EtwInitProvider(a1, a2, a3);
  UserData.Ptr = (ULONGLONG)"admin\\wmi\\winomi\\mp\\perf\\formattedprobe.c";
  *(_QWORD *)&UserData.Size = 42;
  v7 = &v4;
  v8 = 4;
  return EventWrite(RegistrationHandle, &EventDescriptor, 2u, &UserData);
}

```

## disassembly

```asm
0x18000b12c  push    rbp
0x18000b12e  mov     rbp, rsp
0x18000b131  sub     rsp, 60h
0x18000b135  mov     rax, cs:__security_cookie
0x18000b13c  xor     rax, rsp
0x18000b13f  mov     [rbp+var_8], rax
0x18000b143  mov     dword ptr [rbp+EventDescriptor.Id], 12Dh
0x18000b14a  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x18000b151  mov     [rbp+EventDescriptor.Keyword], 1
0x18000b159  mov     [rbp+var_40], edx
0x18000b15c  call    EtwInitProvider
0x18000b161  mov     rcx, cs:RegistrationHandle; RegHandle
0x18000b168  lea     rax, aAdminWmiWinomi_15; "admin\\wmi\\winomi\\mp\\perf\\formatted"...
0x18000b16f  mov     [rbp+UserData.Ptr], rax
0x18000b173  lea     r9, [rbp+UserData]; UserData
0x18000b177  lea     rax, [rbp+var_40]
0x18000b17b  mov     qword ptr [rbp+UserData.Size], 2Ah ; '*'
0x18000b183  mov     r8d, 2; UserDataCount
0x18000b189  mov     [rbp+var_18], rax
0x18000b18d  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x18000b191  mov     [rbp+var_10], 4
0x18000b199  call    cs:__imp_EventWrite
0x18000b19f  mov     rcx, [rbp+var_8]
0x18000b1a3  xor     rcx, rsp; StackCookie
0x18000b1a6  call    __security_check_cookie
0x18000b1ab  add     rsp, 60h
0x18000b1af  pop     rbp
0x18000b1b0  retn
```
