# CommonUnenrollCsp(ushort const *,ushort const *,ushort const *,ushort const *,int,int)

- ea: `0x18004e6c8`
- end: `0x18004ea4d`
- name: `?CommonUnenrollCsp@@YAJPEBG000HH@Z`
- size: `901`
- prototype: `__int64 __fastcall(OLECHAR *psz, OLECHAR *, OLECHAR *, const unsigned __int16 *, int, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006e7c0`
- `0x18006f590`
- `0x18006f680`

## callees

- `0x1800140d0`
- `0x180044b78`
- `0x18004e4b8`
- `0x18004e6c8`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e7a6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e91e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e7a6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e91e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004ea13`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004ea13`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18004e774`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18004e774`
- `OLEAUT32!__imp_SysAllocString` at `0x18004e7c0`
- `OLEAUT32!__imp_SysAllocString` at `0x18004e834`
- `OLEAUT32!__imp_SysAllocString` at `0x18004e8a3`
- `OLEAUT32!__imp_SysAllocString` at `0x18004e7c0`
- `OLEAUT32!__imp_SysAllocString` at `0x18004e834`
- `OLEAUT32!__imp_SysAllocString` at `0x18004e8a3`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ea29`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ea29`
- `OLEAUT32!__imp_VariantInit` at `0x18004e732`
- `OLEAUT32!__imp_VariantInit` at `0x18004e73c`
- `OLEAUT32!__imp_VariantInit` at `0x18004e746`
- `OLEAUT32!__imp_VariantInit` at `0x18004e732`
- `OLEAUT32!__imp_VariantInit` at `0x18004e73c`
- `OLEAUT32!__imp_VariantInit` at `0x18004e746`
- `OLEAUT32!__imp_VariantClear` at `0x18004e99d`
- `OLEAUT32!__imp_VariantClear` at `0x18004e9a7`
- `OLEAUT32!__imp_VariantClear` at `0x18004e9b1`
- `OLEAUT32!__imp_VariantClear` at `0x18004e99d`
- `OLEAUT32!__imp_VariantClear` at `0x18004e9a7`
- `OLEAUT32!__imp_VariantClear` at `0x18004e9b1`

## string_xrefs

- `0x18004e8ba`: `OMADM::TargetedUserSID`
- `0x18004e74c`: `CommonUnenrollCsp`

## pseudocode

```c
__int64 __fastcall CommonUnenrollCsp(
        OLECHAR *psz,
        OLECHAR *a2,
        OLECHAR *a3,
        const unsigned __int16 *a4,
        int a5,
        int a6)
{
  OLECHAR *v10; // rbx
  char v11; // di
  __int64 v12; // rdx
  unsigned int v13; // edi
  struct IConfigManager2 *ppv; // [rsp+30h] [rbp-79h] BYREF
  BSTR v16; // [rsp+38h] [rbp-71h] BYREF
  LPVOID v17; // [rsp+40h] [rbp-69h] BYREF
  struct IConfigManager2URI *v18; // [rsp+48h] [rbp-61h] BYREF
  VARIANTARG v19; // [rsp+50h] [rbp-59h] BYREF
  VARIANTARG v20; // [rsp+70h] [rbp-39h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-21h] BYREF
  VARIANTARG v22; // [rsp+A0h] [rbp-9h] BYREF
  _QWORD v23[3]; // [rsp+B8h] [rbp+Fh] BYREF
  HRESULT Instance; // [rsp+108h] [rbp+5Fh] BYREF

  Instance = 0;
  v10 = 0;
  v16 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v22, 0, sizeof(v22));
  memset(&v20, 0, sizeof(v20));
  v11 = 0;
  ppv = 0;
  v17 = 0;
  v18 = 0;
  VariantInit(&pvarg);
  VariantInit(&v22);
  VariantInit(&v20);
  v23[0] = "CommonUnenrollCsp";
  v23[1] = &Instance;
  if ( !a2 )
  {
    Instance = -2147418113;
    goto LABEL_21;
  }
  Instance = CoInitializeEx(0, 0);
  if ( Instance >= 0 )
  {
    v11 = 1;
    Instance = CoCreateInstance(
                 &GUID_66d0db14_5638_475f_a386_629522d8c461,
                 0,
                 1u,
                 &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
                 (LPVOID *)&ppv);
    if ( Instance >= 0 )
    {
      if ( !a6 )
        goto LABEL_32;
      pvarg.llVal = (LONGLONG)SysAllocString(a2);
      if ( !pvarg.llVal )
      {
LABEL_7:
        Instance = -2147024882;
        goto LABEL_21;
      }
      pvarg.vt = 8;
      ATL::CComBSTR::operator=(&v16, L"OMADM::ServerID");
      v19 = pvarg;
      v10 = v16;
      Instance = (*(__int64 (__fastcall **)(struct IConfigManager2 *, BSTR, VARIANTARG *))(*(_QWORD *)ppv + 104LL))(
                   ppv,
                   v16,
                   &v19);
      if ( Instance >= 0 )
      {
LABEL_32:
        if ( !psz )
          goto LABEL_33;
        v22.llVal = (LONGLONG)SysAllocString(psz);
        if ( !v22.llVal )
          goto LABEL_7;
        v22.vt = 8;
        ATL::CComBSTR::operator=(&v16, L"OMADM::AccountID");
        v19 = v22;
        v10 = v16;
        Instance = (*(__int64 (__fastcall **)(struct IConfigManager2 *, BSTR, VARIANTARG *))(*(_QWORD *)ppv + 104LL))(
                     ppv,
                     v16,
                     &v19);
        if ( Instance >= 0 )
        {
LABEL_33:
          if ( !a3 )
            goto LABEL_15;
          v20.llVal = (LONGLONG)SysAllocString(a3);
          if ( !v20.llVal )
            goto LABEL_7;
          v20.vt = 8;
          ATL::CComBSTR::operator=(&v16, L"OMADM::TargetedUserSID");
          v19 = v20;
          v10 = v16;
          Instance = (*(__int64 (__fastcall **)(struct IConfigManager2 *, BSTR, VARIANTARG *))(*(_QWORD *)ppv + 104LL))(
                       ppv,
                       v16,
                       &v19);
          if ( Instance >= 0 )
          {
LABEL_15:
            Instance = CoCreateInstance(
                         &GUID_c196b2be_ba06_4049_8518_322e1e04282b,
                         0,
                         1u,
                         &GUID_4b965405_f21f_4702_95dd_4e81c3d1bb30,
                         &v17);
            if ( Instance >= 0 )
            {
              Instance = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *))(*(_QWORD *)v17 + 40LL))(v17, a4);
              if ( Instance >= 0 )
              {
                if ( !a5
                  || (Instance = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, _QWORD))(*(_QWORD *)v17 + 176LL))(
                                   v17,
                                   a2,
                                   0),
                      Instance >= 0) )
                {
                  Instance = (*(__int64 (__fastcall **)(LPVOID, struct IConfigManager2URI **))(*(_QWORD *)v17 + 224LL))(
                               v17,
                               &v18);
                  if ( Instance >= 0 )
                    Instance = DeleteUri(ppv, v18);
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_21:
  VariantClear(&v20);
  VariantClear(&pvarg);
  VariantClear(&v22);
  if ( ppv )
  {
    (*(void (__fastcall **)(struct IConfigManager2 *))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v11 )
    CoUninitialize();
  v13 = Instance;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v23, v12);
  SysFreeString(v10);
  return v13;
}

```

## disassembly

```asm
0x18004e6c8  mov     [rsp-8+arg_0], rbx
0x18004e6cd  mov     [rsp-8+arg_10], rsi
0x18004e6d2  push    rbp
0x18004e6d3  push    rdi
0x18004e6d4  push    r12
0x18004e6d6  push    r14
0x18004e6d8  push    r15
0x18004e6da  lea     rbp, [rsp-27h]
0x18004e6df  sub     rsp, 0D0h
0x18004e6e6  mov     r12, r9
0x18004e6e9  mov     r14, r8
0x18004e6ec  mov     r15, rdx
0x18004e6ef  mov     rsi, rcx
0x18004e6f2  mov     [rbp+47h+arg_8], 0
0x18004e6f9  xor     ebx, ebx
0x18004e6fb  mov     [rbp+47h+var_B8], rbx
0x18004e6ff  xorps   xmm0, xmm0
0x18004e702  xor     eax, eax
0x18004e704  movups  xmmword ptr [rbp+47h+pvarg], xmm0
0x18004e708  mov     qword ptr [rbp+47h+pvarg+10h], rax
0x18004e70c  xorps   xmm1, xmm1
0x18004e70f  movups  xmmword ptr [rbp+47h+var_50], xmm1
0x18004e713  mov     qword ptr [rbp+47h+var_50+10h], rax
0x18004e717  movups  xmmword ptr [rbp+47h+var_80], xmm0
0x18004e71b  mov     qword ptr [rbp+47h+var_80+10h], rax
0x18004e71f  xor     dil, dil
0x18004e722  mov     [rbp+47h+var_C0], rax
0x18004e726  mov     [rbp+47h+var_B0], rax
0x18004e72a  mov     [rbp+47h+var_A8], rax
0x18004e72e  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18004e732  call    cs:__imp_VariantInit
0x18004e738  lea     rcx, [rbp+47h+var_50]; pvarg
0x18004e73c  call    cs:__imp_VariantInit
0x18004e742  lea     rcx, [rbp+47h+var_80]; pvarg
0x18004e746  call    cs:__imp_VariantInit
0x18004e74c  lea     rax, aCommonunenroll; "CommonUnenrollCsp"
0x18004e753  mov     [rbp+47h+var_38], rax
0x18004e757  lea     rax, [rbp+47h+arg_8]
0x18004e75b  mov     [rbp+47h+var_30], rax
0x18004e75f  test    r15, r15
0x18004e762  jnz     short loc_18004E770
0x18004e764  mov     [rbp+47h+arg_8], 8000FFFFh
0x18004e76b  jmp     loc_18004E999
0x18004e770  xor     edx, edx; dwCoInit
0x18004e772  xor     ecx, ecx; pvReserved
0x18004e774  call    cs:__imp_CoInitializeEx
0x18004e77a  mov     [rbp+47h+arg_8], eax
0x18004e77d  test    eax, eax
0x18004e77f  js      loc_18004E999
0x18004e785  mov     edi, 1
0x18004e78a  lea     rax, [rbp+47h+var_C0]
0x18004e78e  mov     [rsp+0F0h+ppv], rax; ppv
0x18004e793  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x18004e79a  mov     r8d, edi; dwClsContext
0x18004e79d  xor     edx, edx; pUnkOuter
0x18004e79f  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x18004e7a6  call    cs:__imp_CoCreateInstance
0x18004e7ac  mov     [rbp+47h+arg_8], eax
0x18004e7af  test    eax, eax
0x18004e7b1  js      loc_18004E999
0x18004e7b7  cmp     [rbp+47h+arg_28], 0
0x18004e7bb  jz      short loc_18004E82C
0x18004e7bd  mov     rcx, r15; psz
0x18004e7c0  call    cs:__imp_SysAllocString
0x18004e7c6  mov     qword ptr [rbp+47h+pvarg+8], rax
0x18004e7ca  test    rax, rax
0x18004e7cd  jnz     short loc_18004E7DB
0x18004e7cf  mov     [rbp+47h+arg_8], 8007000Eh
0x18004e7d6  jmp     loc_18004E999
0x18004e7db  mov     eax, 8
0x18004e7e0  mov     word ptr [rbp+47h+pvarg], ax
0x18004e7e4  lea     rdx, aOmadmServerid; "OMADM::ServerID"
0x18004e7eb  lea     rcx, [rbp+47h+var_B8]
0x18004e7ef  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18004e7f4  movups  xmm0, xmmword ptr [rbp+47h+pvarg]
0x18004e7f8  movaps  [rbp+47h+var_A0], xmm0
0x18004e7fc  movsd   xmm1, qword ptr [rbp+47h+pvarg+10h]
0x18004e801  movsd   [rbp+47h+var_90], xmm1
0x18004e806  mov     rcx, [rbp+47h+var_C0]
0x18004e80a  mov     rax, [rcx]
0x18004e80d  lea     r8, [rbp+47h+var_A0]
0x18004e811  mov     rbx, [rbp+47h+var_B8]
0x18004e815  mov     rdx, rbx
0x18004e818  mov     rax, [rax+68h]
0x18004e81c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e821  mov     [rbp+47h+arg_8], eax
0x18004e824  test    eax, eax
0x18004e826  js      loc_18004E999
0x18004e82c  test    rsi, rsi
0x18004e82f  jz      short loc_18004E896
0x18004e831  mov     rcx, rsi; psz
0x18004e834  call    cs:__imp_SysAllocString
0x18004e83a  mov     qword ptr [rbp+47h+var_50+8], rax
0x18004e83e  test    rax, rax
0x18004e841  jz      short loc_18004E7CF
0x18004e843  mov     esi, 8
0x18004e848  mov     word ptr [rbp+47h+var_50], si
0x18004e84c  lea     rdx, aOmadmAccountid; "OMADM::AccountID"
0x18004e853  lea     rcx, [rbp+47h+var_B8]
0x18004e857  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18004e85c  movups  xmm0, xmmword ptr [rbp+47h+var_50]
0x18004e860  movaps  [rbp+47h+var_A0], xmm0
0x18004e864  movsd   xmm1, qword ptr [rbp+47h+var_50+10h]
0x18004e869  movsd   [rbp+47h+var_90], xmm1
0x18004e86e  mov     rcx, [rbp+47h+var_C0]
0x18004e872  mov     rax, [rcx]
0x18004e875  lea     r8, [rbp+47h+var_A0]
0x18004e879  mov     rbx, [rbp+47h+var_B8]
0x18004e87d  mov     rdx, rbx
0x18004e880  mov     rax, [rax+68h]
0x18004e884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e889  mov     [rbp+47h+arg_8], eax
0x18004e88c  test    eax, eax
0x18004e88e  js      loc_18004E999
0x18004e894  jmp     short loc_18004E89B
0x18004e896  mov     esi, 8
0x18004e89b  test    r14, r14
0x18004e89e  jz      short loc_18004E902
0x18004e8a0  mov     rcx, r14; psz
0x18004e8a3  call    cs:__imp_SysAllocString
0x18004e8a9  mov     qword ptr [rbp+47h+var_80+8], rax
0x18004e8ad  test    rax, rax
0x18004e8b0  jz      loc_18004E7CF
0x18004e8b6  mov     word ptr [rbp+47h+var_80], si
0x18004e8ba  lea     rdx, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x18004e8c1  lea     rcx, [rbp+47h+var_B8]
0x18004e8c5  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18004e8ca  movups  xmm0, xmmword ptr [rbp+47h+var_80]
0x18004e8ce  movaps  [rbp+47h+var_A0], xmm0
0x18004e8d2  movsd   xmm1, qword ptr [rbp+47h+var_80+10h]
0x18004e8d7  movsd   [rbp+47h+var_90], xmm1
0x18004e8dc  mov     rcx, [rbp+47h+var_C0]
0x18004e8e0  mov     rax, [rcx]
0x18004e8e3  lea     r8, [rbp+47h+var_A0]
0x18004e8e7  mov     rbx, [rbp+47h+var_B8]
0x18004e8eb  mov     rdx, rbx
0x18004e8ee  mov     rax, [rax+68h]
0x18004e8f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e8f7  mov     [rbp+47h+arg_8], eax
0x18004e8fa  test    eax, eax
0x18004e8fc  js      loc_18004E999
0x18004e902  lea     rax, [rbp+47h+var_B0]
0x18004e906  mov     [rsp+0F0h+ppv], rax; ppv
0x18004e90b  lea     r9, _GUID_4b965405_f21f_4702_95dd_4e81c3d1bb30; riid
0x18004e912  mov     r8d, edi; dwClsContext
0x18004e915  xor     edx, edx; pUnkOuter
0x18004e917  lea     rcx, _GUID_c196b2be_ba06_4049_8518_322e1e04282b; rclsid
0x18004e91e  call    cs:__imp_CoCreateInstance
0x18004e924  mov     [rbp+47h+arg_8], eax
0x18004e927  test    eax, eax
0x18004e929  js      short loc_18004E999
0x18004e92b  mov     rcx, [rbp+47h+var_B0]
0x18004e92f  mov     rax, [rcx]
0x18004e932  mov     rdx, r12
0x18004e935  mov     rax, [rax+28h]
0x18004e939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e93e  mov     [rbp+47h+arg_8], eax
0x18004e941  test    eax, eax
0x18004e943  js      short loc_18004E999
0x18004e945  cmp     [rbp+47h+arg_20], 0
0x18004e949  jz      short loc_18004E96B
0x18004e94b  mov     rcx, [rbp+47h+var_B0]
0x18004e94f  mov     rax, [rcx]
0x18004e952  xor     r8d, r8d
0x18004e955  mov     rdx, r15
0x18004e958  mov     rax, [rax+0B0h]
0x18004e95f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e964  mov     [rbp+47h+arg_8], eax
0x18004e967  test    eax, eax
0x18004e969  js      short loc_18004E999
0x18004e96b  mov     rcx, [rbp+47h+var_B0]
0x18004e96f  mov     rax, [rcx]
0x18004e972  lea     rdx, [rbp+47h+var_A8]
0x18004e976  mov     rax, [rax+0E0h]
0x18004e97d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e982  mov     [rbp+47h+arg_8], eax
0x18004e985  test    eax, eax
0x18004e987  js      short loc_18004E999
0x18004e989  mov     rdx, [rbp+47h+var_A8]; struct IConfigManager2URI *
0x18004e98d  mov     rcx, [rbp+47h+var_C0]; struct IConfigManager2 *
0x18004e991  call    ?DeleteUri@@YAJPEAUIConfigManager2@@PEAUIConfigManager2URI@@@Z; DeleteUri(IConfigManager2 *,IConfigManager2URI *)
0x18004e996  mov     [rbp+47h+arg_8], eax
0x18004e999  lea     rcx, [rbp+47h+var_80]; pvarg
0x18004e99d  call    cs:__imp_VariantClear
0x18004e9a3  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18004e9a7  call    cs:__imp_VariantClear
0x18004e9ad  lea     rcx, [rbp+47h+var_50]; pvarg
0x18004e9b1  call    cs:__imp_VariantClear
0x18004e9b7  mov     rcx, [rbp+47h+var_C0]
0x18004e9bb  test    rcx, rcx
0x18004e9be  jz      short loc_18004E9D4
0x18004e9c0  mov     rax, [rcx]
0x18004e9c3  mov     rax, [rax+10h]
0x18004e9c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9cc  mov     [rbp+47h+var_C0], 0
0x18004e9d4  mov     rcx, [rbp+47h+var_B0]
0x18004e9d8  test    rcx, rcx
0x18004e9db  jz      short loc_18004E9F1
0x18004e9dd  mov     rax, [rcx]
0x18004e9e0  mov     rax, [rax+10h]
0x18004e9e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9e9  mov     [rbp+47h+var_B0], 0
0x18004e9f1  mov     rcx, [rbp+47h+var_A8]
0x18004e9f5  test    rcx, rcx
0x18004e9f8  jz      short loc_18004EA0E
0x18004e9fa  mov     rax, [rcx]
0x18004e9fd  mov     rax, [rax+10h]
0x18004ea01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea06  mov     [rbp+47h+var_A8], 0
0x18004ea0e  test    dil, dil
0x18004ea11  jz      short loc_18004EA19
0x18004ea13  call    cs:__imp_CoUninitialize
0x18004ea19  mov     edi, [rbp+47h+arg_8]
0x18004ea1c  lea     rcx, [rbp+47h+var_38]; this
0x18004ea20  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18004ea25  nop
0x18004ea26  mov     rcx, rbx; bstrString
0x18004ea29  call    cs:__imp_SysFreeString
0x18004ea2f  mov     eax, edi
0x18004ea31  lea     r11, [rsp+0F0h+var_20]
0x18004ea39  mov     rbx, [r11+30h]
0x18004ea3d  mov     rsi, [r11+40h]
0x18004ea41  mov     rsp, r11
0x18004ea44  pop     r15
0x18004ea46  pop     r14
0x18004ea48  pop     r12
0x18004ea4a  pop     rdi
0x18004ea4b  pop     rbp
0x18004ea4c  retn
```
