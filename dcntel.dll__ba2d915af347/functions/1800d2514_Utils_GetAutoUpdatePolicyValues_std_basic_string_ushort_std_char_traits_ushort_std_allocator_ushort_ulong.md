# Utils::GetAutoUpdatePolicyValues(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong &)

- ea: `0x1800d2514`
- end: `0x1800d27e1`
- name: `?GetAutoUpdatePolicyValues@Utils@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK@Z`
- size: `717`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800940b4`

## callees

- `0x180008dc0`
- `0x180014f2c`
- `0x180016748`
- `0x180016db0`
- `0x180019354`
- `0x18001c194`
- `0x18001daf0`
- `0x18001dcc8`
- `0x18002b470`
- `0x180030574`
- `0x1800d2514`
- `0x18018e010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800d2738`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800d2738`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x1800d2746`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x1800d2746`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800d26d8`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800d26d8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800d26a8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800d26a8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d2565`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d2565`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d258d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d25a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d258d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d25a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d27c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d27c1`
- `OLEAUT32!__imp_SysStringLen` at `0x1800d25f0`
- `OLEAUT32!__imp_SysStringLen` at `0x1800d25f0`

## string_xrefs

- `0x1800d255e`: `updatepolicy.dll`
- `0x1800d2583`: `GetAutoUpdatePolicy`
- `0x1800d2596`: `ReleaseAutoUpdatePolicy`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Utils::GetAutoUpdatePolicyValues(__int64 a1, int *a2)
{
  __int64 v3; // r12
  unsigned int v4; // r14d
  HMODULE Library; // rax
  FARPROC ProcAddress; // rbx
  FARPROC v7; // rax
  void (__fastcall *v8)(BSTR *); // rdi
  int v9; // esi
  UINT v10; // eax
  unsigned __int64 v11; // rbx
  __int64 i; // r8
  unsigned __int64 v13; // r8
  __int128 *p_Src; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  _DWORD *v18; // rax
  _DWORD *v19; // r12
  const wchar_t *v20; // rbx
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // r15
  signed int LastError; // eax
  int v27; // edx
  unsigned int v28; // r8d
  BSTR pbstr; // [rsp+20h] [rbp-69h] BYREF
  wchar_t *EndPtr; // [rsp+28h] [rbp-61h] BYREF
  const int *v31; // [rsp+30h] [rbp-59h] BYREF
  HMODULE hModule; // [rsp+38h] [rbp-51h]
  __int64 v33; // [rsp+40h] [rbp-49h]
  __int128 Src; // [rsp+48h] [rbp-41h] BYREF
  __int128 v35; // [rsp+58h] [rbp-31h]
  wchar_t *String[2]; // [rsp+68h] [rbp-21h] BYREF
  __m128i si128; // [rsp+78h] [rbp-11h]
  _OWORD v38[2]; // [rsp+88h] [rbp-1h] BYREF

  v3 = a1;
  v33 = a1;
  v4 = -2147467259;
  pbstr = 0;
  Library = LoadLibraryExW(L"updatepolicy.dll", 0, 0x800u);
  v31 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = Library;
  if ( !Library )
  {
    v8 = 0;
    goto LABEL_27;
  }
  ProcAddress = GetProcAddress(Library, "GetAutoUpdatePolicy");
  v7 = GetProcAddress(hModule, "ReleaseAutoUpdatePolicy");
  v8 = (void (__fastcall *)(BSTR *))v7;
  if ( ProcAddress && v7 && ((int (__fastcall *)(BSTR *))ProcAddress)(&pbstr) >= 0 )
  {
    v9 = 0;
    *(_OWORD *)String = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(String[0]) = 0;
    v10 = SysStringLen(pbstr);
    Src = 0;
    v35 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&Src, pbstr, v10);
    std::wstring::append(&Src, L"|");
    v11 = 0;
    for ( i = 0; ; i = v24 + 1 )
    {
      v22 = std::wstring::find(&Src, L"|", i);
      v24 = v22;
      if ( v22 == -1 )
      {
        std::wstring::~wstring((char **)&Src);
        std::wstring::~wstring((char **)String);
        v4 = 0;
        break;
      }
      memset(v38, 0, sizeof(v38));
      if ( (unsigned __int64)v35 < v11 )
        goto LABEL_35;
      v13 = v35 - v11;
      if ( (unsigned __int64)v35 - v11 >= v22 - v11 )
        v13 = v22 - v11;
      p_Src = &Src;
      if ( *((_QWORD *)&v35 + 1) > 7u )
        p_Src = (__int128 *)Src;
      std::wstring::_Construct<1,unsigned short const *>((char **)v38, (char *)p_Src + 2 * v11, v13);
      std::wstring::operator=(String, v38);
      std::wstring::~wstring((char **)v38);
      if ( v9 )
      {
        if ( v9 != 1 )
          goto LABEL_24;
        v18 = (_DWORD *)_o__errno(v16, v15, v17);
        v19 = v18;
        v20 = (const wchar_t *)String;
        if ( si128.m128i_i64[1] > 7uLL )
          v20 = String[0];
        EndPtr = 0;
        *v18 = 0;
        v21 = wcstol(v20, &EndPtr, 10);
        if ( v20 == EndPtr )
        {
          std::_Xinvalid_argument("invalid stol argument");
LABEL_24:
          std::wstring::~wstring((char **)&Src);
          std::wstring::~wstring((char **)String);
          break;
        }
        if ( *v19 == 34 )
        {
          std::_Xout_of_range("stol argument out of range");
          __debugbreak();
        }
        *a2 = v21;
        v3 = v33;
      }
      else
      {
        std::wstring::operator=(v3, String);
      }
      v11 = v24 + 1;
      ++v9;
    }
  }
LABEL_27:
  if ( pbstr )
    v8(&pbstr);
  v31 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v31) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v27, v28);
LABEL_35:
    std::_String_val<std::_Simple_types<unsigned short>>::_Xran(v23);
  }
  return v4;
}

```

## disassembly

```asm
0x1800d2514  mov     [rsp-8+arg_10], rbx
0x1800d2519  push    rbp
0x1800d251a  push    rsi
0x1800d251b  push    rdi
0x1800d251c  push    r12
0x1800d251e  push    r13
0x1800d2520  push    r14
0x1800d2522  push    r15
0x1800d2524  lea     rbp, [rsp-27h]
0x1800d2529  sub     rsp, 0B0h
0x1800d2530  mov     rax, cs:__security_cookie
0x1800d2537  xor     rax, rsp
0x1800d253a  mov     [rbp+57h+var_38], rax
0x1800d253e  mov     r13, rdx
0x1800d2541  mov     r12, rcx
0x1800d2544  mov     [rbp+57h+var_A0], rcx
0x1800d2548  mov     r14d, 80004005h
0x1800d254e  mov     [rbp+57h+pbstr], 0
0x1800d2556  xor     edx, edx; hFile
0x1800d2558  mov     r8d, 800h; dwFlags
0x1800d255e  lea     rcx, aUpdatepolicyDl; "updatepolicy.dll"
0x1800d2565  call    cs:__imp_LoadLibraryExW
0x1800d256b  lea     rbx, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800d2572  mov     [rbp+57h+var_B0], rbx
0x1800d2576  mov     [rbp+57h+hModule], rax
0x1800d257a  test    rax, rax
0x1800d257d  jz      loc_1800D2769
0x1800d2583  lea     rdx, aGetautoupdatep; "GetAutoUpdatePolicy"
0x1800d258a  mov     rcx, rax; hModule
0x1800d258d  call    cs:__imp_GetProcAddress
0x1800d2593  mov     rbx, rax
0x1800d2596  lea     rdx, aReleaseautoupd; "ReleaseAutoUpdatePolicy"
0x1800d259d  mov     rcx, [rbp+57h+hModule]; hModule
0x1800d25a1  call    cs:__imp_GetProcAddress
0x1800d25a7  mov     rdi, rax
0x1800d25aa  test    rbx, rbx
0x1800d25ad  jz      loc_1800D2760
0x1800d25b3  test    rax, rax
0x1800d25b6  jz      loc_1800D2760
0x1800d25bc  lea     rcx, [rbp+57h+pbstr]
0x1800d25c0  mov     rax, rbx
0x1800d25c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d25c8  test    eax, eax
0x1800d25ca  js      loc_1800D2760
0x1800d25d0  xor     esi, esi
0x1800d25d2  xorps   xmm0, xmm0
0x1800d25d5  movups  xmmword ptr [rbp+57h+String], xmm0
0x1800d25d9  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800d25e1  movdqu  [rbp+57h+var_68], xmm1
0x1800d25e6  xor     eax, eax
0x1800d25e8  mov     word ptr [rbp+57h+String], ax
0x1800d25ec  mov     rcx, [rbp+57h+pbstr]; pbstr
0x1800d25f0  call    cs:__imp_SysStringLen
0x1800d25f6  mov     r8d, eax
0x1800d25f9  xorps   xmm0, xmm0
0x1800d25fc  movups  [rbp+57h+Src], xmm0
0x1800d2600  xorps   xmm1, xmm1
0x1800d2603  movdqu  [rbp+57h+var_88], xmm1
0x1800d2608  mov     rdx, [rbp+57h+pbstr]
0x1800d260c  lea     rcx, [rbp+57h+Src]
0x1800d2610  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800d2615  nop
0x1800d2616  lea     rdx, asc_1801B58D8; "|"
0x1800d261d  lea     rcx, [rbp+57h+Src]; Src
0x1800d2621  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800d2626  xor     ebx, ebx
0x1800d2628  xor     r8d, r8d
0x1800d262b  jmp     loc_1800D26FC
0x1800d2630  xorps   xmm0, xmm0
0x1800d2633  movups  [rbp+57h+var_58], xmm0
0x1800d2637  xorps   xmm1, xmm1
0x1800d263a  movdqu  [rbp+57h+var_48], xmm1
0x1800d263f  mov     r8, qword ptr [rbp+57h+var_88]
0x1800d2643  cmp     r8, rbx
0x1800d2646  jb      loc_1800D27DB
0x1800d264c  sub     r8, rbx
0x1800d264f  mov     rax, r15
0x1800d2652  sub     rax, rbx
0x1800d2655  cmp     r8, rax
0x1800d2658  cmovnb  r8, rax
0x1800d265c  lea     rax, [rbp+57h+Src]
0x1800d2660  cmp     qword ptr [rbp+57h+var_88+8], 7
0x1800d2665  cmova   rax, qword ptr [rbp+57h+Src]
0x1800d266a  lea     rdx, [rax+rbx*2]
0x1800d266e  lea     rcx, [rbp+57h+var_58]
0x1800d2672  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800d2677  lea     rdx, [rbp+57h+var_58]
0x1800d267b  lea     rcx, [rbp+57h+String]
0x1800d267f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800d2684  lea     rcx, [rbp+57h+var_58]
0x1800d2688  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d268d  test    esi, esi
0x1800d268f  jnz     short loc_1800D269F
0x1800d2691  lea     rdx, [rbp+57h+String]
0x1800d2695  mov     rcx, r12
0x1800d2698  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800d269d  jmp     short loc_1800D26F3
0x1800d269f  cmp     esi, 1
0x1800d26a2  jnz     loc_1800D274D
0x1800d26a8  call    cs:__imp__o__errno
0x1800d26ae  mov     r12, rax
0x1800d26b1  lea     rbx, [rbp+57h+String]
0x1800d26b5  cmp     qword ptr [rbp+57h+var_68+8], 7
0x1800d26ba  cmova   rbx, [rbp+57h+String]
0x1800d26bf  mov     [rbp+57h+EndPtr], 0
0x1800d26c7  mov     dword ptr [rax], 0
0x1800d26cd  lea     r8d, [rsi+9]; Radix
0x1800d26d1  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x1800d26d5  mov     rcx, rbx; String
0x1800d26d8  call    cs:__imp_wcstol
0x1800d26de  cmp     rbx, [rbp+57h+EndPtr]
0x1800d26e2  jz      short loc_1800D273F
0x1800d26e4  cmp     dword ptr [r12], 22h ; '"'
0x1800d26e9  jz      short loc_1800D2731
0x1800d26eb  mov     [r13+0], eax
0x1800d26ef  mov     r12, [rbp+57h+var_A0]
0x1800d26f3  lea     rbx, [r15+1]
0x1800d26f7  inc     esi
0x1800d26f9  mov     r8, rbx
0x1800d26fc  lea     rdx, asc_1801B58D8; "|"
0x1800d2703  lea     rcx, [rbp+57h+Src]
0x1800d2707  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x1800d270c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d2710  mov     r15, rax
0x1800d2713  jnz     loc_1800D2630
0x1800d2719  lea     rcx, [rbp+57h+Src]
0x1800d271d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d2722  nop
0x1800d2723  lea     rcx, [rbp+57h+String]
0x1800d2727  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d272c  xor     r14d, r14d
0x1800d272f  jmp     short loc_1800D2760
0x1800d2731  lea     rcx, aStolArgumentOu; "stol argument out of range"
0x1800d2738  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1800d273e  int     3; Trap to Debugger
0x1800d273f  lea     rcx, aInvalidStolArg; "invalid stol argument"
0x1800d2746  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x1800d274c  nop
0x1800d274d  lea     rcx, [rbp+57h+Src]
0x1800d2751  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d2756  nop
0x1800d2757  lea     rcx, [rbp+57h+String]
0x1800d275b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d2760  lea     rbx, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800d2767  jmp     short loc_1800D276B
0x1800d2769  xor     edi, edi
0x1800d276b  cmp     [rbp+57h+pbstr], 0
0x1800d2770  jz      short loc_1800D277F
0x1800d2772  lea     rcx, [rbp+57h+pbstr]
0x1800d2776  mov     rax, rdi
0x1800d2779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d277e  nop
0x1800d277f  mov     [rbp+57h+var_B0], rbx
0x1800d2783  cmp     [rbp+57h+hModule], 0
0x1800d2788  jz      short loc_1800D2797
0x1800d278a  lea     rcx, [rbp+57h+var_B0]
0x1800d278e  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800d2793  test    al, al
0x1800d2795  jz      short loc_1800D27C1
0x1800d2797  mov     eax, r14d
0x1800d279a  mov     rcx, [rbp+57h+var_38]
0x1800d279e  xor     rcx, rsp; StackCookie
0x1800d27a1  call    __security_check_cookie
0x1800d27a6  mov     rbx, [rsp+0E0h+arg_10]
0x1800d27ae  add     rsp, 0B0h
0x1800d27b5  pop     r15
0x1800d27b7  pop     r14
0x1800d27b9  pop     r13
0x1800d27bb  pop     r12
0x1800d27bd  pop     rdi
0x1800d27be  pop     rsi
0x1800d27bf  pop     rbp
0x1800d27c0  retn
0x1800d27c1  call    cs:__imp_GetLastError
0x1800d27c7  test    eax, eax
0x1800d27c9  jle     short loc_1800D27D3
0x1800d27cb  movzx   eax, ax
0x1800d27ce  or      eax, 80070000h
0x1800d27d3  mov     ecx, eax; this
0x1800d27d5  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800d27da  nop
0x1800d27db  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
