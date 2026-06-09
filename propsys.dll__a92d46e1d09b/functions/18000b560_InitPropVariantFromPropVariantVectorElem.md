# InitPropVariantFromPropVariantVectorElem

- ea: `0x18000b560`
- end: `0x18000b923`
- name: `InitPropVariantFromPropVariantVectorElem`
- size: `963`
- prototype: `HRESULT __stdcall(const PROPVARIANT *const propvarIn, ULONG iElem, PROPVARIANT *ppropvar)`
- caller_count: `12`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000c5dc`
- `0x18000df60`
- `0x18000f050`
- `0x18002b6c4`
- `0x180032ba4`
- `0x18005b8c0`
- `0x180063a6c`
- `0x180066dd4`
- `0x18007a67c`
- `0x18007a7d0`
- `0x18007ae08`
- `0x18007ef20`

## callees

- `0x180009240`
- `0x18000b410`
- `0x18000b560`
- `0x18000c890`
- `0x18000fa10`
- `0x180015170`
- `0x180033310`
- `0x180033e40`
- `0x1800537f0`
- `0x18006ed20`
- `0x18006fb80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000b80a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000b8b5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000b80a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000b8b5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b7d7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b7d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b647`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b647`
- `OLEAUT32!__imp_VariantClear` at `0x18000b7e2`
- `OLEAUT32!__imp_VariantClear` at `0x18000b7ed`
- `OLEAUT32!__imp_VariantClear` at `0x18000b7e2`
- `OLEAUT32!__imp_VariantClear` at `0x18000b7ed`

## pseudocode

```c
HRESULT __stdcall InitPropVariantFromPropVariantVectorElem(
        const PROPVARIANT *const propvarIn,
        ULONG iElem,
        PROPVARIANT *ppropvar)
{
  __int64 v3; // rsi
  int inited; // edi
  int v7; // r9d
  unsigned int v8; // r8d
  __int64 v9; // rcx
  wchar_t v10; // dx
  unsigned int v11; // edx
  _WORD *v12; // rbx
  __int64 v13; // rax
  SIZE_T v15; // rsi
  void *v16; // rax
  __int128 v18; // xmm0
  VARIANT pVar; // [rsp+20h] [rbp-68h] BYREF
  VARIANT pvar; // [rsp+38h] [rbp-50h] BYREF
  PROPVARIANT propvarSrc[2]; // [rsp+50h] [rbp-38h] BYREF
  PROPVARIANT v22; // [rsp+60h] [rbp-28h]

  v3 = iElem;
  *(_OWORD *)ppropvar = 0;
  ppropvar[2] = 0;
  inited = -2147024809;
  if ( !(unsigned int)IsPropVariantValidForVista((const struct tagPROPVARIANT *)propvarIn)
    || (unsigned int)v3 >= PropVariantGetElementCount(propvarIn) )
  {
    return inited;
  }
  v7 = *(unsigned __int16 *)propvarIn;
  v8 = v7 & 0xCFFF;
  v9 = v7 & 0xFFF;
  if ( (unsigned int)v9 > 0x1F )
  {
    if ( (unsigned int)(v9 - 64) > 9 )
    {
      LOBYTE(v10) = 32;
      if ( (_DWORD)v9 == 4095 )
        LOBYTE(v10) = 16;
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
  v11 = v10 & 0x1F;
  if ( v11 )
  {
    if ( (v7 & 0xFFFFF000) == 0x1000 )
    {
      if ( v8 == 31 )
      {
        v12 = *(_WORD **)(*((_QWORD *)propvarIn + 2) + 8 * v3);
        if ( v12 )
        {
          v13 = -1;
          while ( v12[++v13] != 0 )
            ;
          v15 = 2 * v13 + 2;
          v16 = CoTaskMemAlloc(v15);
          ppropvar[1] = v16;
          if ( v16 )
          {
            inited = 0;
            if ( v15 )
              memcpy_0(v16, v12, v15);
            *(_WORD *)ppropvar = 31;
            return inited;
          }
          inited = -2147024882;
        }
        *(_OWORD *)ppropvar = 0;
        ppropvar[2] = 0;
        return inited;
      }
      switch ( v7 & 0xCFFF )
      {
        case 2:
        case 3:
        case 4:
        case 5:
        case 7:
        case 0xB:
        case 0x10:
        case 0x11:
        case 0x12:
        case 0x13:
        case 0x14:
        case 0x15:
        case 0x40:
          *(_WORD *)ppropvar = v8;
          memcpy_0(ppropvar + 1, (const void *)(*((_QWORD *)propvarIn + 2) + (unsigned int)v3 * v11), v11);
          inited = 0;
          break;
        case 8:
          inited = InitPropVariantFromString(
                     *(const unsigned __int16 **)(*((_QWORD *)propvarIn + 2) + 8 * v3),
                     (struct tagPROPVARIANT *)ppropvar);
          break;
        case 0xC:
          inited = PropVariantCopy(ppropvar, (const PROPVARIANT *)(*((_QWORD *)propvarIn + 2) + 24 * v3));
          break;
        case 0x1E:
          memset(&pVar, 0, sizeof(pVar));
          pVar.vt = 30;
          pVar.llVal = *(_QWORD *)(*((_QWORD *)propvarIn + 2) + 8 * v3);
          inited = PropVariantChangeType(ppropvar, (const PROPVARIANT *const)&pVar, 0, 0x1Fu);
          break;
        case 0x48:
          inited = InitPropVariantFromCLSID((const IID *const)(*((_QWORD *)propvarIn + 2) + 16 * v3), ppropvar);
          break;
        default:
          return inited;
      }
    }
    else if ( (v7 & 0xF000) != 0 )
    {
      if ( (v7 & 0xF000) == 0x2000 )
      {
        memset(&pVar, 0, sizeof(pVar));
        inited = PropVariantToVariant(propvarIn, &pVar);
        if ( inited >= 0 )
        {
          memset(&pvar, 0, sizeof(pvar));
          inited = InitVariantFromVariantArrayElem(&pVar, v3, &pvar);
          if ( inited >= 0 )
          {
            inited = VariantToPropVariant(&pvar, ppropvar);
            if ( inited >= 0 && *(_WORD *)ppropvar == 8 )
            {
              v18 = *(_OWORD *)ppropvar;
              v22 = ppropvar[2];
              *(_OWORD *)propvarSrc = v18;
              inited = PropVariantChangeType(ppropvar, propvarSrc, 0, 0x1Fu);
              PropVariantClear(propvarSrc);
            }
            VariantClear(&pvar);
          }
          VariantClear(&pVar);
        }
      }
    }
    else if ( v8 == 8 || v8 == 30 )
    {
      return PropVariantChangeType(ppropvar, propvarIn, 0, 0x1Fu);
    }
    else
    {
      return PropVariantCopy(ppropvar, propvarIn);
    }
  }
  else if ( v8 <= 1 )
  {
    *(_WORD *)ppropvar = v8;
    return 0;
  }
  return inited;
}

```

## disassembly

```asm
0x18000b560  mov     [rsp+arg_18], rbx
0x18000b565  push    rsi
0x18000b566  push    rdi
0x18000b567  push    r14
0x18000b569  sub     rsp, 70h
0x18000b56d  mov     rax, cs:__security_cookie
0x18000b574  xor     rax, rsp
0x18000b577  mov     [rsp+88h+var_20], rax
0x18000b57c  xorps   xmm0, xmm0
0x18000b57f  mov     esi, edx
0x18000b581  xor     eax, eax
0x18000b583  mov     r14, r8
0x18000b586  movups  xmmword ptr [r8], xmm0
0x18000b58a  mov     [r8+10h], rax
0x18000b58e  mov     rbx, rcx
0x18000b591  mov     edi, 80070057h
0x18000b596  call    ?IsPropVariantValidForVista@@YAHAEBUtagPROPVARIANT@@@Z; IsPropVariantValidForVista(tagPROPVARIANT const &)
0x18000b59b  test    eax, eax
0x18000b59d  jz      def_18000B6CA; jumptable 000000018000B6CA default case, cases 6,9,10,13-15,22-29,31-63,65-71
0x18000b5a3  mov     rcx, rbx; propvar
0x18000b5a6  call    PropVariantGetElementCount
0x18000b5ab  cmp     esi, eax
0x18000b5ad  jnb     def_18000B6CA; jumptable 000000018000B6CA default case, cases 6,9,10,13-15,22-29,31-63,65-71
0x18000b5b3  movzx   r9d, word ptr [rbx]
0x18000b5b7  lea     r10, __ImageBase
0x18000b5be  mov     ecx, 0CFFFh
0x18000b5c3  movzx   eax, r9w
0x18000b5c7  and     ax, cx
0x18000b5ca  movzx   r8d, ax
0x18000b5ce  mov     ecx, r8d
0x18000b5d1  and     ecx, 0FFFh
0x18000b5d7  cmp     ecx, 1Fh
0x18000b5da  ja      loc_18000B695
0x18000b5e0  movzx   edx, ds:rva ?m_ucTypeSizesA@CRGTypeSizes@@0QBGB[r10+rcx*2]; ushort const near * const CRGTypeSizes::m_ucTypeSizesA ...
0x18000b5e9  and     edx, 1Fh
0x18000b5ec  jz      loc_18000B717
0x18000b5f2  mov     eax, r9d
0x18000b5f5  and     eax, 0FFFFF000h
0x18000b5fa  cmp     eax, 1000h
0x18000b5ff  jnz     loc_18000B72C
0x18000b605  cmp     r8d, 1Fh
0x18000b609  jnz     loc_18000B6AB
0x18000b60f  mov     rax, [rbx+10h]
0x18000b613  mov     rbx, [rax+rsi*8]
0x18000b617  test    rbx, rbx
0x18000b61a  jz      loc_18000B6EC
0x18000b620  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000b627  nop     word ptr [rax+rax+00000000h]
0x18000b630  cmp     word ptr [rbx+rax*2+2], 0
0x18000b636  lea     rax, [rax+1]
0x18000b63a  jnz     short loc_18000B630
0x18000b63c  lea     rsi, ds:2[rax*2]
0x18000b644  mov     rcx, rsi; cb
0x18000b647  call    cs:__imp_CoTaskMemAlloc
0x18000b64d  mov     [r14+8], rax
0x18000b651  test    rax, rax
0x18000b654  jz      loc_18000B6E7
0x18000b65a  xor     edi, edi
0x18000b65c  test    rsi, rsi
0x18000b65f  jz      short loc_18000B66F
0x18000b661  mov     r8, rsi; Size
0x18000b664  mov     rdx, rbx; Src
0x18000b667  mov     rcx, rax; void *
0x18000b66a  call    memcpy_0
0x18000b66f  mov     word ptr [r14], 1Fh
0x18000b675  mov     eax, edi; jumptable 000000018000B6CA default case, cases 6,9,10,13-15,22-29,31-63,65-71
0x18000b677  mov     rcx, [rsp+88h+var_20]
0x18000b67c  xor     rcx, rsp; StackCookie
0x18000b67f  call    __security_check_cookie
0x18000b684  mov     rbx, [rsp+88h+arg_18]
0x18000b68c  add     rsp, 70h
0x18000b690  pop     r14
0x18000b692  pop     rdi
0x18000b693  pop     rsi
0x18000b694  retn
0x18000b695  lea     eax, [rcx-40h]
0x18000b698  cmp     eax, 9
0x18000b69b  ja      short loc_18000B6FE
0x18000b69d  movzx   edx, word ptr ds:(rva aAggregateprope+8)[r10+rcx*2]; "egatePropertyProvider" ...
0x18000b6a6  jmp     loc_18000B5E9
0x18000b6ab  lea     eax, [r8-2]; switch 71 cases
0x18000b6af  cmp     eax, 46h
0x18000b6b2  ja      short def_18000B6CA; jumptable 000000018000B6CA default case, cases 6,9,10,13-15,22-29,31-63,65-71
0x18000b6b4  cdqe
0x18000b6b6  movzx   eax, ds:(byte_18000B8DC - 180000000h)[r10+rax]
0x18000b6bf  mov     ecx, ds:(jpt_18000B6CA - 180000000h)[r10+rax*4]
0x18000b6c7  add     rcx, r10
0x18000b6ca  jmp     rcx; switch jump
0x18000b6cc  mov     [r14], r8w; jumptable 000000018000B6CA cases 2-5,7,11,16-21,64
0x18000b6d0  lea     rcx, [r14+8]; void *
0x18000b6d4  mov     r8d, edx; Size
0x18000b6d7  imul    edx, esi
0x18000b6da  add     rdx, [rbx+10h]; Src
0x18000b6de  call    memcpy_0
0x18000b6e3  xor     edi, edi
0x18000b6e5  jmp     short def_18000B6CA; jumptable 000000018000B6CA default case, cases 6,9,10,13-15,22-29,31-63,65-71
0x18000b6e7  mov     edi, 8007000Eh
0x18000b6ec  xorps   xmm0, xmm0
0x18000b6ef  xor     eax, eax
0x18000b6f1  movups  xmmword ptr [r14], xmm0
0x18000b6f5  mov     [r14+10h], rax
0x18000b6f9  jmp     def_18000B6CA; jumptable 000000018000B6CA default case, cases 6,9,10,13-15,22-29,31-63,65-71
0x18000b6fe  cmp     ecx, 0FFFh
0x18000b704  mov     eax, 1010h
0x18000b709  mov     edx, 20h ; ' '
0x18000b70e  cmovz   dx, ax
0x18000b712  jmp     loc_18000B5E9
0x18000b717  cmp     r8d, 1
0x18000b71b  ja      def_18000B6CA; jumptable 000000018000B6CA default case, cases 6,9,10,13-15,22-29,31-63,65-71
0x18000b721  mov     [r14], r8w
0x18000b725  xor     edi, edi
0x18000b727  jmp     def_18000B6CA; jumptable 000000018000B6CA default case, cases 6,9,10,13-15,22-29,31-63,65-71
0x18000b72c  test    eax, eax
0x18000b72e  jz      loc_18000B7F8
0x18000b734  cmp     eax, 2000h
0x18000b739  jnz     def_18000B6CA; jumptable 000000018000B6CA default case, cases 6,9,10,13-15,22-29,31-63,65-71
0x18000b73f  xorps   xmm0, xmm0
0x18000b742  lea     rdx, [rsp+88h+pVar]; pVar
0x18000b747  xor     eax, eax
0x18000b749  mov     rcx, rbx; pPropVar
0x18000b74c  movups  xmmword ptr [rsp+88h+pVar], xmm0
0x18000b751  mov     qword ptr [rsp+88h+pVar+10h], rax
0x18000b756  call    PropVariantToVariant
0x18000b75b  mov     edi, eax
0x18000b75d  test    eax, eax
0x18000b75f  js      def_18000B6CA; jumptable 000000018000B6CA default case, cases 6,9,10,13-15,22-29,31-63,65-71
0x18000b765  xorps   xmm0, xmm0
0x18000b768  lea     r8, [rsp+88h+pvar]; pvar
0x18000b76d  xor     eax, eax
0x18000b76f  lea     rcx, [rsp+88h+pVar]; varIn
0x18000b774  mov     edx, esi; iElem
0x18000b776  mov     qword ptr [rsp+88h+pvar+10h], rax
0x18000b77b  movups  xmmword ptr [rsp+88h+pvar], xmm0
0x18000b780  call    InitVariantFromVariantArrayElem
0x18000b785  mov     edi, eax
0x18000b787  test    eax, eax
0x18000b789  js      short loc_18000B7E8
0x18000b78b  mov     rdx, r14; pPropVar
0x18000b78e  lea     rcx, [rsp+88h+pvar]; pVar
0x18000b793  call    VariantToPropVariant
0x18000b798  mov     edi, eax
0x18000b79a  test    eax, eax
0x18000b79c  js      short loc_18000B7DD
0x18000b79e  cmp     word ptr [r14], 8
0x18000b7a3  jnz     short loc_18000B7DD
0x18000b7a5  movups  xmm0, xmmword ptr [r14]
0x18000b7a9  lea     rdx, [rsp+88h+propvarSrc]; propvarSrc
0x18000b7ae  mov     r9d, 1Fh; vt
0x18000b7b4  movsd   xmm1, qword ptr [r14+10h]
0x18000b7ba  xor     r8d, r8d; flags
0x18000b7bd  mov     rcx, r14; ppropvarDest
0x18000b7c0  movsd   [rsp+88h+var_28], xmm1
0x18000b7c6  movups  xmmword ptr [rsp+88h+propvarSrc], xmm0
0x18000b7cb  call    PropVariantChangeType
0x18000b7d0  lea     rcx, [rsp+88h+propvarSrc]; pvar
0x18000b7d5  mov     edi, eax
0x18000b7d7  call    cs:__imp_PropVariantClear
0x18000b7dd  lea     rcx, [rsp+88h+pvar]; pvarg
0x18000b7e2  call    cs:__imp_VariantClear
0x18000b7e8  lea     rcx, [rsp+88h+pVar]; pvarg
0x18000b7ed  call    cs:__imp_VariantClear
0x18000b7f3  jmp     def_18000B6CA; jumptable 000000018000B6CA default case, cases 6,9,10,13-15,22-29,31-63,65-71
0x18000b7f8  cmp     r8d, 8
0x18000b7fc  jz      short loc_18000B817
0x18000b7fe  cmp     r8d, 1Eh
0x18000b802  jz      short loc_18000B817
0x18000b804  mov     rdx, rbx; pvarSrc
0x18000b807  mov     rcx, r14; pvarDest
0x18000b80a  call    cs:__imp_PropVariantCopy
0x18000b810  mov     edi, eax
0x18000b812  jmp     def_18000B6CA; jumptable 000000018000B6CA default case, cases 6,9,10,13-15,22-29,31-63,65-71
0x18000b817  mov     r9d, 1Fh; vt
0x18000b81d  xor     r8d, r8d; flags
0x18000b820  mov     rdx, rbx; propvarSrc
0x18000b823  mov     rcx, r14; ppropvarDest
0x18000b826  call    PropVariantChangeType
0x18000b82b  mov     edi, eax
0x18000b82d  jmp     def_18000B6CA; jumptable 000000018000B6CA default case, cases 6,9,10,13-15,22-29,31-63,65-71
0x18000b832  mov     rcx, rsi; jumptable 000000018000B6CA case 72
0x18000b835  mov     rdx, r14; ppropvar
0x18000b838  shl     rcx, 4
0x18000b83c  add     rcx, [rbx+10h]; clsid
0x18000b840  call    InitPropVariantFromCLSID
0x18000b845  mov     edi, eax
0x18000b847  jmp     def_18000B6CA; jumptable 000000018000B6CA default case, cases 6,9,10,13-15,22-29,31-63,65-71
0x18000b84c  mov     rcx, [rbx+10h]; jumptable 000000018000B6CA case 8
0x18000b850  mov     rdx, r14; struct tagPROPVARIANT *
0x18000b853  mov     rcx, [rcx+rsi*8]; Src
0x18000b857  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x18000b85c  mov     edi, eax
0x18000b85e  jmp     def_18000B6CA; jumptable 000000018000B6CA default case, cases 6,9,10,13-15,22-29,31-63,65-71
0x18000b863  xor     eax, eax; jumptable 000000018000B6CA case 30
0x18000b865  lea     rdx, [rsp+88h+pVar]; propvarSrc
0x18000b86a  mov     qword ptr [rsp+88h+pVar+10h], rax
0x18000b86f  xorps   xmm0, xmm0
0x18000b872  movups  xmmword ptr [rsp+88h+pVar], xmm0
0x18000b877  mov     eax, 1Eh
0x18000b87c  mov     r9d, 1Fh; vt
0x18000b882  mov     word ptr [rsp+88h+pVar], ax
0x18000b887  xor     r8d, r8d; flags
0x18000b88a  mov     rax, [rbx+10h]
0x18000b88e  mov     rcx, [rax+rsi*8]
0x18000b892  mov     qword ptr [rsp+88h+pVar+8], rcx
0x18000b897  mov     rcx, r14; ppropvarDest
0x18000b89a  call    PropVariantChangeType
0x18000b89f  mov     edi, eax
0x18000b8a1  jmp     def_18000B6CA; jumptable 000000018000B6CA default case, cases 6,9,10,13-15,22-29,31-63,65-71
0x18000b8a6  mov     rax, [rbx+10h]; jumptable 000000018000B6CA case 12
0x18000b8aa  lea     rcx, [rsi+rsi*2]
0x18000b8ae  lea     rdx, [rax+rcx*8]; pvarSrc
0x18000b8b2  mov     rcx, r14; pvarDest
0x18000b8b5  call    cs:__imp_PropVariantCopy
0x18000b8bb  mov     edi, eax
0x18000b8bd  jmp     def_18000B6CA; jumptable 000000018000B6CA default case, cases 6,9,10,13-15,22-29,31-63,65-71
```
