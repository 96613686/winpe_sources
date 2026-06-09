# Imapi2Utility::CreateVariantSafeArrayFromIDispatch(IDispatch * *,ulong,tagSAFEARRAY * *)

- ea: `0x180077640`
- end: `0x18007772a`
- name: `?CreateVariantSafeArrayFromIDispatch@Imapi2Utility@@YA?BJPEAPEAUIDispatch@@KPEAPEAUtagSAFEARRAY@@@Z`
- size: `234`
- prototype: `int(Imapi2Utility *__hidden this, struct IDispatch **, unsigned int, struct tagSAFEARRAY **)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001e0a0`
- `0x180046900`
- `0x180058e30`

## callees

- `0x180047f7c`
- `0x1800515ec`
- `0x180077640`
- `0x180088010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800776db`
- `OLEAUT32!__imp_VariantInit` at `0x1800776db`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18007766f`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18007766f`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::CreateVariantSafeArrayFromIDispatch(
        LONGLONG *this,
        struct IDispatch **a2,
        SAFEARRAY **a3,
        struct tagSAFEARRAY **a4)
{
  unsigned int v5; // ebx
  SAFEARRAY *Vector; // rax
  struct tagSAFEARRAY **v8; // rdx
  SAFEARRAY *v9; // rdi
  unsigned int v10; // esi
  VARIANTARG *pvData; // r14
  unsigned int i; // ebp
  LONGLONG v13; // rcx
  SAFEARRAY *v15; // [rsp+60h] [rbp+8h] BYREF

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
      (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)*this + 8LL))(*this);
      pvData->vt = 9;
      ++i;
      v13 = *this++;
      pvData->llVal = v13;
    }
    *a3 = v9;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, v5, v5);
    }
    v10 = -2147024882;
    Imapi2Utility::SafeArrayDestroyAndNull((Imapi2Utility *)&v15, v8);
  }
  return v10;
}

```

## disassembly

```asm
0x180077640  mov     [rsp+arg_8], rbx
0x180077645  mov     [rsp+arg_10], rbp
0x18007764a  push    rsi
0x18007764b  push    rdi
0x18007764c  push    r12
0x18007764e  push    r14
0x180077650  push    r15
0x180077652  sub     rsp, 30h
0x180077656  mov     r15, r8
0x180077659  mov     qword ptr [r8], 0
0x180077660  mov     r8d, edx; cElements
0x180077663  mov     ebx, edx
0x180077665  mov     r12, rcx
0x180077668  xor     edx, edx; lLbound
0x18007766a  mov     ecx, 0Ch; vt
0x18007766f  call    cs:__imp_SafeArrayCreateVector
0x180077675  mov     [rsp+58h+arg_0], rax
0x18007767a  mov     rdi, rax
0x18007767d  test    rax, rax
0x180077680  jnz     short loc_1800776CC
0x180077682  mov     rcx, cs:WPP_GLOBAL_Control
0x180077689  lea     rax, WPP_GLOBAL_Control
0x180077690  cmp     rcx, rax
0x180077693  jz      short loc_1800776BB
0x180077695  test    byte ptr [rcx+1Ch], 4
0x180077699  jz      short loc_1800776BB
0x18007769b  cmp     byte ptr [rcx+19h], 3
0x18007769f  jb      short loc_1800776BB
0x1800776a1  mov     rcx, [rcx+10h]
0x1800776a5  lea     edx, [rdi+53h]
0x1800776a8  mov     r9d, ebx
0x1800776ab  mov     [rsp+58h+var_38], ebx
0x1800776af  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x1800776b6  call    WPP_SF_DD
0x1800776bb  lea     rcx, [rsp+58h+arg_0]; this
0x1800776c0  mov     esi, 8007000Eh
0x1800776c5  call    ?SafeArrayDestroyAndNull@Imapi2Utility@@YAXAEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::SafeArrayDestroyAndNull(tagSAFEARRAY * &)
0x1800776ca  jmp     short loc_180077711
0x1800776cc  mov     r14, [rax+10h]
0x1800776d0  xor     esi, esi
0x1800776d2  xor     ebp, ebp
0x1800776d4  test    ebx, ebx
0x1800776d6  jz      short loc_18007770E
0x1800776d8  mov     rcx, r14; pvarg
0x1800776db  call    cs:__imp_VariantInit
0x1800776e1  mov     rcx, [r12]
0x1800776e5  mov     rax, [rcx]
0x1800776e8  mov     rax, [rax+8]
0x1800776ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800776f1  mov     word ptr [r14], 9
0x1800776f7  inc     ebp
0x1800776f9  mov     rcx, [r12]
0x1800776fd  lea     r12, [r12+8]
0x180077702  mov     [r14+8], rcx
0x180077706  add     r14, 18h
0x18007770a  cmp     ebp, ebx
0x18007770c  jb      short loc_1800776D8
0x18007770e  mov     [r15], rdi
0x180077711  mov     rbx, [rsp+58h+arg_8]
0x180077716  mov     eax, esi
0x180077718  mov     rbp, [rsp+58h+arg_10]
0x18007771d  add     rsp, 30h
0x180077721  pop     r15
0x180077723  pop     r14
0x180077725  pop     r12
0x180077727  pop     rdi
0x180077728  pop     rsi
0x180077729  retn
```
