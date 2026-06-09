# EnumInfo_Copy(PSFORMAT_ENUMINFO *,PSFORMAT_ENUMINFO const *)

- ea: `0x18002c7b0`
- end: `0x18002cd1d`
- name: `?EnumInfo_Copy@@YAJPEAUPSFORMAT_ENUMINFO@@PEBU1@@Z`
- size: `1389`
- prototype: `__int64 __fastcall(struct PSFORMAT_ENUMINFO *, const struct PSFORMAT_ENUMINFO *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002ae10`
- `0x18002c28c`

## callees

- `0x18002c7b0`
- `0x18002cd24`
- `0x18006fb98`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002c910`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002c929`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002ca5f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002c910`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002c929`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002ca5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c845`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c98d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ca80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002cb9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c845`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c98d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ca80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002cb9a`

## pseudocode

```c
__int64 __fastcall EnumInfo_Copy(struct PSFORMAT_ENUMINFO *a1, const struct PSFORMAT_ENUMINFO *a2)
{
  _WORD *v3; // rsi
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // r14
  HRESULT v9; // ebp
  _WORD *v10; // r10
  unsigned __int64 v11; // rdx
  _WORD *v12; // r8
  __int64 v13; // rcx
  __int64 v14; // r9
  _WORD *v15; // rcx
  __int64 v16; // r14
  bool v17; // cf
  const PROPVARIANT *v18; // rdx
  PROPVARIANT *v19; // rcx
  _WORD *v20; // rsi
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // r14
  _WORD *v23; // rax
  unsigned __int64 v24; // rdx
  _WORD *v25; // r8
  __int64 v26; // rcx
  __int64 v27; // r9
  _WORD *v28; // rcx
  __int64 v29; // r14
  _WORD *v30; // rax
  unsigned __int64 v31; // rdx
  _WORD *v32; // r8
  __int64 v33; // rcx
  _WORD *v34; // rbx
  __int64 v35; // r9
  _WORD *v36; // rcx
  __int64 v37; // rsi
  unsigned __int64 v38; // rsi
  _WORD *v39; // rax
  unsigned __int64 v40; // rdx
  _WORD *v41; // r8
  __int64 v42; // rcx
  _WORD *v43; // rsi
  unsigned __int64 v44; // rbx
  __int64 v45; // r9
  _WORD *v46; // rcx
  __int64 v47; // r14
  unsigned __int64 v48; // r14

  *(_DWORD *)a1 = *(_DWORD *)a2;
  v3 = (_WORD *)*((_QWORD *)a2 + 11);
  v5 = -1;
  if ( !v3 )
    goto LABEL_27;
  v6 = -1;
  do
    ++v6;
  while ( v3[v6] );
  v7 = v6 + 1;
  *((_QWORD *)a1 + 11) = 0;
  if ( v6 + 1 < v6 || !is_mul_ok(v7, 2u) )
    return 2147942934LL;
  v10 = CoTaskMemAlloc(2 * v7);
  *((_QWORD *)a1 + 11) = v10;
  if ( v10 )
  {
    if ( v7 <= 0x7FFFFFFF )
    {
      if ( v6 < 0x7FFFFFFF )
      {
        v11 = v6 + 1;
        v12 = v10;
        v13 = 0;
        do
        {
          if ( !v6 )
            break;
          if ( !*v3 )
            break;
          *v12++ = *v3++;
          --v6;
          ++v13;
          --v11;
        }
        while ( v11 );
        v14 = v13 - 1;
        if ( v11 )
          v14 = v13;
        v15 = v12 - 1;
        if ( v11 )
          v15 = v12;
        *v15 = 0;
        if ( v11 )
        {
          v17 = v7 == v14;
          v16 = v7 - v14;
          if ( !v17 && v16 != 1 && (unsigned __int64)(2 * v16) > 2 )
            memset_0(&v10[v14 + 1], 0, 2 * v16 - 2);
        }
LABEL_27:
        if ( !*(_DWORD *)a2 || *(_DWORD *)a2 == 3 )
        {
          v9 = PropVariantCopy((PROPVARIANT *)a1 + 1, (const PROPVARIANT *)a2 + 1);
          if ( v9 >= 0 )
          {
            v18 = (const PROPVARIANT *)((char *)a2 + 32);
            v19 = (PROPVARIANT *)((char *)a1 + 32);
            goto LABEL_30;
          }
        }
        else
        {
          v9 = PropVariantCopy((PROPVARIANT *)a1 + 4, (const PROPVARIANT *)a2 + 4);
          if ( v9 >= 0 )
          {
            v18 = (const PROPVARIANT *)((char *)a2 + 56);
            v19 = (PROPVARIANT *)((char *)a1 + 56);
LABEL_30:
            v9 = PropVariantCopy(v19, v18);
            if ( v9 >= 0 )
            {
              v20 = (_WORD *)*((_QWORD *)a2 + 10);
              if ( !v20 )
                goto LABEL_97;
              v21 = -1;
              do
                ++v21;
              while ( v20[v21] );
              v22 = v21 + 1;
              *((_QWORD *)a1 + 10) = 0;
              if ( v21 + 1 >= v21 && is_mul_ok(v22, 2u) )
              {
                v23 = CoTaskMemAlloc(2 * v22);
                v9 = 0;
                *((_QWORD *)a1 + 10) = v23;
                if ( v23 )
                {
                  if ( v22 > 0x7FFFFFFF )
                  {
                    *v23 = 0;
                  }
                  else if ( v21 >= 0x7FFFFFFF )
                  {
                    if ( v21 != -1 )
                      *v23 = 0;
                  }
                  else
                  {
                    v24 = v21 + 1;
                    v25 = v23;
                    v26 = 0;
                    do
                    {
                      if ( !v21 )
                        break;
                      if ( !*v20 )
                        break;
                      *v25++ = *v20++;
                      --v21;
                      ++v26;
                      --v24;
                    }
                    while ( v24 );
                    v27 = v26 - 1;
                    if ( v24 )
                      v27 = v26;
                    v28 = v25 - 1;
                    if ( v24 )
                      v28 = v25;
                    *v28 = 0;
                    if ( v24 )
                    {
                      v17 = v22 == v27;
                      v29 = v22 - v27;
                      if ( !v17 && v29 != 1 && (unsigned __int64)(2 * v29) > 2 )
                        memset_0(&v23[v27 + 1], 0, 2 * v29 - 2);
                    }
                  }
                }
                else
                {
                  v9 = -2147024882;
                }
              }
              else
              {
                v9 = -2147024362;
              }
              if ( v9 >= 0 )
              {
LABEL_97:
                v43 = (_WORD *)*((_QWORD *)a2 + 12);
                if ( !v43 )
                  goto LABEL_72;
                v44 = -1;
                do
                  ++v44;
                while ( v43[v44] );
                v48 = v44 + 1;
                *((_QWORD *)a1 + 12) = 0;
                if ( v44 + 1 >= v44 && is_mul_ok(v48, 2u) )
                {
                  v39 = CoTaskMemAlloc(2 * v48);
                  v9 = 0;
                  *((_QWORD *)a1 + 12) = v39;
                  if ( v39 )
                  {
                    if ( v48 > 0x7FFFFFFF )
                    {
                      *v39 = 0;
                    }
                    else if ( v44 >= 0x7FFFFFFF )
                    {
                      if ( v44 != -1 )
                        *v39 = 0;
                    }
                    else
                    {
                      v40 = v44 + 1;
                      v41 = v39;
                      v42 = 0;
                      do
                      {
                        if ( !v44 )
                          break;
                        if ( !*v43 )
                          break;
                        *v41++ = *v43++;
                        --v44;
                        ++v42;
                        --v40;
                      }
                      while ( v40 );
                      v45 = v42 - 1;
                      if ( v40 )
                        v45 = v42;
                      v46 = v41 - 1;
                      if ( v40 )
                        v46 = v41;
                      *v46 = 0;
                      if ( v40 )
                      {
                        v17 = v48 == v45;
                        v47 = v48 - v45;
                        if ( !v17 && v47 != 1 && (unsigned __int64)(2 * v47) > 2 )
                          memset_0(&v39[v45 + 1], 0, 2 * v47 - 2);
                      }
                    }
                  }
                  else
                  {
                    v9 = -2147024882;
                  }
                }
                else
                {
                  v9 = -2147024362;
                }
                if ( v9 >= 0 )
                {
LABEL_72:
                  v34 = (_WORD *)*((_QWORD *)a2 + 13);
                  if ( !v34 )
                    return (unsigned int)v9;
                  do
                    ++v5;
                  while ( v34[v5] );
                  v38 = v5 + 1;
                  *((_QWORD *)a1 + 13) = 0;
                  if ( v5 + 1 >= v5 && is_mul_ok(v38, 2u) )
                  {
                    v30 = CoTaskMemAlloc(2 * v38);
                    v9 = 0;
                    *((_QWORD *)a1 + 13) = v30;
                    if ( v30 )
                    {
                      if ( v38 > 0x7FFFFFFF )
                      {
                        *v30 = 0;
                      }
                      else if ( v5 >= 0x7FFFFFFF )
                      {
                        if ( v5 != -1 )
                          *v30 = 0;
                      }
                      else
                      {
                        v31 = v5 + 1;
                        v32 = v30;
                        v33 = 0;
                        do
                        {
                          if ( !v5 )
                            break;
                          if ( !*v34 )
                            break;
                          *v32++ = *v34++;
                          --v5;
                          ++v33;
                          --v31;
                        }
                        while ( v31 );
                        v35 = v33 - 1;
                        if ( v31 )
                          v35 = v33;
                        v36 = v32 - 1;
                        if ( v31 )
                          v36 = v32;
                        *v36 = 0;
                        if ( v31 )
                        {
                          v17 = v38 == v35;
                          v37 = v38 - v35;
                          if ( !v17 && v37 != 1 && (unsigned __int64)(2 * v37) > 2 )
                            memset_0(&v30[v35 + 1], 0, 2 * v37 - 2);
                        }
                      }
                    }
                    else
                    {
                      v9 = -2147024882;
                    }
                  }
                  else
                  {
                    v9 = -2147024362;
                  }
                  if ( v9 >= 0 )
                    return (unsigned int)v9;
                }
              }
            }
          }
        }
        EnumInfo_Clear(a1);
        return (unsigned int)v9;
      }
      if ( v6 == -1 )
        goto LABEL_27;
    }
    *v10 = 0;
    goto LABEL_27;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18002c7b0  push    rbx
0x18002c7b2  push    rbp
0x18002c7b3  push    rsi
0x18002c7b4  push    rdi
0x18002c7b5  push    r12
0x18002c7b7  push    r13
0x18002c7b9  push    r14
0x18002c7bb  push    r15
0x18002c7bd  sub     rsp, 28h
0x18002c7c1  mov     eax, [rdx]
0x18002c7c3  xor     ebp, ebp
0x18002c7c5  mov     [rcx], eax
0x18002c7c7  mov     r15, rdx
0x18002c7ca  mov     rsi, [rdx+58h]
0x18002c7ce  mov     r12, rcx
0x18002c7d1  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18002c7d8  mov     r13d, 8007000Eh
0x18002c7de  test    rsi, rsi
0x18002c7e1  jz      loc_18002C8FC
0x18002c7e7  mov     rbx, rdi
0x18002c7ea  nop     word ptr [rax+rax+00h]
0x18002c7f0  inc     rbx
0x18002c7f3  cmp     [rsi+rbx*2], bp
0x18002c7f7  jnz     short loc_18002C7F0
0x18002c7f9  lea     r14, [rbx+1]
0x18002c7fd  mov     [rcx+58h], rbp
0x18002c801  cmp     r14, rbx
0x18002c804  jnb     short loc_18002C835
0x18002c806  mov     eax, 80070216h
0x18002c80b  jmp     short loc_18002C824
0x18002c80d  mov     ebp, 80070216h
0x18002c812  test    ebp, ebp
0x18002c814  jns     loc_18002CC58
0x18002c81a  mov     rcx, r12; struct PSFORMAT_ENUMINFO *
0x18002c81d  call    ?EnumInfo_Clear@@YAXPEAUPSFORMAT_ENUMINFO@@@Z; EnumInfo_Clear(PSFORMAT_ENUMINFO *)
0x18002c822  mov     eax, ebp
0x18002c824  add     rsp, 28h
0x18002c828  pop     r15
0x18002c82a  pop     r14
0x18002c82c  pop     r13
0x18002c82e  pop     r12
0x18002c830  pop     rdi
0x18002c831  pop     rsi
0x18002c832  pop     rbp
0x18002c833  pop     rbx
0x18002c834  retn
0x18002c835  mov     eax, 2
0x18002c83a  mul     r14
0x18002c83d  test    rdx, rdx
0x18002c840  jnz     short loc_18002C806
0x18002c842  mov     rcx, rax; cb
0x18002c845  call    cs:__imp_CoTaskMemAlloc
0x18002c84b  mov     r10, rax
0x18002c84e  mov     [r12+58h], rax
0x18002c853  test    r10, r10
0x18002c856  mov     eax, ebp
0x18002c858  cmovz   eax, r13d
0x18002c85c  jz      loc_18002C8F4
0x18002c862  cmp     r14, 7FFFFFFFh
0x18002c869  ja      loc_18002CCB8
0x18002c86f  cmp     rbx, 7FFFFFFFh
0x18002c876  jnb     loc_18002CCAF
0x18002c87c  test    r14, r14
0x18002c87f  jz      short loc_18002C8FC
0x18002c881  mov     rdx, r14
0x18002c884  mov     r8, r10
0x18002c887  mov     rcx, rbp
0x18002c88a  nop     word ptr [rax+rax+00h]
0x18002c890  test    rbx, rbx
0x18002c893  jz      short loc_18002C8B5
0x18002c895  movzx   eax, word ptr [rsi]
0x18002c898  test    ax, ax
0x18002c89b  jz      short loc_18002C8B5
0x18002c89d  mov     [r8], ax
0x18002c8a1  add     rsi, 2
0x18002c8a5  add     r8, 2
0x18002c8a9  dec     rbx
0x18002c8ac  inc     rcx
0x18002c8af  sub     rdx, 1
0x18002c8b3  jnz     short loc_18002C890
0x18002c8b5  lea     r9, [rcx-1]
0x18002c8b9  test    rdx, rdx
0x18002c8bc  cmovnz  r9, rcx
0x18002c8c0  lea     rcx, [r8-2]
0x18002c8c4  cmovnz  rcx, r8
0x18002c8c8  mov     [rcx], bp
0x18002c8cb  jz      short loc_18002C8FC
0x18002c8cd  sub     r14, r9
0x18002c8d0  cmp     r14, 1
0x18002c8d4  jbe     short loc_18002C8FC
0x18002c8d6  lea     r8, [r14+r14]
0x18002c8da  cmp     r8, 2
0x18002c8de  jbe     short loc_18002C8FC
0x18002c8e0  inc     r9
0x18002c8e3  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18002c8e7  xor     edx, edx; Val
0x18002c8e9  lea     rcx, [r10+r9*2]; void *
0x18002c8ed  call    memset_0
0x18002c8f2  jmp     short loc_18002C8FC
0x18002c8f4  test    eax, eax
0x18002c8f6  js      loc_18002C824
0x18002c8fc  mov     eax, [r15]
0x18002c8ff  test    eax, eax
0x18002c901  jnz     loc_18002CA4D
0x18002c907  lea     rdx, [r15+8]; pvarSrc
0x18002c90b  lea     rcx, [r12+8]; pvarDest
0x18002c910  call    cs:__imp_PropVariantCopy
0x18002c916  mov     ebp, eax
0x18002c918  test    eax, eax
0x18002c91a  js      loc_18002C81A
0x18002c920  lea     rdx, [r15+20h]; pvarSrc
0x18002c924  lea     rcx, [r12+20h]; pvarDest
0x18002c929  call    cs:__imp_PropVariantCopy
0x18002c92f  mov     ebp, eax
0x18002c931  test    eax, eax
0x18002c933  js      loc_18002C81A
0x18002c939  mov     rsi, [r15+50h]
0x18002c93d  test    rsi, rsi
0x18002c940  jz      loc_18002CC58
0x18002c946  mov     rbx, rdi
0x18002c949  nop     dword ptr [rax+00000000h]
0x18002c950  inc     rbx
0x18002c953  cmp     word ptr [rsi+rbx*2], 0
0x18002c958  jnz     short loc_18002C950
0x18002c95a  lea     r14, [rbx+1]
0x18002c95e  mov     qword ptr [r12+50h], 0
0x18002c967  cmp     r14, rbx
0x18002c96a  jb      loc_18002C80D
0x18002c970  mov     eax, 2
0x18002c975  mov     [rsp+68h+arg_0], 0
0x18002c97e  mul     r14
0x18002c981  test    rdx, rdx
0x18002c984  jnz     loc_18002C80D
0x18002c98a  mov     rcx, rax; cb
0x18002c98d  call    cs:__imp_CoTaskMemAlloc
0x18002c993  xor     ebp, ebp
0x18002c995  mov     [r12+50h], rax
0x18002c99a  test    rax, rax
0x18002c99d  mov     r10, rax
0x18002c9a0  cmovz   ebp, r13d
0x18002c9a4  jz      loc_18002C812
0x18002c9aa  cmp     r14, 7FFFFFFFh
0x18002c9b1  ja      loc_18002CCC1
0x18002c9b7  cmp     rbx, 7FFFFFFFh
0x18002c9be  jnb     loc_18002CCCC
0x18002c9c4  test    r14, r14
0x18002c9c7  jz      loc_18002C812
0x18002c9cd  mov     rdx, r14
0x18002c9d0  mov     r8, rax
0x18002c9d3  xor     ecx, ecx
0x18002c9d5  test    rbx, rbx
0x18002c9d8  jz      short loc_18002C9FA
0x18002c9da  movzx   eax, word ptr [rsi]
0x18002c9dd  test    ax, ax
0x18002c9e0  jz      short loc_18002C9FA
0x18002c9e2  mov     [r8], ax
0x18002c9e6  add     rsi, 2
0x18002c9ea  add     r8, 2
0x18002c9ee  dec     rbx
0x18002c9f1  inc     rcx
0x18002c9f4  sub     rdx, 1
0x18002c9f8  jnz     short loc_18002C9D5
0x18002c9fa  test    rdx, rdx
0x18002c9fd  lea     r9, [rcx-1]
0x18002ca01  cmovnz  r9, rcx
0x18002ca05  lea     rcx, [r8-2]
0x18002ca09  cmovnz  rcx, r8
0x18002ca0d  xor     eax, eax
0x18002ca0f  mov     [rcx], ax
0x18002ca12  test    rdx, rdx
0x18002ca15  jz      loc_18002C812
0x18002ca1b  sub     r14, r9
0x18002ca1e  cmp     r14, 1
0x18002ca22  jbe     loc_18002C812
0x18002ca28  lea     r8, [r14+r14]
0x18002ca2c  cmp     r8, 2
0x18002ca30  jbe     loc_18002C812
0x18002ca36  inc     r9
0x18002ca39  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18002ca3d  xor     edx, edx; Val
0x18002ca3f  lea     rcx, [r10+r9*2]; void *
0x18002ca43  call    memset_0
0x18002ca48  jmp     loc_18002C812
0x18002ca4d  cmp     eax, 3
0x18002ca50  jz      loc_18002C907
0x18002ca56  lea     rdx, [r15+20h]; pvarSrc
0x18002ca5a  lea     rcx, [r12+20h]; pvarDest
0x18002ca5f  call    cs:__imp_PropVariantCopy
0x18002ca65  mov     ebp, eax
0x18002ca67  test    eax, eax
0x18002ca69  js      loc_18002C81A
0x18002ca6f  lea     rdx, [r15+38h]
0x18002ca73  lea     rcx, [r12+38h]
0x18002ca78  jmp     loc_18002C929
0x18002ca7d  mov     rcx, rax; cb
0x18002ca80  call    cs:__imp_CoTaskMemAlloc
0x18002ca86  xor     ebp, ebp
0x18002ca88  mov     [r12+68h], rax
0x18002ca8d  test    rax, rax
0x18002ca90  mov     r10, rax
0x18002ca93  cmovz   ebp, r13d
0x18002ca97  jz      loc_18002CB32
0x18002ca9d  cmp     rsi, 7FFFFFFFh
0x18002caa4  ja      loc_18002CCFF
0x18002caaa  cmp     rdi, 7FFFFFFFh
0x18002cab1  jnb     loc_18002CD09
0x18002cab7  test    rsi, rsi
0x18002caba  jz      short loc_18002CB32
0x18002cabc  mov     rdx, rsi
0x18002cabf  mov     r8, rax
0x18002cac2  xor     ecx, ecx
0x18002cac4  test    rdi, rdi
0x18002cac7  jz      short loc_18002CAE9
0x18002cac9  movzx   eax, word ptr [rbx]
0x18002cacc  test    ax, ax
0x18002cacf  jz      short loc_18002CAE9
0x18002cad1  mov     [r8], ax
0x18002cad5  add     rbx, 2
0x18002cad9  add     r8, 2
0x18002cadd  dec     rdi
0x18002cae0  inc     rcx
0x18002cae3  sub     rdx, 1
0x18002cae7  jnz     short loc_18002CAC4
0x18002cae9  test    rdx, rdx
0x18002caec  lea     r9, [rcx-1]
0x18002caf0  cmovnz  r9, rcx
0x18002caf4  lea     rcx, [r8-2]
0x18002caf8  cmovnz  rcx, r8
0x18002cafc  xor     eax, eax
0x18002cafe  mov     [rcx], ax
0x18002cb01  test    rdx, rdx
0x18002cb04  jz      short loc_18002CB32
0x18002cb06  sub     rsi, r9
0x18002cb09  cmp     rsi, 1
0x18002cb0d  jbe     short loc_18002CB32
0x18002cb0f  lea     r8, [rsi+rsi]
0x18002cb13  cmp     r8, 2
0x18002cb17  jbe     short loc_18002CB32
0x18002cb19  inc     r9
0x18002cb1c  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18002cb20  xor     edx, edx; Val
0x18002cb22  lea     rcx, [r10+r9*2]; void *
0x18002cb26  call    memset_0
0x18002cb2b  jmp     short loc_18002CB32
0x18002cb2d  mov     ebp, 80070216h
0x18002cb32  test    ebp, ebp
0x18002cb34  jns     loc_18002C822
0x18002cb3a  jmp     loc_18002C81A
0x18002cb3f  mov     ebp, 80070216h
0x18002cb44  test    ebp, ebp
0x18002cb46  js      loc_18002C81A
0x18002cb4c  mov     rbx, [r15+68h]
0x18002cb50  test    rbx, rbx
0x18002cb53  jz      loc_18002C822
0x18002cb59  nop     dword ptr [rax+00000000h]
0x18002cb60  inc     rdi
0x18002cb63  cmp     word ptr [rbx+rdi*2], 0
0x18002cb68  jnz     short loc_18002CB60
0x18002cb6a  lea     rsi, [rdi+1]
0x18002cb6e  mov     qword ptr [r12+68h], 0
0x18002cb77  cmp     rsi, rdi
0x18002cb7a  jb      short loc_18002CB2D
0x18002cb7c  mov     eax, 2
0x18002cb81  mov     [rsp+68h+arg_0], 0
0x18002cb8a  mul     rsi
0x18002cb8d  test    rdx, rdx
0x18002cb90  jnz     short loc_18002CB2D
0x18002cb92  jmp     loc_18002CA7D
0x18002cb97  mov     rcx, rax; cb
0x18002cb9a  call    cs:__imp_CoTaskMemAlloc
0x18002cba0  xor     ebp, ebp
0x18002cba2  mov     [r12+60h], rax
0x18002cba7  test    rax, rax
0x18002cbaa  mov     r10, rax
0x18002cbad  cmovz   ebp, r13d
0x18002cbb1  jz      short loc_18002CB44
0x18002cbb3  cmp     r14, 7FFFFFFFh
0x18002cbba  ja      loc_18002CCE0
0x18002cbc0  cmp     rbx, 7FFFFFFFh
0x18002cbc7  jnb     loc_18002CCEB
0x18002cbcd  test    r14, r14
0x18002cbd0  jz      loc_18002CB44
0x18002cbd6  mov     rdx, r14
0x18002cbd9  mov     r8, rax
0x18002cbdc  xor     ecx, ecx
0x18002cbde  xchg    ax, ax
0x18002cbe0  test    rbx, rbx
0x18002cbe3  jz      short loc_18002CC05
0x18002cbe5  movzx   eax, word ptr [rsi]
0x18002cbe8  test    ax, ax
0x18002cbeb  jz      short loc_18002CC05
0x18002cbed  mov     [r8], ax
0x18002cbf1  add     rsi, 2
0x18002cbf5  add     r8, 2
0x18002cbf9  dec     rbx
0x18002cbfc  inc     rcx
0x18002cbff  sub     rdx, 1
0x18002cc03  jnz     short loc_18002CBE0
0x18002cc05  test    rdx, rdx
0x18002cc08  lea     r9, [rcx-1]
  ... truncated ...
```
