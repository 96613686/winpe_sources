# Microsoft::VisualStudio::PkgDef::CPkgDefManagement::MergeConfigurationFile(void)

- ea: `0x140021f90`
- end: `0x1400222ae`
- name: `?MergeConfigurationFile@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@UEAAJXZ`
- size: `798`
- prototype: `__int64 __fastcall(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140001020`
- `0x140001040`
- `0x140002160`
- `0x140002190`
- `0x140002c10`
- `0x140002dd0`
- `0x140003ec0`
- `0x140014c2c`
- `0x140021f90`
- `0x1400222b0`
- `0x140030d30`
- `0x140033ab0`
- `0x140046514`

## import_xrefs

- `KERNEL32!SetEnvironmentVariableW` at `0x1400221df`
- `KERNEL32!SetEnvironmentVariableW` at `0x1400221df`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14002218c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14002218c`
- `SHLWAPI!PathIsDirectoryW` at `0x140021fde`
- `SHLWAPI!PathIsDirectoryW` at `0x140021fde`

## string_xrefs

- `0x1400221d8`: `PkgDefApplicationConfigFile`
- `0x140021fec`: `Executable path is a directory. Cannot perform configuration merge.`
- `0x140022008`: `CMergeConfigFile already exists inside CPkgDefManagement::MergeConfigurationFile.`
- `0x1400221bc`: `Configuration file merge failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::VisualStudio::PkgDef::CPkgDefManagement::MergeConfigurationFile(
        Microsoft::VisualStudio::PkgDef::CPkgDefManagement *this)
{
  const WCHAR *v2; // rcx
  const unsigned __int16 *v4; // r8
  const unsigned __int16 *v5; // rcx
  Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile *v6; // rax
  Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile *v7; // rbx
  __int64 v8; // rax
  Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile *v9; // rbx
  struct ATL::IAtlStringMgr *Instance; // rax
  struct ATL::IAtlStringMgr *v11; // rax
  struct ATL::IAtlStringMgr *v12; // rax
  unsigned __int16 *v13; // rbx
  int v14; // esi
  unsigned __int16 *v15; // r14
  const unsigned __int16 *v16; // r15
  unsigned __int16 *v17; // r12
  Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile *v18; // r13
  __int64 v19; // rdi
  char v20; // si
  HKEY v21; // rax
  int v22; // eax
  unsigned __int16 *v23; // rdx
  unsigned __int16 *v24; // rdx
  unsigned __int16 *v25; // [rsp+50h] [rbp-30h] BYREF
  Microsoft::VisualStudio::PkgDef::CPkgDefManagement *v26; // [rsp+58h] [rbp-28h]
  unsigned __int16 *v27; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int16 *v28; // [rsp+68h] [rbp-18h] BYREF

  v26 = this;
  v2 = (const WCHAR *)*((_QWORD *)this + 11);
  if ( !*((_DWORD *)v2 - 4) )
    return 2147549183LL;
  if ( PathIsDirectoryW(v2) )
  {
    v4 = (const unsigned __int16 *)*((_QWORD *)this + 11);
    v5 = L"Executable path is a directory. Cannot perform configuration merge.";
LABEL_5:
    CLogger::LogError(v5, -2147418113, v4);
    return 2147549183LL;
  }
  if ( *((_QWORD *)this + 1) )
  {
    v4 = 0;
    v5 = L"CMergeConfigFile already exists inside CPkgDefManagement::MergeConfigurationFile.";
    goto LABEL_5;
  }
  v6 = (Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile *)operator new(0xC0u);
  v7 = v6;
  v25 = (unsigned __int16 *)v6;
  if ( v6 )
  {
    memset_0(v6, 0, 0xC0u);
    v8 = Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::CMergeConfigFile(v7);
  }
  else
  {
    v8 = 0;
  }
  v9 = (Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = v8;
  if ( v9 )
  {
    Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::~CMergeConfigFile(v9);
    operator delete(v9, (const struct std::nothrow_t *)0xC0);
  }
  v28 = 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v28 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                           + 24);
  v27 = 0;
  v11 = ATL::CAtlStringMgr::GetInstance();
  if ( !v11 )
    ATL::AtlThrowImpl(-2147467259);
  v27 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v11 + 24LL))(v11) + 24);
  v12 = ATL::CAtlStringMgr::GetInstance();
  if ( !v12 )
    ATL::AtlThrowImpl(-2147467259);
  v13 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v12 + 24LL))(v12) + 24);
  v25 = v13;
  v14 = (*(__int64 (__fastcall **)(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *, unsigned __int16 **, _QWORD))(*(_QWORD *)this + 72LL))(
          this,
          &v28,
          0);
  if ( v14 >= 0 )
  {
    _mm_lfence();
    v14 = (*(__int64 (__fastcall **)(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *, unsigned __int16 **, _QWORD))(*(_QWORD *)this + 24LL))(
            this,
            &v27,
            0);
    if ( v14 >= 0 )
    {
      _mm_lfence();
      if ( ((1 - *((_DWORD *)v13 - 2)) | (*((_DWORD *)v13 - 3) - 260)) < 0 )
      {
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v25, 260);
        v13 = v25;
      }
      v15 = v27;
      v16 = (const unsigned __int16 *)*((_QWORD *)this + 11);
      v17 = v28;
      v18 = (Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile *)*((_QWORD *)this + 1);
      v19 = *((_QWORD *)this + 2);
      v20 = (*(__int64 (**)(void))(*(_QWORD *)v19 + 88LL))();
      LOBYTE(v19) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 80LL))(v19);
      v21 = (HKEY)(*(__int64 (__fastcall **)(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *))(*(_QWORD *)v26
                                                                                                  + 280LL))(v26);
      v14 = Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::Merge(
              v18,
              v21,
              v17,
              v16,
              v15,
              v19,
              v20,
              v13);
      v22 = wcsnlen(v13, *((int *)v13 - 3));
      if ( v22 < 0 || v22 > *((_DWORD *)v13 - 3) )
        ATL::AtlThrowImpl(-2147024809);
      *((_DWORD *)v13 - 4) = v22;
      v13[v22] = 0;
      if ( v14 < 0 )
      {
        _mm_lfence();
        CLogger::LogError(L"Configuration file merge failed.", v14, 0);
        ATL::CSimpleStringT<unsigned short,0>::Empty(&v25);
        v13 = v25;
      }
      SetEnvironmentVariableW(L"PkgDefApplicationConfigFile", v13);
    }
  }
  if ( _InterlockedDecrement((volatile signed __int32 *)v13 - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v13 - 3) + 8LL))(*((_QWORD *)v13 - 3));
  }
  v23 = v27 - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)v27 - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 8LL))(*(_QWORD *)v23);
  }
  v24 = v28 - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)v28 - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v24 + 8LL))(*(_QWORD *)v24);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140021f90  mov     [rsp-28h+arg_8], rbx
0x140021f95  mov     [rsp-28h+arg_10], rsi
0x140021f9a  mov     [rsp-28h+arg_18], rdi
0x140021f9f  push    rbp
0x140021fa0  push    r12
0x140021fa2  push    r13
0x140021fa4  push    r14
0x140021fa6  push    r15
0x140021fa8  mov     rbp, rsp
0x140021fab  sub     rsp, 80h
0x140021fb2  mov     rax, cs:__security_cookie
0x140021fb9  xor     rax, rsp
0x140021fbc  mov     [rbp+var_10], rax
0x140021fc0  mov     rdi, rcx
0x140021fc3  mov     [rbp+var_28], rcx
0x140021fc7  mov     rcx, [rcx+58h]; pszPath
0x140021fcb  xor     r14d, r14d
0x140021fce  cmp     [rcx-10h], r14d
0x140021fd2  jnz     short loc_140021FDE
0x140021fd4  mov     eax, 8000FFFFh
0x140021fd9  jmp     loc_14002224C
0x140021fde  call    cs:__imp_PathIsDirectoryW
0x140021fe4  test    eax, eax
0x140021fe6  jz      short loc_140021FFF
0x140021fe8  mov     r8, [rdi+58h]; unsigned __int16 *
0x140021fec  lea     rcx, aExecutablePath; "Executable path is a directory. Cannot "...
0x140021ff3  mov     edx, 8000FFFFh; int
0x140021ff8  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x140021ffd  jmp     short loc_140021FD4
0x140021fff  cmp     [rdi+8], r14
0x140022003  jz      short loc_140022011
0x140022005  xor     r8d, r8d
0x140022008  lea     rcx, aCmergeconfigfi; "CMergeConfigFile already exists inside "...
0x14002200f  jmp     short loc_140021FF3
0x140022011  mov     esi, 0C0h
0x140022016  mov     ecx, esi; Size
0x140022018  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002201d  mov     rbx, rax
0x140022020  mov     [rbp+var_30], rax
0x140022024  test    rax, rax
0x140022027  jz      short loc_140022040
0x140022029  mov     r8d, esi; Size
0x14002202c  xor     edx, edx; Val
0x14002202e  mov     rcx, rax; void *
0x140022031  call    memset_0
0x140022036  mov     rcx, rbx; this
0x140022039  call    ??0CMergeConfigFile@BindingRedirects@PkgDef@VisualStudio@Microsoft@@QEAA@XZ; Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::CMergeConfigFile(void)
0x14002203e  jmp     short loc_140022043
0x140022040  mov     rax, r14
0x140022043  mov     rbx, [rdi+8]
0x140022047  mov     [rdi+8], rax
0x14002204b  test    rbx, rbx
0x14002204e  jz      short loc_140022063
0x140022050  mov     rcx, rbx; this
0x140022053  call    ??1CMergeConfigFile@BindingRedirects@PkgDef@VisualStudio@Microsoft@@QEAA@XZ; Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::~CMergeConfigFile(void)
0x140022058  mov     rdx, rsi; struct std::nothrow_t *
0x14002205b  mov     rcx, rbx; void *
0x14002205e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140022063  mov     [rbp+var_18], r14
0x140022067  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002206c  mov     rcx, rax
0x14002206f  test    rax, rax
0x140022072  jz      loc_140022295
0x140022078  mov     rax, [rax]
0x14002207b  call    qword ptr [rax+18h]
0x14002207e  add     rax, 18h
0x140022082  mov     [rbp+var_18], rax
0x140022086  mov     [rbp+var_20], r14
0x14002208a  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002208f  mov     rcx, rax
0x140022092  test    rax, rax
0x140022095  jz      loc_1400222A3
0x14002209b  mov     rax, [rax]
0x14002209e  call    qword ptr [rax+18h]
0x1400220a1  add     rax, 18h
0x1400220a5  mov     [rbp+var_20], rax
0x1400220a9  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1400220ae  mov     rcx, rax
0x1400220b1  test    rax, rax
0x1400220b4  jz      loc_140022279
0x1400220ba  mov     rax, [rax]
0x1400220bd  call    qword ptr [rax+18h]
0x1400220c0  lea     rbx, [rax+18h]
0x1400220c4  mov     [rbp+var_30], rbx
0x1400220c8  mov     rax, [rdi]
0x1400220cb  xor     r8d, r8d
0x1400220ce  lea     rdx, [rbp+var_18]
0x1400220d2  mov     rcx, rdi
0x1400220d5  call    qword ptr [rax+48h]
0x1400220d8  mov     esi, eax
0x1400220da  test    eax, eax
0x1400220dc  js      loc_1400221E6
0x1400220e2  lfence
0x1400220e5  mov     rax, [rdi]
0x1400220e8  xor     r8d, r8d
0x1400220eb  lea     rdx, [rbp+var_20]
0x1400220ef  mov     rcx, rdi
0x1400220f2  call    qword ptr [rax+18h]
0x1400220f5  mov     esi, eax
0x1400220f7  test    eax, eax
0x1400220f9  js      loc_1400221E6
0x1400220ff  lfence
0x140022102  mov     ecx, 1
0x140022107  sub     ecx, [rbx-8]
0x14002210a  mov     eax, [rbx-0Ch]
0x14002210d  mov     edx, 104h
0x140022112  sub     eax, edx
0x140022114  or      eax, ecx
0x140022116  jge     short loc_140022125
0x140022118  lea     rcx, [rbp+var_30]
0x14002211c  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x140022121  mov     rbx, [rbp+var_30]
0x140022125  mov     r14, [rbp+var_20]
0x140022129  mov     r15, [rdi+58h]
0x14002212d  mov     r12, [rbp+var_18]
0x140022131  mov     r13, [rdi+8]
0x140022135  mov     rcx, [rdi+10h]
0x140022139  mov     rdi, rcx
0x14002213c  mov     rax, [rcx]
0x14002213f  call    qword ptr [rax+58h]
0x140022142  mov     sil, al
0x140022145  mov     rdx, [rdi]
0x140022148  mov     rcx, rdi
0x14002214b  call    qword ptr [rdx+50h]
0x14002214e  mov     dil, al
0x140022151  mov     rcx, [rbp+var_28]
0x140022155  mov     rdx, [rcx]
0x140022158  call    qword ptr [rdx+118h]
0x14002215e  mov     rdx, rax; HKEY
0x140022161  mov     [rsp+80h+var_48], rbx; unsigned __int16 *
0x140022166  mov     [rsp+80h+var_50], sil; bool
0x14002216b  mov     [rsp+80h+var_58], dil; bool
0x140022170  mov     [rsp+80h+var_60], r14; unsigned __int16 *
0x140022175  mov     r9, r15; unsigned __int16 *
0x140022178  mov     r8, r12; unsigned __int16 *
0x14002217b  mov     rcx, r13; this
0x14002217e  call    ?Merge@CMergeConfigFile@BindingRedirects@PkgDef@VisualStudio@Microsoft@@QEAAJPEAUHKEY__@@PEBG11_N2PEAGH@Z; Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::Merge(HKEY__ *,ushort const *,ushort const *,ushort const *,bool,bool,ushort *,int)
0x140022183  mov     esi, eax
0x140022185  movsxd  rdx, dword ptr [rbx-0Ch]; MaxCount
0x140022189  mov     rcx, rbx; Source
0x14002218c  call    cs:__imp_wcsnlen
0x140022192  xor     r14d, r14d
0x140022195  test    eax, eax
0x140022197  js      loc_140022287
0x14002219d  cmp     eax, [rbx-0Ch]
0x1400221a0  jg      loc_140022287
0x1400221a6  mov     [rbx-10h], eax
0x1400221a9  cdqe
0x1400221ab  mov     [rbx+rax*2], r14w
0x1400221b0  test    esi, esi
0x1400221b2  jns     short loc_1400221D5
0x1400221b4  lfence
0x1400221b7  xor     r8d, r8d; unsigned __int16 *
0x1400221ba  mov     edx, esi; int
0x1400221bc  lea     rcx, aConfigurationF_0; "Configuration file merge failed."
0x1400221c3  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x1400221c8  lea     rcx, [rbp+var_30]
0x1400221cc  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1400221d1  mov     rbx, [rbp+var_30]
0x1400221d5  mov     rdx, rbx; lpValue
0x1400221d8  lea     rcx, aPkgdefapplicat; "PkgDefApplicationConfigFile"
0x1400221df  call    cs:__imp_SetEnvironmentVariableW
0x1400221e5  nop
0x1400221e6  lea     rdx, [rbx-18h]
0x1400221ea  or      ebx, 0FFFFFFFFh
0x1400221ed  mov     eax, ebx
0x1400221ef  lock xadd [rdx+10h], eax
0x1400221f4  add     eax, ebx
0x1400221f6  test    eax, eax
0x1400221f8  jg      short loc_140022207
0x1400221fa  lfence
0x1400221fd  mov     rcx, [rdx]
0x140022200  mov     rax, [rcx]
0x140022203  call    qword ptr [rax+8]
0x140022206  nop
0x140022207  mov     rdx, [rbp+var_20]
0x14002220b  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14002220f  mov     eax, ebx
0x140022211  lock xadd [rdx+10h], eax
0x140022216  add     eax, ebx
0x140022218  test    eax, eax
0x14002221a  jg      short loc_140022229
0x14002221c  lfence
0x14002221f  mov     rcx, [rdx]
0x140022222  mov     rax, [rcx]
0x140022225  call    qword ptr [rax+8]
0x140022228  nop
0x140022229  mov     rdx, [rbp+var_18]
0x14002222d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140022231  mov     eax, ebx
0x140022233  lock xadd [rdx+10h], eax
0x140022238  add     eax, ebx
0x14002223a  test    eax, eax
0x14002223c  jg      short loc_14002224A
0x14002223e  lfence
0x140022241  mov     rcx, [rdx]
0x140022244  mov     rax, [rcx]
0x140022247  call    qword ptr [rax+8]
0x14002224a  mov     eax, esi
0x14002224c  mov     rcx, [rbp+var_10]
0x140022250  xor     rcx, rsp; StackCookie
0x140022253  call    __security_check_cookie
0x140022258  lea     r11, [rsp+80h+var_s0]
0x140022260  mov     rbx, [r11+38h]
0x140022264  mov     rsi, [r11+40h]
0x140022268  mov     rdi, [r11+48h]
0x14002226c  mov     rsp, r11
0x14002226f  pop     r15
0x140022271  pop     r14
0x140022273  pop     r13
0x140022275  pop     r12
0x140022277  pop     rbp
0x140022278  retn
0x140022279  mov     ecx, 80004005h; int
0x14002227e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140022284  jmp     short $+2
0x140022286  nop
0x140022287  mov     ecx, 80070057h; int
0x14002228c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140022292  jmp     short $+2
0x140022294  nop
0x140022295  mov     ecx, 80004005h; int
0x14002229a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400222a0  jmp     short $+2
0x1400222a2  nop
0x1400222a3  mov     ecx, 80004005h; int
0x1400222a8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
