# DwGetUserPreferences

- ea: `0x18003eab8`
- end: `0x18003ebee`
- name: `DwGetUserPreferences`
- size: `310`
- prototype: `__int64 __fastcall(void *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180044f90`

## callees

- `0x18003eab8`
- `0x18003f18c`
- `0x18003f2a4`
- `0x18003f408`
- `0x18003fa48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003eb68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003eb68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003eb94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003eb94`
- `rtutils!TracePrintfExA` at `0x18003eae6`
- `rtutils!TracePrintfExA` at `0x18003ebb6`
- `rtutils!TracePrintfExA` at `0x18003ebd6`
- `rtutils!TracePrintfExA` at `0x18003eae6`
- `rtutils!TracePrintfExA` at `0x18003ebb6`
- `rtutils!TracePrintfExA` at `0x18003ebd6`

## string_xrefs

- `0x18003ebaa`: `RegOpenKeyEx=%d`

## pseudocode

```c
__int64 __fastcall DwGetUserPreferences(void *a1, int a2)
{
  unsigned int v4; // edi
  const WCHAR *v5; // rdx
  __int64 v6; // rcx
  LSTATUS v7; // eax
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "GetUserPreferences(m=%d)", a2);
  if ( a2 )
  {
    if ( a2 == 1 )
      MoveLogonPreferences();
  }
  else
  {
    MoveUserPreferences();
  }
  v4 = SetDefaultUserPreferences(a1);
  if ( !v4 )
  {
    hKey = 0;
    if ( a2 )
    {
      if ( a2 == 1 )
      {
        v5 = L".DEFAULT\\Software\\Microsoft\\RAS Logon Phonebook";
        v6 = -2147483645;
      }
      else
      {
        v5 = L"Software\\Microsoft\\Router Phonebook";
        v6 = -2147483646;
      }
    }
    else
    {
      v5 = L"Software\\Microsoft\\RAS Phonebook";
      v6 = -2147483647;
    }
    v7 = RegOpenKeyExW((HKEY)v6, v5, 0, 0x20019u, &hKey);
    if ( v7 )
    {
      if ( g_dwTraceId == -1 )
        return v4;
      TracePrintfExA(g_dwTraceId, 0xCu, "RegOpenKeyEx=%d", v7);
    }
    else
    {
      if ( (unsigned int)ReadUserPreferences(hKey, a1) )
        v4 = SetDefaultUserPreferences(a1);
      RegCloseKey(hKey);
    }
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "GetUserPreferences=%d", v4);
  return v4;
}

```

## disassembly

```asm
0x18003eab8  mov     [rsp+arg_0], rbx
0x18003eabd  mov     [rsp+arg_8], rsi
0x18003eac2  push    rdi
0x18003eac3  sub     rsp, 30h
0x18003eac7  mov     rsi, rcx
0x18003eaca  mov     ebx, edx
0x18003eacc  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003ead2  cmp     ecx, 0FFFFFFFFh
0x18003ead5  jz      short loc_18003EAEC
0x18003ead7  mov     r9d, edx
0x18003eada  lea     r8, aGetuserprefere; "GetUserPreferences(m=%d)"
0x18003eae1  mov     edx, 0Ch; dwFlags
0x18003eae6  call    cs:__imp_TracePrintfExA
0x18003eaec  test    ebx, ebx
0x18003eaee  jnz     short loc_18003EAF7
0x18003eaf0  call    MoveUserPreferences
0x18003eaf5  jmp     short loc_18003EB01
0x18003eaf7  cmp     ebx, 1
0x18003eafa  jnz     short loc_18003EB01
0x18003eafc  call    MoveLogonPreferences
0x18003eb01  mov     edx, ebx
0x18003eb03  mov     rcx, rsi; void *
0x18003eb06  call    SetDefaultUserPreferences
0x18003eb0b  mov     edi, eax
0x18003eb0d  test    eax, eax
0x18003eb0f  jnz     loc_18003EBBC
0x18003eb15  mov     [rsp+38h+hKey], 0
0x18003eb1e  test    ebx, ebx
0x18003eb20  jnz     short loc_18003EB32
0x18003eb22  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\RAS Phonebook"
0x18003eb29  mov     rcx, 0FFFFFFFF80000001h
0x18003eb30  jmp     short loc_18003EB55
0x18003eb32  cmp     ebx, 1
0x18003eb35  jnz     short loc_18003EB47
0x18003eb37  lea     rdx, aDefaultSoftwar; ".DEFAULT\\Software\\Microsoft\\RAS Logo"...
0x18003eb3e  mov     rcx, 0FFFFFFFF80000003h
0x18003eb45  jmp     short loc_18003EB55
0x18003eb47  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Router Phonebook"
0x18003eb4e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003eb55  lea     rax, [rsp+38h+hKey]
0x18003eb5a  mov     r9d, 20019h; samDesired
0x18003eb60  xor     r8d, r8d; ulOptions
0x18003eb63  mov     [rsp+38h+phkResult], rax; phkResult
0x18003eb68  call    cs:__imp_RegOpenKeyExW
0x18003eb6e  test    eax, eax
0x18003eb70  jnz     short loc_18003EB9C
0x18003eb72  mov     rcx, [rsp+38h+hKey]; hKey
0x18003eb77  mov     rdx, rsi; void *
0x18003eb7a  call    ReadUserPreferences
0x18003eb7f  test    eax, eax
0x18003eb81  jz      short loc_18003EB8F
0x18003eb83  mov     edx, ebx
0x18003eb85  mov     rcx, rsi; void *
0x18003eb88  call    SetDefaultUserPreferences
0x18003eb8d  mov     edi, eax
0x18003eb8f  mov     rcx, [rsp+38h+hKey]; hKey
0x18003eb94  call    cs:__imp_RegCloseKey
0x18003eb9a  jmp     short loc_18003EBBC
0x18003eb9c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003eba2  cmp     ecx, 0FFFFFFFFh
0x18003eba5  jz      short loc_18003EBDC
0x18003eba7  mov     r9d, eax
0x18003ebaa  lea     r8, aRegopenkeyexD; "RegOpenKeyEx=%d"
0x18003ebb1  mov     edx, 0Ch; dwFlags
0x18003ebb6  call    cs:__imp_TracePrintfExA
0x18003ebbc  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003ebc2  cmp     ecx, 0FFFFFFFFh
0x18003ebc5  jz      short loc_18003EBDC
0x18003ebc7  mov     r9d, edi
0x18003ebca  lea     r8, aGetuserprefere_0; "GetUserPreferences=%d"
0x18003ebd1  mov     edx, 0Ch; dwFlags
0x18003ebd6  call    cs:__imp_TracePrintfExA
0x18003ebdc  mov     rbx, [rsp+38h+arg_0]
0x18003ebe1  mov     eax, edi
0x18003ebe3  mov     rsi, [rsp+38h+arg_8]
0x18003ebe8  add     rsp, 30h
0x18003ebec  pop     rdi
0x18003ebed  retn
```
