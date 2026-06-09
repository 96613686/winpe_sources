# Rdp8Scheduler::Initialize(IUnknown *)

- ea: `0x1800deca0`
- end: `0x1800df073`
- name: `?Initialize@Rdp8Scheduler@@UEAAJPEAUIUnknown@@@Z`
- size: `979`
- prototype: `__int64 __fastcall(Rdp8Scheduler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800e007c`

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x180004a94`
- `0x18001e164`
- `0x1800de6c8`
- `0x1800deca0`
- `0x1800df07c`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dee3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800deed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dee3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800deed9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800deec7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800deec7`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800dee2a`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800dee2a`
- `OLEAUT32!__imp_VariantInit` at `0x1800def1b`
- `OLEAUT32!__imp_VariantInit` at `0x1800def1b`
- `OLEAUT32!__imp_VariantClear` at `0x1800def90`
- `OLEAUT32!__imp_VariantClear` at `0x1800def90`

## string_xrefs

- `0x1800dee67`: `Failed CreateSem`
- `0x1800def04`: `Failed CreateEvent`
- `0x1800defc0`: `Failed to initialize Idd security attributes`
- `0x1800deff0`: `CreateNamedEvent`

## pseudocode

```c
__int64 __fastcall Rdp8Scheduler::Initialize(Rdp8Scheduler *this, struct IUnknown *a2, int a3)
{
  _QWORD *v4; // rsi
  unsigned int NamedEvent; // ebx
  int v6; // r8d
  int v7; // r9d
  int v8; // ecx
  char *v9; // rdx
  const char **v10; // rax
  const char *v11; // rax
  HANDLE SemaphoreW; // rax
  signed int v13; // eax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  const char *v17; // rax
  char *v18; // rdx
  HANDLE EventW; // rax
  signed int LastError; // eax
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  Rdp8Scheduler *v24; // rcx
  const char **v26; // [rsp+40h] [rbp-40h]
  const char *v27; // [rsp+50h] [rbp-30h] BYREF
  const char *v28; // [rsp+58h] [rbp-28h] BYREF
  const char *v29; // [rsp+60h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-18h] BYREF
  int v31; // [rsp+B8h] [rbp+38h] BYREF
  const char *v32; // [rsp+C0h] [rbp+40h] BYREF
  const char *v33; // [rsp+C8h] [rbp+48h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  if ( !a2 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v33 = "Initialize";
      v28 = "Unexpected: pPlatformContext is NULL";
      v31 = 441;
      v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdp8scheduler.cpp";
      LODWORD(v32) = -2147418113;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)this,
        (unsigned int)byte_1801BCFE3,
        a3,
        0,
        (__int64)&v28,
        (__int64)&v32,
        (__int64)&v29,
        (__int64)&v31,
        (__int64)&v33);
    }
    v4 = (_QWORD *)((char *)this + 1464);
LABEL_8:
    if ( !(unsigned int)CTSCriticalSection::Initialize((Rdp8Scheduler *)((char *)this + 56)) )
    {
      NamedEvent = -2147024882;
      if ( (unsigned int)CallbackContext <= 2 )
        return NamedEvent;
      v11 = "m_Queue.Initialize";
      v31 = 445;
      v9 = byte_1801BCF43;
      goto LABEL_32;
    }
    SemaphoreW = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
    *((_QWORD *)this + 16) = SemaphoreW;
    if ( SemaphoreW )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 17) = EventW;
      if ( EventW )
      {
        VariantInit(&pvarg);
        if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(*(_QWORD *)*v4 + 24LL))(
               *v4,
               L"EnableWddmIdd",
               &pvarg) >= 0 )
        {
          *((_DWORD *)this + 369) = pvarg.iVal == -1;
          if ( (unsigned int)CallbackContext > 4 )
          {
            v31 = *((_DWORD *)this + 369);
            v32 = "WDDM IDD mode (0=Off, 1=On)";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v21,
              (unsigned int)byte_1801BCE89,
              v22,
              v23,
              (__int64)&v32,
              (__int64)&v31);
          }
        }
        VariantClear(&pvarg);
        if ( *((_DWORD *)this + 369)
          && (NamedEvent = Rdp8Scheduler::InitializeIddSecurityAttr(
                             v24,
                             (struct _SECURITY_ATTRIBUTES *)((char *)this + 1480)),
              (NamedEvent & 0x80000000) != 0) )
        {
          if ( (unsigned int)CallbackContext <= 2 )
            return NamedEvent;
          v11 = "Failed to initialize Idd security attributes";
          v31 = 490;
          v9 = byte_1801BCDE9;
        }
        else
        {
          NamedEvent = Rdp8Scheduler::CreateNamedEvent(this);
          if ( (NamedEvent & 0x80000000) == 0 || (unsigned int)CallbackContext <= 2 )
            return NamedEvent;
          v11 = "CreateNamedEvent";
          v31 = 494;
          v9 = byte_1801BCE39;
        }
LABEL_32:
        v33 = v11;
        v27 = "Error HResult failed";
        v26 = &v29;
        v10 = &v27;
        v29 = "Initialize";
        goto LABEL_33;
      }
      LastError = GetLastError();
      NamedEvent = LastError;
      if ( LastError > 0 )
        NamedEvent = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)CallbackContext <= 2 )
        return NamedEvent;
      v31 = 469;
      v17 = "Failed CreateEvent";
      v18 = byte_1801BCEFB;
    }
    else
    {
      v13 = GetLastError();
      NamedEvent = v13;
      if ( v13 > 0 )
        NamedEvent = (unsigned __int16)v13 | 0x80070000;
      if ( (unsigned int)CallbackContext <= 2 )
        return NamedEvent;
      v31 = 458;
      v17 = "Failed CreateSem";
      v18 = byte_1801BCEB3;
    }
    v28 = v17;
    LODWORD(v32) = NamedEvent;
    v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdp8scheduler.cpp";
    v33 = "Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v14,
      (_DWORD)v18,
      v15,
      v16,
      (__int64)&v28,
      (__int64)&v32,
      (__int64)&v29,
      (__int64)&v31,
      (__int64)&v33);
    return NamedEvent;
  }
  v4 = (_QWORD *)((char *)this + 1464);
  NamedEvent = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
                 a2,
                 &IID_IRDPENCPlatformContext,
                 (char *)this + 1464);
  if ( (NamedEvent & 0x80000000) == 0 )
    goto LABEL_8;
  v8 = (int)CallbackContext;
  if ( (unsigned int)CallbackContext > 2 )
  {
    v27 = "Initialize";
    v33 = "Failed to get the platform context";
    v9 = byte_1801BCF93;
    v31 = 437;
    v29 = "Error HResult failed";
    v26 = &v27;
    v10 = &v29;
LABEL_33:
    v28 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdp8scheduler.cpp";
    LODWORD(v32) = NamedEvent;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v8,
      (_DWORD)v9,
      v6,
      v7,
      (__int64)v10,
      (__int64)&v32,
      (__int64)&v28,
      (__int64)&v31,
      (__int64)v26,
      (__int64)&v33);
  }
  return NamedEvent;
}

```

## disassembly

```asm
0x1800deca0  mov     [rsp-28h+arg_0], rbx
0x1800deca5  push    rbp
0x1800deca6  push    rsi
0x1800deca7  push    rdi
0x1800deca8  push    r12
0x1800decaa  push    r15
0x1800decac  mov     rbp, rsp
0x1800decaf  sub     rsp, 80h
0x1800decb6  xor     eax, eax
0x1800decb8  lea     r15, aInitialize; "Initialize"
0x1800decbf  mov     qword ptr [rbp+pvarg+10h], rax
0x1800decc3  xorps   xmm0, xmm0
0x1800decc6  lea     r12, aOnecoreTermsrv_82; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800deccd  mov     r9, rdx
0x1800decd0  mov     rdi, rcx
0x1800decd3  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800decd7  test    rdx, rdx
0x1800decda  jz      loc_1800DED76
0x1800dece0  mov     rax, [rdx]
0x1800dece3  lea     rsi, [rcx+5B8h]
0x1800decea  mov     r8, rsi
0x1800deced  lea     rdx, IID_IRDPENCPlatformContext
0x1800decf4  mov     rcx, r9
0x1800decf7  mov     rax, [rax]
0x1800decfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800decff  mov     ebx, eax
0x1800ded01  test    eax, eax
0x1800ded03  jns     loc_1800DEDE2
0x1800ded09  mov     ecx, cs:CallbackContext
0x1800ded0f  cmp     ecx, 2
0x1800ded12  jbe     loc_1800DF05A
0x1800ded18  lea     rax, aFailedToGetThe_26; "Failed to get the platform context"
0x1800ded1f  mov     [rbp+var_30], r15
0x1800ded23  mov     [rbp+arg_18], rax
0x1800ded27  lea     rdx, byte_1801BCF93
0x1800ded2e  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800ded35  mov     [rbp+arg_8], 1B5h
0x1800ded3c  mov     [rbp+var_20], rax
0x1800ded40  lea     rax, [rbp+arg_18]
0x1800ded44  mov     [rsp+80h+var_38], rax
0x1800ded49  lea     rax, [rbp+var_30]
0x1800ded4d  mov     [rsp+80h+var_40], rax
0x1800ded52  lea     rax, [rbp+arg_8]
0x1800ded56  mov     [rsp+80h+var_48], rax
0x1800ded5b  lea     rax, [rbp+var_28]
0x1800ded5f  mov     [rsp+80h+var_50], rax
0x1800ded64  lea     rax, [rbp+arg_10]
0x1800ded68  mov     [rsp+80h+var_58], rax
0x1800ded6d  lea     rax, [rbp+var_20]
0x1800ded71  jmp     loc_1800DF049
0x1800ded76  mov     eax, cs:CallbackContext
0x1800ded7c  cmp     eax, 2
0x1800ded7f  jbe     short loc_1800DEDDB
0x1800ded81  lea     rax, aUnexpectedPpla; "Unexpected: pPlatformContext is NULL"
0x1800ded88  mov     [rbp+arg_18], r15
0x1800ded8c  mov     [rbp+var_28], rax
0x1800ded90  lea     rdx, byte_1801BCFE3
0x1800ded97  lea     rax, [rbp+arg_18]
0x1800ded9b  mov     [rbp+arg_8], 1B9h
0x1800deda2  mov     [rsp+80h+var_40], rax
0x1800deda7  lea     rax, [rbp+arg_8]
0x1800dedab  mov     [rsp+80h+var_48], rax
0x1800dedb0  lea     rax, [rbp+var_20]
0x1800dedb4  mov     [rsp+80h+var_50], rax
0x1800dedb9  lea     rax, [rbp+arg_10]
0x1800dedbd  mov     [rsp+80h+var_58], rax
0x1800dedc2  lea     rax, [rbp+var_28]
0x1800dedc6  mov     [rsp+80h+var_60], rax
0x1800dedcb  mov     [rbp+var_20], r12
0x1800dedcf  mov     dword ptr [rbp+arg_10], 8000FFFFh
0x1800dedd6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800deddb  lea     rsi, [rdi+5B8h]
0x1800dede2  lea     rcx, [rdi+38h]; this
0x1800dede6  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x1800dedeb  test    eax, eax
0x1800deded  jnz     short loc_1800DEE1D
0x1800dedef  mov     eax, cs:CallbackContext
0x1800dedf5  mov     ebx, 8007000Eh
0x1800dedfa  cmp     eax, 2
0x1800dedfd  jbe     loc_1800DF05A
0x1800dee03  lea     rax, aMQueueInitiali; "m_Queue.Initialize"
0x1800dee0a  mov     [rbp+arg_8], 1BDh
0x1800dee11  lea     rdx, byte_1801BCF43
0x1800dee18  jmp     loc_1800DF005
0x1800dee1d  xor     r9d, r9d; lpName
0x1800dee20  xor     edx, edx; lInitialCount
0x1800dee22  xor     ecx, ecx; lpSemaphoreAttributes
0x1800dee24  mov     r8d, 7FFFFFFFh; lMaximumCount
0x1800dee2a  call    cs:__imp_CreateSemaphoreW
0x1800dee30  mov     [rdi+80h], rax
0x1800dee37  test    rax, rax
0x1800dee3a  jnz     short loc_1800DEEBB
0x1800dee3c  call    cs:__imp_GetLastError
0x1800dee42  mov     ebx, eax
0x1800dee44  test    eax, eax
0x1800dee46  jle     short loc_1800DEE51
0x1800dee48  movzx   ebx, ax
0x1800dee4b  or      ebx, 80070000h
0x1800dee51  mov     eax, cs:CallbackContext
0x1800dee57  cmp     eax, 2
0x1800dee5a  jbe     loc_1800DF05A
0x1800dee60  mov     [rbp+arg_8], 1CAh
0x1800dee67  lea     rax, aFailedCreatese; "Failed CreateSem"
0x1800dee6e  lea     rdx, byte_1801BCEB3
0x1800dee75  mov     [rbp+var_28], rax
0x1800dee79  lea     rax, [rbp+arg_18]
0x1800dee7d  mov     [rsp+80h+var_40], rax
0x1800dee82  lea     rax, [rbp+arg_8]
0x1800dee86  mov     [rsp+80h+var_48], rax
0x1800dee8b  lea     rax, [rbp+var_20]
0x1800dee8f  mov     [rsp+80h+var_50], rax
0x1800dee94  lea     rax, [rbp+arg_10]
0x1800dee98  mov     [rsp+80h+var_58], rax
0x1800dee9d  lea     rax, [rbp+var_28]
0x1800deea1  mov     [rsp+80h+var_60], rax
0x1800deea6  mov     dword ptr [rbp+arg_10], ebx
0x1800deea9  mov     [rbp+var_20], r12
0x1800deead  mov     [rbp+arg_18], r15
0x1800deeb1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800deeb6  jmp     loc_1800DF05A
0x1800deebb  xor     r9d, r9d; lpName
0x1800deebe  xor     r8d, r8d; bInitialState
0x1800deec1  xor     ecx, ecx; lpEventAttributes
0x1800deec3  lea     edx, [r9+1]; bManualReset
0x1800deec7  call    cs:__imp_CreateEventW
0x1800deecd  mov     [rdi+88h], rax
0x1800deed4  test    rax, rax
0x1800deed7  jnz     short loc_1800DEF17
0x1800deed9  call    cs:__imp_GetLastError
0x1800deedf  mov     ebx, eax
0x1800deee1  test    eax, eax
0x1800deee3  jle     short loc_1800DEEEE
0x1800deee5  movzx   ebx, ax
0x1800deee8  or      ebx, 80070000h
0x1800deeee  mov     eax, cs:CallbackContext
0x1800deef4  cmp     eax, 2
0x1800deef7  jbe     loc_1800DF05A
0x1800deefd  mov     [rbp+arg_8], 1D5h
0x1800def04  lea     rax, aFailedCreateev; "Failed CreateEvent"
0x1800def0b  lea     rdx, byte_1801BCEFB
0x1800def12  jmp     loc_1800DEE75
0x1800def17  lea     rcx, [rbp+pvarg]; pvarg
0x1800def1b  call    cs:__imp_VariantInit
0x1800def21  mov     rcx, [rsi]
0x1800def24  lea     r8, [rbp+pvarg]
0x1800def28  lea     rdx, String2; "EnableWddmIdd"
0x1800def2f  mov     rax, [rcx]
0x1800def32  mov     rax, [rax+18h]
0x1800def36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800def3b  test    eax, eax
0x1800def3d  js      short loc_1800DEF8C
0x1800def3f  xor     eax, eax
0x1800def41  cmp     word ptr [rbp+pvarg+8], 0FFFFh
0x1800def46  setz    al
0x1800def49  mov     [rdi+5C4h], eax
0x1800def4f  mov     eax, cs:CallbackContext
0x1800def55  cmp     eax, 4
0x1800def58  jbe     short loc_1800DEF8C
0x1800def5a  mov     eax, [rdi+5C4h]
0x1800def60  lea     rdx, byte_1801BCE89
0x1800def67  mov     [rbp+arg_8], eax
0x1800def6a  lea     rax, aWddmIddMode0Of; "WDDM IDD mode (0=Off, 1=On)"
0x1800def71  mov     [rbp+arg_10], rax
0x1800def75  lea     rax, [rbp+arg_8]
0x1800def79  mov     [rsp+80h+var_58], rax
0x1800def7e  lea     rax, [rbp+arg_10]
0x1800def82  mov     [rsp+80h+var_60], rax
0x1800def87  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800def8c  lea     rcx, [rbp+pvarg]; pvarg
0x1800def90  call    cs:__imp_VariantClear
0x1800def96  cmp     dword ptr [rdi+5C4h], 0
0x1800def9d  jz      short loc_1800DEFD7
0x1800def9f  lea     rdx, [rdi+5C8h]; struct _SECURITY_ATTRIBUTES *
0x1800defa6  call    ?InitializeIddSecurityAttr@Rdp8Scheduler@@AEAAJPEAU_SECURITY_ATTRIBUTES@@@Z; Rdp8Scheduler::InitializeIddSecurityAttr(_SECURITY_ATTRIBUTES *)
0x1800defab  mov     ebx, eax
0x1800defad  test    eax, eax
0x1800defaf  jns     short loc_1800DEFD7
0x1800defb1  mov     eax, cs:CallbackContext
0x1800defb7  cmp     eax, 2
0x1800defba  jbe     loc_1800DF05A
0x1800defc0  lea     rax, aFailedToInitia_38; "Failed to initialize Idd security attri"...
0x1800defc7  mov     [rbp+arg_8], 1EAh
0x1800defce  lea     rdx, byte_1801BCDE9
0x1800defd5  jmp     short loc_1800DF005
0x1800defd7  mov     rcx, rdi; this
0x1800defda  call    ?CreateNamedEvent@Rdp8Scheduler@@AEAAJXZ; Rdp8Scheduler::CreateNamedEvent(void)
0x1800defdf  mov     ebx, eax
0x1800defe1  test    eax, eax
0x1800defe3  jns     short loc_1800DF05A
0x1800defe5  mov     eax, cs:CallbackContext
0x1800defeb  cmp     eax, 2
0x1800defee  jbe     short loc_1800DF05A
0x1800deff0  lea     rax, aCreatenamedeve; "CreateNamedEvent"
0x1800deff7  mov     [rbp+arg_8], 1EEh
0x1800deffe  lea     rdx, byte_1801BCE39
0x1800df005  mov     [rbp+arg_18], rax
0x1800df009  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800df010  mov     [rbp+var_30], rax
0x1800df014  lea     rax, [rbp+arg_18]
0x1800df018  mov     [rsp+80h+var_38], rax
0x1800df01d  lea     rax, [rbp+var_20]
0x1800df021  mov     [rsp+80h+var_40], rax
0x1800df026  lea     rax, [rbp+arg_8]
0x1800df02a  mov     [rsp+80h+var_48], rax
0x1800df02f  lea     rax, [rbp+var_28]
0x1800df033  mov     [rsp+80h+var_50], rax
0x1800df038  lea     rax, [rbp+arg_10]
0x1800df03c  mov     [rsp+80h+var_58], rax
0x1800df041  lea     rax, [rbp+var_30]
0x1800df045  mov     [rbp+var_20], r15
0x1800df049  mov     [rsp+80h+var_60], rax
0x1800df04e  mov     [rbp+var_28], r12
0x1800df052  mov     dword ptr [rbp+arg_10], ebx
0x1800df055  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800df05a  mov     eax, ebx
0x1800df05c  mov     rbx, [rsp+80h+arg_0]
0x1800df064  add     rsp, 80h
0x1800df06b  pop     r15
0x1800df06d  pop     r12
0x1800df06f  pop     rdi
0x1800df070  pop     rsi
0x1800df071  pop     rbp
0x1800df072  retn
```
