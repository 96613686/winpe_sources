# SPACES_StorageSubsystem_Invoke_CreateFileServer

- ea: `0x18016fc10`
- end: `0x180170230`
- name: `SPACES_StorageSubsystem_Invoke_CreateFileServer`
- size: `1568`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, broker_com_uri`

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
- `0x180025e78`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x18016fc10`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016fc8d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016fcf8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801701f9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016fc8d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016fcf8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801701f9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18016fcb6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18016fcb6`

## string_xrefs

- `0x180170111`: `CreateFileServer`
- `0x18016fd0a`: `SPACES_StorageSubsystem_Invoke_CreateFileServer`
- `0x18016fe45`: `SPACES_StorageSubsystem_Invoke_CreateFileServer`
- `0x18016ff7a`: `SPACES_StorageSubsystem_Invoke_CreateFileServer`
- `0x18016ffa9`: `SPACES_StorageSubsystem_Invoke_CreateFileServer`
- `0x18016ffbe`: `SPACES_StorageSubsystem_Invoke_CreateFileServer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall SPACES_StorageSubsystem_Invoke_CreateFileServer(
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
  int v13; // r14d
  int IsRemoteRequest; // r12d
  enum _MI_Result v15; // ebx
  CSpProvider *v16; // rbx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  const char **v20; // rax
  int *v21; // rdx
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  int v25; // r8d
  int v26; // r9d
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rax
  const MI_Char *v29; // rax
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  const char **v34; // [rsp+30h] [rbp-D0h]
  const char *v35; // [rsp+70h] [rbp-90h] BYREF
  int v36; // [rsp+78h] [rbp-88h] BYREF
  MI_Uint32 v37; // [rsp+7Ch] [rbp-84h] BYREF
  struct ISpWmiObject *v38; // [rsp+80h] [rbp-80h] BYREF
  const char *v39; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v40; // [rsp+90h] [rbp-70h] BYREF
  int v41; // [rsp+98h] [rbp-68h] BYREF
  const char *v42; // [rsp+A0h] [rbp-60h] BYREF
  const char *v43; // [rsp+A8h] [rbp-58h] BYREF
  const MI_Char *v44; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v45; // [rsp+B8h] [rbp-48h] BYREF
  const char *v46; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v47; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v48[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v49; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v50; // [rsp+100h] [rbp+0h]
  struct _MI_Instance v51; // [rsp+110h] [rbp+10h] BYREF
  MI_Value value; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance instance; // [rsp+180h] [rbp+80h] BYREF
  struct _MI_ConstUint32Field v54; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _MI_Instance *v55; // [rsp+208h] [rbp+108h]
  char v56; // [rsp+210h] [rbp+110h]
  struct _MI_Instance *v57; // [rsp+218h] [rbp+118h]
  char v58; // [rsp+220h] [rbp+120h]
  GUID ActivityId; // [rsp+240h] [rbp+140h] BYREF
  GUID v60; // [rsp+250h] [rbp+150h]
  GUID v61; // [rsp+260h] [rbp+160h] BYREF

  v40 = a4;
  v47 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v60 = ActivityId;
  v61 = ActivityId;
  EventActivityIdControl(4u, &v61);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v36 = 1139;
    v35 = "SPACES_StorageSubsystem_Invoke_CreateFileServer";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StorageSubsystem_Invoke_CreateFileServer",
      (unsigned int)&byte_18036357F,
      v11,
      v12,
      (__int64)&v35,
      (__int64)&v36);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0xB0u);
  v49 = 0;
  v50 = 0;
  v38 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
  v38 = 0;
  v13 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v48);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v48);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = 0;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v49) = 13;
    *((_QWORD *)&v49 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v49, &v38, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v36 = v15;
        v41 = 1170;
        v34 = (const char **)&v36;
        v20 = (const char **)&v41;
        v21 = &dword_180363E74;
LABEL_13:
        v35 = "SPACES_StorageSubsystem_Invoke_CreateFileServer";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (_DWORD)v21,
          v18,
          v19,
          (__int64)&v35,
          (__int64)v20,
          (__int64)v34);
      }
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, a6[4].value) )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StorageSubsystem_CreateFileServer_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v44) = v15;
          LODWORD(v45) = 1188;
          v34 = (const char **)&v44;
          v20 = (const char **)&v45;
          v21 = (int *)&unk_180364AB8;
          goto LABEL_13;
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v38 + 48LL))(
                v38,
                851976,
                a2,
                a7,
                &instance);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v37 = v15;
            LODWORD(v35) = 1205;
            v39 = "SPACES_StorageSubsystem_Invoke_CreateFileServer";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v22,
              (unsigned int)&unk_1803646E8,
              v23,
              v24,
              (__int64)&v39,
              (__int64)&v35,
              (__int64)&v37);
          }
          goto LABEL_27;
        }
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v46) = v15;
          LODWORD(v39) = 1198;
          v34 = &v46;
          v20 = &v39;
          v21 = (int *)&unk_180364928;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v15 = MI_RESULT_NOT_SUPPORTED;
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v42) = 7;
        LODWORD(v43) = 1181;
        v34 = &v42;
        v20 = &v43;
        v21 = (int *)byte_180364793;
        goto LABEL_13;
      }
    }
LABEL_27:
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v40, v47, a6 + 4, &v54, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v48);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        if ( v58 )
        {
          v51 = *v57;
          v27 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v51, 0);
        }
        else
        {
          v27 = 0;
        }
        v40 = v27;
        if ( v56 )
        {
          v51 = *v55;
          v28 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v51, 0);
        }
        else
        {
          v28 = 0;
        }
        v47 = v28;
        v46 = "FileServer";
        v45 = (unsigned __int64)(1000LL * (v48[1] - v48[0])) / v48[2];
        LODWORD(v35) = v15;
        v37 = v54.exists != 0 ? v54.value : 0;
        LODWORD(v39) = v13;
        if ( a6[4].exists )
          v29 = a6[4].value;
        else
          v29 = 0;
        v44 = v29;
        v43 = "CreateFileServer";
        v42 = "StorageSubsystem";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v54.exists != 0 ? v54.value : 0,
          (unsigned int)byte_1803640B9,
          v25,
          v26,
          (__int64)&v42,
          (__int64)&v43,
          (__int64)&v44,
          (__int64)&v39,
          (__int64)&v37,
          (__int64)&v35,
          (__int64)&v45,
          (__int64)&v46,
          (__int64)&v47,
          (__int64)&v40);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v35) = 1238;
    v40 = (unsigned __int16 *)"SPACES_StorageSubsystem_Invoke_CreateFileServer";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v30,
      (unsigned int)&word_180363EE6,
      v31,
      v32,
      (__int64)&v40,
      (__int64)&v35);
  }
  MI_Context_PostResult_0(a2, v15);
  CSmTimer::~CSmTimer((CSmTimer *)v48);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
  return EventActivityIdControl(4u, &v61);
}

```

## disassembly

```asm
0x18016fc10  mov     [rsp-8+arg_10], rbx
0x18016fc15  push    rbp
0x18016fc16  push    rsi
0x18016fc17  push    rdi
0x18016fc18  push    r12
0x18016fc1a  push    r13
0x18016fc1c  push    r14
0x18016fc1e  push    r15
0x18016fc20  lea     rbp, [rsp-180h]
0x18016fc28  sub     rsp, 280h
0x18016fc2f  mov     rax, cs:__security_cookie
0x18016fc36  xor     rax, rsp
0x18016fc39  mov     [rbp+1B0h+var_40], rax
0x18016fc40  mov     [rbp+1B0h+var_220], r9
0x18016fc44  mov     rsi, rdx
0x18016fc47  mov     r15, rcx
0x18016fc4a  mov     rax, [rbp+1B0h+arg_20]
0x18016fc51  mov     [rbp+1B0h+var_1E8], rax
0x18016fc55  mov     rdi, [rbp+1B0h+arg_28]
0x18016fc5c  mov     r13, [rbp+1B0h+arg_30]
0x18016fc63  xorps   xmm0, xmm0
0x18016fc66  xor     eax, eax
0x18016fc68  movups  xmmword ptr [rbp+1B0h+value], xmm0
0x18016fc6c  movups  xmmword ptr [rbp+1B0h+value+10h], xmm0
0x18016fc70  mov     qword ptr [rbp+1B0h+value+20h], rax
0x18016fc74  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18016fc7b  movdqu  xmmword ptr [rbp+1B0h+ActivityId.Data1], xmm0
0x18016fc83  lea     rdx, [rbp+1B0h+ActivityId]; ActivityId
0x18016fc8a  lea     ecx, [rax+1]; ControlCode
0x18016fc8d  call    cs:__imp_EventActivityIdControl
0x18016fc94  nop     dword ptr [rax+rax+00h]
0x18016fc99  lea     r9, [rbp+1B0h+value]; value
0x18016fc9d  mov     rcx, rsi; context
0x18016fca0  call    MI_Context_GetCustomOption_1
0x18016fca5  xor     ebx, ebx
0x18016fca7  test    eax, eax
0x18016fca9  jnz     short loc_18016FCC2
0x18016fcab  lea     rdx, [rbp+1B0h+ActivityId]; pclsid
0x18016fcb2  mov     rcx, qword ptr [rbp+1B0h+value]; lpsz
0x18016fcb6  call    cs:__imp_CLSIDFromString
0x18016fcbd  nop     dword ptr [rax+rax+00h]
0x18016fcc2  mov     rcx, qword ptr [rbp+1B0h+ActivityId.Data1]
0x18016fcc9  mov     [rbp+1B0h+var_60], rcx
0x18016fcd0  mov     rax, qword ptr [rbp+1B0h+ActivityId.Data4]
0x18016fcd7  mov     [rbp+1B0h+var_58], rax
0x18016fcde  mov     qword ptr [rbp+1B0h+var_50.Data1], rcx
0x18016fce5  mov     qword ptr [rbp+1B0h+var_50.Data4], rax
0x18016fcec  lea     rdx, [rbp+1B0h+var_50]; ActivityId
0x18016fcf3  mov     ecx, 4; ControlCode
0x18016fcf8  call    cs:__imp_EventActivityIdControl
0x18016fcff  nop     dword ptr [rax+rax+00h]
0x18016fd04  mov     eax, cs:dword_18039EB68
0x18016fd0a  lea     rcx, aSpacesStorages_30; "SPACES_StorageSubsystem_Invoke_CreateFi"...
0x18016fd11  cmp     eax, 5
0x18016fd14  jbe     short loc_18016FD43
0x18016fd16  mov     [rsp+2B0h+var_238], 473h
0x18016fd1e  mov     [rsp+2B0h+var_240], rcx
0x18016fd23  lea     rax, [rsp+2B0h+var_238]
0x18016fd28  mov     [rsp+2B0h+var_288], rax
0x18016fd2d  lea     rax, [rsp+2B0h+var_240]
0x18016fd32  mov     qword ptr [rsp+2B0h+var_290], rax
0x18016fd37  lea     rdx, byte_18036357F
0x18016fd3e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18016fd43  mov     [rbp+1B0h+instance.ft], rbx
0x18016fd4a  xor     edx, edx; Val
0x18016fd4c  mov     r8d, 0B0h; Size
0x18016fd52  lea     rcx, [rbp+1B0h+instance.classDecl]; void *
0x18016fd59  call    memset_0
0x18016fd5e  xorps   xmm0, xmm0
0x18016fd61  xor     eax, eax
0x18016fd63  movups  [rbp+1B0h+var_1C0], xmm0
0x18016fd67  mov     [rbp+1B0h+var_1B0], rax
0x18016fd6b  mov     [rbp+1B0h+var_230], rbx
0x18016fd6f  lea     rcx, [rbp+1B0h+var_230]
0x18016fd73  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18016fd78  mov     [rbp+1B0h+var_230], rbx
0x18016fd7c  mov     r14d, ebx
0x18016fd7f  lea     rcx, [rbp+1B0h+var_1E0]; this
0x18016fd83  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18016fd88  mov     rcx, rsi; context
0x18016fd8b  call    WspIsRemoteRequest
0x18016fd90  mov     r12d, eax
0x18016fd93  test    eax, eax
0x18016fd95  jnz     short loc_18016FDBA
0x18016fd97  lea     rcx, [rbp+1B0h+var_1E0]; this
0x18016fd9b  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18016fda0  cmp     [rdi+48h], bl
0x18016fda3  jz      short loc_18016FDB7
0x18016fda5  mov     rcx, [rdi+40h]; unsigned __int16 *
0x18016fda9  call    WspIsRemoteInstance
0x18016fdae  test    al, al
0x18016fdb0  lea     r14d, [r12+1]
0x18016fdb5  jnz     short loc_18016FDBA
0x18016fdb7  mov     r14d, ebx
0x18016fdba  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18016fdc1  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18016fdc6  mov     ebx, eax
0x18016fdc8  test    eax, eax
0x18016fdca  jnz     loc_18016FFBE
0x18016fdd0  mov     dword ptr [rbp+1B0h+var_1C0], 0Dh
0x18016fdd7  mov     rax, [rdi+40h]
0x18016fddb  mov     qword ptr [rbp+1B0h+var_1C0+8], rax
0x18016fddf  mov     rbx, [r15]
0x18016fde2  lea     rcx, [rbp+1B0h+var_230]
0x18016fde6  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18016fdeb  mov     [rsp+2B0h+var_290], 1; int
0x18016fdf3  lea     r9, [rbp+1B0h+var_230]; struct ISpWmiObject **
0x18016fdf7  lea     r8, [rbp+1B0h+var_1C0]; struct _SP_OBJECT_ID *
0x18016fdfb  mov     rdx, rsi; context
0x18016fdfe  mov     rcx, rbx; this
0x18016fe01  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18016fe06  mov     ebx, eax
0x18016fe08  test    eax, eax
0x18016fe0a  jz      short loc_18016FE60
0x18016fe0c  mov     eax, cs:dword_18039EB68
0x18016fe12  cmp     eax, 2
0x18016fe15  jbe     loc_18016FFA9
0x18016fe1b  mov     [rsp+2B0h+var_238], ebx
0x18016fe1f  mov     [rbp+1B0h+var_218], 492h
0x18016fe26  lea     rax, [rsp+2B0h+var_238]
0x18016fe2b  mov     [rsp+2B0h+var_280], rax
0x18016fe30  lea     rax, [rbp+1B0h+var_218]
0x18016fe34  lea     rdx, dword_180363E74
0x18016fe3b  mov     [rsp+2B0h+var_288], rax
0x18016fe40  lea     rax, [rsp+2B0h+var_240]
0x18016fe45  lea     r13, aSpacesStorages_30; "SPACES_StorageSubsystem_Invoke_CreateFi"...
0x18016fe4c  mov     [rsp+2B0h+var_240], r13
0x18016fe51  mov     qword ptr [rsp+2B0h+var_290], rax
0x18016fe56  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18016fe5b  jmp     loc_18016FFB0
0x18016fe60  mov     r8, [rdi+40h]
0x18016fe64  mov     rdx, rsi
0x18016fe67  mov     rcx, [r15]
0x18016fe6a  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x18016fe6f  test    eax, eax
0x18016fe71  jnz     short loc_18016FEA5
0x18016fe73  lea     ebx, [rax+7]
0x18016fe76  mov     eax, cs:dword_18039EB68
0x18016fe7c  cmp     eax, 2
0x18016fe7f  jbe     loc_18016FFA9
0x18016fe85  mov     dword ptr [rbp+1B0h+var_210], ebx
0x18016fe88  mov     dword ptr [rbp+1B0h+var_208], 49Dh
0x18016fe8f  lea     rax, [rbp+1B0h+var_210]
0x18016fe93  mov     [rsp+2B0h+var_280], rax
0x18016fe98  lea     rax, [rbp+1B0h+var_208]
0x18016fe9c  lea     rdx, byte_180364793
0x18016fea3  jmp     short loc_18016FE3B
0x18016fea5  lea     r8, [rbp+1B0h+instance]; instance
0x18016feac  lea     rdx, SPACES_StorageSubsystem_CreateFileServer_rtti; methodDecl
0x18016feb3  mov     rcx, rsi; context
0x18016feb6  call    MI_Context_ConstructParameters
0x18016febb  mov     ebx, eax
0x18016febd  test    eax, eax
0x18016febf  jz      short loc_18016FEF3
0x18016fec1  mov     eax, cs:dword_18039EB68
0x18016fec7  cmp     eax, 2
0x18016feca  jbe     loc_18016FFA9
0x18016fed0  mov     dword ptr [rbp+1B0h+var_200], ebx
0x18016fed3  mov     dword ptr [rbp+1B0h+var_1F8], 4A4h
0x18016feda  lea     rax, [rbp+1B0h+var_200]
0x18016fede  mov     [rsp+2B0h+var_280], rax
0x18016fee3  lea     rax, [rbp+1B0h+var_1F8]
0x18016fee7  lea     rdx, unk_180364AB8
0x18016feee  jmp     loc_18016FE3B
0x18016fef3  mov     rcx, [rbp+1B0h+var_230]
0x18016fef7  mov     rax, [rcx]
0x18016fefa  lea     rdx, [rbp+1B0h+instance]
0x18016ff01  mov     qword ptr [rsp+2B0h+var_290], rdx
0x18016ff06  mov     r9, r13
0x18016ff09  mov     r8, rsi
0x18016ff0c  mov     edx, 0D0008h
0x18016ff11  mov     rax, [rax+30h]
0x18016ff15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016ff1a  mov     ebx, eax
0x18016ff1c  test    eax, eax
0x18016ff1e  jz      short loc_18016FF4E
0x18016ff20  mov     eax, cs:dword_18039EB68
0x18016ff26  cmp     eax, 2
0x18016ff29  jbe     short loc_18016FFA9
0x18016ff2b  mov     dword ptr [rbp+1B0h+var_1F0], ebx
0x18016ff2e  mov     dword ptr [rbp+1B0h+var_228], 4AEh
0x18016ff35  lea     rax, [rbp+1B0h+var_1F0]
0x18016ff39  mov     [rsp+2B0h+var_280], rax
0x18016ff3e  lea     rax, [rbp+1B0h+var_228]
0x18016ff42  lea     rdx, unk_180364928
0x18016ff49  jmp     loc_18016FE3B
0x18016ff4e  lea     rdx, [rbp+1B0h+instance]
0x18016ff55  mov     rcx, rsi; self
0x18016ff58  call    MI_Instance_Destruct
0x18016ff5d  mov     ebx, eax
0x18016ff5f  test    eax, eax
0x18016ff61  jz      short loc_18016FFA9
0x18016ff63  mov     eax, cs:dword_18039EB68
0x18016ff69  cmp     eax, 2
0x18016ff6c  jbe     short loc_18016FFA9
0x18016ff6e  mov     [rsp+2B0h+var_234], ebx
0x18016ff72  mov     dword ptr [rsp+2B0h+var_240], 4B5h
0x18016ff7a  lea     r13, aSpacesStorages_30; "SPACES_StorageSubsystem_Invoke_CreateFi"...
0x18016ff81  mov     [rbp+1B0h+var_228], r13
0x18016ff85  lea     rax, [rsp+2B0h+var_234]
0x18016ff8a  mov     [rsp+2B0h+var_280], rax
0x18016ff8f  lea     rax, [rsp+2B0h+var_240]
0x18016ff94  mov     [rsp+2B0h+var_288], rax
0x18016ff99  lea     rax, [rbp+1B0h+var_228]
0x18016ff9d  lea     rdx, unk_1803646E8
0x18016ffa4  jmp     loc_18016FE51
0x18016ffa9  lea     r13, aSpacesStorages_30; "SPACES_StorageSubsystem_Invoke_CreateFi"...
0x18016ffb0  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18016ffb7  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18016ffbc  jmp     short loc_18016FFC5
0x18016ffbe  lea     r13, aSpacesStorages_30; "SPACES_StorageSubsystem_Invoke_CreateFi"...
0x18016ffc5  lea     r8, [rdi+40h]; struct _MI_ConstStringField *
0x18016ffc9  xor     r15d, r15d
0x18016ffcc  mov     [rsp+2B0h+var_288], r15; unsigned __int16 *
0x18016ffd1  mov     [rsp+2B0h+var_290], ebx; enum _MI_Result
0x18016ffd5  lea     r9, [rbp+1B0h+var_F0]; struct _MI_ConstUint32Field *
0x18016ffdc  mov     rdx, [rbp+1B0h+var_1E8]; unsigned __int16 *
0x18016ffe0  mov     rcx, [rbp+1B0h+var_220]; unsigned __int16 *
0x18016ffe4  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18016ffe9  test    r12d, r12d
0x18016ffec  jnz     loc_18017018F
0x18016fff2  lea     rcx, [rbp+1B0h+var_1E0]; this
0x18016fff6  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18016fffb  mov     eax, cs:dword_18039EB68
0x180170001  cmp     eax, 5
0x180170004  jbe     loc_18017018F
0x18017000a  mov     rdx, 400000000000h
0x180170014  lea     rcx, dword_18039EB68
0x18017001b  call    _tlgKeywordOn
0x180170020  test    al, al
0x180170022  jz      loc_18017018F
0x180170028  cmp     [rbp+1B0h+var_90], r15b
0x18017002f  jz      short loc_18017006C
0x180170031  mov     rax, [rbp+1B0h+var_98]
0x180170038  movups  xmm0, xmmword ptr [rax]
0x18017003b  movaps  xmmword ptr [rbp+1B0h+var_1A0.ft], xmm0
0x18017003f  movups  xmm1, xmmword ptr [rax+10h]
0x180170043  movaps  xmmword ptr [rbp+1B0h+var_1A0.serverName], xmm1
0x180170047  movups  xmm0, xmmword ptr [rax+20h]
0x18017004b  movaps  xmmword ptr [rbp+1B0h+var_1A0.reserved], xmm0
0x18017004f  movups  xmm1, xmmword ptr [rax+30h]
0x180170053  movaps  xmmword ptr [rbp+1B0h+var_1A0.reserved+10h], xmm1
0x180170057  xor     r8d, r8d; unsigned __int16 *
0x18017005a  lea     rdx, [rbp+1B0h+var_1A0]; struct _MI_Instance
0x18017005e  lea     rcx, name; "ObjectId"
0x180170065  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18017006a  jmp     short loc_18017006F
0x18017006c  mov     rax, r15
0x18017006f  mov     [rbp+1B0h+var_220], rax
0x180170073  cmp     [rbp+1B0h+var_A0], r15b
0x18017007a  jz      short loc_1801700B7
0x18017007c  mov     rax, [rbp+1B0h+var_A8]
0x180170083  movups  xmm0, xmmword ptr [rax]
0x180170086  movaps  xmmword ptr [rbp+1B0h+var_1A0.ft], xmm0
0x18017008a  movups  xmm1, xmmword ptr [rax+10h]
0x18017008e  movaps  xmmword ptr [rbp+1B0h+var_1A0.serverName], xmm1
0x180170092  movups  xmm0, xmmword ptr [rax+20h]
0x180170096  movaps  xmmword ptr [rbp+1B0h+var_1A0.reserved], xmm0
0x18017009a  movups  xmm1, xmmword ptr [rax+30h]
0x18017009e  movaps  xmmword ptr [rbp+1B0h+var_1A0.reserved+10h], xmm1
0x1801700a2  xor     r8d, r8d; unsigned __int16 *
0x1801700a5  lea     rdx, [rbp+1B0h+var_1A0]; struct _MI_Instance
0x1801700a9  lea     rcx, name; "ObjectId"
0x1801700b0  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x1801700b5  jmp     short loc_1801700BA
0x1801700b7  mov     rax, r15
0x1801700ba  mov     [rbp+1B0h+var_1E8], rax
0x1801700be  lea     rax, aFileserver; "FileServer"
0x1801700c5  mov     [rbp+1B0h+var_1F0], rax
0x1801700c9  mov     rax, [rbp+1B0h+var_1D8]
0x1801700cd  sub     rax, [rbp+1B0h+var_1E0]
0x1801700d1  imul    rax, 3E8h
0x1801700d8  xor     edx, edx
0x1801700da  div     [rbp+1B0h+var_1D0]
0x1801700de  mov     [rbp+1B0h+var_1F8], rax
0x1801700e2  mov     dword ptr [rsp+2B0h+var_240], ebx
0x1801700e6  mov     al, [rbp+1B0h+var_F0.exists]
0x1801700ec  neg     al
0x1801700ee  sbb     ecx, ecx
0x1801700f0  and     ecx, [rbp+1B0h+var_F0.value]
0x1801700f6  mov     [rsp+2B0h+var_234], ecx
0x1801700fa  mov     dword ptr [rbp+1B0h+var_228], r14d
0x1801700fe  cmp     [rdi+48h], r15b
0x180170102  jz      short loc_18017010A
0x180170104  mov     rax, [rdi+40h]
0x180170108  jmp     short loc_18017010D
0x18017010a  mov     rax, r15
0x18017010d  mov     [rbp+1B0h+var_200], rax
0x180170111  lea     rax, aCreatefileserv_0; "CreateFileServer"
0x180170118  mov     [rbp+1B0h+var_208], rax
0x18017011c  lea     rax, aStoragesubsyst_3; "StorageSubsystem"
0x180170123  mov     [rbp+1B0h+var_210], rax
0x180170127  lea     rax, [rbp+1B0h+var_220]
0x18017012b  mov     [rsp+2B0h+var_248], rax
0x180170130  lea     rax, [rbp+1B0h+var_1E8]
0x180170134  mov     [rsp+2B0h+var_250], rax
0x180170139  lea     rax, [rbp+1B0h+var_1F0]
0x18017013d  mov     [rsp+2B0h+var_258], rax
0x180170142  lea     rax, [rbp+1B0h+var_1F8]
0x180170146  mov     [rsp+2B0h+var_260], rax
  ... truncated ...
```
