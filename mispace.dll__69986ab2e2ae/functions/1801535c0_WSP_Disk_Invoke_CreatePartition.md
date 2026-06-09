# WSP_Disk_Invoke_CreatePartition

- ea: `0x1801535c0`
- end: `0x180153f86`
- name: `WSP_Disk_Invoke_CreatePartition`
- size: `2502`
- prototype: ``
- caller_count: `0`
- callee_count: `38`
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
- `0x18000c644`
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
- `0x180025e78`
- `0x180081c44`
- `0x180114b00`
- `0x1801166d4`
- `0x180117ba4`
- `0x180119964`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x180151ac4`
- `0x1801535c0`
- `0x180167798`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180153641`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801536ad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180153f4f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180153641`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801536ad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180153f4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180153e1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180153e1d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015366b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015366b`

## string_xrefs

- `0x1801536bf`: `WSP_Disk_Invoke_CreatePartition`
- `0x1801537fb`: `WSP_Disk_Invoke_CreatePartition`
- `0x180153901`: `WSP_Disk_Invoke_CreatePartition`
- `0x180153a08`: `WSP_Disk_Invoke_CreatePartition`
- `0x180153be7`: `WSP_Disk_Invoke_CreatePartition`
- `0x180153802`: `CreatePartition`
- `0x180153d84`: `CreatePartition`
- `0x180153e05`: `CreatePartition`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall WSP_Disk_Invoke_CreatePartition(
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
  unsigned int v11; // r13d
  int v12; // r8d
  int v13; // r9d
  const WCHAR *v14; // r14
  const struct _MI_ConstStringField *v15; // r12
  enum _MI_Result v16; // ebx
  int v17; // r15d
  unsigned int SubsystemType; // ebx
  int SubsystemVersion; // r15d
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  int v23; // r8d
  int v24; // r9d
  const unsigned __int16 *v25; // rax
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  __int16 *v29; // rdx
  int v30; // ecx
  MI_Uint32 Partition; // esi
  int v32; // r8d
  int v33; // r9d
  struct CPmPartition *v34; // rcx
  struct CPmPartition *v35; // rcx
  char *v36; // rdx
  const MI_Char *v37; // rax
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  int v42; // [rsp+70h] [rbp-90h] BYREF
  MI_Uint32 v43; // [rsp+74h] [rbp-8Ch] BYREF
  const char *p_self; // [rsp+78h] [rbp-88h] BYREF
  const char *v45; // [rsp+80h] [rbp-80h] BYREF
  int v46; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v47; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v48; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpFileName; // [rsp+98h] [rbp-68h] BYREF
  struct CPmPartition *v50; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v51; // [rsp+A8h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v53; // [rsp+B8h] [rbp-48h] BYREF
  const char *v54; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v55; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v56; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v57; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v58; // [rsp+E0h] [rbp-20h]
  struct _MI_Instance v59; // [rsp+F0h] [rbp-10h] BYREF
  MI_Value value; // [rsp+130h] [rbp+30h] BYREF
  MI_Instance instance; // [rsp+160h] [rbp+60h] BYREF
  struct _MI_ConstUint32Field v62; // [rsp+1A0h] [rbp+A0h] BYREF
  struct _MI_Instance *v63; // [rsp+200h] [rbp+100h]
  char v64; // [rsp+208h] [rbp+108h]
  MI_Instance self; // [rsp+220h] [rbp+120h] BYREF
  MI_Instance v66; // [rsp+330h] [rbp+230h] BYREF
  GUID ActivityId; // [rsp+480h] [rbp+380h] BYREF
  __int128 v68; // [rsp+490h] [rbp+390h] BYREF
  int v69; // [rsp+4A0h] [rbp+3A0h]
  GUID v70; // [rsp+4A8h] [rbp+3A8h]
  GUID v71; // [rsp+4B8h] [rbp+3B8h] BYREF
  __int128 v72; // [rsp+4D0h] [rbp+3D0h] BYREF
  int v73; // [rsp+4E0h] [rbp+3E0h]
  char v74; // [rsp+4E4h] [rbp+3E4h]
  __int16 v75; // [rsp+4E6h] [rbp+3E6h]
  __int128 v76; // [rsp+4E8h] [rbp+3E8h]
  __int128 v77; // [rsp+4F8h] [rbp+3F8h]
  __int64 v78; // [rsp+508h] [rbp+408h]

  v53 = a4;
  v55 = a5;
  v51 = (unsigned __int64)a6;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  v11 = 0;
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v70 = ActivityId;
  v71 = ActivityId;
  EventActivityIdControl(4u, &v71);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v48 = 807;
    lpFileName = (LPCWSTR)"WSP_Disk_Invoke_CreatePartition";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"WSP_Disk_Invoke_CreatePartition",
      (unsigned int)byte_18035A779,
      v12,
      v13,
      (__int64)&lpFileName,
      (__int64)&v48);
  }
  v14 = 0;
  lpFileName = 0;
  LODWORD(v54) = 0;
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0xB8u);
  v66.ft = 0;
  memset_0(&v66.classDecl, 0, 0x148u);
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v50 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v50);
  v50 = 0;
  v47 = 0;
  CSmTimer::CSmTimer((CSmTimer *)&v56);
  hMem = 0;
  self.ft = 0;
  memset_0(&self.classDecl, 0, 0x108u);
  CSmTimer::Start((CSmTimer *)&v56);
  LODWORD(v45) = WspIsRemoteRequest(a2);
  v15 = a6 + 4;
  if ( a6[4].exists && (unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)v15->value) )
    v11 = 1;
  v48 = 0;
  v16 = (unsigned int)WspProviderEnter(a2);
  if ( v16 )
    goto LABEL_9;
  if ( (unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)v15->value) )
  {
    v16 = (unsigned int)WspInvokeRemoteMethod(a2, a4, (unsigned __int16 *)v15->value, v55, a7);
LABEL_9:
    v17 = (int)v45;
    goto LABEL_73;
  }
  v68 = 0;
  v69 = 0;
  v46 = 0;
  SubsystemType = WspGetSubsystemType(v15->value);
  SubsystemVersion = _GetSubsystemVersion(&v46);
  WspGetSubsystemInfo(SubsystemType, (struct _SUBSYSTEM_INFO *)&v68);
  if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
  {
    v43 = SubsystemVersion != v46;
    LOWORD(v46) = v69;
    v42 = SubsystemType;
    p_self = (const char *)&v68;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v20,
      (unsigned int)byte_18035A041,
      v21,
      v22,
      (__int64)&p_self,
      (__int64)&v42,
      (__int64)&v46,
      (__int64)&v43);
  }
  if ( !a7 )
  {
    v16 = MI_RESULT_INVALID_PARAMETER;
LABEL_17:
    v17 = (int)v45;
    goto LABEL_18;
  }
  v16 = (unsigned int)WspUnpackObjectId((unsigned __int16 *)v15->value, &v54, &v42, &lpFileName);
  if ( v16 )
  {
    if ( (unsigned int)dword_18039EB68 > 2 )
    {
      v43 = 848;
      v29 = &word_18035AB0E;
LABEL_25:
      p_self = "WSP_Disk_Invoke_CreatePartition";
      v42 = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v26,
        (_DWORD)v29,
        v27,
        v28,
        (__int64)&p_self,
        (__int64)&v43,
        (__int64)&v42);
      v14 = lpFileName;
      v17 = (int)v45;
      goto LABEL_18;
    }
    goto LABEL_29;
  }
  v16 = MI_Context_ConstructParameters(a2, &WSP_Disk_CreatePartition_rtti, &instance);
  if ( v16 )
  {
    if ( (unsigned int)dword_18039EB68 > 2 )
    {
      v43 = 856;
      v29 = (__int16 *)byte_180359A59;
      goto LABEL_25;
    }
LABEL_29:
    v14 = lpFileName;
    goto LABEL_17;
  }
  Partition = WspParseCreatePartitionParameters(a7, &v72);
  v14 = lpFileName;
  if ( Partition )
  {
    v17 = (int)v45;
    goto LABEL_51;
  }
  if ( (_DWORD)v54 )
  {
    Partition = PmcCreatePartition(lpFileName, &v72, &v50, &hMem);
    v17 = (int)v45;
    if ( Partition )
      goto LABEL_51;
    v34 = v50;
    *((_BYTE *)v50 + 76) = 0;
    *(_WORD *)((char *)v34 + 77) = *(_WORD *)((char *)&p_self + 1);
    *((_BYTE *)v34 + 79) = BYTE3(p_self);
    *((_DWORD *)v34 + 20) = 0;
    if ( !v17 && (unsigned int)PmGetDiskNumber(v14, &v47) )
    {
      v35 = v50;
      *((_DWORD *)v50 + 20) = v47;
      *((_BYTE *)v35 + 76) = 1;
    }
    PmcRefreshDisk(v14);
  }
  else
  {
    Partition = PmCreatePartition((unsigned __int16 *)lpFileName);
    v17 = (int)v45;
    if ( Partition )
      goto LABEL_51;
  }
  if ( !a2 || !a2->ft )
  {
    v16 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_47;
  }
  v16 = ((unsigned int (__fastcall *)(MI_Context *, __int64 *, MI_Instance *))a2->ft->ConstructInstance)(
          a2,
          &WSP_Partition_rtti,
          &v66);
  if ( v16 )
  {
LABEL_47:
    if ( (unsigned int)dword_18039EB68 <= 2 )
      goto LABEL_18;
    v43 = 909;
    v36 = &byte_180359317;
    goto LABEL_49;
  }
  if ( WSP_Partition_PopulateMIStructure(v50, 0, (struct _WSP_Partition *)&v66) == MI_RESULT_OK )
  {
    p_self = (const char *)&v66;
    v16 = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD, const char **, _QWORD, enum _MI_Result))instance.ft->SetElementAt)(
            &instance,
            (unsigned int)(v16 + 11),
            &p_self,
            (unsigned int)(v16 + 15),
            v16);
    if ( v16 )
    {
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_18;
      v43 = 921;
      v36 = &byte_18035A7A7;
      goto LABEL_49;
    }
  }
LABEL_51:
  v62.value = Partition;
  v62.exists = 1;
  if ( !hMem )
    goto LABEL_62;
  if ( a2 && a2->ft )
  {
    v16 = ((unsigned int (__fastcall *)(MI_Context *, __int64 *, MI_Instance *))a2->ft->ConstructInstance)(
            a2,
            &MSFT_StorageExtendedStatus_rtti,
            &self);
    if ( v16 == MI_RESULT_OK )
    {
      if ( (unsigned int)CSpExtendedStatus::SuexToMsftExtendedStatus(
                           (struct _SUEX_EXTENDEDSTATUS_OBJECT *)hMem,
                           (struct _MSFT_StorageExtendedStatus *)&self) )
      {
        p_self = (const char *)&self;
        v16 = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD, const char **, _QWORD, enum _MI_Result))instance.ft->SetElementAt)(
                &instance,
                (unsigned int)(v16 + 12),
                &p_self,
                (unsigned int)(v16 + 15),
                v16);
        if ( v16 )
        {
          if ( (unsigned int)dword_18039EB68 > 2 )
          {
            v43 = 952;
            v36 = byte_180359DDD;
LABEL_49:
            p_self = "WSP_Disk_Invoke_CreatePartition";
            v42 = v16;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v30,
              (_DWORD)v36,
              v32,
              v33,
              (__int64)&p_self,
              (__int64)&v43,
              (__int64)&v42);
            goto LABEL_18;
          }
          goto LABEL_18;
        }
      }
LABEL_62:
      v16 = MI_Instance_Destruct((MI_Instance *)a2);
      if ( v16 == MI_RESULT_OK || (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_18;
      v43 = 962;
      v36 = byte_180359BA3;
      goto LABEL_49;
    }
  }
  else
  {
    v16 = MI_RESULT_INVALID_PARAMETER;
  }
  if ( (unsigned int)dword_18039EB68 > 2 )
  {
    v43 = 942;
    v36 = (char *)&dword_180358CAC;
    goto LABEL_49;
  }
LABEL_18:
  CSmTimer::Stop((CSmTimer *)&v56);
  SmLogOnMethodFailure(v53, v55, v15, &v62, v16, 0);
  if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
  {
    v53 = 0;
    if ( v64 )
    {
      v59 = *v63;
      v25 = SmMIGetString(L"ObjectId", &v59, 0);
    }
    else
    {
      v25 = 0;
    }
    p_self = (const char *)v25;
    v55 = (unsigned __int16 *)"WspPartition";
    lpFileName = (LPCWSTR)(1000 * (v57 - v56) / v58);
    v42 = v16;
    v43 = v62.exists != 0 ? v62.value : 0;
    v47 = v11;
    if ( *(_BYTE *)(v51 + 72) )
      v37 = v15->value;
    else
      v37 = 0;
    v51 = (unsigned __int64)v37;
    v54 = "CreatePartition";
    v45 = "WspDisk";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v62.exists != 0 ? v62.value : 0,
      (unsigned int)&byte_180358777,
      v23,
      v24,
      (__int64)&v45,
      (__int64)&v54,
      (__int64)&v51,
      (__int64)&v47,
      (__int64)&v43,
      (__int64)&v42,
      (__int64)&lpFileName,
      (__int64)&v55,
      (__int64)&p_self,
      (__int64)&v53);
  }
  WspFreeString(v14);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  MI_Instance_Destruct(&self);
  MI_Instance_Destruct(&v66);
  MI_Instance_Destruct(&instance);
LABEL_73:
  MI_Context_PostResult_0(a2, v16);
  WspProviderExit(v48);
  if ( v17 )
  {
    CSmTimer::Stop((CSmTimer *)&v56);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        v51 = 1000 * (v57 - v56) / v58;
        v42 = v11;
        v53 = (unsigned __int16 *)"CreatePartition";
        p_self = "WspDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v38,
          (unsigned int)&unk_180358E30,
          v39,
          v40,
          (__int64)&p_self,
          (__int64)&v53,
          (__int64)&v42,
          (__int64)&v51);
      }
    }
  }
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v42 = 1013;
    v51 = (unsigned __int64)"WSP_Disk_Invoke_CreatePartition";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v38,
      (unsigned int)&dword_180359974,
      v39,
      v40,
      (__int64)&v51,
      (__int64)&v42);
  }
  CSmTimer::~CSmTimer((CSmTimer *)&v56);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v50);
  return EventActivityIdControl(4u, &v71);
}

```

## disassembly

```asm
0x1801535c0  mov     [rsp-8+arg_0], rbx
0x1801535c5  push    rbp
0x1801535c6  push    rsi
0x1801535c7  push    rdi
0x1801535c8  push    r12
0x1801535ca  push    r13
0x1801535cc  push    r14
0x1801535ce  push    r15
0x1801535d0  lea     rbp, [rsp-420h]
0x1801535d8  sub     rsp, 520h
0x1801535df  mov     rax, cs:__security_cookie
0x1801535e6  xor     rax, rsp
0x1801535e9  mov     [rbp+450h+var_40], rax
0x1801535f0  mov     r15, r9
0x1801535f3  mov     [rbp+450h+var_498], r9
0x1801535f7  mov     rdi, rdx
0x1801535fa  mov     rax, [rbp+450h+arg_20]
0x180153601  mov     [rbp+450h+var_488], rax
0x180153605  mov     rbx, [rbp+450h+arg_28]
0x18015360c  mov     [rbp+450h+var_4A8], rbx
0x180153610  mov     rsi, [rbp+450h+arg_30]
0x180153617  xorps   xmm0, xmm0
0x18015361a  xor     eax, eax
0x18015361c  movups  xmmword ptr [rbp+450h+value], xmm0
0x180153620  movups  xmmword ptr [rbp+450h+value+10h], xmm0
0x180153624  mov     qword ptr [rbp+450h+value+20h], rax
0x180153628  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18015362f  movdqu  xmmword ptr [rbp+450h+ActivityId.Data1], xmm0
0x180153637  lea     rdx, [rbp+450h+ActivityId]; ActivityId
0x18015363e  lea     ecx, [rax+1]; ControlCode
0x180153641  call    cs:__imp_EventActivityIdControl
0x180153648  nop     dword ptr [rax+rax+00h]
0x18015364d  lea     r9, [rbp+450h+value]; value
0x180153651  mov     rcx, rdi; context
0x180153654  call    MI_Context_GetCustomOption_1
0x180153659  xor     r13d, r13d
0x18015365c  test    eax, eax
0x18015365e  jnz     short loc_180153677
0x180153660  lea     rdx, [rbp+450h+ActivityId]; pclsid
0x180153667  mov     rcx, qword ptr [rbp+450h+value]; lpsz
0x18015366b  call    cs:__imp_CLSIDFromString
0x180153672  nop     dword ptr [rax+rax+00h]
0x180153677  mov     rcx, qword ptr [rbp+450h+ActivityId.Data1]
0x18015367e  mov     [rbp+450h+var_A8], rcx
0x180153685  mov     rax, qword ptr [rbp+450h+ActivityId.Data4]
0x18015368c  mov     [rbp+450h+var_A0], rax
0x180153693  mov     qword ptr [rbp+450h+var_98.Data1], rcx
0x18015369a  mov     qword ptr [rbp+450h+var_98.Data4], rax
0x1801536a1  lea     rdx, [rbp+450h+var_98]; ActivityId
0x1801536a8  mov     ecx, 4; ControlCode
0x1801536ad  call    cs:__imp_EventActivityIdControl
0x1801536b4  nop     dword ptr [rax+rax+00h]
0x1801536b9  mov     eax, cs:dword_18039EB68
0x1801536bf  lea     rcx, aWspDiskInvokeC_1; "WSP_Disk_Invoke_CreatePartition"
0x1801536c6  cmp     eax, 5
0x1801536c9  jbe     short loc_1801536F4
0x1801536cb  mov     [rbp+450h+var_4C0], 327h
0x1801536d2  mov     [rbp+450h+lpFileName], rcx
0x1801536d6  lea     rax, [rbp+450h+var_4C0]
0x1801536da  mov     [rsp+550h+var_528], rax
0x1801536df  lea     rax, [rbp+450h+lpFileName]
0x1801536e3  mov     qword ptr [rsp+550h+var_530], rax
0x1801536e8  lea     rdx, byte_18035A779
0x1801536ef  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1801536f4  mov     r14, r13
0x1801536f7  mov     [rbp+450h+lpFileName], r13
0x1801536fb  mov     dword ptr [rbp+450h+var_490], r13d
0x1801536ff  mov     [rbp+450h+instance.ft], r13
0x180153703  xor     edx, edx; Val
0x180153705  mov     r8d, 0B8h; Size
0x18015370b  lea     rcx, [rbp+450h+instance.classDecl]; void *
0x18015370f  call    memset_0
0x180153714  mov     [rbp+450h+var_220.ft], r13
0x18015371b  xor     edx, edx; Val
0x18015371d  mov     r8d, 148h; Size
0x180153723  lea     rcx, [rbp+450h+var_220.classDecl]; void *
0x18015372a  call    memset_0
0x18015372f  xorps   xmm0, xmm0
0x180153732  xor     eax, eax
0x180153734  movups  [rbp+450h+var_80], xmm0
0x18015373b  mov     [rbp+450h+var_70], eax
0x180153741  mov     [rbp+450h+var_6C], r13b
0x180153748  mov     [rbp+450h+var_6A], r13w
0x180153750  movups  [rbp+450h+var_68], xmm0
0x180153757  movups  [rbp+450h+var_58], xmm0
0x18015375e  mov     [rbp+450h+var_48], rax
0x180153765  mov     [rbp+450h+var_4B0], r13
0x180153769  lea     rcx, [rbp+450h+var_4B0]
0x18015376d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180153772  mov     [rbp+450h+var_4B0], r13
0x180153776  mov     [rbp+450h+var_4C4], r13d
0x18015377a  lea     rcx, [rbp+450h+var_480]; this
0x18015377e  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180153783  mov     [rbp+450h+hMem], r13
0x180153787  mov     [rbp+450h+self.ft], r13
0x18015378e  xor     edx, edx; Val
0x180153790  mov     r8d, 108h; Size
0x180153796  lea     rcx, [rbp+450h+self.classDecl]; void *
0x18015379d  call    memset_0
0x1801537a2  lea     rcx, [rbp+450h+var_480]; this
0x1801537a6  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x1801537ab  mov     rcx, rdi; context
0x1801537ae  call    WspIsRemoteRequest
0x1801537b3  mov     dword ptr [rbp+450h+var_4D0], eax
0x1801537b6  lea     r12, [rbx+40h]
0x1801537ba  cmp     [r12+8], r13b
0x1801537bf  jz      short loc_1801537D4
0x1801537c1  mov     rcx, [r12]; unsigned __int16 *
0x1801537c5  call    WspIsRemoteInstance
0x1801537ca  test    al, al
0x1801537cc  jz      short loc_1801537D4
0x1801537ce  mov     r13d, 1
0x1801537d4  mov     [rbp+450h+var_4C0], 0
0x1801537db  lea     r9, [rbp+450h+var_4C0]
0x1801537df  mov     r8d, 1
0x1801537e5  mov     rdx, [r12]
0x1801537e9  mov     rcx, rdi; context
0x1801537ec  call    WspProviderEnter
0x1801537f1  mov     ebx, eax
0x1801537f3  test    eax, eax
0x1801537f5  jz      short loc_18015380E
0x1801537f7  mov     r15d, dword ptr [rbp+450h+var_4D0]
0x1801537fb  lea     rsi, aWspDiskInvokeC_1; "WSP_Disk_Invoke_CreatePartition"
0x180153802  lea     r12, aCreatepartitio_0; "CreatePartition"
0x180153809  jmp     loc_180153E52
0x18015380e  mov     rcx, [r12]; unsigned __int16 *
0x180153812  call    WspIsRemoteInstance
0x180153817  test    al, al
0x180153819  jz      short loc_180153837
0x18015381b  mov     qword ptr [rsp+550h+var_530], rsi; void *
0x180153820  mov     r9, [rbp+450h+var_488]; unsigned __int16 *
0x180153824  mov     r8, [r12]; unsigned __int16 *
0x180153828  mov     rdx, r15; unsigned __int16 *
0x18015382b  mov     rcx, rdi; struct _MI_Context *
0x18015382e  call    WspInvokeRemoteMethod
0x180153833  mov     ebx, eax
0x180153835  jmp     short loc_1801537F7
0x180153837  xorps   xmm0, xmm0
0x18015383a  xor     eax, eax
0x18015383c  movups  [rbp+450h+var_C0], xmm0
0x180153843  mov     [rbp+450h+var_B0], eax
0x180153849  mov     [rbp+450h+var_4C8], eax
0x18015384c  mov     rcx, [r12]
0x180153850  call    WspGetSubsystemType
0x180153855  mov     ebx, eax
0x180153857  lea     rcx, [rbp+450h+var_4C8]
0x18015385b  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x180153860  mov     r15d, eax
0x180153863  lea     rdx, [rbp+450h+var_C0]; struct _SUBSYSTEM_INFO *
0x18015386a  mov     ecx, ebx; unsigned int
0x18015386c  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x180153871  mov     ecx, cs:dword_18039EB68
0x180153877  cmp     ecx, 5
0x18015387a  jbe     short loc_1801538F1
0x18015387c  mov     rdx, 400000000000h
0x180153886  lea     rcx, dword_18039EB68
0x18015388d  call    _tlgKeywordOn
0x180153892  test    al, al
0x180153894  jz      short loc_1801538F1
0x180153896  xor     eax, eax
0x180153898  cmp     r15d, [rbp+450h+var_4C8]
0x18015389c  setnz   al
0x18015389f  mov     [rsp+550h+var_4DC], eax
0x1801538a3  movzx   eax, word ptr [rbp+450h+var_B0]
0x1801538aa  mov     word ptr [rbp+450h+var_4C8], ax
0x1801538ae  mov     [rsp+550h+var_4E0], ebx
0x1801538b2  lea     rax, [rbp+450h+var_C0]
0x1801538b9  mov     [rsp+550h+var_4D8], rax
0x1801538be  lea     rax, [rsp+550h+var_4DC]
0x1801538c3  mov     [rsp+550h+var_518], rax
0x1801538c8  lea     rax, [rbp+450h+var_4C8]
0x1801538cc  mov     [rsp+550h+var_520], rax
0x1801538d1  lea     rax, [rsp+550h+var_4E0]
0x1801538d6  mov     [rsp+550h+var_528], rax
0x1801538db  lea     rax, [rsp+550h+var_4D8]
0x1801538e0  mov     qword ptr [rsp+550h+var_530], rax
0x1801538e5  lea     rdx, byte_18035A041
0x1801538ec  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1801538f1  test    rsi, rsi
0x1801538f4  jnz     loc_1801539B5
0x1801538fa  lea     ebx, [rsi+4]
0x1801538fd  mov     r15d, dword ptr [rbp+450h+var_4D0]
0x180153901  lea     rsi, aWspDiskInvokeC_1; "WSP_Disk_Invoke_CreatePartition"
0x180153908  lea     rcx, [rbp+450h+var_480]; this
0x18015390c  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180153911  mov     [rsp+550h+var_528], 0; unsigned __int16 *
0x18015391a  mov     [rsp+550h+var_530], ebx; enum _MI_Result
0x18015391e  lea     r9, [rbp+450h+var_3B0]; struct _MI_ConstUint32Field *
0x180153925  mov     r8, r12; struct _MI_ConstStringField *
0x180153928  mov     rdx, [rbp+450h+var_488]; unsigned __int16 *
0x18015392c  mov     rcx, [rbp+450h+var_498]; unsigned __int16 *
0x180153930  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x180153935  mov     eax, cs:dword_18039EB68
0x18015393b  cmp     eax, 5
0x18015393e  jbe     loc_180153E05
0x180153944  mov     rdx, 400000000000h
0x18015394e  lea     rcx, dword_18039EB68
0x180153955  call    _tlgKeywordOn
0x18015395a  test    al, al
0x18015395c  jz      loc_180153E05
0x180153962  mov     [rbp+450h+var_498], 0
0x18015396a  cmp     [rbp+450h+var_348], 0
0x180153971  jz      loc_180153D27
0x180153977  mov     rax, [rbp+450h+var_350]
0x18015397e  movups  xmm0, xmmword ptr [rax]
0x180153981  movaps  xmmword ptr [rbp+450h+var_460.ft], xmm0
0x180153985  movups  xmm1, xmmword ptr [rax+10h]
0x180153989  movaps  xmmword ptr [rbp+450h+var_460.serverName], xmm1
0x18015398d  movups  xmm0, xmmword ptr [rax+20h]
0x180153991  movaps  xmmword ptr [rbp+450h+var_460.reserved], xmm0
0x180153995  movups  xmm1, xmmword ptr [rax+30h]
0x180153999  movaps  xmmword ptr [rbp+450h+var_460.reserved+10h], xmm1
0x18015399d  xor     r8d, r8d; unsigned __int16 *
0x1801539a0  lea     rdx, [rbp+450h+var_460]; struct _MI_Instance
0x1801539a4  lea     rcx, name; "ObjectId"
0x1801539ab  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x1801539b0  jmp     loc_180153D29
0x1801539b5  lea     r9, [rbp+450h+lpFileName]
0x1801539b9  lea     r8, [rsp+550h+var_4E0]
0x1801539be  lea     rdx, [rbp+450h+var_490]
0x1801539c2  mov     rcx, [r12]; unsigned __int16 *
0x1801539c6  call    WspUnpackObjectId
0x1801539cb  mov     ebx, eax
0x1801539cd  test    eax, eax
0x1801539cf  jz      short loc_180153A2F
0x1801539d1  mov     eax, cs:dword_18039EB68
0x1801539d7  cmp     eax, 2
0x1801539da  jbe     loc_180153A64
0x1801539e0  mov     [rsp+550h+var_4DC], 350h
0x1801539e8  lea     rdx, word_18035AB0E
0x1801539ef  lea     rax, [rsp+550h+var_4E0]
0x1801539f4  mov     [rsp+550h+var_520], rax
0x1801539f9  lea     rax, [rsp+550h+var_4DC]
0x1801539fe  mov     [rsp+550h+var_528], rax
0x180153a03  lea     rax, [rsp+550h+var_4D8]
0x180153a08  lea     rsi, aWspDiskInvokeC_1; "WSP_Disk_Invoke_CreatePartition"
0x180153a0f  mov     qword ptr [rsp+550h+var_530], rax
0x180153a14  mov     [rsp+550h+var_4D8], rsi
0x180153a19  mov     [rsp+550h+var_4E0], ebx
0x180153a1d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180153a22  mov     r14, [rbp+450h+lpFileName]
0x180153a26  mov     r15d, dword ptr [rbp+450h+var_4D0]
0x180153a2a  jmp     loc_180153908
0x180153a2f  lea     r8, [rbp+450h+instance]; instance
0x180153a33  lea     rdx, WSP_Disk_CreatePartition_rtti; methodDecl
0x180153a3a  mov     rcx, rdi; context
0x180153a3d  call    MI_Context_ConstructParameters
0x180153a42  mov     ebx, eax
0x180153a44  test    eax, eax
0x180153a46  jz      short loc_180153A6D
0x180153a48  mov     eax, cs:dword_18039EB68
0x180153a4e  cmp     eax, 2
0x180153a51  jbe     short loc_180153A64
0x180153a53  mov     [rsp+550h+var_4DC], 358h
0x180153a5b  lea     rdx, byte_180359A59
0x180153a62  jmp     short loc_1801539EF
0x180153a64  mov     r14, [rbp+450h+lpFileName]
0x180153a68  jmp     loc_1801538FD
0x180153a6d  lea     rdx, [rbp+450h+var_80]
0x180153a74  mov     rcx, rsi
0x180153a77  call    ?WspParseCreatePartitionParameters@@YA?AW4SM_RETURN_CODE@@PEBU_WSP_Disk_CreatePartition@@PEAU_PM_CREATE_PARTITION_PARAMETERS@@@Z; WspParseCreatePartitionParameters(_WSP_Disk_CreatePartition const *,_PM_CREATE_PARTITION_PARAMETERS *)
0x180153a7c  mov     esi, eax
0x180153a7e  mov     r14, [rbp+450h+lpFileName]
0x180153a82  test    eax, eax
0x180153a84  jnz     loc_180153C0B
0x180153a8a  lea     r9, [rbp+450h+hMem]
0x180153a8e  lea     r8, [rbp+450h+var_4B0]
0x180153a92  lea     rdx, [rbp+450h+var_80]
0x180153a99  mov     rcx, r14; unsigned __int16 *
0x180153a9c  cmp     dword ptr [rbp+450h+var_490], eax
0x180153a9f  jnz     short loc_180153AB6
0x180153aa1  call    ?PmCreatePartition@@YA?AW4SM_RETURN_CODE@@PEBGPEAU_PM_CREATE_PARTITION_PARAMETERS@@AEAV?$CSmRefPtr@VCPmPartition@@X@@PEAPEAU_SUEX_EXTENDEDSTATUS_OBJECT@@@Z; PmCreatePartition(ushort const *,_PM_CREATE_PARTITION_PARAMETERS *,CSmRefPtr<CPmPartition,void> &,_SUEX_EXTENDEDSTATUS_OBJECT * *)
0x180153aa6  mov     esi, eax
0x180153aa8  mov     r15d, dword ptr [rbp+450h+var_4D0]
0x180153aac  test    eax, eax
0x180153aae  jnz     loc_180153C0F
0x180153ab4  jmp     short loc_180153B0E
0x180153ab6  call    ?PmcCreatePartition@@YA?AW4SM_RETURN_CODE@@PEBGPEAU_PM_CREATE_PARTITION_PARAMETERS@@AEAV?$CSmRefPtr@VCPmPartition@@X@@PEAPEAU_SUEX_EXTENDEDSTATUS_OBJECT@@@Z; PmcCreatePartition(ushort const *,_PM_CREATE_PARTITION_PARAMETERS *,CSmRefPtr<CPmPartition,void> &,_SUEX_EXTENDEDSTATUS_OBJECT * *)
0x180153abb  mov     esi, eax
0x180153abd  mov     r15d, dword ptr [rbp+450h+var_4D0]
0x180153ac1  test    eax, eax
0x180153ac3  jnz     loc_180153C0F
0x180153ac9  mov     rcx, [rbp+450h+var_4B0]
0x180153acd  mov     [rcx+4Ch], al
0x180153ad0  movzx   eax, word ptr [rsp+550h+var_4D8+1]
0x180153ad5  mov     [rcx+4Dh], ax
0x180153ad9  mov     al, byte ptr [rsp+550h+var_4D8+3]
0x180153add  mov     [rcx+4Fh], al
0x180153ae0  mov     [rcx+50h], esi
0x180153ae3  test    r15d, r15d
0x180153ae6  jnz     short loc_180153B06
0x180153ae8  lea     rdx, [rbp+450h+var_4C4]; unsigned int *
0x180153aec  mov     rcx, r14; lpFileName
0x180153aef  call    ?PmGetDiskNumber@@YAHPEBGPEAK@Z; PmGetDiskNumber(ushort const *,ulong *)
0x180153af4  test    eax, eax
0x180153af6  jz      short loc_180153B06
0x180153af8  mov     rcx, [rbp+450h+var_4B0]
0x180153afc  mov     eax, [rbp+450h+var_4C4]
0x180153aff  mov     [rcx+50h], eax
0x180153b02  mov     byte ptr [rcx+4Ch], 1
  ... truncated ...
```
