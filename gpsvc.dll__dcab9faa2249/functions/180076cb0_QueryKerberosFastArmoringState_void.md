# QueryKerberosFastArmoringState(void)

- ea: `0x180076cb0`
- end: `0x18007709c`
- name: `?QueryKerberosFastArmoringState@@YAHXZ`
- size: `1004`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005ce5c`

## callees

- `0x180075ec0`
- `0x180076cb0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076eb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077074`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076eb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077074`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076cf7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076eec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076cf7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076eec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180076d45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180076de2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180076f37`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180076fcc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180076d45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180076de2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180076f37`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180076fcc`

## string_xrefs

- `0x180076d7b`: `Failed to query EnableCbacAndArmor in GP Kerberos Armoring in Registry = 0x%x`
- `0x180076da0`: `Failed to query EnableCbacAndArmor in GP Kerberos Armoring in Registry = 0x%x`
- `0x180076e14`: `Failed to query RequireFast in GP Kerberos Armoring in Registry = 0x%x`
- `0x180076e39`: `Failed to query RequireFast in GP Kerberos Armoring in Registry = 0x%x`
- `0x180076e6e`: `Failed to query GP Kerberos Armoring in Registry = 0x%x`
- `0x180076e96`: `Failed to query GP Kerberos Armoring in Registry = 0x%x`
- `0x180076f63`: `Failed to query EnableCbacAndArmor in Manual Kerberos Armoring in Registry = 0x%x`
- `0x180076f8b`: `Failed to query EnableCbacAndArmor in Manual Kerberos Armoring in Registry = 0x%x`
- `0x180076ff9`: `Failed to query RequireFast in Manual Kerberos Armoring in Registry = 0x%x`
- `0x180077014`: `Failed to query RequireFast in Manual Kerberos Armoring in Registry = 0x%x`
- `0x180077032`: `Failed to query Manual Kerberos Armoring in Registry = 0x%x`
- `0x18007705a`: `Failed to query Manual Kerberos Armoring in Registry = 0x%x`

## pseudocode

```c
__int64 QueryKerberosFastArmoringState(void)
{
  int v0; // eax
  bool v1; // sf
  int v2; // r14d
  int v3; // r15d
  LSTATUS v4; // eax
  unsigned int v5; // edi
  unsigned int v6; // esi
  LSTATUS v7; // eax
  unsigned int v8; // edi
  int v9; // eax
  bool v10; // sf
  int v11; // eax
  bool v12; // sf
  bool v13; // sf
  void (*v14)(unsigned int, const unsigned __int16 *, ...); // r9
  const wchar_t *v15; // rdx
  DWORD cbData; // [rsp+80h] [rbp+48h] BYREF
  int Data; // [rsp+88h] [rbp+50h] BYREF
  int v19; // [rsp+90h] [rbp+58h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+60h] BYREF

  hKey = 0;
  Data = 0;
  v19 = 0;
  cbData = 0;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System\\Kerberos\\Parameters",
         0,
         0x20019u,
         &hKey);
  v1 = v0 < 0;
  if ( v0 > 0 )
  {
    v0 = (unsigned __int16)v0 | 0x80070000;
    v1 = v0 < 0;
  }
  if ( v1 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"Failed to query GP Kerberos Armoring in Registry = 0x%x", (unsigned int)v0);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"Failed to query GP Kerberos Armoring in Registry = 0x%x", (unsigned int)v0);
      }
    }
    v6 = 1;
    v2 = 1;
    goto LABEL_33;
  }
  cbData = 4;
  v2 = 0;
  v3 = 0;
  v4 = RegQueryValueExW(hKey, L"EnableCbacAndArmor", 0, 0, (LPBYTE)&Data, &cbData);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  v6 = 1;
  if ( (v5 & 0x80000000) != 0 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"Failed to query EnableCbacAndArmor in GP Kerberos Armoring in Registry = 0x%x", v5);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"Failed to query EnableCbacAndArmor in GP Kerberos Armoring in Registry = 0x%x", v5);
      }
    }
    if ( v5 == -2147024894 )
      v2 = 1;
  }
  cbData = 4;
  v7 = RegQueryValueExW(hKey, L"RequireFast", 0, 0, (LPBYTE)&v19, &cbData);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( (v8 & 0x80000000) != 0 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"Failed to query RequireFast in GP Kerberos Armoring in Registry = 0x%x", v8);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"Failed to query RequireFast in GP Kerberos Armoring in Registry = 0x%x", v8);
      }
    }
    if ( v8 == -2147024894 )
LABEL_33:
      v3 = 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v2 || v3 )
  {
    v9 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\Kerberos\\Parameters",
           0,
           0x20019u,
           &hKey);
    v10 = v9 < 0;
    if ( v9 > 0 )
    {
      v9 = (unsigned __int16)v9 | 0x80070000;
      v10 = v9 < 0;
    }
    if ( v10 )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_68;
      v14 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"Failed to query Manual Kerberos Armoring in Registry = 0x%x", (unsigned int)v9);
        goto LABEL_68;
      }
      v15 = L"Failed to query Manual Kerberos Armoring in Registry = 0x%x";
    }
    else
    {
      if ( v2 )
      {
        cbData = 4;
        v11 = RegQueryValueExW(hKey, L"EnableCbacAndArmor", 0, 0, (LPBYTE)&Data, &cbData);
        v12 = v11 < 0;
        if ( v11 > 0 )
        {
          v11 = (unsigned __int16)v11 | 0x80070000;
          v12 = v11 < 0;
        }
        if ( v12 && *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              2u,
              L"Failed to query EnableCbacAndArmor in Manual Kerberos Armoring in Registry = 0x%x",
              (unsigned int)v11);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              2u,
              L"Failed to query EnableCbacAndArmor in Manual Kerberos Armoring in Registry = 0x%x",
              (unsigned int)v11);
          }
        }
      }
      if ( !v3 )
        goto LABEL_68;
      cbData = 4;
      v9 = RegQueryValueExW(hKey, L"RequireFast", 0, 0, (LPBYTE)&v19, &cbData);
      v13 = v9 < 0;
      if ( v9 > 0 )
      {
        v9 = (unsigned __int16)v9 | 0x80070000;
        v13 = v9 < 0;
      }
      if ( !v13 || !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_68;
      v14 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(
            2u,
            L"Failed to query RequireFast in Manual Kerberos Armoring in Registry = 0x%x",
            (unsigned int)v9);
        goto LABEL_68;
      }
      v15 = L"Failed to query RequireFast in Manual Kerberos Armoring in Registry = 0x%x";
    }
    v14(2u, v15, (unsigned int)v9);
LABEL_68:
    if ( hKey )
      RegCloseKey(hKey);
  }
  if ( !Data || !v19 )
    return 0;
  return v6;
}

```

## disassembly

```asm
0x180076cb0  push    rbp
0x180076cb2  push    rbx
0x180076cb3  push    rsi
0x180076cb4  push    rdi
0x180076cb5  push    r12
0x180076cb7  push    r13
0x180076cb9  push    r14
0x180076cbb  push    r15
0x180076cbd  mov     rbp, rsp
0x180076cc0  sub     rsp, 38h
0x180076cc4  xor     r12d, r12d
0x180076cc7  lea     rax, [rbp+hKey]
0x180076ccb  mov     r9d, 20019h; samDesired
0x180076cd1  mov     [rbp+hKey], r12
0x180076cd5  xor     r8d, r8d; ulOptions
0x180076cd8  mov     [rbp+Data], r12d
0x180076cdc  lea     rdx, aSoftwareMicros_31; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180076ce3  mov     [rbp+arg_10], r12d
0x180076ce7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180076cee  mov     [rbp+cbData], r12d
0x180076cf2  mov     [rsp+38h+phkResult], rax; phkResult
0x180076cf7  call    cs:__imp_RegOpenKeyExW
0x180076cfd  mov     r13d, 80070000h
0x180076d03  test    eax, eax
0x180076d05  jle     short loc_180076D0F
0x180076d07  movzx   eax, ax
0x180076d0a  or      eax, r13d
0x180076d0d  test    eax, eax
0x180076d0f  js      loc_180076E51
0x180076d15  mov     rcx, [rbp+hKey]; hKey
0x180076d19  lea     rax, [rbp+cbData]
0x180076d1d  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180076d22  lea     rdx, aEnablecbacanda; "EnableCbacAndArmor"
0x180076d29  lea     rax, [rbp+Data]
0x180076d2d  mov     [rbp+cbData], 4
0x180076d34  xor     r9d, r9d; lpType
0x180076d37  mov     [rsp+38h+phkResult], rax; lpData
0x180076d3c  xor     r8d, r8d; lpReserved
0x180076d3f  mov     r14d, r12d
0x180076d42  mov     r15d, r12d
0x180076d45  call    cs:__imp_RegQueryValueExW
0x180076d4b  mov     edi, eax
0x180076d4d  test    eax, eax
0x180076d4f  jle     short loc_180076D57
0x180076d51  movzx   edi, ax
0x180076d54  or      edi, r13d
0x180076d57  mov     ebx, 2
0x180076d5c  lea     esi, [rbx-1]
0x180076d5f  test    edi, edi
0x180076d61  jns     short loc_180076DB8
0x180076d63  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180076d6a  jz      short loc_180076DAE
0x180076d6c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180076d73  test    rax, rax
0x180076d76  jz      short loc_180076D8B
0x180076d78  mov     r8d, edi
0x180076d7b  lea     rdx, aFailedToQueryE; "Failed to query EnableCbacAndArmor in G"...
0x180076d82  mov     ecx, ebx
0x180076d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076d89  jmp     short loc_180076DAE
0x180076d8b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180076d92  jz      short loc_180076DAE
0x180076d94  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180076d9b  jz      short loc_180076DAE
0x180076d9d  mov     r8d, edi
0x180076da0  lea     rdx, aFailedToQueryE; "Failed to query EnableCbacAndArmor in G"...
0x180076da7  mov     ecx, ebx; unsigned int
0x180076da9  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180076dae  cmp     edi, 80070002h
0x180076db4  cmovz   r14d, esi
0x180076db8  mov     rcx, [rbp+hKey]; hKey
0x180076dbc  lea     rax, [rbp+cbData]
0x180076dc0  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180076dc5  lea     rdx, aRequirefast; "RequireFast"
0x180076dcc  lea     rax, [rbp+arg_10]
0x180076dd0  mov     [rbp+cbData], 4
0x180076dd7  xor     r9d, r9d; lpType
0x180076dda  mov     [rsp+38h+phkResult], rax; lpData
0x180076ddf  xor     r8d, r8d; lpReserved
0x180076de2  call    cs:__imp_RegQueryValueExW
0x180076de8  mov     edi, eax
0x180076dea  test    eax, eax
0x180076dec  jle     short loc_180076DF4
0x180076dee  movzx   edi, ax
0x180076df1  or      edi, r13d
0x180076df4  test    edi, edi
0x180076df6  jns     loc_180076EAF
0x180076dfc  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180076e03  jz      short loc_180076E47
0x180076e05  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180076e0c  test    rax, rax
0x180076e0f  jz      short loc_180076E24
0x180076e11  mov     r8d, edi
0x180076e14  lea     rdx, aFailedToQueryR; "Failed to query RequireFast in GP Kerbe"...
0x180076e1b  mov     ecx, ebx
0x180076e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076e22  jmp     short loc_180076E47
0x180076e24  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180076e2b  jz      short loc_180076E47
0x180076e2d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180076e34  jz      short loc_180076E47
0x180076e36  mov     r8d, edi
0x180076e39  lea     rdx, aFailedToQueryR; "Failed to query RequireFast in GP Kerbe"...
0x180076e40  mov     ecx, ebx; unsigned int
0x180076e42  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180076e47  cmp     edi, 80070002h
0x180076e4d  jnz     short loc_180076EAF
0x180076e4f  jmp     short loc_180076EAC
0x180076e51  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180076e58  mov     ebx, 2
0x180076e5d  jz      short loc_180076EA4
0x180076e5f  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180076e66  test    r9, r9
0x180076e69  jz      short loc_180076E81
0x180076e6b  mov     r8d, eax
0x180076e6e  lea     rdx, aFailedToQueryG; "Failed to query GP Kerberos Armoring in"...
0x180076e75  mov     rax, r9
0x180076e78  mov     ecx, ebx
0x180076e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076e7f  jmp     short loc_180076EA4
0x180076e81  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180076e88  jz      short loc_180076EA4
0x180076e8a  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180076e91  jz      short loc_180076EA4
0x180076e93  mov     r8d, eax
0x180076e96  lea     rdx, aFailedToQueryG; "Failed to query GP Kerberos Armoring in"...
0x180076e9d  mov     ecx, ebx; unsigned int
0x180076e9f  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180076ea4  mov     esi, 1
0x180076ea9  mov     r14d, esi
0x180076eac  mov     r15d, esi
0x180076eaf  mov     rcx, [rbp+hKey]; hKey
0x180076eb3  test    rcx, rcx
0x180076eb6  jz      short loc_180076EBE
0x180076eb8  call    cs:__imp_RegCloseKey
0x180076ebe  test    r14d, r14d
0x180076ec1  jnz     short loc_180076ECC
0x180076ec3  test    r15d, r15d
0x180076ec6  jz      loc_18007707A
0x180076ecc  lea     rax, [rbp+hKey]
0x180076ed0  mov     r9d, 20019h; samDesired
0x180076ed6  xor     r8d, r8d; ulOptions
0x180076ed9  mov     [rsp+38h+phkResult], rax; phkResult
0x180076ede  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x180076ee5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180076eec  call    cs:__imp_RegOpenKeyExW
0x180076ef2  test    eax, eax
0x180076ef4  jle     short loc_180076EFE
0x180076ef6  movzx   eax, ax
0x180076ef9  or      eax, r13d
0x180076efc  test    eax, eax
0x180076efe  js      loc_18007701D
0x180076f04  test    r14d, r14d
0x180076f07  jz      loc_180076F99
0x180076f0d  mov     rcx, [rbp+hKey]; hKey
0x180076f11  lea     rax, [rbp+cbData]
0x180076f15  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180076f1a  lea     rdx, aEnablecbacanda; "EnableCbacAndArmor"
0x180076f21  lea     rax, [rbp+Data]
0x180076f25  mov     [rbp+cbData], 4
0x180076f2c  xor     r9d, r9d; lpType
0x180076f2f  mov     [rsp+38h+phkResult], rax; lpData
0x180076f34  xor     r8d, r8d; lpReserved
0x180076f37  call    cs:__imp_RegQueryValueExW
0x180076f3d  test    eax, eax
0x180076f3f  jle     short loc_180076F49
0x180076f41  movzx   eax, ax
0x180076f44  or      eax, r13d
0x180076f47  test    eax, eax
0x180076f49  jns     short loc_180076F99
0x180076f4b  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180076f52  jz      short loc_180076F99
0x180076f54  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180076f5b  test    r9, r9
0x180076f5e  jz      short loc_180076F76
0x180076f60  mov     r8d, eax
0x180076f63  lea     rdx, aFailedToQueryE_0; "Failed to query EnableCbacAndArmor in M"...
0x180076f6a  mov     rax, r9
0x180076f6d  mov     ecx, ebx
0x180076f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076f74  jmp     short loc_180076F99
0x180076f76  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180076f7d  jz      short loc_180076F99
0x180076f7f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180076f86  jz      short loc_180076F99
0x180076f88  mov     r8d, eax
0x180076f8b  lea     rdx, aFailedToQueryE_0; "Failed to query EnableCbacAndArmor in M"...
0x180076f92  mov     ecx, ebx; unsigned int
0x180076f94  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180076f99  test    r15d, r15d
0x180076f9c  jz      loc_18007706B
0x180076fa2  mov     rcx, [rbp+hKey]; hKey
0x180076fa6  lea     rax, [rbp+cbData]
0x180076faa  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180076faf  lea     rdx, aRequirefast; "RequireFast"
0x180076fb6  lea     rax, [rbp+arg_10]
0x180076fba  mov     [rbp+cbData], 4
0x180076fc1  xor     r9d, r9d; lpType
0x180076fc4  mov     [rsp+38h+phkResult], rax; lpData
0x180076fc9  xor     r8d, r8d; lpReserved
0x180076fcc  call    cs:__imp_RegQueryValueExW
0x180076fd2  test    eax, eax
0x180076fd4  jle     short loc_180076FDE
0x180076fd6  movzx   eax, ax
0x180076fd9  or      eax, r13d
0x180076fdc  test    eax, eax
0x180076fde  jns     loc_18007706B
0x180076fe4  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180076feb  jz      short loc_18007706B
0x180076fed  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180076ff4  test    r9, r9
0x180076ff7  jz      short loc_180077002
0x180076ff9  lea     rdx, aFailedToQueryR_0; "Failed to query RequireFast in Manual K"...
0x180077000  jmp     short loc_180077039
0x180077002  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180077009  jz      short loc_18007706B
0x18007700b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180077012  jz      short loc_18007706B
0x180077014  lea     rdx, aFailedToQueryR_0; "Failed to query RequireFast in Manual K"...
0x18007701b  jmp     short loc_180077061
0x18007701d  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180077024  jz      short loc_18007706B
0x180077026  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18007702d  test    r9, r9
0x180077030  jz      short loc_180077048
0x180077032  lea     rdx, aFailedToQueryM; "Failed to query Manual Kerberos Armorin"...
0x180077039  mov     r8d, eax
0x18007703c  mov     ecx, ebx
0x18007703e  mov     rax, r9
0x180077041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077046  jmp     short loc_18007706B
0x180077048  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18007704f  jz      short loc_18007706B
0x180077051  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180077058  jz      short loc_18007706B
0x18007705a  lea     rdx, aFailedToQueryM; "Failed to query Manual Kerberos Armorin"...
0x180077061  mov     r8d, eax
0x180077064  mov     ecx, ebx; unsigned int
0x180077066  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18007706b  mov     rcx, [rbp+hKey]; hKey
0x18007706f  test    rcx, rcx
0x180077072  jz      short loc_18007707A
0x180077074  call    cs:__imp_RegCloseKey
0x18007707a  cmp     [rbp+Data], r12d
0x18007707e  jz      short loc_180077086
0x180077080  cmp     [rbp+arg_10], r12d
0x180077084  jnz     short loc_180077089
0x180077086  mov     esi, r12d
0x180077089  mov     eax, esi
0x18007708b  add     rsp, 38h
0x18007708f  pop     r15
0x180077091  pop     r14
0x180077093  pop     r13
0x180077095  pop     r12
0x180077097  pop     rdi
0x180077098  pop     rsi
0x180077099  pop     rbx
0x18007709a  pop     rbp
0x18007709b  retn
```
