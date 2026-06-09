# DusmSruQueryStats(_SYSTEMTIME const &,_SYSTEMTIME const &,_SRU_PROVIDER_CLASS)

- ea: `0x180024898`
- end: `0x180024a31`
- name: `?DusmSruQueryStats@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_SRU_STATS_RECORD_SET@@P6AXPEAU1@@Z$1?SruFreeRecordSet@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_SYSTEMTIME@@0W4_SRU_PROVIDER_CLASS@@@Z`
- size: `409`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180022d90`
- `0x1800235e4`
- `0x180023b48`
- `0x180024074`
- `0x180024578`

## callees

- `0x180008710`
- `0x18000a6c4`
- `0x18001d87c`
- `0x1800222dc`
- `0x180022628`
- `0x180024898`
- `0x180024afc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800248cf`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800248cf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180024963`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180024963`
- `SrumAPI!SruUpdateStats` at `0x1800248ef`
- `SrumAPI!SruUpdateStats` at `0x1800248ef`
- `SrumAPI!SruQueryStats` at `0x180024929`
- `SrumAPI!SruQueryStats` at `0x180024929`

## string_xrefs

- `0x1800249eb`: `DusmSruQueryStats::SruUpdateStats`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall DusmSruQueryStats(_QWORD *a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned int v8; // eax
  unsigned int v9; // edi
  unsigned int updated; // eax
  unsigned int v11; // ebx
  unsigned int v13; // eax
  const char *v14; // [rsp+28h] [rbp-40h]
  _QWORD *pExceptionObject; // [rsp+40h] [rbp-28h] BYREF
  __int64 v16; // [rsp+48h] [rbp-20h] BYREF
  char v17; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  *a1 = 0;
  v8 = CoInitializeEx(0, 0);
  v9 = v8;
  if ( v8 != -2147417850 && v8 )
  {
    v13 = wil::verify_hresult<long>(v8);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x14,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmattribution.cpp",
      (const char *)v13,
      (int)"DusmSruQueryStats::CoInitializeEx",
      v14);
  }
  updated = SruUpdateStats(a4);
  if ( updated != 21 )
  {
    if ( updated )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x27,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmattribution.cpp",
        (const char *)updated,
        (unsigned int)"DusmSruQueryStats::SruUpdateStats",
        v14);
    pExceptionObject = a1;
    v16 = 0;
    v17 = 1;
    v11 = SruQueryStats(a4, a2, a3, 2, &v16);
    wil::details::out_param_ptr_t<_SRU_STATS_RECORD_SET * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SRU_STATS_RECORD_SET *,void (*)(_SRU_STATS_RECORD_SET *),&void SruFreeRecordSet(_SRU_STATS_RECORD_SET *),wistd::integral_constant<unsigned __int64,0>,_SRU_STATS_RECORD_SET *,_SRU_STATS_RECORD_SET *,0,std::nullptr_t>>>>::~out_param_ptr_t<_SRU_STATS_RECORD_SET * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SRU_STATS_RECORD_SET *,void (*)(_SRU_STATS_RECORD_SET *),&void SruFreeRecordSet(_SRU_STATS_RECORD_SET *),wistd::integral_constant<unsigned __int64,0>,_SRU_STATS_RECORD_SET *,_SRU_STATS_RECORD_SET *,0,std::nullptr_t>>>>(&pExceptionObject);
    if ( v11 )
    {
      if ( v11 != 1808 && v11 != 529 )
      {
        if ( v11 != 1011 )
          wil::details::in1diag3::Throw_Win32Msg(
            retaddr,
            (void *)0x3F,
            (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmattribution.cpp",
            (const char *)v11,
            (unsigned int)"DusmSruQueryStats::SruQueryStats::2",
            v14);
        std::bad_alloc::bad_alloc((std::bad_alloc *)&pExceptionObject);
        throw (std::bad_alloc *)&pExceptionObject;
      }
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x37,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmattribution.cpp",
        (const char *)0x70,
        (unsigned int)"DusmSruQueryStats::SruQueryStats::1",
        v14);
    }
  }
  if ( v9 != -2147417850 )
    CoUninitialize();
  return a1;
}

```

## disassembly

```asm
0x180024898  mov     [rsp-30h+arg_0], rcx
0x18002489d  push    rbp
0x18002489e  push    rbx
0x18002489f  push    rsi
0x1800248a0  push    rdi
0x1800248a1  push    r14
0x1800248a3  push    r15
0x1800248a5  mov     rbp, rsp
0x1800248a8  sub     rsp, 68h
0x1800248ac  mov     ebx, r9d
0x1800248af  mov     r14, r8
0x1800248b2  mov     r15, rdx
0x1800248b5  mov     rsi, rcx
0x1800248b8  mov     [rbp+var_38], 1
0x1800248bf  xor     eax, eax
0x1800248c1  mov     [rcx], rax
0x1800248c4  mov     [rbp+var_38], 1
0x1800248cb  xor     edx, edx; dwCoInit
0x1800248cd  xor     ecx, ecx; pvReserved
0x1800248cf  call    cs:__imp_CoInitializeEx
0x1800248d5  mov     edi, eax
0x1800248d7  cmp     eax, 80010106h
0x1800248dc  jz      short loc_1800248E6
0x1800248de  test    eax, eax
0x1800248e0  jnz     loc_1800249BB
0x1800248e6  mov     [rbp+var_30], edi
0x1800248e9  mov     [rbp+var_2C], 1
0x1800248ed  mov     ecx, ebx
0x1800248ef  call    cs:__imp_SruUpdateStats
0x1800248f5  cmp     eax, 15h
0x1800248f8  jz      short loc_18002495B
0x1800248fa  test    eax, eax
0x1800248fc  jnz     loc_1800249E7
0x180024902  mov     [rbp+pExceptionObject], rsi
0x180024906  mov     [rbp+var_20], 0
0x18002490e  mov     [rbp+var_18], 1
0x180024912  lea     rax, [rbp+var_20]
0x180024916  mov     qword ptr [rsp+68h+var_48], rax
0x18002491b  mov     r9d, 2
0x180024921  mov     r8, r14
0x180024924  mov     rdx, r15
0x180024927  mov     ecx, ebx
0x180024929  call    cs:__imp_SruQueryStats
0x18002492f  mov     ebx, eax
0x180024931  lea     rcx, [rbp+pExceptionObject]
0x180024935  call    ??1?$out_param_ptr_t@PEAPEAU_SRU_STATS_RECORD_SET@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_SRU_STATS_RECORD_SET@@P6AXPEAU1@@Z$1?SruFreeRecordSet@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<_SRU_STATS_RECORD_SET * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SRU_STATS_RECORD_SET *,void (*)(_SRU_STATS_RECORD_SET *),&SruFreeRecordSet(_SRU_STATS_RECORD_SET *),wistd::integral_constant<unsigned __int64,0>,_SRU_STATS_RECORD_SET *,_SRU_STATS_RECORD_SET *,0,std::nullptr_t>>>>::~out_param_ptr_t<_SRU_STATS_RECORD_SET * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SRU_STATS_RECORD_SET *,void (*)(_SRU_STATS_RECORD_SET *),&SruFreeRecordSet(_SRU_STATS_RECORD_SET *),wistd::integral_constant<unsigned __int64,0>,_SRU_STATS_RECORD_SET *,_SRU_STATS_RECORD_SET *,0,std::nullptr_t>>>>(void)
0x18002493a  test    ebx, ebx
0x18002493c  jz      short loc_18002495B
0x18002493e  cmp     ebx, 710h
0x180024944  jz      short loc_18002497A
0x180024946  cmp     ebx, 211h
0x18002494c  jz      short loc_18002497A
0x18002494e  cmp     ebx, 3F3h
0x180024954  jz      short loc_1800249A1
0x180024956  jmp     loc_180024A0C
0x18002495b  cmp     edi, 80010106h
0x180024961  jz      short loc_18002496A
0x180024963  call    cs:__imp_CoUninitialize
0x180024969  nop
0x18002496a  mov     rax, rsi
0x18002496d  add     rsp, 68h
0x180024971  pop     r15
0x180024973  pop     r14
0x180024975  pop     rdi
0x180024976  pop     rsi
0x180024977  pop     rbx
0x180024978  pop     rbp
0x180024979  retn
0x18002497a  mov     rcx, [rbp+30h]; this
0x18002497e  lea     rax, aDusmsruqueryst_2; "DusmSruQueryStats::SruQueryStats::1"
0x180024985  mov     qword ptr [rsp+68h+var_48], rax; unsigned int
0x18002498a  mov     r9d, 70h ; 'p'; char *
0x180024990  lea     r8, aOnecoreuapNetD_0; "onecoreuap\\net\\dusm\\lib\\dusmattribu"...
0x180024997  lea     edx, [r9-39h]; void *
0x18002499b  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800249a1  lea     rcx, [rbp+pExceptionObject]; this
0x1800249a5  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x1800249aa  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800249b1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800249b5  call    _CxxThrowException_0
0x1800249bb  mov     ecx, edi
0x1800249bd  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800249c2  mov     r9d, eax; char *
0x1800249c5  mov     rcx, [rbp+30h]; this
0x1800249c9  lea     rax, aDusmsruqueryst_0; "DusmSruQueryStats::CoInitializeEx"
0x1800249d0  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800249d5  lea     r8, aOnecoreuapNetD_0; "onecoreuap\\net\\dusm\\lib\\dusmattribu"...
0x1800249dc  mov     edx, 14h; void *
0x1800249e1  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800249e7  mov     rcx, [rbp+30h]; this
0x1800249eb  lea     rdx, aDusmsruqueryst_1; "DusmSruQueryStats::SruUpdateStats"
0x1800249f2  mov     qword ptr [rsp+68h+var_48], rdx; unsigned int
0x1800249f7  mov     r9d, eax; char *
0x1800249fa  lea     r8, aOnecoreuapNetD_0; "onecoreuap\\net\\dusm\\lib\\dusmattribu"...
0x180024a01  mov     edx, 27h ; '''; void *
0x180024a06  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180024a0c  mov     rcx, [rbp+30h]; this
0x180024a10  lea     rax, aDusmsruqueryst; "DusmSruQueryStats::SruQueryStats::2"
0x180024a17  mov     qword ptr [rsp+68h+var_48], rax; unsigned int
0x180024a1c  mov     r9d, ebx; char *
0x180024a1f  lea     r8, aOnecoreuapNetD_0; "onecoreuap\\net\\dusm\\lib\\dusmattribu"...
0x180024a26  mov     edx, 3Fh ; '?'; void *
0x180024a2b  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
