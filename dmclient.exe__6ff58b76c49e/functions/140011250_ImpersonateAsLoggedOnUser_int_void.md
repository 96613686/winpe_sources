# ImpersonateAsLoggedOnUser(int,void * *)

- ea: `0x140011250`
- end: `0x140011504`
- name: `?ImpersonateAsLoggedOnUser@@YAJHPEAPEAX@Z`
- size: `692`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14000c47c`

## callees

- `0x140001414`
- `0x1400018cc`
- `0x140001b9c`
- `0x140011250`
- `0x14001150c`
- `0x140011928`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011299`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400112b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400114b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011299`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400112b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400114b9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14001128b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14001128b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140011278`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140011278`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1400112fc`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1400112fc`

## string_xrefs

- `0x1400112d1`: `Thread has no token attached. Proceed with impersonation.`
- `0x1400113c4`: `Returned from ImpersonateLoggedOnUserUsingWTSAPI`
- `0x14001139f`: `Returned from ImpersonateLoggedOnUserUsingUMgr`
- `0x1400114d5`: `OpenThreadToken failed.`
- `0x140011437`: `ImpersonateAsLoggedOnUser`
- `0x140011451`: `onecore\base\diagnosis\feedback\siuf\libs\impersonate\impersonate.cpp`
- `0x140011463`: `Failed to impersonate.`

## pseudocode

```c
__int64 __fastcall ImpersonateAsLoggedOnUser(__int64 a1, void **a2)
{
  unsigned int v3; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rcx
  const char *v13; // rax
  __int64 *v14; // rdx
  signed int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  void *TokenHandle; // [rsp+50h] [rbp-30h] BYREF
  __int64 v21; // [rsp+58h] [rbp-28h] BYREF
  const char *v22; // [rsp+60h] [rbp-20h] BYREF
  const char *v23; // [rsp+68h] [rbp-18h] BYREF
  const char *v24; // [rsp+70h] [rbp-10h] BYREF
  int v25; // [rsp+A0h] [rbp+20h] BYREF
  int v26; // [rsp+B0h] [rbp+30h] BYREF
  const char *v27; // [rsp+B8h] [rbp+38h] BYREF

  TokenHandle = (void *)-1LL;
  v3 = 1;
  v25 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) && GetLastError() == 1008 )
  {
    if ( (unsigned int)dword_140027000 > 5 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v26 = LastError;
      v27 = "Thread has no token attached. Proceed with impersonation.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)&dword_140022554,
        v7,
        v8,
        (const unsigned __int16 **)&v27,
        (__int64)&v26);
    }
    RtlGetDeviceFamilyInfoEnum(0, &v25, 0);
    switch ( v25 )
    {
      case 3:
        goto LABEL_18;
      case 4:
      case 5:
        return v3;
      case 6:
LABEL_18:
        v3 = ImpersonateLoggedOnUserUsingWTSAPI(a2);
        if ( (unsigned int)dword_140027000 <= 5 )
          goto LABEL_21;
        v13 = "Returned from ImpersonateLoggedOnUserUsingWTSAPI";
        v14 = qword_140022470;
        break;
      case 10:
      case 14:
      case 16:
        v3 = ImpersonateLoggedOnUserUsingUMgr(a2);
        if ( (unsigned int)dword_140027000 <= 5 )
        {
LABEL_21:
          if ( (v3 & 0x80000000) == 0 )
            return v3;
          goto LABEL_22;
        }
        v13 = "Returned from ImpersonateLoggedOnUserUsingUMgr";
        v14 = (__int64 *)byte_140022179;
        break;
      default:
        v3 = -2147024846;
        if ( (unsigned int)dword_140027000 > 5 )
        {
          LODWORD(v27) = v25;
          v21 = (__int64)"Device family not supported";
          v26 = -2147024846;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v9,
            (__int64)qword_1400225D8,
            v10,
            v11,
            (const unsigned __int16 **)&v21,
            (__int64)&v27,
            (__int64)&v26);
        }
LABEL_22:
        if ( (unsigned int)dword_140027000 > 2
          && (qword_140027010 & 0x400000000000LL) != 0
          && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
        {
          v21 = 0x1000000;
          v22 = "ImpersonateAsLoggedOnUser";
          v26 = 628;
          v23 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\impersonate\\impersonate.cpp";
          v24 = "Failed to impersonate.";
          LODWORD(v27) = v3;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            qword_140027018,
            (__int64)word_14002257A,
            v10,
            v11,
            (const unsigned __int16 **)&v24,
            (__int64)&v27,
            (const unsigned __int16 **)&v23,
            (const unsigned __int16 **)&v22,
            (__int64)&v26,
            (__int64)&v21);
        }
        return v3;
    }
    v27 = v13;
    v26 = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v12,
      (__int64)v14,
      v10,
      v11,
      (const unsigned __int16 **)&v27,
      (__int64)&v26);
    goto LABEL_21;
  }
  if ( (unsigned int)dword_140027000 > 5 )
  {
    v15 = GetLastError();
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    v26 = v15;
    v27 = "OpenThreadToken failed.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v16,
      (__int64)word_1400223B2,
      v17,
      v18,
      (const unsigned __int16 **)&v27,
      (__int64)&v26);
  }
  return v3;
}

```

## disassembly

```asm
0x140011250  mov     [rsp-18h+arg_0], ecx
0x140011254  push    rbp
0x140011255  push    rbx
0x140011256  push    rdi
0x140011257  mov     rbp, rsp
0x14001125a  sub     rsp, 80h
0x140011261  mov     rdi, rdx
0x140011264  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x14001126c  mov     ebx, 1
0x140011271  mov     [rbp+arg_0], 0
0x140011278  call    cs:__imp_GetCurrentThread
0x14001127e  lea     r9, [rbp+TokenHandle]; TokenHandle
0x140011282  xor     r8d, r8d; OpenAsSelf
0x140011285  mov     rcx, rax; ThreadHandle
0x140011288  lea     edx, [rbx+7]; DesiredAccess
0x14001128b  call    cs:__imp_OpenThreadToken
0x140011291  test    eax, eax
0x140011293  jnz     loc_1400114AE
0x140011299  call    cs:__imp_GetLastError
0x14001129f  cmp     eax, 3F0h
0x1400112a4  jnz     loc_1400114AE
0x1400112aa  mov     eax, cs:dword_140027000
0x1400112b0  cmp     eax, 5
0x1400112b3  jbe     short loc_1400112F3
0x1400112b5  call    cs:__imp_GetLastError
0x1400112bb  test    eax, eax
0x1400112bd  jle     short loc_1400112C7
0x1400112bf  movzx   eax, ax
0x1400112c2  or      eax, 80070000h
0x1400112c7  mov     [rbp+arg_10], eax
0x1400112ca  lea     rdx, dword_140022554
0x1400112d1  lea     rax, aThreadHasNoTok; "Thread has no token attached. Proceed w"...
0x1400112d8  mov     [rbp+arg_18], rax
0x1400112dc  lea     rax, [rbp+arg_10]
0x1400112e0  mov     [rsp+80h+var_58], rax
0x1400112e5  lea     rax, [rbp+arg_18]
0x1400112e9  mov     [rsp+80h+var_60], rax
0x1400112ee  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400112f3  xor     r8d, r8d
0x1400112f6  lea     rdx, [rbp+arg_0]
0x1400112fa  xor     ecx, ecx
0x1400112fc  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x140011302  mov     eax, [rbp+arg_0]
0x140011305  sub     eax, 3
0x140011308  jz      loc_1400113AF
0x14001130e  sub     eax, ebx
0x140011310  jz      loc_1400114F7
0x140011316  sub     eax, ebx
0x140011318  jz      loc_1400114F7
0x14001131e  sub     eax, ebx
0x140011320  jz      loc_1400113AF
0x140011326  sub     eax, 4
0x140011329  jz      short loc_14001138A
0x14001132b  sub     eax, 4
0x14001132e  jz      short loc_14001138A
0x140011330  cmp     eax, 2
0x140011333  jz      short loc_14001138A
0x140011335  mov     eax, cs:dword_140027000
0x14001133b  mov     ebx, 80070032h
0x140011340  cmp     eax, 5
0x140011343  jbe     loc_1400113F8
0x140011349  mov     eax, [rbp+arg_0]
0x14001134c  lea     rdx, qword_1400225D8
0x140011353  mov     dword ptr [rbp+arg_18], eax
0x140011356  lea     rax, aDeviceFamilyNo; "Device family not supported"
0x14001135d  mov     [rbp+var_28], rax
0x140011361  lea     rax, [rbp+arg_10]
0x140011365  mov     [rsp+80h+var_50], rax
0x14001136a  lea     rax, [rbp+arg_18]
0x14001136e  mov     [rsp+80h+var_58], rax
0x140011373  lea     rax, [rbp+var_28]
0x140011377  mov     [rsp+80h+var_60], rax
0x14001137c  mov     [rbp+arg_10], 80070032h
0x140011383  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140011388  jmp     short loc_1400113F8
0x14001138a  mov     rcx, rdi
0x14001138d  call    ImpersonateLoggedOnUserUsingUMgr
0x140011392  mov     ebx, eax
0x140011394  mov     eax, cs:dword_140027000
0x14001139a  cmp     eax, 5
0x14001139d  jbe     short loc_1400113F0
0x14001139f  lea     rax, aReturnedFromIm; "Returned from ImpersonateLoggedOnUserUs"...
0x1400113a6  lea     rdx, byte_140022179
0x1400113ad  jmp     short loc_1400113D2
0x1400113af  mov     rcx, rdi; phToken
0x1400113b2  call    ?ImpersonateLoggedOnUserUsingWTSAPI@@YAJPEAPEAX@Z; ImpersonateLoggedOnUserUsingWTSAPI(void * *)
0x1400113b7  mov     ebx, eax
0x1400113b9  mov     eax, cs:dword_140027000
0x1400113bf  cmp     eax, 5
0x1400113c2  jbe     short loc_1400113F0
0x1400113c4  lea     rax, aReturnedFromIm_0; "Returned from ImpersonateLoggedOnUserUs"...
0x1400113cb  lea     rdx, qword_140022470
0x1400113d2  mov     [rbp+arg_18], rax
0x1400113d6  lea     rax, [rbp+arg_10]
0x1400113da  mov     [rsp+80h+var_58], rax
0x1400113df  lea     rax, [rbp+arg_18]
0x1400113e3  mov     [rsp+80h+var_60], rax
0x1400113e8  mov     [rbp+arg_10], ebx
0x1400113eb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400113f0  test    ebx, ebx
0x1400113f2  jns     loc_1400114F7
0x1400113f8  mov     eax, cs:dword_140027000
0x1400113fe  cmp     eax, 2
0x140011401  jbe     loc_1400114F7
0x140011407  mov     rcx, cs:qword_140027018
0x14001140e  mov     rdx, 400000000000h
0x140011418  mov     rax, cs:qword_140027010
0x14001141f  test    rdx, rax
0x140011422  jz      loc_1400114F7
0x140011428  mov     rax, rcx
0x14001142b  and     rax, rdx
0x14001142e  cmp     rax, rcx
0x140011431  jnz     loc_1400114F7
0x140011437  lea     rax, aImpersonateasl; "ImpersonateAsLoggedOnUser"
0x14001143e  mov     [rbp+var_28], 1000000h
0x140011446  mov     [rbp+var_20], rax
0x14001144a  lea     rdx, word_14002257A
0x140011451  lea     rax, aOnecoreBaseDia_1; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140011458  mov     [rbp+arg_10], 274h
0x14001145f  mov     [rbp+var_18], rax
0x140011463  lea     rax, aFailedToImpers; "Failed to impersonate."
0x14001146a  mov     [rbp+var_10], rax
0x14001146e  lea     rax, [rbp+var_28]
0x140011472  mov     [rsp+80h+var_38], rax
0x140011477  lea     rax, [rbp+arg_10]
0x14001147b  mov     [rsp+80h+var_40], rax
0x140011480  lea     rax, [rbp+var_20]
0x140011484  mov     [rsp+80h+var_48], rax
0x140011489  lea     rax, [rbp+var_18]
0x14001148d  mov     [rsp+80h+var_50], rax
0x140011492  lea     rax, [rbp+arg_18]
0x140011496  mov     [rsp+80h+var_58], rax
0x14001149b  lea     rax, [rbp+var_10]
0x14001149f  mov     [rsp+80h+var_60], rax
0x1400114a4  mov     dword ptr [rbp+arg_18], ebx
0x1400114a7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400114ac  jmp     short loc_1400114F7
0x1400114ae  mov     eax, cs:dword_140027000
0x1400114b4  cmp     eax, 5
0x1400114b7  jbe     short loc_1400114F7
0x1400114b9  call    cs:__imp_GetLastError
0x1400114bf  test    eax, eax
0x1400114c1  jle     short loc_1400114CB
0x1400114c3  movzx   eax, ax
0x1400114c6  or      eax, 80070000h
0x1400114cb  mov     [rbp+arg_10], eax
0x1400114ce  lea     rdx, word_1400223B2
0x1400114d5  lea     rax, aOpenthreadtoke; "OpenThreadToken failed."
0x1400114dc  mov     [rbp+arg_18], rax
0x1400114e0  lea     rax, [rbp+arg_10]
0x1400114e4  mov     [rsp+80h+var_58], rax
0x1400114e9  lea     rax, [rbp+arg_18]
0x1400114ed  mov     [rsp+80h+var_60], rax
0x1400114f2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400114f7  mov     eax, ebx
0x1400114f9  add     rsp, 80h
0x140011500  pop     rdi
0x140011501  pop     rbx
0x140011502  pop     rbp
0x140011503  retn
```
