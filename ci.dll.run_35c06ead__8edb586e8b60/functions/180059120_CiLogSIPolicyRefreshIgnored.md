# CiLogSIPolicyRefreshIgnored

- ea: `0x180059120`
- end: `0x1800591d6`
- name: `CiLogSIPolicyRefreshIgnored`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180058048`

## callees

- `0x18002c0d0`
- `0x180059120`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18005915d`
- `ntoskrnl!EtwEventEnabled` at `0x18005915d`
- `ntoskrnl!EtwWrite` at `0x1800591ad`
- `ntoskrnl!EtwWrite` at `0x1800591ad`

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
0x180059120  mov     [rsp+arg_0], rbx
0x180059125  mov     [rsp+arg_8], edx
0x180059129  push    rdi
0x18005912a  sub     rsp, 60h
0x18005912e  mov     rax, cs:__security_cookie
0x180059135  xor     rax, rsp
0x180059138  mov     [rsp+68h+var_18], rax
0x18005913d  xorps   xmm0, xmm0
0x180059140  lea     rdx, CiPolicyRefreshIgnored; EventDescriptor
0x180059147  mov     rdi, rcx
0x18005914a  xor     ebx, ebx
0x18005914c  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x180059153  movups  xmmword ptr [rsp+68h+var_38.Ptr], xmm0
0x180059158  movups  [rsp+68h+var_28], xmm0
0x18005915d  call    cs:__imp_EtwEventEnabled
0x180059164  nop     dword ptr [rax+rax+00h]
0x180059169  test    al, al
0x18005916b  jz      short loc_1800591BB
0x18005916d  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x180059174  lea     rax, [rsp+68h+arg_8]
0x180059179  mov     qword ptr [rsp+68h+var_28], rax
0x18005917e  lea     r9d, [rbx+2]; UserDataCount
0x180059182  lea     rax, [rsp+68h+var_38]
0x180059187  mov     [rsp+68h+var_38.Ptr], rdi
0x18005918c  xor     r8d, r8d; ActivityId
0x18005918f  mov     [rsp+68h+UserData], rax; UserData
0x180059194  lea     rdx, CiPolicyRefreshIgnored; EventDescriptor
0x18005919b  mov     qword ptr [rsp+68h+var_38.Size], 10h
0x1800591a4  mov     qword ptr [rsp+68h+var_28+8], 4
0x1800591ad  call    cs:__imp_EtwWrite
0x1800591b4  nop     dword ptr [rax+rax+00h]
0x1800591b9  mov     ebx, eax
0x1800591bb  mov     eax, ebx
0x1800591bd  mov     rcx, [rsp+68h+var_18]
0x1800591c2  xor     rcx, rsp; StackCookie
0x1800591c5  call    __security_check_cookie
0x1800591ca  mov     rbx, [rsp+68h+arg_0]
0x1800591cf  add     rsp, 60h
0x1800591d3  pop     rdi
0x1800591d4  retn
```
