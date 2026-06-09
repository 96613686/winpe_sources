# KeyManager::CreateUserKey(HWND__ *)

- ea: `0x180081edc`
- end: `0x1800822aa`
- name: `?CreateUserKey@KeyManager@@QEAAJPEAUHWND__@@@Z`
- size: `974`
- prototype: `__int64 __fastcall(KeyManager *__hidden this, HWND)`
- caller_count: `3`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180080ca4`
- `0x180080fbc`
- `0x1800811cc`

## callees

- `0x1800011ec`
- `0x1800012a4`
- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x18000cbd8`
- `0x1800204f0`
- `0x180031ae0`
- `0x18003c288`
- `0x18003f4dc`
- `0x180044300`
- `0x180051604`
- `0x180055174`
- `0x180055194`
- `0x180081edc`
- `0x180082c18`
- `0x180082d04`
- `0x180083004`
- `0x180083a48`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180081fbe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18008208f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180081fbe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18008208f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180082227`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180082227`
- `cryptngc!NgcCreateUserIdKey` at `0x180082038`
- `cryptngc!NgcCreateUserIdKey` at `0x180082038`

## string_xrefs

- `0x180082055`: `KeyManager::CreateUserKey`
- `0x18008207c`: `KeyManager::CreateUserKey`
- `0x1800820cb`: `KeyManager::CreateUserKey`
- `0x180082181`: `KeyManager::CreateUserKey`
- `0x18008204e`: `NgcCreateUserIdKey`
- `0x1800820d6`: `%s: NgcCreateUserIdKey failed. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Flags: %lu, Error code: 0x%08x.`
- `0x18008218c`: `%s: NgcCreateUserIdKey succeeded. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Flags: %lu.`

## pseudocode

```c
__int64 __fastcall KeyManager::CreateUserKey(KeyManager *this, HWND a2)
{
  __int64 v4; // r8
  DWORD TickCount; // eax
  DWORD v6; // r15d
  int UserSid; // edi
  int UserKeyAttestation; // eax
  DWORD v9; // eax
  const unsigned __int16 *v10; // r9
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // esi
  __int64 v14; // rcx
  _QWORD *v16; // [rsp+20h] [rbp-69h]
  char *v17; // [rsp+30h] [rbp-59h]
  unsigned int *v18; // [rsp+38h] [rbp-51h]
  unsigned __int16 *v19; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v20; // [rsp+58h] [rbp-31h] BYREF
  _QWORD v21[3]; // [rsp+60h] [rbp-29h] BYREF
  int v22; // [rsp+78h] [rbp-11h] BYREF
  char v23; // [rsp+7Ch] [rbp-Dh]
  GUID ActivityId; // [rsp+90h] [rbp+7h] BYREF
  _QWORD v25[2]; // [rsp+A0h] [rbp+17h] BYREF

  v19 = 0;
  v20 = 0;
  v22 = 0;
  v23 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v22);
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
  {
    v25[0] = 0x1000000;
    if ( v23 )
      _tlgGuidIsZero(&ActivityId);
    v16 = v25;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_18013D150,
      (__int64)&byte_18012B08F);
  }
  if ( (Microsoft_Windows_HelloForBusinessEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(MS_PROVIDER_HFB_Context, EVENT_HFB_KEY_CREATION_START, v4, 1, v25);
  TickCount = GetTickCount();
  v21[0] = *((_QWORD *)this + 2);
  v6 = TickCount;
  v21[1] = *((_QWORD *)this + 3);
  v21[2] = *((_QWORD *)this + 4);
  UserSid = KeyManager::GetUserSid(this, &v19);
  if ( UserSid >= 0 )
  {
    KeyManager::FreeUserKey(this);
    v18 = &v20;
    v17 = (char *)this + 72;
    LODWORD(v16) = 74;
    UserSid = NgcCreateUserIdKey(v21, v19, a2, *((_QWORD *)this + 5));
    *((_QWORD *)this + 10) = v20;
    if ( UserSid >= 0 )
    {
      UserKeyAttestation = KeyManager::GetUserKeyAttestation(this, a2);
      if ( UserKeyAttestation < 0 )
        Logger::TraceWarning(
          (wchar_t *)L"%s: Unable to get Attestation for NGC Key continuing without attestation. GetUserKeyAttestation fai"
                      "led with error code 0x%08x.",
          L"KeyManager::CreateUserKey",
          (unsigned int)UserKeyAttestation);
    }
    else
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"KeyManager::CreateUserKey",
        L"NgcCreateUserIdKey",
        (unsigned int)UserSid);
    }
  }
  v9 = GetTickCount();
  v10 = (const unsigned __int16 *)*((_QWORD *)this + 4);
  v11 = (const unsigned __int16 *)*((_QWORD *)this + 3);
  v12 = (const unsigned __int16 *)*((_QWORD *)this + 2);
  v13 = (v9 - v6) / 0x3E8;
  if ( UserSid >= 0 )
  {
    Logger::WriteNgcCreateUserIdKeySuccessEvent(v19, v12, v11, v10, (unsigned int)v16);
    LODWORD(v17) = 74;
    Logger::TraceVerbose(
      (wchar_t *)L"%s: NgcCreateUserIdKey succeeded. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Flags: %lu.",
      L"KeyManager::CreateUserKey",
      v19,
      *((_QWORD *)this + 2),
      *((_QWORD *)this + 3),
      *((_QWORD *)this + 4),
      v17);
    if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
      McTemplateU0q_EventWriteTransfer(MS_PROVIDER_HFB_Context, EVENT_HFB_KEY_CREATION_SUCCESS, v13);
    if ( (unsigned int)dword_18013D150 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
    {
      v25[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        (__int64)&dword_18013D150,
        (__int64)byte_18012AE75);
    }
  }
  else
  {
    Logger::WriteNgcCreateUserIdKeyFailureEvent(v19, v12, v11, v10, (unsigned int)v16, UserSid);
    LODWORD(v18) = UserSid;
    LODWORD(v17) = 74;
    Logger::TraceError(
      L"%s: NgcCreateUserIdKey failed. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Flags: %lu, Error code: 0x%08x.",
      L"KeyManager::CreateUserKey",
      v19,
      *((_QWORD *)this + 2),
      *((_QWORD *)this + 3),
      *((_QWORD *)this + 4),
      v17,
      v18);
    if ( (Microsoft_Windows_HelloForBusinessEnableBits & 2) != 0 )
      McTemplateU0dq_EventWriteTransfer(v14, EVENT_HFB_KEY_CREATION_FAILURE, (unsigned int)UserSid, v13);
    if ( (unsigned int)dword_18013D150 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
    {
      LODWORD(v19) = UserSid;
      v25[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        (__int64)&dword_18013D150,
        (__int64)byte_18012AE01);
    }
    KeyManager::FreeUserKey(this);
  }
  if ( v23 )
    EventActivityIdControl(4u, &ActivityId);
  v22 = 2;
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
  {
    v25[0] = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_18013D150,
      (__int64)byte_18012ADCD);
  }
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v22);
  return (unsigned int)UserSid;
}

```

## disassembly

```asm
0x180081edc  mov     [rsp-8+arg_10], rbx
0x180081ee1  push    rbp
0x180081ee2  push    rsi
0x180081ee3  push    rdi
0x180081ee4  push    r13
0x180081ee6  push    r15
0x180081ee8  lea     rbp, [rsp-37h]
0x180081eed  sub     rsp, 0C0h
0x180081ef4  mov     rax, cs:__security_cookie
0x180081efb  xor     rax, rsp
0x180081efe  mov     [rbp+57h+var_30], rax
0x180081f02  mov     rbx, rcx
0x180081f05  mov     [rbp+57h+var_90], 0
0x180081f0d  lea     rcx, [rbp+57h+var_68]
0x180081f11  mov     [rbp+57h+var_88], 0
0x180081f18  mov     rsi, rdx
0x180081f1b  mov     [rbp+57h+var_68], 0
0x180081f22  mov     [rbp+57h+var_64], 0
0x180081f26  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x180081f2b  mov     eax, cs:dword_18013D150
0x180081f31  lea     r13, dword_18013D150
0x180081f38  cmp     eax, 5
0x180081f3b  jbe     short loc_180081F93
0x180081f3d  mov     rdx, 400000000000h
0x180081f47  mov     rcx, r13
0x180081f4a  call    _tlgKeywordOn
0x180081f4f  test    al, al
0x180081f51  jz      short loc_180081F93
0x180081f53  cmp     [rbp+57h+var_64], 0
0x180081f57  mov     [rbp+57h+var_40], 1000000h
0x180081f5f  jz      short loc_180081F74
0x180081f61  lea     rcx, [rbp+57h+ActivityId]; struct _GUID *
0x180081f65  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180081f6a  test    al, al
0x180081f6c  jnz     short loc_180081F74
0x180081f6e  lea     r9, [rbp+57h+ActivityId]
0x180081f72  jmp     short loc_180081F77
0x180081f74  xor     r9d, r9d
0x180081f77  lea     rax, [rbp+57h+var_40]
0x180081f7b  mov     rcx, r13
0x180081f7e  lea     r8, [rbp+57h+var_60]
0x180081f82  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180081f87  lea     rdx, byte_18012B08F
0x180081f8e  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180081f93  mov     r9d, 1
0x180081f99  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, r9b
0x180081fa0  jz      short loc_180081FBE
0x180081fa2  lea     rax, [rbp+57h+var_40]
0x180081fa6  lea     rdx, EVENT_HFB_KEY_CREATION_START
0x180081fad  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180081fb2  lea     rcx, MS_PROVIDER_HFB_Context
0x180081fb9  call    McGenEventWrite_EventWriteTransfer
0x180081fbe  call    cs:__imp_GetTickCount
0x180081fc4  mov     rcx, [rbx+10h]
0x180081fc8  lea     rdx, [rbp+57h+var_90]; unsigned __int16 **
0x180081fcc  mov     [rbp+57h+var_80], rcx
0x180081fd0  mov     r15d, eax
0x180081fd3  mov     rcx, [rbx+18h]
0x180081fd7  mov     [rbp+57h+var_78], rcx
0x180081fdb  mov     rcx, [rbx+20h]
0x180081fdf  mov     [rbp+57h+var_70], rcx
0x180081fe3  mov     rcx, rbx; this
0x180081fe6  call    ?GetUserSid@KeyManager@@AEAAJPEAPEAG@Z; KeyManager::GetUserSid(ushort * *)
0x180081feb  mov     edi, eax
0x180081fed  test    eax, eax
0x180081fef  js      loc_18008208F
0x180081ff5  mov     rcx, rbx; this
0x180081ff8  call    ?FreeUserKey@KeyManager@@AEAAXXZ; KeyManager::FreeUserKey(void)
0x180081ffd  mov     r9, [rbx+28h]
0x180082001  lea     rax, [rbx+30h]
0x180082005  mov     [rsp+0E0h+var_A0], rax
0x18008200a  lea     rcx, [rbx+48h]
0x18008200e  lea     rax, [rbp+57h+var_88]
0x180082012  mov     r8, rsi
0x180082015  mov     [rsp+0E0h+var_A8], rax
0x18008201a  lea     rdx, [rbx+40h]
0x18008201e  mov     [rsp+0E0h+var_B0], rcx
0x180082023  lea     rcx, [rbp+57h+var_80]
0x180082027  mov     qword ptr [rsp+0E0h+var_B8], rdx
0x18008202c  mov     rdx, [rbp+57h+var_90]
0x180082030  mov     [rsp+0E0h+var_C0], 4Ah ; 'J'; unsigned int
0x180082038  call    cs:__imp_NgcCreateUserIdKey
0x18008203e  mov     edi, eax
0x180082040  mov     eax, [rbp+57h+var_88]
0x180082043  mov     [rbx+50h], rax
0x180082047  test    edi, edi
0x180082049  jns     short loc_18008206A
0x18008204b  mov     r9d, edi
0x18008204e  lea     r8, aNgccreateuseri_0; "NgcCreateUserIdKey"
0x180082055  lea     rdx, aKeymanagerCrea; "KeyManager::CreateUserKey"
0x18008205c  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180082063  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180082068  jmp     short loc_18008208F
0x18008206a  mov     rdx, rsi; HWND
0x18008206d  mov     rcx, rbx; this
0x180082070  call    ?GetUserKeyAttestation@KeyManager@@AEAAJPEAUHWND__@@@Z; KeyManager::GetUserKeyAttestation(HWND__ *)
0x180082075  test    eax, eax
0x180082077  jns     short loc_18008208F
0x180082079  mov     r8d, eax
0x18008207c  lea     rdx, aKeymanagerCrea; "KeyManager::CreateUserKey"
0x180082083  lea     rcx, aSUnableToGetAt; "%s: Unable to get Attestation for NGC K"...
0x18008208a  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18008208f  call    cs:__imp_GetTickCount
0x180082095  mov     r9, [rbx+20h]; unsigned __int16 *
0x180082099  mov     ecx, eax
0x18008209b  mov     r8, [rbx+18h]; unsigned __int16 *
0x18008209f  sub     ecx, r15d
0x1800820a2  mov     eax, 10624DD3h
0x1800820a7  mul     ecx
0x1800820a9  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x1800820ad  mov     esi, edx
0x1800820af  mov     rdx, [rbx+10h]; unsigned __int16 *
0x1800820b3  shr     esi, 6
0x1800820b6  test    edi, edi
0x1800820b8  jns     loc_180082178
0x1800820be  mov     [rsp+0E0h+var_B8], edi; int
0x1800820c2  call    ?WriteNgcCreateUserIdKeyFailureEvent@Logger@@SAJPEBG000KJ@Z; Logger::WriteNgcCreateUserIdKeyFailureEvent(ushort const *,ushort const *,ushort const *,ushort const *,ulong,long)
0x1800820c7  mov     rax, [rbx+20h]
0x1800820cb  lea     rdx, aKeymanagerCrea; "KeyManager::CreateUserKey"
0x1800820d2  mov     r9, [rbx+10h]
0x1800820d6  lea     rcx, aSNgccreateuser_0; "%s: NgcCreateUserIdKey failed. SID: %s,"...
0x1800820dd  mov     r8, [rbp+57h+var_90]
0x1800820e1  mov     dword ptr [rsp+0E0h+var_A8], edi
0x1800820e5  mov     dword ptr [rsp+0E0h+var_B0], 4Ah ; 'J'
0x1800820ed  mov     qword ptr [rsp+0E0h+var_B8], rax
0x1800820f2  mov     rax, [rbx+18h]
0x1800820f6  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800820fb  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180082100  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 2
0x180082107  jz      short loc_18008211B
0x180082109  mov     r9d, esi
0x18008210c  lea     rdx, EVENT_HFB_KEY_CREATION_FAILURE
0x180082113  mov     r8d, edi
0x180082116  call    McTemplateU0dq_EventWriteTransfer
0x18008211b  mov     eax, cs:dword_18013D150
0x180082121  cmp     eax, 2
0x180082124  jbe     short loc_18008216B
0x180082126  mov     rdx, 400000000000h
0x180082130  mov     rcx, r13
0x180082133  call    _tlgKeywordOn
0x180082138  test    al, al
0x18008213a  jz      short loc_18008216B
0x18008213c  lea     rax, [rbp+57h+var_90]
0x180082140  mov     dword ptr [rbp+57h+var_90], edi
0x180082143  mov     qword ptr [rsp+0E0h+var_B8], rax
0x180082148  lea     rdx, byte_18012AE01
0x18008214f  lea     rax, [rbp+57h+var_40]
0x180082153  mov     [rbp+57h+var_40], 1000000h
0x18008215b  xor     r8d, r8d
0x18008215e  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180082163  mov     rcx, r13
0x180082166  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18008216b  mov     rcx, rbx; this
0x18008216e  call    ?FreeUserKey@KeyManager@@AEAAXXZ; KeyManager::FreeUserKey(void)
0x180082173  jmp     loc_180082218
0x180082178  call    ?WriteNgcCreateUserIdKeySuccessEvent@Logger@@SAJPEBG000K@Z; Logger::WriteNgcCreateUserIdKeySuccessEvent(ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x18008217d  mov     rax, [rbx+20h]
0x180082181  lea     rdx, aKeymanagerCrea; "KeyManager::CreateUserKey"
0x180082188  mov     r9, [rbx+10h]
0x18008218c  lea     rcx, aSNgccreateuser; "%s: NgcCreateUserIdKey succeeded. SID: "...
0x180082193  mov     r8, [rbp+57h+var_90]
0x180082197  mov     dword ptr [rsp+0E0h+var_B0], 4Ah ; 'J'
0x18008219f  mov     qword ptr [rsp+0E0h+var_B8], rax
0x1800821a4  mov     rax, [rbx+18h]
0x1800821a8  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800821ad  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800821b2  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 4
0x1800821b9  jz      short loc_1800821D1
0x1800821bb  mov     r8d, esi
0x1800821be  lea     rdx, EVENT_HFB_KEY_CREATION_SUCCESS
0x1800821c5  lea     rcx, MS_PROVIDER_HFB_Context
0x1800821cc  call    McTemplateU0q_EventWriteTransfer
0x1800821d1  mov     eax, cs:dword_18013D150
0x1800821d7  cmp     eax, 4
0x1800821da  jbe     short loc_180082218
0x1800821dc  mov     rdx, 400000000000h
0x1800821e6  mov     rcx, r13
0x1800821e9  call    _tlgKeywordOn
0x1800821ee  test    al, al
0x1800821f0  jz      short loc_180082218
0x1800821f2  lea     rax, [rbp+57h+var_40]
0x1800821f6  mov     [rbp+57h+var_40], 1000000h
0x1800821fe  xor     r9d, r9d
0x180082201  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180082206  xor     r8d, r8d
0x180082209  lea     rdx, byte_18012AE75
0x180082210  mov     rcx, r13
0x180082213  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180082218  cmp     [rbp+57h+var_64], 0
0x18008221c  jz      short loc_18008222D
0x18008221e  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180082222  mov     ecx, 4; ControlCode
0x180082227  call    cs:__imp_EventActivityIdControl
0x18008222d  mov     eax, cs:dword_18013D150
0x180082233  mov     [rbp+57h+var_68], 2
0x18008223a  cmp     eax, 5
0x18008223d  jbe     short loc_18008227C
0x18008223f  mov     rdx, 400000000000h
0x180082249  mov     rcx, r13
0x18008224c  call    _tlgKeywordOn
0x180082251  test    al, al
0x180082253  jz      short loc_18008227C
0x180082255  lea     rax, [rbp+57h+var_40]
0x180082259  mov     [rbp+57h+var_40], 1000000h
0x180082261  xor     r9d, r9d
0x180082264  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180082269  lea     r8, [rbp+57h+var_60]
0x18008226d  mov     rcx, r13
0x180082270  lea     rdx, byte_18012ADCD
0x180082277  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18008227c  lea     rcx, [rbp+57h+var_68]
0x180082280  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x180082285  mov     eax, edi
0x180082287  mov     rcx, [rbp+57h+var_30]
0x18008228b  xor     rcx, rsp; StackCookie
0x18008228e  call    __security_check_cookie
0x180082293  mov     rbx, [rsp+0E0h+arg_10]
0x18008229b  add     rsp, 0C0h
0x1800822a2  pop     r15
0x1800822a4  pop     r13
0x1800822a6  pop     rdi
0x1800822a7  pop     rsi
0x1800822a8  pop     rbp
0x1800822a9  retn
```
