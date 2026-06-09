# MoveLogonPreferences

- ea: `0x18003f18c`
- end: `0x18003f29b`
- name: `MoveLogonPreferences`
- size: `271`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003eab8`

## callees

- `0x18003e9ec`
- `0x18003ebf4`
- `0x18003f18c`
- `0x18003f408`
- `0x18003fa48`
- `0x18004d0d2`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f1e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f20c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f1e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f20c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f21a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f284`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f21a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f284`
- `rtutils!TracePrintfExA` at `0x18003f27a`
- `rtutils!TracePrintfExA` at `0x18003f27a`

## string_xrefs

- `0x18003f26e`: `MoveLogonPreferences=%d`

## pseudocode

```c
LSTATUS MoveLogonPreferences()
{
  LSTATUS result; // eax
  int UserPreferences; // ebx
  _BYTE v2[192]; // [rsp+30h] [rbp-69h] BYREF
  HKEY phkResult; // [rsp+100h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+108h] [rbp+6Fh] BYREF

  phkResult = 0;
  hKey = 0;
  memset_0(v2, 0, 0xB8u);
  result = RegOpenKeyExW(HKEY_USERS, L".DEFAULT\\Software\\Microsoft\\RAS Phonebook", 0, 0x20019u, &phkResult);
  if ( !result )
  {
    if ( RegOpenKeyExW(HKEY_USERS, L".DEFAULT\\Software\\Microsoft\\RAS Logon Phonebook", 0, 0x20019u, &hKey) )
    {
      UserPreferences = SetDefaultUserPreferences(v2);
      if ( !UserPreferences )
      {
        UserPreferences = ReadUserPreferences(phkResult, v2);
        if ( !UserPreferences )
          UserPreferences = DwSetUserPreferences((__int64)v2, 1);
      }
      DestroyUserPreferences(v2);
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "MoveLogonPreferences=%d", UserPreferences);
    }
    else
    {
      RegCloseKey(hKey);
    }
    return RegCloseKey(phkResult);
  }
  return result;
}

```

## disassembly

```asm
0x18003f18c  mov     [rsp-8+arg_10], rbx
0x18003f191  push    rbp
0x18003f192  lea     rbp, [rsp-57h]
0x18003f197  sub     rsp, 0F0h
0x18003f19e  xor     edx, edx; Val
0x18003f1a0  mov     [rbp+57h+arg_0], 0
0x18003f1a8  mov     r8d, 0B8h; Size
0x18003f1ae  mov     [rbp+57h+hKey], 0
0x18003f1b6  lea     rcx, [rbp+57h+var_C0]; void *
0x18003f1ba  call    memset_0
0x18003f1bf  lea     rax, [rbp+57h+arg_0]
0x18003f1c3  mov     ebx, 20019h
0x18003f1c8  mov     r9d, ebx; samDesired
0x18003f1cb  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18003f1d0  xor     r8d, r8d; ulOptions
0x18003f1d3  lea     rdx, aDefaultSoftwar_0; ".DEFAULT\\Software\\Microsoft\\RAS Phon"...
0x18003f1da  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003f1e1  call    cs:__imp_RegOpenKeyExW
0x18003f1e7  test    eax, eax
0x18003f1e9  jnz     loc_18003F28A
0x18003f1ef  lea     rax, [rbp+57h+hKey]
0x18003f1f3  mov     r9d, ebx; samDesired
0x18003f1f6  xor     r8d, r8d; ulOptions
0x18003f1f9  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18003f1fe  lea     rdx, aDefaultSoftwar; ".DEFAULT\\Software\\Microsoft\\RAS Logo"...
0x18003f205  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003f20c  call    cs:__imp_RegOpenKeyExW
0x18003f212  test    eax, eax
0x18003f214  jnz     short loc_18003F222
0x18003f216  mov     rcx, [rbp+57h+hKey]; hKey
0x18003f21a  call    cs:__imp_RegCloseKey
0x18003f220  jmp     short loc_18003F280
0x18003f222  mov     edx, 1
0x18003f227  lea     rcx, [rbp+57h+var_C0]; void *
0x18003f22b  call    SetDefaultUserPreferences
0x18003f230  mov     ebx, eax
0x18003f232  test    eax, eax
0x18003f234  jnz     short loc_18003F257
0x18003f236  mov     rcx, [rbp+57h+arg_0]; hKey
0x18003f23a  lea     rdx, [rbp+57h+var_C0]; void *
0x18003f23e  call    ReadUserPreferences
0x18003f243  mov     ebx, eax
0x18003f245  test    eax, eax
0x18003f247  jnz     short loc_18003F257
0x18003f249  lea     edx, [rax+1]
0x18003f24c  lea     rcx, [rbp+57h+var_C0]
0x18003f250  call    DwSetUserPreferences
0x18003f255  mov     ebx, eax
0x18003f257  lea     rcx, [rbp+57h+var_C0]; void *
0x18003f25b  call    DestroyUserPreferences
0x18003f260  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003f266  cmp     ecx, 0FFFFFFFFh
0x18003f269  jz      short loc_18003F280
0x18003f26b  mov     r9d, ebx
0x18003f26e  lea     r8, aMovelogonprefe; "MoveLogonPreferences=%d"
0x18003f275  mov     edx, 0Ch; dwFlags
0x18003f27a  call    cs:__imp_TracePrintfExA
0x18003f280  mov     rcx, [rbp+57h+arg_0]; hKey
0x18003f284  call    cs:__imp_RegCloseKey
0x18003f28a  mov     rbx, [rsp+0F0h+arg_10]
0x18003f292  add     rsp, 0F0h
0x18003f299  pop     rbp
0x18003f29a  retn
```
