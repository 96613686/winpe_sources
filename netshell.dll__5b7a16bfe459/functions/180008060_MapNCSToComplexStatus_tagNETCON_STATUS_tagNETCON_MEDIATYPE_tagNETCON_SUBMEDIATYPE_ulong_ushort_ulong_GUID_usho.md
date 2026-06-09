# MapNCSToComplexStatus(tagNETCON_STATUS,tagNETCON_MEDIATYPE,tagNETCON_SUBMEDIATYPE,ulong,ushort *,ulong,_GUID,ushort const *)

- ea: `0x180008060`
- end: `0x1800085e4`
- name: `?MapNCSToComplexStatus@@YAXW4tagNETCON_STATUS@@W4tagNETCON_MEDIATYPE@@W4tagNETCON_SUBMEDIATYPE@@KPEAGKU_GUID@@PEBG@Z`
- size: `1412`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004400`
- `0x18001d630`
- `0x180048cb0`

## callees

- `0x180002460`
- `0x180002898`
- `0x1800032b0`
- `0x180008060`
- `0x180015268`
- `0x18001644c`
- `0x180017674`
- `0x18001e1e0`
- `0x18001eb7c`
- `0x1800228a4`
- `0x180034a44`
- `0x1800402b0`
- `0x18004a7b8`
- `0x180065010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180008511`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180008511`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180008500`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180008500`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000851f`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000851f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008572`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008572`
- `ole32!CoTaskMemFree` at `0x18000832c`
- `ole32!CoTaskMemFree` at `0x180008337`
- `ole32!CoTaskMemFree` at `0x18000832c`
- `ole32!CoTaskMemFree` at `0x180008337`

## pseudocode

```c
DWORD __fastcall MapNCSToComplexStatus(
        CConnectionList *a1,
        int a2,
        unsigned int a3,
        __int16 a4,
        LPWSTR lpBuffer,
        __int64 a6,
        struct _GUID *a7,
        unsigned __int16 *a8)
{
  int v11; // ebx
  int v12; // edi
  unsigned int v13; // r15d
  const unsigned __int16 *Ids; // rax
  const unsigned __int16 *v15; // r8
  __int64 v16; // rax
  __int64 v17; // rcx
  wchar_t *v18; // rax
  __int64 v19; // r8
  __int64 v20; // rcx
  const wchar_t *v21; // rdx
  __int64 v22; // rdi
  wchar_t *v23; // rax
  wchar_t v24; // r8
  wchar_t *v25; // rcx
  const unsigned __int16 *v26; // rax
  unsigned int v27; // edi
  va_list v28; // rcx
  unsigned int v29; // ecx
  int v30; // eax
  int v31; // ebx
  int v32; // ebx
  HMODULE v33; // rdi
  const WCHAR *v34; // rbx
  HRSRC Resource; // rax
  HGLOBAL v36; // rax
  int v37; // edx
  __int64 v38; // rcx
  const WCHAR *v39; // rax
  DWORD result; // eax
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v42; // [rsp+48h] [rbp-B8h] BYREF
  void *v43[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v44[8]; // [rsp+60h] [rbp-A0h] BYREF
  char v45[168]; // [rsp+68h] [rbp-98h] BYREF
  va_list Arguments[4]; // [rsp+110h] [rbp+10h] BYREF
  wchar_t pszDest[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v48[264]; // [rsp+1B0h] [rbp+B0h] BYREF

  v11 = (int)a1;
  *lpBuffer = 0;
  Arguments[0] = (va_list)&Caption;
  Arguments[1] = (va_list)&Caption;
  Arguments[2] = (va_list)&Caption;
  Arguments[3] = (va_list)&Caption;
  v12 = 0;
  if ( !a2 && (a4 & 0x20) != 0 )
  {
    LODWORD(pv) = 0;
    if ( (int)CConnectionList::HasActiveIncomingConnections(a1, (unsigned int *)&pv) >= 0
      && (v13 = (unsigned int)pv) != 0 )
    {
      if ( (_DWORD)pv == 1 )
      {
        Arguments[0] = (va_list)SzLoadIds(0x484u);
        v12 = 1;
      }
      else
      {
        Ids = SzLoadIds(0x485u);
        if ( DwFormatString(Ids, v48, 0x104u, v13) )
        {
          Arguments[0] = (va_list)v48;
          v12 = 1;
        }
      }
    }
    else
    {
      Arguments[0] = (va_list)SzLoadIds(0x483u);
      v12 = 1;
    }
    goto LABEL_68;
  }
  if ( a3 == 7 && a2 == 3 )
  {
    if ( (_DWORD)a1 == 2 )
    {
      ConnListEntry::ConnListEntry((ConnListEntry *)v44);
      if ( !(unsigned int)CConnectionList::HrFindConnectionByGuid((__int64 **)&g_ccl, a7, (struct ConnListEntry *)v44) )
      {
        v43[0] = 0;
        if ( CConFoldEntry::HrGetNetCon((CConFoldEntry *)v45, &IID_INetConnection, v43, 1) >= 0 )
        {
          v42 = 0;
          if ( (**(int (__fastcall ***)(void *, GUID *, __int64 *))v43[0])(
                 v43[0],
                 &GUID_15fd01a3_6e5d_4ecd_9ebd_1813cb3887a1,
                 &v42) >= 0 )
          {
            pv = 0;
            if ( !(*(unsigned int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v42 + 64LL))(v42, &pv) )
            {
              memset_0(pszDest, 0, sizeof(pszDest));
              v15 = (const unsigned __int16 *)*((_QWORD *)pv + 3);
              v16 = -1;
              do
                ++v16;
              while ( v15[v16] );
              if ( (unsigned int)v16 < 0x40 )
              {
                StringCchCopyW(pszDest, 0x40u, v15);
              }
              else
              {
                StringCchCopyNW(pszDest, 0x40u, v15, 0x3Cu);
                v17 = 64;
                v18 = pszDest;
                do
                {
                  if ( !*v18 )
                    break;
                  ++v18;
                  --v17;
                }
                while ( v17 );
                v19 = 64 - v17;
                if ( v17 )
                {
                  v20 = 2147483646;
                  v21 = L"...";
                  v22 = 64 - v19;
                  v23 = &pszDest[v19];
                  if ( 64 != v19 )
                  {
                    do
                    {
                      if ( !v20 )
                        break;
                      v24 = *v21;
                      if ( !*v21 )
                        break;
                      ++v21;
                      *v23++ = v24;
                      --v20;
                      --v22;
                    }
                    while ( v22 );
                  }
                  v25 = v23 - 1;
                  if ( v22 )
                    v25 = v23;
                  *v25 = 0;
                }
              }
              v26 = SzLoadIds(0x6AFu);
              v27 = DwFormatString(v26, v48, 0x104u, pszDest);
              v28 = (va_list)v48;
              if ( !v27 )
                v28 = Arguments[0];
              Arguments[0] = v28;
              CoTaskMemFree(*((LPVOID *)pv + 3));
              CoTaskMemFree(pv);
              v12 = v27 != 0;
            }
          }
          ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(&v42);
        }
        ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>((__int64 *)v43);
      }
      ConnListEntry::~ConnListEntry((ConnListEntry *)v44);
      if ( v12 )
        goto LABEL_73;
      goto LABEL_40;
    }
  }
  else if ( (_DWORD)a1 == 2 )
  {
LABEL_40:
    if ( *a8 )
    {
      if ( StringCchCopyW(v48, 0x104u, a8) >= 0 )
        Arguments[v12++] = (va_list)v48;
LABEL_70:
      v31 = v11 - 2;
      if ( v31 )
      {
        v32 = v31 - 6;
        if ( v32 )
        {
          if ( (unsigned int)(v32 - 1) > 1 )
            goto LABEL_77;
        }
      }
      goto LABEL_73;
    }
  }
  switch ( v11 )
  {
    case 0:
      v29 = 1048;
      if ( a2 != 3 )
        v29 = 1040;
      goto LABEL_67;
    case 1:
      v29 = 1051;
      if ( a2 != 3 )
        v29 = 1041;
      goto LABEL_67;
    case 2:
      v29 = 1050;
      if ( a2 != 3 )
        v29 = 1042;
      goto LABEL_67;
    case 3:
      v29 = 1043;
      goto LABEL_67;
    case 4:
      v29 = 1044;
      goto LABEL_67;
    case 5:
      v29 = 1045;
      goto LABEL_67;
    case 6:
      v29 = 1046;
      goto LABEL_67;
    case 7:
      if ( a2 == 3 && a3 <= 9 && (v30 = 644, _bittest(&v30, a3)) )
        v29 = 1056;
      else
        v29 = 1047;
      goto LABEL_67;
    case 8:
      v29 = 1035;
      goto LABEL_67;
    case 10:
      v29 = 1036;
      goto LABEL_67;
    case 12:
      v29 = 1038;
      goto LABEL_67;
    case 13:
    case 14:
      v29 = 1181;
      goto LABEL_67;
    case 15:
      v29 = 1040;
LABEL_67:
      Arguments[v12++] = (va_list)SzLoadIds(v29);
      break;
    default:
      break;
  }
LABEL_68:
  if ( v11 && v11 != 12 )
    goto LABEL_70;
LABEL_73:
  if ( (a4 & 0x200) != 0 )
    Arguments[v12++] = (va_list)SzLoadIds(0x41Du);
  if ( (a4 & 0x100) != 0 )
    Arguments[v12++] = (va_list)SzLoadIds(0x41Cu);
LABEL_77:
  if ( (a4 & 0x400) != 0 )
    Arguments[v12] = (va_list)SzLoadIds(0x41Eu);
  v33 = hInst;
  v34 = L" ";
  Resource = FindResourceExW(hInst, (LPCWSTR)6, (LPCWSTR)0x4A, 0);
  if ( Resource )
  {
    v36 = LoadResource(v33, Resource);
    if ( v36 )
    {
      v34 = (const WCHAR *)LockResource(v36);
      if ( !v34 )
        goto LABEL_85;
      v37 = 12;
      v38 = 0;
      do
      {
        v39 = &v34[v38];
        v38 = *v39;
        v34 = v39 + 1;
        LODWORD(v39) = v37--;
      }
      while ( (_DWORD)v39 );
      if ( !(_DWORD)v38 )
LABEL_85:
        v34 = L" ";
    }
  }
  result = FormatMessageW(0x2400u, v34, 0, 0, lpBuffer, 0xFFu, Arguments);
  if ( !result )
    *lpBuffer = 0;
  return result;
}

```

## disassembly

```asm
0x180008060  push    rbp
0x180008062  push    rbx
0x180008063  push    rsi
0x180008064  push    rdi
0x180008065  push    r12
0x180008067  push    r13
0x180008069  push    r14
0x18000806b  push    r15
0x18000806d  lea     rbp, [rsp-2D8h]
0x180008075  sub     rsp, 3D8h
0x18000807c  mov     rax, cs:__security_cookie
0x180008083  xor     rax, rsp
0x180008086  mov     [rbp+310h+var_50], rax
0x18000808d  mov     r14d, r9d
0x180008090  mov     r15d, r8d
0x180008093  mov     r12d, edx
0x180008096  movsxd  rbx, ecx
0x180008099  mov     rsi, [rbp+310h+arg_20]
0x1800080a0  mov     r13, [rbp+310h+arg_38]
0x1800080a7  xor     eax, eax
0x1800080a9  mov     [rsi], ax
0x1800080ac  lea     rax, Caption
0x1800080b3  mov     [rbp+310h+var_300], rax
0x1800080b7  mov     [rbp+310h+var_2F8], rax
0x1800080bb  mov     [rbp+310h+var_2F0], rax
0x1800080bf  mov     [rbp+310h+var_2E8], rax
0x1800080c3  xor     edi, edi
0x1800080c5  test    edx, edx
0x1800080c7  jnz     loc_180008166
0x1800080cd  test    r14b, 20h
0x1800080d1  jz      loc_180008166
0x1800080d7  mov     dword ptr [rsp+410h+pv], edi
0x1800080db  lea     rdx, [rsp+410h+pv]; unsigned int *
0x1800080e0  call    ?HasActiveIncomingConnections@CConnectionList@@QEAAJPEAK@Z; CConnectionList::HasActiveIncomingConnections(ulong *)
0x1800080e5  test    eax, eax
0x1800080e7  js      short loc_18000814E
0x1800080e9  mov     r15d, dword ptr [rsp+410h+pv]
0x1800080ee  test    r15d, r15d
0x1800080f1  jz      short loc_18000814E
0x1800080f3  cmp     r15d, 1
0x1800080f7  jnz     short loc_18000810F
0x1800080f9  mov     ecx, 484h; unsigned int
0x1800080fe  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x180008103  mov     [rbp+310h+var_300], rax
0x180008107  mov     edi, r15d
0x18000810a  jmp     def_1800083C7; jumptable 00000001800083C7 default case, cases 9,11
0x18000810f  mov     ecx, 485h; unsigned int
0x180008114  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x180008119  mov     r9d, r15d
0x18000811c  mov     r8d, 104h; unsigned int
0x180008122  lea     rdx, [rbp+310h+var_260]; unsigned __int16 *
0x180008129  mov     rcx, rax; lpSource
0x18000812c  call    ?DwFormatString@@YAKPEBGPEAGKZZ; DwFormatString(ushort const *,ushort *,ulong,...)
0x180008131  test    eax, eax
0x180008133  jz      def_1800083C7; jumptable 00000001800083C7 default case, cases 9,11
0x180008139  lea     rax, [rbp+310h+var_260]
0x180008140  mov     [rbp+310h+var_300], rax
0x180008144  mov     edi, 1
0x180008149  jmp     def_1800083C7; jumptable 00000001800083C7 default case, cases 9,11
0x18000814e  mov     ecx, 483h; unsigned int
0x180008153  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x180008158  mov     [rbp+310h+var_300], rax
0x18000815c  mov     edi, 1
0x180008161  jmp     def_1800083C7; jumptable 00000001800083C7 default case, cases 9,11
0x180008166  cmp     r15d, 7
0x18000816a  jnz     loc_18000836F
0x180008170  cmp     r12d, 3
0x180008174  jnz     loc_18000836F
0x18000817a  cmp     ebx, 2
0x18000817d  jnz     loc_1800083AD
0x180008183  lea     rcx, [rsp+410h+var_3B0]; this
0x180008188  call    ??0ConnListEntry@@QEAA@XZ; ConnListEntry::ConnListEntry(void)
0x18000818d  lea     r8, [rsp+410h+var_3B0]; struct ConnListEntry *
0x180008192  mov     rdx, [rbp+310h+arg_30]; struct _GUID *
0x180008199  lea     rcx, ?g_ccl@@3VCConnectionList@@A; this
0x1800081a0  call    ?HrFindConnectionByGuid@CConnectionList@@QEAAJPEFBU_GUID@@AEAVConnListEntry@@@Z; CConnectionList::HrFindConnectionByGuid(_GUID const *,ConnListEntry &)
0x1800081a5  test    eax, eax
0x1800081a7  jnz     loc_18000835C
0x1800081ad  mov     [rsp+410h+var_3C0], rdi
0x1800081b2  mov     r9d, 1; int
0x1800081b8  lea     r8, [rsp+410h+var_3C0]; void **
0x1800081bd  lea     rdx, IID_INetConnection; struct _GUID *
0x1800081c4  lea     rcx, [rsp+410h+var_3A8]; this
0x1800081c9  call    ?HrGetNetCon@CConFoldEntry@@QEBAJAEBU_GUID@@PEAPEAXH@Z; CConFoldEntry::HrGetNetCon(_GUID const &,void * *,int)
0x1800081ce  test    eax, eax
0x1800081d0  js      loc_180008352
0x1800081d6  mov     [rsp+410h+var_3C8], rdi
0x1800081db  mov     rcx, [rsp+410h+var_3C0]
0x1800081e0  mov     rax, [rcx]
0x1800081e3  lea     r8, [rsp+410h+var_3C8]
0x1800081e8  lea     rdx, _GUID_15fd01a3_6e5d_4ecd_9ebd_1813cb3887a1
0x1800081ef  mov     rax, [rax]
0x1800081f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081f7  test    eax, eax
0x1800081f9  js      loc_180008348
0x1800081ff  mov     [rsp+410h+pv], rdi
0x180008204  mov     rcx, [rsp+410h+var_3C8]
0x180008209  mov     rax, [rcx]
0x18000820c  lea     rdx, [rsp+410h+pv]
0x180008211  mov     rax, [rax+40h]
0x180008215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000821a  test    eax, eax
0x18000821c  jnz     loc_180008348
0x180008222  xor     edx, edx; Val
0x180008224  mov     r8d, 80h; Size
0x18000822a  lea     rcx, [rbp+310h+pszDest]; void *
0x18000822e  call    memset_0
0x180008233  mov     rax, [rsp+410h+pv]
0x180008238  mov     r8, [rax+18h]; unsigned __int16 *
0x18000823c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008243  inc     rax
0x180008246  cmp     [r8+rax*2], di
0x18000824b  jnz     short loc_180008243
0x18000824d  lea     rcx, [rbp+310h+pszDest]; unsigned __int16 *
0x180008251  cmp     eax, 40h ; '@'
0x180008254  jb      loc_1800082E2
0x18000825a  mov     edi, 40h ; '@'
0x18000825f  mov     r9d, 3Ch ; '<'; cchToCopy
0x180008265  mov     edx, edi; cchDest
0x180008267  call    StringCchCopyNW
0x18000826c  mov     ecx, edi
0x18000826e  lea     rax, [rbp+310h+pszDest]
0x180008272  cmp     word ptr [rax], 0
0x180008276  jz      short loc_180008282
0x180008278  add     rax, 2
0x18000827c  sub     rcx, 1
0x180008280  jnz     short loc_180008272
0x180008282  mov     r8, rdi
0x180008285  sub     r8, rcx
0x180008288  xor     eax, eax
0x18000828a  test    rcx, rcx
0x18000828d  cmovz   r8, rax
0x180008291  jz      short loc_1800082EC
0x180008293  mov     ecx, 7FFFFFFEh
0x180008298  lea     rdx, asc_1800734F8; "..."
0x18000829f  sub     rdi, r8
0x1800082a2  lea     rax, [rbp+310h+pszDest]
0x1800082a6  lea     rax, [rax+r8*2]
0x1800082aa  jz      short loc_1800082D0
0x1800082ac  test    rcx, rcx
0x1800082af  jz      short loc_1800082D0
0x1800082b1  movzx   r8d, word ptr [rdx]
0x1800082b5  test    r8w, r8w
0x1800082b9  jz      short loc_1800082D0
0x1800082bb  add     rdx, 2
0x1800082bf  mov     [rax], r8w
0x1800082c3  add     rax, 2
0x1800082c7  dec     rcx
0x1800082ca  sub     rdi, 1
0x1800082ce  jnz     short loc_1800082AC
0x1800082d0  lea     rcx, [rax-2]
0x1800082d4  test    rdi, rdi
0x1800082d7  cmovnz  rcx, rax
0x1800082db  xor     eax, eax
0x1800082dd  mov     [rcx], ax
0x1800082e0  jmp     short loc_1800082EC
0x1800082e2  mov     edx, 40h ; '@'; unsigned __int64
0x1800082e7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800082ec  mov     ecx, 6AFh; unsigned int
0x1800082f1  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x1800082f6  mov     rcx, rax; lpSource
0x1800082f9  lea     r9, [rbp+310h+pszDest]
0x1800082fd  mov     r8d, 104h; unsigned int
0x180008303  lea     rdx, [rbp+310h+var_260]; unsigned __int16 *
0x18000830a  call    ?DwFormatString@@YAKPEBGPEAGKZZ; DwFormatString(ushort const *,ushort *,ulong,...)
0x18000830f  mov     edi, eax
0x180008311  lea     rcx, [rbp+310h+var_260]
0x180008318  test    eax, eax
0x18000831a  cmovz   rcx, [rbp+310h+var_300]
0x18000831f  mov     [rbp+310h+var_300], rcx
0x180008323  mov     rcx, [rsp+410h+pv]
0x180008328  mov     rcx, [rcx+18h]; pv
0x18000832c  call    cs:__imp_CoTaskMemFree
0x180008332  mov     rcx, [rsp+410h+pv]; pv
0x180008337  call    cs:__imp_CoTaskMemFree
0x18000833d  test    edi, edi
0x18000833f  mov     edi, 0
0x180008344  setnz   dil
0x180008348  lea     rcx, [rsp+410h+var_3C8]
0x18000834d  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x180008352  lea     rcx, [rsp+410h+var_3C0]
0x180008357  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x18000835c  lea     rcx, [rsp+410h+var_3B0]; this
0x180008361  call    ??1ConnListEntry@@QEAA@XZ; ConnListEntry::~ConnListEntry(void)
0x180008366  test    edi, edi
0x180008368  jz      short loc_180008374
0x18000836a  jmp     loc_180008492
0x18000836f  cmp     ebx, 2
0x180008372  jnz     short loc_1800083AD
0x180008374  cmp     word ptr [r13+0], 0
0x18000837a  jz      short loc_1800083AD
0x18000837c  mov     r8, r13; unsigned __int16 *
0x18000837f  mov     edx, 104h; unsigned __int64
0x180008384  lea     rcx, [rbp+310h+var_260]; unsigned __int16 *
0x18000838b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008390  test    eax, eax
0x180008392  js      loc_18000847E
0x180008398  mov     eax, edi
0x18000839a  lea     rcx, [rbp+310h+var_260]
0x1800083a1  mov     [rbp+rax*8+310h+var_300], rcx
0x1800083a6  inc     edi
0x1800083a8  jmp     loc_18000847E
0x1800083ad  cmp     ebx, 0Fh; switch 16 cases
0x1800083b0  ja      def_1800083C7; jumptable 00000001800083C7 default case, cases 9,11
0x1800083b6  lea     rdx, __ImageBase
0x1800083bd  mov     ecx, ds:(jpt_1800083C7 - 180000000h)[rdx+rbx*4]
0x1800083c4  add     rcx, rdx
0x1800083c7  jmp     rcx; switch jump
0x1800083c9  mov     ecx, 418h; jumptable 00000001800083C7 case 0
0x1800083ce  mov     eax, 410h
0x1800083d3  cmp     r12d, 3
0x1800083d7  cmovnz  ecx, eax
0x1800083da  jmp     loc_180008467
0x1800083df  mov     ecx, 41Bh; jumptable 00000001800083C7 case 1
0x1800083e4  mov     eax, 411h
0x1800083e9  cmp     r12d, 3
0x1800083ed  cmovnz  ecx, eax
0x1800083f0  jmp     short loc_180008467
0x1800083f2  mov     ecx, 41Ah; jumptable 00000001800083C7 case 2
0x1800083f7  mov     eax, 412h
0x1800083fc  cmp     r12d, 3
0x180008400  cmovnz  ecx, eax
0x180008403  jmp     short loc_180008467
0x180008405  mov     ecx, 413h; jumptable 00000001800083C7 case 3
0x18000840a  jmp     short loc_180008467
0x18000840c  mov     ecx, 414h; jumptable 00000001800083C7 case 4
0x180008411  jmp     short loc_180008467
0x180008413  mov     ecx, 415h; jumptable 00000001800083C7 case 5
0x180008418  jmp     short loc_180008467
0x18000841a  mov     ecx, 416h; jumptable 00000001800083C7 case 6
0x18000841f  jmp     short loc_180008467
0x180008421  cmp     r12d, 3; jumptable 00000001800083C7 case 7
0x180008425  jnz     short loc_18000843F
0x180008427  cmp     r15d, 9
0x18000842b  ja      short loc_18000843F
0x18000842d  mov     eax, 284h
0x180008432  bt      eax, r15d
0x180008436  jnb     short loc_18000843F
0x180008438  mov     ecx, 420h
0x18000843d  jmp     short loc_180008467
0x18000843f  mov     ecx, 417h
0x180008444  jmp     short loc_180008467
0x180008446  mov     ecx, 40Bh; jumptable 00000001800083C7 case 8
0x18000844b  jmp     short loc_180008467
0x18000844d  mov     ecx, 40Ch; jumptable 00000001800083C7 case 10
0x180008452  jmp     short loc_180008467
0x180008454  mov     ecx, 40Eh; jumptable 00000001800083C7 case 12
0x180008459  jmp     short loc_180008467
0x18000845b  mov     ecx, 49Dh; jumptable 00000001800083C7 cases 13,14
0x180008460  jmp     short loc_180008467
0x180008462  mov     ecx, 410h; jumptable 00000001800083C7 case 15
0x180008467  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x18000846c  mov     ecx, edi
0x18000846e  mov     [rbp+rcx*8+310h+var_300], rax
0x180008473  inc     edi
0x180008475  test    ebx, ebx; jumptable 00000001800083C7 default case, cases 9,11
0x180008477  jz      short loc_180008492
0x180008479  cmp     ebx, 0Ch
0x18000847c  jz      short loc_180008492
0x18000847e  sub     ebx, 2
0x180008481  jz      short loc_180008492
0x180008483  sub     ebx, 6
0x180008486  jz      short loc_180008492
0x180008488  sub     ebx, 1
0x18000848b  jz      short loc_180008492
0x18000848d  cmp     ebx, 1
0x180008490  jnz     short loc_1800084C6
0x180008492  bt      r14d, 9
0x180008497  jnb     short loc_1800084AC
0x180008499  mov     ecx, 41Dh; unsigned int
0x18000849e  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x1800084a3  mov     ecx, edi
0x1800084a5  mov     [rbp+rcx*8+310h+var_300], rax
0x1800084aa  inc     edi
0x1800084ac  bt      r14d, 8
0x1800084b1  jnb     short loc_1800084C6
0x1800084b3  mov     ecx, 41Ch; unsigned int
0x1800084b8  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x1800084bd  mov     ecx, edi
0x1800084bf  mov     [rbp+rcx*8+310h+var_300], rax
0x1800084c4  inc     edi
0x1800084c6  bt      r14d, 0Ah
0x1800084cb  jnb     short loc_1800084DE
0x1800084cd  mov     ecx, 41Eh; unsigned int
0x1800084d2  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x1800084d7  mov     ecx, edi
0x1800084d9  mov     [rbp+rcx*8+310h+var_300], rax
0x1800084de  mov     rdi, cs:hInst
0x1800084e5  lea     r14, ?c_szSpace@@3QBGB; " "
0x1800084ec  mov     rbx, r14
0x1800084ef  xor     r9d, r9d; wLanguage
0x1800084f2  mov     edx, 6; lpType
0x1800084f7  mov     r8d, 4Ah ; 'J'; lpName
0x1800084fd  mov     rcx, rdi; hModule
0x180008500  call    cs:__imp_FindResourceExW
0x180008506  test    rax, rax
0x180008509  jz      short loc_18000854E
0x18000850b  mov     rdx, rax; hResInfo
0x18000850e  mov     rcx, rdi; hModule
0x180008511  call    cs:__imp_LoadResource
  ... truncated ...
```
