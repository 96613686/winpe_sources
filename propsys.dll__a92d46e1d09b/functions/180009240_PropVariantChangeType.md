# PropVariantChangeType

- ea: `0x180009240`
- end: `0x18000957c`
- name: `PropVariantChangeType`
- size: `828`
- prototype: `HRESULT __stdcall(PROPVARIANT *ppropvarDest, const PROPVARIANT *const propvarSrc, PROPVAR_CHANGE_FLAGS flags, VARTYPE vt)`
- caller_count: `27`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008870`
- `0x180009590`
- `0x180009db0`
- `0x18000b560`
- `0x18000f050`
- `0x180016110`
- `0x180019200`
- `0x180021374`
- `0x1800224d0`
- `0x1800228a4`
- `0x180027610`
- `0x18002a824`
- `0x18002bd14`
- `0x18002c3fc`
- `0x18002d8f0`
- `0x180034fc0`
- `0x180041950`
- `0x180048220`
- `0x18004a330`
- `0x180060cf0`
- `0x180061ec0`
- `0x180065ee0`
- `0x18006af24`
- `0x180081ab0`
- `0x18008eb60`
- `0x18008f050`
- `0x180094e40`

## callees

- `0x180009240`
- `0x180009590`
- `0x18000fa10`
- `0x180065b84`
- `0x18006ed20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180009466`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180009466`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180009405`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180009405`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000943f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000943f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180009420`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180009420`

## pseudocode

```c
HRESULT __stdcall PropVariantChangeType(
        PROPVARIANT *ppropvarDest,
        const PROPVARIANT *const propvarSrc,
        PROPVAR_CHANGE_FLAGS flags,
        VARTYPE vt)
{
  unsigned int v4; // edi
  unsigned __int16 v6; // bp
  const struct tagPROPVARIANT *v7; // rsi
  __int64 v9; // rcx
  __int16 v10; // r8
  HRESULT v11; // ebx
  unsigned int v12; // edx
  int lVal; // eax
  SAFEARRAY *parray; // r15
  LONG plUbound; // [rsp+30h] [rbp-88h] BYREF
  LONG plLbound; // [rsp+34h] [rbp-84h] BYREF
  __int128 v18; // [rsp+38h] [rbp-80h] BYREF
  __int64 v19; // [rsp+48h] [rbp-70h]
  __int128 v20; // [rsp+50h] [rbp-68h] BYREF
  __int64 v21; // [rsp+60h] [rbp-58h]

  v4 = vt;
  v19 = 0;
  *(_OWORD *)ppropvarDest = 0;
  ppropvarDest[2] = 0;
  v6 = *(_WORD *)propvarSrc;
  v7 = (const struct tagPROPVARIANT *)propvarSrc;
  v18 = 0;
  if ( v6 == 31 )
  {
    v6 = 31;
    if ( !*((_QWORD *)propvarSrc + 1) )
    {
      LOWORD(v18) = 31;
      *((_QWORD *)&v18 + 1) = &Src;
      v7 = (const struct tagPROPVARIANT *)&v18;
    }
  }
  v9 = vt & 0xFFF;
  if ( (unsigned int)v9 > 0x1F )
  {
    if ( (unsigned int)(v9 - 64) > 9 )
    {
      v10 = 32;
      if ( (_DWORD)v9 == 4095 )
        v10 = 4112;
    }
    else
    {
      v10 = aAggregateprope[v9 + 4];
    }
  }
  else
  {
    v10 = *((_WORD *)&CRGTypeSizes::m_ucTypeSizesA + v9);
  }
  if ( (v10 & 0x20) != 0 )
    goto LABEL_7;
  if ( (vt & 0xF000) != 0 )
  {
    if ( (vt & 0x8000u) != 0
      || (vt & 0x1000) != 0 && ((vt & 0x6000) != 0 || (v10 & 0x1000) == 0)
      || (vt & 0x2000) != 0 && ((vt & 0x5000) != 0 || (v10 & 0x2000) == 0)
      || (vt & 0x4000) != 0 && ((vt & 0x3000) != 0 || (v10 & 0x4000) == 0) )
    {
      goto LABEL_7;
    }
  }
  else if ( v10 >= 0 )
  {
LABEL_7:
    v11 = -2147024809;
    goto LABEL_8;
  }
  if ( !(unsigned int)IsPropVariantValidForVista(v7) )
    goto LABEL_7;
  if ( v4 < 2 )
  {
    *(_WORD *)ppropvarDest = v4;
    v11 = 0;
LABEL_8:
    if ( v6 == (_WORD)v4 )
      return v11;
LABEL_19:
    if ( (byte_1800F1382 & 0x10) != 0 )
      McTemplateU0hhq_EtwEventWriteTransfer(
        v9,
        (unsigned int)ShellTraceId_Properties_PropVariantChangeType_Coercion_Info,
        v6,
        (unsigned __int16)v4,
        v11);
    return v11;
  }
  v12 = v7->vt;
  v21 = 0;
  v20 = 0;
  if ( v12 != 8 )
  {
    if ( v12 <= 0xFFF )
    {
      if ( v12 != 4095 )
      {
        switch ( v12 )
        {
          case 2u:
          case 3u:
          case 4u:
          case 5u:
          case 6u:
          case 7u:
          case 9u:
          case 0xAu:
          case 0xBu:
          case 0xCu:
          case 0xDu:
          case 0xEu:
          case 0x10u:
          case 0x11u:
          case 0x12u:
          case 0x13u:
          case 0x14u:
          case 0x15u:
          case 0x16u:
          case 0x17u:
          case 0x1Eu:
          case 0x1Fu:
          case 0x40u:
          case 0x41u:
          case 0x42u:
          case 0x43u:
          case 0x44u:
          case 0x45u:
          case 0x47u:
          case 0x48u:
          case 0x49u:
            goto LABEL_17;
          default:
            goto LABEL_23;
        }
      }
      goto LABEL_17;
    }
LABEL_23:
    if ( (v12 & 0x4000) != 0 )
      goto LABEL_17;
    if ( (v12 & 0x1000) != 0 )
    {
      lVal = v7->lVal;
    }
    else
    {
      if ( (v12 & 0x2000) == 0
        || (parray = v7->parray, SafeArrayGetDim(parray) != 1)
        || (plLbound = 0, SafeArrayGetLBound(parray, 1u, &plLbound) < 0)
        || (plUbound = 0, SafeArrayGetUBound(parray, 1u, &plUbound) < 0)
        || plUbound < plLbound )
      {
LABEL_27:
        v7 = (const struct tagPROPVARIANT *)&v20;
        goto LABEL_17;
      }
      lVal = plUbound - plLbound + 1;
    }
    if ( lVal )
      goto LABEL_17;
    goto LABEL_27;
  }
LABEL_17:
  if ( v6 != (_WORD)v4 )
  {
    v11 = _StrictPropVariantCoerceType(ppropvarDest, v7, flags, v4);
    goto LABEL_19;
  }
  return PropVariantCopy(ppropvarDest, (const PROPVARIANT *)v7);
}

```

## disassembly

```asm
0x180009240  push    rbx
0x180009242  push    rbp
0x180009243  push    rsi
0x180009244  push    rdi
0x180009245  push    r12
0x180009247  push    r14
0x180009249  sub     rsp, 88h
0x180009250  mov     rax, cs:__security_cookie
0x180009257  xor     rax, rsp
0x18000925a  mov     [rsp+0B8h+var_50], rax
0x18000925f  xor     eax, eax
0x180009261  movzx   edi, r9w
0x180009265  xorps   xmm0, xmm0
0x180009268  mov     [rsp+0B8h+var_70], rax
0x18000926d  movups  xmmword ptr [rcx], xmm0
0x180009270  mov     [rcx+10h], rax
0x180009274  mov     r12d, r8d
0x180009277  movzx   ebp, word ptr [rdx]
0x18000927a  mov     rsi, rdx
0x18000927d  mov     r14, rcx
0x180009280  movups  [rsp+0B8h+var_80], xmm0
0x180009285  cmp     bp, 1Fh
0x180009289  jz      loc_1800093A9
0x18000928f  mov     ecx, edi
0x180009291  lea     rbx, __ImageBase
0x180009298  and     ecx, 0FFFh
0x18000929e  cmp     ecx, 1Fh
0x1800092a1  ja      loc_180009471
0x1800092a7  movzx   r8d, ds:rva ?m_ucTypeSizesA@CRGTypeSizes@@0QBGB[rbx+rcx*2]; ushort const near * const CRGTypeSizes::m_ucTypeSizesA ...
0x1800092b0  mov     [rsp+0B8h+var_38], r13
0x1800092b8  mov     [rsp+0B8h+var_40], r15
0x1800092bd  test    r8b, 20h
0x1800092c1  jnz     short loc_1800092D1
0x1800092c3  test    edi, 0FFFFF000h
0x1800092c9  jnz     short loc_1800092DD
0x1800092cb  test    r8w, r8w
0x1800092cf  js      short loc_180009303
0x1800092d1  mov     ebx, 80070057h
0x1800092d6  cmp     bp, di
0x1800092d9  jz      short loc_180009359
0x1800092db  jmp     short loc_18000934C
0x1800092dd  test    di, di
0x1800092e0  js      short loc_1800092D1
0x1800092e2  bt      di, 0Ch
0x1800092e7  jb      loc_18000950B
0x1800092ed  bt      di, 0Dh
0x1800092f2  jb      loc_18000951B
0x1800092f8  bt      di, 0Eh
0x1800092fd  jb      loc_180009492
0x180009303  mov     rcx, rsi; struct tagPROPVARIANT *
0x180009306  call    ?IsPropVariantValidForVista@@YAHAEBUtagPROPVARIANT@@@Z; IsPropVariantValidForVista(tagPROPVARIANT const &)
0x18000930b  test    eax, eax
0x18000930d  jz      short loc_1800092D1
0x18000930f  cmp     edi, 2
0x180009312  jb      loc_180009487
0x180009318  movzx   edx, word ptr [rsi]
0x18000931b  xor     eax, eax
0x18000931d  mov     [rsp+0B8h+var_58], rax
0x180009322  xorps   xmm0, xmm0
0x180009325  movups  [rsp+0B8h+var_68], xmm0
0x18000932a  cmp     edx, 8
0x18000932d  jnz     short loc_180009385
0x18000932f  mov     rdx, rsi; jumptable 00000001800093F5 cases 2-7,9-14,16-23,30,31,64-69,71-73
0x180009332  mov     rcx, r14; pVar
0x180009335  cmp     bp, di
0x180009338  jz      loc_180009466
0x18000933e  movzx   r9d, di; unsigned __int16
0x180009342  mov     r8d, r12d; int
0x180009345  call    ?_StrictPropVariantCoerceType@@YAJPEAUtagPROPVARIANT@@AEBU1@HG@Z; _StrictPropVariantCoerceType(tagPROPVARIANT *,tagPROPVARIANT const &,int,ushort)
0x18000934a  mov     ebx, eax
0x18000934c  test    cs:byte_1800F1382, 10h
0x180009353  jnz     loc_1800094B1
0x180009359  mov     eax, ebx
0x18000935b  mov     r15, [rsp+0B8h+var_40]
0x180009360  mov     r13, [rsp+0B8h+var_38]
0x180009368  mov     rcx, [rsp+0B8h+var_50]
0x18000936d  xor     rcx, rsp; StackCookie
0x180009370  call    __security_check_cookie
0x180009375  add     rsp, 88h
0x18000937c  pop     r14
0x18000937e  pop     r12
0x180009380  pop     rdi
0x180009381  pop     rsi
0x180009382  pop     rbp
0x180009383  pop     rbx
0x180009384  retn
0x180009385  cmp     edx, 0FFFh
0x18000938b  jbe     short loc_1800093D3
0x18000938d  bt      dx, 0Eh; jumptable 00000001800093F5 default case, cases 8,15,24-29,32-63,70
0x180009392  jb      short loc_18000932F; jumptable 00000001800093F5 cases 2-7,9-14,16-23,30,31,64-69,71-73
0x180009394  bt      dx, 0Ch
0x180009399  jnb     short loc_1800093F7
0x18000939b  mov     eax, [rsi+8]
0x18000939e  test    eax, eax
0x1800093a0  jnz     short loc_18000932F; jumptable 00000001800093F5 cases 2-7,9-14,16-23,30,31,64-69,71-73
0x1800093a2  lea     rsi, [rsp+0B8h+var_68]
0x1800093a7  jmp     short loc_18000932F; jumptable 00000001800093F5 cases 2-7,9-14,16-23,30,31,64-69,71-73
0x1800093a9  mov     ebp, 1Fh
0x1800093ae  cmp     [rdx+8], rax
0x1800093b2  jnz     loc_18000928F
0x1800093b8  lea     rax, Src
0x1800093bf  mov     word ptr [rsp+0B8h+var_80], bp
0x1800093c4  mov     qword ptr [rsp+0B8h+var_80+8], rax
0x1800093c9  lea     rsi, [rsp+0B8h+var_80]
0x1800093ce  jmp     loc_18000928F
0x1800093d3  jz      loc_18000932F; jumptable 00000001800093F5 cases 2-7,9-14,16-23,30,31,64-69,71-73
0x1800093d9  lea     eax, [rdx-2]; switch 72 cases
0x1800093dc  cmp     eax, 47h
0x1800093df  ja      short def_1800093F5; jumptable 00000001800093F5 default case, cases 8,15,24-29,32-63,70
0x1800093e1  cdqe
0x1800093e3  movzx   eax, ds:(byte_180009534 - 180000000h)[rbx+rax]
0x1800093eb  mov     ecx, ds:(jpt_1800093F5 - 180000000h)[rbx+rax*4]
0x1800093f2  add     rcx, rbx
0x1800093f5  jmp     rcx; switch jump
0x1800093f7  bt      dx, 0Dh
0x1800093fc  jnb     short loc_1800093A2
0x1800093fe  mov     r15, [rsi+8]
0x180009402  mov     rcx, r15; psa
0x180009405  call    cs:__imp_SafeArrayGetDim
0x18000940b  cmp     eax, 1
0x18000940e  jnz     short loc_1800093A2
0x180009410  xor     ebx, ebx
0x180009412  lea     r8, [rsp+0B8h+plLbound]; plLbound
0x180009417  mov     edx, eax; nDim
0x180009419  mov     [rsp+0B8h+plLbound], ebx
0x18000941d  mov     rcx, r15; psa
0x180009420  call    cs:__imp_SafeArrayGetLBound
0x180009426  test    eax, eax
0x180009428  js      loc_1800093A2
0x18000942e  lea     r8, [rsp+0B8h+plUbound]; plUbound
0x180009433  mov     [rsp+0B8h+plUbound], ebx
0x180009437  mov     edx, 1; nDim
0x18000943c  mov     rcx, r15; psa
0x18000943f  call    cs:__imp_SafeArrayGetUBound
0x180009445  test    eax, eax
0x180009447  js      loc_1800093A2
0x18000944d  mov     eax, [rsp+0B8h+plUbound]
0x180009451  mov     ecx, [rsp+0B8h+plLbound]
0x180009455  cmp     eax, ecx
0x180009457  jl      loc_1800093A2
0x18000945d  sub     eax, ecx
0x18000945f  inc     eax
0x180009461  jmp     loc_18000939E
0x180009466  call    cs:__imp_PropVariantCopy
0x18000946c  jmp     loc_18000935B
0x180009471  lea     eax, [rcx-40h]
0x180009474  cmp     eax, 9
0x180009477  ja      short loc_1800094CE
0x180009479  movzx   r8d, word ptr ds:(rva aAggregateprope+8)[rbx+rcx*2]; "egatePropertyProvider" ...
0x180009482  jmp     loc_1800092B0
0x180009487  mov     [r14], di
0x18000948b  xor     ebx, ebx
0x18000948d  jmp     loc_1800092D6
0x180009492  mov     eax, 3000h
0x180009497  test    ax, di
0x18000949a  jnz     loc_1800092D1
0x1800094a0  bt      r8w, 0Eh
0x1800094a6  jnb     loc_1800092D1
0x1800094ac  jmp     loc_180009303
0x1800094b1  movzx   r9d, di
0x1800094b5  mov     [rsp+0B8h+var_98], ebx
0x1800094b9  movzx   r8d, bp
0x1800094bd  lea     rdx, ShellTraceId_Properties_PropVariantChangeType_Coercion_Info
0x1800094c4  call    McTemplateU0hhq_EtwEventWriteTransfer
0x1800094c9  jmp     loc_180009359
0x1800094ce  cmp     ecx, 0FFFh
0x1800094d4  mov     eax, 1010h
0x1800094d9  mov     r8d, 20h ; ' '
0x1800094df  cmovz   r8w, ax
0x1800094e4  jmp     loc_1800092B0
0x1800094e9  bt      r8w, 0Ch
0x1800094ef  jnb     loc_1800092D1
0x1800094f5  jmp     loc_1800092ED
0x1800094fa  bt      r8w, 0Dh
0x180009500  jb      loc_1800092F8
0x180009506  jmp     loc_1800092D1
0x18000950b  mov     eax, 6000h
0x180009510  test    ax, di
0x180009513  jnz     loc_1800092D1
0x180009519  jmp     short loc_1800094E9
0x18000951b  mov     eax, 5000h
0x180009520  test    ax, di
0x180009523  jnz     loc_1800092D1
0x180009529  jmp     short loc_1800094FA
```
