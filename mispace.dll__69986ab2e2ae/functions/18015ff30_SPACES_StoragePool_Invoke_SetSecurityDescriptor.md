# SPACES_StoragePool_Invoke_SetSecurityDescriptor

- ea: `0x18015ff30`
- end: `0x180160475`
- name: `SPACES_StoragePool_Invoke_SetSecurityDescriptor`
- size: `1349`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011c4`
- `0x180001504`
- `0x1800015d8`
- `0x180004608`
- `0x180006350`
- `0x180006dd4`
- `0x18000b840`
- `0x18000ba50`
- `0x18000c644`
- `0x18000cca4`
- `0x18000ccd4`
- `0x180015ea0`
- `0x180015fc0`
- `0x1800179c0`
- `0x18001aa70`
- `0x18001b4a0`
- `0x180021dcc`
- `0x180023e18`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x18015ff30`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015ffad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180160018`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016043e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015ffad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180160018`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016043e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015ffd6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015ffd6`

## string_xrefs

- `0x180160352`: `SetSecurityDescriptor`
- `0x18016002a`: `SPACES_StoragePool_Invoke_SetSecurityDescriptor`
- `0x18016013c`: `SPACES_StoragePool_Invoke_SetSecurityDescriptor`
- `0x18016019d`: `SPACES_StoragePool_Invoke_SetSecurityDescriptor`
- `0x18016020f`: `SPACES_StoragePool_Invoke_SetSecurityDescriptor`
- `0x180160264`: `SPACES_StoragePool_Invoke_SetSecurityDescriptor`
- `0x1801603ec`: `SPACES_StoragePool_Invoke_SetSecurityDescriptor`

## pseudocode

```c
ULONG __fastcall SPACES_StoragePool_Invoke_SetSecurityDescriptor(
        CSpProvider **a1,
        MI_Context *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        const struct _MI_ConstStringField *a6,
        __int64 a7)
{
  const MI_Char *v9; // rdx
  MI_Type *v10; // r8
  int v11; // r8d
  int v12; // r9d
  int v13; // r15d
  int IsRemoteRequest; // r12d
  enum _MI_Result v15; // ebx
  CSpProvider *v16; // rbx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  int v29; // r8d
  int v30; // r9d
  const MI_Char *v31; // rax
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  const char *v36; // [rsp+70h] [rbp-90h] BYREF
  MI_Uint32 v37; // [rsp+78h] [rbp-88h] BYREF
  struct ISpWmiObject *v38; // [rsp+80h] [rbp-80h] BYREF
  const char *v39; // [rsp+88h] [rbp-78h] BYREF
  const char *v40; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v41; // [rsp+98h] [rbp-68h] BYREF
  const char *v42; // [rsp+A0h] [rbp-60h] BYREF
  const MI_Char *v43; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v44; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v45; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v46; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v47[4]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v48; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v49; // [rsp+F8h] [rbp-8h]
  MI_Value value; // [rsp+100h] [rbp+0h] BYREF
  MI_Instance instance; // [rsp+130h] [rbp+30h] BYREF
  struct _MI_ConstUint32Field v52; // [rsp+170h] [rbp+70h] BYREF
  GUID ActivityId; // [rsp+1A0h] [rbp+A0h] BYREF
  GUID v54; // [rsp+1B0h] [rbp+B0h]
  GUID v55; // [rsp+1C0h] [rbp+C0h] BYREF

  v41 = a4;
  v46 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v54 = ActivityId;
  v55 = ActivityId;
  EventActivityIdControl(4u, &v55);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v39) = 2207;
    v36 = "SPACES_StoragePool_Invoke_SetSecurityDescriptor";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StoragePool_Invoke_SetSecurityDescriptor",
      (unsigned int)byte_18035B75D,
      v11,
      v12,
      (__int64)&v36,
      (__int64)&v39);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x60u);
  v48 = 0;
  v49 = 0;
  v38 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
  v38 = 0;
  v13 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v47);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v47);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = 0;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v48) = 11;
    *((_QWORD *)&v48 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v48, &v38, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v39) = v15;
        LODWORD(v42) = 2238;
        v36 = "SPACES_StoragePool_Invoke_SetSecurityDescriptor";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)word_18035D152,
          v18,
          v19,
          (__int64)&v36,
          (__int64)&v42,
          (__int64)&v39);
      }
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_SetSecurityDescriptor_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v43) = v15;
          LODWORD(v44) = 2246;
          v36 = "SPACES_StoragePool_Invoke_SetSecurityDescriptor";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v20,
            (unsigned int)byte_18035B515,
            v21,
            v22,
            (__int64)&v36,
            (__int64)&v44,
            (__int64)&v43);
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v38 + 48LL))(
                v38,
                720903,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_18039EB68 > 2 )
          {
            LODWORD(v45) = v15;
            LODWORD(v40) = 2257;
            v36 = "SPACES_StoragePool_Invoke_SetSecurityDescriptor";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v23,
              (unsigned int)&word_18035D6DE,
              v24,
              v25,
              (__int64)&v36,
              (__int64)&v40,
              (__int64)&v45);
          }
        }
        else
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v37 = v15;
            LODWORD(v36) = 2265;
            v40 = "SPACES_StoragePool_Invoke_SetSecurityDescriptor";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)byte_18035BCC1,
              v27,
              v28,
              (__int64)&v40,
              (__int64)&v36,
              (__int64)&v37);
          }
        }
      }
    }
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v41, v46, a6 + 4, &v52, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v47);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        v41 = 0;
        v46 = 0;
        v45 = 0;
        v44 = (unsigned __int64)(1000LL * (v47[1] - v47[0])) / v47[2];
        LODWORD(v36) = v15;
        v37 = v52.exists != 0 ? v52.value : 0;
        LODWORD(v40) = v13;
        if ( a6[4].exists )
          v31 = a6[4].value;
        else
          v31 = 0;
        v43 = v31;
        v42 = "SetSecurityDescriptor";
        v39 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v52.exists != 0 ? v52.value : 0,
          (unsigned int)word_18035B362,
          v29,
          v30,
          (__int64)&v39,
          (__int64)&v42,
          (__int64)&v43,
          (__int64)&v40,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)&v44,
          (__int64)&v45,
          (__int64)&v46,
          (__int64)&v41);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v36) = 2298;
    v41 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_SetSecurityDescriptor";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v32,
      (unsigned int)byte_18035BEAB,
      v33,
      v34,
      (__int64)&v41,
      (__int64)&v36);
  }
  MI_Context_PostResult_0(a2, v15);
  CSmTimer::~CSmTimer((CSmTimer *)v47);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
  return EventActivityIdControl(4u, &v55);
}

```

## disassembly

```asm
0x18015ff30  mov     [rsp-8+arg_10], rbx
0x18015ff35  push    rbp
0x18015ff36  push    rsi
0x18015ff37  push    rdi
0x18015ff38  push    r12
0x18015ff3a  push    r13
0x18015ff3c  push    r14
0x18015ff3e  push    r15
0x18015ff40  lea     rbp, [rsp-0E0h]
0x18015ff48  sub     rsp, 1E0h
0x18015ff4f  mov     rax, cs:__security_cookie
0x18015ff56  xor     rax, rsp
0x18015ff59  mov     [rbp+110h+var_40], rax
0x18015ff60  mov     [rbp+110h+var_178], r9
0x18015ff64  mov     rsi, rdx
0x18015ff67  mov     rdi, rcx
0x18015ff6a  mov     rax, [rbp+110h+arg_20]
0x18015ff71  mov     [rbp+110h+var_150], rax
0x18015ff75  mov     r14, [rbp+110h+arg_28]
0x18015ff7c  mov     r13, [rbp+110h+arg_30]
0x18015ff83  xorps   xmm0, xmm0
0x18015ff86  xor     eax, eax
0x18015ff88  movups  xmmword ptr [rbp+110h+value], xmm0
0x18015ff8c  movups  xmmword ptr [rbp+110h+value+10h], xmm0
0x18015ff90  mov     qword ptr [rbp+110h+value+20h], rax
0x18015ff94  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18015ff9b  movdqu  xmmword ptr [rbp+110h+ActivityId.Data1], xmm0
0x18015ffa3  lea     rdx, [rbp+110h+ActivityId]; ActivityId
0x18015ffaa  lea     ecx, [rax+1]; ControlCode
0x18015ffad  call    cs:__imp_EventActivityIdControl
0x18015ffb4  nop     dword ptr [rax+rax+00h]
0x18015ffb9  lea     r9, [rbp+110h+value]; value
0x18015ffbd  mov     rcx, rsi; context
0x18015ffc0  call    MI_Context_GetCustomOption_1
0x18015ffc5  xor     ebx, ebx
0x18015ffc7  test    eax, eax
0x18015ffc9  jnz     short loc_18015FFE2
0x18015ffcb  lea     rdx, [rbp+110h+ActivityId]; pclsid
0x18015ffd2  mov     rcx, qword ptr [rbp+110h+value]; lpsz
0x18015ffd6  call    cs:__imp_CLSIDFromString
0x18015ffdd  nop     dword ptr [rax+rax+00h]
0x18015ffe2  mov     rcx, qword ptr [rbp+110h+ActivityId.Data1]
0x18015ffe9  mov     [rbp+110h+var_60], rcx
0x18015fff0  mov     rax, qword ptr [rbp+110h+ActivityId.Data4]
0x18015fff7  mov     [rbp+110h+var_58], rax
0x18015fffe  mov     qword ptr [rbp+110h+var_50.Data1], rcx
0x180160005  mov     qword ptr [rbp+110h+var_50.Data4], rax
0x18016000c  lea     rdx, [rbp+110h+var_50]; ActivityId
0x180160013  mov     ecx, 4; ControlCode
0x180160018  call    cs:__imp_EventActivityIdControl
0x18016001f  nop     dword ptr [rax+rax+00h]
0x180160024  mov     eax, cs:dword_18039EB68
0x18016002a  lea     rcx, aSpacesStoragep_6; "SPACES_StoragePool_Invoke_SetSecurityDe"...
0x180160031  cmp     eax, 5
0x180160034  jbe     short loc_180160061
0x180160036  mov     dword ptr [rbp+110h+var_188], 89Fh
0x18016003d  mov     [rsp+210h+var_1A0], rcx
0x180160042  lea     rax, [rbp+110h+var_188]
0x180160046  mov     [rsp+210h+var_1E8], rax
0x18016004b  lea     rax, [rsp+210h+var_1A0]
0x180160050  mov     qword ptr [rsp+210h+var_1F0], rax
0x180160055  lea     rdx, byte_18035B75D
0x18016005c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180160061  mov     [rbp+110h+instance.ft], rbx
0x180160065  xor     edx, edx; Val
0x180160067  lea     r8d, [rdx+60h]; Size
0x18016006b  lea     rcx, [rbp+110h+instance.classDecl]; void *
0x18016006f  call    memset_0
0x180160074  xorps   xmm0, xmm0
0x180160077  xor     eax, eax
0x180160079  movups  [rbp+110h+var_128], xmm0
0x18016007d  mov     [rbp+110h+var_118], rax
0x180160081  mov     [rbp+110h+var_190], rbx
0x180160085  lea     rcx, [rbp+110h+var_190]
0x180160089  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18016008e  mov     [rbp+110h+var_190], rbx
0x180160092  mov     r15d, ebx
0x180160095  lea     rcx, [rbp+110h+var_148]; this
0x180160099  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18016009e  mov     rcx, rsi; context
0x1801600a1  call    WspIsRemoteRequest
0x1801600a6  mov     r12d, eax
0x1801600a9  test    eax, eax
0x1801600ab  jnz     short loc_1801600D1
0x1801600ad  lea     rcx, [rbp+110h+var_148]; this
0x1801600b1  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x1801600b6  cmp     [r14+48h], bl
0x1801600ba  jz      short loc_1801600CE
0x1801600bc  mov     rcx, [r14+40h]; unsigned __int16 *
0x1801600c0  call    WspIsRemoteInstance
0x1801600c5  test    al, al
0x1801600c7  lea     r15d, [r12+1]
0x1801600cc  jnz     short loc_1801600D1
0x1801600ce  mov     r15d, ebx
0x1801600d1  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x1801600d8  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x1801600dd  mov     ebx, eax
0x1801600df  test    eax, eax
0x1801600e1  jnz     loc_1801602A4
0x1801600e7  mov     dword ptr [rbp+110h+var_128], 0Bh
0x1801600ee  mov     rax, [r14+40h]
0x1801600f2  mov     qword ptr [rbp+110h+var_128+8], rax
0x1801600f6  mov     rbx, [rdi]
0x1801600f9  lea     rcx, [rbp+110h+var_190]
0x1801600fd  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180160102  mov     [rsp+210h+var_1F0], 1; int
0x18016010a  lea     r9, [rbp+110h+var_190]; struct ISpWmiObject **
0x18016010e  lea     r8, [rbp+110h+var_128]; struct _SP_OBJECT_ID *
0x180160112  mov     rdx, rsi; context
0x180160115  mov     rcx, rbx; this
0x180160118  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18016011d  mov     ebx, eax
0x18016011f  test    eax, eax
0x180160121  jz      short loc_18016016B
0x180160123  mov     eax, cs:dword_18039EB68
0x180160129  cmp     eax, 2
0x18016012c  jbe     loc_180160298
0x180160132  mov     dword ptr [rbp+110h+var_188], ebx
0x180160135  mov     dword ptr [rbp+110h+var_170], 8BEh
0x18016013c  lea     rax, aSpacesStoragep_6; "SPACES_StoragePool_Invoke_SetSecurityDe"...
0x180160143  mov     [rsp+210h+var_1A0], rax
0x180160148  lea     rax, [rbp+110h+var_188]
0x18016014c  mov     [rsp+210h+var_1E0], rax
0x180160151  lea     rax, [rbp+110h+var_170]
0x180160155  mov     [rsp+210h+var_1E8], rax
0x18016015a  lea     rax, [rsp+210h+var_1A0]
0x18016015f  lea     rdx, word_18035D152
0x180160166  jmp     loc_18016028E
0x18016016b  lea     r8, [rbp+110h+instance]; instance
0x18016016f  lea     rdx, SPACES_StoragePool_SetSecurityDescriptor_rtti; methodDecl
0x180160176  mov     rcx, rsi; context
0x180160179  call    MI_Context_ConstructParameters
0x18016017e  mov     ebx, eax
0x180160180  test    eax, eax
0x180160182  jz      short loc_1801601CC
0x180160184  mov     eax, cs:dword_18039EB68
0x18016018a  cmp     eax, 2
0x18016018d  jbe     loc_180160298
0x180160193  mov     dword ptr [rbp+110h+var_168], ebx
0x180160196  mov     dword ptr [rbp+110h+var_160], 8C6h
0x18016019d  lea     rax, aSpacesStoragep_6; "SPACES_StoragePool_Invoke_SetSecurityDe"...
0x1801601a4  mov     [rsp+210h+var_1A0], rax
0x1801601a9  lea     rax, [rbp+110h+var_168]
0x1801601ad  mov     [rsp+210h+var_1E0], rax
0x1801601b2  lea     rax, [rbp+110h+var_160]
0x1801601b6  mov     [rsp+210h+var_1E8], rax
0x1801601bb  lea     rax, [rsp+210h+var_1A0]
0x1801601c0  lea     rdx, byte_18035B515
0x1801601c7  jmp     loc_18016028E
0x1801601cc  mov     rcx, [rbp+110h+var_190]
0x1801601d0  mov     rax, [rcx]
0x1801601d3  lea     rdx, [rbp+110h+instance]
0x1801601d7  mov     qword ptr [rsp+210h+var_1F0], rdx
0x1801601dc  mov     r9, r13
0x1801601df  mov     r8, rsi
0x1801601e2  mov     edx, 0B0007h
0x1801601e7  mov     rax, [rax+30h]
0x1801601eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801601f0  mov     ebx, eax
0x1801601f2  test    eax, eax
0x1801601f4  jz      short loc_18016023B
0x1801601f6  mov     eax, cs:dword_18039EB68
0x1801601fc  cmp     eax, 2
0x1801601ff  jbe     loc_180160298
0x180160205  mov     dword ptr [rbp+110h+var_158], ebx
0x180160208  mov     dword ptr [rbp+110h+var_180], 8D1h
0x18016020f  lea     rax, aSpacesStoragep_6; "SPACES_StoragePool_Invoke_SetSecurityDe"...
0x180160216  mov     [rsp+210h+var_1A0], rax
0x18016021b  lea     rax, [rbp+110h+var_158]
0x18016021f  mov     [rsp+210h+var_1E0], rax
0x180160224  lea     rax, [rbp+110h+var_180]
0x180160228  mov     [rsp+210h+var_1E8], rax
0x18016022d  lea     rax, [rsp+210h+var_1A0]
0x180160232  lea     rdx, word_18035D6DE
0x180160239  jmp     short loc_18016028E
0x18016023b  lea     rdx, [rbp+110h+instance]
0x18016023f  mov     rcx, rsi; self
0x180160242  call    MI_Instance_Destruct
0x180160247  mov     ebx, eax
0x180160249  test    eax, eax
0x18016024b  jz      short loc_180160298
0x18016024d  mov     eax, cs:dword_18039EB68
0x180160253  cmp     eax, 2
0x180160256  jbe     short loc_180160298
0x180160258  mov     [rsp+210h+var_198], ebx
0x18016025c  mov     dword ptr [rsp+210h+var_1A0], 8D9h
0x180160264  lea     rax, aSpacesStoragep_6; "SPACES_StoragePool_Invoke_SetSecurityDe"...
0x18016026b  mov     [rbp+110h+var_180], rax
0x18016026f  lea     rax, [rsp+210h+var_198]
0x180160274  mov     [rsp+210h+var_1E0], rax
0x180160279  lea     rax, [rsp+210h+var_1A0]
0x18016027e  mov     [rsp+210h+var_1E8], rax
0x180160283  lea     rax, [rbp+110h+var_180]
0x180160287  lea     rdx, byte_18035BCC1
0x18016028e  mov     qword ptr [rsp+210h+var_1F0], rax
0x180160293  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180160298  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18016029f  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x1801602a4  xor     r13d, r13d
0x1801602a7  mov     [rsp+210h+var_1E8], r13; unsigned __int16 *
0x1801602ac  mov     [rsp+210h+var_1F0], ebx; enum _MI_Result
0x1801602b0  lea     r9, [rbp+110h+var_A0]; struct _MI_ConstUint32Field *
0x1801602b4  lea     r8, [r14+40h]; struct _MI_ConstStringField *
0x1801602b8  mov     rdx, [rbp+110h+var_150]; unsigned __int16 *
0x1801602bc  mov     rcx, [rbp+110h+var_178]; unsigned __int16 *
0x1801602c0  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x1801602c5  test    r12d, r12d
0x1801602c8  jnz     loc_1801603D0
0x1801602ce  lea     rcx, [rbp+110h+var_148]; this
0x1801602d2  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x1801602d7  mov     eax, cs:dword_18039EB68
0x1801602dd  cmp     eax, 5
0x1801602e0  jbe     loc_1801603D0
0x1801602e6  mov     rdx, 400000000000h
0x1801602f0  lea     rcx, dword_18039EB68
0x1801602f7  call    _tlgKeywordOn
0x1801602fc  test    al, al
0x1801602fe  jz      loc_1801603D0
0x180160304  mov     [rbp+110h+var_178], r13
0x180160308  mov     [rbp+110h+var_150], r13
0x18016030c  mov     [rbp+110h+var_158], r13
0x180160310  mov     rax, [rbp+110h+var_140]
0x180160314  sub     rax, [rbp+110h+var_148]
0x180160318  imul    rax, 3E8h
0x18016031f  xor     edx, edx
0x180160321  div     [rbp+110h+var_138]
0x180160325  mov     [rbp+110h+var_160], rax
0x180160329  mov     dword ptr [rsp+210h+var_1A0], ebx
0x18016032d  mov     al, [rbp+110h+var_A0.exists]
0x180160330  neg     al
0x180160332  sbb     ecx, ecx
0x180160334  and     ecx, [rbp+110h+var_A0.value]
0x180160337  mov     [rsp+210h+var_198], ecx
0x18016033b  mov     dword ptr [rbp+110h+var_180], r15d
0x18016033f  cmp     [r14+48h], r13b
0x180160343  jz      short loc_18016034B
0x180160345  mov     rax, [r14+40h]
0x180160349  jmp     short loc_18016034E
0x18016034b  mov     rax, r13
0x18016034e  mov     [rbp+110h+var_168], rax
0x180160352  lea     rax, aSetsecuritydes_0; "SetSecurityDescriptor"
0x180160359  mov     [rbp+110h+var_170], rax
0x18016035d  lea     rax, aStoragepool_0; "StoragePool"
0x180160364  mov     [rbp+110h+var_188], rax
0x180160368  lea     rax, [rbp+110h+var_178]
0x18016036c  mov     [rsp+210h+var_1A8], rax
0x180160371  lea     rax, [rbp+110h+var_150]
0x180160375  mov     [rsp+210h+var_1B0], rax
0x18016037a  lea     rax, [rbp+110h+var_158]
0x18016037e  mov     [rsp+210h+var_1B8], rax
0x180160383  lea     rax, [rbp+110h+var_160]
0x180160387  mov     [rsp+210h+var_1C0], rax
0x18016038c  lea     rax, [rsp+210h+var_1A0]
0x180160391  mov     [rsp+210h+var_1C8], rax
0x180160396  lea     rax, [rsp+210h+var_198]
0x18016039b  mov     [rsp+210h+var_1D0], rax
0x1801603a0  lea     rax, [rbp+110h+var_180]
0x1801603a4  mov     [rsp+210h+var_1D8], rax
0x1801603a9  lea     rax, [rbp+110h+var_168]
0x1801603ad  mov     [rsp+210h+var_1E0], rax
0x1801603b2  lea     rax, [rbp+110h+var_170]
0x1801603b6  mov     [rsp+210h+var_1E8], rax
0x1801603bb  lea     rax, [rbp+110h+var_188]
0x1801603bf  mov     qword ptr [rsp+210h+var_1F0], rax
0x1801603c4  lea     rdx, word_18035B362
0x1801603cb  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1801603d0  lea     rcx, [rbp+110h+instance]; self
0x1801603d4  call    MI_Instance_Destruct
0x1801603d9  mov     eax, cs:dword_18039EB68
0x1801603df  cmp     eax, 5
0x1801603e2  jbe     short loc_180160416
0x1801603e4  mov     dword ptr [rsp+210h+var_1A0], 8FAh
0x1801603ec  lea     rax, aSpacesStoragep_6; "SPACES_StoragePool_Invoke_SetSecurityDe"...
0x1801603f3  mov     [rbp+110h+var_178], rax
0x1801603f7  lea     rax, [rsp+210h+var_1A0]
0x1801603fc  mov     [rsp+210h+var_1E8], rax
0x180160401  lea     rax, [rbp+110h+var_178]
0x180160405  mov     qword ptr [rsp+210h+var_1F0], rax
0x18016040a  lea     rdx, byte_18035BEAB
0x180160411  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180160416  mov     edx, ebx; result
0x180160418  mov     rcx, rsi; context
0x18016041b  call    MI_Context_PostResult_0
0x180160420  lea     rcx, [rbp+110h+var_148]; this
0x180160424  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x180160429  lea     rcx, [rbp+110h+var_190]
0x18016042d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180160432  lea     rdx, [rbp+110h+var_50]; ActivityId
0x180160439  mov     ecx, 4; ControlCode
0x18016043e  call    cs:__imp_EventActivityIdControl
0x180160445  nop     dword ptr [rax+rax+00h]
0x18016044a  mov     rcx, [rbp+110h+var_40]
0x180160451  xor     rcx, rsp; StackCookie
0x180160454  call    __security_check_cookie
0x180160459  mov     rbx, [rsp+210h+arg_10]
0x180160461  add     rsp, 1E0h
0x180160468  pop     r15
0x18016046a  pop     r14
0x18016046c  pop     r13
0x18016046e  pop     r12
  ... truncated ...
```
