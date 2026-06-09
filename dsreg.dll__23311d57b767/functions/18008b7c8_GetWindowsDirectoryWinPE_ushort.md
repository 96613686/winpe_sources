# GetWindowsDirectoryWinPE(ushort * *)

- ea: `0x18008b7c8`
- end: `0x18008b89b`
- name: `?GetWindowsDirectoryWinPE@@YAKPEAPEAG@Z`
- size: `211`
- prototype: `unsigned int __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008bc58`

## callees

- `0x180006750`
- `0x1800084f4`
- `0x180009780`
- `0x18008b7c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008b805`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008b805`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b875`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b875`

## string_xrefs

- `0x18008b84e`: `RegReadStringValue`
- `0x18008b85f`: `GetWindowsDirectoryWinPE`
- `0x18008b818`: `%s: Cannot open registry key %s. Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall GetWindowsDirectoryWinPE(unsigned __int16 **a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int StringValue; // eax
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
                    2u,
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
0x18008b7c8  mov     r11, rsp
0x18008b7cb  mov     [r11+10h], rbx
0x18008b7cf  push    rdi
0x18008b7d0  sub     rsp, 30h
0x18008b7d4  mov     rdi, rcx
0x18008b7d7  mov     qword ptr [rcx], 0
0x18008b7de  lea     rax, [r11+8]
0x18008b7e2  mov     qword ptr [r11+8], 0
0x18008b7ea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008b7f1  mov     [r11-18h], rax
0x18008b7f5  mov     r9d, 20019h; samDesired
0x18008b7fb  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\RecoveryEnvironmen"...
0x18008b802  xor     r8d, r8d; ulOptions
0x18008b805  call    cs:__imp_RegOpenKeyExW
0x18008b80b  mov     ebx, eax
0x18008b80d  test    eax, eax
0x18008b80f  jz      short loc_18008B821
0x18008b811  lea     r8, aHkeyLocalMachi_4; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x18008b818  lea     rcx, aSCannotOpenReg_3; "%s: Cannot open registry key %s. Error "...
0x18008b81f  jmp     short loc_18008B85C
0x18008b821  mov     rcx, [rsp+38h+hKey]; hkey
0x18008b826  lea     r9, aHkeyLocalMachi_4; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x18008b82d  mov     [rsp+38h+var_10], rdi; unsigned __int16 **
0x18008b832  lea     r8, aTargetos; "TargetOS"
0x18008b839  xor     edx, edx; lpSubKey
0x18008b83b  mov     [rsp+38h+dwFlags], 2; dwFlags
0x18008b843  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18008b848  mov     ebx, eax
0x18008b84a  test    eax, eax
0x18008b84c  jz      short loc_18008B86B
0x18008b84e  lea     r8, aRegreadstringv; "RegReadStringValue"
0x18008b855  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18008b85c  mov     r9d, eax
0x18008b85f  lea     rdx, aGetwindowsdire; "GetWindowsDirectoryWinPE"
0x18008b866  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008b86b  mov     rcx, [rsp+38h+hKey]; hKey
0x18008b870  test    rcx, rcx
0x18008b873  jz      short loc_18008B87B
0x18008b875  call    cs:__imp_RegCloseKey
0x18008b87b  test    ebx, ebx
0x18008b87d  jz      short loc_18008B88E
0x18008b87f  mov     rcx, [rdi]; lpMem
0x18008b882  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008b887  mov     qword ptr [rdi], 0
0x18008b88e  mov     eax, ebx
0x18008b890  mov     rbx, [rsp+38h+arg_8]
0x18008b895  add     rsp, 30h
0x18008b899  pop     rdi
0x18008b89a  retn
```
