# CTSThread::StartThread(long (*)(void *))

- ea: `0x14001e310`
- end: `0x14001e6d4`
- name: `?StartThread@CTSThread@@UEAAJP6AJPEAX@Z@Z`
- size: `964`
- prototype: `__int64 __fastcall(CTSThread *__hidden this, int (*)(void *))`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1400010c0`
- `0x14000142c`
- `0x1400014d4`
- `0x1400015ec`
- `0x140001a2c`
- `0x14001096c`
- `0x140010998`
- `0x140017d98`
- `0x1400186c4`
- `0x14001e310`
- `0x14001ff1c`
- `0x1400256b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001e3f9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001e3f9`

## string_xrefs

- `0x14001e3a1`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x14001e48e`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x14001e38d`: `StartThread`
- `0x14001e481`: `StartThread`
- `0x14001e37b`: `Entry function does not exist can't start thread`
- `0x14001e416`: `start sync event %p created - now create thread`
- `0x14001e4b7`: `Thread exited with error code: 0x%x`
- `0x14001e521`: `Thread exited with success error code`
- `0x14001e54e`: `thread %d created successfully`

## pseudocode

```c
__int64 __fastcall CTSThread::StartThread(CTSThread *this, int (*a2)(void *))
{
  CTSReaderWriterLock *v4; // r13
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  int v8; // ebx
  unsigned int (*v9)(void *); // rcx
  char *EventW; // rdi
  int v11; // r8d
  int v12; // r9d
  PVOID *v13; // rcx
  int v14; // r8d
  int v15; // r9d
  int v16; // esi
  void *v17; // r12
  unsigned int ActivityIdPrefix; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  int v21; // r8d
  int v22; // r9d
  const char *v24; // [rsp+50h] [rbp-29h] BYREF
  const char *v25; // [rsp+58h] [rbp-21h] BYREF
  const char *v26; // [rsp+60h] [rbp-19h] BYREF
  __int128 v27; // [rsp+68h] [rbp-11h] BYREF
  __int128 v28; // [rsp+78h] [rbp-1h]
  __int128 v29; // [rsp+88h] [rbp+Fh]
  const char *v30; // [rsp+E0h] [rbp+67h] BYREF
  void *v31; // [rsp+F0h] [rbp+77h] BYREF
  const char *v32; // [rsp+F8h] [rbp+7Fh] BYREF

  LODWORD(v30) = 0;
  v27 = 0;
  v28 = 0;
  v31 = 0;
  v29 = 0;
  v4 = (CTSThread *)((char *)this + 148);
  CTSReaderWriterLock::WriteLock((CTSThread *)((char *)this + 148));
  if ( *((_DWORD *)this + 20) != 1 )
    goto LABEL_28;
  if ( !*((_QWORD *)this + 11) )
  {
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      LODWORD(v30) = 703;
      v25 = "Entry function does not exist can't start thread";
      v32 = "StartThread";
      v24 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      LODWORD(v31) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v5,
        (unsigned int)&byte_14007EAFF,
        v6,
        v7,
        (__int64)&v25,
        (__int64)&v31,
        (__int64)&v24,
        (__int64)&v30,
        (__int64)&v32);
    }
    v8 = -2147024809;
    goto LABEL_29;
  }
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  if ( !EventW )
  {
LABEL_28:
    v8 = -2147467259;
    goto LABEL_29;
  }
  if ( (unsigned int)dword_1400880C8 > 4 )
  {
    v32 = EventW;
    v25 = "start sync event %p created - now create thread";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v9,
      (unsigned int)&byte_14007EAC7,
      v11,
      v12,
      (__int64)&v25,
      (__int64)&v32);
  }
  *((_QWORD *)&v28 + 1) = *((_QWORD *)this + 12);
  *(_QWORD *)&v27 = *((_QWORD *)this + 11);
  *(_QWORD *)&v28 = EventW;
  *(_QWORD *)&v29 = this;
  *((_QWORD *)&v27 + 1) = a2;
  DWORD2(v29) = 0;
  if ( PAL_System_ThreadAllocInit(v9, &v27, EventW, (unsigned int *)&v30, &v31) >= 0 )
  {
    v16 = (int)v30;
    if ( (unsigned int)dword_1400880C8 > 4 )
    {
      v32 = "thread %d created successfully";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)v13,
        (unsigned int)word_14007EA22,
        v14,
        v15,
        (__int64)&v32,
        (__int64)&v30);
    }
    if ( (unsigned int)dword_1400880C8 > 4 )
    {
      v30 = "event signalled";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v13,
        (unsigned int)byte_14007EA01,
        v14,
        v15,
        (__int64)&v30);
    }
    v17 = v31;
    *((_DWORD *)this + 20) = 2;
    *((_QWORD *)this + 8) = v17;
    *((_DWORD *)this + 14) = v16;
    *((_DWORD *)this + 18) = 1;
    v13 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
      WPP_SF_DDi(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v20, ActivityIdPrefix, v16, v17);
    }
  }
  else if ( (SDWORD2(v29) & 0x80000000) == 0 )
  {
    if ( (unsigned int)dword_1400880C8 > 4 )
    {
      v30 = "Thread exited with success error code";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v13,
        (unsigned int)byte_14007EA4D,
        v14,
        v15,
        (__int64)&v30);
    }
  }
  else if ( (unsigned int)dword_1400880C8 > 2 )
  {
    LODWORD(v30) = DWORD2(v29);
    v26 = "Thread exited with error code: 0x%x";
    v25 = "StartThread";
    LODWORD(v31) = 746;
    v24 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
    LODWORD(v32) = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)v13,
      (unsigned int)&word_14007EA6E,
      v14,
      v15,
      (__int64)&v26,
      (__int64)&v32,
      (__int64)&v24,
      (__int64)&v31,
      (__int64)&v25,
      (__int64)&v30);
  }
  if ( (unsigned int)dword_1400880C8 > 4 )
  {
    v30 = "Destroy event object";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)v13,
      (unsigned int)qword_14007E9E0,
      v14,
      v15,
      (__int64)&v30);
  }
  v8 = PAL_System_HandleFree(EventW);
  if ( v8 < 0 && (unsigned int)dword_1400880C8 > 2 )
  {
    v32 = "StartThread";
    v25 = "Failed to close condition handle";
    LODWORD(v30) = 778;
    v26 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
    LODWORD(v31) = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      dword_1400880C8,
      (unsigned int)byte_14007E99B,
      v21,
      v22,
      (__int64)&v25,
      (__int64)&v31,
      (__int64)&v26,
      (__int64)&v30,
      (__int64)&v32);
  }
LABEL_29:
  CTSReaderWriterLock::WriteUnlock(v4);
  if ( v8 >= 0 && SDWORD2(v29) < 0 )
    return (unsigned int)DWORD2(v29);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14001e310  mov     [rsp-8+arg_8], rbx
0x14001e315  push    rbp
0x14001e316  push    rsi
0x14001e317  push    rdi
0x14001e318  push    r12
0x14001e31a  push    r13
0x14001e31c  push    r14
0x14001e31e  push    r15
0x14001e320  lea     rbp, [rsp-27h]
0x14001e325  sub     rsp, 0A0h
0x14001e32c  xorps   xmm0, xmm0
0x14001e32f  mov     dword ptr [rbp+57h+arg_0], 0
0x14001e336  movups  [rbp+57h+var_68], xmm0
0x14001e33a  mov     rsi, rdx
0x14001e33d  mov     rbx, rcx
0x14001e340  movups  [rbp+57h+var_58], xmm0
0x14001e344  mov     [rbp+57h+arg_10], 0
0x14001e34c  movups  [rbp+57h+var_48], xmm0
0x14001e350  lea     r13, [rcx+94h]
0x14001e357  mov     rcx, r13; this
0x14001e35a  call    ?WriteLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteLock(void)
0x14001e35f  cmp     dword ptr [rbx+50h], 1
0x14001e363  jnz     loc_14001E69E
0x14001e369  cmp     qword ptr [rbx+58h], 0
0x14001e36e  jnz     short loc_14001E3ED
0x14001e370  mov     eax, cs:dword_1400880C8
0x14001e376  cmp     eax, 2
0x14001e379  jbe     short loc_14001E3E3
0x14001e37b  lea     rax, aEntryFunctionD; "Entry function does not exist can't sta"...
0x14001e382  mov     dword ptr [rbp+57h+arg_0], 2BFh
0x14001e389  mov     [rbp+57h+var_78], rax
0x14001e38d  lea     r14, aStartthread; "StartThread"
0x14001e394  lea     rax, [rbp+57h+arg_18]
0x14001e398  mov     [rbp+57h+arg_18], r14
0x14001e39c  mov     [rsp+0D0h+var_90], rax
0x14001e3a1  lea     r15, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14001e3a8  lea     rax, [rbp+57h+arg_0]
0x14001e3ac  mov     [rbp+57h+var_80], r15
0x14001e3b0  mov     [rsp+0D0h+var_98], rax
0x14001e3b5  lea     rdx, byte_14007EAFF
0x14001e3bc  lea     rax, [rbp+57h+var_80]
0x14001e3c0  mov     dword ptr [rbp+57h+arg_10], 80004005h
0x14001e3c7  mov     [rsp+0D0h+var_A0], rax
0x14001e3cc  lea     rax, [rbp+57h+arg_10]
0x14001e3d0  mov     [rsp+0D0h+var_A8], rax
0x14001e3d5  lea     rax, [rbp+57h+var_78]
0x14001e3d9  mov     [rsp+0D0h+var_B0], rax
0x14001e3de  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14001e3e3  mov     ebx, 80070057h
0x14001e3e8  jmp     loc_14001E6A3
0x14001e3ed  xor     r9d, r9d; lpName
0x14001e3f0  xor     r8d, r8d; bInitialState
0x14001e3f3  xor     ecx, ecx; lpEventAttributes
0x14001e3f5  lea     edx, [r9+1]; bManualReset
0x14001e3f9  call    cs:__imp_CreateEventW
0x14001e3ff  mov     rdi, rax
0x14001e402  test    rax, rax
0x14001e405  jz      loc_14001E69E
0x14001e40b  mov     eax, cs:dword_1400880C8
0x14001e411  cmp     eax, 4
0x14001e414  jbe     short loc_14001E443
0x14001e416  lea     rax, aStartSyncEvent; "start sync event %p created - now creat"...
0x14001e41d  mov     [rbp+57h+arg_18], rdi
0x14001e421  mov     [rbp+57h+var_78], rax
0x14001e425  lea     rdx, byte_14007EAC7
0x14001e42c  lea     rax, [rbp+57h+arg_18]
0x14001e430  mov     [rsp+0D0h+var_A8], rax
0x14001e435  lea     rax, [rbp+57h+var_78]
0x14001e439  mov     [rsp+0D0h+var_B0], rax
0x14001e43e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x14001e443  mov     rax, [rbx+60h]
0x14001e447  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x14001e44b  mov     qword ptr [rbp+57h+var_58+8], rax
0x14001e44f  lea     rdx, [rbp+57h+var_68]; void *
0x14001e453  mov     rax, [rbx+58h]
0x14001e457  mov     r8, rdi; void *
0x14001e45a  mov     qword ptr [rbp+57h+var_68], rax
0x14001e45e  lea     rax, [rbp+57h+arg_10]
0x14001e462  mov     [rsp+0D0h+var_B0], rax; void **
0x14001e467  mov     qword ptr [rbp+57h+var_58], rdi
0x14001e46b  mov     qword ptr [rbp+57h+var_48], rbx
0x14001e46f  mov     qword ptr [rbp+57h+var_68+8], rsi
0x14001e473  mov     dword ptr [rbp+57h+var_48+8], 0
0x14001e47a  call    ?PAL_System_ThreadAllocInit@@YAJP6AIPEAX@Z00PEAKPEAPEAX@Z; PAL_System_ThreadAllocInit(uint (*)(void *),void *,void *,ulong *,void * *)
0x14001e47f  test    eax, eax
0x14001e481  lea     r14, aStartthread; "StartThread"
0x14001e488  mov     eax, cs:dword_1400880C8
0x14001e48e  lea     r15, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14001e495  jns     loc_14001E546
0x14001e49b  cmp     dword ptr [rbp+57h+var_48+8], 0
0x14001e49f  jge     short loc_14001E518
0x14001e4a1  cmp     eax, 2
0x14001e4a4  jbe     loc_14001E5FE
0x14001e4aa  mov     eax, dword ptr [rbp+57h+var_48+8]
0x14001e4ad  lea     rdx, word_14007EA6E
0x14001e4b4  mov     dword ptr [rbp+57h+arg_0], eax
0x14001e4b7  lea     rax, aThreadExitedWi; "Thread exited with error code: 0x%x"
0x14001e4be  mov     [rbp+57h+var_70], rax
0x14001e4c2  lea     rax, [rbp+57h+arg_0]
0x14001e4c6  mov     [rsp+0D0h+var_88], rax
0x14001e4cb  lea     rax, [rbp+57h+var_78]
0x14001e4cf  mov     [rsp+0D0h+var_90], rax
0x14001e4d4  lea     rax, [rbp+57h+arg_10]
0x14001e4d8  mov     [rsp+0D0h+var_98], rax
0x14001e4dd  lea     rax, [rbp+57h+var_80]
0x14001e4e1  mov     [rsp+0D0h+var_A0], rax
0x14001e4e6  lea     rax, [rbp+57h+arg_18]
0x14001e4ea  mov     [rsp+0D0h+var_A8], rax
0x14001e4ef  lea     rax, [rbp+57h+var_70]
0x14001e4f3  mov     [rsp+0D0h+var_B0], rax
0x14001e4f8  mov     [rbp+57h+var_78], r14
0x14001e4fc  mov     dword ptr [rbp+57h+arg_10], 2EAh
0x14001e503  mov     [rbp+57h+var_80], r15
0x14001e507  mov     dword ptr [rbp+57h+arg_18], 80004005h
0x14001e50e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14001e513  jmp     loc_14001E5FE
0x14001e518  cmp     eax, 4
0x14001e51b  jbe     loc_14001E5FE
0x14001e521  lea     rax, aThreadExitedWi_0; "Thread exited with success error code"
0x14001e528  mov     [rbp+57h+arg_0], rax
0x14001e52c  lea     rdx, byte_14007EA4D
0x14001e533  lea     rax, [rbp+57h+arg_0]
0x14001e537  mov     [rsp+0D0h+var_B0], rax
0x14001e53c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14001e541  jmp     loc_14001E5FE
0x14001e546  mov     esi, dword ptr [rbp+57h+arg_0]
0x14001e549  cmp     eax, 4
0x14001e54c  jbe     short loc_14001E57A
0x14001e54e  lea     rax, aThreadDCreated; "thread %d created successfully"
0x14001e555  mov     dword ptr [rbp+57h+arg_0], esi
0x14001e558  mov     [rbp+57h+arg_18], rax
0x14001e55c  lea     rdx, word_14007EA22
0x14001e563  lea     rax, [rbp+57h+arg_0]
0x14001e567  mov     [rsp+0D0h+var_A8], rax
0x14001e56c  lea     rax, [rbp+57h+arg_18]
0x14001e570  mov     [rsp+0D0h+var_B0], rax
0x14001e575  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14001e57a  mov     eax, cs:dword_1400880C8
0x14001e580  cmp     eax, 4
0x14001e583  jbe     short loc_14001E5A5
0x14001e585  lea     rax, aEventSignalled; "event signalled"
0x14001e58c  mov     [rbp+57h+arg_0], rax
0x14001e590  lea     rdx, byte_14007EA01
0x14001e597  lea     rax, [rbp+57h+arg_0]
0x14001e59b  mov     [rsp+0D0h+var_B0], rax
0x14001e5a0  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14001e5a5  mov     r12, [rbp+57h+arg_10]
0x14001e5a9  mov     dword ptr [rbx+50h], 2
0x14001e5b0  mov     [rbx+40h], r12
0x14001e5b4  mov     [rbx+38h], esi
0x14001e5b7  mov     dword ptr [rbx+48h], 1
0x14001e5be  mov     rax, cs:WPP_GLOBAL_Control
0x14001e5c5  lea     rcx, WPP_GLOBAL_Control
0x14001e5cc  cmp     rax, rcx
0x14001e5cf  jz      short loc_14001E5FE
0x14001e5d1  test    byte ptr [rax+1Ch], 1
0x14001e5d5  jz      short loc_14001E5FE
0x14001e5d7  cmp     byte ptr [rax+19h], 3
0x14001e5db  jb      short loc_14001E5FE
0x14001e5dd  call    RdpX_GetActivityIdPrefix
0x14001e5e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e5e9  mov     r9d, eax
0x14001e5ec  mov     [rsp+0D0h+var_A8], r12
0x14001e5f1  mov     dword ptr [rsp+0D0h+var_B0], esi
0x14001e5f5  mov     rcx, [rcx+10h]
0x14001e5f9  call    WPP_SF_DDi
0x14001e5fe  mov     eax, cs:dword_1400880C8
0x14001e604  cmp     eax, 4
0x14001e607  jbe     short loc_14001E629
0x14001e609  lea     rax, aDestroyEventOb; "Destroy event object"
0x14001e610  mov     [rbp+57h+arg_0], rax
0x14001e614  lea     rdx, qword_14007E9E0
0x14001e61b  lea     rax, [rbp+57h+arg_0]
0x14001e61f  mov     [rsp+0D0h+var_B0], rax
0x14001e624  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14001e629  mov     rcx, rdi
0x14001e62c  call    PAL_System_HandleFree
0x14001e631  mov     ebx, eax
0x14001e633  test    eax, eax
0x14001e635  jns     short loc_14001E6A3
0x14001e637  mov     ecx, cs:dword_1400880C8
0x14001e63d  cmp     ecx, 2
0x14001e640  jbe     short loc_14001E6A3
0x14001e642  lea     rax, aFailedToCloseC; "Failed to close condition handle"
0x14001e649  mov     [rbp+57h+arg_18], r14
0x14001e64d  mov     [rbp+57h+var_78], rax
0x14001e651  lea     rdx, byte_14007E99B
0x14001e658  lea     rax, [rbp+57h+arg_18]
0x14001e65c  mov     dword ptr [rbp+57h+arg_0], 30Ah
0x14001e663  mov     [rsp+0D0h+var_90], rax
0x14001e668  lea     rax, [rbp+57h+arg_0]
0x14001e66c  mov     [rsp+0D0h+var_98], rax
0x14001e671  lea     rax, [rbp+57h+var_70]
0x14001e675  mov     [rsp+0D0h+var_A0], rax
0x14001e67a  lea     rax, [rbp+57h+arg_10]
0x14001e67e  mov     [rsp+0D0h+var_A8], rax
0x14001e683  lea     rax, [rbp+57h+var_78]
0x14001e687  mov     [rsp+0D0h+var_B0], rax
0x14001e68c  mov     [rbp+57h+var_70], r15
0x14001e690  mov     dword ptr [rbp+57h+arg_10], 80004005h
0x14001e697  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14001e69c  jmp     short loc_14001E6A3
0x14001e69e  mov     ebx, 80004005h
0x14001e6a3  mov     rcx, r13; this
0x14001e6a6  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x14001e6ab  test    ebx, ebx
0x14001e6ad  js      short loc_14001E6B7
0x14001e6af  mov     eax, dword ptr [rbp+57h+var_48+8]
0x14001e6b2  test    eax, eax
0x14001e6b4  cmovs   ebx, eax
0x14001e6b7  mov     eax, ebx
0x14001e6b9  mov     rbx, [rsp+0D0h+arg_8]
0x14001e6c1  add     rsp, 0A0h
0x14001e6c8  pop     r15
0x14001e6ca  pop     r14
0x14001e6cc  pop     r13
0x14001e6ce  pop     r12
0x14001e6d0  pop     rdi
0x14001e6d1  pop     rsi
0x14001e6d2  pop     rbp
0x14001e6d3  retn
```
