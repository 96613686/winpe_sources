# WSP_Partition_Invoke_GetAccessPaths

- ea: `0x1801695a0`
- end: `0x180169c3f`
- name: `WSP_Partition_Invoke_GetAccessPaths`
- size: `1695`
- prototype: ``
- caller_count: `0`
- callee_count: `33`
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
- `0x18000cc78`
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
- `0x18012ac3c`
- `0x18012cea4`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x1801695a0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180169621`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016968c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180169c08`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180169621`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016968c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180169c08`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18016964a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18016964a`

## string_xrefs

- `0x180169a55`: `GetAccessPaths`
- `0x180169b76`: `GetAccessPaths`
- `0x18016969e`: `WSP_Partition_Invoke_GetAccessPaths`
- `0x180169967`: `WSP_Partition_Invoke_GetAccessPaths`
- `0x180169bc1`: `WSP_Partition_Invoke_GetAccessPaths`

## pseudocode

```c
ULONG __fastcall WSP_Partition_Invoke_GetAccessPaths(
        __int64 a1,
        MI_Context *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        const struct _MI_ConstStringField *a6,
        void *a7)
{
  const MI_Char *v9; // rdx
  MI_Type *v10; // r8
  int v11; // r8d
  int v12; // r9d
  unsigned __int16 **v13; // r14
  unsigned int v14; // r12d
  const struct _MI_ConstStringField *v15; // rdi
  char IsRemoteInstance; // al
  enum _MI_Result v17; // ebx
  int v18; // esi
  char v19; // al
  unsigned __int16 *v20; // rcx
  unsigned int SubsystemType; // ebx
  int SubsystemVersion; // esi
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  enum _MI_Result v26; // eax
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  unsigned __int64 v30; // r13
  __int16 *v31; // rdx
  MI_Uint32 AccessPaths; // eax
  MI_Uint32 v33; // esi
  int v34; // r8d
  int v35; // r9d
  bool v36; // zf
  const MI_Char *v37; // rax
  __int64 i; // rdi
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  unsigned __int32 v43; // [rsp+70h] [rbp-90h] BYREF
  MI_Uint32 v44; // [rsp+74h] [rbp-8Ch] BYREF
  int v45; // [rsp+78h] [rbp-88h]
  int IsRemoteRequest; // [rsp+7Ch] [rbp-84h] BYREF
  int v47; // [rsp+80h] [rbp-80h] BYREF
  int v48; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v49; // [rsp+88h] [rbp-78h] BYREF
  const char *v50; // [rsp+90h] [rbp-70h] BYREF
  int v51; // [rsp+98h] [rbp-68h]
  int v52; // [rsp+9Ch] [rbp-64h]
  unsigned __int64 v53; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v54; // [rsp+A8h] [rbp-58h] BYREF
  const char *v55; // [rsp+B0h] [rbp-50h] BYREF
  const char *v56; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v57; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v58; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v59; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v60; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v61; // [rsp+E0h] [rbp-20h]
  MI_Value value; // [rsp+F0h] [rbp-10h] BYREF
  MI_Instance instance; // [rsp+120h] [rbp+20h] BYREF
  struct _MI_ConstUint32Field v64; // [rsp+160h] [rbp+60h] BYREF
  GUID ActivityId; // [rsp+190h] [rbp+90h] BYREF
  __int128 v66; // [rsp+1A0h] [rbp+A0h] BYREF
  int v67; // [rsp+1B0h] [rbp+B0h]
  GUID v68; // [rsp+1B8h] [rbp+B8h]
  GUID v69; // [rsp+1C8h] [rbp+C8h] BYREF

  v58 = a5;
  v57 = a4;
  memset(&value, 0, sizeof(value));
  v53 = (unsigned __int64)a6;
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v68 = ActivityId;
  v69 = ActivityId;
  EventActivityIdControl(4u, &v69);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v49 = 758;
    v54 = (unsigned __int64)"WSP_Partition_Invoke_GetAccessPaths";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"WSP_Partition_Invoke_GetAccessPaths",
      (unsigned int)word_1803623F2,
      v11,
      v12,
      (__int64)&v54,
      (__int64)&v49);
  }
  v54 = 0;
  v48 = 0;
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x68u);
  v56 = 0;
  v13 = 0;
  LODWORD(v55) = 0;
  v14 = 0;
  CSmTimer::CSmTimer((CSmTimer *)&v59);
  CSmTimer::Start((CSmTimer *)&v59);
  v15 = a6 + 4;
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !a6[4].exists
    || (IsRemoteInstance = WspIsRemoteInstance((unsigned __int16 *)v15->value), v45 = 1, !IsRemoteInstance) )
  {
    v45 = 0;
  }
  v49 = 0;
  v17 = (unsigned int)WspProviderEnter(a2);
  if ( v17 )
    goto LABEL_9;
  v19 = WspIsRemoteInstance((unsigned __int16 *)v15->value);
  v20 = (unsigned __int16 *)v15->value;
  if ( v19 )
  {
    v17 = (unsigned int)WspInvokeRemoteMethod(a2, a4, (unsigned __int16 *)v15->value, v58, a7);
LABEL_9:
    v18 = v45;
    goto LABEL_43;
  }
  v66 = 0;
  v67 = 0;
  v47 = 0;
  SubsystemType = WspGetSubsystemType(v20);
  SubsystemVersion = _GetSubsystemVersion(&v47);
  WspGetSubsystemInfo(SubsystemType, (struct _SUBSYSTEM_INFO *)&v66);
  if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
  {
    v43 = SubsystemType;
    v44 = SubsystemVersion != v47;
    LOWORD(v47) = v67;
    v50 = (const char *)&v66;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v23,
      (unsigned int)word_180361012,
      v24,
      v25,
      (__int64)&v50,
      (__int64)&v43,
      (__int64)&v47,
      (__int64)&v44);
  }
  v26 = (unsigned int)WspUnpackObjectId((unsigned __int16 *)v15->value, &v48, &v43, &v54);
  v30 = v54;
  v17 = v26;
  if ( v26 )
  {
    if ( (unsigned int)dword_18039EB68 <= 2 )
      goto LABEL_31;
    v44 = 789;
    v31 = (__int16 *)&dword_1803609F4;
  }
  else
  {
    v17 = MI_Context_ConstructParameters(a2, &WSP_Partition_GetAccessPaths_rtti, &instance);
    if ( v17 )
    {
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_31;
      v44 = 797;
      v31 = &word_1803610E6;
    }
    else
    {
      if ( v48 )
        AccessPaths = PmcGetAccessPaths(v30, &v56, &v55);
      else
        AccessPaths = PmGetAccessPaths(v30, &v56, &v55);
      v13 = (unsigned __int16 **)v56;
      v14 = (unsigned int)v55;
      v33 = AccessPaths;
      v52 = 0;
      v50 = v56;
      v51 = (int)v55;
      v17 = ((unsigned int (__fastcall *)(MI_Instance *, __int64, const char **))instance.ft->SetElementAt)(
              &instance,
              1,
              &v50);
      if ( v17 )
      {
        if ( (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_31;
        v44 = 814;
        v31 = (__int16 *)&unk_180360598;
      }
      else
      {
        v64.value = v33;
        v64.exists = 1;
        v17 = MI_Instance_Destruct((MI_Instance *)a2);
        if ( v17 == MI_RESULT_OK || (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_31;
        v44 = 830;
        v31 = (__int16 *)byte_180361A13;
      }
    }
  }
  v50 = "WSP_Partition_Invoke_GetAccessPaths";
  v43 = v17;
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
    v27,
    (_DWORD)v31,
    v28,
    v29,
    (__int64)&v50,
    (__int64)&v44,
    (__int64)&v43);
LABEL_31:
  CSmTimer::Stop((CSmTimer *)&v59);
  SmLogOnMethodFailure(v57, v58, v15, &v64, v17, 0);
  if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
  {
    v18 = v45;
    v57 = 0;
    v50 = 0;
    v54 = 1000 * (v60 - v59) / v61;
    v58 = 0;
    v43 = v17;
    v44 = v64.exists != 0 ? v64.value : 0;
    v36 = *(_BYTE *)(v53 + 72) == 0;
    v48 = v45;
    if ( v36 )
      v37 = 0;
    else
      v37 = v15->value;
    v53 = (unsigned __int64)v37;
    v56 = "GetAccessPaths";
    v55 = "WspPartition";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v64.exists != 0 ? v64.value : 0,
      (unsigned int)&unk_180361F50,
      v34,
      v35,
      (__int64)&v55,
      (__int64)&v56,
      (__int64)&v53,
      (__int64)&v48,
      (__int64)&v44,
      (__int64)&v43,
      (__int64)&v54,
      (__int64)&v58,
      (__int64)&v50,
      (__int64)&v57);
  }
  else
  {
    v18 = v45;
  }
  for ( i = 0; (unsigned int)i < v14; i = (unsigned int)(i + 1) )
    SmFreeString(&v13[i]);
  if ( v13 )
    operator delete(v13);
  WspFreeString(v30);
  MI_Instance_Destruct(&instance);
LABEL_43:
  MI_Context_PostResult_0(a2, v17);
  WspProviderExit(v49);
  if ( IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)&v59);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        IsRemoteRequest = v18;
        v53 = 1000 * (v60 - v59) / v61;
        v57 = (unsigned __int16 *)"GetAccessPaths";
        v50 = "WspPartition";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v39,
          (unsigned int)word_180362132,
          v40,
          v41,
          (__int64)&v50,
          (__int64)&v57,
          (__int64)&IsRemoteRequest,
          (__int64)&v53);
      }
    }
  }
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    IsRemoteRequest = 883;
    v53 = (unsigned __int64)"WSP_Partition_Invoke_GetAccessPaths";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v39,
      (unsigned int)word_180360D72,
      v40,
      v41,
      (__int64)&v53,
      (__int64)&IsRemoteRequest);
  }
  CSmTimer::~CSmTimer((CSmTimer *)&v59);
  return EventActivityIdControl(4u, &v69);
}

```

## disassembly

```asm
0x1801695a0  mov     [rsp-8+arg_0], rbx
0x1801695a5  push    rbp
0x1801695a6  push    rsi
0x1801695a7  push    rdi
0x1801695a8  push    r12
0x1801695aa  push    r13
0x1801695ac  push    r14
0x1801695ae  push    r15
0x1801695b0  lea     rbp, [rsp-0E0h]
0x1801695b8  sub     rsp, 1E0h
0x1801695bf  mov     rax, cs:__security_cookie
0x1801695c6  xor     rax, rsp
0x1801695c9  mov     [rbp+110h+var_38], rax
0x1801695d0  mov     rax, [rbp+110h+arg_20]
0x1801695d7  xorps   xmm0, xmm0
0x1801695da  mov     rbx, [rbp+110h+arg_28]
0x1801695e1  mov     r15, rdx
0x1801695e4  mov     rsi, [rbp+110h+arg_30]
0x1801695eb  lea     rdx, [rbp+110h+ActivityId]; ActivityId
0x1801695f2  mov     [rbp+110h+var_148], rax
0x1801695f6  mov     r13, r9
0x1801695f9  xor     eax, eax
0x1801695fb  mov     [rbp+110h+var_150], r9
0x1801695ff  movups  xmmword ptr [rbp+110h+value], xmm0
0x180169603  mov     [rbp+110h+var_170], rbx
0x180169607  movups  xmmword ptr [rbp+110h+value+10h], xmm0
0x18016960b  lea     ecx, [rax+1]; ControlCode
0x18016960e  mov     qword ptr [rbp+110h+value+20h], rax
0x180169612  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180169619  movdqu  xmmword ptr [rbp+110h+ActivityId.Data1], xmm0
0x180169621  call    cs:__imp_EventActivityIdControl
0x180169628  nop     dword ptr [rax+rax+00h]
0x18016962d  lea     r9, [rbp+110h+value]; value
0x180169631  mov     rcx, r15; context
0x180169634  call    MI_Context_GetCustomOption_1
0x180169639  xor     edi, edi
0x18016963b  test    eax, eax
0x18016963d  jnz     short loc_180169656
0x18016963f  mov     rcx, qword ptr [rbp+110h+value]; lpsz
0x180169643  lea     rdx, [rbp+110h+ActivityId]; pclsid
0x18016964a  call    cs:__imp_CLSIDFromString
0x180169651  nop     dword ptr [rax+rax+00h]
0x180169656  mov     rcx, qword ptr [rbp+110h+ActivityId.Data1]
0x18016965d  lea     rdx, [rbp+110h+var_48]; ActivityId
0x180169664  mov     rax, qword ptr [rbp+110h+ActivityId.Data4]
0x18016966b  mov     [rbp+110h+var_58], rcx
0x180169672  mov     qword ptr [rbp+110h+var_48.Data1], rcx
0x180169679  mov     ecx, 4; ControlCode
0x18016967e  mov     [rbp+110h+var_50], rax
0x180169685  mov     qword ptr [rbp+110h+var_48.Data4], rax
0x18016968c  call    cs:__imp_EventActivityIdControl
0x180169693  nop     dword ptr [rax+rax+00h]
0x180169698  mov     eax, cs:dword_18039EB68
0x18016969e  lea     rcx, aWspPartitionIn; "WSP_Partition_Invoke_GetAccessPaths"
0x1801696a5  cmp     eax, 5
0x1801696a8  jbe     short loc_1801696D3
0x1801696aa  lea     rax, [rbp+110h+var_188]
0x1801696ae  mov     [rbp+110h+var_188], 2F6h
0x1801696b5  mov     [rsp+210h+var_1E8], rax
0x1801696ba  lea     rdx, word_1803623F2
0x1801696c1  lea     rax, [rbp+110h+var_168]
0x1801696c5  mov     [rbp+110h+var_168], rcx
0x1801696c9  mov     qword ptr [rsp+210h+var_1F0], rax
0x1801696ce  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1801696d3  xor     edx, edx; Val
0x1801696d5  mov     [rbp+110h+var_168], rdi
0x1801696d9  lea     rcx, [rbp+110h+instance.classDecl]; void *
0x1801696dd  mov     [rbp+110h+var_18C], edi
0x1801696e0  mov     [rbp+110h+instance.ft], rdi
0x1801696e4  lea     r8d, [rdx+68h]; Size
0x1801696e8  call    memset_0
0x1801696ed  lea     rcx, [rbp+110h+var_140]; this
0x1801696f1  mov     [rbp+110h+var_158], rdi
0x1801696f5  mov     r14, rdi
0x1801696f8  mov     dword ptr [rbp+110h+var_160], edi
0x1801696fb  mov     r12d, edi
0x1801696fe  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180169703  lea     rcx, [rbp+110h+var_140]; this
0x180169707  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18016970c  mov     rcx, r15; context
0x18016970f  call    WspIsRemoteRequest
0x180169714  lea     rdi, [rbx+40h]
0x180169718  mov     [rsp+210h+var_194], eax
0x18016971c  xor     ebx, ebx
0x18016971e  cmp     [rdi+8], bl
0x180169721  jz      short loc_180169737
0x180169723  mov     rcx, [rdi]; unsigned __int16 *
0x180169726  call    WspIsRemoteInstance
0x18016972b  mov     [rsp+210h+var_198], 1
0x180169733  test    al, al
0x180169735  jnz     short loc_18016973B
0x180169737  mov     [rsp+210h+var_198], ebx
0x18016973b  mov     rdx, [rdi]
0x18016973e  lea     r9, [rbp+110h+var_188]
0x180169742  mov     r8d, 1
0x180169748  mov     [rbp+110h+var_188], ebx
0x18016974b  mov     rcx, r15; context
0x18016974e  call    WspProviderEnter
0x180169753  mov     ebx, eax
0x180169755  test    eax, eax
0x180169757  jz      short loc_180169762
0x180169759  mov     esi, [rsp+210h+var_198]
0x18016975d  jmp     loc_180169B07
0x180169762  mov     rcx, [rdi]; unsigned __int16 *
0x180169765  call    WspIsRemoteInstance
0x18016976a  mov     rcx, [rdi]
0x18016976d  test    al, al
0x18016976f  jz      short loc_18016978C
0x180169771  mov     r9, [rbp+110h+var_148]; unsigned __int16 *
0x180169775  mov     r8, rcx; unsigned __int16 *
0x180169778  mov     rcx, r15; struct _MI_Context *
0x18016977b  mov     qword ptr [rsp+210h+var_1F0], rsi; void *
0x180169780  mov     rdx, r13; unsigned __int16 *
0x180169783  call    WspInvokeRemoteMethod
0x180169788  mov     ebx, eax
0x18016978a  jmp     short loc_180169759
0x18016978c  xor     eax, eax
0x18016978e  xorps   xmm0, xmm0
0x180169791  movups  [rbp+110h+var_70], xmm0
0x180169798  mov     [rbp+110h+var_60], eax
0x18016979e  mov     [rbp+110h+var_190], eax
0x1801697a1  call    WspGetSubsystemType
0x1801697a6  lea     rcx, [rbp+110h+var_190]
0x1801697aa  mov     ebx, eax
0x1801697ac  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1801697b1  lea     rdx, [rbp+110h+var_70]; struct _SUBSYSTEM_INFO *
0x1801697b8  mov     ecx, ebx; unsigned int
0x1801697ba  mov     esi, eax
0x1801697bc  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1801697c1  mov     ecx, cs:dword_18039EB68
0x1801697c7  cmp     ecx, 5
0x1801697ca  jbe     short loc_18016983E
0x1801697cc  mov     rdx, 400000000000h
0x1801697d6  lea     rcx, dword_18039EB68
0x1801697dd  call    _tlgKeywordOn
0x1801697e2  test    al, al
0x1801697e4  jz      short loc_18016983E
0x1801697e6  xor     eax, eax
0x1801697e8  mov     [rsp+210h+var_1A0], ebx
0x1801697ec  cmp     esi, [rbp+110h+var_190]
0x1801697ef  lea     rdx, word_180361012
0x1801697f6  setnz   al
0x1801697f9  mov     [rsp+210h+var_19C], eax
0x1801697fd  movzx   eax, word ptr [rbp+110h+var_60]
0x180169804  mov     word ptr [rbp+110h+var_190], ax
0x180169808  lea     rax, [rbp+110h+var_70]
0x18016980f  mov     [rbp+110h+var_180], rax
0x180169813  lea     rax, [rsp+210h+var_19C]
0x180169818  mov     [rsp+210h+var_1D8], rax
0x18016981d  lea     rax, [rbp+110h+var_190]
0x180169821  mov     [rsp+210h+var_1E0], rax
0x180169826  lea     rax, [rsp+210h+var_1A0]
0x18016982b  mov     [rsp+210h+var_1E8], rax
0x180169830  lea     rax, [rbp+110h+var_180]
0x180169834  mov     qword ptr [rsp+210h+var_1F0], rax
0x180169839  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18016983e  mov     rcx, [rdi]; unsigned __int16 *
0x180169841  lea     r9, [rbp+110h+var_168]
0x180169845  lea     r8, [rsp+210h+var_1A0]
0x18016984a  lea     rdx, [rbp+110h+var_18C]
0x18016984e  call    WspUnpackObjectId
0x180169853  mov     r13, [rbp+110h+var_168]
0x180169857  mov     ebx, eax
0x180169859  test    eax, eax
0x18016985b  jz      short loc_180169880
0x18016985d  mov     eax, cs:dword_18039EB68
0x180169863  cmp     eax, 2
0x180169866  jbe     loc_180169998
0x18016986c  mov     [rsp+210h+var_19C], 315h
0x180169874  lea     rdx, dword_1803609F4
0x18016987b  jmp     loc_180169967
0x180169880  lea     r8, [rbp+110h+instance]; instance
0x180169884  mov     rcx, r15; context
0x180169887  lea     rdx, WSP_Partition_GetAccessPaths_rtti; methodDecl
0x18016988e  call    MI_Context_ConstructParameters
0x180169893  mov     ebx, eax
0x180169895  test    eax, eax
0x180169897  jz      short loc_1801698BC
0x180169899  mov     eax, cs:dword_18039EB68
0x18016989f  cmp     eax, 2
0x1801698a2  jbe     loc_180169998
0x1801698a8  mov     [rsp+210h+var_19C], 31Dh
0x1801698b0  lea     rdx, word_1803610E6
0x1801698b7  jmp     loc_180169967
0x1801698bc  xor     ebx, ebx
0x1801698be  lea     r8, [rbp+110h+var_160]
0x1801698c2  lea     rdx, [rbp+110h+var_158]
0x1801698c6  mov     rcx, r13
0x1801698c9  cmp     [rbp+110h+var_18C], ebx
0x1801698cc  jnz     short loc_1801698D5
0x1801698ce  call    ?PmGetAccessPaths@@YA?AW4SM_RETURN_CODE@@PEBGPEAPEAPEAGPEAK@Z; PmGetAccessPaths(ushort const *,ushort * * *,ulong *)
0x1801698d3  jmp     short loc_1801698DA
0x1801698d5  call    ?PmcGetAccessPaths@@YA?AW4SM_RETURN_CODE@@PEBGPEAPEAPEAGPEAK@Z; PmcGetAccessPaths(ushort const *,ushort * * *,ulong *)
0x1801698da  mov     r14, [rbp+110h+var_158]
0x1801698de  lea     r8, [rbp+110h+var_180]
0x1801698e2  mov     r12d, dword ptr [rbp+110h+var_160]
0x1801698e6  lea     rcx, [rbp+110h+instance]
0x1801698ea  mov     esi, eax
0x1801698ec  mov     [rbp+110h+var_174], ebx
0x1801698ef  mov     rax, [rbp+110h+instance.ft]
0x1801698f3  mov     r9d, 1Dh
0x1801698f9  mov     [rbp+110h+var_180], r14
0x1801698fd  mov     [rbp+110h+var_178], r12d
0x180169901  mov     [rsp+210h+var_1F0], ebx
0x180169905  mov     rax, [rax+50h]
0x180169909  lea     edx, [r9-1Ch]
0x18016990d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180169912  mov     ebx, eax
0x180169914  test    eax, eax
0x180169916  jz      short loc_180169934
0x180169918  mov     eax, cs:dword_18039EB68
0x18016991e  cmp     eax, 2
0x180169921  jbe     short loc_180169998
0x180169923  mov     [rsp+210h+var_19C], 32Eh
0x18016992b  lea     rdx, unk_180360598
0x180169932  jmp     short loc_180169967
0x180169934  lea     rdx, [rbp+110h+instance]
0x180169938  mov     [rbp+110h+var_B0.value], esi
0x18016993b  mov     rcx, r15; self
0x18016993e  mov     [rbp+110h+var_B0.exists], 1
0x180169942  call    MI_Instance_Destruct
0x180169947  mov     ebx, eax
0x180169949  test    eax, eax
0x18016994b  jz      short loc_180169998
0x18016994d  mov     eax, cs:dword_18039EB68
0x180169953  cmp     eax, 2
0x180169956  jbe     short loc_180169998
0x180169958  mov     [rsp+210h+var_19C], 33Eh
0x180169960  lea     rdx, byte_180361A13
0x180169967  lea     rax, aWspPartitionIn; "WSP_Partition_Invoke_GetAccessPaths"
0x18016996e  mov     [rbp+110h+var_180], rax
0x180169972  lea     rax, [rsp+210h+var_1A0]
0x180169977  mov     [rsp+210h+var_1E0], rax
0x18016997c  lea     rax, [rsp+210h+var_19C]
0x180169981  mov     [rsp+210h+var_1E8], rax
0x180169986  lea     rax, [rbp+110h+var_180]
0x18016998a  mov     qword ptr [rsp+210h+var_1F0], rax
0x18016998f  mov     [rsp+210h+var_1A0], ebx
0x180169993  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180169998  lea     rcx, [rbp+110h+var_140]; this
0x18016999c  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x1801699a1  mov     rdx, [rbp+110h+var_148]; unsigned __int16 *
0x1801699a5  lea     r9, [rbp+110h+var_B0]; struct _MI_ConstUint32Field *
0x1801699a9  mov     rcx, [rbp+110h+var_150]; unsigned __int16 *
0x1801699ad  mov     r8, rdi; struct _MI_ConstStringField *
0x1801699b0  mov     [rsp+210h+var_1E8], 0; unsigned __int16 *
0x1801699b9  mov     [rsp+210h+var_1F0], ebx; enum _MI_Result
0x1801699bd  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x1801699c2  mov     eax, cs:dword_18039EB68
0x1801699c8  cmp     eax, 5
0x1801699cb  jbe     loc_180169ACE
0x1801699d1  mov     rdx, 400000000000h
0x1801699db  lea     rcx, dword_18039EB68
0x1801699e2  call    _tlgKeywordOn
0x1801699e7  test    al, al
0x1801699e9  jz      loc_180169ACE
0x1801699ef  mov     rax, [rbp+110h+var_138]
0x1801699f3  xor     edx, edx
0x1801699f5  sub     rax, [rbp+110h+var_140]
0x1801699f9  mov     esi, [rsp+210h+var_198]
0x1801699fd  imul    rax, 3E8h
0x180169a04  mov     [rbp+110h+var_150], 0
0x180169a0c  div     [rbp+110h+var_130]
0x180169a10  mov     [rbp+110h+var_180], 0
0x180169a18  mov     [rbp+110h+var_168], rax
0x180169a1c  mov     al, [rbp+110h+var_B0.exists]
0x180169a1f  neg     al
0x180169a21  mov     [rbp+110h+var_148], 0
0x180169a29  mov     rax, [rbp+110h+var_170]
0x180169a2d  sbb     ecx, ecx
0x180169a2f  mov     [rsp+210h+var_1A0], ebx
0x180169a33  and     ecx, [rbp+110h+var_B0.value]
0x180169a36  mov     [rsp+210h+var_19C], ecx
0x180169a3a  cmp     byte ptr [rax+48h], 0
0x180169a3e  mov     [rbp+110h+var_18C], esi
0x180169a41  jz      short loc_180169A48
0x180169a43  mov     rax, [rdi]
0x180169a46  jmp     short loc_180169A4A
0x180169a48  xor     eax, eax
0x180169a4a  mov     [rbp+110h+var_170], rax
0x180169a4e  lea     rdx, unk_180361F50
0x180169a55  lea     rax, aGetaccesspaths_0; "GetAccessPaths"
0x180169a5c  mov     [rbp+110h+var_158], rax
0x180169a60  lea     rax, aWsppartition; "WspPartition"
0x180169a67  mov     [rbp+110h+var_160], rax
0x180169a6b  lea     rax, [rbp+110h+var_150]
0x180169a6f  mov     [rsp+210h+var_1A8], rax
0x180169a74  lea     rax, [rbp+110h+var_180]
0x180169a78  mov     [rsp+210h+var_1B0], rax
0x180169a7d  lea     rax, [rbp+110h+var_148]
0x180169a81  mov     [rsp+210h+var_1B8], rax
0x180169a86  lea     rax, [rbp+110h+var_168]
0x180169a8a  mov     [rsp+210h+var_1C0], rax
0x180169a8f  lea     rax, [rsp+210h+var_1A0]
0x180169a94  mov     [rsp+210h+var_1C8], rax
0x180169a99  lea     rax, [rsp+210h+var_19C]
0x180169a9e  mov     [rsp+210h+var_1D0], rax
0x180169aa3  lea     rax, [rbp+110h+var_18C]
0x180169aa7  mov     [rsp+210h+var_1D8], rax
0x180169aac  lea     rax, [rbp+110h+var_170]
  ... truncated ...
```
