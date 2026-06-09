# CNoPinList::_Initialize(void)

- ea: `0x18003b380`
- end: `0x18003b5d5`
- name: `?_Initialize@CNoPinList@@AEAAJXZ`
- size: `597`
- prototype: `__int64 __fastcall(CNoPinList *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003ae4c`
- `0x18003ae7c`

## callees

- `0x180003544`
- `0x18000c1e8`
- `0x18000ee64`
- `0x18003aa18`
- `0x18003acec`
- `0x18003ad1c`
- `0x18003ad5c`
- `0x18003adcc`
- `0x18003ae0c`
- `0x18003b254`
- `0x18003b380`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003b3f1`
- `OLEAUT32!__imp_VariantInit` at `0x18003b3f1`
- `OLEAUT32!__imp_VariantClear` at `0x18003b585`
- `OLEAUT32!__imp_VariantClear` at `0x18003b585`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18003b472`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18003b472`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18003b572`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18003b572`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18003b487`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18003b487`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18003b565`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18003b565`

## pseudocode

```c
__int64 __fastcall CNoPinList::_Initialize(CNoPinList *this)
{
  int inited; // edi
  _QWORD *v3; // rax
  unsigned int v4; // r15d
  SAFEARRAY *v5; // rax
  SAFEARRAY *v6; // rbx
  HRESULT v7; // eax
  int i; // esi
  int LowerBound; // edi
  int v10; // eax
  __int64 v11; // rdi
  VARIANTARG pvarg; // [rsp+40h] [rbp-28h] BYREF
  SAFEARRAY *ppsaOut; // [rsp+A0h] [rbp+38h] BYREF
  SAFEARRAY *v15; // [rsp+A8h] [rbp+40h] BYREF
  int v16; // [rsp+B0h] [rbp+48h]
  int v17; // [rsp+B4h] [rbp+4Ch]
  SAFEARRAYBOUND rgsabound; // [rsp+B8h] [rbp+50h] BYREF

  if ( *(_QWORD *)this )
  {
    return 1;
  }
  else
  {
    v3 = operator new(0x18u);
    if ( v3 )
    {
      inited = 0;
      *v3 = 0;
      v3[1] = 0;
      v4 = 0;
      v3[2] = 0;
      *(_QWORD *)this = v3;
      v16 = 49;
      v17 = 50;
      while ( v4 < 2 )
      {
        VariantInit(&pvarg);
        if ( (int)GetUserStateSetting(3, qword_180066230, 6) >= 0 && pvarg.vt == 8204 )
        {
          ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(&ppsaOut, pvarg.parray);
          `vector constructor iterator'(
            &rgsabound,
            8u,
            1u,
            (void *(*)(void *))ATL::CComSafeArrayBound::`default constructor closure');
          rgsabound.lLbound = 0;
          v5 = SafeArrayCreate(8u, 1u, &rgsabound);
          v6 = v5;
          if ( !v5 )
          {
            v7 = -2147024882;
LABEL_29:
            ATL::AtlThrowImpl(v7);
          }
          v7 = SafeArrayLock(v5);
          if ( v7 < 0 )
            goto LABEL_29;
          for ( i = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&ppsaOut);
                i < (int)ATL::CComSafeArray<tagVARIANT,12>::GetCount(&ppsaOut);
                ++i )
          {
            if ( !ppsaOut )
              goto LABEL_27;
            LowerBound = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&ppsaOut);
            if ( i < LowerBound || i > (int)ATL::CComSafeArray<tagVARIANT,12>::GetUpperBound(&ppsaOut) )
              goto LABEL_26;
            ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(
              &v15,
              *((struct tagSAFEARRAY **)ppsaOut->pvData + 3 * (i - LowerBound) + 1));
            if ( !v15 )
LABEL_27:
              ATL::AtlThrowImpl(-2147467259);
            v10 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v15);
            v11 = v10;
            if ( v10 > 0 || (int)ATL::CComSafeArray<tagVARIANT,12>::GetUpperBound(&v15) < 0 )
LABEL_26:
              ATL::AtlThrowImpl(-2147024809);
            inited = CNoPinList::_InitPathFromRegistry(this, ((LPCWSTR *)v15->pvData - 3 * v11)[1]);
            if ( inited < 0 )
            {
              ATL::CComSafeArray<tagVARIANT,12>::Destroy(&v15);
              break;
            }
            ATL::CComSafeArray<tagVARIANT,12>::Destroy(&v15);
          }
          if ( SafeArrayUnlock(v6) >= 0 )
            SafeArrayDestroy(v6);
          ATL::CComSafeArray<tagVARIANT,12>::Destroy(&ppsaOut);
        }
        VariantClear(&pvarg);
        if ( inited < 0 )
          break;
        ++v4;
      }
    }
    else
    {
      *(_QWORD *)this = 0;
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18003b380  push    rbp
0x18003b382  push    rbx
0x18003b383  push    rsi
0x18003b384  push    rdi
0x18003b385  push    r14
0x18003b387  push    r15
0x18003b389  mov     rbp, rsp
0x18003b38c  sub     rsp, 68h
0x18003b390  cmp     qword ptr [rcx], 0
0x18003b394  mov     r14, rcx
0x18003b397  jz      short loc_18003B3A3
0x18003b399  mov     edi, 1
0x18003b39e  jmp     loc_18003B5C6
0x18003b3a3  mov     ecx, 18h; Size
0x18003b3a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b3ad  test    rax, rax
0x18003b3b0  jz      loc_18003B5BA
0x18003b3b6  xor     edi, edi
0x18003b3b8  mov     qword ptr [rax], 0
0x18003b3bf  mov     qword ptr [rax+8], 0
0x18003b3c7  xor     r15d, r15d
0x18003b3ca  mov     qword ptr [rax+10h], 0
0x18003b3d2  mov     [r14], rax
0x18003b3d5  mov     [rbp+arg_10], 31h ; '1'
0x18003b3dc  mov     [rbp+arg_14], 32h ; '2'
0x18003b3e3  cmp     r15d, 2
0x18003b3e7  jnb     loc_18003B5C6
0x18003b3ed  lea     rcx, [rbp+pvarg]; pvarg
0x18003b3f1  call    cs:__imp_VariantInit
0x18003b3f7  xor     r9d, r9d
0x18003b3fa  movsxd  rax, r15d
0x18003b3fd  lea     rdx, qword_180066230
0x18003b404  mov     ecx, [rbp+rax*4+arg_10]
0x18003b408  lea     r8d, [r9+6]
0x18003b40c  mov     [rsp+68h+var_38], ecx
0x18003b410  lea     rax, [rbp+pvarg]
0x18003b414  lea     ecx, [r9+3]
0x18003b418  mov     [rsp+68h+var_48], rax
0x18003b41d  call    ?GetUserStateSetting@@YAJW4UST_COMPONENT_ID@@QEBUUSERSTATE_SETTING_DESCRIPTOR@@IIAEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z; GetUserStateSetting(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const * const,uint,uint,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)
0x18003b422  test    eax, eax
0x18003b424  js      loc_18003B581
0x18003b42a  mov     eax, 200Ch
0x18003b42f  cmp     word ptr [rbp+pvarg], ax
0x18003b433  jnz     loc_18003B581
0x18003b439  mov     rdx, qword ptr [rbp+pvarg+8]; struct tagSAFEARRAY *
0x18003b43d  lea     rcx, [rbp+ppsaOut]; ppsaOut
0x18003b441  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAY const *)
0x18003b446  mov     edx, 8; unsigned __int64
0x18003b44b  lea     r9, ??_FCComSafeArrayBound@ATL@@QEAAXXZ; void *(*)(void *)
0x18003b452  lea     rcx, [rbp+rgsabound]; void *
0x18003b456  lea     r8d, [rdx-7]; unsigned __int64
0x18003b45a  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18003b45f  mov     ecx, 8; vt
0x18003b464  mov     [rbp+rgsabound.lLbound], 0
0x18003b46b  lea     r8, [rbp+rgsabound]; rgsabound
0x18003b46f  lea     edx, [rcx-7]; cDims
0x18003b472  call    cs:__imp_SafeArrayCreate
0x18003b478  mov     rbx, rax
0x18003b47b  test    rax, rax
0x18003b47e  jz      loc_18003B5AD
0x18003b484  mov     rcx, rax; psa
0x18003b487  call    cs:__imp_SafeArrayLock
0x18003b48d  test    eax, eax
0x18003b48f  js      loc_18003B5B2
0x18003b495  lea     rcx, [rbp+ppsaOut]
0x18003b499  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18003b49e  mov     esi, eax
0x18003b4a0  lea     rcx, [rbp+ppsaOut]
0x18003b4a4  call    ?GetCount@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAKI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetCount(uint)
0x18003b4a9  cmp     esi, eax
0x18003b4ab  jge     loc_18003B562
0x18003b4b1  cmp     [rbp+ppsaOut], 0
0x18003b4b6  jz      loc_18003B5A2
0x18003b4bc  lea     rcx, [rbp+ppsaOut]
0x18003b4c0  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18003b4c5  mov     edi, eax
0x18003b4c7  cmp     esi, eax
0x18003b4c9  jl      loc_18003B597
0x18003b4cf  lea     rcx, [rbp+ppsaOut]
0x18003b4d3  call    ?GetUpperBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetUpperBound(uint)
0x18003b4d8  cmp     esi, eax
0x18003b4da  jg      loc_18003B597
0x18003b4e0  mov     eax, esi
0x18003b4e2  sub     eax, edi
0x18003b4e4  cdqe
0x18003b4e6  lea     rcx, [rax+rax*2]
0x18003b4ea  mov     rax, [rbp+ppsaOut]
0x18003b4ee  mov     rdx, [rax+10h]
0x18003b4f2  mov     rdx, [rdx+rcx*8+8]; struct tagSAFEARRAY *
0x18003b4f7  lea     rcx, [rbp+arg_8]; ppsaOut
0x18003b4fb  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAY const *)
0x18003b500  cmp     [rbp+arg_8], 0
0x18003b505  jz      loc_18003B5A2
0x18003b50b  lea     rcx, [rbp+arg_8]
0x18003b50f  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18003b514  movsxd  rdi, eax
0x18003b517  test    eax, eax
0x18003b519  jg      short loc_18003B597
0x18003b51b  lea     rcx, [rbp+arg_8]
0x18003b51f  call    ?GetUpperBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetUpperBound(uint)
0x18003b524  test    eax, eax
0x18003b526  js      short loc_18003B597
0x18003b528  mov     rax, [rbp+arg_8]
0x18003b52c  lea     rcx, [rdi+rdi*2]
0x18003b530  shl     rcx, 3
0x18003b534  mov     rdx, [rax+10h]
0x18003b538  sub     rdx, rcx
0x18003b53b  mov     rcx, r14; this
0x18003b53e  mov     rdx, [rdx+8]; lpSrc
0x18003b542  call    ?_InitPathFromRegistry@CNoPinList@@AEAAJPEBG@Z; CNoPinList::_InitPathFromRegistry(ushort const *)
0x18003b547  lea     rcx, [rbp+arg_8]
0x18003b54b  mov     edi, eax
0x18003b54d  test    eax, eax
0x18003b54f  js      short loc_18003B55D
0x18003b551  call    ?Destroy@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJXZ; ATL::CComSafeArray<tagVARIANT,12>::Destroy(void)
0x18003b556  inc     esi
0x18003b558  jmp     loc_18003B4A0
0x18003b55d  call    ?Destroy@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJXZ; ATL::CComSafeArray<tagVARIANT,12>::Destroy(void)
0x18003b562  mov     rcx, rbx; psa
0x18003b565  call    cs:__imp_SafeArrayUnlock
0x18003b56b  test    eax, eax
0x18003b56d  js      short loc_18003B578
0x18003b56f  mov     rcx, rbx; psa
0x18003b572  call    cs:__imp_SafeArrayDestroy
0x18003b578  lea     rcx, [rbp+ppsaOut]
0x18003b57c  call    ?Destroy@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJXZ; ATL::CComSafeArray<tagVARIANT,12>::Destroy(void)
0x18003b581  lea     rcx, [rbp+pvarg]; pvarg
0x18003b585  call    cs:__imp_VariantClear
0x18003b58b  test    edi, edi
0x18003b58d  js      short loc_18003B5C6
0x18003b58f  inc     r15d
0x18003b592  jmp     loc_18003B3E3
0x18003b597  mov     ecx, 80070057h; int
0x18003b59c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18003b5a2  mov     ecx, 80004005h; int
0x18003b5a7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18003b5ad  mov     eax, 8007000Eh
0x18003b5b2  mov     ecx, eax; int
0x18003b5b4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18003b5ba  mov     qword ptr [r14], 0
0x18003b5c1  mov     edi, 8007000Eh
0x18003b5c6  mov     eax, edi
0x18003b5c8  add     rsp, 68h
0x18003b5cc  pop     r15
0x18003b5ce  pop     r14
0x18003b5d0  pop     rdi
0x18003b5d1  pop     rsi
0x18003b5d2  pop     rbx
0x18003b5d3  pop     rbp
0x18003b5d4  retn
```
