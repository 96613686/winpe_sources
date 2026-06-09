# GetInstallLanguage

- ea: `0x180006418`
- end: `0x18000651a`
- name: `GetInstallLanguage`
- size: `258`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180006b68`

## callees

- `0x180001a4d`
- `0x180006418`
- `0x1800096b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800064b2`
- `ADVAPI32!RegCloseKey` at `0x1800064b2`
- `ADVAPI32!RegQueryValueExW` at `0x1800064a5`
- `ADVAPI32!RegQueryValueExW` at `0x1800064a5`
- `ADVAPI32!RegOpenKeyExW` at `0x180006475`
- `ADVAPI32!RegOpenKeyExW` at `0x180006475`

## string_xrefs

- `0x180006467`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  LSTATUS v0; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  hKey = 0;
  if ( !word_180014CC4 )
  {
    cbData = 6;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Active Setup\\Installed Components\\{89820200-ECBD-11CF-8B85-00AA005B4383}",
            0,
            1u,
            &hKey) )
    {
      v0 = RegQueryValueExW(hKey, L"Locale", 0, 0, (LPBYTE)&Data, &cbData);
      RegCloseKey(hKey);
      if ( !v0 )
      {
        while ( wcsnicmp_0(&Data, (&off_18000CD70)[2 * v0], 3u) )
        {
          if ( (unsigned int)++v0 >= 0x1C )
            return (unsigned __int16)word_180014CC4;
        }
        word_180014CC4 = *((_WORD *)&off_18000CD70 + 8 * v0 + 4);
      }
    }
  }
  return (unsigned __int16)word_180014CC4;
}

```

## disassembly

```asm
0x180006418  mov     r11, rsp
0x18000641b  mov     [r11+8], rbx
0x18000641f  mov     [r11+10h], rsi
0x180006423  push    rdi
0x180006424  sub     rsp, 50h
0x180006428  mov     rax, cs:__security_cookie
0x18000642f  xor     rax, rsp
0x180006432  mov     [rsp+58h+var_10], rax
0x180006437  xor     eax, eax
0x180006439  mov     qword ptr [r11-20h], 0
0x180006441  cmp     ax, cs:word_180014CC4
0x180006448  jnz     loc_1800064F6
0x18000644e  lea     rax, [r11-20h]
0x180006452  mov     [rsp+58h+cbData], 6
0x18000645a  mov     r9d, 1; samDesired
0x180006460  mov     [r11-38h], rax
0x180006464  xor     r8d, r8d; ulOptions
0x180006467  lea     rdx, SubKey; "Software\\Microsoft\\Active Setup\\Inst"...
0x18000646e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006475  call    cs:__imp_RegOpenKeyExW
0x18000647b  test    eax, eax
0x18000647d  jnz     short loc_1800064F6
0x18000647f  mov     rcx, [rsp+58h+hKey]; hKey
0x180006484  lea     rax, [rsp+58h+cbData]
0x180006489  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000648e  lea     rdx, ValueName; "Locale"
0x180006495  lea     rax, [rsp+58h+Data]
0x18000649a  xor     r9d, r9d; lpType
0x18000649d  xor     r8d, r8d; lpReserved
0x1800064a0  mov     [rsp+58h+lpData], rax; lpData
0x1800064a5  call    cs:__imp_RegQueryValueExW
0x1800064ab  mov     rcx, [rsp+58h+hKey]; hKey
0x1800064b0  mov     ebx, eax
0x1800064b2  call    cs:__imp_RegCloseKey
0x1800064b8  test    ebx, ebx
0x1800064ba  jnz     short loc_1800064F6
0x1800064bc  lea     rsi, off_18000CD70; "EN"
0x1800064c3  movsxd  rdi, ebx
0x1800064c6  lea     rcx, [rsp+58h+Data]; String1
0x1800064cb  add     rdi, rdi
0x1800064ce  mov     r8d, 3; MaxCount
0x1800064d4  mov     rdx, [rsi+rdi*8]; String2
0x1800064d8  call    _wcsnicmp_0
0x1800064dd  test    eax, eax
0x1800064df  jz      short loc_1800064EA
0x1800064e1  inc     ebx
0x1800064e3  cmp     ebx, 1Ch
0x1800064e6  jb      short loc_1800064C3
0x1800064e8  jmp     short loc_1800064F6
0x1800064ea  movzx   eax, word ptr [rsi+rdi*8+8]
0x1800064ef  mov     cs:word_180014CC4, ax
0x1800064f6  movzx   eax, cs:word_180014CC4
0x1800064fd  mov     rcx, [rsp+58h+var_10]
0x180006502  xor     rcx, rsp; StackCookie
0x180006505  call    __security_check_cookie
0x18000650a  mov     rbx, [rsp+58h+arg_0]
0x18000650f  mov     rsi, [rsp+58h+arg_8]
0x180006514  add     rsp, 50h
0x180006518  pop     rdi
0x180006519  retn
```
