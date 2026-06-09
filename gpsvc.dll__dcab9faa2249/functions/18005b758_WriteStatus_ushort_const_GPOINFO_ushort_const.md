# WriteStatus(ushort const *,_GPOINFO *,ushort const *)

- ea: `0x18005b758`
- end: `0x18005b9ff`
- name: `?WriteStatus@@YAHPEBGPEAU_GPOINFO@@0@Z`
- size: `679`
- prototype: `__int64 __fastcall(BYTE *lpData, struct _GPOINFO *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180058f20`
- `0x18005b2d0`
- `0x18005ce5c`

## callees

- `0x180003770`
- `0x18001dcf0`
- `0x18005b758`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b7d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b9d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b7d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b9d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b79e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b8d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b79e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b8d4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005b9b9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005b9b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b9cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b9cc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005b95e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005b95e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b82a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b82a`

## string_xrefs

- `0x18005b7c6`: `Software\Microsoft\Windows\CurrentVersion\Group Policy\Status\%ws\GPExtensions`
- `0x18005b7b5`: `Software\Microsoft\Windows\CurrentVersion\Group Policy\Status\GPExtensions`
- `0x18005b853`: `WriteStatus: Failed to create reg key with %d.`
- `0x18005b889`: `WriteStatus: Failed to create reg key with %d.`
- `0x18005b952`: `Extension`
- `0x18005b9ad`: `Extension`
- `0x18005b983`: `WriteStatus: Failed to set reg value with %d. OK for async returns.`
- `0x18005b9a1`: `WriteStatus: Failed to set reg value with %d. OK for async returns.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WriteStatus(BYTE *lpData, struct _GPOINFO *a2, const unsigned __int16 *a3)
{
  DWORD LastError; // ebx
  int v7; // eax
  unsigned int v9; // r14d
  __int64 v10; // rcx
  unsigned int v11; // eax
  void (*v12)(unsigned int, const unsigned __int16 *, ...); // r9
  const wchar_t *v13; // rdx
  __int64 v14; // rcx
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition[4]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[400]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  dwDisposition[0] = 0;
  cbData = 0;
  LastError = GetLastError();
  if ( a3 )
    v7 = StringCchPrintfW(
           SubKey,
           0x190u,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\Status\\%ws\\GPExtensions",
           a3);
  else
    v7 = StringCchPrintfW(
           SubKey,
           0x190u,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\Status\\GPExtensions");
  if ( v7 < 0 )
  {
    SetLastError((unsigned __int16)v7);
    return 0;
  }
  v9 = 0;
  v10 = -2147483646;
  if ( !a3 )
    v10 = *((_QWORD *)a2 + 5);
  v11 = RegCreateKeyExW((HKEY)v10, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, dwDisposition);
  if ( !v11 )
  {
    if ( lpData )
    {
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)&lpData[2 * v14] );
      if ( (int)ULongLongToULong(2 * v14 + 2, &cbData) < 0 )
      {
        LastError = GetLastError();
        cbData = LastError;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"SizeTToDWord() Failed to convert to DWORD");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"SizeTToDWord() Failed to convert to DWORD");
          }
        }
        goto LABEL_36;
      }
      v11 = RegSetValueExW(hKey, L"Extension", 0, 1u, lpData, cbData);
      if ( v11 )
      {
        LastError = v11;
        cbData = v11;
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_36;
        v12 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
        {
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(2u, L"WriteStatus: Failed to set reg value with %d. OK for async returns.", v11);
          goto LABEL_36;
        }
        v13 = L"WriteStatus: Failed to set reg value with %d. OK for async returns.";
        goto LABEL_12;
      }
    }
    else
    {
      RegDeleteValueW(hKey, L"Extension");
    }
    v9 = 1;
    goto LABEL_36;
  }
  LastError = v11;
  cbData = v11;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    v12 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"WriteStatus: Failed to create reg key with %d.", v11);
      goto LABEL_36;
    }
    v13 = L"WriteStatus: Failed to create reg key with %d.";
LABEL_12:
    v12(2u, v13, v11);
  }
LABEL_36:
  if ( hKey )
    RegCloseKey(hKey);
  SetLastError(LastError);
  return v9;
}

```

## disassembly

```asm
0x18005b758  push    rbp
0x18005b75a  push    rbx
0x18005b75b  push    rsi
0x18005b75c  push    rdi
0x18005b75d  push    r12
0x18005b75f  push    r14
0x18005b761  push    r15
0x18005b763  lea     rbp, [rsp-2A0h]
0x18005b76b  sub     rsp, 3A0h
0x18005b772  mov     rax, cs:__security_cookie
0x18005b779  xor     rax, rsp
0x18005b77c  mov     [rbp+2D0h+var_40], rax
0x18005b783  mov     rdi, r8
0x18005b786  mov     r15, rdx
0x18005b789  mov     rsi, rcx
0x18005b78c  xor     r12d, r12d
0x18005b78f  mov     [rsp+3D0h+hKey], r12
0x18005b794  mov     [rsp+3D0h+dwDisposition], r12d
0x18005b799  mov     [rsp+3D0h+cbData], r12d
0x18005b79e  call    cs:__imp_GetLastError
0x18005b7a4  mov     ebx, eax
0x18005b7a6  mov     edx, 190h; unsigned __int64
0x18005b7ab  lea     rcx, [rsp+3D0h+SubKey]; unsigned __int16 *
0x18005b7b0  test    rdi, rdi
0x18005b7b3  jnz     short loc_18005B7C3
0x18005b7b5  lea     r8, aSoftwareMicros_34; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005b7bc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005b7c1  jmp     short loc_18005B7D2
0x18005b7c3  mov     r9, rdi
0x18005b7c6  lea     r8, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005b7cd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005b7d2  test    eax, eax
0x18005b7d4  jns     short loc_18005B7E6
0x18005b7d6  movzx   ecx, ax; dwErrCode
0x18005b7d9  call    cs:__imp_SetLastError
0x18005b7df  xor     eax, eax
0x18005b7e1  jmp     loc_18005B9DE
0x18005b7e6  mov     r14d, r12d
0x18005b7e9  test    rdi, rdi
0x18005b7ec  mov     rcx, 0FFFFFFFF80000002h
0x18005b7f3  jnz     short loc_18005B7F9
0x18005b7f5  mov     rcx, [r15+28h]; hKey
0x18005b7f9  lea     rax, [rsp+3D0h+dwDisposition]
0x18005b7fe  mov     [rsp+3D0h+lpdwDisposition], rax; lpdwDisposition
0x18005b803  lea     rax, [rsp+3D0h+hKey]
0x18005b808  mov     [rsp+3D0h+phkResult], rax; phkResult
0x18005b80d  mov     [rsp+3D0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18005b812  mov     [rsp+3D0h+samDesired], 20006h; samDesired
0x18005b81a  mov     [rsp+3D0h+dwOptions], r12d; dwOptions
0x18005b81f  xor     r9d, r9d; lpClass
0x18005b822  xor     r8d, r8d; Reserved
0x18005b825  lea     rdx, [rsp+3D0h+SubKey]; lpSubKey
0x18005b82a  call    cs:__imp_RegCreateKeyExW
0x18005b830  test    eax, eax
0x18005b832  jz      short loc_18005B8A2
0x18005b834  mov     ebx, eax
0x18005b836  mov     [rsp+3D0h+cbData], eax
0x18005b83a  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18005b841  jz      loc_18005B9C2
0x18005b847  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18005b84e  test    r9, r9
0x18005b851  jz      short loc_18005B86F
0x18005b853  lea     rdx, aWritestatusFai_5; "WriteStatus: Failed to create reg key w"...
0x18005b85a  mov     r8d, eax
0x18005b85d  mov     ecx, 2
0x18005b862  mov     rax, r9
0x18005b865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b86a  jmp     loc_18005B9C2
0x18005b86f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18005b876  jz      loc_18005B9C2
0x18005b87c  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18005b883  jz      loc_18005B9C2
0x18005b889  lea     rdx, aWritestatusFai_5; "WriteStatus: Failed to create reg key w"...
0x18005b890  mov     r8d, eax
0x18005b893  mov     ecx, 2; unsigned int
0x18005b898  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18005b89d  jmp     loc_18005B9C2
0x18005b8a2  mov     edi, 1
0x18005b8a7  test    rsi, rsi
0x18005b8aa  jz      loc_18005B9AD
0x18005b8b0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005b8b4  inc     rcx
0x18005b8b7  cmp     [rsi+rcx*2], r12w
0x18005b8bc  jnz     short loc_18005B8B4
0x18005b8be  lea     rcx, ds:2[rcx*2]; unsigned __int64
0x18005b8c6  lea     rdx, [rsp+3D0h+cbData]; unsigned int *
0x18005b8cb  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18005b8d0  test    eax, eax
0x18005b8d2  jns     short loc_18005B93F
0x18005b8d4  call    cs:__imp_GetLastError
0x18005b8da  mov     ebx, eax
0x18005b8dc  mov     [rsp+3D0h+cbData], eax
0x18005b8e0  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18005b8e7  jz      loc_18005B9C2
0x18005b8ed  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18005b8f4  test    rax, rax
0x18005b8f7  jz      short loc_18005B90F
0x18005b8f9  lea     rdx, aSizettodwordFa_1; "SizeTToDWord() Failed to convert to DWO"...
0x18005b900  mov     ecx, 2
0x18005b905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b90a  jmp     loc_18005B9C2
0x18005b90f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18005b916  jz      loc_18005B9C2
0x18005b91c  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18005b923  jz      loc_18005B9C2
0x18005b929  lea     rdx, aSizettodwordFa_1; "SizeTToDWord() Failed to convert to DWO"...
0x18005b930  mov     ecx, 2; unsigned int
0x18005b935  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18005b93a  jmp     loc_18005B9C2
0x18005b93f  mov     eax, [rsp+3D0h+cbData]
0x18005b943  mov     [rsp+3D0h+samDesired], eax; cbData
0x18005b947  mov     qword ptr [rsp+3D0h+dwOptions], rsi; lpData
0x18005b94c  mov     r9d, edi; dwType
0x18005b94f  xor     r8d, r8d; Reserved
0x18005b952  lea     rdx, aExtension; "Extension"
0x18005b959  mov     rcx, [rsp+3D0h+hKey]; hKey
0x18005b95e  call    cs:__imp_RegSetValueExW
0x18005b964  test    eax, eax
0x18005b966  jz      short loc_18005B9BF
0x18005b968  mov     ebx, eax
0x18005b96a  mov     [rsp+3D0h+cbData], eax
0x18005b96e  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18005b975  jz      short loc_18005B9C2
0x18005b977  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18005b97e  test    r9, r9
0x18005b981  jz      short loc_18005B98F
0x18005b983  lea     rdx, aWritestatusFai_1; "WriteStatus: Failed to set reg value wi"...
0x18005b98a  jmp     loc_18005B85A
0x18005b98f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18005b996  jz      short loc_18005B9C2
0x18005b998  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18005b99f  jz      short loc_18005B9C2
0x18005b9a1  lea     rdx, aWritestatusFai_1; "WriteStatus: Failed to set reg value wi"...
0x18005b9a8  jmp     loc_18005B890
0x18005b9ad  lea     rdx, aExtension; "Extension"
0x18005b9b4  mov     rcx, [rsp+3D0h+hKey]; hKey
0x18005b9b9  call    cs:__imp_RegDeleteValueW
0x18005b9bf  mov     r14d, edi
0x18005b9c2  mov     rcx, [rsp+3D0h+hKey]; hKey
0x18005b9c7  test    rcx, rcx
0x18005b9ca  jz      short loc_18005B9D3
0x18005b9cc  call    cs:__imp_RegCloseKey
0x18005b9d2  nop
0x18005b9d3  mov     ecx, ebx; dwErrCode
0x18005b9d5  call    cs:__imp_SetLastError
0x18005b9db  mov     eax, r14d
0x18005b9de  mov     rcx, [rbp+2D0h+var_40]
0x18005b9e5  xor     rcx, rsp; StackCookie
0x18005b9e8  call    __security_check_cookie
0x18005b9ed  add     rsp, 3A0h
0x18005b9f4  pop     r15
0x18005b9f6  pop     r14
0x18005b9f8  pop     r12
0x18005b9fa  pop     rdi
0x18005b9fb  pop     rsi
0x18005b9fc  pop     rbx
0x18005b9fd  pop     rbp
0x18005b9fe  retn
```
