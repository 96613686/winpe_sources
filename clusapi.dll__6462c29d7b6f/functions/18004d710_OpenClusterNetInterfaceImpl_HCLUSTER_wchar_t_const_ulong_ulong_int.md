# OpenClusterNetInterfaceImpl(_HCLUSTER *,wchar_t const *,ulong,ulong *,int)

- ea: `0x18004d710`
- end: `0x18004d99f`
- name: `?OpenClusterNetInterfaceImpl@@YAPEAU_HNETINTERFACE@@PEAU_HCLUSTER@@PEB_WKPEAKH@Z`
- size: `655`
- prototype: `struct _HNETINTERFACE *(struct _HCLUSTER *, const wchar_t *, unsigned int, unsigned int *, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800204d0`
- `0x18004dba0`
- `0x18004dbd0`

## callees

- `0x18001236c`
- `0x180014638`
- `0x180025478`
- `0x18004cd40`
- `0x18004d17c`
- `0x18004d35c`
- `0x18004d528`
- `0x18004d710`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d916`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d916`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d8e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d8e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d988`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d988`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d793`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d7bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d7dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d7e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d976`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d97f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d793`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d7bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d7dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d7e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d976`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d97f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004d760`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004d7ab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004d760`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004d7ab`

## string_xrefs

- `0x18004d95a`: `OpenClusterNetInterfaceImpl`
- `0x18004d875`: `ApiOpenNetInterface`
- `0x18004d82b`: `ApiOpenNetInterfaceEx`

## pseudocode

```c
struct _HNETINTERFACE *__fastcall OpenClusterNetInterfaceImpl(
        struct _HCLUSTER *a1,
        const wchar_t *a2,
        int a3,
        unsigned int *a4,
        int a5)
{
  DWORD v9; // ecx
  _QWORD *v10; // rbx
  unsigned __int64 v11; // rsi
  wchar_t *v12; // rax
  int v13; // esi
  DWORD v14; // eax
  unsigned int v15; // ecx
  struct _RTL_CRITICAL_SECTION *v16; // rsi
  char *v17; // rdi
  __int64 v18; // rax
  __int64 v19; // rcx
  DWORD v20; // edi
  DWORD dwErrCode; // [rsp+30h] [rbp-40h] BYREF
  int v23; // [rsp+34h] [rbp-3Ch] BYREF
  unsigned int v24; // [rsp+38h] [rbp-38h] BYREF
  const char *v25; // [rsp+40h] [rbp-30h] BYREF
  char *v26; // [rsp+48h] [rbp-28h]
  const wchar_t *v27; // [rsp+50h] [rbp-20h]
  DWORD *p_dwErrCode; // [rsp+58h] [rbp-18h]
  int *v29; // [rsp+60h] [rbp-10h]
  DWORD *v30; // [rsp+68h] [rbp-8h]

  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           a1,
                           a1) )
  {
    v9 = 6;
LABEL_32:
    SetLastError(v9);
    return 0;
  }
  dwErrCode = 0;
  v24 = 0;
  v23 = 0;
  v10 = LocalAlloc(0, 0x40u);
  if ( !v10 )
  {
LABEL_4:
    v9 = 8;
    goto LABEL_32;
  }
  dwErrCode = MylstrlenW(a2, 0x7FFFFFFFu, &v24);
  if ( !dwErrCode )
  {
    v11 = v24 + 1;
    v12 = (wchar_t *)LocalAlloc(0, 2 * v11);
    v10[5] = v12;
    if ( !v12 )
    {
      LocalFree(v10);
      goto LABEL_4;
    }
    v13 = StringCchCopyW(v12, v11, a2);
    if ( v13 < 0 )
    {
      LocalFree((HLOCAL)v10[5]);
      LocalFree(v10);
      if ( (v13 & 0x1FFF0000) != 0x70000 || (v9 = (unsigned __int16)v13, !(_WORD)v13) )
        v9 = v13;
      goto LABEL_32;
    }
    v10[4] = a1;
    v10[3] = v10 + 2;
    v10[2] = v10 + 2;
    if ( *((_WORD *)a1 + 162) <= 5u )
    {
      if ( a5 )
      {
        v27 = a2;
        v25 = "ApiOpenNetInterface";
        v26 = (char *)a1 + 40;
        p_dwErrCode = &dwErrCode;
        v10[6] = ReconnectOnNull<OpenNetInterfaceFunctor>(&v25, &dwErrCode, a1);
        v15 = 0x10000000;
        v14 = dwErrCode;
        v23 = 0x10000000;
LABEL_19:
        if ( !v10[6] || v14 )
        {
          if ( v14 == 1745 && *((_WORD *)a1 + 162) > 5u )
            TraceMsg(
              2u,
              5u,
              (__int64)L"OpenClusterNetInterfaceImpl",
              139,
              L"Procnum out of range when we thought we were talking to a post-win2k8 cluster.");
          LocalFree((HLOCAL)v10[5]);
          LocalFree(v10);
          v9 = dwErrCode;
        }
        else
        {
          if ( a4 )
            *a4 = v15;
          *((_DWORD *)v10 + 14) = v15;
          v16 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 232);
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 232));
          v17 = (char *)a1 + 136;
          v18 = *(_QWORD *)v17;
          if ( *(char **)(*(_QWORD *)v17 + 8LL) != v17 )
            __fastfail(3u);
          *v10 = v18;
          v10[1] = v17;
          *(_QWORD *)(v18 + 8) = v10;
          *(_QWORD *)v17 = v10;
          LeaveCriticalSection(v16);
          v20 = HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Insert<_HNETINTERFACE *>(
                  v19,
                  v10);
          if ( !v20 )
            return (struct _HNETINTERFACE *)v10;
          CloseClusterNetInterfaceCommon(v10, 0);
          v9 = v20;
        }
        goto LABEL_32;
      }
      v14 = 1745;
      v10[6] = 0;
      dwErrCode = 1745;
    }
    else
    {
      v27 = a2;
      v25 = "ApiOpenNetInterfaceEx";
      LODWORD(p_dwErrCode) = a3;
      v26 = (char *)a1 + 40;
      v29 = &v23;
      v30 = &dwErrCode;
      v10[6] = ReconnectOnNull<OpenNetInterfaceExFunctor>(&v25, &dwErrCode, a1);
      v14 = dwErrCode;
    }
    v15 = v23;
    goto LABEL_19;
  }
  LocalFree(v10);
  return 0;
}

```

## disassembly

```asm
0x18004d710  push    rbp
0x18004d712  push    rbx
0x18004d713  push    rsi
0x18004d714  push    rdi
0x18004d715  push    r12
0x18004d717  push    r14
0x18004d719  push    r15
0x18004d71b  mov     rbp, rsp
0x18004d71e  sub     rsp, 70h
0x18004d722  mov     r14, rdx
0x18004d725  mov     r15, r9
0x18004d728  mov     rdx, rcx
0x18004d72b  mov     r12d, r8d
0x18004d72e  mov     rdi, rcx
0x18004d731  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x18004d736  test    al, al
0x18004d738  jnz     short loc_18004D744
0x18004d73a  mov     ecx, 6
0x18004d73f  jmp     loc_18004D988
0x18004d744  mov     edx, 40h ; '@'; uBytes
0x18004d749  mov     [rbp+dwErrCode], 0
0x18004d750  xor     ecx, ecx; uFlags
0x18004d752  mov     [rbp+var_38], 0
0x18004d759  mov     [rbp+var_3C], 0
0x18004d760  call    cs:__imp_LocalAlloc
0x18004d766  mov     rbx, rax
0x18004d769  test    rax, rax
0x18004d76c  jnz     short loc_18004D778
0x18004d76e  mov     ecx, 8
0x18004d773  jmp     loc_18004D988
0x18004d778  lea     r8, [rbp+var_38]; unsigned int *
0x18004d77c  mov     edx, 7FFFFFFFh; unsigned int
0x18004d781  mov     rcx, r14; wchar_t *
0x18004d784  call    ?MylstrlenW@@YAKPEB_WKPEAK@Z; MylstrlenW(wchar_t const *,ulong,ulong *)
0x18004d789  mov     [rbp+dwErrCode], eax
0x18004d78c  test    eax, eax
0x18004d78e  jz      short loc_18004D79E
0x18004d790  mov     rcx, rbx; hMem
0x18004d793  call    cs:__imp_LocalFree
0x18004d799  jmp     loc_18004D98E
0x18004d79e  mov     eax, [rbp+var_38]
0x18004d7a1  xor     ecx, ecx; uFlags
0x18004d7a3  inc     eax
0x18004d7a5  mov     esi, eax
0x18004d7a7  lea     rdx, [rax+rax]; uBytes
0x18004d7ab  call    cs:__imp_LocalAlloc
0x18004d7b1  mov     [rbx+28h], rax
0x18004d7b5  test    rax, rax
0x18004d7b8  jnz     short loc_18004D7C5
0x18004d7ba  mov     rcx, rbx; hMem
0x18004d7bd  call    cs:__imp_LocalFree
0x18004d7c3  jmp     short loc_18004D76E
0x18004d7c5  mov     r8, r14; wchar_t *
0x18004d7c8  mov     rdx, rsi; unsigned __int64
0x18004d7cb  mov     rcx, rax; wchar_t *
0x18004d7ce  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18004d7d3  mov     esi, eax
0x18004d7d5  test    eax, eax
0x18004d7d7  jns     short loc_18004D80E
0x18004d7d9  mov     rcx, [rbx+28h]; hMem
0x18004d7dd  call    cs:__imp_LocalFree
0x18004d7e3  mov     rcx, rbx; hMem
0x18004d7e6  call    cs:__imp_LocalFree
0x18004d7ec  mov     ecx, esi
0x18004d7ee  and     ecx, 1FFF0000h
0x18004d7f4  cmp     ecx, 70000h
0x18004d7fa  jnz     short loc_18004D807
0x18004d7fc  movzx   ecx, si
0x18004d7ff  test    ecx, ecx
0x18004d801  jnz     loc_18004D988
0x18004d807  mov     ecx, esi
0x18004d809  jmp     loc_18004D988
0x18004d80e  mov     [rbx+20h], rdi
0x18004d812  lea     rax, [rbx+10h]
0x18004d816  mov     esi, 5
0x18004d81b  mov     [rax+8], rax
0x18004d81f  mov     [rax], rax
0x18004d822  cmp     [rdi+144h], si
0x18004d829  jbe     short loc_18004D86F
0x18004d82b  lea     rax, aApiopennetinte_0; "ApiOpenNetInterfaceEx"
0x18004d832  mov     [rbp+var_20], r14
0x18004d836  mov     [rbp+var_30], rax
0x18004d83a  lea     rdx, [rbp+dwErrCode]
0x18004d83e  lea     rax, [rdi+28h]
0x18004d842  mov     dword ptr [rbp+var_18], r12d
0x18004d846  mov     [rbp+var_28], rax
0x18004d84a  lea     rcx, [rbp+var_30]
0x18004d84e  lea     rax, [rbp+var_3C]
0x18004d852  mov     r8, rdi
0x18004d855  mov     [rbp+var_10], rax
0x18004d859  lea     rax, [rbp+dwErrCode]
0x18004d85d  mov     [rbp+var_8], rax
0x18004d861  call    ??$ReconnectOnNull@VOpenNetInterfaceExFunctor@@@@YAPEAXAEBVOpenNetInterfaceExFunctor@@PEAKPEAU_CLUSTER@@@Z; ReconnectOnNull<OpenNetInterfaceExFunctor>(OpenNetInterfaceExFunctor const &,ulong *,_CLUSTER *)
0x18004d866  mov     [rbx+30h], rax
0x18004d86a  mov     eax, [rbp+dwErrCode]
0x18004d86d  jmp     short loc_18004D8C5
0x18004d86f  cmp     [rbp+arg_20], 0
0x18004d873  jz      short loc_18004D8B5
0x18004d875  lea     rax, aApiopennetinte; "ApiOpenNetInterface"
0x18004d87c  mov     [rbp+var_20], r14
0x18004d880  mov     [rbp+var_30], rax
0x18004d884  lea     rdx, [rbp+dwErrCode]
0x18004d888  lea     rax, [rdi+28h]
0x18004d88c  mov     r8, rdi
0x18004d88f  mov     [rbp+var_28], rax
0x18004d893  lea     rcx, [rbp+var_30]
0x18004d897  lea     rax, [rbp+dwErrCode]
0x18004d89b  mov     [rbp+var_18], rax
0x18004d89f  call    ??$ReconnectOnNull@VOpenNetInterfaceFunctor@@@@YAPEAXAEBVOpenNetInterfaceFunctor@@PEAKPEAU_CLUSTER@@@Z; ReconnectOnNull<OpenNetInterfaceFunctor>(OpenNetInterfaceFunctor const &,ulong *,_CLUSTER *)
0x18004d8a4  mov     [rbx+30h], rax
0x18004d8a8  mov     ecx, 10000000h
0x18004d8ad  mov     eax, [rbp+dwErrCode]
0x18004d8b0  mov     [rbp+var_3C], ecx
0x18004d8b3  jmp     short loc_18004D8C8
0x18004d8b5  mov     eax, 6D1h
0x18004d8ba  mov     qword ptr [rbx+30h], 0
0x18004d8c2  mov     [rbp+dwErrCode], eax
0x18004d8c5  mov     ecx, [rbp+var_3C]
0x18004d8c8  cmp     qword ptr [rbx+30h], 0
0x18004d8cd  jz      short loc_18004D93D
0x18004d8cf  test    eax, eax
0x18004d8d1  jnz     short loc_18004D93D
0x18004d8d3  test    r15, r15
0x18004d8d6  jz      short loc_18004D8DB
0x18004d8d8  mov     [r15], ecx
0x18004d8db  mov     [rbx+38h], ecx
0x18004d8de  lea     rsi, [rdi+0E8h]
0x18004d8e5  mov     rcx, rsi; lpCriticalSection
0x18004d8e8  call    cs:__imp_EnterCriticalSection
0x18004d8ee  add     rdi, 88h
0x18004d8f5  mov     rax, [rdi]
0x18004d8f8  cmp     [rax+8], rdi
0x18004d8fc  jz      short loc_18004D905
0x18004d8fe  mov     ecx, 3
0x18004d903  int     29h; Win8: RtlFailFast(ecx)
0x18004d905  mov     [rbx], rax
0x18004d908  mov     rcx, rsi; lpCriticalSection
0x18004d90b  mov     [rbx+8], rdi
0x18004d90f  mov     [rax+8], rbx
0x18004d913  mov     [rdi], rbx
0x18004d916  call    cs:__imp_LeaveCriticalSection
0x18004d91c  mov     rdx, rbx
0x18004d91f  call    ??$Insert@PEAU_HNETINTERFACE@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAAKPEAU_HNETINTERFACE@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Insert<_HNETINTERFACE *>(_HNETINTERFACE *)
0x18004d924  mov     edi, eax
0x18004d926  test    eax, eax
0x18004d928  jz      short loc_18004D938
0x18004d92a  xor     edx, edx; int
0x18004d92c  mov     rcx, rbx; hMem
0x18004d92f  call    ?CloseClusterNetInterfaceCommon@@YAHPEAU_HNETINTERFACE@@H@Z; CloseClusterNetInterfaceCommon(_HNETINTERFACE *,int)
0x18004d934  mov     ecx, edi
0x18004d936  jmp     short loc_18004D988
0x18004d938  mov     rax, rbx
0x18004d93b  jmp     short loc_18004D990
0x18004d93d  cmp     eax, 6D1h
0x18004d942  jnz     short loc_18004D972
0x18004d944  cmp     [rdi+144h], si
0x18004d94b  jbe     short loc_18004D972
0x18004d94d  lea     rax, aProcnumOutOfRa; "Procnum out of range when we thought we"...
0x18004d954  mov     r9d, 8Bh
0x18004d95a  lea     r8, aOpenclusternet_3; "OpenClusterNetInterfaceImpl"
0x18004d961  mov     [rsp+70h+var_50], rax
0x18004d966  mov     edx, esi
0x18004d968  mov     ecx, 2
0x18004d96d  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18004d972  mov     rcx, [rbx+28h]; hMem
0x18004d976  call    cs:__imp_LocalFree
0x18004d97c  mov     rcx, rbx; hMem
0x18004d97f  call    cs:__imp_LocalFree
0x18004d985  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x18004d988  call    cs:__imp_SetLastError
0x18004d98e  xor     eax, eax
0x18004d990  add     rsp, 70h
0x18004d994  pop     r15
0x18004d996  pop     r14
0x18004d998  pop     r12
0x18004d99a  pop     rdi
0x18004d99b  pop     rsi
0x18004d99c  pop     rbx
0x18004d99d  pop     rbp
0x18004d99e  retn
```
