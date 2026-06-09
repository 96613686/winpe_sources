# NetworkInfo::GetMCCMNC(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,uchar,SimNumber_2)

- ea: `0x18004fed8`
- end: `0x180050193`
- name: `?GetMCCMNC@NetworkInfo@@CAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0EW4SimNumber_2@@@Z`
- size: `699`
- prototype: `__int64 __fastcall(wchar_t *S1, wchar_t *)`
- caller_count: `8`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004fd00`
- `0x18004fdf0`
- `0x1800501a0`
- `0x180050290`
- `0x1800b7e50`
- `0x1800b7f40`
- `0x1800b8030`
- `0x1800b8120`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x1800157b8`
- `0x180016748`
- `0x180016db0`
- `0x180019b0c`
- `0x18001daf0`
- `0x18001dcc8`
- `0x18002b4f0`
- `0x18004fed8`
- `0x180051070`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004ffa9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004ffa9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004fff0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004fff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005015f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005015f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050179`

## string_xrefs

- `0x18004ffa2`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HMODULE __fastcall NetworkInfo::GetMCCMNC(wchar_t *S1, wchar_t *a2, __int64 a3, int a4)
{
  wchar_t *v6; // rdi
  wchar_t *v7; // rcx
  HMODULE result; // rax
  __int64 *v9; // rcx
  __int64 v10; // rax
  _DWORD *v11; // rsi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 WwanNetworkInfo; // rax
  __int64 v15; // rax
  signed int LastError; // eax
  int v17; // edx
  unsigned int v18; // r8d
  signed int v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  int v22; // [rsp+40h] [rbp-69h] BYREF
  int v23; // [rsp+44h] [rbp-65h] BYREF
  const int *v24; // [rsp+48h] [rbp-61h] BYREF
  HMODULE v25; // [rsp+50h] [rbp-59h]
  char *v26[5]; // [rsp+58h] [rbp-51h] BYREF
  _DWORD v27[20]; // [rsp+80h] [rbp-29h] BYREF

  v6 = S1;
  if ( *((_QWORD *)S1 + 3) )
  {
    if ( *((_QWORD *)S1 + 3) > 7u )
      S1 = *(wchar_t **)S1;
    *((_QWORD *)v6 + 2) = 1;
    *S1 = asc_1801B4764[0];
    S1[1] = 0;
  }
  else
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char **)S1,
      1u,
      a3,
      L"#");
  }
  if ( *((_QWORD *)a2 + 3) )
  {
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v7 = a2;
    else
      v7 = *(wchar_t **)a2;
    *((_QWORD *)a2 + 2) = 1;
    *v7 = asc_1801B4764[0];
    v7[1] = 0;
  }
  else
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char **)a2,
      1u,
      a3,
      L"#");
  }
  v23 = 0;
  memset_0(v27, 0, 0x44u);
  v22 = 68;
  result = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v24 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v25 = result;
  if ( result )
  {
    result = (HMODULE)GetProcAddress(result, "NtQueryWnfStateData");
    if ( result )
    {
      v9 = &WNF_CELL_HOME_OPERATOR_CAN0;
      if ( a4 != 1 )
        v9 = &WNF_CELL_HOME_OPERATOR_CAN1;
      if ( ((int (__fastcall *)(__int64 *, _QWORD, _QWORD, int *, _DWORD *, int *))result)(v9, 0, 0, &v23, v27, &v22) >= 0
        && v22 == 68 )
      {
        v10 = v27[0] ? (unsigned int)(v27[0] - 1) : 0LL;
        v11 = &v27[8 * v10 + 1];
        if ( v11 )
        {
          v12 = std::to_wstring(v26, (unsigned int)v11[3]);
          std::wstring::operator=(v6, v12);
          std::wstring::~wstring(v26);
          v13 = std::to_wstring(v26, (unsigned int)v11[4]);
          std::wstring::operator=(a2, v13);
          std::wstring::~wstring(v26);
        }
      }
      if ( (unsigned __int8)std::operator==<unsigned short>((wchar_t *)L"#", v6) || !*((_QWORD *)v6 + 2) )
      {
        WwanNetworkInfo = NetworkInfo::GetWwanNetworkInfo((__int64)v26, 1u, a4, 2);
        std::wstring::operator=(v6, WwanNetworkInfo);
        std::wstring::~wstring(v26);
      }
      result = (HMODULE)std::operator==<unsigned short>((wchar_t *)L"#", a2);
      if ( (_BYTE)result || !*((_QWORD *)a2 + 2) )
      {
        v15 = NetworkInfo::GetWwanNetworkInfo((__int64)v26, 1u, a4, 3);
        std::wstring::operator=(a2, v15);
        result = (HMODULE)std::wstring::~wstring(v26);
      }
      v24 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( v25 )
      {
        result = (HMODULE)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v24);
        if ( !(_BYTE)result )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v17, v18);
          __debugbreak();
        }
      }
    }
    else
    {
      v24 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( v25 )
      {
        result = (HMODULE)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v24);
        if ( !(_BYTE)result )
        {
          v19 = GetLastError();
          if ( v19 > 0 )
            v19 = (unsigned __int16)v19 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
          JUMPOUT(0x180050192LL);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004fed8  mov     [rsp-8+arg_10], rbx
0x18004fedd  push    rbp
0x18004fede  push    rsi
0x18004fedf  push    rdi
0x18004fee0  push    r12
0x18004fee2  push    r14
0x18004fee4  lea     rbp, [rsp-37h]
0x18004fee9  sub     rsp, 0E0h
0x18004fef0  mov     rax, cs:__security_cookie
0x18004fef7  xor     rax, rsp
0x18004fefa  mov     [rbp+57h+var_30], rax
0x18004fefe  mov     r14d, r9d
0x18004ff01  mov     rbx, rdx
0x18004ff04  mov     rdi, rcx
0x18004ff07  mov     r12d, 1
0x18004ff0d  cmp     [rcx+18h], r12
0x18004ff11  jb      short loc_18004FF32
0x18004ff13  cmp     qword ptr [rcx+18h], 7
0x18004ff18  jbe     short loc_18004FF1D
0x18004ff1a  mov     rcx, [rcx]
0x18004ff1d  mov     [rdi+10h], r12
0x18004ff21  mov     eax, dword ptr cs:asc_1801B4764; "#"
0x18004ff27  mov     [rcx], ax
0x18004ff2a  xor     eax, eax
0x18004ff2c  mov     [rcx+2], ax
0x18004ff30  jmp     short loc_18004FF41
0x18004ff32  lea     r9, asc_1801B4764; "#"
0x18004ff39  mov     rdx, r12
0x18004ff3c  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18004ff41  cmp     [rbx+18h], r12
0x18004ff45  jb      short loc_18004FF6B
0x18004ff47  cmp     qword ptr [rbx+18h], 7
0x18004ff4c  jbe     short loc_18004FF53
0x18004ff4e  mov     rcx, [rbx]
0x18004ff51  jmp     short loc_18004FF56
0x18004ff53  mov     rcx, rbx
0x18004ff56  mov     [rbx+10h], r12
0x18004ff5a  mov     eax, dword ptr cs:asc_1801B4764; "#"
0x18004ff60  mov     [rcx], ax
0x18004ff63  xor     eax, eax
0x18004ff65  mov     [rcx+2], ax
0x18004ff69  jmp     short loc_18004FF7D
0x18004ff6b  lea     r9, asc_1801B4764; "#"
0x18004ff72  mov     rdx, r12
0x18004ff75  mov     rcx, rbx
0x18004ff78  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18004ff7d  mov     [rbp+57h+var_BC], 0
0x18004ff84  mov     esi, 44h ; 'D'
0x18004ff89  mov     r8d, esi; Size
0x18004ff8c  xor     edx, edx; Val
0x18004ff8e  lea     rcx, [rbp+57h+var_80]; void *
0x18004ff92  call    memset_0
0x18004ff97  mov     [rbp+57h+var_C0], esi
0x18004ff9a  xor     edx, edx; hFile
0x18004ff9c  mov     r8d, 800h; dwFlags
0x18004ffa2  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18004ffa9  call    cs:__imp_LoadLibraryExW
0x18004ffaf  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18004ffb6  mov     [rbp+57h+var_B8], rsi
0x18004ffba  mov     [rbp+57h+var_B0], rax
0x18004ffbe  test    rax, rax
0x18004ffc1  jnz     short loc_18004FFE6
0x18004ffc3  mov     rcx, [rbp+57h+var_30]
0x18004ffc7  xor     rcx, rsp; StackCookie
0x18004ffca  call    __security_check_cookie
0x18004ffcf  mov     rbx, [rsp+100h+arg_10]
0x18004ffd7  add     rsp, 0E0h
0x18004ffde  pop     r14
0x18004ffe0  pop     r12
0x18004ffe2  pop     rdi
0x18004ffe3  pop     rsi
0x18004ffe4  pop     rbp
0x18004ffe5  retn
0x18004ffe6  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18004ffed  mov     rcx, rax; hModule
0x18004fff0  call    cs:__imp_GetProcAddress
0x18004fff6  test    rax, rax
0x18004fff9  jnz     short loc_180050018
0x18004fffb  mov     [rbp+57h+var_B8], rsi
0x18004ffff  cmp     [rbp+57h+var_B0], rax
0x180050003  jz      short loc_18004FFC3
0x180050005  lea     rcx, [rbp+57h+var_B8]
0x180050009  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18005000e  test    al, al
0x180050010  jz      loc_180050179
0x180050016  jmp     short loc_18004FFC3
0x180050018  lea     rdx, WNF_CELL_HOME_OPERATOR_CAN1
0x18005001f  lea     rcx, WNF_CELL_HOME_OPERATOR_CAN0
0x180050026  cmp     r14d, r12d
0x180050029  cmovnz  rcx, rdx
0x18005002d  lea     rdx, [rbp+57h+var_C0]
0x180050031  mov     [rsp+100h+var_D8], rdx
0x180050036  lea     rdx, [rbp+57h+var_80]
0x18005003a  mov     [rsp+100h+var_E0], rdx
0x18005003f  lea     r9, [rbp+57h+var_BC]
0x180050043  xor     r8d, r8d
0x180050046  xor     edx, edx
0x180050048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005004d  test    eax, eax
0x18005004f  js      short loc_1800500B8
0x180050051  cmp     [rbp+57h+var_C0], 44h ; 'D'
0x180050055  jnz     short loc_1800500B8
0x180050057  mov     eax, [rbp+57h+var_80]
0x18005005a  test    eax, eax
0x18005005c  jz      short loc_180050062
0x18005005e  dec     eax
0x180050060  jmp     short loc_180050064
0x180050062  xor     eax, eax
0x180050064  shl     rax, 5
0x180050068  lea     rsi, [rbp+57h+var_7C]
0x18005006c  add     rsi, rax
0x18005006f  jz      short loc_1800500B1
0x180050071  mov     edx, [rsi+0Ch]
0x180050074  lea     rcx, [rbp+57h+var_A8]
0x180050078  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x18005007d  mov     rdx, rax
0x180050080  mov     rcx, rdi
0x180050083  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180050088  lea     rcx, [rbp+57h+var_A8]
0x18005008c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050091  mov     edx, [rsi+10h]
0x180050094  lea     rcx, [rbp+57h+var_A8]
0x180050098  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x18005009d  mov     rdx, rax
0x1800500a0  mov     rcx, rbx
0x1800500a3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800500a8  lea     rcx, [rbp+57h+var_A8]
0x1800500ac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800500b1  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800500b8  mov     rdx, rdi; S1
0x1800500bb  lea     rcx, asc_1801B4764; "#"
0x1800500c2  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NQEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator==<ushort>(ushort const * const,std::wstring const &)
0x1800500c7  test    al, al
0x1800500c9  jnz     short loc_1800500D2
0x1800500cb  cmp     qword ptr [rdi+10h], 0
0x1800500d0  jnz     short loc_1800500FB
0x1800500d2  mov     r9d, 2
0x1800500d8  mov     r8d, r14d
0x1800500db  mov     dl, r12b
0x1800500de  lea     rcx, [rbp+57h+var_A8]
0x1800500e2  call    ?GetWwanNetworkInfo@NetworkInfo@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@EW4SimNumber_2@@W4NetworkWwanInfo_2@@@Z; NetworkInfo::GetWwanNetworkInfo(uchar,SimNumber_2,NetworkWwanInfo_2)
0x1800500e7  mov     rdx, rax
0x1800500ea  mov     rcx, rdi
0x1800500ed  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800500f2  lea     rcx, [rbp+57h+var_A8]
0x1800500f6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800500fb  mov     rdx, rbx; S1
0x1800500fe  lea     rcx, asc_1801B4764; "#"
0x180050105  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NQEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator==<ushort>(ushort const * const,std::wstring const &)
0x18005010a  test    al, al
0x18005010c  jnz     short loc_180050115
0x18005010e  cmp     qword ptr [rbx+10h], 0
0x180050113  jnz     short loc_18005013F
0x180050115  mov     r9d, 3
0x18005011b  mov     r8d, r14d
0x18005011e  mov     dl, r12b
0x180050121  lea     rcx, [rbp+57h+var_A8]
0x180050125  call    ?GetWwanNetworkInfo@NetworkInfo@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@EW4SimNumber_2@@W4NetworkWwanInfo_2@@@Z; NetworkInfo::GetWwanNetworkInfo(uchar,SimNumber_2,NetworkWwanInfo_2)
0x18005012a  mov     rdx, rax
0x18005012d  mov     rcx, rbx
0x180050130  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180050135  lea     rcx, [rbp+57h+var_A8]
0x180050139  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005013e  nop
0x18005013f  mov     [rbp+57h+var_B8], rsi
0x180050143  cmp     [rbp+57h+var_B0], 0
0x180050148  jz      loc_18004FFC3
0x18005014e  lea     rcx, [rbp+57h+var_B8]
0x180050152  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180050157  test    al, al
0x180050159  jnz     loc_18004FFC3
0x18005015f  call    cs:__imp_GetLastError
0x180050165  test    eax, eax
0x180050167  jle     short loc_180050171
0x180050169  movzx   eax, ax
0x18005016c  or      eax, 80070000h
0x180050171  mov     ecx, eax; this
0x180050173  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180050178  int     3; Trap to Debugger
0x180050179  call    cs:__imp_GetLastError
0x18005017f  test    eax, eax
0x180050181  jle     short loc_18005018B
0x180050183  movzx   eax, ax
0x180050186  or      eax, 80070000h
0x18005018b  mov     ecx, eax; this
0x18005018d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
