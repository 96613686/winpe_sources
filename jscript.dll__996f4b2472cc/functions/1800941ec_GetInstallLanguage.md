# GetInstallLanguage

- ea: `0x1800941ec`
- end: `0x18009430d`
- name: `GetInstallLanguage`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800948cc`

## callees

- `0x180059267`
- `0x1800941ec`
- `0x1800966e0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180094299`
- `ADVAPI32!RegCloseKey` at `0x180094299`
- `ADVAPI32!RegQueryValueExW` at `0x180094286`
- `ADVAPI32!RegQueryValueExW` at `0x180094286`
- `ADVAPI32!RegOpenKeyExW` at `0x18009424c`
- `ADVAPI32!RegOpenKeyExW` at `0x18009424c`

## string_xrefs

- `0x18009423e`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_1800B8F98;
  hKey = 0;
  if ( !word_1800B8F98 )
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
          if ( !wcsnicmp_0(&Data, (&off_1800A01E0)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_1800A01E0 + 8 * (int)v1 + 4);
            word_1800B8F98 = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_1800B8F98;
  }
  return v0;
}

```

## disassembly

```asm
0x1800941ec  mov     r11, rsp
0x1800941ef  mov     [r11+8], rbx
0x1800941f3  mov     [r11+10h], rsi
0x1800941f7  push    rdi
0x1800941f8  sub     rsp, 50h
0x1800941fc  mov     rax, cs:__security_cookie
0x180094203  xor     rax, rsp
0x180094206  mov     [rsp+58h+var_10], rax
0x18009420b  movzx   ecx, cs:word_1800B8F98
0x180094212  xor     eax, eax
0x180094214  mov     qword ptr [r11-20h], 0
0x18009421c  cmp     ax, cx
0x18009421f  jnz     loc_1800942EC
0x180094225  lea     rax, [r11-20h]
0x180094229  mov     [rsp+58h+cbData], 6
0x180094231  mov     r9d, 1; samDesired
0x180094237  mov     [r11-38h], rax
0x18009423b  xor     r8d, r8d; ulOptions
0x18009423e  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Active Setup\\Inst"...
0x180094245  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009424c  call    cs:__imp_RegOpenKeyExW
0x180094253  nop     dword ptr [rax+rax+00h]
0x180094258  test    eax, eax
0x18009425a  jnz     loc_1800942E5
0x180094260  mov     rcx, [rsp+58h+hKey]; hKey
0x180094265  lea     rax, [rsp+58h+cbData]
0x18009426a  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18009426f  lea     rdx, aLocale; "Locale"
0x180094276  lea     rax, [rsp+58h+Data]
0x18009427b  xor     r9d, r9d; lpType
0x18009427e  xor     r8d, r8d; lpReserved
0x180094281  mov     [rsp+58h+lpData], rax; lpData
0x180094286  call    cs:__imp_RegQueryValueExW
0x18009428d  nop     dword ptr [rax+rax+00h]
0x180094292  mov     rcx, [rsp+58h+hKey]; hKey
0x180094297  mov     ebx, eax
0x180094299  call    cs:__imp_RegCloseKey
0x1800942a0  nop     dword ptr [rax+rax+00h]
0x1800942a5  test    ebx, ebx
0x1800942a7  jnz     short loc_1800942E5
0x1800942a9  lea     rsi, off_1800A01E0; "EN"
0x1800942b0  cmp     ebx, 1Ch
0x1800942b3  jnb     short loc_1800942E5
0x1800942b5  movsxd  rdi, ebx
0x1800942b8  lea     rcx, [rsp+58h+Data]; String1
0x1800942bd  add     rdi, rdi
0x1800942c0  mov     r8d, 3; MaxCount
0x1800942c6  mov     rdx, [rsi+rdi*8]; String2
0x1800942ca  call    _wcsnicmp_0
0x1800942cf  test    eax, eax
0x1800942d1  jz      short loc_1800942D7
0x1800942d3  inc     ebx
0x1800942d5  jmp     short loc_1800942B0
0x1800942d7  movzx   ecx, word ptr [rsi+rdi*8+8]
0x1800942dc  mov     cs:word_1800B8F98, cx
0x1800942e3  jmp     short loc_1800942EC
0x1800942e5  movzx   ecx, cs:word_1800B8F98
0x1800942ec  movzx   eax, cx
0x1800942ef  mov     rcx, [rsp+58h+var_10]
0x1800942f4  xor     rcx, rsp; StackCookie
0x1800942f7  call    __security_check_cookie
0x1800942fc  mov     rbx, [rsp+58h+arg_0]
0x180094301  mov     rsi, [rsp+58h+arg_8]
0x180094306  add     rsp, 50h
0x18009430a  pop     rdi
0x18009430b  retn
```
