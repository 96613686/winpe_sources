# GetMultiValueSetting(HKEY__ *,ushort const *,ATL::CComVariant &)

- ea: `0x18001a91c`
- end: `0x18001ac5a`
- name: `?GetMultiValueSetting@@YAJPEAUHKEY__@@PEBGAEAVCComVariant@ATL@@@Z`
- size: `830`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, struct ATL::CComVariant *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800025b0`

## callees

- `0x1800025b0`
- `0x180002940`
- `0x18000a520`
- `0x18000aef8`
- `0x18000f700`
- `0x18001a56c`
- `0x18001a5a8`
- `0x18001a610`
- `0x18001a6d4`
- `0x18001a728`
- `0x18001a82c`
- `0x18001a91c`
- `0x18001ad58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001a9e1`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001a9e1`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001aadf`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001ac14`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001aadf`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001ac14`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall GetMultiValueSetting(HKEY a1, const unsigned __int16 *a2, struct ATL::CComVariant *a3)
{
  signed int v5; // ebx
  DWORD v6; // r14d
  LSTATUS v7; // eax
  int v8; // edx
  __int16 v9; // r9
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
  unsigned __int16 v22; // [rsp+78h] [rbp-88h] BYREF
  SAFEARRAY *v23; // [rsp+80h] [rbp-80h]
  VARIANTARG v24; // [rsp+90h] [rbp-70h] BYREF
  _WORD v25[12]; // [rsp+A8h] [rbp-58h] BYREF
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
    v25[0] = 0;
    ATL::CComVariant::operator=(v25, ValueName);
    v8 = ATL::CComSafeArray<tagVARIANT,12>::SetAt(&psa, 0, v25);
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
    memset(&v24, 0, sizeof(v24));
    v24.vt = 0;
    if ( v8 < 0 || (int)GetStoredValue(a1, 0, ValueName, v9, &v24) < 0 )
      ATL::CComVariant::Clear((ATL::CComVariant *)&v24);
    v5 = ATL::CComSafeArray<tagVARIANT,12>::SetAt(&psa, 1, &v24);
    if ( v5 < 0 )
    {
      ATL::CComVariant::Clear((ATL::CComVariant *)&v24);
      ATL::CComVariant::Clear((ATL::CComVariant *)v25);
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
        v22 = 10;
        LODWORD(v23) = v11;
        ATL::AtlThrowImpl(-2147024882);
      }
      ATL::AtlSafeArrayGetActualVartype(v10, &v22);
      v22 |= 0x2000u;
      v23 = ppsaOut;
    }
    else
    {
      v22 = 0;
    }
    ATL::CComSafeArray<tagVARIANT,12>::Add(&v21, &v22);
    ATL::CComVariant::Clear((ATL::CComVariant *)&v22);
    ++v6;
    ATL::CComVariant::Clear((ATL::CComVariant *)&v24);
    ATL::CComVariant::Clear((ATL::CComVariant *)v25);
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
    ATL::CComVariant::Clear(a3);
    v15 = 0;
    if ( v13 )
    {
      v14 = SafeArrayCopy(v13, &v15);
      if ( v14 < 0 || !v15 )
      {
        *(_WORD *)a3 = 10;
        *((_DWORD *)a3 + 2) = v14;
        ATL::AtlThrowImpl(-2147024882);
      }
      ATL::AtlSafeArrayGetActualVartype(v13, (unsigned __int16 *)a3);
      *(_WORD *)a3 |= 0x2000u;
      *((_QWORD *)a3 + 1) = v15;
    }
  }
LABEL_21:
  ATL::CComSafeArray<tagVARIANT,12>::Destroy(&v21);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001a91c  mov     [rsp-8+arg_8], rbx
0x18001a921  mov     [rsp-8+arg_18], rsi
0x18001a926  push    rbp
0x18001a927  push    rdi
0x18001a928  push    r13
0x18001a92a  push    r14
0x18001a92c  push    r15
0x18001a92e  lea     rbp, [rsp-1E0h]
0x18001a936  sub     rsp, 2E0h
0x18001a93d  mov     rax, cs:__security_cookie
0x18001a944  xor     rax, rsp
0x18001a947  mov     [rbp+200h+var_30], rax
0x18001a94e  mov     rdi, r8
0x18001a951  mov     r15, rcx
0x18001a954  xor     ebx, ebx
0x18001a956  lea     r9, ??_FCComSafeArrayBound@ATL@@QEAAXXZ; void *(*)(void *)
0x18001a95d  lea     esi, [rbx+8]
0x18001a960  lea     r8d, [rbx+1]; unsigned __int64
0x18001a964  mov     edx, esi; unsigned __int64
0x18001a966  lea     rcx, [rsp+300h+var_298]; void *
0x18001a96b  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18001a970  mov     [rsp+300h+var_298], rbx
0x18001a975  lea     rdx, [rsp+300h+var_298]
0x18001a97a  lea     rcx, [rsp+300h+var_290]
0x18001a97f  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAYBOUND const *,uint)
0x18001a984  nop
0x18001a985  xor     r14d, r14d
0x18001a988  lea     r13d, [rbx+3]
0x18001a98c  mov     [rsp+300h+Type], 0
0x18001a994  xor     edx, edx; Val
0x18001a996  mov     r8d, 208h; Size
0x18001a99c  lea     rcx, [rbp+200h+ValueName]; void *
0x18001a9a0  call    memset_0
0x18001a9a5  mov     [rsp+300h+cchValueName], 104h
0x18001a9ad  mov     [rsp+300h+lpcbData], 0; lpcbData
0x18001a9b6  mov     [rsp+300h+lpData], 0; lpData
0x18001a9bf  lea     rax, [rsp+300h+Type]
0x18001a9c4  mov     [rsp+300h+lpType], rax; lpType
0x18001a9c9  mov     [rsp+300h+lpReserved], 0; lpReserved
0x18001a9d2  lea     r9, [rsp+300h+cchValueName]; lpcchValueName
0x18001a9d7  lea     r8, [rbp+200h+ValueName]; lpValueName
0x18001a9db  mov     edx, r14d; dwIndex
0x18001a9de  mov     rcx, r15; hKey
0x18001a9e1  call    cs:__imp_RegEnumValueW
0x18001a9e7  test    eax, eax
0x18001a9e9  jnz     loc_18001ABD5
0x18001a9ef  lea     r9, ??_FCComSafeArrayBound@ATL@@QEAAXXZ; void *(*)(void *)
0x18001a9f6  lea     r8d, [rax+1]; unsigned __int64
0x18001a9fa  mov     rdx, rsi; unsigned __int64
0x18001a9fd  lea     rcx, [rsp+300h+var_2C0]; void *
0x18001aa02  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18001aa07  mov     [rsp+300h+var_2C0], 2
0x18001aa10  lea     rdx, [rsp+300h+var_2C0]
0x18001aa15  lea     rcx, [rsp+300h+psa]
0x18001aa1a  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAYBOUND const *,uint)
0x18001aa1f  nop
0x18001aa20  xor     eax, eax
0x18001aa22  mov     [rbp+200h+var_258], ax
0x18001aa26  lea     rdx, [rbp+200h+ValueName]
0x18001aa2a  lea     rcx, [rbp+200h+var_258]
0x18001aa2e  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x18001aa33  nop
0x18001aa34  lea     r8, [rbp+200h+var_258]
0x18001aa38  xor     edx, edx
0x18001aa3a  lea     rcx, [rsp+300h+psa]
0x18001aa3f  call    ?SetAt@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::SetAt(long,tagVARIANT const &,int)
0x18001aa44  mov     edx, eax
0x18001aa46  xor     r9d, r9d
0x18001aa49  mov     ecx, [rsp+300h+Type]
0x18001aa4d  sub     ecx, 1
0x18001aa50  jz      short loc_18001AA6A
0x18001aa52  sub     ecx, r13d
0x18001aa55  jz      short loc_18001AA64
0x18001aa57  cmp     ecx, r13d
0x18001aa5a  jnz     short loc_18001AA6E
0x18001aa5c  mov     r9d, 2008h
0x18001aa62  jmp     short loc_18001AA6E
0x18001aa64  movzx   r9d, r13w
0x18001aa68  jmp     short loc_18001AA6E
0x18001aa6a  movzx   r9d, si; unsigned __int16
0x18001aa6e  xorps   xmm0, xmm0
0x18001aa71  xor     eax, eax
0x18001aa73  movups  [rbp+200h+var_270], xmm0
0x18001aa77  mov     [rbp+200h+var_260], rax
0x18001aa7b  mov     word ptr [rbp+200h+var_270], ax
0x18001aa7f  test    edx, edx
0x18001aa81  js      short loc_18001AA9E
0x18001aa83  lea     rax, [rbp+200h+var_270]
0x18001aa87  mov     [rsp+300h+lpReserved], rax; struct ATL::CComVariant *
0x18001aa8c  lea     r8, [rbp+200h+ValueName]; unsigned __int16 *
0x18001aa90  xor     edx, edx; unsigned __int16 *
0x18001aa92  mov     rcx, r15; HKEY
0x18001aa95  call    ?GetStoredValue@@YAJPEAUHKEY__@@PEBG1GAEAVCComVariant@ATL@@@Z; GetStoredValue(HKEY__ *,ushort const *,ushort const *,ushort,ATL::CComVariant &)
0x18001aa9a  test    eax, eax
0x18001aa9c  jns     short loc_18001AAA7
0x18001aa9e  lea     rcx, [rbp+200h+var_270]; this
0x18001aaa2  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x18001aaa7  lea     r8, [rbp+200h+var_270]
0x18001aaab  mov     edx, 1
0x18001aab0  lea     rcx, [rsp+300h+psa]
0x18001aab5  call    ?SetAt@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::SetAt(long,tagVARIANT const &,int)
0x18001aaba  mov     ebx, eax
0x18001aabc  test    eax, eax
0x18001aabe  js      loc_18001AB7F
0x18001aac4  mov     rsi, [rsp+300h+psa]
0x18001aac9  mov     [rsp+300h+ppsaOut], 0
0x18001aad2  test    rsi, rsi
0x18001aad5  jz      short loc_18001AB1A
0x18001aad7  lea     rdx, [rsp+300h+ppsaOut]; ppsaOut
0x18001aadc  mov     rcx, rsi; psa
0x18001aadf  call    cs:__imp_SafeArrayCopy
0x18001aae5  mov     ecx, eax
0x18001aae7  test    eax, eax
0x18001aae9  js      short loc_18001AB67
0x18001aaeb  cmp     [rsp+300h+ppsaOut], 0
0x18001aaf1  jz      short loc_18001AB67
0x18001aaf3  lea     rdx, [rsp+300h+var_288]; unsigned __int16 *
0x18001aaf8  mov     rcx, rsi; struct tagSAFEARRAY *
0x18001aafb  call    ?AtlSafeArrayGetActualVartype@ATL@@YAJPEAUtagSAFEARRAY@@PEAG@Z; ATL::AtlSafeArrayGetActualVartype(tagSAFEARRAY *,ushort *)
0x18001ab00  mov     eax, 2000h
0x18001ab05  or      [rsp+300h+var_288], ax
0x18001ab0a  mov     eax, dword ptr [rsp+300h+ppsaOut]
0x18001ab0e  mov     dword ptr [rbp+200h+var_280], eax
0x18001ab11  mov     eax, dword ptr [rsp+300h+ppsaOut+4]
0x18001ab15  mov     dword ptr [rbp+200h+var_280+4], eax
0x18001ab18  jmp     short loc_18001AB21
0x18001ab1a  xor     eax, eax
0x18001ab1c  mov     [rsp+300h+var_288], ax
0x18001ab21  lea     rdx, [rsp+300h+var_288]
0x18001ab26  lea     rcx, [rsp+300h+var_290]
0x18001ab2b  call    ?Add@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::Add(tagVARIANT const &,int)
0x18001ab30  nop
0x18001ab31  lea     rcx, [rsp+300h+var_288]; this
0x18001ab36  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x18001ab3b  nop
0x18001ab3c  inc     r14d
0x18001ab3f  lea     rcx, [rbp+200h+var_270]; this
0x18001ab43  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x18001ab48  nop
0x18001ab49  lea     rcx, [rbp+200h+var_258]; this
0x18001ab4d  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x18001ab52  nop
0x18001ab53  lea     rcx, [rsp+300h+psa]
0x18001ab58  call    ?Destroy@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJXZ; ATL::CComSafeArray<tagVARIANT,12>::Destroy(void)
0x18001ab5d  mov     esi, 8
0x18001ab62  jmp     loc_18001A98C
0x18001ab67  mov     eax, 0Ah
0x18001ab6c  mov     [rsp+300h+var_288], ax
0x18001ab71  mov     dword ptr [rbp+200h+var_280], ecx
0x18001ab74  mov     ecx, 8007000Eh; int
0x18001ab79  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001ab7f  lea     rcx, [rbp+200h+var_270]; this
0x18001ab83  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x18001ab88  nop
0x18001ab89  lea     rcx, [rbp+200h+var_258]; this
0x18001ab8d  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x18001ab92  nop
0x18001ab93  lea     rcx, [rsp+300h+psa]
0x18001ab98  call    ?Destroy@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJXZ; ATL::CComSafeArray<tagVARIANT,12>::Destroy(void)
0x18001ab9d  nop
0x18001ab9e  lea     rcx, [rsp+300h+var_290]
0x18001aba3  call    ?Destroy@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJXZ; ATL::CComSafeArray<tagVARIANT,12>::Destroy(void)
0x18001aba8  mov     eax, ebx
0x18001abaa  mov     rcx, [rbp+200h+var_30]
0x18001abb1  xor     rcx, rsp; StackCookie
0x18001abb4  call    __security_check_cookie
0x18001abb9  lea     r11, [rsp+300h+var_20]
0x18001abc1  mov     rbx, [r11+38h]
0x18001abc5  mov     rsi, [r11+48h]
0x18001abc9  mov     rsp, r11
0x18001abcc  pop     r15
0x18001abce  pop     r14
0x18001abd0  pop     r13
0x18001abd2  pop     rdi
0x18001abd3  pop     rbp
0x18001abd4  retn
0x18001abd5  cmp     eax, 103h
0x18001abda  jz      short loc_18001ABED
0x18001abdc  test    eax, eax
0x18001abde  jg      short loc_18001ABE4
0x18001abe0  mov     ebx, eax
0x18001abe2  jmp     short loc_18001ABED
0x18001abe4  movzx   ebx, ax
0x18001abe7  or      ebx, 80070000h
0x18001abed  test    ebx, ebx
0x18001abef  js      short loc_18001AB9E
0x18001abf1  mov     rsi, [rsp+300h+var_290]
0x18001abf6  mov     rcx, rdi; this
0x18001abf9  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x18001abfe  mov     [rsp+300h+var_2C0], 0
0x18001ac07  test    rsi, rsi
0x18001ac0a  jz      short loc_18001AB9E
0x18001ac0c  lea     rdx, [rsp+300h+var_2C0]; ppsaOut
0x18001ac11  mov     rcx, rsi; psa
0x18001ac14  call    cs:__imp_SafeArrayCopy
0x18001ac1a  test    eax, eax
0x18001ac1c  js      short loc_18001AC47
0x18001ac1e  cmp     [rsp+300h+var_2C0], 0
0x18001ac24  jz      short loc_18001AC47
0x18001ac26  mov     rdx, rdi; unsigned __int16 *
0x18001ac29  mov     rcx, rsi; struct tagSAFEARRAY *
0x18001ac2c  call    ?AtlSafeArrayGetActualVartype@ATL@@YAJPEAUtagSAFEARRAY@@PEAG@Z; ATL::AtlSafeArrayGetActualVartype(tagSAFEARRAY *,ushort *)
0x18001ac31  mov     eax, 2000h
0x18001ac36  or      [rdi], ax
0x18001ac39  mov     rax, [rsp+300h+var_2C0]
0x18001ac3e  mov     [rdi+8], rax
0x18001ac42  jmp     loc_18001AB9E
0x18001ac47  mov     word ptr [rdi], 0Ah
0x18001ac4c  mov     [rdi+8], eax
0x18001ac4f  mov     ecx, 8007000Eh; int
0x18001ac54  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
