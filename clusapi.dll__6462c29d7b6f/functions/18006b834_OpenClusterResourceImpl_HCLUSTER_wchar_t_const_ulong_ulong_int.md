# OpenClusterResourceImpl(_HCLUSTER *,wchar_t const *,ulong,ulong *,int)

- ea: `0x18006b834`
- end: `0x18006ba21`
- name: `?OpenClusterResourceImpl@@YAPEAU_HRESOURCE@@PEAU_HCLUSTER@@PEB_WKPEAKH@Z`
- size: `493`
- prototype: `struct _HRESOURCE *__fastcall(struct _HCLUSTER *, const wchar_t *, unsigned int, unsigned int *, int)`
- caller_count: `11`
- callee_count: `9`
- tags: ``

## callers

- `0x180022dbc`
- `0x180039028`
- `0x18003acf0`
- `0x18003d5b8`
- `0x18003e594`
- `0x180041f00`
- `0x18006b834`
- `0x18006d3b0`
- `0x18006d3e0`
- `0x180087540`
- `0x18008cdd0`

## callees

- `0x180014638`
- `0x18001e0f8`
- `0x180024908`
- `0x18006b22c`
- `0x18006b40c`
- `0x18006b6e8`
- `0x18006b834`
- `0x18006f910`
- `0x180090a84`

## import_xrefs

- `RPCRT4!RpcSmDestroyClientContext` at `0x18006b9ac`
- `RPCRT4!RpcSmDestroyClientContext` at `0x18006b9ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b98c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b98c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b9b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006ba08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b9b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006ba08`

## string_xrefs

- `0x18006b9f1`: `OpenClusterResourceImpl`
- `0x18006b92d`: `ApiOpenResource`
- `0x18006b8e3`: `ApiOpenResourceEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _HRESOURCE *__fastcall OpenClusterResourceImpl(
        struct _HCLUSTER *a1,
        const wchar_t *a2,
        unsigned int a3,
        unsigned int *a4,
        int a5)
{
  DWORD v9; // ecx
  struct _HCLUSTER **v10; // rbx
  struct _HCLUSTER **v11; // r15
  struct _HRESOURCE *v12; // rdi
  void *v14; // rax
  unsigned int v15; // r9d
  struct _HRESOURCE *inited; // rbx
  DWORD dwErrCode; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v18; // [rsp+34h] [rbp-44h] BYREF
  void *ContextHandle; // [rsp+38h] [rbp-40h] BYREF
  const char *v20; // [rsp+40h] [rbp-38h] BYREF
  struct _HCLUSTER **v21; // [rsp+48h] [rbp-30h]
  const wchar_t *v22; // [rsp+50h] [rbp-28h]
  DWORD *p_dwErrCode; // [rsp+58h] [rbp-20h]
  unsigned int *v24; // [rsp+60h] [rbp-18h]
  DWORD *v25; // [rsp+68h] [rbp-10h]

  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           a1,
                           a1) )
  {
    v9 = 6;
LABEL_29:
    SetLastError(v9);
    return 0;
  }
  ContextHandle = 0;
  dwErrCode = 0;
  v18 = 0;
  if ( !*((_DWORD *)a1 + 87) )
  {
    if ( *((_WORD *)a1 + 162) <= 5u )
    {
      if ( !a5 )
      {
        v9 = 1745;
        dwErrCode = 1745;
        goto LABEL_26;
      }
      v20 = "ApiOpenResource";
      v21 = (struct _HCLUSTER **)((char *)a1 + 40);
      v22 = a2;
      p_dwErrCode = &dwErrCode;
      v14 = (void *)ReconnectOnNull<OpenResourceFunctor>(&v20, &dwErrCode, a1);
      v15 = 0x10000000;
      v18 = 0x10000000;
    }
    else
    {
      v20 = "ApiOpenResourceEx";
      v21 = (struct _HCLUSTER **)((char *)a1 + 40);
      v22 = a2;
      LODWORD(p_dwErrCode) = a3;
      v24 = &v18;
      v25 = &dwErrCode;
      v14 = (void *)ReconnectOnNull<OpenResourceExFunctor>(&v20, &dwErrCode, a1);
      v15 = v18;
    }
    ContextHandle = v14;
    v9 = dwErrCode;
    if ( v14 && !dwErrCode )
    {
      inited = InitClusterResource(v14, a2, a1, v15);
      if ( !inited )
      {
        dwErrCode = GetLastError();
        if ( (unsigned int)ApiCloseResource(&ContextHandle) && ContextHandle )
          RpcSmDestroyClientContext(&ContextHandle);
        SetLastError(dwErrCode);
      }
      if ( a4 )
        *a4 = v18;
      return inited;
    }
LABEL_26:
    if ( v9 == 1745 && *((_WORD *)a1 + 162) > 5u )
    {
      TraceMsg(
        2u,
        3u,
        (__int64)L"OpenClusterResourceImpl",
        450,
        L"Procnum out of range when we thought we were talking to a post-win2k8 cluster.");
      v9 = dwErrCode;
    }
    goto LABEL_29;
  }
  GetRefCountedHCLUSTER(&v20, a1);
  v10 = (struct _HCLUSTER **)v20;
  v11 = v21;
  while ( v10 != v11 )
  {
    v12 = OpenClusterResourceImpl(*v10, a2, a3, a4, a5);
    if ( v12 )
      goto LABEL_10;
    ++v10;
  }
  v12 = 0;
LABEL_10:
  std::pair<std::vector<_HCLUSTER *>,std::vector<std::shared_ptr<_CLUSTER>>>::~pair<std::vector<_HCLUSTER *>,std::vector<std::shared_ptr<_CLUSTER>>>(&v20);
  return v12;
}

```

## disassembly

```asm
0x18006b834  push    rbp
0x18006b836  push    rbx
0x18006b837  push    rsi
0x18006b838  push    rdi
0x18006b839  push    r12
0x18006b83b  push    r13
0x18006b83d  push    r14
0x18006b83f  push    r15
0x18006b841  mov     rbp, rsp
0x18006b844  sub     rsp, 78h
0x18006b848  mov     rsi, r9
0x18006b84b  mov     r13d, r8d
0x18006b84e  mov     r14, rdx
0x18006b851  mov     rbx, rcx
0x18006b854  mov     rdx, rcx
0x18006b857  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x18006b85c  xor     edi, edi
0x18006b85e  test    al, al
0x18006b860  jnz     short loc_18006B86A
0x18006b862  lea     ecx, [rdi+6]
0x18006b865  jmp     loc_18006BA08
0x18006b86a  mov     [rbp+ContextHandle], rdi
0x18006b86e  mov     [rbp+dwErrCode], edi
0x18006b871  mov     [rbp+var_44], edi
0x18006b874  cmp     [rbx+15Ch], edi
0x18006b87a  jz      short loc_18006B8D3
0x18006b87c  mov     rdx, rbx
0x18006b87f  lea     rcx, [rbp+var_38]
0x18006b883  call    ?GetRefCountedHCLUSTER@@YA?AU?$pair@V?$vector@PEAU_HCLUSTER@@V?$allocator@PEAU_HCLUSTER@@@std@@@std@@V?$vector@V?$shared_ptr@U_CLUSTER@@@std@@V?$allocator@V?$shared_ptr@U_CLUSTER@@@std@@@2@@2@@std@@PEAU_CLUSTER@@@Z; GetRefCountedHCLUSTER(_CLUSTER *)
0x18006b888  nop
0x18006b889  mov     rbx, [rbp+var_38]
0x18006b88d  mov     r15, [rbp+var_30]
0x18006b891  mov     r12d, [rbp+arg_20]
0x18006b895  cmp     rbx, r15
0x18006b898  jz      short loc_18006B8C0
0x18006b89a  mov     [rsp+78h+var_58], r12d; int
0x18006b89f  mov     r9, rsi; unsigned int *
0x18006b8a2  mov     r8d, r13d; unsigned int
0x18006b8a5  mov     rdx, r14; wchar_t *
0x18006b8a8  mov     rcx, [rbx]; struct _HCLUSTER *
0x18006b8ab  call    ?OpenClusterResourceImpl@@YAPEAU_HRESOURCE@@PEAU_HCLUSTER@@PEB_WKPEAKH@Z; OpenClusterResourceImpl(_HCLUSTER *,wchar_t const *,ulong,ulong *,int)
0x18006b8b0  mov     rdi, rax
0x18006b8b3  test    rax, rax
0x18006b8b6  jnz     short loc_18006B8BE
0x18006b8b8  add     rbx, 8
0x18006b8bc  jmp     short loc_18006B895
0x18006b8be  jmp     short loc_18006B8C2
0x18006b8c0  xor     edi, edi
0x18006b8c2  lea     rcx, [rbp+var_38]
0x18006b8c6  call    ??1?$pair@V?$vector@PEAU_HCLUSTER@@V?$allocator@PEAU_HCLUSTER@@@std@@@std@@V?$vector@V?$shared_ptr@U_CLUSTER@@@std@@V?$allocator@V?$shared_ptr@U_CLUSTER@@@std@@@2@@2@@std@@QEAA@XZ; std::pair<std::vector<_HCLUSTER *>,std::vector<std::shared_ptr<_CLUSTER>>>::~pair<std::vector<_HCLUSTER *>,std::vector<std::shared_ptr<_CLUSTER>>>(void)
0x18006b8cb  mov     rax, rdi
0x18006b8ce  jmp     loc_18006BA10
0x18006b8d3  mov     r15d, 6D1h
0x18006b8d9  cmp     word ptr [rbx+144h], 5
0x18006b8e1  jbe     short loc_18006B924
0x18006b8e3  lea     rax, aApiopenresourc_0; "ApiOpenResourceEx"
0x18006b8ea  mov     [rbp+var_38], rax
0x18006b8ee  lea     rax, [rbx+28h]
0x18006b8f2  mov     [rbp+var_30], rax
0x18006b8f6  mov     [rbp+var_28], r14
0x18006b8fa  mov     dword ptr [rbp+var_20], r13d
0x18006b8fe  lea     rax, [rbp+var_44]
0x18006b902  mov     [rbp+var_18], rax
0x18006b906  lea     rax, [rbp+dwErrCode]
0x18006b90a  mov     [rbp+var_10], rax
0x18006b90e  mov     r8, rbx
0x18006b911  lea     rdx, [rbp+dwErrCode]
0x18006b915  lea     rcx, [rbp+var_38]
0x18006b919  call    ??$ReconnectOnNull@VOpenResourceExFunctor@@@@YAPEAXAEBVOpenResourceExFunctor@@PEAKPEAU_CLUSTER@@@Z; ReconnectOnNull<OpenResourceExFunctor>(OpenResourceExFunctor const &,ulong *,_CLUSTER *)
0x18006b91e  mov     r9d, [rbp+var_44]
0x18006b922  jmp     short loc_18006B966
0x18006b924  cmp     [rbp+arg_20], edi
0x18006b927  jz      loc_18006B9CA
0x18006b92d  lea     rax, aApiopenresourc; "ApiOpenResource"
0x18006b934  mov     [rbp+var_38], rax
0x18006b938  lea     rax, [rbx+28h]
0x18006b93c  mov     [rbp+var_30], rax
0x18006b940  mov     [rbp+var_28], r14
0x18006b944  lea     rax, [rbp+dwErrCode]
0x18006b948  mov     [rbp+var_20], rax
0x18006b94c  mov     r8, rbx
0x18006b94f  lea     rdx, [rbp+dwErrCode]
0x18006b953  lea     rcx, [rbp+var_38]
0x18006b957  call    ??$ReconnectOnNull@VOpenResourceFunctor@@@@YAPEAXAEBVOpenResourceFunctor@@PEAKPEAU_CLUSTER@@@Z; ReconnectOnNull<OpenResourceFunctor>(OpenResourceFunctor const &,ulong *,_CLUSTER *)
0x18006b95c  mov     r9d, 10000000h; unsigned int
0x18006b962  mov     [rbp+var_44], r9d
0x18006b966  mov     [rbp+ContextHandle], rax
0x18006b96a  mov     ecx, [rbp+dwErrCode]
0x18006b96d  test    rax, rax
0x18006b970  jz      short loc_18006B9D0
0x18006b972  test    ecx, ecx
0x18006b974  jnz     short loc_18006B9D0
0x18006b976  mov     r8, rbx; struct _CLUSTER *
0x18006b979  mov     rdx, r14; wchar_t *
0x18006b97c  mov     rcx, rax; void *
0x18006b97f  call    ?InitClusterResource@@YAPEAU_HRESOURCE@@PEAXPEB_WPEAU_CLUSTER@@K@Z; InitClusterResource(void *,wchar_t const *,_CLUSTER *,ulong)
0x18006b984  mov     rbx, rax
0x18006b987  test    rax, rax
0x18006b98a  jnz     short loc_18006B9BB
0x18006b98c  call    cs:__imp_GetLastError
0x18006b992  mov     [rbp+dwErrCode], eax
0x18006b995  lea     rcx, [rbp+ContextHandle]
0x18006b999  call    ApiCloseResource
0x18006b99e  test    eax, eax
0x18006b9a0  jz      short loc_18006B9B2
0x18006b9a2  cmp     [rbp+ContextHandle], rdi
0x18006b9a6  jz      short loc_18006B9B2
0x18006b9a8  lea     rcx, [rbp+ContextHandle]; ContextHandle
0x18006b9ac  call    cs:__imp_RpcSmDestroyClientContext
0x18006b9b2  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x18006b9b5  call    cs:__imp_SetLastError
0x18006b9bb  test    rsi, rsi
0x18006b9be  jz      short loc_18006B9C5
0x18006b9c0  mov     eax, [rbp+var_44]
0x18006b9c3  mov     [rsi], eax
0x18006b9c5  mov     rax, rbx
0x18006b9c8  jmp     short loc_18006BA10
0x18006b9ca  mov     ecx, r15d
0x18006b9cd  mov     [rbp+dwErrCode], ecx
0x18006b9d0  cmp     ecx, r15d
0x18006b9d3  jnz     short loc_18006BA08
0x18006b9d5  cmp     word ptr [rbx+144h], 5
0x18006b9dd  jbe     short loc_18006BA08
0x18006b9df  lea     rax, aProcnumOutOfRa; "Procnum out of range when we thought we"...
0x18006b9e6  mov     qword ptr [rsp+78h+var_58], rax
0x18006b9eb  mov     r9d, 1C2h
0x18006b9f1  lea     r8, aOpenclusterres_2; "OpenClusterResourceImpl"
0x18006b9f8  mov     edx, 3
0x18006b9fd  lea     ecx, [rdx-1]
0x18006ba00  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18006ba05  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x18006ba08  call    cs:__imp_SetLastError
0x18006ba0e  xor     eax, eax
0x18006ba10  add     rsp, 78h
0x18006ba14  pop     r15
0x18006ba16  pop     r14
0x18006ba18  pop     r13
0x18006ba1a  pop     r12
0x18006ba1c  pop     rdi
0x18006ba1d  pop     rsi
0x18006ba1e  pop     rbx
0x18006ba1f  pop     rbp
0x18006ba20  retn
```
