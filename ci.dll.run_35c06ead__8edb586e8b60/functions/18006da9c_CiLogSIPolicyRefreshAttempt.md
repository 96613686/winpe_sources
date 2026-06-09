# CiLogSIPolicyRefreshAttempt

- ea: `0x18006da9c`
- end: `0x18006db36`
- name: `CiLogSIPolicyRefreshAttempt`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180058048`

## callees

- `0x18002c0d0`
- `0x18006da9c`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006dad0`
- `ntoskrnl!EtwEventEnabled` at `0x18006dad0`
- `ntoskrnl!EtwWrite` at `0x18006db0d`
- `ntoskrnl!EtwWrite` at `0x18006db0d`

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
0x18006da9c  mov     [rsp+arg_0], rbx
0x18006daa1  push    rdi
0x18006daa2  sub     rsp, 50h
0x18006daa6  mov     rax, cs:__security_cookie
0x18006daad  xor     rax, rsp
0x18006dab0  mov     [rsp+58h+var_18], rax
0x18006dab5  mov     rdi, rcx
0x18006dab8  lea     rdx, CiPolicyRefreshAttempted; EventDescriptor
0x18006dabf  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006dac6  xorps   xmm0, xmm0
0x18006dac9  movups  xmmword ptr [rsp+58h+var_28.Ptr], xmm0
0x18006dace  xor     ebx, ebx
0x18006dad0  call    cs:__imp_EtwEventEnabled
0x18006dad7  nop     dword ptr [rax+rax+00h]
0x18006dadc  test    al, al
0x18006dade  jz      short loc_18006DB1B
0x18006dae0  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006dae7  lea     rax, [rsp+58h+var_28]
0x18006daec  lea     r9d, [rbx+1]; UserDataCount
0x18006daf0  mov     [rsp+58h+UserData], rax; UserData
0x18006daf5  xor     r8d, r8d; ActivityId
0x18006daf8  mov     [rsp+58h+var_28.Ptr], rdi
0x18006dafd  lea     rdx, CiPolicyRefreshAttempted; EventDescriptor
0x18006db04  mov     qword ptr [rsp+58h+var_28.Size], 10h
0x18006db0d  call    cs:__imp_EtwWrite
0x18006db14  nop     dword ptr [rax+rax+00h]
0x18006db19  mov     ebx, eax
0x18006db1b  mov     eax, ebx
0x18006db1d  mov     rcx, [rsp+58h+var_18]
0x18006db22  xor     rcx, rsp; StackCookie
0x18006db25  call    __security_check_cookie
0x18006db2a  mov     rbx, [rsp+58h+arg_0]
0x18006db2f  add     rsp, 50h
0x18006db33  pop     rdi
0x18006db34  retn
```
