# CAsyncRxThread::CreateCallbackRequest(CCallbackDescriptor * *,void *,ulong,ulong,tagMQMSGPROPS *,_OVERLAPPED *,void (*)(long,void *,ulong,ulong,tagMQMSGPROPS *,_OVERLAPPED *,void *),void *)

- ea: `0x18001a1b8`
- end: `0x18001a3a8`
- name: `?CreateCallbackRequest@CAsyncRxThread@@QEAAXPEAPEAVCCallbackDescriptor@@PEAXKKPEAUtagMQMSGPROPS@@PEAU_OVERLAPPED@@P6AXJ1KK231@Z1@Z`
- size: `496`
- prototype: `void __fastcall(CAsyncRxThread *__hidden this, struct CCallbackDescriptor **, void *, unsigned int, unsigned int, struct tagMQMSGPROPS *, struct _OVERLAPPED *, void (*)(int, void *, unsigned int, unsigned int, struct tagMQMSGPROPS *, struct _OVERLAPPED *, void *), void *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001cca4`

## callees

- `0x1800022d6`
- `0x1800093d0`
- `0x18000da78`
- `0x180013bbc`
- `0x180013bdc`
- `0x180013d20`
- `0x18001a1b8`
- `0x18001a49c`
- `0x180021010`

## import_xrefs

- `msvcrt!free` at `0x18001a374`
- `msvcrt!free` at `0x18001a374`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18001a235`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18001a235`
- `KERNEL32!SetEvent` at `0x18001a31b`
- `KERNEL32!SetEvent` at `0x18001a31b`
- `KERNEL32!CreateEventW` at `0x18001a261`
- `KERNEL32!CreateEventW` at `0x18001a261`
- `KERNEL32!GetLastError` at `0x18001a273`
- `KERNEL32!GetLastError` at `0x18001a32b`
- `KERNEL32!GetLastError` at `0x18001a273`
- `KERNEL32!GetLastError` at `0x18001a32b`
- `KERNEL32!LeaveCriticalSection` at `0x18001a388`
- `KERNEL32!LeaveCriticalSection` at `0x18001a388`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CAsyncRxThread::CreateCallbackRequest(
        CAsyncRxThread *this,
        struct CCallbackDescriptor **a2,
        void *a3,
        int a4,
        unsigned int a5,
        struct tagMQMSGPROPS *a6,
        struct _OVERLAPPED *a7,
        void (*a8)(int, void *, unsigned int, unsigned int, struct tagMQMSGPROPS *, struct _OVERLAPPED *, void *),
        void *a9)
{
  CAsyncRxThread *v12; // rcx
  CAsyncRxThread *EventW; // rdi
  DWORD LastError; // eax
  unsigned int v15; // ebx
  _QWORD *v16; // rbx
  DWORD v17; // eax
  unsigned int v18; // ebx
  _QWORD pExceptionObject[4]; // [rsp+30h] [rbp-20h] BYREF
  CAsyncRxThread *v20; // [rsp+80h] [rbp+30h] BYREF

  v20 = this;
  CCriticalSection::Lock((CCriticalSection *)&g_AsyncRxThread);
  if ( !byte_18003D498 )
  {
    CAsyncRxThread::Initialize(v12);
    byte_18003D498 = 1;
  }
  if ( (unsigned int)dword_18003D4B8 >= 0x40 )
  {
    LogIllegalPoint((wchar_t *)L"rt/CRtReceive", 0x4B7u);
    exception::exception((exception *)pExceptionObject, &std::_bad_alloc_Message, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  EventW = (CAsyncRxThread *)CreateEventW(0, 1, 0, 0);
  v20 = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError )
      LogMsgNTStatus(LastError, (wchar_t *)L"rt/CRtReceive", 0x4B8u);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v15);
    throw (bad_win32_error *)pExceptionObject;
  }
  v16 = MmAllocate(0x58u);
  *(_BYTE *)v16 = 0;
  v16[1] = a3;
  *((_DWORD *)v16 + 4) = a4;
  *((_DWORD *)v16 + 5) = a5;
  v16[3] = a6;
  v16[4] = a7;
  v16[6] = a8;
  v16[5] = a9;
  v16[10] = EventW;
  *((_QWORD *)&g_AsyncRxThread + (unsigned int)dword_18003D4B8 + 74) = EventW;
  *((_QWORD *)&g_AsyncRxThread + (unsigned int)dword_18003D4B8++ + 10) = v16;
  if ( !SetEvent(hEvent) )
  {
    --dword_18003D4B8;
    v17 = GetLastError();
    v18 = v17;
    if ( v17 )
      LogMsgNTStatus(v17, (wchar_t *)L"rt/CRtReceive", 0x4B9u);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v18);
    throw (bad_win32_error *)pExceptionObject;
  }
  v20 = 0;
  *a2 = (struct CCallbackDescriptor *)v16;
  free(0);
  CHandle::~CHandle((CHandle *)&v20);
  LeaveCriticalSection(&g_AsyncRxThread);
}

```

## disassembly

```asm
0x18001a1b8  mov     [rsp-28h+arg_8], rbx
0x18001a1bd  mov     [rsp-28h+arg_10], rsi
0x18001a1c2  mov     [rsp-28h+arg_0], rcx
0x18001a1c7  push    rbp
0x18001a1c8  push    rdi
0x18001a1c9  push    r13
0x18001a1cb  push    r14
0x18001a1cd  push    r15
0x18001a1cf  mov     rbp, rsp
0x18001a1d2  sub     rsp, 50h
0x18001a1d6  mov     r14d, r9d
0x18001a1d9  mov     r15, r8
0x18001a1dc  mov     rsi, rdx
0x18001a1df  lea     r13, ?g_AsyncRxThread@@3VCAsyncRxThread@@A; CAsyncRxThread g_AsyncRxThread
0x18001a1e6  mov     [rbp+var_30], r13
0x18001a1ea  mov     rcx, r13; this
0x18001a1ed  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001a1f2  nop
0x18001a1f3  mov     ebx, 1
0x18001a1f8  cmp     cs:byte_18003D498, 0
0x18001a1ff  jnz     short loc_18001A20C
0x18001a201  call    ?Initialize@CAsyncRxThread@@AEAAXXZ; CAsyncRxThread::Initialize(void)
0x18001a206  mov     cs:byte_18003D498, bl
0x18001a20c  cmp     cs:dword_18003D4B8, 40h ; '@'
0x18001a213  jb      short loc_18001A257
0x18001a215  mov     edx, 4B7h; unsigned __int16
0x18001a21a  lea     rcx, aRtCrtreceive; "rt/CRtReceive"
0x18001a221  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x18001a226  nop
0x18001a227  mov     r8d, ebx
0x18001a22a  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x18001a231  lea     rcx, [rbp+pExceptionObject]
0x18001a235  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18001a23b  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001a242  mov     [rbp+pExceptionObject], rax
0x18001a246  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001a24d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a251  call    _CxxThrowException_0
0x18001a257  xor     r9d, r9d; lpName
0x18001a25a  xor     r8d, r8d; bInitialState
0x18001a25d  mov     edx, ebx; bManualReset
0x18001a25f  xor     ecx, ecx; lpEventAttributes
0x18001a261  call    cs:__imp_CreateEventW
0x18001a267  mov     rdi, rax
0x18001a26a  mov     [rbp+arg_0], rax
0x18001a26e  test    rax, rax
0x18001a271  jnz     short loc_18001A2AF
0x18001a273  call    cs:__imp_GetLastError
0x18001a279  mov     ebx, eax
0x18001a27b  test    eax, eax
0x18001a27d  jz      short loc_18001A293
0x18001a27f  mov     r8d, 4B8h; unsigned __int16
0x18001a285  lea     rdx, aRtCrtreceive; "rt/CRtReceive"
0x18001a28c  mov     ecx, eax; int
0x18001a28e  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18001a293  mov     edx, ebx; unsigned int
0x18001a295  lea     rcx, [rbp+pExceptionObject]; this
0x18001a299  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18001a29e  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18001a2a5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a2a9  call    _CxxThrowException_0
0x18001a2af  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001a2b4  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001a2b9  mov     rbx, rax
0x18001a2bc  mov     [rbp+var_28], rax
0x18001a2c0  mov     byte ptr [rax], 0
0x18001a2c3  mov     [rax+8], r15
0x18001a2c7  mov     [rax+10h], r14d
0x18001a2cb  mov     eax, [rbp+arg_20]
0x18001a2ce  mov     [rbx+14h], eax
0x18001a2d1  mov     rax, [rbp+arg_28]
0x18001a2d5  mov     [rbx+18h], rax
0x18001a2d9  mov     rax, [rbp+arg_30]
0x18001a2dd  mov     [rbx+20h], rax
0x18001a2e1  mov     rax, [rbp+arg_38]
0x18001a2e5  mov     [rbx+30h], rax
0x18001a2e9  mov     rax, [rbp+arg_40]
0x18001a2ed  mov     [rbx+28h], rax
0x18001a2f1  mov     [rbx+50h], rdi
0x18001a2f5  mov     eax, cs:dword_18003D4B8
0x18001a2fb  mov     [r13+rax*8+250h], rdi
0x18001a303  mov     eax, cs:dword_18003D4B8
0x18001a309  mov     [r13+rax*8+50h], rbx
0x18001a30e  inc     cs:dword_18003D4B8
0x18001a314  mov     rcx, cs:hEvent; hEvent
0x18001a31b  call    cs:__imp_SetEvent
0x18001a321  test    eax, eax
0x18001a323  jnz     short loc_18001A367
0x18001a325  dec     cs:dword_18003D4B8
0x18001a32b  call    cs:__imp_GetLastError
0x18001a331  mov     ebx, eax
0x18001a333  test    eax, eax
0x18001a335  jz      short loc_18001A34B
0x18001a337  mov     r8d, 4B9h; unsigned __int16
0x18001a33d  lea     rdx, aRtCrtreceive; "rt/CRtReceive"
0x18001a344  mov     ecx, eax; int
0x18001a346  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18001a34b  mov     edx, ebx; unsigned int
0x18001a34d  lea     rcx, [rbp+pExceptionObject]; this
0x18001a351  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18001a356  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18001a35d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a361  call    _CxxThrowException_0
0x18001a367  mov     [rbp+arg_0], 0
0x18001a36f  mov     [rsi], rbx
0x18001a372  xor     ecx, ecx; Block
0x18001a374  call    cs:__imp_free
0x18001a37a  nop
0x18001a37b  lea     rcx, [rbp+arg_0]; this
0x18001a37f  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18001a384  nop
0x18001a385  mov     rcx, r13; lpCriticalSection
0x18001a388  call    cs:__imp_LeaveCriticalSection
0x18001a38e  nop
0x18001a38f  lea     r11, [rsp+50h+var_s0]
0x18001a394  mov     rbx, [r11+38h]
0x18001a398  mov     rsi, [r11+40h]
0x18001a39c  mov     rsp, r11
0x18001a39f  pop     r15
0x18001a3a1  pop     r14
0x18001a3a3  pop     r13
0x18001a3a5  pop     rdi
0x18001a3a6  pop     rbp
0x18001a3a7  retn
```
