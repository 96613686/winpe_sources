# WSP_Volume_Invoke_DeleteObject

- ea: `0x180149950`
- end: `0x180149f29`
- name: `WSP_Volume_Invoke_DeleteObject`
- size: `1497`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011c4`
- `0x180001504`
- `0x1800015d8`
- `0x180001994`
- `0x180004608`
- `0x180004c3c`
- `0x180006350`
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
- `0x180122c88`
- `0x18013c4e8`
- `0x18013c50c`
- `0x180149950`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801499c7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180149a24`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180149ef2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801499c7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180149a24`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180149ef2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801499f7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801499f7`

## string_xrefs

- `0x180149ad9`: `DeleteVolume`
- `0x180149d60`: `DeleteVolume`
- `0x180149de8`: `DeleteVolume`
- `0x180149a36`: `WSP_Volume_Invoke_DeleteObject`
- `0x180149c86`: `WSP_Volume_Invoke_DeleteObject`
- `0x180149eae`: `WSP_Volume_Invoke_DeleteObject`

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
  int v10; // r8d
  int v11; // r9d
  unsigned __int16 **v12; // rdi
  enum _MI_Result v13; // ebx
  char IsRemoteInstance; // al
  unsigned __int16 *v15; // rcx
  unsigned int SubsystemType; // ebx
  int SubsystemVersion; // r14d
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  char *v24; // rdx
  MI_Uint32 v25; // eax
  int v26; // r8d
  int v27; // r9d
  unsigned __int16 *v28; // rax
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  unsigned __int32 v33; // [rsp+70h] [rbp-90h] BYREF
  MI_Uint32 v34; // [rsp+74h] [rbp-8Ch] BYREF
  int IsRemoteRequest; // [rsp+78h] [rbp-88h] BYREF
  int v36; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v37; // [rsp+80h] [rbp-80h] BYREF
  const char *v38; // [rsp+88h] [rbp-78h] BYREF
  __int64 v39; // [rsp+90h] [rbp-70h] BYREF
  const char *v40; // [rsp+98h] [rbp-68h] BYREF
  const char *v41; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v42; // [rsp+A8h] [rbp-58h] BYREF
  const char *v43; // [rsp+B0h] [rbp-50h] BYREF
  const char *v44; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v45; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v46; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v47; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v48; // [rsp+E0h] [rbp-20h] BYREF
  MI_Value value; // [rsp+E8h] [rbp-18h] BYREF
  GUID ActivityId; // [rsp+110h] [rbp+10h] BYREF
  __int128 v51; // [rsp+120h] [rbp+20h] BYREF
  int v52; // [rsp+130h] [rbp+30h]
  GUID v53; // [rsp+138h] [rbp+38h]
  GUID v54; // [rsp+148h] [rbp+48h] BYREF
  MI_Instance instance; // [rsp+160h] [rbp+60h] BYREF
  struct _MI_ConstUint32Field v56; // [rsp+1A0h] [rbp+A0h] BYREF

  v42 = a5;
  memset(&value, 0, sizeof(value));
  v9 = 1;
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption(a2, L"ActivityId", 0, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v53 = ActivityId;
  v54 = ActivityId;
  EventActivityIdControl(4u, &v54);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v37 = 1916;
    v40 = "WSP_Volume_Invoke_DeleteObject";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"WSP_Volume_Invoke_DeleteObject",
      (unsigned int)byte_18035598B,
      v10,
      v11,
      (__int64)&v40,
      (__int64)&v37);
  }
  v40 = 0;
  v36 = 0;
  memset_0(&instance, 0, 0x68u);
  CSmTimer::CSmTimer((CSmTimer *)&v45);
  CSmTimer::Start((CSmTimer *)&v45);
  v12 = (unsigned __int16 **)&a6[4];
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !a6[4].exists || !(unsigned __int8)WspIsRemoteInstance(*v12) )
    v9 = 0;
  v37 = 0;
  v13 = (unsigned int)WspProviderEnter(a2);
  if ( v13 == MI_RESULT_OK )
  {
    IsRemoteInstance = WspIsRemoteInstance(*v12);
    v15 = *v12;
    if ( IsRemoteInstance )
    {
      v13 = (unsigned int)WspInvokeRemoteMethod(a2, a4, *v12, v42, a7);
      goto LABEL_34;
    }
    v51 = 0;
    v52 = 0;
    LODWORD(v39) = 0;
    SubsystemType = WspGetSubsystemType(v15);
    SubsystemVersion = _GetSubsystemVersion(&v39);
    WspGetSubsystemInfo(SubsystemType, (struct _SUBSYSTEM_INFO *)&v51);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v33 = SubsystemType;
      v34 = SubsystemVersion != v39;
      LOWORD(v39) = v52;
      v38 = (const char *)&v51;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v18,
        (unsigned int)&unk_180357FF8,
        v19,
        v20,
        (__int64)&v38,
        (__int64)&v33,
        (__int64)&v39,
        (__int64)&v34);
    }
    v13 = (unsigned int)WspUnpackObjectId(*v12, &v36, &v33, &v40);
    if ( v13 )
    {
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_27;
      v34 = 1946;
      v24 = &byte_18035691F;
    }
    else
    {
      v13 = MI_Context_ConstructParameters(a2, &WSP_Volume_DeleteObject_rtti, &instance);
      if ( v13 )
      {
        if ( (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_27;
        v34 = 1954;
        v24 = &byte_180358237;
      }
      else
      {
        if ( v36 )
          v25 = PmcDeleteVolume(v40);
        else
          v25 = 1;
        v56.value = v25;
        v56.exists = 1;
        v13 = MI_Instance_Destruct((MI_Instance *)a2);
        if ( v13 == MI_RESULT_OK || (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_27;
        v34 = 1976;
        v24 = &byte_180356367;
      }
    }
    v38 = "WSP_Volume_Invoke_DeleteObject";
    v33 = v13;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v21,
      (_DWORD)v24,
      v22,
      v23,
      (__int64)&v38,
      (__int64)&v34,
      (__int64)&v33);
LABEL_27:
    CSmTimer::Stop((CSmTimer *)&v45);
    SmLogOnMethodFailure(a4, v42, a6 + 4, &v56, v13, 0);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v38 = 0;
      v42 = 0;
      v48 = 1000 * (v46 - v45) / v47;
      v39 = 0;
      v33 = v13;
      v36 = v9;
      v34 = v56.exists != 0 ? v56.value : 0;
      if ( a6[4].exists )
        v28 = *v12;
      else
        v28 = 0;
      v43 = (const char *)v28;
      v44 = "DeleteVolume";
      v41 = "WspVolume";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v56.exists != 0 ? v56.value : 0,
        (unsigned int)&unk_180357980,
        v26,
        v27,
        (__int64)&v41,
        (__int64)&v44,
        (__int64)&v43,
        (__int64)&v36,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v48,
        (__int64)&v39,
        (__int64)&v42,
        (__int64)&v38);
    }
    WspFreeString(v40);
    MI_Instance_Destruct(&instance);
  }
LABEL_34:
  MI_Context_PostResult_0(a2, v13);
  WspProviderExit(v37);
  if ( IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)&v45);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        IsRemoteRequest = v9;
        v44 = "DeleteVolume";
        v41 = (const char *)(1000 * (v46 - v45) / v47);
        v43 = "WspVolume";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v29,
          (unsigned int)byte_180356461,
          v30,
          v31,
          (__int64)&v43,
          (__int64)&v44,
          (__int64)&IsRemoteRequest,
          (__int64)&v41);
      }
    }
  }
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    IsRemoteRequest = 2020;
    v41 = "WSP_Volume_Invoke_DeleteObject";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v29,
      (unsigned int)qword_180357B08,
      v30,
      v31,
      (__int64)&v41,
      (__int64)&IsRemoteRequest);
  }
  CSmTimer::~CSmTimer((CSmTimer *)&v45);
  return EventActivityIdControl(4u, &v54);
}

```

## disassembly

```asm
0x180149950  mov     [rsp-8+arg_0], rbx
0x180149955  push    rbp
0x180149956  push    rsi
0x180149957  push    rdi
0x180149958  push    r12
0x18014995a  push    r13
0x18014995c  push    r14
0x18014995e  push    r15
0x180149960  lea     rbp, [rsp-0E0h]
0x180149968  sub     rsp, 1E0h
0x18014996f  mov     rax, cs:__security_cookie
0x180149976  xor     rax, rsp
0x180149979  mov     [rbp+110h+var_40], rax
0x180149980  mov     rax, [rbp+110h+arg_20]
0x180149987  xorps   xmm0, xmm0
0x18014998a  mov     r13, [rbp+110h+arg_28]
0x180149991  mov     rsi, rdx
0x180149994  mov     r14, [rbp+110h+arg_30]
0x18014999b  lea     rdx, [rbp+110h+ActivityId]; ActivityId
0x18014999f  mov     [rbp+110h+var_168], rax
0x1801499a3  mov     r12, r9
0x1801499a6  xor     eax, eax
0x1801499a8  movups  xmmword ptr [rbp+110h+value], xmm0
0x1801499ac  mov     qword ptr [rbp+110h+value+20h], rax
0x1801499b0  movups  xmmword ptr [rbp+110h+value+10h], xmm0
0x1801499b4  lea     r15d, [rax+1]
0x1801499b8  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801499bf  mov     ecx, r15d; ControlCode
0x1801499c2  movdqu  xmmword ptr [rbp+110h+ActivityId.Data1], xmm0
0x1801499c7  call    cs:__imp_EventActivityIdControl
0x1801499ce  nop     dword ptr [rax+rax+00h]
0x1801499d3  lea     r9, [rbp+110h+value]; value
0x1801499d7  xor     r8d, r8d; valueType
0x1801499da  lea     rdx, aActivityid; "ActivityId"
0x1801499e1  mov     rcx, rsi; context
0x1801499e4  call    MI_Context_GetCustomOption
0x1801499e9  xor     ebx, ebx
0x1801499eb  test    eax, eax
0x1801499ed  jnz     short loc_180149A03
0x1801499ef  mov     rcx, qword ptr [rbp+110h+value]; lpsz
0x1801499f3  lea     rdx, [rbp+110h+ActivityId]; pclsid
0x1801499f7  call    cs:__imp_CLSIDFromString
0x1801499fe  nop     dword ptr [rax+rax+00h]
0x180149a03  mov     rcx, qword ptr [rbp+110h+ActivityId.Data1]
0x180149a07  lea     rdx, [rbp+110h+var_C8]; ActivityId
0x180149a0b  mov     rax, qword ptr [rbp+110h+ActivityId.Data4]
0x180149a0f  mov     [rbp+110h+var_D8], rcx
0x180149a13  mov     qword ptr [rbp+110h+var_C8.Data1], rcx
0x180149a17  mov     ecx, 4; ControlCode
0x180149a1c  mov     [rbp+110h+var_D0], rax
0x180149a20  mov     qword ptr [rbp+110h+var_C8.Data4], rax
0x180149a24  call    cs:__imp_EventActivityIdControl
0x180149a2b  nop     dword ptr [rax+rax+00h]
0x180149a30  mov     eax, cs:dword_18039EB68
0x180149a36  lea     rcx, aWspVolumeInvok_3; "WSP_Volume_Invoke_DeleteObject"
0x180149a3d  cmp     eax, 5
0x180149a40  jbe     short loc_180149A6B
0x180149a42  lea     rax, [rbp+110h+var_190]
0x180149a46  mov     [rbp+110h+var_190], 77Ch
0x180149a4d  mov     [rsp+210h+var_1E8], rax
0x180149a52  lea     rdx, byte_18035598B
0x180149a59  lea     rax, [rbp+110h+var_178]
0x180149a5d  mov     [rbp+110h+var_178], rcx
0x180149a61  mov     qword ptr [rsp+210h+var_1F0], rax
0x180149a66  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180149a6b  xor     edx, edx; Val
0x180149a6d  mov     [rbp+110h+var_178], rbx
0x180149a71  lea     rcx, [rbp+110h+instance]; void *
0x180149a75  mov     [rsp+210h+var_194], ebx
0x180149a79  lea     r8d, [rdx+68h]; Size
0x180149a7d  call    memset_0
0x180149a82  lea     rcx, [rbp+110h+var_150]; this
0x180149a86  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180149a8b  lea     rcx, [rbp+110h+var_150]; this
0x180149a8f  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180149a94  mov     rcx, rsi; context
0x180149a97  call    WspIsRemoteRequest
0x180149a9c  lea     rdi, [r13+40h]
0x180149aa0  mov     [rsp+210h+var_198], eax
0x180149aa4  cmp     [rdi+8], bl
0x180149aa7  jz      short loc_180149AB5
0x180149aa9  mov     rcx, [rdi]; unsigned __int16 *
0x180149aac  call    WspIsRemoteInstance
0x180149ab1  test    al, al
0x180149ab3  jnz     short loc_180149AB8
0x180149ab5  mov     r15d, ebx
0x180149ab8  mov     rdx, [rdi]
0x180149abb  lea     r9, [rbp+110h+var_190]
0x180149abf  mov     r8d, 1
0x180149ac5  mov     [rbp+110h+var_190], ebx
0x180149ac8  mov     rcx, rsi; context
0x180149acb  call    WspProviderEnter
0x180149ad0  mov     ebx, eax
0x180149ad2  test    eax, eax
0x180149ad4  jz      short loc_180149AEC
0x180149ad6  xor     r14d, r14d
0x180149ad9  lea     rdi, aDeletevolume; "DeleteVolume"
0x180149ae0  lea     r12, aWspvolume; "WspVolume"
0x180149ae7  jmp     loc_180149E01
0x180149aec  mov     rcx, [rdi]; unsigned __int16 *
0x180149aef  call    WspIsRemoteInstance
0x180149af4  mov     rcx, [rdi]
0x180149af7  test    al, al
0x180149af9  jz      short loc_180149B16
0x180149afb  mov     r9, [rbp+110h+var_168]; unsigned __int16 *
0x180149aff  mov     r8, rcx; unsigned __int16 *
0x180149b02  mov     rcx, rsi; struct _MI_Context *
0x180149b05  mov     qword ptr [rsp+210h+var_1F0], r14; void *
0x180149b0a  mov     rdx, r12; unsigned __int16 *
0x180149b0d  call    WspInvokeRemoteMethod
0x180149b12  mov     ebx, eax
0x180149b14  jmp     short loc_180149AD6
0x180149b16  xor     eax, eax
0x180149b18  xorps   xmm0, xmm0
0x180149b1b  movups  [rbp+110h+var_F0], xmm0
0x180149b1f  mov     [rbp+110h+var_E0], eax
0x180149b22  mov     dword ptr [rbp+110h+var_180], eax
0x180149b25  call    WspGetSubsystemType
0x180149b2a  lea     rcx, [rbp+110h+var_180]
0x180149b2e  mov     ebx, eax
0x180149b30  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x180149b35  lea     rdx, [rbp+110h+var_F0]; struct _SUBSYSTEM_INFO *
0x180149b39  mov     ecx, ebx; unsigned int
0x180149b3b  mov     r14d, eax
0x180149b3e  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x180149b43  mov     ecx, cs:dword_18039EB68
0x180149b49  cmp     ecx, 5
0x180149b4c  jbe     short loc_180149BBB
0x180149b4e  mov     rdx, 400000000000h
0x180149b58  lea     rcx, dword_18039EB68
0x180149b5f  call    _tlgKeywordOn
0x180149b64  test    al, al
0x180149b66  jz      short loc_180149BBB
0x180149b68  xor     eax, eax
0x180149b6a  mov     [rsp+210h+var_1A0], ebx
0x180149b6e  cmp     r14d, dword ptr [rbp+110h+var_180]
0x180149b72  lea     rdx, unk_180357FF8
0x180149b79  setnz   al
0x180149b7c  mov     [rsp+210h+var_19C], eax
0x180149b80  movzx   eax, word ptr [rbp+110h+var_E0]
0x180149b84  mov     word ptr [rbp+110h+var_180], ax
0x180149b88  lea     rax, [rbp+110h+var_F0]
0x180149b8c  mov     [rbp+110h+var_188], rax
0x180149b90  lea     rax, [rsp+210h+var_19C]
0x180149b95  mov     [rsp+210h+var_1D8], rax
0x180149b9a  lea     rax, [rbp+110h+var_180]
0x180149b9e  mov     [rsp+210h+var_1E0], rax
0x180149ba3  lea     rax, [rsp+210h+var_1A0]
0x180149ba8  mov     [rsp+210h+var_1E8], rax
0x180149bad  lea     rax, [rbp+110h+var_188]
0x180149bb1  mov     qword ptr [rsp+210h+var_1F0], rax
0x180149bb6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x180149bbb  mov     rcx, [rdi]; unsigned __int16 *
0x180149bbe  lea     r9, [rbp+110h+var_178]
0x180149bc2  lea     r8, [rsp+210h+var_1A0]
0x180149bc7  lea     rdx, [rsp+210h+var_194]
0x180149bcc  call    WspUnpackObjectId
0x180149bd1  xor     r14d, r14d
0x180149bd4  mov     ebx, eax
0x180149bd6  test    eax, eax
0x180149bd8  jz      short loc_180149BFD
0x180149bda  mov     eax, cs:dword_18039EB68
0x180149be0  cmp     eax, 2
0x180149be3  jbe     loc_180149CB7
0x180149be9  mov     [rsp+210h+var_19C], 79Ah
0x180149bf1  lea     rdx, byte_18035691F
0x180149bf8  jmp     loc_180149C86
0x180149bfd  lea     r8, [rbp+110h+instance]; instance
0x180149c01  mov     rcx, rsi; context
0x180149c04  lea     rdx, WSP_Volume_DeleteObject_rtti; methodDecl
0x180149c0b  call    MI_Context_ConstructParameters
0x180149c10  mov     ebx, eax
0x180149c12  test    eax, eax
0x180149c14  jz      short loc_180149C36
0x180149c16  mov     eax, cs:dword_18039EB68
0x180149c1c  cmp     eax, 2
0x180149c1f  jbe     loc_180149CB7
0x180149c25  mov     [rsp+210h+var_19C], 7A2h
0x180149c2d  lea     rdx, byte_180358237
0x180149c34  jmp     short loc_180149C86
0x180149c36  cmp     [rsp+210h+var_194], r14d
0x180149c3b  jnz     short loc_180149C44
0x180149c3d  mov     eax, 1
0x180149c42  jmp     short loc_180149C4D
0x180149c44  mov     rcx, [rbp+110h+var_178]
0x180149c48  call    ?PmcDeleteVolume@@YA?AW4SM_RETURN_CODE@@PEBG@Z; PmcDeleteVolume(ushort const *)
0x180149c4d  lea     rdx, [rbp+110h+instance]
0x180149c51  mov     [rbp+110h+var_70.value], eax
0x180149c57  mov     rcx, rsi; self
0x180149c5a  mov     [rbp+110h+var_70.exists], 1
0x180149c61  call    MI_Instance_Destruct
0x180149c66  mov     ebx, eax
0x180149c68  test    eax, eax
0x180149c6a  jz      short loc_180149CB7
0x180149c6c  mov     eax, cs:dword_18039EB68
0x180149c72  cmp     eax, 2
0x180149c75  jbe     short loc_180149CB7
0x180149c77  mov     [rsp+210h+var_19C], 7B8h
0x180149c7f  lea     rdx, byte_180356367
0x180149c86  lea     rax, aWspVolumeInvok_3; "WSP_Volume_Invoke_DeleteObject"
0x180149c8d  mov     [rbp+110h+var_188], rax
0x180149c91  lea     rax, [rsp+210h+var_1A0]
0x180149c96  mov     [rsp+210h+var_1E0], rax
0x180149c9b  lea     rax, [rsp+210h+var_19C]
0x180149ca0  mov     [rsp+210h+var_1E8], rax
0x180149ca5  lea     rax, [rbp+110h+var_188]
0x180149ca9  mov     qword ptr [rsp+210h+var_1F0], rax
0x180149cae  mov     [rsp+210h+var_1A0], ebx
0x180149cb2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180149cb7  lea     rcx, [rbp+110h+var_150]; this
0x180149cbb  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180149cc0  mov     rdx, [rbp+110h+var_168]; unsigned __int16 *
0x180149cc4  lea     r9, [rbp+110h+var_70]; struct _MI_ConstUint32Field *
0x180149ccb  mov     r8, rdi; struct _MI_ConstStringField *
0x180149cce  mov     [rsp+210h+var_1E8], r14; unsigned __int16 *
0x180149cd3  mov     rcx, r12; unsigned __int16 *
0x180149cd6  mov     [rsp+210h+var_1F0], ebx; enum _MI_Result
0x180149cda  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x180149cdf  mov     eax, cs:dword_18039EB68
0x180149ce5  cmp     eax, 5
0x180149ce8  jbe     loc_180149DE1
0x180149cee  mov     rdx, 400000000000h
0x180149cf8  lea     rcx, dword_18039EB68
0x180149cff  call    _tlgKeywordOn
0x180149d04  test    al, al
0x180149d06  jz      loc_180149DE1
0x180149d0c  mov     rax, [rbp+110h+var_148]
0x180149d10  xor     edx, edx
0x180149d12  sub     rax, [rbp+110h+var_150]
0x180149d16  imul    rax, 3E8h
0x180149d1d  mov     [rbp+110h+var_188], r14
0x180149d21  div     [rbp+110h+var_140]
0x180149d25  mov     [rbp+110h+var_168], r14
0x180149d29  mov     [rbp+110h+var_130], rax
0x180149d2d  mov     al, [rbp+110h+var_70.exists]
0x180149d33  neg     al
0x180149d35  mov     [rbp+110h+var_180], r14
0x180149d39  mov     [rsp+210h+var_1A0], ebx
0x180149d3d  sbb     ecx, ecx
0x180149d3f  mov     [rsp+210h+var_194], r15d
0x180149d44  and     ecx, [rbp+110h+var_70.value]
0x180149d4a  mov     [rsp+210h+var_19C], ecx
0x180149d4e  cmp     [r13+48h], r14b
0x180149d52  jz      short loc_180149D59
0x180149d54  mov     rax, [rdi]
0x180149d57  jmp     short loc_180149D5C
0x180149d59  mov     rax, r14
0x180149d5c  mov     [rbp+110h+var_160], rax
0x180149d60  lea     rdi, aDeletevolume; "DeleteVolume"
0x180149d67  lea     rax, [rbp+110h+var_188]
0x180149d6b  mov     [rbp+110h+var_158], rdi
0x180149d6f  mov     [rsp+210h+var_1A8], rax
0x180149d74  lea     r12, aWspvolume; "WspVolume"
0x180149d7b  lea     rax, [rbp+110h+var_168]
0x180149d7f  mov     [rbp+110h+var_170], r12
0x180149d83  mov     [rsp+210h+var_1B0], rax
0x180149d88  lea     rdx, unk_180357980
0x180149d8f  lea     rax, [rbp+110h+var_180]
0x180149d93  mov     [rsp+210h+var_1B8], rax
0x180149d98  lea     rax, [rbp+110h+var_130]
0x180149d9c  mov     [rsp+210h+var_1C0], rax
0x180149da1  lea     rax, [rsp+210h+var_1A0]
0x180149da6  mov     [rsp+210h+var_1C8], rax
0x180149dab  lea     rax, [rsp+210h+var_19C]
0x180149db0  mov     [rsp+210h+var_1D0], rax
0x180149db5  lea     rax, [rsp+210h+var_194]
0x180149dba  mov     [rsp+210h+var_1D8], rax
0x180149dbf  lea     rax, [rbp+110h+var_160]
0x180149dc3  mov     [rsp+210h+var_1E0], rax
0x180149dc8  lea     rax, [rbp+110h+var_158]
0x180149dcc  mov     [rsp+210h+var_1E8], rax
0x180149dd1  lea     rax, [rbp+110h+var_170]
0x180149dd5  mov     qword ptr [rsp+210h+var_1F0], rax
0x180149dda  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180149ddf  jmp     short loc_180149DEF
0x180149de1  lea     r12, aWspvolume; "WspVolume"
0x180149de8  lea     rdi, aDeletevolume; "DeleteVolume"
0x180149def  mov     rcx, [rbp+110h+var_178]
0x180149df3  call    WspFreeString
0x180149df8  lea     rcx, [rbp+110h+instance]; self
0x180149dfc  call    MI_Instance_Destruct
0x180149e01  mov     edx, ebx; result
0x180149e03  mov     rcx, rsi; context
0x180149e06  call    MI_Context_PostResult_0
0x180149e0b  mov     ecx, [rbp+110h+var_190]
0x180149e0e  call    WspProviderExit
0x180149e13  cmp     [rsp+210h+var_198], r14d
0x180149e18  jz      loc_180149EA3
0x180149e1e  lea     rcx, [rbp+110h+var_150]; this
0x180149e22  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180149e27  mov     eax, cs:dword_18039EB68
0x180149e2d  cmp     eax, 5
0x180149e30  jbe     short loc_180149EA3
0x180149e32  mov     rdx, 400000000000h
0x180149e3c  lea     rcx, dword_18039EB68
0x180149e43  call    _tlgKeywordOn
0x180149e48  test    al, al
0x180149e4a  jz      short loc_180149EA3
0x180149e4c  mov     rax, [rbp+110h+var_148]
0x180149e50  xor     edx, edx
  ... truncated ...
```
