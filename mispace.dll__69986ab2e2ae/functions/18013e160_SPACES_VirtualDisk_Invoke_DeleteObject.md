# SPACES_VirtualDisk_Invoke_DeleteObject

- ea: `0x18013e160`
- end: `0x18013e6d5`
- name: `SPACES_VirtualDisk_Invoke_DeleteObject`
- size: `1397`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
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
- `0x180025e78`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x18013e160`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013e1dd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013e248`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013e69e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013e1dd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013e248`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013e69e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013e206`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013e206`

## string_xrefs

- `0x18013e5b9`: `DeleteVirtualDisk`
- `0x18013e25a`: `SPACES_VirtualDisk_Invoke_DeleteObject`
- `0x18013e387`: `SPACES_VirtualDisk_Invoke_DeleteObject`
- `0x18013e470`: `SPACES_VirtualDisk_Invoke_DeleteObject`
- `0x18013e49f`: `SPACES_VirtualDisk_Invoke_DeleteObject`
- `0x18013e4b7`: `SPACES_VirtualDisk_Invoke_DeleteObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall SPACES_VirtualDisk_Invoke_DeleteObject(
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
    LODWORD(v37) = 148;
    v34 = "SPACES_VirtualDisk_Invoke_DeleteObject";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_VirtualDisk_Invoke_DeleteObject",
      (unsigned int)word_180353612,
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
        LODWORD(v40) = 179;
        v33 = &v37;
        v20 = &v40;
        v21 = byte_180352383;
LABEL_13:
        v34 = "SPACES_VirtualDisk_Invoke_DeleteObject";
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
      v15 = MI_Context_ConstructParameters(a2, &SPACES_VirtualDisk_DeleteObject_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v41) = v15;
          LODWORD(v42) = 187;
          v33 = (const char **)&v41;
          v20 = (const char **)&v42;
          v21 = &byte_180351A7F;
          goto LABEL_13;
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v36 + 48LL))(
                v36,
                1048577,
                a2,
                a7,
                &instance);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v35 = v15;
            LODWORD(v34) = 206;
            v38 = "SPACES_VirtualDisk_Invoke_DeleteObject";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v22,
              (unsigned int)&byte_18035293F,
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
          LODWORD(v38) = 198;
          v33 = (const char **)&v43;
          v20 = &v38;
          v21 = (char *)&dword_180353834;
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
        v40 = "DeleteVirtualDisk";
        v37 = "VirtualDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v51.exists != 0 ? v51.value : 0,
          (unsigned int)&dword_180353CC4,
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
    LODWORD(v34) = 239;
    v39 = (unsigned __int16 *)"SPACES_VirtualDisk_Invoke_DeleteObject";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v29,
      (unsigned int)&byte_1803528B7,
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
0x18013e160  mov     [rsp-8+arg_10], rbx
0x18013e165  push    rbp
0x18013e166  push    rsi
0x18013e167  push    rdi
0x18013e168  push    r12
0x18013e16a  push    r13
0x18013e16c  push    r14
0x18013e16e  push    r15
0x18013e170  lea     rbp, [rsp-120h]
0x18013e178  sub     rsp, 220h
0x18013e17f  mov     rax, cs:__security_cookie
0x18013e186  xor     rax, rsp
0x18013e189  mov     [rbp+150h+var_40], rax
0x18013e190  mov     [rbp+150h+var_1B8], r9
0x18013e194  mov     rsi, rdx
0x18013e197  mov     r15, rcx
0x18013e19a  mov     rax, [rbp+150h+arg_20]
0x18013e1a1  mov     [rbp+150h+var_190], rax
0x18013e1a5  mov     rdi, [rbp+150h+arg_28]
0x18013e1ac  mov     r13, [rbp+150h+arg_30]
0x18013e1b3  xorps   xmm0, xmm0
0x18013e1b6  xor     eax, eax
0x18013e1b8  movups  xmmword ptr [rbp+150h+value], xmm0
0x18013e1bc  movups  xmmword ptr [rbp+150h+value+10h], xmm0
0x18013e1c0  mov     qword ptr [rbp+150h+value+20h], rax
0x18013e1c4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18013e1cb  movdqu  xmmword ptr [rbp+150h+ActivityId.Data1], xmm0
0x18013e1d3  lea     rdx, [rbp+150h+ActivityId]; ActivityId
0x18013e1da  lea     ecx, [rax+1]; ControlCode
0x18013e1dd  call    cs:__imp_EventActivityIdControl
0x18013e1e4  nop     dword ptr [rax+rax+00h]
0x18013e1e9  lea     r9, [rbp+150h+value]; value
0x18013e1ed  mov     rcx, rsi; context
0x18013e1f0  call    MI_Context_GetCustomOption_1
0x18013e1f5  xor     ebx, ebx
0x18013e1f7  test    eax, eax
0x18013e1f9  jnz     short loc_18013E212
0x18013e1fb  lea     rdx, [rbp+150h+ActivityId]; pclsid
0x18013e202  mov     rcx, qword ptr [rbp+150h+value]; lpsz
0x18013e206  call    cs:__imp_CLSIDFromString
0x18013e20d  nop     dword ptr [rax+rax+00h]
0x18013e212  mov     rcx, qword ptr [rbp+150h+ActivityId.Data1]
0x18013e219  mov     [rbp+150h+var_60], rcx
0x18013e220  mov     rax, qword ptr [rbp+150h+ActivityId.Data4]
0x18013e227  mov     [rbp+150h+var_58], rax
0x18013e22e  mov     qword ptr [rbp+150h+var_50.Data1], rcx
0x18013e235  mov     qword ptr [rbp+150h+var_50.Data4], rax
0x18013e23c  lea     rdx, [rbp+150h+var_50]; ActivityId
0x18013e243  mov     ecx, 4; ControlCode
0x18013e248  call    cs:__imp_EventActivityIdControl
0x18013e24f  nop     dword ptr [rax+rax+00h]
0x18013e254  mov     eax, cs:dword_18039EB68
0x18013e25a  lea     rcx, aSpacesVirtuald_22; "SPACES_VirtualDisk_Invoke_DeleteObject"
0x18013e261  cmp     eax, 5
0x18013e264  jbe     short loc_18013E291
0x18013e266  mov     dword ptr [rbp+150h+var_1C8], 94h
0x18013e26d  mov     [rsp+250h+var_1E0], rcx
0x18013e272  lea     rax, [rbp+150h+var_1C8]
0x18013e276  mov     [rsp+250h+var_228], rax
0x18013e27b  lea     rax, [rsp+250h+var_1E0]
0x18013e280  mov     qword ptr [rsp+250h+var_230], rax
0x18013e285  lea     rdx, word_180353612
0x18013e28c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18013e291  mov     [rbp+150h+instance.ft], rbx
0x18013e295  xor     edx, edx; Val
0x18013e297  lea     r8d, [rdx+60h]; Size
0x18013e29b  lea     rcx, [rbp+150h+instance.classDecl]; void *
0x18013e29f  call    memset_0
0x18013e2a4  xorps   xmm0, xmm0
0x18013e2a7  xor     eax, eax
0x18013e2a9  movups  [rbp+150h+var_168], xmm0
0x18013e2ad  mov     [rbp+150h+var_158], rax
0x18013e2b1  mov     [rbp+150h+var_1D0], rbx
0x18013e2b5  lea     rcx, [rbp+150h+var_1D0]
0x18013e2b9  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013e2be  mov     [rbp+150h+var_1D0], rbx
0x18013e2c2  lea     rcx, [rbp+150h+var_188]; this
0x18013e2c6  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18013e2cb  mov     r14d, ebx
0x18013e2ce  mov     rcx, rsi; context
0x18013e2d1  call    WspIsRemoteRequest
0x18013e2d6  mov     r12d, eax
0x18013e2d9  test    eax, eax
0x18013e2db  jnz     short loc_18013E300
0x18013e2dd  lea     rcx, [rbp+150h+var_188]; this
0x18013e2e1  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18013e2e6  cmp     [rdi+48h], bl
0x18013e2e9  jz      short loc_18013E2FD
0x18013e2eb  mov     rcx, [rdi+40h]; unsigned __int16 *
0x18013e2ef  call    WspIsRemoteInstance
0x18013e2f4  test    al, al
0x18013e2f6  lea     r14d, [r12+1]
0x18013e2fb  jnz     short loc_18013E300
0x18013e2fd  mov     r14d, ebx
0x18013e300  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18013e307  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18013e30c  mov     ebx, eax
0x18013e30e  test    eax, eax
0x18013e310  jnz     loc_18013E4B4
0x18013e316  mov     dword ptr [rbp+150h+var_168], 10h
0x18013e31d  mov     rax, [rdi+40h]
0x18013e321  mov     qword ptr [rbp+150h+var_168+8], rax
0x18013e325  mov     rbx, [r15]
0x18013e328  lea     rcx, [rbp+150h+var_1D0]
0x18013e32c  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013e331  mov     [rsp+250h+var_230], 1; int
0x18013e339  lea     r9, [rbp+150h+var_1D0]; struct ISpWmiObject **
0x18013e33d  lea     r8, [rbp+150h+var_168]; struct _SP_OBJECT_ID *
0x18013e341  mov     rdx, rsi; context
0x18013e344  mov     rcx, rbx; this
0x18013e347  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18013e34c  mov     ebx, eax
0x18013e34e  xor     r15d, r15d
0x18013e351  test    eax, eax
0x18013e353  jz      short loc_18013E3A7
0x18013e355  mov     eax, cs:dword_18039EB68
0x18013e35b  cmp     eax, 2
0x18013e35e  jbe     loc_18013E49F
0x18013e364  mov     dword ptr [rbp+150h+var_1C8], ebx
0x18013e367  mov     dword ptr [rbp+150h+var_1B0], 0B3h
0x18013e36e  lea     rax, [rbp+150h+var_1C8]
0x18013e372  mov     [rsp+250h+var_220], rax
0x18013e377  lea     rax, [rbp+150h+var_1B0]
0x18013e37b  lea     rdx, byte_180352383
0x18013e382  mov     [rsp+250h+var_228], rax
0x18013e387  lea     r13, aSpacesVirtuald_22; "SPACES_VirtualDisk_Invoke_DeleteObject"
0x18013e38e  lea     rax, [rsp+250h+var_1E0]
0x18013e393  mov     [rsp+250h+var_1E0], r13
0x18013e398  mov     qword ptr [rsp+250h+var_230], rax
0x18013e39d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18013e3a2  jmp     loc_18013E4A6
0x18013e3a7  lea     r8, [rbp+150h+instance]; instance
0x18013e3ab  lea     rdx, SPACES_VirtualDisk_DeleteObject_rtti; methodDecl
0x18013e3b2  mov     rcx, rsi; context
0x18013e3b5  call    MI_Context_ConstructParameters
0x18013e3ba  mov     ebx, eax
0x18013e3bc  test    eax, eax
0x18013e3be  jz      short loc_18013E3EF
0x18013e3c0  mov     eax, cs:dword_18039EB68
0x18013e3c6  cmp     eax, 2
0x18013e3c9  jbe     loc_18013E49F
0x18013e3cf  mov     dword ptr [rbp+150h+var_1A8], ebx
0x18013e3d2  mov     dword ptr [rbp+150h+var_1A0], 0BBh
0x18013e3d9  lea     rax, [rbp+150h+var_1A8]
0x18013e3dd  mov     [rsp+250h+var_220], rax
0x18013e3e2  lea     rax, [rbp+150h+var_1A0]
0x18013e3e6  lea     rdx, byte_180351A7F
0x18013e3ed  jmp     short loc_18013E382
0x18013e3ef  mov     rcx, [rbp+150h+var_1D0]
0x18013e3f3  mov     rax, [rcx]
0x18013e3f6  lea     rdx, [rbp+150h+instance]
0x18013e3fa  mov     qword ptr [rsp+250h+var_230], rdx
0x18013e3ff  mov     r9, r13
0x18013e402  mov     r8, rsi
0x18013e405  mov     edx, 100001h
0x18013e40a  mov     rax, [rax+30h]
0x18013e40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013e413  mov     ebx, eax
0x18013e415  test    eax, eax
0x18013e417  jz      short loc_18013E447
0x18013e419  mov     eax, cs:dword_18039EB68
0x18013e41f  cmp     eax, 2
0x18013e422  jbe     short loc_18013E49F
0x18013e424  mov     dword ptr [rbp+150h+var_198], ebx
0x18013e427  mov     dword ptr [rbp+150h+var_1C0], 0C6h
0x18013e42e  lea     rax, [rbp+150h+var_198]
0x18013e432  mov     [rsp+250h+var_220], rax
0x18013e437  lea     rax, [rbp+150h+var_1C0]
0x18013e43b  lea     rdx, dword_180353834
0x18013e442  jmp     loc_18013E382
0x18013e447  lea     rdx, [rbp+150h+instance]
0x18013e44b  mov     rcx, rsi; self
0x18013e44e  call    MI_Instance_Destruct
0x18013e453  mov     ebx, eax
0x18013e455  test    eax, eax
0x18013e457  jz      short loc_18013E49F
0x18013e459  mov     eax, cs:dword_18039EB68
0x18013e45f  cmp     eax, 2
0x18013e462  jbe     short loc_18013E49F
0x18013e464  mov     [rsp+250h+var_1D8], ebx
0x18013e468  mov     dword ptr [rsp+250h+var_1E0], 0CEh
0x18013e470  lea     r13, aSpacesVirtuald_22; "SPACES_VirtualDisk_Invoke_DeleteObject"
0x18013e477  mov     [rbp+150h+var_1C0], r13
0x18013e47b  lea     rax, [rsp+250h+var_1D8]
0x18013e480  mov     [rsp+250h+var_220], rax
0x18013e485  lea     rax, [rsp+250h+var_1E0]
0x18013e48a  mov     [rsp+250h+var_228], rax
0x18013e48f  lea     rax, [rbp+150h+var_1C0]
0x18013e493  lea     rdx, byte_18035293F
0x18013e49a  jmp     loc_18013E398
0x18013e49f  lea     r13, aSpacesVirtuald_22; "SPACES_VirtualDisk_Invoke_DeleteObject"
0x18013e4a6  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18013e4ad  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18013e4b2  jmp     short loc_18013E4BE
0x18013e4b4  xor     r15d, r15d
0x18013e4b7  lea     r13, aSpacesVirtuald_22; "SPACES_VirtualDisk_Invoke_DeleteObject"
0x18013e4be  lea     r8, [rdi+40h]; struct _MI_ConstStringField *
0x18013e4c2  mov     [rsp+250h+var_228], r15; unsigned __int16 *
0x18013e4c7  mov     [rsp+250h+var_230], ebx; enum _MI_Result
0x18013e4cb  lea     r9, [rbp+150h+var_A0]; struct _MI_ConstUint32Field *
0x18013e4d2  mov     rdx, [rbp+150h+var_190]; unsigned __int16 *
0x18013e4d6  mov     rcx, [rbp+150h+var_1B8]; unsigned __int16 *
0x18013e4da  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18013e4df  test    r12d, r12d
0x18013e4e2  jnz     loc_18013E637
0x18013e4e8  lea     rcx, [rbp+150h+var_188]; this
0x18013e4ec  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18013e4f1  mov     eax, cs:dword_18039EB68
0x18013e4f7  cmp     eax, 5
0x18013e4fa  jbe     loc_18013E637
0x18013e500  mov     rdx, 400000000000h
0x18013e50a  lea     rcx, dword_18039EB68
0x18013e511  call    _tlgKeywordOn
0x18013e516  test    al, al
0x18013e518  jz      loc_18013E637
0x18013e51e  cmp     [rbp+150h+var_90], r15b
0x18013e525  jz      short loc_18013E562
0x18013e527  mov     rax, [rbp+150h+var_98]
0x18013e52e  movups  xmm0, xmmword ptr [rax]
0x18013e531  movaps  xmmword ptr [rbp+150h+var_150.ft], xmm0
0x18013e535  movups  xmm1, xmmword ptr [rax+10h]
0x18013e539  movaps  xmmword ptr [rbp+150h+var_150.serverName], xmm1
0x18013e53d  movups  xmm0, xmmword ptr [rax+20h]
0x18013e541  movaps  xmmword ptr [rbp+150h+var_150.reserved], xmm0
0x18013e545  movups  xmm1, xmmword ptr [rax+30h]
0x18013e549  movaps  xmmword ptr [rbp+150h+var_150.reserved+10h], xmm1
0x18013e54d  xor     r8d, r8d; unsigned __int16 *
0x18013e550  lea     rdx, [rbp+150h+var_150]; struct _MI_Instance
0x18013e554  lea     rcx, name; "ObjectId"
0x18013e55b  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18013e560  jmp     short loc_18013E565
0x18013e562  mov     rax, r15
0x18013e565  mov     [rbp+150h+var_1B8], rax
0x18013e569  mov     [rbp+150h+var_190], r15
0x18013e56d  mov     [rbp+150h+var_198], r15
0x18013e571  mov     rax, [rbp+150h+var_180]
0x18013e575  sub     rax, [rbp+150h+var_188]
0x18013e579  imul    rax, 3E8h
0x18013e580  xor     edx, edx
0x18013e582  div     [rbp+150h+var_178]
0x18013e586  mov     [rbp+150h+var_1A0], rax
0x18013e58a  mov     dword ptr [rsp+250h+var_1E0], ebx
0x18013e58e  mov     al, [rbp+150h+var_A0.exists]
0x18013e594  neg     al
0x18013e596  sbb     ecx, ecx
0x18013e598  and     ecx, [rbp+150h+var_A0.value]
0x18013e59e  mov     [rsp+250h+var_1D8], ecx
0x18013e5a2  mov     dword ptr [rbp+150h+var_1C0], r14d
0x18013e5a6  cmp     [rdi+48h], r15b
0x18013e5aa  jz      short loc_18013E5B2
0x18013e5ac  mov     rax, [rdi+40h]
0x18013e5b0  jmp     short loc_18013E5B5
0x18013e5b2  mov     rax, r15
0x18013e5b5  mov     [rbp+150h+var_1A8], rax
0x18013e5b9  lea     rax, aDeletevirtuald; "DeleteVirtualDisk"
0x18013e5c0  mov     [rbp+150h+var_1B0], rax
0x18013e5c4  lea     rax, aVirtualdisk_0; "VirtualDisk"
0x18013e5cb  mov     [rbp+150h+var_1C8], rax
0x18013e5cf  lea     rax, [rbp+150h+var_1B8]
0x18013e5d3  mov     [rsp+250h+var_1E8], rax
0x18013e5d8  lea     rax, [rbp+150h+var_190]
0x18013e5dc  mov     [rsp+250h+var_1F0], rax
0x18013e5e1  lea     rax, [rbp+150h+var_198]
0x18013e5e5  mov     [rsp+250h+var_1F8], rax
0x18013e5ea  lea     rax, [rbp+150h+var_1A0]
0x18013e5ee  mov     [rsp+250h+var_200], rax
0x18013e5f3  lea     rax, [rsp+250h+var_1E0]
0x18013e5f8  mov     [rsp+250h+var_208], rax
0x18013e5fd  lea     rax, [rsp+250h+var_1D8]
0x18013e602  mov     [rsp+250h+var_210], rax
0x18013e607  lea     rax, [rbp+150h+var_1C0]
0x18013e60b  mov     [rsp+250h+var_218], rax
0x18013e610  lea     rax, [rbp+150h+var_1A8]
0x18013e614  mov     [rsp+250h+var_220], rax
0x18013e619  lea     rax, [rbp+150h+var_1B0]
0x18013e61d  mov     [rsp+250h+var_228], rax
0x18013e622  lea     rax, [rbp+150h+var_1C8]
0x18013e626  mov     qword ptr [rsp+250h+var_230], rax
0x18013e62b  lea     rdx, dword_180353CC4
0x18013e632  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18013e637  lea     rcx, [rbp+150h+instance]; self
0x18013e63b  call    MI_Instance_Destruct
0x18013e640  mov     eax, cs:dword_18039EB68
0x18013e646  cmp     eax, 5
0x18013e649  jbe     short loc_18013E676
0x18013e64b  mov     dword ptr [rsp+250h+var_1E0], 0EFh
0x18013e653  mov     [rbp+150h+var_1B8], r13
0x18013e657  lea     rax, [rsp+250h+var_1E0]
0x18013e65c  mov     [rsp+250h+var_228], rax
0x18013e661  lea     rax, [rbp+150h+var_1B8]
0x18013e665  mov     qword ptr [rsp+250h+var_230], rax
0x18013e66a  lea     rdx, byte_1803528B7
0x18013e671  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18013e676  mov     edx, ebx; result
0x18013e678  mov     rcx, rsi; context
0x18013e67b  call    MI_Context_PostResult_0
0x18013e680  lea     rcx, [rbp+150h+var_188]; this
0x18013e684  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x18013e689  lea     rcx, [rbp+150h+var_1D0]
0x18013e68d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
  ... truncated ...
```
