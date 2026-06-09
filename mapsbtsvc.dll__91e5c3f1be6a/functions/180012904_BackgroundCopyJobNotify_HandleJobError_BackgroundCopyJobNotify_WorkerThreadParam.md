# BackgroundCopyJobNotify::HandleJobError(BackgroundCopyJobNotify::WorkerThreadParam *)

- ea: `0x180012904`
- end: `0x180012a65`
- name: `?HandleJobError@BackgroundCopyJobNotify@@CAJPEAUWorkerThreadParam@1@@Z`
- size: `353`
- prototype: `__int64 __fastcall(struct BackgroundCopyJobNotify::WorkerThreadParam *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800128a0`

## callees

- `0x1800043e4`
- `0x180004680`
- `0x1800047cc`
- `0x180005b9c`
- `0x18000c348`
- `0x180011130`
- `0x180012904`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012980`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012980`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180012997`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180012997`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x1800129c2`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x1800129c2`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800129f5`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800129f5`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180012a1a`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180012a1a`

## string_xrefs

- `0x1800129b9`: `BackgroundCopyJobNotify::HandleJobError`
- `0x1800129ec`: `BackgroundCopyJobNotify::HandleJobError`
- `0x180012a11`: `BackgroundCopyJobNotify::HandleJobError`

## pseudocode

```c
__int64 __fastcall BackgroundCopyJobNotify::HandleJobError(struct BackgroundCopyJobNotify::WorkerThreadParam *a1)
{
  unsigned int v2; // edi
  int v3; // eax
  int v4; // r8d
  __int64 v5; // rsi
  __int64 (__fastcall *v6)(__int64, _QWORD, LPVOID *); // r15
  void *v7; // rbx
  unsigned __int16 ThreadLocale; // ax
  int v9; // eax
  std::_Ref_count_base *v10; // rbx
  MapsBackgroundTransferJob *v12; // [rsp+40h] [rbp-10h] BYREF
  std::_Ref_count_base *v13; // [rsp+48h] [rbp-8h]
  int v14; // [rsp+80h] [rbp+30h] BYREF
  int v15; // [rsp+88h] [rbp+38h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+40h] BYREF
  char v17; // [rsp+98h] [rbp+48h] BYREF

  v2 = 0;
  v14 = 0;
  v15 = 0;
  pv = 0;
  std::weak_ptr<MapsBackgroundTransferJob>::lock((char *)a1 + 24, &v12);
  if ( v12 )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD, int *, int *))(**((_QWORD **)a1 + 2) + 24LL))(
           *((_QWORD *)a1 + 2),
           &v15,
           &v14);
    if ( v3 < 0 )
    {
      v4 = 194;
LABEL_10:
      v2 = ZTraceReportPropagationNoThis(v3, "BackgroundCopyJobNotify::HandleJobError", v4);
      goto LABEL_11;
    }
    v5 = *((_QWORD *)a1 + 2);
    v6 = *(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v5 + 40LL);
    v7 = pv;
    if ( pv )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v17);
      CoTaskMemFree(v7);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v17);
    }
    pv = 0;
    ThreadLocale = GetThreadLocale();
    v9 = v6(v5, ThreadLocale, &pv);
    if ( v9 < 0 )
      ZTraceReportIgnoreNoThis(v9, "BackgroundCopyJobNotify::HandleJobError", 197);
    ZTraceHelperNoThis(
      0,
      "BackgroundCopyJobNotify::HandleJobError",
      199,
      "Job Error. Context: %d. Error: 0x%08X. Description: %ls",
      v15,
      v14,
      (const wchar_t *)pv);
    v3 = MapsBackgroundTransferJob::AllRequestsFail(v12, v14);
    if ( v3 < 0 )
    {
      v4 = 201;
      goto LABEL_10;
    }
  }
LABEL_11:
  v10 = v13;
  if ( v13 && _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(std::_Ref_count_base *))v10)(v10);
    std::_Ref_count_base::_Decwref(v10);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
  return v2;
}

```

## disassembly

```asm
0x180012904  push    rbp
0x180012906  push    rbx
0x180012907  push    rsi
0x180012908  push    rdi
0x180012909  push    r15
0x18001290b  mov     rbp, rsp
0x18001290e  sub     rsp, 50h
0x180012912  mov     rbx, rcx
0x180012915  xor     edi, edi
0x180012917  mov     [rbp+arg_0], edi
0x18001291a  mov     [rbp+arg_8], edi
0x18001291d  mov     [rbp+pv], rdi
0x180012921  add     rcx, 18h
0x180012925  lea     rdx, [rbp+var_10]
0x180012929  call    ?lock@?$weak_ptr@VMapsBackgroundTransferJob@@@std@@QEBA?AV?$shared_ptr@VMapsBackgroundTransferJob@@@2@XZ; std::weak_ptr<MapsBackgroundTransferJob>::lock(void)
0x18001292e  nop
0x18001292f  cmp     [rbp+var_10], rdi
0x180012933  jz      loc_180012A22
0x180012939  mov     rcx, [rbx+10h]
0x18001293d  mov     rax, [rcx]
0x180012940  lea     r8, [rbp+arg_0]
0x180012944  lea     rdx, [rbp+arg_8]
0x180012948  mov     rax, [rax+18h]
0x18001294c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012951  test    eax, eax
0x180012953  jns     short loc_180012960
0x180012955  mov     r8d, 0C2h
0x18001295b  jmp     loc_180012A11
0x180012960  mov     rsi, [rbx+10h]
0x180012964  mov     rax, [rsi]
0x180012967  mov     r15, [rax+28h]
0x18001296b  mov     rbx, [rbp+pv]
0x18001296f  test    rbx, rbx
0x180012972  jz      short loc_18001298F
0x180012974  lea     rcx, [rbp+arg_18]; this
0x180012978  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001297d  mov     rcx, rbx; pv
0x180012980  call    cs:__imp_CoTaskMemFree
0x180012986  lea     rcx, [rbp+arg_18]; this
0x18001298a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001298f  mov     [rbp+pv], 0
0x180012997  call    cs:__imp_GetThreadLocale
0x18001299d  movzx   edx, ax
0x1800129a0  lea     r8, [rbp+pv]
0x1800129a4  mov     rcx, rsi
0x1800129a7  mov     rax, r15
0x1800129aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129af  test    eax, eax
0x1800129b1  jns     short loc_1800129C8
0x1800129b3  mov     r8d, 0C5h
0x1800129b9  lea     rdx, aBackgroundcopy_1; "BackgroundCopyJobNotify::HandleJobError"
0x1800129c0  mov     ecx, eax
0x1800129c2  call    cs:__imp_?ZTraceReportIgnoreNoThis@@YAXHPEBDH@Z; ZTraceReportIgnoreNoThis(int,char const *,int)
0x1800129c8  mov     rax, [rbp+pv]
0x1800129cc  mov     [rsp+50h+var_20], rax
0x1800129d1  mov     eax, [rbp+arg_0]
0x1800129d4  mov     [rsp+50h+var_28], eax
0x1800129d8  mov     eax, [rbp+arg_8]
0x1800129db  mov     [rsp+50h+var_30], eax
0x1800129df  lea     r9, aJobErrorContex_0; "Job Error. Context: %d. Error: 0x%08X. "...
0x1800129e6  mov     r8d, 0C7h
0x1800129ec  lea     rdx, aBackgroundcopy_1; "BackgroundCopyJobNotify::HandleJobError"
0x1800129f3  xor     ecx, ecx
0x1800129f5  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x1800129fb  mov     edx, [rbp+arg_0]; int
0x1800129fe  mov     rcx, [rbp+var_10]; this
0x180012a02  call    ?AllRequestsFail@MapsBackgroundTransferJob@@AEAAJJ@Z; MapsBackgroundTransferJob::AllRequestsFail(long)
0x180012a07  test    eax, eax
0x180012a09  jns     short loc_180012A22
0x180012a0b  mov     r8d, 0C9h
0x180012a11  lea     rdx, aBackgroundcopy_1; "BackgroundCopyJobNotify::HandleJobError"
0x180012a18  mov     ecx, eax
0x180012a1a  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180012a20  mov     edi, eax
0x180012a22  mov     rbx, [rbp+var_8]
0x180012a26  test    rbx, rbx
0x180012a29  jz      short loc_180012A4F
0x180012a2b  or      eax, 0FFFFFFFFh
0x180012a2e  lock xadd [rbx+8], eax
0x180012a33  cmp     eax, 1
0x180012a36  jnz     short loc_180012A4F
0x180012a38  mov     rax, [rbx]
0x180012a3b  mov     rcx, rbx
0x180012a3e  mov     rax, [rax]
0x180012a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a46  mov     rcx, rbx; this
0x180012a49  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180012a4e  nop
0x180012a4f  lea     rcx, [rbp+pv]
0x180012a53  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012a58  mov     eax, edi
0x180012a5a  add     rsp, 50h
0x180012a5e  pop     r15
0x180012a60  pop     rdi
0x180012a61  pop     rsi
0x180012a62  pop     rbx
0x180012a63  pop     rbp
0x180012a64  retn
```
