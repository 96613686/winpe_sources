# WcsGetDefaultRenderingIntent

- ea: `0x1800087e0`
- end: `0x1800089d0`
- name: `WcsGetDefaultRenderingIntent`
- size: `496`
- prototype: `BOOL __stdcall(WCS_PROFILE_MANAGEMENT_SCOPE scope, PDWORD pdwRenderingIntent)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800087e0`
- `0x1800089d8`
- `0x18000913c`
- `0x18002e5f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008971`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800089ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008971`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800089ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800088c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800088c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800089c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800089c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000892a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000892a`

## pseudocode

```c
BOOL __stdcall WcsGetDefaultRenderingIntent(WCS_PROFILE_MANAGEMENT_SCOPE scope, PDWORD pdwRenderingIntent)
{
  int v4; // eax
  int DefaultRenderingIntent; // ebx
  signed int i; // r8d
  __int64 v7; // rdx
  char *v8; // rax
  DWORD v10; // ecx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ValueName[12]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( pdwRenderingIntent && (unsigned int)scope <= WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER )
  {
    cbData = 0;
    hKey = 0;
    Type = 0;
    v4 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", gszICMRegPath, gszRegisteredProfiles);
    DefaultRenderingIntent = v4;
    if ( v4 < 0 )
    {
      if ( (v4 & 0x1FFF0000) == 0x70000 )
        DefaultRenderingIntent = (unsigned __int16)v4;
    }
    else
    {
      v14 = 1919483904;
      for ( i = 0; (unsigned int)i < 4; ++i )
      {
        v7 = i;
        v8 = (char *)&v14 - i + 3;
        ValueName[v7] = *v8;
      }
      ValueName[4] = 0;
      DefaultRenderingIntent = RegOpenKeyExW(
                                 (HKEY)(-(__int64)(scope != WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE) - 2147483646),
                                 SubKey,
                                 0,
                                 0x20119u,
                                 &hKey);
      if ( !DefaultRenderingIntent )
      {
        DefaultRenderingIntent = RegQueryValueExW(hKey, ValueName, 0, &Type, 0, &cbData);
        if ( !DefaultRenderingIntent )
        {
          if ( Type == 4 && cbData == 4 )
            DefaultRenderingIntent = RegQueryValueExW(hKey, ValueName, 0, 0, (LPBYTE)pdwRenderingIntent, &cbData);
          else
            DefaultRenderingIntent = -2147467259;
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( !DefaultRenderingIntent )
      return 1;
    if ( scope == WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER )
    {
      DefaultRenderingIntent = GetDefaultRenderingIntent(
                                 WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE,
                                 (BYTE *)pdwRenderingIntent);
      if ( !DefaultRenderingIntent )
        return 1;
    }
    v10 = DefaultRenderingIntent;
  }
  else
  {
    v10 = 87;
  }
  SetLastError(v10);
  return 0;
}

```

## disassembly

```asm
0x1800087e0  mov     [rsp-8+arg_0], rbx
0x1800087e5  mov     [rsp-8+arg_10], rsi
0x1800087ea  push    rbp
0x1800087eb  push    rdi
0x1800087ec  push    r14
0x1800087ee  lea     rbp, [rsp-180h]
0x1800087f6  sub     rsp, 280h
0x1800087fd  mov     rax, cs:__security_cookie
0x180008804  xor     rax, rsp
0x180008807  mov     [rbp+190h+var_20], rax
0x18000880e  mov     rsi, rdx
0x180008811  mov     edi, ecx
0x180008813  test    rdx, rdx
0x180008816  jz      loc_180008934
0x18000881c  test    ecx, ecx
0x18000881e  jz      short loc_180008829
0x180008820  cmp     ecx, 1
0x180008823  jnz     loc_180008934
0x180008829  mov     eax, edi
0x18000882b  mov     [rsp+290h+cbData], 0
0x180008833  neg     eax
0x180008835  mov     [rsp+290h+hKey], 0
0x18000883e  lea     rax, gszRegisteredProfiles; "RegisteredProfiles"
0x180008845  mov     [rsp+290h+Type], 0
0x18000884d  lea     r9, gszICMRegPath; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180008854  mov     [rsp+290h+phkResult], rax
0x180008859  lea     r8, aSS; "%s\\%s"
0x180008860  mov     edx, 104h; unsigned __int64
0x180008865  lea     rcx, [rsp+290h+SubKey]; unsigned __int16 *
0x18000886a  sbb     r14, r14
0x18000886d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008872  mov     ebx, eax
0x180008874  test    eax, eax
0x180008876  js      loc_18000893B
0x18000887c  mov     [rsp+290h+var_250], 72690000h
0x180008884  xor     r8d, r8d
0x180008887  movsxd  rdx, r8d
0x18000888a  lea     rax, [rsp+290h+var_250+3]
0x18000888f  sub     rax, rdx
0x180008892  inc     r8d
0x180008895  movsx   eax, byte ptr [rax]
0x180008898  mov     [rsp+rdx*2+290h+ValueName], ax
0x18000889d  cmp     r8d, 4
0x1800088a1  jb      short loc_180008887
0x1800088a3  xor     eax, eax
0x1800088a5  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x1800088aa  mov     [rsp+290h+var_240], ax
0x1800088af  lea     rcx, [r14-7FFFFFFEh]; hKey
0x1800088b6  lea     rax, [rsp+290h+hKey]
0x1800088bb  mov     r9d, 20119h; samDesired
0x1800088c1  xor     r8d, r8d; ulOptions
0x1800088c4  mov     [rsp+290h+phkResult], rax; phkResult
0x1800088c9  call    cs:__imp_RegOpenKeyExW
0x1800088cf  mov     ebx, eax
0x1800088d1  test    eax, eax
0x1800088d3  jz      short loc_18000894C
0x1800088d5  mov     rcx, [rsp+290h+hKey]; hKey
0x1800088da  test    rcx, rcx
0x1800088dd  jnz     loc_1800089C5
0x1800088e3  test    ebx, ebx
0x1800088e5  jnz     short loc_180008913
0x1800088e7  mov     eax, 1
0x1800088ec  mov     rcx, [rbp+190h+var_20]
0x1800088f3  xor     rcx, rsp; StackCookie
0x1800088f6  call    __security_check_cookie
0x1800088fb  lea     r11, [rsp+290h+var_10]
0x180008903  mov     rbx, [r11+20h]
0x180008907  mov     rsi, [r11+30h]
0x18000890b  mov     rsp, r11
0x18000890e  pop     r14
0x180008910  pop     rdi
0x180008911  pop     rbp
0x180008912  retn
0x180008913  cmp     edi, 1
0x180008916  jnz     short loc_180008928
0x180008918  mov     rdx, rsi; unsigned int *
0x18000891b  xor     ecx, ecx; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x18000891d  call    ?GetDefaultRenderingIntent@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEAK@Z; GetDefaultRenderingIntent(WCS_PROFILE_MANAGEMENT_SCOPE,ulong *)
0x180008922  mov     ebx, eax
0x180008924  test    eax, eax
0x180008926  jz      short loc_1800088E7
0x180008928  mov     ecx, ebx; dwErrCode
0x18000892a  call    cs:__imp_SetLastError
0x180008930  xor     eax, eax
0x180008932  jmp     short loc_1800088EC
0x180008934  mov     ecx, 57h ; 'W'
0x180008939  jmp     short loc_18000892A
0x18000893b  and     eax, 1FFF0000h
0x180008940  cmp     eax, 70000h
0x180008945  jnz     short loc_1800088D5
0x180008947  movzx   ebx, bx
0x18000894a  jmp     short loc_1800088D5
0x18000894c  mov     rcx, [rsp+290h+hKey]; hKey
0x180008951  lea     rax, [rsp+290h+cbData]
0x180008956  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18000895b  lea     r9, [rsp+290h+Type]; lpType
0x180008960  xor     r8d, r8d; lpReserved
0x180008963  mov     [rsp+290h+phkResult], 0; lpData
0x18000896c  lea     rdx, [rsp+290h+ValueName]; lpValueName
0x180008971  call    cs:__imp_RegQueryValueExW
0x180008977  mov     ebx, eax
0x180008979  test    eax, eax
0x18000897b  jnz     loc_1800088D5
0x180008981  cmp     [rsp+290h+Type], 4
0x180008986  jnz     short loc_1800089BB
0x180008988  cmp     [rsp+290h+cbData], 4
0x18000898d  jnz     short loc_1800089BB
0x18000898f  mov     rcx, [rsp+290h+hKey]; hKey
0x180008994  lea     rax, [rsp+290h+cbData]
0x180008999  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18000899e  lea     rdx, [rsp+290h+ValueName]; lpValueName
0x1800089a3  xor     r9d, r9d; lpType
0x1800089a6  mov     [rsp+290h+phkResult], rsi; lpData
0x1800089ab  xor     r8d, r8d; lpReserved
0x1800089ae  call    cs:__imp_RegQueryValueExW
0x1800089b4  mov     ebx, eax
0x1800089b6  jmp     loc_1800088D5
0x1800089bb  mov     ebx, 80004005h
0x1800089c0  jmp     loc_1800088D5
0x1800089c5  call    cs:__imp_RegCloseKey
0x1800089cb  jmp     loc_1800088E3
```
