# Windows::UI::Composition::ExpressionAnimationParser::ParseTargetProperty(HSTRING__ *,Windows::UI::Composition::CompositionObject *,Windows::UI::Composition::ExpressionErrorInfo *,ExpressionObjectPropertyInfo *,DCOMPOSITION_EXPRESSION_TYPE *,SubchannelMaskInfo * *,HSTRING__ * *)

- ea: `0x180007504`
- end: `0x18000789b`
- name: `?ParseTargetProperty@ExpressionAnimationParser@Composition@UI@Windows@@SAXPEAUHSTRING__@@PEAVCompositionObject@234@PEAUExpressionErrorInfo@234@PEAVExpressionObjectPropertyInfo@@PEAW4DCOMPOSITION_EXPRESSION_TYPE@@PEAPEAVSubchannelMaskInfo@@PEAPEAU5@@Z`
- size: `919`
- prototype: `void __usercall(HSTRING string@<rcx>, struct Windows::UI::Composition::CompositionObject *@<rdx>, struct Windows::UI::Composition::ExpressionErrorInfo *@<r8>, struct ExpressionObjectPropertyInfo *@<r9>, enum DCOMPOSITION_EXPRESSION_TYPE *, struct SubchannelMaskInfo **, HSTRING *)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007250`
- `0x1800a7908`
- `0x1800a8d7c`
- `0x18016e8ac`

## callees

- `0x180006590`
- `0x180007504`
- `0x1800078a4`
- `0x180007cc4`
- `0x180008034`
- `0x1800df108`
- `0x1800ebd74`
- `0x1800f6f34`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800075e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800075e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007595`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007696`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007595`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007696`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007587`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007688`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007587`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007688`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x18000775b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1800077bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x18000775b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1800077bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000765c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000765c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800076c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000772f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800076c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000772f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800075a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800075a8`

## pseudocode

```c
void __fastcall Windows::UI::Composition::ExpressionAnimationParser::ParseTargetProperty(
        HSTRING string,
        struct Windows::UI::Composition::CompositionObject *a2,
        struct Windows::UI::Composition::ExpressionErrorInfo *a3,
        struct ExpressionObjectPropertyInfo *a4,
        enum DCOMPOSITION_EXPRESSION_TYPE *a5,
        struct SubchannelMaskInfo **a6,
        HSTRING *newString)
{
  struct SubchannelMaskInfo *v8; // r12
  unsigned __int8 v12; // al
  void *v13; // r14
  int v14; // edi
  _WORD *v15; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v17; // rax
  _WORD *v18; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  _WORD *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  _WORD *v24; // rcx
  HRESULT v25; // eax
  unsigned __int64 v26; // rcx
  struct SubchannelMaskInfo **v27; // rax
  struct SubchannelMaskInfo *v28; // rdi
  void *v29; // rsi
  HANDLE v30; // rax
  const unsigned __int16 *v31; // rsi
  UINT32 v32; // eax
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v34; // rcx
  unsigned __int8 v35; // al
  UINT32 v36; // [rsp+40h] [rbp-28h] BYREF
  int v37; // [rsp+44h] [rbp-24h]
  struct SubchannelMaskInfo *v38; // [rsp+48h] [rbp-20h]
  HSTRING stringa; // [rsp+50h] [rbp-18h] BYREF
  void *retaddr; // [rsp+A8h] [rbp+40h]
  UINT32 length; // [rsp+B8h] [rbp+50h] BYREF

  v8 = 0;
  v38 = 0;
  v37 = 0;
  stringa = 0;
  v36 = 0;
  length = 0;
  v12 = (*(__int64 (__fastcall **)(struct Windows::UI::Composition::CompositionObject *, HSTRING, UINT32 *))(*(_QWORD *)a2 + 200LL))(
          a2,
          string,
          &length);
  if ( ((unsigned __int8)-((length & 2) != 0) & v12) != 0 )
  {
    v13 = (void *)*((_QWORD *)a3 + 2);
    v14 = -1;
    *(_QWORD *)a3 = 0;
    *((_DWORD *)a3 + 2) = 0;
    v15 = 0;
    if ( v13 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v13);
      *((_QWORD *)a3 + 2) = 0;
    }
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, &v36);
    v14 = v36;
    v15 = StringRawBuffer;
    do
    {
      if ( --v14 < 0 )
      {
        v14 = -1;
        goto LABEL_42;
      }
    }
    while ( StringRawBuffer[v14] != 46 );
    if ( WindowsSubstringWithSpecifiedLength(string, 0, v14, &stringa) < 0 )
      Microsoft::WRL2::FailFast::OutOfMemory(v34);
    v35 = (*(__int64 (__fastcall **)(struct Windows::UI::Composition::CompositionObject *, HSTRING, UINT32 *, struct ExpressionObjectPropertyInfo *, enum DCOMPOSITION_EXPRESSION_TYPE *))(*(_QWORD *)a2 + 200LL))(
            a2,
            stringa,
            &length,
            a4,
            a5);
    if ( ((unsigned __int8)-((length & 2) != 0) & v35) != 0 )
    {
      *(_QWORD *)a3 = 0;
      *((_DWORD *)a3 + 2) = 0;
      Windows::UI::Composition::ExpressionErrorInfo::ClearErrorContext(a3);
      goto LABEL_4;
    }
LABEL_42:
    *(_DWORD *)a3 = 19;
  }
LABEL_4:
  if ( stringa )
    WindowsDeleteString(stringa);
  if ( *(_DWORD *)a3 )
  {
    *((_DWORD *)a3 + 2) = v36;
    *((_DWORD *)a3 + 1) = 0;
    if ( v15 )
    {
      if ( !*((_QWORD *)a3 + 2) )
      {
        v17 = GetProcessHeap();
        v18 = HeapAlloc(v17, 0, 0xF2u);
        if ( !v18 )
          ModuleFailFastForHRESULT(2147942414LL, retaddr, v19, v20);
        *((_QWORD *)a3 + 2) = v18;
        *v18 = 0;
      }
      v21 = (_WORD *)*((_QWORD *)a3 + 2);
      v22 = 2147483646;
      v23 = 120;
      do
      {
        if ( !v22 )
          break;
        if ( !*v15 )
          break;
        *v21++ = *v15++;
        --v22;
        --v23;
      }
      while ( v23 );
      v24 = v21 - 1;
      if ( v23 )
        v24 = v21;
      *v24 = 0;
    }
    else
    {
      Windows::UI::Composition::ExpressionErrorInfo::ClearErrorContext(a3);
    }
    if ( *(_DWORD *)a3 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(
        4u,
        &Windows::UI::Composition::ExpressionAnimationParser::MILINSTRUMENTATIONHRESULTLIST,
        2u,
        -2147024809,
        0xBCDu,
        0);
      return;
    }
  }
  if ( v14 > -1 )
  {
    length = 0;
    v31 = WindowsGetStringRawBuffer(string, &length);
    Windows::UI::Composition::ExpressionAnimationParser::ParseSwizzle(
      &v31[v14 + 1],
      length - v14,
      *(unsigned int *)a5,
      0);
    if ( *(_DWORD *)a3 )
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
      v32 = length - v14 - 1;
      if ( v32 == v37 )
      {
        v8 = v38;
        goto LABEL_20;
      }
      *((_DWORD *)a3 + 2) = v37;
      *(_DWORD *)a3 = 17;
      *((_DWORD *)a3 + 1) = v32;
      Windows::UI::Composition::ExpressionErrorInfo::SetErrorContext(a3, v31);
      MilInstrumentationCheckHR_MaybeFailFast(
        4u,
        &Windows::UI::Composition::ExpressionAnimationParser::MILINSTRUMENTATIONHRESULTLIST,
        2u,
        -2147024809,
        0xBF9u,
        0);
    }
    v28 = v38;
LABEL_26:
    if ( v28 )
      operator delete(v28, 8u);
    return;
  }
LABEL_20:
  if ( newString )
  {
    if ( v14 > -1 )
      v25 = WindowsSubstringWithSpecifiedLength(string, 0, v14, newString);
    else
      v25 = WindowsDuplicateString(string, newString);
    if ( v25 < 0 )
      Microsoft::WRL2::FailFast::OutOfMemory(v26);
  }
  v27 = a6;
  v28 = 0;
  v29 = (void *)*((_QWORD *)a3 + 2);
  *(_QWORD *)a3 = 0;
  *((_DWORD *)a3 + 2) = 0;
  *v27 = v8;
  if ( v29 )
  {
    v30 = GetProcessHeap();
    HeapFree(v30, 0, v29);
    *((_QWORD *)a3 + 2) = 0;
    goto LABEL_26;
  }
}

```

## disassembly

```asm
0x180007504  push    rbp
0x180007506  push    rbx
0x180007507  push    rsi
0x180007508  push    rdi
0x180007509  push    r12
0x18000750b  push    r13
0x18000750d  push    r14
0x18000750f  push    r15
0x180007511  mov     rbp, rsp
0x180007514  sub     rsp, 68h
0x180007518  xor     eax, eax
0x18000751a  mov     r15, rcx
0x18000751d  mov     rcx, [rbp+arg_20]
0x180007521  mov     r12d, eax
0x180007524  mov     [rbp+var_20], rax
0x180007528  mov     r14, rdx
0x18000752b  mov     [rbp+var_24], eax
0x18000752e  mov     rbx, r8
0x180007531  mov     [rbp+string], rax
0x180007535  lea     r8, [rbp+length]
0x180007539  mov     [rbp+var_28], eax
0x18000753c  mov     r13, r9
0x18000753f  mov     [rbp+length], eax
0x180007542  mov     rax, [rdx]
0x180007545  mov     rdx, r15
0x180007548  mov     qword ptr [rsp+68h+var_48], rcx
0x18000754d  mov     rcx, r14
0x180007550  mov     rax, [rax+0C8h]
0x180007557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000755c  mov     ecx, [rbp+length]
0x18000755f  and     cl, 2
0x180007562  neg     cl
0x180007564  sbb     cl, cl
0x180007566  test    al, cl
0x180007568  jz      loc_180007728
0x18000756e  mov     r14, [rbx+10h]
0x180007572  xor     r13d, r13d
0x180007575  or      edi, 0FFFFFFFFh
0x180007578  mov     [rbx], r13
0x18000757b  mov     [rbx+8], r13d
0x18000757f  mov     esi, r13d
0x180007582  test    r14, r14
0x180007585  jz      short loc_18000759F
0x180007587  call    cs:__imp_GetProcessHeap
0x18000758d  mov     r8, r14; lpMem
0x180007590  xor     edx, edx; dwFlags
0x180007592  mov     rcx, rax; hHeap
0x180007595  call    cs:__imp_HeapFree
0x18000759b  mov     [rbx+10h], r13
0x18000759f  mov     rcx, [rbp+string]; string
0x1800075a3  test    rcx, rcx
0x1800075a6  jz      short loc_1800075AE
0x1800075a8  call    cs:__imp_WindowsDeleteString
0x1800075ae  cmp     [rbx], r13d
0x1800075b1  jz      loc_180007642
0x1800075b7  mov     eax, [rbp+var_28]
0x1800075ba  mov     [rbx+8], eax
0x1800075bd  mov     [rbx+4], r13d
0x1800075c1  test    rsi, rsi
0x1800075c4  jz      loc_18000781C
0x1800075ca  cmp     [rbx+10h], r13
0x1800075ce  jnz     short loc_1800075F8
0x1800075d0  call    cs:__imp_GetProcessHeap
0x1800075d6  xor     edx, edx; dwFlags
0x1800075d8  mov     r8d, 0F2h; dwBytes
0x1800075de  mov     rcx, rax; hHeap
0x1800075e1  call    cs:__imp_HeapAlloc
0x1800075e7  test    rax, rax
0x1800075ea  jz      loc_18000788C
0x1800075f0  mov     [rbx+10h], rax
0x1800075f4  mov     [rax], r13w
0x1800075f8  mov     rax, [rbx+10h]
0x1800075fc  mov     ecx, 7FFFFFFEh
0x180007601  mov     edx, 78h ; 'x'
0x180007606  test    rcx, rcx
0x180007609  jz      short loc_18000762A
0x18000760b  movzx   r8d, word ptr [rsi]
0x18000760f  test    r8w, r8w
0x180007613  jz      short loc_18000762A
0x180007615  mov     [rax], r8w
0x180007619  add     rsi, 2
0x18000761d  add     rax, 2
0x180007621  dec     rcx
0x180007624  sub     rdx, 1
0x180007628  jnz     short loc_180007606
0x18000762a  test    rdx, rdx
0x18000762d  lea     rcx, [rax-2]
0x180007631  cmovnz  rcx, rax
0x180007635  mov     [rcx], r13w
0x180007639  cmp     [rbx], r13d
0x18000763c  jnz     loc_180007835
0x180007642  cmp     edi, 0FFFFFFFFh
0x180007645  jg      short loc_1800076BA
0x180007647  mov     rdx, [rbp+newString]; newString
0x18000764b  test    rdx, rdx
0x18000764e  jz      short loc_18000766A
0x180007650  mov     rcx, r15; string
0x180007653  cmp     edi, 0FFFFFFFFh
0x180007656  jg      loc_1800077B4
0x18000765c  call    cs:__imp_WindowsDuplicateString
0x180007662  test    eax, eax
0x180007664  js      loc_180007829
0x18000766a  mov     rax, [rbp+arg_28]
0x18000766e  mov     rdi, r13
0x180007671  mov     rsi, [rbx+10h]
0x180007675  mov     qword ptr [rbx], 0
0x18000767c  mov     [rbx+8], r13d
0x180007680  mov     [rax], r12
0x180007683  test    rsi, rsi
0x180007686  jz      short loc_1800076A9
0x180007688  call    cs:__imp_GetProcessHeap
0x18000768e  mov     r8, rsi; lpMem
0x180007691  xor     edx, edx; dwFlags
0x180007693  mov     rcx, rax; hHeap
0x180007696  call    cs:__imp_HeapFree
0x18000769c  mov     [rbx+10h], r13
0x1800076a0  test    rdi, rdi
0x1800076a3  jnz     loc_1800077C7
0x1800076a9  add     rsp, 68h
0x1800076ad  pop     r15
0x1800076af  pop     r14
0x1800076b1  pop     r13
0x1800076b3  pop     r12
0x1800076b5  pop     rdi
0x1800076b6  pop     rsi
0x1800076b7  pop     rbx
0x1800076b8  pop     rbp
0x1800076b9  retn
0x1800076ba  lea     rdx, [rbp+length]; length
0x1800076be  mov     [rbp+length], r13d
0x1800076c2  mov     rcx, r15; string
0x1800076c5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800076cb  mov     edx, [rbp+length]
0x1800076ce  xor     r9d, r9d
0x1800076d1  mov     rsi, rax
0x1800076d4  movsxd  rcx, edi
0x1800076d7  add     rax, 2
0x1800076db  sub     edx, edi
0x1800076dd  lea     rcx, [rax+rcx*2]
0x1800076e1  lea     rax, [rbp+var_24]
0x1800076e5  mov     [rsp+68h+var_38], rax
0x1800076ea  lea     rax, [rbp+var_20]
0x1800076ee  mov     [rsp+68h+var_40], rax
0x1800076f3  mov     rax, [rbp+arg_20]
0x1800076f7  mov     qword ptr [rsp+68h+var_48], rbx
0x1800076fc  mov     r8d, [rax]
0x1800076ff  call    ?ParseSwizzle@ExpressionAnimationParser@Composition@UI@Windows@@CAXPEBGIW4DCOMPOSITION_EXPRESSION_TYPE@@_NPEAUExpressionErrorInfo@234@PEAPEAVSubchannelMaskInfo@@PEAI@Z; Windows::UI::Composition::ExpressionAnimationParser::ParseSwizzle(ushort const *,uint,DCOMPOSITION_EXPRESSION_TYPE,bool,Windows::UI::Composition::ExpressionErrorInfo *,SubchannelMaskInfo * *,uint *)
0x180007704  cmp     [rbx], r13d
0x180007707  jnz     loc_1800077D9
0x18000770d  mov     eax, [rbp+length]
0x180007710  mov     ecx, [rbp+var_24]
0x180007713  sub     eax, edi
0x180007715  dec     eax
0x180007717  cmp     eax, ecx
0x180007719  jnz     loc_180007863
0x18000771f  mov     r12, [rbp+var_20]
0x180007723  jmp     loc_180007647
0x180007728  lea     rdx, [rbp+var_28]; length
0x18000772c  mov     rcx, r15; string
0x18000772f  call    cs:__imp_WindowsGetStringRawBuffer
0x180007735  mov     edi, [rbp+var_28]
0x180007738  mov     rsi, rax
0x18000773b  dec     edi
0x18000773d  test    edi, edi
0x18000773f  js      loc_18000780B
0x180007745  movsxd  rcx, edi
0x180007748  cmp     word ptr [rax+rcx*2], 2Eh ; '.'
0x18000774d  jnz     short loc_18000773B
0x18000774f  lea     r9, [rbp+string]; newString
0x180007753  mov     r8d, edi; length
0x180007756  xor     edx, edx; startIndex
0x180007758  mov     rcx, r15; string
0x18000775b  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x180007761  test    eax, eax
0x180007763  js      loc_18000782F
0x180007769  mov     rax, [r14]
0x18000776c  lea     r8, [rbp+length]
0x180007770  mov     rcx, [rbp+arg_20]
0x180007774  mov     r9, r13
0x180007777  mov     rdx, [rbp+string]
0x18000777b  mov     qword ptr [rsp+68h+var_48], rcx
0x180007780  mov     rcx, r14
0x180007783  mov     rax, [rax+0C8h]
0x18000778a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000778f  mov     ecx, [rbp+length]
0x180007792  and     cl, 2
0x180007795  neg     cl
0x180007797  sbb     cl, cl
0x180007799  xor     r13d, r13d
0x18000779c  test    al, cl
0x18000779e  jz      short loc_180007811
0x1800077a0  mov     rcx, rbx; this
0x1800077a3  mov     [rbx], r13
0x1800077a6  mov     [rbx+8], r13d
0x1800077aa  call    ?ClearErrorContext@ExpressionErrorInfo@Composition@UI@Windows@@AEAAXXZ; Windows::UI::Composition::ExpressionErrorInfo::ClearErrorContext(void)
0x1800077af  jmp     loc_18000759F
0x1800077b4  mov     r9, rdx; newString
0x1800077b7  mov     r8d, edi; length
0x1800077ba  xor     edx, edx; startIndex
0x1800077bc  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x1800077c2  jmp     loc_180007662
0x1800077c7  mov     edx, 8; unsigned __int64
0x1800077cc  mov     rcx, rdi; void *
0x1800077cf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800077d4  jmp     loc_1800076A9
0x1800077d9  mov     [rsp+68h+var_40], r13; void *
0x1800077de  mov     [rsp+68h+var_48], 0BE4h; unsigned int
0x1800077e6  mov     r8d, 2; unsigned int
0x1800077ec  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@ExpressionAnimationParser@Composition@UI@Windows@@0QBJB; int *
0x1800077f3  mov     r9d, 80070057h; int
0x1800077f9  lea     ecx, [r8+2]; unsigned int
0x1800077fd  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180007802  mov     rdi, [rbp+var_20]
0x180007806  jmp     loc_1800076A0
0x18000780b  or      edi, 0FFFFFFFFh
0x18000780e  xor     r13d, r13d
0x180007811  mov     dword ptr [rbx], 13h
0x180007817  jmp     loc_18000759F
0x18000781c  mov     rcx, rbx; this
0x18000781f  call    ?ClearErrorContext@ExpressionErrorInfo@Composition@UI@Windows@@AEAAXXZ; Windows::UI::Composition::ExpressionErrorInfo::ClearErrorContext(void)
0x180007824  jmp     loc_180007639
0x180007829  call    ?OutOfMemory@FailFast@WRL2@Microsoft@@SAX_K@Z; Microsoft::WRL2::FailFast::OutOfMemory(unsigned __int64)
0x18000782f  call    ?OutOfMemory@FailFast@WRL2@Microsoft@@SAX_K@Z; Microsoft::WRL2::FailFast::OutOfMemory(unsigned __int64)
0x180007835  mov     r8d, 2; unsigned int
0x18000783b  mov     [rsp+68h+var_40], r13; void *
0x180007840  mov     r9d, 80070057h; int
0x180007846  mov     [rsp+68h+var_48], 0BCDh; unsigned int
0x18000784e  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@ExpressionAnimationParser@Composition@UI@Windows@@0QBJB; int *
0x180007855  lea     ecx, [r8+2]; unsigned int
0x180007859  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18000785e  jmp     loc_1800076A9
0x180007863  mov     [rbx+8], ecx
0x180007866  mov     rdx, rsi; unsigned __int16 *
0x180007869  mov     rcx, rbx; this
0x18000786c  mov     dword ptr [rbx], 11h
0x180007872  mov     [rbx+4], eax
0x180007875  call    ?SetErrorContext@ExpressionErrorInfo@Composition@UI@Windows@@QEAAXPEBG@Z; Windows::UI::Composition::ExpressionErrorInfo::SetErrorContext(ushort const *)
0x18000787a  mov     [rsp+68h+var_40], r13
0x18000787f  mov     [rsp+68h+var_48], 0BF9h
0x180007887  jmp     loc_1800077E6
0x18000788c  mov     rdx, [rbp+40h]
0x180007890  mov     ecx, 8007000Eh
0x180007895  call    ModuleFailFastForHRESULT
```
