# DeviceUpdateController::AsyncDeviceUpdateResponseCallback(DeviceUpdateHttpRequest *,STRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT *,long)

- ea: `0x1800650f0`
- end: `0x180065526`
- name: `?AsyncDeviceUpdateResponseCallback@DeviceUpdateController@@SAXPEAVDeviceUpdateHttpRequest@@PEAUSTRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT@@J@Z`
- size: `1078`
- prototype: `void __fastcall(struct DeviceUpdateHttpRequest *, struct STRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT *, int)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, installer_update`

## callees

- `0x1800012a4`
- `0x180001934`
- `0x1800084f4`
- `0x18000bac0`
- `0x1800204f0`
- `0x18003e3e0`
- `0x180042158`
- `0x180043ef8`
- `0x180044300`
- `0x180051604`
- `0x180055174`
- `0x180055194`
- `0x1800650f0`
- `0x18006552c`
- `0x1800658d8`
- `0x180066678`
- `0x180066938`
- `0x1800781ec`
- `0x18007c4c0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800653c0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800653c0`

## string_xrefs

- `0x1800652ca`: `%s: DeviceUpdateController::SaveAttribute failed with error code: 0x%08x. Attribute: "%s", Device ID: "%s".`
- `0x18006519e`: `DeviceUpdateController::AsyncDeviceUpdateResponseCallback`
- `0x18006520a`: `DeviceUpdateController::AsyncDeviceUpdateResponseCallback`
- `0x180065239`: `DeviceUpdateController::AsyncDeviceUpdateResponseCallback`
- `0x1800652c3`: `DeviceUpdateController::AsyncDeviceUpdateResponseCallback`
- `0x180065332`: `DeviceUpdateController::AsyncDeviceUpdateResponseCallback`
- `0x18006539e`: `DeviceUpdateController::AsyncDeviceUpdateResponseCallback`
- `0x1800654e2`: `DeviceUpdateController::AsyncDeviceUpdateResponseCallback`
- `0x1800651ff`: `%s: DeviceUpdateResponseParser::Parse failed with error code: 0x%08x`
- `0x180065339`: `%s: Device update callback succeeded. Attribute: "%s", Tenant ID: "%s", Device ID: "%s", Join type: %d, HTTP status: %lu, Server response body: "%s".`
- `0x1800653a5`: `%s: Device update callback failed with error code: 0x%08x. Attribute: "%s", Tenant ID: "%s", Device ID: "%s", Join type: %d, HTTP status: %lu, Server response body: "%s".`

## pseudocode

```c
void __fastcall DeviceUpdateController::AsyncDeviceUpdateResponseCallback(
        struct DeviceUpdateHttpRequest *a1,
        struct STRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT *a2,
        int a3)
{
  __int64 v6; // r14
  unsigned int v7; // r15d
  unsigned __int16 *v8; // rsi
  __int64 AttributeName; // r12
  unsigned int *v10; // rdi
  unsigned int v11; // r10d
  int v12; // eax
  __int64 v13; // r9
  void (*v14)(struct DeviceUpdateHttpRequest *, struct STRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT *, int); // rcx
  __int64 v15; // [rsp+28h] [rbp-D8h]
  __int64 v16; // [rsp+30h] [rbp-D0h]
  __int64 v17; // [rsp+30h] [rbp-D0h]
  __int64 v18; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v19; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v20[2]; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v21; // [rsp+90h] [rbp-70h] BYREF
  __int128 v22; // [rsp+98h] [rbp-68h] BYREF
  __int128 v23; // [rsp+A8h] [rbp-58h]
  __int128 v24; // [rsp+B8h] [rbp-48h]
  __int64 v25; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v26; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v27; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v28; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v29; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v30; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v31; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v32; // [rsp+100h] [rbp+0h] BYREF
  __int64 v33; // [rsp+108h] [rbp+8h] BYREF
  __int64 v34; // [rsp+110h] [rbp+10h] BYREF
  int v35; // [rsp+118h] [rbp+18h] BYREF
  char v36; // [rsp+11Ch] [rbp+1Ch]
  _BYTE v37[16]; // [rsp+120h] [rbp+20h] BYREF
  GUID ActivityId; // [rsp+130h] [rbp+30h] BYREF

  v35 = 0;
  v36 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v35);
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
  {
    *(_QWORD *)v20 = 0x1000000;
    if ( v36 )
      _tlgGuidIsZero(&ActivityId);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_18013D150,
      (__int64)byte_180129DB1);
  }
  Logger::TraceVerbose((wchar_t *)L"%s started", L"DeviceUpdateController::AsyncDeviceUpdateResponseCallback");
  v6 = *((_QWORD *)a2 + 2);
  v7 = *((_DWORD *)a1 + 35);
  v8 = 0;
  v19 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  if ( a3 >= 0 )
  {
    a3 = DeviceUpdateResponseParser::Parse(a1, (struct struct_dsreg_server_response *)&v22, &v19, v20);
    if ( a3 >= 0 )
    {
      a3 = ServerResponseParser::TranslateResponse((const struct struct_dsreg_server_response *)&v22);
      v8 = v19;
    }
    else
    {
      v8 = v19;
      Logger::TraceError(
        L"%s: DeviceUpdateResponseParser::Parse failed with error code: 0x%08x",
        L"DeviceUpdateController::AsyncDeviceUpdateResponseCallback",
        (unsigned int)a3);
    }
  }
  else
  {
    Logger::TraceError(
      L"%s: The transaction failed with error code: 0x%08x",
      L"DeviceUpdateController::AsyncDeviceUpdateResponseCallback",
      (unsigned int)a3);
  }
  if ( v7 >= 0x190 )
    Logger::TraceError(
      L"%s: The response http status %d is a failure. The resulting HRESULT is 0x%08x.",
      L"DeviceUpdateController::AsyncDeviceUpdateResponseCallback",
      v7,
      (unsigned int)a3);
  AttributeName = GetAttributeName(*(unsigned int *)(v6 + 188));
  v10 = (unsigned int *)(*(_QWORD *)(*(_QWORD *)(v6 + 176) + 8LL) + 336LL * *(unsigned int *)(v6 + 184));
  v12 = DeviceUpdateController::SaveAttribute(v6, v11, v10, a3, (__int64)&v22);
  if ( a3 < 0 )
  {
    if ( v12 < 0 )
      Logger::TraceError(
        L"%s: DeviceUpdateController::SaveAttribute failed with error code: 0x%08x. Attribute: \"%s\", Device ID: \"%s\".",
        L"DeviceUpdateController::AsyncDeviceUpdateResponseCallback",
        (unsigned int)v12,
        L"none",
        *((_QWORD *)v10 + 2));
  }
  else
  {
    a3 = v12;
    if ( v12 < 0 )
      Logger::TraceError(
        L"%s: DeviceUpdateController::SaveAttribute failed with error code: 0x%08x. Attribute: \"%s\", Device ID: \"%s\".",
        L"DeviceUpdateController::AsyncDeviceUpdateResponseCallback",
        (unsigned int)v12,
        AttributeName,
        *((_QWORD *)v10 + 2));
  }
  if ( a3 < 0 )
  {
    *((_DWORD *)a2 + 6) = a3;
    Logger::WriteDeviceUpdateAttributeCallbackFailureEvent(
      (unsigned int)a3,
      AttributeName,
      *((_QWORD *)v10 + 4),
      *((_QWORD *)v10 + 2),
      *v10,
      v7,
      v8,
      &v22);
    LODWORD(v18) = v7;
    LODWORD(v17) = *v10;
    Logger::TraceError(
      L"%s: Device update callback failed with error code: 0x%08x. Attribute: \"%s\", Tenant ID: \"%s\", Device ID: \"%s\""
       ", Join type: %d, HTTP status: %lu, Server response body: \"%s\".",
      L"DeviceUpdateController::AsyncDeviceUpdateResponseCallback",
      (unsigned int)a3,
      AttributeName,
      *((_QWORD *)v10 + 4),
      *((_QWORD *)v10 + 2),
      v17,
      v18,
      v8);
  }
  else
  {
    Logger::WriteDeviceUpdateAttributeCallbackSuccessEvent(
      AttributeName,
      *((_QWORD *)v10 + 4),
      *((_QWORD *)v10 + 2),
      *v10,
      v7,
      v22,
      *((_QWORD *)&v22 + 1),
      *((_QWORD *)&v24 + 1),
      v8);
    LODWORD(v16) = v7;
    LODWORD(v15) = *v10;
    Logger::TraceVerbose(
      (wchar_t *)L"%s: Device update callback succeeded. Attribute: \"%s\", Tenant ID: \"%s\", Device ID: \"%s\", Join typ"
                  "e: %d, HTTP status: %lu, Server response body: \"%s\".",
      L"DeviceUpdateController::AsyncDeviceUpdateResponseCallback",
      AttributeName,
      *((_QWORD *)v10 + 4),
      *((_QWORD *)v10 + 2),
      v15,
      v16,
      v8);
  }
  if ( v36 )
    EventActivityIdControl(4u, &ActivityId);
  v35 = 2;
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
  {
    v26 = v8;
    v27 = *((_QWORD *)&v24 + 1);
    v28 = v24;
    v29 = *((_QWORD *)&v23 + 1);
    v30 = *((_QWORD *)&v22 + 1);
    v21 = v7;
    v31 = v22;
    LODWORD(v19) = *v10;
    v32 = *((_QWORD *)v10 + 4);
    v33 = AttributeName;
    v20[0] = a3;
    v34 = 16779264;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)&dword_18013D150,
      (__int64)byte_180129C29,
      (__int64)v37,
      v13,
      (__int64)&v34,
      (__int64)v20,
      &v33,
      &v32,
      (__int64)&v19,
      &v31,
      (__int64)&v21,
      &v30,
      &v29,
      &v28,
      &v27,
      &v26);
  }
  operator delete(v8);
  ServerResponseParser::FreeServerResponseContent((struct struct_dsreg_server_response *)&v22);
  DeviceUpdateController::UpdateDeviceContinue(v14, a2);
  Logger::TraceVerbose((wchar_t *)L"%s finished", L"DeviceUpdateController::AsyncDeviceUpdateResponseCallback");
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v35);
}

```

## disassembly

```asm
0x1800650f0  mov     [rsp-8+arg_18], rbx
0x1800650f5  push    rbp
0x1800650f6  push    rsi
0x1800650f7  push    rdi
0x1800650f8  push    r12
0x1800650fa  push    r13
0x1800650fc  push    r14
0x1800650fe  push    r15
0x180065100  lea     rbp, [rsp-50h]
0x180065105  sub     rsp, 150h
0x18006510c  mov     rax, cs:__security_cookie
0x180065113  xor     rax, rsp
0x180065116  mov     [rbp+80h+var_40], rax
0x18006511a  mov     ebx, r8d
0x18006511d  mov     r13, rdx
0x180065120  mov     rdi, rcx
0x180065123  xor     r12d, r12d
0x180065126  mov     [rbp+80h+var_68], r12d
0x18006512a  mov     [rbp+80h+var_64], r12b
0x18006512e  lea     rcx, [rbp+80h+var_68]
0x180065132  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x180065137  mov     eax, cs:dword_18013D150
0x18006513d  cmp     eax, 5
0x180065140  jbe     short loc_18006519E
0x180065142  mov     rdx, 400000000000h
0x18006514c  lea     rcx, dword_18013D150
0x180065153  call    _tlgKeywordOn
0x180065158  test    al, al
0x18006515a  jz      short loc_18006519E
0x18006515c  mov     qword ptr [rbp+80h+var_F8], 1000000h
0x180065164  cmp     [rbp+80h+var_64], r12b
0x180065168  jz      short loc_18006517B
0x18006516a  lea     rcx, [rbp+80h+ActivityId]; struct _GUID *
0x18006516e  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180065173  test    al, al
0x180065175  lea     r9, [rbp+80h+ActivityId]
0x180065179  jz      short loc_18006517E
0x18006517b  mov     r9, r12
0x18006517e  lea     rax, [rbp+80h+var_F8]
0x180065182  mov     [rsp+180h+var_160], rax
0x180065187  lea     r8, [rbp+80h+var_60]
0x18006518b  lea     rdx, byte_180129DB1
0x180065192  lea     rcx, dword_18013D150
0x180065199  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18006519e  lea     rdx, aDeviceupdateco_0; "DeviceUpdateController::AsyncDeviceUpda"...
0x1800651a5  lea     rcx, aSStarted; "%s started"
0x1800651ac  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800651b1  mov     r14, [r13+10h]
0x1800651b5  mov     r15d, [rdi+8Ch]
0x1800651bc  mov     rsi, r12
0x1800651bf  mov     [rbp+80h+var_100], r12
0x1800651c3  xorps   xmm0, xmm0
0x1800651c6  xor     eax, eax
0x1800651c8  movups  [rbp+80h+var_E8], xmm0
0x1800651cc  movups  [rbp+80h+var_D8], xmm0
0x1800651d0  movups  [rbp+80h+var_C8], xmm0
0x1800651d4  mov     [rbp+80h+var_B8], rax
0x1800651d8  test    ebx, ebx
0x1800651da  jns     short loc_1800651E5
0x1800651dc  lea     rcx, aSTheTransactio; "%s: The transaction failed with error c"...
0x1800651e3  jmp     short loc_18006520A
0x1800651e5  lea     r9, [rbp+80h+var_F8]; unsigned int *
0x1800651e9  lea     r8, [rbp+80h+var_100]; unsigned __int16 **
0x1800651ed  lea     rdx, [rbp+80h+var_E8]; struct struct_dsreg_server_response *
0x1800651f1  mov     rcx, rdi; struct DeviceUpdateHttpRequest *
0x1800651f4  call    ?Parse@DeviceUpdateResponseParser@@SAJPEAVDeviceUpdateHttpRequest@@PEAUstruct_dsreg_server_response@@PEAPEAGPEAK@Z; DeviceUpdateResponseParser::Parse(DeviceUpdateHttpRequest *,struct_dsreg_server_response *,ushort * *,ulong *)
0x1800651f9  mov     ebx, eax
0x1800651fb  test    eax, eax
0x1800651fd  jns     short loc_18006521B
0x1800651ff  lea     rcx, aSDeviceupdater; "%s: DeviceUpdateResponseParser::Parse f"...
0x180065206  mov     rsi, [rbp+80h+var_100]
0x18006520a  lea     rdx, aDeviceupdateco_0; "DeviceUpdateController::AsyncDeviceUpda"...
0x180065211  mov     r8d, ebx
0x180065214  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180065219  jmp     short loc_18006522A
0x18006521b  lea     rcx, [rbp+80h+var_E8]; struct struct_dsreg_server_response *
0x18006521f  call    ?TranslateResponse@ServerResponseParser@@SAJAEBUstruct_dsreg_server_response@@@Z; ServerResponseParser::TranslateResponse(struct_dsreg_server_response const &)
0x180065224  mov     ebx, eax
0x180065226  mov     rsi, [rbp+80h+var_100]
0x18006522a  cmp     r15d, 190h
0x180065231  jb      short loc_18006524C
0x180065233  mov     r9d, ebx
0x180065236  mov     r8d, r15d
0x180065239  lea     rdx, aDeviceupdateco_0; "DeviceUpdateController::AsyncDeviceUpda"...
0x180065240  lea     rcx, aSTheResponseHt_0; "%s: The response http status %d is a fa"...
0x180065247  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006524c  mov     r10d, [r14+0BCh]
0x180065253  mov     ecx, r10d
0x180065256  call    GetAttributeName
0x18006525b  mov     r12, rax
0x18006525e  mov     edx, [r14+0B8h]
0x180065265  imul    rdi, rdx, 150h
0x18006526c  mov     rdx, [r14+0B0h]
0x180065273  add     rdi, [rdx+8]
0x180065277  lea     rax, [rbp+80h+var_E8]
0x18006527b  mov     r9d, ebx
0x18006527e  mov     r8, rdi
0x180065281  mov     edx, r10d
0x180065284  mov     rcx, r14
0x180065287  mov     [rsp+180h+var_160], rax
0x18006528c  call    ?SaveAttribute@DeviceUpdateController@@AEAAJW4_DSREG_DEVICE_ATTRIBUTES@@PEAU_DSREG_ACCOUNT_INFO_2@@JPEBUstruct_dsreg_server_response@@@Z; DeviceUpdateController::SaveAttribute(_DSREG_DEVICE_ATTRIBUTES,_DSREG_ACCOUNT_INFO_2 *,long,struct_dsreg_server_response const *)
0x180065291  test    ebx, ebx
0x180065293  js      short loc_1800652AC
0x180065295  mov     ebx, eax
0x180065297  test    eax, eax
0x180065299  jns     short loc_1800652D6
0x18006529b  mov     rax, [rdi+10h]
0x18006529f  mov     [rsp+180h+var_160], rax
0x1800652a4  mov     r9, r12
0x1800652a7  mov     r8d, ebx
0x1800652aa  jmp     short loc_1800652C3
0x1800652ac  test    eax, eax
0x1800652ae  jns     short loc_1800652D6
0x1800652b0  mov     rcx, [rdi+10h]
0x1800652b4  mov     [rsp+180h+var_160], rcx
0x1800652b9  lea     r9, aNone; "none"
0x1800652c0  mov     r8d, eax
0x1800652c3  lea     rdx, aDeviceupdateco_0; "DeviceUpdateController::AsyncDeviceUpda"...
0x1800652ca  lea     rcx, aSDeviceupdatec_0; "%s: DeviceUpdateController::SaveAttribu"...
0x1800652d1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800652d6  test    ebx, ebx
0x1800652d8  js      short loc_180065347
0x1800652da  mov     [rsp+180h+var_140], rsi
0x1800652df  mov     rax, qword ptr [rbp+80h+var_C8+8]
0x1800652e3  mov     [rsp+180h+var_148], rax
0x1800652e8  mov     rax, qword ptr [rbp+80h+var_E8+8]
0x1800652ec  mov     qword ptr [rsp+180h+var_158+8], rax
0x1800652f1  mov     rax, qword ptr [rbp+80h+var_E8]
0x1800652f5  mov     qword ptr [rsp+180h+var_158], rax
0x1800652fa  mov     dword ptr [rsp+180h+var_160], r15d
0x1800652ff  mov     r9d, [rdi]
0x180065302  mov     r8, [rdi+10h]
0x180065306  mov     rdx, [rdi+20h]
0x18006530a  mov     rcx, r12
0x18006530d  call    ?WriteDeviceUpdateAttributeCallbackSuccessEvent@Logger@@SAJPEBG00W4_DSREG_JOIN_TYPE@@K0000@Z; Logger::WriteDeviceUpdateAttributeCallbackSuccessEvent(ushort const *,ushort const *,ushort const *,_DSREG_JOIN_TYPE,ulong,ushort const *,ushort const *,ushort const *,ushort const *)
0x180065312  mov     [rsp+180h+var_148], rsi
0x180065317  mov     dword ptr [rsp+180h+var_158+8], r15d
0x18006531c  mov     eax, [rdi]
0x18006531e  mov     dword ptr [rsp+180h+var_158], eax
0x180065322  mov     rax, [rdi+10h]
0x180065326  mov     [rsp+180h+var_160], rax
0x18006532b  mov     r9, [rdi+20h]
0x18006532f  mov     r8, r12
0x180065332  lea     rdx, aDeviceupdateco_0; "DeviceUpdateController::AsyncDeviceUpda"...
0x180065339  lea     rcx, aSDeviceUpdateC_0; "%s: Device update callback succeeded. A"...
0x180065340  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180065345  jmp     short loc_1800653B1
0x180065347  mov     [r13+18h], ebx
0x18006534b  lea     rax, [rbp+80h+var_E8]
0x18006534f  mov     [rsp+180h+var_148], rax
0x180065354  mov     qword ptr [rsp+180h+var_158+8], rsi
0x180065359  mov     dword ptr [rsp+180h+var_158], r15d
0x18006535e  mov     eax, [rdi]
0x180065360  mov     dword ptr [rsp+180h+var_160], eax
0x180065364  mov     r9, [rdi+10h]
0x180065368  mov     r8, [rdi+20h]
0x18006536c  mov     rdx, r12
0x18006536f  mov     ecx, ebx
0x180065371  call    ?WriteDeviceUpdateAttributeCallbackFailureEvent@Logger@@SAJJPEBG00W4_DSREG_JOIN_TYPE@@K0AEBUstruct_dsreg_server_response@@@Z; Logger::WriteDeviceUpdateAttributeCallbackFailureEvent(long,ushort const *,ushort const *,ushort const *,_DSREG_JOIN_TYPE,ulong,ushort const *,struct_dsreg_server_response const &)
0x180065376  mov     [rsp+180h+var_140], rsi
0x18006537b  mov     dword ptr [rsp+180h+var_148], r15d
0x180065380  mov     eax, [rdi]
0x180065382  mov     dword ptr [rsp+180h+var_158+8], eax
0x180065386  mov     rax, [rdi+10h]
0x18006538a  mov     qword ptr [rsp+180h+var_158], rax
0x18006538f  mov     rax, [rdi+20h]
0x180065393  mov     [rsp+180h+var_160], rax
0x180065398  mov     r9, r12
0x18006539b  mov     r8d, ebx
0x18006539e  lea     rdx, aDeviceupdateco_0; "DeviceUpdateController::AsyncDeviceUpda"...
0x1800653a5  lea     rcx, aSDeviceUpdateC; "%s: Device update callback failed with "...
0x1800653ac  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800653b1  cmp     [rbp+80h+var_64], 0
0x1800653b5  jz      short loc_1800653C6
0x1800653b7  lea     rdx, [rbp+80h+ActivityId]; ActivityId
0x1800653bb  mov     ecx, 4; ControlCode
0x1800653c0  call    cs:__imp_EventActivityIdControl
0x1800653c6  mov     [rbp+80h+var_68], 2
0x1800653cd  mov     eax, cs:dword_18013D150
0x1800653d3  cmp     eax, 5
0x1800653d6  jbe     loc_1800654C9
0x1800653dc  mov     rdx, 400000000000h
0x1800653e6  lea     rcx, dword_18013D150
0x1800653ed  call    _tlgKeywordOn
0x1800653f2  test    al, al
0x1800653f4  jz      loc_1800654C9
0x1800653fa  mov     [rbp+80h+var_B0], rsi
0x1800653fe  mov     rax, qword ptr [rbp+80h+var_C8+8]
0x180065402  mov     [rbp+80h+var_A8], rax
0x180065406  mov     rax, qword ptr [rbp+80h+var_C8]
0x18006540a  mov     [rbp+80h+var_A0], rax
0x18006540e  mov     rax, qword ptr [rbp+80h+var_D8+8]
0x180065412  mov     [rbp+80h+var_98], rax
0x180065416  mov     rax, qword ptr [rbp+80h+var_E8+8]
0x18006541a  mov     [rbp+80h+var_90], rax
0x18006541e  mov     [rbp+80h+var_F0], r15d
0x180065422  mov     rax, qword ptr [rbp+80h+var_E8]
0x180065426  mov     [rbp+80h+var_88], rax
0x18006542a  mov     eax, [rdi]
0x18006542c  mov     dword ptr [rbp+80h+var_100], eax
0x18006542f  mov     rax, [rdi+20h]
0x180065433  mov     [rbp+80h+var_80], rax
0x180065437  mov     [rbp+80h+var_78], r12
0x18006543b  mov     [rbp+80h+var_F8], ebx
0x18006543e  mov     [rbp+80h+var_70], 1000800h
0x180065446  lea     rax, [rbp+80h+var_B0]
0x18006544a  mov     [rsp+180h+var_108], rax
0x18006544f  lea     rax, [rbp+80h+var_A8]
0x180065453  mov     [rsp+180h+var_110], rax
0x180065458  lea     rax, [rbp+80h+var_A0]
0x18006545c  mov     [rsp+180h+var_118], rax
0x180065461  lea     rax, [rbp+80h+var_98]
0x180065465  mov     [rsp+180h+var_120], rax
0x18006546a  lea     rax, [rbp+80h+var_90]
0x18006546e  mov     [rsp+180h+var_128], rax
0x180065473  lea     rax, [rbp+80h+var_F0]
0x180065477  mov     [rsp+180h+var_130], rax
0x18006547c  lea     rax, [rbp+80h+var_88]
0x180065480  mov     [rsp+180h+var_138], rax
0x180065485  lea     rax, [rbp+80h+var_100]
0x180065489  mov     [rsp+180h+var_140], rax
0x18006548e  lea     rax, [rbp+80h+var_80]
0x180065492  mov     [rsp+180h+var_148], rax
0x180065497  lea     rax, [rbp+80h+var_78]
0x18006549b  mov     qword ptr [rsp+180h+var_158+8], rax
0x1800654a0  lea     rax, [rbp+80h+var_F8]
0x1800654a4  mov     qword ptr [rsp+180h+var_158], rax
0x1800654a9  lea     rax, [rbp+80h+var_70]
0x1800654ad  mov     [rsp+180h+var_160], rax
0x1800654b2  lea     r8, [rbp+80h+var_60]
0x1800654b6  lea     rdx, byte_180129C29
0x1800654bd  lea     rcx, dword_18013D150
0x1800654c4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U2@U3@U2@U3@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@545455555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800654c9  mov     rcx, rsi; Block
0x1800654cc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800654d1  lea     rcx, [rbp+80h+var_E8]; struct struct_dsreg_server_response *
0x1800654d5  call    ?FreeServerResponseContent@ServerResponseParser@@SAXPEAUstruct_dsreg_server_response@@@Z; ServerResponseParser::FreeServerResponseContent(struct_dsreg_server_response *)
0x1800654da  mov     rdx, r13; struct STRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT *
0x1800654dd  call    ?UpdateDeviceContinue@DeviceUpdateController@@CAXP6AXPEAVDeviceUpdateHttpRequest@@PEAUSTRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT@@J@Z1@Z; DeviceUpdateController::UpdateDeviceContinue(void (*)(DeviceUpdateHttpRequest *,STRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT *,long),STRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT *)
0x1800654e2  lea     rdx, aDeviceupdateco_0; "DeviceUpdateController::AsyncDeviceUpda"...
0x1800654e9  lea     rcx, aSFinished; "%s finished"
0x1800654f0  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800654f5  nop
0x1800654f6  lea     rcx, [rbp+80h+var_68]
0x1800654fa  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x1800654ff  mov     rcx, [rbp+80h+var_40]
0x180065503  xor     rcx, rsp; StackCookie
0x180065506  call    __security_check_cookie
0x18006550b  mov     rbx, [rsp+180h+arg_18]
0x180065513  add     rsp, 150h
0x18006551a  pop     r15
0x18006551c  pop     r14
0x18006551e  pop     r13
0x180065520  pop     r12
0x180065522  pop     rdi
0x180065523  pop     rsi
0x180065524  pop     rbp
0x180065525  retn
```
