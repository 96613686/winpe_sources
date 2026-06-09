# GetWindowsDirectoryWinPE(ushort * *)

- ea: `0x180076f80`
- end: `0x18007704b`
- name: `?GetWindowsDirectoryWinPE@@YAKPEAPEAG@Z`
- size: `203`
- prototype: `unsigned int __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c978`

## callees

- `0x18002cca4`
- `0x18002ce0c`
- `0x180076f80`
- `0x180077054`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077025`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077025`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076fbd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076fbd`

## string_xrefs

- `0x180076ffe`: `RegReadStringValue`
- `0x180076fd0`: `%s: Cannot open registry key %s. Error code: 0x%08x.`
- `0x18007700f`: `GetWindowsDirectoryWinPE`

## pseudocode

```c
__int64 __fastcall GetWindowsDirectoryWinPE(unsigned __int16 **a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int StringValue; // eax
  DWORD v6; // [rsp+20h] [rbp-18h]
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  *a1 = 0;
  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\RecoveryEnvironment", 0, 0x20019u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    Logger::TraceError(
      L"%s: Cannot open registry key %s. Error code: 0x%08x.",
      L"GetWindowsDirectoryWinPE",
      L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\RecoveryEnvironment",
      v2);
  }
  else
  {
    StringValue = RegReadStringValue(
                    hKey,
                    0,
                    L"TargetOS",
                    L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\RecoveryEnvironment",
                    v6,
                    a1);
    v3 = StringValue;
    if ( StringValue )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"GetWindowsDirectoryWinPE",
        L"RegReadStringValue",
        StringValue);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v3 )
  {
    SafeFree(*a1);
    *a1 = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180076f80  mov     r11, rsp
0x180076f83  mov     [r11+10h], rbx
0x180076f87  push    rdi
0x180076f88  sub     rsp, 30h
0x180076f8c  mov     rdi, rcx
0x180076f8f  mov     qword ptr [rcx], 0
0x180076f96  lea     rax, [r11+8]
0x180076f9a  mov     qword ptr [r11+8], 0
0x180076fa2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180076fa9  mov     [r11-18h], rax
0x180076fad  mov     r9d, 20019h; samDesired
0x180076fb3  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\RecoveryEnvironmen"...
0x180076fba  xor     r8d, r8d; ulOptions
0x180076fbd  call    cs:__imp_RegOpenKeyExW
0x180076fc3  mov     ebx, eax
0x180076fc5  test    eax, eax
0x180076fc7  jz      short loc_180076FD9
0x180076fc9  lea     r8, aHkeyLocalMachi_1; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x180076fd0  lea     rcx, aSCannotOpenReg_1; "%s: Cannot open registry key %s. Error "...
0x180076fd7  jmp     short loc_18007700C
0x180076fd9  mov     rcx, [rsp+38h+hKey]; hkey
0x180076fde  lea     r9, aHkeyLocalMachi_1; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x180076fe5  lea     r8, aTargetos; "TargetOS"
0x180076fec  mov     [rsp+38h+var_10], rdi; unsigned __int16 **
0x180076ff1  xor     edx, edx; lpSubKey
0x180076ff3  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x180076ff8  mov     ebx, eax
0x180076ffa  test    eax, eax
0x180076ffc  jz      short loc_18007701B
0x180076ffe  lea     r8, aRegreadstringv; "RegReadStringValue"
0x180077005  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18007700c  mov     r9d, eax
0x18007700f  lea     rdx, aGetwindowsdire; "GetWindowsDirectoryWinPE"
0x180077016  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007701b  mov     rcx, [rsp+38h+hKey]; hKey
0x180077020  test    rcx, rcx
0x180077023  jz      short loc_18007702B
0x180077025  call    cs:__imp_RegCloseKey
0x18007702b  test    ebx, ebx
0x18007702d  jz      short loc_18007703E
0x18007702f  mov     rcx, [rdi]; void *
0x180077032  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180077037  mov     qword ptr [rdi], 0
0x18007703e  mov     eax, ebx
0x180077040  mov     rbx, [rsp+38h+arg_8]
0x180077045  add     rsp, 30h
0x180077049  pop     rdi
0x18007704a  retn
```
