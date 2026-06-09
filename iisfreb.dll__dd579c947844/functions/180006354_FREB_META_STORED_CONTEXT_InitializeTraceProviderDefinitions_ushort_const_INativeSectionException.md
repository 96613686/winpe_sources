# FREB_META_STORED_CONTEXT::InitializeTraceProviderDefinitions(ushort const *,INativeSectionException * *)

- ea: `0x180006354`
- end: `0x18000688e`
- name: `?InitializeTraceProviderDefinitions@FREB_META_STORED_CONTEXT@@AEAAJPEBGPEAPEAVINativeSectionException@@@Z`
- size: `1338`
- prototype: `__int64 __fastcall(FREB_META_STORED_CONTEXT *__hidden this, const unsigned __int16 *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180005b28`

## callees

- `0x180001008`
- `0x18000594c`
- `0x180006354`
- `0x18000795c`
- `0x18000b010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800066aa`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800066aa`
- `iisutil!PuDbgPrintError` at `0x180006872`
- `iisutil!PuDbgPrintError` at `0x180006872`

## string_xrefs

- `0x18000686b`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_meta_context.cxx`
- `0x18000684e`: `Failed to initialize freb configuration for trace provider definitions\n`

## pseudocode

```c
__int64 __fastcall FREB_META_STORED_CONTEXT::InitializeTraceProviderDefinitions(
        FREB_META_STORED_CONTEXT *this,
        const unsigned __int16 *a2,
        struct INativeSectionException **a3)
{
  __int64 v6; // rax
  __int64 (__fastcall *v7)(struct IHttpServer *); // rax
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rax
  int v9; // ebx
  unsigned int v10; // r15d
  __int64 v11; // rbx
  __int64 v12; // rax
  bool v13; // cf
  size_t v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rdi
  PROVIDER_DEFINITIONS_STORED_ENTRY *v17; // rsi
  unsigned int v18; // r15d
  PROVIDER_DEFINITIONS_STORED_ENTRY *v19; // rsi
  unsigned int i; // edi
  int v21; // r12d
  STRU *v22; // r13
  unsigned int v24; // [rsp+40h] [rbp-59h] BYREF
  __int64 v25; // [rsp+48h] [rbp-51h] BYREF
  __int64 v26; // [rsp+50h] [rbp-49h] BYREF
  __int64 v27; // [rsp+58h] [rbp-41h] BYREF
  __int64 v28; // [rsp+60h] [rbp-39h] BYREF
  __int64 v29; // [rsp+68h] [rbp-31h] BYREF
  __int64 v30; // [rsp+70h] [rbp-29h] BYREF
  __int64 v31; // [rsp+78h] [rbp-21h] BYREF
  int v32; // [rsp+80h] [rbp-19h] BYREF
  __int64 v33; // [rsp+88h] [rbp-11h] BYREF
  unsigned __int16 *v34; // [rsp+90h] [rbp-9h] BYREF
  unsigned __int16 *v35; // [rsp+98h] [rbp-1h] BYREF
  unsigned __int16 *v36; // [rsp+A0h] [rbp+7h] BYREF
  const unsigned __int16 *v37; // [rsp+A8h] [rbp+Fh] BYREF
  unsigned int v38; // [rsp+118h] [rbp+7Fh] BYREF

  v34 = (unsigned __int16 *)&qword_18000E008;
  v33 = 0;
  v31 = 0;
  v28 = 0;
  v6 = *(_QWORD *)g_pGlobalInfo;
  v27 = 0;
  v25 = 0;
  v26 = 0;
  v7 = *(__int64 (__fastcall **)(struct IHttpServer *))(v6 + 56);
  v30 = 0;
  v29 = 0;
  v24 = 0;
  v38 = 0;
  v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v7(g_pGlobalInfo);
  v9 = (**v8)(v8, &IID_INativeConfigurationSystem, &v33);
  if ( v9 < 0 )
    goto LABEL_32;
  v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, __int64 *, struct INativeSectionException **, __int64 *))(*(_QWORD *)v33 + 24LL))(
         v33,
         L"system.webServer/tracing/traceProviderDefinitions",
         a2,
         &v31,
         a3,
         &v29);
  if ( v9 < 0 )
    goto LABEL_32;
  (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v29 + 24LL))(v29, &v34);
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 40LL))(v31, &v28);
  if ( v9 < 0 )
    goto LABEL_32;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  v31 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v28 + 24LL))(v28, &v24);
  if ( v9 < 0 )
    goto LABEL_32;
  v10 = v24;
  v11 = v24;
  v12 = 88LL * v24;
  if ( !is_mul_ok(v24, 0x58u) )
    v12 = -1;
  v13 = __CFADD__(v12, 8);
  v14 = v12 + 8;
  if ( v13 )
    v14 = -1;
  v15 = operator new(v14);
  if ( !v15 )
  {
    *((_QWORD *)this + 3) = 0;
LABEL_31:
    v9 = -2147024888;
    goto LABEL_32;
  }
  *v15 = v11;
  v16 = v15 + 1;
  v17 = (PROVIDER_DEFINITIONS_STORED_ENTRY *)(v15 + 1);
  if ( v10 )
  {
    do
    {
      PROVIDER_DEFINITIONS_STORED_ENTRY::PROVIDER_DEFINITIONS_STORED_ENTRY(v17);
      v17 = (PROVIDER_DEFINITIONS_STORED_ENTRY *)((char *)v17 + 88);
      --v11;
    }
    while ( v11 );
  }
  *((_QWORD *)this + 3) = v16;
  if ( !v16 )
    goto LABEL_31;
  *((_DWORD *)this + 8) = v10;
  v18 = 0;
  if ( !v24 )
  {
LABEL_28:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    return 0;
  }
  while ( 1 )
  {
    v36 = 0;
    v35 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v28 + 32LL))(v28, v18, &v25);
    if ( v9 < 0 )
      break;
    v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v25 + 64LL))(
           v25,
           L"name",
           &v36,
           0,
           0);
    if ( v9 < 0 )
      break;
    v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v25 + 64LL))(
           v25,
           L"guid",
           &v35,
           0,
           0);
    if ( v9 < 0 )
      break;
    v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v25 + 32LL))(v25, L"areas", &v30);
    if ( v9 < 0 )
      break;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 40LL))(v30, &v27);
    if ( v9 < 0 )
      break;
    v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v27 + 24LL))(v27, &v38);
    if ( v9 < 0 )
      break;
    v19 = (PROVIDER_DEFINITIONS_STORED_ENTRY *)(*((_QWORD *)this + 3) + 88LL * v18);
    v9 = PROVIDER_DEFINITIONS_STORED_ENTRY::InitializeInstance(v19, v36, v35, v38, v34);
    if ( v9 < 0 )
      break;
    for ( i = 0; i < v38; v26 = 0 )
    {
      v37 = 0;
      v32 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v27 + 32LL))(v27, i, &v26);
      if ( v9 < 0 )
        goto LABEL_32;
      v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v26 + 64LL))(
             v26,
             L"name",
             &v37,
             0,
             0);
      if ( v9 < 0 )
        goto LABEL_32;
      v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v26 + 48LL))(
             v26,
             L"value",
             &v32,
             0,
             0);
      if ( v9 < 0 )
        goto LABEL_32;
      v21 = v32;
      v22 = (STRU *)(*((_QWORD *)v19 + 10) + ((unsigned __int64)i << 6));
      v9 = STRU::Copy(v22, v37);
      if ( v9 < 0 )
        goto LABEL_32;
      *((_DWORD *)v22 + 14) = v21;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      ++i;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    ++v18;
    v25 = 0;
    if ( v18 >= v24 )
      goto LABEL_28;
  }
LABEL_32:
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_meta_context.cxx",
      886,
      "FREB_META_STORED_CONTEXT::InitializeTraceProviderDefinitions",
      v9,
      "Failed to initialize freb configuration for trace provider definitions\n");
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180006354  push    rbp
0x180006356  push    rbx
0x180006357  push    rsi
0x180006358  push    rdi
0x180006359  push    r12
0x18000635b  push    r13
0x18000635d  push    r14
0x18000635f  push    r15
0x180006361  lea     rbp, [rsp-1Fh]
0x180006366  sub     rsp, 0B8h
0x18000636d  xor     r12d, r12d
0x180006370  lea     rax, qword_18000E008
0x180006377  mov     [rbp+57h+var_60], rax
0x18000637b  mov     r14, rcx
0x18000637e  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180006385  mov     rdi, r8
0x180006388  mov     rsi, rdx
0x18000638b  mov     [rbp+57h+var_68], r12
0x18000638f  mov     [rbp+57h+var_78], r12
0x180006393  mov     [rbp+57h+var_90], r12
0x180006397  mov     rax, [rcx]
0x18000639a  mov     [rbp+57h+var_98], r12
0x18000639e  mov     [rbp+57h+var_A8], r12
0x1800063a2  mov     [rbp+57h+var_A0], r12
0x1800063a6  mov     rax, [rax+38h]
0x1800063aa  mov     [rbp+57h+var_80], r12
0x1800063ae  mov     [rbp+57h+var_88], r12
0x1800063b2  mov     [rbp+57h+var_B0], r12d
0x1800063b6  mov     [rbp+57h+arg_18], r12d
0x1800063ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063bf  mov     r9, rax
0x1800063c2  lea     r8, [rbp+57h+var_68]
0x1800063c6  lea     rdx, IID_INativeConfigurationSystem
0x1800063cd  mov     rcx, [rax]
0x1800063d0  mov     rax, [rcx]
0x1800063d3  mov     rcx, r9
0x1800063d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063db  mov     ebx, eax
0x1800063dd  test    eax, eax
0x1800063df  js      loc_180006776
0x1800063e5  mov     rcx, [rbp+57h+var_68]
0x1800063e9  lea     rdx, [rbp+57h+var_88]
0x1800063ed  mov     [rsp+0F0h+var_C8], rdx
0x1800063f2  lea     r9, [rbp+57h+var_78]
0x1800063f6  mov     r8, rsi
0x1800063f9  mov     [rsp+0F0h+var_D0], rdi
0x1800063fe  lea     rdx, aSystemWebserve; "system.webServer/tracing/traceProviderD"...
0x180006405  mov     rax, [rcx]
0x180006408  mov     rax, [rax+18h]
0x18000640c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006411  mov     ebx, eax
0x180006413  test    eax, eax
0x180006415  js      loc_180006776
0x18000641b  mov     rcx, [rbp+57h+var_88]
0x18000641f  lea     rdx, [rbp+57h+var_60]
0x180006423  mov     rax, [rcx]
0x180006426  mov     rax, [rax+18h]
0x18000642a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000642f  mov     rcx, [rbp+57h+var_78]
0x180006433  lea     rdx, [rbp+57h+var_90]
0x180006437  mov     rax, [rcx]
0x18000643a  mov     rax, [rax+28h]
0x18000643e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006443  mov     ebx, eax
0x180006445  test    eax, eax
0x180006447  js      loc_180006776
0x18000644d  mov     rcx, [rbp+57h+var_78]
0x180006451  mov     rax, [rcx]
0x180006454  mov     rax, [rax+10h]
0x180006458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000645d  mov     rcx, [rbp+57h+var_90]
0x180006461  lea     rdx, [rbp+57h+var_B0]
0x180006465  mov     [rbp+57h+var_78], r12
0x180006469  mov     rax, [rcx]
0x18000646c  mov     rax, [rax+18h]
0x180006470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006475  mov     ebx, eax
0x180006477  test    eax, eax
0x180006479  js      loc_180006776
0x18000647f  mov     r15d, [rbp+57h+var_B0]
0x180006483  lea     rcx, [r12-1]
0x180006488  lea     eax, [r12+58h]
0x18000648d  mov     ebx, r15d
0x180006490  mul     r15
0x180006493  cmovb   rax, rcx
0x180006497  add     rax, 8
0x18000649b  cmovb   rax, rcx
0x18000649f  mov     rcx, rax; Size
0x1800064a2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800064a7  test    rax, rax
0x1800064aa  jz      loc_18000676D
0x1800064b0  mov     [rax], rbx
0x1800064b3  lea     rdi, [rax+8]
0x1800064b7  mov     rsi, rdi
0x1800064ba  test    r15d, r15d
0x1800064bd  jz      short loc_1800064D1
0x1800064bf  mov     rcx, rsi; this
0x1800064c2  call    ??0PROVIDER_DEFINITIONS_STORED_ENTRY@@QEAA@XZ; PROVIDER_DEFINITIONS_STORED_ENTRY::PROVIDER_DEFINITIONS_STORED_ENTRY(void)
0x1800064c7  add     rsi, 58h ; 'X'
0x1800064cb  sub     rbx, 1
0x1800064cf  jnz     short loc_1800064BF
0x1800064d1  mov     [r14+18h], rdi
0x1800064d5  test    rdi, rdi
0x1800064d8  jz      loc_180006771
0x1800064de  mov     [r14+20h], r15d
0x1800064e2  mov     r15d, r12d
0x1800064e5  cmp     [rbp+57h+var_B0], r12d
0x1800064e9  jbe     loc_180006729
0x1800064ef  mov     rcx, [rbp+57h+var_90]
0x1800064f3  lea     r8, [rbp+57h+var_A8]
0x1800064f7  mov     [rbp+57h+var_50], r12
0x1800064fb  mov     edx, r15d
0x1800064fe  mov     [rbp+57h+var_58], r12
0x180006502  mov     rax, [rcx]
0x180006505  mov     rax, [rax+20h]
0x180006509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000650e  mov     ebx, eax
0x180006510  test    eax, eax
0x180006512  js      loc_180006776
0x180006518  mov     rcx, [rbp+57h+var_A8]
0x18000651c  lea     r8, [rbp+57h+var_50]
0x180006520  xor     r9d, r9d
0x180006523  mov     [rsp+0F0h+var_D0], r12
0x180006528  lea     rdx, aName; "name"
0x18000652f  mov     rax, [rcx]
0x180006532  mov     rax, [rax+40h]
0x180006536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000653b  mov     ebx, eax
0x18000653d  test    eax, eax
0x18000653f  js      loc_180006776
0x180006545  mov     rcx, [rbp+57h+var_A8]
0x180006549  lea     r8, [rbp+57h+var_58]
0x18000654d  xor     r9d, r9d
0x180006550  mov     [rsp+0F0h+var_D0], r12
0x180006555  lea     rdx, aGuid_0; "guid"
0x18000655c  mov     rax, [rcx]
0x18000655f  mov     rax, [rax+40h]
0x180006563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006568  mov     ebx, eax
0x18000656a  test    eax, eax
0x18000656c  js      loc_180006776
0x180006572  mov     rcx, [rbp+57h+var_A8]
0x180006576  lea     r8, [rbp+57h+var_80]
0x18000657a  lea     rdx, aAreas; "areas"
0x180006581  mov     rax, [rcx]
0x180006584  mov     rax, [rax+20h]
0x180006588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000658d  mov     ebx, eax
0x18000658f  test    eax, eax
0x180006591  js      loc_180006776
0x180006597  mov     rcx, [rbp+57h+var_80]
0x18000659b  lea     rdx, [rbp+57h+var_98]
0x18000659f  mov     rax, [rcx]
0x1800065a2  mov     rax, [rax+28h]
0x1800065a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ab  mov     ebx, eax
0x1800065ad  test    eax, eax
0x1800065af  js      loc_180006776
0x1800065b5  mov     rcx, [rbp+57h+var_98]
0x1800065b9  lea     rdx, [rbp+57h+arg_18]
0x1800065bd  mov     rax, [rcx]
0x1800065c0  mov     rax, [rax+18h]
0x1800065c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065c9  mov     ebx, eax
0x1800065cb  test    eax, eax
0x1800065cd  js      loc_180006776
0x1800065d3  mov     r9d, [rbp+57h+arg_18]; unsigned int
0x1800065d7  mov     r8, [rbp+57h+var_58]; unsigned __int16 *
0x1800065db  mov     rdx, [rbp+57h+var_50]; unsigned __int16 *
0x1800065df  mov     eax, r15d
0x1800065e2  imul    rsi, rax, 58h ; 'X'
0x1800065e6  mov     rax, [rbp+57h+var_60]
0x1800065ea  add     rsi, [r14+18h]
0x1800065ee  mov     rcx, rsi; this
0x1800065f1  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x1800065f6  call    ?InitializeInstance@PROVIDER_DEFINITIONS_STORED_ENTRY@@QEAAJPEBG0K0@Z; PROVIDER_DEFINITIONS_STORED_ENTRY::InitializeInstance(ushort const *,ushort const *,ulong,ushort const *)
0x1800065fb  mov     ebx, eax
0x1800065fd  test    eax, eax
0x1800065ff  js      loc_180006776
0x180006605  mov     edi, r12d
0x180006608  cmp     [rbp+57h+arg_18], r12d
0x18000660c  jbe     loc_1800066E0
0x180006612  mov     rcx, [rbp+57h+var_98]
0x180006616  lea     r8, [rbp+57h+var_A0]
0x18000661a  mov     [rbp+57h+var_48], r12
0x18000661e  mov     edx, edi
0x180006620  mov     [rbp+57h+var_70], r12d
0x180006624  mov     rax, [rcx]
0x180006627  mov     rax, [rax+20h]
0x18000662b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006630  mov     ebx, eax
0x180006632  test    eax, eax
0x180006634  js      loc_180006776
0x18000663a  mov     rcx, [rbp+57h+var_A0]
0x18000663e  lea     r8, [rbp+57h+var_48]
0x180006642  xor     r9d, r9d
0x180006645  mov     [rsp+0F0h+var_D0], r12
0x18000664a  lea     rdx, aName; "name"
0x180006651  mov     rax, [rcx]
0x180006654  mov     rax, [rax+40h]
0x180006658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000665d  mov     ebx, eax
0x18000665f  test    eax, eax
0x180006661  js      loc_180006776
0x180006667  mov     rcx, [rbp+57h+var_A0]
0x18000666b  lea     r8, [rbp+57h+var_70]
0x18000666f  xor     r9d, r9d
0x180006672  mov     [rsp+0F0h+var_D0], r12
0x180006677  lea     rdx, aValue; "value"
0x18000667e  mov     rax, [rcx]
0x180006681  mov     rax, [rax+30h]
0x180006685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000668a  mov     ebx, eax
0x18000668c  test    eax, eax
0x18000668e  js      loc_180006776
0x180006694  mov     rdx, [rbp+57h+var_48]
0x180006698  mov     r12d, [rbp+57h+var_70]
0x18000669c  mov     r13d, edi
0x18000669f  shl     r13, 6
0x1800066a3  add     r13, [rsi+50h]
0x1800066a7  mov     rcx, r13
0x1800066aa  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800066b0  mov     ebx, eax
0x1800066b2  test    eax, eax
0x1800066b4  js      loc_180006768
0x1800066ba  mov     [r13+38h], r12d
0x1800066be  mov     rcx, [rbp+57h+var_A0]
0x1800066c2  mov     rax, [rcx]
0x1800066c5  mov     rax, [rax+10h]
0x1800066c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066ce  xor     r12d, r12d
0x1800066d1  inc     edi
0x1800066d3  mov     [rbp+57h+var_A0], r12
0x1800066d7  cmp     edi, [rbp+57h+arg_18]
0x1800066da  jb      loc_180006612
0x1800066e0  mov     rcx, [rbp+57h+var_98]
0x1800066e4  mov     rax, [rcx]
0x1800066e7  mov     rax, [rax+10h]
0x1800066eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066f0  mov     rcx, [rbp+57h+var_80]
0x1800066f4  mov     [rbp+57h+var_98], r12
0x1800066f8  mov     rax, [rcx]
0x1800066fb  mov     rax, [rax+10h]
0x1800066ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006704  mov     rcx, [rbp+57h+var_A8]
0x180006708  mov     [rbp+57h+var_80], r12
0x18000670c  mov     rax, [rcx]
0x18000670f  mov     rax, [rax+10h]
0x180006713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006718  inc     r15d
0x18000671b  mov     [rbp+57h+var_A8], r12
0x18000671f  cmp     r15d, [rbp+57h+var_B0]
0x180006723  jb      loc_1800064EF
0x180006729  mov     rcx, [rbp+57h+var_88]
0x18000672d  mov     rax, [rcx]
0x180006730  mov     rax, [rax+10h]
0x180006734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006739  mov     rcx, [rbp+57h+var_90]
0x18000673d  mov     [rbp+57h+var_88], r12
0x180006741  mov     rax, [rcx]
0x180006744  mov     rax, [rax+10h]
0x180006748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000674d  mov     rcx, [rbp+57h+var_68]
0x180006751  mov     [rbp+57h+var_90], r12
0x180006755  mov     rax, [rcx]
0x180006758  mov     rax, [rax+10h]
0x18000675c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006761  xor     eax, eax
0x180006763  jmp     loc_18000687A
0x180006768  xor     r12d, r12d
0x18000676b  jmp     short loc_180006776
0x18000676d  mov     [r14+18h], r12
0x180006771  mov     ebx, 80070008h
0x180006776  mov     rcx, [rbp+57h+var_88]
0x18000677a  test    rcx, rcx
0x18000677d  jz      short loc_18000678F
0x18000677f  mov     rax, [rcx]
0x180006782  mov     rax, [rax+10h]
0x180006786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000678b  mov     [rbp+57h+var_88], r12
0x18000678f  mov     rcx, [rbp+57h+var_A0]
0x180006793  test    rcx, rcx
0x180006796  jz      short loc_1800067A8
0x180006798  mov     rax, [rcx]
0x18000679b  mov     rax, [rax+10h]
0x18000679f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067a4  mov     [rbp+57h+var_A0], r12
0x1800067a8  mov     rcx, [rbp+57h+var_98]
0x1800067ac  test    rcx, rcx
0x1800067af  jz      short loc_1800067C1
0x1800067b1  mov     rax, [rcx]
0x1800067b4  mov     rax, [rax+10h]
0x1800067b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067bd  mov     [rbp+57h+var_98], r12
0x1800067c1  mov     rcx, [rbp+57h+var_80]
0x1800067c5  test    rcx, rcx
0x1800067c8  jz      short loc_1800067DA
0x1800067ca  mov     rax, [rcx]
0x1800067cd  mov     rax, [rax+10h]
0x1800067d1  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
