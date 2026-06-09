# SNIOpenSyncEx

- ea: `0x10043d748`
- end: `0x10043e12b`
- name: `SNIOpenSyncEx`
- size: `2531`
- prototype: `__int64 __fastcall(struct SNI_CLIENT_CONSUMER_INFO *)`
- caller_count: `1`
- callee_count: `26`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1004670d4`

## callees

- `0x100405948`
- `0x1004134a0`
- `0x10041470c`
- `0x1004165dc`
- `0x10043a7c4`
- `0x10043a930`
- `0x10043c498`
- `0x10043c684`
- `0x10043ca50`
- `0x10043cba8`
- `0x10043d260`
- `0x10043d334`
- `0x10043d748`
- `0x10043ebd8`
- `0x10043f328`
- `0x10043f424`
- `0x10043f9dc`
- `0x100441a7c`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x100546af8`
- `0x100548140`
- `0x100548210`
- `0x1005494b8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10043e019`
- `KERNEL32!GetLastError` at `0x10043e019`
- `KERNEL32!GetTickCount` at `0x10043d8a9`
- `KERNEL32!GetTickCount` at `0x10043daee`
- `KERNEL32!GetTickCount` at `0x10043dba2`
- `KERNEL32!GetTickCount` at `0x10043dd6d`
- `KERNEL32!GetTickCount` at `0x10043d8a9`
- `KERNEL32!GetTickCount` at `0x10043daee`
- `KERNEL32!GetTickCount` at `0x10043dba2`
- `KERNEL32!GetTickCount` at `0x10043dd6d`
- `KERNEL32!WideCharToMultiByte` at `0x10043dfbb`
- `KERNEL32!WideCharToMultiByte` at `0x10043dff8`
- `KERNEL32!WideCharToMultiByte` at `0x10043dfbb`
- `KERNEL32!WideCharToMultiByte` at `0x10043dff8`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x10043de59`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x10043de59`

## pseudocode

```c
__int64 __fastcall SNIOpenSyncEx(struct SNI_CLIENT_CONSUMER_INFO *a1, struct SNI_Conn **a2)
{
  unsigned int ProtocolList; // r13d
  DWORD TickCount; // eax
  bool v5; // cc
  unsigned int v6; // r15d
  unsigned int started; // esi
  __int64 v8; // rax
  __int64 v9; // r14
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r12
  __int64 v13; // rbx
  struct __crt_locale_pointers *v14; // rax
  char v15; // al
  char v16; // r8
  const unsigned __int16 *v17; // rdx
  DWORD v18; // ebx
  unsigned int v19; // eax
  struct ProtList *v20; // r9
  struct ProtElem *v21; // r15
  unsigned int v22; // edi
  unsigned int v23; // ecx
  DWORD v24; // eax
  struct SNI_Conn **v25; // r15
  __int64 v26; // r13
  DWORD v27; // eax
  DWORD v28; // ecx
  unsigned int v29; // ebx
  unsigned int v30; // ecx
  char v31; // bl
  struct ProtElem *v32; // r8
  unsigned int Info; // eax
  unsigned int v34; // ebx
  unsigned int v35; // edi
  __int64 v36; // rdx
  unsigned int v37; // esi
  DWORD v38; // ecx
  unsigned int v39; // eax
  int v40; // eax
  unsigned __int16 *v41; // r9
  __int64 v42; // r8
  __int64 v43; // rdx
  __int64 cbMultiByte; // rbx
  int v45; // eax
  struct SNI_Conn *v46; // rbx
  int lpMultiByteStr; // [rsp+20h] [rbp-E0h]
  bool v49; // [rsp+60h] [rbp-A0h] BYREF
  bool v50; // [rsp+62h] [rbp-9Eh] BYREF
  unsigned __int16 v51; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v52; // [rsp+68h] [rbp-98h]
  struct ProtElem *v53; // [rsp+70h] [rbp-90h] BYREF
  struct SNI_Conn **v54; // [rsp+78h] [rbp-88h]
  DWORD v55; // [rsp+80h] [rbp-80h]
  __int64 v56; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v57[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v58[528]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SrcStr[784]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v54 = a2;
  v57[0] = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7EF8[0] )
    bidScopeEnterW(v57, off_1005E7EF8[0], a1);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5EC0[0] )
    bidTraceW(0, 786432, off_1005E5EC0[0], *((unsigned int *)a1 + 41));
  v49 = 0;
  ProtocolList = 0;
  memset_0(v58, 0, 0x208u);
  v53 = 0;
  TickCount = GetTickCount();
  v5 = *((_DWORD *)a1 + 30) < 4;
  v6 = *((_DWORD *)a1 + 41);
  v55 = TickCount;
  v52 = v6;
  if ( v5 )
  {
    v8 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 3108);
    v9 = v8;
    if ( !v8 )
    {
      started = 14;
      if ( (bidGblFlags & 2) != 0 && off_1005E5EC8[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceW(0, 815104, off_1005E5EC8[0], 9);
      }
      SNISetLastError(9, 14, 50100);
      goto LABEL_115;
    }
    *(_WORD *)v8 = 0;
    *(_WORD *)(v8 + 512) = 0;
    *(_WORD *)(v8 + 1024) = 0;
    *(_WORD *)(v8 + 1536) = 0;
    *(_WORD *)(v8 + 1558) = 0;
    *(_WORD *)(v8 + 2070) = 0;
    *(_DWORD *)(v8 + 3094) = 257;
    *(_DWORD *)(v8 + 3100) = -1;
    *(_DWORD *)(v8 + 3104) = 2;
    v56 = *((_QWORD *)a1 + 13);
    started = StartLocalDBInstanceIfLocalDB(&v56, v58, 260);
    v12 = v9;
    if ( started )
      goto LABEL_110;
    v13 = *((int *)a1 + 30);
    v14 = (struct __crt_locale_pointers *)ImplBidTouch(v10);
    if ( (int)StringCchPrintf_lW(SrcStr, 0x30Bu, L"%s%s", v14, (&g_rgwszPrefix)[v13], v56) < 0 )
    {
      started = 87;
LABEL_110:
      ((void (__fastcall *)(struct IMalloc *, __int64, __int64))g_pMO->lpVtbl[1].Realloc)(g_pMO, v12, v11);
      goto LABEL_115;
    }
    v15 = *((_BYTE *)a1 + 172);
    v16 = *((_DWORD *)a1 + 42) != 0;
    *(_DWORD *)(v9 + 3100) = *((_DWORD *)a1 + 44);
    *(_BYTE *)(v9 + 3097) = v15;
    started = ConnectParameter::ParseConnectionString((WCHAR *)v9, SrcStr, v16);
    if ( started )
      goto LABEL_110;
    if ( !*(_WORD *)(v9 + 1536) )
      ProtocolList = GetProtocolList(
                       (struct ProtList *)&v53,
                       (const unsigned __int16 *)v9,
                       (const unsigned __int16 *)(v9 + 512),
                       &v49);
    if ( *((_DWORD *)a1 + 39) )
    {
      LastConnectCache::RemoveEntry((LastConnectCache *)(v9 + 2070), v17);
      v18 = v55;
    }
    else
    {
      if ( *((_DWORD *)a1 + 41) == -1 )
      {
        v18 = v55;
      }
      else
      {
        v24 = GetTickCount();
        v6 = -2;
        v18 = v55;
        if ( v55 + *((_DWORD *)a1 + 41) - v24 != -1 )
          v6 = v55 + *((_DWORD *)a1 + 41) - v24;
        v52 = v6;
        if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5ED0[0] )
          bidTraceW(0, 898048, off_1005E5ED0[0], v6);
      }
      if ( *(_BYTE *)(v9 + 3094) == 1 )
      {
        lpMultiByteStr = v6;
        v25 = v54;
        if ( ConnectUsingCache((struct ConnectParameter *)v9, (struct ProtList *)&v53, a1, v54, lpMultiByteStr) == 1 )
        {
          v26 = v9;
          started = 0;
          goto LABEL_100;
        }
      }
    }
    v19 = MakeProtocolList((const struct ConnectParameter *)v9, (struct ProtList *)&v53, &v50);
    v11 = 0;
    started = v19;
    if ( v19 )
      goto LABEL_110;
    v21 = v53;
    if ( !v53 )
    {
      v22 = 50127;
      started = -1;
      if ( (bidGblFlags & 2) != 0 && off_1005E5ED8[0] )
      {
        v23 = 50127;
        if ( !ProtocolList )
          v23 = v49 + 50145;
        SniErrorIdFromStringId(v23);
        bidTraceW(0, 942080, off_1005E5ED8[0], 9);
      }
      if ( !ProtocolList )
        v22 = v49 + 50145;
      SNISetLastError(9, 0xFFFFFFFFLL, v22);
      v12 = v9;
      goto LABEL_110;
    }
    if ( *(_DWORD *)v53 == 4 )
    {
      if ( *((_DWORD *)a1 + 41) == -1 )
      {
        v29 = v52;
      }
      else
      {
        v27 = GetTickCount();
        v28 = v18 + *((_DWORD *)a1 + 41);
        v29 = -2;
        v30 = v28 - v27;
        if ( v30 != -1 )
          v29 = v30;
        v52 = v29;
        if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5EE0[0] )
          bidTraceW(0, 976896, off_1005E5EE0[0], v29);
      }
      started = Connect((struct ConnectParameter *)v9, a1, v21, v54, v29);
      if ( !started )
      {
        v26 = v9;
LABEL_48:
        if ( *(_BYTE *)(v9 + 3094) )
          LastConnectCache::SetEntry((LastConnectCache *)(v9 + 2070), (const unsigned __int16 *)v21, 0);
LABEL_99:
        v25 = v54;
LABEL_100:
        if ( !*(_BYTE *)(v26 + 3095) )
          goto LABEL_108;
        cbMultiByte = -1;
        do
          ++cbMultiByte;
        while ( *(_WORD *)(v26 + 2 * cbMultiByte + 1024) );
        if ( (_DWORD)cbMultiByte )
        {
          if ( (unsigned int)(WideCharToMultiByte(0, 0, (LPCWCH)(v26 + 1024), cbMultiByte, 0, 0, 0, 0) - 1) > 0xFC
            || (_mm_lfence(),
                v45 = WideCharToMultiByte(
                        0,
                        0,
                        (LPCWCH)(v26 + 1024),
                        cbMultiByte,
                        *((LPSTR *)a1 + 18),
                        cbMultiByte,
                        0,
                        0),
                (unsigned int)(v45 - 1) > 0xFC) )
          {
            started = GetLastError();
            goto LABEL_118;
          }
          *(_BYTE *)(v45 + *((_QWORD *)a1 + 18)) = 0;
        }
        else
        {
LABEL_108:
          *((_QWORD *)a1 + 18) = qword_100558430;
        }
        v46 = *v25;
        *((_DWORD *)v46 + 12) = bidUpdateItemIDA(*((unsigned int *)*v25 + 12), off_1005E42A0, *((_QWORD *)a1 + 13));
        goto LABEL_110;
      }
      v31 = 1;
      v32 = ProtList::RemoveFirst((ProtList *)&v53);
      if ( v32 )
        ((void (__fastcall *)(struct IMalloc *, struct ProtElem *))g_pMO->lpVtbl[1].Realloc)(g_pMO, v32);
      v21 = v53;
      v11 = 0;
    }
    else
    {
      v31 = 0;
    }
    if ( v50 )
    {
      Info = SSRP::SsrpGetInfo((LPCWCH)v9, (LPCWCH)(v9 + 1024), (unsigned __int16 *)&v53, v20);
      v11 = 0;
      started = Info;
      if ( Info )
      {
        v34 = 9;
        v35 = 50126;
        if ( (bidGblFlags & 2) != 0 && off_1005E5EE8[0] )
        {
          SniErrorIdFromStringId(0xC3CEu);
          bidTraceW(0, 1014784, off_1005E5EE8[0], 9);
        }
        v36 = started;
        goto LABEL_66;
      }
      v21 = v53;
      if ( !v53 )
      {
        started = -1;
        if ( v31 )
          goto LABEL_110;
        v34 = (_DWORD)v53 + 9;
        v35 = 50128;
        if ( (bidGblFlags & 2) != 0 && off_1005E5EF0[0] )
        {
          SniErrorIdFromStringId(0xC3D0u);
          bidTraceW(0, 1032192, off_1005E5EF0[0], v34);
        }
        v36 = 0xFFFFFFFFLL;
LABEL_66:
        SNISetLastError(v34, v36, v35);
        goto LABEL_110;
      }
    }
    else if ( !v21 )
    {
      v26 = v9;
      if ( started )
        goto LABEL_110;
      goto LABEL_99;
    }
    v26 = v9;
    while ( 1 )
    {
      if ( *((_DWORD *)a1 + 41) == -1 )
      {
        v37 = v52;
      }
      else
      {
        v37 = -2;
        v38 = v55 + *((_DWORD *)a1 + 41) - GetTickCount();
        if ( v38 != -1 )
          v37 = v38;
        v52 = v37;
        if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5EF8[0] )
          bidTraceW(0, 1051648, off_1005E5EF8[0], v37);
      }
      if ( *(_DWORD *)v21 == 7 )
      {
        *((_BYTE *)v21 + 2057) = *(_BYTE *)(v9 + 3097);
        *((_DWORD *)v21 + 515) = *(_DWORD *)(v9 + 3100);
        *((_DWORD *)v21 + 516) = *((_DWORD *)a1 + 47);
      }
      v39 = Connect((struct ConnectParameter *)v9, a1, v21, v54, v37);
      v11 = 0;
      started = v39;
      if ( !v39 )
        goto LABEL_48;
      if ( !g_fSandbox )
      {
        v40 = wcscmp_0(L"admin", (const wchar_t *)(v9 + 1536));
        v11 = 0;
        if ( !v40 && !*(_WORD *)(v9 + 1024) && _wtoi((const wchar_t *)v21 + 772) == 1434 )
        {
          if ( SSRP::GetAdminPort((SSRP *)v9, L"MSSQLServer", &v51, v41) )
          {
            if ( v51 != 1434 )
            {
              StringCchPrintfW((unsigned __int16 *)v21 + 772, 0x100u, L"%d", v51);
              *((_BYTE *)v21 + 2058) = 1;
              goto LABEL_95;
            }
            if ( (bidGblFlags & 2) != 0 && off_1005E5F08[0] )
            {
              SniErrorIdFromStringId(0xC3DEu);
              bidTraceW(0, 1102848, off_1005E5F08[0], 9);
            }
            v42 = 50142;
            v43 = started;
          }
          else
          {
            if ( (bidGblFlags & 2) != 0 && off_1005E5F00[0] )
            {
              SniErrorIdFromStringId(0xC3DFu);
              bidTraceW(0, 1095680, off_1005E5F00[0], 9);
            }
            v42 = 50143;
            v43 = 0xFFFFFFFFLL;
          }
          SNISetLastError(9, v43, v42);
        }
      }
      v21 = (struct ProtElem *)*((_QWORD *)v21 + 321);
LABEL_95:
      if ( !v21 )
        goto LABEL_110;
    }
  }
  started = 87;
LABEL_115:
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5F10[0] )
    bidTraceW(0, 1176576, off_1005E5F10[0], started);
LABEL_118:
  ProtList::DeleteAll((ProtList *)&v53);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v57);
  return started;
}

```

## disassembly

```asm
0x10043d748  mov     [rsp-8+arg_10], rbx
0x10043d74d  push    rbp
0x10043d74e  push    rsi
0x10043d74f  push    rdi
0x10043d750  push    r12
0x10043d752  push    r13
0x10043d754  push    r14
0x10043d756  push    r15
0x10043d758  lea     rbp, [rsp-7E0h]
0x10043d760  sub     rsp, 8E0h
0x10043d767  mov     rax, cs:__security_cookie
0x10043d76e  xor     rax, rsp
0x10043d771  mov     [rbp+810h+var_40], rax
0x10043d778  mov     eax, cs:_bidGblFlags
0x10043d77e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x10043d782  mov     rdi, rcx
0x10043d785  mov     [rsp+910h+var_898], rdx
0x10043d78a  mov     ecx, 20004h
0x10043d78f  mov     [rbp+810h+var_880], rbx
0x10043d793  and     eax, ecx
0x10043d795  xor     r12d, r12d
0x10043d798  cmp     eax, ecx
0x10043d79a  jnz     short loc_10043D80E
0x10043d79c  mov     rax, cs:off_1005E7EF8; "<SNIOpenSyncEx|API|SNI> pClientConsumer"...
0x10043d7a3  test    rax, rax
0x10043d7a6  jz      short loc_10043D80E
0x10043d7a8  mov     eax, [rdi+0A0h]
0x10043d7ae  lea     rcx, [rbp+810h+var_880]
0x10043d7b2  mov     dword ptr [rsp+910h+var_8B8], eax
0x10043d7b6  mov     r9, rdx
0x10043d7b9  mov     eax, [rdi+9Ch]
0x10043d7bf  mov     r8, rdi
0x10043d7c2  mov     rdx, cs:off_1005E7EF8; "<SNIOpenSyncEx|API|SNI> pClientConsumer"...
0x10043d7c9  mov     dword ptr [rsp+910h+var_8C0], eax
0x10043d7cd  mov     eax, [rdi+98h]
0x10043d7d3  mov     dword ptr [rsp+910h+var_8C8], eax
0x10043d7d7  mov     rax, [rdi+90h]
0x10043d7de  mov     [rsp+910h+var_8D0], rax
0x10043d7e3  mov     eax, [rdi+88h]
0x10043d7e9  mov     dword ptr [rsp+910h+lpUsedDefaultChar], eax
0x10043d7ed  mov     rax, [rdi+80h]
0x10043d7f4  mov     [rsp+910h+lpDefaultChar], rax
0x10043d7f9  mov     eax, [rdi+78h]
0x10043d7fc  mov     [rsp+910h+cbMultiByte], eax
0x10043d800  mov     rax, [rdi+68h]
0x10043d804  mov     [rsp+910h+lpMultiByteStr], rax
0x10043d809  call    _bidScopeEnterW
0x10043d80e  mov     eax, cs:_bidGblFlags
0x10043d814  mov     ecx, 20002h
0x10043d819  and     eax, ecx
0x10043d81b  cmp     eax, ecx
0x10043d81d  jnz     short loc_10043D88B
0x10043d81f  mov     rax, cs:off_1005E5EC0; "<SNIOpenSyncEx|API|SNI> pClientConsumer"...
0x10043d826  test    rax, rax
0x10043d829  jz      short loc_10043D88B
0x10043d82b  mov     rax, [rdi+30h]
0x10043d82f  mov     edx, 0C0000h
0x10043d834  mov     r9d, [rdi+0A4h]
0x10043d83b  xor     ecx, ecx
0x10043d83d  mov     r8, cs:off_1005E5EC0; "<SNIOpenSyncEx|API|SNI> pClientConsumer"...
0x10043d844  mov     [rsp+910h+var_8B8], rax
0x10043d849  mov     rax, [rdi+28h]
0x10043d84d  mov     [rsp+910h+var_8C0], rax
0x10043d852  mov     rax, [rdi+20h]
0x10043d856  mov     [rsp+910h+var_8C8], rax
0x10043d85b  mov     rax, [rdi+18h]
0x10043d85f  mov     [rsp+910h+var_8D0], rax
0x10043d864  mov     rax, [rdi+10h]
0x10043d868  mov     [rsp+910h+lpUsedDefaultChar], rax
0x10043d86d  mov     rax, [rdi+8]
0x10043d871  mov     [rsp+910h+lpDefaultChar], rax
0x10043d876  mov     eax, [rdi]
0x10043d878  mov     [rsp+910h+cbMultiByte], eax
0x10043d87c  mov     eax, [rdi+0A8h]
0x10043d882  mov     dword ptr [rsp+910h+lpMultiByteStr], eax
0x10043d886  call    _bidTraceW
0x10043d88b  xor     edx, edx; Val
0x10043d88d  mov     [rsp+910h+var_8B0], r12b
0x10043d892  mov     r8d, 208h; Size
0x10043d898  lea     rcx, [rbp+810h+var_870]; void *
0x10043d89c  mov     r13d, r12d
0x10043d89f  call    memset_0
0x10043d8a4  mov     [rsp+910h+var_8A0], r12
0x10043d8a9  call    cs:__imp_GetTickCount
0x10043d8af  cmp     dword ptr [rdi+78h], 4
0x10043d8b3  mov     r15d, [rdi+0A4h]
0x10043d8ba  mov     [rbp+810h+var_890], eax
0x10043d8bd  mov     [rsp+910h+var_8A8], r15d
0x10043d8c2  jl      short loc_10043D8CE
0x10043d8c4  mov     esi, 57h ; 'W'
0x10043d8c9  jmp     loc_10043E0B9
0x10043d8ce  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x10043d8d5  mov     edx, 0C24h
0x10043d8da  mov     rax, [rcx]
0x10043d8dd  mov     rax, [rax+58h]
0x10043d8e1  call    cs:__guard_dispatch_icall_fptr
0x10043d8e7  mov     r14, rax
0x10043d8ea  test    rax, rax
0x10043d8ed  jz      loc_10043E066
0x10043d8f3  mov     [rax], r12w
0x10043d8f7  lea     rdx, [rbp+810h+var_870]
0x10043d8fb  mov     [rax+200h], r12w
0x10043d903  lea     rcx, [rbp+810h+var_888]
0x10043d907  mov     [rax+400h], r12w
0x10043d90f  mov     r8d, 104h
0x10043d915  mov     [rax+600h], r12w
0x10043d91d  mov     [rax+616h], r12w
0x10043d925  mov     [rax+816h], r12w
0x10043d92d  mov     dword ptr [rax+0C16h], 101h
0x10043d937  mov     [rax+0C1Ch], ebx
0x10043d93d  mov     dword ptr [rax+0C20h], 2
0x10043d947  mov     rax, [rdi+68h]
0x10043d94b  mov     [rbp+810h+var_888], rax
0x10043d94f  call    StartLocalDBInstanceIfLocalDB
0x10043d954  mov     esi, eax
0x10043d956  mov     r12, r14
0x10043d959  test    eax, eax
0x10043d95b  jnz     loc_10043E04D
0x10043d961  movsxd  rbx, dword ptr [rdi+78h]
0x10043d965  lea     rsi, ?g_rgwszPrefix@@3PAPEBGA; ushort const * near * g_rgwszPrefix
0x10043d96c  call    ImplBidTouch
0x10043d971  mov     r9, rax; struct __crt_locale_pointers *
0x10043d974  lea     r8, aSS_4; "%s%s"
0x10043d97b  mov     rax, [rbp+810h+var_888]
0x10043d97f  lea     rcx, [rbp+810h+SrcStr]; unsigned __int16 *
0x10043d986  mov     qword ptr [rsp+910h+cbMultiByte], rax
0x10043d98b  mov     edx, 30Bh; unsigned __int64
0x10043d990  mov     rax, [rsi+rbx*8]
0x10043d994  mov     [rsp+910h+lpMultiByteStr], rax
0x10043d999  call    ?StringCchPrintf_lW@@YAJPEAG_KPEBGPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(ushort *,unsigned __int64,ushort const *,__crt_locale_pointers *,...)
0x10043d99e  xor     ebx, ebx
0x10043d9a0  test    eax, eax
0x10043d9a2  jns     short loc_10043D9AC
0x10043d9a4  lea     esi, [rbx+57h]
0x10043d9a7  jmp     loc_10043E04D
0x10043d9ac  cmp     [rdi+0A8h], ebx
0x10043d9b2  lea     rdx, [rbp+810h+SrcStr]; lpSrcStr
0x10043d9b9  mov     ecx, [rdi+0B0h]
0x10043d9bf  mov     al, [rdi+0ACh]
0x10043d9c5  setnz   r8b; bool
0x10043d9c9  mov     [r14+0C1Ch], ecx
0x10043d9d0  mov     rcx, r14; lpString2
0x10043d9d3  mov     [r14+0C19h], al
0x10043d9da  call    ?ParseConnectionString@ConnectParameter@@QEAAKPEBG_N@Z; ConnectParameter::ParseConnectionString(ushort const *,bool)
0x10043d9df  mov     esi, eax
0x10043d9e1  test    eax, eax
0x10043d9e3  jnz     loc_10043E04D
0x10043d9e9  cmp     [r14+600h], bx
0x10043d9f1  jnz     short loc_10043DA0F
0x10043d9f3  lea     r8, [r14+200h]; unsigned __int16 *
0x10043d9fa  mov     rdx, r14; unsigned __int16 *
0x10043d9fd  lea     r9, [rsp+910h+var_8B0]; bool *
0x10043da02  lea     rcx, [rsp+910h+var_8A0]; this
0x10043da07  call    ?GetProtocolList@@YAKPEAVProtList@@PEBG1PEA_N@Z; GetProtocolList(ProtList *,ushort const *,ushort const *,bool *)
0x10043da0c  mov     r13d, eax
0x10043da0f  or      esi, 0FFFFFFFFh
0x10043da12  cmp     [rdi+9Ch], ebx
0x10043da18  jz      loc_10043DAE6
0x10043da1e  lea     rcx, [r14+816h]; this
0x10043da25  call    ?RemoveEntry@LastConnectCache@@YAXPEBG@Z; LastConnectCache::RemoveEntry(ushort const *)
0x10043da2a  mov     ebx, [rbp+810h+var_890]
0x10043da2d  lea     r8, [rsp+910h+var_8AE]; bool *
0x10043da32  mov     rcx, r14; this
0x10043da35  lea     rdx, [rsp+910h+var_8A0]; struct ProtList *
0x10043da3a  call    ?MakeProtocolList@@YAKPEBVConnectParameter@@PEAVProtList@@PEA_N@Z; MakeProtocolList(ConnectParameter const *,ProtList *,bool *)
0x10043da3f  xor     r8d, r8d
0x10043da42  mov     esi, eax
0x10043da44  test    eax, eax
0x10043da46  jnz     loc_10043E04D
0x10043da4c  mov     r15, [rsp+910h+var_8A0]
0x10043da51  test    r15, r15
0x10043da54  jnz     loc_10043DB8B
0x10043da5a  or      r15d, 0FFFFFFFFh
0x10043da5e  lea     ebx, [rax+9]
0x10043da61  test    byte ptr cs:_bidGblFlags, 2
0x10043da68  mov     edi, 0C3CFh
0x10043da6d  mov     esi, r15d
0x10043da70  lea     r12d, [rdi+12h]
0x10043da74  jz      short loc_10043DABB
0x10043da76  mov     rax, cs:off_1005E5ED8; "<SNIOpenSyncEx|ERR|SNI> ProviderNum: %d"...
0x10043da7d  test    rax, rax
0x10043da80  jz      short loc_10043DABB
0x10043da82  mov     al, [rsp+910h+var_8B0]
0x10043da86  mov     ecx, edi
0x10043da88  neg     al
0x10043da8a  sbb     edx, edx
0x10043da8c  neg     edx
0x10043da8e  add     edx, r12d
0x10043da91  test    r13d, r13d
0x10043da94  cmovz   ecx, edx; unsigned int
0x10043da97  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10043da9c  mov     r8, cs:off_1005E5ED8; "<SNIOpenSyncEx|ERR|SNI> ProviderNum: %d"...
0x10043daa3  mov     r9d, ebx
0x10043daa6  mov     edx, 0E6000h
0x10043daab  mov     [rsp+910h+cbMultiByte], r15d
0x10043dab0  xor     ecx, ecx
0x10043dab2  mov     dword ptr [rsp+910h+lpMultiByteStr], eax
0x10043dab6  call    _bidTraceW
0x10043dabb  mov     al, [rsp+910h+var_8B0]
0x10043dabf  mov     edx, r15d
0x10043dac2  neg     al
0x10043dac4  mov     ecx, ebx
0x10043dac6  sbb     r9d, r9d
0x10043dac9  neg     r9d
0x10043dacc  add     r9d, r12d
0x10043dacf  test    r13d, r13d
0x10043dad2  cmovz   edi, r9d
0x10043dad6  mov     r8d, edi
0x10043dad9  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043dade  mov     r12, r14
0x10043dae1  jmp     loc_10043E04D
0x10043dae6  cmp     [rdi+0A4h], esi
0x10043daec  jz      short loc_10043DB47
0x10043daee  call    cs:__imp_GetTickCount
0x10043daf4  mov     ecx, [rdi+0A4h]
0x10043dafa  mov     r15d, 0FFFFFFFEh
0x10043db00  mov     ebx, [rbp+810h+var_890]
0x10043db03  add     ecx, ebx
0x10043db05  sub     ecx, eax
0x10043db07  mov     eax, cs:_bidGblFlags
0x10043db0d  cmp     ecx, esi
0x10043db0f  cmovnz  r15d, ecx
0x10043db13  mov     ecx, 20002h
0x10043db18  and     eax, ecx
0x10043db1a  mov     [rsp+910h+var_8A8], r15d
0x10043db1f  cmp     eax, ecx
0x10043db21  jnz     short loc_10043DB4A
0x10043db23  mov     rax, cs:off_1005E5ED0; "<SNIOpenSyncEx|SNI> timeout(0): %d\n"
0x10043db2a  xor     ecx, ecx
0x10043db2c  test    rax, rax
0x10043db2f  jz      short loc_10043DB4A
0x10043db31  mov     r8, cs:off_1005E5ED0; "<SNIOpenSyncEx|SNI> timeout(0): %d\n"
0x10043db38  mov     r9d, r15d
0x10043db3b  mov     edx, 0DB400h
0x10043db40  call    _bidTraceW
0x10043db45  jmp     short loc_10043DB4A
0x10043db47  mov     ebx, [rbp+810h+var_890]
0x10043db4a  cmp     byte ptr [r14+0C16h], 1
0x10043db52  jnz     loc_10043DA2D
0x10043db58  mov     dword ptr [rsp+910h+lpMultiByteStr], r15d; int
0x10043db5d  lea     rdx, [rsp+910h+var_8A0]; struct ProtList *
0x10043db62  mov     r15, [rsp+910h+var_898]
0x10043db67  mov     r8, rdi; struct SNI_CLIENT_CONSUMER_INFO *
0x10043db6a  mov     r9, r15; struct SNI_Conn **
0x10043db6d  mov     rcx, r14; struct ConnectParameter *
0x10043db70  call    ?ConnectUsingCache@@YA_NPEAVConnectParameter@@PEAVProtList@@PEAUSNI_CLIENT_CONSUMER_INFO@@PEAPEAVSNI_Conn@@H@Z; ConnectUsingCache(ConnectParameter *,ProtList *,SNI_CLIENT_CONSUMER_INFO *,SNI_Conn * *,int)
0x10043db75  cmp     al, 1
0x10043db77  jnz     loc_10043DA2D
0x10043db7d  xor     r8d, r8d
0x10043db80  mov     r13, r14
0x10043db83  mov     esi, r8d
0x10043db86  jmp     loc_10043DF72
0x10043db8b  or      r13d, 0FFFFFFFFh
0x10043db8f  cmp     dword ptr [r15], 4
0x10043db93  jnz     loc_10043DC76
0x10043db99  cmp     [rdi+0A4h], r13d
0x10043dba0  jz      short loc_10043DBF6
0x10043dba2  call    cs:__imp_GetTickCount
0x10043dba8  mov     ecx, [rdi+0A4h]
0x10043dbae  add     ecx, ebx
0x10043dbb0  mov     ebx, 0FFFFFFFEh
0x10043dbb5  sub     ecx, eax
0x10043dbb7  mov     eax, cs:_bidGblFlags
0x10043dbbd  cmp     ecx, r13d
0x10043dbc0  cmovnz  ebx, ecx
0x10043dbc3  mov     ecx, 20002h
0x10043dbc8  and     eax, ecx
0x10043dbca  mov     [rsp+910h+var_8A8], ebx
0x10043dbce  cmp     eax, ecx
0x10043dbd0  jnz     short loc_10043DBFA
0x10043dbd2  mov     rax, cs:off_1005E5EE0; "<SNIOpenSyncEx|SNI> timeout(1): %d\n"
0x10043dbd9  xor     ecx, ecx
0x10043dbdb  test    rax, rax
0x10043dbde  jz      short loc_10043DBFA
0x10043dbe0  mov     r8, cs:off_1005E5EE0; "<SNIOpenSyncEx|SNI> timeout(1): %d\n"
0x10043dbe7  mov     r9d, ebx
0x10043dbea  mov     edx, 0EE800h
0x10043dbef  call    _bidTraceW
0x10043dbf4  jmp     short loc_10043DBFA
0x10043dbf6  mov     ebx, [rsp+910h+var_8A8]
0x10043dbfa  mov     r9, [rsp+910h+var_898]; struct SNI_Conn **
0x10043dbff  mov     r8, r15; struct ProtElem *
0x10043dc02  mov     rdx, rdi; struct SNI_CLIENT_CONSUMER_INFO *
0x10043dc05  mov     dword ptr [rsp+910h+lpMultiByteStr], ebx; int
0x10043dc09  mov     rcx, r14; struct ConnectParameter *
0x10043dc0c  call    ?Connect@@YAKPEAVConnectParameter@@PEAUSNI_CLIENT_CONSUMER_INFO@@PEAVProtElem@@PEAPEAVSNI_Conn@@H@Z; Connect(ConnectParameter *,SNI_CLIENT_CONSUMER_INFO *,ProtElem *,SNI_Conn * *,int)
0x10043dc11  xor     r8d, r8d; struct ProtElem *
0x10043dc14  mov     esi, eax
0x10043dc16  test    eax, eax
0x10043dc18  jnz     short loc_10043DC41
0x10043dc1a  mov     r13, r14
0x10043dc1d  cmp     [r14+0C16h], r8b
0x10043dc24  jz      loc_10043DF6D
0x10043dc2a  lea     rcx, [r14+816h]; this
0x10043dc31  mov     rdx, r15; unsigned __int16 *
0x10043dc34  call    ?SetEntry@LastConnectCache@@YAXPEBGPEAVProtElem@@@Z; LastConnectCache::SetEntry(ushort const *,ProtElem *)
0x10043dc39  xor     r8d, r8d
0x10043dc3c  jmp     loc_10043DF6D
0x10043dc41  lea     rcx, [rsp+910h+var_8A0]; this
0x10043dc46  mov     bl, 1
  ... truncated ...
```
