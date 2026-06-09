# CCertTypeInfo::SetExtension(ushort const *,void *,ulong)

- ea: `0x180031060`
- end: `0x180031486`
- name: `?SetExtension@CCertTypeInfo@@QEAAJPEBGPEAXK@Z`
- size: `1062`
- prototype: `int __fastcall(CCertTypeInfo *this, const unsigned __int16 *, char *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18002ec40`

## callees

- `0x180002ef0`
- `0x180008400`
- `0x1800113e0`
- `0x180012450`
- `0x180012a7c`
- `0x180013a86`
- `0x180031060`
- `0x180038286`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031145`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800312a1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003136b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800313d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031145`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800312a1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003136b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800313d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800311f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003122f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003125e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031452`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031469`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800311f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003122f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003125e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031452`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031469`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003111a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800311bf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003111a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800311bf`

## string_xrefs

- `0x1800312fd`: `pKICriticalExtensions`

## pseudocode

```c
int __fastcall CCertTypeInfo::SetExtension(CCertTypeInfo *this, const unsigned __int16 *a2, char *a3, int a4)
{
  unsigned int v4; // r15d
  char v5; // r14
  _QWORD *v10; // r12
  unsigned int v11; // esi
  unsigned int v12; // r14d
  const CHAR *v13; // r8
  __int64 v14; // rax
  unsigned int v15; // ecx
  int v16; // ebx
  int v17; // edx
  char *v18; // rax
  HLOCAL v19; // rsi
  WCHAR *lpWideCharStr; // r13
  int cchWideChar; // r14d
  __int64 v22; // rax
  unsigned int v23; // eax
  int v24; // eax
  int v25; // eax
  void *v26; // rcx
  _DWORD *v27; // rcx
  HLOCAL v28; // rax
  DWORD Property; // eax
  CCertTypeInfo *v30; // rcx
  int v31; // r14d
  _QWORD *v32; // rcx
  unsigned int v33; // esi
  unsigned __int16 **v34; // rax
  unsigned __int16 **v35; // r14
  unsigned __int16 **v36; // rcx
  _QWORD *v37; // rdx
  char *v38; // rcx
  unsigned int v39; // r8d
  unsigned __int16 *v40; // rax
  int v41; // r10d
  int v42; // r9d
  __int64 v43; // rax
  void *Src; // [rsp+78h] [rbp+10h] BYREF
  int v45; // [rsp+88h] [rbp+20h]

  v45 = a4;
  v4 = 0;
  v5 = a4;
  Src = 0;
  if ( !a2 )
    return -2147467261;
  if ( !wcscmp_0(a2, L"2.5.29.37") )
  {
    if ( !a3 )
      return CCertTypeInfo::SetProperty(this, L"pKIExtendedKeyUsage", 0);
    v10 = a3 + 8;
    v11 = 0;
    v12 = 8 * *(_DWORD *)a3 + 8;
    while ( v11 < *(_DWORD *)a3 )
    {
      v10 = a3 + 8;
      v13 = *(const CHAR **)(*((_QWORD *)a3 + 1) + 8LL * v11);
      v14 = -1;
      do
        ++v14;
      while ( v13[v14] );
      if ( (unsigned __int64)(v14 + 1) > 0x10000 )
      {
        v15 = 434701096;
        v16 = -2147024362;
LABEL_13:
        v17 = -2147024362;
        goto LABEL_14;
      }
      ++v11;
      v12 += 2 * MultiByteToWideChar(0, 0, v13, v14 + 1, 0, 0);
    }
    v18 = (char *)LocalAlloc(0, v12);
    v19 = v18;
    if ( !v18 )
      goto LABEL_16;
    lpWideCharStr = (WCHAR *)&v18[8 * (*(_DWORD *)a3 + 1)];
    cchWideChar = -8 - 8 * *(_DWORD *)a3 + v12;
    while ( v4 < *(_DWORD *)a3 )
    {
      v22 = -1;
      do
        ++v22;
      while ( *(_BYTE *)(*(_QWORD *)(*v10 + 8LL * v4) + v22) );
      if ( (unsigned __int64)(v22 + 1) > 0x10000 )
      {
        v16 = -2147024362;
        LocalFree(v19);
        v15 = 436273960;
        goto LABEL_13;
      }
      *((_QWORD *)v19 + v4) = lpWideCharStr;
      v23 = MultiByteToWideChar(0, 0, *(LPCCH *)(*v10 + 8LL * v4), v22 + 1, lpWideCharStr, cchWideChar);
      if ( !v23 )
      {
        v24 = myHLastError();
        goto LABEL_68;
      }
      v10 = a3 + 8;
      cchWideChar += -2 * v23;
      lpWideCharStr += v23;
      ++v4;
    }
    *((_QWORD *)v19 + v4) = 0;
    v25 = CCertTypeInfo::SetProperty(this, L"pKIExtendedKeyUsage", (unsigned __int16 **)v19);
    if ( v25 )
      CSPrintErrorLineFile(0x1A170328u, v25);
    LocalFree(v19);
    v5 = v45;
  }
  else if ( !wcscmp_0(a2, L"2.5.29.15") )
  {
    v26 = (void *)*((_QWORD *)this + 5);
    if ( v26 )
    {
      LocalFree(v26);
      v27 = (_DWORD *)((char *)this + 48);
      *((_QWORD *)this + 5) = 0;
      *((_DWORD *)this + 12) = 0;
      *((_DWORD *)this + 8) = 0;
    }
    else
    {
      v27 = (_DWORD *)((char *)this + 48);
    }
    if ( !a3 )
      return 0;
    *((_DWORD *)this + 8) = *(_DWORD *)a3;
    *v27 = *((_DWORD *)a3 + 4);
    if ( !*((_QWORD *)a3 + 1) )
    {
LABEL_36:
      v16 = 0;
      goto LABEL_71;
    }
    v28 = LocalAlloc(0, *(unsigned int *)a3);
    *((_QWORD *)this + 5) = v28;
    if ( !v28 )
    {
LABEL_16:
      v16 = -2147024882;
      goto LABEL_71;
    }
    memcpy_0(v28, *((const void **)a3 + 1), *(unsigned int *)a3);
  }
  else
  {
    if ( wcscmp_0(a2, L"2.5.29.19") )
    {
      v16 = -2147467263;
LABEL_71:
      if ( Src )
        LocalFree(Src);
      return v16;
    }
    if ( !a3 )
    {
      *((_QWORD *)this + 2) = 0;
      *((_DWORD *)this + 6) = 0;
      return -2147467261;
    }
    *((_QWORD *)this + 2) = *(_QWORD *)a3;
    *((_DWORD *)this + 6) = *((_DWORD *)a3 + 2);
  }
  Property = CCertTypeInfo::GetProperty(this, L"pKICriticalExtensions", &Src);
  v16 = Property;
  if ( Property )
  {
    v17 = Property;
    v15 = 441385768;
LABEL_14:
    CSPrintErrorLineFile(v15, v17);
    goto LABEL_71;
  }
  v31 = v5 & 1;
  if ( v31 == (unsigned int)CCertTypeInfo::_IsCritical(v30, a2, (const unsigned __int16 **)Src) )
    goto LABEL_36;
  v32 = Src;
  v33 = 0;
  if ( Src )
  {
    while ( *v32 )
    {
      ++v33;
      ++v32;
    }
  }
  if ( v31 )
  {
    v34 = (unsigned __int16 **)LocalAlloc(0x40u, 8LL * (v33 + 2));
    v35 = v34;
    if ( !v34 )
    {
      v16 = -2147024882;
      v15 = 443220776;
      v17 = -2147024882;
      goto LABEL_14;
    }
    if ( Src )
      memcpy_0(v34, Src, 8LL * v33);
    v35[v33] = (unsigned __int16 *)a2;
    v24 = CCertTypeInfo::SetProperty(this, L"pKICriticalExtensions", v35);
    v36 = v35;
    goto LABEL_69;
  }
  if ( Src )
  {
    v19 = LocalAlloc(0x40u, 8LL * v33);
    if ( !v19 )
    {
      v16 = -2147024882;
      v15 = 444793640;
      v17 = -2147024882;
      goto LABEL_14;
    }
    v37 = Src;
    v38 = *(char **)Src;
    if ( *(_QWORD *)Src )
    {
      v39 = 0;
      do
      {
        v40 = (unsigned __int16 *)v38;
        do
        {
          v41 = *(unsigned __int16 *)((char *)v40 + (char *)a2 - v38);
          v42 = *v40 - v41;
          if ( v42 )
            break;
          ++v40;
        }
        while ( v41 );
        if ( v42 )
        {
          v43 = v39++;
          *((_QWORD *)v19 + v43) = v38;
        }
        v38 = (char *)*++v37;
      }
      while ( *v37 );
    }
    v24 = CCertTypeInfo::SetProperty(this, L"pKICriticalExtensions", (unsigned __int16 **)v19);
LABEL_68:
    v36 = (unsigned __int16 **)v19;
LABEL_69:
    v16 = v24;
    LocalFree(v36);
    goto LABEL_71;
  }
  return v16;
}

```

## disassembly

```asm
0x180031060  mov     [rsp+arg_0], rbx
0x180031065  mov     [rsp+arg_18], r9d
0x18003106a  push    rbp
0x18003106b  push    rsi
0x18003106c  push    rdi
0x18003106d  push    r12
0x18003106f  push    r13
0x180031071  push    r14
0x180031073  push    r15
0x180031075  sub     rsp, 30h
0x180031079  xor     r15d, r15d
0x18003107c  mov     r14d, r9d
0x18003107f  mov     [rsp+68h+Src], r15
0x180031084  mov     rbx, r8
0x180031087  mov     rbp, rdx
0x18003108a  mov     rdi, rcx
0x18003108d  test    rdx, rdx
0x180031090  jnz     short loc_18003109C
0x180031092  mov     eax, 80004003h
0x180031097  jmp     loc_180031471
0x18003109c  lea     rdx, a252937; "2.5.29.37"
0x1800310a3  mov     rcx, rbp; String1
0x1800310a6  call    wcscmp_0
0x1800310ab  test    eax, eax
0x1800310ad  jnz     loc_180031242
0x1800310b3  test    rbx, rbx
0x1800310b6  jnz     short loc_1800310CF
0x1800310b8  xor     r8d, r8d; unsigned __int16 **
0x1800310bb  lea     rdx, aPkiextendedkey; "pKIExtendedKeyUsage"
0x1800310c2  mov     rcx, rdi; this
0x1800310c5  call    ?SetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAG@Z; CCertTypeInfo::SetProperty(ushort const *,ushort * *)
0x1800310ca  jmp     loc_180031471
0x1800310cf  mov     eax, [rbx]
0x1800310d1  lea     r12, [rbx+8]
0x1800310d5  mov     esi, r15d
0x1800310d8  lea     r14d, ds:8[rax*8]
0x1800310e0  cmp     esi, [rbx]
0x1800310e2  jnb     short loc_180031140
0x1800310e4  lea     r12, [rbx+8]
0x1800310e8  mov     ecx, esi
0x1800310ea  mov     rax, [r12]
0x1800310ee  mov     r8, [rax+rcx*8]; lpMultiByteStr
0x1800310f2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800310f6  inc     rax
0x1800310f9  cmp     [r8+rax], r15b
0x1800310fd  jnz     short loc_1800310F6
0x1800310ff  lea     r9, [rax+1]; cbMultiByte
0x180031103  cmp     r9, 10000h
0x18003110a  ja      short loc_180031128
0x18003110c  mov     [rsp+68h+cchWideChar], r15d; cchWideChar
0x180031111  xor     edx, edx; dwFlags
0x180031113  xor     ecx, ecx; CodePage
0x180031115  mov     [rsp+68h+lpWideCharStr], r15; lpWideCharStr
0x18003111a  call    cs:__imp_MultiByteToWideChar
0x180031120  inc     esi
0x180031122  lea     r14d, [r14+rax*2]
0x180031126  jmp     short loc_1800310E0
0x180031128  mov     edi, 80070216h
0x18003112d  mov     ecx, 19E90328h; unsigned int
0x180031132  mov     ebx, edi
0x180031134  mov     edx, edi; int
0x180031136  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18003113b  jmp     loc_18003145F
0x180031140  mov     edx, r14d; uBytes
0x180031143  xor     ecx, ecx; uFlags
0x180031145  call    cs:__imp_LocalAlloc
0x18003114b  mov     rsi, rax
0x18003114e  test    rax, rax
0x180031151  jnz     short loc_18003115D
0x180031153  mov     ebx, 8007000Eh
0x180031158  jmp     loc_18003145F
0x18003115d  mov     edx, [rbx]
0x18003115f  mov     ecx, 0FFFFFFF8h
0x180031164  lea     eax, [rdx+1]
0x180031167  lea     r13, [rsi+rax*8]
0x18003116b  lea     eax, ds:0[rdx*8]
0x180031172  sub     ecx, eax
0x180031174  add     r14d, ecx
0x180031177  mov     ecx, r15d
0x18003117a  cmp     r15d, [rbx]
0x18003117d  jnb     loc_180031203
0x180031183  mov     rax, [r12]
0x180031187  mov     rdx, [rax+rcx*8]
0x18003118b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003118f  inc     rax
0x180031192  cmp     byte ptr [rdx+rax], 0
0x180031196  jnz     short loc_18003118F
0x180031198  lea     r9, [rax+1]; cbMultiByte
0x18003119c  cmp     r9, 10000h
0x1800311a3  ja      short loc_1800311E9
0x1800311a5  mov     [rsi+rcx*8], r13
0x1800311a9  xor     edx, edx; dwFlags
0x1800311ab  mov     r8, [r12]
0x1800311af  mov     [rsp+68h+cchWideChar], r14d; cchWideChar
0x1800311b4  mov     [rsp+68h+lpWideCharStr], r13; lpWideCharStr
0x1800311b9  mov     r8, [r8+rcx*8]; lpMultiByteStr
0x1800311bd  xor     ecx, ecx; CodePage
0x1800311bf  call    cs:__imp_MultiByteToWideChar
0x1800311c5  test    eax, eax
0x1800311c7  jz      short loc_1800311DF
0x1800311c9  imul    ecx, eax, -2
0x1800311cc  lea     r12, [rbx+8]
0x1800311d0  mov     eax, eax
0x1800311d2  add     r14d, ecx
0x1800311d5  lea     r13, [r13+rax*2+0]
0x1800311da  inc     r15d
0x1800311dd  jmp     short loc_180031177
0x1800311df  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800311e4  jmp     loc_18003144D
0x1800311e9  mov     edi, 80070216h
0x1800311ee  mov     rcx, rsi; hMem
0x1800311f1  mov     ebx, edi
0x1800311f3  call    cs:__imp_LocalFree
0x1800311f9  mov     ecx, 1A010328h
0x1800311fe  jmp     loc_180031134
0x180031203  xor     r15d, r15d
0x180031206  lea     rdx, aPkiextendedkey; "pKIExtendedKeyUsage"
0x18003120d  mov     [rsi+rcx*8], r15
0x180031211  mov     r8, rsi; unsigned __int16 **
0x180031214  mov     rcx, rdi; this
0x180031217  call    ?SetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAG@Z; CCertTypeInfo::SetProperty(ushort const *,ushort * *)
0x18003121c  test    eax, eax
0x18003121e  jz      short loc_18003122C
0x180031220  mov     edx, eax; int
0x180031222  mov     ecx, 1A170328h; unsigned int
0x180031227  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18003122c  mov     rcx, rsi; hMem
0x18003122f  call    cs:__imp_LocalFree
0x180031235  mov     r14d, [rsp+68h+arg_18]
0x18003123d  jmp     loc_1800312FD
0x180031242  lea     rdx, a252915_0; "2.5.29.15"
0x180031249  mov     rcx, rbp; String1
0x18003124c  call    wcscmp_0
0x180031251  test    eax, eax
0x180031253  jnz     short loc_1800312C5
0x180031255  mov     rcx, [rdi+28h]; hMem
0x180031259  test    rcx, rcx
0x18003125c  jz      short loc_180031275
0x18003125e  call    cs:__imp_LocalFree
0x180031264  lea     rcx, [rdi+30h]
0x180031268  mov     [rdi+28h], r15
0x18003126c  mov     [rcx], r15d
0x18003126f  mov     [rdi+20h], r15d
0x180031273  jmp     short loc_180031279
0x180031275  lea     rcx, [rdi+30h]
0x180031279  test    rbx, rbx
0x18003127c  jnz     short loc_180031285
0x18003127e  xor     eax, eax
0x180031280  jmp     loc_180031471
0x180031285  mov     eax, [rbx]
0x180031287  mov     [rdi+20h], eax
0x18003128a  mov     eax, [rbx+10h]
0x18003128d  mov     [rcx], eax
0x18003128f  cmp     [rbx+8], r15
0x180031293  jnz     short loc_18003129D
0x180031295  mov     ebx, r15d
0x180031298  jmp     loc_18003145F
0x18003129d  mov     edx, [rbx]; uBytes
0x18003129f  xor     ecx, ecx; uFlags
0x1800312a1  call    cs:__imp_LocalAlloc
0x1800312a7  mov     [rdi+28h], rax
0x1800312ab  test    rax, rax
0x1800312ae  jz      loc_180031153
0x1800312b4  mov     r8d, [rbx]; Size
0x1800312b7  mov     rcx, rax; void *
0x1800312ba  mov     rdx, [rbx+8]; Src
0x1800312be  call    memcpy_0
0x1800312c3  jmp     short loc_1800312FD
0x1800312c5  lea     rdx, a252919_1; "2.5.29.19"
0x1800312cc  mov     rcx, rbp; String1
0x1800312cf  call    wcscmp_0
0x1800312d4  test    eax, eax
0x1800312d6  jnz     loc_18003145A
0x1800312dc  test    rbx, rbx
0x1800312df  jnz     short loc_1800312EE
0x1800312e1  mov     [rdi+10h], r15
0x1800312e5  mov     [rdi+18h], r15d
0x1800312e9  jmp     loc_180031092
0x1800312ee  movsd   xmm0, qword ptr [rbx]
0x1800312f2  movsd   qword ptr [rdi+10h], xmm0
0x1800312f7  mov     eax, [rbx+8]
0x1800312fa  mov     [rdi+18h], eax
0x1800312fd  lea     r12, aPkicriticalext; "pKICriticalExtensions"
0x180031304  mov     rcx, rdi; this
0x180031307  mov     rdx, r12; unsigned __int16 *
0x18003130a  lea     r8, [rsp+68h+Src]; unsigned __int16 ***
0x18003130f  call    ?GetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCertTypeInfo::GetProperty(ushort const *,ushort * * *)
0x180031314  mov     ebx, eax
0x180031316  test    eax, eax
0x180031318  jz      short loc_180031326
0x18003131a  mov     edx, eax
0x18003131c  mov     ecx, 1A4F0328h
0x180031321  jmp     loc_180031136
0x180031326  mov     r8, [rsp+68h+Src]; unsigned __int16 **
0x18003132b  mov     rdx, rbp; unsigned __int16 *
0x18003132e  and     r14d, 1
0x180031332  call    ?_IsCritical@CCertTypeInfo@@IEAAHPEBGPEAPEBG@Z; CCertTypeInfo::_IsCritical(ushort const *,ushort const * *)
0x180031337  cmp     r14d, eax
0x18003133a  jz      loc_180031295
0x180031340  mov     rcx, [rsp+68h+Src]
0x180031345  mov     esi, r15d
0x180031348  test    rcx, rcx
0x18003134b  jz      short loc_18003135A
0x18003134d  jmp     short loc_180031355
0x18003134f  inc     esi
0x180031351  lea     rcx, [rcx+8]
0x180031355  cmp     [rcx], r15
0x180031358  jnz     short loc_18003134F
0x18003135a  test    r14d, r14d
0x18003135d  jz      short loc_1800313BF
0x18003135f  lea     edx, [rsi+2]
0x180031362  mov     ecx, 40h ; '@'; uFlags
0x180031367  shl     rdx, 3; uBytes
0x18003136b  call    cs:__imp_LocalAlloc
0x180031371  mov     r14, rax
0x180031374  test    rax, rax
0x180031377  jnz     short loc_18003138A
0x180031379  mov     ebx, 8007000Eh
0x18003137e  mov     ecx, 1A6B0328h
0x180031383  mov     edx, ebx
0x180031385  jmp     loc_180031136
0x18003138a  mov     rdx, [rsp+68h+Src]; Src
0x18003138f  test    rdx, rdx
0x180031392  jz      short loc_1800313A3
0x180031394  mov     r8d, esi
0x180031397  mov     rcx, r14; void *
0x18003139a  shl     r8, 3; Size
0x18003139e  call    memcpy_0
0x1800313a3  mov     eax, esi
0x1800313a5  mov     r8, r14; unsigned __int16 **
0x1800313a8  mov     rdx, r12; unsigned __int16 *
0x1800313ab  mov     rcx, rdi; this
0x1800313ae  mov     [r14+rax*8], rbp
0x1800313b2  call    ?SetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAG@Z; CCertTypeInfo::SetProperty(ushort const *,ushort * *)
0x1800313b7  mov     rcx, r14
0x1800313ba  jmp     loc_180031450
0x1800313bf  cmp     [rsp+68h+Src], r15
0x1800313c4  jz      loc_18003146F
0x1800313ca  mov     edx, esi
0x1800313cc  mov     ecx, 40h ; '@'; uFlags
0x1800313d1  shl     rdx, 3; uBytes
0x1800313d5  call    cs:__imp_LocalAlloc
0x1800313db  mov     rsi, rax
0x1800313de  test    rax, rax
0x1800313e1  jnz     short loc_1800313F4
0x1800313e3  mov     ebx, 8007000Eh
0x1800313e8  mov     ecx, 1A830328h
0x1800313ed  mov     edx, ebx
0x1800313ef  jmp     loc_180031136
0x1800313f4  mov     rdx, [rsp+68h+Src]
0x1800313f9  mov     rcx, [rdx]
0x1800313fc  test    rcx, rcx
0x1800313ff  jz      short loc_18003143F
0x180031401  mov     r8d, r15d
0x180031404  mov     r11, rbp
0x180031407  mov     rax, rcx
0x18003140a  sub     r11, rcx
0x18003140d  movzx   r9d, word ptr [rax]
0x180031411  movzx   r10d, word ptr [rax+r11]
0x180031416  sub     r9d, r10d
0x180031419  jnz     short loc_180031424
0x18003141b  add     rax, 2
0x18003141f  test    r10d, r10d
0x180031422  jnz     short loc_18003140D
0x180031424  test    r9d, r9d
0x180031427  jz      short loc_180031433
0x180031429  mov     eax, r8d
0x18003142c  inc     r8d
0x18003142f  mov     [rsi+rax*8], rcx
0x180031433  add     rdx, 8
0x180031437  mov     rcx, [rdx]
0x18003143a  test    rcx, rcx
0x18003143d  jnz     short loc_180031404
0x18003143f  mov     r8, rsi; unsigned __int16 **
0x180031442  mov     rdx, r12; unsigned __int16 *
0x180031445  mov     rcx, rdi; this
0x180031448  call    ?SetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAG@Z; CCertTypeInfo::SetProperty(ushort const *,ushort * *)
0x18003144d  mov     rcx, rsi; hMem
0x180031450  mov     ebx, eax
0x180031452  call    cs:__imp_LocalFree
0x180031458  jmp     short loc_18003145F
0x18003145a  mov     ebx, 80004001h
0x18003145f  mov     rcx, [rsp+68h+Src]; hMem
0x180031464  test    rcx, rcx
0x180031467  jz      short loc_18003146F
0x180031469  call    cs:__imp_LocalFree
0x18003146f  mov     eax, ebx
0x180031471  mov     rbx, [rsp+68h+arg_0]
0x180031476  add     rsp, 30h
0x18003147a  pop     r15
0x18003147c  pop     r14
0x18003147e  pop     r13
0x180031480  pop     r12
0x180031482  pop     rdi
0x180031483  pop     rsi
0x180031484  pop     rbp
0x180031485  retn
```
