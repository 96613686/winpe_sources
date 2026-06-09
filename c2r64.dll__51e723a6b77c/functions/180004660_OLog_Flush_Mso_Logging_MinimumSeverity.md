# OLog::Flush(Mso::Logging::MinimumSeverity)

- ea: `0x180004660`
- end: `0x180004b29`
- name: `?Flush@OLog@@QEAAXW4MinimumSeverity@Logging@Mso@@@Z`
- size: `1225`
- prototype: ``
- caller_count: `3`
- callee_count: `26`
- tags: `broker_com_uri`

## callers

- `0x1800038d0`
- `0x18000b300`
- `0x18002dc5c`

## callees

- `0x180001b54`
- `0x1800039ac`
- `0x180004660`
- `0x180004b2c`
- `0x180004b6c`
- `0x180007d88`
- `0x180009748`
- `0x180009d68`
- `0x18000adf0`
- `0x18000ae28`
- `0x18000b300`
- `0x18000b6e0`
- `0x18000c0a4`
- `0x18000c2dc`
- `0x180010730`
- `0x18001c344`
- `0x18001ca50`
- `0x18001d3a4`
- `0x1800201ec`
- `0x18002074c`
- `0x180036024`
- `0x1800381f8`
- `0x18003e690`
- `0x1800fc6f4`
- `0x180132804`
- `0x180133920`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800046af`
- `KERNEL32!GetCurrentThreadId` at `0x1800046cc`
- `KERNEL32!GetCurrentThreadId` at `0x1800046af`
- `KERNEL32!GetCurrentThreadId` at `0x1800046cc`
- `KERNEL32!EnterCriticalSection` at `0x1800046c0`
- `KERNEL32!EnterCriticalSection` at `0x1800046c0`

## string_xrefs

- `0x180004aeb`: `==========A logging failure has occured. The process has encountered an error when writing to the log file. The messages in the log file may not be complete.`
- `0x1800048f3`: `Log path %s is not valid.  Reverting to default log path`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall OLog::Flush(__int64 a1, unsigned __int8 a2)
{
  unsigned int v2; // r12d
  __int64 v3; // rdi
  __int64 v4; // r14
  char v5; // r13
  __int64 v6; // r15
  const wchar_t **v7; // rsi
  const wchar_t *v8; // rdx
  size_t v9; // r8
  const wchar_t *v10; // rcx
  const wchar_t *v12; // rax
  __int64 v13; // rax
  _BYTE *v14; // rsi
  _BYTE *v15; // rax
  _BYTE v18[8]; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v19; // [rsp+48h] [rbp-D0h]
  __int64 v20; // [rsp+50h] [rbp-C8h]
  __int64 v21; // [rsp+58h] [rbp-C0h]
  OFile *v22; // [rsp+60h] [rbp-B8h]
  _RTL_CRITICAL_SECTION *v23; // [rsp+68h] [rbp-B0h] BYREF
  char v24; // [rsp+70h] [rbp-A8h]
  char v25[8]; // [rsp+78h] [rbp-A0h] BYREF
  __int128 v26; // [rsp+80h] [rbp-98h] BYREF
  __int64 v27; // [rsp+90h] [rbp-88h]
  __int64 v28; // [rsp+98h] [rbp-80h]
  __int128 Src; // [rsp+A0h] [rbp-78h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-68h]
  wchar_t *S1[2]; // [rsp+C0h] [rbp-58h] BYREF
  size_t N; // [rsp+D0h] [rbp-48h]
  unsigned __int64 v33; // [rsp+D8h] [rbp-40h]

  v2 = a2;
  v3 = a1;
  v20 = a1;
  v23 = &CriticalSection;
  v24 = 0;
  if ( dword_18021C0B4 != GetCurrentThreadId() )
  {
    EnterCriticalSection(&CriticalSection);
    ++dword_18021C0B0;
    dword_18021C0B4 = GetCurrentThreadId();
    v24 = 1;
  }
  v4 = v3 + 40;
  v21 = v3 + 40;
  if ( *(_QWORD *)(v3 + 48) != *(_QWORD *)(v3 + 40) )
  {
    if ( *(_BYTE *)(v3 + 1) > (unsigned __int8)v2 )
    {
      std::vector<OLog::OLogLine>::clear(v3 + 40);
      *(_BYTE *)(v3 + 1) = 0;
      return AcquireExclusive<OLock>::~AcquireExclusive<OLock>(&v23);
    }
    v5 = 0;
    v6 = v3 + 64;
    v19 = v3 + 64;
    v22 = (OFile *)(v3 + 64);
    if ( *(_QWORD *)(v3 + 112) == -1 )
    {
      v7 = (const wchar_t **)(v3 + 8);
      if ( *(_QWORD *)(v3 + 24) )
      {
        *(_OWORD *)S1 = 0;
        N = 0;
        v33 = 7;
        LOWORD(S1[0]) = 0;
        OPath::GetDirectoryName(v3 + 8, S1);
        v8 = (const wchar_t *)(v3 + 8);
        if ( *(_QWORD *)(v3 + 32) > 7u )
          v8 = *v7;
        v9 = N;
        v10 = (const wchar_t *)S1;
        if ( v33 > 7 )
          v10 = S1[0];
        if ( (N != *(_QWORD *)(v3 + 24) || N && wmemcmp(v10, v8, N))
          && !(unsigned __int8)ODirectory::Exists(S1, v8, v9)
          && !(unsigned __int8)ODirectory::CreateDirectoryW(S1, 0) )
        {
          if ( !*(_BYTE *)(v3 + 129) )
          {
            _mm_lfence();
            Src = 0;
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            LOWORD(Src) = 0;
            OString::Format<std::wstring>(v25, L"Log path %s is not valid.  Reverting to default log path", v3 + 8);
            std::wstring::operator=(&Src);
            std::wstring::~wstring(v25);
            OLog::AddLine(v3, v2, (__int64)&Src);
            std::wstring::~wstring(&Src);
          }
          *(_QWORD *)(v3 + 24) = 0;
          v12 = (const wchar_t *)(v3 + 8);
          if ( *(_QWORD *)(v3 + 32) > 7u )
            v12 = *v7;
          *v12 = 0;
        }
        std::wstring::_Tidy_deallocate(S1);
      }
      if ( !*(_QWORD *)(v3 + 24) )
      {
        OPath::GetTempPathW(v3 + 8);
        v13 = std::wstring::wstring(v25, L"Office(*).log");
        OPath::Combine(v3 + 8, v13, v3 + 8);
        std::wstring::~wstring(v25);
      }
      OLog::EnsureUniqueFileName((OLog *)v3);
      if ( (unsigned __int8)OFile::Exists((LPCWSTR)(v3 + 8)) )
      {
        OFile::Open(v3 + 64, v3 + 8, 0, 3, 1, 0);
        v26 = 0;
        v27 = 0;
        v28 = 7;
        LOWORD(v26) = 0;
        v25[0] = 50;
        std::vector<OLog::OLogLine>::emplace<OLog::OLogLine const &>(v3 + 40, v18, *(_QWORD *)(v3 + 40), v25);
        std::wstring::~wstring(&v26);
      }
      else
      {
        try
        {
          Src = 0;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(Src) = 0;
          OFile::Open(v3 + 64, v3 + 8, 1, 3, 1, 0);
        }
        catch ( OException )
        {
          v5 = 1;
          v3 = v20;
          LOBYTE(v2) = a2;
          v4 = v21;
          v6 = v19;
        }
        std::wstring::_Tidy_deallocate(&Src);
        if ( v5 )
        {
LABEL_19:
          std::vector<OLog::OLogLine>::clear(v4);
          *(_BYTE *)(v3 + 1) = 0;
          if ( v5 )
          {
            v26 = 0;
            v27 = 0;
            v28 = 7;
            LOWORD(v26) = 0;
            v25[0] = v2;
            std::wstring::assign(
              &v26,
              L"==========A logging failure has occured. The process has encountered an error when writing to the log file"
               ". The messages in the log file may not be complete.");
            std::vector<OLog::OLogLine>::emplace<OLog::OLogLine const &>(v4, v18, *(_QWORD *)(v3 + 40), v25);
            std::wstring::~wstring(&v26);
          }
          return AcquireExclusive<OLock>::~AcquireExclusive<OLock>(&v23);
        }
      }
    }
    v14 = *(_BYTE **)(v3 + 40);
    v15 = *(_BYTE **)(v3 + 48);
    v19 = (__int64)v15;
    while ( v14 != v15 )
    {
      if ( *v14 <= (unsigned __int8)v2 )
      {
        OString::UnicodeToAnsi(&Src, v14 + 8, 65001);
        std::string::append(&Src);
        if ( !(unsigned __int8)OFile::TryWrite(v6, &Src) )
        {
          OFile::Close(v22);
          v5 = 1;
          std::string::~string(&Src);
          goto LABEL_19;
        }
        *(_BYTE *)(v3 + 128) = 1;
        std::string::~string(&Src);
        v15 = (_BYTE *)v19;
      }
      v14 += 40;
    }
    goto LABEL_19;
  }
  return AcquireExclusive<OLock>::~AcquireExclusive<OLock>(&v23);
}

```

## disassembly

```asm
0x180004660  mov     [rsp+arg_10], rbx
0x180004665  mov     [rsp+arg_18], rsi
0x18000466a  push    rdi
0x18000466b  push    r12
0x18000466d  push    r13
0x18000466f  push    r14
0x180004671  push    r15
0x180004673  sub     rsp, 0F0h
0x18000467a  mov     rax, cs:__security_cookie
0x180004681  xor     rax, rsp
0x180004684  mov     [rsp+118h+var_38], rax
0x18000468c  movzx   r12d, dl
0x180004690  mov     rdi, rcx
0x180004693  mov     [rsp+118h+var_C8], rcx
0x180004698  mov     [rsp+118h+var_E0], r12b
0x18000469d  lea     rsi, CriticalSection
0x1800046a4  mov     [rsp+118h+var_B0], rsi
0x1800046a9  xor     ebx, ebx
0x1800046ab  mov     [rsp+118h+var_A8], bl
0x1800046af  call    cs:__imp_GetCurrentThreadId
0x1800046b5  cmp     cs:dword_18021C0B4, eax
0x1800046bb  jz      short loc_1800046DD
0x1800046bd  mov     rcx, rsi; lpCriticalSection
0x1800046c0  call    cs:__imp_EnterCriticalSection
0x1800046c6  inc     cs:dword_18021C0B0
0x1800046cc  call    cs:__imp_GetCurrentThreadId
0x1800046d2  mov     cs:dword_18021C0B4, eax
0x1800046d8  mov     [rsp+118h+var_A8], 1
0x1800046dd  lea     r14, [rdi+28h]
0x1800046e1  mov     [rsp+118h+var_C0], r14
0x1800046e6  mov     rax, [r14+8]
0x1800046ea  cmp     rax, [r14]
0x1800046ed  jz      loc_18000484B
0x1800046f3  cmp     [rdi+1], r12b
0x1800046f7  ja      loc_180004882
0x1800046fd  mov     r13b, bl
0x180004700  lea     r15, [rdi+40h]
0x180004704  mov     [rsp+118h+var_D0], r15
0x180004709  mov     [rsp+118h+var_B8], r15
0x18000470e  cmp     qword ptr [r15+30h], 0FFFFFFFFFFFFFFFFh
0x180004713  jnz     loc_180004A00
0x180004719  lea     rsi, [rdi+8]
0x18000471d  cmp     [rsi+10h], rbx
0x180004721  jz      loc_1800047B9
0x180004727  xorps   xmm0, xmm0
0x18000472a  movups  xmmword ptr [rsp+118h+S1], xmm0
0x180004732  mov     [rsp+118h+N], rbx
0x18000473a  mov     [rsp+118h+var_40], 7
0x180004746  mov     word ptr [rsp+118h+S1], bx
0x18000474e  lea     rdx, [rsp+118h+S1]
0x180004756  mov     rcx, rsi
0x180004759  call    ?GetDirectoryName@OPath@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV23@@Z; OPath::GetDirectoryName(std::wstring const &,std::wstring &)
0x18000475e  mov     rdx, rsi
0x180004761  cmp     qword ptr [rsi+18h], 7
0x180004766  jbe     short loc_18000476B
0x180004768  mov     rdx, [rsi]; S2
0x18000476b  mov     r8, [rsp+118h+N]; N
0x180004773  lea     rcx, [rsp+118h+S1]
0x18000477b  cmp     [rsp+118h+var_40], 7
0x180004784  cmova   rcx, [rsp+118h+S1]; S1
0x18000478d  cmp     r8, [rsi+10h]
0x180004791  jz      loc_18000488F
0x180004797  lea     rcx, [rsp+118h+S1]
0x18000479f  call    ?Exists@ODirectory@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; ODirectory::Exists(std::wstring const &)
0x1800047a4  test    al, al
0x1800047a6  jz      loc_1800048AA
0x1800047ac  lea     rcx, [rsp+118h+S1]
0x1800047b4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800047b9  cmp     [rdi+18h], rbx
0x1800047bd  jz      loc_180004958
0x1800047c3  mov     rcx, rdi; this
0x1800047c6  call    ?EnsureUniqueFileName@OLog@@AEAAXXZ; OLog::EnsureUniqueFileName(void)
0x1800047cb  mov     rcx, rsi; lpFileName
0x1800047ce  call    ?Exists@OFile@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; OFile::Exists(std::wstring const &)
0x1800047d3  test    al, al
0x1800047d5  jnz     loc_180004990
0x1800047db  xorps   xmm0, xmm0
0x1800047de  movups  [rsp+118h+Src], xmm0
0x1800047e6  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800047ee  movdqu  [rsp+118h+var_68], xmm1
0x1800047f7  mov     word ptr [rsp+118h+Src], bx
0x1800047ff  mov     [rsp+118h+var_F0], bl
0x180004803  mov     [rsp+118h+var_F8], 1
0x18000480b  mov     r9d, 3
0x180004811  lea     r8d, [r9-2]
0x180004815  mov     rdx, rsi
0x180004818  mov     rcx, r15
0x18000481b  call    ?Open@OFile@@QEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4FileMode@fm@@W4FileAccess@fa@@W4FileShare@fs@@_N@Z; OFile::Open(std::wstring const &,fm::FileMode,fa::FileAccess,fs::FileShare,bool)
0x180004820  nop
0x180004821  lea     rcx, [rsp+118h+Src]
0x180004829  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000482e  test    r13b, r13b
0x180004831  jz      loc_180004A00
0x180004837  mov     rcx, r14
0x18000483a  call    ?clear@?$vector@UOLogLine@OLog@@V?$allocator@UOLogLine@OLog@@@std@@@std@@QEAAXXZ; std::vector<OLog::OLogLine>::clear(void)
0x18000483f  mov     [rdi+1], bl
0x180004842  test    r13b, r13b
0x180004845  jnz     loc_180004ABF
0x18000484b  lea     rcx, [rsp+118h+var_B0]
0x180004850  call    ??1?$AcquireExclusive@VOLock@@@@QEAA@XZ; AcquireExclusive<OLock>::~AcquireExclusive<OLock>(void)
0x180004855  mov     rcx, [rsp+118h+var_38]
0x18000485d  xor     rcx, rsp; StackCookie
0x180004860  call    __security_check_cookie
0x180004865  lea     r11, [rsp+118h+var_28]
0x18000486d  mov     rbx, [r11+40h]
0x180004871  mov     rsi, [r11+48h]
0x180004875  mov     rsp, r11
0x180004878  pop     r15
0x18000487a  pop     r14
0x18000487c  pop     r13
0x18000487e  pop     r12
0x180004880  pop     rdi
0x180004881  retn
0x180004882  mov     rcx, r14
0x180004885  call    ?clear@?$vector@UOLogLine@OLog@@V?$allocator@UOLogLine@OLog@@@std@@@std@@QEAAXXZ; std::vector<OLog::OLogLine>::clear(void)
0x18000488a  mov     [rdi+1], bl
0x18000488d  jmp     short loc_18000484B
0x18000488f  test    r8, r8
0x180004892  jz      loc_1800047AC
0x180004898  call    wmemcmp
0x18000489d  test    eax, eax
0x18000489f  jz      loc_1800047AC
0x1800048a5  jmp     loc_180004797
0x1800048aa  xor     edx, edx
0x1800048ac  lea     rcx, [rsp+118h+S1]
0x1800048b4  call    ?CreateDirectoryW@ODirectory@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAU_SECURITY_ATTRIBUTES@@@Z; ODirectory::CreateDirectoryW(std::wstring const &,bool,_SECURITY_ATTRIBUTES *)
0x1800048b9  test    al, al
0x1800048bb  jnz     loc_1800047AC
0x1800048c1  cmp     [rdi+81h], bl
0x1800048c7  jnz     short loc_18000493F
0x1800048c9  lfence
0x1800048cc  xorps   xmm0, xmm0
0x1800048cf  movups  [rsp+118h+Src], xmm0
0x1800048d7  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800048df  movdqu  [rsp+118h+var_68], xmm1
0x1800048e8  mov     word ptr [rsp+118h+Src], bx
0x1800048f0  mov     r8, rsi
0x1800048f3  lea     rdx, aLogPathSIsNotV; "Log path %s is not valid.  Reverting to"...
0x1800048fa  lea     rcx, [rsp+118h+var_A0]
0x1800048ff  call    ??$Format@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@OString@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WAEBV12@@Z; OString::Format<std::wstring>(wchar_t const *,std::wstring const &)
0x180004904  mov     rdx, rax
0x180004907  lea     rcx, [rsp+118h+Src]
0x18000490f  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180004914  lea     rcx, [rsp+118h+var_A0]; void *
0x180004919  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000491e  mov     edx, r12d
0x180004921  lea     r8, [rsp+118h+Src]
0x180004929  mov     rcx, rdi
0x18000492c  call    ?AddLine@OLog@@QEAAXW4Severity@Logging@Mso@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z; OLog::AddLine(Mso::Logging::Severity,std::wstring const &,bool)
0x180004931  nop
0x180004932  lea     rcx, [rsp+118h+Src]; void *
0x18000493a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000493f  mov     [rsi+10h], rbx
0x180004943  mov     rax, rsi
0x180004946  cmp     qword ptr [rsi+18h], 7
0x18000494b  jbe     short loc_180004950
0x18000494d  mov     rax, [rsi]
0x180004950  mov     [rax], bx
0x180004953  jmp     loc_1800047AC
0x180004958  mov     rcx, rsi
0x18000495b  call    ?GetTempPathW@OPath@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; OPath::GetTempPathW(std::wstring &)
0x180004960  lea     rdx, aOfficeLog; "Office(*).log"
0x180004967  lea     rcx, [rsp+118h+var_A0]
0x18000496c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180004971  nop
0x180004972  mov     r8, rsi
0x180004975  mov     rdx, rax
0x180004978  mov     rcx, rsi
0x18000497b  call    ?Combine@OPath@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAV23@@Z; OPath::Combine(std::wstring const &,std::wstring const &,std::wstring &)
0x180004980  nop
0x180004981  lea     rcx, [rsp+118h+var_A0]; void *
0x180004986  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000498b  jmp     loc_1800047C3
0x180004990  mov     [rsp+118h+var_F0], bl
0x180004994  mov     [rsp+118h+var_F8], 1
0x18000499c  mov     r9d, 3
0x1800049a2  xor     r8d, r8d
0x1800049a5  mov     rdx, rsi
0x1800049a8  mov     rcx, r15
0x1800049ab  call    ?Open@OFile@@QEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4FileMode@fm@@W4FileAccess@fa@@W4FileShare@fs@@_N@Z; OFile::Open(std::wstring const &,fm::FileMode,fa::FileAccess,fs::FileShare,bool)
0x1800049b0  xorps   xmm0, xmm0
0x1800049b3  movups  [rsp+118h+var_98], xmm0
0x1800049bb  mov     [rsp+118h+var_88], rbx
0x1800049c3  mov     [rsp+118h+var_80], 7
0x1800049cf  mov     word ptr [rsp+118h+var_98], bx
0x1800049d7  mov     [rsp+118h+var_A0], 32h ; '2'
0x1800049dc  mov     r8, [rdi+28h]
0x1800049e0  lea     r9, [rsp+118h+var_A0]
0x1800049e5  lea     rdx, [rsp+118h+var_D8]
0x1800049ea  mov     rcx, r14
0x1800049ed  call    ??$emplace@AEBUOLogLine@OLog@@@?$vector@UOLogLine@OLog@@V?$allocator@UOLogLine@OLog@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UOLogLine@OLog@@@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UOLogLine@OLog@@@std@@@std@@@1@AEBUOLogLine@OLog@@@Z; std::vector<OLog::OLogLine>::emplace<OLog::OLogLine const &>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<OLog::OLogLine>>>,OLog::OLogLine const &)
0x1800049f2  nop
0x1800049f3  lea     rcx, [rsp+118h+var_98]; void *
0x1800049fb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180004a00  mov     rsi, [rdi+28h]
0x180004a04  mov     rax, [rdi+30h]
0x180004a08  mov     [rsp+118h+var_D0], rax
0x180004a0d  cmp     rsi, rax
0x180004a10  jz      loc_180004837
0x180004a16  cmp     [rsi], r12b
0x180004a19  ja      short loc_180004A7A
0x180004a1b  lea     rdx, [rsi+8]
0x180004a1f  mov     r8d, 0FDE9h
0x180004a25  lea     rcx, [rsp+118h+Src]
0x180004a2d  call    ?UnicodeToAnsi@OString@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@I@Z; OString::UnicodeToAnsi(std::wstring const &,uint)
0x180004a32  nop
0x180004a33  mov     r8d, 2
0x180004a39  lea     rdx, asc_1801A911C; "\r\n"
0x180004a40  lea     rcx, [rsp+118h+Src]; Src
0x180004a48  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x180004a4d  lea     rdx, [rsp+118h+Src]
0x180004a55  mov     rcx, r15
0x180004a58  call    ?TryWrite@OFile@@QEAA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; OFile::TryWrite(std::string const &)
0x180004a5d  test    al, al
0x180004a5f  jz      short loc_180004AA0
0x180004a61  mov     byte ptr [rdi+80h], 1
0x180004a68  lea     rcx, [rsp+118h+Src]; void *
0x180004a70  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180004a75  mov     rax, [rsp+118h+var_D0]
0x180004a7a  add     rsi, 28h ; '('
0x180004a7e  jmp     short loc_180004A0D
0x180004a80  xor     ebx, ebx
0x180004a82  mov     r13b, [rsp+118h+var_E8]
0x180004a87  mov     rdi, [rsp+118h+var_C8]
0x180004a8c  mov     r12b, [rsp+118h+var_E0]
0x180004a91  mov     r14, [rsp+118h+var_C0]
0x180004a96  mov     r15, [rsp+118h+var_D0]
0x180004a9b  jmp     loc_180004821
0x180004aa0  mov     rcx, [rsp+118h+var_B8]; this
0x180004aa5  call    ?Close@OFile@@QEAAXXZ; OFile::Close(void)
0x180004aaa  mov     r13b, 1
0x180004aad  lea     rcx, [rsp+118h+Src]; void *
0x180004ab5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180004aba  jmp     loc_180004837
0x180004abf  xorps   xmm0, xmm0
0x180004ac2  movups  [rsp+118h+var_98], xmm0
0x180004aca  mov     [rsp+118h+var_88], rbx
0x180004ad2  mov     [rsp+118h+var_80], 7
0x180004ade  mov     word ptr [rsp+118h+var_98], bx
0x180004ae6  mov     [rsp+118h+var_A0], r12b
0x180004aeb  lea     rdx, aALoggingFailur; "==========A logging failure has occured"...
0x180004af2  lea     rcx, [rsp+118h+var_98]; void *
0x180004afa  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180004aff  mov     r8, [rdi+28h]
0x180004b03  lea     r9, [rsp+118h+var_A0]
0x180004b08  lea     rdx, [rsp+118h+var_D8]
0x180004b0d  mov     rcx, r14
0x180004b10  call    ??$emplace@AEBUOLogLine@OLog@@@?$vector@UOLogLine@OLog@@V?$allocator@UOLogLine@OLog@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UOLogLine@OLog@@@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UOLogLine@OLog@@@std@@@std@@@1@AEBUOLogLine@OLog@@@Z; std::vector<OLog::OLogLine>::emplace<OLog::OLogLine const &>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<OLog::OLogLine>>>,OLog::OLogLine const &)
0x180004b15  nop
0x180004b16  lea     rcx, [rsp+118h+var_98]; void *
0x180004b1e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180004b23  jmp     loc_18000484B
```
