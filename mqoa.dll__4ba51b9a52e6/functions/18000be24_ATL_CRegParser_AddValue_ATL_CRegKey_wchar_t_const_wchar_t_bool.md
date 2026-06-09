# ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *,bool)

- ea: `0x18000be24`
- end: `0x18000c2f3`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W_N@Z`
- size: `1231`
- prototype: `__int64 __usercall@<rax>(ATL::CRegParser *__hidden this@<rcx>, struct ATL::CRegKey *@<rdx>, const wchar_t *@<r8>, wchar_t *@<r9>, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180011504`

## callees

- `0x18000aa00`
- `0x18000be24`
- `0x18000c2fc`
- `0x18000fe18`
- `0x1800124f8`
- `0x180012584`
- `0x1800125f0`
- `0x180012ae8`
- `0x18002737e`
- `0x1800273b0`
- `0x180027470`

## import_xrefs

- `msvcrt!free` at `0x18000bed2`
- `msvcrt!free` at `0x18000c115`
- `msvcrt!free` at `0x18000c11e`
- `msvcrt!free` at `0x18000c146`
- `msvcrt!free` at `0x18000c269`
- `msvcrt!free` at `0x18000c284`
- `msvcrt!free` at `0x18000c28d`
- `msvcrt!free` at `0x18000c2a4`
- `msvcrt!free` at `0x18000c2ad`
- `msvcrt!free` at `0x18000c2c1`
- `msvcrt!free` at `0x18000bed2`
- `msvcrt!free` at `0x18000c115`
- `msvcrt!free` at `0x18000c11e`
- `msvcrt!free` at `0x18000c146`
- `msvcrt!free` at `0x18000c269`
- `msvcrt!free` at `0x18000c284`
- `msvcrt!free` at `0x18000c28d`
- `msvcrt!free` at `0x18000c2a4`
- `msvcrt!free` at `0x18000c2ad`
- `msvcrt!free` at `0x18000c2c1`
- `msvcrt!malloc` at `0x18000be6c`
- `msvcrt!malloc` at `0x18000bec1`
- `msvcrt!malloc` at `0x18000c133`
- `msvcrt!malloc` at `0x18000be6c`
- `msvcrt!malloc` at `0x18000bec1`
- `msvcrt!malloc` at `0x18000c133`
- `msvcrt!wcscat_s` at `0x18000c1cc`
- `msvcrt!wcscat_s` at `0x18000c1dd`
- `msvcrt!wcscat_s` at `0x18000c1f2`
- `msvcrt!wcscat_s` at `0x18000c211`
- `msvcrt!wcscat_s` at `0x18000c1cc`
- `msvcrt!wcscat_s` at `0x18000c1dd`
- `msvcrt!wcscat_s` at `0x18000c1f2`
- `msvcrt!wcscat_s` at `0x18000c211`
- `KERNEL32!lstrcmpiW` at `0x18000beae`
- `KERNEL32!lstrcmpiW` at `0x18000beae`
- `KERNEL32!lstrcpynW` at `0x18000c1b7`
- `KERNEL32!lstrcpynW` at `0x18000c1b7`
- `USER32!CharPrevW` at `0x18000c195`
- `USER32!CharPrevW` at `0x18000c195`
- `ADVAPI32!RegSetValueExW` at `0x18000c0de`
- `ADVAPI32!RegSetValueExW` at `0x18000c25b`
- `ADVAPI32!RegSetValueExW` at `0x18000c0de`
- `ADVAPI32!RegSetValueExW` at `0x18000c25b`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000bf3c`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000bf3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::AddValue(ATL::CRegObject **this, HKEY *a2, const wchar_t *a3, wchar_t *a4, bool a5)
{
  const WCHAR *v5; // r15
  ATL::CRegObject **v7; // r12
  wchar_t *v8; // rax
  wchar_t *v9; // rsi
  int Token; // ebx
  unsigned int i; // ebx
  wchar_t *v12; // rdi
  __int16 v13; // r14
  __int64 v14; // rbx
  unsigned __int64 v15; // rdx
  unsigned __int64 cbData; // r13
  __int64 v17; // rax
  void *v18; // rsp
  LPCWSTR *lpData; // r15
  unsigned int v20; // r9d
  unsigned int v21; // edx
  char v22; // r8
  const BYTE *v23; // r13
  _WORD *v24; // r14
  __int64 v25; // rbx
  __int64 v26; // rax
  const WCHAR *v27; // rax
  const wchar_t *v28; // r12
  wchar_t *v29; // rax
  wchar_t *v30; // r15
  __int64 v31; // rax
  LPCWSTR lpValueName; // [rsp+30h] [rbp+0h] BYREF
  ULONG pulOut; // [rsp+38h] [rbp+8h] BYREF
  __int64 v35; // [rsp+40h] [rbp+10h] BYREF
  HKEY *v36; // [rsp+48h] [rbp+18h]
  wchar_t *v37; // [rsp+50h] [rbp+20h]
  __int64 v38; // [rsp+58h] [rbp+28h] BYREF
  ATL::CRegParser *v39; // [rsp+60h] [rbp+30h]

  v37 = a4;
  v5 = a3;
  lpValueName = a3;
  v36 = a2;
  v7 = this;
  v39 = (ATL::CRegParser *)this;
  v35 = 0;
  v8 = (wchar_t *)malloc(0x2000u);
  v9 = v8;
  if ( !v8 )
    goto LABEL_9;
  Token = ATL::CRegParser::NextToken((ATL::CRegParser *)v7, v8);
  if ( Token < 0 )
  {
LABEL_74:
    free(v9);
    goto LABEL_75;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
    {
      free(v9);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v35);
      return 2147614729LL;
    }
    if ( !lstrcmpiW(v9, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * (int)i]) )
      break;
  }
  v12 = (wchar_t *)malloc(0x2000u);
  if ( !v12 )
    goto LABEL_8;
  v13 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * (int)i + 4);
  ATL::CRegParser::SkipWhiteSpace((ATL::CRegParser *)v7);
  Token = ATL::CRegParser::NextToken((ATL::CRegParser *)v7, v12);
  if ( Token < 0 )
  {
LABEL_73:
    free(v12);
    goto LABEL_74;
  }
  pulOut = 0;
  if ( v13 != 8 )
  {
    if ( v13 != 17 )
    {
      if ( v13 == 19 )
      {
        VarUI4FromStr(v12, 0, 0, &pulOut);
        LODWORD(lpValueName) = pulOut;
        RegSetValueExW(*a2, v5, 0, 4u, (const BYTE *)&lpValueName, 4u);
      }
      goto LABEL_72;
    }
    v14 = -1;
    do
      ++v14;
    while ( v12[v14] );
    if ( (v14 & 1) == 0 )
    {
      v15 = (unsigned int)((int)v14 >> 31);
      cbData = (int)v14 / 2;
      if ( cbData <= 0x400
        && (LODWORD(v15) = (int)v14 % 2,
            ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)((int)v14 / 2), v15)) )
      {
        v17 = cbData + 15;
        if ( cbData + 15 < cbData )
          v17 = 0xFFFFFFFFFFFFFF0LL;
        v18 = alloca(v17 & 0xFFFFFFFFFFFFFFF0uLL);
        lpData = &lpValueName;
      }
      else
      {
        lpData = (LPCWSTR *)ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(
                              &v35,
                              cbData);
      }
      if ( lpData )
      {
        memset_0(lpData, 0, cbData);
        v20 = 0;
        if ( (int)v14 <= 0 )
        {
LABEL_52:
          RegSetValueExW(*v36, lpValueName, 0, 3u, (const BYTE *)lpData, cbData);
          goto LABEL_72;
        }
        while ( 2 )
        {
          v21 = v12[v20];
          if ( v21 > 0x61 )
          {
            if ( v21 != 98 && v21 != 99 && v21 != 100 && v21 - 101 >= 2 )
              goto LABEL_49;
          }
          else if ( v21 != 97 )
          {
            if ( v21 > 0x38 )
            {
              if ( v21 == 57 )
                goto LABEL_37;
              if ( v21 != 65 && v21 != 66 && v21 != 67 && v21 != 68 && v21 - 69 > 1 )
                goto LABEL_49;
              v22 = v21 - 55;
            }
            else
            {
              if ( v21 == 56
                || v21 == 48
                || v21 == 49
                || v21 == 50
                || v21 == 51
                || v21 == 52
                || v21 == 53
                || v21 - 54 <= 1 )
              {
LABEL_37:
                v22 = v21 - 48;
                goto LABEL_51;
              }
LABEL_49:
              v22 = 0;
            }
LABEL_51:
            *((_BYTE *)lpData + ((unsigned __int64)v20 >> 1)) |= v22 << (4 - 4 * (v20 & 1));
            if ( (int)++v20 >= (int)v14 )
              goto LABEL_52;
            continue;
          }
          break;
        }
        v22 = v21 - 87;
        goto LABEL_51;
      }
    }
    goto LABEL_57;
  }
  v23 = (const BYTE *)v12;
  v24 = 0;
  v25 = -1;
  if ( !a5 )
  {
    do
LABEL_69:
      ++v25;
    while ( *(_WORD *)&v23[2 * v25] );
    RegSetValueExW(*v36, v5, 0, 1u, v23, 2 * v25 + 2);
    if ( v24 )
      free(v24);
LABEL_72:
    Token = ATL::CRegParser::NextToken((ATL::CRegParser *)v7, v37);
    if ( Token >= 0 )
    {
      free(v12);
      free(v9);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v35);
      return 0;
    }
    goto LABEL_73;
  }
  v26 = -1;
  do
    ++v26;
  while ( v12[v26] );
  if ( (int)v26 > 4094 )
  {
LABEL_57:
    free(v12);
    free(v9);
    Token = -2147467259;
    goto LABEL_75;
  }
  v24 = malloc(0x2000u);
  if ( v24 )
  {
    v38 = 0;
    v27 = ATL::CRegObject::StrFromMap(v7[1], (wchar_t *)L"Module");
    v28 = v27;
    if ( v27 )
    {
      v29 = (wchar_t *)ATL::CRegParser::StrStrW(v12, v27);
      v30 = v29;
      if ( v29 && (v29 == v37 || *CharPrevW(v12, v29) != 34) )
      {
        *v24 = 0;
        lstrcpynW(v24, v12, v30 - v12);
        wcscat_s(v24, 0x1000u, L"\"");
        wcscat_s(v24, 0x1000u, v28);
        wcscat_s(v24, 0x1000u, L"\"");
        v31 = -1;
        do
          ++v31;
        while ( v28[v31] );
        wcscat_s(v24, 0x1000u, &v30[v31]);
        v23 = (const BYTE *)v24;
      }
      v5 = lpValueName;
    }
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v38);
    v7 = (ATL::CRegObject **)v39;
    goto LABEL_69;
  }
  free(v12);
LABEL_8:
  free(v9);
LABEL_9:
  Token = -2147024882;
LABEL_75:
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v35);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x18000be24  push    rbp
0x18000be26  push    rbx
0x18000be27  push    rsi
0x18000be28  push    rdi
0x18000be29  push    r12
0x18000be2b  push    r13
0x18000be2d  push    r14
0x18000be2f  push    r15
0x18000be31  sub     rsp, 78h
0x18000be35  lea     rbp, [rsp+30h]
0x18000be3a  mov     rax, cs:__security_cookie
0x18000be41  xor     rax, rbp
0x18000be44  mov     [rbp+80h+var_48], rax
0x18000be48  mov     [rbp+80h+var_60], r9
0x18000be4c  mov     r15, r8
0x18000be4f  mov     [rbp+80h+lpValueName], r8
0x18000be53  mov     r13, rdx
0x18000be56  mov     [rbp+80h+var_68], rdx
0x18000be5a  mov     r12, rcx
0x18000be5d  mov     [rbp+80h+var_50], rcx
0x18000be61  xor     edi, edi
0x18000be63  mov     [rbp+80h+var_70], rdi
0x18000be67  mov     ecx, 2000h; Size
0x18000be6c  call    cs:__imp_malloc
0x18000be72  mov     rsi, rax
0x18000be75  test    rax, rax
0x18000be78  jz      short loc_18000BED8
0x18000be7a  mov     rdx, rax; wchar_t *
0x18000be7d  mov     rcx, r12; this
0x18000be80  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000be85  mov     ebx, eax
0x18000be87  test    eax, eax
0x18000be89  js      loc_18000C28A
0x18000be8f  mov     ebx, edi
0x18000be91  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEB_WAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::map
0x18000be98  mov     rcx, rsi; Block
0x18000be9b  cmp     ebx, 3
0x18000be9e  jnb     loc_18000C2C1
0x18000bea4  movsxd  r14, ebx
0x18000bea7  add     r14, r14
0x18000beaa  mov     rdx, [rax+r14*8]; lpString2
0x18000beae  call    cs:__imp_lstrcmpiW
0x18000beb4  test    eax, eax
0x18000beb6  jz      short loc_18000BEBC
0x18000beb8  inc     ebx
0x18000beba  jmp     short loc_18000BE91
0x18000bebc  mov     ecx, 2000h; Size
0x18000bec1  call    cs:__imp_malloc
0x18000bec7  mov     rdi, rax
0x18000beca  test    rax, rax
0x18000becd  jnz     short loc_18000BEE2
0x18000becf  mov     rcx, rsi; Block
0x18000bed2  call    cs:__imp_free
0x18000bed8  mov     ebx, 8007000Eh
0x18000bedd  jmp     loc_18000C294
0x18000bee2  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEB_WAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::map
0x18000bee9  movzx   r14d, word ptr [rax+r14*8+8]
0x18000beef  mov     rcx, r12; this
0x18000bef2  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000bef7  mov     rdx, rdi; wchar_t *
0x18000befa  mov     rcx, r12; this
0x18000befd  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000bf02  mov     ebx, eax
0x18000bf04  xor     ecx, ecx
0x18000bf06  test    eax, eax
0x18000bf08  js      loc_18000C281
0x18000bf0e  mov     [rbp+80h+pulOut], ecx
0x18000bf11  lea     eax, [rcx+8]
0x18000bf14  cmp     r14w, ax
0x18000bf18  jz      loc_18000C0E9
0x18000bf1e  cmp     r14w, 11h
0x18000bf23  jz      short loc_18000BF6B
0x18000bf25  cmp     r14w, 13h
0x18000bf2a  jnz     loc_18000C26F
0x18000bf30  lea     r9, [rbp+80h+pulOut]; pulOut
0x18000bf34  xor     r8d, r8d; dwFlags
0x18000bf37  xor     edx, edx; lcid
0x18000bf39  mov     rcx, rdi; strIn
0x18000bf3c  call    cs:__imp_VarUI4FromStr
0x18000bf42  mov     eax, [rbp+80h+pulOut]
0x18000bf45  mov     dword ptr [rbp+80h+lpValueName], eax
0x18000bf48  mov     [rsp+0B0h+cbData], 4
0x18000bf50  lea     rax, [rbp+80h+lpValueName]
0x18000bf54  mov     [rsp+0B0h+lpData], rax
0x18000bf59  mov     r9d, 4
0x18000bf5f  mov     rdx, r15
0x18000bf62  mov     rcx, [r13+0]
0x18000bf66  jmp     loc_18000C0DB
0x18000bf6b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000bf6f  inc     rbx
0x18000bf72  cmp     [rdi+rbx*2], cx
0x18000bf76  jnz     short loc_18000BF6F
0x18000bf78  test    bl, 1
0x18000bf7b  jnz     loc_18000C112
0x18000bf81  mov     eax, ebx
0x18000bf83  cdq; unsigned __int64
0x18000bf84  mov     ecx, 2
0x18000bf89  idiv    ecx
0x18000bf8b  movsxd  r13, eax
0x18000bf8e  cmp     r13, 400h
0x18000bf95  ja      short loc_18000BFC9
0x18000bf97  mov     rcx, r13; this
0x18000bf9a  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x18000bf9f  test    al, al
0x18000bfa1  jz      short loc_18000BFC9
0x18000bfa3  lea     rax, [r13+0Fh]
0x18000bfa7  cmp     rax, r13
0x18000bfaa  ja      short loc_18000BFB6
0x18000bfac  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000bfb6  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000bfba  call    _alloca_probe
0x18000bfbf  sub     rsp, rax
0x18000bfc2  lea     r15, [rsp+0B0h+lpValueName]
0x18000bfc7  jmp     short loc_18000BFD8
0x18000bfc9  mov     rdx, r13
0x18000bfcc  lea     rcx, [rbp+80h+var_70]
0x18000bfd0  call    ?Allocate@?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAAPEAX_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(unsigned __int64)
0x18000bfd5  mov     r15, rax
0x18000bfd8  test    r15, r15
0x18000bfdb  jz      loc_18000C112
0x18000bfe1  mov     r8, r13; Size
0x18000bfe4  xor     edx, edx; Val
0x18000bfe6  mov     rcx, r15; void *
0x18000bfe9  call    memset_0
0x18000bfee  xor     r10d, r10d
0x18000bff1  mov     r9d, r10d
0x18000bff4  test    ebx, ebx
0x18000bff6  jle     loc_18000C0C0
0x18000bffc  mov     eax, r9d
0x18000bfff  movzx   edx, word ptr [rdi+rax*2]
0x18000c003  cmp     edx, 61h ; 'a'
0x18000c006  ja      short loc_18000C073
0x18000c008  jz      loc_18000C093
0x18000c00e  cmp     edx, 38h ; '8'
0x18000c011  ja      short loc_18000C045
0x18000c013  jz      short loc_18000C03F
0x18000c015  mov     ecx, edx
0x18000c017  sub     ecx, 30h ; '0'
0x18000c01a  jz      short loc_18000C03F
0x18000c01c  sub     ecx, 1
0x18000c01f  jz      short loc_18000C03F
0x18000c021  sub     ecx, 1
0x18000c024  jz      short loc_18000C03F
0x18000c026  sub     ecx, 1
0x18000c029  jz      short loc_18000C03F
0x18000c02b  sub     ecx, 1
0x18000c02e  jz      short loc_18000C03F
0x18000c030  sub     ecx, 1
0x18000c033  jz      short loc_18000C03F
0x18000c035  sub     ecx, 1
0x18000c038  jz      short loc_18000C03F
0x18000c03a  cmp     ecx, 1
0x18000c03d  jnz     short loc_18000C08E
0x18000c03f  lea     r8d, [rdx-30h]
0x18000c043  jmp     short loc_18000C097
0x18000c045  mov     r8d, edx
0x18000c048  mov     ecx, edx
0x18000c04a  sub     ecx, 39h ; '9'
0x18000c04d  jz      short loc_18000C03F
0x18000c04f  sub     ecx, 8
0x18000c052  jz      short loc_18000C06D
0x18000c054  sub     ecx, 1
0x18000c057  jz      short loc_18000C06D
0x18000c059  sub     ecx, 1
0x18000c05c  jz      short loc_18000C06D
0x18000c05e  sub     ecx, 1
0x18000c061  jz      short loc_18000C06D
0x18000c063  sub     ecx, 1
0x18000c066  jz      short loc_18000C06D
0x18000c068  cmp     ecx, 1
0x18000c06b  jnz     short loc_18000C08E
0x18000c06d  add     r8d, 0FFFFFFC9h
0x18000c071  jmp     short loc_18000C097
0x18000c073  mov     ecx, edx
0x18000c075  sub     ecx, 62h ; 'b'
0x18000c078  jz      short loc_18000C093
0x18000c07a  sub     ecx, 1
0x18000c07d  jz      short loc_18000C093
0x18000c07f  sub     ecx, 1
0x18000c082  jz      short loc_18000C093
0x18000c084  sub     ecx, 1
0x18000c087  jz      short loc_18000C093
0x18000c089  cmp     ecx, 1
0x18000c08c  jz      short loc_18000C093
0x18000c08e  mov     r8d, r10d
0x18000c091  jmp     short loc_18000C097
0x18000c093  lea     r8d, [rdx-57h]
0x18000c097  mov     edx, r9d
0x18000c09a  shr     rdx, 1
0x18000c09d  mov     eax, r9d
0x18000c0a0  and     eax, 1
0x18000c0a3  shl     eax, 2
0x18000c0a6  mov     ecx, 4
0x18000c0ab  sub     ecx, eax
0x18000c0ad  shl     r8b, cl
0x18000c0b0  or      [rdx+r15], r8b
0x18000c0b4  inc     r9d
0x18000c0b7  cmp     r9d, ebx
0x18000c0ba  jl      loc_18000BFFC
0x18000c0c0  mov     [rsp+0B0h+cbData], r13d; cbData
0x18000c0c5  mov     [rsp+0B0h+lpData], r15; lpData
0x18000c0ca  mov     r9d, 3; dwType
0x18000c0d0  mov     rdx, [rbp+80h+lpValueName]; lpValueName
0x18000c0d4  mov     rcx, [rbp+80h+var_68]
0x18000c0d8  mov     rcx, [rcx]; hKey
0x18000c0db  xor     r8d, r8d; Reserved
0x18000c0de  call    cs:__imp_RegSetValueExW
0x18000c0e4  jmp     loc_18000C26F
0x18000c0e9  mov     r13, rdi
0x18000c0ec  mov     r14, rcx
0x18000c0ef  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000c0f3  cmp     [rbp+80h+arg_20], cl
0x18000c0f9  jz      loc_18000C22D
0x18000c0ff  mov     rax, rbx
0x18000c102  inc     rax
0x18000c105  cmp     [rdi+rax*2], cx
0x18000c109  jnz     short loc_18000C102
0x18000c10b  cmp     eax, 0FFEh
0x18000c110  jle     short loc_18000C12E
0x18000c112  mov     rcx, rdi; Block
0x18000c115  call    cs:__imp_free
0x18000c11b  mov     rcx, rsi; Block
0x18000c11e  call    cs:__imp_free
0x18000c124  mov     ebx, 80004005h
0x18000c129  jmp     loc_18000C294
0x18000c12e  mov     ecx, 2000h; Size
0x18000c133  call    cs:__imp_malloc
0x18000c139  mov     r14, rax
0x18000c13c  xor     eax, eax
0x18000c13e  test    r14, r14
0x18000c141  jnz     short loc_18000C151
0x18000c143  mov     rcx, rdi; Block
0x18000c146  call    cs:__imp_free
0x18000c14c  jmp     loc_18000BECF
0x18000c151  mov     [rbp+80h+var_58], rax
0x18000c155  lea     rdx, aModule; "Module"
0x18000c15c  mov     rcx, [r12+8]; this
0x18000c161  call    ?StrFromMap@CRegObject@ATL@@QEAAPEB_WPEA_W@Z; ATL::CRegObject::StrFromMap(wchar_t *)
0x18000c166  mov     r12, rax
0x18000c169  test    rax, rax
0x18000c16c  jz      loc_18000C21E
0x18000c172  mov     rdx, rax; LPCWSTR
0x18000c175  mov     rcx, rdi; lpsz
0x18000c178  call    ?StrStrW@CRegParser@ATL@@KAPEB_WPEB_W0@Z; ATL::CRegParser::StrStrW(wchar_t const *,wchar_t const *)
0x18000c17d  mov     r15, rax
0x18000c180  test    rax, rax
0x18000c183  jz      loc_18000C21A
0x18000c189  cmp     rax, [rbp+80h+var_60]
0x18000c18d  jz      short loc_18000C1A1
0x18000c18f  mov     rdx, rax; lpszCurrent
0x18000c192  mov     rcx, rdi; lpszStart
0x18000c195  call    cs:__imp_CharPrevW
0x18000c19b  cmp     word ptr [rax], 22h ; '"'
0x18000c19f  jz      short loc_18000C21A
0x18000c1a1  xor     r13d, r13d
0x18000c1a4  mov     [r14], r13w
0x18000c1a8  mov     r8, r15
0x18000c1ab  sub     r8, rdi
0x18000c1ae  sar     r8, 1; iMaxLength
0x18000c1b1  mov     rdx, rdi; lpString2
0x18000c1b4  mov     rcx, r14; lpString1
0x18000c1b7  call    cs:__imp_lstrcpynW
0x18000c1bd  lea     r8, Source; "\""
0x18000c1c4  mov     edx, 1000h; SizeInWords
0x18000c1c9  mov     rcx, r14; Destination
0x18000c1cc  call    cs:__imp_wcscat_s
0x18000c1d2  mov     r8, r12; Source
0x18000c1d5  mov     edx, 1000h; SizeInWords
0x18000c1da  mov     rcx, r14; Destination
0x18000c1dd  call    cs:__imp_wcscat_s
0x18000c1e3  lea     r8, Source; "\""
0x18000c1ea  mov     edx, 1000h; SizeInWords
0x18000c1ef  mov     rcx, r14; Destination
0x18000c1f2  call    cs:__imp_wcscat_s
0x18000c1f8  mov     rax, rbx
0x18000c1fb  inc     rax
0x18000c1fe  cmp     [r12+rax*2], r13w
0x18000c203  jnz     short loc_18000C1FB
0x18000c205  lea     r8, [r15+rax*2]; Source
0x18000c209  mov     edx, 1000h; SizeInWords
0x18000c20e  mov     rcx, r14; Destination
0x18000c211  call    cs:__imp_wcscat_s
0x18000c217  mov     r13, r14
0x18000c21a  mov     r15, [rbp+80h+lpValueName]
0x18000c21e  lea     rcx, [rbp+80h+var_58]
0x18000c222  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x18000c227  mov     r12, [rbp+80h+var_50]
0x18000c22b  xor     ecx, ecx
0x18000c22d  inc     rbx
0x18000c230  cmp     [r13+rbx*2+0], cx
0x18000c236  jnz     short loc_18000C22D
0x18000c238  lea     eax, ds:2[rbx*2]
0x18000c23f  mov     [rsp+0B0h+cbData], eax; cbData
0x18000c243  mov     [rsp+0B0h+lpData], r13; lpData
0x18000c248  mov     r9d, 1; dwType
0x18000c24e  xor     r8d, r8d; Reserved
0x18000c251  mov     rdx, r15; lpValueName
0x18000c254  mov     rcx, [rbp+80h+var_68]
0x18000c258  mov     rcx, [rcx]; hKey
0x18000c25b  call    cs:__imp_RegSetValueExW
  ... truncated ...
```
