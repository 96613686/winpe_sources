# GetInstallLanguage

- ea: `0x180037590`
- end: `0x18003769b`
- name: `GetInstallLanguage`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180037bf8`

## callees

- `0x180037590`
- `0x1800382c0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180037658`
- `msvcrt!_wcsnicmp` at `0x180037658`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003762d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003762d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037620`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037620`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800375f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800375f0`

## string_xrefs

- `0x1800375e2`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_1800C4F50;
  hKey = 0;
  if ( !word_1800C4F50 )
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
          if ( !_wcsnicmp(&Data, (&off_180060480)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_180060480 + 8 * (int)v1 + 4);
            word_1800C4F50 = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_1800C4F50;
  }
  return v0;
}

```

## disassembly

```asm
0x180037590  mov     r11, rsp
0x180037593  mov     [r11+8], rbx
0x180037597  mov     [r11+10h], rsi
0x18003759b  push    rdi
0x18003759c  sub     rsp, 50h
0x1800375a0  mov     rax, cs:__security_cookie
0x1800375a7  xor     rax, rsp
0x1800375aa  mov     [rsp+58h+var_10], rax
0x1800375af  movzx   ecx, cs:word_1800C4F50
0x1800375b6  xor     eax, eax
0x1800375b8  mov     qword ptr [r11-20h], 0
0x1800375c0  cmp     ax, cx
0x1800375c3  jnz     loc_18003767B
0x1800375c9  lea     rax, [r11-20h]
0x1800375cd  mov     [rsp+58h+cbData], 6
0x1800375d5  mov     r9d, 1; samDesired
0x1800375db  mov     [r11-38h], rax
0x1800375df  xor     r8d, r8d; ulOptions
0x1800375e2  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Active Setup\\Inst"...
0x1800375e9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800375f0  call    cs:__imp_RegOpenKeyExW
0x1800375f6  test    eax, eax
0x1800375f8  jnz     short loc_180037674
0x1800375fa  mov     rcx, [rsp+58h+hKey]; hKey
0x1800375ff  lea     rax, [rsp+58h+cbData]
0x180037604  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180037609  lea     rdx, aLocale; "Locale"
0x180037610  lea     rax, [rsp+58h+Data]
0x180037615  xor     r9d, r9d; lpType
0x180037618  xor     r8d, r8d; lpReserved
0x18003761b  mov     [rsp+58h+lpData], rax; lpData
0x180037620  call    cs:__imp_RegQueryValueExW
0x180037626  mov     rcx, [rsp+58h+hKey]; hKey
0x18003762b  mov     ebx, eax
0x18003762d  call    cs:__imp_RegCloseKey
0x180037633  test    ebx, ebx
0x180037635  jnz     short loc_180037674
0x180037637  lea     rsi, off_180060480; "EN"
0x18003763e  cmp     ebx, 1Ch
0x180037641  jnb     short loc_180037674
0x180037643  movsxd  rdi, ebx
0x180037646  lea     rcx, [rsp+58h+Data]; String1
0x18003764b  add     rdi, rdi
0x18003764e  mov     r8d, 3; MaxCount
0x180037654  mov     rdx, [rsi+rdi*8]; String2
0x180037658  call    cs:__imp__wcsnicmp
0x18003765e  test    eax, eax
0x180037660  jz      short loc_180037666
0x180037662  inc     ebx
0x180037664  jmp     short loc_18003763E
0x180037666  movzx   ecx, word ptr [rsi+rdi*8+8]
0x18003766b  mov     cs:word_1800C4F50, cx
0x180037672  jmp     short loc_18003767B
0x180037674  movzx   ecx, cs:word_1800C4F50
0x18003767b  movzx   eax, cx
0x18003767e  mov     rcx, [rsp+58h+var_10]
0x180037683  xor     rcx, rsp; StackCookie
0x180037686  call    __security_check_cookie
0x18003768b  mov     rbx, [rsp+58h+arg_0]
0x180037690  mov     rsi, [rsp+58h+arg_8]
0x180037695  add     rsp, 50h
0x180037699  pop     rdi
0x18003769a  retn
```
