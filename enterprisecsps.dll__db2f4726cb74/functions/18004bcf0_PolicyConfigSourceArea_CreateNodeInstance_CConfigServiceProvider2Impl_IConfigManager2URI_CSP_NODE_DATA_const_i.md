# PolicyConfigSourceArea::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x18004bcf0`
- end: `0x18004bf0e`
- name: `?CreateNodeInstance@PolicyConfigSourceArea@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `542`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, int, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004b140`

## callees

- `0x18001a4fc`
- `0x180023fa0`
- `0x18004b544`
- `0x18004bcf0`
- `0x180107010`

## import_xrefs

- `policymanager!EnterprisePolicyManagerStore_IsPolicyAreaForIngestedAdmx` at `0x18004bdc9`
- `policymanager!EnterprisePolicyManagerStore_IsPolicyAreaForIngestedAdmx` at `0x18004bdc9`
- `policymanager!EnterprisePolicyManagerStore_EnsureProviderContextSidAreaExist` at `0x18004be39`
- `policymanager!EnterprisePolicyManagerStore_EnsureProviderContextSidAreaExist` at `0x18004be39`
- `policymanager!EnterprisePolicyManagerStore_CSPConfigSourceAreaCreateNodeInstance` at `0x18004be03`
- `policymanager!EnterprisePolicyManagerStore_CSPConfigSourceAreaCreateNodeInstance` at `0x18004be03`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PolicyConfigSourceArea::CreateNodeInstance(
        struct CConfigServiceProvider2Impl *a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        int a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  struct ICSPNode **v10; // r15
  unsigned int *v11; // rax
  int IsPolicyAreaForIngestedAdmx; // edi
  struct ICSPNode *v13; // rbx
  int v15; // [rsp+30h] [rbp-48h] BYREF
  int v16; // [rsp+34h] [rbp-44h] BYREF
  const unsigned __int16 *v17; // [rsp+38h] [rbp-40h] BYREF
  _QWORD v18[2]; // [rsp+40h] [rbp-38h] BYREF
  int v19; // [rsp+80h] [rbp+8h] BYREF

  v17 = 0;
  v15 = 0;
  v19 = 0;
  v18[0] = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        v10 = a5;
        if ( a5 )
        {
          v11 = a6;
          if ( a6 )
          {
            *a5 = 0;
            *v11 = 0;
            IsPolicyAreaForIngestedAdmx = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(
                                            a2,
                                            &v15);
            if ( IsPolicyAreaForIngestedAdmx < 0 )
              goto LABEL_27;
            IsPolicyAreaForIngestedAdmx = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, const unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
                                            a2,
                                            (unsigned int)(v15 - 1),
                                            &v17);
            if ( IsPolicyAreaForIngestedAdmx < 0 )
              goto LABEL_27;
            if ( *((_DWORD *)a3 + 3) != 34 )
              goto LABEL_13;
            v16 = 0;
            IsPolicyAreaForIngestedAdmx = EnterprisePolicyManagerStore_IsPolicyAreaForIngestedAdmx(v17, &v16);
            if ( IsPolicyAreaForIngestedAdmx < 0 )
              goto LABEL_27;
            if ( v16 && *((_DWORD *)a1 + 48) == 1 )
LABEL_13:
              IsPolicyAreaForIngestedAdmx = EnterprisePolicyManagerStore_CSPConfigSourceAreaCreateNodeInstance(
                                              (struct CConfigServiceProvider2Impl *)((char *)a1 + 104),
                                              v17,
                                              &v19);
            else
              IsPolicyAreaForIngestedAdmx = -2046820350;
            if ( IsPolicyAreaForIngestedAdmx >= 0 )
            {
              if ( v19 )
              {
                if ( a4 )
                {
                  IsPolicyAreaForIngestedAdmx = -2046820335;
                  goto LABEL_27;
                }
              }
              else
              {
                if ( !a4 )
                {
                  IsPolicyAreaForIngestedAdmx = -2046820350;
                  goto LABEL_27;
                }
                IsPolicyAreaForIngestedAdmx = EnterprisePolicyManagerStore_EnsureProviderContextSidAreaExist(
                                                (struct CConfigServiceProvider2Impl *)((char *)a1 + 104),
                                                v17);
                if ( IsPolicyAreaForIngestedAdmx < 0 )
                  goto LABEL_27;
              }
              IsPolicyAreaForIngestedAdmx = ATL::CComObject<PolicyConfigSourceArea>::CreateInstance(v18);
              if ( IsPolicyAreaForIngestedAdmx >= 0 )
              {
                v13 = (struct ICSPNode *)v18[0];
                if ( v18[0] )
                {
                  IsPolicyAreaForIngestedAdmx = (*(__int64 (__fastcall **)(_QWORD, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*(_QWORD *)v18[0] + 136LL))(
                                                  v18[0],
                                                  a1,
                                                  a2,
                                                  a3);
                  if ( IsPolicyAreaForIngestedAdmx >= 0 )
                  {
                    *((_QWORD *)v13 + 16) = (char *)a1 + 104;
                    try
                    {
                      std::wstring::operator=((char *)v13 + 136, v17);
                    }
                    catch ( std::bad_alloc )
                    {
                      v16 = -2147024882;
                      IsPolicyAreaForIngestedAdmx = -2147024882;
                      goto LABEL_27;
                    }
                    (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v13 + 8LL))(v13);
                    v18[0] = 0;
                    *v10 = v13;
                  }
                }
                else
                {
                  IsPolicyAreaForIngestedAdmx = -2147024882;
                }
              }
            }
LABEL_27:
            ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(v18);
            return (unsigned int)IsPolicyAreaForIngestedAdmx;
          }
        }
      }
    }
  }
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(v18);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18004bcf0  mov     rax, rsp
0x18004bcf3  mov     [rax+10h], rbx
0x18004bcf7  mov     [rax+18h], rsi
0x18004bcfb  push    rdi
0x18004bcfc  push    r12
0x18004bcfe  push    r13
0x18004bd00  push    r14
0x18004bd02  push    r15
0x18004bd04  sub     rsp, 50h
0x18004bd08  mov     ebx, r9d
0x18004bd0b  mov     r12, r8
0x18004bd0e  mov     r14, rdx
0x18004bd11  mov     r13, rcx
0x18004bd14  xor     esi, esi
0x18004bd16  mov     [rax-40h], rsi
0x18004bd1a  mov     [rax-48h], esi
0x18004bd1d  mov     [rax+8], esi
0x18004bd20  mov     [rax-38h], rsi
0x18004bd24  test    rcx, rcx
0x18004bd27  jz      loc_18004BEE4
0x18004bd2d  test    rdx, rdx
0x18004bd30  jz      loc_18004BEE4
0x18004bd36  test    r8, r8
0x18004bd39  jz      loc_18004BEE4
0x18004bd3f  mov     r15, [rsp+78h+arg_20]
0x18004bd47  test    r15, r15
0x18004bd4a  jz      loc_18004BEE4
0x18004bd50  mov     rax, [rsp+78h+arg_28]
0x18004bd58  test    rax, rax
0x18004bd5b  jz      loc_18004BEE4
0x18004bd61  mov     [r15], rsi
0x18004bd64  mov     [rax], esi
0x18004bd66  mov     rax, [rdx]
0x18004bd69  lea     rdx, [rsp+78h+var_48]
0x18004bd6e  mov     rcx, r14
0x18004bd71  mov     rax, [rax+88h]
0x18004bd78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd7d  mov     edi, eax
0x18004bd7f  test    eax, eax
0x18004bd81  js      loc_18004BED6
0x18004bd87  mov     rax, [r14]
0x18004bd8a  mov     edx, [rsp+78h+var_48]
0x18004bd8e  dec     edx
0x18004bd90  lea     r8, [rsp+78h+var_40]
0x18004bd95  mov     rcx, r14
0x18004bd98  mov     rax, [rax+58h]
0x18004bd9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bda1  mov     edi, eax
0x18004bda3  test    eax, eax
0x18004bda5  js      loc_18004BED6
0x18004bdab  lea     rsi, [r13+68h]
0x18004bdaf  cmp     dword ptr [r12+0Ch], 22h ; '"'
0x18004bdb5  jnz     short loc_18004BDF3
0x18004bdb7  mov     [rsp+78h+var_44], 0
0x18004bdbf  lea     rdx, [rsp+78h+var_44]
0x18004bdc4  mov     rcx, [rsp+78h+var_40]
0x18004bdc9  call    cs:__imp_?EnterprisePolicyManagerStore_IsPolicyAreaForIngestedAdmx@@YAJPEBGPEAH@Z; EnterprisePolicyManagerStore_IsPolicyAreaForIngestedAdmx(ushort const *,int *)
0x18004bdd0  nop     dword ptr [rax+rax+00h]
0x18004bdd5  mov     edi, eax
0x18004bdd7  test    eax, eax
0x18004bdd9  js      loc_18004BED6
0x18004bddf  cmp     [rsp+78h+var_44], 0
0x18004bde4  jz      short loc_18004BDEC
0x18004bde6  cmp     dword ptr [rsi+58h], 1
0x18004bdea  jz      short loc_18004BDF3
0x18004bdec  mov     edi, 86000002h
0x18004bdf1  jmp     short loc_18004BE11
0x18004bdf3  lea     r8, [rsp+78h+arg_0]
0x18004bdfb  mov     rdx, [rsp+78h+var_40]
0x18004be00  mov     rcx, rsi
0x18004be03  call    cs:__imp_?EnterprisePolicyManagerStore_CSPConfigSourceAreaCreateNodeInstance@@YAJPEAUPolicyManagerScopeData@@PEBGPEAH@Z; EnterprisePolicyManagerStore_CSPConfigSourceAreaCreateNodeInstance(PolicyManagerScopeData *,ushort const *,int *)
0x18004be0a  nop     dword ptr [rax+rax+00h]
0x18004be0f  mov     edi, eax
0x18004be11  test    edi, edi
0x18004be13  js      loc_18004BED6
0x18004be19  cmp     [rsp+78h+arg_0], 0
0x18004be21  jnz     short loc_18004BE70
0x18004be23  test    ebx, ebx
0x18004be25  jnz     short loc_18004BE31
0x18004be27  mov     edi, 86000002h
0x18004be2c  jmp     loc_18004BED6
0x18004be31  mov     rdx, [rsp+78h+var_40]
0x18004be36  mov     rcx, rsi
0x18004be39  call    cs:__imp_?EnterprisePolicyManagerStore_EnsureProviderContextSidAreaExist@@YAJPEAUPolicyManagerScopeData@@PEBG@Z; EnterprisePolicyManagerStore_EnsureProviderContextSidAreaExist(PolicyManagerScopeData *,ushort const *)
0x18004be40  nop     dword ptr [rax+rax+00h]
0x18004be45  mov     edi, eax
0x18004be47  test    eax, eax
0x18004be49  js      loc_18004BED6
0x18004be4f  lea     rcx, [rsp+78h+var_38]
0x18004be54  call    ?CreateInstance@?$CComObject@VPolicyConfigSourceArea@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<PolicyConfigSourceArea>::CreateInstance(ATL::CComObject<PolicyConfigSourceArea> * *)
0x18004be59  mov     edi, eax
0x18004be5b  test    eax, eax
0x18004be5d  js      short loc_18004BED6
0x18004be5f  mov     rbx, [rsp+78h+var_38]
0x18004be64  test    rbx, rbx
0x18004be67  jnz     short loc_18004BE7B
0x18004be69  mov     edi, 8007000Eh
0x18004be6e  jmp     short loc_18004BED6
0x18004be70  test    ebx, ebx
0x18004be72  jz      short loc_18004BE4F
0x18004be74  mov     edi, 86000011h
0x18004be79  jmp     short loc_18004BED6
0x18004be7b  mov     rax, [rbx]
0x18004be7e  mov     r9, r12
0x18004be81  mov     r8, r14
0x18004be84  mov     rdx, r13
0x18004be87  mov     rcx, rbx
0x18004be8a  mov     rax, [rax+88h]
0x18004be91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be96  mov     edi, eax
0x18004be98  test    eax, eax
0x18004be9a  js      short loc_18004BED6
0x18004be9c  mov     [rbx+80h], rsi
0x18004bea3  lea     rcx, [rbx+88h]
0x18004beaa  mov     rdx, [rsp+78h+var_40]
0x18004beaf  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x18004beb4  nop
0x18004beb5  mov     rax, [rbx]
0x18004beb8  mov     rcx, rbx
0x18004bebb  mov     rax, [rax+8]
0x18004bebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bec4  mov     [rsp+78h+var_38], 0
0x18004becd  mov     [r15], rbx
0x18004bed0  jmp     short loc_18004BED6
0x18004bed2  mov     edi, [rsp+78h+var_44]
0x18004bed6  lea     rcx, [rsp+78h+var_38]
0x18004bedb  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x18004bee0  mov     eax, edi
0x18004bee2  jmp     short loc_18004BEF3
0x18004bee4  lea     rcx, [rsp+78h+var_38]
0x18004bee9  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x18004beee  mov     eax, 80070057h
0x18004bef3  lea     r11, [rsp+78h+var_28]
0x18004bef8  mov     rbx, [r11+38h]
0x18004befc  mov     rsi, [r11+40h]
0x18004bf00  mov     rsp, r11
0x18004bf03  pop     r15
0x18004bf05  pop     r14
0x18004bf07  pop     r13
0x18004bf09  pop     r12
0x18004bf0b  pop     rdi
0x18004bf0c  retn
```
