# CiLogSIPolicyRefreshFinished

- ea: `0x18006d85c`
- end: `0x18006d90b`
- name: `CiLogSIPolicyRefreshFinished`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180058120`

## callees

- `0x18002bf20`
- `0x18006d85c`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006d898`
- `ntoskrnl!EtwEventEnabled` at `0x18006d898`
- `ntoskrnl!EtwWrite` at `0x18006d8ec`
- `ntoskrnl!EtwWrite` at `0x18006d8ec`

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
0x18006d85c  mov     [rsp-8+arg_8], edx
0x18006d860  push    rbp
0x18006d861  mov     rbp, rsp
0x18006d864  sub     rsp, 60h
0x18006d868  mov     rax, cs:__security_cookie
0x18006d86f  xor     rax, rsp
0x18006d872  mov     [rbp+var_8], rax
0x18006d876  mov     eax, cs:g_NumberOfSiPolicies
0x18006d87c  lea     rdx, CiPolicyRefreshFinished; EventDescriptor
0x18006d883  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d88a  xorps   xmm0, xmm0
0x18006d88d  movups  xmmword ptr [rbp+var_28.Ptr], xmm0
0x18006d891  mov     [rbp+var_30], eax
0x18006d894  movups  [rbp+var_18], xmm0
0x18006d898  call    cs:__imp_EtwEventEnabled
0x18006d89f  nop     dword ptr [rax+rax+00h]
0x18006d8a4  test    al, al
0x18006d8a6  jnz     short loc_18006D8AC
0x18006d8a8  xor     eax, eax
0x18006d8aa  jmp     short loc_18006D8F8
0x18006d8ac  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d8b3  lea     rax, [rbp+var_30]
0x18006d8b7  mov     [rbp+var_28.Ptr], rax
0x18006d8bb  lea     rdx, CiPolicyRefreshFinished; EventDescriptor
0x18006d8c2  lea     rax, [rbp+arg_8]
0x18006d8c6  mov     qword ptr [rbp+var_28.Size], 4
0x18006d8ce  mov     qword ptr [rbp+var_18], rax
0x18006d8d2  mov     r9d, 2; UserDataCount
0x18006d8d8  lea     rax, [rbp+var_28]
0x18006d8dc  mov     qword ptr [rbp+var_18+8], 4
0x18006d8e4  xor     r8d, r8d; ActivityId
0x18006d8e7  mov     [rsp+60h+UserData], rax; UserData
0x18006d8ec  call    cs:__imp_EtwWrite
0x18006d8f3  nop     dword ptr [rax+rax+00h]
0x18006d8f8  mov     rcx, [rbp+var_8]
0x18006d8fc  xor     rcx, rsp; StackCookie
0x18006d8ff  call    __security_check_cookie
0x18006d904  add     rsp, 60h
0x18006d908  pop     rbp
0x18006d909  retn
```
