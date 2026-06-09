# TimerResolutionTroubleshooter::LocalTelemetryAnalysis(_GUID)

- ea: `0x18003a950`
- end: `0x18003ae71`
- name: `?LocalTelemetryAnalysis@TimerResolutionTroubleshooter@@MEAAXU_GUID@@@Z`
- size: `1313`
- prototype: `void __fastcall(TimerResolutionTroubleshooter *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting`

## callees

- `0x1800021e8`
- `0x180002f50`
- `0x1800097cc`
- `0x18000b6f0`
- `0x18001c8cc`
- `0x18001e218`
- `0x18001f0c8`
- `0x180020454`
- `0x1800253e0`
- `0x18003020c`
- `0x180033c4c`
- `0x18003a950`
- `0x18003bce0`
- `0x18004507c`
- `0x18004ca90`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003a9b1`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003a9d3`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003a9b1`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003a9d3`
- `msvcp_win!_Mtx_unlock` at `0x18003aa08`
- `msvcp_win!_Mtx_unlock` at `0x18003aa08`
- `msvcp_win!_Mtx_lock` at `0x18003a9a2`
- `msvcp_win!_Mtx_lock` at `0x18003a9a2`

## string_xrefs

- `0x18003abc8`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TimerResolutionTroubleshooter::LocalTelemetryAnalysis(
        TimerResolutionTroubleshooter *this,
        struct _GUID *a2)
{
  int v4; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 i; // rbx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  const unsigned __int16 *v11; // rax
  unsigned int v12; // r13d
  int *j; // rdi
  char v14; // r14
  unsigned int *k; // rbx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  unsigned int v19; // ecx
  unsigned int *m; // rax
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  unsigned int v27; // r15d
  unsigned int n; // r14d
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  const unsigned __int16 *v35; // rax
  const unsigned __int16 *v36; // rax
  const unsigned __int16 *v37; // rax
  const unsigned __int16 *v38; // rax
  const unsigned __int16 *v39; // rax
  unsigned int v40; // [rsp+60h] [rbp-A0h] BYREF
  int v41; // [rsp+64h] [rbp-9Ch] BYREF
  struct _GUID *v42; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v43; // [rsp+70h] [rbp-90h] BYREF
  char v44[8]; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 *v45; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v46; // [rsp+88h] [rbp-78h] BYREF
  const unsigned __int16 *v47; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v48[3]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v49; // [rsp+B0h] [rbp-50h]
  _QWORD v50[4]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v51[3]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v52; // [rsp+F0h] [rbp-10h]
  _BYTE v53[32]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v54[32]; // [rsp+118h] [rbp+18h] BYREF

  std::wstring::wstring(v48);
  std::wstring::wstring(v51);
  std::wstring::wstring(v50);
  if ( _Mtx_lock((_Mtx_t)`ProviderRegistrationGuard<&_tlgProvider_t const * const TimerResolutionLoggingProvider>::GetProviderContext'::`2'::Context) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( dword_1800C84FC == 0x7FFFFFFF )
  {
    dword_1800C84FC = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  v4 = dword_1800C8500;
  if ( !dword_1800C8500 )
  {
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1800C6368);
    v4 = dword_1800C8500;
  }
  dword_1800C8500 = v4 + 1;
  _Mtx_unlock((_Mtx_t)`ProviderRegistrationGuard<&_tlgProvider_t const * const TimerResolutionLoggingProvider>::GetProviderContext'::`2'::Context);
  if ( (unsigned int)dword_1800C6368 > 5 )
  {
    v41 = *((_DWORD *)this + 8);
    LODWORD(v42) = *((_DWORD *)this + 9);
    v40 = *((_DWORD *)this + 7);
    v43 = (const unsigned __int16 *)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&dword_1800C6368,
      (__int64)byte_1800B61E3,
      v5,
      v6,
      (__int64 *)&v43,
      (__int64)&v40,
      (__int64)&v42,
      (__int64)&v41);
  }
  for ( i = *((_QWORD *)this + 6); i != *((_QWORD *)this + 7); i += 88 )
  {
    v8 = std::wstring::wstring((__int64)v53, (_QWORD *)(i + 8));
    v10 = Troubleshooter::SanitizeFilePathForSqm(v9, v54, v8);
    std::wstring::operator=(v48, v10);
    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v54);
    if ( (unsigned int)dword_1800C6368 > 5 )
    {
      v11 = (const unsigned __int16 *)v48;
      if ( v49 > 7 )
        v11 = (const unsigned __int16 *)v48[0];
      v43 = v11;
      v40 = *(_DWORD *)i;
      v42 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        (__int64)&dword_1800C6368,
        (__int64)&dword_1800B619C,
        v5,
        v6,
        (__int64 *)&v42,
        (__int64)&v40,
        &v43);
    }
  }
  if ( *((_DWORD *)this + 10) && (unsigned int)dword_1800C6368 > 5 )
  {
    v43 = L"System";
    v40 = *((_DWORD *)this + 11);
    v42 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (__int64)&dword_1800C6368,
      (__int64)byte_1800B62B5,
      v5,
      v6,
      (__int64 *)&v42,
      (__int64)&v40,
      &v43);
  }
  v12 = 75;
  for ( j = (int *)*((_QWORD *)this + 9); j != *((int **)this + 10); j += 22 )
  {
    v14 = 0;
    for ( k = (unsigned int *)*((_QWORD *)j + 8); k != *((unsigned int **)j + 9); k += 2 )
    {
      if ( *k == -1 )
      {
        std::wstring::assign(v50, &qword_18009CA18);
      }
      else
      {
        v16 = std::wstring::wstring((__int64)v54, (_QWORD *)(*((_QWORD *)this + 14) + 32LL * *k));
        v18 = Troubleshooter::SanitizeFilePathForSqm(v17, v53, v16);
        std::wstring::operator=(v50, v18);
        std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v53);
      }
      if ( std::wstring::find(v50, L"ntdll.dll") )
      {
        if ( v14 )
          break;
      }
      else
      {
        v14 = 1;
      }
    }
    v19 = 1;
    for ( m = k; m != *((unsigned int **)j + 9) && *k != -1; m += 2 )
      ++v19;
    if ( v19 > 0x10 )
      v19 = 16;
    if ( v12 >= v19 )
    {
      v12 -= v19;
      v21 = std::wstring::wstring((__int64)v54, (_QWORD *)j + 1);
      v23 = Troubleshooter::SanitizeFilePathForSqm(v22, v53, v21);
      std::wstring::operator=(v48, v23);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v53);
      std::wstring::assign(v51, L"NtSetTimerResolution()");
      v27 = 0;
      for ( n = 0; k != *((unsigned int **)j + 9) && *k != -1 && n <= 0xF; ++n )
      {
        v29 = std::wstring::wstring((__int64)v54, (_QWORD *)(*((_QWORD *)this + 14) + 32LL * *k));
        v31 = Troubleshooter::SanitizeFilePathForSqm(v30, v53, v29);
        std::wstring::operator=(v50, v31);
        std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v53);
        if ( (unsigned int)dword_1800C6368 > 5 )
        {
          v40 = v27;
          v35 = (const unsigned __int16 *)v51;
          if ( v52 > 7 )
            v35 = (const unsigned __int16 *)v51[0];
          v43 = v35;
          LODWORD(v42) = k[1];
          v36 = (const unsigned __int16 *)v50;
          if ( v50[3] > 7u )
            v36 = (const unsigned __int16 *)v50[0];
          v46 = v36;
          v37 = (const unsigned __int16 *)v48;
          if ( v49 > 7 )
            v37 = (const unsigned __int16 *)v48[0];
          v47 = v37;
          v41 = *j;
          v45 = (const unsigned __int16 *)a2;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v32,
            (__int64)qword_1800B6238,
            v33,
            v34,
            (__int64 *)&v45,
            (__int64)&v41,
            &v47,
            &v46,
            (__int64)&v42,
            &v43,
            (__int64)&v40);
        }
        std::wstring::operator=(v51, v50);
        v27 = k[1];
        k += 2;
      }
      if ( (unsigned int)dword_1800C6368 > 5 )
      {
        v40 = v27;
        v38 = (const unsigned __int16 *)v51;
        if ( v52 > 7 )
          v38 = (const unsigned __int16 *)v51[0];
        v45 = v38;
        LODWORD(v42) = 0;
        v47 = L"StackBase";
        v39 = (const unsigned __int16 *)v48;
        if ( v49 > 7 )
          v39 = (const unsigned __int16 *)v48[0];
        v46 = v39;
        v41 = *j;
        v43 = (const unsigned __int16 *)a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v24,
          (__int64)&dword_1800B62FC,
          v25,
          v26,
          (__int64 *)&v43,
          (__int64)&v41,
          &v46,
          &v47,
          (__int64)&v42,
          &v45,
          (__int64)&v40);
      }
    }
  }
  ProviderRegistrationGuard<&_tlgProvider_t const * const TimerResolutionLoggingProvider>::~ProviderRegistrationGuard<&_tlgProvider_t const * const TimerResolutionLoggingProvider>(v44);
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v50);
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v51);
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v48);
}

```

## disassembly

```asm
0x18003a950  push    rbp
0x18003a952  push    rbx
0x18003a953  push    rsi
0x18003a954  push    rdi
0x18003a955  push    r12
0x18003a957  push    r13
0x18003a959  push    r14
0x18003a95b  push    r15
0x18003a95d  lea     rbp, [rsp-48h]
0x18003a962  sub     rsp, 148h
0x18003a969  mov     rax, cs:__security_cookie
0x18003a970  xor     rax, rsp
0x18003a973  mov     [rbp+80h+var_48], rax
0x18003a977  mov     r12, rdx
0x18003a97a  mov     rsi, rcx
0x18003a97d  lea     rcx, [rbp+80h+var_E8]; void *
0x18003a981  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003a986  nop
0x18003a987  lea     rcx, [rbp+80h+var_A8]; void *
0x18003a98b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003a990  nop
0x18003a991  lea     rcx, [rbp+80h+var_C8]; void *
0x18003a995  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003a99a  nop
0x18003a99b  lea     rcx, ?Context@?1??GetProviderContext@?$ProviderRegistrationGuard@$1?TimerResolutionLoggingProvider@@3QEBU_tlgProvider_t@@EB@@CAAEAU?$ProviderContext@$1?TimerResolutionLoggingProvider@@3QEBU_tlgProvider_t@@EB@2@XZ@4U32@A; _Mtx_t
0x18003a9a2  call    cs:__imp__Mtx_lock
0x18003a9a8  test    eax, eax
0x18003a9aa  jz      short loc_18003A9B8
0x18003a9ac  mov     ecx, 5
0x18003a9b1  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003a9b7  int     3; Trap to Debugger
0x18003a9b8  cmp     cs:dword_1800C84FC, 7FFFFFFFh
0x18003a9c2  jnz     short loc_18003A9DA
0x18003a9c4  mov     cs:dword_1800C84FC, 7FFFFFFEh
0x18003a9ce  mov     ecx, 6
0x18003a9d3  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003a9d9  int     3; Trap to Debugger
0x18003a9da  lea     rdi, dword_1800C6368
0x18003a9e1  mov     eax, cs:dword_1800C8500
0x18003a9e7  test    eax, eax
0x18003a9e9  jnz     short loc_18003A9F9
0x18003a9eb  mov     rcx, rdi; CallbackContext
0x18003a9ee  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18003a9f3  mov     eax, cs:dword_1800C8500
0x18003a9f9  inc     eax
0x18003a9fb  mov     cs:dword_1800C8500, eax
0x18003aa01  lea     rcx, ?Context@?1??GetProviderContext@?$ProviderRegistrationGuard@$1?TimerResolutionLoggingProvider@@3QEBU_tlgProvider_t@@EB@@CAAEAU?$ProviderContext@$1?TimerResolutionLoggingProvider@@3QEBU_tlgProvider_t@@EB@2@XZ@4U32@A; _Mtx_t
0x18003aa08  call    cs:__imp__Mtx_unlock
0x18003aa0e  nop
0x18003aa0f  mov     eax, cs:dword_1800C6368
0x18003aa15  cmp     eax, 5
0x18003aa18  jbe     short loc_18003AA6B
0x18003aa1a  mov     eax, [rsi+20h]
0x18003aa1d  mov     [rsp+180h+var_11C], eax
0x18003aa21  mov     eax, [rsi+24h]
0x18003aa24  mov     dword ptr [rsp+180h+var_118], eax
0x18003aa28  mov     eax, [rsi+1Ch]
0x18003aa2b  mov     [rsp+180h+var_120], eax
0x18003aa2f  mov     [rsp+180h+var_110], r12
0x18003aa34  lea     rax, [rsp+180h+var_11C]
0x18003aa39  mov     [rsp+180h+var_148], rax
0x18003aa3e  lea     rax, [rsp+180h+var_118]
0x18003aa43  mov     [rsp+180h+var_150], rax
0x18003aa48  lea     rax, [rsp+180h+var_120]
0x18003aa4d  mov     [rsp+180h+var_158], rax
0x18003aa52  lea     rax, [rsp+180h+var_110]
0x18003aa57  mov     [rsp+180h+var_160], rax
0x18003aa5c  lea     rdx, byte_1800B61E3
0x18003aa63  mov     rcx, rdi
0x18003aa66  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003aa6b  mov     rbx, [rsi+30h]
0x18003aa6f  cmp     rbx, [rsi+38h]
0x18003aa73  jz      loc_18003AB06
0x18003aa79  lea     rdx, [rbx+8]
0x18003aa7d  lea     rcx, [rbp+80h+var_88]
0x18003aa81  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003aa86  mov     r8, rax
0x18003aa89  lea     rdx, [rbp+80h+var_68]
0x18003aa8d  call    ?SanitizeFilePathForSqm@Troubleshooter@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; Troubleshooter::SanitizeFilePathForSqm(std::wstring)
0x18003aa92  mov     rdx, rax
0x18003aa95  lea     rcx, [rbp+80h+var_E8]
0x18003aa99  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003aa9e  lea     rcx, [rbp+80h+var_68]; void *
0x18003aaa2  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x18003aaa7  mov     eax, cs:dword_1800C6368
0x18003aaad  cmp     eax, 5
0x18003aab0  jbe     short loc_18003AAFD
0x18003aab2  lea     rax, [rbp+80h+var_E8]
0x18003aab6  cmp     [rbp+80h+var_D0], 7
0x18003aabb  cmova   rax, [rbp+80h+var_E8]
0x18003aac0  mov     [rsp+180h+var_110], rax
0x18003aac5  mov     eax, [rbx]
0x18003aac7  mov     [rsp+180h+var_120], eax
0x18003aacb  mov     [rsp+180h+var_118], r12
0x18003aad0  lea     rax, [rsp+180h+var_110]
0x18003aad5  mov     [rsp+180h+var_150], rax
0x18003aada  lea     rax, [rsp+180h+var_120]
0x18003aadf  mov     [rsp+180h+var_158], rax
0x18003aae4  lea     rax, [rsp+180h+var_118]
0x18003aae9  mov     [rsp+180h+var_160], rax
0x18003aaee  lea     rdx, dword_1800B619C
0x18003aaf5  mov     rcx, rdi
0x18003aaf8  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18003aafd  add     rbx, 58h ; 'X'
0x18003ab01  jmp     loc_18003AA6F
0x18003ab06  cmp     dword ptr [rsi+28h], 0
0x18003ab0a  jbe     short loc_18003AB5C
0x18003ab0c  mov     eax, cs:dword_1800C6368
0x18003ab12  cmp     eax, 5
0x18003ab15  jbe     short loc_18003AB5C
0x18003ab17  lea     rax, aSystem; "System"
0x18003ab1e  mov     [rsp+180h+var_110], rax
0x18003ab23  mov     eax, [rsi+2Ch]
0x18003ab26  mov     [rsp+180h+var_120], eax
0x18003ab2a  mov     [rsp+180h+var_118], r12
0x18003ab2f  lea     rax, [rsp+180h+var_110]
0x18003ab34  mov     [rsp+180h+var_150], rax
0x18003ab39  lea     rax, [rsp+180h+var_120]
0x18003ab3e  mov     [rsp+180h+var_158], rax
0x18003ab43  lea     rax, [rsp+180h+var_118]
0x18003ab48  mov     [rsp+180h+var_160], rax
0x18003ab4d  lea     rdx, byte_1800B62B5
0x18003ab54  mov     rcx, rdi
0x18003ab57  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18003ab5c  mov     r13d, 4Bh ; 'K'
0x18003ab62  mov     rdi, [rsi+48h]
0x18003ab66  cmp     rdi, [rsi+50h]
0x18003ab6a  jz      loc_18003AE29
0x18003ab70  xor     r14b, r14b
0x18003ab73  mov     rbx, [rdi+40h]
0x18003ab77  cmp     rbx, [rdi+48h]
0x18003ab7b  jz      short loc_18003ABED
0x18003ab7d  cmp     dword ptr [rbx], 0FFFFFFFFh
0x18003ab80  jz      short loc_18003ABB8
0x18003ab82  mov     edx, [rbx]
0x18003ab84  shl     rdx, 5
0x18003ab88  add     rdx, [rsi+70h]
0x18003ab8c  lea     rcx, [rbp+80h+var_68]
0x18003ab90  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003ab95  mov     r8, rax
0x18003ab98  lea     rdx, [rbp+80h+var_88]
0x18003ab9c  call    ?SanitizeFilePathForSqm@Troubleshooter@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; Troubleshooter::SanitizeFilePathForSqm(std::wstring)
0x18003aba1  mov     rdx, rax
0x18003aba4  lea     rcx, [rbp+80h+var_C8]
0x18003aba8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003abad  lea     rcx, [rbp+80h+var_88]; void *
0x18003abb1  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x18003abb6  jmp     short loc_18003ABC8
0x18003abb8  lea     rdx, qword_18009CA18
0x18003abbf  lea     rcx, [rbp+80h+var_C8]
0x18003abc3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18003abc8  lea     rdx, aNtdllDll_1; "ntdll.dll"
0x18003abcf  lea     rcx, [rbp+80h+var_C8]
0x18003abd3  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x18003abd8  test    rax, rax
0x18003abdb  jnz     short loc_18003ABE2
0x18003abdd  mov     r14b, 1
0x18003abe0  jmp     short loc_18003ABE7
0x18003abe2  test    r14b, r14b
0x18003abe5  jnz     short loc_18003ABED
0x18003abe7  add     rbx, 8
0x18003abeb  jmp     short loc_18003AB77
0x18003abed  mov     ecx, 1
0x18003abf2  mov     rax, rbx
0x18003abf5  cmp     rax, [rdi+48h]
0x18003abf9  jz      short loc_18003AC08
0x18003abfb  cmp     dword ptr [rbx], 0FFFFFFFFh
0x18003abfe  jz      short loc_18003AC08
0x18003ac00  add     rax, 8
0x18003ac04  inc     ecx
0x18003ac06  jmp     short loc_18003ABF5
0x18003ac08  mov     edx, 10h
0x18003ac0d  cmp     ecx, edx
0x18003ac0f  cmova   ecx, edx
0x18003ac12  cmp     r13d, ecx
0x18003ac15  jb      loc_18003AE20
0x18003ac1b  sub     r13d, ecx
0x18003ac1e  lea     rdx, [rdi+8]
0x18003ac22  lea     rcx, [rbp+80h+var_68]
0x18003ac26  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003ac2b  mov     r8, rax
0x18003ac2e  lea     rdx, [rbp+80h+var_88]
0x18003ac32  call    ?SanitizeFilePathForSqm@Troubleshooter@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; Troubleshooter::SanitizeFilePathForSqm(std::wstring)
0x18003ac37  mov     rdx, rax
0x18003ac3a  lea     rcx, [rbp+80h+var_E8]
0x18003ac3e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003ac43  lea     rcx, [rbp+80h+var_88]; void *
0x18003ac47  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x18003ac4c  lea     rdx, aNtsettimerreso; "NtSetTimerResolution()"
0x18003ac53  lea     rcx, [rbp+80h+var_A8]
0x18003ac57  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18003ac5c  xor     r15d, r15d
0x18003ac5f  xor     r14d, r14d
0x18003ac62  cmp     rbx, [rdi+48h]
0x18003ac66  jz      loc_18003AD7B
0x18003ac6c  cmp     dword ptr [rbx], 0FFFFFFFFh
0x18003ac6f  jz      loc_18003AD7B
0x18003ac75  cmp     r14d, 0Fh
0x18003ac79  ja      loc_18003AD7B
0x18003ac7f  mov     edx, [rbx]
0x18003ac81  shl     rdx, 5
0x18003ac85  add     rdx, [rsi+70h]
0x18003ac89  lea     rcx, [rbp+80h+var_68]
0x18003ac8d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003ac92  mov     r8, rax
0x18003ac95  lea     rdx, [rbp+80h+var_88]
0x18003ac99  call    ?SanitizeFilePathForSqm@Troubleshooter@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; Troubleshooter::SanitizeFilePathForSqm(std::wstring)
0x18003ac9e  mov     rdx, rax
0x18003aca1  lea     rcx, [rbp+80h+var_C8]
0x18003aca5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003acaa  lea     rcx, [rbp+80h+var_88]; void *
0x18003acae  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x18003acb3  mov     eax, cs:dword_1800C6368
0x18003acb9  cmp     eax, 5
0x18003acbc  jbe     loc_18003AD5E
0x18003acc2  mov     [rsp+180h+var_120], r15d
0x18003acc7  lea     rax, [rbp+80h+var_A8]
0x18003accb  cmp     [rbp+80h+var_90], 7
0x18003acd0  cmova   rax, [rbp+80h+var_A8]
0x18003acd5  mov     [rsp+180h+var_110], rax
0x18003acda  mov     eax, [rbx+4]
0x18003acdd  mov     dword ptr [rsp+180h+var_118], eax
0x18003ace1  lea     rax, [rbp+80h+var_C8]
0x18003ace5  cmp     [rbp+80h+var_B0], 7
0x18003acea  cmova   rax, [rbp+80h+var_C8]
0x18003acef  mov     [rbp+80h+var_F8], rax
0x18003acf3  lea     rax, [rbp+80h+var_E8]
0x18003acf7  cmp     [rbp+80h+var_D0], 7
0x18003acfc  cmova   rax, [rbp+80h+var_E8]
0x18003ad01  mov     [rbp+80h+var_F0], rax
0x18003ad05  mov     eax, [rdi]
0x18003ad07  mov     [rsp+180h+var_11C], eax
0x18003ad0b  mov     [rbp+80h+var_100], r12
0x18003ad0f  lea     rax, [rsp+180h+var_120]
0x18003ad14  mov     [rsp+180h+var_130], rax
0x18003ad19  lea     rax, [rsp+180h+var_110]
0x18003ad1e  mov     [rsp+180h+var_138], rax
0x18003ad23  lea     rax, [rsp+180h+var_118]
0x18003ad28  mov     [rsp+180h+var_140], rax
0x18003ad2d  lea     rax, [rbp+80h+var_F8]
0x18003ad31  mov     [rsp+180h+var_148], rax
0x18003ad36  lea     rax, [rbp+80h+var_F0]
0x18003ad3a  mov     [rsp+180h+var_150], rax
0x18003ad3f  lea     rax, [rsp+180h+var_11C]
0x18003ad44  mov     [rsp+180h+var_158], rax
0x18003ad49  lea     rax, [rbp+80h+var_100]
0x18003ad4d  mov     [rsp+180h+var_160], rax
0x18003ad52  lea     rdx, qword_1800B6238
0x18003ad59  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U2@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5454@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18003ad5e  lea     rdx, [rbp+80h+var_C8]
0x18003ad62  lea     rcx, [rbp+80h+var_A8]
0x18003ad66  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003ad6b  mov     r15d, [rbx+4]
0x18003ad6f  inc     r14d
0x18003ad72  add     rbx, 8
0x18003ad76  jmp     loc_18003AC62
0x18003ad7b  mov     eax, cs:dword_1800C6368
0x18003ad81  cmp     eax, 5
0x18003ad84  jbe     loc_18003AE20
0x18003ad8a  mov     [rsp+180h+var_120], r15d
0x18003ad8f  lea     rax, [rbp+80h+var_A8]
0x18003ad93  cmp     [rbp+80h+var_90], 7
0x18003ad98  cmova   rax, [rbp+80h+var_A8]
0x18003ad9d  mov     [rbp+80h+var_100], rax
0x18003ada1  mov     dword ptr [rsp+180h+var_118], 0
0x18003ada9  lea     rax, aStackbase; "StackBase"
0x18003adb0  mov     [rbp+80h+var_F0], rax
0x18003adb4  lea     rax, [rbp+80h+var_E8]
0x18003adb8  cmp     [rbp+80h+var_D0], 7
0x18003adbd  cmova   rax, [rbp+80h+var_E8]
0x18003adc2  mov     [rbp+80h+var_F8], rax
0x18003adc6  mov     eax, [rdi]
0x18003adc8  mov     [rsp+180h+var_11C], eax
0x18003adcc  mov     [rsp+180h+var_110], r12
0x18003add1  lea     rax, [rsp+180h+var_120]
0x18003add6  mov     [rsp+180h+var_130], rax
0x18003addb  lea     rax, [rbp+80h+var_100]
0x18003addf  mov     [rsp+180h+var_138], rax
0x18003ade4  lea     rax, [rsp+180h+var_118]
0x18003ade9  mov     [rsp+180h+var_140], rax
0x18003adee  lea     rax, [rbp+80h+var_F0]
0x18003adf2  mov     [rsp+180h+var_148], rax
0x18003adf7  lea     rax, [rbp+80h+var_F8]
0x18003adfb  mov     [rsp+180h+var_150], rax
0x18003ae00  lea     rax, [rsp+180h+var_11C]
0x18003ae05  mov     [rsp+180h+var_158], rax
0x18003ae0a  lea     rax, [rsp+180h+var_110]
0x18003ae0f  mov     [rsp+180h+var_160], rax
0x18003ae14  lea     rdx, dword_1800B62FC
0x18003ae1b  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U2@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5454@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18003ae20  add     rdi, 58h ; 'X'
0x18003ae24  jmp     loc_18003AB66
0x18003ae29  lea     rcx, [rsp+180h+var_108]
0x18003ae2e  call    ??1?$ProviderRegistrationGuard@$1?TimerResolutionLoggingProvider@@3QEBU_tlgProvider_t@@EB@@QEAA@XZ; ProviderRegistrationGuard<&_tlgProvider_t const * const TimerResolutionLoggingProvider>::~ProviderRegistrationGuard<&_tlgProvider_t const * const TimerResolutionLoggingProvider>(void)
0x18003ae33  nop
0x18003ae34  lea     rcx, [rbp+80h+var_C8]; void *
0x18003ae38  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x18003ae3d  nop
0x18003ae3e  lea     rcx, [rbp+80h+var_A8]; void *
0x18003ae42  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
  ... truncated ...
```
