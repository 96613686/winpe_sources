# CRDPENCCONSecurityFilterStream::InternalGetElevatedIdentificationUserToken(void * *,int)

- ea: `0x1800eebbc`
- end: `0x1800eedb3`
- name: `?InternalGetElevatedIdentificationUserToken@CRDPENCCONSecurityFilterStream@@AEAAJPEAPEAXH@Z`
- size: `503`
- prototype: `int(CRDPENCCONSecurityFilterStream *__hidden this, void **, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800ec510`
- `0x1800edf60`

## callees

- `0x180001aa0`
- `0x1800888d8`
- `0x1800eebbc`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eec99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eec99`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800eebdd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800eebdd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800eed9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800eed9b`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800eec8f`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800eec8f`

## string_xrefs

- `0x1800eecc5`: `DuplicateToken failed`
- `0x1800eec24`: `InternalGetElevatedIdentificationUserToken`
- `0x1800eed31`: `InternalGetElevatedIdentificationUserToken`
- `0x1800eed18`: `m_spSecFilter->GetUserToken failed.`

## pseudocode

```c
__int64 __fastcall CRDPENCCONSecurityFilterStream::InternalGetElevatedIdentificationUserToken(
        RTL_SRWLOCK *this,
        void **a2,
        int a3,
        int a4)
{
  signed int v7; // ebx
  __int16 *v8; // rdx
  const char **v9; // rax
  PVOID Ptr; // rcx
  signed int LastError; // eax
  const char *v12; // rax
  unsigned int v13; // eax
  const char **v15; // [rsp+40h] [rbp-30h]
  const char *v16; // [rsp+50h] [rbp-20h] BYREF
  const char *v17; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v18[2]; // [rsp+60h] [rbp-10h] BYREF
  signed int v19; // [rsp+90h] [rbp+20h] BYREF
  int v20; // [rsp+A0h] [rbp+30h] BYREF
  const char *v21; // [rsp+A8h] [rbp+38h] BYREF

  if ( a3 )
    AcquireSRWLockShared(this + 16);
  if ( ((LODWORD(this[42].Ptr) - 6) & 0xFFFFFFFD) != 0 )
  {
    v7 = -2147019873;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_19;
    v20 = 3418;
    v21 = "state check failed.";
    v8 = (__int16 *)byte_1801C049B;
    v16 = "InternalGetElevatedIdentificationUserToken";
    v17 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencsecfilter.cpp";
    v18[0] = "Error HResult failed";
    v15 = &v16;
    v9 = (const char **)v18;
    goto LABEL_18;
  }
  Ptr = this[60].Ptr;
  if ( Ptr )
  {
    if ( DuplicateToken(Ptr, SecurityIdentification, a2) )
    {
      v7 = 0;
      goto LABEL_19;
    }
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 && (unsigned int)CallbackContext > 2 )
    {
      v12 = "DuplicateToken failed";
      v20 = 3426;
      v8 = (__int16 *)&unk_1801C04F0;
LABEL_17:
      v21 = v12;
      v18[0] = "InternalGetElevatedIdentificationUserToken";
      v17 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencsecfilter.cpp";
      v16 = "Error HResult failed";
      v15 = (const char **)v18;
      v9 = &v16;
LABEL_18:
      v19 = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)this,
        (_DWORD)v8,
        a3,
        a4,
        (__int64)v9,
        (__int64)&v19,
        (__int64)&v17,
        (__int64)&v20,
        (__int64)v15,
        (__int64)&v21);
    }
  }
  else
  {
    v13 = (*(__int64 (__fastcall **)(PVOID, void **))(*(_QWORD *)this[55].Ptr + 160LL))(this[55].Ptr, a2);
    v7 = MapXResultToHR(v13);
    if ( v7 < 0 && (unsigned int)CallbackContext > 2 )
    {
      v12 = "m_spSecFilter->GetUserToken failed.";
      v20 = 3436;
      v8 = &word_1801C0446;
      goto LABEL_17;
    }
  }
LABEL_19:
  if ( a3 )
    ReleaseSRWLockShared(this + 16);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800eebbc  mov     [rsp-18h+arg_8], rbx
0x1800eebc1  push    rbp
0x1800eebc2  push    rsi
0x1800eebc3  push    rdi
0x1800eebc4  mov     rbp, rsp
0x1800eebc7  sub     rsp, 70h
0x1800eebcb  mov     esi, r8d
0x1800eebce  mov     rbx, rdx
0x1800eebd1  mov     rdi, rcx
0x1800eebd4  test    r8d, r8d
0x1800eebd7  jz      short loc_1800EEBE3
0x1800eebd9  sub     rcx, 0FFFFFFFFFFFFFF80h; SRWLock
0x1800eebdd  call    cs:__imp_AcquireSRWLockShared
0x1800eebe3  mov     eax, [rdi+150h]
0x1800eebe9  sub     eax, 6
0x1800eebec  test    eax, 0FFFFFFFDh
0x1800eebf1  jz      loc_1800EEC7B
0x1800eebf7  mov     eax, cs:CallbackContext
0x1800eebfd  mov     ebx, 8007139Fh
0x1800eec02  cmp     eax, 2
0x1800eec05  jbe     loc_1800EED90
0x1800eec0b  lea     rax, aStateCheckFail; "state check failed."
0x1800eec12  mov     [rbp+arg_10], 0D5Ah
0x1800eec19  mov     [rbp+arg_18], rax
0x1800eec1d  lea     rdx, byte_1801C049B
0x1800eec24  lea     rax, aInternalgetele; "InternalGetElevatedIdentificationUserTo"...
0x1800eec2b  mov     [rbp+var_20], rax
0x1800eec2f  lea     rax, aOnecoreTermsrv_70; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800eec36  mov     [rbp+var_18], rax
0x1800eec3a  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800eec41  mov     [rbp+var_10], rax
0x1800eec45  lea     rax, [rbp+arg_18]
0x1800eec49  mov     [rsp+70h+var_28], rax
0x1800eec4e  lea     rax, [rbp+var_20]
0x1800eec52  mov     [rsp+70h+var_30], rax
0x1800eec57  lea     rax, [rbp+arg_10]
0x1800eec5b  mov     [rsp+70h+var_38], rax
0x1800eec60  lea     rax, [rbp+var_18]
0x1800eec64  mov     [rsp+70h+var_40], rax
0x1800eec69  lea     rax, [rbp+arg_0]
0x1800eec6d  mov     [rsp+70h+var_48], rax
0x1800eec72  lea     rax, [rbp+var_10]
0x1800eec76  jmp     loc_1800EED83
0x1800eec7b  mov     rcx, [rdi+1E0h]; ExistingTokenHandle
0x1800eec82  test    rcx, rcx
0x1800eec85  jz      short loc_1800EECE3
0x1800eec87  mov     r8, rbx; DuplicateTokenHandle
0x1800eec8a  mov     edx, 1; ImpersonationLevel
0x1800eec8f  call    cs:__imp_DuplicateToken
0x1800eec95  test    eax, eax
0x1800eec97  jnz     short loc_1800EECDC
0x1800eec99  call    cs:__imp_GetLastError
0x1800eec9f  mov     ebx, eax
0x1800eeca1  test    eax, eax
0x1800eeca3  jle     short loc_1800EECAE
0x1800eeca5  movzx   ebx, ax
0x1800eeca8  or      ebx, 80070000h
0x1800eecae  test    ebx, ebx
0x1800eecb0  jns     loc_1800EED90
0x1800eecb6  mov     eax, cs:CallbackContext
0x1800eecbc  cmp     eax, 2
0x1800eecbf  jbe     loc_1800EED90
0x1800eecc5  lea     rax, aDuplicatetoken; "DuplicateToken failed"
0x1800eeccc  mov     [rbp+arg_10], 0D62h
0x1800eecd3  lea     rdx, unk_1801C04F0
0x1800eecda  jmp     short loc_1800EED2D
0x1800eecdc  xor     ebx, ebx
0x1800eecde  jmp     loc_1800EED90
0x1800eece3  mov     rcx, [rdi+1B8h]
0x1800eecea  mov     rdx, rbx
0x1800eeced  mov     rax, [rcx]
0x1800eecf0  mov     rax, [rax+0A0h]
0x1800eecf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eecfc  mov     ecx, eax
0x1800eecfe  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x1800eed03  mov     ebx, eax
0x1800eed05  test    eax, eax
0x1800eed07  jns     loc_1800EED90
0x1800eed0d  mov     eax, cs:CallbackContext
0x1800eed13  cmp     eax, 2
0x1800eed16  jbe     short loc_1800EED90
0x1800eed18  lea     rax, aMSpsecfilterGe_2; "m_spSecFilter->GetUserToken failed."
0x1800eed1f  mov     [rbp+arg_10], 0D6Ch
0x1800eed26  lea     rdx, word_1801C0446
0x1800eed2d  mov     [rbp+arg_18], rax
0x1800eed31  lea     rax, aInternalgetele; "InternalGetElevatedIdentificationUserTo"...
0x1800eed38  mov     [rbp+var_10], rax
0x1800eed3c  lea     rax, aOnecoreTermsrv_70; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800eed43  mov     [rbp+var_18], rax
0x1800eed47  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800eed4e  mov     [rbp+var_20], rax
0x1800eed52  lea     rax, [rbp+arg_18]
0x1800eed56  mov     [rsp+70h+var_28], rax
0x1800eed5b  lea     rax, [rbp+var_10]
0x1800eed5f  mov     [rsp+70h+var_30], rax
0x1800eed64  lea     rax, [rbp+arg_10]
0x1800eed68  mov     [rsp+70h+var_38], rax
0x1800eed6d  lea     rax, [rbp+var_18]
0x1800eed71  mov     [rsp+70h+var_40], rax
0x1800eed76  lea     rax, [rbp+arg_0]
0x1800eed7a  mov     [rsp+70h+var_48], rax
0x1800eed7f  lea     rax, [rbp+var_20]
0x1800eed83  mov     [rsp+70h+var_50], rax
0x1800eed88  mov     [rbp+arg_0], ebx
0x1800eed8b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800eed90  test    esi, esi
0x1800eed92  jz      short loc_1800EEDA1
0x1800eed94  lea     rcx, [rdi+80h]; SRWLock
0x1800eed9b  call    cs:__imp_ReleaseSRWLockShared
0x1800eeda1  mov     eax, ebx
0x1800eeda3  mov     rbx, [rsp+70h+arg_8]
0x1800eedab  add     rsp, 70h
0x1800eedaf  pop     rdi
0x1800eedb0  pop     rsi
0x1800eedb1  pop     rbp
0x1800eedb2  retn
```
