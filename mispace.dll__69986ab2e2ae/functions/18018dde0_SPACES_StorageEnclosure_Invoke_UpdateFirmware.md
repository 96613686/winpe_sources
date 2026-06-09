# SPACES_StorageEnclosure_Invoke_UpdateFirmware

- ea: `0x18018dde0`
- end: `0x18018e38a`
- name: `SPACES_StorageEnclosure_Invoke_UpdateFirmware`
- size: `1450`
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
- `0x18018dde0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18018de5d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18018dec8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18018e353`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18018de5d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18018dec8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18018e353`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18018de86`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18018de86`

## string_xrefs

- `0x18018e267`: `UpdateFirmware`
- `0x18018deda`: `SPACES_StorageEnclosure_Invoke_UpdateFirmware`
- `0x18018dfef`: `SPACES_StorageEnclosure_Invoke_UpdateFirmware`
- `0x18018e051`: `SPACES_StorageEnclosure_Invoke_UpdateFirmware`
- `0x18018e0b2`: `SPACES_StorageEnclosure_Invoke_UpdateFirmware`
- `0x18018e124`: `SPACES_StorageEnclosure_Invoke_UpdateFirmware`
- `0x18018e179`: `SPACES_StorageEnclosure_Invoke_UpdateFirmware`
- `0x18018e301`: `SPACES_StorageEnclosure_Invoke_UpdateFirmware`

## pseudocode

```c
ULONG __fastcall SPACES_StorageEnclosure_Invoke_UpdateFirmware(
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
    v40 = 718;
    v39 = "SPACES_StorageEnclosure_Invoke_UpdateFirmware";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StorageEnclosure_Invoke_UpdateFirmware",
      (unsigned int)word_18036D94A,
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
    LODWORD(v53) = 8;
    *((_QWORD *)&v53 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v42);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v53, &v42, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v40 = v15;
        v45 = 750;
        v39 = "SPACES_StorageEnclosure_Invoke_UpdateFirmware";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&word_18036D096,
          v18,
          v19,
          (__int64)&v39,
          (__int64)&v45,
          (__int64)&v40);
      }
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, a6[4].value) >= 3 )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StorageEnclosure_UpdateFirmware_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v48) = v15;
          LODWORD(v49) = 768;
          v39 = "SPACES_StorageEnclosure_Invoke_UpdateFirmware";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v23,
            (unsigned int)&word_18036CB5E,
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
                524294,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_18039EB68 > 2 )
          {
            LODWORD(v50) = v15;
            LODWORD(v43) = 779;
            v39 = "SPACES_StorageEnclosure_Invoke_UpdateFirmware";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)word_18036D612,
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
            LODWORD(v39) = 787;
            v43 = "SPACES_StorageEnclosure_Invoke_UpdateFirmware";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v29,
              (unsigned int)&unk_18036D1E0,
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
        LODWORD(v47) = 760;
        v39 = "SPACES_StorageEnclosure_Invoke_UpdateFirmware";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v20,
          (unsigned int)&unk_18036CED8,
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
        v46 = "StorageEnclosure";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v57.exists != 0 ? v57.value : 0,
          (unsigned int)&word_18036CFDE,
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
    LODWORD(v39) = 820;
    v44 = (unsigned __int16 *)"SPACES_StorageEnclosure_Invoke_UpdateFirmware";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v35,
      (unsigned int)byte_18036CA9D,
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
0x18018dde0  mov     [rsp-8+arg_10], rbx
0x18018dde5  push    rbp
0x18018dde6  push    rsi
0x18018dde7  push    rdi
0x18018dde8  push    r12
0x18018ddea  push    r13
0x18018ddec  push    r14
0x18018ddee  push    r15
0x18018ddf0  lea     rbp, [rsp-0E0h]
0x18018ddf8  sub     rsp, 1E0h
0x18018ddff  mov     rax, cs:__security_cookie
0x18018de06  xor     rax, rsp
0x18018de09  mov     [rbp+110h+var_40], rax
0x18018de10  mov     [rbp+110h+var_180], r9
0x18018de14  mov     rsi, rdx
0x18018de17  mov     rdi, rcx
0x18018de1a  mov     rax, [rbp+110h+arg_20]
0x18018de21  mov     [rbp+110h+var_148], rax
0x18018de25  mov     r14, [rbp+110h+arg_28]
0x18018de2c  mov     r13, [rbp+110h+arg_30]
0x18018de33  xorps   xmm0, xmm0
0x18018de36  xor     eax, eax
0x18018de38  movups  xmmword ptr [rbp+110h+value], xmm0
0x18018de3c  movups  xmmword ptr [rbp+110h+value+10h], xmm0
0x18018de40  mov     qword ptr [rbp+110h+value+20h], rax
0x18018de44  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18018de4b  movdqu  xmmword ptr [rbp+110h+ActivityId.Data1], xmm0
0x18018de53  lea     rdx, [rbp+110h+ActivityId]; ActivityId
0x18018de5a  lea     ecx, [rax+1]; ControlCode
0x18018de5d  call    cs:__imp_EventActivityIdControl
0x18018de64  nop     dword ptr [rax+rax+00h]
0x18018de69  lea     r9, [rbp+110h+value]; value
0x18018de6d  mov     rcx, rsi; context
0x18018de70  call    MI_Context_GetCustomOption_1
0x18018de75  xor     ebx, ebx
0x18018de77  test    eax, eax
0x18018de79  jnz     short loc_18018DE92
0x18018de7b  lea     rdx, [rbp+110h+ActivityId]; pclsid
0x18018de82  mov     rcx, qword ptr [rbp+110h+value]; lpsz
0x18018de86  call    cs:__imp_CLSIDFromString
0x18018de8d  nop     dword ptr [rax+rax+00h]
0x18018de92  mov     rcx, qword ptr [rbp+110h+ActivityId.Data1]
0x18018de99  mov     [rbp+110h+var_60], rcx
0x18018dea0  mov     rax, qword ptr [rbp+110h+ActivityId.Data4]
0x18018dea7  mov     [rbp+110h+var_58], rax
0x18018deae  mov     qword ptr [rbp+110h+var_50.Data1], rcx
0x18018deb5  mov     qword ptr [rbp+110h+var_50.Data4], rax
0x18018debc  lea     rdx, [rbp+110h+var_50]; ActivityId
0x18018dec3  mov     ecx, 4; ControlCode
0x18018dec8  call    cs:__imp_EventActivityIdControl
0x18018decf  nop     dword ptr [rax+rax+00h]
0x18018ded4  mov     eax, cs:dword_18039EB68
0x18018deda  lea     rcx, aSpacesStoragee_10; "SPACES_StorageEnclosure_Invoke_UpdateFi"...
0x18018dee1  cmp     eax, 5
0x18018dee4  jbe     short loc_18018DF13
0x18018dee6  mov     [rsp+210h+var_198], 2CEh
0x18018deee  mov     [rsp+210h+var_1A0], rcx
0x18018def3  lea     rax, [rsp+210h+var_198]
0x18018def8  mov     [rsp+210h+var_1E8], rax
0x18018defd  lea     rax, [rsp+210h+var_1A0]
0x18018df02  mov     qword ptr [rsp+210h+var_1F0], rax
0x18018df07  lea     rdx, word_18036D94A
0x18018df0e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18018df13  mov     [rbp+110h+instance.ft], rbx
0x18018df17  xor     edx, edx; Val
0x18018df19  lea     r8d, [rdx+68h]; Size
0x18018df1d  lea     rcx, [rbp+110h+instance.classDecl]; void *
0x18018df21  call    memset_0
0x18018df26  xorps   xmm0, xmm0
0x18018df29  xor     eax, eax
0x18018df2b  movups  [rbp+110h+var_120], xmm0
0x18018df2f  mov     [rbp+110h+var_110], rax
0x18018df33  mov     [rbp+110h+var_190], rbx
0x18018df37  lea     rcx, [rbp+110h+var_190]
0x18018df3b  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18018df40  mov     [rbp+110h+var_190], rbx
0x18018df44  mov     r15d, ebx
0x18018df47  lea     rcx, [rbp+110h+var_140]; this
0x18018df4b  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18018df50  mov     rcx, rsi; context
0x18018df53  call    WspIsRemoteRequest
0x18018df58  mov     r12d, eax
0x18018df5b  test    eax, eax
0x18018df5d  jnz     short loc_18018DF83
0x18018df5f  lea     rcx, [rbp+110h+var_140]; this
0x18018df63  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18018df68  cmp     [r14+48h], bl
0x18018df6c  jz      short loc_18018DF80
0x18018df6e  mov     rcx, [r14+40h]; unsigned __int16 *
0x18018df72  call    WspIsRemoteInstance
0x18018df77  test    al, al
0x18018df79  lea     r15d, [r12+1]
0x18018df7e  jnz     short loc_18018DF83
0x18018df80  mov     r15d, ebx
0x18018df83  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18018df8a  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18018df8f  mov     ebx, eax
0x18018df91  test    eax, eax
0x18018df93  jnz     loc_18018E1B9
0x18018df99  mov     dword ptr [rbp+110h+var_120], 8
0x18018dfa0  mov     rax, [r14+40h]
0x18018dfa4  mov     qword ptr [rbp+110h+var_120+8], rax
0x18018dfa8  mov     rbx, [rdi]
0x18018dfab  lea     rcx, [rbp+110h+var_190]
0x18018dfaf  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18018dfb4  mov     [rsp+210h+var_1F0], 1; int
0x18018dfbc  lea     r9, [rbp+110h+var_190]; struct ISpWmiObject **
0x18018dfc0  lea     r8, [rbp+110h+var_120]; struct _SP_OBJECT_ID *
0x18018dfc4  mov     rdx, rsi; context
0x18018dfc7  mov     rcx, rbx; this
0x18018dfca  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18018dfcf  mov     ebx, eax
0x18018dfd1  test    eax, eax
0x18018dfd3  jz      short loc_18018E01F
0x18018dfd5  mov     eax, cs:dword_18039EB68
0x18018dfdb  cmp     eax, 2
0x18018dfde  jbe     loc_18018E1AD
0x18018dfe4  mov     [rsp+210h+var_198], ebx
0x18018dfe8  mov     [rbp+110h+var_178], 2EEh
0x18018dfef  lea     rax, aSpacesStoragee_10; "SPACES_StorageEnclosure_Invoke_UpdateFi"...
0x18018dff6  mov     [rsp+210h+var_1A0], rax
0x18018dffb  lea     rax, [rsp+210h+var_198]
0x18018e000  mov     [rsp+210h+var_1E0], rax
0x18018e005  lea     rax, [rbp+110h+var_178]
0x18018e009  mov     [rsp+210h+var_1E8], rax
0x18018e00e  lea     rax, [rsp+210h+var_1A0]
0x18018e013  lea     rdx, word_18036D096
0x18018e01a  jmp     loc_18018E1A3
0x18018e01f  mov     r8, [r14+40h]
0x18018e023  mov     rdx, rsi
0x18018e026  mov     rcx, [rdi]
0x18018e029  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x18018e02e  cmp     eax, 3
0x18018e031  jnb     short loc_18018E080
0x18018e033  mov     ebx, 7
0x18018e038  mov     eax, cs:dword_18039EB68
0x18018e03e  cmp     eax, 2
0x18018e041  jbe     loc_18018E1AD
0x18018e047  mov     dword ptr [rbp+110h+var_170], ebx
0x18018e04a  mov     dword ptr [rbp+110h+var_168], 2F8h
0x18018e051  lea     rax, aSpacesStoragee_10; "SPACES_StorageEnclosure_Invoke_UpdateFi"...
0x18018e058  mov     [rsp+210h+var_1A0], rax
0x18018e05d  lea     rax, [rbp+110h+var_170]
0x18018e061  mov     [rsp+210h+var_1E0], rax
0x18018e066  lea     rax, [rbp+110h+var_168]
0x18018e06a  mov     [rsp+210h+var_1E8], rax
0x18018e06f  lea     rax, [rsp+210h+var_1A0]
0x18018e074  lea     rdx, unk_18036CED8
0x18018e07b  jmp     loc_18018E1A3
0x18018e080  lea     r8, [rbp+110h+instance]; instance
0x18018e084  lea     rdx, SPACES_StorageEnclosure_UpdateFirmware_rtti; methodDecl
0x18018e08b  mov     rcx, rsi; context
0x18018e08e  call    MI_Context_ConstructParameters
0x18018e093  mov     ebx, eax
0x18018e095  test    eax, eax
0x18018e097  jz      short loc_18018E0E1
0x18018e099  mov     eax, cs:dword_18039EB68
0x18018e09f  cmp     eax, 2
0x18018e0a2  jbe     loc_18018E1AD
0x18018e0a8  mov     dword ptr [rbp+110h+var_160], ebx
0x18018e0ab  mov     dword ptr [rbp+110h+var_158], 300h
0x18018e0b2  lea     rax, aSpacesStoragee_10; "SPACES_StorageEnclosure_Invoke_UpdateFi"...
0x18018e0b9  mov     [rsp+210h+var_1A0], rax
0x18018e0be  lea     rax, [rbp+110h+var_160]
0x18018e0c2  mov     [rsp+210h+var_1E0], rax
0x18018e0c7  lea     rax, [rbp+110h+var_158]
0x18018e0cb  mov     [rsp+210h+var_1E8], rax
0x18018e0d0  lea     rax, [rsp+210h+var_1A0]
0x18018e0d5  lea     rdx, word_18036CB5E
0x18018e0dc  jmp     loc_18018E1A3
0x18018e0e1  mov     rcx, [rbp+110h+var_190]
0x18018e0e5  mov     rax, [rcx]
0x18018e0e8  lea     rdx, [rbp+110h+instance]
0x18018e0ec  mov     qword ptr [rsp+210h+var_1F0], rdx
0x18018e0f1  mov     r9, r13
0x18018e0f4  mov     r8, rsi
0x18018e0f7  mov     edx, 80006h
0x18018e0fc  mov     rax, [rax+30h]
0x18018e100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e105  mov     ebx, eax
0x18018e107  test    eax, eax
0x18018e109  jz      short loc_18018E150
0x18018e10b  mov     eax, cs:dword_18039EB68
0x18018e111  cmp     eax, 2
0x18018e114  jbe     loc_18018E1AD
0x18018e11a  mov     dword ptr [rbp+110h+var_150], ebx
0x18018e11d  mov     dword ptr [rbp+110h+var_188], 30Bh
0x18018e124  lea     rax, aSpacesStoragee_10; "SPACES_StorageEnclosure_Invoke_UpdateFi"...
0x18018e12b  mov     [rsp+210h+var_1A0], rax
0x18018e130  lea     rax, [rbp+110h+var_150]
0x18018e134  mov     [rsp+210h+var_1E0], rax
0x18018e139  lea     rax, [rbp+110h+var_188]
0x18018e13d  mov     [rsp+210h+var_1E8], rax
0x18018e142  lea     rax, [rsp+210h+var_1A0]
0x18018e147  lea     rdx, word_18036D612
0x18018e14e  jmp     short loc_18018E1A3
0x18018e150  lea     rdx, [rbp+110h+instance]
0x18018e154  mov     rcx, rsi; self
0x18018e157  call    MI_Instance_Destruct
0x18018e15c  mov     ebx, eax
0x18018e15e  test    eax, eax
0x18018e160  jz      short loc_18018E1AD
0x18018e162  mov     eax, cs:dword_18039EB68
0x18018e168  cmp     eax, 2
0x18018e16b  jbe     short loc_18018E1AD
0x18018e16d  mov     [rsp+210h+var_194], ebx
0x18018e171  mov     dword ptr [rsp+210h+var_1A0], 313h
0x18018e179  lea     rax, aSpacesStoragee_10; "SPACES_StorageEnclosure_Invoke_UpdateFi"...
0x18018e180  mov     [rbp+110h+var_188], rax
0x18018e184  lea     rax, [rsp+210h+var_194]
0x18018e189  mov     [rsp+210h+var_1E0], rax
0x18018e18e  lea     rax, [rsp+210h+var_1A0]
0x18018e193  mov     [rsp+210h+var_1E8], rax
0x18018e198  lea     rax, [rbp+110h+var_188]
0x18018e19c  lea     rdx, unk_18036D1E0
0x18018e1a3  mov     qword ptr [rsp+210h+var_1F0], rax
0x18018e1a8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18018e1ad  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18018e1b4  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18018e1b9  xor     r13d, r13d
0x18018e1bc  mov     [rsp+210h+var_1E8], r13; unsigned __int16 *
0x18018e1c1  mov     [rsp+210h+var_1F0], ebx; enum _MI_Result
0x18018e1c5  lea     r9, [rbp+110h+var_A0]; struct _MI_ConstUint32Field *
0x18018e1c9  lea     r8, [r14+40h]; struct _MI_ConstStringField *
0x18018e1cd  mov     rdx, [rbp+110h+var_148]; unsigned __int16 *
0x18018e1d1  mov     rcx, [rbp+110h+var_180]; unsigned __int16 *
0x18018e1d5  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18018e1da  test    r12d, r12d
0x18018e1dd  jnz     loc_18018E2E5
0x18018e1e3  lea     rcx, [rbp+110h+var_140]; this
0x18018e1e7  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18018e1ec  mov     eax, cs:dword_18039EB68
0x18018e1f2  cmp     eax, 5
0x18018e1f5  jbe     loc_18018E2E5
0x18018e1fb  mov     rdx, 400000000000h
0x18018e205  lea     rcx, dword_18039EB68
0x18018e20c  call    _tlgKeywordOn
0x18018e211  test    al, al
0x18018e213  jz      loc_18018E2E5
0x18018e219  mov     [rbp+110h+var_180], r13
0x18018e21d  mov     [rbp+110h+var_148], r13
0x18018e221  mov     [rbp+110h+var_150], r13
0x18018e225  mov     rax, [rbp+110h+var_138]
0x18018e229  sub     rax, [rbp+110h+var_140]
0x18018e22d  imul    rax, 3E8h
0x18018e234  xor     edx, edx
0x18018e236  div     [rbp+110h+var_130]
0x18018e23a  mov     [rbp+110h+var_158], rax
0x18018e23e  mov     dword ptr [rsp+210h+var_1A0], ebx
0x18018e242  mov     al, [rbp+110h+var_A0.exists]
0x18018e245  neg     al
0x18018e247  sbb     ecx, ecx
0x18018e249  and     ecx, [rbp+110h+var_A0.value]
0x18018e24c  mov     [rsp+210h+var_194], ecx
0x18018e250  mov     dword ptr [rbp+110h+var_188], r15d
0x18018e254  cmp     [r14+48h], r13b
0x18018e258  jz      short loc_18018E260
0x18018e25a  mov     rax, [r14+40h]
0x18018e25e  jmp     short loc_18018E263
0x18018e260  mov     rax, r13
0x18018e263  mov     [rbp+110h+var_160], rax
0x18018e267  lea     rax, aUpdatefirmware_0; "UpdateFirmware"
0x18018e26e  mov     [rbp+110h+var_168], rax
0x18018e272  lea     rax, aStorageenclosu; "StorageEnclosure"
0x18018e279  mov     [rbp+110h+var_170], rax
0x18018e27d  lea     rax, [rbp+110h+var_180]
0x18018e281  mov     [rsp+210h+var_1A8], rax
0x18018e286  lea     rax, [rbp+110h+var_148]
0x18018e28a  mov     [rsp+210h+var_1B0], rax
0x18018e28f  lea     rax, [rbp+110h+var_150]
0x18018e293  mov     [rsp+210h+var_1B8], rax
0x18018e298  lea     rax, [rbp+110h+var_158]
0x18018e29c  mov     [rsp+210h+var_1C0], rax
0x18018e2a1  lea     rax, [rsp+210h+var_1A0]
0x18018e2a6  mov     [rsp+210h+var_1C8], rax
0x18018e2ab  lea     rax, [rsp+210h+var_194]
0x18018e2b0  mov     [rsp+210h+var_1D0], rax
0x18018e2b5  lea     rax, [rbp+110h+var_188]
0x18018e2b9  mov     [rsp+210h+var_1D8], rax
0x18018e2be  lea     rax, [rbp+110h+var_160]
0x18018e2c2  mov     [rsp+210h+var_1E0], rax
0x18018e2c7  lea     rax, [rbp+110h+var_168]
0x18018e2cb  mov     [rsp+210h+var_1E8], rax
0x18018e2d0  lea     rax, [rbp+110h+var_170]
0x18018e2d4  mov     qword ptr [rsp+210h+var_1F0], rax
0x18018e2d9  lea     rdx, word_18036CFDE
0x18018e2e0  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18018e2e5  lea     rcx, [rbp+110h+instance]; self
0x18018e2e9  call    MI_Instance_Destruct
0x18018e2ee  mov     eax, cs:dword_18039EB68
0x18018e2f4  cmp     eax, 5
0x18018e2f7  jbe     short loc_18018E32B
0x18018e2f9  mov     dword ptr [rsp+210h+var_1A0], 334h
0x18018e301  lea     rax, aSpacesStoragee_10; "SPACES_StorageEnclosure_Invoke_UpdateFi"...
0x18018e308  mov     [rbp+110h+var_180], rax
0x18018e30c  lea     rax, [rsp+210h+var_1A0]
0x18018e311  mov     [rsp+210h+var_1E8], rax
0x18018e316  lea     rax, [rbp+110h+var_180]
0x18018e31a  mov     qword ptr [rsp+210h+var_1F0], rax
0x18018e31f  lea     rdx, byte_18036CA9D
  ... truncated ...
```
