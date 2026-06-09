# BaseDllWriteVariableValue

- ea: `0x18006a978`
- end: `0x18006ab42`
- name: `BaseDllWriteVariableValue`
- size: `458`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180012204`
- `0x1800449e0`
- `0x18005ab2c`

## callees

- `0x1800128dc`
- `0x18001299c`
- `0x18002dc1c`
- `0x18002ded4`
- `0x18003a73c`
- `0x18006a978`
- `0x18007a840`

## import_xrefs

- `ntdll!NtDeleteValueKey` at `0x18006aab7`
- `ntdll!NtDeleteValueKey` at `0x18006aab7`
- `ntdll!NtSetValueKey` at `0x18006ab07`
- `ntdll!NtSetValueKey` at `0x18006ab07`
- `ntdll!NtQueryValueKey` at `0x18006aa73`
- `ntdll!NtQueryValueKey` at `0x18006aa73`
- `ntdll!NtClose` at `0x18006aa96`
- `ntdll!NtClose` at `0x18006ab13`
- `ntdll!NtClose` at `0x18006aa96`
- `ntdll!NtClose` at `0x18006ab13`

## pseudocode

```c
__int64 __fastcall BaseDllWriteVariableValue(
        _DWORD *a1,
        __int64 a2,
        __int64 VarNameMapping,
        struct _UNICODE_STRING *a4)
{
  struct _UNICODE_STRING *v4; // rbx
  __int64 result; // rax
  NTSTATUS v9; // eax
  NTSTATUS v10; // ebx
  HANDLE KeyHandle; // [rsp+30h] [rbp-40h] BYREF
  ULONG DataSize; // [rsp+38h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+3Ch] [rbp-34h] BYREF
  struct _UNICODE_STRING *v14; // [rsp+40h] [rbp-30h] BYREF
  const UNICODE_STRING *v15; // [rsp+48h] [rbp-28h] BYREF
  PVOID Data; // [rsp+50h] [rbp-20h] BYREF
  __int128 KeyValueInformation; // [rsp+58h] [rbp-18h] BYREF

  v15 = 0;
  v4 = a4;
  v14 = a4;
  Data = 0;
  DataSize = 0;
  KeyHandle = 0;
  ResultLength = 0;
  KeyValueInformation = 0;
  if ( !a4 )
  {
    if ( !(unsigned __int8)BaseDllGetVariableName(a1, 0, &v14) )
      return 3221225485LL;
    v4 = v14;
  }
  if ( !VarNameMapping )
  {
    VarNameMapping = BaseDllFindVarNameMapping(a2, v4);
    if ( !VarNameMapping )
      return 3221225494LL;
  }
  if ( !(unsigned __int8)BaseDllGetApplicationName(a1, 0, &v15) )
    return 3221225485LL;
  result = BaseDllOpenMappingTarget((__int64)a1, VarNameMapping, v15, 1, &KeyHandle);
  if ( (int)result >= 0 && KeyHandle != (HANDLE)-1LL )
  {
    v9 = NtQueryValueKey(KeyHandle, v4, KeyValueBasicInformation, &KeyValueInformation, 0x10u, &ResultLength);
    if ( (int)(v9 + 0x80000000) >= 0 && v9 != -2147483643 || DWORD1(KeyValueInformation) == 1 )
    {
      if ( *a1 == 2 || *a1 == 7 )
      {
        if ( (unsigned __int8)BaseDllGetVariableValue(a1, 0, &Data, &DataSize) )
          v10 = NtSetValueKey(KeyHandle, v4, 0, 1u, Data, DataSize);
        else
          v10 = -1073741811;
      }
      else
      {
        v10 = NtDeleteValueKey(KeyHandle, v4);
        if ( v10 == -1073741772 )
          v10 = 0;
      }
      NtClose(KeyHandle);
      if ( v10 >= 0 && (*(_BYTE *)(VarNameMapping + 24) & 1) != 0 )
        return (unsigned int)-1073741802;
      return (unsigned int)v10;
    }
    else
    {
      NtClose(KeyHandle);
      return 3221225508LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006a978  push    rbp
0x18006a97a  push    rbx
0x18006a97b  push    rsi
0x18006a97c  push    rdi
0x18006a97d  push    r14
0x18006a97f  mov     rbp, rsp
0x18006a982  sub     rsp, 70h
0x18006a986  mov     rax, cs:__security_cookie
0x18006a98d  xor     rax, rsp
0x18006a990  mov     [rbp+var_8], rax
0x18006a994  mov     [rbp+var_28], 0
0x18006a99c  mov     rbx, r9
0x18006a99f  mov     [rbp+var_30], rbx
0x18006a9a3  xorps   xmm0, xmm0
0x18006a9a6  mov     [rbp+Data], 0
0x18006a9ae  mov     rsi, r8
0x18006a9b1  mov     [rbp+DataSize], 0
0x18006a9b8  mov     r14, rdx
0x18006a9bb  mov     [rbp+KeyHandle], 0
0x18006a9c3  mov     rdi, rcx
0x18006a9c6  mov     [rbp+var_34], 0
0x18006a9cd  movups  [rbp+KeyValueInformation], xmm0
0x18006a9d1  test    r9, r9
0x18006a9d4  jnz     short loc_18006A9E9
0x18006a9d6  lea     r8, [rbp+var_30]
0x18006a9da  xor     edx, edx
0x18006a9dc  call    BaseDllGetVariableName
0x18006a9e1  test    al, al
0x18006a9e3  jz      short loc_18006AA1D
0x18006a9e5  mov     rbx, [rbp+var_30]
0x18006a9e9  test    rsi, rsi
0x18006a9ec  jnz     short loc_18006AA0B
0x18006a9ee  mov     rdx, rbx
0x18006a9f1  mov     rcx, r14
0x18006a9f4  call    BaseDllFindVarNameMapping
0x18006a9f9  mov     rsi, rax
0x18006a9fc  test    rax, rax
0x18006a9ff  jnz     short loc_18006AA0B
0x18006aa01  mov     eax, 0C0000016h
0x18006aa06  jmp     loc_18006AB2B
0x18006aa0b  lea     r8, [rbp+var_28]
0x18006aa0f  xor     edx, edx
0x18006aa11  mov     rcx, rdi
0x18006aa14  call    BaseDllGetApplicationName
0x18006aa19  test    al, al
0x18006aa1b  jnz     short loc_18006AA27
0x18006aa1d  mov     eax, 0C000000Dh
0x18006aa22  jmp     loc_18006AB2B
0x18006aa27  mov     r8, [rbp+var_28]
0x18006aa2b  lea     rax, [rbp+KeyHandle]
0x18006aa2f  mov     r9b, 1
0x18006aa32  mov     qword ptr [rsp+70h+Length], rax
0x18006aa37  mov     rdx, rsi
0x18006aa3a  mov     rcx, rdi
0x18006aa3d  call    BaseDllOpenMappingTarget
0x18006aa42  test    eax, eax
0x18006aa44  js      loc_18006AB2B
0x18006aa4a  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18006aa4e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006aa52  jz      loc_18006AB2B
0x18006aa58  lea     rax, [rbp+var_34]
0x18006aa5c  xor     r8d, r8d; KeyValueInformationClass
0x18006aa5f  mov     [rsp+70h+ResultLength], rax; ResultLength
0x18006aa64  lea     r9, [rbp+KeyValueInformation]; KeyValueInformation
0x18006aa68  mov     rdx, rbx; ValueName
0x18006aa6b  mov     [rsp+70h+Length], 10h; Length
0x18006aa73  call    cs:__imp_NtQueryValueKey
0x18006aa79  mov     edx, 80000000h
0x18006aa7e  lea     ecx, [rax+rdx]
0x18006aa81  test    edx, ecx
0x18006aa83  jnz     short loc_18006AA8C
0x18006aa85  cmp     eax, 80000005h
0x18006aa8a  jnz     short loc_18006AAA6
0x18006aa8c  cmp     dword ptr [rbp+KeyValueInformation+4], 1
0x18006aa90  jz      short loc_18006AAA6
0x18006aa92  mov     rcx, [rbp+KeyHandle]; Handle
0x18006aa96  call    cs:__imp_NtClose
0x18006aa9c  mov     eax, 0C0000024h
0x18006aaa1  jmp     loc_18006AB2B
0x18006aaa6  cmp     dword ptr [rdi], 2
0x18006aaa9  jz      short loc_18006AACA
0x18006aaab  cmp     dword ptr [rdi], 7
0x18006aaae  jz      short loc_18006AACA
0x18006aab0  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18006aab4  mov     rdx, rbx; ValueName
0x18006aab7  call    cs:__imp_NtDeleteValueKey
0x18006aabd  mov     ebx, eax
0x18006aabf  cmp     eax, 0C0000034h
0x18006aac4  jnz     short loc_18006AB0F
0x18006aac6  xor     ebx, ebx
0x18006aac8  jmp     short loc_18006AB0F
0x18006aaca  lea     r9, [rbp+DataSize]
0x18006aace  xor     edx, edx
0x18006aad0  lea     r8, [rbp+Data]
0x18006aad4  mov     rcx, rdi
0x18006aad7  call    BaseDllGetVariableValue
0x18006aadc  test    al, al
0x18006aade  jnz     short loc_18006AAE7
0x18006aae0  mov     ebx, 0C000000Dh
0x18006aae5  jmp     short loc_18006AB0F
0x18006aae7  mov     eax, [rbp+DataSize]
0x18006aaea  mov     r9d, 1; Type
0x18006aaf0  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18006aaf4  xor     r8d, r8d; TitleIndex
0x18006aaf7  mov     dword ptr [rsp+70h+ResultLength], eax; DataSize
0x18006aafb  mov     rdx, rbx; ValueName
0x18006aafe  mov     rax, [rbp+Data]
0x18006ab02  mov     qword ptr [rsp+70h+Length], rax; Data
0x18006ab07  call    cs:__imp_NtSetValueKey
0x18006ab0d  mov     ebx, eax
0x18006ab0f  mov     rcx, [rbp+KeyHandle]; Handle
0x18006ab13  call    cs:__imp_NtClose
0x18006ab19  test    ebx, ebx
0x18006ab1b  js      short loc_18006AB29
0x18006ab1d  test    byte ptr [rsi+18h], 1
0x18006ab21  mov     eax, 0C0000016h
0x18006ab26  cmovnz  ebx, eax
0x18006ab29  mov     eax, ebx
0x18006ab2b  mov     rcx, [rbp+var_8]
0x18006ab2f  xor     rcx, rsp; StackCookie
0x18006ab32  call    __security_check_cookie
0x18006ab37  add     rsp, 70h
0x18006ab3b  pop     r14
0x18006ab3d  pop     rdi
0x18006ab3e  pop     rsi
0x18006ab3f  pop     rbx
0x18006ab40  pop     rbp
0x18006ab41  retn
```
