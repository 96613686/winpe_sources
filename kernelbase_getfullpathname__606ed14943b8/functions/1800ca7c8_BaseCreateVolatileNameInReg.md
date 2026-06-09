# BaseCreateVolatileNameInReg

- ea: `0x1800ca7c8`
- end: `0x1800ca94c`
- name: `BaseCreateVolatileNameInReg`
- size: `388`
- prototype: `__int64 __fastcall(PVOID Data)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800caa90`

## callees

- `0x1800ca7c8`
- `0x1800caffc`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800ca815`
- `ntdll!RtlInitUnicodeString` at `0x1800ca82c`
- `ntdll!RtlInitUnicodeString` at `0x1800ca8fd`
- `ntdll!RtlInitUnicodeString` at `0x1800ca815`
- `ntdll!RtlInitUnicodeString` at `0x1800ca82c`
- `ntdll!RtlInitUnicodeString` at `0x1800ca8fd`
- `ntdll!wcslen` at `0x1800ca90c`
- `ntdll!wcslen` at `0x1800ca90c`
- `ntdll!NtCreateKey` at `0x1800ca888`
- `ntdll!NtCreateKey` at `0x1800ca888`
- `ntdll!NtSetValueKey` at `0x1800ca939`
- `ntdll!NtSetValueKey` at `0x1800ca939`
- `ntdll!NtClose` at `0x1800ca8d0`
- `ntdll!NtClose` at `0x1800ca8d0`

## string_xrefs

- `0x1800ca821`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName\ActiveComputerName`
- `0x1800ca8b1`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName\ActiveComputerName`
- `0x1800ca7ee`: `Network ComputerName`
- `0x1800ca8a8`: `ComputerName`
- `0x1800ca8f2`: `ComputerName`

## pseudocode

```c
__int64 __fastcall BaseCreateVolatileNameInReg(wchar_t *Data, __int64 a2)
{
  NTSTATUS v4; // ebx
  int v6; // eax
  struct _UNICODE_STRING v7; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-9h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+60h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+17h] BYREF
  ULONG Disposition; // [rsp+D0h] [rbp+77h] BYREF
  HANDLE KeyHandle; // [rsp+D8h] [rbp+7Fh] BYREF

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
      v6 = wcslen(Data);
      v4 = NtSetValueKey(KeyHandle, &ValueName, 0, 1u, Data, 2 * v6 + 2);
    }
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800ca7c8  mov     [rsp-8+arg_0], rbx
0x1800ca7cd  push    rbp
0x1800ca7ce  push    rsi
0x1800ca7cf  push    rdi
0x1800ca7d0  lea     rbp, [rsp-47h]
0x1800ca7d5  sub     rsp, 0A0h
0x1800ca7dc  xorps   xmm0, xmm0
0x1800ca7df  mov     [rbp+57h+arg_10], 0
0x1800ca7e6  mov     rsi, rdx
0x1800ca7e9  mov     rdi, rcx
0x1800ca7ec  xor     eax, eax
0x1800ca7ee  lea     rdx, aNetworkCompute; "Network ComputerName"
0x1800ca7f5  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800ca7f9  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800ca7fd  mov     [rbp+57h+KeyHandle], rax
0x1800ca801  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800ca805  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800ca809  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x1800ca80d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800ca811  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x1800ca815  call    cs:__imp_RtlInitUnicodeString
0x1800ca81c  nop     dword ptr [rax+rax+00h]
0x1800ca821  lea     rdx, aRegistryMachin_33; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800ca828  lea     rcx, [rbp+57h+var_70]; DestinationString
0x1800ca82c  call    cs:__imp_RtlInitUnicodeString
0x1800ca833  nop     dword ptr [rax+rax+00h]
0x1800ca838  lea     rax, [rbp+57h+var_70]
0x1800ca83c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800ca843  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800ca847  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800ca84b  lea     rax, [rbp+57h+arg_10]
0x1800ca84f  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800ca857  mov     [rsp+0B0h+Disposition], rax; Disposition
0x1800ca85c  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800ca860  lea     rax, [rbp+57h+DestinationString]
0x1800ca864  mov     [rsp+0B0h+CreateOptions], 1; CreateOptions
0x1800ca86c  xorps   xmm0, xmm0
0x1800ca86f  mov     [rsp+0B0h+Class], rax; Class
0x1800ca874  xor     r9d, r9d; TitleIndex
0x1800ca877  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800ca87e  mov     edx, 2001Fh; DesiredAccess
0x1800ca883  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ca888  call    cs:__imp_NtCreateKey
0x1800ca88f  nop     dword ptr [rax+rax+00h]
0x1800ca894  mov     ebx, eax
0x1800ca896  test    eax, eax
0x1800ca898  js      short loc_1800CA8C7
0x1800ca89a  cmp     [rbp+57h+arg_10], 2
0x1800ca89e  jnz     short loc_1800CA8F2
0x1800ca8a0  mov     r9, rdi
0x1800ca8a3  mov     [rsp+0B0h+Class], rsi
0x1800ca8a8  lea     r8, aComputername_1; "ComputerName"
0x1800ca8af  xor     ecx, ecx
0x1800ca8b1  lea     rdx, aRegistryMachin_33; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800ca8b8  call    BasepGetNameFromReg
0x1800ca8bd  cmp     eax, 0C0000034h
0x1800ca8c2  jnz     short loc_1800CA8F2
0x1800ca8c4  lea     ebx, [rax-33h]
0x1800ca8c7  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800ca8cb  test    rcx, rcx
0x1800ca8ce  jz      short loc_1800CA8DC
0x1800ca8d0  call    cs:__imp_NtClose
0x1800ca8d7  nop     dword ptr [rax+rax+00h]
0x1800ca8dc  mov     eax, ebx
0x1800ca8de  mov     rbx, [rsp+0B0h+arg_0]
0x1800ca8e6  add     rsp, 0A0h
0x1800ca8ed  pop     rdi
0x1800ca8ee  pop     rsi
0x1800ca8ef  pop     rbp
0x1800ca8f0  retn
0x1800ca8f2  lea     rdx, aComputername_1; "ComputerName"
0x1800ca8f9  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1800ca8fd  call    cs:__imp_RtlInitUnicodeString
0x1800ca904  nop     dword ptr [rax+rax+00h]
0x1800ca909  mov     rcx, rdi; String
0x1800ca90c  call    cs:__imp_wcslen
0x1800ca913  nop     dword ptr [rax+rax+00h]
0x1800ca918  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800ca91c  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800ca920  mov     r9d, 1; Type
0x1800ca926  xor     r8d, r8d; TitleIndex
0x1800ca929  lea     eax, ds:2[rax*2]
0x1800ca930  mov     [rsp+0B0h+CreateOptions], eax; DataSize
0x1800ca934  mov     [rsp+0B0h+Class], rdi; Data
0x1800ca939  call    cs:__imp_NtSetValueKey
0x1800ca940  nop     dword ptr [rax+rax+00h]
0x1800ca945  mov     ebx, eax
0x1800ca947  jmp     loc_1800CA8C7
```
