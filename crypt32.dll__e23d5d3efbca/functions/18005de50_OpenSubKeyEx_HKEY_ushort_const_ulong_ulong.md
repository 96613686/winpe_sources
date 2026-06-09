# OpenSubKeyEx(HKEY__ *,ushort const *,ulong,ulong *)

- ea: `0x18005de50`
- end: `0x18005e0bb`
- name: `?OpenSubKeyEx@@YAPEAUHKEY__@@PEAU1@PEBGKPEAK@Z`
- size: `619`
- prototype: `HKEY __fastcall(HKEY, const unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `21`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034b48`
- `0x180034c88`
- `0x180043070`
- `0x1800480a8`
- `0x18005b450`
- `0x18005be80`
- `0x18005db3c`
- `0x18005dc68`
- `0x18005de50`
- `0x18005ed18`
- `0x180072e24`
- `0x18008a464`
- `0x18008a85c`
- `0x18008a924`
- `0x18008ab48`
- `0x18008abf8`
- `0x180096048`
- `0x1800b8b18`
- `0x1800c7a84`
- `0x1800c81b0`
- `0x1800c83d4`

## callees

- `0x1800336b8`
- `0x180033e14`
- `0x18005d484`
- `0x18005de50`
- `0x1800bec20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119535`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119535`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005dfb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005dfb1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005df87`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005df87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005def3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dfa1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119525`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005def3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dfa1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119525`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ded9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ded9`
- `ntdll!NtQueryObject` at `0x18005dff6`
- `ntdll!NtQueryObject` at `0x18005dff6`
- `profapi!__imp_GetAppContainerRegistryHandle` at `0x18005e06d`
- `profapi!__imp_GetAppContainerRegistryHandle` at `0x18005e07e`
- `profapi!__imp_GetAppContainerRegistryHandle` at `0x18005e06d`
- `profapi!__imp_GetAppContainerRegistryHandle` at `0x18005e07e`

## pseudocode

```c
HKEY __fastcall OpenSubKeyEx(HKEY a1, const unsigned __int16 *a2, int a3, unsigned int *a4)
{
  __int16 v5; // bx
  const WCHAR *v6; // r15
  HKEY v7; // rsi
  int v8; // r14d
  LSTATUS v9; // ebx
  DWORD v11; // ecx
  LSTATUS AppContainerRegistryHandle; // eax
  LSTATUS v13; // eax
  HKEY v14; // rax
  HKEY v15; // rcx
  const WCHAR *v16; // rdx
  int AppContainerKey; // eax
  HKEY phkResult; // [rsp+50h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-31h] BYREF
  HKEY v20; // [rsp+60h] [rbp-29h] BYREF
  _OWORD ObjectInformation[3]; // [rsp+68h] [rbp-21h] BYREF
  __int64 v22; // [rsp+98h] [rbp+Fh]

  phkResult = 0;
  v5 = a3;
  v6 = a2;
  v7 = a1;
  if ( (a3 & 0x800) == 0 )
  {
    if ( (a3 & 0x2000) == 0 )
      goto LABEL_3;
    v14 = OpenSubKeyEx(a1, a2, a3 & 0xFFFF1FFF | 0xC000, 0);
    phkResult = v14;
    if ( !v14 )
    {
      if ( GetLastError() != 2 )
        return 0;
LABEL_3:
      if ( (v5 & 0xC000) != 0 )
      {
        hKey = 0;
        v8 = 131097;
        phkResult = 0;
        if ( v7 != HKEY_CURRENT_USER )
        {
LABEL_5:
          v9 = RegOpenKeyExW(v7, v6, 0, 0x20019u, &phkResult);
          if ( hKey && hKey != HKEY_CURRENT_USER )
            RegCloseKey(hKey);
          if ( !v9 )
            goto LABEL_9;
          goto LABEL_19;
        }
        if ( (unsigned int)I_CryptIsAppContainerToken(0) )
          AppContainerRegistryHandle = GetAppContainerRegistryHandle(131097, &hKey);
        else
          AppContainerRegistryHandle = RegOpenHKCUEx(&hKey);
        v9 = AppContainerRegistryHandle;
        if ( !AppContainerRegistryHandle )
        {
          v7 = hKey;
          goto LABEL_5;
        }
LABEL_19:
        v11 = v9;
LABEL_20:
        SetLastError(v11);
        return 0;
      }
      LODWORD(hKey) = 0;
      if ( !v6 )
        v6 = &szPassword;
      v20 = 0;
      phkResult = 0;
      if ( v7 == HKEY_CURRENT_USER )
      {
        if ( (unsigned int)I_CryptIsAppContainerToken(0) )
          v13 = GetAppContainerRegistryHandle(131097, &v20);
        else
          v13 = RegOpenHKCUEx(&v20);
        v9 = v13;
        if ( v13 )
          goto LABEL_19;
        v7 = v20;
      }
      v8 = 196639;
      v9 = RegCreateKeyExW(v7, v6, 0, 0, 0, 0x3001Fu, 0, &phkResult, (LPDWORD)&hKey);
      if ( v20 && v20 != HKEY_CURRENT_USER )
        RegCloseKey(v20);
      if ( !v9 )
        goto LABEL_9;
      goto LABEL_19;
    }
    v15 = v14;
LABEL_49:
    RegCloseKey(v15);
    v11 = 80;
    goto LABEL_20;
  }
  LODWORD(hKey) = 0;
  v16 = &szPassword;
  v8 = 131097;
  if ( (a3 & 0x8000) == 0 )
    v8 = 196639;
  if ( v6 )
    v16 = v6;
  AppContainerKey = RegCreateAppContainerKeyExU(a1, v16);
  if ( AppContainerKey )
  {
    if ( (v5 & 0xC000) != 0 )
      AppContainerKey = 2;
    v11 = AppContainerKey;
    goto LABEL_20;
  }
  if ( (v5 & 0x2000) != 0 )
  {
    v15 = phkResult;
    goto LABEL_49;
  }
LABEL_9:
  if ( a4 && (*(_BYTE *)a4 & 1) != 0 )
  {
    if ( (v8 & 0xFFFDFFE6) == 0
      || (memset(ObjectInformation, 0, sizeof(ObjectInformation)),
          DWORD1(ObjectInformation[0]) = v8,
          v22 = 0,
          NtQueryObject(phkResult, ObjectBasicInformation, ObjectInformation, 0x38u, 0) >= 0)
      && (DWORD1(ObjectInformation[0]) & 0xFFFDFFE6) == 0 )
    {
      *a4 |= 2u;
    }
    *a4 &= ~1u;
  }
  return phkResult;
}

```

## disassembly

```asm
0x18005de50  push    rbp
0x18005de52  push    rbx
0x18005de53  push    rsi
0x18005de54  push    rdi
0x18005de55  push    r12
0x18005de57  push    r14
0x18005de59  push    r15
0x18005de5b  lea     rbp, [rsp-27h]
0x18005de60  sub     rsp, 0B0h
0x18005de67  mov     rax, cs:__security_cookie
0x18005de6e  xor     rax, rsp
0x18005de71  mov     [rbp+57h+var_40], rax
0x18005de75  xor     r12d, r12d
0x18005de78  mov     rdi, r9
0x18005de7b  mov     [rbp+57h+var_90], r12
0x18005de7f  mov     ebx, r8d
0x18005de82  mov     r15, rdx
0x18005de85  mov     rsi, rcx
0x18005de88  bt      r8d, 0Bh
0x18005de8d  jb      loc_1801194A8
0x18005de93  bt      ebx, 0Dh
0x18005de97  jb      loc_18005E086
0x18005de9d  test    ebx, 0C000h
0x18005dea3  jz      loc_18005DF31
0x18005dea9  mov     [rbp+57h+hKey], r12
0x18005dead  mov     r14d, 20019h
0x18005deb3  mov     [rbp+57h+var_90], r12
0x18005deb7  cmp     rsi, 0FFFFFFFF80000001h
0x18005debe  jz      loc_18005E014
0x18005dec4  lea     rax, [rbp+57h+var_90]
0x18005dec8  mov     r9d, r14d; samDesired
0x18005decb  xor     r8d, r8d; ulOptions
0x18005dece  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18005ded3  mov     rdx, r15; lpSubKey
0x18005ded6  mov     rcx, rsi; hKey
0x18005ded9  call    cs:__imp_RegOpenKeyExW
0x18005dedf  mov     rcx, [rbp+57h+hKey]; hKey
0x18005dee3  mov     ebx, eax
0x18005dee5  test    rcx, rcx
0x18005dee8  jz      short loc_18005DEF9
0x18005deea  cmp     rcx, 0FFFFFFFF80000001h
0x18005def1  jz      short loc_18005DEF9
0x18005def3  call    cs:__imp_RegCloseKey
0x18005def9  test    ebx, ebx
0x18005defb  jnz     loc_18005DFAF
0x18005df01  test    rdi, rdi
0x18005df04  jz      short loc_18005DF0F
0x18005df06  test    byte ptr [rdi], 1
0x18005df09  jnz     loc_18005DFBF
0x18005df0f  mov     rax, [rbp+57h+var_90]
0x18005df13  mov     rcx, [rbp+57h+var_40]
0x18005df17  xor     rcx, rsp; StackCookie
0x18005df1a  call    __security_check_cookie
0x18005df1f  add     rsp, 0B0h
0x18005df26  pop     r15
0x18005df28  pop     r14
0x18005df2a  pop     r12
0x18005df2c  pop     rdi
0x18005df2d  pop     rsi
0x18005df2e  pop     rbx
0x18005df2f  pop     rbp
0x18005df30  retn
0x18005df31  mov     dword ptr [rbp+57h+hKey], r12d
0x18005df35  test    r15, r15
0x18005df38  jz      loc_18005E0AF
0x18005df3e  mov     [rbp+57h+var_80], r12
0x18005df42  mov     [rbp+57h+var_90], r12
0x18005df46  cmp     rsi, 0FFFFFFFF80000001h
0x18005df4d  jz      loc_18005E03D
0x18005df53  mov     eax, 3001Fh
0x18005df58  lea     rcx, [rbp+57h+hKey]
0x18005df5c  mov     [rsp+0E0h+lpdwDisposition], rcx; lpdwDisposition
0x18005df61  xor     r9d, r9d; lpClass
0x18005df64  lea     rcx, [rbp+57h+var_90]
0x18005df68  xor     r8d, r8d; Reserved
0x18005df6b  mov     [rsp+0E0h+var_A8], rcx; phkResult
0x18005df70  mov     rdx, r15; lpSubKey
0x18005df73  mov     [rsp+0E0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18005df78  mov     rcx, rsi; hKey
0x18005df7b  mov     [rsp+0E0h+samDesired], eax; samDesired
0x18005df7f  mov     r14d, eax
0x18005df82  mov     dword ptr [rsp+0E0h+phkResult], r12d; dwOptions
0x18005df87  call    cs:__imp_RegCreateKeyExW
0x18005df8d  mov     rcx, [rbp+57h+var_80]; hKey
0x18005df91  mov     ebx, eax
0x18005df93  test    rcx, rcx
0x18005df96  jz      short loc_18005DFA7
0x18005df98  cmp     rcx, 0FFFFFFFF80000001h
0x18005df9f  jz      short loc_18005DFA7
0x18005dfa1  call    cs:__imp_RegCloseKey
0x18005dfa7  test    ebx, ebx
0x18005dfa9  jz      loc_18005DF01
0x18005dfaf  mov     ecx, ebx; dwErrCode
0x18005dfb1  call    cs:__imp_SetLastError
0x18005dfb7  mov     rax, r12
0x18005dfba  jmp     loc_18005DF13
0x18005dfbf  test    r14d, 0FFFDFFE6h
0x18005dfc6  jz      short loc_18005E009
0x18005dfc8  mov     rcx, [rbp+57h+var_90]; Handle
0x18005dfcc  lea     r8, [rbp+57h+ObjectInformation]; ObjectInformation
0x18005dfd0  xorps   xmm0, xmm0
0x18005dfd3  mov     [rsp+0E0h+phkResult], r12; ReturnLength
0x18005dfd8  xor     eax, eax
0x18005dfda  mov     r9d, 38h ; '8'; ObjectInformationLength
0x18005dfe0  movups  [rbp+57h+ObjectInformation], xmm0
0x18005dfe4  xor     edx, edx; ObjectInformationClass
0x18005dfe6  mov     dword ptr [rbp+57h+ObjectInformation+4], r14d
0x18005dfea  movups  [rbp+57h+var_68], xmm0
0x18005dfee  mov     [rbp+57h+var_48], rax
0x18005dff2  movups  [rbp+57h+var_58], xmm0
0x18005dff6  call    cs:__imp_NtQueryObject
0x18005dffc  test    eax, eax
0x18005dffe  js      short loc_18005E00C
0x18005e000  test    dword ptr [rbp+57h+ObjectInformation+4], 0FFFDFFE6h
0x18005e007  jnz     short loc_18005E00C
0x18005e009  or      dword ptr [rdi], 2
0x18005e00c  and     dword ptr [rdi], 0FFFFFFFEh
0x18005e00f  jmp     loc_18005DF0F
0x18005e014  xor     ecx, ecx
0x18005e016  call    I_CryptIsAppContainerToken
0x18005e01b  test    eax, eax
0x18005e01d  jnz     short loc_18005E066
0x18005e01f  xor     edx, edx
0x18005e021  lea     rcx, [rbp+57h+hKey]; phkResult
0x18005e025  call    RegOpenHKCUEx
0x18005e02a  mov     ebx, eax
0x18005e02c  test    eax, eax
0x18005e02e  jnz     loc_18005DFAF
0x18005e034  mov     rsi, [rbp+57h+hKey]
0x18005e038  jmp     loc_18005DEC4
0x18005e03d  xor     ecx, ecx
0x18005e03f  call    I_CryptIsAppContainerToken
0x18005e044  test    eax, eax
0x18005e046  jnz     short loc_18005E075
0x18005e048  xor     edx, edx
0x18005e04a  lea     rcx, [rbp+57h+var_80]; phkResult
0x18005e04e  call    RegOpenHKCUEx
0x18005e053  mov     ebx, eax
0x18005e055  test    eax, eax
0x18005e057  jnz     loc_18005DFAF
0x18005e05d  mov     rsi, [rbp+57h+var_80]
0x18005e061  jmp     loc_18005DF53
0x18005e066  lea     rdx, [rbp+57h+hKey]
0x18005e06a  mov     ecx, r14d
0x18005e06d  call    cs:__imp_GetAppContainerRegistryHandle
0x18005e073  jmp     short loc_18005E02A
0x18005e075  lea     rdx, [rbp+57h+var_80]
0x18005e079  mov     ecx, 20019h
0x18005e07e  call    cs:__imp_GetAppContainerRegistryHandle
0x18005e084  jmp     short loc_18005E053
0x18005e086  btr     r8d, 0Dh
0x18005e08b  xor     r9d, r9d; unsigned int *
0x18005e08e  or      r8d, 0C000h; unsigned int
0x18005e095  call    ?OpenSubKeyEx@@YAPEAUHKEY__@@PEAU1@PEBGKPEAK@Z; OpenSubKeyEx(HKEY__ *,ushort const *,ulong,ulong *)
0x18005e09a  mov     [rbp+57h+var_90], rax
0x18005e09e  test    rax, rax
0x18005e0a1  jz      loc_180119535
0x18005e0a7  mov     rcx, rax
0x18005e0aa  jmp     loc_180119525
0x18005e0af  lea     r15, szPassword
0x18005e0b6  jmp     loc_18005DF3E
0x1801194a8  bt      ebx, 0Fh
0x1801194ac  mov     dword ptr [rbp+57h+hKey], r12d
0x1801194b0  mov     eax, 3001Fh
0x1801194b5  lea     rcx, [rbp+57h+hKey]
0x1801194b9  mov     [rsp+0E0h+lpdwDisposition], rcx
0x1801194be  lea     rdx, szPassword
0x1801194c5  lea     rcx, [rbp+57h+var_90]
0x1801194c9  mov     r14d, 20019h
0x1801194cf  mov     [rsp+0E0h+var_A8], rcx
0x1801194d4  cmovnb  r14d, eax
0x1801194d8  test    r15, r15
0x1801194db  mov     [rsp+0E0h+samDesired], r14d
0x1801194e0  mov     rcx, rsi
0x1801194e3  mov     dword ptr [rsp+0E0h+phkResult], 4
0x1801194eb  cmovnz  rdx, r15
0x1801194ef  call    RegCreateAppContainerKeyExU
0x1801194f4  test    eax, eax
0x1801194f6  jz      short loc_18011950D
0x1801194f8  test    ebx, 0C000h
0x1801194fe  mov     ecx, 2
0x180119503  cmovnz  eax, ecx
0x180119506  mov     ecx, eax
0x180119508  jmp     loc_18005DFB1
0x18011950d  bt      ebx, 0Dh
0x180119511  jnb     loc_18005DF01
0x180119517  cmp     dword ptr [rbp+57h+hKey], 1
0x18011951b  jz      loc_18005DF01
0x180119521  mov     rcx, [rbp+57h+var_90]; hKey
0x180119525  call    cs:__imp_RegCloseKey
0x18011952b  mov     ecx, 50h ; 'P'
0x180119530  jmp     loc_18005DFB1
0x180119535  call    cs:__imp_GetLastError
0x18011953b  cmp     eax, 2
0x18011953e  jnz     loc_18005DFB7
0x180119544  jmp     loc_18005DE9D
```
