# GetWindowsDirectoryWinPE(ushort * *)

- ea: `0x180044480`
- end: `0x18004454b`
- name: `?GetWindowsDirectoryWinPE@@YAKPEAPEAG@Z`
- size: `203`
- prototype: `unsigned int __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180044554`

## callees

- `0x18000c1b0`
- `0x18000ced0`
- `0x180027448`
- `0x180044480`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800444bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800444bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044525`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044525`

## string_xrefs

- `0x1800444fe`: `RegReadStringValue`
- `0x18004450f`: `GetWindowsDirectoryWinPE`
- `0x1800444d0`: `%s: Cannot open registry key %s. Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall GetWindowsDirectoryWinPE(unsigned __int16 **a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int StringValue; // eax
  SIZE_T v6; // [rsp+20h] [rbp-18h]
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
0x180044480  mov     r11, rsp
0x180044483  mov     [r11+10h], rbx
0x180044487  push    rdi
0x180044488  sub     rsp, 30h
0x18004448c  mov     rdi, rcx
0x18004448f  mov     qword ptr [rcx], 0
0x180044496  lea     rax, [r11+8]
0x18004449a  mov     qword ptr [r11+8], 0
0x1800444a2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800444a9  mov     [r11-18h], rax
0x1800444ad  mov     r9d, 20019h; samDesired
0x1800444b3  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\RecoveryEnvironmen"...
0x1800444ba  xor     r8d, r8d; ulOptions
0x1800444bd  call    cs:__imp_RegOpenKeyExW
0x1800444c3  mov     ebx, eax
0x1800444c5  test    eax, eax
0x1800444c7  jz      short loc_1800444D9
0x1800444c9  lea     r8, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1800444d0  lea     rcx, aSCannotOpenReg_2; "%s: Cannot open registry key %s. Error "...
0x1800444d7  jmp     short loc_18004450C
0x1800444d9  mov     rcx, [rsp+38h+hKey]; hkey
0x1800444de  lea     r9, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1800444e5  lea     r8, aTargetos; "TargetOS"
0x1800444ec  mov     [rsp+38h+var_10], rdi; unsigned __int16 **
0x1800444f1  xor     edx, edx; lpSubKey
0x1800444f3  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x1800444f8  mov     ebx, eax
0x1800444fa  test    eax, eax
0x1800444fc  jz      short loc_18004451B
0x1800444fe  lea     r8, aRegreadstringv; "RegReadStringValue"
0x180044505  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18004450c  mov     r9d, eax
0x18004450f  lea     rdx, aGetwindowsdire; "GetWindowsDirectoryWinPE"
0x180044516  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004451b  mov     rcx, [rsp+38h+hKey]; hKey
0x180044520  test    rcx, rcx
0x180044523  jz      short loc_18004452B
0x180044525  call    cs:__imp_RegCloseKey
0x18004452b  test    ebx, ebx
0x18004452d  jz      short loc_18004453E
0x18004452f  mov     rcx, [rdi]; lpMem
0x180044532  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180044537  mov     qword ptr [rdi], 0
0x18004453e  mov     eax, ebx
0x180044540  mov     rbx, [rsp+38h+arg_8]
0x180044545  add     rsp, 30h
0x180044549  pop     rdi
0x18004454a  retn
```
