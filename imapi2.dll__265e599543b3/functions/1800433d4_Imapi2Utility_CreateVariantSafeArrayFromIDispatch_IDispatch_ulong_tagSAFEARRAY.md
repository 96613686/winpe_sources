# Imapi2Utility::CreateVariantSafeArrayFromIDispatch(IDispatch * *,ulong,tagSAFEARRAY * *)

- ea: `0x1800433d4`
- end: `0x1800434be`
- name: `?CreateVariantSafeArrayFromIDispatch@Imapi2Utility@@YA?BJPEAPEAUIDispatch@@KPEAPEAUtagSAFEARRAY@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(LONGLONG *this, struct IDispatch **, SAFEARRAY **, struct tagSAFEARRAY **)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180021bc0`
- `0x180044698`

## callees

- `0x180014134`
- `0x18001cb0c`
- `0x1800433d4`
- `0x18004a010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18004346f`
- `OLEAUT32!__imp_VariantInit` at `0x18004346f`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180043403`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180043403`

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
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, v5, v5);
    }
    v10 = -2147024882;
    Imapi2Utility::SafeArrayDestroyAndNull((Imapi2Utility *)&v15, v8);
  }
  return v10;
}

```

## disassembly

```asm
0x1800433d4  mov     [rsp+arg_8], rbx
0x1800433d9  mov     [rsp+arg_10], rbp
0x1800433de  push    rsi
0x1800433df  push    rdi
0x1800433e0  push    r12
0x1800433e2  push    r14
0x1800433e4  push    r15
0x1800433e6  sub     rsp, 30h
0x1800433ea  mov     r15, r8
0x1800433ed  mov     qword ptr [r8], 0
0x1800433f4  mov     r8d, edx; cElements
0x1800433f7  mov     ebx, edx
0x1800433f9  mov     r12, rcx
0x1800433fc  xor     edx, edx; lLbound
0x1800433fe  mov     ecx, 0Ch; vt
0x180043403  call    cs:__imp_SafeArrayCreateVector
0x180043409  mov     [rsp+58h+arg_0], rax
0x18004340e  mov     rdi, rax
0x180043411  test    rax, rax
0x180043414  jnz     short loc_180043460
0x180043416  mov     rcx, cs:WPP_GLOBAL_Control
0x18004341d  lea     rax, WPP_GLOBAL_Control
0x180043424  cmp     rcx, rax
0x180043427  jz      short loc_18004344F
0x180043429  test    byte ptr [rcx+1Ch], 4
0x18004342d  jz      short loc_18004344F
0x18004342f  cmp     byte ptr [rcx+19h], 3
0x180043433  jb      short loc_18004344F
0x180043435  mov     rcx, [rcx+10h]
0x180043439  lea     edx, [rdi+53h]
0x18004343c  mov     r9d, ebx
0x18004343f  mov     [rsp+58h+var_38], ebx
0x180043443  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18004344a  call    WPP_SF_Dd
0x18004344f  lea     rcx, [rsp+58h+arg_0]; this
0x180043454  mov     esi, 8007000Eh
0x180043459  call    ?SafeArrayDestroyAndNull@Imapi2Utility@@YAXAEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::SafeArrayDestroyAndNull(tagSAFEARRAY * &)
0x18004345e  jmp     short loc_1800434A5
0x180043460  mov     r14, [rax+10h]
0x180043464  xor     esi, esi
0x180043466  xor     ebp, ebp
0x180043468  test    ebx, ebx
0x18004346a  jz      short loc_1800434A2
0x18004346c  mov     rcx, r14; pvarg
0x18004346f  call    cs:__imp_VariantInit
0x180043475  mov     rcx, [r12]
0x180043479  mov     rax, [rcx]
0x18004347c  mov     rax, [rax+8]
0x180043480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043485  mov     word ptr [r14], 9
0x18004348b  inc     ebp
0x18004348d  mov     rcx, [r12]
0x180043491  lea     r12, [r12+8]
0x180043496  mov     [r14+8], rcx
0x18004349a  add     r14, 18h
0x18004349e  cmp     ebp, ebx
0x1800434a0  jb      short loc_18004346C
0x1800434a2  mov     [r15], rdi
0x1800434a5  mov     rbx, [rsp+58h+arg_8]
0x1800434aa  mov     eax, esi
0x1800434ac  mov     rbp, [rsp+58h+arg_10]
0x1800434b1  add     rsp, 30h
0x1800434b5  pop     r15
0x1800434b7  pop     r14
0x1800434b9  pop     r12
0x1800434bb  pop     rdi
0x1800434bc  pop     rsi
0x1800434bd  retn
```
