# DvrInit(void)

- ea: `0x1004e7330`
- end: `0x1004e7900`
- name: `?DvrInit@@YAKXZ`
- size: `1488`
- prototype: `unsigned int(void)`
- caller_count: `3`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1004eaf58`
- `0x10053ffb0`
- `0x100540510`

## callees

- `0x100405948`
- `0x10044bb88`
- `0x1004610b8`
- `0x10046c3c8`
- `0x1004e4ec4`
- `0x1004e7330`
- `0x1004e81b0`
- `0x1004e8c34`
- `0x1005458b4`
- `0x100545a0c`
- `0x100545d84`
- `0x100546a7c`
- `0x100546aa8`
- `0x100548140`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetTempPathW` at `0x1004e74ec`
- `KERNEL32!GetTempPathW` at `0x1004e74ec`
- `KERNEL32!GetComputerNameW` at `0x1004e764c`
- `KERNEL32!GetComputerNameW` at `0x1004e764c`
- `KERNEL32!GetLastError` at `0x1004e7618`
- `KERNEL32!GetLastError` at `0x1004e7675`
- `KERNEL32!GetLastError` at `0x1004e7888`
- `KERNEL32!GetLastError` at `0x1004e7618`
- `KERNEL32!GetLastError` at `0x1004e7675`
- `KERNEL32!GetLastError` at `0x1004e7888`
- `USER32!LoadStringW` at `0x1004e76ac`
- `USER32!LoadStringW` at `0x1004e76ac`
- `ADVAPI32!GetUserNameW` at `0x1004e75f9`
- `ADVAPI32!GetUserNameW` at `0x1004e75f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 DvrInit(void)
{
  int v0; // edi
  unsigned int v1; // ebx
  __int64 v2; // rdx
  DWORD TempPathW; // eax
  __int64 v4; // rdx
  WCHAR *v5; // rcx
  WCHAR v6; // ax
  WCHAR *v7; // rax
  __int64 v8; // rdx
  WCHAR *v9; // rcx
  WCHAR v10; // ax
  WCHAR *v11; // rax
  WCHAR *v12; // r9
  wchar_t *v13; // r8
  __int64 v14; // rdx
  CTdsParser *v15; // rax
  CTdsParser *v16; // rax
  __int64 v17; // rax
  CAsyncStatementTimeoutHandler *v18; // rbx
  DWORD pcbBuffer[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+58h] [rbp-B0h]
  __int64 v23; // [rsp+60h] [rbp-A8h]
  WCHAR Buffer[264]; // [rsp+68h] [rbp-A0h] BYREF

  v23 = -2;
  v0 = 0;
  pcbBuffer[0] = 0;
  v21 = -1;
  if ( (bidGblFlags & 4) != 0 && off_1005E8188[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_1005D39F0)(
      bidID,
      0,
      0,
      &v21,
      off_1005E8188[0],
      0);
  if ( (unsigned int)InitializeDll() )
  {
    (*(void (__fastcall **)(char *))(*((_QWORD *)g_pcsGlobal + 4) + 8LL))((char *)g_pcsGlobal + 32);
    if ( (g_uInitializationStatus & 0x100) == 0 )
    {
      if ( !(unsigned int)InitializeSharedModules() )
      {
        v0 = 1;
        if ( (bidGblFlags & 2) == 0 )
        {
LABEL_69:
          (*(void (__fastcall **)(char *))(*((_QWORD *)g_pcsGlobal + 4) + 24LL))((char *)g_pcsGlobal + 32);
          v1 = v0;
          goto LABEL_70;
        }
        v2 = 5838857;
LABEL_13:
        bidTraceMark(0, v2);
        goto LABEL_69;
      }
      if ( !(unsigned int)MPInitializeCriticalSectionAndSpinCount(&g_csSQLPerf) )
      {
        v0 = 1;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_69;
        v2 = 5846025;
        goto LABEL_13;
      }
      g_uInitializationStatus |= 0x100u;
    }
    if ( g_cInitRefCount )
    {
      ++g_cInitRefCount;
      if ( (bidGblFlags & 2) != 0 && off_1005E7328[0] )
        bidTraceW(0, 5857280, off_1005E7328[0], (unsigned int)g_cInitRefCount);
      goto LABEL_69;
    }
    memset_0(Buffer, 0, 0x20Au);
    TempPathW = GetTempPathW(0x105u, Buffer);
    if ( TempPathW - 1 > 0x103 )
    {
      v0 = 1;
      if ( (bidGblFlags & 2) == 0 || !off_1005E7330[0] )
        goto LABEL_69;
      GetLastError();
      v12 = Buffer;
      v13 = off_1005E7330[0];
      v14 = 5873664;
LABEL_68:
      bidTraceW(0, v14, v13, v12);
      goto LABEL_69;
    }
    if ( (unsigned __int64)TempPathW + 10 > 0x105 )
    {
      v0 = 1;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_69;
      v2 = 5882889;
      goto LABEL_13;
    }
    StringCchPrintfW(&g_szDefPerfDataFile, 0x105u, L"%s%s", Buffer, L"STATS.LOG");
    StringCchPrintfW(&g_szDefPerfQueryFile, 0x105u, L"%s%s", Buffer, L"QUERY.LOG");
    v4 = 261;
    v5 = &g_szPerfQueryFile;
    do
    {
      if ( v4 == -2147483385 )
        break;
      v6 = *(WCHAR *)((char *)v5 + (char *)&g_szDefPerfQueryFile - (char *)&g_szPerfQueryFile);
      if ( !v6 )
        break;
      *v5++ = v6;
      --v4;
    }
    while ( v4 );
    v7 = v5 - 1;
    if ( v4 )
      v7 = v5;
    *v7 = 0;
    v8 = 261;
    v9 = &g_szPerfDataFile;
    do
    {
      if ( v8 == -2147483385 )
        break;
      v10 = *(WCHAR *)((char *)v9 + (char *)&g_szDefPerfDataFile - (char *)&g_szPerfDataFile);
      if ( !v10 )
        break;
      *v9++ = v10;
      --v8;
    }
    while ( v8 );
    v11 = v9 - 1;
    if ( v8 )
      v11 = v9;
    *v11 = 0;
    pcbBuffer[0] = 257;
    if ( !GetUserNameW(&g_szUserName, pcbBuffer) && (bidGblFlags & 2) != 0 && off_1005E7338[0] )
    {
      GetLastError();
      bidTraceW(0, 5908480, off_1005E7338[0], &g_szUserName);
    }
    pcbBuffer[0] = 257;
    if ( !GetComputerNameW(&g_szComputerName, pcbBuffer) )
    {
      v0 = 1;
      if ( (bidGblFlags & 2) == 0 || !off_1005E7340[0] )
        goto LABEL_69;
      GetLastError();
      v12 = &g_szComputerName;
      v13 = off_1005E7340[0];
      v14 = 5916672;
      goto LABEL_68;
    }
    pcbBuffer[0] = LoadStringW(g_hinstance_language, 0x9C46u, &g_wszLocal, 30);
    GetAppName(&g_szAppName, 0x105u, &g_szExeName, 0x100u);
    memset_0(&g_SQLPerfData, 0, sizeof(g_SQLPerfData));
    if ( g_pTdsParser )
      goto LABEL_54;
    v15 = (CTdsParser *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 136);
    v22 = (__int64)v15;
    if ( v15 )
      v16 = CTdsParser::CTdsParser(v15);
    else
      v16 = 0;
    g_pTdsParser = v16;
    if ( !v16 )
    {
      v0 = 1;
      if ( (bidGblFlags & 2) != 0 && off_1005E7348[0] && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
          bidID,
          0,
          5944320,
          off_1005E7348[0],
          0);
      goto LABEL_59;
    }
    if ( (int)CTdsParser::InitParser(v16) >= 0 )
    {
LABEL_54:
      v17 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 64);
      v22 = v17;
      if ( v17 )
      {
        *(_DWORD *)v17 = 500;
        *(_QWORD *)(v17 + 8) = 0;
        *(_QWORD *)(v17 + 16) = 0;
        *(_QWORD *)(v17 + 24) = 0;
        *(_DWORD *)(v17 + 32) = 0;
        *(_QWORD *)(v17 + 40) = 0;
        *(_QWORD *)(v17 + 56) = v17 + 48;
        *(_QWORD *)(v17 + 48) = v17 + 48;
        g_pAsyncStatementTimeoutHandler = (CAsyncStatementTimeoutHandler *)v17;
        if ( (int)CAsyncStatementTimeoutHandler::Init((CAsyncStatementTimeoutHandler *)v17) >= 0 )
        {
          g_cInitRefCount = 1;
          goto LABEL_69;
        }
      }
      else
      {
        g_pAsyncStatementTimeoutHandler = 0;
      }
    }
    v0 = 1;
LABEL_59:
    if ( g_pTdsParser )
    {
      (**(void (__fastcall ***)(CTdsParser *, __int64))g_pTdsParser)(g_pTdsParser, 1);
      g_pTdsParser = 0;
    }
    v18 = g_pAsyncStatementTimeoutHandler;
    if ( g_pAsyncStatementTimeoutHandler )
    {
      CAsyncStatementTimeoutHandler::~CAsyncStatementTimeoutHandler(g_pAsyncStatementTimeoutHandler);
      ((void (__fastcall *)(struct IMalloc *, CAsyncStatementTimeoutHandler *))g_pMO->lpVtbl[1].Realloc)(g_pMO, v18);
      g_pAsyncStatementTimeoutHandler = 0;
    }
    goto LABEL_69;
  }
  if ( (bidGblFlags & 2) != 0 )
    bidTraceMark(0, 5826569);
  v1 = 1;
LABEL_70:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v21);
  return v1;
}

```

## disassembly

```asm
0x1004e7330  mov     rax, rsp
0x1004e7333  push    rbp
0x1004e7334  push    r14
0x1004e7336  push    r15
0x1004e7338  lea     rbp, [rax-198h]
0x1004e733f  sub     rsp, 280h
0x1004e7346  mov     [rsp+290h+var_238], 0FFFFFFFFFFFFFFFEh
0x1004e734f  mov     [rax+8], rbx
0x1004e7353  mov     [rax+10h], rsi
0x1004e7357  mov     [rax+18h], rdi
0x1004e735b  mov     [rax+20h], r12
0x1004e735f  mov     rax, cs:__security_cookie
0x1004e7366  xor     rax, rsp
0x1004e7369  mov     [rbp+190h+var_20], rax
0x1004e7370  xor     r15d, r15d
0x1004e7373  mov     edi, r15d
0x1004e7376  mov     [rsp+290h+pcbBuffer], r15d
0x1004e737b  or      [rsp+290h+var_248], 0FFFFFFFFFFFFFFFFh
0x1004e7381  test    byte ptr cs:_bidGblFlags, 4
0x1004e7388  jz      short loc_1004E73CF
0x1004e738a  mov     rax, cs:off_1005E8188; "<DvrInit|ODBC|DRIVER> "
0x1004e7391  test    rax, rax
0x1004e7394  jz      short loc_1004E73CF
0x1004e7396  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1004e739e  jz      short loc_1004E73CF
0x1004e73a0  mov     rax, cs:off_1005D39F0
0x1004e73a7  mov     [rsp+290h+var_268], r15
0x1004e73ac  mov     rcx, cs:off_1005E8188; "<DvrInit|ODBC|DRIVER> "
0x1004e73b3  mov     [rsp+290h+var_270], rcx
0x1004e73b8  lea     r9, [rsp+290h+var_248]
0x1004e73bd  xor     r8d, r8d
0x1004e73c0  xor     edx, edx
0x1004e73c2  mov     rcx, cs:_bidID
0x1004e73c9  call    cs:__guard_dispatch_icall_fptr
0x1004e73cf  call    ?InitializeDll@@YAHXZ; InitializeDll(void)
0x1004e73d4  test    eax, eax
0x1004e73d6  jnz     short loc_1004E73F7
0x1004e73d8  test    byte ptr cs:_bidGblFlags, 2
0x1004e73df  jz      short loc_1004E73ED
0x1004e73e1  mov     edx, 58E809h
0x1004e73e6  xor     ecx, ecx
0x1004e73e8  call    _bidTraceMark
0x1004e73ed  mov     ebx, 1
0x1004e73f2  jmp     loc_1004E78C4
0x1004e73f7  mov     rcx, cs:?g_pcsGlobal@@3PEAVCCriticalSection@@EA; CCriticalSection * g_pcsGlobal
0x1004e73fe  add     rcx, 20h ; ' '
0x1004e7402  mov     rax, [rcx]
0x1004e7405  mov     rax, [rax+8]
0x1004e7409  call    cs:__guard_dispatch_icall_fptr
0x1004e740f  mov     eax, cs:?g_uInitializationStatus@@3KC; ulong volatile g_uInitializationStatus
0x1004e7415  bt      eax, 8
0x1004e7419  jb      short loc_1004E747E
0x1004e741b  call    ?InitializeSharedModules@@YAHXZ; InitializeSharedModules(void)
0x1004e7420  test    eax, eax
0x1004e7422  jnz     short loc_1004E7445
0x1004e7424  lea     edi, [rax+1]
0x1004e7427  test    byte ptr cs:_bidGblFlags, 2
0x1004e742e  jz      loc_1004E78AA
0x1004e7434  mov     edx, 591809h
0x1004e7439  xor     ecx, ecx
0x1004e743b  call    _bidTraceMark
0x1004e7440  jmp     loc_1004E78AA
0x1004e7445  xor     edx, edx
0x1004e7447  lea     rcx, ?g_csSQLPerf@@3PEAVCCriticalSection@@EA; struct CCriticalSection **
0x1004e744e  call    MPInitializeCriticalSectionAndSpinCount
0x1004e7453  test    eax, eax
0x1004e7455  jnz     short loc_1004E746E
0x1004e7457  lea     edi, [rax+1]
0x1004e745a  test    byte ptr cs:_bidGblFlags, 2
0x1004e7461  jz      loc_1004E78AA
0x1004e7467  mov     edx, 593409h
0x1004e746c  jmp     short loc_1004E7439
0x1004e746e  mov     eax, cs:?g_uInitializationStatus@@3KC; ulong volatile g_uInitializationStatus
0x1004e7474  bts     eax, 8
0x1004e7478  mov     cs:?g_uInitializationStatus@@3KC, eax; ulong volatile g_uInitializationStatus
0x1004e747e  mov     eax, cs:?g_cInitRefCount@@3JA; long g_cInitRefCount
0x1004e7484  test    eax, eax
0x1004e7486  jz      short loc_1004E74CC
0x1004e7488  inc     eax
0x1004e748a  mov     cs:?g_cInitRefCount@@3JA, eax; long g_cInitRefCount
0x1004e7490  test    byte ptr cs:_bidGblFlags, 2
0x1004e7497  jz      loc_1004E78AA
0x1004e749d  mov     rax, cs:off_1005E7328; "<DvrInit|ODBC|DRIVER> Initialization Re"...
0x1004e74a4  test    rax, rax
0x1004e74a7  jz      loc_1004E78AA
0x1004e74ad  mov     r9d, cs:?g_cInitRefCount@@3JA; long g_cInitRefCount
0x1004e74b4  mov     r8, cs:off_1005E7328; "<DvrInit|ODBC|DRIVER> Initialization Re"...
0x1004e74bb  mov     edx, 596000h
0x1004e74c0  xor     ecx, ecx
0x1004e74c2  call    _bidTraceW
0x1004e74c7  jmp     loc_1004E78AA
0x1004e74cc  xor     edx, edx; Val
0x1004e74ce  mov     r8d, 20Ah; Size
0x1004e74d4  lea     rcx, [rsp+290h+Buffer]; void *
0x1004e74d9  call    memset_0
0x1004e74de  lea     rdx, [rsp+290h+Buffer]; lpBuffer
0x1004e74e3  mov     r12d, 105h
0x1004e74e9  mov     ecx, r12d; nBufferLength
0x1004e74ec  call    cs:__imp_GetTempPathW
0x1004e74f2  lea     ecx, [rax-1]
0x1004e74f5  cmp     ecx, 103h
0x1004e74fb  ja      loc_1004E786E
0x1004e7501  mov     eax, eax
0x1004e7503  add     rax, 0Ah
0x1004e7507  cmp     rax, r12
0x1004e750a  ja      loc_1004E7856
0x1004e7510  lea     rax, aStatsLog; "STATS.LOG"
0x1004e7517  mov     [rsp+290h+var_270], rax
0x1004e751c  lea     r9, [rsp+290h+Buffer]
0x1004e7521  lea     r8, aSS_4; "%s%s"
0x1004e7528  mov     edx, r12d; unsigned __int64
0x1004e752b  lea     rsi, ?g_szDefPerfDataFile@@3PAGA; ushort near * g_szDefPerfDataFile
0x1004e7532  mov     rcx, rsi; unsigned __int16 *
0x1004e7535  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1004e753a  lea     rax, aQueryLog; "QUERY.LOG"
0x1004e7541  mov     [rsp+290h+var_270], rax
0x1004e7546  lea     r9, [rsp+290h+Buffer]
0x1004e754b  lea     r8, aSS_4; "%s%s"
0x1004e7552  mov     edx, r12d; unsigned __int64
0x1004e7555  lea     r14, ?g_szDefPerfQueryFile@@3PAGA; ushort near * g_szDefPerfQueryFile
0x1004e755c  mov     rcx, r14; unsigned __int16 *
0x1004e755f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1004e7564  mov     edx, r12d
0x1004e7567  lea     rcx, ?g_szPerfQueryFile@@3PAGA; ushort near * g_szPerfQueryFile
0x1004e756e  sub     r14, rcx
0x1004e7571  mov     ebx, 1
0x1004e7576  lea     rax, [rdx+7FFFFEF9h]
0x1004e757d  test    rax, rax
0x1004e7580  jz      short loc_1004E7598
0x1004e7582  movzx   eax, word ptr [r14+rcx]
0x1004e7587  test    ax, ax
0x1004e758a  jz      short loc_1004E7598
0x1004e758c  mov     [rcx], ax
0x1004e758f  add     rcx, 2
0x1004e7593  sub     rdx, rbx
0x1004e7596  jnz     short loc_1004E7576
0x1004e7598  lea     rax, [rcx-2]
0x1004e759c  test    rdx, rdx
0x1004e759f  cmovnz  rax, rcx
0x1004e75a3  mov     [rax], r15w
0x1004e75a7  mov     rdx, r12
0x1004e75aa  lea     rcx, ?g_szPerfDataFile@@3PAGA; ushort near * g_szPerfDataFile
0x1004e75b1  sub     rsi, rcx
0x1004e75b4  lea     rax, [rdx+7FFFFEF9h]
0x1004e75bb  test    rax, rax
0x1004e75be  jz      short loc_1004E75D5
0x1004e75c0  movzx   eax, word ptr [rsi+rcx]
0x1004e75c4  test    ax, ax
0x1004e75c7  jz      short loc_1004E75D5
0x1004e75c9  mov     [rcx], ax
0x1004e75cc  add     rcx, 2
0x1004e75d0  sub     rdx, rbx
0x1004e75d3  jnz     short loc_1004E75B4
0x1004e75d5  lea     rax, [rcx-2]
0x1004e75d9  test    rdx, rdx
0x1004e75dc  cmovnz  rax, rcx
0x1004e75e0  mov     [rax], r15w
0x1004e75e4  mov     esi, 101h
0x1004e75e9  mov     [rsp+290h+pcbBuffer], esi
0x1004e75ed  lea     rdx, [rsp+290h+pcbBuffer]; pcbBuffer
0x1004e75f2  lea     rcx, ?g_szUserName@@3PAGA; lpBuffer
0x1004e75f9  call    cs:__imp_GetUserNameW
0x1004e75ff  test    eax, eax
0x1004e7601  jnz     short loc_1004E763C
0x1004e7603  test    byte ptr cs:_bidGblFlags, 2
0x1004e760a  jz      short loc_1004E763C
0x1004e760c  mov     rax, cs:off_1005E7338; "<DvrInit|WARN> GetUserName failed. g_sz"...
0x1004e7613  test    rax, rax
0x1004e7616  jz      short loc_1004E763C
0x1004e7618  call    cs:__imp_GetLastError
0x1004e761e  mov     dword ptr [rsp+290h+var_270], eax
0x1004e7622  lea     r9, ?g_szUserName@@3PAGA; ushort near * g_szUserName
0x1004e7629  mov     r8, cs:off_1005E7338; "<DvrInit|WARN> GetUserName failed. g_sz"...
0x1004e7630  mov     edx, 5A2800h
0x1004e7635  xor     ecx, ecx
0x1004e7637  call    _bidTraceW
0x1004e763c  mov     [rsp+290h+pcbBuffer], esi
0x1004e7640  lea     rdx, [rsp+290h+pcbBuffer]; nSize
0x1004e7645  lea     rcx, ?g_szComputerName@@3PAGA; lpBuffer
0x1004e764c  call    cs:__imp_GetComputerNameW
0x1004e7652  test    eax, eax
0x1004e7654  jnz     short loc_1004E7693
0x1004e7656  mov     edi, ebx
0x1004e7658  test    byte ptr cs:_bidGblFlags, 2
0x1004e765f  jz      loc_1004E78AA
0x1004e7665  mov     rax, cs:off_1005E7340; "<DvrInit|ERR> GetComputerName failed. g"...
0x1004e766c  test    rax, rax
0x1004e766f  jz      loc_1004E78AA
0x1004e7675  call    cs:__imp_GetLastError
0x1004e767b  lea     r9, ?g_szComputerName@@3PAGA; ushort near * g_szComputerName
0x1004e7682  mov     r8, cs:off_1005E7340; "<DvrInit|ERR> GetComputerName failed. g"...
0x1004e7689  mov     edx, 5A4800h
0x1004e768e  jmp     loc_1004E789F
0x1004e7693  mov     r9d, 1Eh; cchBufferMax
0x1004e7699  lea     r8, ?g_wszLocal@@3PAGA; lpBuffer
0x1004e76a0  mov     edx, 9C46h; uID
0x1004e76a5  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x1004e76ac  call    cs:__imp_LoadStringW
0x1004e76b2  mov     [rsp+290h+pcbBuffer], eax
0x1004e76b6  mov     r9d, 100h; unsigned __int64
0x1004e76bc  lea     r8, ?g_szExeName@@3PAGA; unsigned __int16 *
0x1004e76c3  mov     rdx, r12; unsigned __int64
0x1004e76c6  lea     rcx, ?g_szAppName@@3PAGA; unsigned __int16 *
0x1004e76cd  call    ?GetAppName@@YAHPEAG_K01@Z; GetAppName(ushort *,unsigned __int64,ushort *,unsigned __int64)
0x1004e76d2  xor     edx, edx; Val
0x1004e76d4  mov     r8d, 0A0h; Size
0x1004e76da  lea     rcx, ?g_SQLPerfData@@3Usqlperf@@A; void *
0x1004e76e1  call    memset_0
0x1004e76e6  cmp     cs:?g_pTdsParser@@3PEAVCTdsParser@@EA, r15; CTdsParser * g_pTdsParser
0x1004e76ed  jnz     loc_1004E7792
0x1004e76f3  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1004e76fa  mov     rax, [rcx]
0x1004e76fd  mov     edx, 88h
0x1004e7702  mov     rax, [rax+58h]
0x1004e7706  call    cs:__guard_dispatch_icall_fptr
0x1004e770c  mov     [rsp+290h+var_240], rax
0x1004e7711  test    rax, rax
0x1004e7714  jz      short loc_1004E7720
0x1004e7716  mov     rcx, rax; this
0x1004e7719  call    ??0CTdsParser@@QEAA@XZ; CTdsParser::CTdsParser(void)
0x1004e771e  jmp     short loc_1004E7723
0x1004e7720  mov     rax, r15
0x1004e7723  mov     cs:?g_pTdsParser@@3PEAVCTdsParser@@EA, rax; CTdsParser * g_pTdsParser
0x1004e772a  test    rax, rax
0x1004e772d  jnz     short loc_1004E7786
0x1004e772f  mov     edi, ebx
0x1004e7731  test    byte ptr cs:_bidGblFlags, 2
0x1004e7738  jz      loc_1004E7801
0x1004e773e  mov     rax, cs:off_1005E7348; "<DvrInit|TDS> TDSParser instantiation f"...
0x1004e7745  test    rax, rax
0x1004e7748  jz      loc_1004E7801
0x1004e774e  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1004e7756  jz      loc_1004E7801
0x1004e775c  mov     rax, cs:off_1005D39E0
0x1004e7763  mov     [rsp+290h+var_270], r15
0x1004e7768  mov     r9, cs:off_1005E7348; "<DvrInit|TDS> TDSParser instantiation f"...
0x1004e776f  xor     edx, edx
0x1004e7771  mov     r8d, 5AB400h
0x1004e7777  mov     rcx, cs:_bidID
0x1004e777e  call    cs:__guard_dispatch_icall_fptr
0x1004e7784  jmp     short loc_1004E7801
0x1004e7786  mov     rcx, rax; this
0x1004e7789  call    ?InitParser@CTdsParser@@QEAAJXZ; CTdsParser::InitParser(void)
0x1004e778e  test    eax, eax
0x1004e7790  js      short loc_1004E77FF
0x1004e7792  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1004e7799  mov     rax, [rcx]
0x1004e779c  mov     edx, 40h ; '@'
0x1004e77a1  mov     rax, [rax+58h]
0x1004e77a5  call    cs:__guard_dispatch_icall_fptr
0x1004e77ab  mov     [rsp+290h+var_240], rax
0x1004e77b0  test    rax, rax
0x1004e77b3  jz      short loc_1004E77F8
0x1004e77b5  mov     dword ptr [rax], 1F4h
0x1004e77bb  mov     [rax+8], r15
0x1004e77bf  mov     [rax+10h], r15
0x1004e77c3  mov     [rax+18h], r15
0x1004e77c7  mov     [rax+20h], r15d
0x1004e77cb  mov     [rax+28h], r15
0x1004e77cf  lea     rcx, [rax+30h]
0x1004e77d3  mov     [rcx+8], rcx
0x1004e77d7  mov     [rcx], rcx
0x1004e77da  mov     cs:?g_pAsyncStatementTimeoutHandler@@3PEAVCAsyncStatementTimeoutHandler@@EA, rax; CAsyncStatementTimeoutHandler * g_pAsyncStatementTimeoutHandler
0x1004e77e1  mov     rcx, rax; this
0x1004e77e4  call    ?Init@CAsyncStatementTimeoutHandler@@QEAAJXZ; CAsyncStatementTimeoutHandler::Init(void)
0x1004e77e9  test    eax, eax
0x1004e77eb  js      short loc_1004E77FF
0x1004e77ed  mov     cs:?g_cInitRefCount@@3JA, ebx; long g_cInitRefCount
0x1004e77f3  jmp     loc_1004E78AA
0x1004e77f8  mov     cs:?g_pAsyncStatementTimeoutHandler@@3PEAVCAsyncStatementTimeoutHandler@@EA, r15; CAsyncStatementTimeoutHandler * g_pAsyncStatementTimeoutHandler
0x1004e77ff  mov     edi, ebx
0x1004e7801  mov     rcx, cs:?g_pTdsParser@@3PEAVCTdsParser@@EA; CTdsParser * g_pTdsParser
0x1004e7808  test    rcx, rcx
0x1004e780b  jz      short loc_1004E7822
0x1004e780d  mov     rax, [rcx]
0x1004e7810  mov     edx, ebx
0x1004e7812  mov     rax, [rax]
0x1004e7815  call    cs:__guard_dispatch_icall_fptr
0x1004e781b  mov     cs:?g_pTdsParser@@3PEAVCTdsParser@@EA, r15; CTdsParser * g_pTdsParser
0x1004e7822  mov     rbx, cs:?g_pAsyncStatementTimeoutHandler@@3PEAVCAsyncStatementTimeoutHandler@@EA; CAsyncStatementTimeoutHandler * g_pAsyncStatementTimeoutHandler
0x1004e7829  test    rbx, rbx
0x1004e782c  jz      short loc_1004E78AA
0x1004e782e  mov     rcx, rbx; this
0x1004e7831  call    ??1CAsyncStatementTimeoutHandler@@QEAA@XZ; CAsyncStatementTimeoutHandler::~CAsyncStatementTimeoutHandler(void)
0x1004e7836  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1004e783d  mov     rax, [rcx]
0x1004e7840  mov     rdx, rbx
0x1004e7843  mov     rax, [rax+68h]
0x1004e7847  call    cs:__guard_dispatch_icall_fptr
0x1004e784d  mov     cs:?g_pAsyncStatementTimeoutHandler@@3PEAVCAsyncStatementTimeoutHandler@@EA, r15; CAsyncStatementTimeoutHandler * g_pAsyncStatementTimeoutHandler
0x1004e7854  jmp     short loc_1004E78AA
0x1004e7856  mov     edi, 1
0x1004e785b  test    byte ptr cs:_bidGblFlags, 2
0x1004e7862  jz      short loc_1004E78AA
0x1004e7864  mov     edx, 59C409h
0x1004e7869  jmp     loc_1004E7439
0x1004e786e  mov     edi, 1
0x1004e7873  test    byte ptr cs:_bidGblFlags, 2
0x1004e787a  jz      short loc_1004E78AA
0x1004e787c  mov     rax, cs:off_1005E7330; "<DvrInit|ERR> GetTempPath failed. wszTe"...
  ... truncated ...
```
