# CUserNLSInfo::CollectAppLanguage(void)

- ea: `0x180089c60`
- end: `0x180089e8e`
- name: `?CollectAppLanguage@CUserNLSInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `558`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008dc0`
- `0x180009f08`
- `0x180014f2c`
- `0x1800157b8`
- `0x180016748`
- `0x18001daf0`
- `0x18001dcc8`
- `0x18001e3e4`
- `0x180089c60`
- `0x1800d42e0`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180089cf0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180089d11`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180089cf0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180089d11`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089d3c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089d50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089d3c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180089d50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089e5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089e74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089e5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089e74`

## string_xrefs

- `0x180089d0a`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x180089ce9`: `Bcp47Langs.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CUserNLSInfo::CollectAppLanguage(__int64 a1, __int64 a2)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rsi
  FARPROC v5; // rax
  __int64 (__fastcall *v6)(_QWORD, _QWORD); // rbx
  _WORD *v7; // rax
  __int64 v8; // r8
  unsigned __int64 v9; // rdx
  char *v10; // rsi
  __int64 v11; // rbx
  signed int LastError; // eax
  int v14; // edx
  unsigned int v15; // r8d
  signed int v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  const int *v19; // [rsp+28h] [rbp-31h] BYREF
  HMODULE v20; // [rsp+30h] [rbp-29h]
  const int *v21; // [rsp+38h] [rbp-21h] BYREF
  HMODULE hModule; // [rsp+40h] [rbp-19h]
  _QWORD v23[2]; // [rsp+48h] [rbp-11h] BYREF
  _OWORD v24[2]; // [rsp+58h] [rbp-1h] BYREF

  v23[1] = a2;
  v23[0] = 0;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)a2, L"#", 1u);
  memset(v24, 0, sizeof(v24));
  std::wstring::_Construct<1,unsigned short const *>((char **)v24, L";", 1u);
  v21 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = LoadLibraryExW(L"Bcp47Langs.dll", 0, 0x800u);
  Library = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u);
  v19 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v20 = Library;
  if ( hModule )
  {
    if ( Library )
    {
      ProcAddress = GetProcAddress(hModule, "GetUserLanguages");
      v5 = GetProcAddress(v20, "WindowsGetStringRawBuffer");
      v6 = (__int64 (__fastcall *)(_QWORD, _QWORD))v5;
      if ( ProcAddress )
      {
        if ( v5 && ((int (__fastcall *)(__int64, _QWORD *))ProcAddress)(59, v23) >= 0 )
        {
          v7 = (_WORD *)v6(v23[0], 0);
          v9 = -1;
          do
            ++v9;
          while ( v7[v9] );
          if ( v9 > *(_QWORD *)(a2 + 24) )
          {
            std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
              (char **)a2,
              v9,
              v8,
              v7);
          }
          else
          {
            v10 = *(_QWORD *)(a2 + 24) <= 7u ? (char *)a2 : *(char **)a2;
            *(_QWORD *)(a2 + 16) = v9;
            v11 = 2 * v9;
            memmove_0(v10, v7, 2 * v9);
            *(_WORD *)&v10[v11] = 0;
          }
          if ( *(_QWORD *)(a2 + 16) && Utils::find_ith(a2, v24) != -1 )
            std::wstring::resize((void *)a2);
        }
      }
    }
  }
  v19 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( v20 )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v19) )
      goto LABEL_27;
    v20 = 0;
  }
  v21 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule )
  {
    if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v21) )
    {
      hModule = 0;
      goto LABEL_23;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v14, v15);
LABEL_27:
    v16 = GetLastError();
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
    JUMPOUT(0x180089E8DLL);
  }
LABEL_23:
  std::wstring::~wstring((char **)v24);
  return a2;
}

```

## disassembly

```asm
0x180089c60  push    rbp
0x180089c62  push    rbx
0x180089c63  push    rsi
0x180089c64  push    rdi
0x180089c65  push    r14
0x180089c67  push    r15
0x180089c69  lea     rbp, [rsp-2Fh]
0x180089c6e  sub     rsp, 88h
0x180089c75  mov     rax, cs:__security_cookie
0x180089c7c  xor     rax, rsp
0x180089c7f  mov     [rbp+57h+var_38], rax
0x180089c83  mov     rdi, rdx
0x180089c86  mov     [rbp+57h+var_60], rdx
0x180089c8a  xor     r14d, r14d
0x180089c8d  mov     [rbp+57h+var_90], r14d
0x180089c91  mov     [rbp+57h+var_68], r14
0x180089c95  xorps   xmm0, xmm0
0x180089c98  movups  xmmword ptr [rdx], xmm0
0x180089c9b  mov     [rdx+10h], r14
0x180089c9f  mov     [rdx+18h], r14
0x180089ca3  lea     ebx, [r14+1]
0x180089ca7  mov     r8d, ebx
0x180089caa  lea     rdx, asc_1801B4764; "#"
0x180089cb1  mov     rcx, rdi
0x180089cb4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180089cb9  mov     [rbp+57h+var_90], ebx
0x180089cbc  xorps   xmm0, xmm0
0x180089cbf  movups  [rbp+57h+var_58], xmm0
0x180089cc3  xorps   xmm1, xmm1
0x180089cc6  movdqu  [rbp+57h+var_48], xmm1
0x180089ccb  mov     r8d, ebx
0x180089cce  lea     rdx, asc_1801B9DA0; ";"
0x180089cd5  lea     rcx, [rbp+57h+var_58]
0x180089cd9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180089cde  nop
0x180089cdf  mov     ebx, 800h
0x180089ce4  mov     r8d, ebx; dwFlags
0x180089ce7  xor     edx, edx; hFile
0x180089ce9  lea     rcx, aBcp47langsDll; "Bcp47Langs.dll"
0x180089cf0  call    cs:__imp_LoadLibraryExW
0x180089cf6  lea     r15, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180089cfd  mov     [rbp+57h+var_78], r15
0x180089d01  mov     [rbp+57h+hModule], rax
0x180089d05  mov     r8d, ebx; dwFlags
0x180089d08  xor     edx, edx; hFile
0x180089d0a  lea     rcx, aApiMsWinCoreWi_2; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x180089d11  call    cs:__imp_LoadLibraryExW
0x180089d17  mov     [rbp+57h+var_88], r15
0x180089d1b  mov     [rbp+57h+var_80], rax
0x180089d1f  mov     rcx, [rbp+57h+hModule]; hModule
0x180089d23  test    rcx, rcx
0x180089d26  jz      loc_180089DFC
0x180089d2c  test    rax, rax
0x180089d2f  jz      loc_180089DFC
0x180089d35  lea     rdx, aGetuserlanguag; "GetUserLanguages"
0x180089d3c  call    cs:__imp_GetProcAddress
0x180089d42  mov     rsi, rax
0x180089d45  lea     rdx, aWindowsgetstri; "WindowsGetStringRawBuffer"
0x180089d4c  mov     rcx, [rbp+57h+var_80]; hModule
0x180089d50  call    cs:__imp_GetProcAddress
0x180089d56  mov     rbx, rax
0x180089d59  test    rsi, rsi
0x180089d5c  jz      loc_180089DFC
0x180089d62  test    rax, rax
0x180089d65  jz      loc_180089DFC
0x180089d6b  lea     ecx, [r14+3Bh]
0x180089d6f  lea     rdx, [rbp+57h+var_68]
0x180089d73  mov     rax, rsi
0x180089d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089d7b  test    eax, eax
0x180089d7d  js      short loc_180089DFC
0x180089d7f  xor     edx, edx
0x180089d81  mov     rcx, [rbp+57h+var_68]
0x180089d85  mov     rax, rbx
0x180089d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089d8d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180089d91  inc     rdx
0x180089d94  cmp     [rax+rdx*2], r14w
0x180089d99  jnz     short loc_180089D91
0x180089d9b  cmp     rdx, [rdi+18h]
0x180089d9f  ja      short loc_180089DCD
0x180089da1  cmp     qword ptr [rdi+18h], 7
0x180089da6  jbe     short loc_180089DAD
0x180089da8  mov     rsi, [rdi]
0x180089dab  jmp     short loc_180089DB0
0x180089dad  mov     rsi, rdi
0x180089db0  mov     [rdi+10h], rdx
0x180089db4  lea     rbx, [rdx+rdx]
0x180089db8  mov     r8, rbx; Size
0x180089dbb  mov     rdx, rax; Src
0x180089dbe  mov     rcx, rsi; void *
0x180089dc1  call    memmove_0
0x180089dc6  mov     [rbx+rsi], r14w
0x180089dcb  jmp     short loc_180089DD8
0x180089dcd  mov     r9, rax
0x180089dd0  mov     rcx, rdi
0x180089dd3  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180089dd8  cmp     [rdi+10h], r14
0x180089ddc  jz      short loc_180089DFC
0x180089dde  lea     rdx, [rbp+57h+var_58]
0x180089de2  mov     rcx, rdi
0x180089de5  call    ?find_ith@Utils@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_K@Z; Utils::find_ith(std::wstring const &,std::wstring const &,unsigned __int64)
0x180089dea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180089dee  jz      short loc_180089DFC
0x180089df0  mov     rdx, rax
0x180089df3  mov     rcx, rdi; Src
0x180089df6  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180089dfb  nop
0x180089dfc  mov     [rbp+57h+var_88], r15
0x180089e00  cmp     [rbp+57h+var_80], r14
0x180089e04  jz      short loc_180089E17
0x180089e06  lea     rcx, [rbp+57h+var_88]
0x180089e0a  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180089e0f  test    al, al
0x180089e11  jz      short loc_180089E74
0x180089e13  mov     [rbp+57h+var_80], r14
0x180089e17  mov     [rbp+57h+var_78], r15
0x180089e1b  cmp     [rbp+57h+hModule], r14
0x180089e1f  jz      short loc_180089E32
0x180089e21  lea     rcx, [rbp+57h+var_78]
0x180089e25  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180089e2a  test    al, al
0x180089e2c  jz      short loc_180089E5A
0x180089e2e  mov     [rbp+57h+hModule], r14
0x180089e32  lea     rcx, [rbp+57h+var_58]
0x180089e36  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180089e3b  mov     rax, rdi
0x180089e3e  mov     rcx, [rbp+57h+var_38]
0x180089e42  xor     rcx, rsp; StackCookie
0x180089e45  call    __security_check_cookie
0x180089e4a  add     rsp, 88h
0x180089e51  pop     r15
0x180089e53  pop     r14
0x180089e55  pop     rdi
0x180089e56  pop     rsi
0x180089e57  pop     rbx
0x180089e58  pop     rbp
0x180089e59  retn
0x180089e5a  call    cs:__imp_GetLastError
0x180089e60  test    eax, eax
0x180089e62  jle     short loc_180089E6C
0x180089e64  movzx   eax, ax
0x180089e67  or      eax, 80070000h
0x180089e6c  mov     ecx, eax; this
0x180089e6e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180089e73  nop
0x180089e74  call    cs:__imp_GetLastError
0x180089e7a  test    eax, eax
0x180089e7c  jle     short loc_180089E86
0x180089e7e  movzx   eax, ax
0x180089e81  or      eax, 80070000h
0x180089e86  mov     ecx, eax; this
0x180089e88  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
