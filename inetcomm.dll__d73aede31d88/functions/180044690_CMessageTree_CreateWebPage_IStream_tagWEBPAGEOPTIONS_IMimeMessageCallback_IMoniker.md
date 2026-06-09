# CMessageTree::CreateWebPage(IStream *,tagWEBPAGEOPTIONS *,IMimeMessageCallback *,IMoniker * *)

- ea: `0x180044690`
- end: `0x18004495c`
- name: `?CreateWebPage@CMessageTree@@UEAAJPEAUIStream@@PEAUtagWEBPAGEOPTIONS@@PEAUIMimeMessageCallback@@PEAPEAUIMoniker@@@Z`
- size: `716`
- prototype: `__int64 __fastcall(CMessageTree *__hidden this, struct IStream *, struct tagWEBPAGEOPTIONS *, struct IMimeMessageCallback *, struct IMoniker **)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180002098`
- `0x180004d60`
- `0x180005748`
- `0x18000910c`
- `0x18001f120`
- `0x180022784`
- `0x1800299d0`
- `0x18003446c`
- `0x180044690`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180044872`
- `KERNEL32!LeaveCriticalSection` at `0x180044916`
- `KERNEL32!LeaveCriticalSection` at `0x180044872`
- `KERNEL32!LeaveCriticalSection` at `0x180044916`
- `KERNEL32!EnterCriticalSection` at `0x18004470b`
- `KERNEL32!EnterCriticalSection` at `0x180044864`
- `KERNEL32!EnterCriticalSection` at `0x18004470b`
- `KERNEL32!EnterCriticalSection` at `0x180044864`
- `urlmon!CreateURLMoniker` at `0x18004488b`
- `urlmon!CreateURLMoniker` at `0x18004488b`

## pseudocode

```c
__int64 __fastcall CMessageTree::CreateWebPage(
        CMessageTree *this,
        struct IStream *a2,
        struct tagWEBPAGEOPTIONS *a3,
        struct IMimeMessageCallback *a4,
        struct IMoniker **a5)
{
  int v9; // eax
  char *v10; // rsi
  const WCHAR *v11; // r15
  HRESULT MhtmlPrefixW; // ebx
  const WCHAR *v13; // rdx
  __int64 v14; // rdi
  struct IMonikerVtbl *v15; // rbx
  LPMONIKER v16; // rsi
  CURLMonikerWrapper *v17; // rax
  CURLMonikerWrapper *v18; // rax
  struct IMoniker *v19; // rdi
  unsigned int v21; // [rsp+20h] [rbp-E0h]
  LPMONIKER ppmk; // [rsp+30h] [rbp-D0h] BYREF
  struct IMonikerVtbl *v23; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-B8h]
  unsigned __int16 v26[264]; // [rsp+50h] [rbp-B0h] BYREF

  v24 = 0;
  v23 = 0;
  ppmk = 0;
  if ( a5 && (!a3 || *(_DWORD *)a3 == 20) )
  {
    *a5 = 0;
    lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 376);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 376));
    OE_SafeReleaseAndNullPtr<IStream>((char *)this + 224);
    OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 328);
    if ( a2 )
    {
      OE_SafeReleaseAndNullPtr<IStream>((char *)this + 224);
      *((_QWORD *)this + 28) = a2;
      ((void (__fastcall *)(struct IStream *))a2->lpVtbl->AddRef)(a2);
    }
    else
    {
      *((_DWORD *)this + 30) = 1;
    }
    OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 360);
    if ( a4 )
    {
      *((_QWORD *)this + 45) = a4;
      (*(void (__fastcall **)(struct IMimeMessageCallback *))(*(_QWORD *)a4 + 8LL))(a4);
    }
    if ( a3 )
    {
      *((_OWORD *)this + 21) = *(_OWORD *)a3;
      v9 = *((_DWORD *)a3 + 4);
    }
    else
    {
      *((_OWORD *)this + 21) = xmmword_1800D8D28;
      v9 = 0;
    }
    v10 = (char *)this + 288;
    *((_DWORD *)this + 88) = v9;
    v11 = &cchOriginalDestLength;
    if ( *((_DWORD *)this + 72) )
      goto LABEL_21;
    MhtmlPrefixW = GetMhtmlPrefixW(&v24);
    if ( MhtmlPrefixW < 0 )
      goto LABEL_30;
    v21 = DwCounterNext();
    StringCchPrintfW(v26, 0x107u, L"%smid://%08d/", v24, v21);
    MhtmlPrefixW = STRW::Append((CMessageTree *)((char *)this + 288), v26);
    if ( MhtmlPrefixW < 0 )
      goto LABEL_30;
    v13 = &cchOriginalDestLength;
    if ( *(_DWORD *)v10 )
      v13 = (const WCHAR *)*((_QWORD *)this + 37);
    MhtmlPrefixW = (*(__int64 (__fastcall **)(struct IMimeActiveUrlCache *, const WCHAR *, char *, bool, struct IMonikerVtbl **))(*(_QWORD *)g_pUrlCache + 40LL))(
                     g_pUrlCache,
                     v13,
                     (char *)this - 32,
                     a2 != 0,
                     &v23);
    if ( MhtmlPrefixW < 0 )
      goto LABEL_30;
    v14 = *((_QWORD *)this + 40);
    if ( v14 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v14 + 88));
      *(_DWORD *)(v14 + 80) |= 1u;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 88));
    }
    if ( *(_DWORD *)v10 )
LABEL_21:
      v11 = (const WCHAR *)*((_QWORD *)v10 + 1);
    MhtmlPrefixW = CreateURLMoniker(0, v11, &ppmk);
    if ( MhtmlPrefixW >= 0 )
    {
      v15 = v23;
      if ( !v23 )
      {
        *a5 = ppmk;
        ppmk = 0;
        goto LABEL_29;
      }
      v16 = ppmk;
      *a5 = 0;
      v17 = (CURLMonikerWrapper *)operator new(0x28u);
      if ( v17 )
      {
        v18 = CURLMonikerWrapper::CURLMonikerWrapper(v17);
        v19 = (struct IMoniker *)v18;
        if ( v18 )
        {
          *((_QWORD *)v18 + 3) = v16;
          ((void (__fastcall *)(LPMONIKER))v16->lpVtbl->AddRef)(v16);
          v19[2].lpVtbl = v15;
          (*((void (__fastcall **)(struct IMonikerVtbl *))v15->QueryInterface + 1))(v15);
          *a5 = v19;
LABEL_29:
          MhtmlPrefixW = 0;
          goto LABEL_30;
        }
      }
      MhtmlPrefixW = -2147024882;
    }
LABEL_30:
    LeaveCriticalSection(lpCriticalSection);
    OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&ppmk);
    OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v23);
    return (unsigned int)MhtmlPrefixW;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180044690  push    rbp
0x180044692  push    rbx
0x180044693  push    rsi
0x180044694  push    rdi
0x180044695  push    r12
0x180044697  push    r13
0x180044699  push    r14
0x18004469b  push    r15
0x18004469d  lea     rbp, [rsp-178h]
0x1800446a5  sub     rsp, 278h
0x1800446ac  mov     rax, cs:__security_cookie
0x1800446b3  xor     rax, rsp
0x1800446b6  mov     [rbp+1B0h+var_50], rax
0x1800446bd  mov     r14, [rbp+1B0h+arg_20]
0x1800446c4  xor     eax, eax
0x1800446c6  mov     [rsp+2B0h+var_270], rax
0x1800446cb  mov     rsi, r9
0x1800446ce  mov     [rsp+2B0h+var_278], rax
0x1800446d3  mov     rbx, r8
0x1800446d6  mov     [rsp+2B0h+ppmk], rax
0x1800446db  mov     r12, rdx
0x1800446de  mov     rdi, rcx
0x1800446e1  test    r14, r14
0x1800446e4  jz      loc_180044934
0x1800446ea  test    rbx, rbx
0x1800446ed  jz      short loc_1800446F9
0x1800446ef  cmp     dword ptr [r8], 14h
0x1800446f3  jnz     loc_180044934
0x1800446f9  mov     [r14], rax
0x1800446fc  lea     rax, [rcx+178h]
0x180044703  mov     rcx, rax; lpCriticalSection
0x180044706  mov     [rsp+2B0h+lpCriticalSection], rax
0x18004470b  call    cs:__imp_EnterCriticalSection
0x180044711  lea     r15, [rdi+0E0h]
0x180044718  mov     rcx, r15
0x18004471b  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x180044720  lea     rcx, [rdi+148h]
0x180044727  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18004472c  test    r12, r12
0x18004472f  jz      short loc_180044752
0x180044731  mov     rcx, r15
0x180044734  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x180044739  mov     [rdi+0E0h], r12
0x180044740  mov     rcx, r12
0x180044743  mov     rax, [r12]
0x180044747  mov     rax, [rax+8]
0x18004474b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044750  jmp     short loc_180044759
0x180044752  mov     dword ptr [rdi+78h], 1
0x180044759  lea     r15, [rdi+168h]
0x180044760  mov     rcx, r15
0x180044763  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180044768  test    rsi, rsi
0x18004476b  jz      short loc_18004477F
0x18004476d  mov     [r15], rsi
0x180044770  mov     rcx, rsi
0x180044773  mov     rax, [rsi]
0x180044776  mov     rax, [rax+8]
0x18004477a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004477f  test    rbx, rbx
0x180044782  jz      short loc_180044793
0x180044784  movups  xmm0, xmmword ptr [rbx]
0x180044787  movups  xmmword ptr [rdi+150h], xmm0
0x18004478e  mov     eax, [rbx+10h]
0x180044791  jmp     short loc_1800447A7
0x180044793  movups  xmm0, cs:xmmword_1800D8D28
0x18004479a  movups  xmmword ptr [rdi+150h], xmm0
0x1800447a1  mov     eax, cs:dword_1800D8D38
0x1800447a7  lea     rsi, [rdi+120h]
0x1800447ae  mov     [rdi+160h], eax
0x1800447b4  cmp     dword ptr [rsi], 0
0x1800447b7  lea     r15, cchOriginalDestLength
0x1800447be  jnz     loc_18004487D
0x1800447c4  lea     rcx, [rsp+2B0h+var_270]
0x1800447c9  call    GetMhtmlPrefixW
0x1800447ce  mov     ebx, eax
0x1800447d0  test    eax, eax
0x1800447d2  js      loc_180044911
0x1800447d8  call    ?DwCounterNext@@YAKXZ; DwCounterNext(void)
0x1800447dd  mov     r9, [rsp+2B0h+var_270]
0x1800447e2  lea     r8, aSmid08d; "%smid://%08d/"
0x1800447e9  mov     edx, 107h; unsigned __int64
0x1800447ee  mov     [rsp+2B0h+var_290], eax
0x1800447f2  lea     rcx, [rsp+2B0h+var_260]; unsigned __int16 *
0x1800447f7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800447fc  lea     rdx, [rsp+2B0h+var_260]; unsigned __int16 *
0x180044801  mov     rcx, rsi; this
0x180044804  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x180044809  mov     ebx, eax
0x18004480b  test    eax, eax
0x18004480d  js      loc_180044911
0x180044813  mov     rcx, cs:?g_pUrlCache@@3PEAUIMimeActiveUrlCache@@EA; IMimeActiveUrlCache * g_pUrlCache
0x18004481a  xor     r9d, r9d
0x18004481d  test    r12, r12
0x180044820  mov     rdx, r15
0x180044823  setnz   r9b
0x180044827  cmp     dword ptr [rsi], 0
0x18004482a  mov     rax, [rcx]
0x18004482d  jz      short loc_180044833
0x18004482f  mov     rdx, [rsi+8]
0x180044833  mov     rax, [rax+28h]
0x180044837  lea     r8, [rsp+2B0h+var_278]
0x18004483c  mov     qword ptr [rsp+2B0h+var_290], r8
0x180044841  lea     r8, [rdi-20h]
0x180044845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004484a  mov     ebx, eax
0x18004484c  test    eax, eax
0x18004484e  js      loc_180044911
0x180044854  mov     rdi, [rdi+140h]
0x18004485b  test    rdi, rdi
0x18004485e  jz      short loc_180044878
0x180044860  lea     rcx, [rdi+58h]; lpCriticalSection
0x180044864  call    cs:__imp_EnterCriticalSection
0x18004486a  or      dword ptr [rdi+50h], 1
0x18004486e  lea     rcx, [rdi+58h]; lpCriticalSection
0x180044872  call    cs:__imp_LeaveCriticalSection
0x180044878  cmp     dword ptr [rsi], 0
0x18004487b  jz      short loc_180044881
0x18004487d  mov     r15, [rsi+8]
0x180044881  lea     r8, [rsp+2B0h+ppmk]; ppmk
0x180044886  mov     rdx, r15; szURL
0x180044889  xor     ecx, ecx; pMkCtx
0x18004488b  call    cs:__imp_CreateURLMoniker
0x180044891  mov     ebx, eax
0x180044893  test    eax, eax
0x180044895  js      short loc_180044911
0x180044897  mov     rbx, [rsp+2B0h+var_278]
0x18004489c  test    rbx, rbx
0x18004489f  jz      short loc_1800448FE
0x1800448a1  mov     rsi, [rsp+2B0h+ppmk]
0x1800448a6  mov     ecx, 28h ; '('; Size
0x1800448ab  mov     qword ptr [r14], 0
0x1800448b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800448b7  test    rax, rax
0x1800448ba  jz      short loc_1800448F7
0x1800448bc  mov     rcx, rax; this
0x1800448bf  call    ??0CURLMonikerWrapper@@AEAA@XZ; CURLMonikerWrapper::CURLMonikerWrapper(void)
0x1800448c4  mov     rdi, rax
0x1800448c7  test    rax, rax
0x1800448ca  jz      short loc_1800448F7
0x1800448cc  mov     [rax+18h], rsi
0x1800448d0  mov     rcx, rsi
0x1800448d3  mov     rdx, [rsi]
0x1800448d6  mov     rax, [rdx+8]
0x1800448da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448df  mov     [rdi+10h], rbx
0x1800448e3  mov     rcx, rbx
0x1800448e6  mov     rdx, [rbx]
0x1800448e9  mov     rax, [rdx+8]
0x1800448ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448f2  mov     [r14], rdi
0x1800448f5  jmp     short loc_18004490F
0x1800448f7  mov     ebx, 8007000Eh
0x1800448fc  jmp     short loc_180044911
0x1800448fe  mov     rax, [rsp+2B0h+ppmk]
0x180044903  mov     [r14], rax
0x180044906  mov     [rsp+2B0h+ppmk], 0
0x18004490f  xor     ebx, ebx
0x180044911  mov     rcx, [rsp+2B0h+lpCriticalSection]; lpCriticalSection
0x180044916  call    cs:__imp_LeaveCriticalSection
0x18004491c  lea     rcx, [rsp+2B0h+ppmk]
0x180044921  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180044926  lea     rcx, [rsp+2B0h+var_278]
0x18004492b  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180044930  mov     eax, ebx
0x180044932  jmp     short loc_180044939
0x180044934  mov     eax, 80070057h
0x180044939  mov     rcx, [rbp+1B0h+var_50]
0x180044940  xor     rcx, rsp; StackCookie
0x180044943  call    __security_check_cookie
0x180044948  add     rsp, 278h
0x18004494f  pop     r15
0x180044951  pop     r14
0x180044953  pop     r13
0x180044955  pop     r12
0x180044957  pop     rdi
0x180044958  pop     rsi
0x180044959  pop     rbx
0x18004495a  pop     rbp
0x18004495b  retn
```
