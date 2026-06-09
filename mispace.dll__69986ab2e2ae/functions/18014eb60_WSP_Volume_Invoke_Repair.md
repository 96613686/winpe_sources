# WSP_Volume_Invoke_Repair

- ea: `0x18014eb60`
- end: `0x18014f2d9`
- name: `WSP_Volume_Invoke_Repair`
- size: `1913`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800011c4`
- `0x180001504`
- `0x1800015d8`
- `0x180001994`
- `0x180004608`
- `0x180004c3c`
- `0x180006350`
- `0x1800063a0`
- `0x180006dd4`
- `0x18000b840`
- `0x18000ba50`
- `0x18000cca4`
- `0x18000ccd4`
- `0x1800142e8`
- `0x180014a54`
- `0x180015850`
- `0x180015a20`
- `0x180015c30`
- `0x180015ea0`
- `0x180015fc0`
- `0x1800167e0`
- `0x180016950`
- `0x180016b40`
- `0x180017020`
- `0x18001b4a0`
- `0x180023e18`
- `0x180025e78`
- `0x180057a2c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x1801485dc`
- `0x18014eb60`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014ebe1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014ec57`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014f2a2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014ebe1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014ec57`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014f2a2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18014ec15`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18014ec15`

## string_xrefs

- `0x18014ed27`: `Repair`
- `0x18014f105`: `Repair`
- `0x18014f186`: `Repair`
- `0x18014ef0a`: `Repair Volume`
- `0x18014ec69`: `WSP_Volume_Invoke_Repair`
- `0x18014ed20`: `WSP_Volume_Invoke_Repair`
- `0x18014ee58`: `WSP_Volume_Invoke_Repair`
- `0x18014efc6`: `WSP_Volume_Invoke_Repair`
- `0x18014effc`: `WSP_Volume_Invoke_Repair`
- `0x18014f009`: `WSP_Volume_Invoke_Repair`

## pseudocode

```c
ULONG __fastcall WSP_Volume_Invoke_Repair(
        __int64 a1,
        MI_Context *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        const struct _MI_ConstStringField *a6,
        struct _WSP_Volume_Repair *a7)
{
  int v9; // r13d
  int v10; // r8d
  int v11; // r9d
  struct _PM_REPAIR_VOLUME_PARAMETERS_EX *v12; // rsi
  const struct _MI_ConstStringField *v13; // rdi
  enum _MI_Result v14; // ebx
  char IsRemoteInstance; // al
  unsigned __int16 *v16; // rcx
  unsigned int SubsystemType; // ebx
  int SubsystemVersion; // r15d
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  char *v25; // rdx
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  int v29; // r8d
  int v30; // r9d
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  unsigned __int16 *v34; // rax
  const MI_Char *v35; // rax
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  MI_Uint32 v40; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int32 v41; // [rsp+74h] [rbp-8Ch] BYREF
  const char *v42; // [rsp+78h] [rbp-88h] BYREF
  int IsRemoteRequest; // [rsp+80h] [rbp-80h] BYREF
  int v44; // [rsp+84h] [rbp-7Ch] BYREF
  int v45; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v46; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned __int64 v47; // [rsp+90h] [rbp-70h] BYREF
  __int64 v48; // [rsp+98h] [rbp-68h] BYREF
  struct _PM_REPAIR_VOLUME_PARAMETERS_EX *v49; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v50; // [rsp+A8h] [rbp-58h] BYREF
  int v51[2]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v52; // [rsp+B8h] [rbp-48h] BYREF
  const char *v53; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v54; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v55; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v56; // [rsp+D8h] [rbp-28h]
  struct _MI_Instance v57; // [rsp+F0h] [rbp-10h] BYREF
  MI_Value value; // [rsp+130h] [rbp+30h] BYREF
  MI_Instance instance; // [rsp+160h] [rbp+60h] BYREF
  struct _MI_ConstUint32Field v60; // [rsp+1A0h] [rbp+A0h] BYREF
  int v61; // [rsp+230h] [rbp+130h]
  char v62; // [rsp+234h] [rbp+134h]
  _OWORD *v63; // [rsp+238h] [rbp+138h]
  char v64; // [rsp+240h] [rbp+140h]
  GUID ActivityId; // [rsp+260h] [rbp+160h] BYREF
  __int128 v66; // [rsp+270h] [rbp+170h] BYREF
  int v67; // [rsp+280h] [rbp+180h]
  GUID v68; // [rsp+288h] [rbp+188h]
  GUID v69; // [rsp+298h] [rbp+198h] BYREF

  v52 = a5;
  v50 = a4;
  memset(&value, 0, sizeof(value));
  v47 = (unsigned __int64)a6;
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  v9 = 0;
  if ( MI_Context_GetCustomOption(a2, L"ActivityId", 0, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v68 = ActivityId;
  v69 = ActivityId;
  EventActivityIdControl(4u, &v69);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v46 = 774;
    v53 = "WSP_Volume_Invoke_Repair";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"WSP_Volume_Invoke_Repair",
      (unsigned int)byte_180355A85,
      v10,
      v11,
      (__int64)&v53,
      (__int64)&v46);
  }
  LODWORD(v48) = 0;
  v53 = 0;
  v45 = 0;
  v51[0] = 0;
  memset_0(&instance, 0, 0xF8u);
  v49 = 0;
  v12 = 0;
  CSmTimer::CSmTimer((CSmTimer *)&v54);
  CSmTimer::Start((CSmTimer *)&v54);
  v13 = a6 + 4;
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( a6[4].exists && (unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)v13->value) )
    v9 = 1;
  v46 = 0;
  v14 = (unsigned int)WspProviderEnter(a2);
  if ( v14 == MI_RESULT_OK )
  {
    IsRemoteInstance = WspIsRemoteInstance((unsigned __int16 *)v13->value);
    v16 = (unsigned __int16 *)v13->value;
    if ( IsRemoteInstance )
    {
      v14 = (unsigned int)WspInvokeRemoteMethod(a2, a4, (unsigned __int16 *)v13->value, v52, a7);
      goto LABEL_45;
    }
    v66 = 0;
    v67 = 0;
    v44 = 0;
    SubsystemType = WspGetSubsystemType(v16);
    SubsystemVersion = _GetSubsystemVersion(&v44);
    WspGetSubsystemInfo(SubsystemType, (struct _SUBSYSTEM_INFO *)&v66);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v41 = SubsystemType;
      v40 = SubsystemVersion != v44;
      LOWORD(v44) = v67;
      v42 = (const char *)&v66;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v19,
        (unsigned int)&byte_180355DE7,
        v20,
        v21,
        (__int64)&v42,
        (__int64)&v41,
        (__int64)&v44,
        (__int64)&v40);
    }
    v14 = (unsigned int)WspUnpackObjectId((unsigned __int16 *)v13->value, &v45, v51, &v53);
    if ( v14 )
    {
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_34;
      v40 = 806;
      v25 = byte_18035676B;
      goto LABEL_17;
    }
    v14 = MI_Context_ConstructParameters(a2, &WSP_Volume_Repair_rtti, &instance);
    if ( v14 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v40 = 814;
        v25 = (char *)&word_180358666;
LABEL_17:
        v42 = "WSP_Volume_Invoke_Repair";
        v41 = v14;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v22,
          (_DWORD)v25,
          v23,
          v24,
          (__int64)&v42,
          (__int64)&v40,
          (__int64)&v41);
      }
    }
    else
    {
      v14 = (unsigned int)WSP_Volume_Params_Repair(a7, &v49, (enum SM_RETURN_CODE *)&v48);
      if ( v14 || (_DWORD)v48 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          v41 = v14;
          v40 = 822;
          v42 = "WSP_Volume_Invoke_Repair";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v26,
            (unsigned int)&word_18035628E,
            v27,
            v28,
            (__int64)&v42,
            (__int64)&v40,
            (__int64)&v41);
        }
        v12 = v49;
        goto LABEL_34;
      }
      v12 = v49;
      v14 = (unsigned int)WspRunMethodAsJob(
                            a2,
                            (__int64)L"Repair Volume",
                            2u,
                            (__int64)WSP_Volume_Invoke_Repair_Async,
                            (__int64)v49,
                            v45,
                            v51[0],
                            (__int64)v13->value,
                            &instance,
                            &v48);
      if ( v14 == MI_RESULT_OK )
      {
        v12 = 0;
        if ( !(_DWORD)v48 )
        {
          v61 = 0;
          v62 = 1;
        }
        v60.value = v48;
        v60.exists = 1;
        v14 = MI_Instance_Destruct((MI_Instance *)a2);
        if ( v14 == MI_RESULT_OK || (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_34;
        v40 = 871;
        v25 = (char *)&dword_1803573D4;
        goto LABEL_17;
      }
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v40 = 841;
        v25 = byte_180355B11;
        goto LABEL_17;
      }
    }
LABEL_34:
    CSmTimer::Stop((CSmTimer *)&v54);
    SmLogOnMethodFailure(v50, v52, v13, &v60, v14, 0);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      if ( v64 )
      {
        v31 = v63[1];
        *(_OWORD *)&v57.ft = *v63;
        v32 = v63[2];
        *(_OWORD *)&v57.serverName = v31;
        v33 = v63[3];
        *(_OWORD *)v57.reserved = v32;
        *(_OWORD *)&v57.reserved[2] = v33;
        v34 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v57, 0);
      }
      else
      {
        v34 = 0;
      }
      v50 = v34;
      v42 = 0;
      v52 = 0;
      v49 = (struct _PM_REPAIR_VOLUME_PARAMETERS_EX *)(1000 * (v55 - v54) / v56);
      v41 = v14;
      v45 = v9;
      v40 = v60.exists != 0 ? v60.value : 0;
      if ( *(_BYTE *)(v47 + 72) )
        v35 = v13->value;
      else
        v35 = 0;
      v47 = (unsigned __int64)v35;
      *(_QWORD *)v51 = "Repair";
      v48 = (__int64)"WspVolume";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v60.exists != 0 ? v60.value : 0,
        (unsigned int)&byte_18035766F,
        v29,
        v30,
        (__int64)&v48,
        (__int64)v51,
        (__int64)&v47,
        (__int64)&v45,
        (__int64)&v40,
        (__int64)&v41,
        (__int64)&v49,
        (__int64)&v52,
        (__int64)&v42,
        (__int64)&v50);
    }
    WspFreeString(v53);
    MI_Instance_Destruct(&instance);
    if ( v12 )
      operator delete(v12);
  }
LABEL_45:
  MI_Context_PostResult_0(a2, v14);
  WspProviderExit(v46);
  if ( IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)&v54);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        IsRemoteRequest = v9;
        v50 = (unsigned __int16 *)"Repair";
        v47 = 1000 * (v55 - v54) / v56;
        v42 = "WspVolume";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v36,
          (unsigned int)&unk_180357260,
          v37,
          v38,
          (__int64)&v42,
          (__int64)&v50,
          (__int64)&IsRemoteRequest,
          (__int64)&v47);
      }
    }
  }
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    IsRemoteRequest = 916;
    v47 = (unsigned __int64)"WSP_Volume_Invoke_Repair";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v36,
      (unsigned int)qword_1803563A0,
      v37,
      v38,
      (__int64)&v47,
      (__int64)&IsRemoteRequest);
  }
  CSmTimer::~CSmTimer((CSmTimer *)&v54);
  return EventActivityIdControl(4u, &v69);
}

```

## disassembly

```asm
0x18014eb60  mov     [rsp-8+arg_0], rbx
0x18014eb65  push    rbp
0x18014eb66  push    rsi
0x18014eb67  push    rdi
0x18014eb68  push    r12
0x18014eb6a  push    r13
0x18014eb6c  push    r14
0x18014eb6e  push    r15
0x18014eb70  lea     rbp, [rsp-1B0h]
0x18014eb78  sub     rsp, 2B0h
0x18014eb7f  mov     rax, cs:__security_cookie
0x18014eb86  xor     rax, rsp
0x18014eb89  mov     [rbp+1E0h+var_38], rax
0x18014eb90  mov     rax, [rbp+1E0h+arg_20]
0x18014eb97  xorps   xmm0, xmm0
0x18014eb9a  mov     rbx, [rbp+1E0h+arg_28]
0x18014eba1  mov     r14, rdx
0x18014eba4  mov     r12, [rbp+1E0h+arg_30]
0x18014ebab  lea     rdx, [rbp+1E0h+ActivityId]; ActivityId
0x18014ebb2  mov     [rbp+1E0h+var_228], rax
0x18014ebb6  mov     r15, r9
0x18014ebb9  xor     eax, eax
0x18014ebbb  mov     [rbp+1E0h+var_238], r9
0x18014ebbf  movups  xmmword ptr [rbp+1E0h+value], xmm0
0x18014ebc3  mov     [rbp+1E0h+var_250], rbx
0x18014ebc7  movups  xmmword ptr [rbp+1E0h+value+10h], xmm0
0x18014ebcb  lea     ecx, [rax+1]; ControlCode
0x18014ebce  mov     qword ptr [rbp+1E0h+value+20h], rax
0x18014ebd2  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18014ebd9  movdqu  xmmword ptr [rbp+1E0h+ActivityId.Data1], xmm0
0x18014ebe1  call    cs:__imp_EventActivityIdControl
0x18014ebe8  nop     dword ptr [rax+rax+00h]
0x18014ebed  lea     r9, [rbp+1E0h+value]; value
0x18014ebf1  xor     r8d, r8d; valueType
0x18014ebf4  lea     rdx, aActivityid; "ActivityId"
0x18014ebfb  mov     rcx, r14; context
0x18014ebfe  call    MI_Context_GetCustomOption
0x18014ec03  xor     r13d, r13d
0x18014ec06  test    eax, eax
0x18014ec08  jnz     short loc_18014EC21
0x18014ec0a  mov     rcx, qword ptr [rbp+1E0h+value]; lpsz
0x18014ec0e  lea     rdx, [rbp+1E0h+ActivityId]; pclsid
0x18014ec15  call    cs:__imp_CLSIDFromString
0x18014ec1c  nop     dword ptr [rax+rax+00h]
0x18014ec21  mov     rcx, qword ptr [rbp+1E0h+ActivityId.Data1]
0x18014ec28  lea     rdx, [rbp+1E0h+var_48]; ActivityId
0x18014ec2f  mov     rax, qword ptr [rbp+1E0h+ActivityId.Data4]
0x18014ec36  mov     [rbp+1E0h+var_58], rcx
0x18014ec3d  mov     qword ptr [rbp+1E0h+var_48.Data1], rcx
0x18014ec44  mov     ecx, 4; ControlCode
0x18014ec49  mov     [rbp+1E0h+var_50], rax
0x18014ec50  mov     qword ptr [rbp+1E0h+var_48.Data4], rax
0x18014ec57  call    cs:__imp_EventActivityIdControl
0x18014ec5e  nop     dword ptr [rax+rax+00h]
0x18014ec63  mov     eax, cs:dword_18039EB68
0x18014ec69  lea     rcx, aWspVolumeInvok_8; "WSP_Volume_Invoke_Repair"
0x18014ec70  cmp     eax, 5
0x18014ec73  jbe     short loc_18014EC9E
0x18014ec75  lea     rax, [rbp+1E0h+var_254]
0x18014ec79  mov     [rbp+1E0h+var_254], 306h
0x18014ec80  mov     [rsp+2E0h+var_2B8], rax
0x18014ec85  lea     rdx, byte_180355A85
0x18014ec8c  lea     rax, [rbp+1E0h+var_220]
0x18014ec90  mov     [rbp+1E0h+var_220], rcx
0x18014ec94  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x18014ec99  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18014ec9e  xor     edx, edx; Val
0x18014eca0  mov     dword ptr [rbp+1E0h+var_248], r13d
0x18014eca4  mov     r8d, 0F8h; Size
0x18014ecaa  mov     [rbp+1E0h+var_220], r13
0x18014ecae  lea     rcx, [rbp+1E0h+instance]; void *
0x18014ecb2  mov     [rbp+1E0h+var_258], r13d
0x18014ecb6  mov     [rbp+1E0h+var_230], r13d
0x18014ecba  call    memset_0
0x18014ecbf  lea     rcx, [rbp+1E0h+var_218]; this
0x18014ecc3  mov     [rbp+1E0h+var_240], r13
0x18014ecc7  mov     rsi, r13
0x18014ecca  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18014eccf  lea     rcx, [rbp+1E0h+var_218]; this
0x18014ecd3  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18014ecd8  mov     rcx, r14; context
0x18014ecdb  call    WspIsRemoteRequest
0x18014ece0  lea     rdi, [rbx+40h]
0x18014ece4  mov     [rbp+1E0h+var_260], eax
0x18014ece7  cmp     [rdi+8], r13b
0x18014eceb  jz      short loc_18014ECFF
0x18014eced  mov     rcx, [rdi]; unsigned __int16 *
0x18014ecf0  call    WspIsRemoteInstance
0x18014ecf5  test    al, al
0x18014ecf7  jz      short loc_18014ECFF
0x18014ecf9  mov     r13d, 1
0x18014ecff  mov     rdx, [rdi]
0x18014ed02  lea     r9, [rbp+1E0h+var_254]
0x18014ed06  mov     r8d, 1
0x18014ed0c  mov     [rbp+1E0h+var_254], esi
0x18014ed0f  mov     rcx, r14; context
0x18014ed12  call    WspProviderEnter
0x18014ed17  mov     ebx, eax
0x18014ed19  test    eax, eax
0x18014ed1b  jz      short loc_18014ED33
0x18014ed1d  xor     r15d, r15d
0x18014ed20  lea     r12, aWspVolumeInvok_8; "WSP_Volume_Invoke_Repair"
0x18014ed27  lea     rdi, aRepair_0; "Repair"
0x18014ed2e  jmp     loc_18014F1B1
0x18014ed33  mov     rcx, [rdi]; unsigned __int16 *
0x18014ed36  call    WspIsRemoteInstance
0x18014ed3b  mov     rcx, [rdi]
0x18014ed3e  test    al, al
0x18014ed40  jz      short loc_18014ED5D
0x18014ed42  mov     r9, [rbp+1E0h+var_228]; unsigned __int16 *
0x18014ed46  mov     r8, rcx; unsigned __int16 *
0x18014ed49  mov     rcx, r14; struct _MI_Context *
0x18014ed4c  mov     qword ptr [rsp+2E0h+var_2C0], r12; void *
0x18014ed51  mov     rdx, r15; unsigned __int16 *
0x18014ed54  call    WspInvokeRemoteMethod
0x18014ed59  mov     ebx, eax
0x18014ed5b  jmp     short loc_18014ED1D
0x18014ed5d  xor     eax, eax
0x18014ed5f  xorps   xmm0, xmm0
0x18014ed62  movups  [rbp+1E0h+var_70], xmm0
0x18014ed69  mov     [rbp+1E0h+var_60], eax
0x18014ed6f  mov     [rbp+1E0h+var_25C], eax
0x18014ed72  call    WspGetSubsystemType
0x18014ed77  lea     rcx, [rbp+1E0h+var_25C]
0x18014ed7b  mov     ebx, eax
0x18014ed7d  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18014ed82  lea     rdx, [rbp+1E0h+var_70]; struct _SUBSYSTEM_INFO *
0x18014ed89  mov     ecx, ebx; unsigned int
0x18014ed8b  mov     r15d, eax
0x18014ed8e  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18014ed93  mov     ecx, cs:dword_18039EB68
0x18014ed99  cmp     ecx, 5
0x18014ed9c  jbe     short loc_18014EE13
0x18014ed9e  mov     rdx, 400000000000h
0x18014eda8  lea     rcx, dword_18039EB68
0x18014edaf  call    _tlgKeywordOn
0x18014edb4  test    al, al
0x18014edb6  jz      short loc_18014EE13
0x18014edb8  xor     eax, eax
0x18014edba  mov     [rsp+2E0h+var_26C], ebx
0x18014edbe  cmp     r15d, [rbp+1E0h+var_25C]
0x18014edc2  lea     rdx, byte_180355DE7
0x18014edc9  setnz   al
0x18014edcc  mov     [rsp+2E0h+var_270], eax
0x18014edd0  movzx   eax, word ptr [rbp+1E0h+var_60]
0x18014edd7  mov     word ptr [rbp+1E0h+var_25C], ax
0x18014eddb  lea     rax, [rbp+1E0h+var_70]
0x18014ede2  mov     [rsp+2E0h+var_268], rax
0x18014ede7  lea     rax, [rsp+2E0h+var_270]
0x18014edec  mov     [rsp+2E0h+var_2A8], rax
0x18014edf1  lea     rax, [rbp+1E0h+var_25C]
0x18014edf5  mov     qword ptr [rsp+2E0h+var_2B0], rax
0x18014edfa  lea     rax, [rsp+2E0h+var_26C]
0x18014edff  mov     [rsp+2E0h+var_2B8], rax
0x18014ee04  lea     rax, [rsp+2E0h+var_268]
0x18014ee09  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x18014ee0e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18014ee13  mov     rcx, [rdi]; unsigned __int16 *
0x18014ee16  lea     r9, [rbp+1E0h+var_220]
0x18014ee1a  lea     r8, [rbp+1E0h+var_230]
0x18014ee1e  lea     rdx, [rbp+1E0h+var_258]
0x18014ee22  call    WspUnpackObjectId
0x18014ee27  xor     r15d, r15d
0x18014ee2a  mov     ebx, eax
0x18014ee2c  test    eax, eax
0x18014ee2e  jz      short loc_18014EE86
0x18014ee30  mov     eax, cs:dword_18039EB68
0x18014ee36  cmp     eax, 2
0x18014ee39  jbe     loc_18014F009
0x18014ee3f  mov     [rsp+2E0h+var_270], 326h
0x18014ee47  lea     rdx, byte_18035676B
0x18014ee4e  lea     rax, [rsp+2E0h+var_26C]
0x18014ee53  mov     qword ptr [rsp+2E0h+var_2B0], rax
0x18014ee58  lea     r12, aWspVolumeInvok_8; "WSP_Volume_Invoke_Repair"
0x18014ee5f  lea     rax, [rsp+2E0h+var_270]
0x18014ee64  mov     [rsp+2E0h+var_268], r12
0x18014ee69  mov     [rsp+2E0h+var_2B8], rax
0x18014ee6e  lea     rax, [rsp+2E0h+var_268]
0x18014ee73  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x18014ee78  mov     [rsp+2E0h+var_26C], ebx
0x18014ee7c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18014ee81  jmp     loc_18014F010
0x18014ee86  lea     r8, [rbp+1E0h+instance]; instance
0x18014ee8a  mov     rcx, r14; context
0x18014ee8d  lea     rdx, WSP_Volume_Repair_rtti; methodDecl
0x18014ee94  call    MI_Context_ConstructParameters
0x18014ee99  mov     ebx, eax
0x18014ee9b  test    eax, eax
0x18014ee9d  jz      short loc_18014EEBF
0x18014ee9f  mov     eax, cs:dword_18039EB68
0x18014eea5  cmp     eax, 2
0x18014eea8  jbe     loc_18014F009
0x18014eeae  mov     [rsp+2E0h+var_270], 32Eh
0x18014eeb6  lea     rdx, word_180358666
0x18014eebd  jmp     short loc_18014EE4E
0x18014eebf  lea     r8, [rbp+1E0h+var_248]; enum SM_RETURN_CODE *
0x18014eec3  mov     rcx, r12; struct _WSP_Volume_Repair *
0x18014eec6  lea     rdx, [rbp+1E0h+var_240]; struct _PM_REPAIR_VOLUME_PARAMETERS_EX **
0x18014eeca  call    ?WSP_Volume_Params_Repair@@YA?AW4_MI_Result@@PEBU_WSP_Volume_Repair@@PEAPEAU_PM_REPAIR_VOLUME_PARAMETERS_EX@@PEAW4SM_RETURN_CODE@@@Z; WSP_Volume_Params_Repair(_WSP_Volume_Repair const *,_PM_REPAIR_VOLUME_PARAMETERS_EX * *,SM_RETURN_CODE *)
0x18014eecf  mov     ebx, eax
0x18014eed1  test    eax, eax
0x18014eed3  jnz     loc_18014EFAD
0x18014eed9  cmp     dword ptr [rbp+1E0h+var_248], r15d
0x18014eedd  jnz     loc_18014EFAD
0x18014eee3  mov     rsi, [rbp+1E0h+var_240]
0x18014eee7  lea     rax, [rbp+1E0h+var_248]
0x18014eeeb  mov     [rsp+2E0h+var_298], rax; __int64
0x18014eef0  lea     r9, ?WSP_Volume_Invoke_Repair_Async@@YAXPEAX0@Z; WSP_Volume_Invoke_Repair_Async(void *,void *)
0x18014eef7  lea     rax, [rbp+1E0h+instance]
0x18014eefb  mov     rcx, r14; struct _MI_Context *
0x18014eefe  mov     [rsp+2E0h+var_2A0], rax; struct _MI_Instance *
0x18014ef03  lea     r8d, [rbx+2]
0x18014ef07  mov     rax, [rdi]
0x18014ef0a  lea     rdx, aRepairVolume; "Repair Volume"
0x18014ef11  mov     [rsp+2E0h+var_2A8], rax; __int64
0x18014ef16  mov     eax, [rbp+1E0h+var_230]
0x18014ef19  mov     [rsp+2E0h+var_2B0], eax; int
0x18014ef1d  mov     eax, [rbp+1E0h+var_258]
0x18014ef20  mov     dword ptr [rsp+2E0h+var_2B8], eax; int
0x18014ef24  mov     qword ptr [rsp+2E0h+var_2C0], rsi; __int64
0x18014ef29  call    WspRunMethodAsJob
0x18014ef2e  mov     ebx, eax
0x18014ef30  test    eax, eax
0x18014ef32  jz      short loc_18014EF57
0x18014ef34  mov     eax, cs:dword_18039EB68
0x18014ef3a  cmp     eax, 2
0x18014ef3d  jbe     loc_18014F009
0x18014ef43  mov     [rsp+2E0h+var_270], 349h
0x18014ef4b  lea     rdx, byte_180355B11
0x18014ef52  jmp     loc_18014EE4E
0x18014ef57  mov     eax, dword ptr [rbp+1E0h+var_248]
0x18014ef5a  mov     rsi, r15
0x18014ef5d  test    eax, eax
0x18014ef5f  jnz     short loc_18014EF6F
0x18014ef61  mov     [rbp+1E0h+var_B0], r15d
0x18014ef68  mov     [rbp+1E0h+var_AC], 1
0x18014ef6f  lea     rdx, [rbp+1E0h+instance]
0x18014ef73  mov     [rbp+1E0h+var_140.value], eax
0x18014ef79  mov     rcx, r14; self
0x18014ef7c  mov     [rbp+1E0h+var_140.exists], 1
0x18014ef83  call    MI_Instance_Destruct
0x18014ef88  mov     ebx, eax
0x18014ef8a  test    eax, eax
0x18014ef8c  jz      short loc_18014F009
0x18014ef8e  mov     eax, cs:dword_18039EB68
0x18014ef94  cmp     eax, 2
0x18014ef97  jbe     short loc_18014F009
0x18014ef99  mov     [rsp+2E0h+var_270], 367h
0x18014efa1  lea     rdx, dword_1803573D4
0x18014efa8  jmp     loc_18014EE4E
0x18014efad  mov     eax, cs:dword_18039EB68
0x18014efb3  cmp     eax, 2
0x18014efb6  jbe     short loc_18014EFFC
0x18014efb8  lea     rax, [rsp+2E0h+var_26C]
0x18014efbd  mov     [rsp+2E0h+var_26C], ebx
0x18014efc1  mov     qword ptr [rsp+2E0h+var_2B0], rax
0x18014efc6  lea     r12, aWspVolumeInvok_8; "WSP_Volume_Invoke_Repair"
0x18014efcd  lea     rax, [rsp+2E0h+var_270]
0x18014efd2  mov     [rsp+2E0h+var_270], 336h
0x18014efda  mov     [rsp+2E0h+var_2B8], rax
0x18014efdf  lea     rdx, word_18035628E
0x18014efe6  lea     rax, [rsp+2E0h+var_268]
0x18014efeb  mov     [rsp+2E0h+var_268], r12
0x18014eff0  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x18014eff5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18014effa  jmp     short loc_18014F003
0x18014effc  lea     r12, aWspVolumeInvok_8; "WSP_Volume_Invoke_Repair"
0x18014f003  mov     rsi, [rbp+1E0h+var_240]
0x18014f007  jmp     short loc_18014F010
0x18014f009  lea     r12, aWspVolumeInvok_8; "WSP_Volume_Invoke_Repair"
0x18014f010  lea     rcx, [rbp+1E0h+var_218]; this
0x18014f014  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18014f019  mov     rdx, [rbp+1E0h+var_228]; unsigned __int16 *
0x18014f01d  lea     r9, [rbp+1E0h+var_140]; struct _MI_ConstUint32Field *
0x18014f024  mov     rcx, [rbp+1E0h+var_238]; unsigned __int16 *
0x18014f028  mov     r8, rdi; struct _MI_ConstStringField *
0x18014f02b  mov     [rsp+2E0h+var_2B8], r15; unsigned __int16 *
0x18014f030  mov     [rsp+2E0h+var_2C0], ebx; enum _MI_Result
0x18014f034  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18014f039  mov     eax, cs:dword_18039EB68
0x18014f03f  cmp     eax, 5
0x18014f042  jbe     loc_18014F186
0x18014f048  mov     rdx, 400000000000h
0x18014f052  lea     rcx, dword_18039EB68
0x18014f059  call    _tlgKeywordOn
0x18014f05e  test    al, al
0x18014f060  jz      loc_18014F186
0x18014f066  cmp     [rbp+1E0h+var_A0], r15b
0x18014f06d  jz      short loc_18014F0AA
0x18014f06f  mov     rax, [rbp+1E0h+var_A8]
0x18014f076  lea     rdx, [rbp+1E0h+var_1F0]; struct _MI_Instance
0x18014f07a  xor     r8d, r8d; unsigned __int16 *
0x18014f07d  lea     rcx, name; "ObjectId"
0x18014f084  movups  xmm0, xmmword ptr [rax]
0x18014f087  movups  xmm1, xmmword ptr [rax+10h]
0x18014f08b  movaps  xmmword ptr [rbp+1E0h+var_1F0.ft], xmm0
0x18014f08f  movups  xmm0, xmmword ptr [rax+20h]
0x18014f093  movaps  xmmword ptr [rbp+1E0h+var_1F0.serverName], xmm1
0x18014f097  movups  xmm1, xmmword ptr [rax+30h]
0x18014f09b  movaps  xmmword ptr [rbp+1E0h+var_1F0.reserved], xmm0
  ... truncated ...
```
