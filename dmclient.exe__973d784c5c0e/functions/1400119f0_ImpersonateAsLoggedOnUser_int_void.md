# ImpersonateAsLoggedOnUser(int,void * *)

- ea: `0x1400119f0`
- end: `0x140011cc9`
- name: `?ImpersonateAsLoggedOnUser@@YAJHPEAPEAX@Z`
- size: `729`
- prototype: `int(int, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14000c928`

## callees

- `0x140001418`
- `0x1400018e4`
- `0x140001bb4`
- `0x1400119f0`
- `0x140011cd0`
- `0x140012120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011a67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011c77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011a67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011c77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140011a18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140011a18`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140011a31`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140011a31`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140011ab4`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140011ab4`

## string_xrefs

- `0x140011a89`: `Thread has no token attached. Proceed with impersonation.`
- `0x140011b82`: `Returned from ImpersonateLoggedOnUserUsingWTSAPI`
- `0x140011b5d`: `Returned from ImpersonateLoggedOnUserUsingUMgr`
- `0x140011c99`: `OpenThreadToken failed.`
- `0x140011bf5`: `ImpersonateAsLoggedOnUser`
- `0x140011c0f`: `onecore\base\diagnosis\feedback\siuf\libs\impersonate\impersonate.cpp`
- `0x140011c21`: `Failed to impersonate.`

## pseudocode

```c
__int64 __fastcall ImpersonateAsLoggedOnUser(__int64 a1, void **a2)
{
  unsigned int v3; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // ecx
  const char *v13; // rax
  __int64 *v14; // rdx
  signed int v15; // eax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
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
    if ( (unsigned int)dword_140028000 > 5 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v26 = LastError;
      v27 = "Thread has no token attached. Proceed with impersonation.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)&dword_14002355C,
        v7,
        v8,
        (__int64)&v27,
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
        if ( (unsigned int)dword_140028000 <= 5 )
          goto LABEL_21;
        v13 = "Returned from ImpersonateLoggedOnUserUsingWTSAPI";
        v14 = qword_140023478;
        break;
      case 10:
      case 14:
      case 16:
        v3 = ImpersonateLoggedOnUserUsingUMgr(a2);
        if ( (unsigned int)dword_140028000 <= 5 )
        {
LABEL_21:
          if ( (v3 & 0x80000000) == 0 )
            return v3;
          goto LABEL_22;
        }
        v13 = "Returned from ImpersonateLoggedOnUserUsingUMgr";
        v14 = (__int64 *)byte_140023181;
        break;
      default:
        v3 = -2147024846;
        if ( (unsigned int)dword_140028000 > 5 )
        {
          LODWORD(v27) = v25;
          v21 = (__int64)"Device family not supported";
          v26 = -2147024846;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v9,
            (unsigned int)qword_1400235E0,
            v10,
            v11,
            (__int64)&v21,
            (__int64)&v27,
            (__int64)&v26);
        }
LABEL_22:
        if ( (unsigned int)dword_140028000 > 2
          && (qword_140028010 & 0x400000000000LL) != 0
          && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
        {
          v21 = 0x1000000;
          v22 = "ImpersonateAsLoggedOnUser";
          v26 = 628;
          v23 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\impersonate\\impersonate.cpp";
          v24 = "Failed to impersonate.";
          LODWORD(v27) = v3;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            qword_140028018,
            (unsigned int)word_140023582,
            v10,
            v11,
            (__int64)&v24,
            (__int64)&v27,
            (__int64)&v23,
            (__int64)&v22,
            (__int64)&v26,
            (__int64)&v21);
        }
        return v3;
    }
    v27 = v13;
    v26 = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v12,
      (_DWORD)v14,
      v10,
      v11,
      (__int64)&v27,
      (__int64)&v26);
    goto LABEL_21;
  }
  if ( (unsigned int)dword_140028000 > 5 )
  {
    v15 = GetLastError();
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    v26 = v15;
    v27 = "OpenThreadToken failed.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v16,
      (unsigned int)word_1400233BA,
      v17,
      v18,
      (__int64)&v27,
      (__int64)&v26);
  }
  return v3;
}

```

## disassembly

```asm
0x1400119f0  mov     [rsp-18h+arg_0], ecx
0x1400119f4  push    rbp
0x1400119f5  push    rbx
0x1400119f6  push    rdi
0x1400119f7  mov     rbp, rsp
0x1400119fa  sub     rsp, 80h
0x140011a01  mov     rdi, rdx
0x140011a04  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x140011a0c  mov     ebx, 1
0x140011a11  mov     [rbp+arg_0], 0
0x140011a18  call    cs:__imp_GetCurrentThread
0x140011a1f  nop     dword ptr [rax+rax+00h]
0x140011a24  lea     r9, [rbp+TokenHandle]; TokenHandle
0x140011a28  xor     r8d, r8d; OpenAsSelf
0x140011a2b  mov     rcx, rax; ThreadHandle
0x140011a2e  lea     edx, [rbx+7]; DesiredAccess
0x140011a31  call    cs:__imp_OpenThreadToken
0x140011a38  nop     dword ptr [rax+rax+00h]
0x140011a3d  test    eax, eax
0x140011a3f  jnz     loc_140011C6C
0x140011a45  call    cs:__imp_GetLastError
0x140011a4c  nop     dword ptr [rax+rax+00h]
0x140011a51  cmp     eax, 3F0h
0x140011a56  jnz     loc_140011C6C
0x140011a5c  mov     eax, cs:dword_140028000
0x140011a62  cmp     eax, 5
0x140011a65  jbe     short loc_140011AAB
0x140011a67  call    cs:__imp_GetLastError
0x140011a6e  nop     dword ptr [rax+rax+00h]
0x140011a73  test    eax, eax
0x140011a75  jle     short loc_140011A7F
0x140011a77  movzx   eax, ax
0x140011a7a  or      eax, 80070000h
0x140011a7f  mov     [rbp+arg_10], eax
0x140011a82  lea     rdx, dword_14002355C
0x140011a89  lea     rax, aThreadHasNoTok; "Thread has no token attached. Proceed w"...
0x140011a90  mov     [rbp+arg_18], rax
0x140011a94  lea     rax, [rbp+arg_10]
0x140011a98  mov     [rsp+80h+var_58], rax
0x140011a9d  lea     rax, [rbp+arg_18]
0x140011aa1  mov     [rsp+80h+var_60], rax
0x140011aa6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140011aab  xor     r8d, r8d
0x140011aae  lea     rdx, [rbp+arg_0]
0x140011ab2  xor     ecx, ecx
0x140011ab4  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x140011abb  nop     dword ptr [rax+rax+00h]
0x140011ac0  mov     eax, [rbp+arg_0]
0x140011ac3  sub     eax, 3
0x140011ac6  jz      loc_140011B6D
0x140011acc  sub     eax, ebx
0x140011ace  jz      loc_140011CBB
0x140011ad4  sub     eax, ebx
0x140011ad6  jz      loc_140011CBB
0x140011adc  sub     eax, ebx
0x140011ade  jz      loc_140011B6D
0x140011ae4  sub     eax, 4
0x140011ae7  jz      short loc_140011B48
0x140011ae9  sub     eax, 4
0x140011aec  jz      short loc_140011B48
0x140011aee  cmp     eax, 2
0x140011af1  jz      short loc_140011B48
0x140011af3  mov     eax, cs:dword_140028000
0x140011af9  mov     ebx, 80070032h
0x140011afe  cmp     eax, 5
0x140011b01  jbe     loc_140011BB6
0x140011b07  mov     eax, [rbp+arg_0]
0x140011b0a  lea     rdx, qword_1400235E0
0x140011b11  mov     dword ptr [rbp+arg_18], eax
0x140011b14  lea     rax, aDeviceFamilyNo; "Device family not supported"
0x140011b1b  mov     [rbp+var_28], rax
0x140011b1f  lea     rax, [rbp+arg_10]
0x140011b23  mov     [rsp+80h+var_50], rax
0x140011b28  lea     rax, [rbp+arg_18]
0x140011b2c  mov     [rsp+80h+var_58], rax
0x140011b31  lea     rax, [rbp+var_28]
0x140011b35  mov     [rsp+80h+var_60], rax
0x140011b3a  mov     [rbp+arg_10], 80070032h
0x140011b41  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140011b46  jmp     short loc_140011BB6
0x140011b48  mov     rcx, rdi
0x140011b4b  call    ImpersonateLoggedOnUserUsingUMgr
0x140011b50  mov     ebx, eax
0x140011b52  mov     eax, cs:dword_140028000
0x140011b58  cmp     eax, 5
0x140011b5b  jbe     short loc_140011BAE
0x140011b5d  lea     rax, aReturnedFromIm; "Returned from ImpersonateLoggedOnUserUs"...
0x140011b64  lea     rdx, byte_140023181
0x140011b6b  jmp     short loc_140011B90
0x140011b6d  mov     rcx, rdi; phToken
0x140011b70  call    ?ImpersonateLoggedOnUserUsingWTSAPI@@YAJPEAPEAX@Z; ImpersonateLoggedOnUserUsingWTSAPI(void * *)
0x140011b75  mov     ebx, eax
0x140011b77  mov     eax, cs:dword_140028000
0x140011b7d  cmp     eax, 5
0x140011b80  jbe     short loc_140011BAE
0x140011b82  lea     rax, aReturnedFromIm_0; "Returned from ImpersonateLoggedOnUserUs"...
0x140011b89  lea     rdx, qword_140023478
0x140011b90  mov     [rbp+arg_18], rax
0x140011b94  lea     rax, [rbp+arg_10]
0x140011b98  mov     [rsp+80h+var_58], rax
0x140011b9d  lea     rax, [rbp+arg_18]
0x140011ba1  mov     [rsp+80h+var_60], rax
0x140011ba6  mov     [rbp+arg_10], ebx
0x140011ba9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140011bae  test    ebx, ebx
0x140011bb0  jns     loc_140011CBB
0x140011bb6  mov     eax, cs:dword_140028000
0x140011bbc  cmp     eax, 2
0x140011bbf  jbe     loc_140011CBB
0x140011bc5  mov     rcx, cs:qword_140028018
0x140011bcc  mov     rdx, 400000000000h
0x140011bd6  mov     rax, cs:qword_140028010
0x140011bdd  test    rdx, rax
0x140011be0  jz      loc_140011CBB
0x140011be6  mov     rax, rcx
0x140011be9  and     rax, rdx
0x140011bec  cmp     rax, rcx
0x140011bef  jnz     loc_140011CBB
0x140011bf5  lea     rax, aImpersonateasl; "ImpersonateAsLoggedOnUser"
0x140011bfc  mov     [rbp+var_28], 1000000h
0x140011c04  mov     [rbp+var_20], rax
0x140011c08  lea     rdx, word_140023582
0x140011c0f  lea     rax, aOnecoreBaseDia_1; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140011c16  mov     [rbp+arg_10], 274h
0x140011c1d  mov     [rbp+var_18], rax
0x140011c21  lea     rax, aFailedToImpers; "Failed to impersonate."
0x140011c28  mov     [rbp+var_10], rax
0x140011c2c  lea     rax, [rbp+var_28]
0x140011c30  mov     [rsp+80h+var_38], rax
0x140011c35  lea     rax, [rbp+arg_10]
0x140011c39  mov     [rsp+80h+var_40], rax
0x140011c3e  lea     rax, [rbp+var_20]
0x140011c42  mov     [rsp+80h+var_48], rax
0x140011c47  lea     rax, [rbp+var_18]
0x140011c4b  mov     [rsp+80h+var_50], rax
0x140011c50  lea     rax, [rbp+arg_18]
0x140011c54  mov     [rsp+80h+var_58], rax
0x140011c59  lea     rax, [rbp+var_10]
0x140011c5d  mov     [rsp+80h+var_60], rax
0x140011c62  mov     dword ptr [rbp+arg_18], ebx
0x140011c65  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140011c6a  jmp     short loc_140011CBB
0x140011c6c  mov     eax, cs:dword_140028000
0x140011c72  cmp     eax, 5
0x140011c75  jbe     short loc_140011CBB
0x140011c77  call    cs:__imp_GetLastError
0x140011c7e  nop     dword ptr [rax+rax+00h]
0x140011c83  test    eax, eax
0x140011c85  jle     short loc_140011C8F
0x140011c87  movzx   eax, ax
0x140011c8a  or      eax, 80070000h
0x140011c8f  mov     [rbp+arg_10], eax
0x140011c92  lea     rdx, word_1400233BA
0x140011c99  lea     rax, aOpenthreadtoke; "OpenThreadToken failed."
0x140011ca0  mov     [rbp+arg_18], rax
0x140011ca4  lea     rax, [rbp+arg_10]
0x140011ca8  mov     [rsp+80h+var_58], rax
0x140011cad  lea     rax, [rbp+arg_18]
0x140011cb1  mov     [rsp+80h+var_60], rax
0x140011cb6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140011cbb  mov     eax, ebx
0x140011cbd  add     rsp, 80h
0x140011cc4  pop     rdi
0x140011cc5  pop     rbx
0x140011cc6  pop     rbp
0x140011cc7  retn
```
