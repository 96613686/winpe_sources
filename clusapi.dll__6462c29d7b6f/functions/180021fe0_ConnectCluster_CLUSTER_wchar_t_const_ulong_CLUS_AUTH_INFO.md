# ConnectCluster(_CLUSTER *,wchar_t const *,ulong,CLUS_AUTH_INFO *)

- ea: `0x180021fe0`
- end: `0x180022225`
- name: `?ConnectCluster@@YAKPEAU_CLUSTER@@PEB_WKPEAUCLUS_AUTH_INFO@@@Z`
- size: `581`
- prototype: `unsigned int __fastcall(struct _CLUSTER *, const wchar_t *, unsigned int, struct CLUS_AUTH_INFO *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180025650`

## callees

- `0x180021fe0`
- `0x180022508`
- `0x180023550`
- `0x180024288`
- `0x1800254d8`
- `0x18006f910`
- `0x180090b7c`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x1800221ee`
- `RPCRT4!RpcBindingFree` at `0x1800221ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022201`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022210`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022201`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022210`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002201b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002201b`

## string_xrefs

- `0x18002205a`: `CreateRPCAuthInfoFromClusterAuthInfo returned credentials? '%ws'`
- `0x1800221c9`: `Failed to open local cluster, status == %u.`
- `0x1800220f0`: `Failed to open remote cluster '%ws', status == %u.`

## pseudocode

```c
__int64 __fastcall ConnectCluster(
        struct _CLUSTER *a1,
        const wchar_t *a2,
        struct _SEC_WINNT_AUTH_IDENTITY_W *a3,
        struct CLUS_AUTH_INFO *a4)
{
  struct _SEC_WINNT_AUTH_IDENTITY_W *v7; // rax
  unsigned int RPCAuthInfoFromClusterAuthInfo; // eax
  const wchar_t *v9; // rdx
  unsigned int v10; // ebx
  unsigned int v11; // eax
  RPC_BINDING_HANDLE v12; // rcx
  unsigned int ClusterNameWrapper; // eax
  unsigned int v14; // eax
  RPC_BINDING_HANDLE v15; // rcx
  unsigned int ClusterName; // eax
  HLOCAL v17; // rdx
  HLOCAL v18; // rax
  __int64 v20; // [rsp+28h] [rbp-30h]
  unsigned int v21; // [rsp+30h] [rbp-28h]
  unsigned int v22; // [rsp+30h] [rbp-28h]
  HLOCAL hMem; // [rsp+40h] [rbp-18h] BYREF
  HLOCAL v24[2]; // [rsp+48h] [rbp-10h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+A8h] [rbp+50h] BYREF

  Binding = 0;
  hMem = 0;
  v24[0] = 0;
  if ( !a4 )
    goto LABEL_28;
  v7 = (struct _SEC_WINNT_AUTH_IDENTITY_W *)LocalAlloc(0x40u, 0x30u);
  *((_QWORD *)a1 + 45) = v7;
  RPCAuthInfoFromClusterAuthInfo = CreateRPCAuthInfoFromClusterAuthInfo(v7, a4);
  v9 = L"Yes";
  v10 = RPCAuthInfoFromClusterAuthInfo;
  if ( !**((_QWORD **)a1 + 45) )
    v9 = L"No";
  TraceMsg(
    4u,
    0,
    (__int64)L"ConnectCluster",
    1588,
    L"CreateRPCAuthInfoFromClusterAuthInfo returned credentials? '%ws'",
    v9);
  if ( !v10 )
  {
LABEL_28:
    if ( a2 && *a2 )
    {
      *((_DWORD *)a1 + 8) = 0;
      v11 = ConnectRemoteClusterParallel(a2, 6u, &Binding, a1);
      v10 = v11;
      if ( v11 )
      {
        v22 = v11;
        TraceMsg(
          2u,
          0,
          (__int64)L"ConnectCluster",
          1638,
          L"Failed to open remote cluster '%ws', status == %u.",
          a2,
          v22);
        goto LABEL_19;
      }
      v12 = Binding;
      *((_DWORD *)a1 + 54) = 6;
      ClusterNameWrapper = GetClusterNameWrapper(v12, (wchar_t **)&hMem, (wchar_t **)v24);
      v10 = ClusterNameWrapper;
      if ( ClusterNameWrapper )
      {
        v21 = ClusterNameWrapper;
        TraceMsg(
          2u,
          0,
          (__int64)L"ConnectCluster",
          1635,
          L"Connect %ws: GetClusterNameWrapper failed, sc = %u.",
          a2,
          v21);
LABEL_19:
        if ( Binding )
        {
          RpcBindingFree(&Binding);
          *((_QWORD *)a1 + 5) = 0;
        }
        if ( hMem )
          LocalFree(hMem);
        if ( v24[0] )
          LocalFree(v24[0]);
        return v10;
      }
    }
    else
    {
      v14 = ObtainLRPCBindingHandle(&Binding, (__int64)a2, a3);
      v10 = v14;
      if ( v14 )
      {
        LODWORD(v20) = v14;
        TraceMsg(4u, 0, (__int64)L"ConnectCluster", 1620, L"Failed to open local cluster, status == %u.", v20);
        goto LABEL_19;
      }
      v15 = Binding;
      *((_QWORD *)a1 + 5) = Binding;
      *((_DWORD *)a1 + 54) = 6;
      *((_DWORD *)a1 + 8) = 4;
      ClusterName = ApiGetClusterName(v15, &hMem, v24);
      v10 = ClusterName;
      if ( ClusterName )
      {
        LODWORD(v20) = ClusterName;
        TraceMsg(
          2u,
          0,
          (__int64)L"ConnectCluster",
          1617,
          L"Connect to Local Cluster: ApiGetClusterName failed, sc = %u.",
          v20);
        goto LABEL_19;
      }
    }
    v17 = hMem;
    *((_QWORD *)a1 + 5) = Binding;
    v18 = v24[0];
    *((HLOCAL *)a1 + 3) = v24[0];
    *((_QWORD *)a1 + 2) = v17;
    if ( v17 && v18 )
      TraceMsg(4u, 0, (__int64)L"ConnectCluster", 1648, L"Connected to ClusterName %ws, nodeName %ws", v17, v18);
  }
  return v10;
}

```

## disassembly

```asm
0x180021fe0  push    rbp
0x180021fe2  push    rbx
0x180021fe3  push    rsi
0x180021fe4  push    rdi
0x180021fe5  push    r14
0x180021fe7  push    r15
0x180021fe9  mov     rbp, rsp
0x180021fec  sub     rsp, 58h
0x180021ff0  xor     r14d, r14d
0x180021ff3  lea     r15, aConnectcluster; "ConnectCluster"
0x180021ffa  mov     [rbp+Binding], r14
0x180021ffe  mov     rbx, r9
0x180022001  mov     [rbp+hMem], r14
0x180022005  mov     rsi, rdx
0x180022008  mov     [rbp+var_10], r14
0x18002200c  mov     rdi, rcx
0x18002200f  test    r9, r9
0x180022012  jz      short loc_18002207D
0x180022014  lea     edx, [r14+30h]; uBytes
0x180022018  lea     ecx, [rdx+10h]; uFlags
0x18002201b  call    cs:__imp_LocalAlloc
0x180022021  mov     rcx, rax; struct _SEC_WINNT_AUTH_IDENTITY_W *
0x180022024  mov     [rdi+168h], rax
0x18002202b  mov     rdx, rbx; struct CLUS_AUTH_INFO *
0x18002202e  call    ?CreateRPCAuthInfoFromClusterAuthInfo@@YAJPEAU_SEC_WINNT_AUTH_IDENTITY_W@@PEAUCLUS_AUTH_INFO@@@Z; CreateRPCAuthInfoFromClusterAuthInfo(_SEC_WINNT_AUTH_IDENTITY_W *,CLUS_AUTH_INFO *)
0x180022033  mov     rcx, [rdi+168h]
0x18002203a  lea     rdx, aYes; "Yes"
0x180022041  mov     ebx, eax
0x180022043  mov     r9d, 634h
0x180022049  lea     rax, aNo; "No"
0x180022050  mov     r8, r15
0x180022053  cmp     [rcx], r14
0x180022056  cmovz   rdx, rax
0x18002205a  lea     rax, aCreaterpcauthi; "CreateRPCAuthInfoFromClusterAuthInfo re"...
0x180022061  mov     [rsp+58h+var_30], rdx
0x180022066  xor     edx, edx
0x180022068  mov     [rsp+58h+var_38], rax
0x18002206d  lea     ecx, [rdx+4]
0x180022070  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180022075  test    ebx, ebx
0x180022077  jnz     loc_180022216
0x18002207d  test    rsi, rsi
0x180022080  jz      loc_180022113
0x180022086  cmp     [rsi], r14w
0x18002208a  jz      loc_180022113
0x180022090  mov     r9, rdi; struct _CLUSTER *
0x180022093  mov     [rdi+20h], r14d
0x180022097  lea     r8, [rbp+Binding]; void **
0x18002209b  mov     edx, 6; unsigned int
0x1800220a0  mov     rcx, rsi; wchar_t *
0x1800220a3  call    ?ConnectRemoteClusterParallel@@YAKPEB_WKAEAPEAXPEAU_CLUSTER@@@Z; ConnectRemoteClusterParallel(wchar_t const *,ulong,void * &,_CLUSTER *)
0x1800220a8  mov     ebx, eax
0x1800220aa  test    eax, eax
0x1800220ac  jnz     short loc_1800220E6
0x1800220ae  mov     rcx, [rbp+Binding]; Binding
0x1800220b2  lea     r8, [rbp+var_10]; wchar_t **
0x1800220b6  lea     rdx, [rbp+hMem]; wchar_t **
0x1800220ba  mov     dword ptr [rdi+0D8h], 6
0x1800220c4  call    ?GetClusterNameWrapper@@YAKPEAXPEAPEA_W1@Z; GetClusterNameWrapper(void *,wchar_t * *,wchar_t * *)
0x1800220c9  mov     ebx, eax
0x1800220cb  test    eax, eax
0x1800220cd  jz      loc_18002216A
0x1800220d3  mov     [rsp+58h+var_28], eax
0x1800220d7  mov     r9d, 663h
0x1800220dd  lea     rax, aConnectWsGetcl; "Connect %ws: GetClusterNameWrapper fail"...
0x1800220e4  jmp     short loc_1800220F7
0x1800220e6  mov     [rsp+58h+var_28], eax
0x1800220ea  mov     r9d, 666h
0x1800220f0  lea     rax, aFailedToOpenRe_1; "Failed to open remote cluster '%ws', st"...
0x1800220f7  xor     edx, edx
0x1800220f9  mov     [rsp+58h+var_30], rsi
0x1800220fe  mov     r8, r15
0x180022101  mov     [rsp+58h+var_38], rax
0x180022106  lea     ecx, [rdx+2]
0x180022109  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18002210e  jmp     loc_1800221E4
0x180022113  lea     rcx, [rbp+Binding]; Binding
0x180022117  call    ?ObtainLRPCBindingHandle@@YAKPEAPEAXKPEAU_SEC_WINNT_AUTH_IDENTITY_W@@@Z; ObtainLRPCBindingHandle(void * *,ulong,_SEC_WINNT_AUTH_IDENTITY_W *)
0x18002211c  mov     ebx, eax
0x18002211e  test    eax, eax
0x180022120  jnz     loc_1800221BF
0x180022126  mov     rcx, [rbp+Binding]
0x18002212a  lea     r8, [rbp+var_10]
0x18002212e  lea     rdx, [rbp+hMem]
0x180022132  mov     [rdi+28h], rcx
0x180022136  mov     dword ptr [rdi+0D8h], 6
0x180022140  mov     dword ptr [rdi+20h], 4
0x180022147  call    ApiGetClusterName
0x18002214c  mov     ebx, eax
0x18002214e  test    eax, eax
0x180022150  jz      short loc_18002216A
0x180022152  mov     dword ptr [rsp+58h+var_30], eax
0x180022156  mov     r9d, 651h
0x18002215c  lea     rax, aConnectToLocal; "Connect to Local Cluster: ApiGetCluster"...
0x180022163  mov     ecx, 2
0x180022168  jmp     short loc_1800221D5
0x18002216a  mov     rax, [rbp+Binding]
0x18002216e  mov     rdx, [rbp+hMem]
0x180022172  mov     [rdi+28h], rax
0x180022176  mov     rax, [rbp+var_10]
0x18002217a  mov     [rdi+18h], rax
0x18002217e  mov     [rdi+10h], rdx
0x180022182  test    rdx, rdx
0x180022185  jz      loc_180022216
0x18002218b  test    rax, rax
0x18002218e  jz      loc_180022216
0x180022194  mov     qword ptr [rsp+58h+var_28], rax
0x180022199  mov     r9d, 670h
0x18002219f  mov     [rsp+58h+var_30], rdx
0x1800221a4  lea     rax, aConnectedToClu; "Connected to ClusterName %ws, nodeName "...
0x1800221ab  xor     edx, edx
0x1800221ad  mov     [rsp+58h+var_38], rax
0x1800221b2  mov     r8, r15
0x1800221b5  lea     ecx, [rdx+4]
0x1800221b8  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800221bd  jmp     short loc_180022216
0x1800221bf  mov     dword ptr [rsp+58h+var_30], eax
0x1800221c3  mov     r9d, 654h
0x1800221c9  lea     rax, aFailedToOpenLo; "Failed to open local cluster, status =="...
0x1800221d0  mov     ecx, 4
0x1800221d5  mov     r8, r15
0x1800221d8  mov     [rsp+58h+var_38], rax
0x1800221dd  xor     edx, edx
0x1800221df  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800221e4  cmp     [rbp+Binding], r14
0x1800221e8  jz      short loc_1800221F8
0x1800221ea  lea     rcx, [rbp+Binding]; Binding
0x1800221ee  call    cs:__imp_RpcBindingFree
0x1800221f4  mov     [rdi+28h], r14
0x1800221f8  mov     rcx, [rbp+hMem]; hMem
0x1800221fc  test    rcx, rcx
0x1800221ff  jz      short loc_180022207
0x180022201  call    cs:__imp_LocalFree
0x180022207  mov     rcx, [rbp+var_10]; hMem
0x18002220b  test    rcx, rcx
0x18002220e  jz      short loc_180022216
0x180022210  call    cs:__imp_LocalFree
0x180022216  mov     eax, ebx
0x180022218  add     rsp, 58h
0x18002221c  pop     r15
0x18002221e  pop     r14
0x180022220  pop     rdi
0x180022221  pop     rsi
0x180022222  pop     rbx
0x180022223  pop     rbp
0x180022224  retn
```
