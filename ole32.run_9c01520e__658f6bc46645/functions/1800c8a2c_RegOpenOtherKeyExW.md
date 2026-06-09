# RegOpenOtherKeyExW

- ea: `0x1800c8a2c`
- end: `0x1800c8be6`
- name: `RegOpenOtherKeyExW`
- size: `442`
- prototype: `int __fastcall(HKEY__ *hKey, const wchar_t *lpSubKey, unsigned int samDesired, unsigned int phkResult, HKEY__ **hKey, unsigned __int16 *lpSubKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18003a394`

## callees

- `0x180046460`
- `0x180046de0`
- `0x1800c8a2c`

## import_xrefs

- `ntdll!NtQuerySystemInformationEx` at `0x1800c8ab5`
- `ntdll!NtQuerySystemInformationEx` at `0x1800c8b19`
- `ntdll!NtQuerySystemInformationEx` at `0x1800c8ab5`
- `ntdll!NtQuerySystemInformationEx` at `0x1800c8b19`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x1800c8b48`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x1800c8b7d`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x1800c8b48`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x1800c8b7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c8b6c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c8baf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c8b6c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c8baf`

## pseudocode

```c
__int64 __fastcall RegOpenOtherKeyExW(
        HKEY hKey,
        const wchar_t *lpSubKey,
        unsigned int samDesired,
        REGSAM phkResult,
        HKEY__ **phkResulta)
{
  int v5; // esi
  char v9; // r15
  unsigned int v10; // edi
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  unsigned int *p_ReturnLength; // rbx
  unsigned int v16; // ecx
  unsigned __int16 v17; // bx
  unsigned int ReturnLength; // [rsp+30h] [rbp+0h] BYREF
  void *Process; // [rsp+38h] [rbp+8h] BYREF
  unsigned int *v21; // [rsp+40h] [rbp+10h]

  v5 = 0;
  ReturnLength = 0;
  Process = 0;
  v9 = 0;
  v10 = 0;
  if ( (phkResult & 0x300) != 0x200
    || NtCurrentTeb()->WowTebOffset < 0
    || (unsigned int)NtQuerySystemInformationEx(230, &Process, 8, 0, 0, &ReturnLength) != -1073741789 )
  {
    return (unsigned int)RegOpenKeyExW(hKey, lpSubKey, 0, phkResult, phkResulta);
  }
  v11 = ReturnLength + 15LL;
  if ( v11 <= ReturnLength )
    v11 = 0xFFFFFFFFFFFFFF0LL;
  v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
  v13 = alloca(v12);
  v14 = alloca(v12);
  p_ReturnLength = &ReturnLength;
  v21 = &ReturnLength;
  if ( (int)NtQuerySystemInformationEx(230, &Process, 8, &ReturnLength, ReturnLength, &ReturnLength) < 0 )
    return (unsigned int)RegOpenKeyExW(hKey, lpSubKey, 0, phkResult, phkResulta);
  while ( 1 )
  {
    v16 = p_ReturnLength[v5];
    if ( !(_WORD)v16 )
      break;
    if ( (v16 & 0x160000) == 0x120000 )
    {
      v9 = 1;
      v17 = Wow64SetThreadDefaultGuestMachine(LOWORD(p_ReturnLength[v5]));
      v10 = RegOpenKeyExW(hKey, lpSubKey, 0, phkResult, phkResulta);
      Wow64SetThreadDefaultGuestMachine(v17);
      if ( !v10 )
        return v10;
      p_ReturnLength = v21;
    }
    ++v5;
  }
  if ( !v9 )
    return (unsigned int)RegOpenKeyExW(hKey, lpSubKey, 0, phkResult, phkResulta);
  return v10;
}

```

## disassembly

```asm
0x1800c8a2c  push    rbp
0x1800c8a2e  push    r12
0x1800c8a30  push    r13
0x1800c8a32  push    r14
0x1800c8a34  push    r15
0x1800c8a36  sub     rsp, 50h
0x1800c8a3a  lea     rbp, [rsp+30h]
0x1800c8a3f  mov     [rbp+40h+arg_0], rbx
0x1800c8a43  mov     [rbp+40h+arg_8], rsi
0x1800c8a47  mov     [rbp+40h+arg_10], rdi
0x1800c8a4b  mov     rax, cs:__security_cookie
0x1800c8a52  xor     rax, rbp
0x1800c8a55  mov     [rbp+40h+var_28], rax
0x1800c8a59  xor     esi, esi
0x1800c8a5b  mov     eax, samDesired
0x1800c8a5e  and     eax, 300h
0x1800c8a63  mov     [rbp+40h+ReturnLength], esi
0x1800c8a66  mov     [rbp+40h+Process], rsi
0x1800c8a6a  mov     r14d, samDesired
0x1800c8a6d  mov     r12, lpSubKey
0x1800c8a70  mov     r13, hKey
0x1800c8a73  mov     r15b, sil
0x1800c8a76  mov     edi, esi
0x1800c8a78  cmp     eax, 200h
0x1800c8a7d  jnz     loc_1800C8B9A
0x1800c8a83  mov     rax, gs:30h
0x1800c8a8c  cmp     [rax+180Ch], esi
0x1800c8a92  jl      loc_1800C8B9A
0x1800c8a98  lea     rax, [rbp+40h+ReturnLength]
0x1800c8a9c  xor     samDesired, samDesired
0x1800c8a9f  mov     [rsp+70h+var_48], rax
0x1800c8aa4  lea     r8d, [rsi+8]
0x1800c8aa8  lea     lpSubKey, [rbp+40h+Process]
0x1800c8aac  mov     dword ptr [rsp+70h+var_50], esi
0x1800c8ab0  mov     ecx, 0E6h
0x1800c8ab5  call    cs:__imp_NtQuerySystemInformationEx
0x1800c8abc  nop     dword ptr [rax+rax+00h]
0x1800c8ac1  cmp     eax, 0C0000023h
0x1800c8ac6  jnz     loc_1800C8B9A
0x1800c8acc  mov     edx, [rbp+40h+ReturnLength]
0x1800c8acf  lea     hKey, [lpSubKey+0Fh]
0x1800c8ad3  cmp     hKey, lpSubKey
0x1800c8ad6  ja      short loc_1800C8AE2
0x1800c8ad8  mov     hKey, 0FFFFFFFFFFFFFF0h
0x1800c8ae2  and     hKey, 0FFFFFFFFFFFFFFF0h
0x1800c8ae6  mov     rax, hKey
0x1800c8ae9  call    _alloca_probe
0x1800c8aee  sub     rsp, hKey
0x1800c8af1  lea     rax, [rbp+40h+ReturnLength]
0x1800c8af5  mov     r8d, 8
0x1800c8afb  mov     ecx, 0E6h
0x1800c8b00  lea     rbx, [rsp+70h+ReturnLength]
0x1800c8b05  mov     [rsp+70h+var_48], rax
0x1800c8b0a  mov     dword ptr [rsp+70h+var_50], edx
0x1800c8b0e  mov     r9, rbx
0x1800c8b11  lea     lpSubKey, [rbp+40h+Process]
0x1800c8b15  mov     [rbp+40h+var_30], rbx
0x1800c8b19  call    cs:__imp_NtQuerySystemInformationEx
0x1800c8b20  nop     dword ptr [rax+rax+00h]
0x1800c8b25  test    eax, eax
0x1800c8b27  js      short loc_1800C8B9A
0x1800c8b29  mov     edx, esi
0x1800c8b2b  mov     ecx, [rbx+lpSubKey*4]
0x1800c8b2e  test    cx, cx
0x1800c8b31  jz      short loc_1800C8B95
0x1800c8b33  and     ecx, 160000h
0x1800c8b39  cmp     ecx, 120000h
0x1800c8b3f  jnz     short loc_1800C8B91
0x1800c8b41  movzx   ecx, word ptr [rbx+lpSubKey*4]
0x1800c8b45  mov     r15b, 1
0x1800c8b48  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x1800c8b4f  nop     dword ptr [rax+rax+00h]
0x1800c8b54  mov     samDesired, r14d; samDesired
0x1800c8b57  xor     r8d, r8d; ulOptions
0x1800c8b5a  movzx   ebx, ax
0x1800c8b5d  mov     lpSubKey, r12; lpSubKey
0x1800c8b60  mov     rax, [rbp+40h+phkResult]
0x1800c8b64  mov     hKey, r13; hKey
0x1800c8b67  mov     [rsp+70h+var_50], rax; phkResult
0x1800c8b6c  call    cs:__imp_RegOpenKeyExW
0x1800c8b73  nop     dword ptr [rax+rax+00h]
0x1800c8b78  movzx   ecx, bx
0x1800c8b7b  mov     edi, eax
0x1800c8b7d  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x1800c8b84  nop     dword ptr [rax+rax+00h]
0x1800c8b89  test    edi, edi
0x1800c8b8b  jz      short loc_1800C8BBD
0x1800c8b8d  mov     rbx, [rbp+40h+var_30]
0x1800c8b91  inc     esi
0x1800c8b93  jmp     short loc_1800C8B29
0x1800c8b95  test    r15b, r15b
0x1800c8b98  jnz     short loc_1800C8BBD
0x1800c8b9a  mov     rax, [rbp+40h+phkResult]
0x1800c8b9e  mov     samDesired, r14d; samDesired
0x1800c8ba1  xor     r8d, r8d; ulOptions
0x1800c8ba4  mov     [rsp+70h+var_50], rax; phkResult
0x1800c8ba9  mov     lpSubKey, r12; lpSubKey
0x1800c8bac  mov     hKey, r13; hKey
0x1800c8baf  call    cs:__imp_RegOpenKeyExW
0x1800c8bb6  nop     dword ptr [rax+rax+00h]
0x1800c8bbb  mov     edi, eax
0x1800c8bbd  mov     eax, edi
0x1800c8bbf  mov     hKey, [rbp+40h+var_28]
0x1800c8bc3  xor     hKey, rbp; StackCookie
0x1800c8bc6  call    __security_check_cookie
0x1800c8bcb  mov     rbx, [rbp+40h+arg_0]
0x1800c8bcf  mov     rsi, [rbp+40h+arg_8]
0x1800c8bd3  mov     rdi, [rbp+40h+arg_10]
0x1800c8bd7  lea     rsp, [rbp+20h]
0x1800c8bdb  pop     r15
0x1800c8bdd  pop     r14
0x1800c8bdf  pop     r13
0x1800c8be1  pop     r12
0x1800c8be3  pop     rbp
0x1800c8be4  retn
```
