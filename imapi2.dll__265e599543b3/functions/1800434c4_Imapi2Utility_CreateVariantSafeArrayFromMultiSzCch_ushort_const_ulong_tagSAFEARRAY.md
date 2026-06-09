# Imapi2Utility::CreateVariantSafeArrayFromMultiSzCch(ushort const *,ulong,tagSAFEARRAY * *)

- ea: `0x1800434c4`
- end: `0x1800436f1`
- name: `?CreateVariantSafeArrayFromMultiSzCch@Imapi2Utility@@YA?BJPEBGKPEAPEAUtagSAFEARRAY@@@Z`
- size: `557`
- prototype: `__int64 __fastcall(OLECHAR *strIn, const unsigned __int16 *, unsigned int, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002c9d0`

## callees

- `0x180012700`
- `0x180014134`
- `0x180016778`
- `0x18001cb0c`
- `0x1800236b4`
- `0x180023790`
- `0x1800434c4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180043651`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180043651`
- `OLEAUT32!__imp_VariantInit` at `0x180043632`
- `OLEAUT32!__imp_VariantInit` at `0x180043632`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180043554`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180043554`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::CreateVariantSafeArrayFromMultiSzCch(
        OLECHAR *strIn,
        struct tagSAFEARRAY **a2,
        SAFEARRAY **a3,
        struct tagSAFEARRAY **a4)
{
  const OLECHAR *v5; // rsi
  int v6; // r9d
  unsigned int v7; // edi
  bool v8; // zf
  unsigned int v9; // eax
  ULONG v10; // edi
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v12; // r14
  unsigned int v13; // ebx
  __int128 v14; // xmm0
  __int64 v15; // rcx
  VARIANTARG *pvData; // r12
  int v17; // ebp
  ULONG v18; // r15d
  __int64 v19; // rdx
  BSTR v20; // rax
  __int128 v22; // [rsp+40h] [rbp-68h] BYREF
  char v23[88]; // [rsp+50h] [rbp-58h] BYREF
  SAFEARRAY *v24; // [rsp+C8h] [rbp+20h] BYREF

  v24 = 0;
  v5 = strIn;
  v6 = (int)a2;
  v7 = 0;
  if ( !(_DWORD)a2 )
  {
LABEL_11:
    v10 = 0;
    goto LABEL_12;
  }
  do
  {
    v8 = *strIn == 0;
    v9 = v7 + 1;
    ++strIn;
    if ( !v8 )
      v9 = v7;
    v7 = v9;
    --v6;
  }
  while ( v6 );
  if ( (unsigned int)a2 <= 2 )
  {
    if ( (_DWORD)a2 == 1
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
    }
    goto LABEL_11;
  }
  if ( v9 < 2 )
  {
    v13 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = *(_OWORD *)LOG_BLOB(v23, 2LL * (unsigned int)a2, v5);
      v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v22 = v14;
      WPP_SF__HEX_(v15, 79, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, &v22);
    }
    goto LABEL_38;
  }
  v10 = v9 - 1;
LABEL_12:
  Vector = SafeArrayCreateVector(0xCu, 0, v10);
  v24 = Vector;
  v12 = Vector;
  if ( !Vector )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, v10, v10);
    }
    v13 = -2147024882;
LABEL_38:
    Imapi2Utility::SafeArrayDestroyAndNull((Imapi2Utility *)&v24, a2);
    return v13;
  }
  pvData = (VARIANTARG *)Vector->pvData;
  v17 = 0;
  v18 = 0;
  while ( v18 < v10 )
  {
    VariantInit(pvData);
    v19 = -1;
    pvData->vt = 8;
    do
      ++v19;
    while ( v5[v19] );
    v20 = SysAllocStringLen(v5, v19);
    pvData->llVal = (LONGLONG)v20;
    if ( !v20 )
    {
      v17 = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
      }
    }
    while ( *v5 )
      ++v5;
    ++v5;
    ++v18;
    ++pvData;
    if ( v17 < 0 )
    {
      v13 = v17;
      goto LABEL_38;
    }
  }
  *a3 = v12;
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800434c4  mov     rax, rsp
0x1800434c7  push    rbx
0x1800434c8  push    rbp
0x1800434c9  push    rsi
0x1800434ca  push    rdi
0x1800434cb  push    r12
0x1800434cd  push    r13
0x1800434cf  push    r14
0x1800434d1  push    r15
0x1800434d3  sub     rsp, 68h
0x1800434d7  xor     ebx, ebx
0x1800434d9  lea     r15, WPP_GLOBAL_Control
0x1800434e0  mov     [rax+20h], rbx
0x1800434e4  mov     r13, r8
0x1800434e7  lea     r12, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x1800434ee  mov     rsi, rcx
0x1800434f1  mov     r9d, edx
0x1800434f4  mov     edi, ebx
0x1800434f6  mov     bpl, 4
0x1800434f9  test    edx, edx
0x1800434fb  jz      short loc_180043548
0x1800434fd  cmp     [rcx], bx
0x180043500  lea     eax, [rdi+1]
0x180043503  lea     rcx, [rcx+2]
0x180043507  cmovnz  eax, edi
0x18004350a  mov     edi, eax
0x18004350c  add     r9d, 0FFFFFFFFh
0x180043510  jnz     short loc_1800434FD
0x180043512  cmp     edx, 2
0x180043515  ja      loc_1800435A6
0x18004351b  cmp     edx, 1
0x18004351e  jnz     short loc_180043548
0x180043520  mov     rcx, cs:WPP_GLOBAL_Control
0x180043527  cmp     rcx, r15
0x18004352a  jz      short loc_180043548
0x18004352c  test    [rcx+1Ch], bpl
0x180043530  jz      short loc_180043548
0x180043532  cmp     byte ptr [rcx+19h], 3
0x180043536  jb      short loc_180043548
0x180043538  mov     rcx, [rcx+10h]
0x18004353c  lea     edx, [r9+4Eh]
0x180043540  mov     r8, r12
0x180043543  call    WPP_SF_
0x180043548  mov     edi, ebx
0x18004354a  mov     ecx, 0Ch; vt
0x18004354f  mov     r8d, edi; cElements
0x180043552  xor     edx, edx; lLbound
0x180043554  call    cs:__imp_SafeArrayCreateVector
0x18004355a  mov     [rsp+0A8h+arg_18], rax
0x180043562  mov     r14, rax
0x180043565  test    rax, rax
0x180043568  jnz     loc_180043618
0x18004356e  mov     rcx, cs:WPP_GLOBAL_Control
0x180043575  cmp     rcx, r15
0x180043578  jz      short loc_18004359C
0x18004357a  test    [rcx+1Ch], bpl
0x18004357e  jz      short loc_18004359C
0x180043580  cmp     byte ptr [rcx+19h], 3
0x180043584  jb      short loc_18004359C
0x180043586  mov     rcx, [rcx+10h]
0x18004358a  lea     edx, [rax+50h]
0x18004358d  mov     r9d, edi
0x180043590  mov     [rsp+0A8h+var_88], edi
0x180043594  mov     r8, r12
0x180043597  call    WPP_SF_Dd
0x18004359c  mov     ebx, 8007000Eh
0x1800435a1  jmp     loc_1800436C9
0x1800435a6  cmp     edi, 2
0x1800435a9  jnb     short loc_180043611
0x1800435ab  mov     ebx, 80004005h
0x1800435b0  mov     rax, cs:WPP_GLOBAL_Control
0x1800435b7  cmp     rax, r15
0x1800435ba  jz      loc_1800436C9
0x1800435c0  test    [rax+1Ch], bpl
0x1800435c4  jz      loc_1800436C9
0x1800435ca  cmp     byte ptr [rax+19h], 2
0x1800435ce  jb      loc_1800436C9
0x1800435d4  mov     edx, edx
0x1800435d6  lea     rcx, [rsp+0A8h+var_58]
0x1800435db  add     rdx, rdx
0x1800435de  mov     r8, rsi
0x1800435e1  call    ?LOG_BLOB@@YA?AU_IMAPI_BLOB@@_KPEBX@Z; LOG_BLOB(unsigned __int64,void const *)
0x1800435e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800435ed  lea     r9, [rsp+0A8h+var_68]
0x1800435f2  mov     edx, 4Fh ; 'O'
0x1800435f7  mov     r8, r12
0x1800435fa  movups  xmm0, xmmword ptr [rax]
0x1800435fd  mov     rcx, [rcx+10h]
0x180043601  movdqu  [rsp+0A8h+var_68], xmm0
0x180043607  call    WPP_SF__HEX_
0x18004360c  jmp     loc_1800436C9
0x180043611  dec     edi
0x180043613  jmp     loc_18004354A
0x180043618  mov     r12, [rax+10h]
0x18004361c  mov     ebp, ebx
0x18004361e  mov     r15d, ebx
0x180043621  mov     ebx, 8007000Eh
0x180043626  cmp     r15d, edi
0x180043629  jnb     loc_1800436D8
0x18004362f  mov     rcx, r12; pvarg
0x180043632  call    cs:__imp_VariantInit
0x180043638  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004363c  mov     word ptr [r12], 8
0x180043643  xor     eax, eax
0x180043645  inc     rdx; ui
0x180043648  cmp     [rsi+rdx*2], ax
0x18004364c  jnz     short loc_180043645
0x18004364e  mov     rcx, rsi; strIn
0x180043651  call    cs:__imp_SysAllocStringLen
0x180043657  mov     [r12+8], rax
0x18004365c  test    rax, rax
0x18004365f  jnz     short loc_1800436A7
0x180043661  mov     ebp, ebx
0x180043663  mov     rcx, cs:WPP_GLOBAL_Control
0x18004366a  lea     rax, WPP_GLOBAL_Control
0x180043671  cmp     rcx, rax
0x180043674  jz      short loc_1800436A7
0x180043676  test    byte ptr [rcx+1Ch], 4
0x18004367a  jz      short loc_1800436A7
0x18004367c  cmp     byte ptr [rcx+19h], 3
0x180043680  jb      short loc_1800436A7
0x180043682  mov     rcx, [rcx+10h]
0x180043686  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18004368d  mov     [rsp+0A8h+var_78], edi
0x180043691  mov     edx, 51h ; 'Q'
0x180043696  mov     [rsp+0A8h+var_80], edi
0x18004369a  mov     r9d, r15d
0x18004369d  mov     [rsp+0A8h+var_88], r15d
0x1800436a2  call    WPP_SF_DDDd
0x1800436a7  xor     eax, eax
0x1800436a9  jmp     short loc_1800436AF
0x1800436ab  add     rsi, 2
0x1800436af  cmp     [rsi], ax
0x1800436b2  jnz     short loc_1800436AB
0x1800436b4  add     rsi, 2
0x1800436b8  inc     r15d
0x1800436bb  add     r12, 18h
0x1800436bf  test    ebp, ebp
0x1800436c1  jns     loc_180043626
0x1800436c7  mov     ebx, ebp
0x1800436c9  lea     rcx, [rsp+0A8h+arg_18]; this
0x1800436d1  call    ?SafeArrayDestroyAndNull@Imapi2Utility@@YAXAEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::SafeArrayDestroyAndNull(tagSAFEARRAY * &)
0x1800436d6  jmp     short loc_1800436DE
0x1800436d8  mov     [r13+0], r14
0x1800436dc  mov     ebx, ebp
0x1800436de  mov     eax, ebx
0x1800436e0  add     rsp, 68h
0x1800436e4  pop     r15
0x1800436e6  pop     r14
0x1800436e8  pop     r13
0x1800436ea  pop     r12
0x1800436ec  pop     rdi
0x1800436ed  pop     rsi
0x1800436ee  pop     rbp
0x1800436ef  pop     rbx
0x1800436f0  retn
```
