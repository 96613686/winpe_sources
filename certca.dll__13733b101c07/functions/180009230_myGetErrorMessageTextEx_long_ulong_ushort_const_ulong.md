# myGetErrorMessageTextEx(long,ulong,ushort const * *,ulong)

- ea: `0x180009230`
- end: `0x180009b12`
- name: `?myGetErrorMessageTextEx@@YAPEAGJKPEAPEBGK@Z`
- size: `2274`
- prototype: `unsigned __int16 *__fastcall(int, char, unsigned __int16 **, unsigned int)`
- caller_count: `3`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x18000a400`
- `0x18001b07c`
- `0x180029ae0`

## callees

- `0x180007a00`
- `0x180008420`
- `0x180008610`
- `0x180009230`
- `0x180009b20`
- `0x18000a3b0`
- `0x180013a86`
- `0x18001d4c4`
- `0x18001dfa0`
- `0x180038262`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000933a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000933a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009480`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800096c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009480`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800096c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000966c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000966c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009501`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009501`

## string_xrefs

- `0x1800099c2`: `ntdll.dll`
- `0x180009938`: `winhttp.dll`
- `0x180009975`: `cdosys.dll`
- `0x180009a02`: `webservices.dll`

## pseudocode

```c
unsigned __int16 *__fastcall myGetErrorMessageTextEx(int a1, char a2, unsigned __int16 **a3, unsigned int a4)
{
  wchar_t *v4; // r14
  char v5; // si
  int v7; // r13d
  __int64 v8; // rbx
  UINT v9; // ecx
  const unsigned __int16 *ResourceString; // r15
  __int64 v11; // rdi
  __int64 v12; // rsi
  unsigned __int64 v13; // rbx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r12
  const unsigned __int16 *v16; // r14
  __int64 v17; // rdx
  unsigned __int64 v18; // rcx
  unsigned __int16 *v19; // rax
  unsigned __int64 v20; // r8
  __int64 v21; // rcx
  bool v22; // zf
  unsigned __int64 v23; // rax
  unsigned __int16 *v24; // r8
  unsigned __int16 *v25; // rcx
  unsigned __int64 v26; // rcx
  unsigned __int16 *v27; // rax
  unsigned __int64 v28; // r8
  unsigned __int16 *v29; // rax
  unsigned __int16 *v30; // rcx
  unsigned __int64 j; // rbx
  unsigned __int16 *v32; // rdx
  va_list *Arguments; // rax
  DWORD v35; // ecx
  unsigned __int64 v36; // rsi
  __int64 v37; // rcx
  char v38; // al
  int v39; // edx
  wchar_t v40; // ax
  char **i; // rcx
  char **v42; // rcx
  int v43; // edx
  __int64 v44; // rax
  int v45; // r9d
  int v46; // r10d
  __int64 v47; // rax
  DWORD LastError; // eax
  int v49; // esi
  DWORD v50; // r13d
  unsigned int v51; // edx
  unsigned int v52; // esi
  __int64 v53; // r13
  const unsigned __int16 *v54; // rax
  int v55; // r8d
  const char *v56; // rdx
  int v57; // r8d
  unsigned int v58; // eax
  unsigned int v59; // eax
  unsigned __int16 **v60; // rsi
  unsigned int v61; // eax
  unsigned int v62; // eax
  int v63; // edx
  int v64; // edx
  int v66; // [rsp+40h] [rbp-C0h]
  void *Src; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v69; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 **v70; // [rsp+58h] [rbp-A8h]
  WCHAR Buffer[4]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v72[800]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v73[120]; // [rsp+390h] [rbp+290h] BYREF

  v4 = 0;
  v70 = a3;
  v5 = 0;
  Src = 0;
  v69 = 0;
  v7 = a1;
  v8 = -1;
  if ( a1 == -2147418113 )
  {
    v9 = 211;
    goto LABEL_3;
  }
  if ( a1 == -2147483646 )
  {
    v9 = 246;
LABEL_3:
    ResourceString = myLoadResourceString(v9);
    if ( ResourceString )
      goto LABEL_4;
  }
  v39 = (unsigned __int16)v7;
  if ( (v7 & 0xFFFF0000) != 0x80070000 )
    v39 = v7;
  if ( (unsigned int)(v39 - 100) <= 0x195 )
  {
    for ( i = &off_18003C000; i < (char **)&std::error_category::`vftable'; i += 2 )
    {
      if ( v39 == *((_DWORD *)i + 2) )
      {
        _mm_lfence();
        ResourceString = myLoadResourceString(*((_DWORD *)i + 3));
        if ( !ResourceString )
          break;
        v47 = -1;
        do
          ++v47;
        while ( ResourceString[v47] );
        if ( (_DWORD)v47 && (a2 & 2) != 0 )
          v5 = 1;
        goto LABEL_4;
      }
    }
  }
  ResourceString = (const unsigned __int16 *)&v69;
LABEL_4:
  v11 = -1;
  do
    ++v11;
  while ( ResourceString[v11] );
  if ( v5 )
    goto LABEL_7;
  *(_QWORD *)Buffer = 0;
  memset_0(v72, 0, sizeof(v72));
  if ( v70 && a4 )
  {
    if ( a4 - 1 <= 0x62 )
      memcpy_0(v72, v70, 8LL * a4);
    Arguments = (va_list *)v72;
    v35 = 12544;
  }
  else
  {
    Arguments = 0;
    v35 = 4864;
  }
  if ( !FormatMessageW(v35, 0, v7, 0x400u, Buffer, 1u, Arguments) )
  {
    LastError = GetLastError();
    v49 = -2147024579;
    v50 = myHError(LastError);
    CSPrintErrorLineFileData2(0, 0x46101CAu, v50, -2147024579);
    if ( v50 )
    {
      CSPrintErrorLineFileData2(0, 0x41501CAu, v50, -2147024579);
      CSPrintErrorLineFileData2(0, 0x44D0334u, v50, -2147024579);
      v51 = 72876852;
      goto LABEL_77;
    }
    v7 = a1;
  }
  v36 = -1;
  do
    ++v36;
  while ( *(_WORD *)(*(_QWORD *)Buffer + 2 * v36) );
  if ( v36 <= 0x10000 )
  {
    Src = *(void **)Buffer;
    v37 = (unsigned int)v36;
    if ( (_DWORD)v36 )
      goto LABEL_56;
    goto LABEL_80;
  }
  v51 = 73728820;
  v49 = 0;
  v50 = -2147024362;
LABEL_77:
  CSPrintErrorLineFileData2(0, v51, v50, v49);
  if ( *(_QWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
  SetLastError(v50);
  v7 = a1;
  v37 = 0;
LABEL_80:
  if ( (v7 & 0xFFFF0000) == 0xC06D0000 )
    v37 = errFormatMessage(
            0,
            (unsigned __int16)v7,
            (unsigned __int16)v7,
            0,
            1,
            (const unsigned __int16 **)v70,
            a4,
            (unsigned __int16 **)&Src);
LABEL_56:
  if ( !v37 )
  {
    v52 = v7 & 0xFFFF0000;
    if ( (v7 & 0xFFFF0000) != 0xE0000000 )
      goto LABEL_111;
    v42 = &off_18003CD80;
    LODWORD(v53) = 0;
    while ( v42 < (char **)qword_18003CDF0 )
    {
      if ( a1 == *((_DWORD *)v42 + 2) )
      {
        _mm_lfence();
        v54 = myLoadResourceString(*((_DWORD *)v42 + 3));
        v4 = (wchar_t *)v54;
        if ( v54 )
        {
          v53 = -1;
          do
            ++v53;
          while ( v54[v53] );
        }
        break;
      }
      v42 += 2;
    }
    v37 = (unsigned int)v53;
    v22 = (_DWORD)v53 == 0;
    v7 = a1;
    if ( v22 )
    {
LABEL_111:
      if ( v52 == -939524096 )
      {
        v55 = -(unsigned __int16)v7;
      }
      else
      {
        if ( v52 != -65536 )
          goto LABEL_121;
        v55 = v7;
      }
      v45 = 0;
      v46 = 368;
      while ( v45 <= v46 )
      {
        v43 = (v46 - v45) / 2 + v45;
        v44 = 2LL * v43;
        if ( v55 == LODWORD(qword_18003CDF0[v44]) )
        {
          v56 = (const char *)qword_18003CDF0[v44 + 1];
          if ( !v56 )
            break;
          if ( !(unsigned int)myConvertSzToWsz((unsigned __int16 **)&Src, v56, v55) )
          {
            v15 = 0;
            CSPrintErrorLineFileData2(0, 0x5110334u, -2147024882, 0);
            goto LABEL_46;
          }
          v37 = -1;
          do
            ++v37;
          while ( *((_WORD *)Src + v37) );
          break;
        }
        if ( v55 - LODWORD(qword_18003CDF0[v44]) <= 0 )
          v46 = v43 - 1;
        else
          v45 = v43 + 1;
      }
    }
LABEL_121:
    if ( v37 )
      goto LABEL_57;
    if ( (v7 & 0xEFFF0000) != 0xC0000000 )
    {
      v57 = (unsigned __int16)v7;
      if ( (v7 & 0xFFFF0000) != 0x80070000 )
        v57 = v7;
      v58 = errFormatMessage(
              L"winhttp.dll",
              v7,
              v57,
              0,
              1,
              (const unsigned __int16 **)v70,
              a4,
              (unsigned __int16 **)&Src);
      v37 = v58;
      if ( v58 )
        goto LABEL_57;
    }
    v59 = errFormatMessage(L"cdosys.dll", v7, v7, 0, 1, (const unsigned __int16 **)v70, a4, (unsigned __int16 **)&Src);
    v37 = v59;
    if ( v59 )
      goto LABEL_57;
    v60 = v70;
    if ( (v7 & 0xEFFF0000) == 0xC0000000 )
    {
      v61 = errFormatMessage(
              L"ntdll.dll",
              v7,
              v7 & 0xEFFFFFFF,
              1,
              1,
              (const unsigned __int16 **)v70,
              a4,
              (unsigned __int16 **)&Src);
      v37 = v61;
      if ( v61 )
        goto LABEL_57;
    }
    v62 = errFormatMessage(
            L"webservices.dll",
            v7,
            v7,
            1,
            1,
            (const unsigned __int16 **)v60,
            a4,
            (unsigned __int16 **)&Src);
    v37 = v62;
    if ( v62 || v7 >= 0 )
      goto LABEL_57;
    v63 = (v7 >> 16) & 0x1FFF;
    if ( v63 == 24 )
    {
      v64 = v7 & 0x21FF | 0xDE00;
    }
    else if ( v63 == 2000 )
    {
      v64 = v7 & 0x1FFF | 0xE000;
    }
    else if ( (unsigned int)(v63 - 682) > 5 )
    {
      if ( v63 != 28 )
        goto LABEL_57;
      v64 = v7 & 0x31FF | 0xCE00;
    }
    else
    {
      v64 = (unsigned __int8)v7 | (((v7 >> 8) & 0x1FFF00) - 174592) | 0xF000;
    }
    v37 = errFormatMessage(
            L"certutil.exe",
            v64,
            v64,
            1,
            0,
            (const unsigned __int16 **)v60,
            a4,
            (unsigned __int16 **)&Src);
  }
LABEL_57:
  v38 = a2 | 1;
  if ( v37 )
    v38 = a2;
  a2 = v38;
  if ( !v37 )
  {
    v4 = (wchar_t *)myLoadResourceString(0xD2u);
    if ( !v4 )
      v4 = aError_0;
  }
LABEL_7:
  v73[0] = 0;
  v66 = a2 & 1;
  if ( (a2 & 1) != 0 )
    myHResultToStringInternal(v73, 0x73u, v7, 0, (a2 & 2) != 0);
  if ( Src )
    v4 = (wchar_t *)Src;
  v12 = 0;
  if ( v4 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v4[v12] );
    for ( ; v12; --v12 )
    {
      v40 = v4[v12 - 1];
      if ( v40 != 10 && v40 != 13 )
        break;
    }
  }
  do
    ++v8;
  while ( v73[v8] );
  v13 = v12 + v11 + v8 + 3;
  v14 = (unsigned __int16 *)LocalAlloc(0, 2 * v13);
  v15 = v14;
  if ( v14 )
  {
    if ( v4 )
      memcpy_0(v14, v4, 2 * v12);
    v16 = L" ";
    v15[v12] = 0;
    if ( v11 )
    {
      if ( v12 )
        StringCchCatW(v15, v13, L" ");
      StringCchCatW(v15, v13, ResourceString);
    }
    if ( v66 )
    {
      v17 = 2147483646;
      if ( v13 - 1 <= 0x7FFFFFFE )
      {
        v18 = v13;
        v19 = v15;
        while ( *v19 )
        {
          ++v19;
          if ( !--v18 )
          {
            v20 = 0;
            goto LABEL_27;
          }
        }
        v20 = v13 - v18;
LABEL_27:
        if ( v18 )
        {
          v21 = 2147483646;
          v23 = v13 - v20;
          v22 = v13 == v20;
          v24 = &v15[v20];
          if ( !v22 )
          {
            do
            {
              if ( !v21 )
                break;
              if ( !*v16 )
                break;
              *v24++ = *v16++;
              --v21;
              --v23;
            }
            while ( v23 );
          }
          v25 = v24 - 1;
          if ( v23 )
            v25 = v24;
          *v25 = 0;
        }
        v26 = v13;
        v27 = v15;
        do
        {
          if ( !*v27 )
            break;
          ++v27;
          --v26;
        }
        while ( v26 );
        if ( v26 )
        {
          v28 = v13 - v26;
          v29 = v73;
          v30 = &v15[v13 - v26];
          for ( j = v13 - v28; j; --j )
          {
            if ( !v17 )
              break;
            if ( !*v29 )
              break;
            *v30++ = *v29++;
            --v17;
          }
          v32 = v30 - 1;
          if ( j )
            v32 = v30;
          *v32 = 0;
        }
      }
    }
  }
  else
  {
    CSPrintErrorLineFileData2(0, 0x5980334u, -2147024882, 0);
  }
LABEL_46:
  if ( Src )
    LocalFree(Src);
  return v15;
}

```

## disassembly

```asm
0x180009230  mov     [rsp-8+arg_8], rbx
0x180009235  push    rbp
0x180009236  push    rsi
0x180009237  push    rdi
0x180009238  push    r12
0x18000923a  push    r13
0x18000923c  push    r14
0x18000923e  push    r15
0x180009240  lea     rbp, [rsp-390h]
0x180009248  sub     rsp, 490h
0x18000924f  mov     rax, cs:__security_cookie
0x180009256  xor     rax, rsp
0x180009259  mov     [rbp+3C0h+var_40], rax
0x180009260  xor     eax, eax
0x180009262  mov     [rsp+4C0h+var_47C], r9d
0x180009267  xor     r14d, r14d
0x18000926a  mov     [rsp+4C0h+var_468], r8
0x18000926f  xor     sil, sil
0x180009272  mov     [rsp+4C0h+var_480], ecx
0x180009276  mov     [rsp+4C0h+Src], 0
0x18000927f  mov     r12d, edx
0x180009282  mov     [rsp+4C0h+var_470], ax
0x180009287  mov     r13d, ecx
0x18000928a  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180009291  cmp     ecx, 8000FFFFh
0x180009297  jnz     loc_1800095C9
0x18000929d  mov     ecx, 0D3h; uID
0x1800092a2  call    ?myLoadResourceString@@YAPEBGK@Z; myLoadResourceString(ulong)
0x1800092a7  mov     r15, rax
0x1800092aa  test    rax, rax
0x1800092ad  jz      loc_1800095D6
0x1800092b3  mov     rdi, rbx
0x1800092b6  inc     rdi
0x1800092b9  cmp     [r15+rdi*2], r14w
0x1800092be  jnz     short loc_1800092B6
0x1800092c0  test    sil, sil
0x1800092c3  jz      loc_1800094B3
0x1800092c9  xor     eax, eax
0x1800092cb  mov     [rbp+3C0h+var_130], ax
0x1800092d2  mov     eax, r12d
0x1800092d5  and     eax, 1
0x1800092d8  mov     [rsp+4C0h+var_480], eax
0x1800092dc  jnz     loc_180009587
0x1800092e2  mov     rcx, [rsp+4C0h+Src]
0x1800092e7  test    rcx, rcx
0x1800092ea  cmovnz  r14, rcx
0x1800092ee  xor     esi, esi
0x1800092f0  test    r14, r14
0x1800092f3  jz      short loc_180009315
0x1800092f5  mov     rsi, rbx
0x1800092f8  nop     dword ptr [rax+rax+00000000h]
0x180009300  inc     rsi
0x180009303  cmp     word ptr [r14+rsi*2], 0
0x180009309  jnz     short loc_180009300
0x18000930b  cmp     rsi, 1
0x18000930f  jnb     loc_180009600
0x180009315  lea     rax, [rbp+3C0h+var_130]
0x18000931c  nop     dword ptr [rax+00h]
0x180009320  inc     rbx
0x180009323  cmp     word ptr [rax+rbx*2], 0
0x180009328  jnz     short loc_180009320
0x18000932a  add     rbx, 3
0x18000932e  xor     ecx, ecx; uFlags
0x180009330  add     rbx, rdi
0x180009333  add     rbx, rsi
0x180009336  lea     rdx, [rbx+rbx]; uBytes
0x18000933a  call    cs:__imp_LocalAlloc
0x180009340  mov     r12, rax
0x180009343  test    rax, rax
0x180009346  jz      loc_1800095AF
0x18000934c  lea     r13, [rsi+rsi]
0x180009350  test    r14, r14
0x180009353  jz      short loc_180009363
0x180009355  mov     r8, r13; Size
0x180009358  mov     rdx, r14; Src
0x18000935b  mov     rcx, rax; void *
0x18000935e  call    memcpy_0
0x180009363  xor     eax, eax
0x180009365  lea     r14, asc_180061CE8; " "
0x18000936c  mov     [r12+r13], ax
0x180009371  test    rdi, rdi
0x180009374  jnz     loc_180009AEC
0x18000937a  cmp     [rsp+4C0h+var_480], 0
0x18000937f  jz      loc_180009476
0x180009385  lea     rax, [rbx-1]
0x180009389  mov     edx, 7FFFFFFEh
0x18000938e  cmp     rax, rdx
0x180009391  ja      loc_180009476
0x180009397  mov     rcx, rbx
0x18000939a  mov     rax, r12
0x18000939d  nop     dword ptr [rax]
0x1800093a0  cmp     word ptr [rax], 0
0x1800093a4  jz      short loc_1800093B5
0x1800093a6  add     rax, 2
0x1800093aa  sub     rcx, 1
0x1800093ae  jnz     short loc_1800093A0
0x1800093b0  xor     r8d, r8d
0x1800093b3  jmp     short loc_1800093BB
0x1800093b5  mov     r8, rbx
0x1800093b8  sub     r8, rcx
0x1800093bb  test    rcx, rcx
0x1800093be  jz      short loc_180009404
0x1800093c0  mov     rax, rbx
0x1800093c3  mov     rcx, rdx
0x1800093c6  sub     rax, r8
0x1800093c9  lea     r8, [r12+r8*2]
0x1800093cd  jz      short loc_1800093F4
0x1800093cf  nop
0x1800093d0  test    rcx, rcx
0x1800093d3  jz      short loc_1800093F4
0x1800093d5  movzx   r9d, word ptr [r14]
0x1800093d9  test    r9w, r9w
0x1800093dd  jz      short loc_1800093F4
0x1800093df  mov     [r8], r9w
0x1800093e3  add     r14, 2
0x1800093e7  add     r8, 2
0x1800093eb  dec     rcx
0x1800093ee  sub     rax, 1
0x1800093f2  jnz     short loc_1800093D0
0x1800093f4  test    rax, rax
0x1800093f7  lea     rcx, [r8-2]
0x1800093fb  cmovnz  rcx, r8
0x1800093ff  xor     eax, eax
0x180009401  mov     [rcx], ax
0x180009404  mov     rcx, rbx
0x180009407  mov     rax, r12
0x18000940a  nop     word ptr [rax+rax+00h]
0x180009410  cmp     word ptr [rax], 0
0x180009414  jz      short loc_180009420
0x180009416  add     rax, 2
0x18000941a  sub     rcx, 1
0x18000941e  jnz     short loc_180009410
0x180009420  xor     r8d, r8d
0x180009423  mov     rax, rbx
0x180009426  sub     rax, rcx
0x180009429  test    rcx, rcx
0x18000942c  cmovnz  r8, rax
0x180009430  jz      short loc_180009476
0x180009432  lea     rax, [rbp+3C0h+var_130]
0x180009439  lea     rcx, [r12+r8*2]
0x18000943d  sub     rbx, r8
0x180009440  jz      short loc_180009466
0x180009442  test    rdx, rdx
0x180009445  jz      short loc_180009466
0x180009447  movzx   r8d, word ptr [rax]
0x18000944b  test    r8w, r8w
0x18000944f  jz      short loc_180009466
0x180009451  mov     [rcx], r8w
0x180009455  add     rax, 2
0x180009459  add     rcx, 2
0x18000945d  dec     rdx
0x180009460  sub     rbx, 1
0x180009464  jnz     short loc_180009442
0x180009466  test    rbx, rbx
0x180009469  lea     rdx, [rcx-2]
0x18000946d  cmovnz  rdx, rcx
0x180009471  xor     ecx, ecx
0x180009473  mov     [rdx], cx
0x180009476  mov     rcx, [rsp+4C0h+Src]; hMem
0x18000947b  test    rcx, rcx
0x18000947e  jz      short loc_180009486
0x180009480  call    cs:__imp_LocalFree
0x180009486  mov     rax, r12
0x180009489  mov     rcx, [rbp+3C0h+var_40]
0x180009490  xor     rcx, rsp; StackCookie
0x180009493  call    __security_check_cookie
0x180009498  mov     rbx, [rsp+4C0h+arg_8]
0x1800094a0  add     rsp, 490h
0x1800094a7  pop     r15
0x1800094a9  pop     r14
0x1800094ab  pop     r13
0x1800094ad  pop     r12
0x1800094af  pop     rdi
0x1800094b0  pop     rsi
0x1800094b1  pop     rbp
0x1800094b2  retn
0x1800094b3  xor     edx, edx; Val
0x1800094b5  mov     qword ptr [rsp+4C0h+Buffer], r14
0x1800094ba  mov     r8d, 320h; Size
0x1800094c0  lea     rcx, [rsp+4C0h+var_450]; void *
0x1800094c5  call    memset_0
0x1800094ca  mov     rcx, [rsp+4C0h+var_468]
0x1800094cf  test    rcx, rcx
0x1800094d2  jnz     loc_180009779
0x1800094d8  xor     eax, eax
0x1800094da  mov     ecx, 1300h; dwFlags
0x1800094df  mov     [rsp+4C0h+Arguments], rax; Arguments
0x1800094e4  mov     r9d, 400h; dwLanguageId
0x1800094ea  lea     rax, [rsp+4C0h+Buffer]
0x1800094ef  mov     [rsp+4C0h+nSize], 1; nSize
0x1800094f7  mov     r8d, r13d; dwMessageId
0x1800094fa  mov     [rsp+4C0h+lpBuffer], rax; lpBuffer
0x1800094ff  xor     edx, edx; lpSource
0x180009501  call    cs:__imp_FormatMessageW
0x180009507  test    eax, eax
0x180009509  jz      loc_1800097B0
0x18000950f  mov     rax, qword ptr [rsp+4C0h+Buffer]
0x180009514  mov     rsi, rbx
0x180009517  nop     word ptr [rax+rax+00000000h]
0x180009520  inc     rsi
0x180009523  cmp     [rax+rsi*2], r14w
0x180009528  jnz     short loc_180009520
0x18000952a  cmp     rsi, 10000h
0x180009531  ja      loc_180009816
0x180009537  mov     [rsp+4C0h+Src], rax
0x18000953c  mov     ecx, esi
0x18000953e  test    esi, esi
0x180009540  jz      loc_180009679
0x180009546  test    rcx, rcx
0x180009549  jz      loc_18000982A
0x18000954f  mov     eax, r12d
0x180009552  or      eax, 1
0x180009555  test    rcx, rcx
0x180009558  cmovnz  eax, r12d
0x18000955c  mov     r12d, eax
0x18000955f  jnz     loc_1800092C9
0x180009565  mov     ecx, 0D2h; uID
0x18000956a  call    ?myLoadResourceString@@YAPEBGK@Z; myLoadResourceString(ulong)
0x18000956f  mov     r14, rax
0x180009572  test    rax, rax
0x180009575  jnz     loc_1800092C9
0x18000957b  lea     r14, aError_0; "Error"
0x180009582  jmp     loc_1800092C9
0x180009587  shr     r12d, 1
0x18000958a  lea     rcx, [rbp+3C0h+var_130]; unsigned __int16 *
0x180009591  and     r12b, 1
0x180009595  xor     r9d, r9d; bool
0x180009598  mov     r8d, r13d; int
0x18000959b  mov     byte ptr [rsp+4C0h+lpBuffer], r12b; bool
0x1800095a0  mov     edx, 73h ; 's'; unsigned __int64
0x1800095a5  call    ?myHResultToStringInternal@@YAPEBGPEAG_KJ_N2@Z; myHResultToStringInternal(ushort *,unsigned __int64,long,bool,bool)
0x1800095aa  jmp     loc_1800092E2
0x1800095af  xor     r9d, r9d; int
0x1800095b2  mov     edx, 5980334h; unsigned int
0x1800095b7  xor     ecx, ecx; unsigned __int16 *
0x1800095b9  mov     r8d, 8007000Eh; int
0x1800095bf  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800095c4  jmp     loc_180009476
0x1800095c9  cmp     r13d, 80000002h
0x1800095d0  jz      loc_180009731
0x1800095d6  mov     eax, r13d
0x1800095d9  movzx   edx, r13w
0x1800095dd  and     eax, 0FFFF0000h
0x1800095e2  cmp     eax, 80070000h
0x1800095e7  jz      short loc_1800095EC
0x1800095e9  mov     edx, r13d
0x1800095ec  lea     eax, [rdx-64h]
0x1800095ef  cmp     eax, 195h
0x1800095f4  jbe     short loc_18000962E
0x1800095f6  lea     r15, [rsp+4C0h+var_470]
0x1800095fb  jmp     loc_1800092B3
0x180009600  mov     ecx, 0Ah
0x180009605  mov     edx, 0Dh
0x18000960a  movzx   eax, word ptr [r14+rsi*2-2]
0x180009610  cmp     cx, ax
0x180009613  jnz     short loc_180009624
0x180009615  dec     rsi
0x180009618  cmp     rsi, 1
0x18000961c  jb      loc_180009315
0x180009622  jmp     short loc_18000960A
0x180009624  cmp     dx, ax
0x180009627  jz      short loc_180009615
0x180009629  jmp     loc_180009315
0x18000962e  lea     rcx, off_18003C000; "HTTP_STATUS_CONTINUE"
0x180009635  lea     rax, ??_7error_category@std@@6B@; const std::error_category::`vftable'
0x18000963c  nop     dword ptr [rax+00h]
0x180009640  cmp     rcx, rax
0x180009643  jnb     short loc_1800095F6
0x180009645  cmp     edx, [rcx+8]
0x180009648  jz      loc_18000973B
0x18000964e  add     rcx, 10h
0x180009652  jmp     short loc_180009640
0x180009654  mov     r9d, esi; int
0x180009657  mov     r8d, r13d; int
0x18000965a  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000965f  mov     rcx, qword ptr [rsp+4C0h+Buffer]; hMem
0x180009664  test    rcx, rcx
0x180009667  jnz     short loc_1800096C5
0x180009669  mov     ecx, r13d; dwErrCode
0x18000966c  call    cs:__imp_SetLastError
0x180009672  mov     r13d, [rsp+4C0h+var_480]
0x180009677  xor     ecx, ecx
0x180009679  mov     eax, r13d
0x18000967c  and     eax, 0FFFF0000h
0x180009681  cmp     eax, 0C06D0000h
0x180009686  jnz     loc_180009546
0x18000968c  lea     rax, [rsp+4C0h+Src]
0x180009691  movzx   edx, r13w; dwMessageId
0x180009695  mov     [rsp+4C0h+var_488], rax; unsigned __int16 **
0x18000969a  xor     r9d, r9d; bool
0x18000969d  mov     eax, [rsp+4C0h+var_47C]
0x1800096a1  mov     r8d, edx; int
0x1800096a4  mov     dword ptr [rsp+4C0h+Arguments], eax; unsigned int
0x1800096a8  xor     ecx, ecx; lpModuleName
0x1800096aa  mov     rax, [rsp+4C0h+var_468]
0x1800096af  mov     qword ptr [rsp+4C0h+nSize], rax; unsigned __int16 **
0x1800096b4  mov     byte ptr [rsp+4C0h+lpBuffer], 1; bool
0x1800096b9  call    ?errFormatMessage@@YAKPEBGJJ_N1PEAPEBGKPEAPEAG@Z; errFormatMessage(ushort const *,long,long,bool,bool,ushort const * *,ulong,ushort * *)
0x1800096be  mov     ecx, eax
0x1800096c0  jmp     loc_180009546
  ... truncated ...
```
