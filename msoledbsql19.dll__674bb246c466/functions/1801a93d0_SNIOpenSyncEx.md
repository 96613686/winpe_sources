# SNIOpenSyncEx

- ea: `0x1801a93d0`
- end: `0x1801a9fb0`
- name: `SNIOpenSyncEx`
- size: `3040`
- prototype: `__int64 __fastcall(struct SNI_CLIENT_CONSUMER_INFO *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1801a06d0`

## callees

- `0x1800013e0`
- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003150`
- `0x180003824`
- `0x180003d80`
- `0x180013360`
- `0x180153e00`
- `0x180156400`
- `0x18015a6f0`
- `0x18015a880`
- `0x18015d1e0`
- `0x18015de80`
- `0x18015dfa0`
- `0x1801a65e1`
- `0x1801a7e30`
- `0x1801a80d0`
- `0x1801a8690`
- `0x1801a8e50`
- `0x1801a8f50`
- `0x1801a93d0`
- `0x1801aa0b0`
- `0x1801ac440`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801a9d56`
- `KERNEL32!GetLastError` at `0x1801a9d56`
- `KERNEL32!GetTickCount` at `0x1801a953a`
- `KERNEL32!GetTickCount` at `0x1801a974d`
- `KERNEL32!GetTickCount` at `0x1801a9859`
- `KERNEL32!GetTickCount` at `0x1801a9a49`
- `KERNEL32!GetTickCount` at `0x1801a953a`
- `KERNEL32!GetTickCount` at `0x1801a974d`
- `KERNEL32!GetTickCount` at `0x1801a9859`
- `KERNEL32!GetTickCount` at `0x1801a9a49`
- `KERNEL32!WideCharToMultiByte` at `0x1801a9cfa`
- `KERNEL32!WideCharToMultiByte` at `0x1801a9d35`
- `KERNEL32!WideCharToMultiByte` at `0x1801a9cfa`
- `KERNEL32!WideCharToMultiByte` at `0x1801a9d35`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x1801a9b27`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x1801a9b27`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SNIOpenSyncEx(struct SNI_CLIENT_CONSUMER_INFO *a1, struct SNI_Conn **a2)
{
  int ProtocolList; // r15d
  char v4; // r12
  unsigned int v5; // r13d
  unsigned int started; // r14d
  __int64 v7; // rax
  __int64 v8; // rsi
  void *v9; // rcx
  __int64 v10; // rbx
  struct localeinfo_struct *v11; // rax
  __int64 v12; // r9
  int v13; // ecx
  char v14; // r8
  const wchar_t *v15; // rdx
  struct ProtList *v16; // r9
  void *v17; // rbx
  unsigned int v18; // ebx
  unsigned int v19; // ecx
  __int64 v20; // r12
  __int64 v21; // r8
  struct SNI_Conn **v22; // r15
  struct ProtElem *v23; // r8
  struct ProtElem *v24; // rax
  struct ProtElem *v25; // r8
  __int64 v26; // rcx
  wchar_t v27; // ax
  unsigned __int16 *v28; // r9
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rbx
  int v32; // eax
  struct SNI_Conn *v33; // rbx
  void *v34; // rbx
  LPSTR lpMultiByteStr; // [rsp+20h] [rbp-E0h]
  int cbMultiByte; // [rsp+28h] [rbp-D8h]
  LPCCH lpDefaultChar; // [rsp+30h] [rbp-D0h]
  LPBOOL lpUsedDefaultChar; // [rsp+38h] [rbp-C8h]
  __int64 v40; // [rsp+40h] [rbp-C0h]
  __int64 v41; // [rsp+48h] [rbp-B8h]
  __int64 v42; // [rsp+50h] [rbp-B0h]
  __int64 v43; // [rsp+58h] [rbp-A8h]
  DWORD TickCount; // [rsp+60h] [rbp-A0h]
  wchar_t v45[4]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v46; // [rsp+70h] [rbp-90h] BYREF
  bool v47; // [rsp+78h] [rbp-88h] BYREF
  bool v48; // [rsp+79h] [rbp-87h] BYREF
  wchar_t v49; // [rsp+7Ch] [rbp-84h] BYREF
  void *v50; // [rsp+80h] [rbp-80h] BYREF
  struct SNI_Conn **v51; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v52[2]; // [rsp+90h] [rbp-70h] BYREF
  int v53; // [rsp+A0h] [rbp-60h] BYREF
  char v54[524]; // [rsp+A4h] [rbp-5Ch] BYREF
  wchar_t Buffer[784]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v51 = a2;
  v52[0] = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266FD8[0] )
  {
    LODWORD(v43) = *((_DWORD *)a1 + 36);
    LODWORD(v42) = *((_DWORD *)a1 + 35);
    LODWORD(v41) = *((_DWORD *)a1 + 34);
    v40 = *((_QWORD *)a1 + 16);
    LODWORD(lpUsedDefaultChar) = *((_DWORD *)a1 + 30);
    lpDefaultChar = (LPCCH)*((_QWORD *)a1 + 14);
    cbMultiByte = *((_DWORD *)a1 + 26);
    lpMultiByteStr = (LPSTR)*((_QWORD *)a1 + 12);
    bidScopeEnterW(v52, off_180266FD8[0], a1, a2);
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180266010[0] )
  {
    v43 = *((_QWORD *)a1 + 6);
    v42 = *((_QWORD *)a1 + 5);
    v41 = *((_QWORD *)a1 + 4);
    v40 = *((_QWORD *)a1 + 3);
    lpUsedDefaultChar = (LPBOOL)*((_QWORD *)a1 + 2);
    lpDefaultChar = (LPCCH)*((_QWORD *)a1 + 1);
    cbMultiByte = *(_DWORD *)a1;
    LODWORD(lpMultiByteStr) = *((_DWORD *)a1 + 38);
    bidTraceW(off_180262840[0], 903168, off_180266010[0], *((unsigned int *)a1 + 37));
  }
  ProtocolList = 0;
  v47 = 0;
  v4 = 0;
  v46 = 0;
  v53 = 0;
  memset_0(v54, 0, 0x204u);
  *(_QWORD *)v45 = 0;
  TickCount = GetTickCount();
  v5 = *((_DWORD *)a1 + 37);
  if ( *((int *)a1 + 26) >= 4 )
  {
    started = 87;
    goto LABEL_117;
  }
  v7 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 3104);
  v8 = v7;
  if ( !v7 )
  {
    started = 14;
    if ( (bidGblFlags & 2) != 0 && off_180266018[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(off_180262848[0], 931840, off_180266018[0], 8);
    }
    SNISetLastError(8, 14, 50100);
    goto LABEL_117;
  }
  *(_WORD *)v7 = 0;
  *(_WORD *)(v7 + 512) = 0;
  *(_WORD *)(v7 + 1024) = 0;
  *(_WORD *)(v7 + 1536) = 0;
  *(_WORD *)(v7 + 1558) = 0;
  *(_WORD *)(v7 + 2070) = 0;
  *(_DWORD *)(v7 + 3094) = 257;
  *(_DWORD *)(v7 + 3100) = -1;
  v46 = *((_QWORD *)a1 + 12);
  started = StartLocalDBInstanceIfLocalDB(
              &v46,
              &v53,
              260,
              (char *)a1 + 180,
              lpMultiByteStr,
              cbMultiByte,
              lpDefaultChar,
              lpUsedDefaultChar,
              v40,
              v41,
              v42,
              v43);
  v9 = (void *)v8;
  if ( started )
    goto LABEL_40;
  v10 = *((int *)a1 + 26);
  v11 = (struct localeinfo_struct *)ImplBidTouch(v8);
  if ( (int)StringCchPrintf_lW(Buffer, 779, L"%s%s", v11, (&g_rgwszPrefix)[v10], v46) < 0 )
  {
    started = 87;
    operator delete((void *)v8, 0xC20u);
    goto LABEL_117;
  }
  v13 = *((_DWORD *)a1 + 44);
  v14 = *((_DWORD *)a1 + 38) != 0;
  *(_BYTE *)(v8 + 3097) = *((_BYTE *)a1 + 172);
  *(_DWORD *)(v8 + 3100) = v13;
  started = ConnectParameter::ParseConnectionString((wchar_t *)v8, Buffer, v14, v12);
  v9 = (void *)v8;
  if ( started )
    goto LABEL_40;
  if ( !*(_WORD *)(v8 + 1536) )
    ProtocolList = GetProtocolList((struct ProtList *)v45, (const wchar_t *)v8, (const wchar_t *)(v8 + 512), &v47);
  if ( *((_DWORD *)a1 + 35) )
  {
    LastConnectCache::RemoveEntry((wchar_t *)(v8 + 2070), v15);
  }
  else
  {
    if ( *((_DWORD *)a1 + 37) != -1 )
    {
      v5 = TickCount + *((_DWORD *)a1 + 37) - GetTickCount();
      if ( v5 == -1 )
        v5 = -2;
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_180266020[0] )
        bidTraceW(off_180262850[0], 1017856, off_180266020[0], v5);
    }
    if ( *(_BYTE *)(v8 + 3094) == 1 && ConnectUsingCache((wchar_t *)v8, (struct ProtList *)v45, a1, v51, v5) == 1 )
    {
      started = 0;
      v20 = v8;
      v50 = (void *)v8;
      goto LABEL_103;
    }
  }
  v48 = 0;
  started = MakeProtocolList((wchar_t *)v8, (struct ProtList *)v45, &v48);
  v9 = (void *)v8;
  if ( started )
  {
LABEL_40:
    operator delete(v9, 0xC20u);
    goto LABEL_117;
  }
  v17 = *(void **)v45;
  if ( !*(_QWORD *)v45 )
  {
    v18 = 50127;
    started = -1;
    if ( (bidGblFlags & 2) != 0 && off_180266028[0] )
    {
      if ( ProtocolList )
        v19 = 50127;
      else
        v19 = v47 + 50145;
      SniErrorIdFromStringId(v19);
      bidTraceW(off_180262858[0], 1058816, off_180266028[0], 8);
    }
    if ( !ProtocolList )
      v18 = v47 + 50145;
    v21 = v18;
LABEL_38:
    SNISetLastError(8, started, v21);
LABEL_39:
    v9 = (void *)v8;
    goto LABEL_40;
  }
  if ( **(_DWORD **)v45 == 3 )
  {
    if ( *((_DWORD *)a1 + 37) != -1 )
    {
      v5 = TickCount + *((_DWORD *)a1 + 37) - GetTickCount();
      if ( v5 == -1 )
        v5 = -2;
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_180266030[0] )
        bidTraceW(off_180262860[0], 1093632, off_180266030[0], v5);
    }
    if ( *(_DWORD *)v17 == 6 )
    {
      *((_BYTE *)v17 + 2057) = *(_BYTE *)(v8 + 3097);
      *((_DWORD *)v17 + 515) = *(_DWORD *)(v8 + 3100);
    }
    v22 = v51;
    started = Connect((struct ConnectParameter *)v8, a1, (struct ProtElem *)v17, v51, v5);
    if ( !started )
    {
      v20 = v8;
      v50 = (void *)v8;
      if ( *(_BYTE *)(v8 + 3094) )
      {
        LastConnectCache::SetEntry((wchar_t *)(v8 + 2070), (const wchar_t *)v17, v23);
        v50 = (void *)v8;
      }
      goto LABEL_103;
    }
    v4 = 1;
    v24 = ProtList::RemoveFirst((ProtList *)v45);
    if ( v24 )
      operator delete(v24, 0xA10u);
    v17 = *(void **)v45;
  }
  else
  {
    v22 = v51;
  }
  if ( v48 )
  {
    started = SSRP::SsrpGetInfo((wchar_t *)v8, (LPCWCH)(v8 + 1024), v45, v16);
    if ( started )
    {
      if ( (bidGblFlags & 2) != 0 && off_180266038[0] )
      {
        SniErrorIdFromStringId(0xC3CEu);
        bidTraceW(off_180262868[0], 1138688, off_180266038[0], 8);
      }
      v21 = 50126;
      goto LABEL_38;
    }
    v17 = *(void **)v45;
    if ( !*(_QWORD *)v45 )
    {
      started = -1;
      v9 = (void *)v8;
      if ( v4 )
        goto LABEL_40;
      if ( (bidGblFlags & 2) != 0 && off_180266040[0] )
      {
        SniErrorIdFromStringId(0xC3D0u);
        bidTraceW(off_180262870[0], 1156096, off_180266040[0], 8);
      }
      v21 = 50128;
      goto LABEL_38;
    }
    goto LABEL_70;
  }
  if ( v17 )
  {
LABEL_70:
    v20 = v8;
    v50 = (void *)v8;
    while ( 1 )
    {
      if ( *((_DWORD *)a1 + 37) != -1 )
      {
        v5 = TickCount + *((_DWORD *)a1 + 37) - GetTickCount();
        if ( v5 == -1 )
          v5 = -2;
        if ( (bidGblFlags & 0x20002) == 0x20002 && off_180266048[0] )
          bidTraceW(off_180262878[0], 1175552, off_180266048[0], v5);
      }
      if ( *(_DWORD *)v17 == 6 )
      {
        *((_BYTE *)v17 + 2057) = *(_BYTE *)(v8 + 3097);
        *((_DWORD *)v17 + 515) = *(_DWORD *)(v8 + 3100);
      }
      started = Connect((struct ConnectParameter *)v8, a1, (struct ProtElem *)v17, v22, v5);
      if ( !started )
        break;
      v26 = 0;
      do
      {
        v27 = aAdmin[v26++];
        if ( v27 != *(_WORD *)(v8 + 2 * v26 + 1534) )
          goto LABEL_91;
      }
      while ( v26 != 6 );
      if ( *(_WORD *)(v8 + 1024) || _wtoi((const wchar_t *)v17 + 772) != 1434 )
        goto LABEL_91;
      v49 = 0;
      if ( !SSRP::GetAdminPort((wchar_t *)v8, L"MSSQLServer", &v49, v28) )
      {
        if ( (bidGblFlags & 2) != 0 && off_180266050[0] )
        {
          SniErrorIdFromStringId(0xC3DFu);
          bidTraceW(off_180262880[0], 1215488, off_180266050[0], 8);
        }
        v29 = 0xFFFFFFFFLL;
        v30 = 50143;
LABEL_90:
        SNISetLastError(8, v29, v30);
LABEL_91:
        v17 = (void *)*((_QWORD *)v17 + 321);
        goto LABEL_92;
      }
      if ( v49 == 1434 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180266058[0] )
        {
          SniErrorIdFromStringId(0xC3DEu);
          bidTraceW(off_180262888[0], 1222656, off_180266058[0], 8);
        }
        v30 = 50142;
        v29 = started;
        goto LABEL_90;
      }
      StringCchPrintfW((wchar_t *)v17 + 772, 256, L"%d", v49);
      *((_BYTE *)v17 + 2058) = 1;
LABEL_92:
      v22 = v51;
      if ( !v17 )
      {
        operator delete((void *)v8, 0xC20u);
        goto LABEL_117;
      }
    }
    if ( *(_BYTE *)(v8 + 3094) )
      LastConnectCache::SetEntry((wchar_t *)(v8 + 2070), (const wchar_t *)v17, v25);
    goto LABEL_103;
  }
  v20 = v8;
  v50 = (void *)v8;
  if ( started )
    goto LABEL_39;
LABEL_103:
  if ( !*(_BYTE *)(v20 + 3095) )
    goto LABEL_111;
  v31 = -1;
  do
    ++v31;
  while ( *(_WORD *)(v20 + 2 * v31 + 1024) );
  if ( (_DWORD)v31 )
  {
    if ( (unsigned int)(WideCharToMultiByte(0, 0, (LPCWCH)(v20 + 1024), v31, 0, 0, 0, 0) - 1) > 0xFC
      || (_mm_lfence(),
          v32 = WideCharToMultiByte(0, 0, (LPCWCH)(v20 + 1024), v31, *((LPSTR *)a1 + 16), v31, 0, 0),
          (unsigned int)(v32 - 1) > 0xFC) )
    {
      started = GetLastError();
      goto LABEL_120;
    }
    *(_BYTE *)(v32 + *((_QWORD *)a1 + 16)) = 0;
  }
  else
  {
LABEL_111:
    *((_QWORD *)a1 + 16) = qword_1801C0CA0;
  }
  v33 = *v51;
  *((_DWORD *)v33 + 12) = bidUpdateItemIDA(*((unsigned int *)*v51 + 12), off_180262B80, *((_QWORD *)a1 + 12));
  operator delete(v50, 0xC20u);
LABEL_117:
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180266060[0] )
    bidTraceW(off_180262890[0], 1295360, off_180266060[0], started);
LABEL_120:
  v50 = (void *)-1LL;
  if ( (bidGblFlags & 0x20004) == 0x20004 && `ProtList::DeleteAll'::`7'::_bidPtrSA_040_980[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, void **, wchar_t *, _QWORD))off_180248060[0])(
      bidID,
      0,
      0,
      &v50,
      `ProtList::DeleteAll'::`7'::_bidPtrSA_040_980[0],
      0);
  while ( 1 )
  {
    v51 = (struct SNI_Conn **)-1LL;
    if ( (bidGblFlags & 0x20004) == 0x20004 && `ProtList::RemoveFirst'::`7'::_bidPtrSA_040_966[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, _QWORD, struct SNI_Conn ***, wchar_t *, _QWORD))off_180248060[0])(
        bidID,
        0,
        0,
        &v51,
        `ProtList::RemoveFirst'::`7'::_bidPtrSA_040_966[0],
        0);
    v34 = *(void **)v45;
    if ( *(_QWORD *)v45 )
      *(_QWORD *)v45 = *(_QWORD *)(*(_QWORD *)v45 + 2568LL);
    if ( (bidGblFlags & 0x20002) == 0x20002 && `ProtList::RemoveFirst'::`19'::_bidPtrSA_030_974[0] )
      bidTraceW(
        `ProtList::RemoveFirst'::`19'::_bidSrcFileA[0],
        997376,
        `ProtList::RemoveFirst'::`19'::_bidPtrSA_030_974[0],
        v34);
    _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v51);
    if ( !v34 )
      break;
    operator delete(v34, 0xA10u);
  }
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v50);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v52);
  return started;
}

```

## disassembly

```asm
0x1801a93d0  mov     [rsp-8+arg_10], rbx
0x1801a93d5  push    rbp
0x1801a93d6  push    rsi
0x1801a93d7  push    rdi
0x1801a93d8  push    r12
0x1801a93da  push    r13
0x1801a93dc  push    r14
0x1801a93de  push    r15
0x1801a93e0  lea     rbp, [rsp-7E0h]
0x1801a93e8  sub     rsp, 8E0h
0x1801a93ef  mov     rax, cs:__security_cookie
0x1801a93f6  xor     rax, rsp
0x1801a93f9  mov     [rbp+810h+var_40], rax
0x1801a9400  mov     [rbp+810h+var_888], rdx
0x1801a9404  mov     rdi, rcx
0x1801a9407  mov     [rbp+810h+var_880], 0FFFFFFFFFFFFFFFFh
0x1801a940f  mov     eax, cs:_bidGblFlags
0x1801a9415  and     eax, 20004h
0x1801a941a  cmp     eax, 20004h
0x1801a941f  jnz     short loc_1801A948D
0x1801a9421  mov     rax, cs:off_180266FD8; "<SNIOpenSyncEx|API|SNI> pClientConsumer"...
0x1801a9428  test    rax, rax
0x1801a942b  jz      short loc_1801A948D
0x1801a942d  mov     eax, [rcx+90h]
0x1801a9433  mov     dword ptr [rsp+910h+var_8B8], eax
0x1801a9437  mov     eax, [rcx+8Ch]
0x1801a943d  mov     dword ptr [rsp+910h+var_8C0], eax
0x1801a9441  mov     eax, [rcx+88h]
0x1801a9447  mov     dword ptr [rsp+910h+var_8C8], eax
0x1801a944b  mov     rax, [rcx+80h]
0x1801a9452  mov     [rsp+910h+var_8D0], rax
0x1801a9457  mov     eax, [rcx+78h]
0x1801a945a  mov     dword ptr [rsp+910h+lpUsedDefaultChar], eax
0x1801a945e  mov     rax, [rcx+70h]
0x1801a9462  mov     [rsp+910h+lpDefaultChar], rax
0x1801a9467  mov     eax, [rcx+68h]
0x1801a946a  mov     [rsp+910h+cbMultiByte], eax
0x1801a946e  mov     rax, [rcx+60h]
0x1801a9472  mov     [rsp+910h+lpMultiByteStr], rax
0x1801a9477  mov     r9, rdx
0x1801a947a  mov     r8, rcx
0x1801a947d  mov     rdx, cs:off_180266FD8; "<SNIOpenSyncEx|API|SNI> pClientConsumer"...
0x1801a9484  lea     rcx, [rbp+810h+var_880]
0x1801a9488  call    _bidScopeEnterW
0x1801a948d  mov     eax, cs:_bidGblFlags
0x1801a9493  and     eax, 20002h
0x1801a9498  cmp     eax, 20002h
0x1801a949d  jnz     short loc_1801A9510
0x1801a949f  mov     rax, cs:off_180266010; "<SNIOpenSyncEx|API|SNI> pClientConsumer"...
0x1801a94a6  test    rax, rax
0x1801a94a9  jz      short loc_1801A9510
0x1801a94ab  mov     rax, [rdi+30h]
0x1801a94af  mov     [rsp+910h+var_8B8], rax
0x1801a94b4  mov     rax, [rdi+28h]
0x1801a94b8  mov     [rsp+910h+var_8C0], rax
0x1801a94bd  mov     rax, [rdi+20h]
0x1801a94c1  mov     [rsp+910h+var_8C8], rax
0x1801a94c6  mov     rax, [rdi+18h]
0x1801a94ca  mov     [rsp+910h+var_8D0], rax
0x1801a94cf  mov     rax, [rdi+10h]
0x1801a94d3  mov     [rsp+910h+lpUsedDefaultChar], rax
0x1801a94d8  mov     rax, [rdi+8]
0x1801a94dc  mov     [rsp+910h+lpDefaultChar], rax
0x1801a94e1  mov     eax, [rdi]
0x1801a94e3  mov     [rsp+910h+cbMultiByte], eax
0x1801a94e7  mov     eax, [rdi+98h]
0x1801a94ed  mov     dword ptr [rsp+910h+lpMultiByteStr], eax
0x1801a94f1  mov     r9d, [rdi+94h]
0x1801a94f8  mov     r8, cs:off_180266010; "<SNIOpenSyncEx|API|SNI> pClientConsumer"...
0x1801a94ff  mov     edx, 0DC800h
0x1801a9504  mov     rcx, cs:off_180262840; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801a950b  call    _bidTraceW
0x1801a9510  xor     ebx, ebx
0x1801a9512  mov     r15d, ebx
0x1801a9515  mov     [rsp+910h+var_898], bl
0x1801a9519  xor     r12b, r12b
0x1801a951c  mov     [rsp+910h+var_8A0], rbx
0x1801a9521  mov     [rbp+810h+var_870], ebx
0x1801a9524  xor     edx, edx; Val
0x1801a9526  mov     r8d, 204h; Size
0x1801a952c  lea     rcx, [rbp+810h+var_86C]; void *
0x1801a9530  call    memset_0
0x1801a9535  mov     qword ptr [rsp+910h+var_8A8], rbx
0x1801a953a  call    cs:__imp_GetTickCount
0x1801a9540  mov     [rsp+910h+var_8B0], eax
0x1801a9544  mov     r13d, [rdi+94h]
0x1801a954b  cmp     dword ptr [rdi+68h], 4
0x1801a954f  jl      short loc_1801A955C
0x1801a9551  mov     r14d, 57h ; 'W'
0x1801a9557  jmp     loc_1801A9DFE
0x1801a955c  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x1801a9563  mov     rax, [rcx]
0x1801a9566  mov     edx, 0C20h
0x1801a956b  mov     rax, [rax+58h]
0x1801a956f  call    cs:__guard_dispatch_icall_fptr
0x1801a9575  mov     rsi, rax
0x1801a9578  test    rax, rax
0x1801a957b  jz      loc_1801A9D9F
0x1801a9581  mov     [rax], bx
0x1801a9584  mov     [rax+200h], bx
0x1801a958b  mov     [rax+400h], bx
0x1801a9592  mov     [rax+600h], bx
0x1801a9599  mov     [rax+616h], bx
0x1801a95a0  mov     [rax+816h], bx
0x1801a95a7  mov     dword ptr [rax+0C16h], 101h
0x1801a95b1  mov     dword ptr [rax+0C1Ch], 0FFFFFFFFh
0x1801a95bb  mov     rax, [rdi+60h]
0x1801a95bf  mov     [rsp+910h+var_8A0], rax
0x1801a95c4  lea     r9, [rdi+0B4h]
0x1801a95cb  mov     r8d, 104h
0x1801a95d1  lea     rdx, [rbp+810h+var_870]
0x1801a95d5  lea     rcx, [rsp+910h+var_8A0]
0x1801a95da  call    StartLocalDBInstanceIfLocalDB
0x1801a95df  mov     r14d, eax
0x1801a95e2  mov     rcx, rsi
0x1801a95e5  test    eax, eax
0x1801a95e7  jnz     loc_1801A9838
0x1801a95ed  movsxd  rbx, dword ptr [rdi+68h]
0x1801a95f1  lea     r14, ?g_rgwszPrefix@@3PAPEB_WA; wchar_t const * near * g_rgwszPrefix
0x1801a95f8  call    ImplBidTouch
0x1801a95fd  mov     r9, rax; struct __crt_locale_pointers *
0x1801a9600  mov     rax, [rsp+910h+var_8A0]
0x1801a9605  mov     qword ptr [rsp+910h+cbMultiByte], rax
0x1801a960a  mov     rax, [r14+rbx*8]
0x1801a960e  mov     [rsp+910h+lpMultiByteStr], rax
0x1801a9613  lea     r8, aSS_1; "%s%s"
0x1801a961a  mov     edx, 30Bh; unsigned __int64
0x1801a961f  lea     rcx, [rbp+810h+Buffer]; Buffer
0x1801a9626  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x1801a962b  test    eax, eax
0x1801a962d  jns     short loc_1801A9647
0x1801a962f  mov     r14d, 57h ; 'W'
0x1801a9635  mov     rcx, rsi; void *
0x1801a9638  mov     edx, 0C20h; unsigned __int64
0x1801a963d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801a9642  jmp     loc_1801A9DFE
0x1801a9647  mov     ecx, [rdi+0B0h]
0x1801a964d  movzx   eax, byte ptr [rdi+0ACh]
0x1801a9654  cmp     [rdi+98h], r15d
0x1801a965b  setnz   r8b; bool
0x1801a965f  mov     [rsi+0C19h], al
0x1801a9665  mov     [rsi+0C1Ch], ecx
0x1801a966b  lea     rdx, [rbp+810h+Buffer]; wchar_t *
0x1801a9672  mov     rcx, rsi; this
0x1801a9675  call    ?ParseConnectionString@ConnectParameter@@QEAAKPEB_W_N@Z; ConnectParameter::ParseConnectionString(wchar_t const *,bool)
0x1801a967a  mov     r14d, eax
0x1801a967d  mov     rcx, rsi
0x1801a9680  test    eax, eax
0x1801a9682  jnz     loc_1801A9838
0x1801a9688  cmp     [rsi+600h], r15w
0x1801a9690  jnz     short loc_1801A96AE
0x1801a9692  lea     r8, [rsi+200h]; wchar_t *
0x1801a9699  lea     r9, [rsp+910h+var_898]; bool *
0x1801a969e  mov     rdx, rsi; wchar_t *
0x1801a96a1  lea     rcx, [rsp+910h+var_8A8]; struct ProtList *
0x1801a96a6  call    ?GetProtocolList@@YAKPEAVProtList@@PEB_W1PEA_N@Z; GetProtocolList(ProtList *,wchar_t const *,wchar_t const *,bool *)
0x1801a96ab  mov     r15d, eax
0x1801a96ae  mov     ebx, 0FFFFFFFEh
0x1801a96b3  cmp     dword ptr [rdi+8Ch], 0
0x1801a96ba  jz      loc_1801A9744
0x1801a96c0  lea     rcx, [rsi+816h]; this
0x1801a96c7  call    ?RemoveEntry@LastConnectCache@@YAXPEB_W@Z; LastConnectCache::RemoveEntry(wchar_t const *)
0x1801a96cc  mov     [rsp+910h+var_897], r12b
0x1801a96d1  lea     r8, [rsp+910h+var_897]; bool *
0x1801a96d6  lea     rdx, [rsp+910h+var_8A8]; struct ProtList *
0x1801a96db  mov     rcx, rsi; this
0x1801a96de  call    ?MakeProtocolList@@YAKPEBVConnectParameter@@PEAVProtList@@PEA_N@Z; MakeProtocolList(ConnectParameter const *,ProtList *,bool *)
0x1801a96e3  mov     r14d, eax
0x1801a96e6  mov     rcx, rsi
0x1801a96e9  test    eax, eax
0x1801a96eb  jnz     loc_1801A9838
0x1801a96f1  mov     rbx, qword ptr [rsp+910h+var_8A8]
0x1801a96f6  test    rbx, rbx
0x1801a96f9  jnz     loc_1801A9847
0x1801a96ff  mov     ebx, 0C3CFh
0x1801a9704  mov     r14d, 0FFFFFFFFh
0x1801a970a  test    byte ptr cs:_bidGblFlags, 2
0x1801a9711  jz      loc_1801A9811
0x1801a9717  mov     rax, cs:off_180266028; "<SNIOpenSyncEx|ERR|SNI> ProviderNum: %d"...
0x1801a971e  test    rax, rax
0x1801a9721  jz      loc_1801A9811
0x1801a9727  test    r15d, r15d
0x1801a972a  jnz     loc_1801A97E3
0x1801a9730  xor     ecx, ecx
0x1801a9732  cmp     [rsp+910h+var_898], cl
0x1801a9736  setnz   cl
0x1801a9739  add     ecx, 0C3E1h
0x1801a973f  jmp     loc_1801A97E5
0x1801a9744  cmp     dword ptr [rdi+94h], 0FFFFFFFFh
0x1801a974b  jz      short loc_1801A97A3
0x1801a974d  call    cs:__imp_GetTickCount
0x1801a9753  mov     r13d, [rdi+94h]
0x1801a975a  add     r13d, [rsp+910h+var_8B0]
0x1801a975f  sub     r13d, eax
0x1801a9762  cmp     r13d, 0FFFFFFFFh
0x1801a9766  cmovz   r13d, ebx
0x1801a976a  mov     eax, cs:_bidGblFlags
0x1801a9770  and     eax, 20002h
0x1801a9775  cmp     eax, 20002h
0x1801a977a  jnz     short loc_1801A97A3
0x1801a977c  mov     rax, cs:off_180266020; "<SNIOpenSyncEx|SNI> timeout(0): %d\n"
0x1801a9783  test    rax, rax
0x1801a9786  jz      short loc_1801A97A3
0x1801a9788  mov     r9d, r13d
0x1801a978b  mov     r8, cs:off_180266020; "<SNIOpenSyncEx|SNI> timeout(0): %d\n"
0x1801a9792  mov     edx, 0F8800h
0x1801a9797  mov     rcx, cs:off_180262850; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801a979e  call    _bidTraceW
0x1801a97a3  cmp     byte ptr [rsi+0C16h], 1
0x1801a97aa  jnz     loc_1801A96CC
0x1801a97b0  mov     dword ptr [rsp+910h+lpMultiByteStr], r13d; int
0x1801a97b5  mov     r9, [rbp+810h+var_888]; struct SNI_Conn **
0x1801a97b9  mov     r8, rdi; struct SNI_CLIENT_CONSUMER_INFO *
0x1801a97bc  lea     rdx, [rsp+910h+var_8A8]; struct ProtList *
0x1801a97c1  mov     rcx, rsi; struct ConnectParameter *
0x1801a97c4  call    ?ConnectUsingCache@@YA_NPEAVConnectParameter@@PEAVProtList@@PEAUSNI_CLIENT_CONSUMER_INFO@@PEAPEAVSNI_Conn@@H@Z; ConnectUsingCache(ConnectParameter *,ProtList *,SNI_CLIENT_CONSUMER_INFO *,SNI_Conn * *,int)
0x1801a97c9  cmp     al, 1
0x1801a97cb  jnz     loc_1801A96CC
0x1801a97d1  xor     r15d, r15d
0x1801a97d4  mov     r14d, r15d
0x1801a97d7  mov     r12, rsi
0x1801a97da  mov     [rbp+810h+var_890], rsi
0x1801a97de  jmp     loc_1801A9C9D
0x1801a97e3  mov     ecx, ebx; unsigned int
0x1801a97e5  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1801a97ea  mov     [rsp+910h+cbMultiByte], r14d
0x1801a97ef  mov     dword ptr [rsp+910h+lpMultiByteStr], eax
0x1801a97f3  mov     r9d, 8
0x1801a97f9  mov     r8, cs:off_180266028; "<SNIOpenSyncEx|ERR|SNI> ProviderNum: %d"...
0x1801a9800  mov     edx, 102800h
0x1801a9805  mov     rcx, cs:off_180262858; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801a980c  call    _bidTraceW
0x1801a9811  test    r15d, r15d
0x1801a9814  jnz     short loc_1801A9825
0x1801a9816  xor     ebx, ebx
0x1801a9818  cmp     [rsp+910h+var_898], bl
0x1801a981c  setnz   bl
0x1801a981f  add     ebx, 0C3E1h
0x1801a9825  mov     r8d, ebx
0x1801a9828  mov     edx, r14d
0x1801a982b  mov     ecx, 8
0x1801a9830  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1801a9835  mov     rcx, rsi; void *
0x1801a9838  mov     edx, 0C20h; unsigned __int64
0x1801a983d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801a9842  jmp     loc_1801A9DFE
0x1801a9847  cmp     dword ptr [rbx], 3
0x1801a984a  jnz     loc_1801A9944
0x1801a9850  cmp     dword ptr [rdi+94h], 0FFFFFFFFh
0x1801a9857  jz      short loc_1801A98B4
0x1801a9859  call    cs:__imp_GetTickCount
0x1801a985f  mov     r13d, [rdi+94h]
0x1801a9866  add     r13d, [rsp+910h+var_8B0]
0x1801a986b  sub     r13d, eax
0x1801a986e  cmp     r13d, 0FFFFFFFFh
0x1801a9872  mov     eax, 0FFFFFFFEh
0x1801a9877  cmovz   r13d, eax
0x1801a987b  mov     eax, cs:_bidGblFlags
0x1801a9881  and     eax, 20002h
0x1801a9886  cmp     eax, 20002h
0x1801a988b  jnz     short loc_1801A98B4
0x1801a988d  mov     rax, cs:off_180266030; "<SNIOpenSyncEx|SNI> timeout(1): %d\n"
0x1801a9894  test    rax, rax
0x1801a9897  jz      short loc_1801A98B4
0x1801a9899  mov     r9d, r13d
0x1801a989c  mov     r8, cs:off_180266030; "<SNIOpenSyncEx|SNI> timeout(1): %d\n"
0x1801a98a3  mov     edx, 10B000h
0x1801a98a8  mov     rcx, cs:off_180262860; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801a98af  call    _bidTraceW
0x1801a98b4  cmp     dword ptr [rbx], 6
0x1801a98b7  jnz     short loc_1801A98D2
0x1801a98b9  movzx   eax, byte ptr [rsi+0C19h]
0x1801a98c0  mov     [rbx+809h], al
0x1801a98c6  mov     eax, [rsi+0C1Ch]
0x1801a98cc  mov     [rbx+80Ch], eax
0x1801a98d2  mov     dword ptr [rsp+910h+lpMultiByteStr], r13d; int
0x1801a98d7  mov     r15, [rbp+810h+var_888]
0x1801a98db  mov     r9, r15; struct SNI_Conn **
0x1801a98de  mov     r8, rbx; struct ProtElem *
0x1801a98e1  mov     rdx, rdi; struct SNI_CLIENT_CONSUMER_INFO *
0x1801a98e4  mov     rcx, rsi; struct ConnectParameter *
0x1801a98e7  call    ?Connect@@YAKPEAVConnectParameter@@PEAUSNI_CLIENT_CONSUMER_INFO@@PEAVProtElem@@PEAPEAVSNI_Conn@@H@Z; Connect(ConnectParameter *,SNI_CLIENT_CONSUMER_INFO *,ProtElem *,SNI_Conn * *,int)
0x1801a98ec  mov     r14d, eax
0x1801a98ef  test    eax, eax
0x1801a98f1  jnz     short loc_1801A991E
0x1801a98f3  mov     r12, rsi
0x1801a98f6  mov     [rbp+810h+var_890], rsi
0x1801a98fa  cmp     [rsi+0C16h], al
0x1801a9900  jz      loc_1801A9C9A
0x1801a9906  lea     rcx, [rsi+816h]; this
0x1801a990d  mov     rdx, rbx; wchar_t *
0x1801a9910  call    ?SetEntry@LastConnectCache@@YAXPEB_WPEAVProtElem@@@Z; LastConnectCache::SetEntry(wchar_t const *,ProtElem *)
0x1801a9915  mov     [rbp+810h+var_890], rsi
0x1801a9919  jmp     loc_1801A9C9A
0x1801a991e  mov     r12b, 1
0x1801a9921  lea     rcx, [rsp+910h+var_8A8]; this
0x1801a9926  call    ?RemoveFirst@ProtList@@QEAAPEAVProtElem@@XZ; ProtList::RemoveFirst(void)
0x1801a992b  test    rax, rax
0x1801a992e  jz      short loc_1801A993D
0x1801a9930  mov     edx, 0A10h; unsigned __int64
  ... truncated ...
```
