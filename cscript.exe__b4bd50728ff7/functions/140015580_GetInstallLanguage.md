# GetInstallLanguage

- ea: `0x140015580`
- end: `0x14001568b`
- name: `GetInstallLanguage`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140015be8`

## callees

- `0x140015580`
- `0x1400161d0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x140015648`
- `msvcrt!_wcsnicmp` at `0x140015648`
- `ADVAPI32!RegQueryValueExW` at `0x140015610`
- `ADVAPI32!RegQueryValueExW` at `0x140015610`
- `ADVAPI32!RegOpenKeyExW` at `0x1400155e0`
- `ADVAPI32!RegOpenKeyExW` at `0x1400155e0`
- `ADVAPI32!RegCloseKey` at `0x14001561d`
- `ADVAPI32!RegCloseKey` at `0x14001561d`

## string_xrefs

- `0x1400155d2`: `Software\Microsoft\Active Setup\Installed Components\{89820200-ECBD-11CF-8B85-00AA005B4383}`

## pseudocode

```c
__int64 GetInstallLanguage()
{
  unsigned __int16 v0; // cx
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wchar_t Data; // [rsp+40h] [rbp-18h] BYREF

  v0 = word_14001EA4C;
  hKey = 0;
  if ( !word_14001EA4C )
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
          if ( !_wcsnicmp(&Data, (&off_140018AF0)[2 * (int)v1], 3u) )
          {
            v0 = *((_WORD *)&off_140018AF0 + 8 * (int)v1 + 4);
            word_14001EA4C = v0;
            return v0;
          }
          ++v1;
        }
      }
    }
    return (unsigned __int16)word_14001EA4C;
  }
  return v0;
}

```

## disassembly

```asm
0x140015580  mov     r11, rsp
0x140015583  mov     [r11+8], rbx
0x140015587  mov     [r11+10h], rsi
0x14001558b  push    rdi
0x14001558c  sub     rsp, 50h
0x140015590  mov     rax, cs:__security_cookie
0x140015597  xor     rax, rsp
0x14001559a  mov     [rsp+58h+var_10], rax
0x14001559f  movzx   ecx, cs:word_14001EA4C
0x1400155a6  xor     eax, eax
0x1400155a8  mov     qword ptr [r11-20h], 0
0x1400155b0  cmp     ax, cx
0x1400155b3  jnz     loc_14001566B
0x1400155b9  lea     rax, [r11-20h]
0x1400155bd  mov     [rsp+58h+cbData], 6
0x1400155c5  mov     r9d, 1; samDesired
0x1400155cb  mov     [r11-38h], rax
0x1400155cf  xor     r8d, r8d; ulOptions
0x1400155d2  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Active Setup\\Inst"...
0x1400155d9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400155e0  call    cs:__imp_RegOpenKeyExW
0x1400155e6  test    eax, eax
0x1400155e8  jnz     short loc_140015664
0x1400155ea  mov     rcx, [rsp+58h+hKey]; hKey
0x1400155ef  lea     rax, [rsp+58h+cbData]
0x1400155f4  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1400155f9  lea     rdx, aLocale; "Locale"
0x140015600  lea     rax, [rsp+58h+Data]
0x140015605  xor     r9d, r9d; lpType
0x140015608  xor     r8d, r8d; lpReserved
0x14001560b  mov     [rsp+58h+lpData], rax; lpData
0x140015610  call    cs:__imp_RegQueryValueExW
0x140015616  mov     rcx, [rsp+58h+hKey]; hKey
0x14001561b  mov     ebx, eax
0x14001561d  call    cs:__imp_RegCloseKey
0x140015623  test    ebx, ebx
0x140015625  jnz     short loc_140015664
0x140015627  lea     rsi, off_140018AF0; "EN"
0x14001562e  cmp     ebx, 1Ch
0x140015631  jnb     short loc_140015664
0x140015633  movsxd  rdi, ebx
0x140015636  lea     rcx, [rsp+58h+Data]; String1
0x14001563b  add     rdi, rdi
0x14001563e  mov     r8d, 3; MaxCount
0x140015644  mov     rdx, [rsi+rdi*8]; String2
0x140015648  call    cs:__imp__wcsnicmp
0x14001564e  test    eax, eax
0x140015650  jz      short loc_140015656
0x140015652  inc     ebx
0x140015654  jmp     short loc_14001562E
0x140015656  movzx   ecx, word ptr [rsi+rdi*8+8]
0x14001565b  mov     cs:word_14001EA4C, cx
0x140015662  jmp     short loc_14001566B
0x140015664  movzx   ecx, cs:word_14001EA4C
0x14001566b  movzx   eax, cx
0x14001566e  mov     rcx, [rsp+58h+var_10]
0x140015673  xor     rcx, rsp; StackCookie
0x140015676  call    __security_check_cookie
0x14001567b  mov     rbx, [rsp+58h+arg_0]
0x140015680  mov     rsi, [rsp+58h+arg_8]
0x140015685  add     rsp, 50h
0x140015689  pop     rdi
0x14001568a  retn
```
