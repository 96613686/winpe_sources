# CiLogSIPolicyRefreshAttempt

- ea: `0x18006d7bc`
- end: `0x18006d856`
- name: `CiLogSIPolicyRefreshAttempt`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180058120`

## callees

- `0x18002bf20`
- `0x18006d7bc`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006d7f0`
- `ntoskrnl!EtwEventEnabled` at `0x18006d7f0`
- `ntoskrnl!EtwWrite` at `0x18006d82d`
- `ntoskrnl!EtwWrite` at `0x18006d82d`

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
0x18006d7bc  mov     [rsp+arg_0], rbx
0x18006d7c1  push    rdi
0x18006d7c2  sub     rsp, 50h
0x18006d7c6  mov     rax, cs:__security_cookie
0x18006d7cd  xor     rax, rsp
0x18006d7d0  mov     [rsp+58h+var_18], rax
0x18006d7d5  mov     rdi, rcx
0x18006d7d8  lea     rdx, CiPolicyRefreshAttempted; EventDescriptor
0x18006d7df  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d7e6  xorps   xmm0, xmm0
0x18006d7e9  movups  xmmword ptr [rsp+58h+var_28.Ptr], xmm0
0x18006d7ee  xor     ebx, ebx
0x18006d7f0  call    cs:__imp_EtwEventEnabled
0x18006d7f7  nop     dword ptr [rax+rax+00h]
0x18006d7fc  test    al, al
0x18006d7fe  jz      short loc_18006D83B
0x18006d800  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d807  lea     rax, [rsp+58h+var_28]
0x18006d80c  lea     r9d, [rbx+1]; UserDataCount
0x18006d810  mov     [rsp+58h+UserData], rax; UserData
0x18006d815  xor     r8d, r8d; ActivityId
0x18006d818  mov     [rsp+58h+var_28.Ptr], rdi
0x18006d81d  lea     rdx, CiPolicyRefreshAttempted; EventDescriptor
0x18006d824  mov     qword ptr [rsp+58h+var_28.Size], 10h
0x18006d82d  call    cs:__imp_EtwWrite
0x18006d834  nop     dword ptr [rax+rax+00h]
0x18006d839  mov     ebx, eax
0x18006d83b  mov     eax, ebx
0x18006d83d  mov     rcx, [rsp+58h+var_18]
0x18006d842  xor     rcx, rsp; StackCookie
0x18006d845  call    __security_check_cookie
0x18006d84a  mov     rbx, [rsp+58h+arg_0]
0x18006d84f  add     rsp, 50h
0x18006d853  pop     rdi
0x18006d854  retn
```
