# GetMultiValueSetting(HKEY__ *,ushort const *,ATL::CComVariant &)

- ea: `0x180051d64`
- end: `0x18005208f`
- name: `?GetMultiValueSetting@@YAJPEAUHKEY__@@PEBGAEAVCComVariant@ATL@@@Z`
- size: `811`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, struct ATL::CComVariant *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022490`

## callees

- `0x180022490`
- `0x18002744c`
- `0x18003bc70`
- `0x18003c870`
- `0x180051930`
- `0x180051970`
- `0x1800519d0`
- `0x1800519e0`
- `0x180051abc`
- `0x180051b14`
- `0x180051c54`
- `0x180051d64`
- `0x180052160`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180051e14`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180051e14`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180051f0c`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180052041`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180051f0c`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180052041`

## pseudocode

```c
__int64 __fastcall GetMultiValueSetting(HKEY a1, const unsigned __int16 *a2, struct ATL::CComVariant *a3)
{
  signed int v5; // ebx
  DWORD v6; // r14d
  LSTATUS v7; // eax
  int v8; // edx
  __int16 v9; // r9
  HRESULT v10; // ecx
  HRESULT v12; // eax
  SAFEARRAY *psa; // [rsp+40h] [rbp-C0h] BYREF
  SAFEARRAY *v14; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  SAFEARRAY *v16; // [rsp+58h] [rbp-A8h] BYREF
  SAFEARRAY *ppsaOut; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-98h] BYREF
  __int64 v19; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v20; // [rsp+78h] [rbp-88h] BYREF
  SAFEARRAY *v21; // [rsp+80h] [rbp-80h]
  VARIANTARG v22; // [rsp+90h] [rbp-70h] BYREF
  _WORD v23[12]; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR ValueName[264]; // [rsp+C0h] [rbp-40h] BYREF

  v5 = 0;
  ATL::CComSafeArrayBound::`default constructor closure'((ATL::CComSafeArrayBound *)&v19);
  v19 = 0;
  ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(&v16, &v19);
  v6 = 0;
  while ( 1 )
  {
    Type = 0;
    memset_0(ValueName, 0, 0x208u);
    cchValueName = 260;
    v7 = RegEnumValueW(a1, v6, ValueName, &cchValueName, 0, &Type, 0, 0);
    if ( v7 )
      break;
    ATL::CComSafeArrayBound::`default constructor closure'((ATL::CComSafeArrayBound *)&v14);
    v14 = (SAFEARRAY *)2;
    ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(&psa, &v14);
    v23[0] = 0;
    ATL::CComVariant::operator=(v23, ValueName);
    v8 = ATL::CComSafeArray<tagVARIANT,12>::SetAt(&psa, 0, v23);
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
    memset(&v22, 0, sizeof(v22));
    v22.vt = 0;
    if ( v8 < 0 || (int)GetStoredValue(a1, 0, ValueName, v9, &v22) < 0 )
      ATL::CComVariant::~CComVariant((ATL::CComVariant *)&v22);
    v5 = ATL::CComSafeArray<tagVARIANT,12>::SetAt(&psa, 1, &v22);
    if ( v5 < 0 )
    {
      ATL::CComVariant::~CComVariant((ATL::CComVariant *)&v22);
      ATL::CComVariant::~CComVariant((ATL::CComVariant *)v23);
      ATL::CComSafeArray<tagVARIANT,12>::Destroy(&psa);
      goto LABEL_21;
    }
    ppsaOut = 0;
    if ( psa )
    {
      v10 = SafeArrayCopy(psa, &ppsaOut);
      if ( v10 < 0 || !ppsaOut )
      {
        v20 = 10;
        LODWORD(v21) = v10;
        ATL::AtlThrowImpl(-2147024882);
      }
      ATL::AtlSafeArrayGetActualVartype(psa, &v20);
      v20 |= 0x2000u;
      v21 = ppsaOut;
    }
    else
    {
      v20 = 0;
    }
    ATL::CComSafeArray<tagVARIANT,12>::Add(&v16, &v20);
    ATL::CComVariant::~CComVariant((ATL::CComVariant *)&v20);
    ++v6;
    ATL::CComVariant::~CComVariant((ATL::CComVariant *)&v22);
    ATL::CComVariant::~CComVariant((ATL::CComVariant *)v23);
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
    ATL::CComVariant::~CComVariant(a3);
    v14 = 0;
    if ( v16 )
    {
      v12 = SafeArrayCopy(v16, &v14);
      if ( v12 < 0 || !v14 )
      {
        *(_WORD *)a3 = 10;
        *((_DWORD *)a3 + 2) = v12;
        ATL::AtlThrowImpl(-2147024882);
      }
      ATL::AtlSafeArrayGetActualVartype(v16, (unsigned __int16 *)a3);
      *(_WORD *)a3 |= 0x2000u;
      *((_QWORD *)a3 + 1) = v14;
    }
  }
LABEL_21:
  ATL::CComSafeArray<tagVARIANT,12>::Destroy(&v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180051d64  mov     [rsp-8+arg_8], rbx
0x180051d69  push    rbp
0x180051d6a  push    rdi
0x180051d6b  push    r13
0x180051d6d  push    r14
0x180051d6f  push    r15
0x180051d71  lea     rbp, [rsp-1E0h]
0x180051d79  sub     rsp, 2E0h
0x180051d80  mov     rax, cs:__security_cookie
0x180051d87  xor     rax, rsp
0x180051d8a  mov     [rbp+200h+var_30], rax
0x180051d91  mov     rdi, r8
0x180051d94  mov     r15, rcx
0x180051d97  xor     ebx, ebx
0x180051d99  lea     rcx, [rsp+300h+var_290]; this
0x180051d9e  call    ??_FCComSafeArrayBound@ATL@@QEAAXXZ; ATL::CComSafeArrayBound::`default constructor closure'(void)
0x180051da3  mov     [rsp+300h+var_290], rbx
0x180051da8  lea     rdx, [rsp+300h+var_290]
0x180051dad  lea     rcx, [rsp+300h+var_2A8]
0x180051db2  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAYBOUND const *,uint)
0x180051db7  nop
0x180051db8  xor     r14d, r14d
0x180051dbb  lea     r13d, [rbx+3]
0x180051dbf  mov     [rsp+300h+Type], 0
0x180051dc7  xor     edx, edx; Val
0x180051dc9  mov     r8d, 208h; Size
0x180051dcf  lea     rcx, [rbp+200h+ValueName]; void *
0x180051dd3  call    memset_0
0x180051dd8  mov     [rsp+300h+cchValueName], 104h
0x180051de0  mov     [rsp+300h+lpcbData], 0; lpcbData
0x180051de9  mov     [rsp+300h+lpData], 0; lpData
0x180051df2  lea     rax, [rsp+300h+Type]
0x180051df7  mov     [rsp+300h+lpType], rax; lpType
0x180051dfc  mov     [rsp+300h+lpReserved], 0; lpReserved
0x180051e05  lea     r9, [rsp+300h+cchValueName]; lpcchValueName
0x180051e0a  lea     r8, [rbp+200h+ValueName]; lpValueName
0x180051e0e  mov     edx, r14d; dwIndex
0x180051e11  mov     rcx, r15; hKey
0x180051e14  call    cs:__imp_RegEnumValueW
0x180051e1b  nop     dword ptr [rax+rax+00h]
0x180051e20  test    eax, eax
0x180051e22  jnz     loc_180052002
0x180051e28  lea     rcx, [rsp+300h+var_2B8]; this
0x180051e2d  call    ??_FCComSafeArrayBound@ATL@@QEAAXXZ; ATL::CComSafeArrayBound::`default constructor closure'(void)
0x180051e32  mov     [rsp+300h+var_2B8], 2
0x180051e3b  lea     rdx, [rsp+300h+var_2B8]
0x180051e40  lea     rcx, [rsp+300h+psa]
0x180051e45  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAYBOUND const *,uint)
0x180051e4a  nop
0x180051e4b  xor     eax, eax
0x180051e4d  mov     [rbp+200h+var_258], ax
0x180051e51  lea     rdx, [rbp+200h+ValueName]
0x180051e55  lea     rcx, [rbp+200h+var_258]
0x180051e59  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x180051e5e  nop
0x180051e5f  lea     r8, [rbp+200h+var_258]
0x180051e63  xor     edx, edx
0x180051e65  lea     rcx, [rsp+300h+psa]
0x180051e6a  call    ?SetAt@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::SetAt(long,tagVARIANT const &,int)
0x180051e6f  mov     edx, eax
0x180051e71  xor     r9d, r9d
0x180051e74  mov     ecx, [rsp+300h+Type]
0x180051e78  sub     ecx, 1
0x180051e7b  jz      short loc_180051E95
0x180051e7d  sub     ecx, r13d
0x180051e80  jz      short loc_180051E8F
0x180051e82  cmp     ecx, r13d
0x180051e85  jnz     short loc_180051E9B
0x180051e87  mov     r9d, 2008h
0x180051e8d  jmp     short loc_180051E9B
0x180051e8f  movzx   r9d, r13w
0x180051e93  jmp     short loc_180051E9B
0x180051e95  mov     r9d, 8; unsigned __int16
0x180051e9b  xorps   xmm0, xmm0
0x180051e9e  xor     eax, eax
0x180051ea0  movups  [rbp+200h+var_270], xmm0
0x180051ea4  mov     [rbp+200h+var_260], rax
0x180051ea8  mov     word ptr [rbp+200h+var_270], ax
0x180051eac  test    edx, edx
0x180051eae  js      short loc_180051ECB
0x180051eb0  lea     rax, [rbp+200h+var_270]
0x180051eb4  mov     [rsp+300h+lpReserved], rax; struct ATL::CComVariant *
0x180051eb9  lea     r8, [rbp+200h+ValueName]; unsigned __int16 *
0x180051ebd  xor     edx, edx; unsigned __int16 *
0x180051ebf  mov     rcx, r15; HKEY
0x180051ec2  call    ?GetStoredValue@@YAJPEAUHKEY__@@PEBG1GAEAVCComVariant@ATL@@@Z; GetStoredValue(HKEY__ *,ushort const *,ushort const *,ushort,ATL::CComVariant &)
0x180051ec7  test    eax, eax
0x180051ec9  jns     short loc_180051ED4
0x180051ecb  lea     rcx, [rbp+200h+var_270]; this
0x180051ecf  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x180051ed4  lea     r8, [rbp+200h+var_270]
0x180051ed8  mov     edx, 1
0x180051edd  lea     rcx, [rsp+300h+psa]
0x180051ee2  call    ?SetAt@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::SetAt(long,tagVARIANT const &,int)
0x180051ee7  mov     ebx, eax
0x180051ee9  test    eax, eax
0x180051eeb  js      loc_180051FAF
0x180051ef1  mov     [rsp+300h+ppsaOut], 0
0x180051efa  cmp     [rsp+300h+psa], 0
0x180051f00  jz      short loc_180051F4F
0x180051f02  lea     rdx, [rsp+300h+ppsaOut]; ppsaOut
0x180051f07  mov     rcx, [rsp+300h+psa]; psa
0x180051f0c  call    cs:__imp_SafeArrayCopy
0x180051f13  nop     dword ptr [rax+rax+00h]
0x180051f18  mov     ecx, eax
0x180051f1a  test    eax, eax
0x180051f1c  js      short loc_180051F97
0x180051f1e  cmp     [rsp+300h+ppsaOut], 0
0x180051f24  jz      short loc_180051F97
0x180051f26  lea     rdx, [rsp+300h+var_288]; unsigned __int16 *
0x180051f2b  mov     rcx, [rsp+300h+psa]; struct tagSAFEARRAY *
0x180051f30  call    ?AtlSafeArrayGetActualVartype@ATL@@YAJPEAUtagSAFEARRAY@@PEAG@Z; ATL::AtlSafeArrayGetActualVartype(tagSAFEARRAY *,ushort *)
0x180051f35  mov     eax, 2000h
0x180051f3a  or      [rsp+300h+var_288], ax
0x180051f3f  mov     eax, dword ptr [rsp+300h+ppsaOut]
0x180051f43  mov     dword ptr [rbp+200h+var_280], eax
0x180051f46  mov     eax, dword ptr [rsp+300h+ppsaOut+4]
0x180051f4a  mov     dword ptr [rbp+200h+var_280+4], eax
0x180051f4d  jmp     short loc_180051F56
0x180051f4f  xor     eax, eax
0x180051f51  mov     [rsp+300h+var_288], ax
0x180051f56  lea     rdx, [rsp+300h+var_288]
0x180051f5b  lea     rcx, [rsp+300h+var_2A8]
0x180051f60  call    ?Add@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::Add(tagVARIANT const &,int)
0x180051f65  nop
0x180051f66  lea     rcx, [rsp+300h+var_288]; this
0x180051f6b  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x180051f70  nop
0x180051f71  inc     r14d
0x180051f74  lea     rcx, [rbp+200h+var_270]; this
0x180051f78  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x180051f7d  nop
0x180051f7e  lea     rcx, [rbp+200h+var_258]; this
0x180051f82  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x180051f87  nop
0x180051f88  lea     rcx, [rsp+300h+psa]
0x180051f8d  call    ?Destroy@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJXZ; ATL::CComSafeArray<tagVARIANT,12>::Destroy(void)
0x180051f92  jmp     loc_180051DBF
0x180051f97  mov     eax, 0Ah
0x180051f9c  mov     [rsp+300h+var_288], ax
0x180051fa1  mov     dword ptr [rbp+200h+var_280], ecx
0x180051fa4  mov     ecx, 8007000Eh; int
0x180051fa9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180051faf  lea     rcx, [rbp+200h+var_270]; this
0x180051fb3  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x180051fb8  nop
0x180051fb9  lea     rcx, [rbp+200h+var_258]; this
0x180051fbd  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x180051fc2  nop
0x180051fc3  lea     rcx, [rsp+300h+psa]
0x180051fc8  call    ?Destroy@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJXZ; ATL::CComSafeArray<tagVARIANT,12>::Destroy(void)
0x180051fcd  nop
0x180051fce  lea     rcx, [rsp+300h+var_2A8]
0x180051fd3  call    ?Destroy@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJXZ; ATL::CComSafeArray<tagVARIANT,12>::Destroy(void)
0x180051fd8  mov     eax, ebx
0x180051fda  mov     rcx, [rbp+200h+var_30]
0x180051fe1  xor     rcx, rsp; StackCookie
0x180051fe4  call    __security_check_cookie
0x180051fe9  mov     rbx, [rsp+300h+arg_8]
0x180051ff1  add     rsp, 2E0h
0x180051ff8  pop     r15
0x180051ffa  pop     r14
0x180051ffc  pop     r13
0x180051ffe  pop     rdi
0x180051fff  pop     rbp
0x180052000  retn
0x180052002  cmp     eax, 103h
0x180052007  jz      short loc_18005201A
0x180052009  test    eax, eax
0x18005200b  jg      short loc_180052011
0x18005200d  mov     ebx, eax
0x18005200f  jmp     short loc_18005201A
0x180052011  movzx   ebx, ax
0x180052014  or      ebx, 80070000h
0x18005201a  test    ebx, ebx
0x18005201c  js      short loc_180051FCE
0x18005201e  mov     rcx, rdi; this
0x180052021  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x180052026  mov     [rsp+300h+var_2B8], 0
0x18005202f  cmp     [rsp+300h+var_2A8], 0
0x180052035  jz      short loc_180051FCE
0x180052037  lea     rdx, [rsp+300h+var_2B8]; ppsaOut
0x18005203c  mov     rcx, [rsp+300h+var_2A8]; psa
0x180052041  call    cs:__imp_SafeArrayCopy
0x180052048  nop     dword ptr [rax+rax+00h]
0x18005204d  test    eax, eax
0x18005204f  js      short loc_18005207C
0x180052051  cmp     [rsp+300h+var_2B8], 0
0x180052057  jz      short loc_18005207C
0x180052059  mov     rdx, rdi; unsigned __int16 *
0x18005205c  mov     rcx, [rsp+300h+var_2A8]; struct tagSAFEARRAY *
0x180052061  call    ?AtlSafeArrayGetActualVartype@ATL@@YAJPEAUtagSAFEARRAY@@PEAG@Z; ATL::AtlSafeArrayGetActualVartype(tagSAFEARRAY *,ushort *)
0x180052066  mov     eax, 2000h
0x18005206b  or      [rdi], ax
0x18005206e  mov     rax, [rsp+300h+var_2B8]
0x180052073  mov     [rdi+8], rax
0x180052077  jmp     loc_180051FCE
0x18005207c  mov     word ptr [rdi], 0Ah
0x180052081  mov     [rdi+8], eax
0x180052084  mov     ecx, 8007000Eh; int
0x180052089  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
