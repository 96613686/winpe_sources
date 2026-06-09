# BaseCreateVolatileNameInReg

- ea: `0x180045364`
- end: `0x1800454e9`
- name: `BaseCreateVolatileNameInReg`
- size: `389`
- prototype: `__int64 __fastcall(PVOID Data)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003c870`

## callees

- `0x18003a464`
- `0x180045364`

## import_xrefs

- `ntdll!NtSetValueKey` at `0x1800454b0`
- `ntdll!NtSetValueKey` at `0x1800454b0`
- `ntdll!NtClose` at `0x1800454c7`
- `ntdll!NtClose` at `0x1800454c7`
- `ntdll!wcslen` at `0x180045483`
- `ntdll!wcslen` at `0x180045483`
- `ntdll!NtCreateKey` at `0x180045424`
- `ntdll!NtCreateKey` at `0x180045424`
- `ntdll!RtlInitUnicodeString` at `0x1800453b1`
- `ntdll!RtlInitUnicodeString` at `0x1800453c8`
- `ntdll!RtlInitUnicodeString` at `0x180045474`
- `ntdll!RtlInitUnicodeString` at `0x1800453b1`
- `ntdll!RtlInitUnicodeString` at `0x1800453c8`
- `ntdll!RtlInitUnicodeString` at `0x180045474`

## string_xrefs

- `0x180045448`: `ComputerName`
- `0x180045469`: `ComputerName`
- `0x1800453bd`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName\ActiveComputerName`
- `0x180045451`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName\ActiveComputerName`
- `0x18004538a`: `Network ComputerName`

## pseudocode

```c
__int64 __fastcall BaseCreateVolatileNameInReg(wchar_t *Data, __int64 a2)
{
  NTSTATUS v4; // ebx
  int v5; // eax
  struct _UNICODE_STRING v7; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-9h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+60h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+17h] BYREF
  ULONG Disposition; // [rsp+D0h] [rbp+77h] BYREF
  void *KeyHandle; // [rsp+D8h] [rbp+7Fh] BYREF

  Disposition = 0;
  KeyHandle = 0;
  DestinationString = 0;
  v7 = 0;
  memset(&ObjectAttributes, 0, 44);
  ValueName = 0;
  RtlInitUnicodeString(&DestinationString, L"Network ComputerName");
  RtlInitUnicodeString(
    &v7,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\ComputerName\\ActiveComputerName");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v7;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, &DestinationString, 1u, &Disposition);
  if ( v4 >= 0 )
  {
    if ( Disposition == 2
      && (unsigned int)BasepGetNameFromReg(
                         0,
                         (unsigned int)L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\ComputerName\\ActiveComputerName",
                         (unsigned int)L"ComputerName",
                         (_DWORD)Data,
                         a2) == -1073741772 )
    {
      v4 = -1073741823;
    }
    else
    {
      RtlInitUnicodeString(&ValueName, L"ComputerName");
      v5 = wcslen(Data);
      v4 = NtSetValueKey(KeyHandle, &ValueName, 0, 1u, Data, 2 * v5 + 2);
    }
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180045364  mov     [rsp-8+arg_0], rbx
0x180045369  push    rbp
0x18004536a  push    rsi
0x18004536b  push    rdi
0x18004536c  lea     rbp, [rsp-47h]
0x180045371  sub     rsp, 0A0h
0x180045378  xorps   xmm0, xmm0
0x18004537b  mov     [rbp+57h+arg_10], 0
0x180045382  mov     rsi, rdx
0x180045385  mov     rdi, rcx
0x180045388  xor     eax, eax
0x18004538a  lea     rdx, aNetworkCompute; "Network ComputerName"
0x180045391  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180045395  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180045399  mov     [rbp+57h+KeyHandle], rax
0x18004539d  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800453a1  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800453a5  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x1800453a9  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800453ad  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x1800453b1  call    cs:__imp_RtlInitUnicodeString
0x1800453b8  nop     dword ptr [rax+rax+00h]
0x1800453bd  lea     rdx, aRegistryMachin_21; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800453c4  lea     rcx, [rbp+57h+var_70]; DestinationString
0x1800453c8  call    cs:__imp_RtlInitUnicodeString
0x1800453cf  nop     dword ptr [rax+rax+00h]
0x1800453d4  lea     rax, [rbp+57h+var_70]
0x1800453d8  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800453df  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800453e3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800453e7  lea     rax, [rbp+57h+arg_10]
0x1800453eb  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800453f3  mov     [rsp+0B0h+Disposition], rax; Disposition
0x1800453f8  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800453fc  lea     rax, [rbp+57h+DestinationString]
0x180045400  mov     [rsp+0B0h+CreateOptions], 1; CreateOptions
0x180045408  xorps   xmm0, xmm0
0x18004540b  mov     [rsp+0B0h+Class], rax; Class
0x180045410  xor     r9d, r9d; TitleIndex
0x180045413  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18004541a  mov     edx, 2001Fh; DesiredAccess
0x18004541f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180045424  call    cs:__imp_NtCreateKey
0x18004542b  nop     dword ptr [rax+rax+00h]
0x180045430  mov     ebx, eax
0x180045432  test    eax, eax
0x180045434  js      loc_1800454BE
0x18004543a  cmp     [rbp+57h+arg_10], 2
0x18004543e  jnz     short loc_180045469
0x180045440  mov     r9, rdi
0x180045443  mov     [rsp+0B0h+Class], rsi
0x180045448  lea     r8, aComputername; "ComputerName"
0x18004544f  xor     ecx, ecx
0x180045451  lea     rdx, aRegistryMachin_21; "\\Registry\\Machine\\System\\CurrentCon"...
0x180045458  call    BasepGetNameFromReg
0x18004545d  cmp     eax, 0C0000034h
0x180045462  jnz     short loc_180045469
0x180045464  lea     ebx, [rax-33h]
0x180045467  jmp     short loc_1800454BE
0x180045469  lea     rdx, aComputername; "ComputerName"
0x180045470  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180045474  call    cs:__imp_RtlInitUnicodeString
0x18004547b  nop     dword ptr [rax+rax+00h]
0x180045480  mov     rcx, rdi; String
0x180045483  call    cs:__imp_wcslen
0x18004548a  nop     dword ptr [rax+rax+00h]
0x18004548f  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180045493  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180045497  mov     r9d, 1; Type
0x18004549d  xor     r8d, r8d; TitleIndex
0x1800454a0  lea     eax, ds:2[rax*2]
0x1800454a7  mov     [rsp+0B0h+CreateOptions], eax; DataSize
0x1800454ab  mov     [rsp+0B0h+Class], rdi; Data
0x1800454b0  call    cs:__imp_NtSetValueKey
0x1800454b7  nop     dword ptr [rax+rax+00h]
0x1800454bc  mov     ebx, eax
0x1800454be  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800454c2  test    rcx, rcx
0x1800454c5  jz      short loc_1800454D3
0x1800454c7  call    cs:__imp_NtClose
0x1800454ce  nop     dword ptr [rax+rax+00h]
0x1800454d3  mov     eax, ebx
0x1800454d5  mov     rbx, [rsp+0B0h+arg_0]
0x1800454dd  add     rsp, 0A0h
0x1800454e4  pop     rdi
0x1800454e5  pop     rsi
0x1800454e6  pop     rbp
0x1800454e7  retn
```
