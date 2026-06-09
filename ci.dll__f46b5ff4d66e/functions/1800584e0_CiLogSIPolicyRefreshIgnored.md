# CiLogSIPolicyRefreshIgnored

- ea: `0x1800584e0`
- end: `0x180058596`
- name: `CiLogSIPolicyRefreshIgnored`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180057408`

## callees

- `0x18002bef0`
- `0x1800584e0`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18005851d`
- `ntoskrnl!EtwEventEnabled` at `0x18005851d`
- `ntoskrnl!EtwWrite` at `0x18005856d`
- `ntoskrnl!EtwWrite` at `0x18005856d`

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
0x1800584e0  mov     [rsp+arg_0], rbx
0x1800584e5  mov     [rsp+arg_8], edx
0x1800584e9  push    rdi
0x1800584ea  sub     rsp, 60h
0x1800584ee  mov     rax, cs:__security_cookie
0x1800584f5  xor     rax, rsp
0x1800584f8  mov     [rsp+68h+var_18], rax
0x1800584fd  xorps   xmm0, xmm0
0x180058500  lea     rdx, CiPolicyRefreshIgnored; EventDescriptor
0x180058507  mov     rdi, rcx
0x18005850a  xor     ebx, ebx
0x18005850c  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x180058513  movups  xmmword ptr [rsp+68h+var_38.Ptr], xmm0
0x180058518  movups  [rsp+68h+var_28], xmm0
0x18005851d  call    cs:__imp_EtwEventEnabled
0x180058524  nop     dword ptr [rax+rax+00h]
0x180058529  test    al, al
0x18005852b  jz      short loc_18005857B
0x18005852d  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x180058534  lea     rax, [rsp+68h+arg_8]
0x180058539  mov     qword ptr [rsp+68h+var_28], rax
0x18005853e  lea     r9d, [rbx+2]; UserDataCount
0x180058542  lea     rax, [rsp+68h+var_38]
0x180058547  mov     [rsp+68h+var_38.Ptr], rdi
0x18005854c  xor     r8d, r8d; ActivityId
0x18005854f  mov     [rsp+68h+UserData], rax; UserData
0x180058554  lea     rdx, CiPolicyRefreshIgnored; EventDescriptor
0x18005855b  mov     qword ptr [rsp+68h+var_38.Size], 10h
0x180058564  mov     qword ptr [rsp+68h+var_28+8], 4
0x18005856d  call    cs:__imp_EtwWrite
0x180058574  nop     dword ptr [rax+rax+00h]
0x180058579  mov     ebx, eax
0x18005857b  mov     eax, ebx
0x18005857d  mov     rcx, [rsp+68h+var_18]
0x180058582  xor     rcx, rsp; StackCookie
0x180058585  call    __security_check_cookie
0x18005858a  mov     rbx, [rsp+68h+arg_0]
0x18005858f  add     rsp, 60h
0x180058593  pop     rdi
0x180058594  retn
```
