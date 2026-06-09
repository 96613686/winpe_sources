# DWMInputRouter::GetTargetFromInputSite(Microsoft::WRL::ComPtr<InputSite> const &,InputType,HitTestResult const &,_LUID const &,Microsoft::WRL::ComPtr<IDCompInputTarget> &)

- ea: `0x180018190`
- end: `0x180018627`
- name: `?GetTargetFromInputSite@DWMInputRouter@@AEAA?AV?$ComPtr@UIInputTarget@@@WRL@Microsoft@@AEBV?$ComPtr@VInputSite@@@34@W4InputType@@AEBUHitTestResult@@AEBU_LUID@@AEAV?$ComPtr@UIDCompInputTarget@@@34@@Z`
- size: `1175`
- prototype: `__int64 __usercall@<rax>(DWMInputRouter *this@<rcx>, struct IInputTarget **@<rdx>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180017c60`

## callees

- `0x18000dcd4`
- `0x180012b74`
- `0x18001301c`
- `0x180018190`
- `0x180018630`
- `0x180026554`
- `0x180031f4c`
- `0x180075758`
- `0x18008247c`
- `0x1800af5cc`
- `0x1800f0990`
- `0x18012fcf0`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800182de`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800182de`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18001832e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18001832e`
- `win32u!NtQueryCompositionInputQueueAndTransform` at `0x18001827c`
- `win32u!NtQueryCompositionInputQueueAndTransform` at `0x18001827c`

## string_xrefs

- `0x18001859f`: `onecoreuap\windows\moderncore\inputv2\components\inputsitemanager\server\legacyinputsinkdata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct IInputTarget **__fastcall DWMInputRouter::GetTargetFromInputSite(
        DWMInputRouter *this,
        struct IInputTarget **a2,
        __int64 *a3,
        int a4,
        HWND *a5,
        __int64 a6,
        _QWORD *a7)
{
  __int64 v11; // r14
  __int64 v12; // rdx
  __int64 v13; // r15
  __int128 v14; // xmm1
  HWND *v15; // rdi
  __int64 v16; // rax
  HWND *v17; // rcx
  void (__fastcall ***v18)(_QWORD, GUID *, struct IInputTarget **); // rdi
  void (__fastcall *v19)(_QWORD, GUID *, struct IInputTarget **); // rsi
  struct IInputTarget *v20; // rcx
  char *v21; // rcx
  struct IInputTarget *v22; // rax
  struct IInputTarget *v23; // rcx
  __int64 v24; // rcx
  const struct _LUID *Luid; // rax
  const char *v27; // [rsp+20h] [rbp-C1h]
  __int64 v28; // [rsp+30h] [rbp-B1h] BYREF
  HWND *v29; // [rsp+38h] [rbp-A9h] BYREF
  DWORD dwProcessId[2]; // [rsp+40h] [rbp-A1h] BYREF
  __int64 *v31; // [rsp+48h] [rbp-99h]
  struct IInputTarget **v32; // [rsp+50h] [rbp-91h]
  char v33; // [rsp+58h] [rbp-89h] BYREF
  __int128 v34; // [rsp+60h] [rbp-81h] BYREF
  __int128 v35; // [rsp+70h] [rbp-71h]
  __int128 v36; // [rsp+80h] [rbp-61h]
  __int64 v37; // [rsp+90h] [rbp-51h]
  __int128 v38; // [rsp+A0h] [rbp-41h] BYREF
  __int128 v39; // [rsp+B0h] [rbp-31h]
  __int128 v40; // [rsp+C0h] [rbp-21h]
  __int128 v41; // [rsp+D0h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]

  v32 = a2;
  v29 = a5;
  *a2 = 0;
  dwProcessId[1] = 1;
  v11 = *a3;
  if ( !*(_BYTE *)(*a3 + 480) )
    goto LABEL_35;
  if ( *a7 )
  {
    if ( *(_BYTE *)(v11 + 56) >= 2u )
      std::_Throw_bad_variant_access();
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a7 + 40LL))(*a7, *(_QWORD *)(v11 + 48)) )
    {
      v18 = (void (__fastcall ***)(_QWORD, GUID *, struct IInputTarget **))*a7;
      v19 = **(void (__fastcall ***)(_QWORD, GUID *, struct IInputTarget **))*a7;
      v20 = *a2;
      if ( *a2 )
      {
        *a2 = 0;
        (*(void (__fastcall **)(struct IInputTarget *))(*(_QWORD *)v20 + 16LL))(v20);
      }
      v19(v18, &GUID_9586ac30_9ca0_43dc_8c1c_f977b92a1fd3, a2);
      goto LABEL_26;
    }
  }
  if ( (a4 & 0x1000028) != 0 )
  {
    v12 = 3;
    v13 = 168;
  }
  else if ( (a4 & 0x10) != 0 )
  {
    v12 = 4;
    v13 = 232;
  }
  else if ( (a4 & 2) != 0 )
  {
    v12 = 1;
    v13 = 40;
  }
  else
  {
    if ( (a4 & 4) == 0 )
      wil::details::in1diag3::FailFast_UnexpectedMsg(
        retaddr,
        (void *)0xB7,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\components\\inputsitemanager\\server\\legacyinputsinkdata.cpp",
        "Invalid input type provided.",
        v27);
    v12 = 2;
    v13 = 104;
  }
  if ( !*(_BYTE *)(v13 + v11 + 104) )
  {
    v34 = 0;
    v35 = 0;
    v36 = 0;
    v37 = 0;
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v41 = 0;
    if ( *(_BYTE *)(v11 + 56) >= 2u )
      std::_Throw_bad_variant_access();
    NtQueryCompositionInputQueueAndTransform(*(_QWORD *)(v11 + 48), v12, &v34, &v38);
    v14 = v35;
    *(_OWORD *)(v13 + v11 + 48) = v34;
    *(_OWORD *)(v13 + v11 + 64) = v14;
    *(_QWORD *)&v14 = v37;
    *(_OWORD *)(v13 + v11 + 80) = v36;
    *(_QWORD *)(v13 + v11 + 96) = v14;
    if ( !*(_BYTE *)(v13 + v11 + 104) )
      *(_BYTE *)(v13 + v11 + 104) = 1;
  }
  if ( (unsigned int)(*(_DWORD *)(v13 + v11 + 48) - 3) <= 1 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a2);
    v28 = *a3;
    wil::com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>::~com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>(&v28);
    v38 = *(_OWORD *)(v13 + v11 + 64);
    v39 = *(_OWORD *)(v13 + v11 + 80);
    *(_QWORD *)&v40 = *(_QWORD *)(v13 + v11 + 96);
    DWMInputRouter::CreateAndRegisterTarget(this, &v38, &v28, a2);
LABEL_26:
    v15 = v29;
    goto LABEL_27;
  }
  if ( !InitOnceExecuteOnce(&gInitOnce, InitEditionOnceCallback, 0, 0) )
    __fastfail(7u);
  if ( ((1LL << gdwDeviceFamily) & 0x224A) == 0 || *(_DWORD *)(v13 + v11 + 48) != 2 )
    goto LABEL_26;
  v15 = v29;
  if ( (a4 & 0x4000) != 0 )
  {
    dwProcessId[0] = 0;
    GetWindowThreadProcessId(v29[10], dwProcessId);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a2);
    DWMInputRouter::CreateAndRegisterTarget(this, dwProcessId[0], 0, 0, (unsigned __int64)v29[10], a2);
    v29 = 0;
    if ( (int)Microsoft::WRL::ComPtr<IInputTarget>::As<IDCompInputTarget>(a2, &v29) >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a2);
      v31 = &v28;
      v28 = *a3;
      wil::com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>::~com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>(&v28);
      v16 = (*((__int64 (__fastcall **)(HWND *, __int128 *))*v29 + 9))(v29, &v34);
      v38 = *(_OWORD *)v16;
      v39 = *(_OWORD *)(v16 + 16);
      *(_QWORD *)&v40 = *(_QWORD *)(v16 + 32);
      DWMInputRouter::CreateAndRegisterTarget(this, &v38, &v28, a2);
    }
    v17 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*((void (__fastcall **)(HWND *))*v17 + 2))(v17);
    }
  }
LABEL_27:
  if ( *a2 )
  {
    if ( *((_BYTE *)v15 + 88) )
    {
      Luid = LegacyInputSinkData::GetLuid((LegacyInputSinkData *)(v11 + 48));
      if ( (unsigned __int8)operator==(Luid, a6) )
      {
        v28 = 0;
        if ( (int)Microsoft::WRL::ComPtr<IInputTarget>::As<IDCompInputTarget>(a2, &v28) >= 0 )
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 80LL))(v28, *((unsigned int *)v15 + 23));
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
      }
    }
LABEL_35:
    if ( *a2 )
      return a2;
  }
  v21 = (char *)InputSiteTarget::Create(&v28, a3);
  v22 = 0;
  if ( &v33 != v21 )
  {
    v22 = *(struct IInputTarget **)v21;
    *(_QWORD *)v21 = 0;
  }
  v23 = *a2;
  *a2 = v22;
  if ( v23 )
    (*(void (__fastcall **)(struct IInputTarget *))(*(_QWORD *)v23 + 16LL))(v23);
  v24 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  return a2;
}

```

## disassembly

```asm
0x180018190  mov     [rsp-8+arg_18], rbx
0x180018195  mov     [rsp-8+arg_8], rdx
0x18001819a  push    rbp
0x18001819b  push    rsi
0x18001819c  push    rdi
0x18001819d  push    r12
0x18001819f  push    r13
0x1800181a1  push    r14
0x1800181a3  push    r15
0x1800181a5  lea     rbp, [rsp-0Fh]
0x1800181aa  sub     rsp, 0F0h
0x1800181b1  mov     rax, cs:__security_cookie
0x1800181b8  xor     rax, rsp
0x1800181bb  mov     [rbp+3Fh+var_40], rax
0x1800181bf  mov     esi, r9d
0x1800181c2  mov     r12, r8
0x1800181c5  mov     rbx, rdx
0x1800181c8  mov     r13, rcx
0x1800181cb  mov     r15, [rbp+3Fh+arg_30]
0x1800181cf  mov     [rsp+120h+var_D0], rdx
0x1800181d4  mov     rax, [rbp+3Fh+arg_20]
0x1800181d8  mov     [rsp+120h+var_E8], rax
0x1800181dd  xor     eax, eax
0x1800181df  mov     [rsp+120h+var_DC], eax
0x1800181e3  mov     [rdx], rax
0x1800181e6  mov     edi, 1
0x1800181eb  mov     [rsp+120h+var_DC], edi
0x1800181ef  mov     r14, [r8]
0x1800181f2  cmp     [r14+1E0h], al
0x1800181f9  jz      loc_1800184F7
0x1800181ff  mov     rcx, [r15]
0x180018202  test    rcx, rcx
0x180018205  jnz     loc_180018402
0x18001820b  test    esi, 1000028h
0x180018211  jnz     loc_180018524
0x180018217  test    sil, 10h
0x18001821b  jnz     loc_180018514
0x180018221  test    sil, 2
0x180018225  jz      loc_18001858E
0x18001822b  mov     edx, edi
0x18001822d  mov     r15d, 28h ; '('
0x180018233  cmp     byte ptr [r15+r14+68h], 0
0x180018239  jnz     short loc_1800182BA
0x18001823b  xorps   xmm0, xmm0
0x18001823e  xor     eax, eax
0x180018240  movups  [rsp+120h+var_C0], xmm0
0x180018245  movups  [rbp+3Fh+var_B0], xmm0
0x180018249  movups  [rbp+3Fh+var_A0], xmm0
0x18001824d  mov     [rbp+3Fh+var_90], rax
0x180018251  xorps   xmm1, xmm1
0x180018254  movups  [rbp+3Fh+var_80], xmm1
0x180018258  movups  [rbp+3Fh+var_70], xmm1
0x18001825c  movups  [rbp+3Fh+var_60], xmm1
0x180018260  movups  [rbp+3Fh+var_50], xmm1
0x180018264  cmp     byte ptr [r14+38h], 2
0x180018269  jnb     loc_180018502
0x18001826f  lea     r9, [rbp+3Fh+var_80]
0x180018273  lea     r8, [rsp+120h+var_C0]
0x180018278  mov     rcx, [r14+30h]
0x18001827c  call    cs:__imp_NtQueryCompositionInputQueueAndTransform
0x180018282  movups  xmm0, [rsp+120h+var_C0]
0x180018287  movups  xmm1, [rbp+3Fh+var_B0]
0x18001828b  movups  xmmword ptr [r15+r14+30h], xmm0
0x180018291  movups  xmmword ptr [r15+r14+40h], xmm1
0x180018297  movups  xmm0, [rbp+3Fh+var_A0]
0x18001829b  movsd   xmm1, [rbp+3Fh+var_90]
0x1800182a0  movups  xmmword ptr [r15+r14+50h], xmm0
0x1800182a6  movsd   qword ptr [r15+r14+60h], xmm1
0x1800182ad  cmp     byte ptr [r15+r14+68h], 0
0x1800182b3  jnz     short loc_1800182BA
0x1800182b5  mov     [r15+r14+68h], dil
0x1800182ba  mov     eax, [r15+r14+30h]
0x1800182bf  sub     eax, 3
0x1800182c2  cmp     eax, edi
0x1800182c4  jbe     loc_18001853A
0x1800182ca  xor     r9d, r9d; Context
0x1800182cd  xor     r8d, r8d; Parameter
0x1800182d0  lea     rdx, ?InitEditionOnceCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800182d7  lea     rcx, ?gInitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1800182de  call    cs:__imp_InitOnceExecuteOnce
0x1800182e4  test    eax, eax
0x1800182e6  jz      loc_180018508
0x1800182ec  mov     ecx, cs:?gdwDeviceFamily@@3KA; ulong gdwDeviceFamily
0x1800182f2  shl     rdi, cl
0x1800182f5  test    rdi, 224Ah
0x1800182fc  jz      loc_180018460
0x180018302  cmp     dword ptr [r15+r14+30h], 2
0x180018308  jnz     loc_180018460
0x18001830e  mov     rdi, [rsp+120h+var_E8]
0x180018313  bt      esi, 0Eh
0x180018317  jnb     loc_180018465
0x18001831d  mov     [rsp+120h+dwProcessId], 0
0x180018325  lea     rdx, [rsp+120h+dwProcessId]; lpdwProcessId
0x18001832a  mov     rcx, [rdi+50h]; hWnd
0x18001832e  call    cs:__imp_GetWindowThreadProcessId
0x180018334  mov     rcx, rbx
0x180018337  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001833c  mov     [rsp+120h+var_F8], rbx; struct IInputTarget **
0x180018341  mov     rax, [rdi+50h]
0x180018345  mov     [rsp+120h+var_100], rax; unsigned __int64
0x18001834a  xor     r9d, r9d; unsigned int
0x18001834d  xor     r8d, r8d; unsigned int
0x180018350  mov     edx, [rsp+120h+dwProcessId]; unsigned int
0x180018354  mov     rcx, r13; this
0x180018357  call    ?CreateAndRegisterTarget@DWMInputRouter@@IEAAJKKK_KPEAPEAUIInputTarget@@@Z; DWMInputRouter::CreateAndRegisterTarget(ulong,ulong,ulong,unsigned __int64,IInputTarget * *)
0x18001835c  mov     [rsp+120h+var_E8], 0
0x180018365  lea     rdx, [rsp+120h+var_E8]
0x18001836a  mov     rcx, rbx
0x18001836d  call    ??$As@UIDCompInputTarget@@@?$ComPtr@UIInputTarget@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDCompInputTarget@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInputTarget>::As<IDCompInputTarget>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDCompInputTarget>>)
0x180018372  test    eax, eax
0x180018374  js      short loc_1800183E0
0x180018376  mov     rcx, rbx
0x180018379  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001837e  lea     rax, [rsp+120h+var_F0]
0x180018383  mov     [rsp+120h+var_D8], rax
0x180018388  mov     rax, [r12]
0x18001838c  mov     [rsp+120h+var_F0], rax
0x180018391  lea     rcx, [rsp+120h+var_F0]
0x180018396  call    ??1?$com_ptr_t@VAsyncHRESULTPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>::~com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>(void)
0x18001839b  nop
0x18001839c  mov     rcx, [rsp+120h+var_E8]
0x1800183a1  mov     rax, [rcx]
0x1800183a4  lea     rdx, [rsp+120h+var_C0]
0x1800183a9  mov     rax, [rax+48h]
0x1800183ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183b2  movups  xmm0, xmmword ptr [rax]
0x1800183b5  movaps  [rbp+3Fh+var_80], xmm0
0x1800183b9  movups  xmm1, xmmword ptr [rax+10h]
0x1800183bd  movaps  [rbp+3Fh+var_70], xmm1
0x1800183c1  movsd   xmm0, qword ptr [rax+20h]
0x1800183c6  movsd   qword ptr [rbp+3Fh+var_60], xmm0
0x1800183cb  mov     r9, rbx
0x1800183ce  lea     r8, [rsp+120h+var_F0]
0x1800183d3  lea     rdx, [rbp+3Fh+var_80]
0x1800183d7  mov     rcx, r13
0x1800183da  call    ?CreateAndRegisterTarget@DWMInputRouter@@IEAAJUtagMsgRoutingInfo@@V?$ComPtr@VInputSite@@@WRL@Microsoft@@PEAPEAUIInputTarget@@@Z; DWMInputRouter::CreateAndRegisterTarget(tagMsgRoutingInfo,Microsoft::WRL::ComPtr<InputSite>,IInputTarget * *)
0x1800183df  nop
0x1800183e0  mov     rcx, [rsp+120h+var_E8]
0x1800183e5  test    rcx, rcx
0x1800183e8  jz      short loc_180018400
0x1800183ea  mov     [rsp+120h+var_E8], 0
0x1800183f3  mov     rax, [rcx]
0x1800183f6  mov     rax, [rax+10h]
0x1800183fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183ff  nop
0x180018400  jmp     short loc_180018465
0x180018402  cmp     byte ptr [r14+38h], 2
0x180018407  jnb     loc_180018534
0x18001840d  mov     rax, [rcx]
0x180018410  mov     rdx, [r14+30h]
0x180018414  mov     rax, [rax+28h]
0x180018418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001841d  test    al, al
0x18001841f  jz      loc_18001820B
0x180018425  mov     rdi, [r15]
0x180018428  mov     rax, [rdi]
0x18001842b  mov     rsi, [rax]
0x18001842e  mov     rcx, [rbx]
0x180018431  test    rcx, rcx
0x180018434  jz      short loc_18001844A
0x180018436  mov     qword ptr [rbx], 0
0x18001843d  mov     rax, [rcx]
0x180018440  mov     rax, [rax+10h]
0x180018444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018449  nop
0x18001844a  mov     r8, rbx
0x18001844d  lea     rdx, _GUID_9586ac30_9ca0_43dc_8c1c_f977b92a1fd3
0x180018454  mov     rcx, rdi
0x180018457  mov     rax, rsi
0x18001845a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001845f  nop
0x180018460  mov     rdi, [rsp+120h+var_E8]
0x180018465  cmp     qword ptr [rbx], 0
0x180018469  jnz     loc_1800185C1
0x18001846f  mov     rdx, r12
0x180018472  lea     rcx, [rsp+120h+var_F0]
0x180018477  call    ?Create@InputSiteTarget@@SA?AV?$ComPtr@UIInputTarget@@@WRL@Microsoft@@AEBV?$ComPtr@VInputSite@@@34@@Z; InputSiteTarget::Create(Microsoft::WRL::ComPtr<InputSite> const &)
0x18001847c  mov     rcx, rax
0x18001847f  xor     eax, eax
0x180018481  lea     rdx, [rsp+120h+var_C8]
0x180018486  cmp     rdx, rcx
0x180018489  jz      short loc_180018495
0x18001848b  mov     rax, [rcx]
0x18001848e  mov     qword ptr [rcx], 0
0x180018495  mov     rcx, [rbx]
0x180018498  mov     [rbx], rax
0x18001849b  test    rcx, rcx
0x18001849e  jz      short loc_1800184AD
0x1800184a0  mov     rax, [rcx]
0x1800184a3  mov     rax, [rax+10h]
0x1800184a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184ac  nop
0x1800184ad  mov     rcx, [rsp+120h+var_F0]
0x1800184b2  test    rcx, rcx
0x1800184b5  jz      short loc_1800184CD
0x1800184b7  mov     [rsp+120h+var_F0], 0
0x1800184c0  mov     rdx, [rcx]
0x1800184c3  mov     rax, [rdx+10h]
0x1800184c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184cc  nop
0x1800184cd  mov     rax, rbx
0x1800184d0  mov     rcx, [rbp+3Fh+var_40]
0x1800184d4  xor     rcx, rsp; StackCookie
0x1800184d7  call    __security_check_cookie
0x1800184dc  mov     rbx, [rsp+120h+arg_18]
0x1800184e4  add     rsp, 0F0h
0x1800184eb  pop     r15
0x1800184ed  pop     r14
0x1800184ef  pop     r13
0x1800184f1  pop     r12
0x1800184f3  pop     rdi
0x1800184f4  pop     rsi
0x1800184f5  pop     rbp
0x1800184f6  retn
0x1800184f7  cmp     qword ptr [rbx], 0
0x1800184fb  jnz     short loc_1800184CD
0x1800184fd  jmp     loc_18001846F
0x180018502  call    ?_Throw_bad_variant_access@std@@YAXXZ; std::_Throw_bad_variant_access(void)
0x180018508  mov     ecx, 7
0x18001850d  int     29h; Win8: RtlFailFast(ecx)
0x18001850f  jmp     loc_1800182EC
0x180018514  mov     edx, 4
0x180018519  mov     r15d, 0E8h
0x18001851f  jmp     loc_180018233
0x180018524  mov     edx, 3
0x180018529  mov     r15d, 0A8h
0x18001852f  jmp     loc_180018233
0x180018534  call    ?_Throw_bad_variant_access@std@@YAXXZ; std::_Throw_bad_variant_access(void)
0x18001853a  mov     rcx, rbx
0x18001853d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018542  mov     rax, [r12]
0x180018546  mov     [rsp+120h+var_F0], rax
0x18001854b  lea     rcx, [rsp+120h+var_F0]
0x180018550  call    ??1?$com_ptr_t@VAsyncHRESULTPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>::~com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>(void)
0x180018555  movups  xmm0, xmmword ptr [r15+r14+40h]
0x18001855b  movaps  [rbp+3Fh+var_80], xmm0
0x18001855f  movups  xmm1, xmmword ptr [r15+r14+50h]
0x180018565  movaps  [rbp+3Fh+var_70], xmm1
0x180018569  movsd   xmm0, qword ptr [r15+r14+60h]
0x180018570  movsd   qword ptr [rbp+3Fh+var_60], xmm0
0x180018575  mov     r9, rbx
0x180018578  lea     r8, [rsp+120h+var_F0]
0x18001857d  lea     rdx, [rbp+3Fh+var_80]
0x180018581  mov     rcx, r13
0x180018584  call    ?CreateAndRegisterTarget@DWMInputRouter@@IEAAJUtagMsgRoutingInfo@@V?$ComPtr@VInputSite@@@WRL@Microsoft@@PEAPEAUIInputTarget@@@Z; DWMInputRouter::CreateAndRegisterTarget(tagMsgRoutingInfo,Microsoft::WRL::ComPtr<InputSite>,IInputTarget * *)
0x180018589  jmp     loc_180018460
0x18001858e  test    sil, 4
0x180018592  jnz     short loc_1800185B1
0x180018594  mov     rcx, [rbp+47h]; this
0x180018598  lea     r9, aInvalidInputTy; "Invalid input type provided."
0x18001859f  lea     r8, aOnecoreuapWind_124; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800185a6  mov     edx, 0B7h; void *
0x1800185ab  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x1800185b1  mov     edx, 2
0x1800185b6  mov     r15d, 68h ; 'h'
0x1800185bc  jmp     loc_180018233
0x1800185c1  cmp     byte ptr [rdi+58h], 0
0x1800185c5  jz      loc_1800184F7
0x1800185cb  lea     rcx, [r14+30h]; this
0x1800185cf  call    ?GetLuid@LegacyInputSinkData@@QEBAAEBU_LUID@@XZ; LegacyInputSinkData::GetLuid(void)
0x1800185d4  mov     rcx, rax
0x1800185d7  mov     rdx, [rbp+3Fh+arg_28]
0x1800185db  call    ??8@YA_NAEBU_LUID@@0@Z; operator==(_LUID const &,_LUID const &)
0x1800185e0  test    al, al
0x1800185e2  jz      loc_1800184F7
0x1800185e8  mov     [rsp+120h+var_F0], 0
0x1800185f1  lea     rdx, [rsp+120h+var_F0]
0x1800185f6  mov     rcx, rbx
0x1800185f9  call    ??$As@UIDCompInputTarget@@@?$ComPtr@UIInputTarget@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDCompInputTarget@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInputTarget>::As<IDCompInputTarget>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDCompInputTarget>>)
0x1800185fe  test    eax, eax
0x180018600  js      short loc_180018617
0x180018602  mov     rcx, [rsp+120h+var_F0]
0x180018607  mov     rax, [rcx]
0x18001860a  mov     edx, [rdi+5Ch]
0x18001860d  mov     rax, [rax+50h]
0x180018611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018616  nop
0x180018617  lea     rcx, [rsp+120h+var_F0]
0x18001861c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018621  jmp     loc_1800184F7
```
