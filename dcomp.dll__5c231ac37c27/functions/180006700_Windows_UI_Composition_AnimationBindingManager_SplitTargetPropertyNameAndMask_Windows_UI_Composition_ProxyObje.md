# Windows::UI::Composition::AnimationBindingManager::SplitTargetPropertyNameAndMask(Windows::UI::Composition::ProxyObject *,HSTRING__ *,HSTRING__ * *,ExpressionObjectPropertyInfo *,DCOMPOSITION_EXPRESSION_TYPE *,SubchannelMaskInfo * *)

- ea: `0x180006700`
- end: `0x180006b59`
- name: `?SplitTargetPropertyNameAndMask@AnimationBindingManager@Composition@UI@Windows@@QEAAJPEAVProxyObject@234@PEAUHSTRING__@@PEAPEAU6@PEAVExpressionObjectPropertyInfo@@PEAW4DCOMPOSITION_EXPRESSION_TYPE@@PEAPEAVSubchannelMaskInfo@@@Z`
- size: `1113`
- prototype: `int(Windows::UI::Composition::AnimationBindingManager *__hidden this, struct Windows::UI::Composition::ProxyObject *, HSTRING, HSTRING *, struct ExpressionObjectPropertyInfo *, enum DCOMPOSITION_EXPRESSION_TYPE *, struct SubchannelMaskInfo **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180076de8`

## callees

- `0x180006590`
- `0x180006700`
- `0x1800078a4`
- `0x180008034`
- `0x18001358c`
- `0x18006c5b0`
- `0x1800ce320`
- `0x1800df108`
- `0x1800e77ac`
- `0x1800ebd74`
- `0x1800f6f34`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800067df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800067df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800068bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006910`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800068bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006910`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006902`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006902`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1800069da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180006a31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1800069da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180006a31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180006886`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180006886`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000693d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800069ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180006aa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000693d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800069ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180006aa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800067b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800067b0`

## string_xrefs

- `0x180006ad0`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtanimationbindingmanager.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::AnimationBindingManager::SplitTargetPropertyNameAndMask(
        Windows::UI::Composition::AnimationBindingManager *this,
        struct Windows::UI::Composition::ProxyObject *a2,
        HSTRING a3,
        HSTRING *a4,
        struct ExpressionObjectPropertyInfo *a5,
        enum DCOMPOSITION_EXPRESSION_TYPE *a6,
        struct SubchannelMaskInfo **a7)
{
  __int64 v7; // rax
  _WORD *v8; // r14
  __int64 (__fastcall *v11)(struct Windows::UI::Composition::ProxyObject *, HSTRING, Windows::UI::Composition::AnimationBindingManager **, __int64 *); // rax
  HSTRING *v13; // rbx
  struct SubchannelMaskInfo *v14; // r12
  unsigned __int8 v15; // al
  int v16; // esi
  int v17; // edi
  HANDLE ProcessHeap; // rax
  _WORD *v19; // rax
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // rcx
  _WORD *v24; // rcx
  HRESULT v25; // eax
  unsigned __int64 v26; // rcx
  HSTRING *v27; // rsi
  HANDLE v28; // rax
  struct ExpressionObjectPropertyInfo *v29; // rcx
  int v30; // eax
  HANDLE v31; // rax
  const unsigned __int16 *v33; // rbx
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v35; // rcx
  unsigned __int8 v36; // al
  struct Windows::UI::Composition::ExpressionErrorInfo *v37; // rax
  const unsigned __int16 *v38; // r8
  int *v39; // [rsp+20h] [rbp-60h]
  UINT32 v40; // [rsp+40h] [rbp-40h] BYREF
  UINT32 v41; // [rsp+44h] [rbp-3Ch]
  struct SubchannelMaskInfo *v42; // [rsp+48h] [rbp-38h]
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  __int64 v44; // [rsp+58h] [rbp-28h] BYREF
  int v45; // [rsp+60h] [rbp-20h]
  __int64 v46; // [rsp+68h] [rbp-18h] BYREF
  UINT32 v47; // [rsp+70h] [rbp-10h]
  void *lpMem; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  Windows::UI::Composition::AnimationBindingManager *length; // [rsp+C0h] [rbp+40h] BYREF
  int v51; // [rsp+C8h] [rbp+48h] BYREF

  length = this;
  v7 = *(_QWORD *)a2;
  v8 = 0;
  v39 = &v51;
  v46 = 1;
  v47 = 0;
  v11 = *(__int64 (__fastcall **)(struct Windows::UI::Composition::ProxyObject *, HSTRING, Windows::UI::Composition::AnimationBindingManager **, __int64 *))(v7 + 200);
  v44 = 0;
  v13 = 0;
  v45 = 2;
  lpMem = 0;
  v51 = 18;
  v42 = 0;
  v14 = 0;
  v41 = 0;
  string = 0;
  v40 = 0;
  LODWORD(length) = 0;
  v15 = v11(a2, a3, &length, &v44);
  if ( ((unsigned __int8)-(((unsigned __int8)length & 2) != 0) & v15) != 0 )
  {
    v16 = -1;
    v17 = 0;
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a3, &v40);
    v16 = v40;
    v8 = StringRawBuffer;
    do
    {
      if ( --v16 < 0 )
      {
        v17 = 19;
        v16 = -1;
        goto LABEL_3;
      }
    }
    while ( StringRawBuffer[v16] != 46 );
    if ( WindowsSubstringWithSpecifiedLength(a3, 0, v16, &string) < 0 )
      Microsoft::WRL2::FailFast::OutOfMemory(v35);
    v39 = &v51;
    v36 = (*(__int64 (__fastcall **)(struct Windows::UI::Composition::ProxyObject *, HSTRING, Windows::UI::Composition::AnimationBindingManager **, __int64 *))(*(_QWORD *)a2 + 200LL))(
            a2,
            string,
            &length,
            &v44);
    v17 = (v36 & (unsigned __int8)-(((unsigned __int8)length & 2) != 0)) == 0 ? 0x13 : 0;
  }
LABEL_3:
  LODWORD(v46) = v17;
  if ( string )
    WindowsDeleteString(string);
  if ( v17 )
  {
    v47 = v40;
    if ( v8 )
    {
      ProcessHeap = GetProcessHeap();
      v19 = HeapAlloc(ProcessHeap, 0, 0xF2u);
      v13 = (HSTRING *)v19;
      if ( !v19 )
        ModuleFailFastForHRESULT(2147942414LL, retaddr, v20, v21);
      lpMem = v19;
      v22 = 120;
      *v19 = 0;
      v23 = 2147483646;
      do
      {
        if ( !v23 )
          break;
        if ( !*v8 )
          break;
        *v19++ = *v8++;
        --v23;
        --v22;
      }
      while ( v22 );
      v24 = v19 - 1;
      if ( v22 )
        v24 = v19;
      *v24 = 0;
    }
    MilInstrumentationCheckHR_MaybeFailFast(
      4u,
      &Windows::UI::Composition::ExpressionAnimationParser::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      -2147024809,
      0xBCDu,
      0);
    goto LABEL_25;
  }
  if ( v16 <= -1 )
    goto LABEL_17;
  LODWORD(length) = 0;
  v33 = WindowsGetStringRawBuffer(a3, (UINT32 *)&length);
  v39 = (int *)&v46;
  Windows::UI::Composition::ExpressionAnimationParser::ParseSwizzle(
    &v33[v16 + 1],
    (unsigned int)((_DWORD)length - v16),
    (unsigned int)v51,
    0);
  v17 = v46;
  if ( (_DWORD)v46 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(
      4u,
      &Windows::UI::Composition::ExpressionAnimationParser::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      -2147024809,
      0xBE4u,
      0);
  }
  else
  {
    if ( (_DWORD)length - v16 - 1 == v41 )
    {
      v13 = (HSTRING *)lpMem;
      v14 = v42;
LABEL_17:
      if ( a4 )
      {
        v25 = v16 > -1 ? WindowsSubstringWithSpecifiedLength(a3, 0, v16, a4) : WindowsDuplicateString(a3, a4);
        a4 = 0;
        if ( v25 < 0 )
          Microsoft::WRL2::FailFast::OutOfMemory(v26);
      }
      v46 = 0;
      v27 = a4;
      v47 = (unsigned int)a4;
      v17 = (int)a4;
      if ( !v13 )
        goto LABEL_26;
      v28 = GetProcessHeap();
      HeapFree(v28, 0, v13);
      v13 = a4;
      lpMem = a4;
      goto LABEL_23;
    }
    v47 = v41;
    LODWORD(v46) = 17;
    HIDWORD(v46) = (_DWORD)length - v16 - 1;
    Windows::UI::Composition::ExpressionErrorInfo::SetErrorContext(
      (Windows::UI::Composition::ExpressionErrorInfo *)&v46,
      v33);
    MilInstrumentationCheckHR_MaybeFailFast(
      4u,
      &Windows::UI::Composition::ExpressionAnimationParser::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      -2147024809,
      0xBF9u,
      0);
    v17 = v46;
  }
  v13 = (HSTRING *)lpMem;
  v27 = (HSTRING *)v42;
LABEL_23:
  if ( v27 )
    operator delete(v27, 8u);
LABEL_25:
  if ( !v17 )
  {
LABEL_26:
    v29 = a5;
    v30 = v45;
    *(_QWORD *)a5 = v44;
    *((_DWORD *)v29 + 2) = v30;
    *(_DWORD *)a6 = v51;
    *a7 = v14;
    if ( v13 )
    {
      v31 = GetProcessHeap();
      HeapFree(v31, 0, v13);
    }
    return 0;
  }
  v37 = (struct Windows::UI::Composition::ExpressionErrorInfo *)WindowsGetStringRawBuffer(a3, 0);
  if ( v17 == 4 || v17 == 20 )
    Microsoft::WRL2::FailFast::Unexpected(0);
  Windows::UI::Composition::OriginateExpressionErrorInfo((Windows::UI::Composition *)&v46, v37, v38);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7A,
    (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtanimationbindingmanager.cpp",
    (const char *)0x80070057LL,
    (int)v39);
  if ( lpMem )
    operator delete(lpMem);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180006700  mov     [rsp-38h+arg_10], rbx
0x180006705  mov     [rsp-38h+length], rcx
0x18000670a  push    rbp
0x18000670b  push    rsi
0x18000670c  push    rdi
0x18000670d  push    r12
0x18000670f  push    r13
0x180006711  push    r14
0x180006713  push    r15
0x180006715  mov     rbp, rsp
0x180006718  sub     rsp, 80h
0x18000671f  mov     rax, [rdx]
0x180006722  lea     rcx, [rbp+arg_8]
0x180006726  xor     r14d, r14d
0x180006729  mov     qword ptr [rsp+80h+var_60], rcx; int
0x18000672e  mov     r15, r8
0x180006731  mov     [rbp+var_18], 1
0x180006739  mov     rdi, rdx
0x18000673c  mov     [rbp+var_10], r14d
0x180006740  mov     rax, [rax+0C8h]
0x180006747  lea     r8, [rbp+length]
0x18000674b  mov     r13, r9
0x18000674e  mov     [rbp+var_28], r14
0x180006752  mov     ebx, r14d
0x180006755  mov     [rbp+var_20], 2
0x18000675c  lea     r9, [rbp+var_28]
0x180006760  mov     [rbp+lpMem], rbx
0x180006764  mov     rdx, r15
0x180006767  mov     [rbp+arg_8], 12h
0x18000676e  mov     rcx, rdi
0x180006771  mov     [rbp+var_38], r14
0x180006775  mov     r12d, r14d
0x180006778  mov     [rbp+var_3C], r14d
0x18000677c  mov     [rbp+string], r14
0x180006780  mov     [rbp+var_40], r14d
0x180006784  mov     dword ptr [rbp+length], r14d
0x180006788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000678d  mov     ecx, dword ptr [rbp+length]
0x180006790  and     cl, 2
0x180006793  neg     cl
0x180006795  sbb     cl, cl
0x180006797  test    al, cl
0x180006799  jz      loc_1800069A7
0x18000679f  or      esi, 0FFFFFFFFh
0x1800067a2  xor     edi, edi
0x1800067a4  mov     dword ptr [rbp+var_18], edi
0x1800067a7  mov     rcx, [rbp+string]; string
0x1800067ab  test    rcx, rcx
0x1800067ae  jz      short loc_1800067B6
0x1800067b0  call    cs:__imp_WindowsDeleteString
0x1800067b6  xor     ecx, ecx
0x1800067b8  test    edi, edi
0x1800067ba  jz      loc_180006863
0x1800067c0  mov     eax, [rbp+var_40]
0x1800067c3  xor     r13d, r13d
0x1800067c6  mov     [rbp+var_10], eax
0x1800067c9  test    r14, r14
0x1800067cc  jz      short loc_180006835
0x1800067ce  call    cs:__imp_GetProcessHeap
0x1800067d4  xor     edx, edx; dwFlags
0x1800067d6  mov     r8d, 0F2h; dwBytes
0x1800067dc  mov     rcx, rax; hHeap
0x1800067df  call    cs:__imp_HeapAlloc
0x1800067e5  mov     rbx, rax
0x1800067e8  test    rax, rax
0x1800067eb  jz      loc_180006B42
0x1800067f1  mov     [rbp+lpMem], rax
0x1800067f5  lea     edx, [r13+78h]
0x1800067f9  mov     [rax], r13w
0x1800067fd  mov     ecx, 7FFFFFFEh
0x180006802  test    rcx, rcx
0x180006805  jz      short loc_180006826
0x180006807  movzx   r8d, word ptr [r14]
0x18000680b  test    r8w, r8w
0x18000680f  jz      short loc_180006826
0x180006811  mov     [rax], r8w
0x180006815  add     r14, 2
0x180006819  add     rax, 2
0x18000681d  dec     rcx
0x180006820  sub     rdx, 1
0x180006824  jnz     short loc_180006802
0x180006826  test    rdx, rdx
0x180006829  lea     rcx, [rax-2]
0x18000682d  cmovnz  rcx, rax
0x180006831  mov     [rcx], r13w
0x180006835  mov     r8d, 2; unsigned int
0x18000683b  mov     [rsp+80h+var_58], r13; void *
0x180006840  mov     r14d, 80070057h
0x180006846  mov     [rsp+80h+var_60], 0BCDh; unsigned int
0x18000684e  mov     r9d, r14d; int
0x180006851  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@ExpressionAnimationParser@Composition@UI@Windows@@0QBJB; int *
0x180006858  lea     ecx, [r8+2]; unsigned int
0x18000685c  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180006861  jmp     short loc_1800068D2
0x180006863  mov     r14d, 80070057h
0x180006869  cmp     esi, 0FFFFFFFFh
0x18000686c  jg      loc_180006933
0x180006872  test    r13, r13
0x180006875  jz      short loc_180006897
0x180006877  mov     rcx, r15; string
0x18000687a  cmp     esi, 0FFFFFFFFh
0x18000687d  jg      loc_180006A29
0x180006883  mov     rdx, r13; newString
0x180006886  call    cs:__imp_WindowsDuplicateString
0x18000688c  xor     r13d, r13d
0x18000688f  test    eax, eax
0x180006891  js      loc_180006A8F
0x180006897  mov     [rbp+var_18], 0
0x18000689f  mov     rsi, r13
0x1800068a2  mov     [rbp+var_10], r13d
0x1800068a6  mov     edi, r13d
0x1800068a9  test    rbx, rbx
0x1800068ac  jz      short loc_1800068DA
0x1800068ae  call    cs:__imp_GetProcessHeap
0x1800068b4  mov     r8, rbx; lpMem
0x1800068b7  xor     edx, edx; dwFlags
0x1800068b9  mov     rcx, rax; hHeap
0x1800068bc  call    cs:__imp_HeapFree
0x1800068c2  mov     rbx, r13
0x1800068c5  mov     [rbp+lpMem], rbx
0x1800068c9  test    rsi, rsi
0x1800068cc  jnz     loc_180006A3C
0x1800068d2  test    edi, edi
0x1800068d4  jnz     loc_180006A9B
0x1800068da  mov     rcx, [rbp+arg_20]
0x1800068de  mov     eax, [rbp+var_20]
0x1800068e1  movsd   xmm0, [rbp+var_28]
0x1800068e6  movsd   qword ptr [rcx], xmm0
0x1800068ea  mov     [rcx+8], eax
0x1800068ed  mov     rax, [rbp+arg_28]
0x1800068f1  mov     ecx, [rbp+arg_8]
0x1800068f4  mov     [rax], ecx
0x1800068f6  mov     rax, [rbp+arg_30]
0x1800068fa  mov     [rax], r12
0x1800068fd  test    rbx, rbx
0x180006900  jz      short loc_180006916
0x180006902  call    cs:__imp_GetProcessHeap
0x180006908  mov     r8, rbx; lpMem
0x18000690b  xor     edx, edx; dwFlags
0x18000690d  mov     rcx, rax; hHeap
0x180006910  call    cs:__imp_HeapFree
0x180006916  xor     eax, eax
0x180006918  mov     rbx, [rsp+80h+arg_10]
0x180006920  add     rsp, 80h
0x180006927  pop     r15
0x180006929  pop     r14
0x18000692b  pop     r13
0x18000692d  pop     r12
0x18000692f  pop     rdi
0x180006930  pop     rsi
0x180006931  pop     rbp
0x180006932  retn
0x180006933  mov     dword ptr [rbp+length], ecx
0x180006936  lea     rdx, [rbp+length]; length
0x18000693a  mov     rcx, r15; string
0x18000693d  call    cs:__imp_WindowsGetStringRawBuffer
0x180006943  mov     edx, dword ptr [rbp+length]
0x180006946  xor     r9d, r9d
0x180006949  mov     r8d, [rbp+arg_8]
0x18000694d  mov     rbx, rax
0x180006950  add     rax, 2
0x180006954  movsxd  rcx, esi
0x180006957  sub     edx, esi
0x180006959  lea     rcx, [rax+rcx*2]
0x18000695d  lea     rax, [rbp+var_3C]
0x180006961  mov     [rsp+80h+var_50], rax
0x180006966  lea     rax, [rbp+var_38]
0x18000696a  mov     [rsp+80h+var_58], rax
0x18000696f  lea     rax, [rbp+var_18]
0x180006973  mov     qword ptr [rsp+80h+var_60], rax
0x180006978  call    ?ParseSwizzle@ExpressionAnimationParser@Composition@UI@Windows@@CAXPEBGIW4DCOMPOSITION_EXPRESSION_TYPE@@_NPEAUExpressionErrorInfo@234@PEAPEAVSubchannelMaskInfo@@PEAI@Z; Windows::UI::Composition::ExpressionAnimationParser::ParseSwizzle(ushort const *,uint,DCOMPOSITION_EXPRESSION_TYPE,bool,Windows::UI::Composition::ExpressionErrorInfo *,SubchannelMaskInfo * *,uint *)
0x18000697d  mov     edi, dword ptr [rbp+var_18]
0x180006980  test    edi, edi
0x180006982  jnz     loc_180006A4E
0x180006988  mov     eax, dword ptr [rbp+length]
0x18000698b  mov     ecx, [rbp+var_3C]
0x18000698e  sub     eax, esi
0x180006990  dec     eax
0x180006992  cmp     eax, ecx
0x180006994  jnz     loc_180006AFA
0x18000699a  mov     rbx, [rbp+lpMem]
0x18000699e  mov     r12, [rbp+var_38]
0x1800069a2  jmp     loc_180006872
0x1800069a7  lea     rdx, [rbp+var_40]; length
0x1800069ab  mov     rcx, r15; string
0x1800069ae  call    cs:__imp_WindowsGetStringRawBuffer
0x1800069b4  mov     esi, [rbp+var_40]
0x1800069b7  mov     r14, rax
0x1800069ba  dec     esi
0x1800069bc  test    esi, esi
0x1800069be  js      loc_180006A82
0x1800069c4  movsxd  rcx, esi
0x1800069c7  cmp     word ptr [rax+rcx*2], 2Eh ; '.'
0x1800069cc  jnz     short loc_1800069BA
0x1800069ce  lea     r9, [rbp+string]; newString
0x1800069d2  mov     r8d, esi; length
0x1800069d5  xor     edx, edx; startIndex
0x1800069d7  mov     rcx, r15; string
0x1800069da  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x1800069e0  test    eax, eax
0x1800069e2  js      loc_180006A95
0x1800069e8  mov     rax, [rdi]
0x1800069eb  lea     rcx, [rbp+arg_8]
0x1800069ef  mov     rdx, [rbp+string]
0x1800069f3  lea     r9, [rbp+var_28]
0x1800069f7  mov     qword ptr [rsp+80h+var_60], rcx
0x1800069fc  lea     r8, [rbp+length]
0x180006a00  mov     rcx, rdi
0x180006a03  mov     rax, [rax+0C8h]
0x180006a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a0f  mov     cl, byte ptr [rbp+length]
0x180006a12  and     cl, 2
0x180006a15  neg     cl
0x180006a17  sbb     dl, dl
0x180006a19  and     dl, al
0x180006a1b  neg     dl
0x180006a1d  sbb     edi, edi
0x180006a1f  not     edi
0x180006a21  and     edi, 13h
0x180006a24  jmp     loc_1800067A4
0x180006a29  mov     r9, r13; newString
0x180006a2c  mov     r8d, esi; length
0x180006a2f  xor     edx, edx; startIndex
0x180006a31  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x180006a37  jmp     loc_18000688C
0x180006a3c  mov     edx, 8; unsigned __int64
0x180006a41  mov     rcx, rsi; void *
0x180006a44  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006a49  jmp     loc_1800068D2
0x180006a4e  xor     r13d, r13d
0x180006a51  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@ExpressionAnimationParser@Composition@UI@Windows@@0QBJB; int *
0x180006a58  mov     [rsp+80h+var_58], r13; void *
0x180006a5d  mov     r9d, r14d; int
0x180006a60  mov     [rsp+80h+var_60], 0BE4h; unsigned int
0x180006a68  lea     r8d, [r13+2]; unsigned int
0x180006a6c  lea     ecx, [r13+4]; unsigned int
0x180006a70  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180006a75  mov     rbx, [rbp+lpMem]
0x180006a79  mov     rsi, [rbp+var_38]
0x180006a7d  jmp     loc_1800068C9
0x180006a82  mov     edi, 13h
0x180006a87  or      esi, 0FFFFFFFFh
0x180006a8a  jmp     loc_1800067A4
0x180006a8f  call    ?OutOfMemory@FailFast@WRL2@Microsoft@@SAX_K@Z; Microsoft::WRL2::FailFast::OutOfMemory(unsigned __int64)
0x180006a95  call    ?OutOfMemory@FailFast@WRL2@Microsoft@@SAX_K@Z; Microsoft::WRL2::FailFast::OutOfMemory(unsigned __int64)
0x180006a9b  xor     edx, edx; length
0x180006a9d  mov     rcx, r15; string
0x180006aa0  call    cs:__imp_WindowsGetStringRawBuffer
0x180006aa6  test    edi, edi
0x180006aa8  jz      loc_180006B51
0x180006aae  cmp     edi, 4
0x180006ab1  jz      loc_180006B51
0x180006ab7  cmp     edi, 14h
0x180006aba  jz      loc_180006B51
0x180006ac0  mov     rdx, rax; struct Windows::UI::Composition::ExpressionErrorInfo *
0x180006ac3  lea     rcx, [rbp+var_18]; this
0x180006ac7  call    ?OriginateExpressionErrorInfo@Composition@UI@Windows@@YAXPEAUExpressionErrorInfo@123@PEBG@Z; Windows::UI::Composition::OriginateExpressionErrorInfo(Windows::UI::Composition::ExpressionErrorInfo *,ushort const *)
0x180006acc  mov     rcx, [rbp+38h]; this
0x180006ad0  lea     r8, aOnecoreuapWind_53; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180006ad7  mov     r9d, r14d; char *
0x180006ada  mov     edx, 7Ah ; 'z'; void *
0x180006adf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ae4  mov     rcx, [rbp+lpMem]; lpMem
0x180006ae8  test    rcx, rcx
0x180006aeb  jz      short loc_180006AF2
0x180006aed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006af2  mov     eax, r14d
0x180006af5  jmp     loc_180006918
0x180006afa  mov     [rbp+var_10], ecx
0x180006afd  mov     rdx, rbx; unsigned __int16 *
0x180006b00  lea     rcx, [rbp+var_18]; this
0x180006b04  mov     dword ptr [rbp+var_18], 11h
0x180006b0b  mov     dword ptr [rbp+var_18+4], eax
0x180006b0e  call    ?SetErrorContext@ExpressionErrorInfo@Composition@UI@Windows@@QEAAXPEBG@Z; Windows::UI::Composition::ExpressionErrorInfo::SetErrorContext(ushort const *)
0x180006b13  xor     r13d, r13d
0x180006b16  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@ExpressionAnimationParser@Composition@UI@Windows@@0QBJB; int *
0x180006b1d  mov     [rsp+80h+var_58], r13; void *
0x180006b22  mov     r9d, r14d; int
0x180006b25  mov     [rsp+80h+var_60], 0BF9h; unsigned int
0x180006b2d  lea     r8d, [r13+2]; unsigned int
0x180006b31  lea     ecx, [r13+4]; unsigned int
0x180006b35  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180006b3a  mov     edi, dword ptr [rbp+var_18]
0x180006b3d  jmp     loc_180006A75
0x180006b42  mov     rdx, [rbp+38h]
0x180006b46  mov     ecx, 8007000Eh
0x180006b4b  call    ModuleFailFastForHRESULT
0x180006b51  xor     ecx, ecx; char *
0x180006b53  call    ?Unexpected@FailFast@WRL2@Microsoft@@SAXPEBD@Z; Microsoft::WRL2::FailFast::Unexpected(char const *)
```
