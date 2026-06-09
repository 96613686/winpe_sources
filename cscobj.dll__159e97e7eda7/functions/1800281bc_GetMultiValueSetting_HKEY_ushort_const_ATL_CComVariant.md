# GetMultiValueSetting(HKEY__ *,ushort const *,ATL::CComVariant &)

- ea: `0x1800281bc`
- end: `0x180028416`
- name: `?GetMultiValueSetting@@YAJPEAUHKEY__@@PEBGAEAVCComVariant@ATL@@@Z`
- size: `602`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, struct ATL::CComVariant *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a5a0`

## callees

- `0x18000a5a0`
- `0x18000b7c0`
- `0x18000c174`
- `0x1800186c0`
- `0x18001c8c8`
- `0x18001ca10`
- `0x18001cb6c`
- `0x18001cbf0`
- `0x18001cda0`
- `0x18001d74c`
- `0x18001dec8`
- `0x1800281bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002826f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002826f`
- `OLEAUT32!__imp_VariantInit` at `0x1800282f2`
- `OLEAUT32!__imp_VariantInit` at `0x1800282f2`
- `OLEAUT32!__imp_VariantClear` at `0x180028322`
- `OLEAUT32!__imp_VariantClear` at `0x180028363`
- `OLEAUT32!__imp_VariantClear` at `0x180028371`
- `OLEAUT32!__imp_VariantClear` at `0x18002837c`
- `OLEAUT32!__imp_VariantClear` at `0x180028397`
- `OLEAUT32!__imp_VariantClear` at `0x1800283a2`
- `OLEAUT32!__imp_VariantClear` at `0x180028322`
- `OLEAUT32!__imp_VariantClear` at `0x180028363`
- `OLEAUT32!__imp_VariantClear` at `0x180028371`
- `OLEAUT32!__imp_VariantClear` at `0x18002837c`
- `OLEAUT32!__imp_VariantClear` at `0x180028397`
- `OLEAUT32!__imp_VariantClear` at `0x1800283a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetMultiValueSetting(HKEY hKey, const unsigned __int16 *a2, VARIANTARG *a3)
{
  int v5; // ebx
  DWORD v6; // edi
  LSTATUS v7; // eax
  HRESULT v8; // esi
  __int16 v9; // bx
  ATL::CComVariant *v10; // rax
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  struct tagSAFEARRAY *v13; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchValueName; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v15; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h] BYREF
  struct tagSAFEARRAY *v17; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG v19; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v20; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[264]; // [rsp+C0h] [rbp-40h] BYREF

  v5 = 0;
  ATL::CComSafeArrayBound::`default constructor closure'((ATL::CComSafeArrayBound *)&v15);
  v15 = 0;
  ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(&v17, &v15);
  v6 = 0;
  while ( 1 )
  {
    Type = 0;
    memset_0(ValueName, 0, 0x208u);
    cchValueName = 260;
    v7 = RegEnumValueW(hKey, v6, ValueName, &cchValueName, 0, &Type, 0, 0);
    if ( v7 )
      break;
    ATL::CComSafeArrayBound::`default constructor closure'((ATL::CComSafeArrayBound *)&v16);
    v16 = 2;
    ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(&v13, &v16);
    v19.vt = 0;
    ATL::CComVariant::operator=(&v19, ValueName);
    v8 = ATL::CComSafeArray<tagVARIANT,12>::SetAt((__int64)&v13, 0, &v19);
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
    if ( v8 < 0 || (int)GetStoredValue(hKey, 0, ValueName, v9, &pvarg) < 0 )
      VariantClear(&pvarg);
    v5 = ATL::CComSafeArray<tagVARIANT,12>::SetAt((__int64)&v13, 1, &pvarg);
    if ( v5 < 0 )
    {
      VariantClear(&pvarg);
      VariantClear(&v19);
      ATL::CComSafeArray<unsigned short *,8>::Destroy(&v13);
      goto LABEL_21;
    }
    v10 = ATL::CComVariant::CComVariant((ATL::CComVariant *)&v20, v13);
    ATL::CComSafeArray<tagVARIANT,12>::Add(&v17, v10);
    VariantClear(&v20);
    ++v6;
    VariantClear(&pvarg);
    VariantClear(&v19);
    ATL::CComSafeArray<unsigned short *,8>::Destroy(&v13);
  }
  if ( v7 != 259 )
  {
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    else
      v5 = v7;
  }
  if ( v5 >= 0 )
    ATL::CComVariant::operator=(a3, v17);
LABEL_21:
  ATL::CComSafeArray<unsigned short *,8>::Destroy(&v17);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800281bc  mov     [rsp-8+arg_8], rbx
0x1800281c1  mov     [rsp-8+arg_18], rsi
0x1800281c6  push    rbp
0x1800281c7  push    rdi
0x1800281c8  push    r13
0x1800281ca  push    r14
0x1800281cc  push    r15
0x1800281ce  lea     rbp, [rsp-1E0h]
0x1800281d6  sub     rsp, 2E0h
0x1800281dd  mov     rax, cs:__security_cookie
0x1800281e4  xor     rax, rsp
0x1800281e7  mov     [rbp+200h+var_30], rax
0x1800281ee  mov     r15, r8
0x1800281f1  mov     r14, rcx
0x1800281f4  xor     ebx, ebx
0x1800281f6  lea     rcx, [rsp+300h+var_2A8]; this
0x1800281fb  call    ??_FCComSafeArrayBound@ATL@@QEAAXXZ; ATL::CComSafeArrayBound::`default constructor closure'(void)
0x180028200  mov     [rsp+300h+var_2A8], rbx
0x180028205  lea     rdx, [rsp+300h+var_2A8]
0x18002820a  lea     rcx, [rsp+300h+var_298]
0x18002820f  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAYBOUND const *,uint)
0x180028214  nop
0x180028215  xor     edi, edi
0x180028217  lea     r13d, [rbx+3]
0x18002821b  mov     [rsp+300h+Type], 0
0x180028223  xor     edx, edx; Val
0x180028225  mov     r8d, 208h; Size
0x18002822b  lea     rcx, [rbp+200h+ValueName]; void *
0x18002822f  call    memset_0
0x180028234  mov     [rsp+300h+cchValueName], 104h
0x18002823c  mov     [rsp+300h+lpcbData], 0; lpcbData
0x180028245  mov     [rsp+300h+lpData], 0; lpData
0x18002824e  lea     rax, [rsp+300h+Type]
0x180028253  mov     [rsp+300h+lpType], rax; lpType
0x180028258  mov     [rsp+300h+lpReserved], 0; lpReserved
0x180028261  lea     r9, [rsp+300h+cchValueName]; lpcchValueName
0x180028266  lea     r8, [rbp+200h+ValueName]; lpValueName
0x18002826a  mov     edx, edi; dwIndex
0x18002826c  mov     rcx, r14; hKey
0x18002826f  call    cs:__imp_RegEnumValueW
0x180028275  test    eax, eax
0x180028277  jnz     loc_1800283B5
0x18002827d  lea     rcx, [rsp+300h+var_2A0]; this
0x180028282  call    ??_FCComSafeArrayBound@ATL@@QEAAXXZ; ATL::CComSafeArrayBound::`default constructor closure'(void)
0x180028287  mov     [rsp+300h+var_2A0], 2
0x180028290  lea     rdx, [rsp+300h+var_2A0]
0x180028295  lea     rcx, [rsp+300h+var_2B8]
0x18002829a  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAYBOUND const *,uint)
0x18002829f  nop
0x1800282a0  xor     eax, eax
0x1800282a2  mov     word ptr [rbp+200h+var_278], ax
0x1800282a6  lea     rdx, [rbp+200h+ValueName]
0x1800282aa  lea     rcx, [rbp+200h+var_278]
0x1800282ae  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x1800282b3  nop
0x1800282b4  lea     r8, [rbp+200h+var_278]
0x1800282b8  xor     edx, edx
0x1800282ba  lea     rcx, [rsp+300h+var_2B8]
0x1800282bf  call    ?SetAt@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::SetAt(long,tagVARIANT const &,int)
0x1800282c4  mov     esi, eax
0x1800282c6  xor     ebx, ebx
0x1800282c8  mov     ecx, [rsp+300h+Type]
0x1800282cc  sub     ecx, 1
0x1800282cf  jz      short loc_1800282E8
0x1800282d1  sub     ecx, r13d
0x1800282d4  jz      short loc_1800282E2
0x1800282d6  cmp     ecx, r13d
0x1800282d9  jnz     short loc_1800282ED
0x1800282db  mov     ebx, 2008h
0x1800282e0  jmp     short loc_1800282ED
0x1800282e2  movzx   ebx, r13w
0x1800282e6  jmp     short loc_1800282ED
0x1800282e8  mov     ebx, 8
0x1800282ed  lea     rcx, [rsp+300h+pvarg]; pvarg
0x1800282f2  call    cs:__imp_VariantInit
0x1800282f8  nop
0x1800282f9  test    esi, esi
0x1800282fb  js      short loc_18002831D
0x1800282fd  lea     rax, [rsp+300h+pvarg]
0x180028302  mov     [rsp+300h+lpReserved], rax; struct ATL::CComVariant *
0x180028307  movzx   r9d, bx; unsigned __int16
0x18002830b  lea     r8, [rbp+200h+ValueName]; unsigned __int16 *
0x18002830f  xor     edx, edx; lpSubKey
0x180028311  mov     rcx, r14; hKey
0x180028314  call    ?GetStoredValue@@YAJPEAUHKEY__@@PEBG1GAEAVCComVariant@ATL@@@Z; GetStoredValue(HKEY__ *,ushort const *,ushort const *,ushort,ATL::CComVariant &)
0x180028319  test    eax, eax
0x18002831b  jns     short loc_180028328
0x18002831d  lea     rcx, [rsp+300h+pvarg]; pvarg
0x180028322  call    cs:__imp_VariantClear
0x180028328  lea     r8, [rsp+300h+pvarg]
0x18002832d  mov     edx, 1
0x180028332  lea     rcx, [rsp+300h+var_2B8]
0x180028337  call    ?SetAt@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::SetAt(long,tagVARIANT const &,int)
0x18002833c  mov     ebx, eax
0x18002833e  test    eax, eax
0x180028340  js      short loc_180028392
0x180028342  mov     rdx, [rsp+300h+var_2B8]; struct tagSAFEARRAY *
0x180028347  lea     rcx, [rbp+200h+var_260]; this
0x18002834b  call    ??0CComVariant@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComVariant::CComVariant(tagSAFEARRAY const *)
0x180028350  nop
0x180028351  mov     rdx, rax
0x180028354  lea     rcx, [rsp+300h+var_298]
0x180028359  call    ?Add@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::Add(tagVARIANT const &,int)
0x18002835e  nop
0x18002835f  lea     rcx, [rbp+200h+var_260]; pvarg
0x180028363  call    cs:__imp_VariantClear
0x180028369  nop
0x18002836a  inc     edi
0x18002836c  lea     rcx, [rsp+300h+pvarg]; pvarg
0x180028371  call    cs:__imp_VariantClear
0x180028377  nop
0x180028378  lea     rcx, [rbp+200h+var_278]; pvarg
0x18002837c  call    cs:__imp_VariantClear
0x180028382  nop
0x180028383  lea     rcx, [rsp+300h+var_2B8]
0x180028388  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18002838d  jmp     loc_18002821B
0x180028392  lea     rcx, [rsp+300h+pvarg]; pvarg
0x180028397  call    cs:__imp_VariantClear
0x18002839d  nop
0x18002839e  lea     rcx, [rbp+200h+var_278]; pvarg
0x1800283a2  call    cs:__imp_VariantClear
0x1800283a8  nop
0x1800283a9  lea     rcx, [rsp+300h+var_2B8]
0x1800283ae  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x1800283b3  jmp     short loc_1800283DF
0x1800283b5  cmp     eax, 103h
0x1800283ba  jz      short loc_1800283CD
0x1800283bc  test    eax, eax
0x1800283be  jg      short loc_1800283C4
0x1800283c0  mov     ebx, eax
0x1800283c2  jmp     short loc_1800283CD
0x1800283c4  movzx   ebx, ax
0x1800283c7  or      ebx, 80070000h
0x1800283cd  test    ebx, ebx
0x1800283cf  js      short loc_1800283DF
0x1800283d1  mov     rdx, [rsp+300h+var_298]; struct tagSAFEARRAY *
0x1800283d6  mov     rcx, r15; unsigned __int16 *
0x1800283d9  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBUtagSAFEARRAY@@@Z; ATL::CComVariant::operator=(tagSAFEARRAY const *)
0x1800283de  nop
0x1800283df  lea     rcx, [rsp+300h+var_298]
0x1800283e4  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x1800283e9  mov     eax, ebx
0x1800283eb  mov     rcx, [rbp+200h+var_30]
0x1800283f2  xor     rcx, rsp; StackCookie
0x1800283f5  call    __security_check_cookie
0x1800283fa  lea     r11, [rsp+300h+var_20]
0x180028402  mov     rbx, [r11+38h]
0x180028406  mov     rsi, [r11+48h]
0x18002840a  mov     rsp, r11
0x18002840d  pop     r15
0x18002840f  pop     r14
0x180028411  pop     r13
0x180028413  pop     rdi
0x180028414  pop     rbp
0x180028415  retn
```
