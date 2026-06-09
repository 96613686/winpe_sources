# CFvePolicyReader::UsePolicyFromVolume(ushort const *)

- ea: `0x18002b0b0`
- end: `0x18002b382`
- name: `?UsePolicyFromVolume@CFvePolicyReader@@UEAAJPEBG@Z`
- size: `722`
- prototype: `__int64 __fastcall(CFvePolicyReader *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x18000b91c`
- `0x18000b978`
- `0x18002a940`
- `0x18002af80`
- `0x18002b068`
- `0x18002b0b0`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x18002b210`
- `KERNEL32!GetFileAttributesW` at `0x18002b269`
- `KERNEL32!GetFileAttributesW` at `0x18002b210`
- `KERNEL32!GetFileAttributesW` at `0x18002b269`
- `ADVAPI32!RegCloseKey` at `0x18002b182`
- `ADVAPI32!RegCloseKey` at `0x18002b192`
- `ADVAPI32!RegCloseKey` at `0x18002b182`
- `ADVAPI32!RegCloseKey` at `0x18002b192`
- `ADVAPI32!RegOpenKeyExW` at `0x18002b2eb`
- `ADVAPI32!RegOpenKeyExW` at `0x18002b322`
- `ADVAPI32!RegOpenKeyExW` at `0x18002b2eb`
- `ADVAPI32!RegOpenKeyExW` at `0x18002b322`
- `ADVAPI32!RegLoadKeyW` at `0x18002b283`
- `ADVAPI32!RegLoadKeyW` at `0x18002b2b4`
- `ADVAPI32!RegLoadKeyW` at `0x18002b283`
- `ADVAPI32!RegLoadKeyW` at `0x18002b2b4`
- `ADVAPI32!RegUnLoadKeyW` at `0x18002b162`
- `ADVAPI32!RegUnLoadKeyW` at `0x18002b172`
- `ADVAPI32!RegUnLoadKeyW` at `0x18002b162`
- `ADVAPI32!RegUnLoadKeyW` at `0x18002b172`

## string_xrefs

- `0x18002b1f0`: `\Windows\System32\Config\SOFTWARE`
- `0x18002b245`: `\Windows\System32\Config\SYSTEM`

## pseudocode

```c
__int64 __fastcall CFvePolicyReader::UsePolicyFromVolume(CFvePolicyReader *this, const unsigned __int16 *a2)
{
  int v4; // ebx
  __int64 v6; // rdx
  __int64 v7; // rdx
  LSTATUS KeyW; // eax
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR FileName[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR File[264]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(FileName, 0, 0x208u);
  hKey = 0;
  memset_0(File, 0, 0x208u);
  phkResult = 0;
  if ( a2 )
  {
    CFvePolicyReader::CloseRootPolicyKeys(this);
    CFvePolicyReader::UnloadVolumePolicy(this);
    v4 = StringCchCopyW(FileName, 0x104u, a2);
    if ( v4 < 0 )
      goto LABEL_4;
    v4 = StringCchCatW(FileName, v6, L"\\Windows\\System32\\Config\\SOFTWARE");
    if ( v4 < 0 )
      goto LABEL_4;
    if ( GetFileAttributesW(FileName) == -1 )
      goto LABEL_13;
    v4 = StringCchCopyW(File, 0x104u, a2);
    if ( v4 < 0 )
      goto LABEL_4;
    v4 = StringCchCatW(File, v7, L"\\Windows\\System32\\Config\\SYSTEM");
    if ( v4 < 0 )
      goto LABEL_4;
    if ( GetFileAttributesW(File) == -1 )
    {
LABEL_13:
      v4 = -2147024894;
LABEL_4:
      RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"BitLockerSoftwareRoot");
      RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"BitLockerSystemRoot");
      goto LABEL_5;
    }
    KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"BitLockerSoftwareRoot", FileName);
    v4 = KeyW;
    if ( KeyW > 0 )
      v4 = (unsigned __int16)KeyW | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_4;
    v9 = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"BitLockerSystemRoot", File);
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_4;
    v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"BitLockerSoftwareRoot", 0, 0x20019u, &hKey);
    v4 = v10;
    if ( v10 > 0 )
      v4 = (unsigned __int16)v10 | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_4;
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"BitLockerSystemRoot", 0, 0x20019u, &phkResult);
    v4 = v11;
    if ( v11 > 0 )
      v4 = (unsigned __int16)v11 | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_4;
    *((_QWORD *)this + 2) = hKey;
    *((_QWORD *)this + 3) = phkResult;
    hKey = 0;
    phkResult = 0;
    v4 = StringCchCopyW((unsigned __int16 *)this + 17, 0x104u, a2);
    if ( v4 < 0 )
      goto LABEL_4;
    *((_BYTE *)this + 32) = 1;
  }
  else
  {
    v4 = CFvePolicyReader::ResetRootPolicyKeys(this);
    if ( v4 < 0 )
      goto LABEL_4;
    v4 = StringCchCopyW((unsigned __int16 *)this + 17, 0x104u, &qword_1800318B0);
    if ( v4 < 0 )
      goto LABEL_4;
  }
LABEL_5:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002b0b0  mov     [rsp-8+arg_10], rbx
0x18002b0b5  mov     [rsp-8+arg_18], rsi
0x18002b0ba  push    rbp
0x18002b0bb  push    rdi
0x18002b0bc  push    r12
0x18002b0be  push    r13
0x18002b0c0  push    r14
0x18002b0c2  lea     rbp, [rsp-370h]
0x18002b0ca  sub     rsp, 470h
0x18002b0d1  mov     rax, cs:__security_cookie
0x18002b0d8  xor     rax, rsp
0x18002b0db  mov     [rbp+390h+var_30], rax
0x18002b0e2  mov     r14, rdx
0x18002b0e5  mov     rdi, rcx
0x18002b0e8  mov     ebx, 208h
0x18002b0ed  lea     rcx, [rsp+490h+FileName]; void *
0x18002b0f2  mov     r8d, ebx; Size
0x18002b0f5  xor     edx, edx; Val
0x18002b0f7  call    memset_0
0x18002b0fc  mov     r8d, ebx; Size
0x18002b0ff  mov     [rsp+490h+hKey], 0
0x18002b108  xor     edx, edx; Val
0x18002b10a  lea     rcx, [rbp+390h+File]; void *
0x18002b111  call    memset_0
0x18002b116  mov     [rsp+490h+var_458], 0
0x18002b11f  mov     r13, 0FFFFFFFF80000002h
0x18002b126  mov     rcx, rdi; this
0x18002b129  test    r14, r14
0x18002b12c  jnz     loc_18002B1C5
0x18002b132  call    ?ResetRootPolicyKeys@CFvePolicyReader@@AEAAJXZ; CFvePolicyReader::ResetRootPolicyKeys(void)
0x18002b137  mov     ebx, eax
0x18002b139  test    eax, eax
0x18002b13b  js      short loc_18002B158
0x18002b13d  lea     rcx, [rdi+22h]; unsigned __int16 *
0x18002b141  mov     edx, 104h; unsigned __int64
0x18002b146  lea     r8, qword_1800318B0; unsigned __int16 *
0x18002b14d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b152  mov     ebx, eax
0x18002b154  test    eax, eax
0x18002b156  jns     short loc_18002B178
0x18002b158  lea     rdx, aBitlockersoftw; "BitLockerSoftwareRoot"
0x18002b15f  mov     rcx, r13; hKey
0x18002b162  call    cs:__imp_RegUnLoadKeyW
0x18002b168  lea     rdx, aBitlockersyste; "BitLockerSystemRoot"
0x18002b16f  mov     rcx, r13; hKey
0x18002b172  call    cs:__imp_RegUnLoadKeyW
0x18002b178  mov     rcx, [rsp+490h+hKey]; hKey
0x18002b17d  test    rcx, rcx
0x18002b180  jz      short loc_18002B188
0x18002b182  call    cs:__imp_RegCloseKey
0x18002b188  mov     rcx, [rsp+490h+var_458]; hKey
0x18002b18d  test    rcx, rcx
0x18002b190  jz      short loc_18002B198
0x18002b192  call    cs:__imp_RegCloseKey
0x18002b198  mov     eax, ebx
0x18002b19a  mov     rcx, [rbp+390h+var_30]
0x18002b1a1  xor     rcx, rsp; StackCookie
0x18002b1a4  call    __security_check_cookie
0x18002b1a9  lea     r11, [rsp+490h+var_20]
0x18002b1b1  mov     rbx, [r11+40h]
0x18002b1b5  mov     rsi, [r11+48h]
0x18002b1b9  mov     rsp, r11
0x18002b1bc  pop     r14
0x18002b1be  pop     r13
0x18002b1c0  pop     r12
0x18002b1c2  pop     rdi
0x18002b1c3  pop     rbp
0x18002b1c4  retn
0x18002b1c5  call    ?CloseRootPolicyKeys@CFvePolicyReader@@AEAAXXZ; CFvePolicyReader::CloseRootPolicyKeys(void)
0x18002b1ca  mov     rcx, rdi; this
0x18002b1cd  call    ?UnloadVolumePolicy@CFvePolicyReader@@AEAAXXZ; CFvePolicyReader::UnloadVolumePolicy(void)
0x18002b1d2  mov     esi, 104h
0x18002b1d7  lea     rcx, [rsp+490h+FileName]; unsigned __int16 *
0x18002b1dc  mov     edx, esi; unsigned __int64
0x18002b1de  mov     r8, r14; unsigned __int16 *
0x18002b1e1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b1e6  mov     ebx, eax
0x18002b1e8  test    eax, eax
0x18002b1ea  js      loc_18002B158
0x18002b1f0  lea     r8, aWindowsSystem3; "\\Windows\\System32\\Config\\SOFTWARE"
0x18002b1f7  lea     rcx, [rsp+490h+FileName]; unsigned __int16 *
0x18002b1fc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b201  mov     ebx, eax
0x18002b203  test    eax, eax
0x18002b205  js      loc_18002B158
0x18002b20b  lea     rcx, [rsp+490h+FileName]; lpFileName
0x18002b210  call    cs:__imp_GetFileAttributesW
0x18002b216  or      r12d, 0FFFFFFFFh
0x18002b21a  cmp     eax, r12d
0x18002b21d  jnz     short loc_18002B229
0x18002b21f  mov     ebx, 80070002h
0x18002b224  jmp     loc_18002B158
0x18002b229  mov     r8, r14; unsigned __int16 *
0x18002b22c  lea     rcx, [rbp+390h+File]; unsigned __int16 *
0x18002b233  mov     rdx, rsi; unsigned __int64
0x18002b236  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b23b  mov     ebx, eax
0x18002b23d  test    eax, eax
0x18002b23f  js      loc_18002B158
0x18002b245  lea     r8, aWindowsSystem3_0; "\\Windows\\System32\\Config\\SYSTEM"
0x18002b24c  lea     rcx, [rbp+390h+File]; unsigned __int16 *
0x18002b253  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b258  mov     ebx, eax
0x18002b25a  test    eax, eax
0x18002b25c  js      loc_18002B158
0x18002b262  lea     rcx, [rbp+390h+File]; lpFileName
0x18002b269  call    cs:__imp_GetFileAttributesW
0x18002b26f  cmp     eax, r12d
0x18002b272  jz      short loc_18002B21F
0x18002b274  lea     r8, [rsp+490h+FileName]; lpFile
0x18002b279  mov     rcx, r13; hKey
0x18002b27c  lea     rdx, aBitlockersoftw; "BitLockerSoftwareRoot"
0x18002b283  call    cs:__imp_RegLoadKeyW
0x18002b289  mov     ebx, eax
0x18002b28b  mov     r12d, 80070000h
0x18002b291  test    eax, eax
0x18002b293  jle     short loc_18002B29B
0x18002b295  movzx   ebx, ax
0x18002b298  or      ebx, r12d
0x18002b29b  test    ebx, ebx
0x18002b29d  js      loc_18002B158
0x18002b2a3  lea     r8, [rbp+390h+File]; lpFile
0x18002b2aa  mov     rcx, r13; hKey
0x18002b2ad  lea     rdx, aBitlockersyste; "BitLockerSystemRoot"
0x18002b2b4  call    cs:__imp_RegLoadKeyW
0x18002b2ba  mov     ebx, eax
0x18002b2bc  test    eax, eax
0x18002b2be  jle     short loc_18002B2C6
0x18002b2c0  movzx   ebx, ax
0x18002b2c3  or      ebx, r12d
0x18002b2c6  test    ebx, ebx
0x18002b2c8  js      loc_18002B158
0x18002b2ce  lea     rax, [rsp+490h+hKey]
0x18002b2d3  mov     r9d, 20019h; samDesired
0x18002b2d9  xor     r8d, r8d; ulOptions
0x18002b2dc  mov     [rsp+490h+phkResult], rax; phkResult
0x18002b2e1  lea     rdx, aBitlockersoftw; "BitLockerSoftwareRoot"
0x18002b2e8  mov     rcx, r13; hKey
0x18002b2eb  call    cs:__imp_RegOpenKeyExW
0x18002b2f1  mov     ebx, eax
0x18002b2f3  test    eax, eax
0x18002b2f5  jle     short loc_18002B2FD
0x18002b2f7  movzx   ebx, ax
0x18002b2fa  or      ebx, r12d
0x18002b2fd  test    ebx, ebx
0x18002b2ff  js      loc_18002B158
0x18002b305  lea     rax, [rsp+490h+var_458]
0x18002b30a  mov     r9d, 20019h; samDesired
0x18002b310  xor     r8d, r8d; ulOptions
0x18002b313  mov     [rsp+490h+phkResult], rax; phkResult
0x18002b318  lea     rdx, aBitlockersyste; "BitLockerSystemRoot"
0x18002b31f  mov     rcx, r13; hKey
0x18002b322  call    cs:__imp_RegOpenKeyExW
0x18002b328  mov     ebx, eax
0x18002b32a  test    eax, eax
0x18002b32c  jle     short loc_18002B334
0x18002b32e  movzx   ebx, ax
0x18002b331  or      ebx, r12d
0x18002b334  test    ebx, ebx
0x18002b336  js      loc_18002B158
0x18002b33c  mov     rax, [rsp+490h+hKey]
0x18002b341  lea     rcx, [rdi+22h]; unsigned __int16 *
0x18002b345  mov     [rdi+10h], rax
0x18002b349  mov     r8, r14; unsigned __int16 *
0x18002b34c  mov     rax, [rsp+490h+var_458]
0x18002b351  mov     rdx, rsi; unsigned __int64
0x18002b354  mov     [rdi+18h], rax
0x18002b358  mov     [rsp+490h+hKey], 0
0x18002b361  mov     [rsp+490h+var_458], 0
0x18002b36a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b36f  mov     ebx, eax
0x18002b371  test    eax, eax
0x18002b373  js      loc_18002B158
0x18002b379  mov     byte ptr [rdi+20h], 1
0x18002b37d  jmp     loc_18002B178
```
