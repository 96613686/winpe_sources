# CPkgDefCacheNonVolatile::AreTimestampsCurrent(PkgDefMergeReason *)

- ea: `0x14001875c`
- end: `0x140018978`
- name: `?AreTimestampsCurrent@CPkgDefCacheNonVolatile@@IEBA_NPEAW4PkgDefMergeReason@@@Z`
- size: `540`
- prototype: `bool __fastcall(CPkgDefCacheNonVolatile *__hidden this, enum PkgDefMergeReason *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400147e0`
- `0x140018740`

## callees

- `0x140001020`
- `0x140002618`
- `0x1400095f4`
- `0x14001875c`
- `0x140018978`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x140018867`
- `KERNEL32!CompareFileTime` at `0x1400188bf`
- `KERNEL32!CompareFileTime` at `0x1400188fc`
- `KERNEL32!CompareFileTime` at `0x140018867`
- `KERNEL32!CompareFileTime` at `0x1400188bf`
- `KERNEL32!CompareFileTime` at `0x1400188fc`

## string_xrefs

- `0x140018949`: `PkgDefCache fast check: timestamps are current.`
- `0x140018799`: `PkgDefCache fast check: the timestamps are not current because the cache lock was abandoned.`
- `0x1400187d2`: `PkgDefCache fast check: the timestamps are not current because the cache is either missing or corrupt.`
- `0x1400187f0`: `PkgDefCache fast check: forcing refresh because the PKGDEFMANAGEMENT_FORCECACHEREFRESH flag was present.`
- `0x14001887d`: `PkgDefCache fast check: the timestamps are not current because the per-user configuration changed timestamp was modfied since the last merge.`
- `0x1400188d5`: `PkgDefCache fast check: the timestamps are not current because the HKLM configuration changed timestamp was modified since the last merge.`
- `0x140018912`: `PkgDefCache fast check: the timestamps are not current because the extensions.configurationchanged file has been updated.`
- `0x140018938`: `PkgDefCache fast check: timestamps are not current because we got default FILETIME results for all checked timestamp locations.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CPkgDefCacheNonVolatile::AreTimestampsCurrent(
        CPkgDefCacheNonVolatile *this,
        enum PkgDefMergeReason *a2)
{
  const unsigned __int16 *v4; // rcx
  __int64 UserSettingsRoot; // r9
  HKEY v7; // r8
  _QWORD *v8; // rdx
  bool v9; // r14
  bool v10; // si
  const FILETIME *v11; // rdx
  bool v12; // di
  __int64 v13; // [rsp+20h] [rbp-30h] BYREF
  FILETIME FileTime1; // [rsp+28h] [rbp-28h] BYREF
  FILETIME FileTime2; // [rsp+30h] [rbp-20h] BYREF
  FILETIME v16; // [rsp+38h] [rbp-18h] BYREF

  if ( *((_BYTE *)this + 321) )
  {
    if ( a2 )
      *(_DWORD *)a2 = 7;
    v4 = L"PkgDefCache fast check: the timestamps are not current because the cache lock was abandoned.";
LABEL_5:
    CLogger::LogInfo(v4, 0, 0);
    return 0;
  }
  (*(void (__fastcall **)(CPkgDefCacheNonVolatile *, FILETIME *))(*(_QWORD *)this + 24LL))(this, &FileTime1);
  if ( !*(_QWORD *)&FileTime1 )
  {
    if ( a2 )
      *(_DWORD *)a2 = 9;
    v4 = L"PkgDefCache fast check: the timestamps are not current because the cache is either missing or corrupt.";
    goto LABEL_5;
  }
  if ( (*((_DWORD *)this + 2) & 0x100) != 0 )
  {
    if ( a2 )
      *(_DWORD *)a2 = 6;
    v4 = L"PkgDefCache fast check: forcing refresh because the PKGDEFMANAGEMENT_FORCECACHEREFRESH flag was present.";
    goto LABEL_5;
  }
  UserSettingsRoot = CPkgDefCache::GetUserSettingsRoot(this, &v13);
  v7 = hKey;
  if ( *((_QWORD *)this + 29) )
    v7 = (HKEY)*((_QWORD *)this + 29);
  CPkgDefCacheNonVolatile::GetConfigurationChangedTimestamp(this, &FileTime2, v7, UserSettingsRoot);
  v8 = (_QWORD *)(v13 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v13 - 24 + 16), 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
  }
  v9 = !FileTime2.dwHighDateTime && !FileTime2.dwLowDateTime;
  if ( CompareFileTime(&FileTime1, &FileTime2) == -1 )
  {
    if ( a2 )
      *(_DWORD *)a2 = 11;
    v4 = L"PkgDefCache fast check: the timestamps are not current because the per-user configuration changed timestamp was"
          " modfied since the last merge.";
    goto LABEL_5;
  }
  CPkgDefCacheNonVolatile::GetConfigurationChangedTimestamp(this, &v16, *((_QWORD *)this + 48), (char *)this + 392);
  v10 = !v16.dwHighDateTime && !v16.dwLowDateTime;
  if ( CompareFileTime(&FileTime1, &v16) == -1 )
  {
    if ( a2 )
      *(_DWORD *)a2 = 12;
    v4 = L"PkgDefCache fast check: the timestamps are not current because the HKLM configuration changed timestamp was mod"
          "ified since the last merge.";
    goto LABEL_5;
  }
  v11 = (const FILETIME *)((char *)this + 52);
  v12 = !*((_DWORD *)this + 14) && !v11->dwLowDateTime;
  if ( CompareFileTime(&FileTime1, v11) == -1 )
  {
    if ( a2 )
      *(_DWORD *)a2 = 10;
    v4 = L"PkgDefCache fast check: the timestamps are not current because the extensions.configurationchanged file has been updated.";
    goto LABEL_5;
  }
  if ( v9 && v10 && v12 )
  {
    if ( a2 )
      *(_DWORD *)a2 = 8;
    v4 = L"PkgDefCache fast check: timestamps are not current because we got default FILETIME results for all checked time"
          "stamp locations.";
    goto LABEL_5;
  }
  CLogger::LogInfo(L"PkgDefCache fast check: timestamps are current.", 0, 0);
  return 1;
}

```

## disassembly

```asm
0x14001875c  mov     [rsp-18h+arg_10], rbx
0x140018761  mov     [rsp-18h+arg_18], rsi
0x140018766  push    rbp
0x140018767  push    rdi
0x140018768  push    r14
0x14001876a  mov     rbp, rsp
0x14001876d  sub     rsp, 50h
0x140018771  mov     rax, cs:__security_cookie
0x140018778  xor     rax, rsp
0x14001877b  mov     [rbp+var_10], rax
0x14001877f  mov     rbx, rdx
0x140018782  mov     rdi, rcx
0x140018785  cmp     byte ptr [rcx+141h], 0
0x14001878c  jz      short loc_1400187B1
0x14001878e  test    rdx, rdx
0x140018791  jz      short loc_140018799
0x140018793  mov     dword ptr [rdx], 7
0x140018799  lea     rcx, aPkgdefcacheFas; "PkgDefCache fast check: the timestamps "...
0x1400187a0  xor     r8d, r8d; unsigned __int16 *
0x1400187a3  xor     edx, edx; int
0x1400187a5  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x1400187aa  xor     al, al
0x1400187ac  jmp     loc_140018957
0x1400187b1  mov     rax, [rcx]
0x1400187b4  lea     rdx, [rbp+FileTime1]
0x1400187b8  call    qword ptr [rax+18h]
0x1400187bb  cmp     [rbp+FileTime1.dwHighDateTime], 0
0x1400187bf  jnz     short loc_1400187DB
0x1400187c1  cmp     [rbp+FileTime1.dwLowDateTime], 0
0x1400187c5  jnz     short loc_1400187DB
0x1400187c7  test    rbx, rbx
0x1400187ca  jz      short loc_1400187D2
0x1400187cc  mov     dword ptr [rbx], 9
0x1400187d2  lea     rcx, aPkgdefcacheFas_1; "PkgDefCache fast check: the timestamps "...
0x1400187d9  jmp     short loc_1400187A0
0x1400187db  mov     eax, [rdi+8]
0x1400187de  shr     eax, 8
0x1400187e1  test    al, 1
0x1400187e3  jz      short loc_1400187F9
0x1400187e5  test    rbx, rbx
0x1400187e8  jz      short loc_1400187F0
0x1400187ea  mov     dword ptr [rbx], 6
0x1400187f0  lea     rcx, aPkgdefcacheFas_6; "PkgDefCache fast check: forcing refresh"...
0x1400187f7  jmp     short loc_1400187A0
0x1400187f9  lea     rdx, [rbp+var_30]
0x1400187fd  mov     rcx, rdi
0x140018800  call    ?GetUserSettingsRoot@CPkgDefCache@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPkgDefCache::GetUserSettingsRoot(void)
0x140018805  mov     r9, rax
0x140018808  mov     rax, [rdi+0E8h]
0x14001880f  mov     r8, cs:hKey
0x140018816  test    rax, rax
0x140018819  cmovnz  r8, rax
0x14001881d  lea     rdx, [rbp+FileTime2]
0x140018821  mov     rcx, rdi
0x140018824  call    ?GetConfigurationChangedTimestamp@CPkgDefCacheNonVolatile@@IEBA?AU_FILETIME@@PEAUHKEY__@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CPkgDefCacheNonVolatile::GetConfigurationChangedTimestamp(HKEY__ *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140018829  nop
0x14001882a  mov     rdx, [rbp+var_30]
0x14001882e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140018832  or      eax, 0FFFFFFFFh
0x140018835  lock xadd [rdx+10h], eax
0x14001883a  sub     eax, 1
0x14001883d  jg      short loc_14001884B
0x14001883f  lfence
0x140018842  mov     rcx, [rdx]
0x140018845  mov     rax, [rcx]
0x140018848  call    qword ptr [rax+8]
0x14001884b  cmp     [rbp+FileTime2.dwHighDateTime], 0
0x14001884f  jnz     short loc_14001885C
0x140018851  cmp     [rbp+FileTime2.dwLowDateTime], 0
0x140018855  jnz     short loc_14001885C
0x140018857  mov     r14b, 1
0x14001885a  jmp     short loc_14001885F
0x14001885c  xor     r14b, r14b
0x14001885f  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x140018863  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x140018867  call    cs:__imp_CompareFileTime
0x14001886d  cmp     eax, 0FFFFFFFFh
0x140018870  jnz     short loc_140018889
0x140018872  test    rbx, rbx
0x140018875  jz      short loc_14001887D
0x140018877  mov     dword ptr [rbx], 0Bh
0x14001887d  lea     rcx, aPkgdefcacheFas_2; "PkgDefCache fast check: the timestamps "...
0x140018884  jmp     loc_1400187A0
0x140018889  lea     r9, [rdi+188h]
0x140018890  mov     r8, [rdi+180h]
0x140018897  lea     rdx, [rbp+var_18]
0x14001889b  mov     rcx, rdi
0x14001889e  call    ?GetConfigurationChangedTimestamp@CPkgDefCacheNonVolatile@@IEBA?AU_FILETIME@@PEAUHKEY__@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CPkgDefCacheNonVolatile::GetConfigurationChangedTimestamp(HKEY__ *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400188a3  cmp     [rbp+var_18.dwHighDateTime], 0
0x1400188a7  jnz     short loc_1400188B4
0x1400188a9  cmp     [rbp+var_18.dwLowDateTime], 0
0x1400188ad  jnz     short loc_1400188B4
0x1400188af  mov     sil, 1
0x1400188b2  jmp     short loc_1400188B7
0x1400188b4  xor     sil, sil
0x1400188b7  lea     rdx, [rbp+var_18]; lpFileTime2
0x1400188bb  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1400188bf  call    cs:__imp_CompareFileTime
0x1400188c5  cmp     eax, 0FFFFFFFFh
0x1400188c8  jnz     short loc_1400188E1
0x1400188ca  test    rbx, rbx
0x1400188cd  jz      short loc_1400188D5
0x1400188cf  mov     dword ptr [rbx], 0Ch
0x1400188d5  lea     rcx, aPkgdefcacheFas_5; "PkgDefCache fast check: the timestamps "...
0x1400188dc  jmp     loc_1400187A0
0x1400188e1  lea     rdx, [rdi+34h]; lpFileTime2
0x1400188e5  cmp     dword ptr [rdx+4], 0
0x1400188e9  jnz     short loc_1400188F5
0x1400188eb  cmp     dword ptr [rdx], 0
0x1400188ee  jnz     short loc_1400188F5
0x1400188f0  mov     dil, 1
0x1400188f3  jmp     short loc_1400188F8
0x1400188f5  xor     dil, dil
0x1400188f8  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1400188fc  call    cs:__imp_CompareFileTime
0x140018902  cmp     eax, 0FFFFFFFFh
0x140018905  jnz     short loc_14001891E
0x140018907  test    rbx, rbx
0x14001890a  jz      short loc_140018912
0x14001890c  mov     dword ptr [rbx], 0Ah
0x140018912  lea     rcx, aPkgdefcacheFas_4; "PkgDefCache fast check: the timestamps "...
0x140018919  jmp     loc_1400187A0
0x14001891e  test    r14b, r14b
0x140018921  jz      short loc_140018944
0x140018923  test    sil, sil
0x140018926  jz      short loc_140018944
0x140018928  test    dil, dil
0x14001892b  jz      short loc_140018944
0x14001892d  test    rbx, rbx
0x140018930  jz      short loc_140018938
0x140018932  mov     dword ptr [rbx], 8
0x140018938  lea     rcx, aPkgdefcacheFas_3; "PkgDefCache fast check: timestamps are "...
0x14001893f  jmp     loc_1400187A0
0x140018944  xor     r8d, r8d; unsigned __int16 *
0x140018947  xor     edx, edx; int
0x140018949  lea     rcx, aPkgdefcacheFas_0; "PkgDefCache fast check: timestamps are "...
0x140018950  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x140018955  mov     al, 1
0x140018957  mov     rcx, [rbp+var_10]
0x14001895b  xor     rcx, rsp; StackCookie
0x14001895e  call    __security_check_cookie
0x140018963  lea     r11, [rsp+50h+var_s0]
0x140018968  mov     rbx, [r11+30h]
0x14001896c  mov     rsi, [r11+38h]
0x140018970  mov     rsp, r11
0x140018973  pop     r14
0x140018975  pop     rdi
0x140018976  pop     rbp
0x140018977  retn
```
