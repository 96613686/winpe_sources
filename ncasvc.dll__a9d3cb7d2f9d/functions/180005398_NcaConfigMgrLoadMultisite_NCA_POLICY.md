# NcaConfigMgrLoadMultisite(NCA_POLICY_ *)

- ea: `0x180005398`
- end: `0x180005767`
- name: `?NcaConfigMgrLoadMultisite@@YAJPEAUNCA_POLICY_@@@Z`
- size: `975`
- prototype: `__int64 __fastcall(struct NCA_POLICY_ *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005df8`

## callees

- `0x180003770`
- `0x180004f34`
- `0x180005398`
- `0x180019c70`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800055c9`
- `OLEAUT32!__imp_SysAllocString` at `0x180005630`
- `OLEAUT32!__imp_SysAllocString` at `0x1800055c9`
- `OLEAUT32!__imp_SysAllocString` at `0x180005630`
- `OLEAUT32!__imp_SysFreeString` at `0x180005607`
- `OLEAUT32!__imp_SysFreeString` at `0x18000567e`
- `OLEAUT32!__imp_SysFreeString` at `0x180005607`
- `OLEAUT32!__imp_SysFreeString` at `0x18000567e`
- `OLEAUT32!__imp_VariantInit` at `0x1800053d5`
- `OLEAUT32!__imp_VariantInit` at `0x1800053d5`
- `OLEAUT32!__imp_VariantClear` at `0x18000561d`
- `OLEAUT32!__imp_VariantClear` at `0x18000568e`
- `OLEAUT32!__imp_VariantClear` at `0x18000561d`
- `OLEAUT32!__imp_VariantClear` at `0x18000568e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800053f8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800053f8`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180005523`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180005523`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180005749`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180005749`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005458`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005458`

## pseudocode

```c
__int64 __fastcall NcaConfigMgrLoadMultisite(struct NCA_POLICY_ *a1)
{
  HRESULT v2; // eax
  int v3; // r14d
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  OLECHAR *v6; // rdi
  OLECHAR *v7; // rdi
  LPVOID ppv; // [rsp+50h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-18h] BYREF
  int v11; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v12; // [rsp+B8h] [rbp+48h] BYREF
  IUnknown *pProxy; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v14; // [rsp+C8h] [rbp+58h] BYREF

  ppv = 0;
  pProxy = 0;
  v14 = 0;
  v12 = 0;
  v11 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  *((_DWORD *)a1 + 23) = 0;
  NcaFree(*((LPVOID *)a1 + 12));
  *((_QWORD *)a1 + 12) = 0;
  v2 = CoInitializeEx(0, 0);
  if ( v2 >= 0 )
  {
    v3 = 1;
    v2 = CoCreateInstance(&CLSID_WbemAdministrativeLocator, 0, 1u, &IID_IWbemLocator, &ppv);
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD, _QWORD, _QWORD, int, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)ppv + 24LL))(
             ppv,
             L"root\\StandardCimv2",
             0,
             0,
             0,
             128,
             0,
             0,
             &pProxy);
      if ( v2 >= 0 )
      {
        CoSetProxyBlanket(pProxy, 0xAu, 0, 0, 3u, 3u, 0, 0);
        v2 = ((__int64 (__fastcall *)(IUnknown *, const wchar_t *, const wchar_t *, __int64, _QWORD, __int64 *))pProxy->lpVtbl[6].Release)(
               pProxy,
               L"WQL",
               L"SELECT * FROM MSFT_DASiteTableEntry",
               32,
               0,
               &v14);
        if ( v2 >= 0 )
        {
          while ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64, __int64 *, int *))(*(_QWORD *)v14 + 32LL))(
                     v14,
                     0xFFFFFFFFLL,
                     1,
                     &v12,
                     &v11) )
          {
            *((_DWORD *)a1 + 23) = 1;
            v6 = SysAllocString(L"State");
            v2 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v12 + 32LL))(
                   v12,
                   v6,
                   0,
                   &pvarg,
                   0,
                   0);
            if ( v2 < 0 )
            {
              v4 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v5 = 38;
                goto LABEL_29;
              }
              break;
            }
            SysFreeString(v6);
            if ( pvarg.lVal > 0 )
            {
              VariantClear(&pvarg);
              v7 = SysAllocString(L"EntryPointName");
              v2 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v12 + 32LL))(
                     v12,
                     v7,
                     0,
                     &pvarg,
                     0,
                     0);
              if ( v2 < 0 )
              {
                v4 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v5 = 39;
                  goto LABEL_29;
                }
                break;
              }
              NcaFree(*((LPVOID *)a1 + 12));
              NcaStringCopy(pvarg.bstrVal);
              SysFreeString(v7);
            }
            VariantClear(&pvarg);
          }
        }
        else
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v5 = 37;
            goto LABEL_29;
          }
        }
      }
      else
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v5 = 36;
          goto LABEL_29;
        }
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 35;
        goto LABEL_29;
      }
    }
  }
  else
  {
    v3 = 0;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 34;
LABEL_29:
      WPP_SF_d(v4[2], v5, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids, (unsigned int)v2);
    }
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( pProxy )
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v3 == 1 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x180005398  push    rbp
0x18000539a  push    rbx
0x18000539b  push    rsi
0x18000539c  push    rdi
0x18000539d  push    r12
0x18000539f  push    r14
0x1800053a1  push    r15
0x1800053a3  mov     rbp, rsp
0x1800053a6  sub     rsp, 70h
0x1800053aa  xor     r15d, r15d
0x1800053ad  mov     rsi, rcx
0x1800053b0  xorps   xmm0, xmm0
0x1800053b3  mov     [rbp+var_20], r15
0x1800053b7  xor     eax, eax
0x1800053b9  mov     [rbp+pProxy], r15
0x1800053bd  lea     rcx, [rbp+pvarg]; pvarg
0x1800053c1  mov     [rbp+arg_18], r15
0x1800053c5  mov     [rbp+arg_8], r15
0x1800053c9  mov     [rbp+arg_0], r15d
0x1800053cd  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800053d1  mov     qword ptr [rbp+pvarg+10h], rax
0x1800053d5  call    cs:__imp_VariantInit
0x1800053dc  nop     dword ptr [rax+rax+00h]
0x1800053e1  lea     rbx, [rsi+60h]
0x1800053e5  mov     [rsi+5Ch], r15d
0x1800053e9  mov     rcx, [rbx]; lpMem
0x1800053ec  call    NcaFree
0x1800053f1  xor     edx, edx; dwCoInit
0x1800053f3  mov     [rbx], r15
0x1800053f6  xor     ecx, ecx; pvReserved
0x1800053f8  call    cs:__imp_CoInitializeEx
0x1800053ff  nop     dword ptr [rax+rax+00h]
0x180005404  lea     r12d, [r15+1]
0x180005408  test    eax, eax
0x18000540a  jns     short loc_180005439
0x18000540c  mov     r14d, r15d
0x18000540f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005416  lea     rdx, WPP_GLOBAL_Control
0x18000541d  cmp     rcx, rdx
0x180005420  jz      loc_1800056F0
0x180005426  test    [rcx+1Ch], r12b
0x18000542a  jz      loc_1800056F0
0x180005430  lea     edx, [r15+22h]
0x180005434  jmp     loc_1800056DD
0x180005439  lea     rax, [rbp+var_20]
0x18000543d  mov     r8d, r12d; dwClsContext
0x180005440  lea     r9, IID_IWbemLocator; riid
0x180005447  mov     [rsp+70h+ppv], rax; ppv
0x18000544c  xor     edx, edx; pUnkOuter
0x18000544e  lea     rcx, CLSID_WbemAdministrativeLocator; rclsid
0x180005455  mov     r14d, r12d
0x180005458  call    cs:__imp_CoCreateInstance
0x18000545f  nop     dword ptr [rax+rax+00h]
0x180005464  test    eax, eax
0x180005466  jns     short loc_180005493
0x180005468  mov     rcx, cs:WPP_GLOBAL_Control
0x18000546f  lea     rdx, WPP_GLOBAL_Control
0x180005476  cmp     rcx, rdx
0x180005479  jz      loc_1800056F0
0x18000547f  test    [rcx+1Ch], r12b
0x180005483  jz      loc_1800056F0
0x180005489  mov     edx, 23h ; '#'
0x18000548e  jmp     loc_1800056DD
0x180005493  mov     rcx, [rbp+var_20]
0x180005497  lea     rdx, [rbp+pProxy]
0x18000549b  mov     [rsp+70h+var_30], rdx
0x1800054a0  xor     r9d, r9d
0x1800054a3  mov     qword ptr [rsp+70h+dwCapabilities], r15
0x1800054a8  lea     rdx, aRootStandardci; "root\\StandardCimv2"
0x1800054af  mov     [rsp+70h+pAuthInfo], r15
0x1800054b4  xor     r8d, r8d
0x1800054b7  mov     rax, [rcx]
0x1800054ba  mov     [rsp+70h+dwImpLevel], 80h
0x1800054c2  mov     [rsp+70h+ppv], r15
0x1800054c7  mov     rax, [rax+18h]
0x1800054cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054d0  test    eax, eax
0x1800054d2  jns     short loc_1800054FF
0x1800054d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054db  lea     rdx, WPP_GLOBAL_Control
0x1800054e2  cmp     rcx, rdx
0x1800054e5  jz      loc_1800056F0
0x1800054eb  test    [rcx+1Ch], r12b
0x1800054ef  jz      loc_1800056F0
0x1800054f5  mov     edx, 24h ; '$'
0x1800054fa  jmp     loc_1800056DD
0x1800054ff  mov     rcx, [rbp+pProxy]; pProxy
0x180005503  mov     eax, 3
0x180005508  mov     [rsp+70h+dwCapabilities], r15d; dwCapabilities
0x18000550d  xor     r9d, r9d; pServerPrincName
0x180005510  mov     [rsp+70h+pAuthInfo], r15; pAuthInfo
0x180005515  xor     r8d, r8d; dwAuthzSvc
0x180005518  mov     [rsp+70h+dwImpLevel], eax; dwImpLevel
0x18000551c  lea     edx, [rax+7]; dwAuthnSvc
0x18000551f  mov     dword ptr [rsp+70h+ppv], eax; dwAuthnLevel
0x180005523  call    cs:__imp_CoSetProxyBlanket
0x18000552a  nop     dword ptr [rax+rax+00h]
0x18000552f  mov     rcx, [rbp+pProxy]
0x180005533  lea     rdx, [rbp+arg_18]
0x180005537  mov     qword ptr [rsp+70h+dwImpLevel], rdx
0x18000553c  lea     r8, aSelectFromMsft; "SELECT * FROM MSFT_DASiteTableEntry"
0x180005543  mov     r9d, 20h ; ' '
0x180005549  mov     [rsp+70h+ppv], r15
0x18000554e  lea     rdx, aWql; "WQL"
0x180005555  mov     rax, [rcx]
0x180005558  mov     rax, [rax+0A0h]
0x18000555f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005564  test    eax, eax
0x180005566  jns     short loc_180005593
0x180005568  mov     rcx, cs:WPP_GLOBAL_Control
0x18000556f  lea     rdx, WPP_GLOBAL_Control
0x180005576  cmp     rcx, rdx
0x180005579  jz      loc_1800056F0
0x18000557f  test    [rcx+1Ch], r12b
0x180005583  jz      loc_1800056F0
0x180005589  mov     edx, 25h ; '%'
0x18000558e  jmp     loc_1800056DD
0x180005593  mov     rcx, [rbp+arg_18]
0x180005597  lea     rdx, [rbp+arg_0]
0x18000559b  mov     [rsp+70h+ppv], rdx
0x1800055a0  lea     r9, [rbp+arg_8]
0x1800055a4  mov     r8d, r12d
0x1800055a7  or      edx, 0FFFFFFFFh
0x1800055aa  mov     rax, [rcx]
0x1800055ad  mov     rax, [rax+20h]
0x1800055b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055b6  test    eax, eax
0x1800055b8  jnz     loc_1800056F0
0x1800055be  lea     rcx, psz; "State"
0x1800055c5  mov     [rsi+5Ch], r12d
0x1800055c9  call    cs:__imp_SysAllocString
0x1800055d0  nop     dword ptr [rax+rax+00h]
0x1800055d5  mov     rcx, [rbp+arg_8]
0x1800055d9  lea     r9, [rbp+pvarg]
0x1800055dd  mov     rdi, rax
0x1800055e0  mov     qword ptr [rsp+70h+dwImpLevel], r15
0x1800055e5  xor     r8d, r8d
0x1800055e8  mov     [rsp+70h+ppv], r15
0x1800055ed  mov     rdx, [rcx]
0x1800055f0  mov     rax, [rdx+20h]
0x1800055f4  mov     rdx, rdi
0x1800055f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055fc  test    eax, eax
0x1800055fe  js      loc_1800056BF
0x180005604  mov     rcx, rdi; bstrString
0x180005607  call    cs:__imp_SysFreeString
0x18000560e  nop     dword ptr [rax+rax+00h]
0x180005613  cmp     dword ptr [rbp+pvarg+8], r15d
0x180005617  jle     short loc_18000568A
0x180005619  lea     rcx, [rbp+pvarg]; pvarg
0x18000561d  call    cs:__imp_VariantClear
0x180005624  nop     dword ptr [rax+rax+00h]
0x180005629  lea     rcx, aEntrypointname; "EntryPointName"
0x180005630  call    cs:__imp_SysAllocString
0x180005637  nop     dword ptr [rax+rax+00h]
0x18000563c  mov     rcx, [rbp+arg_8]
0x180005640  lea     r9, [rbp+pvarg]
0x180005644  mov     rdi, rax
0x180005647  mov     qword ptr [rsp+70h+dwImpLevel], r15
0x18000564c  xor     r8d, r8d
0x18000564f  mov     [rsp+70h+ppv], r15
0x180005654  mov     rdx, [rcx]
0x180005657  mov     rax, [rdx+20h]
0x18000565b  mov     rdx, rdi
0x18000565e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005663  test    eax, eax
0x180005665  js      short loc_18000569F
0x180005667  mov     rcx, [rbx]; lpMem
0x18000566a  call    NcaFree
0x18000566f  mov     rcx, qword ptr [rbp+pvarg+8]; Src
0x180005673  mov     rdx, rbx
0x180005676  call    NcaStringCopy
0x18000567b  mov     rcx, rdi; bstrString
0x18000567e  call    cs:__imp_SysFreeString
0x180005685  nop     dword ptr [rax+rax+00h]
0x18000568a  lea     rcx, [rbp+pvarg]; pvarg
0x18000568e  call    cs:__imp_VariantClear
0x180005695  nop     dword ptr [rax+rax+00h]
0x18000569a  jmp     loc_180005593
0x18000569f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056a6  lea     rdx, WPP_GLOBAL_Control
0x1800056ad  cmp     rcx, rdx
0x1800056b0  jz      short loc_1800056F0
0x1800056b2  test    [rcx+1Ch], r12b
0x1800056b6  jz      short loc_1800056F0
0x1800056b8  mov     edx, 27h ; '''
0x1800056bd  jmp     short loc_1800056DD
0x1800056bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056c6  lea     rdx, WPP_GLOBAL_Control
0x1800056cd  cmp     rcx, rdx
0x1800056d0  jz      short loc_1800056F0
0x1800056d2  test    [rcx+1Ch], r12b
0x1800056d6  jz      short loc_1800056F0
0x1800056d8  mov     edx, 26h ; '&'
0x1800056dd  mov     rcx, [rcx+10h]
0x1800056e1  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x1800056e8  mov     r9d, eax
0x1800056eb  call    WPP_SF_d
0x1800056f0  mov     rcx, [rbp+arg_8]
0x1800056f4  test    rcx, rcx
0x1800056f7  jz      short loc_180005705
0x1800056f9  mov     rax, [rcx]
0x1800056fc  mov     rax, [rax+10h]
0x180005700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005705  mov     rcx, [rbp+arg_18]
0x180005709  test    rcx, rcx
0x18000570c  jz      short loc_18000571A
0x18000570e  mov     rax, [rcx]
0x180005711  mov     rax, [rax+10h]
0x180005715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000571a  mov     rcx, [rbp+pProxy]
0x18000571e  test    rcx, rcx
0x180005721  jz      short loc_18000572F
0x180005723  mov     rax, [rcx]
0x180005726  mov     rax, [rax+10h]
0x18000572a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000572f  mov     rcx, [rbp+var_20]
0x180005733  test    rcx, rcx
0x180005736  jz      short loc_180005744
0x180005738  mov     rax, [rcx]
0x18000573b  mov     rax, [rax+10h]
0x18000573f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005744  cmp     r14d, r12d
0x180005747  jnz     short loc_180005755
0x180005749  call    cs:__imp_CoUninitialize
0x180005750  nop     dword ptr [rax+rax+00h]
0x180005755  xor     eax, eax
0x180005757  add     rsp, 70h
0x18000575b  pop     r15
0x18000575d  pop     r14
0x18000575f  pop     r12
0x180005761  pop     rdi
0x180005762  pop     rsi
0x180005763  pop     rbx
0x180005764  pop     rbp
0x180005765  retn
```
