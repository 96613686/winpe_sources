# GetInstallLanguage

- ea: `0x180091f6c`
- end: `0x180092076`
- name: `GetInstallLanguage`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800925d0`

## callees

- `0x180058317`
- `0x180091f6c`
- `0x1800942d0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180092009`
- `ADVAPI32!RegCloseKey` at `0x180092009`
- `ADVAPI32!RegQueryValueExW` at `0x180091ffc`
- `ADVAPI32!RegQueryValueExW` at `0x180091ffc`
- `ADVAPI32!RegOpenKeyExW` at `0x180091fcc`
- `ADVAPI32!RegOpenKeyExW` at `0x180091fcc`

## string_xrefs

- `0x180091fbe`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_1800B6F98;
  hKey = 0;
  if ( !word_1800B6F98 )
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
          if ( !wcsnicmp_0(&Data, (&off_18009E1F0)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_18009E1F0 + 8 * (int)v1 + 4);
            word_1800B6F98 = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_1800B6F98;
  }
  return v0;
}

```

## disassembly

```asm
0x180091f6c  mov     r11, rsp
0x180091f6f  mov     [r11+8], rbx
0x180091f73  mov     [r11+10h], rsi
0x180091f77  push    rdi
0x180091f78  sub     rsp, 50h
0x180091f7c  mov     rax, cs:__security_cookie
0x180091f83  xor     rax, rsp
0x180091f86  mov     [rsp+58h+var_10], rax
0x180091f8b  movzx   ecx, cs:word_1800B6F98
0x180091f92  xor     eax, eax
0x180091f94  mov     qword ptr [r11-20h], 0
0x180091f9c  cmp     ax, cx
0x180091f9f  jnz     loc_180092056
0x180091fa5  lea     rax, [r11-20h]
0x180091fa9  mov     [rsp+58h+cbData], 6
0x180091fb1  mov     r9d, 1; samDesired
0x180091fb7  mov     [r11-38h], rax
0x180091fbb  xor     r8d, r8d; ulOptions
0x180091fbe  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Active Setup\\Inst"...
0x180091fc5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180091fcc  call    cs:__imp_RegOpenKeyExW
0x180091fd2  test    eax, eax
0x180091fd4  jnz     short loc_18009204F
0x180091fd6  mov     rcx, [rsp+58h+hKey]; hKey
0x180091fdb  lea     rax, [rsp+58h+cbData]
0x180091fe0  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180091fe5  lea     rdx, aLocale; "Locale"
0x180091fec  lea     rax, [rsp+58h+Data]
0x180091ff1  xor     r9d, r9d; lpType
0x180091ff4  xor     r8d, r8d; lpReserved
0x180091ff7  mov     [rsp+58h+lpData], rax; lpData
0x180091ffc  call    cs:__imp_RegQueryValueExW
0x180092002  mov     rcx, [rsp+58h+hKey]; hKey
0x180092007  mov     ebx, eax
0x180092009  call    cs:__imp_RegCloseKey
0x18009200f  test    ebx, ebx
0x180092011  jnz     short loc_18009204F
0x180092013  lea     rsi, off_18009E1F0; "EN"
0x18009201a  cmp     ebx, 1Ch
0x18009201d  jnb     short loc_18009204F
0x18009201f  movsxd  rdi, ebx
0x180092022  lea     rcx, [rsp+58h+Data]; String1
0x180092027  add     rdi, rdi
0x18009202a  mov     r8d, 3; MaxCount
0x180092030  mov     rdx, [rsi+rdi*8]; String2
0x180092034  call    _wcsnicmp_0
0x180092039  test    eax, eax
0x18009203b  jz      short loc_180092041
0x18009203d  inc     ebx
0x18009203f  jmp     short loc_18009201A
0x180092041  movzx   ecx, word ptr [rsi+rdi*8+8]
0x180092046  mov     cs:word_1800B6F98, cx
0x18009204d  jmp     short loc_180092056
0x18009204f  movzx   ecx, cs:word_1800B6F98
0x180092056  movzx   eax, cx
0x180092059  mov     rcx, [rsp+58h+var_10]
0x18009205e  xor     rcx, rsp; StackCookie
0x180092061  call    __security_check_cookie
0x180092066  mov     rbx, [rsp+58h+arg_0]
0x18009206b  mov     rsi, [rsp+58h+arg_8]
0x180092070  add     rsp, 50h
0x180092074  pop     rdi
0x180092075  retn
```
