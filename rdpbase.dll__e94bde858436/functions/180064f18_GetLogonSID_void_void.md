# GetLogonSID(void *,void * *)

- ea: `0x180064f18`
- end: `0x180065297`
- name: `?GetLogonSID@@YAJPEAXPEAPEAX@Z`
- size: `895`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800648e4`

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x180064f18`
- `0x1800787d4`
- `0x180078820`
- `0x18007969c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800650ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006524f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800650ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006524f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180065245`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180065245`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064f4f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800650c0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064f4f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800650c0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800651e5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800651e5`

## string_xrefs

- `0x180065273`: `Failed to copy SID`
- `0x180064f8a`: `GetLogonSID`
- `0x180065032`: `GetLogonSID`
- `0x180065155`: `GetLogonSID`
- `0x18006501d`: `Failed to allocate token`
- `0x180064fb1`: `Fail to GetTokenInformation`
- `0x1800650ee`: `Fail to GetTokenInformation`
- `0x180065139`: `Logged on SID doesn't exist. Fatal!`
- `0x180065212`: `Failed to allocate SID`

## pseudocode

```c
__int64 __fastcall GetLogonSID(HANDLE TokenHandle, void **a2)
{
  void *v2; // rsi
  signed int LastError; // eax
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  unsigned int v9; // ebx
  _DWORD *v10; // rax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  _DWORD *v14; // rdi
  int v15; // r8d
  int v16; // r9d
  signed int v17; // eax
  unsigned int v18; // ecx
  const char *v19; // rax
  char *v20; // rdx
  __int64 v21; // rbx
  void *v23; // rax
  signed int v24; // eax
  const char *v25; // [rsp+50h] [rbp-20h] BYREF
  const char *v26; // [rsp+58h] [rbp-18h] BYREF
  const char *v27; // [rsp+60h] [rbp-10h] BYREF
  const char *v28; // [rsp+68h] [rbp-8h] BYREF
  DWORD TokenInformationLength; // [rsp+A8h] [rbp+38h] BYREF
  int v30; // [rsp+B0h] [rbp+40h] BYREF
  int v31; // [rsp+B8h] [rbp+48h] BYREF

  v2 = 0;
  TokenInformationLength = 0;
  *a2 = 0;
  if ( !GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError != 122 )
    {
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v30 = 930;
        v25 = "GetLogonSID";
        v31 = v9;
        v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
        v27 = "Fail to GetTokenInformation";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v6,
          (unsigned int)byte_1801C5989,
          v7,
          v8,
          (__int64)&v27,
          (__int64)&v31,
          (__int64)&v26,
          (__int64)&v30,
          (__int64)&v25);
      }
      goto LABEL_23;
    }
  }
  v10 = operator new(TokenInformationLength);
  v14 = v10;
  if ( v10 )
  {
    memset_0(v10, 0, TokenInformationLength);
    if ( GetTokenInformation(TokenHandle, TokenGroups, v14, TokenInformationLength, &TokenInformationLength) )
    {
      v18 = 0;
      if ( *v14 )
      {
        while ( 1 )
        {
          v21 = 2LL * v18;
          if ( (v14[4 * v18 + 4] & 0xC0000000) == 0xC0000000 )
            break;
          if ( ++v18 >= *v14 )
            goto LABEL_18;
        }
        TokenInformationLength = GetLengthSid(*(PSID *)&v14[4 * v18 + 2]);
        v23 = operator new(TokenInformationLength);
        v2 = v23;
        if ( !v23 )
        {
          v18 = (unsigned int)CallbackContext;
          v9 = -2147024882;
          if ( (unsigned int)CallbackContext <= 2 )
            goto LABEL_22;
          v31 = -2147024882;
          v19 = "Failed to allocate SID";
          v20 = byte_1801C5841;
          v30 = 964;
          goto LABEL_21;
        }
        memset_0(v23, 0, TokenInformationLength);
        if ( CopySid(TokenInformationLength, v2, *(PSID *)&v14[2 * v21 + 2]) )
        {
          *a2 = v2;
          v9 = 0;
          goto LABEL_22;
        }
        v24 = GetLastError();
        v9 = v24;
        if ( v24 > 0 )
          v9 = (unsigned __int16)v24 | 0x80070000;
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_22;
        v19 = "Failed to copy SID";
        v30 = 969;
        v20 = byte_1801C5893;
      }
      else
      {
LABEL_18:
        v9 = -2147418113;
        if ( (unsigned int)CallbackContext <= 2 )
        {
LABEL_22:
          operator delete(v14);
LABEL_23:
          if ( (v9 & 0x80000000) != 0 && v2 )
            operator delete(v2);
          return v9;
        }
        v19 = "Logged on SID doesn't exist. Fatal!";
        v30 = 975;
        v20 = byte_1801C579D;
      }
    }
    else
    {
      v17 = GetLastError();
      v9 = v17;
      if ( v17 > 0 )
        v9 = (unsigned __int16)v17 | 0x80070000;
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_22;
      v19 = "Fail to GetTokenInformation";
      v30 = 950;
      v20 = &byte_1801C5937;
    }
    v31 = v9;
LABEL_21:
    v28 = v19;
    v27 = "GetLogonSID";
    v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
    v25 = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v18,
      (_DWORD)v20,
      v15,
      v16,
      (__int64)&v25,
      (__int64)&v31,
      (__int64)&v26,
      (__int64)&v30,
      (__int64)&v27,
      (__int64)&v28);
    goto LABEL_22;
  }
  v9 = -2147024882;
  if ( (unsigned int)CallbackContext > 2 )
  {
    v31 = -2147024882;
    v27 = "Failed to allocate token";
    v30 = 936;
    v26 = "GetLogonSID";
    v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
    v28 = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v11,
      (unsigned int)byte_1801C58E5,
      v12,
      v13,
      (__int64)&v28,
      (__int64)&v31,
      (__int64)&v25,
      (__int64)&v30,
      (__int64)&v26,
      (__int64)&v27);
  }
  return v9;
}

```

## disassembly

```asm
0x180064f18  mov     [rsp-28h+arg_0], rbx
0x180064f1d  push    rbp
0x180064f1e  push    rsi
0x180064f1f  push    rdi
0x180064f20  push    r14
0x180064f22  push    r15
0x180064f24  mov     rbp, rsp
0x180064f27  sub     rsp, 70h
0x180064f2b  xor     esi, esi
0x180064f2d  mov     [rbp+TokenInformationLength], 0
0x180064f34  mov     r15, rdx
0x180064f37  mov     [rdx], rsi
0x180064f3a  lea     rax, [rbp+TokenInformationLength]
0x180064f3e  xor     r9d, r9d; TokenInformationLength
0x180064f41  xor     r8d, r8d; TokenInformation
0x180064f44  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180064f49  lea     edx, [rsi+2]; TokenInformationClass
0x180064f4c  mov     r14, rcx
0x180064f4f  call    cs:__imp_GetTokenInformation
0x180064f55  test    eax, eax
0x180064f57  jnz     loc_180064FF3
0x180064f5d  call    cs:__imp_GetLastError
0x180064f63  mov     ebx, eax
0x180064f65  cmp     eax, 7Ah ; 'z'
0x180064f68  jz      loc_180064FF3
0x180064f6e  test    eax, eax
0x180064f70  jle     short loc_180064F7B
0x180064f72  movzx   ebx, ax
0x180064f75  or      ebx, 80070000h
0x180064f7b  mov     eax, cs:CallbackContext
0x180064f81  cmp     eax, 2
0x180064f84  jbe     loc_1800651B9
0x180064f8a  lea     rax, aGetlogonsid; "GetLogonSID"
0x180064f91  mov     [rbp+arg_10], 3A2h
0x180064f98  mov     [rbp+var_20], rax
0x180064f9c  lea     rdx, byte_1801C5989
0x180064fa3  lea     rax, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180064faa  mov     [rbp+arg_18], ebx
0x180064fad  mov     [rbp+var_18], rax
0x180064fb1  lea     rax, aFailToGettoken; "Fail to GetTokenInformation"
0x180064fb8  mov     [rbp+var_10], rax
0x180064fbc  lea     rax, [rbp+var_20]
0x180064fc0  mov     [rsp+70h+var_30], rax
0x180064fc5  lea     rax, [rbp+arg_10]
0x180064fc9  mov     [rsp+70h+var_38], rax
0x180064fce  lea     rax, [rbp+var_18]
0x180064fd2  mov     [rsp+70h+var_40], rax
0x180064fd7  lea     rax, [rbp+arg_18]
0x180064fdb  mov     [rsp+70h+var_48], rax
0x180064fe0  lea     rax, [rbp+var_10]
0x180064fe4  mov     [rsp+70h+ReturnLength], rax
0x180064fe9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180064fee  jmp     loc_1800651B9
0x180064ff3  mov     ecx, [rbp+TokenInformationLength]; Size
0x180064ff6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180064ffb  mov     rdi, rax
0x180064ffe  test    rax, rax
0x180065001  jnz     loc_18006509A
0x180065007  mov     eax, cs:CallbackContext
0x18006500d  mov     edx, 8007000Eh
0x180065012  mov     ebx, edx
0x180065014  cmp     eax, 2
0x180065017  jbe     loc_1800651CA
0x18006501d  lea     rax, aFailedToAlloca_13; "Failed to allocate token"
0x180065024  mov     [rbp+arg_18], edx
0x180065027  mov     [rbp+var_10], rax
0x18006502b  lea     rdx, byte_1801C58E5
0x180065032  lea     rax, aGetlogonsid; "GetLogonSID"
0x180065039  mov     [rbp+arg_10], 3A8h
0x180065040  mov     [rbp+var_18], rax
0x180065044  lea     rax, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18006504b  mov     [rbp+var_20], rax
0x18006504f  lea     rax, aErrorCondition; "Error condition failed"
0x180065056  mov     [rbp+var_8], rax
0x18006505a  lea     rax, [rbp+var_10]
0x18006505e  mov     [rsp+70h+var_28], rax
0x180065063  lea     rax, [rbp+var_18]
0x180065067  mov     [rsp+70h+var_30], rax
0x18006506c  lea     rax, [rbp+arg_10]
0x180065070  mov     [rsp+70h+var_38], rax
0x180065075  lea     rax, [rbp+var_20]
0x180065079  mov     [rsp+70h+var_40], rax
0x18006507e  lea     rax, [rbp+arg_18]
0x180065082  mov     [rsp+70h+var_48], rax
0x180065087  lea     rax, [rbp+var_8]
0x18006508b  mov     [rsp+70h+ReturnLength], rax
0x180065090  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180065095  jmp     loc_1800651CA
0x18006509a  mov     r8d, [rbp+TokenInformationLength]; Size
0x18006509e  xor     edx, edx; Val
0x1800650a0  mov     rcx, rdi; void *
0x1800650a3  call    memset_0
0x1800650a8  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800650ac  lea     rax, [rbp+TokenInformationLength]
0x1800650b0  mov     r8, rdi; TokenInformation
0x1800650b3  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800650b8  mov     edx, 2; TokenInformationClass
0x1800650bd  mov     rcx, r14; TokenHandle
0x1800650c0  call    cs:__imp_GetTokenInformation
0x1800650c6  test    eax, eax
0x1800650c8  jnz     short loc_180065105
0x1800650ca  call    cs:__imp_GetLastError
0x1800650d0  mov     ebx, eax
0x1800650d2  test    eax, eax
0x1800650d4  jle     short loc_1800650DF
0x1800650d6  movzx   ebx, ax
0x1800650d9  or      ebx, 80070000h
0x1800650df  mov     eax, cs:CallbackContext
0x1800650e5  cmp     eax, 2
0x1800650e8  jbe     loc_1800651B1
0x1800650ee  lea     rax, aFailToGettoken; "Fail to GetTokenInformation"
0x1800650f5  mov     [rbp+arg_10], 3B6h
0x1800650fc  lea     rdx, byte_1801C5937
0x180065103  jmp     short loc_18006514E
0x180065105  xor     ecx, ecx
0x180065107  cmp     [rdi], ecx
0x180065109  jbe     short loc_180065129
0x18006510b  mov     edx, 0C0000000h
0x180065110  mov     ebx, ecx
0x180065112  add     rbx, rbx
0x180065115  mov     eax, [rdi+rbx*8+10h]
0x180065119  and     eax, edx
0x18006511b  cmp     eax, edx
0x18006511d  jz      loc_1800651E0
0x180065123  inc     ecx
0x180065125  cmp     ecx, [rdi]
0x180065127  jb      short loc_180065110
0x180065129  mov     eax, cs:CallbackContext
0x18006512f  mov     ebx, 8000FFFFh
0x180065134  cmp     eax, 2
0x180065137  jbe     short loc_1800651B1
0x180065139  lea     rax, aLoggedOnSidDoe; "Logged on SID doesn't exist. Fatal!"
0x180065140  mov     [rbp+arg_10], 3CFh
0x180065147  lea     rdx, byte_1801C579D
0x18006514e  mov     [rbp+arg_18], ebx
0x180065151  mov     [rbp+var_8], rax
0x180065155  lea     rax, aGetlogonsid; "GetLogonSID"
0x18006515c  mov     [rbp+var_10], rax
0x180065160  lea     rax, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180065167  mov     [rbp+var_18], rax
0x18006516b  lea     rax, aErrorCondition; "Error condition failed"
0x180065172  mov     [rbp+var_20], rax
0x180065176  lea     rax, [rbp+var_8]
0x18006517a  mov     [rsp+70h+var_28], rax
0x18006517f  lea     rax, [rbp+var_10]
0x180065183  mov     [rsp+70h+var_30], rax
0x180065188  lea     rax, [rbp+arg_10]
0x18006518c  mov     [rsp+70h+var_38], rax
0x180065191  lea     rax, [rbp+var_18]
0x180065195  mov     [rsp+70h+var_40], rax
0x18006519a  lea     rax, [rbp+arg_18]
0x18006519e  mov     [rsp+70h+var_48], rax
0x1800651a3  lea     rax, [rbp+var_20]
0x1800651a7  mov     [rsp+70h+ReturnLength], rax
0x1800651ac  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800651b1  mov     rcx, rdi; Block
0x1800651b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800651b9  test    ebx, ebx
0x1800651bb  jns     short loc_1800651CA
0x1800651bd  test    rsi, rsi
0x1800651c0  jz      short loc_1800651CA
0x1800651c2  mov     rcx, rsi; Block
0x1800651c5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800651ca  mov     eax, ebx
0x1800651cc  mov     rbx, [rsp+70h+arg_0]
0x1800651d4  add     rsp, 70h
0x1800651d8  pop     r15
0x1800651da  pop     r14
0x1800651dc  pop     rdi
0x1800651dd  pop     rsi
0x1800651de  pop     rbp
0x1800651df  retn
0x1800651e0  mov     rcx, [rdi+rbx*8+8]; pSid
0x1800651e5  call    cs:__imp_GetLengthSid
0x1800651eb  mov     ecx, eax; Size
0x1800651ed  mov     [rbp+TokenInformationLength], ecx
0x1800651f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800651f5  mov     rsi, rax
0x1800651f8  test    rax, rax
0x1800651fb  jnz     short loc_18006522C
0x1800651fd  mov     ecx, cs:CallbackContext
0x180065203  mov     edx, 8007000Eh
0x180065208  mov     ebx, edx
0x18006520a  cmp     ecx, 2
0x18006520d  jbe     short loc_1800651B1
0x18006520f  mov     [rbp+arg_18], edx
0x180065212  lea     rax, aFailedToAlloca_30; "Failed to allocate SID"
0x180065219  lea     rdx, byte_1801C5841
0x180065220  mov     [rbp+arg_10], 3C4h
0x180065227  jmp     loc_180065151
0x18006522c  mov     r8d, [rbp+TokenInformationLength]; Size
0x180065230  xor     edx, edx; Val
0x180065232  mov     rcx, rsi; void *
0x180065235  call    memset_0
0x18006523a  mov     r8, [rdi+rbx*8+8]; pSourceSid
0x18006523f  mov     rdx, rsi; pDestinationSid
0x180065242  mov     ecx, [rbp+TokenInformationLength]; nDestinationSidLength
0x180065245  call    cs:__imp_CopySid
0x18006524b  test    eax, eax
0x18006524d  jnz     short loc_18006528D
0x18006524f  call    cs:__imp_GetLastError
0x180065255  mov     ebx, eax
0x180065257  test    eax, eax
0x180065259  jle     short loc_180065264
0x18006525b  movzx   ebx, ax
0x18006525e  or      ebx, 80070000h
0x180065264  mov     eax, cs:CallbackContext
0x18006526a  cmp     eax, 2
0x18006526d  jbe     loc_1800651B1
0x180065273  lea     rax, aFailedToCopySi; "Failed to copy SID"
0x18006527a  mov     [rbp+arg_10], 3C9h
0x180065281  lea     rdx, byte_1801C5893
0x180065288  jmp     loc_18006514E
0x18006528d  mov     [r15], rsi
0x180065290  xor     ebx, ebx
0x180065292  jmp     loc_1800651B1
```
