# CRTFConverter::ReadFontSubInfo(void)

- ea: `0x180080090`
- end: `0x1800803ce`
- name: `?ReadFontSubInfo@CRTFConverter@@IEAAXXZ`
- size: `830`
- prototype: `void __fastcall(CRTFConverter *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18004cdfc`

## callees

- `0x180025944`
- `0x18002720c`
- `0x1800274a0`
- `0x1800426c8`
- `0x18007ff64`
- `0x180080090`
- `0x180090858`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800800af`
- `KERNEL32!EnterCriticalSection` at `0x1800800af`
- `KERNEL32!LeaveCriticalSection` at `0x1800803c2`

## pseudocode

```c
void __fastcall CRTFConverter::ReadFontSubInfo(CRTFConverter *this)
{
  signed int v1; // ebx
  unsigned __int16 *v2; // rdx
  const unsigned __int16 *v3; // rcx
  signed int ProfileSection; // eax
  __int64 v5; // rdi
  WCHAR *v6; // rax
  WCHAR *v7; // rax
  _WORD *v8; // rcx
  char *v9; // rbx
  int v10; // r13d
  int v11; // eax
  WCHAR *v12; // r12
  unsigned int v13; // edi
  __int64 v14; // r14
  _WORD *v15; // r15
  __int64 i; // rsi
  wchar_t **j; // rdi
  char v18; // al
  char *v19; // rax
  __int64 v20; // rdx
  int v21; // [rsp+40h] [rbp-28h] BYREF
  LPWSTR v22; // [rsp+48h] [rbp-20h] BYREF
  __int64 v23; // [rsp+50h] [rbp-18h] BYREF
  _WORD *v24; // [rsp+58h] [rbp-10h] BYREF
  CRTFConverter *v25; // [rsp+B0h] [rbp+48h] BYREF
  char v26; // [rsp+B8h] [rbp+50h] BYREF
  int v27; // [rsp+C0h] [rbp+58h]
  int v28; // [rsp+C8h] [rbp+60h] BYREF

  v25 = this;
  EnterCriticalSection(&g_CriticalSection);
  if ( CRTFConverter::_ctfi )
    goto LABEL_47;
  v1 = 600;
  CRTFConverter::_pchFontSubInfo = (LPWSTR)CW32System::PvAlloc(0x4B0u, 0);
  if ( !CRTFConverter::_pchFontSubInfo )
    goto LABEL_42;
  while ( 1 )
  {
    ProfileSection = CW32System::GetProfileSection(v3, v2, v1);
    v5 = ProfileSection;
    if ( ProfileSection < v1 - 2 )
      break;
    if ( (v1 & 0x20000000) != 0 )
      goto LABEL_42;
    if ( 2 * v1 < v1 )
      goto LABEL_42;
    v6 = (WCHAR *)CW32System::PvReAlloc(CRTFConverter::_pchFontSubInfo, 4 * v1);
    if ( !v6 )
      goto LABEL_42;
    v1 *= 2;
    CRTFConverter::_pchFontSubInfo = v6;
  }
  if ( ProfileSection )
  {
    v7 = (WCHAR *)CW32System::PvReAlloc(CRTFConverter::_pchFontSubInfo, 2 * ProfileSection);
    if ( !v7 )
      goto LABEL_42;
    CRTFConverter::_pchFontSubInfo = v7;
  }
  else
  {
    *CRTFConverter::_pchFontSubInfo = 0;
  }
  CRTFConverter::_ctfi = 12;
  CRTFConverter::_rgtfi = CW32System::PvAlloc(0x120u, 0);
  v9 = (char *)CRTFConverter::_rgtfi;
  if ( !CRTFConverter::_rgtfi )
  {
LABEL_42:
    if ( CRTFConverter::_pchFontSubInfo )
    {
      CW32System::FreePv(CRTFConverter::_pchFontSubInfo);
      CRTFConverter::_pchFontSubInfo = 0;
    }
    if ( CRTFConverter::_rgtfi )
    {
      CW32System::FreePv(CRTFConverter::_rgtfi);
      CRTFConverter::_rgtfi = 0;
    }
    CRTFConverter::_ctfi = 0;
    goto LABEL_47;
  }
  v10 = 0;
  v22 = CRTFConverter::_pchFontSubInfo;
  v11 = 0;
  v23 = 0;
  v24 = 0;
  v12 = &CRTFConverter::_pchFontSubInfo[v5];
  LOBYTE(v25) = 0;
  v13 = CRTFConverter::_ctfi;
  v26 = 0;
  while ( v22 < v12 && v11 != 2 && v10 != 2 )
  {
    v28 = 0;
    v21 = 0;
    v11 = CRTFConverter::ParseFontName(v8, v22, v12, 61, &v23, &v25, &v28, &v22);
    v27 = v11;
    if ( !v11 )
    {
      v10 = CRTFConverter::ParseFontName(v8, v22, v12, 0, &v24, &v26, &v21, &v22);
      if ( v10 )
        goto LABEL_39;
      v14 = v23;
      v15 = v24;
      if ( v28 )
      {
        v18 = (char)v25;
      }
      else
      {
        v8 = v24;
        for ( i = v23; *v8 == *(_WORD *)i; ++v8 )
          i += 2;
        while ( *v8 )
        {
          if ( *v8 != 32 && *v8 != 9 )
            goto LABEL_39;
          ++v8;
        }
        for ( j = &off_180099490; ; j += 2 )
        {
          if ( !*((_BYTE *)j + 8) )
          {
            v13 = CRTFConverter::_ctfi;
            goto LABEL_39;
          }
          if ( !(unsigned int)CW32System::lstrcmpi((const unsigned __int16 *)(i + 2), *j) )
            break;
        }
        v18 = *((_BYTE *)j + 8);
        v13 = CRTFConverter::_ctfi;
      }
      if ( v21 && v18 != v26 )
        goto LABEL_39;
      v8 = CRTFConverter::_rgtfi;
      v9[16] = v18;
      *((_QWORD *)v9 + 1) = v14;
      *(_QWORD *)v9 = v15;
      v9 += 24;
      if ( -1431655765 * (unsigned int)((v9 - (char *)v8) >> 3) < v13 )
      {
        v11 = v27;
      }
      else
      {
        v19 = (char *)CW32System::PvReAlloc(v8, 24 * (v13 + 4));
        CRTFConverter::_rgtfi = v19;
        if ( !v19 )
          goto LABEL_42;
        v20 = 3LL * CRTFConverter::_ctfi;
        v13 = CRTFConverter::_ctfi + 4;
        CRTFConverter::_ctfi += 4;
        v9 = &v19[8 * v20];
LABEL_39:
        v11 = v27;
      }
    }
  }
  CRTFConverter::_ctfi = -1431655765 * ((v9 - (_BYTE *)CRTFConverter::_rgtfi) >> 3);
  if ( !CRTFConverter::_ctfi )
    goto LABEL_42;
LABEL_47:
  LeaveCriticalSection(&g_CriticalSection);
}

```

## disassembly

```asm
0x180080090  mov     [rsp-40h+arg_0], rcx
0x180080095  push    rbp
0x180080096  push    rbx
0x180080097  push    rsi
0x180080098  push    rdi
0x180080099  push    r12
0x18008009b  push    r13
0x18008009d  push    r14
0x18008009f  push    r15
0x1800800a1  mov     rbp, rsp
0x1800800a4  sub     rsp, 68h
0x1800800a8  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800800af  call    cs:__imp_EnterCriticalSection
0x1800800b6  nop     dword ptr [rax+rax+00h]
0x1800800bb  xor     esi, esi
0x1800800bd  cmp     cs:?_ctfi@CRTFConverter@@1HA, esi; int CRTFConverter::_ctfi
0x1800800c3  jnz     loc_1800803AB
0x1800800c9  xor     edx, edx; unsigned int
0x1800800cb  mov     ecx, 4B0h; unsigned int
0x1800800d0  mov     ebx, 258h
0x1800800d5  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x1800800da  mov     cs:?_pchFontSubInfo@CRTFConverter@@1PEAGEA, rax; ushort * CRTFConverter::_pchFontSubInfo
0x1800800e1  test    rax, rax
0x1800800e4  jz      loc_180080375
0x1800800ea  mov     r8d, ebx; unsigned int
0x1800800ed  call    ?GetProfileSection@CW32System@@SAKPEBGPEAGK@Z; CW32System::GetProfileSection(ushort const *,ushort *,ulong)
0x1800800f2  movsxd  rdi, eax
0x1800800f5  lea     ecx, [rbx-2]
0x1800800f8  cmp     edi, ecx
0x1800800fa  jl      short loc_180080132
0x1800800fc  lea     edi, [rbx+rbx]
0x1800800ff  lea     edx, [rdi+rdi]; unsigned int
0x180080102  test    edx, edx
0x180080104  js      loc_180080375
0x18008010a  cmp     edi, ebx
0x18008010c  jl      loc_180080375
0x180080112  mov     rcx, cs:?_pchFontSubInfo@CRTFConverter@@1PEAGEA; void *
0x180080119  call    ?PvReAlloc@CW32System@@SAPEAXPEAXK@Z; CW32System::PvReAlloc(void *,ulong)
0x18008011e  test    rax, rax
0x180080121  jz      loc_180080375
0x180080127  mov     ebx, edi
0x180080129  mov     cs:?_pchFontSubInfo@CRTFConverter@@1PEAGEA, rax; ushort * CRTFConverter::_pchFontSubInfo
0x180080130  jmp     short loc_1800800EA
0x180080132  test    eax, eax
0x180080134  jnz     short loc_180080142
0x180080136  mov     rax, cs:?_pchFontSubInfo@CRTFConverter@@1PEAGEA; ushort * CRTFConverter::_pchFontSubInfo
0x18008013d  mov     [rax], si
0x180080140  jmp     short loc_180080161
0x180080142  mov     rcx, cs:?_pchFontSubInfo@CRTFConverter@@1PEAGEA; void *
0x180080149  lea     edx, [rdi+rdi]; unsigned int
0x18008014c  call    ?PvReAlloc@CW32System@@SAPEAXPEAXK@Z; CW32System::PvReAlloc(void *,ulong)
0x180080151  test    rax, rax
0x180080154  jz      loc_180080375
0x18008015a  mov     cs:?_pchFontSubInfo@CRTFConverter@@1PEAGEA, rax; ushort * CRTFConverter::_pchFontSubInfo
0x180080161  xor     edx, edx; unsigned int
0x180080163  mov     cs:?_ctfi@CRTFConverter@@1HA, 0Ch; int CRTFConverter::_ctfi
0x18008016d  mov     ecx, 120h; unsigned int
0x180080172  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x180080177  mov     cs:?_rgtfi@CRTFConverter@@1PEAU_tfi@@EA, rax; _tfi * CRTFConverter::_rgtfi
0x18008017e  mov     rbx, rax
0x180080181  test    rax, rax
0x180080184  jz      loc_180080375
0x18008018a  mov     rdx, cs:?_pchFontSubInfo@CRTFConverter@@1PEAGEA; ushort * CRTFConverter::_pchFontSubInfo
0x180080191  mov     r13d, esi
0x180080194  mov     [rbp+var_20], rdx
0x180080198  mov     eax, esi
0x18008019a  mov     [rbp+var_18], rsi
0x18008019e  mov     [rbp+var_10], rsi
0x1800801a2  lea     r12, [rdx+rdi*2]
0x1800801a6  mov     byte ptr [rbp+arg_0], sil
0x1800801aa  mov     edi, cs:?_ctfi@CRTFConverter@@1HA; int CRTFConverter::_ctfi
0x1800801b0  mov     [rbp+arg_8], sil
0x1800801b4  mov     r8, 0AAAAAAAAAAAAAAABh
0x1800801be  mov     rdx, [rbp+var_20]
0x1800801c2  cmp     rdx, r12
0x1800801c5  jnb     loc_18008035C
0x1800801cb  cmp     eax, 2
0x1800801ce  jz      loc_18008035C
0x1800801d4  cmp     r13d, 2
0x1800801d8  jz      loc_18008035C
0x1800801de  lea     rax, [rbp+var_20]
0x1800801e2  mov     [rbp+arg_18], esi
0x1800801e5  mov     [rsp+68h+var_30], rax
0x1800801ea  mov     r9d, 3Dh ; '='
0x1800801f0  lea     rax, [rbp+arg_18]
0x1800801f4  mov     [rbp+var_28], esi
0x1800801f7  mov     [rsp+68h+var_38], rax
0x1800801fc  mov     r8, r12
0x1800801ff  lea     rax, [rbp+arg_0]
0x180080203  mov     [rsp+68h+var_40], rax
0x180080208  lea     rax, [rbp+var_18]
0x18008020c  mov     [rsp+68h+var_48], rax
0x180080211  call    ?ParseFontName@CRTFConverter@@IEBA?AW4PARSEFONTNAME@1@PEAG0GPEAPEAGAEAEAEAH1@Z; CRTFConverter::ParseFontName(ushort *,ushort *,ushort,ushort * *,uchar &,int &,ushort * *)
0x180080216  mov     [rbp+arg_10], eax
0x180080219  test    eax, eax
0x18008021b  jnz     short loc_1800801B4
0x18008021d  mov     rdx, [rbp+var_20]
0x180080221  lea     rax, [rbp+var_20]
0x180080225  mov     [rsp+68h+var_30], rax
0x18008022a  xor     r9d, r9d
0x18008022d  lea     rax, [rbp+var_28]
0x180080231  mov     r8, r12
0x180080234  mov     [rsp+68h+var_38], rax
0x180080239  lea     rax, [rbp+arg_8]
0x18008023d  mov     [rsp+68h+var_40], rax
0x180080242  lea     rax, [rbp+var_10]
0x180080246  mov     [rsp+68h+var_48], rax
0x18008024b  call    ?ParseFontName@CRTFConverter@@IEBA?AW4PARSEFONTNAME@1@PEAG0GPEAPEAGAEAEAEAH1@Z; CRTFConverter::ParseFontName(ushort *,ushort *,ushort,ushort * *,uchar &,int &,ushort * *)
0x180080250  mov     r13d, eax
0x180080253  test    eax, eax
0x180080255  jnz     loc_18008034C
0x18008025b  mov     r14, [rbp+var_18]
0x18008025f  mov     r15, [rbp+var_10]
0x180080263  cmp     [rbp+arg_18], esi
0x180080266  jnz     short loc_1800802DC
0x180080268  movzx   eax, word ptr [r14]
0x18008026c  mov     rcx, r15
0x18008026f  mov     rsi, r14
0x180080272  cmp     [r15], ax
0x180080276  jnz     short loc_180080288
0x180080278  add     rsi, 2
0x18008027c  add     rcx, 2
0x180080280  movzx   eax, word ptr [rsi]
0x180080283  cmp     [rcx], ax
0x180080286  jz      short loc_180080278
0x180080288  xor     eax, eax
0x18008028a  cmp     [rcx], ax
0x18008028d  jz      short loc_1800802A1
0x18008028f  cmp     word ptr [rcx], 20h ; ' '
0x180080293  jz      short loc_18008029B
0x180080295  cmp     word ptr [rcx], 9
0x180080299  jnz     short loc_1800802CB
0x18008029b  add     rcx, 2
0x18008029f  jmp     short loc_18008028A
0x1800802a1  lea     rdi, off_180099490; "cyr"
0x1800802a8  cmp     [rdi+8], al
0x1800802ab  jz      short loc_1800802C5
0x1800802ad  mov     rdx, [rdi]; unsigned __int16 *
0x1800802b0  lea     rcx, [rsi+2]; unsigned __int16 *
0x1800802b4  call    ?lstrcmpi@CW32System@@SAHPEBG0@Z; CW32System::lstrcmpi(ushort const *,ushort const *)
0x1800802b9  test    eax, eax
0x1800802bb  jz      short loc_1800802CF
0x1800802bd  add     rdi, 10h
0x1800802c1  xor     eax, eax
0x1800802c3  jmp     short loc_1800802A8
0x1800802c5  mov     edi, cs:?_ctfi@CRTFConverter@@1HA; int CRTFConverter::_ctfi
0x1800802cb  xor     esi, esi
0x1800802cd  jmp     short loc_18008034C
0x1800802cf  mov     al, [rdi+8]
0x1800802d2  xor     esi, esi
0x1800802d4  mov     edi, cs:?_ctfi@CRTFConverter@@1HA; int CRTFConverter::_ctfi
0x1800802da  jmp     short loc_1800802DF
0x1800802dc  mov     al, byte ptr [rbp+arg_0]
0x1800802df  cmp     [rbp+var_28], esi
0x1800802e2  jz      short loc_1800802E9
0x1800802e4  cmp     al, [rbp+arg_8]
0x1800802e7  jnz     short loc_18008034C
0x1800802e9  mov     rcx, cs:?_rgtfi@CRTFConverter@@1PEAU_tfi@@EA; void *
0x1800802f0  mov     r8, 0AAAAAAAAAAAAAAABh
0x1800802fa  mov     [rbx+10h], al
0x1800802fd  mov     [rbx+8], r14
0x180080301  mov     [rbx], r15
0x180080304  add     rbx, 18h
0x180080308  mov     rax, rbx
0x18008030b  sub     rax, rcx
0x18008030e  sar     rax, 3
0x180080312  imul    rax, r8
0x180080316  cmp     eax, edi
0x180080318  jb      short loc_180080354
0x18008031a  lea     eax, [rdi+4]
0x18008031d  lea     edx, [rax+rax*2]
0x180080320  shl     edx, 3; unsigned int
0x180080323  call    ?PvReAlloc@CW32System@@SAPEAXPEAXK@Z; CW32System::PvReAlloc(void *,ulong)
0x180080328  mov     cs:?_rgtfi@CRTFConverter@@1PEAU_tfi@@EA, rax; _tfi * CRTFConverter::_rgtfi
0x18008032f  test    rax, rax
0x180080332  jz      short loc_180080375
0x180080334  movsxd  rdi, cs:?_ctfi@CRTFConverter@@1HA; int CRTFConverter::_ctfi
0x18008033b  lea     rdx, [rdi+rdi*2]
0x18008033f  add     edi, 4
0x180080342  mov     cs:?_ctfi@CRTFConverter@@1HA, edi; int CRTFConverter::_ctfi
0x180080348  lea     rbx, [rax+rdx*8]
0x18008034c  mov     eax, [rbp+arg_10]
0x18008034f  jmp     loc_1800801B4
0x180080354  mov     eax, [rbp+arg_10]
0x180080357  jmp     loc_1800801BE
0x18008035c  sub     rbx, cs:?_rgtfi@CRTFConverter@@1PEAU_tfi@@EA; _tfi * CRTFConverter::_rgtfi
0x180080363  sar     rbx, 3
0x180080367  imul    rbx, r8
0x18008036b  mov     cs:?_ctfi@CRTFConverter@@1HA, ebx; int CRTFConverter::_ctfi
0x180080371  test    ebx, ebx
0x180080373  jnz     short loc_1800803AB
0x180080375  mov     rcx, cs:?_pchFontSubInfo@CRTFConverter@@1PEAGEA; lpMem
0x18008037c  test    rcx, rcx
0x18008037f  jz      short loc_18008038D
0x180080381  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x180080386  mov     cs:?_pchFontSubInfo@CRTFConverter@@1PEAGEA, rsi; ushort * CRTFConverter::_pchFontSubInfo
0x18008038d  mov     rcx, cs:?_rgtfi@CRTFConverter@@1PEAU_tfi@@EA; lpMem
0x180080394  test    rcx, rcx
0x180080397  jz      short loc_1800803A5
0x180080399  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x18008039e  mov     cs:?_rgtfi@CRTFConverter@@1PEAU_tfi@@EA, rsi; _tfi * CRTFConverter::_rgtfi
0x1800803a5  mov     cs:?_ctfi@CRTFConverter@@1HA, esi; int CRTFConverter::_ctfi
0x1800803ab  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_CriticalSection
0x1800803b2  add     rsp, 68h
0x1800803b6  pop     r15
0x1800803b8  pop     r14
0x1800803ba  pop     r13
0x1800803bc  pop     r12
0x1800803be  pop     rdi
0x1800803bf  pop     rsi
0x1800803c0  pop     rbx
0x1800803c1  pop     rbp
0x1800803c2  jmp     cs:__imp_LeaveCriticalSection
```
