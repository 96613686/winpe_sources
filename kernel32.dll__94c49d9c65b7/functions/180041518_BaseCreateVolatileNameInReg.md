# BaseCreateVolatileNameInReg

- ea: `0x180041518`
- end: `0x18004166e`
- name: `BaseCreateVolatileNameInReg`
- size: `342`
- prototype: `__int64 __fastcall(PVOID Data)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180039820`

## callees

- `0x1800378d4`
- `0x180041518`

## import_xrefs

- `ntdll!NtSetValueKey` at `0x180041642`
- `ntdll!NtSetValueKey` at `0x180041642`
- `ntdll!NtClose` at `0x180041653`
- `ntdll!NtClose` at `0x180041653`
- `ntdll!wcslen` at `0x18004161b`
- `ntdll!wcslen` at `0x18004161b`
- `ntdll!NtCreateKey` at `0x1800415cc`
- `ntdll!NtCreateKey` at `0x1800415cc`
- `ntdll!RtlInitUnicodeString` at `0x180041565`
- `ntdll!RtlInitUnicodeString` at `0x180041576`
- `ntdll!RtlInitUnicodeString` at `0x180041612`
- `ntdll!RtlInitUnicodeString` at `0x180041565`
- `ntdll!RtlInitUnicodeString` at `0x180041576`
- `ntdll!RtlInitUnicodeString` at `0x180041612`

## string_xrefs

- `0x1800415e6`: `ComputerName`
- `0x180041607`: `ComputerName`
- `0x18004156b`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName\ActiveComputerName`
- `0x1800415ef`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName\ActiveComputerName`
- `0x18004153e`: `Network ComputerName`

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
0x180041518  mov     [rsp-8+arg_0], rbx
0x18004151d  push    rbp
0x18004151e  push    rsi
0x18004151f  push    rdi
0x180041520  lea     rbp, [rsp-47h]
0x180041525  sub     rsp, 0A0h
0x18004152c  xorps   xmm0, xmm0
0x18004152f  mov     [rbp+57h+arg_10], 0
0x180041536  mov     rsi, rdx
0x180041539  mov     rdi, rcx
0x18004153c  xor     eax, eax
0x18004153e  lea     rdx, aNetworkCompute; "Network ComputerName"
0x180041545  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180041549  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18004154d  mov     [rbp+57h+KeyHandle], rax
0x180041551  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180041555  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180041559  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x18004155d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180041561  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x180041565  call    cs:__imp_RtlInitUnicodeString
0x18004156b  lea     rdx, aRegistryMachin_21; "\\Registry\\Machine\\System\\CurrentCon"...
0x180041572  lea     rcx, [rbp+57h+var_70]; DestinationString
0x180041576  call    cs:__imp_RtlInitUnicodeString
0x18004157c  lea     rax, [rbp+57h+var_70]
0x180041580  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180041587  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18004158b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18004158f  lea     rax, [rbp+57h+arg_10]
0x180041593  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18004159b  mov     [rsp+0B0h+Disposition], rax; Disposition
0x1800415a0  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800415a4  lea     rax, [rbp+57h+DestinationString]
0x1800415a8  mov     [rsp+0B0h+CreateOptions], 1; CreateOptions
0x1800415b0  xorps   xmm0, xmm0
0x1800415b3  mov     [rsp+0B0h+Class], rax; Class
0x1800415b8  xor     r9d, r9d; TitleIndex
0x1800415bb  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800415c2  mov     edx, 2001Fh; DesiredAccess
0x1800415c7  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800415cc  call    cs:__imp_NtCreateKey
0x1800415d2  mov     ebx, eax
0x1800415d4  test    eax, eax
0x1800415d6  js      short loc_18004164A
0x1800415d8  cmp     [rbp+57h+arg_10], 2
0x1800415dc  jnz     short loc_180041607
0x1800415de  mov     r9, rdi
0x1800415e1  mov     [rsp+0B0h+Class], rsi
0x1800415e6  lea     r8, aComputername; "ComputerName"
0x1800415ed  xor     ecx, ecx
0x1800415ef  lea     rdx, aRegistryMachin_21; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800415f6  call    BasepGetNameFromReg
0x1800415fb  cmp     eax, 0C0000034h
0x180041600  jnz     short loc_180041607
0x180041602  lea     ebx, [rax-33h]
0x180041605  jmp     short loc_18004164A
0x180041607  lea     rdx, aComputername; "ComputerName"
0x18004160e  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180041612  call    cs:__imp_RtlInitUnicodeString
0x180041618  mov     rcx, rdi; String
0x18004161b  call    cs:__imp_wcslen
0x180041621  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180041625  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180041629  mov     r9d, 1; Type
0x18004162f  xor     r8d, r8d; TitleIndex
0x180041632  lea     eax, ds:2[rax*2]
0x180041639  mov     [rsp+0B0h+CreateOptions], eax; DataSize
0x18004163d  mov     [rsp+0B0h+Class], rdi; Data
0x180041642  call    cs:__imp_NtSetValueKey
0x180041648  mov     ebx, eax
0x18004164a  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18004164e  test    rcx, rcx
0x180041651  jz      short loc_180041659
0x180041653  call    cs:__imp_NtClose
0x180041659  mov     eax, ebx
0x18004165b  mov     rbx, [rsp+0B0h+arg_0]
0x180041663  add     rsp, 0A0h
0x18004166a  pop     rdi
0x18004166b  pop     rsi
0x18004166c  pop     rbp
0x18004166d  retn
```
