# CMDCOM::ComMDRestoreHistoryW(ushort const *,ulong,ulong,ulong)

- ea: `0x180019560`
- end: `0x180019a61`
- name: `?ComMDRestoreHistoryW@CMDCOM@@UEAAJPEBGKKK@Z`
- size: `1281`
- prototype: `__int64 __fastcall(CMDCOM *this, WCHAR *, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180008a08`
- `0x180019560`
- `0x18001a584`
- `0x18001c21c`
- `0x18001e0bc`
- `0x1800309d0`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x1800198b5`
- `msvcrt!_snwprintf_s` at `0x1800198de`
- `msvcrt!_snwprintf_s` at `0x1800198b5`
- `msvcrt!_snwprintf_s` at `0x1800198de`
- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x18001996b`
- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x180019998`
- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x18001996b`
- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x180019998`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180019644`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x18001964e`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180019644`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x18001964e`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180019a2c`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180019a36`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180019a2c`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180019a36`
- `IisRTL!PuDbgPrint` at `0x1800195f9`
- `IisRTL!PuDbgPrint` at `0x180019758`
- `IisRTL!PuDbgPrint` at `0x180019a12`
- `IisRTL!PuDbgPrint` at `0x1800195f9`
- `IisRTL!PuDbgPrint` at `0x180019758`
- `IisRTL!PuDbgPrint` at `0x180019a12`

## string_xrefs

- `0x1800195f2`: `inetsrv\iis\mb\metadata\comobj.cxx`
- `0x18001974b`: `inetsrv\iis\mb\metadata\comobj.cxx`
- `0x180019a0b`: `inetsrv\iis\mb\metadata\comobj.cxx`
- `0x1800195e4`: `CMDCOM::ComMDRestoreHistoryW`
- `0x18001973d`: `CMDCOM::ComMDRestoreHistoryW`
- `0x1800199fd`: `CMDCOM::ComMDRestoreHistoryW`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDRestoreHistoryW(
        CMDCOM *this,
        WCHAR *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5)
{
  WCHAR *v7; // r14
  unsigned int v8; // edi
  unsigned int v9; // ebx
  __int64 v10; // r8
  unsigned __int16 *v11; // rsi
  int v12; // eax
  WCHAR *v13; // r15
  int v14; // eax
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // r14
  unsigned __int64 v17; // r12
  unsigned int v18; // r8d
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  _OWORD *v24; // rdx
  int MostRecentHistoryFile; // eax
  __int64 v26; // r8
  unsigned int v27; // r15d
  unsigned int v28; // esi
  __int64 v29; // rax
  __int64 v30; // rbx
  size_t v31; // r13
  unsigned __int64 v32; // rax
  unsigned __int64 v33; // rax
  unsigned __int64 v34; // rax
  char *v36; // [rsp+20h] [rbp-E0h]
  char *v37; // [rsp+20h] [rbp-E0h]
  unsigned int v39; // [rsp+50h] [rbp-B0h]
  unsigned int v40; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 *v41; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v42[2]; // [rsp+60h] [rbp-A0h] BYREF
  void *Block; // [rsp+68h] [rbp-98h] BYREF
  CMDCOM *v44; // [rsp+70h] [rbp-90h]
  __int128 v45; // [rsp+78h] [rbp-88h]
  __int64 v46; // [rsp+88h] [rbp-78h]
  _QWORD v47[3]; // [rsp+90h] [rbp-70h]
  _QWORD v48[3]; // [rsp+A8h] [rbp-58h]
  _BYTE v49[128]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v50[128]; // [rsp+140h] [rbp+40h] BYREF

  v44 = this;
  v7 = a2;
  v8 = 0;
  if ( a2 )
  {
    while ( a2[v8] )
    {
      if ( (int)++v8 >= 100 )
      {
        if ( v8 != 100 )
          break;
        v9 = -2147024809;
        if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          v10 = 4854;
          goto LABEL_7;
        }
        return v9;
      }
    }
  }
  if ( (a5 & 0xFFFFFFFE) == 0 || !a5 )
  {
    Block = 0;
    v11 = 0;
    v41 = 0;
    STRAU::STRAU((STRAU *)v50);
    STRAU::STRAU((STRAU *)v49);
    if ( !v7 || !*v7 || !v8 )
    {
      v7 = (WCHAR *)g_wszHistoryFileDir;
      v8 = g_cchHistoryFileDir;
    }
    v12 = ConstructHistoryFileName(
            (unsigned __int16 **)&Block,
            v7,
            v8,
            g_wszRealFileNameWithoutPathWithoutExtension,
            g_cchRealFileNameWithoutPathWithoutExtension,
            g_wszRealFileNameExtension,
            g_cchRealFileNameExtension,
            a3,
            a4);
    v13 = (WCHAR *)Block;
    v9 = v12;
    if ( v12 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\comobj.cxx",
          4906,
          "CMDCOM::ComMDRestoreHistoryW",
          "hr=0x%x\n",
          v12);
      goto LABEL_68;
    }
    v14 = ConstructHistoryFileName(
            &v41,
            v7,
            v8,
            g_wszSchemaFileNameWithoutPathWithoutExtension,
            g_cchSchemaFileNameWithoutPathWithoutExtension,
            g_wszSchemaFileNameExtension,
            g_cchSchemaFileNameExtension,
            a3,
            a4);
    v9 = v14;
    if ( v14 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\comobj.cxx",
          4921,
          "CMDCOM::ComMDRestoreHistoryW",
          "hr=0x%x\n",
          v14);
      v11 = v41;
      goto LABEL_68;
    }
    v11 = v41;
    v48[0] = g_wszRealFileNameExtension;
    v48[1] = g_wszSchemaFileNameExtension;
    v47[0] = v13;
    v47[1] = v41;
    v47[2] = 0;
    v48[2] = 0;
    v46 = 0;
    v45 = 0;
    if ( (a5 & 1) != 0 )
    {
      v15 = -1;
      v40 = 0;
      v16 = -1;
      v42[0] = 0;
      do
        ++v16;
      while ( v13[v16] );
      v17 = -1;
      do
        ++v17;
      while ( v41[v17] );
      v18 = 0;
      do
      {
        v19 = v18;
        v20 = v47[v18];
        if ( !v20 )
          break;
        v21 = -1;
        do
          ++v21;
        while ( *(_WORD *)(v20 + 2 * v21) );
        v22 = v20 + 2 * v21;
        v23 = -1;
        do
          ++v23;
        while ( *(_WORD *)(v48[v18] + 2 * v23) );
        ++v18;
        v24 = (_OWORD *)(v22 - (2 * v23 + 44));
        *((_QWORD *)&v45 + v19) = v24;
        *v24 = *(_OWORD *)L"_??????????_??????????";
        v24[1] = *(_OWORD *)L"???_??????????";
        *(_OWORD *)((char *)v24 + 28) = *(_OWORD *)L"????????";
      }
      while ( v18 < 3 );
      MostRecentHistoryFile = GetMostRecentHistoryFile(v13, &v40, v42);
      v9 = MostRecentHistoryFile;
      if ( MostRecentHistoryFile < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          v26 = 4961;
LABEL_67:
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\comobj.cxx",
            v26,
            "CMDCOM::ComMDRestoreHistoryW",
            "hr=0x%x\n",
            MostRecentHistoryFile);
          goto LABEL_68;
        }
        goto LABEL_68;
      }
      v27 = v40;
      v28 = v42[0];
      v29 = 0;
      v39 = 0;
      do
      {
        v30 = *((_QWORD *)&v45 + v29);
        *(_QWORD *)v42 = v29;
        if ( !v30 )
          break;
        v31 = -1;
        do
          ++v31;
        while ( *(_WORD *)(v30 + 2 * v31) );
        LODWORD(v36) = v27;
        _snwprintf_s((wchar_t *const)(v30 + 2), v31, 0xAu, L"%010lu", v36);
        LODWORD(v37) = v28;
        *((_QWORD *)&v45 + *(_QWORD *)v42) = v30 + 24;
        _snwprintf_s((wchar_t *const)(v30 + 24), v31 - 11, 0xAu, L"%010lu", v37);
        v29 = v39 + 1;
        v39 = v29;
      }
      while ( (unsigned int)v29 < 3 );
      v11 = v41;
      v32 = -1;
      v13 = (WCHAR *)Block;
      do
        ++v32;
      while ( *((_WORD *)Block + v32) );
      if ( v32 < v16 )
        *((_WORD *)Block + v32) = 95;
      v33 = -1;
      do
        ++v33;
      while ( v13[v33] );
      if ( v33 < v16 )
        v13[v33] = 46;
      v34 = -1;
      do
        ++v34;
      while ( v11[v34] );
      if ( v34 < v17 )
        v11[v34] = 95;
      do
        ++v15;
      while ( v11[v15] );
      if ( v15 < v17 )
        v11[v15] = 46;
    }
    if ( STRAU::Copy((STRAU *)v50, v13) )
    {
      if ( STRAU::Copy((STRAU *)v49, v11) )
      {
        MostRecentHistoryFile = CMDCOM::Restore(v44, 0, (struct STRAU *)v50, (struct STRAU *)v49, 0, 0);
        v9 = MostRecentHistoryFile;
        if ( MostRecentHistoryFile >= 0 || (g_dwDebugFlags & 0xF) == 0 )
          goto LABEL_68;
        v26 = 5033;
        goto LABEL_67;
      }
      MostRecentHistoryFile = -2147024882;
      v9 = -2147024882;
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v26 = 5022;
        goto LABEL_67;
      }
    }
    else
    {
      MostRecentHistoryFile = -2147024882;
      v9 = -2147024882;
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v26 = 5016;
        goto LABEL_67;
      }
    }
LABEL_68:
    operator delete(v13);
    operator delete(v11);
    STRAU::~STRAU((STRAU *)v49);
    STRAU::~STRAU((STRAU *)v50);
    return v9;
  }
  v9 = -2147023892;
  if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v10 = 4866;
LABEL_7:
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\comobj.cxx", v10, "CMDCOM::ComMDRestoreHistoryW", "hr=0x%x\n", v9);
  }
  return v9;
}

```

## disassembly

```asm
0x180019560  push    rbp
0x180019562  push    rbx
0x180019563  push    rsi
0x180019564  push    rdi
0x180019565  push    r12
0x180019567  push    r13
0x180019569  push    r14
0x18001956b  push    r15
0x18001956d  lea     rbp, [rsp-0D8h]
0x180019575  sub     rsp, 1D8h
0x18001957c  mov     rax, cs:__security_cookie
0x180019583  xor     rax, rsp
0x180019586  mov     [rbp+110h+var_50], rax
0x18001958d  xor     r15d, r15d
0x180019590  mov     [rsp+210h+var_1A0], rcx
0x180019595  mov     ebx, r9d
0x180019598  mov     r13d, r8d
0x18001959b  mov     [rsp+210h+var_1C0], ebx
0x18001959f  mov     r14, rdx
0x1800195a2  mov     edi, r15d
0x1800195a5  test    rdx, rdx
0x1800195a8  jz      short loc_180019604
0x1800195aa  mov     eax, edi
0x1800195ac  cmp     [rdx+rax*2], r15w
0x1800195b1  jz      short loc_180019604
0x1800195b3  inc     edi
0x1800195b5  cmp     edi, 64h ; 'd'
0x1800195b8  jl      short loc_1800195AA
0x1800195ba  jnz     short loc_180019604
0x1800195bc  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800195c3  mov     ebx, 80070057h
0x1800195c8  jz      loc_180019A3C
0x1800195ce  mov     r8d, 12F6h
0x1800195d4  lea     rcx, aHr0xX; "hr=0x%x\n"
0x1800195db  mov     dword ptr [rsp+210h+var_1E8], ebx
0x1800195df  mov     [rsp+210h+var_1F0], rcx
0x1800195e4  lea     r9, aCmdcomCommdres; "CMDCOM::ComMDRestoreHistoryW"
0x1800195eb  mov     rcx, cs:g_pDebug
0x1800195f2  lea     rdx, aInetsrvIisMbMe_2; "inetsrv\\iis\\mb\\metadata\\comobj.cxx"
0x1800195f9  call    cs:__imp_PuDbgPrint
0x1800195ff  jmp     loc_180019A3C
0x180019604  mov     r12d, [rbp+110h+arg_20]
0x18001960b  test    r12d, 0FFFFFFFEh
0x180019612  jz      short loc_180019633
0x180019614  test    r12d, r12d
0x180019617  jz      short loc_180019633
0x180019619  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180019620  mov     ebx, 800703ECh
0x180019625  jz      loc_180019A3C
0x18001962b  mov     r8d, 1302h
0x180019631  jmp     short loc_1800195D4
0x180019633  lea     rcx, [rbp+110h+var_D0]
0x180019637  mov     [rsp+210h+Block], r15
0x18001963c  mov     rsi, r15
0x18001963f  mov     [rsp+210h+var_1B8], r15
0x180019644  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x18001964a  lea     rcx, [rbp+110h+var_150]
0x18001964e  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x180019654  test    r14, r14
0x180019657  jz      short loc_180019663
0x180019659  cmp     [r14], r15w
0x18001965d  jz      short loc_180019663
0x18001965f  test    edi, edi
0x180019661  jnz     short loc_180019670
0x180019663  mov     r14, cs:?g_wszHistoryFileDir@@3PEAGEA; ushort * g_wszHistoryFileDir
0x18001966a  mov     edi, cs:?g_cchHistoryFileDir@@3KA; ulong g_cchHistoryFileDir
0x180019670  mov     eax, cs:?g_cchRealFileNameExtension@@3KA; ulong g_cchRealFileNameExtension
0x180019676  lea     rcx, [rsp+210h+Block]; unsigned __int16 **
0x18001967b  mov     r9, cs:?g_wszRealFileNameWithoutPathWithoutExtension@@3PEAGEA; unsigned __int16 *
0x180019682  mov     r8d, edi; unsigned int
0x180019685  mov     [rsp+210h+var_1D0], ebx; unsigned int
0x180019689  mov     rdx, r14; unsigned __int16 *
0x18001968c  mov     [rsp+210h+var_1D8], r13d; unsigned int
0x180019691  mov     [rsp+210h+var_1E0], eax; unsigned int
0x180019695  mov     rax, cs:?g_wszRealFileNameExtension@@3PEAGEA; ushort * g_wszRealFileNameExtension
0x18001969c  mov     [rsp+210h+var_1E8], rax; unsigned __int16 *
0x1800196a1  mov     eax, cs:?g_cchRealFileNameWithoutPathWithoutExtension@@3KA; ulong g_cchRealFileNameWithoutPathWithoutExtension
0x1800196a7  mov     dword ptr [rsp+210h+var_1F0], eax; unsigned int
0x1800196ab  call    ?ConstructHistoryFileName@@YAJPEAPEAGPEAGK1K1KKK@Z; ConstructHistoryFileName(ushort * *,ushort *,ulong,ushort *,ulong,ushort *,ulong,ulong,ulong)
0x1800196b0  mov     r15, [rsp+210h+Block]
0x1800196b5  mov     ebx, eax
0x1800196b7  test    eax, eax
0x1800196b9  jns     short loc_1800196D7
0x1800196bb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800196c2  jz      loc_180019A18
0x1800196c8  mov     dword ptr [rsp+210h+var_1E8], eax
0x1800196cc  mov     r8d, 132Ah
0x1800196d2  jmp     loc_1800199F1
0x1800196d7  mov     eax, [rsp+210h+var_1C0]
0x1800196db  lea     rcx, [rsp+210h+var_1B8]; unsigned __int16 **
0x1800196e0  mov     r9, cs:?g_wszSchemaFileNameWithoutPathWithoutExtension@@3PEAGEA; unsigned __int16 *
0x1800196e7  mov     r8d, edi; unsigned int
0x1800196ea  mov     [rsp+210h+var_1D0], eax; unsigned int
0x1800196ee  mov     rdx, r14; unsigned __int16 *
0x1800196f1  mov     eax, cs:?g_cchSchemaFileNameExtension@@3KA; ulong g_cchSchemaFileNameExtension
0x1800196f7  mov     [rsp+210h+var_1D8], r13d; unsigned int
0x1800196fc  mov     [rsp+210h+var_1E0], eax; unsigned int
0x180019700  mov     rax, cs:?g_wszSchemaFileNameExtension@@3PEAGEA; ushort * g_wszSchemaFileNameExtension
0x180019707  mov     [rsp+210h+var_1E8], rax; unsigned __int16 *
0x18001970c  mov     eax, cs:?g_cchSchemaFileNameWithoutPathWithoutExtension@@3KA; ulong g_cchSchemaFileNameWithoutPathWithoutExtension
0x180019712  mov     dword ptr [rsp+210h+var_1F0], eax; unsigned int
0x180019716  call    ?ConstructHistoryFileName@@YAJPEAPEAGPEAGK1K1KKK@Z; ConstructHistoryFileName(ushort * *,ushort *,ulong,ushort *,ulong,ushort *,ulong,ulong,ulong)
0x18001971b  xor     r13d, r13d
0x18001971e  mov     ebx, eax
0x180019720  test    eax, eax
0x180019722  jns     short loc_180019768
0x180019724  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001972b  jz      short loc_18001975E
0x18001972d  lea     rcx, aHr0xX; "hr=0x%x\n"
0x180019734  mov     dword ptr [rsp+210h+var_1E8], eax
0x180019738  mov     [rsp+210h+var_1F0], rcx
0x18001973d  lea     r9, aCmdcomCommdres; "CMDCOM::ComMDRestoreHistoryW"
0x180019744  mov     rcx, cs:g_pDebug
0x18001974b  lea     rdx, aInetsrvIisMbMe_2; "inetsrv\\iis\\mb\\metadata\\comobj.cxx"
0x180019752  mov     r8d, 1339h
0x180019758  call    cs:__imp_PuDbgPrint
0x18001975e  mov     rsi, [rsp+210h+var_1B8]
0x180019763  jmp     loc_180019A18
0x180019768  mov     rax, cs:?g_wszRealFileNameExtension@@3PEAGEA; ushort * g_wszRealFileNameExtension
0x18001976f  xorps   xmm0, xmm0
0x180019772  mov     rsi, [rsp+210h+var_1B8]
0x180019777  mov     [rbp+110h+var_168], rax
0x18001977b  mov     rax, cs:?g_wszSchemaFileNameExtension@@3PEAGEA; ushort * g_wszSchemaFileNameExtension
0x180019782  mov     [rbp+110h+var_160], rax
0x180019786  mov     [rbp+110h+var_180], r15
0x18001978a  mov     [rbp+110h+var_178], rsi
0x18001978e  mov     [rbp+110h+var_170], r13
0x180019792  mov     [rbp+110h+var_158], r13
0x180019796  mov     [rbp+110h+var_188], r13
0x18001979a  movdqu  [rsp+210h+var_198], xmm0
0x1800197a0  test    r12b, 1
0x1800197a4  jz      loc_180019964
0x1800197aa  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800197ae  mov     [rsp+210h+var_1BC], r13d
0x1800197b3  mov     r14, rdi
0x1800197b6  mov     [rsp+210h+var_1B0], r13d
0x1800197bb  inc     r14
0x1800197be  cmp     [r15+r14*2], r13w
0x1800197c3  jnz     short loc_1800197BB
0x1800197c5  mov     r12, rdi
0x1800197c8  inc     r12
0x1800197cb  cmp     [rsi+r12*2], r13w
0x1800197d0  jnz     short loc_1800197C8
0x1800197d2  mov     r8d, r13d
0x1800197d5  mov     r9d, r8d
0x1800197d8  mov     rcx, [rbp+r9*8+110h+var_180]
0x1800197dd  test    rcx, rcx
0x1800197e0  jz      short loc_18001983E
0x1800197e2  mov     rax, rdi
0x1800197e5  inc     rax
0x1800197e8  cmp     [rcx+rax*2], r13w
0x1800197ed  jnz     short loc_1800197E5
0x1800197ef  lea     rdx, [rcx+rax*2]
0x1800197f3  mov     rcx, [rbp+r9*8+110h+var_168]
0x1800197f8  mov     rax, rdi
0x1800197fb  inc     rax
0x1800197fe  cmp     [rcx+rax*2], r13w
0x180019803  jnz     short loc_1800197FB
0x180019805  movups  xmm0, xmmword ptr cs:asc_18003A640; "_??????????_??????????"
0x18001980c  lea     rax, ds:2Ch[rax*2]
0x180019814  inc     r8d
0x180019817  sub     rdx, rax
0x18001981a  mov     qword ptr [rsp+r9*8+210h+var_198], rdx
0x18001981f  movups  xmmword ptr [rdx], xmm0
0x180019822  movups  xmm1, xmmword ptr cs:asc_18003A640+10h; "???_??????????"
0x180019829  movups  xmmword ptr [rdx+10h], xmm1
0x18001982d  movups  xmm0, xmmword ptr cs:asc_18003A640+1Ch; "????????"
0x180019834  movups  xmmword ptr [rdx+1Ch], xmm0
0x180019838  cmp     r8d, 3
0x18001983c  jb      short loc_1800197D5
0x18001983e  lea     r8, [rsp+210h+var_1B0]; unsigned int *
0x180019843  mov     rcx, r15; lpFileName
0x180019846  lea     rdx, [rsp+210h+var_1BC]; unsigned int *
0x18001984b  call    ?GetMostRecentHistoryFile@@YAJPEBGPEAK1@Z; GetMostRecentHistoryFile(ushort const *,ulong *,ulong *)
0x180019850  mov     ebx, eax
0x180019852  test    eax, eax
0x180019854  jns     short loc_18001986E
0x180019856  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001985d  jz      loc_180019A18
0x180019863  mov     r8d, 1361h
0x180019869  jmp     loc_1800199ED
0x18001986e  mov     r15d, [rsp+210h+var_1BC]
0x180019873  mov     esi, [rsp+210h+var_1B0]
0x180019877  mov     eax, r13d
0x18001987a  mov     [rsp+210h+var_1C0], eax
0x18001987e  mov     rbx, qword ptr [rsp+rax*8+210h+var_198]
0x180019883  mov     qword ptr [rsp+210h+var_1B0], rax
0x180019888  test    rbx, rbx
0x18001988b  jz      short loc_1800198F9
0x18001988d  mov     r13, rdi
0x180019890  xor     eax, eax
0x180019892  inc     r13
0x180019895  cmp     [rbx+r13*2], ax
0x18001989a  jnz     short loc_180019892
0x18001989c  lea     r9, a010lu; "%010lu"
0x1800198a3  mov     dword ptr [rsp+210h+var_1F0], r15d
0x1800198a8  mov     r8d, 0Ah; MaxCount
0x1800198ae  lea     rcx, [rbx+2]; Buffer
0x1800198b2  mov     rdx, r13; BufferCount
0x1800198b5  call    cs:__imp__snwprintf_s
0x1800198bb  mov     rax, qword ptr [rsp+210h+var_1B0]
0x1800198c0  lea     rcx, [rbx+18h]; Buffer
0x1800198c4  lea     rdx, [r13-0Bh]; BufferCount
0x1800198c8  mov     dword ptr [rsp+210h+var_1F0], esi
0x1800198cc  lea     r9, a010lu; "%010lu"
0x1800198d3  mov     r8d, 0Ah; MaxCount
0x1800198d9  mov     qword ptr [rsp+rax*8+210h+var_198], rcx
0x1800198de  call    cs:__imp__snwprintf_s
0x1800198e4  mov     eax, [rsp+210h+var_1C0]
0x1800198e8  mov     r13d, 0
0x1800198ee  inc     eax
0x1800198f0  mov     [rsp+210h+var_1C0], eax
0x1800198f4  cmp     eax, 3
0x1800198f7  jb      short loc_18001987E
0x1800198f9  mov     rsi, [rsp+210h+var_1B8]
0x1800198fe  mov     rax, rdi
0x180019901  mov     r15, [rsp+210h+Block]
0x180019906  inc     rax
0x180019909  cmp     [r15+rax*2], r13w
0x18001990e  jnz     short loc_180019906
0x180019910  mov     edx, 5Fh ; '_'
0x180019915  cmp     rax, r14
0x180019918  jnb     short loc_18001991F
0x18001991a  mov     [r15+rax*2], dx
0x18001991f  mov     rax, rdi
0x180019922  inc     rax
0x180019925  cmp     [r15+rax*2], r13w
0x18001992a  jnz     short loc_180019922
0x18001992c  mov     ecx, 2Eh ; '.'
0x180019931  cmp     rax, r14
0x180019934  jnb     short loc_18001993B
0x180019936  mov     [r15+rax*2], cx
0x18001993b  mov     rax, rdi
0x18001993e  inc     rax
0x180019941  cmp     [rsi+rax*2], r13w
0x180019946  jnz     short loc_18001993E
0x180019948  cmp     rax, r12
0x18001994b  jnb     short loc_180019951
0x18001994d  mov     [rsi+rax*2], dx
0x180019951  inc     rdi
0x180019954  cmp     [rsi+rdi*2], r13w
0x180019959  jnz     short loc_180019951
0x18001995b  cmp     rdi, r12
0x18001995e  jnb     short loc_180019964
0x180019960  mov     [rsi+rdi*2], cx
0x180019964  mov     rdx, r15
0x180019967  lea     rcx, [rbp+110h+var_D0]
0x18001996b  call    cs:__imp_?Copy@STRAU@@QEAAHPEBG@Z; STRAU::Copy(ushort const *)
0x180019971  test    eax, eax
0x180019973  jnz     short loc_180019991
0x180019975  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001997c  mov     eax, 8007000Eh
0x180019981  mov     ebx, eax
0x180019983  jz      loc_180019A18
0x180019989  mov     r8d, 1398h
0x18001998f  jmp     short loc_1800199ED
0x180019991  mov     rdx, rsi
0x180019994  lea     rcx, [rbp+110h+var_150]
0x180019998  call    cs:__imp_?Copy@STRAU@@QEAAHPEBG@Z; STRAU::Copy(ushort const *)
0x18001999e  test    eax, eax
0x1800199a0  jnz     short loc_1800199BA
0x1800199a2  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800199a9  mov     eax, 8007000Eh
0x1800199ae  mov     ebx, eax
0x1800199b0  jz      short loc_180019A18
0x1800199b2  mov     r8d, 139Eh
0x1800199b8  jmp     short loc_1800199ED
0x1800199ba  mov     rcx, [rsp+210h+var_1A0]; this
0x1800199bf  lea     r9, [rbp+110h+var_150]; struct STRAU *
0x1800199c3  mov     dword ptr [rsp+210h+var_1E8], r13d; int
0x1800199c8  lea     r8, [rbp+110h+var_D0]; struct STRAU *
0x1800199cc  xor     edx, edx; char *
0x1800199ce  mov     [rsp+210h+var_1F0], r13; char *
0x1800199d3  call    ?Restore@CMDCOM@@AEAAJPEADPEAVSTRAU@@10H@Z; CMDCOM::Restore(char *,STRAU *,STRAU *,char *,int)
0x1800199d8  mov     ebx, eax
0x1800199da  test    eax, eax
0x1800199dc  jns     short loc_180019A18
0x1800199de  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800199e5  jz      short loc_180019A18
0x1800199e7  mov     r8d, 13A9h
0x1800199ed  mov     dword ptr [rsp+210h+var_1E8], eax
0x1800199f1  lea     rcx, aHr0xX; "hr=0x%x\n"
0x1800199f8  mov     [rsp+210h+var_1F0], rcx
0x1800199fd  lea     r9, aCmdcomCommdres; "CMDCOM::ComMDRestoreHistoryW"
0x180019a04  mov     rcx, cs:g_pDebug
0x180019a0b  lea     rdx, aInetsrvIisMbMe_2; "inetsrv\\iis\\mb\\metadata\\comobj.cxx"
0x180019a12  call    cs:__imp_PuDbgPrint
0x180019a18  mov     rcx, r15; Block
0x180019a1b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019a20  mov     rcx, rsi; Block
0x180019a23  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019a28  lea     rcx, [rbp+110h+var_150]
0x180019a2c  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x180019a32  lea     rcx, [rbp+110h+var_D0]
0x180019a36  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x180019a3c  mov     eax, ebx
0x180019a3e  mov     rcx, [rbp+110h+var_50]
0x180019a45  xor     rcx, rsp; StackCookie
0x180019a48  call    __security_check_cookie
0x180019a4d  add     rsp, 1D8h
  ... truncated ...
```
