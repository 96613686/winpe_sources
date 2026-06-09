# MigrateMembershipData(ushort const *,ushort const *)

- ea: `0x18009d4a8`
- end: `0x18009db3a`
- name: `?MigrateMembershipData@@YAHPEBG0@Z`
- size: `1682`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800631a8`

## callees

- `0x180003770`
- `0x18001dcf0`
- `0x18002f6e0`
- `0x180075ec0`
- `0x18007d320`
- `0x18009d4a8`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009d536`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009db07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009d536`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009db07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d98b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d98b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009d805`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009d805`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009dad0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009dad0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009daef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009dafe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009daef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009dafe`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18009d773`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18009d773`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009d917`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009da6f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009d917`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009da6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009d567`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009d567`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009d62f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009d62f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009d6d0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009d8c6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009d6d0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009d8c6`

## string_xrefs

- `0x18009d657`: `MigrateMembershipData: Failed to create key with %d.`
- `0x18009d686`: `MigrateMembershipData: Failed to create key with %d.`
- `0x18009d6f9`: `MigrateMembershipData: Failed to read membership count`
- `0x18009d726`: `MigrateMembershipData: Failed to read membership count`
- `0x18009da01`: `MigrateMembershipData: Failed to read value %ws`
- `0x18009da27`: `MigrateMembershipData: Failed to read value %ws`
- `0x18009d94b`: `MigrateMembershipData: Failed to write value %ws`
- `0x18009d97f`: `MigrateMembershipData: Failed to write value %ws`
- `0x18009da97`: `MigrateMembershipData: Failed to write count value`
- `0x18009dabc`: `MigrateMembershipData: Failed to write count value`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MigrateMembershipData(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  DWORD LastError; // ebx
  int v5; // eax
  unsigned int v7; // edi
  unsigned int v8; // eax
  unsigned int v9; // eax
  __int64 v10; // r8
  const wchar_t *v11; // rdx
  void (*v12)(unsigned int, const unsigned __int16 *, ...); // rax
  LSTATUS v13; // eax
  unsigned int v14; // eax
  DWORD v15; // ecx
  BYTE *v16; // r15
  unsigned int i; // r14d
  int v18; // eax
  LSTATUS v19; // eax
  __int64 v20; // rcx
  LSTATUS v21; // eax
  void (*v22)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v23; // rdx
  void (*v24)(unsigned int, const unsigned __int16 *, ...); // rax
  const unsigned __int16 *v25; // rdx
  LSTATUS v26; // eax
  DWORD cbData; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbMaxValueLen; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[4]; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD Type; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  HKEY v32; // [rsp+80h] [rbp-80h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  WCHAR ValueName[32]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR v35[256]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR SubKey[256]; // [rsp+2D0h] [rbp+1D0h] BYREF

  *(_DWORD *)Data = 0;
  cbData = 0;
  Type = 0;
  cbMaxValueLen = 0;
  dwDisposition = 0;
  hKey = 0;
  v32 = 0;
  LastError = GetLastError();
  v5 = StringCchPrintfW(
         SubKey,
         0xFAu,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\%ws\\GroupMembership",
         a2);
  if ( v5 < 0 )
    goto LABEL_2;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
  {
    v5 = StringCchPrintfW(
           v35,
           0xFAu,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\%ws\\GroupMembership",
           a1);
    if ( v5 < 0 )
    {
LABEL_2:
      SetLastError((unsigned __int16)v5);
      return 0;
    }
    v8 = GPRegDelnode(HKEY_LOCAL_MACHINE, v35);
    if ( v8 )
    {
      LastError = v8;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"MigrateMembershipData: GPRegDelnode failed.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"MigrateMembershipData: GPRegDelnode failed.");
        }
      }
      goto LABEL_13;
    }
    v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v35, 0, 0, 0, 0x20006u, 0, &v32, &dwDisposition);
    if ( v9 )
    {
      LastError = v9;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( !g_lpDebugMsg )
        {
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(2u, L"MigrateMembershipData: Failed to create key with %d.", v9);
          goto LABEL_13;
        }
        v10 = v9;
        v11 = L"MigrateMembershipData: Failed to create key with %d.";
        v12 = g_lpDebugMsg;
        goto LABEL_18;
      }
    }
    else
    {
      v7 = 1;
      cbData = 4;
      v13 = RegQueryValueExW(hKey, L"Count", 0, &Type, Data, &cbData);
      if ( v13 )
      {
        LastError = v13;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"MigrateMembershipData: Failed to read membership count");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"MigrateMembershipData: Failed to read membership count");
          }
        }
        goto LABEL_85;
      }
      v14 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueLen, 0, 0);
      if ( v14 )
      {
        LastError = v14;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"MigrateMembershipData: Failed to query max size with %d.", v14);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"MigrateMembershipData: Failed to query max size with %d.", v14);
          }
        }
        goto LABEL_85;
      }
      v15 = cbMaxValueLen + 2;
      if ( cbMaxValueLen + 2 < cbMaxValueLen )
      {
        cbMaxValueLen = -1;
        LastError = 534;
        goto LABEL_85;
      }
      cbMaxValueLen += 2;
      v16 = (BYTE *)LocalAlloc(0x40u, v15);
      if ( v16 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= *(_DWORD *)Data )
          {
            cbData = 4;
            v26 = RegSetValueExW(v32, L"Count", 0, 4u, Data, 4u);
            if ( v26 )
            {
              LastError = v26;
              v7 = 0;
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                v24 = g_lpDebugMsg;
                if ( g_lpDebugMsg )
                {
                  v25 = L"MigrateMembershipData: Failed to write count value";
LABEL_79:
                  v24(2u, v25);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(2u, L"MigrateMembershipData: Failed to write count value");
                }
              }
            }
            goto LABEL_83;
          }
          v18 = StringCchPrintfW(ValueName, 0x1Eu, L"Group%d", i);
          if ( v18 < 0 )
          {
            LastError = (unsigned __int16)v18;
            v7 = 0;
            goto LABEL_83;
          }
          cbData = cbMaxValueLen;
          v19 = RegQueryValueExW(hKey, ValueName, 0, &Type, v16, &cbData);
          if ( v19 )
            break;
          v20 = -1;
          do
            ++v20;
          while ( *(_WORD *)&v16[2 * v20] );
          if ( (int)ULongLongToULong(2 * v20 + 2, &cbData) < 0 )
          {
            LastError = GetLastError();
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              v24 = g_lpDebugMsg;
              if ( g_lpDebugMsg )
              {
                v25 = L"SizeTToDWord() Failed to convert to DWORD";
                goto LABEL_79;
              }
              if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                RedirectDebugMsg(2u, L"SizeTToDWord() Failed to convert to DWORD");
            }
            goto LABEL_83;
          }
          v21 = RegSetValueExW(v32, ValueName, 0, 1u, v16, cbData);
          if ( v21 )
          {
            LastError = v21;
            v7 = 0;
            if ( !*(_DWORD *)&g_dwDebugLevel )
              goto LABEL_83;
            v22 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
              v23 = L"MigrateMembershipData: Failed to write value %ws";
LABEL_57:
              v22(2u, v23, ValueName);
              goto LABEL_83;
            }
            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              RedirectDebugMsg(2u, L"MigrateMembershipData: Failed to write value %ws", ValueName);
            goto LABEL_83;
          }
        }
        LastError = v19;
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_83;
        v22 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v23 = L"MigrateMembershipData: Failed to read value %ws";
          goto LABEL_57;
        }
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"MigrateMembershipData: Failed to read value %ws", ValueName);
LABEL_83:
        LocalFree(v16);
        goto LABEL_85;
      }
      LastError = GetLastError();
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v12 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
        {
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(2u, L"MigrateMembershipData: Failed to allocate memory with %d.", 0);
          goto LABEL_13;
        }
        v10 = 0;
        v11 = L"MigrateMembershipData: Failed to allocate memory with %d.";
LABEL_18:
        v12(2u, v11, v10);
      }
    }
LABEL_13:
    v7 = 0;
LABEL_85:
    if ( hKey )
      RegCloseKey(hKey);
    if ( v32 )
      RegCloseKey(v32);
    goto LABEL_89;
  }
  v7 = 1;
LABEL_89:
  SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x18009d4a8  mov     [rsp-8+arg_10], rbx
0x18009d4ad  mov     [rsp-8+arg_18], rsi
0x18009d4b2  push    rbp
0x18009d4b3  push    rdi
0x18009d4b4  push    r12
0x18009d4b6  push    r14
0x18009d4b8  push    r15
0x18009d4ba  lea     rbp, [rsp-3E0h]
0x18009d4c2  sub     rsp, 4E0h
0x18009d4c9  mov     rax, cs:__security_cookie
0x18009d4d0  xor     rax, rsp
0x18009d4d3  mov     [rbp+400h+var_30], rax
0x18009d4da  mov     rdi, rdx
0x18009d4dd  mov     rsi, rcx
0x18009d4e0  xor     r12d, r12d
0x18009d4e3  mov     dword ptr [rsp+500h+Data], r12d
0x18009d4e8  mov     [rsp+500h+cbData], r12d
0x18009d4ed  mov     [rsp+500h+Type], r12d
0x18009d4f2  mov     [rsp+500h+cbMaxValueLen], r12d
0x18009d4f7  mov     [rbp+400h+dwDisposition], r12d
0x18009d4fb  mov     [rsp+500h+hKey], r12
0x18009d500  mov     [rbp+400h+var_480], r12
0x18009d504  call    cs:__imp_GetLastError
0x18009d50a  mov     ebx, eax
0x18009d50c  mov     [rsp+500h+var_4A0], eax
0x18009d510  mov     r9, rdi
0x18009d513  lea     r8, aSoftwareMicros_33; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18009d51a  mov     r14d, 0FAh
0x18009d520  mov     edx, r14d; unsigned __int64
0x18009d523  lea     rcx, [rbp+400h+SubKey]; unsigned __int16 *
0x18009d52a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009d52f  test    eax, eax
0x18009d531  jns     short loc_18009D543
0x18009d533  movzx   ecx, ax; dwErrCode
0x18009d536  call    cs:__imp_SetLastError
0x18009d53c  xor     eax, eax
0x18009d53e  jmp     loc_18009DB0F
0x18009d543  lea     rax, [rsp+500h+hKey]
0x18009d548  mov     [rsp+500h+phkResult], rax; phkResult
0x18009d54d  mov     r9d, 20019h; samDesired
0x18009d553  xor     r8d, r8d; ulOptions
0x18009d556  lea     rdx, [rbp+400h+SubKey]; lpSubKey
0x18009d55d  mov     rdi, 0FFFFFFFF80000002h
0x18009d564  mov     rcx, rdi; hKey
0x18009d567  call    cs:__imp_RegOpenKeyExW
0x18009d56d  test    eax, eax
0x18009d56f  jz      short loc_18009D57B
0x18009d571  mov     edi, 1
0x18009d576  jmp     loc_18009DB05
0x18009d57b  mov     r9, rsi
0x18009d57e  lea     r8, aSoftwareMicros_33; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18009d585  mov     rdx, r14; unsigned __int64
0x18009d588  lea     rcx, [rbp+400h+var_430]; unsigned __int16 *
0x18009d58c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009d591  test    eax, eax
0x18009d593  js      short loc_18009D533
0x18009d595  lea     rdx, [rbp+400h+var_430]; unsigned __int16 *
0x18009d599  mov     rcx, rdi; HKEY
0x18009d59c  call    ?GPRegDelnode@@YAKPEAUHKEY__@@PEBG@Z; GPRegDelnode(HKEY__ *,ushort const *)
0x18009d5a1  test    eax, eax
0x18009d5a3  jz      short loc_18009D5FE
0x18009d5a5  mov     ebx, eax
0x18009d5a7  mov     [rsp+500h+var_4A0], eax
0x18009d5ab  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18009d5b2  jz      short loc_18009D5F6
0x18009d5b4  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009d5bb  test    rax, rax
0x18009d5be  jz      short loc_18009D5D3
0x18009d5c0  lea     rdx, aMigratemembers_6; "MigrateMembershipData: GPRegDelnode fai"...
0x18009d5c7  mov     ecx, 4
0x18009d5cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d5d1  jmp     short loc_18009D5F6
0x18009d5d3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18009d5da  jz      short loc_18009D5F6
0x18009d5dc  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009d5e3  jz      short loc_18009D5F6
0x18009d5e5  lea     rdx, aMigratemembers_6; "MigrateMembershipData: GPRegDelnode fai"...
0x18009d5ec  mov     ecx, 4; unsigned int
0x18009d5f1  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009d5f6  mov     edi, r12d
0x18009d5f9  jmp     loc_18009DAE5
0x18009d5fe  lea     rax, [rbp+400h+dwDisposition]
0x18009d602  mov     [rsp+500h+lpdwDisposition], rax; lpdwDisposition
0x18009d607  lea     rax, [rbp+400h+var_480]
0x18009d60b  mov     [rsp+500h+var_4C8], rax; phkResult
0x18009d610  mov     [rsp+500h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18009d615  mov     [rsp+500h+samDesired], 20006h; samDesired
0x18009d61d  mov     dword ptr [rsp+500h+phkResult], r12d; dwOptions
0x18009d622  xor     r9d, r9d; lpClass
0x18009d625  xor     r8d, r8d; Reserved
0x18009d628  lea     rdx, [rbp+400h+var_430]; lpSubKey
0x18009d62c  mov     rcx, rdi; hKey
0x18009d62f  call    cs:__imp_RegCreateKeyExW
0x18009d635  test    eax, eax
0x18009d637  jz      short loc_18009D69C
0x18009d639  mov     ebx, eax
0x18009d63b  mov     [rsp+500h+var_4A0], eax
0x18009d63f  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18009d646  jz      short loc_18009D5F6
0x18009d648  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009d64f  test    r9, r9
0x18009d652  jz      short loc_18009D66D
0x18009d654  mov     r8d, eax
0x18009d657  lea     rdx, aMigratemembers_2; "MigrateMembershipData: Failed to create"...
0x18009d65e  mov     rax, r9
0x18009d661  mov     ecx, 2
0x18009d666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d66b  jmp     short loc_18009D5F6
0x18009d66d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18009d674  jz      short loc_18009D5F6
0x18009d676  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009d67d  jz      loc_18009D5F6
0x18009d683  mov     r8d, eax
0x18009d686  lea     rdx, aMigratemembers_2; "MigrateMembershipData: Failed to create"...
0x18009d68d  mov     ecx, 2; unsigned int
0x18009d692  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009d697  jmp     loc_18009D5F6
0x18009d69c  mov     edi, 1
0x18009d6a1  lea     esi, [rdi+3]
0x18009d6a4  mov     [rsp+500h+cbData], esi
0x18009d6a8  lea     rax, [rsp+500h+cbData]
0x18009d6ad  mov     qword ptr [rsp+500h+samDesired], rax; lpcbData
0x18009d6b2  lea     rax, [rsp+500h+Data]
0x18009d6b7  mov     [rsp+500h+phkResult], rax; lpData
0x18009d6bc  lea     r9, [rsp+500h+Type]; lpType
0x18009d6c1  xor     r8d, r8d; lpReserved
0x18009d6c4  lea     rdx, ValueName; "Count"
0x18009d6cb  mov     rcx, [rsp+500h+hKey]; hKey
0x18009d6d0  call    cs:__imp_RegQueryValueExW
0x18009d6d6  test    eax, eax
0x18009d6d8  jz      short loc_18009D739
0x18009d6da  mov     ebx, eax
0x18009d6dc  mov     [rsp+500h+var_4A0], eax
0x18009d6e0  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18009d6e7  jz      loc_18009DAE5
0x18009d6ed  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009d6f4  test    rax, rax
0x18009d6f7  jz      short loc_18009D70C
0x18009d6f9  lea     rdx, aMigratemembers_3; "MigrateMembershipData: Failed to read m"...
0x18009d700  mov     ecx, esi
0x18009d702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d707  jmp     loc_18009DAE5
0x18009d70c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18009d713  jz      loc_18009DAE5
0x18009d719  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009d720  jz      loc_18009DAE5
0x18009d726  lea     rdx, aMigratemembers_3; "MigrateMembershipData: Failed to read m"...
0x18009d72d  mov     ecx, esi; unsigned int
0x18009d72f  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009d734  jmp     loc_18009DAE5
0x18009d739  mov     [rsp+500h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18009d73e  mov     [rsp+500h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18009d743  lea     rax, [rsp+500h+cbMaxValueLen]
0x18009d748  mov     [rsp+500h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18009d74d  mov     [rsp+500h+lpdwDisposition], r12; lpcbMaxValueNameLen
0x18009d752  mov     [rsp+500h+var_4C8], r12; lpcValues
0x18009d757  mov     [rsp+500h+lpSecurityAttributes], r12; lpcbMaxClassLen
0x18009d75c  mov     qword ptr [rsp+500h+samDesired], r12; lpcbMaxSubKeyLen
0x18009d761  mov     [rsp+500h+phkResult], r12; lpcSubKeys
0x18009d766  xor     r9d, r9d; lpReserved
0x18009d769  xor     r8d, r8d; lpcchClass
0x18009d76c  xor     edx, edx; lpClass
0x18009d76e  mov     rcx, [rsp+500h+hKey]; hKey
0x18009d773  call    cs:__imp_RegQueryInfoKeyW
0x18009d779  test    eax, eax
0x18009d77b  jz      short loc_18009D7EB
0x18009d77d  mov     ebx, eax
0x18009d77f  mov     [rsp+500h+var_4A0], eax
0x18009d783  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18009d78a  jz      loc_18009DAE5
0x18009d790  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009d797  test    r9, r9
0x18009d79a  jz      short loc_18009D7B8
0x18009d79c  mov     r8d, eax
0x18009d79f  lea     rdx, aMigratemembers_0; "MigrateMembershipData: Failed to query "...
0x18009d7a6  mov     ecx, 2
0x18009d7ab  mov     rax, r9
0x18009d7ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d7b3  jmp     loc_18009DAE5
0x18009d7b8  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18009d7bf  jz      loc_18009DAE5
0x18009d7c5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009d7cc  jz      loc_18009DAE5
0x18009d7d2  mov     r8d, eax
0x18009d7d5  lea     rdx, aMigratemembers_0; "MigrateMembershipData: Failed to query "...
0x18009d7dc  mov     ecx, 2; unsigned int
0x18009d7e1  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009d7e6  jmp     loc_18009DAE5
0x18009d7eb  mov     eax, [rsp+500h+cbMaxValueLen]
0x18009d7ef  lea     ecx, [rax+2]
0x18009d7f2  cmp     ecx, eax
0x18009d7f4  jb      loc_18009DAD8
0x18009d7fa  mov     [rsp+500h+cbMaxValueLen], ecx
0x18009d7fe  mov     edx, ecx; uBytes
0x18009d800  mov     ecx, 40h ; '@'; uFlags
0x18009d805  call    cs:__imp_LocalAlloc
0x18009d80b  mov     r15, rax
0x18009d80e  test    rax, rax
0x18009d811  jnz     short loc_18009D870
0x18009d813  call    cs:__imp_GetLastError
0x18009d819  mov     ebx, eax
0x18009d81b  mov     [rsp+500h+var_4A0], eax
0x18009d81f  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18009d826  jz      loc_18009D5F6
0x18009d82c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009d833  test    rax, rax
0x18009d836  jz      short loc_18009D847
0x18009d838  xor     r8d, r8d
0x18009d83b  lea     rdx, aMigratemembers; "MigrateMembershipData: Failed to alloca"...
0x18009d842  jmp     loc_18009D661
0x18009d847  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18009d84e  jz      loc_18009D5F6
0x18009d854  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009d85b  jz      loc_18009D5F6
0x18009d861  xor     r8d, r8d
0x18009d864  lea     rdx, aMigratemembers; "MigrateMembershipData: Failed to alloca"...
0x18009d86b  jmp     loc_18009D68D
0x18009d870  mov     r14d, r12d
0x18009d873  cmp     r14d, dword ptr [rsp+500h+Data]
0x18009d878  jnb     loc_18009DA4C
0x18009d87e  mov     r9d, r14d
0x18009d881  lea     r8, aGroupD; "Group%d"
0x18009d888  mov     edx, 1Eh; unsigned __int64
0x18009d88d  lea     rcx, [rbp+400h+ValueName]; unsigned __int16 *
0x18009d891  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009d896  test    eax, eax
0x18009d898  js      loc_18009DA41
0x18009d89e  mov     eax, [rsp+500h+cbMaxValueLen]
0x18009d8a2  mov     [rsp+500h+cbData], eax
0x18009d8a6  lea     rax, [rsp+500h+cbData]
0x18009d8ab  mov     qword ptr [rsp+500h+samDesired], rax; lpcbData
0x18009d8b0  mov     [rsp+500h+phkResult], r15; lpData
0x18009d8b5  lea     r9, [rsp+500h+Type]; lpType
0x18009d8ba  xor     r8d, r8d; lpReserved
0x18009d8bd  lea     rdx, [rbp+400h+ValueName]; lpValueName
0x18009d8c1  mov     rcx, [rsp+500h+hKey]; hKey
0x18009d8c6  call    cs:__imp_RegQueryValueExW
0x18009d8cc  test    eax, eax
0x18009d8ce  jnz     loc_18009D9E2
0x18009d8d4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18009d8d8  inc     rcx
0x18009d8db  cmp     [r15+rcx*2], r12w
0x18009d8e0  jnz     short loc_18009D8D8
0x18009d8e2  lea     rcx, ds:2[rcx*2]; unsigned __int64
0x18009d8ea  lea     rdx, [rsp+500h+cbData]; unsigned int *
0x18009d8ef  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18009d8f4  test    eax, eax
0x18009d8f6  js      loc_18009D98B
0x18009d8fc  mov     eax, [rsp+500h+cbData]
0x18009d900  mov     [rsp+500h+samDesired], eax; cbData
0x18009d904  mov     [rsp+500h+phkResult], r15; lpData
0x18009d909  mov     r9d, edi; dwType
0x18009d90c  xor     r8d, r8d; Reserved
0x18009d90f  lea     rdx, [rbp+400h+ValueName]; lpValueName
0x18009d913  mov     rcx, [rbp+400h+var_480]; hKey
0x18009d917  call    cs:__imp_RegSetValueExW
0x18009d91d  test    eax, eax
0x18009d91f  jnz     short loc_18009D929
0x18009d921  add     r14d, edi
0x18009d924  jmp     loc_18009D873
0x18009d929  mov     ebx, eax
0x18009d92b  mov     [rsp+500h+var_4A0], eax
0x18009d92f  mov     edi, r12d
0x18009d932  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18009d939  jz      loc_18009DACD
0x18009d93f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009d946  test    rax, rax
0x18009d949  jz      short loc_18009D965
0x18009d94b  lea     rdx, aMigratemembers_1; "MigrateMembershipData: Failed to write "...
0x18009d952  lea     r8, [rbp+400h+ValueName]
0x18009d956  mov     ecx, 2
0x18009d95b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d960  jmp     loc_18009DACD
0x18009d965  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18009d96c  jz      loc_18009DACD
0x18009d972  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009d979  jz      loc_18009DACD
0x18009d97f  lea     rdx, aMigratemembers_1; "MigrateMembershipData: Failed to write "...
0x18009d986  jmp     loc_18009DA2E
0x18009d98b  call    cs:__imp_GetLastError
0x18009d991  mov     ebx, eax
0x18009d993  mov     [rsp+500h+var_4A0], eax
0x18009d997  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18009d99e  jz      loc_18009DACD
0x18009d9a4  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009d9ab  test    rax, rax
0x18009d9ae  jz      short loc_18009D9BC
0x18009d9b0  lea     rdx, aSizettodwordFa_1; "SizeTToDWord() Failed to convert to DWO"...
0x18009d9b7  jmp     loc_18009DA9E
0x18009d9bc  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18009d9c3  jz      loc_18009DACD
0x18009d9c9  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009d9d0  jz      loc_18009DACD
0x18009d9d6  lea     rdx, aSizettodwordFa_1; "SizeTToDWord() Failed to convert to DWO"...
0x18009d9dd  jmp     loc_18009DAC3
0x18009d9e2  mov     ebx, eax
0x18009d9e4  mov     [rsp+500h+var_4A0], eax
0x18009d9e8  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18009d9ef  jz      loc_18009DACD
0x18009d9f5  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
  ... truncated ...
```
