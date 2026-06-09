# SaveEntireTree(IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *,ulong,ushort *,ushort *,_SECURITY_ATTRIBUTES *,void *)

- ea: `0x180023df4`
- end: `0x1800242a5`
- name: `?SaveEntireTree@@YAJPEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@KPEAG2PEAU_SECURITY_ATTRIBUTES@@PEAX@Z`
- size: `1201`
- prototype: `__int64 __usercall@<rax>(struct IIS_CRYPTO_STORAGE *@<rcx>, struct _IIS_CRYPTO_BLOB *@<rdx>, unsigned int@<r8d>, unsigned __int16 *@<r9>, unsigned __int16 *, struct _SECURITY_ATTRIBUTES *, void *)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180023548`
- `0x180023be0`

## callees

- `0x180002d60`
- `0x1800053b0`
- `0x180005cd8`
- `0x180007810`
- `0x1800089c8`
- `0x180008a08`
- `0x180008a14`
- `0x180009b80`
- `0x180012824`
- `0x18001497c`
- `0x1800204fc`
- `0x180023df4`
- `0x180024388`
- `0x1800249b0`
- `0x1800274d0`
- `0x18002d4fc`
- `0x18002d788`
- `0x18002db80`
- `0x18003099a`
- `0x1800309d0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800241b7`
- `msvcrt!_wcsnicmp` at `0x1800241e4`
- `msvcrt!_wcsnicmp` at `0x1800241b7`
- `msvcrt!_wcsnicmp` at `0x1800241e4`
- `msvcrt!qsort` at `0x180024181`
- `msvcrt!qsort` at `0x180024181`
- `IisRTL!?FreeMemory@BUFFER@@QEAAXXZ` at `0x18002424c`
- `IisRTL!?FreeMemory@BUFFER@@QEAAXXZ` at `0x18002424c`
- `IisRTL!PuDbgPrintW` at `0x180023f27`
- `IisRTL!PuDbgPrintW` at `0x180023f8e`
- `IisRTL!PuDbgPrintW` at `0x180023ffe`
- `IisRTL!PuDbgPrintW` at `0x180023f27`
- `IisRTL!PuDbgPrintW` at `0x180023f8e`
- `IisRTL!PuDbgPrintW` at `0x180023ffe`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x180023e9e`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x180023e9e`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180023eb8`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180023ec9`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180023eb8`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180023ec9`

## string_xrefs

- `0x180023ff2`: `[SaveAllData] Initializing writer with write file: %s bin file: %s.\n`

## pseudocode

```c
__int64 __fastcall SaveEntireTree(
        struct IIS_CRYPTO_STORAGE *a1,
        struct _IIS_CRYPTO_BLOB *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct _SECURITY_ATTRIBUTES *a6,
        void *a7)
{
  struct CMDHandle *HandleObject; // rax
  int v11; // edi
  BUFFER *v12; // rax
  BUFFER *v13; // rax
  BUFFER *v14; // rbp
  _BYTE *v15; // r15
  int v16; // eax
  int v17; // eax
  int v18; // ebx
  HANDLE *v19; // rax
  HANDLE *v20; // rsi
  unsigned int v21; // edx
  struct _IIS_CRYPTO_BLOB *v22; // r8
  CMDBaseObject *v23; // r9
  unsigned int v24; // r14d
  struct CMDBaseObject *i; // rdx
  struct CMDBaseObject *ChildObject; // rax
  struct CMDBaseObject *v27; // rax
  CMDBaseObject *v28; // r9
  __int64 j; // r10
  int v30; // r10d
  __int64 v31; // r12
  unsigned int v32; // ebx
  const wchar_t *Name; // rax
  unsigned int v34; // ebx
  const wchar_t *v35; // rax
  int v36; // eax
  unsigned int v37; // edx
  int v39[2]; // [rsp+30h] [rbp-A8h]
  _BYTE Base[64]; // [rsp+50h] [rbp-88h] BYREF

  memset_0(Base, 0, sizeof(Base));
  if ( a3 )
  {
    HandleObject = GetHandleObject(a3);
    if ( !HandleObject || *((CMDBaseObject **)HandleObject + 3) != g_pboMasterRoot )
      return (unsigned int)-2147024890;
    if ( (*((_BYTE *)HandleObject + 12) & 1) == 0 && (*((_BYTE *)HandleObject + 12) & 2) == 0 )
      return (unsigned int)-2147024891;
  }
  v12 = (BUFFER *)operator new(0x30u);
  if ( !v12 )
    return (unsigned int)-2147024882;
  v13 = BUFFER::BUFFER(v12);
  if ( (v14 = v13) == 0 )
    return (unsigned int)-2147024882;
  v15 = Base;
  *(_WORD *)BUFFER::QueryPtr(v13) = 47;
  *((_WORD *)BUFFER::QueryPtr(v14) + 1) = 0;
  if ( a4 )
  {
    ++g_dwSchemaChangeNumber;
  }
  else
  {
    v16 = UnlockMetabaseFile(1);
    v11 = v16;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        8409,
        "SaveEntireTree",
        L"[SaveAllData] Unlocking metabase file %s returned 0x%x.\n",
        a5,
        v16);
    if ( v11 < 0 )
      goto LABEL_49;
  }
  v11 = SaveSchemaIfNeeded(a5, a6);
  if ( !a4 )
  {
    v17 = LockMetabaseFile(a5, 1);
    v18 = v17;
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v39[0] = v17;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        8434,
        "SaveEntireTree",
        L"[SaveAllData] Locking metabase file %s returned 0x%x.\n",
        a5,
        *(_QWORD *)v39);
    }
    if ( v18 < 0 )
    {
      if ( v11 >= 0 )
        v11 = v18;
      goto LABEL_49;
    }
  }
  if ( v11 >= 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        8453,
        "SaveEntireTree",
        L"[SaveAllData] Initializing writer with write file: %s bin file: %s.\n",
        g_wszTempFileName,
        *((_QWORD *)g_pGlobalISTHelper + 31));
    v19 = (HANDLE *)operator new(0x10050u);
    v20 = v19;
    if ( !v19 )
    {
      v11 = -2147024882;
      goto LABEL_49;
    }
    v19[8199] = (HANDLE)-1LL;
    *v19 = 0;
    v19[1] = 0;
    v19[8200] = 0;
    v19[8201] = 0;
    *((_DWORD *)v19 + 4) = 0;
    v19[8195] = 0;
    v19[8196] = 0;
    v19[8197] = 0;
    v19[8198] = 0;
    v11 = CWriter::Initialize((CWriter *)v19, g_wszTempFileName, g_pGlobalISTHelper, a7);
    if ( v11 < 0 )
      goto LABEL_47;
    v11 = CWriter::BeginWrite(v20, 1, 0);
    if ( v11 < 0 )
      goto LABEL_47;
    v11 = SaveGlobalsToXML((struct CWriter *)v20, a2, 0);
    if ( v11 < 0 )
      goto LABEL_47;
    v11 = SaveMasterRoot((struct CWriter *)v20, a1, v22);
    if ( v11 < 0 )
      goto LABEL_47;
    v23 = g_pboMasterRoot;
    v24 = 0;
    for ( i = 0; ; i = ChildObject )
    {
      ChildObject = CMDBaseObject::NextChildObject(v23, i);
      if ( !ChildObject )
        break;
      ++v24;
    }
    if ( v24 > 8 )
    {
      v15 = operator new[](saturated_mul(v24, 8u));
      if ( !v15 )
      {
        v11 = -2147024882;
LABEL_47:
        CWriter::`scalar deleting destructor'((CWriter *)v20, v21);
        goto LABEL_49;
      }
      v23 = g_pboMasterRoot;
    }
    v27 = CMDBaseObject::NextChildObject(v23, 0);
    for ( j = 0; v27 && (unsigned int)j < v24; j = (unsigned int)(v30 + 1) )
    {
      *(_QWORD *)&v15[8 * j] = v27;
      v27 = CMDBaseObject::NextChildObject(v28, v27);
    }
    qsort(v15, v24, 8u, (_CoreCrtNonSecureSearchSortCompareFunction)MyComparePBaseObject);
    v31 = 0;
    while ( (unsigned int)v31 < v24 )
    {
      v32 = g_cchSchema;
      Name = (const wchar_t *)CMDBaseObject::GetName(*(CMDBaseObject **)&v15[8 * v31], 1, 0);
      if ( _wcsnicmp(Name, L"Schema", v32) )
      {
        v34 = g_cchLM;
        v35 = (const wchar_t *)CMDBaseObject::GetName(*(CMDBaseObject **)&v15[8 * v31], 1, 0);
        v36 = _wcsnicmp(v35, L"LM", v34);
        v11 = SaveTree((struct CWriter *)v20, *(struct CMDBaseObject **)&v15[8 * v31], v14, a1, a2, 1, 1, v36 == 0);
      }
      v31 = (unsigned int)(v31 + 1);
      if ( v11 < 0 )
        goto LABEL_47;
    }
    v11 = CWriter::EndWrite((__int64)v20, 1);
    goto LABEL_47;
  }
LABEL_49:
  BUFFER::FreeMemory(v14);
  BUFFER::`scalar deleting destructor'(v14, v37);
  if ( v15 && v15 != Base )
    operator delete(v15);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180023df4  mov     [rsp+arg_18], rbx
0x180023df9  push    rbp
0x180023dfa  push    rsi
0x180023dfb  push    rdi
0x180023dfc  push    r12
0x180023dfe  push    r13
0x180023e00  push    r14
0x180023e02  push    r15
0x180023e04  sub     rsp, 0A0h
0x180023e0b  mov     rax, cs:__security_cookie
0x180023e12  xor     rax, rsp
0x180023e15  mov     [rsp+0D8h+var_48], rax
0x180023e1d  mov     rsi, [rsp+0D8h+arg_20]
0x180023e25  mov     ebx, r8d
0x180023e28  mov     r12, [rsp+0D8h+arg_28]
0x180023e30  mov     r13, rcx
0x180023e33  mov     [rsp+0D8h+var_98], rdx
0x180023e38  lea     rcx, [rsp+0D8h+Base]; void *
0x180023e3d  xor     edx, edx; Val
0x180023e3f  mov     r14, r9
0x180023e42  lea     r8d, [rdx+40h]; Size
0x180023e46  call    memset_0
0x180023e4b  test    ebx, ebx
0x180023e4d  jz      short loc_180023E88
0x180023e4f  mov     ecx, ebx; unsigned int
0x180023e51  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x180023e56  test    rax, rax
0x180023e59  jz      short loc_180023E7E
0x180023e5b  mov     rcx, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; CMDBaseObject * g_pboMasterRoot
0x180023e62  cmp     [rax+18h], rcx
0x180023e66  jnz     short loc_180023E7E
0x180023e68  test    byte ptr [rax+0Ch], 1
0x180023e6c  jnz     short loc_180023E88
0x180023e6e  test    byte ptr [rax+0Ch], 2
0x180023e72  jnz     short loc_180023E88
0x180023e74  mov     edi, 80070005h
0x180023e79  jmp     loc_180024278
0x180023e7e  mov     edi, 80070006h
0x180023e83  jmp     loc_180024278
0x180023e88  mov     ecx, 30h ; '0'; Size
0x180023e8d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023e92  test    rax, rax
0x180023e95  jz      loc_180024273
0x180023e9b  mov     rcx, rax
0x180023e9e  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180023ea4  mov     rbp, rax
0x180023ea7  test    rax, rax
0x180023eaa  jz      loc_180024273
0x180023eb0  mov     rcx, rax
0x180023eb3  lea     r15, [rsp+0D8h+Base]
0x180023eb8  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180023ebe  mov     ecx, 2Fh ; '/'
0x180023ec3  mov     [rax], cx
0x180023ec6  mov     rcx, rbp
0x180023ec9  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180023ecf  xor     ecx, ecx
0x180023ed1  mov     [rax+2], cx
0x180023ed5  test    r14, r14
0x180023ed8  jz      short loc_180023EE2
0x180023eda  inc     cs:?g_dwSchemaChangeNumber@@3KA; ulong g_dwSchemaChangeNumber
0x180023ee0  jmp     short loc_180023F35
0x180023ee2  mov     ecx, 1
0x180023ee7  call    ?UnlockMetabaseFile@@YAJW4_eMetabaseFile@@H@Z; UnlockMetabaseFile(_eMetabaseFile,int)
0x180023eec  test    byte ptr cs:g_dwDebugFlags, 3
0x180023ef3  mov     edi, eax
0x180023ef5  jz      short loc_180023F2D
0x180023ef7  mov     rcx, cs:g_pDebug
0x180023efe  lea     r9, aSaveentiretree; "SaveEntireTree"
0x180023f05  mov     [rsp+0D8h+var_A8], eax
0x180023f09  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180023f10  lea     rax, aSavealldataUnl; "[SaveAllData] Unlocking metabase file %"...
0x180023f17  mov     qword ptr [rsp+0D8h+var_B0], rsi
0x180023f1c  mov     r8d, 20D9h
0x180023f22  mov     [rsp+0D8h+var_B8], rax
0x180023f27  call    cs:__imp_PuDbgPrintW
0x180023f2d  test    edi, edi
0x180023f2f  js      loc_180024249
0x180023f35  mov     rdx, r12; struct _SECURITY_ATTRIBUTES *
0x180023f38  mov     rcx, rsi; unsigned __int16 *
0x180023f3b  call    ?SaveSchemaIfNeeded@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; SaveSchemaIfNeeded(ushort const *,_SECURITY_ATTRIBUTES *)
0x180023f40  mov     edi, eax
0x180023f42  test    r14, r14
0x180023f45  jnz     short loc_180023FA7
0x180023f47  lea     edx, [r14+1]
0x180023f4b  mov     rcx, rsi
0x180023f4e  call    ?LockMetabaseFile@@YAJPEBGW4_eMetabaseFile@@H@Z; LockMetabaseFile(ushort const *,_eMetabaseFile,int)
0x180023f53  test    byte ptr cs:g_dwDebugFlags, 3
0x180023f5a  mov     ebx, eax
0x180023f5c  jz      short loc_180023F94
0x180023f5e  mov     rcx, cs:g_pDebug
0x180023f65  lea     r9, aSaveentiretree; "SaveEntireTree"
0x180023f6c  mov     [rsp+0D8h+var_A8], eax
0x180023f70  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180023f77  lea     rax, aSavealldataLoc; "[SaveAllData] Locking metabase file %s "...
0x180023f7e  mov     qword ptr [rsp+0D8h+var_B0], rsi
0x180023f83  mov     r8d, 20F2h
0x180023f89  mov     [rsp+0D8h+var_B8], rax
0x180023f8e  call    cs:__imp_PuDbgPrintW
0x180023f94  test    ebx, ebx
0x180023f96  jns     short loc_180023FA7
0x180023f98  test    edi, edi
0x180023f9a  js      loc_180024249
0x180023fa0  mov     edi, ebx
0x180023fa2  jmp     loc_180024249
0x180023fa7  test    edi, edi
0x180023fa9  js      loc_180024249
0x180023faf  test    byte ptr cs:g_dwDebugFlags, 3
0x180023fb6  jz      short loc_180024004
0x180023fb8  mov     rax, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x180023fbf  lea     r9, aSaveentiretree; "SaveEntireTree"
0x180023fc6  mov     r8d, 2105h
0x180023fcc  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180023fd3  mov     rcx, [rax+0F8h]
0x180023fda  mov     rax, cs:?g_wszTempFileName@@3PEAGEA; ushort * g_wszTempFileName
0x180023fe1  mov     qword ptr [rsp+0D8h+var_A8], rcx
0x180023fe6  mov     rcx, cs:g_pDebug
0x180023fed  mov     qword ptr [rsp+0D8h+var_B0], rax
0x180023ff2  lea     rax, aSavealldataIni; "[SaveAllData] Initializing writer with "...
0x180023ff9  mov     [rsp+0D8h+var_B8], rax
0x180023ffe  call    cs:__imp_PuDbgPrintW
0x180024004  mov     ecx, 10050h; Size
0x180024009  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002400e  mov     rsi, rax
0x180024011  test    rax, rax
0x180024014  jz      loc_180024244
0x18002401a  mov     r9, [rsp+0D8h+arg_30]; void *
0x180024022  or      r12, 0FFFFFFFFFFFFFFFFh
0x180024026  mov     [rax+10038h], r12
0x18002402d  mov     rcx, rax; this
0x180024030  mov     qword ptr [rax], 0
0x180024037  mov     qword ptr [rax+8], 0
0x18002403f  mov     qword ptr [rax+10040h], 0
0x18002404a  mov     qword ptr [rax+10048h], 0
0x180024055  mov     dword ptr [rax+10h], 0
0x18002405c  mov     qword ptr [rax+10018h], 0
0x180024067  mov     qword ptr [rax+10020h], 0
0x180024072  mov     qword ptr [rax+10028h], 0
0x18002407d  mov     qword ptr [rax+10030h], 0
0x180024088  mov     r8, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; struct CWriterGlobalHelper *
0x18002408f  mov     rdx, cs:?g_wszTempFileName@@3PEAGEA; unsigned __int16 *
0x180024096  call    ?Initialize@CWriter@@QEAAJPEBGPEAVCWriterGlobalHelper@@PEAX@Z; CWriter::Initialize(ushort const *,CWriterGlobalHelper *,void *)
0x18002409b  mov     edi, eax
0x18002409d  test    eax, eax
0x18002409f  js      loc_18002423A
0x1800240a5  xor     r8d, r8d
0x1800240a8  lea     edx, [r12+2]
0x1800240ad  mov     rcx, rsi
0x1800240b0  call    ?BeginWrite@CWriter@@QEAAJW4eWriter@@PEAU_SECURITY_ATTRIBUTES@@@Z; CWriter::BeginWrite(eWriter,_SECURITY_ATTRIBUTES *)
0x1800240b5  mov     edi, eax
0x1800240b7  test    eax, eax
0x1800240b9  js      loc_18002423A
0x1800240bf  mov     rdx, [rsp+0D8h+var_98]; struct _IIS_CRYPTO_BLOB *
0x1800240c4  xor     r8d, r8d; bool
0x1800240c7  mov     rcx, rsi; struct CWriter *
0x1800240ca  call    ?SaveGlobalsToXML@@YAJPEAVCWriter@@PEFAU_IIS_CRYPTO_BLOB@@_N@Z; SaveGlobalsToXML(CWriter *,_IIS_CRYPTO_BLOB *,bool)
0x1800240cf  mov     edi, eax
0x1800240d1  test    eax, eax
0x1800240d3  js      loc_18002423A
0x1800240d9  mov     rdx, r13; struct IIS_CRYPTO_STORAGE *
0x1800240dc  mov     rcx, rsi; struct CWriter *
0x1800240df  call    ?SaveMasterRoot@@YAJPEAVCWriter@@PEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@@Z; SaveMasterRoot(CWriter *,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *)
0x1800240e4  mov     edi, eax
0x1800240e6  test    eax, eax
0x1800240e8  js      loc_18002423A
0x1800240ee  mov     r9, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; CMDBaseObject * g_pboMasterRoot
0x1800240f5  xor     r14d, r14d
0x1800240f8  xor     edx, edx; struct CMDBaseObject *
0x1800240fa  mov     rcx, r9; this
0x1800240fd  call    ?NextChildObject@CMDBaseObject@@QEAAPEAV1@PEAV1@@Z; CMDBaseObject::NextChildObject(CMDBaseObject *)
0x180024102  test    rax, rax
0x180024105  jz      short loc_18002410F
0x180024107  inc     r14d
0x18002410a  mov     rdx, rax
0x18002410d  jmp     short loc_1800240FA
0x18002410f  mov     ebx, 8
0x180024114  cmp     r14d, ebx
0x180024117  jbe     short loc_180024146
0x180024119  mov     ecx, r14d
0x18002411c  mov     eax, ebx
0x18002411e  mul     rcx
0x180024121  cmovb   rax, r12
0x180024125  mov     rcx, rax; unsigned __int64
0x180024128  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002412d  mov     r15, rax
0x180024130  test    rax, rax
0x180024133  jnz     short loc_18002413F
0x180024135  mov     edi, 8007000Eh
0x18002413a  jmp     loc_18002423A
0x18002413f  mov     r9, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; CMDBaseObject * g_pboMasterRoot
0x180024146  xor     edx, edx; struct CMDBaseObject *
0x180024148  mov     rcx, r9; this
0x18002414b  call    ?NextChildObject@CMDBaseObject@@QEAAPEAV1@PEAV1@@Z; CMDBaseObject::NextChildObject(CMDBaseObject *)
0x180024150  xor     r10d, r10d
0x180024153  test    rax, rax
0x180024156  jz      short loc_180024171
0x180024158  cmp     r10d, r14d
0x18002415b  jnb     short loc_180024171
0x18002415d  mov     rdx, rax; struct CMDBaseObject *
0x180024160  mov     [r15+r10*8], rax
0x180024164  mov     rcx, r9; this
0x180024167  call    ?NextChildObject@CMDBaseObject@@QEAAPEAV1@PEAV1@@Z; CMDBaseObject::NextChildObject(CMDBaseObject *)
0x18002416c  inc     r10d
0x18002416f  jmp     short loc_180024153
0x180024171  mov     edx, r14d; NumOfElements
0x180024174  lea     r9, ?MyComparePBaseObject@@YAHPEBX0@Z; CompareFunction
0x18002417b  mov     r8, rbx; SizeOfElements
0x18002417e  mov     rcx, r15; Base
0x180024181  call    cs:__imp_qsort
0x180024187  xor     r12d, r12d
0x18002418a  mov     edx, 1; int
0x18002418f  cmp     r12d, r14d
0x180024192  jnb     loc_180024230
0x180024198  mov     rcx, [r15+r12*8]; this
0x18002419c  xor     r8d, r8d; unsigned int *
0x18002419f  mov     ebx, cs:?g_cchSchema@@3KA; ulong g_cchSchema
0x1800241a5  call    ?GetName@CMDBaseObject@@QEAAPEADHPEAK@Z; CMDBaseObject::GetName(int,ulong *)
0x1800241aa  mov     r8d, ebx; MaxCount
0x1800241ad  lea     rdx, aSchema_4; "Schema"
0x1800241b4  mov     rcx, rax; String1
0x1800241b7  call    cs:__imp__wcsnicmp
0x1800241bd  test    eax, eax
0x1800241bf  jz      short loc_180024223
0x1800241c1  mov     rcx, [r15+r12*8]; this
0x1800241c5  xor     r8d, r8d; unsigned int *
0x1800241c8  mov     ebx, cs:?g_cchLM@@3KA; ulong g_cchLM
0x1800241ce  lea     edx, [r8+1]; int
0x1800241d2  call    ?GetName@CMDBaseObject@@QEAAPEADHPEAK@Z; CMDBaseObject::GetName(int,ulong *)
0x1800241d7  mov     r8d, ebx; MaxCount
0x1800241da  lea     rdx, aLm; "LM"
0x1800241e1  mov     rcx, rax; String1
0x1800241e4  call    cs:__imp__wcsnicmp
0x1800241ea  mov     rdx, [r15+r12*8]; struct CMDBaseObject *
0x1800241ee  xor     ecx, ecx
0x1800241f0  test    eax, eax
0x1800241f2  mov     r9, r13; struct IIS_CRYPTO_STORAGE *
0x1800241f5  mov     rax, [rsp+0D8h+var_98]
0x1800241fa  mov     r8, rbp; struct BUFFER *
0x1800241fd  setz    cl
0x180024200  mov     [rsp+0D8h+var_A0], ecx; int
0x180024204  mov     rcx, rsi; struct CWriter *
0x180024207  mov     [rsp+0D8h+var_A8], 1; int
0x18002420f  mov     [rsp+0D8h+var_B0], 1; int
0x180024217  mov     [rsp+0D8h+var_B8], rax; struct _IIS_CRYPTO_BLOB *
0x18002421c  call    ?SaveTree@@YAJPEAVCWriter@@PEAVCMDBaseObject@@PEAVBUFFER@@PEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@HHH@Z; SaveTree(CWriter *,CMDBaseObject *,BUFFER *,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *,int,int,int)
0x180024221  mov     edi, eax
0x180024223  inc     r12d
0x180024226  test    edi, edi
0x180024228  jns     loc_18002418A
0x18002422e  jmp     short loc_18002423A
0x180024230  mov     rcx, rsi
0x180024233  call    ?EndWrite@CWriter@@QEAAJW4eWriter@@@Z; CWriter::EndWrite(eWriter)
0x180024238  mov     edi, eax
0x18002423a  mov     rcx, rsi; this
0x18002423d  call    ??_GCWriter@@QEAAPEAXI@Z; CWriter::`scalar deleting destructor'(uint)
0x180024242  jmp     short loc_180024249
0x180024244  mov     edi, 8007000Eh
0x180024249  mov     rcx, rbp
0x18002424c  call    cs:__imp_?FreeMemory@BUFFER@@QEAAXXZ; BUFFER::FreeMemory(void)
0x180024252  mov     rcx, rbp; this
0x180024255  call    ??_GBUFFER@@QEAAPEAXI@Z; BUFFER::`scalar deleting destructor'(uint)
0x18002425a  test    r15, r15
0x18002425d  jz      short loc_180024278
0x18002425f  lea     rax, [rsp+0D8h+Base]
0x180024264  cmp     r15, rax
0x180024267  jz      short loc_180024278
0x180024269  mov     rcx, r15; Block
0x18002426c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024271  jmp     short loc_180024278
0x180024273  mov     edi, 8007000Eh
0x180024278  mov     eax, edi
0x18002427a  mov     rcx, [rsp+0D8h+var_48]
0x180024282  xor     rcx, rsp; StackCookie
0x180024285  call    __security_check_cookie
0x18002428a  mov     rbx, [rsp+0D8h+arg_18]
0x180024292  add     rsp, 0A0h
0x180024299  pop     r15
0x18002429b  pop     r14
0x18002429d  pop     r13
0x18002429f  pop     r12
0x1800242a1  pop     rdi
0x1800242a2  pop     rsi
0x1800242a3  pop     rbp
0x1800242a4  retn
```
