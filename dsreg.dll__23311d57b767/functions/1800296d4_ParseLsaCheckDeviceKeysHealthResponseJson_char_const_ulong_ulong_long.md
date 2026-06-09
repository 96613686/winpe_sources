# ParseLsaCheckDeviceKeysHealthResponseJson(char const *,ulong,ulong &,long &)

- ea: `0x1800296d4`
- end: `0x180029993`
- name: `?ParseLsaCheckDeviceKeysHealthResponseJson@@YAJPEBDKAEAKAEAJ@Z`
- size: `703`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, unsigned int cbMultiByte, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callers

- `0x1800aa97c`

## callees

- `0x1800084f4`
- `0x18001378c`
- `0x180024dbc`
- `0x18002927c`
- `0x1800296d4`
- `0x18002999c`
- `0x18002b9b4`
- `0x1800307c4`
- `0x180031b38`
- `0x180032530`
- `0x18003334c`
- `0x180043ef8`
- `0x180044300`
- `0x18004654c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297c3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800297b6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180029865`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800297b6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180029865`

## string_xrefs

- `0x180029771`: `ParseLsaCheckDeviceKeysHealthResponseJson`
- `0x18002978b`: `ParseLsaCheckDeviceKeysHealthResponseJson`
- `0x1800297e9`: `ParseLsaCheckDeviceKeysHealthResponseJson`
- `0x18002982f`: `ParseLsaCheckDeviceKeysHealthResponseJson`
- `0x18002988b`: `CJsonParser::Initialize`
- `0x1800298b5`: `CJsonParser::Parse`
- `0x18002976a`: `responseJson`
- `0x180029784`: `responseJson`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ParseLsaCheckDeviceKeysHealthResponseJson(
        LPCCH lpMultiByteStr,
        int cbMultiByte,
        unsigned int *a3,
        int *a4)
{
  unsigned __int16 *v8; // rsi
  _DWORD *v9; // r8
  _DWORD *v10; // r9
  unsigned int v11; // ebx
  int v12; // eax
  __int64 cchWideChar; // rbx
  signed int LastError; // eax
  unsigned __int64 v15; // rax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  int v18; // eax
  const wchar_t *v19; // r8
  _QWORD *v20; // rdi
  __int64 v21; // r14
  _DWORD *v22; // rax
  double *v23; // rax
  __int64 v24; // r14
  _DWORD *v25; // rax
  double *v26; // rax
  unsigned int v27; // edx
  _BYTE v29[16]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v30[2]; // [rsp+40h] [rbp-C0h] BYREF
  void *Block; // [rsp+50h] [rbp-B0h]
  int v32; // [rsp+58h] [rbp-A8h]
  __int64 v33; // [rsp+60h] [rbp-A0h]
  __int64 v34; // [rsp+68h] [rbp-98h]
  int v35; // [rsp+70h] [rbp-90h]
  char v36; // [rsp+74h] [rbp-8Ch]
  __int64 v37; // [rsp+80h] [rbp-80h]
  __int64 v38; // [rsp+88h] [rbp-78h]
  _BYTE v39[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v40[8]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v41[44]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v42; // [rsp+E4h] [rbp-1Ch]
  __int128 v43; // [rsp+F0h] [rbp-10h]

  Block = 0;
  v33 = 0;
  v32 = 0;
  v34 = 12;
  v36 = 0;
  v30[0] = 0;
  v30[1] = 1;
  v35 = 0;
  v38 = 0;
  v37 = 0;
  std::wstring::wstring((__int64)v41);
  v42 = 0;
  v43 = 0;
  v8 = 0;
  *v9 = 0;
  *v10 = 0;
  if ( !lpMultiByteStr )
  {
    v11 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"ParseLsaCheckDeviceKeysHealthResponseJson", L"responseJson");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"ParseLsaCheckDeviceKeysHealthResponseJson", L"responseJson");
    goto LABEL_26;
  }
  v12 = MultiByteToWideChar(0xFDE9u, 8u, lpMultiByteStr, cbMultiByte, 0, 0);
  cchWideChar = v12;
  if ( !v12 )
    goto LABEL_4;
  v15 = 2LL * (v12 + 1);
  if ( !is_mul_ok((int)cchWideChar + 1, 2u) )
    v15 = -1;
  lpWideCharStr = (WCHAR *)operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
  v8 = lpWideCharStr;
  if ( !lpWideCharStr )
  {
    v11 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"ParseLsaCheckDeviceKeysHealthResponseJson");
    goto LABEL_26;
  }
  lpWideCharStr[cchWideChar] = 0;
  v17 = MultiByteToWideChar(0xFDE9u, 8u, lpMultiByteStr, cbMultiByte, lpWideCharStr, cchWideChar);
  if ( v17 )
  {
    v18 = dsreg::CJsonParser::Initialize((dsreg::CJsonParser *)v30, v8, v17 + 1);
    v11 = v18;
    if ( v18 < 0 )
    {
      v19 = L"CJsonParser::Initialize";
LABEL_15:
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"ParseLsaCheckDeviceKeysHealthResponseJson",
        v19,
        (unsigned int)v18);
      goto LABEL_26;
    }
    v18 = dsreg::CJsonParser::Parse((dsreg::CJsonParser *)v30, (struct dsreg::CJsonValue *)v40);
    v11 = v18;
    if ( v18 < 0 )
    {
      v19 = L"CJsonParser::Parse";
      goto LABEL_15;
    }
    v20 = (_QWORD *)v43;
    std::wstring::wstring((__int64)v39, (__int64)L"FailedKeyType");
    v21 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,dsreg::CJsonValue *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,dsreg::CJsonValue *>>,0>>::find(
                       v20,
                       v29,
                       v39);
    std::wstring::_Tidy_deallocate((__int64)v39);
    if ( v21 != *v20 )
    {
      v22 = *(_DWORD **)(v21 + 64);
      if ( *v22 == 2 )
      {
        v23 = (double *)(v22 + 10);
        if ( v23 )
          *a3 = (int)*v23;
      }
    }
    std::wstring::wstring((__int64)v39, (__int64)L"Result");
    v24 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,dsreg::CJsonValue *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,dsreg::CJsonValue *>>,0>>::find(
                       v20,
                       v29,
                       v39);
    std::wstring::_Tidy_deallocate((__int64)v39);
    if ( v24 != *v20 )
    {
      v25 = *(_DWORD **)(v24 + 64);
      if ( *v25 == 2 )
      {
        v26 = (double *)(v25 + 10);
        if ( v26 )
          *a4 = (int)*v26;
      }
    }
  }
  else
  {
LABEL_4:
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x",
      L"ParseLsaCheckDeviceKeysHealthResponseJson",
      L"MultiByteToWideChar",
      v11);
  }
LABEL_26:
  operator delete(v8);
  dsreg::CJsonValue::~CJsonValue((dsreg::CJsonValue *)v40, v27);
  operator delete(Block);
  return v11;
}

```

## disassembly

```asm
0x1800296d4  push    rbp
0x1800296d6  push    rbx
0x1800296d7  push    rsi
0x1800296d8  push    rdi
0x1800296d9  push    r12
0x1800296db  push    r13
0x1800296dd  push    r14
0x1800296df  push    r15
0x1800296e1  lea     rbp, [rsp-18h]
0x1800296e6  sub     rsp, 118h
0x1800296ed  mov     rax, cs:__security_cookie
0x1800296f4  xor     rax, rsp
0x1800296f7  mov     [rbp+50h+var_50], rax
0x1800296fb  mov     r12, r9
0x1800296fe  mov     r15, r8
0x180029701  mov     r14d, edx
0x180029704  mov     rdi, rcx
0x180029707  xor     r13d, r13d
0x18002970a  mov     [rsp+150h+Block], r13
0x18002970f  mov     [rsp+150h+var_F0], r13
0x180029714  mov     [rsp+150h+var_F8], r13d
0x180029719  mov     [rsp+150h+var_E8], 0Ch
0x180029722  mov     [rsp+150h+var_DC], r13b
0x180029727  mov     [rsp+150h+var_110], r13
0x18002972c  mov     [rsp+150h+var_108], 1
0x180029735  mov     [rsp+150h+var_E0], r13d
0x18002973a  mov     [rbp+50h+var_C8], r13
0x18002973e  mov     [rbp+50h+var_D0], r13
0x180029742  lea     rcx, [rbp+50h+var_98]
0x180029746  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002974b  mov     [rbp+50h+var_6C], r13
0x18002974f  xorps   xmm1, xmm1
0x180029752  movdqa  [rbp+50h+var_60], xmm1
0x180029757  mov     esi, r13d
0x18002975a  mov     [r8], r13d
0x18002975d  mov     [r9], r13d
0x180029760  test    rdi, rdi
0x180029763  jnz     short loc_18002979C
0x180029765  mov     ebx, 80070057h
0x18002976a  lea     r8, aResponsejson; "responseJson"
0x180029771  lea     rdx, aParselsacheckd; "ParseLsaCheckDeviceKeysHealthResponseJs"...
0x180029778  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18002977f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180029784  lea     rdx, aResponsejson; "responseJson"
0x18002978b  lea     rcx, aParselsacheckd; "ParseLsaCheckDeviceKeysHealthResponseJs"...
0x180029792  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180029797  jmp     loc_180029954
0x18002979c  mov     [rsp+150h+cchWideChar], r13d; cchWideChar
0x1800297a1  mov     [rsp+150h+lpWideCharStr], r13; lpWideCharStr
0x1800297a6  mov     r9d, r14d; cbMultiByte
0x1800297a9  mov     r8, rdi; lpMultiByteStr
0x1800297ac  mov     edx, 8; dwFlags
0x1800297b1  mov     ecx, 0FDE9h; CodePage
0x1800297b6  call    cs:__imp_MultiByteToWideChar
0x1800297bc  movsxd  rbx, eax
0x1800297bf  test    eax, eax
0x1800297c1  jnz     short loc_1800297FA
0x1800297c3  call    cs:__imp_GetLastError
0x1800297c9  test    eax, eax
0x1800297cb  mov     ebx, eax
0x1800297cd  jle     short loc_1800297D8
0x1800297cf  movzx   ebx, ax
0x1800297d2  or      ebx, 80070000h
0x1800297d8  mov     r9d, ebx
0x1800297db  lea     r8, aMultibytetowid; "MultiByteToWideChar"
0x1800297e2  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x1800297e9  lea     rdx, aParselsacheckd; "ParseLsaCheckDeviceKeysHealthResponseJs"...
0x1800297f0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800297f5  jmp     loc_180029954
0x1800297fa  lea     eax, [rbx+1]
0x1800297fd  movsxd  rcx, eax
0x180029800  mov     eax, 2
0x180029805  mul     rcx
0x180029808  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002980f  cmovb   rax, rcx
0x180029813  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002981a  mov     rcx, rax; unsigned __int64
0x18002981d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180029822  mov     rsi, rax
0x180029825  test    rax, rax
0x180029828  jnz     short loc_180029847
0x18002982a  mov     ebx, 8007000Eh
0x18002982f  lea     rdx, aParselsacheckd; "ParseLsaCheckDeviceKeysHealthResponseJs"...
0x180029836  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18002983d  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180029842  jmp     loc_180029954
0x180029847  mov     [rax+rbx*2], r13w
0x18002984c  mov     [rsp+150h+cchWideChar], ebx; cchWideChar
0x180029850  mov     [rsp+150h+lpWideCharStr], rsi; lpWideCharStr
0x180029855  mov     r9d, r14d; cbMultiByte
0x180029858  mov     r8, rdi; lpMultiByteStr
0x18002985b  mov     edx, 8; dwFlags
0x180029860  mov     ecx, 0FDE9h; CodePage
0x180029865  call    cs:__imp_MultiByteToWideChar
0x18002986b  test    eax, eax
0x18002986d  jz      loc_1800297C3
0x180029873  inc     eax
0x180029875  movsxd  r8, eax; unsigned __int64
0x180029878  mov     rdx, rsi; unsigned __int16 *
0x18002987b  lea     rcx, [rsp+150h+var_110]; this
0x180029880  call    ?Initialize@CJsonParser@dsreg@@QEAAJPEBG_K@Z; dsreg::CJsonParser::Initialize(ushort const *,unsigned __int64)
0x180029885  mov     ebx, eax
0x180029887  test    eax, eax
0x180029889  jns     short loc_1800298A1
0x18002988b  lea     r8, aCjsonparserIni; "CJsonParser::Initialize"
0x180029892  mov     r9d, eax
0x180029895  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18002989c  jmp     loc_1800297E9
0x1800298a1  lea     rdx, [rbp+50h+var_A0]; struct dsreg::CJsonValue *
0x1800298a5  lea     rcx, [rsp+150h+var_110]; this
0x1800298aa  call    ?Parse@CJsonParser@dsreg@@QEAAJPEAVCJsonValue@2@@Z; dsreg::CJsonParser::Parse(dsreg::CJsonValue *)
0x1800298af  mov     ebx, eax
0x1800298b1  test    eax, eax
0x1800298b3  jns     short loc_1800298BE
0x1800298b5  lea     r8, aCjsonparserPar; "CJsonParser::Parse"
0x1800298bc  jmp     short loc_180029892
0x1800298be  mov     rdi, qword ptr [rbp+50h+var_60]
0x1800298c2  lea     rdx, aFailedkeytype; "FailedKeyType"
0x1800298c9  lea     rcx, [rbp+50h+var_C0]
0x1800298cd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800298d2  lea     r8, [rbp+50h+var_C0]
0x1800298d6  lea     rdx, [rsp+150h+var_120]
0x1800298db  mov     rcx, rdi
0x1800298de  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,dsreg::CJsonValue *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,dsreg::CJsonValue *>>,0>>::find(std::wstring const &)
0x1800298e3  mov     r14, [rax]
0x1800298e6  lea     rcx, [rbp+50h+var_C0]
0x1800298ea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800298ef  cmp     r14, [rdi]
0x1800298f2  jz      short loc_18002990B
0x1800298f4  mov     rax, [r14+40h]
0x1800298f8  cmp     dword ptr [rax], 2
0x1800298fb  jnz     short loc_18002990B
0x1800298fd  add     rax, 28h ; '('
0x180029901  jz      short loc_18002990B
0x180029903  cvttsd2si rax, qword ptr [rax]
0x180029908  mov     [r15], eax
0x18002990b  lea     rdx, aResult; "Result"
0x180029912  lea     rcx, [rbp+50h+var_C0]
0x180029916  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002991b  lea     r8, [rbp+50h+var_C0]
0x18002991f  lea     rdx, [rsp+150h+var_120]
0x180029924  mov     rcx, rdi
0x180029927  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCJsonValue@dsreg@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,dsreg::CJsonValue *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,dsreg::CJsonValue *>>,0>>::find(std::wstring const &)
0x18002992c  mov     r14, [rax]
0x18002992f  lea     rcx, [rbp+50h+var_C0]
0x180029933  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029938  cmp     r14, [rdi]
0x18002993b  jz      short loc_180029954
0x18002993d  mov     rax, [r14+40h]
0x180029941  cmp     dword ptr [rax], 2
0x180029944  jnz     short loc_180029954
0x180029946  add     rax, 28h ; '('
0x18002994a  jz      short loc_180029954
0x18002994c  cvttsd2si eax, qword ptr [rax]
0x180029950  mov     [r12], eax
0x180029954  mov     rcx, rsi; Block
0x180029957  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002995c  nop
0x18002995d  lea     rcx, [rbp+50h+var_A0]; this
0x180029961  call    ??1CJsonValue@dsreg@@QEAA@XZ; dsreg::CJsonValue::~CJsonValue(void)
0x180029966  nop
0x180029967  mov     rcx, [rsp+150h+Block]; Block
0x18002996c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029971  mov     eax, ebx
0x180029973  mov     rcx, [rbp+50h+var_50]
0x180029977  xor     rcx, rsp; StackCookie
0x18002997a  call    __security_check_cookie
0x18002997f  add     rsp, 118h
0x180029986  pop     r15
0x180029988  pop     r14
0x18002998a  pop     r13
0x18002998c  pop     r12
0x18002998e  pop     rdi
0x18002998f  pop     rsi
0x180029990  pop     rbx
0x180029991  pop     rbp
0x180029992  retn
```
