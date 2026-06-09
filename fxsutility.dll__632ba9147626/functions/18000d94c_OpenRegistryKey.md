# OpenRegistryKey

- ea: `0x18000d94c`
- end: `0x18000da15`
- name: `OpenRegistryKey`
- size: `201`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800155f8`
- `0x1800157a4`
- `0x1800159c0`

## callees

- `0x18000613c`
- `0x18000d94c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000d9c1`
- `KERNEL32!SetLastError` at `0x18000d9e2`
- `KERNEL32!SetLastError` at `0x18000d9c1`
- `KERNEL32!SetLastError` at `0x18000d9e2`
- `ADVAPI32!RegOpenKeyExW` at `0x18000da00`
- `ADVAPI32!RegOpenKeyExW` at `0x18000da00`
- `ADVAPI32!RegCreateKeyExW` at `0x18000d9a5`
- `ADVAPI32!RegCreateKeyExW` at `0x18000d9a5`

## string_xrefs

- `0x18000d9b1`: `RegCreateKeyEx() failed, ec=%d`
- `0x18000d9d4`: `Created new fax registry key, ec=%d`
- `0x18000da0c`: `RegOpenKeyEx() failed, ec=%d`

## pseudocode

```c
HKEY __fastcall OpenRegistryKey(__int64 a1, __int64 a2, int a3, REGSAM a4)
{
  unsigned int v4; // ebx
  HKEY phkResult; // [rsp+68h] [rbp+10h] BYREF
  DWORD v7; // [rsp+70h] [rbp+18h] BYREF

  phkResult = 0;
  v7 = 0;
  if ( a3 )
  {
    v4 = RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Fax\\UserInfo", 0, 0, 0, a4, 0, &phkResult, &v7);
    if ( v4 )
    {
      fax_dprintf(L"RegCreateKeyEx() failed, ec=%d", v4);
LABEL_4:
      SetLastError(v4);
      return 0;
    }
    if ( v7 == 1 )
      fax_dprintf(L"Created new fax registry key, ec=%d", 0);
  }
  else
  {
    v4 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Fax\\UserInfo", 0, a4, &phkResult);
    if ( v4 )
    {
      fax_dprintf(L"RegOpenKeyEx() failed, ec=%d", v4);
      goto LABEL_4;
    }
  }
  SetLastError(0);
  return phkResult;
}

```

## disassembly

```asm
0x18000d94c  mov     r11, rsp
0x18000d94f  mov     [r11+10h], rdx
0x18000d953  push    rbx
0x18000d954  sub     rsp, 50h
0x18000d958  mov     qword ptr [r11+10h], 0
0x18000d960  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Fax\\UserInfo"
0x18000d967  mov     [rsp+58h+arg_10], 0
0x18000d96f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000d976  test    r8d, r8d
0x18000d979  jz      short loc_18000D9F3
0x18000d97b  lea     rax, [r11+18h]
0x18000d97f  xor     r8d, r8d; Reserved
0x18000d982  mov     [r11-18h], rax
0x18000d986  lea     rax, [r11+10h]
0x18000d98a  mov     [r11-20h], rax
0x18000d98e  mov     qword ptr [r11-28h], 0
0x18000d996  mov     [r11-30h], r9d
0x18000d99a  xor     r9d, r9d; lpClass
0x18000d99d  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000d9a5  call    cs:__imp_RegCreateKeyExW
0x18000d9ab  mov     ebx, eax
0x18000d9ad  test    eax, eax
0x18000d9af  jz      short loc_18000D9CB
0x18000d9b1  lea     rcx, aRegcreatekeyex; "RegCreateKeyEx() failed, ec=%d"
0x18000d9b8  mov     edx, ebx
0x18000d9ba  call    fax_dprintf
0x18000d9bf  mov     ecx, ebx; dwErrCode
0x18000d9c1  call    cs:__imp_SetLastError
0x18000d9c7  xor     eax, eax
0x18000d9c9  jmp     short loc_18000D9ED
0x18000d9cb  cmp     [rsp+58h+arg_10], 1
0x18000d9d0  jnz     short loc_18000D9E0
0x18000d9d2  xor     edx, edx
0x18000d9d4  lea     rcx, aCreatedNewFaxR; "Created new fax registry key, ec=%d"
0x18000d9db  call    fax_dprintf
0x18000d9e0  xor     ecx, ecx; dwErrCode
0x18000d9e2  call    cs:__imp_SetLastError
0x18000d9e8  mov     rax, [rsp+58h+phkResult]
0x18000d9ed  add     rsp, 50h
0x18000d9f1  pop     rbx
0x18000d9f2  retn
0x18000d9f3  lea     rax, [rsp+58h+phkResult]
0x18000d9f8  xor     r8d, r8d; ulOptions
0x18000d9fb  mov     qword ptr [rsp+58h+dwOptions], rax; phkResult
0x18000da00  call    cs:__imp_RegOpenKeyExW
0x18000da06  mov     ebx, eax
0x18000da08  test    eax, eax
0x18000da0a  jz      short loc_18000D9E0
0x18000da0c  lea     rcx, aRegopenkeyexFa; "RegOpenKeyEx() failed, ec=%d"
0x18000da13  jmp     short loc_18000D9B8
```
