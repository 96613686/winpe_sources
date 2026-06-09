# GetMultiValueSetting(HKEY__ *,ushort const *,ATL::CComVariant &)

- ea: `0x180086294`
- end: `0x1800865ae`
- name: `?GetMultiValueSetting@@YAJPEAUHKEY__@@PEBGAEAVCComVariant@ATL@@@Z`
- size: `794`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, struct ATL::CComVariant *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037c3c`

## callees

- `0x1800301ac`
- `0x180030234`
- `0x180037c3c`
- `0x180039610`
- `0x180039fb4`
- `0x180085bcc`
- `0x180085eec`
- `0x180085f88`
- `0x18008604c`
- `0x1800860a0`
- `0x1800861a4`
- `0x180086294`
- `0x180086834`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180086344`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180086344`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180086436`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180086566`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180086436`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180086566`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall GetMultiValueSetting(HKEY hKey, const unsigned __int16 *a2, struct ATL::CComVariant *a3)
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
  unsigned __int16 v20; // [rsp+78h] [rbp-88h] BYREF
  SAFEARRAY *v21; // [rsp+80h] [rbp-80h]
  __int128 v22; // [rsp+90h] [rbp-70h] BYREF
  __int64 v23; // [rsp+A0h] [rbp-60h]
  _WORD v24[12]; // [rsp+A8h] [rbp-58h] BYREF
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
    v7 = RegEnumValueW(hKey, v6, ValueName, &cchValueName, 0, &Type, 0, 0);
    if ( v7 )
      break;
    ATL::CComSafeArrayBound::`default constructor closure'((ATL::CComSafeArrayBound *)&v14);
    v14 = (SAFEARRAY *)2;
    ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(&psa, &v14);
    v24[0] = 0;
    ATL::CComVariant::operator=(v24, ValueName);
    v8 = ATL::CComSafeArray<tagVARIANT,12>::SetAt(&psa, 0, v24);
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
    v22 = 0;
    v23 = 0;
    LOWORD(v22) = 0;
    if ( v8 < 0 || (int)GetStoredValue(hKey, 0, ValueName, v9, (struct ATL::CComVariant *)&v22) < 0 )
      ATL::CComVariant::Clear((ATL::CComVariant *)&v22);
    v5 = ATL::CComSafeArray<tagVARIANT,12>::SetAt(&psa, 1, &v22);
    if ( v5 < 0 )
    {
      ATL::CComVariant::Clear((ATL::CComVariant *)&v22);
      ATL::CComVariant::Clear((ATL::CComVariant *)v24);
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
    ATL::CComVariant::Clear((ATL::CComVariant *)&v20);
    ++v6;
    ATL::CComVariant::Clear((ATL::CComVariant *)&v22);
    ATL::CComVariant::Clear((ATL::CComVariant *)v24);
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
    ATL::CComVariant::Clear(a3);
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
0x180086294  mov     [rsp-8+arg_8], rbx
0x180086299  push    rbp
0x18008629a  push    rdi
0x18008629b  push    r13
0x18008629d  push    r14
0x18008629f  push    r15
0x1800862a1  lea     rbp, [rsp-1E0h]
0x1800862a9  sub     rsp, 2E0h
0x1800862b0  mov     rax, cs:__security_cookie
0x1800862b7  xor     rax, rsp
0x1800862ba  mov     [rbp+200h+var_30], rax
0x1800862c1  mov     rdi, r8
0x1800862c4  mov     r15, rcx
0x1800862c7  xor     ebx, ebx
0x1800862c9  lea     rcx, [rsp+300h+var_290]; this
0x1800862ce  call    ??_FCComSafeArrayBound@ATL@@QEAAXXZ; ATL::CComSafeArrayBound::`default constructor closure'(void)
0x1800862d3  mov     [rsp+300h+var_290], rbx
0x1800862d8  lea     rdx, [rsp+300h+var_290]
0x1800862dd  lea     rcx, [rsp+300h+var_2A8]
0x1800862e2  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAYBOUND const *,uint)
0x1800862e7  nop
0x1800862e8  xor     r14d, r14d
0x1800862eb  lea     r13d, [rbx+3]
0x1800862ef  mov     [rsp+300h+Type], 0
0x1800862f7  xor     edx, edx; Val
0x1800862f9  mov     r8d, 208h; Size
0x1800862ff  lea     rcx, [rbp+200h+ValueName]; void *
0x180086303  call    memset_0
0x180086308  mov     [rsp+300h+cchValueName], 104h
0x180086310  mov     [rsp+300h+lpcbData], 0; lpcbData
0x180086319  mov     [rsp+300h+lpData], 0; lpData
0x180086322  lea     rax, [rsp+300h+Type]
0x180086327  mov     [rsp+300h+lpType], rax; lpType
0x18008632c  mov     [rsp+300h+lpReserved], 0; lpReserved
0x180086335  lea     r9, [rsp+300h+cchValueName]; lpcchValueName
0x18008633a  lea     r8, [rbp+200h+ValueName]; lpValueName
0x18008633e  mov     edx, r14d; dwIndex
0x180086341  mov     rcx, r15; hKey
0x180086344  call    cs:__imp_RegEnumValueW
0x18008634a  test    eax, eax
0x18008634c  jnz     loc_180086527
0x180086352  lea     rcx, [rsp+300h+var_2B8]; this
0x180086357  call    ??_FCComSafeArrayBound@ATL@@QEAAXXZ; ATL::CComSafeArrayBound::`default constructor closure'(void)
0x18008635c  mov     [rsp+300h+var_2B8], 2
0x180086365  lea     rdx, [rsp+300h+var_2B8]
0x18008636a  lea     rcx, [rsp+300h+psa]
0x18008636f  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAYBOUND const *,uint)
0x180086374  nop
0x180086375  xor     eax, eax
0x180086377  mov     [rbp+200h+var_258], ax
0x18008637b  lea     rdx, [rbp+200h+ValueName]
0x18008637f  lea     rcx, [rbp+200h+var_258]
0x180086383  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x180086388  nop
0x180086389  lea     r8, [rbp+200h+var_258]
0x18008638d  xor     edx, edx
0x18008638f  lea     rcx, [rsp+300h+psa]
0x180086394  call    ?SetAt@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::SetAt(long,tagVARIANT const &,int)
0x180086399  mov     edx, eax
0x18008639b  xor     r9d, r9d
0x18008639e  mov     ecx, [rsp+300h+Type]
0x1800863a2  sub     ecx, 1
0x1800863a5  jz      short loc_1800863BF
0x1800863a7  sub     ecx, r13d
0x1800863aa  jz      short loc_1800863B9
0x1800863ac  cmp     ecx, r13d
0x1800863af  jnz     short loc_1800863C5
0x1800863b1  mov     r9d, 2008h
0x1800863b7  jmp     short loc_1800863C5
0x1800863b9  movzx   r9d, r13w
0x1800863bd  jmp     short loc_1800863C5
0x1800863bf  mov     r9d, 8; unsigned __int16
0x1800863c5  xorps   xmm0, xmm0
0x1800863c8  xor     eax, eax
0x1800863ca  movups  [rbp+200h+var_270], xmm0
0x1800863ce  mov     [rbp+200h+var_260], rax
0x1800863d2  mov     word ptr [rbp+200h+var_270], ax
0x1800863d6  test    edx, edx
0x1800863d8  js      short loc_1800863F5
0x1800863da  lea     rax, [rbp+200h+var_270]
0x1800863de  mov     [rsp+300h+lpReserved], rax; struct ATL::CComVariant *
0x1800863e3  lea     r8, [rbp+200h+ValueName]; unsigned __int16 *
0x1800863e7  xor     edx, edx; lpSubKey
0x1800863e9  mov     rcx, r15; hKey
0x1800863ec  call    ?GetStoredValue@@YAJPEAUHKEY__@@PEBG1GAEAVCComVariant@ATL@@@Z; GetStoredValue(HKEY__ *,ushort const *,ushort const *,ushort,ATL::CComVariant &)
0x1800863f1  test    eax, eax
0x1800863f3  jns     short loc_1800863FE
0x1800863f5  lea     rcx, [rbp+200h+var_270]; this
0x1800863f9  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x1800863fe  lea     r8, [rbp+200h+var_270]
0x180086402  mov     edx, 1
0x180086407  lea     rcx, [rsp+300h+psa]
0x18008640c  call    ?SetAt@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::SetAt(long,tagVARIANT const &,int)
0x180086411  mov     ebx, eax
0x180086413  test    eax, eax
0x180086415  js      loc_1800864D4
0x18008641b  mov     [rsp+300h+ppsaOut], 0
0x180086424  cmp     [rsp+300h+psa], 0
0x18008642a  jz      short loc_180086473
0x18008642c  lea     rdx, [rsp+300h+ppsaOut]; ppsaOut
0x180086431  mov     rcx, [rsp+300h+psa]; psa
0x180086436  call    cs:__imp_SafeArrayCopy
0x18008643c  mov     ecx, eax
0x18008643e  test    eax, eax
0x180086440  js      short loc_1800864BC
0x180086442  cmp     [rsp+300h+ppsaOut], 0
0x180086448  jz      short loc_1800864BC
0x18008644a  lea     rdx, [rsp+300h+var_288]; unsigned __int16 *
0x18008644f  mov     rcx, [rsp+300h+psa]; struct tagSAFEARRAY *
0x180086454  call    ?AtlSafeArrayGetActualVartype@ATL@@YAJPEAUtagSAFEARRAY@@PEAG@Z; ATL::AtlSafeArrayGetActualVartype(tagSAFEARRAY *,ushort *)
0x180086459  mov     eax, 2000h
0x18008645e  or      [rsp+300h+var_288], ax
0x180086463  mov     eax, dword ptr [rsp+300h+ppsaOut]
0x180086467  mov     dword ptr [rbp+200h+var_280], eax
0x18008646a  mov     eax, dword ptr [rsp+300h+ppsaOut+4]
0x18008646e  mov     dword ptr [rbp+200h+var_280+4], eax
0x180086471  jmp     short loc_18008647A
0x180086473  xor     eax, eax
0x180086475  mov     [rsp+300h+var_288], ax
0x18008647a  lea     rdx, [rsp+300h+var_288]
0x18008647f  lea     rcx, [rsp+300h+var_2A8]
0x180086484  call    ?Add@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::Add(tagVARIANT const &,int)
0x180086489  nop
0x18008648a  lea     rcx, [rsp+300h+var_288]; this
0x18008648f  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x180086494  nop
0x180086495  inc     r14d
0x180086498  lea     rcx, [rbp+200h+var_270]; this
0x18008649c  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x1800864a1  nop
0x1800864a2  lea     rcx, [rbp+200h+var_258]; this
0x1800864a6  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x1800864ab  nop
0x1800864ac  lea     rcx, [rsp+300h+psa]
0x1800864b1  call    ?Destroy@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJXZ; ATL::CComSafeArray<tagVARIANT,12>::Destroy(void)
0x1800864b6  nop
0x1800864b7  jmp     loc_1800862EF
0x1800864bc  mov     eax, 0Ah
0x1800864c1  mov     [rsp+300h+var_288], ax
0x1800864c6  mov     dword ptr [rbp+200h+var_280], ecx
0x1800864c9  mov     ecx, 8007000Eh; int
0x1800864ce  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800864d4  lea     rcx, [rbp+200h+var_270]; this
0x1800864d8  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x1800864dd  nop
0x1800864de  lea     rcx, [rbp+200h+var_258]; this
0x1800864e2  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x1800864e7  nop
0x1800864e8  lea     rcx, [rsp+300h+psa]
0x1800864ed  call    ?Destroy@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJXZ; ATL::CComSafeArray<tagVARIANT,12>::Destroy(void)
0x1800864f2  nop
0x1800864f3  lea     rcx, [rsp+300h+var_2A8]
0x1800864f8  call    ?Destroy@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJXZ; ATL::CComSafeArray<tagVARIANT,12>::Destroy(void)
0x1800864fd  nop
0x1800864fe  mov     eax, ebx
0x180086500  mov     rcx, [rbp+200h+var_30]
0x180086507  xor     rcx, rsp; StackCookie
0x18008650a  call    __security_check_cookie
0x18008650f  mov     rbx, [rsp+300h+arg_8]
0x180086517  add     rsp, 2E0h
0x18008651e  pop     r15
0x180086520  pop     r14
0x180086522  pop     r13
0x180086524  pop     rdi
0x180086525  pop     rbp
0x180086526  retn
0x180086527  cmp     eax, 103h
0x18008652c  jz      short loc_18008653F
0x18008652e  test    eax, eax
0x180086530  jg      short loc_180086536
0x180086532  mov     ebx, eax
0x180086534  jmp     short loc_18008653F
0x180086536  movzx   ebx, ax
0x180086539  or      ebx, 80070000h
0x18008653f  test    ebx, ebx
0x180086541  js      short loc_1800864F3
0x180086543  mov     rcx, rdi; this
0x180086546  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x18008654b  mov     [rsp+300h+var_2B8], 0
0x180086554  cmp     [rsp+300h+var_2A8], 0
0x18008655a  jz      short loc_1800864F3
0x18008655c  lea     rdx, [rsp+300h+var_2B8]; ppsaOut
0x180086561  mov     rcx, [rsp+300h+var_2A8]; psa
0x180086566  call    cs:__imp_SafeArrayCopy
0x18008656c  test    eax, eax
0x18008656e  js      short loc_18008659B
0x180086570  cmp     [rsp+300h+var_2B8], 0
0x180086576  jz      short loc_18008659B
0x180086578  mov     rdx, rdi; unsigned __int16 *
0x18008657b  mov     rcx, [rsp+300h+var_2A8]; struct tagSAFEARRAY *
0x180086580  call    ?AtlSafeArrayGetActualVartype@ATL@@YAJPEAUtagSAFEARRAY@@PEAG@Z; ATL::AtlSafeArrayGetActualVartype(tagSAFEARRAY *,ushort *)
0x180086585  mov     eax, 2000h
0x18008658a  or      [rdi], ax
0x18008658d  mov     rax, [rsp+300h+var_2B8]
0x180086592  mov     [rdi+8], rax
0x180086596  jmp     loc_1800864F3
0x18008659b  mov     word ptr [rdi], 0Ah
0x1800865a0  mov     [rdi+8], eax
0x1800865a3  mov     ecx, 8007000Eh; int
0x1800865a8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
