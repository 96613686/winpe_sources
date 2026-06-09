# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)

- ea: `0x1800154e4`
- end: `0x1800159b2`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z`
- size: `1230`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180008670`

## callees

- `0x180008d08`
- `0x1800154e4`
- `0x1800159b8`
- `0x180016350`
- `0x180016a94`
- `0x180016b20`
- `0x180016bb4`
- `0x180016c58`
- `0x18001b522`
- `0x18001b550`
- `0x18001b610`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18001588e`
- `msvcrt!wcscat_s` at `0x18001589f`
- `msvcrt!wcscat_s` at `0x1800158b4`
- `msvcrt!wcscat_s` at `0x1800158d3`
- `msvcrt!wcscat_s` at `0x18001588e`
- `msvcrt!wcscat_s` at `0x18001589f`
- `msvcrt!wcscat_s` at `0x1800158b4`
- `msvcrt!wcscat_s` at `0x1800158d3`
- `msvcrt!free` at `0x180015592`
- `msvcrt!free` at `0x1800157d7`
- `msvcrt!free` at `0x1800157e0`
- `msvcrt!free` at `0x180015808`
- `msvcrt!free` at `0x18001592b`
- `msvcrt!free` at `0x180015946`
- `msvcrt!free` at `0x18001594f`
- `msvcrt!free` at `0x180015965`
- `msvcrt!free` at `0x18001596e`
- `msvcrt!free` at `0x180015981`
- `msvcrt!free` at `0x180015592`
- `msvcrt!free` at `0x1800157d7`
- `msvcrt!free` at `0x1800157e0`
- `msvcrt!free` at `0x180015808`
- `msvcrt!free` at `0x18001592b`
- `msvcrt!free` at `0x180015946`
- `msvcrt!free` at `0x18001594f`
- `msvcrt!free` at `0x180015965`
- `msvcrt!free` at `0x18001596e`
- `msvcrt!free` at `0x180015981`
- `msvcrt!malloc` at `0x18001552c`
- `msvcrt!malloc` at `0x180015581`
- `msvcrt!malloc` at `0x1800157f5`
- `msvcrt!malloc` at `0x18001552c`
- `msvcrt!malloc` at `0x180015581`
- `msvcrt!malloc` at `0x1800157f5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800157a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001591d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800157a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001591d`
- `USER32!CharPrevW` at `0x180015857`
- `USER32!CharPrevW` at `0x180015857`
- `KERNEL32!lstrcmpiW` at `0x18001556e`
- `KERNEL32!lstrcmpiW` at `0x18001556e`
- `KERNEL32!lstrcpynW` at `0x180015879`
- `KERNEL32!lstrcpynW` at `0x180015879`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800155fc`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800155fc`

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
0x1800154e4  push    rbp
0x1800154e6  push    rbx
0x1800154e7  push    rsi
0x1800154e8  push    rdi
0x1800154e9  push    r12
0x1800154eb  push    r13
0x1800154ed  push    r14
0x1800154ef  push    r15
0x1800154f1  sub     rsp, 78h
0x1800154f5  lea     rbp, [rsp+30h]
0x1800154fa  mov     rax, cs:__security_cookie
0x180015501  xor     rax, rbp
0x180015504  mov     [rbp+80h+var_48], rax
0x180015508  mov     r12, rcx
0x18001550b  mov     [rbp+80h+var_68], rcx
0x18001550f  xor     edi, edi
0x180015511  mov     [rbp+80h+var_58], r9
0x180015515  mov     ecx, 2000h; Size
0x18001551a  mov     [rbp+80h+var_70], rdi
0x18001551e  mov     r15, r8
0x180015521  mov     qword ptr [rbp+80h+Data], r8
0x180015525  mov     r13, rdx
0x180015528  mov     [rbp+80h+var_60], rdx
0x18001552c  call    cs:__imp_malloc
0x180015532  mov     rsi, rax
0x180015535  test    rax, rax
0x180015538  jz      short loc_180015598
0x18001553a  mov     rdx, rax; unsigned __int16 *
0x18001553d  mov     rcx, r12; this
0x180015540  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180015545  mov     ebx, eax
0x180015547  test    eax, eax
0x180015549  js      loc_18001594C
0x18001554f  mov     ebx, edi
0x180015551  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180015558  mov     rcx, rsi; Block
0x18001555b  cmp     ebx, 3
0x18001555e  jnb     loc_180015981
0x180015564  movsxd  r14, ebx
0x180015567  add     r14, r14
0x18001556a  mov     rdx, [rax+r14*8]; lpString2
0x18001556e  call    cs:__imp_lstrcmpiW
0x180015574  test    eax, eax
0x180015576  jz      short loc_18001557C
0x180015578  inc     ebx
0x18001557a  jmp     short loc_180015551
0x18001557c  mov     ecx, 2000h; Size
0x180015581  call    cs:__imp_malloc
0x180015587  mov     rdi, rax
0x18001558a  test    rax, rax
0x18001558d  jnz     short loc_1800155A2
0x18001558f  mov     rcx, rsi; Block
0x180015592  call    cs:__imp_free
0x180015598  mov     ebx, 8007000Eh
0x18001559d  jmp     loc_180015955
0x1800155a2  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800155a9  mov     rcx, r12; this
0x1800155ac  movzx   r14d, word ptr [rax+r14*8+8]
0x1800155b2  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800155b7  mov     rdx, rdi; unsigned __int16 *
0x1800155ba  mov     rcx, r12; this
0x1800155bd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800155c2  xor     ecx, ecx
0x1800155c4  mov     ebx, eax
0x1800155c6  test    eax, eax
0x1800155c8  js      loc_180015943
0x1800155ce  lea     eax, [rcx+8]
0x1800155d1  mov     [rbp+80h+pulOut], ecx
0x1800155d4  cmp     r14w, ax
0x1800155d8  jz      loc_1800157AB
0x1800155de  cmp     r14w, 11h
0x1800155e3  jz      short loc_18001562B
0x1800155e5  cmp     r14w, 13h
0x1800155ea  jnz     loc_180015931
0x1800155f0  lea     r9, [rbp+80h+pulOut]; pulOut
0x1800155f4  xor     r8d, r8d; dwFlags
0x1800155f7  xor     edx, edx; lcid
0x1800155f9  mov     rcx, rdi; strIn
0x1800155fc  call    cs:__imp_VarUI4FromStr
0x180015602  mov     eax, [rbp+80h+pulOut]
0x180015605  mov     r9d, 4
0x18001560b  mov     rcx, [r13+0]
0x18001560f  mov     rdx, r15
0x180015612  mov     dword ptr [rbp+80h+Data], eax
0x180015615  lea     rax, [rbp+80h+Data]
0x180015619  mov     [rsp+0B0h+cbData], 4
0x180015621  mov     [rsp+0B0h+lpData], rax
0x180015626  jmp     loc_18001579D
0x18001562b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001562f  inc     rbx
0x180015632  cmp     [rdi+rbx*2], cx
0x180015636  jnz     short loc_18001562F
0x180015638  test    bl, 1
0x18001563b  jnz     loc_1800157D4
0x180015641  mov     eax, ebx
0x180015643  mov     ecx, 2
0x180015648  cdq; unsigned __int64
0x180015649  idiv    ecx
0x18001564b  movsxd  r13, eax
0x18001564e  cmp     r13, 400h
0x180015655  ja      short loc_180015689
0x180015657  mov     rcx, r13; this
0x18001565a  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x18001565f  test    al, al
0x180015661  jz      short loc_180015689
0x180015663  lea     rax, [r13+0Fh]
0x180015667  cmp     rax, r13
0x18001566a  ja      short loc_180015676
0x18001566c  mov     rax, 0FFFFFFFFFFFFFF0h
0x180015676  and     rax, 0FFFFFFFFFFFFFFF0h
0x18001567a  call    _alloca_probe
0x18001567f  sub     rsp, rax
0x180015682  lea     r15, [rsp+0B0h+Data]
0x180015687  jmp     short loc_180015698
0x180015689  mov     rdx, r13
0x18001568c  lea     rcx, [rbp+80h+var_70]
0x180015690  call    ?Allocate@?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAAPEAX_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(unsigned __int64)
0x180015695  mov     r15, rax
0x180015698  test    r15, r15
0x18001569b  jz      loc_1800157D4
0x1800156a1  mov     r8, r13; Size
0x1800156a4  xor     edx, edx; Val
0x1800156a6  mov     rcx, r15; void *
0x1800156a9  call    memset_0
0x1800156ae  xor     eax, eax
0x1800156b0  mov     r9d, eax
0x1800156b3  test    ebx, ebx
0x1800156b5  jle     loc_180015782
0x1800156bb  mov     eax, r9d
0x1800156be  movzx   r8d, word ptr [rdi+rax*2]
0x1800156c3  cmp     r8d, 61h ; 'a'
0x1800156c7  ja      short loc_180015734
0x1800156c9  jz      loc_180015755
0x1800156cf  cmp     r8d, 38h ; '8'
0x1800156d3  ja      short loc_180015708
0x1800156d5  jz      short loc_180015702
0x1800156d7  mov     ecx, r8d
0x1800156da  sub     ecx, 30h ; '0'
0x1800156dd  jz      short loc_180015702
0x1800156df  sub     ecx, 1
0x1800156e2  jz      short loc_180015702
0x1800156e4  sub     ecx, 1
0x1800156e7  jz      short loc_180015702
0x1800156e9  sub     ecx, 1
0x1800156ec  jz      short loc_180015702
0x1800156ee  sub     ecx, 1
0x1800156f1  jz      short loc_180015702
0x1800156f3  sub     ecx, 1
0x1800156f6  jz      short loc_180015702
0x1800156f8  sub     ecx, 1
0x1800156fb  jz      short loc_180015702
0x1800156fd  cmp     ecx, 1
0x180015700  jnz     short loc_180015750
0x180015702  sub     r8b, 30h ; '0'
0x180015706  jmp     short loc_180015759
0x180015708  mov     ecx, r8d
0x18001570b  sub     ecx, 39h ; '9'
0x18001570e  jz      short loc_180015702
0x180015710  sub     ecx, 8
0x180015713  jz      short loc_18001572E
0x180015715  sub     ecx, 1
0x180015718  jz      short loc_18001572E
0x18001571a  sub     ecx, 1
0x18001571d  jz      short loc_18001572E
0x18001571f  sub     ecx, 1
0x180015722  jz      short loc_18001572E
0x180015724  sub     ecx, 1
0x180015727  jz      short loc_18001572E
0x180015729  cmp     ecx, 1
0x18001572c  jnz     short loc_180015750
0x18001572e  sub     r8b, 37h ; '7'
0x180015732  jmp     short loc_180015759
0x180015734  mov     ecx, r8d
0x180015737  sub     ecx, 62h ; 'b'
0x18001573a  jz      short loc_180015755
0x18001573c  sub     ecx, 1
0x18001573f  jz      short loc_180015755
0x180015741  sub     ecx, 1
0x180015744  jz      short loc_180015755
0x180015746  sub     ecx, 1
0x180015749  jz      short loc_180015755
0x18001574b  cmp     ecx, 1
0x18001574e  jz      short loc_180015755
0x180015750  xor     r8b, r8b
0x180015753  jmp     short loc_180015759
0x180015755  sub     r8b, 57h ; 'W'
0x180015759  mov     eax, r9d
0x18001575c  mov     edx, r9d
0x18001575f  and     eax, 1
0x180015762  shr     rdx, 1
0x180015765  shl     eax, 2
0x180015768  mov     ecx, 4
0x18001576d  sub     ecx, eax
0x18001576f  inc     r9d
0x180015772  shl     r8b, cl
0x180015775  or      [rdx+r15], r8b
0x180015779  cmp     r9d, ebx
0x18001577c  jl      loc_1800156BB
0x180015782  mov     rcx, [rbp+80h+var_60]
0x180015786  mov     r9d, 3; dwType
0x18001578c  mov     rdx, qword ptr [rbp+80h+Data]; lpValueName
0x180015790  mov     [rsp+0B0h+cbData], r13d; cbData
0x180015795  mov     [rsp+0B0h+lpData], r15; lpData
0x18001579a  mov     rcx, [rcx]; hKey
0x18001579d  xor     r8d, r8d; Reserved
0x1800157a0  call    cs:__imp_RegSetValueExW
0x1800157a6  jmp     loc_180015931
0x1800157ab  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800157af  mov     r13, rdi
0x1800157b2  mov     r14, rcx
0x1800157b5  cmp     [rbp+80h+arg_20], cl
0x1800157bb  jz      loc_1800158EF
0x1800157c1  mov     rax, rbx
0x1800157c4  inc     rax
0x1800157c7  cmp     [rdi+rax*2], cx
0x1800157cb  jnz     short loc_1800157C4
0x1800157cd  cmp     eax, 0FFEh
0x1800157d2  jle     short loc_1800157F0
0x1800157d4  mov     rcx, rdi; Block
0x1800157d7  call    cs:__imp_free
0x1800157dd  mov     rcx, rsi; Block
0x1800157e0  call    cs:__imp_free
0x1800157e6  mov     ebx, 80004005h
0x1800157eb  jmp     loc_180015955
0x1800157f0  mov     ecx, 2000h; Size
0x1800157f5  call    cs:__imp_malloc
0x1800157fb  mov     r14, rax
0x1800157fe  xor     eax, eax
0x180015800  test    r14, r14
0x180015803  jnz     short loc_180015813
0x180015805  mov     rcx, rdi; Block
0x180015808  call    cs:__imp_free
0x18001580e  jmp     loc_18001558F
0x180015813  mov     rcx, [r12+8]; this
0x180015818  lea     rdx, aModule; "Module"
0x18001581f  mov     [rbp+80h+var_50], rax
0x180015823  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x180015828  mov     r12, rax
0x18001582b  test    rax, rax
0x18001582e  jz      loc_1800158E0
0x180015834  mov     rdx, rax; LPCWSTR
0x180015837  mov     rcx, rdi; lpsz
0x18001583a  call    ?StrStrW@CRegParser@ATL@@KAPEBGPEBG0@Z; ATL::CRegParser::StrStrW(ushort const *,ushort const *)
0x18001583f  mov     r15, rax
0x180015842  test    rax, rax
0x180015845  jz      loc_1800158DC
0x18001584b  cmp     rax, [rbp+80h+var_58]
0x18001584f  jz      short loc_180015863
0x180015851  mov     rdx, rax; lpszCurrent
0x180015854  mov     rcx, rdi; lpszStart
0x180015857  call    cs:__imp_CharPrevW
0x18001585d  cmp     word ptr [rax], 22h ; '"'
0x180015861  jz      short loc_1800158DC
0x180015863  mov     r8, r15
0x180015866  xor     r13d, r13d
0x180015869  sub     r8, rdi
0x18001586c  mov     [r14], r13w
0x180015870  sar     r8, 1; iMaxLength
0x180015873  mov     rdx, rdi; lpString2
0x180015876  mov     rcx, r14; lpString1
0x180015879  call    cs:__imp_lstrcpynW
0x18001587f  lea     r8, Source; "\""
0x180015886  mov     edx, 1000h; SizeInWords
0x18001588b  mov     rcx, r14; Destination
0x18001588e  call    cs:__imp_wcscat_s
0x180015894  mov     r8, r12; Source
0x180015897  mov     edx, 1000h; SizeInWords
0x18001589c  mov     rcx, r14; Destination
0x18001589f  call    cs:__imp_wcscat_s
0x1800158a5  lea     r8, Source; "\""
0x1800158ac  mov     edx, 1000h; SizeInWords
0x1800158b1  mov     rcx, r14; Destination
0x1800158b4  call    cs:__imp_wcscat_s
0x1800158ba  mov     rax, rbx
0x1800158bd  inc     rax
0x1800158c0  cmp     [r12+rax*2], r13w
0x1800158c5  jnz     short loc_1800158BD
0x1800158c7  lea     r8, [r15+rax*2]; Source
0x1800158cb  mov     edx, 1000h; SizeInWords
0x1800158d0  mov     rcx, r14; Destination
0x1800158d3  call    cs:__imp_wcscat_s
0x1800158d9  mov     r13, r14
0x1800158dc  mov     r15, qword ptr [rbp+80h+Data]
0x1800158e0  lea     rcx, [rbp+80h+var_50]
0x1800158e4  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x1800158e9  mov     r12, [rbp+80h+var_68]
0x1800158ed  xor     ecx, ecx
0x1800158ef  inc     rbx
0x1800158f2  cmp     [r13+rbx*2+0], cx
0x1800158f8  jnz     short loc_1800158EF
0x1800158fa  mov     rcx, [rbp+80h+var_60]
0x1800158fe  lea     eax, ds:2[rbx*2]
0x180015905  mov     [rsp+0B0h+cbData], eax; cbData
0x180015909  mov     r9d, 1; dwType
0x18001590f  xor     r8d, r8d; Reserved
0x180015912  mov     [rsp+0B0h+lpData], r13; lpData
0x180015917  mov     rdx, r15; lpValueName
0x18001591a  mov     rcx, [rcx]; hKey
0x18001591d  call    cs:__imp_RegSetValueExW
0x180015923  test    r14, r14
  ... truncated ...
```
