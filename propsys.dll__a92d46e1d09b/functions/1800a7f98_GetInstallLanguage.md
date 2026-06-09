# GetInstallLanguage

- ea: `0x1800a7f98`
- end: `0x1800a80a2`
- name: `GetInstallLanguage`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005a1cc`

## callees

- `0x18006ed20`
- `0x18006fb50`
- `0x1800a7f98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a7ff8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a7ff8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a8028`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a8028`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a8035`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a8035`

## string_xrefs

- `0x1800a7fea`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_1800F1910;
  hKey = 0;
  if ( !word_1800F1910 )
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
          if ( !wcsnicmp(&Data, (&off_1800BE8B0)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_1800BE8B0 + 8 * (int)v1 + 4);
            word_1800F1910 = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_1800F1910;
  }
  return v0;
}

```

## disassembly

```asm
0x1800a7f98  mov     r11, rsp
0x1800a7f9b  mov     [r11+8], rbx
0x1800a7f9f  mov     [r11+10h], rsi
0x1800a7fa3  push    rdi
0x1800a7fa4  sub     rsp, 50h
0x1800a7fa8  mov     rax, cs:__security_cookie
0x1800a7faf  xor     rax, rsp
0x1800a7fb2  mov     [rsp+58h+var_10], rax
0x1800a7fb7  movzx   ecx, cs:word_1800F1910
0x1800a7fbe  xor     eax, eax
0x1800a7fc0  mov     qword ptr [r11-20h], 0
0x1800a7fc8  cmp     ax, cx
0x1800a7fcb  jnz     loc_1800A8082
0x1800a7fd1  lea     rax, [r11-20h]
0x1800a7fd5  mov     [rsp+58h+cbData], 6
0x1800a7fdd  mov     r9d, 1; samDesired
0x1800a7fe3  mov     [r11-38h], rax
0x1800a7fe7  xor     r8d, r8d; ulOptions
0x1800a7fea  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Active Setup\\Inst"...
0x1800a7ff1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a7ff8  call    cs:__imp_RegOpenKeyExW
0x1800a7ffe  test    eax, eax
0x1800a8000  jnz     short loc_1800A807B
0x1800a8002  mov     rcx, [rsp+58h+hKey]; hKey
0x1800a8007  lea     rax, [rsp+58h+cbData]
0x1800a800c  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800a8011  lea     rdx, ValueName; "Locale"
0x1800a8018  lea     rax, [rsp+58h+Data]
0x1800a801d  xor     r9d, r9d; lpType
0x1800a8020  xor     r8d, r8d; lpReserved
0x1800a8023  mov     [rsp+58h+lpData], rax; lpData
0x1800a8028  call    cs:__imp_RegQueryValueExW
0x1800a802e  mov     rcx, [rsp+58h+hKey]; hKey
0x1800a8033  mov     ebx, eax
0x1800a8035  call    cs:__imp_RegCloseKey
0x1800a803b  test    ebx, ebx
0x1800a803d  jnz     short loc_1800A807B
0x1800a803f  lea     rsi, off_1800BE8B0; "EN"
0x1800a8046  cmp     ebx, 1Ch
0x1800a8049  jnb     short loc_1800A807B
0x1800a804b  movsxd  rdi, ebx
0x1800a804e  lea     rcx, [rsp+58h+Data]; String1
0x1800a8053  add     rdi, rdi
0x1800a8056  mov     r8d, 3; MaxCount
0x1800a805c  mov     rdx, [rsi+rdi*8]; String2
0x1800a8060  call    _wcsnicmp
0x1800a8065  test    eax, eax
0x1800a8067  jz      short loc_1800A806D
0x1800a8069  inc     ebx
0x1800a806b  jmp     short loc_1800A8046
0x1800a806d  movzx   ecx, word ptr [rsi+rdi*8+8]
0x1800a8072  mov     cs:word_1800F1910, cx
0x1800a8079  jmp     short loc_1800A8082
0x1800a807b  movzx   ecx, cs:word_1800F1910
0x1800a8082  movzx   eax, cx
0x1800a8085  mov     rcx, [rsp+58h+var_10]
0x1800a808a  xor     rcx, rsp; StackCookie
0x1800a808d  call    __security_check_cookie
0x1800a8092  mov     rbx, [rsp+58h+arg_0]
0x1800a8097  mov     rsi, [rsp+58h+arg_8]
0x1800a809c  add     rsp, 50h
0x1800a80a0  pop     rdi
0x1800a80a1  retn
```
