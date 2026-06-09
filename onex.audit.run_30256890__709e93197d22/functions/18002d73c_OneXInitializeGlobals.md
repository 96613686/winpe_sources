# OneXInitializeGlobals

- ea: `0x18002d73c`
- end: `0x18002d9a0`
- name: `OneXInitializeGlobals`
- size: `612`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180019b60`

## callees

- `0x180005440`
- `0x180010ae0`
- `0x18001dd84`
- `0x1800214f0`
- `0x18002d73c`

## import_xrefs

- `ntdll!WinSqmIsOptedIn` at `0x18002d7b1`
- `ntdll!WinSqmIsOptedIn` at `0x18002d7b1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18002d895`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18002d895`
- `MobileNetworking!DeInitializeTimers` at `0x18002d944`
- `MobileNetworking!DeInitializeTimers` at `0x18002d944`
- `MobileNetworking!InitializeTimers` at `0x18002d845`
- `MobileNetworking!InitializeTimers` at `0x18002d845`
- `MobileNetworking!IsWinPE` at `0x18002d7bd`
- `MobileNetworking!IsWinPE` at `0x18002d7bd`
- `MobileNetworking!CreateReadWriteLock` at `0x18002d7fa`
- `MobileNetworking!CreateReadWriteLock` at `0x18002d8bd`
- `MobileNetworking!CreateReadWriteLock` at `0x18002d909`
- `MobileNetworking!CreateReadWriteLock` at `0x18002d7fa`
- `MobileNetworking!CreateReadWriteLock` at `0x18002d8bd`
- `MobileNetworking!CreateReadWriteLock` at `0x18002d909`
- `MobileNetworking!DeleteReadWriteLock` at `0x18002d951`
- `MobileNetworking!DeleteReadWriteLock` at `0x18002d962`
- `MobileNetworking!DeleteReadWriteLock` at `0x18002d951`
- `MobileNetworking!DeleteReadWriteLock` at `0x18002d962`

## pseudocode

```c
__int64 OneXInitializeGlobals()
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  _QWORD *v2; // rcx
  int v3; // esi
  unsigned int v4; // eax
  unsigned int v5; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids);
  qword_18003DD8C = 0;
  dword_18003DE08 = 0;
  dword_18003DE0C = -1;
  qword_18003DD5C = 0;
  dword_18003DD88 = 0;
  dword_18003DE10 = WinSqmIsOptedIn();
  dword_18003DE90 = IsWinPE();
  qword_18003DD70 = (__int64)&qword_18003DD68;
  qword_18003DD68 = (__int64)&qword_18003DD68;
  qword_18003DD80 = (__int64)&qword_18003DD78;
  qword_18003DD78 = (__int64)&qword_18003DD78;
  v0 = CreateReadWriteLock(qword_18003DD98);
  v1 = v0;
  if ( !v0 )
  {
    v3 = 0;
    v4 = InitializeTimers(&qword_18003DE00);
    v1 = v4;
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids, v4);
      goto LABEL_22;
    }
    dword_18003DE08 = IsAppServer();
    dword_18003DE0C = WTSGetActiveConsoleSessionId();
    qword_18003DE20 = (__int64)&qword_18003DE18;
    qword_18003DE18 = (__int64)&qword_18003DE18;
    v5 = CreateReadWriteLock(qword_18003DE28);
    v1 = v5;
    if ( v5 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_21;
      v7 = 14;
    }
    else
    {
      hObject = (HANDLE)-1LL;
      qword_18003DF20 = 0;
      pConnectionIdThatLastSavedCreds = 0;
      fSaveToCredMan = 0;
      v5 = CreateReadWriteLock(g_OneXSsoInfo);
      v1 = v5;
      if ( !v5 )
        goto LABEL_24;
      v3 = 1;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_21;
      v7 = 15;
    }
    WPP_SF_d(v6[7], v7, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids, v5);
LABEL_21:
    DeInitializeTimers(qword_18003DE00);
LABEL_22:
    DeleteReadWriteLock(qword_18003DD98);
    if ( v3 )
      DeleteReadWriteLock(qword_18003DE28);
    goto LABEL_24;
  }
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids, v0);
LABEL_24:
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 17) & 0x800) != 0 )
    WPP_SF_D(v2[7], 16, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x18002d73c  push    rbx
0x18002d73e  push    rbp
0x18002d73f  push    rsi
0x18002d740  push    rdi
0x18002d741  push    r12
0x18002d743  push    r15
0x18002d745  sub     rsp, 28h
0x18002d749  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d750  lea     r15, WPP_GLOBAL_Control
0x18002d757  lea     r12, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x18002d75e  cmp     rcx, r15
0x18002d761  jz      short loc_18002D77D
0x18002d763  test    dword ptr [rcx+44h], 800h
0x18002d76a  jz      short loc_18002D77D
0x18002d76c  mov     rcx, [rcx+38h]
0x18002d770  mov     edx, 0Ah
0x18002d775  mov     r8, r12
0x18002d778  call    WPP_SF_
0x18002d77d  mov     cs:qword_18003DD8C, 0
0x18002d788  mov     cs:dword_18003DE08, 0
0x18002d792  mov     cs:dword_18003DE0C, 0FFFFFFFFh
0x18002d79c  mov     cs:qword_18003DD5C, 0
0x18002d7a7  mov     cs:dword_18003DD88, 0
0x18002d7b1  call    cs:__imp_WinSqmIsOptedIn
0x18002d7b7  mov     cs:dword_18003DE10, eax
0x18002d7bd  call    cs:__imp_IsWinPE
0x18002d7c3  mov     cs:dword_18003DE90, eax
0x18002d7c9  lea     rcx, qword_18003DD98
0x18002d7d0  lea     rax, qword_18003DD68
0x18002d7d7  mov     cs:qword_18003DD70, rax
0x18002d7de  mov     cs:qword_18003DD68, rax
0x18002d7e5  lea     rax, qword_18003DD78
0x18002d7ec  mov     cs:qword_18003DD80, rax
0x18002d7f3  mov     cs:qword_18003DD78, rax
0x18002d7fa  call    cs:__imp_CreateReadWriteLock
0x18002d800  mov     ebx, eax
0x18002d802  test    eax, eax
0x18002d804  jz      short loc_18002D83C
0x18002d806  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d80d  cmp     rcx, r15
0x18002d810  jz      loc_18002D991
0x18002d816  mov     edi, 1
0x18002d81b  test    [rcx+44h], dil
0x18002d81f  jz      loc_18002D96F
0x18002d825  mov     rcx, [rcx+38h]
0x18002d829  lea     edx, [rdi+0Ah]
0x18002d82c  mov     r9d, eax
0x18002d82f  mov     r8, r12
0x18002d832  call    WPP_SF_d
0x18002d837  jmp     loc_18002D968
0x18002d83c  lea     rcx, qword_18003DE00
0x18002d843  xor     esi, esi
0x18002d845  call    cs:__imp_InitializeTimers
0x18002d84b  mov     ebx, eax
0x18002d84d  test    eax, eax
0x18002d84f  jz      short loc_18002D885
0x18002d851  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d858  cmp     rcx, r15
0x18002d85b  jz      loc_18002D94A
0x18002d861  lea     edi, [rsi+1]
0x18002d864  test    [rcx+44h], dil
0x18002d868  jz      loc_18002D94A
0x18002d86e  mov     rcx, [rcx+38h]
0x18002d872  lea     edx, [rsi+0Ch]
0x18002d875  mov     r9d, eax
0x18002d878  mov     r8, r12
0x18002d87b  call    WPP_SF_d
0x18002d880  jmp     loc_18002D94A
0x18002d885  mov     edi, 1
0x18002d88a  call    IsAppServer
0x18002d88f  mov     cs:dword_18003DE08, eax
0x18002d895  call    cs:__imp_WTSGetActiveConsoleSessionId
0x18002d89b  mov     cs:dword_18003DE0C, eax
0x18002d8a1  lea     rcx, qword_18003DE28
0x18002d8a8  lea     rax, qword_18003DE18
0x18002d8af  mov     cs:qword_18003DE20, rax
0x18002d8b6  mov     cs:qword_18003DE18, rax
0x18002d8bd  call    cs:__imp_CreateReadWriteLock
0x18002d8c3  mov     ebx, eax
0x18002d8c5  test    eax, eax
0x18002d8c7  jz      short loc_18002D8E0
0x18002d8c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d8d0  cmp     rcx, r15
0x18002d8d3  jz      short loc_18002D93D
0x18002d8d5  test    [rcx+44h], dil
0x18002d8d9  jz      short loc_18002D93D
0x18002d8db  lea     edx, [rdi+0Dh]
0x18002d8de  jmp     short loc_18002D92E
0x18002d8e0  xorps   xmm0, xmm0
0x18002d8e3  mov     cs:hObject, 0FFFFFFFFFFFFFFFFh
0x18002d8ee  lea     rcx, g_OneXSsoInfo
0x18002d8f5  mov     cs:qword_18003DF20, rsi
0x18002d8fc  movups  xmmword ptr cs:pConnectionIdThatLastSavedCreds.Data1, xmm0
0x18002d903  mov     cs:fSaveToCredMan, esi
0x18002d909  call    cs:__imp_CreateReadWriteLock
0x18002d90f  mov     ebx, eax
0x18002d911  test    eax, eax
0x18002d913  jz      short loc_18002D968
0x18002d915  mov     esi, edi
0x18002d917  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d91e  cmp     rcx, r15
0x18002d921  jz      short loc_18002D93D
0x18002d923  test    [rcx+44h], dil
0x18002d927  jz      short loc_18002D93D
0x18002d929  mov     edx, 0Fh
0x18002d92e  mov     rcx, [rcx+38h]
0x18002d932  mov     r9d, eax
0x18002d935  mov     r8, r12
0x18002d938  call    WPP_SF_d
0x18002d93d  mov     rcx, cs:qword_18003DE00
0x18002d944  call    cs:__imp_DeInitializeTimers
0x18002d94a  lea     rcx, qword_18003DD98
0x18002d951  call    cs:__imp_DeleteReadWriteLock
0x18002d957  test    esi, esi
0x18002d959  jz      short loc_18002D968
0x18002d95b  lea     rcx, qword_18003DE28
0x18002d962  call    cs:__imp_DeleteReadWriteLock
0x18002d968  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d96f  cmp     rcx, r15
0x18002d972  jz      short loc_18002D991
0x18002d974  test    dword ptr [rcx+44h], 800h
0x18002d97b  jz      short loc_18002D991
0x18002d97d  mov     rcx, [rcx+38h]
0x18002d981  mov     edx, 10h
0x18002d986  mov     r9d, ebx
0x18002d989  mov     r8, r12
0x18002d98c  call    WPP_SF_D
0x18002d991  mov     eax, ebx
0x18002d993  add     rsp, 28h
0x18002d997  pop     r15
0x18002d999  pop     r12
0x18002d99b  pop     rdi
0x18002d99c  pop     rsi
0x18002d99d  pop     rbp
0x18002d99e  pop     rbx
0x18002d99f  retn
```
