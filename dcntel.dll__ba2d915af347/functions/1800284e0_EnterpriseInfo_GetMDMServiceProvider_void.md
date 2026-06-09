# EnterpriseInfo::GetMDMServiceProvider(void)

- ea: `0x1800284e0`
- end: `0x18002880c`
- name: `?GetMDMServiceProvider@EnterpriseInfo@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `812`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180008dc0`
- `0x180014f2c`
- `0x180016748`
- `0x180016db0`
- `0x18001daf0`
- `0x18001dcc8`
- `0x180021d10`
- `0x1800284e0`
- `0x1800d30d8`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002855a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002855a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028582`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002859f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028582`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002859f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028727`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028727`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028735`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800287f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800287f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028717`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028717`

## string_xrefs

- `0x180028553`: `dmenrollengine.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall EnterpriseInfo::GetMDMServiceProvider(__int64 a1, __int64 a2)
{
  HMODULE Library; // rax
  __int64 (*ProcAddress)(void); // rbx
  FARPROC v5; // rdi
  __int64 v6; // rax
  const char *v7; // r9
  unsigned __int64 v8; // rbx
  _WORD *v9; // rdi
  __int64 SHA256CngHash; // rax
  void *v11; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  signed int LastError; // eax
  int v19; // edx
  unsigned int v20; // r8d
  __int64 v21; // [rsp+20h] [rbp-89h] BYREF
  __int64 v22; // [rsp+28h] [rbp-81h] BYREF
  LPVOID lpMem; // [rsp+30h] [rbp-79h] BYREF
  int v24; // [rsp+38h] [rbp-71h]
  const int *v25; // [rsp+40h] [rbp-69h] BYREF
  HMODULE hModule; // [rsp+48h] [rbp-61h]
  HLOCAL hMem[2]; // [rsp+50h] [rbp-59h] BYREF
  __int128 v28; // [rsp+60h] [rbp-49h] BYREF
  __int64 v29; // [rsp+70h] [rbp-39h]
  __int128 v30; // [rsp+80h] [rbp-29h] BYREF
  _OWORD v31[2]; // [rsp+90h] [rbp-19h] BYREF
  char *v32[4]; // [rsp+B0h] [rbp+7h] BYREF

  v29 = a2;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)a2, L"#", 1u);
  v24 = 1;
  v22 = 0;
  v21 = 0;
  Library = LoadLibraryExW(L"dmenrollengine.dll", 0, 0x800u);
  v25 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetDatabaseManagerInstance");
    if ( ProcAddress )
    {
      v5 = GetProcAddress(hModule, "GetProviderID");
      if ( v5 )
      {
        v6 = ProcAddress();
        if ( v6 )
        {
          if ( (*(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v6 + 32LL))(v6, 222306401, &v22) >= 0
            && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 24LL))(v22, &v21) >= 0 )
          {
            if ( v21 )
            {
              v30 = 0;
              if ( (*(int (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v21 + 24LL))(v21, &v30) >= 0 )
              {
                lpMem = 0;
                v28 = v30;
                if ( ((int (__fastcall *)(__int128 *, LPVOID *))v5)(&v28, &lpMem) >= 0 )
                {
                  v8 = -1;
                  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                    hMem,
                    (char *)lpMem,
                    0xFFFFFFFFFFFFFFFFuLL,
                    v7);
                  v9 = hMem[0];
                  hMem[0] = 0;
                  *(_QWORD *)&v28 = v9;
                  if ( v9 )
                  {
                    memset(v31, 0, sizeof(v31));
                    do
                      ++v8;
                    while ( v9[v8] );
                    std::wstring::_Construct<1,unsigned short const *>((char **)v31, v9, v8);
                    SHA256CngHash = Utils::GetSHA256CngHash(v32, v31);
                    std::wstring::operator=(a2, SHA256CngHash);
                    std::wstring::~wstring(v32);
                    std::wstring::~wstring((char **)v31);
                    LocalFree(v9);
                  }
                }
                v11 = lpMem;
                if ( lpMem )
                {
                  ProcessHeap = GetProcessHeap();
                  HeapFree(ProcessHeap, 0, v11);
                }
              }
            }
          }
        }
      }
    }
  }
  v13 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v25 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v25) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v19, v20);
      JUMPOUT(0x18002880BLL);
    }
    hModule = 0;
  }
  v15 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v16 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return a2;
}

```

## disassembly

```asm
0x1800284e0  mov     [rsp-8+arg_0], rbx
0x1800284e5  mov     [rsp-8+arg_10], rsi
0x1800284ea  push    rbp
0x1800284eb  push    rdi
0x1800284ec  push    r12
0x1800284ee  push    r14
0x1800284f0  push    r15
0x1800284f2  lea     rbp, [rsp-37h]
0x1800284f7  sub     rsp, 0E0h
0x1800284fe  mov     rax, cs:__security_cookie
0x180028505  xor     rax, rsp
0x180028508  mov     [rbp+57h+var_30], rax
0x18002850c  mov     rsi, rdx
0x18002850f  mov     [rbp+57h+var_90], rdx
0x180028513  xor     r15d, r15d
0x180028516  mov     [rbp+57h+var_C8], r15d
0x18002851a  xorps   xmm0, xmm0
0x18002851d  movups  xmmword ptr [rdx], xmm0
0x180028520  mov     [rdx+10h], r15
0x180028524  mov     [rdx+18h], r15
0x180028528  lea     ebx, [r15+1]
0x18002852c  mov     r8d, ebx
0x18002852f  lea     rdx, asc_1801B4764; "#"
0x180028536  mov     rcx, rsi
0x180028539  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002853e  mov     [rbp+57h+var_C8], ebx
0x180028541  mov     [rsp+100h+var_D8], r15
0x180028546  mov     [rsp+100h+var_E0], r15
0x18002854b  xor     edx, edx; hFile
0x18002854d  mov     r8d, 800h; dwFlags
0x180028553  lea     rcx, aDmenrollengine; "dmenrollengine.dll"
0x18002855a  call    cs:__imp_LoadLibraryExW
0x180028560  lea     r12, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180028567  mov     [rbp+57h+var_C0], r12
0x18002856b  mov     [rbp+57h+hModule], rax
0x18002856f  test    rax, rax
0x180028572  jz      loc_18002873C
0x180028578  lea     rdx, aGetdatabaseman; "GetDatabaseManagerInstance"
0x18002857f  mov     rcx, rax; hModule
0x180028582  call    cs:__imp_GetProcAddress
0x180028588  mov     rbx, rax
0x18002858b  test    rax, rax
0x18002858e  jz      loc_18002873C
0x180028594  lea     rdx, aGetproviderid; "GetProviderID"
0x18002859b  mov     rcx, [rbp+57h+hModule]; hModule
0x18002859f  call    cs:__imp_GetProcAddress
0x1800285a5  mov     rdi, rax
0x1800285a8  test    rax, rax
0x1800285ab  jz      loc_18002873C
0x1800285b1  mov     rax, rbx
0x1800285b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285b9  mov     rbx, rax
0x1800285bc  test    rax, rax
0x1800285bf  jz      loc_18002873C
0x1800285c5  mov     rax, [rax]
0x1800285c8  mov     r14, [rax+20h]
0x1800285cc  mov     rcx, [rsp+100h+var_D8]
0x1800285d1  test    rcx, rcx
0x1800285d4  jz      short loc_1800285E8
0x1800285d6  mov     [rsp+100h+var_D8], r15
0x1800285db  mov     rax, [rcx]
0x1800285de  mov     rax, [rax+10h]
0x1800285e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285e7  nop
0x1800285e8  lea     r8, [rsp+100h+var_D8]
0x1800285ed  mov     edx, 0D402061h
0x1800285f2  mov     rcx, rbx
0x1800285f5  mov     rax, r14
0x1800285f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285fd  test    eax, eax
0x1800285ff  js      loc_18002873C
0x180028605  mov     rbx, [rsp+100h+var_D8]
0x18002860a  mov     rax, [rbx]
0x18002860d  mov     r14, [rax+18h]
0x180028611  mov     rcx, [rsp+100h+var_E0]
0x180028616  test    rcx, rcx
0x180028619  jz      short loc_18002862D
0x18002861b  mov     [rsp+100h+var_E0], r15
0x180028620  mov     rax, [rcx]
0x180028623  mov     rax, [rax+10h]
0x180028627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002862c  nop
0x18002862d  lea     rdx, [rsp+100h+var_E0]
0x180028632  mov     rcx, rbx
0x180028635  mov     rax, r14
0x180028638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002863d  test    eax, eax
0x18002863f  js      loc_18002873C
0x180028645  mov     rcx, [rsp+100h+var_E0]
0x18002864a  test    rcx, rcx
0x18002864d  jz      loc_18002873C
0x180028653  xorps   xmm0, xmm0
0x180028656  movups  [rbp+57h+var_80], xmm0
0x18002865a  mov     rax, [rcx]
0x18002865d  lea     rdx, [rbp+57h+var_80]
0x180028661  mov     rax, [rax+18h]
0x180028665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002866a  test    eax, eax
0x18002866c  js      loc_18002873C
0x180028672  mov     [rbp+57h+lpMem], r15
0x180028676  movaps  xmm0, [rbp+57h+var_80]
0x18002867a  movdqa  [rbp+57h+var_A0], xmm0
0x18002867f  lea     rdx, [rbp+57h+lpMem]
0x180028683  lea     rcx, [rbp+57h+var_A0]
0x180028687  mov     rax, rdi
0x18002868a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002868f  test    eax, eax
0x180028691  js      loc_18002871E
0x180028697  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002869b  mov     r8, rbx
0x18002869e  mov     rdx, [rbp+57h+lpMem]
0x1800286a2  lea     rcx, [rbp+57h+hMem]
0x1800286a6  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800286ab  nop
0x1800286ac  mov     rdi, [rbp+57h+hMem]
0x1800286b0  mov     [rbp+57h+hMem], r15
0x1800286b4  mov     qword ptr [rbp+57h+var_A0], rdi
0x1800286b8  test    rdi, rdi
0x1800286bb  jnz     short loc_1800286BF
0x1800286bd  jmp     short loc_18002871E
0x1800286bf  xorps   xmm0, xmm0
0x1800286c2  movups  [rbp+57h+var_70], xmm0
0x1800286c6  xorps   xmm1, xmm1
0x1800286c9  movdqu  [rbp+57h+var_60], xmm1
0x1800286ce  inc     rbx
0x1800286d1  cmp     [rdi+rbx*2], r15w
0x1800286d6  jnz     short loc_1800286CE
0x1800286d8  mov     r8, rbx
0x1800286db  mov     rdx, rdi
0x1800286de  lea     rcx, [rbp+57h+var_70]
0x1800286e2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800286e7  nop
0x1800286e8  lea     rdx, [rbp+57h+var_70]
0x1800286ec  lea     rcx, [rbp+57h+var_50]
0x1800286f0  call    ?GetSHA256CngHash@Utils@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utils::GetSHA256CngHash(std::wstring const &)
0x1800286f5  mov     rdx, rax
0x1800286f8  mov     rcx, rsi
0x1800286fb  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180028700  lea     rcx, [rbp+57h+var_50]
0x180028704  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028709  nop
0x18002870a  lea     rcx, [rbp+57h+var_70]
0x18002870e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028713  nop
0x180028714  mov     rcx, rdi; hMem
0x180028717  call    cs:__imp_LocalFree
0x18002871d  nop
0x18002871e  mov     rbx, [rbp+57h+lpMem]
0x180028722  test    rbx, rbx
0x180028725  jz      short loc_18002873C
0x180028727  call    cs:__imp_GetProcessHeap
0x18002872d  mov     r8, rbx; lpMem
0x180028730  xor     edx, edx; dwFlags
0x180028732  mov     rcx, rax; hHeap
0x180028735  call    cs:__imp_HeapFree
0x18002873b  nop
0x18002873c  mov     rcx, [rsp+100h+var_E0]
0x180028741  test    rcx, rcx
0x180028744  jz      short loc_180028758
0x180028746  mov     [rsp+100h+var_E0], r15
0x18002874b  mov     rax, [rcx]
0x18002874e  mov     rax, [rax+10h]
0x180028752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028757  nop
0x180028758  mov     rcx, [rsp+100h+var_D8]
0x18002875d  test    rcx, rcx
0x180028760  jz      short loc_180028774
0x180028762  mov     [rsp+100h+var_D8], r15
0x180028767  mov     rax, [rcx]
0x18002876a  mov     rax, [rax+10h]
0x18002876e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028773  nop
0x180028774  mov     [rbp+57h+var_C0], r12
0x180028778  cmp     [rbp+57h+hModule], r15
0x18002877c  jz      short loc_18002878F
0x18002877e  lea     rcx, [rbp+57h+var_C0]
0x180028782  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180028787  test    al, al
0x180028789  jz      short loc_1800287F2
0x18002878b  mov     [rbp+57h+hModule], r15
0x18002878f  mov     rcx, [rsp+100h+var_E0]
0x180028794  test    rcx, rcx
0x180028797  jz      short loc_1800287AB
0x180028799  mov     [rsp+100h+var_E0], r15
0x18002879e  mov     rax, [rcx]
0x1800287a1  mov     rax, [rax+10h]
0x1800287a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287aa  nop
0x1800287ab  mov     rcx, [rsp+100h+var_D8]
0x1800287b0  test    rcx, rcx
0x1800287b3  jz      short loc_1800287C7
0x1800287b5  mov     [rsp+100h+var_D8], r15
0x1800287ba  mov     rdx, [rcx]
0x1800287bd  mov     rax, [rdx+10h]
0x1800287c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287c6  nop
0x1800287c7  mov     rax, rsi
0x1800287ca  mov     rcx, [rbp+57h+var_30]
0x1800287ce  xor     rcx, rsp; StackCookie
0x1800287d1  call    __security_check_cookie
0x1800287d6  lea     r11, [rsp+100h+var_20]
0x1800287de  mov     rbx, [r11+30h]
0x1800287e2  mov     rsi, [r11+40h]
0x1800287e6  mov     rsp, r11
0x1800287e9  pop     r15
0x1800287eb  pop     r14
0x1800287ed  pop     r12
0x1800287ef  pop     rdi
0x1800287f0  pop     rbp
0x1800287f1  retn
0x1800287f2  call    cs:__imp_GetLastError
0x1800287f8  test    eax, eax
0x1800287fa  jle     short loc_180028804
0x1800287fc  movzx   eax, ax
0x1800287ff  or      eax, 80070000h
0x180028804  mov     ecx, eax; this
0x180028806  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
