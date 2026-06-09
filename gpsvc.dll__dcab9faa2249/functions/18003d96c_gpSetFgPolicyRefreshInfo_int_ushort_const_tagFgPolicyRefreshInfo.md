# gpSetFgPolicyRefreshInfo(int,ushort const *,_tagFgPolicyRefreshInfo)

- ea: `0x18003d96c`
- end: `0x18003df2e`
- name: `?gpSetFgPolicyRefreshInfo@@YAKHPEBGU_tagFgPolicyRefreshInfo@@@Z`
- size: `1474`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180034870`
- `0x180058f20`
- `0x18005ce5c`
- `0x1800689e0`
- `0x1800b98e0`

## callees

- `0x180003770`
- `0x18003d8d0`
- `0x18003d96c`
- `0x1800686a4`
- `0x180074884`
- `0x180075ec0`
- `0x18007d320`
- `0x18007de08`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dbaf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003defc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dbaf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003defc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dae0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003dc96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003dda8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003dc96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003dda8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dc1a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dc59`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dd69`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dd96`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dc1a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dc59`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dd69`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dd96`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003dbdb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003dd3c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003dbdb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003dd3c`

## string_xrefs

- `0x18003da0f`: `gpSetFgPolicyRefreshInfo (bPrev: %ld, szUserSid: %s, info.mode: %s)`
- `0x18003da61`: `gpSetFgPolicyRefreshInfo (bPrev: %ld, szUserSid: %s, info.mode: %s)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall gpSetFgPolicyRefreshInfo(unsigned int a1, const unsigned __int16 *a2, unsigned __int64 a3)
{
  unsigned __int64 v5; // r8
  const wchar_t *v6; // r9
  const wchar_t *v7; // r9
  DWORD LastError; // ebx
  __int64 v9; // r8
  WCHAR *v10; // rax
  signed int v11; // edx
  __int64 v12; // r9
  __int64 v13; // rcx
  const wchar_t *v14; // r8
  __int64 v15; // rdx
  WCHAR *v16; // rax
  wchar_t v17; // r9
  WCHAR *v18; // rcx
  unsigned int v19; // ebx
  unsigned int v21; // edi
  const WCHAR *v22; // rdx
  const WCHAR *v23; // rdx
  HKEY v24; // rcx
  int v25; // eax
  const wchar_t *v26; // r11
  const wchar_t *v27; // rsi
  const wchar_t *v28; // r9
  const wchar_t *v29; // r8
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v32; // [rsp+50h] [rbp-B0h]
  WCHAR SubKey[62]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v34[404]; // [rsp+DCh] [rbp-24h] BYREF

  *(_QWORD *)Data = a3;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      v5 = HIDWORD(a3);
      v6 = a2;
      if ( !a2 )
        v6 = L"Machine";
      g_lpDebugMsg(
        4u,
        L"gpSetFgPolicyRefreshInfo (bPrev: %ld, szUserSid: %s, info.mode: %s)",
        a1,
        v6,
        (&g_szModes)[(int)v5 % 3uLL]);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v7 = a2;
      if ( !a2 )
        v7 = L"Machine";
      RedirectDebugMsg(
        4u,
        L"gpSetFgPolicyRefreshInfo (bPrev: %ld, szUserSid: %s, info.mode: %s)",
        a1,
        v7,
        (&g_szModes)[*(int *)&Data[4] % 3uLL]);
    }
  }
  wcscpy(SubKey, L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Poli\\State\\");
  memset_0(v34, 0, 0x18Eu);
  hKey = 0;
  LastError = GetLastError();
  v32 = LastError;
  if ( a2 )
  {
    v11 = StringCchCatW(SubKey, 0x105u, a2);
  }
  else
  {
    v9 = 261;
    v10 = SubKey;
    do
    {
      if ( !*v10 )
        break;
      ++v10;
      --v9;
    }
    while ( v9 );
    v11 = v9 == 0 ? 0x80070057 : 0;
    v12 = (261 - v9) & -(__int64)(v9 != 0);
    if ( v9 )
    {
      v13 = 2147483646;
      v14 = L"Machine";
      v15 = 261 - v12;
      v16 = &SubKey[v12];
      if ( v12 != 261 )
      {
        do
        {
          if ( !v13 )
            break;
          v17 = *v14;
          if ( !*v14 )
            break;
          ++v14;
          *v16++ = v17;
          --v13;
          --v15;
        }
        while ( v15 );
      }
      v18 = v16 - 1;
      if ( v15 )
        v18 = v16;
      *v18 = 0;
      v11 = v15 == 0 ? 0x8007007A : 0;
    }
  }
  if ( v11 >= 0 )
  {
    v21 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, &hKey);
    if ( !v21 )
    {
      v22 = L"PrevRefreshMode";
      if ( !a1 )
        v22 = L"NextRefreshMode";
      v21 = RegSetValueExW(hKey, v22, 0, 4u, &Data[4], 4u);
      if ( !v21 )
      {
        v23 = L"PrevRefreshReason";
        if ( !a1 )
          v23 = L"NextRefreshReason";
        v21 = RegSetValueExW(hKey, v23, 0, 4u, Data, 4u);
        if ( !v21 && !a1 && a2 && ((unsigned int)IsTSAsyncLogonPolicyEnabled(v24) || (unsigned int)IsVDIPooled()) )
        {
          RegCloseKey(hKey);
          hKey = 0;
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"gpSetFgPolicyRefreshInfo: Switching to user hive.");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"gpSetFgPolicyRefreshInfo: Switching to user hive.");
            }
          }
          v25 = StringCchPrintfW(
                  SubKey,
                  0x105u,
                  L"%ls\\%ls",
                  a2,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\State\\");
          if ( v25 >= 0 )
          {
            v21 = RegOpenKeyExW(HKEY_USERS, SubKey, 0, 0xF003Fu, &hKey);
            if ( !v21 )
            {
              v21 = RegSetValueExW(hKey, L"NextRefreshMode", 0, 4u, &Data[4], 4u);
              if ( !v21 )
                v21 = RegSetValueExW(hKey, L"NextRefreshReason", 0, 4u, Data, 4u);
            }
          }
          else
          {
            LastError = (unsigned __int16)v25;
            v21 = (unsigned __int16)v25;
            v32 = (unsigned __int16)v25;
          }
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( !v21 && *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        v26 = L"User";
        if ( !a2 )
          v26 = L"Machine";
        v27 = L"Previous";
        if ( !a1 )
          v27 = L"Next";
        g_lpDebugMsg(
          4u,
          L"SetFgRefreshInfo: %s %s Fg policy %s, Reason: %s.",
          v27,
          v26,
          (&g_szModes)[*(int *)&Data[4] % 3uLL],
          (&g_szReasons)[Data[0] & 7]);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v28 = L"User";
        if ( !a2 )
          v28 = L"Machine";
        v29 = L"Previous";
        if ( !a1 )
          v29 = L"Next";
        RedirectDebugMsg(
          4u,
          L"SetFgRefreshInfo: %s %s Fg policy %s, Reason: %s.",
          v29,
          v28,
          (&g_szModes)[*(int *)&Data[4] % 3uLL],
          (&g_szReasons)[Data[0] & 7]);
      }
    }
    SetLastError(LastError);
    return v21;
  }
  else
  {
    v19 = (unsigned __int16)v11;
    SetLastError((unsigned __int16)v11);
    return v19;
  }
}

```

## disassembly

```asm
0x18003d96c  mov     [rsp-8+arg_18], rbx
0x18003d971  push    rbp
0x18003d972  push    rsi
0x18003d973  push    rdi
0x18003d974  push    r12
0x18003d976  push    r13
0x18003d978  push    r14
0x18003d97a  push    r15
0x18003d97c  lea     rbp, [rsp-180h]
0x18003d984  sub     rsp, 280h
0x18003d98b  mov     rax, cs:__security_cookie
0x18003d992  xor     rax, rsp
0x18003d995  mov     [rbp+1B0h+var_40], rax
0x18003d99c  mov     r14, rdx
0x18003d99f  mov     r15d, ecx
0x18003d9a2  mov     qword ptr [rsp+2B0h+Data], r8
0x18003d9a7  mov     rax, 0AAAAAAAAAAAAAAABh
0x18003d9b1  lea     r11, __ImageBase
0x18003d9b8  lea     rdi, aMachine; "Machine"
0x18003d9bf  mov     r13d, 4
0x18003d9c5  xor     r12d, r12d
0x18003d9c8  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18003d9cf  jz      loc_18003DA70
0x18003d9d5  mov     r10, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003d9dc  test    r10, r10
0x18003d9df  jz      short loc_18003DA23
0x18003d9e1  shr     r8, 20h
0x18003d9e5  movsxd  rcx, r8d
0x18003d9e8  mul     rcx
0x18003d9eb  shr     rdx, 1
0x18003d9ee  lea     rax, [rdx+rdx*2]
0x18003d9f2  sub     rcx, rax
0x18003d9f5  mov     r9, r14
0x18003d9f8  test    r14, r14
0x18003d9fb  cmovz   r9, rdi
0x18003d9ff  mov     rax, ds:rva ?g_szModes@@3PAPEAGA[r11+rcx*8]; ushort * near * g_szModes ...
0x18003da07  mov     [rsp+2B0h+phkResult], rax
0x18003da0c  mov     r8d, r15d
0x18003da0f  lea     rdx, aGpsetfgpolicyr; "gpSetFgPolicyRefreshInfo (bPrev: %ld, s"...
0x18003da16  mov     ecx, r13d
0x18003da19  mov     rax, r10
0x18003da1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da21  jmp     short loc_18003DA70
0x18003da23  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18003da2a  jz      short loc_18003DA70
0x18003da2c  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003da33  jz      short loc_18003DA70
0x18003da35  movsxd  rcx, dword ptr [rsp+2B0h+Data+4]
0x18003da3a  mul     rcx
0x18003da3d  shr     rdx, 1
0x18003da40  lea     rax, [rdx+rdx*2]
0x18003da44  sub     rcx, rax
0x18003da47  mov     r9, r14
0x18003da4a  test    r14, r14
0x18003da4d  cmovz   r9, rdi
0x18003da51  mov     rax, ds:rva ?g_szModes@@3PAPEAGA[r11+rcx*8]; ushort * near * g_szModes ...
0x18003da59  mov     [rsp+2B0h+phkResult], rax
0x18003da5e  mov     r8d, r15d
0x18003da61  lea     rdx, aGpsetfgpolicyr; "gpSetFgPolicyRefreshInfo (bPrev: %ld, s"...
0x18003da68  mov     ecx, r13d; unsigned int
0x18003da6b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003da70  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003da77  movaps  xmmword ptr [rsp+2B0h+SubKey], xmm0
0x18003da7c  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_4+10h; "\\Microsoft\\Windows\\CurrentVersion\\G"...
0x18003da83  movaps  [rsp+2B0h+var_240], xmm1
0x18003da88  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_4+20h; "ft\\Windows\\CurrentVersion\\Group Poli"...
0x18003da8f  movaps  [rbp+1B0h+var_230], xmm0
0x18003da93  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_4+30h; "ws\\CurrentVersion\\Group Policy\\State"...
0x18003da9a  movaps  [rbp+1B0h+var_220], xmm1
0x18003da9e  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_4+40h; "ntVersion\\Group Policy\\State\\"
0x18003daa5  movaps  [rbp+1B0h+var_210], xmm0
0x18003daa9  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_4+50h; "n\\Group Policy\\State\\"
0x18003dab0  movaps  [rbp+1B0h+var_200], xmm1
0x18003dab4  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_4+60h; "Policy\\State\\"
0x18003dabb  movaps  [rbp+1B0h+var_1F0], xmm0
0x18003dabf  movups  xmm1, xmmword ptr cs:aSoftwareMicros_4+6Ch; "\\State\\"
0x18003dac6  movups  [rbp+1B0h+var_1F0+0Ch], xmm1
0x18003daca  xor     edx, edx; Val
0x18003dacc  mov     r8d, 18Eh; Size
0x18003dad2  lea     rcx, [rbp+1B0h+var_1D4]; void *
0x18003dad6  call    memset_0
0x18003dadb  mov     [rsp+2B0h+hKey], r12
0x18003dae0  call    cs:__imp_GetLastError
0x18003dae6  mov     ebx, eax
0x18003dae8  mov     [rsp+2B0h+var_260], eax
0x18003daec  mov     esi, 105h
0x18003daf1  test    r14, r14
0x18003daf4  jnz     loc_18003DB94
0x18003dafa  mov     r8d, esi
0x18003dafd  lea     rax, [rsp+2B0h+SubKey]
0x18003db02  cmp     [rax], r12w
0x18003db06  jz      short loc_18003DB12
0x18003db08  add     rax, 2
0x18003db0c  sub     r8, 1
0x18003db10  jnz     short loc_18003DB02
0x18003db12  mov     rax, r8
0x18003db15  neg     rax
0x18003db18  sbb     edx, edx
0x18003db1a  not     edx
0x18003db1c  and     edx, 80070057h
0x18003db22  mov     rax, r8
0x18003db25  mov     rcx, rsi
0x18003db28  sub     rcx, r8
0x18003db2b  neg     rax
0x18003db2e  sbb     r9, r9
0x18003db31  and     r9, rcx
0x18003db34  test    r8, r8
0x18003db37  jz      short loc_18003DBA6
0x18003db39  mov     ecx, 7FFFFFFEh
0x18003db3e  mov     r8, rdi
0x18003db41  mov     rdx, rsi
0x18003db44  sub     rdx, r9
0x18003db47  lea     rax, [rsp+2B0h+SubKey]
0x18003db4c  lea     rax, [rax+r9*2]
0x18003db50  jz      short loc_18003DB76
0x18003db52  test    rcx, rcx
0x18003db55  jz      short loc_18003DB76
0x18003db57  movzx   r9d, word ptr [r8]
0x18003db5b  test    r9w, r9w
0x18003db5f  jz      short loc_18003DB76
0x18003db61  add     r8, 2
0x18003db65  mov     [rax], r9w
0x18003db69  add     rax, 2
0x18003db6d  dec     rcx
0x18003db70  sub     rdx, 1
0x18003db74  jnz     short loc_18003DB52
0x18003db76  lea     rcx, [rax-2]
0x18003db7a  test    rdx, rdx
0x18003db7d  cmovnz  rcx, rax
0x18003db81  mov     [rcx], r12w
0x18003db85  neg     rdx
0x18003db88  sbb     edx, edx
0x18003db8a  not     edx
0x18003db8c  and     edx, 8007007Ah
0x18003db92  jmp     short loc_18003DBA6
0x18003db94  mov     r8, r14; unsigned __int16 *
0x18003db97  mov     rdx, rsi; unsigned __int64
0x18003db9a  lea     rcx, [rsp+2B0h+SubKey]; unsigned __int16 *
0x18003db9f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003dba4  mov     edx, eax
0x18003dba6  test    edx, edx
0x18003dba8  jns     short loc_18003DBBC
0x18003dbaa  movzx   ebx, dx
0x18003dbad  mov     ecx, ebx; dwErrCode
0x18003dbaf  call    cs:__imp_SetLastError
0x18003dbb5  mov     eax, ebx
0x18003dbb7  jmp     loc_18003DF04
0x18003dbbc  lea     rax, [rsp+2B0h+hKey]
0x18003dbc1  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18003dbc6  mov     r9d, 0F003Fh; samDesired
0x18003dbcc  xor     r8d, r8d; ulOptions
0x18003dbcf  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x18003dbd4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003dbdb  call    cs:__imp_RegOpenKeyExW
0x18003dbe1  mov     edi, eax
0x18003dbe3  test    eax, eax
0x18003dbe5  jnz     loc_18003DD9E
0x18003dbeb  lea     rax, aNextrefreshmod; "NextRefreshMode"
0x18003dbf2  lea     rdx, aPrevrefreshmod; "PrevRefreshMode"
0x18003dbf9  test    r15d, r15d
0x18003dbfc  cmovz   rdx, rax; lpValueName
0x18003dc00  mov     [rsp+2B0h+cbData], r13d; cbData
0x18003dc05  lea     rax, [rsp+2B0h+Data+4]
0x18003dc0a  mov     [rsp+2B0h+phkResult], rax; lpData
0x18003dc0f  mov     r9d, r13d; dwType
0x18003dc12  xor     r8d, r8d; Reserved
0x18003dc15  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18003dc1a  call    cs:__imp_RegSetValueExW
0x18003dc20  mov     edi, eax
0x18003dc22  test    eax, eax
0x18003dc24  jnz     loc_18003DD9E
0x18003dc2a  lea     rax, aNextrefreshrea; "NextRefreshReason"
0x18003dc31  lea     rdx, aPrevrefreshrea; "PrevRefreshReason"
0x18003dc38  test    r15d, r15d
0x18003dc3b  cmovz   rdx, rax; lpValueName
0x18003dc3f  mov     [rsp+2B0h+cbData], r13d; cbData
0x18003dc44  lea     rax, [rsp+2B0h+Data]
0x18003dc49  mov     [rsp+2B0h+phkResult], rax; lpData
0x18003dc4e  mov     r9d, r13d; dwType
0x18003dc51  xor     r8d, r8d; Reserved
0x18003dc54  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18003dc59  call    cs:__imp_RegSetValueExW
0x18003dc5f  mov     edi, eax
0x18003dc61  test    eax, eax
0x18003dc63  jnz     loc_18003DD9E
0x18003dc69  test    r15d, r15d
0x18003dc6c  jnz     loc_18003DD9E
0x18003dc72  test    r14, r14
0x18003dc75  jz      loc_18003DD9E
0x18003dc7b  call    ?IsTSAsyncLogonPolicyEnabled@@YAHPEAUHKEY__@@@Z; IsTSAsyncLogonPolicyEnabled(HKEY__ *)
0x18003dc80  test    eax, eax
0x18003dc82  jnz     short loc_18003DC91
0x18003dc84  call    ?IsVDIPooled@@YAHXZ; IsVDIPooled(void)
0x18003dc89  test    eax, eax
0x18003dc8b  jz      loc_18003DD9E
0x18003dc91  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18003dc96  call    cs:__imp_RegCloseKey
0x18003dc9c  mov     [rsp+2B0h+hKey], r12
0x18003dca1  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18003dca8  jz      short loc_18003DCE8
0x18003dcaa  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003dcb1  test    rax, rax
0x18003dcb4  jz      short loc_18003DCC7
0x18003dcb6  lea     rdx, aGpsetfgpolicyr_0; "gpSetFgPolicyRefreshInfo: Switching to "...
0x18003dcbd  mov     ecx, r13d
0x18003dcc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dcc5  jmp     short loc_18003DCE8
0x18003dcc7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18003dcce  jz      short loc_18003DCE8
0x18003dcd0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003dcd7  jz      short loc_18003DCE8
0x18003dcd9  lea     rdx, aGpsetfgpolicyr_0; "gpSetFgPolicyRefreshInfo: Switching to "...
0x18003dce0  mov     ecx, r13d; unsigned int
0x18003dce3  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003dce8  lea     rax, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003dcef  mov     [rsp+2B0h+phkResult], rax
0x18003dcf4  mov     r9, r14
0x18003dcf7  lea     r8, aLsLs; "%ls\\%ls"
0x18003dcfe  mov     rdx, rsi; unsigned __int64
0x18003dd01  lea     rcx, [rsp+2B0h+SubKey]; unsigned __int16 *
0x18003dd06  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003dd0b  test    eax, eax
0x18003dd0d  jns     short loc_18003DD1D
0x18003dd0f  movzx   ebx, ax
0x18003dd12  mov     edi, ebx
0x18003dd14  mov     [rsp+2B0h+var_260], ebx
0x18003dd18  jmp     loc_18003DD9E
0x18003dd1d  lea     rax, [rsp+2B0h+hKey]
0x18003dd22  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18003dd27  mov     r9d, 0F003Fh; samDesired
0x18003dd2d  xor     r8d, r8d; ulOptions
0x18003dd30  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x18003dd35  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003dd3c  call    cs:__imp_RegOpenKeyExW
0x18003dd42  mov     edi, eax
0x18003dd44  test    eax, eax
0x18003dd46  jnz     short loc_18003DD9E
0x18003dd48  mov     [rsp+2B0h+cbData], r13d; cbData
0x18003dd4d  lea     rax, [rsp+2B0h+Data+4]
0x18003dd52  mov     [rsp+2B0h+phkResult], rax; lpData
0x18003dd57  mov     r9d, r13d; dwType
0x18003dd5a  xor     r8d, r8d; Reserved
0x18003dd5d  lea     rdx, aNextrefreshmod; "NextRefreshMode"
0x18003dd64  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18003dd69  call    cs:__imp_RegSetValueExW
0x18003dd6f  mov     edi, eax
0x18003dd71  test    eax, eax
0x18003dd73  jnz     short loc_18003DD9E
0x18003dd75  mov     [rsp+2B0h+cbData], r13d; cbData
0x18003dd7a  lea     rax, [rsp+2B0h+Data]
0x18003dd7f  mov     [rsp+2B0h+phkResult], rax; lpData
0x18003dd84  mov     r9d, r13d; dwType
0x18003dd87  xor     r8d, r8d; Reserved
0x18003dd8a  lea     rdx, aNextrefreshrea; "NextRefreshReason"
0x18003dd91  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18003dd96  call    cs:__imp_RegSetValueExW
0x18003dd9c  mov     edi, eax
0x18003dd9e  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18003dda3  test    rcx, rcx
0x18003dda6  jz      short loc_18003DDAE
0x18003dda8  call    cs:__imp_RegCloseKey
0x18003ddae  test    edi, edi
0x18003ddb0  jnz     loc_18003DEFA
0x18003ddb6  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18003ddbd  jz      loc_18003DEFA
0x18003ddc3  mov     r10, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003ddca  test    r10, r10
0x18003ddcd  jz      loc_18003DE60
0x18003ddd3  mov     r9, qword ptr [rsp+2B0h+Data]
0x18003ddd8  and     r9d, 7
0x18003dddc  movsxd  r8, dword ptr [rsp+2B0h+Data+4]
0x18003dde1  mov     rax, 0AAAAAAAAAAAAAAABh
0x18003ddeb  mul     r8
0x18003ddee  shr     rdx, 1
0x18003ddf1  lea     rax, [rdx+rdx*2]
0x18003ddf5  sub     r8, rax
0x18003ddf8  lea     r11, aUser; "User"
0x18003ddff  test    r14, r14
0x18003de02  lea     rax, aMachine; "Machine"
0x18003de09  cmovz   r11, rax
0x18003de0d  lea     rax, aNext; "Next"
0x18003de14  lea     rsi, aPrevious; "Previous"
0x18003de1b  test    r15d, r15d
0x18003de1e  cmovz   rsi, rax
0x18003de22  lea     r14, __ImageBase
0x18003de29  mov     rdx, ds:rva ?g_szReasons@@3PAPEAGA[r14+r9*8]; ushort * near * g_szReasons ...
0x18003de31  mov     qword ptr [rsp+2B0h+cbData], rdx
0x18003de36  mov     rdx, ds:rva ?g_szModes@@3PAPEAGA[r14+r8*8]; ushort * near * g_szModes ...
0x18003de3e  mov     [rsp+2B0h+phkResult], rdx
0x18003de43  mov     r9, r11
0x18003de46  mov     r8, rsi
0x18003de49  lea     rdx, aSetfgrefreshin; "SetFgRefreshInfo: %s %s Fg policy %s, R"...
0x18003de50  mov     ecx, r13d
0x18003de53  mov     rax, r10
0x18003de56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de5b  jmp     loc_18003DEFA
0x18003de60  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18003de67  jz      loc_18003DEFA
0x18003de6d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003de74  jz      loc_18003DEFA
  ... truncated ...
```
