# CTSSession::ShowMessageBoxClassic(ushort const *,ushort const *,ulong,ulong,ulong *,int,int)

- ea: `0x180071f50`
- end: `0x18007234d`
- name: `?ShowMessageBoxClassic@CTSSession@@UEAAJPEBG0KKPEAKHH@Z`
- size: `1021`
- prototype: `__int64 __usercall@<rax>(CTSSession *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int, unsigned int *, int, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180071e80`

## callees

- `0x1800077a0`
- `0x180009580`
- `0x18000c684`
- `0x1800129d0`
- `0x180014b20`
- `0x1800248ac`
- `0x1800308e0`
- `0x18004f354`
- `0x180071f50`
- `0x18009c010`

## import_xrefs

- `ntdll!NtClose` at `0x180072309`
- `ntdll!NtClose` at `0x180072309`
- `ntdll!NtCreateEvent` at `0x1800721e1`
- `ntdll!NtCreateEvent` at `0x1800721e1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18007227b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18007227b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007201f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007201f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007203c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007203c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180071f9a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180071f9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072318`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072318`

## string_xrefs

- `0x180072065`: `CreateEvent failed: 0x%x in %s`
- `0x1800720af`: `GetCacheCsrPipe failed: 0x%x in %s`
- `0x180072134`: `StringCchCopy(pSendMessage->pTitle) failed: 0x%x in %s`
- `0x180072158`: `StringCchCopy(pSendMessage->pMessage) failed: 0x%x in %s`
- `0x1800721f7`: `NtCreateEvent failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180071f50  mov     [rsp-28h+arg_0], rbx
0x180071f55  mov     [rsp-28h+arg_8], rsi
0x180071f5a  mov     [rsp-28h+arg_18], r9d
0x180071f5f  push    rbp
0x180071f60  push    rdi
0x180071f61  push    r12
0x180071f63  push    r13
0x180071f65  push    r15
0x180071f67  mov     rbp, rsp
0x180071f6a  sub     rsp, 80h
0x180071f71  mov     r12, r8
0x180071f74  mov     rsi, rdx
0x180071f77  mov     r15, rcx
0x180071f7a  xor     ebx, ebx
0x180071f7c  mov     [rbp+var_50], ebx
0x180071f7f  xorps   xmm0, xmm0
0x180071f82  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180071f86  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180071f8a  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180071f8e  mov     [rbp+var_48], rbx
0x180071f92  mov     edx, 4038h; uBytes
0x180071f97  lea     ecx, [rbx+40h]; uFlags
0x180071f9a  call    cs:__imp_LocalAlloc
0x180071fa1  nop     dword ptr [rax+rax+00h]
0x180071fa6  mov     rdi, rax
0x180071fa9  test    rax, rax
0x180071fac  jnz     short loc_180071FD1
0x180071fae  mov     ebx, 8007000Eh
0x180071fb3  lea     r9, aCtssessionShow_1; "CTSSession::ShowMessageBoxClassic"
0x180071fba  mov     r8d, ebx
0x180071fbd  lea     rdx, aNewWinstations; "new WINSTATIONSENDMESSAGEMSG failed: 0x"...
0x180071fc4  lea     ecx, [rax+8]; int
0x180071fc7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180071fcc  jmp     loc_180072325
0x180071fd1  xor     edx, edx; Val
0x180071fd3  mov     r8d, 4030h; Size
0x180071fd9  mov     rcx, rdi; void *
0x180071fdc  call    memset_0
0x180071fe1  lea     r13, [rdi+4030h]
0x180071fe8  mov     [r13+0], rbx
0x180071fec  cmp     [rbp+arg_30], ebx
0x180071fef  jnz     loc_18007209A
0x180071ff5  lea     rdx, [r15+740h]; struct CResource *
0x180071ffc  lea     rcx, [rbp+Handles]; this
0x180072000  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180072005  nop
0x180072006  lea     rbx, [r15+0CA0h]
0x18007200d  cmp     qword ptr [rbx], 0
0x180072011  jnz     short loc_180072086
0x180072013  xor     r9d, r9d; lpName
0x180072016  xor     r8d, r8d; bInitialState
0x180072019  lea     edx, [r9+1]; bManualReset
0x18007201d  xor     ecx, ecx; lpEventAttributes
0x18007201f  call    cs:__imp_CreateEventW
0x180072026  nop     dword ptr [rax+rax+00h]
0x18007202b  mov     rdx, rax
0x18007202e  mov     rcx, rbx
0x180072031  call    ??4SmartHANDLE@@QEAAXPEAX@Z; SmartHANDLE::operator=(void *)
0x180072036  cmp     qword ptr [rbx], 0
0x18007203a  jnz     short loc_180072086
0x18007203c  call    cs:__imp_GetLastError
0x180072043  nop     dword ptr [rax+rax+00h]
0x180072048  mov     ebx, eax
0x18007204a  test    eax, eax
0x18007204c  jle     short loc_180072059
0x18007204e  movzx   ebx, bx
0x180072051  or      ebx, 80070000h
0x180072057  test    ebx, ebx
0x180072059  jns     short loc_180072086
0x18007205b  lea     r9, aCtssessionShow_1; "CTSSession::ShowMessageBoxClassic"
0x180072062  mov     r8d, ebx
0x180072065  lea     rdx, aCreateeventFai; "CreateEvent failed: 0x%x in %s"
0x18007206c  mov     ecx, 8; int
0x180072071  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180072076  nop
0x180072077  lea     rcx, [rbp+Handles]; this
0x18007207b  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180072080  nop
0x180072081  jmp     loc_180072300
0x180072086  lea     rcx, [rbp+Handles]; this
0x18007208a  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18007208f  nop
0x180072090  lea     rcx, [rbp+Handles]; this
0x180072094  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180072099  nop
0x18007209a  lea     rdx, [rbp+var_48]; struct ICsrPipe **
0x18007209e  mov     rcx, r15; this
0x1800720a1  call    ?GetCacheCsrPipe@CTSSession@@UEAAJPEAPEAVICsrPipe@@@Z; CTSSession::GetCacheCsrPipe(ICsrPipe * *)
0x1800720a6  mov     ebx, eax
0x1800720a8  xor     r10d, r10d
0x1800720ab  test    eax, eax
0x1800720ad  jns     short loc_1800720CF
0x1800720af  lea     rdx, aGetcachecsrpip; "GetCacheCsrPipe failed: 0x%x in %s"
0x1800720b6  mov     r8d, eax
0x1800720b9  lea     r9, aCtssessionShow_1; "CTSSession::ShowMessageBoxClassic"
0x1800720c0  mov     ecx, 8; int
0x1800720c5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800720ca  jmp     loc_180072300
0x1800720cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800720d3  mov     rcx, rax
0x1800720d6  inc     rcx
0x1800720d9  cmp     [rsi+rcx*2], r10w
0x1800720de  jnz     short loc_1800720D6
0x1800720e0  lea     r8d, ds:2[rcx*2]
0x1800720e8  mov     [rdi+2000h], r8d
0x1800720ef  inc     rax
0x1800720f2  cmp     [r12+rax*2], r10w
0x1800720f7  jnz     short loc_1800720EF
0x1800720f9  lea     r9d, ds:2[rax*2]
0x180072101  mov     [rdi+4004h], r9d
0x180072108  mov     r11d, 1000h
0x18007210e  cmp     r8d, r11d
0x180072111  ja      loc_1800722EA
0x180072117  cmp     r9d, r11d
0x18007211a  ja      loc_1800722EA
0x180072120  mov     r8, rsi; unsigned __int16 *
0x180072123  mov     edx, r11d; unsigned __int64
0x180072126  mov     rcx, rdi; unsigned __int16 *
0x180072129  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007212e  mov     ebx, eax
0x180072130  test    eax, eax
0x180072132  jns     short loc_180072140
0x180072134  lea     rdx, aStringcchcopyP_0; "StringCchCopy(pSendMessage->pTitle) fai"...
0x18007213b  jmp     loc_1800720B6
0x180072140  lea     rcx, [rdi+2004h]; unsigned __int16 *
0x180072147  mov     r8, r12; unsigned __int16 *
0x18007214a  mov     rdx, r11; unsigned __int64
0x18007214d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180072152  mov     ebx, eax
0x180072154  test    eax, eax
0x180072156  jns     short loc_180072164
0x180072158  lea     rdx, aStringcchcopyP; "StringCchCopy(pSendMessage->pMessage) f"...
0x18007215f  jmp     loc_1800720B6
0x180072164  mov     eax, [rbp+arg_18]
0x180072167  mov     [rdi+4008h], eax
0x18007216d  mov     eax, [rbp+arg_20]
0x180072170  mov     [rdi+400Ch], eax
0x180072176  cmp     [rbp+arg_30], r10d
0x18007217a  setnz   al
0x18007217d  mov     [rdi+4020h], al
0x180072183  cmp     [rbp+arg_38], r10d
0x180072187  setnz   al
0x18007218a  mov     [rdi+4021h], al
0x180072190  mov     r12d, 10000000h
0x180072196  mov     rsi, [rbp+arg_28]
0x18007219a  cmp     [rbp+arg_30], r10d
0x18007219e  jnz     short loc_18007220A
0x1800721a0  lea     rax, [rbp+var_50]
0x1800721a4  mov     [rdi+4028h], rax
0x1800721ab  mov     [rdi+4018h], rsi
0x1800721b2  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800721b9  mov     [rbp+ObjectAttributes.RootDirectory], r10
0x1800721bd  mov     [rbp+ObjectAttributes.Attributes], r10d
0x1800721c1  mov     [rbp+ObjectAttributes.ObjectName], r10
0x1800721c5  xorps   xmm0, xmm0
0x1800721c8  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800721cd  mov     [rsp+80h+InitialState], r10b; InitialState
0x1800721d2  xor     r9d, r9d; EventType
0x1800721d5  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800721d9  mov     edx, 1F0003h; DesiredAccess
0x1800721de  mov     rcx, r13; EventHandle
0x1800721e1  call    cs:__imp_NtCreateEvent
0x1800721e8  nop     dword ptr [rax+rax+00h]
0x1800721ed  mov     ebx, eax
0x1800721ef  or      ebx, r12d
0x1800721f2  jge     short loc_180072203
0x1800721f4  mov     r8d, ebx
0x1800721f7  lea     rdx, aNtcreateeventF; "NtCreateEvent failed: 0x%x in %s"
0x1800721fe  jmp     loc_1800720B9
0x180072203  mov     eax, 7D00h
0x180072208  jmp     short loc_18007221D
0x18007220a  mov     [rdi+4028h], r10
0x180072211  mov     [rdi+4018h], r10
0x180072218  mov     eax, 7D01h
0x18007221d  mov     [rsi], eax
0x18007221f  mov     rcx, [rbp+var_48]
0x180072223  mov     rax, [rcx]
0x180072226  xor     r8d, r8d
0x180072229  mov     rdx, rdi
0x18007222c  mov     rax, [rax+80h]
0x180072233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072238  mov     ebx, eax
0x18007223a  xor     ecx, ecx
0x18007223c  test    eax, eax
0x18007223e  jns     short loc_18007224C
0x180072240  lea     rdx, aSenddomessageF; "SendDoMessage failed: 0x%x in %s"
0x180072247  jmp     loc_1800720B6
0x18007224c  cmp     [rbp+arg_30], ecx
0x18007224f  jnz     loc_1800722E6
0x180072255  mov     rax, [r13+0]
0x180072259  mov     [rbp+Handles], rax
0x18007225d  mov     rax, [r15+0CA0h]
0x180072264  mov     [rbp+var_38], rax
0x180072268  mov     dword ptr [rsp+80h+InitialState], ecx; bAlertable
0x18007226c  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180072270  xor     r8d, r8d; bWaitAll
0x180072273  lea     rdx, [rbp+Handles]; lpHandles
0x180072277  lea     ecx, [r8+2]; nCount
0x18007227b  call    cs:__imp_WaitForMultipleObjectsEx
0x180072282  nop     dword ptr [rax+rax+00h]
0x180072287  mov     ebx, eax
0x180072289  test    eax, eax
0x18007228b  jz      short loc_1800722B9
0x18007228d  cmp     eax, 1
0x180072290  jnz     short loc_180072299
0x180072292  mov     ebx, 80071B5Fh
0x180072297  jmp     short loc_1800722AA
0x180072299  test    ebx, ebx
0x18007229b  jle     short loc_1800722A8
0x18007229d  movzx   ebx, bx
0x1800722a0  or      ebx, 80070000h
0x1800722a6  test    ebx, ebx
0x1800722a8  jns     short loc_1800722B9
0x1800722aa  mov     r8d, ebx
0x1800722ad  lea     rdx, aWaitformultipl; "WaitForMultipleObjects failed: 0x%x in "...
0x1800722b4  jmp     loc_1800720B9
0x1800722b9  mov     ebx, [rbp+var_50]
0x1800722bc  or      ebx, r12d
0x1800722bf  jge     short loc_1800722D0
0x1800722c1  mov     r8d, ebx
0x1800722c4  lea     rdx, aSendmessageDel; "SendMessage delivery failed: 0x%x in %s"
0x1800722cb  jmp     loc_1800720B9
0x1800722d0  mov     r8d, [rsi]
0x1800722d3  lea     rdx, aShowmessagebox_0; "ShowMessageBox: got response %u"
0x1800722da  mov     ecx, 1; int
0x1800722df  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800722e4  jmp     short loc_180072300
0x1800722e6  mov     ebx, ecx
0x1800722e8  jmp     short loc_180072300
0x1800722ea  lea     rdx, aTooLongTitleDO; "Too long title (%d) or message (%d) str"...
0x1800722f1  mov     ecx, 8; int
0x1800722f6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800722fb  mov     ebx, 80070057h
0x180072300  mov     rcx, [r13+0]; Handle
0x180072304  test    rcx, rcx
0x180072307  jz      short loc_180072315
0x180072309  call    cs:__imp_NtClose
0x180072310  nop     dword ptr [rax+rax+00h]
0x180072315  mov     rcx, rdi; hMem
0x180072318  call    cs:__imp_LocalFree
0x18007231f  nop     dword ptr [rax+rax+00h]
0x180072324  nop
0x180072325  lea     rcx, [rbp+var_48]
0x180072329  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18007232e  mov     eax, ebx
0x180072330  lea     r11, [rsp+80h+var_s0]
0x180072338  mov     rbx, [r11+30h]
0x18007233c  mov     rsi, [r11+38h]
0x180072340  mov     rsp, r11
0x180072343  pop     r15
0x180072345  pop     r13
0x180072347  pop     r12
0x180072349  pop     rdi
0x18007234a  pop     rbp
0x18007234b  retn
```
