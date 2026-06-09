# SPACES_StorageTier_Invoke_RemoveStorageFaultDomain

- ea: `0x18017c3e0`
- end: `0x18017c952`
- name: `SPACES_StorageTier_Invoke_RemoveStorageFaultDomain`
- size: `1394`
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
- `0x1800179c0`
- `0x18001aa70`
- `0x18001b4a0`
- `0x180021dcc`
- `0x1800226ac`
- `0x180023e18`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x18017c3e0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017c45a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017c4ad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017c91b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017c45a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017c4ad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017c91b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18017c480`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18017c480`

## string_xrefs

- `0x18017c832`: `RemoveStorageFaultDomain`
- `0x18017c4bf`: `SPACES_StorageTier_Invoke_RemoveStorageFaultDomain`
- `0x18017c5bb`: `SPACES_StorageTier_Invoke_RemoveStorageFaultDomain`
- `0x18017c61d`: `SPACES_StorageTier_Invoke_RemoveStorageFaultDomain`
- `0x18017c67e`: `SPACES_StorageTier_Invoke_RemoveStorageFaultDomain`
- `0x18017c6f0`: `SPACES_StorageTier_Invoke_RemoveStorageFaultDomain`
- `0x18017c745`: `SPACES_StorageTier_Invoke_RemoveStorageFaultDomain`
- `0x18017c8cc`: `SPACES_StorageTier_Invoke_RemoveStorageFaultDomain`

## pseudocode

```c
ULONG __fastcall SPACES_StorageTier_Invoke_RemoveStorageFaultDomain(
        CSpProvider **a1,
        MI_Context *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        const struct _MI_ConstStringField *a6,
        __int64 a7)
{
  int v10; // r15d
  const MI_Char *v11; // rdx
  MI_Type *v12; // r8
  int v13; // r8d
  int v14; // r9d
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
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  int v32; // r8d
  int v33; // r9d
  const MI_Char *v34; // rax
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  const char *v39; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+78h] [rbp-88h] BYREF
  MI_Uint32 v41; // [rsp+7Ch] [rbp-84h] BYREF
  struct ISpWmiObject *v42; // [rsp+80h] [rbp-80h] BYREF
  const char *v43; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v44; // [rsp+90h] [rbp-70h] BYREF
  const char *v45; // [rsp+98h] [rbp-68h] BYREF
  const char *v46; // [rsp+A0h] [rbp-60h] BYREF
  const MI_Char *v47; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v48; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v50; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v51[4]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v52; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v53; // [rsp+F8h] [rbp-8h]
  MI_Value value; // [rsp+100h] [rbp+0h] BYREF
  GUID ActivityId; // [rsp+128h] [rbp+28h] BYREF
  GUID v56; // [rsp+138h] [rbp+38h]
  GUID v57; // [rsp+148h] [rbp+48h] BYREF
  MI_Instance instance; // [rsp+160h] [rbp+60h] BYREF
  struct _MI_ConstUint32Field v59; // [rsp+1A0h] [rbp+A0h] BYREF

  v44 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  v10 = 1;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v11, v12, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v56 = ActivityId;
  v57 = ActivityId;
  EventActivityIdControl(4u, &v57);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v40 = 1245;
    v39 = "SPACES_StorageTier_Invoke_RemoveStorageFaultDomain";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StorageTier_Invoke_RemoveStorageFaultDomain",
      (unsigned int)byte_180367711,
      v13,
      v14,
      (__int64)&v39,
      (__int64)&v40);
  }
  v52 = 0;
  v53 = 0;
  memset_0(&instance, 0, 0x80u);
  CSmTimer::CSmTimer((CSmTimer *)v51);
  v42 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v42);
  v42 = 0;
  CSmTimer::Start((CSmTimer *)v51);
  if ( !a6[4].exists || !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value) )
    v10 = 0;
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v52) = 12;
    *((_QWORD *)&v52 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v42);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v52, &v42, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v40 = v15;
        LODWORD(v45) = 1274;
        v39 = "SPACES_StorageTier_Invoke_RemoveStorageFaultDomain";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&word_180367E6E,
          v18,
          v19,
          (__int64)&v39,
          (__int64)&v45,
          (__int64)&v40);
      }
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, a6[4].value) >= 3 )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StorageTier_RemoveStorageFaultDomain_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v48) = v15;
          LODWORD(v49) = 1291;
          v39 = "SPACES_StorageTier_Invoke_RemoveStorageFaultDomain";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v23,
            (unsigned int)&unk_180366D40,
            v24,
            v25,
            (__int64)&v39,
            (__int64)&v49,
            (__int64)&v48);
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v42 + 48LL))(
                v42,
                786442,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_18039EB68 > 2 )
          {
            LODWORD(v50) = v15;
            LODWORD(v43) = 1302;
            v39 = "SPACES_StorageTier_Invoke_RemoveStorageFaultDomain";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)byte_18036802D,
              v27,
              v28,
              (__int64)&v39,
              (__int64)&v43,
              (__int64)&v50);
          }
        }
        else
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v41 = v15;
            LODWORD(v39) = 1310;
            v43 = "SPACES_StorageTier_Invoke_RemoveStorageFaultDomain";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v29,
              (unsigned int)&unk_180367260,
              v30,
              v31,
              (__int64)&v43,
              (__int64)&v39,
              (__int64)&v41);
          }
        }
      }
    }
    else
    {
      v15 = MI_RESULT_NOT_SUPPORTED;
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v46) = 7;
        LODWORD(v47) = 1283;
        v39 = "SPACES_StorageTier_Invoke_RemoveStorageFaultDomain";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v20,
          (unsigned int)byte_1803680CD,
          v21,
          v22,
          (__int64)&v39,
          (__int64)&v47,
          (__int64)&v46);
      }
    }
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(a4, v44, a6 + 4, &v59, v15, 0);
  CSmTimer::Stop((CSmTimer *)v51);
  if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
  {
    v44 = 0;
    v50 = 0;
    v49 = 0;
    v48 = (unsigned __int64)(1000LL * (v51[1] - v51[0])) / v51[2];
    LODWORD(v39) = v15;
    v41 = v59.exists != 0 ? v59.value : 0;
    LODWORD(v43) = v10;
    if ( a6[4].exists )
      v34 = a6[4].value;
    else
      v34 = 0;
    v47 = v34;
    v46 = "RemoveStorageFaultDomain";
    v45 = "StorageTier";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v59.exists != 0 ? v59.value : 0,
      (unsigned int)&byte_1803672FF,
      v32,
      v33,
      (__int64)&v45,
      (__int64)&v46,
      (__int64)&v47,
      (__int64)&v43,
      (__int64)&v41,
      (__int64)&v39,
      (__int64)&v48,
      (__int64)&v49,
      (__int64)&v50,
      (__int64)&v44);
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v39) = 1344;
    v44 = (unsigned __int16 *)"SPACES_StorageTier_Invoke_RemoveStorageFaultDomain";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v35,
      (unsigned int)byte_1803684C5,
      v36,
      v37,
      (__int64)&v44,
      (__int64)&v39);
  }
  MI_Context_PostResult_0(a2, v15);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v42);
  CSmTimer::~CSmTimer((CSmTimer *)v51);
  return EventActivityIdControl(4u, &v57);
}

```

## disassembly

```asm
0x18017c3e0  mov     [rsp-8+arg_10], rbx
0x18017c3e5  push    rbp
0x18017c3e6  push    rsi
0x18017c3e7  push    rdi
0x18017c3e8  push    r12
0x18017c3ea  push    r13
0x18017c3ec  push    r14
0x18017c3ee  push    r15
0x18017c3f0  lea     rbp, [rsp-0F0h]
0x18017c3f8  sub     rsp, 1F0h
0x18017c3ff  mov     rax, cs:__security_cookie
0x18017c406  xor     rax, rsp
0x18017c409  mov     [rbp+120h+var_40], rax
0x18017c410  mov     r13, r9
0x18017c413  mov     rsi, rdx
0x18017c416  mov     rdi, rcx
0x18017c419  mov     rax, [rbp+120h+arg_20]
0x18017c420  mov     [rbp+120h+var_190], rax
0x18017c424  mov     r14, [rbp+120h+arg_28]
0x18017c42b  mov     r12, [rbp+120h+arg_30]
0x18017c432  xorps   xmm0, xmm0
0x18017c435  xor     eax, eax
0x18017c437  movups  xmmword ptr [rbp+120h+value], xmm0
0x18017c43b  movups  xmmword ptr [rbp+120h+value+10h], xmm0
0x18017c43f  mov     qword ptr [rbp+120h+value+20h], rax
0x18017c443  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18017c44a  movdqu  xmmword ptr [rbp+120h+ActivityId.Data1], xmm0
0x18017c44f  lea     rdx, [rbp+120h+ActivityId]; ActivityId
0x18017c453  lea     r15d, [rax+1]
0x18017c457  mov     ecx, r15d; ControlCode
0x18017c45a  call    cs:__imp_EventActivityIdControl
0x18017c461  nop     dword ptr [rax+rax+00h]
0x18017c466  lea     r9, [rbp+120h+value]; value
0x18017c46a  mov     rcx, rsi; context
0x18017c46d  call    MI_Context_GetCustomOption_1
0x18017c472  xor     ebx, ebx
0x18017c474  test    eax, eax
0x18017c476  jnz     short loc_18017C48C
0x18017c478  lea     rdx, [rbp+120h+ActivityId]; pclsid
0x18017c47c  mov     rcx, qword ptr [rbp+120h+value]; lpsz
0x18017c480  call    cs:__imp_CLSIDFromString
0x18017c487  nop     dword ptr [rax+rax+00h]
0x18017c48c  mov     rcx, qword ptr [rbp+120h+ActivityId.Data1]
0x18017c490  mov     [rbp+120h+var_E8], rcx
0x18017c494  mov     rax, qword ptr [rbp+120h+ActivityId.Data4]
0x18017c498  mov     [rbp+120h+var_E0], rax
0x18017c49c  mov     qword ptr [rbp+120h+var_D8.Data1], rcx
0x18017c4a0  mov     qword ptr [rbp+120h+var_D8.Data4], rax
0x18017c4a4  lea     rdx, [rbp+120h+var_D8]; ActivityId
0x18017c4a8  mov     ecx, 4; ControlCode
0x18017c4ad  call    cs:__imp_EventActivityIdControl
0x18017c4b4  nop     dword ptr [rax+rax+00h]
0x18017c4b9  mov     eax, cs:dword_18039EB68
0x18017c4bf  lea     rcx, aSpacesStoraget_9; "SPACES_StorageTier_Invoke_RemoveStorage"...
0x18017c4c6  cmp     eax, 5
0x18017c4c9  jbe     short loc_18017C4F8
0x18017c4cb  mov     [rsp+220h+var_1A8], 4DDh
0x18017c4d3  mov     [rsp+220h+var_1B0], rcx
0x18017c4d8  lea     rax, [rsp+220h+var_1A8]
0x18017c4dd  mov     [rsp+220h+var_1F8], rax
0x18017c4e2  lea     rax, [rsp+220h+var_1B0]
0x18017c4e7  mov     qword ptr [rsp+220h+var_200], rax
0x18017c4ec  lea     rdx, byte_180367711
0x18017c4f3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18017c4f8  xorps   xmm0, xmm0
0x18017c4fb  xor     eax, eax
0x18017c4fd  movups  [rbp+120h+var_138], xmm0
0x18017c501  mov     [rbp+120h+var_128], rax
0x18017c505  xor     edx, edx; Val
0x18017c507  mov     r8d, 80h; Size
0x18017c50d  lea     rcx, [rbp+120h+instance]; void *
0x18017c511  call    memset_0
0x18017c516  lea     rcx, [rbp+120h+var_158]; this
0x18017c51a  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18017c51f  mov     [rbp+120h+var_1A0], rbx
0x18017c523  lea     rcx, [rbp+120h+var_1A0]
0x18017c527  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18017c52c  mov     [rbp+120h+var_1A0], rbx
0x18017c530  lea     rcx, [rbp+120h+var_158]; this
0x18017c534  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18017c539  cmp     [r14+48h], bl
0x18017c53d  jz      short loc_18017C54C
0x18017c53f  mov     rcx, [r14+40h]; unsigned __int16 *
0x18017c543  call    WspIsRemoteInstance
0x18017c548  test    al, al
0x18017c54a  jnz     short loc_18017C54F
0x18017c54c  mov     r15d, ebx
0x18017c54f  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18017c556  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18017c55b  mov     ebx, eax
0x18017c55d  test    eax, eax
0x18017c55f  jnz     loc_18017C785
0x18017c565  mov     dword ptr [rbp+120h+var_138], 0Ch
0x18017c56c  mov     rax, [r14+40h]
0x18017c570  mov     qword ptr [rbp+120h+var_138+8], rax
0x18017c574  mov     rbx, [rdi]
0x18017c577  lea     rcx, [rbp+120h+var_1A0]
0x18017c57b  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18017c580  mov     [rsp+220h+var_200], 1; int
0x18017c588  lea     r9, [rbp+120h+var_1A0]; struct ISpWmiObject **
0x18017c58c  lea     r8, [rbp+120h+var_138]; struct _SP_OBJECT_ID *
0x18017c590  mov     rdx, rsi; context
0x18017c593  mov     rcx, rbx; this
0x18017c596  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18017c59b  mov     ebx, eax
0x18017c59d  test    eax, eax
0x18017c59f  jz      short loc_18017C5EB
0x18017c5a1  mov     eax, cs:dword_18039EB68
0x18017c5a7  cmp     eax, 2
0x18017c5aa  jbe     loc_18017C779
0x18017c5b0  mov     [rsp+220h+var_1A8], ebx
0x18017c5b4  mov     dword ptr [rbp+120h+var_188], 4FAh
0x18017c5bb  lea     rax, aSpacesStoraget_9; "SPACES_StorageTier_Invoke_RemoveStorage"...
0x18017c5c2  mov     [rsp+220h+var_1B0], rax
0x18017c5c7  lea     rax, [rsp+220h+var_1A8]
0x18017c5cc  mov     [rsp+220h+var_1F0], rax
0x18017c5d1  lea     rax, [rbp+120h+var_188]
0x18017c5d5  mov     [rsp+220h+var_1F8], rax
0x18017c5da  lea     rax, [rsp+220h+var_1B0]
0x18017c5df  lea     rdx, word_180367E6E
0x18017c5e6  jmp     loc_18017C76F
0x18017c5eb  mov     r8, [r14+40h]
0x18017c5ef  mov     rdx, rsi
0x18017c5f2  mov     rcx, [rdi]
0x18017c5f5  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x18017c5fa  cmp     eax, 3
0x18017c5fd  jnb     short loc_18017C64C
0x18017c5ff  mov     ebx, 7
0x18017c604  mov     eax, cs:dword_18039EB68
0x18017c60a  cmp     eax, 2
0x18017c60d  jbe     loc_18017C779
0x18017c613  mov     dword ptr [rbp+120h+var_180], ebx
0x18017c616  mov     dword ptr [rbp+120h+var_178], 503h
0x18017c61d  lea     rax, aSpacesStoraget_9; "SPACES_StorageTier_Invoke_RemoveStorage"...
0x18017c624  mov     [rsp+220h+var_1B0], rax
0x18017c629  lea     rax, [rbp+120h+var_180]
0x18017c62d  mov     [rsp+220h+var_1F0], rax
0x18017c632  lea     rax, [rbp+120h+var_178]
0x18017c636  mov     [rsp+220h+var_1F8], rax
0x18017c63b  lea     rax, [rsp+220h+var_1B0]
0x18017c640  lea     rdx, byte_1803680CD
0x18017c647  jmp     loc_18017C76F
0x18017c64c  lea     r8, [rbp+120h+instance]; instance
0x18017c650  lea     rdx, SPACES_StorageTier_RemoveStorageFaultDomain_rtti; methodDecl
0x18017c657  mov     rcx, rsi; context
0x18017c65a  call    MI_Context_ConstructParameters
0x18017c65f  mov     ebx, eax
0x18017c661  test    eax, eax
0x18017c663  jz      short loc_18017C6AD
0x18017c665  mov     eax, cs:dword_18039EB68
0x18017c66b  cmp     eax, 2
0x18017c66e  jbe     loc_18017C779
0x18017c674  mov     dword ptr [rbp+120h+var_170], ebx
0x18017c677  mov     dword ptr [rbp+120h+var_168], 50Bh
0x18017c67e  lea     rax, aSpacesStoraget_9; "SPACES_StorageTier_Invoke_RemoveStorage"...
0x18017c685  mov     [rsp+220h+var_1B0], rax
0x18017c68a  lea     rax, [rbp+120h+var_170]
0x18017c68e  mov     [rsp+220h+var_1F0], rax
0x18017c693  lea     rax, [rbp+120h+var_168]
0x18017c697  mov     [rsp+220h+var_1F8], rax
0x18017c69c  lea     rax, [rsp+220h+var_1B0]
0x18017c6a1  lea     rdx, unk_180366D40
0x18017c6a8  jmp     loc_18017C76F
0x18017c6ad  mov     rcx, [rbp+120h+var_1A0]
0x18017c6b1  mov     rax, [rcx]
0x18017c6b4  lea     rdx, [rbp+120h+instance]
0x18017c6b8  mov     qword ptr [rsp+220h+var_200], rdx
0x18017c6bd  mov     r9, r12
0x18017c6c0  mov     r8, rsi
0x18017c6c3  mov     edx, 0C000Ah
0x18017c6c8  mov     rax, [rax+30h]
0x18017c6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017c6d1  mov     ebx, eax
0x18017c6d3  test    eax, eax
0x18017c6d5  jz      short loc_18017C71C
0x18017c6d7  mov     eax, cs:dword_18039EB68
0x18017c6dd  cmp     eax, 2
0x18017c6e0  jbe     loc_18017C779
0x18017c6e6  mov     dword ptr [rbp+120h+var_160], ebx
0x18017c6e9  mov     dword ptr [rbp+120h+var_198], 516h
0x18017c6f0  lea     rax, aSpacesStoraget_9; "SPACES_StorageTier_Invoke_RemoveStorage"...
0x18017c6f7  mov     [rsp+220h+var_1B0], rax
0x18017c6fc  lea     rax, [rbp+120h+var_160]
0x18017c700  mov     [rsp+220h+var_1F0], rax
0x18017c705  lea     rax, [rbp+120h+var_198]
0x18017c709  mov     [rsp+220h+var_1F8], rax
0x18017c70e  lea     rax, [rsp+220h+var_1B0]
0x18017c713  lea     rdx, byte_18036802D
0x18017c71a  jmp     short loc_18017C76F
0x18017c71c  lea     rdx, [rbp+120h+instance]
0x18017c720  mov     rcx, rsi; self
0x18017c723  call    MI_Instance_Destruct
0x18017c728  mov     ebx, eax
0x18017c72a  test    eax, eax
0x18017c72c  jz      short loc_18017C779
0x18017c72e  mov     eax, cs:dword_18039EB68
0x18017c734  cmp     eax, 2
0x18017c737  jbe     short loc_18017C779
0x18017c739  mov     [rsp+220h+var_1A4], ebx
0x18017c73d  mov     dword ptr [rsp+220h+var_1B0], 51Eh
0x18017c745  lea     rax, aSpacesStoraget_9; "SPACES_StorageTier_Invoke_RemoveStorage"...
0x18017c74c  mov     [rbp+120h+var_198], rax
0x18017c750  lea     rax, [rsp+220h+var_1A4]
0x18017c755  mov     [rsp+220h+var_1F0], rax
0x18017c75a  lea     rax, [rsp+220h+var_1B0]
0x18017c75f  mov     [rsp+220h+var_1F8], rax
0x18017c764  lea     rax, [rbp+120h+var_198]
0x18017c768  lea     rdx, unk_180367260
0x18017c76f  mov     qword ptr [rsp+220h+var_200], rax
0x18017c774  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18017c779  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18017c780  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18017c785  xor     r12d, r12d
0x18017c788  mov     [rsp+220h+var_1F8], r12; unsigned __int16 *
0x18017c78d  mov     [rsp+220h+var_200], ebx; enum _MI_Result
0x18017c791  lea     r9, [rbp+120h+var_80]; struct _MI_ConstUint32Field *
0x18017c798  lea     r8, [r14+40h]; struct _MI_ConstStringField *
0x18017c79c  mov     rdx, [rbp+120h+var_190]; unsigned __int16 *
0x18017c7a0  mov     rcx, r13; unsigned __int16 *
0x18017c7a3  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18017c7a8  lea     rcx, [rbp+120h+var_158]; this
0x18017c7ac  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18017c7b1  mov     eax, cs:dword_18039EB68
0x18017c7b7  cmp     eax, 5
0x18017c7ba  jbe     loc_18017C8B0
0x18017c7c0  mov     rdx, 400000000000h
0x18017c7ca  lea     rcx, dword_18039EB68
0x18017c7d1  call    _tlgKeywordOn
0x18017c7d6  test    al, al
0x18017c7d8  jz      loc_18017C8B0
0x18017c7de  mov     [rbp+120h+var_190], r12
0x18017c7e2  mov     [rbp+120h+var_160], r12
0x18017c7e6  mov     [rbp+120h+var_168], r12
0x18017c7ea  mov     rax, [rbp+120h+var_150]
0x18017c7ee  sub     rax, [rbp+120h+var_158]
0x18017c7f2  imul    rax, 3E8h
0x18017c7f9  xor     edx, edx
0x18017c7fb  div     [rbp+120h+var_148]
0x18017c7ff  mov     [rbp+120h+var_170], rax
0x18017c803  mov     dword ptr [rsp+220h+var_1B0], ebx
0x18017c807  mov     al, [rbp+120h+var_80.exists]
0x18017c80d  neg     al
0x18017c80f  sbb     ecx, ecx
0x18017c811  and     ecx, [rbp+120h+var_80.value]
0x18017c817  mov     [rsp+220h+var_1A4], ecx
0x18017c81b  mov     dword ptr [rbp+120h+var_198], r15d
0x18017c81f  cmp     [r14+48h], r12b
0x18017c823  jz      short loc_18017C82B
0x18017c825  mov     rax, [r14+40h]
0x18017c829  jmp     short loc_18017C82E
0x18017c82b  mov     rax, r12
0x18017c82e  mov     [rbp+120h+var_178], rax
0x18017c832  lea     rax, aRemovestoragef_0; "RemoveStorageFaultDomain"
0x18017c839  mov     [rbp+120h+var_180], rax
0x18017c83d  lea     rax, aStoragetier; "StorageTier"
0x18017c844  mov     [rbp+120h+var_188], rax
0x18017c848  lea     rax, [rbp+120h+var_190]
0x18017c84c  mov     [rsp+220h+var_1B8], rax
0x18017c851  lea     rax, [rbp+120h+var_160]
0x18017c855  mov     [rsp+220h+var_1C0], rax
0x18017c85a  lea     rax, [rbp+120h+var_168]
0x18017c85e  mov     [rsp+220h+var_1C8], rax
0x18017c863  lea     rax, [rbp+120h+var_170]
0x18017c867  mov     [rsp+220h+var_1D0], rax
0x18017c86c  lea     rax, [rsp+220h+var_1B0]
0x18017c871  mov     [rsp+220h+var_1D8], rax
0x18017c876  lea     rax, [rsp+220h+var_1A4]
0x18017c87b  mov     [rsp+220h+var_1E0], rax
0x18017c880  lea     rax, [rbp+120h+var_198]
0x18017c884  mov     [rsp+220h+var_1E8], rax
0x18017c889  lea     rax, [rbp+120h+var_178]
0x18017c88d  mov     [rsp+220h+var_1F0], rax
0x18017c892  lea     rax, [rbp+120h+var_180]
0x18017c896  mov     [rsp+220h+var_1F8], rax
0x18017c89b  lea     rax, [rbp+120h+var_188]
0x18017c89f  mov     qword ptr [rsp+220h+var_200], rax
0x18017c8a4  lea     rdx, byte_1803672FF
0x18017c8ab  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18017c8b0  lea     rcx, [rbp+120h+instance]; self
0x18017c8b4  call    MI_Instance_Destruct
0x18017c8b9  mov     eax, cs:dword_18039EB68
0x18017c8bf  cmp     eax, 5
0x18017c8c2  jbe     short loc_18017C8F6
0x18017c8c4  mov     dword ptr [rsp+220h+var_1B0], 540h
0x18017c8cc  lea     rax, aSpacesStoraget_9; "SPACES_StorageTier_Invoke_RemoveStorage"...
0x18017c8d3  mov     [rbp+120h+var_190], rax
0x18017c8d7  lea     rax, [rsp+220h+var_1B0]
0x18017c8dc  mov     [rsp+220h+var_1F8], rax
0x18017c8e1  lea     rax, [rbp+120h+var_190]
0x18017c8e5  mov     qword ptr [rsp+220h+var_200], rax
0x18017c8ea  lea     rdx, byte_1803684C5
0x18017c8f1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18017c8f6  mov     edx, ebx; result
0x18017c8f8  mov     rcx, rsi; context
0x18017c8fb  call    MI_Context_PostResult_0
0x18017c900  lea     rcx, [rbp+120h+var_1A0]
0x18017c904  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18017c909  lea     rcx, [rbp+120h+var_158]; this
0x18017c90d  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x18017c912  lea     rdx, [rbp+120h+var_D8]; ActivityId
  ... truncated ...
```
