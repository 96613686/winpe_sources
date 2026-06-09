# CUiccHandler2::AddLogonTriggerToCellularTask(void)

- ea: `0x18002cec4`
- end: `0x18002d46e`
- name: `?AddLogonTriggerToCellularTask@CUiccHandler2@@KAXXZ`
- size: `1450`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180031410`

## callees

- `0x18000108c`
- `0x180012d80`
- `0x180012da0`
- `0x18002cec4`
- `0x180032d30`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002cf0e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002cf0e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cfa1`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cfa1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002cfeb`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d2e1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002cfeb`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d2e1`
- `OLEAUT32!__imp_VariantInit` at `0x18002cf27`
- `OLEAUT32!__imp_VariantInit` at `0x18002cf27`
- `OLEAUT32!__imp_VariantClear` at `0x18002d322`
- `OLEAUT32!__imp_VariantClear` at `0x18002d322`

## string_xrefs

- `0x18002d38a`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void CUiccHandler2::AddLogonTriggerToCellularTask(void)
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
  OLECHAR *v15; // rcx
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  OLECHAR *v19; // rcx
  BSTR v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 *v24; // rcx
  LPVOID v25; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR *v28; // [rsp+58h] [rbp-A8h] BYREF
  int v29; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h] BYREF
  __int64 v31; // [rsp+70h] [rbp-90h] BYREF
  __int64 v32; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v33; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v34; // [rsp+88h] [rbp-78h] BYREF
  BSTR v35; // [rsp+90h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-68h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG v38; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG v39; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG v40; // [rsp+100h] [rbp+0h] BYREF
  VARIANTARG v41; // [rsp+120h] [rbp+20h] BYREF
  int *v42; // [rsp+140h] [rbp+40h]
  __int64 v43; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v27 = 0;
  v34 = 0;
  v0 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v34);
  if ( v0 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22E,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)(unsigned int)v0,
      ppv);
  VariantInit(&pvarg);
  v40 = pvarg;
  v38 = pvarg;
  v39 = pvarg;
  v41 = pvarg;
  v1 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v34 + 80LL))(
         v34,
         &v41,
         &v39,
         &v38);
  if ( v1 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x230,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)(unsigned int)v1,
      (int)&v40);
  v33 = 0;
  v2 = v34;
  v3 = *(_QWORD *)v34;
  v4 = SysAllocString(L"\\Microsoft\\Windows\\Management\\Provisioning");
  v6 = v4;
  v35 = v4;
  v27 = 1;
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
      (void *)0x233,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)(unsigned int)v7,
      (int)&v40);
  SysFreeString(v6);
  v31 = 0;
  wil::make_bstr(&bstrString, L"Cellular");
  v8 = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int64 *))(*v33 + 104))(v33, bstrString, &v31);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x237,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)(unsigned int)v8,
      (int)&v40);
  v32 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 152LL))(v31, &v32);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23A,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)(unsigned int)v9,
      (int)&v40);
  v30 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 72LL))(v32, &v30);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23D,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)(unsigned int)v10,
      (int)&v40);
  v29 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v30 + 56LL))(v30, &v29);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x240,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)(unsigned int)v11,
      (int)&v40);
  v12 = 1;
  if ( v29 < 1 )
  {
LABEL_16:
    v35 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, __int64, BSTR *))(*(_QWORD *)v30 + 80LL))(v30, 9, &v35);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x255,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
        (const char *)(unsigned int)v16,
        (int)&v40);
    v28 = 0;
    v17 = *v33;
    v41 = pvarg;
    v39 = pvarg;
    v38 = pvarg;
    v18 = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int64, __int64))(v17 + 136))(v33, bstrString, v32, 4);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x259,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
        (const char *)(unsigned int)v18,
        (int)&v38);
    if ( (unsigned int)dword_180052170 > 4 )
    {
      v27 = v29;
      v42 = &v27;
      v43 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180052170, &unk_180049938, 0, 0, 3, &v41);
    }
    v19 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v35;
    if ( v35 )
    {
      v35 = 0;
LABEL_24:
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v20 + 16LL))(v20);
    }
  }
  else
  {
    while ( 1 )
    {
      v28 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, OLECHAR **))(*(_QWORD *)v30 + 64LL))(v30, v12, &v28);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x246,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
          (const char *)(unsigned int)v13,
          (int)&v40);
      v27 = 0;
      v14 = (*(__int64 (__fastcall **)(OLECHAR *, int *))(*(_QWORD *)v28 + 56LL))(v28, &v27);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x249,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
          (const char *)(unsigned int)v14,
          (int)&v40);
      if ( v27 == 9 )
        break;
      v15 = v28;
      if ( v28 )
      {
        v28 = 0;
        (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v15 + 16LL))(v15);
      }
      if ( (int)++v12 > v29 )
        goto LABEL_16;
    }
    v20 = v28;
    if ( v28 )
    {
      v28 = 0;
      goto LABEL_24;
    }
  }
  v21 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v22 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  if ( bstrString )
    SysFreeString(bstrString);
  v23 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64 *))(*v24 + 16))(v24);
  }
  VariantClear(&pvarg);
  v25 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v25 + 16LL))(v25);
  }
}

```

## disassembly

```asm
0x18002cec4  push    rbp
0x18002cec6  push    rbx
0x18002cec7  push    rsi
0x18002cec8  push    rdi
0x18002cec9  push    r14
0x18002cecb  lea     rbp, [rsp-60h]
0x18002ced0  sub     rsp, 160h
0x18002ced7  mov     rax, cs:__security_cookie
0x18002cede  xor     rax, rsp
0x18002cee1  mov     [rbp+80h+var_30], rax
0x18002cee5  xor     r14d, r14d
0x18002cee8  mov     [rsp+180h+var_130], r14d
0x18002ceed  mov     [rbp+80h+var_F8], r14
0x18002cef1  lea     rax, [rbp+80h+var_F8]
0x18002cef5  mov     [rsp+180h+ppv], rax; int
0x18002cefa  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18002cf01  xor     edx, edx; pUnkOuter
0x18002cf03  lea     r8d, [r14+1]; dwClsContext
0x18002cf07  lea     rcx, CLSID_TaskScheduler; rclsid
0x18002cf0e  call    cs:__imp_CoCreateInstance
0x18002cf14  mov     rcx, [rbp+88h]; this
0x18002cf1b  test    eax, eax
0x18002cf1d  js      loc_18002D39C
0x18002cf23  lea     rcx, [rbp+80h+pvarg]; pvarg
0x18002cf27  call    cs:__imp_VariantInit
0x18002cf2d  nop
0x18002cf2e  mov     rcx, [rbp+80h+var_F8]
0x18002cf32  movups  xmm1, xmmword ptr [rbp+80h+pvarg]
0x18002cf36  movsd   xmm0, qword ptr [rbp+80h+pvarg+10h]
0x18002cf3b  movaps  xmmword ptr [rbp+80h+var_80], xmm1
0x18002cf3f  movsd   [rbp+80h+var_70], xmm0
0x18002cf44  movaps  xmmword ptr [rbp+80h+var_C0], xmm1
0x18002cf48  movsd   [rbp+80h+var_B0], xmm0
0x18002cf4d  movaps  [rbp+80h+var_A0], xmm1
0x18002cf51  movsd   [rbp+80h+var_90], xmm0
0x18002cf56  movaps  [rbp+80h+var_60], xmm1
0x18002cf5a  movsd   [rbp+80h+var_50], xmm0
0x18002cf5f  mov     rax, [rcx]
0x18002cf62  lea     rdx, [rbp+80h+var_80]
0x18002cf66  mov     [rsp+180h+ppv], rdx; int
0x18002cf6b  lea     r9, [rbp+80h+var_C0]
0x18002cf6f  lea     r8, [rbp+80h+var_A0]
0x18002cf73  lea     rdx, [rbp+80h+var_60]
0x18002cf77  mov     rax, [rax+50h]
0x18002cf7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf80  mov     rcx, [rbp+88h]; this
0x18002cf87  test    eax, eax
0x18002cf89  js      loc_18002D3B1
0x18002cf8f  mov     [rbp+80h+var_100], r14
0x18002cf93  mov     rdi, [rbp+80h+var_F8]
0x18002cf97  mov     rsi, [rdi]
0x18002cf9a  lea     rcx, psz; "\\Microsoft\\Windows\\Management\\Provi"...
0x18002cfa1  call    cs:__imp_SysAllocString
0x18002cfa7  mov     rbx, rax
0x18002cfaa  mov     [rbp+80h+var_F0], rax
0x18002cfae  mov     [rsp+180h+var_130], 1
0x18002cfb6  mov     rcx, [rbp+88h]; this
0x18002cfbd  test    rax, rax
0x18002cfc0  jz      loc_18002D38A
0x18002cfc6  lea     r8, [rbp+80h+var_100]
0x18002cfca  mov     rdx, rax
0x18002cfcd  mov     rcx, rdi
0x18002cfd0  mov     rax, [rsi+38h]
0x18002cfd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cfd9  mov     rcx, [rbp+88h]; this
0x18002cfe0  test    eax, eax
0x18002cfe2  js      loc_18002D3C6
0x18002cfe8  mov     rcx, rbx; bstrString
0x18002cfeb  call    cs:__imp_SysFreeString
0x18002cff1  mov     [rsp+180h+var_110], r14
0x18002cff6  lea     rdx, aCellular; "Cellular"
0x18002cffd  lea     rcx, [rbp+80h+bstrString]
0x18002d001  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18002d006  nop
0x18002d007  mov     rbx, [rbp+80h+var_100]
0x18002d00b  mov     rax, [rbx]
0x18002d00e  mov     rdi, [rax+68h]
0x18002d012  mov     rcx, [rsp+180h+var_110]
0x18002d017  test    rcx, rcx
0x18002d01a  jz      short loc_18002D02E
0x18002d01c  mov     [rsp+180h+var_110], r14
0x18002d021  mov     rdx, [rcx]
0x18002d024  mov     rax, [rdx+10h]
0x18002d028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d02d  nop
0x18002d02e  lea     r8, [rsp+180h+var_110]
0x18002d033  mov     rdx, [rbp+80h+bstrString]
0x18002d037  mov     rcx, rbx
0x18002d03a  mov     rax, rdi
0x18002d03d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d042  mov     rcx, [rbp+88h]; this
0x18002d049  test    eax, eax
0x18002d04b  js      loc_18002D3DB
0x18002d051  mov     [rsp+180h+var_108], r14
0x18002d056  mov     rcx, [rsp+180h+var_110]
0x18002d05b  mov     rax, [rcx]
0x18002d05e  lea     rdx, [rsp+180h+var_108]
0x18002d063  mov     rax, [rax+98h]
0x18002d06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d06f  mov     rcx, [rbp+88h]; this
0x18002d076  test    eax, eax
0x18002d078  js      loc_18002D3F0
0x18002d07e  mov     [rsp+180h+var_118], r14
0x18002d083  mov     rcx, [rsp+180h+var_108]
0x18002d088  mov     rax, [rcx]
0x18002d08b  lea     rdx, [rsp+180h+var_118]
0x18002d090  mov     rax, [rax+48h]
0x18002d094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d099  mov     rcx, [rbp+88h]; this
0x18002d0a0  test    eax, eax
0x18002d0a2  js      loc_18002D405
0x18002d0a8  mov     [rsp+180h+var_120], r14d
0x18002d0ad  mov     rcx, [rsp+180h+var_118]
0x18002d0b2  mov     rax, [rcx]
0x18002d0b5  lea     rdx, [rsp+180h+var_120]
0x18002d0ba  mov     rax, [rax+38h]
0x18002d0be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0c3  mov     rcx, [rbp+88h]; this
0x18002d0ca  test    eax, eax
0x18002d0cc  js      loc_18002D41A
0x18002d0d2  mov     ebx, 1
0x18002d0d7  cmp     [rsp+180h+var_120], ebx
0x18002d0db  jl      loc_18002D16A
0x18002d0e1  mov     [rsp+180h+var_128], r14
0x18002d0e6  mov     rcx, [rsp+180h+var_118]
0x18002d0eb  mov     rax, [rcx]
0x18002d0ee  lea     r8, [rsp+180h+var_128]
0x18002d0f3  mov     edx, ebx
0x18002d0f5  mov     rax, [rax+40h]
0x18002d0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0fe  mov     rcx, [rbp+88h]; this
0x18002d105  test    eax, eax
0x18002d107  js      loc_18002D459
0x18002d10d  mov     [rsp+180h+var_130], r14d
0x18002d112  mov     rcx, [rsp+180h+var_128]
0x18002d117  mov     rax, [rcx]
0x18002d11a  lea     rdx, [rsp+180h+var_130]
0x18002d11f  mov     rax, [rax+38h]
0x18002d123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d128  mov     rcx, [rbp+88h]; this
0x18002d12f  test    eax, eax
0x18002d131  js      loc_18002D444
0x18002d137  cmp     [rsp+180h+var_130], 9
0x18002d13c  jz      loc_18002D35D
0x18002d142  mov     rcx, [rsp+180h+var_128]
0x18002d147  test    rcx, rcx
0x18002d14a  jz      short loc_18002D15E
0x18002d14c  mov     [rsp+180h+var_128], r14
0x18002d151  mov     rax, [rcx]
0x18002d154  mov     rax, [rax+10h]
0x18002d158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d15d  nop
0x18002d15e  inc     ebx
0x18002d160  cmp     ebx, [rsp+180h+var_120]
0x18002d164  jle     loc_18002D0E1
0x18002d16a  mov     [rbp+80h+var_F0], r14
0x18002d16e  mov     rcx, [rsp+180h+var_118]
0x18002d173  mov     rax, [rcx]
0x18002d176  lea     r8, [rbp+80h+var_F0]
0x18002d17a  mov     edx, 9
0x18002d17f  mov     rax, [rax+50h]
0x18002d183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d188  mov     rcx, [rbp+88h]; this
0x18002d18f  test    eax, eax
0x18002d191  js      loc_18002D42F
0x18002d197  mov     [rsp+180h+var_128], r14
0x18002d19c  mov     rcx, [rbp+80h+var_100]
0x18002d1a0  mov     rax, [rcx]
0x18002d1a3  movups  xmm1, xmmword ptr [rbp+80h+pvarg]
0x18002d1a7  movsd   xmm0, qword ptr [rbp+80h+pvarg+10h]
0x18002d1ac  movaps  [rbp+80h+var_60], xmm1
0x18002d1b0  movsd   [rbp+80h+var_50], xmm0
0x18002d1b5  movaps  [rbp+80h+var_A0], xmm1
0x18002d1b9  movsd   [rbp+80h+var_90], xmm0
0x18002d1be  movaps  xmmword ptr [rbp+80h+var_C0], xmm1
0x18002d1c2  movsd   [rbp+80h+var_B0], xmm0
0x18002d1c7  lea     rdx, [rsp+180h+var_128]
0x18002d1cc  mov     [rsp+180h+var_140], rdx
0x18002d1d1  lea     rdx, [rbp+80h+var_60]
0x18002d1d5  mov     [rsp+180h+var_148], rdx
0x18002d1da  mov     [rsp+180h+var_150], 5
0x18002d1e2  lea     rdx, [rbp+80h+var_A0]
0x18002d1e6  mov     [rsp+180h+var_158], rdx
0x18002d1eb  lea     rdx, [rbp+80h+var_C0]
0x18002d1ef  mov     [rsp+180h+ppv], rdx; int
0x18002d1f4  mov     ebx, 4
0x18002d1f9  mov     r9d, ebx
0x18002d1fc  mov     r8, [rsp+180h+var_108]
0x18002d201  mov     rdx, [rbp+80h+bstrString]
0x18002d205  mov     rax, [rax+88h]
0x18002d20c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d211  mov     rcx, [rbp+88h]; this
0x18002d218  test    eax, eax
0x18002d21a  js      loc_18002D375
0x18002d220  mov     eax, cs:dword_180052170
0x18002d226  cmp     eax, ebx
0x18002d228  jbe     short loc_18002D26A
0x18002d22a  mov     eax, [rsp+180h+var_120]
0x18002d22e  mov     [rsp+180h+var_130], eax
0x18002d232  lea     rax, [rsp+180h+var_130]
0x18002d237  mov     [rbp+80h+var_40], rax
0x18002d23b  mov     [rbp+80h+var_38], rbx
0x18002d23f  lea     rax, [rbp+80h+var_60]
0x18002d243  mov     [rsp+180h+var_158], rax
0x18002d248  mov     dword ptr [rsp+180h+ppv], 3
0x18002d250  xor     r9d, r9d
0x18002d253  xor     r8d, r8d
0x18002d256  lea     rdx, unk_180049938
0x18002d25d  lea     rcx, dword_180052170
0x18002d264  call    _tlgWriteTransfer_EventWriteTransfer
0x18002d269  nop
0x18002d26a  mov     rcx, [rsp+180h+var_128]
0x18002d26f  test    rcx, rcx
0x18002d272  jz      short loc_18002D286
0x18002d274  mov     [rsp+180h+var_128], r14
0x18002d279  mov     rax, [rcx]
0x18002d27c  mov     rax, [rax+10h]
0x18002d280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d285  nop
0x18002d286  mov     rcx, [rbp+80h+var_F0]
0x18002d28a  test    rcx, rcx
0x18002d28d  jz      short loc_18002D2A0
0x18002d28f  mov     [rbp+80h+var_F0], r14
0x18002d293  mov     rax, [rcx]
0x18002d296  mov     rax, [rax+10h]
0x18002d29a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d29f  nop
0x18002d2a0  mov     rcx, [rsp+180h+var_118]
0x18002d2a5  test    rcx, rcx
0x18002d2a8  jz      short loc_18002D2BC
0x18002d2aa  mov     [rsp+180h+var_118], r14
0x18002d2af  mov     rax, [rcx]
0x18002d2b2  mov     rax, [rax+10h]
0x18002d2b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2bb  nop
0x18002d2bc  mov     rcx, [rsp+180h+var_108]
0x18002d2c1  test    rcx, rcx
0x18002d2c4  jz      short loc_18002D2D8
0x18002d2c6  mov     [rsp+180h+var_108], r14
0x18002d2cb  mov     rax, [rcx]
0x18002d2ce  mov     rax, [rax+10h]
0x18002d2d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2d7  nop
0x18002d2d8  mov     rcx, [rbp+80h+bstrString]; bstrString
0x18002d2dc  test    rcx, rcx
0x18002d2df  jz      short loc_18002D2E8
0x18002d2e1  call    cs:__imp_SysFreeString
0x18002d2e7  nop
0x18002d2e8  mov     rcx, [rsp+180h+var_110]
0x18002d2ed  test    rcx, rcx
0x18002d2f0  jz      short loc_18002D304
0x18002d2f2  mov     [rsp+180h+var_110], r14
0x18002d2f7  mov     rax, [rcx]
0x18002d2fa  mov     rax, [rax+10h]
0x18002d2fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d303  nop
0x18002d304  mov     rcx, [rbp+80h+var_100]
0x18002d308  test    rcx, rcx
0x18002d30b  jz      short loc_18002D31E
0x18002d30d  mov     [rbp+80h+var_100], r14
0x18002d311  mov     rax, [rcx]
0x18002d314  mov     rax, [rax+10h]
0x18002d318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d31d  nop
0x18002d31e  lea     rcx, [rbp+80h+pvarg]; pvarg
0x18002d322  call    cs:__imp_VariantClear
0x18002d328  nop
0x18002d329  mov     rcx, [rbp+80h+var_F8]
0x18002d32d  test    rcx, rcx
0x18002d330  jz      short loc_18002D343
0x18002d332  mov     [rbp+80h+var_F8], r14
0x18002d336  mov     rax, [rcx]
0x18002d339  mov     rax, [rax+10h]
0x18002d33d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d342  nop
0x18002d343  mov     rcx, [rbp+80h+var_30]
0x18002d347  xor     rcx, rsp; StackCookie
0x18002d34a  call    __security_check_cookie
0x18002d34f  add     rsp, 160h
0x18002d356  pop     r14
0x18002d358  pop     rdi
0x18002d359  pop     rsi
0x18002d35a  pop     rbx
0x18002d35b  pop     rbp
0x18002d35c  retn
0x18002d35d  mov     rcx, [rsp+180h+var_128]
0x18002d362  test    rcx, rcx
0x18002d365  jz      loc_18002D2A0
0x18002d36b  mov     [rsp+180h+var_128], r14
0x18002d370  jmp     loc_18002D293
0x18002d375  mov     r9d, eax; char *
0x18002d378  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002d37f  mov     edx, 259h; void *
0x18002d384  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d38a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002d391  mov     edx, 15F3h; void *
0x18002d396  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18002d39c  mov     r9d, eax; char *
0x18002d39f  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002d3a6  mov     edx, 22Eh; void *
  ... truncated ...
```
