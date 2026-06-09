# GetMultiValueSetting(HKEY__ *,ushort const *,ATL::CComVariant &)

- ea: `0x18004ea70`
- end: `0x18004ed88`
- name: `?GetMultiValueSetting@@YAJPEAUHKEY__@@PEBGAEAVCComVariant@ATL@@@Z`
- size: `792`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, struct ATL::CComVariant *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e560`

## callees

- `0x18001e560`
- `0x180024c20`
- `0x18003a730`
- `0x18003b310`
- `0x18004e6c0`
- `0x18004e6fc`
- `0x18004e754`
- `0x18004e764`
- `0x18004e828`
- `0x18004e87c`
- `0x18004e980`
- `0x18004ea70`
- `0x18004ee50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004eb20`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004eb20`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18004ec12`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18004ed40`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18004ec12`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18004ed40`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetMultiValueSetting(HKEY a1, const unsigned __int16 *a2, VARIANTARG *a3)
{
  signed int v5; // ebx
  DWORD v6; // r14d
  LSTATUS v7; // eax
  int v8; // edx
  unsigned __int16 v9; // r9
  HRESULT v10; // ecx
  HRESULT v12; // eax
  SAFEARRAY *psa; // [rsp+40h] [rbp-C0h] BYREF
  SAFEARRAY *v14; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  SAFEARRAY *v16; // [rsp+58h] [rbp-A8h] BYREF
  SAFEARRAY *ppsaOut; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-98h] BYREF
  __int64 v19; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG v20; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG v21; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG v22; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR ValueName[264]; // [rsp+C0h] [rbp-40h] BYREF

  v5 = 0;
  ATL::CComSafeArrayBound::`default constructor closure'((ATL::CComSafeArrayBound *)&v19);
  v19 = 0;
  ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(&v16);
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
    ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(&psa);
    v22.vt = 0;
    ATL::CComVariant::operator=(&v22, ValueName);
    v8 = ATL::CComSafeArray<tagVARIANT,12>::SetAt(&psa, 0, &v22);
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
    memset(&v21, 0, sizeof(v21));
    v21.vt = 0;
    if ( v8 < 0 || GetStoredValue(a1, 0, ValueName, v9, (struct ATL::CComVariant *)&v21) < 0 )
      ATL::CComVariant::~CComVariant(&v21);
    v5 = ATL::CComSafeArray<tagVARIANT,12>::SetAt(&psa, 1, &v21);
    if ( v5 < 0 )
    {
      ATL::CComVariant::~CComVariant(&v21);
      ATL::CComVariant::~CComVariant(&v22);
      ATL::CComSafeArray<tagVARIANT,12>::Destroy(&psa);
      goto LABEL_21;
    }
    ppsaOut = 0;
    if ( psa )
    {
      v10 = SafeArrayCopy(psa, &ppsaOut);
      if ( v10 < 0 || !ppsaOut )
      {
        v20.vt = 10;
        v20.lVal = v10;
        ATL::AtlThrowImpl(-2147024882);
      }
      ATL::AtlSafeArrayGetActualVartype(psa, &v20.vt);
      v20.vt |= 0x2000u;
      v20.llVal = (LONGLONG)ppsaOut;
    }
    else
    {
      v20.vt = 0;
    }
    ATL::CComSafeArray<tagVARIANT,12>::Add(&v16, (__int64)&v20);
    ATL::CComVariant::~CComVariant(&v20);
    ++v6;
    ATL::CComVariant::~CComVariant(&v21);
    ATL::CComVariant::~CComVariant(&v22);
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
        a3->vt = 10;
        a3->lVal = v12;
        ATL::AtlThrowImpl(-2147024882);
      }
      ATL::AtlSafeArrayGetActualVartype(v16, &a3->vt);
      a3->vt |= 0x2000u;
      a3->llVal = (LONGLONG)v14;
    }
  }
LABEL_21:
  ATL::CComSafeArray<tagVARIANT,12>::Destroy(&v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004ea70  mov     [rsp-8+arg_8], rbx
0x18004ea75  push    rbp
0x18004ea76  push    rdi
0x18004ea77  push    r13
0x18004ea79  push    r14
0x18004ea7b  push    r15
0x18004ea7d  lea     rbp, [rsp-1E0h]
0x18004ea85  sub     rsp, 2E0h
0x18004ea8c  mov     rax, cs:__security_cookie
0x18004ea93  xor     rax, rsp
0x18004ea96  mov     [rbp+200h+var_30], rax
0x18004ea9d  mov     rdi, r8
0x18004eaa0  mov     r15, rcx
0x18004eaa3  xor     ebx, ebx
0x18004eaa5  lea     rcx, [rsp+300h+var_290]; this
0x18004eaaa  call    ??_FCComSafeArrayBound@ATL@@QEAAXXZ; ATL::CComSafeArrayBound::`default constructor closure'(void)
0x18004eaaf  mov     [rsp+300h+var_290], rbx
0x18004eab4  lea     rdx, [rsp+300h+var_290]
0x18004eab9  lea     rcx, [rsp+300h+var_2A8]
0x18004eabe  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAYBOUND const *,uint)
0x18004eac3  nop
0x18004eac4  xor     r14d, r14d
0x18004eac7  lea     r13d, [rbx+3]
0x18004eacb  mov     [rsp+300h+Type], 0
0x18004ead3  xor     edx, edx; Val
0x18004ead5  mov     r8d, 208h; Size
0x18004eadb  lea     rcx, [rbp+200h+ValueName]; void *
0x18004eadf  call    memset_0
0x18004eae4  mov     [rsp+300h+cchValueName], 104h
0x18004eaec  mov     [rsp+300h+lpcbData], 0; lpcbData
0x18004eaf5  mov     [rsp+300h+lpData], 0; lpData
0x18004eafe  lea     rax, [rsp+300h+Type]
0x18004eb03  mov     [rsp+300h+lpType], rax; lpType
0x18004eb08  mov     [rsp+300h+lpReserved], 0; lpReserved
0x18004eb11  lea     r9, [rsp+300h+cchValueName]; lpcchValueName
0x18004eb16  lea     r8, [rbp+200h+ValueName]; lpValueName
0x18004eb1a  mov     edx, r14d; dwIndex
0x18004eb1d  mov     rcx, r15; hKey
0x18004eb20  call    cs:__imp_RegEnumValueW
0x18004eb26  test    eax, eax
0x18004eb28  jnz     loc_18004ED01
0x18004eb2e  lea     rcx, [rsp+300h+var_2B8]; this
0x18004eb33  call    ??_FCComSafeArrayBound@ATL@@QEAAXXZ; ATL::CComSafeArrayBound::`default constructor closure'(void)
0x18004eb38  mov     [rsp+300h+var_2B8], 2
0x18004eb41  lea     rdx, [rsp+300h+var_2B8]
0x18004eb46  lea     rcx, [rsp+300h+psa]
0x18004eb4b  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAYBOUND const *,uint)
0x18004eb50  nop
0x18004eb51  xor     eax, eax
0x18004eb53  mov     word ptr [rbp+200h+var_258], ax
0x18004eb57  lea     rdx, [rbp+200h+ValueName]
0x18004eb5b  lea     rcx, [rbp+200h+var_258]
0x18004eb5f  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x18004eb64  nop
0x18004eb65  lea     r8, [rbp+200h+var_258]
0x18004eb69  xor     edx, edx
0x18004eb6b  lea     rcx, [rsp+300h+psa]
0x18004eb70  call    ?SetAt@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::SetAt(long,tagVARIANT const &,int)
0x18004eb75  mov     edx, eax
0x18004eb77  xor     r9d, r9d
0x18004eb7a  mov     ecx, [rsp+300h+Type]
0x18004eb7e  sub     ecx, 1
0x18004eb81  jz      short loc_18004EB9B
0x18004eb83  sub     ecx, r13d
0x18004eb86  jz      short loc_18004EB95
0x18004eb88  cmp     ecx, r13d
0x18004eb8b  jnz     short loc_18004EBA1
0x18004eb8d  mov     r9d, 2008h
0x18004eb93  jmp     short loc_18004EBA1
0x18004eb95  movzx   r9d, r13w
0x18004eb99  jmp     short loc_18004EBA1
0x18004eb9b  mov     r9d, 8; unsigned __int16
0x18004eba1  xorps   xmm0, xmm0
0x18004eba4  xor     eax, eax
0x18004eba6  movups  [rbp+200h+var_270], xmm0
0x18004ebaa  mov     [rbp+200h+var_260], rax
0x18004ebae  mov     word ptr [rbp+200h+var_270], ax
0x18004ebb2  test    edx, edx
0x18004ebb4  js      short loc_18004EBD1
0x18004ebb6  lea     rax, [rbp+200h+var_270]
0x18004ebba  mov     [rsp+300h+lpReserved], rax; struct ATL::CComVariant *
0x18004ebbf  lea     r8, [rbp+200h+ValueName]; unsigned __int16 *
0x18004ebc3  xor     edx, edx; unsigned __int16 *
0x18004ebc5  mov     rcx, r15; HKEY
0x18004ebc8  call    ?GetStoredValue@@YAJPEAUHKEY__@@PEBG1GAEAVCComVariant@ATL@@@Z; GetStoredValue(HKEY__ *,ushort const *,ushort const *,ushort,ATL::CComVariant &)
0x18004ebcd  test    eax, eax
0x18004ebcf  jns     short loc_18004EBDA
0x18004ebd1  lea     rcx, [rbp+200h+var_270]; this
0x18004ebd5  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x18004ebda  lea     r8, [rbp+200h+var_270]
0x18004ebde  mov     edx, 1
0x18004ebe3  lea     rcx, [rsp+300h+psa]
0x18004ebe8  call    ?SetAt@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::SetAt(long,tagVARIANT const &,int)
0x18004ebed  mov     ebx, eax
0x18004ebef  test    eax, eax
0x18004ebf1  js      loc_18004ECAF
0x18004ebf7  mov     [rsp+300h+ppsaOut], 0
0x18004ec00  cmp     [rsp+300h+psa], 0
0x18004ec06  jz      short loc_18004EC4F
0x18004ec08  lea     rdx, [rsp+300h+ppsaOut]; ppsaOut
0x18004ec0d  mov     rcx, [rsp+300h+psa]; psa
0x18004ec12  call    cs:__imp_SafeArrayCopy
0x18004ec18  mov     ecx, eax
0x18004ec1a  test    eax, eax
0x18004ec1c  js      short loc_18004EC97
0x18004ec1e  cmp     [rsp+300h+ppsaOut], 0
0x18004ec24  jz      short loc_18004EC97
0x18004ec26  lea     rdx, [rsp+300h+var_288]; unsigned __int16 *
0x18004ec2b  mov     rcx, [rsp+300h+psa]; struct tagSAFEARRAY *
0x18004ec30  call    ?AtlSafeArrayGetActualVartype@ATL@@YAJPEAUtagSAFEARRAY@@PEAG@Z; ATL::AtlSafeArrayGetActualVartype(tagSAFEARRAY *,ushort *)
0x18004ec35  mov     eax, 2000h
0x18004ec3a  or      [rsp+300h+var_288], ax
0x18004ec3f  mov     eax, dword ptr [rsp+300h+ppsaOut]
0x18004ec43  mov     dword ptr [rbp+200h+var_280], eax
0x18004ec46  mov     eax, dword ptr [rsp+300h+ppsaOut+4]
0x18004ec4a  mov     dword ptr [rbp+200h+var_280+4], eax
0x18004ec4d  jmp     short loc_18004EC56
0x18004ec4f  xor     eax, eax
0x18004ec51  mov     [rsp+300h+var_288], ax
0x18004ec56  lea     rdx, [rsp+300h+var_288]
0x18004ec5b  lea     rcx, [rsp+300h+var_2A8]
0x18004ec60  call    ?Add@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::Add(tagVARIANT const &,int)
0x18004ec65  nop
0x18004ec66  lea     rcx, [rsp+300h+var_288]; this
0x18004ec6b  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x18004ec70  nop
0x18004ec71  inc     r14d
0x18004ec74  lea     rcx, [rbp+200h+var_270]; this
0x18004ec78  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x18004ec7d  nop
0x18004ec7e  lea     rcx, [rbp+200h+var_258]; this
0x18004ec82  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x18004ec87  nop
0x18004ec88  lea     rcx, [rsp+300h+psa]
0x18004ec8d  call    ?Destroy@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJXZ; ATL::CComSafeArray<tagVARIANT,12>::Destroy(void)
0x18004ec92  jmp     loc_18004EACB
0x18004ec97  mov     eax, 0Ah
0x18004ec9c  mov     [rsp+300h+var_288], ax
0x18004eca1  mov     dword ptr [rbp+200h+var_280], ecx
0x18004eca4  mov     ecx, 8007000Eh; int
0x18004eca9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18004ecaf  lea     rcx, [rbp+200h+var_270]; this
0x18004ecb3  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x18004ecb8  nop
0x18004ecb9  lea     rcx, [rbp+200h+var_258]; this
0x18004ecbd  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x18004ecc2  nop
0x18004ecc3  lea     rcx, [rsp+300h+psa]
0x18004ecc8  call    ?Destroy@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJXZ; ATL::CComSafeArray<tagVARIANT,12>::Destroy(void)
0x18004eccd  nop
0x18004ecce  lea     rcx, [rsp+300h+var_2A8]
0x18004ecd3  call    ?Destroy@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJXZ; ATL::CComSafeArray<tagVARIANT,12>::Destroy(void)
0x18004ecd8  mov     eax, ebx
0x18004ecda  mov     rcx, [rbp+200h+var_30]
0x18004ece1  xor     rcx, rsp; StackCookie
0x18004ece4  call    __security_check_cookie
0x18004ece9  mov     rbx, [rsp+300h+arg_8]
0x18004ecf1  add     rsp, 2E0h
0x18004ecf8  pop     r15
0x18004ecfa  pop     r14
0x18004ecfc  pop     r13
0x18004ecfe  pop     rdi
0x18004ecff  pop     rbp
0x18004ed00  retn
0x18004ed01  cmp     eax, 103h
0x18004ed06  jz      short loc_18004ED19
0x18004ed08  test    eax, eax
0x18004ed0a  jg      short loc_18004ED10
0x18004ed0c  mov     ebx, eax
0x18004ed0e  jmp     short loc_18004ED19
0x18004ed10  movzx   ebx, ax
0x18004ed13  or      ebx, 80070000h
0x18004ed19  test    ebx, ebx
0x18004ed1b  js      short loc_18004ECCE
0x18004ed1d  mov     rcx, rdi; this
0x18004ed20  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x18004ed25  mov     [rsp+300h+var_2B8], 0
0x18004ed2e  cmp     [rsp+300h+var_2A8], 0
0x18004ed34  jz      short loc_18004ECCE
0x18004ed36  lea     rdx, [rsp+300h+var_2B8]; ppsaOut
0x18004ed3b  mov     rcx, [rsp+300h+var_2A8]; psa
0x18004ed40  call    cs:__imp_SafeArrayCopy
0x18004ed46  test    eax, eax
0x18004ed48  js      short loc_18004ED75
0x18004ed4a  cmp     [rsp+300h+var_2B8], 0
0x18004ed50  jz      short loc_18004ED75
0x18004ed52  mov     rdx, rdi; unsigned __int16 *
0x18004ed55  mov     rcx, [rsp+300h+var_2A8]; struct tagSAFEARRAY *
0x18004ed5a  call    ?AtlSafeArrayGetActualVartype@ATL@@YAJPEAUtagSAFEARRAY@@PEAG@Z; ATL::AtlSafeArrayGetActualVartype(tagSAFEARRAY *,ushort *)
0x18004ed5f  mov     eax, 2000h
0x18004ed64  or      [rdi], ax
0x18004ed67  mov     rax, [rsp+300h+var_2B8]
0x18004ed6c  mov     [rdi+8], rax
0x18004ed70  jmp     loc_18004ECCE
0x18004ed75  mov     word ptr [rdi], 0Ah
0x18004ed7a  mov     [rdi+8], eax
0x18004ed7d  mov     ecx, 8007000Eh; int
0x18004ed82  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
