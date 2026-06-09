# GetMultiValueSetting(HKEY__ *,ushort const *,ATL::CComVariant &)

- ea: `0x18004afd8`
- end: `0x18004b31a`
- name: `?GetMultiValueSetting@@YAJPEAUHKEY__@@PEBGAEAVCComVariant@ATL@@@Z`
- size: `834`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, VARIANTARG *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003290`

## callees

- `0x180003290`
- `0x18000ee64`
- `0x18003ac98`
- `0x18003acec`
- `0x18003ad1c`
- `0x18004ac50`
- `0x18004ae1c`
- `0x18004aeb8`
- `0x18004afd8`
- `0x18004b334`
- `0x18004c636`
- `0x18004c670`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004b09d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004b09d`
- `OLEAUT32!__imp_VariantInit` at `0x18004b12d`
- `OLEAUT32!__imp_VariantInit` at `0x18004b12d`
- `OLEAUT32!__imp_VariantClear` at `0x18004b15b`
- `OLEAUT32!__imp_VariantClear` at `0x18004b1f0`
- `OLEAUT32!__imp_VariantClear` at `0x18004b1fe`
- `OLEAUT32!__imp_VariantClear` at `0x18004b209`
- `OLEAUT32!__imp_VariantClear` at `0x18004b240`
- `OLEAUT32!__imp_VariantClear` at `0x18004b24b`
- `OLEAUT32!__imp_VariantClear` at `0x18004b2b8`
- `OLEAUT32!__imp_VariantClear` at `0x18004b15b`
- `OLEAUT32!__imp_VariantClear` at `0x18004b1f0`
- `OLEAUT32!__imp_VariantClear` at `0x18004b1fe`
- `OLEAUT32!__imp_VariantClear` at `0x18004b209`
- `OLEAUT32!__imp_VariantClear` at `0x18004b240`
- `OLEAUT32!__imp_VariantClear` at `0x18004b24b`
- `OLEAUT32!__imp_VariantClear` at `0x18004b2b8`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18004b199`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18004b2d4`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18004b199`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18004b2d4`

## pseudocode

```c
__int64 __fastcall GetMultiValueSetting(HKEY a1, const unsigned __int16 *a2, VARIANTARG *a3)
{
  signed int v5; // ebx
  DWORD v6; // r14d
  LSTATUS v7; // eax
  int v8; // esi
  unsigned __int16 v9; // bx
  SAFEARRAY *v10; // rsi
  HRESULT v11; // ecx
  SAFEARRAY *v13; // rsi
  HRESULT v14; // eax
  SAFEARRAY *v15; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  SAFEARRAY *psa; // [rsp+50h] [rbp-B0h] BYREF
  SAFEARRAY *ppsaOut; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchValueName; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v20; // [rsp+68h] [rbp-98h] BYREF
  SAFEARRAY *v21; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG v22; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG v24; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR ValueName[264]; // [rsp+C0h] [rbp-40h] BYREF

  v5 = 0;
  `vector constructor iterator'(&v20, 8u, 1u, (void *(*)(void *))ATL::CComSafeArrayBound::`default constructor closure');
  v20 = 0;
  ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(&v21, &v20);
  v6 = 0;
  while ( 1 )
  {
    Type = 0;
    memset_0(ValueName, 0, 0x208u);
    cchValueName = 260;
    v7 = RegEnumValueW(a1, v6, ValueName, &cchValueName, 0, &Type, 0, 0);
    if ( v7 )
      break;
    `vector constructor iterator'(
      &v15,
      8u,
      1u,
      (void *(*)(void *))ATL::CComSafeArrayBound::`default constructor closure');
    v15 = (SAFEARRAY *)2;
    ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(&psa, &v15);
    v24.vt = 0;
    ATL::CComVariant::operator=(&v24, ValueName);
    v8 = ATL::CComSafeArray<tagVARIANT,12>::SetAt(&psa, 0, &v24);
    v9 = 0;
    switch ( Type )
    {
      case 1u:
        v9 = 8;
        break;
      case 4u:
        v9 = 3;
        break;
      case 7u:
        v9 = 8200;
        break;
    }
    VariantInit(&pvarg);
    if ( v8 < 0 || GetStoredValue(a1, 0, ValueName, v9, (struct ATL::CComVariant *)&pvarg) < 0 )
      VariantClear(&pvarg);
    v5 = ATL::CComSafeArray<tagVARIANT,12>::SetAt(&psa, 1, &pvarg);
    if ( v5 < 0 )
    {
      VariantClear(&pvarg);
      VariantClear(&v24);
      ATL::CComSafeArray<tagVARIANT,12>::Destroy(&psa);
      goto LABEL_21;
    }
    v10 = psa;
    ppsaOut = 0;
    if ( psa )
    {
      v11 = SafeArrayCopy(psa, &ppsaOut);
      if ( v11 < 0 || !ppsaOut )
      {
        v22.vt = 10;
        v22.lVal = v11;
        ATL::AtlThrowImpl(-2147024882);
      }
      ATL::AtlSafeArrayGetActualVartype(v10, &v22.vt);
      v22.vt |= 0x2000u;
      v22.llVal = (LONGLONG)ppsaOut;
    }
    else
    {
      v22.vt = 0;
    }
    ATL::CComSafeArray<tagVARIANT,12>::Add(&v21, &v22);
    VariantClear(&v22);
    ++v6;
    VariantClear(&pvarg);
    VariantClear(&v24);
    ATL::CComSafeArray<tagVARIANT,12>::Destroy(&psa);
  }
  if ( v7 != 259 )
  {
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    else
      v5 = v7;
  }
  if ( v5 >= 0 )
  {
    v13 = v21;
    VariantClear(a3);
    v15 = 0;
    if ( v13 )
    {
      v14 = SafeArrayCopy(v13, &v15);
      if ( v14 < 0 || !v15 )
      {
        a3->vt = 10;
        a3->lVal = v14;
        ATL::AtlThrowImpl(-2147024882);
      }
      ATL::AtlSafeArrayGetActualVartype(v13, &a3->vt);
      a3->vt |= 0x2000u;
      a3->llVal = (LONGLONG)v15;
    }
  }
LABEL_21:
  ATL::CComSafeArray<tagVARIANT,12>::Destroy(&v21);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004afd8  mov     [rsp-8+arg_8], rbx
0x18004afdd  mov     [rsp-8+arg_18], rsi
0x18004afe2  push    rbp
0x18004afe3  push    rdi
0x18004afe4  push    r13
0x18004afe6  push    r14
0x18004afe8  push    r15
0x18004afea  lea     rbp, [rsp-1E0h]
0x18004aff2  sub     rsp, 2E0h
0x18004aff9  mov     rax, cs:__security_cookie
0x18004b000  xor     rax, rsp
0x18004b003  mov     [rbp+200h+var_30], rax
0x18004b00a  mov     rdi, r8
0x18004b00d  mov     r15, rcx
0x18004b010  xor     ebx, ebx
0x18004b012  lea     r9, ??_FCComSafeArrayBound@ATL@@QEAAXXZ; void *(*)(void *)
0x18004b019  lea     esi, [rbx+8]
0x18004b01c  lea     r8d, [rbx+1]; unsigned __int64
0x18004b020  mov     edx, esi; unsigned __int64
0x18004b022  lea     rcx, [rsp+300h+var_298]; void *
0x18004b027  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18004b02c  mov     [rsp+300h+var_298], rbx
0x18004b031  lea     rdx, [rsp+300h+var_298]
0x18004b036  lea     rcx, [rsp+300h+var_290]
0x18004b03b  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAYBOUND const *,uint)
0x18004b040  nop
0x18004b041  xor     r14d, r14d
0x18004b044  lea     r13d, [rbx+3]
0x18004b048  mov     [rsp+300h+Type], 0
0x18004b050  xor     edx, edx; Val
0x18004b052  mov     r8d, 208h; Size
0x18004b058  lea     rcx, [rbp+200h+ValueName]; void *
0x18004b05c  call    memset_0
0x18004b061  mov     [rsp+300h+cchValueName], 104h
0x18004b069  mov     [rsp+300h+lpcbData], 0; lpcbData
0x18004b072  mov     [rsp+300h+lpData], 0; lpData
0x18004b07b  lea     rax, [rsp+300h+Type]
0x18004b080  mov     [rsp+300h+lpType], rax; lpType
0x18004b085  mov     [rsp+300h+lpReserved], 0; lpReserved
0x18004b08e  lea     r9, [rsp+300h+cchValueName]; lpcchValueName
0x18004b093  lea     r8, [rbp+200h+ValueName]; lpValueName
0x18004b097  mov     edx, r14d; dwIndex
0x18004b09a  mov     rcx, r15; hKey
0x18004b09d  call    cs:__imp_RegEnumValueW
0x18004b0a3  test    eax, eax
0x18004b0a5  jnz     loc_18004B294
0x18004b0ab  lea     r9, ??_FCComSafeArrayBound@ATL@@QEAAXXZ; void *(*)(void *)
0x18004b0b2  lea     r8d, [rax+1]; unsigned __int64
0x18004b0b6  mov     rdx, rsi; unsigned __int64
0x18004b0b9  lea     rcx, [rsp+300h+var_2C0]; void *
0x18004b0be  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18004b0c3  mov     [rsp+300h+var_2C0], 2
0x18004b0cc  lea     rdx, [rsp+300h+var_2C0]
0x18004b0d1  lea     rcx, [rsp+300h+psa]
0x18004b0d6  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAYBOUND const *,uint)
0x18004b0db  nop
0x18004b0dc  xor     eax, eax
0x18004b0de  mov     word ptr [rbp+200h+var_258], ax
0x18004b0e2  lea     rdx, [rbp+200h+ValueName]
0x18004b0e6  lea     rcx, [rbp+200h+var_258]
0x18004b0ea  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x18004b0ef  nop
0x18004b0f0  lea     r8, [rbp+200h+var_258]
0x18004b0f4  xor     edx, edx
0x18004b0f6  lea     rcx, [rsp+300h+psa]
0x18004b0fb  call    ?SetAt@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::SetAt(long,tagVARIANT const &,int)
0x18004b100  mov     esi, eax
0x18004b102  xor     ebx, ebx
0x18004b104  mov     ecx, [rsp+300h+Type]
0x18004b108  sub     ecx, 1
0x18004b10b  jz      short loc_18004B124
0x18004b10d  sub     ecx, r13d
0x18004b110  jz      short loc_18004B11E
0x18004b112  cmp     ecx, r13d
0x18004b115  jnz     short loc_18004B129
0x18004b117  mov     ebx, 2008h
0x18004b11c  jmp     short loc_18004B129
0x18004b11e  movzx   ebx, r13w
0x18004b122  jmp     short loc_18004B129
0x18004b124  mov     ebx, 8
0x18004b129  lea     rcx, [rbp+200h+pvarg]; pvarg
0x18004b12d  call    cs:__imp_VariantInit
0x18004b133  nop
0x18004b134  test    esi, esi
0x18004b136  js      short loc_18004B157
0x18004b138  lea     rax, [rbp+200h+pvarg]
0x18004b13c  mov     [rsp+300h+lpReserved], rax; struct ATL::CComVariant *
0x18004b141  movzx   r9d, bx; unsigned __int16
0x18004b145  lea     r8, [rbp+200h+ValueName]; unsigned __int16 *
0x18004b149  xor     edx, edx; unsigned __int16 *
0x18004b14b  mov     rcx, r15; HKEY
0x18004b14e  call    ?GetStoredValue@@YAJPEAUHKEY__@@PEBG1GAEAVCComVariant@ATL@@@Z; GetStoredValue(HKEY__ *,ushort const *,ushort const *,ushort,ATL::CComVariant &)
0x18004b153  test    eax, eax
0x18004b155  jns     short loc_18004B161
0x18004b157  lea     rcx, [rbp+200h+pvarg]; pvarg
0x18004b15b  call    cs:__imp_VariantClear
0x18004b161  lea     r8, [rbp+200h+pvarg]
0x18004b165  mov     edx, 1
0x18004b16a  lea     rcx, [rsp+300h+psa]
0x18004b16f  call    ?SetAt@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::SetAt(long,tagVARIANT const &,int)
0x18004b174  mov     ebx, eax
0x18004b176  test    eax, eax
0x18004b178  js      loc_18004B23C
0x18004b17e  mov     rsi, [rsp+300h+psa]
0x18004b183  mov     [rsp+300h+ppsaOut], 0
0x18004b18c  test    rsi, rsi
0x18004b18f  jz      short loc_18004B1D4
0x18004b191  lea     rdx, [rsp+300h+ppsaOut]; ppsaOut
0x18004b196  mov     rcx, rsi; psa
0x18004b199  call    cs:__imp_SafeArrayCopy
0x18004b19f  mov     ecx, eax
0x18004b1a1  test    eax, eax
0x18004b1a3  js      short loc_18004B224
0x18004b1a5  cmp     [rsp+300h+ppsaOut], 0
0x18004b1ab  jz      short loc_18004B224
0x18004b1ad  lea     rdx, [rsp+300h+var_288]; unsigned __int16 *
0x18004b1b2  mov     rcx, rsi; struct tagSAFEARRAY *
0x18004b1b5  call    ?AtlSafeArrayGetActualVartype@ATL@@YAJPEAUtagSAFEARRAY@@PEAG@Z; ATL::AtlSafeArrayGetActualVartype(tagSAFEARRAY *,ushort *)
0x18004b1ba  mov     eax, 2000h
0x18004b1bf  or      word ptr [rsp+300h+var_288], ax
0x18004b1c4  mov     eax, dword ptr [rsp+300h+ppsaOut]
0x18004b1c8  mov     dword ptr [rbp+200h+var_288+8], eax
0x18004b1cb  mov     eax, dword ptr [rsp+300h+ppsaOut+4]
0x18004b1cf  mov     dword ptr [rbp+200h+var_288+0Ch], eax
0x18004b1d2  jmp     short loc_18004B1DB
0x18004b1d4  xor     eax, eax
0x18004b1d6  mov     word ptr [rsp+300h+var_288], ax
0x18004b1db  lea     rdx, [rsp+300h+var_288]
0x18004b1e0  lea     rcx, [rsp+300h+var_290]
0x18004b1e5  call    ?Add@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::Add(tagVARIANT const &,int)
0x18004b1ea  nop
0x18004b1eb  lea     rcx, [rsp+300h+var_288]; pvarg
0x18004b1f0  call    cs:__imp_VariantClear
0x18004b1f6  nop
0x18004b1f7  inc     r14d
0x18004b1fa  lea     rcx, [rbp+200h+pvarg]; pvarg
0x18004b1fe  call    cs:__imp_VariantClear
0x18004b204  nop
0x18004b205  lea     rcx, [rbp+200h+var_258]; pvarg
0x18004b209  call    cs:__imp_VariantClear
0x18004b20f  nop
0x18004b210  lea     rcx, [rsp+300h+psa]
0x18004b215  call    ?Destroy@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJXZ; ATL::CComSafeArray<tagVARIANT,12>::Destroy(void)
0x18004b21a  mov     esi, 8
0x18004b21f  jmp     loc_18004B048
0x18004b224  mov     eax, 0Ah
0x18004b229  mov     word ptr [rsp+300h+var_288], ax
0x18004b22e  mov     dword ptr [rbp+200h+var_288+8], ecx
0x18004b231  mov     ecx, 8007000Eh; int
0x18004b236  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18004b23c  lea     rcx, [rbp+200h+pvarg]; pvarg
0x18004b240  call    cs:__imp_VariantClear
0x18004b246  nop
0x18004b247  lea     rcx, [rbp+200h+var_258]; pvarg
0x18004b24b  call    cs:__imp_VariantClear
0x18004b251  nop
0x18004b252  lea     rcx, [rsp+300h+psa]
0x18004b257  call    ?Destroy@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJXZ; ATL::CComSafeArray<tagVARIANT,12>::Destroy(void)
0x18004b25c  nop
0x18004b25d  lea     rcx, [rsp+300h+var_290]
0x18004b262  call    ?Destroy@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJXZ; ATL::CComSafeArray<tagVARIANT,12>::Destroy(void)
0x18004b267  mov     eax, ebx
0x18004b269  mov     rcx, [rbp+200h+var_30]
0x18004b270  xor     rcx, rsp; StackCookie
0x18004b273  call    __security_check_cookie
0x18004b278  lea     r11, [rsp+300h+var_20]
0x18004b280  mov     rbx, [r11+38h]
0x18004b284  mov     rsi, [r11+48h]
0x18004b288  mov     rsp, r11
0x18004b28b  pop     r15
0x18004b28d  pop     r14
0x18004b28f  pop     r13
0x18004b291  pop     rdi
0x18004b292  pop     rbp
0x18004b293  retn
0x18004b294  cmp     eax, 103h
0x18004b299  jz      short loc_18004B2AC
0x18004b29b  test    eax, eax
0x18004b29d  jg      short loc_18004B2A3
0x18004b29f  mov     ebx, eax
0x18004b2a1  jmp     short loc_18004B2AC
0x18004b2a3  movzx   ebx, ax
0x18004b2a6  or      ebx, 80070000h
0x18004b2ac  test    ebx, ebx
0x18004b2ae  js      short loc_18004B25D
0x18004b2b0  mov     rsi, [rsp+300h+var_290]
0x18004b2b5  mov     rcx, rdi; pvarg
0x18004b2b8  call    cs:__imp_VariantClear
0x18004b2be  mov     [rsp+300h+var_2C0], 0
0x18004b2c7  test    rsi, rsi
0x18004b2ca  jz      short loc_18004B25D
0x18004b2cc  lea     rdx, [rsp+300h+var_2C0]; ppsaOut
0x18004b2d1  mov     rcx, rsi; psa
0x18004b2d4  call    cs:__imp_SafeArrayCopy
0x18004b2da  test    eax, eax
0x18004b2dc  js      short loc_18004B307
0x18004b2de  cmp     [rsp+300h+var_2C0], 0
0x18004b2e4  jz      short loc_18004B307
0x18004b2e6  mov     rdx, rdi; unsigned __int16 *
0x18004b2e9  mov     rcx, rsi; struct tagSAFEARRAY *
0x18004b2ec  call    ?AtlSafeArrayGetActualVartype@ATL@@YAJPEAUtagSAFEARRAY@@PEAG@Z; ATL::AtlSafeArrayGetActualVartype(tagSAFEARRAY *,ushort *)
0x18004b2f1  mov     eax, 2000h
0x18004b2f6  or      [rdi], ax
0x18004b2f9  mov     rax, [rsp+300h+var_2C0]
0x18004b2fe  mov     [rdi+8], rax
0x18004b302  jmp     loc_18004B25D
0x18004b307  mov     word ptr [rdi], 0Ah
0x18004b30c  mov     [rdi+8], eax
0x18004b30f  mov     ecx, 8007000Eh; int
0x18004b314  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
