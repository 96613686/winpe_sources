# StoragePolicy::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x180051500`
- end: `0x180051748`
- name: `?CreateNodeInstance@StoragePolicy@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `584`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, int, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800511d0`

## callees

- `0x18001a4fc`
- `0x180023fa0`
- `0x1800512f8`
- `0x180051500`
- `0x180107010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800515e5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800515e5`
- `OLEAUT32!__imp_VariantInit` at `0x180051555`
- `OLEAUT32!__imp_VariantInit` at `0x180051555`
- `OLEAUT32!__imp_VariantClear` at `0x18005171e`
- `OLEAUT32!__imp_VariantClear` at `0x18005171e`
- `policymanager!EnterprisePolicyManagerStore_DoesProviderContextSidAreaPolicyValueExist` at `0x18005161e`
- `policymanager!EnterprisePolicyManagerStore_DoesProviderContextSidAreaPolicyValueExist` at `0x18005161e`
- `policymanager!EnterprisePolicyManagerStore_SetProviderContextSidAreaPolicyValue` at `0x180051657`
- `policymanager!EnterprisePolicyManagerStore_SetProviderContextSidAreaPolicyValue` at `0x180051657`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StoragePolicy::CreateNodeInstance(
        struct CConfigServiceProvider2Impl *a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        int a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  int v9; // edi
  struct ICSPNode *v10; // rbx
  int v12; // [rsp+30h] [rbp-78h] BYREF
  int v13; // [rsp+34h] [rbp-74h]
  int v14; // [rsp+38h] [rbp-70h] BYREF
  const unsigned __int16 *v15; // [rsp+40h] [rbp-68h] BYREF
  struct ICSPNode *v16; // [rsp+48h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-58h] BYREF

  v13 = a4;
  v15 = 0;
  v14 = 0;
  v12 = 0;
  v16 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !a1 || !a2 || !a3 || !a5 || !a6 )
  {
    v9 = -2147024809;
    goto LABEL_21;
  }
  *a5 = 0;
  *a6 = 0;
  v9 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v14);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, const unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
           a2,
           (unsigned int)(v14 - 1),
           &v15);
    if ( v9 >= 0 )
    {
      if ( (unsigned int)_o__wcsicmp(v15, L"Disable") )
        goto LABEL_9;
      v15 = L"AllowStorageCard";
      EnterprisePolicyManagerStore_DoesProviderContextSidAreaPolicyValueExist(
        (struct CConfigServiceProvider2Impl *)((char *)a1 + 104),
        L"System",
        L"AllowStorageCard",
        &v12);
      if ( !v12 )
      {
        pvarg.lVal = 0;
        pvarg.vt = 3;
        v9 = EnterprisePolicyManagerStore_SetProviderContextSidAreaPolicyValue(
               (struct CConfigServiceProvider2Impl *)((char *)a1 + 104),
               L"System",
               v15,
               &pvarg,
               0);
        if ( v9 < 0 )
          goto LABEL_21;
        v12 = 1;
      }
      if ( v13 )
      {
LABEL_9:
        v9 = -2046820335;
      }
      else
      {
        v9 = ATL::CComObject<StoragePolicy>::CreateInstance(&v16);
        if ( v9 >= 0 )
        {
          v10 = v16;
          if ( v16 )
          {
            v9 = (*(__int64 (__fastcall **)(struct ICSPNode *, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*(_QWORD *)v16 + 136LL))(
                   v16,
                   a1,
                   a2,
                   a3);
            if ( v9 >= 0 )
            {
              *((_QWORD *)v10 + 16) = (char *)a1 + 104;
              try
              {
                std::wstring::operator=((char *)v10 + 136, L"System");
                std::wstring::operator=((char *)v10 + 168, v15);
              }
              catch ( std::bad_alloc )
              {
                v13 = -2147024882;
                v9 = -2147024882;
                goto LABEL_21;
              }
              (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v10 + 8LL))(v10);
              v16 = 0;
              *a5 = v10;
            }
          }
          else
          {
            v9 = -2147024882;
          }
        }
      }
    }
  }
LABEL_21:
  VariantClear(&pvarg);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180051500  mov     r11, rsp
0x180051503  push    rbx
0x180051504  push    rsi
0x180051505  push    rdi
0x180051506  push    r12
0x180051508  push    r13
0x18005150a  push    r14
0x18005150c  push    r15
0x18005150e  sub     rsp, 70h
0x180051512  mov     [rsp+0A8h+var_74], r9d
0x180051517  mov     r12, r8
0x18005151a  mov     rsi, rdx
0x18005151d  mov     r13, rcx
0x180051520  mov     r15, [rsp+0A8h+arg_20]
0x180051528  mov     rbx, [rsp+0A8h+arg_28]
0x180051530  xor     r14d, r14d
0x180051533  mov     [r11-68h], r14
0x180051537  mov     [r11-70h], r14d
0x18005153b  mov     [r11-78h], r14d
0x18005153f  mov     [r11-60h], r14
0x180051543  xorps   xmm0, xmm0
0x180051546  xor     eax, eax
0x180051548  movups  xmmword ptr [rsp+0A8h+pvarg], xmm0
0x18005154d  mov     [r11-48h], rax
0x180051551  lea     rcx, [r11-58h]; pvarg
0x180051555  call    cs:__imp_VariantInit
0x18005155c  nop     dword ptr [rax+rax+00h]
0x180051561  test    r13, r13
0x180051564  jz      loc_180051714
0x18005156a  test    rsi, rsi
0x18005156d  jz      loc_180051714
0x180051573  test    r12, r12
0x180051576  jz      loc_180051714
0x18005157c  test    r15, r15
0x18005157f  jz      loc_180051714
0x180051585  test    rbx, rbx
0x180051588  jz      loc_180051714
0x18005158e  mov     [r15], r14
0x180051591  mov     [rbx], r14d
0x180051594  mov     rax, [rsi]
0x180051597  lea     rdx, [rsp+0A8h+var_70]
0x18005159c  mov     rcx, rsi
0x18005159f  mov     rax, [rax+88h]
0x1800515a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800515ab  mov     edi, eax
0x1800515ad  test    eax, eax
0x1800515af  js      loc_180051719
0x1800515b5  mov     rax, [rsi]
0x1800515b8  mov     edx, [rsp+0A8h+var_70]
0x1800515bc  dec     edx
0x1800515be  lea     r8, [rsp+0A8h+var_68]
0x1800515c3  mov     rcx, rsi
0x1800515c6  mov     rax, [rax+58h]
0x1800515ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800515cf  mov     edi, eax
0x1800515d1  test    eax, eax
0x1800515d3  js      loc_180051719
0x1800515d9  lea     rdx, aDisable; "Disable"
0x1800515e0  mov     rcx, [rsp+0A8h+var_68]
0x1800515e5  call    cs:__imp__o__wcsicmp
0x1800515ec  nop     dword ptr [rax+rax+00h]
0x1800515f1  test    eax, eax
0x1800515f3  jz      short loc_1800515FF
0x1800515f5  mov     edi, 86000011h
0x1800515fa  jmp     loc_180051719
0x1800515ff  lea     r14, [r13+68h]
0x180051603  lea     r8, aAllowstorageca; "AllowStorageCard"
0x18005160a  mov     [rsp+0A8h+var_68], r8
0x18005160f  lea     r9, [rsp+0A8h+var_78]
0x180051614  lea     rdx, aSystem_0; "System"
0x18005161b  mov     rcx, r14
0x18005161e  call    cs:__imp_?EnterprisePolicyManagerStore_DoesProviderContextSidAreaPolicyValueExist@@YAJPEAUPolicyManagerScopeData@@PEBG1PEAH@Z; EnterprisePolicyManagerStore_DoesProviderContextSidAreaPolicyValueExist(PolicyManagerScopeData *,ushort const *,ushort const *,int *)
0x180051625  nop     dword ptr [rax+rax+00h]
0x18005162a  xor     ebx, ebx
0x18005162c  cmp     [rsp+0A8h+var_78], ebx
0x180051630  jnz     short loc_180051675
0x180051632  mov     dword ptr [rsp+0A8h+pvarg+8], ebx
0x180051636  lea     eax, [rbx+3]
0x180051639  mov     word ptr [rsp+0A8h+pvarg], ax
0x18005163e  mov     [rsp+0A8h+var_88], rbx
0x180051643  lea     r9, [rsp+0A8h+pvarg]
0x180051648  mov     r8, [rsp+0A8h+var_68]
0x18005164d  lea     rdx, aSystem_0; "System"
0x180051654  mov     rcx, r14
0x180051657  call    cs:__imp_?EnterprisePolicyManagerStore_SetProviderContextSidAreaPolicyValue@@YAJPEAUPolicyManagerScopeData@@PEBG1PEAUtagVARIANT@@PEAUDynamicallyAllocatedPolicyData@@@Z; EnterprisePolicyManagerStore_SetProviderContextSidAreaPolicyValue(PolicyManagerScopeData *,ushort const *,ushort const *,tagVARIANT *,DynamicallyAllocatedPolicyData *)
0x18005165e  nop     dword ptr [rax+rax+00h]
0x180051663  mov     edi, eax
0x180051665  test    eax, eax
0x180051667  js      loc_180051719
0x18005166d  mov     [rsp+0A8h+var_78], 1
0x180051675  cmp     [rsp+0A8h+var_74], ebx
0x180051679  jnz     loc_1800515F5
0x18005167f  lea     rcx, [rsp+0A8h+var_60]
0x180051684  call    ?CreateInstance@?$CComObject@VStoragePolicy@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<StoragePolicy>::CreateInstance(ATL::CComObject<StoragePolicy> * *)
0x180051689  mov     edi, eax
0x18005168b  test    eax, eax
0x18005168d  js      loc_180051719
0x180051693  mov     rbx, [rsp+0A8h+var_60]
0x180051698  test    rbx, rbx
0x18005169b  jnz     short loc_1800516A4
0x18005169d  mov     edi, 8007000Eh
0x1800516a2  jmp     short loc_180051719
0x1800516a4  mov     rax, [rbx]
0x1800516a7  mov     r9, r12
0x1800516aa  mov     r8, rsi
0x1800516ad  mov     rdx, r13
0x1800516b0  mov     rcx, rbx
0x1800516b3  mov     rax, [rax+88h]
0x1800516ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516bf  mov     edi, eax
0x1800516c1  test    eax, eax
0x1800516c3  js      short loc_180051719
0x1800516c5  mov     [rbx+80h], r14
0x1800516cc  lea     rcx, [rbx+88h]
0x1800516d3  lea     rdx, aSystem_0; "System"
0x1800516da  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x1800516df  lea     rcx, [rbx+0A8h]
0x1800516e6  mov     rdx, [rsp+0A8h+var_68]
0x1800516eb  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x1800516f0  nop
0x1800516f1  mov     rax, [rbx]
0x1800516f4  mov     rcx, rbx
0x1800516f7  mov     rax, [rax+8]
0x1800516fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051700  mov     [rsp+0A8h+var_60], 0
0x180051709  mov     [r15], rbx
0x18005170c  jmp     short loc_180051719
0x18005170e  mov     edi, [rsp+0A8h+var_74]
0x180051712  jmp     short loc_180051719
0x180051714  mov     edi, 80070057h
0x180051719  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x18005171e  call    cs:__imp_VariantClear
0x180051725  nop     dword ptr [rax+rax+00h]
0x18005172a  nop
0x18005172b  lea     rcx, [rsp+0A8h+var_60]
0x180051730  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x180051735  mov     eax, edi
0x180051737  add     rsp, 70h
0x18005173b  pop     r15
0x18005173d  pop     r14
0x18005173f  pop     r13
0x180051741  pop     r12
0x180051743  pop     rdi
0x180051744  pop     rsi
0x180051745  pop     rbx
0x180051746  retn
```
