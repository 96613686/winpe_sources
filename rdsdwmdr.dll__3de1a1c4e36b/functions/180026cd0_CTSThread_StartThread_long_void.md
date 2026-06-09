# CTSThread::StartThread(long (*)(void *))

- ea: `0x180026cd0`
- end: `0x180027094`
- name: `?StartThread@CTSThread@@UEAAJP6AJPEAX@Z@Z`
- size: `964`
- prototype: `__int64 __fastcall(CTSThread *__hidden this, int (*)(void *))`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1800010f8`
- `0x180001564`
- `0x18000160c`
- `0x180001bfc`
- `0x180001f98`
- `0x18001e8e0`
- `0x18001f298`
- `0x180026cd0`
- `0x180027b6c`
- `0x180027b98`
- `0x180028b88`
- `0x18002a1c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026db9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026db9`

## string_xrefs

- `0x180026d61`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180026e4e`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180026d4d`: `StartThread`
- `0x180026e41`: `StartThread`
- `0x180026d3b`: `Entry function does not exist can't start thread`
- `0x180026dd6`: `start sync event %p created - now create thread`
- `0x180026e77`: `Thread exited with error code: 0x%x`
- `0x180026ee1`: `Thread exited with success error code`
- `0x180026f0e`: `thread %d created successfully`

## pseudocode

```c
__int64 __fastcall CTSThread::StartThread(CTSThread *this, int (*a2)(void *))
{
  CTSReaderWriterLock *v4; // r13
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  int v8; // ebx
  unsigned int (*v9)(void *); // rcx
  unsigned __int16 *EventW; // rdi
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx
  _UNKNOWN **v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // esi
  void *v18; // r12
  unsigned int ActivityIdPrefix; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // r9
  const char *v25; // [rsp+50h] [rbp-29h] BYREF
  const char *v26; // [rsp+58h] [rbp-21h] BYREF
  const char *v27; // [rsp+60h] [rbp-19h] BYREF
  __int128 v28; // [rsp+68h] [rbp-11h] BYREF
  __int128 v29; // [rsp+78h] [rbp-1h]
  __int128 v30; // [rsp+88h] [rbp+Fh]
  const char *v31; // [rsp+E0h] [rbp+67h] BYREF
  void *v32; // [rsp+F0h] [rbp+77h] BYREF
  const char *v33; // [rsp+F8h] [rbp+7Fh] BYREF

  LODWORD(v31) = 0;
  v28 = 0;
  v29 = 0;
  v32 = 0;
  v30 = 0;
  v4 = (CTSThread *)((char *)this + 148);
  CTSReaderWriterLock::WriteLock((CTSThread *)((char *)this + 148));
  if ( *((_DWORD *)this + 20) != 1 )
    goto LABEL_28;
  if ( !*((_QWORD *)this + 11) )
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v31) = 703;
      v26 = "Entry function does not exist can't start thread";
      v33 = "StartThread";
      v25 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      LODWORD(v32) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v5,
        (__int64)word_18003FC12,
        v6,
        v7,
        (const unsigned __int16 **)&v26,
        (__int64)&v32,
        (const unsigned __int16 **)&v25,
        (__int64)&v31,
        (const unsigned __int16 **)&v33);
    }
    v8 = -2147024809;
    goto LABEL_29;
  }
  EventW = (unsigned __int16 *)CreateEventW(0, 1, 0, 0);
  if ( !EventW )
  {
LABEL_28:
    v8 = -2147467259;
    goto LABEL_29;
  }
  if ( (unsigned int)dword_180044008 > 4 )
  {
    v33 = (const char *)EventW;
    v26 = "start sync event %p created - now create thread";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)v9,
      (__int64)word_18003FBDA,
      v11,
      v12,
      (const unsigned __int16 **)&v26,
      (__int64)&v33);
  }
  *((_QWORD *)&v29 + 1) = *((_QWORD *)this + 12);
  *(_QWORD *)&v28 = *((_QWORD *)this + 11);
  *(_QWORD *)&v29 = EventW;
  *(_QWORD *)&v30 = this;
  *((_QWORD *)&v28 + 1) = a2;
  DWORD2(v30) = 0;
  if ( PAL_System_ThreadAllocInit(v9, &v28, EventW, (unsigned int *)&v31, &v32) >= 0 )
  {
    v17 = (int)v31;
    if ( (unsigned int)dword_180044008 > 4 )
    {
      v33 = "thread %d created successfully";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (__int64)v14,
        (__int64)byte_18003FB35,
        v15,
        v16,
        (const unsigned __int16 **)&v33,
        (__int64)&v31);
    }
    if ( (unsigned int)dword_180044008 > 4 )
    {
      v31 = "event signalled";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)v14,
        (__int64)&dword_18003FB14,
        v15,
        v16,
        (const unsigned __int16 **)&v31);
    }
    v18 = v32;
    *((_DWORD *)this + 20) = 2;
    *((_QWORD *)this + 8) = v18;
    *((_DWORD *)this + 14) = v17;
    *((_DWORD *)this + 18) = 1;
    v14 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v13, v15, v16);
      WPP_SF_DDi(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, v21, ActivityIdPrefix, v17, v18);
    }
  }
  else if ( (SDWORD2(v30) & 0x80000000) == 0 )
  {
    if ( (unsigned int)dword_180044008 > 4 )
    {
      v31 = "Thread exited with success error code";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)v14,
        (__int64)qword_18003FB60,
        v15,
        v16,
        (const unsigned __int16 **)&v31);
    }
  }
  else if ( (unsigned int)dword_180044008 > 2 )
  {
    LODWORD(v31) = DWORD2(v30);
    v27 = "Thread exited with error code: 0x%x";
    v26 = "StartThread";
    LODWORD(v32) = 746;
    v25 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
    LODWORD(v33) = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)v14,
      (__int64)byte_18003FB81,
      v15,
      v16,
      (const unsigned __int16 **)&v27,
      (__int64)&v33,
      (const unsigned __int16 **)&v25,
      (__int64)&v32,
      (const unsigned __int16 **)&v26,
      (__int64)&v31);
  }
  if ( (unsigned int)dword_180044008 > 4 )
  {
    v31 = "Destroy event object";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)v14,
      (__int64)byte_18003FAF3,
      v15,
      v16,
      (const unsigned __int16 **)&v31);
  }
  v8 = PAL_System_HandleFree(EventW);
  if ( v8 < 0 && (unsigned int)dword_180044008 > 2 )
  {
    v33 = "StartThread";
    v26 = "Failed to close condition handle";
    LODWORD(v31) = 778;
    v27 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
    LODWORD(v32) = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)&word_18003FAAE,
      v22,
      v23,
      (const unsigned __int16 **)&v26,
      (__int64)&v32,
      (const unsigned __int16 **)&v27,
      (__int64)&v31,
      (const unsigned __int16 **)&v33);
  }
LABEL_29:
  CTSReaderWriterLock::WriteUnlock(v4);
  if ( v8 >= 0 && SDWORD2(v30) < 0 )
    return (unsigned int)DWORD2(v30);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180026cd0  mov     [rsp-8+arg_8], rbx
0x180026cd5  push    rbp
0x180026cd6  push    rsi
0x180026cd7  push    rdi
0x180026cd8  push    r12
0x180026cda  push    r13
0x180026cdc  push    r14
0x180026cde  push    r15
0x180026ce0  lea     rbp, [rsp-27h]
0x180026ce5  sub     rsp, 0A0h
0x180026cec  xorps   xmm0, xmm0
0x180026cef  mov     dword ptr [rbp+57h+arg_0], 0
0x180026cf6  movups  [rbp+57h+var_68], xmm0
0x180026cfa  mov     rsi, rdx
0x180026cfd  mov     rbx, rcx
0x180026d00  movups  [rbp+57h+var_58], xmm0
0x180026d04  mov     [rbp+57h+arg_10], 0
0x180026d0c  movups  [rbp+57h+var_48], xmm0
0x180026d10  lea     r13, [rcx+94h]
0x180026d17  mov     rcx, r13; this
0x180026d1a  call    ?WriteLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteLock(void)
0x180026d1f  cmp     dword ptr [rbx+50h], 1
0x180026d23  jnz     loc_18002705E
0x180026d29  cmp     qword ptr [rbx+58h], 0
0x180026d2e  jnz     short loc_180026DAD
0x180026d30  mov     eax, cs:dword_180044008
0x180026d36  cmp     eax, 2
0x180026d39  jbe     short loc_180026DA3
0x180026d3b  lea     rax, aEntryFunctionD; "Entry function does not exist can't sta"...
0x180026d42  mov     dword ptr [rbp+57h+arg_0], 2BFh
0x180026d49  mov     [rbp+57h+var_78], rax
0x180026d4d  lea     r14, aStartthread; "StartThread"
0x180026d54  lea     rax, [rbp+57h+arg_18]
0x180026d58  mov     [rbp+57h+arg_18], r14
0x180026d5c  mov     [rsp+0D0h+var_90], rax
0x180026d61  lea     r15, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180026d68  lea     rax, [rbp+57h+arg_0]
0x180026d6c  mov     [rbp+57h+var_80], r15
0x180026d70  mov     [rsp+0D0h+var_98], rax
0x180026d75  lea     rdx, word_18003FC12
0x180026d7c  lea     rax, [rbp+57h+var_80]
0x180026d80  mov     dword ptr [rbp+57h+arg_10], 80004005h
0x180026d87  mov     [rsp+0D0h+var_A0], rax
0x180026d8c  lea     rax, [rbp+57h+arg_10]
0x180026d90  mov     [rsp+0D0h+var_A8], rax
0x180026d95  lea     rax, [rbp+57h+var_78]
0x180026d99  mov     [rsp+0D0h+var_B0], rax
0x180026d9e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180026da3  mov     ebx, 80070057h
0x180026da8  jmp     loc_180027063
0x180026dad  xor     r9d, r9d; lpName
0x180026db0  xor     r8d, r8d; bInitialState
0x180026db3  xor     ecx, ecx; lpEventAttributes
0x180026db5  lea     edx, [r9+1]; bManualReset
0x180026db9  call    cs:__imp_CreateEventW
0x180026dbf  mov     rdi, rax
0x180026dc2  test    rax, rax
0x180026dc5  jz      loc_18002705E
0x180026dcb  mov     eax, cs:dword_180044008
0x180026dd1  cmp     eax, 4
0x180026dd4  jbe     short loc_180026E03
0x180026dd6  lea     rax, aStartSyncEvent; "start sync event %p created - now creat"...
0x180026ddd  mov     [rbp+57h+arg_18], rdi
0x180026de1  mov     [rbp+57h+var_78], rax
0x180026de5  lea     rdx, word_18003FBDA
0x180026dec  lea     rax, [rbp+57h+arg_18]
0x180026df0  mov     [rsp+0D0h+var_A8], rax
0x180026df5  lea     rax, [rbp+57h+var_78]
0x180026df9  mov     [rsp+0D0h+var_B0], rax
0x180026dfe  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180026e03  mov     rax, [rbx+60h]
0x180026e07  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x180026e0b  mov     qword ptr [rbp+57h+var_58+8], rax
0x180026e0f  lea     rdx, [rbp+57h+var_68]; void *
0x180026e13  mov     rax, [rbx+58h]
0x180026e17  mov     r8, rdi; void *
0x180026e1a  mov     qword ptr [rbp+57h+var_68], rax
0x180026e1e  lea     rax, [rbp+57h+arg_10]
0x180026e22  mov     [rsp+0D0h+var_B0], rax; void **
0x180026e27  mov     qword ptr [rbp+57h+var_58], rdi
0x180026e2b  mov     qword ptr [rbp+57h+var_48], rbx
0x180026e2f  mov     qword ptr [rbp+57h+var_68+8], rsi
0x180026e33  mov     dword ptr [rbp+57h+var_48+8], 0
0x180026e3a  call    ?PAL_System_ThreadAllocInit@@YAJP6AIPEAX@Z00PEAKPEAPEAX@Z; PAL_System_ThreadAllocInit(uint (*)(void *),void *,void *,ulong *,void * *)
0x180026e3f  test    eax, eax
0x180026e41  lea     r14, aStartthread; "StartThread"
0x180026e48  mov     eax, cs:dword_180044008
0x180026e4e  lea     r15, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180026e55  jns     loc_180026F06
0x180026e5b  cmp     dword ptr [rbp+57h+var_48+8], 0
0x180026e5f  jge     short loc_180026ED8
0x180026e61  cmp     eax, 2
0x180026e64  jbe     loc_180026FBE
0x180026e6a  mov     eax, dword ptr [rbp+57h+var_48+8]
0x180026e6d  lea     rdx, byte_18003FB81
0x180026e74  mov     dword ptr [rbp+57h+arg_0], eax
0x180026e77  lea     rax, aThreadExitedWi; "Thread exited with error code: 0x%x"
0x180026e7e  mov     [rbp+57h+var_70], rax
0x180026e82  lea     rax, [rbp+57h+arg_0]
0x180026e86  mov     [rsp+0D0h+var_88], rax
0x180026e8b  lea     rax, [rbp+57h+var_78]
0x180026e8f  mov     [rsp+0D0h+var_90], rax
0x180026e94  lea     rax, [rbp+57h+arg_10]
0x180026e98  mov     [rsp+0D0h+var_98], rax
0x180026e9d  lea     rax, [rbp+57h+var_80]
0x180026ea1  mov     [rsp+0D0h+var_A0], rax
0x180026ea6  lea     rax, [rbp+57h+arg_18]
0x180026eaa  mov     [rsp+0D0h+var_A8], rax
0x180026eaf  lea     rax, [rbp+57h+var_70]
0x180026eb3  mov     [rsp+0D0h+var_B0], rax
0x180026eb8  mov     [rbp+57h+var_78], r14
0x180026ebc  mov     dword ptr [rbp+57h+arg_10], 2EAh
0x180026ec3  mov     [rbp+57h+var_80], r15
0x180026ec7  mov     dword ptr [rbp+57h+arg_18], 80004005h
0x180026ece  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180026ed3  jmp     loc_180026FBE
0x180026ed8  cmp     eax, 4
0x180026edb  jbe     loc_180026FBE
0x180026ee1  lea     rax, aThreadExitedWi_0; "Thread exited with success error code"
0x180026ee8  mov     [rbp+57h+arg_0], rax
0x180026eec  lea     rdx, qword_18003FB60
0x180026ef3  lea     rax, [rbp+57h+arg_0]
0x180026ef7  mov     [rsp+0D0h+var_B0], rax
0x180026efc  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180026f01  jmp     loc_180026FBE
0x180026f06  mov     esi, dword ptr [rbp+57h+arg_0]
0x180026f09  cmp     eax, 4
0x180026f0c  jbe     short loc_180026F3A
0x180026f0e  lea     rax, aThreadDCreated; "thread %d created successfully"
0x180026f15  mov     dword ptr [rbp+57h+arg_0], esi
0x180026f18  mov     [rbp+57h+arg_18], rax
0x180026f1c  lea     rdx, byte_18003FB35
0x180026f23  lea     rax, [rbp+57h+arg_0]
0x180026f27  mov     [rsp+0D0h+var_A8], rax
0x180026f2c  lea     rax, [rbp+57h+arg_18]
0x180026f30  mov     [rsp+0D0h+var_B0], rax
0x180026f35  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180026f3a  mov     eax, cs:dword_180044008
0x180026f40  cmp     eax, 4
0x180026f43  jbe     short loc_180026F65
0x180026f45  lea     rax, aEventSignalled; "event signalled"
0x180026f4c  mov     [rbp+57h+arg_0], rax
0x180026f50  lea     rdx, dword_18003FB14
0x180026f57  lea     rax, [rbp+57h+arg_0]
0x180026f5b  mov     [rsp+0D0h+var_B0], rax
0x180026f60  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180026f65  mov     r12, [rbp+57h+arg_10]
0x180026f69  mov     dword ptr [rbx+50h], 2
0x180026f70  mov     [rbx+40h], r12
0x180026f74  mov     [rbx+38h], esi
0x180026f77  mov     dword ptr [rbx+48h], 1
0x180026f7e  mov     rax, cs:WPP_GLOBAL_Control
0x180026f85  lea     rcx, WPP_GLOBAL_Control
0x180026f8c  cmp     rax, rcx
0x180026f8f  jz      short loc_180026FBE
0x180026f91  test    byte ptr [rax+1Ch], 1
0x180026f95  jz      short loc_180026FBE
0x180026f97  cmp     byte ptr [rax+19h], 3
0x180026f9b  jb      short loc_180026FBE
0x180026f9d  call    RdpX_GetActivityIdPrefix
0x180026fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180026fa9  mov     r9d, eax
0x180026fac  mov     [rsp+0D0h+var_A8], r12
0x180026fb1  mov     dword ptr [rsp+0D0h+var_B0], esi
0x180026fb5  mov     rcx, [rcx+10h]
0x180026fb9  call    WPP_SF_DDi
0x180026fbe  mov     eax, cs:dword_180044008
0x180026fc4  cmp     eax, 4
0x180026fc7  jbe     short loc_180026FE9
0x180026fc9  lea     rax, aDestroyEventOb; "Destroy event object"
0x180026fd0  mov     [rbp+57h+arg_0], rax
0x180026fd4  lea     rdx, byte_18003FAF3
0x180026fdb  lea     rax, [rbp+57h+arg_0]
0x180026fdf  mov     [rsp+0D0h+var_B0], rax
0x180026fe4  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180026fe9  mov     rcx, rdi
0x180026fec  call    PAL_System_HandleFree
0x180026ff1  mov     ebx, eax
0x180026ff3  test    eax, eax
0x180026ff5  jns     short loc_180027063
0x180026ff7  mov     ecx, cs:dword_180044008
0x180026ffd  cmp     ecx, 2
0x180027000  jbe     short loc_180027063
0x180027002  lea     rax, aFailedToCloseC; "Failed to close condition handle"
0x180027009  mov     [rbp+57h+arg_18], r14
0x18002700d  mov     [rbp+57h+var_78], rax
0x180027011  lea     rdx, word_18003FAAE
0x180027018  lea     rax, [rbp+57h+arg_18]
0x18002701c  mov     dword ptr [rbp+57h+arg_0], 30Ah
0x180027023  mov     [rsp+0D0h+var_90], rax
0x180027028  lea     rax, [rbp+57h+arg_0]
0x18002702c  mov     [rsp+0D0h+var_98], rax
0x180027031  lea     rax, [rbp+57h+var_70]
0x180027035  mov     [rsp+0D0h+var_A0], rax
0x18002703a  lea     rax, [rbp+57h+arg_10]
0x18002703e  mov     [rsp+0D0h+var_A8], rax
0x180027043  lea     rax, [rbp+57h+var_78]
0x180027047  mov     [rsp+0D0h+var_B0], rax
0x18002704c  mov     [rbp+57h+var_70], r15
0x180027050  mov     dword ptr [rbp+57h+arg_10], 80004005h
0x180027057  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002705c  jmp     short loc_180027063
0x18002705e  mov     ebx, 80004005h
0x180027063  mov     rcx, r13; this
0x180027066  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x18002706b  test    ebx, ebx
0x18002706d  js      short loc_180027077
0x18002706f  mov     eax, dword ptr [rbp+57h+var_48+8]
0x180027072  test    eax, eax
0x180027074  cmovs   ebx, eax
0x180027077  mov     eax, ebx
0x180027079  mov     rbx, [rsp+0D0h+arg_8]
0x180027081  add     rsp, 0A0h
0x180027088  pop     r15
0x18002708a  pop     r14
0x18002708c  pop     r13
0x18002708e  pop     r12
0x180027090  pop     rdi
0x180027091  pop     rsi
0x180027092  pop     rbp
0x180027093  retn
```
