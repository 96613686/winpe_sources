# _anonymous_namespace_::CreateConfigManangerForSettingRollback

- ea: `0x1800e2518`
- end: `0x1800e2702`
- name: `_anonymous_namespace_::CreateConfigManangerForSettingRollback`
- size: `490`
- prototype: `__int64 __fastcall(int, OLECHAR *psz, OLECHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800e6ccc`

## callees

- `0x18000caf4`
- `0x18000d4d4`
- `0x18005a32c`
- `0x1800e2518`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800e254e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e2635`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e2696`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e254e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e2635`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e2696`
- `OLEAUT32!__imp_VariantInit` at `0x1800e2533`
- `OLEAUT32!__imp_VariantInit` at `0x1800e2533`
- `OLEAUT32!__imp_VariantClear` at `0x1800e26e8`
- `OLEAUT32!__imp_VariantClear` at `0x1800e26e8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e257f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e257f`

## string_xrefs

- `0x1800e2661`: `OMADM::TargetedUserSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::CreateConfigManangerForSettingRollback(LPVOID *a1, OLECHAR *psz, OLECHAR *a3)
{
  HRESULT Instance; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  LPVOID v9; // rcx
  LPVOID v10; // rcx
  __int64 v11; // rdx
  LPVOID v12; // rcx
  LPVOID v13; // rcx
  int ppv; // [rsp+20h] [rbp-50h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG v17; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  VariantInit(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(psz);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(a1);
  Instance = CoCreateInstance(
               &GUID_66d0db14_5638_475f_a386_629522d8c461,
               0,
               1u,
               &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
               a1);
  v7 = Instance;
  if ( Instance >= 0 )
  {
    v9 = *a1;
    v17 = pvarg;
    Instance = (*(__int64 (__fastcall **)(LPVOID, const OLECHAR *, VARIANTARG *))(*(_QWORD *)v9 + 104LL))(
                 v9,
                 L"OMADM::ServerID",
                 &v17);
    v7 = Instance;
    if ( Instance >= 0 )
    {
      v10 = *a1;
      v17 = pvarg;
      Instance = (*(__int64 (__fastcall **)(LPVOID, const OLECHAR *, VARIANTARG *))(*(_QWORD *)v10 + 104LL))(
                   v10,
                   L"OMADM::AccountID",
                   &v17);
      v7 = Instance;
      if ( Instance >= 0 )
      {
        if ( a3
          && (wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>::reset(
                &pvarg,
                v11),
              pvarg.vt = 8,
              pvarg.llVal = (LONGLONG)SysAllocString(a3),
              v12 = *a1,
              v17 = pvarg,
              Instance = (*(__int64 (__fastcall **)(LPVOID, const OLECHAR *, VARIANTARG *))(*(_QWORD *)v12 + 104LL))(
                           v12,
                           L"OMADM::TargetedUserSID",
                           &v17),
              v7 = Instance,
              Instance < 0) )
        {
          v8 = 67;
        }
        else
        {
          wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>::reset(
            &pvarg,
            v11);
          pvarg.vt = 8;
          pvarg.llVal = (LONGLONG)SysAllocString(L"9ff451dc-a529-468f-a37d-e0aa6144a29f");
          v13 = *a1;
          v17 = pvarg;
          Instance = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(*(_QWORD *)v13 + 104LL))(
                       v13,
                       L"DYNAMO::CONTEXTID",
                       &v17);
          v7 = Instance;
          if ( Instance >= 0 )
          {
            v7 = 0;
            goto LABEL_14;
          }
          v8 = 74;
        }
      }
      else
      {
        v8 = 59;
      }
    }
    else
    {
      v8 = 58;
    }
  }
  else
  {
    v8 = 57;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
    (const char *)(unsigned int)Instance,
    ppv);
LABEL_14:
  VariantClear(&pvarg);
  return v7;
}

```

## disassembly

```asm
0x1800e2518  push    rbp
0x1800e251a  push    rbx
0x1800e251b  push    rsi
0x1800e251c  push    rdi
0x1800e251d  push    r14
0x1800e251f  mov     rbp, rsp
0x1800e2522  sub     rsp, 70h
0x1800e2526  mov     rsi, r8
0x1800e2529  mov     rbx, rdx
0x1800e252c  mov     rdi, rcx
0x1800e252f  lea     rcx, [rbp+pvarg]; pvarg
0x1800e2533  call    cs:__imp_VariantInit
0x1800e253a  nop     dword ptr [rax+rax+00h]
0x1800e253f  nop
0x1800e2540  mov     r14d, 8
0x1800e2546  mov     word ptr [rbp+pvarg], r14w
0x1800e254b  mov     rcx, rbx; psz
0x1800e254e  call    cs:__imp_SysAllocString
0x1800e2555  nop     dword ptr [rax+rax+00h]
0x1800e255a  mov     qword ptr [rbp+pvarg+8], rax
0x1800e255e  mov     rcx, rdi
0x1800e2561  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800e2566  mov     qword ptr [rsp+70h+ppv], rdi; int
0x1800e256b  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x1800e2572  xor     edx, edx; pUnkOuter
0x1800e2574  lea     r8d, [r14-7]; dwClsContext
0x1800e2578  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x1800e257f  call    cs:__imp_CoCreateInstance
0x1800e2586  nop     dword ptr [rax+rax+00h]
0x1800e258b  mov     ebx, eax
0x1800e258d  test    eax, eax
0x1800e258f  jns     short loc_1800E2597
0x1800e2591  lea     edx, [r14+31h]
0x1800e2595  jmp     short loc_1800E25CE
0x1800e2597  mov     rcx, [rdi]
0x1800e259a  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800e259e  movaps  [rbp+var_20], xmm0
0x1800e25a2  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800e25a7  movsd   [rbp+var_10], xmm1
0x1800e25ac  mov     rax, [rcx]
0x1800e25af  lea     r8, [rbp+var_20]
0x1800e25b3  lea     rdx, aOmadmServerid; "OMADM::ServerID"
0x1800e25ba  mov     rax, [rax+68h]
0x1800e25be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e25c3  mov     ebx, eax
0x1800e25c5  test    eax, eax
0x1800e25c7  jns     short loc_1800E25E6
0x1800e25c9  mov     edx, 3Ah ; ':'; void *
0x1800e25ce  mov     rcx, [rbp+28h]; this
0x1800e25d2  mov     r9d, eax; char *
0x1800e25d5  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800e25dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e25e1  jmp     loc_1800E26E4
0x1800e25e6  mov     rcx, [rdi]
0x1800e25e9  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800e25ed  movaps  [rbp+var_20], xmm0
0x1800e25f1  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800e25f6  movsd   [rbp+var_10], xmm1
0x1800e25fb  mov     rax, [rcx]
0x1800e25fe  lea     r8, [rbp+var_20]
0x1800e2602  lea     rdx, aOmadmAccountid_0; "OMADM::AccountID"
0x1800e2609  mov     rax, [rax+68h]
0x1800e260d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2612  mov     ebx, eax
0x1800e2614  test    eax, eax
0x1800e2616  jns     short loc_1800E261F
0x1800e2618  mov     edx, 3Bh ; ';'
0x1800e261d  jmp     short loc_1800E25CE
0x1800e261f  test    rsi, rsi
0x1800e2622  jz      short loc_1800E2681
0x1800e2624  lea     rcx, [rbp+pvarg]
0x1800e2628  call    ?reset@?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@QEAAXXZ; wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>::reset(void)
0x1800e262d  mov     word ptr [rbp+pvarg], r14w
0x1800e2632  mov     rcx, rsi; psz
0x1800e2635  call    cs:__imp_SysAllocString
0x1800e263c  nop     dword ptr [rax+rax+00h]
0x1800e2641  mov     qword ptr [rbp+pvarg+8], rax
0x1800e2645  mov     rcx, [rdi]
0x1800e2648  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800e264c  movaps  [rbp+var_20], xmm0
0x1800e2650  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800e2655  movsd   [rbp+var_10], xmm1
0x1800e265a  mov     rax, [rcx]
0x1800e265d  lea     r8, [rbp+var_20]
0x1800e2661  lea     rdx, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x1800e2668  mov     rax, [rax+68h]
0x1800e266c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2671  mov     ebx, eax
0x1800e2673  test    eax, eax
0x1800e2675  jns     short loc_1800E2681
0x1800e2677  mov     edx, 43h ; 'C'
0x1800e267c  jmp     loc_1800E25CE
0x1800e2681  lea     rcx, [rbp+pvarg]
0x1800e2685  call    ?reset@?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@QEAAXXZ; wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>::reset(void)
0x1800e268a  mov     word ptr [rbp+pvarg], r14w
0x1800e268f  lea     rcx, a9ff451dcA52946; "9ff451dc-a529-468f-a37d-e0aa6144a29f"
0x1800e2696  call    cs:__imp_SysAllocString
0x1800e269d  nop     dword ptr [rax+rax+00h]
0x1800e26a2  mov     qword ptr [rbp+pvarg+8], rax
0x1800e26a6  mov     rcx, [rdi]
0x1800e26a9  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800e26ad  movaps  [rbp+var_20], xmm0
0x1800e26b1  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800e26b6  movsd   [rbp+var_10], xmm1
0x1800e26bb  mov     rax, [rcx]
0x1800e26be  lea     r8, [rbp+var_20]
0x1800e26c2  lea     rdx, aDynamoContexti; "DYNAMO::CONTEXTID"
0x1800e26c9  mov     rax, [rax+68h]
0x1800e26cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e26d2  mov     ebx, eax
0x1800e26d4  test    eax, eax
0x1800e26d6  jns     short loc_1800E26E2
0x1800e26d8  mov     edx, 4Ah ; 'J'
0x1800e26dd  jmp     loc_1800E25CE
0x1800e26e2  xor     ebx, ebx
0x1800e26e4  lea     rcx, [rbp+pvarg]; pvarg
0x1800e26e8  call    cs:__imp_VariantClear
0x1800e26ef  nop     dword ptr [rax+rax+00h]
0x1800e26f4  mov     eax, ebx
0x1800e26f6  add     rsp, 70h
0x1800e26fa  pop     r14
0x1800e26fc  pop     rdi
0x1800e26fd  pop     rsi
0x1800e26fe  pop     rbx
0x1800e26ff  pop     rbp
0x1800e2700  retn
```
