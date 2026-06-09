# ContainerCiCacheStart

- ea: `0x180027668`
- end: `0x180027a47`
- name: `ContainerCiCacheStart`
- size: `991`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn)`
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e844`

## callees

- `0x180002690`
- `0x1800026b4`
- `0x1800032b8`
- `0x180006e10`
- `0x180008fac`
- `0x180009a38`
- `0x18000a578`
- `0x1800138b4`
- `0x180021528`
- `0x180021d60`
- `0x1800224dc`
- `0x180024578`
- `0x1800247e4`
- `0x180024f88`
- `0x180026f4c`
- `0x180027668`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180027880`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180027880`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180027741`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180027741`
- `ntdll!RtlFreeUnicodeString` at `0x1800277a8`
- `ntdll!RtlFreeUnicodeString` at `0x1800277a8`

## string_xrefs

- `0x180027a29`: `onecore\vm\common\vml\VmPath.h`
- `0x180027706`: `Windows\System32\catroot\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ContainerCiCacheStart(PCWSTR pszPathIn, _DWORD *a2, _QWORD *a3)
{
  char *v6; // rdi
  _QWORD *v7; // rsi
  _QWORD *v8; // rax
  int v9; // eax
  _QWORD *Files; // rbx
  const char *v11; // r9
  DWORD dwNumberOfProcessors; // esi
  DWORD i; // r15d
  void *v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rbx
  void (__fastcall ***v17)(_QWORD, __int64); // rcx
  __int64 v18; // rdx
  char *v19; // rcx
  void (__fastcall ***v20)(_QWORD, char *); // r8
  __int64 result; // rax
  int v22; // [rsp+20h] [rbp-F8h]
  __int128 v23; // [rsp+38h] [rbp-E0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-D0h]
  __int64 v25; // [rsp+50h] [rbp-C8h]
  struct _UNICODE_STRING *p_UnicodeString; // [rsp+58h] [rbp-C0h] BYREF
  void (__fastcall *v27)(struct CiCacheState *); // [rsp+60h] [rbp-B8h]
  __int64 Src; // [rsp+70h] [rbp-A8h] BYREF
  wchar_t **v29; // [rsp+78h] [rbp-A0h]
  struct _UNICODE_STRING UnicodeString; // [rsp+90h] [rbp-88h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+A0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  *a3 = 0;
  try
  {
    EnableUSN(pszPathIn);
    SetCatalogHints(pszPathIn);
    v6 = (char *)operator new(0x70u);
    *(_WORD *)(v6 + 109) = 0;
    v6[111] = 0;
    *(_OWORD *)v6 = 0;
    *((_QWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 3) = 7;
    *(_WORD *)v6 = 0;
    *((_QWORD *)v6 + 4) = 0;
    *((_QWORD *)v6 + 5) = 0;
    *((_QWORD *)v6 + 6) = 0;
    v7 = v6 + 56;
    *((_QWORD *)v6 + 7) = 0;
    *((_QWORD *)v6 + 8) = 0;
    *((_QWORD *)v6 + 9) = 0;
    *((_QWORD *)v6 + 10) = 0;
    *((_QWORD *)v6 + 11) = 0;
    *((_QWORD *)v6 + 12) = 0;
    *((_DWORD *)v6 + 26) = 0;
    v6[108] = 0;
    v8 = Vml::CombineFilePath(&Src, pszPathIn, L"Windows\\System32\\catroot\\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}");
    if ( v8[3] > 7u )
      v8 = (_QWORD *)*v8;
    UnicodeString = 0;
    v9 = RtlDosPathNameToNtPathName_U_WithStatus(v8, &UnicodeString, 0, 0);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x29E,
        (unsigned int)"onecore\\vm\\common\\vml\\VmPath.h",
        (const char *)(unsigned int)v9,
        v22);
    p_UnicodeString = &UnicodeString;
    LOBYTE(v27) = 1;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    std::wstring::_Construct<1,unsigned short const *>(
      (__int64)&v23,
      UnicodeString.Buffer,
      (unsigned __int64)UnicodeString.Length >> 1);
    RtlFreeUnicodeString(&UnicodeString);
    std::wstring::operator=(v6, &v23);
    std::wstring::~wstring((char **)&v23);
    std::wstring::~wstring((char **)&Src);
    Src = 5;
    v29 = off_18004AE10;
    *(_QWORD *)&UnicodeString.Length = 5;
    UnicodeString.Buffer = (PWSTR)off_18004AE38;
    Files = (_QWORD *)FindFiles((__int64)&v23, pszPathIn, &UnicodeString, &Src, 1);
    if ( v7 != Files )
    {
      std::vector<std::wstring>::_Tidy(v6 + 56);
      *v7 = *Files;
      *((_QWORD *)v6 + 8) = Files[1];
      *((_QWORD *)v6 + 9) = Files[2];
      *Files = 0;
      Files[1] = 0;
      Files[2] = 0;
    }
    std::vector<std::wstring>::_Tidy(&v23);
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetSystemInfo(&SystemInfo);
    dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
    if ( SystemInfo.dwNumberOfProcessors >= 4 )
    {
      dwNumberOfProcessors = 4;
    }
    else if ( SystemInfo.dwNumberOfProcessors <= 1 )
    {
      dwNumberOfProcessors = 1;
    }
    for ( i = 0; i < dwNumberOfProcessors; ++i )
    {
      v23 = 0;
      v24 = 0;
      p_UnicodeString = (struct _UNICODE_STRING *)v6;
      v27 = CacheFiles;
      v14 = operator new(0x120u);
      *(_QWORD *)&UnicodeString.Length = v14;
      memset_0(v14, 0, 0x120u);
      v15 = std::_Task_async_state<void>::_Task_async_state<void>((__int64)v14, &p_UnicodeString);
      v16 = v15;
      *(_QWORD *)&v23 = v15;
      BYTE8(v23) = 0;
      LOBYTE(v24) = 0;
      if ( !v15 )
        std::_Throw_future_error2(4);
      Src = v15;
      LOBYTE(v29) = 1;
      _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 8), 0xFFFFFFFF) == 1 )
      {
        v17 = *(void (__fastcall ****)(_QWORD, __int64))(v15 + 200);
        if ( v17 )
          (**v17)(v17, v15);
        else
          (**(void (__fastcall ***)(__int64, __int64))v15)(v15, 1);
      }
      v18 = *((_QWORD *)v6 + 5);
      if ( v18 == *((_QWORD *)v6 + 6) )
      {
        std::vector<std::future<void>>::_Emplace_reallocate<std::future<void>>(v6 + 32, v18, &Src);
        v19 = (char *)Src;
      }
      else
      {
        v19 = 0;
        *(_QWORD *)v18 = v16;
        *(_BYTE *)(v18 + 8) = 1;
        *((_QWORD *)v6 + 5) += 16LL;
      }
      if ( v19 && _InterlockedExchangeAdd((volatile signed __int32 *)v19 + 2, 0xFFFFFFFF) == 1 )
      {
        v20 = (void (__fastcall ***)(_QWORD, char *))*((_QWORD *)v19 + 25);
        if ( v20 )
          (**v20)(*((_QWORD *)v19 + 25), v19);
        else
          (**(void (__fastcall ***)(char *, __int64))v19)(v19, 1);
      }
    }
    *a2 = (__int64)(*((_QWORD *)v6 + 8) - *((_QWORD *)v6 + 7)) >> 5;
    *a3 = v6;
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1C7,
                           (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x180027668  push    rbx
0x18002766a  push    rsi
0x18002766b  push    rdi
0x18002766c  push    r12
0x18002766e  push    r13
0x180027670  push    r14
0x180027672  push    r15
0x180027674  sub     rsp, 0E0h
0x18002767b  mov     rax, cs:__security_cookie
0x180027682  xor     rax, rsp
0x180027685  mov     [rsp+118h+var_48], rax
0x18002768d  mov     r12, r8
0x180027690  mov     r13, rdx
0x180027693  mov     rbx, rcx
0x180027696  xor     r14d, r14d
0x180027699  mov     [r8], r14
0x18002769c  call    ?EnableUSN@@YAXPEBG@Z; EnableUSN(ushort const *)
0x1800276a1  mov     rcx, rbx; pszPathIn
0x1800276a4  call    ?SetCatalogHints@@YAXPEBG@Z; SetCatalogHints(ushort const *)
0x1800276a9  lea     ecx, [r14+70h]; Size
0x1800276ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800276b2  mov     rdi, rax
0x1800276b5  xor     eax, eax
0x1800276b7  mov     [rdi+6Dh], ax
0x1800276bb  mov     [rdi+6Fh], al
0x1800276be  xorps   xmm0, xmm0
0x1800276c1  movups  xmmword ptr [rdi], xmm0
0x1800276c4  mov     [rdi+10h], r14
0x1800276c8  mov     qword ptr [rdi+18h], 7
0x1800276d0  mov     [rdi], r14w
0x1800276d4  mov     [rdi+20h], r14
0x1800276d8  mov     [rdi+28h], r14
0x1800276dc  mov     [rdi+30h], r14
0x1800276e0  lea     rsi, [rdi+38h]
0x1800276e4  mov     [rsi], r14
0x1800276e7  mov     [rsi+8], r14
0x1800276eb  mov     [rsi+10h], r14
0x1800276ef  mov     [rdi+50h], r14
0x1800276f3  mov     [rdi+58h], rax
0x1800276f7  mov     [rdi+60h], rax
0x1800276fb  mov     [rdi+68h], eax
0x1800276fe  mov     [rdi+6Ch], al
0x180027701  mov     [rsp+118h+var_E8], rdi
0x180027706  lea     r8, aWindowsSystem3_6; "Windows\\System32\\catroot\\{F750E6C3-3"...
0x18002770d  mov     rdx, rbx; pszPathIn
0x180027710  lea     rcx, [rsp+118h+Src]; Src
0x180027715  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18002771a  nop
0x18002771b  cmp     qword ptr [rax+18h], 7
0x180027720  jbe     short loc_180027725
0x180027722  mov     rax, [rax]
0x180027725  xorps   xmm0, xmm0
0x180027728  movups  xmmword ptr [rsp+118h+UnicodeString.Length], xmm0
0x180027730  xor     r9d, r9d
0x180027733  xor     r8d, r8d
0x180027736  lea     rdx, [rsp+118h+UnicodeString]
0x18002773e  mov     rcx, rax
0x180027741  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180027748  nop     dword ptr [rax+rax+00h]
0x18002774d  mov     rcx, [rsp+118h]; this
0x180027755  test    eax, eax
0x180027757  js      loc_180027A26
0x18002775d  lea     rax, [rsp+118h+UnicodeString]
0x180027765  mov     [rsp+118h+var_C0], rax
0x18002776a  mov     byte ptr [rsp+118h+var_B8], 1
0x18002776f  xorps   xmm0, xmm0
0x180027772  movups  [rsp+118h+var_E0], xmm0
0x180027777  mov     [rsp+118h+var_D0], r14
0x18002777c  mov     [rsp+118h+var_C8], r14
0x180027781  movzx   r8d, [rsp+118h+UnicodeString.Length]
0x18002778a  shr     r8, 1
0x18002778d  mov     rdx, [rsp+118h+UnicodeString.Buffer]
0x180027795  lea     rcx, [rsp+118h+var_E0]
0x18002779a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002779f  nop
0x1800277a0  lea     rcx, [rsp+118h+UnicodeString]; UnicodeString
0x1800277a8  call    cs:__imp_RtlFreeUnicodeString
0x1800277af  nop     dword ptr [rax+rax+00h]
0x1800277b4  lea     rdx, [rsp+118h+var_E0]
0x1800277b9  mov     rcx, rdi
0x1800277bc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800277c1  lea     rcx, [rsp+118h+var_E0]
0x1800277c6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800277cb  nop
0x1800277cc  lea     rcx, [rsp+118h+Src]
0x1800277d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800277d6  mov     ecx, 5
0x1800277db  mov     [rsp+118h+Src], rcx
0x1800277e0  lea     rax, off_18004AE10; "dll"
0x1800277e7  mov     [rsp+118h+var_A0], rax
0x1800277ec  mov     qword ptr [rsp+118h+UnicodeString.Length], rcx
0x1800277f4  lea     rax, off_18004AE38; "Windows\\System32"
0x1800277fb  mov     [rsp+118h+UnicodeString.Buffer], rax
0x180027803  mov     byte ptr [rsp+118h+var_F8], 1
0x180027808  lea     r9, [rsp+118h+Src]
0x18002780d  lea     r8, [rsp+118h+UnicodeString]
0x180027815  mov     rdx, rbx
0x180027818  lea     rcx, [rsp+118h+var_E0]
0x18002781d  call    ?FindFiles@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBGV?$span@QEBG$0?0@gsl@@1_N@Z; FindFiles(ushort const *,gsl::span<ushort const * const,-1>,gsl::span<ushort const * const,-1>,bool)
0x180027822  mov     rbx, rax
0x180027825  cmp     rsi, rax
0x180027828  jz      short loc_180027853
0x18002782a  mov     rcx, rsi
0x18002782d  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180027832  mov     rcx, [rbx]
0x180027835  mov     [rsi], rcx
0x180027838  mov     rcx, [rbx+8]
0x18002783c  mov     [rsi+8], rcx
0x180027840  mov     rcx, [rbx+10h]
0x180027844  mov     [rsi+10h], rcx
0x180027848  mov     [rbx], r14
0x18002784b  mov     [rbx+8], r14
0x18002784f  mov     [rbx+10h], r14
0x180027853  lea     rcx, [rsp+118h+var_E0]
0x180027858  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18002785d  xorps   xmm0, xmm0
0x180027860  movups  xmmword ptr [rsp+118h+SystemInfo], xmm0
0x180027868  movups  xmmword ptr [rsp+118h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180027870  movups  xmmword ptr [rsp+118h+SystemInfo.dwNumberOfProcessors], xmm0
0x180027878  lea     rcx, [rsp+118h+SystemInfo]; lpSystemInfo
0x180027880  call    cs:__imp_GetSystemInfo
0x180027887  nop     dword ptr [rax+rax+00h]
0x18002788c  mov     esi, [rsp+118h+SystemInfo.dwNumberOfProcessors]
0x180027893  cmp     esi, 4
0x180027896  jnb     short loc_1800278A4
0x180027898  cmp     esi, 1
0x18002789b  ja      short loc_1800278A9
0x18002789d  mov     esi, 1
0x1800278a2  jmp     short loc_1800278A9
0x1800278a4  mov     esi, 4
0x1800278a9  mov     r15d, r14d
0x1800278ac  cmp     r15d, esi
0x1800278af  jnb     loc_1800279E6
0x1800278b5  xorps   xmm0, xmm0
0x1800278b8  xor     eax, eax
0x1800278ba  movups  [rsp+118h+var_E0], xmm0
0x1800278bf  mov     [rsp+118h+var_D0], rax
0x1800278c4  mov     [rsp+118h+var_C0], rdi
0x1800278c9  lea     rax, ?CacheFiles@@YAXPEAUCiCacheState@@@Z; CacheFiles(CiCacheState *)
0x1800278d0  mov     [rsp+118h+var_B8], rax
0x1800278d5  mov     ecx, 120h; Size
0x1800278da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800278df  mov     rbx, rax
0x1800278e2  mov     qword ptr [rsp+118h+UnicodeString.Length], rax
0x1800278ea  xor     edx, edx; Val
0x1800278ec  mov     r8d, 120h; Size
0x1800278f2  mov     rcx, rax; void *
0x1800278f5  call    memset_0
0x1800278fa  lea     rdx, [rsp+118h+var_C0]
0x1800278ff  mov     rcx, rbx
0x180027902  call    ??$?0V?$_Fake_no_copy_callable_adapter@A6AXPEAUCiCacheState@@@ZPEAU1@@std@@@?$_Task_async_state@X@std@@QEAA@$$QEAV?$_Fake_no_copy_callable_adapter@A6AXPEAUCiCacheState@@@ZPEAU1@@1@@Z; std::_Task_async_state<void>::_Task_async_state<void>(std::_Fake_no_copy_callable_adapter<void (&)(CiCacheState *),CiCacheState *> &&)
0x180027907  mov     rbx, rax
0x18002790a  mov     qword ptr [rsp+118h+var_E0], rax
0x18002790f  mov     byte ptr [rsp+118h+var_E0+8], r14b
0x180027914  mov     byte ptr [rsp+118h+var_D0], r14b
0x180027919  test    rax, rax
0x18002791c  jz      loc_180027A3B
0x180027922  mov     [rsp+118h+Src], rax
0x180027927  mov     byte ptr [rsp+118h+var_A0], 1
0x18002792c  lock inc dword ptr [rax+8]
0x180027930  or      eax, 0FFFFFFFFh
0x180027933  lock xadd [rbx+8], eax
0x180027938  cmp     eax, 1
0x18002793b  jnz     short loc_18002796D
0x18002793d  mov     rcx, [rbx+0C8h]
0x180027944  test    rcx, rcx
0x180027947  jz      short loc_180027959
0x180027949  mov     rax, [rcx]
0x18002794c  mov     rdx, rbx
0x18002794f  mov     rax, [rax]
0x180027952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027957  jmp     short loc_18002796D
0x180027959  mov     rax, [rbx]
0x18002795c  mov     edx, 1
0x180027961  mov     rcx, rbx
0x180027964  mov     rax, [rax]
0x180027967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002796c  nop
0x18002796d  mov     rdx, [rdi+28h]
0x180027971  cmp     rdx, [rdi+30h]
0x180027975  jz      short loc_180027987
0x180027977  xor     ecx, ecx
0x180027979  mov     [rdx], rbx
0x18002797c  mov     byte ptr [rdx+8], 1
0x180027980  add     qword ptr [rdi+28h], 10h
0x180027985  jmp     short loc_18002799A
0x180027987  lea     r8, [rsp+118h+Src]
0x18002798c  lea     rcx, [rdi+20h]
0x180027990  call    ??$_Emplace_reallocate@V?$future@X@std@@@?$vector@V?$future@X@std@@V?$allocator@V?$future@X@std@@@2@@std@@AEAAPEAV?$future@X@1@QEAV21@$$QEAV21@@Z; std::vector<std::future<void>>::_Emplace_reallocate<std::future<void>>(std::future<void> * const,std::future<void> &&)
0x180027995  mov     rcx, [rsp+118h+Src]
0x18002799a  xor     r14d, r14d
0x18002799d  test    rcx, rcx
0x1800279a0  jz      short loc_1800279DE
0x1800279a2  or      eax, 0FFFFFFFFh
0x1800279a5  lock xadd [rcx+8], eax
0x1800279aa  cmp     eax, 1
0x1800279ad  jnz     short loc_1800279DE
0x1800279af  mov     r8, [rcx+0C8h]
0x1800279b6  test    r8, r8
0x1800279b9  jz      short loc_1800279CE
0x1800279bb  mov     rax, [r8]
0x1800279be  mov     rdx, rcx
0x1800279c1  mov     rcx, r8
0x1800279c4  mov     rax, [rax]
0x1800279c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279cc  jmp     short loc_1800279DE
0x1800279ce  mov     rax, [rcx]
0x1800279d1  mov     edx, 1
0x1800279d6  mov     rax, [rax]
0x1800279d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279de  inc     r15d
0x1800279e1  jmp     loc_1800278AC
0x1800279e6  mov     rax, [rdi+40h]
0x1800279ea  sub     rax, [rdi+38h]
0x1800279ee  sar     rax, 5
0x1800279f2  mov     [r13+0], eax
0x1800279f6  mov     [r12], rdi
0x1800279fa  xor     eax, eax
0x1800279fc  jmp     short loc_180027A02
0x1800279fe  mov     eax, dword ptr [rsp+118h+var_E8]
0x180027a02  mov     rcx, [rsp+118h+var_48]
0x180027a0a  xor     rcx, rsp; StackCookie
0x180027a0d  call    __security_check_cookie
0x180027a12  add     rsp, 0E0h
0x180027a19  pop     r15
0x180027a1b  pop     r14
0x180027a1d  pop     r13
0x180027a1f  pop     r12
0x180027a21  pop     rdi
0x180027a22  pop     rsi
0x180027a23  pop     rbx
0x180027a24  retn
0x180027a26  mov     r9d, eax; char *
0x180027a29  lea     r8, aOnecoreVmCommo; "onecore\\vm\\common\\vml\\VmPath.h"
0x180027a30  mov     edx, 29Eh; void *
0x180027a35  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180027a3b  mov     ecx, 4
0x180027a40  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
```
