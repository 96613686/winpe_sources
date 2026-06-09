# GetInstallLanguage

- ea: `0x1800386ec`
- end: `0x1800387f6`
- name: `GetInstallLanguage`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180038d50`

## callees

- `0x18000228a`
- `0x1800386ec`
- `0x180039740`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003874c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003874c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003877c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003877c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038789`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038789`

## string_xrefs

- `0x18003873e`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_18006B1A0;
  hKey = 0;
  if ( !word_18006B1A0 )
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
          if ( !wcsnicmp_0(&Data, (&off_18004DE80)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_18004DE80 + 8 * (int)v1 + 4);
            word_18006B1A0 = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_18006B1A0;
  }
  return v0;
}

```

## disassembly

```asm
0x1800386ec  mov     r11, rsp
0x1800386ef  mov     [r11+8], rbx
0x1800386f3  mov     [r11+10h], rsi
0x1800386f7  push    rdi
0x1800386f8  sub     rsp, 50h
0x1800386fc  mov     rax, cs:__security_cookie
0x180038703  xor     rax, rsp
0x180038706  mov     [rsp+58h+var_10], rax
0x18003870b  movzx   ecx, cs:word_18006B1A0
0x180038712  xor     eax, eax
0x180038714  mov     qword ptr [r11-20h], 0
0x18003871c  cmp     ax, cx
0x18003871f  jnz     loc_1800387D6
0x180038725  lea     rax, [r11-20h]
0x180038729  mov     [rsp+58h+cbData], 6
0x180038731  mov     r9d, 1; samDesired
0x180038737  mov     [r11-38h], rax
0x18003873b  xor     r8d, r8d; ulOptions
0x18003873e  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Active Setup\\Inst"...
0x180038745  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003874c  call    cs:__imp_RegOpenKeyExW
0x180038752  test    eax, eax
0x180038754  jnz     short loc_1800387CF
0x180038756  mov     rcx, [rsp+58h+hKey]; hKey
0x18003875b  lea     rax, [rsp+58h+cbData]
0x180038760  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180038765  lea     rdx, aLocale; "Locale"
0x18003876c  lea     rax, [rsp+58h+Data]
0x180038771  xor     r9d, r9d; lpType
0x180038774  xor     r8d, r8d; lpReserved
0x180038777  mov     [rsp+58h+lpData], rax; lpData
0x18003877c  call    cs:__imp_RegQueryValueExW
0x180038782  mov     rcx, [rsp+58h+hKey]; hKey
0x180038787  mov     ebx, eax
0x180038789  call    cs:__imp_RegCloseKey
0x18003878f  test    ebx, ebx
0x180038791  jnz     short loc_1800387CF
0x180038793  lea     rsi, off_18004DE80; "EN"
0x18003879a  cmp     ebx, 1Ch
0x18003879d  jnb     short loc_1800387CF
0x18003879f  movsxd  rdi, ebx
0x1800387a2  lea     rcx, [rsp+58h+Data]; String1
0x1800387a7  add     rdi, rdi
0x1800387aa  mov     r8d, 3; MaxCount
0x1800387b0  mov     rdx, [rsi+rdi*8]; String2
0x1800387b4  call    _wcsnicmp_0
0x1800387b9  test    eax, eax
0x1800387bb  jz      short loc_1800387C1
0x1800387bd  inc     ebx
0x1800387bf  jmp     short loc_18003879A
0x1800387c1  movzx   ecx, word ptr [rsi+rdi*8+8]
0x1800387c6  mov     cs:word_18006B1A0, cx
0x1800387cd  jmp     short loc_1800387D6
0x1800387cf  movzx   ecx, cs:word_18006B1A0
0x1800387d6  movzx   eax, cx
0x1800387d9  mov     rcx, [rsp+58h+var_10]
0x1800387de  xor     rcx, rsp; StackCookie
0x1800387e1  call    __security_check_cookie
0x1800387e6  mov     rbx, [rsp+58h+arg_0]
0x1800387eb  mov     rsi, [rsp+58h+arg_8]
0x1800387f0  add     rsp, 50h
0x1800387f4  pop     rdi
0x1800387f5  retn
```
