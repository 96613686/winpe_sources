# Imapi2Utility::CreateVariantSafeArrayFromV1Enums(long const *,ulong,tagSAFEARRAY * *)

- ea: `0x180077730`
- end: `0x18007780a`
- name: `?CreateVariantSafeArrayFromV1Enums@Imapi2Utility@@YA?BJPEBJKPEAPEAUtagSAFEARRAY@@@Z`
- size: `218`
- prototype: `int(Imapi2Utility *__hidden this, const int *, unsigned int, struct tagSAFEARRAY **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180046b98`
- `0x180049210`

## callees

- `0x180047f7c`
- `0x1800515ec`
- `0x180077730`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800777cf`
- `OLEAUT32!__imp_VariantInit` at `0x1800777cf`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18007775a`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18007775a`

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
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, v5, v5);
    }
    v10 = -2147024882;
    Imapi2Utility::SafeArrayDestroyAndNull((Imapi2Utility *)&v15, v8);
  }
  return v10;
}

```

## disassembly

```asm
0x180077730  push    rbx
0x180077732  push    rbp
0x180077733  push    rsi
0x180077734  push    rdi
0x180077735  push    r12
0x180077737  push    r13
0x180077739  push    r14
0x18007773b  push    r15
0x18007773d  sub     rsp, 38h
0x180077741  mov     r12, r8
0x180077744  mov     qword ptr [r8], 0
0x18007774b  mov     r8d, edx; cElements
0x18007774e  mov     edi, edx
0x180077750  mov     r13, rcx
0x180077753  xor     edx, edx; lLbound
0x180077755  mov     ecx, 0Ch; vt
0x18007775a  call    cs:__imp_SafeArrayCreateVector
0x180077760  mov     [rsp+78h+arg_0], rax
0x180077768  mov     rbp, rax
0x18007776b  test    rax, rax
0x18007776e  jnz     short loc_1800777BF
0x180077770  mov     rcx, cs:WPP_GLOBAL_Control
0x180077777  lea     rax, WPP_GLOBAL_Control
0x18007777e  cmp     rcx, rax
0x180077781  jz      short loc_1800777AB
0x180077783  test    byte ptr [rcx+1Ch], 4
0x180077787  jz      short loc_1800777AB
0x180077789  lea     ebx, [rbp+3]
0x18007778c  cmp     [rcx+19h], bl
0x18007778f  jb      short loc_1800777AB
0x180077791  mov     rcx, [rcx+10h]
0x180077795  lea     edx, [rbp+52h]
0x180077798  mov     r9d, edi
0x18007779b  mov     [rsp+78h+var_58], edi
0x18007779f  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x1800777a6  call    WPP_SF_DD
0x1800777ab  lea     rcx, [rsp+78h+arg_0]; this
0x1800777b3  mov     esi, 8007000Eh
0x1800777b8  call    ?SafeArrayDestroyAndNull@Imapi2Utility@@YAXAEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::SafeArrayDestroyAndNull(tagSAFEARRAY * &)
0x1800777bd  jmp     short loc_1800777F7
0x1800777bf  mov     r14, [rax+10h]
0x1800777c3  xor     esi, esi
0x1800777c5  xor     r15d, r15d
0x1800777c8  test    edi, edi
0x1800777ca  jz      short loc_1800777F3
0x1800777cc  mov     rcx, r14; pvarg
0x1800777cf  call    cs:__imp_VariantInit
0x1800777d5  mov     word ptr [r14], 3
0x1800777db  inc     r15d
0x1800777de  mov     ecx, [r13+0]
0x1800777e2  lea     r13, [r13+4]
0x1800777e6  mov     [r14+8], ecx
0x1800777ea  add     r14, 18h
0x1800777ee  cmp     r15d, edi
0x1800777f1  jb      short loc_1800777CC
0x1800777f3  mov     [r12], rbp
0x1800777f7  mov     eax, esi
0x1800777f9  add     rsp, 38h
0x1800777fd  pop     r15
0x1800777ff  pop     r14
0x180077801  pop     r13
0x180077803  pop     r12
0x180077805  pop     rdi
0x180077806  pop     rsi
0x180077807  pop     rbp
0x180077808  pop     rbx
0x180077809  retn
```
