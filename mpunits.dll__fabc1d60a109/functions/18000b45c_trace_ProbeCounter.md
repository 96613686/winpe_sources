# trace_ProbeCounter

- ea: `0x18000b45c`
- end: `0x18000b50f`
- name: `trace_ProbeCounter`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002b490`

## callees

- `0x18000b45c`
- `0x18000babc`
- `0x180044880`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000b4ed`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000b4ed`

## pseudocode

```c
ULONG __fastcall trace_ProbeCounter(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rax
  int v5; // eax
  int v7; // [rsp+20h] [rbp-40h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+28h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-28h] BYREF
  __int64 v10; // [rsp+48h] [rbp-18h]
  int v11; // [rsp+50h] [rbp-10h]
  int v12; // [rsp+54h] [rbp-Ch]

  *(_DWORD *)&EventDescriptor.Id = 10301;
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
0x18000b45c  mov     [rsp-8+arg_0], rbx
0x18000b461  mov     [rsp-8+arg_8], rdi
0x18000b466  push    rbp
0x18000b467  mov     rbp, rsp
0x18000b46a  sub     rsp, 60h
0x18000b46e  mov     rax, cs:__security_cookie
0x18000b475  xor     rax, rsp
0x18000b478  mov     [rbp+var_8], rax
0x18000b47c  mov     rbx, rdx
0x18000b47f  mov     dword ptr [rbp+EventDescriptor.Id], 283Dh
0x18000b486  xor     edi, edi
0x18000b488  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x18000b48f  mov     [rbp+EventDescriptor.Keyword], 1
0x18000b497  mov     [rbp+var_40], ecx
0x18000b49a  call    EtwInitProvider
0x18000b49f  mov     qword ptr [rbp+UserData.Size], 4
0x18000b4a7  lea     rax, [rbp+var_40]
0x18000b4ab  mov     [rbp+UserData.Ptr], rax
0x18000b4af  mov     [rbp+var_18], rbx
0x18000b4b3  test    rbx, rbx
0x18000b4b6  jz      short loc_18000B4CF
0x18000b4b8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b4bc  inc     rax
0x18000b4bf  cmp     [rbx+rax*2], di
0x18000b4c3  jnz     short loc_18000B4BC
0x18000b4c5  lea     rax, ds:2[rax*2]
0x18000b4cd  jmp     short loc_18000B4D2
0x18000b4cf  mov     rax, rdi
0x18000b4d2  mov     rcx, cs:RegistrationHandle; RegHandle
0x18000b4d9  lea     r9, [rbp+UserData]; UserData
0x18000b4dd  mov     r8d, 2; UserDataCount
0x18000b4e3  mov     [rbp+var_10], eax
0x18000b4e6  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x18000b4ea  mov     [rbp+var_C], edi
0x18000b4ed  call    cs:__imp_EventWrite
0x18000b4f3  mov     rcx, [rbp+var_8]
0x18000b4f7  xor     rcx, rsp; StackCookie
0x18000b4fa  call    __security_check_cookie
0x18000b4ff  mov     rbx, [rsp+60h+arg_0]
0x18000b504  mov     rdi, [rsp+60h+arg_8]
0x18000b509  add     rsp, 60h
0x18000b50d  pop     rbp
0x18000b50e  retn
```
