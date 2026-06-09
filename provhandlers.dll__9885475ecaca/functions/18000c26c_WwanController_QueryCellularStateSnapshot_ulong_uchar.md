# WwanController::QueryCellularStateSnapshot(ulong *,uchar * *)

- ea: `0x18000c26c`
- end: `0x18000cc87`
- name: `?QueryCellularStateSnapshot@WwanController@@QEAAJPEAKPEAPEAE@Z`
- size: `2587`
- prototype: `__int64 __fastcall(WwanController *this, const unsigned __int16 *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180009240`

## callees

- `0x18000108c`
- `0x1800011bc`
- `0x180001264`
- `0x180001424`
- `0x180001518`
- `0x180009454`
- `0x180009508`
- `0x1800095bc`
- `0x180009e28`
- `0x180009f98`
- `0x18000a118`
- `0x18000a288`
- `0x18000a350`
- `0x18000a59c`
- `0x18000b004`
- `0x18000b08c`
- `0x18000b388`
- `0x18000b5c8`
- `0x18000b7f4`
- `0x18000bbdc`
- `0x18000c26c`
- `0x18000d060`
- `0x18000d72c`
- `0x18000d900`
- `0x18000e418`
- `0x18000e6b4`
- `0x18003b946`
- `0x18003b96a`
- `0x18003b9a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c2f3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c2f3`
- `msvcrt!memcpy_s` at `0x18000c6d7`
- `msvcrt!memcpy_s` at `0x18000c91f`
- `msvcrt!memcpy_s` at `0x18000c6d7`
- `msvcrt!memcpy_s` at `0x18000c91f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cadb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cadb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc0f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WwanController::QueryCellularStateSnapshot(
        WwanController *this,
        const unsigned __int16 *a2,
        unsigned __int8 **a3)
{
  unsigned __int8 **v3; // r13
  unsigned __int16 *v4; // r15
  char *v6; // r12
  void **v7; // rsi
  void **i; // rbx
  __int64 v9; // r8
  __int64 v10; // r9
  _DWORD *v11; // rax
  __int64 v12; // rsi
  unsigned int v13; // ecx
  _DWORD *v14; // rbx
  __int64 *v15; // r15
  __int64 *v16; // rbx
  __int64 *v17; // r14
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  int v26; // eax
  __int32 v27; // eax
  _OWORD *v28; // r13
  _BYTE *v29; // r15
  __int64 *v30; // rbx
  _BYTE *v31; // r14
  bool v32; // al
  bool v33; // al
  __int64 v34; // rax
  __int64 v35; // r8
  __int16 *v36; // rdx
  int v37; // ecx
  int DeviceCaps; // eax
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // rax
  __int64 v43; // r8
  __int64 v44; // rax
  __int64 v45; // r8
  unsigned int v46; // esi
  unsigned __int8 *v47; // rax
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 v50; // r9
  unsigned __int8 *v51; // rbx
  int *v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // r9
  const char *v57; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v58; // [rsp+48h] [rbp-B8h] BYREF
  const char *v59; // [rsp+50h] [rbp-B0h] BYREF
  const char *v60; // [rsp+58h] [rbp-A8h] BYREF
  const char *v61; // [rsp+60h] [rbp-A0h] BYREF
  const char *v62; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v63[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v64[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v65[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v66[16]; // [rsp+A0h] [rbp-60h] BYREF
  __m256i v67; // [rsp+B0h] [rbp-50h] BYREF
  __int128 Source; // [rsp+D0h] [rbp-30h] BYREF
  __m256i v69; // [rsp+E0h] [rbp-20h]
  __int128 v70; // [rsp+100h] [rbp+0h]
  __int128 v71; // [rsp+110h] [rbp+10h]
  __int128 v72; // [rsp+120h] [rbp+20h]
  __int128 v73; // [rsp+130h] [rbp+30h]
  __int128 v74; // [rsp+140h] [rbp+40h]
  __int128 v75; // [rsp+150h] [rbp+50h]
  __int128 v76; // [rsp+160h] [rbp+60h]
  __int128 v77; // [rsp+170h] [rbp+70h] BYREF
  _BYTE Destination[60]; // [rsp+180h] [rbp+80h] BYREF
  __int128 v79; // [rsp+1C0h] [rbp+C0h] BYREF
  __m256i v80; // [rsp+1D0h] [rbp+D0h]
  __int128 v81; // [rsp+1F0h] [rbp+F0h]
  __m256i v82; // [rsp+200h] [rbp+100h]
  _OWORD v83[7]; // [rsp+220h] [rbp+120h] BYREF
  __m256i v84; // [rsp+290h] [rbp+190h] BYREF
  __int128 v85; // [rsp+2B0h] [rbp+1B0h]
  __int128 v86; // [rsp+2C0h] [rbp+1C0h]
  __int64 v87; // [rsp+2D0h] [rbp+1D0h]
  __int16 v88; // [rsp+2D8h] [rbp+1D8h]
  __int128 v89; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v90[100]; // [rsp+2F0h] [rbp+1F0h] BYREF
  char v91[252]; // [rsp+354h] [rbp+254h] BYREF

  v3 = a3;
  v60 = (const char *)a3;
  v4 = (unsigned __int16 *)a2;
  v61 = (const char *)a2;
  *(_DWORD *)a2 = 0;
  *a3 = 0;
  WwanController::clearExecIntfList(this);
  v6 = (char *)this + 136;
  v7 = *(void ***)(*((_QWORD *)this + 17) + 8LL);
  for ( i = v7; !*((_BYTE *)i + 25); v7 = i )
  {
    std::_Tree<std::_Tmap_traits<_GUID,WwanController::WwanModemInformation,WwanController::GuidLessThan,std::allocator<std::pair<_GUID const,WwanController::WwanModemInformation>>,0>>::_Erase(
      (char *)this + 136,
      i[2]);
    i = (void **)*i;
    std::_Tree<std::_Tmap_traits<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001,long,std::less<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001>,std::allocator<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>,0>>::~_Tree<std::_Tmap_traits<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001,long,std::less<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001>,std::allocator<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>,0>>(v7 + 16);
    operator delete(v7);
  }
  *(_QWORD *)(*(_QWORD *)v6 + 8LL) = *(_QWORD *)v6;
  **(_QWORD **)v6 = *(_QWORD *)v6;
  *(_QWORD *)(*(_QWORD *)v6 + 16LL) = *(_QWORD *)v6;
  *((_QWORD *)this + 18) = 0;
  *((_DWORD *)this + 48) = 4;
  if ( (int)WwanController::GetSeqNumLastCellStateChgWnf(this) < 0 || (int)WwanController::EnumerateInterfaces(this) < 0 )
    goto LABEL_62;
  if ( (unsigned int)dword_180052170 > 5 )
  {
    v57 = "WwanController::QueryCellularStateSnapshot";
    v58 = **((_DWORD **)this + 21);
    v59 = "Retrieved a list of interfaces";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v58,
      (__int64)&unk_180048D80,
      v9,
      v10,
      (const unsigned __int16 **)&v59,
      (__int64)&v58,
      (const unsigned __int16 **)&v57);
  }
  v11 = (_DWORD *)*((_QWORD *)this + 21);
  v12 = (__int64)(v11 + 1);
  v13 = 0;
  v58 = 0;
  if ( !*v11 )
    goto LABEL_62;
  while ( 1 )
  {
    v14 = (_DWORD *)(v12 + 552);
    if ( (unsigned int)dword_180052170 > 4 )
    {
      LODWORD(v62) = *(_DWORD *)(v12 + 576);
      LODWORD(v59) = *(_DWORD *)(v12 + 572);
      LODWORD(v57) = *v14;
      v82.m256i_i64[2] = (__int64)&v62;
      v82.m256i_i64[3] = 4;
      v82.m256i_i64[0] = (__int64)&v59;
      v82.m256i_i64[1] = 4;
      *(_QWORD *)&v81 = &v57;
      *((_QWORD *)&v81 + 1) = 4;
      v80.m256i_i64[2] = v12;
      v80.m256i_i64[3] = 16;
      tlgWriteTransfer_EventWriteTransfer(&dword_180052170, &dword_180048974, 0, 0, 6, &v79);
      v13 = v58;
    }
    if ( *v14 )
      goto LABEL_60;
    *((_OWORD *)this + 11) = *(_OWORD *)v12;
    v15 = (__int64 *)*((_QWORD *)this + 19);
    v16 = (__int64 *)v15[1];
    v17 = v15;
    if ( !*((_BYTE *)v16 + 25) )
    {
      do
      {
        if ( memcmp_0(v16 + 4, (char *)this + 176, 0x10u) >= 0 )
        {
          v17 = v16;
          v16 = (__int64 *)*v16;
        }
        else
        {
          v16 = (__int64 *)v16[2];
        }
      }
      while ( !*((_BYTE *)v16 + 25) );
      v6 = (char *)this + 136;
      if ( v17 != v15 && memcmp_0((char *)this + 176, v17 + 4, 0x10u) >= 0 )
      {
        if ( (unsigned int)dword_180052170 > 5 )
        {
          v57 = "WwanController::QueryCellularStateSnapshot";
          v59 = (const char *)v12;
          v62 = "duplicate physical interface";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
            v18,
            (__int64)byte_180049003,
            v19,
            v20,
            (const unsigned __int16 **)&v62,
            (__int64 *)&v59,
            (const unsigned __int16 **)&v57);
        }
        goto LABEL_59;
      }
    }
    memset_0(&v67, 0, 0xC0u);
    if ( WwanController::GetSubscInfo(this, (struct WwanController::WwanExecutorInformation *)&v67) < 0
      || *(_DWORD *)(v12 + 572) > 1u
      && (int)WwanController::GetUiccBinds(this, (struct WwanController::WwanExecutorInformation *)&v67) < 0
      || v67.m256i_i32[0] == 1
      && (int)WwanController::GetUiccAddiInfo(this, (struct WwanController::WwanExecutorInformation *)&v67) < 0
      || (int)WwanController::verifyUICCCardLineInfoAccumulateSize(
                this,
                (struct WwanController::WwanExecutorInformation *)&v67) < 0 )
    {
      goto LABEL_61;
    }
    v79 = *(_OWORD *)v12;
    v80 = v67;
    v81 = Source;
    v82 = v69;
    v83[0] = v70;
    v83[1] = v71;
    v83[2] = v72;
    v83[3] = v73;
    v83[4] = v74;
    v83[5] = v75;
    v83[6] = v76;
    v21 = std::_Tree_buy<std::pair<_GUID const,WwanController::WwanExecutorInformation>>::_Buynode<std::pair<_GUID,WwanController::WwanExecutorInformation>>(
            (char *)this + 152,
            &v79);
    std::_Tree<std::_Tmap_traits<_GUID,WwanController::WwanExecutorInformation,WwanController::GuidLessThan,std::allocator<std::pair<_GUID const,WwanController::WwanExecutorInformation>>,0>>::_Insert_nohint<std::pair<_GUID const,WwanController::WwanExecutorInformation> &,std::_Tree_node<std::pair<_GUID const,WwanController::WwanExecutorInformation>,void *> *>(
      (char *)this + 152,
      v63,
      v22,
      v21 + 32,
      v21);
    if ( !v63[8] )
      break;
    memset_0(&v77, 0, 0x4Cu);
    DWORD2(v77) = HIDWORD(v73);
    HIDWORD(v77) = *(_DWORD *)(v12 + 576);
    if ( v67.m256i_i32[0] == 1 )
    {
      v26 = 1;
    }
    else
    {
      v26 = 0;
      if ( v67.m256i_i32[0] != 2 )
      {
        LOBYTE(v26) = v67.m256i_i32[0] != 6;
        v26 += 2;
      }
    }
    *(_DWORD *)Destination = v26;
    memcpy_s(&Destination[4], 0x2Au, (char *)&Source + 8, 0x2Au);
    v27 = v67.m256i_i32[0];
    if ( v67.m256i_i32[0] == 1 || v67.m256i_i32[0] == 6 )
    {
      *(_DWORD *)&Destination[48] = WwanController::_IsESIMProvisioningProfile((unsigned __int16 (*)[21])&Destination[4]);
      v27 = v67.m256i_i32[0];
    }
    if ( v27 == 1 )
    {
      *(_DWORD *)&Destination[52] = *(_DWORD *)(v75 + 12);
      *(_DWORD *)&Destination[56] = *(_DWORD *)(v75 + 16);
    }
    v28 = (_OWORD *)(v12 + 556);
    v29 = *(_BYTE **)v6;
    v30 = *(__int64 **)(*(_QWORD *)v6 + 8LL);
    v31 = *(_BYTE **)v6;
    if ( *((_BYTE *)v30 + 25) )
      goto LABEL_55;
    do
    {
      if ( memcmp_0(v30 + 4, (const void *)(v12 + 556), 0x10u) >= 0 )
      {
        v31 = v30;
        v30 = (__int64 *)*v30;
      }
      else
      {
        v30 = (__int64 *)v30[2];
      }
    }
    while ( !*((_BYTE *)v30 + 25) );
    if ( v31 == v29 || memcmp_0((const void *)(v12 + 556), v31 + 32, 0x10u) < 0 )
    {
LABEL_55:
      v89 = 0;
      *(_QWORD *)&v89 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_GUID const,_MVCellularSIMStateHdr>>>::_Buyheadnode();
      *(_OWORD *)&v84.m256i_u64[1] = *v28;
      HIDWORD(v87) = *(_DWORD *)(v12 + 572);
      v37 = *(_DWORD *)(v12 + 580);
      LOBYTE(v88) = v37 & 1;
      HIBYTE(v88) = (v37 & 2) != 0;
      memset_0(v90, 0, 0x158u);
      DeviceCaps = WwanController::GetDeviceCaps(this, (struct _WWAN_DEVICE_CAPS *)v90);
      *((_DWORD *)this + 14) = DeviceCaps;
      if ( DeviceCaps < 0 )
      {
        if ( (unsigned int)dword_180052170 <= 2 )
          goto LABEL_73;
        v52 = (int *)&unk_180047E08;
        goto LABEL_70;
      }
      memcpy_s(&v84.m256i_u64[3], 0x24u, v91, 0x24u);
      v79 = *((_OWORD *)this + 11);
      *(_OWORD *)v80.m256i_i8 = v77;
      *(_OWORD *)&v80.m256i_u64[2] = *(_OWORD *)Destination;
      v81 = *(_OWORD *)&Destination[16];
      *(_OWORD *)v82.m256i_i8 = *(_OWORD *)&Destination[32];
      *(_OWORD *)((char *)&v82.m256i_u64[1] + 4) = *(_OWORD *)&Destination[44];
      v42 = std::_Tree_buy<std::pair<_GUID const,_MVCellularSIMStateHdr>>::_Buynode<std::pair<_GUID,_MVCellularSIMStateHdr>>(
              &v89,
              &v79);
      std::_Tree<std::_Tmap_traits<_GUID,_MVCellularSIMStateHdr,WwanController::GuidLessThan,std::allocator<std::pair<_GUID const,_MVCellularSIMStateHdr>>,0>>::_Insert_nohint<std::pair<_GUID const,_MVCellularSIMStateHdr> &,std::_Tree_node<std::pair<_GUID const,_MVCellularSIMStateHdr>,void *> *>(
        &v89,
        v65,
        v43,
        v42 + 28,
        v42);
      if ( !v65[8] )
      {
        *((_DWORD *)this + 14) = -2147024882;
        if ( (unsigned int)dword_180052170 <= 2 )
          goto LABEL_73;
        v52 = (int *)&byte_1800482FF;
LABEL_70:
        LODWORD(v57) = *((_DWORD *)this + 14);
        v59 = "WwanController::QueryCellularStateSnapshot";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v39,
          (__int64)v52,
          v40,
          v41,
          (const unsigned __int16 **)&v59,
          (__int64)&v57);
        goto LABEL_73;
      }
      v79 = *v28;
      v80 = v84;
      v81 = v85;
      *(_OWORD *)v82.m256i_i8 = v86;
      v82.m256i_i64[2] = v87;
      v82.m256i_i16[12] = v88;
      std::_Tree<std::_Tmap_traits<_GUID,_MVCellularSIMStateHdr,WwanController::GuidLessThan,std::allocator<std::pair<_GUID const,_MVCellularSIMStateHdr>>,0>>::_Tree<std::_Tmap_traits<_GUID,_MVCellularSIMStateHdr,WwanController::GuidLessThan,std::allocator<std::pair<_GUID const,_MVCellularSIMStateHdr>>,0>>(
        v83,
        &v89);
      v44 = std::_Tree_buy<std::pair<_GUID const,WwanController::WwanModemInformation>>::_Buynode<std::pair<_GUID,WwanController::WwanModemInformation>>(
              v6,
              &v79);
      std::_Tree<std::_Tmap_traits<_GUID,WwanController::WwanModemInformation,WwanController::GuidLessThan,std::allocator<std::pair<_GUID const,WwanController::WwanModemInformation>>,0>>::_Insert_nohint<std::pair<_GUID const,WwanController::WwanModemInformation> &,std::_Tree_node<std::pair<_GUID const,WwanController::WwanModemInformation>,void *> *>(
        v6,
        v66,
        v45,
        v44 + 32,
        v44);
      std::_Tree<std::_Tmap_traits<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001,long,std::less<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001>,std::allocator<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>,0>>::~_Tree<std::_Tmap_traits<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001,long,std::less<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001>,std::allocator<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>,0>>((void **)v83);
      if ( !v66[8] )
      {
        *((_DWORD *)this + 14) = -2147024882;
        if ( (unsigned int)dword_180052170 > 2 )
        {
          v52 = &dword_1800491BC;
          goto LABEL_70;
        }
LABEL_73:
        std::_Tree<std::_Tmap_traits<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001,long,std::less<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001>,std::allocator<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>,0>>::~_Tree<std::_Tmap_traits<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001,long,std::less<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001>,std::allocator<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>,0>>((void **)&v89);
        goto LABEL_74;
      }
      std::_Tree<std::_Tmap_traits<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001,long,std::less<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001>,std::allocator<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>,0>>::~_Tree<std::_Tmap_traits<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001,long,std::less<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001>,std::allocator<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>,0>>((void **)&v89);
    }
    else
    {
      v32 = v31[120] || (*(_BYTE *)(v12 + 580) & 1) != 0;
      v31[120] = v32;
      v33 = v31[121] || (*(_BYTE *)(v12 + 580) & 2) != 0;
      v31[121] = v33;
      v79 = *((_OWORD *)this + 11);
      *(_OWORD *)v80.m256i_i8 = v77;
      *(_OWORD *)&v80.m256i_u64[2] = *(_OWORD *)Destination;
      v81 = *(_OWORD *)&Destination[16];
      *(_OWORD *)v82.m256i_i8 = *(_OWORD *)&Destination[32];
      *(_OWORD *)((char *)&v82.m256i_u64[1] + 4) = *(_OWORD *)&Destination[44];
      v34 = std::_Tree_buy<std::pair<_GUID const,_MVCellularSIMStateHdr>>::_Buynode<std::pair<_GUID,_MVCellularSIMStateHdr>>(
              v31 + 128,
              &v79);
      std::_Tree<std::_Tmap_traits<_GUID,_MVCellularSIMStateHdr,WwanController::GuidLessThan,std::allocator<std::pair<_GUID const,_MVCellularSIMStateHdr>>,0>>::_Insert_nohint<std::pair<_GUID const,_MVCellularSIMStateHdr> &,std::_Tree_node<std::pair<_GUID const,_MVCellularSIMStateHdr>,void *> *>(
        v31 + 128,
        v64,
        v35,
        v34 + 28,
        v34);
      if ( !v64[8] )
      {
        *((_DWORD *)this + 14) = -2147024882;
        if ( (unsigned int)dword_180052170 > 2 )
        {
          v36 = &word_180049186;
          goto LABEL_54;
        }
LABEL_61:
        v3 = (unsigned __int8 **)v60;
        v4 = (unsigned __int16 *)v61;
        goto LABEL_62;
      }
    }
LABEL_59:
    v13 = v58;
LABEL_60:
    v58 = ++v13;
    v12 += 588;
    if ( v13 >= **((_DWORD **)this + 21) )
      goto LABEL_61;
  }
  *((_DWORD *)this + 14) = -2147024882;
  if ( (unsigned int)dword_180052170 <= 2 )
    goto LABEL_61;
  v36 = (__int16 *)byte_18004908D;
LABEL_54:
  LODWORD(v57) = *((_DWORD *)this + 14);
  v59 = "WwanController::QueryCellularStateSnapshot";
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
    v23,
    (__int64)v36,
    v24,
    v25,
    (const unsigned __int16 **)&v59,
    (__int64)&v57);
LABEL_74:
  v4 = (unsigned __int16 *)v61;
  v3 = (unsigned __int8 **)v60;
LABEL_62:
  if ( *((int *)this + 14) >= 0 )
  {
    *((_DWORD *)this + 48) += (unsigned int)(72 * *((_DWORD *)this + 36) + 3) >> 2;
    v46 = 4 * *((_DWORD *)this + 48);
    v47 = (unsigned __int8 *)CoTaskMemAlloc(v46);
    v51 = v47;
    if ( v47 )
    {
      memset_0(v47, 0, v46);
      if ( (int)WwanController::BuildCellularStateSnapshot(this, v46, (char *)v51) >= 0 )
      {
        *(_DWORD *)v4 = v46;
        *v3 = v51;
        if ( (unsigned int)dword_180052170 > 5 )
        {
          v60 = "WwanController::QueryCellularStateSnapshot";
          v61 = "Cellular State Snapshot returned";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v53,
            (__int64)byte_1800490C3,
            v54,
            v55,
            (const unsigned __int16 **)&v61,
            (const unsigned __int16 **)&v60);
        }
      }
      else
      {
        CoTaskMemFree(v51);
      }
    }
    else
    {
      *((_DWORD *)this + 14) = -2147024882;
      if ( (unsigned int)dword_180052170 > 2 )
      {
        LODWORD(v57) = *((_DWORD *)this + 14);
        v60 = "WwanController::QueryCellularStateSnapshot";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v48,
          (__int64)&unk_180047FA8,
          v49,
          v50,
          (const unsigned __int16 **)&v60,
          (__int64)&v57);
      }
    }
  }
  return *((unsigned int *)this + 14);
}

```

## disassembly

```asm
0x18000c26c  mov     [rsp-8+arg_18], rbx
0x18000c271  push    rbp
0x18000c272  push    rsi
0x18000c273  push    rdi
0x18000c274  push    r12
0x18000c276  push    r13
0x18000c278  push    r14
0x18000c27a  push    r15
0x18000c27c  lea     rbp, [rsp-360h]
0x18000c284  sub     rsp, 460h
0x18000c28b  mov     rax, cs:__security_cookie
0x18000c292  xor     rax, rsp
0x18000c295  mov     [rbp+390h+var_40], rax
0x18000c29c  mov     r13, r8
0x18000c29f  mov     [rsp+490h+var_438], r8
0x18000c2a4  mov     r15, rdx
0x18000c2a7  mov     [rsp+490h+var_430], rdx
0x18000c2ac  mov     rdi, rcx
0x18000c2af  xor     r14d, r14d
0x18000c2b2  mov     [rdx], r14d
0x18000c2b5  mov     [r8], r14
0x18000c2b8  call    ?clearExecIntfList@WwanController@@AEAAXXZ; WwanController::clearExecIntfList(void)
0x18000c2bd  lea     r12, [rdi+88h]
0x18000c2c4  mov     rax, [r12]
0x18000c2c8  mov     rsi, [rax+8]
0x18000c2cc  mov     rbx, rsi
0x18000c2cf  cmp     [rsi+19h], r14b
0x18000c2d3  jnz     short loc_18000C302
0x18000c2d5  mov     rdx, [rbx+10h]
0x18000c2d9  mov     rcx, r12
0x18000c2dc  call    ?_Erase@?$_Tree@V?$_Tmap_traits@U_GUID@@UWwanModemInformation@WwanController@@UGuidLessThan@3@V?$allocator@U?$pair@$$CBU_GUID@@UWwanModemInformation@WwanController@@@std@@@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UWwanModemInformation@WwanController@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<_GUID,WwanController::WwanModemInformation,WwanController::GuidLessThan,std::allocator<std::pair<_GUID const,WwanController::WwanModemInformation>>,0>>::_Erase(std::_Tree_node<std::pair<_GUID const,WwanController::WwanModemInformation>,void *> *)
0x18000c2e1  mov     rbx, [rbx]
0x18000c2e4  lea     rcx, [rsi+80h]
0x18000c2eb  call    ??1?$_Tree@V?$_Tmap_traits@W4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@JU?$less@W4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@@std@@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<__MIDL___MIDL_itf_mvengine_0000_0000_0001,long,std::less<__MIDL___MIDL_itf_mvengine_0000_0000_0001>,std::allocator<std::pair<__MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>,0>>::~_Tree<std::_Tmap_traits<__MIDL___MIDL_itf_mvengine_0000_0000_0001,long,std::less<__MIDL___MIDL_itf_mvengine_0000_0000_0001>,std::allocator<std::pair<__MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>,0>>(void)
0x18000c2f0  mov     rcx, rsi
0x18000c2f3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c2f9  mov     rsi, rbx
0x18000c2fc  cmp     [rbx+19h], r14b
0x18000c300  jz      short loc_18000C2D5
0x18000c302  mov     rax, [r12]
0x18000c306  mov     [rax+8], rax
0x18000c30a  mov     rax, [r12]
0x18000c30e  mov     [rax], rax
0x18000c311  mov     rax, [r12]
0x18000c315  mov     [rax+10h], rax
0x18000c319  mov     [r12+8], r14
0x18000c31e  mov     dword ptr [rdi+0C0h], 4
0x18000c328  mov     rcx, rdi; this
0x18000c32b  call    ?GetSeqNumLastCellStateChgWnf@WwanController@@AEAAJXZ; WwanController::GetSeqNumLastCellStateChgWnf(void)
0x18000c330  lea     rbx, aWwancontroller_6; "WwanController::QueryCellularStateSnaps"...
0x18000c337  test    eax, eax
0x18000c339  js      loc_18000CA9F
0x18000c33f  mov     rcx, rdi; this
0x18000c342  call    ?EnumerateInterfaces@WwanController@@AEAAJXZ; WwanController::EnumerateInterfaces(void)
0x18000c347  test    eax, eax
0x18000c349  js      loc_18000CA9F
0x18000c34f  mov     eax, cs:dword_180052170
0x18000c355  cmp     eax, 5
0x18000c358  jbe     short loc_18000C3A2
0x18000c35a  mov     [rsp+490h+var_450], rbx
0x18000c35f  mov     rax, [rdi+0A8h]
0x18000c366  mov     ecx, [rax]
0x18000c368  mov     [rsp+490h+var_448], ecx
0x18000c36c  lea     rax, aRetrievedAList; "Retrieved a list of interfaces"
0x18000c373  mov     [rsp+490h+var_440], rax
0x18000c378  lea     rax, [rsp+490h+var_450]
0x18000c37d  mov     [rsp+490h+var_460], rax
0x18000c382  lea     rax, [rsp+490h+var_448]
0x18000c387  mov     [rsp+490h+var_468], rax
0x18000c38c  lea     rax, [rsp+490h+var_440]
0x18000c391  mov     [rsp+490h+var_470], rax
0x18000c396  lea     rdx, unk_180048D80
0x18000c39d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000c3a2  mov     rax, [rdi+0A8h]
0x18000c3a9  lea     rsi, [rax+4]
0x18000c3ad  mov     ecx, r14d
0x18000c3b0  mov     [rsp+490h+var_448], ecx
0x18000c3b4  cmp     [rax], r14d
0x18000c3b7  jbe     loc_18000CA9F
0x18000c3bd  mov     eax, cs:dword_180052170
0x18000c3c3  lea     rbx, [rsi+228h]
0x18000c3ca  mov     edx, 4
0x18000c3cf  cmp     eax, edx
0x18000c3d1  jbe     loc_18000C46D
0x18000c3d7  mov     eax, [rsi+240h]
0x18000c3dd  mov     dword ptr [rsp+490h+var_428], eax
0x18000c3e1  mov     eax, [rsi+23Ch]
0x18000c3e7  mov     dword ptr [rsp+490h+var_440], eax
0x18000c3eb  mov     eax, [rbx]
0x18000c3ed  mov     dword ptr [rsp+490h+var_450], eax
0x18000c3f1  lea     rax, [rsp+490h+var_428]
0x18000c3f6  mov     qword ptr [rbp+390h+var_280], rax
0x18000c3fd  mov     qword ptr [rbp+390h+var_280+8], rdx
0x18000c404  lea     rax, [rsp+490h+var_440]
0x18000c409  mov     qword ptr [rbp+390h+var_290], rax
0x18000c410  mov     qword ptr [rbp+390h+var_290+8], rdx
0x18000c417  lea     rax, [rsp+490h+var_450]
0x18000c41c  mov     qword ptr [rbp+390h+var_2A0], rax
0x18000c423  mov     qword ptr [rbp+390h+var_2A0+8], rdx
0x18000c42a  mov     qword ptr [rbp+390h+var_2B0], rsi
0x18000c431  mov     qword ptr [rbp+390h+var_2B0+8], 10h
0x18000c43c  lea     rax, [rbp+390h+var_2D0]
0x18000c443  mov     [rsp+490h+var_468], rax
0x18000c448  mov     dword ptr [rsp+490h+var_470], 6
0x18000c450  xor     r9d, r9d
0x18000c453  xor     r8d, r8d
0x18000c456  lea     rdx, dword_180048974
0x18000c45d  lea     rcx, dword_180052170
0x18000c464  call    _tlgWriteTransfer_EventWriteTransfer
0x18000c469  mov     ecx, [rsp+490h+var_448]
0x18000c46d  cmp     [rbx], r14d
0x18000c470  jnz     loc_18000CA79
0x18000c476  movups  xmm0, xmmword ptr [rsi]
0x18000c479  movdqu  xmmword ptr [rdi+0B0h], xmm0
0x18000c481  lea     r13, [rdi+98h]
0x18000c488  mov     r15, [r13+0]
0x18000c48c  mov     rbx, [r15+8]
0x18000c490  mov     r14, r15
0x18000c493  cmp     byte ptr [rbx+19h], 0
0x18000c497  jnz     loc_18000C54D
0x18000c49d  lea     rcx, [rbx+20h]; Buf1
0x18000c4a1  mov     r8d, 10h; Size
0x18000c4a7  lea     rdx, [rdi+0B0h]; Buf2
0x18000c4ae  call    memcmp_0
0x18000c4b3  test    eax, eax
0x18000c4b5  jns     short loc_18000C4BD
0x18000c4b7  mov     rbx, [rbx+10h]
0x18000c4bb  jmp     short loc_18000C4C3
0x18000c4bd  mov     r14, rbx
0x18000c4c0  mov     rbx, [rbx]
0x18000c4c3  cmp     byte ptr [rbx+19h], 0
0x18000c4c7  jz      short loc_18000C49D
0x18000c4c9  lea     r12, [rdi+88h]
0x18000c4d0  cmp     r14, r15
0x18000c4d3  jz      short loc_18000C54D
0x18000c4d5  lea     rdx, [r14+20h]; Buf2
0x18000c4d9  mov     r8d, 10h; Size
0x18000c4df  lea     rcx, [rdi+0B0h]; Buf1
0x18000c4e6  call    memcmp_0
0x18000c4eb  xor     r14d, r14d
0x18000c4ee  test    eax, eax
0x18000c4f0  js      short loc_18000C550
0x18000c4f2  mov     eax, cs:dword_180052170
0x18000c4f8  cmp     eax, 5
0x18000c4fb  jbe     loc_18000CA75
0x18000c501  lea     rax, aWwancontroller_6; "WwanController::QueryCellularStateSnaps"...
0x18000c508  mov     [rsp+490h+var_450], rax
0x18000c50d  mov     [rsp+490h+var_440], rsi
0x18000c512  lea     rax, aDuplicatePhysi; "duplicate physical interface"
0x18000c519  mov     [rsp+490h+var_428], rax
0x18000c51e  lea     rax, [rsp+490h+var_450]
0x18000c523  mov     [rsp+490h+var_460], rax
0x18000c528  lea     rax, [rsp+490h+var_440]
0x18000c52d  mov     [rsp+490h+var_468], rax
0x18000c532  lea     rax, [rsp+490h+var_428]
0x18000c537  mov     [rsp+490h+var_470], rax
0x18000c53c  lea     rdx, byte_180049003
0x18000c543  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x18000c548  jmp     loc_18000CA75
0x18000c54d  xor     r14d, r14d
0x18000c550  xor     edx, edx; Val
0x18000c552  mov     r8d, 0C0h; Size
0x18000c558  lea     rcx, [rbp+390h+var_3E0]; void *
0x18000c55c  call    memset_0
0x18000c561  lea     rdx, [rbp+390h+var_3E0]; struct WwanController::WwanExecutorInformation *
0x18000c565  mov     rcx, rdi; this
0x18000c568  call    ?GetSubscInfo@WwanController@@AEAAJAEAUWwanExecutorInformation@1@@Z; WwanController::GetSubscInfo(WwanController::WwanExecutorInformation &)
0x18000c56d  test    eax, eax
0x18000c56f  js      loc_18000CA95
0x18000c575  mov     ebx, 1
0x18000c57a  cmp     [rsi+23Ch], ebx
0x18000c580  jbe     short loc_18000C596
0x18000c582  lea     rdx, [rbp+390h+var_3E0]; struct WwanController::WwanExecutorInformation *
0x18000c586  mov     rcx, rdi; this
0x18000c589  call    ?GetUiccBinds@WwanController@@AEAAJAEAUWwanExecutorInformation@1@@Z; WwanController::GetUiccBinds(WwanController::WwanExecutorInformation &)
0x18000c58e  test    eax, eax
0x18000c590  js      loc_18000CA95
0x18000c596  cmp     dword ptr [rbp+390h+var_3E0], ebx
0x18000c599  jnz     short loc_18000C5AF
0x18000c59b  lea     rdx, [rbp+390h+var_3E0]; struct WwanController::WwanExecutorInformation *
0x18000c59f  mov     rcx, rdi; this
0x18000c5a2  call    ?GetUiccAddiInfo@WwanController@@AEAAJAEAUWwanExecutorInformation@1@@Z; WwanController::GetUiccAddiInfo(WwanController::WwanExecutorInformation &)
0x18000c5a7  test    eax, eax
0x18000c5a9  js      loc_18000CA95
0x18000c5af  lea     rdx, [rbp+390h+var_3E0]; struct WwanController::WwanExecutorInformation *
0x18000c5b3  mov     rcx, rdi; this
0x18000c5b6  call    ?verifyUICCCardLineInfoAccumulateSize@WwanController@@AEAAJAEAUWwanExecutorInformation@1@@Z; WwanController::verifyUICCCardLineInfoAccumulateSize(WwanController::WwanExecutorInformation &)
0x18000c5bb  test    eax, eax
0x18000c5bd  js      loc_18000CA95
0x18000c5c3  movups  xmm0, xmmword ptr [rsi]
0x18000c5c6  movdqu  [rbp+390h+var_2D0], xmm0
0x18000c5ce  movaps  xmm1, [rbp+390h+var_3E0]
0x18000c5d2  movups  [rbp+390h+var_2C0], xmm1
0x18000c5d9  movaps  xmm0, [rbp+390h+var_3D0]
0x18000c5dd  movups  [rbp+390h+var_2B0], xmm0
0x18000c5e4  movaps  xmm1, [rbp+390h+Source]
0x18000c5e8  movups  [rbp+390h+var_2A0], xmm1
0x18000c5ef  movaps  xmm0, [rbp+390h+var_3B0]
0x18000c5f3  movups  [rbp+390h+var_290], xmm0
0x18000c5fa  movaps  xmm1, [rbp+390h+var_3A0]
0x18000c5fe  movups  [rbp+390h+var_280], xmm1
0x18000c605  movaps  xmm0, [rbp+390h+var_390]
0x18000c609  movups  [rbp+390h+var_270], xmm0
0x18000c610  movaps  xmm1, [rbp+390h+var_380]
0x18000c614  movups  [rbp+390h+var_260], xmm1
0x18000c61b  movaps  xmm0, [rbp+390h+var_370]
0x18000c61f  movups  [rbp+390h+var_250], xmm0
0x18000c626  movaps  xmm1, [rbp+390h+var_360]
0x18000c62a  movups  [rbp+390h+var_240], xmm1
0x18000c631  movaps  xmm0, [rbp+390h+var_350]
0x18000c635  movups  [rbp+390h+var_230], xmm0
0x18000c63c  movaps  xmm1, [rbp+390h+var_340]
0x18000c640  movups  [rbp+390h+var_220], xmm1
0x18000c647  movaps  xmm0, [rbp+390h+var_330]
0x18000c64b  movups  [rbp+390h+var_210], xmm0
0x18000c652  lea     rdx, [rbp+390h+var_2D0]
0x18000c659  mov     rcx, r13
0x18000c65c  call    ??$_Buynode@U?$pair@U_GUID@@UWwanExecutorInformation@WwanController@@@std@@@?$_Tree_buy@U?$pair@$$CBU_GUID@@UWwanExecutorInformation@WwanController@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UWwanExecutorInformation@WwanController@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UWwanExecutorInformation@WwanController@@@std@@PEAX@1@$$QEAU?$pair@U_GUID@@UWwanExecutorInformation@WwanController@@@1@@Z; std::_Tree_buy<std::pair<_GUID const,WwanController::WwanExecutorInformation>>::_Buynode<std::pair<_GUID,WwanController::WwanExecutorInformation>>(std::pair<_GUID,WwanController::WwanExecutorInformation> &&)
0x18000c661  lea     r9, [rax+20h]
0x18000c665  mov     [rsp+490h+var_470], rax
0x18000c66a  lea     rdx, [rsp+490h+var_420]
0x18000c66f  mov     rcx, r13
0x18000c672  call    ??$_Insert_nohint@AEAU?$pair@$$CBU_GUID@@UWwanExecutorInformation@WwanController@@@std@@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UWwanExecutorInformation@WwanController@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@U_GUID@@UWwanExecutorInformation@WwanController@@UGuidLessThan@3@V?$allocator@U?$pair@$$CBU_GUID@@UWwanExecutorInformation@WwanController@@@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UWwanExecutorInformation@WwanController@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBU_GUID@@UWwanExecutorInformation@WwanController@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UWwanExecutorInformation@WwanController@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<_GUID,WwanController::WwanExecutorInformation,WwanController::GuidLessThan,std::allocator<std::pair<_GUID const,WwanController::WwanExecutorInformation>>,0>>::_Insert_nohint<std::pair<_GUID const,WwanController::WwanExecutorInformation> &,std::_Tree_node<std::pair<_GUID const,WwanController::WwanExecutorInformation>,void *> *>(bool,std::pair<_GUID const,WwanController::WwanExecutorInformation> &,std::_Tree_node<std::pair<_GUID const,WwanController::WwanExecutorInformation>,void *> *)
0x18000c677  cmp     [rsp+490h+var_418], r14b
0x18000c67c  jz      loc_18000CBCC
0x18000c682  xor     edx, edx; Val
0x18000c684  lea     r8d, [rdx+4Ch]; Size
0x18000c688  lea     rcx, [rbp+390h+var_320]; void *
0x18000c68c  call    memset_0
0x18000c691  mov     eax, dword ptr [rbp+390h+var_360+0Ch]
0x18000c694  mov     dword ptr [rbp+390h+var_320+8], eax
0x18000c697  mov     eax, [rsi+240h]
0x18000c69d  mov     dword ptr [rbp+390h+var_320+0Ch], eax
0x18000c6a0  mov     ecx, dword ptr [rbp+390h+var_3E0]
0x18000c6a3  cmp     ecx, ebx
0x18000c6a5  jnz     short loc_18000C6AB
0x18000c6a7  mov     eax, ebx
0x18000c6a9  jmp     short loc_18000C6BC
0x18000c6ab  mov     eax, r14d
0x18000c6ae  cmp     ecx, 2
0x18000c6b1  jz      short loc_18000C6BC
0x18000c6b3  cmp     ecx, 6
0x18000c6b6  setnz   al
0x18000c6b9  add     eax, 2
0x18000c6bc  mov     dword ptr [rbp+390h+Destination], eax
0x18000c6c2  mov     eax, 2Ah ; '*'
0x18000c6c7  mov     r9d, eax; SourceSize
0x18000c6ca  lea     r8, [rbp+390h+Source+8]; Source
0x18000c6ce  mov     edx, eax; DestinationSize
0x18000c6d0  lea     rcx, [rbp+390h+Destination+4]; Destination
0x18000c6d7  call    cs:__imp_memcpy_s
0x18000c6dd  mov     eax, dword ptr [rbp+390h+var_3E0]
0x18000c6e0  cmp     eax, ebx
0x18000c6e2  jz      short loc_18000C6E9
0x18000c6e4  cmp     eax, 6
0x18000c6e7  jnz     short loc_18000C6FE
0x18000c6e9  lea     rcx, [rbp+390h+Destination+4]; Src
0x18000c6f0  call    ?_IsESIMProvisioningProfile@WwanController@@CAKAEAY0BF@$$CBG@Z; WwanController::_IsESIMProvisioningProfile(ushort const (&)[21])
0x18000c6f5  mov     [rbp+390h+var_2E0], eax
0x18000c6fb  mov     eax, dword ptr [rbp+390h+var_3E0]
0x18000c6fe  cmp     eax, ebx
0x18000c700  jnz     short loc_18000C718
0x18000c702  mov     rcx, qword ptr [rbp+390h+var_340]
0x18000c706  mov     eax, [rcx+0Ch]
0x18000c709  mov     [rbp+390h+var_2DC], eax
0x18000c70f  mov     eax, [rcx+10h]
0x18000c712  mov     [rbp+390h+var_2D8], eax
0x18000c718  lea     r13, [rsi+22Ch]
0x18000c71f  mov     r15, [r12]
0x18000c723  mov     rbx, [r15+8]
0x18000c727  mov     r14, r15
0x18000c72a  cmp     byte ptr [rbx+19h], 0
0x18000c72e  jnz     loc_18000C88B
0x18000c734  lea     rcx, [rbx+20h]; Buf1
0x18000c738  mov     r8d, 10h; Size
0x18000c73e  mov     rdx, r13; Buf2
0x18000c741  call    memcmp_0
0x18000c746  test    eax, eax
0x18000c748  jns     short loc_18000C750
0x18000c74a  mov     rbx, [rbx+10h]
0x18000c74e  jmp     short loc_18000C756
0x18000c750  mov     r14, rbx
0x18000c753  mov     rbx, [rbx]
0x18000c756  cmp     byte ptr [rbx+19h], 0
0x18000c75a  jz      short loc_18000C734
0x18000c75c  cmp     r14, r15
0x18000c75f  jz      loc_18000C88B
0x18000c765  lea     rdx, [r14+20h]; Buf2
0x18000c769  mov     r8d, 10h; Size
0x18000c76f  mov     rcx, r13; Buf1
0x18000c772  call    memcmp_0
0x18000c777  test    eax, eax
0x18000c779  js      loc_18000C88B
0x18000c77f  cmp     byte ptr [r14+78h], 0
0x18000c784  jnz     short loc_18000C793
0x18000c786  test    byte ptr [rsi+244h], 1
0x18000c78d  jnz     short loc_18000C793
0x18000c78f  xor     al, al
0x18000c791  jmp     short loc_18000C795
0x18000c793  mov     al, 1
  ... truncated ...
```
