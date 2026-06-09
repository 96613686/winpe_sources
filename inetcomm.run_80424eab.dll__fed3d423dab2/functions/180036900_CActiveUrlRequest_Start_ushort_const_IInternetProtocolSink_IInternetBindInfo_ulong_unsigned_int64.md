# CActiveUrlRequest::Start(ushort const *,IInternetProtocolSink *,IInternetBindInfo *,ulong,unsigned __int64)

- ea: `0x180036900`
- end: `0x180036c78`
- name: `?Start@CActiveUrlRequest@@UEAAJPEBGPEAUIInternetProtocolSink@@PEAUIInternetBindInfo@@K_K@Z`
- size: `888`
- prototype: `int(CActiveUrlRequest *__hidden this, const unsigned __int16 *, struct IInternetProtocolSink *, struct IInternetBindInfo *, unsigned int, unsigned __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002098`
- `0x180004d60`
- `0x180004f40`
- `0x180012590`
- `0x180015858`
- `0x180021a14`
- `0x1800359b8`
- `0x180036900`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!PszDupW` at `0x180036afd`
- `MSOERT2!PszDupW` at `0x180036afd`
- `MSOERT2!UlStripWhitespaceW` at `0x180036b44`
- `MSOERT2!UlStripWhitespaceW` at `0x180036b44`
- `SHLWAPI!PathFindExtensionW` at `0x180036b4d`
- `SHLWAPI!PathFindExtensionW` at `0x180036b4d`
- `KERNEL32!GetModuleHandleW` at `0x180036a81`
- `KERNEL32!GetModuleHandleW` at `0x180036a81`
- `KERNEL32!CompareStringW` at `0x180036a6b`
- `KERNEL32!CompareStringW` at `0x180036b7d`
- `KERNEL32!CompareStringW` at `0x180036ba6`
- `KERNEL32!CompareStringW` at `0x180036a6b`
- `KERNEL32!CompareStringW` at `0x180036b7d`
- `KERNEL32!CompareStringW` at `0x180036ba6`
- `urlmon!CoInternetCreateSecurityManager` at `0x180036aa4`
- `urlmon!CoInternetCreateSecurityManager` at `0x180036aa4`

## pseudocode

```c
__int64 __fastcall CActiveUrlRequest::Start(
        CActiveUrlRequest *this,
        const unsigned __int16 *a2,
        struct IInternetProtocolSink *a3,
        struct IInternetBindInfo *a4)
{
  const WCHAR *v8; // rdi
  int active; // ebx
  struct IInternetBindInfoVtbl *lpVtbl; // rax
  const WCHAR *v11; // rcx
  PCNZWCH *v12; // rsi
  WCHAR *i; // rcx
  const WCHAR *v14; // rax
  WCHAR v15; // ax
  const WCHAR *v16; // rcx
  const WCHAR *ExtensionW; // rbx
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+44h] [rbp-BCh] BYREF
  IInternetSecurityManager *ppSM; // [rsp+48h] [rbp-B8h] BYREF
  CActiveUrl *v22; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+58h] [rbp-A8h] BYREF
  PCWSTR psz1; // [rsp+60h] [rbp-A0h]
  int v25; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v26[124]; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned __int16 v27[264]; // [rsp+100h] [rbp+0h] BYREF

  v22 = 0;
  v19 = 0;
  memset_0(&v25, 0, 0x80u);
  STRW::STRW((STRW *)&v23, v27, 0x104u);
  if ( !a2 || !a3 || !a4 )
  {
    STRW::~STRW((STRW *)&v23);
    return 2147942487LL;
  }
  v8 = 0;
  active = STRW::Append((STRW *)&v23, a2);
  if ( active >= 0 )
  {
    memset_0(v26, 0, sizeof(v26));
    lpVtbl = a4->lpVtbl;
    v25 = 128;
    if ( ((int (__fastcall *)(struct IInternetBindInfo *, int *, int *))lpVtbl->GetBindInfo)(a4, &v19, &v25) >= 0
      && (v19 & 0x40) != 0 )
    {
      *((_DWORD *)this + 20) |= 4u;
    }
    *((_QWORD *)this + 4) = a3;
    ((void (__fastcall *)(struct IInternetProtocolSink *))a3->lpVtbl->AddRef)(a3);
    *((_QWORD *)this + 5) = a4;
    ((void (__fastcall *)(struct IInternetBindInfo *))a4->lpVtbl->AddRef)(a4);
    active = STRW::UrlUnescapeA((STRW *)&v23);
    if ( active >= 0 )
    {
      v11 = &cchOriginalDestLength;
      v12 = (PCNZWCH *)((char *)this + 56);
      if ( v23 )
        v11 = psz1;
      active = MimeOleParseMhtmlUrlW(v11);
      if ( active >= 0 )
      {
        if ( CompareStringW(0x7Fu, 1u, *v12, 4, L"mid:", 4) != 2 && GetModuleHandleW(L"IEXPLORE.EXE") )
        {
          ppSM = 0;
          v20 = 0;
          if ( !CoInternetCreateSecurityManager(0, &ppSM, 0) )
          {
            ((void (__fastcall *)(IInternetSecurityManager *, PCNZWCH, int *, _QWORD))ppSM->lpVtbl->MapUrlToZone)(
              ppSM,
              *v12,
              &v20,
              0);
            ((void (__fastcall *)(IInternetSecurityManager *))ppSM->lpVtbl->Release)(ppSM);
          }
          if ( !v20 )
          {
            for ( i = (WCHAR *)*v12; *i == 47; ++i )
              ;
            v14 = (const WCHAR *)PszDupW(i);
            v8 = v14;
            if ( !v14 )
            {
              active = -2147024882;
              goto LABEL_33;
            }
            v15 = *v14;
            v16 = v8;
            while ( v15 && v15 != 63 && v15 != 35 )
              v15 = *++v16;
            *v16 = 0;
            UlStripWhitespaceW(v8, 1, 1, 0);
            ExtensionW = PathFindExtensionW(v8);
            if ( !ExtensionW
              || CompareStringW(0x7Fu, 1u, ExtensionW, -1, L".mht", -1) != 2
              && CompareStringW(0x7Fu, 1u, ExtensionW, -1, L".mhtml", -1) != 2 )
            {
              active = -2146697202;
              goto LABEL_33;
            }
          }
        }
        OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 72);
        active = (*(__int64 (__fastcall **)(struct IMimeActiveUrlCache *, PCNZWCH, __int64, GUID *, CActiveUrl **, char *))(*(_QWORD *)g_pUrlCache + 32LL))(
                   g_pUrlCache,
                   *v12,
                   1,
                   &GUID_dde6416b_a337_480e_9be3_dec0855608ba,
                   &v22,
                   (char *)this + 72);
        if ( active >= 0 )
          active = CActiveUrl::HrActiveUrlRequest(v22, (CActiveUrlRequest *)((char *)this - 32));
      }
    }
  }
LABEL_33:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v22);
  if ( v8 )
    ((void (__fastcall *)(LPMALLOC, const WCHAR *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v8);
  STRW::~STRW((STRW *)&v23);
  return (unsigned int)active;
}

```

## disassembly

```asm
0x180036900  mov     [rsp-8+arg_10], rbx
0x180036905  push    rbp
0x180036906  push    rsi
0x180036907  push    rdi
0x180036908  push    r12
0x18003690a  push    r13
0x18003690c  push    r14
0x18003690e  push    r15
0x180036910  lea     rbp, [rsp-220h]
0x180036918  sub     rsp, 320h
0x18003691f  mov     rax, cs:__security_cookie
0x180036926  xor     rax, rsp
0x180036929  mov     [rbp+250h+var_40], rax
0x180036930  mov     r15, r8
0x180036933  mov     rbx, rdx
0x180036936  mov     r14, rcx
0x180036939  xor     r12d, r12d
0x18003693c  mov     r13d, 80h
0x180036942  mov     [rsp+350h+var_300], r12
0x180036947  mov     r8d, r13d; Size
0x18003694a  mov     [rsp+350h+var_310], r12d
0x18003694f  xor     edx, edx; Val
0x180036951  lea     rcx, [rbp+250h+var_2D0]; void *
0x180036955  mov     rsi, r9
0x180036958  call    memset_0
0x18003695d  mov     r8d, 104h; unsigned int
0x180036963  lea     rdx, [rbp+250h+var_250]; unsigned __int16 *
0x180036967  lea     rcx, [rsp+350h+var_2F8]; this
0x18003696c  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x180036971  test    rbx, rbx
0x180036974  jz      loc_180036C3F
0x18003697a  test    r15, r15
0x18003697d  jz      loc_180036C3F
0x180036983  test    rsi, rsi
0x180036986  jz      loc_180036C3F
0x18003698c  mov     rdx, rbx; unsigned __int16 *
0x18003698f  lea     rcx, [rsp+350h+var_2F8]; this
0x180036994  mov     edi, r12d
0x180036997  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x18003699c  mov     ebx, eax
0x18003699e  test    eax, eax
0x1800369a0  js      loc_180036C0C
0x1800369a6  xor     edx, edx; Val
0x1800369a8  lea     r8d, [r12+7Ch]; Size
0x1800369ad  lea     rcx, [rbp+250h+var_2CC]; void *
0x1800369b1  call    memset_0
0x1800369b6  mov     rax, [rsi]
0x1800369b9  lea     r8, [rbp+250h+var_2D0]
0x1800369bd  lea     rdx, [rsp+350h+var_310]
0x1800369c2  mov     [rbp+250h+var_2D0], r13d
0x1800369c6  mov     rcx, rsi
0x1800369c9  mov     rax, [rax+18h]
0x1800369cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369d2  test    eax, eax
0x1800369d4  js      short loc_1800369E2
0x1800369d6  test    byte ptr [rsp+350h+var_310], 40h
0x1800369db  jz      short loc_1800369E2
0x1800369dd  or      dword ptr [r14+50h], 4
0x1800369e2  mov     [r14+20h], r15
0x1800369e6  mov     rcx, r15
0x1800369e9  mov     rax, [r15]
0x1800369ec  mov     rax, [rax+8]
0x1800369f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369f5  mov     [r14+28h], rsi
0x1800369f9  mov     rcx, rsi
0x1800369fc  mov     rax, [rsi]
0x1800369ff  mov     rax, [rax+8]
0x180036a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a08  lea     rcx, [rsp+350h+var_2F8]; this
0x180036a0d  call    ?UrlUnescapeA@STRW@@QEAAJXZ; STRW::UrlUnescapeA(void)
0x180036a12  mov     ebx, eax
0x180036a14  test    eax, eax
0x180036a16  js      loc_180036C0C
0x180036a1c  cmp     [rsp+350h+var_2F8], r12d
0x180036a21  lea     rcx, cchOriginalDestLength
0x180036a28  lea     rsi, [r14+38h]
0x180036a2c  cmovnz  rcx, [rsp+350h+psz1]; psz1
0x180036a32  lea     r8, [r14+40h]
0x180036a36  mov     rdx, rsi
0x180036a39  call    MimeOleParseMhtmlUrlW
0x180036a3e  mov     ebx, eax
0x180036a40  test    eax, eax
0x180036a42  js      loc_180036C0C
0x180036a48  mov     r8, [rsi]; lpString1
0x180036a4b  lea     rax, aMid; "mid:"
0x180036a52  mov     r9d, 4; cchCount1
0x180036a58  mov     [rsp+350h+cchCount2], r9d; cchCount2
0x180036a5d  mov     [rsp+350h+lpString2], rax; lpString2
0x180036a62  lea     ebx, [r9-3]
0x180036a66  mov     edx, ebx; dwCmpFlags
0x180036a68  lea     ecx, [rbx+7Eh]; Locale
0x180036a6b  call    cs:__imp_CompareStringW
0x180036a71  cmp     eax, 2
0x180036a74  jz      loc_180036BB8
0x180036a7a  lea     rcx, ModuleName; "IEXPLORE.EXE"
0x180036a81  call    cs:__imp_GetModuleHandleW
0x180036a87  test    rax, rax
0x180036a8a  jz      loc_180036BB8
0x180036a90  xor     r8d, r8d; dwReserved
0x180036a93  mov     [rsp+350h+ppSM], r12
0x180036a98  lea     rdx, [rsp+350h+ppSM]; ppSM
0x180036a9d  mov     [rsp+350h+var_30C], r12d
0x180036aa2  xor     ecx, ecx; pSP
0x180036aa4  call    cs:__imp_CoInternetCreateSecurityManager
0x180036aaa  test    eax, eax
0x180036aac  jnz     short loc_180036ADB
0x180036aae  mov     rcx, [rsp+350h+ppSM]
0x180036ab3  lea     r8, [rsp+350h+var_30C]
0x180036ab8  mov     rdx, [rsi]
0x180036abb  xor     r9d, r9d
0x180036abe  mov     rax, [rcx]
0x180036ac1  mov     rax, [rax+28h]
0x180036ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036aca  mov     rcx, [rsp+350h+ppSM]
0x180036acf  mov     rax, [rcx]
0x180036ad2  mov     rax, [rax+10h]
0x180036ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036adb  cmp     [rsp+350h+var_30C], r12d
0x180036ae0  jnz     loc_180036BB8
0x180036ae6  mov     rcx, [rsi]
0x180036ae9  jmp     short loc_180036AF5
0x180036aeb  cmp     ax, 2Fh ; '/'
0x180036aef  jnz     short loc_180036AFD
0x180036af1  add     rcx, 2
0x180036af5  movzx   eax, word ptr [rcx]
0x180036af8  test    ax, ax
0x180036afb  jnz     short loc_180036AEB
0x180036afd  call    cs:__imp_PszDupW
0x180036b03  mov     rdi, rax
0x180036b06  test    rax, rax
0x180036b09  jnz     short loc_180036B15
0x180036b0b  mov     ebx, 8007000Eh
0x180036b10  jmp     loc_180036C0C
0x180036b15  movzx   eax, word ptr [rax]
0x180036b18  mov     rcx, rdi
0x180036b1b  jmp     short loc_180036B30
0x180036b1d  cmp     ax, 3Fh ; '?'
0x180036b21  jz      short loc_180036B35
0x180036b23  cmp     ax, 23h ; '#'
0x180036b27  jz      short loc_180036B35
0x180036b29  add     rcx, 2
0x180036b2d  movzx   eax, word ptr [rcx]
0x180036b30  test    ax, ax
0x180036b33  jnz     short loc_180036B1D
0x180036b35  mov     [rcx], r12w
0x180036b39  xor     r9d, r9d
0x180036b3c  mov     rcx, rdi
0x180036b3f  mov     r8d, ebx
0x180036b42  mov     edx, ebx
0x180036b44  call    cs:__imp_UlStripWhitespaceW
0x180036b4a  mov     rcx, rdi; pszPath
0x180036b4d  call    cs:__imp_PathFindExtensionW
0x180036b53  mov     rbx, rax
0x180036b56  test    rax, rax
0x180036b59  jz      short loc_180036BB1
0x180036b5b  or      r15d, 0FFFFFFFFh
0x180036b5f  lea     rax, aMht; ".mht"
0x180036b66  mov     [rsp+350h+cchCount2], r15d; cchCount2
0x180036b6b  mov     r9d, r15d; cchCount1
0x180036b6e  mov     r8, rbx; lpString1
0x180036b71  mov     [rsp+350h+lpString2], rax; lpString2
0x180036b76  lea     edx, [r15+2]; dwCmpFlags
0x180036b7a  lea     ecx, [rdx+7Eh]; Locale
0x180036b7d  call    cs:__imp_CompareStringW
0x180036b83  cmp     eax, 2
0x180036b86  jz      short loc_180036BB8
0x180036b88  lea     edx, [r15+2]; dwCmpFlags
0x180036b8c  mov     [rsp+350h+cchCount2], r15d; cchCount2
0x180036b91  lea     rax, aMhtml; ".mhtml"
0x180036b98  mov     r9d, r15d; cchCount1
0x180036b9b  lea     ecx, [rdx+7Eh]; Locale
0x180036b9e  mov     [rsp+350h+lpString2], rax; lpString2
0x180036ba3  mov     r8, rbx; lpString1
0x180036ba6  call    cs:__imp_CompareStringW
0x180036bac  cmp     eax, 2
0x180036baf  jz      short loc_180036BB8
0x180036bb1  mov     ebx, 800C000Eh
0x180036bb6  jmp     short loc_180036C0C
0x180036bb8  lea     rbx, [r14+48h]
0x180036bbc  mov     rcx, rbx
0x180036bbf  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180036bc4  mov     rcx, cs:?g_pUrlCache@@3PEAUIMimeActiveUrlCache@@EA; IMimeActiveUrlCache * g_pUrlCache
0x180036bcb  lea     rdx, [rsp+350h+var_300]
0x180036bd0  mov     qword ptr [rsp+350h+cchCount2], rbx
0x180036bd5  lea     r9, _GUID_dde6416b_a337_480e_9be3_dec0855608ba
0x180036bdc  mov     [rsp+350h+lpString2], rdx
0x180036be1  mov     r8d, 1
0x180036be7  mov     rdx, [rsi]
0x180036bea  mov     rax, [rcx]
0x180036bed  mov     rax, [rax+20h]
0x180036bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036bf6  mov     ebx, eax
0x180036bf8  test    eax, eax
0x180036bfa  js      short loc_180036C0C
0x180036bfc  mov     rcx, [rsp+350h+var_300]; this
0x180036c01  lea     rdx, [r14-20h]; struct CActiveUrlRequest *
0x180036c05  call    ?HrActiveUrlRequest@CActiveUrl@@QEAAJPEAVCActiveUrlRequest@@@Z; CActiveUrl::HrActiveUrlRequest(CActiveUrlRequest *)
0x180036c0a  mov     ebx, eax
0x180036c0c  lea     rcx, [rsp+350h+var_300]
0x180036c11  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180036c16  test    rdi, rdi
0x180036c19  jz      short loc_180036C31
0x180036c1b  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180036c22  mov     rdx, rdi
0x180036c25  mov     rax, [rcx]
0x180036c28  mov     rax, [rax+28h]
0x180036c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c31  lea     rcx, [rsp+350h+var_2F8]; this
0x180036c36  call    ??1STRW@@QEAA@XZ; STRW::~STRW(void)
0x180036c3b  mov     eax, ebx
0x180036c3d  jmp     short loc_180036C4E
0x180036c3f  lea     rcx, [rsp+350h+var_2F8]; this
0x180036c44  call    ??1STRW@@QEAA@XZ; STRW::~STRW(void)
0x180036c49  mov     eax, 80070057h
0x180036c4e  mov     rcx, [rbp+250h+var_40]
0x180036c55  xor     rcx, rsp; StackCookie
0x180036c58  call    __security_check_cookie
0x180036c5d  mov     rbx, [rsp+350h+arg_10]
0x180036c65  add     rsp, 320h
0x180036c6c  pop     r15
0x180036c6e  pop     r14
0x180036c70  pop     r13
0x180036c72  pop     r12
0x180036c74  pop     rdi
0x180036c75  pop     rsi
0x180036c76  pop     rbp
0x180036c77  retn
```
