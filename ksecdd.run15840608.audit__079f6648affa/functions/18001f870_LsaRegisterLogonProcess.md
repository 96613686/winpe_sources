# LsaRegisterLogonProcess

- ea: `0x18001f870`
- end: `0x18001f9dd`
- name: `LsaRegisterLogonProcess`
- size: `365`
- prototype: `NTSTATUS __stdcall(PLSA_STRING LogonProcessName, PHANDLE LsaHandle, PLSA_OPERATIONAL_MODE SecurityMode)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x1800108a0`
- `0x180010a00`
- `0x180010d00`
- `0x18001f310`
- `0x18001f870`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18001f963`
- `ntoskrnl!ZwClose` at `0x18001f963`
- `ntoskrnl!ZwWaitForSingleObject` at `0x18001f950`
- `ntoskrnl!ZwWaitForSingleObject` at `0x18001f950`
- `ntoskrnl!ZwOpenEvent` at `0x18001f936`
- `ntoskrnl!ZwOpenEvent` at `0x18001f936`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001f8f3`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001f8f3`

## string_xrefs

- `0x18001f8e7`: `\SECURITY\LSA_AUTHENTICATION_INITIALIZED`

## pseudocode

```c
NTSTATUS __stdcall LsaRegisterLogonProcess(
        PLSA_STRING LogonProcessName,
        PHANDLE LsaHandle,
        PLSA_OPERATIONAL_MODE SecurityMode)
{
  int v4; // esi
  NTSTATUS result; // eax
  int v7; // edi
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE EventHandle; // [rsp+38h] [rbp-C8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v12[128]; // [rsp+80h] [rbp-80h] BYREF

  v4 = (int)LsaHandle;
  EventHandle = 0;
  DestinationString = 0;
  v8 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset(v12, 0, sizeof(v12));
  if ( LogonProcessName->Length > 0x7Fu )
    return -1073741562;
  RtlInitUnicodeString(&DestinationString, L"\\SECURITY\\LSA_AUTHENTICATION_INITIALIZED");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenEvent(&EventHandle, 0x100000u, &ObjectAttributes);
  if ( result >= 0 )
  {
    v7 = ZwWaitForSingleObject(EventHandle, 1u, 0);
    ZwClose(EventHandle);
    if ( v7 >= 0 )
    {
      if ( LogonProcessName && LogonProcessName->Length )
        memmove(v12, LogonProcessName->Buffer, LogonProcessName->Length);
      result = CreateRpcConnection((unsigned int)v12, 0, v4, (unsigned int)&v8, (__int64)SecurityMode);
      if ( result == -1073741727 )
        return -1073741759;
    }
    else
    {
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001f870  mov     [rsp-8+arg_18], rbx
0x18001f875  push    rbp
0x18001f876  push    rsi
0x18001f877  push    rdi
0x18001f878  push    r14
0x18001f87a  push    r15
0x18001f87c  lea     rbp, [rsp-10h]
0x18001f881  sub     rsp, 110h
0x18001f888  mov     rax, cs:__security_cookie
0x18001f88f  xor     rax, rsp
0x18001f892  mov     [rbp+30h+var_30], rax
0x18001f896  xorps   xmm1, xmm1
0x18001f899  mov     r14, r8
0x18001f89c  mov     rsi, rdx
0x18001f89f  mov     rbx, rcx
0x18001f8a2  xorps   xmm0, xmm0
0x18001f8a5  lea     rcx, [rbp+30h+var_B0]; void *
0x18001f8a9  xor     r15d, r15d
0x18001f8ac  xor     edx, edx; Val
0x18001f8ae  mov     r8d, 80h; Size
0x18001f8b4  mov     [rsp+130h+EventHandle], r15
0x18001f8b9  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x18001f8be  mov     [rsp+130h+var_100], r15d
0x18001f8c3  movups  xmmword ptr [rsp+130h+ObjectAttributes.Length], xmm1
0x18001f8c8  movups  xmmword ptr [rsp+130h+ObjectAttributes.ObjectName], xmm1
0x18001f8cd  movups  xmmword ptr [rsp+130h+ObjectAttributes.SecurityDescriptor], xmm1
0x18001f8d2  call    memset
0x18001f8d7  cmp     word ptr [rbx], 7Fh
0x18001f8db  jbe     short loc_18001F8E7
0x18001f8dd  mov     eax, 0C0000106h
0x18001f8e2  jmp     loc_18001F9B9
0x18001f8e7  lea     rdx, aSecurityLsaAut; "\\SECURITY\\LSA_AUTHENTICATION_INITIALI"...
0x18001f8ee  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x18001f8f3  call    cs:__imp_RtlInitUnicodeString
0x18001f8fa  nop     dword ptr [rax+rax+00h]
0x18001f8ff  lea     rax, [rsp+130h+DestinationString]
0x18001f904  mov     [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x18001f90c  xorps   xmm0, xmm0
0x18001f90f  mov     [rsp+130h+ObjectAttributes.ObjectName], rax
0x18001f914  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x18001f919  mov     [rsp+130h+ObjectAttributes.RootDirectory], r15
0x18001f91e  mov     edx, 100000h; DesiredAccess
0x18001f923  mov     [rsp+130h+ObjectAttributes.Attributes], 240h
0x18001f92b  lea     rcx, [rsp+130h+EventHandle]; EventHandle
0x18001f930  movdqu  xmmword ptr [rsp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001f936  call    cs:__imp_ZwOpenEvent
0x18001f93d  nop     dword ptr [rax+rax+00h]
0x18001f942  test    eax, eax
0x18001f944  js      short loc_18001F9B9
0x18001f946  mov     rcx, [rsp+130h+EventHandle]; Handle
0x18001f94b  xor     r8d, r8d; Timeout
0x18001f94e  mov     dl, 1; Alertable
0x18001f950  call    cs:__imp_ZwWaitForSingleObject
0x18001f957  nop     dword ptr [rax+rax+00h]
0x18001f95c  mov     rcx, [rsp+130h+EventHandle]; Handle
0x18001f961  mov     edi, eax
0x18001f963  call    cs:__imp_ZwClose
0x18001f96a  nop     dword ptr [rax+rax+00h]
0x18001f96f  test    edi, edi
0x18001f971  jns     short loc_18001F977
0x18001f973  mov     eax, edi
0x18001f975  jmp     short loc_18001F9B9
0x18001f977  test    rbx, rbx
0x18001f97a  jz      short loc_18001F994
0x18001f97c  movzx   eax, word ptr [rbx]
0x18001f97f  test    ax, ax
0x18001f982  jz      short loc_18001F994
0x18001f984  mov     rdx, [rbx+8]; Src
0x18001f988  lea     rcx, [rbp+30h+var_B0]; void *
0x18001f98c  mov     r8d, eax; Size
0x18001f98f  call    memmove
0x18001f994  lea     r9, [rsp+130h+var_100]
0x18001f999  mov     [rsp+130h+var_110], r14
0x18001f99e  mov     r8, rsi
0x18001f9a1  lea     rcx, [rbp+30h+var_B0]
0x18001f9a5  xor     edx, edx
0x18001f9a7  call    CreateRpcConnection
0x18001f9ac  cmp     eax, 0C0000061h
0x18001f9b1  mov     ecx, 0C0000041h
0x18001f9b6  cmovz   eax, ecx
0x18001f9b9  mov     rcx, [rbp+30h+var_30]
0x18001f9bd  xor     rcx, rsp; StackCookie
0x18001f9c0  call    __security_check_cookie
0x18001f9c5  mov     rbx, [rsp+130h+arg_18]
0x18001f9cd  add     rsp, 110h
0x18001f9d4  pop     r15
0x18001f9d6  pop     r14
0x18001f9d8  pop     rdi
0x18001f9d9  pop     rsi
0x18001f9da  pop     rbp
0x18001f9db  retn
```
