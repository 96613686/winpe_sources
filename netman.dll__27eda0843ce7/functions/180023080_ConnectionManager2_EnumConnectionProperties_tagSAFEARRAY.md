# ConnectionManager2::EnumConnectionProperties(tagSAFEARRAY * *)

- ea: `0x180023080`
- end: `0x180023474`
- name: `?EnumConnectionProperties@ConnectionManager2@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `1012`
- prototype: `__int64 __fastcall(ConnectionManager2 *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001710`
- `0x180002320`
- `0x1800043a8`
- `0x18000538c`
- `0x180008168`
- `0x180019200`
- `0x180019c68`
- `0x18001e124`
- `0x180023080`
- `0x1800306f8`
- `0x180030714`
- `0x180031d0c`
- `0x180031d44`
- `0x18003202c`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023212`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023212`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023126`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023126`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002326e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002326e`
- `OLEAUT32!__imp_VariantInit` at `0x180023352`
- `OLEAUT32!__imp_VariantInit` at `0x180023352`
- `OLEAUT32!__imp_VariantClear` at `0x180023380`
- `OLEAUT32!__imp_VariantClear` at `0x180023380`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180023311`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180023311`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180023374`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180023374`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ConnectionManager2::EnumConnectionProperties(ConnectionManager2 *this, struct tagSAFEARRAY **a2)
{
  PVOID *v3; // rcx
  HRESULT v4; // edi
  _QWORD *v5; // rax
  SAFEARRAY *v6; // rax
  __int64 **v7; // rcx
  __int64 **v8; // rbx
  HRESULT v9; // esi
  SAFEARRAY *v10; // rcx
  __int64 **i; // rbx
  __int64 *v12; // rcx
  __int64 *v13; // rbx
  PVOID *v14; // rcx
  void *pv; // [rsp+30h] [rbp-59h] BYREF
  struct tagNETCON_PROPERTIES *v17; // [rsp+38h] [rbp-51h] BYREF
  struct IUnknown *v18; // [rsp+40h] [rbp-49h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-41h] BYREF
  int v20; // [rsp+60h] [rbp-29h] BYREF
  LONG rgIndices[2]; // [rsp+68h] [rbp-21h] BYREF
  __int128 v22; // [rsp+70h] [rbp-19h] BYREF
  __int64 v23; // [rsp+80h] [rbp-9h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp-1h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+90h] [rbp+7h] BYREF

  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b09e5d3fdceb38afdbed09c2b50fca1c_Traceguids);
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 )
      WPP_SF_(v3[2], 11, WPP_b09e5d3fdceb38afdbed09c2b50fca1c_Traceguids);
  }
  ppv = 0;
  pv = 0;
  v4 = CoCreateInstance(&CLSID_ConnectionManager, 0, 3u, &GUID_c08956a2_1cd3_11d1_b1c5_00805fc1270e, &ppv);
  if ( v4 >= 0 )
  {
    v23 = 0;
    v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, 0, &v23);
    if ( v4 >= 0 )
    {
      v18 = 0;
      v20 = 0;
      v22 = 0;
      v5 = MemAlloc(0x18u);
      *v5 = v5;
      v5[1] = v5;
      *(_QWORD *)&v22 = v5;
      do
      {
        if ( (*(unsigned int (__fastcall **)(__int64, __int64, struct IUnknown **, int *))(*(_QWORD *)v23 + 24LL))(
               v23,
               1,
               &v18,
               &v20)
          || !v20 )
        {
          break;
        }
        rgsabound = 0;
        if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, SAFEARRAYBOUND *))v18->lpVtbl->QueryInterface)(
               v18,
               &GUID_faedcf6a_31fe_11d1_aad2_00805fc1270e,
               &rgsabound) < 0 )
        {
          v17 = 0;
          v4 = ((__int64 (__fastcall *)(struct IUnknown *, struct tagNETCON_PROPERTIES **))v18->lpVtbl[2].AddRef)(
                 v18,
                 &v17);
          if ( v4 >= 0 )
          {
            pv = CoTaskMemAlloc(0x68u);
            if ( pv )
            {
              *(_QWORD *)rgIndices = 0;
              v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, LONG *))v18->lpVtbl->QueryInterface)(
                     v18,
                     &GUID_faedcf59_31fe_11d1_aad2_00805fc1270e,
                     rgIndices);
              if ( v4 >= 0 )
              {
                memset_0(pv, 0, 0x68u);
                v4 = HrBuildPropertiesExFromProperties(
                       v17,
                       (struct tagNETCON_PROPERTIES_EX *)pv,
                       *(struct IPersistNetConnection **)rgIndices);
              }
              if ( v4 )
              {
                CoTaskMemFree(pv);
                pv = 0;
              }
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(rgIndices);
            }
            else
            {
              v4 = -2147024882;
            }
            FreeNetconProperties(v17);
          }
        }
        else
        {
          v4 = (*(__int64 (__fastcall **)(SAFEARRAYBOUND, void **))(**(_QWORD **)&rgsabound + 24LL))(rgsabound, &pv);
        }
        if ( v4 )
        {
          if ( v4 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              13,
              WPP_b09e5d3fdceb38afdbed09c2b50fca1c_Traceguids,
              (unsigned int)v4);
        }
        else
        {
          std::list<tagNETCON_PROPERTIES_EX *>::_Emplace<tagNETCON_PROPERTIES_EX * const &>(&v22, v22, &pv);
        }
        ReleaseObj(v18);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&rgsabound);
      }
      while ( v20 );
      if ( *((_QWORD *)&v22 + 1) )
      {
        rgsabound.cElements = DWORD2(v22);
        rgsabound.lLbound = 0;
        rgIndices[0] = 0;
        v4 = 0;
        v6 = SafeArrayCreate(0xCu, 1u, &rgsabound);
        v7 = (__int64 **)v22;
        *a2 = v6;
        v8 = (__int64 **)*v7;
        while ( v8 != v7 )
        {
          pv = v8[2];
          v17 = 0;
          memset(&pvarg, 0, sizeof(pvarg));
          v9 = HrSafeArrayFromNetConPropertiesEx((struct tagNETCON_PROPERTIES_EX *)pv, (struct tagSAFEARRAY **)&v17);
          if ( v9 < 0
            || (VariantInit(&pvarg),
                v10 = *a2,
                pvarg.vt = 8204,
                pvarg.llVal = (LONGLONG)v17,
                v9 = SafeArrayPutElement(v10, rgIndices, &pvarg),
                VariantClear(&pvarg),
                v9 < 0) )
          {
            v4 = v9;
            goto LABEL_37;
          }
          ++rgIndices[0];
          v8 = (__int64 **)*v8;
          v7 = (__int64 **)v22;
        }
      }
      else
      {
LABEL_37:
        v7 = (__int64 **)v22;
      }
      for ( i = (__int64 **)*v7; i != v7; i = (__int64 **)*i )
      {
        HrFreeNetConProperties2((struct tagNETCON_PROPERTIES_EX *)i[2]);
        v7 = (__int64 **)v22;
      }
      *v7[1] = 0;
      v12 = *v7;
      if ( v12 )
      {
        do
        {
          v13 = (__int64 *)*v12;
          std::_Deallocate<16>(v12, 24);
          v12 = v13;
        }
        while ( v13 );
      }
      std::_Deallocate<16>(v22, 24);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
    if ( v4 >= 0 && !*a2 )
      v4 = 1;
  }
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_b09e5d3fdceb38afdbed09c2b50fca1c_Traceguids);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 )
      WPP_SF_d(v14[2], 15, WPP_b09e5d3fdceb38afdbed09c2b50fca1c_Traceguids, (unsigned int)v4);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180023080  push    rbp
0x180023082  push    rbx
0x180023083  push    rsi
0x180023084  push    rdi
0x180023085  push    r12
0x180023087  push    r13
0x180023089  push    r14
0x18002308b  push    r15
0x18002308d  lea     rbp, [rsp-1Fh]
0x180023092  sub     rsp, 0A8h
0x180023099  mov     rax, cs:__security_cookie
0x1800230a0  xor     rax, rsp
0x1800230a3  mov     [rbp+57h+var_48], rax
0x1800230a7  mov     r14, rdx
0x1800230aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800230b1  lea     r12, WPP_GLOBAL_Control
0x1800230b8  lea     r13, WPP_b09e5d3fdceb38afdbed09c2b50fca1c_Traceguids
0x1800230bf  cmp     rcx, r12
0x1800230c2  jz      short loc_1800230FE
0x1800230c4  test    byte ptr [rcx+1Ch], 8
0x1800230c8  jz      short loc_1800230E2
0x1800230ca  mov     rcx, [rcx+10h]
0x1800230ce  mov     edx, 0Ah
0x1800230d3  mov     r8, r13
0x1800230d6  call    WPP_SF_
0x1800230db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800230e2  cmp     rcx, r12
0x1800230e5  jz      short loc_1800230FE
0x1800230e7  test    byte ptr [rcx+1Ch], 8
0x1800230eb  jz      short loc_1800230FE
0x1800230ed  mov     rcx, [rcx+10h]
0x1800230f1  mov     edx, 0Bh
0x1800230f6  mov     r8, r13
0x1800230f9  call    WPP_SF_
0x1800230fe  xor     r15d, r15d
0x180023101  lea     rax, [rbp+57h+var_58]
0x180023105  lea     r9, _GUID_c08956a2_1cd3_11d1_b1c5_00805fc1270e; riid
0x18002310c  mov     [rbp+57h+var_58], r15
0x180023110  xor     edx, edx; pUnkOuter
0x180023112  mov     [rbp+57h+pv], r15
0x180023116  lea     rcx, CLSID_ConnectionManager; rclsid
0x18002311d  mov     [rsp+0E0h+ppv], rax; ppv
0x180023122  lea     r8d, [r15+3]; dwClsContext
0x180023126  call    cs:__imp_CoCreateInstance
0x18002312c  mov     edi, eax
0x18002312e  test    eax, eax
0x180023130  js      loc_180023400
0x180023136  mov     rcx, [rbp+57h+var_58]
0x18002313a  lea     r8, [rbp+57h+var_60]
0x18002313e  mov     [rbp+57h+var_60], r15
0x180023142  xor     edx, edx
0x180023144  mov     rax, [rcx]
0x180023147  mov     rax, [rax+18h]
0x18002314b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023150  lea     ebx, [r15+1]
0x180023154  mov     edi, eax
0x180023156  test    eax, eax
0x180023158  js      loc_1800233ED
0x18002315e  xorps   xmm0, xmm0
0x180023161  mov     [rbp+57h+var_A0], r15
0x180023165  lea     ecx, [rbx+17h]; unsigned __int64
0x180023168  mov     [rbp+57h+var_80], r15d
0x18002316c  movdqu  [rbp+57h+var_70], xmm0
0x180023171  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180023176  lea     esi, [rbx+67h]
0x180023179  mov     [rax], rax
0x18002317c  mov     [rax+8], rax
0x180023180  mov     qword ptr [rbp+57h+var_70], rax
0x180023184  mov     rcx, [rbp+57h+var_60]
0x180023188  lea     r9, [rbp+57h+var_80]
0x18002318c  lea     r8, [rbp+57h+var_A0]
0x180023190  mov     edx, ebx
0x180023192  mov     rax, [rcx]
0x180023195  mov     rax, [rax+18h]
0x180023199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002319e  test    eax, eax
0x1800231a0  jnz     loc_1800232EB
0x1800231a6  cmp     [rbp+57h+var_80], r15d
0x1800231aa  jz      loc_1800232EB
0x1800231b0  mov     rcx, [rbp+57h+var_A0]
0x1800231b4  lea     r8, [rbp+57h+rgsabound]
0x1800231b8  mov     qword ptr [rbp+57h+rgsabound.cElements], r15
0x1800231bc  lea     rdx, _GUID_faedcf6a_31fe_11d1_aad2_00805fc1270e
0x1800231c3  mov     rax, [rcx]
0x1800231c6  mov     rax, [rax]
0x1800231c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231ce  test    eax, eax
0x1800231d0  js      short loc_1800231ED
0x1800231d2  mov     rcx, qword ptr [rbp+57h+rgsabound.cElements]
0x1800231d6  lea     rdx, [rbp+57h+pv]
0x1800231da  mov     rax, [rcx]
0x1800231dd  mov     rax, [rax+18h]
0x1800231e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231e6  mov     edi, eax
0x1800231e8  jmp     loc_180023291
0x1800231ed  mov     rcx, [rbp+57h+var_A0]
0x1800231f1  lea     rdx, [rbp+57h+var_A8]
0x1800231f5  mov     [rbp+57h+var_A8], r15
0x1800231f9  mov     rax, [rcx]
0x1800231fc  mov     rax, [rax+38h]
0x180023200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023205  mov     edi, eax
0x180023207  test    eax, eax
0x180023209  js      loc_180023291
0x18002320f  mov     rcx, rsi; cb
0x180023212  call    cs:__imp_CoTaskMemAlloc
0x180023218  mov     [rbp+57h+pv], rax
0x18002321c  test    rax, rax
0x18002321f  jz      short loc_180023283
0x180023221  mov     rcx, [rbp+57h+var_A0]
0x180023225  lea     r8, [rbp+57h+rgIndices]
0x180023229  mov     qword ptr [rbp+57h+rgIndices], r15
0x18002322d  lea     rdx, _GUID_faedcf59_31fe_11d1_aad2_00805fc1270e
0x180023234  mov     rax, [rcx]
0x180023237  mov     rax, [rax]
0x18002323a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002323f  mov     edi, eax
0x180023241  test    eax, eax
0x180023243  js      short loc_180023266
0x180023245  mov     rcx, [rbp+57h+pv]; void *
0x180023249  mov     r8, rsi; Size
0x18002324c  xor     edx, edx; Val
0x18002324e  call    memset_0
0x180023253  mov     r8, qword ptr [rbp+57h+rgIndices]; struct IPersistNetConnection *
0x180023257  mov     rdx, [rbp+57h+pv]; struct tagNETCON_PROPERTIES_EX *
0x18002325b  mov     rcx, [rbp+57h+var_A8]; struct tagNETCON_PROPERTIES *
0x18002325f  call    ?HrBuildPropertiesExFromProperties@@YAJPEAUtagNETCON_PROPERTIES@@PEAUtagNETCON_PROPERTIES_EX@@PEAUIPersistNetConnection@@@Z; HrBuildPropertiesExFromProperties(tagNETCON_PROPERTIES *,tagNETCON_PROPERTIES_EX *,IPersistNetConnection *)
0x180023264  mov     edi, eax
0x180023266  test    edi, edi
0x180023268  jz      short loc_180023278
0x18002326a  mov     rcx, [rbp+57h+pv]; pv
0x18002326e  call    cs:__imp_CoTaskMemFree
0x180023274  mov     [rbp+57h+pv], r15
0x180023278  lea     rcx, [rbp+57h+rgIndices]
0x18002327c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180023281  jmp     short loc_180023288
0x180023283  mov     edi, 8007000Eh
0x180023288  mov     rcx, [rbp+57h+var_A8]; pv
0x18002328c  call    ?FreeNetconProperties@@YAXPEAUtagNETCON_PROPERTIES@@@Z; FreeNetconProperties(tagNETCON_PROPERTIES *)
0x180023291  test    edi, edi
0x180023293  jnz     short loc_1800232A8
0x180023295  mov     rdx, qword ptr [rbp+57h+var_70]
0x180023299  lea     r8, [rbp+57h+pv]
0x18002329d  lea     rcx, [rbp+57h+var_70]
0x1800232a1  call    ??$_Emplace@AEBQEAUtagNETCON_PROPERTIES_EX@@@?$list@PEAUtagNETCON_PROPERTIES_EX@@V?$allocator@PEAUtagNETCON_PROPERTIES_EX@@@std@@@std@@QEAAPEAU?$_List_node@PEAUtagNETCON_PROPERTIES_EX@@PEAX@1@QEAU21@AEBQEAUtagNETCON_PROPERTIES_EX@@@Z; std::list<tagNETCON_PROPERTIES_EX *>::_Emplace<tagNETCON_PROPERTIES_EX * const &>(std::_List_node<tagNETCON_PROPERTIES_EX *,void *> * const,tagNETCON_PROPERTIES_EX * const &)
0x1800232a6  jmp     short loc_1800232CF
0x1800232a8  jns     short loc_1800232CF
0x1800232aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800232b1  cmp     rcx, r12
0x1800232b4  jz      short loc_1800232CF
0x1800232b6  test    [rcx+1Ch], bl
0x1800232b9  jz      short loc_1800232CF
0x1800232bb  mov     rcx, [rcx+10h]
0x1800232bf  mov     edx, 0Dh
0x1800232c4  mov     r9d, edi
0x1800232c7  mov     r8, r13
0x1800232ca  call    WPP_SF_d
0x1800232cf  mov     rcx, [rbp+57h+var_A0]; struct IUnknown *
0x1800232d3  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x1800232d8  lea     rcx, [rbp+57h+rgsabound]
0x1800232dc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800232e1  cmp     [rbp+57h+var_80], r15d
0x1800232e5  jnz     loc_180023184
0x1800232eb  mov     rax, qword ptr [rbp+57h+var_70+8]
0x1800232ef  test    rax, rax
0x1800232f2  jz      loc_180023398
0x1800232f8  mov     ecx, 0Ch; vt
0x1800232fd  mov     [rbp+57h+rgsabound.cElements], eax
0x180023300  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x180023304  mov     [rbp+57h+rgsabound.lLbound], r15d
0x180023308  mov     edx, ebx; cDims
0x18002330a  mov     [rbp+57h+rgIndices], r15d
0x18002330e  mov     edi, r15d
0x180023311  call    cs:__imp_SafeArrayCreate
0x180023317  mov     rcx, qword ptr [rbp+57h+var_70]
0x18002331b  mov     [r14], rax
0x18002331e  mov     rbx, [rcx]
0x180023321  cmp     rbx, rcx
0x180023324  jz      short loc_18002339C
0x180023326  mov     rcx, [rbx+10h]; struct tagNETCON_PROPERTIES_EX *
0x18002332a  lea     rdx, [rbp+57h+var_A8]; struct tagSAFEARRAY **
0x18002332e  xorps   xmm0, xmm0
0x180023331  mov     [rbp+57h+pv], rcx
0x180023335  xor     eax, eax
0x180023337  mov     [rbp+57h+var_A8], r15
0x18002333b  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18002333f  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180023343  call    ?HrSafeArrayFromNetConPropertiesEx@@YAJPEAUtagNETCON_PROPERTIES_EX@@PEAPEAUtagSAFEARRAY@@@Z; HrSafeArrayFromNetConPropertiesEx(tagNETCON_PROPERTIES_EX *,tagSAFEARRAY * *)
0x180023348  mov     esi, eax
0x18002334a  test    eax, eax
0x18002334c  js      short loc_180023396
0x18002334e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180023352  call    cs:__imp_VariantInit
0x180023358  mov     rcx, [r14]; psa
0x18002335b  lea     r8, [rbp+57h+pvarg]; pv
0x18002335f  mov     eax, 200Ch
0x180023364  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x180023368  mov     word ptr [rbp+57h+pvarg], ax
0x18002336c  mov     rax, [rbp+57h+var_A8]
0x180023370  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180023374  call    cs:__imp_SafeArrayPutElement
0x18002337a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002337e  mov     esi, eax
0x180023380  call    cs:__imp_VariantClear
0x180023386  test    esi, esi
0x180023388  js      short loc_180023396
0x18002338a  inc     [rbp+57h+rgIndices]
0x18002338d  mov     rbx, [rbx]
0x180023390  mov     rcx, qword ptr [rbp+57h+var_70]
0x180023394  jmp     short loc_180023321
0x180023396  mov     edi, esi
0x180023398  mov     rcx, qword ptr [rbp+57h+var_70]
0x18002339c  mov     rbx, [rcx]
0x18002339f  cmp     rbx, rcx
0x1800233a2  jz      short loc_1800233B6
0x1800233a4  mov     rcx, [rbx+10h]; pv
0x1800233a8  call    ?HrFreeNetConProperties2@@YAJPEAUtagNETCON_PROPERTIES_EX@@@Z; HrFreeNetConProperties2(tagNETCON_PROPERTIES_EX *)
0x1800233ad  mov     rcx, qword ptr [rbp+57h+var_70]
0x1800233b1  mov     rbx, [rbx]
0x1800233b4  jmp     short loc_18002339F
0x1800233b6  mov     rax, [rcx+8]
0x1800233ba  mov     [rax], r15
0x1800233bd  mov     rcx, [rcx]
0x1800233c0  test    rcx, rcx
0x1800233c3  jz      short loc_1800233DA
0x1800233c5  mov     rbx, [rcx]
0x1800233c8  mov     edx, 18h
0x1800233cd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800233d2  mov     rcx, rbx
0x1800233d5  test    rbx, rbx
0x1800233d8  jnz     short loc_1800233C5
0x1800233da  mov     rcx, qword ptr [rbp+57h+var_70]
0x1800233de  mov     edx, 18h
0x1800233e3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800233e8  mov     ebx, 1
0x1800233ed  lea     rcx, [rbp+57h+var_60]
0x1800233f1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800233f6  test    edi, edi
0x1800233f8  js      short loc_180023400
0x1800233fa  cmp     [r14], r15
0x1800233fd  cmovz   edi, ebx
0x180023400  mov     rcx, cs:WPP_GLOBAL_Control
0x180023407  cmp     rcx, r12
0x18002340a  jz      short loc_180023449
0x18002340c  test    byte ptr [rcx+1Ch], 8
0x180023410  jz      short loc_18002342A
0x180023412  mov     rcx, [rcx+10h]
0x180023416  mov     edx, 0Eh
0x18002341b  mov     r8, r13
0x18002341e  call    WPP_SF_
0x180023423  mov     rcx, cs:WPP_GLOBAL_Control
0x18002342a  cmp     rcx, r12
0x18002342d  jz      short loc_180023449
0x18002342f  test    byte ptr [rcx+1Ch], 8
0x180023433  jz      short loc_180023449
0x180023435  mov     rcx, [rcx+10h]
0x180023439  mov     edx, 0Fh
0x18002343e  mov     r9d, edi
0x180023441  mov     r8, r13
0x180023444  call    WPP_SF_d
0x180023449  lea     rcx, [rbp+57h+var_58]
0x18002344d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180023452  mov     eax, edi
0x180023454  mov     rcx, [rbp+57h+var_48]
0x180023458  xor     rcx, rsp; StackCookie
0x18002345b  call    __security_check_cookie
0x180023460  add     rsp, 0A8h
0x180023467  pop     r15
0x180023469  pop     r14
0x18002346b  pop     r13
0x18002346d  pop     r12
0x18002346f  pop     rdi
0x180023470  pop     rsi
0x180023471  pop     rbx
0x180023472  pop     rbp
0x180023473  retn
```
