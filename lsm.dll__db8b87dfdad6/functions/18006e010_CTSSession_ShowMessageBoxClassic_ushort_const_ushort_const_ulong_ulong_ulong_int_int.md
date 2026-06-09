# CTSSession::ShowMessageBoxClassic(ushort const *,ushort const *,ulong,ulong,ulong *,int,int)

- ea: `0x18006e010`
- end: `0x18006e3e2`
- name: `?ShowMessageBoxClassic@CTSSession@@UEAAJPEBG0KKPEAKHH@Z`
- size: `978`
- prototype: `__int64 __fastcall(CTSSession *this, const unsigned __int16 *, const unsigned __int16 *, int, unsigned int, unsigned int *, int, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006df40`

## callees

- `0x1800074c0`
- `0x180008f64`
- `0x180010fb0`
- `0x18001aa50`
- `0x18001ce00`
- `0x180022bb8`
- `0x18002e940`
- `0x18004bf44`
- `0x18006e010`
- `0x180097010`

## import_xrefs

- `ntdll!NtClose` at `0x18006e3ab`
- `ntdll!NtClose` at `0x18006e3ab`
- `ntdll!NtCreateEvent` at `0x18006e28f`
- `ntdll!NtCreateEvent` at `0x18006e28f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18006e323`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18006e323`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006e0d9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006e0d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e0f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e0f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e05a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e05a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e3b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e3b4`

## string_xrefs

- `0x18006e113`: `CreateEvent failed: 0x%x in %s`
- `0x18006e15d`: `GetCacheCsrPipe failed: 0x%x in %s`
- `0x18006e1e2`: `StringCchCopy(pSendMessage->pTitle) failed: 0x%x in %s`
- `0x18006e206`: `StringCchCopy(pSendMessage->pMessage) failed: 0x%x in %s`
- `0x18006e29f`: `NtCreateEvent failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSession::ShowMessageBoxClassic(
        CTSSession *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int a5,
        unsigned int *a6,
        int a7,
        int a8)
{
  char *v11; // rax
  char *v12; // rdi
  int LastError; // ebx
  HANDLE *v14; // r13
  HANDLE EventW; // rax
  bool v16; // sf
  int CacheCsrPipe; // eax
  const char *v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned int v21; // r8d
  unsigned int v22; // r9d
  unsigned __int64 v23; // r11
  struct _UNICODE_STRING *InitialState; // r10
  NTSTATUS v25; // eax
  unsigned int v26; // eax
  signed int v27; // eax
  bool v28; // sf
  int v30; // [rsp+30h] [rbp-50h] BYREF
  struct ICsrPipe *v31; // [rsp+38h] [rbp-48h] BYREF
  HANDLE Handles[2]; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF

  v30 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v31 = 0;
  v11 = (char *)LocalAlloc(0x40u, 0x4038u);
  v12 = v11;
  if ( !v11 )
  {
    LastError = -2147024882;
    _DbgPrintMessage(
      8,
      "new WINSTATIONSENDMESSAGEMSG failed: 0x%x in %s",
      -2147024882,
      "CTSSession::ShowMessageBoxClassic");
    goto LABEL_48;
  }
  memset_0(v11, 0, 0x4030u);
  v14 = (HANDLE *)(v12 + 16432);
  *((_QWORD *)v12 + 2054) = 0;
  if ( a7 )
  {
LABEL_11:
    CacheCsrPipe = CTSSession::GetCacheCsrPipe(this, &v31);
    LastError = CacheCsrPipe;
    if ( CacheCsrPipe < 0 )
    {
      v18 = "GetCacheCsrPipe failed: 0x%x in %s";
LABEL_13:
      _DbgPrintMessage(8, v18, (unsigned int)CacheCsrPipe, "CTSSession::ShowMessageBoxClassic");
      goto LABEL_45;
    }
    v19 = -1;
    v20 = -1;
    do
      ++v20;
    while ( a2[v20] );
    v21 = 2 * v20 + 2;
    *((_DWORD *)v12 + 2048) = v21;
    do
      ++v19;
    while ( a3[v19] );
    v22 = 2 * v19 + 2;
    *((_DWORD *)v12 + 4097) = v22;
    if ( v21 > 0x1000 || v22 > 0x1000 )
    {
      _DbgPrintMessage(8, "Too long title (%d) or message (%d) string", v21, v22);
      LastError = -2147024809;
      goto LABEL_45;
    }
    CacheCsrPipe = StringCchCopyW((unsigned __int16 *)v12, 0x1000u, a2);
    LastError = CacheCsrPipe;
    if ( CacheCsrPipe < 0 )
    {
      v18 = "StringCchCopy(pSendMessage->pTitle) failed: 0x%x in %s";
      goto LABEL_13;
    }
    CacheCsrPipe = StringCchCopyW((unsigned __int16 *)v12 + 4098, v23, a3);
    LastError = CacheCsrPipe;
    if ( CacheCsrPipe < 0 )
    {
      v18 = "StringCchCopy(pSendMessage->pMessage) failed: 0x%x in %s";
      goto LABEL_13;
    }
    *((_DWORD *)v12 + 4098) = a4;
    *((_DWORD *)v12 + 4099) = a5;
    v12[16416] = a7 != (_DWORD)InitialState;
    v12[16417] = a8 != (_DWORD)InitialState;
    if ( a7 == (_DWORD)InitialState )
    {
      *((_QWORD *)v12 + 2053) = &v30;
      *((_QWORD *)v12 + 2051) = a6;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = InitialState;
      ObjectAttributes.Attributes = (unsigned int)InitialState;
      ObjectAttributes.ObjectName = InitialState;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v25 = NtCreateEvent((PHANDLE)v12 + 2054, 0x1F0003u, &ObjectAttributes, NotificationEvent, (BOOLEAN)InitialState);
      LastError = v25 | 0x10000000;
      if ( v25 < 0 )
      {
        _DbgPrintMessage(
          8,
          "NtCreateEvent failed: 0x%x in %s",
          (unsigned int)LastError,
          "CTSSession::ShowMessageBoxClassic");
        goto LABEL_45;
      }
      v26 = 32000;
    }
    else
    {
      *((_QWORD *)v12 + 2053) = InitialState;
      *((_QWORD *)v12 + 2051) = InitialState;
      v26 = 32001;
    }
    *a6 = v26;
    CacheCsrPipe = (*(__int64 (__fastcall **)(struct ICsrPipe *, char *, _QWORD))(*(_QWORD *)v31 + 128LL))(v31, v12, 0);
    LastError = CacheCsrPipe;
    if ( CacheCsrPipe < 0 )
    {
      v18 = "SendDoMessage failed: 0x%x in %s";
      goto LABEL_13;
    }
    if ( a7 )
    {
      LastError = 0;
      goto LABEL_45;
    }
    Handles[0] = *v14;
    Handles[1] = *((HANDLE *)this + 404);
    v27 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
    LastError = v27;
    if ( v27 )
    {
      if ( v27 == 1 )
      {
        LastError = -2147017889;
LABEL_39:
        _DbgPrintMessage(
          8,
          "WaitForMultipleObjects failed: 0x%x in %s",
          (unsigned int)LastError,
          "CTSSession::ShowMessageBoxClassic");
        goto LABEL_45;
      }
      v28 = v27 < 0;
      if ( v27 > 0 )
      {
        LastError = (unsigned __int16)v27 | 0x80070000;
        v28 = 1;
      }
      if ( v28 )
        goto LABEL_39;
    }
    LastError = v30 | 0x10000000;
    if ( v30 >= 0 )
      _DbgPrintMessage(1, "ShowMessageBox: got response %u", *a6);
    else
      _DbgPrintMessage(
        8,
        "SendMessage delivery failed: 0x%x in %s",
        (unsigned int)LastError,
        "CTSSession::ShowMessageBoxClassic");
    goto LABEL_45;
  }
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)Handles, (CTSSession *)((char *)this + 1856));
  if ( *((_QWORD *)this + 404) )
    goto LABEL_10;
  EventW = CreateEventW(0, 1, 0, 0);
  SmartHANDLE::operator=((char *)this + 3232, EventW);
  if ( *((_QWORD *)this + 404) )
    goto LABEL_10;
  LastError = GetLastError();
  v16 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v16 = LastError < 0;
  }
  if ( !v16 )
  {
LABEL_10:
    CAutoLock::Unlock((CAutoLock *)Handles);
    CAutoLock::Unlock((CAutoLock *)Handles);
    goto LABEL_11;
  }
  _DbgPrintMessage(8, "CreateEvent failed: 0x%x in %s", LastError, "CTSSession::ShowMessageBoxClassic");
  CAutoLock::Unlock((CAutoLock *)Handles);
LABEL_45:
  if ( *v14 )
    NtClose(*v14);
  LocalFree(v12);
LABEL_48:
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v31);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18006e010  mov     [rsp-28h+arg_0], rbx
0x18006e015  mov     [rsp-28h+arg_8], rsi
0x18006e01a  mov     [rsp-28h+arg_18], r9d
0x18006e01f  push    rbp
0x18006e020  push    rdi
0x18006e021  push    r12
0x18006e023  push    r13
0x18006e025  push    r15
0x18006e027  mov     rbp, rsp
0x18006e02a  sub     rsp, 80h
0x18006e031  mov     r12, r8
0x18006e034  mov     rsi, rdx
0x18006e037  mov     r15, rcx
0x18006e03a  xor     ebx, ebx
0x18006e03c  mov     [rbp+var_50], ebx
0x18006e03f  xorps   xmm0, xmm0
0x18006e042  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18006e046  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18006e04a  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18006e04e  mov     [rbp+var_48], rbx
0x18006e052  mov     edx, 4038h; uBytes
0x18006e057  lea     ecx, [rbx+40h]; uFlags
0x18006e05a  call    cs:__imp_LocalAlloc
0x18006e060  mov     rdi, rax
0x18006e063  test    rax, rax
0x18006e066  jnz     short loc_18006E08B
0x18006e068  mov     ebx, 8007000Eh
0x18006e06d  lea     r9, aCtssessionShow_1; "CTSSession::ShowMessageBoxClassic"
0x18006e074  mov     r8d, ebx
0x18006e077  lea     rdx, aNewWinstations; "new WINSTATIONSENDMESSAGEMSG failed: 0x"...
0x18006e07e  lea     ecx, [rax+8]; int
0x18006e081  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006e086  jmp     loc_18006E3BB
0x18006e08b  xor     edx, edx; Val
0x18006e08d  mov     r8d, 4030h; Size
0x18006e093  mov     rcx, rdi; void *
0x18006e096  call    memset_0
0x18006e09b  lea     r13, [rdi+4030h]
0x18006e0a2  mov     [r13+0], rbx
0x18006e0a6  cmp     [rbp+arg_30], ebx
0x18006e0a9  jnz     loc_18006E148
0x18006e0af  lea     rdx, [r15+740h]; struct CResource *
0x18006e0b6  lea     rcx, [rbp+Handles]; this
0x18006e0ba  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18006e0bf  nop
0x18006e0c0  lea     rbx, [r15+0CA0h]
0x18006e0c7  cmp     qword ptr [rbx], 0
0x18006e0cb  jnz     short loc_18006E134
0x18006e0cd  xor     r9d, r9d; lpName
0x18006e0d0  xor     r8d, r8d; bInitialState
0x18006e0d3  lea     edx, [r9+1]; bManualReset
0x18006e0d7  xor     ecx, ecx; lpEventAttributes
0x18006e0d9  call    cs:__imp_CreateEventW
0x18006e0df  mov     rdx, rax
0x18006e0e2  mov     rcx, rbx
0x18006e0e5  call    ??4SmartHANDLE@@QEAAXPEAX@Z; SmartHANDLE::operator=(void *)
0x18006e0ea  cmp     qword ptr [rbx], 0
0x18006e0ee  jnz     short loc_18006E134
0x18006e0f0  call    cs:__imp_GetLastError
0x18006e0f6  mov     ebx, eax
0x18006e0f8  test    eax, eax
0x18006e0fa  jle     short loc_18006E107
0x18006e0fc  movzx   ebx, bx
0x18006e0ff  or      ebx, 80070000h
0x18006e105  test    ebx, ebx
0x18006e107  jns     short loc_18006E134
0x18006e109  lea     r9, aCtssessionShow_1; "CTSSession::ShowMessageBoxClassic"
0x18006e110  mov     r8d, ebx
0x18006e113  lea     rdx, aCreateeventFai; "CreateEvent failed: 0x%x in %s"
0x18006e11a  mov     ecx, 8; int
0x18006e11f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006e124  nop
0x18006e125  lea     rcx, [rbp+Handles]; this
0x18006e129  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18006e12e  nop
0x18006e12f  jmp     loc_18006E3A2
0x18006e134  lea     rcx, [rbp+Handles]; this
0x18006e138  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18006e13d  nop
0x18006e13e  lea     rcx, [rbp+Handles]; this
0x18006e142  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18006e147  nop
0x18006e148  lea     rdx, [rbp+var_48]; struct ICsrPipe **
0x18006e14c  mov     rcx, r15; this
0x18006e14f  call    ?GetCacheCsrPipe@CTSSession@@UEAAJPEAPEAVICsrPipe@@@Z; CTSSession::GetCacheCsrPipe(ICsrPipe * *)
0x18006e154  mov     ebx, eax
0x18006e156  xor     r10d, r10d
0x18006e159  test    eax, eax
0x18006e15b  jns     short loc_18006E17D
0x18006e15d  lea     rdx, aGetcachecsrpip; "GetCacheCsrPipe failed: 0x%x in %s"
0x18006e164  mov     r8d, eax
0x18006e167  lea     r9, aCtssessionShow_1; "CTSSession::ShowMessageBoxClassic"
0x18006e16e  mov     ecx, 8; int
0x18006e173  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006e178  jmp     loc_18006E3A2
0x18006e17d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006e181  mov     rcx, rax
0x18006e184  inc     rcx
0x18006e187  cmp     [rsi+rcx*2], r10w
0x18006e18c  jnz     short loc_18006E184
0x18006e18e  lea     r8d, ds:2[rcx*2]
0x18006e196  mov     [rdi+2000h], r8d
0x18006e19d  inc     rax
0x18006e1a0  cmp     [r12+rax*2], r10w
0x18006e1a5  jnz     short loc_18006E19D
0x18006e1a7  lea     r9d, ds:2[rax*2]
0x18006e1af  mov     [rdi+4004h], r9d
0x18006e1b6  mov     r11d, 1000h
0x18006e1bc  cmp     r8d, r11d
0x18006e1bf  ja      loc_18006E38C
0x18006e1c5  cmp     r9d, r11d
0x18006e1c8  ja      loc_18006E38C
0x18006e1ce  mov     r8, rsi; unsigned __int16 *
0x18006e1d1  mov     edx, r11d; unsigned __int64
0x18006e1d4  mov     rcx, rdi; unsigned __int16 *
0x18006e1d7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006e1dc  mov     ebx, eax
0x18006e1de  test    eax, eax
0x18006e1e0  jns     short loc_18006E1EE
0x18006e1e2  lea     rdx, aStringcchcopyP_0; "StringCchCopy(pSendMessage->pTitle) fai"...
0x18006e1e9  jmp     loc_18006E164
0x18006e1ee  lea     rcx, [rdi+2004h]; unsigned __int16 *
0x18006e1f5  mov     r8, r12; unsigned __int16 *
0x18006e1f8  mov     rdx, r11; unsigned __int64
0x18006e1fb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006e200  mov     ebx, eax
0x18006e202  test    eax, eax
0x18006e204  jns     short loc_18006E212
0x18006e206  lea     rdx, aStringcchcopyP; "StringCchCopy(pSendMessage->pMessage) f"...
0x18006e20d  jmp     loc_18006E164
0x18006e212  mov     eax, [rbp+arg_18]
0x18006e215  mov     [rdi+4008h], eax
0x18006e21b  mov     eax, [rbp+arg_20]
0x18006e21e  mov     [rdi+400Ch], eax
0x18006e224  cmp     [rbp+arg_30], r10d
0x18006e228  setnz   al
0x18006e22b  mov     [rdi+4020h], al
0x18006e231  cmp     [rbp+arg_38], r10d
0x18006e235  setnz   al
0x18006e238  mov     [rdi+4021h], al
0x18006e23e  mov     r12d, 10000000h
0x18006e244  mov     rsi, [rbp+arg_28]
0x18006e248  cmp     [rbp+arg_30], r10d
0x18006e24c  jnz     short loc_18006E2B2
0x18006e24e  lea     rax, [rbp+var_50]
0x18006e252  mov     [rdi+4028h], rax
0x18006e259  mov     [rdi+4018h], rsi
0x18006e260  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18006e267  mov     [rbp+ObjectAttributes.RootDirectory], r10
0x18006e26b  mov     [rbp+ObjectAttributes.Attributes], r10d
0x18006e26f  mov     [rbp+ObjectAttributes.ObjectName], r10
0x18006e273  xorps   xmm0, xmm0
0x18006e276  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18006e27b  mov     [rsp+80h+InitialState], r10b; InitialState
0x18006e280  xor     r9d, r9d; EventType
0x18006e283  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18006e287  mov     edx, 1F0003h; DesiredAccess
0x18006e28c  mov     rcx, r13; EventHandle
0x18006e28f  call    cs:__imp_NtCreateEvent
0x18006e295  mov     ebx, eax
0x18006e297  or      ebx, r12d
0x18006e29a  jge     short loc_18006E2AB
0x18006e29c  mov     r8d, ebx
0x18006e29f  lea     rdx, aNtcreateeventF; "NtCreateEvent failed: 0x%x in %s"
0x18006e2a6  jmp     loc_18006E167
0x18006e2ab  mov     eax, 7D00h
0x18006e2b0  jmp     short loc_18006E2C5
0x18006e2b2  mov     [rdi+4028h], r10
0x18006e2b9  mov     [rdi+4018h], r10
0x18006e2c0  mov     eax, 7D01h
0x18006e2c5  mov     [rsi], eax
0x18006e2c7  mov     rcx, [rbp+var_48]
0x18006e2cb  mov     rax, [rcx]
0x18006e2ce  xor     r8d, r8d
0x18006e2d1  mov     rdx, rdi
0x18006e2d4  mov     rax, [rax+80h]
0x18006e2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e2e0  mov     ebx, eax
0x18006e2e2  xor     ecx, ecx
0x18006e2e4  test    eax, eax
0x18006e2e6  jns     short loc_18006E2F4
0x18006e2e8  lea     rdx, aSenddomessageF; "SendDoMessage failed: 0x%x in %s"
0x18006e2ef  jmp     loc_18006E164
0x18006e2f4  cmp     [rbp+arg_30], ecx
0x18006e2f7  jnz     loc_18006E388
0x18006e2fd  mov     rax, [r13+0]
0x18006e301  mov     [rbp+Handles], rax
0x18006e305  mov     rax, [r15+0CA0h]
0x18006e30c  mov     [rbp+var_38], rax
0x18006e310  mov     dword ptr [rsp+80h+InitialState], ecx; bAlertable
0x18006e314  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18006e318  xor     r8d, r8d; bWaitAll
0x18006e31b  lea     rdx, [rbp+Handles]; lpHandles
0x18006e31f  lea     ecx, [r8+2]; nCount
0x18006e323  call    cs:__imp_WaitForMultipleObjectsEx
0x18006e329  mov     ebx, eax
0x18006e32b  test    eax, eax
0x18006e32d  jz      short loc_18006E35B
0x18006e32f  cmp     eax, 1
0x18006e332  jnz     short loc_18006E33B
0x18006e334  mov     ebx, 80071B5Fh
0x18006e339  jmp     short loc_18006E34C
0x18006e33b  test    ebx, ebx
0x18006e33d  jle     short loc_18006E34A
0x18006e33f  movzx   ebx, bx
0x18006e342  or      ebx, 80070000h
0x18006e348  test    ebx, ebx
0x18006e34a  jns     short loc_18006E35B
0x18006e34c  mov     r8d, ebx
0x18006e34f  lea     rdx, aWaitformultipl; "WaitForMultipleObjects failed: 0x%x in "...
0x18006e356  jmp     loc_18006E167
0x18006e35b  mov     ebx, [rbp+var_50]
0x18006e35e  or      ebx, r12d
0x18006e361  jge     short loc_18006E372
0x18006e363  mov     r8d, ebx
0x18006e366  lea     rdx, aSendmessageDel; "SendMessage delivery failed: 0x%x in %s"
0x18006e36d  jmp     loc_18006E167
0x18006e372  mov     r8d, [rsi]
0x18006e375  lea     rdx, aShowmessagebox_0; "ShowMessageBox: got response %u"
0x18006e37c  mov     ecx, 1; int
0x18006e381  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006e386  jmp     short loc_18006E3A2
0x18006e388  mov     ebx, ecx
0x18006e38a  jmp     short loc_18006E3A2
0x18006e38c  lea     rdx, aTooLongTitleDO; "Too long title (%d) or message (%d) str"...
0x18006e393  mov     ecx, 8; int
0x18006e398  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006e39d  mov     ebx, 80070057h
0x18006e3a2  mov     rcx, [r13+0]; Handle
0x18006e3a6  test    rcx, rcx
0x18006e3a9  jz      short loc_18006E3B1
0x18006e3ab  call    cs:__imp_NtClose
0x18006e3b1  mov     rcx, rdi; hMem
0x18006e3b4  call    cs:__imp_LocalFree
0x18006e3ba  nop
0x18006e3bb  lea     rcx, [rbp+var_48]
0x18006e3bf  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18006e3c4  mov     eax, ebx
0x18006e3c6  lea     r11, [rsp+80h+var_s0]
0x18006e3ce  mov     rbx, [r11+30h]
0x18006e3d2  mov     rsi, [r11+38h]
0x18006e3d6  mov     rsp, r11
0x18006e3d9  pop     r15
0x18006e3db  pop     r13
0x18006e3dd  pop     r12
0x18006e3df  pop     rdi
0x18006e3e0  pop     rbp
0x18006e3e1  retn
```
