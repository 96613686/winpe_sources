# FveRegistryGetAlgorithmProvider

- ea: `0x18001d830`
- end: `0x18001da5f`
- name: `FveRegistryGetAlgorithmProvider`
- size: `559`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d6e0`
- `0x18001ea4c`

## callees

- `0x18001d830`
- `0x18002fd50`
- `0x180030060`
- `0x180045108`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001d87b`
- `ntdll!RtlInitUnicodeString` at `0x18001d892`
- `ntdll!RtlInitUnicodeString` at `0x18001d87b`
- `ntdll!RtlInitUnicodeString` at `0x18001d892`
- `ntdll!NtClose` at `0x18001d9b1`
- `ntdll!NtClose` at `0x18001d9b1`
- `ntdll!NtQueryValueKey` at `0x18001d90e`
- `ntdll!NtQueryValueKey` at `0x18001d96a`
- `ntdll!NtQueryValueKey` at `0x18001d90e`
- `ntdll!NtQueryValueKey` at `0x18001d96a`
- `ntdll!NtOpenKey` at `0x18001d8db`
- `ntdll!NtOpenKey` at `0x18001d8db`

## string_xrefs

- `0x18001d866`: `\Registry\Machine\System\CurrentControlSet\Control\BitLocker`

## pseudocode

```c
__int64 __fastcall FveRegistryGetAlgorithmProvider(_QWORD *a1, ULONG *a2)
{
  ULONG v2; // r15d
  ULONG v5; // r14d
  __int64 v6; // rsi
  NTSTATUS Value; // ebx
  int v8; // eax
  _DWORD *v9; // rdi
  int v10; // eax
  ULONG v11; // edx
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-39h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-19h] BYREF
  ULONG ResultLength; // [rsp+D0h] [rbp+67h] BYREF
  void *KeyHandle; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v18; // [rsp+E0h] [rbp+77h]
  PVOID KeyValueInformation; // [rsp+E8h] [rbp+7Fh]

  v2 = 0;
  *a1 = 0;
  *a2 = 0;
  v18 = 0;
  DestinationString = 0;
  v5 = 0;
  v6 = 0;
  ValueName = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\BitLocker");
  RtlInitUnicodeString(&ValueName, L"AlgorithmProvider");
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ResultLength = 0;
  KeyHandle = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  KeyValueInformation = 0;
  ObjectAttributes.RootDirectory = 0;
  Value = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( Value >= 0 )
  {
    Value = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
    if ( (int)(Value + 0x80000000) < 0 || Value == -1073741789 )
    {
      v8 = FveLibAllocWithTagZero(ResultLength);
      v9 = KeyValueInformation;
      Value = v8;
      if ( v8 >= 0 )
      {
        v2 = ResultLength;
        Value = NtQueryValueKey(
                  KeyHandle,
                  &ValueName,
                  KeyValuePartialInformation,
                  KeyValueInformation,
                  ResultLength,
                  &ResultLength);
        if ( Value >= 0 )
        {
          if ( v9[1] == 1 )
          {
            v5 = v9[2];
            Value = -1073741789;
          }
          else
          {
            Value = -1073741438;
          }
        }
      }
      if ( v9 )
        FveLibFreeWithTag(v9, v2, 0);
    }
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( Value == -1073741789 )
  {
    v10 = FveLibAllocWithTagZero(v5);
    v6 = v18;
    Value = v10;
    if ( v10 >= 0 )
    {
      ResultLength = v5;
      Value = FveRegistryGetValue(&DestinationString, &ValueName, 1, v18, &ResultLength);
      if ( Value >= 0 )
      {
        v11 = ResultLength;
        if ( ResultLength == v5 && ResultLength >= 2 && (ResultLength & 1) == 0 )
        {
          *a1 = v6;
          *a2 = v11;
          *(_WORD *)(v6 + 2 * ((unsigned __int64)v11 >> 1) - 2) = 0;
          return (unsigned int)Value;
        }
        Value = -1073741811;
      }
    }
  }
  if ( v6 )
    FveLibFreeWithTag(v6, v5, 0);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x18001d830  push    rbp
0x18001d832  push    rbx
0x18001d833  push    rsi
0x18001d834  push    rdi
0x18001d835  push    r12
0x18001d837  push    r13
0x18001d839  push    r14
0x18001d83b  push    r15
0x18001d83d  lea     rbp, [rsp-1Fh]
0x18001d842  sub     rsp, 88h
0x18001d849  xor     r15d, r15d
0x18001d84c  mov     r12, rdx
0x18001d84f  mov     [rcx], r15
0x18001d852  mov     r13, rcx
0x18001d855  mov     [rdx], r15d
0x18001d858  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001d85c  xorps   xmm0, xmm0
0x18001d85f  mov     [rbp+57h+arg_10], r15
0x18001d863  xorps   xmm1, xmm1
0x18001d866  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x18001d86d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18001d871  mov     r14d, r15d
0x18001d874  mov     esi, r15d
0x18001d877  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x18001d87b  call    cs:__imp_RtlInitUnicodeString
0x18001d882  nop     dword ptr [rax+rax+00h]
0x18001d887  lea     rdx, aAlgorithmprovi; "AlgorithmProvider"
0x18001d88e  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x18001d892  call    cs:__imp_RtlInitUnicodeString
0x18001d899  nop     dword ptr [rax+rax+00h]
0x18001d89e  lea     rax, [rbp+57h+DestinationString]
0x18001d8a2  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001d8aa  xorps   xmm0, xmm0
0x18001d8ad  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001d8b1  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001d8b5  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18001d8bd  mov     edx, 20019h; DesiredAccess
0x18001d8c2  mov     [rbp+57h+arg_0], r15d
0x18001d8c6  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001d8ca  mov     [rbp+57h+KeyHandle], r15
0x18001d8ce  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001d8d3  mov     [rbp+57h+KeyValueInformation], r15
0x18001d8d7  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x18001d8db  call    cs:__imp_NtOpenKey
0x18001d8e2  nop     dword ptr [rax+rax+00h]
0x18001d8e7  mov     ebx, eax
0x18001d8e9  test    eax, eax
0x18001d8eb  js      loc_18001D9A8
0x18001d8f1  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001d8f5  lea     rax, [rbp+57h+arg_0]
0x18001d8f9  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x18001d8fe  lea     r8d, [r15+2]; KeyValueInformationClass
0x18001d902  xor     r9d, r9d; KeyValueInformation
0x18001d905  mov     [rsp+0C0h+Length], r15d; Length
0x18001d90a  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18001d90e  call    cs:__imp_NtQueryValueKey
0x18001d915  nop     dword ptr [rax+rax+00h]
0x18001d91a  mov     ecx, 80000000h
0x18001d91f  mov     ebx, eax
0x18001d921  add     eax, ecx
0x18001d923  test    ecx, eax
0x18001d925  jnz     short loc_18001D92F
0x18001d927  cmp     ebx, 0C0000023h
0x18001d92d  jnz     short loc_18001D9A8
0x18001d92f  mov     ecx, [rbp+57h+arg_0]; Size
0x18001d932  lea     r8, [rbp+57h+KeyValueInformation]
0x18001d936  xor     edx, edx
0x18001d938  call    FveLibAllocWithTagZero
0x18001d93d  mov     rdi, [rbp+57h+KeyValueInformation]
0x18001d941  mov     ebx, eax
0x18001d943  test    eax, eax
0x18001d945  js      short loc_18001D992
0x18001d947  mov     r15d, [rbp+57h+arg_0]
0x18001d94b  lea     rax, [rbp+57h+arg_0]
0x18001d94f  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001d953  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18001d957  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x18001d95c  mov     r9, rdi; KeyValueInformation
0x18001d95f  mov     r8d, 2; KeyValueInformationClass
0x18001d965  mov     [rsp+0C0h+Length], r15d; Length
0x18001d96a  call    cs:__imp_NtQueryValueKey
0x18001d971  nop     dword ptr [rax+rax+00h]
0x18001d976  mov     ebx, eax
0x18001d978  test    eax, eax
0x18001d97a  js      short loc_18001D992
0x18001d97c  cmp     dword ptr [rdi+4], 1
0x18001d980  jz      short loc_18001D989
0x18001d982  mov     ebx, 0C0000182h
0x18001d987  jmp     short loc_18001D992
0x18001d989  mov     r14d, [rdi+8]
0x18001d98d  mov     ebx, 0C0000023h
0x18001d992  test    rdi, rdi
0x18001d995  jz      short loc_18001D9A5
0x18001d997  mov     edx, r15d
0x18001d99a  xor     r8d, r8d
0x18001d99d  mov     rcx, rdi
0x18001d9a0  call    FveLibFreeWithTag
0x18001d9a5  xor     r15d, r15d
0x18001d9a8  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18001d9ac  test    rcx, rcx
0x18001d9af  jz      short loc_18001D9BD
0x18001d9b1  call    cs:__imp_NtClose
0x18001d9b8  nop     dword ptr [rax+rax+00h]
0x18001d9bd  mov     edi, r14d
0x18001d9c0  cmp     ebx, 0C0000023h
0x18001d9c6  jnz     short loc_18001DA35
0x18001d9c8  lea     r8, [rbp+57h+arg_10]
0x18001d9cc  mov     ecx, r14d; Size
0x18001d9cf  xor     edx, edx
0x18001d9d1  call    FveLibAllocWithTagZero
0x18001d9d6  mov     rsi, [rbp+57h+arg_10]
0x18001d9da  mov     ebx, eax
0x18001d9dc  test    eax, eax
0x18001d9de  js      short loc_18001DA35
0x18001d9e0  lea     rax, [rbp+57h+arg_0]
0x18001d9e4  mov     [rbp+57h+arg_0], r14d
0x18001d9e8  mov     r9, rsi
0x18001d9eb  mov     qword ptr [rsp+0C0h+Length], rax
0x18001d9f0  mov     r8d, 1
0x18001d9f6  lea     rdx, [rbp+57h+ValueName]
0x18001d9fa  lea     rcx, [rbp+57h+DestinationString]
0x18001d9fe  call    FveRegistryGetValue
0x18001da03  mov     ebx, eax
0x18001da05  test    eax, eax
0x18001da07  js      short loc_18001DA35
0x18001da09  mov     edx, [rbp+57h+arg_0]
0x18001da0c  cmp     edx, r14d
0x18001da0f  jnz     short loc_18001DA30
0x18001da11  cmp     edx, 2
0x18001da14  jb      short loc_18001DA30
0x18001da16  test    dl, 1
0x18001da19  jnz     short loc_18001DA30
0x18001da1b  mov     ecx, edx
0x18001da1d  mov     [r13+0], rsi
0x18001da21  shr     rcx, 1
0x18001da24  mov     [r12], edx
0x18001da28  mov     [rsi+rcx*2-2], r15w
0x18001da2e  jmp     short loc_18001DA48
0x18001da30  mov     ebx, 0C000000Dh
0x18001da35  test    rsi, rsi
0x18001da38  jz      short loc_18001DA48
0x18001da3a  xor     r8d, r8d
0x18001da3d  mov     rdx, rdi
0x18001da40  mov     rcx, rsi
0x18001da43  call    FveLibFreeWithTag
0x18001da48  mov     eax, ebx
0x18001da4a  add     rsp, 88h
0x18001da51  pop     r15
0x18001da53  pop     r14
0x18001da55  pop     r13
0x18001da57  pop     r12
0x18001da59  pop     rdi
0x18001da5a  pop     rsi
0x18001da5b  pop     rbx
0x18001da5c  pop     rbp
0x18001da5d  retn
```
