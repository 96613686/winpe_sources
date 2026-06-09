# FltpOpenInstancesRegistryKey

- ea: `0x18006a860`
- end: `0x18006aac7`
- name: `FltpOpenInstancesRegistryKey`
- size: `615`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180055154`
- `0x1800698d0`
- `0x18006b340`

## callees

- `0x180009f20`
- `0x180024800`
- `0x18006a860`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x18006a9c0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18006a9c0`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18006a9d9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18006a9d9`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006a8c1`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006a8c1`
- `ntoskrnl!ZwClose` at `0x18006a95b`
- `ntoskrnl!ZwClose` at `0x18006aa91`
- `ntoskrnl!ZwClose` at `0x18006a95b`
- `ntoskrnl!ZwClose` at `0x18006aa91`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x18006a8e5`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x18006a8e5`
- `ntoskrnl!ZwOpenKey` at `0x18006a948`
- `ntoskrnl!ZwOpenKey` at `0x18006aa16`
- `ntoskrnl!ZwOpenKey` at `0x18006aa79`
- `ntoskrnl!ZwOpenKey` at `0x18006a948`
- `ntoskrnl!ZwOpenKey` at `0x18006aa16`
- `ntoskrnl!ZwOpenKey` at `0x18006aa79`

## string_xrefs

- `0x18006a98e`: `\Registry\Machine\System\ControlSet001\Services\`

## pseudocode

```c
__int64 __fastcall FltpOpenInstancesRegistryKey(__int64 a1, void **a2)
{
  unsigned int v4; // ebx
  HANDLE Handle; // [rsp+30h] [rbp-D0h] BYREF
  UNICODE_STRING Destination; // [rsp+38h] [rbp-C8h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  OBJECT_ATTRIBUTES v10; // [rsp+88h] [rbp-78h] BYREF
  char v11; // [rsp+C0h] [rbp-40h] BYREF

  Handle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, L"INSTANCES");
  v4 = IoOpenDriverRegistryKey(a1, 0, 131097, 0, &Handle);
  if ( (int)FltpDbgStatus(v4, "minkernel\\fs\\filtermgr\\filter\\instancesup.c", 991, 0) >= 0 )
  {
    ObjectAttributes.RootDirectory = Handle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v4 = ZwOpenKey(a2, 0x20019u, &ObjectAttributes);
    ZwClose(Handle);
    Handle = 0;
  }
  if ( (int)FltpDbgStatus(v4, "minkernel\\fs\\filtermgr\\filter\\instancesup.c", 1017, 0) < 0 )
  {
    *(_QWORD *)&Destination.Length = 20971520;
    Destination.Buffer = (wchar_t *)&v11;
    memset(&v10, 0, 44);
    RtlAppendUnicodeToString(&Destination, L"\\Registry\\Machine\\System\\ControlSet001\\Services\\");
    RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)(*(_QWORD *)(a1 + 48) + 24LL));
    v10.Length = 48;
    v10.ObjectName = &Destination;
    v10.RootDirectory = 0;
    v10.Attributes = 576;
    *(_OWORD *)&v10.SecurityDescriptor = 0;
    v4 = ZwOpenKey(&Handle, 0x20019u, &v10);
    if ( (int)FltpDbgStatus(v4, "minkernel\\fs\\filtermgr\\filter\\instancesup.c", 1021, 0) >= 0 )
    {
      ObjectAttributes.RootDirectory = Handle;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v4 = ZwOpenKey(a2, 0x20019u, &ObjectAttributes);
    }
  }
  if ( Handle )
    ZwClose(Handle);
  return v4;
}

```

## disassembly

```asm
0x18006a860  mov     [rsp-8+arg_10], rbx
0x18006a865  mov     [rsp-8+arg_18], rsi
0x18006a86a  push    rbp
0x18006a86b  push    rdi
0x18006a86c  push    r14
0x18006a86e  lea     rbp, [rsp-110h]
0x18006a876  sub     rsp, 210h
0x18006a87d  mov     rax, cs:__security_cookie
0x18006a884  xor     rax, rsp
0x18006a887  mov     [rbp+120h+var_20], rax
0x18006a88e  xorps   xmm0, xmm0
0x18006a891  mov     rdi, rdx
0x18006a894  mov     rsi, rcx
0x18006a897  lea     rdx, FltpRegFilterInstancesSubKey; "INSTANCES"
0x18006a89e  movups  xmmword ptr [rsp+220h+ObjectAttributes.ObjectName], xmm0
0x18006a8a3  xor     r14d, r14d
0x18006a8a6  lea     rcx, [rsp+220h+DestinationString]; DestinationString
0x18006a8ab  xor     eax, eax
0x18006a8ad  mov     [rsp+220h+Handle], r14
0x18006a8b2  movups  xmmword ptr [rsp+220h+ObjectAttributes+1Ch], xmm0
0x18006a8b7  movups  xmmword ptr [rsp+220h+DestinationString.Length], xmm0
0x18006a8bc  movups  xmmword ptr [rsp+220h+ObjectAttributes.Length], xmm0
0x18006a8c1  call    cs:__imp_RtlInitUnicodeString
0x18006a8c8  nop     dword ptr [rax+rax+00h]
0x18006a8cd  lea     rax, [rsp+220h+Handle]
0x18006a8d2  xor     r9d, r9d
0x18006a8d5  xor     edx, edx
0x18006a8d7  mov     [rsp+220h+var_200], rax
0x18006a8dc  mov     r8d, 20019h
0x18006a8e2  mov     rcx, rsi
0x18006a8e5  call    cs:__imp_IoOpenDriverRegistryKey
0x18006a8ec  nop     dword ptr [rax+rax+00h]
0x18006a8f1  mov     r8d, 3DFh
0x18006a8f7  lea     rdx, aMinkernelFsFil_19; "minkernel\\fs\\filtermgr\\filter\\insta"...
0x18006a8fe  mov     ecx, eax
0x18006a900  xor     r9d, r9d
0x18006a903  mov     ebx, eax
0x18006a905  call    FltpDbgStatus
0x18006a90a  test    eax, eax
0x18006a90c  js      short loc_18006A96C
0x18006a90e  mov     rax, [rsp+220h+Handle]
0x18006a913  lea     r8, [rsp+220h+ObjectAttributes]; ObjectAttributes
0x18006a918  mov     [rsp+220h+ObjectAttributes.RootDirectory], rax
0x18006a91d  xorps   xmm0, xmm0
0x18006a920  lea     rax, [rsp+220h+DestinationString]
0x18006a925  mov     [rsp+220h+ObjectAttributes.Length], 30h ; '0'
0x18006a92d  mov     edx, 20019h; DesiredAccess
0x18006a932  mov     [rsp+220h+ObjectAttributes.ObjectName], rax
0x18006a937  mov     rcx, rdi; KeyHandle
0x18006a93a  mov     [rsp+220h+ObjectAttributes.Attributes], 240h
0x18006a942  movdqu  xmmword ptr [rsp+220h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006a948  call    cs:__imp_ZwOpenKey
0x18006a94f  nop     dword ptr [rax+rax+00h]
0x18006a954  mov     rcx, [rsp+220h+Handle]; Handle
0x18006a959  mov     ebx, eax
0x18006a95b  call    cs:__imp_ZwClose
0x18006a962  nop     dword ptr [rax+rax+00h]
0x18006a967  mov     [rsp+220h+Handle], r14
0x18006a96c  mov     r8d, 3F9h
0x18006a972  lea     rdx, aMinkernelFsFil_19; "minkernel\\fs\\filtermgr\\filter\\insta"...
0x18006a979  xor     r9d, r9d
0x18006a97c  mov     ecx, ebx
0x18006a97e  call    FltpDbgStatus
0x18006a983  test    eax, eax
0x18006a985  jns     loc_18006AA87
0x18006a98b  xorps   xmm0, xmm0
0x18006a98e  lea     rdx, FltpServicesRegistryPathDesktop; "\\Registry\\Machine\\System\\ControlSet"...
0x18006a995  xor     eax, eax
0x18006a997  lea     rcx, [rsp+220h+Destination]; Destination
0x18006a99c  movups  xmmword ptr [rsp+220h+Destination.Length], xmm0
0x18006a9a1  mov     eax, 140h
0x18006a9a6  mov     [rsp+220h+Destination.MaximumLength], ax
0x18006a9ab  lea     rax, [rbp+120h+var_160]
0x18006a9af  movups  xmmword ptr [rbp+120h+var_198.ObjectName], xmm0
0x18006a9b3  mov     [rsp+220h+Destination.Buffer], rax
0x18006a9b8  movups  xmmword ptr [rbp+120h+var_198.Length], xmm0
0x18006a9bc  movups  xmmword ptr [rbp+120h+var_198+1Ch], xmm0
0x18006a9c0  call    cs:__imp_RtlAppendUnicodeToString
0x18006a9c7  nop     dword ptr [rax+rax+00h]
0x18006a9cc  mov     rdx, [rsi+30h]
0x18006a9d0  lea     rcx, [rsp+220h+Destination]; Destination
0x18006a9d5  add     rdx, 18h; Source
0x18006a9d9  call    cs:__imp_RtlAppendUnicodeStringToString
0x18006a9e0  nop     dword ptr [rax+rax+00h]
0x18006a9e5  lea     rax, [rsp+220h+Destination]
0x18006a9ea  mov     [rbp+120h+var_198.Length], 30h ; '0'
0x18006a9f1  xorps   xmm0, xmm0
0x18006a9f4  mov     [rbp+120h+var_198.ObjectName], rax
0x18006a9f8  lea     r8, [rbp+120h+var_198]; ObjectAttributes
0x18006a9fc  mov     [rbp+120h+var_198.RootDirectory], r14
0x18006aa00  mov     edx, 20019h; DesiredAccess
0x18006aa05  mov     [rbp+120h+var_198.Attributes], 240h
0x18006aa0c  lea     rcx, [rsp+220h+Handle]; KeyHandle
0x18006aa11  movdqu  xmmword ptr [rbp+120h+var_198.SecurityDescriptor], xmm0
0x18006aa16  call    cs:__imp_ZwOpenKey
0x18006aa1d  nop     dword ptr [rax+rax+00h]
0x18006aa22  mov     r8d, 3FDh
0x18006aa28  lea     rdx, aMinkernelFsFil_19; "minkernel\\fs\\filtermgr\\filter\\insta"...
0x18006aa2f  mov     ecx, eax
0x18006aa31  xor     r9d, r9d
0x18006aa34  mov     ebx, eax
0x18006aa36  call    FltpDbgStatus
0x18006aa3b  test    eax, eax
0x18006aa3d  js      short loc_18006AA87
0x18006aa3f  mov     rax, [rsp+220h+Handle]
0x18006aa44  lea     r8, [rsp+220h+ObjectAttributes]; ObjectAttributes
0x18006aa49  mov     [rsp+220h+ObjectAttributes.RootDirectory], rax
0x18006aa4e  xorps   xmm0, xmm0
0x18006aa51  lea     rax, [rsp+220h+DestinationString]
0x18006aa56  mov     [rsp+220h+ObjectAttributes.Length], 30h ; '0'
0x18006aa5e  mov     edx, 20019h; DesiredAccess
0x18006aa63  mov     [rsp+220h+ObjectAttributes.ObjectName], rax
0x18006aa68  mov     rcx, rdi; KeyHandle
0x18006aa6b  mov     [rsp+220h+ObjectAttributes.Attributes], 240h
0x18006aa73  movdqu  xmmword ptr [rsp+220h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006aa79  call    cs:__imp_ZwOpenKey
0x18006aa80  nop     dword ptr [rax+rax+00h]
0x18006aa85  mov     ebx, eax
0x18006aa87  mov     rcx, [rsp+220h+Handle]; Handle
0x18006aa8c  test    rcx, rcx
0x18006aa8f  jz      short loc_18006AA9D
0x18006aa91  call    cs:__imp_ZwClose
0x18006aa98  nop     dword ptr [rax+rax+00h]
0x18006aa9d  mov     eax, ebx
0x18006aa9f  mov     rcx, [rbp+120h+var_20]
0x18006aaa6  xor     rcx, rsp; StackCookie
0x18006aaa9  call    __security_check_cookie
0x18006aaae  lea     r11, [rsp+220h+var_10]
0x18006aab6  mov     rbx, [r11+30h]
0x18006aaba  mov     rsi, [r11+38h]
0x18006aabe  mov     rsp, r11
0x18006aac1  pop     r14
0x18006aac3  pop     rdi
0x18006aac4  pop     rbp
0x18006aac5  retn
```
