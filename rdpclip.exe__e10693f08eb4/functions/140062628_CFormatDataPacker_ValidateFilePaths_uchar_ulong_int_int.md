# CFormatDataPacker::ValidateFilePaths(uchar *,ulong,int,int *)

- ea: `0x140062628`
- end: `0x140062b81`
- name: `?ValidateFilePaths@CFormatDataPacker@@AEAAJPEAEKHPEAH@Z`
- size: `1369`
- prototype: `__int64 __fastcall(CFormatDataPacker *__hidden this, unsigned __int8 *, unsigned int, int, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x1400614c8`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005750`
- `0x1400620ec`
- `0x140062628`
- `0x14006a120`

## import_xrefs

- `msvcrt!wcsnlen` at `0x140062808`
- `msvcrt!wcsnlen` at `0x140062808`
- `msvcrt!strnlen` at `0x1400628d1`
- `msvcrt!strnlen` at `0x1400628d1`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x14006286a`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x14006286a`

## string_xrefs

- `0x140062a66`: `PathCchCanonicalizeA failed.`
- `0x14006299a`: `PathCchCanonicalize failed.`

## pseudocode

```c
__int64 __fastcall CFormatDataPacker::ValidateFilePaths(
        CFormatDataPacker *this,
        unsigned __int8 *a2,
        unsigned int a3,
        int a4,
        int *a5)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v8; // rdx
  unsigned int v9; // ebx
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rbp
  unsigned int v13; // eax
  unsigned int v14; // ecx
  unsigned int i; // esi
  unsigned __int8 *v16; // rcx
  unsigned __int8 *v17; // rbx
  size_t v18; // rax
  unsigned __int64 v19; // r8
  __int64 v20; // rcx
  WCHAR v21; // ax
  WCHAR *v22; // rax
  int v23; // ecx
  int v24; // edx
  unsigned __int8 *v25; // rcx
  unsigned __int8 *v26; // rbx
  size_t v27; // rax
  unsigned __int64 v28; // r8
  unsigned __int64 v29; // rdx
  char v30; // al
  unsigned int v31; // eax
  unsigned int v32; // eax
  __int64 v33; // rdx
  unsigned int v34; // eax
  unsigned int v35; // eax
  char v37[272]; // [rsp+30h] [rbp-678h] BYREF
  char v38[272]; // [rsp+140h] [rbp-568h] BYREF
  WCHAR pszPathIn[264]; // [rsp+250h] [rbp-458h] BYREF
  WCHAR pszPathOut[264]; // [rsp+460h] [rbp-248h] BYREF

  if ( !a5 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024809;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 39;
LABEL_6:
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      &WPP_f92c957a97133e2e821460ff528c58fd_Traceguids,
      CurrentThreadActivityIdPrefix);
    return (unsigned int)-2147024809;
  }
  *a5 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024809;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 40;
    goto LABEL_6;
  }
  if ( a3 < 4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 41;
      goto LABEL_18;
    }
    return (unsigned int)-2092629015;
  }
  v12 = *(unsigned int *)a2;
  if ( !(_DWORD)v12 )
  {
    v9 = 0;
    *a5 = 1;
    return v9;
  }
  if ( a4 )
  {
    if ( (unsigned __int64)(592 * v12) <= 0xFFFFFFFF )
    {
      v13 = 592 * v12 + 4;
LABEL_27:
      if ( a3 < v13 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = RdpWppGetCurrentThreadActivityIdPrefix();
          v11 = 44;
          goto LABEL_18;
        }
        return (unsigned int)-2092629015;
      }
      for ( i = 0; ; ++i )
      {
        if ( i >= (unsigned int)v12 )
        {
          *a5 = 1;
          return 0;
        }
        if ( a4 )
        {
          v16 = &a2[592 * i + 4];
          if ( !v16 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v32 = RdpWppGetCurrentThreadActivityIdPrefix();
              v33 = 45;
              goto LABEL_71;
            }
            return (unsigned int)-2147467261;
          }
          v17 = v16 + 72;
          if ( v16 == (unsigned __int8 *)-72LL || (v18 = wcsnlen((const wchar_t *)v16 + 36, 0x104u), v18 - 1 > 0x102) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v10 = RdpWppGetCurrentThreadActivityIdPrefix();
              v11 = 46;
              goto LABEL_18;
            }
            return (unsigned int)-2092629015;
          }
          v19 = v18 + 1;
          v20 = 0;
          if ( v18 != -1 )
          {
            do
            {
              v21 = *(_WORD *)&v17[2 * v20];
              if ( v21 == 47 )
                v21 = 92;
              pszPathIn[v20] = v21;
              v20 = (unsigned int)(v20 + 1);
            }
            while ( (unsigned int)v20 < v19 );
          }
          v9 = PathCchCanonicalize(pszPathOut, 0x104u, pszPathIn);
          if ( (v9 & 0x80000000) != 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v31 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                47,
                (unsigned int)&WPP_f92c957a97133e2e821460ff528c58fd_Traceguids,
                v31,
                (__int64)"PathCchCanonicalize failed.",
                v9);
            }
            return v9;
          }
          v22 = pszPathOut;
          do
          {
            v23 = *(WCHAR *)((char *)v22 + (char *)pszPathIn - (char *)pszPathOut);
            v24 = *v22 - v23;
            if ( v24 )
              break;
            ++v22;
          }
          while ( v23 );
        }
        else
        {
          v25 = &a2[332 * i + 4];
          if ( !v25 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v32 = RdpWppGetCurrentThreadActivityIdPrefix();
              v33 = 48;
LABEL_71:
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v33, &WPP_f92c957a97133e2e821460ff528c58fd_Traceguids, v32);
            }
            return (unsigned int)-2147467261;
          }
          v26 = v25 + 72;
          if ( v25 == (unsigned __int8 *)-72LL || (v27 = strnlen((const char *)v25 + 72, 0x104u), v27 - 1 > 0x102) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v10 = RdpWppGetCurrentThreadActivityIdPrefix();
              v11 = 49;
LABEL_18:
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_f92c957a97133e2e821460ff528c58fd_Traceguids, v10);
            }
            return (unsigned int)-2092629015;
          }
          v28 = v27 + 1;
          v29 = 0;
          if ( v27 != -1 )
          {
            do
            {
              v30 = v26[v29];
              if ( v30 == 47 )
                v30 = 92;
              v37[v29] = v30;
              v29 = (unsigned int)(v29 + 1);
            }
            while ( (unsigned int)v29 < v28 );
          }
          v9 = PathCchCanonicalizeA(v38, v29, v37);
          if ( (v9 & 0x80000000) != 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v34 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                50,
                (unsigned int)&WPP_f92c957a97133e2e821460ff528c58fd_Traceguids,
                v34,
                (__int64)"PathCchCanonicalizeA failed.",
                v9);
            }
            return v9;
          }
          v24 = strcmp(v38, v37);
        }
        if ( v24 )
        {
          v9 = 0;
          *a5 = 0;
          return v9;
        }
      }
    }
    return (unsigned int)-2147024362;
  }
  v14 = 332 * v12;
  if ( (unsigned __int64)(332 * v12) > 0xFFFFFFFF )
    return (unsigned int)-2147024362;
  v13 = v14 + 4;
  if ( v14 < 0xFFFFFFFC )
    goto LABEL_27;
  v9 = -2147024362;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v35 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      43,
      (unsigned int)&WPP_f92c957a97133e2e821460ff528c58fd_Traceguids,
      v35,
      (__int64)"UIntAdd failed",
      22);
  }
  return v9;
}

```

## disassembly

```asm
0x140062628  mov     [rsp+arg_0], rbx
0x14006262d  mov     [rsp+arg_10], rbp
0x140062632  push    rsi
0x140062633  push    rdi
0x140062634  push    r13
0x140062636  push    r14
0x140062638  push    r15
0x14006263a  sub     rsp, 680h
0x140062641  mov     rax, cs:__security_cookie
0x140062648  xor     rax, rsp
0x14006264b  mov     [rsp+6A8h+var_38], rax
0x140062653  mov     rdi, [rsp+6A8h+arg_20]
0x14006265b  mov     r15d, r9d
0x14006265e  mov     r14, rdx
0x140062661  test    rdi, rdi
0x140062664  jnz     short loc_1400626B1
0x140062666  mov     rcx, cs:WPP_GLOBAL_Control
0x14006266d  lea     rax, WPP_GLOBAL_Control
0x140062674  cmp     rcx, rax
0x140062677  jz      short loc_1400626A7
0x140062679  test    byte ptr [rcx+1Ch], 1
0x14006267d  jz      short loc_1400626A7
0x14006267f  cmp     byte ptr [rcx+19h], 2
0x140062683  jb      short loc_1400626A7
0x140062685  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006268a  lea     edx, [rdi+27h]
0x14006268d  mov     rcx, cs:WPP_GLOBAL_Control
0x140062694  lea     r8, WPP_f92c957a97133e2e821460ff528c58fd_Traceguids
0x14006269b  mov     r9d, eax
0x14006269e  mov     rcx, [rcx+10h]
0x1400626a2  call    WPP_SF_d
0x1400626a7  mov     ebx, 80070057h
0x1400626ac  jmp     loc_140062B53
0x1400626b1  mov     dword ptr [rdi], 0
0x1400626b7  test    r14, r14
0x1400626ba  jnz     short loc_1400626E6
0x1400626bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400626c3  lea     rax, WPP_GLOBAL_Control
0x1400626ca  cmp     rcx, rax
0x1400626cd  jz      short loc_1400626A7
0x1400626cf  test    byte ptr [rcx+1Ch], 1
0x1400626d3  jz      short loc_1400626A7
0x1400626d5  cmp     byte ptr [rcx+19h], 2
0x1400626d9  jb      short loc_1400626A7
0x1400626db  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400626e0  lea     edx, [r14+28h]
0x1400626e4  jmp     short loc_14006268D
0x1400626e6  cmp     r8d, 4
0x1400626ea  jnb     short loc_140062739
0x1400626ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400626f3  lea     rax, WPP_GLOBAL_Control
0x1400626fa  cmp     rcx, rax
0x1400626fd  jz      short loc_14006272F
0x1400626ff  test    byte ptr [rcx+1Ch], 1
0x140062703  jz      short loc_14006272F
0x140062705  cmp     byte ptr [rcx+19h], 2
0x140062709  jb      short loc_14006272F
0x14006270b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140062710  mov     edx, 29h ; ')'
0x140062715  mov     rcx, cs:WPP_GLOBAL_Control
0x14006271c  lea     r8, WPP_f92c957a97133e2e821460ff528c58fd_Traceguids
0x140062723  mov     r9d, eax
0x140062726  mov     rcx, [rcx+10h]
0x14006272a  call    WPP_SF_d
0x14006272f  mov     ebx, 834503E9h
0x140062734  jmp     loc_140062B53
0x140062739  mov     ebp, [rdx]
0x14006273b  test    ebp, ebp
0x14006273d  jnz     short loc_14006274C
0x14006273f  xor     ebx, ebx
0x140062741  mov     dword ptr [rdi], 1
0x140062747  jmp     loc_140062B53
0x14006274c  mov     rax, rbp
0x14006274f  test    r15d, r15d
0x140062752  jz      short loc_14006276E
0x140062754  imul    rcx, rax, 250h
0x14006275b  mov     eax, 0FFFFFFFFh
0x140062760  cmp     rcx, rax
0x140062763  ja      loc_140062B4E
0x140062769  lea     eax, [rcx+4]
0x14006276c  jmp     short loc_14006278F
0x14006276e  imul    rcx, rax, 14Ch
0x140062775  mov     eax, 0FFFFFFFFh
0x14006277a  cmp     rcx, rax
0x14006277d  ja      loc_140062B4E
0x140062783  lea     eax, [rcx+4]
0x140062786  cmp     eax, 4
0x140062789  jb      loc_140062AF0
0x14006278f  cmp     r8d, eax
0x140062792  jnb     short loc_1400627C6
0x140062794  mov     rcx, cs:WPP_GLOBAL_Control
0x14006279b  lea     rax, WPP_GLOBAL_Control
0x1400627a2  cmp     rcx, rax
0x1400627a5  jz      short loc_14006272F
0x1400627a7  test    byte ptr [rcx+1Ch], 1
0x1400627ab  jz      short loc_14006272F
0x1400627ad  cmp     byte ptr [rcx+19h], 2
0x1400627b1  jb      loc_14006272F
0x1400627b7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400627bc  mov     edx, 2Ch ; ','
0x1400627c1  jmp     loc_140062715
0x1400627c6  xor     esi, esi
0x1400627c8  mov     r13d, 104h
0x1400627ce  cmp     esi, ebp
0x1400627d0  jnb     loc_140062AE6
0x1400627d6  mov     eax, esi
0x1400627d8  test    r15d, r15d
0x1400627db  jz      loc_1400628AA
0x1400627e1  imul    rcx, rax, 250h
0x1400627e8  add     rcx, 4
0x1400627ec  add     rcx, r14
0x1400627ef  jz      loc_1400629E0
0x1400627f5  lea     rbx, [rcx+48h]
0x1400627f9  test    rbx, rbx
0x1400627fc  jz      loc_1400629A6
0x140062802  mov     rdx, r13; MaxCount
0x140062805  mov     rcx, rbx; Source
0x140062808  call    cs:__imp_wcsnlen
0x14006280e  lea     rcx, [rax-1]
0x140062812  cmp     rcx, 102h
0x140062819  ja      loc_1400629A6
0x14006281f  lea     r8, [rax+1]
0x140062823  xor     ecx, ecx
0x140062825  test    r8, r8
0x140062828  jz      short loc_140062857
0x14006282a  lea     r9d, [rcx+2Fh]
0x14006282e  lea     r13d, [rcx+5Ch]
0x140062832  movzx   eax, word ptr [rbx+rcx*2]
0x140062836  cmp     ax, r9w
0x14006283a  jnz     short loc_140062840
0x14006283c  movzx   eax, r13w
0x140062840  mov     [rsp+rcx*2+6A8h+pszPathIn], ax
0x140062848  inc     ecx
0x14006284a  mov     eax, ecx
0x14006284c  cmp     rax, r8
0x14006284f  jb      short loc_140062832
0x140062851  mov     r13d, 104h
0x140062857  lea     r8, [rsp+6A8h+pszPathIn]; pszPathIn
0x14006285f  mov     rdx, r13; cchPathOut
0x140062862  lea     rcx, [rsp+6A8h+pszPathOut]; pszPathOut
0x14006286a  call    cs:__imp_PathCchCanonicalize
0x140062870  mov     ebx, eax
0x140062872  test    eax, eax
0x140062874  js      loc_140062961
0x14006287a  lea     rax, [rsp+6A8h+pszPathOut]
0x140062882  lea     r8, [rsp+6A8h+pszPathIn]
0x14006288a  sub     r8, rax
0x14006288d  movzx   edx, word ptr [rax]
0x140062890  movzx   ecx, word ptr [rax+r8]
0x140062895  sub     edx, ecx
0x140062897  jnz     loc_14006294D
0x14006289d  add     rax, 2
0x1400628a1  test    ecx, ecx
0x1400628a3  jnz     short loc_14006288D
0x1400628a5  jmp     loc_14006294D
0x1400628aa  imul    rcx, rax, 14Ch
0x1400628b1  add     rcx, 4
0x1400628b5  add     rcx, r14
0x1400628b8  jz      loc_140062AAC
0x1400628be  lea     rbx, [rcx+48h]
0x1400628c2  test    rbx, rbx
0x1400628c5  jz      loc_140062A72
0x1400628cb  mov     rdx, r13; MaxCount
0x1400628ce  mov     rcx, rbx; String
0x1400628d1  call    cs:__imp_strnlen
0x1400628d7  lea     rcx, [rax-1]
0x1400628db  cmp     rcx, 102h
0x1400628e2  ja      loc_140062A72
0x1400628e8  lea     r8, [rax+1]
0x1400628ec  xor     edx, edx
0x1400628ee  test    r8, r8
0x1400628f1  jz      short loc_14006290E
0x1400628f3  lea     r9d, [rdx+5Ch]
0x1400628f7  movzx   eax, byte ptr [rdx+rbx]
0x1400628fb  cmp     al, 2Fh ; '/'
0x1400628fd  cmovz   eax, r9d
0x140062901  mov     [rsp+rdx+6A8h+var_678], al
0x140062905  inc     edx; unsigned __int64
0x140062907  mov     eax, edx
0x140062909  cmp     rax, r8
0x14006290c  jb      short loc_1400628F7
0x14006290e  lea     r8, [rsp+6A8h+var_678]; char *
0x140062913  lea     rcx, [rsp+6A8h+var_568]; char *
0x14006291b  call    ?PathCchCanonicalizeA@@YAJPEAD_KPEBD@Z; PathCchCanonicalizeA(char *,unsigned __int64,char const *)
0x140062920  mov     ebx, eax
0x140062922  test    eax, eax
0x140062924  js      loc_140062A2D
0x14006292a  lea     rax, [rsp+6A8h+var_568]
0x140062932  lea     r8, [rsp+6A8h+var_678]
0x140062937  sub     r8, rax
0x14006293a  movzx   edx, byte ptr [rax]
0x14006293d  movzx   ecx, byte ptr [rax+r8]
0x140062942  sub     edx, ecx
0x140062944  jnz     short loc_14006294D
0x140062946  inc     rax
0x140062949  test    ecx, ecx
0x14006294b  jnz     short loc_14006293A
0x14006294d  test    edx, edx
0x14006294f  jnz     short loc_140062958
0x140062951  inc     esi
0x140062953  jmp     loc_1400627CE
0x140062958  xor     ebx, ebx
0x14006295a  mov     [rdi], ebx
0x14006295c  jmp     loc_140062B53
0x140062961  mov     rcx, cs:WPP_GLOBAL_Control
0x140062968  lea     rax, WPP_GLOBAL_Control
0x14006296f  cmp     rcx, rax
0x140062972  jz      loc_140062B53
0x140062978  test    byte ptr [rcx+1Ch], 8
0x14006297c  jz      loc_140062B53
0x140062982  cmp     byte ptr [rcx+19h], 2
0x140062986  jb      loc_140062B53
0x14006298c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140062991  mov     edx, 2Fh ; '/'
0x140062996  mov     [rsp+6A8h+var_680], ebx
0x14006299a  lea     rcx, aPathcchcanonic_0; "PathCchCanonicalize failed."
0x1400629a1  jmp     loc_140062B2D
0x1400629a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400629ad  lea     rax, WPP_GLOBAL_Control
0x1400629b4  cmp     rcx, rax
0x1400629b7  jz      loc_14006272F
0x1400629bd  test    byte ptr [rcx+1Ch], 1
0x1400629c1  jz      loc_14006272F
0x1400629c7  cmp     byte ptr [rcx+19h], 2
0x1400629cb  jb      loc_14006272F
0x1400629d1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400629d6  mov     edx, 2Eh ; '.'
0x1400629db  jmp     loc_140062715
0x1400629e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400629e7  lea     rax, WPP_GLOBAL_Control
0x1400629ee  cmp     rcx, rax
0x1400629f1  jz      short loc_140062A23
0x1400629f3  test    byte ptr [rcx+1Ch], 1
0x1400629f7  jz      short loc_140062A23
0x1400629f9  cmp     byte ptr [rcx+19h], 2
0x1400629fd  jb      short loc_140062A23
0x1400629ff  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140062a04  mov     edx, 2Dh ; '-'
0x140062a09  mov     rcx, cs:WPP_GLOBAL_Control
0x140062a10  lea     r8, WPP_f92c957a97133e2e821460ff528c58fd_Traceguids
0x140062a17  mov     r9d, eax
0x140062a1a  mov     rcx, [rcx+10h]
0x140062a1e  call    WPP_SF_d
0x140062a23  mov     ebx, 80004003h
0x140062a28  jmp     loc_140062B53
0x140062a2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140062a34  lea     rax, WPP_GLOBAL_Control
0x140062a3b  cmp     rcx, rax
0x140062a3e  jz      loc_140062B53
0x140062a44  test    byte ptr [rcx+1Ch], 8
0x140062a48  jz      loc_140062B53
0x140062a4e  cmp     byte ptr [rcx+19h], 2
0x140062a52  jb      loc_140062B53
0x140062a58  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140062a5d  mov     edx, 32h ; '2'
0x140062a62  mov     [rsp+6A8h+var_680], ebx
0x140062a66  lea     rcx, aPathcchcanonic; "PathCchCanonicalizeA failed."
0x140062a6d  jmp     loc_140062B2D
0x140062a72  mov     rcx, cs:WPP_GLOBAL_Control
0x140062a79  lea     rax, WPP_GLOBAL_Control
0x140062a80  cmp     rcx, rax
0x140062a83  jz      loc_14006272F
0x140062a89  test    byte ptr [rcx+1Ch], 1
0x140062a8d  jz      loc_14006272F
0x140062a93  cmp     byte ptr [rcx+19h], 2
0x140062a97  jb      loc_14006272F
0x140062a9d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140062aa2  mov     edx, 31h ; '1'
0x140062aa7  jmp     loc_140062715
0x140062aac  mov     rcx, cs:WPP_GLOBAL_Control
0x140062ab3  lea     rax, WPP_GLOBAL_Control
0x140062aba  cmp     rcx, rax
0x140062abd  jz      loc_140062A23
0x140062ac3  test    byte ptr [rcx+1Ch], 1
0x140062ac7  jz      loc_140062A23
0x140062acd  cmp     byte ptr [rcx+19h], 2
0x140062ad1  jb      loc_140062A23
0x140062ad7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140062adc  mov     edx, 30h ; '0'
0x140062ae1  jmp     loc_140062A09
0x140062ae6  mov     dword ptr [rdi], 1
0x140062aec  xor     ebx, ebx
0x140062aee  jmp     short loc_140062B53
0x140062af0  mov     ebx, 80070216h
0x140062af5  mov     rcx, cs:WPP_GLOBAL_Control
0x140062afc  lea     rax, WPP_GLOBAL_Control
0x140062b03  cmp     rcx, rax
0x140062b06  jz      short loc_140062B53
0x140062b08  test    byte ptr [rcx+1Ch], 8
0x140062b0c  jz      short loc_140062B53
0x140062b0e  cmp     byte ptr [rcx+19h], 2
0x140062b12  jb      short loc_140062B53
0x140062b14  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140062b19  mov     edx, 2Bh ; '+'
0x140062b1e  mov     [rsp+6A8h+var_680], 80070216h
0x140062b26  lea     rcx, aUintaddFailed; "UIntAdd failed"
0x140062b2d  mov     [rsp+6A8h+var_688], rcx
0x140062b32  lea     r8, WPP_f92c957a97133e2e821460ff528c58fd_Traceguids
0x140062b39  mov     rcx, cs:WPP_GLOBAL_Control
0x140062b40  mov     r9d, eax
  ... truncated ...
```
