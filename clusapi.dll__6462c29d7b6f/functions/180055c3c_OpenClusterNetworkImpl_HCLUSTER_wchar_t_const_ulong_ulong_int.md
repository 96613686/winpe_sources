# OpenClusterNetworkImpl(_HCLUSTER *,wchar_t const *,ulong,ulong *,int)

- ea: `0x180055c3c`
- end: `0x180055ec5`
- name: `?OpenClusterNetworkImpl@@YAPEAU_HNETWORK@@PEAU_HCLUSTER@@PEB_WKPEAKH@Z`
- size: `649`
- prototype: `struct _HNETWORK *(struct _HCLUSTER *, const wchar_t *, unsigned int, unsigned int *, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003855c`
- `0x180056240`
- `0x180056270`

## callees

- `0x18001236c`
- `0x180014638`
- `0x180025478`
- `0x180054bd4`
- `0x180055618`
- `0x1800557f8`
- `0x1800559c4`
- `0x180055c3c`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055e3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055e3d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055e12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055e12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055eae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055eae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055cbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055ce9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055d09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055d12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055e9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055ea5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055cbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055ce9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055d09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055d12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055e9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055ea5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180055c8c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180055cd7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180055c8c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180055cd7`

## string_xrefs

- `0x180055e89`: `OpenClusterNetworkImpl`
- `0x180055da2`: `ApiOpenNetwork`
- `0x180055d58`: `ApiOpenNetworkEx`

## pseudocode

```c
struct _HNETWORK *__fastcall OpenClusterNetworkImpl(
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
        v25 = "ApiOpenNetwork";
        v26 = (char *)a1 + 40;
        p_dwErrCode = &dwErrCode;
        v10[6] = ReconnectOnNull<OpenNetworkFunctor>(&v25, &dwErrCode, a1);
        v15 = 0x10000000;
        v14 = dwErrCode;
        v23 = 0x10000000;
LABEL_19:
        if ( !v10[6] || v14 )
        {
          if ( v14 == 1745 && *((_WORD *)a1 + 162) > 5u )
            TraceMsg(
              2u,
              4u,
              (__int64)L"OpenClusterNetworkImpl",
              144,
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
          v17 = (char *)a1 + 120;
          v18 = *(_QWORD *)v17;
          if ( *(char **)(*(_QWORD *)v17 + 8LL) != v17 )
            __fastfail(3u);
          *v10 = v18;
          v10[1] = v17;
          *(_QWORD *)(v18 + 8) = v10;
          *(_QWORD *)v17 = v10;
          LeaveCriticalSection(v16);
          v20 = HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Insert<_HNETWORK *>(
                  v19,
                  v10);
          if ( !v20 )
            return (struct _HNETWORK *)v10;
          CloseClusterNetworkCommon(v10, 0);
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
      v25 = "ApiOpenNetworkEx";
      LODWORD(p_dwErrCode) = a3;
      v26 = (char *)a1 + 40;
      v29 = &v23;
      v30 = &dwErrCode;
      v10[6] = ReconnectOnNull<OpenNetworkExFunctor>(&v25, &dwErrCode, a1);
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
0x180055c3c  push    rbp
0x180055c3e  push    rbx
0x180055c3f  push    rsi
0x180055c40  push    rdi
0x180055c41  push    r12
0x180055c43  push    r14
0x180055c45  push    r15
0x180055c47  mov     rbp, rsp
0x180055c4a  sub     rsp, 70h
0x180055c4e  mov     r14, rdx
0x180055c51  mov     r15, r9
0x180055c54  mov     rdx, rcx
0x180055c57  mov     r12d, r8d
0x180055c5a  mov     rdi, rcx
0x180055c5d  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x180055c62  test    al, al
0x180055c64  jnz     short loc_180055C70
0x180055c66  mov     ecx, 6
0x180055c6b  jmp     loc_180055EAE
0x180055c70  mov     edx, 40h ; '@'; uBytes
0x180055c75  mov     [rbp+dwErrCode], 0
0x180055c7c  xor     ecx, ecx; uFlags
0x180055c7e  mov     [rbp+var_38], 0
0x180055c85  mov     [rbp+var_3C], 0
0x180055c8c  call    cs:__imp_LocalAlloc
0x180055c92  mov     rbx, rax
0x180055c95  test    rax, rax
0x180055c98  jnz     short loc_180055CA4
0x180055c9a  mov     ecx, 8
0x180055c9f  jmp     loc_180055EAE
0x180055ca4  lea     r8, [rbp+var_38]; unsigned int *
0x180055ca8  mov     edx, 7FFFFFFFh; unsigned int
0x180055cad  mov     rcx, r14; wchar_t *
0x180055cb0  call    ?MylstrlenW@@YAKPEB_WKPEAK@Z; MylstrlenW(wchar_t const *,ulong,ulong *)
0x180055cb5  mov     [rbp+dwErrCode], eax
0x180055cb8  test    eax, eax
0x180055cba  jz      short loc_180055CCA
0x180055cbc  mov     rcx, rbx; hMem
0x180055cbf  call    cs:__imp_LocalFree
0x180055cc5  jmp     loc_180055EB4
0x180055cca  mov     eax, [rbp+var_38]
0x180055ccd  xor     ecx, ecx; uFlags
0x180055ccf  inc     eax
0x180055cd1  mov     esi, eax
0x180055cd3  lea     rdx, [rax+rax]; uBytes
0x180055cd7  call    cs:__imp_LocalAlloc
0x180055cdd  mov     [rbx+28h], rax
0x180055ce1  test    rax, rax
0x180055ce4  jnz     short loc_180055CF1
0x180055ce6  mov     rcx, rbx; hMem
0x180055ce9  call    cs:__imp_LocalFree
0x180055cef  jmp     short loc_180055C9A
0x180055cf1  mov     r8, r14; wchar_t *
0x180055cf4  mov     rdx, rsi; unsigned __int64
0x180055cf7  mov     rcx, rax; wchar_t *
0x180055cfa  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180055cff  mov     esi, eax
0x180055d01  test    eax, eax
0x180055d03  jns     short loc_180055D3A
0x180055d05  mov     rcx, [rbx+28h]; hMem
0x180055d09  call    cs:__imp_LocalFree
0x180055d0f  mov     rcx, rbx; hMem
0x180055d12  call    cs:__imp_LocalFree
0x180055d18  mov     ecx, esi
0x180055d1a  and     ecx, 1FFF0000h
0x180055d20  cmp     ecx, 70000h
0x180055d26  jnz     short loc_180055D33
0x180055d28  movzx   ecx, si
0x180055d2b  test    ecx, ecx
0x180055d2d  jnz     loc_180055EAE
0x180055d33  mov     ecx, esi
0x180055d35  jmp     loc_180055EAE
0x180055d3a  mov     [rbx+20h], rdi
0x180055d3e  lea     rax, [rbx+10h]
0x180055d42  mov     [rax+8], rax
0x180055d46  mov     esi, 6D1h
0x180055d4b  mov     [rax], rax
0x180055d4e  cmp     word ptr [rdi+144h], 5
0x180055d56  jbe     short loc_180055D9C
0x180055d58  lea     rax, aApiopennetwork; "ApiOpenNetworkEx"
0x180055d5f  mov     [rbp+var_20], r14
0x180055d63  mov     [rbp+var_30], rax
0x180055d67  lea     rdx, [rbp+dwErrCode]
0x180055d6b  lea     rax, [rdi+28h]
0x180055d6f  mov     dword ptr [rbp+var_18], r12d
0x180055d73  mov     [rbp+var_28], rax
0x180055d77  lea     rcx, [rbp+var_30]
0x180055d7b  lea     rax, [rbp+var_3C]
0x180055d7f  mov     r8, rdi
0x180055d82  mov     [rbp+var_10], rax
0x180055d86  lea     rax, [rbp+dwErrCode]
0x180055d8a  mov     [rbp+var_8], rax
0x180055d8e  call    ??$ReconnectOnNull@VOpenNetworkExFunctor@@@@YAPEAXAEBVOpenNetworkExFunctor@@PEAKPEAU_CLUSTER@@@Z; ReconnectOnNull<OpenNetworkExFunctor>(OpenNetworkExFunctor const &,ulong *,_CLUSTER *)
0x180055d93  mov     [rbx+30h], rax
0x180055d97  mov     eax, [rbp+dwErrCode]
0x180055d9a  jmp     short loc_180055DEF
0x180055d9c  cmp     [rbp+arg_20], 0
0x180055da0  jz      short loc_180055DE2
0x180055da2  lea     rax, aApiopennetwork_0; "ApiOpenNetwork"
0x180055da9  mov     [rbp+var_20], r14
0x180055dad  mov     [rbp+var_30], rax
0x180055db1  lea     rdx, [rbp+dwErrCode]
0x180055db5  lea     rax, [rdi+28h]
0x180055db9  mov     r8, rdi
0x180055dbc  mov     [rbp+var_28], rax
0x180055dc0  lea     rcx, [rbp+var_30]
0x180055dc4  lea     rax, [rbp+dwErrCode]
0x180055dc8  mov     [rbp+var_18], rax
0x180055dcc  call    ??$ReconnectOnNull@VOpenNetworkFunctor@@@@YAPEAXAEBVOpenNetworkFunctor@@PEAKPEAU_CLUSTER@@@Z; ReconnectOnNull<OpenNetworkFunctor>(OpenNetworkFunctor const &,ulong *,_CLUSTER *)
0x180055dd1  mov     [rbx+30h], rax
0x180055dd5  mov     ecx, 10000000h
0x180055dda  mov     eax, [rbp+dwErrCode]
0x180055ddd  mov     [rbp+var_3C], ecx
0x180055de0  jmp     short loc_180055DF2
0x180055de2  mov     eax, esi
0x180055de4  mov     qword ptr [rbx+30h], 0
0x180055dec  mov     [rbp+dwErrCode], eax
0x180055def  mov     ecx, [rbp+var_3C]
0x180055df2  cmp     qword ptr [rbx+30h], 0
0x180055df7  jz      short loc_180055E64
0x180055df9  test    eax, eax
0x180055dfb  jnz     short loc_180055E64
0x180055dfd  test    r15, r15
0x180055e00  jz      short loc_180055E05
0x180055e02  mov     [r15], ecx
0x180055e05  mov     [rbx+38h], ecx
0x180055e08  lea     rsi, [rdi+0E8h]
0x180055e0f  mov     rcx, rsi; lpCriticalSection
0x180055e12  call    cs:__imp_EnterCriticalSection
0x180055e18  add     rdi, 78h ; 'x'
0x180055e1c  mov     rax, [rdi]
0x180055e1f  cmp     [rax+8], rdi
0x180055e23  jz      short loc_180055E2C
0x180055e25  mov     ecx, 3
0x180055e2a  int     29h; Win8: RtlFailFast(ecx)
0x180055e2c  mov     [rbx], rax
0x180055e2f  mov     rcx, rsi; lpCriticalSection
0x180055e32  mov     [rbx+8], rdi
0x180055e36  mov     [rax+8], rbx
0x180055e3a  mov     [rdi], rbx
0x180055e3d  call    cs:__imp_LeaveCriticalSection
0x180055e43  mov     rdx, rbx
0x180055e46  call    ??$Insert@PEAU_HNETWORK@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAAKPEAU_HNETWORK@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Insert<_HNETWORK *>(_HNETWORK *)
0x180055e4b  mov     edi, eax
0x180055e4d  test    eax, eax
0x180055e4f  jz      short loc_180055E5F
0x180055e51  xor     edx, edx; int
0x180055e53  mov     rcx, rbx; hMem
0x180055e56  call    ?CloseClusterNetworkCommon@@YAHPEAU_HNETWORK@@H@Z; CloseClusterNetworkCommon(_HNETWORK *,int)
0x180055e5b  mov     ecx, edi
0x180055e5d  jmp     short loc_180055EAE
0x180055e5f  mov     rax, rbx
0x180055e62  jmp     short loc_180055EB6
0x180055e64  cmp     eax, esi
0x180055e66  jnz     short loc_180055E98
0x180055e68  cmp     word ptr [rdi+144h], 5
0x180055e70  jbe     short loc_180055E98
0x180055e72  mov     edx, 4
0x180055e77  lea     rax, aProcnumOutOfRa; "Procnum out of range when we thought we"...
0x180055e7e  mov     r9d, 90h
0x180055e84  mov     [rsp+70h+var_50], rax
0x180055e89  lea     r8, aOpenclusternet_4; "OpenClusterNetworkImpl"
0x180055e90  lea     ecx, [rdx-2]
0x180055e93  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180055e98  mov     rcx, [rbx+28h]; hMem
0x180055e9c  call    cs:__imp_LocalFree
0x180055ea2  mov     rcx, rbx; hMem
0x180055ea5  call    cs:__imp_LocalFree
0x180055eab  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x180055eae  call    cs:__imp_SetLastError
0x180055eb4  xor     eax, eax
0x180055eb6  add     rsp, 70h
0x180055eba  pop     r15
0x180055ebc  pop     r14
0x180055ebe  pop     r12
0x180055ec0  pop     rdi
0x180055ec1  pop     rsi
0x180055ec2  pop     rbx
0x180055ec3  pop     rbp
0x180055ec4  retn
```
