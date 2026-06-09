# PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)

- ea: `0x180095444`
- end: `0x180095ac0`
- name: `?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z`
- size: `1660`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, enum PATHCCH_OPTIONS)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path`

## callers

- `0x180095f20`

## callees

- `0x18004b43c`
- `0x180095308`
- `0x180095400`
- `0x180095428`
- `0x180095444`
- `0x180095ac8`
- `0x180095ba0`
- `0x180095bfc`
- `0x180095cac`
- `0x1800961b4`
- `0x180098010`

## import_xrefs

- `msvcrt!wcspbrk` at `0x1800955d0`
- `msvcrt!wcspbrk` at `0x1800955d0`
- `msvcrt!iswalpha` at `0x18009562a`
- `msvcrt!iswalpha` at `0x180095664`
- `msvcrt!iswalpha` at `0x18009562a`
- `msvcrt!iswalpha` at `0x180095664`

## pseudocode

```c
int __fastcall PathCchCanonicalizeEx(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3, enum PATHCCH_OPTIONS a4)
{
  int result; // eax
  int v7; // esi
  __int64 v8; // r15
  enum PATHCCH_OPTIONS v9; // ebx
  char v10; // cl
  __int64 (__fastcall *v11)(); // rax
  wchar_t *v12; // rdx
  wchar_t *v13; // r14
  const unsigned __int16 *v14; // r8
  int v15; // eax
  unsigned __int16 *v16; // rbx
  __int64 v17; // r11
  char v18; // r13
  unsigned __int64 i; // r12
  wchar_t *v20; // rax
  wchar_t *v21; // r13
  bool v22; // r13
  wint_t v23; // cx
  int v24; // eax
  wint_t v25; // cx
  int v26; // eax
  int v27; // eax
  BOOL v28; // eax
  BOOL IsRoot; // eax
  int v30; // eax
  __int64 (__fastcall *v31)(); // r13
  wchar_t *j; // rbx
  char v33; // al
  char v34; // al
  wchar_t v35; // ax
  unsigned __int16 *v36; // rbx
  int v37; // eax
  unsigned __int16 *v38; // rbx
  unsigned __int16 *v39; // rcx
  unsigned __int16 *v40; // rax
  __int64 v41; // rax
  unsigned __int16 *v42; // rbx
  const unsigned __int16 *v43; // r8
  unsigned __int16 *v44; // rcx
  unsigned __int64 v45; // rdx
  unsigned int v46; // [rsp+30h] [rbp-41h]
  unsigned int v47; // [rsp+38h] [rbp-39h]
  unsigned __int16 *v48; // [rsp+48h] [rbp-29h] BYREF
  unsigned __int64 v49; // [rsp+50h] [rbp-21h] BYREF
  __int64 (__fastcall *v50)(); // [rsp+58h] [rbp-19h]
  wchar_t *String; // [rsp+60h] [rbp-11h]
  enum PATHCCH_OPTIONS v52; // [rsp+68h] [rbp-9h] BYREF
  __int64 v53; // [rsp+70h] [rbp-1h]
  __int32 v54; // [rsp+78h] [rbp+7h]
  int v55; // [rsp+7Ch] [rbp+Bh]
  int IsUnc2; // [rsp+80h] [rbp+Fh]
  wchar_t *Control; // [rsp+88h] [rbp+17h]
  enum PATHCCH_OPTIONS v58; // [rsp+E0h] [rbp+6Fh]
  char v59; // [rsp+F0h] [rbp+7Fh]

  v52 = PATHCCH_NONE;
  result = StringCchCopyW(a1, 0x104u, &::String);
  v7 = result;
  if ( result < 0 )
    return result;
  if ( !AreOptionsValidAndOptInLongPathAwareProcess(&v52) )
    return -2147024809;
  v8 = 260;
  v9 = v52 & 0xFFFFFFF8;
  v49 = 260;
  v58 = v52 & 0xFFFFFFF8;
  v48 = 0;
  v54 = v52 & 0x10;
  v53 = 0;
  if ( (v52 & 0x40) != 0 )
  {
    v10 = 1;
    v11 = IsBackOrForwardSlash;
  }
  else
  {
    v10 = 0;
    v11 = IsBackslash;
  }
  v59 = v10;
  v50 = v11;
  v12 = L"\\/";
  String = 0;
  if ( !v10 )
    v12 = (wchar_t *)L"\\";
  Control = v12;
  IsUnc2 = PathIsUnc2(a3);
  if ( IsUnc2 )
  {
    v13 = String;
    if ( MayNeedExtendedLengthPrefix(v9) )
    {
      v53 = 6;
      v14 = L"\\\\?\\UNC\\";
    }
    else
    {
      v14 = L"\\\\";
    }
    v15 = StringCchCopyExW(a1, 0x104u, v14, &v48, &v49, v46);
    v8 = v49;
    v7 = v15;
    v16 = v48;
    v17 = 0;
    goto LABEL_13;
  }
  v16 = a1;
  v48 = a1;
  v13 = a3;
  v22 = IsExtendedLengthDosDevicePath(a3);
  if ( v22 )
  {
    v23 = a3[4];
    String = a3 + 4;
    v24 = iswalpha(v23);
    v17 = 0;
    if ( v24 && a3[5] == 58 )
      v13 = a3 + 4;
    else
      v22 = 0;
    if ( !v22 )
      goto LABEL_13;
  }
  else
  {
    v25 = *a3;
    String = a3;
    v26 = iswalpha(v25);
    v17 = 0;
    if ( !v26 || a3[1] != 58 )
    {
LABEL_13:
      v18 = v58;
      goto LABEL_14;
    }
  }
  v18 = v58;
  if ( MayNeedExtendedLengthPrefix(v58) )
  {
    v53 = 4;
    v27 = StringCchCopyExW(a1, 0x104u, L"\\\\?\\", &v48, &v49, v46);
    v8 = v49;
    v7 = v27;
    v16 = v48;
    v17 = 0;
  }
LABEL_14:
  v55 = v18 & 5;
  if ( v55 == 5 && v53 != v17 )
  {
    v53 = v17;
    v16 = a1;
    v49 = 260;
    v48 = a1;
    v8 = 260;
    v13 = a3;
    v7 = StringCchCopyW(a1, 0x104u, &::String);
  }
LABEL_17:
  for ( i = -1; ; i = -1 )
  {
    if ( v7 < 0 || *v13 == (_WORD)v17 )
      goto LABEL_83;
    v20 = wcspbrk(v13, Control);
    LOWORD(v17) = 0;
    v21 = v20;
    if ( v20 )
    {
      i = v20 - v13;
    }
    else
    {
      do
        ++i;
      while ( v13[i] );
    }
    if ( i > 0x100 && !v54 || i >= 0x8000 )
      break;
    if ( i != 1 )
    {
      if ( i != 2 )
      {
        if ( i )
        {
LABEL_66:
          v7 = StringCchCopyNExW(v16, v8, v13, i, &v48, &v49, v47);
          LOWORD(v17) = 0;
        }
        else
        {
          v30 = StringCchCopyNExW(v16, v8, L"\\", 1u, &v48, &v49, v47);
          LOWORD(v17) = 0;
          ++v13;
          v7 = v30;
          if ( v13 > String )
          {
            v31 = v50;
            if ( v59 )
            {
              for ( j = v13 + 1; ; ++j )
              {
                v33 = ((__int64 (__fastcall *)(_QWORD))v31)(*v13);
                LOWORD(v17) = 0;
                if ( !v33 )
                  break;
                v13 = j;
              }
            }
LABEL_68:
            if ( v7 == -2147024774
              && i == 1
              && (v34 = ((__int64 (__fastcall *)(_QWORD))v31)(*v13), LOWORD(v17) = 0, v34) )
            {
              v35 = v13[1];
              if ( !v35 || v35 == 46 && !v13[2] )
              {
                v8 = v49;
                v7 = 0;
                v16 = v48;
                i = -1;
                goto LABEL_84;
              }
              v8 = v49;
              if ( v49 == 1 && v35 == 46 && v13[2] == 46 )
              {
                v36 = v48;
                v8 = 0;
                v49 = 0;
                v7 = 0;
                *v48 = 0;
                v16 = v36 + 1;
                v48 = v16;
LABEL_80:
                v13 += i;
                goto LABEL_17;
              }
            }
            else
            {
              v8 = v49;
            }
            v16 = v48;
            goto LABEL_80;
          }
        }
        v31 = v50;
        goto LABEL_68;
      }
      if ( *v13 != 46 || v13[1] != 46 )
        goto LABEL_66;
      if ( v16 > a1 )
      {
        IsRoot = PathCchIsRoot(a1);
        LOWORD(v17) = 0;
        if ( !IsRoot )
        {
          --v16;
          while ( a1 < v16 )
          {
            if ( *--v16 == 92 )
            {
              v48 = v16;
              if ( v16 )
              {
                v8 = 260 - (v16 - a1);
                goto LABEL_56;
              }
              break;
            }
          }
          v16 = a1;
          v8 = 260;
          v48 = a1;
LABEL_56:
          v49 = v8;
          v7 = StringCchCopyW(v16, v8, &::String);
          goto LABEL_57;
        }
      }
      if ( !v21 )
      {
LABEL_57:
        v13 += 2;
        goto LABEL_17;
      }
      v13 = v21 + 1;
      goto LABEL_17;
    }
    if ( *v13 != 46 )
      goto LABEL_66;
    if ( v20 )
    {
      v13 = v20 + 1;
      goto LABEL_17;
    }
    ++v13;
    if ( v16 > a1 )
    {
      v28 = PathCchIsRoot(a1);
      LOWORD(v17) = 0;
      if ( !v28 )
      {
        --v16;
        ++v8;
        v48 = v16;
        v49 = v8;
        v7 = StringCchCopyW(v16, v8, &::String);
      }
    }
  }
  v7 = -2147024690;
  i = -1;
LABEL_83:
  v31 = v50;
LABEL_84:
  if ( (v58 & 0x20) != 0 && v16 > a1 && !((unsigned __int8 (__fastcall *)(_QWORD))v31)(*(v16 - 1)) )
  {
    v37 = StringCchCopyNExW(v16, v8, L"\\", 1u, &v48, &v49, v47);
    v16 = v48;
    v7 = v37;
  }
  if ( v7 >= 0 )
  {
    if ( (v58 & 0x18) == 0 )
    {
      if ( v16 > a1 )
      {
        v38 = v16 - 1;
        v39 = v38;
        v40 = v38;
        while ( *v38 == 46 )
        {
          if ( v39 == a1 )
          {
            *v38 = 0;
            break;
          }
          v39 = v40 - 1;
          if ( *(v40 - 1) == 42 )
            break;
          *v38 = 0;
          --v40;
          v38 = v39;
        }
      }
      v41 = -1;
      do
        ++v41;
      while ( a1[v41] );
      v42 = &a1[v41];
      if ( v42 >= a1 + 7 && StrIsEqualCaseInsensitive(v42 - 7, L"::$DATA", 7) )
        *(v42 - 7) = 0;
    }
    if ( v53 && v55 == 5 )
    {
      do
        ++i;
      while ( a1[v53 + i] );
      if ( i < 0x104 )
      {
        if ( IsUnc2 )
        {
          v43 = a1 + 8;
          v44 = a1 + 2;
          v45 = 258;
        }
        else
        {
          v43 = a1 + 4;
          v45 = 260;
          v44 = a1;
        }
        StringCchCopyW(v44, v45, v43);
      }
    }
    if ( !*a1 )
      *(_DWORD *)a1 = 92;
    if ( a1[1] == 58 && !a1[2] )
      *((_DWORD *)a1 + 1) = 92;
    return 0;
  }
  else
  {
    StringCchCopyW(a1, 0x104u, &::String);
    if ( v7 == -2147024774 && (v58 & 1) == 0 )
      return -2147024690;
    return v7;
  }
}

```

## disassembly

```asm
0x180095444  mov     rax, rsp
0x180095447  mov     [rax+8], rbx
0x18009544b  mov     [rax+20h], r9d
0x18009544f  mov     [rax+10h], rdx
0x180095453  push    rbp
0x180095454  push    rsi
0x180095455  push    rdi
0x180095456  push    r12
0x180095458  push    r13
0x18009545a  push    r14
0x18009545c  push    r15
0x18009545e  lea     rbp, [rax-5Fh]
0x180095462  sub     rsp, 90h
0x180095469  mov     r12, r8
0x18009546c  mov     r14d, 104h
0x180095472  xor     r13d, r13d
0x180095475  lea     r8, String; unsigned __int16 *
0x18009547c  mov     edx, r14d; unsigned __int64
0x18009547f  mov     [rbp+57h+var_60], r13d
0x180095483  mov     rdi, rcx
0x180095486  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009548b  mov     esi, eax
0x18009548d  test    eax, eax
0x18009548f  js      loc_180095AA4
0x180095495  lea     rcx, [rbp+57h+var_60]; enum PATHCCH_OPTIONS *
0x180095499  call    ?AreOptionsValidAndOptInLongPathAwareProcess@@YA_NAEAW4PATHCCH_OPTIONS@@@Z; AreOptionsValidAndOptInLongPathAwareProcess(PATHCCH_OPTIONS &)
0x18009549e  test    al, al
0x1800954a0  jnz     short loc_1800954AC
0x1800954a2  mov     eax, 80070057h
0x1800954a7  jmp     loc_180095AA4
0x1800954ac  mov     ebx, [rbp+57h+var_60]
0x1800954af  mov     r15, r14
0x1800954b2  and     ebx, 0FFFFFFF8h
0x1800954b5  mov     [rbp+57h+var_78], r14
0x1800954b9  mov     eax, ebx
0x1800954bb  mov     [rbp+57h+arg_8], ebx
0x1800954be  and     eax, 11h
0x1800954c1  mov     [rbp+57h+var_80], r13
0x1800954c5  mov     [rbp+57h+var_50], eax
0x1800954c8  mov     [rbp+57h+var_58], r13
0x1800954cc  test    bl, 40h
0x1800954cf  jz      short loc_1800954DC
0x1800954d1  mov     cl, 1
0x1800954d3  lea     rax, IsBackOrForwardSlash
0x1800954da  jmp     short loc_1800954E6
0x1800954dc  mov     cl, r13b
0x1800954df  lea     rax, IsBackslash
0x1800954e6  test    cl, cl
0x1800954e8  mov     [rbp+57h+arg_18], cl
0x1800954eb  lea     r8, SubBlock; "\\"
0x1800954f2  mov     [rbp+57h+var_70], rax
0x1800954f6  lea     rdx, asc_1800AA880; "\\/"
0x1800954fd  mov     [rbp+57h+String], r13
0x180095501  cmovz   rdx, r8
0x180095505  mov     rcx, r12; unsigned __int16 *
0x180095508  mov     [rbp+57h+Control], rdx
0x18009550c  mov     r8, rax
0x18009550f  lea     rdx, [rbp+57h+String]
0x180095513  call    PathIsUnc2
0x180095518  mov     [rbp+57h+var_48], eax
0x18009551b  test    eax, eax
0x18009551d  jz      loc_180095605
0x180095523  mov     r14, [rbp+57h+String]
0x180095527  mov     ecx, ebx; enum PATHCCH_OPTIONS
0x180095529  mov     [rbp+57h+String], r14
0x18009552d  call    ?MayNeedExtendedLengthPrefix@@YA_NW4PATHCCH_OPTIONS@@@Z; MayNeedExtendedLengthPrefix(PATHCCH_OPTIONS)
0x180095532  test    al, al
0x180095534  lea     r9, [rbp+57h+var_80]; unsigned __int16 **
0x180095538  lea     rax, [rbp+57h+var_78]
0x18009553c  mov     rdx, r15; unsigned __int64
0x18009553f  mov     [rsp+0C0h+var_A0], rax; unsigned __int64 *
0x180095544  mov     rcx, rdi; unsigned __int16 *
0x180095547  jz      loc_1800955F9
0x18009554d  mov     [rbp+57h+var_58], 6
0x180095555  lea     r8, aUnc; "\\\\?\\UNC\\"
0x18009555c  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180095561  mov     r15, [rbp+57h+var_78]
0x180095565  mov     esi, eax
0x180095567  mov     rbx, [rbp+57h+var_80]
0x18009556b  xor     r11d, r11d
0x18009556e  mov     r13d, [rbp+57h+arg_8]
0x180095572  mov     eax, r13d
0x180095575  and     eax, 5
0x180095578  mov     [rbp+57h+var_4C], eax
0x18009557b  cmp     eax, 5
0x18009557e  jnz     short loc_1800955B3
0x180095580  cmp     [rbp+57h+var_58], r11
0x180095584  jz      short loc_1800955B3
0x180095586  mov     eax, 104h
0x18009558b  mov     [rbp+57h+var_58], r11
0x18009558f  mov     rbx, rdi
0x180095592  mov     [rbp+57h+var_78], rax
0x180095596  mov     edx, eax; unsigned __int64
0x180095598  mov     [rbp+57h+var_80], rbx
0x18009559c  lea     r8, String; unsigned __int16 *
0x1800955a3  mov     rcx, rdi; unsigned __int16 *
0x1800955a6  mov     r15d, eax
0x1800955a9  mov     r14, r12
0x1800955ac  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800955b1  mov     esi, eax
0x1800955b3  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800955b7  test    esi, esi
0x1800955b9  js      loc_18009593E
0x1800955bf  cmp     [r14], r11w
0x1800955c3  jz      loc_18009593E
0x1800955c9  mov     rdx, [rbp+57h+Control]; Control
0x1800955cd  mov     rcx, r14; String
0x1800955d0  call    cs:__imp_wcspbrk
0x1800955d7  nop     dword ptr [rax+rax+00h]
0x1800955dc  xor     r11d, r11d
0x1800955df  mov     r13, rax
0x1800955e2  test    rax, rax
0x1800955e5  jz      loc_1800956D5
0x1800955eb  mov     r12, rax
0x1800955ee  sub     r12, r14
0x1800955f1  sar     r12, 1
0x1800955f4  jmp     loc_1800956DF
0x1800955f9  lea     r8, asc_1800A71DC; "\\\\"
0x180095600  jmp     loc_18009555C
0x180095605  mov     rbx, rdi
0x180095608  mov     rcx, r12; unsigned __int16 *
0x18009560b  mov     [rbp+57h+var_80], rbx
0x18009560f  mov     r14, r12
0x180095612  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x180095617  mov     r13b, al
0x18009561a  test    al, al
0x18009561c  jz      short loc_18009565B
0x18009561e  lea     rax, [r12+8]
0x180095623  movzx   ecx, word ptr [rax]; C
0x180095626  mov     [rbp+57h+String], rax
0x18009562a  call    cs:__imp_iswalpha
0x180095631  nop     dword ptr [rax+rax+00h]
0x180095636  xor     r11d, r11d
0x180095639  test    eax, eax
0x18009563b  jz      short loc_18009564D
0x18009563d  cmp     word ptr [r12+0Ah], 3Ah ; ':'
0x180095644  jnz     short loc_18009564D
0x180095646  lea     r14, [r12+8]
0x18009564b  jmp     short loc_180095650
0x18009564d  mov     r13b, r11b
0x180095650  test    r13b, r13b
0x180095653  jz      loc_18009556E
0x180095659  jmp     short loc_180095688
0x18009565b  movzx   ecx, word ptr [r12]; C
0x180095660  mov     [rbp+57h+String], r12
0x180095664  call    cs:__imp_iswalpha
0x18009566b  nop     dword ptr [rax+rax+00h]
0x180095670  xor     r11d, r11d
0x180095673  test    eax, eax
0x180095675  jz      loc_18009556E
0x18009567b  cmp     word ptr [r12+2], 3Ah ; ':'
0x180095682  jnz     loc_18009556E
0x180095688  mov     r13d, [rbp+57h+arg_8]
0x18009568c  mov     ecx, r13d; enum PATHCCH_OPTIONS
0x18009568f  call    ?MayNeedExtendedLengthPrefix@@YA_NW4PATHCCH_OPTIONS@@@Z; MayNeedExtendedLengthPrefix(PATHCCH_OPTIONS)
0x180095694  test    al, al
0x180095696  jz      loc_180095572
0x18009569c  lea     rax, [rbp+57h+var_78]
0x1800956a0  mov     [rbp+57h+var_58], 4
0x1800956a8  lea     r9, [rbp+57h+var_80]; unsigned __int16 **
0x1800956ac  mov     [rsp+0C0h+var_A0], rax; unsigned __int64 *
0x1800956b1  lea     r8, asc_1800AADA0; "\\\\?\\"
0x1800956b8  mov     rdx, r15; unsigned __int64
0x1800956bb  mov     rcx, rdi; unsigned __int16 *
0x1800956be  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800956c3  mov     r15, [rbp+57h+var_78]
0x1800956c7  mov     esi, eax
0x1800956c9  mov     rbx, [rbp+57h+var_80]
0x1800956cd  xor     r11d, r11d
0x1800956d0  jmp     loc_180095572
0x1800956d5  inc     r12
0x1800956d8  cmp     [r14+r12*2], r11w
0x1800956dd  jnz     short loc_1800956D5
0x1800956df  cmp     r12, 100h
0x1800956e6  jbe     short loc_1800956F2
0x1800956e8  cmp     [rbp+57h+var_50], r11d
0x1800956ec  jz      loc_180095935
0x1800956f2  cmp     r12, 8000h
0x1800956f9  jnb     loc_180095935
0x1800956ff  cmp     r12, 1
0x180095703  jnz     short loc_180095770
0x180095705  cmp     word ptr [r14], 2Eh ; '.'
0x18009570a  jnz     loc_18009587C
0x180095710  test    r13, r13
0x180095713  jz      short loc_18009571E
0x180095715  lea     r14, [rax+2]
0x180095719  jmp     loc_1800955B3
0x18009571e  add     r14, 2
0x180095722  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180095729  cmp     rbx, rdi
0x18009572c  jbe     loc_1800955B7
0x180095732  mov     rcx, rdi; pszPath
0x180095735  call    PathCchIsRoot
0x18009573a  xor     r11d, r11d
0x18009573d  test    eax, eax
0x18009573f  jnz     loc_1800955B7
0x180095745  sub     rbx, 2
0x180095749  lea     r8, String; unsigned __int16 *
0x180095750  inc     r15
0x180095753  mov     [rbp+57h+var_80], rbx
0x180095757  mov     rdx, r15; unsigned __int64
0x18009575a  mov     [rbp+57h+var_78], r15
0x18009575e  mov     rcx, rbx; unsigned __int16 *
0x180095761  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180095766  mov     esi, eax
0x180095768  or      r12, r12
0x18009576b  jmp     loc_1800955B7
0x180095770  cmp     r12, 2
0x180095774  jnz     loc_180095815
0x18009577a  cmp     word ptr [r14], 2Eh ; '.'
0x18009577f  jnz     loc_18009587C
0x180095785  cmp     word ptr [r14+2], 2Eh ; '.'
0x18009578b  jnz     loc_18009587C
0x180095791  cmp     rbx, rdi
0x180095794  jbe     short loc_180095807
0x180095796  mov     rcx, rdi; pszPath
0x180095799  call    PathCchIsRoot
0x18009579e  xor     r11d, r11d
0x1800957a1  test    eax, eax
0x1800957a3  jnz     short loc_180095807
0x1800957a5  add     rbx, 0FFFFFFFFFFFFFFFEh
0x1800957a9  lea     eax, [r12+5Ah]
0x1800957ae  cmp     rdi, rbx
0x1800957b1  jnb     short loc_1800957D9
0x1800957b3  sub     rbx, 2
0x1800957b7  cmp     [rbx], ax
0x1800957ba  jnz     short loc_1800957AE
0x1800957bc  mov     [rbp+57h+var_80], rbx
0x1800957c0  test    rbx, rbx
0x1800957c3  jz      short loc_1800957D9
0x1800957c5  mov     rax, rbx
0x1800957c8  mov     r15d, 104h
0x1800957ce  sub     rax, rdi
0x1800957d1  sar     rax, 1
0x1800957d4  sub     r15, rax
0x1800957d7  jmp     short loc_1800957E6
0x1800957d9  mov     rbx, rdi
0x1800957dc  mov     r15d, 104h
0x1800957e2  mov     [rbp+57h+var_80], rbx
0x1800957e6  lea     r8, String; unsigned __int16 *
0x1800957ed  mov     [rbp+57h+var_78], r15
0x1800957f1  mov     rdx, r15; unsigned __int64
0x1800957f4  mov     rcx, rbx; unsigned __int16 *
0x1800957f7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800957fc  mov     esi, eax
0x1800957fe  add     r14, 4
0x180095802  jmp     loc_1800955B3
0x180095807  test    r13, r13
0x18009580a  jz      short loc_1800957FE
0x18009580c  lea     r14, [r13+2]
0x180095810  jmp     loc_1800955B3
0x180095815  test    r12, r12
0x180095818  jnz     short loc_18009587C
0x18009581a  lea     rax, [rbp+57h+var_78]
0x18009581e  mov     rdx, r15; unsigned __int64
0x180095821  mov     [rsp+28h], rax; unsigned __int64 *
0x180095826  lea     r9d, [r12+1]; unsigned __int64
0x18009582b  lea     rax, [rbp+57h+var_80]
0x18009582f  mov     rcx, rbx; unsigned __int16 *
0x180095832  lea     r8, SubBlock; "\\"
0x180095839  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 **
0x18009583e  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180095843  xor     r11d, r11d
0x180095846  add     r14, 2
0x18009584a  mov     esi, eax
0x18009584c  cmp     r14, [rbp+57h+String]
0x180095850  jbe     short loc_1800958A4
0x180095852  mov     r13, [rbp+57h+var_70]
0x180095856  cmp     [rbp+57h+arg_18], r11b
0x18009585a  jz      short loc_1800958A8
0x18009585c  lea     rbx, [r14+2]
0x180095860  movzx   ecx, word ptr [r14]
0x180095864  mov     rax, r13
0x180095867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009586c  xor     r11d, r11d
0x18009586f  test    al, al
0x180095871  jz      short loc_1800958A8
0x180095873  mov     r14, rbx
0x180095876  add     rbx, 2
0x18009587a  jmp     short loc_180095860
0x18009587c  lea     rax, [rbp+57h+var_78]
0x180095880  mov     r9, r12; unsigned __int64
0x180095883  mov     [rsp+28h], rax; unsigned __int64 *
0x180095888  mov     r8, r14; unsigned __int16 *
0x18009588b  lea     rax, [rbp+57h+var_80]
0x18009588f  mov     rdx, r15; unsigned __int64
0x180095892  mov     rcx, rbx; unsigned __int16 *
0x180095895  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 **
0x18009589a  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18009589f  mov     esi, eax
0x1800958a1  xor     r11d, r11d
0x1800958a4  mov     r13, [rbp+57h+var_70]
0x1800958a8  cmp     esi, 8007007Ah
0x1800958ae  jnz     short loc_180095913
0x1800958b0  cmp     r12, 1
0x1800958b4  jnz     short loc_180095913
0x1800958b6  movzx   ecx, word ptr [r14]
0x1800958ba  mov     rax, r13
0x1800958bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800958c2  xor     r11d, r11d
  ... truncated ...
```
