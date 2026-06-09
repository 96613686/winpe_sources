# OpenClusterNodeImpl(_HCLUSTER *,wchar_t const *,ulong,ulong *,int)

- ea: `0x180057f5c`
- end: `0x1800582cc`
- name: `?OpenClusterNodeImpl@@YAPEAU_HNODE@@PEAU_HCLUSTER@@PEB_WKPEAKH@Z`
- size: `880`
- prototype: `struct _HNODE *(struct _HCLUSTER *, const wchar_t *, unsigned int, unsigned int *, int)`
- caller_count: `15`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800204d0`
- `0x180032770`
- `0x1800386a0`
- `0x18003a688`
- `0x18003b758`
- `0x18003c320`
- `0x18003e32c`
- `0x180040790`
- `0x1800545b0`
- `0x180056360`
- `0x180058b60`
- `0x180058b90`
- `0x1800590f0`
- `0x18008e110`
- `0x18009fd58`

## callees

- `0x18001236c`
- `0x180014638`
- `0x180025478`
- `0x180056360`
- `0x1800563d0`
- `0x1800577c0`
- `0x1800579a0`
- `0x180057c9c`
- `0x180057f5c`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058217`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058217`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800581ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800581ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800582b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800582b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005809e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800580e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800580ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800582a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800582ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005809e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800580e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800580ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800582a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800582ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180057fd8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180058067`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180057fd8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180058067`

## string_xrefs

- `0x180057ff6`: `OpenClusterNodeImpl`
- `0x18005803d`: `OpenClusterNodeImpl`
- `0x180058083`: `OpenClusterNodeImpl`
- `0x1800580ca`: `OpenClusterNodeImpl`
- `0x180058263`: `OpenClusterNodeImpl`
- `0x180058279`: `OpenClusterNodeImpl`
- `0x1800580c3`: `Can't copy node name.`
- `0x180058285`: `OpenNode failed - sc %u`
- `0x18005817a`: `ApiOpenNode`
- `0x180058133`: `ApiOpenNodeEx`

## pseudocode

```c
struct _HNODE *__fastcall OpenClusterNodeImpl(struct _HCLUSTER *a1, wchar_t *a2, int a3, unsigned int *a4, int a5)
{
  DWORD v9; // ecx
  bool v10; // zf
  _QWORD *v12; // rbx
  unsigned __int64 v13; // rsi
  wchar_t *v14; // rax
  int v15; // esi
  DWORD v16; // eax
  struct _RTL_CRITICAL_SECTION *v17; // rsi
  char *v18; // rdi
  __int64 v19; // rax
  __int64 v20; // rcx
  DWORD v21; // edi
  DWORD dwErrCode; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v23; // [rsp+34h] [rbp-3Ch] BYREF
  unsigned int v24; // [rsp+38h] [rbp-38h] BYREF
  const char *v25; // [rsp+40h] [rbp-30h] BYREF
  char *v26; // [rsp+48h] [rbp-28h]
  unsigned int *v27; // [rsp+50h] [rbp-20h]
  DWORD *p_dwErrCode; // [rsp+58h] [rbp-18h]
  unsigned int *v29; // [rsp+60h] [rbp-10h]
  DWORD *v30; // [rsp+68h] [rbp-8h]

  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           a1,
                           a1) )
  {
    v9 = 6;
    goto LABEL_36;
  }
  v10 = *((_DWORD *)a1 + 87) == 0;
  dwErrCode = 0;
  v24 = 0;
  v23 = 0;
  if ( !v10 )
  {
    LODWORD(p_dwErrCode) = a5;
    v25 = (const char *)a2;
    LODWORD(v26) = a3;
    v27 = a4;
    return (struct _HNODE *)FindClustersHandle__lambda_7f1729b582a2d8fb9d59e8145204842e_(a1, &v25);
  }
  v12 = LocalAlloc(0, 0x40u);
  if ( !v12 )
  {
    TraceMsg(2, 1, L"OpenClusterNodeImpl", 96, L"Can't alloc memory for node handle.");
LABEL_7:
    v9 = 8;
    goto LABEL_36;
  }
  *((_WORD *)v12 + 28) = 0;
  dwErrCode = MylstrlenW(a2, 0x7FFFFFFFu, &v24);
  if ( dwErrCode )
  {
    TraceMsg(2, 1, L"OpenClusterNodeImpl", 105, L"Can't find length of node name.");
LABEL_35:
    LocalFree(v12);
    v9 = dwErrCode;
    goto LABEL_36;
  }
  v13 = v24 + 1;
  v14 = (wchar_t *)LocalAlloc(0, 2 * v13);
  v12[5] = v14;
  if ( !v14 )
  {
    TraceMsg(2, 1, L"OpenClusterNodeImpl", 114, L"Can't alloc memory for node name.");
    LocalFree(v12);
    goto LABEL_7;
  }
  v15 = StringCchCopyW(v14, v13, a2);
  if ( v15 < 0 )
  {
    TraceMsg(2, 1, L"OpenClusterNodeImpl", 122, L"Can't copy node name.");
    LocalFree((HLOCAL)v12[5]);
    LocalFree(v12);
    if ( (v15 & 0x1FFF0000) != 0x70000 || (v9 = (unsigned __int16)v15, !(_WORD)v15) )
      v9 = v15;
    goto LABEL_36;
  }
  v12[4] = a1;
  v12[3] = v12 + 2;
  v12[2] = v12 + 2;
  if ( *((_WORD *)a1 + 162) <= 5u )
  {
    if ( !a5 )
    {
      v16 = 1745;
      v12[6] = 0;
      dwErrCode = 1745;
      goto LABEL_22;
    }
    v27 = (unsigned int *)a2;
    v25 = "ApiOpenNode";
    v26 = (char *)a1 + 40;
    p_dwErrCode = &dwErrCode;
    v12[6] = ReconnectOnNull<OpenNodeFunctor>(&v25, &dwErrCode, a1);
    v23 = 0x10000000;
  }
  else
  {
    v27 = (unsigned int *)a2;
    v25 = "ApiOpenNodeEx";
    LODWORD(p_dwErrCode) = a3;
    v26 = (char *)a1 + 40;
    v29 = &v23;
    v30 = &dwErrCode;
    v12[6] = ReconnectOnNull<OpenNodeExFunctor>(&v25, &dwErrCode, a1);
  }
  v16 = dwErrCode;
LABEL_22:
  if ( !v12[6] || v16 )
  {
    if ( v16 == 1745 && *((_WORD *)a1 + 162) > 5u )
    {
      TraceMsg(
        2,
        1,
        L"OpenClusterNodeImpl",
        156,
        L"Procnum out of range when we thought we were talking to a post-win2k8 cluster.");
      v16 = dwErrCode;
    }
    TraceMsg(2, 1, L"OpenClusterNodeImpl", 159, L"OpenNode failed - sc %u", v16);
    LocalFree((HLOCAL)v12[5]);
    goto LABEL_35;
  }
  *((_DWORD *)v12 + 15) = v23;
  if ( a4 )
    *a4 = v23;
  v17 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 232);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 232));
  v18 = (char *)a1 + 104;
  v19 = *(_QWORD *)v18;
  if ( *(char **)(*(_QWORD *)v18 + 8LL) != v18 )
    __fastfail(3u);
  *v12 = v19;
  v12[1] = v18;
  *(_QWORD *)(v19 + 8) = v12;
  *(_QWORD *)v18 = v12;
  LeaveCriticalSection(v17);
  v21 = HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Insert<_HNODE *>(
          v20,
          v12);
  if ( !v21 )
    return (struct _HNODE *)v12;
  CloseClusterNodeCommon(v12, 0);
  v9 = v21;
LABEL_36:
  SetLastError(v9);
  return 0;
}

```

## disassembly

```asm
0x180057f5c  push    rbp
0x180057f5e  push    rbx
0x180057f5f  push    rsi
0x180057f60  push    rdi
0x180057f61  push    r12
0x180057f63  push    r14
0x180057f65  push    r15
0x180057f67  mov     rbp, rsp
0x180057f6a  sub     rsp, 70h
0x180057f6e  mov     r14, rdx
0x180057f71  mov     r15, r9
0x180057f74  mov     rdx, rcx
0x180057f77  mov     r12d, r8d
0x180057f7a  mov     rdi, rcx
0x180057f7d  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x180057f82  test    al, al
0x180057f84  jnz     short loc_180057F90
0x180057f86  mov     ecx, 6
0x180057f8b  jmp     loc_1800582B5
0x180057f90  cmp     dword ptr [rdi+15Ch], 0
0x180057f97  mov     [rbp+dwErrCode], 0
0x180057f9e  mov     [rbp+var_38], 0
0x180057fa5  mov     [rbp+var_3C], 0
0x180057fac  jz      short loc_180057FD1
0x180057fae  mov     eax, [rbp+arg_20]
0x180057fb1  lea     rdx, [rbp+var_30]
0x180057fb5  mov     rcx, rdi
0x180057fb8  mov     dword ptr [rbp+var_18], eax
0x180057fbb  mov     [rbp+var_30], r14
0x180057fbf  mov     dword ptr [rbp+var_28], r12d
0x180057fc3  mov     [rbp+var_20], r15
0x180057fc7  call    FindClustersHandle__lambda_7f1729b582a2d8fb9d59e8145204842e___; FindClustersHandle__lambda_7f1729b582a2d8fb9d59e8145204842e_
0x180057fcc  jmp     loc_1800582BD
0x180057fd1  mov     edx, 40h ; '@'; uBytes
0x180057fd6  xor     ecx, ecx; uFlags
0x180057fd8  call    cs:__imp_LocalAlloc
0x180057fde  mov     rbx, rax
0x180057fe1  test    rax, rax
0x180057fe4  jnz     short loc_180058012
0x180057fe6  lea     rax, aCanTAllocMemor; "Can't alloc memory for node handle."
0x180057fed  lea     r9d, [rbx+60h]
0x180057ff1  mov     [rsp+70h+var_50], rax
0x180057ff6  lea     r8, aOpenclusternod_4; "OpenClusterNodeImpl"
0x180057ffd  lea     edx, [rbx+1]
0x180058000  lea     ecx, [rbx+2]
0x180058003  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180058008  mov     ecx, 8
0x18005800d  jmp     loc_1800582B5
0x180058012  xor     eax, eax
0x180058014  lea     r8, [rbp+var_38]; unsigned int *
0x180058018  mov     edx, 7FFFFFFFh; unsigned int
0x18005801d  mov     [rbx+38h], ax
0x180058021  mov     rcx, r14; wchar_t *
0x180058024  call    ?MylstrlenW@@YAKPEB_WKPEAK@Z; MylstrlenW(wchar_t const *,ulong,ulong *)
0x180058029  mov     [rbp+dwErrCode], eax
0x18005802c  test    eax, eax
0x18005802e  jz      short loc_18005805A
0x180058030  mov     r9d, 69h ; 'i'
0x180058036  lea     rax, aCanTFindLength; "Can't find length of node name."
0x18005803d  lea     r8, aOpenclusternod_4; "OpenClusterNodeImpl"
0x180058044  mov     [rsp+70h+var_50], rax
0x180058049  lea     edx, [r9-68h]
0x18005804d  lea     ecx, [rdx+1]
0x180058050  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180058055  jmp     loc_1800582A9
0x18005805a  mov     eax, [rbp+var_38]
0x18005805d  xor     ecx, ecx; uFlags
0x18005805f  inc     eax
0x180058061  mov     esi, eax
0x180058063  lea     rdx, [rax+rax]; uBytes
0x180058067  call    cs:__imp_LocalAlloc
0x18005806d  mov     [rbx+28h], rax
0x180058071  test    rax, rax
0x180058074  jnz     short loc_1800580A9
0x180058076  mov     r9d, 72h ; 'r'
0x18005807c  lea     rax, aCanTAllocMemor_0; "Can't alloc memory for node name."
0x180058083  lea     r8, aOpenclusternod_4; "OpenClusterNodeImpl"
0x18005808a  mov     [rsp+70h+var_50], rax
0x18005808f  lea     edx, [r9-71h]
0x180058093  lea     ecx, [rdx+1]
0x180058096  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005809b  mov     rcx, rbx; hMem
0x18005809e  call    cs:__imp_LocalFree
0x1800580a4  jmp     loc_180058008
0x1800580a9  mov     r8, r14; wchar_t *
0x1800580ac  mov     rdx, rsi; unsigned __int64
0x1800580af  mov     rcx, rax; wchar_t *
0x1800580b2  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800580b7  mov     esi, eax
0x1800580b9  test    eax, eax
0x1800580bb  jns     short loc_180058115
0x1800580bd  mov     r9d, 7Ah ; 'z'
0x1800580c3  lea     rax, aCanTCopyNodeNa; "Can't copy node name."
0x1800580ca  lea     r8, aOpenclusternod_4; "OpenClusterNodeImpl"
0x1800580d1  mov     [rsp+70h+var_50], rax
0x1800580d6  lea     edx, [r9-79h]
0x1800580da  lea     ecx, [rdx+1]
0x1800580dd  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800580e2  mov     rcx, [rbx+28h]; hMem
0x1800580e6  call    cs:__imp_LocalFree
0x1800580ec  mov     rcx, rbx; hMem
0x1800580ef  call    cs:__imp_LocalFree
0x1800580f5  mov     eax, esi
0x1800580f7  and     eax, 1FFF0000h
0x1800580fc  cmp     eax, 70000h
0x180058101  jnz     short loc_18005810E
0x180058103  movzx   ecx, si
0x180058106  test    ecx, ecx
0x180058108  jnz     loc_1800582B5
0x18005810e  mov     ecx, esi
0x180058110  jmp     loc_1800582B5
0x180058115  lea     rax, [rbx+10h]
0x180058119  mov     [rbx+20h], rdi
0x18005811d  mov     [rax+8], rax
0x180058121  mov     esi, 6D1h
0x180058126  mov     [rax], rax
0x180058129  cmp     word ptr [rdi+144h], 5
0x180058131  jbe     short loc_180058174
0x180058133  lea     rax, aApiopennodeex; "ApiOpenNodeEx"
0x18005813a  mov     [rbp+var_20], r14
0x18005813e  mov     [rbp+var_30], rax
0x180058142  lea     rdx, [rbp+dwErrCode]
0x180058146  lea     rax, [rdi+28h]
0x18005814a  mov     dword ptr [rbp+var_18], r12d
0x18005814e  mov     [rbp+var_28], rax
0x180058152  lea     rcx, [rbp+var_30]
0x180058156  lea     rax, [rbp+var_3C]
0x18005815a  mov     r8, rdi
0x18005815d  mov     [rbp+var_10], rax
0x180058161  lea     rax, [rbp+dwErrCode]
0x180058165  mov     [rbp+var_8], rax
0x180058169  call    ??$ReconnectOnNull@VOpenNodeExFunctor@@@@YAPEAXAEBVOpenNodeExFunctor@@PEAKPEAU_CLUSTER@@@Z; ReconnectOnNull<OpenNodeExFunctor>(OpenNodeExFunctor const &,ulong *,_CLUSTER *)
0x18005816e  mov     [rbx+30h], rax
0x180058172  jmp     short loc_1800581B4
0x180058174  cmp     [rbp+arg_20], 0
0x180058178  jz      short loc_1800581B9
0x18005817a  lea     rax, aApiopennode; "ApiOpenNode"
0x180058181  mov     [rbp+var_20], r14
0x180058185  mov     [rbp+var_30], rax
0x180058189  lea     rdx, [rbp+dwErrCode]
0x18005818d  lea     rax, [rdi+28h]
0x180058191  mov     r8, rdi
0x180058194  mov     [rbp+var_28], rax
0x180058198  lea     rcx, [rbp+var_30]
0x18005819c  lea     rax, [rbp+dwErrCode]
0x1800581a0  mov     [rbp+var_18], rax
0x1800581a4  call    ??$ReconnectOnNull@VOpenNodeFunctor@@@@YAPEAXAEBVOpenNodeFunctor@@PEAKPEAU_CLUSTER@@@Z; ReconnectOnNull<OpenNodeFunctor>(OpenNodeFunctor const &,ulong *,_CLUSTER *)
0x1800581a9  mov     [rbx+30h], rax
0x1800581ad  mov     [rbp+var_3C], 10000000h
0x1800581b4  mov     eax, [rbp+dwErrCode]
0x1800581b7  jmp     short loc_1800581C6
0x1800581b9  mov     eax, esi
0x1800581bb  mov     qword ptr [rbx+30h], 0
0x1800581c3  mov     [rbp+dwErrCode], eax
0x1800581c6  cmp     qword ptr [rbx+30h], 0
0x1800581cb  jz      short loc_18005823E
0x1800581cd  test    eax, eax
0x1800581cf  jnz     short loc_18005823E
0x1800581d1  mov     eax, [rbp+var_3C]
0x1800581d4  mov     [rbx+3Ch], eax
0x1800581d7  test    r15, r15
0x1800581da  jz      short loc_1800581E2
0x1800581dc  mov     eax, [rbp+var_3C]
0x1800581df  mov     [r15], eax
0x1800581e2  lea     rsi, [rdi+0E8h]
0x1800581e9  mov     rcx, rsi; lpCriticalSection
0x1800581ec  call    cs:__imp_EnterCriticalSection
0x1800581f2  add     rdi, 68h ; 'h'
0x1800581f6  mov     rax, [rdi]
0x1800581f9  cmp     [rax+8], rdi
0x1800581fd  jz      short loc_180058206
0x1800581ff  mov     ecx, 3
0x180058204  int     29h; Win8: RtlFailFast(ecx)
0x180058206  mov     [rbx], rax
0x180058209  mov     rcx, rsi; lpCriticalSection
0x18005820c  mov     [rbx+8], rdi
0x180058210  mov     [rax+8], rbx
0x180058214  mov     [rdi], rbx
0x180058217  call    cs:__imp_LeaveCriticalSection
0x18005821d  mov     rdx, rbx
0x180058220  call    ??$Insert@PEAU_HNODE@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAAKPEAU_HNODE@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Insert<_HNODE *>(_HNODE *)
0x180058225  mov     edi, eax
0x180058227  test    eax, eax
0x180058229  jz      short loc_180058239
0x18005822b  xor     edx, edx; int
0x18005822d  mov     rcx, rbx; hMem
0x180058230  call    ?CloseClusterNodeCommon@@YAHPEAU_HNODE@@H@Z; CloseClusterNodeCommon(_HNODE *,int)
0x180058235  mov     ecx, edi
0x180058237  jmp     short loc_1800582B5
0x180058239  mov     rax, rbx
0x18005823c  jmp     short loc_1800582BD
0x18005823e  cmp     eax, esi
0x180058240  jnz     short loc_180058275
0x180058242  cmp     word ptr [rdi+144h], 5
0x18005824a  jbe     short loc_180058275
0x18005824c  mov     edx, 1
0x180058251  lea     rax, aProcnumOutOfRa; "Procnum out of range when we thought we"...
0x180058258  mov     r9d, 9Ch
0x18005825e  mov     [rsp+70h+var_50], rax
0x180058263  lea     r8, aOpenclusternod_4; "OpenClusterNodeImpl"
0x18005826a  lea     ecx, [rdx+1]
0x18005826d  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180058272  mov     eax, [rbp+dwErrCode]
0x180058275  mov     [rsp+70h+var_48], eax
0x180058279  lea     r8, aOpenclusternod_4; "OpenClusterNodeImpl"
0x180058280  mov     edx, 1
0x180058285  lea     rax, aOpennodeFailed; "OpenNode failed - sc %u"
0x18005828c  mov     r9d, 9Fh
0x180058292  mov     [rsp+70h+var_50], rax
0x180058297  lea     ecx, [rdx+1]
0x18005829a  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005829f  mov     rcx, [rbx+28h]; hMem
0x1800582a3  call    cs:__imp_LocalFree
0x1800582a9  mov     rcx, rbx; hMem
0x1800582ac  call    cs:__imp_LocalFree
0x1800582b2  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x1800582b5  call    cs:__imp_SetLastError
0x1800582bb  xor     eax, eax
0x1800582bd  add     rsp, 70h
0x1800582c1  pop     r15
0x1800582c3  pop     r14
0x1800582c5  pop     r12
0x1800582c7  pop     rdi
0x1800582c8  pop     rsi
0x1800582c9  pop     rbx
0x1800582ca  pop     rbp
0x1800582cb  retn
```
