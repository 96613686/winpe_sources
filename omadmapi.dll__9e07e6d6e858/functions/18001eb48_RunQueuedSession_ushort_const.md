# RunQueuedSession(ushort const *)

- ea: `0x18001eb48`
- end: `0x18001f43e`
- name: `?RunQueuedSession@@YAJPEBG@Z`
- size: `2294`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001f444`

## callees

- `0x180011b98`
- `0x18001e5e4`
- `0x18001e7b4`
- `0x18001eb48`
- `0x18002043c`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001ec9b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001eeb7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001efd3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001f0f4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001f21c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001f353`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001f3f5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001ec9b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001eeb7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001efd3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001f0f4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001f21c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001f353`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001f3f5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ebe7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ebe7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001eb81`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001eb81`
- `OLEAUT32!__imp_VariantInit` at `0x18001ecbf`
- `OLEAUT32!__imp_VariantInit` at `0x18001ece1`
- `OLEAUT32!__imp_VariantInit` at `0x18001ed09`
- `OLEAUT32!__imp_VariantInit` at `0x18001ed2f`
- `OLEAUT32!__imp_VariantInit` at `0x18001f25f`
- `OLEAUT32!__imp_VariantInit` at `0x18001ecbf`
- `OLEAUT32!__imp_VariantInit` at `0x18001ece1`
- `OLEAUT32!__imp_VariantInit` at `0x18001ed09`
- `OLEAUT32!__imp_VariantInit` at `0x18001ed2f`
- `OLEAUT32!__imp_VariantInit` at `0x18001f25f`
- `OLEAUT32!__imp_VariantClear` at `0x18001edc9`
- `OLEAUT32!__imp_VariantClear` at `0x18001edde`
- `OLEAUT32!__imp_VariantClear` at `0x18001edf3`
- `OLEAUT32!__imp_VariantClear` at `0x18001ee05`
- `OLEAUT32!__imp_VariantClear` at `0x18001f2a1`
- `OLEAUT32!__imp_VariantClear` at `0x18001edc9`
- `OLEAUT32!__imp_VariantClear` at `0x18001edde`
- `OLEAUT32!__imp_VariantClear` at `0x18001edf3`
- `OLEAUT32!__imp_VariantClear` at `0x18001ee05`
- `OLEAUT32!__imp_VariantClear` at `0x18001f2a1`

## string_xrefs

- `0x18001f134`: `Queued Schedule created for queued alerts`

## pseudocode

```c
// Hidden C++ exception states: #wind=17 #try_helpers=1
__int64 __fastcall RunQueuedSession(const unsigned __int16 *a1)
{
  HRESULT v2; // eax
  void *v3; // rdx
  unsigned int v4; // r8d
  HRESULT v5; // eax
  int v6; // ebx
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v10; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v12; // xmm8
  IRecordInfo *v13; // xmm9_8
  __int128 v14; // xmm6
  IRecordInfo *v15; // xmm7_8
  LPVOID v16; // rbx
  __int64 v17; // rdi
  __int64 *v18; // rax
  __int64 v19; // rdx
  int v20; // ebx
  __int64 *v21; // rbx
  __int64 v22; // rdi
  __int64 *v23; // rcx
  __int64 *v24; // rax
  __int64 v25; // rdx
  __int64 *v26; // rbx
  __int64 v27; // rdi
  __int64 v28; // rcx
  __int64 *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rbx
  __int64 (__fastcall *v32)(__int64, VARIANTARG *, __int64 *); // rdi
  __int64 v33; // rcx
  int ppv; // [rsp+20h] [rbp-1A8h]
  int ppva; // [rsp+20h] [rbp-1A8h]
  __int64 *v36; // [rsp+30h] [rbp-198h] BYREF
  __int64 v37; // [rsp+38h] [rbp-190h] BYREF
  LPVOID v38; // [rsp+40h] [rbp-188h] BYREF
  _BYTE v39[8]; // [rsp+48h] [rbp-180h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-178h] BYREF
  VARIANTARG v41; // [rsp+70h] [rbp-158h] BYREF
  VARIANTARG v42; // [rsp+90h] [rbp-138h] BYREF
  VARIANTARG v43; // [rsp+A8h] [rbp-120h] BYREF
  VARIANTARG v44; // [rsp+C0h] [rbp-108h] BYREF
  int v45[4]; // [rsp+E0h] [rbp-E8h] BYREF
  IRecordInfo *v46; // [rsp+F0h] [rbp-D8h]
  __int128 v47; // [rsp+100h] [rbp-C8h] BYREF
  IRecordInfo *v48; // [rsp+110h] [rbp-B8h]
  __int128 v49; // [rsp+120h] [rbp-A8h] BYREF
  IRecordInfo *v50; // [rsp+130h] [rbp-98h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]
  __int64 v52; // [rsp+1E0h] [rbp+18h] BYREF
  __int64 *v53; // [rsp+1E8h] [rbp+20h] BYREF

  v2 = CoInitializeEx(0, 0);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, v3, v4, (const char *)(unsigned int)v2, ppv);
  v36 = 0;
  v53 = 0;
  v52 = 0;
  v37 = 0;
  v38 = 0;
  v5 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v38);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\throttling.cpp",
      (const char *)(unsigned int)v5,
      ppva);
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    if ( v53 )
      (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
    if ( v38 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v38 + 16LL))(v38);
LABEL_9:
    CoUninitialize();
    return (unsigned int)v6;
  }
  v8 = v38;
  v9 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)v38 + 80LL);
  VariantInit(&pvarg);
  v10 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v44);
  v12 = *(_OWORD *)&v44.vt;
  v13 = v44.pRecInfo;
  VariantInit(&v43);
  v14 = *(_OWORD *)&v43.vt;
  v15 = v43.pRecInfo;
  VariantInit(&v42);
  *(_OWORD *)v45 = v10;
  v46 = pRecInfo;
  v47 = v12;
  v48 = v13;
  v49 = v14;
  v50 = v15;
  v41 = v42;
  v6 = v9(v8, &v41, &v49, &v47);
  VariantClear(&v42);
  VariantClear(&v43);
  VariantClear(&v44);
  VariantClear(&pvarg);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFC,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\throttling.cpp",
      (const char *)(unsigned int)v6,
      (int)v45);
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    if ( v53 )
      (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
    if ( v38 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v38 + 16LL))(v38);
    goto LABEL_9;
  }
  v16 = v38;
  v17 = *(_QWORD *)v38;
  v36 = 0;
  v18 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)v39, L"\\Microsoft\\Windows\\EnterpriseMgmtNonCritical");
  if ( v18 )
    v19 = *v18;
  else
    v19 = 0;
  v20 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 **))(v17 + 56))(v16, v19, &v36);
  _bstr_t::~_bstr_t((_bstr_t *)v39);
  if ( v20 >= 0 )
  {
    v21 = v36;
    v22 = *v36;
    v23 = v53;
    v53 = 0;
    if ( v23 )
      (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
    v24 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)v39, a1);
    if ( v24 )
      v25 = *v24;
    else
      v25 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 **))(v22 + 72))(v21, v25, &v53);
    _bstr_t::~_bstr_t((_bstr_t *)v39);
    if ( v20 >= 0 )
    {
      v26 = v53;
      v27 = *v53;
      v28 = v52;
      v52 = 0;
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      v29 = *(__int64 **)_bstr_t::_bstr_t((_bstr_t *)v39, L"Queued Schedule created for queued alerts");
      if ( v29 )
        v30 = *v29;
      else
        v30 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v27 + 104))(v26, v30, &v52);
      _bstr_t::~_bstr_t((_bstr_t *)v39);
      if ( v20 >= 0 )
      {
        v31 = v52;
        v32 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, __int64 *))(*(_QWORD *)v52 + 96LL);
        v33 = v37;
        v37 = 0;
        if ( v33 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
        VariantInit(&pvarg);
        v41 = pvarg;
        v20 = v32(v31, &v41, &v37);
        VariantClear(&pvarg);
        if ( v20 >= 0 )
        {
          if ( v37 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
          if ( v52 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
          if ( v53 )
            (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
          if ( v36 )
            (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
          if ( v38 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v38 + 16LL))(v38);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x108,
            (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\throttling.cpp",
            (const char *)(unsigned int)v20,
            (int)v45);
          if ( v37 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
          if ( v52 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
          if ( v53 )
            (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
          if ( v36 )
            (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
          if ( v38 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v38 + 16LL))(v38);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x105,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\throttling.cpp",
          (const char *)(unsigned int)v20,
          (int)v45);
        if ( v37 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        if ( v52 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
        if ( v53 )
          (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
        if ( v36 )
          (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
        if ( v38 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v38 + 16LL))(v38);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x102,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\throttling.cpp",
        (const char *)(unsigned int)v20,
        (int)v45);
      if ( v37 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      if ( v52 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      if ( v53 )
        (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
      if ( v36 )
        (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
      if ( v38 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v38 + 16LL))(v38);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFF,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\throttling.cpp",
      (const char *)(unsigned int)v20,
      (int)v45);
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    if ( v53 )
      (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
    if ( v36 )
      (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
    if ( v38 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v38 + 16LL))(v38);
  }
  CoUninitialize();
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x18001eb48  mov     rax, rsp
0x18001eb4b  push    rbx
0x18001eb4c  push    rsi
0x18001eb4d  push    rdi
0x18001eb4e  push    r14
0x18001eb50  push    r15
0x18001eb52  sub     rsp, 1A0h
0x18001eb59  movaps  xmmword ptr [rax-38h], xmm6
0x18001eb5d  movaps  xmmword ptr [rax-48h], xmm7
0x18001eb61  movaps  xmmword ptr [rax-58h], xmm8
0x18001eb66  movaps  xmmword ptr [rax-68h], xmm9
0x18001eb6b  movaps  xmmword ptr [rax-78h], xmm10
0x18001eb70  movaps  xmmword ptr [rax-88h], xmm11
0x18001eb78  mov     r15, rcx
0x18001eb7b  xor     esi, esi
0x18001eb7d  xor     edx, edx; dwCoInit
0x18001eb7f  xor     ecx, ecx; pvReserved
0x18001eb81  call    cs:__imp_CoInitializeEx
0x18001eb88  nop     dword ptr [rax+rax+00h]
0x18001eb8d  mov     rcx, [rsp+1C8h]; this
0x18001eb95  test    eax, eax
0x18001eb97  js      loc_18001F435
0x18001eb9d  mov     r14d, 1
0x18001eba3  mov     [rsp+1C8h+arg_8], r14b
0x18001ebab  mov     [rsp+1C8h+var_198], rsi
0x18001ebb0  mov     [rsp+1C8h+arg_18], rsi
0x18001ebb8  mov     [rsp+1C8h+arg_10], rsi
0x18001ebc0  mov     [rsp+1C8h+var_190], rsi
0x18001ebc5  mov     [rsp+1C8h+var_188], rsi
0x18001ebca  lea     rax, [rsp+1C8h+var_188]
0x18001ebcf  mov     qword ptr [rsp+1C8h+ppv], rax; int
0x18001ebd4  lea     r9, IID_ITaskService; riid
0x18001ebdb  mov     r8d, r14d; dwClsContext
0x18001ebde  xor     edx, edx; pUnkOuter
0x18001ebe0  lea     rcx, CLSID_TaskScheduler; rclsid
0x18001ebe7  call    cs:__imp_CoCreateInstance
0x18001ebee  nop     dword ptr [rax+rax+00h]
0x18001ebf3  mov     ebx, eax
0x18001ebf5  test    eax, eax
0x18001ebf7  jns     loc_18001ECAE
0x18001ebfd  mov     rcx, [rsp+1C8h]; this
0x18001ec05  mov     r9d, eax; char *
0x18001ec08  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
0x18001ec0f  mov     edx, 0F9h; void *
0x18001ec14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ec19  nop
0x18001ec1a  mov     rcx, [rsp+1C8h+var_190]
0x18001ec1f  test    rcx, rcx
0x18001ec22  jz      short loc_18001EC31
0x18001ec24  mov     rax, [rcx]
0x18001ec27  mov     rax, [rax+10h]
0x18001ec2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec30  nop
0x18001ec31  mov     rcx, [rsp+1C8h+arg_10]
0x18001ec39  test    rcx, rcx
0x18001ec3c  jz      short loc_18001EC4B
0x18001ec3e  mov     rax, [rcx]
0x18001ec41  mov     rax, [rax+10h]
0x18001ec45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec4a  nop
0x18001ec4b  mov     rcx, [rsp+1C8h+arg_18]
0x18001ec53  test    rcx, rcx
0x18001ec56  jz      short loc_18001EC65
0x18001ec58  mov     rax, [rcx]
0x18001ec5b  mov     rax, [rax+10h]
0x18001ec5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec64  nop
0x18001ec65  mov     rcx, [rsp+1C8h+var_198]
0x18001ec6a  test    rcx, rcx
0x18001ec6d  jz      short loc_18001EC7C
0x18001ec6f  mov     rax, [rcx]
0x18001ec72  mov     rax, [rax+10h]
0x18001ec76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec7b  nop
0x18001ec7c  mov     rcx, [rsp+1C8h+var_188]
0x18001ec81  test    rcx, rcx
0x18001ec84  jz      short loc_18001EC93
0x18001ec86  mov     rax, [rcx]
0x18001ec89  mov     rax, [rax+10h]
0x18001ec8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec92  nop
0x18001ec93  mov     [rsp+1C8h+arg_8], sil
0x18001ec9b  call    cs:__imp_CoUninitialize
0x18001eca2  nop     dword ptr [rax+rax+00h]
0x18001eca7  mov     eax, ebx
0x18001eca9  jmp     loc_18001F403
0x18001ecae  mov     rdi, [rsp+1C8h+var_188]
0x18001ecb3  mov     rax, [rdi]
0x18001ecb6  mov     rbx, [rax+50h]
0x18001ecba  lea     rcx, [rsp+1C8h+pvarg]; pvarg
0x18001ecbf  call    cs:__imp_VariantInit
0x18001ecc6  nop     dword ptr [rax+rax+00h]
0x18001eccb  nop
0x18001eccc  movups  xmm10, xmmword ptr [rsp+1C8h+pvarg]
0x18001ecd2  movsd   xmm11, qword ptr [rsp+1C8h+pvarg+10h]
0x18001ecd9  lea     rcx, [rsp+1C8h+var_108]; pvarg
0x18001ece1  call    cs:__imp_VariantInit
0x18001ece8  nop     dword ptr [rax+rax+00h]
0x18001eced  nop
0x18001ecee  movups  xmm8, xmmword ptr [rsp+1C8h+var_108]
0x18001ecf7  movsd   xmm9, qword ptr [rsp+1C8h+var_108+10h]
0x18001ed01  lea     rcx, [rsp+1C8h+var_120]; pvarg
0x18001ed09  call    cs:__imp_VariantInit
0x18001ed10  nop     dword ptr [rax+rax+00h]
0x18001ed15  nop
0x18001ed16  movups  xmm6, xmmword ptr [rsp+1C8h+var_120]
0x18001ed1e  movsd   xmm7, qword ptr [rsp+1C8h+var_120+10h]
0x18001ed27  lea     rcx, [rsp+1C8h+var_138]; pvarg
0x18001ed2f  call    cs:__imp_VariantInit
0x18001ed36  nop     dword ptr [rax+rax+00h]
0x18001ed3b  nop
0x18001ed3c  movups  xmm0, xmmword ptr [rsp+1C8h+var_138]
0x18001ed44  movsd   xmm1, qword ptr [rsp+1C8h+var_138+10h]
0x18001ed4d  movaps  xmmword ptr [rsp+1C8h+var_E8], xmm10
0x18001ed56  movsd   [rsp+1C8h+var_D8], xmm11
0x18001ed60  movaps  [rsp+1C8h+var_C8], xmm8
0x18001ed69  movsd   [rsp+1C8h+var_B8], xmm9
0x18001ed73  movaps  [rsp+1C8h+var_A8], xmm6
0x18001ed7b  movsd   [rsp+1C8h+var_98], xmm7
0x18001ed84  movaps  [rsp+1C8h+var_158], xmm0
0x18001ed89  movsd   [rsp+1C8h+var_148], xmm1
0x18001ed92  lea     rax, [rsp+1C8h+var_E8]
0x18001ed9a  mov     qword ptr [rsp+1C8h+ppv], rax; int
0x18001ed9f  lea     r9, [rsp+1C8h+var_C8]
0x18001eda7  lea     r8, [rsp+1C8h+var_A8]
0x18001edaf  lea     rdx, [rsp+1C8h+var_158]
0x18001edb4  mov     rcx, rdi
0x18001edb7  mov     rax, rbx
0x18001edba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edbf  mov     ebx, eax
0x18001edc1  lea     rcx, [rsp+1C8h+var_138]; pvarg
0x18001edc9  call    cs:__imp_VariantClear
0x18001edd0  nop     dword ptr [rax+rax+00h]
0x18001edd5  nop
0x18001edd6  lea     rcx, [rsp+1C8h+var_120]; pvarg
0x18001edde  call    cs:__imp_VariantClear
0x18001ede5  nop     dword ptr [rax+rax+00h]
0x18001edea  nop
0x18001edeb  lea     rcx, [rsp+1C8h+var_108]; pvarg
0x18001edf3  call    cs:__imp_VariantClear
0x18001edfa  nop     dword ptr [rax+rax+00h]
0x18001edff  nop
0x18001ee00  lea     rcx, [rsp+1C8h+pvarg]; pvarg
0x18001ee05  call    cs:__imp_VariantClear
0x18001ee0c  nop     dword ptr [rax+rax+00h]
0x18001ee11  test    ebx, ebx
0x18001ee13  jns     loc_18001EECA
0x18001ee19  mov     rcx, [rsp+1C8h]; this
0x18001ee21  mov     r9d, ebx; char *
0x18001ee24  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
0x18001ee2b  mov     edx, 0FCh; void *
0x18001ee30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ee35  nop
0x18001ee36  mov     rcx, [rsp+1C8h+var_190]
0x18001ee3b  test    rcx, rcx
0x18001ee3e  jz      short loc_18001EE4D
0x18001ee40  mov     rax, [rcx]
0x18001ee43  mov     rax, [rax+10h]
0x18001ee47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee4c  nop
0x18001ee4d  mov     rcx, [rsp+1C8h+arg_10]
0x18001ee55  test    rcx, rcx
0x18001ee58  jz      short loc_18001EE67
0x18001ee5a  mov     rax, [rcx]
0x18001ee5d  mov     rax, [rax+10h]
0x18001ee61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee66  nop
0x18001ee67  mov     rcx, [rsp+1C8h+arg_18]
0x18001ee6f  test    rcx, rcx
0x18001ee72  jz      short loc_18001EE81
0x18001ee74  mov     rax, [rcx]
0x18001ee77  mov     rax, [rax+10h]
0x18001ee7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee80  nop
0x18001ee81  mov     rcx, [rsp+1C8h+var_198]
0x18001ee86  test    rcx, rcx
0x18001ee89  jz      short loc_18001EE98
0x18001ee8b  mov     rax, [rcx]
0x18001ee8e  mov     rax, [rax+10h]
0x18001ee92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee97  nop
0x18001ee98  mov     rcx, [rsp+1C8h+var_188]
0x18001ee9d  test    rcx, rcx
0x18001eea0  jz      short loc_18001EEAF
0x18001eea2  mov     rax, [rcx]
0x18001eea5  mov     rax, [rax+10h]
0x18001eea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eeae  nop
0x18001eeaf  mov     [rsp+1C8h+arg_8], sil
0x18001eeb7  call    cs:__imp_CoUninitialize
0x18001eebe  nop     dword ptr [rax+rax+00h]
0x18001eec3  mov     eax, ebx
0x18001eec5  jmp     loc_18001F403
0x18001eeca  mov     rbx, [rsp+1C8h+var_188]
0x18001eecf  mov     rdi, [rbx]
0x18001eed2  mov     rcx, [rsp+1C8h+var_198]
0x18001eed7  mov     [rsp+1C8h+var_198], rsi
0x18001eedc  test    rcx, rcx
0x18001eedf  jz      short loc_18001EEEE
0x18001eee1  mov     rax, [rcx]
0x18001eee4  mov     rax, [rax+10h]
0x18001eee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eeed  nop
0x18001eeee  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\EnterpriseMgmtNon"...
0x18001eef5  lea     rcx, [rsp+1C8h+var_180]; this
0x18001eefa  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001eeff  nop
0x18001ef00  mov     rax, [rax]
0x18001ef03  test    rax, rax
0x18001ef06  jz      short loc_18001EF0D
0x18001ef08  mov     rdx, [rax]
0x18001ef0b  jmp     short loc_18001EF10
0x18001ef0d  mov     rdx, rsi
0x18001ef10  lea     r8, [rsp+1C8h+var_198]
0x18001ef15  mov     rcx, rbx
0x18001ef18  mov     rax, [rdi+38h]
0x18001ef1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef21  mov     ebx, eax
0x18001ef23  lea     rcx, [rsp+1C8h+var_180]; this
0x18001ef28  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001ef2d  test    ebx, ebx
0x18001ef2f  jns     loc_18001EFE6
0x18001ef35  mov     rcx, [rsp+1C8h]; this
0x18001ef3d  mov     r9d, ebx; char *
0x18001ef40  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
0x18001ef47  mov     edx, 0FFh; void *
0x18001ef4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ef51  nop
0x18001ef52  mov     rcx, [rsp+1C8h+var_190]
0x18001ef57  test    rcx, rcx
0x18001ef5a  jz      short loc_18001EF69
0x18001ef5c  mov     rax, [rcx]
0x18001ef5f  mov     rax, [rax+10h]
0x18001ef63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef68  nop
0x18001ef69  mov     rcx, [rsp+1C8h+arg_10]
0x18001ef71  test    rcx, rcx
0x18001ef74  jz      short loc_18001EF83
0x18001ef76  mov     rax, [rcx]
0x18001ef79  mov     rax, [rax+10h]
0x18001ef7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef82  nop
0x18001ef83  mov     rcx, [rsp+1C8h+arg_18]
0x18001ef8b  test    rcx, rcx
0x18001ef8e  jz      short loc_18001EF9D
0x18001ef90  mov     rax, [rcx]
0x18001ef93  mov     rax, [rax+10h]
0x18001ef97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef9c  nop
0x18001ef9d  mov     rcx, [rsp+1C8h+var_198]
0x18001efa2  test    rcx, rcx
0x18001efa5  jz      short loc_18001EFB4
0x18001efa7  mov     rax, [rcx]
0x18001efaa  mov     rax, [rax+10h]
0x18001efae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efb3  nop
0x18001efb4  mov     rcx, [rsp+1C8h+var_188]
0x18001efb9  test    rcx, rcx
0x18001efbc  jz      short loc_18001EFCB
0x18001efbe  mov     rax, [rcx]
0x18001efc1  mov     rax, [rax+10h]
0x18001efc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efca  nop
0x18001efcb  mov     [rsp+1C8h+arg_8], sil
0x18001efd3  call    cs:__imp_CoUninitialize
0x18001efda  nop     dword ptr [rax+rax+00h]
0x18001efdf  mov     eax, ebx
0x18001efe1  jmp     loc_18001F403
0x18001efe6  mov     rbx, [rsp+1C8h+var_198]
0x18001efeb  mov     rdi, [rbx]
0x18001efee  mov     rcx, [rsp+1C8h+arg_18]
0x18001eff6  mov     [rsp+1C8h+arg_18], rsi
0x18001effe  test    rcx, rcx
0x18001f001  jz      short loc_18001F010
0x18001f003  mov     rax, [rcx]
0x18001f006  mov     rax, [rax+10h]
0x18001f00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f00f  nop
0x18001f010  mov     rdx, r15; unsigned __int16 *
0x18001f013  lea     rcx, [rsp+1C8h+var_180]; this
0x18001f018  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001f01d  nop
0x18001f01e  mov     rax, [rax]
0x18001f021  test    rax, rax
0x18001f024  jz      short loc_18001F02B
0x18001f026  mov     rdx, [rax]
0x18001f029  jmp     short loc_18001F02E
0x18001f02b  mov     rdx, rsi
0x18001f02e  lea     r8, [rsp+1C8h+arg_18]
0x18001f036  mov     rcx, rbx
0x18001f039  mov     rax, [rdi+48h]
0x18001f03d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f042  mov     ebx, eax
0x18001f044  lea     rcx, [rsp+1C8h+var_180]; this
0x18001f049  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001f04e  test    ebx, ebx
0x18001f050  jns     loc_18001F107
0x18001f056  mov     rcx, [rsp+1C8h]; this
0x18001f05e  mov     r9d, ebx; char *
0x18001f061  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
  ... truncated ...
```
