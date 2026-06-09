# KeyManager::DeleteUserKey(ushort const *)

- ea: `0x18008271c`
- end: `0x180082af6`
- name: `?DeleteUserKey@KeyManager@@AEAAJPEBG@Z`
- size: `986`
- prototype: `__int64 __fastcall(KeyManager *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `18`
- tags: `authz_impersonation`

## callers

- `0x180029e68`
- `0x180080100`
- `0x1800822b0`

## callees

- `0x1800011ec`
- `0x1800012a4`
- `0x180005ba0`
- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x180012948`
- `0x1800204f0`
- `0x180031f44`
- `0x1800334e0`
- `0x180034cd0`
- `0x1800351b0`
- `0x1800429a8`
- `0x180044300`
- `0x180055174`
- `0x18008271c`
- `0x180082c18`
- `0x180083004`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082a3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082a3d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180082a6e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180082a6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082a32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082a32`
- `cryptngc!NgcFreeEnumState` at `0x180082a59`
- `cryptngc!NgcFreeEnumState` at `0x180082a59`
- `cryptngc!NgcEnumUserIdKeys` at `0x180082844`
- `cryptngc!NgcEnumUserIdKeys` at `0x180082844`
- `cryptngc!NgcDeleteUserIdKey` at `0x180082914`
- `cryptngc!NgcDeleteUserIdKey` at `0x180082914`

## string_xrefs

- `0x1800827ee`: `KeyManager::DeleteUserKey`
- `0x180082859`: `%s: User ID key is not found. Return success. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Error code: 0x%08x.`
- `0x1800828e0`: `%s: NgcEnumUserIdKeys returns NULL pKeyInfo. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, HRESULT: 0x%08x.`
- `0x1800828a6`: `%s: Cannot find user ID key. NgcEnumUserIdKeys failed. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Error code: 0x%08x.`
- `0x1800829cb`: `%s: NgcDeleteUserIdKey failed because the key is not found. Ignoring this error. Keyname: %s, Error code: 0x%08x.`
- `0x1800829b7`: `%s: NgcDeleteUserIdKey succeeded. Keyname: %s.`
- `0x180082943`: `%s: NgcDeleteUserIdKey failed. Keyname: %s, Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall KeyManager::DeleteUserKey(KeyManager *this, unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // rsi
  int UserSid; // ebx
  int v6; // eax
  DWORD LastError; // eax
  __int64 *v9; // [rsp+20h] [rbp-39h]
  __int64 v10; // [rsp+40h] [rbp-19h] BYREF
  unsigned __int16 *v11; // [rsp+48h] [rbp-11h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-9h] BYREF
  __int64 v13; // [rsp+58h] [rbp-1h] BYREF
  int v14; // [rsp+60h] [rbp+7h] BYREF
  char v15; // [rsp+64h] [rbp+Bh]
  GUID ActivityId; // [rsp+78h] [rbp+1Fh] BYREF

  v2 = (const unsigned __int16 *)*((_QWORD *)this + 8);
  hMem = 0;
  v13 = 0;
  v11 = 0;
  v14 = 0;
  v15 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v14);
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x200000000000LL) )
  {
    v10 = 0x1000000;
    if ( v15 )
      _tlgGuidIsZero(&ActivityId);
    v9 = &v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_18013D150,
      (__int64)byte_18012AD0D);
  }
  if ( (unsigned int)IsEmptyString(v2) )
  {
    if ( (unsigned int)IsEmptyString(a2) )
    {
      UserSid = KeyManager::GetUserSid(this, &v11);
      if ( UserSid < 0 )
        goto LABEL_21;
      a2 = v11;
    }
    UserSid = NgcEnumUserIdKeys(*((_QWORD *)this + 2), *((_QWORD *)this + 3), *((_QWORD *)this + 4), a2, &hMem, &v13);
    if ( UserSid == -2146893782 )
    {
      Logger::TraceVerbose(
        (wchar_t *)L"%s: User ID key is not found. Return success. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s"
                    ", Error code: 0x%08x.",
        L"KeyManager::DeleteUserKey",
        a2,
        *((_QWORD *)this + 2),
        *((_QWORD *)this + 3),
        *((_QWORD *)this + 4),
        -2146893782);
LABEL_26:
      UserSid = 0;
LABEL_27:
      if ( (unsigned int)dword_18013D150 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x200000000000LL) )
      {
        v10 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
          (__int64)&dword_18013D150,
          (__int64)byte_18012AF9B);
      }
      KeyManager::FreeUserKey(this);
      goto LABEL_31;
    }
    if ( UserSid < 0 )
    {
      Logger::WriteNgcEnumUserIdKeysFailureEvent(
        a2,
        *((const unsigned __int16 **)this + 2),
        *((const unsigned __int16 **)this + 3),
        *((const unsigned __int16 **)this + 4),
        UserSid);
      Logger::TraceError(
        L"%s: Cannot find user ID key. NgcEnumUserIdKeys failed. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, "
         "Error code: 0x%08x.",
        L"KeyManager::DeleteUserKey",
        a2,
        *((_QWORD *)this + 2),
        *((_QWORD *)this + 3),
        *((_QWORD *)this + 4),
        UserSid);
      goto LABEL_21;
    }
    if ( !hMem )
    {
      Logger::TraceError(
        L"%s: NgcEnumUserIdKeys returns NULL pKeyInfo. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, HRESULT: 0x%08x.",
        L"KeyManager::DeleteUserKey",
        a2,
        *((_QWORD *)this + 2),
        *((_QWORD *)this + 3),
        *((_QWORD *)this + 4),
        UserSid);
      goto LABEL_27;
    }
    v2 = (const unsigned __int16 *)*((_QWORD *)hMem + 4);
  }
  v6 = NgcDeleteUserIdKey(v2);
  UserSid = v6;
  if ( v6 == -2147023728 || v6 == -2146893807 )
  {
    Logger::TraceVerbose(
      (wchar_t *)L"%s: NgcDeleteUserIdKey failed because the key is not found. Ignoring this error. Keyname: %s, Error code: 0x%08x.",
      L"KeyManager::DeleteUserKey",
      v2,
      (unsigned int)v6,
      v9);
    goto LABEL_26;
  }
  if ( v6 >= 0 )
  {
    Logger::WriteNgcDeleteUserIdKeySuccessEvent(v2);
    Logger::TraceInformation(L"%s: NgcDeleteUserIdKey succeeded. Keyname: %s.", L"KeyManager::DeleteUserKey", v2);
    goto LABEL_27;
  }
  Logger::WriteNgcDeleteUserIdKeyFailureEvent(v2, v6);
  Logger::TraceError(
    L"%s: NgcDeleteUserIdKey failed. Keyname: %s, Error code: 0x%08x.",
    L"KeyManager::DeleteUserKey",
    v2,
    (unsigned int)UserSid);
LABEL_21:
  if ( (unsigned int)dword_18013D150 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x200000000000LL) )
  {
    LODWORD(v11) = UserSid;
    v10 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)&dword_18013D150,
      (__int64)byte_18012AF5B);
  }
LABEL_31:
  if ( LocalFree(hMem) )
  {
    LastError = GetLastError();
    Logger::TraceWarning((wchar_t *)L"%s: LocalFree failed with error 0x%08x.", L"KeyManager::DeleteUserKey", LastError);
  }
  NgcFreeEnumState(v13);
  if ( v15 )
    EventActivityIdControl(4u, &ActivityId);
  v14 = 2;
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x200000000000LL) )
  {
    v10 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_18013D150,
      (__int64)byte_18012AE41);
  }
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>((__int64)&v14);
  return (unsigned int)UserSid;
}

```

## disassembly

```asm
0x18008271c  mov     [rsp-8+arg_10], rbx
0x180082721  mov     [rsp-8+arg_18], rsi
0x180082726  push    rbp
0x180082727  push    rdi
0x180082728  push    r12
0x18008272a  push    r13
0x18008272c  push    r14
0x18008272e  lea     rbp, [rsp-37h]
0x180082733  sub     rsp, 90h
0x18008273a  mov     rax, cs:__security_cookie
0x180082741  xor     rax, rsp
0x180082744  mov     [rbp+57h+var_28], rax
0x180082748  mov     rsi, [rcx+40h]
0x18008274c  mov     rdi, rcx
0x18008274f  lea     rcx, [rbp+57h+var_50]
0x180082753  mov     [rbp+57h+hMem], 0
0x18008275b  mov     r14, rdx
0x18008275e  mov     [rbp+57h+var_58], 0
0x180082766  mov     [rbp+57h+var_68], 0
0x18008276e  mov     [rbp+57h+var_50], 0
0x180082775  mov     [rbp+57h+var_4C], 0
0x180082779  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18008277e  mov     eax, cs:dword_18013D150
0x180082784  lea     r12, dword_18013D150
0x18008278b  cmp     eax, 5
0x18008278e  jbe     short loc_1800827E6
0x180082790  mov     rdx, 200000000000h
0x18008279a  mov     rcx, r12
0x18008279d  call    _tlgKeywordOn
0x1800827a2  test    al, al
0x1800827a4  jz      short loc_1800827E6
0x1800827a6  cmp     [rbp+57h+var_4C], 0
0x1800827aa  mov     [rbp+57h+var_70], 1000000h
0x1800827b2  jz      short loc_1800827C7
0x1800827b4  lea     rcx, [rbp+57h+ActivityId]; struct _GUID *
0x1800827b8  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800827bd  test    al, al
0x1800827bf  jnz     short loc_1800827C7
0x1800827c1  lea     r9, [rbp+57h+ActivityId]
0x1800827c5  jmp     short loc_1800827CA
0x1800827c7  xor     r9d, r9d
0x1800827ca  lea     rax, [rbp+57h+var_70]
0x1800827ce  mov     rcx, r12
0x1800827d1  lea     r8, [rbp+57h+var_48]
0x1800827d5  mov     qword ptr [rsp+0B0h+var_90], rax
0x1800827da  lea     rdx, byte_18012AD0D
0x1800827e1  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800827e6  mov     rcx, rsi; unsigned __int16 *
0x1800827e9  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800827ee  lea     r13, aKeymanagerDele_0; "KeyManager::DeleteUserKey"
0x1800827f5  test    eax, eax
0x1800827f7  jz      loc_180082911
0x1800827fd  mov     rcx, r14; unsigned __int16 *
0x180082800  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180082805  test    eax, eax
0x180082807  jz      short loc_180082823
0x180082809  lea     rdx, [rbp+57h+var_68]; unsigned __int16 **
0x18008280d  mov     rcx, rdi; this
0x180082810  call    ?GetUserSid@KeyManager@@AEAAJPEAPEAG@Z; KeyManager::GetUserSid(ushort * *)
0x180082815  mov     ebx, eax
0x180082817  test    eax, eax
0x180082819  js      loc_180082955
0x18008281f  mov     r14, [rbp+57h+var_68]
0x180082823  mov     r8, [rdi+20h]
0x180082827  lea     rax, [rbp+57h+var_58]
0x18008282b  mov     rdx, [rdi+18h]
0x18008282f  mov     r9, r14
0x180082832  mov     rcx, [rdi+10h]
0x180082836  mov     [rsp+0B0h+var_88], rax
0x18008283b  lea     rax, [rbp+57h+hMem]
0x18008283f  mov     qword ptr [rsp+0B0h+var_90], rax
0x180082844  call    cs:__imp_NgcEnumUserIdKeys
0x18008284a  mov     ebx, eax
0x18008284c  mov     eax, 8009002Ah
0x180082851  cmp     ebx, eax
0x180082853  jnz     short loc_180082886
0x180082855  mov     r9, [rdi+10h]
0x180082859  lea     rcx, aSUserIdKeyIsNo; "%s: User ID key is not found. Return su"...
0x180082860  mov     [rsp+0B0h+var_80], eax
0x180082864  mov     r8, r14
0x180082867  mov     rax, [rdi+20h]
0x18008286b  mov     rdx, r13
0x18008286e  mov     [rsp+0B0h+var_88], rax
0x180082873  mov     rax, [rdi+18h]
0x180082877  mov     qword ptr [rsp+0B0h+var_90], rax
0x18008287c  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180082881  jmp     loc_1800829DD
0x180082886  test    ebx, ebx
0x180082888  jns     short loc_1800828D3
0x18008288a  mov     r9, [rdi+20h]; unsigned __int16 *
0x18008288e  mov     rcx, r14; unsigned __int16 *
0x180082891  mov     r8, [rdi+18h]; unsigned __int16 *
0x180082895  mov     rdx, [rdi+10h]; unsigned __int16 *
0x180082899  mov     [rsp+0B0h+var_90], ebx; int
0x18008289d  call    ?WriteNgcEnumUserIdKeysFailureEvent@Logger@@SAJPEBG000J@Z; Logger::WriteNgcEnumUserIdKeysFailureEvent(ushort const *,ushort const *,ushort const *,ushort const *,long)
0x1800828a2  mov     rax, [rdi+20h]
0x1800828a6  lea     rcx, aSCannotFindUse_1; "%s: Cannot find user ID key. NgcEnumUse"...
0x1800828ad  mov     r9, [rdi+10h]
0x1800828b1  mov     r8, r14
0x1800828b4  mov     [rsp+0B0h+var_80], ebx
0x1800828b8  mov     rdx, r13
0x1800828bb  mov     [rsp+0B0h+var_88], rax
0x1800828c0  mov     rax, [rdi+18h]
0x1800828c4  mov     qword ptr [rsp+0B0h+var_90], rax
0x1800828c9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800828ce  jmp     loc_180082955
0x1800828d3  mov     rsi, [rbp+57h+hMem]
0x1800828d7  test    rsi, rsi
0x1800828da  jnz     short loc_18008290D
0x1800828dc  mov     rax, [rdi+20h]
0x1800828e0  lea     rcx, aSNgcenumuserid; "%s: NgcEnumUserIdKeys returns NULL pKey"...
0x1800828e7  mov     r9, [rdi+10h]
0x1800828eb  mov     r8, r14
0x1800828ee  mov     [rsp+0B0h+var_80], ebx
0x1800828f2  mov     rdx, r13
0x1800828f5  mov     [rsp+0B0h+var_88], rax
0x1800828fa  mov     rax, [rdi+18h]
0x1800828fe  mov     qword ptr [rsp+0B0h+var_90], rax
0x180082903  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180082908  jmp     loc_1800829DF
0x18008290d  mov     rsi, [rsi+20h]
0x180082911  mov     rcx, rsi
0x180082914  call    cs:__imp_NgcDeleteUserIdKey
0x18008291a  mov     ebx, eax
0x18008291c  cmp     eax, 80070490h
0x180082921  jz      loc_1800829C8
0x180082927  cmp     eax, 80090011h
0x18008292c  jz      loc_1800829C8
0x180082932  mov     rcx, rsi; unsigned __int16 *
0x180082935  test    eax, eax
0x180082937  jns     short loc_1800829AF
0x180082939  mov     edx, eax; int
0x18008293b  call    ?WriteNgcDeleteUserIdKeyFailureEvent@Logger@@SAJPEBGJ@Z; Logger::WriteNgcDeleteUserIdKeyFailureEvent(ushort const *,long)
0x180082940  mov     r9d, ebx
0x180082943  lea     rcx, aSNgcdeleteuser; "%s: NgcDeleteUserIdKey failed. Keyname:"...
0x18008294a  mov     r8, rsi
0x18008294d  mov     rdx, r13
0x180082950  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180082955  mov     eax, cs:dword_18013D150
0x18008295b  cmp     eax, 2
0x18008295e  jbe     loc_180082A2E
0x180082964  mov     rdx, 200000000000h
0x18008296e  mov     rcx, r12
0x180082971  call    _tlgKeywordOn
0x180082976  test    al, al
0x180082978  jz      loc_180082A2E
0x18008297e  lea     rax, [rbp+57h+var_68]
0x180082982  mov     dword ptr [rbp+57h+var_68], ebx
0x180082985  mov     [rsp+0B0h+var_88], rax
0x18008298a  lea     rdx, byte_18012AF5B
0x180082991  lea     rax, [rbp+57h+var_70]
0x180082995  mov     [rbp+57h+var_70], 1000000h
0x18008299d  xor     r8d, r8d
0x1800829a0  mov     qword ptr [rsp+0B0h+var_90], rax
0x1800829a5  mov     rcx, r12
0x1800829a8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800829ad  jmp     short loc_180082A2E
0x1800829af  call    ?WriteNgcDeleteUserIdKeySuccessEvent@Logger@@SAJPEBG@Z; Logger::WriteNgcDeleteUserIdKeySuccessEvent(ushort const *)
0x1800829b4  mov     r8, rsi
0x1800829b7  lea     rcx, aSNgcdeleteuser_0; "%s: NgcDeleteUserIdKey succeeded. Keyna"...
0x1800829be  mov     rdx, r13
0x1800829c1  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800829c6  jmp     short loc_1800829DF
0x1800829c8  mov     r9d, ebx
0x1800829cb  lea     rcx, aSNgcdeleteuser_1; "%s: NgcDeleteUserIdKey failed because t"...
0x1800829d2  mov     r8, rsi
0x1800829d5  mov     rdx, r13
0x1800829d8  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800829dd  xor     ebx, ebx
0x1800829df  mov     eax, cs:dword_18013D150
0x1800829e5  cmp     eax, 4
0x1800829e8  jbe     short loc_180082A26
0x1800829ea  mov     rdx, 200000000000h
0x1800829f4  mov     rcx, r12
0x1800829f7  call    _tlgKeywordOn
0x1800829fc  test    al, al
0x1800829fe  jz      short loc_180082A26
0x180082a00  lea     rax, [rbp+57h+var_70]
0x180082a04  mov     [rbp+57h+var_70], 1000000h
0x180082a0c  xor     r9d, r9d
0x180082a0f  mov     qword ptr [rsp+0B0h+var_90], rax
0x180082a14  xor     r8d, r8d
0x180082a17  lea     rdx, byte_18012AF9B
0x180082a1e  mov     rcx, r12
0x180082a21  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180082a26  mov     rcx, rdi; this
0x180082a29  call    ?FreeUserKey@KeyManager@@AEAAXXZ; KeyManager::FreeUserKey(void)
0x180082a2e  mov     rcx, [rbp+57h+hMem]; hMem
0x180082a32  call    cs:__imp_LocalFree
0x180082a38  test    rax, rax
0x180082a3b  jz      short loc_180082A55
0x180082a3d  call    cs:__imp_GetLastError
0x180082a43  mov     rdx, r13
0x180082a46  lea     rcx, aSLocalfreeFail; "%s: LocalFree failed with error 0x%08x."
0x180082a4d  mov     r8d, eax
0x180082a50  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180082a55  mov     rcx, [rbp+57h+var_58]
0x180082a59  call    cs:__imp_NgcFreeEnumState
0x180082a5f  cmp     [rbp+57h+var_4C], 0
0x180082a63  jz      short loc_180082A74
0x180082a65  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180082a69  mov     ecx, 4; ControlCode
0x180082a6e  call    cs:__imp_EventActivityIdControl
0x180082a74  mov     eax, cs:dword_18013D150
0x180082a7a  mov     [rbp+57h+var_50], 2
0x180082a81  cmp     eax, 5
0x180082a84  jbe     short loc_180082AC3
0x180082a86  mov     rdx, 200000000000h
0x180082a90  mov     rcx, r12
0x180082a93  call    _tlgKeywordOn
0x180082a98  test    al, al
0x180082a9a  jz      short loc_180082AC3
0x180082a9c  lea     rax, [rbp+57h+var_70]
0x180082aa0  mov     [rbp+57h+var_70], 1000000h
0x180082aa8  xor     r9d, r9d
0x180082aab  mov     qword ptr [rsp+0B0h+var_90], rax
0x180082ab0  lea     r8, [rbp+57h+var_48]
0x180082ab4  mov     rcx, r12
0x180082ab7  lea     rdx, byte_18012AE41
0x180082abe  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180082ac3  lea     rcx, [rbp+57h+var_50]
0x180082ac7  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(void)
0x180082acc  mov     eax, ebx
0x180082ace  mov     rcx, [rbp+57h+var_28]
0x180082ad2  xor     rcx, rsp; StackCookie
0x180082ad5  call    __security_check_cookie
0x180082ada  lea     r11, [rsp+0B0h+var_20]
0x180082ae2  mov     rbx, [r11+40h]
0x180082ae6  mov     rsi, [r11+48h]
0x180082aea  mov     rsp, r11
0x180082aed  pop     r14
0x180082aef  pop     r13
0x180082af1  pop     r12
0x180082af3  pop     rdi
0x180082af4  pop     rbp
0x180082af5  retn
```
