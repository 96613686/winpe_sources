# CRDPENCCONSecurityFilterStream::GetUserToken(void * *)

- ea: `0x180060140`
- end: `0x18006036f`
- name: `?GetUserToken@CRDPENCCONSecurityFilterStream@@UEAAJPEAPEAX@Z`
- size: `559`
- prototype: `int(CRDPENCCONSecurityFilterStream *__hidden this, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001aa0`
- `0x18004e90c`
- `0x180060140`
- `0x1800888d8`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060210`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006035c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006035c`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180060206`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180060206`

## string_xrefs

- `0x18006023c`: `DuplicateToken failed`
- `0x18006019b`: `GetUserToken`
- `0x1800602f3`: `GetUserToken`
- `0x180060291`: `m_spRdsAadAuthServer->GetUserToken failed.`
- `0x1800602da`: `m_spSecFilter->GetUserToken failed.`

## pseudocode

```c
__int64 __fastcall CRDPENCCONSecurityFilterStream::GetUserToken(CRDPENCCONSecurityFilterStream *this, void **a2)
{
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  signed int v7; // ebx
  char *v8; // rdx
  const char **v9; // rax
  void *v10; // rcx
  signed int LastError; // eax
  const char *v12; // rax
  __int64 v13; // rcx
  unsigned int v14; // eax
  const char **v16; // [rsp+40h] [rbp-40h]
  const char *v17; // [rsp+50h] [rbp-30h] BYREF
  const char *v18; // [rsp+58h] [rbp-28h] BYREF
  const char *v19; // [rsp+60h] [rbp-20h] BYREF
  int v20; // [rsp+68h] [rbp-18h] BYREF
  PSRWLOCK SRWLock; // [rsp+70h] [rbp-10h]
  int v22; // [rsp+A0h] [rbp+20h] BYREF
  signed int v23; // [rsp+B0h] [rbp+30h] BYREF
  const char *v24; // [rsp+B8h] [rbp+38h] BYREF

  CAutoReadLock<CTSThreadPoolSafeReaderWriterLock>::CAutoReadLock<CTSThreadPoolSafeReaderWriterLock>(
    &v20,
    (char *)this + 64);
  if ( *((_DWORD *)this + 68) != 8 )
  {
    v7 = -2147019873;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_21;
    v22 = 3358;
    v24 = "state check failed.";
    v8 = byte_1801C0699;
    v17 = "GetUserToken";
    v18 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencsecfilter.cpp";
    v19 = "Error HResult failed";
    v16 = &v17;
    v9 = &v19;
    goto LABEL_20;
  }
  v10 = (void *)*((_QWORD *)this + 52);
  if ( v10 )
  {
    if ( DuplicateToken(v10, SecurityImpersonation, a2) )
    {
      v7 = 0;
      goto LABEL_21;
    }
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 && (unsigned int)CallbackContext > 2 )
    {
      v12 = "DuplicateToken failed";
      v22 = 3366;
      v8 = (char *)word_1801C059A;
LABEL_19:
      v24 = v12;
      v19 = "GetUserToken";
      v18 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencsecfilter.cpp";
      v17 = "Error HResult failed";
      v16 = &v19;
      v9 = &v17;
LABEL_20:
      v23 = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v4,
        (_DWORD)v8,
        v5,
        v6,
        (__int64)v9,
        (__int64)&v23,
        (__int64)&v18,
        (__int64)&v22,
        (__int64)v16,
        (__int64)&v24);
    }
  }
  else
  {
    v13 = *((_QWORD *)this + 48);
    if ( v13 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v13 + 48LL))(v13, a2);
      if ( v7 < 0 )
      {
        v4 = (int)CallbackContext;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v12 = "m_spRdsAadAuthServer->GetUserToken failed.";
          v22 = 3375;
          v8 = &byte_1801C05EF;
          goto LABEL_19;
        }
      }
    }
    else
    {
      v14 = (*(__int64 (__fastcall **)(_QWORD, void **))(**((_QWORD **)this + 47) + 152LL))(*((_QWORD *)this + 47), a2);
      v7 = MapXResultToHR(v14);
      if ( v7 < 0 && (unsigned int)CallbackContext > 2 )
      {
        v12 = "m_spSecFilter->GetUserToken failed.";
        v22 = 3380;
        v8 = byte_1801C0545;
        goto LABEL_19;
      }
    }
  }
LABEL_21:
  if ( v20 )
    ReleaseSRWLockShared(SRWLock);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180060140  push    rbp
0x180060142  push    rbx
0x180060143  push    rdi
0x180060144  mov     rbp, rsp
0x180060147  sub     rsp, 80h
0x18006014e  mov     rdi, rdx
0x180060151  mov     rbx, rcx
0x180060154  lea     rdx, [rcx+40h]
0x180060158  lea     rcx, [rbp+var_18]
0x18006015c  call    ??0?$CAutoReadLock@VCTSThreadPoolSafeReaderWriterLock@@@@QEAA@AEAVCTSThreadPoolSafeReaderWriterLock@@H@Z; CAutoReadLock<CTSThreadPoolSafeReaderWriterLock>::CAutoReadLock<CTSThreadPoolSafeReaderWriterLock>(CTSThreadPoolSafeReaderWriterLock &,int)
0x180060161  cmp     dword ptr [rbx+110h], 8
0x180060168  jz      loc_1800601F2
0x18006016e  mov     eax, cs:CallbackContext
0x180060174  mov     ebx, 8007139Fh
0x180060179  cmp     eax, 2
0x18006017c  jbe     loc_180060352
0x180060182  lea     rax, aStateCheckFail; "state check failed."
0x180060189  mov     [rbp+arg_0], 0D1Eh
0x180060190  mov     [rbp+arg_18], rax
0x180060194  lea     rdx, byte_1801C0699
0x18006019b  lea     rax, aGetusertoken; "GetUserToken"
0x1800601a2  mov     [rbp+var_30], rax
0x1800601a6  lea     rax, aOnecoreTermsrv_70; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800601ad  mov     [rbp+var_28], rax
0x1800601b1  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800601b8  mov     [rbp+var_20], rax
0x1800601bc  lea     rax, [rbp+arg_18]
0x1800601c0  mov     [rsp+80h+var_38], rax
0x1800601c5  lea     rax, [rbp+var_30]
0x1800601c9  mov     [rsp+80h+var_40], rax
0x1800601ce  lea     rax, [rbp+arg_0]
0x1800601d2  mov     [rsp+80h+var_48], rax
0x1800601d7  lea     rax, [rbp+var_28]
0x1800601db  mov     [rsp+80h+var_50], rax
0x1800601e0  lea     rax, [rbp+arg_10]
0x1800601e4  mov     [rsp+80h+var_58], rax
0x1800601e9  lea     rax, [rbp+var_20]
0x1800601ed  jmp     loc_180060345
0x1800601f2  mov     rcx, [rbx+1A0h]; ExistingTokenHandle
0x1800601f9  test    rcx, rcx
0x1800601fc  jz      short loc_18006025D
0x1800601fe  mov     r8, rdi; DuplicateTokenHandle
0x180060201  mov     edx, 2; ImpersonationLevel
0x180060206  call    cs:__imp_DuplicateToken
0x18006020c  test    eax, eax
0x18006020e  jnz     short loc_180060256
0x180060210  call    cs:__imp_GetLastError
0x180060216  mov     ebx, eax
0x180060218  test    eax, eax
0x18006021a  jle     short loc_180060225
0x18006021c  movzx   ebx, ax
0x18006021f  or      ebx, 80070000h
0x180060225  test    ebx, ebx
0x180060227  jns     loc_180060352
0x18006022d  mov     eax, cs:CallbackContext
0x180060233  cmp     eax, 2
0x180060236  jbe     loc_180060352
0x18006023c  lea     rax, aDuplicatetoken; "DuplicateToken failed"
0x180060243  mov     [rbp+arg_0], 0D26h
0x18006024a  lea     rdx, word_1801C059A
0x180060251  jmp     loc_1800602EF
0x180060256  xor     ebx, ebx
0x180060258  jmp     loc_180060352
0x18006025d  mov     rcx, [rbx+180h]
0x180060264  mov     rdx, rdi
0x180060267  test    rcx, rcx
0x18006026a  jz      short loc_1800602A8
0x18006026c  mov     rax, [rcx]
0x18006026f  mov     rax, [rax+30h]
0x180060273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060278  mov     ebx, eax
0x18006027a  test    eax, eax
0x18006027c  jns     loc_180060352
0x180060282  mov     ecx, cs:CallbackContext
0x180060288  cmp     ecx, 2
0x18006028b  jbe     loc_180060352
0x180060291  lea     rax, aMSprdsaadauths_0; "m_spRdsAadAuthServer->GetUserToken fail"...
0x180060298  mov     [rbp+arg_0], 0D2Fh
0x18006029f  lea     rdx, byte_1801C05EF
0x1800602a6  jmp     short loc_1800602EF
0x1800602a8  mov     rcx, [rbx+178h]
0x1800602af  mov     rax, [rcx]
0x1800602b2  mov     rax, [rax+98h]
0x1800602b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800602be  mov     ecx, eax
0x1800602c0  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x1800602c5  mov     ebx, eax
0x1800602c7  test    eax, eax
0x1800602c9  jns     loc_180060352
0x1800602cf  mov     eax, cs:CallbackContext
0x1800602d5  cmp     eax, 2
0x1800602d8  jbe     short loc_180060352
0x1800602da  lea     rax, aMSpsecfilterGe_2; "m_spSecFilter->GetUserToken failed."
0x1800602e1  mov     [rbp+arg_0], 0D34h
0x1800602e8  lea     rdx, byte_1801C0545
0x1800602ef  mov     [rbp+arg_18], rax
0x1800602f3  lea     rax, aGetusertoken; "GetUserToken"
0x1800602fa  mov     [rbp+var_20], rax
0x1800602fe  lea     rax, aOnecoreTermsrv_70; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180060305  mov     [rbp+var_28], rax
0x180060309  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180060310  mov     [rbp+var_30], rax
0x180060314  lea     rax, [rbp+arg_18]
0x180060318  mov     [rsp+80h+var_38], rax
0x18006031d  lea     rax, [rbp+var_20]
0x180060321  mov     [rsp+80h+var_40], rax
0x180060326  lea     rax, [rbp+arg_0]
0x18006032a  mov     [rsp+80h+var_48], rax
0x18006032f  lea     rax, [rbp+var_28]
0x180060333  mov     [rsp+80h+var_50], rax
0x180060338  lea     rax, [rbp+arg_10]
0x18006033c  mov     [rsp+80h+var_58], rax
0x180060341  lea     rax, [rbp+var_30]
0x180060345  mov     [rsp+80h+var_60], rax
0x18006034a  mov     [rbp+arg_10], ebx
0x18006034d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180060352  cmp     [rbp+var_18], 0
0x180060356  jz      short loc_180060362
0x180060358  mov     rcx, [rbp+SRWLock]; SRWLock
0x18006035c  call    cs:__imp_ReleaseSRWLockShared
0x180060362  mov     eax, ebx
0x180060364  add     rsp, 80h
0x18006036b  pop     rdi
0x18006036c  pop     rbx
0x18006036d  pop     rbp
0x18006036e  retn
```
