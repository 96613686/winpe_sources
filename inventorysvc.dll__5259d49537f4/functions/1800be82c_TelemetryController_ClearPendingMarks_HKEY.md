# TelemetryController::ClearPendingMarks(HKEY__ *)

- ea: `0x1800be82c`
- end: `0x1800be9e2`
- name: `?ClearPendingMarks@TelemetryController@@SAXPEAUHKEY__@@@Z`
- size: `438`
- prototype: `void __fastcall(HKEY, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ff40`

## callees

- `0x180002bf0`
- `0x1800152d0`
- `0x180026430`
- `0x1800be82c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800be94b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800be94b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800be99b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800be99b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be956`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be9b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be956`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800be9b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800be8ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800be8ba`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800be911`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800be911`

## string_xrefs

- `0x1800be886`: `CompatTelRunner`
- `0x1800be877`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\TelemetryController`
- `0x1800be8c4`: `RegOpenKeyEx failed [%d]`
- `0x1800be91b`: `RegOpenKeyW failed [%d]`

## pseudocode

```c
void __fastcall TelemetryController::ClearPendingMarks(HKEY a1, __int64 a2)
{
  HKEY v2; // rbx
  LSTATUS v3; // eax
  int v4; // edi
  DWORD v5; // edx
  LSTATUS v6; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v9; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+270h] [rbp+170h] BYREF

  cchName = 260;
  v2 = a1;
  hKey = 0;
  if ( a1 )
  {
    hKey = a1;
  }
  else
  {
    Windows::Compat::Shared::Registry::GetPersistedLocation(
      SubKey,
      a2,
      L"CompatTelRunner",
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\TelemetryController",
      1);
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, &hKey);
    if ( v3 )
    {
      AslLogCallPrintf(1, "TelemetryController::ClearPendingMarks", 495, "RegOpenKeyEx failed [%d]", v3);
      return;
    }
    a1 = hKey;
  }
  v4 = 1;
  v5 = 0;
  while ( !RegEnumKeyExW(a1, v5, Name, &cchName, 0, 0, 0, 0) )
  {
    v9 = 0;
    v6 = RegOpenKeyW(hKey, Name, &v9);
    if ( v6 )
    {
      AslLogCallPrintf(1, "TelemetryController::ClearPendingMarks", 506, "RegOpenKeyW failed [%d]", v6);
    }
    else
    {
      RegDeleteValueW(v9, L"Pending");
      RegCloseKey(v9);
    }
    a1 = hKey;
    v5 = v4++;
    cchName = 260;
  }
  if ( !v2 )
  {
    if ( hKey )
      RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x1800be82c  mov     [rsp-8+arg_8], rbx
0x1800be831  mov     [rsp-8+arg_10], rdi
0x1800be836  push    rbp
0x1800be837  lea     rbp, [rsp-390h]
0x1800be83f  sub     rsp, 490h
0x1800be846  mov     rax, cs:__security_cookie
0x1800be84d  xor     rax, rsp
0x1800be850  mov     [rbp+390h+var_10], rax
0x1800be857  mov     [rsp+490h+cchName], 104h
0x1800be85f  mov     rbx, rcx
0x1800be862  mov     [rsp+490h+hKey], 0
0x1800be86b  test    rcx, rcx
0x1800be86e  jz      short loc_1800BE877
0x1800be870  mov     [rsp+490h+hKey], rcx
0x1800be875  jmp     short loc_1800BE8F0
0x1800be877  lea     r9, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800be87e  mov     dword ptr [rsp+490h+phkResult], 1; int
0x1800be886  lea     r8, aCompattelrunne_0; "CompatTelRunner"
0x1800be88d  lea     rcx, [rbp+390h+SubKey]; unsigned __int16 *
0x1800be894  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x1800be899  lea     rax, [rsp+490h+hKey]
0x1800be89e  mov     r9d, 0F003Fh; samDesired
0x1800be8a4  xor     r8d, r8d; ulOptions
0x1800be8a7  mov     [rsp+490h+phkResult], rax; phkResult
0x1800be8ac  lea     rdx, [rbp+390h+SubKey]; lpSubKey
0x1800be8b3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800be8ba  call    cs:__imp_RegOpenKeyExW
0x1800be8c0  test    eax, eax
0x1800be8c2  jz      short loc_1800BE8EB
0x1800be8c4  lea     r9, aRegopenkeyexFa; "RegOpenKeyEx failed [%d]"
0x1800be8cb  mov     dword ptr [rsp+490h+phkResult], eax
0x1800be8cf  mov     r8d, 1EFh
0x1800be8d5  lea     rdx, aTelemetrycontr; "TelemetryController::ClearPendingMarks"
0x1800be8dc  mov     ecx, 1
0x1800be8e1  call    AslLogCallPrintf
0x1800be8e6  jmp     loc_1800BE9BE
0x1800be8eb  mov     rcx, [rsp+490h+hKey]
0x1800be8f0  mov     edi, 1
0x1800be8f5  xor     edx, edx
0x1800be8f7  jmp     short loc_1800BE96D
0x1800be8f9  mov     rcx, [rsp+490h+hKey]; hKey
0x1800be8fe  lea     r8, [rsp+490h+var_440]; phkResult
0x1800be903  lea     rdx, [rsp+490h+Name]; lpSubKey
0x1800be908  mov     [rsp+490h+var_440], 0
0x1800be911  call    cs:__imp_RegOpenKeyW
0x1800be917  test    eax, eax
0x1800be919  jz      short loc_1800BE93F
0x1800be91b  lea     r9, aRegopenkeywFai; "RegOpenKeyW failed [%d]"
0x1800be922  mov     dword ptr [rsp+490h+phkResult], eax
0x1800be926  mov     r8d, 1FAh
0x1800be92c  lea     rdx, aTelemetrycontr; "TelemetryController::ClearPendingMarks"
0x1800be933  mov     ecx, 1
0x1800be938  call    AslLogCallPrintf
0x1800be93d  jmp     short loc_1800BE95C
0x1800be93f  mov     rcx, [rsp+490h+var_440]; hKey
0x1800be944  lea     rdx, ValueName; "Pending"
0x1800be94b  call    cs:__imp_RegDeleteValueW
0x1800be951  mov     rcx, [rsp+490h+var_440]; hKey
0x1800be956  call    cs:__imp_RegCloseKey
0x1800be95c  mov     rcx, [rsp+490h+hKey]; hKey
0x1800be961  mov     edx, edi; dwIndex
0x1800be963  inc     edi
0x1800be965  mov     [rsp+490h+cchName], 104h
0x1800be96d  mov     [rsp+490h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800be976  lea     r9, [rsp+490h+cchName]; lpcchName
0x1800be97b  mov     [rsp+490h+lpcchClass], 0; lpcchClass
0x1800be984  lea     r8, [rsp+490h+Name]; lpName
0x1800be989  mov     [rsp+490h+lpClass], 0; lpClass
0x1800be992  mov     [rsp+490h+phkResult], 0; lpReserved
0x1800be99b  call    cs:__imp_RegEnumKeyExW
0x1800be9a1  test    eax, eax
0x1800be9a3  jz      loc_1800BE8F9
0x1800be9a9  test    rbx, rbx
0x1800be9ac  jnz     short loc_1800BE9BE
0x1800be9ae  mov     rcx, [rsp+490h+hKey]; hKey
0x1800be9b3  test    rcx, rcx
0x1800be9b6  jz      short loc_1800BE9BE
0x1800be9b8  call    cs:__imp_RegCloseKey
0x1800be9be  mov     rcx, [rbp+390h+var_10]
0x1800be9c5  xor     rcx, rsp; StackCookie
0x1800be9c8  call    __security_check_cookie
0x1800be9cd  lea     r11, [rsp+490h+var_s0]
0x1800be9d5  mov     rbx, [r11+18h]
0x1800be9d9  mov     rdi, [r11+20h]
0x1800be9dd  mov     rsp, r11
0x1800be9e0  pop     rbp
0x1800be9e1  retn
```
