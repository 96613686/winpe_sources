# ProcessDmpComplexElement::ProcessElement(IXMLDOMNode *,RGBCaptureMeasurementData *)

- ea: `0x18005b7ac`
- end: `0x18005bb5f`
- name: `?ProcessElement@ProcessDmpComplexElement@@SAJPEAUIXMLDOMNode@@PEAURGBCaptureMeasurementData@@@Z`
- size: `947`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct RGBCaptureMeasurementData *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005a3c4`

## callees

- `0x18001b074`
- `0x18001ecb8`
- `0x18002b98c`
- `0x18002e5f0`
- `0x18002eab4`
- `0x180059e24`
- `0x18005b390`
- `0x18005b7ac`
- `0x180084010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18005ba9d`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18005ba9d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18005ba82`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18005ba82`
- `OLEAUT32!__imp_SysFreeString` at `0x18005bb21`
- `OLEAUT32!__imp_SysFreeString` at `0x18005bb21`
- `OLEAUT32!__imp_VariantInit` at `0x18005b8d5`
- `OLEAUT32!__imp_VariantInit` at `0x18005b8d5`
- `OLEAUT32!__imp_VariantClear` at `0x18005b93e`
- `OLEAUT32!__imp_VariantClear` at `0x18005b93e`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18005b913`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18005b913`

## pseudocode

```c
__int64 __fastcall ProcessDmpComplexElement::ProcessElement(
        struct IXMLDOMNode *a1,
        struct RGBCaptureMeasurementData *a2)
{
  int RequiredDOMNode; // ebx
  wchar_t *v5; // rdi
  LONG *v6; // r13
  __int64 v7; // r14
  wchar_t *v8; // rdi
  __int64 v9; // rax
  const unsigned __int16 *v10; // rdx
  int DOMNode; // eax
  bool v12; // sf
  wchar_t *v13; // rsi
  struct IXMLDOMNode *v14; // r12
  wchar_t *v15; // rsi
  int v16; // eax
  const unsigned __int16 *v17; // rdx
  unsigned int SubstringCount; // eax
  unsigned int v19; // edi
  void *v20; // rax
  void *v21; // rax
  __int64 *v22; // r12
  wchar_t *v23; // rcx
  unsigned int v24; // r14d
  wchar_t *v25; // rax
  int v26; // eax
  __int64 v27; // r9
  __int64 v28; // r8
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // r9
  __int64 v33; // r8
  wchar_t *String; // [rsp+30h] [rbp-39h] BYREF
  wchar_t *Context; // [rsp+38h] [rbp-31h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-29h] BYREF
  _OWORD v38[2]; // [rsp+58h] [rbp-11h]
  wchar_t Delimiter[4]; // [rsp+78h] [rbp+Fh] BYREF

  *(_QWORD *)Delimiter = a1;
  String = 0;
  Context = 0;
  RequiredDOMNode = FindRequiredDOMNode(a1, L"./cdm:ColorSamples[1]", (struct IXMLDOMNode **)&String);
  if ( RequiredDOMNode < 0 )
    return (unsigned int)RequiredDOMNode;
  v5 = String;
  v6 = (LONG *)((char *)a2 + 56);
  RequiredDOMNode = ProcessDmpComplexElement::ProcessSampleArray(
                      (struct IXMLDOMNode *)String,
                      (struct RGBCaptureMeasurementData *)((char *)a2 + 56));
  if ( v5 )
    (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v5 + 16LL))(v5);
  if ( RequiredDOMNode < 0 )
    return (unsigned int)RequiredDOMNode;
  RequiredDOMNode = FindRequiredDOMNode(a1, L"./cdm:PrimaryIndex[1]", (struct IXMLDOMNode **)&Context);
  if ( RequiredDOMNode < 0 )
    return (unsigned int)RequiredDOMNode;
  v7 = 0;
  v8 = Context;
  v38[0] = _mm_load_si128((const __m128i *)&_xmm);
  v38[1] = _mm_load_si128((const __m128i *)&_xmm);
  do
  {
    v9 = *((int *)v38 + v7);
    String = 0;
    v10 = (&gc_apwszCdmpXpathQuery)[v9];
    if ( (_DWORD)v9 == 39 )
      DOMNode = FindRequiredDOMNode((struct IXMLDOMNode *)v8, v10, (struct IXMLDOMNode **)&String);
    else
      DOMNode = FindDOMNode((struct IXMLDOMNode *)v8, v10, (struct IXMLDOMNode **)&String);
    RequiredDOMNode = DOMNode;
    v12 = DOMNode < 0;
    if ( !DOMNode )
    {
      v13 = String;
      if ( !String )
        goto LABEL_21;
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      RequiredDOMNode = (*(__int64 (__fastcall **)(wchar_t *, VARIANTARG *))(*(_QWORD *)v13 + 240LL))(v13, &pvarg);
      if ( RequiredDOMNode >= 0 )
      {
        if ( pvarg.vt == 19
          || (RequiredDOMNode = VariantChangeTypeEx(&pvarg, &pvarg, 0x7Fu, 0, 0x13u), RequiredDOMNode >= 0) )
        {
          if ( pvarg.lVal && pvarg.lVal <= (unsigned int)*v6 )
            *((_DWORD *)a2 + v7) = pvarg.lVal - 1;
          else
            RequiredDOMNode = -2147022885;
        }
      }
      VariantClear(&pvarg);
      (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v13 + 16LL))(v13);
      v12 = RequiredDOMNode < 0;
    }
    if ( v12 )
      break;
LABEL_21:
    v7 = (unsigned int)(v7 + 1);
  }
  while ( (unsigned int)v7 < 8 );
  v14 = *(struct IXMLDOMNode **)Delimiter;
  if ( v8 )
    (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( RequiredDOMNode >= 0 )
  {
    Context = 0;
    RequiredDOMNode = FindRequiredDOMNode(v14, L"./cdm:NeutralIndices[1]", (struct IXMLDOMNode **)&Context);
    if ( RequiredDOMNode >= 0 )
    {
      v15 = Context;
      String = 0;
      v16 = (*(__int64 (__fastcall **)(wchar_t *, wchar_t **))(*(_QWORD *)Context + 208LL))(Context, &String);
      RequiredDOMNode = v16;
      if ( v16 == 1 )
        goto LABEL_29;
      if ( v16 >= 0 )
      {
        SubstringCount = ProcessSimpleTypeElement::GetSubstringCount((ProcessSimpleTypeElement *)String, v17);
        v19 = SubstringCount;
        if ( SubstringCount )
        {
          v20 = operator new[](saturated_mul(SubstringCount, 0xCu));
          NCoreLibrary::TAutoPtrArray<enum CHuePlane::ECacheStatus>::operator=((_QWORD *)a2 + 5, (__int64)v20);
          v21 = operator new[](saturated_mul(3 * v19, 4u));
          v22 = (__int64 *)((char *)a2 + 48);
          NCoreLibrary::TAutoPtrArray<enum CHuePlane::ECacheStatus>::operator=((_QWORD *)a2 + 6, (__int64)v21);
          if ( *((_QWORD *)a2 + 5) && *v22 )
          {
            v23 = String;
            v24 = 0;
            Context = 0;
            wcscpy(Delimiter, L" \t\n");
            *((_DWORD *)a2 + 8) = v19;
            while ( 1 )
            {
              v25 = wcstok_s(v23, Delimiter, &Context);
              if ( !v25 || v24 >= v19 )
                break;
              v26 = _o__wtoi(v25);
              if ( v26 < 1 || v26 > *v6 )
                goto LABEL_29;
              v27 = *((_QWORD *)a2 + 8);
              v28 = *((_QWORD *)a2 + 5);
              v29 = 3LL * v24;
              *(_QWORD *)(v28 + 4 * v29) = *(_QWORD *)(v27 + 12LL * v26 - 12);
              v30 = (unsigned int)(3 * (v26 - 1));
              *(_DWORD *)(v28 + 4 * v29 + 8) = *(_DWORD *)(v27 + 12LL * v26 - 4);
              v31 = 3 * v24;
              v32 = *((_QWORD *)a2 + 9);
              ++v24;
              v33 = *v22;
              *(_QWORD *)(v33 + 4 * v31) = *(_QWORD *)(v32 + 4 * v30);
              *(_DWORD *)(v33 + 4LL * (unsigned int)v31 + 8) = *(_DWORD *)(v32 + 4 * v30 + 8);
              v23 = 0;
            }
          }
          else
          {
            RequiredDOMNode = -2147024882;
          }
        }
        else
        {
LABEL_29:
          RequiredDOMNode = -2147022885;
        }
      }
      SysFreeString(String);
      (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  return (unsigned int)RequiredDOMNode;
}

```

## disassembly

```asm
0x18005b7ac  mov     [rsp-8+arg_10], rbx
0x18005b7b1  push    rbp
0x18005b7b2  push    rsi
0x18005b7b3  push    rdi
0x18005b7b4  push    r12
0x18005b7b6  push    r13
0x18005b7b8  push    r14
0x18005b7ba  push    r15
0x18005b7bc  lea     rbp, [rsp-27h]
0x18005b7c1  sub     rsp, 90h
0x18005b7c8  mov     rax, cs:__security_cookie
0x18005b7cf  xor     rax, rsp
0x18005b7d2  mov     [rbp+57h+var_40], rax
0x18005b7d6  mov     r15, rdx
0x18005b7d9  mov     qword ptr [rbp+57h+Delimiter], rcx
0x18005b7dd  mov     rdx, cs:off_1800867B0; unsigned __int16 *
0x18005b7e4  lea     r8, [rbp+57h+String]; struct IXMLDOMNode **
0x18005b7e8  mov     r12, rcx
0x18005b7eb  mov     [rbp+57h+String], 0
0x18005b7f3  mov     [rbp+57h+Context], 0
0x18005b7fb  call    ?FindRequiredDOMNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; FindRequiredDOMNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18005b800  mov     ebx, eax
0x18005b802  test    eax, eax
0x18005b804  js      loc_18005BB36
0x18005b80a  mov     rdi, [rbp+57h+String]
0x18005b80e  lea     r13, [r15+38h]
0x18005b812  mov     rdx, r13; struct RGBSamples *
0x18005b815  mov     rcx, rdi; struct IXMLDOMNode *
0x18005b818  call    ?ProcessSampleArray@ProcessDmpComplexElement@@SAJPEAUIXMLDOMNode@@PEAURGBSamples@@@Z; ProcessDmpComplexElement::ProcessSampleArray(IXMLDOMNode *,RGBSamples *)
0x18005b81d  mov     ebx, eax
0x18005b81f  test    rdi, rdi
0x18005b822  jz      short loc_18005B833
0x18005b824  mov     rax, [rdi]
0x18005b827  mov     rcx, rdi
0x18005b82a  mov     rax, [rax+10h]
0x18005b82e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b833  test    ebx, ebx
0x18005b835  js      loc_18005BB36
0x18005b83b  mov     rdx, cs:off_1800867A0; unsigned __int16 *
0x18005b842  lea     r8, [rbp+57h+Context]; struct IXMLDOMNode **
0x18005b846  mov     rcx, r12; struct IXMLDOMNode *
0x18005b849  call    ?FindRequiredDOMNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; FindRequiredDOMNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18005b84e  mov     ebx, eax
0x18005b850  test    eax, eax
0x18005b852  js      loc_18005BB36
0x18005b858  movdqa  xmm0, cs:__xmm@00000021000000250000002300000024
0x18005b860  lea     rcx, ?gc_apwszCdmpXpathQuery@@3PAPEBGA; ushort const * near * gc_apwszCdmpXpathQuery
0x18005b867  movdqa  xmm1, cs:__xmm@00000027000000280000002200000026
0x18005b86f  xor     r14d, r14d
0x18005b872  mov     rdi, [rbp+57h+Context]
0x18005b876  movdqu  [rbp+57h+var_68], xmm0
0x18005b87b  lea     r12d, [r14+13h]
0x18005b87f  movdqu  [rbp+57h+var_58], xmm1
0x18005b884  movsxd  rax, dword ptr [rbp+r14*4+57h+var_68]
0x18005b889  lea     r8, [rbp+57h+String]; struct IXMLDOMNode **
0x18005b88d  mov     [rbp+57h+String], 0
0x18005b895  mov     rdx, [rcx+rax*8]; unsigned __int16 *
0x18005b899  mov     rcx, rdi; struct IXMLDOMNode *
0x18005b89c  cmp     eax, 27h ; '''
0x18005b89f  jnz     short loc_18005B8A8
0x18005b8a1  call    ?FindRequiredDOMNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; FindRequiredDOMNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18005b8a6  jmp     short loc_18005B8AD
0x18005b8a8  call    ?FindDOMNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; FindDOMNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18005b8ad  mov     ebx, eax
0x18005b8af  test    eax, eax
0x18005b8b1  jnz     loc_18005B955
0x18005b8b7  mov     rsi, [rbp+57h+String]
0x18005b8bb  test    rsi, rsi
0x18005b8be  jz      loc_18005B957
0x18005b8c4  xorps   xmm0, xmm0
0x18005b8c7  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005b8cb  xor     eax, eax
0x18005b8cd  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18005b8d1  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18005b8d5  call    cs:__imp_VariantInit
0x18005b8db  mov     rax, [rsi]
0x18005b8de  lea     rdx, [rbp+57h+pvarg]
0x18005b8e2  mov     rcx, rsi
0x18005b8e5  mov     rax, [rax+0F0h]
0x18005b8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b8f1  mov     ebx, eax
0x18005b8f3  test    eax, eax
0x18005b8f5  js      short loc_18005B93A
0x18005b8f7  cmp     word ptr [rbp+57h+pvarg], r12w
0x18005b8fc  jz      short loc_18005B91F
0x18005b8fe  xor     r9d, r9d; wFlags
0x18005b901  mov     [rsp+0C0h+vt], r12w; vt
0x18005b907  lea     rdx, [rbp+57h+pvarg]; pvarSrc
0x18005b90b  lea     rcx, [rbp+57h+pvarg]; pvargDest
0x18005b90f  lea     r8d, [r9+7Fh]; lcid
0x18005b913  call    cs:__imp_VariantChangeTypeEx
0x18005b919  mov     ebx, eax
0x18005b91b  test    eax, eax
0x18005b91d  js      short loc_18005B93A
0x18005b91f  mov     eax, dword ptr [rbp+57h+pvarg+8]
0x18005b922  cmp     eax, 1
0x18005b925  jb      short loc_18005B935
0x18005b927  cmp     eax, [r13+0]
0x18005b92b  ja      short loc_18005B935
0x18005b92d  dec     eax
0x18005b92f  mov     [r15+r14*4], eax
0x18005b933  jmp     short loc_18005B93A
0x18005b935  mov     ebx, 800707DBh
0x18005b93a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005b93e  call    cs:__imp_VariantClear
0x18005b944  mov     rax, [rsi]
0x18005b947  mov     rcx, rsi
0x18005b94a  mov     rax, [rax+10h]
0x18005b94e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b953  test    ebx, ebx
0x18005b955  js      short loc_18005B96B
0x18005b957  inc     r14d
0x18005b95a  lea     rcx, ?gc_apwszCdmpXpathQuery@@3PAPEBGA; ushort const * near * gc_apwszCdmpXpathQuery
0x18005b961  cmp     r14d, 8
0x18005b965  jb      loc_18005B884
0x18005b96b  mov     r12, qword ptr [rbp+57h+Delimiter]
0x18005b96f  test    rdi, rdi
0x18005b972  jz      short loc_18005B983
0x18005b974  mov     rax, [rdi]
0x18005b977  mov     rcx, rdi
0x18005b97a  mov     rax, [rax+10h]
0x18005b97e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b983  test    ebx, ebx
0x18005b985  js      loc_18005BB36
0x18005b98b  mov     rdx, cs:off_180086818; unsigned __int16 *
0x18005b992  lea     r8, [rbp+57h+Context]; struct IXMLDOMNode **
0x18005b996  mov     rcx, r12; struct IXMLDOMNode *
0x18005b999  mov     [rbp+57h+Context], 0
0x18005b9a1  call    ?FindRequiredDOMNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; FindRequiredDOMNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18005b9a6  mov     ebx, eax
0x18005b9a8  test    eax, eax
0x18005b9aa  js      loc_18005BB36
0x18005b9b0  mov     rsi, [rbp+57h+Context]
0x18005b9b4  lea     rdx, [rbp+57h+String]
0x18005b9b8  mov     [rbp+57h+String], 0
0x18005b9c0  mov     rcx, rsi
0x18005b9c3  mov     rax, [rsi]
0x18005b9c6  mov     rax, [rax+0D0h]
0x18005b9cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b9d2  mov     ebx, eax
0x18005b9d4  cmp     eax, 1
0x18005b9d7  jz      short loc_18005B9F0
0x18005b9d9  test    eax, eax
0x18005b9db  js      loc_18005BB1D
0x18005b9e1  mov     rcx, [rbp+57h+String]; this
0x18005b9e5  call    ?GetSubstringCount@ProcessSimpleTypeElement@@YAIPEBG@Z; ProcessSimpleTypeElement::GetSubstringCount(ushort const *)
0x18005b9ea  mov     edi, eax
0x18005b9ec  test    eax, eax
0x18005b9ee  jnz     short loc_18005B9FA
0x18005b9f0  mov     ebx, 800707DBh
0x18005b9f5  jmp     loc_18005BB1D
0x18005b9fa  mov     eax, 0Ch
0x18005b9ff  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18005ba06  mul     rdi
0x18005ba09  cmovb   rax, r12
0x18005ba0d  mov     rcx, rax; unsigned __int64
0x18005ba10  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005ba15  mov     rdx, rax
0x18005ba18  lea     rcx, [r15+28h]
0x18005ba1c  call    ??4?$TAutoPtrArray@W4ECacheStatus@CHuePlane@@@NCoreLibrary@@QEAAPEAW4ECacheStatus@CHuePlane@@PEAW423@@Z; NCoreLibrary::TAutoPtrArray<CHuePlane::ECacheStatus>::operator=(CHuePlane::ECacheStatus *)
0x18005ba21  lea     ecx, [rdi+rdi*2]
0x18005ba24  lea     eax, [r12+5]
0x18005ba29  mul     rcx
0x18005ba2c  cmovb   rax, r12
0x18005ba30  mov     rcx, rax; unsigned __int64
0x18005ba33  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005ba38  lea     r12, [r15+30h]
0x18005ba3c  mov     rdx, rax
0x18005ba3f  mov     rcx, r12
0x18005ba42  call    ??4?$TAutoPtrArray@W4ECacheStatus@CHuePlane@@@NCoreLibrary@@QEAAPEAW4ECacheStatus@CHuePlane@@PEAW423@@Z; NCoreLibrary::TAutoPtrArray<CHuePlane::ECacheStatus>::operator=(CHuePlane::ECacheStatus *)
0x18005ba47  xor     eax, eax
0x18005ba49  cmp     [r15+28h], rax
0x18005ba4d  jz      loc_18005BB18
0x18005ba53  cmp     [r12], rax
0x18005ba57  jz      loc_18005BB18
0x18005ba5d  mov     rcx, [rbp+57h+String]; String
0x18005ba61  mov     r14d, eax
0x18005ba64  mov     [rbp+57h+Context], rax
0x18005ba68  mov     rax, 0A00090020h
0x18005ba72  mov     qword ptr [rbp+57h+Delimiter], rax
0x18005ba76  mov     [r15+20h], edi
0x18005ba7a  lea     r8, [rbp+57h+Context]; Context
0x18005ba7e  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x18005ba82  call    cs:__imp_wcstok_s
0x18005ba88  test    rax, rax
0x18005ba8b  jz      loc_18005BB1D
0x18005ba91  cmp     r14d, edi
0x18005ba94  jnb     loc_18005BB1D
0x18005ba9a  mov     rcx, rax
0x18005ba9d  call    cs:__imp__o__wtoi
0x18005baa3  cmp     eax, 1
0x18005baa6  jl      loc_18005B9F0
0x18005baac  cmp     eax, [r13+0]
0x18005bab0  jg      loc_18005B9F0
0x18005bab6  mov     r9, [r15+40h]
0x18005baba  lea     r10d, [rax-1]
0x18005babe  mov     r8, [r15+28h]
0x18005bac2  cdqe
0x18005bac4  lea     rdx, [rax+rax*2]
0x18005bac8  mov     eax, r14d
0x18005bacb  movsd   xmm0, qword ptr [r9+rdx*4-0Ch]
0x18005bad2  lea     rcx, [rax+rax*2]
0x18005bad6  movsd   qword ptr [r8+rcx*4], xmm0
0x18005badc  mov     eax, [r9+rdx*4-4]
0x18005bae1  lea     edx, [r10+r10*2]
0x18005bae5  mov     [r8+rcx*4+8], eax
0x18005baea  lea     eax, [r14+r14*2]
0x18005baee  mov     r9, [r15+48h]
0x18005baf2  inc     r14d
0x18005baf5  mov     r8, [r12]
0x18005baf9  mov     ecx, eax
0x18005bafb  movsd   xmm0, qword ptr [r9+rdx*4]
0x18005bb01  movsd   qword ptr [r8+rax*4], xmm0
0x18005bb07  mov     eax, [r9+rdx*4+8]
0x18005bb0c  mov     [r8+rcx*4+8], eax
0x18005bb11  xor     ecx, ecx
0x18005bb13  jmp     loc_18005BA7A
0x18005bb18  mov     ebx, 8007000Eh
0x18005bb1d  mov     rcx, [rbp+57h+String]; bstrString
0x18005bb21  call    cs:__imp_SysFreeString
0x18005bb27  mov     rax, [rsi]
0x18005bb2a  mov     rcx, rsi
0x18005bb2d  mov     rax, [rax+10h]
0x18005bb31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb36  mov     eax, ebx
0x18005bb38  mov     rcx, [rbp+57h+var_40]
0x18005bb3c  xor     rcx, rsp; StackCookie
0x18005bb3f  call    __security_check_cookie
0x18005bb44  mov     rbx, [rsp+0C0h+arg_10]
0x18005bb4c  add     rsp, 90h
0x18005bb53  pop     r15
0x18005bb55  pop     r14
0x18005bb57  pop     r13
0x18005bb59  pop     r12
0x18005bb5b  pop     rdi
0x18005bb5c  pop     rsi
0x18005bb5d  pop     rbp
0x18005bb5e  retn
```
