# CiLogSIPolicyRefreshFinished

- ea: `0x18006db3c`
- end: `0x18006dbeb`
- name: `CiLogSIPolicyRefreshFinished`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180058048`

## callees

- `0x18002c0d0`
- `0x18006db3c`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006db78`
- `ntoskrnl!EtwEventEnabled` at `0x18006db78`
- `ntoskrnl!EtwWrite` at `0x18006dbcc`
- `ntoskrnl!EtwWrite` at `0x18006dbcc`

## pseudocode

```c
NTSTATUS __fastcall CiLogSIPolicyRefreshFinished(__int64 a1, int a2)
{
  int v3; // [rsp+30h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-28h] BYREF
  __int128 v5; // [rsp+48h] [rbp-18h]
  int v6; // [rsp+78h] [rbp+18h] BYREF

  v6 = a2;
  UserData = 0;
  v3 = g_NumberOfSiPolicies;
  v5 = 0;
  if ( !EtwEventEnabled(g_EtwEventHandle, &CiPolicyRefreshFinished) )
    return 0;
  UserData.Ptr = (ULONGLONG)&v3;
  *(_QWORD *)&UserData.Size = 4;
  *(_QWORD *)&v5 = &v6;
  *((_QWORD *)&v5 + 1) = 4;
  return EtwWrite(g_EtwEventHandle, &CiPolicyRefreshFinished, 0, 2u, &UserData);
}

```

## disassembly

```asm
0x18006db3c  mov     [rsp-8+arg_8], edx
0x18006db40  push    rbp
0x18006db41  mov     rbp, rsp
0x18006db44  sub     rsp, 60h
0x18006db48  mov     rax, cs:__security_cookie
0x18006db4f  xor     rax, rsp
0x18006db52  mov     [rbp+var_8], rax
0x18006db56  mov     eax, cs:g_NumberOfSiPolicies
0x18006db5c  lea     rdx, CiPolicyRefreshFinished; EventDescriptor
0x18006db63  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006db6a  xorps   xmm0, xmm0
0x18006db6d  movups  xmmword ptr [rbp+var_28.Ptr], xmm0
0x18006db71  mov     [rbp+var_30], eax
0x18006db74  movups  [rbp+var_18], xmm0
0x18006db78  call    cs:__imp_EtwEventEnabled
0x18006db7f  nop     dword ptr [rax+rax+00h]
0x18006db84  test    al, al
0x18006db86  jnz     short loc_18006DB8C
0x18006db88  xor     eax, eax
0x18006db8a  jmp     short loc_18006DBD8
0x18006db8c  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006db93  lea     rax, [rbp+var_30]
0x18006db97  mov     [rbp+var_28.Ptr], rax
0x18006db9b  lea     rdx, CiPolicyRefreshFinished; EventDescriptor
0x18006dba2  lea     rax, [rbp+arg_8]
0x18006dba6  mov     qword ptr [rbp+var_28.Size], 4
0x18006dbae  mov     qword ptr [rbp+var_18], rax
0x18006dbb2  mov     r9d, 2; UserDataCount
0x18006dbb8  lea     rax, [rbp+var_28]
0x18006dbbc  mov     qword ptr [rbp+var_18+8], 4
0x18006dbc4  xor     r8d, r8d; ActivityId
0x18006dbc7  mov     [rsp+60h+UserData], rax; UserData
0x18006dbcc  call    cs:__imp_EtwWrite
0x18006dbd3  nop     dword ptr [rax+rax+00h]
0x18006dbd8  mov     rcx, [rbp+var_8]
0x18006dbdc  xor     rcx, rsp; StackCookie
0x18006dbdf  call    __security_check_cookie
0x18006dbe4  add     rsp, 60h
0x18006dbe8  pop     rbp
0x18006dbe9  retn
```
