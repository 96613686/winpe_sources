# BuildNamedPipeAcl(void * *,unsigned __int64,_ACL * *)

- ea: `0x1800648e4`
- end: `0x180064e59`
- name: `?BuildNamedPipeAcl@@YAJPEAPEAX_KPEAPEAU_ACL@@@Z`
- size: `1397`
- prototype: `__int64 __fastcall(void **, unsigned __int64, struct _ACL **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180065920`

## callees

- `0x180001aa0`
- `0x1800648e4`
- `0x180064f18`
- `0x1800787d4`
- `0x180078820`
- `0x18007969c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800649c8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800649c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800649b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800649b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800649d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064c00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064ce4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800649d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064c00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064ce4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064e35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064e35`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180064bf2`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180064bf2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180064cb0`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180064cd6`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180064cb0`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180064cd6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180064b13`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180064b2c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180064b13`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180064b2c`

## string_xrefs

- `0x180064950`: `BuildNamedPipeAcl`
- `0x180064a13`: `BuildNamedPipeAcl`
- `0x180064aab`: `BuildNamedPipeAcl`
- `0x180064b83`: `BuildNamedPipeAcl`
- `0x180064c3d`: `BuildNamedPipeAcl`
- `0x180064d21`: `BuildNamedPipeAcl`
- `0x180064db1`: `BuildNamedPipeAcl`
- `0x180064937`: `ppAcl is NULL`
- `0x180064a92`: `Failed to get logged on SID`
- `0x1800649fa`: `OpenProcessToken failed.`
- `0x180064c24`: `Fail to InitializeAcl`
- `0x180064b6a`: `Failed to allocate ACL`
- `0x180064d08`: `Fail to AddAccessAllowedAce for current process SID`
- `0x180064d98`: `Fail to AddAccessAllowedAce for supplied SID`

## pseudocode

```c
__int64 __fastcall BuildNamedPipeAcl(void **a1, unsigned __int64 a2, struct _ACL **a3, int a4)
{
  signed int LogonSID; // ebx
  char *v8; // rdx
  PSID *v9; // rax
  HANDLE CurrentProcess; // rax
  signed int v11; // eax
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  struct _ACL *v15; // rdi
  char *v16; // rdx
  const char **v17; // rax
  DWORD v18; // ebx
  __int64 i; // rdi
  DWORD LengthSid; // eax
  struct _ACL *v21; // rax
  signed int v22; // eax
  __int64 v23; // rbx
  signed int v24; // eax
  signed int LastError; // eax
  const char **v27; // [rsp+30h] [rbp-50h]
  const char **v28; // [rsp+30h] [rbp-50h]
  const char **v29; // [rsp+40h] [rbp-40h]
  const char **v30; // [rsp+40h] [rbp-40h]
  PSID *p_pSid; // [rsp+48h] [rbp-38h]
  const char **v32; // [rsp+48h] [rbp-38h]
  PSID pSid; // [rsp+50h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-28h] BYREF
  const char *v35; // [rsp+60h] [rbp-20h] BYREF
  const char *v36; // [rsp+68h] [rbp-18h] BYREF
  const char *v37; // [rsp+70h] [rbp-10h] BYREF
  const char *v38; // [rsp+78h] [rbp-8h] BYREF
  int v39; // [rsp+C0h] [rbp+40h] BYREF
  signed int v40; // [rsp+C8h] [rbp+48h] BYREF

  TokenHandle = 0;
  pSid = 0;
  if ( !a3 )
  {
    LogonSID = -2147467261;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_42;
    v39 = 1047;
    pSid = "ppAcl is NULL";
    v8 = &byte_1801C57EF;
    v35 = "BuildNamedPipeAcl";
    v36 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
    v37 = "Error condition failed";
    p_pSid = &pSid;
    v29 = &v35;
    v27 = &v36;
    v9 = (PSID *)&v37;
    goto LABEL_4;
  }
  *a3 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xF01FFu, &TokenHandle) )
  {
    LogonSID = GetLogonSID(TokenHandle, &pSid);
    if ( LogonSID >= 0 )
    {
      v18 = GetLengthSid(pSid) + 16;
      if ( a1 )
      {
        for ( i = 0; (unsigned int)i < a2; v18 += LengthSid + 16 )
        {
          LengthSid = GetLengthSid(a1[i]);
          i = (unsigned int)(i + 1);
        }
      }
      v21 = (struct _ACL *)operator new(v18);
      v15 = v21;
      if ( v21 )
      {
        memset_0(v21, 0, v18);
        if ( InitializeAcl(v15, v18, 2u) )
        {
          v23 = 0;
          if ( a2 )
          {
            while ( AddAccessAllowedAce(v15, 2u, 0x1F01FFu, a1[v23]) )
            {
              v23 = (unsigned int)(v23 + 1);
              if ( (unsigned int)v23 >= a2 )
                goto LABEL_28;
            }
            LastError = GetLastError();
            LogonSID = LastError;
            if ( LastError > 0 )
              LogonSID = (unsigned __int16)LastError | 0x80070000;
            if ( (unsigned int)CallbackContext <= 2 )
              goto LABEL_38;
            v39 = 1095;
            v38 = "Fail to AddAccessAllowedAce for supplied SID";
            v16 = byte_1801C55B1;
            v37 = "BuildNamedPipeAcl";
            v36 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
            v35 = "Error condition failed";
            v32 = &v38;
            v30 = &v37;
            v28 = &v36;
            v17 = &v35;
          }
          else
          {
LABEL_28:
            if ( AddAccessAllowedAce(v15, 2u, 0x1F01FFu, pSid) )
            {
              *a3 = v15;
              v15 = 0;
              LogonSID = 0;
              goto LABEL_38;
            }
            v24 = GetLastError();
            LogonSID = v24;
            if ( v24 > 0 )
              LogonSID = (unsigned __int16)v24 | 0x80070000;
            if ( (unsigned int)CallbackContext <= 2 )
              goto LABEL_38;
            v39 = 1107;
            v38 = "Fail to AddAccessAllowedAce for current process SID";
            v16 = byte_1801C5603;
            v37 = "BuildNamedPipeAcl";
            v36 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
            v35 = "Error condition failed";
            v32 = &v38;
            v30 = &v37;
            v28 = &v36;
            v17 = &v35;
          }
        }
        else
        {
          v22 = GetLastError();
          LogonSID = v22;
          if ( v22 > 0 )
            LogonSID = (unsigned __int16)v22 | 0x80070000;
          if ( (unsigned int)CallbackContext <= 2 )
            goto LABEL_38;
          v39 = 1083;
          v38 = "Fail to InitializeAcl";
          v16 = byte_1801C5655;
          v37 = "BuildNamedPipeAcl";
          v36 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
          v35 = "Error condition failed";
          v32 = &v38;
          v30 = &v37;
          v28 = &v36;
          v17 = &v35;
        }
      }
      else
      {
        v14 = (int)CallbackContext;
        LogonSID = -2147024882;
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_38;
        v39 = 1078;
        v38 = "Failed to allocate ACL";
        v16 = &byte_1801C56A7;
        v37 = "BuildNamedPipeAcl";
        v36 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
        v35 = "Error condition failed";
        v32 = &v38;
        v30 = &v37;
        v28 = &v36;
        v17 = &v35;
      }
    }
    else
    {
      v14 = (int)CallbackContext;
      v15 = 0;
      if ( (unsigned int)CallbackContext <= 2 )
      {
LABEL_38:
        if ( pSid )
          operator delete(pSid);
        if ( v15 )
          operator delete(v15);
        goto LABEL_42;
      }
      v39 = 1060;
      v37 = "Failed to get logged on SID";
      v16 = byte_1801C574B;
      v36 = "BuildNamedPipeAcl";
      v35 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
      v38 = "Error HResult failed";
      v32 = &v37;
      v30 = &v36;
      v28 = &v35;
      v17 = &v38;
    }
    v40 = LogonSID;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v14,
      (_DWORD)v16,
      v12,
      v13,
      (__int64)v17,
      (__int64)&v40,
      (__int64)v28,
      (__int64)&v39,
      (__int64)v30,
      (__int64)v32);
    goto LABEL_38;
  }
  v11 = GetLastError();
  LogonSID = v11;
  if ( v11 > 0 )
    LogonSID = (unsigned __int16)v11 | 0x80070000;
  if ( (unsigned int)CallbackContext > 2 )
  {
    v39 = 1057;
    v37 = "OpenProcessToken failed.";
    v8 = byte_1801C56F9;
    v36 = "BuildNamedPipeAcl";
    v35 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
    pSid = "Error condition failed";
    p_pSid = (PSID *)&v37;
    v29 = &v36;
    v27 = &v35;
    v9 = &pSid;
LABEL_4:
    v40 = LogonSID;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)a1,
      (_DWORD)v8,
      (_DWORD)a3,
      a4,
      (__int64)v9,
      (__int64)&v40,
      (__int64)v27,
      (__int64)&v39,
      (__int64)v29,
      (__int64)p_pSid);
  }
LABEL_42:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)LogonSID;
}

```

## disassembly

```asm
0x1800648e4  mov     r11, rsp
0x1800648e7  mov     [r11+8], rbx
0x1800648eb  mov     [r11+10h], rsi
0x1800648ef  push    rbp
0x1800648f0  push    rdi
0x1800648f1  push    r12
0x1800648f3  push    r13
0x1800648f5  push    r14
0x1800648f7  mov     rbp, rsp
0x1800648fa  sub     rsp, 80h
0x180064901  mov     [rbp+TokenHandle], 0
0x180064909  mov     r14, r8
0x18006490c  mov     [rbp+pSid], 0
0x180064914  mov     rsi, rdx
0x180064917  mov     r12, rcx
0x18006491a  test    r8, r8
0x18006491d  jnz     loc_1800649AF
0x180064923  mov     eax, cs:CallbackContext
0x180064929  mov     ebx, 80004003h
0x18006492e  cmp     eax, 2
0x180064931  jbe     loc_180064E2C
0x180064937  lea     rax, aPpaclIsNull; "ppAcl is NULL"
0x18006493e  mov     [rbp+arg_10], 417h
0x180064945  mov     [rbp+pSid], rax
0x180064949  lea     rdx, byte_1801C57EF
0x180064950  lea     rax, aBuildnamedpipe; "BuildNamedPipeAcl"
0x180064957  mov     [rbp+var_20], rax
0x18006495b  lea     rax, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180064962  mov     [rbp+var_18], rax
0x180064966  lea     rax, aErrorCondition; "Error condition failed"
0x18006496d  mov     [rbp+var_10], rax
0x180064971  lea     rax, [rbp+pSid]
0x180064975  mov     [r11-60h], rax
0x180064979  lea     rax, [rbp+var_20]
0x18006497d  mov     [r11-68h], rax
0x180064981  lea     rax, [rbp+arg_10]
0x180064985  mov     [r11-70h], rax
0x180064989  lea     rax, [rbp+var_18]
0x18006498d  mov     [r11-78h], rax
0x180064991  lea     rax, [rbp+arg_18]
0x180064995  mov     [r11-80h], rax
0x180064999  lea     rax, [rbp+var_10]
0x18006499d  mov     [rsp+80h+var_60], rax
0x1800649a2  mov     [rbp+arg_18], ebx
0x1800649a5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800649aa  jmp     loc_180064E2C
0x1800649af  mov     qword ptr [r8], 0
0x1800649b6  call    cs:__imp_GetCurrentProcess
0x1800649bc  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800649c0  mov     edx, 0F01FFh; DesiredAccess
0x1800649c5  mov     rcx, rax; ProcessHandle
0x1800649c8  call    cs:__imp_OpenProcessToken
0x1800649ce  test    eax, eax
0x1800649d0  jnz     loc_180064A6A
0x1800649d6  call    cs:__imp_GetLastError
0x1800649dc  mov     ebx, eax
0x1800649de  test    eax, eax
0x1800649e0  jle     short loc_1800649EB
0x1800649e2  movzx   ebx, ax
0x1800649e5  or      ebx, 80070000h
0x1800649eb  mov     eax, cs:CallbackContext
0x1800649f1  cmp     eax, 2
0x1800649f4  jbe     loc_180064E2C
0x1800649fa  lea     rax, aOpenprocesstok; "OpenProcessToken failed."
0x180064a01  mov     [rbp+arg_10], 421h
0x180064a08  mov     [rbp+var_10], rax
0x180064a0c  lea     rdx, byte_1801C56F9
0x180064a13  lea     rax, aBuildnamedpipe; "BuildNamedPipeAcl"
0x180064a1a  mov     [rbp+var_18], rax
0x180064a1e  lea     rax, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180064a25  mov     [rbp+var_20], rax
0x180064a29  lea     rax, aErrorCondition; "Error condition failed"
0x180064a30  mov     [rbp+pSid], rax
0x180064a34  lea     rax, [rbp+var_10]
0x180064a38  mov     [rsp+80h+var_38], rax
0x180064a3d  lea     rax, [rbp+var_18]
0x180064a41  mov     [rsp+80h+var_40], rax
0x180064a46  lea     rax, [rbp+arg_10]
0x180064a4a  mov     [rsp+80h+var_48], rax
0x180064a4f  lea     rax, [rbp+var_20]
0x180064a53  mov     [rsp+80h+var_50], rax
0x180064a58  lea     rax, [rbp+arg_18]
0x180064a5c  mov     [rsp+80h+var_58], rax
0x180064a61  lea     rax, [rbp+pSid]
0x180064a65  jmp     loc_18006499D
0x180064a6a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180064a6e  lea     rdx, [rbp+pSid]; void **
0x180064a72  call    ?GetLogonSID@@YAJPEAXPEAPEAX@Z; GetLogonSID(void *,void * *)
0x180064a77  mov     ebx, eax
0x180064a79  test    eax, eax
0x180064a7b  jns     loc_180064B0F
0x180064a81  mov     ecx, cs:CallbackContext
0x180064a87  xor     edi, edi
0x180064a89  cmp     ecx, 2
0x180064a8c  jbe     loc_180064E0F
0x180064a92  lea     rax, aFailedToGetLog; "Failed to get logged on SID"
0x180064a99  mov     [rbp+arg_10], 424h
0x180064aa0  mov     [rbp+var_10], rax
0x180064aa4  lea     rdx, byte_1801C574B
0x180064aab  lea     rax, aBuildnamedpipe; "BuildNamedPipeAcl"
0x180064ab2  mov     [rbp+var_18], rax
0x180064ab6  lea     rax, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180064abd  mov     [rbp+var_20], rax
0x180064ac1  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180064ac8  mov     [rbp+var_8], rax
0x180064acc  lea     rax, [rbp+var_10]
0x180064ad0  mov     [rsp+80h+var_38], rax
0x180064ad5  lea     rax, [rbp+var_18]
0x180064ad9  mov     [rsp+80h+var_40], rax
0x180064ade  lea     rax, [rbp+arg_10]
0x180064ae2  mov     [rsp+80h+var_48], rax
0x180064ae7  lea     rax, [rbp+var_20]
0x180064aeb  mov     [rsp+80h+var_50], rax
0x180064af0  lea     rax, [rbp+arg_18]
0x180064af4  mov     [rsp+80h+var_58], rax
0x180064af9  lea     rax, [rbp+var_8]
0x180064afd  mov     [rbp+arg_18], ebx
0x180064b00  mov     [rsp+80h+var_60], rax
0x180064b05  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180064b0a  jmp     loc_180064E0F
0x180064b0f  mov     rcx, [rbp+pSid]; pSid
0x180064b13  call    cs:__imp_GetLengthSid
0x180064b19  lea     ebx, [rax+10h]
0x180064b1c  test    r12, r12
0x180064b1f  jz      short loc_180064B40
0x180064b21  xor     edi, edi
0x180064b23  test    rsi, rsi
0x180064b26  jz      short loc_180064B40
0x180064b28  mov     rcx, [r12+rdi*8]; pSid
0x180064b2c  call    cs:__imp_GetLengthSid
0x180064b32  add     eax, 10h
0x180064b35  inc     edi
0x180064b37  add     ebx, eax
0x180064b39  mov     eax, edi
0x180064b3b  cmp     rax, rsi
0x180064b3e  jb      short loc_180064B28
0x180064b40  mov     ecx, ebx; Size
0x180064b42  mov     r13d, ebx
0x180064b45  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180064b4a  mov     rdi, rax
0x180064b4d  test    rax, rax
0x180064b50  jnz     loc_180064BDA
0x180064b56  mov     ecx, cs:CallbackContext
0x180064b5c  mov     ebx, 8007000Eh
0x180064b61  cmp     ecx, 2
0x180064b64  jbe     loc_180064E0F
0x180064b6a  lea     rax, aFailedToAlloca_8; "Failed to allocate ACL"
0x180064b71  mov     [rbp+arg_10], 436h
0x180064b78  mov     [rbp+var_8], rax
0x180064b7c  lea     rdx, byte_1801C56A7
0x180064b83  lea     rax, aBuildnamedpipe; "BuildNamedPipeAcl"
0x180064b8a  mov     [rbp+var_10], rax
0x180064b8e  lea     rax, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180064b95  mov     [rbp+var_18], rax
0x180064b99  lea     rax, aErrorCondition; "Error condition failed"
0x180064ba0  mov     [rbp+var_20], rax
0x180064ba4  lea     rax, [rbp+var_8]
0x180064ba8  mov     [rsp+80h+var_38], rax
0x180064bad  lea     rax, [rbp+var_10]
0x180064bb1  mov     [rsp+80h+var_40], rax
0x180064bb6  lea     rax, [rbp+arg_10]
0x180064bba  mov     [rsp+80h+var_48], rax
0x180064bbf  lea     rax, [rbp+var_18]
0x180064bc3  mov     [rsp+80h+var_50], rax
0x180064bc8  lea     rax, [rbp+arg_18]
0x180064bcc  mov     [rsp+80h+var_58], rax
0x180064bd1  lea     rax, [rbp+var_20]
0x180064bd5  jmp     loc_180064AFD
0x180064bda  mov     r8, r13; Size
0x180064bdd  xor     edx, edx; Val
0x180064bdf  mov     rcx, rdi; void *
0x180064be2  call    memset_0
0x180064be7  mov     r8d, 2; dwAclRevision
0x180064bed  mov     edx, ebx; nAclLength
0x180064bef  mov     rcx, rdi; pAcl
0x180064bf2  call    cs:__imp_InitializeAcl
0x180064bf8  test    eax, eax
0x180064bfa  jnz     loc_180064C94
0x180064c00  call    cs:__imp_GetLastError
0x180064c06  mov     ebx, eax
0x180064c08  test    eax, eax
0x180064c0a  jle     short loc_180064C15
0x180064c0c  movzx   ebx, ax
0x180064c0f  or      ebx, 80070000h
0x180064c15  mov     eax, cs:CallbackContext
0x180064c1b  cmp     eax, 2
0x180064c1e  jbe     loc_180064E0F
0x180064c24  lea     rax, aFailToInitiali; "Fail to InitializeAcl"
0x180064c2b  mov     [rbp+arg_10], 43Bh
0x180064c32  mov     [rbp+var_8], rax
0x180064c36  lea     rdx, byte_1801C5655
0x180064c3d  lea     rax, aBuildnamedpipe; "BuildNamedPipeAcl"
0x180064c44  mov     [rbp+var_10], rax
0x180064c48  lea     rax, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180064c4f  mov     [rbp+var_18], rax
0x180064c53  lea     rax, aErrorCondition; "Error condition failed"
0x180064c5a  mov     [rbp+var_20], rax
0x180064c5e  lea     rax, [rbp+var_8]
0x180064c62  mov     [rsp+80h+var_38], rax
0x180064c67  lea     rax, [rbp+var_10]
0x180064c6b  mov     [rsp+80h+var_40], rax
0x180064c70  lea     rax, [rbp+arg_10]
0x180064c74  mov     [rsp+80h+var_48], rax
0x180064c79  lea     rax, [rbp+var_18]
0x180064c7d  mov     [rsp+80h+var_50], rax
0x180064c82  lea     rax, [rbp+arg_18]
0x180064c86  mov     [rsp+80h+var_58], rax
0x180064c8b  lea     rax, [rbp+var_20]
0x180064c8f  jmp     loc_180064AFD
0x180064c94  xor     ebx, ebx
0x180064c96  mov     r13d, 1F01FFh
0x180064c9c  test    rsi, rsi
0x180064c9f  jz      short loc_180064CC7
0x180064ca1  mov     r9, [r12+rbx*8]; pSid
0x180064ca5  mov     r8d, r13d; AccessMask
0x180064ca8  mov     edx, 2; dwAceRevision
0x180064cad  mov     rcx, rdi; pAcl
0x180064cb0  call    cs:__imp_AddAccessAllowedAce
0x180064cb6  test    eax, eax
0x180064cb8  jz      loc_180064D78
0x180064cbe  inc     ebx
0x180064cc0  mov     eax, ebx
0x180064cc2  cmp     rax, rsi
0x180064cc5  jb      short loc_180064CA1
0x180064cc7  mov     r9, [rbp+pSid]; pSid
0x180064ccb  mov     r8d, r13d; AccessMask
0x180064cce  mov     edx, 2; dwAceRevision
0x180064cd3  mov     rcx, rdi; pAcl
0x180064cd6  call    cs:__imp_AddAccessAllowedAce
0x180064cdc  test    eax, eax
0x180064cde  jnz     loc_180064E08
0x180064ce4  call    cs:__imp_GetLastError
0x180064cea  mov     ebx, eax
0x180064cec  test    eax, eax
0x180064cee  jle     short loc_180064CF9
0x180064cf0  movzx   ebx, ax
0x180064cf3  or      ebx, 80070000h
0x180064cf9  mov     eax, cs:CallbackContext
0x180064cff  cmp     eax, 2
0x180064d02  jbe     loc_180064E0F
0x180064d08  lea     rax, aFailToAddacces_0; "Fail to AddAccessAllowedAce for current"...
0x180064d0f  mov     [rbp+arg_10], 453h
0x180064d16  mov     [rbp+var_8], rax
0x180064d1a  lea     rdx, byte_1801C5603
0x180064d21  lea     rax, aBuildnamedpipe; "BuildNamedPipeAcl"
0x180064d28  mov     [rbp+var_10], rax
0x180064d2c  lea     rax, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180064d33  mov     [rbp+var_18], rax
0x180064d37  lea     rax, aErrorCondition; "Error condition failed"
0x180064d3e  mov     [rbp+var_20], rax
0x180064d42  lea     rax, [rbp+var_8]
0x180064d46  mov     [rsp+80h+var_38], rax
0x180064d4b  lea     rax, [rbp+var_10]
0x180064d4f  mov     [rsp+80h+var_40], rax
0x180064d54  lea     rax, [rbp+arg_10]
0x180064d58  mov     [rsp+80h+var_48], rax
0x180064d5d  lea     rax, [rbp+var_18]
0x180064d61  mov     [rsp+80h+var_50], rax
0x180064d66  lea     rax, [rbp+arg_18]
0x180064d6a  mov     [rsp+80h+var_58], rax
0x180064d6f  lea     rax, [rbp+var_20]
0x180064d73  jmp     loc_180064AFD
0x180064d78  call    cs:__imp_GetLastError
0x180064d7e  mov     ebx, eax
0x180064d80  test    eax, eax
0x180064d82  jle     short loc_180064D8D
0x180064d84  movzx   ebx, ax
0x180064d87  or      ebx, 80070000h
0x180064d8d  mov     eax, cs:CallbackContext
0x180064d93  cmp     eax, 2
0x180064d96  jbe     short loc_180064E0F
0x180064d98  lea     rax, aFailToAddacces; "Fail to AddAccessAllowedAce for supplie"...
0x180064d9f  mov     [rbp+arg_10], 447h
0x180064da6  mov     [rbp+var_8], rax
0x180064daa  lea     rdx, byte_1801C55B1
0x180064db1  lea     rax, aBuildnamedpipe; "BuildNamedPipeAcl"
0x180064db8  mov     [rbp+var_10], rax
0x180064dbc  lea     rax, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180064dc3  mov     [rbp+var_18], rax
0x180064dc7  lea     rax, aErrorCondition; "Error condition failed"
0x180064dce  mov     [rbp+var_20], rax
0x180064dd2  lea     rax, [rbp+var_8]
0x180064dd6  mov     [rsp+80h+var_38], rax
0x180064ddb  lea     rax, [rbp+var_10]
0x180064ddf  mov     [rsp+80h+var_40], rax
0x180064de4  lea     rax, [rbp+arg_10]
0x180064de8  mov     [rsp+80h+var_48], rax
0x180064ded  lea     rax, [rbp+var_18]
0x180064df1  mov     [rsp+80h+var_50], rax
0x180064df6  lea     rax, [rbp+arg_18]
0x180064dfa  mov     [rsp+80h+var_58], rax
0x180064dff  lea     rax, [rbp+var_20]
0x180064e03  jmp     loc_180064AFD
0x180064e08  mov     [r14], rdi
0x180064e0b  xor     edi, edi
0x180064e0d  xor     ebx, ebx
0x180064e0f  cmp     [rbp+pSid], 0
0x180064e14  jz      short loc_180064E1F
0x180064e16  mov     rcx, [rbp+pSid]; Block
0x180064e1a  call    ??3@YAXPEAX@Z; operator delete(void *)
  ... truncated ...
```
