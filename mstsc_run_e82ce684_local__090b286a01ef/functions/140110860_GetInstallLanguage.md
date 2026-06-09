# GetInstallLanguage

- ea: `0x140110860`
- end: `0x14011096a`
- name: `GetInstallLanguage`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140110ec0`

## callees

- `0x1400043ac`
- `0x140110860`
- `0x140113390`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1401108c0`
- `ADVAPI32!RegOpenKeyExW` at `0x1401108c0`
- `ADVAPI32!RegCloseKey` at `0x1401108fd`
- `ADVAPI32!RegCloseKey` at `0x1401108fd`
- `ADVAPI32!RegQueryValueExW` at `0x1401108f0`
- `ADVAPI32!RegQueryValueExW` at `0x1401108f0`

## string_xrefs

- `0x1401108b2`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_140154928;
  hKey = 0;
  if ( !word_140154928 )
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
          if ( !wcsnicmp_0(&Data, (&off_14011D3F0)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_14011D3F0 + 8 * (int)v1 + 4);
            word_140154928 = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_140154928;
  }
  return v0;
}

```

## disassembly

```asm
0x140110860  mov     r11, rsp
0x140110863  mov     [r11+8], rbx
0x140110867  mov     [r11+10h], rsi
0x14011086b  push    rdi
0x14011086c  sub     rsp, 50h
0x140110870  mov     rax, cs:__security_cookie
0x140110877  xor     rax, rsp
0x14011087a  mov     [rsp+58h+var_10], rax
0x14011087f  movzx   ecx, cs:word_140154928
0x140110886  xor     eax, eax
0x140110888  mov     qword ptr [r11-20h], 0
0x140110890  cmp     ax, cx
0x140110893  jnz     loc_14011094A
0x140110899  lea     rax, [r11-20h]
0x14011089d  mov     [rsp+58h+cbData], 6
0x1401108a5  mov     r9d, 1; samDesired
0x1401108ab  mov     [r11-38h], rax
0x1401108af  xor     r8d, r8d; ulOptions
0x1401108b2  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Active Setup\\Inst"...
0x1401108b9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1401108c0  call    cs:__imp_RegOpenKeyExW
0x1401108c6  test    eax, eax
0x1401108c8  jnz     short loc_140110943
0x1401108ca  mov     rcx, [rsp+58h+hKey]; hKey
0x1401108cf  lea     rax, [rsp+58h+cbData]
0x1401108d4  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1401108d9  lea     rdx, aLocale; "Locale"
0x1401108e0  lea     rax, [rsp+58h+Data]
0x1401108e5  xor     r9d, r9d; lpType
0x1401108e8  xor     r8d, r8d; lpReserved
0x1401108eb  mov     [rsp+58h+lpData], rax; lpData
0x1401108f0  call    cs:__imp_RegQueryValueExW
0x1401108f6  mov     rcx, [rsp+58h+hKey]; hKey
0x1401108fb  mov     ebx, eax
0x1401108fd  call    cs:__imp_RegCloseKey
0x140110903  test    ebx, ebx
0x140110905  jnz     short loc_140110943
0x140110907  lea     rsi, off_14011D3F0; "EN"
0x14011090e  cmp     ebx, 1Ch
0x140110911  jnb     short loc_140110943
0x140110913  movsxd  rdi, ebx
0x140110916  lea     rcx, [rsp+58h+Data]; String1
0x14011091b  add     rdi, rdi
0x14011091e  mov     r8d, 3; MaxCount
0x140110924  mov     rdx, [rsi+rdi*8]; String2
0x140110928  call    _wcsnicmp_0
0x14011092d  test    eax, eax
0x14011092f  jz      short loc_140110935
0x140110931  inc     ebx
0x140110933  jmp     short loc_14011090E
0x140110935  movzx   ecx, word ptr [rsi+rdi*8+8]
0x14011093a  mov     cs:word_140154928, cx
0x140110941  jmp     short loc_14011094A
0x140110943  movzx   ecx, cs:word_140154928
0x14011094a  movzx   eax, cx
0x14011094d  mov     rcx, [rsp+58h+var_10]
0x140110952  xor     rcx, rsp; StackCookie
0x140110955  call    __security_check_cookie
0x14011095a  mov     rbx, [rsp+58h+arg_0]
0x14011095f  mov     rsi, [rsp+58h+arg_8]
0x140110964  add     rsp, 50h
0x140110968  pop     rdi
0x140110969  retn
```
