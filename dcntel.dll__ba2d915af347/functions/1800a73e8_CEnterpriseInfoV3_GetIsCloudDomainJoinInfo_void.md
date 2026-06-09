# CEnterpriseInfoV3::GetIsCloudDomainJoinInfo(void)

- ea: `0x1800a73e8`
- end: `0x1800a767c`
- name: `?GetIsCloudDomainJoinInfo@CEnterpriseInfoV3@@AEBAAEAU_CLOUD_DOMAIN_JOIN_INFO_V3@@XZ`
- size: `660`
- prototype: `struct _CLOUD_DOMAIN_JOIN_INFO_V3 *__fastcall(CEnterpriseInfoV3 *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a7370`
- `0x1800a73a0`
- `0x1800a73c0`

## callees

- `0x180009448`
- `0x180009f08`
- `0x180014f2c`
- `0x1800157b8`
- `0x18001daf0`
- `0x18001dcc8`
- `0x1800a73e8`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a74bc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a74bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a74e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a74f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a74e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a74f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7662`

## string_xrefs

- `0x1800a74b5`: `netapi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct _CLOUD_DOMAIN_JOIN_INFO_V3 *__fastcall CEnterpriseInfoV3::GetIsCloudDomainJoinInfo(CEnterpriseInfoV3 *this)
{
  __int64 v1; // rdi
  int v2; // eax
  void (__fastcall *v3)(CEnterpriseInfoV3 *); // r14
  HMODULE Library; // rax
  FARPROC ProcAddress; // rbx
  FARPROC v6; // rax
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rbx
  char *v10; // rcx
  const wchar_t *v11; // r9
  char *v12; // rcx
  CEnterpriseInfoV3 *v13; // rcx
  _WORD *v14; // r9
  char **v15; // rcx
  unsigned __int64 v16; // rdx
  char *v17; // rsi
  __int64 v18; // rbx
  signed int LastError; // eax
  int v21; // edx
  unsigned int v22; // r8d
  const int *v23; // [rsp+20h] [rbp-18h] BYREF
  HMODULE hModule; // [rsp+28h] [rbp-10h]
  CEnterpriseInfoV3 *v25; // [rsp+80h] [rbp+48h] BYREF

  v25 = this;
  v1 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + *(unsigned int *)&tls_index);
  v2 = *(_DWORD *)(v1 + 792);
  if ( (v2 & 1) == 0 )
  {
    *(_DWORD *)(v1 + 792) = v2 | 1;
    v25 = (CEnterpriseInfoV3 *)(v1 + 800);
    *(_OWORD *)(v1 + 800) = 0;
    *(_QWORD *)(v1 + 816) = 0;
    *(_QWORD *)(v1 + 824) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)(v1 + 800), L"#", 1u);
    *(_DWORD *)(v1 + 832) = -1;
    *(_OWORD *)(v1 + 840) = 0;
    *(_QWORD *)(v1 + 856) = 0;
    *(_QWORD *)(v1 + 864) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)(v1 + 840), L"#", 1u);
    _tlregdtor(CEnterpriseInfoV3::GetIsCloudDomainJoinInfo_::_2_::_dynamic_atexit_destructor_for__result__);
  }
  if ( !*(_BYTE *)(v1 + 314) )
  {
    *(_BYTE *)(v1 + 314) = 1;
    v25 = 0;
    v3 = 0;
    Library = LoadLibraryExW(L"netapi32.dll", 0, 0x800u);
    v23 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    hModule = Library;
    if ( !Library )
      goto LABEL_37;
    ProcAddress = GetProcAddress(Library, "NetGetAadJoinInformation");
    v6 = GetProcAddress(hModule, "NetFreeAadJoinInformation");
    v3 = (void (__fastcall *)(CEnterpriseInfoV3 *))v6;
    if ( !ProcAddress || !v6 || ((int (__fastcall *)(_QWORD, CEnterpriseInfoV3 **))ProcAddress)(0, &v25) < 0 )
      goto LABEL_37;
    if ( v25 && (v8 = *((_QWORD *)v25 + 1)) != 0 && *(_QWORD *)(v8 + 24) && *((_QWORD *)v25 + 4) && *(_DWORD *)v25 != 2 )
    {
      v9 = v1 + 800;
      if ( *(_QWORD *)(v1 + 824) )
      {
        if ( *(_QWORD *)(v1 + 824) <= 7u )
          v10 = (char *)(v1 + 800);
        else
          v10 = *(char **)v9;
        *(_QWORD *)(v1 + 816) = 1;
        *(_DWORD *)v10 = 49;
        goto LABEL_26;
      }
      v11 = L"1";
    }
    else
    {
      v9 = v1 + 800;
      if ( *(_QWORD *)(v1 + 824) )
      {
        if ( *(_QWORD *)(v1 + 824) <= 7u )
          v12 = (char *)(v1 + 800);
        else
          v12 = *(char **)v9;
        *(_QWORD *)(v1 + 816) = 1;
        *(_WORD *)v12 = a0_0[0];
        *((_WORD *)v12 + 1) = 0;
        goto LABEL_26;
      }
      v11 = L"0";
    }
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char **)v9,
      1u,
      v7,
      v11);
LABEL_26:
    v13 = v25;
    if ( !v25 )
    {
LABEL_40:
      v23 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( hModule && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v23) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v21, v22);
        JUMPOUT(0x1800A767BLL);
      }
      return (struct _CLOUD_DOMAIN_JOIN_INFO_V3 *)(v1 + 800);
    }
    if ( *(_DWORD *)v25 == 2 || (*(_DWORD *)(v9 + 32) = *(_DWORD *)v25, (v14 = (_WORD *)*((_QWORD *)v13 + 2)) == 0) )
    {
LABEL_38:
      if ( v13 )
        v3(v13);
      goto LABEL_40;
    }
    v15 = (char **)(v9 + 40);
    v16 = -1;
    do
      ++v16;
    while ( v14[v16] );
    if ( v16 > *(_QWORD *)(v9 + 64) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v15, v16, v7, v14);
    }
    else
    {
      if ( *(_QWORD *)(v9 + 64) <= 7u )
        v17 = (char *)(v9 + 40);
      else
        v17 = *v15;
      *(_QWORD *)(v9 + 56) = v16;
      v18 = 2 * v16;
      memmove_0(v17, v14, 2 * v16);
      *(_WORD *)&v17[v18] = 0;
    }
LABEL_37:
    v13 = v25;
    goto LABEL_38;
  }
  return (struct _CLOUD_DOMAIN_JOIN_INFO_V3 *)(v1 + 800);
}

```

## disassembly

```asm
0x1800a73e8  mov     [rsp-40h+arg_0], rcx
0x1800a73ed  push    rbp
0x1800a73ee  push    rbx
0x1800a73ef  push    rsi
0x1800a73f0  push    rdi
0x1800a73f1  push    r12
0x1800a73f3  push    r13
0x1800a73f5  push    r14
0x1800a73f7  push    r15
0x1800a73f9  mov     rbp, rsp
0x1800a73fc  sub     rsp, 38h
0x1800a7400  mov     ecx, cs:_tls_index
0x1800a7406  mov     rax, gs:58h
0x1800a740f  mov     rdi, [rax+rcx*8]
0x1800a7413  mov     ecx, 318h
0x1800a7418  mov     eax, [rcx+rdi]
0x1800a741b  mov     r12d, 320h
0x1800a7421  xor     r15d, r15d
0x1800a7424  lea     esi, [r15+1]
0x1800a7428  test    sil, al
0x1800a742b  jnz     short loc_1800A7493
0x1800a742d  or      eax, esi
0x1800a742f  mov     [rcx+rdi], eax
0x1800a7432  mov     ebx, r12d
0x1800a7435  add     rbx, rdi
0x1800a7438  mov     [rbp+arg_0], rbx
0x1800a743c  xorps   xmm0, xmm0
0x1800a743f  movups  xmmword ptr [rbx], xmm0
0x1800a7442  mov     [rbx+10h], r15
0x1800a7446  mov     [rbx+18h], r15
0x1800a744a  mov     r8d, esi
0x1800a744d  lea     rdx, asc_1801B4764; "#"
0x1800a7454  mov     rcx, rbx
0x1800a7457  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800a745c  nop
0x1800a745d  mov     dword ptr [rbx+20h], 0FFFFFFFFh
0x1800a7464  lea     rcx, [rbx+28h]
0x1800a7468  xorps   xmm0, xmm0
0x1800a746b  movups  xmmword ptr [rcx], xmm0
0x1800a746e  mov     [rcx+10h], r15
0x1800a7472  mov     [rcx+18h], r15
0x1800a7476  mov     r8d, esi
0x1800a7479  lea     rdx, asc_1801B4764; "#"
0x1800a7480  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800a7485  nop
0x1800a7486  lea     rcx, _CEnterpriseInfoV3__GetIsCloudDomainJoinInfo____2____dynamic_atexit_destructor_for__result__
0x1800a748d  call    __tlregdtor
0x1800a7492  nop
0x1800a7493  mov     eax, 13Ah
0x1800a7498  cmp     [rax+rdi], r15b
0x1800a749c  jnz     loc_1800A764B
0x1800a74a2  mov     [rax+rdi], sil
0x1800a74a6  mov     [rbp+arg_0], r15
0x1800a74aa  mov     r14, r15
0x1800a74ad  xor     edx, edx; hFile
0x1800a74af  mov     r8d, 800h; dwFlags
0x1800a74b5  lea     rcx, aNetapi32Dll; "netapi32.dll"
0x1800a74bc  call    cs:__imp_LoadLibraryExW
0x1800a74c2  lea     r13, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800a74c9  mov     [rbp+var_18], r13
0x1800a74cd  mov     [rbp+hModule], rax
0x1800a74d1  test    rax, rax
0x1800a74d4  jz      loc_1800A7622
0x1800a74da  lea     rdx, aNetgetaadjoini; "NetGetAadJoinInformation"
0x1800a74e1  mov     rcx, rax; hModule
0x1800a74e4  call    cs:__imp_GetProcAddress
0x1800a74ea  mov     rbx, rax
0x1800a74ed  lea     rdx, aNetfreeaadjoin; "NetFreeAadJoinInformation"
0x1800a74f4  mov     rcx, [rbp+hModule]; hModule
0x1800a74f8  call    cs:__imp_GetProcAddress
0x1800a74fe  mov     r14, rax
0x1800a7501  test    rbx, rbx
0x1800a7504  jz      loc_1800A7622
0x1800a750a  test    rax, rax
0x1800a750d  jz      loc_1800A7622
0x1800a7513  lea     rdx, [rbp+arg_0]
0x1800a7517  xor     ecx, ecx
0x1800a7519  mov     rax, rbx
0x1800a751c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7521  test    eax, eax
0x1800a7523  js      loc_1800A7622
0x1800a7529  mov     rax, [rbp+arg_0]
0x1800a752d  test    rax, rax
0x1800a7530  jz      short loc_1800A757C
0x1800a7532  mov     rcx, [rax+8]
0x1800a7536  test    rcx, rcx
0x1800a7539  jz      short loc_1800A757C
0x1800a753b  cmp     [rcx+18h], r15
0x1800a753f  jz      short loc_1800A757C
0x1800a7541  cmp     [rax+20h], r15
0x1800a7545  jz      short loc_1800A757C
0x1800a7547  cmp     dword ptr [rax], 2
0x1800a754a  jz      short loc_1800A757C
0x1800a754c  mov     ebx, r12d
0x1800a754f  add     rbx, rdi
0x1800a7552  cmp     [rbx+18h], rsi
0x1800a7556  jb      short loc_1800A7573
0x1800a7558  cmp     qword ptr [rbx+18h], 7
0x1800a755d  jbe     short loc_1800A7564
0x1800a755f  mov     rcx, [rbx]
0x1800a7562  jmp     short loc_1800A7567
0x1800a7564  mov     rcx, rbx
0x1800a7567  mov     [rbx+10h], rsi
0x1800a756b  mov     dword ptr [rcx], 31h ; '1'
0x1800a7571  jmp     short loc_1800A75BD
0x1800a7573  lea     r9, a1_0; "1"
0x1800a757a  jmp     short loc_1800A75B2
0x1800a757c  mov     ebx, r12d
0x1800a757f  add     rbx, rdi
0x1800a7582  cmp     [rbx+18h], rsi
0x1800a7586  jb      short loc_1800A75AB
0x1800a7588  cmp     qword ptr [rbx+18h], 7
0x1800a758d  jbe     short loc_1800A7594
0x1800a758f  mov     rcx, [rbx]
0x1800a7592  jmp     short loc_1800A7597
0x1800a7594  mov     rcx, rbx
0x1800a7597  mov     [rbx+10h], rsi
0x1800a759b  mov     eax, dword ptr cs:a0_0; "0"
0x1800a75a1  mov     [rcx], ax
0x1800a75a4  mov     [rcx+2], r15w
0x1800a75a9  jmp     short loc_1800A75BD
0x1800a75ab  lea     r9, a0_0; "0"
0x1800a75b2  mov     rdx, rsi
0x1800a75b5  mov     rcx, rbx
0x1800a75b8  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800a75bd  mov     rcx, [rbp+arg_0]
0x1800a75c1  test    rcx, rcx
0x1800a75c4  jz      short loc_1800A7634
0x1800a75c6  mov     eax, [rcx]
0x1800a75c8  cmp     eax, 2
0x1800a75cb  jz      short loc_1800A7626
0x1800a75cd  mov     [rbx+20h], eax
0x1800a75d0  mov     r9, [rcx+10h]
0x1800a75d4  test    r9, r9
0x1800a75d7  jz      short loc_1800A7626
0x1800a75d9  lea     rcx, [rbx+28h]
0x1800a75dd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800a75e1  inc     rdx
0x1800a75e4  cmp     [r9+rdx*2], r15w
0x1800a75e9  jnz     short loc_1800A75E1
0x1800a75eb  cmp     rdx, [rcx+18h]
0x1800a75ef  ja      short loc_1800A761D
0x1800a75f1  cmp     qword ptr [rcx+18h], 7
0x1800a75f6  jbe     short loc_1800A75FD
0x1800a75f8  mov     rsi, [rcx]
0x1800a75fb  jmp     short loc_1800A7600
0x1800a75fd  mov     rsi, rcx
0x1800a7600  mov     [rcx+10h], rdx
0x1800a7604  lea     rbx, [rdx+rdx]
0x1800a7608  mov     r8, rbx; Size
0x1800a760b  mov     rdx, r9; Src
0x1800a760e  mov     rcx, rsi; void *
0x1800a7611  call    memmove_0
0x1800a7616  mov     [rbx+rsi], r15w
0x1800a761b  jmp     short loc_1800A7622
0x1800a761d  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800a7622  mov     rcx, [rbp+arg_0]
0x1800a7626  test    rcx, rcx
0x1800a7629  jz      short loc_1800A7634
0x1800a762b  mov     rax, r14
0x1800a762e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7633  nop
0x1800a7634  mov     [rbp+var_18], r13
0x1800a7638  cmp     [rbp+hModule], r15
0x1800a763c  jz      short loc_1800A764B
0x1800a763e  lea     rcx, [rbp+var_18]
0x1800a7642  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800a7647  test    al, al
0x1800a7649  jz      short loc_1800A7662
0x1800a764b  mov     eax, r12d
0x1800a764e  add     rax, rdi
0x1800a7651  add     rsp, 38h
0x1800a7655  pop     r15
0x1800a7657  pop     r14
0x1800a7659  pop     r13
0x1800a765b  pop     r12
0x1800a765d  pop     rdi
0x1800a765e  pop     rsi
0x1800a765f  pop     rbx
0x1800a7660  pop     rbp
0x1800a7661  retn
0x1800a7662  call    cs:__imp_GetLastError
0x1800a7668  test    eax, eax
0x1800a766a  jle     short loc_1800A7674
0x1800a766c  movzx   eax, ax
0x1800a766f  or      eax, 80070000h
0x1800a7674  mov     ecx, eax; this
0x1800a7676  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
