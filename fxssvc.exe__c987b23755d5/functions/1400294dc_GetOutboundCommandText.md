# GetOutboundCommandText

- ea: `0x1400294dc`
- end: `0x14002ab80`
- name: `GetOutboundCommandText`
- size: `5796`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002b8c0`

## callees

- `0x140001b8c`
- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004b98`
- `0x140004ce4`
- `0x140004e68`
- `0x140025d24`
- `0x14002862c`
- `0x140028988`
- `0x1400294dc`
- `0x14002c18c`
- `0x14002c28c`
- `0x14002c54c`
- `0x14004fb78`
- `0x14004fc7c`
- `0x14005049c`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002959c`
- `KERNEL32!GetLastError` at `0x1400295fd`
- `KERNEL32!GetLastError` at `0x140029661`
- `KERNEL32!GetLastError` at `0x1400296ba`
- `KERNEL32!GetLastError` at `0x140029825`
- `KERNEL32!GetLastError` at `0x140029901`
- `KERNEL32!GetLastError` at `0x140029d8d`
- `KERNEL32!GetLastError` at `0x140029e5f`
- `KERNEL32!GetLastError` at `0x14002959c`
- `KERNEL32!GetLastError` at `0x1400295fd`
- `KERNEL32!GetLastError` at `0x140029661`
- `KERNEL32!GetLastError` at `0x1400296ba`
- `KERNEL32!GetLastError` at `0x140029825`
- `KERNEL32!GetLastError` at `0x140029901`
- `KERNEL32!GetLastError` at `0x140029d8d`
- `KERNEL32!GetLastError` at `0x140029e5f`
- `KERNEL32!FileTimeToSystemTime` at `0x140029573`
- `KERNEL32!FileTimeToSystemTime` at `0x1400295d1`
- `KERNEL32!FileTimeToSystemTime` at `0x140029573`
- `KERNEL32!FileTimeToSystemTime` at `0x1400295d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall GetOutboundCommandText(__int64 a1, _QWORD *a2)
{
  int RealFaxTimeAsSystemTime; // esi
  int v5; // r14d
  BOOL v6; // r12d
  DWORD LastError; // eax
  BOOL v8; // r15d
  DWORD v9; // eax
  __int64 v10; // rcx
  DWORD v11; // eax
  DWORD v12; // eax
  int v13; // eax
  CMapDeviceId *v14; // rcx
  __int64 v15; // rdx
  DWORD v16; // eax
  void **v17; // rdx
  __int64 v18; // rax
  DWORD v19; // eax
  void *v20; // rcx
  void **v21; // rdx
  __int64 v22; // rax
  __int64 v23; // r9
  unsigned __int16 *String; // rax
  __int64 v25; // rax
  unsigned __int16 *v26; // rax
  __int64 v27; // rax
  unsigned __int16 *v28; // rax
  __int64 v29; // rax
  unsigned __int16 *v30; // rax
  __int64 v31; // rax
  __int64 v32; // rcx
  wchar_t *v33; // rdx
  unsigned int v34; // ecx
  unsigned __int16 *v35; // rax
  void **v36; // rdx
  __int64 v37; // rax
  unsigned __int16 *v38; // rdx
  int v39; // eax
  CMapDeviceId *v40; // rcx
  __int64 v41; // rdx
  DWORD v42; // eax
  void **v43; // rdx
  __int64 v44; // rax
  DWORD v45; // eax
  void **v46; // rdx
  __int64 v47; // rax
  __int64 v48; // rax
  _WORD *v49; // rdx
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v57; // rdx
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rdx
  __int64 v78; // rax
  __int64 v79; // rdx
  __int64 v80; // rax
  __int64 v81; // rdx
  __int64 v82; // rax
  __int64 v83; // rdx
  __int64 v84; // rax
  __int64 v85; // rdx
  __int64 v86; // rax
  __int64 v87; // rdx
  __int64 v88; // rax
  __int64 v89; // rdx
  __int64 v90; // rax
  __int64 v91; // rdx
  __int64 v92; // rax
  __int64 v93; // rdx
  __int64 v94; // rax
  __int64 v95; // rdx
  __int64 v96; // rax
  __int64 v97; // rdx
  __int64 v98; // rax
  __int64 v99; // rdx
  __int64 v100; // rax
  __int64 v101; // rdx
  void *v102[3]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v103; // [rsp+48h] [rbp-B8h]
  void *v104[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v105; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v106; // [rsp+68h] [rbp-98h]
  void *Block[3]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v108; // [rsp+88h] [rbp-78h]
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-70h] BYREF
  SYSTEMTIME UniversalTime; // [rsp+A0h] [rbp-60h] BYREF
  SYSTEMTIME v111; // [rsp+B0h] [rbp-50h] BYREF
  SYSTEMTIME v112; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 Src[104]; // [rsp+D0h] [rbp-30h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
  }
  RealFaxTimeAsSystemTime = 0;
  v5 = 0;
  v111 = 0;
  v112 = 0;
  UniversalTime = 0;
  SystemTime = 0;
  v6 = FileTimeToSystemTime((const FILETIME *)(*(_QWORD *)(a1 + 584) + 424LL), &SystemTime);
  if ( !v6
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, LastError);
  }
  v8 = FileTimeToSystemTime((const FILETIME *)(*(_QWORD *)(a1 + 584) + 424LL), &UniversalTime);
  if ( !v8
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = GetLastError();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)(v8 + 54),
      WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids,
      v9);
  }
  v10 = *(_QWORD *)(a1 + 40);
  if ( v10 )
  {
    RealFaxTimeAsSystemTime = GetRealFaxTimeAsSystemTime(v10, 1, &v111);
    if ( !RealFaxTimeAsSystemTime
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = GetLastError();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)(RealFaxTimeAsSystemTime + 55),
        WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids,
        v11);
    }
    v5 = GetRealFaxTimeAsSystemTime(*(_QWORD *)(a1 + 40), 2, &v112);
    if ( !v5
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = GetLastError();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)(v5 + 56),
        WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids,
        v12);
    }
  }
  v13 = StringCchPrintfW(Src, 0x64u, L"0x%016I64x", *(_QWORD *)(a1 + 16));
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v15 = 57;
    goto LABEL_174;
  }
  std::wstring::append(a2, (void *)L"\"");
  std::wstring::append(a2, Src);
  std::wstring::append(a2, L"\"\t\"");
  v13 = StringCchPrintfW(Src, 0x64u, L"0x%016I64x", *(_QWORD *)(*(_QWORD *)(a1 + 584) + 16LL));
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v15 = 58;
    goto LABEL_174;
  }
  std::wstring::append(a2, Src);
  std::wstring::append(a2, L"\"\t");
  if ( v6 )
  {
    v106 = 7;
    v105 = 0;
    LOWORD(v104[0]) = 0;
    if ( !(unsigned int)GetFaxTimeAsString(&SystemTime, v104) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v16);
      }
      goto LABEL_55;
    }
    v17 = v104;
    if ( v106 >= 8 )
      v17 = (void **)v104[0];
    v18 = FilteredLogString(Block, v17);
    std::wstring::append(a2, v18, 0, -1);
    if ( v108 >= 8 )
      operator delete(Block[0]);
    if ( v106 >= 8 )
      operator delete(v104[0]);
  }
  std::wstring::append(a2, L"\t");
  if ( v8 )
  {
    v106 = 7;
    v105 = 0;
    LOWORD(v104[0]) = 0;
    if ( !(unsigned int)GetFaxTimeAsString(&UniversalTime, v104) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v19);
      }
LABEL_55:
      if ( v106 >= 8 )
      {
        v20 = v104[0];
LABEL_152:
        operator delete(v20);
        return 0;
      }
      return 0;
    }
    v21 = v104;
    if ( v106 >= 8 )
      v21 = (void **)v104[0];
    v22 = FilteredLogString(Block, v21);
    std::wstring::append(a2, v22, 0, -1);
    if ( v108 >= 8 )
      operator delete(Block[0]);
    if ( v106 >= 8 )
      operator delete(v104[0]);
  }
  std::wstring::append(a2, L"\t\"");
  v23 = *(unsigned int *)(a1 + 1844);
  if ( (_DWORD)v23 == 512 )
  {
    String = GetString(0x1F69u);
    v25 = FilteredLogString(v104, String);
    std::wstring::append(a2, v25, 0, -1);
    if ( v106 >= 8 )
      operator delete(v104[0]);
    std::wstring::append(a2, L"\"\t\"");
    std::wstring::append(a2, L"\"\t\"");
    std::wstring::append(a2, L"\"\t");
    std::wstring::append(a2, L"\t");
    std::wstring::append(a2, L"\t\"");
    std::wstring::append(a2, L"\"\t\"");
    std::wstring::append(a2, L"\"\t\"");
    std::wstring::append(a2, L"\"\t\"");
    std::wstring::append(a2, L"\"\t");
    std::wstring::append(a2, L"\t");
    goto LABEL_155;
  }
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 40) + 1128LL) == 8 )
  {
    v30 = GetString(0x1F69u);
    v31 = FilteredLogString(v104, v30);
    std::wstring::append(a2, v31, 0, -1);
  }
  else if ( *(_DWORD *)(*(_QWORD *)(a1 + 40) + 1128LL) == 9 )
  {
    v28 = GetString(0x20000008u);
    v29 = FilteredLogString(v104, v28);
    std::wstring::append(a2, v29, 0, -1);
  }
  else
  {
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 40) + 1128LL) != 11
      && (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 40) + 1128LL) - 12) >= 2 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids,
          v23,
          *(_DWORD *)(a1 + 32));
      }
      goto LABEL_80;
    }
    v26 = GetString(0x1F68u);
    v27 = FilteredLogString(v104, v26);
    std::wstring::append(a2, v27, 0, -1);
  }
  if ( v106 >= 8 )
    operator delete(v104[0]);
LABEL_80:
  std::wstring::append(a2, L"\"\t\"");
  v108 = 7;
  Block[2] = 0;
  LOWORD(Block[0]) = 0;
  v32 = *(_QWORD *)(a1 + 40);
  v33 = (wchar_t *)(v32 + 1216);
  if ( v32 != -1216 && *v33 )
    goto LABEL_90;
  v34 = *(_DWORD *)(v32 + 1132);
  if ( !v34 )
  {
    v33 = L" ";
LABEL_90:
    std::wstring::assign(Block, v33);
    goto LABEL_91;
  }
  v35 = MapFSPIJobExtendedStatusToString(v34);
  if ( v35 )
  {
    v33 = v35;
    goto LABEL_90;
  }
  std::wstring::assign(Block, L" ");
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      62,
      (unsigned int)WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids,
      *(_DWORD *)(*(_QWORD *)(a1 + 40) + 1132LL),
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 16LL) + 40LL) + 584LL);
  }
LABEL_91:
  v36 = Block;
  if ( v108 >= 8 )
    v36 = (void **)Block[0];
  v37 = FilteredLogString(v104, v36);
  std::wstring::append(a2, v37, 0, -1);
  if ( v106 >= 8 )
    operator delete(v104[0]);
  std::wstring::append(a2, L"\"\t\"");
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 40) + 1132LL) )
  {
    v39 = StringCchPrintfW(Src, 0x64u, L"0x%08x");
    if ( v39 < 0 )
    {
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_150;
      }
      v41 = 63;
LABEL_149:
      WPP_SF_d(*((_QWORD *)v40 + 2), v41, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, (unsigned int)v39);
      goto LABEL_150;
    }
    v38 = Src;
  }
  else
  {
    v38 = L" ";
  }
  std::wstring::assign(Block, v38);
  std::wstring::append(a2, Block, 0, -1);
  std::wstring::append(a2, L"\"\t");
  if ( RealFaxTimeAsSystemTime )
  {
    v106 = 7;
    v105 = 0;
    LOWORD(v104[0]) = 0;
    if ( !(unsigned int)GetFaxTimeAsString(&v111, v104) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v42 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v42);
      }
LABEL_122:
      if ( v106 >= 8 )
        operator delete(v104[0]);
      v106 = 7;
      v105 = 0;
      LOWORD(v104[0]) = 0;
LABEL_150:
      if ( v108 >= 8 )
      {
        v20 = Block[0];
        goto LABEL_152;
      }
      return 0;
    }
    v43 = v104;
    if ( v106 >= 8 )
      v43 = (void **)v104[0];
    v44 = FilteredLogString(v102, v43);
    std::wstring::append(a2, v44, 0, -1);
    if ( v103 >= 8 )
      operator delete(v102[0]);
    if ( v106 >= 8 )
      operator delete(v104[0]);
  }
  std::wstring::append(a2, L"\t");
  if ( v5 )
  {
    v106 = 7;
    v105 = 0;
    LOWORD(v104[0]) = 0;
    if ( !(unsigned int)GetFaxTimeAsString(&v112, v104) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v45 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v45);
      }
      goto LABEL_122;
    }
    v46 = v104;
    if ( v106 >= 8 )
      v46 = (void **)v104[0];
    v47 = FilteredLogString(v102, v46);
    std::wstring::append(a2, v47, 0, -1);
    if ( v103 >= 8 )
      operator delete(v102[0]);
    if ( v106 >= 8 )
      operator delete(v104[0]);
  }
  std::wstring::append(a2, L"\t\"");
  v48 = FilteredLogString(v102, *(void **)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 16LL) + 56LL));
  std::wstring::append(a2, v48, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v49 = (_WORD *)(*(_QWORD *)(a1 + 40) + 76LL);
  v50 = -1;
  do
    ++v50;
  while ( v49[v50] );
  if ( v50 )
    v51 = FilteredLogString(v102, v49);
  else
    v51 = FilteredLogString(v102, *(void **)(a1 + 464));
  std::wstring::append(a2, v51, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v52 = FilteredLogString(v102, *(void **)(*(_QWORD *)(a1 + 40) + 1144LL));
  std::wstring::append(a2, v52, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v53 = FilteredLogString(v102, *(void **)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 16LL) + 96LL));
  std::wstring::append(a2, v53, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t");
  v39 = StringCchPrintfW(Src, 0x64u, L"%ld", *(unsigned int *)(*(_QWORD *)(a1 + 40) + 1168LL));
  if ( v39 < 0 )
  {
    v40 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_150;
    }
    v41 = 66;
    goto LABEL_149;
  }
  std::wstring::append(a2, Src);
  std::wstring::append(a2, L"\t");
  if ( v108 >= 8 )
    operator delete(Block[0]);
LABEL_155:
  v13 = StringCchPrintfW(Src, 0x64u, L"%ld", *(unsigned int *)(*(_QWORD *)(a1 + 584) + 64LL));
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v15 = 67;
    goto LABEL_174;
  }
  std::wstring::append(a2, Src);
  std::wstring::append(a2, L"\t\"");
  v54 = FilteredLogString(v102, *(void **)(a1 + 56));
  std::wstring::append(a2, v54, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v55 = FilteredLogString(v102, *(void **)(*(_QWORD *)(a1 + 584) + 160LL));
  std::wstring::append(a2, v55, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t");
  v13 = StringCchPrintfW(Src, 0x64u, L"%ld", *(unsigned int *)(*(_QWORD *)(a1 + 584) + 388LL));
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v15 = 68;
    goto LABEL_174;
  }
  std::wstring::append(a2, Src);
  std::wstring::append(a2, L"\t");
  v13 = StringCchPrintfW(Src, 0x64u, L"%d", *(unsigned int *)(a1 + 592));
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v15 = 69;
LABEL_174:
    WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, (unsigned int)v13);
    return 0;
  }
  std::wstring::append(a2, Src);
  std::wstring::append(a2, L"\t\"");
  v57 = *(_QWORD *)(a1 + 584);
  if ( *(_DWORD *)(v57 + 192) == 1 )
  {
    v58 = FilteredLogString(v102, *(void **)(v57 + 184));
    std::wstring::append(a2, v58, 0, -1);
    if ( v103 >= 8 )
      operator delete(v102[0]);
  }
  else
  {
    std::wstring::append(a2, L" ");
  }
  std::wstring::append(a2, L"\"\t\"");
  v59 = FilteredLogString(v102, *(void **)(*(_QWORD *)(a1 + 584) + 208LL));
  std::wstring::append(a2, v59, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v60 = FilteredLogString(v102, *(void **)(*(_QWORD *)(a1 + 584) + 200LL));
  std::wstring::append(a2, v60, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v61 = FilteredLogString(v102, *(void **)(*(_QWORD *)(a1 + 584) + 400LL));
  std::wstring::append(a2, v61, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v62 = FilteredLogString(v102, *(void **)(*(_QWORD *)(a1 + 584) + 248LL));
  std::wstring::append(a2, v62, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v63 = FilteredLogString(v102, *(void **)(*(_QWORD *)(a1 + 584) + 256LL));
  std::wstring::append(a2, v63, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v64 = FilteredLogString(v102, *(void **)(*(_QWORD *)(a1 + 584) + 264LL));
  std::wstring::append(a2, v64, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v65 = FilteredLogString(v102, *(void **)(*(_QWORD *)(a1 + 584) + 272LL));
  std::wstring::append(a2, v65, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v66 = FilteredLogString(v102, *(void **)(*(_QWORD *)(a1 + 584) + 280LL));
  std::wstring::append(a2, v66, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v67 = FilteredLogString(v102, *(void **)(*(_QWORD *)(a1 + 584) + 296LL));
  std::wstring::append(a2, v67, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v68 = FilteredLogString(v102, *(void **)(*(_QWORD *)(a1 + 584) + 304LL));
  std::wstring::append(a2, v68, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v69 = FilteredLogString(v102, *(void **)(*(_QWORD *)(a1 + 584) + 312LL));
  std::wstring::append(a2, v69, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v70 = FilteredLogString(v102, *(void **)(*(_QWORD *)(a1 + 584) + 320LL));
  std::wstring::append(a2, v70, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v71 = FilteredLogString(v102, *(void **)(*(_QWORD *)(a1 + 584) + 328LL));
  std::wstring::append(a2, v71, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v72 = FilteredLogString(v102, *(void **)(*(_QWORD *)(a1 + 584) + 336LL));
  std::wstring::append(a2, v72, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v73 = FilteredLogString(v102, *(void **)(*(_QWORD *)(a1 + 584) + 344LL));
  std::wstring::append(a2, v73, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v74 = FilteredLogString(v102, *(void **)(*(_QWORD *)(a1 + 584) + 352LL));
  std::wstring::append(a2, v74, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v75 = FilteredLogString(v102, *(void **)(a1 + 456));
  std::wstring::append(a2, v75, 0, -1);
  if ( v103 >= 8 )
    operator delete(v102[0]);
  std::wstring::append(a2, L"\"\t\"");
  v76 = FilteredLogString(v102, *(void **)(a1 + 464));
  std::wstring::append(a2, v76, 0, -1);
  LOBYTE(v77) = 1;
  std::wstring::_Tidy(v102, v77, 0);
  std::wstring::append(a2, L"\"\t\"");
  v78 = FilteredLogString(v102, *(void **)(a1 + 472));
  std::wstring::append(a2, v78, 0, -1);
  LOBYTE(v79) = 1;
  std::wstring::_Tidy(v102, v79, 0);
  std::wstring::append(a2, L"\"\t\"");
  v80 = FilteredLogString(v102, *(void **)(a1 + 480));
  std::wstring::append(a2, v80, 0, -1);
  LOBYTE(v81) = 1;
  std::wstring::_Tidy(v102, v81, 0);
  std::wstring::append(a2, L"\"\t\"");
  v82 = FilteredLogString(v102, *(void **)(a1 + 488));
  std::wstring::append(a2, v82, 0, -1);
  LOBYTE(v83) = 1;
  std::wstring::_Tidy(v102, v83, 0);
  std::wstring::append(a2, L"\"\t\"");
  v84 = FilteredLogString(v102, *(void **)(a1 + 504));
  std::wstring::append(a2, v84, 0, -1);
  LOBYTE(v85) = 1;
  std::wstring::_Tidy(v102, v85, 0);
  std::wstring::append(a2, L"\"\t\"");
  v86 = FilteredLogString(v102, *(void **)(a1 + 512));
  std::wstring::append(a2, v86, 0, -1);
  LOBYTE(v87) = 1;
  std::wstring::_Tidy(v102, v87, 0);
  std::wstring::append(a2, L"\"\t\"");
  v88 = FilteredLogString(v102, *(void **)(a1 + 520));
  std::wstring::append(a2, v88, 0, -1);
  LOBYTE(v89) = 1;
  std::wstring::_Tidy(v102, v89, 0);
  std::wstring::append(a2, L"\"\t\"");
  v90 = FilteredLogString(v102, *(void **)(a1 + 528));
  std::wstring::append(a2, v90, 0, -1);
  LOBYTE(v91) = 1;
  std::wstring::_Tidy(v102, v91, 0);
  std::wstring::append(a2, L"\"\t\"");
  v92 = FilteredLogString(v102, *(void **)(a1 + 536));
  std::wstring::append(a2, v92, 0, -1);
  LOBYTE(v93) = 1;
  std::wstring::_Tidy(v102, v93, 0);
  std::wstring::append(a2, L"\"\t\"");
  v94 = FilteredLogString(v102, *(void **)(a1 + 544));
  std::wstring::append(a2, v94, 0, -1);
  LOBYTE(v95) = 1;
  std::wstring::_Tidy(v102, v95, 0);
  std::wstring::append(a2, L"\"\t\"");
  v96 = FilteredLogString(v102, *(void **)(a1 + 552));
  std::wstring::append(a2, v96, 0, -1);
  LOBYTE(v97) = 1;
  std::wstring::_Tidy(v102, v97, 0);
  std::wstring::append(a2, L"\"\t\"");
  v98 = FilteredLogString(v102, *(void **)(a1 + 560));
  std::wstring::append(a2, v98, 0, -1);
  LOBYTE(v99) = 1;
  std::wstring::_Tidy(v102, v99, 0);
  std::wstring::append(a2, L"\"\t\"");
  v100 = FilteredLogString(v102, *(void **)(a1 + 360));
  std::wstring::append(a2, v100, 0, -1);
  LOBYTE(v101) = 1;
  std::wstring::_Tidy(v102, v101, 0);
  std::wstring::append(a2, L"\"\r\n");
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    if ( a2[3] >= 8u )
      a2 = (_QWORD *)*a2;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, a2);
  }
  return 1;
}

```

## disassembly

```asm
0x1400294dc  mov     [rsp-8+arg_10], rbx
0x1400294e1  push    rbp
0x1400294e2  push    rsi
0x1400294e3  push    rdi
0x1400294e4  push    r12
0x1400294e6  push    r13
0x1400294e8  push    r14
0x1400294ea  push    r15
0x1400294ec  lea     rbp, [rsp-0B0h]
0x1400294f4  sub     rsp, 1B0h
0x1400294fb  mov     rax, cs:__security_cookie
0x140029502  xor     rax, rsp
0x140029505  mov     [rbp+0E0h+var_40], rax
0x14002950c  mov     rbx, rdx
0x14002950f  mov     rdi, rcx
0x140029512  lea     r15, WPP_GLOBAL_Control
0x140029519  mov     rcx, cs:WPP_GLOBAL_Control
0x140029520  cmp     rcx, r15
0x140029523  jz      short loc_140029546
0x140029525  test    byte ptr [rcx+1Ch], 4
0x140029529  jz      short loc_140029546
0x14002952b  cmp     byte ptr [rcx+19h], 5
0x14002952f  jb      short loc_140029546
0x140029531  mov     edx, 34h ; '4'
0x140029536  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002953d  mov     rcx, [rcx+10h]
0x140029541  call    WPP_SF_
0x140029546  xor     esi, esi
0x140029548  xor     r14d, r14d
0x14002954b  xorps   xmm0, xmm0
0x14002954e  movups  xmmword ptr [rbp+0E0h+var_130.wYear], xmm0
0x140029552  xorps   xmm1, xmm1
0x140029555  movups  xmmword ptr [rbp+0E0h+var_120.wYear], xmm1
0x140029559  movups  xmmword ptr [rbp+0E0h+UniversalTime.wYear], xmm0
0x14002955d  movups  xmmword ptr [rbp+0E0h+SystemTime.wYear], xmm1
0x140029561  mov     rcx, [rdi+248h]
0x140029568  add     rcx, 1A8h; lpFileTime
0x14002956f  lea     rdx, [rbp+0E0h+SystemTime]; lpSystemTime
0x140029573  call    cs:__imp_FileTimeToSystemTime
0x140029579  mov     r12d, eax
0x14002957c  lea     r13d, [rsi+2]
0x140029580  test    eax, eax
0x140029582  jnz     short loc_1400295BF
0x140029584  mov     rax, cs:WPP_GLOBAL_Control
0x14002958b  cmp     rax, r15
0x14002958e  jz      short loc_1400295BF
0x140029590  test    byte ptr [rax+1Ch], 4
0x140029594  jz      short loc_1400295BF
0x140029596  cmp     [rax+19h], r13b
0x14002959a  jb      short loc_1400295BF
0x14002959c  call    cs:__imp_GetLastError
0x1400295a2  lea     edx, [rsi+35h]
0x1400295a5  mov     r9d, eax
0x1400295a8  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x1400295af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400295b6  mov     rcx, [rcx+10h]
0x1400295ba  call    WPP_SF_d
0x1400295bf  mov     rcx, [rdi+248h]
0x1400295c6  add     rcx, 1A8h; lpFileTime
0x1400295cd  lea     rdx, [rbp+0E0h+UniversalTime]; lpSystemTime
0x1400295d1  call    cs:__imp_FileTimeToSystemTime
0x1400295d7  mov     r15d, eax
0x1400295da  test    eax, eax
0x1400295dc  jnz     short loc_140029621
0x1400295de  mov     rax, cs:WPP_GLOBAL_Control
0x1400295e5  lea     rcx, WPP_GLOBAL_Control
0x1400295ec  cmp     rax, rcx
0x1400295ef  jz      short loc_140029621
0x1400295f1  test    byte ptr [rax+1Ch], 4
0x1400295f5  jz      short loc_140029621
0x1400295f7  cmp     [rax+19h], r13b
0x1400295fb  jb      short loc_140029621
0x1400295fd  call    cs:__imp_GetLastError
0x140029603  lea     edx, [r15+36h]
0x140029607  mov     r9d, eax
0x14002960a  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140029611  mov     rcx, cs:WPP_GLOBAL_Control
0x140029618  mov     rcx, [rcx+10h]
0x14002961c  call    WPP_SF_d
0x140029621  mov     rcx, [rdi+28h]
0x140029625  test    rcx, rcx
0x140029628  jz      loc_1400296DE
0x14002962e  lea     r8, [rbp+0E0h+var_130]
0x140029632  mov     edx, 1
0x140029637  call    ?GetRealFaxTimeAsSystemTime@@YAHQEAU_JOB_ENTRY@@W4FAX_ENUM_TIME_TYPES@@PEAU_SYSTEMTIME@@@Z; GetRealFaxTimeAsSystemTime(_JOB_ENTRY * const,FAX_ENUM_TIME_TYPES,_SYSTEMTIME *)
0x14002963c  mov     esi, eax
0x14002963e  test    eax, eax
0x140029640  jnz     short loc_140029684
0x140029642  mov     rcx, cs:WPP_GLOBAL_Control
0x140029649  lea     rax, WPP_GLOBAL_Control
0x140029650  cmp     rcx, rax
0x140029653  jz      short loc_140029684
0x140029655  test    byte ptr [rcx+1Ch], 4
0x140029659  jz      short loc_140029684
0x14002965b  cmp     [rcx+19h], r13b
0x14002965f  jb      short loc_140029684
0x140029661  call    cs:__imp_GetLastError
0x140029667  lea     edx, [rsi+37h]
0x14002966a  mov     r9d, eax
0x14002966d  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140029674  mov     rcx, cs:WPP_GLOBAL_Control
0x14002967b  mov     rcx, [rcx+10h]
0x14002967f  call    WPP_SF_d
0x140029684  lea     r8, [rbp+0E0h+var_120]
0x140029688  mov     edx, r13d
0x14002968b  mov     rcx, [rdi+28h]
0x14002968f  call    ?GetRealFaxTimeAsSystemTime@@YAHQEAU_JOB_ENTRY@@W4FAX_ENUM_TIME_TYPES@@PEAU_SYSTEMTIME@@@Z; GetRealFaxTimeAsSystemTime(_JOB_ENTRY * const,FAX_ENUM_TIME_TYPES,_SYSTEMTIME *)
0x140029694  mov     r14d, eax
0x140029697  test    eax, eax
0x140029699  jnz     short loc_1400296DE
0x14002969b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400296a2  lea     rax, WPP_GLOBAL_Control
0x1400296a9  cmp     rcx, rax
0x1400296ac  jz      short loc_1400296DE
0x1400296ae  test    byte ptr [rcx+1Ch], 4
0x1400296b2  jz      short loc_1400296DE
0x1400296b4  cmp     [rcx+19h], r13b
0x1400296b8  jb      short loc_1400296DE
0x1400296ba  call    cs:__imp_GetLastError
0x1400296c0  lea     edx, [r14+38h]
0x1400296c4  mov     r9d, eax
0x1400296c7  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x1400296ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400296d5  mov     rcx, [rcx+10h]
0x1400296d9  call    WPP_SF_d
0x1400296de  mov     r9, [rdi+10h]
0x1400296e2  lea     r8, a0x016i64x; "0x%016I64x"
0x1400296e9  mov     edx, 64h ; 'd'; unsigned __int64
0x1400296ee  lea     rcx, [rbp+0E0h+Src]; unsigned __int16 *
0x1400296f2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400296f7  test    eax, eax
0x1400296f9  jns     short loc_140029730
0x1400296fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140029702  lea     rdx, WPP_GLOBAL_Control
0x140029709  cmp     rcx, rdx
0x14002970c  jz      loc_14002A2B4
0x140029712  test    byte ptr [rcx+1Ch], 4
0x140029716  jz      loc_14002A2B4
0x14002971c  cmp     [rcx+19h], r13b
0x140029720  jb      loc_14002A2B4
0x140029726  mov     edx, 39h ; '9'
0x14002972b  jmp     loc_14002A2A1
0x140029730  lea     rdx, asc_14008D0EC; "\""
0x140029737  mov     rcx, rbx; Src
0x14002973a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14002973f  lea     rdx, [rbp+0E0h+Src]; void *
0x140029743  mov     rcx, rbx; Src
0x140029746  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14002974b  lea     rdx, asc_14008D200; "\"\t\""
0x140029752  mov     rcx, rbx; Src
0x140029755  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14002975a  mov     r9, [rdi+248h]
0x140029761  mov     r9, [r9+10h]
0x140029765  lea     r8, a0x016i64x; "0x%016I64x"
0x14002976c  mov     edx, 64h ; 'd'; unsigned __int64
0x140029771  lea     rcx, [rbp+0E0h+Src]; unsigned __int16 *
0x140029775  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002977a  test    eax, eax
0x14002977c  jns     short loc_1400297B3
0x14002977e  mov     rcx, cs:WPP_GLOBAL_Control
0x140029785  lea     rdx, WPP_GLOBAL_Control
0x14002978c  cmp     rcx, rdx
0x14002978f  jz      loc_14002A2B4
0x140029795  test    byte ptr [rcx+1Ch], 4
0x140029799  jz      loc_14002A2B4
0x14002979f  cmp     [rcx+19h], r13b
0x1400297a3  jb      loc_14002A2B4
0x1400297a9  mov     edx, 3Ah ; ':'
0x1400297ae  jmp     loc_14002A2A1
0x1400297b3  lea     rdx, [rbp+0E0h+Src]; void *
0x1400297b7  mov     rcx, rbx; Src
0x1400297ba  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1400297bf  lea     rdx, asc_14008D228; "\"\t"
0x1400297c6  mov     rcx, rbx; Src
0x1400297c9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1400297ce  mov     r13d, 8
0x1400297d4  test    r12d, r12d
0x1400297d7  jz      loc_1400298A1
0x1400297dd  mov     [rsp+1E0h+var_178], 7
0x1400297e6  xor     r12d, r12d
0x1400297e9  mov     [rsp+1E0h+var_180], r12
0x1400297ee  mov     word ptr [rsp+1E0h+var_190], r12w
0x1400297f4  lea     rdx, [rsp+1E0h+var_190]; void *
0x1400297f9  lea     rcx, [rbp+0E0h+SystemTime]; lpUniversalTime
0x1400297fd  call    GetFaxTimeAsString
0x140029802  test    eax, eax
0x140029804  jnz     short loc_14002984F
0x140029806  mov     rax, cs:WPP_GLOBAL_Control
0x14002980d  lea     rcx, WPP_GLOBAL_Control
0x140029814  cmp     rax, rcx
0x140029817  jz      short loc_14002984A
0x140029819  test    byte ptr [rax+1Ch], 4
0x14002981d  jz      short loc_14002984A
0x14002981f  cmp     byte ptr [rax+19h], 2
0x140029823  jb      short loc_14002984A
0x140029825  call    cs:__imp_GetLastError
0x14002982b  lea     edx, [r13+33h]
0x14002982f  mov     r9d, eax
0x140029832  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140029839  mov     rcx, cs:WPP_GLOBAL_Control
0x140029840  mov     rcx, [rcx+10h]
0x140029844  call    WPP_SF_d
0x140029849  nop
0x14002984a  jmp     loc_140029927
0x14002984f  lea     rdx, [rsp+1E0h+var_190]
0x140029854  cmp     [rsp+1E0h+var_178], r13
0x140029859  cmovnb  rdx, [rsp+1E0h+var_190]; Src
0x14002985f  lea     rcx, [rsp+1E0h+Block]; void *
0x140029864  call    FilteredLogString
0x140029869  nop
0x14002986a  or      r9, 0FFFFFFFFFFFFFFFFh
0x14002986e  xor     r8d, r8d
0x140029871  mov     rdx, rax
0x140029874  mov     rcx, rbx
0x140029877  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14002987c  nop
0x14002987d  cmp     [rbp+0E0h+var_158], r13
0x140029881  jb      short loc_14002988E
0x140029883  mov     rcx, [rsp+1E0h+Block]; Block
0x140029888  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002988d  nop
0x14002988e  cmp     [rsp+1E0h+var_178], r13
0x140029893  jb      short loc_1400298A4
0x140029895  mov     rcx, [rsp+1E0h+var_190]; Block
0x14002989a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002989f  jmp     short loc_1400298A4
0x1400298a1  xor     r12d, r12d
0x1400298a4  lea     rdx, asc_14008D0F0; "\t"
0x1400298ab  mov     rcx, rbx; Src
0x1400298ae  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1400298b3  test    r15d, r15d
0x1400298b6  jz      loc_140029991
0x1400298bc  mov     [rsp+1E0h+var_178], 7
0x1400298c5  mov     [rsp+1E0h+var_180], r12
0x1400298ca  mov     word ptr [rsp+1E0h+var_190], r12w
0x1400298d0  lea     rdx, [rsp+1E0h+var_190]; void *
0x1400298d5  lea     rcx, [rbp+0E0h+UniversalTime]; lpUniversalTime
0x1400298d9  call    GetFaxTimeAsString
0x1400298de  test    eax, eax
0x1400298e0  jnz     short loc_14002993C
0x1400298e2  mov     rax, cs:WPP_GLOBAL_Control
0x1400298e9  lea     rcx, WPP_GLOBAL_Control
0x1400298f0  cmp     rax, rcx
0x1400298f3  jz      short loc_140029927
0x1400298f5  test    byte ptr [rax+1Ch], 4
0x1400298f9  jz      short loc_140029927
0x1400298fb  cmp     byte ptr [rax+19h], 2
0x1400298ff  jb      short loc_140029927
0x140029901  call    cs:__imp_GetLastError
0x140029907  mov     edx, 3Ch ; '<'
0x14002990c  mov     r9d, eax
0x14002990f  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140029916  mov     rcx, cs:WPP_GLOBAL_Control
0x14002991d  mov     rcx, [rcx+10h]
0x140029921  call    WPP_SF_d
0x140029926  nop
0x140029927  cmp     [rsp+1E0h+var_178], r13
0x14002992c  jb      loc_14002A2B4
0x140029932  mov     rcx, [rsp+1E0h+var_190]
0x140029937  jmp     loc_14002A0C5
0x14002993c  lea     rdx, [rsp+1E0h+var_190]
0x140029941  cmp     [rsp+1E0h+var_178], r13
0x140029946  cmovnb  rdx, [rsp+1E0h+var_190]; Src
0x14002994c  lea     rcx, [rsp+1E0h+Block]; void *
0x140029951  call    FilteredLogString
0x140029956  nop
0x140029957  or      r15, 0FFFFFFFFFFFFFFFFh
0x14002995b  mov     r9, r15
0x14002995e  xor     r8d, r8d
0x140029961  mov     rdx, rax
0x140029964  mov     rcx, rbx
0x140029967  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14002996c  nop
0x14002996d  cmp     [rbp+0E0h+var_158], r13
0x140029971  jb      short loc_14002997E
0x140029973  mov     rcx, [rsp+1E0h+Block]; Block
0x140029978  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002997d  nop
0x14002997e  cmp     [rsp+1E0h+var_178], r13
0x140029983  jb      short loc_140029995
0x140029985  mov     rcx, [rsp+1E0h+var_190]; Block
0x14002998a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002998f  jmp     short loc_140029995
0x140029991  or      r15, 0FFFFFFFFFFFFFFFFh
0x140029995  lea     rdx, asc_14008D230; "\t\""
0x14002999c  mov     rcx, rbx; Src
0x14002999f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1400299a4  mov     r9d, [rdi+734h]
0x1400299ab  cmp     r9d, 200h
0x1400299b2  jnz     loc_140029A87
0x1400299b8  mov     ecx, 1F69h; unsigned int
0x1400299bd  call    ?GetString@@YAPEAGK@Z; GetString(ulong)
0x1400299c2  mov     rdx, rax; Src
0x1400299c5  lea     rcx, [rsp+1E0h+var_190]; void *
0x1400299ca  call    FilteredLogString
0x1400299cf  nop
0x1400299d0  mov     r9, r15
0x1400299d3  xor     r8d, r8d
0x1400299d6  mov     rdx, rax
0x1400299d9  mov     rcx, rbx
  ... truncated ...
```
