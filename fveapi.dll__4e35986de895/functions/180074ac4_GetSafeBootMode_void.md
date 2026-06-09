# GetSafeBootMode(void)

- ea: `0x180074ac4`
- end: `0x180074bd7`
- name: `?GetSafeBootMode@@YAKXZ`
- size: `275`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180047a48`

## callees

- `0x180074ac4`
- `0x18011f010`

## import_xrefs

- `ntdll!NtClose` at `0x180074b8c`
- `ntdll!NtClose` at `0x180074b8c`
- `ntdll!NtQueryValueKey` at `0x180074b7a`
- `ntdll!NtQueryValueKey` at `0x180074b7a`
- `ntdll!NtOpenKey` at `0x180074b44`
- `ntdll!NtOpenKey` at `0x180074b44`

## pseudocode

```c
__int64 GetSafeBootMode(void)
{
  __int64 result; // rax
  NTSTATUS v1; // ebx
  void *KeyHandle; // [rsp+30h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-41h] BYREF
  ULONG ResultLength; // [rsp+68h] [rbp-11h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+70h] [rbp-9h] BYREF
  int v6; // [rsp+74h] [rbp-5h]
  int v7; // [rsp+78h] [rbp-1h]
  unsigned int v8; // [rsp+7Ch] [rbp+3h]

  result = (unsigned int)dword_180172B60;
  if ( dword_180172B60 == -1 )
  {
    ResultLength = 0;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_18012CDD0;
    KeyHandle = 0;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    dword_180172B60 = 0;
    ObjectAttributes.RootDirectory = 0;
    if ( NtOpenKey(&KeyHandle, 1u, &ObjectAttributes) >= 0
      && (v1 = NtQueryValueKey(
                 KeyHandle,
                 (PUNICODE_STRING)&stru_18012CDC0,
                 KeyValuePartialInformation,
                 KeyValueInformation,
                 0x50u,
                 &ResultLength),
          NtClose(KeyHandle),
          v1 >= 0)
      && v6 == 4
      && v7 == 4 )
    {
      result = v8;
      dword_180172B60 = v8;
    }
    else
    {
      return (unsigned int)dword_180172B60;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180074ac4  mov     [rsp-8+arg_0], rbx
0x180074ac9  push    rbp
0x180074aca  lea     rbp, [rsp-57h]
0x180074acf  sub     rsp, 0D0h
0x180074ad6  mov     rax, cs:__security_cookie
0x180074add  xor     rax, rsp
0x180074ae0  mov     [rbp+57h+var_10], rax
0x180074ae4  mov     eax, cs:dword_180172B60
0x180074aea  cmp     eax, 0FFFFFFFFh
0x180074aed  jnz     loc_180074BB9
0x180074af3  lea     rax, qword_18012CDD0
0x180074afa  mov     [rbp+57h+var_68], 0
0x180074b01  xorps   xmm0, xmm0
0x180074b04  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180074b08  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180074b0c  mov     [rbp+57h+KeyHandle], 0
0x180074b14  mov     edx, 1; DesiredAccess
0x180074b19  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180074b21  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180074b25  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180074b2d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180074b32  mov     cs:dword_180172B60, 0
0x180074b3c  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180074b44  call    cs:__imp_NtOpenKey
0x180074b4b  nop     dword ptr [rax+rax+00h]
0x180074b50  test    eax, eax
0x180074b52  js      short loc_180074BB3
0x180074b54  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180074b58  lea     rax, [rbp+57h+var_68]
0x180074b5c  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x180074b61  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180074b65  mov     r8d, 2; KeyValueInformationClass
0x180074b6b  mov     [rsp+0D0h+Length], 50h ; 'P'; Length
0x180074b73  lea     rdx, stru_18012CDC0; ValueName
0x180074b7a  call    cs:__imp_NtQueryValueKey
0x180074b81  nop     dword ptr [rax+rax+00h]
0x180074b86  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180074b8a  mov     ebx, eax
0x180074b8c  call    cs:__imp_NtClose
0x180074b93  nop     dword ptr [rax+rax+00h]
0x180074b98  test    ebx, ebx
0x180074b9a  js      short loc_180074BB3
0x180074b9c  cmp     [rbp+57h+var_5C], 4
0x180074ba0  jnz     short loc_180074BB3
0x180074ba2  cmp     [rbp+57h+var_58], 4
0x180074ba6  jnz     short loc_180074BB3
0x180074ba8  mov     eax, [rbp+57h+var_54]
0x180074bab  mov     cs:dword_180172B60, eax
0x180074bb1  jmp     short loc_180074BB9
0x180074bb3  mov     eax, cs:dword_180172B60
0x180074bb9  mov     rcx, [rbp+57h+var_10]
0x180074bbd  xor     rcx, rsp; StackCookie
0x180074bc0  call    __security_check_cookie
0x180074bc5  mov     rbx, [rsp+0D0h+arg_0]
0x180074bcd  add     rsp, 0D0h
0x180074bd4  pop     rbp
0x180074bd5  retn
```
