# SecUtils::TraceAuthenticationPackageInfo(void *)

- ea: `0x180096fb8`
- end: `0x18009731a`
- name: `?TraceAuthenticationPackageInfo@SecUtils@@YAJPEAX@Z`
- size: `866`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800943c0`
- `0x1800f2dd8`
- `0x1800f382c`

## callees

- `0x18000552c`
- `0x1800056bc`
- `0x18004c01c`
- `0x1800711c8`
- `0x180071a60`
- `0x180078c20`
- `0x180096f88`
- `0x180096fb8`
- `0x1801614a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800970a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800970a6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18009707b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18009707b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009709c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009709c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800972dd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800972dd`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800972f6`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800972f6`
- `SspiCli!LsaGetLogonSessionData` at `0x180097121`
- `SspiCli!LsaGetLogonSessionData` at `0x180097121`

## string_xrefs

- `0x180097041`: `Invalid token handle`
- `0x1800970f8`: `GetTokenInformation failed on token`

## pseudocode

```c
__int64 __fastcall SecUtils::TraceAuthenticationPackageInfo(HANDLE TokenHandle, void *a2, __int64 a3)
{
  signed int v4; // ebx
  int v5; // eax
  BOOL v6; // r15d
  signed int LastError; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // eax
  NTSTATUS LogonSessionData; // edi
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // edi
  const wchar_t *v15; // rsi
  unsigned int v16; // edi
  int v17; // r14d
  __int128 v18; // xmm0
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int ActivityIdPrefix; // eax
  PVOID v23; // rcx
  PVOID Buffer; // [rsp+60h] [rbp-A0h] BYREF
  DWORD ReturnLength; // [rsp+68h] [rbp-98h] BYREF
  int v27; // [rsp+6Ch] [rbp-94h] BYREF
  int v28; // [rsp+70h] [rbp-90h] BYREF
  __int128 *v29; // [rsp+78h] [rbp-88h] BYREF
  char *v30; // [rsp+80h] [rbp-80h] BYREF
  const char *v31; // [rsp+88h] [rbp-78h] BYREF
  const char *v32; // [rsp+90h] [rbp-70h] BYREF
  __int64 v33; // [rsp+98h] [rbp-68h] BYREF
  const char *v34; // [rsp+A0h] [rbp-60h] BYREF
  GUID ActivityId; // [rsp+A8h] [rbp-58h] BYREF
  char v36; // [rsp+B8h] [rbp-48h]
  __int128 v37; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD TokenInformation[3]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v39; // [rsp+100h] [rbp+0h]

  Buffer = 0;
  v39 = 0;
  ReturnLength = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  if ( (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v4 = 0;
    v6 = ImpersonateLoggedOnUser(TokenHandle);
    if ( GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
      goto LABEL_14;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_14:
      *(_QWORD *)ActivityId.Data4 = 0;
      *(_QWORD *)&ActivityId.Data1 = &Buffer;
      v36 = 1;
      LogonSessionData = LsaGetLogonSessionData(
                           (PLUID)TokenInformation + 1,
                           (PSECURITY_LOGON_SESSION_DATA *)ActivityId.Data4);
      wil::details::out_param_t<wistd::unique_ptr<_SECURITY_LOGON_SESSION_DATA,wil::function_deleter<long (*)(void *),&long LsaFreeReturnBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<_SECURITY_LOGON_SESSION_DATA,wil::function_deleter<long (*)(void *),&long LsaFreeReturnBuffer(void *)>>>(&ActivityId);
      v14 = LogonSessionData | 0x10000000;
      if ( v14 < 0 )
      {
        v4 = v14;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v12, v13);
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            (unsigned int)WPP_f5b992e9d455330a647a66dd3f03467f_Traceguids,
            ActivityIdPrefix,
            (__int64)"LsaGetLogonSessionData failed",
            v14);
        }
      }
      else if ( Buffer )
      {
        v15 = (const wchar_t *)*((_QWORD *)Buffer + 7);
        v16 = *((unsigned __int16 *)Buffer + 24) >> 1;
        if ( !wcsncmp_0(v15, L"NTLM", v16)
          || !wcsncmp_0(v15, L"MICROSOFT_AUTHENTICATION_PACKAGE_V1_0", v16)
          || (v17 = 0, !wcsncmp_0(v15, L"MSV1_0", v16)) )
        {
          v17 = 1;
        }
        if ( (unsigned int)CallbackContext > 4 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL) )
        {
          v18 = (__int128)*RdpActivityId::GetCurrentActivityId(&ActivityId);
          v27 = v17;
          v29 = &v37;
          v37 = v18;
          v19 = *((_DWORD *)Buffer + 16);
          v30 = (char *)Buffer + 48;
          v31 = "Authentication";
          v32 = "Stack";
          v34 = "Checkpoint";
          v28 = v19;
          v33 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
            v19,
            (unsigned int)byte_1801B06CD,
            v20,
            v21,
            (__int64)&v34,
            (__int64)&v33,
            (__int64)&v32,
            (__int64)&v31,
            (__int64)&v30,
            (__int64)&v28,
            (__int64)&v27,
            (__int64)&v29);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v8, v9);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)WPP_f5b992e9d455330a647a66dd3f03467f_Traceguids,
        v10,
        (__int64)"GetTokenInformation failed on token",
        v4);
    }
    if ( v6 )
      RevertToSelf();
  }
  else
  {
    v4 = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, a2, a3);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_f5b992e9d455330a647a66dd3f03467f_Traceguids,
        v5,
        (__int64)"Invalid token handle",
        87);
    }
  }
  v23 = Buffer;
  Buffer = 0;
  if ( v23 )
    LsaFreeReturnBuffer(v23);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180096fb8  push    rbp
0x180096fba  push    rbx
0x180096fbb  push    rsi
0x180096fbc  push    rdi
0x180096fbd  push    r14
0x180096fbf  push    r15
0x180096fc1  lea     rbp, [rsp-18h]
0x180096fc6  sub     rsp, 118h
0x180096fcd  mov     rax, cs:__security_cookie
0x180096fd4  xor     rax, rsp
0x180096fd7  mov     [rbp+40h+var_38], rax
0x180096fdb  xor     eax, eax
0x180096fdd  mov     [rsp+140h+Buffer], 0
0x180096fe6  xorps   xmm0, xmm0
0x180096fe9  mov     [rbp+40h+var_40], rax
0x180096fed  mov     [rsp+140h+var_D8], eax
0x180096ff1  mov     rdi, rcx
0x180096ff4  lea     rax, [rcx+1]
0x180096ff8  movups  [rbp+40h+TokenInformation], xmm0
0x180096ffc  movups  [rbp+40h+var_60], xmm0
0x180097000  movups  [rbp+40h+var_50], xmm0
0x180097004  test    rax, 0FFFFFFFFFFFFFFFEh
0x18009700a  jnz     short loc_180097079
0x18009700c  mov     ebx, 80070057h
0x180097011  mov     rcx, cs:WPP_GLOBAL_Control
0x180097018  lea     rax, WPP_GLOBAL_Control
0x18009701f  cmp     rcx, rax
0x180097022  jz      loc_1800972E3
0x180097028  test    byte ptr [rcx+1Ch], 8
0x18009702c  jz      loc_1800972E3
0x180097032  cmp     byte ptr [rcx+19h], 2
0x180097036  jb      loc_1800972E3
0x18009703c  call    RdpX_GetActivityIdPrefix
0x180097041  lea     rcx, aInvalidTokenHa; "Invalid token handle"
0x180097048  mov     dword ptr [rsp+140h+var_118], 80070057h
0x180097050  mov     [rsp+140h+ReturnLength], rcx
0x180097055  lea     r8, WPP_f5b992e9d455330a647a66dd3f03467f_Traceguids
0x18009705c  mov     rcx, cs:WPP_GLOBAL_Control
0x180097063  mov     edx, 0Ch
0x180097068  mov     r9d, eax
0x18009706b  mov     rcx, [rcx+10h]
0x18009706f  call    WPP_SF_DsD
0x180097074  jmp     loc_1800972E3
0x180097079  xor     ebx, ebx
0x18009707b  call    cs:__imp_ImpersonateLoggedOnUser
0x180097081  lea     r9d, [rbx+38h]; TokenInformationLength
0x180097085  mov     rcx, rdi; TokenHandle
0x180097088  mov     r15d, eax
0x18009708b  lea     r8, [rbp+40h+TokenInformation]; TokenInformation
0x18009708f  lea     rax, [rsp+140h+var_D8]
0x180097094  lea     edx, [rbx+0Ah]; TokenInformationClass
0x180097097  mov     [rsp+140h+ReturnLength], rax; ReturnLength
0x18009709c  call    cs:__imp_GetTokenInformation
0x1800970a2  test    eax, eax
0x1800970a4  jnz     short loc_180097104
0x1800970a6  call    cs:__imp_GetLastError
0x1800970ac  mov     ebx, eax
0x1800970ae  test    eax, eax
0x1800970b0  jle     short loc_1800970BB
0x1800970b2  movzx   ebx, ax
0x1800970b5  or      ebx, 80070000h
0x1800970bb  test    ebx, ebx
0x1800970bd  jns     short loc_180097104
0x1800970bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800970c6  lea     rax, WPP_GLOBAL_Control
0x1800970cd  cmp     rcx, rax
0x1800970d0  jz      loc_1800972D8
0x1800970d6  test    byte ptr [rcx+1Ch], 8
0x1800970da  jz      loc_1800972D8
0x1800970e0  cmp     byte ptr [rcx+19h], 2
0x1800970e4  jb      loc_1800972D8
0x1800970ea  call    RdpX_GetActivityIdPrefix
0x1800970ef  mov     edx, 0Dh
0x1800970f4  mov     dword ptr [rsp+140h+var_118], ebx
0x1800970f8  lea     rcx, aGettokeninform; "GetTokenInformation failed on token"
0x1800970ff  jmp     loc_1800972B9
0x180097104  lea     rax, [rsp+140h+Buffer]
0x180097109  mov     qword ptr [rbp+40h+ActivityId.Data4], 0
0x180097111  lea     rdx, [rbp+40h+ActivityId.Data4]; ppLogonSessionData
0x180097115  mov     qword ptr [rbp+40h+ActivityId.Data1], rax
0x180097119  lea     rcx, [rbp+40h+TokenInformation+8]; LogonId
0x18009711d  mov     [rbp+40h+var_88], 1
0x180097121  call    cs:__imp_LsaGetLogonSessionData
0x180097127  lea     rcx, [rbp+40h+ActivityId]
0x18009712b  mov     edi, eax
0x18009712d  call    ??1?$out_param_t@V?$unique_ptr@U_SECURITY_LOGON_SESSION_DATA@@U?$function_deleter@P6AJPEAX@Z$1?LsaFreeReturnBuffer@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_SECURITY_LOGON_SESSION_DATA,wil::function_deleter<long (*)(void *),&LsaFreeReturnBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<_SECURITY_LOGON_SESSION_DATA,wil::function_deleter<long (*)(void *),&LsaFreeReturnBuffer(void *)>>>(void)
0x180097132  or      edi, 10000000h
0x180097138  jl      loc_180097283
0x18009713e  mov     rax, [rsp+140h+Buffer]
0x180097143  test    rax, rax
0x180097146  jz      loc_1800972D8
0x18009714c  movzx   edi, word ptr [rax+30h]
0x180097150  lea     rdx, aNtlm; "NTLM"
0x180097157  mov     rsi, [rax+38h]
0x18009715b  shr     edi, 1
0x18009715d  mov     rcx, rsi; String1
0x180097160  mov     r8d, edi; MaxCount
0x180097163  call    wcsncmp_0
0x180097168  test    eax, eax
0x18009716a  jz      short loc_18009719B
0x18009716c  mov     r8d, edi; MaxCount
0x18009716f  lea     rdx, aMicrosoftAuthe; "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0"
0x180097176  mov     rcx, rsi; String1
0x180097179  call    wcsncmp_0
0x18009717e  test    eax, eax
0x180097180  jz      short loc_18009719B
0x180097182  mov     r8d, edi; MaxCount
0x180097185  lea     rdx, aMsv10; "MSV1_0"
0x18009718c  mov     rcx, rsi; String1
0x18009718f  xor     r14d, r14d
0x180097192  call    wcsncmp_0
0x180097197  test    eax, eax
0x180097199  jnz     short loc_1800971A1
0x18009719b  mov     r14d, 1
0x1800971a1  mov     eax, cs:CallbackContext
0x1800971a7  cmp     eax, 4
0x1800971aa  jbe     loc_1800972D8
0x1800971b0  mov     rdx, 470000000000h
0x1800971ba  lea     rcx, CallbackContext
0x1800971c1  call    _tlgKeywordOn
0x1800971c6  test    al, al
0x1800971c8  jz      loc_1800972D8
0x1800971ce  lea     rcx, [rbp+40h+ActivityId]; ActivityId
0x1800971d2  call    ?GetCurrentActivityId@RdpActivityId@@SA?AU_GUID@@XZ; RdpActivityId::GetCurrentActivityId(void)
0x1800971d7  lea     rdx, byte_1801B06CD
0x1800971de  movups  xmm0, xmmword ptr [rax]
0x1800971e1  lea     rax, [rbp+40h+var_80]
0x1800971e5  mov     [rsp+140h+var_D4], r14d
0x1800971ea  mov     [rsp+140h+var_C8], rax
0x1800971ef  mov     rax, [rsp+140h+Buffer]
0x1800971f4  movdqu  [rbp+40h+var_80], xmm0
0x1800971f9  mov     ecx, [rax+40h]
0x1800971fc  add     rax, 30h ; '0'
0x180097200  mov     [rbp+40h+var_C0], rax
0x180097204  lea     rax, aAuthentication_2; "Authentication"
0x18009720b  mov     [rbp+40h+var_B8], rax
0x18009720f  lea     rax, aStack; "Stack"
0x180097216  mov     [rbp+40h+var_B0], rax
0x18009721a  lea     rax, aCheckpoint; "Checkpoint"
0x180097221  mov     [rbp+40h+var_A0], rax
0x180097225  lea     rax, [rsp+140h+var_C8]
0x18009722a  mov     [rsp+140h+var_E8], rax
0x18009722f  lea     rax, [rsp+140h+var_D4]
0x180097234  mov     [rsp+140h+var_F0], rax
0x180097239  lea     rax, [rsp+140h+var_D0]
0x18009723e  mov     [rsp+140h+var_F8], rax
0x180097243  lea     rax, [rbp+40h+var_C0]
0x180097247  mov     [rsp+140h+var_100], rax
0x18009724c  lea     rax, [rbp+40h+var_B8]
0x180097250  mov     [rsp+140h+var_108], rax
0x180097255  lea     rax, [rbp+40h+var_B0]
0x180097259  mov     [rsp+140h+var_110], rax
0x18009725e  lea     rax, [rbp+40h+var_A8]
0x180097262  mov     [rsp+140h+var_118], rax
0x180097267  lea     rax, [rbp+40h+var_A0]
0x18009726b  mov     [rsp+140h+ReturnLength], rax
0x180097270  mov     [rsp+140h+var_D0], ecx
0x180097274  mov     [rbp+40h+var_A8], 1000000h
0x18009727c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180097281  jmp     short loc_1800972D8
0x180097283  mov     ebx, edi
0x180097285  mov     rcx, cs:WPP_GLOBAL_Control
0x18009728c  lea     rax, WPP_GLOBAL_Control
0x180097293  cmp     rcx, rax
0x180097296  jz      short loc_1800972D8
0x180097298  test    byte ptr [rcx+1Ch], 8
0x18009729c  jz      short loc_1800972D8
0x18009729e  cmp     byte ptr [rcx+19h], 2
0x1800972a2  jb      short loc_1800972D8
0x1800972a4  call    RdpX_GetActivityIdPrefix
0x1800972a9  mov     edx, 0Eh
0x1800972ae  mov     dword ptr [rsp+140h+var_118], edi
0x1800972b2  lea     rcx, aLsagetlogonses_0; "LsaGetLogonSessionData failed"
0x1800972b9  mov     [rsp+140h+ReturnLength], rcx
0x1800972be  lea     r8, WPP_f5b992e9d455330a647a66dd3f03467f_Traceguids
0x1800972c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800972cc  mov     r9d, eax
0x1800972cf  mov     rcx, [rcx+10h]
0x1800972d3  call    WPP_SF_DsD
0x1800972d8  test    r15d, r15d
0x1800972db  jz      short loc_1800972E3
0x1800972dd  call    cs:__imp_RevertToSelf
0x1800972e3  mov     rcx, [rsp+140h+Buffer]; Buffer
0x1800972e8  mov     [rsp+140h+Buffer], 0
0x1800972f1  test    rcx, rcx
0x1800972f4  jz      short loc_1800972FC
0x1800972f6  call    cs:__imp_LsaFreeReturnBuffer
0x1800972fc  mov     eax, ebx
0x1800972fe  mov     rcx, [rbp+40h+var_38]
0x180097302  xor     rcx, rsp; StackCookie
0x180097305  call    __security_check_cookie
0x18009730a  add     rsp, 118h
0x180097311  pop     r15
0x180097313  pop     r14
0x180097315  pop     rdi
0x180097316  pop     rsi
0x180097317  pop     rbx
0x180097318  pop     rbp
0x180097319  retn
```
