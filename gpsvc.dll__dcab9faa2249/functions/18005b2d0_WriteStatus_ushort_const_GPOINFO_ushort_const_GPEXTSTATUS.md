# WriteStatus(ushort const *,_GPOINFO *,ushort const *,_GPEXTSTATUS *)

- ea: `0x18005b2d0`
- end: `0x18005b750`
- name: `?WriteStatus@@YAHPEBGPEAU_GPOINFO@@0PEAU_GPEXTSTATUS@@@Z`
- size: `1152`
- prototype: `int(const unsigned __int16 *, struct _GPOINFO *, const unsigned __int16 *, struct _GPEXTSTATUS *)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180058f20`
- `0x18005ce5c`
- `0x1800689e0`
- `0x18009db40`

## callees

- `0x180003770`
- `0x18005b2d0`
- `0x18005b758`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b35d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b724`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b35d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b316`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b316`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b71b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b71b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005b44c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005b4c7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005b542`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005b5b9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005b634`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005b6af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005b44c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005b4c7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005b542`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005b5b9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005b634`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005b6af`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b3ae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b3ae`

## string_xrefs

- `0x18005b334`: `Software\Microsoft\Windows\CurrentVersion\Group Policy\Status\GPExtensions\%ws`
- `0x18005b34a`: `Software\Microsoft\Windows\CurrentVersion\Group Policy\Status\%ws\GPExtensions\%ws`
- `0x18005b5ad`: `PrevSlowLink`
- `0x18005b3d7`: `WriteStatus: Failed to create reg key with %d.`
- `0x18005b40d`: `WriteStatus: Failed to create reg key with %d.`
- `0x18005b475`: `WriteStatus: Failed to set status reg value with %d.`
- `0x18005b49b`: `WriteStatus: Failed to set status reg value with %d.`
- `0x18005b4f0`: `WriteStatus: Failed to set rsop status reg value with %d.`
- `0x18005b516`: `WriteStatus: Failed to set rsop status reg value with %d.`
- `0x18005b56b`: `WriteStatus: Failed to set time reg value with %d.`
- `0x18005b591`: `WriteStatus: Failed to set time reg value with %d.`
- `0x18005b5e2`: `WriteStatus: Failed to set slowlink reg value with %d.`
- `0x18005b608`: `WriteStatus: Failed to set slowlink reg value with %d.`
- `0x18005b65d`: `WriteStatus: Failed to set RsopLogging reg value with %d.`
- `0x18005b683`: `WriteStatus: Failed to set RsopLogging reg value with %d.`
- `0x18005b6d4`: `WriteStatus: Failed to set ForceRefresh reg value with %d.`
- `0x18005b6f2`: `WriteStatus: Failed to set ForceRefresh reg value with %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WriteStatus(
        const unsigned __int16 *a1,
        struct _GPOINFO *a2,
        const unsigned __int16 *a3,
        const BYTE *a4)
{
  DWORD LastError; // ebx
  int v9; // eax
  unsigned int v11; // r14d
  __int64 v12; // rcx
  unsigned int v13; // eax
  void (*v14)(unsigned int, const unsigned __int16 *, ...); // r9
  const wchar_t *v15; // rdx
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition[4]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[400]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  dwDisposition[0] = 0;
  LastError = GetLastError();
  if ( a3 )
    v9 = StringCchPrintfW(
           SubKey,
           0x190u,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\Status\\%ws\\GPExtensions\\%ws",
           a3,
           a1);
  else
    v9 = StringCchPrintfW(
           SubKey,
           0x190u,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\Status\\GPExtensions\\%ws",
           a1);
  if ( v9 < 0 )
  {
    SetLastError((unsigned __int16)v9);
    return 0;
  }
  v11 = 0;
  v12 = -2147483646;
  if ( !a3 )
    v12 = *((_QWORD *)a2 + 5);
  v13 = RegCreateKeyExW((HKEY)v12, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, dwDisposition);
  if ( v13 )
  {
    LastError = v13;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v14 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"WriteStatus: Failed to create reg key with %d.", v13);
        goto LABEL_60;
      }
      v15 = L"WriteStatus: Failed to create reg key with %d.";
      goto LABEL_12;
    }
  }
  else
  {
    v13 = RegSetValueExW(hKey, L"Status", 0, 4u, a4 + 8, 4u);
    if ( v13 )
    {
      LastError = v13;
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_60;
      v14 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"WriteStatus: Failed to set status reg value with %d.", v13);
        goto LABEL_60;
      }
      v15 = L"WriteStatus: Failed to set status reg value with %d.";
      goto LABEL_12;
    }
    v13 = RegSetValueExW(hKey, L"RsopStatus", 0, 4u, a4 + 12, 4u);
    if ( v13 )
    {
      LastError = v13;
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_60;
      v14 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"WriteStatus: Failed to set rsop status reg value with %d.", v13);
        goto LABEL_60;
      }
      v15 = L"WriteStatus: Failed to set rsop status reg value with %d.";
      goto LABEL_12;
    }
    v13 = RegSetValueExW(hKey, L"LastPolicyTime", 0, 4u, a4 + 16, 4u);
    if ( v13 )
    {
      LastError = v13;
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_60;
      v14 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"WriteStatus: Failed to set time reg value with %d.", v13);
        goto LABEL_60;
      }
      v15 = L"WriteStatus: Failed to set time reg value with %d.";
      goto LABEL_12;
    }
    v13 = RegSetValueExW(hKey, L"PrevSlowLink", 0, 4u, a4, 4u);
    if ( v13 )
    {
      LastError = v13;
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_60;
      v14 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"WriteStatus: Failed to set slowlink reg value with %d.", v13);
        goto LABEL_60;
      }
      v15 = L"WriteStatus: Failed to set slowlink reg value with %d.";
      goto LABEL_12;
    }
    v13 = RegSetValueExW(hKey, L"PrevRsopLogging", 0, 4u, a4 + 4, 4u);
    if ( v13 )
    {
      LastError = v13;
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_60;
      v14 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"WriteStatus: Failed to set RsopLogging reg value with %d.", v13);
        goto LABEL_60;
      }
      v15 = L"WriteStatus: Failed to set RsopLogging reg value with %d.";
      goto LABEL_12;
    }
    v13 = RegSetValueExW(hKey, L"ForceRefreshFG", 0, 4u, a4 + 24, 4u);
    if ( !v13 )
    {
      WriteStatus(0, a2, a3);
      v11 = 1;
      goto LABEL_60;
    }
    LastError = v13;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v14 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"WriteStatus: Failed to set ForceRefresh reg value with %d.", v13);
        goto LABEL_60;
      }
      v15 = L"WriteStatus: Failed to set ForceRefresh reg value with %d.";
LABEL_12:
      v14(2u, v15, v13);
    }
  }
LABEL_60:
  if ( hKey )
    RegCloseKey(hKey);
  SetLastError(LastError);
  return v11;
}

```

## disassembly

```asm
0x18005b2d0  push    rbp
0x18005b2d2  push    rbx
0x18005b2d3  push    rsi
0x18005b2d4  push    rdi
0x18005b2d5  push    r12
0x18005b2d7  push    r13
0x18005b2d9  push    r14
0x18005b2db  push    r15
0x18005b2dd  lea     rbp, [rsp-2A8h]
0x18005b2e5  sub     rsp, 3A8h
0x18005b2ec  mov     rax, cs:__security_cookie
0x18005b2f3  xor     rax, rsp
0x18005b2f6  mov     [rbp+2E0h+var_50], rax
0x18005b2fd  mov     rdi, r9
0x18005b300  mov     rsi, r8
0x18005b303  mov     r15, rdx
0x18005b306  mov     r14, rcx
0x18005b309  xor     r12d, r12d
0x18005b30c  mov     [rsp+3E0h+hKey], r12
0x18005b311  mov     [rsp+3E0h+dwDisposition], r12d
0x18005b316  call    cs:__imp_GetLastError
0x18005b31c  mov     ebx, eax
0x18005b31e  mov     [rsp+3E0h+var_390], eax
0x18005b322  mov     edx, 190h; unsigned __int64
0x18005b327  lea     rcx, [rsp+3E0h+SubKey]; unsigned __int16 *
0x18005b32c  test    rsi, rsi
0x18005b32f  jnz     short loc_18005B342
0x18005b331  mov     r9, r14
0x18005b334  lea     r8, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005b33b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005b340  jmp     short loc_18005B356
0x18005b342  mov     qword ptr [rsp+3E0h+dwOptions], r14
0x18005b347  mov     r9, rsi
0x18005b34a  lea     r8, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005b351  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005b356  test    eax, eax
0x18005b358  jns     short loc_18005B36A
0x18005b35a  movzx   ecx, ax; dwErrCode
0x18005b35d  call    cs:__imp_SetLastError
0x18005b363  xor     eax, eax
0x18005b365  jmp     loc_18005B72D
0x18005b36a  mov     r14d, r12d
0x18005b36d  test    rsi, rsi
0x18005b370  mov     rcx, 0FFFFFFFF80000002h
0x18005b377  jnz     short loc_18005B37D
0x18005b379  mov     rcx, [r15+28h]; hKey
0x18005b37d  lea     rax, [rsp+3E0h+dwDisposition]
0x18005b382  mov     [rsp+3E0h+lpdwDisposition], rax; lpdwDisposition
0x18005b387  lea     rax, [rsp+3E0h+hKey]
0x18005b38c  mov     [rsp+3E0h+phkResult], rax; phkResult
0x18005b391  mov     [rsp+3E0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18005b396  mov     [rsp+3E0h+samDesired], 20006h; samDesired
0x18005b39e  mov     [rsp+3E0h+dwOptions], r12d; dwOptions
0x18005b3a3  xor     r9d, r9d; lpClass
0x18005b3a6  xor     r8d, r8d; Reserved
0x18005b3a9  lea     rdx, [rsp+3E0h+SubKey]; lpSubKey
0x18005b3ae  call    cs:__imp_RegCreateKeyExW
0x18005b3b4  test    eax, eax
0x18005b3b6  jz      short loc_18005B426
0x18005b3b8  mov     ebx, eax
0x18005b3ba  mov     [rsp+3E0h+var_390], eax
0x18005b3be  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18005b3c5  jz      loc_18005B711
0x18005b3cb  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18005b3d2  test    r9, r9
0x18005b3d5  jz      short loc_18005B3F3
0x18005b3d7  lea     rdx, aWritestatusFai_5; "WriteStatus: Failed to create reg key w"...
0x18005b3de  mov     r8d, eax
0x18005b3e1  mov     ecx, 2
0x18005b3e6  mov     rax, r9
0x18005b3e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b3ee  jmp     loc_18005B711
0x18005b3f3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18005b3fa  jz      loc_18005B711
0x18005b400  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18005b407  jz      loc_18005B711
0x18005b40d  lea     rdx, aWritestatusFai_5; "WriteStatus: Failed to create reg key w"...
0x18005b414  mov     r8d, eax
0x18005b417  mov     ecx, 2; unsigned int
0x18005b41c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18005b421  jmp     loc_18005B711
0x18005b426  lea     rax, [rdi+8]
0x18005b42a  mov     r13d, 4
0x18005b430  mov     [rsp+3E0h+samDesired], r13d; cbData
0x18005b435  mov     qword ptr [rsp+3E0h+dwOptions], rax; lpData
0x18005b43a  mov     r9d, r13d; dwType
0x18005b43d  xor     r8d, r8d; Reserved
0x18005b440  lea     rdx, aStatus_0; "Status"
0x18005b447  mov     rcx, [rsp+3E0h+hKey]; hKey
0x18005b44c  call    cs:__imp_RegSetValueExW
0x18005b452  test    eax, eax
0x18005b454  jz      short loc_18005B4A7
0x18005b456  mov     ebx, eax
0x18005b458  mov     [rsp+3E0h+var_390], eax
0x18005b45c  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18005b463  jz      loc_18005B711
0x18005b469  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18005b470  test    r9, r9
0x18005b473  jz      short loc_18005B481
0x18005b475  lea     rdx, aWritestatusFai_6; "WriteStatus: Failed to set status reg v"...
0x18005b47c  jmp     loc_18005B3DE
0x18005b481  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18005b488  jz      loc_18005B711
0x18005b48e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18005b495  jz      loc_18005B711
0x18005b49b  lea     rdx, aWritestatusFai_6; "WriteStatus: Failed to set status reg v"...
0x18005b4a2  jmp     loc_18005B414
0x18005b4a7  lea     rax, [rdi+0Ch]
0x18005b4ab  mov     [rsp+3E0h+samDesired], r13d; cbData
0x18005b4b0  mov     qword ptr [rsp+3E0h+dwOptions], rax; lpData
0x18005b4b5  mov     r9d, r13d; dwType
0x18005b4b8  xor     r8d, r8d; Reserved
0x18005b4bb  lea     rdx, aRsopstatus; "RsopStatus"
0x18005b4c2  mov     rcx, [rsp+3E0h+hKey]; hKey
0x18005b4c7  call    cs:__imp_RegSetValueExW
0x18005b4cd  test    eax, eax
0x18005b4cf  jz      short loc_18005B522
0x18005b4d1  mov     ebx, eax
0x18005b4d3  mov     [rsp+3E0h+var_390], eax
0x18005b4d7  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18005b4de  jz      loc_18005B711
0x18005b4e4  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18005b4eb  test    r9, r9
0x18005b4ee  jz      short loc_18005B4FC
0x18005b4f0  lea     rdx, aWritestatusFai; "WriteStatus: Failed to set rsop status "...
0x18005b4f7  jmp     loc_18005B3DE
0x18005b4fc  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18005b503  jz      loc_18005B711
0x18005b509  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18005b510  jz      loc_18005B711
0x18005b516  lea     rdx, aWritestatusFai; "WriteStatus: Failed to set rsop status "...
0x18005b51d  jmp     loc_18005B414
0x18005b522  lea     rax, [rdi+10h]
0x18005b526  mov     [rsp+3E0h+samDesired], r13d; cbData
0x18005b52b  mov     qword ptr [rsp+3E0h+dwOptions], rax; lpData
0x18005b530  mov     r9d, r13d; dwType
0x18005b533  xor     r8d, r8d; Reserved
0x18005b536  lea     rdx, aLastpolicytime; "LastPolicyTime"
0x18005b53d  mov     rcx, [rsp+3E0h+hKey]; hKey
0x18005b542  call    cs:__imp_RegSetValueExW
0x18005b548  test    eax, eax
0x18005b54a  jz      short loc_18005B59D
0x18005b54c  mov     ebx, eax
0x18005b54e  mov     [rsp+3E0h+var_390], eax
0x18005b552  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18005b559  jz      loc_18005B711
0x18005b55f  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18005b566  test    r9, r9
0x18005b569  jz      short loc_18005B577
0x18005b56b  lea     rdx, aWritestatusFai_0; "WriteStatus: Failed to set time reg val"...
0x18005b572  jmp     loc_18005B3DE
0x18005b577  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18005b57e  jz      loc_18005B711
0x18005b584  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18005b58b  jz      loc_18005B711
0x18005b591  lea     rdx, aWritestatusFai_0; "WriteStatus: Failed to set time reg val"...
0x18005b598  jmp     loc_18005B414
0x18005b59d  mov     [rsp+3E0h+samDesired], r13d; cbData
0x18005b5a2  mov     qword ptr [rsp+3E0h+dwOptions], rdi; lpData
0x18005b5a7  mov     r9d, r13d; dwType
0x18005b5aa  xor     r8d, r8d; Reserved
0x18005b5ad  lea     rdx, aPrevslowlink; "PrevSlowLink"
0x18005b5b4  mov     rcx, [rsp+3E0h+hKey]; hKey
0x18005b5b9  call    cs:__imp_RegSetValueExW
0x18005b5bf  test    eax, eax
0x18005b5c1  jz      short loc_18005B614
0x18005b5c3  mov     ebx, eax
0x18005b5c5  mov     [rsp+3E0h+var_390], eax
0x18005b5c9  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18005b5d0  jz      loc_18005B711
0x18005b5d6  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18005b5dd  test    r9, r9
0x18005b5e0  jz      short loc_18005B5EE
0x18005b5e2  lea     rdx, aWritestatusFai_2; "WriteStatus: Failed to set slowlink reg"...
0x18005b5e9  jmp     loc_18005B3DE
0x18005b5ee  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18005b5f5  jz      loc_18005B711
0x18005b5fb  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18005b602  jz      loc_18005B711
0x18005b608  lea     rdx, aWritestatusFai_2; "WriteStatus: Failed to set slowlink reg"...
0x18005b60f  jmp     loc_18005B414
0x18005b614  lea     rax, [rdi+4]
0x18005b618  mov     [rsp+3E0h+samDesired], r13d; cbData
0x18005b61d  mov     qword ptr [rsp+3E0h+dwOptions], rax; lpData
0x18005b622  mov     r9d, r13d; dwType
0x18005b625  xor     r8d, r8d; Reserved
0x18005b628  lea     rdx, aPrevrsoploggin; "PrevRsopLogging"
0x18005b62f  mov     rcx, [rsp+3E0h+hKey]; hKey
0x18005b634  call    cs:__imp_RegSetValueExW
0x18005b63a  test    eax, eax
0x18005b63c  jz      short loc_18005B68F
0x18005b63e  mov     ebx, eax
0x18005b640  mov     [rsp+3E0h+var_390], eax
0x18005b644  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18005b64b  jz      loc_18005B711
0x18005b651  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18005b658  test    r9, r9
0x18005b65b  jz      short loc_18005B669
0x18005b65d  lea     rdx, aWritestatusFai_4; "WriteStatus: Failed to set RsopLogging "...
0x18005b664  jmp     loc_18005B3DE
0x18005b669  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18005b670  jz      loc_18005B711
0x18005b676  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18005b67d  jz      loc_18005B711
0x18005b683  lea     rdx, aWritestatusFai_4; "WriteStatus: Failed to set RsopLogging "...
0x18005b68a  jmp     loc_18005B414
0x18005b68f  lea     rax, [rdi+18h]
0x18005b693  mov     [rsp+3E0h+samDesired], r13d; cbData
0x18005b698  mov     qword ptr [rsp+3E0h+dwOptions], rax; lpData
0x18005b69d  mov     r9d, r13d; dwType
0x18005b6a0  xor     r8d, r8d; Reserved
0x18005b6a3  lea     rdx, aForcerefreshfg; "ForceRefreshFG"
0x18005b6aa  mov     rcx, [rsp+3E0h+hKey]; hKey
0x18005b6af  call    cs:__imp_RegSetValueExW
0x18005b6b5  test    eax, eax
0x18005b6b7  jz      short loc_18005B6FE
0x18005b6b9  mov     ebx, eax
0x18005b6bb  mov     [rsp+3E0h+var_390], eax
0x18005b6bf  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18005b6c6  jz      short loc_18005B711
0x18005b6c8  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18005b6cf  test    r9, r9
0x18005b6d2  jz      short loc_18005B6E0
0x18005b6d4  lea     rdx, aWritestatusFai_3; "WriteStatus: Failed to set ForceRefresh"...
0x18005b6db  jmp     loc_18005B3DE
0x18005b6e0  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18005b6e7  jz      short loc_18005B711
0x18005b6e9  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18005b6f0  jz      short loc_18005B711
0x18005b6f2  lea     rdx, aWritestatusFai_3; "WriteStatus: Failed to set ForceRefresh"...
0x18005b6f9  jmp     loc_18005B414
0x18005b6fe  mov     r8, rsi; unsigned __int16 *
0x18005b701  mov     rdx, r15; struct _GPOINFO *
0x18005b704  xor     ecx, ecx; lpData
0x18005b706  call    ?WriteStatus@@YAHPEBGPEAU_GPOINFO@@0@Z; WriteStatus(ushort const *,_GPOINFO *,ushort const *)
0x18005b70b  mov     r14d, 1
0x18005b711  mov     rcx, [rsp+3E0h+hKey]; hKey
0x18005b716  test    rcx, rcx
0x18005b719  jz      short loc_18005B722
0x18005b71b  call    cs:__imp_RegCloseKey
0x18005b721  nop
0x18005b722  mov     ecx, ebx; dwErrCode
0x18005b724  call    cs:__imp_SetLastError
0x18005b72a  mov     eax, r14d
0x18005b72d  mov     rcx, [rbp+2E0h+var_50]
0x18005b734  xor     rcx, rsp; StackCookie
0x18005b737  call    __security_check_cookie
0x18005b73c  add     rsp, 3A8h
0x18005b743  pop     r15
0x18005b745  pop     r14
0x18005b747  pop     r13
0x18005b749  pop     r12
0x18005b74b  pop     rdi
0x18005b74c  pop     rsi
0x18005b74d  pop     rbx
0x18005b74e  pop     rbp
0x18005b74f  retn
```
