# CAggregatePropertyProvider::_GetRange(_tagpropertykey const &,tagPROPVARIANT *,PROPVAR_COMPARE_UNIT)

- ea: `0x180075c08`
- end: `0x180075e49`
- name: `?_GetRange@CAggregatePropertyProvider@@AEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@W4PROPVAR_COMPARE_UNIT@@@Z`
- size: `577`
- prototype: `__int64 __fastcall(CAggregatePropertyProvider *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *, enum PROPVAR_COMPARE_UNIT)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180065820`

## callees

- `0x18000f050`
- `0x18002ab10`
- `0x180048760`
- `0x180048880`
- `0x18006ed20`
- `0x180075c08`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180075cca`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180075cca`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180075d2f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180075d68`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180075d8d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180075e19`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180075e23`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180075d2f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180075d68`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180075d8d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180075e19`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180075e23`

## pseudocode

```c
__int64 __fastcall CAggregatePropertyProvider::_GetRange(
        CAggregatePropertyProvider *this,
        const struct _tagpropertykey *a2,
        struct tagPROPVARIANT *a3,
        enum PROPVAR_COMPARE_UNIT a4)
{
  HRESULT v4; // ebx
  unsigned int v5; // esi
  int v6; // edi
  __int128 v10; // xmm0
  struct _DPA *v11; // rcx
  int v12; // eax
  PVOID Ptr; // rax
  BYTE *v14; // xmm1_8
  BYTE *v15; // xmm1_8
  void *v16; // rcx
  PROPVARIANT *v17; // r9
  int v18; // eax
  unsigned __int64 v20; // [rsp+20h] [rbp-60h] BYREF
  PROPVARIANT propvar1[2]; // [rsp+28h] [rbp-58h] BYREF
  void *v22; // [rsp+38h] [rbp-48h] BYREF
  PROPVARIANT pvarSrc[2]; // [rsp+40h] [rbp-40h] BYREF
  BYTE *v24; // [rsp+50h] [rbp-30h]
  PROPVARIANT pvarDest[2]; // [rsp+58h] [rbp-28h] BYREF
  void *v26; // [rsp+68h] [rbp-18h]

  v4 = 0;
  v24 = 0;
  v5 = 0;
  v26 = 0;
  *(_OWORD *)pvarDest = 0;
  v6 = 0;
  v10 = 0;
LABEL_2:
  *(_OWORD *)pvarSrc = v10;
  while ( 1 )
  {
    v11 = (struct _DPA *)*((_QWORD *)this + 13);
    v12 = v11 ? *(_DWORD *)v11 : 0;
    if ( v6 >= v12 )
      break;
    *(_OWORD *)propvar1 = 0;
    v22 = 0;
    Ptr = g_pfn_DPA_GetPtr(v11, v6);
    v4 = (*(__int64 (__fastcall **)(PVOID, const struct _tagpropertykey *, PROPVARIANT *))(*(_QWORD *)Ptr + 40LL))(
           Ptr,
           a2,
           propvar1);
    if ( v4 < 0 || !LOWORD(propvar1[0]) )
      goto LABEL_11;
    if ( v5 )
    {
      if ( PropVariantCompareEx(propvar1, pvarSrc, PVCU_DAY, 0) < 0 )
      {
        PropVariantClear(pvarSrc);
        ++v5;
        v10 = *(_OWORD *)propvar1;
        ++v6;
        v24 = (BYTE *)v22;
        goto LABEL_2;
      }
      if ( PropVariantCompareEx(propvar1, pvarDest, PVCU_DAY, 0) <= 0 )
      {
        PropVariantClear(propvar1);
      }
      else
      {
        PropVariantClear(pvarDest);
        ++v5;
        *(_OWORD *)pvarDest = *(_OWORD *)propvar1;
        v26 = v22;
      }
      ++v6;
    }
    else
    {
      v14 = (BYTE *)v22;
      *(_OWORD *)pvarSrc = *(_OWORD *)propvar1;
      v22 = 0;
      v24 = v14;
      *(_OWORD *)propvar1 = 0;
      v4 = PropVariantCopy(pvarDest, pvarSrc);
      v5 = 1;
LABEL_11:
      ++v6;
      if ( v4 < 0 )
        break;
    }
  }
  if ( v4 >= 0 )
  {
    if ( v5 > 1 )
    {
      v22 = 0;
      *(_OWORD *)propvar1 = 0;
      LOWORD(propvar1[0]) = LOWORD(pvarSrc[0]) | 0x1000;
      if ( LOWORD(pvarSrc[0]) == 64 )
      {
        v22 = 0;
        v20 = 0;
        v4 = ULongLongMult(2u, 8u, &v20);
        if ( v4 >= 0 )
        {
          v18 = CTCoAllocPolicy::Alloc(v16, 1u, v20, &v22);
          v17 = (PROPVARIANT *)v22;
          v4 = v18;
        }
        if ( v4 >= 0 )
        {
          *v17 = pvarSrc[1];
          v17[1] = pvarDest[1];
          LODWORD(propvar1[1]) = 2;
          *(_OWORD *)&a3->vt = *(_OWORD *)propvar1;
          a3->bstrblobVal.pData = (BYTE *)v17;
        }
      }
      else
      {
        v4 = -2147467259;
      }
    }
    else
    {
      v15 = v24;
      *(_OWORD *)&a3->vt = *(_OWORD *)pvarSrc;
      v24 = 0;
      a3->bstrblobVal.pData = v15;
      *(_OWORD *)pvarSrc = 0;
    }
  }
  PropVariantClear(pvarSrc);
  PropVariantClear(pvarDest);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180075c08  push    rbp
0x180075c0a  push    rbx
0x180075c0b  push    rsi
0x180075c0c  push    rdi
0x180075c0d  push    r12
0x180075c0f  push    r14
0x180075c11  push    r15
0x180075c13  mov     rbp, rsp
0x180075c16  sub     rsp, 80h
0x180075c1d  mov     rax, cs:__security_cookie
0x180075c24  xor     rax, rsp
0x180075c27  mov     [rbp+var_10], rax
0x180075c2b  xor     eax, eax
0x180075c2d  xor     ebx, ebx
0x180075c2f  xorps   xmm1, xmm1
0x180075c32  mov     [rbp+var_30], rax
0x180075c36  xor     esi, esi
0x180075c38  mov     [rbp+var_18], rax
0x180075c3c  movups  xmmword ptr [rbp+pvarDest], xmm1
0x180075c40  xor     edi, edi
0x180075c42  mov     r14, r8
0x180075c45  mov     r12, rdx
0x180075c48  mov     r15, rcx
0x180075c4b  xorps   xmm0, xmm0
0x180075c4e  movups  xmmword ptr [rbp+pvarSrc], xmm0
0x180075c52  mov     rcx, [r15+68h]; hdpa
0x180075c56  test    rcx, rcx
0x180075c59  jz      short loc_180075C5F
0x180075c5b  mov     eax, [rcx]
0x180075c5d  jmp     short loc_180075C61
0x180075c5f  xor     eax, eax
0x180075c61  cmp     edi, eax
0x180075c63  jge     short loc_180075CE1
0x180075c65  xorps   xmm0, xmm0
0x180075c68  movsxd  rdx, edi; i
0x180075c6b  xor     eax, eax
0x180075c6d  movups  xmmword ptr [rbp+propvar1], xmm0
0x180075c71  mov     [rbp+var_48], rax
0x180075c75  call    cs:g_pfn_DPA_GetPtr
0x180075c7b  lea     r8, [rbp+propvar1]
0x180075c7f  mov     rdx, r12
0x180075c82  mov     rcx, rax
0x180075c85  mov     rax, [rax]
0x180075c88  mov     rax, [rax+28h]
0x180075c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075c91  mov     ebx, eax
0x180075c93  test    eax, eax
0x180075c95  js      short loc_180075CD7
0x180075c97  xor     ecx, ecx
0x180075c99  cmp     cx, word ptr [rbp+propvar1]
0x180075c9d  jz      short loc_180075CD7
0x180075c9f  lea     rdx, [rbp+pvarSrc]; propvar2
0x180075ca3  test    esi, esi
0x180075ca5  jnz     short loc_180075D17
0x180075ca7  movups  xmm0, xmmword ptr [rbp+propvar1]
0x180075cab  lea     rcx, [rbp+pvarDest]; pvarDest
0x180075caf  xor     eax, eax
0x180075cb1  movsd   xmm1, [rbp+var_48]
0x180075cb6  movups  xmmword ptr [rbp+pvarSrc], xmm0
0x180075cba  mov     [rbp+var_48], rax
0x180075cbe  xorps   xmm0, xmm0
0x180075cc1  movsd   [rbp+var_30], xmm1
0x180075cc6  movups  xmmword ptr [rbp+propvar1], xmm0
0x180075cca  call    cs:__imp_PropVariantCopy
0x180075cd0  mov     ebx, eax
0x180075cd2  mov     esi, 1
0x180075cd7  inc     edi
0x180075cd9  test    ebx, ebx
0x180075cdb  jns     loc_180075C52
0x180075ce1  test    ebx, ebx
0x180075ce3  js      loc_180075E15
0x180075ce9  xor     eax, eax
0x180075ceb  cmp     esi, 1
0x180075cee  ja      loc_180075D95
0x180075cf4  movups  xmm0, xmmword ptr [rbp+pvarSrc]
0x180075cf8  movsd   xmm1, [rbp+var_30]
0x180075cfd  movups  xmmword ptr [r14], xmm0
0x180075d01  mov     [rbp+var_30], rax
0x180075d05  xorps   xmm0, xmm0
0x180075d08  movsd   qword ptr [r14+10h], xmm1
0x180075d0e  movups  xmmword ptr [rbp+pvarSrc], xmm0
0x180075d12  jmp     loc_180075E15
0x180075d17  xor     r9d, r9d; flags
0x180075d1a  lea     rcx, [rbp+propvar1]; propvar1
0x180075d1e  lea     r8d, [r9+4]; unit
0x180075d22  call    PropVariantCompareEx
0x180075d27  test    eax, eax
0x180075d29  jns     short loc_180075D4C
0x180075d2b  lea     rcx, [rbp+pvarSrc]; pvar
0x180075d2f  call    cs:__imp_PropVariantClear
0x180075d35  movsd   xmm1, [rbp+var_48]
0x180075d3a  inc     esi
0x180075d3c  movups  xmm0, xmmword ptr [rbp+propvar1]
0x180075d40  inc     edi
0x180075d42  movsd   [rbp+var_30], xmm1
0x180075d47  jmp     loc_180075C4E
0x180075d4c  xor     r9d, r9d; flags
0x180075d4f  lea     rdx, [rbp+pvarDest]; propvar2
0x180075d53  lea     rcx, [rbp+propvar1]; propvar1
0x180075d57  lea     r8d, [r9+4]; unit
0x180075d5b  call    PropVariantCompareEx
0x180075d60  test    eax, eax
0x180075d62  jle     short loc_180075D89
0x180075d64  lea     rcx, [rbp+pvarDest]; pvar
0x180075d68  call    cs:__imp_PropVariantClear
0x180075d6e  movups  xmm0, xmmword ptr [rbp+propvar1]
0x180075d72  inc     esi
0x180075d74  movsd   xmm1, [rbp+var_48]
0x180075d79  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180075d7d  movsd   [rbp+var_18], xmm1
0x180075d82  inc     edi
0x180075d84  jmp     loc_180075C52
0x180075d89  lea     rcx, [rbp+propvar1]; pvar
0x180075d8d  call    cs:__imp_PropVariantClear
0x180075d93  jmp     short loc_180075D82
0x180075d95  mov     [rbp+var_48], rax
0x180075d99  xorps   xmm0, xmm0
0x180075d9c  movzx   eax, word ptr [rbp+pvarSrc]
0x180075da0  or      ax, 1000h
0x180075da4  cmp     word ptr [rbp+pvarSrc], 40h ; '@'
0x180075da9  movups  xmmword ptr [rbp+propvar1], xmm0
0x180075dad  mov     word ptr [rbp+propvar1], ax
0x180075db1  jz      short loc_180075DBA
0x180075db3  mov     ebx, 80004005h
0x180075db8  jmp     short loc_180075E15
0x180075dba  xor     r9d, r9d
0x180075dbd  lea     r8, [rbp+var_60]; unsigned __int64 *
0x180075dc1  mov     [rbp+var_48], r9
0x180075dc5  mov     [rbp+var_60], r9
0x180075dc9  lea     edx, [r9+8]; unsigned __int64
0x180075dcd  lea     edi, [rdx-6]
0x180075dd0  mov     ecx, edi; unsigned __int64
0x180075dd2  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180075dd7  mov     ebx, eax
0x180075dd9  test    eax, eax
0x180075ddb  js      short loc_180075DF3
0x180075ddd  mov     r8, [rbp+var_60]; unsigned __int64
0x180075de1  lea     r9, [rbp+var_48]; void **
0x180075de5  lea     edx, [rdi-1]; unsigned int
0x180075de8  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180075ded  mov     r9, [rbp+var_48]
0x180075df1  mov     ebx, eax
0x180075df3  test    ebx, ebx
0x180075df5  js      short loc_180075E15
0x180075df7  mov     rax, [rbp+pvarSrc+8]
0x180075dfb  mov     [r9], rax
0x180075dfe  mov     rax, [rbp+pvarDest+8]
0x180075e02  mov     [r9+8], rax
0x180075e06  mov     dword ptr [rbp+propvar1+8], edi
0x180075e09  movups  xmm0, xmmword ptr [rbp+propvar1]
0x180075e0d  movups  xmmword ptr [r14], xmm0
0x180075e11  mov     [r14+10h], r9
0x180075e15  lea     rcx, [rbp+pvarSrc]; pvar
0x180075e19  call    cs:__imp_PropVariantClear
0x180075e1f  lea     rcx, [rbp+pvarDest]; pvar
0x180075e23  call    cs:__imp_PropVariantClear
0x180075e29  mov     eax, ebx
0x180075e2b  mov     rcx, [rbp+var_10]
0x180075e2f  xor     rcx, rsp; StackCookie
0x180075e32  call    __security_check_cookie
0x180075e37  add     rsp, 80h
0x180075e3e  pop     r15
0x180075e40  pop     r14
0x180075e42  pop     r12
0x180075e44  pop     rdi
0x180075e45  pop     rsi
0x180075e46  pop     rbx
0x180075e47  pop     rbp
0x180075e48  retn
```
