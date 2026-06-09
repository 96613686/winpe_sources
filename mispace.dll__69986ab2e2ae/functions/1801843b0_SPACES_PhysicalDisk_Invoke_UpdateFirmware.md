# SPACES_PhysicalDisk_Invoke_UpdateFirmware

- ea: `0x1801843b0`
- end: `0x180184957`
- name: `SPACES_PhysicalDisk_Invoke_UpdateFirmware`
- size: `1447`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, installer_update, broker_com_uri`

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
- `0x1800226ac`
- `0x180023e18`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x1801843b0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18018442d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180184498`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180184920`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18018442d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180184498`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180184920`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180184456`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180184456`

## string_xrefs

- `0x1801844aa`: `SPACES_PhysicalDisk_Invoke_UpdateFirmware`
- `0x1801845bf`: `SPACES_PhysicalDisk_Invoke_UpdateFirmware`
- `0x18018461e`: `SPACES_PhysicalDisk_Invoke_UpdateFirmware`
- `0x18018467f`: `SPACES_PhysicalDisk_Invoke_UpdateFirmware`
- `0x1801846f1`: `SPACES_PhysicalDisk_Invoke_UpdateFirmware`
- `0x180184746`: `SPACES_PhysicalDisk_Invoke_UpdateFirmware`
- `0x1801848ce`: `SPACES_PhysicalDisk_Invoke_UpdateFirmware`
- `0x180184834`: `UpdateFirmware`

## pseudocode

```c
ULONG __fastcall SPACES_PhysicalDisk_Invoke_UpdateFirmware(
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
  int v45; // [rsp+98h] [rbp-68h] BYREF
  const char *v46; // [rsp+A0h] [rbp-60h] BYREF
  const char *v47; // [rsp+A8h] [rbp-58h] BYREF
  const MI_Char *v48; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v49; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v50; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v51; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v52[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v53; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v54; // [rsp+100h] [rbp+0h]
  MI_Value value; // [rsp+108h] [rbp+8h] BYREF
  MI_Instance instance; // [rsp+130h] [rbp+30h] BYREF
  struct _MI_ConstUint32Field v57; // [rsp+170h] [rbp+70h] BYREF
  GUID ActivityId; // [rsp+1A0h] [rbp+A0h] BYREF
  GUID v59; // [rsp+1B0h] [rbp+B0h]
  GUID v60; // [rsp+1C0h] [rbp+C0h] BYREF

  v44 = a4;
  v51 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v59 = ActivityId;
  v60 = ActivityId;
  EventActivityIdControl(4u, &v60);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v40 = 1371;
    v39 = "SPACES_PhysicalDisk_Invoke_UpdateFirmware";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_PhysicalDisk_Invoke_UpdateFirmware",
      (unsigned int)&word_180369106,
      v11,
      v12,
      (__int64)&v39,
      (__int64)&v40);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x68u);
  v53 = 0;
  v54 = 0;
  v42 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v42);
  v42 = 0;
  v13 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v52);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v52);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = 0;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v53) = 4;
    *((_QWORD *)&v53 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v42);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v53, &v42, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v40 = v15;
        v45 = 1403;
        v39 = "SPACES_PhysicalDisk_Invoke_UpdateFirmware";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)word_18036A5E2,
          v18,
          v19,
          (__int64)&v39,
          (__int64)&v45,
          (__int64)&v40);
      }
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, a6[4].value) )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_PhysicalDisk_UpdateFirmware_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v48) = v15;
          LODWORD(v49) = 1421;
          v39 = "SPACES_PhysicalDisk_Invoke_UpdateFirmware";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v23,
            (unsigned int)&word_180368CF6,
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
                262154,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_18039EB68 > 2 )
          {
            LODWORD(v50) = v15;
            LODWORD(v43) = 1432;
            v39 = "SPACES_PhysicalDisk_Invoke_UpdateFirmware";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)word_18036A432,
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
            LODWORD(v39) = 1440;
            v43 = "SPACES_PhysicalDisk_Invoke_UpdateFirmware";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v29,
              (unsigned int)&byte_180368D2F,
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
        LODWORD(v47) = 1413;
        v39 = "SPACES_PhysicalDisk_Invoke_UpdateFirmware";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v20,
          (unsigned int)byte_180369D25,
          v21,
          v22,
          (__int64)&v39,
          (__int64)&v47,
          (__int64)&v46);
      }
    }
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v44, v51, a6 + 4, &v57, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v52);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        v44 = 0;
        v51 = 0;
        v50 = 0;
        v49 = (unsigned __int64)(1000LL * (v52[1] - v52[0])) / v52[2];
        LODWORD(v39) = v15;
        v41 = v57.exists != 0 ? v57.value : 0;
        LODWORD(v43) = v13;
        if ( a6[4].exists )
          v34 = a6[4].value;
        else
          v34 = 0;
        v48 = v34;
        v47 = "UpdateFirmware";
        v46 = "PhysicalDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v57.exists != 0 ? v57.value : 0,
          (unsigned int)byte_180369E63,
          v32,
          v33,
          (__int64)&v46,
          (__int64)&v47,
          (__int64)&v48,
          (__int64)&v43,
          (__int64)&v41,
          (__int64)&v39,
          (__int64)&v49,
          (__int64)&v50,
          (__int64)&v51,
          (__int64)&v44);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v39) = 1473;
    v44 = (unsigned __int16 *)"SPACES_PhysicalDisk_Invoke_UpdateFirmware";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v35,
      (unsigned int)&dword_180368B94,
      v36,
      v37,
      (__int64)&v44,
      (__int64)&v39);
  }
  MI_Context_PostResult_0(a2, v15);
  CSmTimer::~CSmTimer((CSmTimer *)v52);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v42);
  return EventActivityIdControl(4u, &v60);
}

```

## disassembly

```asm
0x1801843b0  mov     [rsp-8+arg_10], rbx
0x1801843b5  push    rbp
0x1801843b6  push    rsi
0x1801843b7  push    rdi
0x1801843b8  push    r12
0x1801843ba  push    r13
0x1801843bc  push    r14
0x1801843be  push    r15
0x1801843c0  lea     rbp, [rsp-0E0h]
0x1801843c8  sub     rsp, 1E0h
0x1801843cf  mov     rax, cs:__security_cookie
0x1801843d6  xor     rax, rsp
0x1801843d9  mov     [rbp+110h+var_40], rax
0x1801843e0  mov     [rbp+110h+var_180], r9
0x1801843e4  mov     rsi, rdx
0x1801843e7  mov     rdi, rcx
0x1801843ea  mov     rax, [rbp+110h+arg_20]
0x1801843f1  mov     [rbp+110h+var_148], rax
0x1801843f5  mov     r14, [rbp+110h+arg_28]
0x1801843fc  mov     r13, [rbp+110h+arg_30]
0x180184403  xorps   xmm0, xmm0
0x180184406  xor     eax, eax
0x180184408  movups  xmmword ptr [rbp+110h+value], xmm0
0x18018440c  movups  xmmword ptr [rbp+110h+value+10h], xmm0
0x180184410  mov     qword ptr [rbp+110h+value+20h], rax
0x180184414  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18018441b  movdqu  xmmword ptr [rbp+110h+ActivityId.Data1], xmm0
0x180184423  lea     rdx, [rbp+110h+ActivityId]; ActivityId
0x18018442a  lea     ecx, [rax+1]; ControlCode
0x18018442d  call    cs:__imp_EventActivityIdControl
0x180184434  nop     dword ptr [rax+rax+00h]
0x180184439  lea     r9, [rbp+110h+value]; value
0x18018443d  mov     rcx, rsi; context
0x180184440  call    MI_Context_GetCustomOption_1
0x180184445  xor     ebx, ebx
0x180184447  test    eax, eax
0x180184449  jnz     short loc_180184462
0x18018444b  lea     rdx, [rbp+110h+ActivityId]; pclsid
0x180184452  mov     rcx, qword ptr [rbp+110h+value]; lpsz
0x180184456  call    cs:__imp_CLSIDFromString
0x18018445d  nop     dword ptr [rax+rax+00h]
0x180184462  mov     rcx, qword ptr [rbp+110h+ActivityId.Data1]
0x180184469  mov     [rbp+110h+var_60], rcx
0x180184470  mov     rax, qword ptr [rbp+110h+ActivityId.Data4]
0x180184477  mov     [rbp+110h+var_58], rax
0x18018447e  mov     qword ptr [rbp+110h+var_50.Data1], rcx
0x180184485  mov     qword ptr [rbp+110h+var_50.Data4], rax
0x18018448c  lea     rdx, [rbp+110h+var_50]; ActivityId
0x180184493  mov     ecx, 4; ControlCode
0x180184498  call    cs:__imp_EventActivityIdControl
0x18018449f  nop     dword ptr [rax+rax+00h]
0x1801844a4  mov     eax, cs:dword_18039EB68
0x1801844aa  lea     rcx, aSpacesPhysical_19; "SPACES_PhysicalDisk_Invoke_UpdateFirmwa"...
0x1801844b1  cmp     eax, 5
0x1801844b4  jbe     short loc_1801844E3
0x1801844b6  mov     [rsp+210h+var_198], 55Bh
0x1801844be  mov     [rsp+210h+var_1A0], rcx
0x1801844c3  lea     rax, [rsp+210h+var_198]
0x1801844c8  mov     [rsp+210h+var_1E8], rax
0x1801844cd  lea     rax, [rsp+210h+var_1A0]
0x1801844d2  mov     qword ptr [rsp+210h+var_1F0], rax
0x1801844d7  lea     rdx, word_180369106
0x1801844de  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1801844e3  mov     [rbp+110h+instance.ft], rbx
0x1801844e7  xor     edx, edx; Val
0x1801844e9  lea     r8d, [rdx+68h]; Size
0x1801844ed  lea     rcx, [rbp+110h+instance.classDecl]; void *
0x1801844f1  call    memset_0
0x1801844f6  xorps   xmm0, xmm0
0x1801844f9  xor     eax, eax
0x1801844fb  movups  [rbp+110h+var_120], xmm0
0x1801844ff  mov     [rbp+110h+var_110], rax
0x180184503  mov     [rbp+110h+var_190], rbx
0x180184507  lea     rcx, [rbp+110h+var_190]
0x18018450b  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180184510  mov     [rbp+110h+var_190], rbx
0x180184514  mov     r15d, ebx
0x180184517  lea     rcx, [rbp+110h+var_140]; this
0x18018451b  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180184520  mov     rcx, rsi; context
0x180184523  call    WspIsRemoteRequest
0x180184528  mov     r12d, eax
0x18018452b  test    eax, eax
0x18018452d  jnz     short loc_180184553
0x18018452f  lea     rcx, [rbp+110h+var_140]; this
0x180184533  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180184538  cmp     [r14+48h], bl
0x18018453c  jz      short loc_180184550
0x18018453e  mov     rcx, [r14+40h]; unsigned __int16 *
0x180184542  call    WspIsRemoteInstance
0x180184547  test    al, al
0x180184549  lea     r15d, [r12+1]
0x18018454e  jnz     short loc_180184553
0x180184550  mov     r15d, ebx
0x180184553  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18018455a  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18018455f  mov     ebx, eax
0x180184561  test    eax, eax
0x180184563  jnz     loc_180184786
0x180184569  mov     dword ptr [rbp+110h+var_120], 4
0x180184570  mov     rax, [r14+40h]
0x180184574  mov     qword ptr [rbp+110h+var_120+8], rax
0x180184578  mov     rbx, [rdi]
0x18018457b  lea     rcx, [rbp+110h+var_190]
0x18018457f  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180184584  mov     [rsp+210h+var_1F0], 1; int
0x18018458c  lea     r9, [rbp+110h+var_190]; struct ISpWmiObject **
0x180184590  lea     r8, [rbp+110h+var_120]; struct _SP_OBJECT_ID *
0x180184594  mov     rdx, rsi; context
0x180184597  mov     rcx, rbx; this
0x18018459a  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18018459f  mov     ebx, eax
0x1801845a1  test    eax, eax
0x1801845a3  jz      short loc_1801845EF
0x1801845a5  mov     eax, cs:dword_18039EB68
0x1801845ab  cmp     eax, 2
0x1801845ae  jbe     loc_18018477A
0x1801845b4  mov     [rsp+210h+var_198], ebx
0x1801845b8  mov     [rbp+110h+var_178], 57Bh
0x1801845bf  lea     rax, aSpacesPhysical_19; "SPACES_PhysicalDisk_Invoke_UpdateFirmwa"...
0x1801845c6  mov     [rsp+210h+var_1A0], rax
0x1801845cb  lea     rax, [rsp+210h+var_198]
0x1801845d0  mov     [rsp+210h+var_1E0], rax
0x1801845d5  lea     rax, [rbp+110h+var_178]
0x1801845d9  mov     [rsp+210h+var_1E8], rax
0x1801845de  lea     rax, [rsp+210h+var_1A0]
0x1801845e3  lea     rdx, word_18036A5E2
0x1801845ea  jmp     loc_180184770
0x1801845ef  mov     r8, [r14+40h]
0x1801845f3  mov     rdx, rsi
0x1801845f6  mov     rcx, [rdi]
0x1801845f9  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x1801845fe  test    eax, eax
0x180184600  jnz     short loc_18018464D
0x180184602  lea     ebx, [rax+7]
0x180184605  mov     eax, cs:dword_18039EB68
0x18018460b  cmp     eax, 2
0x18018460e  jbe     loc_18018477A
0x180184614  mov     dword ptr [rbp+110h+var_170], ebx
0x180184617  mov     dword ptr [rbp+110h+var_168], 585h
0x18018461e  lea     rax, aSpacesPhysical_19; "SPACES_PhysicalDisk_Invoke_UpdateFirmwa"...
0x180184625  mov     [rsp+210h+var_1A0], rax
0x18018462a  lea     rax, [rbp+110h+var_170]
0x18018462e  mov     [rsp+210h+var_1E0], rax
0x180184633  lea     rax, [rbp+110h+var_168]
0x180184637  mov     [rsp+210h+var_1E8], rax
0x18018463c  lea     rax, [rsp+210h+var_1A0]
0x180184641  lea     rdx, byte_180369D25
0x180184648  jmp     loc_180184770
0x18018464d  lea     r8, [rbp+110h+instance]; instance
0x180184651  lea     rdx, SPACES_PhysicalDisk_UpdateFirmware_rtti; methodDecl
0x180184658  mov     rcx, rsi; context
0x18018465b  call    MI_Context_ConstructParameters
0x180184660  mov     ebx, eax
0x180184662  test    eax, eax
0x180184664  jz      short loc_1801846AE
0x180184666  mov     eax, cs:dword_18039EB68
0x18018466c  cmp     eax, 2
0x18018466f  jbe     loc_18018477A
0x180184675  mov     dword ptr [rbp+110h+var_160], ebx
0x180184678  mov     dword ptr [rbp+110h+var_158], 58Dh
0x18018467f  lea     rax, aSpacesPhysical_19; "SPACES_PhysicalDisk_Invoke_UpdateFirmwa"...
0x180184686  mov     [rsp+210h+var_1A0], rax
0x18018468b  lea     rax, [rbp+110h+var_160]
0x18018468f  mov     [rsp+210h+var_1E0], rax
0x180184694  lea     rax, [rbp+110h+var_158]
0x180184698  mov     [rsp+210h+var_1E8], rax
0x18018469d  lea     rax, [rsp+210h+var_1A0]
0x1801846a2  lea     rdx, word_180368CF6
0x1801846a9  jmp     loc_180184770
0x1801846ae  mov     rcx, [rbp+110h+var_190]
0x1801846b2  mov     rax, [rcx]
0x1801846b5  lea     rdx, [rbp+110h+instance]
0x1801846b9  mov     qword ptr [rsp+210h+var_1F0], rdx
0x1801846be  mov     r9, r13
0x1801846c1  mov     r8, rsi
0x1801846c4  mov     edx, 4000Ah
0x1801846c9  mov     rax, [rax+30h]
0x1801846cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801846d2  mov     ebx, eax
0x1801846d4  test    eax, eax
0x1801846d6  jz      short loc_18018471D
0x1801846d8  mov     eax, cs:dword_18039EB68
0x1801846de  cmp     eax, 2
0x1801846e1  jbe     loc_18018477A
0x1801846e7  mov     dword ptr [rbp+110h+var_150], ebx
0x1801846ea  mov     dword ptr [rbp+110h+var_188], 598h
0x1801846f1  lea     rax, aSpacesPhysical_19; "SPACES_PhysicalDisk_Invoke_UpdateFirmwa"...
0x1801846f8  mov     [rsp+210h+var_1A0], rax
0x1801846fd  lea     rax, [rbp+110h+var_150]
0x180184701  mov     [rsp+210h+var_1E0], rax
0x180184706  lea     rax, [rbp+110h+var_188]
0x18018470a  mov     [rsp+210h+var_1E8], rax
0x18018470f  lea     rax, [rsp+210h+var_1A0]
0x180184714  lea     rdx, word_18036A432
0x18018471b  jmp     short loc_180184770
0x18018471d  lea     rdx, [rbp+110h+instance]
0x180184721  mov     rcx, rsi; self
0x180184724  call    MI_Instance_Destruct
0x180184729  mov     ebx, eax
0x18018472b  test    eax, eax
0x18018472d  jz      short loc_18018477A
0x18018472f  mov     eax, cs:dword_18039EB68
0x180184735  cmp     eax, 2
0x180184738  jbe     short loc_18018477A
0x18018473a  mov     [rsp+210h+var_194], ebx
0x18018473e  mov     dword ptr [rsp+210h+var_1A0], 5A0h
0x180184746  lea     rax, aSpacesPhysical_19; "SPACES_PhysicalDisk_Invoke_UpdateFirmwa"...
0x18018474d  mov     [rbp+110h+var_188], rax
0x180184751  lea     rax, [rsp+210h+var_194]
0x180184756  mov     [rsp+210h+var_1E0], rax
0x18018475b  lea     rax, [rsp+210h+var_1A0]
0x180184760  mov     [rsp+210h+var_1E8], rax
0x180184765  lea     rax, [rbp+110h+var_188]
0x180184769  lea     rdx, byte_180368D2F
0x180184770  mov     qword ptr [rsp+210h+var_1F0], rax
0x180184775  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18018477a  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x180184781  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x180184786  xor     r13d, r13d
0x180184789  mov     [rsp+210h+var_1E8], r13; unsigned __int16 *
0x18018478e  mov     [rsp+210h+var_1F0], ebx; enum _MI_Result
0x180184792  lea     r9, [rbp+110h+var_A0]; struct _MI_ConstUint32Field *
0x180184796  lea     r8, [r14+40h]; struct _MI_ConstStringField *
0x18018479a  mov     rdx, [rbp+110h+var_148]; unsigned __int16 *
0x18018479e  mov     rcx, [rbp+110h+var_180]; unsigned __int16 *
0x1801847a2  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x1801847a7  test    r12d, r12d
0x1801847aa  jnz     loc_1801848B2
0x1801847b0  lea     rcx, [rbp+110h+var_140]; this
0x1801847b4  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x1801847b9  mov     eax, cs:dword_18039EB68
0x1801847bf  cmp     eax, 5
0x1801847c2  jbe     loc_1801848B2
0x1801847c8  mov     rdx, 400000000000h
0x1801847d2  lea     rcx, dword_18039EB68
0x1801847d9  call    _tlgKeywordOn
0x1801847de  test    al, al
0x1801847e0  jz      loc_1801848B2
0x1801847e6  mov     [rbp+110h+var_180], r13
0x1801847ea  mov     [rbp+110h+var_148], r13
0x1801847ee  mov     [rbp+110h+var_150], r13
0x1801847f2  mov     rax, [rbp+110h+var_138]
0x1801847f6  sub     rax, [rbp+110h+var_140]
0x1801847fa  imul    rax, 3E8h
0x180184801  xor     edx, edx
0x180184803  div     [rbp+110h+var_130]
0x180184807  mov     [rbp+110h+var_158], rax
0x18018480b  mov     dword ptr [rsp+210h+var_1A0], ebx
0x18018480f  mov     al, [rbp+110h+var_A0.exists]
0x180184812  neg     al
0x180184814  sbb     ecx, ecx
0x180184816  and     ecx, [rbp+110h+var_A0.value]
0x180184819  mov     [rsp+210h+var_194], ecx
0x18018481d  mov     dword ptr [rbp+110h+var_188], r15d
0x180184821  cmp     [r14+48h], r13b
0x180184825  jz      short loc_18018482D
0x180184827  mov     rax, [r14+40h]
0x18018482b  jmp     short loc_180184830
0x18018482d  mov     rax, r13
0x180184830  mov     [rbp+110h+var_160], rax
0x180184834  lea     rax, aUpdatefirmware_0; "UpdateFirmware"
0x18018483b  mov     [rbp+110h+var_168], rax
0x18018483f  lea     rax, aPhysicaldisk_0; "PhysicalDisk"
0x180184846  mov     [rbp+110h+var_170], rax
0x18018484a  lea     rax, [rbp+110h+var_180]
0x18018484e  mov     [rsp+210h+var_1A8], rax
0x180184853  lea     rax, [rbp+110h+var_148]
0x180184857  mov     [rsp+210h+var_1B0], rax
0x18018485c  lea     rax, [rbp+110h+var_150]
0x180184860  mov     [rsp+210h+var_1B8], rax
0x180184865  lea     rax, [rbp+110h+var_158]
0x180184869  mov     [rsp+210h+var_1C0], rax
0x18018486e  lea     rax, [rsp+210h+var_1A0]
0x180184873  mov     [rsp+210h+var_1C8], rax
0x180184878  lea     rax, [rsp+210h+var_194]
0x18018487d  mov     [rsp+210h+var_1D0], rax
0x180184882  lea     rax, [rbp+110h+var_188]
0x180184886  mov     [rsp+210h+var_1D8], rax
0x18018488b  lea     rax, [rbp+110h+var_160]
0x18018488f  mov     [rsp+210h+var_1E0], rax
0x180184894  lea     rax, [rbp+110h+var_168]
0x180184898  mov     [rsp+210h+var_1E8], rax
0x18018489d  lea     rax, [rbp+110h+var_170]
0x1801848a1  mov     qword ptr [rsp+210h+var_1F0], rax
0x1801848a6  lea     rdx, byte_180369E63
0x1801848ad  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1801848b2  lea     rcx, [rbp+110h+instance]; self
0x1801848b6  call    MI_Instance_Destruct
0x1801848bb  mov     eax, cs:dword_18039EB68
0x1801848c1  cmp     eax, 5
0x1801848c4  jbe     short loc_1801848F8
0x1801848c6  mov     dword ptr [rsp+210h+var_1A0], 5C1h
0x1801848ce  lea     rax, aSpacesPhysical_19; "SPACES_PhysicalDisk_Invoke_UpdateFirmwa"...
0x1801848d5  mov     [rbp+110h+var_180], rax
0x1801848d9  lea     rax, [rsp+210h+var_1A0]
0x1801848de  mov     [rsp+210h+var_1E8], rax
0x1801848e3  lea     rax, [rbp+110h+var_180]
0x1801848e7  mov     qword ptr [rsp+210h+var_1F0], rax
0x1801848ec  lea     rdx, dword_180368B94
  ... truncated ...
```
