# ABBind_local

- ea: `0x1803823d4`
- end: `0x180382d57`
- name: `ABBind_local`
- size: `2435`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180389390`

## callees

- `0x180006360`
- `0x18001e090`
- `0x18001ea60`
- `0x180123a30`
- `0x18013f698`
- `0x180180c50`
- `0x180181ae0`
- `0x180181bf0`
- `0x1801822d0`
- `0x1803823d4`
- `0x180382d60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180382d16`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180382d16`
- `RPCRT4!RpcBindingServerFromClient` at `0x18038244b`
- `RPCRT4!RpcBindingServerFromClient` at `0x18038244b`
- `RPCRT4!RpcBindingFree` at `0x180382528`
- `RPCRT4!RpcBindingFree` at `0x180382528`
- `RPCRT4!RpcBindingToStringBindingA` at `0x180382461`
- `RPCRT4!RpcBindingToStringBindingA` at `0x180382461`
- `RPCRT4!RpcStringFreeA` at `0x180382d08`
- `RPCRT4!RpcStringFreeA` at `0x180382d08`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180382642`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180382642`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180382d25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180382d25`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x180382532`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x180382532`
- `ntdll!RtlCopySid` at `0x180382953`
- `ntdll!RtlCopySid` at `0x180382953`
- `ADVAPI32!ConvertSidToStringSidA` at `0x180382655`
- `ADVAPI32!ConvertSidToStringSidA` at `0x180382655`

## pseudocode

```c
__int64 __fastcall ABBind_local(__int64 a1, void *a2, char a3, __int64 a4, _OWORD *a5, unsigned int **a6)
{
  LPOVERLAPPED v6; // rbx
  void *v9; // rsi
  unsigned int *v10; // r14
  int Internal; // eax
  int v12; // edi
  LPOVERLAPPED v13; // rbx
  int v14; // eax
  int v15; // edi
  void *CurrentUserSid; // rax
  int v17; // eax
  LPOVERLAPPED v18; // rbx
  unsigned int *v19; // rax
  unsigned int v20; // r12d
  __int64 *v21; // r8
  int v22; // eax
  int v23; // eax
  int v24; // eax
  LPSTR v25; // r8
  RPC_CSTR v26; // rdx
  bool v27; // zf
  __int64 v28; // rdx
  unsigned int v29; // eax
  int v31; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v32[3]; // [rsp+24h] [rbp-DCh] BYREF
  __int64 v33; // [rsp+30h] [rbp-D0h] BYREF
  int v34; // [rsp+38h] [rbp-C8h]
  int v35; // [rsp+3Ch] [rbp-C4h]
  __int64 v36; // [rsp+40h] [rbp-C0h]
  int v37; // [rsp+48h] [rbp-B8h]
  int v38; // [rsp+4Ch] [rbp-B4h]
  __int64 v39; // [rsp+50h] [rbp-B0h]
  __int64 v40; // [rsp+58h] [rbp-A8h]
  __int64 v41; // [rsp+60h] [rbp-A0h]
  __int64 v42; // [rsp+68h] [rbp-98h]
  __int64 v43; // [rsp+70h] [rbp-90h]
  int v44; // [rsp+78h] [rbp-88h]
  __int64 v45; // [rsp+7Ch] [rbp-84h]
  int v46; // [rsp+84h] [rbp-7Ch]
  _DWORD *v47; // [rsp+88h] [rbp-78h]
  unsigned int v48; // [rsp+90h] [rbp-70h]
  BOOL v49; // [rsp+94h] [rbp-6Ch]
  RPC_CSTR StringBinding; // [rsp+98h] [rbp-68h] BYREF
  LPSTR StringSid; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-50h] BYREF
  int v53; // [rsp+B8h] [rbp-48h]
  int v54; // [rsp+BCh] [rbp-44h]
  __int64 v55; // [rsp+C0h] [rbp-40h]
  int v56; // [rsp+C8h] [rbp-38h]
  int v57; // [rsp+CCh] [rbp-34h]
  __int64 v58; // [rsp+D0h] [rbp-30h]
  __int64 v59; // [rsp+D8h] [rbp-28h]
  __int64 v60; // [rsp+E0h] [rbp-20h]
  int v61; // [rsp+E8h] [rbp-18h]
  __int64 v62; // [rsp+F0h] [rbp-10h]
  int v63; // [rsp+F8h] [rbp-8h]
  __int64 (__fastcall *v64)(int, int, int, int, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64); // [rsp+100h] [rbp+0h]
  _DWORD *v65; // [rsp+108h] [rbp+8h]
  RPC_BINDING_HANDLE ServerBinding; // [rsp+110h] [rbp+10h] BYREF
  __int64 v67; // [rsp+118h] [rbp+18h]
  _DWORD v68[2]; // [rsp+120h] [rbp+20h] BYREF
  const char *v69; // [rsp+128h] [rbp+28h]
  __int64 v70; // [rsp+138h] [rbp+38h] BYREF

  LODWORD(v6) = 0;
  v67 = a1;
  StringBinding = 0;
  *a6 = 0;
  v48 = -1;
  v9 = 0;
  ServerBinding = 0;
  v10 = 0;
  StringSid = 0;
  v49 = 0;
  v32[0] = 0;
  if ( !RpcBindingServerFromClient(a2, &ServerBinding) )
  {
    if ( RpcBindingToStringBindingA(ServerBinding, &StringBinding) )
      goto LABEL_10;
    v6 = gpDsEventConfig;
    if ( !gpDsEventConfig )
      goto LABEL_10;
    if ( SHIDWORD(gpDsEventConfig[2].Internal) < 4
      && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(1028, 4)) )
    {
      LODWORD(v6) = 0;
      if ( !(unsigned int)DoLogMsgOverride(1073742996) )
      {
LABEL_10:
        RpcBindingFree(&ServerBinding);
        goto LABEL_11;
      }
      v6 = gpDsEventConfig;
    }
    v36 = 4;
    v42 = 0;
    v45 = 0;
    v46 = 0;
    Internal = v6[2].Internal;
    LODWORD(v6) = 0;
    v35 = Internal;
    v47 = v68;
    v34 = 1073742996;
    v38 = 1;
    v33 = 1;
    v39 = 1;
    v37 = 0;
    v68[0] = 0;
    v69 = (const char *)StringBinding;
    v41 = 0;
    v40 = 1028;
    v43 = 0;
    v44 = 0;
    DoLogEventAndTrace(&v33);
    goto LABEL_10;
  }
LABEL_11:
  if ( !IsValidCodePage(*(_DWORD *)(a4 + 24)) || *(_DWORD *)(a4 + 24) == 1200 )
  {
    v13 = gpDsEventConfig;
    if ( gpDsEventConfig )
    {
      if ( SHIDWORD(gpDsEventConfig[2].Internal) >= 1
        || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(1028, 1)
        || (v23 = DoLogMsgOverride(2147484827LL), v13 = gpDsEventConfig, v23) )
      {
        v36 = 1;
        v42 = 0;
        v45 = 0;
        v46 = 0;
        v35 = v13[2].Internal;
        v47 = v68;
        v70 = *(unsigned int *)(a4 + 24);
        v69 = (const char *)&v70;
        v34 = -2147482469;
        v37 = 0;
        v38 = 1;
        v68[0] = 5;
        v33 = 1;
        v41 = 0;
        v40 = 1028;
        v39 = 1;
        v43 = 0;
        v44 = 0;
        DoLogEventAndTrace(&v33);
        v13 = gpDsEventConfig;
      }
    }
    v15 = -2147221218;
    goto LABEL_57;
  }
  v12 = a3 & 0x20;
  if ( !v12 || gbAllowAnonymousNspi == (_DWORD)v6 )
  {
    if ( (unsigned int)VerifyRpcClientIsAuthenticatedUser(0)
      || (CurrentUserSid = GetCurrentUserSid(), (v9 = CurrentUserSid) == 0) )
    {
      v13 = gpDsEventConfig;
      if ( !gpDsEventConfig )
        goto LABEL_23;
      if ( SHIDWORD(gpDsEventConfig[1].Internal) < 4
        && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(1028, 4)) )
      {
        v14 = DoLogMsgOverride(1073743000);
        v13 = gpDsEventConfig;
        if ( !v14 )
          goto LABEL_23;
      }
      v36 = 4;
      v42 = 0;
      v45 = 0;
      v46 = 0;
      v35 = v13[1].Internal;
      v47 = v68;
      v33 = 0;
      v38 = 1;
      v37 = 0;
      v34 = 1073743000;
      v39 = 1;
      goto LABEL_22;
    }
    LODWORD(v6) = GetLengthSid(CurrentUserSid);
    if ( !v12 )
      v49 = ConvertSidToStringSidA(v9, &StringSid);
  }
  v31 = dword_180527F80;
  v15 = 0;
  if ( (unsigned int)CheckForNSPIMaxConnLimit(v9) )
  {
    v13 = gpDsEventConfig;
    if ( !gpDsEventConfig )
      goto LABEL_23;
    if ( SHIDWORD(gpDsEventConfig[2].Internal) < 4
      && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(1028, 4)) )
    {
      v17 = DoLogMsgOverride(1073744643);
      v13 = gpDsEventConfig;
      if ( !v17 )
        goto LABEL_23;
    }
    v36 = 4;
    v42 = 0;
    v45 = 0;
    v46 = 0;
    v35 = v13[2].Internal;
    v47 = v68;
    v33 = 0;
    v34 = 1073744643;
    v37 = 0;
    v38 = 1;
    if ( StringSid )
    {
      v68[0] = 0;
      v69 = StringSid;
      v33 = 1;
    }
    v39 = 1;
LABEL_22:
    v40 = 1028;
    v41 = 0;
    v43 = 0;
    v44 = 0;
    DoLogEventAndTrace(&v33);
    v13 = gpDsEventConfig;
LABEL_23:
    v15 = -2147221231;
LABEL_57:
    v20 = -1;
    goto LABEL_58;
  }
  v31 = 0;
  v32[0] = 0;
  HTGetGALAndTemplateDNT(v9, (unsigned int)v6, &v31, v32);
  v18 = gpDsEventConfig;
  v48 = v32[0];
  if ( gpDsEventConfig )
  {
    if ( SHIDWORD(gpDsEventConfig[2].Internal) < 5
      && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(1028, 5)) )
    {
      if ( !(unsigned int)DoLogMsgOverride(1073742962) )
        goto LABEL_43;
      v18 = gpDsEventConfig;
    }
    v36 = 5;
    v42 = 0;
    v45 = 0;
    v46 = 0;
    v35 = v18[2].Internal;
    v47 = v68;
    v69 = "NspiBind";
    v34 = 1073742962;
    v37 = 0;
    v38 = 1;
    v68[0] = 0;
    v33 = 1;
    v41 = 0;
    v40 = 1028;
    v39 = 1;
    v43 = 0;
    v44 = 0;
    DoLogEventAndTrace(&v33);
  }
LABEL_43:
  v19 = (unsigned int *)DSAllocAux(152, 67371481);
  v10 = v19;
  if ( v19 )
  {
    memset_0(v19, 0, 0x98u);
    v21 = gNSPIAnonymousSID;
    v10[2] = BindNumber;
    v22 = BindNumber + 1;
    *a6 = v10;
    v20 = v31;
    BindNumber = v22;
    if ( v9 )
      v21 = (__int64 *)v9;
    v10[1] = v48;
    *v10 = v20;
    *((_QWORD *)v10 + 9) = StringBinding;
    RtlCopySid(0x44u, v10 + 20, v21);
    v13 = gpDsEventConfig;
    if ( a5 )
      *a5 = *(_OWORD *)(v67 + 5976);
  }
  else
  {
    v13 = gpDsEventConfig;
    v15 = -2147221231;
    v20 = v31;
  }
LABEL_58:
  if ( !v13 )
    goto LABEL_78;
  if ( !LODWORD(v13->Internal)
    && SHIDWORD(v13[4].Internal) < 4
    && (!HIDWORD(v13->Internal) || !(unsigned int)DoLogOverride(1028, 4)) )
  {
    if ( !(unsigned int)DoLogMsgOverride(1073743936) )
      goto LABEL_78;
    v13 = gpDsEventConfig;
  }
  memset_0(&v52, 0, 0x60u);
  v54 = v13[4].Internal;
  v56 = v13->Internal;
  v64 = DsTraceEvent;
  v55 = 4;
  v53 = 1073743936;
  v61 = 38;
  if ( SHIDWORD(v13[4].Internal) >= 4
    || HIDWORD(v13->Internal) && (unsigned int)DoLogOverride(1028, 4)
    || (v24 = DoLogMsgOverride(1073743936), v57 = 0, v24) )
  {
    v57 = 1;
  }
  v65 = v68;
  v25 = (LPSTR)"NULL";
  v68[8 * v52] = 5;
  *(_QWORD *)&v65[8 * v52 + 6] = v15;
  *(_QWORD *)&v65[8 * v52 + 2] = &v65[8 * v52 + 6];
  v26 = (RPC_CSTR)"NULL";
  ++v52;
  v65[8 * v52] = 0;
  if ( StringBinding )
    v26 = StringBinding;
  *(_QWORD *)&v65[8 * v52++ + 2] = v26;
  v65[8 * v52] = 5;
  *(_QWORD *)&v65[8 * v52 + 6] = *(unsigned int *)(a4 + 24);
  *(_QWORD *)&v65[8 * v52 + 2] = &v65[8 * v52 + 6];
  ++v52;
  v27 = !v49;
  v65[8 * v52] = 0;
  if ( !v27 )
    v25 = StringSid;
  *(_QWORD *)&v65[8 * v52++ + 2] = v25;
  v65[8 * v52] = 5;
  *(_QWORD *)&v65[8 * v52 + 6] = v20;
  *(_QWORD *)&v65[8 * v52 + 2] = &v65[8 * v52 + 6];
  ++v52;
  v28 = v48;
  v65[8 * v52] = 5;
  *(_QWORD *)&v65[8 * v52 + 6] = v28;
  *(_QWORD *)&v65[8 * v52 + 2] = &v65[8 * v52 + 6];
  ++v52;
  v65[8 * v52] = 5;
  if ( v10 )
    v29 = v10[2];
  else
    v29 = 0;
  *(_QWORD *)&v65[8 * v52 + 6] = v29;
  *(_QWORD *)&v65[8 * v52 + 2] = &v65[8 * v52 + 6];
  ++v52;
  v60 = 0;
  v59 = 1028;
  v58 = 1;
  v62 = 0;
  v63 = 0;
  DoLogEventAndTrace(&v52);
LABEL_78:
  if ( v15 )
    RpcStringFreeA(&StringBinding);
  if ( v9 )
    free(v9);
  if ( StringSid )
    LocalFree(StringSid);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1803823d4  mov     [rsp-8+arg_0], rbx
0x1803823d9  push    rbp
0x1803823da  push    rsi
0x1803823db  push    rdi
0x1803823dc  push    r12
0x1803823de  push    r13
0x1803823e0  push    r14
0x1803823e2  push    r15
0x1803823e4  lea     rbp, [rsp-250h]
0x1803823ec  sub     rsp, 350h
0x1803823f3  mov     rax, cs:__security_cookie
0x1803823fa  xor     rax, rsp
0x1803823fd  mov     [rbp+280h+var_40], rax
0x180382404  mov     r12, [rbp+280h+arg_28]
0x18038240b  xor     ebx, ebx
0x18038240d  mov     r15, [rbp+280h+arg_20]
0x180382414  mov     rax, rdx
0x180382417  mov     [rbp+280h+var_268], rcx
0x18038241b  lea     rdx, [rbp+280h+ServerBinding]; ServerBinding
0x18038241f  mov     rcx, rax; ClientBinding
0x180382422  mov     [rbp+280h+StringBinding], rbx
0x180382426  mov     [r12], rbx
0x18038242a  mov     r13, r9
0x18038242d  mov     edi, r8d
0x180382430  mov     [rbp+280h+var_2F0], 0FFFFFFFFh
0x180382437  mov     esi, ebx
0x180382439  mov     [rbp+280h+ServerBinding], rbx
0x18038243d  mov     r14d, ebx
0x180382440  mov     [rbp+280h+StringSid], rbx
0x180382444  mov     [rbp+280h+var_2EC], ebx
0x180382447  mov     [rsp+380h+var_35C], ebx
0x18038244b  call    cs:__imp_RpcBindingServerFromClient
0x180382451  test    eax, eax
0x180382453  jnz     loc_18038252E
0x180382459  mov     rcx, [rbp+280h+ServerBinding]; Binding
0x18038245d  lea     rdx, [rbp+280h+StringBinding]; StringBinding
0x180382461  call    cs:__imp_RpcBindingToStringBindingA
0x180382467  test    eax, eax
0x180382469  jnz     loc_180382524
0x18038246f  mov     rbx, cs:gpDsEventConfig
0x180382476  test    rbx, rbx
0x180382479  jz      loc_180382524
0x18038247f  cmp     dword ptr [rbx+44h], 4
0x180382483  jge     short loc_1803824B2
0x180382485  cmp     [rbx+4], esi
0x180382488  jz      short loc_18038249B
0x18038248a  lea     edx, [rax+4]
0x18038248d  mov     ecx, 404h
0x180382492  call    DoLogOverride
0x180382497  test    eax, eax
0x180382499  jnz     short loc_1803824B2
0x18038249b  mov     ecx, 40000494h
0x1803824a0  call    DoLogMsgOverride
0x1803824a5  xor     ebx, ebx
0x1803824a7  test    eax, eax
0x1803824a9  jz      short loc_180382524
0x1803824ab  mov     rbx, cs:gpDsEventConfig
0x1803824b2  xor     eax, eax
0x1803824b4  mov     [rsp+380h+var_340], 4
0x1803824bd  mov     [rsp+380h+var_318], rax
0x1803824c2  mov     [rsp+380h+var_304], rax
0x1803824c7  mov     [rbp+280h+var_2FC], eax
0x1803824ca  mov     eax, [rbx+40h]
0x1803824cd  xor     ebx, ebx
0x1803824cf  mov     [rsp+380h+var_344], eax
0x1803824d3  lea     rax, [rbp+280h+var_260]
0x1803824d7  mov     [rbp+280h+var_2F8], rax
0x1803824db  mov     rax, [rbp+280h+StringBinding]
0x1803824df  lea     ecx, [rbx+1]
0x1803824e2  mov     [rsp+380h+var_348], 40000494h
0x1803824ea  mov     [rsp+380h+var_334], ecx
0x1803824ee  mov     [rsp+380h+var_350], rcx
0x1803824f3  mov     [rsp+380h+var_330], rcx
0x1803824f8  lea     rcx, [rsp+380h+var_350]
0x1803824fd  mov     [rsp+380h+var_338], ebx
0x180382501  mov     [rbp+280h+var_260], ebx
0x180382504  mov     [rbp+280h+var_258], rax
0x180382508  mov     [rsp+380h+var_320], rbx
0x18038250d  mov     [rsp+380h+var_328], 404h
0x180382516  mov     [rsp+380h+var_310], rbx
0x18038251b  mov     [rsp+380h+var_308], ebx
0x18038251f  call    DoLogEventAndTrace
0x180382524  lea     rcx, [rbp+280h+ServerBinding]; Binding
0x180382528  call    cs:__imp_RpcBindingFree
0x18038252e  mov     ecx, [r13+18h]; CodePage
0x180382532  call    cs:__imp_IsValidCodePage
0x180382538  test    eax, eax
0x18038253a  jz      loc_18038297A
0x180382540  cmp     dword ptr [r13+18h], 4B0h
0x180382548  jz      loc_18038297A
0x18038254e  and     edi, 20h
0x180382551  jz      short loc_18038255F
0x180382553  cmp     cs:gbAllowAnonymousNspi, ebx
0x180382559  jnz     loc_18038265E
0x18038255f  xor     ecx, ecx
0x180382561  call    VerifyRpcClientIsAuthenticatedUser
0x180382566  test    eax, eax
0x180382568  jz      loc_18038262E
0x18038256e  mov     rbx, cs:gpDsEventConfig
0x180382575  xor     r15d, r15d
0x180382578  test    rbx, rbx
0x18038257b  jz      loc_180382624
0x180382581  lea     r12d, [r15+4]
0x180382585  mov     edi, 40000498h
0x18038258a  cmp     [rbx+24h], r12d
0x18038258e  jge     short loc_1803825B9
0x180382590  cmp     [rbx+4], r15d
0x180382594  jz      short loc_1803825A7
0x180382596  mov     edx, r12d
0x180382599  mov     ecx, 404h
0x18038259e  call    DoLogOverride
0x1803825a3  test    eax, eax
0x1803825a5  jnz     short loc_1803825B9
0x1803825a7  mov     ecx, edi
0x1803825a9  call    DoLogMsgOverride
0x1803825ae  mov     rbx, cs:gpDsEventConfig
0x1803825b5  test    eax, eax
0x1803825b7  jz      short loc_180382624
0x1803825b9  xor     eax, eax
0x1803825bb  mov     [rsp+380h+var_340], r12
0x1803825c0  mov     [rsp+380h+var_318], rax
0x1803825c5  mov     [rsp+380h+var_304], rax
0x1803825ca  mov     [rbp+280h+var_2FC], eax
0x1803825cd  mov     eax, [rbx+20h]
0x1803825d0  mov     [rsp+380h+var_344], eax
0x1803825d4  lea     rax, [rbp+280h+var_260]
0x1803825d8  mov     [rbp+280h+var_2F8], rax
0x1803825dc  mov     [rsp+380h+var_350], r15
0x1803825e1  mov     [rsp+380h+var_334], 1
0x1803825e9  mov     [rsp+380h+var_338], r15d
0x1803825ee  mov     [rsp+380h+var_348], edi
0x1803825f2  mov     [rsp+380h+var_330], 1
0x1803825fb  lea     rcx, [rsp+380h+var_350]
0x180382600  mov     [rsp+380h+var_328], 404h
0x180382609  mov     [rsp+380h+var_320], r15
0x18038260e  mov     [rsp+380h+var_310], r15
0x180382613  mov     [rsp+380h+var_308], r15d
0x180382618  call    DoLogEventAndTrace
0x18038261d  mov     rbx, cs:gpDsEventConfig
0x180382624  mov     edi, 80040111h
0x180382629  jmp     loc_180382A45
0x18038262e  call    GetCurrentUserSid
0x180382633  mov     rsi, rax
0x180382636  test    rax, rax
0x180382639  jz      loc_18038256E
0x18038263f  mov     rcx, rax; pSid
0x180382642  call    cs:__imp_GetLengthSid
0x180382648  mov     ebx, eax
0x18038264a  test    edi, edi
0x18038264c  jnz     short loc_18038265E
0x18038264e  lea     rdx, [rbp+280h+StringSid]; StringSid
0x180382652  mov     rcx, rsi; Sid
0x180382655  call    cs:__imp_ConvertSidToStringSidA
0x18038265b  mov     [rbp+280h+var_2EC], eax
0x18038265e  mov     eax, cs:dword_180527F80
0x180382664  lea     r8, [rsp+380h+var_35C]
0x180382669  lea     rdx, [rsp+380h+var_360]
0x18038266e  mov     [rsp+380h+var_360], eax
0x180382672  mov     rcx, rsi; SourceSid
0x180382675  call    CheckForNSPIMaxConnLimit
0x18038267a  xor     edi, edi
0x18038267c  test    eax, eax
0x18038267e  jz      loc_18038272A
0x180382684  mov     rbx, cs:gpDsEventConfig
0x18038268b  xor     r15d, r15d
0x18038268e  test    rbx, rbx
0x180382691  jz      short loc_180382624
0x180382693  lea     edi, [r15+4]
0x180382697  mov     r12d, 40000B03h
0x18038269d  cmp     [rbx+44h], edi
0x1803826a0  jge     short loc_1803826CF
0x1803826a2  cmp     [rbx+4], r15d
0x1803826a6  jz      short loc_1803826B8
0x1803826a8  mov     edx, edi
0x1803826aa  mov     ecx, 404h
0x1803826af  call    DoLogOverride
0x1803826b4  test    eax, eax
0x1803826b6  jnz     short loc_1803826CF
0x1803826b8  mov     ecx, r12d
0x1803826bb  call    DoLogMsgOverride
0x1803826c0  mov     rbx, cs:gpDsEventConfig
0x1803826c7  test    eax, eax
0x1803826c9  jz      loc_180382624
0x1803826cf  xor     eax, eax
0x1803826d1  mov     [rsp+380h+var_340], rdi
0x1803826d6  mov     [rsp+380h+var_318], rax
0x1803826db  mov     ecx, 1
0x1803826e0  mov     [rsp+380h+var_304], rax
0x1803826e5  mov     [rbp+280h+var_2FC], eax
0x1803826e8  mov     eax, [rbx+40h]
0x1803826eb  mov     [rsp+380h+var_344], eax
0x1803826ef  lea     rax, [rbp+280h+var_260]
0x1803826f3  mov     [rbp+280h+var_2F8], rax
0x1803826f7  mov     rax, [rbp+280h+StringSid]
0x1803826fb  mov     [rsp+380h+var_350], r15
0x180382700  mov     [rsp+380h+var_348], r12d
0x180382705  mov     [rsp+380h+var_338], r15d
0x18038270a  mov     [rsp+380h+var_334], ecx
0x18038270e  test    rax, rax
0x180382711  jz      short loc_180382720
0x180382713  mov     [rbp+280h+var_260], r15d
0x180382717  mov     [rbp+280h+var_258], rax
0x18038271b  mov     [rsp+380h+var_350], rcx
0x180382720  mov     [rsp+380h+var_330], rcx
0x180382725  jmp     loc_1803825FB
0x18038272a  cmp     [rsp+380h+var_35C], edi
0x18038272e  jz      loc_1803827E0
0x180382734  mov     rbx, cs:gpDsEventConfig
0x18038273b  xor     r15d, r15d
0x18038273e  test    rbx, rbx
0x180382741  jz      loc_180382624
0x180382747  mov     edi, 40000B04h
0x18038274c  cmp     [rbx+44h], r15d
0x180382750  jge     short loc_18038277E
0x180382752  cmp     [rbx+4], r15d
0x180382756  jz      short loc_180382768
0x180382758  xor     edx, edx
0x18038275a  mov     ecx, 404h
0x18038275f  call    DoLogOverride
0x180382764  test    eax, eax
0x180382766  jnz     short loc_18038277E
0x180382768  mov     ecx, edi
0x18038276a  call    DoLogMsgOverride
0x18038276f  mov     rbx, cs:gpDsEventConfig
0x180382776  test    eax, eax
0x180382778  jz      loc_180382624
0x18038277e  xor     eax, eax
0x180382780  mov     [rbp+280h+var_260], 5
0x180382787  mov     [rsp+380h+var_340], rax
0x18038278c  lea     rcx, Source; "NULL"
0x180382793  mov     [rsp+380h+var_318], rax
0x180382798  mov     [rsp+380h+var_304], rax
0x18038279d  mov     [rbp+280h+var_2FC], eax
0x1803827a0  mov     eax, [rbx+40h]
0x1803827a3  mov     [rsp+380h+var_344], eax
0x1803827a7  lea     rax, [rbp+280h+var_260]
0x1803827ab  mov     [rbp+280h+var_2F8], rax
0x1803827af  mov     eax, [rsp+380h+var_360]
0x1803827b3  mov     [rbp+280h+var_248], rax
0x1803827b7  lea     rax, [rbp+280h+var_248]
0x1803827bb  mov     [rbp+280h+var_258], rax
0x1803827bf  mov     rax, [rbp+280h+StringSid]
0x1803827c3  test    rax, rax
0x1803827c6  mov     [rbp+280h+var_240], r15d
0x1803827ca  mov     [rsp+380h+var_350], 2
0x1803827d3  cmovnz  rcx, rax
0x1803827d7  mov     [rbp+280h+var_238], rcx
0x1803827db  jmp     loc_1803825E1
0x1803827e0  lea     r9, [rsp+380h+var_35C]
0x1803827e5  mov     [rsp+380h+var_360], edi
0x1803827e9  lea     r8, [rsp+380h+var_360]
0x1803827ee  mov     [rsp+380h+var_35C], edi
0x1803827f2  mov     edx, ebx
0x1803827f4  mov     rcx, rsi
0x1803827f7  call    HTGetGALAndTemplateDNT
0x1803827fc  mov     eax, [rsp+380h+var_360]
0x180382800  mov     rbx, cs:gpDsEventConfig
0x180382807  mov     [rsp+380h+var_360], eax
0x18038280b  mov     eax, [rsp+380h+var_35C]
0x18038280f  mov     [rbp+280h+var_2F0], eax
0x180382812  test    rbx, rbx
0x180382815  jz      loc_1803828CA
0x18038281b  mov     r14d, 5
0x180382821  cmp     [rbx+44h], r14d
0x180382825  jge     short loc_180382852
0x180382827  cmp     [rbx+4], edi
0x18038282a  jz      short loc_18038283D
0x18038282c  mov     edx, r14d
0x18038282f  mov     ecx, 404h
0x180382834  call    DoLogOverride
0x180382839  test    eax, eax
0x18038283b  jnz     short loc_180382852
0x18038283d  mov     ecx, 40000472h
0x180382842  call    DoLogMsgOverride
0x180382847  test    eax, eax
0x180382849  jz      short loc_1803828CA
0x18038284b  mov     rbx, cs:gpDsEventConfig
0x180382852  xor     eax, eax
0x180382854  mov     [rsp+380h+var_340], r14
0x180382859  mov     [rsp+380h+var_318], rax
0x18038285e  lea     rcx, [rsp+380h+var_350]
0x180382863  mov     [rsp+380h+var_304], rax
0x180382868  mov     [rbp+280h+var_2FC], eax
0x18038286b  mov     eax, [rbx+40h]
0x18038286e  mov     [rsp+380h+var_344], eax
0x180382872  lea     rax, [rbp+280h+var_260]
0x180382876  mov     [rbp+280h+var_2F8], rax
0x18038287a  lea     rax, aNspibind; "NspiBind"
0x180382881  mov     [rbp+280h+var_258], rax
0x180382885  mov     [rsp+380h+var_348], 40000472h
0x18038288d  mov     [rsp+380h+var_338], edi
0x180382891  mov     [rsp+380h+var_334], 1
0x180382899  mov     [rbp+280h+var_260], edi
0x18038289c  mov     [rsp+380h+var_350], 1
0x1803828a5  mov     [rsp+380h+var_320], rdi
0x1803828aa  mov     [rsp+380h+var_328], 404h
0x1803828b3  mov     [rsp+380h+var_330], 1
0x1803828bc  mov     [rsp+380h+var_310], rdi
0x1803828c1  mov     [rsp+380h+var_308], edi
0x1803828c5  call    DoLogEventAndTrace
  ... truncated ...
```
