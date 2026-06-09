# ExpeditedUpdateUSOTask::DownloadInstallRun(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *)

- ea: `0x180079120`
- end: `0x18007970d`
- name: `?DownloadInstallRun@ExpeditedUpdateUSOTask@@UEAAJPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Z`
- size: `1517`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180008544`
- `0x1800230b0`
- `0x180039b04`
- `0x180060014`
- `0x180079120`
- `0x18007c410`
- `0x18007c614`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180079269`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180079269`

## string_xrefs

- `0x18007937b`: `ExpeditedUpdateStatus`
- `0x1800795c2`: `ExpeditedUpdateStatus`
- `0x180079158`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x180079188`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x1800791ad`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x18007920c`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x1800792a7`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x180079300`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x180079399`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x180079406`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x180079470`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x1800794ee`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x180079547`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x1800795e0`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x18007964d`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x180079277`: `ExpeditedUpdateUSOTask starting filter process`
- `0x1800793ed`: `ExpeditedUpdateUSOTask filtering failed HResult code [hr=0x%08X]`
- `0x1800794c1`: `ExpeditedUpdateUSOTask starting download/install process`
- `0x180079634`: `ExpeditedUpdateUSOTask download/install failed HResult code [hr=0x%08X]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall ExpeditedUpdateUSOTask::DownloadInstallRun(__int64 a1, __int64 a2)
{
  __int64 v4; // r15
  int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rcx
  int v12; // eax
  unsigned int v13; // r14d
  __int64 v14; // rcx
  int v15; // eax
  unsigned int v16; // esi
  int v17; // eax
  unsigned int v18; // edi
  __int64 v19; // rcx
  int v20; // eax
  unsigned int v21; // r14d
  __int64 v22; // rcx
  int v23; // eax
  unsigned int v24; // esi
  int v25[4]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v26; // [rsp+30h] [rbp-38h]
  __int128 v27; // [rsp+38h] [rbp-30h] BYREF
  __int64 v28; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v30; // [rsp+70h] [rbp+8h] BYREF

  v4 = a1 - 568;
  if ( !*(_QWORD *)(a1 - 568 + 656) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x179,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
      (const char *)0x8000FFFFLL,
      v25[0]);
    return 2147549183LL;
  }
  if ( !*(_QWORD *)(a1 + 104) )
  {
    v6 = -2147023728;
    v7 = 378;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
      (const char *)(unsigned int)v6,
      v25[0]);
    return (unsigned int)v6;
  }
  if ( !a2 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
      (const char *)0x80070057LL,
      v25[0]);
LABEL_11:
    v7 = 379;
    goto LABEL_5;
  }
  v30 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 56LL))(a2, &v30);
  if ( v6 < 0 )
    goto LABEL_11;
  if ( !v30 )
  {
    v6 = -2147024809;
    goto LABEL_11;
  }
  v8 = *(_QWORD *)(a1 + 104);
  if ( !v8 )
  {
    v6 = -2147023728;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
      (const char *)0x80070490LL,
      v25[0]);
LABEL_17:
    v7 = 380;
    goto LABEL_5;
  }
  v30 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 32LL))(v8, &v30);
  if ( v6 < 0 )
    goto LABEL_17;
  if ( !v30 )
  {
    v6 = -2147023728;
    goto LABEL_17;
  }
  *(_OWORD *)v25 = 0;
  v26 = 0;
  if ( !WaitForSingleObject(*(HANDLE *)(a1 + 32), 0) )
    goto LABEL_47;
  UnattendLogW(0, L"ExpeditedUpdateUSOTask starting filter process");
  v9 = ExpeditedUpdateUSOTask::_FilterUpdates(v4, a2, v25);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x185,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
      (const char *)(unsigned int)v9,
      v25[0]);
    v11 = *(_QWORD *)(a1 + 72);
    v27 = 0;
    v28 = 0;
    LOWORD(v27) = 19;
    DWORD2(v27) = v10;
    v12 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, __int128 *))(*(_QWORD *)v11 + 32LL))(
            v11,
            L"StatusCode",
            &v27);
    v13 = v12;
    if ( v12 >= 0 )
    {
      v14 = *(_QWORD *)(a1 + 72);
      v27 = 0;
      v28 = 0;
      LOWORD(v27) = 19;
      DWORD2(v27) = 14;
      v15 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, __int128 *))(*(_QWORD *)v14 + 32LL))(
              v14,
              L"ExpeditedUpdateStatus",
              &v27);
      v16 = v15;
      if ( v15 >= 0 )
      {
        UnattendLogW(1, L"ExpeditedUpdateUSOTask filtering failed HResult code [hr=0x%08X]", v10);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18A,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)v10,
          v25[0]);
        if ( *(_QWORD *)v25 )
        {
          std::_Destroy_range<std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>>(
            *(__int64 *)v25,
            *(__int64 *)&v25[2]);
          std::_Deallocate<16>(*(void **)v25, (struct std::nothrow_t *)((v26 - *(_QWORD *)v25) & 0xFFFFFFFFFFFFFFF8uLL));
          *(_OWORD *)v25 = 0;
          v26 = 0;
        }
        return v10;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x188,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)(unsigned int)v15,
          v25[0]);
        if ( *(_QWORD *)v25 )
        {
          std::_Destroy_range<std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>>(
            *(__int64 *)v25,
            *(__int64 *)&v25[2]);
          std::_Deallocate<16>(*(void **)v25, (struct std::nothrow_t *)((v26 - *(_QWORD *)v25) & 0xFFFFFFFFFFFFFFF8uLL));
          *(_OWORD *)v25 = 0;
          v26 = 0;
        }
        return v16;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x187,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)v12,
        v25[0]);
      if ( *(_QWORD *)v25 )
      {
        std::_Destroy_range<std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>>(
          *(__int64 *)v25,
          *(__int64 *)&v25[2]);
        std::_Deallocate<16>(*(void **)v25, (struct std::nothrow_t *)((v26 - *(_QWORD *)v25) & 0xFFFFFFFFFFFFFFF8uLL));
        *(_OWORD *)v25 = 0;
        v26 = 0;
      }
      return v13;
    }
  }
  if ( *(_QWORD *)&v25[2] == *(_QWORD *)v25 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18D,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
      (const char *)0x80070057LL,
      v25[0]);
    if ( *(_QWORD *)v25 )
    {
      std::_Destroy_range<std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>>(
        *(__int64 *)v25,
        *(__int64 *)&v25[2]);
      std::_Deallocate<16>(*(void **)v25, (struct std::nothrow_t *)((v26 - *(_QWORD *)v25) & 0xFFFFFFFFFFFFFFF8uLL));
      *(_OWORD *)v25 = 0;
      v26 = 0;
    }
    return 2147942487LL;
  }
  UnattendLogW(0, L"ExpeditedUpdateUSOTask starting download/install process");
  v17 = ExpeditedUpdateUSOTask::_DownloadAndInstall(v4, v25);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
      (const char *)(unsigned int)v17,
      v25[0]);
    v19 = *(_QWORD *)(a1 + 72);
    v27 = 0;
    v28 = 0;
    LOWORD(v27) = 19;
    DWORD2(v27) = v18;
    v20 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, __int128 *))(*(_QWORD *)v19 + 32LL))(
            v19,
            L"StatusCode",
            &v27);
    v21 = v20;
    if ( v20 >= 0 )
    {
      v22 = *(_QWORD *)(a1 + 72);
      v27 = 0;
      v28 = 0;
      LOWORD(v27) = 19;
      DWORD2(v27) = 14;
      v23 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, __int128 *))(*(_QWORD *)v22 + 32LL))(
              v22,
              L"ExpeditedUpdateStatus",
              &v27);
      v24 = v23;
      if ( v23 >= 0 )
      {
        UnattendLogW(1, L"ExpeditedUpdateUSOTask download/install failed HResult code [hr=0x%08X]", v18);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x198,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)v18,
          v25[0]);
        if ( *(_QWORD *)v25 )
        {
          std::_Destroy_range<std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>>(
            *(__int64 *)v25,
            *(__int64 *)&v25[2]);
          std::_Deallocate<16>(*(void **)v25, (struct std::nothrow_t *)((v26 - *(_QWORD *)v25) & 0xFFFFFFFFFFFFFFF8uLL));
          *(_OWORD *)v25 = 0;
          v26 = 0;
        }
        return v18;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x196,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)(unsigned int)v23,
          v25[0]);
        if ( *(_QWORD *)v25 )
        {
          std::_Destroy_range<std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>>(
            *(__int64 *)v25,
            *(__int64 *)&v25[2]);
          std::_Deallocate<16>(*(void **)v25, (struct std::nothrow_t *)((v26 - *(_QWORD *)v25) & 0xFFFFFFFFFFFFFFF8uLL));
          *(_OWORD *)v25 = 0;
          v26 = 0;
        }
        return v24;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x195,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
        (const char *)(unsigned int)v20,
        v25[0]);
      if ( *(_QWORD *)v25 )
      {
        std::_Destroy_range<std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>>(
          *(__int64 *)v25,
          *(__int64 *)&v25[2]);
        std::_Deallocate<16>(*(void **)v25, (struct std::nothrow_t *)((v26 - *(_QWORD *)v25) & 0xFFFFFFFFFFFFFFF8uLL));
        *(_OWORD *)v25 = 0;
        v26 = 0;
      }
      return v21;
    }
  }
  else
  {
LABEL_47:
    if ( *(_QWORD *)v25 )
    {
      std::_Destroy_range<std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>>(
        *(__int64 *)v25,
        *(__int64 *)&v25[2]);
      std::_Deallocate<16>(*(void **)v25, (struct std::nothrow_t *)((v26 - *(_QWORD *)v25) & 0xFFFFFFFFFFFFFFF8uLL));
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180079120  mov     [rsp+arg_8], rbx
0x180079125  mov     [rsp+arg_10], rsi
0x18007912a  push    rdi
0x18007912b  push    r14
0x18007912d  push    r15
0x18007912f  sub     rsp, 50h
0x180079133  mov     r14, rdx
0x180079136  mov     rsi, rcx
0x180079139  lea     r15, [rcx-238h]
0x180079140  xor     ebx, ebx
0x180079142  cmp     [r15+290h], rbx
0x180079149  jnz     short loc_180079170
0x18007914b  mov     rcx, [rsp+68h]; this
0x180079150  mov     ebx, 8000FFFFh
0x180079155  mov     r9d, ebx; char *
0x180079158  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007915f  mov     edx, 179h; void *
0x180079164  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079169  mov     eax, ebx
0x18007916b  jmp     loc_1800796F7
0x180079170  cmp     [rcx+68h], rbx
0x180079174  jnz     short loc_18007919B
0x180079176  mov     edi, 80070490h
0x18007917b  mov     edx, 17Ah; void *
0x180079180  mov     rcx, [rsp+68h]; this
0x180079185  mov     r9d, edi; char *
0x180079188  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007918f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079194  mov     eax, edi
0x180079196  jmp     loc_1800796F7
0x18007919b  test    r14, r14
0x18007919e  jnz     short loc_1800791C0
0x1800791a0  mov     rcx, [rsp+68h]; this
0x1800791a5  mov     edi, 80070057h
0x1800791aa  mov     r9d, edi; char *
0x1800791ad  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800791b4  mov     edx, 1E2h; void *
0x1800791b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800791be  jmp     short loc_1800791EF
0x1800791c0  mov     [rsp+68h+arg_0], ebx
0x1800791c4  mov     rax, [rdx]
0x1800791c7  lea     rdx, [rsp+68h+arg_0]
0x1800791cc  mov     rcx, r14
0x1800791cf  mov     rax, [rax+38h]
0x1800791d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800791d8  mov     edi, eax
0x1800791da  test    eax, eax
0x1800791dc  js      short loc_1800791EF
0x1800791de  cmp     [rsp+68h+arg_0], ebx
0x1800791e2  jnz     short loc_1800791EB
0x1800791e4  mov     edi, 80070057h
0x1800791e9  jmp     short loc_1800791EF
0x1800791eb  test    eax, eax
0x1800791ed  jns     short loc_1800791F6
0x1800791ef  mov     edx, 17Bh
0x1800791f4  jmp     short loc_180079180
0x1800791f6  mov     rcx, [rsi+68h]
0x1800791fa  test    rcx, rcx
0x1800791fd  jnz     short loc_18007921F
0x1800791ff  mov     rcx, [rsp+68h]; this
0x180079204  mov     edi, 80070490h
0x180079209  mov     r9d, edi; char *
0x18007920c  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x180079213  mov     edx, 1CAh; void *
0x180079218  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007921d  jmp     short loc_18007924B
0x18007921f  mov     [rsp+68h+arg_0], ebx
0x180079223  mov     rax, [rcx]
0x180079226  lea     rdx, [rsp+68h+arg_0]
0x18007922b  mov     rax, [rax+20h]
0x18007922f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079234  mov     edi, eax
0x180079236  test    eax, eax
0x180079238  js      short loc_18007924B
0x18007923a  cmp     [rsp+68h+arg_0], ebx
0x18007923e  jnz     short loc_180079247
0x180079240  mov     edi, 80070490h
0x180079245  jmp     short loc_18007924B
0x180079247  test    eax, eax
0x180079249  jns     short loc_180079255
0x18007924b  mov     edx, 17Ch
0x180079250  jmp     loc_180079180
0x180079255  xorps   xmm0, xmm0
0x180079258  movdqu  xmmword ptr [rsp+68h+var_48], xmm0; int
0x18007925e  mov     [rsp+68h+var_38], rbx
0x180079263  xor     edx, edx; dwMilliseconds
0x180079265  mov     rcx, [rsi+20h]; hHandle
0x180079269  call    cs:__imp_WaitForSingleObject
0x18007926f  test    eax, eax
0x180079271  jz      loc_18007969B
0x180079277  lea     rdx, aExpeditedupdat_31; "ExpeditedUpdateUSOTask starting filter "...
0x18007927e  xor     ecx, ecx
0x180079280  call    UnattendLogW
0x180079285  lea     r8, [rsp+68h+var_48]
0x18007928a  mov     rdx, r14
0x18007928d  mov     rcx, r15
0x180079290  call    ?_FilterUpdates@ExpeditedUpdateUSOTask@@AEAAJPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@AEAV?$vector@V?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@Z; ExpeditedUpdateUSOTask::_FilterUpdates(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *,std::vector<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>> &)
0x180079295  mov     edi, eax
0x180079297  mov     rcx, [rsp+68h]; this
0x18007929c  test    eax, eax
0x18007929e  jns     loc_180079457
0x1800792a4  mov     r9d, eax; char *
0x1800792a7  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800792ae  mov     edx, 185h; void *
0x1800792b3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800792b8  mov     rcx, [rsi+48h]
0x1800792bc  xorps   xmm0, xmm0
0x1800792bf  xor     eax, eax
0x1800792c1  movups  [rsp+68h+var_30], xmm0
0x1800792c6  mov     [rsp+68h+var_20], rax
0x1800792cb  lea     r15d, [rax+13h]
0x1800792cf  mov     word ptr [rsp+68h+var_30], r15w
0x1800792d5  mov     dword ptr [rsp+68h+var_30+8], edi
0x1800792d9  mov     rax, [rcx]
0x1800792dc  lea     r8, [rsp+68h+var_30]
0x1800792e1  lea     rdx, aStatuscode; "StatusCode"
0x1800792e8  mov     rax, [rax+20h]
0x1800792ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800792f1  mov     r14d, eax
0x1800792f4  test    eax, eax
0x1800792f6  jns     short loc_180079352
0x1800792f8  mov     rcx, [rsp+68h]; this
0x1800792fd  mov     r9d, eax; char *
0x180079300  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x180079307  mov     edx, 187h; void *
0x18007930c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079311  nop
0x180079312  mov     rcx, qword ptr [rsp+68h+var_48]
0x180079317  test    rcx, rcx
0x18007931a  jz      short loc_18007934A
0x18007931c  mov     rdx, qword ptr [rsp+68h+var_48+8]
0x180079321  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>>(wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy> *,wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>> &)
0x180079326  mov     rcx, qword ptr [rsp+68h+var_48]
0x18007932b  mov     rdx, [rsp+68h+var_38]
0x180079330  sub     rdx, rcx
0x180079333  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180079337  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007933c  xorps   xmm0, xmm0
0x18007933f  movdqu  xmmword ptr [rsp+68h+var_48], xmm0
0x180079345  mov     [rsp+68h+var_38], rbx
0x18007934a  mov     eax, r14d
0x18007934d  jmp     loc_1800796F7
0x180079352  mov     rcx, [rsi+48h]
0x180079356  xorps   xmm0, xmm0
0x180079359  xor     eax, eax
0x18007935b  movups  [rsp+68h+var_30], xmm0
0x180079360  mov     [rsp+68h+var_20], rax
0x180079365  mov     word ptr [rsp+68h+var_30], r15w
0x18007936b  mov     dword ptr [rsp+68h+var_30+8], 0Eh
0x180079373  mov     rax, [rcx]
0x180079376  lea     r8, [rsp+68h+var_30]
0x18007937b  lea     rdx, aExpeditedupdat_15; "ExpeditedUpdateStatus"
0x180079382  mov     rax, [rax+20h]
0x180079386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007938b  mov     esi, eax
0x18007938d  test    eax, eax
0x18007938f  jns     short loc_1800793EA
0x180079391  mov     rcx, [rsp+68h]; this
0x180079396  mov     r9d, eax; char *
0x180079399  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800793a0  mov     edx, 188h; void *
0x1800793a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800793aa  nop
0x1800793ab  mov     rcx, qword ptr [rsp+68h+var_48]
0x1800793b0  test    rcx, rcx
0x1800793b3  jz      short loc_1800793E3
0x1800793b5  mov     rdx, qword ptr [rsp+68h+var_48+8]
0x1800793ba  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>>(wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy> *,wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>> &)
0x1800793bf  mov     rcx, qword ptr [rsp+68h+var_48]
0x1800793c4  mov     rdx, [rsp+68h+var_38]
0x1800793c9  sub     rdx, rcx
0x1800793cc  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800793d0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800793d5  xorps   xmm0, xmm0
0x1800793d8  movdqu  xmmword ptr [rsp+68h+var_48], xmm0
0x1800793de  mov     [rsp+68h+var_38], rbx
0x1800793e3  mov     eax, esi
0x1800793e5  jmp     loc_1800796F7
0x1800793ea  mov     r8d, edi
0x1800793ed  lea     rdx, aExpeditedupdat_57; "ExpeditedUpdateUSOTask filtering failed"...
0x1800793f4  mov     ecx, 1
0x1800793f9  call    UnattendLogW
0x1800793fe  mov     rcx, [rsp+68h]; this
0x180079403  mov     r9d, edi; char *
0x180079406  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007940d  mov     edx, 18Ah; void *
0x180079412  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079417  nop
0x180079418  mov     rcx, qword ptr [rsp+68h+var_48]
0x18007941d  test    rcx, rcx
0x180079420  jz      short loc_180079450
0x180079422  mov     rdx, qword ptr [rsp+68h+var_48+8]
0x180079427  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>>(wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy> *,wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>> &)
0x18007942c  mov     rcx, qword ptr [rsp+68h+var_48]
0x180079431  mov     rdx, [rsp+68h+var_38]
0x180079436  sub     rdx, rcx
0x180079439  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18007943d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180079442  xorps   xmm0, xmm0
0x180079445  movdqu  xmmword ptr [rsp+68h+var_48], xmm0
0x18007944b  mov     [rsp+68h+var_38], rbx
0x180079450  mov     eax, edi
0x180079452  jmp     loc_1800796F7
0x180079457  mov     rax, qword ptr [rsp+68h+var_48+8]
0x18007945c  cmp     rax, qword ptr [rsp+68h+var_48]
0x180079461  jnz     short loc_1800794C1
0x180079463  mov     rcx, [rsp+68h]; this
0x180079468  mov     edi, 80070057h
0x18007946d  mov     r9d, edi; char *
0x180079470  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x180079477  mov     edx, 18Dh; void *
0x18007947c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079481  nop
0x180079482  mov     rcx, qword ptr [rsp+68h+var_48]
0x180079487  test    rcx, rcx
0x18007948a  jz      short loc_1800794BA
0x18007948c  mov     rdx, qword ptr [rsp+68h+var_48+8]
0x180079491  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>>(wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy> *,wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>> &)
0x180079496  mov     rcx, qword ptr [rsp+68h+var_48]
0x18007949b  mov     rdx, [rsp+68h+var_38]
0x1800794a0  sub     rdx, rcx
0x1800794a3  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800794a7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800794ac  xorps   xmm0, xmm0
0x1800794af  movdqu  xmmword ptr [rsp+68h+var_48], xmm0
0x1800794b5  mov     [rsp+68h+var_38], rbx
0x1800794ba  mov     eax, edi
0x1800794bc  jmp     loc_1800796F7
0x1800794c1  lea     rdx, aExpeditedupdat_53; "ExpeditedUpdateUSOTask starting downloa"...
0x1800794c8  xor     ecx, ecx
0x1800794ca  call    UnattendLogW
0x1800794cf  lea     rdx, [rsp+68h+var_48]
0x1800794d4  mov     rcx, r15
0x1800794d7  call    ?_DownloadAndInstall@ExpeditedUpdateUSOTask@@AEAAJAEBV?$vector@V?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@Z; ExpeditedUpdateUSOTask::_DownloadAndInstall(std::vector<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>> const &)
0x1800794dc  mov     edi, eax
0x1800794de  mov     rcx, [rsp+68h]; this
0x1800794e3  test    eax, eax
0x1800794e5  jns     loc_18007969B
0x1800794eb  mov     r9d, eax; char *
0x1800794ee  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800794f5  mov     edx, 193h; void *
0x1800794fa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800794ff  mov     rcx, [rsi+48h]
0x180079503  xorps   xmm0, xmm0
0x180079506  xor     eax, eax
0x180079508  movups  [rsp+68h+var_30], xmm0
0x18007950d  mov     [rsp+68h+var_20], rax
0x180079512  lea     r15d, [rax+13h]
0x180079516  mov     word ptr [rsp+68h+var_30], r15w
0x18007951c  mov     dword ptr [rsp+68h+var_30+8], edi
0x180079520  mov     rax, [rcx]
0x180079523  lea     r8, [rsp+68h+var_30]
0x180079528  lea     rdx, aStatuscode; "StatusCode"
0x18007952f  mov     rax, [rax+20h]
0x180079533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079538  mov     r14d, eax
0x18007953b  test    eax, eax
0x18007953d  jns     short loc_180079599
0x18007953f  mov     rcx, [rsp+68h]; this
0x180079544  mov     r9d, eax; char *
0x180079547  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007954e  mov     edx, 195h; void *
0x180079553  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079558  nop
0x180079559  mov     rcx, qword ptr [rsp+68h+var_48]
0x18007955e  test    rcx, rcx
0x180079561  jz      short loc_180079591
0x180079563  mov     rdx, qword ptr [rsp+68h+var_48+8]
0x180079568  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>>(wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy> *,wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>> &)
0x18007956d  mov     rcx, qword ptr [rsp+68h+var_48]
0x180079572  mov     rdx, [rsp+68h+var_38]
0x180079577  sub     rdx, rcx
0x18007957a  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18007957e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180079583  xorps   xmm0, xmm0
0x180079586  movdqu  xmmword ptr [rsp+68h+var_48], xmm0
0x18007958c  mov     [rsp+68h+var_38], rbx
0x180079591  mov     eax, r14d
0x180079594  jmp     loc_1800796F7
0x180079599  mov     rcx, [rsi+48h]
0x18007959d  xorps   xmm0, xmm0
0x1800795a0  xor     eax, eax
0x1800795a2  movups  [rsp+68h+var_30], xmm0
0x1800795a7  mov     [rsp+68h+var_20], rax
0x1800795ac  mov     word ptr [rsp+68h+var_30], r15w
0x1800795b2  mov     dword ptr [rsp+68h+var_30+8], 0Eh
0x1800795ba  mov     rax, [rcx]
0x1800795bd  lea     r8, [rsp+68h+var_30]
0x1800795c2  lea     rdx, aExpeditedupdat_15; "ExpeditedUpdateStatus"
0x1800795c9  mov     rax, [rax+20h]
0x1800795cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800795d2  mov     esi, eax
0x1800795d4  test    eax, eax
0x1800795d6  jns     short loc_180079631
0x1800795d8  mov     rcx, [rsp+68h]; this
0x1800795dd  mov     r9d, eax; char *
0x1800795e0  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800795e7  mov     edx, 196h; void *
0x1800795ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800795f1  nop
  ... truncated ...
```
