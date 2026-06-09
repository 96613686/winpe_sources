# GetInstallLanguage

- ea: `0x14010e6f0`
- end: `0x14010e7fa`
- name: `GetInstallLanguage`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14010ed50`

## callees

- `0x1400043ac`
- `0x14010e6f0`
- `0x140111220`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14010e750`
- `ADVAPI32!RegOpenKeyExW` at `0x14010e750`
- `ADVAPI32!RegCloseKey` at `0x14010e78d`
- `ADVAPI32!RegCloseKey` at `0x14010e78d`
- `ADVAPI32!RegQueryValueExW` at `0x14010e780`
- `ADVAPI32!RegQueryValueExW` at `0x14010e780`

## string_xrefs

- `0x14010e742`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_1401527F8;
  hKey = 0;
  if ( !word_1401527F8 )
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
          if ( !wcsnicmp_0(&Data, (&off_14011B3F0)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_14011B3F0 + 8 * (int)v1 + 4);
            word_1401527F8 = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_1401527F8;
  }
  return v0;
}

```

## disassembly

```asm
0x14010e6f0  mov     r11, rsp
0x14010e6f3  mov     [r11+8], rbx
0x14010e6f7  mov     [r11+10h], rsi
0x14010e6fb  push    rdi
0x14010e6fc  sub     rsp, 50h
0x14010e700  mov     rax, cs:__security_cookie
0x14010e707  xor     rax, rsp
0x14010e70a  mov     [rsp+58h+var_10], rax
0x14010e70f  movzx   ecx, cs:word_1401527F8
0x14010e716  xor     eax, eax
0x14010e718  mov     qword ptr [r11-20h], 0
0x14010e720  cmp     ax, cx
0x14010e723  jnz     loc_14010E7DA
0x14010e729  lea     rax, [r11-20h]
0x14010e72d  mov     [rsp+58h+cbData], 6
0x14010e735  mov     r9d, 1; samDesired
0x14010e73b  mov     [r11-38h], rax
0x14010e73f  xor     r8d, r8d; ulOptions
0x14010e742  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Active Setup\\Inst"...
0x14010e749  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14010e750  call    cs:__imp_RegOpenKeyExW
0x14010e756  test    eax, eax
0x14010e758  jnz     short loc_14010E7D3
0x14010e75a  mov     rcx, [rsp+58h+hKey]; hKey
0x14010e75f  lea     rax, [rsp+58h+cbData]
0x14010e764  mov     [rsp+58h+lpcbData], rax; lpcbData
0x14010e769  lea     rdx, aLocale; "Locale"
0x14010e770  lea     rax, [rsp+58h+Data]
0x14010e775  xor     r9d, r9d; lpType
0x14010e778  xor     r8d, r8d; lpReserved
0x14010e77b  mov     [rsp+58h+lpData], rax; lpData
0x14010e780  call    cs:__imp_RegQueryValueExW
0x14010e786  mov     rcx, [rsp+58h+hKey]; hKey
0x14010e78b  mov     ebx, eax
0x14010e78d  call    cs:__imp_RegCloseKey
0x14010e793  test    ebx, ebx
0x14010e795  jnz     short loc_14010E7D3
0x14010e797  lea     rsi, off_14011B3F0; "EN"
0x14010e79e  cmp     ebx, 1Ch
0x14010e7a1  jnb     short loc_14010E7D3
0x14010e7a3  movsxd  rdi, ebx
0x14010e7a6  lea     rcx, [rsp+58h+Data]; String1
0x14010e7ab  add     rdi, rdi
0x14010e7ae  mov     r8d, 3; MaxCount
0x14010e7b4  mov     rdx, [rsi+rdi*8]; String2
0x14010e7b8  call    _wcsnicmp_0
0x14010e7bd  test    eax, eax
0x14010e7bf  jz      short loc_14010E7C5
0x14010e7c1  inc     ebx
0x14010e7c3  jmp     short loc_14010E79E
0x14010e7c5  movzx   ecx, word ptr [rsi+rdi*8+8]
0x14010e7ca  mov     cs:word_1401527F8, cx
0x14010e7d1  jmp     short loc_14010E7DA
0x14010e7d3  movzx   ecx, cs:word_1401527F8
0x14010e7da  movzx   eax, cx
0x14010e7dd  mov     rcx, [rsp+58h+var_10]
0x14010e7e2  xor     rcx, rsp; StackCookie
0x14010e7e5  call    __security_check_cookie
0x14010e7ea  mov     rbx, [rsp+58h+arg_0]
0x14010e7ef  mov     rsi, [rsp+58h+arg_8]
0x14010e7f4  add     rsp, 50h
0x14010e7f8  pop     rdi
0x14010e7f9  retn
```
