# GetInstallLanguage

- ea: `0x180345ad0`
- end: `0x180345bf1`
- name: `GetInstallLanguage`
- size: `289`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1803461f8`

## callees

- `0x1801cb20e`
- `0x180345ad0`
- `0x1803481f0`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180345b7d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180345b7d`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180345b30`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180345b30`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180345b6a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180345b6a`

## string_xrefs

- `0x180345b22`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_180443AD4;
  hKey = 0;
  if ( !word_180443AD4 )
  {
    cbData = 6;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Active Setup\\Installed Components\\{89820200-ECBD-11CF-8B85-00AA005B4383}",
            0,
            1u,
            &hKey) )
    {
      v1 = RegQueryValueExW(hKey, L"Locale", 0, 0, (LPBYTE)&Data, &cbData);
      RegCloseKey(hKey);
      if ( !v1 )
      {
        while ( v1 < 0x1C )
        {
          if ( !wcsnicmp_0(&Data, (&off_1803A6C10)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_1803A6C10 + 8 * (int)v1 + 4);
            word_180443AD4 = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_180443AD4;
  }
  return v0;
}

```

## disassembly

```asm
0x180345ad0  mov     r11, rsp
0x180345ad3  mov     [r11+8], rbx
0x180345ad7  mov     [r11+10h], rsi
0x180345adb  push    rdi
0x180345adc  sub     rsp, 50h
0x180345ae0  mov     rax, cs:__security_cookie
0x180345ae7  xor     rax, rsp
0x180345aea  mov     [rsp+58h+var_10], rax
0x180345aef  movzx   ecx, cs:word_180443AD4
0x180345af6  xor     eax, eax
0x180345af8  mov     qword ptr [r11-20h], 0
0x180345b00  cmp     ax, cx
0x180345b03  jnz     loc_180345BD0
0x180345b09  lea     rax, [r11-20h]
0x180345b0d  mov     [rsp+58h+cbData], 6
0x180345b15  mov     r9d, 1; samDesired
0x180345b1b  mov     [r11-38h], rax
0x180345b1f  xor     r8d, r8d; ulOptions
0x180345b22  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Active Setup\\Inst"...
0x180345b29  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180345b30  call    cs:__imp_RegOpenKeyExW
0x180345b37  nop     dword ptr [rax+rax+00h]
0x180345b3c  test    eax, eax
0x180345b3e  jnz     loc_180345BC9
0x180345b44  mov     rcx, [rsp+58h+hKey]; hKey
0x180345b49  lea     rax, [rsp+58h+cbData]
0x180345b4e  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180345b53  lea     rdx, aLocale; "Locale"
0x180345b5a  lea     rax, [rsp+58h+Data]
0x180345b5f  xor     r9d, r9d; lpType
0x180345b62  xor     r8d, r8d; lpReserved
0x180345b65  mov     [rsp+58h+lpData], rax; lpData
0x180345b6a  call    cs:__imp_RegQueryValueExW
0x180345b71  nop     dword ptr [rax+rax+00h]
0x180345b76  mov     rcx, [rsp+58h+hKey]; hKey
0x180345b7b  mov     ebx, eax
0x180345b7d  call    cs:__imp_RegCloseKey
0x180345b84  nop     dword ptr [rax+rax+00h]
0x180345b89  test    ebx, ebx
0x180345b8b  jnz     short loc_180345BC9
0x180345b8d  lea     rsi, off_1803A6C10; "EN"
0x180345b94  cmp     ebx, 1Ch
0x180345b97  jnb     short loc_180345BC9
0x180345b99  movsxd  rdi, ebx
0x180345b9c  lea     rcx, [rsp+58h+Data]; String1
0x180345ba1  add     rdi, rdi
0x180345ba4  mov     r8d, 3; MaxCount
0x180345baa  mov     rdx, [rsi+rdi*8]; String2
0x180345bae  call    _wcsnicmp_0
0x180345bb3  test    eax, eax
0x180345bb5  jz      short loc_180345BBB
0x180345bb7  inc     ebx
0x180345bb9  jmp     short loc_180345B94
0x180345bbb  movzx   ecx, word ptr [rsi+rdi*8+8]
0x180345bc0  mov     cs:word_180443AD4, cx
0x180345bc7  jmp     short loc_180345BD0
0x180345bc9  movzx   ecx, cs:word_180443AD4
0x180345bd0  movzx   eax, cx
0x180345bd3  mov     rcx, [rsp+58h+var_10]
0x180345bd8  xor     rcx, rsp; StackCookie
0x180345bdb  call    __security_check_cookie
0x180345be0  mov     rbx, [rsp+58h+arg_0]
0x180345be5  mov     rsi, [rsp+58h+arg_8]
0x180345bea  add     rsp, 50h
0x180345bee  pop     rdi
0x180345bef  retn
```
