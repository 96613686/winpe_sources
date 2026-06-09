# EnterpriseInfo::IsEnterpriseDataProtectionEnabled(void)

- ea: `0x18002a110`
- end: `0x18002a347`
- name: `?IsEnterpriseDataProtectionEnabled@EnterpriseInfo@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `567`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008dc0`
- `0x180009f08`
- `0x180014f2c`
- `0x1800157b8`
- `0x180016748`
- `0x180016db0`
- `0x180019324`
- `0x18001daf0`
- `0x18001dcc8`
- `0x1800220b4`
- `0x1800273bc`
- `0x18002a110`
- `0x18002b3e4`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002a19c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002a19c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a1df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a1df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a327`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a327`

## string_xrefs

- `0x18002a195`: `edputil.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EnterpriseInfo::IsEnterpriseDataProtectionEnabled(__int64 a1, __int64 a2)
{
  __int64 DplState; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int (*ProcAddress)(void); // rax
  char *v7; // rbx
  __int64 v8; // rcx
  char *v9; // r9
  __int64 v10; // rax
  signed int LastError; // eax
  int v13; // edx
  unsigned int v14; // r8d
  const int *v15; // [rsp+48h] [rbp-51h] BYREF
  HMODULE hModule; // [rsp+50h] [rbp-49h]
  __int64 v17; // [rsp+58h] [rbp-41h]
  __int128 v18; // [rsp+60h] [rbp-39h] BYREF
  __int64 v19; // [rsp+70h] [rbp-29h]
  __int64 v20; // [rsp+78h] [rbp-21h]
  char *Src[4]; // [rsp+80h] [rbp-19h] BYREF
  _OWORD v22[2]; // [rsp+A0h] [rbp+7h] BYREF

  v17 = a2;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)a2, L"EDP_NOT_ENABLED", 0xFu);
  v18 = 0;
  v19 = 0;
  v20 = 7;
  LOWORD(v18) = 0;
  v15 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = LoadLibraryExW(L"edputil.DLL", 0, 0x800u);
  DplState = EnterpriseInfo::GetDplState((__int64)Src);
  std::wstring::operator=(&v18, DplState);
  std::wstring::~wstring(Src);
  if ( hModule )
  {
    ProcAddress = (unsigned int (*)(void))GetProcAddress(hModule, "EdpGetIsManaged");
    if ( ProcAddress )
    {
      if ( ProcAddress() )
      {
        if ( *(_QWORD *)(a2 + 24) < 0xBu )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            (char **)a2,
            0xBu,
            v5,
            L"EDP_ENABLED");
        }
        else
        {
          v7 = *(char **)a2;
          *(_QWORD *)(a2 + 16) = 11;
          memmove_0(v7, L"EDP_ENABLED", 0x16u);
          *((_WORD *)v7 + 11) = 0;
        }
      }
    }
  }
  if ( v19 )
  {
    v8 = *(_QWORD *)(a2 + 16);
    if ( v8 == 0x7FFFFFFFFFFFFFFELL )
      goto LABEL_20;
    if ( *(_QWORD *)(a2 + 24) <= 7u )
      v9 = (char *)a2;
    else
      v9 = *(char **)a2;
    std::wstring::wstring(Src, v4, v5, v9, v8, L"|", 1);
    v10 = std::wstring::append(Src);
    v22[0] = *(_OWORD *)v10;
    v22[1] = *(_OWORD *)(v10 + 16);
    *(_QWORD *)(v10 + 16) = 0;
    *(_QWORD *)(v10 + 24) = 7;
    *(_WORD *)v10 = 0;
    std::wstring::operator=(a2, v22);
    std::wstring::~wstring((char **)v22);
    std::wstring::~wstring(Src);
  }
  v15 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule )
  {
    if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v15) )
    {
      hModule = 0;
      goto LABEL_16;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v13, v14);
LABEL_20:
    std::_Xlen_string();
  }
LABEL_16:
  std::wstring::~wstring((char **)&v18);
  return a2;
}

```

## disassembly

```asm
0x18002a110  push    rbp
0x18002a112  push    rbx
0x18002a113  push    rdi
0x18002a114  push    r12
0x18002a116  lea     rbp, [rsp-3Fh]
0x18002a11b  sub     rsp, 0D8h
0x18002a122  mov     rax, cs:__security_cookie
0x18002a129  xor     rax, rsp
0x18002a12c  mov     [rbp+57h+var_30], rax
0x18002a130  mov     rdi, rdx
0x18002a133  mov     [rbp+57h+var_98], rdx
0x18002a137  mov     [rbp+57h+var_B0], 0
0x18002a13e  xorps   xmm0, xmm0
0x18002a141  movups  xmmword ptr [rdx], xmm0
0x18002a144  mov     qword ptr [rdx+10h], 0
0x18002a14c  mov     qword ptr [rdx+18h], 0
0x18002a154  mov     r8d, 0Fh
0x18002a15a  lea     rdx, aEdpNotEnabled; "EDP_NOT_ENABLED"
0x18002a161  mov     rcx, rdi
0x18002a164  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002a169  mov     [rbp+57h+var_B0], 1
0x18002a170  xorps   xmm0, xmm0
0x18002a173  movups  [rbp+57h+var_90], xmm0
0x18002a177  mov     [rbp+57h+var_80], 0
0x18002a17f  mov     [rbp+57h+var_78], 7
0x18002a187  xor     eax, eax
0x18002a189  mov     word ptr [rbp+57h+var_90], ax
0x18002a18d  xor     edx, edx; hFile
0x18002a18f  mov     r8d, 800h; dwFlags
0x18002a195  lea     rcx, aEdputilDll; "edputil.DLL"
0x18002a19c  call    cs:__imp_LoadLibraryExW
0x18002a1a2  lea     r12, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18002a1a9  mov     [rbp+57h+var_A8], r12
0x18002a1ad  mov     [rbp+57h+hModule], rax
0x18002a1b1  lea     rcx, [rbp+57h+Src]
0x18002a1b5  call    ?GetDplState@EnterpriseInfo@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; EnterpriseInfo::GetDplState(void)
0x18002a1ba  mov     rdx, rax
0x18002a1bd  lea     rcx, [rbp+57h+var_90]
0x18002a1c1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002a1c6  lea     rcx, [rbp+57h+Src]
0x18002a1ca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a1cf  mov     rcx, [rbp+57h+hModule]; hModule
0x18002a1d3  test    rcx, rcx
0x18002a1d6  jz      short loc_18002A22F
0x18002a1d8  lea     rdx, aEdpgetismanage; "EdpGetIsManaged"
0x18002a1df  call    cs:__imp_GetProcAddress
0x18002a1e5  test    rax, rax
0x18002a1e8  jz      short loc_18002A22F
0x18002a1ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1ef  test    eax, eax
0x18002a1f1  jz      short loc_18002A22F
0x18002a1f3  mov     edx, 0Bh
0x18002a1f8  cmp     [rdi+18h], rdx
0x18002a1fc  jb      short loc_18002A220
0x18002a1fe  mov     rbx, [rdi]
0x18002a201  mov     [rdi+10h], rdx
0x18002a205  lea     r8d, [rdx+0Bh]; Size
0x18002a209  lea     rdx, aEdpEnabled; "EDP_ENABLED"
0x18002a210  mov     rcx, rbx; void *
0x18002a213  call    memmove_0
0x18002a218  xor     eax, eax
0x18002a21a  mov     [rbx+16h], ax
0x18002a21e  jmp     short loc_18002A22F
0x18002a220  lea     r9, aEdpEnabled; "EDP_ENABLED"
0x18002a227  mov     rcx, rdi
0x18002a22a  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18002a22f  cmp     [rbp+57h+var_80], 0
0x18002a234  jz      loc_18002A2E2
0x18002a23a  mov     rcx, [rdi+10h]
0x18002a23e  mov     rax, 7FFFFFFFFFFFFFFEh
0x18002a248  sub     rax, rcx
0x18002a24b  cmp     rax, 1
0x18002a24f  jb      loc_18002A341
0x18002a255  cmp     qword ptr [rdi+18h], 7
0x18002a25a  jbe     short loc_18002A261
0x18002a25c  mov     r9, [rdi]
0x18002a25f  jmp     short loc_18002A264
0x18002a261  mov     r9, rdi
0x18002a264  mov     [rsp+0F0h+var_C0], 1
0x18002a26d  lea     rax, asc_1801B58D8; "|"
0x18002a274  mov     [rsp+0F0h+var_C8], rax
0x18002a279  mov     [rsp+0F0h+var_D0], rcx
0x18002a27e  lea     rcx, [rbp+57h+Src]
0x18002a282  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002a287  mov     [rbp+57h+var_B0], 3
0x18002a28e  lea     rdx, [rbp+57h+var_90]
0x18002a292  lea     rcx, [rbp+57h+Src]; Src
0x18002a296  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18002a29b  mov     rcx, rax
0x18002a29e  movups  xmm0, xmmword ptr [rax]
0x18002a2a1  movups  [rbp+57h+var_50], xmm0
0x18002a2a5  movups  xmm1, xmmword ptr [rax+10h]
0x18002a2a9  movups  [rbp+57h+var_40], xmm1
0x18002a2ad  mov     qword ptr [rax+10h], 0
0x18002a2b5  mov     qword ptr [rax+18h], 7
0x18002a2bd  xor     eax, eax
0x18002a2bf  mov     [rcx], ax
0x18002a2c2  lea     rdx, [rbp+57h+var_50]
0x18002a2c6  mov     rcx, rdi
0x18002a2c9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002a2ce  lea     rcx, [rbp+57h+var_50]
0x18002a2d2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a2d7  nop
0x18002a2d8  lea     rcx, [rbp+57h+Src]
0x18002a2dc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a2e1  nop
0x18002a2e2  mov     [rbp+57h+var_A8], r12
0x18002a2e6  cmp     [rbp+57h+hModule], 0
0x18002a2eb  jz      short loc_18002A302
0x18002a2ed  lea     rcx, [rbp+57h+var_A8]
0x18002a2f1  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18002a2f6  test    al, al
0x18002a2f8  jz      short loc_18002A327
0x18002a2fa  mov     [rbp+57h+hModule], 0
0x18002a302  lea     rcx, [rbp+57h+var_90]
0x18002a306  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a30b  mov     rax, rdi
0x18002a30e  mov     rcx, [rbp+57h+var_30]
0x18002a312  xor     rcx, rsp; StackCookie
0x18002a315  call    __security_check_cookie
0x18002a31a  add     rsp, 0D8h
0x18002a321  pop     r12
0x18002a323  pop     rdi
0x18002a324  pop     rbx
0x18002a325  pop     rbp
0x18002a326  retn
0x18002a327  call    cs:__imp_GetLastError
0x18002a32d  test    eax, eax
0x18002a32f  jle     short loc_18002A339
0x18002a331  movzx   eax, ax
0x18002a334  or      eax, 80070000h
0x18002a339  mov     ecx, eax; this
0x18002a33b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002a340  nop
0x18002a341  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
