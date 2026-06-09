# CDMClientValueNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x180033640`
- end: `0x180033ca6`
- name: `?CreateNodeInstance@CDMClientValueNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `1638`
- prototype: `__int64 __usercall@<rax>(struct CConfigServiceProvider2Impl *@<rcx>, struct IConfigManager2URI *@<rdx>, const struct CSP_NODE_DATA *@<r8>, int@<r9d>, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180030660`

## callees

- `0x180008de0`
- `0x18001a4fc`
- `0x180021944`
- `0x180027388`
- `0x18002796c`
- `0x180028994`
- `0x180028b60`
- `0x18002955c`
- `0x180029ab0`
- `0x180029ec8`
- `0x1800319cc`
- `0x180033640`
- `0x180036b00`
- `0x1800384d0`
- `0x1800397e0`
- `0x18003a120`
- `0x18003f3d4`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180033bf7`
- `OLEAUT32!__imp_SysAllocString` at `0x180033bf7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800337a9`
- `OLEAUT32!__imp_SysFreeString` at `0x180033a35`
- `OLEAUT32!__imp_SysFreeString` at `0x180033c47`
- `OLEAUT32!__imp_SysFreeString` at `0x180033c63`
- `OLEAUT32!__imp_SysFreeString` at `0x1800337a9`
- `OLEAUT32!__imp_SysFreeString` at `0x180033a35`
- `OLEAUT32!__imp_SysFreeString` at `0x180033c47`
- `OLEAUT32!__imp_SysFreeString` at `0x180033c63`
- `OLEAUT32!__imp_VariantInit` at `0x1800336aa`
- `OLEAUT32!__imp_VariantInit` at `0x180033802`
- `OLEAUT32!__imp_VariantInit` at `0x1800336aa`
- `OLEAUT32!__imp_VariantInit` at `0x180033802`
- `OLEAUT32!__imp_VariantClear` at `0x180033a4c`
- `OLEAUT32!__imp_VariantClear` at `0x180033a4c`
- `RPCRT4!UuidFromStringW` at `0x18003387d`
- `RPCRT4!UuidFromStringW` at `0x180033894`
- `RPCRT4!UuidFromStringW` at `0x180033973`
- `RPCRT4!UuidFromStringW` at `0x180033b05`
- `RPCRT4!UuidFromStringW` at `0x180033b1c`
- `RPCRT4!UuidFromStringW` at `0x180033b6c`
- `RPCRT4!UuidFromStringW` at `0x18003387d`
- `RPCRT4!UuidFromStringW` at `0x180033894`
- `RPCRT4!UuidFromStringW` at `0x180033973`
- `RPCRT4!UuidFromStringW` at `0x180033b05`
- `RPCRT4!UuidFromStringW` at `0x180033b1c`
- `RPCRT4!UuidFromStringW` at `0x180033b6c`
- `dmEnrollEngine!GetEnrollmentUPN` at `0x1800338c7`
- `dmEnrollEngine!GetEnrollmentUPN` at `0x1800338c7`
- `dmEnrollEngine!GetEnrollmentAadSendDeviceToken` at `0x180033b8d`
- `dmEnrollEngine!GetEnrollmentAadSendDeviceToken` at `0x180033b8d`
- `dmEnrollEngine!GetEnrollmentForceAadToken` at `0x180033b46`
- `dmEnrollEngine!GetEnrollmentForceAadToken` at `0x180033b46`
- `dmEnrollEngine!GetEnrollmentAadResourceUrl` at `0x180033998`
- `dmEnrollEngine!GetEnrollmentAadResourceUrl` at `0x180033998`

## string_xrefs

- `0x180033c37`: `CDMClientValueNode::CreateNodeInstance`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDMClientValueNode::CreateNodeInstance(
        struct CConfigServiceProvider2Impl *a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        int a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  struct ICSPNode **v9; // r14
  int v10; // ebx
  unsigned __int16 *EnrollmentId2; // rax
  signed int DoesProviderIdExist; // edi
  int *v13; // r9
  DMClient *v14; // rsi
  unsigned __int16 **v15; // rdx
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  bool v19; // zf
  unsigned int v20; // eax
  int DeviceIDString; // ebx
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  const unsigned __int16 *v25; // rdi
  OLECHAR *v26; // r14
  int ProviderPolicyValue; // eax
  int EnrollmentUPN; // eax
  unsigned int *v29; // r8
  int ExpiryTime; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  int v35; // eax
  unsigned __int16 **v36; // r8
  int HardwareDevID; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // eax
  unsigned int *v41; // r8
  struct ICSPNode *v42; // rbx
  BSTR v43; // rax
  struct tagVARIANT *v45; // [rsp+20h] [rbp-89h]
  BSTR bstrString; // [rsp+30h] [rbp-79h] BYREF
  int v47; // [rsp+38h] [rbp-71h]
  OLECHAR *psz; // [rsp+40h] [rbp-69h] BYREF
  int v49; // [rsp+48h] [rbp-61h] BYREF
  _QWORD v50[2]; // [rsp+50h] [rbp-59h] BYREF
  VARIANTARG v51; // [rsp+60h] [rbp-49h] BYREF
  RPC_WSTR StringUuid; // [rsp+80h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-21h] BYREF
  UUID Uuid; // [rsp+A0h] [rbp-9h] BYREF

  v47 = a4;
  v9 = a5;
  *(_QWORD *)&Uuid.Data1 = a5;
  psz = 0;
  v49 = 0;
  v10 = 0;
  LODWORD(bstrString) = 0;
  v50[0] = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  StringUuid = 0;
  VariantInit(&pvarg);
  if ( a1 && a2 && a3 && a5 && a6 )
  {
    *a5 = 0;
    *a6 = 0;
    EnrollmentId2 = GetEnrollmentId2(a1);
    ATL::CComBSTR::operator=(&StringUuid, EnrollmentId2);
    if ( *((_DWORD *)a3 + 3) == 32 )
      *a6 = 2;
    DoesProviderIdExist = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(
                            a2,
                            &v49);
    v14 = (DMClient *)StringUuid;
    if ( DoesProviderIdExist < 0 )
      goto LABEL_97;
    DoesProviderIdExist = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, OLECHAR **))(*(_QWORD *)a2 + 88LL))(
                            a2,
                            (unsigned int)(v49 - 2),
                            &psz);
    if ( DoesProviderIdExist < 0 )
      goto LABEL_97;
    v16 = *((_DWORD *)a3 + 3);
    if ( v16 <= 0x2F )
    {
      if ( v16 == 47 )
      {
        DoesProviderIdExist = DMClient::DoesProviderIdExist(v14, psz, (const unsigned __int16 *)&bstrString, v13);
        if ( DoesProviderIdExist < 0 )
          goto LABEL_97;
        v10 = (int)bstrString;
        if ( !(_DWORD)bstrString )
          goto LABEL_72;
        ExpiryTime = DMClient::GetExpiryTime(v14, 0, v41);
LABEL_59:
        if ( ExpiryTime != -2147024894 )
        {
          if ( ExpiryTime < 0 )
            goto LABEL_71;
LABEL_89:
          v10 = 1;
          goto LABEL_71;
        }
        v10 = 0;
LABEL_72:
        v35 = v47;
        if ( !v47 )
        {
          DoesProviderIdExist = -2046820350;
          goto LABEL_97;
        }
        if ( !v10 )
        {
LABEL_91:
          DoesProviderIdExist = ATL::CComObject<CDMClientValueNode>::CreateInstance(v50);
          if ( DoesProviderIdExist >= 0 )
          {
            v42 = (struct ICSPNode *)v50[0];
            if ( v50[0] )
            {
              DoesProviderIdExist = (*(__int64 (__fastcall **)(_QWORD, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*(_QWORD *)v50[0] + 136LL))(
                                      v50[0],
                                      a1,
                                      a2,
                                      a3);
              if ( DoesProviderIdExist < 0 )
                goto LABEL_97;
              v43 = SysAllocString(psz);
              *((_QWORD *)v42 + 16) = v43;
              if ( v43 )
              {
                (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v42 + 8LL))(v42);
                *((_QWORD *)v42 + 17) = a1;
                v50[0] = 0;
                *v9 = v42;
                goto LABEL_97;
              }
            }
            DoesProviderIdExist = -2147024882;
          }
LABEL_97:
          DmClientLogging::Write(
            L"CDMClientValueNode::CreateNodeInstance",
            *((_DWORD *)a3 + 3),
            DoesProviderIdExist,
            (int)v13);
          SysFreeString((BSTR)v14);
          ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(v50);
          return (unsigned int)DoesProviderIdExist;
        }
LABEL_52:
        if ( v35 )
        {
          DoesProviderIdExist = -2046820335;
          goto LABEL_97;
        }
        goto LABEL_91;
      }
      if ( v16 <= 0x1D )
      {
        if ( v16 != 29 )
        {
          if ( v16 <= 7 )
          {
            if ( v16 == 7 )
              goto LABEL_22;
            v17 = v16 - 2;
            if ( v17 )
            {
              v18 = v17 - 1;
              if ( !v18 )
                goto LABEL_29;
              v20 = v18 - 1;
              v19 = v20 == 0;
LABEL_26:
              if ( !v19 )
              {
                v24 = v20 - 1;
                if ( v24 )
                  goto LABEL_28;
              }
LABEL_29:
              v25 = *(const unsigned __int16 **)a3;
              v26 = psz;
              memset(&v51, 0, sizeof(v51));
              VariantInit(&v51);
              if ( v26 && v25 && v14 )
              {
                ProviderPolicyValue = DMClient::GetProviderPolicyValue(v14, v26, v25, &v51.vt, v45);
                DoesProviderIdExist = ProviderPolicyValue;
                if ( ProviderPolicyValue != -2147024894 )
                {
                  if ( (int)(ProviderPolicyValue + 0x80000000) >= 0 && ProviderPolicyValue != -2147023266 )
                    goto LABEL_69;
                  v10 = 1;
                }
                DoesProviderIdExist = 0;
              }
              else
              {
                DoesProviderIdExist = -2147024809;
              }
LABEL_69:
              VariantClear(&v51);
              if ( DoesProviderIdExist < 0 )
                goto LABEL_97;
              v9 = *(struct ICSPNode ***)&Uuid.Data1;
LABEL_71:
              if ( !v10 )
                goto LABEL_72;
LABEL_51:
              v35 = v47;
              goto LABEL_52;
            }
            bstrString = 0;
            DeviceIDString = GetDeviceIDString(a1, &bstrString);
            if ( bstrString )
              SysFreeString(bstrString);
LABEL_21:
            v10 = DeviceIDString >= 0;
            goto LABEL_71;
          }
          v22 = v16 - 8;
          if ( v22 )
          {
            v23 = v22 - 13;
            if ( v23 )
            {
              v20 = v23 - 3;
              v19 = v20 == 0;
              goto LABEL_26;
            }
            Uuid = 0;
            bstrString = 0;
            if ( UuidFromStringW((RPC_WSTR)v14, &Uuid) )
            {
LABEL_38:
              DoesProviderIdExist = UuidFromStringW((RPC_WSTR)v14, &Uuid) | 0x80010000;
              CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&bstrString);
              goto LABEL_97;
            }
            *(UUID *)&v51.vt = Uuid;
            EnrollmentUPN = GetEnrollmentUPN(&v51, &bstrString);
LABEL_40:
            v10 = EnrollmentUPN >= 0;
            CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&bstrString);
            goto LABEL_71;
          }
LABEL_76:
          DoesProviderIdExist = DMClient::DoesProviderIdExist(v14, psz, (const unsigned __int16 *)&bstrString, v13);
          if ( DoesProviderIdExist < 0 )
            goto LABEL_97;
          v10 = (int)bstrString;
          goto LABEL_71;
        }
        DoesProviderIdExist = DMClient::DoesProviderIdExist(v14, psz, (const unsigned __int16 *)&bstrString, v13);
        if ( DoesProviderIdExist < 0 )
          goto LABEL_97;
        v10 = (int)bstrString;
        if ( !(_DWORD)bstrString )
          goto LABEL_72;
        ExpiryTime = DMClient::GetSignatureRequired(v14, 0, v29);
        goto LABEL_59;
      }
      if ( v16 > 0x24 )
      {
        v38 = v16 - 37;
        if ( !v38 )
          goto LABEL_76;
        v39 = v38 - 1;
        if ( v39 )
        {
          v40 = v39 - 1;
          if ( !v40 )
            goto LABEL_51;
          v24 = v40 - 1;
          if ( !v24 )
          {
            bstrString = 0;
            v10 = (int)GetCommercialID(&bstrString) >= 0;
            SysFreeString(bstrString);
            goto LABEL_71;
          }
LABEL_28:
          if ( v24 == 1 )
            goto LABEL_29;
LABEL_22:
          DoesProviderIdExist = -2147418113;
          goto LABEL_97;
        }
        HardwareDevID = DMClient::GetHardwareDevID(0, v15);
      }
      else
      {
        if ( v16 != 36 )
        {
          v31 = v16 - 30;
          if ( v31 )
          {
            v32 = v31 - 1;
            if ( !v32 )
              goto LABEL_51;
            v33 = v32 - 1;
            if ( !v33 )
              goto LABEL_51;
            v34 = v33 - 1;
            if ( v34 )
            {
              if ( v34 == 2 )
                goto LABEL_51;
              goto LABEL_22;
            }
            Uuid = 0;
            bstrString = 0;
            if ( UuidFromStringW((RPC_WSTR)v14, &Uuid) )
              goto LABEL_38;
            *(UUID *)&v51.vt = Uuid;
            EnrollmentUPN = GetEnrollmentAadResourceUrl(&v51, &bstrString);
            goto LABEL_40;
          }
          DoesProviderIdExist = DMClient::DoesProviderIdExist(v14, psz, (const unsigned __int16 *)&bstrString, v13);
          if ( DoesProviderIdExist < 0 )
            goto LABEL_97;
          v10 = (int)bstrString;
          if ( !(_DWORD)bstrString )
            goto LABEL_72;
          ExpiryTime = DMClient::GetManagementServiceVersion(v14, 0, v36);
          goto LABEL_59;
        }
        HardwareDevID = DMClient::GetAADDeviceID(0, v15);
      }
LABEL_75:
      DeviceIDString = HardwareDevID;
      goto LABEL_21;
    }
    if ( v16 == 69 )
    {
      Uuid = 0;
      LODWORD(bstrString) = 0;
      if ( !UuidFromStringW((RPC_WSTR)v14, &Uuid) )
      {
        *(UUID *)&v51.vt = Uuid;
        if ( (int)GetEnrollmentAadSendDeviceToken(&v51, &bstrString) >= 0 )
          goto LABEL_89;
        goto LABEL_72;
      }
    }
    else
    {
      if ( v16 != 85 )
        goto LABEL_22;
      Uuid = 0;
      LODWORD(bstrString) = 0;
      if ( !UuidFromStringW((RPC_WSTR)v14, &Uuid) )
      {
        *(UUID *)&v51.vt = Uuid;
        HardwareDevID = GetEnrollmentForceAadToken(&v51, &bstrString);
        goto LABEL_75;
      }
    }
    DoesProviderIdExist = UuidFromStringW((RPC_WSTR)v14, &Uuid) | 0x80010000;
    goto LABEL_97;
  }
  SysFreeString(0);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(v50);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180033640  mov     [rsp-8+arg_18], rbx
0x180033645  push    rbp
0x180033646  push    rsi
0x180033647  push    rdi
0x180033648  push    r12
0x18003364a  push    r13
0x18003364c  push    r14
0x18003364e  push    r15
0x180033650  lea     rbp, [rsp-17h]
0x180033655  sub     rsp, 0C0h
0x18003365c  mov     rax, cs:__security_cookie
0x180033663  xor     rax, rsp
0x180033666  mov     [rbp+47h+var_40], rax
0x18003366a  mov     [rbp+47h+var_B8], r9d
0x18003366e  mov     r15, r8
0x180033671  mov     r13, rdx
0x180033674  mov     r12, rcx
0x180033677  mov     r14, [rbp+47h+arg_20]
0x18003367b  mov     qword ptr [rbp+47h+Uuid.Data1], r14
0x18003367f  mov     rdi, [rbp+47h+arg_28]
0x180033683  xor     esi, esi
0x180033685  mov     [rbp+47h+psz], rsi
0x180033689  mov     [rbp+47h+var_A8], esi
0x18003368c  mov     ebx, esi
0x18003368e  mov     dword ptr [rbp+47h+bstrString], ebx
0x180033691  mov     [rbp+47h+var_A0], rsi
0x180033695  xorps   xmm0, xmm0
0x180033698  xor     eax, eax
0x18003369a  movups  xmmword ptr [rbp+47h+pvarg], xmm0
0x18003369e  mov     qword ptr [rbp+47h+pvarg+10h], rax
0x1800336a2  mov     [rbp+47h+StringUuid], rsi
0x1800336a6  lea     rcx, [rbp+47h+pvarg]; pvarg
0x1800336aa  call    cs:__imp_VariantInit
0x1800336b1  nop     dword ptr [rax+rax+00h]
0x1800336b6  test    r12, r12
0x1800336b9  jz      loc_180033C61
0x1800336bf  test    r13, r13
0x1800336c2  jz      loc_180033C61
0x1800336c8  test    r15, r15
0x1800336cb  jz      loc_180033C61
0x1800336d1  test    r14, r14
0x1800336d4  jz      loc_180033C61
0x1800336da  test    rdi, rdi
0x1800336dd  jz      loc_180033C61
0x1800336e3  mov     [r14], rsi
0x1800336e6  mov     [rdi], esi
0x1800336e8  mov     rcx, r12; struct CConfigServiceProvider2Impl *
0x1800336eb  call    ?GetEnrollmentId2@@YAPEAGPEAVCConfigServiceProvider2Impl@@@Z; GetEnrollmentId2(CConfigServiceProvider2Impl *)
0x1800336f0  mov     rdx, rax
0x1800336f3  lea     rcx, [rbp+47h+StringUuid]
0x1800336f7  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1800336fc  cmp     dword ptr [r15+0Ch], 20h ; ' '
0x180033701  jnz     short loc_180033709
0x180033703  mov     dword ptr [rdi], 2
0x180033709  mov     rax, [r13+0]
0x18003370d  lea     rdx, [rbp+47h+var_A8]
0x180033711  mov     rcx, r13
0x180033714  mov     rax, [rax+88h]
0x18003371b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033720  mov     edi, eax
0x180033722  mov     rsi, [rbp+47h+StringUuid]
0x180033726  test    eax, eax
0x180033728  js      loc_180033C30
0x18003372e  mov     rax, [r13+0]
0x180033732  mov     edx, [rbp+47h+var_A8]
0x180033735  add     edx, 0FFFFFFFEh
0x180033738  lea     r8, [rbp+47h+psz]
0x18003373c  mov     rcx, r13
0x18003373f  mov     rax, [rax+58h]
0x180033743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033748  mov     edi, eax
0x18003374a  test    eax, eax
0x18003374c  js      loc_180033C30
0x180033752  mov     eax, [r15+0Ch]
0x180033756  cmp     eax, 2Fh ; '/'
0x180033759  ja      loc_180033AE2
0x18003375f  jz      loc_180033AAE
0x180033765  cmp     eax, 1Dh
0x180033768  ja      loc_18003391C
0x18003376e  jz      loc_1800338E8
0x180033774  cmp     eax, 7
0x180033777  ja      short loc_1800337C9
0x180033779  jz      short loc_1800337BF
0x18003377b  sub     eax, 2
0x18003377e  jz      short loc_18003378A
0x180033780  sub     eax, 1
0x180033783  jz      short loc_1800337EA
0x180033785  sub     eax, 1
0x180033788  jmp     short loc_1800337DE
0x18003378a  mov     [rbp+47h+bstrString], 0
0x180033792  lea     rdx, [rbp+47h+bstrString]; unsigned __int16 **
0x180033796  mov     rcx, r12; struct CConfigServiceProvider2Impl *
0x180033799  call    ?GetDeviceIDString@@YAJPEAVCConfigServiceProvider2Impl@@PEAPEAG@Z; GetDeviceIDString(CConfigServiceProvider2Impl *,ushort * *)
0x18003379e  mov     ebx, eax
0x1800337a0  mov     rcx, [rbp+47h+bstrString]; bstrString
0x1800337a4  test    rcx, rcx
0x1800337a7  jz      short loc_1800337B5
0x1800337a9  call    cs:__imp_SysFreeString
0x1800337b0  nop     dword ptr [rax+rax+00h]
0x1800337b5  not     ebx
0x1800337b7  shr     ebx, 1Fh
0x1800337ba  jmp     loc_180033A64
0x1800337bf  mov     edi, 8000FFFFh
0x1800337c4  jmp     loc_180033C30
0x1800337c9  sub     eax, 8
0x1800337cc  jz      loc_180033A8F
0x1800337d2  sub     eax, 0Dh
0x1800337d5  jz      loc_180033867
0x1800337db  sub     eax, 3
0x1800337de  jz      short loc_1800337EA
0x1800337e0  sub     eax, 1
0x1800337e3  jz      short loc_1800337EA
0x1800337e5  cmp     eax, 1
0x1800337e8  jnz     short loc_1800337BF
0x1800337ea  mov     rdi, [r15]
0x1800337ed  mov     r14, [rbp+47h+psz]
0x1800337f1  xorps   xmm0, xmm0
0x1800337f4  xor     eax, eax
0x1800337f6  movups  xmmword ptr [rbp+47h+var_90], xmm0
0x1800337fa  mov     qword ptr [rbp+47h+var_90+10h], rax
0x1800337fe  lea     rcx, [rbp+47h+var_90]; pvarg
0x180033802  call    cs:__imp_VariantInit
0x180033809  nop     dword ptr [rax+rax+00h]
0x18003380e  test    r14, r14
0x180033811  jz      loc_180033A43
0x180033817  test    rdi, rdi
0x18003381a  jz      loc_180033A43
0x180033820  test    rsi, rsi
0x180033823  jz      loc_180033A43
0x180033829  lea     r9, [rbp+47h+var_90]; unsigned __int16 *
0x18003382d  mov     r8, rdi; unsigned __int16 *
0x180033830  mov     rdx, r14; unsigned __int16 *
0x180033833  mov     rcx, rsi; this
0x180033836  call    ?GetProviderPolicyValue@DMClient@@YAJPEBG00PEAUtagVARIANT@@@Z; DMClient::GetProviderPolicyValue(ushort const *,ushort const *,ushort const *,tagVARIANT *)
0x18003383b  mov     edi, eax
0x18003383d  cmp     eax, 80070002h
0x180033842  jz      short loc_180033860
0x180033844  mov     ecx, 80000000h
0x180033849  add     eax, ecx
0x18003384b  test    ecx, eax
0x18003384d  jnz     short loc_18003385B
0x18003384f  cmp     edi, 8007065Eh
0x180033855  jnz     loc_180033A48
0x18003385b  mov     ebx, 1
0x180033860  xor     edi, edi
0x180033862  jmp     loc_180033A48
0x180033867  xorps   xmm0, xmm0
0x18003386a  movups  xmmword ptr [rbp+47h+Uuid.Data1], xmm0
0x18003386e  mov     [rbp+47h+bstrString], 0
0x180033876  lea     rdx, [rbp+47h+Uuid]; Uuid
0x18003387a  mov     rcx, rsi; StringUuid
0x18003387d  call    cs:__imp_UuidFromStringW
0x180033884  nop     dword ptr [rax+rax+00h]
0x180033889  test    eax, eax
0x18003388b  jz      short loc_1800338B6
0x18003388d  lea     rdx, [rbp+47h+Uuid]; Uuid
0x180033891  mov     rcx, rsi; StringUuid
0x180033894  call    cs:__imp_UuidFromStringW
0x18003389b  nop     dword ptr [rax+rax+00h]
0x1800338a0  mov     edi, eax
0x1800338a2  or      edi, 80010000h
0x1800338a8  lea     rcx, [rbp+47h+bstrString]
0x1800338ac  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x1800338b1  jmp     loc_180033C30
0x1800338b6  movaps  xmm0, xmmword ptr [rbp+47h+Uuid.Data1]
0x1800338ba  movdqa  xmmword ptr [rbp+47h+var_90], xmm0
0x1800338bf  lea     rdx, [rbp+47h+bstrString]
0x1800338c3  lea     rcx, [rbp+47h+var_90]
0x1800338c7  call    cs:__imp_GetEnrollmentUPN
0x1800338ce  nop     dword ptr [rax+rax+00h]
0x1800338d3  mov     ebx, eax
0x1800338d5  not     ebx
0x1800338d7  shr     ebx, 1Fh
0x1800338da  lea     rcx, [rbp+47h+bstrString]
0x1800338de  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x1800338e3  jmp     loc_180033A64
0x1800338e8  lea     r8, [rbp+47h+bstrString]; unsigned __int16 *
0x1800338ec  mov     rdx, [rbp+47h+psz]; unsigned __int16 *
0x1800338f0  mov     rcx, rsi; this
0x1800338f3  call    ?DoesProviderIdExist@DMClient@@YAJPEBG0PEAH@Z; DMClient::DoesProviderIdExist(ushort const *,ushort const *,int *)
0x1800338f8  mov     edi, eax
0x1800338fa  test    eax, eax
0x1800338fc  js      loc_180033C30
0x180033902  mov     ebx, dword ptr [rbp+47h+bstrString]
0x180033905  test    ebx, ebx
0x180033907  jz      loc_180033A6C
0x18003390d  xor     edx, edx; unsigned __int16 *
0x18003390f  mov     rcx, rsi; this
0x180033912  call    ?GetSignatureRequired@DMClient@@YAJPEBGPEAK@Z; DMClient::GetSignatureRequired(ushort const *,ulong *)
0x180033917  jmp     loc_1800339D8
0x18003391c  cmp     eax, 24h ; '$'
0x18003391f  ja      loc_1800339F9
0x180033925  jz      loc_1800339ED
0x18003392b  sub     eax, 1Eh
0x18003392e  jz      short loc_1800339A9
0x180033930  sub     eax, 1
0x180033933  jz      short loc_180033948
0x180033935  sub     eax, 1
0x180033938  jz      short loc_180033948
0x18003393a  sub     eax, 1
0x18003393d  jz      short loc_18003395D
0x18003393f  cmp     eax, 2
0x180033942  jnz     loc_1800337BF
0x180033948  mov     eax, [rbp+47h+var_B8]
0x18003394b  test    eax, eax
0x18003394d  jz      loc_180033BB3
0x180033953  mov     edi, 86000011h
0x180033958  jmp     loc_180033C30
0x18003395d  xorps   xmm0, xmm0
0x180033960  movups  xmmword ptr [rbp+47h+Uuid.Data1], xmm0
0x180033964  mov     [rbp+47h+bstrString], 0
0x18003396c  lea     rdx, [rbp+47h+Uuid]; Uuid
0x180033970  mov     rcx, rsi; StringUuid
0x180033973  call    cs:__imp_UuidFromStringW
0x18003397a  nop     dword ptr [rax+rax+00h]
0x18003397f  test    eax, eax
0x180033981  jnz     loc_18003388D
0x180033987  movaps  xmm0, xmmword ptr [rbp+47h+Uuid.Data1]
0x18003398b  movdqa  xmmword ptr [rbp+47h+var_90], xmm0
0x180033990  lea     rdx, [rbp+47h+bstrString]
0x180033994  lea     rcx, [rbp+47h+var_90]
0x180033998  call    cs:__imp_GetEnrollmentAadResourceUrl
0x18003399f  nop     dword ptr [rax+rax+00h]
0x1800339a4  jmp     loc_1800338D3
0x1800339a9  lea     r8, [rbp+47h+bstrString]; unsigned __int16 *
0x1800339ad  mov     rdx, [rbp+47h+psz]; unsigned __int16 *
0x1800339b1  mov     rcx, rsi; this
0x1800339b4  call    ?DoesProviderIdExist@DMClient@@YAJPEBG0PEAH@Z; DMClient::DoesProviderIdExist(ushort const *,ushort const *,int *)
0x1800339b9  mov     edi, eax
0x1800339bb  test    eax, eax
0x1800339bd  js      loc_180033C30
0x1800339c3  mov     ebx, dword ptr [rbp+47h+bstrString]
0x1800339c6  test    ebx, ebx
0x1800339c8  jz      loc_180033A6C
0x1800339ce  xor     edx, edx; unsigned __int16 *
0x1800339d0  mov     rcx, rsi; this
0x1800339d3  call    ?GetManagementServiceVersion@DMClient@@YAJPEBGPEAPEAG@Z; DMClient::GetManagementServiceVersion(ushort const *,ushort * *)
0x1800339d8  cmp     eax, 80070002h
0x1800339dd  jz      loc_180033ADE
0x1800339e3  test    eax, eax
0x1800339e5  jns     loc_180033BA1
0x1800339eb  jmp     short loc_180033A64
0x1800339ed  xor     ecx, ecx; this
0x1800339ef  call    ?GetAADDeviceID@DMClient@@YAJPEAPEAG@Z; DMClient::GetAADDeviceID(ushort * *)
0x1800339f4  jmp     loc_180033A88
0x1800339f9  sub     eax, 25h ; '%'
0x1800339fc  jz      loc_180033A8F
0x180033a02  sub     eax, 1
0x180033a05  jz      short loc_180033A81
0x180033a07  sub     eax, 1
0x180033a0a  jz      loc_180033948
0x180033a10  sub     eax, 1
0x180033a13  jnz     loc_1800337E5
0x180033a19  mov     [rbp+47h+bstrString], 0
0x180033a21  lea     rcx, [rbp+47h+bstrString]; unsigned __int16 **
0x180033a25  call    ?GetCommercialID@@YAJPEAPEAG@Z; GetCommercialID(ushort * *)
0x180033a2a  mov     ebx, eax
0x180033a2c  not     ebx
0x180033a2e  shr     ebx, 1Fh
0x180033a31  mov     rcx, [rbp+47h+bstrString]; bstrString
0x180033a35  call    cs:__imp_SysFreeString
0x180033a3c  nop     dword ptr [rax+rax+00h]
0x180033a41  jmp     short loc_180033A64
0x180033a43  mov     edi, 80070057h
0x180033a48  lea     rcx, [rbp+47h+var_90]; pvarg
0x180033a4c  call    cs:__imp_VariantClear
0x180033a53  nop     dword ptr [rax+rax+00h]
0x180033a58  test    edi, edi
0x180033a5a  js      loc_180033C30
0x180033a60  mov     r14, qword ptr [rbp+47h+Uuid.Data1]
0x180033a64  test    ebx, ebx
0x180033a66  jnz     loc_180033948
0x180033a6c  mov     eax, [rbp+47h+var_B8]
0x180033a6f  test    eax, eax
0x180033a71  jnz     loc_180033BAB
0x180033a77  mov     edi, 86000002h
0x180033a7c  jmp     loc_180033C30
0x180033a81  xor     ecx, ecx; this
0x180033a83  call    ?GetHardwareDevID@DMClient@@YAJPEAPEAG@Z; DMClient::GetHardwareDevID(ushort * *)
0x180033a88  mov     ebx, eax
0x180033a8a  jmp     loc_1800337B5
0x180033a8f  lea     r8, [rbp+47h+bstrString]; unsigned __int16 *
0x180033a93  mov     rdx, [rbp+47h+psz]; unsigned __int16 *
0x180033a97  mov     rcx, rsi; this
0x180033a9a  call    ?DoesProviderIdExist@DMClient@@YAJPEBG0PEAH@Z; DMClient::DoesProviderIdExist(ushort const *,ushort const *,int *)
0x180033a9f  mov     edi, eax
0x180033aa1  test    eax, eax
0x180033aa3  js      loc_180033C30
0x180033aa9  mov     ebx, dword ptr [rbp+47h+bstrString]
0x180033aac  jmp     short loc_180033A64
0x180033aae  lea     r8, [rbp+47h+bstrString]; unsigned __int16 *
0x180033ab2  mov     rdx, [rbp+47h+psz]; unsigned __int16 *
0x180033ab6  mov     rcx, rsi; this
0x180033ab9  call    ?DoesProviderIdExist@DMClient@@YAJPEBG0PEAH@Z; DMClient::DoesProviderIdExist(ushort const *,ushort const *,int *)
0x180033abe  mov     edi, eax
0x180033ac0  test    eax, eax
0x180033ac2  js      loc_180033C30
0x180033ac8  mov     ebx, dword ptr [rbp+47h+bstrString]
0x180033acb  test    ebx, ebx
0x180033acd  jz      short loc_180033A6C
  ... truncated ...
```
