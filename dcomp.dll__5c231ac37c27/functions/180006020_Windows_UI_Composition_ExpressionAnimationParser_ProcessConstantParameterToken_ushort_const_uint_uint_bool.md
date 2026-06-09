# Windows::UI::Composition::ExpressionAnimationParser::ProcessConstantParameterToken(ushort const *,uint,uint,bool)

- ea: `0x180006020`
- end: `0x180006385`
- name: `?ProcessConstantParameterToken@ExpressionAnimationParser@Composition@UI@Windows@@AEAAJPEBGII_N@Z`
- size: `869`
- prototype: `__int64 __fastcall(Windows::UI::Composition::ExpressionAnimationParser *this, const unsigned __int16 *, UINT32, unsigned int, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800059f8`
- `0x180006020`

## callees

- `0x180006020`
- `0x180006590`
- `0x180007cc4`
- `0x1800890b0`
- `0x1800df108`
- `0x1800f6f10`
- `0x1800f6f34`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006202`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006202`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800061f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800061f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000608f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000608f`
- `ntdll!RtlLookupElementGenericTable` at `0x1800060c8`
- `ntdll!RtlLookupElementGenericTable` at `0x1800060c8`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::ExpressionAnimationParser::ProcessConstantParameterToken(
        Windows::UI::Composition::ExpressionAnimationParser *this,
        const unsigned __int16 *a2,
        UINT32 a3,
        unsigned int a4,
        bool a5)
{
  const unsigned __int16 *v5; // rsi
  __int64 v8; // r15
  char v9; // r12
  HRESULT v10; // eax
  int v11; // ebx
  __int64 v12; // rdx
  _DWORD *v13; // rbx
  __int64 v14; // rcx
  volatile signed __int32 *v15; // rcx
  int v16; // r9d
  unsigned int v17; // r15d
  __int64 v18; // rax
  __int64 v19; // rdi
  HANDLE ProcessHeap; // rax
  _WORD *v21; // rax
  __int64 v22; // r8
  _WORD *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rdx
  _WORD *v26; // rcx
  void *v28; // rcx
  unsigned __int64 v29; // rdx
  unsigned int v30; // [rsp+20h] [rbp-61h]
  unsigned int v31; // [rsp+30h] [rbp-51h]
  HSTRING string; // [rsp+38h] [rbp-49h] BYREF
  HSTRING Buffer; // [rsp+48h] [rbp-39h] BYREF
  int v35; // [rsp+50h] [rbp-31h]
  __int128 v36; // [rsp+58h] [rbp-29h]
  int v37; // [rsp+68h] [rbp-19h]
  void *v38; // [rsp+70h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-1h] BYREF
  void *retaddr; // [rsp+D8h] [rbp+57h]

  string = 0;
  v31 = a4 + a3;
  v5 = a2;
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  v8 = *((_QWORD *)this + !a5 + 12);
  v9 = 0;
  v10 = WindowsCreateStringReference(a2, a3, &hstringHeader, &string);
  v11 = v10;
  if ( v10 < 0 )
  {
    v30 = 849;
LABEL_31:
    v16 = v10;
    goto LABEL_14;
  }
  Buffer = string;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v13 = RtlLookupElementGenericTable((PRTL_GENERIC_TABLE)(v8 + 208), &Buffer);
  if ( v35 == 104 )
  {
    v28 = v38;
    if ( v38 )
    {
      v29 = 24;
      goto LABEL_39;
    }
  }
  else if ( v35 == 265 )
  {
    v28 = v38;
    if ( v38 )
    {
      v29 = 64;
LABEL_39:
      operator delete(v28, v29);
      v38 = 0;
    }
  }
  v14 = *((_QWORD *)&v36 + 1);
  if ( *((_QWORD *)&v36 + 1) )
  {
    *((_QWORD *)&v36 + 1) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = (volatile signed __int32 *)v36;
  if ( (_QWORD)v36 )
  {
    *(_QWORD *)&v36 = 0;
    if ( _InterlockedExchangeAdd(v15 + 4, 0xFFFFFFFF) == 1 )
    {
      LOBYTE(v12) = 1;
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v15 + 64LL))(v15, v12);
    }
  }
  if ( !v13 )
  {
    if ( a5 )
    {
      v11 = -2147467259;
      *(_DWORD *)(*((_QWORD *)this + 12) + 960LL) = 11;
      MilInstrumentationCheckHR_MaybeFailFast(
        4u,
        &Windows::UI::Composition::ExpressionAnimationParser::MILINSTRUMENTATIONHRESULTLIST,
        2u,
        -2147467259,
        0x37Du,
        0);
      goto LABEL_15;
    }
    v10 = Windows::UI::Composition::ExpressionAnimationParser::ProcessConstantParameterToken(this, v5, a3, a4, 1);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v9 = 1;
      goto LABEL_15;
    }
    v30 = 880;
    goto LABEL_31;
  }
  if ( !v13[2] )
  {
    v16 = -2147467259;
    v11 = -2147467259;
    v30 = 864;
    *(_DWORD *)(*((_QWORD *)this + 12) + 960LL) = 14;
LABEL_14:
    MilInstrumentationCheckHR_MaybeFailFast(
      4u,
      &Windows::UI::Composition::ExpressionAnimationParser::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      v16,
      v30,
      0);
    goto LABEL_15;
  }
  v11 = Windows::UI::Composition::ExpressionAnimationBuilder::PushConstantParameter(*((_QWORD *)this + 11), string);
  if ( v11 < 0 )
  {
    v17 = v31;
    *(_DWORD *)(*((_QWORD *)this + 12) + 964LL) = a4;
    *(_DWORD *)(*((_QWORD *)this + 12) + 968LL) = v31;
    MilInstrumentationCheckHR_MaybeFailFast(
      4u,
      &Windows::UI::Composition::ExpressionAnimationParser::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      v11,
      0x357u,
      0);
    goto LABEL_16;
  }
LABEL_15:
  v17 = v31;
LABEL_16:
  v18 = *((_QWORD *)this + 12);
  if ( *(_DWORD *)(v18 + 960) && !v9 )
  {
    *(_DWORD *)(v18 + 964) = a4;
    *(_DWORD *)(*((_QWORD *)this + 12) + 968LL) = v17;
    v19 = *((_QWORD *)this + 12);
    if ( v5 )
    {
      if ( !*(_QWORD *)(v19 + 976) )
      {
        ProcessHeap = GetProcessHeap();
        v21 = HeapAlloc(ProcessHeap, 0, 0xF2u);
        if ( !v21 )
          ModuleFailFastForHRESULT(2147942414LL, retaddr, v22, 0);
        *(_QWORD *)(v19 + 976) = v21;
        *v21 = 0;
      }
      v23 = *(_WORD **)(v19 + 976);
      v24 = 2147483646;
      v25 = 120;
      do
      {
        if ( !v24 )
          break;
        if ( !*v5 )
          break;
        *v23++ = *v5++;
        --v24;
        --v25;
      }
      while ( v25 );
      v26 = v23 - 1;
      if ( v25 )
        v26 = v23;
      *v26 = 0;
    }
    else
    {
      Windows::UI::Composition::ExpressionErrorInfo::ClearErrorContext((Windows::UI::Composition::ExpressionErrorInfo *)(v19 + 960));
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180006020  push    rbp
0x180006022  push    rbx
0x180006023  push    rsi
0x180006024  push    rdi
0x180006025  push    r12
0x180006027  push    r14
0x180006029  push    r15
0x18000602b  lea     rbp, [rsp-1Fh]
0x180006030  sub     rsp, 0A0h
0x180006037  mov     rax, cs:__security_cookie
0x18000603e  xor     rax, rsp
0x180006041  mov     [rbp+4Fh+var_38], rax
0x180006045  xor     eax, eax
0x180006047  mov     [rbp+4Fh+string], 0
0x18000604f  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved+10h], rax
0x180006053  mov     r10d, r8d
0x180006056  lea     eax, [r9+r8]
0x18000605a  mov     [rbp+4Fh+length], r8d
0x18000605e  mov     [rbp+4Fh+var_A0], eax
0x180006061  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x180006065  movzx   eax, [rbp+4Fh+arg_20]
0x180006069  mov     rsi, rdx
0x18000606c  xor     rax, 1
0x180006070  xorps   xmm0, xmm0
0x180006073  movups  xmmword ptr [rbp+4Fh+hstringHeader.Reserved], xmm0
0x180006077  mov     r14d, r9d
0x18000607a  mov     rdi, rcx
0x18000607d  lea     r9, [rbp+4Fh+string]; string
0x180006081  mov     edx, r10d; length
0x180006084  mov     r15, [rcx+rax*8+60h]
0x180006089  xor     r12b, r12b
0x18000608c  mov     rcx, rsi; sourceString
0x18000608f  call    cs:__imp_WindowsCreateStringReference
0x180006095  mov     ebx, eax
0x180006097  test    eax, eax
0x180006099  js      loc_180006283
0x18000609f  mov     rax, [rbp+4Fh+string]
0x1800060a3  lea     rcx, [r15+0D0h]; Table
0x1800060aa  xorps   xmm0, xmm0
0x1800060ad  mov     [rbp+4Fh+Buffer], rax
0x1800060b1  lea     rdx, [rbp+4Fh+Buffer]; Buffer
0x1800060b5  mov     [rbp+4Fh+var_80], 0
0x1800060bc  movdqu  [rbp+4Fh+var_78], xmm0
0x1800060c1  mov     [rbp+4Fh+var_68], 0
0x1800060c8  call    cs:__imp_RtlLookupElementGenericTable
0x1800060ce  xor     r15d, r15d
0x1800060d1  mov     rbx, rax
0x1800060d4  cmp     [rbp+4Fh+var_80], 68h ; 'h'
0x1800060d8  jz      loc_180006362
0x1800060de  cmp     [rbp+4Fh+var_80], 109h
0x1800060e5  jz      loc_18000633A
0x1800060eb  mov     rcx, qword ptr [rbp+4Fh+var_78+8]
0x1800060ef  test    rcx, rcx
0x1800060f2  jz      short loc_180006104
0x1800060f4  mov     qword ptr [rbp+4Fh+var_78+8], r15
0x1800060f8  mov     rax, [rcx]
0x1800060fb  mov     rax, [rax+10h]
0x1800060ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006104  mov     rcx, qword ptr [rbp+4Fh+var_78]
0x180006108  test    rcx, rcx
0x18000610b  jz      short loc_18000612C
0x18000610d  mov     qword ptr [rbp+4Fh+var_78], r15
0x180006111  or      eax, 0FFFFFFFFh
0x180006114  lock xadd [rcx+10h], eax
0x180006119  cmp     eax, 1
0x18000611c  jnz     short loc_18000612C
0x18000611e  mov     rax, [rcx]
0x180006121  mov     dl, 1
0x180006123  mov     rax, [rax+40h]
0x180006127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000612c  test    rbx, rbx
0x18000612f  jnz     short loc_180006161
0x180006131  cmp     [rbp+4Fh+arg_20], r15b
0x180006135  jz      loc_18000629C
0x18000613b  mov     rax, [rdi+60h]
0x18000613f  mov     r9d, 80004005h
0x180006145  mov     [rsp+0D0h+var_A8], r15
0x18000614a  mov     ebx, r9d
0x18000614d  mov     dword ptr [rsp+0D0h+var_B0], 37Dh
0x180006155  mov     dword ptr [rax+3C0h], 0Bh
0x18000615f  jmp     short loc_180006192
0x180006161  mov     r8d, [rbx+8]
0x180006165  test    r8d, r8d
0x180006168  jnz     loc_1800062DA
0x18000616e  mov     rax, [rdi+60h]
0x180006172  mov     r9d, 80004005h; int
0x180006178  mov     [rsp+0D0h+var_A8], r15; void *
0x18000617d  mov     ebx, r9d
0x180006180  mov     dword ptr [rsp+0D0h+var_B0], 360h; unsigned int
0x180006188  mov     dword ptr [rax+3C0h], 0Eh
0x180006192  mov     r8d, 2; unsigned int
0x180006198  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@ExpressionAnimationParser@Composition@UI@Windows@@0QBJB; int *
0x18000619f  lea     ecx, [r8+2]; unsigned int
0x1800061a3  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800061a8  mov     r15d, [rbp+4Fh+var_A0]
0x1800061ac  mov     rax, [rdi+60h]
0x1800061b0  xor     r9d, r9d
0x1800061b3  cmp     [rax+3C0h], r9d
0x1800061ba  jz      loc_180006263
0x1800061c0  test    r12b, r12b
0x1800061c3  jnz     loc_180006263
0x1800061c9  mov     [rax+3C4h], r14d
0x1800061d0  mov     rax, [rdi+60h]
0x1800061d4  mov     [rax+3C8h], r15d
0x1800061db  mov     rdi, [rdi+60h]
0x1800061df  test    rsi, rsi
0x1800061e2  jz      loc_1800062CC
0x1800061e8  cmp     [rdi+3D0h], r9
0x1800061ef  jnz     short loc_18000621F
0x1800061f1  call    cs:__imp_GetProcessHeap
0x1800061f7  xor     edx, edx; dwFlags
0x1800061f9  mov     r8d, 0F2h; dwBytes
0x1800061ff  mov     rcx, rax; hHeap
0x180006202  call    cs:__imp_HeapAlloc
0x180006208  xor     r9d, r9d
0x18000620b  test    rax, rax
0x18000620e  jz      loc_180006376
0x180006214  mov     [rdi+3D0h], rax
0x18000621b  mov     [rax], r9w
0x18000621f  mov     rax, [rdi+3D0h]
0x180006226  mov     ecx, 7FFFFFFEh
0x18000622b  mov     edx, 78h ; 'x'
0x180006230  test    rcx, rcx
0x180006233  jz      short loc_180006254
0x180006235  movzx   r8d, word ptr [rsi]
0x180006239  test    r8w, r8w
0x18000623d  jz      short loc_180006254
0x18000623f  mov     [rax], r8w
0x180006243  add     rsi, 2
0x180006247  add     rax, 2
0x18000624b  dec     rcx
0x18000624e  sub     rdx, 1
0x180006252  jnz     short loc_180006230
0x180006254  test    rdx, rdx
0x180006257  lea     rcx, [rax-2]
0x18000625b  cmovnz  rcx, rax
0x18000625f  mov     [rcx], r9w
0x180006263  mov     eax, ebx
0x180006265  mov     rcx, [rbp+4Fh+var_38]
0x180006269  xor     rcx, rsp; StackCookie
0x18000626c  call    __security_check_cookie
0x180006271  add     rsp, 0A0h
0x180006278  pop     r15
0x18000627a  pop     r14
0x18000627c  pop     r12
0x18000627e  pop     rdi
0x18000627f  pop     rsi
0x180006280  pop     rbx
0x180006281  pop     rbp
0x180006282  retn
0x180006283  mov     [rsp+0D0h+var_A8], 0
0x18000628c  mov     dword ptr [rsp+0D0h+var_B0], 351h
0x180006294  mov     r9d, eax
0x180006297  jmp     loc_180006192
0x18000629c  mov     r8d, [rbp+4Fh+length]; unsigned int
0x1800062a0  mov     r9d, r14d; unsigned int
0x1800062a3  mov     rdx, rsi; unsigned __int16 *
0x1800062a6  mov     [rsp+0D0h+var_B0], 1; bool
0x1800062ab  mov     rcx, rdi; this
0x1800062ae  call    ?ProcessConstantParameterToken@ExpressionAnimationParser@Composition@UI@Windows@@AEAAJPEBGII_N@Z; Windows::UI::Composition::ExpressionAnimationParser::ProcessConstantParameterToken(ushort const *,uint,uint,bool)
0x1800062b3  mov     ebx, eax
0x1800062b5  test    eax, eax
0x1800062b7  jns     loc_18000635A
0x1800062bd  mov     [rsp+0D0h+var_A8], r15
0x1800062c2  mov     dword ptr [rsp+0D0h+var_B0], 370h
0x1800062ca  jmp     short loc_180006294
0x1800062cc  lea     rcx, [rdi+3C0h]; this
0x1800062d3  call    ?ClearErrorContext@ExpressionErrorInfo@Composition@UI@Windows@@AEAAXXZ; Windows::UI::Composition::ExpressionErrorInfo::ClearErrorContext(void)
0x1800062d8  jmp     short loc_180006263
0x1800062da  mov     rdx, [rbp+4Fh+string]
0x1800062de  mov     rcx, [rdi+58h]
0x1800062e2  call    ?PushConstantParameter@ExpressionAnimationBuilder@Composition@UI@Windows@@QEAAJPEAUHSTRING__@@W4DCOMPOSITION_EXPRESSION_TYPE@@@Z; Windows::UI::Composition::ExpressionAnimationBuilder::PushConstantParameter(HSTRING__ *,DCOMPOSITION_EXPRESSION_TYPE)
0x1800062e7  mov     ebx, eax
0x1800062e9  test    eax, eax
0x1800062eb  jns     loc_1800061A8
0x1800062f1  mov     rax, [rdi+60h]
0x1800062f5  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@ExpressionAnimationParser@Composition@UI@Windows@@0QBJB; int *
0x1800062fc  mov     r15d, [rbp+4Fh+var_A0]
0x180006300  mov     r8d, 2; unsigned int
0x180006306  mov     [rsp+0D0h+var_A8], 0; void *
0x18000630f  mov     r9d, ebx; int
0x180006312  mov     dword ptr [rsp+0D0h+var_B0], 357h; unsigned int
0x18000631a  mov     [rax+3C4h], r14d
0x180006321  mov     rax, [rdi+60h]
0x180006325  lea     ecx, [r8+2]; unsigned int
0x180006329  mov     [rax+3C8h], r15d
0x180006330  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180006335  jmp     loc_1800061AC
0x18000633a  mov     rcx, [rbp+4Fh+var_60]; void *
0x18000633e  test    rcx, rcx
0x180006341  jz      loc_1800060EB
0x180006347  mov     edx, 40h ; '@'; unsigned __int64
0x18000634c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006351  mov     [rbp+4Fh+var_60], r15
0x180006355  jmp     loc_1800060EB
0x18000635a  mov     r12b, 1
0x18000635d  jmp     loc_1800061A8
0x180006362  mov     rcx, [rbp+4Fh+var_60]
0x180006366  test    rcx, rcx
0x180006369  jz      loc_1800060EB
0x18000636f  mov     edx, 18h
0x180006374  jmp     short loc_18000634C
0x180006376  mov     rdx, [rbp+57h]
0x18000637a  mov     ecx, 8007000Eh
0x18000637f  call    ModuleFailFastForHRESULT
```
