# CreateBucket(ushort const *,RULE_CATEGORY,ushort const *,ushort const *,ushort const *,RULE_TYPE,_RULE_BUCKET * *)

- ea: `0x14000b144`
- end: `0x14000b7d4`
- name: `?CreateBucket@@YAJPEBGW4RULE_CATEGORY@@000W4RULE_TYPE@@PEAPEAU_RULE_BUCKET@@@Z`
- size: `1680`
- prototype: `__int64 __fastcall(_WORD *, int, _WORD *, void *, void *, int, HCRYPTHASH *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x14000a854`
- `0x14000b088`

## callees

- `0x140001c50`
- `0x140001c74`
- `0x140001cb8`
- `0x140001d20`
- `0x1400027c6`
- `0x1400027d2`
- `0x140002d90`
- `0x140002fb8`
- `0x140004f34`
- `0x14000b144`
- `0x14000d010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000b679`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000b679`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x14000b410`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x14000b4f9`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x14000b5dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b2ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b2ae`
- `CRYPTSP!CryptDestroyHash` at `0x14000b31d`
- `CRYPTSP!CryptDestroyHash` at `0x14000b31d`
- `CRYPTSP!CryptGetHashParam` at `0x14000b302`
- `CRYPTSP!CryptGetHashParam` at `0x14000b302`
- `CRYPTSP!CryptHashData` at `0x14000b2e0`
- `CRYPTSP!CryptHashData` at `0x14000b2e0`
- `CRYPTSP!CryptCreateHash` at `0x14000b2a4`
- `CRYPTSP!CryptCreateHash` at `0x14000b2a4`

## pseudocode

```c
__int64 __fastcall CreateBucket(_WORD *a1, int a2, _WORD *a3, void *a4, void *a5, int a6, HCRYPTHASH *a7)
{
  _WORD *v7; // r14
  unsigned int v10; // r13d
  void *v11; // rax
  HCRYPTHASH v12; // rsi
  char **v13; // rax
  __int64 v14; // r8
  signed int v15; // ebx
  unsigned __int64 v16; // rdx
  char *v17; // r14
  __int64 v18; // rbx
  signed int LastError; // eax
  __int64 v20; // r8
  char **v21; // rax
  __int64 v22; // r8
  unsigned __int64 v23; // r13
  unsigned __int64 v24; // rdx
  char *v25; // r14
  __int64 v26; // rbx
  unsigned __int16 *v27; // r14
  unsigned __int16 *v28; // r15
  unsigned __int16 *v29; // rcx
  unsigned __int16 *v30; // rbx
  char **v31; // rax
  __int64 v32; // r8
  unsigned __int64 v33; // rdx
  void *v34; // rcx
  char *v35; // r14
  __int64 v36; // rbx
  unsigned __int16 *v37; // r14
  unsigned __int16 *v38; // r15
  unsigned __int16 *v39; // rcx
  unsigned __int16 *v40; // rbx
  char **v41; // rax
  __int64 v42; // r8
  void *v43; // rcx
  char *v44; // r14
  unsigned __int16 *v45; // r14
  unsigned __int16 *v46; // r15
  unsigned __int16 *v47; // rcx
  unsigned __int16 *v48; // rbx
  _QWORD *v49; // rax
  _QWORD *v50; // rbx
  _QWORD *v51; // rax
  _QWORD *v52; // rbx
  __int64 v53; // r14
  _QWORD *v54; // rax
  _QWORD *v55; // rcx
  void *v56; // r14
  void *v57; // r14
  void *v58; // r14
  void *v59; // r14
  void **v60; // r14
  _QWORD *v61; // r15
  void *v62; // rcx
  HCRYPTHASH hHash; // [rsp+30h] [rbp-98h] BYREF
  DWORD pdwDataLen; // [rsp+38h] [rbp-90h] BYREF
  void *Src; // [rsp+40h] [rbp-88h]
  void *v67; // [rsp+48h] [rbp-80h]
  void *v68; // [rsp+50h] [rbp-78h]
  __int64 v69; // [rsp+58h] [rbp-70h]
  HCRYPTHASH *v70; // [rsp+60h] [rbp-68h]
  BYTE pbData[32]; // [rsp+68h] [rbp-60h] BYREF

  v67 = a4;
  v7 = a3;
  Src = a3;
  v68 = a5;
  v70 = a7;
  v10 = 0;
  v11 = operator new(0x60u, (const struct std::nothrow_t *)std::nothrow);
  v12 = (HCRYPTHASH)v11;
  if ( !v11 )
  {
    v15 = -2147024882;
    goto LABEL_115;
  }
  memset_0(v11, 0, 0x60u);
  memset_0((void *)v12, 0, 0x60u);
  *(_DWORD *)(v12 + 72) = a2;
  if ( a2 == 2 )
    *(_DWORD *)(v12 + 76) = 1;
  v13 = (char **)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  if ( v13 )
  {
    *(_OWORD *)v13 = 0;
    v13[2] = 0;
    v13[3] = (char *)7;
    *(_WORD *)v13 = 0;
  }
  else
  {
    v13 = 0;
  }
  *(_QWORD *)(v12 + 32) = v13;
  if ( !v13 )
    goto LABEL_8;
  v16 = -1;
  do
    ++v16;
  while ( a1[v16] );
  if ( v16 > (unsigned __int64)v13[3] )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v13, v16, v14, a1);
  }
  else
  {
    if ( (unsigned __int64)v13[3] <= 7 )
      v17 = (char *)v13;
    else
      v17 = *v13;
    v13[2] = (char *)v16;
    v18 = 2 * v16;
    memmove_0(v17, a1, 2 * v16);
    *(_WORD *)&v17[v18] = 0;
    v7 = Src;
  }
  hHash = 0;
  pdwDataLen = 32;
  if ( !CryptCreateHash(hProv, 0x800Cu, 0, 0, &hHash) )
    goto LABEL_18;
  v20 = -1;
  do
    ++v20;
  while ( a1[v20] );
  if ( CryptHashData(hHash, (const BYTE *)a1, 2 * v20, 0) && CryptGetHashParam(hHash, 2u, pbData, &pdwDataLen, 0) )
  {
    v15 = 0;
    v10 = *(_DWORD *)pbData;
  }
  else
  {
LABEL_18:
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( hHash )
    CryptDestroyHash(hHash);
  if ( v15 < 0 )
    goto LABEL_101;
  *(_QWORD *)(v12 + 88) = 1LL << ((unsigned __int8)(v10 % 0x18) + 12);
  if ( v7 )
  {
    v21 = (char **)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
    if ( v21 )
    {
      *(_OWORD *)v21 = 0;
      v21[2] = 0;
      v21[3] = (char *)7;
      *(_WORD *)v21 = 0;
    }
    else
    {
      v21 = 0;
    }
    *(_QWORD *)(v12 + 48) = v21;
    if ( !v21 )
      goto LABEL_8;
    v23 = -1;
    v24 = -1;
    do
      ++v24;
    while ( v7[v24] );
    if ( v24 > (unsigned __int64)v21[3] )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v21, v24, v22, v7);
    }
    else
    {
      if ( (unsigned __int64)v21[3] <= 7 )
        v25 = (char *)v21;
      else
        v25 = *v21;
      v21[2] = (char *)v24;
      v26 = 2 * v24;
      memmove_0(v25, Src, 2 * v24);
      *(_WORD *)&v25[v26] = 0;
    }
    v27 = *(unsigned __int16 **)(v12 + 48);
    hHash = v12;
    if ( *((_QWORD *)v27 + 3) <= 7u )
    {
      v28 = v27;
      v29 = v27;
    }
    else
    {
      v28 = *(unsigned __int16 **)v27;
      v29 = *(unsigned __int16 **)v27;
    }
    v30 = &v29[*((_QWORD *)v27 + 2)];
    if ( *((_QWORD *)v27 + 3) > 7u )
      v27 = *(unsigned __int16 **)v27;
    while ( v27 != v30 )
      *v28++ = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*v27++);
  }
  else
  {
    hHash = v12;
    v23 = -1;
  }
  if ( v67 )
  {
    v31 = (char **)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
    if ( v31 )
    {
      *(_OWORD *)v31 = 0;
      v31[2] = 0;
      v31[3] = (char *)7;
      *(_WORD *)v31 = 0;
    }
    else
    {
      v31 = 0;
    }
    *(_QWORD *)(v12 + 56) = v31;
    if ( !v31 )
      goto LABEL_8;
    v33 = -1;
    v34 = v67;
    do
      ++v33;
    while ( *((_WORD *)v67 + v33) );
    if ( v33 > (unsigned __int64)v31[3] )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v31,
        v33,
        v32,
        v67);
    }
    else
    {
      if ( (unsigned __int64)v31[3] <= 7 )
        v35 = (char *)v31;
      else
        v35 = *v31;
      v31[2] = (char *)v33;
      v36 = 2 * v33;
      memmove_0(v35, v34, 2 * v33);
      *(_WORD *)&v35[v36] = 0;
    }
    v37 = *(unsigned __int16 **)(v12 + 56);
    hHash = v12;
    if ( *((_QWORD *)v37 + 3) <= 7u )
    {
      v38 = v37;
      v39 = v37;
    }
    else
    {
      v38 = *(unsigned __int16 **)v37;
      v39 = *(unsigned __int16 **)v37;
    }
    v40 = &v39[*((_QWORD *)v37 + 2)];
    if ( *((_QWORD *)v37 + 3) > 7u )
      v37 = *(unsigned __int16 **)v37;
    while ( v37 != v40 )
      *v38++ = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*v37++);
  }
  if ( v68 )
  {
    v41 = (char **)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
    if ( v41 )
    {
      *(_OWORD *)v41 = 0;
      v41[2] = 0;
      v41[3] = (char *)7;
      *(_WORD *)v41 = 0;
    }
    else
    {
      v41 = 0;
    }
    *(_QWORD *)(v12 + 64) = v41;
    if ( !v41 )
      goto LABEL_8;
    v43 = v68;
    do
      ++v23;
    while ( *((_WORD *)v68 + v23) );
    if ( v23 > (unsigned __int64)v41[3] )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v41,
        v23,
        v42,
        v68);
    }
    else
    {
      if ( (unsigned __int64)v41[3] <= 7 )
        v44 = (char *)v41;
      else
        v44 = *v41;
      v41[2] = (char *)v23;
      memmove_0(v44, v43, 2 * v23);
      *(_WORD *)&v44[2 * v23] = 0;
    }
    v45 = *(unsigned __int16 **)(v12 + 64);
    hHash = v12;
    if ( *((_QWORD *)v45 + 3) <= 7u )
    {
      v46 = v45;
      v47 = v45;
    }
    else
    {
      v46 = *(unsigned __int16 **)v45;
      v47 = *(unsigned __int16 **)v45;
    }
    v48 = &v47[*((_QWORD *)v45 + 2)];
    if ( *((_QWORD *)v45 + 3) > 7u )
      v45 = *(unsigned __int16 **)v45;
    while ( v45 != v48 )
      *v46++ = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*v45++);
  }
  *(_DWORD *)(v12 + 80) = a6;
  if ( a6 != 1 )
    goto LABEL_118;
  v49 = operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
  v50 = v49;
  v68 = v49;
  if ( v49 )
  {
    *v49 = 0;
    v49[1] = 0;
    v51 = operator new(0x28u);
    *v51 = v51;
    v51[1] = v51;
    v51[2] = v51;
    *((_WORD *)v51 + 12) = 257;
    *v50 = v51;
  }
  else
  {
    v50 = 0;
  }
  *(_QWORD *)(v12 + 40) = v50;
  if ( v50 )
  {
LABEL_118:
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v52 = g_Rules;
      if ( *((_QWORD *)g_Rules + 1) == 0xAAAAAAAAAAAAAAALL )
        std::_Xlength_error("list too long");
      v53 = *(_QWORD *)g_Rules;
      v68 = g_Rules;
      v69 = 0;
      v54 = operator new(0x18u);
      v54[2] = v12;
      ++v52[1];
      v55 = *(_QWORD **)(v53 + 8);
      *v54 = v53;
      v54[1] = v55;
      *(_QWORD *)(v53 + 8) = v54;
      *v55 = v54;
      if ( v70 )
        *v70 = v12;
      v15 = 0;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        pdwDataLen = -2147024882;
        v15 = -2147024882;
        v12 = hHash;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_14000B6C4);
        goto LABEL_101;
      }
    }
LABEL_115:
    v12 = 0;
    goto LABEL_116;
  }
LABEL_8:
  v15 = -2147024882;
LABEL_101:
  v56 = *(void **)(v12 + 32);
  if ( v56 )
  {
    std::wstring::~wstring(*(char ***)(v12 + 32));
    operator delete(v56, (const struct std::nothrow_t *)0x20);
  }
  v57 = *(void **)(v12 + 48);
  if ( v57 )
  {
    std::wstring::~wstring(*(char ***)(v12 + 48));
    operator delete(v57, (const struct std::nothrow_t *)0x20);
  }
  v58 = *(void **)(v12 + 56);
  if ( v58 )
  {
    std::wstring::~wstring(*(char ***)(v12 + 56));
    operator delete(v58, (const struct std::nothrow_t *)0x20);
  }
  v59 = *(void **)(v12 + 64);
  if ( v59 )
  {
    std::wstring::~wstring(*(char ***)(v12 + 64));
    operator delete(v59, (const struct std::nothrow_t *)0x20);
  }
  v60 = *(void ***)(v12 + 40);
  if ( v60 )
  {
    v61 = (_QWORD *)*((_QWORD *)*v60 + 1);
    while ( !*((_BYTE *)v61 + 25) )
    {
      std::_Tree_val<std::_Tree_simple_types<std::wstring *>>::_Erase_tree<std::allocator<std::_Tree_node<std::wstring *,void *>>>(
        (__int64)v60,
        (__int64)v60,
        v61[2]);
      v62 = v61;
      v61 = (_QWORD *)*v61;
      operator delete(v62, (const struct std::nothrow_t *)0x28);
    }
    operator delete(*v60, (const struct std::nothrow_t *)0x28);
    operator delete(v60, (const struct std::nothrow_t *)0x10);
  }
LABEL_116:
  operator delete((void *)v12, (const struct std::nothrow_t *)0x60);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14000b144  push    rbx
0x14000b146  push    rsi
0x14000b147  push    rdi
0x14000b148  push    r12
0x14000b14a  push    r13
0x14000b14c  push    r14
0x14000b14e  push    r15
0x14000b150  sub     rsp, 90h
0x14000b157  mov     rax, cs:__security_cookie
0x14000b15e  xor     rax, rsp
0x14000b161  mov     [rsp+0C8h+var_40], rax
0x14000b169  mov     [rsp+0C8h+var_80], r9
0x14000b16e  mov     r14, r8
0x14000b171  mov     [rsp+0C8h+Src], r8
0x14000b176  mov     ebx, edx
0x14000b178  mov     r15, rcx
0x14000b17b  mov     rax, [rsp+0C8h+arg_20]
0x14000b183  mov     [rsp+0C8h+var_78], rax
0x14000b188  mov     rcx, [rsp+0C8h+arg_30]
0x14000b190  mov     [rsp+0C8h+var_68], rcx
0x14000b195  xor     edi, edi
0x14000b197  mov     r13d, edi
0x14000b19a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000b1a1  lea     ecx, [rdi+60h]; unsigned __int64
0x14000b1a4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000b1a9  mov     rsi, rax
0x14000b1ac  test    rax, rax
0x14000b1af  jz      loc_14000B79A
0x14000b1b5  xor     edx, edx; Val
0x14000b1b7  lea     r8d, [rdi+60h]; Size
0x14000b1bb  mov     rcx, rax; void *
0x14000b1be  call    memset_0
0x14000b1c3  xor     edx, edx; Val
0x14000b1c5  lea     r8d, [rdi+60h]; Size
0x14000b1c9  mov     rcx, rsi; void *
0x14000b1cc  call    memset_0
0x14000b1d1  mov     [rsi+48h], ebx
0x14000b1d4  cmp     ebx, 2
0x14000b1d7  jnz     short loc_14000B1E0
0x14000b1d9  mov     dword ptr [rsi+4Ch], 1
0x14000b1e0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000b1e7  mov     ecx, 20h ; ' '; unsigned __int64
0x14000b1ec  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000b1f1  mov     r12d, 7
0x14000b1f7  test    rax, rax
0x14000b1fa  jz      short loc_14000B20F
0x14000b1fc  xorps   xmm0, xmm0
0x14000b1ff  movups  xmmword ptr [rax], xmm0
0x14000b202  mov     [rax+10h], rdi
0x14000b206  mov     [rax+18h], r12
0x14000b20a  mov     [rax], di
0x14000b20d  jmp     short loc_14000B212
0x14000b20f  mov     rax, rdi
0x14000b212  mov     [rsi+20h], rax
0x14000b216  test    rax, rax
0x14000b219  jnz     short loc_14000B225
0x14000b21b  mov     ebx, 8007000Eh
0x14000b220  jmp     loc_14000B6CF
0x14000b225  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000b229  mov     rdx, rbx
0x14000b22c  inc     rdx
0x14000b22f  cmp     [r15+rdx*2], di
0x14000b234  jnz     short loc_14000B22C
0x14000b236  cmp     rdx, [rax+18h]
0x14000b23a  ja      short loc_14000B270
0x14000b23c  cmp     [rax+18h], r12
0x14000b240  jbe     short loc_14000B247
0x14000b242  mov     r14, [rax]
0x14000b245  jmp     short loc_14000B24A
0x14000b247  mov     r14, rax
0x14000b24a  mov     [rax+10h], rdx
0x14000b24e  lea     rbx, [rdx+rdx]
0x14000b252  mov     r8, rbx; Size
0x14000b255  mov     rdx, r15; Src
0x14000b258  mov     rcx, r14; void *
0x14000b25b  call    memmove_0
0x14000b260  mov     [rbx+r14], di
0x14000b265  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000b269  mov     r14, [rsp+0C8h+Src]
0x14000b26e  jmp     short loc_14000B27B
0x14000b270  mov     r9, r15
0x14000b273  mov     rcx, rax
0x14000b276  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14000b27b  mov     [rsp+0C8h+hHash], rdi
0x14000b280  mov     [rsp+0C8h+pdwDataLen], 20h ; ' '
0x14000b288  lea     rax, [rsp+0C8h+hHash]
0x14000b28d  mov     [rsp+0C8h+phHash], rax; phHash
0x14000b292  xor     r9d, r9d; dwFlags
0x14000b295  xor     r8d, r8d; hKey
0x14000b298  mov     edx, 800Ch; Algid
0x14000b29d  mov     rcx, cs:hProv; hProv
0x14000b2a4  call    cs:__imp_CryptCreateHash
0x14000b2aa  test    eax, eax
0x14000b2ac  jnz     short loc_14000B2C5
0x14000b2ae  call    cs:__imp_GetLastError
0x14000b2b4  mov     ebx, eax
0x14000b2b6  test    eax, eax
0x14000b2b8  jle     short loc_14000B313
0x14000b2ba  movzx   ebx, ax
0x14000b2bd  or      ebx, 80070000h
0x14000b2c3  jmp     short loc_14000B313
0x14000b2c5  mov     r8, rbx
0x14000b2c8  inc     r8
0x14000b2cb  cmp     [r15+r8*2], di
0x14000b2d0  jnz     short loc_14000B2C8
0x14000b2d2  add     r8d, r8d; dwDataLen
0x14000b2d5  xor     r9d, r9d; dwFlags
0x14000b2d8  mov     rdx, r15; pbData
0x14000b2db  mov     rcx, [rsp+0C8h+hHash]; hHash
0x14000b2e0  call    cs:__imp_CryptHashData
0x14000b2e6  test    eax, eax
0x14000b2e8  jz      short loc_14000B2AE
0x14000b2ea  mov     dword ptr [rsp+0C8h+phHash], edi; dwFlags
0x14000b2ee  lea     r9, [rsp+0C8h+pdwDataLen]; pdwDataLen
0x14000b2f3  lea     r8, [rsp+0C8h+pbData]; pbData
0x14000b2f8  mov     edx, 2; dwParam
0x14000b2fd  mov     rcx, [rsp+0C8h+hHash]; hHash
0x14000b302  call    cs:__imp_CryptGetHashParam
0x14000b308  test    eax, eax
0x14000b30a  jz      short loc_14000B2AE
0x14000b30c  mov     ebx, edi
0x14000b30e  mov     r13d, dword ptr [rsp+0C8h+pbData]
0x14000b313  mov     rcx, [rsp+0C8h+hHash]; hHash
0x14000b318  test    rcx, rcx
0x14000b31b  jz      short loc_14000B323
0x14000b31d  call    cs:__imp_CryptDestroyHash
0x14000b323  test    ebx, ebx
0x14000b325  js      loc_14000B6CF
0x14000b32b  mov     eax, 0AAAAAAABh
0x14000b330  mul     r13d
0x14000b333  shr     edx, 4
0x14000b336  lea     eax, [rdx+rdx*2]
0x14000b339  shl     eax, 3
0x14000b33c  sub     r13d, eax
0x14000b33f  lea     ecx, [r13+0Ch]
0x14000b343  mov     eax, 1
0x14000b348  shl     rax, cl
0x14000b34b  mov     [rsi+58h], rax
0x14000b34f  test    r14, r14
0x14000b352  jz      loc_14000B42F
0x14000b358  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000b35f  mov     ecx, 20h ; ' '; unsigned __int64
0x14000b364  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000b369  test    rax, rax
0x14000b36c  jz      short loc_14000B381
0x14000b36e  xorps   xmm0, xmm0
0x14000b371  movups  xmmword ptr [rax], xmm0
0x14000b374  mov     [rax+10h], rdi
0x14000b378  mov     [rax+18h], r12
0x14000b37c  mov     [rax], di
0x14000b37f  jmp     short loc_14000B384
0x14000b381  mov     rax, rdi
0x14000b384  mov     [rsi+30h], rax
0x14000b388  test    rax, rax
0x14000b38b  jz      loc_14000B21B
0x14000b391  or      r13, 0FFFFFFFFFFFFFFFFh
0x14000b395  mov     rdx, r13
0x14000b398  inc     rdx
0x14000b39b  cmp     [r14+rdx*2], di
0x14000b3a0  jnz     short loc_14000B398
0x14000b3a2  cmp     rdx, [rax+18h]
0x14000b3a6  ja      short loc_14000B3D5
0x14000b3a8  cmp     [rax+18h], r12
0x14000b3ac  jbe     short loc_14000B3B3
0x14000b3ae  mov     r14, [rax]
0x14000b3b1  jmp     short loc_14000B3B6
0x14000b3b3  mov     r14, rax
0x14000b3b6  mov     [rax+10h], rdx
0x14000b3ba  lea     rbx, [rdx+rdx]
0x14000b3be  mov     r8, rbx; Size
0x14000b3c1  mov     rdx, [rsp+0C8h+Src]; Src
0x14000b3c6  mov     rcx, r14; void *
0x14000b3c9  call    memmove_0
0x14000b3ce  mov     [r14+rbx], di
0x14000b3d3  jmp     short loc_14000B3E0
0x14000b3d5  mov     r9, r14
0x14000b3d8  mov     rcx, rax
0x14000b3db  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14000b3e0  mov     r14, [rsi+30h]
0x14000b3e4  mov     [rsp+0C8h+hHash], rsi
0x14000b3e9  cmp     [r14+18h], r12
0x14000b3ed  jbe     short loc_14000B3F7
0x14000b3ef  mov     r15, [r14]
0x14000b3f2  mov     rcx, r15
0x14000b3f5  jmp     short loc_14000B3FD
0x14000b3f7  mov     r15, r14
0x14000b3fa  mov     rcx, r14
0x14000b3fd  mov     rax, [r14+10h]
0x14000b401  lea     rbx, [rcx+rax*2]
0x14000b405  jbe     short loc_14000B428
0x14000b407  mov     r14, [r14]
0x14000b40a  jmp     short loc_14000B428
0x14000b40c  movzx   ecx, word ptr [r14]
0x14000b410  mov     rax, cs:__imp__o_towlower
0x14000b417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b41c  mov     [r15], ax
0x14000b420  lea     r15, [r15+2]
0x14000b424  add     r14, 2
0x14000b428  cmp     r14, rbx
0x14000b42b  jnz     short loc_14000B40C
0x14000b42d  jmp     short loc_14000B438
0x14000b42f  mov     [rsp+0C8h+hHash], rsi
0x14000b434  or      r13, 0FFFFFFFFFFFFFFFFh
0x14000b438  cmp     [rsp+0C8h+var_80], rdi
0x14000b43d  jz      loc_14000B516
0x14000b443  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000b44a  mov     ecx, 20h ; ' '; unsigned __int64
0x14000b44f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000b454  test    rax, rax
0x14000b457  jz      short loc_14000B46C
0x14000b459  xorps   xmm0, xmm0
0x14000b45c  movups  xmmword ptr [rax], xmm0
0x14000b45f  mov     [rax+10h], rdi
0x14000b463  mov     [rax+18h], r12
0x14000b467  mov     [rax], di
0x14000b46a  jmp     short loc_14000B46F
0x14000b46c  mov     rax, rdi
0x14000b46f  mov     [rsi+38h], rax
0x14000b473  test    rax, rax
0x14000b476  jz      loc_14000B21B
0x14000b47c  mov     rdx, r13
0x14000b47f  mov     rcx, [rsp+0C8h+var_80]
0x14000b484  inc     rdx
0x14000b487  cmp     [rcx+rdx*2], di
0x14000b48b  jnz     short loc_14000B484
0x14000b48d  cmp     rdx, [rax+18h]
0x14000b491  ja      short loc_14000B4BE
0x14000b493  cmp     [rax+18h], r12
0x14000b497  jbe     short loc_14000B49E
0x14000b499  mov     r14, [rax]
0x14000b49c  jmp     short loc_14000B4A1
0x14000b49e  mov     r14, rax
0x14000b4a1  mov     [rax+10h], rdx
0x14000b4a5  lea     rbx, [rdx+rdx]
0x14000b4a9  mov     r8, rbx; Size
0x14000b4ac  mov     rdx, rcx; Src
0x14000b4af  mov     rcx, r14; void *
0x14000b4b2  call    memmove_0
0x14000b4b7  mov     [r14+rbx], di
0x14000b4bc  jmp     short loc_14000B4C9
0x14000b4be  mov     r9, rcx
0x14000b4c1  mov     rcx, rax
0x14000b4c4  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14000b4c9  mov     r14, [rsi+38h]
0x14000b4cd  mov     [rsp+0C8h+hHash], rsi
0x14000b4d2  cmp     [r14+18h], r12
0x14000b4d6  jbe     short loc_14000B4E0
0x14000b4d8  mov     r15, [r14]
0x14000b4db  mov     rcx, r15
0x14000b4de  jmp     short loc_14000B4E6
0x14000b4e0  mov     r15, r14
0x14000b4e3  mov     rcx, r14
0x14000b4e6  mov     rax, [r14+10h]
0x14000b4ea  lea     rbx, [rcx+rax*2]
0x14000b4ee  jbe     short loc_14000B511
0x14000b4f0  mov     r14, [r14]
0x14000b4f3  jmp     short loc_14000B511
0x14000b4f5  movzx   ecx, word ptr [r14]
0x14000b4f9  mov     rax, cs:__imp__o_towlower
0x14000b500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b505  mov     [r15], ax
0x14000b509  lea     r15, [r15+2]
0x14000b50d  add     r14, 2
0x14000b511  cmp     r14, rbx
0x14000b514  jnz     short loc_14000B4F5
0x14000b516  cmp     [rsp+0C8h+var_78], rdi
0x14000b51b  jz      loc_14000B5F9
0x14000b521  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000b528  mov     ecx, 20h ; ' '; unsigned __int64
0x14000b52d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000b532  test    rax, rax
0x14000b535  jz      short loc_14000B54A
0x14000b537  xorps   xmm0, xmm0
0x14000b53a  movups  xmmword ptr [rax], xmm0
0x14000b53d  mov     [rax+10h], rdi
0x14000b541  mov     [rax+18h], r12
0x14000b545  mov     [rax], di
0x14000b548  jmp     short loc_14000B54D
0x14000b54a  mov     rax, rdi
0x14000b54d  mov     [rsi+40h], rax
0x14000b551  test    rax, rax
0x14000b554  jz      loc_14000B21B
0x14000b55a  mov     rcx, [rsp+0C8h+var_78]
0x14000b55f  inc     r13
0x14000b562  cmp     [rcx+r13*2], di
0x14000b567  jnz     short loc_14000B55F
0x14000b569  cmp     r13, [rax+18h]
0x14000b56d  ja      short loc_14000B59E
0x14000b56f  cmp     [rax+18h], r12
0x14000b573  jbe     short loc_14000B57A
0x14000b575  mov     r14, [rax]
0x14000b578  jmp     short loc_14000B57D
0x14000b57a  mov     r14, rax
0x14000b57d  mov     [rax+10h], r13
0x14000b581  lea     rbx, ds:0[r13*2]
0x14000b589  mov     r8, rbx; Size
0x14000b58c  mov     rdx, rcx; Src
0x14000b58f  mov     rcx, r14; void *
0x14000b592  call    memmove_0
0x14000b597  mov     [r14+rbx], di
  ... truncated ...
```
