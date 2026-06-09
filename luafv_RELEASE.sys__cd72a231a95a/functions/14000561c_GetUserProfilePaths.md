# GetUserProfilePaths

- ea: `0x14000561c`
- end: `0x140005724`
- name: `GetUserProfilePaths`
- size: `264`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140001f7c`
- `0x1400047cc`

## callees

- `0x14000561c`
- `0x140005800`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14000567b`
- `ntoskrnl!ZwOpenKey` at `0x1400056c0`
- `ntoskrnl!ZwOpenKey` at `0x14000567b`
- `ntoskrnl!ZwOpenKey` at `0x1400056c0`
- `ntoskrnl!ZwClose` at `0x1400056ed`
- `ntoskrnl!ZwClose` at `0x140005702`
- `ntoskrnl!ZwClose` at `0x1400056ed`
- `ntoskrnl!ZwClose` at `0x140005702`

## pseudocode

```c
__int64 __fastcall GetUserProfilePaths(__int64 a1)
{
  NTSTATUS ProfilePaths; // edi
  void *v3; // rbx
  struct _OBJECT_ATTRIBUTES v5; // [rsp+20h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  HANDLE Handle; // [rsp+A8h] [rbp+28h] BYREF
  void *KeyHandle; // [rsp+B0h] [rbp+30h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  Handle = 0;
  KeyHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&g_ProfileKeyPath;
  memset(&v5, 0, 44);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ProfilePaths = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( ProfilePaths >= 0 )
  {
    v3 = KeyHandle;
    v5.RootDirectory = KeyHandle;
    v5.ObjectName = (PUNICODE_STRING)(a1 + 88);
    v5.Length = 48;
    v5.Attributes = 576;
    *(_OWORD *)&v5.SecurityDescriptor = 0;
    ProfilePaths = ZwOpenKey(&Handle, 0x20019u, &v5);
    if ( ProfilePaths >= 0 )
      ProfilePaths = QueryProfilePaths(Handle);
    if ( v3 )
      ZwClose(v3);
  }
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)ProfilePaths;
}

```

## disassembly

```asm
0x14000561c  mov     [rsp-18h+arg_0], rbx
0x140005621  push    rbp
0x140005622  push    rsi
0x140005623  push    rdi
0x140005624  mov     rbp, rsp
0x140005627  sub     rsp, 80h
0x14000562e  xor     eax, eax
0x140005630  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140005638  xorps   xmm0, xmm0
0x14000563b  mov     [rbp+Handle], rax
0x14000563f  mov     [rbp+KeyHandle], rax
0x140005643  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140005647  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x14000564b  mov     rsi, rcx
0x14000564e  lea     rax, g_ProfileKeyPath
0x140005655  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14000565d  movups  xmmword ptr [rbp+var_60.ObjectName], xmm0
0x140005661  mov     edx, 20019h; DesiredAccess
0x140005666  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000566a  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000566e  movups  xmmword ptr [rbp+var_60.Length], xmm0
0x140005672  movups  xmmword ptr [rbp+var_60+1Ch], xmm0
0x140005676  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000567b  call    cs:__imp_ZwOpenKey
0x140005682  nop     dword ptr [rax+rax+00h]
0x140005687  mov     edi, eax
0x140005689  test    eax, eax
0x14000568b  js      short loc_1400056F9
0x14000568d  mov     rbx, [rbp+KeyHandle]
0x140005691  lea     rax, [rsi+58h]
0x140005695  xorps   xmm0, xmm0
0x140005698  mov     [rbp+var_60.RootDirectory], rbx
0x14000569c  lea     r8, [rbp+var_60]; ObjectAttributes
0x1400056a0  mov     [rbp+var_60.ObjectName], rax
0x1400056a4  mov     edx, 20019h; DesiredAccess
0x1400056a9  mov     [rbp+var_60.Length], 30h ; '0'
0x1400056b0  lea     rcx, [rbp+Handle]; KeyHandle
0x1400056b4  mov     [rbp+var_60.Attributes], 240h
0x1400056bb  movdqu  xmmword ptr [rbp+var_60.SecurityDescriptor], xmm0
0x1400056c0  call    cs:__imp_ZwOpenKey
0x1400056c7  nop     dword ptr [rax+rax+00h]
0x1400056cc  mov     edi, eax
0x1400056ce  test    eax, eax
0x1400056d0  js      short loc_1400056E5
0x1400056d2  mov     rcx, [rbp+Handle]; KeyHandle
0x1400056d6  lea     r8, [rsi+78h]
0x1400056da  lea     rdx, [rsi+68h]
0x1400056de  call    QueryProfilePaths
0x1400056e3  mov     edi, eax
0x1400056e5  test    rbx, rbx
0x1400056e8  jz      short loc_1400056F9
0x1400056ea  mov     rcx, rbx; Handle
0x1400056ed  call    cs:__imp_ZwClose
0x1400056f4  nop     dword ptr [rax+rax+00h]
0x1400056f9  mov     rcx, [rbp+Handle]; Handle
0x1400056fd  test    rcx, rcx
0x140005700  jz      short loc_14000570E
0x140005702  call    cs:__imp_ZwClose
0x140005709  nop     dword ptr [rax+rax+00h]
0x14000570e  mov     rbx, [rsp+80h+arg_0]
0x140005716  mov     eax, edi
0x140005718  add     rsp, 80h
0x14000571f  pop     rdi
0x140005720  pop     rsi
0x140005721  pop     rbp
0x140005722  retn
```
