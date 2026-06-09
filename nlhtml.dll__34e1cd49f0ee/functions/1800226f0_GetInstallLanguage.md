# GetInstallLanguage

- ea: `0x1800226f0`
- end: `0x1800227fa`
- name: `GetInstallLanguage`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180022d54`

## callees

- `0x180014130`
- `0x180014f90`
- `0x1800226f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022780`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022780`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002278d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002278d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022750`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022750`

## string_xrefs

- `0x180022742`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_18003E3C4;
  hKey = 0;
  if ( !word_18003E3C4 )
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
          if ( !wcsnicmp(&Data, (&off_18002B2F0)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_18002B2F0 + 8 * (int)v1 + 4);
            word_18003E3C4 = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_18003E3C4;
  }
  return v0;
}

```

## disassembly

```asm
0x1800226f0  mov     r11, rsp
0x1800226f3  mov     [r11+8], rbx
0x1800226f7  mov     [r11+10h], rsi
0x1800226fb  push    rdi
0x1800226fc  sub     rsp, 50h
0x180022700  mov     rax, cs:__security_cookie
0x180022707  xor     rax, rsp
0x18002270a  mov     [rsp+58h+var_10], rax
0x18002270f  movzx   ecx, cs:word_18003E3C4
0x180022716  xor     eax, eax
0x180022718  mov     qword ptr [r11-20h], 0
0x180022720  cmp     ax, cx
0x180022723  jnz     loc_1800227DA
0x180022729  lea     rax, [r11-20h]
0x18002272d  mov     [rsp+58h+cbData], 6
0x180022735  mov     r9d, 1; samDesired
0x18002273b  mov     [r11-38h], rax
0x18002273f  xor     r8d, r8d; ulOptions
0x180022742  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Active Setup\\Inst"...
0x180022749  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022750  call    cs:__imp_RegOpenKeyExW
0x180022756  test    eax, eax
0x180022758  jnz     short loc_1800227D3
0x18002275a  mov     rcx, [rsp+58h+hKey]; hKey
0x18002275f  lea     rax, [rsp+58h+cbData]
0x180022764  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180022769  lea     rdx, aLocale; "Locale"
0x180022770  lea     rax, [rsp+58h+Data]
0x180022775  xor     r9d, r9d; lpType
0x180022778  xor     r8d, r8d; lpReserved
0x18002277b  mov     [rsp+58h+lpData], rax; lpData
0x180022780  call    cs:__imp_RegQueryValueExW
0x180022786  mov     rcx, [rsp+58h+hKey]; hKey
0x18002278b  mov     ebx, eax
0x18002278d  call    cs:__imp_RegCloseKey
0x180022793  test    ebx, ebx
0x180022795  jnz     short loc_1800227D3
0x180022797  lea     rsi, off_18002B2F0; "EN"
0x18002279e  cmp     ebx, 1Ch
0x1800227a1  jnb     short loc_1800227D3
0x1800227a3  movsxd  rdi, ebx
0x1800227a6  lea     rcx, [rsp+58h+Data]; String1
0x1800227ab  add     rdi, rdi
0x1800227ae  mov     r8d, 3; MaxCount
0x1800227b4  mov     rdx, [rsi+rdi*8]; String2
0x1800227b8  call    _wcsnicmp
0x1800227bd  test    eax, eax
0x1800227bf  jz      short loc_1800227C5
0x1800227c1  inc     ebx
0x1800227c3  jmp     short loc_18002279E
0x1800227c5  movzx   ecx, word ptr [rsi+rdi*8+8]
0x1800227ca  mov     cs:word_18003E3C4, cx
0x1800227d1  jmp     short loc_1800227DA
0x1800227d3  movzx   ecx, cs:word_18003E3C4
0x1800227da  movzx   eax, cx
0x1800227dd  mov     rcx, [rsp+58h+var_10]
0x1800227e2  xor     rcx, rsp; StackCookie
0x1800227e5  call    __security_check_cookie
0x1800227ea  mov     rbx, [rsp+58h+arg_0]
0x1800227ef  mov     rsi, [rsp+58h+arg_8]
0x1800227f4  add     rsp, 50h
0x1800227f8  pop     rdi
0x1800227f9  retn
```
