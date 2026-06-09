# CSCWmiConfig::UpdateOrRemoveWMIAssignedOfflineFilesProperty(IWbemClassObject *,void *,USERSTATE_SETTING_SOURCES)

- ea: `0x18001e100`
- end: `0x18001e4f1`
- name: `?UpdateOrRemoveWMIAssignedOfflineFilesProperty@CSCWmiConfig@@YAJPEAUIWbemClassObject@@PEAXW4USERSTATE_SETTING_SOURCES@@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001fdb0`

## callees

- `0x1800186c0`
- `0x18001886c`
- `0x18001957c`
- `0x18001c7bc`
- `0x18001c8c8`
- `0x18001ca10`
- `0x18001cbf0`
- `0x18001cda0`
- `0x18001d74c`
- `0x18001d8e4`
- `0x18001d954`
- `0x18001d9d8`
- `0x18001e100`
- `0x18001e904`
- `0x1800224c4`
- `0x18002c010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18001e273`
- `OLEAUT32!__imp_SysStringLen` at `0x18001e273`
- `OLEAUT32!__imp_VariantInit` at `0x18001e13f`
- `OLEAUT32!__imp_VariantInit` at `0x18001e13f`
- `OLEAUT32!__imp_VariantClear` at `0x18001e2e7`
- `OLEAUT32!__imp_VariantClear` at `0x18001e389`
- `OLEAUT32!__imp_VariantClear` at `0x18001e3f6`
- `OLEAUT32!__imp_VariantClear` at `0x18001e41a`
- `OLEAUT32!__imp_VariantClear` at `0x18001e48f`
- `OLEAUT32!__imp_VariantClear` at `0x18001e4c9`
- `OLEAUT32!__imp_VariantClear` at `0x18001e2e7`
- `OLEAUT32!__imp_VariantClear` at `0x18001e389`
- `OLEAUT32!__imp_VariantClear` at `0x18001e3f6`
- `OLEAUT32!__imp_VariantClear` at `0x18001e41a`
- `OLEAUT32!__imp_VariantClear` at `0x18001e48f`
- `OLEAUT32!__imp_VariantClear` at `0x18001e4c9`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001e303`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001e303`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001e30f`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001e30f`

## pseudocode

```c
__int64 __fastcall CSCWmiConfig::UpdateOrRemoveWMIAssignedOfflineFilesProperty(__int64 a1, __int64 a2)
{
  int v4; // ebx
  int i; // edi
  int LowerBound; // esi
  int v7; // esi
  int v8; // ebx
  __int64 v9; // rbx
  _QWORD *pvData; // rsi
  OLECHAR *v11; // rcx
  BSTR v12; // rax
  UINT v13; // eax
  struct tagSAFEARRAY *v14; // rbx
  int v15; // esi
  VARIANTARG *v16; // rcx
  int v17; // esi
  VARIANTARG *v18; // rcx
  ATL::CComVariant *v19; // rax
  ATL::CComVariant *v20; // rax
  __int64 v22; // [rsp+40h] [rbp-49h] BYREF
  struct tagSAFEARRAY *v23; // [rsp+48h] [rbp-41h] BYREF
  VARIANTARG v24; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v25[4]; // [rsp+68h] [rbp-21h] BYREF
  int v26; // [rsp+6Ch] [rbp-1Dh]
  VARIANTARG v27; // [rsp+70h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-1h] BYREF
  VARIANTARG v29; // [rsp+A0h] [rbp+17h] BYREF
  SAFEARRAY *ppsaOut; // [rsp+F0h] [rbp+67h] BYREF
  struct tagSAFEARRAY *v31; // [rsp+108h] [rbp+7Fh] BYREF

  ATL::CComSafeArrayBound::`default constructor closure'((ATL::CComSafeArrayBound *)v25);
  v26 = 0;
  ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(&v23, v25);
  VariantInit(&pvarg);
  v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)a1 + 32LL))(
         a1,
         L"AssignedOfflineFiles",
         0,
         &pvarg,
         0,
         0);
  if ( v4 >= 0 && pvarg.vt == 8200 )
  {
    ATL::CComSafeArray<unsigned short *,8>::CComSafeArray<unsigned short *,8>(&ppsaOut, pvarg.parray);
    for ( i = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&ppsaOut);
          i < (unsigned int)ATL::CComSafeArray<unsigned short *,8>::GetCount(&ppsaOut);
          ++i )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
      {
        if ( !ppsaOut )
          goto LABEL_39;
        LowerBound = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&ppsaOut);
        if ( i < LowerBound || i > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&ppsaOut) )
          goto LABEL_38;
        WPP_SF_dS(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          80,
          i - LowerBound,
          i,
          *((_QWORD *)ppsaOut->pvData + i - LowerBound));
      }
      if ( !ppsaOut )
LABEL_39:
        ATL::AtlThrowImpl(-2147467259);
      v7 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&ppsaOut);
      if ( i < v7 || i > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&ppsaOut) )
LABEL_38:
        ATL::AtlThrowImpl(-2147024809);
      if ( SysStringLen(*((BSTR *)ppsaOut->pvData + i - v7)) )
      {
        ATL::CComSafeArrayBound::`default constructor closure'((ATL::CComSafeArrayBound *)&v22);
        v22 = 2;
        ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(&v31, &v22);
        if ( !ppsaOut )
          goto LABEL_37;
        v8 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&ppsaOut);
        if ( i < v8 || i > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&ppsaOut) )
          goto LABEL_36;
        v9 = i - v8;
        pvData = ppsaOut->pvData;
        v24.vt = 0;
        VariantClear(&v24);
        v24.vt = 8;
        v11 = (OLECHAR *)pvData[v9];
        if ( v11 )
        {
          v13 = SysStringByteLen(v11);
          v12 = SysAllocStringByteLen((LPCSTR)pvData[v9], v13);
        }
        else
        {
          v12 = 0;
        }
        v24.llVal = (LONGLONG)v12;
        if ( !v12 && pvData[v9] )
        {
          v24.vt = 10;
          v24.lVal = -2147024882;
          ATL::AtlThrowImpl(-2147024882);
        }
        v14 = v31;
        if ( !v31 )
LABEL_37:
          ATL::AtlThrowImpl(-2147467259);
        v15 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v31);
        if ( v15 > 0 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v31) < 0 )
LABEL_36:
          ATL::AtlThrowImpl(-2147024809);
        v16 = (VARIANTARG *)((char *)v14->pvData - 24 * v15);
        if ( v16 != &v24 )
          ATL::CComVariant::InternalCopy(v16, &v24);
        VariantClear(&v24);
        v27.vt = 0;
        ATL::CComVariant::operator=(&v27, &qword_18003ADA8);
        v17 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v31);
        if ( v17 > 1 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v31) < 1 )
          ATL::AtlThrowImpl(-2147024809);
        v18 = (VARIANTARG *)((char *)v14->pvData + 24 * (1 - v17));
        if ( v18 != &v27 )
          ATL::CComVariant::InternalCopy(v18, &v27);
        VariantClear(&v27);
        v19 = ATL::CComVariant::CComVariant((ATL::CComVariant *)&v29, v14);
        v4 = ATL::CComSafeArray<tagVARIANT,12>::Add(&v23, v19);
        VariantClear(&v29);
        ATL::CComSafeArray<unsigned short *,8>::Destroy(&v31);
        if ( v4 < 0 )
          break;
      }
    }
    ATL::CComSafeArray<unsigned short *,8>::Destroy(&ppsaOut);
  }
  VariantClear(&pvarg);
  if ( v4 >= 0 )
  {
    v20 = ATL::CComVariant::CComVariant((ATL::CComVariant *)&v29, v23);
    v4 = CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(L"AssignedOfflineFiles", a2, a1, v20, 33);
    VariantClear(&v29);
  }
  ATL::CComSafeArray<unsigned short *,8>::Destroy(&v23);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001e100  mov     [rsp-8+arg_8], rbx
0x18001e105  push    rbp
0x18001e106  push    rsi
0x18001e107  push    rdi
0x18001e108  push    r14
0x18001e10a  push    r15
0x18001e10c  lea     rbp, [rsp-37h]
0x18001e111  sub     rsp, 0C0h
0x18001e118  mov     r14, rcx
0x18001e11b  mov     r15, rdx
0x18001e11e  lea     rcx, [rbp+57h+var_78]; this
0x18001e122  call    ??_FCComSafeArrayBound@ATL@@QEAAXXZ; ATL::CComSafeArrayBound::`default constructor closure'(void)
0x18001e127  lea     rdx, [rbp+57h+var_78]
0x18001e12b  mov     [rbp+57h+var_74], 0
0x18001e132  lea     rcx, [rbp+57h+var_98]
0x18001e136  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAYBOUND const *,uint)
0x18001e13b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001e13f  call    cs:__imp_VariantInit
0x18001e145  mov     rax, [r14]
0x18001e148  lea     r9, [rbp+57h+pvarg]
0x18001e14c  mov     [rsp+0E0h+var_B8], 0
0x18001e155  lea     rdx, CSCWMI_STR_PROP_ASSIGNEDOFFLINEFILES; "AssignedOfflineFiles"
0x18001e15c  xor     r8d, r8d
0x18001e15f  mov     [rsp+0E0h+var_C0], 0
0x18001e168  mov     rcx, r14
0x18001e16b  mov     rax, [rax+20h]
0x18001e16f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e174  mov     ebx, eax
0x18001e176  test    eax, eax
0x18001e178  js      loc_18001E48B
0x18001e17e  mov     eax, 2008h
0x18001e183  cmp     word ptr [rbp+57h+pvarg], ax
0x18001e187  jnz     loc_18001E48B
0x18001e18d  mov     rdx, qword ptr [rbp+57h+pvarg+8]; struct tagSAFEARRAY *
0x18001e191  lea     rcx, [rbp+57h+ppsaOut]; ppsaOut
0x18001e195  call    ??0?$CComSafeArray@PEAG$07@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<ushort *,8>::CComSafeArray<ushort *,8>(tagSAFEARRAY const *)
0x18001e19a  lea     rcx, [rbp+57h+ppsaOut]
0x18001e19e  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001e1a3  mov     edi, eax
0x18001e1a5  lea     rcx, [rbp+57h+ppsaOut]
0x18001e1a9  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x18001e1ae  cmp     edi, eax
0x18001e1b0  jnb     loc_18001E482
0x18001e1b6  mov     rax, cs:WPP_GLOBAL_Control
0x18001e1bd  lea     rcx, WPP_GLOBAL_Control
0x18001e1c4  cmp     rax, rcx
0x18001e1c7  jz      short loc_18001E231
0x18001e1c9  test    dword ptr [rax+1Ch], 4000000h
0x18001e1d0  jz      short loc_18001E231
0x18001e1d2  cmp     [rbp+57h+ppsaOut], 0
0x18001e1d7  jz      loc_18001E477
0x18001e1dd  lea     rcx, [rbp+57h+ppsaOut]
0x18001e1e1  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001e1e6  mov     esi, eax
0x18001e1e8  cmp     edi, eax
0x18001e1ea  jl      loc_18001E46C
0x18001e1f0  lea     rcx, [rbp+57h+ppsaOut]
0x18001e1f4  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001e1f9  cmp     edi, eax
0x18001e1fb  jg      loc_18001E46C
0x18001e201  mov     rax, [rbp+57h+ppsaOut]
0x18001e205  mov     ecx, edi
0x18001e207  sub     ecx, esi
0x18001e209  mov     edx, 50h ; 'P'
0x18001e20e  movsxd  r8, ecx
0x18001e211  mov     r9d, edi
0x18001e214  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e21b  mov     rax, [rax+10h]
0x18001e21f  mov     rcx, [rcx+10h]
0x18001e223  mov     rax, [rax+r8*8]
0x18001e227  mov     [rsp+0E0h+var_C0], rax
0x18001e22c  call    WPP_SF_dS
0x18001e231  cmp     [rbp+57h+ppsaOut], 0
0x18001e236  jz      loc_18001E477
0x18001e23c  lea     rcx, [rbp+57h+ppsaOut]
0x18001e240  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001e245  mov     esi, eax
0x18001e247  cmp     edi, eax
0x18001e249  jl      loc_18001E46C
0x18001e24f  lea     rcx, [rbp+57h+ppsaOut]
0x18001e253  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001e258  cmp     edi, eax
0x18001e25a  jg      loc_18001E46C
0x18001e260  mov     rax, [rbp+57h+ppsaOut]
0x18001e264  mov     ecx, edi
0x18001e266  sub     ecx, esi
0x18001e268  movsxd  rdx, ecx
0x18001e26b  mov     rcx, [rax+10h]
0x18001e26f  mov     rcx, [rcx+rdx*8]; pbstr
0x18001e273  call    cs:__imp_SysStringLen
0x18001e279  test    eax, eax
0x18001e27b  jz      loc_18001E42D
0x18001e281  lea     rcx, [rbp+57h+var_A0]; this
0x18001e285  call    ??_FCComSafeArrayBound@ATL@@QEAAXXZ; ATL::CComSafeArrayBound::`default constructor closure'(void)
0x18001e28a  lea     rdx, [rbp+57h+var_A0]
0x18001e28e  mov     [rbp+57h+var_A0], 2
0x18001e296  lea     rcx, [rbp+57h+arg_18]
0x18001e29a  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAYBOUND const *,uint)
0x18001e29f  cmp     [rbp+57h+ppsaOut], 0
0x18001e2a4  jz      loc_18001E461
0x18001e2aa  lea     rcx, [rbp+57h+ppsaOut]
0x18001e2ae  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001e2b3  mov     ebx, eax
0x18001e2b5  cmp     edi, eax
0x18001e2b7  jl      loc_18001E456
0x18001e2bd  lea     rcx, [rbp+57h+ppsaOut]
0x18001e2c1  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001e2c6  cmp     edi, eax
0x18001e2c8  jg      loc_18001E456
0x18001e2ce  mov     rax, [rbp+57h+ppsaOut]
0x18001e2d2  mov     ecx, edi
0x18001e2d4  sub     ecx, ebx
0x18001e2d6  movsxd  rbx, ecx
0x18001e2d9  lea     rcx, [rbp+57h+var_90]; pvarg
0x18001e2dd  mov     rsi, [rax+10h]
0x18001e2e1  xor     eax, eax
0x18001e2e3  mov     word ptr [rbp+57h+var_90], ax
0x18001e2e7  call    cs:__imp_VariantClear
0x18001e2ed  mov     eax, 8
0x18001e2f2  mov     word ptr [rbp+57h+var_90], ax
0x18001e2f6  mov     rcx, [rsi+rbx*8]; bstr
0x18001e2fa  test    rcx, rcx
0x18001e2fd  jnz     short loc_18001E303
0x18001e2ff  xor     eax, eax
0x18001e301  jmp     short loc_18001E315
0x18001e303  call    cs:__imp_SysStringByteLen
0x18001e309  mov     rcx, [rsi+rbx*8]; psz
0x18001e30d  mov     edx, eax; len
0x18001e30f  call    cs:__imp_SysAllocStringByteLen
0x18001e315  mov     rcx, rax
0x18001e318  mov     dword ptr [rbp+57h+var_90+8], eax
0x18001e31b  sar     rcx, 20h
0x18001e31f  mov     dword ptr [rbp+57h+var_90+0Ch], ecx
0x18001e322  test    rax, rax
0x18001e325  jnz     short loc_18001E331
0x18001e327  cmp     [rsi+rbx*8], rax
0x18001e32b  jnz     loc_18001E434
0x18001e331  mov     rbx, [rbp+57h+arg_18]
0x18001e335  test    rbx, rbx
0x18001e338  jz      loc_18001E461
0x18001e33e  lea     rcx, [rbp+57h+arg_18]
0x18001e342  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001e347  mov     esi, eax
0x18001e349  test    eax, eax
0x18001e34b  jg      loc_18001E456
0x18001e351  lea     rcx, [rbp+57h+arg_18]
0x18001e355  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001e35a  test    eax, eax
0x18001e35c  js      loc_18001E456
0x18001e362  neg     esi
0x18001e364  movsxd  rax, esi
0x18001e367  lea     rcx, [rax+rax*2]
0x18001e36b  mov     rax, [rbx+10h]
0x18001e36f  lea     rcx, [rax+rcx*8]; this
0x18001e373  lea     rax, [rbp+57h+var_90]
0x18001e377  cmp     rcx, rax
0x18001e37a  jz      short loc_18001E385
0x18001e37c  lea     rdx, [rbp+57h+var_90]; struct tagVARIANT *
0x18001e380  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x18001e385  lea     rcx, [rbp+57h+var_90]; pvarg
0x18001e389  call    cs:__imp_VariantClear
0x18001e38f  xor     eax, eax
0x18001e391  lea     rdx, qword_18003ADA8
0x18001e398  lea     rcx, [rbp+57h+var_70]
0x18001e39c  mov     word ptr [rbp+57h+var_70], ax
0x18001e3a0  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x18001e3a5  lea     rcx, [rbp+57h+arg_18]
0x18001e3a9  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001e3ae  mov     esi, eax
0x18001e3b0  cmp     eax, 1
0x18001e3b3  jg      loc_18001E44B
0x18001e3b9  lea     rcx, [rbp+57h+arg_18]
0x18001e3bd  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001e3c2  cmp     eax, 1
0x18001e3c5  jl      loc_18001E44B
0x18001e3cb  mov     eax, 1
0x18001e3d0  sub     eax, esi
0x18001e3d2  cdqe
0x18001e3d4  lea     rcx, [rax+rax*2]
0x18001e3d8  mov     rax, [rbx+10h]
0x18001e3dc  lea     rcx, [rax+rcx*8]; this
0x18001e3e0  lea     rax, [rbp+57h+var_70]
0x18001e3e4  cmp     rcx, rax
0x18001e3e7  jz      short loc_18001E3F2
0x18001e3e9  lea     rdx, [rbp+57h+var_70]; struct tagVARIANT *
0x18001e3ed  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x18001e3f2  lea     rcx, [rbp+57h+var_70]; pvarg
0x18001e3f6  call    cs:__imp_VariantClear
0x18001e3fc  mov     rdx, rbx; struct tagSAFEARRAY *
0x18001e3ff  lea     rcx, [rbp+57h+var_40]; this
0x18001e403  call    ??0CComVariant@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComVariant::CComVariant(tagSAFEARRAY const *)
0x18001e408  mov     rdx, rax
0x18001e40b  lea     rcx, [rbp+57h+var_98]
0x18001e40f  call    ?Add@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::Add(tagVARIANT const &,int)
0x18001e414  lea     rcx, [rbp+57h+var_40]; pvarg
0x18001e418  mov     ebx, eax
0x18001e41a  call    cs:__imp_VariantClear
0x18001e420  lea     rcx, [rbp+57h+arg_18]
0x18001e424  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18001e429  test    ebx, ebx
0x18001e42b  js      short loc_18001E482
0x18001e42d  inc     edi
0x18001e42f  jmp     loc_18001E1A5
0x18001e434  mov     eax, 0Ah
0x18001e439  mov     ecx, 8007000Eh; int
0x18001e43e  mov     word ptr [rbp+57h+var_90], ax
0x18001e442  mov     dword ptr [rbp+57h+var_90+8], ecx
0x18001e445  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e44b  mov     ecx, 80070057h; int
0x18001e450  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e456  mov     ecx, 80070057h; int
0x18001e45b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e461  mov     ecx, 80004005h; int
0x18001e466  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e46c  mov     ecx, 80070057h; int
0x18001e471  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e477  mov     ecx, 80004005h; int
0x18001e47c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e482  lea     rcx, [rbp+57h+ppsaOut]
0x18001e486  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18001e48b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001e48f  call    cs:__imp_VariantClear
0x18001e495  test    ebx, ebx
0x18001e497  js      short loc_18001E4CF
0x18001e499  mov     rdx, [rbp+57h+var_98]; struct tagSAFEARRAY *
0x18001e49d  lea     rcx, [rbp+57h+var_40]; this
0x18001e4a1  call    ??0CComVariant@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComVariant::CComVariant(tagSAFEARRAY const *)
0x18001e4a6  mov     r9, rax
0x18001e4a9  mov     dword ptr [rsp+0E0h+var_C0], 21h ; '!'
0x18001e4b1  mov     r8, r14
0x18001e4b4  lea     rcx, CSCWMI_STR_PROP_ASSIGNEDOFFLINEFILES; "AssignedOfflineFiles"
0x18001e4bb  mov     rdx, r15
0x18001e4be  call    ?UpdateOrRemoveWMIObjectProperty@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@AEBVCComVariant@ATL@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateOrRemoveWMIObjectProperty(ushort const *,void *,IWbemClassObject *,ATL::CComVariant const &,USERSTATE_SETTING_SOURCES)
0x18001e4c3  lea     rcx, [rbp+57h+var_40]; pvarg
0x18001e4c7  mov     ebx, eax
0x18001e4c9  call    cs:__imp_VariantClear
0x18001e4cf  lea     rcx, [rbp+57h+var_98]
0x18001e4d3  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18001e4d8  mov     eax, ebx
0x18001e4da  mov     rbx, [rsp+0E0h+arg_8]
0x18001e4e2  add     rsp, 0C0h
0x18001e4e9  pop     r15
0x18001e4eb  pop     r14
0x18001e4ed  pop     rdi
0x18001e4ee  pop     rsi
0x18001e4ef  pop     rbp
0x18001e4f0  retn
```
