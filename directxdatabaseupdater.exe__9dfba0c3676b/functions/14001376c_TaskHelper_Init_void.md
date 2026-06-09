# TaskHelper::Init(void)

- ea: `0x14001376c`
- end: `0x140013d07`
- name: `?Init@TaskHelper@@AEAAJXZ`
- size: `1435`
- prototype: `__int64 __fastcall(LPVOID *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400136f0`
- `0x140013f5c`

## callees

- `0x140003218`
- `0x140005cac`
- `0x14000a4bc`
- `0x14000a4e0`
- `0x1400135c0`
- `0x14001376c`
- `0x140013fe0`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400137eb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400137eb`
- `OLEAUT32!__imp_SysFreeString` at `0x14001398a`
- `OLEAUT32!__imp_SysFreeString` at `0x140013a5b`
- `OLEAUT32!__imp_SysFreeString` at `0x14001398a`
- `OLEAUT32!__imp_SysFreeString` at `0x140013a5b`
- `OLEAUT32!__imp_VariantInit` at `0x140013828`
- `OLEAUT32!__imp_VariantInit` at `0x140013840`
- `OLEAUT32!__imp_VariantInit` at `0x140013859`
- `OLEAUT32!__imp_VariantInit` at `0x140013870`
- `OLEAUT32!__imp_VariantInit` at `0x140013828`
- `OLEAUT32!__imp_VariantInit` at `0x140013840`
- `OLEAUT32!__imp_VariantInit` at `0x140013859`
- `OLEAUT32!__imp_VariantInit` at `0x140013870`
- `OLEAUT32!__imp_VariantClear` at `0x1400138d1`
- `OLEAUT32!__imp_VariantClear` at `0x1400138dd`
- `OLEAUT32!__imp_VariantClear` at `0x1400138e9`
- `OLEAUT32!__imp_VariantClear` at `0x1400138f5`
- `OLEAUT32!__imp_VariantClear` at `0x1400138d1`
- `OLEAUT32!__imp_VariantClear` at `0x1400138dd`
- `OLEAUT32!__imp_VariantClear` at `0x1400138e9`
- `OLEAUT32!__imp_VariantClear` at `0x1400138f5`

## string_xrefs

- `0x1400137fc`: `onecore\windows\directx\database\updater\exe\taskschedulerhelper.cpp`
- `0x1400139bc`: `onecore\windows\directx\database\updater\exe\taskschedulerhelper.cpp`
- `0x140013ad9`: `onecore\windows\directx\database\updater\exe\taskschedulerhelper.cpp`
- `0x140013b4e`: `onecore\windows\directx\database\updater\exe\taskschedulerhelper.cpp`
- `0x140013c7a`: `onecore\windows\directx\database\updater\exe\taskschedulerhelper.cpp`
- `0x140013ca7`: `onecore\windows\directx\database\updater\exe\taskschedulerhelper.cpp`
- `0x140013a00`: `DirectXDatabaseUpdater`

## pseudocode

```c
__int64 __fastcall TaskHelper::Init(LPVOID *this)
{
  LPVOID v2; // rcx
  HRESULT Instance; // ebx
  __int64 v4; // rdx
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v8; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v10; // xmm8
  IRecordInfo *v11; // xmm9_8
  __int128 v12; // xmm6
  IRecordInfo *v13; // xmm7_8
  LPVOID v14; // rbx
  __int64 (__fastcall *v15)(LPVOID, __int64, LPVOID *); // r14
  char *v16; // rdi
  LPVOID v17; // rcx
  _bstr_t *v18; // rax
  __int64 v19; // rdx
  unsigned __int64 v20; // rdx
  int v21; // r14d
  BSTR *v22; // rbx
  BSTR v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rbx
  __int64 (__fastcall *v26)(__int64, __int64, LPVOID *); // r14
  LPVOID v27; // rcx
  _bstr_t *v28; // rax
  __int64 v29; // rdx
  unsigned __int64 v30; // rdx
  BSTR *v31; // rbx
  BSTR v32; // rcx
  LPVOID v33; // rdi
  __int64 (__fastcall *v34)(LPVOID, LPVOID *); // r14
  __int64 **v35; // rbx
  LPVOID v36; // rcx
  int v37; // eax
  unsigned int v38; // edi
  __int64 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  __int64 v42; // rdx
  int v43; // r14d
  __int64 v44; // rax
  int v45; // eax
  void *v46; // rdi
  int (__fastcall *v47)(void *, GUID *, void **); // rbx
  void *v48; // rcx
  LPVOID v49; // rbx
  unsigned int *ppv; // [rsp+20h] [rbp-E0h]
  VARIANTARG v51; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG v52; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG v53; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v55[4]; // [rsp+90h] [rbp-70h] BYREF
  IRecordInfo *v56; // [rsp+A0h] [rbp-60h]
  __int128 v57; // [rsp+B0h] [rbp-50h] BYREF
  IRecordInfo *v58; // [rsp+C0h] [rbp-40h]
  __int128 v59; // [rsp+D0h] [rbp-30h] BYREF
  IRecordInfo *v60; // [rsp+E0h] [rbp-20h]
  VARIANTARG v61; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]
  int v63; // [rsp+1B0h] [rbp+B0h] BYREF
  void *v64; // [rsp+1B8h] [rbp+B8h] BYREF
  void *v65; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 *v66; // [rsp+1C8h] [rbp+C8h] BYREF

  v2 = *this;
  if ( !v2 || !this[4] )
  {
    *this = 0;
    if ( v2 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v2 + 16LL))(v2);
    Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, this);
    if ( Instance < 0 )
    {
      v4 = 10;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v4,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\taskschedulerhelper.cpp",
        (const char *)(unsigned int)Instance,
        (int)ppv);
      return (unsigned int)Instance;
    }
    v6 = *this;
    v7 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)*this + 80LL);
    VariantInit(&pvarg);
    v8 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v53);
    v10 = *(_OWORD *)&v53.vt;
    v11 = v53.pRecInfo;
    VariantInit(&v52);
    v12 = *(_OWORD *)&v52.vt;
    v13 = v52.pRecInfo;
    VariantInit(&v51);
    *(_OWORD *)v55 = v8;
    v56 = pRecInfo;
    v57 = v10;
    v58 = v11;
    v59 = v12;
    v60 = v13;
    v61 = v51;
    ppv = v55;
    Instance = v7(v6, &v61, &v59, &v57);
    VariantClear(&v51);
    VariantClear(&v52);
    VariantClear(&v53);
    VariantClear(&pvarg);
    if ( Instance < 0 )
    {
      v4 = 11;
      goto LABEL_7;
    }
    v14 = *this;
    v15 = *(__int64 (__fastcall **)(LPVOID, __int64, LPVOID *))(*(_QWORD *)*this + 56LL);
    v16 = (char *)(this + 1);
    v17 = this[1];
    this[1] = 0;
    if ( v17 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    v18 = _bstr_t::_bstr_t((_bstr_t *)&v65, L"\\Microsoft\\Windows\\DirectX");
    if ( *(_QWORD *)v18 )
      v19 = **(_QWORD **)v18;
    else
      v19 = 0;
    v21 = v15(v14, v19, this + 1);
    v22 = (BSTR *)v65;
    if ( v65 && _InterlockedExchangeAdd((volatile signed __int32 *)v65 + 4, 0xFFFFFFFF) == 1 && v22 )
    {
      if ( *v22 )
      {
        SysFreeString(*v22);
        *v22 = 0;
      }
      v23 = v22[1];
      if ( v23 )
      {
        operator delete(v23, v20);
        v22[1] = 0;
      }
      operator delete(v22, 0x18u);
    }
    if ( v21 < 0 )
    {
      v24 = 14;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\taskschedulerhelper.cpp",
        (const char *)(unsigned int)v21,
        (int)v55);
      return (unsigned int)v21;
    }
    v25 = *(_QWORD *)v16;
    v26 = *(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(**(_QWORD **)v16 + 104LL);
    v27 = this[2];
    this[2] = 0;
    if ( v27 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
    v28 = _bstr_t::_bstr_t((_bstr_t *)&v65, L"DirectXDatabaseUpdater");
    if ( *(_QWORD *)v28 )
      v29 = **(_QWORD **)v28;
    else
      v29 = 0;
    v21 = v26(v25, v29, this + 2);
    v31 = (BSTR *)v65;
    if ( v65 && _InterlockedExchangeAdd((volatile signed __int32 *)v65 + 4, 0xFFFFFFFF) == 1 && v31 )
    {
      if ( *v31 )
      {
        SysFreeString(*v31);
        *v31 = 0;
      }
      v32 = v31[1];
      if ( v32 )
      {
        operator delete(v32, v30);
        v31[1] = 0;
      }
      operator delete(v31, 0x18u);
    }
    if ( v21 < 0 )
    {
      v24 = 16;
      goto LABEL_26;
    }
    v33 = this[2];
    v34 = *(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v33 + 152LL);
    v35 = (__int64 **)(this + 3);
    v36 = this[3];
    this[3] = 0;
    if ( v36 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
    v37 = v34(v33, this + 3);
    v38 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\taskschedulerhelper.cpp",
        (const char *)(unsigned int)v37,
        (int)v55);
      return v38;
    }
    v66 = 0;
    v39 = *v35;
    v40 = **v35;
    v66 = 0;
    v41 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v40 + 72))(v39, &v66);
    Instance = v41;
    if ( v41 < 0 )
    {
      v42 = 21;
      goto LABEL_50;
    }
    v63 = 0;
    v41 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v66 + 56))(v66, &v63);
    Instance = v41;
    if ( v41 < 0 )
    {
      v42 = 24;
LABEL_50:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v42,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\taskschedulerhelper.cpp",
        (const char *)(unsigned int)v41,
        (int)v55);
LABEL_63:
      wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v66);
      return (unsigned int)Instance;
    }
    v43 = 0;
    while ( v43 < v63 )
    {
      v65 = 0;
      v44 = *v66;
      v65 = 0;
      v45 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, void **))(v44 + 64))(v66, (unsigned int)++v43, &v65);
      Instance = v45;
      if ( v45 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D,
          (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\taskschedulerhelper.cpp",
          (const char *)(unsigned int)v45,
          (int)v55);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v65);
        goto LABEL_63;
      }
      v64 = 0;
      v46 = v65;
      v47 = **(int (__fastcall ***)(void *, GUID *, void **))v65;
      wil::com_ptr_t<ILogonTrigger,wil::err_exception_policy>::reset(&v64);
      if ( v47(v46, &GUID_72dade38_fae4_4b3e_baf4_5d009af02b1c, &v64) >= 0 )
      {
        v48 = v64;
        v49 = this[4];
        this[4] = v64;
        if ( v48 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v48 + 8LL))(v48);
        if ( v49 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v49 + 16LL))(v49);
        wil::com_ptr_t<ILogonTrigger,wil::err_exception_policy>::reset(&v64);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v64);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v65);
        break;
      }
      wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v64);
      wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v65);
    }
    if ( !this[4] )
    {
      Instance = wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)0x2A,
                   (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\taskschedulerhelper.cpp",
                   (const char *)2,
                   (unsigned int)v55);
      goto LABEL_63;
    }
    wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v66);
  }
  return 0;
}

```

## disassembly

```asm
0x14001376c  mov     rax, rsp
0x14001376f  push    rbp
0x140013770  push    rbx
0x140013771  push    rsi
0x140013772  push    rdi
0x140013773  push    r14
0x140013775  push    r15
0x140013777  lea     rbp, [rsp-78h]
0x14001377c  sub     rsp, 178h
0x140013783  movaps  xmmword ptr [rax-48h], xmm6
0x140013787  movaps  xmmword ptr [rax-58h], xmm7
0x14001378b  movaps  xmmword ptr [rax-68h], xmm8
0x140013790  movaps  xmmword ptr [rax-78h], xmm9
0x140013795  movaps  xmmword ptr [rax-88h], xmm10
0x14001379d  movaps  xmmword ptr [rax-98h], xmm11
0x1400137a5  mov     rsi, rcx
0x1400137a8  mov     rcx, [rcx]
0x1400137ab  xor     r15d, r15d
0x1400137ae  test    rcx, rcx
0x1400137b1  jz      short loc_1400137BD
0x1400137b3  cmp     [rsi+20h], r15
0x1400137b7  jnz     loc_140013CD3
0x1400137bd  mov     [rsi], r15
0x1400137c0  test    rcx, rcx
0x1400137c3  jz      short loc_1400137D2
0x1400137c5  mov     rax, [rcx]
0x1400137c8  mov     rax, [rax+10h]
0x1400137cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400137d1  nop
0x1400137d2  mov     [rsp+1A0h+ppv], rsi; int
0x1400137d7  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1400137de  xor     edx, edx; pUnkOuter
0x1400137e0  lea     r8d, [rdx+1]; dwClsContext
0x1400137e4  lea     rcx, CLSID_TaskScheduler; rclsid
0x1400137eb  call    cs:__imp_CoCreateInstance
0x1400137f1  mov     ebx, eax
0x1400137f3  test    eax, eax
0x1400137f5  jns     short loc_140013819
0x1400137f7  mov     edx, 0Ah; void *
0x1400137fc  lea     r8, aOnecoreWindows_0; "onecore\\windows\\directx\\database\\up"...
0x140013803  mov     r9d, ebx; char *
0x140013806  mov     rcx, [rbp+0A8h]; this
0x14001380d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013812  mov     eax, ebx
0x140013814  jmp     loc_140013CD5
0x140013819  mov     rdi, [rsi]
0x14001381c  mov     rax, [rdi]
0x14001381f  mov     rbx, [rax+50h]
0x140013823  lea     rcx, [rsp+1A0h+pvarg]; pvarg
0x140013828  call    cs:__imp_VariantInit
0x14001382e  nop
0x14001382f  movups  xmm10, xmmword ptr [rsp+1A0h+pvarg]
0x140013835  movsd   xmm11, qword ptr [rbp+0A0h+pvarg+10h]
0x14001383b  lea     rcx, [rsp+1A0h+var_140]; pvarg
0x140013840  call    cs:__imp_VariantInit
0x140013846  nop
0x140013847  movups  xmm8, xmmword ptr [rsp+1A0h+var_140]
0x14001384d  movsd   xmm9, qword ptr [rsp+1A0h+var_140+10h]
0x140013854  lea     rcx, [rsp+1A0h+var_158]; pvarg
0x140013859  call    cs:__imp_VariantInit
0x14001385f  nop
0x140013860  movups  xmm6, xmmword ptr [rsp+1A0h+var_158]
0x140013865  movsd   xmm7, qword ptr [rsp+1A0h+var_158+10h]
0x14001386b  lea     rcx, [rsp+1A0h+var_170]; pvarg
0x140013870  call    cs:__imp_VariantInit
0x140013876  nop
0x140013877  movups  xmm0, xmmword ptr [rsp+1A0h+var_170]
0x14001387c  movsd   xmm1, qword ptr [rsp+1A0h+var_170+10h]
0x140013882  movaps  xmmword ptr [rbp+0A0h+var_110], xmm10
0x140013887  movsd   [rbp+0A0h+var_100], xmm11
0x14001388d  movaps  [rbp+0A0h+var_F0], xmm8
0x140013892  movsd   [rbp+0A0h+var_E0], xmm9
0x140013898  movaps  [rbp+0A0h+var_D0], xmm6
0x14001389c  movsd   [rbp+0A0h+var_C0], xmm7
0x1400138a1  movaps  [rbp+0A0h+var_B0], xmm0
0x1400138a5  movsd   [rbp+0A0h+var_A0], xmm1
0x1400138aa  lea     rax, [rbp+0A0h+var_110]
0x1400138ae  mov     [rsp+1A0h+ppv], rax; int
0x1400138b3  lea     r9, [rbp+0A0h+var_F0]
0x1400138b7  lea     r8, [rbp+0A0h+var_D0]
0x1400138bb  lea     rdx, [rbp+0A0h+var_B0]
0x1400138bf  mov     rcx, rdi
0x1400138c2  mov     rax, rbx
0x1400138c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400138ca  mov     ebx, eax
0x1400138cc  lea     rcx, [rsp+1A0h+var_170]; pvarg
0x1400138d1  call    cs:__imp_VariantClear
0x1400138d7  nop
0x1400138d8  lea     rcx, [rsp+1A0h+var_158]; pvarg
0x1400138dd  call    cs:__imp_VariantClear
0x1400138e3  nop
0x1400138e4  lea     rcx, [rsp+1A0h+var_140]; pvarg
0x1400138e9  call    cs:__imp_VariantClear
0x1400138ef  nop
0x1400138f0  lea     rcx, [rsp+1A0h+pvarg]; pvarg
0x1400138f5  call    cs:__imp_VariantClear
0x1400138fb  test    ebx, ebx
0x1400138fd  jns     short loc_140013909
0x1400138ff  mov     edx, 0Bh
0x140013904  jmp     loc_1400137FC
0x140013909  mov     rbx, [rsi]
0x14001390c  mov     rax, [rbx]
0x14001390f  mov     r14, [rax+38h]
0x140013913  lea     rdi, [rsi+8]
0x140013917  mov     rcx, [rdi]
0x14001391a  mov     [rdi], r15
0x14001391d  test    rcx, rcx
0x140013920  jz      short loc_14001392F
0x140013922  mov     rax, [rcx]
0x140013925  mov     rax, [rax+10h]
0x140013929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001392e  nop
0x14001392f  lea     rdx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\DirectX"
0x140013936  lea     rcx, [rbp+0A0h+arg_10]; this
0x14001393d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140013942  nop
0x140013943  mov     rcx, [rax]
0x140013946  test    rcx, rcx
0x140013949  jz      short loc_140013950
0x14001394b  mov     rdx, [rcx]
0x14001394e  jmp     short loc_140013953
0x140013950  mov     rdx, r15
0x140013953  mov     r8, rdi
0x140013956  mov     rcx, rbx
0x140013959  mov     rax, r14
0x14001395c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013961  mov     r14d, eax
0x140013964  mov     rbx, [rbp+0A0h+arg_10]
0x14001396b  test    rbx, rbx
0x14001396e  jz      short loc_1400139B2
0x140013970  or      ecx, 0FFFFFFFFh
0x140013973  lock xadd [rbx+10h], ecx
0x140013978  cmp     ecx, 1
0x14001397b  jnz     short loc_1400139B2
0x14001397d  test    rbx, rbx
0x140013980  jz      short loc_1400139B2
0x140013982  mov     rcx, [rbx]; bstrString
0x140013985  test    rcx, rcx
0x140013988  jz      short loc_140013993
0x14001398a  call    cs:__imp_SysFreeString
0x140013990  mov     [rbx], r15
0x140013993  mov     rcx, [rbx+8]; void *
0x140013997  test    rcx, rcx
0x14001399a  jz      short loc_1400139A5
0x14001399c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400139a1  mov     [rbx+8], r15
0x1400139a5  mov     edx, 18h; unsigned __int64
0x1400139aa  mov     rcx, rbx; void *
0x1400139ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400139b2  test    r14d, r14d
0x1400139b5  jns     short loc_1400139DA
0x1400139b7  mov     edx, 0Eh; void *
0x1400139bc  lea     r8, aOnecoreWindows_0; "onecore\\windows\\directx\\database\\up"...
0x1400139c3  mov     r9d, r14d; char *
0x1400139c6  mov     rcx, [rbp+0A8h]; this
0x1400139cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400139d2  mov     eax, r14d
0x1400139d5  jmp     loc_140013CD5
0x1400139da  mov     rbx, [rdi]
0x1400139dd  mov     rax, [rbx]
0x1400139e0  mov     r14, [rax+68h]
0x1400139e4  lea     rdi, [rsi+10h]
0x1400139e8  mov     rcx, [rdi]
0x1400139eb  mov     [rdi], r15
0x1400139ee  test    rcx, rcx
0x1400139f1  jz      short loc_140013A00
0x1400139f3  mov     rax, [rcx]
0x1400139f6  mov     rax, [rax+10h]
0x1400139fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400139ff  nop
0x140013a00  lea     rdx, aDirectxdatabas; "DirectXDatabaseUpdater"
0x140013a07  lea     rcx, [rbp+0A0h+arg_10]; this
0x140013a0e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140013a13  nop
0x140013a14  mov     rcx, [rax]
0x140013a17  test    rcx, rcx
0x140013a1a  jz      short loc_140013A21
0x140013a1c  mov     rdx, [rcx]
0x140013a1f  jmp     short loc_140013A24
0x140013a21  mov     rdx, r15
0x140013a24  mov     r8, rdi
0x140013a27  mov     rcx, rbx
0x140013a2a  mov     rax, r14
0x140013a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013a32  mov     r14d, eax
0x140013a35  mov     rbx, [rbp+0A0h+arg_10]
0x140013a3c  test    rbx, rbx
0x140013a3f  jz      short loc_140013A83
0x140013a41  or      ecx, 0FFFFFFFFh
0x140013a44  lock xadd [rbx+10h], ecx
0x140013a49  cmp     ecx, 1
0x140013a4c  jnz     short loc_140013A83
0x140013a4e  test    rbx, rbx
0x140013a51  jz      short loc_140013A83
0x140013a53  mov     rcx, [rbx]; bstrString
0x140013a56  test    rcx, rcx
0x140013a59  jz      short loc_140013A64
0x140013a5b  call    cs:__imp_SysFreeString
0x140013a61  mov     [rbx], r15
0x140013a64  mov     rcx, [rbx+8]; void *
0x140013a68  test    rcx, rcx
0x140013a6b  jz      short loc_140013A76
0x140013a6d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140013a72  mov     [rbx+8], r15
0x140013a76  mov     edx, 18h; unsigned __int64
0x140013a7b  mov     rcx, rbx; void *
0x140013a7e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140013a83  test    r14d, r14d
0x140013a86  jns     short loc_140013A92
0x140013a88  mov     edx, 10h
0x140013a8d  jmp     loc_1400139BC
0x140013a92  mov     rdi, [rdi]
0x140013a95  mov     rax, [rdi]
0x140013a98  mov     r14, [rax+98h]
0x140013a9f  lea     rbx, [rsi+18h]
0x140013aa3  mov     rcx, [rbx]
0x140013aa6  mov     [rbx], r15
0x140013aa9  test    rcx, rcx
0x140013aac  jz      short loc_140013ABB
0x140013aae  mov     rdx, [rcx]
0x140013ab1  mov     rax, [rdx+10h]
0x140013ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013aba  nop
0x140013abb  mov     rdx, rbx
0x140013abe  mov     rcx, rdi
0x140013ac1  mov     rax, r14
0x140013ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013ac9  mov     edi, eax
0x140013acb  test    eax, eax
0x140013acd  jns     short loc_140013AF1
0x140013acf  mov     rcx, [rbp+0A8h]; this
0x140013ad6  mov     r9d, eax; char *
0x140013ad9  lea     r8, aOnecoreWindows_0; "onecore\\windows\\directx\\database\\up"...
0x140013ae0  mov     edx, 12h; void *
0x140013ae5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013aea  mov     eax, edi
0x140013aec  jmp     loc_140013CD5
0x140013af1  mov     [rbp+0A0h+arg_18], r15
0x140013af8  mov     rcx, [rbx]
0x140013afb  mov     rax, [rcx]
0x140013afe  mov     [rbp+0A0h+arg_18], r15
0x140013b05  lea     rdx, [rbp+0A0h+arg_18]
0x140013b0c  mov     rax, [rax+48h]
0x140013b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013b15  mov     ebx, eax
0x140013b17  test    eax, eax
0x140013b19  jns     short loc_140013B22
0x140013b1b  mov     edx, 15h
0x140013b20  jmp     short loc_140013B4E
0x140013b22  mov     [rbp+0A0h+arg_0], r15d
0x140013b29  mov     rcx, [rbp+0A0h+arg_18]
0x140013b30  mov     rax, [rcx]
0x140013b33  lea     rdx, [rbp+0A0h+arg_0]
0x140013b3a  mov     rax, [rax+38h]
0x140013b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013b43  mov     ebx, eax
0x140013b45  test    eax, eax
0x140013b47  jns     short loc_140013B69
0x140013b49  mov     edx, 18h; void *
0x140013b4e  lea     r8, aOnecoreWindows_0; "onecore\\windows\\directx\\database\\up"...
0x140013b55  mov     r9d, eax; char *
0x140013b58  mov     rcx, [rbp+0A8h]; this
0x140013b5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013b64  jmp     loc_140013C8C
0x140013b69  mov     r14d, r15d
0x140013b6c  cmp     r14d, [rbp+0A0h+arg_0]
0x140013b73  jge     loc_140013C67
0x140013b79  mov     [rbp+0A0h+arg_10], r15
0x140013b80  mov     rcx, [rbp+0A0h+arg_18]
0x140013b87  mov     rax, [rcx]
0x140013b8a  mov     [rbp+0A0h+arg_10], r15
0x140013b91  inc     r14d
0x140013b94  lea     r8, [rbp+0A0h+arg_10]
0x140013b9b  mov     edx, r14d
0x140013b9e  mov     rax, [rax+40h]
0x140013ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013ba7  mov     ebx, eax
0x140013ba9  test    eax, eax
0x140013bab  js      loc_140013C9D
0x140013bb1  mov     [rbp+0A0h+arg_8], r15
0x140013bb8  mov     rdi, [rbp+0A0h+arg_10]
0x140013bbf  mov     rax, [rdi]
0x140013bc2  mov     rbx, [rax]
0x140013bc5  lea     rcx, [rbp+0A0h+arg_8]
0x140013bcc  call    ?reset@?$com_ptr_t@UILogonTrigger@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<ILogonTrigger,wil::err_exception_policy>::reset(void)
0x140013bd1  lea     r8, [rbp+0A0h+arg_8]
0x140013bd8  lea     rdx, _GUID_72dade38_fae4_4b3e_baf4_5d009af02b1c
0x140013bdf  mov     rcx, rdi
0x140013be2  mov     rax, rbx
0x140013be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013bea  test    eax, eax
0x140013bec  jns     short loc_140013C0C
0x140013bee  lea     rcx, [rbp+0A0h+arg_8]
0x140013bf5  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x140013bfa  nop
0x140013bfb  lea     rcx, [rbp+0A0h+arg_10]
0x140013c02  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x140013c07  jmp     loc_140013B6C
0x140013c0c  mov     rcx, [rbp+0A0h+arg_8]
0x140013c13  mov     rbx, [rsi+20h]
  ... truncated ...
```
