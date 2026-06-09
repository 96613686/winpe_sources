# GetWindowsDirectoryWinPE(ushort * *)

- ea: `0x1800240ec`
- end: `0x1800241b7`
- name: `?GetWindowsDirectoryWinPE@@YAKPEAPEAG@Z`
- size: `203`
- prototype: `unsigned int __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010048`

## callees

- `0x180010218`
- `0x180010320`
- `0x1800240ec`
- `0x1800241c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024129`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024129`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024191`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024191`

## string_xrefs

- `0x18002416a`: `RegReadStringValue`
- `0x18002413c`: `%s: Cannot open registry key %s. Error code: 0x%08x.`
- `0x18002417b`: `GetWindowsDirectoryWinPE`

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
0x1800240ec  mov     r11, rsp
0x1800240ef  mov     [r11+10h], rbx
0x1800240f3  push    rdi
0x1800240f4  sub     rsp, 30h
0x1800240f8  mov     rdi, rcx
0x1800240fb  mov     qword ptr [rcx], 0
0x180024102  lea     rax, [r11+8]
0x180024106  mov     qword ptr [r11+8], 0
0x18002410e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180024115  mov     [r11-18h], rax
0x180024119  mov     r9d, 20019h; samDesired
0x18002411f  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\RecoveryEnvironmen"...
0x180024126  xor     r8d, r8d; ulOptions
0x180024129  call    cs:__imp_RegOpenKeyExW
0x18002412f  mov     ebx, eax
0x180024131  test    eax, eax
0x180024133  jz      short loc_180024145
0x180024135  lea     r8, aHkeyLocalMachi_1; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x18002413c  lea     rcx, aSCannotOpenReg_1; "%s: Cannot open registry key %s. Error "...
0x180024143  jmp     short loc_180024178
0x180024145  mov     rcx, [rsp+38h+hKey]; hkey
0x18002414a  lea     r9, aHkeyLocalMachi_1; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x180024151  lea     r8, aTargetos; "TargetOS"
0x180024158  mov     [rsp+38h+var_10], rdi; unsigned __int16 **
0x18002415d  xor     edx, edx; lpSubKey
0x18002415f  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x180024164  mov     ebx, eax
0x180024166  test    eax, eax
0x180024168  jz      short loc_180024187
0x18002416a  lea     r8, aRegreadstringv; "RegReadStringValue"
0x180024171  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180024178  mov     r9d, eax
0x18002417b  lea     rdx, aGetwindowsdire; "GetWindowsDirectoryWinPE"
0x180024182  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180024187  mov     rcx, [rsp+38h+hKey]; hKey
0x18002418c  test    rcx, rcx
0x18002418f  jz      short loc_180024197
0x180024191  call    cs:__imp_RegCloseKey
0x180024197  test    ebx, ebx
0x180024199  jz      short loc_1800241AA
0x18002419b  mov     rcx, [rdi]; void *
0x18002419e  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800241a3  mov     qword ptr [rdi], 0
0x1800241aa  mov     eax, ebx
0x1800241ac  mov     rbx, [rsp+38h+arg_8]
0x1800241b1  add     rsp, 30h
0x1800241b5  pop     rdi
0x1800241b6  retn
```
