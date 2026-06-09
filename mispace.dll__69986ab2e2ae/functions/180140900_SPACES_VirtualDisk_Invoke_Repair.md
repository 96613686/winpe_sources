# SPACES_VirtualDisk_Invoke_Repair

- ea: `0x180140900`
- end: `0x180140e75`
- name: `SPACES_VirtualDisk_Invoke_Repair`
- size: `1397`
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
- `0x180023e18`
- `0x180025e78`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x180140900`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014097d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801409e8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180140e3e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014097d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801409e8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180140e3e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801409a6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801409a6`

## string_xrefs

- `0x1801409fa`: `SPACES_VirtualDisk_Invoke_Repair`
- `0x180140b27`: `SPACES_VirtualDisk_Invoke_Repair`
- `0x180140c10`: `SPACES_VirtualDisk_Invoke_Repair`
- `0x180140c3f`: `SPACES_VirtualDisk_Invoke_Repair`
- `0x180140c57`: `SPACES_VirtualDisk_Invoke_Repair`
- `0x180140d59`: `Repair`

## pseudocode

```c
ULONG __fastcall SPACES_VirtualDisk_Invoke_Repair(
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
  char *v21; // rdx
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  int v25; // r8d
  int v26; // r9d
  unsigned __int16 *v27; // rax
  const MI_Char *v28; // rax
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  const char **v33; // [rsp+30h] [rbp-D0h]
  const char *v34; // [rsp+70h] [rbp-90h] BYREF
  MI_Uint32 v35; // [rsp+78h] [rbp-88h] BYREF
  struct ISpWmiObject *v36; // [rsp+80h] [rbp-80h] BYREF
  const char *v37; // [rsp+88h] [rbp-78h] BYREF
  const char *v38; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v39; // [rsp+98h] [rbp-68h] BYREF
  const char *v40; // [rsp+A0h] [rbp-60h] BYREF
  const MI_Char *v41; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v42; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v43; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v44; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v45[4]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v46; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v47; // [rsp+F8h] [rbp-8h]
  struct _MI_Instance v48; // [rsp+100h] [rbp+0h] BYREF
  MI_Value value; // [rsp+140h] [rbp+40h] BYREF
  MI_Instance instance; // [rsp+170h] [rbp+70h] BYREF
  struct _MI_ConstUint32Field v51; // [rsp+1B0h] [rbp+B0h] BYREF
  struct _MI_Instance *v52; // [rsp+1B8h] [rbp+B8h]
  char v53; // [rsp+1C0h] [rbp+C0h]
  GUID ActivityId; // [rsp+1E0h] [rbp+E0h] BYREF
  GUID v55; // [rsp+1F0h] [rbp+F0h]
  GUID v56; // [rsp+200h] [rbp+100h] BYREF

  v39 = a4;
  v44 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v55 = ActivityId;
  v56 = ActivityId;
  EventActivityIdControl(4u, &v56);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v37) = 362;
    v34 = "SPACES_VirtualDisk_Invoke_Repair";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_VirtualDisk_Invoke_Repair",
      (unsigned int)byte_1803524CD,
      v11,
      v12,
      (__int64)&v34,
      (__int64)&v37);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x60u);
  v46 = 0;
  v47 = 0;
  v36 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v36);
  v36 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v45);
  v13 = 0;
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v45);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = 0;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v46) = 16;
    *((_QWORD *)&v46 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v36);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v46, &v36, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v37) = v15;
        LODWORD(v40) = 393;
        v33 = &v37;
        v20 = &v40;
        v21 = byte_180351D71;
LABEL_13:
        v34 = "SPACES_VirtualDisk_Invoke_Repair";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (_DWORD)v21,
          v18,
          v19,
          (__int64)&v34,
          (__int64)v20,
          (__int64)v33);
      }
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_VirtualDisk_Repair_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v41) = v15;
          LODWORD(v42) = 401;
          v33 = (const char **)&v41;
          v20 = (const char **)&v42;
          v21 = (char *)&unk_180352978;
          goto LABEL_13;
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v36 + 48LL))(
                v36,
                1048579,
                a2,
                a7,
                &instance);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v35 = v15;
            LODWORD(v34) = 420;
            v38 = "SPACES_VirtualDisk_Invoke_Repair";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v22,
              (unsigned int)&unk_180353410,
              v23,
              v24,
              (__int64)&v38,
              (__int64)&v34,
              (__int64)&v35);
          }
          goto LABEL_24;
        }
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v43) = v15;
          LODWORD(v38) = 412;
          v33 = (const char **)&v43;
          v20 = &v38;
          v21 = byte_1803530E1;
          goto LABEL_13;
        }
      }
    }
LABEL_24:
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v39, v44, a6 + 4, &v51, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v45);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        if ( v53 )
        {
          v48 = *v52;
          v27 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v48, 0);
        }
        else
        {
          v27 = 0;
        }
        v39 = v27;
        v44 = 0;
        v43 = 0;
        v42 = (unsigned __int64)(1000LL * (v45[1] - v45[0])) / v45[2];
        LODWORD(v34) = v15;
        v35 = v51.exists != 0 ? v51.value : 0;
        LODWORD(v38) = v13;
        if ( a6[4].exists )
          v28 = a6[4].value;
        else
          v28 = 0;
        v41 = v28;
        v40 = "Repair";
        v37 = "VirtualDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v51.exists != 0 ? v51.value : 0,
          (unsigned int)&word_180352E8E,
          v25,
          v26,
          (__int64)&v37,
          (__int64)&v40,
          (__int64)&v41,
          (__int64)&v38,
          (__int64)&v35,
          (__int64)&v34,
          (__int64)&v42,
          (__int64)&v43,
          (__int64)&v44,
          (__int64)&v39);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v34) = 453;
    v39 = (unsigned __int16 *)"SPACES_VirtualDisk_Invoke_Repair";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v29,
      (unsigned int)byte_180352E61,
      v30,
      v31,
      (__int64)&v39,
      (__int64)&v34);
  }
  MI_Context_PostResult_0(a2, v15);
  CSmTimer::~CSmTimer((CSmTimer *)v45);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v36);
  return EventActivityIdControl(4u, &v56);
}

```

## disassembly

```asm
0x180140900  mov     [rsp-8+arg_10], rbx
0x180140905  push    rbp
0x180140906  push    rsi
0x180140907  push    rdi
0x180140908  push    r12
0x18014090a  push    r13
0x18014090c  push    r14
0x18014090e  push    r15
0x180140910  lea     rbp, [rsp-120h]
0x180140918  sub     rsp, 220h
0x18014091f  mov     rax, cs:__security_cookie
0x180140926  xor     rax, rsp
0x180140929  mov     [rbp+150h+var_40], rax
0x180140930  mov     [rbp+150h+var_1B8], r9
0x180140934  mov     rsi, rdx
0x180140937  mov     r15, rcx
0x18014093a  mov     rax, [rbp+150h+arg_20]
0x180140941  mov     [rbp+150h+var_190], rax
0x180140945  mov     rdi, [rbp+150h+arg_28]
0x18014094c  mov     r13, [rbp+150h+arg_30]
0x180140953  xorps   xmm0, xmm0
0x180140956  xor     eax, eax
0x180140958  movups  xmmword ptr [rbp+150h+value], xmm0
0x18014095c  movups  xmmword ptr [rbp+150h+value+10h], xmm0
0x180140960  mov     qword ptr [rbp+150h+value+20h], rax
0x180140964  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18014096b  movdqu  xmmword ptr [rbp+150h+ActivityId.Data1], xmm0
0x180140973  lea     rdx, [rbp+150h+ActivityId]; ActivityId
0x18014097a  lea     ecx, [rax+1]; ControlCode
0x18014097d  call    cs:__imp_EventActivityIdControl
0x180140984  nop     dword ptr [rax+rax+00h]
0x180140989  lea     r9, [rbp+150h+value]; value
0x18014098d  mov     rcx, rsi; context
0x180140990  call    MI_Context_GetCustomOption_1
0x180140995  xor     ebx, ebx
0x180140997  test    eax, eax
0x180140999  jnz     short loc_1801409B2
0x18014099b  lea     rdx, [rbp+150h+ActivityId]; pclsid
0x1801409a2  mov     rcx, qword ptr [rbp+150h+value]; lpsz
0x1801409a6  call    cs:__imp_CLSIDFromString
0x1801409ad  nop     dword ptr [rax+rax+00h]
0x1801409b2  mov     rcx, qword ptr [rbp+150h+ActivityId.Data1]
0x1801409b9  mov     [rbp+150h+var_60], rcx
0x1801409c0  mov     rax, qword ptr [rbp+150h+ActivityId.Data4]
0x1801409c7  mov     [rbp+150h+var_58], rax
0x1801409ce  mov     qword ptr [rbp+150h+var_50.Data1], rcx
0x1801409d5  mov     qword ptr [rbp+150h+var_50.Data4], rax
0x1801409dc  lea     rdx, [rbp+150h+var_50]; ActivityId
0x1801409e3  mov     ecx, 4; ControlCode
0x1801409e8  call    cs:__imp_EventActivityIdControl
0x1801409ef  nop     dword ptr [rax+rax+00h]
0x1801409f4  mov     eax, cs:dword_18039EB68
0x1801409fa  lea     rcx, aSpacesVirtuald_32; "SPACES_VirtualDisk_Invoke_Repair"
0x180140a01  cmp     eax, 5
0x180140a04  jbe     short loc_180140A31
0x180140a06  mov     dword ptr [rbp+150h+var_1C8], 16Ah
0x180140a0d  mov     [rsp+250h+var_1E0], rcx
0x180140a12  lea     rax, [rbp+150h+var_1C8]
0x180140a16  mov     [rsp+250h+var_228], rax
0x180140a1b  lea     rax, [rsp+250h+var_1E0]
0x180140a20  mov     qword ptr [rsp+250h+var_230], rax
0x180140a25  lea     rdx, byte_1803524CD
0x180140a2c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180140a31  mov     [rbp+150h+instance.ft], rbx
0x180140a35  xor     edx, edx; Val
0x180140a37  lea     r8d, [rdx+60h]; Size
0x180140a3b  lea     rcx, [rbp+150h+instance.classDecl]; void *
0x180140a3f  call    memset_0
0x180140a44  xorps   xmm0, xmm0
0x180140a47  xor     eax, eax
0x180140a49  movups  [rbp+150h+var_168], xmm0
0x180140a4d  mov     [rbp+150h+var_158], rax
0x180140a51  mov     [rbp+150h+var_1D0], rbx
0x180140a55  lea     rcx, [rbp+150h+var_1D0]
0x180140a59  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180140a5e  mov     [rbp+150h+var_1D0], rbx
0x180140a62  lea     rcx, [rbp+150h+var_188]; this
0x180140a66  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180140a6b  mov     r14d, ebx
0x180140a6e  mov     rcx, rsi; context
0x180140a71  call    WspIsRemoteRequest
0x180140a76  mov     r12d, eax
0x180140a79  test    eax, eax
0x180140a7b  jnz     short loc_180140AA0
0x180140a7d  lea     rcx, [rbp+150h+var_188]; this
0x180140a81  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180140a86  cmp     [rdi+48h], bl
0x180140a89  jz      short loc_180140A9D
0x180140a8b  mov     rcx, [rdi+40h]; unsigned __int16 *
0x180140a8f  call    WspIsRemoteInstance
0x180140a94  test    al, al
0x180140a96  lea     r14d, [r12+1]
0x180140a9b  jnz     short loc_180140AA0
0x180140a9d  mov     r14d, ebx
0x180140aa0  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x180140aa7  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x180140aac  mov     ebx, eax
0x180140aae  test    eax, eax
0x180140ab0  jnz     loc_180140C54
0x180140ab6  mov     dword ptr [rbp+150h+var_168], 10h
0x180140abd  mov     rax, [rdi+40h]
0x180140ac1  mov     qword ptr [rbp+150h+var_168+8], rax
0x180140ac5  mov     rbx, [r15]
0x180140ac8  lea     rcx, [rbp+150h+var_1D0]
0x180140acc  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180140ad1  mov     [rsp+250h+var_230], 1; int
0x180140ad9  lea     r9, [rbp+150h+var_1D0]; struct ISpWmiObject **
0x180140add  lea     r8, [rbp+150h+var_168]; struct _SP_OBJECT_ID *
0x180140ae1  mov     rdx, rsi; context
0x180140ae4  mov     rcx, rbx; this
0x180140ae7  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x180140aec  mov     ebx, eax
0x180140aee  xor     r15d, r15d
0x180140af1  test    eax, eax
0x180140af3  jz      short loc_180140B47
0x180140af5  mov     eax, cs:dword_18039EB68
0x180140afb  cmp     eax, 2
0x180140afe  jbe     loc_180140C3F
0x180140b04  mov     dword ptr [rbp+150h+var_1C8], ebx
0x180140b07  mov     dword ptr [rbp+150h+var_1B0], 189h
0x180140b0e  lea     rax, [rbp+150h+var_1C8]
0x180140b12  mov     [rsp+250h+var_220], rax
0x180140b17  lea     rax, [rbp+150h+var_1B0]
0x180140b1b  lea     rdx, byte_180351D71
0x180140b22  mov     [rsp+250h+var_228], rax
0x180140b27  lea     r13, aSpacesVirtuald_32; "SPACES_VirtualDisk_Invoke_Repair"
0x180140b2e  lea     rax, [rsp+250h+var_1E0]
0x180140b33  mov     [rsp+250h+var_1E0], r13
0x180140b38  mov     qword ptr [rsp+250h+var_230], rax
0x180140b3d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180140b42  jmp     loc_180140C46
0x180140b47  lea     r8, [rbp+150h+instance]; instance
0x180140b4b  lea     rdx, SPACES_VirtualDisk_Repair_rtti; methodDecl
0x180140b52  mov     rcx, rsi; context
0x180140b55  call    MI_Context_ConstructParameters
0x180140b5a  mov     ebx, eax
0x180140b5c  test    eax, eax
0x180140b5e  jz      short loc_180140B8F
0x180140b60  mov     eax, cs:dword_18039EB68
0x180140b66  cmp     eax, 2
0x180140b69  jbe     loc_180140C3F
0x180140b6f  mov     dword ptr [rbp+150h+var_1A8], ebx
0x180140b72  mov     dword ptr [rbp+150h+var_1A0], 191h
0x180140b79  lea     rax, [rbp+150h+var_1A8]
0x180140b7d  mov     [rsp+250h+var_220], rax
0x180140b82  lea     rax, [rbp+150h+var_1A0]
0x180140b86  lea     rdx, unk_180352978
0x180140b8d  jmp     short loc_180140B22
0x180140b8f  mov     rcx, [rbp+150h+var_1D0]
0x180140b93  mov     rax, [rcx]
0x180140b96  lea     rdx, [rbp+150h+instance]
0x180140b9a  mov     qword ptr [rsp+250h+var_230], rdx
0x180140b9f  mov     r9, r13
0x180140ba2  mov     r8, rsi
0x180140ba5  mov     edx, 100003h
0x180140baa  mov     rax, [rax+30h]
0x180140bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180140bb3  mov     ebx, eax
0x180140bb5  test    eax, eax
0x180140bb7  jz      short loc_180140BE7
0x180140bb9  mov     eax, cs:dword_18039EB68
0x180140bbf  cmp     eax, 2
0x180140bc2  jbe     short loc_180140C3F
0x180140bc4  mov     dword ptr [rbp+150h+var_198], ebx
0x180140bc7  mov     dword ptr [rbp+150h+var_1C0], 19Ch
0x180140bce  lea     rax, [rbp+150h+var_198]
0x180140bd2  mov     [rsp+250h+var_220], rax
0x180140bd7  lea     rax, [rbp+150h+var_1C0]
0x180140bdb  lea     rdx, byte_1803530E1
0x180140be2  jmp     loc_180140B22
0x180140be7  lea     rdx, [rbp+150h+instance]
0x180140beb  mov     rcx, rsi; self
0x180140bee  call    MI_Instance_Destruct
0x180140bf3  mov     ebx, eax
0x180140bf5  test    eax, eax
0x180140bf7  jz      short loc_180140C3F
0x180140bf9  mov     eax, cs:dword_18039EB68
0x180140bff  cmp     eax, 2
0x180140c02  jbe     short loc_180140C3F
0x180140c04  mov     [rsp+250h+var_1D8], ebx
0x180140c08  mov     dword ptr [rsp+250h+var_1E0], 1A4h
0x180140c10  lea     r13, aSpacesVirtuald_32; "SPACES_VirtualDisk_Invoke_Repair"
0x180140c17  mov     [rbp+150h+var_1C0], r13
0x180140c1b  lea     rax, [rsp+250h+var_1D8]
0x180140c20  mov     [rsp+250h+var_220], rax
0x180140c25  lea     rax, [rsp+250h+var_1E0]
0x180140c2a  mov     [rsp+250h+var_228], rax
0x180140c2f  lea     rax, [rbp+150h+var_1C0]
0x180140c33  lea     rdx, unk_180353410
0x180140c3a  jmp     loc_180140B38
0x180140c3f  lea     r13, aSpacesVirtuald_32; "SPACES_VirtualDisk_Invoke_Repair"
0x180140c46  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x180140c4d  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x180140c52  jmp     short loc_180140C5E
0x180140c54  xor     r15d, r15d
0x180140c57  lea     r13, aSpacesVirtuald_32; "SPACES_VirtualDisk_Invoke_Repair"
0x180140c5e  lea     r8, [rdi+40h]; struct _MI_ConstStringField *
0x180140c62  mov     [rsp+250h+var_228], r15; unsigned __int16 *
0x180140c67  mov     [rsp+250h+var_230], ebx; enum _MI_Result
0x180140c6b  lea     r9, [rbp+150h+var_A0]; struct _MI_ConstUint32Field *
0x180140c72  mov     rdx, [rbp+150h+var_190]; unsigned __int16 *
0x180140c76  mov     rcx, [rbp+150h+var_1B8]; unsigned __int16 *
0x180140c7a  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x180140c7f  test    r12d, r12d
0x180140c82  jnz     loc_180140DD7
0x180140c88  lea     rcx, [rbp+150h+var_188]; this
0x180140c8c  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180140c91  mov     eax, cs:dword_18039EB68
0x180140c97  cmp     eax, 5
0x180140c9a  jbe     loc_180140DD7
0x180140ca0  mov     rdx, 400000000000h
0x180140caa  lea     rcx, dword_18039EB68
0x180140cb1  call    _tlgKeywordOn
0x180140cb6  test    al, al
0x180140cb8  jz      loc_180140DD7
0x180140cbe  cmp     [rbp+150h+var_90], r15b
0x180140cc5  jz      short loc_180140D02
0x180140cc7  mov     rax, [rbp+150h+var_98]
0x180140cce  movups  xmm0, xmmword ptr [rax]
0x180140cd1  movaps  xmmword ptr [rbp+150h+var_150.ft], xmm0
0x180140cd5  movups  xmm1, xmmword ptr [rax+10h]
0x180140cd9  movaps  xmmword ptr [rbp+150h+var_150.serverName], xmm1
0x180140cdd  movups  xmm0, xmmword ptr [rax+20h]
0x180140ce1  movaps  xmmword ptr [rbp+150h+var_150.reserved], xmm0
0x180140ce5  movups  xmm1, xmmword ptr [rax+30h]
0x180140ce9  movaps  xmmword ptr [rbp+150h+var_150.reserved+10h], xmm1
0x180140ced  xor     r8d, r8d; unsigned __int16 *
0x180140cf0  lea     rdx, [rbp+150h+var_150]; struct _MI_Instance
0x180140cf4  lea     rcx, name; "ObjectId"
0x180140cfb  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x180140d00  jmp     short loc_180140D05
0x180140d02  mov     rax, r15
0x180140d05  mov     [rbp+150h+var_1B8], rax
0x180140d09  mov     [rbp+150h+var_190], r15
0x180140d0d  mov     [rbp+150h+var_198], r15
0x180140d11  mov     rax, [rbp+150h+var_180]
0x180140d15  sub     rax, [rbp+150h+var_188]
0x180140d19  imul    rax, 3E8h
0x180140d20  xor     edx, edx
0x180140d22  div     [rbp+150h+var_178]
0x180140d26  mov     [rbp+150h+var_1A0], rax
0x180140d2a  mov     dword ptr [rsp+250h+var_1E0], ebx
0x180140d2e  mov     al, [rbp+150h+var_A0.exists]
0x180140d34  neg     al
0x180140d36  sbb     ecx, ecx
0x180140d38  and     ecx, [rbp+150h+var_A0.value]
0x180140d3e  mov     [rsp+250h+var_1D8], ecx
0x180140d42  mov     dword ptr [rbp+150h+var_1C0], r14d
0x180140d46  cmp     [rdi+48h], r15b
0x180140d4a  jz      short loc_180140D52
0x180140d4c  mov     rax, [rdi+40h]
0x180140d50  jmp     short loc_180140D55
0x180140d52  mov     rax, r15
0x180140d55  mov     [rbp+150h+var_1A8], rax
0x180140d59  lea     rax, aRepair_0; "Repair"
0x180140d60  mov     [rbp+150h+var_1B0], rax
0x180140d64  lea     rax, aVirtualdisk_0; "VirtualDisk"
0x180140d6b  mov     [rbp+150h+var_1C8], rax
0x180140d6f  lea     rax, [rbp+150h+var_1B8]
0x180140d73  mov     [rsp+250h+var_1E8], rax
0x180140d78  lea     rax, [rbp+150h+var_190]
0x180140d7c  mov     [rsp+250h+var_1F0], rax
0x180140d81  lea     rax, [rbp+150h+var_198]
0x180140d85  mov     [rsp+250h+var_1F8], rax
0x180140d8a  lea     rax, [rbp+150h+var_1A0]
0x180140d8e  mov     [rsp+250h+var_200], rax
0x180140d93  lea     rax, [rsp+250h+var_1E0]
0x180140d98  mov     [rsp+250h+var_208], rax
0x180140d9d  lea     rax, [rsp+250h+var_1D8]
0x180140da2  mov     [rsp+250h+var_210], rax
0x180140da7  lea     rax, [rbp+150h+var_1C0]
0x180140dab  mov     [rsp+250h+var_218], rax
0x180140db0  lea     rax, [rbp+150h+var_1A8]
0x180140db4  mov     [rsp+250h+var_220], rax
0x180140db9  lea     rax, [rbp+150h+var_1B0]
0x180140dbd  mov     [rsp+250h+var_228], rax
0x180140dc2  lea     rax, [rbp+150h+var_1C8]
0x180140dc6  mov     qword ptr [rsp+250h+var_230], rax
0x180140dcb  lea     rdx, word_180352E8E
0x180140dd2  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180140dd7  lea     rcx, [rbp+150h+instance]; self
0x180140ddb  call    MI_Instance_Destruct
0x180140de0  mov     eax, cs:dword_18039EB68
0x180140de6  cmp     eax, 5
0x180140de9  jbe     short loc_180140E16
0x180140deb  mov     dword ptr [rsp+250h+var_1E0], 1C5h
0x180140df3  mov     [rbp+150h+var_1B8], r13
0x180140df7  lea     rax, [rsp+250h+var_1E0]
0x180140dfc  mov     [rsp+250h+var_228], rax
0x180140e01  lea     rax, [rbp+150h+var_1B8]
0x180140e05  mov     qword ptr [rsp+250h+var_230], rax
0x180140e0a  lea     rdx, byte_180352E61
0x180140e11  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180140e16  mov     edx, ebx; result
0x180140e18  mov     rcx, rsi; context
0x180140e1b  call    MI_Context_PostResult_0
0x180140e20  lea     rcx, [rbp+150h+var_188]; this
0x180140e24  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x180140e29  lea     rcx, [rbp+150h+var_1D0]
0x180140e2d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
  ... truncated ...
```
