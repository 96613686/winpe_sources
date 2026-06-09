# EnterpriseInfo::GetIsCloudDomainJoinInfo(void)

- ea: `0x180028088`
- end: `0x18002831c`
- name: `?GetIsCloudDomainJoinInfo@EnterpriseInfo@@AEBAAEAU_CLOUD_DOMAIN_JOIN_INFO@@XZ`
- size: `660`
- prototype: `struct _CLOUD_DOMAIN_JOIN_INFO *__fastcall(EnterpriseInfo *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025fc0`
- `0x180026110`
- `0x180028060`

## callees

- `0x180009448`
- `0x180009f08`
- `0x180014f2c`
- `0x1800157b8`
- `0x18001daf0`
- `0x18001dcc8`
- `0x180028088`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002815c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002815c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028184`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028198`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028184`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028198`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028302`

## string_xrefs

- `0x180028155`: `netapi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct _CLOUD_DOMAIN_JOIN_INFO *__fastcall EnterpriseInfo::GetIsCloudDomainJoinInfo(EnterpriseInfo *this)
{
  __int64 v1; // rdi
  int v2; // eax
  void (__fastcall *v3)(EnterpriseInfo *); // r14
  HMODULE Library; // rax
  FARPROC ProcAddress; // rbx
  FARPROC v6; // rax
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rbx
  char *v10; // rcx
  const wchar_t *v11; // r9
  char *v12; // rcx
  EnterpriseInfo *v13; // rcx
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
  EnterpriseInfo *v25; // [rsp+80h] [rbp+48h] BYREF

  v25 = this;
  v1 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + *(unsigned int *)&tls_index);
  v2 = *(_DWORD *)(v1 + 376);
  if ( (v2 & 1) == 0 )
  {
    *(_DWORD *)(v1 + 376) = v2 | 1;
    v25 = (EnterpriseInfo *)(v1 + 384);
    *(_OWORD *)(v1 + 384) = 0;
    *(_QWORD *)(v1 + 400) = 0;
    *(_QWORD *)(v1 + 408) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)(v1 + 384), L"#", 1u);
    *(_DWORD *)(v1 + 416) = -1;
    *(_OWORD *)(v1 + 424) = 0;
    *(_QWORD *)(v1 + 440) = 0;
    *(_QWORD *)(v1 + 448) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)(v1 + 424), L"#", 1u);
    _tlregdtor(EnterpriseInfo::GetIsCloudDomainJoinInfo_::_2_::_dynamic_atexit_destructor_for__result__);
  }
  if ( !*(_BYTE *)(v1 + 309) )
  {
    *(_BYTE *)(v1 + 309) = 1;
    v25 = 0;
    v3 = 0;
    Library = LoadLibraryExW(L"netapi32.dll", 0, 0x800u);
    v23 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    hModule = Library;
    if ( !Library )
      goto LABEL_37;
    ProcAddress = GetProcAddress(Library, "NetGetAadJoinInformation");
    v6 = GetProcAddress(hModule, "NetFreeAadJoinInformation");
    v3 = (void (__fastcall *)(EnterpriseInfo *))v6;
    if ( !ProcAddress || !v6 || ((int (__fastcall *)(_QWORD, EnterpriseInfo **))ProcAddress)(0, &v25) < 0 )
      goto LABEL_37;
    if ( v25 && (v8 = *((_QWORD *)v25 + 1)) != 0 && *(_QWORD *)(v8 + 24) && *((_QWORD *)v25 + 4) && *(_DWORD *)v25 != 2 )
    {
      v9 = v1 + 384;
      if ( *(_QWORD *)(v1 + 408) )
      {
        if ( *(_QWORD *)(v1 + 408) <= 7u )
          v10 = (char *)(v1 + 384);
        else
          v10 = *(char **)v9;
        *(_QWORD *)(v1 + 400) = 1;
        *(_DWORD *)v10 = 49;
        goto LABEL_26;
      }
      v11 = L"1";
    }
    else
    {
      v9 = v1 + 384;
      if ( *(_QWORD *)(v1 + 408) )
      {
        if ( *(_QWORD *)(v1 + 408) <= 7u )
          v12 = (char *)(v1 + 384);
        else
          v12 = *(char **)v9;
        *(_QWORD *)(v1 + 400) = 1;
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
        JUMPOUT(0x18002831BLL);
      }
      return (struct _CLOUD_DOMAIN_JOIN_INFO *)(v1 + 384);
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
  return (struct _CLOUD_DOMAIN_JOIN_INFO *)(v1 + 384);
}

```

## disassembly

```asm
0x180028088  mov     [rsp-40h+arg_0], rcx
0x18002808d  push    rbp
0x18002808e  push    rbx
0x18002808f  push    rsi
0x180028090  push    rdi
0x180028091  push    r12
0x180028093  push    r13
0x180028095  push    r14
0x180028097  push    r15
0x180028099  mov     rbp, rsp
0x18002809c  sub     rsp, 38h
0x1800280a0  mov     ecx, cs:_tls_index
0x1800280a6  mov     rax, gs:58h
0x1800280af  mov     rdi, [rax+rcx*8]
0x1800280b3  mov     ecx, 178h
0x1800280b8  mov     eax, [rcx+rdi]
0x1800280bb  mov     r12d, 180h
0x1800280c1  xor     r15d, r15d
0x1800280c4  lea     esi, [r15+1]
0x1800280c8  test    sil, al
0x1800280cb  jnz     short loc_180028133
0x1800280cd  or      eax, esi
0x1800280cf  mov     [rcx+rdi], eax
0x1800280d2  mov     ebx, r12d
0x1800280d5  add     rbx, rdi
0x1800280d8  mov     [rbp+arg_0], rbx
0x1800280dc  xorps   xmm0, xmm0
0x1800280df  movups  xmmword ptr [rbx], xmm0
0x1800280e2  mov     [rbx+10h], r15
0x1800280e6  mov     [rbx+18h], r15
0x1800280ea  mov     r8d, esi
0x1800280ed  lea     rdx, asc_1801B4764; "#"
0x1800280f4  mov     rcx, rbx
0x1800280f7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800280fc  nop
0x1800280fd  mov     dword ptr [rbx+20h], 0FFFFFFFFh
0x180028104  lea     rcx, [rbx+28h]
0x180028108  xorps   xmm0, xmm0
0x18002810b  movups  xmmword ptr [rcx], xmm0
0x18002810e  mov     [rcx+10h], r15
0x180028112  mov     [rcx+18h], r15
0x180028116  mov     r8d, esi
0x180028119  lea     rdx, asc_1801B4764; "#"
0x180028120  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180028125  nop
0x180028126  lea     rcx, _EnterpriseInfo__GetIsCloudDomainJoinInfo____2____dynamic_atexit_destructor_for__result__
0x18002812d  call    __tlregdtor
0x180028132  nop
0x180028133  mov     eax, 135h
0x180028138  cmp     [rax+rdi], r15b
0x18002813c  jnz     loc_1800282EB
0x180028142  mov     [rax+rdi], sil
0x180028146  mov     [rbp+arg_0], r15
0x18002814a  mov     r14, r15
0x18002814d  xor     edx, edx; hFile
0x18002814f  mov     r8d, 800h; dwFlags
0x180028155  lea     rcx, aNetapi32Dll; "netapi32.dll"
0x18002815c  call    cs:__imp_LoadLibraryExW
0x180028162  lea     r13, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180028169  mov     [rbp+var_18], r13
0x18002816d  mov     [rbp+hModule], rax
0x180028171  test    rax, rax
0x180028174  jz      loc_1800282C2
0x18002817a  lea     rdx, aNetgetaadjoini; "NetGetAadJoinInformation"
0x180028181  mov     rcx, rax; hModule
0x180028184  call    cs:__imp_GetProcAddress
0x18002818a  mov     rbx, rax
0x18002818d  lea     rdx, aNetfreeaadjoin; "NetFreeAadJoinInformation"
0x180028194  mov     rcx, [rbp+hModule]; hModule
0x180028198  call    cs:__imp_GetProcAddress
0x18002819e  mov     r14, rax
0x1800281a1  test    rbx, rbx
0x1800281a4  jz      loc_1800282C2
0x1800281aa  test    rax, rax
0x1800281ad  jz      loc_1800282C2
0x1800281b3  lea     rdx, [rbp+arg_0]
0x1800281b7  xor     ecx, ecx
0x1800281b9  mov     rax, rbx
0x1800281bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281c1  test    eax, eax
0x1800281c3  js      loc_1800282C2
0x1800281c9  mov     rax, [rbp+arg_0]
0x1800281cd  test    rax, rax
0x1800281d0  jz      short loc_18002821C
0x1800281d2  mov     rcx, [rax+8]
0x1800281d6  test    rcx, rcx
0x1800281d9  jz      short loc_18002821C
0x1800281db  cmp     [rcx+18h], r15
0x1800281df  jz      short loc_18002821C
0x1800281e1  cmp     [rax+20h], r15
0x1800281e5  jz      short loc_18002821C
0x1800281e7  cmp     dword ptr [rax], 2
0x1800281ea  jz      short loc_18002821C
0x1800281ec  mov     ebx, r12d
0x1800281ef  add     rbx, rdi
0x1800281f2  cmp     [rbx+18h], rsi
0x1800281f6  jb      short loc_180028213
0x1800281f8  cmp     qword ptr [rbx+18h], 7
0x1800281fd  jbe     short loc_180028204
0x1800281ff  mov     rcx, [rbx]
0x180028202  jmp     short loc_180028207
0x180028204  mov     rcx, rbx
0x180028207  mov     [rbx+10h], rsi
0x18002820b  mov     dword ptr [rcx], 31h ; '1'
0x180028211  jmp     short loc_18002825D
0x180028213  lea     r9, a1_0; "1"
0x18002821a  jmp     short loc_180028252
0x18002821c  mov     ebx, r12d
0x18002821f  add     rbx, rdi
0x180028222  cmp     [rbx+18h], rsi
0x180028226  jb      short loc_18002824B
0x180028228  cmp     qword ptr [rbx+18h], 7
0x18002822d  jbe     short loc_180028234
0x18002822f  mov     rcx, [rbx]
0x180028232  jmp     short loc_180028237
0x180028234  mov     rcx, rbx
0x180028237  mov     [rbx+10h], rsi
0x18002823b  mov     eax, dword ptr cs:a0_0; "0"
0x180028241  mov     [rcx], ax
0x180028244  mov     [rcx+2], r15w
0x180028249  jmp     short loc_18002825D
0x18002824b  lea     r9, a0_0; "0"
0x180028252  mov     rdx, rsi
0x180028255  mov     rcx, rbx
0x180028258  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18002825d  mov     rcx, [rbp+arg_0]
0x180028261  test    rcx, rcx
0x180028264  jz      short loc_1800282D4
0x180028266  mov     eax, [rcx]
0x180028268  cmp     eax, 2
0x18002826b  jz      short loc_1800282C6
0x18002826d  mov     [rbx+20h], eax
0x180028270  mov     r9, [rcx+10h]
0x180028274  test    r9, r9
0x180028277  jz      short loc_1800282C6
0x180028279  lea     rcx, [rbx+28h]
0x18002827d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180028281  inc     rdx
0x180028284  cmp     [r9+rdx*2], r15w
0x180028289  jnz     short loc_180028281
0x18002828b  cmp     rdx, [rcx+18h]
0x18002828f  ja      short loc_1800282BD
0x180028291  cmp     qword ptr [rcx+18h], 7
0x180028296  jbe     short loc_18002829D
0x180028298  mov     rsi, [rcx]
0x18002829b  jmp     short loc_1800282A0
0x18002829d  mov     rsi, rcx
0x1800282a0  mov     [rcx+10h], rdx
0x1800282a4  lea     rbx, [rdx+rdx]
0x1800282a8  mov     r8, rbx; Size
0x1800282ab  mov     rdx, r9; Src
0x1800282ae  mov     rcx, rsi; void *
0x1800282b1  call    memmove_0
0x1800282b6  mov     [rbx+rsi], r15w
0x1800282bb  jmp     short loc_1800282C2
0x1800282bd  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800282c2  mov     rcx, [rbp+arg_0]
0x1800282c6  test    rcx, rcx
0x1800282c9  jz      short loc_1800282D4
0x1800282cb  mov     rax, r14
0x1800282ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282d3  nop
0x1800282d4  mov     [rbp+var_18], r13
0x1800282d8  cmp     [rbp+hModule], r15
0x1800282dc  jz      short loc_1800282EB
0x1800282de  lea     rcx, [rbp+var_18]
0x1800282e2  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800282e7  test    al, al
0x1800282e9  jz      short loc_180028302
0x1800282eb  mov     eax, r12d
0x1800282ee  add     rax, rdi
0x1800282f1  add     rsp, 38h
0x1800282f5  pop     r15
0x1800282f7  pop     r14
0x1800282f9  pop     r13
0x1800282fb  pop     r12
0x1800282fd  pop     rdi
0x1800282fe  pop     rsi
0x1800282ff  pop     rbx
0x180028300  pop     rbp
0x180028301  retn
0x180028302  call    cs:__imp_GetLastError
0x180028308  test    eax, eax
0x18002830a  jle     short loc_180028314
0x18002830c  movzx   eax, ax
0x18002830f  or      eax, 80070000h
0x180028314  mov     ecx, eax; this
0x180028316  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
