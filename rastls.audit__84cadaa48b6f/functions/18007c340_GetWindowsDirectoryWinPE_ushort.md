# GetWindowsDirectoryWinPE(ushort * *)

- ea: `0x18007c340`
- end: `0x18007c418`
- name: `?GetWindowsDirectoryWinPE@@YAKPEAPEAG@Z`
- size: `216`
- prototype: `unsigned int __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ee70`

## callees

- `0x18002f1ac`
- `0x18002f324`
- `0x18007c340`
- `0x18007c420`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c3eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c3eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007c37d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007c37d`

## string_xrefs

- `0x18007c3c4`: `RegReadStringValue`
- `0x18007c3d5`: `GetWindowsDirectoryWinPE`
- `0x18007c396`: `%s: Cannot open registry key %s. Error code: 0x%08x.`

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
0x18007c340  mov     r11, rsp
0x18007c343  mov     [r11+10h], rbx
0x18007c347  push    rdi
0x18007c348  sub     rsp, 30h
0x18007c34c  mov     rdi, rcx
0x18007c34f  mov     qword ptr [rcx], 0
0x18007c356  lea     rax, [r11+8]
0x18007c35a  mov     qword ptr [r11+8], 0
0x18007c362  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007c369  mov     [r11-18h], rax
0x18007c36d  mov     r9d, 20019h; samDesired
0x18007c373  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\RecoveryEnvironmen"...
0x18007c37a  xor     r8d, r8d; ulOptions
0x18007c37d  call    cs:__imp_RegOpenKeyExW
0x18007c384  nop     dword ptr [rax+rax+00h]
0x18007c389  mov     ebx, eax
0x18007c38b  test    eax, eax
0x18007c38d  jz      short loc_18007C39F
0x18007c38f  lea     r8, aHkeyLocalMachi_1; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x18007c396  lea     rcx, aSCannotOpenReg_1; "%s: Cannot open registry key %s. Error "...
0x18007c39d  jmp     short loc_18007C3D2
0x18007c39f  mov     rcx, [rsp+38h+hKey]; hkey
0x18007c3a4  lea     r9, aHkeyLocalMachi_1; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x18007c3ab  lea     r8, aTargetos; "TargetOS"
0x18007c3b2  mov     [rsp+38h+var_10], rdi; unsigned __int16 **
0x18007c3b7  xor     edx, edx; lpSubKey
0x18007c3b9  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18007c3be  mov     ebx, eax
0x18007c3c0  test    eax, eax
0x18007c3c2  jz      short loc_18007C3E1
0x18007c3c4  lea     r8, aRegreadstringv; "RegReadStringValue"
0x18007c3cb  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18007c3d2  mov     r9d, eax
0x18007c3d5  lea     rdx, aGetwindowsdire; "GetWindowsDirectoryWinPE"
0x18007c3dc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007c3e1  mov     rcx, [rsp+38h+hKey]; hKey
0x18007c3e6  test    rcx, rcx
0x18007c3e9  jz      short loc_18007C3F7
0x18007c3eb  call    cs:__imp_RegCloseKey
0x18007c3f2  nop     dword ptr [rax+rax+00h]
0x18007c3f7  test    ebx, ebx
0x18007c3f9  jz      short loc_18007C40A
0x18007c3fb  mov     rcx, [rdi]; void *
0x18007c3fe  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007c403  mov     qword ptr [rdi], 0
0x18007c40a  mov     eax, ebx
0x18007c40c  mov     rbx, [rsp+38h+arg_8]
0x18007c411  add     rsp, 30h
0x18007c415  pop     rdi
0x18007c416  retn
```
