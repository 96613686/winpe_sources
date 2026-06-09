# CThreadInputMgr::_KeyStroke(KeyEventFlags,unsigned __int64,__int64,int *)

- ea: `0x180055c30`
- end: `0x180056aa9`
- name: `?_KeyStroke@CThreadInputMgr@@QEAAJW4KeyEventFlags@@_K_JPEAH@Z`
- size: `3705`
- prototype: ``
- caller_count: `7`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800558f0`
- `0x1800559b0`
- `0x180055a90`
- `0x180055b70`
- `0x180081090`
- `0x1800851a8`
- `0x1800ae7b0`

## callees

- `0x1800273e0`
- `0x18002c138`
- `0x180055c30`
- `0x180058204`
- `0x1800582ac`
- `0x1800623bc`
- `0x18006243c`
- `0x180077614`
- `0x1800a83e0`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800562d0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800565e1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800566b9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800567ad`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005688f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180056965`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180056a9c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800562d0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800565e1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800566b9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800567ad`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005688f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180056965`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180056a9c`

## pseudocode

```c
__int64 __fastcall CThreadInputMgr::_KeyStroke(__int64 a1, unsigned int a2, unsigned __int64 a3, __int64 a4, int *a5)
{
  __int64 v5; // r11
  unsigned __int64 v6; // r10
  __int64 v10; // rcx
  char *v11; // rax
  EVENT_DESCRIPTOR *p_EventDescriptor; // rdx
  struct _EVENT_DATA_DESCRIPTOR *p_UserData; // rax
  __int64 v14; // rbx
  int v15; // esi
  int v16; // r13d
  int v17; // r15d
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rbx
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rbx
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  unsigned int i; // esi
  int *v33; // rbx
  unsigned int v34; // r10d
  __int64 v35; // rax
  __int64 v36; // rdx
  int v37; // eax
  int v38; // r8d
  __int64 v39; // r9
  __int64 v40; // rcx
  unsigned __int64 v41; // rsi
  int v42; // ebx
  unsigned int v43; // ebx
  __int64 v44; // rcx
  int v45; // eax
  __int64 v46; // rcx
  __int64 v47; // rax
  int v48; // eax
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v54; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v55; // [rsp+54h] [rbp-ACh]
  int v56; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v57; // [rsp+60h] [rbp-A0h]
  __int128 v58; // [rsp+68h] [rbp-98h] BYREF
  __int64 v59; // [rsp+78h] [rbp-88h]
  int v60; // [rsp+80h] [rbp-80h] BYREF
  int v61; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v62; // [rsp+88h] [rbp-78h]
  int v63; // [rsp+90h] [rbp-70h] BYREF
  int v64; // [rsp+94h] [rbp-6Ch] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+98h] [rbp-68h] BYREF
  char *v66; // [rsp+A8h] [rbp-58h]
  int v67; // [rsp+B0h] [rbp-50h]
  int v68; // [rsp+B4h] [rbp-4Ch]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+C0h] [rbp-40h] BYREF
  char *v70; // [rsp+D0h] [rbp-30h]
  int v71; // [rsp+D8h] [rbp-28h]
  int v72; // [rsp+DCh] [rbp-24h]
  int *v73; // [rsp+E0h] [rbp-20h]
  __int64 v74; // [rsp+E8h] [rbp-18h]
  int *v75; // [rsp+F0h] [rbp-10h]
  __int64 v76; // [rsp+F8h] [rbp-8h]

  v5 = a4;
  v59 = a4;
  v6 = a3;
  v57 = a3;
  v55 = a2;
  if ( !a5 )
    return 2147942487LL;
  *a5 = 0;
  if ( (*(_DWORD *)(a1 + 3668) & 0x80000) != 0 && !*(_BYTE *)(a1 + 3048) )
    return 0;
  v10 = *(_QWORD *)(a1 + 2944);
  if ( !v10 )
  {
    if ( *(_DWORD *)(a1 + 2968) != -2147483644
      && !*(_BYTE *)(a1 + 3061)
      && (unsigned int)CThreadInputMgr::_PeekHotKey((CThreadInputMgr *)a1, a3, a4) )
    {
      ThreadInputManagerTelemetry::HotKeyFailed(0, a1 + 2912);
    }
    goto LABEL_169;
  }
  if ( *(_DWORD *)(a1 + 2968) == -2147483644 || *(_BYTE *)(a1 + 3061) )
  {
LABEL_169:
    if ( (unsigned int)dword_18013D0D8 <= 5
      || (qword_18013D0E8 & 0x80000) == 0
      || (qword_18013D0F0 & 0x80000) != qword_18013D0F0 )
    {
      return 0;
    }
    *(_DWORD *)&EventDescriptor.Level = 5;
    p_EventDescriptor = &EventDescriptor;
    UserData.Ptr = (ULONGLONG)off_18013D0E0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0x80000;
    UserData.Size = *(unsigned __int16 *)off_18013D0E0;
    v70 = byte_180127C65;
    UserData.Reserved = 2;
    v71 = 55;
    v72 = 1;
    p_UserData = &UserData;
    goto LABEL_173;
  }
  if ( (a2 & 0x60) == 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v10 + 120LL))(v10) )
    {
      if ( (unsigned int)dword_18013D0D8 <= 5
        || (qword_18013D0E8 & 0x80000) == 0
        || (qword_18013D0F0 & 0x80000) != qword_18013D0F0 )
      {
        return 0;
      }
      v61 = 5;
      *(_QWORD *)&EventDescriptor.Id = off_18013D0E0;
      v60 = 184549376;
      v62 = 0x80000;
      LODWORD(EventDescriptor.Keyword) = *(unsigned __int16 *)off_18013D0E0;
      v11 = byte_180127BF1;
      v67 = 104;
      goto LABEL_14;
    }
    v6 = v57;
    v5 = v59;
  }
  if ( (a2 & 0x70) == 0 && *(_BYTE *)(a1 + 240) == 1 )
  {
    if ( (unsigned int)dword_18013D0D8 <= 5
      || (qword_18013D0E8 & 0x80000) == 0
      || (qword_18013D0F0 & 0x80000) != qword_18013D0F0 )
    {
      return 0;
    }
    v61 = 5;
    *(_QWORD *)&EventDescriptor.Id = off_18013D0E0;
    v60 = 184549376;
    v62 = 0x80000;
    LODWORD(EventDescriptor.Keyword) = *(unsigned __int16 *)off_18013D0E0;
    v11 = byte_180127BA3;
    v67 = 66;
    goto LABEL_14;
  }
  v54 = 0;
  if ( (unsigned int)CThreadInputMgr::_ProcessHotKey(a1, v6, v5, 1, (a2 >> 2) & 1, (a2 & 0x40) == 0, &v54) )
  {
    *a5 = 1;
    if ( (unsigned int)dword_18013D0D8 <= 5
      || (qword_18013D0E8 & 0x80000) == 0
      || (qword_18013D0F0 & 0x80000) != qword_18013D0F0 )
    {
      return 0;
    }
    v61 = 5;
    *(_QWORD *)&EventDescriptor.Id = off_18013D0E0;
    v60 = 184549376;
    v62 = 0x80000;
    LODWORD(EventDescriptor.Keyword) = *(unsigned __int16 *)off_18013D0E0;
    v11 = (char *)word_180127B5A;
    v67 = 61;
LABEL_14:
    v66 = v11;
    HIDWORD(EventDescriptor.Keyword) = 2;
    v68 = 1;
    v54 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    p_EventDescriptor = (EVENT_DESCRIPTOR *)&v60;
    p_UserData = (struct _EVENT_DATA_DESCRIPTOR *)&EventDescriptor;
LABEL_173:
    EventWriteTransfer(RegHandle, p_EventDescriptor, 0, 0, 2u, p_UserData);
    return 0;
  }
  v14 = 0;
  v15 = *(_DWORD *)(a1 + 3664) - 1;
  v56 = v15;
  v54 = 0;
  v16 = 0;
  v58 = 0;
  v17 = 0;
  while ( 1 )
  {
    if ( v15 != *(_DWORD *)(a1 + 3664) )
    {
      v18 = *((_QWORD *)&v58 + 1);
      v16 = 0;
      v56 = *(_DWORD *)(a1 + 3664);
      if ( *((_QWORD *)&v58 + 1) )
      {
        *((_QWORD *)&v58 + 1) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      v19 = v58;
      if ( (_QWORD)v58 )
      {
        *(_QWORD *)&v58 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      v20 = *(_QWORD *)(a1 + 2944);
      if ( v20 )
      {
        v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 72LL))(v20);
        v14 = v21;
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
      }
      v22 = v58;
      *(_QWORD *)&v58 = v14;
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      v23 = *(_QWORD *)(a1 + 2944);
      if ( v23 )
        v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 72LL))(v23);
      else
        v24 = 0;
      v25 = *(_QWORD *)(a1 + 2944);
      if ( v25 )
        v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 80LL))(v25);
      else
        v26 = 0;
      if ( v24 == v26 )
      {
        v28 = 0;
      }
      else
      {
        v27 = *(_QWORD *)(a1 + 2944);
        if ( v27 )
          v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 80LL))(v27);
        else
          v28 = 0;
        if ( v28 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
      }
      v29 = *((_QWORD *)&v58 + 1);
      *((_QWORD *)&v58 + 1) = v28;
      if ( v29 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        v28 = *((_QWORD *)&v58 + 1);
      }
      v17 = (_QWORD)v58 != 0;
      if ( v28 )
        ++v17;
      v14 = 0;
    }
    if ( !v17 || v16 >= v17 )
      goto LABEL_127;
    _mm_lfence();
    v53 = 0;
    v30 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v58 + v16))(
            *((_QWORD *)&v58 + v16),
            &GUID_555c94a9_b6a0_45cc_a77e_f2f0820f83bf,
            &v53);
    v31 = v53;
    if ( v30 < 0 )
    {
LABEL_118:
      ++v16;
      if ( v31 )
      {
        v53 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      }
      if ( v16 >= v17 )
        goto LABEL_127;
      v15 = v56;
      goto LABEL_126;
    }
    (*(void (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v53 + 336LL))(v53, &v60, &v61);
    for ( i = 0; i < 2; ++i )
    {
      v33 = (int *)(a1 + 2904);
      v34 = *(&v60 + (int)i);
      if ( v34 != *(_DWORD *)(a1 + 2344) && *v33 > 0 )
      {
        v35 = 0;
        while ( 1 )
        {
          v36 = *(_QWORD *)(*(_QWORD *)(a1 + 2896) + 8 * v35);
          if ( *(_DWORD *)(v36 + 48) == v34 )
            break;
          v35 = (unsigned int)(v35 + 1);
          if ( (int)v35 >= *v33 )
            goto LABEL_73;
        }
        v37 = *(_DWORD *)(v36 + 88);
        if ( ((v37 & 0x20) != 0 || *(_QWORD *)(v36 + 56) || *(_QWORD *)(v36 + 64))
          && (v37 & 1) == 0
          && !*(_DWORD *)(v36 + 140)
          && !(unsigned int)CThreadInputMgr::_CallKeyEventSink(a1, v34, v53, v55, v57, v59, a5)
          && *a5 )
        {
          if ( (unsigned int)dword_18013D0D8 > 5
            && (qword_18013D0E8 & 0x80000) != 0
            && (qword_18013D0F0 & 0x80000) == qword_18013D0F0 )
          {
            *(_DWORD *)&EventDescriptor.Level = 5;
            UserData.Ptr = (ULONGLONG)off_18013D0E0;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            EventDescriptor.Keyword = 0x80000;
            UserData.Size = *(unsigned __int16 *)off_18013D0E0;
            v70 = (char *)&word_180127B06;
            UserData.Reserved = 2;
            v71 = 72;
            v72 = 1;
            EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
          }
          v50 = v53;
          if ( v53 )
          {
            v53 = 0;
            goto LABEL_143;
          }
LABEL_144:
          Microsoft::WRL::ComPtr<ITfContext>::~ComPtr<ITfContext>((char *)&v58 + 8);
          Microsoft::WRL::ComPtr<ITfContext>::~ComPtr<ITfContext>(&v58);
          return 0;
        }
      }
LABEL_73:
      *a5 = 0;
      if ( !*(_QWORD *)(a1 + 2944) )
      {
        if ( (unsigned int)dword_18013D0D8 > 5
          && (qword_18013D0E8 & 0x80000) != 0
          && (qword_18013D0F0 & 0x80000) == qword_18013D0F0 )
        {
          *(_DWORD *)&EventDescriptor.Level = 5;
          UserData.Ptr = (ULONGLONG)off_18013D0E0;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0x80000;
          UserData.Size = *(unsigned __int16 *)off_18013D0E0;
          v70 = (char *)&word_180127A9E;
          UserData.Reserved = 2;
          v71 = 92;
          v72 = 1;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
        }
        v52 = v53;
        if ( v53 )
        {
          v53 = 0;
LABEL_163:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
        }
LABEL_164:
        Microsoft::WRL::ComPtr<ITfContext>::~ComPtr<ITfContext>((char *)&v58 + 8);
        Microsoft::WRL::ComPtr<ITfContext>::~ComPtr<ITfContext>(&v58);
        return 2147500037LL;
      }
      if ( v56 != *(_DWORD *)(a1 + 3664) )
      {
        v49 = v53;
        v14 = 0;
        if ( v53 )
        {
          v53 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        }
        v15 = v56;
        goto LABEL_126;
      }
    }
    v38 = *(_DWORD *)(a1 + 2344);
    if ( !v38 )
    {
      v15 = v56;
      v14 = 0;
      goto LABEL_101;
    }
    if ( *v33 <= 0 )
    {
LABEL_81:
      v41 = v57;
      v42 = -2147024809;
    }
    else
    {
      v39 = *(_QWORD *)(a1 + 2896);
      v40 = 0;
      while ( *(_DWORD *)(*(_QWORD *)(v39 + 8 * v40) + 48LL) != v38 )
      {
        v40 = (unsigned int)(v40 + 1);
        if ( (int)v40 >= *v33 )
          goto LABEL_81;
      }
      v41 = v57;
      v42 = CTip::OnKeyboardEvent(*(_QWORD *)(v39 + 8 * v40), v53, v55, v57, v59, a5);
    }
    if ( (unsigned int)dword_18013D0D8 > 5
      && (qword_18013D0E8 & 0x80000) != 0
      && (qword_18013D0F0 & 0x80000) == qword_18013D0F0 )
    {
      v63 = *a5;
      v64 = v42;
      v75 = &v63;
      v76 = 4;
      v73 = &v64;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_18013D0E0;
      v74 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0x80000;
      UserData.Size = *(unsigned __int16 *)off_18013D0E0;
      v70 = byte_180127A4D;
      UserData.Reserved = 2;
      v71 = 69;
      v72 = 1;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
    }
    if ( !v42 )
      break;
    v45 = v54;
    if ( v42 == 292096 )
      v45 = 292096;
    v54 = v45;
LABEL_96:
    v14 = 0;
    *a5 = 0;
    if ( !*(_QWORD *)(a1 + 2944) )
    {
      if ( (unsigned int)dword_18013D0D8 > 5
        && (qword_18013D0E8 & 0x80000) != 0
        && (qword_18013D0F0 & 0x80000) == qword_18013D0F0 )
      {
        *(_DWORD *)&EventDescriptor.Level = 5;
        UserData.Ptr = (ULONGLONG)off_18013D0E0;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0x80000;
        UserData.Size = *(unsigned __int16 *)off_18013D0E0;
        v70 = byte_1801279F5;
        UserData.Reserved = 2;
        v71 = 76;
        v72 = 1;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
      }
      v50 = v53;
      if ( v53 )
      {
        v53 = 0;
LABEL_143:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      }
      goto LABEL_144;
    }
    v15 = v56;
    if ( v56 != *(_DWORD *)(a1 + 3664) )
    {
      v46 = v53;
      if ( !v53 )
        goto LABEL_126;
LABEL_99:
      v53 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      goto LABEL_126;
    }
LABEL_101:
    v47 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v53 + 288LL))(v53);
    if ( !v47 )
      goto LABEL_117;
    switch ( v55 & 7 )
    {
      case 1u:
        v48 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, __int64, int *))(*(_QWORD *)v47 + 24LL))(
                v47,
                v57,
                v59,
                a5);
        break;
      case 2u:
        v48 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, __int64, int *))(*(_QWORD *)v47 + 32LL))(
                v47,
                v57,
                v59,
                a5);
        break;
      case 5u:
        v48 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, __int64, int *))(*(_QWORD *)v47 + 40LL))(
                v47,
                v57,
                v59,
                a5);
        break;
      case 6u:
        v48 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, __int64, int *))(*(_QWORD *)v47 + 48LL))(
                v47,
                v57,
                v59,
                a5);
        break;
      default:
        goto LABEL_111;
    }
    if ( !v48 )
    {
LABEL_111:
      if ( *a5 )
      {
        if ( (unsigned int)dword_18013D0D8 > 5
          && (qword_18013D0E8 & 0x80000) != 0
          && (qword_18013D0F0 & 0x80000) == qword_18013D0F0 )
        {
          *(_DWORD *)&EventDescriptor.Level = 5;
          UserData.Ptr = (ULONGLONG)off_18013D0E0;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0x80000;
          UserData.Size = *(unsigned __int16 *)off_18013D0E0;
          v70 = &byte_18012799F;
          UserData.Reserved = 2;
          v71 = 74;
          v72 = 1;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
        }
        v51 = v53;
        if ( v53 )
        {
          v53 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        }
LABEL_127:
        v43 = v55;
        goto LABEL_128;
      }
    }
    if ( !*(_QWORD *)(a1 + 2944) )
    {
      if ( (unsigned int)dword_18013D0D8 > 5
        && (qword_18013D0E8 & 0x80000) != 0
        && (qword_18013D0F0 & 0x80000) == qword_18013D0F0 )
      {
        *(_DWORD *)&EventDescriptor.Level = 5;
        UserData.Ptr = (ULONGLONG)off_18013D0E0;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0x80000;
        UserData.Size = *(unsigned __int16 *)off_18013D0E0;
        v70 = byte_180127933;
        UserData.Reserved = 2;
        v71 = 96;
        v72 = 1;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
      }
      v52 = v53;
      if ( v53 )
      {
        v53 = 0;
        goto LABEL_163;
      }
      goto LABEL_164;
    }
    if ( v15 == *(_DWORD *)(a1 + 3664) )
    {
      *a5 = 0;
LABEL_117:
      v31 = v53;
      goto LABEL_118;
    }
    v46 = v53;
    if ( v53 )
      goto LABEL_99;
LABEL_126:
    if ( !*((_QWORD *)&v58 + v16) )
      goto LABEL_127;
  }
  if ( !*a5 )
    goto LABEL_96;
  v43 = v55;
  if ( (v55 & 7) == 1 )
    CThreadInputMgr::OnKeystrokeConsumed((CThreadInputMgr *)a1, v41);
  v44 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
LABEL_128:
  if ( *a5 )
    CInputSessionMgr::UpdateInputSession(a1 + 3128, v43, v57);
  Microsoft::WRL::ComPtr<ITfContext>::~ComPtr<ITfContext>((char *)&v58 + 8);
  Microsoft::WRL::ComPtr<ITfContext>::~ComPtr<ITfContext>(&v58);
  return v54;
}

```

## disassembly

```asm
0x180055c30  push    rbp
0x180055c32  push    rbx
0x180055c33  push    rdi
0x180055c34  push    r14
0x180055c36  lea     rbp, [rsp-38h]
0x180055c3b  sub     rsp, 138h
0x180055c42  mov     rax, cs:__security_cookie
0x180055c49  xor     rax, rsp
0x180055c4c  mov     [rbp+50h+var_50], rax
0x180055c50  mov     r14, [rbp+50h+arg_20]
0x180055c57  mov     r11, r9
0x180055c5a  mov     [rsp+150h+var_D8], r9
0x180055c5f  mov     r10, r8
0x180055c62  mov     [rsp+150h+var_F0], r8
0x180055c67  mov     ebx, edx
0x180055c69  mov     [rsp+150h+var_FC], edx
0x180055c6d  mov     rdi, rcx
0x180055c70  test    r14, r14
0x180055c73  jnz     short loc_180055C7F
0x180055c75  mov     eax, 80070057h
0x180055c7a  jmp     loc_180056510
0x180055c7f  mov     [rsp+150h+var_20], rsi
0x180055c87  xor     esi, esi
0x180055c89  mov     [r14], esi
0x180055c8c  test    dword ptr [rcx+0E54h], 80000h
0x180055c96  mov     [rsp+150h+var_28], r12
0x180055c9e  jz      short loc_180055CAD
0x180055ca0  cmp     [rcx+0BE8h], sil
0x180055ca7  jz      loc_180056AA2
0x180055cad  mov     rcx, [rcx+0B80h]
0x180055cb4  test    rcx, rcx
0x180055cb7  jz      loc_1800569A8
0x180055cbd  cmp     dword ptr [rdi+0B98h], 80000004h
0x180055cc7  jz      loc_1800569DD
0x180055ccd  cmp     [rdi+0BF5h], sil
0x180055cd4  jnz     loc_1800569DD
0x180055cda  test    bl, 60h
0x180055cdd  jnz     loc_180055DAB
0x180055ce3  mov     rax, [rcx]
0x180055ce6  mov     rax, [rax+78h]
0x180055cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055cef  test    al, al
0x180055cf1  jz      loc_180055DA1
0x180055cf7  mov     eax, cs:dword_18013D0D8
0x180055cfd  cmp     eax, 5
0x180055d00  jbe     loc_180056AA2
0x180055d06  mov     rcx, cs:qword_18013D0F0
0x180055d0d  mov     rax, cs:qword_18013D0E8
0x180055d14  bt      rax, 13h
0x180055d19  jnb     loc_180056AA2
0x180055d1f  mov     rax, rcx
0x180055d22  and     eax, 80000h
0x180055d27  cmp     rax, rcx
0x180055d2a  jnz     loc_180056AA2
0x180055d30  movzx   eax, cs:word_180127BE7
0x180055d37  mov     [rbp+50h+var_CC], eax
0x180055d3a  mov     rax, cs:off_18013D0E0
0x180055d41  mov     qword ptr [rbp+50h+EventDescriptor.Id], rax
0x180055d45  mov     [rbp+50h+var_D0], 0B000000h
0x180055d4c  mov     [rbp+50h+var_C8], 80000h
0x180055d54  movzx   eax, word ptr [rax]
0x180055d57  mov     dword ptr [rbp+50h+EventDescriptor.Keyword], eax
0x180055d5a  lea     rax, byte_180127BF1
0x180055d61  mov     [rbp+50h+var_A0], 68h ; 'h'
0x180055d68  mov     [rbp+50h+var_A8], rax
0x180055d6c  lea     r12, _TraceLoggingMetadataEnd
0x180055d73  lea     rax, _TraceLoggingMetadata
0x180055d7a  mov     dword ptr [rbp+50h+EventDescriptor.Keyword+4], 2
0x180055d81  sub     r12d, eax
0x180055d84  mov     [rbp+50h+var_9C], 1
0x180055d8b  mov     [rsp+150h+var_100], r12d
0x180055d90  lea     rdx, [rbp+50h+var_D0]
0x180055d94  mov     eax, [rsp+150h+var_100]
0x180055d98  lea     rax, [rbp+50h+EventDescriptor]
0x180055d9c  jmp     loc_180056A82
0x180055da1  mov     r10, [rsp+150h+var_F0]
0x180055da6  mov     r11, [rsp+150h+var_D8]
0x180055dab  test    bl, 70h
0x180055dae  jnz     short loc_180055E2F
0x180055db0  cmp     byte ptr [rdi+0F0h], 1
0x180055db7  jnz     short loc_180055E2F
0x180055db9  mov     eax, cs:dword_18013D0D8
0x180055dbf  cmp     eax, 5
0x180055dc2  jbe     loc_180056AA2
0x180055dc8  mov     rcx, cs:qword_18013D0F0
0x180055dcf  mov     rax, cs:qword_18013D0E8
0x180055dd6  bt      rax, 13h
0x180055ddb  jnb     loc_180056AA2
0x180055de1  mov     rax, rcx
0x180055de4  and     eax, 80000h
0x180055de9  cmp     rax, rcx
0x180055dec  jnz     loc_180056AA2
0x180055df2  movzx   eax, cs:word_180127B99
0x180055df9  mov     [rbp+50h+var_CC], eax
0x180055dfc  mov     rax, cs:off_18013D0E0
0x180055e03  mov     qword ptr [rbp+50h+EventDescriptor.Id], rax
0x180055e07  mov     [rbp+50h+var_D0], 0B000000h
0x180055e0e  mov     [rbp+50h+var_C8], 80000h
0x180055e16  movzx   eax, word ptr [rax]
0x180055e19  mov     dword ptr [rbp+50h+EventDescriptor.Keyword], eax
0x180055e1c  lea     rax, byte_180127BA3
0x180055e23  mov     [rbp+50h+var_A0], 42h ; 'B'
0x180055e2a  jmp     loc_180055D68
0x180055e2f  mov     ecx, ebx
0x180055e31  mov     [rsp+150h+var_100], esi
0x180055e35  shr     ecx, 6
0x180055e38  lea     rdx, [rsp+150h+var_100]
0x180055e3d  mov     [rsp+150h+var_120], rdx
0x180055e42  not     ecx
0x180055e44  and     ecx, 1
0x180055e47  mov     eax, ebx
0x180055e49  mov     dword ptr [rsp+150h+UserData], ecx
0x180055e4d  mov     r9d, 1
0x180055e53  shr     eax, 2
0x180055e56  mov     rcx, rdi
0x180055e59  and     eax, 1
0x180055e5c  mov     r8, r11
0x180055e5f  mov     rdx, r10
0x180055e62  mov     [rsp+150h+UserDataCount], eax
0x180055e66  call    ?_ProcessHotKey@CThreadInputMgr@@QEAAH_K_JW4TimSysHotkey@@HHPEAH@Z; CThreadInputMgr::_ProcessHotKey(unsigned __int64,__int64,TimSysHotkey,int,int,int *)
0x180055e6b  test    eax, eax
0x180055e6d  jz      short loc_180055EEC
0x180055e6f  mov     dword ptr [r14], 1
0x180055e76  mov     eax, cs:dword_18013D0D8
0x180055e7c  cmp     eax, 5
0x180055e7f  jbe     loc_180056AA2
0x180055e85  mov     rcx, cs:qword_18013D0F0
0x180055e8c  mov     rax, cs:qword_18013D0E8
0x180055e93  bt      rax, 13h
0x180055e98  jnb     loc_180056AA2
0x180055e9e  mov     rax, rcx
0x180055ea1  and     eax, 80000h
0x180055ea6  cmp     rax, rcx
0x180055ea9  jnz     loc_180056AA2
0x180055eaf  movzx   eax, cs:word_180127B50
0x180055eb6  mov     [rbp+50h+var_CC], eax
0x180055eb9  mov     rax, cs:off_18013D0E0
0x180055ec0  mov     qword ptr [rbp+50h+EventDescriptor.Id], rax
0x180055ec4  mov     [rbp+50h+var_D0], 0B000000h
0x180055ecb  mov     [rbp+50h+var_C8], 80000h
0x180055ed3  movzx   eax, word ptr [rax]
0x180055ed6  mov     dword ptr [rbp+50h+EventDescriptor.Keyword], eax
0x180055ed9  lea     rax, word_180127B5A
0x180055ee0  mov     [rbp+50h+var_A0], 3Dh ; '='
0x180055ee7  jmp     loc_180055D68
0x180055eec  mov     esi, [rdi+0E50h]
0x180055ef2  lea     r12, _TraceLoggingMetadataEnd
0x180055ef9  xor     ebx, ebx
0x180055efb  mov     [rsp+150h+var_30], r13
0x180055f03  dec     esi
0x180055f05  mov     [rsp+150h+var_38], r15
0x180055f0d  xorps   xmm0, xmm0
0x180055f10  mov     [rsp+150h+var_F8], esi
0x180055f14  mov     [rsp+150h+var_100], ebx
0x180055f18  mov     r13d, ebx
0x180055f1b  movdqu  [rsp+150h+var_E8], xmm0
0x180055f21  mov     r15d, ebx
0x180055f24  nop     dword ptr [rax+00h]
0x180055f28  nop     dword ptr [rax+rax+00000000h]
0x180055f30  mov     eax, [rdi+0E50h]
0x180055f36  cmp     esi, eax
0x180055f38  jz      loc_18005607E
0x180055f3e  mov     rcx, qword ptr [rsp+150h+var_E8+8]
0x180055f43  mov     r13d, ebx
0x180055f46  mov     [rsp+150h+var_F8], eax
0x180055f4a  test    rcx, rcx
0x180055f4d  jz      short loc_180055F60
0x180055f4f  mov     qword ptr [rsp+150h+var_E8+8], rbx
0x180055f54  mov     rax, [rcx]
0x180055f57  mov     rax, [rax+10h]
0x180055f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f60  mov     rcx, qword ptr [rsp+150h+var_E8]
0x180055f65  test    rcx, rcx
0x180055f68  jz      short loc_180055F7B
0x180055f6a  mov     qword ptr [rsp+150h+var_E8], rbx
0x180055f6f  mov     rax, [rcx]
0x180055f72  mov     rax, [rax+10h]
0x180055f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f7b  mov     rcx, [rdi+0B80h]
0x180055f82  test    rcx, rcx
0x180055f85  jz      short loc_180055FAA
0x180055f87  mov     rax, [rcx]
0x180055f8a  mov     rax, [rax+48h]
0x180055f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f93  mov     rbx, rax
0x180055f96  test    rax, rax
0x180055f99  jz      short loc_180055FAA
0x180055f9b  mov     rcx, [rax]
0x180055f9e  mov     rax, [rcx+8]
0x180055fa2  mov     rcx, rbx
0x180055fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055faa  mov     rcx, qword ptr [rsp+150h+var_E8]
0x180055faf  mov     qword ptr [rsp+150h+var_E8], rbx
0x180055fb4  test    rcx, rcx
0x180055fb7  jz      short loc_180055FC5
0x180055fb9  mov     rax, [rcx]
0x180055fbc  mov     rax, [rax+10h]
0x180055fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055fc5  mov     rcx, [rdi+0B80h]
0x180055fcc  test    rcx, rcx
0x180055fcf  jz      short loc_180055FE2
0x180055fd1  mov     rax, [rcx]
0x180055fd4  mov     rax, [rax+48h]
0x180055fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055fdd  mov     rbx, rax
0x180055fe0  jmp     short loc_180055FE4
0x180055fe2  xor     ebx, ebx
0x180055fe4  mov     rcx, [rdi+0B80h]
0x180055feb  test    rcx, rcx
0x180055fee  jz      short loc_180055FFE
0x180055ff0  mov     rax, [rcx]
0x180055ff3  mov     rax, [rax+50h]
0x180055ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055ffc  jmp     short loc_180056000
0x180055ffe  xor     eax, eax
0x180056000  cmp     rbx, rax
0x180056003  jz      short loc_18005603A
0x180056005  mov     rcx, [rdi+0B80h]
0x18005600c  test    rcx, rcx
0x18005600f  jz      short loc_180056022
0x180056011  mov     rax, [rcx]
0x180056014  mov     rax, [rax+50h]
0x180056018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005601d  mov     rbx, rax
0x180056020  jmp     short loc_180056024
0x180056022  xor     ebx, ebx
0x180056024  test    rbx, rbx
0x180056027  jz      short loc_18005603C
0x180056029  mov     rax, [rbx]
0x18005602c  mov     rcx, rbx
0x18005602f  mov     rax, [rax+8]
0x180056033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056038  jmp     short loc_18005603C
0x18005603a  xor     ebx, ebx
0x18005603c  mov     rcx, qword ptr [rsp+150h+var_E8+8]
0x180056041  mov     qword ptr [rsp+150h+var_E8+8], rbx
0x180056046  test    rcx, rcx
0x180056049  jz      short loc_18005605C
0x18005604b  mov     rax, [rcx]
0x18005604e  mov     rax, [rax+10h]
0x180056052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056057  mov     rbx, qword ptr [rsp+150h+var_E8+8]
0x18005605c  mov     rax, qword ptr [rsp+150h+var_E8]
0x180056061  neg     rax
0x180056064  sbb     ecx, ecx
0x180056066  xor     r15d, r15d
0x180056069  neg     ecx
0x18005606b  dec     ecx
0x18005606d  cmp     ecx, 0FFFFFFFFh
0x180056070  setnz   r15b
0x180056074  test    rbx, rbx
0x180056077  jz      short loc_18005607C
0x180056079  inc     r15d
0x18005607c  xor     ebx, ebx
0x18005607e  test    r15d, r15d
0x180056081  jz      loc_1800564BB
0x180056087  cmp     r13d, r15d
0x18005608a  jge     loc_1800564BB
0x180056090  lfence
0x180056093  movsxd  rax, r13d
0x180056096  lea     r8, [rsp+150h+var_108]
0x18005609b  mov     [rsp+150h+var_108], rbx
0x1800560a0  lea     rdx, _GUID_555c94a9_b6a0_45cc_a77e_f2f0820f83bf
0x1800560a7  mov     rcx, qword ptr [rsp+rax*8+150h+var_E8]
0x1800560ac  mov     rax, [rcx]
0x1800560af  mov     rax, [rax]
0x1800560b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800560b7  mov     rcx, [rsp+150h+var_108]
0x1800560bc  test    eax, eax
0x1800560be  js      loc_180056463
0x1800560c4  mov     rax, [rcx]
0x1800560c7  lea     r8, [rbp+50h+var_CC]
0x1800560cb  lea     rdx, [rbp+50h+var_D0]
0x1800560cf  mov     rax, [rax+150h]
0x1800560d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800560db  mov     esi, ebx
0x1800560dd  nop     dword ptr [rax]
0x1800560e0  movsxd  rax, esi
0x1800560e3  lea     rbx, [rdi+0B58h]
0x1800560ea  mov     r10d, [rbp+rax*4+50h+var_D0]
0x1800560ef  cmp     r10d, [rdi+928h]
0x1800560f6  jz      loc_180056181
0x1800560fc  mov     r8d, [rbx]
0x1800560ff  test    r8d, r8d
0x180056102  jle     loc_180056181
0x180056108  mov     r9, [rdi+0B50h]
0x18005610f  xor     eax, eax
0x180056111  mov     rdx, [r9+rax*8]
0x180056115  cmp     [rdx+30h], r10d
0x180056119  jz      short loc_180056124
0x18005611b  inc     eax
0x18005611d  cmp     eax, r8d
0x180056120  jl      short loc_180056111
0x180056122  jmp     short loc_180056181
0x180056124  mov     eax, [rdx+58h]
0x180056127  test    al, 20h
0x180056129  jnz     short loc_180056139
0x18005612b  cmp     qword ptr [rdx+38h], 0
0x180056130  jnz     short loc_180056139
0x180056132  cmp     qword ptr [rdx+40h], 0
  ... truncated ...
```
