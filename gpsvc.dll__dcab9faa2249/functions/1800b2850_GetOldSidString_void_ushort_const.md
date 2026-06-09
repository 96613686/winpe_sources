# GetOldSidString(void *,ushort const *)

- ea: `0x1800b2850`
- end: `0x1800b2b6e`
- name: `?GetOldSidString@@YAPEAGPEAXPEBG@Z`
- size: `798`
- prototype: `unsigned __int16 *__fastcall(HANDLE hToken, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800631a8`

## callees

- `0x18002c690`
- `0x180049c90`
- `0x180075ec0`
- `0x18007d320`
- `0x1800b2850`
- `0x1800b2d88`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b2b46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b2b46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b28ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b28ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2a2d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2a2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2b1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2b2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2b1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2b2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2b3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2b3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b292f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b292f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b29c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b2abe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b29c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b2abe`

## string_xrefs

- `0x1800b2954`: `GetOldSidString:  Failed to open profile profile guid key with error %d`
- `0x1800b2987`: `GetOldSidString:  Failed to open profile profile guid key with error %d`
- `0x1800b29bc`: `SidString`
- `0x1800b2ab7`: `SidString`
- `0x1800b29e8`: `GetOldSidString:  Failed to query size of SidString with error %d`
- `0x1800b2a13`: `GetOldSidString:  Failed to query size of SidString with error %d`
- `0x1800b2a57`: `GetOldSidString:  Failed to allocate memory for SidString`
- `0x1800b2a85`: `GetOldSidString:  Failed to allocate memory for SidString`
- `0x1800b2ae2`: `GetOldSidString:  Failed to query SidString with error %d`
- `0x1800b2b0a`: `GetOldSidString:  Failed to query SidString with error %d`

## pseudocode

```c
BYTE *__fastcall GetOldSidString(HANDLE hToken, const unsigned __int16 *a2)
{
  BYTE *v3; // rdi
  DWORD LastError; // esi
  unsigned __int16 *UserGuid; // r14
  DWORD v6; // ebx
  int v7; // eax
  unsigned __int16 *v8; // rax
  void (*v9)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v10; // rdx
  __int64 v11; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v14[3]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  cbData = 0;
  v3 = 0;
  v14[1] = 0;
  hKey = 0;
  v14[0] = 0;
  LastError = GetLastError();
  UserGuid = GetUserGuid(hToken);
  if ( !UserGuid )
  {
    v6 = GetLastError();
    goto LABEL_41;
  }
  v7 = StringCchCopyW(SubKey, 0x104u, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PolicyGuid");
  if ( v7 < 0 )
    goto LABEL_4;
  v8 = CheckSlashEx(SubKey, 0x104u, v14);
  if ( !v8 )
  {
    v6 = 122;
    goto LABEL_40;
  }
  v7 = StringCchCopyW(v8, v14[0], UserGuid);
  if ( v7 < 0 )
  {
LABEL_4:
    v6 = (unsigned __int16)v7;
  }
  else
  {
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
    if ( v6 )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_40;
      v9 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(4u, L"GetOldSidString:  Failed to open profile profile guid key with error %d", v6);
        goto LABEL_40;
      }
      v10 = L"GetOldSidString:  Failed to open profile profile guid key with error %d";
      v11 = 4;
LABEL_12:
      v9(v11, v10, v6);
      goto LABEL_40;
    }
    v6 = RegQueryValueExW(hKey, L"SidString", 0, &v14[1], 0, &cbData);
    if ( !v6 )
    {
      v3 = (BYTE *)LocalAlloc(0x40u, cbData);
      if ( v3 )
      {
        v6 = RegQueryValueExW(hKey, L"SidString", 0, &v14[1], v3, &cbData);
        if ( v6 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"GetOldSidString:  Failed to query SidString with error %d", v6);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"GetOldSidString:  Failed to query SidString with error %d", v6);
            }
          }
          LocalFree(v3);
          v3 = 0;
        }
        else
        {
          v6 = LastError;
        }
      }
      else
      {
        v6 = 0;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"GetOldSidString:  Failed to allocate memory for SidString");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"GetOldSidString:  Failed to allocate memory for SidString");
          }
        }
      }
      goto LABEL_40;
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v9 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"GetOldSidString:  Failed to query size of SidString with error %d", v6);
        goto LABEL_40;
      }
      v10 = L"GetOldSidString:  Failed to query size of SidString with error %d";
      v11 = 2;
      goto LABEL_12;
    }
  }
LABEL_40:
  LocalFree(UserGuid);
LABEL_41:
  if ( hKey )
    RegCloseKey(hKey);
  SetLastError(v6);
  return v3;
}

```

## disassembly

```asm
0x1800b2850  push    rbp
0x1800b2852  push    rbx
0x1800b2853  push    rsi
0x1800b2854  push    rdi
0x1800b2855  push    r14
0x1800b2857  push    r15
0x1800b2859  lea     rbp, [rsp-178h]
0x1800b2861  sub     rsp, 278h
0x1800b2868  mov     rax, cs:__security_cookie
0x1800b286f  xor     rax, rsp
0x1800b2872  mov     [rbp+1A0h+var_40], rax
0x1800b2879  xor     r15d, r15d
0x1800b287c  mov     rbx, rcx
0x1800b287f  mov     [rsp+2A0h+cbData], r15d
0x1800b2884  mov     edi, r15d
0x1800b2887  mov     [rsp+2A0h+var_26C+4], r15d
0x1800b288c  mov     [rsp+2A0h+hKey], r15
0x1800b2891  mov     [rsp+2A0h+var_26C], r15d
0x1800b2896  call    cs:__imp_GetLastError
0x1800b289c  mov     rcx, rbx; hToken
0x1800b289f  mov     esi, eax
0x1800b28a1  call    ?GetUserGuid@@YAPEAGPEAX@Z; GetUserGuid(void *)
0x1800b28a6  mov     r14, rax
0x1800b28a9  test    rax, rax
0x1800b28ac  jnz     short loc_1800B28BB
0x1800b28ae  call    cs:__imp_GetLastError
0x1800b28b4  mov     ebx, eax
0x1800b28b6  jmp     loc_1800B2B34
0x1800b28bb  mov     ebx, 104h
0x1800b28c0  lea     r8, aSoftwareMicros_10; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800b28c7  mov     edx, ebx; unsigned __int64
0x1800b28c9  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x1800b28ce  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b28d3  test    eax, eax
0x1800b28d5  jns     short loc_1800B28DF
0x1800b28d7  movzx   ebx, ax
0x1800b28da  jmp     loc_1800B2B2B
0x1800b28df  lea     r8, [rsp+2A0h+var_26C]; unsigned int *
0x1800b28e4  mov     edx, ebx; unsigned int
0x1800b28e6  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x1800b28eb  call    ?CheckSlashEx@@YAPEAGPEAGIPEAI@Z; CheckSlashEx(ushort *,uint,uint *)
0x1800b28f0  test    rax, rax
0x1800b28f3  jnz     short loc_1800B28FD
0x1800b28f5  lea     ebx, [rax+7Ah]
0x1800b28f8  jmp     loc_1800B2B2B
0x1800b28fd  mov     edx, [rsp+2A0h+var_26C]; unsigned __int64
0x1800b2901  mov     r8, r14; unsigned __int16 *
0x1800b2904  mov     rcx, rax; unsigned __int16 *
0x1800b2907  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b290c  test    eax, eax
0x1800b290e  js      short loc_1800B28D7
0x1800b2910  lea     rax, [rsp+2A0h+hKey]
0x1800b2915  mov     r9d, 20019h; samDesired
0x1800b291b  xor     r8d, r8d; ulOptions
0x1800b291e  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800b2923  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x1800b2928  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b292f  call    cs:__imp_RegOpenKeyExW
0x1800b2935  mov     ebx, eax
0x1800b2937  test    eax, eax
0x1800b2939  jz      short loc_1800B29A0
0x1800b293b  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b2942  jz      loc_1800B2B2B
0x1800b2948  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b294f  test    rax, rax
0x1800b2952  jz      short loc_1800B296D
0x1800b2954  lea     rdx, aGetoldsidstrin_0; "GetOldSidString:  Failed to open profil"...
0x1800b295b  mov     ecx, 4
0x1800b2960  mov     r8d, ebx
0x1800b2963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2968  jmp     loc_1800B2B2B
0x1800b296d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b2974  jz      loc_1800B2B2B
0x1800b297a  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b2981  jz      loc_1800B2B2B
0x1800b2987  lea     rdx, aGetoldsidstrin_0; "GetOldSidString:  Failed to open profil"...
0x1800b298e  mov     ecx, 4; unsigned int
0x1800b2993  mov     r8d, ebx
0x1800b2996  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b299b  jmp     loc_1800B2B2B
0x1800b29a0  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800b29a5  lea     rax, [rsp+2A0h+cbData]
0x1800b29aa  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x1800b29af  lea     r9, [rsp+2A0h+var_26C+4]; lpType
0x1800b29b4  xor     r8d, r8d; lpReserved
0x1800b29b7  mov     [rsp+2A0h+phkResult], r15; lpData
0x1800b29bc  lea     rdx, aSidstring; "SidString"
0x1800b29c3  call    cs:__imp_RegQueryValueExW
0x1800b29c9  mov     ebx, eax
0x1800b29cb  test    eax, eax
0x1800b29cd  jz      short loc_1800B2A24
0x1800b29cf  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b29d6  jz      loc_1800B2B2B
0x1800b29dc  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b29e3  test    rax, rax
0x1800b29e6  jz      short loc_1800B29F9
0x1800b29e8  lea     rdx, aGetoldsidstrin_1; "GetOldSidString:  Failed to query size "...
0x1800b29ef  mov     ecx, 2
0x1800b29f4  jmp     loc_1800B2960
0x1800b29f9  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b2a00  jz      loc_1800B2B2B
0x1800b2a06  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b2a0d  jz      loc_1800B2B2B
0x1800b2a13  lea     rdx, aGetoldsidstrin_1; "GetOldSidString:  Failed to query size "...
0x1800b2a1a  mov     ecx, 2
0x1800b2a1f  jmp     loc_1800B2993
0x1800b2a24  mov     edx, [rsp+2A0h+cbData]; uBytes
0x1800b2a28  mov     ecx, 40h ; '@'; uFlags
0x1800b2a2d  call    cs:__imp_LocalAlloc
0x1800b2a33  mov     rdi, rax
0x1800b2a36  test    rax, rax
0x1800b2a39  jnz     short loc_1800B2A9B
0x1800b2a3b  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b2a42  mov     ebx, r15d
0x1800b2a45  jz      loc_1800B2B2B
0x1800b2a4b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b2a52  test    rax, rax
0x1800b2a55  jz      short loc_1800B2A6B
0x1800b2a57  lea     rdx, aGetoldsidstrin; "GetOldSidString:  Failed to allocate me"...
0x1800b2a5e  lea     ecx, [rdi+2]
0x1800b2a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2a66  jmp     loc_1800B2B2B
0x1800b2a6b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b2a72  jz      loc_1800B2B2B
0x1800b2a78  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b2a7f  jz      loc_1800B2B2B
0x1800b2a85  lea     rdx, aGetoldsidstrin; "GetOldSidString:  Failed to allocate me"...
0x1800b2a8c  mov     ecx, 2; unsigned int
0x1800b2a91  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b2a96  jmp     loc_1800B2B2B
0x1800b2a9b  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800b2aa0  lea     rax, [rsp+2A0h+cbData]
0x1800b2aa5  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x1800b2aaa  lea     r9, [rsp+2A0h+var_26C+4]; lpType
0x1800b2aaf  xor     r8d, r8d; lpReserved
0x1800b2ab2  mov     [rsp+2A0h+phkResult], rdi; lpData
0x1800b2ab7  lea     rdx, aSidstring; "SidString"
0x1800b2abe  call    cs:__imp_RegQueryValueExW
0x1800b2ac4  mov     ebx, eax
0x1800b2ac6  test    eax, eax
0x1800b2ac8  jz      short loc_1800B2B29
0x1800b2aca  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b2ad1  jz      short loc_1800B2B1B
0x1800b2ad3  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b2ada  test    rax, rax
0x1800b2add  jz      short loc_1800B2AF5
0x1800b2adf  mov     r8d, ebx
0x1800b2ae2  lea     rdx, aGetoldsidstrin_2; "GetOldSidString:  Failed to query SidSt"...
0x1800b2ae9  mov     ecx, 2
0x1800b2aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2af3  jmp     short loc_1800B2B1B
0x1800b2af5  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b2afc  jz      short loc_1800B2B1B
0x1800b2afe  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b2b05  jz      short loc_1800B2B1B
0x1800b2b07  mov     r8d, ebx
0x1800b2b0a  lea     rdx, aGetoldsidstrin_2; "GetOldSidString:  Failed to query SidSt"...
0x1800b2b11  mov     ecx, 2; unsigned int
0x1800b2b16  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b2b1b  mov     rcx, rdi; hMem
0x1800b2b1e  call    cs:__imp_LocalFree
0x1800b2b24  mov     rdi, r15
0x1800b2b27  jmp     short loc_1800B2B2B
0x1800b2b29  mov     ebx, esi
0x1800b2b2b  mov     rcx, r14; hMem
0x1800b2b2e  call    cs:__imp_LocalFree
0x1800b2b34  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800b2b39  test    rcx, rcx
0x1800b2b3c  jz      short loc_1800B2B44
0x1800b2b3e  call    cs:__imp_RegCloseKey
0x1800b2b44  mov     ecx, ebx; dwErrCode
0x1800b2b46  call    cs:__imp_SetLastError
0x1800b2b4c  mov     rax, rdi
0x1800b2b4f  mov     rcx, [rbp+1A0h+var_40]
0x1800b2b56  xor     rcx, rsp; StackCookie
0x1800b2b59  call    __security_check_cookie
0x1800b2b5e  add     rsp, 278h
0x1800b2b65  pop     r15
0x1800b2b67  pop     r14
0x1800b2b69  pop     rdi
0x1800b2b6a  pop     rsi
0x1800b2b6b  pop     rbx
0x1800b2b6c  pop     rbp
0x1800b2b6d  retn
```
