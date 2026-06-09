# DeletePolicyTask(int)

- ea: `0x18006d498`
- end: `0x18006da12`
- name: `?DeletePolicyTask@@YAJH@Z`
- size: `1402`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180036340`

## callees

- `0x1800525d4`
- `0x1800585e8`
- `0x18006d3c8`
- `0x18006d428`
- `0x18006d498`
- `0x18006da24`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006d508`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006d508`
- `OLEAUT32!__imp_VariantInit` at `0x18006d5df`
- `OLEAUT32!__imp_VariantInit` at `0x18006d5f6`
- `OLEAUT32!__imp_VariantInit` at `0x18006d60f`
- `OLEAUT32!__imp_VariantInit` at `0x18006d626`
- `OLEAUT32!__imp_VariantInit` at `0x18006d5df`
- `OLEAUT32!__imp_VariantInit` at `0x18006d5f6`
- `OLEAUT32!__imp_VariantInit` at `0x18006d60f`
- `OLEAUT32!__imp_VariantInit` at `0x18006d626`

## string_xrefs

- `0x18006d530`: `DeletePolicyTask failed 0x%x`
- `0x18006d562`: `DeletePolicyTask failed 0x%x`
- `0x18006d59b`: `StartTaskScheduler status: 0x%x`
- `0x18006d5be`: `StartTaskScheduler status: 0x%x`
- `0x18006d792`: `DeletePolicyTask %s folder does not exist. No tasks to delete.`
- `0x18006d7c7`: `DeletePolicyTask %s folder does not exist. No tasks to delete.`
- `0x18006d8cc`: `CDeletePolicyTask failed: 0x%x`
- `0x18006d8f2`: `CDeletePolicyTask failed: 0x%x`
- `0x18006d913`: `DeletePolicyTask task didn't exist. No task to delete.`
- `0x18006d936`: `DeletePolicyTask task didn't exist. No task to delete.`
- `0x18006d7f4`: `CDeletePolicyTask (GetFolder (gp)) failed: 0x%x`
- `0x18006d81a`: `CDeletePolicyTask (GetFolder (gp)) failed: 0x%x`
- `0x18006d95f`: `CDeletePolicyTask (GetFolder (root)) failed: 0x%x`
- `0x18006d987`: `CDeletePolicyTask (GetFolder (root)) failed: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall DeletePolicyTask(int a1)
{
  HRESULT v2; // ebx
  __int64 started; // r8
  LPVOID v4; // rdi
  __int64 (__fastcall *v5)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v6; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v8; // xmm8
  IRecordInfo *v9; // xmm9_8
  __int128 v10; // xmm6
  IRecordInfo *v11; // xmm7_8
  LPVOID v12; // rbx
  __int64 (__fastcall *v13)(LPVOID, __int64, __int64 *); // rdi
  _bstr_t *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rbx
  __int64 (__fastcall *v17)(__int64, __int64, __int64 *); // rdi
  _bstr_t *v18; // rax
  __int64 v19; // rdx
  void (*v20)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v21; // rdx
  __int64 v22; // rbx
  __int64 (__fastcall *v23)(__int64, __int64, _QWORD); // rdi
  _bstr_t *v24; // rax
  __int64 v25; // rdx
  _bstr_t *v26; // rax
  _BYTE v28[8]; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG v29; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG v30; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG v31; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int128 v34; // [rsp+A0h] [rbp-60h] BYREF
  IRecordInfo *v35; // [rsp+B0h] [rbp-50h]
  __int128 v36; // [rsp+C0h] [rbp-40h] BYREF
  IRecordInfo *v37; // [rsp+D0h] [rbp-30h]
  __int128 v38; // [rsp+E0h] [rbp-20h] BYREF
  IRecordInfo *v39; // [rsp+F0h] [rbp-10h]
  VARIANTARG v40; // [rsp+100h] [rbp+0h] BYREF
  __int64 v41; // [rsp+1B8h] [rbp+B8h] BYREF
  LPVOID ppv; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v43; // [rsp+1C8h] [rbp+C8h] BYREF

  ppv = 0;
  v41 = 0;
  v33 = 0;
  v2 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( v2 < 0 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"DeletePolicyTask failed 0x%x", (unsigned int)v2);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"DeletePolicyTask failed 0x%x", (unsigned int)v2);
      }
    }
    goto LABEL_66;
  }
  started = (unsigned int)StartTaskScheduler();
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"StartTaskScheduler status: 0x%x", started);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"StartTaskScheduler status: 0x%x", started);
    }
  }
  v4 = ppv;
  v5 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL);
  VariantInit(&pvarg);
  v6 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v31);
  v8 = *(_OWORD *)&v31.vt;
  v9 = v31.pRecInfo;
  VariantInit(&v30);
  v10 = *(_OWORD *)&v30.vt;
  v11 = v30.pRecInfo;
  VariantInit(&v29);
  v34 = v6;
  v35 = pRecInfo;
  v36 = v8;
  v37 = v9;
  v38 = v10;
  v39 = v11;
  v40 = v29;
  v2 = v5(v4, &v40, &v38, &v36, &v34);
  _variant_t::~_variant_t(&v29);
  _variant_t::~_variant_t(&v30);
  _variant_t::~_variant_t(&v31);
  _variant_t::~_variant_t(&pvarg);
  if ( v2 >= 0 )
  {
    v43 = 0;
    v12 = ppv;
    v13 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 56LL);
    v14 = _bstr_t::_bstr_t((_bstr_t *)v28, L"\\");
    if ( *(_QWORD *)v14 )
      v15 = **(_QWORD **)v14;
    else
      v15 = 0;
    v2 = v13(v12, v15, &v43);
    _bstr_t::_Free((_bstr_t *)v28);
    if ( v2 < 0 )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_65;
      v20 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"CDeletePolicyTask (GetFolder (root)) failed: 0x%x", (unsigned int)v2);
        goto LABEL_65;
      }
      v21 = L"CDeletePolicyTask (GetFolder (root)) failed: 0x%x";
    }
    else
    {
      v16 = v43;
      v17 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v43 + 72LL);
      v18 = _bstr_t::_bstr_t((_bstr_t *)v28, L"Microsoft\\Windows\\GroupPolicy");
      if ( *(_QWORD *)v18 )
        v19 = **(_QWORD **)v18;
      else
        v19 = 0;
      v2 = v17(v16, v19, &v41);
      _bstr_t::_Free((_bstr_t *)v28);
      if ( v2 < 0 )
      {
        if ( (unsigned int)(v2 + 2147024894) <= 1 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(
                4u,
                L"DeletePolicyTask %s folder does not exist. No tasks to delete.",
                L"Microsoft\\Windows\\GroupPolicy");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(
                4u,
                L"DeletePolicyTask %s folder does not exist. No tasks to delete.",
                L"Microsoft\\Windows\\GroupPolicy");
            }
          }
LABEL_57:
          v2 = 0;
          goto LABEL_65;
        }
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v20 = g_lpDebugMsg;
          if ( !g_lpDebugMsg )
          {
            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              RedirectDebugMsg(2u, L"CDeletePolicyTask (GetFolder (gp)) failed: 0x%x", (unsigned int)v2);
            goto LABEL_65;
          }
          v21 = L"CDeletePolicyTask (GetFolder (gp)) failed: 0x%x";
          goto LABEL_61;
        }
LABEL_65:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
        goto LABEL_66;
      }
      v22 = v41;
      v23 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v41 + 120LL);
      if ( a1 )
      {
        v24 = _bstr_t::_bstr_t((_bstr_t *)v28, L"{3E0A038B-D834-4930-9981-E89C9BFF83AA}");
        if ( *(_QWORD *)v24 )
          v25 = **(_QWORD **)v24;
        else
          v25 = 0;
      }
      else
      {
        v26 = _bstr_t::_bstr_t((_bstr_t *)v28, L"{A7719E0F-10DB-4640-AD8C-490CC6AD5202}");
        if ( *(_QWORD *)v26 )
          v25 = **(_QWORD **)v26;
        else
          v25 = 0;
      }
      v2 = v23(v22, v25, 0);
      _bstr_t::_Free((_bstr_t *)v28);
      if ( v2 >= 0 )
        goto LABEL_65;
      if ( v2 == -2147024894 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"DeletePolicyTask task didn't exist. No task to delete.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"DeletePolicyTask task didn't exist. No task to delete.");
          }
        }
        goto LABEL_57;
      }
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_65;
      v20 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"CDeletePolicyTask failed: 0x%x", (unsigned int)v2);
        goto LABEL_65;
      }
      v21 = L"CDeletePolicyTask failed: 0x%x";
    }
LABEL_61:
    v20(2u, v21, (unsigned int)v2);
    goto LABEL_65;
  }
LABEL_66:
  if ( v41 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18006d498  mov     rax, rsp
0x18006d49b  mov     [rax+8], rbx
0x18006d49f  push    rbp
0x18006d4a0  push    rsi
0x18006d4a1  push    rdi
0x18006d4a2  push    r14
0x18006d4a4  push    r15
0x18006d4a6  lea     rbp, [rsp-80h]
0x18006d4ab  sub     rsp, 180h
0x18006d4b2  movaps  xmmword ptr [rax-38h], xmm6
0x18006d4b6  movaps  xmmword ptr [rax-48h], xmm7
0x18006d4ba  movaps  xmmword ptr [rax-58h], xmm8
0x18006d4bf  movaps  xmmword ptr [rax-68h], xmm9
0x18006d4c4  movaps  xmmword ptr [rax-78h], xmm10
0x18006d4c9  movaps  xmmword ptr [rax-88h], xmm11
0x18006d4d1  mov     esi, ecx
0x18006d4d3  xor     r14d, r14d
0x18006d4d6  mov     [rbp+0A0h+arg_10], r14
0x18006d4dd  mov     [rbp+0A0h+arg_8], r14
0x18006d4e4  mov     [rbp+0A0h+var_108], r14
0x18006d4e8  lea     rax, [rbp+0A0h+arg_10]
0x18006d4ef  mov     [rsp+1A0h+ppv], rax; ppv
0x18006d4f4  lea     r9, IID_ITaskService; riid
0x18006d4fb  xor     edx, edx; pUnkOuter
0x18006d4fd  lea     r8d, [r14+1]; dwClsContext
0x18006d501  lea     rcx, CLSID_TaskScheduler; rclsid
0x18006d508  call    cs:__imp_CoCreateInstance
0x18006d50e  mov     ebx, eax
0x18006d510  test    eax, eax
0x18006d512  jns     short loc_18006D578
0x18006d514  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18006d51b  jz      loc_18006D9A9
0x18006d521  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006d528  test    rax, rax
0x18006d52b  jz      short loc_18006D545
0x18006d52d  mov     r8d, ebx
0x18006d530  lea     rdx, aDeletepolicyta_0; "DeletePolicyTask failed 0x%x"
0x18006d537  lea     ecx, [r14+2]
0x18006d53b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d540  jmp     loc_18006D9A9
0x18006d545  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18006d54c  jz      loc_18006D9A9
0x18006d552  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006d559  jz      loc_18006D9A9
0x18006d55f  mov     r8d, ebx
0x18006d562  lea     rdx, aDeletepolicyta_0; "DeletePolicyTask failed 0x%x"
0x18006d569  mov     ecx, 2; unsigned int
0x18006d56e  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006d573  jmp     loc_18006D9A9
0x18006d578  call    ?StartTaskScheduler@@YAJXZ; StartTaskScheduler(void)
0x18006d57d  mov     r8d, eax
0x18006d580  mov     r15d, 4
0x18006d586  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18006d58d  jz      short loc_18006D5CD
0x18006d58f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006d596  test    rax, rax
0x18006d599  jz      short loc_18006D5AC
0x18006d59b  lea     rdx, aStarttasksched; "StartTaskScheduler status: 0x%x"
0x18006d5a2  mov     ecx, r15d
0x18006d5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d5aa  jmp     short loc_18006D5CD
0x18006d5ac  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18006d5b3  jz      short loc_18006D5CD
0x18006d5b5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006d5bc  jz      short loc_18006D5CD
0x18006d5be  lea     rdx, aStarttasksched; "StartTaskScheduler status: 0x%x"
0x18006d5c5  mov     ecx, r15d; unsigned int
0x18006d5c8  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006d5cd  mov     rdi, [rbp+0A0h+arg_10]
0x18006d5d4  mov     rax, [rdi]
0x18006d5d7  mov     rbx, [rax+50h]
0x18006d5db  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x18006d5df  call    cs:__imp_VariantInit
0x18006d5e5  nop
0x18006d5e6  movups  xmm10, xmmword ptr [rbp+0A0h+pvarg]
0x18006d5eb  movsd   xmm11, qword ptr [rbp+0A0h+pvarg+10h]
0x18006d5f1  lea     rcx, [rsp+1A0h+var_138]; pvarg
0x18006d5f6  call    cs:__imp_VariantInit
0x18006d5fc  nop
0x18006d5fd  movups  xmm8, xmmword ptr [rsp+1A0h+var_138]
0x18006d603  movsd   xmm9, qword ptr [rsp+1A0h+var_138+10h]
0x18006d60a  lea     rcx, [rsp+1A0h+var_150]; pvarg
0x18006d60f  call    cs:__imp_VariantInit
0x18006d615  nop
0x18006d616  movups  xmm6, xmmword ptr [rsp+1A0h+var_150]
0x18006d61b  movsd   xmm7, qword ptr [rsp+1A0h+var_150+10h]
0x18006d621  lea     rcx, [rsp+1A0h+var_168]; pvarg
0x18006d626  call    cs:__imp_VariantInit
0x18006d62c  nop
0x18006d62d  movups  xmm0, xmmword ptr [rsp+1A0h+var_168]
0x18006d632  movsd   xmm1, qword ptr [rsp+1A0h+var_168+10h]
0x18006d638  movaps  [rbp+0A0h+var_100], xmm10
0x18006d63d  movsd   [rbp+0A0h+var_F0], xmm11
0x18006d643  movaps  [rbp+0A0h+var_E0], xmm8
0x18006d648  movsd   [rbp+0A0h+var_D0], xmm9
0x18006d64e  movaps  [rbp+0A0h+var_C0], xmm6
0x18006d652  movsd   [rbp+0A0h+var_B0], xmm7
0x18006d657  movaps  [rbp+0A0h+var_A0], xmm0
0x18006d65b  movsd   [rbp+0A0h+var_90], xmm1
0x18006d660  lea     rax, [rbp+0A0h+var_100]
0x18006d664  mov     [rsp+1A0h+ppv], rax
0x18006d669  lea     r9, [rbp+0A0h+var_E0]
0x18006d66d  lea     r8, [rbp+0A0h+var_C0]
0x18006d671  lea     rdx, [rbp+0A0h+var_A0]
0x18006d675  mov     rcx, rdi
0x18006d678  mov     rax, rbx
0x18006d67b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d680  mov     ebx, eax
0x18006d682  lea     rcx, [rsp+1A0h+var_168]; this
0x18006d687  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006d68c  nop
0x18006d68d  lea     rcx, [rsp+1A0h+var_150]; this
0x18006d692  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006d697  nop
0x18006d698  lea     rcx, [rsp+1A0h+var_138]; this
0x18006d69d  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006d6a2  nop
0x18006d6a3  lea     rcx, [rbp+0A0h+pvarg]; this
0x18006d6a7  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006d6ac  test    ebx, ebx
0x18006d6ae  js      loc_18006D9A9
0x18006d6b4  mov     [rbp+0A0h+arg_18], r14
0x18006d6bb  mov     rbx, [rbp+0A0h+arg_10]
0x18006d6c2  mov     rax, [rbx]
0x18006d6c5  mov     rdi, [rax+38h]
0x18006d6c9  lea     rdx, asc_1800C3A8C; "\\"
0x18006d6d0  lea     rcx, [rsp+1A0h+var_170]; this
0x18006d6d5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006d6da  nop
0x18006d6db  mov     rdx, [rax]
0x18006d6de  test    rdx, rdx
0x18006d6e1  jz      short loc_18006D6E8
0x18006d6e3  mov     rdx, [rdx]
0x18006d6e6  jmp     short loc_18006D6EB
0x18006d6e8  mov     rdx, r14
0x18006d6eb  lea     r8, [rbp+0A0h+arg_18]
0x18006d6f2  mov     rcx, rbx
0x18006d6f5  mov     rax, rdi
0x18006d6f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d6fd  mov     ebx, eax
0x18006d6ff  lea     rcx, [rsp+1A0h+var_170]; this
0x18006d704  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18006d709  test    ebx, ebx
0x18006d70b  js      loc_18006D94A
0x18006d711  mov     rbx, [rbp+0A0h+arg_18]
0x18006d718  mov     rax, [rbx]
0x18006d71b  mov     rdi, [rax+48h]
0x18006d71f  lea     rdx, aMicrosoftWindo; "Microsoft\\Windows\\GroupPolicy"
0x18006d726  lea     rcx, [rsp+1A0h+var_170]; this
0x18006d72b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006d730  nop
0x18006d731  mov     rdx, [rax]
0x18006d734  test    rdx, rdx
0x18006d737  jz      short loc_18006D73E
0x18006d739  mov     rdx, [rdx]
0x18006d73c  jmp     short loc_18006D741
0x18006d73e  mov     rdx, r14
0x18006d741  lea     r8, [rbp+0A0h+arg_8]
0x18006d748  mov     rcx, rbx
0x18006d74b  mov     rax, rdi
0x18006d74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d753  mov     ebx, eax
0x18006d755  lea     rcx, [rsp+1A0h+var_170]; this
0x18006d75a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18006d75f  test    ebx, ebx
0x18006d761  jns     loc_18006D826
0x18006d767  lea     eax, [rbx+7FF8FFFEh]
0x18006d76d  cmp     eax, 1
0x18006d770  ja      short loc_18006D7DB
0x18006d772  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18006d779  jz      loc_18006D945
0x18006d77f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006d786  test    rax, rax
0x18006d789  jz      short loc_18006D7A6
0x18006d78b  lea     r8, aMicrosoftWindo; "Microsoft\\Windows\\GroupPolicy"
0x18006d792  lea     rdx, aDeletepolicyta_1; "DeletePolicyTask %s folder does not exi"...
0x18006d799  mov     ecx, r15d
0x18006d79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d7a1  jmp     loc_18006D945
0x18006d7a6  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18006d7ad  jz      loc_18006D945
0x18006d7b3  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006d7ba  jz      loc_18006D945
0x18006d7c0  lea     r8, aMicrosoftWindo; "Microsoft\\Windows\\GroupPolicy"
0x18006d7c7  lea     rdx, aDeletepolicyta_1; "DeletePolicyTask %s folder does not exi"...
0x18006d7ce  mov     ecx, r15d; unsigned int
0x18006d7d1  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006d7d6  jmp     loc_18006D945
0x18006d7db  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18006d7e2  jz      loc_18006D99C
0x18006d7e8  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006d7ef  test    rax, rax
0x18006d7f2  jz      short loc_18006D800
0x18006d7f4  lea     rdx, aCdeletepolicyt_1; "CDeletePolicyTask (GetFolder (gp)) fail"...
0x18006d7fb  jmp     loc_18006D966
0x18006d800  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18006d807  jz      loc_18006D99C
0x18006d80d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006d814  jz      loc_18006D99C
0x18006d81a  lea     rdx, aCdeletepolicyt_1; "CDeletePolicyTask (GetFolder (gp)) fail"...
0x18006d821  jmp     loc_18006D98E
0x18006d826  mov     rbx, [rbp+0A0h+arg_8]
0x18006d82d  lea     rcx, [rsp+1A0h+var_170]; this
0x18006d832  mov     rax, [rbx]
0x18006d835  mov     rdi, [rax+78h]
0x18006d839  test    esi, esi
0x18006d83b  jz      short loc_18006D86C
0x18006d83d  lea     rdx, a3e0a038bD83449; "{3E0A038B-D834-4930-9981-E89C9BFF83AA}"
0x18006d844  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006d849  nop
0x18006d84a  mov     rdx, [rax]
0x18006d84d  test    rdx, rdx
0x18006d850  jz      short loc_18006D857
0x18006d852  mov     rdx, [rdx]
0x18006d855  jmp     short loc_18006D85A
0x18006d857  mov     rdx, r14
0x18006d85a  xor     r8d, r8d
0x18006d85d  mov     rcx, rbx
0x18006d860  mov     rax, rdi
0x18006d863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d868  mov     ebx, eax
0x18006d86a  jmp     short loc_18006D899
0x18006d86c  lea     rdx, aA7719e0f10db46; "{A7719E0F-10DB-4640-AD8C-490CC6AD5202}"
0x18006d873  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006d878  nop
0x18006d879  mov     rdx, [rax]
0x18006d87c  test    rdx, rdx
0x18006d87f  jz      short loc_18006D886
0x18006d881  mov     rdx, [rdx]
0x18006d884  jmp     short loc_18006D889
0x18006d886  mov     rdx, r14
0x18006d889  xor     r8d, r8d
0x18006d88c  mov     rcx, rbx
0x18006d88f  mov     rax, rdi
0x18006d892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d897  mov     ebx, eax
0x18006d899  lea     rcx, [rsp+1A0h+var_170]; this
0x18006d89e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18006d8a3  test    ebx, ebx
0x18006d8a5  jns     loc_18006D99C
0x18006d8ab  cmp     ebx, 80070002h
0x18006d8b1  jz      short loc_18006D8FE
0x18006d8b3  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18006d8ba  jz      loc_18006D99C
0x18006d8c0  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006d8c7  test    rax, rax
0x18006d8ca  jz      short loc_18006D8D8
0x18006d8cc  lea     rdx, aCdeletepolicyt; "CDeletePolicyTask failed: 0x%x"
0x18006d8d3  jmp     loc_18006D966
0x18006d8d8  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18006d8df  jz      loc_18006D99C
0x18006d8e5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006d8ec  jz      loc_18006D99C
0x18006d8f2  lea     rdx, aCdeletepolicyt; "CDeletePolicyTask failed: 0x%x"
0x18006d8f9  jmp     loc_18006D98E
0x18006d8fe  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18006d905  jz      short loc_18006D945
0x18006d907  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006d90e  test    rax, rax
0x18006d911  jz      short loc_18006D924
0x18006d913  lea     rdx, aDeletepolicyta; "DeletePolicyTask task didn't exist. No "...
0x18006d91a  mov     ecx, r15d
0x18006d91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d922  jmp     short loc_18006D945
0x18006d924  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18006d92b  jz      short loc_18006D945
0x18006d92d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006d934  jz      short loc_18006D945
0x18006d936  lea     rdx, aDeletepolicyta; "DeletePolicyTask task didn't exist. No "...
0x18006d93d  mov     ecx, r15d; unsigned int
0x18006d940  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006d945  mov     ebx, r14d
0x18006d948  jmp     short loc_18006D99C
0x18006d94a  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18006d951  jz      short loc_18006D99C
0x18006d953  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006d95a  test    rax, rax
0x18006d95d  jz      short loc_18006D975
0x18006d95f  lea     rdx, aCdeletepolicyt_0; "CDeletePolicyTask (GetFolder (root)) fa"...
0x18006d966  mov     r8d, ebx
0x18006d969  mov     ecx, 2
0x18006d96e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d973  jmp     short loc_18006D99C
0x18006d975  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18006d97c  jz      short loc_18006D99C
0x18006d97e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006d985  jz      short loc_18006D99C
0x18006d987  lea     rdx, aCdeletepolicyt_0; "CDeletePolicyTask (GetFolder (root)) fa"...
0x18006d98e  mov     r8d, ebx
0x18006d991  mov     ecx, 2; unsigned int
0x18006d996  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006d99b  nop
0x18006d99c  lea     rcx, [rbp+0A0h+arg_18]
0x18006d9a3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006d9a8  nop
0x18006d9a9  mov     rcx, [rbp+0A0h+arg_8]
0x18006d9b0  test    rcx, rcx
0x18006d9b3  jz      short loc_18006D9C2
0x18006d9b5  mov     rax, [rcx]
0x18006d9b8  mov     rax, [rax+10h]
  ... truncated ...
```
