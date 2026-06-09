# WSP_Volume_Invoke_SetFileSystemLabel

- ea: `0x180150530`
- end: `0x180150b79`
- name: `WSP_Volume_Invoke_SetFileSystemLabel`
- size: `1609`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, broker_com_uri`

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
- `0x180017020`
- `0x18001b4a0`
- `0x180023e18`
- `0x180057a2c`
- `0x1801229e0`
- `0x180125ec0`
- `0x18013c4e8`
- `0x18013c50c`
- `0x1801484dc`
- `0x180150530`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801505ab`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180150609`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180150b42`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801505ab`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180150609`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180150b42`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801505dc`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801505dc`

## string_xrefs

- `0x1801506d2`: `SetFileSystemLabel`
- `0x1801509ab`: `SetFileSystemLabel`
- `0x180150a2c`: `SetFileSystemLabel`
- `0x18015061b`: `WSP_Volume_Invoke_SetFileSystemLabel`
- `0x1801506cb`: `WSP_Volume_Invoke_SetFileSystemLabel`
- `0x1801507f4`: `WSP_Volume_Invoke_SetFileSystemLabel`
- `0x1801508bd`: `WSP_Volume_Invoke_SetFileSystemLabel`
- `0x1801508ef`: `WSP_Volume_Invoke_SetFileSystemLabel`

## pseudocode

```c
ULONG __fastcall WSP_Volume_Invoke_SetFileSystemLabel(
        __int64 a1,
        MI_Context *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        const struct _MI_ConstStringField *a6,
        struct _WSP_Volume_SetFileSystemLabel *a7)
{
  int v9; // r13d
  int v10; // r8d
  int v11; // r9d
  struct _PM_SET_FILESYSTEM_LABEL_PARAMETERS *v12; // rsi
  const struct _MI_ConstStringField *v13; // rdi
  enum _MI_Result v14; // ebx
  char IsRemoteInstance; // al
  unsigned __int16 *v16; // rcx
  unsigned int SubsystemType; // ebx
  int SubsystemVersion; // r15d
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  enum _MI_Result v22; // eax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  unsigned __int64 v26; // r15
  __int16 *v27; // rdx
  MI_Uint32 v28; // eax
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  int v32; // r9d
  const MI_Char *v33; // rax
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  MI_Uint32 v38; // [rsp+70h] [rbp-90h] BYREF
  int v39; // [rsp+74h] [rbp-8Ch] BYREF
  enum _MI_Result v40; // [rsp+78h] [rbp-88h] BYREF
  int IsRemoteRequest; // [rsp+7Ch] [rbp-84h] BYREF
  const char *v42; // [rsp+80h] [rbp-80h] BYREF
  int v43; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v44; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned __int64 v45; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v46; // [rsp+98h] [rbp-68h] BYREF
  struct _PM_SET_FILESYSTEM_LABEL_PARAMETERS *v47; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v48; // [rsp+A8h] [rbp-58h] BYREF
  const char *v49; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v50; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v51; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v52; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v53; // [rsp+D0h] [rbp-30h]
  MI_Value value; // [rsp+E0h] [rbp-20h] BYREF
  GUID ActivityId; // [rsp+108h] [rbp+8h] BYREF
  __int128 v56; // [rsp+118h] [rbp+18h] BYREF
  int v57; // [rsp+128h] [rbp+28h]
  GUID v58; // [rsp+130h] [rbp+30h]
  GUID v59; // [rsp+140h] [rbp+40h] BYREF
  MI_Instance instance; // [rsp+150h] [rbp+50h] BYREF
  struct _MI_ConstUint32Field v61; // [rsp+190h] [rbp+90h] BYREF

  v50 = a5;
  v48 = a4;
  memset(&value, 0, sizeof(value));
  v45 = (unsigned __int64)a6;
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  v9 = 0;
  if ( MI_Context_GetCustomOption(a2, L"ActivityId", 0, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v58 = ActivityId;
  v59 = ActivityId;
  EventActivityIdControl(4u, &v59);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v44 = 1194;
    v46 = (unsigned __int64)"WSP_Volume_Invoke_SetFileSystemLabel";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"WSP_Volume_Invoke_SetFileSystemLabel",
      (unsigned int)byte_180355E49,
      v10,
      v11,
      (__int64)&v46,
      (__int64)&v44);
  }
  v40 = MI_RESULT_OK;
  v46 = 0;
  LODWORD(v49) = 0;
  memset_0(&instance, 0, 0x68u);
  v47 = 0;
  v12 = 0;
  CSmTimer::CSmTimer((CSmTimer *)&v51);
  CSmTimer::Start((CSmTimer *)&v51);
  v13 = a6 + 4;
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( a6[4].exists && (unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)v13->value) )
    v9 = 1;
  v44 = 0;
  v14 = (unsigned int)WspProviderEnter(a2);
  if ( v14 == MI_RESULT_OK )
  {
    IsRemoteInstance = WspIsRemoteInstance((unsigned __int16 *)v13->value);
    v16 = (unsigned __int16 *)v13->value;
    if ( IsRemoteInstance )
    {
      v14 = (unsigned int)WspInvokeRemoteMethod(a2, a4, (unsigned __int16 *)v13->value, v50, a7);
      goto LABEL_35;
    }
    v56 = 0;
    v57 = 0;
    v43 = 0;
    SubsystemType = WspGetSubsystemType(v16);
    SubsystemVersion = _GetSubsystemVersion(&v43);
    WspGetSubsystemInfo(SubsystemType, (struct _SUBSYSTEM_INFO *)&v56);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v38 = SubsystemType;
      v39 = SubsystemVersion != v43;
      LOWORD(v43) = v57;
      v42 = (const char *)&v56;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v19,
        (unsigned int)&byte_18035747F,
        v20,
        v21,
        (__int64)&v42,
        (__int64)&v38,
        (__int64)&v43,
        (__int64)&v39);
    }
    v22 = (unsigned int)WspUnpackObjectId((unsigned __int16 *)v13->value, &v49, &v38, &v46);
    v26 = v46;
    v14 = v22;
    if ( v22 )
    {
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_27;
      v39 = 1225;
      v27 = (__int16 *)&byte_1803575CF;
    }
    else
    {
      v14 = MI_Context_ConstructParameters(a2, &WSP_Volume_SetFileSystemLabel_rtti, &instance);
      if ( v14 == MI_RESULT_OK )
      {
        WSP_Volume_Params_SetFileSystemLabel(a7, &v47, (enum SM_RETURN_CODE *)&v40);
        v12 = v47;
        if ( (_DWORD)v49 )
          v28 = PmcSetFileSystemLabel(v26, v47);
        else
          v28 = PmSetFileSystemLabel(v26, v47);
        v61.value = v28;
        v61.exists = 1;
        v14 = MI_Instance_Destruct((MI_Instance *)a2);
        if ( v14 && (unsigned int)dword_18039EB68 > 2 )
        {
          v40 = v14;
          v38 = 1257;
          v42 = "WSP_Volume_Invoke_SetFileSystemLabel";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v29,
            (unsigned int)&dword_18035819C,
            v30,
            v31,
            (__int64)&v42,
            (__int64)&v38,
            (__int64)&v40);
        }
        goto LABEL_27;
      }
      if ( (unsigned int)dword_18039EB68 <= 2 )
      {
LABEL_27:
        CSmTimer::Stop((CSmTimer *)&v51);
        SmLogOnMethodFailure(v48, v50, v13, &v61, v14, 0);
        if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
        {
          v48 = 0;
          v42 = 0;
          v46 = 1000 * (v52 - v51) / v53;
          v50 = 0;
          v40 = v14;
          v38 = v61.exists != 0 ? v61.value : 0;
          v39 = v9;
          if ( *(_BYTE *)(v45 + 72) )
            v33 = v13->value;
          else
            v33 = 0;
          v45 = (unsigned __int64)v33;
          v47 = (struct _PM_SET_FILESYSTEM_LABEL_PARAMETERS *)"SetFileSystemLabel";
          v49 = "WspVolume";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            v61.exists != 0 ? v61.value : 0,
            (unsigned int)byte_180357755,
            0,
            v32,
            (__int64)&v49,
            (__int64)&v47,
            (__int64)&v45,
            (__int64)&v39,
            (__int64)&v38,
            (__int64)&v40,
            (__int64)&v46,
            (__int64)&v50,
            (__int64)&v42,
            (__int64)&v48);
        }
        WspFreeString(v26);
        MI_Instance_Destruct(&instance);
        if ( v12 )
          operator delete(v12);
        goto LABEL_35;
      }
      v39 = 1233;
      v27 = word_180356E42;
    }
    v42 = "WSP_Volume_Invoke_SetFileSystemLabel";
    v38 = v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v23,
      (_DWORD)v27,
      v24,
      v25,
      (__int64)&v42,
      (__int64)&v39,
      (__int64)&v38);
    goto LABEL_27;
  }
LABEL_35:
  MI_Context_PostResult_0(a2, v14);
  WspProviderExit(v44);
  if ( IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)&v51);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        IsRemoteRequest = v9;
        v48 = (unsigned __int16 *)"SetFileSystemLabel";
        v45 = 1000 * (v52 - v51) / v53;
        v42 = "WspVolume";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v34,
          (unsigned int)&dword_180358534,
          v35,
          v36,
          (__int64)&v42,
          (__int64)&v48,
          (__int64)&IsRemoteRequest,
          (__int64)&v45);
      }
    }
  }
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    IsRemoteRequest = 1302;
    v45 = (unsigned __int64)"WSP_Volume_Invoke_SetFileSystemLabel";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v34,
      (unsigned int)&byte_1803569EF,
      v35,
      v36,
      (__int64)&v45,
      (__int64)&IsRemoteRequest);
  }
  CSmTimer::~CSmTimer((CSmTimer *)&v51);
  return EventActivityIdControl(4u, &v59);
}

```

## disassembly

```asm
0x180150530  mov     [rsp-8+arg_0], rbx
0x180150535  push    rbp
0x180150536  push    rsi
0x180150537  push    rdi
0x180150538  push    r12
0x18015053a  push    r13
0x18015053c  push    r14
0x18015053e  push    r15
0x180150540  lea     rbp, [rsp-0D0h]
0x180150548  sub     rsp, 1D0h
0x18015054f  mov     rax, cs:__security_cookie
0x180150556  xor     rax, rsp
0x180150559  mov     [rbp+100h+var_40], rax
0x180150560  mov     rax, [rbp+100h+arg_20]
0x180150567  xorps   xmm0, xmm0
0x18015056a  mov     rbx, [rbp+100h+arg_28]
0x180150571  mov     r14, rdx
0x180150574  mov     r12, [rbp+100h+arg_30]
0x18015057b  lea     rdx, [rbp+100h+ActivityId]; ActivityId
0x18015057f  mov     [rbp+100h+var_148], rax
0x180150583  mov     r15, r9
0x180150586  xor     eax, eax
0x180150588  mov     [rbp+100h+var_158], r9
0x18015058c  movups  xmmword ptr [rbp+100h+value], xmm0
0x180150590  mov     [rbp+100h+var_170], rbx
0x180150594  movups  xmmword ptr [rbp+100h+value+10h], xmm0
0x180150598  lea     ecx, [rax+1]; ControlCode
0x18015059b  mov     qword ptr [rbp+100h+value+20h], rax
0x18015059f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801505a6  movdqu  xmmword ptr [rbp+100h+ActivityId.Data1], xmm0
0x1801505ab  call    cs:__imp_EventActivityIdControl
0x1801505b2  nop     dword ptr [rax+rax+00h]
0x1801505b7  lea     r9, [rbp+100h+value]; value
0x1801505bb  xor     r8d, r8d; valueType
0x1801505be  lea     rdx, aActivityid; "ActivityId"
0x1801505c5  mov     rcx, r14; context
0x1801505c8  call    MI_Context_GetCustomOption
0x1801505cd  xor     r13d, r13d
0x1801505d0  test    eax, eax
0x1801505d2  jnz     short loc_1801505E8
0x1801505d4  mov     rcx, qword ptr [rbp+100h+value]; lpsz
0x1801505d8  lea     rdx, [rbp+100h+ActivityId]; pclsid
0x1801505dc  call    cs:__imp_CLSIDFromString
0x1801505e3  nop     dword ptr [rax+rax+00h]
0x1801505e8  mov     rcx, qword ptr [rbp+100h+ActivityId.Data1]
0x1801505ec  lea     rdx, [rbp+100h+var_C0]; ActivityId
0x1801505f0  mov     rax, qword ptr [rbp+100h+ActivityId.Data4]
0x1801505f4  mov     [rbp+100h+var_D0], rcx
0x1801505f8  mov     qword ptr [rbp+100h+var_C0.Data1], rcx
0x1801505fc  mov     ecx, 4; ControlCode
0x180150601  mov     [rbp+100h+var_C8], rax
0x180150605  mov     qword ptr [rbp+100h+var_C0.Data4], rax
0x180150609  call    cs:__imp_EventActivityIdControl
0x180150610  nop     dword ptr [rax+rax+00h]
0x180150615  mov     eax, cs:dword_18039EB68
0x18015061b  lea     rcx, aWspVolumeInvok_4; "WSP_Volume_Invoke_SetFileSystemLabel"
0x180150622  cmp     eax, 5
0x180150625  jbe     short loc_180150650
0x180150627  lea     rax, [rbp+100h+var_174]
0x18015062b  mov     [rbp+100h+var_174], 4AAh
0x180150632  mov     [rsp+200h+var_1D8], rax
0x180150637  lea     rdx, byte_180355E49
0x18015063e  lea     rax, [rbp+100h+var_168]
0x180150642  mov     [rbp+100h+var_168], rcx
0x180150646  mov     qword ptr [rsp+200h+var_1E0], rax
0x18015064b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180150650  xor     edx, edx; Val
0x180150652  mov     [rsp+200h+var_188], r13d
0x180150657  lea     rcx, [rbp+100h+instance]; void *
0x18015065b  mov     [rbp+100h+var_168], r13
0x18015065f  mov     dword ptr [rbp+100h+var_150], r13d
0x180150663  lea     r8d, [rdx+68h]; Size
0x180150667  call    memset_0
0x18015066c  lea     rcx, [rbp+100h+var_140]; this
0x180150670  mov     [rbp+100h+var_160], r13
0x180150674  mov     rsi, r13
0x180150677  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18015067c  lea     rcx, [rbp+100h+var_140]; this
0x180150680  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180150685  mov     rcx, r14; context
0x180150688  call    WspIsRemoteRequest
0x18015068d  lea     rdi, [rbx+40h]
0x180150691  mov     [rsp+200h+var_184], eax
0x180150695  cmp     [rdi+8], r13b
0x180150699  jz      short loc_1801506AD
0x18015069b  mov     rcx, [rdi]; unsigned __int16 *
0x18015069e  call    WspIsRemoteInstance
0x1801506a3  test    al, al
0x1801506a5  jz      short loc_1801506AD
0x1801506a7  mov     r13d, 1
0x1801506ad  mov     rdx, [rdi]
0x1801506b0  lea     r9, [rbp+100h+var_174]
0x1801506b4  mov     r8d, 1
0x1801506ba  mov     [rbp+100h+var_174], esi
0x1801506bd  mov     rcx, r14; context
0x1801506c0  call    WspProviderEnter
0x1801506c5  mov     ebx, eax
0x1801506c7  test    eax, eax
0x1801506c9  jz      short loc_1801506DE
0x1801506cb  lea     r12, aWspVolumeInvok_4; "WSP_Volume_Invoke_SetFileSystemLabel"
0x1801506d2  lea     rdi, aSetfilesysteml; "SetFileSystemLabel"
0x1801506d9  jmp     loc_180150A51
0x1801506de  mov     rcx, [rdi]; unsigned __int16 *
0x1801506e1  call    WspIsRemoteInstance
0x1801506e6  mov     rcx, [rdi]
0x1801506e9  test    al, al
0x1801506eb  jz      short loc_180150708
0x1801506ed  mov     r9, [rbp+100h+var_148]; unsigned __int16 *
0x1801506f1  mov     r8, rcx; unsigned __int16 *
0x1801506f4  mov     rcx, r14; struct _MI_Context *
0x1801506f7  mov     qword ptr [rsp+200h+var_1E0], r12; void *
0x1801506fc  mov     rdx, r15; unsigned __int16 *
0x1801506ff  call    WspInvokeRemoteMethod
0x180150704  mov     ebx, eax
0x180150706  jmp     short loc_1801506CB
0x180150708  xor     eax, eax
0x18015070a  xorps   xmm0, xmm0
0x18015070d  movups  [rbp+100h+var_E8], xmm0
0x180150711  mov     [rbp+100h+var_D8], eax
0x180150714  mov     [rbp+100h+var_178], eax
0x180150717  call    WspGetSubsystemType
0x18015071c  lea     rcx, [rbp+100h+var_178]
0x180150720  mov     ebx, eax
0x180150722  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x180150727  lea     rdx, [rbp+100h+var_E8]; struct _SUBSYSTEM_INFO *
0x18015072b  mov     ecx, ebx; unsigned int
0x18015072d  mov     r15d, eax
0x180150730  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x180150735  mov     ecx, cs:dword_18039EB68
0x18015073b  cmp     ecx, 5
0x18015073e  jbe     short loc_1801507AD
0x180150740  mov     rdx, 400000000000h
0x18015074a  lea     rcx, dword_18039EB68
0x180150751  call    _tlgKeywordOn
0x180150756  test    al, al
0x180150758  jz      short loc_1801507AD
0x18015075a  xor     eax, eax
0x18015075c  mov     [rsp+200h+var_190], ebx
0x180150760  cmp     r15d, [rbp+100h+var_178]
0x180150764  lea     rdx, byte_18035747F
0x18015076b  setnz   al
0x18015076e  mov     [rsp+200h+var_18C], eax
0x180150772  movzx   eax, word ptr [rbp+100h+var_D8]
0x180150776  mov     word ptr [rbp+100h+var_178], ax
0x18015077a  lea     rax, [rbp+100h+var_E8]
0x18015077e  mov     [rbp+100h+var_180], rax
0x180150782  lea     rax, [rsp+200h+var_18C]
0x180150787  mov     [rsp+200h+var_1C8], rax
0x18015078c  lea     rax, [rbp+100h+var_178]
0x180150790  mov     [rsp+200h+var_1D0], rax
0x180150795  lea     rax, [rsp+200h+var_190]
0x18015079a  mov     [rsp+200h+var_1D8], rax
0x18015079f  lea     rax, [rbp+100h+var_180]
0x1801507a3  mov     qword ptr [rsp+200h+var_1E0], rax
0x1801507a8  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1801507ad  mov     rcx, [rdi]; unsigned __int16 *
0x1801507b0  lea     r9, [rbp+100h+var_168]
0x1801507b4  lea     r8, [rsp+200h+var_190]
0x1801507b9  lea     rdx, [rbp+100h+var_150]
0x1801507bd  call    WspUnpackObjectId
0x1801507c2  mov     r15, [rbp+100h+var_168]
0x1801507c6  mov     ebx, eax
0x1801507c8  test    eax, eax
0x1801507ca  jz      short loc_180150820
0x1801507cc  mov     eax, cs:dword_18039EB68
0x1801507d2  cmp     eax, 2
0x1801507d5  jbe     loc_1801508EF
0x1801507db  mov     [rsp+200h+var_18C], 4C9h
0x1801507e3  lea     rdx, byte_1803575CF
0x1801507ea  lea     rax, [rsp+200h+var_190]
0x1801507ef  mov     [rsp+200h+var_1D0], rax
0x1801507f4  lea     r12, aWspVolumeInvok_4; "WSP_Volume_Invoke_SetFileSystemLabel"
0x1801507fb  lea     rax, [rsp+200h+var_18C]
0x180150800  mov     [rbp+100h+var_180], r12
0x180150804  mov     [rsp+200h+var_1D8], rax
0x180150809  lea     rax, [rbp+100h+var_180]
0x18015080d  mov     qword ptr [rsp+200h+var_1E0], rax
0x180150812  mov     [rsp+200h+var_190], ebx
0x180150816  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18015081b  jmp     loc_1801508F6
0x180150820  lea     r8, [rbp+100h+instance]; instance
0x180150824  mov     rcx, r14; context
0x180150827  lea     rdx, WSP_Volume_SetFileSystemLabel_rtti; methodDecl
0x18015082e  call    MI_Context_ConstructParameters
0x180150833  mov     ebx, eax
0x180150835  test    eax, eax
0x180150837  jz      short loc_180150859
0x180150839  mov     eax, cs:dword_18039EB68
0x18015083f  cmp     eax, 2
0x180150842  jbe     loc_1801508EF
0x180150848  mov     [rsp+200h+var_18C], 4D1h
0x180150850  lea     rdx, word_180356E42
0x180150857  jmp     short loc_1801507EA
0x180150859  lea     r8, [rsp+200h+var_188]; enum SM_RETURN_CODE *
0x18015085e  mov     rcx, r12; struct _WSP_Volume_SetFileSystemLabel *
0x180150861  lea     rdx, [rbp+100h+var_160]; struct _PM_SET_FILESYSTEM_LABEL_PARAMETERS **
0x180150865  call    ?WSP_Volume_Params_SetFileSystemLabel@@YA?AW4_MI_Result@@PEBU_WSP_Volume_SetFileSystemLabel@@PEAPEAU_PM_SET_FILESYSTEM_LABEL_PARAMETERS@@PEAW4SM_RETURN_CODE@@@Z; WSP_Volume_Params_SetFileSystemLabel(_WSP_Volume_SetFileSystemLabel const *,_PM_SET_FILESYSTEM_LABEL_PARAMETERS * *,SM_RETURN_CODE *)
0x18015086a  cmp     dword ptr [rbp+100h+var_150], esi
0x18015086d  mov     rcx, r15
0x180150870  mov     rsi, [rbp+100h+var_160]
0x180150874  mov     rdx, rsi
0x180150877  jnz     short loc_180150880
0x180150879  call    ?PmSetFileSystemLabel@@YA?AW4SM_RETURN_CODE@@PEBGPEBU_PM_SET_FILESYSTEM_LABEL_PARAMETERS@@@Z; PmSetFileSystemLabel(ushort const *,_PM_SET_FILESYSTEM_LABEL_PARAMETERS const *)
0x18015087e  jmp     short loc_180150885
0x180150880  call    ?PmcSetFileSystemLabel@@YA?AW4SM_RETURN_CODE@@PEBGPEBU_PM_SET_FILESYSTEM_LABEL_PARAMETERS@@@Z; PmcSetFileSystemLabel(ushort const *,_PM_SET_FILESYSTEM_LABEL_PARAMETERS const *)
0x180150885  lea     rdx, [rbp+100h+instance]
0x180150889  mov     [rbp+100h+var_70.value], eax
0x18015088f  mov     rcx, r14; self
0x180150892  mov     [rbp+100h+var_70.exists], 1
0x180150899  call    MI_Instance_Destruct
0x18015089e  mov     ebx, eax
0x1801508a0  test    eax, eax
0x1801508a2  jz      short loc_1801508EF
0x1801508a4  mov     eax, cs:dword_18039EB68
0x1801508aa  cmp     eax, 2
0x1801508ad  jbe     short loc_1801508EF
0x1801508af  lea     rax, [rsp+200h+var_188]
0x1801508b4  mov     [rsp+200h+var_188], ebx
0x1801508b8  mov     [rsp+200h+var_1D0], rax
0x1801508bd  lea     r12, aWspVolumeInvok_4; "WSP_Volume_Invoke_SetFileSystemLabel"
0x1801508c4  lea     rax, [rsp+200h+var_190]
0x1801508c9  mov     [rsp+200h+var_190], 4E9h
0x1801508d1  mov     [rsp+200h+var_1D8], rax
0x1801508d6  lea     rdx, dword_18035819C
0x1801508dd  lea     rax, [rbp+100h+var_180]
0x1801508e1  mov     [rbp+100h+var_180], r12
0x1801508e5  mov     qword ptr [rsp+200h+var_1E0], rax
0x1801508ea  jmp     loc_180150816
0x1801508ef  lea     r12, aWspVolumeInvok_4; "WSP_Volume_Invoke_SetFileSystemLabel"
0x1801508f6  lea     rcx, [rbp+100h+var_140]; this
0x1801508fa  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x1801508ff  mov     rdx, [rbp+100h+var_148]; unsigned __int16 *
0x180150903  lea     r9, [rbp+100h+var_70]; struct _MI_ConstUint32Field *
0x18015090a  mov     rcx, [rbp+100h+var_158]; unsigned __int16 *
0x18015090e  mov     r8, rdi; struct _MI_ConstStringField *
0x180150911  mov     [rsp+200h+var_1D8], 0; unsigned __int16 *
0x18015091a  mov     [rsp+200h+var_1E0], ebx; enum _MI_Result
0x18015091e  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x180150923  mov     eax, cs:dword_18039EB68
0x180150929  cmp     eax, 5
0x18015092c  jbe     loc_180150A2C
0x180150932  mov     rdx, 400000000000h
0x18015093c  lea     rcx, dword_18039EB68
0x180150943  call    _tlgKeywordOn
0x180150948  xor     r8d, r8d
0x18015094b  test    al, al
0x18015094d  jz      loc_180150A2C
0x180150953  mov     rax, [rbp+100h+var_138]
0x180150957  xor     edx, edx
0x180150959  sub     rax, [rbp+100h+var_140]
0x18015095d  imul    rax, 3E8h
0x180150964  mov     [rbp+100h+var_158], r8
0x180150968  div     [rbp+100h+var_130]
0x18015096c  mov     [rbp+100h+var_180], r8
0x180150970  mov     [rbp+100h+var_168], rax
0x180150974  mov     al, [rbp+100h+var_70.exists]
0x18015097a  neg     al
0x18015097c  mov     [rbp+100h+var_148], r8
0x180150980  mov     rax, [rbp+100h+var_170]
0x180150984  sbb     ecx, ecx
0x180150986  mov     [rsp+200h+var_188], ebx
0x18015098a  and     ecx, [rbp+100h+var_70.value]
0x180150990  mov     [rsp+200h+var_190], ecx
0x180150994  mov     [rsp+200h+var_18C], r13d
0x180150999  cmp     [rax+48h], r8b
0x18015099d  jz      short loc_1801509A4
0x18015099f  mov     rax, [rdi]
0x1801509a2  jmp     short loc_1801509A7
0x1801509a4  mov     rax, r8
0x1801509a7  mov     [rbp+100h+var_170], rax
0x1801509ab  lea     rdi, aSetfilesysteml; "SetFileSystemLabel"
0x1801509b2  lea     rax, aWspvolume; "WspVolume"
0x1801509b9  mov     [rbp+100h+var_160], rdi
0x1801509bd  mov     [rbp+100h+var_150], rax
0x1801509c1  lea     rdx, byte_180357755
0x1801509c8  lea     rax, [rbp+100h+var_158]
0x1801509cc  mov     [rsp+200h+var_198], rax
0x1801509d1  lea     rax, [rbp+100h+var_180]
0x1801509d5  mov     [rsp+200h+var_1A0], rax
0x1801509da  lea     rax, [rbp+100h+var_148]
0x1801509de  mov     [rsp+200h+var_1A8], rax
0x1801509e3  lea     rax, [rbp+100h+var_168]
0x1801509e7  mov     [rsp+200h+var_1B0], rax
0x1801509ec  lea     rax, [rsp+200h+var_188]
0x1801509f1  mov     [rsp+200h+var_1B8], rax
0x1801509f6  lea     rax, [rsp+200h+var_190]
0x1801509fb  mov     [rsp+200h+var_1C0], rax
0x180150a00  lea     rax, [rsp+200h+var_18C]
0x180150a05  mov     [rsp+200h+var_1C8], rax
0x180150a0a  lea     rax, [rbp+100h+var_170]
0x180150a0e  mov     [rsp+200h+var_1D0], rax
0x180150a13  lea     rax, [rbp+100h+var_160]
0x180150a17  mov     [rsp+200h+var_1D8], rax
0x180150a1c  lea     rax, [rbp+100h+var_150]
0x180150a20  mov     qword ptr [rsp+200h+var_1E0], rax
0x180150a25  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180150a2a  jmp     short loc_180150A33
0x180150a2c  lea     rdi, aSetfilesysteml; "SetFileSystemLabel"
0x180150a33  mov     rcx, r15
0x180150a36  call    WspFreeString
  ... truncated ...
```
