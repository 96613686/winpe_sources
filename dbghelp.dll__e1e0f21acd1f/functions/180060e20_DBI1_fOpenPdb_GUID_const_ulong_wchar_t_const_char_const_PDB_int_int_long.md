# DBI1::fOpenPdb(_GUID const &,ulong,wchar_t const *,char const *,PDB * *,int,int,long &)

- ea: `0x180060e20`
- end: `0x180061465`
- name: `?fOpenPdb@DBI1@@AEAAHAEBU_GUID@@KPEB_WPEBDPEAPEAUPDB@@HHAEAJ@Z`
- size: `1605`
- prototype: `__int64 __fastcall(DBI1 *__hidden this, const struct _GUID *, unsigned int, const wchar_t *, const char *, struct PDB **, int, int, int *)`
- caller_count: `2`
- callee_count: `16`
- tags: ``

## callers

- `0x180061470`
- `0x18006eed0`

## callees

- `0x180026980`
- `0x18002723e`
- `0x180029c40`
- `0x18002a050`
- `0x18002a270`
- `0x180031a80`
- `0x1800334b0`
- `0x180034730`
- `0x1800349c0`
- `0x180038b30`
- `0x180038b90`
- `0x180058250`
- `0x180060e20`
- `0x180168f90`
- `0x1801d6350`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180061043`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800613b6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180061043`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800613b6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180060ec8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180060ec8`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x1800612d1`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x1800612d1`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180061162`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180061253`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180061299`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180061162`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180061253`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180061299`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18006117b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18006117b`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180060fd0`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180060fd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DBI1::fOpenPdb(
        PDB1 **this,
        struct _GUID *a2,
        unsigned int a3,
        const wchar_t *a4,
        const char *a5,
        struct PDB **a6,
        int a7,
        int a8,
        int *a9)
{
  int v13; // eax
  PDB1 *v14; // rcx
  PSGSI1::EnumPubsByAddr *v15; // rbx
  PSGSI1::EnumPubsByAddr *v16; // rcx
  PSGSI1::EnumPubsByAddr *v17; // rbx
  PSGSI1::EnumPubsByAddr *v18; // rcx
  PSGSI1::EnumPubsByAddr *v19; // rbx
  PSGSI1::EnumPubsByAddr *v20; // rcx
  wchar_t *v22; // rbx
  wchar_t *v23; // rax
  wchar_t *v24; // rcx
  wchar_t *v25; // rdx
  PSGSI1::EnumPubsByAddr *v26; // rbx
  PSGSI1::EnumPubsByAddr *v27; // rcx
  __int64 v28; // r15
  unsigned __int64 v29; // rdx
  unsigned __int64 v30; // rdx
  char *v31; // rbx
  __int64 v32; // rax
  __int64 v33; // rax
  const wchar_t *v34; // rcx
  int v35; // ecx
  __int64 v36; // rax
  int v37; // r15d
  PSGSI1::EnumPubsByAddr *v38; // rbx
  PSGSI1::EnumPubsByAddr *v39; // rcx
  PSGSI1::EnumPubsByAddr *v40; // rbx
  PSGSI1::EnumPubsByAddr *v41; // rcx
  PSGSI1::EnumPubsByAddr *v42; // rbx
  PSGSI1::EnumPubsByAddr *v43; // rcx
  void **v44; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v45; // [rsp+68h] [rbp-98h]
  PSGSI1::EnumPubsByAddr *v46; // [rsp+70h] [rbp-90h]
  char v47[1032]; // [rsp+78h] [rbp-88h] BYREF
  char v48[2]; // [rsp+480h] [rbp+380h] BYREF
  char v49; // [rsp+482h] [rbp+382h]
  wchar_t v50[4]; // [rsp+488h] [rbp+388h] BYREF
  wchar_t Str[264]; // [rsp+490h] [rbp+390h] BYREF
  wchar_t FullPath[264]; // [rsp+6A0h] [rbp+5A0h] BYREF
  wchar_t Drive[264]; // [rsp+8B0h] [rbp+7B0h] BYREF
  wchar_t Dir[264]; // [rsp+AC0h] [rbp+9C0h] BYREF
  wchar_t Ext[256]; // [rsp+CD0h] [rbp+BD0h] BYREF
  wchar_t Filename[256]; // [rsp+ED0h] [rbp+DD0h] BYREF
  wchar_t v57[256]; // [rsp+10D0h] [rbp+FD0h] BYREF
  wchar_t v58[776]; // [rsp+12D0h] [rbp+11D0h] BYREF
  wchar_t v59[1024]; // [rsp+18E0h] [rbp+17E0h] BYREF

  *(_QWORD *)v50 = a5;
  v44 = &SafeStackAllocator<1024>::`vftable';
  v46 = 0;
  v45 = 0;
  *a6 = 0;
  PDB1::QueryPDBNameExW(this[18], FullPath, 0x104u);
  if ( !(unsigned int)_o__wcsnicmp(FullPath, a4, 260) )
  {
    v13 = IsEqualSig(a2, this[18]);
    v14 = this[18];
    if ( !v13 )
    {
      PDB1::setLastError(v14, 5, a4);
      v44 = &SafeStackAllocator<1024>::`vftable';
      v15 = v46;
      while ( v15 )
      {
        v16 = v15;
        v15 = *(PSGSI1::EnumPubsByAddr **)v15;
        PSGSI1::EnumPubsByAddr::release(v16);
      }
      return 0;
    }
    if ( a3 > PDB1::QueryAge(v14) )
    {
      PDB1::setLastError(this[18], 6, a4);
      v44 = &SafeStackAllocator<1024>::`vftable';
      v17 = v46;
      while ( v17 )
      {
        v18 = v17;
        v17 = *(PSGSI1::EnumPubsByAddr **)v17;
        PSGSI1::EnumPubsByAddr::release(v18);
      }
      return 0;
    }
    v44 = &SafeStackAllocator<1024>::`vftable';
    v19 = v46;
    if ( v46 )
    {
      do
      {
        v20 = v19;
        v19 = *(PSGSI1::EnumPubsByAddr **)v19;
        PSGSI1::EnumPubsByAddr::release(v20);
      }
      while ( v19 );
      return 1;
    }
    return 1;
  }
  _o_wcsncpy_s(Str, 260, a4, -1);
  if ( (unsigned int)IsEqualSig(a2, this[18]) && a3 <= PDB1::QueryAge(this[18]) )
  {
    v22 = wcsrchr_0(Str, 0x5Cu);
    v23 = wcsrchr_0(FullPath, 0x5Cu);
    v24 = Str;
    if ( v22 )
      v24 = v22;
    v25 = FullPath;
    if ( v23 )
      v25 = v23;
    if ( !(unsigned int)_o__wcsicmp(v24, v25) )
    {
      v44 = &SafeStackAllocator<1024>::`vftable';
      v26 = v46;
      while ( v26 )
      {
        v27 = v26;
        v26 = *(PSGSI1::EnumPubsByAddr **)v26;
        PSGSI1::EnumPubsByAddr::release(v27);
      }
      return 1;
    }
  }
  v28 = UnicodeLengthOfUTF8(a5);
  v29 = 2 * v28;
  if ( *v44 != SafeStackAllocator<1024>::AllocBytes )
  {
    v32 = ((__int64 (__fastcall *)(void ***, unsigned __int64))*v44)(&v44, v29);
    goto LABEL_30;
  }
  if ( v29 >= 0xFFFFFFFFFFFFFFF0uLL )
  {
    v32 = 0;
    goto LABEL_30;
  }
  v30 = (v29 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
  if ( 1024 - v45 < v30 )
  {
    v32 = SafeStackAllocator<528>::AllocInHeap(&v44);
LABEL_30:
    v31 = (char *)v32;
    goto LABEL_31;
  }
  v31 = &v47[v45];
  v45 += v30;
LABEL_31:
  if ( !v31 )
    goto LABEL_54;
  v33 = UTF8ToUnicode(*(_QWORD *)v50, v31, v28);
  v34 = 0;
  if ( v33 )
    v34 = (const wchar_t *)v31;
  if ( !v34 )
  {
LABEL_54:
    PDB1::setOOMError(this[18]);
    v44 = &SafeStackAllocator<1024>::`vftable';
    v42 = v46;
    while ( v42 )
    {
      v43 = v42;
      v42 = *(PSGSI1::EnumPubsByAddr **)v42;
      PSGSI1::EnumPubsByAddr::release(v43);
    }
    return 0;
  }
  Dir[0] = 0;
  Drive[0] = 0;
  _wsplitpath_s(v34, Drive, 0x107u, Dir, 0x104u, 0, 0, 0, 0);
  _o_wcscat_s(Drive, 263);
  *(_WORD *)v48 = 25458;
  v35 = *((_DWORD *)this + 456);
  if ( v35 )
    v49 = 98;
  v36 = (v35 != 0) + 2LL;
  if ( a8 )
  {
    v48[v36] = 88;
    v36 = (v35 != 0) + 3LL;
  }
  v48[v36] = 0;
  if ( !(unsigned int)PDB1::OpenTSPdb(Str, Drive, v48, a2, a3, a7, a9, v59, 0x400u, a6) )
  {
    v37 = *a9;
    _wsplitpath_s(FullPath, v50, 3u, v57, 0x100u, 0, 0, 0, 0);
    _wsplitpath_s(Str, 0, 0, 0, 0, Filename, 0x100u, Ext, 0x100u);
    _o__wmakepath_s(v58, 776, v50, v57, Filename, Ext);
    if ( !(unsigned int)PDB1::OpenTSPdb(v58, 0, v48, a2, a3, a7, a9, v59, 0x400u, a6) )
    {
      if ( a7 && *a9 == 4 && v37 != 4 && PDB1::FIsLinkerTempFile(Str) )
        *a9 = v37;
      PDB1::setLastError(this[18], *a9, v59);
      v44 = &SafeStackAllocator<1024>::`vftable';
      v38 = v46;
      while ( v38 )
      {
        v39 = v38;
        v38 = *(PSGSI1::EnumPubsByAddr **)v38;
        PSGSI1::EnumPubsByAddr::release(v39);
      }
      return 0;
    }
  }
  (*(void (__fastcall **)(_QWORD, wchar_t *, __int64))(*(_QWORD *)*a6 + 160LL))(*a6, Str, 260);
  if ( !(unsigned int)_o__wcsicmp(FullPath, Str) )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a6 + 88LL))(*a6);
    *a6 = 0;
  }
  v44 = &SafeStackAllocator<1024>::`vftable';
  v40 = v46;
  if ( !v46 )
    return 1;
  do
  {
    v41 = v40;
    v40 = *(PSGSI1::EnumPubsByAddr **)v40;
    PSGSI1::EnumPubsByAddr::release(v41);
  }
  while ( v40 );
  return 1;
}

```

## disassembly

```asm
0x180060e20  push    rbp
0x180060e22  push    rbx
0x180060e23  push    rsi
0x180060e24  push    rdi
0x180060e25  push    r12
0x180060e27  push    r13
0x180060e29  push    r14
0x180060e2b  push    r15
0x180060e2d  lea     rbp, [rsp-1FF8h]
0x180060e35  mov     eax, 20F8h
0x180060e3a  call    _alloca_probe
0x180060e3f  sub     rsp, rax
0x180060e42  mov     [rsp+2130h+var_20E0], 0FFFFFFFFFFFFFFFEh
0x180060e4b  mov     rax, cs:__security_cookie
0x180060e52  xor     rax, rsp
0x180060e55  mov     [rbp+2030h+var_50], rax
0x180060e5c  mov     rbx, r9
0x180060e5f  mov     r12d, r8d
0x180060e62  mov     r13, rdx
0x180060e65  mov     rdi, rcx
0x180060e68  mov     r15, [rbp+2030h+arg_20]
0x180060e6f  mov     qword ptr [rbp+2030h+var_1CA8], r15
0x180060e76  mov     r14, [rbp+2030h+arg_28]
0x180060e7d  mov     rsi, [rbp+2030h+arg_40]
0x180060e84  lea     rax, ??_7?$SafeStackAllocator@$0EAA@@@6B@; const SafeStackAllocator<1024>::`vftable'
0x180060e8b  mov     [rsp+2130h+var_20D0], rax
0x180060e90  xor     eax, eax
0x180060e92  mov     [rsp+2130h+var_20C0], rax
0x180060e97  mov     [rsp+2130h+var_20C8], rax
0x180060e9c  mov     [r14], rax
0x180060e9f  mov     r8d, 104h; unsigned __int64
0x180060ea5  lea     rdx, [rbp+2030h+FullPath]; wchar_t *
0x180060eac  mov     rcx, [rcx+90h]; this
0x180060eb3  call    ?QueryPDBNameExW@PDB1@@UEAAPEA_WPEA_W_K@Z; PDB1::QueryPDBNameExW(wchar_t *,unsigned __int64)
0x180060eb8  mov     r8d, 104h
0x180060ebe  mov     rdx, rbx
0x180060ec1  lea     rcx, [rbp+2030h+FullPath]
0x180060ec8  call    cs:__imp__o__wcsnicmp
0x180060ece  test    eax, eax
0x180060ed0  jnz     loc_180060FBA
0x180060ed6  mov     rdx, [rdi+90h]; struct PDB *
0x180060edd  mov     rcx, r13; struct _GUID *
0x180060ee0  call    ?IsEqualSig@@YAHAEBU_GUID@@PEAUPDB@@@Z; IsEqualSig(_GUID const &,PDB *)
0x180060ee5  mov     rcx, [rdi+90h]; this
0x180060eec  test    eax, eax
0x180060eee  jnz     short loc_180060F35
0x180060ef0  mov     r8, rbx; wchar_t *
0x180060ef3  mov     edx, 5; int
0x180060ef8  call    ?setLastError@PDB1@@QEAAXJPEB_W@Z; PDB1::setLastError(long,wchar_t const *)
0x180060efd  nop
0x180060efe  lea     rax, ??_7?$SafeStackAllocator@$0EAA@@@6B@; const SafeStackAllocator<1024>::`vftable'
0x180060f05  mov     [rsp+2130h+var_20D0], rax
0x180060f0a  mov     rbx, [rsp+2130h+var_20C0]
0x180060f0f  test    rbx, rbx
0x180060f12  jz      loc_180061440
0x180060f18  nop     dword ptr [rax+rax+00000000h]
0x180060f20  mov     rcx, rbx; this
0x180060f23  mov     rbx, [rbx]
0x180060f26  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x180060f2b  test    rbx, rbx
0x180060f2e  jnz     short loc_180060F20
0x180060f30  jmp     loc_180061440
0x180060f35  call    ?QueryAge@PDB1@@UEAAKXZ; PDB1::QueryAge(void)
0x180060f3a  cmp     r12d, eax
0x180060f3d  jbe     short loc_180060F85
0x180060f3f  mov     r8, rbx; wchar_t *
0x180060f42  mov     edx, 6; int
0x180060f47  mov     rcx, [rdi+90h]; this
0x180060f4e  call    ?setLastError@PDB1@@QEAAXJPEB_W@Z; PDB1::setLastError(long,wchar_t const *)
0x180060f53  nop
0x180060f54  lea     rax, ??_7?$SafeStackAllocator@$0EAA@@@6B@; const SafeStackAllocator<1024>::`vftable'
0x180060f5b  mov     [rsp+2130h+var_20D0], rax
0x180060f60  mov     rbx, [rsp+2130h+var_20C0]
0x180060f65  test    rbx, rbx
0x180060f68  jz      loc_180061440
0x180060f6e  xchg    ax, ax
0x180060f70  mov     rcx, rbx; this
0x180060f73  mov     rbx, [rbx]
0x180060f76  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x180060f7b  test    rbx, rbx
0x180060f7e  jnz     short loc_180060F70
0x180060f80  jmp     loc_180061440
0x180060f85  lea     rax, ??_7?$SafeStackAllocator@$0EAA@@@6B@; const SafeStackAllocator<1024>::`vftable'
0x180060f8c  mov     [rsp+2130h+var_20D0], rax
0x180060f91  mov     rbx, [rsp+2130h+var_20C0]
0x180060f96  test    rbx, rbx
0x180060f99  jz      loc_180061073
0x180060f9f  nop
0x180060fa0  mov     rcx, rbx; this
0x180060fa3  mov     rbx, [rbx]
0x180060fa6  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x180060fab  test    rbx, rbx
0x180060fae  jnz     short loc_180060FA0
0x180060fb0  mov     eax, 1
0x180060fb5  jmp     loc_180061442
0x180060fba  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180060fc1  mov     r8, rbx
0x180060fc4  mov     edx, 104h
0x180060fc9  lea     rcx, [rbp+2030h+Str]
0x180060fd0  call    cs:__imp__o_wcsncpy_s
0x180060fd6  mov     rdx, [rdi+90h]; struct PDB *
0x180060fdd  mov     rcx, r13; struct _GUID *
0x180060fe0  call    ?IsEqualSig@@YAHAEBU_GUID@@PEAUPDB@@@Z; IsEqualSig(_GUID const &,PDB *)
0x180060fe5  test    eax, eax
0x180060fe7  jz      loc_18006107D
0x180060fed  mov     rcx, [rdi+90h]; this
0x180060ff4  call    ?QueryAge@PDB1@@UEAAKXZ; PDB1::QueryAge(void)
0x180060ff9  cmp     r12d, eax
0x180060ffc  ja      loc_18006107D
0x180061002  mov     edx, 5Ch ; '\'; Ch
0x180061007  lea     rcx, [rbp+2030h+Str]; Str
0x18006100e  call    wcsrchr_0
0x180061013  mov     rbx, rax
0x180061016  mov     edx, 5Ch ; '\'; Ch
0x18006101b  lea     rcx, [rbp+2030h+FullPath]; Str
0x180061022  call    wcsrchr_0
0x180061027  lea     rcx, [rbp+2030h+Str]
0x18006102e  test    rbx, rbx
0x180061031  cmovnz  rcx, rbx
0x180061035  lea     rdx, [rbp+2030h+FullPath]
0x18006103c  test    rax, rax
0x18006103f  cmovnz  rdx, rax
0x180061043  call    cs:__imp__o__wcsicmp
0x180061049  test    eax, eax
0x18006104b  jnz     short loc_18006107D
0x18006104d  lea     rax, ??_7?$SafeStackAllocator@$0EAA@@@6B@; const SafeStackAllocator<1024>::`vftable'
0x180061054  mov     [rsp+2130h+var_20D0], rax
0x180061059  mov     rbx, [rsp+2130h+var_20C0]
0x18006105e  test    rbx, rbx
0x180061061  jz      short loc_180061073
0x180061063  mov     rcx, rbx; this
0x180061066  mov     rbx, [rbx]
0x180061069  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x18006106e  test    rbx, rbx
0x180061071  jnz     short loc_180061063
0x180061073  mov     eax, 1
0x180061078  jmp     loc_180061442
0x18006107d  mov     rcx, r15
0x180061080  call    UnicodeLengthOfUTF8
0x180061085  mov     r15, rax
0x180061088  mov     rcx, [rsp+2130h+var_20D0]
0x18006108d  mov     rax, [rcx]
0x180061090  lea     rdx, [r15+r15]
0x180061094  lea     rcx, ?AllocBytes@?$SafeStackAllocator@$0EAA@@@UEAAPEAX_K@Z; SafeStackAllocator<1024>::AllocBytes(unsigned __int64)
0x18006109b  cmp     rax, rcx
0x18006109e  jnz     short loc_1800610E2
0x1800610a0  cmp     rdx, 0FFFFFFFFFFFFFFF0h
0x1800610a4  jnb     short loc_1800610DE
0x1800610a6  add     rdx, 7
0x1800610aa  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800610ae  mov     eax, 400h
0x1800610b3  mov     rcx, [rsp+2130h+var_20C8]
0x1800610b8  sub     rax, rcx
0x1800610bb  cmp     rax, rdx
0x1800610be  jb      short loc_1800610D2
0x1800610c0  lea     rbx, [rsp+2130h+var_20B8]
0x1800610c5  add     rbx, rcx
0x1800610c8  add     rcx, rdx
0x1800610cb  mov     [rsp+2130h+var_20C8], rcx
0x1800610d0  jmp     short loc_1800610F0
0x1800610d2  lea     rcx, [rsp+2130h+var_20D0]
0x1800610d7  call    ?AllocInHeap@?$SafeStackAllocator@$0CBA@@@IEAAPEAX_K@Z; SafeStackAllocator<528>::AllocInHeap(unsigned __int64)
0x1800610dc  jmp     short loc_1800610ED
0x1800610de  xor     eax, eax
0x1800610e0  jmp     short loc_1800610ED
0x1800610e2  lea     rcx, [rsp+2130h+var_20D0]
0x1800610e7  call    cs:__guard_dispatch_icall_fptr
0x1800610ed  mov     rbx, rax
0x1800610f0  test    rbx, rbx
0x1800610f3  jz      loc_180061407
0x1800610f9  mov     r8, r15
0x1800610fc  mov     rdx, rbx
0x1800610ff  mov     rcx, qword ptr [rbp+2030h+var_1CA8]
0x180061106  call    UTF8ToUnicode
0x18006110b  xor     r15d, r15d
0x18006110e  mov     ecx, r15d
0x180061111  test    rax, rax
0x180061114  cmovnz  rcx, rbx; FullPath
0x180061118  test    rcx, rcx
0x18006111b  jz      loc_180061407
0x180061121  mov     [rbp+2030h+Dir], r15w
0x180061129  mov     [rbp+2030h+Drive], r15w
0x180061131  mov     [rsp+2130h+ExtCount], r15; ExtCount
0x180061136  mov     [rsp+2130h+Ext], r15; Ext
0x18006113b  mov     [rsp+2130h+FilenameCount], r15; FilenameCount
0x180061140  mov     [rsp+2130h+Filename], r15; Filename
0x180061145  mov     [rsp+2130h+DirCount], 104h; DirCount
0x18006114e  lea     r9, [rbp+2030h+Dir]; Dir
0x180061155  mov     r8d, 107h; DriveCount
0x18006115b  lea     rdx, [rbp+2030h+Drive]; Drive
0x180061162  call    cs:__imp__wsplitpath_s
0x180061168  lea     r8, [rbp+2030h+Dir]
0x18006116f  mov     edx, 107h
0x180061174  lea     rcx, [rbp+2030h+Drive]
0x18006117b  call    cs:__imp__o_wcscat_s
0x180061181  mov     word ptr [rbp+2030h+var_1CB0], 6372h
0x18006118a  mov     ecx, [rdi+720h]
0x180061190  test    ecx, ecx
0x180061192  jz      short loc_18006119B
0x180061194  mov     [rbp+2030h+var_1CAE], 62h ; 'b'
0x18006119b  mov     rax, r15
0x18006119e  test    ecx, ecx
0x1800611a0  setnz   al
0x1800611a3  add     rax, 2
0x1800611a7  cmp     [rbp+2030h+arg_38], r15d
0x1800611ae  jz      short loc_1800611BB
0x1800611b0  mov     [rbp+rax+2030h+var_1CB0], 58h ; 'X'
0x1800611b8  inc     rax
0x1800611bb  mov     [rbp+rax+2030h+var_1CB0], r15b
0x1800611c3  mov     [rsp+2130h+var_20E8], r14; struct PDB **
0x1800611c8  mov     [rsp+2130h+ExtCount], 400h; unsigned __int64
0x1800611d1  lea     rax, [rbp+2030h+var_850]
0x1800611d8  mov     [rsp+2130h+Ext], rax; wchar_t *
0x1800611dd  mov     [rsp+2130h+FilenameCount], rsi; int *
0x1800611e2  mov     ebx, [rbp+2030h+arg_30]
0x1800611e8  mov     dword ptr [rsp+2130h+Filename], ebx; int
0x1800611ec  mov     dword ptr [rsp+2130h+DirCount], r12d; unsigned int
0x1800611f1  mov     r9, r13; struct _GUID *
0x1800611f4  lea     r8, [rbp+2030h+var_1CB0]; char *
0x1800611fb  lea     rdx, [rbp+2030h+Drive]; wchar_t *
0x180061202  lea     rcx, [rbp+2030h+Str]; wchar_t *
0x180061209  call    ?OpenTSPdb@PDB1@@SAHPEB_W0PEBDAEBU_GUID@@KHPEAJPEA_W_KPEAPEAUPDB@@@Z; PDB1::OpenTSPdb(wchar_t const *,wchar_t const *,char const *,_GUID const &,ulong,int,long *,wchar_t *,unsigned __int64,PDB * *)
0x18006120e  test    eax, eax
0x180061210  jnz     loc_180061388
0x180061216  mov     r15d, [rsi]
0x180061219  xor     eax, eax
0x18006121b  mov     [rsp+2130h+ExtCount], rax; ExtCount
0x180061220  mov     [rsp+2130h+Ext], rax; Ext
0x180061225  mov     [rsp+2130h+FilenameCount], rax; FilenameCount
0x18006122a  mov     [rsp+2130h+Filename], rax; Filename
0x18006122f  mov     [rsp+2130h+DirCount], 100h; DirCount
0x180061238  lea     r9, [rbp+2030h+var_1060]; Dir
0x18006123f  mov     r8d, 3; DriveCount
0x180061245  lea     rdx, [rbp+2030h+var_1CA8]; Drive
0x18006124c  lea     rcx, [rbp+2030h+FullPath]; FullPath
0x180061253  call    cs:__imp__wsplitpath_s
0x180061259  mov     [rsp+2130h+ExtCount], 100h; ExtCount
0x180061262  lea     rax, [rbp+2030h+var_1460]
0x180061269  mov     [rsp+2130h+Ext], rax; Ext
0x18006126e  mov     [rsp+2130h+FilenameCount], 100h; FilenameCount
0x180061277  lea     rax, [rbp+2030h+var_1260]
0x18006127e  mov     [rsp+2130h+Filename], rax; Filename
0x180061283  xor     eax, eax
0x180061285  mov     [rsp+2130h+DirCount], rax; DirCount
0x18006128a  xor     r9d, r9d; Dir
0x18006128d  xor     r8d, r8d; DriveCount
0x180061290  xor     edx, edx; Drive
0x180061292  lea     rcx, [rbp+2030h+Str]; FullPath
0x180061299  call    cs:__imp__wsplitpath_s
0x18006129f  lea     rax, [rbp+2030h+var_1460]
0x1800612a6  mov     [rsp+2130h+Filename], rax
0x1800612ab  lea     rax, [rbp+2030h+var_1260]
0x1800612b2  mov     [rsp+2130h+DirCount], rax
0x1800612b7  lea     r9, [rbp+2030h+var_1060]
0x1800612be  lea     r8, [rbp+2030h+var_1CA8]
0x1800612c5  mov     edx, 308h
0x1800612ca  lea     rcx, [rbp+2030h+var_E60]
0x1800612d1  call    cs:__imp__o__wmakepath_s
0x1800612d7  mov     [rsp+2130h+var_20E8], r14; struct PDB **
0x1800612dc  mov     [rsp+2130h+ExtCount], 400h; unsigned __int64
0x1800612e5  lea     rax, [rbp+2030h+var_850]
0x1800612ec  mov     [rsp+2130h+Ext], rax; wchar_t *
0x1800612f1  mov     [rsp+2130h+FilenameCount], rsi; int *
0x1800612f6  mov     dword ptr [rsp+2130h+Filename], ebx; int
0x1800612fa  mov     dword ptr [rsp+2130h+DirCount], r12d; unsigned int
0x1800612ff  mov     r9, r13; struct _GUID *
0x180061302  lea     r8, [rbp+2030h+var_1CB0]; char *
0x180061309  xor     edx, edx; wchar_t *
0x18006130b  lea     rcx, [rbp+2030h+var_E60]; wchar_t *
0x180061312  call    ?OpenTSPdb@PDB1@@SAHPEB_W0PEBDAEBU_GUID@@KHPEAJPEA_W_KPEAPEAUPDB@@@Z; PDB1::OpenTSPdb(wchar_t const *,wchar_t const *,char const *,_GUID const &,ulong,int,long *,wchar_t *,unsigned __int64,PDB * *)
0x180061317  test    eax, eax
0x180061319  jnz     short loc_180061385
0x18006131b  test    ebx, ebx
0x18006131d  jz      short loc_18006133D
0x18006131f  cmp     dword ptr [rsi], 4
0x180061322  jnz     short loc_18006133D
0x180061324  cmp     r15d, 4
0x180061328  jz      short loc_18006133D
0x18006132a  lea     rcx, [rbp+2030h+Str]; wchar_t *
0x180061331  call    ?FIsLinkerTempFile@PDB1@@CA_NPEB_W@Z; PDB1::FIsLinkerTempFile(wchar_t const *)
0x180061336  test    al, al
0x180061338  jz      short loc_18006133D
0x18006133a  mov     [rsi], r15d
0x18006133d  lea     r8, [rbp+2030h+var_850]; wchar_t *
0x180061344  mov     edx, [rsi]; int
0x180061346  mov     rcx, [rdi+90h]; this
0x18006134d  call    ?setLastError@PDB1@@QEAAXJPEB_W@Z; PDB1::setLastError(long,wchar_t const *)
0x180061352  nop
0x180061353  lea     rax, ??_7?$SafeStackAllocator@$0EAA@@@6B@; const SafeStackAllocator<1024>::`vftable'
0x18006135a  mov     [rsp+2130h+var_20D0], rax
0x18006135f  mov     rbx, [rsp+2130h+var_20C0]
0x180061364  test    rbx, rbx
0x180061367  jz      loc_180061440
0x18006136d  nop     dword ptr [rax]
0x180061370  mov     rcx, rbx; this
0x180061373  mov     rbx, [rbx]
0x180061376  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x18006137b  test    rbx, rbx
0x18006137e  jnz     short loc_180061370
0x180061380  jmp     loc_180061440
  ... truncated ...
```
