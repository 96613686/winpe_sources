# PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)

- ea: `0x18000f040`
- end: `0x18000f6a9`
- name: `?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z`
- size: `1641`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *, enum PATHCCH_OPTIONS)`
- caller_count: `9`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x1800068b8`
- `0x18000741c`
- `0x180007cd0`
- `0x1800088dc`
- `0x18000a1e0`
- `0x18000da5c`
- `0x18000fc8c`
- `0x180017608`
- `0x180017898`

## callees

- `0x180005424`
- `0x18000ef58`
- `0x18000f040`
- `0x18000f81c`
- `0x18000f960`
- `0x18000f9b8`
- `0x18000fa70`
- `0x18000ff24`
- `0x180018434`
- `0x180019010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000f1a1`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000f1d0`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000f1a1`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000f1d0`
- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x18000f2a1`
- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x18000f2a1`

## pseudocode

```c
__int64 __fastcall PathCchCanonicalizeEx(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        enum PATHCCH_OPTIONS a4)
{
  __int64 result; // rax
  int v8; // r15d
  char v9; // cl
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // r13
  char v12; // cl
  __int64 (__fastcall *v13)(); // rax
  wchar_t *v14; // rdx
  const unsigned __int16 *v15; // r14
  int v16; // eax
  const unsigned __int16 *v17; // r8
  unsigned __int16 *v18; // rbx
  __int64 v19; // rcx
  char v20; // al
  __int64 v21; // rcx
  char v22; // al
  unsigned __int16 *v23; // rcx
  unsigned __int64 v24; // rdx
  int v25; // eax
  unsigned __int64 v26; // r12
  wchar_t *v27; // rax
  __int64 (__fastcall *v28)(); // r13
  const unsigned __int16 *v29; // rbx
  unsigned __int16 v30; // ax
  unsigned __int16 *v31; // rbx
  int v32; // eax
  unsigned __int16 *v33; // rbx
  unsigned __int16 *v34; // rcx
  unsigned __int16 *v35; // rax
  __int64 v36; // rax
  unsigned __int16 *v37; // rbx
  const unsigned __int16 *v38; // r8
  unsigned __int64 v39; // rdx
  unsigned __int16 *v40; // rcx
  unsigned int v41; // [rsp+28h] [rbp-51h]
  unsigned int v42; // [rsp+30h] [rbp-49h]
  char v43; // [rsp+40h] [rbp-39h]
  char v44; // [rsp+44h] [rbp-35h]
  unsigned __int16 *v45; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int64 v46; // [rsp+50h] [rbp-29h] BYREF
  __int64 (__fastcall *v47)(); // [rsp+58h] [rbp-21h]
  const unsigned __int16 *v48; // [rsp+60h] [rbp-19h]
  __int64 v49; // [rsp+68h] [rbp-11h]
  int v50; // [rsp+70h] [rbp-9h]
  int v51; // [rsp+74h] [rbp-5h]
  int IsUnc2; // [rsp+78h] [rbp-1h]
  wchar_t *Control; // [rsp+80h] [rbp+7h]
  wchar_t *v54; // [rsp+88h] [rbp+Fh]
  PATHCCH_OPTIONS v55; // [rsp+F8h] [rbp+7Fh] BYREF

  v55 = a4;
  result = StringCchCopyW(a1, a2, &dword_18001EDA4);
  v8 = result;
  if ( (int)result < 0 )
    return result;
  if ( a2 > 0x8000 || !AreOptionsValidAndOptInLongPathAwareProcess(&v55) )
    return 2147942487LL;
  v9 = v55;
  if ( a2 <= 0x104 )
    v9 = v55 & 0xF8;
  v44 = v9;
  v45 = 0;
  v50 = v9 & 0x11;
  v49 = 0;
  v10 = v50 != 0 ? 0x8000LL : 260LL;
  if ( a2 < v10 )
    v10 = a2;
  v46 = v10;
  v11 = v10;
  if ( (v9 & 0x40) != 0 )
  {
    v12 = 1;
    v13 = IsBackOrForwardSlash;
  }
  else
  {
    v12 = 0;
    v13 = IsBackslash;
  }
  v43 = v12;
  v47 = v13;
  v14 = L"\\/";
  v48 = 0;
  if ( !v12 )
    v14 = (wchar_t *)L"\\";
  Control = v14;
  IsUnc2 = PathIsUnc2(a3);
  if ( IsUnc2 )
  {
    v15 = v48;
    if ( (v44 & 5) != 5 && (v44 & 0x10) == 0 )
    {
      v16 = StringCchCopyExW(a1, v10, L"\\\\", &v45, &v46, v41);
LABEL_31:
      v18 = v45;
      v8 = v16;
      v11 = v46;
LABEL_32:
      v22 = v44;
      goto LABEL_33;
    }
    v49 = 6;
    v17 = L"\\\\?\\UNC\\";
LABEL_30:
    v16 = StringCchCopyExW(a1, v10, v17, &v45, &v46, v41);
    goto LABEL_31;
  }
  v18 = a1;
  v45 = a1;
  v15 = a3;
  if ( !wcsncmp_0(a3, L"\\\\?\\", 4u) )
  {
    v19 = a3[4];
    v48 = a3 + 4;
    if ( (unsigned int)_o_iswalpha(v19) && a3[5] == 58 )
    {
      v20 = 1;
      v15 = a3 + 4;
    }
    else
    {
      v20 = 0;
    }
    if ( !v20 )
      goto LABEL_32;
  }
  else
  {
    v21 = *a3;
    v48 = a3;
    if ( !(unsigned int)_o_iswalpha(v21) || a3[1] != 58 )
      goto LABEL_32;
  }
  if ( (v44 & 5) == 5 || (v22 = v44, (v44 & 0x10) != 0) )
  {
    v49 = 4;
    v17 = L"\\\\?\\";
    goto LABEL_30;
  }
LABEL_33:
  v51 = v22 & 5;
  if ( v51 == 5 && v49 && v10 <= v49 + 260 )
  {
    v49 = 0;
    v15 = a3;
    v18 = a1;
    v23 = a1;
    if ( v10 > 0x104 )
      v10 = 260;
    v11 = v10;
    v46 = v10;
    v24 = v10;
    goto LABEL_39;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v26 = -1;
        if ( v8 < 0 || !*v15 )
          goto LABEL_95;
        v27 = wcspbrk(v15, Control);
        v54 = v27;
        if ( v27 )
        {
          v26 = v27 - v15;
        }
        else
        {
          do
            ++v26;
          while ( v15[v26] );
        }
        if ( v26 > 0x100 && !v50 || v26 >= 0x8000 )
        {
          v8 = -2147024690;
          goto LABEL_94;
        }
        if ( v26 != 1 )
          break;
        if ( *v15 != 46 )
          goto LABEL_77;
        if ( v27 )
          goto LABEL_52;
        ++v15;
        if ( v18 > a1 && !PathCchIsRoot(a1) )
        {
          --v18;
          ++v11;
          v23 = v18;
          v46 = v11;
          v24 = v11;
LABEL_39:
          v45 = v18;
          v25 = StringCchCopyW(v23, v24, &dword_18001EDA4);
LABEL_40:
          v8 = v25;
          continue;
        }
      }
      if ( v26 != 2 )
        break;
      if ( *v15 != 46 || v15[1] != 46 )
      {
LABEL_77:
        v8 = StringCchCopyNExW(v18, v11, v15, v26, &v45, &v46, v42);
LABEL_78:
        v28 = v47;
        goto LABEL_79;
      }
      if ( v18 > a1 )
      {
        if ( !PathCchIsRoot(a1) )
        {
          if ( a1 >= --v18 )
            goto LABEL_64;
          while ( *--v18 != 92 )
          {
            if ( a1 >= v18 )
              goto LABEL_64;
          }
          v45 = v18;
          if ( v18 )
          {
            v11 = v10 - (v18 - a1);
          }
          else
          {
LABEL_64:
            v18 = a1;
            v11 = v10;
            v45 = a1;
          }
          v46 = v11;
          v25 = StringCchCopyW(v18, v11, &dword_18001EDA4);
          v15 += 2;
          goto LABEL_40;
        }
        v27 = v54;
      }
      if ( v27 )
LABEL_52:
        v15 = v27 + 1;
      else
        v15 += 2;
    }
    if ( v26 )
      goto LABEL_77;
    ++v15;
    v8 = StringCchCopyNExW(v18, v11, L"\\", 1u, &v45, &v46, v42);
    if ( v15 <= v48 )
      goto LABEL_78;
    v28 = v47;
    if ( v43 )
    {
      v29 = v15 + 1;
      while ( ((unsigned __int8 (__fastcall *)(_QWORD))v28)(*v15) )
        v15 = v29++;
    }
LABEL_79:
    if ( v8 != -2147024774 || v26 != 1 || !((unsigned __int8 (__fastcall *)(_QWORD))v28)(*v15) )
    {
      v11 = v46;
      goto LABEL_90;
    }
    v30 = v15[1];
    if ( !v30 || v30 == 46 && !v15[2] )
      break;
    v11 = v46;
    if ( v46 == 1 && v30 == 46 && v15[2] == 46 )
    {
      v31 = v45;
      v11 = 0;
      v46 = 0;
      v8 = 0;
      *v45 = 0;
      v18 = v31 + 1;
      v45 = v18;
      goto LABEL_91;
    }
LABEL_90:
    v18 = v45;
LABEL_91:
    v15 += v26;
  }
  v11 = v46;
  v8 = 0;
  v18 = v45;
LABEL_94:
  v26 = -1;
LABEL_95:
  if ( (v44 & 0x20) != 0 && v18 > a1 && !((unsigned __int8 (__fastcall *)(_QWORD))v47)(*(v18 - 1)) )
  {
    v32 = StringCchCopyNExW(v18, v11, L"\\", 1u, &v45, &v46, v42);
    v18 = v45;
    v8 = v32;
  }
  if ( v8 < 0 )
  {
    StringCchCopyW(a1, v10, &dword_18001EDA4);
    if ( v8 != -2147024774 )
      return (unsigned int)v8;
    if ( (v44 & 1) != 0 )
    {
      if ( v10 != 0x8000 )
        return (unsigned int)v8;
    }
    else if ( v10 != 260 )
    {
      return (unsigned int)v8;
    }
    return (unsigned int)-2147024690;
  }
  if ( (v44 & 0x18) == 0 )
  {
    if ( v18 > a1 )
    {
      v33 = v18 - 1;
      if ( *v33 == 46 )
      {
        v34 = v33;
        v35 = v33;
        while ( v34 != a1 )
        {
          v34 = v35 - 1;
          if ( *(v35 - 1) != 42 )
          {
            *v33 = 0;
            --v35;
            v33 = v34;
            if ( *v34 == 46 )
              continue;
          }
          goto LABEL_116;
        }
        *v33 = 0;
      }
    }
LABEL_116:
    v36 = -1;
    do
      ++v36;
    while ( a1[v36] );
    v37 = &a1[v36];
    if ( v37 >= a1 + 7 && StrIsEqualCaseInsensitive(v37 - 7, L"::$DATA", 7) )
      *(v37 - 7) = 0;
  }
  if ( v49 && v51 == 5 )
  {
    do
      ++v26;
    while ( a1[v49 + v26] );
    if ( v26 < 0x104 )
    {
      if ( IsUnc2 )
      {
        v38 = a1 + 8;
        v39 = v10 - 2;
        v40 = a1 + 2;
      }
      else
      {
        v38 = a1 + 4;
        v39 = v10;
        v40 = a1;
      }
      StringCchCopyW(v40, v39, v38);
    }
  }
  if ( v10 > 1 && !*a1 )
    *(_DWORD *)a1 = 92;
  if ( v10 > 3 && a1[1] == 58 && !a1[2] )
    *((_DWORD *)a1 + 1) = 92;
  return 0;
}

```

## disassembly

```asm
0x18000f040  mov     [rsp-8+arg_18], r9d
0x18000f045  push    rbp
0x18000f046  push    rbx
0x18000f047  push    rsi
0x18000f048  push    rdi
0x18000f049  push    r12
0x18000f04b  push    r13
0x18000f04d  push    r14
0x18000f04f  push    r15
0x18000f051  lea     rbp, [rsp-1Fh]
0x18000f056  sub     rsp, 98h
0x18000f05d  mov     r12, r8
0x18000f060  mov     rbx, rdx
0x18000f063  lea     r8, dword_18001EDA4; unsigned __int16 *
0x18000f06a  mov     rdi, rcx
0x18000f06d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f072  xor     r14d, r14d
0x18000f075  mov     r15d, eax
0x18000f078  test    eax, eax
0x18000f07a  js      loc_18000F695
0x18000f080  cmp     rbx, 8000h
0x18000f087  ja      loc_18000F690
0x18000f08d  lea     rcx, [rbp+57h+arg_18]; enum PATHCCH_OPTIONS *
0x18000f091  call    ?AreOptionsValidAndOptInLongPathAwareProcess@@YA_NAEAW4PATHCCH_OPTIONS@@@Z; AreOptionsValidAndOptInLongPathAwareProcess(PATHCCH_OPTIONS &)
0x18000f096  test    al, al
0x18000f098  jz      loc_18000F690
0x18000f09e  mov     ecx, [rbp+57h+arg_18]
0x18000f0a1  mov     edx, 104h
0x18000f0a6  cmp     rbx, rdx
0x18000f0a9  ja      short loc_18000F0AE
0x18000f0ab  and     ecx, 0FFFFFFF8h
0x18000f0ae  mov     eax, ecx
0x18000f0b0  mov     [rbp+57h+var_8C], ecx
0x18000f0b3  and     eax, 11h
0x18000f0b6  mov     [rbp+57h+var_88], r14
0x18000f0ba  mov     [rbp+57h+var_60], eax
0x18000f0bd  neg     eax
0x18000f0bf  mov     [rbp+57h+var_68], r14
0x18000f0c3  sbb     rsi, rsi
0x18000f0c6  and     esi, 7EFCh
0x18000f0cc  add     rsi, rdx
0x18000f0cf  cmp     rbx, rsi
0x18000f0d2  cmovb   rsi, rbx
0x18000f0d6  mov     [rbp+57h+var_80], rsi
0x18000f0da  mov     r13, rsi
0x18000f0dd  test    cl, 40h
0x18000f0e0  jz      short loc_18000F0ED
0x18000f0e2  mov     cl, 1
0x18000f0e4  lea     rax, IsBackOrForwardSlash
0x18000f0eb  jmp     short loc_18000F0F7
0x18000f0ed  mov     cl, r14b
0x18000f0f0  lea     rax, IsBackslash
0x18000f0f7  test    cl, cl
0x18000f0f9  mov     [rbp+57h+var_90], cl
0x18000f0fc  lea     r8, Delimiter; "\\"
0x18000f103  mov     [rbp+57h+var_78], rax
0x18000f107  lea     rdx, asc_18001ED9C; "\\/"
0x18000f10e  mov     [rbp+57h+var_70], r14
0x18000f112  cmovz   rdx, r8
0x18000f116  mov     rcx, r12; unsigned __int16 *
0x18000f119  mov     [rbp+57h+Control], rdx
0x18000f11d  mov     r8, rax
0x18000f120  lea     rdx, [rbp+57h+var_70]
0x18000f124  call    PathIsUnc2
0x18000f129  mov     [rbp+57h+var_58], eax
0x18000f12c  test    eax, eax
0x18000f12e  jz      short loc_18000F172
0x18000f130  mov     eax, [rbp+57h+var_8C]
0x18000f133  mov     ecx, eax
0x18000f135  mov     r14, [rbp+57h+var_70]
0x18000f139  and     ecx, 5
0x18000f13c  mov     [rbp+57h+var_70], r14
0x18000f140  cmp     cl, 5
0x18000f143  jz      short loc_18000F15E
0x18000f145  test    al, 10h
0x18000f147  jnz     short loc_18000F15E
0x18000f149  lea     rax, [rbp+57h+var_80]
0x18000f14d  mov     [rsp+0D0h+var_B0], rax
0x18000f152  lea     r8, asc_18001EDFC; "\\\\"
0x18000f159  jmp     loc_18000F20C
0x18000f15e  mov     [rbp+57h+var_68], 6
0x18000f166  lea     r8, aUnc; "\\\\?\\UNC\\"
0x18000f16d  jmp     loc_18000F203
0x18000f172  mov     rbx, rdi
0x18000f175  lea     rdx, asc_18001EE88; "\\\\?\\"
0x18000f17c  mov     r8d, 4; MaxCount
0x18000f182  mov     [rbp+57h+var_88], rbx
0x18000f186  mov     rcx, r12; String1
0x18000f189  mov     r14, r12
0x18000f18c  call    wcsncmp_0
0x18000f191  test    eax, eax
0x18000f193  jnz     short loc_18000F1C7
0x18000f195  lea     rax, [r12+8]
0x18000f19a  movzx   ecx, word ptr [rax]
0x18000f19d  mov     [rbp+57h+var_70], rax
0x18000f1a1  call    cs:__imp__o_iswalpha
0x18000f1a7  xor     ecx, ecx
0x18000f1a9  test    eax, eax
0x18000f1ab  jz      short loc_18000F1BF
0x18000f1ad  cmp     word ptr [r12+0Ah], 3Ah ; ':'
0x18000f1b4  jnz     short loc_18000F1BF
0x18000f1b6  mov     al, 1
0x18000f1b8  lea     r14, [r12+8]
0x18000f1bd  jmp     short loc_18000F1C1
0x18000f1bf  mov     al, cl
0x18000f1c1  test    al, al
0x18000f1c3  jz      short loc_18000F226
0x18000f1c5  jmp     short loc_18000F1E3
0x18000f1c7  movzx   ecx, word ptr [r12]
0x18000f1cc  mov     [rbp+57h+var_70], r12
0x18000f1d0  call    cs:__imp__o_iswalpha
0x18000f1d6  test    eax, eax
0x18000f1d8  jz      short loc_18000F226
0x18000f1da  cmp     word ptr [r12+2], 3Ah ; ':'
0x18000f1e1  jnz     short loc_18000F226
0x18000f1e3  mov     eax, [rbp+57h+var_8C]
0x18000f1e6  and     eax, 5
0x18000f1e9  cmp     al, 5
0x18000f1eb  jz      short loc_18000F1F4
0x18000f1ed  mov     eax, [rbp+57h+var_8C]
0x18000f1f0  test    al, 10h
0x18000f1f2  jz      short loc_18000F229
0x18000f1f4  mov     [rbp+57h+var_68], 4
0x18000f1fc  lea     r8, asc_18001EE88; "\\\\?\\"
0x18000f203  lea     rcx, [rbp+57h+var_80]
0x18000f207  mov     [rsp+0D0h+var_B0], rcx; unsigned __int64 *
0x18000f20c  lea     r9, [rbp+57h+var_88]; unsigned __int16 **
0x18000f210  mov     rdx, rsi; unsigned __int64
0x18000f213  mov     rcx, rdi; unsigned __int16 *
0x18000f216  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18000f21b  mov     rbx, [rbp+57h+var_88]
0x18000f21f  mov     r15d, eax
0x18000f222  mov     r13, [rbp+57h+var_80]
0x18000f226  mov     eax, [rbp+57h+var_8C]
0x18000f229  and     eax, 5
0x18000f22c  xor     ecx, ecx
0x18000f22e  mov     [rbp+57h+var_5C], eax
0x18000f231  cmp     eax, 5
0x18000f234  jnz     short loc_18000F283
0x18000f236  mov     r11, [rbp+57h+var_68]
0x18000f23a  test    r11, r11
0x18000f23d  jz      short loc_18000F283
0x18000f23f  lea     rax, [r11+104h]
0x18000f246  cmp     rsi, rax
0x18000f249  ja      short loc_18000F283
0x18000f24b  mov     eax, 104h
0x18000f250  mov     [rbp+57h+var_68], rcx
0x18000f254  cmp     rsi, rax
0x18000f257  mov     r14, r12
0x18000f25a  mov     rbx, rdi
0x18000f25d  mov     rcx, rdi; unsigned __int16 *
0x18000f260  cmova   rsi, rax
0x18000f264  mov     r13, rsi
0x18000f267  mov     [rbp+57h+var_80], rsi
0x18000f26b  mov     rdx, rsi; unsigned __int64
0x18000f26e  lea     r8, dword_18001EDA4; unsigned __int16 *
0x18000f275  mov     [rbp+57h+var_88], rbx
0x18000f279  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f27e  mov     r15d, eax
0x18000f281  xor     ecx, ecx
0x18000f283  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000f287  test    r15d, r15d
0x18000f28a  js      loc_18000F501
0x18000f290  cmp     [r14], cx
0x18000f294  jz      loc_18000F501
0x18000f29a  mov     rdx, [rbp+57h+Control]; Control
0x18000f29e  mov     rcx, r14; String
0x18000f2a1  call    cs:__imp_wcspbrk
0x18000f2a7  xor     ecx, ecx
0x18000f2a9  mov     [rbp+57h+var_48], rax
0x18000f2ad  test    rax, rax
0x18000f2b0  jz      short loc_18000F2BD
0x18000f2b2  mov     r12, rax
0x18000f2b5  sub     r12, r14
0x18000f2b8  sar     r12, 1
0x18000f2bb  jmp     short loc_18000F2C7
0x18000f2bd  inc     r12
0x18000f2c0  cmp     [r14+r12*2], cx
0x18000f2c5  jnz     short loc_18000F2BD
0x18000f2c7  cmp     r12, 100h
0x18000f2ce  jbe     short loc_18000F2D9
0x18000f2d0  cmp     [rbp+57h+var_60], ecx
0x18000f2d3  jz      loc_18000F4F7
0x18000f2d9  cmp     r12, 8000h
0x18000f2e0  jnb     loc_18000F4F7
0x18000f2e6  cmp     r12, 1
0x18000f2ea  jnz     short loc_18000F337
0x18000f2ec  cmp     word ptr [r14], 2Eh ; '.'
0x18000f2f1  jnz     loc_18000F443
0x18000f2f7  test    rax, rax
0x18000f2fa  jz      short loc_18000F302
0x18000f2fc  lea     r14, [rax+2]
0x18000f300  jmp     short loc_18000F283
0x18000f302  add     r14, 2
0x18000f306  cmp     rbx, rdi
0x18000f309  jbe     loc_18000F283
0x18000f30f  mov     rcx, rdi; pszPath
0x18000f312  call    PathCchIsRoot
0x18000f317  xor     ecx, ecx
0x18000f319  test    eax, eax
0x18000f31b  jnz     loc_18000F283
0x18000f321  sub     rbx, 2
0x18000f325  inc     r13
0x18000f328  mov     rcx, rbx
0x18000f32b  mov     [rbp+57h+var_80], r13
0x18000f32f  mov     rdx, r13
0x18000f332  jmp     loc_18000F26E
0x18000f337  cmp     r12, 2
0x18000f33b  jnz     loc_18000F3DE
0x18000f341  cmp     word ptr [r14], 2Eh ; '.'
0x18000f346  jnz     loc_18000F443
0x18000f34c  cmp     word ptr [r14+2], 2Eh ; '.'
0x18000f352  jnz     loc_18000F443
0x18000f358  cmp     rbx, rdi
0x18000f35b  jbe     short loc_18000F3CC
0x18000f35d  mov     rcx, rdi; pszPath
0x18000f360  call    PathCchIsRoot
0x18000f365  xor     ecx, ecx
0x18000f367  test    eax, eax
0x18000f369  jnz     short loc_18000F3C8
0x18000f36b  add     rbx, 0FFFFFFFFFFFFFFFEh
0x18000f36f  cmp     rdi, rbx
0x18000f372  jnb     short loc_18000F385
0x18000f374  lea     eax, [rcx+5Ch]
0x18000f377  sub     rbx, 2
0x18000f37b  cmp     [rbx], ax
0x18000f37e  jz      short loc_18000F3AE
0x18000f380  cmp     rdi, rbx
0x18000f383  jb      short loc_18000F377
0x18000f385  mov     rbx, rdi
0x18000f388  mov     r13, rsi
0x18000f38b  mov     [rbp+57h+var_88], rbx
0x18000f38f  lea     r8, dword_18001EDA4; unsigned __int16 *
0x18000f396  mov     [rbp+57h+var_80], r13
0x18000f39a  mov     rdx, r13; unsigned __int64
0x18000f39d  mov     rcx, rbx; unsigned __int16 *
0x18000f3a0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f3a5  add     r14, 4
0x18000f3a9  jmp     loc_18000F27E
0x18000f3ae  mov     [rbp+57h+var_88], rbx
0x18000f3b2  test    rbx, rbx
0x18000f3b5  jz      short loc_18000F385
0x18000f3b7  mov     rax, rbx
0x18000f3ba  mov     r13, rsi
0x18000f3bd  sub     rax, rdi
0x18000f3c0  sar     rax, 1
0x18000f3c3  sub     r13, rax
0x18000f3c6  jmp     short loc_18000F38F
0x18000f3c8  mov     rax, [rbp+57h+var_48]
0x18000f3cc  test    rax, rax
0x18000f3cf  jnz     loc_18000F2FC
0x18000f3d5  add     r14, 4
0x18000f3d9  jmp     loc_18000F283
0x18000f3de  test    r12, r12
0x18000f3e1  jnz     short loc_18000F443
0x18000f3e3  lea     rax, [rbp+57h+var_80]
0x18000f3e7  mov     rdx, r13; unsigned __int64
0x18000f3ea  mov     [rsp+0D0h+var_A8], rax; unsigned __int64 *
0x18000f3ef  lea     r9d, [r12+1]; unsigned __int64
0x18000f3f4  lea     rax, [rbp+57h+var_88]
0x18000f3f8  mov     rcx, rbx; unsigned __int16 *
0x18000f3fb  lea     r8, Delimiter; "\\"
0x18000f402  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 **
0x18000f407  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18000f40c  xor     ecx, ecx
0x18000f40e  add     r14, 2
0x18000f412  mov     r15d, eax
0x18000f415  cmp     r14, [rbp+57h+var_70]
0x18000f419  jbe     short loc_18000F46B
0x18000f41b  mov     r13, [rbp+57h+var_78]
0x18000f41f  cmp     [rbp+57h+var_90], cl
0x18000f422  jz      short loc_18000F46F
0x18000f424  lea     rbx, [r14+2]
0x18000f428  movzx   ecx, word ptr [r14]
0x18000f42c  mov     rax, r13
0x18000f42f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f434  xor     ecx, ecx
0x18000f436  test    al, al
0x18000f438  jz      short loc_18000F46F
0x18000f43a  mov     r14, rbx
0x18000f43d  add     rbx, 2
0x18000f441  jmp     short loc_18000F428
0x18000f443  lea     rax, [rbp+57h+var_80]
0x18000f447  mov     r9, r12; unsigned __int64
0x18000f44a  mov     [rsp+0D0h+var_A8], rax; unsigned __int64 *
0x18000f44f  mov     r8, r14; unsigned __int16 *
0x18000f452  lea     rax, [rbp+57h+var_88]
0x18000f456  mov     rdx, r13; unsigned __int64
0x18000f459  mov     rcx, rbx; unsigned __int16 *
0x18000f45c  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 **
0x18000f461  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18000f466  mov     r15d, eax
0x18000f469  xor     ecx, ecx
0x18000f46b  mov     r13, [rbp+57h+var_78]
0x18000f46f  cmp     r15d, 8007007Ah
0x18000f476  jnz     short loc_18000F4D9
0x18000f478  cmp     r12, 1
0x18000f47c  jnz     short loc_18000F4D9
0x18000f47e  movzx   ecx, word ptr [r14]
0x18000f482  mov     rax, r13
  ... truncated ...
```
