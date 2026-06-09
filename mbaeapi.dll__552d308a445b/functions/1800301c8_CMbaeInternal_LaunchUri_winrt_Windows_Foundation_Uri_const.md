# CMbaeInternal::_LaunchUri(winrt::Windows::Foundation::Uri const &)

- ea: `0x1800301c8`
- end: `0x1800305c8`
- name: `?_LaunchUri@CMbaeInternal@@AEAAXAEBUUri@Foundation@Windows@winrt@@@Z`
- size: `1024`
- prototype: `void __fastcall(CMbaeInternal *__hidden this, const struct winrt::Windows::Foundation::Uri *)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18002e610`
- `0x18002fe84`

## callees

- `0x180002fcb`
- `0x18000302b`
- `0x180004fb4`
- `0x180016254`
- `0x1800163ec`
- `0x18002b724`
- `0x18002bff4`
- `0x18002c1e0`
- `0x18002d508`
- `0x18002f064`
- `0x18002f090`
- `0x1800301c8`
- `0x180030790`
- `0x1800307b0`
- `0x180030d68`
- `0x180030ec0`
- `0x1800311d8`
- `0x18005c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180030392`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800303a1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180030503`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180030392`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800303a1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180030503`

## string_xrefs

- `0x18003028d`: `CMbaeInternal::_LaunchUri`
- `0x18003044b`: `CMbaeInternal::_LaunchUri`

## pseudocode

```c
void __fastcall CMbaeInternal::_LaunchUri(CMbaeInternal *this, const struct winrt::Windows::Foundation::Uri *a2)
{
  char v3; // di
  __int64 v4; // rax
  const unsigned __int16 *v5; // rsi
  const unsigned __int16 *v6; // r15
  int v7; // eax
  int v8; // ecx
  volatile signed __int32 *v9; // rbx
  int v10; // eax
  HANDLE ProcessHeap; // rax
  void *v12; // rbx
  int v13; // eax
  HANDLE v14; // rax
  int v15; // eax
  LPVOID v16; // rbx
  int v17; // edi
  unsigned int v18; // r8d
  int v19; // edi
  __int64 v20; // rax
  __int64 v21; // rcx
  const unsigned __int16 *v22; // rsi
  void *v23; // rbx
  int v24; // eax
  HANDLE v25; // rax
  int v26; // eax
  LPVOID v27; // rbx
  char v28; // di
  unsigned int v29; // eax
  void *v30; // rdx
  unsigned int v31; // r8d
  unsigned int v32; // [rsp+20h] [rbp-40h]
  LPVOID v33[2]; // [rsp+30h] [rbp-30h] BYREF
  int v34; // [rsp+40h] [rbp-20h] BYREF
  const char *v35; // [rsp+48h] [rbp-18h]
  __int64 v36; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  LPVOID v38; // [rsp+90h] [rbp+30h] BYREF
  __int64 v39; // [rsp+A0h] [rbp+40h] BYREF
  LPVOID lpMem; // [rsp+A8h] [rbp+48h] BYREF

  HIDWORD(v38) = HIDWORD(this);
  v3 = 0;
  LODWORD(v38) = 0;
  CMbaeInternal::_TryGetFirstUserIfDsma(this, &v39);
  if ( v39 )
  {
    if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 1) != 0 )
    {
      v4 = winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::AbsoluteUri(
             a2,
             v33);
      LODWORD(v38) = 1;
      v5 = &dword_1800684AC;
      if ( *(_QWORD *)v4 )
        v6 = *(const unsigned __int16 **)(*(_QWORD *)v4 + 16LL);
      else
        v6 = &dword_1800684AC;
      lpMem = 0;
      v34 = 4006;
      v35 = "onecoreuap\\Internal\\BuildMetadata\\cppwinrt\\winrt\\Windows.System.h";
      v36 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v39 + 48LL))(v39, &lpMem);
      if ( v7 < 0 )
        winrt::throw_hresult((unsigned int)v7, &v34);
      v9 = (volatile signed __int32 *)lpMem;
      v3 = 11;
      if ( lpMem )
        v5 = (const unsigned __int16 *)*((_QWORD *)lpMem + 2);
      McTemplateU0szz_EventWriteTransfer(
        v8,
        (unsigned int)CMbaeInternal_cpp372,
        (unsigned int)"CMbaeInternal::_LaunchUri",
        (_DWORD)v5,
        (__int64)v6);
    }
    else
    {
      v9 = (volatile signed __int32 *)v38;
    }
    if ( (v3 & 2) != 0 )
    {
      v3 &= ~2u;
      if ( v9 )
      {
        v10 = _InterlockedDecrement(v9 + 6);
        if ( v10 )
        {
          if ( v10 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v9);
        }
      }
    }
    if ( (v3 & 1) != 0 )
    {
      v12 = v33[0];
      if ( v33[0] )
      {
        v13 = _InterlockedDecrement((volatile signed __int32 *)v33[0] + 6);
        if ( v13 )
        {
          if ( v13 < 0 )
            abort();
        }
        else
        {
          v14 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v14, 0, v12);
        }
      }
    }
    v33[0] = &v39;
    v33[1] = a2;
    lpMem = &qword_1800887C8;
    _InterlockedIncrement64(&qword_1800887C8);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics4> )
    {
      v38 = 0;
      v34 = 2950;
      v35 = "onecoreuap\\Internal\\BuildMetadata\\cppwinrt\\winrt/Windows.System.h";
      v36 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPVOID *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics4>
                                                                          + 72LL))(
              winrt::impl::factory_cache_entry_v<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics4>,
              v39,
              *(_QWORD *)a2,
              &v38);
      if ( v15 < 0 )
        winrt::throw_hresult((unsigned int)v15, &v34);
      v16 = v38;
      _InterlockedDecrement64(&qword_1800887C8);
    }
    else
    {
      _InterlockedDecrement64(&qword_1800887C8);
      ___call_AEAV_lambda_1___1__LaunchUriForUserAsync_Launcher_System_Windows_winrt__SA_AEBUUser_456_AEBUUri_Foundation_56__Z____factory_cache_entry_ULauncher_System_Windows_winrt__UILauncherStatics4_234__impl_winrt__QEAA_A_PAEAV_lambda_1___1__LaunchUriForUserAsync_Launcher_System_Windows_2_SA_AEBUUser_672_AEBUUri_Foundation_72__Z__Z(
        0,
        &v38,
        v33);
      v16 = v38;
    }
    v17 = winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::System::LaunchUriStatus>,enum winrt::Windows::System::LaunchUriStatus>::get(&v38);
    if ( v16 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
    if ( v17 )
    {
      v19 = v17 - 1;
      if ( v19 )
      {
        if ( v19 == 1 )
          wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x17D, v18, (const char *)0x32, v32);
        v29 = wil::verify_hresult<long>(2147500037LL);
        wil::details::in1diag3::Throw_Hr(retaddr, v30, v31, (const char *)v29, v32);
      }
      wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x17B, v18, (const char *)2, v32);
    }
  }
  else
  {
    if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 1) != 0 )
    {
      v20 = winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::AbsoluteUri(
              a2,
              &v38);
      v3 = 4;
      if ( *(_QWORD *)v20 )
        v22 = *(const unsigned __int16 **)(*(_QWORD *)v20 + 16LL);
      else
        v22 = &dword_1800684AC;
      McTemplateU0sz_EventWriteTransfer(v21, CMbaeInternal_cpp388, "CMbaeInternal::_LaunchUri", v22);
    }
    if ( (v3 & 4) != 0 )
    {
      v23 = v38;
      if ( v38 )
      {
        v24 = _InterlockedDecrement((volatile signed __int32 *)v38 + 6);
        if ( v24 )
        {
          if ( v24 < 0 )
            abort();
        }
        else
        {
          v25 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v25, 0, v23);
        }
      }
    }
    lpMem = a2;
    v33[0] = &qword_1800887A8;
    _InterlockedIncrement64(&qword_1800887A8);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics> )
    {
      v38 = 0;
      v34 = 2644;
      v35 = "onecoreuap\\Internal\\BuildMetadata\\cppwinrt\\winrt/Windows.System.h";
      v36 = 0;
      v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics>
                                                                 + 64LL))(
              winrt::impl::factory_cache_entry_v<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics>,
              *(_QWORD *)a2,
              &v38);
      if ( v26 < 0 )
        winrt::throw_hresult((unsigned int)v26, &v34);
      v27 = v38;
      _InterlockedDecrement64(&qword_1800887A8);
    }
    else
    {
      _InterlockedDecrement64(&qword_1800887A8);
      ___call_AEAV_lambda_1___1__LaunchUriAsync_Launcher_System_Windows_winrt__SA_AEBUUri_Foundation_56__Z____factory_cache_entry_ULauncher_System_Windows_winrt__UILauncherStatics_234__impl_winrt__QEAA_A_PAEAV_lambda_1___1__LaunchUriAsync_Launcher_System_Windows_2_SA_AEBUUri_Foundation_72__Z__Z(
        0,
        &v38,
        &lpMem);
      v27 = v38;
    }
    v28 = winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<bool>,bool>::get(&v38);
    if ( v27 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
    if ( !v28 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x186,
        (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
        (const char *)0x8000FFFFLL,
        v32);
  }
  if ( v39 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v39);
}

```

## disassembly

```asm
0x1800301c8  mov     [rsp-28h+arg_8], rbx
0x1800301cd  mov     [rsp-28h+arg_0], rcx
0x1800301d2  push    rbp
0x1800301d3  push    rsi
0x1800301d4  push    rdi
0x1800301d5  push    r14
0x1800301d7  push    r15
0x1800301d9  mov     rbp, rsp
0x1800301dc  sub     rsp, 60h
0x1800301e0  mov     r14, rdx
0x1800301e3  xor     edi, edi
0x1800301e5  mov     dword ptr [rbp+arg_0], edi
0x1800301e8  lea     rdx, [rbp+arg_10]
0x1800301ec  call    ?_TryGetFirstUserIfDsma@CMbaeInternal@@AEAA?AUUser@System@Windows@winrt@@XZ; CMbaeInternal::_TryGetFirstUserIfDsma(void)
0x1800301f1  nop
0x1800301f2  cmp     [rbp+arg_10], rdi
0x1800301f6  jz      loc_180030419
0x1800301fc  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 1
0x180030203  jz      loc_1800302A2
0x180030209  lea     rdx, [rbp+var_30]
0x18003020d  mov     rcx, r14
0x180030210  call    ?AbsoluteUri@?$consume_Windows_Foundation_IUriRuntimeClass@UIUriRuntimeClass@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::AbsoluteUri(void)
0x180030215  nop
0x180030216  mov     dword ptr [rbp+arg_0], 1
0x18003021d  mov     rcx, [rax]
0x180030220  lea     rsi, dword_1800684AC
0x180030227  test    rcx, rcx
0x18003022a  jz      short loc_180030232
0x18003022c  mov     r15, [rcx+10h]
0x180030230  jmp     short loc_180030235
0x180030232  mov     r15, rsi
0x180030235  mov     [rbp+lpMem], 0
0x18003023d  mov     rcx, [rbp+arg_10]
0x180030241  mov     [rbp+var_20], 0FA6h
0x180030248  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\cp"...
0x18003024f  mov     [rbp+var_18], rax
0x180030253  mov     [rbp+var_10], 0
0x18003025b  mov     rax, [rcx]
0x18003025e  lea     rdx, [rbp+lpMem]
0x180030262  mov     rax, [rax+30h]
0x180030266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003026b  test    eax, eax
0x18003026d  js      loc_180030586
0x180030273  mov     rbx, [rbp+lpMem]
0x180030277  mov     edi, 0Bh
0x18003027c  test    rbx, rbx
0x18003027f  jz      short loc_180030285
0x180030281  mov     rsi, [rbx+10h]
0x180030285  mov     qword ptr [rsp+60h+var_40], r15
0x18003028a  mov     r9, rsi
0x18003028d  lea     r8, aCmbaeinternalL_1; "CMbaeInternal::_LaunchUri"
0x180030294  lea     rdx, CMbaeInternal_cpp372
0x18003029b  call    McTemplateU0szz_EventWriteTransfer
0x1800302a0  jmp     short loc_1800302A6
0x1800302a2  mov     rbx, [rbp+arg_0]
0x1800302a6  test    dil, 2
0x1800302aa  jz      short loc_1800302D9
0x1800302ac  and     edi, 0FFFFFFFDh
0x1800302af  test    rbx, rbx
0x1800302b2  jz      short loc_1800302D9
0x1800302b4  or      eax, 0FFFFFFFFh
0x1800302b7  lock xadd [rbx+18h], eax
0x1800302bc  sub     eax, 1
0x1800302bf  jnz     loc_18003038A
0x1800302c5  nop
0x1800302c6  call    WINRT_IMPL_GetProcessHeap
0x1800302cb  mov     rcx, rax; hHeap
0x1800302ce  mov     r8, rbx; lpMem
0x1800302d1  xor     edx, edx; dwFlags
0x1800302d3  call    WINRT_IMPL_HeapFree
0x1800302d8  nop
0x1800302d9  test    dil, 1
0x1800302dd  jz      short loc_18003030C
0x1800302df  mov     rbx, [rbp+var_30]
0x1800302e3  test    rbx, rbx
0x1800302e6  jz      short loc_18003030C
0x1800302e8  or      eax, 0FFFFFFFFh
0x1800302eb  lock xadd [rbx+18h], eax
0x1800302f0  sub     eax, 1
0x1800302f3  jnz     loc_180030399
0x1800302f9  nop
0x1800302fa  call    WINRT_IMPL_GetProcessHeap
0x1800302ff  mov     rcx, rax; hHeap
0x180030302  mov     r8, rbx; lpMem
0x180030305  xor     edx, edx; dwFlags
0x180030307  call    WINRT_IMPL_HeapFree
0x18003030c  lea     rax, [rbp+arg_10]
0x180030310  mov     [rbp+var_30], rax
0x180030314  mov     [rbp+var_28], r14
0x180030318  lea     rax, qword_1800887C8
0x18003031f  mov     [rbp+lpMem], rax
0x180030323  lock inc cs:qword_1800887C8
0x18003032b  mov     rcx, cs:??$factory_cache_entry_v@ULauncher@System@Windows@winrt@@UILauncherStatics4@234@@impl@winrt@@3U?$factory_cache_entry@ULauncher@System@Windows@winrt@@UILauncherStatics4@234@@12@A; factory_cache_entry<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics4>::winrt::factory_cache_entry<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics4> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics4>
0x180030332  test    rcx, rcx
0x180030335  jz      short loc_1800303A8
0x180030337  mov     [rbp+arg_0], 0
0x18003033f  mov     [rbp+var_20], 0B86h
0x180030346  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\cp"...
0x18003034d  mov     [rbp+var_18], rax
0x180030351  mov     [rbp+var_10], 0
0x180030359  mov     rax, [rcx]
0x18003035c  lea     r9, [rbp+arg_0]
0x180030360  mov     r8, [r14]
0x180030363  mov     rdx, [rbp+arg_10]
0x180030367  mov     rax, [rax+48h]
0x18003036b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030370  test    eax, eax
0x180030372  js      loc_180030592
0x180030378  mov     rbx, [rbp+arg_0]
0x18003037c  mov     [rbp+arg_0], rbx
0x180030380  lock dec cs:qword_1800887C8
0x180030388  jmp     short loc_1800303C1
0x18003038a  test    eax, eax
0x18003038c  jns     loc_1800302D9
0x180030392  call    cs:__imp_abort
0x180030399  test    eax, eax
0x18003039b  jns     loc_18003030C
0x1800303a1  call    cs:__imp_abort
0x1800303a8  lock dec cs:qword_1800887C8
0x1800303b0  lea     r8, [rbp+var_30]
0x1800303b4  lea     rdx, [rbp+arg_0]
0x1800303b8  call    ??$call@AEAV_lambda_1_@?1??LaunchUriForUserAsync@Launcher@System@Windows@winrt@@SA@AEBUUser@456@AEBUUri@Foundation@56@@Z@@?$factory_cache_entry@ULauncher@System@Windows@winrt@@UILauncherStatics4@234@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??LaunchUriForUserAsync@Launcher@System@Windows@2@SA@AEBUUser@672@AEBUUri@Foundation@72@@Z@@Z
0x1800303bd  mov     rbx, [rbp+arg_0]
0x1800303c1  lea     rcx, [rbp+arg_0]
0x1800303c5  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@W4LaunchUriStatus@System@Windows@winrt@@@Foundation@Windows@winrt@@W4LaunchUriStatus@System@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::System::LaunchUriStatus>,winrt::Windows::System::LaunchUriStatus>::get(void)
0x1800303ca  mov     edi, eax
0x1800303cc  test    rbx, rbx
0x1800303cf  jz      short loc_1800303DA
0x1800303d1  lea     rcx, [rbp+arg_0]
0x1800303d5  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800303da  test    edi, edi
0x1800303dc  jz      short loc_1800303F5
0x1800303de  sub     edi, 1
0x1800303e1  jz      loc_1800305B3
0x1800303e7  cmp     edi, 1
0x1800303ea  jnz     loc_180030557
0x1800303f0  jmp     loc_18003059E
0x1800303f5  cmp     [rbp+arg_10], 0
0x1800303fa  jz      short loc_180030405
0x1800303fc  lea     rcx, [rbp+arg_10]
0x180030400  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180030405  mov     rbx, [rsp+60h+arg_8]
0x18003040d  add     rsp, 60h
0x180030411  pop     r15
0x180030413  pop     r14
0x180030415  pop     rdi
0x180030416  pop     rsi
0x180030417  pop     rbp
0x180030418  retn
0x180030419  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 1
0x180030420  jz      short loc_18003045E
0x180030422  lea     rdx, [rbp+arg_0]
0x180030426  mov     rcx, r14
0x180030429  call    ?AbsoluteUri@?$consume_Windows_Foundation_IUriRuntimeClass@UIUriRuntimeClass@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::AbsoluteUri(void)
0x18003042e  mov     edi, 4
0x180030433  mov     rsi, [rax]
0x180030436  test    rsi, rsi
0x180030439  jz      short loc_180030441
0x18003043b  mov     rsi, [rsi+10h]
0x18003043f  jmp     short loc_180030448
0x180030441  lea     rsi, dword_1800684AC
0x180030448  mov     r9, rsi
0x18003044b  lea     r8, aCmbaeinternalL_1; "CMbaeInternal::_LaunchUri"
0x180030452  lea     rdx, CMbaeInternal_cpp388
0x180030459  call    McTemplateU0sz_EventWriteTransfer
0x18003045e  test    dil, 4
0x180030462  jz      short loc_180030491
0x180030464  mov     rbx, [rbp+arg_0]
0x180030468  test    rbx, rbx
0x18003046b  jz      short loc_180030491
0x18003046d  or      eax, 0FFFFFFFFh
0x180030470  lock xadd [rbx+18h], eax
0x180030475  sub     eax, 1
0x180030478  jnz     loc_1800304FF
0x18003047e  nop
0x18003047f  call    WINRT_IMPL_GetProcessHeap
0x180030484  mov     rcx, rax; hHeap
0x180030487  mov     r8, rbx; lpMem
0x18003048a  xor     edx, edx; dwFlags
0x18003048c  call    WINRT_IMPL_HeapFree
0x180030491  mov     [rbp+lpMem], r14
0x180030495  lea     rax, qword_1800887A8
0x18003049c  mov     [rbp+var_30], rax
0x1800304a0  lock inc cs:qword_1800887A8
0x1800304a8  mov     rcx, cs:??$factory_cache_entry_v@ULauncher@System@Windows@winrt@@UILauncherStatics@234@@impl@winrt@@3U?$factory_cache_entry@ULauncher@System@Windows@winrt@@UILauncherStatics@234@@12@A; factory_cache_entry<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics>::winrt::factory_cache_entry<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Launcher,winrt::Windows::System::ILauncherStatics>
0x1800304af  test    rcx, rcx
0x1800304b2  jz      short loc_18003050A
0x1800304b4  mov     [rbp+arg_0], 0
0x1800304bc  mov     [rbp+var_20], 0A54h
0x1800304c3  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\cp"...
0x1800304ca  mov     [rbp+var_18], rax
0x1800304ce  mov     [rbp+var_10], 0
0x1800304d6  mov     rax, [rcx]
0x1800304d9  lea     r8, [rbp+arg_0]
0x1800304dd  mov     rdx, [r14]
0x1800304e0  mov     rax, [rax+40h]
0x1800304e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304e9  test    eax, eax
0x1800304eb  js      short loc_18003054B
0x1800304ed  mov     rbx, [rbp+arg_0]
0x1800304f1  mov     [rbp+arg_0], rbx
0x1800304f5  lock dec cs:qword_1800887A8
0x1800304fd  jmp     short loc_180030523
0x1800304ff  test    eax, eax
0x180030501  jns     short loc_180030491
0x180030503  call    cs:__imp_abort
0x18003050a  lock dec cs:qword_1800887A8
0x180030512  lea     r8, [rbp+lpMem]
0x180030516  lea     rdx, [rbp+arg_0]
0x18003051a  call    ??$call@AEAV_lambda_1_@?1??LaunchUriAsync@Launcher@System@Windows@winrt@@SA@AEBUUri@Foundation@56@@Z@@?$factory_cache_entry@ULauncher@System@Windows@winrt@@UILauncherStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??LaunchUriAsync@Launcher@System@Windows@2@SA@AEBUUri@Foundation@72@@Z@@Z
0x18003051f  mov     rbx, [rbp+arg_0]
0x180030523  lea     rcx, [rbp+arg_0]
0x180030527  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@_N@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<bool>,bool>::get(void)
0x18003052c  mov     dil, al
0x18003052f  test    rbx, rbx
0x180030532  jz      short loc_18003053D
0x180030534  lea     rcx, [rbp+arg_0]
0x180030538  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003053d  mov     rcx, [rbp+28h]; this
0x180030541  test    dil, dil
0x180030544  jz      short loc_18003056E
0x180030546  jmp     loc_1800303F5
0x18003054b  lea     rdx, [rbp+var_20]
0x18003054f  mov     ecx, eax
0x180030551  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180030557  mov     ecx, 80004005h
0x18003055c  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180030561  mov     r9d, eax; char *
0x180030564  mov     rcx, [rbp+28h]; this
0x180030568  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003056e  mov     r9d, 8000FFFFh; char *
0x180030574  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18003057b  mov     edx, 186h; void *
0x180030580  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180030586  lea     rdx, [rbp+var_20]
0x18003058a  mov     ecx, eax
0x18003058c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180030592  lea     rdx, [rbp+var_20]
0x180030596  mov     ecx, eax
0x180030598  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003059e  mov     rcx, [rbp+28h]; this
0x1800305a2  mov     edx, 17Dh; void *
0x1800305a7  mov     r9d, 32h ; '2'; char *
0x1800305ad  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800305b3  mov     rcx, [rbp+28h]; this
0x1800305b7  mov     edx, 17Bh; void *
0x1800305bc  mov     r9d, 2; char *
0x1800305c2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
