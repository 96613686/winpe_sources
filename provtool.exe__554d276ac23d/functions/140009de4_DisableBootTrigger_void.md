# DisableBootTrigger(void)

- ea: `0x140009de4`
- end: `0x14000a3b1`
- name: `?DisableBootTrigger@@YAXXZ`
- size: `1485`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1400059ac`

## callees

- `0x1400022c8`
- `0x140008b88`
- `0x140008ba8`
- `0x140009de4`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140009e38`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140009e38`
- `OLEAUT32!__imp_SysAllocString` at `0x140009ece`
- `OLEAUT32!__imp_SysAllocString` at `0x140009f35`
- `OLEAUT32!__imp_SysAllocString` at `0x14000a1cf`
- `OLEAUT32!__imp_SysAllocString` at `0x140009ece`
- `OLEAUT32!__imp_SysAllocString` at `0x140009f35`
- `OLEAUT32!__imp_SysAllocString` at `0x14000a1cf`
- `OLEAUT32!__imp_SysFreeString` at `0x140009f1b`
- `OLEAUT32!__imp_SysFreeString` at `0x140009f85`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a267`
- `OLEAUT32!__imp_SysFreeString` at `0x140009f1b`
- `OLEAUT32!__imp_SysFreeString` at `0x140009f85`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a267`
- `OLEAUT32!__imp_VariantInit` at `0x140009e51`
- `OLEAUT32!__imp_VariantInit` at `0x140009e51`
- `OLEAUT32!__imp_VariantClear` at `0x14000a157`
- `OLEAUT32!__imp_VariantClear` at `0x14000a157`

## string_xrefs

- `0x14000a2a9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000a2bb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000a375`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140009f2e`: `SetupUpdateBootTask`
- `0x14000a1c8`: `SetupUpdateBootTask`
- `0x14000a2d0`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x14000a2e5`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x14000a2fa`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x14000a30f`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x14000a324`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x14000a339`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x14000a34e`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x14000a363`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x14000a38a`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x14000a39f`: `onecoreuap\admin\prov\lib\taskhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void DisableBootTrigger(void)
{
  LPVOID *v0; // rax
  HRESULT Instance; // eax
  int v2; // eax
  __int64 *v3; // rdi
  __int64 v4; // rsi
  BSTR v5; // rax
  const char *v6; // r9
  OLECHAR *v7; // rbx
  int v8; // eax
  _QWORD *v9; // rdi
  __int64 v10; // rsi
  BSTR v11; // rax
  const char *v12; // r9
  OLECHAR *v13; // rbx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // eax
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  _QWORD *v25; // rcx
  __int64 *v26; // rcx
  _QWORD *v27; // rdi
  __int64 v28; // rsi
  __int128 v29; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int64 v31; // r14
  BSTR v32; // rax
  OLECHAR *v33; // rbx
  int v34; // eax
  __int64 v35; // rcx
  __int64 v36; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  __int64 v38; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v41; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v42; // [rsp+70h] [rbp-90h] BYREF
  __int64 v43; // [rsp+78h] [rbp-88h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h]
  VARIANTARG pvarg; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v46; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG v47; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG v48; // [rsp+E0h] [rbp-20h] BYREF
  BSTR v49; // [rsp+100h] [rbp+0h]
  VARIANTARG v50[3]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]
  BSTR v52; // [rsp+190h] [rbp+90h] BYREF
  int v53; // [rsp+198h] [rbp+98h] BYREF
  int v54; // [rsp+1A0h] [rbp+A0h]
  int v55; // [rsp+1A8h] [rbp+A8h] BYREF

  v54 = 0;
  v42 = 0;
  v0 = (LPVOID *)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(&v42);
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, v0);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  VariantInit(&pvarg);
  v50[0] = pvarg;
  v46 = pvarg;
  v47 = pvarg;
  v48 = pvarg;
  v2 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*v42 + 80))(
         v42,
         &v48,
         &v47,
         &v46);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v2,
      (int)v50);
  v41 = 0;
  v3 = v42;
  v4 = *v42;
  v5 = SysAllocString(L"\\Microsoft\\Windows\\Management\\Provisioning");
  v7 = v5;
  v52 = v5;
  v54 = 1;
  if ( !v5 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v6);
  v8 = (*(__int64 (__fastcall **)(__int64 *, BSTR, _QWORD **))(v4 + 56))(v3, v5, &v41);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v8,
      (int)v50);
  SysFreeString(v7);
  v43 = 0;
  v9 = v41;
  v10 = *v41;
  v11 = SysAllocString(L"SetupUpdateBootTask");
  v13 = v11;
  v52 = v11;
  v54 = 2;
  if ( !v11 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v12);
  v14 = (*(__int64 (__fastcall **)(_QWORD *, BSTR, __int64 *))(v10 + 104))(v9, v11, &v43);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x115,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v14,
      (int)v50);
  SysFreeString(v13);
  v40 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v43 + 152LL))(v43, &v40);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x118,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v15,
      (int)v50);
  v39 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 72LL))(v40, &v39);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11B,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v16,
      (int)v50);
  v53 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v39 + 56LL))(v39, &v53);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11E,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v17,
      (int)v50);
  v18 = 1;
  if ( v53 >= 1 )
  {
    while ( 1 )
    {
      v38 = 0;
      LOWORD(v52) = 0;
      v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v39 + 64LL))(v39, v18, &v38);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x124,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
          (const char *)(unsigned int)v19,
          (int)v50);
      v55 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 56LL))(v38, &v55);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x126,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
          (const char *)(unsigned int)v20,
          (int)v50);
      if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v38 + 144LL))(v38, &v52) >= 0 && v55 == 8 && (_WORD)v52 )
        break;
      v21 = v38;
      if ( v38 )
      {
        v38 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      if ( (int)++v18 > v53 )
        goto LABEL_19;
    }
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 152LL))(v38, 0);
    v44 = 0;
    v27 = v41;
    v28 = *v41;
    v29 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    v31 = v40;
    v32 = SysAllocString(L"SetupUpdateBootTask");
    v33 = v32;
    v49 = v32;
    v54 = 4;
    if ( !v32 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x15F3,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        (const char *)4);
    *(_OWORD *)&v48.vt = v29;
    v48.pRecInfo = pRecInfo;
    *(_OWORD *)&v47.vt = v29;
    v47.pRecInfo = pRecInfo;
    *(_OWORD *)&v46.vt = v29;
    v46.pRecInfo = pRecInfo;
    v34 = (*(__int64 (__fastcall **)(_QWORD *, BSTR, __int64))(v28 + 136))(v27, v32, v31);
    if ( v34 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12E,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
        (const char *)(unsigned int)v34,
        (int)&v46);
    SysFreeString(v33);
    v35 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v36 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
  }
LABEL_19:
  v22 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  v23 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v25 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v25 + 16LL))(v25);
  }
  VariantClear(&pvarg);
  v26 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64 *))(*v26 + 16))(v26);
  }
}

```

## disassembly

```asm
0x140009de4  mov     rax, rsp
0x140009de7  push    rbp
0x140009de8  push    rbx
0x140009de9  push    rsi
0x140009dea  push    rdi
0x140009deb  push    r14
0x140009ded  push    r15
0x140009def  lea     rbp, [rsp-58h]
0x140009df4  sub     rsp, 158h
0x140009dfb  movaps  xmmword ptr [rax-48h], xmm6
0x140009dff  movaps  xmmword ptr [rax-58h], xmm7
0x140009e03  xor     r15d, r15d
0x140009e06  mov     [rbp+80h+arg_10], r15d
0x140009e0d  mov     [rsp+180h+var_110], r15
0x140009e12  lea     rcx, [rsp+180h+var_110]
0x140009e17  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITaskService>>)
0x140009e1c  mov     [rsp+180h+ppv], rax; int
0x140009e21  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x140009e28  lea     r14d, [r15+1]
0x140009e2c  mov     r8d, r14d; dwClsContext
0x140009e2f  xor     edx, edx; pUnkOuter
0x140009e31  lea     rcx, CLSID_TaskScheduler; rclsid
0x140009e38  call    cs:__imp_CoCreateInstance
0x140009e3e  mov     rcx, [rbp+88h]; this
0x140009e45  test    eax, eax
0x140009e47  js      loc_14000A2CD
0x140009e4d  lea     rcx, [rbp+80h+pvarg]; pvarg
0x140009e51  call    cs:__imp_VariantInit
0x140009e57  nop
0x140009e58  mov     rcx, [rsp+180h+var_110]
0x140009e5d  movups  xmm1, xmmword ptr [rbp+80h+pvarg]
0x140009e61  movsd   xmm0, qword ptr [rbp+80h+pvarg+10h]
0x140009e66  movaps  xmmword ptr [rbp+80h+var_70], xmm1
0x140009e6a  movsd   [rbp+80h+var_60], xmm0
0x140009e6f  movaps  xmmword ptr [rbp+80h+var_E0], xmm1
0x140009e73  movsd   [rbp+80h+var_D0], xmm0
0x140009e78  movaps  [rbp+80h+var_C0], xmm1
0x140009e7c  movsd   [rbp+80h+var_B0], xmm0
0x140009e81  movaps  [rbp+80h+var_A0], xmm1
0x140009e85  movsd   [rbp+80h+var_90], xmm0
0x140009e8a  mov     rax, [rcx]
0x140009e8d  lea     rdx, [rbp+80h+var_70]
0x140009e91  mov     [rsp+180h+ppv], rdx; int
0x140009e96  lea     r9, [rbp+80h+var_E0]
0x140009e9a  lea     r8, [rbp+80h+var_C0]
0x140009e9e  lea     rdx, [rbp+80h+var_A0]
0x140009ea2  mov     rax, [rax+50h]
0x140009ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009eab  mov     rcx, [rbp+88h]; this
0x140009eb2  test    eax, eax
0x140009eb4  js      loc_14000A2E2
0x140009eba  mov     [rsp+180h+var_118], r15
0x140009ebf  mov     rdi, [rsp+180h+var_110]
0x140009ec4  mov     rsi, [rdi]
0x140009ec7  lea     rcx, psz; "\\Microsoft\\Windows\\Management\\Provi"...
0x140009ece  call    cs:__imp_SysAllocString
0x140009ed4  mov     rbx, rax
0x140009ed7  mov     [rbp+80h+arg_0], rax
0x140009ede  mov     [rbp+80h+arg_10], r14d
0x140009ee5  mov     rcx, [rbp+88h]; this
0x140009eec  test    rax, rax
0x140009eef  jz      loc_14000A2BB
0x140009ef5  lea     r8, [rsp+180h+var_118]
0x140009efa  mov     rdx, rax
0x140009efd  mov     rcx, rdi
0x140009f00  mov     rax, [rsi+38h]
0x140009f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f09  mov     rcx, [rbp+88h]; this
0x140009f10  test    eax, eax
0x140009f12  js      loc_14000A2F7
0x140009f18  mov     rcx, rbx; bstrString
0x140009f1b  call    cs:__imp_SysFreeString
0x140009f21  mov     [rsp+180h+var_108], r15
0x140009f26  mov     rdi, [rsp+180h+var_118]
0x140009f2b  mov     rsi, [rdi]
0x140009f2e  lea     rcx, aSetupupdateboo; "SetupUpdateBootTask"
0x140009f35  call    cs:__imp_SysAllocString
0x140009f3b  mov     rbx, rax
0x140009f3e  mov     [rbp+80h+arg_0], rax
0x140009f45  mov     [rbp+80h+arg_10], 2
0x140009f4f  mov     rcx, [rbp+88h]; this
0x140009f56  test    rax, rax
0x140009f59  jz      loc_14000A2A9
0x140009f5f  lea     r8, [rsp+180h+var_108]
0x140009f64  mov     rdx, rax
0x140009f67  mov     rcx, rdi
0x140009f6a  mov     rax, [rsi+68h]
0x140009f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f73  mov     rcx, [rbp+88h]; this
0x140009f7a  test    eax, eax
0x140009f7c  js      loc_14000A30C
0x140009f82  mov     rcx, rbx; bstrString
0x140009f85  call    cs:__imp_SysFreeString
0x140009f8b  mov     [rsp+180h+var_120], r15
0x140009f90  mov     rcx, [rsp+180h+var_108]
0x140009f95  mov     rax, [rcx]
0x140009f98  lea     rdx, [rsp+180h+var_120]
0x140009f9d  mov     rax, [rax+98h]
0x140009fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009fa9  mov     rcx, [rbp+88h]; this
0x140009fb0  test    eax, eax
0x140009fb2  js      loc_14000A321
0x140009fb8  mov     [rsp+180h+var_128], r15
0x140009fbd  mov     rcx, [rsp+180h+var_120]
0x140009fc2  mov     rax, [rcx]
0x140009fc5  lea     rdx, [rsp+180h+var_128]
0x140009fca  mov     rax, [rax+48h]
0x140009fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009fd3  mov     rcx, [rbp+88h]; this
0x140009fda  test    eax, eax
0x140009fdc  js      loc_14000A336
0x140009fe2  mov     [rbp+80h+arg_8], r15d
0x140009fe9  mov     rcx, [rsp+180h+var_128]
0x140009fee  mov     rax, [rcx]
0x140009ff1  lea     rdx, [rbp+80h+arg_8]
0x140009ff8  mov     rax, [rax+38h]
0x140009ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a001  mov     rcx, [rbp+88h]; this
0x14000a008  test    eax, eax
0x14000a00a  js      loc_14000A34B
0x14000a010  mov     ebx, r14d
0x14000a013  cmp     [rbp+80h+arg_8], r14d
0x14000a01a  jl      loc_14000A0E3
0x14000a020  mov     [rsp+180h+var_130], r15
0x14000a025  mov     word ptr [rbp+80h+arg_0], r15w
0x14000a02d  mov     rcx, [rsp+180h+var_128]
0x14000a032  mov     rax, [rcx]
0x14000a035  lea     r8, [rsp+180h+var_130]
0x14000a03a  mov     edx, ebx
0x14000a03c  mov     rax, [rax+40h]
0x14000a040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a045  mov     rcx, [rbp+88h]; this
0x14000a04c  test    eax, eax
0x14000a04e  js      loc_14000A39C
0x14000a054  mov     [rbp+80h+arg_18], r15d
0x14000a05b  mov     rcx, [rsp+180h+var_130]
0x14000a060  mov     rax, [rcx]
0x14000a063  lea     rdx, [rbp+80h+arg_18]
0x14000a06a  mov     rax, [rax+38h]
0x14000a06e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a073  mov     rcx, [rbp+88h]; this
0x14000a07a  test    eax, eax
0x14000a07c  js      loc_14000A387
0x14000a082  mov     rcx, [rsp+180h+var_130]
0x14000a087  mov     rax, [rcx]
0x14000a08a  lea     rdx, [rbp+80h+arg_0]
0x14000a091  mov     rax, [rax+90h]
0x14000a098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a09d  test    eax, eax
0x14000a09f  js      short loc_14000A0B8
0x14000a0a1  cmp     [rbp+80h+arg_18], 8
0x14000a0a8  jnz     short loc_14000A0B8
0x14000a0aa  cmp     word ptr [rbp+80h+arg_0], r15w
0x14000a0b2  jnz     loc_14000A198
0x14000a0b8  mov     rcx, [rsp+180h+var_130]
0x14000a0bd  test    rcx, rcx
0x14000a0c0  jz      short loc_14000A0D4
0x14000a0c2  mov     [rsp+180h+var_130], r15
0x14000a0c7  mov     rax, [rcx]
0x14000a0ca  mov     rax, [rax+10h]
0x14000a0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a0d3  nop
0x14000a0d4  add     ebx, r14d
0x14000a0d7  cmp     ebx, [rbp+80h+arg_8]
0x14000a0dd  jle     loc_14000A020
0x14000a0e3  mov     rcx, [rsp+180h+var_128]
0x14000a0e8  test    rcx, rcx
0x14000a0eb  jz      short loc_14000A0FF
0x14000a0ed  mov     [rsp+180h+var_128], r15
0x14000a0f2  mov     rax, [rcx]
0x14000a0f5  mov     rax, [rax+10h]
0x14000a0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a0fe  nop
0x14000a0ff  mov     rcx, [rsp+180h+var_120]
0x14000a104  test    rcx, rcx
0x14000a107  jz      short loc_14000A11B
0x14000a109  mov     [rsp+180h+var_120], r15
0x14000a10e  mov     rax, [rcx]
0x14000a111  mov     rax, [rax+10h]
0x14000a115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a11a  nop
0x14000a11b  mov     rcx, [rsp+180h+var_108]
0x14000a120  test    rcx, rcx
0x14000a123  jz      short loc_14000A137
0x14000a125  mov     [rsp+180h+var_108], r15
0x14000a12a  mov     rax, [rcx]
0x14000a12d  mov     rax, [rax+10h]
0x14000a131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a136  nop
0x14000a137  mov     rcx, [rsp+180h+var_118]
0x14000a13c  test    rcx, rcx
0x14000a13f  jz      short loc_14000A153
0x14000a141  mov     [rsp+180h+var_118], r15
0x14000a146  mov     rax, [rcx]
0x14000a149  mov     rax, [rax+10h]
0x14000a14d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a152  nop
0x14000a153  lea     rcx, [rbp+80h+pvarg]; pvarg
0x14000a157  call    cs:__imp_VariantClear
0x14000a15d  nop
0x14000a15e  mov     rcx, [rsp+180h+var_110]
0x14000a163  test    rcx, rcx
0x14000a166  jz      short loc_14000A17A
0x14000a168  mov     [rsp+180h+var_110], r15
0x14000a16d  mov     rax, [rcx]
0x14000a170  mov     rax, [rax+10h]
0x14000a174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a179  nop
0x14000a17a  lea     r11, [rsp+180h+var_28]
0x14000a182  movaps  xmm6, xmmword ptr [r11-18h]
0x14000a187  movaps  xmm7, xmmword ptr [r11-28h]
0x14000a18c  mov     rsp, r11
0x14000a18f  pop     r15
0x14000a191  pop     r14
0x14000a193  pop     rdi
0x14000a194  pop     rsi
0x14000a195  pop     rbx
0x14000a196  pop     rbp
0x14000a197  retn
0x14000a198  mov     rcx, [rsp+180h+var_130]
0x14000a19d  mov     rax, [rcx]
0x14000a1a0  xor     edx, edx
0x14000a1a2  mov     rax, [rax+98h]
0x14000a1a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a1ae  mov     [rbp+80h+var_100], r15
0x14000a1b2  mov     rdi, [rsp+180h+var_118]
0x14000a1b7  mov     rsi, [rdi]
0x14000a1ba  movups  xmm6, xmmword ptr [rbp+80h+pvarg]
0x14000a1be  movsd   xmm7, qword ptr [rbp+80h+pvarg+10h]
0x14000a1c3  mov     r14, [rsp+180h+var_120]
0x14000a1c8  lea     rcx, aSetupupdateboo; "SetupUpdateBootTask"
0x14000a1cf  call    cs:__imp_SysAllocString
0x14000a1d5  mov     rbx, rax
0x14000a1d8  mov     [rbp+80h+var_80], rax
0x14000a1dc  mov     r9d, 4; char *
0x14000a1e2  mov     [rbp+80h+arg_10], r9d
0x14000a1e9  mov     rcx, [rbp+88h]; this
0x14000a1f0  test    rax, rax
0x14000a1f3  jz      loc_14000A375
0x14000a1f9  movaps  [rbp+80h+var_A0], xmm6
0x14000a1fd  movsd   [rbp+80h+var_90], xmm7
0x14000a202  movaps  [rbp+80h+var_C0], xmm6
0x14000a206  movsd   [rbp+80h+var_B0], xmm7
0x14000a20b  movaps  xmmword ptr [rbp+80h+var_E0], xmm6
0x14000a20f  movsd   [rbp+80h+var_D0], xmm7
0x14000a214  lea     rax, [rbp+80h+var_100]
0x14000a218  mov     [rsp+180h+var_140], rax
0x14000a21d  lea     rax, [rbp+80h+var_A0]
0x14000a221  mov     [rsp+180h+var_148], rax
0x14000a226  mov     [rsp+180h+var_150], 5
0x14000a22e  lea     rax, [rbp+80h+var_C0]
0x14000a232  mov     [rsp+180h+var_158], rax
0x14000a237  lea     rax, [rbp+80h+var_E0]
0x14000a23b  mov     [rsp+180h+ppv], rax; int
0x14000a240  mov     r8, r14
0x14000a243  mov     rdx, rbx
0x14000a246  mov     rcx, rdi
0x14000a249  mov     rax, [rsi+88h]
0x14000a250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a255  mov     rcx, [rbp+88h]; this
0x14000a25c  test    eax, eax
0x14000a25e  js      loc_14000A360
0x14000a264  mov     rcx, rbx; bstrString
0x14000a267  call    cs:__imp_SysFreeString
0x14000a26d  nop
0x14000a26e  mov     rcx, [rbp+80h+var_100]
0x14000a272  test    rcx, rcx
0x14000a275  jz      short loc_14000A288
0x14000a277  mov     [rbp+80h+var_100], r15
0x14000a27b  mov     rax, [rcx]
0x14000a27e  mov     rax, [rax+10h]
0x14000a282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a287  nop
0x14000a288  mov     rcx, [rsp+180h+var_130]
0x14000a28d  test    rcx, rcx
0x14000a290  jz      short loc_14000A2A4
0x14000a292  mov     [rsp+180h+var_130], r15
0x14000a297  mov     rax, [rcx]
0x14000a29a  mov     rax, [rax+10h]
0x14000a29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a2a3  nop
0x14000a2a4  jmp     loc_14000A0E3
0x14000a2a9  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000a2b0  mov     edx, 15F3h; void *
0x14000a2b5  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x14000a2bb  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000a2c2  mov     edx, 15F3h; void *
0x14000a2c7  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x14000a2cd  mov     r9d, eax; char *
0x14000a2d0  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x14000a2d7  mov     edx, 10Ch; void *
0x14000a2dc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000a2e2  mov     r9d, eax; char *
0x14000a2e5  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x14000a2ec  mov     edx, 10Fh; void *
0x14000a2f1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000a2f7  mov     r9d, eax; char *
0x14000a2fa  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x14000a301  mov     edx, 112h; void *
0x14000a306  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
