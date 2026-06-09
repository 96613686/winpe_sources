# CDMSessionActionsNode::GetValue(tagVARIANT *)

- ea: `0x1800412e0`
- end: `0x1800417a8`
- name: `?GetValue@CDMSessionActionsNode@@UEAAJPEAUtagVARIANT@@@Z`
- size: `1224`
- prototype: `int(CDMSessionActionsNode *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000caf4`
- `0x18000d4d4`
- `0x180025a78`
- `0x180025a9c`
- `0x18002dc38`
- `0x18002dc94`
- `0x18003fa90`
- `0x18003fb20`
- `0x18003fb44`
- `0x1800412e0`
- `0x180041f2c`
- `0x180041fc8`
- `0x180044194`
- `0x180044604`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180041316`
- `OLEAUT32!__imp_VariantInit` at `0x180041588`
- `OLEAUT32!__imp_VariantInit` at `0x180041316`
- `OLEAUT32!__imp_VariantInit` at `0x180041588`
- `OLEAUT32!__imp_VariantClear` at `0x1800415f5`
- `OLEAUT32!__imp_VariantClear` at `0x180041625`
- `OLEAUT32!__imp_VariantClear` at `0x1800415f5`
- `OLEAUT32!__imp_VariantClear` at `0x180041625`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041533`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041533`
- `dmxmlhelputils!XMLHEscapeString` at `0x1800416d1`
- `dmxmlhelputils!XMLHEscapeString` at `0x1800416d1`

## pseudocode

```c
__int64 __fastcall CDMSessionActionsNode::GetValue(CDMSessionActionsNode *this, struct tagVARIANT *a2)
{
  DMSessionActionsHelper *v5; // rcx
  DMSessionActionsHelper *v6; // rcx
  DMSessionActionsHelper *v7; // rcx
  HRESULT DwordRegValue; // ebx
  __int64 v9; // rdx
  const unsigned __int16 *v10; // rbx
  const unsigned __int16 *v11; // rdi
  const unsigned __int16 *v12; // rsi
  DMSessionActionsHelper *v13; // rcx
  int NodeUri; // eax
  struct IConfigManager2 **v15; // r12
  int *i; // rdi
  __int64 v17; // r13
  int v18; // eax
  struct IConfigManager2 *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdx
  struct IConfigManager2 *v22; // rax
  const unsigned __int16 *v23; // r9
  unsigned __int16 *v24; // r8
  int v25; // eax
  const unsigned __int16 *bstrVal; // rdi
  int v27; // eax
  HRESULT v28; // edi
  LONGLONG v29; // rax
  int ppv; // [rsp+20h] [rbp-50h]
  LPVOID *ppvc; // [rsp+20h] [rbp-50h]
  LPVOID *ppvd; // [rsp+20h] [rbp-50h]
  LPVOID *ppve; // [rsp+20h] [rbp-50h]
  LPVOID *ppvf; // [rsp+20h] [rbp-50h]
  int ppva; // [rsp+20h] [rbp-50h]
  int ppvb; // [rsp+20h] [rbp-50h]
  unsigned __int16 *v37; // [rsp+28h] [rbp-48h]
  unsigned __int16 *v38; // [rsp+28h] [rbp-48h]
  unsigned __int16 *v39; // [rsp+28h] [rbp-48h]
  unsigned __int16 *v40; // [rsp+28h] [rbp-48h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  void *v42; // [rsp+48h] [rbp-28h] BYREF
  tagSTGMEDIUM v43; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  char v45; // [rsp+B8h] [rbp+48h] BYREF
  unsigned __int16 *v46; // [rsp+C0h] [rbp+50h] BYREF
  unsigned __int16 *v47; // [rsp+C8h] [rbp+58h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v45 = 0;
  VariantInit(a2);
  if ( *((_DWORD *)this + 11) != 3 )
  {
    if ( *((_DWORD *)this + 11) == 6 )
    {
      v10 = (const unsigned __int16 *)*((_QWORD *)this + 17);
      v11 = (const unsigned __int16 *)*((_QWORD *)this + 16);
      v12 = (const unsigned __int16 *)*((_QWORD *)this + 18);
      v46 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v46,
        0);
      NodeUri = DMSessionActionsHelper::GetNodeUri(v13, &v46, v12, v11, v10);
      DwordRegValue = NodeUri;
      if ( NodeUri >= 0 )
      {
        a2->llVal = (LONGLONG)v46;
        a2->vt = 8;
        v46 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2DB,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionsnode.cpp",
          (const char *)(unsigned int)NodeUri,
          ppva);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v46);
      return (unsigned int)DwordRegValue;
    }
    v5 = (DMSessionActionsHelper *)(unsigned int)(*((_DWORD *)this + 11) - 8);
    if ( *((_DWORD *)this + 11) == 8 )
    {
      v40 = (unsigned __int16 *)*((_QWORD *)this + 16);
      ppvf = (LPVOID *)*((_QWORD *)this + 18);
      LODWORD(v46) = 0;
      DwordRegValue = DMSessionActionsHelper::GetDwordRegValue(
                        v5,
                        (unsigned int *)&v46,
                        qword_180157920,
                        L"MaxSkippedSessionsInLowPowerState",
                        (const unsigned __int16 *)ppvf,
                        v40);
      if ( DwordRegValue < 0 )
      {
        v9 = 745;
        goto LABEL_26;
      }
    }
    else
    {
      v6 = (DMSessionActionsHelper *)(unsigned int)(*((_DWORD *)this + 11) - 9);
      if ( *((_DWORD *)this + 11) == 9 )
      {
        v39 = (unsigned __int16 *)*((_QWORD *)this + 16);
        ppve = (LPVOID *)*((_QWORD *)this + 18);
        LODWORD(v46) = 0;
        DwordRegValue = DMSessionActionsHelper::GetDwordRegValue(
                          v6,
                          (unsigned int *)&v46,
                          qword_180157920,
                          L"MaxTimeSessionsSkippedInLowPowerState",
                          (const unsigned __int16 *)ppve,
                          v39);
        if ( DwordRegValue < 0 )
        {
          v9 = 758;
          goto LABEL_26;
        }
      }
      else
      {
        v7 = (DMSessionActionsHelper *)(unsigned int)(*((_DWORD *)this + 11) - 11);
        if ( *((_DWORD *)this + 11) == 11 )
        {
          v38 = (unsigned __int16 *)*((_QWORD *)this + 16);
          ppvd = (LPVOID *)*((_QWORD *)this + 18);
          LODWORD(v46) = 0;
          DwordRegValue = DMSessionActionsHelper::GetDwordRegValue(
                            v7,
                            (unsigned int *)&v46,
                            qword_180157928,
                            L"WindowSize",
                            (const unsigned __int16 *)ppvd,
                            v38);
          if ( DwordRegValue < 0 )
          {
            v9 = 771;
            goto LABEL_26;
          }
        }
        else
        {
          if ( *((_DWORD *)this + 11) != 12 )
          {
            DwordRegValue = -2046820335;
            v9 = 792;
LABEL_26:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v9,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionsnode.cpp",
              (const char *)(unsigned int)DwordRegValue,
              ppv);
            return (unsigned int)DwordRegValue;
          }
          v37 = (unsigned __int16 *)*((_QWORD *)this + 16);
          ppvc = (LPVOID *)*((_QWORD *)this + 18);
          LODWORD(v46) = 0;
          DwordRegValue = DMSessionActionsHelper::GetDwordRegValue(
                            v7,
                            (unsigned int *)&v46,
                            qword_180157928,
                            L"MaxBatchSize",
                            (const unsigned __int16 *)ppvc,
                            v37);
          if ( DwordRegValue < 0 )
          {
            v9 = 784;
            goto LABEL_26;
          }
        }
      }
    }
    a2->lVal = (int)v46;
    a2->vt = 3;
    return (unsigned int)DwordRegValue;
  }
  if ( *((_QWORD *)this + 20) )
  {
    v15 = (struct IConfigManager2 **)((char *)this + 168);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease((char *)this + 168);
    DwordRegValue = CoCreateInstance(
                      &GUID_66d0db14_5638_475f_a386_629522d8c461,
                      0,
                      1u,
                      &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
                      (LPVOID *)this + 21);
    if ( DwordRegValue < 0 )
    {
      v9 = 656;
      goto LABEL_26;
    }
    for ( i = (int *)&g_omaDmSessionVariableNames; i != &dword_180155958; i += 2 )
    {
      v17 = *(_QWORD *)i;
      VariantInit(&pvarg);
      v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, VARIANTARG *))(**((_QWORD **)this + 20) + 32LL))(
              *((_QWORD *)this + 20),
              v17,
              &pvarg);
      DwordRegValue = v18;
      if ( v18 < 0 )
      {
        if ( v18 != -2147023728 )
        {
          v21 = 674;
          goto LABEL_36;
        }
      }
      else
      {
        v19 = *v15;
        v20 = *(_QWORD *)*v15;
        v43 = (tagSTGMEDIUM)pvarg;
        v18 = (*(__int64 (__fastcall **)(struct IConfigManager2 *, __int64, tagSTGMEDIUM *))(v20 + 104))(v19, v17, &v43);
        DwordRegValue = v18;
        if ( v18 < 0 )
        {
          v21 = 666;
LABEL_36:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v21,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionsnode.cpp",
            (const char *)(unsigned int)v18,
            ppv);
          VariantClear(&pvarg);
          return (unsigned int)DwordRegValue;
        }
      }
      VariantClear(&pvarg);
    }
    v22 = *v15;
    v23 = (const unsigned __int16 *)*((_QWORD *)this + 16);
    v24 = (unsigned __int16 *)*((_QWORD *)this + 18);
    v42 = 0;
    v25 = DMSessionActionsHelper::BuildAlertXml((DMSessionActionsHelper *)&v45, &v42, v24, v23, v22);
    DwordRegValue = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B0,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionsnode.cpp",
        (const char *)(unsigned int)v25,
        ppvb);
LABEL_50:
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v42);
      return (unsigned int)DwordRegValue;
    }
    v47 = 0;
    if ( !v42 )
      goto LABEL_45;
    *(_QWORD *)&v43.tymed = 0;
    v43.pUnkForRelease = 0;
    v43.hBitmap = (HBITMAP)v42;
    wil::unique_hglobal_locked::unique_hglobal_locked((wil::unique_hglobal_locked *)&pvarg, &v43);
    bstrVal = pvarg.bstrVal;
    if ( pvarg.llVal )
    {
      LODWORD(v46) = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v47,
        0);
      v27 = XMLHEscapeString(bstrVal, &v47, (unsigned int *)&v46);
      v28 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2C0,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionsnode.cpp",
          (const char *)(unsigned int)v27,
          ppvb);
        wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pvarg);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v47);
        DwordRegValue = v28;
        goto LABEL_50;
      }
      bstrVal = v47;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pvarg);
    if ( !bstrVal )
LABEL_45:
      bstrVal = &Class;
    wil::make_bstr_nothrow(&pvarg, bstrVal);
    v29 = *(_QWORD *)&pvarg.vt;
    if ( *(_QWORD *)&pvarg.vt )
    {
      a2->vt = 8;
      *(_QWORD *)&pvarg.vt = 0;
      a2->llVal = v29;
    }
    else
    {
      DwordRegValue = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2CB,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionsnode.cpp",
        (const char *)0x8007000ELL,
        ppvb);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pvarg);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v47);
    goto LABEL_50;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x1800412e0  mov     [rsp-38h+arg_0], rbx
0x1800412e5  push    rbp
0x1800412e6  push    rsi
0x1800412e7  push    rdi
0x1800412e8  push    r12
0x1800412ea  push    r13
0x1800412ec  push    r14
0x1800412ee  push    r15
0x1800412f0  mov     rbp, rsp
0x1800412f3  sub     rsp, 70h
0x1800412f7  xor     r13d, r13d
0x1800412fa  mov     r14, rdx
0x1800412fd  mov     rsi, rcx
0x180041300  test    rdx, rdx
0x180041303  jnz     short loc_18004130F
0x180041305  mov     eax, 80070057h
0x18004130a  jmp     loc_18004178F
0x18004130f  mov     rcx, r14; pvarg
0x180041312  mov     [rbp+arg_8], r13b
0x180041316  call    cs:__imp_VariantInit
0x18004131d  nop     dword ptr [rax+rax+00h]
0x180041322  mov     ecx, [rsi+2Ch]
0x180041325  mov     edi, 3
0x18004132a  sub     ecx, edi
0x18004132c  jz      loc_1800414FE
0x180041332  sub     ecx, edi
0x180041334  jz      loc_180041489
0x18004133a  sub     ecx, 2; this
0x18004133d  jz      loc_180041436
0x180041343  sub     ecx, 1; this
0x180041346  jz      loc_1800413F3
0x18004134c  sub     ecx, 2; this
0x18004134f  jz      short loc_1800413AC
0x180041351  cmp     ecx, 1
0x180041354  jz      short loc_180041365
0x180041356  mov     ebx, 86000011h
0x18004135b  mov     edx, 318h
0x180041360  jmp     loc_18004154A
0x180041365  mov     rax, [rsi+80h]
0x18004136c  lea     r9, aMaxbatchsize_0; "MaxBatchSize"
0x180041373  mov     r8, cs:qword_180157928; unsigned __int16 *
0x18004137a  lea     rdx, [rbp+arg_10]; unsigned int *
0x18004137e  mov     [rsp+70h+var_48], rax; unsigned __int16 *
0x180041383  mov     rax, [rsi+90h]
0x18004138a  mov     [rsp+70h+ppv], rax; unsigned __int16 *
0x18004138f  mov     dword ptr [rbp+arg_10], r13d
0x180041393  call    ?GetDwordRegValue@DMSessionActionsHelper@@QEAAJPEAKPEBG111@Z; DMSessionActionsHelper::GetDwordRegValue(ulong *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180041398  mov     ebx, eax
0x18004139a  test    eax, eax
0x18004139c  jns     loc_180041479
0x1800413a2  mov     edx, 310h
0x1800413a7  jmp     loc_18004154A
0x1800413ac  mov     rax, [rsi+80h]
0x1800413b3  lea     r9, aWindowsize_0; "WindowSize"
0x1800413ba  mov     r8, cs:qword_180157928; unsigned __int16 *
0x1800413c1  lea     rdx, [rbp+arg_10]; unsigned int *
0x1800413c5  mov     [rsp+70h+var_48], rax; unsigned __int16 *
0x1800413ca  mov     rax, [rsi+90h]
0x1800413d1  mov     [rsp+70h+ppv], rax; unsigned __int16 *
0x1800413d6  mov     dword ptr [rbp+arg_10], r13d
0x1800413da  call    ?GetDwordRegValue@DMSessionActionsHelper@@QEAAJPEAKPEBG111@Z; DMSessionActionsHelper::GetDwordRegValue(ulong *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800413df  mov     ebx, eax
0x1800413e1  test    eax, eax
0x1800413e3  jns     loc_180041479
0x1800413e9  mov     edx, 303h
0x1800413ee  jmp     loc_18004154A
0x1800413f3  mov     rax, [rsi+80h]
0x1800413fa  lea     r9, aMaxtimesession_0; "MaxTimeSessionsSkippedInLowPowerState"
0x180041401  mov     r8, cs:qword_180157920; unsigned __int16 *
0x180041408  lea     rdx, [rbp+arg_10]; unsigned int *
0x18004140c  mov     [rsp+70h+var_48], rax; unsigned __int16 *
0x180041411  mov     rax, [rsi+90h]
0x180041418  mov     [rsp+70h+ppv], rax; unsigned __int16 *
0x18004141d  mov     dword ptr [rbp+arg_10], r13d
0x180041421  call    ?GetDwordRegValue@DMSessionActionsHelper@@QEAAJPEAKPEBG111@Z; DMSessionActionsHelper::GetDwordRegValue(ulong *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180041426  mov     ebx, eax
0x180041428  test    eax, eax
0x18004142a  jns     short loc_180041479
0x18004142c  mov     edx, 2F6h
0x180041431  jmp     loc_18004154A
0x180041436  mov     rax, [rsi+80h]
0x18004143d  lea     r9, aMaxskippedsess_0; "MaxSkippedSessionsInLowPowerState"
0x180041444  mov     r8, cs:qword_180157920; unsigned __int16 *
0x18004144b  lea     rdx, [rbp+arg_10]; unsigned int *
0x18004144f  mov     [rsp+70h+var_48], rax; unsigned __int16 *
0x180041454  mov     rax, [rsi+90h]
0x18004145b  mov     [rsp+70h+ppv], rax; unsigned __int16 *
0x180041460  mov     dword ptr [rbp+arg_10], r13d
0x180041464  call    ?GetDwordRegValue@DMSessionActionsHelper@@QEAAJPEAKPEBG111@Z; DMSessionActionsHelper::GetDwordRegValue(ulong *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180041469  mov     ebx, eax
0x18004146b  test    eax, eax
0x18004146d  jns     short loc_180041479
0x18004146f  mov     edx, 2E9h
0x180041474  jmp     loc_18004154A
0x180041479  mov     eax, dword ptr [rbp+arg_10]
0x18004147c  mov     [r14+8], eax
0x180041480  mov     [r14], di
0x180041484  jmp     loc_18004155D
0x180041489  mov     rbx, [rsi+88h]
0x180041490  lea     rcx, [rbp+arg_10]
0x180041494  mov     rdi, [rsi+80h]
0x18004149b  xor     edx, edx
0x18004149d  mov     rsi, [rsi+90h]
0x1800414a4  mov     [rbp+arg_10], r13
0x1800414a8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800414ad  mov     r9, rdi; unsigned __int16 *
0x1800414b0  mov     [rsp+70h+ppv], rbx; int
0x1800414b5  mov     r8, rsi; unsigned __int16 *
0x1800414b8  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x1800414bc  call    ?GetNodeUri@DMSessionActionsHelper@@QEAAJPEAPEAGPEBG11@Z; DMSessionActionsHelper::GetNodeUri(ushort * *,ushort const *,ushort const *,ushort const *)
0x1800414c1  mov     ebx, eax
0x1800414c3  test    eax, eax
0x1800414c5  jns     short loc_1800414EA
0x1800414c7  mov     rcx, [rbp+38h]; this
0x1800414cb  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800414d2  mov     r9d, eax; char *
0x1800414d5  mov     edx, 2DBh; void *
0x1800414da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800414df  lea     rcx, [rbp+arg_10]
0x1800414e3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800414e8  jmp     short loc_18004155D
0x1800414ea  mov     rax, [rbp+arg_10]
0x1800414ee  mov     [r14+8], rax
0x1800414f2  mov     word ptr [r14], 8
0x1800414f8  mov     [rbp+arg_10], r13
0x1800414fc  jmp     short loc_1800414DF
0x1800414fe  cmp     [rsi+0A0h], r13
0x180041505  jz      loc_18004178A
0x18004150b  lea     r12, [rsi+0A8h]
0x180041512  mov     rcx, r12
0x180041515  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18004151a  xor     edx, edx; pUnkOuter
0x18004151c  mov     [rsp+70h+ppv], r12; int
0x180041521  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180041528  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x18004152f  lea     r8d, [rdx+1]; dwClsContext
0x180041533  call    cs:__imp_CoCreateInstance
0x18004153a  nop     dword ptr [rax+rax+00h]
0x18004153f  mov     ebx, eax
0x180041541  test    eax, eax
0x180041543  jns     short loc_180041564
0x180041545  mov     edx, 290h; void *
0x18004154a  mov     rcx, [rbp+38h]; this
0x18004154e  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180041555  mov     r9d, ebx; char *
0x180041558  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004155d  mov     eax, ebx
0x18004155f  jmp     loc_18004178F
0x180041564  lea     rdi, ?g_omaDmSessionVariableNames@@3PAPEBGA; ushort const * near * g_omaDmSessionVariableNames
0x18004156b  mov     r15d, 8
0x180041571  lea     rax, dword_180155958
0x180041578  cmp     rdi, rax
0x18004157b  jz      loc_180041636
0x180041581  mov     r13, [rdi]
0x180041584  lea     rcx, [rbp+pvarg]; pvarg
0x180041588  call    cs:__imp_VariantInit
0x18004158f  nop     dword ptr [rax+rax+00h]
0x180041594  mov     rcx, [rsi+0A0h]
0x18004159b  lea     r8, [rbp+pvarg]
0x18004159f  mov     rdx, r13
0x1800415a2  mov     rax, [rcx]
0x1800415a5  mov     rax, [rax+20h]
0x1800415a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800415ae  mov     ebx, eax
0x1800415b0  test    eax, eax
0x1800415b2  js      short loc_1800415EA
0x1800415b4  mov     rcx, [r12]
0x1800415b8  lea     r8, [rbp+var_20]
0x1800415bc  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800415c0  mov     rdx, r13
0x1800415c3  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800415c8  mov     rax, [rcx]
0x1800415cb  movaps  xmmword ptr [rbp+var_20.tymed], xmm0
0x1800415cf  movsd   [rbp+var_20.pUnkForRelease], xmm1
0x1800415d4  mov     rax, [rax+68h]
0x1800415d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800415dd  mov     ebx, eax
0x1800415df  test    eax, eax
0x1800415e1  jns     short loc_1800415F1
0x1800415e3  mov     edx, 29Ah
0x1800415e8  jmp     short loc_18004160E
0x1800415ea  cmp     eax, 80070490h
0x1800415ef  jnz     short loc_180041609
0x1800415f1  lea     rcx, [rbp+pvarg]; pvarg
0x1800415f5  call    cs:__imp_VariantClear
0x1800415fc  nop     dword ptr [rax+rax+00h]
0x180041601  add     rdi, r15
0x180041604  jmp     loc_180041571
0x180041609  mov     edx, 2A2h; void *
0x18004160e  mov     rcx, [rbp+38h]; this
0x180041612  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180041619  mov     r9d, eax; char *
0x18004161c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041621  lea     rcx, [rbp+pvarg]; pvarg
0x180041625  call    cs:__imp_VariantClear
0x18004162c  nop     dword ptr [rax+rax+00h]
0x180041631  jmp     loc_18004155D
0x180041636  mov     rax, [r12]
0x18004163a  lea     rdx, [rbp+var_28]; void **
0x18004163e  mov     r9, [rsi+80h]; unsigned __int16 *
0x180041645  lea     rcx, [rbp+arg_8]; this
0x180041649  mov     r8, [rsi+90h]; unsigned __int16 *
0x180041650  xor     r13d, r13d
0x180041653  mov     [rbp+var_28], r13
0x180041657  mov     [rsp+70h+ppv], rax; int
0x18004165c  call    ?BuildAlertXml@DMSessionActionsHelper@@QEAAJPEAPEAXPEBG1PEAUIConfigManager2@@@Z; DMSessionActionsHelper::BuildAlertXml(void * *,ushort const *,ushort const *,IConfigManager2 *)
0x180041661  mov     ebx, eax
0x180041663  test    eax, eax
0x180041665  jns     short loc_180041684
0x180041667  mov     rcx, [rbp+38h]; this
0x18004166b  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180041672  mov     r9d, eax; char *
0x180041675  mov     edx, 2B0h; void *
0x18004167a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004167f  jmp     loc_18004177C
0x180041684  mov     rax, [rbp+var_28]
0x180041688  mov     [rbp+arg_18], r13
0x18004168c  test    rax, rax
0x18004168f  jz      loc_180041723
0x180041695  lea     rdx, [rbp+var_20]; struct tagSTGMEDIUM *
0x180041699  mov     qword ptr [rbp+var_20.tymed], r13
0x18004169d  lea     rcx, [rbp+pvarg]; this
0x1800416a1  mov     [rbp+var_20.pUnkForRelease], r13
0x1800416a5  mov     qword ptr [rbp+var_20.8], rax
0x1800416a9  call    ??0unique_hglobal_locked@wil@@QEAA@AEAUtagSTGMEDIUM@@@Z; wil::unique_hglobal_locked::unique_hglobal_locked(tagSTGMEDIUM &)
0x1800416ae  mov     rdi, qword ptr [rbp+pvarg+8]
0x1800416b2  test    rdi, rdi
0x1800416b5  jz      short loc_180041715
0x1800416b7  xor     edx, edx
0x1800416b9  mov     dword ptr [rbp+arg_10], r13d
0x1800416bd  lea     rcx, [rbp+arg_18]
0x1800416c1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800416c6  lea     r8, [rbp+arg_10]
0x1800416ca  mov     rcx, rdi
0x1800416cd  lea     rdx, [rbp+arg_18]
0x1800416d1  call    cs:__imp_?XMLHEscapeString@@YAJPEBGPEAPEAGPEAK@Z; XMLHEscapeString(ushort const *,ushort * *,ulong *)
0x1800416d8  nop     dword ptr [rax+rax+00h]
0x1800416dd  mov     edi, eax
0x1800416df  test    eax, eax
0x1800416e1  jns     short loc_180041711
0x1800416e3  mov     rcx, [rbp+38h]; this
0x1800416e7  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800416ee  mov     r9d, eax; char *
0x1800416f1  mov     edx, 2C0h; void *
0x1800416f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800416fb  lea     rcx, [rbp+pvarg]
0x1800416ff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?GlobalUnlock@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180041704  lea     rcx, [rbp+arg_18]
0x180041708  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004170d  mov     ebx, edi
0x18004170f  jmp     short loc_18004177C
0x180041711  mov     rdi, [rbp+arg_18]
0x180041715  lea     rcx, [rbp+pvarg]
0x180041719  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?GlobalUnlock@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004171e  test    rdi, rdi
0x180041721  jnz     short loc_18004172A
0x180041723  lea     rdi, Class
0x18004172a  mov     rdx, rdi
0x18004172d  lea     rcx, [rbp+pvarg]
0x180041731  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x180041736  mov     rax, qword ptr [rbp+pvarg]
0x18004173a  test    rax, rax
0x18004173d  jz      short loc_18004174D
0x18004173f  mov     [r14], r15w
0x180041743  mov     qword ptr [rbp+pvarg], r13
0x180041747  mov     [r14+8], rax
0x18004174b  jmp     short loc_18004176A
0x18004174d  mov     rcx, [rbp+38h]; this
0x180041751  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180041758  mov     ebx, 8007000Eh
0x18004175d  mov     edx, 2CBh; void *
0x180041762  mov     r9d, ebx; char *
0x180041765  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004176a  lea     rcx, [rbp+pvarg]
0x18004176e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180041773  lea     rcx, [rbp+arg_18]
0x180041777  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004177c  lea     rcx, [rbp+var_28]
0x180041780  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?GlobalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180041785  jmp     loc_18004155D
0x18004178a  mov     eax, 8000FFFFh
0x18004178f  mov     rbx, [rsp+70h+arg_0]
0x180041797  add     rsp, 70h
0x18004179b  pop     r15
0x18004179d  pop     r14
0x18004179f  pop     r13
0x1800417a1  pop     r12
0x1800417a3  pop     rdi
0x1800417a4  pop     rsi
0x1800417a5  pop     rbp
0x1800417a6  retn
```
