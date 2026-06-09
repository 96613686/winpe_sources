# CiLogSIPolicyRefreshIgnored

- ea: `0x1800591f8`
- end: `0x1800592ae`
- name: `CiLogSIPolicyRefreshIgnored`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180058120`

## callees

- `0x18002bf20`
- `0x1800591f8`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x180059235`
- `ntoskrnl!EtwEventEnabled` at `0x180059235`
- `ntoskrnl!EtwWrite` at `0x180059285`
- `ntoskrnl!EtwWrite` at `0x180059285`

## pseudocode

```c
__int64 __fastcall CiLogSIPolicyRefreshIgnored(ULONGLONG a1, int a2)
{
  unsigned int v3; // ebx
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-38h] BYREF
  __int128 v6; // [rsp+40h] [rbp-28h]
  int v7; // [rsp+78h] [rbp+10h] BYREF

  v7 = a2;
  v3 = 0;
  UserData = 0;
  v6 = 0;
  if ( EtwEventEnabled(g_EtwEventHandle, &CiPolicyRefreshIgnored) )
  {
    *(_QWORD *)&v6 = &v7;
    UserData.Ptr = a1;
    *(_QWORD *)&UserData.Size = 16;
    *((_QWORD *)&v6 + 1) = 4;
    return (unsigned int)EtwWrite(g_EtwEventHandle, &CiPolicyRefreshIgnored, 0, 2u, &UserData);
  }
  return v3;
}

```

## disassembly

```asm
0x1800591f8  mov     [rsp+arg_0], rbx
0x1800591fd  mov     [rsp+arg_8], edx
0x180059201  push    rdi
0x180059202  sub     rsp, 60h
0x180059206  mov     rax, cs:__security_cookie
0x18005920d  xor     rax, rsp
0x180059210  mov     [rsp+68h+var_18], rax
0x180059215  xorps   xmm0, xmm0
0x180059218  lea     rdx, CiPolicyRefreshIgnored; EventDescriptor
0x18005921f  mov     rdi, rcx
0x180059222  xor     ebx, ebx
0x180059224  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18005922b  movups  xmmword ptr [rsp+68h+var_38.Ptr], xmm0
0x180059230  movups  [rsp+68h+var_28], xmm0
0x180059235  call    cs:__imp_EtwEventEnabled
0x18005923c  nop     dword ptr [rax+rax+00h]
0x180059241  test    al, al
0x180059243  jz      short loc_180059293
0x180059245  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18005924c  lea     rax, [rsp+68h+arg_8]
0x180059251  mov     qword ptr [rsp+68h+var_28], rax
0x180059256  lea     r9d, [rbx+2]; UserDataCount
0x18005925a  lea     rax, [rsp+68h+var_38]
0x18005925f  mov     [rsp+68h+var_38.Ptr], rdi
0x180059264  xor     r8d, r8d; ActivityId
0x180059267  mov     [rsp+68h+UserData], rax; UserData
0x18005926c  lea     rdx, CiPolicyRefreshIgnored; EventDescriptor
0x180059273  mov     qword ptr [rsp+68h+var_38.Size], 10h
0x18005927c  mov     qword ptr [rsp+68h+var_28+8], 4
0x180059285  call    cs:__imp_EtwWrite
0x18005928c  nop     dword ptr [rax+rax+00h]
0x180059291  mov     ebx, eax
0x180059293  mov     eax, ebx
0x180059295  mov     rcx, [rsp+68h+var_18]
0x18005929a  xor     rcx, rsp; StackCookie
0x18005929d  call    __security_check_cookie
0x1800592a2  mov     rbx, [rsp+68h+arg_0]
0x1800592a7  add     rsp, 60h
0x1800592ab  pop     rdi
0x1800592ac  retn
```
