# CiLogSIPolicyRefreshAttempt

- ea: `0x18006c9e8`
- end: `0x18006ca82`
- name: `CiLogSIPolicyRefreshAttempt`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180057408`

## callees

- `0x18002bef0`
- `0x18006c9e8`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006ca1c`
- `ntoskrnl!EtwEventEnabled` at `0x18006ca1c`
- `ntoskrnl!EtwWrite` at `0x18006ca59`
- `ntoskrnl!EtwWrite` at `0x18006ca59`

## pseudocode

```c
__int64 __fastcall CiLogSIPolicyRefreshAttempt(ULONGLONG a1)
{
  unsigned int v2; // ebx
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-28h] BYREF

  UserData = 0;
  v2 = 0;
  if ( EtwEventEnabled(g_EtwEventHandle, &CiPolicyRefreshAttempted) )
  {
    UserData.Ptr = a1;
    *(_QWORD *)&UserData.Size = 16;
    return (unsigned int)EtwWrite(g_EtwEventHandle, &CiPolicyRefreshAttempted, 0, 1u, &UserData);
  }
  return v2;
}

```

## disassembly

```asm
0x18006c9e8  mov     [rsp+arg_0], rbx
0x18006c9ed  push    rdi
0x18006c9ee  sub     rsp, 50h
0x18006c9f2  mov     rax, cs:__security_cookie
0x18006c9f9  xor     rax, rsp
0x18006c9fc  mov     [rsp+58h+var_18], rax
0x18006ca01  mov     rdi, rcx
0x18006ca04  lea     rdx, CiPolicyRefreshAttempted; EventDescriptor
0x18006ca0b  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006ca12  xorps   xmm0, xmm0
0x18006ca15  movups  xmmword ptr [rsp+58h+var_28.Ptr], xmm0
0x18006ca1a  xor     ebx, ebx
0x18006ca1c  call    cs:__imp_EtwEventEnabled
0x18006ca23  nop     dword ptr [rax+rax+00h]
0x18006ca28  test    al, al
0x18006ca2a  jz      short loc_18006CA67
0x18006ca2c  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006ca33  lea     rax, [rsp+58h+var_28]
0x18006ca38  lea     r9d, [rbx+1]; UserDataCount
0x18006ca3c  mov     [rsp+58h+UserData], rax; UserData
0x18006ca41  xor     r8d, r8d; ActivityId
0x18006ca44  mov     [rsp+58h+var_28.Ptr], rdi
0x18006ca49  lea     rdx, CiPolicyRefreshAttempted; EventDescriptor
0x18006ca50  mov     qword ptr [rsp+58h+var_28.Size], 10h
0x18006ca59  call    cs:__imp_EtwWrite
0x18006ca60  nop     dword ptr [rax+rax+00h]
0x18006ca65  mov     ebx, eax
0x18006ca67  mov     eax, ebx
0x18006ca69  mov     rcx, [rsp+58h+var_18]
0x18006ca6e  xor     rcx, rsp; StackCookie
0x18006ca71  call    __security_check_cookie
0x18006ca76  mov     rbx, [rsp+58h+arg_0]
0x18006ca7b  add     rsp, 50h
0x18006ca7f  pop     rdi
0x18006ca80  retn
```
