# CDataCollection::InternalCollectDumpAndRegisteredFilesFromProcess(ulong,ulong,ulong,ulong,wchar_t const *,CFileList *,void *,int)

- ea: `0x180009190`
- end: `0x1800096c5`
- name: `?InternalCollectDumpAndRegisteredFilesFromProcess@CDataCollection@@AEAAJKKKKPEB_WPEAVCFileList@@PEAXH@Z`
- size: `1333`
- prototype: `__int64 __fastcall(CDataCollection *this, unsigned int, unsigned int, unsigned int, enum _MINIDUMP_TYPE, wchar_t *, struct CFileList *, void *, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180008030`
- `0x180008490`

## callees

- `0x180002890`
- `0x1800028b4`
- `0x180007924`
- `0x180007db8`
- `0x180008be4`
- `0x180009190`
- `0x180009ed8`
- `0x180009f00`
- `0x180009f40`
- `0x18000a074`
- `0x180038d80`
- `0x18003e760`
- `0x18003e894`
- `0x18003f624`
- `0x18003f818`
- `0x1800401c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000920b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000920b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009396`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009396`
- `ntdll!wcsrchr` at `0x18000956f`
- `ntdll!wcsrchr` at `0x18000956f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009499`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800094da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009499`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800094da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800094b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009546`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800094b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009546`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009475`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009610`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009475`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009610`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180009434`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180009434`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800093c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180009426`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800093c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180009426`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000936b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000936b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000943d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000943d`

## pseudocode

```c
__int64 __fastcall CDataCollection::InternalCollectDumpAndRegisteredFilesFromProcess(
        CDataCollection *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        enum _MINIDUMP_TYPE a5,
        wchar_t *a6,
        struct CFileList *a7,
        void *a8,
        int a9)
{
  enum _WER_FILE_TYPE v12; // esi
  int v13; // ebx
  const wchar_t *DumpSuffix; // rax
  unsigned int v15; // r9d
  int v16; // ebx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  int v19; // eax
  struct _TP_WAIT *ThreadpoolWait; // rax
  struct _TP_WAIT *v21; // r15
  DWORD LastError; // eax
  const wchar_t *v23; // rax
  CDataCollection *v24; // rcx
  HANDLE v25; // r15
  char v26; // r14
  _QWORD *v27; // r14
  _QWORD *v28; // rcx
  _QWORD *v29; // rcx
  __int64 v30; // r9
  enum _WER_FILE_TYPE v32; // [rsp+28h] [rbp-D8h]
  unsigned int v33; // [rsp+40h] [rbp-C0h]
  int v34; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 v35[4]; // [rsp+54h] [rbp-ACh]
  unsigned int v36; // [rsp+58h] [rbp-A8h]
  HANDLE h; // [rsp+60h] [rbp-A0h]
  wchar_t *v38; // [rsp+68h] [rbp-98h]
  char v39; // [rsp+70h] [rbp-90h]
  wchar_t *Str; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v41; // [rsp+80h] [rbp-80h]
  _WORD v42[8]; // [rsp+88h] [rbp-78h] BYREF
  struct _TP_WAIT *v43; // [rsp+98h] [rbp-68h]
  struct CFileList *v44; // [rsp+A0h] [rbp-60h]
  __int128 v45; // [rsp+A8h] [rbp-58h]
  __int64 v46; // [rsp+B8h] [rbp-48h]
  struct _RTL_CRITICAL_SECTION pv[28]; // [rsp+C0h] [rbp-40h] BYREF
  void *v48; // [rsp+540h] [rbp+440h]
  wchar_t v49[268]; // [rsp+A40h] [rbp+940h] BYREF

  v36 = a4;
  v38 = a6;
  v44 = a7;
  h = a8;
  v43 = 0;
  CDumpCollection::CDumpCollection((CDumpCollection *)pv);
  v34 = 0;
  if ( a2 == GetCurrentProcessId() || (a5 & 0xFA000000) != 0 || !a7 )
  {
    v16 = -2147024809;
    goto LABEL_58;
  }
  if ( (a5 & 0x200) != 0 )
    v12 = WerFileTypeHeapdump;
  else
    v12 = (a5 & 0x100000 | 0x80000u) >> 18;
  v13 = a9 != 0;
  if ( a4 == 1073741855 )
    v13 = 2;
  *(_DWORD *)v35 = v13;
  if ( UtilIsProtectedProcessByPid(a2) )
  {
    DumpSuffix = GetDumpSuffix(a5, v13);
    v16 = CDataCollection::CollectSecureDump((CDataCollection *)v49, a2, a3, v15, DumpSuffix, v12, a6, v49, v33, h);
    if ( v16 < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v18 = 31;
LABEL_14:
        WPP_SF_Dd(v17[2], v18, &WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids, a2, a3);
        goto LABEL_58;
      }
      goto LABEL_58;
    }
LABEL_56:
    CFileList::AddFile((__int64)v44, v49, v12, 0, a9 != 0 ? 4 : 1, a2, v34);
    goto LABEL_58;
  }
  v19 = CDumpCollection::Init((CDumpCollection *)pv, a2, a3);
  v16 = v19;
  if ( v19 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        &WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids,
        (unsigned int)v19);
    goto LABEL_58;
  }
  ThreadpoolWait = CreateThreadpoolWait(CDataCollection::StaticCancelDumpCollection, pv, 0);
  v21 = ThreadpoolWait;
  v43 = ThreadpoolWait;
  if ( ThreadpoolWait )
  {
    SetThreadpoolWait(ThreadpoolWait, h, 0);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids, LastError);
  }
  v23 = GetDumpSuffix(a5, v35[0]);
  v16 = CDataCollection::CollectDump(v24, (struct CDumpCollection *)pv, v36, v23, a5, v32, v38, v49, v33, &v34);
  v43 = 0;
  if ( v21 )
  {
    SetThreadpoolWait(v21, 0, 0);
    WaitForThreadpoolWaitCallbacks(v21, 1);
    CloseThreadpoolWait(v21);
  }
  if ( v16 >= 0 )
  {
    v25 = h;
    if ( WaitForSingleObject(h, 0) != 258 )
    {
      v16 = -2147023673;
      goto LABEL_58;
    }
    v38 = (wchar_t *)pv;
    EnterCriticalSection(pv);
    v39 = 1;
    CDumpCollection::_GatherAdditionalInformation((CDumpCollection *)pv);
    LeaveCriticalSection(pv);
    Str = v42;
    v41 = v42;
    v42[0] = 0;
    while ( 1 )
    {
      EnterCriticalSection(pv);
      if ( v48 == (void *)-1LL )
      {
        v41 = Str;
        *Str = 0;
        v26 = 0;
      }
      else
      {
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(&Str, (char *)v48 + 8);
        v27 = v48;
        v48 = *(void **)v48;
        v28 = (_QWORD *)v27[1];
        if ( v28 != v27 + 3 )
          operator delete(v28, (const struct std::nothrow_t *)&std::nothrow);
        operator delete(v27, (const struct std::nothrow_t *)&std::nothrow);
        v26 = 1;
      }
      LeaveCriticalSection(pv);
      if ( !v26 )
        break;
      v45 = 0;
      v46 = 0;
      if ( Str )
      {
        wcsrchr(Str, 0x2Eu);
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            &WPP_5830178aa191323d89eeb6488c1e9d69_Traceguids,
            2147500033LL);
          v29 = WPP_GLOBAL_Control;
        }
        v30 = 2147500033LL;
        v16 = -2147467263;
      }
      else
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_5830178aa191323d89eeb6488c1e9d69_Traceguids);
          v29 = WPP_GLOBAL_Control;
        }
        v16 = -2147024809;
        v30 = 2147942487LL;
      }
      if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 1) != 0 )
        WPP_SF_d(v29[2], 34, &WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids, v30);
      if ( WaitForSingleObject(v25, 0) != 258 )
      {
        v16 = -2147023673;
        if ( Str != v42 )
          operator delete(Str, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_58;
      }
    }
    if ( Str != v42 )
      operator delete(Str, (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_56;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v18 = 33;
    goto LABEL_14;
  }
LABEL_58:
  CDumpCollection::~CDumpCollection((CDumpCollection *)pv);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180009190  mov     [rsp-8+arg_0], rbx
0x180009195  push    rbp
0x180009196  push    rsi
0x180009197  push    rdi
0x180009198  push    r12
0x18000919a  push    r13
0x18000919c  push    r14
0x18000919e  push    r15
0x1800091a0  lea     rbp, [rsp-0B60h]
0x1800091a8  sub     rsp, 0C60h
0x1800091af  mov     rax, cs:__security_cookie
0x1800091b6  xor     rax, rsp
0x1800091b9  mov     [rbp+0B90h+var_38], rax
0x1800091c0  mov     edi, r9d
0x1800091c3  mov     [rsp+0C90h+var_C38], r9d
0x1800091c8  mov     r12d, r8d
0x1800091cb  mov     r13d, edx
0x1800091ce  mov     r15, [rbp+0B90h+arg_28]
0x1800091d5  mov     [rsp+0C90h+var_C28], r15
0x1800091da  mov     rbx, [rbp+0B90h+arg_30]
0x1800091e1  mov     [rbp+0B90h+var_BF0], rbx
0x1800091e5  mov     rax, [rbp+0B90h+arg_38]
0x1800091ec  mov     [rsp+0C90h+h], rax
0x1800091f1  mov     [rbp+0B90h+var_BF8], 0
0x1800091f9  lea     rcx, [rbp+0B90h+pv]; this
0x1800091fd  call    ??0CDumpCollection@@QEAA@XZ; CDumpCollection::CDumpCollection(void)
0x180009202  nop
0x180009203  mov     [rsp+0C90h+var_C40], 0
0x18000920b  call    cs:__imp_GetCurrentProcessId
0x180009211  cmp     r13d, eax
0x180009214  jz      loc_18000968A
0x18000921a  mov     r14d, [rbp+0B90h+arg_20]
0x180009221  test    r14d, 0FA000000h
0x180009228  jnz     loc_18000968A
0x18000922e  test    rbx, rbx
0x180009231  jz      loc_18000968A
0x180009237  bt      r14d, 9
0x18000923c  jnb     short loc_180009245
0x18000923e  mov     esi, 3
0x180009243  jmp     short loc_180009255
0x180009245  mov     esi, r14d
0x180009248  and     esi, 100000h
0x18000924e  bts     esi, 13h
0x180009252  shr     esi, 12h
0x180009255  cmp     [rbp+0B90h+arg_40], 0
0x18000925c  setnz   al
0x18000925f  movzx   ebx, al
0x180009262  mov     eax, 2
0x180009267  cmp     edi, 4000001Fh
0x18000926d  cmovz   ebx, eax
0x180009270  mov     dword ptr [rsp+0C90h+var_C3C], ebx
0x180009274  mov     ecx, r13d; dwProcessId
0x180009277  call    ?UtilIsProtectedProcessByPid@@YA_NK@Z; UtilIsProtectedProcessByPid(ulong)
0x18000927c  test    al, al
0x18000927e  jz      loc_18000930A
0x180009284  mov     dl, bl; unsigned __int8
0x180009286  mov     ecx, r14d; enum _MINIDUMP_TYPE
0x180009289  call    ?GetDumpSuffix@@YAPEB_WW4_MINIDUMP_TYPE@@E@Z; GetDumpSuffix(_MINIDUMP_TYPE,uchar)
0x18000928e  mov     rdx, [rsp+0C90h+h]
0x180009293  mov     [rsp+0C90h+var_C48], rdx; void *
0x180009298  lea     rcx, [rbp+0B90h+var_250]; this
0x18000929f  mov     [rsp+0C90h+var_C58], rcx; wchar_t *
0x1800092a4  mov     [rsp+0C90h+var_C60], r15; wchar_t *
0x1800092a9  mov     [rsp+0C90h+var_C68], esi; enum _WER_FILE_TYPE
0x1800092ad  mov     qword ptr [rsp+0C90h+var_C70], rax; wchar_t *
0x1800092b2  mov     r8d, r12d; unsigned int
0x1800092b5  mov     edx, r13d; unsigned int
0x1800092b8  call    ?CollectSecureDump@CDataCollection@@AEAAJKKKPEB_WW4_WER_FILE_TYPE@@0PEA_WKPEAX@Z; CDataCollection::CollectSecureDump(ulong,ulong,ulong,wchar_t const *,_WER_FILE_TYPE,wchar_t const *,wchar_t *,ulong,void *)
0x1800092bd  mov     ebx, eax
0x1800092bf  test    eax, eax
0x1800092c1  jns     loc_180009654
0x1800092c7  lea     rdi, WPP_GLOBAL_Control
0x1800092ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092d5  cmp     rcx, rdi
0x1800092d8  jz      loc_18000968F
0x1800092de  test    byte ptr [rcx+1Ch], 1
0x1800092e2  jz      loc_18000968F
0x1800092e8  mov     edx, 1Fh
0x1800092ed  mov     [rsp+0C90h+var_C70], r12d
0x1800092f2  mov     r9d, r13d
0x1800092f5  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x1800092fc  mov     rcx, [rcx+10h]
0x180009300  call    WPP_SF_Dd
0x180009305  jmp     loc_18000968F
0x18000930a  mov     r8d, r12d; unsigned int
0x18000930d  mov     edx, r13d; dwProcessId
0x180009310  lea     rcx, [rbp+0B90h+pv]; this
0x180009314  call    ?Init@CDumpCollection@@QEAAJKK@Z; CDumpCollection::Init(ulong,ulong)
0x180009319  mov     ebx, eax
0x18000931b  test    eax, eax
0x18000931d  jns     short loc_18000935D
0x18000931f  lea     rdi, WPP_GLOBAL_Control
0x180009326  mov     rcx, cs:WPP_GLOBAL_Control
0x18000932d  cmp     rcx, rdi
0x180009330  jz      loc_18000968F
0x180009336  test    byte ptr [rcx+1Ch], 1
0x18000933a  jz      loc_18000968F
0x180009340  mov     edx, 20h ; ' '
0x180009345  mov     r9d, eax
0x180009348  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x18000934f  mov     rcx, [rcx+10h]
0x180009353  call    WPP_SF_d
0x180009358  jmp     loc_18000968F
0x18000935d  xor     r8d, r8d; pcbe
0x180009360  lea     rdx, [rbp+0B90h+pv]; pv
0x180009364  lea     rcx, ?StaticCancelDumpCollection@CDataCollection@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18000936b  call    cs:__imp_CreateThreadpoolWait
0x180009371  mov     r15, rax
0x180009374  mov     [rbp+0B90h+var_BF8], rax
0x180009378  lea     rdi, WPP_GLOBAL_Control
0x18000937f  test    rax, rax
0x180009382  jnz     short loc_1800093BC
0x180009384  mov     rax, cs:WPP_GLOBAL_Control
0x18000938b  cmp     rax, rdi
0x18000938e  jz      short loc_1800093CD
0x180009390  test    byte ptr [rax+1Ch], 1
0x180009394  jz      short loc_1800093CD
0x180009396  call    cs:__imp_GetLastError
0x18000939c  lea     edx, [r15+1Ah]
0x1800093a0  mov     r9d, eax
0x1800093a3  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x1800093aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093b1  mov     rcx, [rcx+10h]
0x1800093b5  call    WPP_SF_d
0x1800093ba  jmp     short loc_1800093CD
0x1800093bc  xor     r8d, r8d; pftTimeout
0x1800093bf  mov     rdx, [rsp+0C90h+h]; h
0x1800093c4  mov     rcx, r15; pwa
0x1800093c7  call    cs:__imp_SetThreadpoolWait
0x1800093cd  mov     dl, [rsp+0C90h+var_C3C]; unsigned __int8
0x1800093d1  mov     ecx, r14d; enum _MINIDUMP_TYPE
0x1800093d4  call    ?GetDumpSuffix@@YAPEB_WW4_MINIDUMP_TYPE@@E@Z; GetDumpSuffix(_MINIDUMP_TYPE,uchar)
0x1800093d9  mov     r9, rax; wchar_t *
0x1800093dc  lea     rax, [rsp+0C90h+var_C40]
0x1800093e1  mov     [rsp+0C90h+var_C48], rax; int *
0x1800093e6  lea     rax, [rbp+0B90h+var_250]
0x1800093ed  mov     [rsp+0C90h+var_C58], rax; wchar_t *
0x1800093f2  mov     rax, [rsp+0C90h+var_C28]
0x1800093f7  mov     [rsp+0C90h+var_C60], rax; wchar_t *
0x1800093fc  mov     [rsp+0C90h+var_C70], r14d; enum _MINIDUMP_TYPE
0x180009401  mov     r8d, [rsp+0C90h+var_C38]; unsigned int
0x180009406  lea     rdx, [rbp+0B90h+pv]; struct CDumpCollection *
0x18000940a  call    ?CollectDump@CDataCollection@@AEAAJPEAVCDumpCollection@@KPEB_WW4_MINIDUMP_TYPE@@W4_WER_FILE_TYPE@@1PEA_WKPEAH@Z; CDataCollection::CollectDump(CDumpCollection *,ulong,wchar_t const *,_MINIDUMP_TYPE,_WER_FILE_TYPE,wchar_t const *,wchar_t *,ulong,int *)
0x18000940f  mov     ebx, eax
0x180009411  mov     [rbp+0B90h+var_BF8], 0
0x180009419  test    r15, r15
0x18000941c  jz      short loc_180009443
0x18000941e  xor     r8d, r8d; pftTimeout
0x180009421  xor     edx, edx; h
0x180009423  mov     rcx, r15; pwa
0x180009426  call    cs:__imp_SetThreadpoolWait
0x18000942c  mov     edx, 1; fCancelPendingCallbacks
0x180009431  mov     rcx, r15; pwa
0x180009434  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000943a  mov     rcx, r15; pwa
0x18000943d  call    cs:__imp_CloseThreadpoolWait
0x180009443  test    ebx, ebx
0x180009445  jns     short loc_18000946B
0x180009447  mov     rcx, cs:WPP_GLOBAL_Control
0x18000944e  cmp     rcx, rdi
0x180009451  jz      loc_18000968F
0x180009457  test    byte ptr [rcx+1Ch], 1
0x18000945b  jz      loc_18000968F
0x180009461  mov     edx, 21h ; '!'
0x180009466  jmp     loc_1800092ED
0x18000946b  xor     edx, edx; dwMilliseconds
0x18000946d  mov     r15, [rsp+0C90h+h]
0x180009472  mov     rcx, r15; hHandle
0x180009475  call    cs:__imp_WaitForSingleObject
0x18000947b  cmp     eax, 102h
0x180009480  jz      short loc_18000948C
0x180009482  mov     ebx, 800704C7h
0x180009487  jmp     loc_18000968F
0x18000948c  lea     rax, [rbp+0B90h+pv]
0x180009490  mov     [rsp+0C90h+var_C28], rax
0x180009495  lea     rcx, [rbp+0B90h+pv]; lpCriticalSection
0x180009499  call    cs:__imp_EnterCriticalSection
0x18000949f  mov     [rsp+0C90h+var_C20], 1
0x1800094a4  lea     rcx, [rbp+0B90h+pv]; this
0x1800094a8  call    ?_GatherAdditionalInformation@CDumpCollection@@AEAAJXZ; CDumpCollection::_GatherAdditionalInformation(void)
0x1800094ad  nop
0x1800094ae  lea     rcx, [rbp+0B90h+pv]; lpCriticalSection
0x1800094b2  call    cs:__imp_LeaveCriticalSection
0x1800094b8  lea     rax, [rbp+0B90h+var_C08]
0x1800094bc  mov     [rsp+0C90h+Str], rax
0x1800094c1  lea     rax, [rbp+0B90h+var_C08]
0x1800094c5  mov     [rbp+0B90h+var_C10], rax
0x1800094c9  xor     eax, eax
0x1800094cb  mov     [rbp+0B90h+var_C08], ax
0x1800094cf  lea     r12, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800094d6  lea     rcx, [rbp+0B90h+pv]; lpCriticalSection
0x1800094da  call    cs:__imp_EnterCriticalSection
0x1800094e0  mov     rdx, [rbp+0B90h+var_750]
0x1800094e7  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1800094eb  jnz     short loc_180009500
0x1800094ed  mov     rcx, [rsp+0C90h+Str]
0x1800094f2  mov     [rbp+0B90h+var_C10], rcx
0x1800094f6  xor     eax, eax
0x1800094f8  mov     [rcx], ax
0x1800094fb  xor     r14b, r14b
0x1800094fe  jmp     short loc_180009542
0x180009500  add     rdx, 8
0x180009504  lea     rcx, [rsp+0C90h+Str]
0x180009509  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18000950e  mov     r14, [rbp+0B90h+var_750]
0x180009515  mov     rax, [r14]
0x180009518  mov     [rbp+0B90h+var_750], rax
0x18000951f  mov     rcx, [r14+8]; void *
0x180009523  lea     rax, [r14+18h]
0x180009527  cmp     rcx, rax
0x18000952a  jz      short loc_180009534
0x18000952c  mov     rdx, r12; struct std::nothrow_t *
0x18000952f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009534  mov     rdx, r12; struct std::nothrow_t *
0x180009537  mov     rcx, r14; void *
0x18000953a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000953f  mov     r14b, 1
0x180009542  lea     rcx, [rbp+0B90h+pv]; lpCriticalSection
0x180009546  call    cs:__imp_LeaveCriticalSection
0x18000954c  test    r14b, r14b
0x18000954f  jz      loc_18000963E
0x180009555  mov     rcx, [rsp+0C90h+Str]; Str
0x18000955a  xorps   xmm0, xmm0
0x18000955d  xor     eax, eax
0x18000955f  movups  [rbp+0B90h+var_BE8], xmm0
0x180009563  mov     [rbp+0B90h+var_BD8], rax
0x180009567  test    rcx, rcx
0x18000956a  jz      short loc_1800095B5
0x18000956c  lea     edx, [rax+2Eh]; Ch
0x18000956f  call    cs:__imp_wcsrchr
0x180009575  mov     rcx, cs:WPP_GLOBAL_Control
0x18000957c  cmp     rcx, rdi
0x18000957f  jz      short loc_1800095A9
0x180009581  test    byte ptr [rcx+1Ch], 1
0x180009585  jz      short loc_1800095A9
0x180009587  mov     edx, 0Bh
0x18000958c  mov     r9d, 80004001h
0x180009592  lea     r8, WPP_5830178aa191323d89eeb6488c1e9d69_Traceguids
0x180009599  mov     rcx, [rcx+10h]
0x18000959d  call    WPP_SF_d
0x1800095a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095a9  mov     eax, 80004001h
0x1800095ae  mov     r9d, eax
0x1800095b1  mov     ebx, eax
0x1800095b3  jmp     short loc_1800095EB
0x1800095b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095bc  cmp     rcx, rdi
0x1800095bf  jz      short loc_1800095E3
0x1800095c1  test    byte ptr [rcx+1Ch], 1
0x1800095c5  jz      short loc_1800095E3
0x1800095c7  mov     edx, 0Ah
0x1800095cc  lea     r8, WPP_5830178aa191323d89eeb6488c1e9d69_Traceguids
0x1800095d3  mov     rcx, [rcx+10h]
0x1800095d7  call    WPP_SF_
0x1800095dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095e3  mov     ebx, 80070057h
0x1800095e8  mov     r9d, ebx
0x1800095eb  cmp     rcx, rdi
0x1800095ee  jz      short loc_18000960B
0x1800095f0  test    byte ptr [rcx+1Ch], 1
0x1800095f4  jz      short loc_18000960B
0x1800095f6  mov     edx, 22h ; '"'
0x1800095fb  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x180009602  mov     rcx, [rcx+10h]
0x180009606  call    WPP_SF_d
0x18000960b  xor     edx, edx; dwMilliseconds
0x18000960d  mov     rcx, r15; hHandle
0x180009610  call    cs:__imp_WaitForSingleObject
0x180009616  cmp     eax, 102h
0x18000961b  jz      loc_1800094D6
0x180009621  mov     ebx, 800704C7h
0x180009626  lea     rax, [rbp+0B90h+var_C08]
0x18000962a  mov     rcx, [rsp+0C90h+Str]; void *
0x18000962f  cmp     rcx, rax
0x180009632  jz      short loc_18000968F
0x180009634  mov     rdx, r12; struct std::nothrow_t *
0x180009637  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000963c  jmp     short loc_18000968F
0x18000963e  lea     rax, [rbp+0B90h+var_C08]
0x180009642  mov     rcx, [rsp+0C90h+Str]; void *
0x180009647  cmp     rcx, rax
0x18000964a  jz      short loc_180009654
0x18000964c  mov     rdx, r12; struct std::nothrow_t *
0x18000964f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009654  neg     [rbp+0B90h+arg_40]
0x18000965a  sbb     edx, edx
0x18000965c  and     edx, 3
0x18000965f  inc     edx
0x180009661  mov     eax, [rsp+0C90h+var_C40]
0x180009665  mov     dword ptr [rsp+0C90h+var_C60], eax
0x180009669  mov     [rsp+0C90h+var_C68], r13d
0x18000966e  mov     [rsp+0C90h+var_C70], edx
0x180009672  xor     r9d, r9d
0x180009675  mov     r8d, esi
0x180009678  lea     rdx, [rbp+0B90h+var_250]
0x18000967f  mov     rcx, [rbp+0B90h+var_BF0]
0x180009683  call    ?AddFile@CFileList@@QEAAJPEB_WW4_WER_FILE_TYPE@@KW4FAULTREP_CROSSPROCESS_FILE_TYPE@@KH@Z; CFileList::AddFile(wchar_t const *,_WER_FILE_TYPE,ulong,FAULTREP_CROSSPROCESS_FILE_TYPE,ulong,int)
0x180009688  jmp     short loc_18000968F
0x18000968a  mov     ebx, 80070057h
0x18000968f  lea     rcx, [rbp+0B90h+pv]; this
  ... truncated ...
```
