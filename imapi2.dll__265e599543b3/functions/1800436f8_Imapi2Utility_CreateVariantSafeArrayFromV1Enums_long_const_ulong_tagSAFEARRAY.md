# Imapi2Utility::CreateVariantSafeArrayFromV1Enums(long const *,ulong,tagSAFEARRAY * *)

- ea: `0x1800436f8`
- end: `0x1800437d2`
- name: `?CreateVariantSafeArrayFromV1Enums@Imapi2Utility@@YA?BJPEBJKPEAPEAUtagSAFEARRAY@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(LONG *this, const int *, SAFEARRAY **, struct tagSAFEARRAY **)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x18002be40`
- `0x18002bfb0`
- `0x18002c580`
- `0x18002c6f0`
- `0x18002c860`
- `0x180031ad0`
- `0x180041450`
- `0x1800445b0`
- `0x18004499c`

## callees

- `0x180014134`
- `0x18001cb0c`
- `0x1800436f8`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180043797`
- `OLEAUT32!__imp_VariantInit` at `0x180043797`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180043722`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180043722`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::CreateVariantSafeArrayFromV1Enums(
        LONG *this,
        const int *a2,
        SAFEARRAY **a3,
        struct tagSAFEARRAY **a4)
{
  unsigned int v5; // edi
  SAFEARRAY *Vector; // rax
  struct tagSAFEARRAY **v8; // rdx
  SAFEARRAY *v9; // rbp
  unsigned int v10; // esi
  VARIANTARG *pvData; // r14
  unsigned int i; // r15d
  LONG v13; // ecx
  SAFEARRAY *v15; // [rsp+80h] [rbp+8h] BYREF

  *a3 = 0;
  v5 = (unsigned int)a2;
  Vector = SafeArrayCreateVector(0xCu, 0, (ULONG)a2);
  v15 = Vector;
  v9 = Vector;
  if ( Vector )
  {
    pvData = (VARIANTARG *)Vector->pvData;
    v10 = 0;
    for ( i = 0; i < v5; ++pvData )
    {
      VariantInit(pvData);
      pvData->vt = 3;
      ++i;
      v13 = *this++;
      pvData->lVal = v13;
    }
    *a3 = v9;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, v5, v5);
    }
    v10 = -2147024882;
    Imapi2Utility::SafeArrayDestroyAndNull((Imapi2Utility *)&v15, v8);
  }
  return v10;
}

```

## disassembly

```asm
0x1800436f8  push    rbx
0x1800436fa  push    rbp
0x1800436fb  push    rsi
0x1800436fc  push    rdi
0x1800436fd  push    r12
0x1800436ff  push    r13
0x180043701  push    r14
0x180043703  push    r15
0x180043705  sub     rsp, 38h
0x180043709  mov     r12, r8
0x18004370c  mov     qword ptr [r8], 0
0x180043713  mov     r8d, edx; cElements
0x180043716  mov     edi, edx
0x180043718  mov     r13, rcx
0x18004371b  xor     edx, edx; lLbound
0x18004371d  mov     ecx, 0Ch; vt
0x180043722  call    cs:__imp_SafeArrayCreateVector
0x180043728  mov     [rsp+78h+arg_0], rax
0x180043730  mov     rbp, rax
0x180043733  test    rax, rax
0x180043736  jnz     short loc_180043787
0x180043738  mov     rcx, cs:WPP_GLOBAL_Control
0x18004373f  lea     rax, WPP_GLOBAL_Control
0x180043746  cmp     rcx, rax
0x180043749  jz      short loc_180043773
0x18004374b  test    byte ptr [rcx+1Ch], 4
0x18004374f  jz      short loc_180043773
0x180043751  lea     ebx, [rbp+3]
0x180043754  cmp     [rcx+19h], bl
0x180043757  jb      short loc_180043773
0x180043759  mov     rcx, [rcx+10h]
0x18004375d  lea     edx, [rbp+52h]
0x180043760  mov     r9d, edi
0x180043763  mov     [rsp+78h+var_58], edi
0x180043767  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18004376e  call    WPP_SF_Dd
0x180043773  lea     rcx, [rsp+78h+arg_0]; this
0x18004377b  mov     esi, 8007000Eh
0x180043780  call    ?SafeArrayDestroyAndNull@Imapi2Utility@@YAXAEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::SafeArrayDestroyAndNull(tagSAFEARRAY * &)
0x180043785  jmp     short loc_1800437BF
0x180043787  mov     r14, [rax+10h]
0x18004378b  xor     esi, esi
0x18004378d  xor     r15d, r15d
0x180043790  test    edi, edi
0x180043792  jz      short loc_1800437BB
0x180043794  mov     rcx, r14; pvarg
0x180043797  call    cs:__imp_VariantInit
0x18004379d  mov     word ptr [r14], 3
0x1800437a3  inc     r15d
0x1800437a6  mov     ecx, [r13+0]
0x1800437aa  lea     r13, [r13+4]
0x1800437ae  mov     [r14+8], ecx
0x1800437b2  add     r14, 18h
0x1800437b6  cmp     r15d, edi
0x1800437b9  jb      short loc_180043794
0x1800437bb  mov     [r12], rbp
0x1800437bf  mov     eax, esi
0x1800437c1  add     rsp, 38h
0x1800437c5  pop     r15
0x1800437c7  pop     r14
0x1800437c9  pop     r13
0x1800437cb  pop     r12
0x1800437cd  pop     rdi
0x1800437ce  pop     rsi
0x1800437cf  pop     rbp
0x1800437d0  pop     rbx
0x1800437d1  retn
```
