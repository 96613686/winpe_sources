# PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)

- ea: `0x180093084`
- end: `0x1800936ed`
- name: `?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z`
- size: `1641`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, enum PATHCCH_OPTIONS)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path`

## callers

- `0x180093b44`

## callees

- `0x18004a6ac`
- `0x180092f54`
- `0x180093040`
- `0x180093068`
- `0x180093084`
- `0x1800936f4`
- `0x1800937cc`
- `0x180093824`
- `0x1800938d4`
- `0x180093dc8`
- `0x180096010`

## import_xrefs

- `msvcrt!wcspbrk` at `0x180093210`
- `msvcrt!wcspbrk` at `0x180093210`
- `msvcrt!iswalpha` at `0x180093264`
- `msvcrt!iswalpha` at `0x180093298`
- `msvcrt!iswalpha` at `0x180093264`
- `msvcrt!iswalpha` at `0x180093298`

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
0x180093084  mov     rax, rsp
0x180093087  mov     [rax+8], rbx
0x18009308b  mov     [rax+20h], r9d
0x18009308f  mov     [rax+10h], rdx
0x180093093  push    rbp
0x180093094  push    rsi
0x180093095  push    rdi
0x180093096  push    r12
0x180093098  push    r13
0x18009309a  push    r14
0x18009309c  push    r15
0x18009309e  lea     rbp, [rax-5Fh]
0x1800930a2  sub     rsp, 90h
0x1800930a9  mov     r12, r8
0x1800930ac  mov     r14d, 104h
0x1800930b2  xor     r13d, r13d
0x1800930b5  lea     r8, String; unsigned __int16 *
0x1800930bc  mov     edx, r14d; unsigned __int64
0x1800930bf  mov     [rbp+57h+var_60], r13d
0x1800930c3  mov     rdi, rcx
0x1800930c6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800930cb  mov     esi, eax
0x1800930cd  test    eax, eax
0x1800930cf  js      loc_1800936D2
0x1800930d5  lea     rcx, [rbp+57h+var_60]; enum PATHCCH_OPTIONS *
0x1800930d9  call    ?AreOptionsValidAndOptInLongPathAwareProcess@@YA_NAEAW4PATHCCH_OPTIONS@@@Z; AreOptionsValidAndOptInLongPathAwareProcess(PATHCCH_OPTIONS &)
0x1800930de  test    al, al
0x1800930e0  jnz     short loc_1800930EC
0x1800930e2  mov     eax, 80070057h
0x1800930e7  jmp     loc_1800936D2
0x1800930ec  mov     ebx, [rbp+57h+var_60]
0x1800930ef  mov     r15, r14
0x1800930f2  and     ebx, 0FFFFFFF8h
0x1800930f5  mov     [rbp+57h+var_78], r14
0x1800930f9  mov     eax, ebx
0x1800930fb  mov     [rbp+57h+arg_8], ebx
0x1800930fe  and     eax, 11h
0x180093101  mov     [rbp+57h+var_80], r13
0x180093105  mov     [rbp+57h+var_50], eax
0x180093108  mov     [rbp+57h+var_58], r13
0x18009310c  test    bl, 40h
0x18009310f  jz      short loc_18009311C
0x180093111  mov     cl, 1
0x180093113  lea     rax, IsBackOrForwardSlash
0x18009311a  jmp     short loc_180093126
0x18009311c  mov     cl, r13b
0x18009311f  lea     rax, IsBackslash
0x180093126  test    cl, cl
0x180093128  mov     [rbp+57h+arg_18], cl
0x18009312b  lea     r8, SubBlock; "\\"
0x180093132  mov     [rbp+57h+var_70], rax
0x180093136  lea     rdx, asc_1800A88A4; "\\/"
0x18009313d  mov     [rbp+57h+String], r13
0x180093141  cmovz   rdx, r8
0x180093145  mov     rcx, r12; unsigned __int16 *
0x180093148  mov     [rbp+57h+Control], rdx
0x18009314c  mov     r8, rax
0x18009314f  lea     rdx, [rbp+57h+String]
0x180093153  call    PathIsUnc2
0x180093158  mov     [rbp+57h+var_48], eax
0x18009315b  test    eax, eax
0x18009315d  jz      loc_18009323F
0x180093163  mov     r14, [rbp+57h+String]
0x180093167  mov     ecx, ebx; enum PATHCCH_OPTIONS
0x180093169  mov     [rbp+57h+String], r14
0x18009316d  call    ?MayNeedExtendedLengthPrefix@@YA_NW4PATHCCH_OPTIONS@@@Z; MayNeedExtendedLengthPrefix(PATHCCH_OPTIONS)
0x180093172  test    al, al
0x180093174  lea     r9, [rbp+57h+var_80]; unsigned __int16 **
0x180093178  lea     rax, [rbp+57h+var_78]
0x18009317c  mov     rdx, r15; unsigned __int64
0x18009317f  mov     [rsp+0C0h+var_A0], rax; unsigned __int64 *
0x180093184  mov     rcx, rdi; unsigned __int16 *
0x180093187  jz      loc_180093233
0x18009318d  mov     [rbp+57h+var_58], 6
0x180093195  lea     r8, aUnc; "\\\\?\\UNC\\"
0x18009319c  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800931a1  mov     r15, [rbp+57h+var_78]
0x1800931a5  mov     esi, eax
0x1800931a7  mov     rbx, [rbp+57h+var_80]
0x1800931ab  xor     r11d, r11d
0x1800931ae  mov     r13d, [rbp+57h+arg_8]
0x1800931b2  mov     eax, r13d
0x1800931b5  and     eax, 5
0x1800931b8  mov     [rbp+57h+var_4C], eax
0x1800931bb  cmp     eax, 5
0x1800931be  jnz     short loc_1800931F3
0x1800931c0  cmp     [rbp+57h+var_58], r11
0x1800931c4  jz      short loc_1800931F3
0x1800931c6  mov     eax, 104h
0x1800931cb  mov     [rbp+57h+var_58], r11
0x1800931cf  mov     rbx, rdi
0x1800931d2  mov     [rbp+57h+var_78], rax
0x1800931d6  mov     edx, eax; unsigned __int64
0x1800931d8  mov     [rbp+57h+var_80], rbx
0x1800931dc  lea     r8, String; unsigned __int16 *
0x1800931e3  mov     rcx, rdi; unsigned __int16 *
0x1800931e6  mov     r15d, eax
0x1800931e9  mov     r14, r12
0x1800931ec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800931f1  mov     esi, eax
0x1800931f3  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800931f7  test    esi, esi
0x1800931f9  js      loc_18009356C
0x1800931ff  cmp     [r14], r11w
0x180093203  jz      loc_18009356C
0x180093209  mov     rdx, [rbp+57h+Control]; Control
0x18009320d  mov     rcx, r14; String
0x180093210  call    cs:__imp_wcspbrk
0x180093216  xor     r11d, r11d
0x180093219  mov     r13, rax
0x18009321c  test    rax, rax
0x18009321f  jz      loc_180093303
0x180093225  mov     r12, rax
0x180093228  sub     r12, r14
0x18009322b  sar     r12, 1
0x18009322e  jmp     loc_18009330D
0x180093233  lea     r8, asc_1800A51EC; "\\\\"
0x18009323a  jmp     loc_18009319C
0x18009323f  mov     rbx, rdi
0x180093242  mov     rcx, r12; unsigned __int16 *
0x180093245  mov     [rbp+57h+var_80], rbx
0x180093249  mov     r14, r12
0x18009324c  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x180093251  mov     r13b, al
0x180093254  test    al, al
0x180093256  jz      short loc_18009328F
0x180093258  lea     rax, [r12+8]
0x18009325d  movzx   ecx, word ptr [rax]; C
0x180093260  mov     [rbp+57h+String], rax
0x180093264  call    cs:__imp_iswalpha
0x18009326a  xor     r11d, r11d
0x18009326d  test    eax, eax
0x18009326f  jz      short loc_180093281
0x180093271  cmp     word ptr [r12+0Ah], 3Ah ; ':'
0x180093278  jnz     short loc_180093281
0x18009327a  lea     r14, [r12+8]
0x18009327f  jmp     short loc_180093284
0x180093281  mov     r13b, r11b
0x180093284  test    r13b, r13b
0x180093287  jz      loc_1800931AE
0x18009328d  jmp     short loc_1800932B6
0x18009328f  movzx   ecx, word ptr [r12]; C
0x180093294  mov     [rbp+57h+String], r12
0x180093298  call    cs:__imp_iswalpha
0x18009329e  xor     r11d, r11d
0x1800932a1  test    eax, eax
0x1800932a3  jz      loc_1800931AE
0x1800932a9  cmp     word ptr [r12+2], 3Ah ; ':'
0x1800932b0  jnz     loc_1800931AE
0x1800932b6  mov     r13d, [rbp+57h+arg_8]
0x1800932ba  mov     ecx, r13d; enum PATHCCH_OPTIONS
0x1800932bd  call    ?MayNeedExtendedLengthPrefix@@YA_NW4PATHCCH_OPTIONS@@@Z; MayNeedExtendedLengthPrefix(PATHCCH_OPTIONS)
0x1800932c2  test    al, al
0x1800932c4  jz      loc_1800931B2
0x1800932ca  lea     rax, [rbp+57h+var_78]
0x1800932ce  mov     [rbp+57h+var_58], 4
0x1800932d6  lea     r9, [rbp+57h+var_80]; unsigned __int16 **
0x1800932da  mov     [rsp+0C0h+var_A0], rax; unsigned __int64 *
0x1800932df  lea     r8, asc_1800A8DB8; "\\\\?\\"
0x1800932e6  mov     rdx, r15; unsigned __int64
0x1800932e9  mov     rcx, rdi; unsigned __int16 *
0x1800932ec  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800932f1  mov     r15, [rbp+57h+var_78]
0x1800932f5  mov     esi, eax
0x1800932f7  mov     rbx, [rbp+57h+var_80]
0x1800932fb  xor     r11d, r11d
0x1800932fe  jmp     loc_1800931B2
0x180093303  inc     r12
0x180093306  cmp     [r14+r12*2], r11w
0x18009330b  jnz     short loc_180093303
0x18009330d  cmp     r12, 100h
0x180093314  jbe     short loc_180093320
0x180093316  cmp     [rbp+57h+var_50], r11d
0x18009331a  jz      loc_180093563
0x180093320  cmp     r12, 8000h
0x180093327  jnb     loc_180093563
0x18009332d  cmp     r12, 1
0x180093331  jnz     short loc_18009339E
0x180093333  cmp     word ptr [r14], 2Eh ; '.'
0x180093338  jnz     loc_1800934AA
0x18009333e  test    r13, r13
0x180093341  jz      short loc_18009334C
0x180093343  lea     r14, [rax+2]
0x180093347  jmp     loc_1800931F3
0x18009334c  add     r14, 2
0x180093350  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180093357  cmp     rbx, rdi
0x18009335a  jbe     loc_1800931F7
0x180093360  mov     rcx, rdi; pszPath
0x180093363  call    PathCchIsRoot
0x180093368  xor     r11d, r11d
0x18009336b  test    eax, eax
0x18009336d  jnz     loc_1800931F7
0x180093373  sub     rbx, 2
0x180093377  lea     r8, String; unsigned __int16 *
0x18009337e  inc     r15
0x180093381  mov     [rbp+57h+var_80], rbx
0x180093385  mov     rdx, r15; unsigned __int64
0x180093388  mov     [rbp+57h+var_78], r15
0x18009338c  mov     rcx, rbx; unsigned __int16 *
0x18009338f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180093394  mov     esi, eax
0x180093396  or      r12, r12
0x180093399  jmp     loc_1800931F7
0x18009339e  cmp     r12, 2
0x1800933a2  jnz     loc_180093443
0x1800933a8  cmp     word ptr [r14], 2Eh ; '.'
0x1800933ad  jnz     loc_1800934AA
0x1800933b3  cmp     word ptr [r14+2], 2Eh ; '.'
0x1800933b9  jnz     loc_1800934AA
0x1800933bf  cmp     rbx, rdi
0x1800933c2  jbe     short loc_180093435
0x1800933c4  mov     rcx, rdi; pszPath
0x1800933c7  call    PathCchIsRoot
0x1800933cc  xor     r11d, r11d
0x1800933cf  test    eax, eax
0x1800933d1  jnz     short loc_180093435
0x1800933d3  add     rbx, 0FFFFFFFFFFFFFFFEh
0x1800933d7  lea     eax, [r12+5Ah]
0x1800933dc  cmp     rdi, rbx
0x1800933df  jnb     short loc_180093407
0x1800933e1  sub     rbx, 2
0x1800933e5  cmp     [rbx], ax
0x1800933e8  jnz     short loc_1800933DC
0x1800933ea  mov     [rbp+57h+var_80], rbx
0x1800933ee  test    rbx, rbx
0x1800933f1  jz      short loc_180093407
0x1800933f3  mov     rax, rbx
0x1800933f6  mov     r15d, 104h
0x1800933fc  sub     rax, rdi
0x1800933ff  sar     rax, 1
0x180093402  sub     r15, rax
0x180093405  jmp     short loc_180093414
0x180093407  mov     rbx, rdi
0x18009340a  mov     r15d, 104h
0x180093410  mov     [rbp+57h+var_80], rbx
0x180093414  lea     r8, String; unsigned __int16 *
0x18009341b  mov     [rbp+57h+var_78], r15
0x18009341f  mov     rdx, r15; unsigned __int64
0x180093422  mov     rcx, rbx; unsigned __int16 *
0x180093425  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009342a  mov     esi, eax
0x18009342c  add     r14, 4
0x180093430  jmp     loc_1800931F3
0x180093435  test    r13, r13
0x180093438  jz      short loc_18009342C
0x18009343a  lea     r14, [r13+2]
0x18009343e  jmp     loc_1800931F3
0x180093443  test    r12, r12
0x180093446  jnz     short loc_1800934AA
0x180093448  lea     rax, [rbp+57h+var_78]
0x18009344c  mov     rdx, r15; unsigned __int64
0x18009344f  mov     [rsp+28h], rax; unsigned __int64 *
0x180093454  lea     r9d, [r12+1]; unsigned __int64
0x180093459  lea     rax, [rbp+57h+var_80]
0x18009345d  mov     rcx, rbx; unsigned __int16 *
0x180093460  lea     r8, SubBlock; "\\"
0x180093467  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 **
0x18009346c  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180093471  xor     r11d, r11d
0x180093474  add     r14, 2
0x180093478  mov     esi, eax
0x18009347a  cmp     r14, [rbp+57h+String]
0x18009347e  jbe     short loc_1800934D2
0x180093480  mov     r13, [rbp+57h+var_70]
0x180093484  cmp     [rbp+57h+arg_18], r11b
0x180093488  jz      short loc_1800934D6
0x18009348a  lea     rbx, [r14+2]
0x18009348e  movzx   ecx, word ptr [r14]
0x180093492  mov     rax, r13
0x180093495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009349a  xor     r11d, r11d
0x18009349d  test    al, al
0x18009349f  jz      short loc_1800934D6
0x1800934a1  mov     r14, rbx
0x1800934a4  add     rbx, 2
0x1800934a8  jmp     short loc_18009348E
0x1800934aa  lea     rax, [rbp+57h+var_78]
0x1800934ae  mov     r9, r12; unsigned __int64
0x1800934b1  mov     [rsp+28h], rax; unsigned __int64 *
0x1800934b6  mov     r8, r14; unsigned __int16 *
0x1800934b9  lea     rax, [rbp+57h+var_80]
0x1800934bd  mov     rdx, r15; unsigned __int64
0x1800934c0  mov     rcx, rbx; unsigned __int16 *
0x1800934c3  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 **
0x1800934c8  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800934cd  mov     esi, eax
0x1800934cf  xor     r11d, r11d
0x1800934d2  mov     r13, [rbp+57h+var_70]
0x1800934d6  cmp     esi, 8007007Ah
0x1800934dc  jnz     short loc_180093541
0x1800934de  cmp     r12, 1
0x1800934e2  jnz     short loc_180093541
0x1800934e4  movzx   ecx, word ptr [r14]
0x1800934e8  mov     rax, r13
0x1800934eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800934f0  xor     r11d, r11d
0x1800934f3  test    al, al
0x1800934f5  jz      short loc_180093541
0x1800934f7  movzx   eax, word ptr [r14+2]
  ... truncated ...
```
