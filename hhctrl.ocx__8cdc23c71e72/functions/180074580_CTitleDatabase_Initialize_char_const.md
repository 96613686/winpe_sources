# CTitleDatabase::Initialize(char const *)

- ea: `0x180074580`
- end: `0x1800749a8`
- name: `?Initialize@CTitleDatabase@@QEAAHPEBD@Z`
- size: `1064`
- prototype: `__int64 __fastcall(CTitleDatabase *__hidden this, const char *)`
- caller_count: `3`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003b9e4`
- `0x180072b54`
- `0x180074580`

## callees

- `0x180001710`
- `0x180001728`
- `0x180001768`
- `0x1800038f4`
- `0x1800095c8`
- `0x18000960c`
- `0x18000c02c`
- `0x18000d5bc`
- `0x1800139bc`
- `0x180028598`
- `0x18004f538`
- `0x18006080c`
- `0x180060980`
- `0x18006a7ac`
- `0x180073464`
- `0x180074580`
- `0x1800755fc`
- `0x1800756e0`
- `0x180078010`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x1800746d2`
- `KERNEL32!lstrlenW` at `0x1800746d2`
- `USER32!SetCursor` at `0x1800747ad`
- `USER32!SetCursor` at `0x180074980`
- `USER32!SetCursor` at `0x18007498f`
- `USER32!SetCursor` at `0x1800747ad`
- `USER32!SetCursor` at `0x180074980`
- `USER32!SetCursor` at `0x18007498f`
- `ole32!CoCreateInstance` at `0x1800747dc`
- `ole32!CoCreateInstance` at `0x1800747dc`

## string_xrefs

- `0x180074867`: `$WWKeywordLinks\Data`
- `0x1800748f8`: `$WWAssociativeLinks\Data`
- `0x18007494b`: `AssociativeLinks`
- `0x1800748ba`: `KeywordLinks`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTitleDatabase::Initialize(CTitleDatabase *this, const char *a2)
{
  CExCollection *v4; // rcx
  int v5; // r14d
  BYTE *LocalStoragePathname; // rax
  CExTitle *v7; // rcx
  _BYTE *v8; // rax
  __int64 v9; // rcx
  int v10; // ebp
  unsigned __int64 v11; // rsi
  WCHAR *v12; // rax
  int v13; // r9d
  WCHAR *v14; // rdi
  char *v15; // rax
  char *v16; // rbp
  const unsigned __int16 **v17; // rsi
  const WCHAR *v18; // rcx
  unsigned __int64 v19; // r12
  unsigned __int16 *v20; // rax
  CHAR *v21; // rax
  unsigned int v22; // ebx
  unsigned int v23; // ebp
  CTitleInformation *v24; // rdi
  CExTitle *v25; // rcx
  CTitleInformation *Info; // rax
  _DWORD *v27; // rax
  _DWORD *v28; // rax
  HCURSOR hCursor; // [rsp+40h] [rbp-58h] BYREF
  _DWORD *v30; // [rsp+48h] [rbp-50h]

  if ( *(_DWORD *)this )
    return 1;
  if ( !*((_QWORD *)this + 36) && !*((_QWORD *)this + 37) && !*((_QWORD *)this + 1) && !*((_QWORD *)this + 2) )
    return 0;
  CHourGlass::CHourGlass((CHourGlass *)&hCursor);
  v4 = (CExCollection *)*((_QWORD *)this + 36);
  v5 = 1;
  if ( v4 )
  {
    *((_QWORD *)this + 37) = *((_QWORD *)v4 + 135);
    *((_DWORD *)this + 78) = 1;
    LocalStoragePathname = CExCollection::GetLocalStoragePathname(v4, ".chw");
LABEL_11:
    *((_QWORD *)this + 2) = LocalStoragePathname;
    goto LABEL_12;
  }
  v7 = (CExTitle *)*((_QWORD *)this + 37);
  if ( v7 )
  {
    LocalStoragePathname = (BYTE *)CExTitle::GetIndexFileName(v7);
    goto LABEL_11;
  }
LABEL_12:
  v8 = (_BYTE *)*((_QWORD *)this + 2);
  if ( v8 && *v8 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    v10 = v9 + 1;
    v11 = (unsigned int)(v9 + 1);
    v12 = (WCHAR *)operator new[](saturated_mul(v11, 2u));
    v14 = v12;
    if ( v12 )
    {
      HHMultiByteToWideChar(0, 0, *((const char **)this + 2), v13, v12, v10);
      v15 = (char *)operator new[]((unsigned int)v11);
      v16 = v15;
      if ( !v15 )
      {
        operator delete[](v14);
        OOM();
      }
      StringCchCopyA(v15, v11, *((const char **)this + 2));
      v17 = (const unsigned __int16 **)((char *)this + 8);
      goto LABEL_27;
    }
LABEL_23:
    OOM();
  }
  v14 = 0;
  v16 = 0;
  v17 = (const unsigned __int16 **)((char *)this + 8);
  v18 = (const WCHAR *)*((_QWORD *)this + 1);
  if ( !v18 || !*v18 )
    goto LABEL_27;
  v19 = (unsigned int)(lstrlenW(v18) + 1);
  v20 = (unsigned __int16 *)operator new[](saturated_mul(v19, 2u));
  v14 = v20;
  if ( !v20 )
    goto LABEL_23;
  StringCchCopyW(v20, v19, *v17);
  v21 = (CHAR *)operator new[](v19);
  v16 = v21;
  if ( !v21 )
  {
    operator delete[](v14);
    OOM();
  }
  HHWideCharToMultiByte(0, 0, *v17, -1, v21, v19, 0, 0);
LABEL_27:
  *v17 = v14;
  *((_QWORD *)this + 2) = v16;
  if ( !v14 || !*v14 )
  {
    SetCursor(hCursor);
    return 0;
  }
  if ( *((_DWORD *)this + 78) && !(unsigned int)CTitleDatabase::MergeWordWheels(this) )
  {
    *((_DWORD *)this + 78) = 0;
    *((_QWORD *)this + 36) = 0;
    CTitleDatabase::Free(this);
    v22 = CTitleDatabase::Initialize(this, 0);
    SetCursor(hCursor);
    return v22;
  }
  v23 = 0;
  if ( CoCreateInstance(&CLSID_IITDatabaseLocal, 0, 1u, &IID_IITDatabase, (LPVOID *)this + 38) >= 0 )
  {
    if ( (unsigned int)IsFile(*((const char **)this + 2)) )
    {
      v23 = 1;
      if ( (*(int (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, _QWORD))(**((_QWORD **)this + 38) + 24LL))(
             *((_QWORD *)this + 38),
             0,
             *v17,
             0) >= 0 )
        v23 = 1;
    }
  }
  v24 = 0;
  v25 = (CExTitle *)*((_QWORD *)this + 37);
  if ( !v25 || (Info = CExTitle::GetInfo(v25), (v24 = Info) == 0) )
  {
    if ( *((_QWORD *)this + 37) )
      goto LABEL_56;
    goto LABEL_42;
  }
  if ( !*((_QWORD *)this + 37) )
    goto LABEL_43;
  CTitleInformation::Init(Info);
  if ( !*((_DWORD *)v24 + 7) )
  {
LABEL_42:
    if ( *((_QWORD *)this + 37) )
      goto LABEL_49;
LABEL_43:
    if ( !(unsigned int)IsSubFile(*((const char **)this + 2), "$WWKeywordLinks\\Data") )
      goto LABEL_48;
  }
  v27 = operator new(0xC10u);
  v30 = v27;
  if ( v27 )
  {
    v27[14] = -1;
    v27[766] = -1;
    *((_QWORD *)v27 + 384) = 0;
    v27[8] = 0;
    *((_QWORD *)v27 + 5) = 0;
    v27[770] = -1;
    *((_QWORD *)v27 + 2) = 0;
    *((_QWORD *)v27 + 1) = 0;
    *v27 = 0;
    *((_QWORD *)v27 + 6) = this;
    *((_QWORD *)v27 + 3) = "KeywordLinks";
    v27[771] = 0;
  }
  else
  {
    v27 = 0;
  }
  *((_QWORD *)this + 41) = v27;
LABEL_48:
  if ( !*((_QWORD *)this + 37) )
  {
LABEL_51:
    if ( (unsigned int)IsSubFile(*((const char **)this + 2), "$WWAssociativeLinks\\Data") )
      goto LABEL_52;
    goto LABEL_56;
  }
LABEL_49:
  CTitleInformation::Init(v24);
  if ( *((_DWORD *)v24 + 8) )
  {
LABEL_52:
    v28 = operator new(0xC10u);
    v30 = v28;
    if ( v28 )
    {
      v28[14] = -1;
      v28[766] = -1;
      *((_QWORD *)v28 + 384) = 0;
      v28[8] = 0;
      *((_QWORD *)v28 + 5) = 0;
      v28[770] = -1;
      *((_QWORD *)v28 + 2) = 0;
      *((_QWORD *)v28 + 1) = 0;
      *v28 = 0;
      *((_QWORD *)v28 + 6) = this;
      *((_QWORD *)v28 + 3) = "AssociativeLinks";
      v28[771] = 0;
    }
    else
    {
      v28 = 0;
    }
    *((_QWORD *)this + 42) = v28;
    goto LABEL_56;
  }
  if ( !*((_QWORD *)this + 37) )
    goto LABEL_51;
LABEL_56:
  if ( !v23 )
  {
    CTitleDatabase::Free(this);
    v5 = 0;
  }
  *(_DWORD *)this = v5;
  SetCursor(hCursor);
  return v23;
}

```

## disassembly

```asm
0x180074580  push    rbx
0x180074582  push    rbp
0x180074583  push    rsi
0x180074584  push    rdi
0x180074585  push    r12
0x180074587  push    r13
0x180074589  push    r14
0x18007458b  push    r15
0x18007458d  sub     rsp, 58h
0x180074591  mov     rbx, rcx
0x180074594  xor     r13d, r13d
0x180074597  cmp     [rcx], r13d
0x18007459a  jz      short loc_1800745A5
0x18007459c  lea     eax, [r13+1]
0x1800745a0  jmp     loc_180074997
0x1800745a5  cmp     [rcx+120h], r13
0x1800745ac  jnz     short loc_1800745C7
0x1800745ae  cmp     [rcx+128h], r13
0x1800745b5  jnz     short loc_1800745C7
0x1800745b7  cmp     [rcx+8], r13
0x1800745bb  jnz     short loc_1800745C7
0x1800745bd  cmp     [rcx+10h], r13
0x1800745c1  jz      loc_180074995
0x1800745c7  lea     rcx, [rsp+98h+hCursor]; this
0x1800745cc  call    ??0CHourGlass@@QEAA@XZ; CHourGlass::CHourGlass(void)
0x1800745d1  nop
0x1800745d2  mov     rcx, [rbx+120h]; this
0x1800745d9  mov     r14d, 1
0x1800745df  test    rcx, rcx
0x1800745e2  jz      short loc_180074607
0x1800745e4  mov     rax, [rcx+438h]
0x1800745eb  mov     [rbx+128h], rax
0x1800745f2  mov     [rbx+138h], r14d
0x1800745f9  lea     rdx, aChw; ".chw"
0x180074600  call    ?GetLocalStoragePathname@CExCollection@@QEAAPEBDPEBD@Z; CExCollection::GetLocalStoragePathname(char const *)
0x180074605  jmp     short loc_180074618
0x180074607  mov     rcx, [rbx+128h]; this
0x18007460e  test    rcx, rcx
0x180074611  jz      short loc_18007461C
0x180074613  call    ?GetIndexFileName@CExTitle@@QEAAPEBDXZ; CExTitle::GetIndexFileName(void)
0x180074618  mov     [rbx+10h], rax
0x18007461c  mov     rax, [rbx+10h]
0x180074620  test    rax, rax
0x180074623  jz      loc_1800746B2
0x180074629  cmp     [rax], r13b
0x18007462c  jz      loc_1800746B2
0x180074632  or      r15, 0FFFFFFFFFFFFFFFFh
0x180074636  mov     rcx, r15
0x180074639  inc     rcx
0x18007463c  cmp     [rax+rcx], r13b
0x180074640  jnz     short loc_180074639
0x180074642  lea     ebp, [rcx+1]
0x180074645  mov     esi, ebp
0x180074647  mov     eax, 2
0x18007464c  mul     rsi
0x18007464f  cmovb   rax, r15
0x180074653  mov     rcx, rax; unsigned __int64
0x180074656  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007465b  mov     rdi, rax
0x18007465e  test    rax, rax
0x180074661  jz      loc_180074702
0x180074667  mov     [rsp+98h+var_70], ebp; int
0x18007466b  mov     [rsp+98h+ppv], rax; LPWSTR
0x180074670  mov     r8, [rbx+10h]; char *
0x180074674  xor     edx, edx; unsigned int
0x180074676  xor     ecx, ecx; unsigned int
0x180074678  call    ?HHMultiByteToWideChar@@YAHIKPEBDHPEAGH@Z; HHMultiByteToWideChar(uint,ulong,char const *,int,ushort *,int)
0x18007467d  mov     ecx, esi; unsigned __int64
0x18007467f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180074684  mov     rbp, rax
0x180074687  test    rax, rax
0x18007468a  jnz     short loc_18007469A
0x18007468c  mov     rcx, rdi; void *
0x18007468f  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180074694  call    ?OOM@@YAXXZ; OOM(void)
0x18007469a  mov     r8, [rbx+10h]; char *
0x18007469e  mov     rdx, rsi; unsigned __int64
0x1800746a1  mov     rcx, rax; char *
0x1800746a4  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800746a9  lea     rsi, [rbx+8]
0x1800746ad  jmp     loc_180074757
0x1800746b2  mov     rdi, r13
0x1800746b5  mov     rbp, r13
0x1800746b8  lea     rsi, [rbx+8]
0x1800746bc  mov     rcx, [rsi]; lpString
0x1800746bf  test    rcx, rcx
0x1800746c2  jz      loc_180074757
0x1800746c8  cmp     [rcx], r13w
0x1800746cc  jz      loc_180074757
0x1800746d2  call    cs:__imp_lstrlenW
0x1800746d8  lea     r12d, [rax+1]
0x1800746dc  mov     ebp, r12d
0x1800746df  mov     eax, 2
0x1800746e4  mul     rbp
0x1800746e7  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1800746ee  cmovb   rax, r15
0x1800746f2  mov     rcx, rax; unsigned __int64
0x1800746f5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800746fa  mov     rdi, rax
0x1800746fd  test    rax, rax
0x180074700  jnz     short loc_180074708
0x180074702  call    ?OOM@@YAXXZ; OOM(void)
0x180074708  mov     r8, [rsi]; unsigned __int16 *
0x18007470b  mov     rdx, rbp; unsigned __int64
0x18007470e  mov     rcx, rdi; unsigned __int16 *
0x180074711  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180074716  mov     rcx, rbp; unsigned __int64
0x180074719  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007471e  mov     rbp, rax
0x180074721  test    rax, rax
0x180074724  jnz     short loc_180074734
0x180074726  mov     rcx, rdi; void *
0x180074729  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18007472e  call    ?OOM@@YAXXZ; OOM(void)
0x180074734  mov     [rsp+98h+var_60], r13; LPBOOL
0x180074739  mov     [rsp+98h+var_68], r13; LPCCH
0x18007473e  mov     [rsp+98h+var_70], r12d; int
0x180074743  mov     [rsp+98h+ppv], rax; LPSTR
0x180074748  mov     r9d, r15d; int
0x18007474b  mov     r8, [rsi]; unsigned __int16 *
0x18007474e  xor     edx, edx; unsigned int
0x180074750  xor     ecx, ecx; unsigned int
0x180074752  call    ?HHWideCharToMultiByte@@YAHIKPEBGHPEADHPEBDPEAH@Z; HHWideCharToMultiByte(uint,ulong,ushort const *,int,char *,int,char const *,int *)
0x180074757  mov     [rsi], rdi
0x18007475a  mov     [rbx+10h], rbp
0x18007475e  test    rdi, rdi
0x180074761  jz      loc_18007498A
0x180074767  cmp     [rdi], r13w
0x18007476b  jz      loc_18007498A
0x180074771  cmp     [rbx+138h], r13d
0x180074778  jz      short loc_1800747BA
0x18007477a  mov     rcx, rbx; this
0x18007477d  call    ?MergeWordWheels@CTitleDatabase@@QEAAHXZ; CTitleDatabase::MergeWordWheels(void)
0x180074782  test    eax, eax
0x180074784  jnz     short loc_1800747BA
0x180074786  mov     [rbx+138h], r13d
0x18007478d  mov     [rbx+120h], r13
0x180074794  mov     rcx, rbx; this
0x180074797  call    ?Free@CTitleDatabase@@QEAAHXZ; CTitleDatabase::Free(void)
0x18007479c  xor     edx, edx; char *
0x18007479e  mov     rcx, rbx; this
0x1800747a1  call    ?Initialize@CTitleDatabase@@QEAAHPEBD@Z; CTitleDatabase::Initialize(char const *)
0x1800747a6  mov     ebx, eax
0x1800747a8  mov     rcx, [rsp+98h+hCursor]; hCursor
0x1800747ad  call    cs:__imp_SetCursor
0x1800747b3  mov     eax, ebx
0x1800747b5  jmp     loc_180074997
0x1800747ba  mov     ebp, r13d
0x1800747bd  lea     rdi, [rbx+130h]
0x1800747c4  mov     [rsp+98h+ppv], rdi; ppv
0x1800747c9  lea     r9, IID_IITDatabase; riid
0x1800747d0  mov     r8d, r14d; dwClsContext
0x1800747d3  xor     edx, edx; pUnkOuter
0x1800747d5  lea     rcx, CLSID_IITDatabaseLocal; rclsid
0x1800747dc  call    cs:__imp_CoCreateInstance
0x1800747e2  test    eax, eax
0x1800747e4  js      short loc_180074813
0x1800747e6  mov     rcx, [rbx+10h]; char *
0x1800747ea  call    ?IsFile@@YAHPEBD@Z; IsFile(char const *)
0x1800747ef  test    eax, eax
0x1800747f1  jz      short loc_180074813
0x1800747f3  mov     ebp, r14d
0x1800747f6  mov     rcx, [rdi]
0x1800747f9  mov     rax, [rcx]
0x1800747fc  xor     r9d, r9d
0x1800747ff  mov     r8, [rsi]
0x180074802  xor     edx, edx
0x180074804  mov     rax, [rax+18h]
0x180074808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007480d  test    eax, eax
0x18007480f  cmovns  ebp, r14d
0x180074813  mov     rdi, r13
0x180074816  mov     rcx, [rbx+128h]; this
0x18007481d  mov     r15d, 0C10h
0x180074823  or      esi, 0FFFFFFFFh
0x180074826  test    rcx, rcx
0x180074829  jz      short loc_180074851
0x18007482b  call    ?GetInfo@CExTitle@@QEAAPEAVCTitleInformation@@XZ; CExTitle::GetInfo(void)
0x180074830  mov     rdi, rax
0x180074833  test    rax, rax
0x180074836  jz      short loc_180074851
0x180074838  cmp     [rbx+128h], r13
0x18007483f  jz      short loc_180074867
0x180074841  mov     rcx, rax; this
0x180074844  call    ?Init@CTitleInformation@@AEAAHXZ; CTitleInformation::Init(void)
0x180074849  cmp     [rdi+1Ch], r13d
0x18007484d  jnz     short loc_18007487B
0x18007484f  jmp     short loc_18007485E
0x180074851  cmp     [rbx+128h], r13
0x180074858  jnz     loc_180074969
0x18007485e  cmp     [rbx+128h], r13
0x180074865  jnz     short loc_1800748E1
0x180074867  lea     rdx, aWwkeywordlinks; "$WWKeywordLinks\\Data"
0x18007486e  mov     rcx, [rbx+10h]; char *
0x180074872  call    ?IsSubFile@@YAHPEBD0@Z; IsSubFile(char const *,char const *)
0x180074877  test    eax, eax
0x180074879  jz      short loc_1800748D8
0x18007487b  mov     rcx, r15; Size
0x18007487e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180074883  mov     [rsp+98h+var_50], rax
0x180074888  test    rax, rax
0x18007488b  jz      short loc_1800748CE
0x18007488d  mov     [rax+38h], esi
0x180074890  mov     [rax+0BF8h], esi
0x180074896  mov     [rax+0C00h], r13
0x18007489d  mov     [rax+20h], r13d
0x1800748a1  mov     [rax+28h], r13
0x1800748a5  mov     [rax+0C08h], esi
0x1800748ab  mov     [rax+10h], r13
0x1800748af  mov     [rax+8], r13
0x1800748b3  mov     [rax], r13d
0x1800748b6  mov     [rax+30h], rbx
0x1800748ba  lea     rcx, aKeywordlinks_0; "KeywordLinks"
0x1800748c1  mov     [rax+18h], rcx
0x1800748c5  mov     [rax+0C0Ch], r13d
0x1800748cc  jmp     short loc_1800748D1
0x1800748ce  mov     rax, r13
0x1800748d1  mov     [rbx+148h], rax
0x1800748d8  cmp     [rbx+128h], r13
0x1800748df  jz      short loc_1800748F8
0x1800748e1  mov     rcx, rdi; this
0x1800748e4  call    ?Init@CTitleInformation@@AEAAHXZ; CTitleInformation::Init(void)
0x1800748e9  cmp     [rdi+20h], r13d
0x1800748ed  jnz     short loc_18007490C
0x1800748ef  cmp     [rbx+128h], r13
0x1800748f6  jnz     short loc_180074969
0x1800748f8  lea     rdx, aWwassociativel; "$WWAssociativeLinks\\Data"
0x1800748ff  mov     rcx, [rbx+10h]; char *
0x180074903  call    ?IsSubFile@@YAHPEBD0@Z; IsSubFile(char const *,char const *)
0x180074908  test    eax, eax
0x18007490a  jz      short loc_180074969
0x18007490c  mov     rcx, r15; Size
0x18007490f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180074914  mov     [rsp+98h+var_50], rax
0x180074919  test    rax, rax
0x18007491c  jz      short loc_18007495F
0x18007491e  mov     [rax+38h], esi
0x180074921  mov     [rax+0BF8h], esi
0x180074927  mov     [rax+0C00h], r13
0x18007492e  mov     [rax+20h], r13d
0x180074932  mov     [rax+28h], r13
0x180074936  mov     [rax+0C08h], esi
0x18007493c  mov     [rax+10h], r13
0x180074940  mov     [rax+8], r13
0x180074944  mov     [rax], r13d
0x180074947  mov     [rax+30h], rbx
0x18007494b  lea     rcx, aAssociativelin_0; "AssociativeLinks"
0x180074952  mov     [rax+18h], rcx
0x180074956  mov     [rax+0C0Ch], r13d
0x18007495d  jmp     short loc_180074962
0x18007495f  mov     rax, r13
0x180074962  mov     [rbx+150h], rax
0x180074969  test    ebp, ebp
0x18007496b  jnz     short loc_180074978
0x18007496d  mov     rcx, rbx; this
0x180074970  call    ?Free@CTitleDatabase@@QEAAHXZ; CTitleDatabase::Free(void)
0x180074975  mov     r14d, r13d
0x180074978  mov     [rbx], r14d
0x18007497b  mov     rcx, [rsp+98h+hCursor]; hCursor
0x180074980  call    cs:__imp_SetCursor
0x180074986  mov     eax, ebp
0x180074988  jmp     short loc_180074997
0x18007498a  mov     rcx, [rsp+98h+hCursor]; hCursor
0x18007498f  call    cs:__imp_SetCursor
0x180074995  xor     eax, eax
0x180074997  add     rsp, 58h
0x18007499b  pop     r15
0x18007499d  pop     r14
0x18007499f  pop     r13
0x1800749a1  pop     r12
0x1800749a3  pop     rdi
0x1800749a4  pop     rsi
0x1800749a5  pop     rbp
0x1800749a6  pop     rbx
0x1800749a7  retn
```
