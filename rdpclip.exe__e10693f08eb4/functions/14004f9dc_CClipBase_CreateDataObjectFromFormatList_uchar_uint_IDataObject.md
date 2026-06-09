# CClipBase::CreateDataObjectFromFormatList(uchar *,uint,IDataObject * *)

- ea: `0x14004f9dc`
- end: `0x1400501a1`
- name: `?CreateDataObjectFromFormatList@CClipBase@@IEAAJPEAEIPEAPEAUIDataObject@@@Z`
- size: `1989`
- prototype: `__int64 __fastcall(CClipBase *__hidden this, unsigned __int8 *, unsigned int, struct IDataObject **)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140054610`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005704`
- `0x140005750`
- `0x140011054`
- `0x140047a4c`
- `0x140047f74`
- `0x140048e0c`
- `0x140049880`
- `0x1400498d0`
- `0x14004f06c`
- `0x14004f154`
- `0x14004f9dc`
- `0x140050694`
- `0x1400517dc`
- `0x140051df4`
- `0x1400521f8`
- `0x14005557c`
- `0x140057c28`
- `0x1400648e8`
- `0x14006a120`
- `0x14006b010`

## import_xrefs

- `USER32!RegisterClipboardFormatW` at `0x14004fd71`
- `USER32!RegisterClipboardFormatW` at `0x14004fd71`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x14004ff8c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x14005013d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x14004ff8c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x14005013d`

## string_xrefs

- `0x14004fc3e`: `CreateFormatNamePacker failed!`
- `0x14004fb31`: `CreateDataObject failed!`

## pseudocode

```c
__int64 __fastcall CClipBase::CreateDataObjectFromFormatList(
        CClipBase *this,
        unsigned __int8 *a2,
        unsigned int a3,
        struct IDataObject **a4)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int CloudHistoryDataHandle; // edi
  CProxyDataObjectManager *v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // eax
  struct IClipboardLevelCallback *v12; // rdi
  unsigned __int8 v13; // al
  int v14; // edx
  int v15; // ecx
  int v16; // r8d
  unsigned int v17; // eax
  int v18; // edx
  const char *v19; // rcx
  int v20; // eax
  CClipFormatTypes *v21; // rcx
  PVOID *v22; // rax
  char v23; // bl
  unsigned int v24; // eax
  UINT v25; // ebx
  unsigned int v26; // eax
  CClipFormatTypes *v27; // rcx
  unsigned int v28; // r8d
  CClipFormatTypes *v29; // rcx
  CClipFormatTypes *v30; // rcx
  CClipFormatTypes *v31; // rcx
  CClipFormatTypes *v32; // rcx
  unsigned int v33; // eax
  unsigned int v34; // edi
  struct IDataObject *v35; // rbx
  unsigned int v36; // eax
  __int64 v37; // rax
  CClipFormatTypes *v38; // rcx
  struct IDataObject *v39; // rdi
  unsigned int v40; // ebx
  CClipFormatTypes *v41; // rcx
  unsigned int v42; // eax
  unsigned int v43; // eax
  CClipBase *v44; // rcx
  CClipFormatTypes *v45; // rcx
  struct IDataObject *v46; // rbx
  unsigned int v47; // edi
  CClipFormatTypes *v48; // rcx
  unsigned int v49; // eax
  struct IDataObject *v50; // rbx
  CClipFormatTypes *v51; // rcx
  unsigned int v52; // edi
  CClipFormatTypes *v53; // rcx
  unsigned int v54; // eax
  int IsRunningInWdagContainer; // ebx
  unsigned int v56; // eax
  unsigned int v57; // eax
  unsigned int v58; // eax
  int v60[2]; // [rsp+28h] [rbp-D8h]
  unsigned int v61; // [rsp+50h] [rbp-B0h] BYREF
  struct IDataObject *v62; // [rsp+58h] [rbp-A8h] BYREF
  HGLOBAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v64; // [rsp+68h] [rbp-98h]
  unsigned int v65; // [rsp+6Ch] [rbp-94h]
  void *v66; // [rsp+70h] [rbp-90h]
  struct CFormatNamePacker *v67; // [rsp+78h] [rbp-88h] BYREF
  HGLOBAL v68; // [rsp+80h] [rbp-80h] BYREF
  int v69; // [rsp+88h] [rbp-78h] BYREF
  struct IDataObject **v70; // [rsp+90h] [rbp-70h]
  WCHAR szFormat[264]; // [rsp+A0h] [rbp-60h] BYREF

  v70 = a4;
  v67 = 0;
  v62 = 0;
  v61 = 0;
  v68 = 0;
  v69 = 0;
  if ( !a4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        95,
        (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"ppIDataObject");
    }
    return (unsigned int)-2147467261;
  }
  *a4 = 0;
  v9 = (CProxyDataObjectManager *)*((_QWORD *)this + 34);
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids, v10);
    }
    return (unsigned int)-2147418113;
  }
  CloudHistoryDataHandle = CProxyDataObjectManager::CreateDataObject(v9, *((_DWORD *)this + 66), &v62);
  if ( CloudHistoryDataHandle < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        97,
        (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        v11,
        (__int64)"CreateDataObject failed!",
        CloudHistoryDataHandle);
    }
    goto LABEL_101;
  }
  v12 = (struct IClipboardLevelCallback *)(*(__int64 (__fastcall **)(CClipBase *))(*(_QWORD *)this + 192LL))(this);
  v13 = (*(__int64 (__fastcall **)(CClipBase *))(*(_QWORD *)this + 176LL))(this);
  v14 = *((_DWORD *)this + 198);
  if ( v14 )
    v15 = *((_DWORD *)this + 62);
  else
    v15 = 0;
  if ( v14 )
    v16 = *(_DWORD *)(*((_QWORD *)this + 77) + 48LL);
  else
    v16 = 0;
  CloudHistoryDataHandle = CreateFormatNamePacker(
                             &v67,
                             *((_DWORD *)this + 61),
                             v16,
                             *((_DWORD *)this + 47),
                             v15,
                             *((_DWORD *)this + 63),
                             *((_QWORD *)this + 102) != 0,
                             v13,
                             v12,
                             0);
  if ( CloudHistoryDataHandle < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_98;
    }
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = 98;
    v19 = "CreateFormatNamePacker failed!";
    goto LABEL_29;
  }
  CloudHistoryDataHandle = (*(__int64 (__fastcall **)(struct CFormatNamePacker *, unsigned __int8 *, _QWORD))(*(_QWORD *)v67 + 16LL))(
                             v67,
                             a2,
                             a3);
  if ( CloudHistoryDataHandle < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_98;
    }
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = 99;
    v19 = "SetBlobToDecode failed!";
LABEL_29:
    v60[0] = CloudHistoryDataHandle;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v18,
      (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
      v17,
      (__int64)v19,
      *(_QWORD *)v60);
    goto LABEL_98;
  }
  v65 = 0;
  v64 = 0;
  LODWORD(hMem) = 0;
  LODWORD(v66) = 0;
  while ( 1 )
  {
    v20 = (*(__int64 (__fastcall **)(struct CFormatNamePacker *, unsigned int *, WCHAR *, __int64))(*(_QWORD *)v67 + 24LL))(
            v67,
            &v61,
            szFormat,
            520);
    v21 = 0;
    CloudHistoryDataHandle = v20;
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v57 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          100,
          &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
          v57,
          CloudHistoryDataHandle);
      }
      goto LABEL_98;
    }
    if ( v20 == 1 )
      break;
    v22 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = v61;
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DdS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        101,
        (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        v24,
        v23,
        (__int64)szFormat);
      v22 = (PVOID *)WPP_GLOBAL_Control;
      v21 = 0;
    }
    if ( szFormat[0] )
    {
      v25 = RegisterClipboardFormatW(szFormat);
      if ( v25 )
        goto LABEL_49;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v26 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v25 + 102,
          &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
          v26,
          CloudHistoryDataHandle);
      }
    }
    else
    {
      v25 = v61;
      if ( v61 )
      {
LABEL_49:
        if ( v25 == CClipFormatTypes::RichTextFormat(v21) )
        {
          v28 = v61;
          v65 = v61;
          goto LABEL_60;
        }
        if ( v25 == CClipFormatTypes::MsSourceUrl(v27) )
        {
          v28 = v61;
          LODWORD(v66) = v61;
          goto LABEL_60;
        }
        if ( v25 == CClipFormatTypes::XmlSpreadsheet(v29) )
        {
          v28 = v61;
          LODWORD(hMem) = v61;
          goto LABEL_60;
        }
        if ( v25 == CClipFormatTypes::HtmlFormat(v30) )
        {
          v64 = v61;
        }
        else if ( v25 != CClipFormatTypes::IncludeInHistoryId(v31) && v25 != CClipFormatTypes::UploadToCloudId(v32) )
        {
          v28 = v61;
LABEL_60:
          CClipBase::AddFormatIdToDataObject(this, v25, v28, v62);
        }
      }
      else if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 1) != 0 && *((_BYTE *)v22 + 25) >= 2u )
      {
        v33 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids, v33);
      }
    }
  }
  v34 = v64;
  if ( v64 && (!v65 || (_DWORD)v66 || (_DWORD)hMem) )
  {
    v35 = v62;
    v36 = CClipFormatTypes::HtmlFormat(0);
    CClipBase::AddFormatIdToDataObject(this, v36, v34, v35);
  }
  if ( (*(unsigned int (__fastcall **)(CClipBase *))(*(_QWORD *)this + 128LL))(this) )
  {
    v37 = *(_QWORD *)this;
    hMem = 0;
    CloudHistoryDataHandle = (*(__int64 (__fastcall **)(CClipBase *, HGLOBAL *))(v37 + 136))(this, &hMem);
    if ( CloudHistoryDataHandle < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        v18 = 104;
        v19 = "GetEnterpriseDataId failed.";
        goto LABEL_29;
      }
      goto LABEL_98;
    }
    v66 = hMem;
    if ( hMem )
    {
      v39 = v62;
      v40 = CClipFormatTypes::EnterpriseId(v38);
      v42 = CClipFormatTypes::EnterpriseId(v41);
      CClipBase::AddFormatIdAndHGlobalDataToDataObject(this, v42, v40, v66, v39);
      if ( GlobalFree(hMem) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v43 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids, v43);
        }
      }
    }
  }
  if ( !(*(unsigned int (__fastcall **)(CClipBase *))(*(_QWORD *)this + 144LL))(this) )
  {
LABEL_89:
    IsRunningInWdagContainer = CClipBase::IsRunningInWdagContainer(v44, &v69);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v56 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        107,
        &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        v56,
        IsRunningInWdagContainer);
    }
    CloudHistoryDataHandle = 0;
    *v70 = v62;
    goto LABEL_98;
  }
  CloudHistoryDataHandle = CClipBase::GetCloudHistoryDataHandle(v44, &v68);
  if ( CloudHistoryDataHandle >= 0 )
  {
    v46 = v62;
    v47 = CClipFormatTypes::IncludeInHistoryId(v45);
    v49 = CClipFormatTypes::IncludeInHistoryId(v48);
    CClipBase::AddFormatIdAndHGlobalDataToDataObject(this, v49, v47, v68, v46);
    v50 = v62;
    v52 = CClipFormatTypes::UploadToCloudId(v51);
    v54 = CClipFormatTypes::UploadToCloudId(v53);
    CClipBase::AddFormatIdAndHGlobalDataToDataObject(this, v54, v52, v68, v50);
    goto LABEL_89;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = 106;
    v19 = "GetCloudHistoryDataHandle failed.";
    goto LABEL_29;
  }
LABEL_98:
  if ( v67 )
    (**(void (__fastcall ***)(struct CFormatNamePacker *, __int64))v67)(v67, 1);
  if ( CloudHistoryDataHandle < 0 )
  {
LABEL_101:
    if ( v68
      && GlobalFree(v68)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v58 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids, v58);
    }
  }
  return (unsigned int)CloudHistoryDataHandle;
}

```

## disassembly

```asm
0x14004f9dc  push    rbp
0x14004f9de  push    rbx
0x14004f9df  push    rsi
0x14004f9e0  push    rdi
0x14004f9e1  push    r12
0x14004f9e3  push    r15
0x14004f9e5  lea     rbp, [rsp-1C8h]
0x14004f9ed  sub     rsp, 2C8h
0x14004f9f4  mov     rax, cs:__security_cookie
0x14004f9fb  xor     rax, rsp
0x14004f9fe  mov     [rbp+1F0h+var_40], rax
0x14004fa05  mov     rbx, rdx
0x14004fa08  mov     [rbp+1F0h+var_260], r9
0x14004fa0c  xor     edx, edx
0x14004fa0e  mov     esi, r8d
0x14004fa11  mov     [rsp+2F0h+var_278], rdx
0x14004fa16  mov     r15, rcx
0x14004fa19  mov     [rsp+2F0h+var_298], rdx
0x14004fa1e  mov     [rsp+2F0h+var_2A0], edx
0x14004fa22  mov     [rbp+1F0h+var_270], rdx
0x14004fa26  mov     [rbp+1F0h+var_268], edx
0x14004fa29  test    r9, r9
0x14004fa2c  jnz     short loc_14004FA87
0x14004fa2e  mov     rax, cs:WPP_GLOBAL_Control
0x14004fa35  lea     rsi, WPP_GLOBAL_Control
0x14004fa3c  cmp     rax, rsi
0x14004fa3f  jz      short loc_14004FA7D
0x14004fa41  test    byte ptr [rax+1Ch], 8
0x14004fa45  jz      short loc_14004FA7D
0x14004fa47  cmp     byte ptr [rax+19h], 2
0x14004fa4b  jb      short loc_14004FA7D
0x14004fa4d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004fa52  lea     rcx, aPpidataobject; "ppIDataObject"
0x14004fa59  mov     edx, 5Fh ; '_'
0x14004fa5e  mov     [rsp+2F0h+var_2D0], rcx
0x14004fa63  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x14004fa6a  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fa71  mov     r9d, eax
0x14004fa74  mov     rcx, [rcx+10h]
0x14004fa78  call    WPP_SF_Ds
0x14004fa7d  mov     edi, 80004003h
0x14004fa82  jmp     loc_140050180
0x14004fa87  mov     [r9], rdx
0x14004fa8a  mov     rcx, [rcx+110h]; this
0x14004fa91  test    rcx, rcx
0x14004fa94  jnz     short loc_14004FAE3
0x14004fa96  mov     rax, cs:WPP_GLOBAL_Control
0x14004fa9d  lea     rsi, WPP_GLOBAL_Control
0x14004faa4  cmp     rax, rsi
0x14004faa7  jz      short loc_14004FAD9
0x14004faa9  test    byte ptr [rax+1Ch], 1
0x14004faad  jz      short loc_14004FAD9
0x14004faaf  cmp     byte ptr [rax+19h], 2
0x14004fab3  jb      short loc_14004FAD9
0x14004fab5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004faba  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fac1  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x14004fac8  mov     edx, 60h ; '`'
0x14004facd  mov     r9d, eax
0x14004fad0  mov     rcx, [rcx+10h]
0x14004fad4  call    WPP_SF_d
0x14004fad9  mov     edi, 8000FFFFh
0x14004fade  jmp     loc_140050180
0x14004fae3  mov     edx, [r15+108h]; int
0x14004faea  lea     r8, [rsp+2F0h+var_298]; struct IDataObject **
0x14004faef  call    ?CreateDataObject@CProxyDataObjectManager@@QEAAJHPEAPEAUIDataObject@@@Z; CProxyDataObjectManager::CreateDataObject(int,IDataObject * *)
0x14004faf4  lea     r12, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x14004fafb  mov     edi, eax
0x14004fafd  test    eax, eax
0x14004faff  jns     short loc_14004FB61
0x14004fb01  mov     rax, cs:WPP_GLOBAL_Control
0x14004fb08  lea     rsi, WPP_GLOBAL_Control
0x14004fb0f  cmp     rax, rsi
0x14004fb12  jz      loc_140050131
0x14004fb18  test    byte ptr [rax+1Ch], 8
0x14004fb1c  jz      loc_140050131
0x14004fb22  cmp     byte ptr [rax+19h], 2
0x14004fb26  jb      loc_140050131
0x14004fb2c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004fb31  lea     rcx, aCreatedataobje_0; "CreateDataObject failed!"
0x14004fb38  mov     [rsp+2F0h+var_2C8], edi
0x14004fb3c  mov     [rsp+2F0h+var_2D0], rcx
0x14004fb41  mov     edx, 61h ; 'a'
0x14004fb46  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fb4d  mov     r9d, eax
0x14004fb50  mov     r8, r12
0x14004fb53  mov     rcx, [rcx+10h]
0x14004fb57  call    WPP_SF_DsD
0x14004fb5c  jmp     loc_140050131
0x14004fb61  mov     rax, [r15]
0x14004fb64  mov     rcx, r15
0x14004fb67  mov     rax, [rax+0C0h]
0x14004fb6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fb73  mov     rcx, [r15]
0x14004fb76  mov     rdi, rax
0x14004fb79  mov     rax, [rcx+0B0h]
0x14004fb80  mov     rcx, r15
0x14004fb83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fb88  mov     edx, [r15+318h]
0x14004fb8f  mov     r10b, al
0x14004fb92  mov     r11d, [r15+0FCh]
0x14004fb99  xor     eax, eax
0x14004fb9b  cmp     [r15+330h], rax
0x14004fba2  mov     r9d, eax
0x14004fba5  setnz   r9b
0x14004fba9  test    edx, edx
0x14004fbab  jz      short loc_14004FBB6
0x14004fbad  mov     ecx, [r15+0F8h]
0x14004fbb4  jmp     short loc_14004FBB8
0x14004fbb6  mov     ecx, eax
0x14004fbb8  test    edx, edx
0x14004fbba  jz      short loc_14004FBCB
0x14004fbbc  mov     rax, [r15+268h]
0x14004fbc3  mov     r8d, [rax+30h]
0x14004fbc7  xor     eax, eax
0x14004fbc9  jmp     short loc_14004FBCE
0x14004fbcb  mov     r8d, eax; int
0x14004fbce  mov     edx, [r15+0F4h]; int
0x14004fbd5  mov     [rsp+2F0h+var_2A8], rax; struct IFormatNameIdEnum *
0x14004fbda  mov     [rsp+2F0h+var_2B0], rdi; struct IClipboardLevelCallback *
0x14004fbdf  mov     [rsp+2F0h+var_2B8], r10b; unsigned __int8
0x14004fbe4  mov     [rsp+2F0h+var_2C0], r9d; int
0x14004fbe9  mov     r9d, [r15+0BCh]; int
0x14004fbf0  mov     [rsp+2F0h+var_2C8], r11d; int
0x14004fbf5  mov     dword ptr [rsp+2F0h+var_2D0], ecx; int
0x14004fbf9  lea     rcx, [rsp+2F0h+var_278]; struct CFormatNamePacker **
0x14004fbfe  call    ?CreateFormatNamePacker@@YAJPEAPEAVCFormatNamePacker@@HHHHHHEPEAVIClipboardLevelCallback@@PEAVIFormatNameIdEnum@@@Z; CreateFormatNamePacker(CFormatNamePacker * *,int,int,int,int,int,int,uchar,IClipboardLevelCallback *,IFormatNameIdEnum *)
0x14004fc03  mov     edi, eax
0x14004fc05  test    eax, eax
0x14004fc07  jns     short loc_14004FC69
0x14004fc09  mov     rax, cs:WPP_GLOBAL_Control
0x14004fc10  lea     rsi, WPP_GLOBAL_Control
0x14004fc17  cmp     rax, rsi
0x14004fc1a  jz      loc_140050113
0x14004fc20  test    byte ptr [rax+1Ch], 8
0x14004fc24  jz      loc_140050113
0x14004fc2a  cmp     byte ptr [rax+19h], 2
0x14004fc2e  jb      loc_140050113
0x14004fc34  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004fc39  mov     edx, 62h ; 'b'
0x14004fc3e  lea     rcx, aCreateformatna; "CreateFormatNamePacker failed!"
0x14004fc45  mov     [rsp+2F0h+var_2C8], edi
0x14004fc49  mov     r9d, eax
0x14004fc4c  mov     [rsp+2F0h+var_2D0], rcx
0x14004fc51  mov     r8, r12
0x14004fc54  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fc5b  mov     rcx, [rcx+10h]
0x14004fc5f  call    WPP_SF_DsD
0x14004fc64  jmp     loc_140050113
0x14004fc69  mov     rcx, [rsp+2F0h+var_278]
0x14004fc6e  mov     r8d, esi
0x14004fc71  mov     rdx, rbx
0x14004fc74  mov     rax, [rcx]
0x14004fc77  mov     rax, [rax+10h]
0x14004fc7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fc80  xor     ecx, ecx
0x14004fc82  mov     edi, eax
0x14004fc84  test    eax, eax
0x14004fc86  jns     short loc_14004FCC9
0x14004fc88  mov     rax, cs:WPP_GLOBAL_Control
0x14004fc8f  lea     rsi, WPP_GLOBAL_Control
0x14004fc96  cmp     rax, rsi
0x14004fc99  jz      loc_140050113
0x14004fc9f  test    byte ptr [rax+1Ch], 8
0x14004fca3  jz      loc_140050113
0x14004fca9  cmp     byte ptr [rax+19h], 2
0x14004fcad  jb      loc_140050113
0x14004fcb3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004fcb8  mov     edx, 63h ; 'c'
0x14004fcbd  lea     rcx, aSetblobtodecod; "SetBlobToDecode failed!"
0x14004fcc4  jmp     loc_14004FC45
0x14004fcc9  mov     [rsp+2F0h+var_284], ecx
0x14004fccd  lea     rsi, WPP_GLOBAL_Control
0x14004fcd4  mov     [rsp+2F0h+var_288], ecx
0x14004fcd8  mov     dword ptr [rsp+2F0h+hMem], ecx
0x14004fcdc  mov     dword ptr [rsp+2F0h+var_280], ecx
0x14004fce0  mov     rcx, [rsp+2F0h+var_278]
0x14004fce5  lea     r8, [rbp+1F0h+szFormat]
0x14004fce9  mov     r9d, 208h
0x14004fcef  lea     rdx, [rsp+2F0h+var_2A0]
0x14004fcf4  mov     rax, [rcx]
0x14004fcf7  mov     rax, [rax+18h]
0x14004fcfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fd00  xor     ecx, ecx; this
0x14004fd02  mov     edi, eax
0x14004fd04  test    eax, eax
0x14004fd06  js      loc_1400500D7
0x14004fd0c  cmp     eax, 1
0x14004fd0f  jz      loc_14004FE9E
0x14004fd15  mov     rax, cs:WPP_GLOBAL_Control
0x14004fd1c  cmp     rax, rsi
0x14004fd1f  jz      short loc_14004FD67
0x14004fd21  test    byte ptr [rax+1Ch], 1
0x14004fd25  jz      short loc_14004FD67
0x14004fd27  cmp     byte ptr [rax+19h], 2
0x14004fd2b  jb      short loc_14004FD67
0x14004fd2d  mov     ebx, [rsp+2F0h+var_2A0]
0x14004fd31  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004fd36  lea     rcx, [rbp+1F0h+szFormat]
0x14004fd3a  mov     edx, 65h ; 'e'
0x14004fd3f  mov     qword ptr [rsp+2F0h+var_2C8], rcx
0x14004fd44  mov     r9d, eax
0x14004fd47  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fd4e  mov     r8, r12
0x14004fd51  mov     dword ptr [rsp+2F0h+var_2D0], ebx
0x14004fd55  mov     rcx, [rcx+10h]
0x14004fd59  call    WPP_SF_DdS
0x14004fd5e  mov     rax, cs:WPP_GLOBAL_Control
0x14004fd65  xor     ecx, ecx; this
0x14004fd67  cmp     [rbp+1F0h+szFormat], cx
0x14004fd6b  jz      short loc_14004FDC8
0x14004fd6d  lea     rcx, [rbp+1F0h+szFormat]; lpszFormat
0x14004fd71  call    cs:__imp_RegisterClipboardFormatW
0x14004fd77  mov     ebx, eax
0x14004fd79  test    eax, eax
0x14004fd7b  jnz     short loc_14004FDD4
0x14004fd7d  mov     rax, cs:WPP_GLOBAL_Control
0x14004fd84  cmp     rax, rsi
0x14004fd87  jz      loc_14004FCE0
0x14004fd8d  test    byte ptr [rax+1Ch], 1
0x14004fd91  jz      loc_14004FCE0
0x14004fd97  cmp     byte ptr [rax+19h], 2
0x14004fd9b  jb      loc_14004FCE0
0x14004fda1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004fda6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fdad  lea     edx, [rbx+66h]
0x14004fdb0  mov     r9d, eax
0x14004fdb3  mov     dword ptr [rsp+2F0h+var_2D0], edi
0x14004fdb7  mov     r8, r12
0x14004fdba  mov     rcx, [rcx+10h]
0x14004fdbe  call    WPP_SF_Dd
0x14004fdc3  jmp     loc_14004FCE0
0x14004fdc8  mov     ebx, [rsp+2F0h+var_2A0]
0x14004fdcc  test    ebx, ebx
0x14004fdce  jz      loc_14004FE5C
0x14004fdd4  call    ?RichTextFormat@CClipFormatTypes@@QEAAIXZ; CClipFormatTypes::RichTextFormat(void)
0x14004fdd9  cmp     ebx, eax
0x14004fddb  jnz     short loc_14004FDE9
0x14004fddd  mov     r8d, [rsp+2F0h+var_2A0]
0x14004fde2  mov     [rsp+2F0h+var_284], r8d
0x14004fde7  jmp     short loc_14004FE48
0x14004fde9  call    ?MsSourceUrl@CClipFormatTypes@@QEAAIXZ; CClipFormatTypes::MsSourceUrl(void)
0x14004fdee  cmp     ebx, eax
0x14004fdf0  jnz     short loc_14004FDFE
0x14004fdf2  mov     r8d, [rsp+2F0h+var_2A0]
0x14004fdf7  mov     dword ptr [rsp+2F0h+var_280], r8d
0x14004fdfc  jmp     short loc_14004FE48
0x14004fdfe  call    ?XmlSpreadsheet@CClipFormatTypes@@QEAAIXZ; CClipFormatTypes::XmlSpreadsheet(void)
0x14004fe03  cmp     ebx, eax
0x14004fe05  jnz     short loc_14004FE13
0x14004fe07  mov     r8d, [rsp+2F0h+var_2A0]
0x14004fe0c  mov     dword ptr [rsp+2F0h+hMem], r8d
0x14004fe11  jmp     short loc_14004FE48
0x14004fe13  call    ?HtmlFormat@CClipFormatTypes@@QEAAIXZ; CClipFormatTypes::HtmlFormat(void)
0x14004fe18  cmp     ebx, eax
0x14004fe1a  jnz     short loc_14004FE29
0x14004fe1c  mov     ebx, [rsp+2F0h+var_2A0]
0x14004fe20  mov     [rsp+2F0h+var_288], ebx
0x14004fe24  jmp     loc_14004FCE0
0x14004fe29  call    ?IncludeInHistoryId@CClipFormatTypes@@QEAAIXZ; CClipFormatTypes::IncludeInHistoryId(void)
0x14004fe2e  cmp     ebx, eax
0x14004fe30  jz      loc_14004FCE0
0x14004fe36  call    ?UploadToCloudId@CClipFormatTypes@@QEAAIXZ; CClipFormatTypes::UploadToCloudId(void)
0x14004fe3b  cmp     ebx, eax
0x14004fe3d  jz      loc_14004FCE0
0x14004fe43  mov     r8d, [rsp+2F0h+var_2A0]; unsigned int
0x14004fe48  mov     r9, [rsp+2F0h+var_298]; struct IDataObject *
0x14004fe4d  mov     edx, ebx; unsigned int
0x14004fe4f  mov     rcx, r15; this
0x14004fe52  call    ?AddFormatIdToDataObject@CClipBase@@AEAAXIIPEAUIDataObject@@@Z; CClipBase::AddFormatIdToDataObject(uint,uint,IDataObject *)
0x14004fe57  jmp     loc_14004FCE0
0x14004fe5c  cmp     rax, rsi
0x14004fe5f  jz      loc_14004FCE0
0x14004fe65  test    byte ptr [rax+1Ch], 1
0x14004fe69  jz      loc_14004FCE0
0x14004fe6f  cmp     byte ptr [rax+19h], 2
0x14004fe73  jb      loc_14004FCE0
0x14004fe79  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004fe7e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fe85  mov     edx, 67h ; 'g'
0x14004fe8a  mov     r9d, eax
0x14004fe8d  mov     r8, r12
0x14004fe90  mov     rcx, [rcx+10h]
0x14004fe94  call    WPP_SF_d
0x14004fe99  jmp     loc_14004FCE0
0x14004fe9e  mov     edi, [rsp+2F0h+var_288]
0x14004fea2  test    edi, edi
0x14004fea4  jz      short loc_14004FED8
0x14004fea6  mov     ebx, [rsp+2F0h+var_284]
0x14004feaa  test    ebx, ebx
0x14004feac  jz      short loc_14004FEBE
0x14004feae  cmp     dword ptr [rsp+2F0h+var_280], ecx
0x14004feb2  jnz     short loc_14004FEBE
0x14004feb4  test    ebx, ebx
0x14004feb6  jz      short loc_14004FEBE
0x14004feb8  cmp     dword ptr [rsp+2F0h+hMem], ecx
0x14004febc  jz      short loc_14004FED8
0x14004febe  mov     rbx, [rsp+2F0h+var_298]
0x14004fec3  call    ?HtmlFormat@CClipFormatTypes@@QEAAIXZ; CClipFormatTypes::HtmlFormat(void)
0x14004fec8  mov     r9, rbx; struct IDataObject *
  ... truncated ...
```
