# RemoveAllInstalledProviders

- ea: `0x180035acc`
- end: `0x180035bb8`
- name: `RemoveAllInstalledProviders`
- size: `236`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180034690`

## callees

- `0x1800222f0`
- `0x1800327a8`
- `0x1800327cc`
- `0x180035acc`
- `0x180035bc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180035b3b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180035b3b`

## string_xrefs

- `0x180035b7b`: `Failed to get subkey name to remove provider`
- `0x180035b6d`: `Failed to remove provider using subkey name`

## pseudocode

```c
__int64 __fastcall RemoveAllInstalledProviders(HKEY hKey, __int64 a2, __int64 a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  __int64 result; // rax
  DWORD cchName; // [rsp+40h] [rbp-238h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+48h] [rbp-230h] BYREF
  WCHAR Name[256]; // [rsp+50h] [rbp-228h] BYREF

  ftLastWriteTime = 0;
  while ( 1 )
  {
    cchName = 256;
    v6 = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
    v7 = v6;
    if ( v6 )
      break;
    v8 = RemoveProviderByName((__int64)hKey, (__int64)Name, a2, a3);
    v7 = v8;
    if ( v8 )
    {
      LogErrorWithProvider(v8, L"Failed to remove provider using subkey name", Name);
      goto LABEL_6;
    }
  }
  LogError(v6, L"Failed to get subkey name to remove provider");
LABEL_6:
  result = 0;
  if ( v7 != 259 )
    return v7;
  return result;
}

```

## disassembly

```asm
0x180035acc  mov     [rsp+arg_18], rbx
0x180035ad1  push    rbp
0x180035ad2  push    rsi
0x180035ad3  push    rdi
0x180035ad4  sub     rsp, 260h
0x180035adb  mov     rax, cs:__security_cookie
0x180035ae2  xor     rax, rsp
0x180035ae5  mov     [rsp+278h+var_28], rax
0x180035aed  mov     rbp, r8
0x180035af0  mov     qword ptr [rsp+278h+ftLastWriteTime.dwLowDateTime], 0
0x180035af9  mov     rsi, rdx
0x180035afc  mov     rdi, rcx
0x180035aff  lea     rax, [rsp+278h+ftLastWriteTime]
0x180035b04  mov     [rsp+278h+cchName], 100h
0x180035b0c  mov     [rsp+278h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180035b11  lea     r9, [rsp+278h+cchName]; lpcchName
0x180035b16  mov     [rsp+278h+lpcchClass], 0; lpcchClass
0x180035b1f  lea     r8, [rsp+278h+Name]; lpName
0x180035b24  mov     [rsp+278h+lpClass], 0; lpClass
0x180035b2d  xor     edx, edx; dwIndex
0x180035b2f  mov     rcx, rdi; hKey
0x180035b32  mov     [rsp+278h+lpReserved], 0; lpReserved
0x180035b3b  call    cs:__imp_RegEnumKeyExW
0x180035b42  nop     dword ptr [rax+rax+00h]
0x180035b47  mov     ebx, eax
0x180035b49  test    eax, eax
0x180035b4b  jnz     short loc_180035B7B
0x180035b4d  mov     r9, rbp
0x180035b50  lea     rdx, [rsp+278h+Name]
0x180035b55  mov     r8, rsi
0x180035b58  mov     rcx, rdi
0x180035b5b  call    RemoveProviderByName
0x180035b60  mov     ebx, eax
0x180035b62  test    eax, eax
0x180035b64  jz      short loc_180035AFF
0x180035b66  lea     r8, [rsp+278h+Name]
0x180035b6b  mov     ecx, eax
0x180035b6d  lea     rdx, aFailedToRemove; "Failed to remove provider using subkey "...
0x180035b74  call    LogErrorWithProvider
0x180035b79  jmp     short loc_180035B89
0x180035b7b  lea     rdx, aFailedToGetSub; "Failed to get subkey name to remove pro"...
0x180035b82  mov     ecx, eax
0x180035b84  call    LogError
0x180035b89  xor     eax, eax
0x180035b8b  cmp     ebx, 103h
0x180035b91  cmovnz  eax, ebx
0x180035b94  mov     rcx, [rsp+278h+var_28]
0x180035b9c  xor     rcx, rsp; StackCookie
0x180035b9f  call    __security_check_cookie
0x180035ba4  mov     rbx, [rsp+278h+arg_18]
0x180035bac  add     rsp, 260h
0x180035bb3  pop     rdi
0x180035bb4  pop     rsi
0x180035bb5  pop     rbp
0x180035bb6  retn
```
