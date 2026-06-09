# CWSStream::ReadBuffer(IRDPENCNetStreamBuffer *)

- ea: `0x18010f5d0`
- end: `0x18010f95b`
- name: `?ReadBuffer@CWSStream@@UEAAJPEAUIRDPENCNetStreamBuffer@@@Z`
- size: `907`
- prototype: `__int64 __fastcall(CWSStream *__hidden this, struct IRDPENCNetStreamBuffer *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001aa0`
- `0x18001b3f8`
- `0x180040750`
- `0x180078c20`
- `0x180109550`
- `0x18010c27c`
- `0x18010f5d0`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18010f763`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18010f763`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010f73b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010f73b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010f76c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010f891`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010f76c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010f891`

## string_xrefs

- `0x18010f647`: `ReadBuffer`
- `0x18010f6da`: `ReadBuffer`
- `0x18010f7ed`: `ReadBuffer`
- `0x18010f8cd`: `ReadBuffer`
- `0x18010f62e`: `ReadBuffer: Stream closed`
- `0x18010f6c1`: `ReadBuffer: Stream closed`
- `0x18010f8b4`: `FlushReadBuffer failed`
- `0x18010f7d4`: `ReadBuffer: First payload size must be greater than 1.`

## pseudocode

```c
__int64 __fastcall CWSStream::ReadBuffer(CWSStream *this, struct IRDPENCNetStreamBuffer *a2)
{
  int v4; // r8d
  int v5; // r9d
  int Buffer; // edi
  __int64 v7; // rax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rax
  int v12; // r8d
  int v13; // r9d
  int v15; // [rsp+50h] [rbp-9h] BYREF
  int v16; // [rsp+54h] [rbp-5h] BYREF
  const char *v17; // [rsp+58h] [rbp-1h] BYREF
  const char *v18; // [rsp+60h] [rbp+7h] BYREF
  const char *v19; // [rsp+68h] [rbp+Fh] BYREF
  const char *v20; // [rsp+70h] [rbp+17h] BYREF
  const char *v21; // [rsp+78h] [rbp+1Fh] BYREF
  const char *v22; // [rsp+80h] [rbp+27h] BYREF
  GUID ActivityId; // [rsp+88h] [rbp+2Fh] BYREF

  CAutoSetThreadActivityId::CAutoSetThreadActivityId(&ActivityId, (const struct _GUID *)((char *)this + 1148));
  if ( !*((_DWORD *)this + 30) )
  {
    Buffer = -2147467259;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v16 = 1547;
      v18 = "ReadBuffer: Stream closed";
      v15 = -2147467259;
      v17 = "ReadBuffer";
      v19 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
      v20 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147467259,
        (unsigned int)word_1801C8BBA,
        v4,
        v5,
        (__int64)&v20,
        (__int64)&v15,
        (__int64)&v19,
        (__int64)&v16,
        (__int64)&v17,
        (__int64)&v18);
    }
    goto LABEL_18;
  }
  if ( !*((_DWORD *)this + 31) )
  {
    Buffer = -2147467259;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v16 = 1548;
      v20 = "ReadBuffer: Stream closed";
      v15 = -2147467259;
      v19 = "ReadBuffer";
      v18 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
      v17 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147467259,
        (unsigned int)byte_1801C8C0B,
        v4,
        v5,
        (__int64)&v17,
        (__int64)&v15,
        (__int64)&v18,
        (__int64)&v16,
        (__int64)&v19,
        (__int64)&v20);
    }
    goto LABEL_18;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
  if ( *((_QWORD *)this + 162) )
  {
    Buffer = 0;
    CComPtrList<IRDPENCNetStreamBuffer,ComPlainSmartPtr<IRDPENCNetStreamBuffer>>::AddTail((char *)this + 656, a2);
    SetEvent(*((HANDLE *)this + 222));
LABEL_9:
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
    goto LABEL_18;
  }
  if ( *((_DWORD *)this + 33) )
  {
    v7 = *(_QWORD *)a2;
    v15 = 0;
    v16 = 0;
    (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, int *))(v7 + 56))(a2, &v16);
    (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, int *))(*(_QWORD *)a2 + 40LL))(a2, &v15);
    if ( v15 <= 1 )
    {
      Buffer = -2147024809;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v17) = 1579;
        v20 = "ReadBuffer: First payload size must be greater than 1.";
        LODWORD(v18) = -2147024809;
        v19 = "ReadBuffer";
        v21 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
        v22 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v8,
          (unsigned int)qword_1801C8B18,
          v9,
          v10,
          (__int64)&v22,
          (__int64)&v18,
          (__int64)&v21,
          (__int64)&v17,
          (__int64)&v19,
          (__int64)&v20);
      }
      goto LABEL_9;
    }
    --v15;
    v11 = *(_QWORD *)a2;
    ++v16;
    (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *))(v11 + 64))(a2);
    (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, _QWORD))(*(_QWORD *)a2 + 48LL))(a2, (unsigned int)v15);
  }
  CComPtrList<IRDPENCNetStreamBuffer,ComPlainSmartPtr<IRDPENCNetStreamBuffer>>::AddTail((char *)this + 656, a2);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
  Buffer = CWSStream::FlushReadBuffer(this);
  if ( Buffer < 0 && (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v18) = 1594;
    v22 = "FlushReadBuffer failed";
    LODWORD(v17) = Buffer;
    v21 = "ReadBuffer";
    v20 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
    v19 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)CallbackContext,
      (unsigned int)byte_1801C8B69,
      v12,
      v13,
      (__int64)&v19,
      (__int64)&v17,
      (__int64)&v20,
      (__int64)&v18,
      (__int64)&v21,
      (__int64)&v22);
  }
LABEL_18:
  CAutoSetThreadActivityId::~CAutoSetThreadActivityId(&ActivityId);
  return (unsigned int)Buffer;
}

```

## disassembly

```asm
0x18010f5d0  mov     [rsp-8+arg_10], rbx
0x18010f5d5  mov     [rsp-8+arg_18], rsi
0x18010f5da  push    rbp
0x18010f5db  push    rdi
0x18010f5dc  push    r14
0x18010f5de  lea     rbp, [rsp-47h]
0x18010f5e3  sub     rsp, 0A0h
0x18010f5ea  mov     rax, cs:__security_cookie
0x18010f5f1  xor     rax, rsp
0x18010f5f4  mov     [rbp+57h+var_18], rax
0x18010f5f8  mov     rsi, rdx
0x18010f5fb  mov     rbx, rcx
0x18010f5fe  lea     rdx, [rcx+47Ch]; struct _GUID *
0x18010f605  lea     rcx, [rbp+57h+ActivityId]; ActivityId
0x18010f609  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x18010f60e  cmp     dword ptr [rbx+78h], 0
0x18010f612  jnz     loc_18010F6A1
0x18010f618  mov     eax, cs:CallbackContext
0x18010f61e  mov     ecx, 80004005h
0x18010f623  mov     edi, ecx
0x18010f625  cmp     eax, 2
0x18010f628  jbe     loc_18010F92C
0x18010f62e  lea     rax, aReadbufferStre; "ReadBuffer: Stream closed"
0x18010f635  mov     [rbp+57h+var_5C], 60Bh
0x18010f63c  mov     [rbp+57h+var_50], rax
0x18010f640  lea     rdx, word_1801C8BBA
0x18010f647  lea     rax, aReadbuffer; "ReadBuffer"
0x18010f64e  mov     [rbp+57h+var_60], ecx
0x18010f651  mov     [rbp+57h+var_58], rax
0x18010f655  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010f65c  mov     [rbp+57h+var_48], rax
0x18010f660  lea     rax, aErrorCondition; "Error condition failed"
0x18010f667  mov     [rbp+57h+var_40], rax
0x18010f66b  lea     rax, [rbp+57h+var_50]
0x18010f66f  mov     [rsp+0B0h+var_68], rax
0x18010f674  lea     rax, [rbp+57h+var_58]
0x18010f678  mov     [rsp+0B0h+var_70], rax
0x18010f67d  lea     rax, [rbp+57h+var_5C]
0x18010f681  mov     [rsp+0B0h+var_78], rax
0x18010f686  lea     rax, [rbp+57h+var_48]
0x18010f68a  mov     [rsp+0B0h+var_80], rax
0x18010f68f  lea     rax, [rbp+57h+var_60]
0x18010f693  mov     [rsp+0B0h+var_88], rax
0x18010f698  lea     rax, [rbp+57h+var_40]
0x18010f69c  jmp     loc_18010F922
0x18010f6a1  cmp     dword ptr [rbx+7Ch], 0
0x18010f6a5  jnz     loc_18010F734
0x18010f6ab  mov     eax, cs:CallbackContext
0x18010f6b1  mov     ecx, 80004005h
0x18010f6b6  mov     edi, ecx
0x18010f6b8  cmp     eax, 2
0x18010f6bb  jbe     loc_18010F92C
0x18010f6c1  lea     rax, aReadbufferStre; "ReadBuffer: Stream closed"
0x18010f6c8  mov     [rbp+57h+var_5C], 60Ch
0x18010f6cf  mov     [rbp+57h+var_40], rax
0x18010f6d3  lea     rdx, byte_1801C8C0B
0x18010f6da  lea     rax, aReadbuffer; "ReadBuffer"
0x18010f6e1  mov     [rbp+57h+var_60], ecx
0x18010f6e4  mov     [rbp+57h+var_48], rax
0x18010f6e8  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010f6ef  mov     [rbp+57h+var_50], rax
0x18010f6f3  lea     rax, aErrorCondition; "Error condition failed"
0x18010f6fa  mov     [rbp+57h+var_58], rax
0x18010f6fe  lea     rax, [rbp+57h+var_40]
0x18010f702  mov     [rsp+0B0h+var_68], rax
0x18010f707  lea     rax, [rbp+57h+var_48]
0x18010f70b  mov     [rsp+0B0h+var_70], rax
0x18010f710  lea     rax, [rbp+57h+var_5C]
0x18010f714  mov     [rsp+0B0h+var_78], rax
0x18010f719  lea     rax, [rbp+57h+var_50]
0x18010f71d  mov     [rsp+0B0h+var_80], rax
0x18010f722  lea     rax, [rbp+57h+var_60]
0x18010f726  mov     [rsp+0B0h+var_88], rax
0x18010f72b  lea     rax, [rbp+57h+var_58]
0x18010f72f  jmp     loc_18010F922
0x18010f734  lea     r14, [rbx+50h]
0x18010f738  mov     rcx, r14; lpCriticalSection
0x18010f73b  call    cs:__imp_EnterCriticalSection
0x18010f741  cmp     qword ptr [rbx+510h], 0
0x18010f749  jz      short loc_18010F777
0x18010f74b  lea     rcx, [rbx+290h]
0x18010f752  mov     rdx, rsi
0x18010f755  xor     edi, edi
0x18010f757  call    ?AddTail@?$CComPtrList@UIRDPENCNetStreamBuffer@@V?$ComPlainSmartPtr@UIRDPENCNetStreamBuffer@@@@@@QEAAPEAXPEAUIRDPENCNetStreamBuffer@@@Z; CComPtrList<IRDPENCNetStreamBuffer,ComPlainSmartPtr<IRDPENCNetStreamBuffer>>::AddTail(IRDPENCNetStreamBuffer *)
0x18010f75c  mov     rcx, [rbx+6F0h]; hEvent
0x18010f763  call    cs:__imp_SetEvent
0x18010f769  mov     rcx, r14; lpCriticalSection
0x18010f76c  call    cs:__imp_LeaveCriticalSection
0x18010f772  jmp     loc_18010F92C
0x18010f777  cmp     dword ptr [rbx+84h], 0
0x18010f77e  jz      loc_18010F87F
0x18010f784  mov     rax, [rsi]
0x18010f787  lea     rdx, [rbp+57h+var_5C]
0x18010f78b  mov     rcx, rsi
0x18010f78e  mov     [rbp+57h+var_60], 0
0x18010f795  mov     [rbp+57h+var_5C], 0
0x18010f79c  mov     rax, [rax+38h]
0x18010f7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f7a5  mov     rax, [rsi]
0x18010f7a8  lea     rdx, [rbp+57h+var_60]
0x18010f7ac  mov     rcx, rsi
0x18010f7af  mov     rax, [rax+28h]
0x18010f7b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f7b8  mov     eax, [rbp+57h+var_60]
0x18010f7bb  cmp     eax, 1
0x18010f7be  jg      loc_18010F851
0x18010f7c4  mov     eax, cs:CallbackContext
0x18010f7ca  mov     edi, 80070057h
0x18010f7cf  cmp     eax, 2
0x18010f7d2  jbe     short loc_18010F769
0x18010f7d4  lea     rax, aReadbufferFirs; "ReadBuffer: First payload size must be "...
0x18010f7db  mov     dword ptr [rbp+57h+var_58], 62Bh
0x18010f7e2  mov     [rbp+57h+var_40], rax
0x18010f7e6  lea     rdx, qword_1801C8B18
0x18010f7ed  lea     rax, aReadbuffer; "ReadBuffer"
0x18010f7f4  mov     dword ptr [rbp+57h+var_50], edi
0x18010f7f7  mov     [rbp+57h+var_48], rax
0x18010f7fb  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010f802  mov     [rbp+57h+var_38], rax
0x18010f806  lea     rax, aErrorCondition; "Error condition failed"
0x18010f80d  mov     [rbp+57h+var_30], rax
0x18010f811  lea     rax, [rbp+57h+var_40]
0x18010f815  mov     [rsp+0B0h+var_68], rax
0x18010f81a  lea     rax, [rbp+57h+var_48]
0x18010f81e  mov     [rsp+0B0h+var_70], rax
0x18010f823  lea     rax, [rbp+57h+var_58]
0x18010f827  mov     [rsp+0B0h+var_78], rax
0x18010f82c  lea     rax, [rbp+57h+var_38]
0x18010f830  mov     [rsp+0B0h+var_80], rax
0x18010f835  lea     rax, [rbp+57h+var_50]
0x18010f839  mov     [rsp+0B0h+var_88], rax
0x18010f83e  lea     rax, [rbp+57h+var_30]
0x18010f842  mov     [rsp+0B0h+var_90], rax
0x18010f847  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18010f84c  jmp     loc_18010F769
0x18010f851  mov     edx, [rbp+57h+var_5C]
0x18010f854  dec     eax
0x18010f856  mov     [rbp+57h+var_60], eax
0x18010f859  inc     edx
0x18010f85b  mov     rax, [rsi]
0x18010f85e  mov     rcx, rsi
0x18010f861  mov     [rbp+57h+var_5C], edx
0x18010f864  mov     rax, [rax+40h]
0x18010f868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f86d  mov     rax, [rsi]
0x18010f870  mov     rcx, rsi
0x18010f873  mov     edx, [rbp+57h+var_60]
0x18010f876  mov     rax, [rax+30h]
0x18010f87a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f87f  lea     rcx, [rbx+290h]
0x18010f886  mov     rdx, rsi
0x18010f889  call    ?AddTail@?$CComPtrList@UIRDPENCNetStreamBuffer@@V?$ComPlainSmartPtr@UIRDPENCNetStreamBuffer@@@@@@QEAAPEAXPEAUIRDPENCNetStreamBuffer@@@Z; CComPtrList<IRDPENCNetStreamBuffer,ComPlainSmartPtr<IRDPENCNetStreamBuffer>>::AddTail(IRDPENCNetStreamBuffer *)
0x18010f88e  mov     rcx, r14; lpCriticalSection
0x18010f891  call    cs:__imp_LeaveCriticalSection
0x18010f897  mov     rcx, rbx; this
0x18010f89a  call    ?FlushReadBuffer@CWSStream@@AEAAJXZ; CWSStream::FlushReadBuffer(void)
0x18010f89f  mov     edi, eax
0x18010f8a1  test    eax, eax
0x18010f8a3  jns     loc_18010F92C
0x18010f8a9  mov     ecx, cs:CallbackContext
0x18010f8af  cmp     ecx, 2
0x18010f8b2  jbe     short loc_18010F92C
0x18010f8b4  lea     rax, aFlushreadbuffe; "FlushReadBuffer failed"
0x18010f8bb  mov     dword ptr [rbp+57h+var_50], 63Ah
0x18010f8c2  mov     [rbp+57h+var_30], rax
0x18010f8c6  lea     rdx, byte_1801C8B69
0x18010f8cd  lea     rax, aReadbuffer; "ReadBuffer"
0x18010f8d4  mov     dword ptr [rbp+57h+var_58], edi
0x18010f8d7  mov     [rbp+57h+var_38], rax
0x18010f8db  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010f8e2  mov     [rbp+57h+var_40], rax
0x18010f8e6  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18010f8ed  mov     [rbp+57h+var_48], rax
0x18010f8f1  lea     rax, [rbp+57h+var_30]
0x18010f8f5  mov     [rsp+0B0h+var_68], rax
0x18010f8fa  lea     rax, [rbp+57h+var_38]
0x18010f8fe  mov     [rsp+0B0h+var_70], rax
0x18010f903  lea     rax, [rbp+57h+var_50]
0x18010f907  mov     [rsp+0B0h+var_78], rax
0x18010f90c  lea     rax, [rbp+57h+var_40]
0x18010f910  mov     [rsp+0B0h+var_80], rax
0x18010f915  lea     rax, [rbp+57h+var_58]
0x18010f919  mov     [rsp+0B0h+var_88], rax
0x18010f91e  lea     rax, [rbp+57h+var_48]
0x18010f922  mov     [rsp+0B0h+var_90], rax
0x18010f927  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18010f92c  lea     rcx, [rbp+57h+ActivityId]; ActivityId
0x18010f930  call    ??1CAutoSetThreadActivityId@@QEAA@XZ; CAutoSetThreadActivityId::~CAutoSetThreadActivityId(void)
0x18010f935  mov     eax, edi
0x18010f937  mov     rcx, [rbp+57h+var_18]
0x18010f93b  xor     rcx, rsp; StackCookie
0x18010f93e  call    __security_check_cookie
0x18010f943  lea     r11, [rsp+0B0h+var_10]
0x18010f94b  mov     rbx, [r11+30h]
0x18010f94f  mov     rsi, [r11+38h]
0x18010f953  mov     rsp, r11
0x18010f956  pop     r14
0x18010f958  pop     rdi
0x18010f959  pop     rbp
0x18010f95a  retn
```
