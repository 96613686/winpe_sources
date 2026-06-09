# CHttpWriter::~CHttpWriter(void)

- ea: `0x1800bb4d8`
- end: `0x1800bb6b3`
- name: `??1CHttpWriter@@UEAA@XZ`
- size: `475`
- prototype: `void __fastcall(CHttpWriter *__hidden this)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800bb800`
- `0x1800f305c`
- `0x1800f38f0`

## callees

- `0x180014310`
- `0x180016d60`
- `0x18001d7f0`
- `0x180063c98`
- `0x180063e30`
- `0x1800646a4`
- `0x180067560`
- `0x18006c7f8`
- `0x18007bb30`
- `0x180083654`
- `0x18008ddc8`
- `0x1800ab7fc`
- `0x1800bb4d8`
- `0x1800bb83c`
- `0x1800cc2d0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bb52c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bb52c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800bb51f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800bb51f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb661`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb66e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb661`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb66e`

## pseudocode

```c
void __fastcall CHttpWriter::~CHttpWriter(CHttpWriter *this, unsigned int a2, bool a3)
{
  char *v4; // rsi
  struct _TP_WORK *v5; // rcx
  CHttpWriter::CRequest *v6; // rcx
  URL_INFO *v7; // rcx

  *(_QWORD *)this = &CHttpWriter::`vftable'{for `CAbstractFile'};
  v4 = (char *)this + 304;
  *((_QWORD *)this + 38) = &CHttpWriter::`vftable'{for `AbstractIoThreadAwareWinHttpCallbackHandler'};
  *((_QWORD *)this + 65) = &CHttpWriter::`vftable'{for `AbstractHttpServerCertificateHandler'};
  v5 = (struct _TP_WORK *)*((_QWORD *)this + 175);
  if ( v5 )
  {
    WaitForThreadpoolWorkCallbacks(v5, 1);
    CloseThreadpoolWork(*((PTP_WORK *)this + 175));
    *((_QWORD *)this + 175) = 0;
  }
  v6 = (CHttpWriter::CRequest *)*((_QWORD *)this + 89);
  if ( v6 )
    CHttpWriter::CRequest::`scalar deleting destructor'(v6, a2);
  v7 = (URL_INFO *)*((_QWORD *)this + 88);
  *((_QWORD *)this + 89) = 0;
  if ( v7 )
    URL_INFO::`scalar deleting destructor'(v7, a2);
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, &WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids, this);
  CEvent::Wait((CHttpWriter *)((char *)this + 736), 0xFFFFFFFF, a3);
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 176, &WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids, this);
  AutoThreadpool::UninitializeAndWaitForPendingWorkItems((AutoThreadpool *)(v4 + 16));
  GenericStringHandle<unsigned short>::FreeIt((char *)this + 1408);
  TokenHandle::Decrement((CHttpWriter *)((char *)this + 1120));
  TokenHandle::Decrement((CHttpWriter *)((char *)this + 1112));
  SidHandle::~SidHandle((CHttpWriter *)((char *)this + 1088));
  GenericStringHandle<unsigned short>::FreeIt((char *)this + 1080);
  EidAsyncHelper::~EidAsyncHelper((LPCRITICAL_SECTION)((char *)this + 952));
  UPLOAD_DATA::~UPLOAD_DATA((CHttpWriter *)((char *)this + 864));
  GenericStringHandle<unsigned short>::FreeIt((char *)this + 856);
  GenericStringHandle<unsigned short>::FreeIt((char *)this + 840);
  GenericStringHandle<unsigned short>::FreeIt((char *)this + 816);
  CloseHandle(*((HANDLE *)this + 92));
  CloseHandle(*((HANDLE *)this + 91));
  std::wstring::~wstring((char *)this + 600);
  *((_QWORD *)this + 65) = &AbstractHttpServerCertificateHandler::`vftable';
  CCritSec2::~CCritSec2((CHttpWriter *)((char *)this + 536));
  AbstractIoThreadAwareWinHttpCallbackHandler::~AbstractIoThreadAwareWinHttpCallbackHandler((AbstractIoThreadAwareWinHttpCallbackHandler *)v4);
  CAbstractFile::~CAbstractFile(this);
}

```

## disassembly

```asm
0x1800bb4d8  push    rbx
0x1800bb4da  push    rsi
0x1800bb4db  push    rdi
0x1800bb4dc  push    r14
0x1800bb4de  sub     rsp, 28h
0x1800bb4e2  lea     rax, ??_7CHttpWriter@@6BCAbstractFile@@@; const CHttpWriter::`vftable'{for `CAbstractFile'}
0x1800bb4e9  mov     rbx, rcx
0x1800bb4ec  mov     [rcx], rax
0x1800bb4ef  lea     rsi, [rcx+130h]
0x1800bb4f6  lea     rax, ??_7CHttpWriter@@6BAbstractIoThreadAwareWinHttpCallbackHandler@@@; const CHttpWriter::`vftable'{for `AbstractIoThreadAwareWinHttpCallbackHandler'}
0x1800bb4fd  mov     [rsi], rax
0x1800bb500  lea     rax, ??_7CHttpWriter@@6BAbstractHttpServerCertificateHandler@@@; const CHttpWriter::`vftable'{for `AbstractHttpServerCertificateHandler'}
0x1800bb507  mov     [rcx+208h], rax
0x1800bb50e  mov     rcx, [rcx+578h]; pwk
0x1800bb515  test    rcx, rcx
0x1800bb518  jz      short loc_1800BB53D
0x1800bb51a  mov     edx, 1; fCancelPendingCallbacks
0x1800bb51f  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800bb525  mov     rcx, [rbx+578h]; pwk
0x1800bb52c  call    cs:__imp_CloseThreadpoolWork
0x1800bb532  mov     qword ptr [rbx+578h], 0
0x1800bb53d  mov     rcx, [rbx+2C8h]; this
0x1800bb544  test    rcx, rcx
0x1800bb547  jz      short loc_1800BB54E
0x1800bb549  call    ??_GCRequest@CHttpWriter@@QEAAPEAXI@Z; CHttpWriter::CRequest::`scalar deleting destructor'(uint)
0x1800bb54e  mov     rcx, [rbx+2C0h]; this
0x1800bb555  mov     qword ptr [rbx+2C8h], 0
0x1800bb560  test    rcx, rcx
0x1800bb563  jz      short loc_1800BB56A
0x1800bb565  call    ??_GURL_INFO@@QEAAPEAXI@Z; URL_INFO::`scalar deleting destructor'(uint)
0x1800bb56a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb571  lea     r14, WPP_GLOBAL_Control
0x1800bb578  cmp     rcx, r14
0x1800bb57b  jz      short loc_1800BB59E
0x1800bb57d  test    dword ptr [rcx+1Ch], 800h
0x1800bb584  jz      short loc_1800BB59E
0x1800bb586  mov     rcx, [rcx+10h]
0x1800bb58a  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x1800bb591  mov     edx, 0AFh
0x1800bb596  mov     r9, rbx
0x1800bb599  call    WPP_SF_q
0x1800bb59e  lea     rdi, [rbx+2E0h]
0x1800bb5a5  or      edx, 0FFFFFFFFh; unsigned int
0x1800bb5a8  mov     rcx, rdi; this
0x1800bb5ab  call    ?Wait@CEvent@@QEBAKK_N@Z; CEvent::Wait(ulong,bool)
0x1800bb5b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb5b7  cmp     rcx, r14
0x1800bb5ba  jz      short loc_1800BB5DD
0x1800bb5bc  test    dword ptr [rcx+1Ch], 800h
0x1800bb5c3  jz      short loc_1800BB5DD
0x1800bb5c5  mov     rcx, [rcx+10h]
0x1800bb5c9  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x1800bb5d0  mov     edx, 0B0h
0x1800bb5d5  mov     r9, rbx
0x1800bb5d8  call    WPP_SF_q
0x1800bb5dd  lea     rcx, [rsi+10h]; this
0x1800bb5e1  call    ?UninitializeAndWaitForPendingWorkItems@AutoThreadpool@@QEAAXXZ; AutoThreadpool::UninitializeAndWaitForPendingWorkItems(void)
0x1800bb5e6  lea     rcx, [rbx+580h]
0x1800bb5ed  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x1800bb5f2  lea     rcx, [rbx+460h]; this
0x1800bb5f9  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x1800bb5fe  lea     rcx, [rbx+458h]; this
0x1800bb605  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x1800bb60a  lea     rcx, [rbx+440h]; this
0x1800bb611  call    ??1SidHandle@@QEAA@XZ; SidHandle::~SidHandle(void)
0x1800bb616  lea     rcx, [rbx+438h]
0x1800bb61d  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x1800bb622  lea     rcx, [rbx+3B8h]; lpCriticalSection
0x1800bb629  call    ??1EidAsyncHelper@@QEAA@XZ; EidAsyncHelper::~EidAsyncHelper(void)
0x1800bb62e  lea     rcx, [rbx+360h]; this
0x1800bb635  call    ??1UPLOAD_DATA@@QEAA@XZ; UPLOAD_DATA::~UPLOAD_DATA(void)
0x1800bb63a  lea     rcx, [rbx+358h]
0x1800bb641  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x1800bb646  lea     rcx, [rbx+348h]
0x1800bb64d  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x1800bb652  lea     rcx, [rbx+330h]
0x1800bb659  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x1800bb65e  mov     rcx, [rdi]; hObject
0x1800bb661  call    cs:__imp_CloseHandle
0x1800bb667  mov     rcx, [rbx+2D8h]; hObject
0x1800bb66e  call    cs:__imp_CloseHandle
0x1800bb674  lea     rcx, [rbx+258h]
0x1800bb67b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800bb680  lea     rax, ??_7AbstractHttpServerCertificateHandler@@6B@; const AbstractHttpServerCertificateHandler::`vftable'
0x1800bb687  lea     rcx, [rbx+218h]; this
0x1800bb68e  mov     [rbx+208h], rax
0x1800bb695  call    ??1CCritSec2@@QEAA@XZ; CCritSec2::~CCritSec2(void)
0x1800bb69a  mov     rcx, rsi; this
0x1800bb69d  call    ??1AbstractIoThreadAwareWinHttpCallbackHandler@@UEAA@XZ; AbstractIoThreadAwareWinHttpCallbackHandler::~AbstractIoThreadAwareWinHttpCallbackHandler(void)
0x1800bb6a2  mov     rcx, rbx; this
0x1800bb6a5  add     rsp, 28h
0x1800bb6a9  pop     r14
0x1800bb6ab  pop     rdi
0x1800bb6ac  pop     rsi
0x1800bb6ad  pop     rbx
0x1800bb6ae  jmp     ??1CAbstractFile@@UEAA@XZ; CAbstractFile::~CAbstractFile(void)
```
