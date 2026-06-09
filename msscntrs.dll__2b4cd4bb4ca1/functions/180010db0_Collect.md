# Collect

- ea: `0x180010db0`
- end: `0x1800111a7`
- name: `Collect`
- size: `1015`
- prototype: `__int64 __fastcall(wchar_t *, void **, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1800024a0`
- `0x180002508`
- `0x180002cc0`
- `0x18000c5b4`
- `0x18000da9c`
- `0x18000df84`
- `0x18000fd0c`
- `0x18001067c`
- `0x180010db0`
- `0x1800119ec`
- `0x180015650`

## string_xrefs

- `0x180010e81`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmcntrs\\pkmcntrs.cxx"`
- `0x180010e9a`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmcntrs\\pkmcntrs.cxx"`
- `0x180010fec`: `[UtilCommon] MSSCNTRS: Object %ls requested.`
- `0x18001103c`: `[UtilCommon] MSSCNTRS: Object %ls requesting %u bytes.`
- `0x180010e75`: `[UtilCommon] MSSCNTRS: Foreign request not supported.`
- `0x180010edb`: `[UtilCommon] MSSCNTRS: Cannot get perf statistics on library %ls.`
- `0x1800110bb`: `[UtilCommon] MSSCNTRS: space needed = %u.`
- `0x1800110e4`: `[UtilCommon] MSSCNTRS: Insufficient buffer. Size=%u, Needed=%u.`

## pseudocode

```c
__int64 __fastcall Collect(wchar_t *a1, void **a2, unsigned int *a3, unsigned int *a4)
{
  unsigned int *v4; // r12
  unsigned int *v5; // r15
  unsigned int v7; // ebp
  bool v8; // zf
  const wchar_t *v10; // r9
  unsigned int v11; // r10d
  unsigned int v12; // r8d
  unsigned int v13; // edx
  unsigned int v14; // ebx
  int PerformanceStatistics; // eax
  unsigned int v16; // r13d
  unsigned int v17; // r14d
  unsigned int v18; // eax
  unsigned int v19; // r12d
  _OWORD *v20; // rbp
  unsigned int v21; // r14d
  __int64 v22; // rsi
  int v23; // ebx
  wchar_t *v24; // r9
  _OWORD *v25; // r15
  int v26; // ecx
  int v27; // edx
  int v28; // r8d
  __int64 v29; // rdx
  int v30; // r8d
  int v31; // ecx
  int v32; // edx
  const wchar_t *v33; // r9
  unsigned int v34; // ebx
  unsigned int v35; // eax
  unsigned int i; // ebx
  unsigned int v37; // ebx
  void (*v38)(void *); // [rsp+20h] [rbp-29A8h]
  unsigned int QueryType; // [rsp+34h] [rbp-2994h]
  unsigned int v40; // [rsp+38h] [rbp-2990h]
  unsigned int v41; // [rsp+3Ch] [rbp-298Ch]
  unsigned int v42; // [rsp+40h] [rbp-2988h]
  _OWORD v47[656]; // [rsp+70h] [rbp-2958h] BYREF

  v4 = a4;
  v5 = a3;
  `eh vector constructor iterator'(
    v47,
    0x520u,
    8u,
    (void (*)(void *))PerfLibraryData::PerfLibraryData,
    (void (*)(void *))PerfLibraryData::~PerfLibraryData);
  SearchIndexerTelemetryAggregatedHigh::MSSCNTRSCollect(a1);
  v7 = *v5;
  v8 = g_fInitOk == 0;
  *v5 = 0;
  *v4 = 0;
  v42 = v7;
  if ( v8 )
  {
    `eh vector destructor iterator'(v47, 0x520u, 8u, (void (*)(void *))PerfLibraryData::~PerfLibraryData);
    return 0;
  }
  QueryType = GetQueryType(a1);
  v12 = QueryType;
  if ( QueryType == 3 )
  {
    SearchIndexerTrace::Verbose(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmcntrs\\\\pkmcntrs.cxx\"",
      (const wchar_t *)0x1F1,
      (__int64)L"[UtilCommon] MSSCNTRS: Foreign request not supported.",
      v10);
LABEL_43:
    v34 = 0;
    goto LABEL_44;
  }
  v13 = g_dwLibraries;
  v14 = v11;
  if ( g_dwLibraries )
  {
    do
    {
      PerformanceStatistics = PerfLibraryData::GetPerformanceStatistics(
                                (PerfLibraryData *)&v47[82 * v14],
                                (const wchar_t *)&(&g_rgszLibraries)[4 * v14]);
      v11 = 0;
      if ( !PerformanceStatistics )
      {
        SearchIndexerTrace::Verbose(
          (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmcntrs\\\\pkmcntrs.cxx\"",
          (const wchar_t *)0x1FE,
          (__int64)L"[UtilCommon] MSSCNTRS: Cannot get perf statistics on library %ls.",
          (const wchar_t *)&(&g_rgszLibraries)[4 * v14]);
        v11 = 0;
      }
      v13 = g_dwLibraries;
      ++v14;
    }
    while ( v14 < g_dwLibraries );
    v12 = QueryType;
  }
  v40 = v11;
  v16 = v11;
  v41 = v11;
  v17 = v11;
  if ( v13 )
  {
LABEL_11:
    v18 = v11;
    v19 = v11;
    v20 = &v47[82 * v17];
    if ( *((_DWORD *)v20 + 4) <= v11 )
      goto LABEL_35;
    v21 = v11;
    while ( 1 )
    {
      v22 = 5LL * v19;
      if ( v12 == 1 )
      {
        v25 = &v20[v22 + 4];
LABEL_30:
        SearchIndexerTrace::Verbose(
          (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmcntrs\\\\pkmcntrs.cxx\"",
          (const wchar_t *)0xEB,
          (__int64)L"[UtilCommon] MSSCNTRS: Object %ls requested.",
          *((const wchar_t **)&v20[v22 + 3] + 1));
        v29 = *(_QWORD *)v25;
        LODWORD(v20[v22 + 3]) = 1;
        v30 = *(_DWORD *)(v29 + 40);
        v31 = 40 * *(_DWORD *)(v29 + 32) + 64;
        v32 = **(_DWORD **)&v20[v22 + 5];
        if ( v30 == -1 )
          v23 = v31 + v32;
        else
          v23 = v31 + v30 * (v32 + 88);
      }
      else
      {
        v23 = v11;
        if ( a1 )
        {
          v24 = a1;
          v25 = &v20[v22 + 4];
          v26 = v11;
          v27 = v11;
          v28 = 1;
          while ( 1 )
          {
            if ( (*v24 & 0xFFDF) != 0 )
            {
              if ( (unsigned __int16)(*v24 - 48) > 9u )
              {
                v27 = v11;
              }
              else
              {
                if ( v28 )
                {
                  v28 = v11;
                  v27 = 1;
                }
                else if ( !v27 )
                {
                  goto LABEL_28;
                }
                v26 = *v24 + 2 * (5 * v26 - 24);
              }
            }
            else
            {
              if ( v27 )
              {
                if ( v26 == *(_DWORD *)(*(_QWORD *)v25 + 12LL) )
                  goto LABEL_30;
                v27 = v11;
              }
              if ( *v24 == (_WORD)v11 )
                break;
              v28 = 1;
              v26 = v11;
            }
LABEL_28:
            ++v24;
          }
        }
      }
      v33 = (const wchar_t *)*((_QWORD *)&v20[v22 + 3] + 1);
      DWORD1(v20[v22 + 3]) = v23;
      LODWORD(v38) = v23;
      SearchIndexerTrace::Verbose(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmcntrs\\\\pkmcntrs.cxx\"",
        (const wchar_t *)0x105,
        (__int64)L"[UtilCommon] MSSCNTRS: Object %ls requesting %u bytes.",
        v33,
        v38);
      v12 = QueryType;
      v21 += v23;
      ++v19;
      v11 = 0;
      if ( v19 >= *((_DWORD *)v20 + 4) )
      {
        v13 = g_dwLibraries;
        v16 = v40;
        v18 = v21;
        v17 = v41;
LABEL_35:
        v12 = QueryType;
        v16 += v18;
        ++v17;
        v40 = v16;
        v41 = v17;
        if ( v17 >= v13 )
        {
          v5 = a3;
          v7 = v42;
          v4 = a4;
          break;
        }
        goto LABEL_11;
      }
    }
  }
  SearchIndexerTrace::Verbose(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmcntrs\\\\pkmcntrs.cxx\"",
    (const wchar_t *)0x20D,
    (__int64)L"[UtilCommon] MSSCNTRS: space needed = %u.",
    (const wchar_t *)((v16 + 3) & 0xFFFFFFFC));
  if ( v7 >= ((v16 + 3) & 0xFFFFFFFC) )
  {
    v35 = g_dwLibraries;
    for ( i = 0; i < g_dwLibraries; ++i )
    {
      PerfLibraryData::SavePerformanceData((const wchar_t **)&v47[82 * i], a2, v5, v4);
      v35 = g_dwLibraries;
    }
    v37 = 0;
    if ( v35 )
    {
      do
        PerfLibraryData::Close((PerfLibraryData *)&v47[82 * v37++]);
      while ( v37 < g_dwLibraries );
    }
    goto LABEL_43;
  }
  LODWORD(v38) = (v16 + 3) & 0xFFFFFFFC;
  SearchIndexerTrace::Verbose(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmcntrs\\\\pkmcntrs.cxx\"",
    (const wchar_t *)0x219,
    (__int64)L"[UtilCommon] MSSCNTRS: Insufficient buffer. Size=%u, Needed=%u.",
    (const wchar_t *)v7,
    v38);
  v34 = 234;
LABEL_44:
  `eh vector destructor iterator'(v47, 0x520u, 8u, (void (*)(void *))PerfLibraryData::~PerfLibraryData);
  return v34;
}

```

## disassembly

```asm
0x180010db0  push    rbx
0x180010db2  push    rbp
0x180010db3  push    rsi
0x180010db4  push    rdi
0x180010db5  push    r12
0x180010db7  push    r13
0x180010db9  push    r14
0x180010dbb  push    r15
0x180010dbd  mov     eax, 2988h
0x180010dc2  call    _alloca_probe
0x180010dc7  sub     rsp, rax
0x180010dca  mov     rax, cs:__security_cookie
0x180010dd1  xor     rax, rsp
0x180010dd4  mov     [rsp+29C8h+var_58], rax
0x180010ddc  mov     r12, r9
0x180010ddf  mov     [rsp+29C8h+var_2970], r9
0x180010de4  mov     r15, r8
0x180010de7  mov     [rsp+29C8h+var_2978], r8
0x180010dec  mov     [rsp+29C8h+var_2968], rdx
0x180010df1  lea     rdi, ??1PerfLibraryData@@QEAA@XZ; PerfLibraryData::~PerfLibraryData(void)
0x180010df8  mov     rbx, rcx
0x180010dfb  mov     [rsp+29C8h+var_2980], rcx
0x180010e00  mov     esi, 8
0x180010e05  mov     [rsp+29C8h+var_29A8], rdi; void (*)(void *)
0x180010e0a  mov     r8d, esi; unsigned __int64
0x180010e0d  lea     r9, ??0PerfLibraryData@@QEAA@XZ; void (*)(void *)
0x180010e14  mov     edx, 520h; unsigned __int64
0x180010e19  lea     rcx, [rsp+29C8h+var_2958]; void *
0x180010e1e  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180010e23  mov     rcx, rbx; wchar_t *
0x180010e26  call    ?MSSCNTRSCollect@SearchIndexerTelemetryAggregatedHigh@@SAXPEB_W@Z; SearchIndexerTelemetryAggregatedHigh::MSSCNTRSCollect(wchar_t const *)
0x180010e2b  mov     ebp, [r15]
0x180010e2e  xor     r10d, r10d
0x180010e31  cmp     cs:?g_fInitOk@@3HA, r10d; int g_fInitOk
0x180010e38  mov     [r15], r10d
0x180010e3b  mov     [r12], r10d
0x180010e3f  mov     [rsp+29C8h+var_2988], ebp
0x180010e43  jnz     short loc_180010E61
0x180010e45  mov     r9, rdi; void (*)(void *)
0x180010e48  lea     rcx, [rsp+29C8h+var_2958]; void *
0x180010e4d  mov     r8d, esi; unsigned __int64
0x180010e50  mov     edx, 520h; unsigned __int64
0x180010e55  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180010e5a  xor     eax, eax
0x180010e5c  jmp     loc_180011183
0x180010e61  mov     rcx, rbx; wchar_t *
0x180010e64  call    ?GetQueryType@@YAKPEA_W@Z; GetQueryType(wchar_t *)
0x180010e69  mov     [rsp+29C8h+var_2994], eax
0x180010e6d  mov     r8d, eax
0x180010e70  cmp     eax, 3
0x180010e73  jnz     short loc_180010E94
0x180010e75  lea     r8, aUtilcommonMssc_11; "[UtilCommon] MSSCNTRS: Foreign request "...
0x180010e7c  mov     edx, 1F1h; wchar_t *
0x180010e81  lea     rcx, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180010e88  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180010e8d  xor     esi, esi
0x180010e8f  jmp     loc_180011163
0x180010e94  mov     edx, cs:?g_dwLibraries@@3KA; ulong g_dwLibraries
0x180010e9a  lea     rdi, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180010ea1  mov     ebx, r10d
0x180010ea4  test    edx, edx
0x180010ea6  jz      short loc_180010F03
0x180010ea8  mov     ecx, ebx
0x180010eaa  lea     rdx, ?g_rgszLibraries@@3PAY0BA@_WA; wchar_t (near * g_rgszLibraries)[16]
0x180010eb1  imul    rax, rcx, 520h
0x180010eb8  mov     esi, ebx
0x180010eba  lea     rcx, [rsp+29C8h+var_2958]
0x180010ebf  shl     rsi, 5
0x180010ec3  add     rcx, rax; this
0x180010ec6  add     rsi, rdx
0x180010ec9  mov     rdx, rsi; wchar_t *
0x180010ecc  call    ?GetPerformanceStatistics@PerfLibraryData@@QEAAHPEB_W@Z; PerfLibraryData::GetPerformanceStatistics(wchar_t const *)
0x180010ed1  xor     r10d, r10d
0x180010ed4  test    eax, eax
0x180010ed6  jnz     short loc_180010EF2
0x180010ed8  mov     r9, rsi; wchar_t *
0x180010edb  lea     r8, aUtilcommonMssc_15; "[UtilCommon] MSSCNTRS: Cannot get perf "...
0x180010ee2  mov     edx, 1FEh; wchar_t *
0x180010ee7  mov     rcx, rdi; this
0x180010eea  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180010eef  xor     r10d, r10d
0x180010ef2  mov     edx, cs:?g_dwLibraries@@3KA; ulong g_dwLibraries
0x180010ef8  inc     ebx
0x180010efa  cmp     ebx, edx
0x180010efc  jb      short loc_180010EA8
0x180010efe  mov     r8d, [rsp+29C8h+var_2994]
0x180010f03  mov     [rsp+29C8h+var_2990], r10d
0x180010f08  mov     r13d, r10d
0x180010f0b  mov     [rsp+29C8h+var_298C], r10d
0x180010f10  mov     r14d, r10d
0x180010f13  test    edx, edx
0x180010f15  jz      loc_1800110B8
0x180010f1b  mov     eax, r14d
0x180010f1e  lea     rbp, [rsp+29C8h+var_2958]
0x180010f23  imul    rcx, rax, 520h
0x180010f2a  mov     eax, r10d
0x180010f2d  mov     r12d, r10d
0x180010f30  add     rbp, rcx
0x180010f33  cmp     [rbp+10h], r10d
0x180010f37  jbe     loc_18001108C
0x180010f3d  mov     r13, [rsp+29C8h+var_2980]
0x180010f42  mov     r14d, eax
0x180010f45  mov     eax, r12d
0x180010f48  lea     rsi, [rax+rax*4]
0x180010f4c  shl     rsi, 4
0x180010f50  cmp     r8d, 1
0x180010f54  jz      loc_180010FE0
0x180010f5a  mov     ebx, r10d
0x180010f5d  test    r13, r13
0x180010f60  jz      loc_180011037
0x180010f66  lea     r15, [rbp+40h]
0x180010f6a  mov     r9, r13
0x180010f6d  add     r15, rsi
0x180010f70  mov     ecx, r10d
0x180010f73  mov     edx, r10d
0x180010f76  mov     r8d, 1
0x180010f7c  mov     eax, 0FFDFh
0x180010f81  test    [r9], ax
0x180010f85  jz      short loc_180010FBC
0x180010f87  movzx   eax, word ptr [r9]
0x180010f8b  sub     ax, 30h ; '0'
0x180010f8f  cmp     ax, 9
0x180010f93  ja      short loc_180010FB7
0x180010f95  test    r8d, r8d
0x180010f98  jz      short loc_180010FA4
0x180010f9a  mov     r8d, r10d
0x180010f9d  mov     edx, 1
0x180010fa2  jmp     short loc_180010FA8
0x180010fa4  test    edx, edx
0x180010fa6  jz      short loc_180010FDA
0x180010fa8  movzx   eax, word ptr [r9]
0x180010fac  lea     ecx, [rcx+rcx*4]
0x180010faf  lea     ecx, [rcx-18h]
0x180010fb2  lea     ecx, [rax+rcx*2]
0x180010fb5  jmp     short loc_180010FDA
0x180010fb7  mov     edx, r10d
0x180010fba  jmp     short loc_180010FDA
0x180010fbc  test    edx, edx
0x180010fbe  jz      short loc_180010FCB
0x180010fc0  mov     rax, [r15]
0x180010fc3  cmp     ecx, [rax+0Ch]
0x180010fc6  jz      short loc_180010FE7
0x180010fc8  mov     edx, r10d
0x180010fcb  cmp     [r9], r10w
0x180010fcf  jz      short loc_180011037
0x180010fd1  mov     r8d, 1
0x180010fd7  mov     ecx, r10d
0x180010fda  add     r9, 2
0x180010fde  jmp     short loc_180010F7C
0x180010fe0  lea     r15, [rbp+40h]
0x180010fe4  add     r15, rsi
0x180010fe7  mov     r9, [rsi+rbp+38h]; wchar_t *
0x180010fec  lea     r8, aUtilcommonMssc_10; "[UtilCommon] MSSCNTRS: Object %ls reque"...
0x180010ff3  mov     edx, 0EBh; wchar_t *
0x180010ff8  mov     rcx, rdi; this
0x180010ffb  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180011000  mov     rdx, [r15]
0x180011003  mov     dword ptr [rsi+rbp+30h], 1
0x18001100b  mov     eax, [rdx+20h]
0x18001100e  mov     r8d, [rdx+28h]
0x180011012  lea     ecx, [rax+rax*4]
0x180011015  mov     rax, [rsi+rbp+50h]
0x18001101a  lea     ecx, ds:40h[rcx*8]
0x180011021  mov     edx, [rax]
0x180011023  cmp     r8d, 0FFFFFFFFh
0x180011027  jz      short loc_180011034
0x180011029  lea     ebx, [rdx+58h]
0x18001102c  imul    ebx, r8d
0x180011030  add     ebx, ecx
0x180011032  jmp     short loc_180011037
0x180011034  lea     ebx, [rcx+rdx]
0x180011037  mov     r9, [rsi+rbp+38h]; wchar_t *
0x18001103c  lea     r8, aUtilcommonMssc_17; "[UtilCommon] MSSCNTRS: Object %ls reque"...
0x180011043  mov     edx, 105h; wchar_t *
0x180011048  mov     [rsi+rbp+34h], ebx
0x18001104c  mov     rcx, rdi; this
0x18001104f  mov     dword ptr [rsp+29C8h+var_29A8], ebx
0x180011053  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180011058  mov     r8d, [rsp+29C8h+var_2994]
0x18001105d  add     r14d, ebx
0x180011060  inc     r12d
0x180011063  mov     r10d, 0
0x180011069  cmp     r12d, [rbp+10h]
0x18001106d  jb      loc_180010F45
0x180011073  mov     edx, cs:?g_dwLibraries@@3KA; ulong g_dwLibraries
0x180011079  mov     r13d, [rsp+29C8h+var_2990]
0x18001107e  mov     [rsp+29C8h+var_2998], r14d
0x180011083  mov     eax, [rsp+29C8h+var_2998]
0x180011087  mov     r14d, [rsp+29C8h+var_298C]
0x18001108c  mov     r8d, [rsp+29C8h+var_2994]
0x180011091  add     r13d, eax
0x180011094  inc     r14d
0x180011097  mov     [rsp+29C8h+var_2990], r13d
0x18001109c  mov     [rsp+29C8h+var_298C], r14d
0x1800110a1  cmp     r14d, edx
0x1800110a4  jb      loc_180010F1B
0x1800110aa  mov     r15, [rsp+29C8h+var_2978]
0x1800110af  mov     ebp, [rsp+29C8h+var_2988]
0x1800110b3  mov     r12, [rsp+29C8h+var_2970]
0x1800110b8  mov     ebx, r13d
0x1800110bb  lea     r8, aUtilcommonMssc_9; "[UtilCommon] MSSCNTRS: space needed = %"...
0x1800110c2  add     rbx, 3
0x1800110c6  mov     edx, 20Dh; wchar_t *
0x1800110cb  and     ebx, 0FFFFFFFCh
0x1800110ce  mov     rcx, rdi; this
0x1800110d1  mov     r9d, ebx; wchar_t *
0x1800110d4  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1800110d9  cmp     ebp, ebx
0x1800110db  jnb     short loc_1800110FF
0x1800110dd  mov     r9d, ebp; wchar_t *
0x1800110e0  mov     dword ptr [rsp+29C8h+var_29A8], ebx
0x1800110e4  lea     r8, aUtilcommonMssc_3; "[UtilCommon] MSSCNTRS: Insufficient buf"...
0x1800110eb  mov     edx, 219h; wchar_t *
0x1800110f0  mov     rcx, rdi; this
0x1800110f3  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1800110f8  mov     ebx, 0EAh
0x1800110fd  jmp     short loc_180011165
0x1800110ff  mov     eax, cs:?g_dwLibraries@@3KA; ulong g_dwLibraries
0x180011105  xor     esi, esi
0x180011107  mov     ebx, esi
0x180011109  test    eax, eax
0x18001110b  jz      short loc_18001113D
0x18001110d  mov     rdi, [rsp+29C8h+var_2968]
0x180011112  mov     eax, ebx
0x180011114  mov     r9, r12; unsigned int *
0x180011117  imul    rcx, rax, 520h
0x18001111e  lea     rax, [rsp+29C8h+var_2958]
0x180011123  mov     r8, r15; unsigned int *
0x180011126  add     rcx, rax; this
0x180011129  mov     rdx, rdi; void **
0x18001112c  call    ?SavePerformanceData@PerfLibraryData@@QEAAXPEAPEAXPEAK1@Z; PerfLibraryData::SavePerformanceData(void * *,ulong *,ulong *)
0x180011131  mov     eax, cs:?g_dwLibraries@@3KA; ulong g_dwLibraries
0x180011137  inc     ebx
0x180011139  cmp     ebx, eax
0x18001113b  jb      short loc_180011112
0x18001113d  mov     ebx, esi
0x18001113f  test    eax, eax
0x180011141  jz      short loc_180011163
0x180011143  mov     eax, ebx
0x180011145  imul    rcx, rax, 520h
0x18001114c  lea     rax, [rsp+29C8h+var_2958]
0x180011151  add     rcx, rax; this
0x180011154  call    ?Close@PerfLibraryData@@QEAAXXZ; PerfLibraryData::Close(void)
0x180011159  inc     ebx
0x18001115b  cmp     ebx, cs:?g_dwLibraries@@3KA; ulong g_dwLibraries
0x180011161  jb      short loc_180011143
0x180011163  mov     ebx, esi
0x180011165  lea     r9, ??1PerfLibraryData@@QEAA@XZ; void (*)(void *)
0x18001116c  mov     edx, 520h; unsigned __int64
0x180011171  mov     r8d, 8; unsigned __int64
0x180011177  lea     rcx, [rsp+29C8h+var_2958]; void *
0x18001117c  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180011181  mov     eax, ebx
0x180011183  mov     rcx, [rsp+29C8h+var_58]
0x18001118b  xor     rcx, rsp; StackCookie
0x18001118e  call    __security_check_cookie
0x180011193  add     rsp, 2988h
0x18001119a  pop     r15
0x18001119c  pop     r14
0x18001119e  pop     r13
0x1800111a0  pop     r12
0x1800111a2  pop     rdi
0x1800111a3  pop     rsi
0x1800111a4  pop     rbp
0x1800111a5  pop     rbx
0x1800111a6  retn
```
