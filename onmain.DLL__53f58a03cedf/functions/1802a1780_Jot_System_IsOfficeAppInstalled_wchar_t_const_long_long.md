# Jot::System::IsOfficeAppInstalled(wchar_t const *,long,long *)

- ea: `0x1802a1780`
- end: `0x1802a1b07`
- name: `?IsOfficeAppInstalled@System@Jot@@YA_NPEB_WJPEAJ@Z`
- size: `903`
- prototype: `bool __fastcall(Jot::System *__hidden this, const wchar_t *, int, int *)`
- caller_count: `4`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1802a2670`
- `0x1806e3b90`
- `0x18086f6b8`
- `0x180cc6c60`

## callees

- `0x180067080`
- `0x180141980`
- `0x180232e00`
- `0x1802a1780`
- `0x1802a1b10`
- `0x1802a2c40`
- `0x1802e5170`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802a18ec`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802a1a78`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802a18ec`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802a1a78`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x1802a1827`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x1802a184c`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x1802a1827`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x1802a184c`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x1802a18be`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x1802a18be`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x1802a189f`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x1802a189f`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1802a18fe`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1802a19a7`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1802a19e4`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1802a1a1c`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1802a1a88`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1802a1ac0`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1802a18fe`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1802a19a7`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1802a19e4`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1802a1a1c`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1802a1a88`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x1802a1ac0`

## pseudocode

```c
char __fastcall Jot::System::IsOfficeAppInstalled(Jot::System *this, const wchar_t *a2, int *a3, int *a4)
{
  int v5; // esi
  __int64 v6; // rbx
  unsigned __int64 v7; // r9
  char v8; // di
  const wchar_t *v9; // rdx
  wchar_t *i; // r9
  int v11; // eax
  __int64 v12; // r9
  __int64 v13; // rbx
  int v14; // r9d
  int v15; // ecx
  __int64 v17; // rcx
  int v18[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h]
  _OWORD v21[2]; // [rsp+58h] [rbp-A8h] BYREF
  char v22; // [rsp+78h] [rbp-88h]
  __int128 v23; // [rsp+80h] [rbp-80h] BYREF
  __int64 v24; // [rsp+90h] [rbp-70h]
  _OWORD v25[2]; // [rsp+98h] [rbp-68h] BYREF
  char v26; // [rsp+B8h] [rbp-48h]
  __int128 v27; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v28; // [rsp+D0h] [rbp-30h]
  _OWORD v29[2]; // [rsp+D8h] [rbp-28h] BYREF
  char v30; // [rsp+F8h] [rbp-8h]
  _QWORD v31[2]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t v32[256]; // [rsp+110h] [rbp+10h] BYREF

  v28 = 0;
  v30 = 0;
  v26 = 0;
  v29[1] = (unsigned __int64)&v27;
  v5 = (int)a2;
  v24 = 0;
  v6 = -1;
  v7 = -1;
  v25[1] = (unsigned __int64)&v23;
  v27 = 0;
  v29[0] = 0;
  v23 = 0;
  v25[0] = 0;
  do
    ++v7;
  while ( *((_WORD *)this + v7) );
  if ( !this )
  {
    v17 = 508048474;
    goto LABEL_28;
  }
  if ( !v7 )
  {
    v17 = 508048473;
    goto LABEL_28;
  }
  DynamicMsorid::InitForKey((DynamicMsorid *)&v27, (const struct _msoreg *)&vmsoridHKCR, (const wchar_t *)this, v7);
  if ( !v30 )
  {
    v17 = 508048475;
LABEL_28:
    MsoShipAssertTagProc(v17);
    goto LABEL_29;
  }
  DynamicMsorid::InitForKey((DynamicMsorid *)&v23, (const struct _msoreg *)v29, L"CurVer", 6u);
  v22 = 0;
  v20 = 0;
  v21[1] = (unsigned __int64)&v19;
  v19 = 0;
  v21[0] = 0;
  if ( v26 )
  {
    v8 = 1;
    DynamicMsorid::InitForValue(&v19, v25, &WindowName, 0, 1);
    if ( MsoFRegReadWz((const struct _msoreg *)((unsigned __int64)v21 & -(__int64)(v22 != 0)), v32, 0x80u) && v32[0] )
    {
      do
        ++v6;
      while ( v32[v6] );
      for ( i = (wchar_t *)&v31[1] + (int)v6 + 3; i > v32 && *i != 46; --i )
        ;
      v11 = Ofc::CchWzLen((Ofc *)(i + 1), v9);
      v31[0] = Ofc::CVarStr::Init((const wchar_t *)(v12 + 2), v11);
      v18[0] = 0;
      v13 = v31[0];
      if ( Ofc::CStr::FStrToDecimalLong((Ofc::CStr *)v31, v18, 0, v14) )
      {
        v15 = v18[0];
        *a3 = v18[0];
        if ( v15 >= v5 )
        {
          Ofc::XString::Release((Ofc::XString *)(v13 - 12));
          if ( v22 )
          {
            MsoOrapiDeleteFromCache((const struct _msoreg *)v21);
            DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v19);
            DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v21);
            v22 = 0;
          }
          DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v21);
          DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v19);
          if ( v26 )
          {
            MsoOrapiDeleteFromCache((const struct _msoreg *)v25);
            DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v23);
            DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v25);
            v26 = 0;
          }
          DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v25);
          DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v23);
          if ( v30 )
          {
            MsoOrapiDeleteFromCache((const struct _msoreg *)v29);
            DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v27);
            DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v29);
            v30 = 0;
          }
          goto LABEL_26;
        }
      }
      Ofc::XString::Release((Ofc::XString *)(v13 - 12));
    }
  }
  else
  {
    MsoShipAssertTagProc(508048472);
  }
  if ( v22 )
  {
    MsoOrapiDeleteFromCache((const struct _msoreg *)v21);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v19);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v21);
    v22 = 0;
  }
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v21);
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v19);
LABEL_29:
  if ( v26 )
  {
    MsoOrapiDeleteFromCache((const struct _msoreg *)v25);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v23);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v25);
    v26 = 0;
  }
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v25);
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v23);
  if ( v30 )
  {
    MsoOrapiDeleteFromCache((const struct _msoreg *)v29);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v27);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v29);
    v30 = 0;
  }
  v8 = 0;
LABEL_26:
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)v29);
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v27);
  return v8;
}

```

## disassembly

```asm
0x1802a1780  mov     [rsp-8+arg_8], rbx
0x1802a1785  push    rbp
0x1802a1786  push    rsi
0x1802a1787  push    rdi
0x1802a1788  push    r14
0x1802a178a  push    r15
0x1802a178c  lea     rbp, [rsp-220h]
0x1802a1794  sub     rsp, 320h
0x1802a179b  mov     rax, cs:__security_cookie
0x1802a17a2  xor     rax, rsp
0x1802a17a5  mov     [rbp+240h+var_30], rax
0x1802a17ac  xor     eax, eax
0x1802a17ae  xorps   xmm1, xmm1
0x1802a17b1  mov     [rbp+240h+var_270], rax
0x1802a17b5  xor     r15d, r15d
0x1802a17b8  lea     rax, [rbp+240h+var_280]
0x1802a17bc  mov     [rbp+240h+var_248], r15b
0x1802a17c0  xorps   xmm0, xmm0
0x1802a17c3  mov     [rbp+240h+var_288], r15b
0x1802a17c7  movups  [rbp+240h+var_258], xmm1
0x1802a17cb  mov     qword ptr [rbp+240h+var_258], rax
0x1802a17cf  mov     r14, r8
0x1802a17d2  xor     eax, eax
0x1802a17d4  mov     esi, edx
0x1802a17d6  mov     [rbp+240h+var_2B0], rax
0x1802a17da  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1802a17de  lea     rax, [rbp+240h+var_2C0]
0x1802a17e2  mov     r9, rbx
0x1802a17e5  movups  [rbp+240h+var_298], xmm1
0x1802a17e9  mov     qword ptr [rbp+240h+var_298], rax
0x1802a17ed  movups  [rbp+240h+var_280], xmm0
0x1802a17f1  movups  [rbp+240h+var_268], xmm1
0x1802a17f5  movups  [rbp+240h+var_2C0], xmm0
0x1802a17f9  movups  [rbp+240h+var_2A8], xmm1
0x1802a17fd  inc     r9
0x1802a1800  cmp     [rcx+r9*2], r15w
0x1802a1805  jnz     short loc_1802A17FD
0x1802a1807  test    rcx, rcx
0x1802a180a  jz      loc_1802A1AF2
0x1802a1810  test    r9, r9
0x1802a1813  jz      loc_1802A1AFC
0x1802a1819  mov     r8, rcx
0x1802a181c  lea     rdx, ?vmsoridHKCR@@3U_msoreg@@B; _msoreg const vmsoridHKCR
0x1802a1823  lea     rcx, [rbp+240h+var_280]
0x1802a1827  call    cs:__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z; DynamicMsorid::InitForKey(_msoreg const &,wchar_t const *,unsigned __int64)
0x1802a182d  cmp     [rbp+240h+var_248], r15b
0x1802a1831  jz      loc_1802A1A73
0x1802a1837  mov     r9d, 6
0x1802a183d  lea     r8, aCurver; "CurVer"
0x1802a1844  lea     rdx, [rbp+240h+var_268]
0x1802a1848  lea     rcx, [rbp+240h+var_2C0]
0x1802a184c  call    cs:__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z; DynamicMsorid::InitForKey(_msoreg const &,wchar_t const *,unsigned __int64)
0x1802a1852  xor     eax, eax
0x1802a1854  mov     [rsp+340h+var_2C8], r15b
0x1802a1859  xorps   xmm1, xmm1
0x1802a185c  mov     [rsp+340h+var_2F0], rax
0x1802a1861  lea     rax, [rsp+340h+var_300]
0x1802a1866  xorps   xmm0, xmm0
0x1802a1869  movups  [rsp+340h+var_2D8], xmm1
0x1802a186e  mov     qword ptr [rsp+340h+var_2D8], rax
0x1802a1873  movups  [rsp+340h+var_300], xmm0
0x1802a1878  movups  [rsp+340h+var_2E8], xmm1
0x1802a187d  cmp     [rbp+240h+var_288], r15b
0x1802a1881  jz      short loc_1802A18E7
0x1802a1883  mov     edi, 1
0x1802a1888  lea     r8, WindowName
0x1802a188f  xor     r9d, r9d
0x1802a1892  mov     [rsp+340h+var_320], edi
0x1802a1896  lea     rdx, [rbp+240h+var_2A8]
0x1802a189a  lea     rcx, [rsp+340h+var_300]
0x1802a189f  call    cs:__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z; DynamicMsorid::InitForValue(_msoreg const &,wchar_t const *,unsigned __int64,RegValueType)
0x1802a18a5  mov     al, [rsp+340h+var_2C8]
0x1802a18a9  lea     r8d, [rdi+7Fh]
0x1802a18ad  neg     al
0x1802a18af  lea     rdx, [rbp+240h+var_230]
0x1802a18b3  lea     rax, [rsp+340h+var_2E8]
0x1802a18b8  sbb     rcx, rcx
0x1802a18bb  and     rcx, rax
0x1802a18be  call    cs:__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z; MsoFRegReadWz(_msoreg const *,wchar_t *,ulong)
0x1802a18c4  test    eax, eax
0x1802a18c6  jz      short loc_1802A18F2
0x1802a18c8  cmp     [rbp+240h+var_230], r15w
0x1802a18cd  jz      short loc_1802A18F2
0x1802a18cf  lea     rax, [rbp+240h+var_230]
0x1802a18d3  inc     rbx
0x1802a18d6  cmp     [rax+rbx*2], r15w
0x1802a18db  jnz     short loc_1802A18D3
0x1802a18dd  movsxd  rax, ebx
0x1802a18e0  lea     r9, [rbp+rax*2+240h+var_232]
0x1802a18e5  jmp     short loc_1802A1941
0x1802a18e7  mov     ecx, 1E483458h
0x1802a18ec  call    cs:__imp_MsoShipAssertTagProc
0x1802a18f2  cmp     [rsp+340h+var_2C8], r15b
0x1802a18f7  jz      short loc_1802A191D
0x1802a18f9  lea     rcx, [rsp+340h+var_2E8]
0x1802a18fe  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x1802a1904  lea     rcx, [rsp+340h+var_300]; this
0x1802a1909  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a190e  lea     rcx, [rsp+340h+var_2E8]; this
0x1802a1913  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a1918  mov     [rsp+340h+var_2C8], r15b
0x1802a191d  lea     rcx, [rsp+340h+var_2E8]; this
0x1802a1922  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a1927  lea     rcx, [rsp+340h+var_300]; this
0x1802a192c  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a1931  jmp     loc_1802A1A7E
0x1802a1936  cmp     word ptr [r9], 2Eh ; '.'
0x1802a193b  jz      short loc_1802A194A
0x1802a193d  sub     r9, 2
0x1802a1941  lea     rax, [rbp+240h+var_230]
0x1802a1945  cmp     r9, rax
0x1802a1948  ja      short loc_1802A1936
0x1802a194a  lea     rcx, [r9+2]; this
0x1802a194e  call    ?CchWzLen@Ofc@@YAHPEB_W@Z; Ofc::CchWzLen(wchar_t const *)
0x1802a1953  mov     edx, eax; int
0x1802a1955  lea     rcx, [r9+2]; Src
0x1802a1959  call    ?Init@CVarStr@Ofc@@CAPEA_WPEB_WH@Z; Ofc::CVarStr::Init(wchar_t const *,int)
0x1802a195e  xor     r8d, r8d; int
0x1802a1961  mov     [rbp+240h+var_240], rax
0x1802a1965  lea     rdx, [rsp+340h+var_310]; int *
0x1802a196a  mov     [rsp+340h+var_310], r15d
0x1802a196f  lea     rcx, [rbp+240h+var_240]; this
0x1802a1973  mov     rbx, rax
0x1802a1976  call    ?FStrToDecimalLong@CStr@Ofc@@QEBA_NAEAHHH@Z; Ofc::CStr::FStrToDecimalLong(int &,int,int)
0x1802a197b  test    al, al
0x1802a197d  jz      loc_1802A1AE4
0x1802a1983  mov     ecx, [rsp+340h+var_310]
0x1802a1987  mov     [r14], ecx
0x1802a198a  cmp     ecx, esi
0x1802a198c  jl      loc_1802A1AE4
0x1802a1992  lea     rcx, [rbx-0Ch]; this
0x1802a1996  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x1802a199b  cmp     [rsp+340h+var_2C8], r15b
0x1802a19a0  jz      short loc_1802A19C6
0x1802a19a2  lea     rcx, [rsp+340h+var_2E8]
0x1802a19a7  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x1802a19ad  lea     rcx, [rsp+340h+var_300]; this
0x1802a19b2  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a19b7  lea     rcx, [rsp+340h+var_2E8]; this
0x1802a19bc  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a19c1  mov     [rsp+340h+var_2C8], r15b
0x1802a19c6  lea     rcx, [rsp+340h+var_2E8]; this
0x1802a19cb  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a19d0  lea     rcx, [rsp+340h+var_300]; this
0x1802a19d5  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a19da  cmp     [rbp+240h+var_288], r15b
0x1802a19de  jz      short loc_1802A1A00
0x1802a19e0  lea     rcx, [rbp+240h+var_2A8]
0x1802a19e4  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x1802a19ea  lea     rcx, [rbp+240h+var_2C0]; this
0x1802a19ee  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a19f3  lea     rcx, [rbp+240h+var_2A8]; this
0x1802a19f7  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a19fc  mov     [rbp+240h+var_288], r15b
0x1802a1a00  lea     rcx, [rbp+240h+var_2A8]; this
0x1802a1a04  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a1a09  lea     rcx, [rbp+240h+var_2C0]; this
0x1802a1a0d  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a1a12  cmp     [rbp+240h+var_248], r15b
0x1802a1a16  jz      short loc_1802A1A38
0x1802a1a18  lea     rcx, [rbp+240h+var_268]
0x1802a1a1c  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x1802a1a22  lea     rcx, [rbp+240h+var_280]; this
0x1802a1a26  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a1a2b  lea     rcx, [rbp+240h+var_268]; this
0x1802a1a2f  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a1a34  mov     [rbp+240h+var_248], r15b
0x1802a1a38  lea     rcx, [rbp+240h+var_268]; this
0x1802a1a3c  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a1a41  lea     rcx, [rbp+240h+var_280]; this
0x1802a1a45  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a1a4a  mov     al, dil
0x1802a1a4d  mov     rcx, [rbp+240h+var_30]
0x1802a1a54  xor     rcx, rsp; StackCookie
0x1802a1a57  call    __security_check_cookie
0x1802a1a5c  mov     rbx, [rsp+340h+arg_8]
0x1802a1a64  add     rsp, 320h
0x1802a1a6b  pop     r15
0x1802a1a6d  pop     r14
0x1802a1a6f  pop     rdi
0x1802a1a70  pop     rsi
0x1802a1a71  pop     rbp
0x1802a1a72  retn
0x1802a1a73  mov     ecx, 1E48345Bh
0x1802a1a78  call    cs:__imp_MsoShipAssertTagProc
0x1802a1a7e  cmp     [rbp+240h+var_288], r15b
0x1802a1a82  jz      short loc_1802A1AA4
0x1802a1a84  lea     rcx, [rbp+240h+var_2A8]
0x1802a1a88  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x1802a1a8e  lea     rcx, [rbp+240h+var_2C0]; this
0x1802a1a92  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a1a97  lea     rcx, [rbp+240h+var_2A8]; this
0x1802a1a9b  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a1aa0  mov     [rbp+240h+var_288], r15b
0x1802a1aa4  lea     rcx, [rbp+240h+var_2A8]; this
0x1802a1aa8  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a1aad  lea     rcx, [rbp+240h+var_2C0]; this
0x1802a1ab1  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a1ab6  cmp     [rbp+240h+var_248], r15b
0x1802a1aba  jz      short loc_1802A1ADC
0x1802a1abc  lea     rcx, [rbp+240h+var_268]
0x1802a1ac0  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x1802a1ac6  lea     rcx, [rbp+240h+var_280]; this
0x1802a1aca  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a1acf  lea     rcx, [rbp+240h+var_268]; this
0x1802a1ad3  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x1802a1ad8  mov     [rbp+240h+var_248], r15b
0x1802a1adc  mov     dil, r15b
0x1802a1adf  jmp     loc_1802A1A38
0x1802a1ae4  lea     rcx, [rbx-0Ch]; this
0x1802a1ae8  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x1802a1aed  jmp     loc_1802A18F2
0x1802a1af2  mov     ecx, 1E48345Ah
0x1802a1af7  jmp     loc_1802A1A78
0x1802a1afc  mov     ecx, 1E483459h
0x1802a1b01  jmp     loc_1802A1A78
```
