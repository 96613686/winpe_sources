# MoveUserPreferences

- ea: `0x18003f2a4`
- end: `0x18003f400`
- name: `MoveUserPreferences`
- size: `348`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003eab8`

## callees

- `0x18003ebf4`
- `0x18003f2a4`
- `0x18003f408`
- `0x18003fa48`
- `0x18004176c`
- `0x18004d0d2`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f2e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f382`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f2e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f382`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f3bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f3c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f3bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f3c9`
- `rtutils!TracePrintfExA` at `0x18003f31c`
- `rtutils!TracePrintfExA` at `0x18003f3a3`
- `rtutils!TracePrintfExA` at `0x18003f3e9`
- `rtutils!TracePrintfExA` at `0x18003f31c`
- `rtutils!TracePrintfExA` at `0x18003f3a3`
- `rtutils!TracePrintfExA` at `0x18003f3e9`

## string_xrefs

- `0x18003f2d8`: `Software\Microsoft\Windows NT\CurrentVersion\Network\RemoteAccess`
- `0x18003f399`: `Delete old prefs`
- `0x18003f3ad`: `RemoteAccess`
- `0x18003f3dd`: `MoveUserPreferences=%d`

## pseudocode

```c
LSTATUS MoveUserPreferences()
{
  LSTATUS result; // eax
  int UserPreferences; // ebx
  _BYTE v2[180]; // [rsp+30h] [rbp-69h] BYREF
  int v3; // [rsp+E4h] [rbp+4Bh]
  HKEY hKey; // [rsp+100h] [rbp+67h] BYREF
  HKEY phkResult; // [rsp+108h] [rbp+6Fh] BYREF

  phkResult = 0;
  hKey = 0;
  result = RegOpenKeyExW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Network\\RemoteAccess",
             0,
             0x20019u,
             &phkResult);
  if ( !result )
  {
    memset_0(v2, 0, 0xB8u);
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Getting old prefs");
    UserPreferences = SetDefaultUserPreferences(v2);
    if ( !UserPreferences )
    {
      UserPreferences = ReadUserPreferences(phkResult, v2);
      if ( !UserPreferences )
      {
        v3 = 1;
        UserPreferences = DwSetUserPreferences((__int64)v2, 0);
        if ( !UserPreferences )
        {
          UserPreferences = RegOpenKeyExW(
                              HKEY_CURRENT_USER,
                              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Network",
                              0,
                              0x20006u,
                              &hKey);
          if ( !UserPreferences )
          {
            if ( g_dwTraceId != -1 )
              TracePrintfExA(g_dwTraceId, 0xCu, "Delete old prefs");
            UserPreferences = MyRegDeleteTree(hKey, L"RemoteAccess");
            RegCloseKey(hKey);
          }
        }
      }
    }
    result = RegCloseKey(phkResult);
    if ( g_dwTraceId != -1 )
      return TracePrintfExA(g_dwTraceId, 0xCu, "MoveUserPreferences=%d", UserPreferences);
  }
  return result;
}

```

## disassembly

```asm
0x18003f2a4  mov     [rsp-8+arg_10], rbx
0x18003f2a9  push    rbp
0x18003f2aa  lea     rbp, [rsp-57h]
0x18003f2af  sub     rsp, 0F0h
0x18003f2b6  lea     rax, [rbp+57h+arg_8]
0x18003f2ba  mov     [rbp+57h+arg_8], 0
0x18003f2c2  mov     r9d, 20019h; samDesired
0x18003f2c8  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18003f2cd  xor     r8d, r8d; ulOptions
0x18003f2d0  mov     [rbp+57h+hKey], 0
0x18003f2d8  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003f2df  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003f2e6  call    cs:__imp_RegOpenKeyExW
0x18003f2ec  test    eax, eax
0x18003f2ee  jnz     loc_18003F3EF
0x18003f2f4  xor     edx, edx; Val
0x18003f2f6  lea     rcx, [rbp+57h+var_C0]; void *
0x18003f2fa  mov     r8d, 0B8h; Size
0x18003f300  call    memset_0
0x18003f305  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003f30b  cmp     ecx, 0FFFFFFFFh
0x18003f30e  jz      short loc_18003F322
0x18003f310  lea     r8, aGettingOldPref; "Getting old prefs"
0x18003f317  mov     edx, 0Ch; dwFlags
0x18003f31c  call    cs:__imp_TracePrintfExA
0x18003f322  xor     edx, edx
0x18003f324  lea     rcx, [rbp+57h+var_C0]; void *
0x18003f328  call    SetDefaultUserPreferences
0x18003f32d  mov     ebx, eax
0x18003f32f  test    eax, eax
0x18003f331  jnz     loc_18003F3C5
0x18003f337  mov     rcx, [rbp+57h+arg_8]; hKey
0x18003f33b  lea     rdx, [rbp+57h+var_C0]; void *
0x18003f33f  call    ReadUserPreferences
0x18003f344  mov     ebx, eax
0x18003f346  test    eax, eax
0x18003f348  jnz     short loc_18003F3C5
0x18003f34a  xor     edx, edx
0x18003f34c  mov     [rbp+57h+var_C], 1
0x18003f353  lea     rcx, [rbp+57h+var_C0]
0x18003f357  call    DwSetUserPreferences
0x18003f35c  mov     ebx, eax
0x18003f35e  test    eax, eax
0x18003f360  jnz     short loc_18003F3C5
0x18003f362  lea     rax, [rbp+57h+hKey]
0x18003f366  mov     r9d, 20006h; samDesired
0x18003f36c  xor     r8d, r8d; ulOptions
0x18003f36f  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18003f374  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003f37b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003f382  call    cs:__imp_RegOpenKeyExW
0x18003f388  mov     ebx, eax
0x18003f38a  test    eax, eax
0x18003f38c  jnz     short loc_18003F3C5
0x18003f38e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003f394  cmp     ecx, 0FFFFFFFFh
0x18003f397  jz      short loc_18003F3A9
0x18003f399  lea     r8, aDeleteOldPrefs; "Delete old prefs"
0x18003f3a0  lea     edx, [rax+0Ch]; dwFlags
0x18003f3a3  call    cs:__imp_TracePrintfExA
0x18003f3a9  mov     rcx, [rbp+57h+hKey]
0x18003f3ad  lea     rdx, aRemoteaccess; "RemoteAccess"
0x18003f3b4  call    MyRegDeleteTree
0x18003f3b9  mov     rcx, [rbp+57h+hKey]; hKey
0x18003f3bd  mov     ebx, eax
0x18003f3bf  call    cs:__imp_RegCloseKey
0x18003f3c5  mov     rcx, [rbp+57h+arg_8]; hKey
0x18003f3c9  call    cs:__imp_RegCloseKey
0x18003f3cf  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003f3d5  cmp     ecx, 0FFFFFFFFh
0x18003f3d8  jz      short loc_18003F3EF
0x18003f3da  mov     r9d, ebx
0x18003f3dd  lea     r8, aMoveuserprefer; "MoveUserPreferences=%d"
0x18003f3e4  mov     edx, 0Ch; dwFlags
0x18003f3e9  call    cs:__imp_TracePrintfExA
0x18003f3ef  mov     rbx, [rsp+0F0h+arg_10]
0x18003f3f7  add     rsp, 0F0h
0x18003f3fe  pop     rbp
0x18003f3ff  retn
```
