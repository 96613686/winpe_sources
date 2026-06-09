# CUiccHandler2::RemoveLogonTriggerFromCellularTask(void)

- ea: `0x1800317c4`
- end: `0x180031d82`
- name: `?RemoveLogonTriggerFromCellularTask@CUiccHandler2@@KAXXZ`
- size: `1470`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180031100`

## callees

- `0x18000108c`
- `0x180012d80`
- `0x180012da0`
- `0x1800317c4`
- `0x180032d30`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003180e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003180e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800318a2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800318a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800318ed`
- `OLEAUT32!__imp_SysFreeString` at `0x180031aae`
- `OLEAUT32!__imp_SysFreeString` at `0x1800318ed`
- `OLEAUT32!__imp_SysFreeString` at `0x180031aae`
- `OLEAUT32!__imp_VariantInit` at `0x180031827`
- `OLEAUT32!__imp_VariantInit` at `0x180031b30`
- `OLEAUT32!__imp_VariantInit` at `0x180031827`
- `OLEAUT32!__imp_VariantInit` at `0x180031b30`
- `OLEAUT32!__imp_VariantClear` at `0x180031af1`
- `OLEAUT32!__imp_VariantClear` at `0x180031c61`
- `OLEAUT32!__imp_VariantClear` at `0x180031af1`
- `OLEAUT32!__imp_VariantClear` at `0x180031c61`

## string_xrefs

- `0x180031c9e`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void CUiccHandler2::RemoveLogonTriggerFromCellularTask(void)
{
  HRESULT v0; // eax
  int v1; // eax
  LPVOID v2; // rdi
  __int64 v3; // rsi
  BSTR v4; // rax
  const char *v5; // r9
  OLECHAR *v6; // rbx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 *v19; // rcx
  LPVOID v20; // rcx
  int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  BSTR v24; // rcx
  __int64 v25; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v29; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+68h] [rbp-98h] BYREF
  __int64 v32; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v33; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v34; // [rsp+80h] [rbp-80h] BYREF
  BSTR v35; // [rsp+88h] [rbp-78h]
  int v36; // [rsp+90h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-68h] BYREF
  VARIANTARG v38; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG v40; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG v41; // [rsp+100h] [rbp+0h] BYREF
  VARIANTARG v42; // [rsp+120h] [rbp+20h] BYREF
  int *v43; // [rsp+140h] [rbp+40h]
  __int64 v44; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v28 = 0;
  v34 = 0;
  v0 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v34);
  if ( v0 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x264,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)(unsigned int)v0,
      ppv);
  VariantInit(&pvarg);
  v38 = pvarg;
  v40 = pvarg;
  v41 = pvarg;
  v42 = pvarg;
  v1 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v34 + 80LL))(
         v34,
         &v42,
         &v41,
         &v40);
  if ( v1 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x266,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)(unsigned int)v1,
      (int)&v38);
  v33 = 0;
  v2 = v34;
  v3 = *(_QWORD *)v34;
  v4 = SysAllocString(L"\\Microsoft\\Windows\\Management\\Provisioning");
  v6 = v4;
  v35 = v4;
  v28 = 1;
  if ( !v4 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v5);
  v7 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 **))(v3 + 56))(v2, v4, &v33);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x269,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)(unsigned int)v7,
      (int)&v38);
  SysFreeString(v6);
  v31 = 0;
  wil::make_bstr(&bstrString, L"Cellular");
  v8 = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int64 *))(*v33 + 104))(v33, bstrString, &v31);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x26D,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)(unsigned int)v8,
      (int)&v38);
  v32 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 152LL))(v31, &v32);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x270,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)(unsigned int)v9,
      (int)&v38);
  v30 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 72LL))(v32, &v30);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x273,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)(unsigned int)v10,
      (int)&v38);
  v27 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v30 + 56LL))(v30, &v27);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x276,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)(unsigned int)v11,
      (int)&v38);
  v12 = 1;
  if ( v27 >= 1 )
  {
    while ( 1 )
    {
      v29 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v30 + 64LL))(v30, v12, &v29);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x27B,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
          (const char *)(unsigned int)v13,
          (int)&v38);
      v28 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 56LL))(v29, &v28);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x27E,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
          (const char *)(unsigned int)v14,
          (int)&v38);
      if ( v28 == 9 )
        break;
      v15 = v29;
      if ( v29 )
      {
        v29 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      if ( (int)++v12 > v27 )
        goto LABEL_16;
    }
    VariantInit(&v38);
    v38.vt = 3;
    v38.lVal = v12;
    v42 = v38;
    v21 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v30 + 88LL))(v30, &v42);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x285,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
        (const char *)(unsigned int)v21,
        (int)&v38);
    v35 = 0;
    v22 = *v33;
    v42 = pvarg;
    v41 = pvarg;
    v40 = pvarg;
    v23 = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int64, __int64))(v22 + 136))(v33, bstrString, v32, 4);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x289,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
        (const char *)(unsigned int)v23,
        (int)&v40);
    if ( (unsigned int)dword_180052170 > 4 )
    {
      v36 = v27;
      v43 = &v36;
      v44 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180052170, word_1800498F2, 0, 0, 3, &v42);
    }
    v24 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v24 + 16LL))(v24);
    }
    VariantClear(&v38);
    v25 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
  }
LABEL_16:
  v16 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  v17 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  if ( bstrString )
    SysFreeString(bstrString);
  v18 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v19 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
  }
  VariantClear(&pvarg);
  v20 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
  }
}

```

## disassembly

```asm
0x1800317c4  push    rbp
0x1800317c6  push    rbx
0x1800317c7  push    rsi
0x1800317c8  push    rdi
0x1800317c9  push    r14
0x1800317cb  lea     rbp, [rsp-60h]
0x1800317d0  sub     rsp, 160h
0x1800317d7  mov     rax, cs:__security_cookie
0x1800317de  xor     rax, rsp
0x1800317e1  mov     [rbp+80h+var_30], rax
0x1800317e5  xor     r14d, r14d
0x1800317e8  mov     [rsp+180h+var_12C], r14d
0x1800317ed  mov     [rbp+80h+var_100], r14
0x1800317f1  lea     rax, [rbp+80h+var_100]
0x1800317f5  mov     [rsp+180h+ppv], rax; int
0x1800317fa  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180031801  xor     edx, edx; pUnkOuter
0x180031803  lea     r8d, [r14+1]; dwClsContext
0x180031807  lea     rcx, CLSID_TaskScheduler; rclsid
0x18003180e  call    cs:__imp_CoCreateInstance
0x180031814  mov     rcx, [rbp+88h]; this
0x18003181b  test    eax, eax
0x18003181d  js      loc_180031CB0
0x180031823  lea     rcx, [rbp+80h+pvarg]; pvarg
0x180031827  call    cs:__imp_VariantInit
0x18003182d  nop
0x18003182e  mov     rcx, [rbp+80h+var_100]
0x180031832  movups  xmm1, xmmword ptr [rbp+80h+pvarg]
0x180031836  movsd   xmm0, qword ptr [rbp+80h+pvarg+10h]
0x18003183b  movaps  xmmword ptr [rbp+80h+var_E0], xmm1
0x18003183f  movsd   qword ptr [rbp+80h+var_E0+10h], xmm0
0x180031844  movaps  xmmword ptr [rbp+80h+var_A0], xmm1
0x180031848  movsd   [rbp+80h+var_90], xmm0
0x18003184d  movaps  [rbp+80h+var_80], xmm1
0x180031851  movsd   [rbp+80h+var_70], xmm0
0x180031856  movaps  [rbp+80h+var_60], xmm1
0x18003185a  movsd   [rbp+80h+var_50], xmm0
0x18003185f  mov     rax, [rcx]
0x180031862  lea     rdx, [rbp+80h+var_E0]
0x180031866  mov     [rsp+180h+ppv], rdx; int
0x18003186b  lea     r9, [rbp+80h+var_A0]
0x18003186f  lea     r8, [rbp+80h+var_80]
0x180031873  lea     rdx, [rbp+80h+var_60]
0x180031877  mov     rax, [rax+50h]
0x18003187b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031880  mov     rcx, [rbp+88h]; this
0x180031887  test    eax, eax
0x180031889  js      loc_180031CC5
0x18003188f  mov     [rsp+180h+var_108], r14
0x180031894  mov     rdi, [rbp+80h+var_100]
0x180031898  mov     rsi, [rdi]
0x18003189b  lea     rcx, psz; "\\Microsoft\\Windows\\Management\\Provi"...
0x1800318a2  call    cs:__imp_SysAllocString
0x1800318a8  mov     rbx, rax
0x1800318ab  mov     [rbp+80h+var_F8], rax
0x1800318af  mov     [rsp+180h+var_12C], 1
0x1800318b7  mov     rcx, [rbp+88h]; this
0x1800318be  test    rax, rax
0x1800318c1  jz      loc_180031C9E
0x1800318c7  lea     r8, [rsp+180h+var_108]
0x1800318cc  mov     rdx, rax
0x1800318cf  mov     rcx, rdi
0x1800318d2  mov     rax, [rsi+38h]
0x1800318d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318db  mov     rcx, [rbp+88h]; this
0x1800318e2  test    eax, eax
0x1800318e4  js      loc_180031CDA
0x1800318ea  mov     rcx, rbx; bstrString
0x1800318ed  call    cs:__imp_SysFreeString
0x1800318f3  mov     [rsp+180h+var_118], r14
0x1800318f8  lea     rdx, aCellular; "Cellular"
0x1800318ff  lea     rcx, [rbp+80h+bstrString]
0x180031903  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180031908  nop
0x180031909  mov     rbx, [rsp+180h+var_108]
0x18003190e  mov     rax, [rbx]
0x180031911  mov     rdi, [rax+68h]
0x180031915  mov     rcx, [rsp+180h+var_118]
0x18003191a  test    rcx, rcx
0x18003191d  jz      short loc_180031931
0x18003191f  mov     [rsp+180h+var_118], r14
0x180031924  mov     rdx, [rcx]
0x180031927  mov     rax, [rdx+10h]
0x18003192b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031930  nop
0x180031931  lea     r8, [rsp+180h+var_118]
0x180031936  mov     rdx, [rbp+80h+bstrString]
0x18003193a  mov     rcx, rbx
0x18003193d  mov     rax, rdi
0x180031940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031945  mov     rcx, [rbp+88h]; this
0x18003194c  test    eax, eax
0x18003194e  js      loc_180031CEF
0x180031954  mov     [rsp+180h+var_110], r14
0x180031959  mov     rcx, [rsp+180h+var_118]
0x18003195e  mov     rax, [rcx]
0x180031961  lea     rdx, [rsp+180h+var_110]
0x180031966  mov     rax, [rax+98h]
0x18003196d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031972  mov     rcx, [rbp+88h]; this
0x180031979  test    eax, eax
0x18003197b  js      loc_180031D04
0x180031981  mov     [rsp+180h+var_120], r14
0x180031986  mov     rcx, [rsp+180h+var_110]
0x18003198b  mov     rax, [rcx]
0x18003198e  lea     rdx, [rsp+180h+var_120]
0x180031993  mov     rax, [rax+48h]
0x180031997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003199c  mov     rcx, [rbp+88h]; this
0x1800319a3  test    eax, eax
0x1800319a5  js      loc_180031D19
0x1800319ab  mov     [rsp+180h+var_130], r14d
0x1800319b0  mov     rcx, [rsp+180h+var_120]
0x1800319b5  mov     rax, [rcx]
0x1800319b8  lea     rdx, [rsp+180h+var_130]
0x1800319bd  mov     rax, [rax+38h]
0x1800319c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800319c6  mov     rcx, [rbp+88h]; this
0x1800319cd  test    eax, eax
0x1800319cf  js      loc_180031D2E
0x1800319d5  mov     ebx, 1
0x1800319da  cmp     [rsp+180h+var_130], ebx
0x1800319de  jl      loc_180031A6D
0x1800319e4  mov     [rsp+180h+var_128], r14
0x1800319e9  mov     rcx, [rsp+180h+var_120]
0x1800319ee  mov     rax, [rcx]
0x1800319f1  lea     r8, [rsp+180h+var_128]
0x1800319f6  mov     edx, ebx
0x1800319f8  mov     rax, [rax+40h]
0x1800319fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a01  mov     rcx, [rbp+88h]; this
0x180031a08  test    eax, eax
0x180031a0a  js      loc_180031C89
0x180031a10  mov     [rsp+180h+var_12C], r14d
0x180031a15  mov     rcx, [rsp+180h+var_128]
0x180031a1a  mov     rax, [rcx]
0x180031a1d  lea     rdx, [rsp+180h+var_12C]
0x180031a22  mov     rax, [rax+38h]
0x180031a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a2b  mov     rcx, [rbp+88h]; this
0x180031a32  test    eax, eax
0x180031a34  js      loc_180031D6D
0x180031a3a  cmp     [rsp+180h+var_12C], 9
0x180031a3f  jz      loc_180031B2C
0x180031a45  mov     rcx, [rsp+180h+var_128]
0x180031a4a  test    rcx, rcx
0x180031a4d  jz      short loc_180031A61
0x180031a4f  mov     [rsp+180h+var_128], r14
0x180031a54  mov     rax, [rcx]
0x180031a57  mov     rax, [rax+10h]
0x180031a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a60  nop
0x180031a61  inc     ebx
0x180031a63  cmp     ebx, [rsp+180h+var_130]
0x180031a67  jle     loc_1800319E4
0x180031a6d  mov     rcx, [rsp+180h+var_120]
0x180031a72  test    rcx, rcx
0x180031a75  jz      short loc_180031A89
0x180031a77  mov     [rsp+180h+var_120], r14
0x180031a7c  mov     rax, [rcx]
0x180031a7f  mov     rax, [rax+10h]
0x180031a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a88  nop
0x180031a89  mov     rcx, [rsp+180h+var_110]
0x180031a8e  test    rcx, rcx
0x180031a91  jz      short loc_180031AA5
0x180031a93  mov     [rsp+180h+var_110], r14
0x180031a98  mov     rax, [rcx]
0x180031a9b  mov     rax, [rax+10h]
0x180031a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031aa4  nop
0x180031aa5  mov     rcx, [rbp+80h+bstrString]; bstrString
0x180031aa9  test    rcx, rcx
0x180031aac  jz      short loc_180031AB5
0x180031aae  call    cs:__imp_SysFreeString
0x180031ab4  nop
0x180031ab5  mov     rcx, [rsp+180h+var_118]
0x180031aba  test    rcx, rcx
0x180031abd  jz      short loc_180031AD1
0x180031abf  mov     [rsp+180h+var_118], r14
0x180031ac4  mov     rax, [rcx]
0x180031ac7  mov     rax, [rax+10h]
0x180031acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ad0  nop
0x180031ad1  mov     rcx, [rsp+180h+var_108]
0x180031ad6  test    rcx, rcx
0x180031ad9  jz      short loc_180031AED
0x180031adb  mov     [rsp+180h+var_108], r14
0x180031ae0  mov     rax, [rcx]
0x180031ae3  mov     rax, [rax+10h]
0x180031ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031aec  nop
0x180031aed  lea     rcx, [rbp+80h+pvarg]; pvarg
0x180031af1  call    cs:__imp_VariantClear
0x180031af7  nop
0x180031af8  mov     rcx, [rbp+80h+var_100]
0x180031afc  test    rcx, rcx
0x180031aff  jz      short loc_180031B12
0x180031b01  mov     [rbp+80h+var_100], r14
0x180031b05  mov     rax, [rcx]
0x180031b08  mov     rax, [rax+10h]
0x180031b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b11  nop
0x180031b12  mov     rcx, [rbp+80h+var_30]
0x180031b16  xor     rcx, rsp; StackCookie
0x180031b19  call    __security_check_cookie
0x180031b1e  add     rsp, 160h
0x180031b25  pop     r14
0x180031b27  pop     rdi
0x180031b28  pop     rsi
0x180031b29  pop     rbx
0x180031b2a  pop     rbp
0x180031b2b  retn
0x180031b2c  lea     rcx, [rbp+80h+var_E0]; pvarg
0x180031b30  call    cs:__imp_VariantInit
0x180031b36  nop
0x180031b37  mov     edi, 3
0x180031b3c  mov     word ptr [rbp+80h+var_E0], di
0x180031b40  mov     dword ptr [rbp+80h+var_E0+8], ebx
0x180031b43  mov     rcx, [rsp+180h+var_120]
0x180031b48  movups  xmm0, xmmword ptr [rbp+80h+var_E0]
0x180031b4c  movaps  [rbp+80h+var_60], xmm0
0x180031b50  movsd   xmm1, qword ptr [rbp+80h+var_E0+10h]
0x180031b55  movsd   [rbp+80h+var_50], xmm1
0x180031b5a  mov     rax, [rcx]
0x180031b5d  lea     rdx, [rbp+80h+var_60]
0x180031b61  mov     rax, [rax+58h]
0x180031b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b6a  mov     rcx, [rbp+88h]; this
0x180031b71  test    eax, eax
0x180031b73  js      loc_180031D43
0x180031b79  mov     [rbp+80h+var_F8], r14
0x180031b7d  mov     rcx, [rsp+180h+var_108]
0x180031b82  mov     rax, [rcx]
0x180031b85  movups  xmm1, xmmword ptr [rbp+80h+pvarg]
0x180031b89  movsd   xmm0, qword ptr [rbp+80h+pvarg+10h]
0x180031b8e  movaps  [rbp+80h+var_60], xmm1
0x180031b92  movsd   [rbp+80h+var_50], xmm0
0x180031b97  movaps  [rbp+80h+var_80], xmm1
0x180031b9b  movsd   [rbp+80h+var_70], xmm0
0x180031ba0  movaps  xmmword ptr [rbp+80h+var_A0], xmm1
0x180031ba4  movsd   [rbp+80h+var_90], xmm0
0x180031ba9  lea     rdx, [rbp+80h+var_F8]
0x180031bad  mov     [rsp+180h+var_140], rdx
0x180031bb2  lea     rdx, [rbp+80h+var_60]
0x180031bb6  mov     [rsp+180h+var_148], rdx
0x180031bbb  mov     [rsp+180h+var_150], 5
0x180031bc3  lea     rdx, [rbp+80h+var_80]
0x180031bc7  mov     [rsp+180h+var_158], rdx
0x180031bcc  lea     rdx, [rbp+80h+var_A0]
0x180031bd0  mov     [rsp+180h+ppv], rdx; int
0x180031bd5  lea     ebx, [rdi+1]
0x180031bd8  mov     r9d, ebx
0x180031bdb  mov     r8, [rsp+180h+var_110]
0x180031be0  mov     rdx, [rbp+80h+bstrString]
0x180031be4  mov     rax, [rax+88h]
0x180031beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031bf0  mov     rcx, [rbp+88h]; this
0x180031bf7  test    eax, eax
0x180031bf9  js      loc_180031D58
0x180031bff  mov     eax, cs:dword_180052170
0x180031c05  cmp     eax, ebx
0x180031c07  jbe     short loc_180031C43
0x180031c09  mov     eax, [rsp+180h+var_130]
0x180031c0d  mov     [rbp+80h+var_F0], eax
0x180031c10  lea     rax, [rbp+80h+var_F0]
0x180031c14  mov     [rbp+80h+var_40], rax
0x180031c18  mov     [rbp+80h+var_38], rbx
0x180031c1c  lea     rax, [rbp+80h+var_60]
0x180031c20  mov     [rsp+180h+var_158], rax
0x180031c25  mov     dword ptr [rsp+180h+ppv], edi
0x180031c29  xor     r9d, r9d
0x180031c2c  xor     r8d, r8d
0x180031c2f  lea     rdx, word_1800498F2
0x180031c36  lea     rcx, dword_180052170
0x180031c3d  call    _tlgWriteTransfer_EventWriteTransfer
0x180031c42  nop
0x180031c43  mov     rcx, [rbp+80h+var_F8]
0x180031c47  test    rcx, rcx
0x180031c4a  jz      short loc_180031C5D
0x180031c4c  mov     [rbp+80h+var_F8], r14
0x180031c50  mov     rax, [rcx]
0x180031c53  mov     rax, [rax+10h]
0x180031c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c5c  nop
0x180031c5d  lea     rcx, [rbp+80h+var_E0]; pvarg
0x180031c61  call    cs:__imp_VariantClear
0x180031c67  nop
0x180031c68  mov     rcx, [rsp+180h+var_128]
0x180031c6d  test    rcx, rcx
0x180031c70  jz      short loc_180031C84
0x180031c72  mov     [rsp+180h+var_128], r14
0x180031c77  mov     rax, [rcx]
0x180031c7a  mov     rax, [rax+10h]
0x180031c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c83  nop
0x180031c84  jmp     loc_180031A6D
0x180031c89  mov     r9d, eax; char *
0x180031c8c  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180031c93  mov     edx, 27Bh; void *
  ... truncated ...
```
