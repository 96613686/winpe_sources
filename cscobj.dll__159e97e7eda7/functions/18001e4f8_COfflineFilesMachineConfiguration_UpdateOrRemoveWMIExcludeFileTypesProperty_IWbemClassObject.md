# COfflineFilesMachineConfiguration::UpdateOrRemoveWMIExcludeFileTypesProperty(IWbemClassObject *)

- ea: `0x18001e4f8`
- end: `0x18001e8fd`
- name: `?UpdateOrRemoveWMIExcludeFileTypesProperty@COfflineFilesMachineConfiguration@@CAJPEAUIWbemClassObject@@@Z`
- size: `1029`
- prototype: `__int64 __fastcall(struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001f820`

## callees

- `0x18000f5cc`
- `0x180014068`
- `0x18001886c`
- `0x18001c7bc`
- `0x18001ce94`
- `0x18001d74c`
- `0x18001d8e4`
- `0x18001d954`
- `0x18001d9d8`
- `0x18001e4f8`
- `0x18001e904`
- `0x1800224c4`
- `0x18002c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001e6d4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e7bd`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e8e5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e6d4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e7bd`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e8e5`
- `OLEAUT32!__imp_SysStringLen` at `0x18001e656`
- `OLEAUT32!__imp_SysStringLen` at `0x18001e6ab`
- `OLEAUT32!__imp_SysStringLen` at `0x18001e747`
- `OLEAUT32!__imp_SysStringLen` at `0x18001e794`
- `OLEAUT32!__imp_SysStringLen` at `0x18001e656`
- `OLEAUT32!__imp_SysStringLen` at `0x18001e6ab`
- `OLEAUT32!__imp_SysStringLen` at `0x18001e747`
- `OLEAUT32!__imp_SysStringLen` at `0x18001e794`
- `OLEAUT32!__imp_VariantInit` at `0x18001e517`
- `OLEAUT32!__imp_VariantInit` at `0x18001e517`
- `OLEAUT32!__imp_VariantClear` at `0x18001e7db`
- `OLEAUT32!__imp_VariantClear` at `0x18001e81e`
- `OLEAUT32!__imp_VariantClear` at `0x18001e8b2`
- `OLEAUT32!__imp_VariantClear` at `0x18001e7db`
- `OLEAUT32!__imp_VariantClear` at `0x18001e81e`
- `OLEAUT32!__imp_VariantClear` at `0x18001e8b2`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001e84f`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001e84f`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001e85a`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001e85a`
- `OLEAUT32!__imp_VarBstrCat` at `0x18001e6c7`
- `OLEAUT32!__imp_VarBstrCat` at `0x18001e7b0`
- `OLEAUT32!__imp_VarBstrCat` at `0x18001e6c7`
- `OLEAUT32!__imp_VarBstrCat` at `0x18001e7b0`

## pseudocode

```c
__int64 __fastcall COfflineFilesMachineConfiguration::UpdateOrRemoveWMIExcludeFileTypesProperty(
        struct IWbemClassObject *a1)
{
  OLECHAR *v2; // rbx
  int v3; // r15d
  int v4; // esi
  int LowerBound; // edi
  int v6; // r14d
  int v7; // r14d
  int v8; // r14d
  OLECHAR *v9; // r14
  const unsigned __int16 *v10; // rdx
  int v11; // edi
  int v12; // edi
  OLECHAR *v13; // rdi
  BSTR v14; // rax
  UINT v15; // eax
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF
  SAFEARRAY *ppsaOut; // [rsp+A0h] [rbp+40h] BYREF
  BSTR v19; // [rsp+A8h] [rbp+48h] BYREF
  BSTR pbstrResult; // [rsp+B0h] [rbp+50h] BYREF

  v2 = 0;
  v19 = 0;
  VariantInit(&pvarg);
  v3 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a1->lpVtbl->Get)(
         a1,
         L"ExcludedFileTypes",
         0,
         &pvarg,
         0,
         0);
  if ( v3 >= 0 && pvarg.vt == 8200 )
  {
    ATL::CComSafeArray<unsigned short *,8>::CComSafeArray<unsigned short *,8>(&ppsaOut, pvarg.parray);
    v4 = ATL::CComSafeArray<unsigned short *,8>::GetCount(&ppsaOut) - 1;
    LowerBound = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&ppsaOut);
    if ( LowerBound < v4 )
    {
      while ( 1 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
        {
          if ( !ppsaOut )
            goto LABEL_40;
          v6 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&ppsaOut);
          if ( LowerBound < v6 || LowerBound > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&ppsaOut) )
            break;
          WPP_SF_dS(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            98,
            LowerBound - v6,
            LowerBound,
            *((_QWORD *)ppsaOut->pvData + LowerBound - v6));
        }
        if ( !ppsaOut )
          goto LABEL_40;
        v7 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&ppsaOut);
        if ( LowerBound < v7 || LowerBound > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&ppsaOut) )
          break;
        if ( SysStringLen(*((BSTR *)ppsaOut->pvData + LowerBound - v7)) )
        {
          if ( !ppsaOut )
            goto LABEL_40;
          v8 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&ppsaOut);
          if ( LowerBound < v8 || LowerBound > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&ppsaOut) )
            break;
          v9 = (OLECHAR *)*((_QWORD *)ppsaOut->pvData + LowerBound - v8);
          if ( SysStringLen(v9) )
          {
            pbstrResult = 0;
            if ( VarBstrCat(v2, v9, &pbstrResult) >= 0 )
            {
              SysFreeString(v2);
              v19 = pbstrResult;
            }
          }
          ATL::CComBSTR::Append((ATL::CComBSTR *)&v19, v10, 1);
          v2 = v19;
        }
        if ( ++LowerBound >= v4 )
          goto LABEL_22;
      }
LABEL_39:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_22:
    if ( ppsaOut )
    {
      v11 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&ppsaOut);
      if ( v4 < v11 || v4 > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&ppsaOut) )
        goto LABEL_39;
      if ( !SysStringLen(*((BSTR *)ppsaOut->pvData + v4 - v11)) )
        goto LABEL_32;
      if ( ppsaOut )
      {
        v12 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&ppsaOut);
        if ( v4 < v12 || v4 > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&ppsaOut) )
          goto LABEL_39;
        v13 = (OLECHAR *)*((_QWORD *)ppsaOut->pvData + v4 - v12);
        if ( SysStringLen(v13) )
        {
          v19 = 0;
          if ( VarBstrCat(v2, v13, &v19) >= 0 )
          {
            SysFreeString(v2);
            v2 = v19;
          }
        }
LABEL_32:
        ATL::CComSafeArray<unsigned short *,8>::Destroy(&ppsaOut);
        goto LABEL_33;
      }
    }
LABEL_40:
    ATL::AtlThrowImpl(-2147467259);
  }
LABEL_33:
  VariantClear(&pvarg);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 99, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, v2);
  }
  if ( v3 >= 0 )
  {
    pvarg.vt = 0;
    VariantClear(&pvarg);
    pvarg.vt = 8;
    if ( v2 )
    {
      v15 = SysStringByteLen(v2);
      v14 = SysAllocStringByteLen((LPCSTR)v2, v15);
    }
    else
    {
      v14 = 0;
    }
    pvarg.llVal = (LONGLONG)v14;
    if ( !v14 && v2 )
    {
      pvarg.vt = 10;
      pvarg.lVal = -2147024882;
      ATL::AtlThrowImpl(-2147024882);
    }
    v3 = CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(L"ExcludedFileTypes", 0, a1, &pvarg, 34);
    VariantClear(&pvarg);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        100,
        WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
        (unsigned int)v3);
    }
  }
  SysFreeString(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001e4f8  push    rbp
0x18001e4fa  push    rbx
0x18001e4fb  push    rsi
0x18001e4fc  push    rdi
0x18001e4fd  push    r12
0x18001e4ff  push    r14
0x18001e501  push    r15
0x18001e503  mov     rbp, rsp
0x18001e506  sub     rsp, 60h
0x18001e50a  mov     r12, rcx
0x18001e50d  xor     ebx, ebx
0x18001e50f  lea     rcx, [rbp+pvarg]; pvarg
0x18001e513  mov     [rbp+arg_8], rbx
0x18001e517  call    cs:__imp_VariantInit
0x18001e51d  mov     rax, [r12]
0x18001e521  lea     r9, [rbp+pvarg]
0x18001e525  mov     [rsp+60h+var_38], rbx
0x18001e52a  lea     rdx, CSCWMI_STR_PROP_EXCLUDEDFILETYPES; "ExcludedFileTypes"
0x18001e531  xor     r8d, r8d
0x18001e534  mov     [rsp+60h+var_40], rbx
0x18001e539  mov     rcx, r12
0x18001e53c  mov     rax, [rax+20h]
0x18001e540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e545  lea     rdi, WPP_GLOBAL_Control
0x18001e54c  mov     r15d, eax
0x18001e54f  mov     r14d, 4000000h
0x18001e555  test    eax, eax
0x18001e557  js      loc_18001E7D7
0x18001e55d  mov     eax, 2008h
0x18001e562  cmp     word ptr [rbp+pvarg], ax
0x18001e566  jnz     loc_18001E7D7
0x18001e56c  mov     rdx, qword ptr [rbp+pvarg+8]; struct tagSAFEARRAY *
0x18001e570  lea     rcx, [rbp+ppsaOut]; ppsaOut
0x18001e574  call    ??0?$CComSafeArray@PEAG$07@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<ushort *,8>::CComSafeArray<ushort *,8>(tagSAFEARRAY const *)
0x18001e579  lea     rcx, [rbp+ppsaOut]
0x18001e57d  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x18001e582  lea     rcx, [rbp+ppsaOut]
0x18001e586  lea     esi, [rax-1]
0x18001e589  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001e58e  mov     edi, eax
0x18001e590  cmp     eax, esi
0x18001e592  jge     loc_18001E705
0x18001e598  mov     rax, cs:WPP_GLOBAL_Control
0x18001e59f  lea     rcx, WPP_GLOBAL_Control
0x18001e5a6  cmp     rax, rcx
0x18001e5a9  jz      short loc_18001E612
0x18001e5ab  test    [rax+1Ch], r14d
0x18001e5af  jz      short loc_18001E612
0x18001e5b1  cmp     [rbp+ppsaOut], 0
0x18001e5b6  jz      loc_18001E841
0x18001e5bc  lea     rcx, [rbp+ppsaOut]
0x18001e5c0  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001e5c5  mov     r14d, eax
0x18001e5c8  cmp     edi, eax
0x18001e5ca  jl      loc_18001E836
0x18001e5d0  lea     rcx, [rbp+ppsaOut]
0x18001e5d4  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001e5d9  cmp     edi, eax
0x18001e5db  jg      loc_18001E836
0x18001e5e1  mov     rax, [rbp+ppsaOut]
0x18001e5e5  mov     ecx, edi
0x18001e5e7  sub     ecx, r14d
0x18001e5ea  mov     edx, 62h ; 'b'
0x18001e5ef  movsxd  r8, ecx
0x18001e5f2  mov     r9d, edi
0x18001e5f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e5fc  mov     rax, [rax+10h]
0x18001e600  mov     rcx, [rcx+10h]
0x18001e604  mov     rax, [rax+r8*8]
0x18001e608  mov     [rsp+60h+var_40], rax
0x18001e60d  call    WPP_SF_dS
0x18001e612  cmp     [rbp+ppsaOut], 0
0x18001e617  jz      loc_18001E841
0x18001e61d  lea     rcx, [rbp+ppsaOut]
0x18001e621  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001e626  mov     r14d, eax
0x18001e629  cmp     edi, eax
0x18001e62b  jl      loc_18001E836
0x18001e631  lea     rcx, [rbp+ppsaOut]
0x18001e635  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001e63a  cmp     edi, eax
0x18001e63c  jg      loc_18001E836
0x18001e642  mov     rax, [rbp+ppsaOut]
0x18001e646  mov     ecx, edi
0x18001e648  sub     ecx, r14d
0x18001e64b  movsxd  rdx, ecx
0x18001e64e  mov     rcx, [rax+10h]
0x18001e652  mov     rcx, [rcx+rdx*8]; pbstr
0x18001e656  call    cs:__imp_SysStringLen
0x18001e65c  test    eax, eax
0x18001e65e  jz      loc_18001E6F5
0x18001e664  cmp     [rbp+ppsaOut], 0
0x18001e669  jz      loc_18001E841
0x18001e66f  lea     rcx, [rbp+ppsaOut]
0x18001e673  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001e678  mov     r14d, eax
0x18001e67b  cmp     edi, eax
0x18001e67d  jl      loc_18001E836
0x18001e683  lea     rcx, [rbp+ppsaOut]
0x18001e687  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001e68c  cmp     edi, eax
0x18001e68e  jg      loc_18001E836
0x18001e694  mov     rax, [rbp+ppsaOut]
0x18001e698  mov     ecx, edi
0x18001e69a  sub     ecx, r14d
0x18001e69d  movsxd  rdx, ecx
0x18001e6a0  mov     rcx, [rax+10h]
0x18001e6a4  mov     r14, [rcx+rdx*8]
0x18001e6a8  mov     rcx, r14; pbstr
0x18001e6ab  call    cs:__imp_SysStringLen
0x18001e6b1  test    eax, eax
0x18001e6b3  jz      short loc_18001E6E2
0x18001e6b5  lea     r8, [rbp+pbstrResult]; pbstrResult
0x18001e6b9  mov     [rbp+pbstrResult], 0
0x18001e6c1  mov     rdx, r14; bstrRight
0x18001e6c4  mov     rcx, rbx; bstrLeft
0x18001e6c7  call    cs:__imp_VarBstrCat
0x18001e6cd  test    eax, eax
0x18001e6cf  js      short loc_18001E6E2
0x18001e6d1  mov     rcx, rbx; bstrString
0x18001e6d4  call    cs:__imp_SysFreeString
0x18001e6da  mov     rax, [rbp+pbstrResult]
0x18001e6de  mov     [rbp+arg_8], rax
0x18001e6e2  mov     r8d, 1; int
0x18001e6e8  lea     rcx, [rbp+arg_8]; this
0x18001e6ec  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18001e6f1  mov     rbx, [rbp+arg_8]
0x18001e6f5  inc     edi
0x18001e6f7  mov     r14d, 4000000h
0x18001e6fd  cmp     edi, esi
0x18001e6ff  jl      loc_18001E598
0x18001e705  cmp     [rbp+ppsaOut], 0
0x18001e70a  jz      loc_18001E841
0x18001e710  lea     rcx, [rbp+ppsaOut]
0x18001e714  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001e719  mov     edi, eax
0x18001e71b  cmp     esi, eax
0x18001e71d  jl      loc_18001E836
0x18001e723  lea     rcx, [rbp+ppsaOut]
0x18001e727  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001e72c  cmp     esi, eax
0x18001e72e  jg      loc_18001E836
0x18001e734  mov     rax, [rbp+ppsaOut]
0x18001e738  mov     ecx, esi
0x18001e73a  sub     ecx, edi
0x18001e73c  movsxd  rdx, ecx
0x18001e73f  mov     rcx, [rax+10h]
0x18001e743  mov     rcx, [rcx+rdx*8]; pbstr
0x18001e747  call    cs:__imp_SysStringLen
0x18001e74d  test    eax, eax
0x18001e74f  jz      short loc_18001E7C7
0x18001e751  cmp     [rbp+ppsaOut], 0
0x18001e756  jz      loc_18001E841
0x18001e75c  lea     rcx, [rbp+ppsaOut]
0x18001e760  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001e765  mov     edi, eax
0x18001e767  cmp     esi, eax
0x18001e769  jl      loc_18001E836
0x18001e76f  lea     rcx, [rbp+ppsaOut]
0x18001e773  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001e778  cmp     esi, eax
0x18001e77a  jg      loc_18001E836
0x18001e780  mov     rax, [rbp+ppsaOut]
0x18001e784  sub     esi, edi
0x18001e786  movsxd  rdx, esi
0x18001e789  mov     rcx, [rax+10h]
0x18001e78d  mov     rdi, [rcx+rdx*8]
0x18001e791  mov     rcx, rdi; pbstr
0x18001e794  call    cs:__imp_SysStringLen
0x18001e79a  test    eax, eax
0x18001e79c  jz      short loc_18001E7C7
0x18001e79e  lea     r8, [rbp+arg_8]; pbstrResult
0x18001e7a2  mov     [rbp+arg_8], 0
0x18001e7aa  mov     rdx, rdi; bstrRight
0x18001e7ad  mov     rcx, rbx; bstrLeft
0x18001e7b0  call    cs:__imp_VarBstrCat
0x18001e7b6  test    eax, eax
0x18001e7b8  js      short loc_18001E7C7
0x18001e7ba  mov     rcx, rbx; bstrString
0x18001e7bd  call    cs:__imp_SysFreeString
0x18001e7c3  mov     rbx, [rbp+arg_8]
0x18001e7c7  lea     rcx, [rbp+ppsaOut]
0x18001e7cb  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18001e7d0  lea     rdi, WPP_GLOBAL_Control
0x18001e7d7  lea     rcx, [rbp+pvarg]; pvarg
0x18001e7db  call    cs:__imp_VariantClear
0x18001e7e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e7e8  cmp     rcx, rdi
0x18001e7eb  jz      short loc_18001E80B
0x18001e7ed  test    [rcx+1Ch], r14d
0x18001e7f1  jz      short loc_18001E80B
0x18001e7f3  mov     rcx, [rcx+10h]
0x18001e7f7  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001e7fe  mov     edx, 63h ; 'c'
0x18001e803  mov     r9, rbx
0x18001e806  call    WPP_SF_S
0x18001e80b  test    r15d, r15d
0x18001e80e  js      loc_18001E8E2
0x18001e814  xor     eax, eax
0x18001e816  lea     rcx, [rbp+pvarg]; pvarg
0x18001e81a  mov     word ptr [rbp+pvarg], ax
0x18001e81e  call    cs:__imp_VariantClear
0x18001e824  mov     eax, 8
0x18001e829  mov     word ptr [rbp+pvarg], ax
0x18001e82d  test    rbx, rbx
0x18001e830  jnz     short loc_18001E84C
0x18001e832  xor     eax, eax
0x18001e834  jmp     short loc_18001E860
0x18001e836  mov     ecx, 80070057h; int
0x18001e83b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e841  mov     ecx, 80004005h; int
0x18001e846  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e84c  mov     rcx, rbx; bstr
0x18001e84f  call    cs:__imp_SysStringByteLen
0x18001e855  mov     edx, eax; len
0x18001e857  mov     rcx, rbx; psz
0x18001e85a  call    cs:__imp_SysAllocStringByteLen
0x18001e860  mov     rcx, rax
0x18001e863  mov     dword ptr [rbp+pvarg+8], eax
0x18001e866  sar     rcx, 20h
0x18001e86a  mov     dword ptr [rbp+pvarg+0Ch], ecx
0x18001e86d  test    rax, rax
0x18001e870  jnz     short loc_18001E88E
0x18001e872  test    rbx, rbx
0x18001e875  jz      short loc_18001E88E
0x18001e877  mov     eax, 0Ah
0x18001e87c  mov     ecx, 8007000Eh; int
0x18001e881  mov     word ptr [rbp+pvarg], ax
0x18001e885  mov     dword ptr [rbp+pvarg+8], ecx
0x18001e888  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e88e  lea     r9, [rbp+pvarg]
0x18001e892  mov     dword ptr [rsp+60h+var_40], 22h ; '"'
0x18001e89a  mov     r8, r12
0x18001e89d  lea     rcx, CSCWMI_STR_PROP_EXCLUDEDFILETYPES; "ExcludedFileTypes"
0x18001e8a4  xor     edx, edx
0x18001e8a6  call    ?UpdateOrRemoveWMIObjectProperty@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@AEBVCComVariant@ATL@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(ushort const *,void *,IWbemClassObject *,ATL::CComVariant const &,USERSTATE_SETTING_SOURCES)
0x18001e8ab  lea     rcx, [rbp+pvarg]; pvarg
0x18001e8af  mov     r15d, eax
0x18001e8b2  call    cs:__imp_VariantClear
0x18001e8b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e8bf  cmp     rcx, rdi
0x18001e8c2  jz      short loc_18001E8E2
0x18001e8c4  test    [rcx+1Ch], r14d
0x18001e8c8  jz      short loc_18001E8E2
0x18001e8ca  mov     rcx, [rcx+10h]
0x18001e8ce  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001e8d5  mov     edx, 64h ; 'd'
0x18001e8da  mov     r9d, r15d
0x18001e8dd  call    WPP_SF_d
0x18001e8e2  mov     rcx, rbx; bstrString
0x18001e8e5  call    cs:__imp_SysFreeString
0x18001e8eb  mov     eax, r15d
0x18001e8ee  add     rsp, 60h
0x18001e8f2  pop     r15
0x18001e8f4  pop     r14
0x18001e8f6  pop     r12
0x18001e8f8  pop     rdi
0x18001e8f9  pop     rsi
0x18001e8fa  pop     rbx
0x18001e8fb  pop     rbp
0x18001e8fc  retn
```
