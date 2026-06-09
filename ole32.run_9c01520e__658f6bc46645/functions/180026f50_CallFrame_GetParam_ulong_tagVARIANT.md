# CallFrame::GetParam(ulong,tagVARIANT *)

- ea: `0x180026f50`
- end: `0x18002726c`
- name: `?GetParam@CallFrame@@UEAAJKPEAUtagVARIANT@@@Z`
- size: `796`
- prototype: `HRESULT __fastcall(CallFrame *this, unsigned int iParam, tagVARIANT *pvar)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180026f50`
- `0x1800ce967`
- `0x1800d8010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180026f80`
- `OLEAUT32!__imp_VariantInit` at `0x180026fc4`
- `OLEAUT32!__imp_VariantInit` at `0x1800271d7`
- `OLEAUT32!__imp_VariantInit` at `0x180026f80`
- `OLEAUT32!__imp_VariantInit` at `0x180026fc4`
- `OLEAUT32!__imp_VariantInit` at `0x1800271d7`
- `OLEAUT32!__imp_VariantCopy` at `0x18002706f`
- `OLEAUT32!__imp_VariantCopy` at `0x18002706f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800271b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800271b6`

## pseudocode

```c
HRESULT __fastcall CallFrame::GetParam(CallFrame *this, unsigned int iParam, tagVARIANT *pvar)
{
  __int64 v3; // rbx
  PARAM_DESCRIPTION *m_params; // r12
  __int64 v7; // rdi
  MD_METHOD *m_pmd; // r8
  METHOD_DESCRIPTOR *m_rgMethodDescs; // rcx
  unsigned __int16 vt; // ax
  unsigned int m_cbPushedByCaller; // ecx
  size_t v12; // r8
  bool v14; // zf
  int v15; // ecx
  int v16; // ecx
  bool v17; // zf
  int v18; // ecx
  bool v19; // zf
  int v20; // ecx
  VARIANTARG *v21; // rax
  __int64 v22; // rbx
  tagVARIANT varTemp; // [rsp+20h] [rbp-48h] BYREF

  v3 = iParam;
  if ( !pvar )
    return -2147467261;
  VariantInit(pvar);
  m_params = this->m_pmd->m_params;
  v7 = ((__int64 (__fastcall *)(CallFrame *))this->ICallFrame::IUnknown::lpVtbl[2].QueryInterface)(this)
     + m_params[v3].StackOffset;
  memset(&varTemp, 0, sizeof(varTemp));
  VariantInit(&varTemp);
  m_pmd = this->m_pmd;
  m_rgMethodDescs = this->m_pInterceptor->m_ndrTypeInfo.m_ptr->m_rgMethodDescs;
  if ( (unsigned int)v3 >= m_rgMethodDescs[m_pmd->m_info.iMethod].m_cParams )
    return -2147352562;
  varTemp.vt = m_rgMethodDescs[m_pmd->m_info.iMethod].m_paramVTs[v3];
  vt = varTemp.vt & 0xF000;
  if ( (varTemp.vt & 0x2000) == 0 )
    vt = varTemp.vt;
  if ( vt > 0x24u )
  {
    if ( vt <= 0x400Bu )
    {
      if ( vt == 16395 )
        goto LABEL_7;
      if ( vt <= 0x4005u )
      {
        if ( vt == 16389 || vt == 0x2000 || vt == 0x4000 )
          goto LABEL_7;
        v18 = vt - 16386;
        v17 = vt == 16386;
        goto LABEL_22;
      }
      v15 = vt - 16390;
      v14 = vt == 16390;
LABEL_19:
      if ( v14 )
        goto LABEL_7;
      v16 = v15 - 1;
      if ( !v16 )
        goto LABEL_7;
      v18 = v16 - 1;
      v17 = v18 == 0;
LABEL_22:
      if ( !v17 )
      {
        v20 = v18 - 1;
        v19 = v20 == 0;
        goto LABEL_24;
      }
LABEL_7:
      if ( (_DWORD)v3 == m_pmd->m_numberOfParams )
        m_cbPushedByCaller = m_pmd->m_cbPushedByCaller;
      else
        m_cbPushedByCaller = m_pmd->m_params[(unsigned int)(v3 + 1)].StackOffset;
      v12 = m_cbPushedByCaller - m_params[v3].StackOffset;
      if ( v12 <= 0x10 )
      {
        memcpy_0(&varTemp.boolVal, (const void *)v7, v12);
        return VariantCopy(pvar, &varTemp);
      }
      return -2147352568;
    }
    if ( vt > 0x4012u )
    {
      if ( vt == 16403 || vt == 16406 || vt == 16407 || vt == 16420 || vt == 24576 )
        goto LABEL_7;
      return -2147352568;
    }
    if ( vt == 16402 || vt == 16396 || vt == 16397 || vt == 16398 )
      goto LABEL_7;
    v20 = vt - 16400;
    v19 = vt == 16400;
LABEL_24:
    if ( v19 || v20 == 1 )
      goto LABEL_7;
    return -2147352568;
  }
  if ( vt == 36 )
    goto LABEL_7;
  if ( vt <= 0xBu )
  {
    if ( vt == 11 || vt == 2 || vt == 3 || vt == 4 || vt == 5 )
      goto LABEL_7;
    v15 = vt - 6;
    v14 = vt == 6;
    goto LABEL_19;
  }
  if ( vt != 12 )
  {
    switch ( vt )
    {
      case 0xDu:
        goto LABEL_7;
      case 0xEu:
        varTemp.0 = *($F8E77AD38E9438B2F3CDAA40168E3C34 *)v7;
        return VariantCopy(pvar, &varTemp);
      case 0x10u:
      case 0x11u:
      case 0x12u:
      case 0x13u:
        goto LABEL_7;
    }
    v20 = vt - 22;
    v19 = vt == 22;
    goto LABEL_24;
  }
  v21 = (VARIANTARG *)CoTaskMemAlloc(0x18u);
  v22 = (__int64)v21;
  if ( v21 )
  {
    VariantInit(v21);
    *(_WORD *)v22 = *(_WORD *)v7;
    *(_OWORD *)(v22 + 8) = *(_OWORD *)(v7 + 8);
    varTemp.vt |= 0x4000u;
    varTemp.llVal = v22;
    return VariantCopy(pvar, &varTemp);
  }
  return -2147024882;
}

```

## disassembly

```asm
0x180026f50  mov     [rsp+arg_0], rbx
0x180026f55  mov     [rsp+arg_8], rbp
0x180026f5a  mov     [rsp+arg_10], rsi
0x180026f5f  push    rdi
0x180026f60  push    r12
0x180026f62  push    r13
0x180026f64  push    r14
0x180026f66  push    r15
0x180026f68  sub     rsp, 40h
0x180026f6c  mov     ebx, iParam
0x180026f6e  mov     rbp, pvar
0x180026f71  mov     rsi, this
0x180026f74  test    pvar, pvar
0x180026f77  jz      loc_180027150
0x180026f7d  mov     this, pvar; pvarg
0x180026f80  call    cs:__imp_VariantInit
0x180026f87  nop     dword ptr [rax+rax+00h]
0x180026f8c  mov     rax, [rsi+10h]
0x180026f90  lea     r15, [rbx+rbx*2]
0x180026f94  mov     this, rsi
0x180026f97  mov     r12, [rax+8]
0x180026f9b  mov     rax, [rsi]
0x180026f9e  mov     rax, [rax+30h]
0x180026fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fa7  movzx   edi, word ptr [r12+r15*2+2]
0x180026fad  lea     this, [rsp+68h+varTemp]; pvarg
0x180026fb2  add     rdi, rax
0x180026fb5  xorps   xmm0, xmm0
0x180026fb8  xor     eax, eax
0x180026fba  mov     [rsp+68h+varTemp.pRecInfo], rax
0x180026fbf  movups  xmmword ptr [rsp+68h+varTemp.___u0], xmm0
0x180026fc4  call    cs:__imp_VariantInit
0x180026fcb  nop     dword ptr [rax+rax+00h]
0x180026fd0  mov     pvar, [rsi+10h]
0x180026fd4  movsxd  this, dword ptr [pvar+2Ch]
0x180026fd8  lea     rdx, [this+this*2]
0x180026fdc  mov     this, [rsi+40h]
0x180026fe0  mov     rax, [this+68h]
0x180026fe4  mov     this, [rax+38h]
0x180026fe8  movsx   eax, word ptr [this+rdx*8+8]
0x180026fed  cmp     ebx, eax
0x180026fef  jnb     loc_18002715A
0x180026ff5  mov     rax, [this+rdx*8+10h]
0x180026ffa  mov     r9d, 0F000h
0x180027000  mov     r10d, 2000h
0x180027006  movzx   iParam, word ptr [rax+rbx*2]
0x18002700a  movzx   eax, dx
0x18002700d  mov     word ptr [rsp+68h+varTemp.___u0], dx
0x180027012  and     ax, r9w
0x180027016  test    r10w, dx
0x18002701a  cmovz   ax, dx
0x18002701e  movzx   ecx, ax
0x180027021  cmp     ecx, 24h ; '$'
0x180027024  ja      loc_1800270F9
0x18002702a  jnz     short loc_18002709A
0x18002702c  cmp     ebx, [pvar]
0x18002702f  jz      loc_180027147
0x180027035  lea     eax, [rbx+1]
0x180027038  lea     rdx, [rax+rax*2]
0x18002703c  mov     rax, [pvar+8]
0x180027040  movzx   ecx, word ptr [rax+rdx*2+2]
0x180027045  movzx   eax, word ptr [r12+r15*2+2]
0x18002704b  sub     ecx, eax
0x18002704d  mov     r8d, ecx; Size
0x180027050  cmp     pvar, 10h
0x180027054  ja      loc_1800270F2
0x18002705a  mov     rdx, rdi; Src
0x18002705d  lea     this, [rsp+68h+varTemp.___u0+8]; void *
0x180027062  call    memcpy_0
0x180027067  lea     rdx, [rsp+68h+varTemp]; pvargSrc
0x18002706c  mov     this, rbp; pvargDest
0x18002706f  call    cs:__imp_VariantCopy
0x180027076  nop     dword ptr [rax+rax+00h]
0x18002707b  lea     r11, [rsp+68h+var_28]
0x180027080  mov     rbx, [r11+30h]
0x180027084  mov     rbp, [r11+38h]
0x180027088  mov     rsi, [r11+40h]
0x18002708c  mov     rsp, r11
0x18002708f  pop     r15
0x180027091  pop     r14
0x180027093  pop     r13
0x180027095  pop     r12
0x180027097  pop     rdi
0x180027098  retn
0x18002709a  cmp     ecx, 0Bh
0x18002709d  ja      loc_180027164
0x1800270a3  jz      short loc_18002702C
0x1800270a5  sub     ecx, 2
0x1800270a8  jz      short loc_18002702C
0x1800270aa  sub     ecx, 1
0x1800270ad  jz      loc_18002702C
0x1800270b3  sub     ecx, 1
0x1800270b6  jz      loc_18002702C
0x1800270bc  sub     ecx, 1
0x1800270bf  jz      loc_18002702C
0x1800270c5  sub     ecx, 1
0x1800270c8  jz      loc_18002702C
0x1800270ce  sub     ecx, 1
0x1800270d1  jz      loc_18002702C
0x1800270d7  sub     ecx, 1
0x1800270da  jz      loc_18002702C
0x1800270e0  sub     ecx, 1
0x1800270e3  jz      loc_18002702C
0x1800270e9  cmp     ecx, 1
0x1800270ec  jz      loc_18002702C
0x1800270f2  mov     eax, 80020008h
0x1800270f7  jmp     short loc_18002707B
0x1800270f9  mov     eax, 400Bh
0x1800270fe  cmp     ecx, eax
0x180027100  jbe     loc_180027206
0x180027106  mov     eax, 4012h
0x18002710b  cmp     ecx, eax
0x18002710d  jbe     loc_180027240
0x180027113  sub     ecx, 4013h
0x180027119  jz      loc_18002702C
0x18002711f  sub     ecx, 3
0x180027122  jz      loc_18002702C
0x180027128  sub     ecx, 1
0x18002712b  jz      loc_18002702C
0x180027131  sub     ecx, 0Dh
0x180027134  jz      loc_18002702C
0x18002713a  cmp     ecx, 1FDCh
0x180027140  jnz     short loc_1800270F2
0x180027142  jmp     loc_18002702C
0x180027147  mov     ecx, [pvar+20h]
0x18002714b  jmp     loc_180027045
0x180027150  mov     eax, 80004003h
0x180027155  jmp     loc_18002707B
0x18002715a  mov     eax, 8002000Eh
0x18002715f  jmp     loc_18002707B
0x180027164  sub     ecx, 0Ch
0x180027167  jz      short loc_1800271B1
0x180027169  sub     ecx, 1
0x18002716c  jz      loc_18002702C
0x180027172  sub     ecx, 1
0x180027175  jz      short loc_1800271A3
0x180027177  sub     ecx, 2
0x18002717a  jz      loc_18002702C
0x180027180  sub     ecx, 1
0x180027183  jz      loc_18002702C
0x180027189  sub     ecx, 1
0x18002718c  jz      loc_18002702C
0x180027192  sub     ecx, 1
0x180027195  jz      loc_18002702C
0x18002719b  sub     ecx, 3
0x18002719e  jmp     loc_1800270E3
0x1800271a3  movups  xmm0, xmmword ptr [rdi]
0x1800271a6  movdqu  xmmword ptr [rsp+68h+varTemp.___u0], xmm0
0x1800271ac  jmp     loc_180027067
0x1800271b1  mov     ecx, 18h; cb
0x1800271b6  call    cs:__imp_CoTaskMemAlloc
0x1800271bd  nop     dword ptr [rax+rax+00h]
0x1800271c2  mov     rbx, rax
0x1800271c5  test    rax, rax
0x1800271c8  jnz     short loc_1800271D4
0x1800271ca  mov     eax, 8007000Eh
0x1800271cf  jmp     loc_18002707B
0x1800271d4  mov     this, rbx; pvarg
0x1800271d7  call    cs:__imp_VariantInit
0x1800271de  nop     dword ptr [rax+rax+00h]
0x1800271e3  movzx   eax, word ptr [rdi]
0x1800271e6  mov     [rbx], ax
0x1800271e9  mov     eax, 4000h
0x1800271ee  movups  xmm0, xmmword ptr [rdi+8]
0x1800271f2  movdqu  xmmword ptr [rbx+8], xmm0
0x1800271f7  or      word ptr [rsp+68h+varTemp.___u0], ax
0x1800271fc  mov     qword ptr [rsp+68h+varTemp.___u0+8], rbx
0x180027201  jmp     loc_180027067
0x180027206  jz      loc_18002702C
0x18002720c  mov     eax, 4005h
0x180027211  cmp     ecx, eax
0x180027213  ja      short loc_180027235
0x180027215  jz      loc_18002702C
0x18002721b  sub     ecx, r10d
0x18002721e  jz      loc_18002702C
0x180027224  sub     ecx, r10d
0x180027227  jz      loc_18002702C
0x18002722d  sub     ecx, 2
0x180027230  jmp     loc_1800270DA
0x180027235  sub     ecx, 4006h
0x18002723b  jmp     loc_1800270C8
0x180027240  jz      loc_18002702C
0x180027246  sub     ecx, 400Ch
0x18002724c  jz      loc_18002702C
0x180027252  sub     ecx, 1
0x180027255  jz      loc_18002702C
0x18002725b  sub     ecx, 1
0x18002725e  jz      loc_18002702C
0x180027264  sub     ecx, 2
0x180027267  jmp     loc_1800270E3
```
