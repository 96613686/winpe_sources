# ClientSideConnection::StartFontCacheService(uint)

- ea: `0x1801ebf2c`
- end: `0x1801ec147`
- name: `?StartFontCacheService@ClientSideConnection@@SA_NI@Z`
- size: `539`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18012cf64`

## callees

- `0x18012a6b4`
- `0x18012e204`
- `0x18012e628`
- `0x18012f400`
- `0x1801e7ba8`
- `0x1801ebf2c`
- `0x18020bfec`
- `0x18020c624`
- `0x18020ce2c`
- `0x18020d144`
- `0x180212490`
- `0x180212f4c`

## import_xrefs

- `kernel32!GetLastError` at `0x1801ebfe6`
- `kernel32!GetLastError` at `0x1801ebfe6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801ebfcb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801ec027`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801ebfcb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801ec027`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1801ebfdc`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1801ebfdc`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1801ec071`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1801ec071`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall ClientSideConnection::StartFontCacheService(__int64 a1, unsigned int a2)
{
  const wchar_t *v2; // r8
  unsigned int v3; // r9d
  SC_HANDLE v4; // rbx
  signed int LastError; // eax
  signed int v7; // edi
  __int64 v8; // rdx
  DWORD v9; // ebx
  EventTag *v10; // rax
  char v11; // di
  bool v12; // bl
  EventTag *v13; // rax
  SC_HANDLE hService; // [rsp+20h] [rbp-39h] BYREF
  unsigned int v15; // [rsp+28h] [rbp-31h]
  HANDLE hHandle; // [rsp+30h] [rbp-29h] BYREF
  SC_HANDLE hSCObject; // [rsp+38h] [rbp-21h] BYREF
  unsigned int v18; // [rsp+40h] [rbp-19h]
  _BYTE v19[8]; // [rsp+48h] [rbp-11h] BYREF
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+50h] [rbp-9h] BYREF

  ServiceControlManager::ServiceControlManager((ServiceControlManager *)&hSCObject, a2);
  v4 = hSCObject;
  if ( !hSCObject )
  {
    LogEvent<long,EventTag,unsigned int>(g_errorTag, v18, 0x6D63736E65706FLL, 215);
    ServiceControlManager::~ServiceControlManager((ServiceControlManager *)&hSCObject);
    return 0;
  }
  ServiceHandle::ServiceHandle((ServiceHandle *)&hService, hSCObject, v2, v3);
  if ( !hService )
  {
    LogEvent<long,EventTag,unsigned int>(g_errorTag, v15, 0x6376736E65706FLL, 228);
LABEL_6:
    CloseServiceHandle(v4);
    return 0;
  }
  if ( !StartServiceW(hService, 0, 0) )
  {
    LastError = GetLastError();
    v7 = LastError;
    v8 = LastError > 0 ? (unsigned __int16)LastError | 0x80070000 : (unsigned int)LastError;
    LogEvent<long,EventTag,unsigned int>(g_errorTag, v8, 0x6376737472617473LL, 241);
    if ( v7 != 1056 )
    {
      CloseServiceHandle(hService);
      goto LABEL_6;
    }
  }
  ManualResetEvent::ManualResetEvent((ManualResetEvent *)&hHandle, 0);
  memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
  pNotifyBuffer.dwVersion = 2;
  pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)ServiceStartNotifyCallback;
  pNotifyBuffer.pContext = &hHandle;
  v9 = NotifyServiceStatusChangeW(hService, 9u, &pNotifyBuffer);
  if ( v9 )
  {
    ServiceHandle::Close((ServiceHandle *)&hService);
    v10 = EventTag::EventTag((EventTag *)v19, (const char (*)[9])"startsvc");
    LogEvent<long,EventTag,unsigned int>(g_errorTag, v9, *(_QWORD *)v10, 278);
    v11 = 0;
  }
  else
  {
    v11 = 1;
    v12 = Event::Wait(hHandle, 0x7D0u, 1);
    ServiceHandle::Close((ServiceHandle *)&hService);
    if ( !v12 || pNotifyBuffer.ServiceStatus.dwCurrentState != 4 )
    {
      v11 = 0;
      v13 = EventTag::EventTag((EventTag *)v19, (const char (*)[9])"startsvc");
      LogEvent<long,EventTag,unsigned int>(g_errorTag, 0, *(_QWORD *)v13, 294);
    }
  }
  ScopedHandle<EventHandlePolicy,void *>::~ScopedHandle<EventHandlePolicy,void *>(&hHandle);
  ServiceHandle::Close((ServiceHandle *)&hService);
  ServiceControlManager::~ServiceControlManager((ServiceControlManager *)&hSCObject);
  return v11;
}

```

## disassembly

```asm
0x1801ebf2c  mov     [rsp-8+arg_0], rbx
0x1801ebf31  mov     [rsp-8+arg_8], rdi
0x1801ebf36  push    rbp
0x1801ebf37  lea     rbp, [rsp-57h]
0x1801ebf3c  sub     rsp, 0B0h
0x1801ebf43  mov     rax, cs:__security_cookie
0x1801ebf4a  xor     rax, rsp
0x1801ebf4d  mov     [rbp+57h+var_10], rax
0x1801ebf51  lea     rcx, [rbp+57h+hSCObject]; this
0x1801ebf55  call    ??0ServiceControlManager@@QEAA@K@Z; ServiceControlManager::ServiceControlManager(ulong)
0x1801ebf5a  nop
0x1801ebf5b  mov     rbx, [rbp+57h+hSCObject]
0x1801ebf5f  test    rbx, rbx
0x1801ebf62  jnz     short loc_1801EBF94
0x1801ebf64  mov     r8, 6D63736E65706Fh
0x1801ebf6e  mov     r9d, 0D7h
0x1801ebf74  mov     edx, [rbp+57h+var_70]
0x1801ebf77  mov     rcx, cs:?g_errorTag@@3VEventTag@@B; EventTag const g_errorTag
0x1801ebf7e  call    ??$LogEvent@JVEventTag@@I@@YAXVEventTag@@J0I@Z; LogEvent<long,EventTag,uint>(EventTag,long,EventTag,uint)
0x1801ebf83  nop
0x1801ebf84  lea     rcx, [rbp+57h+hSCObject]; this
0x1801ebf88  call    ??1ServiceControlManager@@QEAA@XZ; ServiceControlManager::~ServiceControlManager(void)
0x1801ebf8d  xor     al, al
0x1801ebf8f  jmp     loc_1801EC126
0x1801ebf94  mov     rdx, rbx; struct SC_HANDLE__ *
0x1801ebf97  lea     rcx, [rbp+57h+hService]; this
0x1801ebf9b  call    ??0ServiceHandle@@QEAA@PEAUSC_HANDLE__@@PEB_WK@Z; ServiceHandle::ServiceHandle(SC_HANDLE__ *,wchar_t const *,ulong)
0x1801ebfa0  nop
0x1801ebfa1  cmp     [rbp+57h+hService], 0
0x1801ebfa6  jnz     short loc_1801EBFD3
0x1801ebfa8  mov     r8, 6376736E65706Fh
0x1801ebfb2  mov     r9d, 0E4h
0x1801ebfb8  mov     edx, [rbp+57h+var_88]
0x1801ebfbb  mov     rcx, cs:?g_errorTag@@3VEventTag@@B; EventTag const g_errorTag
0x1801ebfc2  call    ??$LogEvent@JVEventTag@@I@@YAXVEventTag@@J0I@Z; LogEvent<long,EventTag,uint>(EventTag,long,EventTag,uint)
0x1801ebfc7  nop
0x1801ebfc8  mov     rcx, rbx; hSCObject
0x1801ebfcb  call    cs:__imp_CloseServiceHandle
0x1801ebfd1  jmp     short loc_1801EBF8D
0x1801ebfd3  xor     r8d, r8d; lpServiceArgVectors
0x1801ebfd6  xor     edx, edx; dwNumServiceArgs
0x1801ebfd8  mov     rcx, [rbp+57h+hService]; hService
0x1801ebfdc  call    cs:__imp_StartServiceW
0x1801ebfe2  test    eax, eax
0x1801ebfe4  jnz     short loc_1801EC02F
0x1801ebfe6  call    cs:__imp_GetLastError
0x1801ebfec  mov     edi, eax
0x1801ebfee  test    eax, eax
0x1801ebff0  jg      short loc_1801EBFF6
0x1801ebff2  mov     edx, eax
0x1801ebff4  jmp     short loc_1801EBFFF
0x1801ebff6  movzx   edx, di
0x1801ebff9  or      edx, 80070000h
0x1801ebfff  mov     r8, 6376737472617473h
0x1801ec009  mov     r9d, 0F1h
0x1801ec00f  mov     rcx, cs:?g_errorTag@@3VEventTag@@B; EventTag const g_errorTag
0x1801ec016  call    ??$LogEvent@JVEventTag@@I@@YAXVEventTag@@J0I@Z; LogEvent<long,EventTag,uint>(EventTag,long,EventTag,uint)
0x1801ec01b  cmp     edi, 420h
0x1801ec021  jz      short loc_1801EC02F
0x1801ec023  mov     rcx, [rbp+57h+hService]; hSCObject
0x1801ec027  call    cs:__imp_CloseServiceHandle
0x1801ec02d  jmp     short loc_1801EBFC8
0x1801ec02f  xor     edx, edx; bool
0x1801ec031  lea     rcx, [rbp+57h+hHandle]; this
0x1801ec035  call    ??0ManualResetEvent@@QEAA@_N@Z; ManualResetEvent::ManualResetEvent(bool)
0x1801ec03a  nop
0x1801ec03b  xor     edx, edx; Val
0x1801ec03d  lea     r8d, [rdx+50h]; Size
0x1801ec041  lea     rcx, [rbp+57h+pNotifyBuffer]; void *
0x1801ec045  call    memset_0
0x1801ec04a  mov     [rbp+57h+pNotifyBuffer.dwVersion], 2
0x1801ec051  lea     rax, ?ServiceStartNotifyCallback@@YAXPEAX@Z; ServiceStartNotifyCallback(void *)
0x1801ec058  mov     [rbp+57h+pNotifyBuffer.pfnNotifyCallback], rax
0x1801ec05c  lea     rax, [rbp+57h+hHandle]
0x1801ec060  mov     [rbp+57h+pNotifyBuffer.pContext], rax
0x1801ec064  lea     r8, [rbp+57h+pNotifyBuffer]; pNotifyBuffer
0x1801ec068  mov     edx, 9; dwNotifyMask
0x1801ec06d  mov     rcx, [rbp+57h+hService]; hService
0x1801ec071  call    cs:__imp_NotifyServiceStatusChangeW
0x1801ec077  mov     ebx, eax
0x1801ec079  test    eax, eax
0x1801ec07b  jz      short loc_1801EC0B2
0x1801ec07d  lea     rcx, [rbp+57h+hService]; this
0x1801ec081  call    ?Close@ServiceHandle@@QEAAXXZ; ServiceHandle::Close(void)
0x1801ec086  lea     rdx, aStartsvc; "startsvc"
0x1801ec08d  lea     rcx, [rbp+57h+var_68]; this
0x1801ec091  call    ??0EventTag@@QEAA@AEAY08$$CBD@Z; EventTag::EventTag(char const (&)[9])
0x1801ec096  mov     r9d, 116h
0x1801ec09c  mov     r8, [rax]
0x1801ec09f  mov     edx, ebx
0x1801ec0a1  mov     rcx, cs:?g_errorTag@@3VEventTag@@B; EventTag const g_errorTag
0x1801ec0a8  call    ??$LogEvent@JVEventTag@@I@@YAXVEventTag@@J0I@Z; LogEvent<long,EventTag,uint>(EventTag,long,EventTag,uint)
0x1801ec0ad  xor     dil, dil
0x1801ec0b0  jmp     short loc_1801EC106
0x1801ec0b2  mov     dil, 1
0x1801ec0b5  mov     r8b, dil; bool
0x1801ec0b8  mov     edx, 7D0h; dwMilliseconds
0x1801ec0bd  mov     rcx, [rbp+57h+hHandle]; hHandle
0x1801ec0c1  call    ?Wait@Event@@SA_NPEAXI_N@Z; Event::Wait(void *,uint,bool)
0x1801ec0c6  mov     bl, al
0x1801ec0c8  lea     rcx, [rbp+57h+hService]; this
0x1801ec0cc  call    ?Close@ServiceHandle@@QEAAXXZ; ServiceHandle::Close(void)
0x1801ec0d1  test    bl, bl
0x1801ec0d3  jz      short loc_1801EC0DB
0x1801ec0d5  cmp     [rbp+57h+pNotifyBuffer.ServiceStatus.dwCurrentState], 4
0x1801ec0d9  jz      short loc_1801EC106
0x1801ec0db  xor     dil, dil
0x1801ec0de  lea     rdx, aStartsvc; "startsvc"
0x1801ec0e5  lea     rcx, [rbp+57h+var_68]; this
0x1801ec0e9  call    ??0EventTag@@QEAA@AEAY08$$CBD@Z; EventTag::EventTag(char const (&)[9])
0x1801ec0ee  mov     r9d, 126h
0x1801ec0f4  mov     r8, [rax]
0x1801ec0f7  xor     edx, edx
0x1801ec0f9  mov     rcx, cs:?g_errorTag@@3VEventTag@@B; EventTag const g_errorTag
0x1801ec100  call    ??$LogEvent@JVEventTag@@I@@YAXVEventTag@@J0I@Z; LogEvent<long,EventTag,uint>(EventTag,long,EventTag,uint)
0x1801ec105  nop
0x1801ec106  lea     rcx, [rbp+57h+hHandle]
0x1801ec10a  call    ??1?$ScopedHandle@UEventHandlePolicy@@PEAX@@QEAA@XZ; ScopedHandle<EventHandlePolicy,void *>::~ScopedHandle<EventHandlePolicy,void *>(void)
0x1801ec10f  nop
0x1801ec110  lea     rcx, [rbp+57h+hService]; this
0x1801ec114  call    ?Close@ServiceHandle@@QEAAXXZ; ServiceHandle::Close(void)
0x1801ec119  nop
0x1801ec11a  lea     rcx, [rbp+57h+hSCObject]; this
0x1801ec11e  call    ??1ServiceControlManager@@QEAA@XZ; ServiceControlManager::~ServiceControlManager(void)
0x1801ec123  mov     al, dil
0x1801ec126  mov     rcx, [rbp+57h+var_10]
0x1801ec12a  xor     rcx, rsp; StackCookie
0x1801ec12d  call    __security_check_cookie
0x1801ec132  lea     r11, [rsp+0B0h+var_s0]
0x1801ec13a  mov     rbx, [r11+10h]
0x1801ec13e  mov     rdi, [r11+18h]
0x1801ec142  mov     rsp, r11
0x1801ec145  pop     rbp
0x1801ec146  retn
```
