# CNamespaceHandle::ExecQuerySink(IWbemQuery *,ulong,ulong,IWbemObjectSink *,ulong *)

- ea: `0x180001750`
- end: `0x180001c72`
- name: `?ExecQuerySink@CNamespaceHandle@@QEAAJPEAUIWbemQuery@@KKPEAUIWbemObjectSink@@PEAK@Z`
- size: `1314`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, struct IWbemQuery *, __int64, int, struct IWbemObjectSink *, unsigned int *DestStr)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800032a0`

## callees

- `0x180001274`
- `0x1800012b8`
- `0x1800015d8`
- `0x180001750`
- `0x180001c80`
- `0x180002350`
- `0x180048010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800017f9`
- `msvcrt!_wcsnicmp` at `0x1800017f9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180001a75`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180001ab6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180001a75`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180001ab6`
- `wbemcomn!??0QL1_Parser@@QEAA@PEAVCGenLexSource@@@Z` at `0x180001831`
- `wbemcomn!??0QL1_Parser@@QEAA@PEAVCGenLexSource@@@Z` at `0x180001831`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x180001874`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x180001bcd`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x180001c2a`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x180001874`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x180001bcd`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x180001c2a`
- `wbemcomn!?Parse@QL1_Parser@@QEAAHPEAPEAUQL_LEVEL_1_RPN_EXPRESSION@@@Z` at `0x180001842`
- `wbemcomn!?Parse@QL1_Parser@@QEAAHPEAPEAUQL_LEVEL_1_RPN_EXPRESSION@@@Z` at `0x180001842`
- `wbemcomn!??1QL_LEVEL_1_RPN_EXPRESSION@@QEAA@XZ` at `0x180001a6b`
- `wbemcomn!??1QL_LEVEL_1_RPN_EXPRESSION@@QEAA@XZ` at `0x180001aac`
- `wbemcomn!??1QL_LEVEL_1_RPN_EXPRESSION@@QEAA@XZ` at `0x180001a6b`
- `wbemcomn!??1QL_LEVEL_1_RPN_EXPRESSION@@QEAA@XZ` at `0x180001aac`
- `wbemcomn!GetMemLogObject` at `0x180001ac2`
- `wbemcomn!GetMemLogObject` at `0x180001b13`
- `wbemcomn!GetMemLogObject` at `0x180001b6a`
- `wbemcomn!GetMemLogObject` at `0x180001b80`
- `wbemcomn!GetMemLogObject` at `0x180001bdd`
- `wbemcomn!GetMemLogObject` at `0x180001ac2`
- `wbemcomn!GetMemLogObject` at `0x180001b13`
- `wbemcomn!GetMemLogObject` at `0x180001b6a`
- `wbemcomn!GetMemLogObject` at `0x180001b80`
- `wbemcomn!GetMemLogObject` at `0x180001bdd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001ad0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001b1e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001b75`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001b8e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001beb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001ad0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001b1e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001b75`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001b8e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001beb`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000191b`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000197a`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000191b`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000197a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CNamespaceHandle::ExecQuerySink(
        CNamespaceHandle *this,
        struct IWbemQuery *a2,
        __int64 a3,
        int a4,
        struct IWbemObjectSink *a5,
        unsigned int *DestStr)
{
  int v6; // r13d
  struct IWbemObjectSink *v9; // r15
  int v10; // edi
  wchar_t *i; // rcx
  int v12; // edi
  const unsigned __int16 **v13; // rdx
  QL_LEVEL_1_RPN_EXPRESSION *v14; // rbx
  const wchar_t *v15; // r14
  unsigned __int16 *j; // rsi
  unsigned __int16 v17; // di
  wchar_t v18; // cx
  unsigned int v19; // edi
  __int64 result; // rax
  int v21; // edi
  unsigned int v22; // edi
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v24; // rax
  CMemoryLog *v25; // rax
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  wchar_t *String1; // [rsp+30h] [rbp-118h] BYREF
  struct QL_LEVEL_1_RPN_EXPRESSION *v31; // [rsp+38h] [rbp-110h] BYREF
  _QWORD v32[4]; // [rsp+40h] [rbp-108h] BYREF
  _BYTE v33[192]; // [rsp+60h] [rbp-E8h] BYREF
  int SrcStr; // [rsp+168h] [rbp+20h] BYREF

  SrcStr = a4;
  try
  {
    v6 = a3;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    {
      v9 = a5;
    }
    else
    {
      v9 = a5;
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 441, a3, a5);
    }
    if ( g_bShuttingDown )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217357);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          442,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          2147749939LL);
      }
      result = 2147749939LL;
    }
    else
    {
      String1 = 0;
      v10 = ((__int64 (__fastcall *)(struct IWbemQuery *, __int64, _QWORD, wchar_t **))a2->lpVtbl->GetAnalysis)(
              a2,
              4,
              0,
              &String1);
      if ( v10 < 0 )
      {
        v24 = GetMemLogObject();
        CMemoryLog::Write(v24, v10);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            443,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            (unsigned int)v10);
        }
        result = (unsigned int)v10;
      }
      else
      {
        for ( i = String1; *i == 32; ++i )
          ;
        if ( _wcsnicmp(i, L"references ", 0xBu) )
        {
          v31 = 0;
          v32[0] = &CTextLexSource::`vftable';
          v32[2] = String1;
          v32[1] = String1;
          QL1_Parser::QL1_Parser((QL1_Parser *)v33, (struct CGenLexSource *)v32);
          v12 = QL1_Parser::Parse((QL1_Parser *)v33, &v31);
          ((void (__fastcall *)(struct IWbemQuery *, wchar_t *))a2->lpVtbl->FreeMemory)(a2, String1);
          if ( v12 == 5 )
          {
            v26 = GetMemLogObject();
            CMemoryLog::Write(v26, -2147217402);
            if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                445,
                WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
                2147749894LL);
            }
            QL1_Parser::~QL1_Parser((QL1_Parser *)v33);
            result = 2147749894LL;
          }
          else if ( v12 )
          {
            v27 = GetMemLogObject();
            CMemoryLog::Write(v27, -2147217407);
            if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                446,
                WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
                2147749889LL);
            }
            QL1_Parser::~QL1_Parser((QL1_Parser *)v33);
            result = 2147749889LL;
          }
          else
          {
            QL1_Parser::~QL1_Parser((QL1_Parser *)v33);
            v13 = (const unsigned __int16 **)v31;
            v14 = v31;
            v32[3] = v31;
            v15 = L"meta_class";
            for ( j = (unsigned __int16 *)*((_QWORD *)v31 + 3); ; ++j )
            {
              v17 = *j;
              if ( !*j )
                break;
              if ( v17 > 0x7Fu )
              {
                LOWORD(SrcStr) = *j;
                LOWORD(DestStr) = 0;
                if ( LCMapStringW(0x7Fu, 0x100u, (LPCWSTR)&SrcStr, 1, (LPWSTR)&DestStr, 1) )
                  v17 = (unsigned __int16)DestStr;
                else
                  v17 = SrcStr;
                v13 = (const unsigned __int16 **)v31;
              }
              else if ( (unsigned __int16)(v17 - 65) <= 0x19u )
              {
                v17 += 32;
              }
LABEL_16:
              v18 = *v15;
              if ( *v15 > 0x7Fu )
              {
                LOWORD(SrcStr) = *v15;
                LOWORD(DestStr) = 0;
                if ( LCMapStringW(0x7Fu, 0x100u, (LPCWSTR)&SrcStr, 1, (LPWSTR)&DestStr, 1) )
                  v18 = (unsigned __int16)DestStr;
                else
                  v18 = SrcStr;
                v13 = (const unsigned __int16 **)v31;
              }
              else if ( (unsigned __int16)(v18 - 65) <= 0x19u )
              {
                v18 += 32;
              }
              if ( v17 != v18 )
              {
                v22 = CNamespaceHandle::ExecInstanceQuery(
                        this,
                        (struct QL_LEVEL_1_RPN_EXPRESSION *)v13,
                        v13[3],
                        (v6 & 1) == 0,
                        v9);
                if ( v14 )
                {
                  QL_LEVEL_1_RPN_EXPRESSION::~QL_LEVEL_1_RPN_EXPRESSION(v14);
                  CWin32DefaultArena::WbemMemFree(v14);
                }
                return v22;
              }
              ++v15;
            }
            if ( *v15 )
              goto LABEL_16;
            v19 = CNamespaceHandle::ExecClassQuery(this, (struct QL_LEVEL_1_RPN_EXPRESSION *)v13, v9, v6);
            if ( v14 )
            {
              QL_LEVEL_1_RPN_EXPRESSION::~QL_LEVEL_1_RPN_EXPRESSION(v14);
              CWin32DefaultArena::WbemMemFree(v14);
            }
            result = v19;
          }
        }
        else
        {
          v21 = CNamespaceHandle::ExecReferencesQuery(this, String1, v9);
          ((void (__fastcall *)(struct IWbemQuery *, wchar_t *))a2->lpVtbl->FreeMemory)(a2, String1);
          if ( v21 < 0 )
          {
            v25 = GetMemLogObject();
            CMemoryLog::Write(v25, v21);
          }
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              444,
              WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
              (unsigned int)v21);
          }
          result = (unsigned int)v21;
        }
      }
    }
  }
  catch ( CX_MemoryException )
  {
    v28 = GetMemLogObject();
    CMemoryLog::Write(v28, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 448, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  catch ( CX_Exception )
  {
    v29 = GetMemLogObject();
    CMemoryLog::Write(v29, -2147217398);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 449, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749898LL);
    }
    return 2147749898LL;
  }
  v6 = a3;
}

```

## disassembly

```asm
0x180001750  mov     [rsp+arg_0], rbx
0x180001755  mov     [rsp+arg_10], rsi
0x18000175a  mov     [rsp+SrcStr], r9d
0x18000175f  mov     [rsp+arg_8], rdx
0x180001764  push    rdi
0x180001765  push    r12
0x180001767  push    r13
0x180001769  push    r14
0x18000176b  push    r15
0x18000176d  sub     rsp, 120h
0x180001774  mov     r13d, r8d
0x180001777  mov     rbx, rdx
0x18000177a  mov     r12, rcx
0x18000177d  lea     rsi, WPP_GLOBAL_Control
0x180001784  mov     rcx, cs:WPP_GLOBAL_Control
0x18000178b  cmp     rcx, rsi
0x18000178e  jz      short loc_18000179A
0x180001790  test    byte ptr [rcx+1Ch], 1
0x180001794  jnz     loc_180001A81
0x18000179a  mov     r15, [rsp+148h+arg_20]
0x1800017a2  cmp     cs:?g_bShuttingDown@@3_NA, 0; bool g_bShuttingDown
0x1800017a9  jnz     loc_180001AC2
0x1800017af  xor     r14d, r14d
0x1800017b2  mov     [rsp+148h+String1], r14
0x1800017b7  mov     rax, [rbx]
0x1800017ba  lea     r9, [rsp+148h+String1]
0x1800017bf  xor     r8d, r8d
0x1800017c2  mov     edx, 4
0x1800017c7  mov     rcx, rbx
0x1800017ca  mov     rax, [rax+38h]
0x1800017ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017d3  mov     edi, eax
0x1800017d5  test    eax, eax
0x1800017d7  js      loc_180001B13
0x1800017dd  mov     rcx, [rsp+148h+String1]; String1
0x1800017e2  cmp     word ptr [rcx], 20h ; ' '
0x1800017e6  jz      loc_180001B5B
0x1800017ec  mov     r8d, 0Bh; MaxCount
0x1800017f2  lea     rdx, aReferences; "references "
0x1800017f9  call    cs:__imp__wcsnicmp
0x1800017ff  test    eax, eax
0x180001801  jz      loc_1800019C2
0x180001807  mov     [rsp+148h+var_110], r14
0x18000180c  mov     rax, [rsp+148h+String1]
0x180001811  lea     rcx, ??_7CTextLexSource@@6B@; const CTextLexSource::`vftable'
0x180001818  mov     [rsp+148h+var_108], rcx
0x18000181d  mov     [rsp+148h+var_F8], rax
0x180001822  mov     [rsp+148h+var_100], rax
0x180001827  lea     rdx, [rsp+148h+var_108]
0x18000182c  lea     rcx, [rsp+148h+var_E8]
0x180001831  call    cs:__imp_??0QL1_Parser@@QEAA@PEAVCGenLexSource@@@Z; QL1_Parser::QL1_Parser(CGenLexSource *)
0x180001837  nop
0x180001838  lea     rdx, [rsp+148h+var_110]
0x18000183d  lea     rcx, [rsp+148h+var_E8]
0x180001842  call    cs:__imp_?Parse@QL1_Parser@@QEAAHPEAPEAUQL_LEVEL_1_RPN_EXPRESSION@@@Z; QL1_Parser::Parse(QL_LEVEL_1_RPN_EXPRESSION * *)
0x180001848  mov     edi, eax
0x18000184a  mov     rcx, [rbx]
0x18000184d  mov     rax, [rcx+40h]
0x180001851  mov     rdx, [rsp+148h+String1]
0x180001856  mov     rcx, rbx
0x180001859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000185e  cmp     edi, 5
0x180001861  jz      loc_180001B80
0x180001867  test    edi, edi
0x180001869  jnz     loc_180001BDD
0x18000186f  lea     rcx, [rsp+148h+var_E8]
0x180001874  call    cs:__imp_??1QL1_Parser@@UEAA@XZ; QL1_Parser::~QL1_Parser(void)
0x18000187a  nop
0x18000187b  mov     rdx, [rsp+148h+var_110]; struct QL_LEVEL_1_RPN_EXPRESSION *
0x180001880  mov     rbx, rdx
0x180001883  mov     [rsp+148h+var_F0], rdx
0x180001888  lea     r14, aMetaClass; "meta_class"
0x18000188f  mov     rsi, [rdx+18h]
0x180001893  movzx   edi, word ptr [rsi]
0x180001896  test    di, di
0x180001899  jz      loc_18000199A
0x18000189f  cmp     di, 7Fh
0x1800018a3  ja      short loc_1800018DC
0x1800018a5  lea     eax, [rdi-41h]
0x1800018a8  cmp     ax, 19h
0x1800018ac  ja      short loc_1800018B2
0x1800018ae  add     di, 20h ; ' '
0x1800018b2  movzx   ecx, word ptr [r14]
0x1800018b6  cmp     cx, 7Fh
0x1800018ba  ja      short loc_18000193B
0x1800018bc  lea     eax, [rcx-41h]
0x1800018bf  cmp     ax, 19h
0x1800018c3  ja      short loc_1800018C9
0x1800018c5  add     cx, 20h ; ' '
0x1800018c9  cmp     di, cx
0x1800018cc  jnz     loc_180001A1B
0x1800018d2  add     rsi, 2
0x1800018d6  add     r14, 2
0x1800018da  jmp     short loc_180001893
0x1800018dc  mov     word ptr [rsp+148h+SrcStr], di
0x1800018e4  xor     eax, eax
0x1800018e6  mov     [rsp+148h+DestStr], ax
0x1800018ee  mov     [rsp+148h+cchDest], 1; cchDest
0x1800018f6  lea     rax, [rsp+148h+DestStr]
0x1800018fe  mov     [rsp+148h+lpDestStr], rax; lpDestStr
0x180001903  mov     r9d, 1; cchSrc
0x180001909  lea     r8, [rsp+148h+SrcStr]; lpSrcStr
0x180001911  mov     edx, 100h; dwMapFlags
0x180001916  mov     ecx, 7Fh; Locale
0x18000191b  call    cs:__imp_LCMapStringW
0x180001921  test    eax, eax
0x180001923  jnz     loc_180001C3A
0x180001929  movzx   edi, word ptr [rsp+148h+SrcStr]
0x180001931  mov     rdx, [rsp+148h+var_110]
0x180001936  jmp     loc_1800018B2
0x18000193b  mov     word ptr [rsp+148h+SrcStr], cx
0x180001943  xor     eax, eax
0x180001945  mov     [rsp+148h+DestStr], ax
0x18000194d  mov     [rsp+148h+cchDest], 1; cchDest
0x180001955  lea     rax, [rsp+148h+DestStr]
0x18000195d  mov     [rsp+148h+lpDestStr], rax; lpDestStr
0x180001962  mov     r9d, 1; cchSrc
0x180001968  lea     r8, [rsp+148h+SrcStr]; lpSrcStr
0x180001970  mov     edx, 100h; dwMapFlags
0x180001975  mov     ecx, 7Fh; Locale
0x18000197a  call    cs:__imp_LCMapStringW
0x180001980  test    eax, eax
0x180001982  jnz     loc_180001C47
0x180001988  movzx   ecx, word ptr [rsp+148h+SrcStr]
0x180001990  mov     rdx, [rsp+148h+var_110]
0x180001995  jmp     loc_1800018C9
0x18000199a  cmp     word ptr [r14], 0
0x18000199f  jnz     loc_1800018B2
0x1800019a5  mov     r9d, r13d; unsigned int
0x1800019a8  mov     r8, r15; struct IWbemObjectSink *
0x1800019ab  mov     rcx, r12; this
0x1800019ae  call    ?ExecClassQuery@CNamespaceHandle@@IEAAJPEAUQL_LEVEL_1_RPN_EXPRESSION@@PEAUIWbemObjectSink@@K@Z; CNamespaceHandle::ExecClassQuery(QL_LEVEL_1_RPN_EXPRESSION *,IWbemObjectSink *,ulong)
0x1800019b3  mov     edi, eax
0x1800019b5  test    rbx, rbx
0x1800019b8  jnz     loc_180001A68
0x1800019be  mov     eax, edi
0x1800019c0  jmp     short loc_1800019FE
0x1800019c2  mov     r8, r15; struct IWbemObjectSink *
0x1800019c5  mov     rdx, [rsp+148h+String1]; unsigned __int16 *
0x1800019ca  mov     rcx, r12; this
0x1800019cd  call    ?ExecReferencesQuery@CNamespaceHandle@@IEAAJPEBGPEAUIWbemObjectSink@@@Z; CNamespaceHandle::ExecReferencesQuery(ushort const *,IWbemObjectSink *)
0x1800019d2  mov     edi, eax
0x1800019d4  mov     rcx, [rbx]
0x1800019d7  mov     rax, [rcx+40h]
0x1800019db  mov     rdx, [rsp+148h+String1]
0x1800019e0  mov     rcx, rbx
0x1800019e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019e8  test    edi, edi
0x1800019ea  js      loc_180001B6A
0x1800019f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019f7  cmp     rcx, rsi
0x1800019fa  jnz     short loc_180001A42
0x1800019fc  mov     eax, edi
0x1800019fe  lea     r11, [rsp+148h+var_28]
0x180001a06  mov     rbx, [r11+30h]
0x180001a0a  mov     rsi, [r11+40h]
0x180001a0e  mov     rsp, r11
0x180001a11  pop     r15
0x180001a13  pop     r14
0x180001a15  pop     r13
0x180001a17  pop     r12
0x180001a19  pop     rdi
0x180001a1a  retn
0x180001a1b  not     r13b
0x180001a1e  and     r13b, 1
0x180001a22  mov     [rsp+148h+lpDestStr], r15; struct IWbemObjectSink *
0x180001a27  movzx   r9d, r13b; bool
0x180001a2b  mov     r8, [rdx+18h]; unsigned __int16 *
0x180001a2f  mov     rcx, r12; this
0x180001a32  call    ?ExecInstanceQuery@CNamespaceHandle@@IEAAJPEAUQL_LEVEL_1_RPN_EXPRESSION@@PEBG_NPEAUIWbemObjectSink@@@Z; CNamespaceHandle::ExecInstanceQuery(QL_LEVEL_1_RPN_EXPRESSION *,ushort const *,bool,IWbemObjectSink *)
0x180001a37  mov     edi, eax
0x180001a39  test    rbx, rbx
0x180001a3c  jnz     short loc_180001AA9
0x180001a3e  mov     eax, edi
0x180001a40  jmp     short loc_1800019FE
0x180001a42  test    byte ptr [rcx+1Ch], 1
0x180001a46  jz      short loc_1800019FC
0x180001a48  cmp     byte ptr [rcx+19h], 2
0x180001a4c  jb      short loc_1800019FC
0x180001a4e  mov     edx, 1BCh
0x180001a53  mov     r9d, edi
0x180001a56  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180001a5d  mov     rcx, [rcx+10h]
0x180001a61  call    WPP_SF_d
0x180001a66  jmp     short loc_1800019FC
0x180001a68  mov     rcx, rbx
0x180001a6b  call    cs:__imp_??1QL_LEVEL_1_RPN_EXPRESSION@@QEAA@XZ; QL_LEVEL_1_RPN_EXPRESSION::~QL_LEVEL_1_RPN_EXPRESSION(void)
0x180001a71  nop
0x180001a72  mov     rcx, rbx
0x180001a75  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180001a7b  nop
0x180001a7c  jmp     loc_1800019BE
0x180001a81  cmp     byte ptr [rcx+19h], 5
0x180001a85  jb      loc_18000179A
0x180001a8b  mov     edx, 1B9h
0x180001a90  mov     r15, [rsp+148h+arg_20]
0x180001a98  mov     r9, r15
0x180001a9b  mov     rcx, [rcx+10h]
0x180001a9f  call    WPP_SF_q
0x180001aa4  jmp     loc_1800017A2
0x180001aa9  mov     rcx, rbx
0x180001aac  call    cs:__imp_??1QL_LEVEL_1_RPN_EXPRESSION@@QEAA@XZ; QL_LEVEL_1_RPN_EXPRESSION::~QL_LEVEL_1_RPN_EXPRESSION(void)
0x180001ab2  nop
0x180001ab3  mov     rcx, rbx
0x180001ab6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180001abc  nop
0x180001abd  jmp     loc_180001A3E
0x180001ac2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180001ac8  mov     edx, 80041033h
0x180001acd  mov     rcx, rax
0x180001ad0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180001ad6  mov     rcx, cs:WPP_GLOBAL_Control
0x180001add  cmp     rcx, rsi
0x180001ae0  jz      short loc_180001B09
0x180001ae2  test    byte ptr [rcx+1Ch], 1
0x180001ae6  jz      short loc_180001B09
0x180001ae8  cmp     byte ptr [rcx+19h], 2
0x180001aec  jb      short loc_180001B09
0x180001aee  mov     edx, 1BAh
0x180001af3  mov     r9d, 80041033h
0x180001af9  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180001b00  mov     rcx, [rcx+10h]
0x180001b04  call    WPP_SF_d
0x180001b09  mov     eax, 80041033h
0x180001b0e  jmp     loc_1800019FE
0x180001b13  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180001b19  mov     edx, edi
0x180001b1b  mov     rcx, rax
0x180001b1e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180001b24  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b2b  cmp     rcx, rsi
0x180001b2e  jz      short loc_180001B54
0x180001b30  test    byte ptr [rcx+1Ch], 1
0x180001b34  jz      short loc_180001B54
0x180001b36  cmp     byte ptr [rcx+19h], 2
0x180001b3a  jb      short loc_180001B54
0x180001b3c  mov     edx, 1BBh
0x180001b41  mov     r9d, edi
0x180001b44  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180001b4b  mov     rcx, [rcx+10h]
0x180001b4f  call    WPP_SF_d
0x180001b54  mov     eax, edi
0x180001b56  jmp     loc_1800019FE
0x180001b5b  add     rcx, 2
0x180001b5f  cmp     word ptr [rcx], 20h ; ' '
0x180001b63  jz      short loc_180001B5B
0x180001b65  jmp     loc_1800017EC
0x180001b6a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180001b70  mov     edx, edi
0x180001b72  mov     rcx, rax
0x180001b75  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180001b7b  jmp     loc_1800019F0
0x180001b80  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180001b86  mov     edx, 80041006h
0x180001b8b  mov     rcx, rax
0x180001b8e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180001b94  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b9b  cmp     rcx, rsi
0x180001b9e  jz      short loc_180001BC8
0x180001ba0  test    byte ptr [rcx+1Ch], 1
0x180001ba4  jz      short loc_180001BC8
0x180001ba6  cmp     byte ptr [rcx+19h], 2
0x180001baa  jb      short loc_180001BC8
0x180001bac  mov     edx, 1BDh
0x180001bb1  mov     r9d, 80041006h
0x180001bb7  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180001bbe  mov     rcx, [rcx+10h]
0x180001bc2  call    WPP_SF_d
0x180001bc7  nop
0x180001bc8  lea     rcx, [rsp+148h+var_E8]
0x180001bcd  call    cs:__imp_??1QL1_Parser@@UEAA@XZ; QL1_Parser::~QL1_Parser(void)
0x180001bd3  mov     eax, 80041006h
0x180001bd8  jmp     loc_1800019FE
0x180001bdd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180001be3  mov     edx, 80041001h
0x180001be8  mov     rcx, rax
0x180001beb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180001bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bf8  cmp     rcx, rsi
0x180001bfb  jz      short loc_180001C25
0x180001bfd  test    byte ptr [rcx+1Ch], 1
0x180001c01  jz      short loc_180001C25
0x180001c03  cmp     byte ptr [rcx+19h], 2
0x180001c07  jb      short loc_180001C25
0x180001c09  mov     edx, 1BEh
0x180001c0e  mov     r9d, 80041001h
0x180001c14  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180001c1b  mov     rcx, [rcx+10h]
0x180001c1f  call    WPP_SF_d
0x180001c24  nop
0x180001c25  lea     rcx, [rsp+148h+var_E8]
0x180001c2a  call    cs:__imp_??1QL1_Parser@@UEAA@XZ; QL1_Parser::~QL1_Parser(void)
0x180001c30  mov     eax, 80041001h
0x180001c35  jmp     loc_1800019FE
0x180001c3a  movzx   edi, [rsp+148h+DestStr]
0x180001c42  jmp     loc_180001931
0x180001c47  movzx   ecx, [rsp+148h+DestStr]
0x180001c4f  jmp     loc_180001990
0x180001c54  mov     eax, 80041006h
0x180001c59  jmp     loc_1800019FE
  ... truncated ...
```
