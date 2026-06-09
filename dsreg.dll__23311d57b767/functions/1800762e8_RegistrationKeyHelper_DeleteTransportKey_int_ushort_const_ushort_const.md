# RegistrationKeyHelper::DeleteTransportKey(int,ushort const *,ushort const *)

- ea: `0x1800762e8`
- end: `0x1800765b2`
- name: `?DeleteTransportKey@RegistrationKeyHelper@@SAJHPEBG0@Z`
- size: `714`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800543ec`
- `0x1800565d8`
- `0x18005693c`
- `0x180056ccc`

## callees

- `0x1800011ec`
- `0x1800012a4`
- `0x1800084f4`
- `0x18000bac0`
- `0x180012948`
- `0x180012eb8`
- `0x1800204f0`
- `0x180031f44`
- `0x1800334e0`
- `0x18003e350`
- `0x180044300`
- `0x180055174`
- `0x1800762e8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18007651b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18007651b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076473`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076473`
- `popkeycli!NgcDeleteSymmetricPopKeyTransportKey` at `0x1800763da`
- `popkeycli!NgcDeleteSymmetricPopKeyTransportKey` at `0x1800763da`

## string_xrefs

- `0x180076407`: `RegistrationKeyHelper::DeleteTransportKey`
- `0x180076442`: `RegistrationKeyHelper::DeleteTransportKey`
- `0x18007656f`: `RegistrationKeyHelper::DeleteTransportKey`
- `0x18007644d`: `%s: Transport key deleted. NgcDeleteSymmetricPopKeyTransportKey succeeded. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Flags: %lu.`
- `0x180076412`: `%s: Cannot delete transport key. NgcDeleteSymmetricPopKeyTransportKey failed with error code 0x%08x. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Flags: %lu.`

## pseudocode

```c
__int64 __fastcall RegistrationKeyHelper::DeleteTransportKey(int a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned int v4; // edi
  int CurrentUserSid; // ebx
  int v6; // eax
  unsigned int v8; // [rsp+30h] [rbp-29h]
  unsigned int v9; // [rsp+38h] [rbp-21h]
  HLOCAL hMem; // [rsp+40h] [rbp-19h] BYREF
  __int64 v11; // [rsp+48h] [rbp-11h]
  unsigned __int16 *v12; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int16 *v13; // [rsp+58h] [rbp-1h]
  unsigned __int16 *v14; // [rsp+60h] [rbp+7h]
  __int64 v15; // [rsp+68h] [rbp+Fh]
  int v16; // [rsp+70h] [rbp+17h] BYREF
  char v17; // [rsp+74h] [rbp+1Bh]
  GUID ActivityId; // [rsp+88h] [rbp+2Fh] BYREF

  hMem = 0;
  v13 = a2;
  v12 = L"login.windows.net";
  v4 = a1 != 0 ? 2 : 0;
  v16 = 0;
  v17 = 0;
  if ( a1 )
    a3 = 0;
  v14 = a3;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v16);
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x200000000000LL) )
  {
    v11 = 0x1000000;
    if ( v17 )
      _tlgGuidIsZero(&ActivityId);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_18013D150,
      (__int64)&word_18012A41E);
  }
  if ( a1 || (CurrentUserSid = GetCurrentUserSid((LPWSTR *)&hMem), CurrentUserSid >= 0) )
  {
    v6 = NgcDeleteSymmetricPopKeyTransportKey(&v12, hMem, v4);
    CurrentUserSid = v6;
    if ( v6 >= 0 )
    {
      v8 = v4;
      Logger::TraceInformation(
        L"%s: Transport key deleted. NgcDeleteSymmetricPopKeyTransportKey succeeded. SID: %s, IDP domain: %s, Tenant domai"
         "n: %s, User ID: %s, Flags: %lu.",
        L"RegistrationKeyHelper::DeleteTransportKey",
        hMem,
        v12,
        v13,
        v14,
        v8);
    }
    else
    {
      Logger::WriteNgcDeleteTransportKeyFailureEvent((const unsigned __int16 *)hMem, v12, v13, v14, v4, v6);
      v9 = v4;
      Logger::TraceError(
        L"%s: Cannot delete transport key. NgcDeleteSymmetricPopKeyTransportKey failed with error code 0x%08x. SID: %s, ID"
         "P domain: %s, Tenant domain: %s, User ID: %s, Flags: %lu.",
        L"RegistrationKeyHelper::DeleteTransportKey",
        (unsigned int)CurrentUserSid,
        hMem,
        v12,
        v13,
        v14,
        v9);
    }
  }
  LocalFree(hMem);
  if ( CurrentUserSid < 0 )
  {
    if ( (unsigned int)dword_18013D150 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x200000000000LL) )
    {
      LODWORD(v11) = CurrentUserSid;
      v15 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        (__int64)&dword_18013D150,
        (__int64)byte_18012A335);
    }
  }
  else if ( (unsigned int)dword_18013D150 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x200000000000LL) )
  {
    v11 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_18013D150,
      (__int64)word_18012A1AA);
  }
  if ( v17 )
    EventActivityIdControl(4u, &ActivityId);
  v16 = 2;
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x200000000000LL) )
  {
    v15 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_18013D150,
      (__int64)byte_18012A3AB);
  }
  Logger::TraceVerbose(
    (wchar_t *)L"%s - hr: 0x%08x",
    L"RegistrationKeyHelper::DeleteTransportKey",
    (unsigned int)CurrentUserSid);
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>((__int64)&v16);
  return (unsigned int)CurrentUserSid;
}

```

## disassembly

```asm
0x1800762e8  mov     [rsp-8+arg_0], rbx
0x1800762ed  mov     [rsp-8+arg_18], rdi
0x1800762f2  push    rbp
0x1800762f3  push    r14
0x1800762f5  push    r15
0x1800762f7  lea     rbp, [rsp-47h]
0x1800762fc  sub     rsp, 0A0h
0x180076303  mov     rax, cs:__security_cookie
0x18007630a  xor     rax, rsp
0x18007630d  mov     [rbp+57h+var_18], rax
0x180076311  mov     eax, ecx
0x180076313  mov     [rbp+57h+hMem], 0
0x18007631b  neg     eax
0x18007631d  mov     [rbp+57h+var_58], rdx
0x180076321  lea     rax, aLoginWindowsNe; "login.windows.net"
0x180076328  mov     ebx, ecx
0x18007632a  sbb     edi, edi
0x18007632c  mov     [rbp+57h+var_60], rax
0x180076330  xor     eax, eax
0x180076332  and     edi, 2
0x180076335  test    ecx, ecx
0x180076337  mov     [rbp+57h+var_40], eax
0x18007633a  lea     rcx, [rbp+57h+var_40]
0x18007633e  mov     [rbp+57h+var_3C], al
0x180076341  cmovnz  r8, rax
0x180076345  mov     [rbp+57h+var_50], r8
0x180076349  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18007634e  mov     eax, cs:dword_18013D150
0x180076354  lea     r14, dword_18013D150
0x18007635b  mov     r15d, 1000000h
0x180076361  cmp     eax, 5
0x180076364  jbe     short loc_1800763B8
0x180076366  mov     rdx, 200000000000h
0x180076370  mov     rcx, r14
0x180076373  call    _tlgKeywordOn
0x180076378  test    al, al
0x18007637a  jz      short loc_1800763B8
0x18007637c  cmp     [rbp+57h+var_3C], 0
0x180076380  mov     [rbp+57h+var_68], r15
0x180076384  jz      short loc_180076399
0x180076386  lea     rcx, [rbp+57h+ActivityId]; struct _GUID *
0x18007638a  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18007638f  test    al, al
0x180076391  jnz     short loc_180076399
0x180076393  lea     r9, [rbp+57h+ActivityId]
0x180076397  jmp     short loc_18007639C
0x180076399  xor     r9d, r9d
0x18007639c  lea     rax, [rbp+57h+var_68]
0x1800763a0  mov     rcx, r14
0x1800763a3  lea     r8, [rbp+57h+var_38]
0x1800763a7  mov     qword ptr [rsp+0B0h+var_90], rax
0x1800763ac  lea     rdx, word_18012A41E
0x1800763b3  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800763b8  test    ebx, ebx
0x1800763ba  jnz     short loc_1800763CF
0x1800763bc  lea     rcx, [rbp+57h+hMem]; StringSid
0x1800763c0  call    ?GetCurrentUserSid@@YAJPEAPEAG@Z; GetCurrentUserSid(ushort * *)
0x1800763c5  mov     ebx, eax
0x1800763c7  test    eax, eax
0x1800763c9  js      loc_18007646F
0x1800763cf  mov     rdx, [rbp+57h+hMem]
0x1800763d3  lea     rcx, [rbp+57h+var_60]
0x1800763d7  mov     r8d, edi
0x1800763da  call    cs:__imp_NgcDeleteSymmetricPopKeyTransportKey
0x1800763e0  mov     ebx, eax
0x1800763e2  test    eax, eax
0x1800763e4  jns     short loc_18007643E
0x1800763e6  mov     r9, [rbp+57h+var_50]; unsigned __int16 *
0x1800763ea  mov     r8, [rbp+57h+var_58]; unsigned __int16 *
0x1800763ee  mov     rdx, [rbp+57h+var_60]; unsigned __int16 *
0x1800763f2  mov     rcx, [rbp+57h+hMem]; unsigned __int16 *
0x1800763f6  mov     [rsp+0B0h+var_88], eax; int
0x1800763fa  mov     [rsp+0B0h+var_90], edi; unsigned int
0x1800763fe  call    ?WriteNgcDeleteTransportKeyFailureEvent@Logger@@SAJPEBG000KJ@Z; Logger::WriteNgcDeleteTransportKeyFailureEvent(ushort const *,ushort const *,ushort const *,ushort const *,ulong,long)
0x180076403  mov     rax, [rbp+57h+var_50]
0x180076407  lea     rdx, aRegistrationke_15; "RegistrationKeyHelper::DeleteTransportK"...
0x18007640e  mov     r9, [rbp+57h+hMem]
0x180076412  lea     rcx, aSCannotDeleteT; "%s: Cannot delete transport key. NgcDel"...
0x180076419  mov     [rsp+0B0h+var_78], edi
0x18007641d  mov     r8d, ebx
0x180076420  mov     [rsp+0B0h+var_80], rax
0x180076425  mov     rax, [rbp+57h+var_58]
0x180076429  mov     qword ptr [rsp+0B0h+var_88], rax
0x18007642e  mov     rax, [rbp+57h+var_60]
0x180076432  mov     qword ptr [rsp+0B0h+var_90], rax
0x180076437  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007643c  jmp     short loc_18007646F
0x18007643e  mov     rax, [rbp+57h+var_50]
0x180076442  lea     rdx, aRegistrationke_15; "RegistrationKeyHelper::DeleteTransportK"...
0x180076449  mov     r9, [rbp+57h+var_60]
0x18007644d  lea     rcx, aSTransportKeyD; "%s: Transport key deleted. NgcDeleteSym"...
0x180076454  mov     r8, [rbp+57h+hMem]
0x180076458  mov     dword ptr [rsp+0B0h+var_80], edi
0x18007645c  mov     qword ptr [rsp+0B0h+var_88], rax
0x180076461  mov     rax, [rbp+57h+var_58]
0x180076465  mov     qword ptr [rsp+0B0h+var_90], rax
0x18007646a  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18007646f  mov     rcx, [rbp+57h+hMem]; hMem
0x180076473  call    cs:__imp_LocalFree
0x180076479  mov     eax, cs:dword_18013D150
0x18007647f  test    ebx, ebx
0x180076481  js      short loc_1800764C6
0x180076483  cmp     eax, 4
0x180076486  jbe     loc_18007650C
0x18007648c  mov     rdx, 200000000000h
0x180076496  mov     rcx, r14
0x180076499  call    _tlgKeywordOn
0x18007649e  test    al, al
0x1800764a0  jz      short loc_18007650C
0x1800764a2  lea     rax, [rbp+57h+var_68]
0x1800764a6  mov     [rbp+57h+var_68], r15
0x1800764aa  xor     r9d, r9d
0x1800764ad  mov     qword ptr [rsp+0B0h+var_90], rax
0x1800764b2  xor     r8d, r8d
0x1800764b5  lea     rdx, word_18012A1AA
0x1800764bc  mov     rcx, r14
0x1800764bf  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800764c4  jmp     short loc_18007650C
0x1800764c6  cmp     eax, 2
0x1800764c9  jbe     short loc_18007650C
0x1800764cb  mov     rdx, 200000000000h
0x1800764d5  mov     rcx, r14
0x1800764d8  call    _tlgKeywordOn
0x1800764dd  test    al, al
0x1800764df  jz      short loc_18007650C
0x1800764e1  lea     rax, [rbp+57h+var_68]
0x1800764e5  mov     dword ptr [rbp+57h+var_68], ebx
0x1800764e8  mov     qword ptr [rsp+0B0h+var_88], rax
0x1800764ed  lea     rdx, byte_18012A335
0x1800764f4  lea     rax, [rbp+57h+var_48]
0x1800764f8  mov     [rbp+57h+var_48], r15
0x1800764fc  xor     r8d, r8d
0x1800764ff  mov     qword ptr [rsp+0B0h+var_90], rax
0x180076504  mov     rcx, r14
0x180076507  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18007650c  cmp     [rbp+57h+var_3C], 0
0x180076510  jz      short loc_180076521
0x180076512  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180076516  mov     ecx, 4; ControlCode
0x18007651b  call    cs:__imp_EventActivityIdControl
0x180076521  mov     eax, cs:dword_18013D150
0x180076527  mov     [rbp+57h+var_40], 2
0x18007652e  cmp     eax, 5
0x180076531  jbe     short loc_18007656C
0x180076533  mov     rdx, 200000000000h
0x18007653d  mov     rcx, r14
0x180076540  call    _tlgKeywordOn
0x180076545  test    al, al
0x180076547  jz      short loc_18007656C
0x180076549  lea     rax, [rbp+57h+var_48]
0x18007654d  mov     [rbp+57h+var_48], r15
0x180076551  xor     r9d, r9d
0x180076554  mov     qword ptr [rsp+0B0h+var_90], rax
0x180076559  lea     r8, [rbp+57h+var_38]
0x18007655d  mov     rcx, r14
0x180076560  lea     rdx, byte_18012A3AB
0x180076567  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18007656c  mov     r8d, ebx
0x18007656f  lea     rdx, aRegistrationke_15; "RegistrationKeyHelper::DeleteTransportK"...
0x180076576  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18007657d  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180076582  lea     rcx, [rbp+57h+var_40]
0x180076586  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(void)
0x18007658b  mov     eax, ebx
0x18007658d  mov     rcx, [rbp+57h+var_18]
0x180076591  xor     rcx, rsp; StackCookie
0x180076594  call    __security_check_cookie
0x180076599  lea     r11, [rsp+0B0h+var_10]
0x1800765a1  mov     rbx, [r11+20h]
0x1800765a5  mov     rdi, [r11+38h]
0x1800765a9  mov     rsp, r11
0x1800765ac  pop     r15
0x1800765ae  pop     r14
0x1800765b0  pop     rbp
0x1800765b1  retn
```
