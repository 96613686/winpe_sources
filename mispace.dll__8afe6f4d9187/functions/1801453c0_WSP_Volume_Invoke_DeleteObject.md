# WSP_Volume_Invoke_DeleteObject

- ea: `0x1801453c0`
- end: `0x1801459c0`
- name: `WSP_Volume_Invoke_DeleteObject`
- size: `1536`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011b0`
- `0x1800014ec`
- `0x1800015b8`
- `0x180001970`
- `0x1800045d0`
- `0x180004bfc`
- `0x180006290`
- `0x180006cf4`
- `0x18000b964`
- `0x18000bb68`
- `0x18000cd44`
- `0x18000cd6c`
- `0x180014000`
- `0x180014720`
- `0x180015500`
- `0x1800156c0`
- `0x1800158d0`
- `0x180015b40`
- `0x180015c60`
- `0x180016480`
- `0x1800165f0`
- `0x180016c80`
- `0x18001afd0`
- `0x1800234e4`
- `0x180055ec4`
- `0x18011efcc`
- `0x180138120`
- `0x1801453c0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180145433`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180145485`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014564e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180145433`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180145485`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014564e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18014545e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18014545e`

## string_xrefs

- `0x180145491`: `WSP_Volume_Invoke_DeleteObject`
- `0x18014560a`: `WSP_Volume_Invoke_DeleteObject`
- `0x180145822`: `WSP_Volume_Invoke_DeleteObject`
- `0x180145560`: `DeleteVolume`
- `0x1801458f8`: `DeleteVolume`
- `0x180145980`: `DeleteVolume`

## pseudocode

```c
ULONG __fastcall WSP_Volume_Invoke_DeleteObject(
        __int64 a1,
        MI_Context *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        const struct _MI_ConstStringField *a6,
        void *a7)
{
  int v9; // r15d
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned __int16 **v12; // rsi
  unsigned __int16 *v13; // rdx
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  char IsRemoteInstance; // al
  unsigned __int16 *v21; // rcx
  unsigned int SubsystemType; // edi
  int SubsystemVersion; // r14d
  __int64 v24; // rcx
  enum _MI_Result v25; // eax
  __int64 v26; // r8
  __int64 v27; // r9
  enum _MI_Result v28; // edi
  __int64 v29; // rcx
  char *v30; // rdx
  MI_Uint32 v31; // eax
  __int64 v32; // r8
  __int64 v33; // r9
  unsigned __int16 *v34; // rax
  unsigned __int32 v35; // [rsp+70h] [rbp-90h] BYREF
  MI_Uint32 v36; // [rsp+74h] [rbp-8Ch] BYREF
  int IsRemoteRequest; // [rsp+78h] [rbp-88h]
  int v38; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v39; // [rsp+80h] [rbp-80h] BYREF
  const char *v40; // [rsp+88h] [rbp-78h] BYREF
  __int64 v41; // [rsp+90h] [rbp-70h] BYREF
  const char *v42; // [rsp+98h] [rbp-68h] BYREF
  const char *v43; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v44; // [rsp+A8h] [rbp-58h] BYREF
  const char *v45; // [rsp+B0h] [rbp-50h] BYREF
  const char *v46; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v47; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v48; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v49; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v50; // [rsp+E0h] [rbp-20h] BYREF
  MI_Value value; // [rsp+E8h] [rbp-18h] BYREF
  GUID ActivityId; // [rsp+110h] [rbp+10h] BYREF
  __int128 v53; // [rsp+120h] [rbp+20h] BYREF
  int v54; // [rsp+130h] [rbp+30h]
  GUID v55; // [rsp+138h] [rbp+38h]
  GUID v56; // [rsp+148h] [rbp+48h] BYREF
  MI_Instance instance; // [rsp+160h] [rbp+60h] BYREF
  struct _MI_ConstUint32Field v58; // [rsp+1A0h] [rbp+A0h] BYREF

  memset(&value, 0, sizeof(value));
  v44 = a5;
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  v9 = 0;
  if ( MI_Context_GetCustomOption(a2, L"ActivityId", 0, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v55 = ActivityId;
  v56 = ActivityId;
  EventActivityIdControl(4u, &v56);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v39 = 1916;
    v42 = "WSP_Volume_Invoke_DeleteObject";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"WSP_Volume_Invoke_DeleteObject",
      (__int64)&dword_18034EA3C,
      v10,
      v11,
      &v42);
  }
  v42 = 0;
  v38 = 0;
  memset_0(&instance, 0, 0x68u);
  CSmTimer::CSmTimer((CSmTimer *)&v47);
  CSmTimer::Start((CSmTimer *)&v47);
  v12 = (unsigned __int16 **)&a6[4];
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( a6[4].exists && (unsigned __int8)WspIsRemoteInstance(*v12) )
    v9 = 1;
  v13 = *v12;
  v39 = 0;
  v14 = WspProviderEnter(a2, (__int64)v13, 1u, &v39);
  v15 = v14;
  if ( v14 )
    goto LABEL_9;
  IsRemoteInstance = WspIsRemoteInstance(*v12);
  v21 = *v12;
  if ( IsRemoteInstance )
  {
    v15 = (unsigned int)WspInvokeRemoteMethod(a2, a4, *v12, a5, a7);
LABEL_9:
    if ( a2 && a2->ft )
      ((void (__fastcall *)(MI_Context *, __int64))a2->ft->PostResult)(a2, v15);
    goto LABEL_12;
  }
  v53 = 0;
  v54 = 0;
  LODWORD(v41) = 0;
  SubsystemType = WspGetSubsystemType(v21);
  SubsystemVersion = _GetSubsystemVersion(&v41);
  WspGetSubsystemInfo(SubsystemType, (struct _SUBSYSTEM_INFO *)&v53);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v35 = SubsystemType;
    v36 = SubsystemVersion != v41;
    LOWORD(v41) = v54;
    v40 = (const char *)&v53;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v24,
      (__int64)word_180350F8A);
  }
  v25 = (unsigned int)WspUnpackObjectId(*v12, &v38, &v35, &v42);
  v28 = v25;
  if ( v25 )
  {
    v29 = (unsigned int)dword_180397B68;
    if ( (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_38;
    v35 = v25;
    v30 = &byte_18034F997;
    v36 = 1946;
  }
  else
  {
    v28 = MI_Context_ConstructParameters(a2, &WSP_Volume_DeleteObject_rtti, &instance);
    if ( v28 )
    {
      if ( (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_38;
      v36 = 1954;
      v30 = (char *)&unk_1803512D8;
    }
    else
    {
      if ( v38 )
        v31 = PmcDeleteVolume(v42);
      else
        v31 = 1;
      v58.value = v31;
      v58.exists = 1;
      v28 = MI_Instance_Destruct((MI_Instance *)a2);
      if ( v28 == MI_RESULT_OK || (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_38;
      v36 = 1976;
      v30 = byte_18034F445;
    }
    v35 = v28;
  }
  v40 = "WSP_Volume_Invoke_DeleteObject";
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
    v29,
    (__int64)v30,
    v26,
    v27,
    &v40);
LABEL_38:
  CSmTimer::Stop((CSmTimer *)&v47);
  SmLogOnMethodFailure(a4, v44, a6 + 4, &v58, v28, 0);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v44 = 0;
    v40 = 0;
    v50 = 1000 * (v48 - v47) / v49;
    v41 = 0;
    v35 = v28;
    v38 = v9;
    v36 = v58.exists != 0 ? v58.value : 0;
    if ( a6[4].exists )
      v34 = *v12;
    else
      v34 = 0;
    v45 = (const char *)v34;
    v46 = "DeleteVolume";
    v43 = "WspVolume";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v58.exists != 0 ? v58.value : 0,
      (__int64)&unk_1803509F8,
      v32,
      v33,
      &v43,
      &v46,
      &v45,
      (__int64)&v38,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)&v50,
      &v41,
      &v40,
      &v44);
  }
  WspFreeString(v42);
  MI_Instance_Destruct(&instance);
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v28);
LABEL_12:
  WspProviderExit(v39, v15);
  if ( IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)&v47);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        IsRemoteRequest = v9;
        v46 = "DeleteVolume";
        v43 = (const char *)(1000 * (v48 - v47) / v49);
        v45 = "WspVolume";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v16,
          (__int64)&byte_18034F5F7,
          v17,
          v18,
          &v45,
          &v46);
      }
    }
  }
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    IsRemoteRequest = 2020;
    v43 = "WSP_Volume_Invoke_DeleteObject";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v16,
      (__int64)qword_180350D00,
      v17,
      v18,
      &v43);
  }
  CSmTimer::~CSmTimer((CSmTimer *)&v47);
  return EventActivityIdControl(4u, &v56);
}

```

## disassembly

```asm
0x1801453c0  mov     [rsp-8+arg_0], rbx
0x1801453c5  push    rbp
0x1801453c6  push    rsi
0x1801453c7  push    rdi
0x1801453c8  push    r12
0x1801453ca  push    r13
0x1801453cc  push    r14
0x1801453ce  push    r15
0x1801453d0  lea     rbp, [rsp-0E0h]
0x1801453d8  sub     rsp, 1E0h
0x1801453df  mov     rax, cs:__security_cookie
0x1801453e6  xor     rax, rsp
0x1801453e9  mov     [rbp+110h+var_40], rax
0x1801453f0  mov     r14, [rbp+110h+arg_20]
0x1801453f7  xorps   xmm0, xmm0
0x1801453fa  mov     r13, [rbp+110h+arg_28]
0x180145401  xor     eax, eax
0x180145403  mov     rdi, [rbp+110h+arg_30]
0x18014540a  mov     rbx, rdx
0x18014540d  movups  xmmword ptr [rbp+110h+value], xmm0
0x180145411  lea     rdx, [rbp+110h+ActivityId]; ActivityId
0x180145415  mov     r12, r9
0x180145418  movups  xmmword ptr [rbp+110h+value+10h], xmm0
0x18014541c  lea     ecx, [rax+1]; ControlCode
0x18014541f  mov     [rbp+110h+var_168], r14
0x180145423  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18014542a  mov     qword ptr [rbp+110h+value+20h], rax
0x18014542e  movdqu  xmmword ptr [rbp+110h+ActivityId.Data1], xmm0
0x180145433  call    cs:__imp_EventActivityIdControl
0x180145439  lea     r9, [rbp+110h+value]; value
0x18014543d  xor     r8d, r8d; valueType
0x180145440  lea     rdx, aActivityid; "ActivityId"
0x180145447  mov     rcx, rbx; context
0x18014544a  call    MI_Context_GetCustomOption
0x18014544f  xor     r15d, r15d
0x180145452  test    eax, eax
0x180145454  jnz     short loc_180145464
0x180145456  mov     rcx, qword ptr [rbp+110h+value]; lpsz
0x18014545a  lea     rdx, [rbp+110h+ActivityId]; pclsid
0x18014545e  call    cs:__imp_CLSIDFromString
0x180145464  mov     rcx, qword ptr [rbp+110h+ActivityId.Data1]
0x180145468  lea     rdx, [rbp+110h+var_C8]; ActivityId
0x18014546c  mov     rax, qword ptr [rbp+110h+ActivityId.Data4]
0x180145470  mov     [rbp+110h+var_D8], rcx
0x180145474  mov     qword ptr [rbp+110h+var_C8.Data1], rcx
0x180145478  mov     ecx, 4; ControlCode
0x18014547d  mov     [rbp+110h+var_D0], rax
0x180145481  mov     qword ptr [rbp+110h+var_C8.Data4], rax
0x180145485  call    cs:__imp_EventActivityIdControl
0x18014548b  mov     eax, cs:dword_180397B68
0x180145491  lea     rcx, aWspVolumeInvok_3; "WSP_Volume_Invoke_DeleteObject"
0x180145498  cmp     eax, 5
0x18014549b  jbe     short loc_1801454C6
0x18014549d  lea     rax, [rbp+110h+var_190]
0x1801454a1  mov     [rbp+110h+var_190], 77Ch
0x1801454a8  mov     [rsp+210h+var_1E8], rax
0x1801454ad  lea     rdx, dword_18034EA3C
0x1801454b4  lea     rax, [rbp+110h+var_178]
0x1801454b8  mov     [rbp+110h+var_178], rcx
0x1801454bc  mov     qword ptr [rsp+210h+var_1F0], rax
0x1801454c1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1801454c6  xor     edx, edx; Val
0x1801454c8  mov     [rbp+110h+var_178], r15
0x1801454cc  lea     rcx, [rbp+110h+instance]; void *
0x1801454d0  mov     [rsp+210h+var_194], r15d
0x1801454d5  lea     r8d, [rdx+68h]; Size
0x1801454d9  call    memset_0
0x1801454de  lea     rcx, [rbp+110h+var_150]; this
0x1801454e2  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x1801454e7  lea     rcx, [rbp+110h+var_150]; this
0x1801454eb  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x1801454f0  mov     rcx, rbx; context
0x1801454f3  call    WspIsRemoteRequest
0x1801454f8  lea     rsi, [r13+40h]
0x1801454fc  mov     [rsp+210h+var_198], eax
0x180145500  cmp     [rsi+8], r15b
0x180145504  jz      short loc_180145518
0x180145506  mov     rcx, [rsi]; unsigned __int16 *
0x180145509  call    WspIsRemoteInstance
0x18014550e  test    al, al
0x180145510  jz      short loc_180145518
0x180145512  mov     r15d, 1
0x180145518  mov     rdx, [rsi]
0x18014551b  lea     r9, [rbp+110h+var_190]
0x18014551f  mov     r8d, 1
0x180145525  mov     [rbp+110h+var_190], 0
0x18014552c  mov     rcx, rbx; context
0x18014552f  call    WspProviderEnter
0x180145534  mov     edx, eax
0x180145536  test    eax, eax
0x180145538  jz      loc_18014567E
0x18014553e  xor     r14d, r14d
0x180145541  test    rbx, rbx
0x180145544  jz      short loc_180145559
0x180145546  mov     rax, [rbx]
0x180145549  test    rax, rax
0x18014554c  jz      short loc_180145559
0x18014554e  mov     rax, [rax]
0x180145551  mov     rcx, rbx
0x180145554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145559  lea     r12, aWspvolume; "WspVolume"
0x180145560  lea     rsi, aDeletevolume; "DeleteVolume"
0x180145567  mov     ecx, [rbp+110h+var_190]
0x18014556a  call    WspProviderExit
0x18014556f  cmp     [rsp+210h+var_198], r14d
0x180145574  jz      loc_1801455FF
0x18014557a  lea     rcx, [rbp+110h+var_150]; this
0x18014557e  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180145583  mov     eax, cs:dword_180397B68
0x180145589  cmp     eax, 5
0x18014558c  jbe     short loc_1801455FF
0x18014558e  mov     rdx, 400000000000h
0x180145598  lea     rcx, dword_180397B68
0x18014559f  call    _tlgKeywordOn
0x1801455a4  test    al, al
0x1801455a6  jz      short loc_1801455FF
0x1801455a8  mov     rax, [rbp+110h+var_148]
0x1801455ac  xor     edx, edx
0x1801455ae  sub     rax, [rbp+110h+var_150]
0x1801455b2  imul    rax, 3E8h
0x1801455b9  mov     [rsp+210h+var_198], r15d
0x1801455be  div     [rbp+110h+var_140]
0x1801455c2  lea     rdx, byte_18034F5F7
0x1801455c9  mov     [rbp+110h+var_158], rsi
0x1801455cd  mov     [rbp+110h+var_170], rax
0x1801455d1  lea     rax, [rbp+110h+var_170]
0x1801455d5  mov     [rsp+210h+var_1D8], rax
0x1801455da  lea     rax, [rsp+210h+var_198]
0x1801455df  mov     [rsp+210h+var_1E0], rax
0x1801455e4  lea     rax, [rbp+110h+var_158]
0x1801455e8  mov     [rsp+210h+var_1E8], rax
0x1801455ed  lea     rax, [rbp+110h+var_160]
0x1801455f1  mov     qword ptr [rsp+210h+var_1F0], rax
0x1801455f6  mov     [rbp+110h+var_160], r12
0x1801455fa  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1801455ff  mov     eax, cs:dword_180397B68
0x180145605  cmp     eax, 5
0x180145608  jbe     short loc_18014563C
0x18014560a  lea     rax, aWspVolumeInvok_3; "WSP_Volume_Invoke_DeleteObject"
0x180145611  mov     [rsp+210h+var_198], 7E4h
0x180145619  mov     [rbp+110h+var_170], rax
0x18014561d  lea     rdx, qword_180350D00
0x180145624  lea     rax, [rsp+210h+var_198]
0x180145629  mov     [rsp+210h+var_1E8], rax
0x18014562e  lea     rax, [rbp+110h+var_170]
0x180145632  mov     qword ptr [rsp+210h+var_1F0], rax
0x180145637  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18014563c  lea     rcx, [rbp+110h+var_150]; this
0x180145640  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x180145645  lea     rdx, [rbp+110h+var_C8]; ActivityId
0x180145649  mov     ecx, 4; ControlCode
0x18014564e  call    cs:__imp_EventActivityIdControl
0x180145654  mov     rcx, [rbp+110h+var_40]
0x18014565b  xor     rcx, rsp; StackCookie
0x18014565e  call    __security_check_cookie
0x180145663  mov     rbx, [rsp+210h+arg_0]
0x18014566b  add     rsp, 1E0h
0x180145672  pop     r15
0x180145674  pop     r14
0x180145676  pop     r13
0x180145678  pop     r12
0x18014567a  pop     rdi
0x18014567b  pop     rsi
0x18014567c  pop     rbp
0x18014567d  retn
0x18014567e  mov     rcx, [rsi]; unsigned __int16 *
0x180145681  call    WspIsRemoteInstance
0x180145686  mov     rcx, [rsi]
0x180145689  test    al, al
0x18014568b  jz      short loc_1801456AA
0x18014568d  mov     r8, rcx; unsigned __int16 *
0x180145690  mov     qword ptr [rsp+210h+var_1F0], rdi; void *
0x180145695  mov     rcx, rbx; struct _MI_Context *
0x180145698  mov     r9, r14; unsigned __int16 *
0x18014569b  mov     rdx, r12; unsigned __int16 *
0x18014569e  call    WspInvokeRemoteMethod
0x1801456a3  mov     edx, eax
0x1801456a5  jmp     loc_18014553E
0x1801456aa  xor     eax, eax
0x1801456ac  xorps   xmm0, xmm0
0x1801456af  movups  [rbp+110h+var_F0], xmm0
0x1801456b3  mov     [rbp+110h+var_E0], eax
0x1801456b6  mov     dword ptr [rbp+110h+var_180], eax
0x1801456b9  call    WspGetSubsystemType
0x1801456be  lea     rcx, [rbp+110h+var_180]
0x1801456c2  mov     edi, eax
0x1801456c4  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1801456c9  lea     rdx, [rbp+110h+var_F0]; struct _SUBSYSTEM_INFO *
0x1801456cd  mov     ecx, edi; unsigned int
0x1801456cf  mov     r14d, eax
0x1801456d2  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1801456d7  mov     ecx, cs:dword_180397B68
0x1801456dd  cmp     ecx, 5
0x1801456e0  jbe     short loc_18014574F
0x1801456e2  mov     rdx, 400000000000h
0x1801456ec  lea     rcx, dword_180397B68
0x1801456f3  call    _tlgKeywordOn
0x1801456f8  test    al, al
0x1801456fa  jz      short loc_18014574F
0x1801456fc  xor     eax, eax
0x1801456fe  mov     [rsp+210h+var_1A0], edi
0x180145702  cmp     r14d, dword ptr [rbp+110h+var_180]
0x180145706  lea     rdx, word_180350F8A
0x18014570d  setnz   al
0x180145710  mov     [rsp+210h+var_19C], eax
0x180145714  movzx   eax, word ptr [rbp+110h+var_E0]
0x180145718  mov     word ptr [rbp+110h+var_180], ax
0x18014571c  lea     rax, [rbp+110h+var_F0]
0x180145720  mov     [rbp+110h+var_188], rax
0x180145724  lea     rax, [rsp+210h+var_19C]
0x180145729  mov     [rsp+210h+var_1D8], rax
0x18014572e  lea     rax, [rbp+110h+var_180]
0x180145732  mov     [rsp+210h+var_1E0], rax
0x180145737  lea     rax, [rsp+210h+var_1A0]
0x18014573c  mov     [rsp+210h+var_1E8], rax
0x180145741  lea     rax, [rbp+110h+var_188]
0x180145745  mov     qword ptr [rsp+210h+var_1F0], rax
0x18014574a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18014574f  mov     rcx, [rsi]; unsigned __int16 *
0x180145752  lea     r9, [rbp+110h+var_178]
0x180145756  lea     r8, [rsp+210h+var_1A0]
0x18014575b  lea     rdx, [rsp+210h+var_194]
0x180145760  call    WspUnpackObjectId
0x180145765  xor     r14d, r14d
0x180145768  mov     edi, eax
0x18014576a  test    eax, eax
0x18014576c  jz      short loc_180145795
0x18014576e  mov     ecx, cs:dword_180397B68
0x180145774  cmp     ecx, 2
0x180145777  jbe     loc_18014584F
0x18014577d  mov     [rsp+210h+var_1A0], eax
0x180145781  lea     rdx, byte_18034F997
0x180145788  mov     [rsp+210h+var_19C], 79Ah
0x180145790  jmp     loc_180145822
0x180145795  lea     r8, [rbp+110h+instance]; instance
0x180145799  mov     rcx, rbx; context
0x18014579c  lea     rdx, WSP_Volume_DeleteObject_rtti; methodDecl
0x1801457a3  call    MI_Context_ConstructParameters
0x1801457a8  mov     edi, eax
0x1801457aa  test    eax, eax
0x1801457ac  jz      short loc_1801457CE
0x1801457ae  mov     eax, cs:dword_180397B68
0x1801457b4  cmp     eax, 2
0x1801457b7  jbe     loc_18014584F
0x1801457bd  mov     [rsp+210h+var_19C], 7A2h
0x1801457c5  lea     rdx, unk_1803512D8
0x1801457cc  jmp     short loc_18014581E
0x1801457ce  cmp     [rsp+210h+var_194], r14d
0x1801457d3  jnz     short loc_1801457DC
0x1801457d5  mov     eax, 1
0x1801457da  jmp     short loc_1801457E5
0x1801457dc  mov     rcx, [rbp+110h+var_178]
0x1801457e0  call    ?PmcDeleteVolume@@YA?AW4SM_RETURN_CODE@@PEBG@Z; PmcDeleteVolume(ushort const *)
0x1801457e5  lea     rdx, [rbp+110h+instance]
0x1801457e9  mov     [rbp+110h+var_70.value], eax
0x1801457ef  mov     rcx, rbx; self
0x1801457f2  mov     [rbp+110h+var_70.exists], 1
0x1801457f9  call    MI_Instance_Destruct
0x1801457fe  mov     edi, eax
0x180145800  test    eax, eax
0x180145802  jz      short loc_18014584F
0x180145804  mov     eax, cs:dword_180397B68
0x18014580a  cmp     eax, 2
0x18014580d  jbe     short loc_18014584F
0x18014580f  mov     [rsp+210h+var_19C], 7B8h
0x180145817  lea     rdx, byte_18034F445
0x18014581e  mov     [rsp+210h+var_1A0], edi
0x180145822  lea     rax, aWspVolumeInvok_3; "WSP_Volume_Invoke_DeleteObject"
0x180145829  mov     [rbp+110h+var_188], rax
0x18014582d  lea     rax, [rsp+210h+var_1A0]
0x180145832  mov     [rsp+210h+var_1E0], rax
0x180145837  lea     rax, [rsp+210h+var_19C]
0x18014583c  mov     [rsp+210h+var_1E8], rax
0x180145841  lea     rax, [rbp+110h+var_188]
0x180145845  mov     qword ptr [rsp+210h+var_1F0], rax
0x18014584a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18014584f  lea     rcx, [rbp+110h+var_150]; this
0x180145853  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180145858  mov     rdx, [rbp+110h+var_168]; unsigned __int16 *
0x18014585c  lea     r9, [rbp+110h+var_70]; struct _MI_ConstUint32Field *
0x180145863  mov     r8, rsi; struct _MI_ConstStringField *
0x180145866  mov     [rsp+210h+var_1E8], r14; unsigned __int16 *
0x18014586b  mov     rcx, r12; unsigned __int16 *
0x18014586e  mov     [rsp+210h+var_1F0], edi; enum _MI_Result
0x180145872  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x180145877  mov     eax, cs:dword_180397B68
0x18014587d  cmp     eax, 5
0x180145880  jbe     loc_180145979
0x180145886  mov     rdx, 400000000000h
0x180145890  lea     rcx, dword_180397B68
0x180145897  call    _tlgKeywordOn
0x18014589c  test    al, al
0x18014589e  jz      loc_180145979
0x1801458a4  mov     rax, [rbp+110h+var_148]
0x1801458a8  xor     edx, edx
0x1801458aa  sub     rax, [rbp+110h+var_150]
0x1801458ae  imul    rax, 3E8h
0x1801458b5  mov     [rbp+110h+var_168], r14
0x1801458b9  div     [rbp+110h+var_140]
0x1801458bd  mov     [rbp+110h+var_188], r14
  ... truncated ...
```
