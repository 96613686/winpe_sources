# KclSetSymbolicLinkObjectSecurity

- ea: `0x140040470`
- end: `0x140040528`
- name: `KclSetSymbolicLinkObjectSecurity`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002b374`

## callees

- `0x140011650`
- `0x140040470`

## import_xrefs

- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x1400404cb`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x1400404cb`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400404e6`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400404e6`
- `ntoskrnl!ZwClose` at `0x1400404fd`
- `ntoskrnl!ZwClose` at `0x1400404fd`

## pseudocode

```c
__int64 __fastcall KclSetSymbolicLinkObjectSecurity(struct _UNICODE_STRING *a1, SECURITY_INFORMATION a2, void *a3)
{
  NTSTATUS v5; // ebx
  void *LinkHandle; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+28h] [rbp-38h] BYREF

  ObjectAttributes.ObjectName = a1;
  LinkHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenSymbolicLinkObject(&LinkHandle, 0x1F0000u, &ObjectAttributes);
  if ( v5 >= 0 )
    v5 = ZwSetSecurityObject(LinkHandle, a2, a3);
  if ( LinkHandle )
    ZwClose(LinkHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140040470  mov     [rsp-18h+arg_18], rbx
0x140040475  push    rbp
0x140040476  push    rsi
0x140040477  push    rdi
0x140040478  mov     rbp, rsp
0x14004047b  sub     rsp, 60h
0x14004047f  mov     rax, cs:__security_cookie
0x140040486  xor     rax, rsp
0x140040489  mov     [rbp+var_8], rax
0x14004048d  mov     rsi, r8
0x140040490  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x140040494  mov     edi, edx
0x140040496  mov     [rbp+LinkHandle], 0
0x14004049e  xorps   xmm0, xmm0
0x1400404a1  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400404a9  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400404ad  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x1400404b5  mov     edx, 1F0000h; DesiredAccess
0x1400404ba  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400404c2  lea     rcx, [rbp+LinkHandle]; LinkHandle
0x1400404c6  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400404cb  call    cs:__imp_ZwOpenSymbolicLinkObject
0x1400404d2  nop     dword ptr [rax+rax+00h]
0x1400404d7  mov     ebx, eax
0x1400404d9  test    eax, eax
0x1400404db  js      short loc_1400404F4
0x1400404dd  mov     rcx, [rbp+LinkHandle]; Handle
0x1400404e1  mov     r8, rsi; SecurityDescriptor
0x1400404e4  mov     edx, edi; SecurityInformation
0x1400404e6  call    cs:__imp_ZwSetSecurityObject
0x1400404ed  nop     dword ptr [rax+rax+00h]
0x1400404f2  mov     ebx, eax
0x1400404f4  mov     rcx, [rbp+LinkHandle]; Handle
0x1400404f8  test    rcx, rcx
0x1400404fb  jz      short loc_140040509
0x1400404fd  call    cs:__imp_ZwClose
0x140040504  nop     dword ptr [rax+rax+00h]
0x140040509  mov     eax, ebx
0x14004050b  mov     rcx, [rbp+var_8]
0x14004050f  xor     rcx, rsp; StackCookie
0x140040512  call    __security_check_cookie
0x140040517  mov     rbx, [rsp+60h+arg_18]
0x14004051f  add     rsp, 60h
0x140040523  pop     rdi
0x140040524  pop     rsi
0x140040525  pop     rbp
0x140040526  retn
```
