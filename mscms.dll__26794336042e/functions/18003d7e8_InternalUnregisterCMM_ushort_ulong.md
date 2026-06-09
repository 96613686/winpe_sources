# InternalUnregisterCMM(ushort *,ulong)

- ea: `0x18003d7e8`
- end: `0x18003d8c1`
- name: `?InternalUnregisterCMM@@YAHPEAGK@Z`
- size: `217`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18003e190`
- `0x18003e200`

## callees

- `0x18002e5f0`
- `0x18003d7e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003d88d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003d88d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d843`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d843`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d8a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d8a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d815`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d899`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d815`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d899`

## pseudocode

```c
__int64 __fastcall InternalUnregisterCMM(unsigned __int16 *a1, int a2)
{
  char v2; // bl
  DWORD v3; // ecx
  LSTATUS v5; // eax
  WCHAR v6; // ax
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  WCHAR ValueName[8]; // [rsp+38h] [rbp-20h] BYREF

  hKey = 0;
  v2 = a2;
  if ( a1 )
  {
    v3 = 87;
LABEL_3:
    SetLastError(v3);
    return 0;
  }
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, gszICMatcher, 0, 0x2000000u, &hKey);
  if ( v5 )
  {
    v3 = v5;
    goto LABEL_3;
  }
  ValueName[0] = SHIBYTE(a2);
  ValueName[1] = SBYTE2(a2);
  ValueName[2] = SBYTE1(a2);
  v6 = v2;
  v7 = 1;
  ValueName[3] = v6;
  ValueName[4] = 0;
  v8 = RegDeleteValueW(hKey, ValueName);
  if ( v8 )
  {
    SetLastError(v8);
    v7 = 0;
  }
  RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x18003d7e8  mov     [rsp+arg_8], edx
0x18003d7ec  push    rbx
0x18003d7ed  sub     rsp, 50h
0x18003d7f1  mov     rax, cs:__security_cookie
0x18003d7f8  xor     rax, rsp
0x18003d7fb  mov     [rsp+58h+var_10], rax
0x18003d800  mov     [rsp+58h+hKey], 0
0x18003d809  mov     ebx, edx
0x18003d80b  test    rcx, rcx
0x18003d80e  jz      short loc_18003D822
0x18003d810  mov     ecx, 57h ; 'W'; dwErrCode
0x18003d815  call    cs:__imp_SetLastError
0x18003d81b  xor     eax, eax
0x18003d81d  jmp     loc_18003D8AE
0x18003d822  lea     rax, [rsp+58h+hKey]
0x18003d827  mov     r9d, 2000000h; samDesired
0x18003d82d  xor     r8d, r8d; ulOptions
0x18003d830  mov     [rsp+58h+phkResult], rax; phkResult
0x18003d835  lea     rdx, gszICMatcher; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003d83c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d843  call    cs:__imp_RegOpenKeyExW
0x18003d849  test    eax, eax
0x18003d84b  jz      short loc_18003D851
0x18003d84d  mov     ecx, eax
0x18003d84f  jmp     short loc_18003D815
0x18003d851  movsx   eax, byte ptr [rsp+58h+arg_8+3]
0x18003d856  lea     rdx, [rsp+58h+ValueName]; lpValueName
0x18003d85b  mov     rcx, [rsp+58h+hKey]; hKey
0x18003d860  mov     [rsp+58h+ValueName], ax
0x18003d865  movsx   eax, byte ptr [rsp+58h+arg_8+2]
0x18003d86a  mov     [rsp+58h+var_1E], ax
0x18003d86f  movsx   eax, byte ptr [rsp+58h+arg_8+1]
0x18003d874  mov     [rsp+58h+var_1C], ax
0x18003d879  movsx   eax, bl
0x18003d87c  mov     ebx, 1
0x18003d881  mov     [rsp+58h+var_1A], ax
0x18003d886  xor     eax, eax
0x18003d888  mov     [rsp+58h+var_18], ax
0x18003d88d  call    cs:__imp_RegDeleteValueW
0x18003d893  test    eax, eax
0x18003d895  jz      short loc_18003D8A1
0x18003d897  mov     ecx, eax; dwErrCode
0x18003d899  call    cs:__imp_SetLastError
0x18003d89f  xor     ebx, ebx
0x18003d8a1  mov     rcx, [rsp+58h+hKey]; hKey
0x18003d8a6  call    cs:__imp_RegCloseKey
0x18003d8ac  mov     eax, ebx
0x18003d8ae  mov     rcx, [rsp+58h+var_10]
0x18003d8b3  xor     rcx, rsp; StackCookie
0x18003d8b6  call    __security_check_cookie
0x18003d8bb  add     rsp, 50h
0x18003d8bf  pop     rbx
0x18003d8c0  retn
```
