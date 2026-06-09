# CWSStream::ReportReadCompletion(uchar *,uint,ComPlainSmartPtr<IRDPENCNetStreamBuffer>)

- ea: `0x18010fa68`
- end: `0x18010feaf`
- name: `?ReportReadCompletion@CWSStream@@AEAAXPEAEIV?$ComPlainSmartPtr@UIRDPENCNetStreamBuffer@@@@@Z`
- size: `1095`
- prototype: `void __fastcall(CWSStream *this, void *Src, int, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010f3f4`

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x180002550`
- `0x180019a80`
- `0x180019ab0`
- `0x18001b3f8`
- `0x180040750`
- `0x180078c20`
- `0x180109934`
- `0x18010cb60`
- `0x18010fa68`
- `0x1801614c4`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18010fb42`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18010fba5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18010fb42`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18010fba5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010facd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010facd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010fb23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010fb23`

## string_xrefs

- `0x18010fc21`: `ReadBuffer: Stream closed`
- `0x18010fcbb`: `ReadBuffer: Stream closed`
- `0x18010fc3a`: `ReportReadCompletion`
- `0x18010fcd4`: `ReportReadCompletion`
- `0x18010fd53`: `ReportReadCompletion`

## pseudocode

```c
void __fastcall CWSStream::ReportReadCompletion(CWSStream *this, void *Src, int a3, _QWORD *a4)
{
  __int64 v4; // r14
  __int64 v7; // rbx
  int v10; // r15d
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  unsigned int v14; // r14d
  int v15; // [rsp+50h] [rbp-59h] BYREF
  int v16; // [rsp+54h] [rbp-55h] BYREF
  int v17; // [rsp+58h] [rbp-51h] BYREF
  int v18; // [rsp+5Ch] [rbp-4Dh] BYREF
  const char *v19; // [rsp+60h] [rbp-49h] BYREF
  int v20; // [rsp+68h] [rbp-41h] BYREF
  const char *v21; // [rsp+70h] [rbp-39h] BYREF
  const char *v22; // [rsp+78h] [rbp-31h] BYREF
  __int64 v23; // [rsp+80h] [rbp-29h] BYREF
  __int64 v24; // [rsp+88h] [rbp-21h] BYREF
  const char *v25; // [rsp+90h] [rbp-19h] BYREF
  __int64 v26; // [rsp+98h] [rbp-11h] BYREF
  GUID ActivityId; // [rsp+A0h] [rbp-9h] BYREF

  v4 = 0;
  v26 = 0;
  v20 = 0;
  v7 = 0;
  v18 = 0;
  v24 = 0;
  v17 = 0;
  v23 = 0;
  CAutoSetThreadActivityId::CAutoSetThreadActivityId(&ActivityId, (const struct _GUID *)((char *)this + 1148));
  EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
  if ( *((_QWORD *)this + 21) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease(&v24);
    v7 = *((_QWORD *)this + 21);
    v24 = v7;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v24);
  }
  if ( *((_QWORD *)this + 139) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease(&v23);
    v4 = *((_QWORD *)this + 139);
    v23 = v4;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v23);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
  v10 = 0;
  if ( v4 )
  {
    *((_DWORD *)this + 281) += 8 * a3;
    if ( GetTickCount() - *((_DWORD *)this + 283) > 0x64 )
    {
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v4 + 32LL))(v4, 105, *((unsigned int *)this + 281));
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v4 + 32LL))(v4, 104, *((unsigned int *)this + 281));
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v4 + 32LL))(v4, 124, *((_DWORD *)this + 281) >> 3);
      *((_DWORD *)this + 283) = GetTickCount();
      *((_DWORD *)this + 281) = 0;
    }
  }
  (*(void (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a4 + 24LL))(*a4, &v26);
  (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a4 + 32LL))(*a4, &v20);
  (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a4 + 56LL))(*a4, &v18);
  (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a4 + 40LL))(*a4, &v17);
  if ( *((_DWORD *)this + 30) )
  {
    if ( *((_DWORD *)this + 31) )
    {
      if ( v17 + v18 <= v20 )
      {
        if ( a3 <= v17 )
        {
          v14 = a3;
        }
        else
        {
          if ( (unsigned int)CallbackContext > 4 )
          {
            v19 = "The received data size is greater than the target buffer size. Splitting the payload.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              (unsigned int)&CallbackContext,
              (unsigned int)&dword_1801C7C44,
              0,
              v13,
              (__int64)&v19);
          }
          v14 = v17;
          v10 = a3 - v17;
        }
        (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a4 + 48LL))(*a4, v14);
        memcpy_0((void *)(v26 + v18), Src, (int)v14);
        if ( v7 )
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 32LL))(v7, *a4);
        if ( v10 )
          CWSStream::HandleReceivedData(this, (const unsigned __int8 *)Src + (int)v14, (const char *)v10, 1);
      }
      else
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v16 = 2635;
          v19 = "ReportReadCompletion";
          v15 = -2147418113;
          v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
          v21 = "Buffer overflow detected";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v17 + v18,
            (unsigned int)byte_1801C7BFB,
            v12,
            v13,
            (__int64)&v21,
            (__int64)&v15,
            (__int64)&v22,
            (__int64)&v16,
            (__int64)&v19);
        }
        CWSStream::CloseInternal(this, 0, 0, -2147418113);
      }
    }
    else if ( (unsigned int)CallbackContext > 2 )
    {
      v16 = 2632;
      v19 = "ReadBuffer: Stream closed";
      v15 = -2147467259;
      v22 = "ReportReadCompletion";
      v21 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
      v25 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v11,
        (unsigned int)word_1801C7CBA,
        v12,
        v13,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v21,
        (__int64)&v16,
        (__int64)&v22,
        (__int64)&v19);
    }
  }
  else if ( (unsigned int)CallbackContext > 2 )
  {
    v15 = 2631;
    v25 = "ReadBuffer: Stream closed";
    v16 = -2147467259;
    v21 = "ReportReadCompletion";
    v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
    v19 = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v11,
      (unsigned int)byte_1801C7C69,
      v12,
      v13,
      (__int64)&v19,
      (__int64)&v16,
      (__int64)&v22,
      (__int64)&v15,
      (__int64)&v21,
      (__int64)&v25);
  }
  CAutoSetThreadActivityId::~CAutoSetThreadActivityId(&ActivityId);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v23);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v24);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(a4);
}

```

## disassembly

```asm
0x18010fa68  push    rbp
0x18010fa6a  push    rbx
0x18010fa6b  push    rsi
0x18010fa6c  push    rdi
0x18010fa6d  push    r12
0x18010fa6f  push    r13
0x18010fa71  push    r14
0x18010fa73  push    r15
0x18010fa75  lea     rbp, [rsp-1Fh]
0x18010fa7a  sub     rsp, 0C8h
0x18010fa81  mov     rax, cs:__security_cookie
0x18010fa88  xor     rax, rsp
0x18010fa8b  mov     [rbp+57h+var_50], rax
0x18010fa8f  xor     r14d, r14d
0x18010fa92  mov     r13, rdx
0x18010fa95  mov     rdi, rcx
0x18010fa98  mov     [rbp+57h+var_68], r14
0x18010fa9c  lea     rdx, [rcx+47Ch]; struct _GUID *
0x18010faa3  mov     [rbp+57h+var_98], r14d
0x18010faa7  mov     ebx, r14d
0x18010faaa  mov     [rbp+57h+var_A4], r14d
0x18010faae  lea     rcx, [rbp+57h+ActivityId]; ActivityId
0x18010fab2  mov     [rbp+57h+var_78], rbx
0x18010fab6  mov     r12, r9
0x18010fab9  mov     [rbp+57h+var_A8], r14d
0x18010fabd  mov     esi, r8d
0x18010fac0  mov     [rbp+57h+var_80], r14
0x18010fac4  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x18010fac9  lea     rcx, [rdi+50h]; lpCriticalSection
0x18010facd  call    cs:__imp_EnterCriticalSection
0x18010fad3  cmp     [rdi+0A8h], r14
0x18010fada  jz      short loc_18010FAF9
0x18010fadc  lea     rcx, [rbp+57h+var_78]; void *
0x18010fae0  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18010fae5  mov     rbx, [rdi+0A8h]
0x18010faec  lea     rcx, [rbp+57h+var_78]
0x18010faf0  mov     [rbp+57h+var_78], rbx
0x18010faf4  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18010faf9  cmp     [rdi+458h], r14
0x18010fb00  jz      short loc_18010FB1F
0x18010fb02  lea     rcx, [rbp+57h+var_80]; void *
0x18010fb06  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18010fb0b  mov     r14, [rdi+458h]
0x18010fb12  lea     rcx, [rbp+57h+var_80]
0x18010fb16  mov     [rbp+57h+var_80], r14
0x18010fb1a  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18010fb1f  lea     rcx, [rdi+50h]; lpCriticalSection
0x18010fb23  call    cs:__imp_LeaveCriticalSection
0x18010fb29  xor     r15d, r15d
0x18010fb2c  test    r14, r14
0x18010fb2f  jz      loc_18010FBB8
0x18010fb35  lea     eax, ds:0[rsi*8]
0x18010fb3c  add     [rdi+464h], eax
0x18010fb42  call    cs:__imp_GetTickCount
0x18010fb48  sub     eax, [rdi+46Ch]
0x18010fb4e  cmp     eax, 64h ; 'd'
0x18010fb51  jbe     short loc_18010FBB8
0x18010fb53  mov     rax, [r14]
0x18010fb56  lea     edx, [r15+69h]
0x18010fb5a  mov     r8d, [rdi+464h]
0x18010fb61  mov     rcx, r14
0x18010fb64  mov     rax, [rax+20h]
0x18010fb68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fb6d  mov     rax, [r14]
0x18010fb70  lea     edx, [r15+68h]
0x18010fb74  mov     r8d, [rdi+464h]
0x18010fb7b  mov     rcx, r14
0x18010fb7e  mov     rax, [rax+20h]
0x18010fb82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fb87  mov     rax, [r14]
0x18010fb8a  lea     edx, [r15+7Ch]
0x18010fb8e  mov     r8d, [rdi+464h]
0x18010fb95  mov     rcx, r14
0x18010fb98  shr     r8d, 3
0x18010fb9c  mov     rax, [rax+20h]
0x18010fba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fba5  call    cs:__imp_GetTickCount
0x18010fbab  mov     [rdi+46Ch], eax
0x18010fbb1  mov     [rdi+464h], r15d
0x18010fbb8  mov     rcx, [r12]
0x18010fbbc  lea     rdx, [rbp+57h+var_68]
0x18010fbc0  mov     rax, [rcx]
0x18010fbc3  mov     rax, [rax+18h]
0x18010fbc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fbcc  mov     rcx, [r12]
0x18010fbd0  lea     rdx, [rbp+57h+var_98]
0x18010fbd4  mov     rax, [rcx]
0x18010fbd7  mov     rax, [rax+20h]
0x18010fbdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fbe0  mov     rcx, [r12]
0x18010fbe4  lea     rdx, [rbp+57h+var_A4]
0x18010fbe8  mov     rax, [rcx]
0x18010fbeb  mov     rax, [rax+38h]
0x18010fbef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fbf4  mov     rcx, [r12]
0x18010fbf8  lea     rdx, [rbp+57h+var_A8]
0x18010fbfc  mov     rax, [rcx]
0x18010fbff  mov     rax, [rax+28h]
0x18010fc03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fc08  cmp     [rdi+78h], r15d
0x18010fc0c  jnz     loc_18010FCA2
0x18010fc12  mov     eax, cs:CallbackContext
0x18010fc18  cmp     eax, 2
0x18010fc1b  jbe     loc_18010FE6C
0x18010fc21  lea     rax, aReadbufferStre; "ReadBuffer: Stream closed"
0x18010fc28  mov     [rbp+57h+var_B0], 0A47h
0x18010fc2f  mov     [rbp+57h+var_70], rax
0x18010fc33  lea     rdx, byte_1801C7C69
0x18010fc3a  lea     rax, aReportreadcomp; "ReportReadCompletion"
0x18010fc41  mov     [rbp+57h+var_AC], 80004005h
0x18010fc48  mov     [rbp+57h+var_90], rax
0x18010fc4c  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010fc53  mov     [rbp+57h+var_88], rax
0x18010fc57  lea     rax, aErrorCondition; "Error condition failed"
0x18010fc5e  mov     [rbp+57h+var_A0], rax
0x18010fc62  lea     rax, [rbp+57h+var_70]
0x18010fc66  mov     [rsp+100h+var_B8], rax
0x18010fc6b  lea     rax, [rbp+57h+var_90]
0x18010fc6f  mov     [rsp+100h+var_C0], rax
0x18010fc74  lea     rax, [rbp+57h+var_B0]
0x18010fc78  mov     [rsp+100h+var_C8], rax
0x18010fc7d  lea     rax, [rbp+57h+var_88]
0x18010fc81  mov     [rsp+100h+var_D0], rax
0x18010fc86  lea     rax, [rbp+57h+var_AC]
0x18010fc8a  mov     [rsp+100h+var_D8], rax
0x18010fc8f  lea     rax, [rbp+57h+var_A0]
0x18010fc93  mov     [rsp+100h+var_E0], rax
0x18010fc98  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18010fc9d  jmp     loc_18010FE6C
0x18010fca2  cmp     [rdi+7Ch], r15d
0x18010fca6  jnz     loc_18010FD32
0x18010fcac  mov     eax, cs:CallbackContext
0x18010fcb2  cmp     eax, 2
0x18010fcb5  jbe     loc_18010FE6C
0x18010fcbb  lea     rax, aReadbufferStre; "ReadBuffer: Stream closed"
0x18010fcc2  mov     [rbp+57h+var_AC], 0A48h
0x18010fcc9  mov     [rbp+57h+var_A0], rax
0x18010fccd  lea     rdx, word_1801C7CBA
0x18010fcd4  lea     rax, aReportreadcomp; "ReportReadCompletion"
0x18010fcdb  mov     [rbp+57h+var_B0], 80004005h
0x18010fce2  mov     [rbp+57h+var_88], rax
0x18010fce6  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010fced  mov     [rbp+57h+var_90], rax
0x18010fcf1  lea     rax, aErrorCondition; "Error condition failed"
0x18010fcf8  mov     [rbp+57h+var_70], rax
0x18010fcfc  lea     rax, [rbp+57h+var_A0]
0x18010fd00  mov     [rsp+100h+var_B8], rax
0x18010fd05  lea     rax, [rbp+57h+var_88]
0x18010fd09  mov     [rsp+100h+var_C0], rax
0x18010fd0e  lea     rax, [rbp+57h+var_AC]
0x18010fd12  mov     [rsp+100h+var_C8], rax
0x18010fd17  lea     rax, [rbp+57h+var_90]
0x18010fd1b  mov     [rsp+100h+var_D0], rax
0x18010fd20  lea     rax, [rbp+57h+var_B0]
0x18010fd24  mov     [rsp+100h+var_D8], rax
0x18010fd29  lea     rax, [rbp+57h+var_70]
0x18010fd2d  jmp     loc_18010FC93
0x18010fd32  mov     ecx, [rbp+57h+var_A4]
0x18010fd35  mov     edx, [rbp+57h+var_A8]
0x18010fd38  add     ecx, edx
0x18010fd3a  cmp     ecx, [rbp+57h+var_98]
0x18010fd3d  jle     loc_18010FDCC
0x18010fd43  mov     eax, cs:CallbackContext
0x18010fd49  mov     ebx, 8000FFFFh
0x18010fd4e  cmp     eax, 2
0x18010fd51  jbe     short loc_18010FDB7
0x18010fd53  lea     rax, aReportreadcomp; "ReportReadCompletion"
0x18010fd5a  mov     [rbp+57h+var_AC], 0A4Bh
0x18010fd61  mov     [rbp+57h+var_A0], rax
0x18010fd65  lea     rdx, byte_1801C7BFB
0x18010fd6c  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010fd73  mov     [rbp+57h+var_B0], ebx
0x18010fd76  mov     [rbp+57h+var_88], rax
0x18010fd7a  lea     rax, aBufferOverflow; "Buffer overflow detected"
0x18010fd81  mov     [rbp+57h+var_90], rax
0x18010fd85  lea     rax, [rbp+57h+var_A0]
0x18010fd89  mov     [rsp+100h+var_C0], rax
0x18010fd8e  lea     rax, [rbp+57h+var_AC]
0x18010fd92  mov     [rsp+100h+var_C8], rax
0x18010fd97  lea     rax, [rbp+57h+var_88]
0x18010fd9b  mov     [rsp+100h+var_D0], rax
0x18010fda0  lea     rax, [rbp+57h+var_B0]
0x18010fda4  mov     [rsp+100h+var_D8], rax
0x18010fda9  lea     rax, [rbp+57h+var_90]
0x18010fdad  mov     [rsp+100h+var_E0], rax
0x18010fdb2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18010fdb7  mov     r9d, ebx; int
0x18010fdba  xor     r8d, r8d; unsigned int
0x18010fdbd  xor     edx, edx; int
0x18010fdbf  mov     rcx, rdi; this
0x18010fdc2  call    ?CloseInternal@CWSStream@@AEAAJHKJ@Z; CWSStream::CloseInternal(int,ulong,long)
0x18010fdc7  jmp     loc_18010FE6C
0x18010fdcc  cmp     esi, edx
0x18010fdce  jle     short loc_18010FE11
0x18010fdd0  mov     eax, cs:CallbackContext
0x18010fdd6  cmp     eax, 4
0x18010fdd9  jbe     short loc_18010FE05
0x18010fddb  lea     rax, aTheReceivedDat; "The received data size is greater than "...
0x18010fde2  xor     r8d, r8d
0x18010fde5  mov     [rbp+57h+var_A0], rax
0x18010fde9  lea     rdx, dword_1801C7C44
0x18010fdf0  lea     rax, [rbp+57h+var_A0]
0x18010fdf4  lea     rcx, CallbackContext
0x18010fdfb  mov     [rsp+100h+var_E0], rax
0x18010fe00  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18010fe05  mov     r14d, [rbp+57h+var_A8]
0x18010fe09  sub     esi, r14d
0x18010fe0c  mov     r15d, esi
0x18010fe0f  jmp     short loc_18010FE14
0x18010fe11  mov     r14d, esi
0x18010fe14  mov     rcx, [r12]
0x18010fe18  mov     edx, r14d
0x18010fe1b  mov     rax, [rcx]
0x18010fe1e  mov     rax, [rax+30h]
0x18010fe22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fe27  movsxd  rcx, [rbp+57h+var_A4]
0x18010fe2b  mov     rdx, r13; Src
0x18010fe2e  add     rcx, [rbp+57h+var_68]; void *
0x18010fe32  movsxd  rsi, r14d
0x18010fe35  mov     r8, rsi; Size
0x18010fe38  call    memcpy_0
0x18010fe3d  test    rbx, rbx
0x18010fe40  jz      short loc_18010FE55
0x18010fe42  mov     rax, [rbx]
0x18010fe45  mov     rcx, rbx
0x18010fe48  mov     rdx, [r12]
0x18010fe4c  mov     rax, [rax+20h]
0x18010fe50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fe55  test    r15d, r15d
0x18010fe58  jz      short loc_18010FE6C
0x18010fe5a  movsxd  r8, r15d; unsigned __int64
0x18010fe5d  lea     rdx, [rsi+r13]; unsigned __int8 *
0x18010fe61  mov     r9b, 1; bool
0x18010fe64  mov     rcx, rdi; this
0x18010fe67  call    ?HandleReceivedData@CWSStream@@AEAAXPEBE_K_N@Z; CWSStream::HandleReceivedData(uchar const *,unsigned __int64,bool)
0x18010fe6c  lea     rcx, [rbp+57h+ActivityId]; ActivityId
0x18010fe70  call    ??1CAutoSetThreadActivityId@@QEAA@XZ; CAutoSetThreadActivityId::~CAutoSetThreadActivityId(void)
0x18010fe75  lea     rcx, [rbp+57h+var_80]; void *
0x18010fe79  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18010fe7e  lea     rcx, [rbp+57h+var_78]; void *
0x18010fe82  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18010fe87  mov     rcx, r12; void *
0x18010fe8a  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18010fe8f  mov     rcx, [rbp+57h+var_50]
0x18010fe93  xor     rcx, rsp; StackCookie
0x18010fe96  call    __security_check_cookie
0x18010fe9b  add     rsp, 0C8h
0x18010fea2  pop     r15
0x18010fea4  pop     r14
0x18010fea6  pop     r13
0x18010fea8  pop     r12
0x18010feaa  pop     rdi
0x18010feab  pop     rsi
0x18010feac  pop     rbx
0x18010fead  pop     rbp
0x18010feae  retn
```
