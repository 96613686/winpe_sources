# RedirectionThread(_REDIRECT_INFO *)

- ea: `0x18009def0`
- end: `0x18009e36a`
- name: `?RedirectionThread@@YAHPEAU_REDIRECT_INFO@@@Z`
- size: `1146`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180008520`
- `0x180008560`
- `0x180011f00`
- `0x18003378c`
- `0x18003e984`
- `0x18003ea2c`
- `0x180043064`
- `0x180046650`
- `0x180047330`
- `0x180054638`
- `0x18009def0`
- `0x18009e370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18009e0b0`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18009e0b0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009e033`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009e033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e066`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e073`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e0d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e14f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e24c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e26a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e066`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e073`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e0d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e14f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e24c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e26a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009e1f2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009e1f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e200`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e2f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e310`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e200`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e2f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e310`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x18009e2c6`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x18009e2c6`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18009e33c`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18009e33c`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x18009e009`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x18009e009`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x18009e05a`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x18009e141`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x18009e05a`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x18009e141`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x18009e12d`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x18009e12d`
- `SPOOLSS!DllFreeSplStr` at `0x18009e2cf`
- `SPOOLSS!DllFreeSplStr` at `0x18009e2cf`
- `SPOOLSS!DllFreeSplMem` at `0x18009e20e`
- `SPOOLSS!DllFreeSplMem` at `0x18009e20e`
- `SPOOLSS!DllAllocSplMem` at `0x18009e18c`
- `SPOOLSS!DllAllocSplMem` at `0x18009e18c`

## string_xrefs

- `0x18009e083`: `RedirectionThread`
- `0x18009e0e1`: `RedirectionThread`
- `0x18009e224`: `RedirectionThread`
- `0x18009e239`: `RedirectionThread`
- `0x18009e25c`: `RedirectionThread`
- `0x18009e281`: `RedirectionThread`
- `0x18009e27a`: `CreateNamedPipe failed for %ws. Error %d`
- `0x18009e21d`: `Failed to create reader thread.  Error %d`
- `0x18009e255`: `CreateEvent failed. Error %d`

## pseudocode

```c
__int64 __fastcall RedirectionThread(HANDLE *Parameter)
{
  struct _INIPORT *v2; // rcx
  unsigned int v3; // r8d
  const WCHAR *v4; // r13
  __int64 v5; // rcx
  __int64 i; // rcx
  __int64 v8; // rax
  unsigned int v9; // ebx
  struct _SECURITY_ATTRIBUTES *lpSecurityAttributes; // r12
  HANDLE NamedPipeW; // rsi
  HANDLE EventW; // rax
  __int64 v13; // rdi
  DWORD v14; // eax
  int v15; // r15d
  DWORD v16; // eax
  unsigned int v17; // ecx
  DWORD v18; // eax
  __int64 v19; // rbx
  _DWORD *v20; // rdi
  unsigned int v21; // ecx
  HANDLE v22; // rdi
  DWORD v23; // eax
  _QWORD *v24; // rax
  _QWORD *v25; // rsi
  HANDLE v26; // rax
  DWORD v27; // eax
  DWORD LastError; // eax
  DWORD v29; // eax
  __int64 v30; // rcx
  __int64 j; // rbx
  HANDLE v32; // rcx
  HANDLE v33; // rcx
  DWORD ThreadId; // [rsp+40h] [rbp-C0h] BYREF
  LPSECURITY_ATTRIBUTES v35; // [rsp+48h] [rbp-B8h] BYREF
  struct _SECURITY_ATTRIBUTES v36; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hNamedPipe[16]; // [rsp+70h] [rbp-90h] BYREF
  HANDLE Handles[52]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR Name[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR DeviceName[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  memset(&v36, 0, sizeof(v36));
  v35 = 0;
  memset_0(Handles, 0, 0x58u);
  v2 = (struct _INIPORT *)*Parameter;
  ThreadId = 0;
  v4 = SetupDosDev(v2, Name, v3, &v36, &v35);
  if ( v4 )
  {
    memset_0(hNamedPipe, -1, 0x50u);
    memset_0(Handles, 0, 0x50u);
    for ( i = 0; i != 10; ++i )
    {
      v8 = i;
      Handles[4 * v8 + 15] = 0;
    }
    v9 = 0;
    lpSecurityAttributes = v35;
    Handles[10] = Parameter[1];
    while ( 1 )
    {
      *((_DWORD *)&hNamedPipe[10] + v9) = 0;
      NamedPipeW = CreateNamedPipeW(Name, 0x40000003u, 0, 0xFFu, 0x1000u, 0x10000u, 0, lpSecurityAttributes);
      hNamedPipe[v9] = NamedPipeW;
      if ( NamedPipeW == (HANDLE)-1LL )
        break;
      EventW = CreateEventW(0, 0, 0, 0);
      v13 = 4LL * v9;
      Handles[v9] = EventW;
      Handles[v13 + 15] = EventW;
      if ( !EventW )
      {
        LastError = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceError("RedirectionThread", L"CreateEvent failed. Error %d", LastError);
        goto LABEL_37;
      }
      if ( !ConnectNamedPipe(NamedPipeW, (LPOVERLAPPED)&Handles[v13 + 12]) )
      {
        if ( GetLastError() != 997 )
        {
          v18 = GetLastError();
          LocalSpoolerTelemetry::WriteDbgTraceError("RedirectionThread", L"ConnectNamedPipe failed. Error %d", v18);
          goto LABEL_37;
        }
        v14 = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceInfo("RedirectionThread", L"ConnectNamedPipe %d has IO pending.", v14);
      }
      if ( ++v9 >= 0xA )
      {
        v15 = 0;
        while ( 1 )
        {
          while ( 1 )
          {
            while ( 1 )
            {
              while ( 1 )
              {
                v16 = WaitForMultipleObjectsEx(0xBu, Handles, 0, 0xFFFFFFFF, 0);
                if ( v16 < 0xA )
                  break;
                v17 = 0;
                while ( !*((_DWORD *)&hNamedPipe[10] + v17) )
                {
                  if ( ++v17 >= 0xA )
                    goto LABEL_37;
                }
                v15 = 1;
              }
              v19 = v16;
              v20 = (_DWORD *)&hNamedPipe[10] + v16;
              if ( *v20 )
                break;
              if ( !v15 )
              {
                v24 = (_QWORD *)DllAllocSplMem(1064);
                v25 = v24;
                if ( v24 )
                {
                  *v24 = hNamedPipe[v19];
                  v24[130] = 0;
                  *v20 = 1;
                  v24[129] = &Handles[4 * v19 + 12];
                  v24[132] = *Parameter;
                  v26 = CreateThread(0, 0x8000u, ReadThread, v24, 0, &ThreadId);
                  if ( v26 )
                  {
                    CloseHandle(v26);
                  }
                  else
                  {
                    *v20 = 0;
                    DllFreeSplMem(v25);
                    v27 = GetLastError();
                    LocalSpoolerTelemetry::WriteDbgTraceWarning(
                      "RedirectionThread",
                      L"Failed to create reader thread.  Error %d",
                      v27);
                  }
                }
                else
                {
                  LocalSpoolerTelemetry::WriteDbgTraceWarning(
                    "RedirectionThread",
                    L"Failed to allocate memory for transmission structure.");
                }
              }
            }
            *v20 = 0;
            if ( v15 )
              break;
            v22 = hNamedPipe[v16];
            DisconnectNamedPipe(v22);
            if ( !ConnectNamedPipe(v22, (LPOVERLAPPED)&Handles[4 * v19 + 12]) )
            {
              v23 = GetLastError();
              if ( v23 != 997 )
                LocalSpoolerTelemetry::WriteDbgTraceError(
                  "ReconnectNamedPipe",
                  L"Failed to re-connect named pipe %p.  Error %d",
                  v22,
                  v23);
            }
          }
          v21 = 0;
          while ( !*((_DWORD *)&hNamedPipe[10] + v21) )
          {
            if ( ++v21 >= 0xA )
              goto LABEL_37;
          }
        }
      }
    }
    v29 = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "RedirectionThread",
      L"CreateNamedPipe failed for %ws. Error %d",
      Name,
      v29);
LABEL_37:
    if ( (int)StringCchCopyW(DeviceName, 0x104u, *((const unsigned __int16 **)*Parameter + 3)) >= 0 )
    {
      RemoveColon(DeviceName);
      DefineDosDeviceW(7u, DeviceName, v4);
    }
    DllFreeSplStr(v4);
    EnterSplSem(0);
    FreeRedirectInfo((struct _REDIRECT_INFO *)Parameter);
    LeaveSplSem(v30);
    for ( j = 0; j != 10; ++j )
    {
      v32 = hNamedPipe[j];
      if ( v32 != (HANDLE)-1LL )
      {
        CloseHandle(v32);
        hNamedPipe[j] = (HANDLE)-1LL;
      }
      v33 = Handles[j];
      if ( v33 )
      {
        CloseHandle(v33);
        Handles[j] = 0;
        Handles[4 * j + 15] = 0;
      }
    }
    if ( v36.lpSecurityDescriptor )
      DestroyPrivateObjectSecurity(&v36.lpSecurityDescriptor);
    return 1;
  }
  else
  {
    EnterSplSem(0);
    FreeRedirectInfo((struct _REDIRECT_INFO *)Parameter);
    LeaveSplSem(v5);
    return 0;
  }
}

```

## disassembly

```asm
0x18009def0  push    rbp
0x18009def2  push    rbx
0x18009def3  push    rsi
0x18009def4  push    rdi
0x18009def5  push    r12
0x18009def7  push    r13
0x18009def9  push    r14
0x18009defb  push    r15
0x18009defd  lea     rbp, [rsp-5C8h]
0x18009df05  sub     rsp, 6C8h
0x18009df0c  mov     rax, cs:__security_cookie
0x18009df13  xor     rax, rsp
0x18009df16  mov     [rbp+600h+var_50], rax
0x18009df1d  xor     esi, esi
0x18009df1f  mov     r14, rcx
0x18009df22  xor     edx, edx; Val
0x18009df24  mov     qword ptr [rsp+700h+var_6B0.nLength], rsi
0x18009df29  lea     rcx, [rbp+600h+Handles]; void *
0x18009df2d  mov     qword ptr [rsp+700h+var_6B0.bInheritHandle], rsi
0x18009df32  mov     [rsp+700h+var_6B8], rsi
0x18009df37  lea     r8d, [rsi+58h]; Size
0x18009df3b  call    memset_0
0x18009df40  mov     rcx, [r14]; struct _INIPORT *
0x18009df43  lea     rax, [rsp+700h+var_6B8]
0x18009df48  lea     r9, [rsp+700h+var_6B0]; struct _SECURITY_ATTRIBUTES *
0x18009df4d  mov     qword ptr [rsp+700h+nOutBufferSize], rax; struct _SECURITY_ATTRIBUTES **
0x18009df52  lea     rdx, [rbp+600h+Name]; unsigned __int16 *
0x18009df59  mov     [rsp+700h+ThreadId], esi
0x18009df5d  mov     [rsp+700h+var_6B0.lpSecurityDescriptor], rsi
0x18009df62  call    ?SetupDosDev@@YAPEAGPEAU_INIPORT@@PEAGKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU2@@Z; SetupDosDev(_INIPORT *,ushort *,ulong,_SECURITY_ATTRIBUTES *,_SECURITY_ATTRIBUTES * *)
0x18009df67  mov     r13, rax
0x18009df6a  test    rax, rax
0x18009df6d  jnz     short loc_18009DF8A
0x18009df6f  xor     ecx, ecx
0x18009df71  call    EnterSplSem
0x18009df76  mov     rcx, r14; struct _REDIRECT_INFO *
0x18009df79  call    ?FreeRedirectInfo@@YAXPEAU_REDIRECT_INFO@@@Z; FreeRedirectInfo(_REDIRECT_INFO *)
0x18009df7e  call    LeaveSplSem
0x18009df83  xor     eax, eax
0x18009df85  jmp     loc_18009E347
0x18009df8a  mov     ebx, 50h ; 'P'
0x18009df8f  lea     rcx, [rsp+700h+hNamedPipe]; void *
0x18009df94  mov     r8d, ebx; Size
0x18009df97  or      rdx, 0FFFFFFFFFFFFFFFFh; Val
0x18009df9b  call    memset_0
0x18009dfa0  mov     r8d, ebx; Size
0x18009dfa3  lea     rcx, [rbp+600h+Handles]; void *
0x18009dfa7  xor     edx, edx; Val
0x18009dfa9  call    memset_0
0x18009dfae  mov     rcx, rsi
0x18009dfb1  mov     rax, rcx
0x18009dfb4  inc     rcx
0x18009dfb7  shl     rax, 5
0x18009dfbb  mov     [rbp+rax+600h+var_598], rsi
0x18009dfc0  cmp     rcx, 0Ah
0x18009dfc4  jnz     short loc_18009DFB1
0x18009dfc6  mov     rax, [r14+8]
0x18009dfca  mov     ebx, esi
0x18009dfcc  mov     r12, [rsp+700h+var_6B8]
0x18009dfd1  mov     [rbp+600h+var_5C0], rax
0x18009dfd5  mov     [rsp+700h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18009dfda  lea     rcx, [rbp+600h+Name]; lpName
0x18009dfe1  mov     [rsp+700h+nDefaultTimeOut], esi; nDefaultTimeOut
0x18009dfe5  mov     r9d, 0FFh; nMaxInstances
0x18009dfeb  mov     edi, ebx
0x18009dfed  xor     r8d, r8d; dwPipeMode
0x18009dff0  mov     [rsp+700h+nInBufferSize], 10000h; nInBufferSize
0x18009dff8  mov     edx, 40000003h; dwOpenMode
0x18009dffd  mov     [rsp+700h+nOutBufferSize], 1000h; nOutBufferSize
0x18009e005  mov     [rbp+rdi*4+600h+var_640], esi
0x18009e009  call    cs:__imp_CreateNamedPipeW
0x18009e00f  lea     r15, ds:0[rdi*8]
0x18009e017  mov     rsi, rax
0x18009e01a  mov     [rsp+r15+700h+hNamedPipe], rax
0x18009e01f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009e023  jz      loc_18009E26A
0x18009e029  xor     r9d, r9d; lpName
0x18009e02c  xor     r8d, r8d; bInitialState
0x18009e02f  xor     edx, edx; bManualReset
0x18009e031  xor     ecx, ecx; lpEventAttributes
0x18009e033  call    cs:__imp_CreateEventW
0x18009e039  shl     rdi, 5
0x18009e03d  mov     [rbp+r15+600h+Handles], rax
0x18009e042  mov     [rbp+rdi+600h+var_598], rax
0x18009e047  test    rax, rax
0x18009e04a  jz      loc_18009E24C
0x18009e050  lea     rdx, [rbp+600h+var_5B0]
0x18009e054  mov     rcx, rsi; hNamedPipe
0x18009e057  add     rdx, rdi; lpOverlapped
0x18009e05a  call    cs:__imp_ConnectNamedPipe
0x18009e060  xor     esi, esi
0x18009e062  test    eax, eax
0x18009e064  jnz     short loc_18009E08F
0x18009e066  call    cs:__imp_GetLastError
0x18009e06c  cmp     eax, 3E5h
0x18009e071  jnz     short loc_18009E0D1
0x18009e073  call    cs:__imp_GetLastError
0x18009e079  mov     r8d, eax
0x18009e07c  lea     rdx, aConnectnamedpi; "ConnectNamedPipe %d has IO pending."
0x18009e083  lea     rcx, aRedirectionthr; "RedirectionThread"
0x18009e08a  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18009e08f  inc     ebx
0x18009e091  cmp     ebx, 0Ah
0x18009e094  jb      loc_18009DFD5
0x18009e09a  mov     r15d, esi
0x18009e09d  xor     r8d, r8d; bWaitAll
0x18009e0a0  mov     [rsp+700h+nOutBufferSize], esi; bAlertable
0x18009e0a4  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18009e0a8  lea     rdx, [rbp+600h+Handles]; lpHandles
0x18009e0ac  lea     ecx, [r8+0Bh]; nCount
0x18009e0b0  call    cs:__imp_WaitForMultipleObjectsEx
0x18009e0b6  cmp     eax, 0Ah
0x18009e0b9  jb      short loc_18009E0FA
0x18009e0bb  mov     ecx, esi
0x18009e0bd  mov     eax, ecx
0x18009e0bf  cmp     [rbp+rax*4+600h+var_640], esi
0x18009e0c3  jnz     short loc_18009E0F2
0x18009e0c5  inc     ecx
0x18009e0c7  cmp     ecx, 0Ah
0x18009e0ca  jb      short loc_18009E0BD
0x18009e0cc  jmp     loc_18009E28F
0x18009e0d1  call    cs:__imp_GetLastError
0x18009e0d7  mov     r8d, eax
0x18009e0da  lea     rdx, aConnectnamedpi_0; "ConnectNamedPipe failed. Error %d"
0x18009e0e1  lea     rcx, aRedirectionthr; "RedirectionThread"
0x18009e0e8  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009e0ed  jmp     loc_18009E28F
0x18009e0f2  mov     r15d, 1
0x18009e0f8  jmp     short loc_18009E09D
0x18009e0fa  mov     ebx, eax
0x18009e0fc  lea     rdi, [rbp+600h+var_640]
0x18009e100  lea     rdi, [rdi+rbx*4]
0x18009e104  cmp     [rdi], esi
0x18009e106  jz      short loc_18009E17E
0x18009e108  mov     [rdi], esi
0x18009e10a  test    r15d, r15d
0x18009e10d  jz      short loc_18009E125
0x18009e10f  mov     ecx, esi
0x18009e111  mov     eax, ecx
0x18009e113  cmp     [rbp+rax*4+600h+var_640], esi
0x18009e117  jnz     short loc_18009E09D
0x18009e119  inc     ecx
0x18009e11b  cmp     ecx, 0Ah
0x18009e11e  jb      short loc_18009E111
0x18009e120  jmp     loc_18009E28F
0x18009e125  mov     rdi, [rsp+rbx*8+700h+hNamedPipe]
0x18009e12a  mov     rcx, rdi; hNamedPipe
0x18009e12d  call    cs:__imp_DisconnectNamedPipe
0x18009e133  lea     rdx, [rbp+600h+var_5B0]
0x18009e137  shl     rbx, 5
0x18009e13b  add     rdx, rbx; lpOverlapped
0x18009e13e  mov     rcx, rdi; hNamedPipe
0x18009e141  call    cs:__imp_ConnectNamedPipe
0x18009e147  test    eax, eax
0x18009e149  jnz     loc_18009E09D
0x18009e14f  call    cs:__imp_GetLastError
0x18009e155  cmp     eax, 3E5h
0x18009e15a  jz      loc_18009E09D
0x18009e160  mov     r9d, eax
0x18009e163  lea     rdx, aFailedToReConn; "Failed to re-connect named pipe %p.  Er"...
0x18009e16a  mov     r8, rdi
0x18009e16d  lea     rcx, aReconnectnamed; "ReconnectNamedPipe"
0x18009e174  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009e179  jmp     loc_18009E09D
0x18009e17e  test    r15d, r15d
0x18009e181  jnz     loc_18009E09D
0x18009e187  mov     ecx, 428h
0x18009e18c  call    cs:__imp_DllAllocSplMem
0x18009e192  xor     r12d, r12d
0x18009e195  mov     rsi, rax
0x18009e198  test    rax, rax
0x18009e19b  jz      loc_18009E232
0x18009e1a1  mov     rcx, [rsp+rbx*8+700h+hNamedPipe]
0x18009e1a6  lea     r8, ?ReadThread@@YAXPEAU_TRANSMISSION@@@Z; lpStartAddress
0x18009e1ad  mov     [rax], rcx
0x18009e1b0  mov     r9, rsi; lpParameter
0x18009e1b3  mov     [rax+410h], r12
0x18009e1ba  lea     rcx, [rbp+600h+var_5B0]
0x18009e1be  shl     rbx, 5
0x18009e1c2  mov     edx, 8000h; dwStackSize
0x18009e1c7  add     rcx, rbx
0x18009e1ca  mov     dword ptr [rdi], 1
0x18009e1d0  mov     [rax+408h], rcx
0x18009e1d7  mov     rcx, [r14]
0x18009e1da  mov     [rax+420h], rcx
0x18009e1e1  lea     rax, [rsp+700h+ThreadId]
0x18009e1e6  mov     qword ptr [rsp+700h+nInBufferSize], rax; lpThreadId
0x18009e1eb  xor     ecx, ecx; lpThreadAttributes
0x18009e1ed  mov     [rsp+700h+nOutBufferSize], r12d; dwCreationFlags
0x18009e1f2  call    cs:__imp_CreateThread
0x18009e1f8  test    rax, rax
0x18009e1fb  jz      short loc_18009E208
0x18009e1fd  mov     rcx, rax; hObject
0x18009e200  call    cs:__imp_CloseHandle
0x18009e206  jmp     short loc_18009E245
0x18009e208  mov     rcx, rsi
0x18009e20b  mov     [rdi], r12d
0x18009e20e  call    cs:__imp_DllFreeSplMem
0x18009e214  call    cs:__imp_GetLastError
0x18009e21a  mov     r8d, eax
0x18009e21d  lea     rdx, aFailedToCreate_10; "Failed to create reader thread.  Error "...
0x18009e224  lea     rcx, aRedirectionthr; "RedirectionThread"
0x18009e22b  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18009e230  jmp     short loc_18009E245
0x18009e232  lea     rdx, aFailedToAlloca_7; "Failed to allocate memory for transmiss"...
0x18009e239  lea     rcx, aRedirectionthr; "RedirectionThread"
0x18009e240  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18009e245  xor     esi, esi
0x18009e247  jmp     loc_18009E09D
0x18009e24c  call    cs:__imp_GetLastError
0x18009e252  mov     r8d, eax
0x18009e255  lea     rdx, aCreateeventFai; "CreateEvent failed. Error %d"
0x18009e25c  lea     rcx, aRedirectionthr; "RedirectionThread"
0x18009e263  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009e268  jmp     short loc_18009E28D
0x18009e26a  call    cs:__imp_GetLastError
0x18009e270  mov     r9d, eax
0x18009e273  lea     r8, [rbp+600h+Name]
0x18009e27a  lea     rdx, aCreatenamedpip; "CreateNamedPipe failed for %ws. Error %"...
0x18009e281  lea     rcx, aRedirectionthr; "RedirectionThread"
0x18009e288  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009e28d  xor     esi, esi
0x18009e28f  mov     r8, [r14]
0x18009e292  lea     rcx, [rbp+600h+DeviceName]; unsigned __int16 *
0x18009e299  mov     edx, 104h; unsigned __int64
0x18009e29e  mov     r8, [r8+18h]; unsigned __int16 *
0x18009e2a2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009e2a7  test    eax, eax
0x18009e2a9  js      short loc_18009E2CC
0x18009e2ab  lea     rcx, [rbp+600h+DeviceName]; unsigned __int16 *
0x18009e2b2  call    ?RemoveColon@@YAXPEAG@Z; RemoveColon(ushort *)
0x18009e2b7  mov     r8, r13; lpTargetPath
0x18009e2ba  lea     rdx, [rbp+600h+DeviceName]; lpDeviceName
0x18009e2c1  mov     ecx, 7; dwFlags
0x18009e2c6  call    cs:__imp_DefineDosDeviceW
0x18009e2cc  mov     rcx, r13
0x18009e2cf  call    cs:__imp_DllFreeSplStr
0x18009e2d5  xor     ecx, ecx
0x18009e2d7  call    EnterSplSem
0x18009e2dc  mov     rcx, r14; struct _REDIRECT_INFO *
0x18009e2df  call    ?FreeRedirectInfo@@YAXPEAU_REDIRECT_INFO@@@Z; FreeRedirectInfo(_REDIRECT_INFO *)
0x18009e2e4  call    LeaveSplSem
0x18009e2e9  mov     rbx, rsi
0x18009e2ec  mov     rcx, [rsp+rbx*8+700h+hNamedPipe]; hObject
0x18009e2f1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18009e2f5  jz      short loc_18009E306
0x18009e2f7  call    cs:__imp_CloseHandle
0x18009e2fd  mov     [rsp+rbx*8+700h+hNamedPipe], 0FFFFFFFFFFFFFFFFh
0x18009e306  mov     rcx, [rbp+rbx*8+600h+Handles]; hObject
0x18009e30b  test    rcx, rcx
0x18009e30e  jz      short loc_18009E327
0x18009e310  call    cs:__imp_CloseHandle
0x18009e316  mov     rax, rbx
0x18009e319  mov     [rbp+rbx*8+600h+Handles], rsi
0x18009e31e  shl     rax, 5
0x18009e322  mov     [rbp+rax+600h+var_598], rsi
0x18009e327  inc     rbx
0x18009e32a  cmp     rbx, 0Ah
0x18009e32e  jnz     short loc_18009E2EC
0x18009e330  cmp     [rsp+700h+var_6B0.lpSecurityDescriptor], rsi
0x18009e335  jz      short loc_18009E342
0x18009e337  lea     rcx, [rsp+700h+var_6B0.lpSecurityDescriptor]; ObjectDescriptor
0x18009e33c  call    cs:__imp_DestroyPrivateObjectSecurity
0x18009e342  mov     eax, 1
0x18009e347  mov     rcx, [rbp+600h+var_50]
0x18009e34e  xor     rcx, rsp; StackCookie
0x18009e351  call    __security_check_cookie
0x18009e356  add     rsp, 6C8h
0x18009e35d  pop     r15
0x18009e35f  pop     r14
0x18009e361  pop     r13
0x18009e363  pop     r12
0x18009e365  pop     rdi
0x18009e366  pop     rsi
0x18009e367  pop     rbx
0x18009e368  pop     rbp
0x18009e369  retn
```
