# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)

- ea: `0x1800caa8c`
- end: `0x1800caf5a`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z`
- size: `1230`
- prototype: `__int64 __usercall@<rax>(ATL::CRegParser *__hidden this@<rcx>, struct ATL::CRegKey *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1800d565c`

## callees

- `0x1800472e8`
- `0x1800caa8c`
- `0x1800cb1cc`
- `0x1800d3118`
- `0x1800d787c`
- `0x1800d7908`
- `0x1800d799c`
- `0x1800d90d8`
- `0x180134502`
- `0x180134540`
- `0x180134600`

## import_xrefs

- `msvcrt!free` at `0x1800cab3a`
- `msvcrt!free` at `0x1800cad7f`
- `msvcrt!free` at `0x1800cad88`
- `msvcrt!free` at `0x1800cadb0`
- `msvcrt!free` at `0x1800caed3`
- `msvcrt!free` at `0x1800caeee`
- `msvcrt!free` at `0x1800caef7`
- `msvcrt!free` at `0x1800caf0d`
- `msvcrt!free` at `0x1800caf16`
- `msvcrt!free` at `0x1800caf29`
- `msvcrt!free` at `0x1800cab3a`
- `msvcrt!free` at `0x1800cad7f`
- `msvcrt!free` at `0x1800cad88`
- `msvcrt!free` at `0x1800cadb0`
- `msvcrt!free` at `0x1800caed3`
- `msvcrt!free` at `0x1800caeee`
- `msvcrt!free` at `0x1800caef7`
- `msvcrt!free` at `0x1800caf0d`
- `msvcrt!free` at `0x1800caf16`
- `msvcrt!free` at `0x1800caf29`
- `msvcrt!malloc` at `0x1800caad4`
- `msvcrt!malloc` at `0x1800cab29`
- `msvcrt!malloc` at `0x1800cad9d`
- `msvcrt!malloc` at `0x1800caad4`
- `msvcrt!malloc` at `0x1800cab29`
- `msvcrt!malloc` at `0x1800cad9d`
- `msvcrt!wcscat_s` at `0x1800cae36`
- `msvcrt!wcscat_s` at `0x1800cae47`
- `msvcrt!wcscat_s` at `0x1800cae5c`
- `msvcrt!wcscat_s` at `0x1800cae7b`
- `msvcrt!wcscat_s` at `0x1800cae36`
- `msvcrt!wcscat_s` at `0x1800cae47`
- `msvcrt!wcscat_s` at `0x1800cae5c`
- `msvcrt!wcscat_s` at `0x1800cae7b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800cad48`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800caec5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800cad48`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800caec5`
- `USER32!CharPrevW` at `0x1800cadff`
- `USER32!CharPrevW` at `0x1800cadff`
- `KERNEL32!lstrcmpiW` at `0x1800cab16`
- `KERNEL32!lstrcmpiW` at `0x1800cab16`
- `KERNEL32!lstrcpynW` at `0x1800cae21`
- `KERNEL32!lstrcpynW` at `0x1800cae21`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800caba4`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800caba4`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        bool a5)
{
  ATL::CRegParser *v5; // r12
  const WCHAR *v6; // r15
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rsi
  int Token; // ebx
  unsigned int i; // ebx
  unsigned __int16 *v12; // rdi
  __int16 v13; // r14
  HKEY v14; // rcx
  __int64 v15; // rbx
  unsigned __int64 v16; // rdx
  unsigned __int64 cbData; // r13
  __int64 v18; // rax
  void *v19; // rsp
  BYTE *lpData; // r15
  unsigned int v21; // r9d
  unsigned int v22; // r8d
  char v23; // r8
  unsigned __int64 v24; // rdx
  char v25; // al
  __int64 v26; // rbx
  const BYTE *v27; // r13
  _WORD *v28; // r14
  __int64 v29; // rax
  ATL::CRegObject *v30; // rcx
  const WCHAR *v31; // rax
  const wchar_t *v32; // r12
  unsigned __int16 *v33; // rax
  unsigned __int16 *v34; // r15
  __int64 v35; // rax
  BYTE Data[8]; // [rsp+30h] [rbp+0h] BYREF
  ULONG pulOut; // [rsp+38h] [rbp+8h] BYREF
  __int64 v39; // [rsp+40h] [rbp+10h] BYREF
  ATL::CRegParser *v40; // [rsp+48h] [rbp+18h]
  HKEY *v41; // [rsp+50h] [rbp+20h]
  unsigned __int16 *v42; // [rsp+58h] [rbp+28h]
  __int64 v43; // [rsp+60h] [rbp+30h] BYREF

  v5 = this;
  v40 = this;
  v42 = a4;
  v39 = 0;
  v6 = a3;
  *(_QWORD *)Data = a3;
  v41 = a2;
  v8 = (unsigned __int16 *)malloc(0x2000u);
  v9 = v8;
  if ( !v8 )
    goto LABEL_9;
  Token = ATL::CRegParser::NextToken(v5, v8);
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
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v39);
      return 2147614729LL;
    }
    if ( !lstrcmpiW(v9, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * (int)i]) )
      break;
  }
  v12 = (unsigned __int16 *)malloc(0x2000u);
  if ( !v12 )
    goto LABEL_8;
  v13 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * (int)i + 4);
  ATL::CRegParser::SkipWhiteSpace(v5);
  Token = ATL::CRegParser::NextToken(v5, v12);
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
        v14 = *a2;
        *(_DWORD *)Data = pulOut;
        RegSetValueExW(v14, v6, 0, 4u, Data, 4u);
      }
      goto LABEL_72;
    }
    v15 = -1;
    do
      ++v15;
    while ( v12[v15] );
    if ( (v15 & 1) == 0 )
    {
      v16 = (unsigned int)((int)v15 >> 31);
      cbData = (int)v15 / 2;
      if ( cbData <= 0x400
        && (LODWORD(v16) = (int)v15 % 2,
            ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)((int)v15 / 2), v16)) )
      {
        v18 = cbData + 15;
        if ( cbData + 15 < cbData )
          v18 = 0xFFFFFFFFFFFFFF0LL;
        v19 = alloca(v18 & 0xFFFFFFFFFFFFFFF0uLL);
        lpData = Data;
      }
      else
      {
        lpData = (BYTE *)ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(
                           &v39,
                           cbData);
      }
      if ( lpData )
      {
        memset_0(lpData, 0, cbData);
        v21 = 0;
        if ( (int)v15 <= 0 )
        {
LABEL_52:
          RegSetValueExW(*v41, *(LPCWSTR *)Data, 0, 3u, lpData, cbData);
          goto LABEL_72;
        }
        while ( 2 )
        {
          v22 = v12[v21];
          if ( v22 > 0x61 )
          {
            if ( v22 != 98 && v22 != 99 && v22 != 100 && v22 - 101 >= 2 )
              goto LABEL_49;
          }
          else if ( v22 != 97 )
          {
            if ( v22 > 0x38 )
            {
              if ( v22 == 57 )
                goto LABEL_37;
              if ( v22 != 65 && v22 != 66 && v22 != 67 && v22 != 68 && v22 - 69 > 1 )
                goto LABEL_49;
              v23 = v22 - 55;
            }
            else
            {
              if ( v22 == 56
                || v22 == 48
                || v22 == 49
                || v22 == 50
                || v22 == 51
                || v22 == 52
                || v22 == 53
                || v22 - 54 <= 1 )
              {
LABEL_37:
                v23 = v22 - 48;
                goto LABEL_51;
              }
LABEL_49:
              v23 = 0;
            }
LABEL_51:
            v24 = (unsigned __int64)v21 >> 1;
            v25 = 4 * (v21++ & 1);
            lpData[v24] |= v23 << (4 - v25);
            if ( (int)v21 >= (int)v15 )
              goto LABEL_52;
            continue;
          }
          break;
        }
        v23 = v22 - 87;
        goto LABEL_51;
      }
    }
    goto LABEL_57;
  }
  v26 = -1;
  v27 = (const BYTE *)v12;
  v28 = 0;
  if ( !a5 )
  {
    do
LABEL_69:
      ++v26;
    while ( *(_WORD *)&v27[2 * v26] );
    RegSetValueExW(*v41, v6, 0, 1u, v27, 2 * v26 + 2);
    if ( v28 )
      free(v28);
LABEL_72:
    Token = ATL::CRegParser::NextToken(v5, v42);
    if ( Token >= 0 )
    {
      free(v12);
      free(v9);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v39);
      return 0;
    }
    goto LABEL_73;
  }
  v29 = -1;
  do
    ++v29;
  while ( v12[v29] );
  if ( (int)v29 > 4094 )
  {
LABEL_57:
    free(v12);
    free(v9);
    Token = -2147467259;
    goto LABEL_75;
  }
  v28 = malloc(0x2000u);
  if ( v28 )
  {
    v30 = (ATL::CRegObject *)*((_QWORD *)v5 + 1);
    v43 = 0;
    v31 = ATL::CRegObject::StrFromMap(v30, L"Module");
    v32 = v31;
    if ( v31 )
    {
      v33 = (unsigned __int16 *)ATL::CRegParser::StrStrW(v12, v31);
      v34 = v33;
      if ( v33 && (v33 == v42 || *CharPrevW(v12, v33) != 34) )
      {
        *v28 = 0;
        lstrcpynW(v28, v12, v34 - v12);
        wcscat_s(v28, 0x1000u, L"\"");
        wcscat_s(v28, 0x1000u, v32);
        wcscat_s(v28, 0x1000u, L"\"");
        v35 = -1;
        do
          ++v35;
        while ( v32[v35] );
        wcscat_s(v28, 0x1000u, &v34[v35]);
        v27 = (const BYTE *)v28;
      }
      v6 = *(const WCHAR **)Data;
    }
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v43);
    v5 = v40;
    goto LABEL_69;
  }
  free(v12);
LABEL_8:
  free(v9);
LABEL_9:
  Token = -2147024882;
LABEL_75:
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v39);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x1800caa8c  push    rbp
0x1800caa8e  push    rbx
0x1800caa8f  push    rsi
0x1800caa90  push    rdi
0x1800caa91  push    r12
0x1800caa93  push    r13
0x1800caa95  push    r14
0x1800caa97  push    r15
0x1800caa99  sub     rsp, 78h
0x1800caa9d  lea     rbp, [rsp+30h]
0x1800caaa2  mov     rax, cs:__security_cookie
0x1800caaa9  xor     rax, rbp
0x1800caaac  mov     [rbp+80h+var_48], rax
0x1800caab0  mov     r12, rcx
0x1800caab3  mov     [rbp+80h+var_68], rcx
0x1800caab7  xor     edi, edi
0x1800caab9  mov     [rbp+80h+var_58], r9
0x1800caabd  mov     ecx, 2000h; Size
0x1800caac2  mov     [rbp+80h+var_70], rdi
0x1800caac6  mov     r15, r8
0x1800caac9  mov     qword ptr [rbp+80h+Data], r8
0x1800caacd  mov     r13, rdx
0x1800caad0  mov     [rbp+80h+var_60], rdx
0x1800caad4  call    cs:__imp_malloc
0x1800caada  mov     rsi, rax
0x1800caadd  test    rax, rax
0x1800caae0  jz      short loc_1800CAB40
0x1800caae2  mov     rdx, rax; unsigned __int16 *
0x1800caae5  mov     rcx, r12; this
0x1800caae8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800caaed  mov     ebx, eax
0x1800caaef  test    eax, eax
0x1800caaf1  js      loc_1800CAEF4
0x1800caaf7  mov     ebx, edi
0x1800caaf9  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800cab00  mov     rcx, rsi; Block
0x1800cab03  cmp     ebx, 3
0x1800cab06  jnb     loc_1800CAF29
0x1800cab0c  movsxd  r14, ebx
0x1800cab0f  add     r14, r14
0x1800cab12  mov     rdx, [rax+r14*8]; lpString2
0x1800cab16  call    cs:__imp_lstrcmpiW
0x1800cab1c  test    eax, eax
0x1800cab1e  jz      short loc_1800CAB24
0x1800cab20  inc     ebx
0x1800cab22  jmp     short loc_1800CAAF9
0x1800cab24  mov     ecx, 2000h; Size
0x1800cab29  call    cs:__imp_malloc
0x1800cab2f  mov     rdi, rax
0x1800cab32  test    rax, rax
0x1800cab35  jnz     short loc_1800CAB4A
0x1800cab37  mov     rcx, rsi; Block
0x1800cab3a  call    cs:__imp_free
0x1800cab40  mov     ebx, 8007000Eh
0x1800cab45  jmp     loc_1800CAEFD
0x1800cab4a  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800cab51  mov     rcx, r12; this
0x1800cab54  movzx   r14d, word ptr [rax+r14*8+8]
0x1800cab5a  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800cab5f  mov     rdx, rdi; unsigned __int16 *
0x1800cab62  mov     rcx, r12; this
0x1800cab65  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800cab6a  xor     ecx, ecx
0x1800cab6c  mov     ebx, eax
0x1800cab6e  test    eax, eax
0x1800cab70  js      loc_1800CAEEB
0x1800cab76  lea     eax, [rcx+8]
0x1800cab79  mov     [rbp+80h+pulOut], ecx
0x1800cab7c  cmp     r14w, ax
0x1800cab80  jz      loc_1800CAD53
0x1800cab86  cmp     r14w, 11h
0x1800cab8b  jz      short loc_1800CABD3
0x1800cab8d  cmp     r14w, 13h
0x1800cab92  jnz     loc_1800CAED9
0x1800cab98  lea     r9, [rbp+80h+pulOut]; pulOut
0x1800cab9c  xor     r8d, r8d; dwFlags
0x1800cab9f  xor     edx, edx; lcid
0x1800caba1  mov     rcx, rdi; strIn
0x1800caba4  call    cs:__imp_VarUI4FromStr
0x1800cabaa  mov     eax, [rbp+80h+pulOut]
0x1800cabad  mov     r9d, 4
0x1800cabb3  mov     rcx, [r13+0]
0x1800cabb7  mov     rdx, r15
0x1800cabba  mov     dword ptr [rbp+80h+Data], eax
0x1800cabbd  lea     rax, [rbp+80h+Data]
0x1800cabc1  mov     [rsp+0B0h+cbData], 4
0x1800cabc9  mov     [rsp+0B0h+lpData], rax
0x1800cabce  jmp     loc_1800CAD45
0x1800cabd3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800cabd7  inc     rbx
0x1800cabda  cmp     [rdi+rbx*2], cx
0x1800cabde  jnz     short loc_1800CABD7
0x1800cabe0  test    bl, 1
0x1800cabe3  jnz     loc_1800CAD7C
0x1800cabe9  mov     eax, ebx
0x1800cabeb  mov     ecx, 2
0x1800cabf0  cdq; unsigned __int64
0x1800cabf1  idiv    ecx
0x1800cabf3  movsxd  r13, eax
0x1800cabf6  cmp     r13, 400h
0x1800cabfd  ja      short loc_1800CAC31
0x1800cabff  mov     rcx, r13; this
0x1800cac02  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x1800cac07  test    al, al
0x1800cac09  jz      short loc_1800CAC31
0x1800cac0b  lea     rax, [r13+0Fh]
0x1800cac0f  cmp     rax, r13
0x1800cac12  ja      short loc_1800CAC1E
0x1800cac14  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800cac1e  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800cac22  call    _alloca_probe
0x1800cac27  sub     rsp, rax
0x1800cac2a  lea     r15, [rsp+0B0h+Data]
0x1800cac2f  jmp     short loc_1800CAC40
0x1800cac31  mov     rdx, r13
0x1800cac34  lea     rcx, [rbp+80h+var_70]
0x1800cac38  call    ?Allocate@?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAAPEAX_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(unsigned __int64)
0x1800cac3d  mov     r15, rax
0x1800cac40  test    r15, r15
0x1800cac43  jz      loc_1800CAD7C
0x1800cac49  mov     r8, r13; Size
0x1800cac4c  xor     edx, edx; Val
0x1800cac4e  mov     rcx, r15; void *
0x1800cac51  call    memset_0
0x1800cac56  xor     eax, eax
0x1800cac58  mov     r9d, eax
0x1800cac5b  test    ebx, ebx
0x1800cac5d  jle     loc_1800CAD2A
0x1800cac63  mov     eax, r9d
0x1800cac66  movzx   r8d, word ptr [rdi+rax*2]
0x1800cac6b  cmp     r8d, 61h ; 'a'
0x1800cac6f  ja      short loc_1800CACDC
0x1800cac71  jz      loc_1800CACFD
0x1800cac77  cmp     r8d, 38h ; '8'
0x1800cac7b  ja      short loc_1800CACB0
0x1800cac7d  jz      short loc_1800CACAA
0x1800cac7f  mov     ecx, r8d
0x1800cac82  sub     ecx, 30h ; '0'
0x1800cac85  jz      short loc_1800CACAA
0x1800cac87  sub     ecx, 1
0x1800cac8a  jz      short loc_1800CACAA
0x1800cac8c  sub     ecx, 1
0x1800cac8f  jz      short loc_1800CACAA
0x1800cac91  sub     ecx, 1
0x1800cac94  jz      short loc_1800CACAA
0x1800cac96  sub     ecx, 1
0x1800cac99  jz      short loc_1800CACAA
0x1800cac9b  sub     ecx, 1
0x1800cac9e  jz      short loc_1800CACAA
0x1800caca0  sub     ecx, 1
0x1800caca3  jz      short loc_1800CACAA
0x1800caca5  cmp     ecx, 1
0x1800caca8  jnz     short loc_1800CACF8
0x1800cacaa  sub     r8b, 30h ; '0'
0x1800cacae  jmp     short loc_1800CAD01
0x1800cacb0  mov     ecx, r8d
0x1800cacb3  sub     ecx, 39h ; '9'
0x1800cacb6  jz      short loc_1800CACAA
0x1800cacb8  sub     ecx, 8
0x1800cacbb  jz      short loc_1800CACD6
0x1800cacbd  sub     ecx, 1
0x1800cacc0  jz      short loc_1800CACD6
0x1800cacc2  sub     ecx, 1
0x1800cacc5  jz      short loc_1800CACD6
0x1800cacc7  sub     ecx, 1
0x1800cacca  jz      short loc_1800CACD6
0x1800caccc  sub     ecx, 1
0x1800caccf  jz      short loc_1800CACD6
0x1800cacd1  cmp     ecx, 1
0x1800cacd4  jnz     short loc_1800CACF8
0x1800cacd6  sub     r8b, 37h ; '7'
0x1800cacda  jmp     short loc_1800CAD01
0x1800cacdc  mov     ecx, r8d
0x1800cacdf  sub     ecx, 62h ; 'b'
0x1800cace2  jz      short loc_1800CACFD
0x1800cace4  sub     ecx, 1
0x1800cace7  jz      short loc_1800CACFD
0x1800cace9  sub     ecx, 1
0x1800cacec  jz      short loc_1800CACFD
0x1800cacee  sub     ecx, 1
0x1800cacf1  jz      short loc_1800CACFD
0x1800cacf3  cmp     ecx, 1
0x1800cacf6  jz      short loc_1800CACFD
0x1800cacf8  xor     r8b, r8b
0x1800cacfb  jmp     short loc_1800CAD01
0x1800cacfd  sub     r8b, 57h ; 'W'
0x1800cad01  mov     eax, r9d
0x1800cad04  mov     edx, r9d
0x1800cad07  and     eax, 1
0x1800cad0a  shr     rdx, 1
0x1800cad0d  shl     eax, 2
0x1800cad10  mov     ecx, 4
0x1800cad15  sub     ecx, eax
0x1800cad17  inc     r9d
0x1800cad1a  shl     r8b, cl
0x1800cad1d  or      [rdx+r15], r8b
0x1800cad21  cmp     r9d, ebx
0x1800cad24  jl      loc_1800CAC63
0x1800cad2a  mov     rcx, [rbp+80h+var_60]
0x1800cad2e  mov     r9d, 3; dwType
0x1800cad34  mov     rdx, qword ptr [rbp+80h+Data]; lpValueName
0x1800cad38  mov     [rsp+0B0h+cbData], r13d; cbData
0x1800cad3d  mov     [rsp+0B0h+lpData], r15; lpData
0x1800cad42  mov     rcx, [rcx]; hKey
0x1800cad45  xor     r8d, r8d; Reserved
0x1800cad48  call    cs:__imp_RegSetValueExW
0x1800cad4e  jmp     loc_1800CAED9
0x1800cad53  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800cad57  mov     r13, rdi
0x1800cad5a  mov     r14, rcx
0x1800cad5d  cmp     [rbp+80h+arg_20], cl
0x1800cad63  jz      loc_1800CAE97
0x1800cad69  mov     rax, rbx
0x1800cad6c  inc     rax
0x1800cad6f  cmp     [rdi+rax*2], cx
0x1800cad73  jnz     short loc_1800CAD6C
0x1800cad75  cmp     eax, 0FFEh
0x1800cad7a  jle     short loc_1800CAD98
0x1800cad7c  mov     rcx, rdi; Block
0x1800cad7f  call    cs:__imp_free
0x1800cad85  mov     rcx, rsi; Block
0x1800cad88  call    cs:__imp_free
0x1800cad8e  mov     ebx, 80004005h
0x1800cad93  jmp     loc_1800CAEFD
0x1800cad98  mov     ecx, 2000h; Size
0x1800cad9d  call    cs:__imp_malloc
0x1800cada3  mov     r14, rax
0x1800cada6  xor     eax, eax
0x1800cada8  test    r14, r14
0x1800cadab  jnz     short loc_1800CADBB
0x1800cadad  mov     rcx, rdi; Block
0x1800cadb0  call    cs:__imp_free
0x1800cadb6  jmp     loc_1800CAB37
0x1800cadbb  mov     rcx, [r12+8]; this
0x1800cadc0  lea     rdx, aModule; "Module"
0x1800cadc7  mov     [rbp+80h+var_50], rax
0x1800cadcb  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x1800cadd0  mov     r12, rax
0x1800cadd3  test    rax, rax
0x1800cadd6  jz      loc_1800CAE88
0x1800caddc  mov     rdx, rax; LPCWSTR
0x1800caddf  mov     rcx, rdi; lpsz
0x1800cade2  call    ?StrStrW@CRegParser@ATL@@KAPEBGPEBG0@Z; ATL::CRegParser::StrStrW(ushort const *,ushort const *)
0x1800cade7  mov     r15, rax
0x1800cadea  test    rax, rax
0x1800caded  jz      loc_1800CAE84
0x1800cadf3  cmp     rax, [rbp+80h+var_58]
0x1800cadf7  jz      short loc_1800CAE0B
0x1800cadf9  mov     rdx, rax; lpszCurrent
0x1800cadfc  mov     rcx, rdi; lpszStart
0x1800cadff  call    cs:__imp_CharPrevW
0x1800cae05  cmp     word ptr [rax], 22h ; '"'
0x1800cae09  jz      short loc_1800CAE84
0x1800cae0b  mov     r8, r15
0x1800cae0e  xor     r13d, r13d
0x1800cae11  sub     r8, rdi
0x1800cae14  mov     [r14], r13w
0x1800cae18  sar     r8, 1; iMaxLength
0x1800cae1b  mov     rdx, rdi; lpString2
0x1800cae1e  mov     rcx, r14; lpString1
0x1800cae21  call    cs:__imp_lstrcpynW
0x1800cae27  lea     r8, asc_180162DD0; "\""
0x1800cae2e  mov     edx, 1000h; SizeInWords
0x1800cae33  mov     rcx, r14; Destination
0x1800cae36  call    cs:__imp_wcscat_s
0x1800cae3c  mov     r8, r12; Source
0x1800cae3f  mov     edx, 1000h; SizeInWords
0x1800cae44  mov     rcx, r14; Destination
0x1800cae47  call    cs:__imp_wcscat_s
0x1800cae4d  lea     r8, asc_180162DD0; "\""
0x1800cae54  mov     edx, 1000h; SizeInWords
0x1800cae59  mov     rcx, r14; Destination
0x1800cae5c  call    cs:__imp_wcscat_s
0x1800cae62  mov     rax, rbx
0x1800cae65  inc     rax
0x1800cae68  cmp     [r12+rax*2], r13w
0x1800cae6d  jnz     short loc_1800CAE65
0x1800cae6f  lea     r8, [r15+rax*2]; Source
0x1800cae73  mov     edx, 1000h; SizeInWords
0x1800cae78  mov     rcx, r14; Destination
0x1800cae7b  call    cs:__imp_wcscat_s
0x1800cae81  mov     r13, r14
0x1800cae84  mov     r15, qword ptr [rbp+80h+Data]
0x1800cae88  lea     rcx, [rbp+80h+var_50]
0x1800cae8c  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x1800cae91  mov     r12, [rbp+80h+var_68]
0x1800cae95  xor     ecx, ecx
0x1800cae97  inc     rbx
0x1800cae9a  cmp     [r13+rbx*2+0], cx
0x1800caea0  jnz     short loc_1800CAE97
0x1800caea2  mov     rcx, [rbp+80h+var_60]
0x1800caea6  lea     eax, ds:2[rbx*2]
0x1800caead  mov     [rsp+0B0h+cbData], eax; cbData
0x1800caeb1  mov     r9d, 1; dwType
0x1800caeb7  xor     r8d, r8d; Reserved
0x1800caeba  mov     [rsp+0B0h+lpData], r13; lpData
0x1800caebf  mov     rdx, r15; lpValueName
0x1800caec2  mov     rcx, [rcx]; hKey
0x1800caec5  call    cs:__imp_RegSetValueExW
0x1800caecb  test    r14, r14
  ... truncated ...
```
