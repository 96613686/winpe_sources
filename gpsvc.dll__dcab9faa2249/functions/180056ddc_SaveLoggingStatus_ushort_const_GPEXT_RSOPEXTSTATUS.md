# SaveLoggingStatus(ushort const *,_GPEXT *,_RSOPEXTSTATUS *)

- ea: `0x180056ddc`
- end: `0x180057339`
- name: `?SaveLoggingStatus@@YAKPEBGPEAU_GPEXT@@PEAU_RSOPEXTSTATUS@@@Z`
- size: `1373`
- prototype: `unsigned int(const unsigned __int16 *, struct _GPEXT *, struct _RSOPEXTSTATUS *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180058f20`
- `0x18005ce5c`

## callees

- `0x180003770`
- `0x180056ddc`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056e5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057306`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180056e5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057306`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056e26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800572dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800572ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800572fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800572dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800572ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800572fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057029`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800570a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057117`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005718e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057205`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057276`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057029`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800570a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057117`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005718e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057205`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057276`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180056ea2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180056f29`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180056fb0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180056ea2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180056f29`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180056fb0`

## string_xrefs

- `0x180056f1d`: `Extension-List`
- `0x180056ec7`: `SaveLoggingStatus: Failed to create state key with %d`
- `0x180056eed`: `SaveLoggingStatus: Failed to create state key with %d`
- `0x180056f4e`: `SaveLoggingStatus: Failed to create extension key with %d`
- `0x180056f74`: `SaveLoggingStatus: Failed to create extension key with %d`
- `0x180056fd5`: `SaveLoggingStatus: Failed to create CSE key with %d`
- `0x180056ffb`: `SaveLoggingStatus: Failed to create CSE key with %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SaveLoggingStatus(const unsigned __int16 *a1, struct _GPEXT *a2, const BYTE *a3)
{
  DWORD LastError; // ebx
  const wchar_t *v6; // r9
  int v7; // eax
  unsigned int v8; // ebx
  unsigned int v10; // edi
  void (*v11)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v12; // rdx
  HKEY v13; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v16; // [rsp+68h] [rbp-98h]
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  phkResult = 0;
  v13 = 0;
  LastError = GetLastError();
  v16 = LastError;
  v6 = L"Machine";
  if ( a1 )
    v6 = a1;
  v7 = StringCchPrintfW(SubKey, 0x105u, L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\State\\%ws", v6);
  if ( v7 < 0 )
  {
    v8 = (unsigned __int16)v7;
    SetLastError((unsigned __int16)v7);
    return v8;
  }
  v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( !v10 )
  {
    v10 = RegCreateKeyExW(hKey, L"Extension-List", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
    if ( v10 )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_69;
      v11 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"SaveLoggingStatus: Failed to create extension key with %d", v10);
        goto LABEL_69;
      }
      v12 = L"SaveLoggingStatus: Failed to create extension key with %d";
    }
    else
    {
      v10 = RegCreateKeyExW(phkResult, L"{00000000-0000-0000-0000-000000000000}", 0, 0, 0, 0xF003Fu, 0, &v13, 0);
      if ( v10 )
      {
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_69;
        v11 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
        {
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(2u, L"SaveLoggingStatus: Failed to create CSE key with %d", v10);
          goto LABEL_69;
        }
        v12 = L"SaveLoggingStatus: Failed to create CSE key with %d";
      }
      else
      {
        v10 = RegSetValueExW(v13, L"StartTimeLo", 0, 4u, a3, 4u);
        if ( v10 )
        {
          if ( !*(_DWORD *)&g_dwDebugLevel )
            goto LABEL_69;
          v11 = g_lpDebugMsg;
          if ( !g_lpDebugMsg )
          {
            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              RedirectDebugMsg(2u, L"SaveLoggingStatus: Failed to set STARTTIME1 with %d", v10);
            goto LABEL_69;
          }
          v12 = L"SaveLoggingStatus: Failed to set STARTTIME1 with %d";
        }
        else
        {
          v10 = RegSetValueExW(v13, L"StartTimeHi", 0, 4u, a3 + 4, 4u);
          if ( v10 )
          {
            if ( !*(_DWORD *)&g_dwDebugLevel )
              goto LABEL_69;
            v11 = g_lpDebugMsg;
            if ( !g_lpDebugMsg )
            {
              if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                RedirectDebugMsg(2u, L"SaveLoggingStatus: Failed to set STARTTIME2 with %d", v10);
              goto LABEL_69;
            }
            v12 = L"SaveLoggingStatus: Failed to set STARTTIME2 with %d";
          }
          else
          {
            v10 = RegSetValueExW(v13, L"EndTimeLo", 0, 4u, a3 + 8, 4u);
            if ( v10 )
            {
              if ( !*(_DWORD *)&g_dwDebugLevel )
                goto LABEL_69;
              v11 = g_lpDebugMsg;
              if ( !g_lpDebugMsg )
              {
                if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  RedirectDebugMsg(2u, L"SaveLoggingStatus: Failed to set ENDTIME1 with %d", v10);
                goto LABEL_69;
              }
              v12 = L"SaveLoggingStatus: Failed to set ENDTIME1 with %d";
            }
            else
            {
              v10 = RegSetValueExW(v13, L"EndTimeHi", 0, 4u, a3 + 12, 4u);
              if ( v10 )
              {
                if ( !*(_DWORD *)&g_dwDebugLevel )
                  goto LABEL_69;
                v11 = g_lpDebugMsg;
                if ( !g_lpDebugMsg )
                {
                  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    RedirectDebugMsg(2u, L"SaveLoggingStatus: Failed to set ENDTIME2 with %d", v10);
                  goto LABEL_69;
                }
                v12 = L"SaveLoggingStatus: Failed to set ENDTIME2 with %d";
              }
              else
              {
                v10 = RegSetValueExW(v13, L"Status", 0, 4u, a3 + 16, 4u);
                if ( !v10 )
                {
                  v10 = RegSetValueExW(v13, L"LoggingStatus", 0, 4u, a3 + 20, 4u);
                  if ( !v10 || !*(_DWORD *)&g_dwDebugLevel )
                    goto LABEL_69;
                  v11 = g_lpDebugMsg;
                  if ( !g_lpDebugMsg )
                  {
                    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                      RedirectDebugMsg(2u, L"SaveLoggingStatus: Failed to set LOGSTATUS with %d", v10);
                    goto LABEL_69;
                  }
                  v12 = L"SaveLoggingStatus: Failed to set LOGSTATUS with %d";
                  goto LABEL_65;
                }
                if ( !*(_DWORD *)&g_dwDebugLevel )
                  goto LABEL_69;
                v11 = g_lpDebugMsg;
                if ( !g_lpDebugMsg )
                {
                  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    RedirectDebugMsg(2u, L"SaveLoggingStatus: Failed to set STATUS with %d", v10);
                  goto LABEL_69;
                }
                v12 = L"SaveLoggingStatus: Failed to set STATUS with %d";
              }
            }
          }
        }
      }
    }
LABEL_65:
    v11(2u, v12, v10);
    goto LABEL_69;
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    v11 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"SaveLoggingStatus: Failed to create state key with %d", v10);
      goto LABEL_69;
    }
    v12 = L"SaveLoggingStatus: Failed to create state key with %d";
    goto LABEL_65;
  }
LABEL_69:
  if ( v13 )
    RegCloseKey(v13);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  SetLastError(LastError);
  return v10;
}

```

## disassembly

```asm
0x180056ddc  mov     [rsp-8+arg_8], rbx
0x180056de1  mov     [rsp-8+arg_18], rsi
0x180056de6  push    rbp
0x180056de7  push    rdi
0x180056de8  push    r12
0x180056dea  push    r14
0x180056dec  push    r15
0x180056dee  lea     rbp, [rsp-190h]
0x180056df6  sub     rsp, 290h
0x180056dfd  mov     rax, cs:__security_cookie
0x180056e04  xor     rax, rsp
0x180056e07  mov     [rbp+1B0h+var_30], rax
0x180056e0e  mov     rsi, r8
0x180056e11  mov     rdi, rcx
0x180056e14  xor     r15d, r15d
0x180056e17  mov     [rsp+2B0h+hKey], r15
0x180056e1c  mov     [rsp+2B0h+var_258], r15
0x180056e21  mov     [rsp+2B0h+var_260], r15
0x180056e26  call    cs:__imp_GetLastError
0x180056e2c  mov     ebx, eax
0x180056e2e  mov     [rsp+2B0h+var_248], eax
0x180056e32  lea     r9, aMachine; "Machine"
0x180056e39  test    rdi, rdi
0x180056e3c  cmovnz  r9, rdi
0x180056e40  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180056e47  mov     edx, 105h; unsigned __int64
0x180056e4c  lea     rcx, [rsp+2B0h+SubKey]; unsigned __int16 *
0x180056e51  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180056e56  test    eax, eax
0x180056e58  jns     short loc_180056E6C
0x180056e5a  movzx   ebx, ax
0x180056e5d  mov     ecx, ebx; dwErrCode
0x180056e5f  call    cs:__imp_SetLastError
0x180056e65  mov     eax, ebx
0x180056e67  jmp     loc_18005730E
0x180056e6c  mov     [rsp+2B0h+lpdwDisposition], r15; lpdwDisposition
0x180056e71  lea     rax, [rsp+2B0h+hKey]
0x180056e76  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180056e7b  mov     [rsp+2B0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180056e80  mov     r14d, 0F003Fh
0x180056e86  mov     [rsp+2B0h+samDesired], r14d; samDesired
0x180056e8b  mov     [rsp+2B0h+dwOptions], r15d; dwOptions
0x180056e90  xor     r9d, r9d; lpClass
0x180056e93  xor     r8d, r8d; Reserved
0x180056e96  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x180056e9b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180056ea2  call    cs:__imp_RegCreateKeyExW
0x180056ea8  mov     edi, eax
0x180056eaa  test    eax, eax
0x180056eac  jz      short loc_180056EF9
0x180056eae  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180056eb5  jz      loc_1800572D3
0x180056ebb  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180056ec2  test    rax, rax
0x180056ec5  jz      short loc_180056ED3
0x180056ec7  lea     rdx, aSaveloggingsta_2; "SaveLoggingStatus: Failed to create sta"...
0x180056ece  jmp     loc_18005729E
0x180056ed3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180056eda  jz      loc_1800572D3
0x180056ee0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180056ee7  jz      loc_1800572D3
0x180056eed  lea     rdx, aSaveloggingsta_2; "SaveLoggingStatus: Failed to create sta"...
0x180056ef4  jmp     loc_1800572C6
0x180056ef9  mov     [rsp+2B0h+lpdwDisposition], r15; lpdwDisposition
0x180056efe  lea     rax, [rsp+2B0h+var_258]
0x180056f03  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180056f08  mov     [rsp+2B0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180056f0d  mov     [rsp+2B0h+samDesired], r14d; samDesired
0x180056f12  mov     [rsp+2B0h+dwOptions], r15d; dwOptions
0x180056f17  xor     r9d, r9d; lpClass
0x180056f1a  xor     r8d, r8d; Reserved
0x180056f1d  lea     rdx, aExtensionList; "Extension-List"
0x180056f24  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180056f29  call    cs:__imp_RegCreateKeyExW
0x180056f2f  mov     edi, eax
0x180056f31  test    eax, eax
0x180056f33  jz      short loc_180056F80
0x180056f35  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180056f3c  jz      loc_1800572D3
0x180056f42  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180056f49  test    rax, rax
0x180056f4c  jz      short loc_180056F5A
0x180056f4e  lea     rdx, aSaveloggingsta_1; "SaveLoggingStatus: Failed to create ext"...
0x180056f55  jmp     loc_18005729E
0x180056f5a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180056f61  jz      loc_1800572D3
0x180056f67  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180056f6e  jz      loc_1800572D3
0x180056f74  lea     rdx, aSaveloggingsta_1; "SaveLoggingStatus: Failed to create ext"...
0x180056f7b  jmp     loc_1800572C6
0x180056f80  mov     [rsp+2B0h+lpdwDisposition], r15; lpdwDisposition
0x180056f85  lea     rax, [rsp+2B0h+var_260]
0x180056f8a  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180056f8f  mov     [rsp+2B0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180056f94  mov     [rsp+2B0h+samDesired], r14d; samDesired
0x180056f99  mov     [rsp+2B0h+dwOptions], r15d; dwOptions
0x180056f9e  xor     r9d, r9d; lpClass
0x180056fa1  xor     r8d, r8d; Reserved
0x180056fa4  lea     rdx, a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180056fab  mov     rcx, [rsp+2B0h+var_258]; hKey
0x180056fb0  call    cs:__imp_RegCreateKeyExW
0x180056fb6  mov     edi, eax
0x180056fb8  test    eax, eax
0x180056fba  jz      short loc_180057007
0x180056fbc  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180056fc3  jz      loc_1800572D3
0x180056fc9  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180056fd0  test    rax, rax
0x180056fd3  jz      short loc_180056FE1
0x180056fd5  lea     rdx, aSaveloggingsta_7; "SaveLoggingStatus: Failed to create CSE"...
0x180056fdc  jmp     loc_18005729E
0x180056fe1  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180056fe8  jz      loc_1800572D3
0x180056fee  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180056ff5  jz      loc_1800572D3
0x180056ffb  lea     rdx, aSaveloggingsta_7; "SaveLoggingStatus: Failed to create CSE"...
0x180057002  jmp     loc_1800572C6
0x180057007  mov     r12d, 4
0x18005700d  mov     [rsp+2B0h+samDesired], r12d; cbData
0x180057012  mov     qword ptr [rsp+2B0h+dwOptions], rsi; lpData
0x180057017  mov     r9d, r12d; dwType
0x18005701a  xor     r8d, r8d; Reserved
0x18005701d  lea     rdx, aStarttimelo; "StartTimeLo"
0x180057024  mov     rcx, [rsp+2B0h+var_260]; hKey
0x180057029  call    cs:__imp_RegSetValueExW
0x18005702f  mov     edi, eax
0x180057031  test    eax, eax
0x180057033  jz      short loc_180057080
0x180057035  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18005703c  jz      loc_1800572D3
0x180057042  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180057049  test    rax, rax
0x18005704c  jz      short loc_18005705A
0x18005704e  lea     rdx, aSaveloggingsta_5; "SaveLoggingStatus: Failed to set STARTT"...
0x180057055  jmp     loc_18005729E
0x18005705a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180057061  jz      loc_1800572D3
0x180057067  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18005706e  jz      loc_1800572D3
0x180057074  lea     rdx, aSaveloggingsta_5; "SaveLoggingStatus: Failed to set STARTT"...
0x18005707b  jmp     loc_1800572C6
0x180057080  lea     rax, [rsi+4]
0x180057084  mov     [rsp+2B0h+samDesired], r12d; cbData
0x180057089  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x18005708e  mov     r9d, r12d; dwType
0x180057091  xor     r8d, r8d; Reserved
0x180057094  lea     rdx, aStarttimehi; "StartTimeHi"
0x18005709b  mov     rcx, [rsp+2B0h+var_260]; hKey
0x1800570a0  call    cs:__imp_RegSetValueExW
0x1800570a6  mov     edi, eax
0x1800570a8  test    eax, eax
0x1800570aa  jz      short loc_1800570F7
0x1800570ac  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800570b3  jz      loc_1800572D3
0x1800570b9  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800570c0  test    rax, rax
0x1800570c3  jz      short loc_1800570D1
0x1800570c5  lea     rdx, aSaveloggingsta_4; "SaveLoggingStatus: Failed to set STARTT"...
0x1800570cc  jmp     loc_18005729E
0x1800570d1  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800570d8  jz      loc_1800572D3
0x1800570de  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800570e5  jz      loc_1800572D3
0x1800570eb  lea     rdx, aSaveloggingsta_4; "SaveLoggingStatus: Failed to set STARTT"...
0x1800570f2  jmp     loc_1800572C6
0x1800570f7  lea     r14, [rsi+8]
0x1800570fb  mov     [rsp+2B0h+samDesired], r12d; cbData
0x180057100  mov     qword ptr [rsp+2B0h+dwOptions], r14; lpData
0x180057105  mov     r9d, r12d; dwType
0x180057108  xor     r8d, r8d; Reserved
0x18005710b  lea     rdx, aEndtimelo; "EndTimeLo"
0x180057112  mov     rcx, [rsp+2B0h+var_260]; hKey
0x180057117  call    cs:__imp_RegSetValueExW
0x18005711d  mov     edi, eax
0x18005711f  test    eax, eax
0x180057121  jz      short loc_18005716E
0x180057123  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18005712a  jz      loc_1800572D3
0x180057130  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180057137  test    rax, rax
0x18005713a  jz      short loc_180057148
0x18005713c  lea     rdx, aSaveloggingsta_0; "SaveLoggingStatus: Failed to set ENDTIM"...
0x180057143  jmp     loc_18005729E
0x180057148  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18005714f  jz      loc_1800572D3
0x180057155  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18005715c  jz      loc_1800572D3
0x180057162  lea     rdx, aSaveloggingsta_0; "SaveLoggingStatus: Failed to set ENDTIM"...
0x180057169  jmp     loc_1800572C6
0x18005716e  lea     rax, [r14+4]
0x180057172  mov     [rsp+2B0h+samDesired], r12d; cbData
0x180057177  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x18005717c  mov     r9d, r12d; dwType
0x18005717f  xor     r8d, r8d; Reserved
0x180057182  lea     rdx, aEndtimehi; "EndTimeHi"
0x180057189  mov     rcx, [rsp+2B0h+var_260]; hKey
0x18005718e  call    cs:__imp_RegSetValueExW
0x180057194  mov     edi, eax
0x180057196  test    eax, eax
0x180057198  jz      short loc_1800571E5
0x18005719a  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800571a1  jz      loc_1800572D3
0x1800571a7  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800571ae  test    rax, rax
0x1800571b1  jz      short loc_1800571BF
0x1800571b3  lea     rdx, aSaveloggingsta; "SaveLoggingStatus: Failed to set ENDTIM"...
0x1800571ba  jmp     loc_18005729E
0x1800571bf  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800571c6  jz      loc_1800572D3
0x1800571cc  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800571d3  jz      loc_1800572D3
0x1800571d9  lea     rdx, aSaveloggingsta; "SaveLoggingStatus: Failed to set ENDTIM"...
0x1800571e0  jmp     loc_1800572C6
0x1800571e5  lea     rax, [rsi+10h]
0x1800571e9  mov     [rsp+2B0h+samDesired], r12d; cbData
0x1800571ee  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x1800571f3  mov     r9d, r12d; dwType
0x1800571f6  xor     r8d, r8d; Reserved
0x1800571f9  lea     rdx, aStatus_0; "Status"
0x180057200  mov     rcx, [rsp+2B0h+var_260]; hKey
0x180057205  call    cs:__imp_RegSetValueExW
0x18005720b  mov     edi, eax
0x18005720d  test    eax, eax
0x18005720f  jz      short loc_180057256
0x180057211  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180057218  jz      loc_1800572D3
0x18005721e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180057225  test    rax, rax
0x180057228  jz      short loc_180057233
0x18005722a  lea     rdx, aSaveloggingsta_6; "SaveLoggingStatus: Failed to set STATUS"...
0x180057231  jmp     short loc_18005729E
0x180057233  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18005723a  jz      loc_1800572D3
0x180057240  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180057247  jz      loc_1800572D3
0x18005724d  lea     rdx, aSaveloggingsta_6; "SaveLoggingStatus: Failed to set STATUS"...
0x180057254  jmp     short loc_1800572C6
0x180057256  lea     rax, [rsi+14h]
0x18005725a  mov     [rsp+2B0h+samDesired], r12d; cbData
0x18005725f  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x180057264  mov     r9d, r12d; dwType
0x180057267  xor     r8d, r8d; Reserved
0x18005726a  lea     rdx, aLoggingstatus_0; "LoggingStatus"
0x180057271  mov     rcx, [rsp+2B0h+var_260]; hKey
0x180057276  call    cs:__imp_RegSetValueExW
0x18005727c  mov     edi, eax
0x18005727e  test    eax, eax
0x180057280  jz      short loc_1800572D3
0x180057282  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180057289  jz      short loc_1800572D3
0x18005728b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180057292  test    rax, rax
0x180057295  jz      short loc_1800572AD
0x180057297  lea     rdx, aSaveloggingsta_3; "SaveLoggingStatus: Failed to set LOGSTA"...
0x18005729e  mov     r8d, edi
0x1800572a1  mov     ecx, 2
0x1800572a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800572ab  jmp     short loc_1800572D3
0x1800572ad  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800572b4  jz      short loc_1800572D3
0x1800572b6  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800572bd  jz      short loc_1800572D3
0x1800572bf  lea     rdx, aSaveloggingsta_3; "SaveLoggingStatus: Failed to set LOGSTA"...
0x1800572c6  mov     r8d, edi
0x1800572c9  mov     ecx, 2; unsigned int
0x1800572ce  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800572d3  mov     rcx, [rsp+2B0h+var_260]; hKey
0x1800572d8  test    rcx, rcx
0x1800572db  jz      short loc_1800572E3
0x1800572dd  call    cs:__imp_RegCloseKey
0x1800572e3  mov     rcx, [rsp+2B0h+var_258]; hKey
0x1800572e8  test    rcx, rcx
0x1800572eb  jz      short loc_1800572F3
0x1800572ed  call    cs:__imp_RegCloseKey
0x1800572f3  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800572f8  test    rcx, rcx
0x1800572fb  jz      short loc_180057304
0x1800572fd  call    cs:__imp_RegCloseKey
0x180057303  nop
0x180057304  mov     ecx, ebx; dwErrCode
0x180057306  call    cs:__imp_SetLastError
0x18005730c  mov     eax, edi
0x18005730e  mov     rcx, [rbp+1B0h+var_30]
0x180057315  xor     rcx, rsp; StackCookie
0x180057318  call    __security_check_cookie
0x18005731d  lea     r11, [rsp+2B0h+var_20]
0x180057325  mov     rbx, [r11+38h]
0x180057329  mov     rsi, [r11+48h]
0x18005732d  mov     rsp, r11
0x180057330  pop     r15
0x180057332  pop     r14
0x180057334  pop     r12
0x180057336  pop     rdi
0x180057337  pop     rbp
0x180057338  retn
```
