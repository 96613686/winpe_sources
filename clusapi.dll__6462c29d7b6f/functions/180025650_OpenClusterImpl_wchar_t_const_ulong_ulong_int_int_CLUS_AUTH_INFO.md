# OpenClusterImpl(wchar_t const *,ulong,ulong *,int,int,CLUS_AUTH_INFO *)

- ea: `0x180025650`
- end: `0x180025b3a`
- name: `?OpenClusterImpl@@YAPEAU_HCLUSTER@@PEB_WKPEAKHHPEAUCLUS_AUTH_INFO@@@Z`
- size: `1258`
- prototype: `struct _HCLUSTER *__fastcall(const wchar_t *, unsigned int, unsigned int *, int, int, struct CLUS_AUTH_INFO *)`
- caller_count: `11`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x180025650`
- `0x18002e9f0`
- `0x18002ea30`
- `0x18002ea70`
- `0x18002eaa0`
- `0x18003a4f0`
- `0x18003abe0`
- `0x18003f638`
- `0x1800441a0`
- `0x1800451b0`
- `0x18007a380`

## callees

- `0x180002f50`
- `0x18000335c`
- `0x18001989c`
- `0x18001ba0c`
- `0x18001cc2c`
- `0x18001f650`
- `0x180021fe0`
- `0x180023bf4`
- `0x180024bb8`
- `0x180025560`
- `0x180025650`
- `0x180028f30`
- `0x180029450`
- `0x180029578`
- `0x18003a1f0`
- `0x18003a45c`
- `0x18003aa0c`
- `0x18005f6c0`
- `0x18006f910`
- `0x180090c78`
- `0x180090ca4`
- `0x180093e8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002570b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002570b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025771`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025771`

## string_xrefs

- `0x1800256e1`: `OpenClusterImpl`
- `0x180025b2e`: `OpenClusterImpl`
- `0x1800257ed`: `ApiOpenClusterEx not supported, attempting ApiOpenCluster.`
- `0x18002582b`: `ApiOpenCluster failed - %d`
- `0x18002585a`: `ApiOpenClusterEx failed - %d`
- `0x18002590d`: `Failed to obtain thread or process token - %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
struct _HCLUSTER *__fastcall OpenClusterImpl(
        const wchar_t *a1,
        unsigned int a2,
        unsigned int *a3,
        int a4,
        int a5,
        struct CLUS_AUTH_INFO *a6)
{
  unsigned int *v7; // r13
  const WCHAR *v9; // rax
  struct _CLUSTER *Cluster; // rax
  unsigned int v11; // r8d
  struct _CLUSTER *v12; // rdi
  int v13; // edx
  __int64 v15; // rax
  __int64 v16; // rax
  char v17; // r14
  unsigned __int16 *v18; // rsi
  unsigned int ReconnectCandidates; // eax
  unsigned int ClusterMajorVersion; // eax
  int v21; // eax
  __int64 v22; // r13
  char v23; // r14
  __int64 v24; // rcx
  char v25; // si
  __int64 v26; // rcx
  _QWORD *v27; // rsi
  unsigned __int64 i; // r15
  __int64 v29; // r14
  const wchar_t *v30; // rax
  struct _HCLUSTER *v31; // rax
  __int64 v32; // rdx
  struct CLUS_AUTH_INFO *v33; // [rsp+28h] [rbp-E0h]
  __int64 dwErrCode; // [rsp+30h] [rbp-D8h] BYREF
  int v35; // [rsp+38h] [rbp-D0h] BYREF
  struct _HCLUSTER *v36; // [rsp+40h] [rbp-C8h] BYREF
  int v37; // [rsp+48h] [rbp-C0h]
  unsigned int v38; // [rsp+4Ch] [rbp-BCh]
  int v39; // [rsp+50h] [rbp-B8h]
  unsigned int *v40; // [rsp+58h] [rbp-B0h]
  struct _CLUSTER *v41; // [rsp+60h] [rbp-A8h]
  __int128 v42; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+78h] [rbp-90h]
  struct CLUS_AUTH_INFO *v44; // [rsp+80h] [rbp-88h]
  unsigned int *v45; // [rsp+88h] [rbp-80h]
  _BYTE v46[32]; // [rsp+A0h] [rbp-68h] BYREF

  v39 = a4;
  v7 = a3;
  v40 = a3;
  v38 = a2;
  v45 = a3;
  v37 = a5;
  v44 = a6;
  LODWORD(v36) = 0;
  LODWORD(dwErrCode) = 0;
  v9 = a1;
  if ( !a1 )
    v9 = &base;
  TraceMsg(5, 0, L"OpenClusterImpl", 1729, L"Beginning to connect to cluster name: %ws", v9, dwErrCode);
  Cluster = AllocateCluster();
  v12 = Cluster;
  v41 = Cluster;
  if ( !Cluster )
  {
    LODWORD(dwErrCode) = GetLastError();
    LODWORD(v33) = dwErrCode;
    TraceMsg(2, 0, L"OpenClusterImpl", 1734, L"Could not allocate cluster. sc = %u", v33);
LABEL_5:
    LODWORD(v33) = dwErrCode;
    TraceMsg(2, 0, L"OpenClusterImpl", 1866, L"Could not connect to cluster.  sc = %u", v33);
    FreeClusterCommon(v12, v13, 1);
    SetLastError(dwErrCode);
    return 0;
  }
  LODWORD(dwErrCode) = ConnectCluster(Cluster, a1, v11, a6);
  if ( (_DWORD)dwErrCode )
    goto LABEL_5;
  v35 = 0x10000000;
  v15 = ApiOpenClusterEx(*((_QWORD *)v12 + 5), v38, &v35, &dwErrCode);
  *((_QWORD *)v12 + 6) = v15;
  if ( v15 )
  {
    v17 = 1;
    v18 = (unsigned __int16 *)((char *)v12 + 324);
  }
  else
  {
    if ( (_DWORD)dwErrCode != 1745 || !a4 )
    {
      LODWORD(v33) = dwErrCode;
      TraceMsg(2, 0, L"OpenClusterImpl", 1764, L"ApiOpenClusterEx failed - %d", v33);
      goto LABEL_5;
    }
    TraceMsg(3, 0, L"OpenClusterImpl", 1751, L"ApiOpenClusterEx not supported, attempting ApiOpenCluster.");
    v16 = ApiOpenCluster(*((_QWORD *)v12 + 5), &dwErrCode);
    *((_QWORD *)v12 + 6) = v16;
    if ( !v16 )
    {
      LODWORD(v33) = dwErrCode;
      TraceMsg(2, 0, L"OpenClusterImpl", 1756, L"ApiOpenCluster failed - %d", v33);
      goto LABEL_5;
    }
    v17 = 0;
    v18 = (unsigned __int16 *)((char *)v12 + 324);
    *((_WORD *)v12 + 162) = 5;
    v35 = 0x10000000;
  }
  ReconnectCandidates = GetReconnectCandidates(v12);
  LODWORD(dwErrCode) = ReconnectCandidates;
  if ( ReconnectCandidates )
  {
    LODWORD(v33) = ReconnectCandidates;
    TraceMsg(2, 0, L"OpenClusterImpl", 1774, L"Failed to get reconnect candidates - %d", v33);
    goto LABEL_5;
  }
  if ( v17 )
  {
    ClusterMajorVersion = GetClusterMajorVersion(v12, v18, (unsigned __int16 *const)v12 + 163);
    LODWORD(dwErrCode) = ClusterMajorVersion;
    if ( ClusterMajorVersion )
    {
      LODWORD(v33) = ClusterMajorVersion;
      TraceMsg(2, 0, L"OpenClusterImpl", 1784, L"Failed to get version information - %d", v33);
      goto LABEL_5;
    }
    *((_WORD *)v12 + 164) = GetClusterFunctionalLevel(v12);
    *((_WORD *)v12 + 165) = GetClusterUpgradeVersion(v12);
  }
  if ( v37 )
  {
    v21 = ObtainThreadTokenIfExists((PHANDLE)v12 + 42);
    LODWORD(dwErrCode) = v21;
    if ( v21 )
    {
      LODWORD(v33) = v21;
      TraceMsg(2, 0, L"OpenClusterImpl", 1798, L"Failed to obtain thread or process token - %d", v33);
      goto LABEL_5;
    }
    *((_DWORD *)v12 + 86) = 1;
  }
  *((_DWORD *)v12 + 80) = v35;
  if ( *v18 >= 9u && a1 && *a1 )
  {
    BYTE5(dwErrCode) = 1;
    v42 = 0;
    v43 = 0;
    LODWORD(dwErrCode) = GetScaleoutClusters(v12, &v42);
    if ( (_DWORD)dwErrCode )
    {
      LODWORD(dwErrCode) = 0;
LABEL_50:
      BYTE5(dwErrCode) = 0;
      std::vector<std::wstring>::_Tidy(&v42);
      goto LABEL_51;
    }
    v22 = v42;
    if ( (unsigned __int64)((__int64)(*((_QWORD *)&v42 + 1) - v42) >> 5) < 2 )
    {
      v23 = (char)v36;
    }
    else
    {
      std::wstring::wstring(v46, a1);
      v23 = 1;
      LODWORD(v36) = 1;
      if ( (unsigned __int8)cxl::CaseInsensitive_Equal::operator()(v24, v22, v46) )
      {
        v25 = 1;
LABEL_34:
        if ( (v23 & 1) != 0 )
          std::wstring::_Tidy_deallocate(v46);
        if ( v25 )
        {
          v27 = operator new(0x18u);
          *v27 = 0;
          v27[1] = 0;
          v27[2] = 0;
          *((_QWORD *)v12 + 44) = v27;
          *((_DWORD *)v12 + 87) = 1;
          for ( i = 1; i < (*((_QWORD *)&v42 + 1) - v22) >> 5; ++i )
          {
            v29 = 32 * i;
            if ( i == 1 || !(unsigned __int8)cxl::CaseInsensitive_Equal::operator()(v26, v29 + v22, v22 + 32) )
            {
              v30 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v29 + v22);
              v31 = OpenClusterImpl(v30, v38, 0, v39, v37, v44);
              if ( v31 )
              {
                BYTE4(dwErrCode) = 0;
                v36 = v31;
                v32 = v27[1];
                if ( v32 == v27[2] )
                {
                  std::vector_std::shared_ptr__CLUSTER__std::allocator_std::shared_ptr__CLUSTER_____::_Emplace_reallocate__CLUSTER____lambda_67c530c70e2b457d3f7837c4dfce7e4d____(
                    v27,
                    v32,
                    &v36,
                    (char *)&dwErrCode + 4);
                }
                else
                {
                  std::_Default_allocator_traits_std::allocator_std::shared_ptr__CLUSTER_____::construct_std::shared_ptr__CLUSTER___CLUSTER____lambda_67c530c70e2b457d3f7837c4dfce7e4d____(
                    v26,
                    v32,
                    &v36,
                    (char *)&dwErrCode + 4);
                  v27[1] += 16LL;
                }
              }
              else if ( i == 1 )
              {
                LODWORD(dwErrCode) = GetLastError();
                std::vector<std::wstring>::_Tidy(&v42);
                goto LABEL_5;
              }
            }
          }
        }
        v7 = v40;
        goto LABEL_50;
      }
    }
    v25 = 0;
    goto LABEL_34;
  }
LABEL_51:
  if ( v7 )
    *v7 = v35;
  return v12;
}

```

## disassembly

```asm
0x180025650  push    rbx
0x180025652  push    rsi
0x180025653  push    rdi
0x180025654  push    r12
0x180025656  push    r13
0x180025658  push    r14
0x18002565a  push    r15
0x18002565c  sub     rsp, 0D0h
0x180025663  mov     rax, cs:__security_cookie
0x18002566a  xor     rax, rsp
0x18002566d  mov     [rsp+108h+var_48], rax
0x180025675  mov     esi, r9d
0x180025678  mov     [rsp+108h+var_B8], r9d
0x18002567d  mov     r13, r8
0x180025680  mov     [rsp+108h+var_B0], r8
0x180025685  mov     [rsp+108h+var_BC], edx
0x180025689  mov     r15, rcx
0x18002568c  mov     [rsp+108h+var_80], r8
0x180025694  mov     eax, [rsp+108h+arg_20]
0x18002569b  mov     [rsp+108h+var_C0], eax
0x18002569f  mov     r14, [rsp+108h+arg_28]
0x1800256a7  mov     [rsp+108h+var_88], r14
0x1800256af  xor     ebx, ebx
0x1800256b1  mov     dword ptr [rsp+108h+var_C8], ebx
0x1800256b5  mov     [rsp+108h+dwErrCode], ebx
0x1800256b9  lea     rcx, base
0x1800256c0  mov     rax, r15
0x1800256c3  test    r15, r15
0x1800256c6  cmovz   rax, rcx
0x1800256ca  mov     [rsp+108h+var_E0], rax
0x1800256cf  lea     rax, aBeginningToCon; "Beginning to connect to cluster name: %"...
0x1800256d6  mov     qword ptr [rsp+108h+var_E8], rax
0x1800256db  mov     r9d, 6C1h
0x1800256e1  lea     r12, aOpenclusterimp; "OpenClusterImpl"
0x1800256e8  mov     r8, r12
0x1800256eb  xor     edx, edx
0x1800256ed  lea     ecx, [rbx+5]
0x1800256f0  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800256f5  call    ?AllocateCluster@@YAPEAU_CLUSTER@@XZ; AllocateCluster(void)
0x1800256fa  mov     rdi, rax
0x1800256fd  mov     [rsp+108h+var_A8], rax
0x180025702  test    rax, rax
0x180025705  jnz     loc_18002579C
0x18002570b  call    cs:__imp_GetLastError
0x180025711  mov     [rsp+108h+dwErrCode], eax
0x180025715  mov     dword ptr [rsp+108h+var_E0], eax
0x180025719  lea     rax, aCouldNotAlloca; "Could not allocate cluster. sc = %u"
0x180025720  mov     r9d, 6C6h
0x180025726  mov     qword ptr [rsp+108h+var_E8], rax
0x18002572b  mov     r8, r12
0x18002572e  xor     edx, edx
0x180025730  lea     ecx, [rdx+2]
0x180025733  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180025738  mov     eax, [rsp+108h+dwErrCode]
0x18002573c  mov     dword ptr [rsp+108h+var_E0], eax
0x180025740  lea     rax, aCouldNotConnec; "Could not connect to cluster.  sc = %u"
0x180025747  mov     qword ptr [rsp+108h+var_E8], rax
0x18002574c  mov     r9d, 74Ah
0x180025752  mov     r8, r12
0x180025755  xor     edx, edx
0x180025757  lea     ecx, [rdx+2]
0x18002575a  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18002575f  mov     r8d, 1; int
0x180025765  mov     rcx, rdi; struct _CLUSTER *
0x180025768  call    ?FreeClusterCommon@@YAXPEAU_CLUSTER@@HH@Z; FreeClusterCommon(_CLUSTER *,int,int)
0x18002576d  mov     ecx, [rsp+108h+dwErrCode]; dwErrCode
0x180025771  call    cs:__imp_SetLastError
0x180025777  xor     eax, eax
0x180025779  mov     rcx, [rsp+108h+var_48]
0x180025781  xor     rcx, rsp; StackCookie
0x180025784  call    __security_check_cookie
0x180025789  add     rsp, 0D0h
0x180025790  pop     r15
0x180025792  pop     r14
0x180025794  pop     r13
0x180025796  pop     r12
0x180025798  pop     rdi
0x180025799  pop     rsi
0x18002579a  pop     rbx
0x18002579b  retn
0x18002579c  mov     r9, r14; struct CLUS_AUTH_INFO *
0x18002579f  mov     rdx, r15; wchar_t *
0x1800257a2  mov     rcx, rdi; struct _CLUSTER *
0x1800257a5  call    ?ConnectCluster@@YAKPEAU_CLUSTER@@PEB_WKPEAUCLUS_AUTH_INFO@@@Z; ConnectCluster(_CLUSTER *,wchar_t const *,ulong,CLUS_AUTH_INFO *)
0x1800257aa  mov     [rsp+108h+dwErrCode], eax
0x1800257ae  test    eax, eax
0x1800257b0  jnz     short loc_180025738
0x1800257b2  mov     [rsp+108h+var_D0], 10000000h
0x1800257ba  lea     r9, [rsp+108h+dwErrCode]
0x1800257bf  lea     r8, [rsp+108h+var_D0]
0x1800257c4  mov     edx, [rsp+108h+var_BC]
0x1800257c8  mov     rcx, [rdi+28h]
0x1800257cc  call    ApiOpenClusterEx
0x1800257d1  mov     [rdi+30h], rax
0x1800257d5  test    rax, rax
0x1800257d8  jnz     loc_18002586C
0x1800257de  mov     eax, [rsp+108h+dwErrCode]
0x1800257e2  cmp     eax, 6D1h
0x1800257e7  jnz     short loc_180025856
0x1800257e9  test    esi, esi
0x1800257eb  jz      short loc_180025856
0x1800257ed  lea     rax, aApiopencluster; "ApiOpenClusterEx not supported, attempt"...
0x1800257f4  mov     qword ptr [rsp+108h+var_E8], rax
0x1800257f9  mov     r9d, 6D7h
0x1800257ff  mov     r8, r12
0x180025802  xor     edx, edx
0x180025804  lea     ecx, [rdx+3]
0x180025807  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18002580c  lea     rdx, [rsp+108h+dwErrCode]
0x180025811  mov     rcx, [rdi+28h]
0x180025815  call    ApiOpenCluster
0x18002581a  mov     [rdi+30h], rax
0x18002581e  test    rax, rax
0x180025821  jnz     short loc_18002583D
0x180025823  mov     eax, [rsp+108h+dwErrCode]
0x180025827  mov     dword ptr [rsp+108h+var_E0], eax
0x18002582b  lea     rax, aApiopencluster_2; "ApiOpenCluster failed - %d"
0x180025832  mov     r9d, 6DCh
0x180025838  jmp     loc_180025726
0x18002583d  mov     r14b, bl
0x180025840  lea     rsi, [rdi+144h]
0x180025847  mov     word ptr [rsi], 5
0x18002584c  mov     [rsp+108h+var_D0], 10000000h
0x180025854  jmp     short loc_180025876
0x180025856  mov     dword ptr [rsp+108h+var_E0], eax
0x18002585a  lea     rax, aApiopencluster_0; "ApiOpenClusterEx failed - %d"
0x180025861  mov     r9d, 6E4h
0x180025867  jmp     loc_180025726
0x18002586c  mov     r14b, 1
0x18002586f  lea     rsi, [rdi+144h]
0x180025876  mov     rcx, rdi; struct _CLUSTER *
0x180025879  call    ?GetReconnectCandidates@@YAKPEAU_CLUSTER@@@Z; GetReconnectCandidates(_CLUSTER *)
0x18002587e  mov     [rsp+108h+dwErrCode], eax
0x180025882  test    eax, eax
0x180025884  jz      short loc_18002589C
0x180025886  mov     dword ptr [rsp+108h+var_E0], eax
0x18002588a  lea     rax, aFailedToGetRec; "Failed to get reconnect candidates - %d"
0x180025891  mov     r9d, 6EEh
0x180025897  jmp     loc_180025726
0x18002589c  test    r14b, r14b
0x18002589f  jz      short loc_1800258EF
0x1800258a1  lea     r8, [rdi+146h]; unsigned __int16 *
0x1800258a8  mov     rdx, rsi; unsigned __int16 *
0x1800258ab  mov     rcx, rdi; struct _HCLUSTER *
0x1800258ae  call    ?GetClusterMajorVersion@@YAKPEAU_HCLUSTER@@QEAG1@Z; GetClusterMajorVersion(_HCLUSTER *,ushort * const,ushort * const)
0x1800258b3  mov     [rsp+108h+dwErrCode], eax
0x1800258b7  test    eax, eax
0x1800258b9  jz      short loc_1800258D1
0x1800258bb  mov     dword ptr [rsp+108h+var_E0], eax
0x1800258bf  lea     rax, aFailedToGetVer; "Failed to get version information - %d"
0x1800258c6  mov     r9d, 6F8h
0x1800258cc  jmp     loc_180025726
0x1800258d1  mov     rcx, rdi; hCluster
0x1800258d4  call    ?GetClusterFunctionalLevel@@YAGPEAU_HCLUSTER@@@Z; GetClusterFunctionalLevel(_HCLUSTER *)
0x1800258d9  mov     [rdi+148h], ax
0x1800258e0  mov     rcx, rdi; struct _HCLUSTER *
0x1800258e3  call    ?GetClusterUpgradeVersion@@YAGPEAU_HCLUSTER@@@Z; GetClusterUpgradeVersion(_HCLUSTER *)
0x1800258e8  mov     [rdi+14Ah], ax
0x1800258ef  cmp     [rsp+108h+var_C0], ebx
0x1800258f3  jz      short loc_180025929
0x1800258f5  lea     rcx, [rdi+150h]; DuplicateTokenHandle
0x1800258fc  call    ?ObtainThreadTokenIfExists@@YAKPEAPEAX@Z; ObtainThreadTokenIfExists(void * *)
0x180025901  mov     [rsp+108h+dwErrCode], eax
0x180025905  test    eax, eax
0x180025907  jz      short loc_18002591F
0x180025909  mov     dword ptr [rsp+108h+var_E0], eax
0x18002590d  lea     rax, aFailedToObtain_0; "Failed to obtain thread or process toke"...
0x180025914  mov     r9d, 706h
0x18002591a  jmp     loc_180025726
0x18002591f  mov     dword ptr [rdi+158h], 1
0x180025929  mov     eax, [rsp+108h+var_D0]
0x18002592d  mov     [rdi+140h], eax
0x180025933  cmp     word ptr [rsi], 9
0x180025937  jb      loc_180025AFC
0x18002593d  test    r15, r15
0x180025940  jz      loc_180025AFC
0x180025946  cmp     [r15], bx
0x18002594a  jz      loc_180025AFC
0x180025950  mov     [rsp+108h+var_D3], 1
0x180025955  xorps   xmm0, xmm0
0x180025958  movdqu  [rsp+108h+var_A0], xmm0
0x18002595e  mov     [rsp+108h+var_90], rbx
0x180025963  lea     rdx, [rsp+108h+var_A0]
0x180025968  mov     rcx, rdi
0x18002596b  call    ?GetScaleoutClusters@@YAKPEAU_HCLUSTER@@AEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z; GetScaleoutClusters(_HCLUSTER *,std::vector<std::wstring> &)
0x180025970  mov     [rsp+108h+dwErrCode], eax
0x180025974  test    eax, eax
0x180025976  jnz     loc_180025AE2
0x18002597c  mov     rax, qword ptr [rsp+108h+var_A0+8]
0x180025981  mov     r13, qword ptr [rsp+108h+var_A0]
0x180025986  sub     rax, r13
0x180025989  sar     rax, 5
0x18002598d  cmp     rax, 2
0x180025991  jb      short loc_1800259C8
0x180025993  mov     rdx, r15
0x180025996  lea     rcx, [rsp+108h+var_68]
0x18002599e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800259a3  nop
0x1800259a4  mov     r14d, 1
0x1800259aa  mov     dword ptr [rsp+108h+var_C8], r14d
0x1800259af  lea     r8, [rsp+108h+var_68]
0x1800259b7  mov     rdx, r13
0x1800259ba  call    ??RCaseInsensitive_Equal@cxl@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; cxl::CaseInsensitive_Equal::operator()(std::wstring const &,std::wstring const &)
0x1800259bf  test    al, al
0x1800259c1  jz      short loc_1800259CD
0x1800259c3  mov     sil, r14b
0x1800259c6  jmp     short loc_1800259D0
0x1800259c8  mov     r14d, dword ptr [rsp+108h+var_C8]
0x1800259cd  mov     sil, bl
0x1800259d0  test    r14b, 1
0x1800259d4  jz      short loc_1800259E3
0x1800259d6  lea     rcx, [rsp+108h+var_68]
0x1800259de  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800259e3  test    sil, sil
0x1800259e6  jz      loc_180025AE8
0x1800259ec  mov     ecx, 18h; Size
0x1800259f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800259f6  mov     rsi, rax
0x1800259f9  mov     [rax], rbx
0x1800259fc  mov     [rax+8], rbx
0x180025a00  mov     [rax+10h], rbx
0x180025a04  mov     [rdi+160h], rax
0x180025a0b  mov     dword ptr [rdi+15Ch], 1
0x180025a15  mov     r15d, 1
0x180025a1b  mov     rax, qword ptr [rsp+108h+var_A0+8]
0x180025a20  sub     rax, r13
0x180025a23  sar     rax, 5
0x180025a27  cmp     r15, rax
0x180025a2a  jnb     loc_180025AE8
0x180025a30  mov     r14, r15
0x180025a33  shl     r14, 5
0x180025a37  cmp     r15, 1
0x180025a3b  jz      short loc_180025A52
0x180025a3d  lea     rdx, [r14+r13]
0x180025a41  lea     r8, [r13+20h]
0x180025a45  call    ??RCaseInsensitive_Equal@cxl@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; cxl::CaseInsensitive_Equal::operator()(std::wstring const &,std::wstring const &)
0x180025a4a  test    al, al
0x180025a4c  jnz     loc_180025ADA
0x180025a52  lea     rcx, [r14+r13]
0x180025a56  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180025a5b  mov     rcx, [rsp+108h+var_88]
0x180025a63  mov     [rsp+108h+var_E0], rcx; struct CLUS_AUTH_INFO *
0x180025a68  mov     ecx, [rsp+108h+var_C0]
0x180025a6c  mov     [rsp+108h+var_E8], ecx; int
0x180025a70  mov     r9d, [rsp+108h+var_B8]; int
0x180025a75  xor     r8d, r8d; unsigned int *
0x180025a78  mov     edx, [rsp+108h+var_BC]; unsigned int
0x180025a7c  mov     rcx, rax; wchar_t *
0x180025a7f  call    ?OpenClusterImpl@@YAPEAU_HCLUSTER@@PEB_WKPEAKHHPEAUCLUS_AUTH_INFO@@@Z; OpenClusterImpl(wchar_t const *,ulong,ulong *,int,int,CLUS_AUTH_INFO *)
0x180025a84  test    rax, rax
0x180025a87  jnz     short loc_180025AA9
0x180025a89  cmp     r15, 1
0x180025a8d  jnz     short loc_180025ADA
0x180025a8f  call    cs:__imp_GetLastError
0x180025a95  mov     [rsp+108h+dwErrCode], eax
0x180025a99  lea     rcx, [rsp+108h+var_A0]
0x180025a9e  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180025aa3  nop
0x180025aa4  jmp     loc_180025738
0x180025aa9  mov     [rsp+108h+var_D4], bl
0x180025aad  mov     [rsp+108h+var_C8], rax
0x180025ab2  mov     rdx, [rsi+8]
0x180025ab6  lea     r9, [rsp+108h+var_D4]
0x180025abb  lea     r8, [rsp+108h+var_C8]
0x180025ac0  cmp     rdx, [rsi+10h]
0x180025ac4  jz      short loc_180025AD2
0x180025ac6  call    std___Default_allocator_traits_std__allocator_std__shared_ptr__CLUSTER_______construct_std__shared_ptr__CLUSTER___CLUSTER____lambda_67c530c70e2b457d3f7837c4dfce7e4d____
0x180025acb  add     qword ptr [rsi+8], 10h
0x180025ad0  jmp     short loc_180025ADA
0x180025ad2  mov     rcx, rsi
0x180025ad5  call    std__vector_std__shared_ptr__CLUSTER__std__allocator_std__shared_ptr__CLUSTER________Emplace_reallocate__CLUSTER____lambda_67c530c70e2b457d3f7837c4dfce7e4d____
0x180025ada  inc     r15
0x180025add  jmp     loc_180025A1B
0x180025ae2  mov     [rsp+108h+dwErrCode], ebx
0x180025ae6  jmp     short loc_180025AED
0x180025ae8  mov     r13, [rsp+108h+var_B0]
0x180025aed  mov     [rsp+108h+var_D3], bl
0x180025af1  lea     rcx, [rsp+108h+var_A0]
0x180025af6  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180025afb  nop
0x180025afc  test    r13, r13
0x180025aff  jz      short loc_180025B09
0x180025b01  mov     eax, [rsp+108h+var_D0]
0x180025b05  mov     [r13+0], eax
0x180025b09  mov     rax, rdi
0x180025b0c  jmp     loc_180025779
0x180025b11  xor     ebx, ebx
0x180025b13  mov     rdi, [rsp+108h+var_A8]
0x180025b18  cmp     [rsp+108h+var_D3], bl
0x180025b1c  jnz     short loc_180025B2E
0x180025b1e  mov     r13, [rsp+108h+var_80]
0x180025b26  jmp     short loc_180025AFC
0x180025b28  jmp     short loc_180025B11
0x180025b2a  jmp     short loc_180025B11
0x180025b2c  jmp     short loc_180025B11
0x180025b2e  lea     r12, aOpenclusterimp; "OpenClusterImpl"
0x180025b35  jmp     loc_180025738
```
