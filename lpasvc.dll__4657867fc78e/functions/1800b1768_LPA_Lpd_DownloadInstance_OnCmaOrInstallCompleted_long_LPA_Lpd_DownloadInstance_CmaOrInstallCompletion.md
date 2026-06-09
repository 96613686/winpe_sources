# LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted(long,LPA::Lpd::DownloadInstance::CmaOrInstallCompletion)

- ea: `0x1800b1768`
- end: `0x1800b2460`
- name: `?OnCmaOrInstallCompleted@DownloadInstance@Lpd@LPA@@AEAAXJW4CmaOrInstallCompletion@123@@Z`
- size: `3320`
- prototype: ``
- caller_count: `20`
- callee_count: `24`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800b2530`
- `0x1800b2d30`
- `0x1800b3110`
- `0x1800b3330`
- `0x1800b3600`
- `0x1800b39b0`
- `0x1800b4220`
- `0x1800b4460`
- `0x1800b47c0`
- `0x1800b4930`
- `0x1800b4bf8`
- `0x1800b512c`
- `0x1800b5454`
- `0x1800b5534`
- `0x1800b57d4`
- `0x1800b6738`
- `0x1800b7e04`
- `0x1800bdd40`
- `0x1800bdd70`
- `0x1800bddb0`

## callees

- `0x180001f1c`
- `0x180005d6c`
- `0x180005ea0`
- `0x1800060b8`
- `0x180006828`
- `0x180006970`
- `0x18000df90`
- `0x18005cd20`
- `0x18006d990`
- `0x18006da14`
- `0x1800709e4`
- `0x180071320`
- `0x180071344`
- `0x180071610`
- `0x180071940`
- `0x180071994`
- `0x180076070`
- `0x18008222c`
- `0x1800b0e38`
- `0x1800b1768`
- `0x1800b2468`
- `0x1800d9864`
- `0x1800d9a14`
- `0x180101010`

## string_xrefs

- `0x1800b1869`: `LpaServiceLpd`
- `0x1800b1a74`: `LpaServiceLpd`
- `0x1800b1c54`: `LpaServiceLpd`
- `0x1800b1f8d`: `LpaServiceLpd`
- `0x1800b2358`: `LpaServiceLpd`
- `0x1800b1862`: `LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted`
- `0x1800b1a69`: `LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted`
- `0x1800b1c49`: `LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted`
- `0x1800b1f82`: `LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted`
- `0x1800b234d`: `LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted(__int64 a1, int a2, unsigned int a3)
{
  unsigned int v3; // esi
  int v4; // edi
  int v6; // r12d
  char v7; // r13
  char v8; // r15
  _BYTE *v9; // rdx
  char v10; // r8
  const unsigned __int16 *v11; // rax
  void (*v12)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *); // r9
  unsigned int v13; // r11d
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // r9
  __int64 v16; // rcx
  unsigned __int16 *v17; // rdi
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  unsigned __int8 v24; // bl
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  __int16 v28; // r8
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  _QWORD **v32; // rbx
  _QWORD *i; // rdi
  unsigned int v34; // r9d
  int v35; // r8d
  int v36; // r9d
  int v37; // ecx
  const char *v38; // rax
  __int16 *v39; // rdx
  _QWORD **v40; // rbx
  _QWORD *j; // rdi
  int v42; // esi
  __int64 v43; // rsi
  __int64 v44; // rbx
  __int64 *v45; // rdx
  __int64 v46; // rcx
  const char *v47; // rbx
  const char *v48; // rdi
  const char *v49; // rax
  int v50; // r13d
  _QWORD **v51; // rbx
  _QWORD *k; // rdi
  int v53; // r8d
  int v54; // r9d
  __int64 v55; // rax
  void (__fastcall *v56)(_QWORD, _QWORD, __int64, __int64, _QWORD, __int64, __int64); // r10
  __int64 v57; // r9
  __int16 *v58; // rdx
  const char *v59; // rax
  bool v60[8]; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v61; // [rsp+80h] [rbp-80h]
  char v62; // [rsp+81h] [rbp-7Fh]
  int v63; // [rsp+84h] [rbp-7Ch] BYREF
  char v64; // [rsp+88h] [rbp-78h]
  unsigned __int64 v65; // [rsp+90h] [rbp-70h] BYREF
  const char *v66; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v67; // [rsp+A0h] [rbp-60h] BYREF
  char v68[4]; // [rsp+A4h] [rbp-5Ch] BYREF
  int v69; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v70; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v71; // [rsp+B8h] [rbp-48h] BYREF
  const char *v72; // [rsp+C0h] [rbp-40h] BYREF
  int v73; // [rsp+C8h] [rbp-38h]
  int v74; // [rsp+CCh] [rbp-34h]
  const char *v75; // [rsp+D0h] [rbp-30h] BYREF
  const char *v76; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v77[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v78; // [rsp+E8h] [rbp-18h] BYREF
  std::_Ref_count_base *v79; // [rsp+F0h] [rbp-10h]
  _BYTE v81[18]; // [rsp+108h] [rbp+8h] BYREF
  __int128 v82; // [rsp+11Ah] [rbp+1Ah]
  __int64 v83; // [rsp+12Ah] [rbp+2Ah]
  unsigned __int16 v85[17]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v86; // [rsp+15Ah] [rbp+5Ah]

  v3 = a3;
  v67 = a3;
  v4 = a2;
  v73 = a2;
  v74 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 1;
  v9 = (_BYTE *)(a1 + 877);
  if ( *(_DWORD *)(a1 + 880) == 2 )
  {
    v10 = 1;
    v61 = 1;
    if ( *v9 )
    {
      v62 = 1;
      goto LABEL_6;
    }
  }
  else
  {
    v10 = 0;
    v61 = 0;
  }
  v62 = 0;
LABEL_6:
  v64 = 0;
  memset(v81, 0, sizeof(v81));
  v82 = 0;
  v83 = 0;
  *(_BYTE *)(a1 + 874) = 0;
  if ( v3 )
  {
    if ( v3 == 1 )
    {
      v62 = 0;
      *(_BYTE *)(a1 + 873) = 1;
      goto LABEL_15;
    }
    if ( v3 - 2 > 1 )
      goto LABEL_15;
    v6 = v4;
    v64 = 1;
    if ( !v10 || !*v9 )
      v7 = 1;
  }
  else
  {
    v74 = v4;
    v7 = v10 ^ 1;
  }
  *(_BYTE *)(a1 + 873) = 0;
LABEL_15:
  v11 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 464);
  StringCchCopyW((unsigned __int16 *)v81, 0x15u, v11);
  v12 = (void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *))"Failed";
  if ( v3 > 1 )
  {
LABEL_57:
    v24 = v61;
    goto LABEL_58;
  }
  if ( v4 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v63 = 0;
      LODWORD(v76) = ((v4 >> 31) & 2) + 15;
      *(_QWORD *)v77 = "Failed";
      LODWORD(v75) = *(_DWORD *)(a1 + 912);
      v69 = 2;
      v65 = (unsigned __int64)"LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted";
      v66 = "LpaServiceLpd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)"Succeeded",
        (unsigned int)&byte_180131607,
        (unsigned int)"LpaServiceLpd",
        (unsigned int)"Failed",
        (__int64)&v66,
        (__int64)&v65,
        (__int64)&v69,
        (__int64)&v75,
        (__int64)v77,
        (__int64)&v76,
        (__int64)&v63);
    }
  }
  else if ( (unsigned int)CallbackContext > 4 )
  {
    v69 = 0;
    LODWORD(v75) = 15;
    v65 = (unsigned __int64)"Succeeded";
    LODWORD(v76) = *(_DWORD *)(a1 + 912);
    v63 = 2;
    v66 = "LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted";
    *(_QWORD *)v77 = "LpaServiceLpd";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)"Succeeded",
      (unsigned int)byte_18013166B,
      (unsigned int)"LpaServiceLpd",
      (unsigned int)"Failed",
      (__int64)v77,
      (__int64)&v66,
      (__int64)&v63,
      (__int64)&v76,
      (__int64)&v65,
      (__int64)&v75,
      (__int64)&v69);
  }
  memset(v85, 0, sizeof(v85));
  v86 = 0;
  v65 = 0;
  if ( (int)StringCchLengthW((const unsigned __int16 *)v81, 0x15u, &v65) < 0 )
    goto LABEL_33;
  v14 = v65;
  v15 = v65;
  if ( v65 > v13 - 14 )
    v15 = v13 - 14;
  if ( (int)StringCchCopyNW(v85, v13, (const unsigned __int16 *)v81, v15) < 0 )
  {
LABEL_33:
    v85[0] = 0;
  }
  else
  {
    if ( v14 )
    {
      if ( v14 - 1 > 7 )
      {
        v16 = (unsigned __int8)(v14 - 8);
        v17 = &v85[7];
        while ( v16 )
        {
          *v17++ = 42;
          --v16;
        }
        v4 = v73;
      }
      v85[v14 - 1] = *(_WORD *)&v81[2 * v14 - 2];
    }
    v85[v14] = 0;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    *(_QWORD *)v77 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 400);
    v70 = (__int64)v85;
    v63 = v3;
    LODWORD(v76) = v4;
    LODWORD(v75) = *(unsigned __int8 *)(a1 + 1042);
    v69 = *(unsigned __int8 *)(a1 + 1041);
    LODWORD(v66) = *(unsigned __int8 *)(a1 + 1040);
    LODWORD(v65) = *(_DWORD *)(a1 + 904);
    v71 = (unsigned __int16 *)"LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted";
    v72 = "LpaServiceLpd";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v18,
      (unsigned int)&unk_180131550,
      v19,
      v20,
      (__int64)&v72,
      (__int64)&v71,
      (__int64)&v65,
      (__int64)&v66,
      (__int64)&v69,
      (__int64)&v75,
      (__int64)&v76,
      (__int64)&v63,
      (__int64)&v70,
      (__int64)v77);
  }
  if ( (unsigned int)dword_18015A5E0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18015A5E0, 0x800000000000LL) )
  {
    v72 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 400);
    v71 = v85;
    LODWORD(v65) = v3;
    LODWORD(v66) = v4;
    v63 = *(unsigned __int8 *)(a1 + 1042);
    LODWORD(v76) = *(unsigned __int8 *)(a1 + 1041);
    LODWORD(v75) = *(unsigned __int8 *)(a1 + 1040);
    v69 = *(_DWORD *)(a1 + 904);
    v70 = 16779264;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v21,
      (unsigned int)byte_18013149B,
      v22,
      v23,
      (__int64)&v70,
      (__int64)&v69,
      (__int64)&v75,
      (__int64)&v76,
      (__int64)&v63,
      (__int64)&v66,
      (__int64)&v65,
      (__int64)&v71,
      (__int64)&v72);
  }
  v24 = v61;
  if ( v61 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v78 = a1 + 166;
      LOWORD(v79) = 24;
      *(_QWORD *)v81 = a1 + 142;
      *(_WORD *)&v81[8] = 24;
      v72 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 400);
      v71 = v85;
      v68[0] = v62;
      v70 = *(_QWORD *)(a1 + 944);
      *(_QWORD *)v77 = std::_String_val<std::_Simple_types<char>>::_Myptr(a1 + 240);
      LODWORD(v65) = v3;
      LODWORD(v66) = v4;
      v63 = *(_DWORD *)(a1 + 904);
      v76 = "LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted";
      v75 = "LpaServiceLpd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(
        v25,
        (unsigned int)byte_1801313C1,
        v26,
        v27,
        (__int64)&v75,
        (__int64)&v76,
        (__int64)&v63,
        (__int64)&v66,
        (__int64)&v65,
        (__int64)v77,
        (__int64)&v70,
        (__int64)v68,
        (__int64)&v71,
        (__int64)&v72,
        (__int64)v81,
        (__int64)&v78);
    }
    if ( (unsigned int)dword_18015A5E0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18015A5E0, 0x800000000000LL) )
    {
      *(_QWORD *)v81 = a1 + 166;
      *(_WORD *)&v81[8] = v28;
      v78 = a1 + 142;
      LOWORD(v79) = v28;
      v72 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 400);
      v71 = v85;
      v70 = std::_String_val<std::_Simple_types<char>>::_Myptr(a1 + 240);
      LODWORD(v65) = v3;
      LODWORD(v66) = v4;
      v63 = *(_DWORD *)(a1 + 904);
      *(_QWORD *)v77 = 16779264;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperArray<1>,_tlgWrapperArray<1>>(
        v29,
        (unsigned int)&word_18013131E,
        v30,
        v31,
        (__int64)v77,
        (__int64)&v63,
        (__int64)&v66,
        (__int64)&v65,
        (__int64)&v70,
        (__int64)&v71,
        (__int64)&v72,
        (__int64)&v78,
        (__int64)v81);
    }
  }
  if ( v3 == 1 )
  {
    std::weak_ptr<LPA::Lpd::DownloadInstance>::lock(a1 + 32, &v78);
    if ( v78 )
    {
      v32 = *(_QWORD ***)(v78 + 120);
      for ( i = *v32; i != v32; i = (_QWORD *)*i )
      {
        std::weak_ptr<LPA::LpdNotificationHandler>::lock(i + 2, v81);
        if ( *(_QWORD *)v81 )
        {
          *(_QWORD *)v60 = a1 + 712;
          (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)v81 + 48LL))(
            *(_QWORD *)v81,
            a1 + 884,
            a1 + 992,
            a1 + 368);
        }
        if ( *(_QWORD *)&v81[8] )
          std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v81[8]);
      }
      v3 = v67;
    }
    if ( v79 )
      std::_Ref_count_base::_Decref(v79);
    goto LABEL_57;
  }
LABEL_58:
  if ( *(_BYTE *)(a1 + 873)
    && !*(_BYTE *)(a1 + 872)
    && LPA::Util::CreateTimer(
         (LPA::Util *)(a1 + 928),
         (struct _TP_TIMER **)a1,
         LPA::Lpd::DownloadInstance::InstallClientResponseTimerCallback,
         v12) >= 0 )
  {
    LPA::Util::StartTimer(*(LPA::Util **)(a1 + 928), (struct _TP_TIMER *)0x493E0, 0x2710u, v34, *(unsigned int *)v60);
  }
  if ( v64 )
  {
    std::weak_ptr<LPA::LpdNotificationHandler>::lock(a1 + 64, v81);
    if ( *(_QWORD *)v81 )
    {
      *(_DWORD *)v60 = *(_DWORD *)(a1 + 912);
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64, bool *, __int64, __int64))(**(_QWORD **)v81 + 16LL))(
        *(_QWORD *)v81,
        (unsigned int)v6,
        a1 + 884,
        a1 + 1024,
        *(bool **)v60,
        a1 + 142,
        a1 + 166);
    }
    v37 = *(_DWORD *)&v81[8];
    if ( *(_QWORD *)&v81[8] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v81[8]);
    *(_DWORD *)(a1 + 912) = *(_DWORD *)(a1 + 908);
    if ( v6 < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v38 = "Failed";
        v39 = &word_180131256;
        goto LABEL_72;
      }
    }
    else if ( (unsigned int)CallbackContext > 4 )
    {
      v38 = "Succeeded";
      v39 = word_1801312BA;
LABEL_72:
      v72 = v38;
      LODWORD(v66) = *(_DWORD *)(a1 + 912);
      v71 = (unsigned __int16 *)"LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted";
      v70 = (__int64)"LpaServiceLpd";
      v67 = 0;
      LODWORD(v65) = ((v6 >> 31) & 2) + 15;
      v63 = 4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v37,
        (_DWORD)v39,
        v35,
        v36,
        (__int64)&v70,
        (__int64)&v71,
        (__int64)&v63,
        (__int64)&v66,
        (__int64)&v72,
        (__int64)&v65,
        (__int64)&v67);
    }
  }
  if ( v24 && !*(_BYTE *)(a1 + 877) && !v3 )
  {
    std::weak_ptr<LPA::Lpd::DownloadInstance>::lock(a1 + 32, &v78);
    if ( v78 )
    {
      v40 = *(_QWORD ***)(v78 + 120);
      for ( j = *v40; j != v40; j = (_QWORD *)*j )
      {
        std::weak_ptr<LPA::LpdNotificationHandler>::lock(j + 2, v81);
        if ( *(_QWORD *)v81 )
          (*(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(**(_QWORD **)v81 + 24LL))(
            *(_QWORD *)v81,
            a1 + 884,
            a1 + 936,
            *(unsigned int *)(a1 + 912));
        if ( *(_QWORD *)&v81[8] )
          std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v81[8]);
      }
    }
    if ( v79 )
      std::_Ref_count_base::_Decref(v79);
    v7 = 1;
  }
  v42 = v73;
  if ( v73 == -2147467260 )
  {
    *(_WORD *)(a1 + 872) = 0;
  }
  else if ( v62 )
  {
    if ( *(_QWORD *)(a1 + 944) )
    {
      while ( 1 )
      {
        v43 = **(_QWORD **)(a1 + 936);
        v44 = *(_QWORD *)(a1 + 952);
        std::string::string(&v78, v43 + 16);
        std::string::string(v81, v43 + 48);
        v45 = **(__int64 ***)(a1 + 936);
        v46 = *v45;
        --*(_QWORD *)(a1 + 944);
        *(_QWORD *)v45[1] = v46;
        *(_QWORD *)(v46 + 8) = v45[1];
        std::_List_node<std::tuple<std::string,std::string>,void *>::_Freenode<std::allocator<std::_List_node<std::tuple<std::string,std::string>,void *>>>();
        if ( v43 == v44 )
        {
          *(_QWORD *)(a1 + 952) = *(_QWORD *)(a1 + 936);
          v47 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(a1 + 960);
        }
        else
        {
          v47 = 0;
        }
        v48 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v81);
        v49 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(&v78);
        v50 = LPA::Lpd::DownloadInstance::InitiateCommonMutualAuthentication(
                (LPA::Lpd::DownloadInstance *)a1,
                v49,
                v48,
                0,
                0,
                v47,
                0);
        if ( v50 >= 0 )
          break;
        std::string::_Tidy_deallocate(v81);
        std::string::_Tidy_deallocate(&v78);
        if ( !*(_QWORD *)(a1 + 944) )
        {
          v42 = v73;
          goto LABEL_100;
        }
      }
      v8 = 0;
      std::string::_Tidy_deallocate(v81);
      std::string::_Tidy_deallocate(&v78);
      v42 = v73;
      goto LABEL_129;
    }
  }
  else
  {
    v8 = v7;
    if ( !v7 )
      goto LABEL_129;
  }
  v50 = v74;
LABEL_100:
  if ( *(_BYTE *)(a1 + 873) )
  {
    std::weak_ptr<LPA::Lpd::DownloadInstance>::lock(a1 + 32, &v78);
    if ( v78 )
    {
      v51 = *(_QWORD ***)(v78 + 120);
      for ( k = *v51; k != v51; k = (_QWORD *)*k )
      {
        std::weak_ptr<LPA::LpdNotificationHandler>::lock(k + 2, v81);
        if ( *(_QWORD *)v81 )
          (***(void (__fastcall ****)(_QWORD, __int64, __int64))v81)(*(_QWORD *)v81, a1 + 884, a1 + 1036);
        if ( *(_QWORD *)&v81[8] )
          std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v81[8]);
      }
    }
    if ( v79 )
      std::_Ref_count_base::_Decref(v79);
  }
  std::weak_ptr<LPA::LpdNotificationHandler>::lock(a1 + 48, v81);
  if ( *(_QWORD *)v81 )
  {
    v55 = **(_QWORD **)v81;
    if ( v61 )
      v56 = *(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64, _QWORD, __int64, __int64))(v55 + 8);
    else
      v56 = *(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64, _QWORD, __int64, __int64))(v55 + 24);
    if ( v50 < 0 )
      v57 = a1 + 1024;
    else
      v57 = 0;
    *(_DWORD *)v60 = *(_DWORD *)(a1 + 908);
    v56(*(_QWORD *)v81, (unsigned int)v50, a1 + 884, v57, *(_QWORD *)v60, a1 + 142, a1 + 166);
  }
  if ( *(_QWORD *)&v81[8] )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v81[8]);
  if ( v42 < 0 )
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_129;
    v58 = &word_18013118E;
  }
  else
  {
    if ( (unsigned int)CallbackContext <= 4 )
      goto LABEL_129;
    v58 = word_1801311F2;
  }
  LODWORD(v65) = ((v50 >> 31) & 2) + 15;
  v67 = 0;
  v59 = "Succeeded";
  if ( v50 < 0 )
    v59 = "Failed";
  v72 = v59;
  LODWORD(v66) = *(_DWORD *)(a1 + 912);
  v63 = 2 * v61 + 3;
  v71 = (unsigned __int16 *)"LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted";
  v70 = (__int64)"LpaServiceLpd";
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
    (unsigned int)"Failed",
    (_DWORD)v58,
    v53,
    v54,
    (__int64)&v70,
    (__int64)&v71,
    (__int64)&v63,
    (__int64)&v66,
    (__int64)&v72,
    (__int64)&v65,
    (__int64)&v67);
LABEL_129:
  std::weak_ptr<LPA::LpdNotificationHandler>::lock(a1 + 80, v81);
  if ( *(_QWORD *)v81 )
  {
    *(_DWORD *)v60 = *(_DWORD *)(a1 + 916);
    (***(void (__fastcall ****)(_QWORD, _QWORD, __int64, _QWORD, bool *))v81)(
      *(_QWORD *)v81,
      v42 != -2147467260 ? 0x80004005 : 0,
      a1 + 884,
      0,
      *(bool **)v60);
  }
  if ( *(_QWORD *)&v81[8] )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v81[8]);
  if ( v8 )
  {
    std::weak_ptr<LPA::Lpd::DownloadInstance>::lock(a1 + 32, v81);
    if ( *(_QWORD *)v81 )
      LPA::Lpd::OnDownloadInstanceComplete(
        *(LPA::Lpd **)v81,
        (const struct _GUID *)(a1 + 884),
        (unsigned int *)(a1 + 1036));
    if ( *(_QWORD *)&v81[8] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v81[8]);
  }
}

```

## disassembly

```asm
0x1800b1768  mov     [rsp-8+arg_10], rbx
0x1800b176d  push    rbp
0x1800b176e  push    rsi
0x1800b176f  push    rdi
0x1800b1770  push    r12
0x1800b1772  push    r13
0x1800b1774  push    r14
0x1800b1776  push    r15
0x1800b1778  lea     rbp, [rsp-70h]
0x1800b177d  sub     rsp, 170h
0x1800b1784  mov     rax, cs:__security_cookie
0x1800b178b  xor     rax, rsp
0x1800b178e  mov     [rbp+0A0h+var_38], rax
0x1800b1792  mov     esi, r8d
0x1800b1795  mov     [rbp+0A0h+var_100], r8d
0x1800b1799  mov     edi, edx
0x1800b179b  mov     [rbp+0A0h+var_D8], edx
0x1800b179e  mov     r14, rcx
0x1800b17a1  xor     ebx, ebx
0x1800b17a3  mov     [rbp+0A0h+var_D4], ebx
0x1800b17a6  mov     r12d, ebx
0x1800b17a9  mov     r13b, bl
0x1800b17ac  lea     r15d, [rbx+1]
0x1800b17b0  lea     rdx, [rcx+36Dh]
0x1800b17b7  cmp     dword ptr [rcx+370h], 2
0x1800b17be  jnz     short loc_1800B17D1
0x1800b17c0  mov     r8b, r15b
0x1800b17c3  mov     [rbp+0A0h+var_120], r15b
0x1800b17c7  cmp     [rdx], bl
0x1800b17c9  jz      short loc_1800B17D7
0x1800b17cb  mov     [rbp+0A0h+var_11F], r15b
0x1800b17cf  jmp     short loc_1800B17DA
0x1800b17d1  mov     r8b, bl
0x1800b17d4  mov     [rbp+0A0h+var_120], bl
0x1800b17d7  mov     [rbp+0A0h+var_11F], bl
0x1800b17da  mov     [rbp+0A0h+var_118], bl
0x1800b17dd  mov     word ptr [rbp+0A0h+var_98], bx
0x1800b17e1  xorps   xmm0, xmm0
0x1800b17e4  xor     eax, eax
0x1800b17e6  movups  xmmword ptr [rbp+0A0h+var_98+2], xmm0
0x1800b17ea  movups  [rbp+0A0h+var_86], xmm0
0x1800b17ee  mov     [rbp+0A0h+var_76], rax
0x1800b17f2  mov     [rcx+36Ah], bl
0x1800b17f8  mov     ecx, esi
0x1800b17fa  test    esi, esi
0x1800b17fc  jz      short loc_1800B182E
0x1800b17fe  sub     ecx, r15d
0x1800b1801  jz      short loc_1800B1822
0x1800b1803  sub     ecx, r15d
0x1800b1806  jz      short loc_1800B180D
0x1800b1808  cmp     ecx, r15d
0x1800b180b  jnz     short loc_1800B183E
0x1800b180d  mov     r12d, edi
0x1800b1810  mov     [rbp+0A0h+var_118], r15b
0x1800b1814  test    r8b, r8b
0x1800b1817  jz      short loc_1800B181D
0x1800b1819  cmp     [rdx], bl
0x1800b181b  jnz     short loc_1800B1837
0x1800b181d  mov     r13b, r15b
0x1800b1820  jmp     short loc_1800B1837
0x1800b1822  mov     [rbp+0A0h+var_11F], bl
0x1800b1825  mov     [r14+369h], r15b
0x1800b182c  jmp     short loc_1800B183E
0x1800b182e  mov     [rbp+0A0h+var_D4], edi
0x1800b1831  mov     r13b, r8b
0x1800b1834  xor     r13b, r15b
0x1800b1837  mov     [r14+369h], bl
0x1800b183e  lea     rcx, [r14+1D0h]
0x1800b1845  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b184a  mov     r8, rax; unsigned __int16 *
0x1800b184d  mov     edx, 15h; unsigned __int64
0x1800b1852  lea     rcx, [rbp+0A0h+var_98]; unsigned __int16 *
0x1800b1856  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b185b  lea     rcx, aSucceeded; "Succeeded"
0x1800b1862  lea     rdx, aLpaLpdDownload_12; "LPA::Lpd::DownloadInstance::OnCmaOrInst"...
0x1800b1869  lea     r8, aLpaservicelpd; "LpaServiceLpd"
0x1800b1870  lea     r9, aFailed; "Failed"
0x1800b1877  cmp     esi, r15d
0x1800b187a  ja      loc_1800B1E74
0x1800b1880  mov     eax, cs:CallbackContext
0x1800b1886  test    edi, edi
0x1800b1888  js      short loc_1800B18FD
0x1800b188a  cmp     eax, 4
0x1800b188d  jbe     loc_1800B197B
0x1800b1893  mov     [rbp+0A0h+var_F8], ebx
0x1800b1896  mov     dword ptr [rbp+0A0h+var_D0], 0Fh
0x1800b189d  mov     [rbp+0A0h+var_110], rcx
0x1800b18a1  mov     eax, [r14+390h]
0x1800b18a8  mov     dword ptr [rbp+0A0h+var_C8], eax
0x1800b18ab  mov     [rbp+0A0h+var_11C], 2
0x1800b18b2  mov     [rbp+0A0h+var_108], rdx
0x1800b18b6  mov     qword ptr [rbp+0A0h+var_C0], r8
0x1800b18ba  lea     rax, [rbp+0A0h+var_F8]
0x1800b18be  mov     [rsp+1A0h+var_150], rax
0x1800b18c3  lea     rax, [rbp+0A0h+var_D0]
0x1800b18c7  mov     [rsp+1A0h+var_158], rax
0x1800b18cc  lea     rax, [rbp+0A0h+var_110]
0x1800b18d0  mov     [rsp+1A0h+var_160], rax
0x1800b18d5  lea     rax, [rbp+0A0h+var_C8]
0x1800b18d9  mov     [rsp+1A0h+var_168], rax
0x1800b18de  lea     rax, [rbp+0A0h+var_11C]
0x1800b18e2  mov     [rsp+1A0h+var_170], rax
0x1800b18e7  lea     rax, [rbp+0A0h+var_108]
0x1800b18eb  mov     [rsp+1A0h+var_178], rax
0x1800b18f0  lea     rax, [rbp+0A0h+var_C0]
0x1800b18f4  lea     rdx, byte_18013166B
0x1800b18fb  jmp     short loc_1800B1971
0x1800b18fd  cmp     eax, 2
0x1800b1900  jbe     short loc_1800B197B
0x1800b1902  mov     [rbp+0A0h+var_11C], ebx
0x1800b1905  mov     eax, edi
0x1800b1907  sar     eax, 1Fh
0x1800b190a  and     eax, 2
0x1800b190d  add     eax, 0Fh
0x1800b1910  mov     dword ptr [rbp+0A0h+var_C8], eax
0x1800b1913  mov     qword ptr [rbp+0A0h+var_C0], r9
0x1800b1917  mov     eax, [r14+390h]
0x1800b191e  mov     dword ptr [rbp+0A0h+var_D0], eax
0x1800b1921  mov     [rbp+0A0h+var_F8], 2
0x1800b1928  mov     [rbp+0A0h+var_110], rdx
0x1800b192c  mov     [rbp+0A0h+var_108], r8
0x1800b1930  lea     rax, [rbp+0A0h+var_11C]
0x1800b1934  mov     [rsp+1A0h+var_150], rax
0x1800b1939  lea     rax, [rbp+0A0h+var_C8]
0x1800b193d  mov     [rsp+1A0h+var_158], rax
0x1800b1942  lea     rax, [rbp+0A0h+var_C0]
0x1800b1946  mov     [rsp+1A0h+var_160], rax
0x1800b194b  lea     rax, [rbp+0A0h+var_D0]
0x1800b194f  mov     [rsp+1A0h+var_168], rax
0x1800b1954  lea     rax, [rbp+0A0h+var_F8]
0x1800b1958  mov     [rsp+1A0h+var_170], rax
0x1800b195d  lea     rax, [rbp+0A0h+var_110]
0x1800b1961  mov     [rsp+1A0h+var_178], rax
0x1800b1966  lea     rax, [rbp+0A0h+var_108]
0x1800b196a  lea     rdx, byte_180131607
0x1800b1971  mov     qword ptr [rsp+1A0h+var_180], rax
0x1800b1976  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b197b  mov     [rbp+0A0h+var_68], bx
0x1800b197f  xorps   xmm0, xmm0
0x1800b1982  xor     eax, eax
0x1800b1984  movups  [rbp+0A0h+var_66], xmm0
0x1800b1988  movups  [rbp+0A0h+var_56], xmm0
0x1800b198c  mov     [rbp+0A0h+var_46], rax
0x1800b1990  mov     [rbp+0A0h+var_110], rbx
0x1800b1994  lea     r8, [rbp+0A0h+var_110]; unsigned __int64 *
0x1800b1998  lea     r11d, [rax+15h]
0x1800b199c  mov     edx, r11d; unsigned __int64
0x1800b199f  lea     rcx, [rbp+0A0h+var_98]; unsigned __int16 *
0x1800b19a3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800b19a8  test    eax, eax
0x1800b19aa  js      short loc_1800B1A0D
0x1800b19ac  mov     rbx, [rbp+0A0h+var_110]
0x1800b19b0  mov     r9, rbx
0x1800b19b3  lea     eax, [r11-0Eh]
0x1800b19b7  cmp     rbx, rax
0x1800b19ba  cmova   r9, rax; unsigned __int64
0x1800b19be  lea     r8, [rbp+0A0h+var_98]; unsigned __int16 *
0x1800b19c2  mov     edx, r11d; unsigned __int64
0x1800b19c5  lea     rcx, [rbp+0A0h+var_68]; unsigned __int16 *
0x1800b19c9  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800b19ce  test    eax, eax
0x1800b19d0  js      short loc_1800B1A0B
0x1800b19d2  test    rbx, rbx
0x1800b19d5  jz      short loc_1800B1A02
0x1800b19d7  lea     rax, [rbx-1]
0x1800b19db  cmp     rax, 7
0x1800b19df  jbe     short loc_1800B19F8
0x1800b19e1  sub     al, 7
0x1800b19e3  movzx   ecx, al
0x1800b19e6  mov     eax, 2Ah ; '*'
0x1800b19eb  movzx   eax, ax
0x1800b19ee  lea     rdi, [rbp+0A0h+var_66+0Ch]
0x1800b19f2  rep stosw
0x1800b19f5  mov     edi, [rbp+0A0h+var_D8]
0x1800b19f8  movzx   eax, [rbp+rbx*2+0A0h+var_9A]
0x1800b19fd  mov     [rbp+rbx*2+0A0h+var_6A], ax
0x1800b1a02  xor     eax, eax
0x1800b1a04  mov     [rbp+rbx*2+0A0h+var_68], ax
0x1800b1a09  jmp     short loc_1800B1A11
0x1800b1a0b  xor     ebx, ebx
0x1800b1a0d  mov     [rbp+0A0h+var_68], bx
0x1800b1a11  mov     eax, cs:CallbackContext
0x1800b1a17  cmp     eax, 4
0x1800b1a1a  jbe     loc_1800B1AE5
0x1800b1a20  lea     rcx, [r14+190h]
0x1800b1a27  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b1a2c  mov     qword ptr [rbp+0A0h+var_C0], rax
0x1800b1a30  lea     rax, [rbp+0A0h+var_68]
0x1800b1a34  mov     [rbp+0A0h+var_F0], rax
0x1800b1a38  mov     [rbp+0A0h+var_11C], esi
0x1800b1a3b  mov     dword ptr [rbp+0A0h+var_C8], edi
0x1800b1a3e  movzx   eax, byte ptr [r14+412h]
0x1800b1a46  mov     dword ptr [rbp+0A0h+var_D0], eax
0x1800b1a49  movzx   eax, byte ptr [r14+411h]
0x1800b1a51  mov     [rbp+0A0h+var_F8], eax
0x1800b1a54  movzx   eax, byte ptr [r14+410h]
0x1800b1a5c  mov     dword ptr [rbp+0A0h+var_108], eax
0x1800b1a5f  mov     eax, [r14+388h]
0x1800b1a66  mov     dword ptr [rbp+0A0h+var_110], eax
0x1800b1a69  lea     rax, aLpaLpdDownload_12; "LPA::Lpd::DownloadInstance::OnCmaOrInst"...
0x1800b1a70  mov     [rbp+0A0h+var_E8], rax
0x1800b1a74  lea     rax, aLpaservicelpd; "LpaServiceLpd"
0x1800b1a7b  mov     [rbp+0A0h+var_E0], rax
0x1800b1a7f  lea     rax, [rbp+0A0h+var_C0]
0x1800b1a83  mov     [rsp+1A0h+var_138], rax
0x1800b1a88  lea     rax, [rbp+0A0h+var_F0]
0x1800b1a8c  mov     [rsp+1A0h+var_140], rax
0x1800b1a91  lea     rax, [rbp+0A0h+var_11C]
0x1800b1a95  mov     [rsp+1A0h+var_148], rax
0x1800b1a9a  lea     rax, [rbp+0A0h+var_C8]
0x1800b1a9e  mov     [rsp+1A0h+var_150], rax
0x1800b1aa3  lea     rax, [rbp+0A0h+var_D0]
0x1800b1aa7  mov     [rsp+1A0h+var_158], rax
0x1800b1aac  lea     rax, [rbp+0A0h+var_F8]
0x1800b1ab0  mov     [rsp+1A0h+var_160], rax
0x1800b1ab5  lea     rax, [rbp+0A0h+var_108]
0x1800b1ab9  mov     [rsp+1A0h+var_168], rax
0x1800b1abe  lea     rax, [rbp+0A0h+var_110]
0x1800b1ac2  mov     [rsp+1A0h+var_170], rax
0x1800b1ac7  lea     rax, [rbp+0A0h+var_E8]
0x1800b1acb  mov     [rsp+1A0h+var_178], rax
0x1800b1ad0  lea     rax, [rbp+0A0h+var_E0]
0x1800b1ad4  mov     qword ptr [rsp+1A0h+var_180], rax
0x1800b1ad9  lea     rdx, unk_180131550
0x1800b1ae0  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@44444AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800b1ae5  mov     eax, cs:dword_18015A5E0
0x1800b1aeb  cmp     eax, 5
0x1800b1aee  jbe     loc_1800B1BC0
0x1800b1af4  mov     rdx, 800000000000h
0x1800b1afe  lea     rcx, dword_18015A5E0
0x1800b1b05  call    _tlgKeywordOn
0x1800b1b0a  test    al, al
0x1800b1b0c  jz      loc_1800B1BC0
0x1800b1b12  lea     rcx, [r14+190h]
0x1800b1b19  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b1b1e  mov     [rbp+0A0h+var_E0], rax
0x1800b1b22  lea     rax, [rbp+0A0h+var_68]
0x1800b1b26  mov     [rbp+0A0h+var_E8], rax
0x1800b1b2a  mov     dword ptr [rbp+0A0h+var_110], esi
0x1800b1b2d  mov     dword ptr [rbp+0A0h+var_108], edi
0x1800b1b30  movzx   eax, byte ptr [r14+412h]
0x1800b1b38  mov     [rbp+0A0h+var_11C], eax
0x1800b1b3b  movzx   eax, byte ptr [r14+411h]
0x1800b1b43  mov     dword ptr [rbp+0A0h+var_C8], eax
0x1800b1b46  movzx   eax, byte ptr [r14+410h]
0x1800b1b4e  mov     dword ptr [rbp+0A0h+var_D0], eax
0x1800b1b51  mov     eax, [r14+388h]
0x1800b1b58  mov     [rbp+0A0h+var_F8], eax
0x1800b1b5b  mov     [rbp+0A0h+var_F0], 1000800h
0x1800b1b63  lea     rax, [rbp+0A0h+var_E0]
0x1800b1b67  mov     [rsp+1A0h+var_140], rax
0x1800b1b6c  lea     rax, [rbp+0A0h+var_E8]
0x1800b1b70  mov     [rsp+1A0h+var_148], rax
0x1800b1b75  lea     rax, [rbp+0A0h+var_110]
0x1800b1b79  mov     [rsp+1A0h+var_150], rax
0x1800b1b7e  lea     rax, [rbp+0A0h+var_108]
0x1800b1b82  mov     [rsp+1A0h+var_158], rax
0x1800b1b87  lea     rax, [rbp+0A0h+var_11C]
0x1800b1b8b  mov     [rsp+1A0h+var_160], rax
0x1800b1b90  lea     rax, [rbp+0A0h+var_C8]
0x1800b1b94  mov     [rsp+1A0h+var_168], rax
0x1800b1b99  lea     rax, [rbp+0A0h+var_D0]
0x1800b1b9d  mov     [rsp+1A0h+var_170], rax
0x1800b1ba2  lea     rax, [rbp+0A0h+var_F8]
0x1800b1ba6  mov     [rsp+1A0h+var_178], rax
0x1800b1bab  lea     rax, [rbp+0A0h+var_F0]
0x1800b1baf  mov     qword ptr [rsp+1A0h+var_180], rax
0x1800b1bb4  lea     rdx, byte_18013149B
0x1800b1bbb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44444AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800b1bc0  mov     bl, [rbp+0A0h+var_120]
0x1800b1bc3  test    bl, bl
0x1800b1bc5  jz      loc_1800B1DC7
0x1800b1bcb  mov     eax, cs:CallbackContext
0x1800b1bd1  mov     r8d, 18h
0x1800b1bd7  cmp     eax, 4
0x1800b1bda  jbe     loc_1800B1CDD
0x1800b1be0  lea     rax, [r14+0A6h]
0x1800b1be7  mov     [rbp+0A0h+var_B8], rax
0x1800b1beb  mov     word ptr [rbp+0A0h+var_B0], r8w
0x1800b1bf0  lea     rax, [r14+8Eh]
0x1800b1bf7  mov     [rbp+0A0h+var_98], rax
0x1800b1bfb  mov     word ptr [rbp+0A0h+var_90], r8w
0x1800b1c00  lea     rcx, [r14+190h]
0x1800b1c07  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b1c0c  mov     [rbp+0A0h+var_E0], rax
0x1800b1c10  lea     rax, [rbp+0A0h+var_68]
0x1800b1c14  mov     [rbp+0A0h+var_E8], rax
0x1800b1c18  mov     al, [rbp+0A0h+var_11F]
0x1800b1c1b  mov     [rbp+0A0h+var_FC], al
0x1800b1c1e  mov     rax, [r14+3B0h]
0x1800b1c25  mov     [rbp+0A0h+var_F0], rax
0x1800b1c29  lea     rcx, [r14+0F0h]
0x1800b1c30  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800b1c35  mov     qword ptr [rbp+0A0h+var_C0], rax
0x1800b1c39  mov     dword ptr [rbp+0A0h+var_110], esi
0x1800b1c3c  mov     dword ptr [rbp+0A0h+var_108], edi
0x1800b1c3f  mov     eax, [r14+388h]
0x1800b1c46  mov     [rbp+0A0h+var_11C], eax
0x1800b1c49  lea     rax, aLpaLpdDownload_12; "LPA::Lpd::DownloadInstance::OnCmaOrInst"...
0x1800b1c50  mov     [rbp+0A0h+var_C8], rax
  ... truncated ...
```
