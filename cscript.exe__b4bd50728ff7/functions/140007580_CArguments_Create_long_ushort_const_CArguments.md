# CArguments::Create(long,ushort const * *,CArguments * *)

- ea: `0x140007580`
- end: `0x140007742`
- name: `?Create@CArguments@@SAJJPEAPEBGPEAPEAV1@@Z`
- size: `450`
- prototype: `__int64 __fastcall(int, const unsigned __int16 **, struct CArguments **)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140001bd0`

## callees

- `0x140007580`
- `0x140009c70`
- `0x140013904`
- `0x140013bf8`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400076bb`
- `OLEAUT32!__imp_SysAllocString` at `0x1400076bb`
- `OLEAUT32!__imp_VariantClear` at `0x1400076e2`
- `OLEAUT32!__imp_VariantClear` at `0x1400076e2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140007678`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140007678`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1400076d6`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1400076d6`

## pseudocode

```c
__int64 __fastcall CArguments::Create(signed int a1, const unsigned __int16 **a2, struct CArguments **a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  SAFEARRAY *v8; // rax
  int v9; // ebx
  LONG i; // eax
  SAFEARRAYBOUND rgsabound; // [rsp+20h] [rbp-28h] BYREF
  VARIANTARG pv; // [rsp+28h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+A8h] [rbp+60h] BYREF

  rgsabound = 0;
  rgIndices = 0;
  memset(&pv, 0, sizeof(pv));
  v6 = operator new(0x98u);
  v7 = v6;
  if ( !v6 )
    return (unsigned int)-2147024882;
  v6[1] = &IWshRuntime::`vftable';
  v6[3] = &CUnknown::`vftable';
  v6[6] = &CUnknown::InnerUnknown::`vftable';
  *((_DWORD *)v6 + 14) = 1;
  v6[4] = v6 + 6;
  v6[5] = v6;
  _InterlockedAdd(&Global::g_cObjects, 1u);
  *((_BYTE *)v6 + 72) = 0;
  v6[8] = &TaUser_DescCArguments;
  v6[10] = 0;
  *v6 = &CArguments::`vftable'{for `IArguments2'};
  v6[11] = 0;
  v6[1] = &CArguments::`vftable'{for `IWshRuntime'};
  v6[2] = &CArguments::`vftable'{for `IProvideClassInfo'};
  v6[3] = &CArguments::`vftable'{for `CDispatch'};
  v6[12] = 0;
  v6[14] = 0;
  v6[13] = 0;
  v6[16] = 0;
  v6[17] = 0;
  v6[15] = 0;
  *((_DWORD *)v6 + 36) = 1;
  rgsabound.lLbound = 0;
  rgsabound.cElements = a1;
  v8 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  v7[10] = v8;
  if ( v8 )
  {
    rgIndices = 0;
    for ( i = 0; i < a1; i = ++rgIndices )
    {
      pv.vt = 8;
      pv.llVal = (LONGLONG)SysAllocString(a2[i]);
      if ( !pv.llVal )
        goto LABEL_3;
      v9 = SafeArrayPutElement((SAFEARRAY *)v7[10], &rgIndices, &pv);
      VariantClear(&pv);
      if ( v9 < 0 )
        goto LABEL_4;
    }
    v9 = CNamedArguments::Create(a1, a2, (SAFEARRAY ***)v7 + 11);
    if ( v9 >= 0 )
    {
      v9 = CUnnamedArguments::Create(a1, a2, (struct CUnnamedArguments **)v7 + 12);
      if ( v9 >= 0 )
      {
        *a3 = (struct CArguments *)v7;
        return 0;
      }
    }
  }
  else
  {
LABEL_3:
    v9 = -2147024882;
  }
LABEL_4:
  (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140007580  push    rbp
0x140007582  push    rbx
0x140007583  push    rsi
0x140007584  push    rdi
0x140007585  push    r12
0x140007587  push    r13
0x140007589  push    r14
0x14000758b  push    r15
0x14000758d  mov     rbp, rsp
0x140007590  sub     rsp, 48h
0x140007594  mov     esi, ecx
0x140007596  xor     r13d, r13d
0x140007599  xorps   xmm0, xmm0
0x14000759c  mov     qword ptr [rbp+rgsabound.cElements], r13
0x1400075a0  xor     eax, eax
0x1400075a2  mov     [rbp+rgIndices], r13d
0x1400075a6  mov     ecx, 98h; Size
0x1400075ab  mov     [rbp+var_10], rax
0x1400075af  movups  [rbp+pv], xmm0
0x1400075b3  mov     r15, r8
0x1400075b6  mov     r14, rdx
0x1400075b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400075be  mov     rdi, rax
0x1400075c1  test    rax, rax
0x1400075c4  jz      loc_14000772A
0x1400075ca  lea     rax, ??_7IWshRuntime@@6B@; const IWshRuntime::`vftable'
0x1400075d1  mov     [rdi+8], rax
0x1400075d5  lea     rcx, ??_7InnerUnknown@CUnknown@@6B@; const CUnknown::InnerUnknown::`vftable'
0x1400075dc  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x1400075e3  mov     [rdi+18h], rax
0x1400075e7  lea     edx, [r13+1]; cDims
0x1400075eb  lea     rax, [rdi+30h]
0x1400075ef  mov     [rax], rcx
0x1400075f2  mov     [rax+8], edx
0x1400075f5  mov     [rdi+20h], rax
0x1400075f9  mov     [rdi+28h], rdi
0x1400075fd  lock add cs:?g_cObjects@Global@@2JA, edx; long Global::g_cObjects
0x140007604  mov     [rdi+48h], r13b
0x140007608  lea     rax, ?TaUser_DescCArguments@@3UTaDescDispatch@@A; TaDescDispatch TaUser_DescCArguments
0x14000760f  mov     [rdi+40h], rax
0x140007613  lea     ecx, [rdx+0Bh]; vt
0x140007616  mov     [rdi+50h], r13
0x14000761a  lea     rax, ??_7CArguments@@6BIArguments2@@@; const CArguments::`vftable'{for `IArguments2'}
0x140007621  mov     [rdi], rax
0x140007624  lea     r8, [rbp+rgsabound]; rgsabound
0x140007628  mov     [rdi+58h], r13
0x14000762c  lea     rax, ??_7CArguments@@6BIWshRuntime@@@; const CArguments::`vftable'{for `IWshRuntime'}
0x140007633  mov     [rdi+8], rax
0x140007637  lea     rax, ??_7CArguments@@6BIProvideClassInfo@@@; const CArguments::`vftable'{for `IProvideClassInfo'}
0x14000763e  mov     [rdi+10h], rax
0x140007642  lea     rax, ??_7CArguments@@6BCDispatch@@@; const CArguments::`vftable'{for `CDispatch'}
0x140007649  mov     [rdi+18h], rax
0x14000764d  mov     [rdi+60h], r13
0x140007651  mov     [rdi+70h], r13
0x140007655  mov     [rdi+68h], r13
0x140007659  mov     [rdi+80h], r13
0x140007660  mov     [rdi+88h], r13
0x140007667  mov     [rdi+78h], r13
0x14000766b  mov     [rdi+90h], edx
0x140007671  mov     [rbp+rgsabound.lLbound], r13d
0x140007675  mov     [rbp+rgsabound.cElements], esi
0x140007678  call    cs:__imp_SafeArrayCreate
0x14000767e  mov     [rdi+50h], rax
0x140007682  test    rax, rax
0x140007685  jnz     short loc_1400076A0
0x140007687  mov     ebx, 8007000Eh
0x14000768c  mov     rax, [rdi]
0x14000768f  mov     rcx, rdi
0x140007692  mov     rax, [rax+10h]
0x140007696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000769b  jmp     loc_14000772F
0x1400076a0  mov     [rbp+rgIndices], r13d
0x1400076a4  mov     eax, r13d
0x1400076a7  cmp     eax, esi
0x1400076a9  jge     short loc_1400076F6
0x1400076ab  mov     ecx, 8
0x1400076b0  mov     word ptr [rbp+pv], cx
0x1400076b4  movsxd  rcx, eax
0x1400076b7  mov     rcx, [r14+rcx*8]; psz
0x1400076bb  call    cs:__imp_SysAllocString
0x1400076c1  mov     qword ptr [rbp+pv+8], rax
0x1400076c5  test    rax, rax
0x1400076c8  jz      short loc_140007687
0x1400076ca  mov     rcx, [rdi+50h]; psa
0x1400076ce  lea     r8, [rbp+pv]; pv
0x1400076d2  lea     rdx, [rbp+rgIndices]; rgIndices
0x1400076d6  call    cs:__imp_SafeArrayPutElement
0x1400076dc  lea     rcx, [rbp+pv]; pvarg
0x1400076e0  mov     ebx, eax
0x1400076e2  call    cs:__imp_VariantClear
0x1400076e8  test    ebx, ebx
0x1400076ea  js      short loc_14000768C
0x1400076ec  mov     eax, [rbp+rgIndices]
0x1400076ef  inc     eax
0x1400076f1  mov     [rbp+rgIndices], eax
0x1400076f4  jmp     short loc_1400076A7
0x1400076f6  lea     r8, [rdi+58h]; struct CNamedArguments **
0x1400076fa  mov     rdx, r14; unsigned __int16 **
0x1400076fd  mov     ecx, esi; int
0x1400076ff  call    ?Create@CNamedArguments@@SAJJPEAPEBGPEAPEAV1@@Z; CNamedArguments::Create(long,ushort const * *,CNamedArguments * *)
0x140007704  mov     ebx, eax
0x140007706  test    eax, eax
0x140007708  js      short loc_14000768C
0x14000770a  lea     r8, [rdi+60h]; struct CUnnamedArguments **
0x14000770e  mov     rdx, r14; unsigned __int16 **
0x140007711  mov     ecx, esi; int
0x140007713  call    ?Create@CUnnamedArguments@@SAJJPEAPEBGPEAPEAV1@@Z; CUnnamedArguments::Create(long,ushort const * *,CUnnamedArguments * *)
0x140007718  mov     ebx, eax
0x14000771a  test    eax, eax
0x14000771c  js      loc_14000768C
0x140007722  mov     [r15], rdi
0x140007725  mov     ebx, r13d
0x140007728  jmp     short loc_14000772F
0x14000772a  mov     ebx, 8007000Eh
0x14000772f  mov     eax, ebx
0x140007731  add     rsp, 48h
0x140007735  pop     r15
0x140007737  pop     r14
0x140007739  pop     r13
0x14000773b  pop     r12
0x14000773d  pop     rdi
0x14000773e  pop     rsi
0x14000773f  pop     rbx
0x140007740  pop     rbp
0x140007741  retn
```
