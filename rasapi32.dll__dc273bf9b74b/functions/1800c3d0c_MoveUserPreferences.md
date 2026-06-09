# MoveUserPreferences

- ea: `0x1800c3d0c`
- end: `0x1800c3e68`
- name: `MoveUserPreferences`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800c3608`

## callees

- `0x18003ff38`
- `0x1800c3744`
- `0x1800c3d0c`
- `0x1800c3e70`
- `0x1800c51dc`
- `0x1800ded06`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c3d4e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c3dea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c3d4e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c3dea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3e27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3e31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3e27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3e31`
- `rtutils!TracePrintfExA` at `0x1800c3d84`
- `rtutils!TracePrintfExA` at `0x1800c3e0b`
- `rtutils!TracePrintfExA` at `0x1800c3e51`
- `rtutils!TracePrintfExA` at `0x1800c3d84`
- `rtutils!TracePrintfExA` at `0x1800c3e0b`
- `rtutils!TracePrintfExA` at `0x1800c3e51`

## string_xrefs

- `0x1800c3d40`: `Software\Microsoft\Windows NT\CurrentVersion\Network\RemoteAccess`
- `0x1800c3e45`: `MoveUserPreferences=%d`
- `0x1800c3e01`: `Delete old prefs`
- `0x1800c3e15`: `RemoteAccess`

## pseudocode

```c
LSTATUS MoveUserPreferences()
{
  LSTATUS result; // eax
  LSTATUS UserPreferences; // ebx
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
        UserPreferences = DwSetUserPreferences(v2, 0);
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
0x1800c3d0c  mov     [rsp-8+arg_10], rbx
0x1800c3d11  push    rbp
0x1800c3d12  lea     rbp, [rsp-57h]
0x1800c3d17  sub     rsp, 0F0h
0x1800c3d1e  lea     rax, [rbp+57h+arg_8]
0x1800c3d22  mov     [rbp+57h+arg_8], 0
0x1800c3d2a  mov     r9d, 20019h; samDesired
0x1800c3d30  mov     [rsp+0F0h+phkResult], rax; phkResult
0x1800c3d35  xor     r8d, r8d; ulOptions
0x1800c3d38  mov     [rbp+57h+hKey], 0
0x1800c3d40  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800c3d47  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800c3d4e  call    cs:__imp_RegOpenKeyExW
0x1800c3d54  test    eax, eax
0x1800c3d56  jnz     loc_1800C3E57
0x1800c3d5c  xor     edx, edx; Val
0x1800c3d5e  lea     rcx, [rbp+57h+var_C0]; void *
0x1800c3d62  mov     r8d, 0B8h; Size
0x1800c3d68  call    memset_0
0x1800c3d6d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c3d73  cmp     ecx, 0FFFFFFFFh
0x1800c3d76  jz      short loc_1800C3D8A
0x1800c3d78  lea     r8, aGettingOldPref; "Getting old prefs"
0x1800c3d7f  mov     edx, 0Ch; dwFlags
0x1800c3d84  call    cs:__imp_TracePrintfExA
0x1800c3d8a  xor     edx, edx
0x1800c3d8c  lea     rcx, [rbp+57h+var_C0]; void *
0x1800c3d90  call    SetDefaultUserPreferences
0x1800c3d95  mov     ebx, eax
0x1800c3d97  test    eax, eax
0x1800c3d99  jnz     loc_1800C3E2D
0x1800c3d9f  mov     rcx, [rbp+57h+arg_8]; hKey
0x1800c3da3  lea     rdx, [rbp+57h+var_C0]; void *
0x1800c3da7  call    ReadUserPreferences
0x1800c3dac  mov     ebx, eax
0x1800c3dae  test    eax, eax
0x1800c3db0  jnz     short loc_1800C3E2D
0x1800c3db2  xor     edx, edx
0x1800c3db4  mov     [rbp+57h+var_C], 1
0x1800c3dbb  lea     rcx, [rbp+57h+var_C0]
0x1800c3dbf  call    DwSetUserPreferences
0x1800c3dc4  mov     ebx, eax
0x1800c3dc6  test    eax, eax
0x1800c3dc8  jnz     short loc_1800C3E2D
0x1800c3dca  lea     rax, [rbp+57h+hKey]
0x1800c3dce  mov     r9d, 20006h; samDesired
0x1800c3dd4  xor     r8d, r8d; ulOptions
0x1800c3dd7  mov     [rsp+0F0h+phkResult], rax; phkResult
0x1800c3ddc  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800c3de3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800c3dea  call    cs:__imp_RegOpenKeyExW
0x1800c3df0  mov     ebx, eax
0x1800c3df2  test    eax, eax
0x1800c3df4  jnz     short loc_1800C3E2D
0x1800c3df6  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c3dfc  cmp     ecx, 0FFFFFFFFh
0x1800c3dff  jz      short loc_1800C3E11
0x1800c3e01  lea     r8, aDeleteOldPrefs; "Delete old prefs"
0x1800c3e08  lea     edx, [rax+0Ch]; dwFlags
0x1800c3e0b  call    cs:__imp_TracePrintfExA
0x1800c3e11  mov     rcx, [rbp+57h+hKey]
0x1800c3e15  lea     rdx, aRemoteaccess; "RemoteAccess"
0x1800c3e1c  call    MyRegDeleteTree
0x1800c3e21  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c3e25  mov     ebx, eax
0x1800c3e27  call    cs:__imp_RegCloseKey
0x1800c3e2d  mov     rcx, [rbp+57h+arg_8]; hKey
0x1800c3e31  call    cs:__imp_RegCloseKey
0x1800c3e37  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c3e3d  cmp     ecx, 0FFFFFFFFh
0x1800c3e40  jz      short loc_1800C3E57
0x1800c3e42  mov     r9d, ebx
0x1800c3e45  lea     r8, aMoveuserprefer; "MoveUserPreferences=%d"
0x1800c3e4c  mov     edx, 0Ch; dwFlags
0x1800c3e51  call    cs:__imp_TracePrintfExA
0x1800c3e57  mov     rbx, [rsp+0F0h+arg_10]
0x1800c3e5f  add     rsp, 0F0h
0x1800c3e66  pop     rbp
0x1800c3e67  retn
```
