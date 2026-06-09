# trace_Logger_CleanupLoggerFiles

- ea: `0x18000b2f8`
- end: `0x18000b3ab`
- name: `trace_Logger_CleanupLoggerFiles`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800272c0`

## callees

- `0x18000b2f8`
- `0x18000babc`
- `0x180044880`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000b389`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000b389`

## pseudocode

```c
ULONG __fastcall trace_Logger_CleanupLoggerFiles(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rax
  int v5; // eax
  int v7; // [rsp+20h] [rbp-40h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+28h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-28h] BYREF
  __int64 v10; // [rsp+48h] [rbp-18h]
  int v11; // [rsp+50h] [rbp-10h]
  int v12; // [rsp+54h] [rbp-Ch]

  *(_DWORD *)&EventDescriptor.Id = 10309;
  *(_DWORD *)&EventDescriptor.Level = 4;
  EventDescriptor.Keyword = 1;
  v7 = a1;
  EtwInitProvider(a1, a2, a3);
  *(_QWORD *)&UserData.Size = 4;
  UserData.Ptr = (ULONGLONG)&v7;
  v10 = a2;
  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(a2 + 2 * v4) );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 0;
  }
  v11 = v5;
  v12 = 0;
  return EventWrite(RegistrationHandle, &EventDescriptor, 2u, &UserData);
}

```

## disassembly

```asm
0x18000b2f8  mov     [rsp-8+arg_0], rbx
0x18000b2fd  mov     [rsp-8+arg_8], rdi
0x18000b302  push    rbp
0x18000b303  mov     rbp, rsp
0x18000b306  sub     rsp, 60h
0x18000b30a  mov     rax, cs:__security_cookie
0x18000b311  xor     rax, rsp
0x18000b314  mov     [rbp+var_8], rax
0x18000b318  mov     rbx, rdx
0x18000b31b  mov     dword ptr [rbp+EventDescriptor.Id], 2845h
0x18000b322  xor     edi, edi
0x18000b324  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x18000b32b  mov     [rbp+EventDescriptor.Keyword], 1
0x18000b333  mov     [rbp+var_40], ecx
0x18000b336  call    EtwInitProvider
0x18000b33b  mov     qword ptr [rbp+UserData.Size], 4
0x18000b343  lea     rax, [rbp+var_40]
0x18000b347  mov     [rbp+UserData.Ptr], rax
0x18000b34b  mov     [rbp+var_18], rbx
0x18000b34f  test    rbx, rbx
0x18000b352  jz      short loc_18000B36B
0x18000b354  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b358  inc     rax
0x18000b35b  cmp     [rbx+rax*2], di
0x18000b35f  jnz     short loc_18000B358
0x18000b361  lea     rax, ds:2[rax*2]
0x18000b369  jmp     short loc_18000B36E
0x18000b36b  mov     rax, rdi
0x18000b36e  mov     rcx, cs:RegistrationHandle; RegHandle
0x18000b375  lea     r9, [rbp+UserData]; UserData
0x18000b379  mov     r8d, 2; UserDataCount
0x18000b37f  mov     [rbp+var_10], eax
0x18000b382  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x18000b386  mov     [rbp+var_C], edi
0x18000b389  call    cs:__imp_EventWrite
0x18000b38f  mov     rcx, [rbp+var_8]
0x18000b393  xor     rcx, rsp; StackCookie
0x18000b396  call    __security_check_cookie
0x18000b39b  mov     rbx, [rsp+60h+arg_0]
0x18000b3a0  mov     rdi, [rsp+60h+arg_8]
0x18000b3a5  add     rsp, 60h
0x18000b3a9  pop     rbp
0x18000b3aa  retn
```
