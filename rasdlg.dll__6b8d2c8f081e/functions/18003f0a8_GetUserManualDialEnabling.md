# GetUserManualDialEnabling

- ea: `0x18003f0a8`
- end: `0x18003f185`
- name: `GetUserManualDialEnabling`
- size: `221`
- prototype: `LSTATUS __fastcall(_DWORD *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029100`

## callees

- `0x18003f0a8`
- `0x18004146c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f148`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f148`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f16b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f16b`
- `rtutils!TracePrintfExA` at `0x18003f0da`
- `rtutils!TracePrintfExA` at `0x18003f0da`

## pseudocode

```c
LSTATUS __fastcall GetUserManualDialEnabling(_DWORD *a1, int a2)
{
  const WCHAR *v4; // rdx
  __int64 v5; // rcx
  LSTATUS result; // eax
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  hKey = 0;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "GetUserManualDialEnabling (m=%d)", a2);
  if ( !a1 )
    return 87;
  *a1 = 0;
  if ( !a2 )
  {
    v4 = L"Software\\Microsoft\\RAS Phonebook";
    v5 = -2147483647;
    goto LABEL_8;
  }
  if ( a2 != 1 )
    return 87;
  v4 = L".DEFAULT\\Software\\Microsoft\\RAS Logon Phonebook";
  v5 = -2147483645;
LABEL_8:
  result = RegCreateKeyExW((HKEY)v5, v4, 0, 0, 0, 0x20019u, 0, &hKey, 0);
  if ( !result )
  {
    GetRegDword(hKey, L"OperatorDial", a1);
    RegCloseKey(hKey);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18003f0a8  mov     [rsp+arg_8], rbx
0x18003f0ad  push    rdi
0x18003f0ae  sub     rsp, 50h
0x18003f0b2  mov     rdi, rcx
0x18003f0b5  mov     [rsp+58h+hKey], 0
0x18003f0be  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003f0c4  mov     ebx, edx
0x18003f0c6  cmp     ecx, 0FFFFFFFFh
0x18003f0c9  jz      short loc_18003F0E0
0x18003f0cb  mov     r9d, edx
0x18003f0ce  lea     r8, aGetusermanuald; "GetUserManualDialEnabling (m=%d)"
0x18003f0d5  mov     edx, 0Ch; dwFlags
0x18003f0da  call    cs:__imp_TracePrintfExA
0x18003f0e0  test    rdi, rdi
0x18003f0e3  jz      loc_18003F175
0x18003f0e9  mov     dword ptr [rdi], 0
0x18003f0ef  test    ebx, ebx
0x18003f0f1  jnz     short loc_18003F103
0x18003f0f3  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\RAS Phonebook"
0x18003f0fa  mov     rcx, 0FFFFFFFF80000001h
0x18003f101  jmp     short loc_18003F116
0x18003f103  cmp     ebx, 1
0x18003f106  jnz     short loc_18003F175
0x18003f108  lea     rdx, aDefaultSoftwar; ".DEFAULT\\Software\\Microsoft\\RAS Logo"...
0x18003f10f  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003f116  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18003f11f  lea     rax, [rsp+58h+hKey]
0x18003f124  mov     [rsp+58h+phkResult], rax; phkResult
0x18003f129  xor     r9d, r9d; lpClass
0x18003f12c  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003f135  xor     r8d, r8d; Reserved
0x18003f138  mov     [rsp+58h+samDesired], 20019h; samDesired
0x18003f140  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18003f148  call    cs:__imp_RegCreateKeyExW
0x18003f14e  test    eax, eax
0x18003f150  jnz     short loc_18003F17A
0x18003f152  mov     rcx, [rsp+58h+hKey]
0x18003f157  lea     rdx, aOperatordial; "OperatorDial"
0x18003f15e  mov     r8, rdi
0x18003f161  call    GetRegDword
0x18003f166  mov     rcx, [rsp+58h+hKey]; hKey
0x18003f16b  call    cs:__imp_RegCloseKey
0x18003f171  xor     eax, eax
0x18003f173  jmp     short loc_18003F17A
0x18003f175  mov     eax, 57h ; 'W'
0x18003f17a  mov     rbx, [rsp+58h+arg_8]
0x18003f17f  add     rsp, 50h
0x18003f183  pop     rdi
0x18003f184  retn
```
