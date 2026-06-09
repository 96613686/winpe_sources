# BaseDllWriteVariableValue

- ea: `0x180071c4c`
- end: `0x180071e35`
- name: `BaseDllWriteVariableValue`
- size: `489`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000f864`
- `0x180048ff8`
- `0x180060350`

## callees

- `0x18000ff90`
- `0x180010058`
- `0x18002f698`
- `0x18002fa2c`
- `0x18003d800`
- `0x180071c4c`
- `0x1800827c0`

## import_xrefs

- `ntdll!NtDeleteValueKey` at `0x180071d97`
- `ntdll!NtDeleteValueKey` at `0x180071d97`
- `ntdll!NtSetValueKey` at `0x180071ded`
- `ntdll!NtSetValueKey` at `0x180071ded`
- `ntdll!NtQueryValueKey` at `0x180071d47`
- `ntdll!NtQueryValueKey` at `0x180071d47`
- `ntdll!NtClose` at `0x180071d70`
- `ntdll!NtClose` at `0x180071dff`
- `ntdll!NtClose` at `0x180071d70`
- `ntdll!NtClose` at `0x180071dff`

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
0x180071c4c  push    rbp
0x180071c4e  push    rbx
0x180071c4f  push    rsi
0x180071c50  push    rdi
0x180071c51  push    r14
0x180071c53  mov     rbp, rsp
0x180071c56  sub     rsp, 70h
0x180071c5a  mov     rax, cs:__security_cookie
0x180071c61  xor     rax, rsp
0x180071c64  mov     [rbp+var_8], rax
0x180071c68  mov     [rbp+var_28], 0
0x180071c70  mov     rbx, r9
0x180071c73  mov     [rbp+var_30], rbx
0x180071c77  xorps   xmm0, xmm0
0x180071c7a  mov     [rbp+Data], 0
0x180071c82  mov     rsi, r8
0x180071c85  mov     [rbp+DataSize], 0
0x180071c8c  mov     r14, rdx
0x180071c8f  mov     [rbp+KeyHandle], 0
0x180071c97  mov     rdi, rcx
0x180071c9a  mov     [rbp+var_34], 0
0x180071ca1  movups  [rbp+KeyValueInformation], xmm0
0x180071ca5  test    r9, r9
0x180071ca8  jnz     short loc_180071CBD
0x180071caa  lea     r8, [rbp+var_30]
0x180071cae  xor     edx, edx
0x180071cb0  call    BaseDllGetVariableName
0x180071cb5  test    al, al
0x180071cb7  jz      short loc_180071CF1
0x180071cb9  mov     rbx, [rbp+var_30]
0x180071cbd  test    rsi, rsi
0x180071cc0  jnz     short loc_180071CDF
0x180071cc2  mov     rdx, rbx
0x180071cc5  mov     rcx, r14
0x180071cc8  call    BaseDllFindVarNameMapping
0x180071ccd  mov     rsi, rax
0x180071cd0  test    rax, rax
0x180071cd3  jnz     short loc_180071CDF
0x180071cd5  mov     eax, 0C0000016h
0x180071cda  jmp     loc_180071E1D
0x180071cdf  lea     r8, [rbp+var_28]
0x180071ce3  xor     edx, edx
0x180071ce5  mov     rcx, rdi
0x180071ce8  call    BaseDllGetApplicationName
0x180071ced  test    al, al
0x180071cef  jnz     short loc_180071CFB
0x180071cf1  mov     eax, 0C000000Dh
0x180071cf6  jmp     loc_180071E1D
0x180071cfb  mov     r8, [rbp+var_28]
0x180071cff  lea     rax, [rbp+KeyHandle]
0x180071d03  mov     r9b, 1
0x180071d06  mov     qword ptr [rsp+70h+Length], rax
0x180071d0b  mov     rdx, rsi
0x180071d0e  mov     rcx, rdi
0x180071d11  call    BaseDllOpenMappingTarget
0x180071d16  test    eax, eax
0x180071d18  js      loc_180071E1D
0x180071d1e  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180071d22  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180071d26  jz      loc_180071E1D
0x180071d2c  lea     rax, [rbp+var_34]
0x180071d30  xor     r8d, r8d; KeyValueInformationClass
0x180071d33  mov     [rsp+70h+ResultLength], rax; ResultLength
0x180071d38  lea     r9, [rbp+KeyValueInformation]; KeyValueInformation
0x180071d3c  mov     rdx, rbx; ValueName
0x180071d3f  mov     [rsp+70h+Length], 10h; Length
0x180071d47  call    cs:__imp_NtQueryValueKey
0x180071d4e  nop     dword ptr [rax+rax+00h]
0x180071d53  mov     edx, 80000000h
0x180071d58  lea     ecx, [rax+rdx]
0x180071d5b  test    edx, ecx
0x180071d5d  jnz     short loc_180071D66
0x180071d5f  cmp     eax, 80000005h
0x180071d64  jnz     short loc_180071D86
0x180071d66  cmp     dword ptr [rbp+KeyValueInformation+4], 1
0x180071d6a  jz      short loc_180071D86
0x180071d6c  mov     rcx, [rbp+KeyHandle]; Handle
0x180071d70  call    cs:__imp_NtClose
0x180071d77  nop     dword ptr [rax+rax+00h]
0x180071d7c  mov     eax, 0C0000024h
0x180071d81  jmp     loc_180071E1D
0x180071d86  cmp     dword ptr [rdi], 2
0x180071d89  jz      short loc_180071DB0
0x180071d8b  cmp     dword ptr [rdi], 7
0x180071d8e  jz      short loc_180071DB0
0x180071d90  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180071d94  mov     rdx, rbx; ValueName
0x180071d97  call    cs:__imp_NtDeleteValueKey
0x180071d9e  nop     dword ptr [rax+rax+00h]
0x180071da3  mov     ebx, eax
0x180071da5  cmp     eax, 0C0000034h
0x180071daa  jnz     short loc_180071DFB
0x180071dac  xor     ebx, ebx
0x180071dae  jmp     short loc_180071DFB
0x180071db0  lea     r9, [rbp+DataSize]
0x180071db4  xor     edx, edx
0x180071db6  lea     r8, [rbp+Data]
0x180071dba  mov     rcx, rdi
0x180071dbd  call    BaseDllGetVariableValue
0x180071dc2  test    al, al
0x180071dc4  jnz     short loc_180071DCD
0x180071dc6  mov     ebx, 0C000000Dh
0x180071dcb  jmp     short loc_180071DFB
0x180071dcd  mov     eax, [rbp+DataSize]
0x180071dd0  mov     r9d, 1; Type
0x180071dd6  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180071dda  xor     r8d, r8d; TitleIndex
0x180071ddd  mov     dword ptr [rsp+70h+ResultLength], eax; DataSize
0x180071de1  mov     rdx, rbx; ValueName
0x180071de4  mov     rax, [rbp+Data]
0x180071de8  mov     qword ptr [rsp+70h+Length], rax; Data
0x180071ded  call    cs:__imp_NtSetValueKey
0x180071df4  nop     dword ptr [rax+rax+00h]
0x180071df9  mov     ebx, eax
0x180071dfb  mov     rcx, [rbp+KeyHandle]; Handle
0x180071dff  call    cs:__imp_NtClose
0x180071e06  nop     dword ptr [rax+rax+00h]
0x180071e0b  test    ebx, ebx
0x180071e0d  js      short loc_180071E1B
0x180071e0f  test    byte ptr [rsi+18h], 1
0x180071e13  mov     eax, 0C0000016h
0x180071e18  cmovnz  ebx, eax
0x180071e1b  mov     eax, ebx
0x180071e1d  mov     rcx, [rbp+var_8]
0x180071e21  xor     rcx, rsp; StackCookie
0x180071e24  call    __security_check_cookie
0x180071e29  add     rsp, 70h
0x180071e2d  pop     r14
0x180071e2f  pop     rdi
0x180071e30  pop     rsi
0x180071e31  pop     rbx
0x180071e32  pop     rbp
0x180071e33  retn
```
