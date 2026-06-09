# GetDefaultRenderingIntent(WCS_PROFILE_MANAGEMENT_SCOPE,ulong *)

- ea: `0x18000913c`
- end: `0x1800092bc`
- name: `?GetDefaultRenderingIntent@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEAK@Z`
- size: `384`
- prototype: `unsigned int(enum WCS_PROFILE_MANAGEMENT_SCOPE, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800087e0`
- `0x1800462e0`

## callees

- `0x1800089d8`
- `0x18000913c`
- `0x18002e5f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009247`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009280`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009247`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009280`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009216`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009216`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009299`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009299`

## pseudocode

```c
__int64 __fastcall GetDefaultRenderingIntent(enum WCS_PROFILE_MANAGEMENT_SCOPE a1, BYTE *a2)
{
  __int64 v3; // rdi
  int v4; // eax
  unsigned int v5; // ebx
  signed int i; // r8d
  __int64 v7; // rdx
  char *v8; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ValueName[12]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  cbData = 0;
  hKey = 0;
  Type = 0;
  v3 = -(__int64)(a1 != WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE);
  v4 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", gszICMRegPath, gszRegisteredProfiles);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v13 = 1919483904;
    for ( i = 0; (unsigned int)i < 4; ++i )
    {
      v7 = i;
      v8 = (char *)&v13 - i + 3;
      ValueName[v7] = *v8;
    }
    ValueName[4] = 0;
    v5 = RegOpenKeyExW((HKEY)(v3 - 2147483646), SubKey, 0, 0x20119u, &hKey);
    if ( !v5 )
    {
      v5 = RegQueryValueExW(hKey, ValueName, 0, &Type, 0, &cbData);
      if ( !v5 )
      {
        if ( Type == 4 && cbData == 4 )
          v5 = RegQueryValueExW(hKey, ValueName, 0, 0, a2, &cbData);
        else
          v5 = -2147467259;
      }
    }
  }
  else if ( (v4 & 0x1FFF0000) == 0x70000 )
  {
    v5 = (unsigned __int16)v4;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x18000913c  push    rbp
0x18000913e  push    rbx
0x18000913f  push    rsi
0x180009140  push    rdi
0x180009141  lea     rbp, [rsp-188h]
0x180009149  sub     rsp, 288h
0x180009150  mov     rax, cs:__security_cookie
0x180009157  xor     rax, rsp
0x18000915a  mov     [rbp+1A0h+var_30], rax
0x180009161  neg     ecx
0x180009163  mov     [rsp+2A0h+cbData], 0
0x18000916b  mov     rsi, rdx
0x18000916e  mov     [rsp+2A0h+hKey], 0
0x180009177  lea     rax, gszRegisteredProfiles; "RegisteredProfiles"
0x18000917e  mov     [rsp+2A0h+Type], 0
0x180009186  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x18000918b  mov     [rsp+2A0h+phkResult], rax
0x180009190  lea     r9, gszICMRegPath; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180009197  mov     edx, 104h; unsigned __int64
0x18000919c  lea     r8, aSS; "%s\\%s"
0x1800091a3  sbb     rdi, rdi
0x1800091a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800091ab  mov     ebx, eax
0x1800091ad  test    eax, eax
0x1800091af  jns     short loc_1800091C9
0x1800091b1  and     eax, 1FFF0000h
0x1800091b6  cmp     eax, 70000h
0x1800091bb  jnz     loc_18000928F
0x1800091c1  movzx   ebx, bx
0x1800091c4  jmp     loc_18000928F
0x1800091c9  mov     [rsp+2A0h+var_260], 72690000h
0x1800091d1  xor     r8d, r8d
0x1800091d4  movsxd  rdx, r8d
0x1800091d7  lea     rax, [rsp+2A0h+var_260+3]
0x1800091dc  sub     rax, rdx
0x1800091df  inc     r8d
0x1800091e2  movsx   eax, byte ptr [rax]
0x1800091e5  mov     [rsp+rdx*2+2A0h+ValueName], ax
0x1800091ea  cmp     r8d, 4
0x1800091ee  jb      short loc_1800091D4
0x1800091f0  xor     eax, eax
0x1800091f2  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x1800091f7  mov     [rsp+2A0h+var_250], ax
0x1800091fc  lea     rcx, [rdi-7FFFFFFEh]; hKey
0x180009203  lea     rax, [rsp+2A0h+hKey]
0x180009208  mov     r9d, 20119h; samDesired
0x18000920e  xor     r8d, r8d; ulOptions
0x180009211  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180009216  call    cs:__imp_RegOpenKeyExW
0x18000921c  mov     ebx, eax
0x18000921e  test    eax, eax
0x180009220  jnz     short loc_18000928F
0x180009222  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180009227  lea     rax, [rsp+2A0h+cbData]
0x18000922c  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x180009231  lea     r9, [rsp+2A0h+Type]; lpType
0x180009236  xor     r8d, r8d; lpReserved
0x180009239  mov     [rsp+2A0h+phkResult], 0; lpData
0x180009242  lea     rdx, [rsp+2A0h+ValueName]; lpValueName
0x180009247  call    cs:__imp_RegQueryValueExW
0x18000924d  mov     ebx, eax
0x18000924f  test    eax, eax
0x180009251  jnz     short loc_18000928F
0x180009253  cmp     [rsp+2A0h+Type], 4
0x180009258  jnz     short loc_18000928A
0x18000925a  cmp     [rsp+2A0h+cbData], 4
0x18000925f  jnz     short loc_18000928A
0x180009261  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180009266  lea     rax, [rsp+2A0h+cbData]
0x18000926b  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x180009270  lea     rdx, [rsp+2A0h+ValueName]; lpValueName
0x180009275  xor     r9d, r9d; lpType
0x180009278  mov     [rsp+2A0h+phkResult], rsi; lpData
0x18000927d  xor     r8d, r8d; lpReserved
0x180009280  call    cs:__imp_RegQueryValueExW
0x180009286  mov     ebx, eax
0x180009288  jmp     short loc_18000928F
0x18000928a  mov     ebx, 80004005h
0x18000928f  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180009294  test    rcx, rcx
0x180009297  jz      short loc_18000929F
0x180009299  call    cs:__imp_RegCloseKey
0x18000929f  mov     eax, ebx
0x1800092a1  mov     rcx, [rbp+1A0h+var_30]
0x1800092a8  xor     rcx, rsp; StackCookie
0x1800092ab  call    __security_check_cookie
0x1800092b0  add     rsp, 288h
0x1800092b7  pop     rdi
0x1800092b8  pop     rsi
0x1800092b9  pop     rbx
0x1800092ba  pop     rbp
0x1800092bb  retn
```
