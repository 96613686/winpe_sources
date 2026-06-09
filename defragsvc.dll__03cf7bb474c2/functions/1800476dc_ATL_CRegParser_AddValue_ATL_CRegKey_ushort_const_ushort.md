# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800476dc`
- end: `0x180047aad`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `977`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1800493b8`

## callees

- `0x180047054`
- `0x180047080`
- `0x1800471f0`
- `0x1800476dc`
- `0x180047ab4`
- `0x180047d44`
- `0x1800480c4`
- `0x180048910`
- `0x180049c08`
- `0x180067b0a`
- `0x180067b30`
- `0x180067bf0`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800478de`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800478de`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800478a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047922`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047a17`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047a61`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800478a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047922`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047a17`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047a61`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18004782a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180047846`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18004782a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180047846`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004774a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004774a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  ATL::CRegParser *v7; // r12
  __int64 result; // rax
  int v9; // ebx
  __int16 v10; // bx
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  BYTE *v13; // rbx
  WCHAR *v14; // rsi
  const WCHAR *v15; // rax
  DWORD cbData; // r9d
  BYTE *v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rcx
  LSTATUS v20; // ebx
  HRESULT v21; // ebx
  HKEY v22; // rcx
  __int64 v23; // rdi
  size_t v24; // rsi
  unsigned __int64 v25; // rax
  BYTE *v26; // rcx
  int i; // r10d
  unsigned __int8 v28; // al
  int v29; // r10d
  char v30; // dl
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rdi
  int Token; // eax
  unsigned int v35; // ecx
  ULONG pulOut; // [rsp+30h] [rbp-D0h] BYREF
  ATL::CRegParser *v37; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *lpData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v40[264]; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR String1[4096]; // [rsp+160h] [rbp+60h] BYREF

  v37 = this;
  v7 = this;
  result = ATL::CRegParser::NextToken(this, String1);
  if ( (int)result >= 0 )
  {
    v9 = 0;
    while ( lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
    {
      if ( (unsigned int)++v9 >= 4 )
        return 2147614729LL;
    }
    v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
    ATL::CRegParser::SkipWhiteSpace(v7);
    result = ATL::CRegParser::NextToken(v7, String1);
    if ( (int)result >= 0 )
    {
      if ( v10 == 8 )
      {
        v33 = -1;
        do
          ++v33;
        while ( String1[v33] );
        v20 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)String1, 2 * v33 + 2);
        goto LABEL_49;
      }
      if ( v10 != 17 )
      {
        if ( v10 == 19 )
        {
          pulOut = 0;
          v37 = 0;
          v21 = VarUI4FromStr(String1, 0, 0, &pulOut);
          if ( v21 < 0 )
          {
            ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v37);
            return (unsigned int)v21;
          }
          v22 = *a2;
          *(_DWORD *)Data = pulOut;
          v20 = RegSetValueExW(v22, a3, 0, 4u, Data, 4u);
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v37);
        }
        else
        {
          if ( v10 != 16392 )
          {
LABEL_51:
            Token = ATL::CRegParser::NextToken(v7, a4);
            v35 = 0;
            if ( Token < 0 )
              return (unsigned int)Token;
            return v35;
          }
          lpData = 0;
          v11 = -1;
          do
            ++v11;
          while ( String1[v11] );
          v12 = ATL::AtlMultiplyThrow<unsigned __int64>((int)v11 + 2, 2);
          if ( v12 <= 0x100 )
          {
            v13 = v40;
            lpData = v40;
          }
          else
          {
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v12);
            v13 = lpData;
          }
          if ( v13 )
          {
            v14 = String1;
            if ( String1[0] )
            {
              do
              {
                v15 = CharNextW(v14);
                if ( *v14 == 92 && *v15 == 48 )
                {
                  *(_WORD *)v13 = 0;
                  v14 = CharNextW(v15);
                }
                else
                {
                  *(_WORD *)v13 = *v14++;
                }
                v13 += 2;
              }
              while ( *v14 );
              v7 = v37;
            }
            *(_DWORD *)v13 = 0;
            cbData = 0;
            v17 = lpData;
            do
            {
              v18 = -1;
              do
                ++v18;
              while ( *(_WORD *)&v17[2 * v18] );
              v19 = (unsigned int)(v18 + 1);
              v17 += 2 * v19;
              cbData += 2 * v19;
            }
            while ( (_DWORD)v19 != 1 );
            v20 = RegSetValueExW(*a2, a3, 0, 7u, lpData, cbData);
          }
          else
          {
            v20 = 14;
          }
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        }
LABEL_49:
        if ( v20 )
          return ATL::AtlHresultFromWin32(v20);
        goto LABEL_51;
      }
      v23 = -1;
      do
        ++v23;
      while ( String1[v23] );
      if ( (v23 & 1) == 0 )
      {
        lpData = 0;
        v24 = (int)v23 / 2;
        v25 = ATL::AtlMultiplyThrow<unsigned __int64>(v24, 1);
        if ( v25 <= 0x100 )
        {
          v26 = v40;
          lpData = v40;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v25);
          v26 = lpData;
        }
        if ( v26 )
        {
          memset_0(v26, 0, v24);
          for ( i = 0; i < (int)v23; *(_BYTE *)(v32 + v31) |= v28 << (4 - 4 * v30) )
          {
            v28 = ATL::CRegParser::ChToByte(String1[i]);
            v30 = v29 & 1;
            i = v29 + 1;
          }
          v20 = RegSetValueExW(*a2, a3, 0, 3u, lpData, v24);
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
          goto LABEL_49;
        }
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      }
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800476dc  push    rbp
0x1800476de  push    rbx
0x1800476df  push    rsi
0x1800476e0  push    rdi
0x1800476e1  push    r12
0x1800476e3  push    r13
0x1800476e5  push    r14
0x1800476e7  push    r15
0x1800476e9  lea     rbp, [rsp-2078h]
0x1800476f1  mov     eax, 2178h
0x1800476f6  call    _alloca_probe
0x1800476fb  sub     rsp, rax
0x1800476fe  mov     rax, cs:__security_cookie
0x180047705  xor     rax, rsp
0x180047708  mov     [rbp+20B0h+var_50], rax
0x18004770f  mov     r14, rdx
0x180047712  mov     [rsp+21B0h+var_2178], rcx
0x180047717  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x18004771b  mov     r13, r9
0x18004771e  mov     r15, r8
0x180047721  mov     r12, rcx
0x180047724  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180047729  xor     esi, esi
0x18004772b  test    eax, eax
0x18004772d  js      loc_180047A8A
0x180047733  mov     ebx, esi
0x180047735  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18004773c  movsxd  rdi, ebx
0x18004773f  lea     rcx, [rbp+20B0h+String1]; lpString1
0x180047743  add     rdi, rdi
0x180047746  mov     rdx, [rax+rdi*8]; lpString2
0x18004774a  call    cs:__imp_lstrcmpiW
0x180047750  test    eax, eax
0x180047752  jz      short loc_18004776C
0x180047754  inc     ebx
0x180047756  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18004775d  cmp     ebx, 4
0x180047760  jb      short loc_18004773C
0x180047762  mov     eax, 80020009h
0x180047767  jmp     loc_180047A8A
0x18004776c  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180047773  mov     rcx, r12; this
0x180047776  movzx   ebx, word ptr [rbx+rdi*8+8]
0x18004777b  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180047780  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x180047784  mov     rcx, r12; this
0x180047787  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18004778c  test    eax, eax
0x18004778e  js      loc_180047A8A
0x180047794  cmp     bx, 8
0x180047798  jz      loc_180047A2D
0x18004779e  cmp     bx, 11h
0x1800477a2  jz      loc_180047939
0x1800477a8  cmp     bx, 13h
0x1800477ac  jz      loc_1800478C7
0x1800477b2  mov     eax, 4008h
0x1800477b7  cmp     bx, ax
0x1800477ba  jnz     loc_180047A76
0x1800477c0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800477c4  mov     [rsp+21B0h+var_2160], rsi
0x1800477c9  mov     rax, rdi
0x1800477cc  lea     rcx, [rbp+20B0h+String1]
0x1800477d0  inc     rax
0x1800477d3  cmp     [rcx+rax*2], si
0x1800477d7  jnz     short loc_1800477D0
0x1800477d9  add     eax, 2
0x1800477dc  mov     edx, 2
0x1800477e1  movsxd  rcx, eax
0x1800477e4  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800477e9  cmp     rax, 100h
0x1800477ef  jbe     short loc_180047805
0x1800477f1  mov     rdx, rax
0x1800477f4  lea     rcx, [rsp+21B0h+var_2160]
0x1800477f9  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800477fe  mov     rbx, [rsp+21B0h+var_2160]
0x180047803  jmp     short loc_18004780F
0x180047805  lea     rbx, [rsp+21B0h+var_2158]
0x18004780a  mov     [rsp+21B0h+var_2160], rbx
0x18004780f  test    rbx, rbx
0x180047812  jz      loc_1800478B3
0x180047818  xor     eax, eax
0x18004781a  lea     rsi, [rbp+20B0h+String1]
0x18004781e  cmp     [rbp+20B0h+String1], ax
0x180047822  jz      short loc_180047867
0x180047824  xor     r12d, r12d
0x180047827  mov     rcx, rsi; lpsz
0x18004782a  call    cs:__imp_CharNextW
0x180047830  movzx   ecx, word ptr [rsi]
0x180047833  cmp     cx, 5Ch ; '\'
0x180047837  jnz     short loc_180047851
0x180047839  cmp     word ptr [rax], 30h ; '0'
0x18004783d  jnz     short loc_180047851
0x18004783f  mov     rcx, rax; lpsz
0x180047842  mov     [rbx], r12w
0x180047846  call    cs:__imp_CharNextW
0x18004784c  mov     rsi, rax
0x18004784f  jmp     short loc_180047858
0x180047851  mov     [rbx], cx
0x180047854  add     rsi, 2
0x180047858  add     rbx, 2
0x18004785c  cmp     [rsi], r12w
0x180047860  jnz     short loc_180047827
0x180047862  mov     r12, [rsp+21B0h+var_2178]
0x180047867  xor     esi, esi
0x180047869  mov     [rbx], esi
0x18004786b  mov     r9d, esi
0x18004786e  mov     r10, [rsp+21B0h+var_2160]
0x180047873  mov     r8, r10
0x180047876  mov     rcx, rdi
0x180047879  inc     rcx
0x18004787c  cmp     [r8+rcx*2], si
0x180047881  jnz     short loc_180047879
0x180047883  inc     ecx
0x180047885  lea     r8, [r8+rcx*2]
0x180047889  lea     r9d, [r9+rcx*2]
0x18004788d  cmp     ecx, 1
0x180047890  jnz     short loc_180047876
0x180047892  mov     [rsp+21B0h+cbData], r9d; cbData
0x180047897  xor     r8d, r8d; Reserved
0x18004789a  lea     r9d, [rcx+6]; dwType
0x18004789e  mov     [rsp+21B0h+lpData], r10; lpData
0x1800478a3  mov     rcx, [r14]; hKey
0x1800478a6  mov     rdx, r15; lpValueName
0x1800478a9  call    cs:__imp_RegSetValueExW
0x1800478af  mov     ebx, eax
0x1800478b1  jmp     short loc_1800478B8
0x1800478b3  mov     ebx, 0Eh
0x1800478b8  lea     rcx, [rsp+21B0h+var_2160]
0x1800478bd  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800478c2  jmp     loc_180047A69
0x1800478c7  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x1800478cc  mov     [rsp+21B0h+pulOut], esi
0x1800478d0  xor     r8d, r8d; dwFlags
0x1800478d3  mov     [rsp+21B0h+var_2178], rsi
0x1800478d8  xor     edx, edx; lcid
0x1800478da  lea     rcx, [rbp+20B0h+String1]; strIn
0x1800478de  call    cs:__imp_VarUI4FromStr
0x1800478e4  mov     ebx, eax
0x1800478e6  test    eax, eax
0x1800478e8  jns     short loc_1800478FB
0x1800478ea  lea     rcx, [rsp+21B0h+var_2178]
0x1800478ef  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800478f4  mov     eax, ebx
0x1800478f6  jmp     loc_180047A8A
0x1800478fb  mov     eax, [rsp+21B0h+pulOut]
0x1800478ff  mov     ecx, 4
0x180047904  mov     [rsp+21B0h+cbData], ecx; cbData
0x180047908  mov     r9d, ecx; dwType
0x18004790b  mov     rcx, [r14]; hKey
0x18004790e  xor     r8d, r8d; Reserved
0x180047911  mov     dword ptr [rsp+21B0h+Data], eax
0x180047915  mov     rdx, r15; lpValueName
0x180047918  lea     rax, [rsp+21B0h+Data]
0x18004791d  mov     [rsp+21B0h+lpData], rax; lpData
0x180047922  call    cs:__imp_RegSetValueExW
0x180047928  lea     rcx, [rsp+21B0h+var_2178]
0x18004792d  mov     ebx, eax
0x18004792f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180047934  jmp     loc_180047A69
0x180047939  lea     rax, [rbp+20B0h+String1]
0x18004793d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180047941  inc     rdi
0x180047944  cmp     [rax+rdi*2], si
0x180047948  jnz     short loc_180047941
0x18004794a  test    dil, 1
0x18004794e  jz      short loc_18004795A
0x180047950  mov     eax, 80004005h
0x180047955  jmp     loc_180047A8A
0x18004795a  mov     eax, edi
0x18004795c  mov     [rsp+21B0h+var_2160], 0
0x180047965  cdq
0x180047966  sub     eax, edx
0x180047968  mov     edx, 1
0x18004796d  sar     eax, 1
0x18004796f  movsxd  rsi, eax
0x180047972  mov     rcx, rsi
0x180047975  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18004797a  cmp     rax, 100h
0x180047980  jbe     short loc_180047996
0x180047982  mov     rdx, rax
0x180047985  lea     rcx, [rsp+21B0h+var_2160]
0x18004798a  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18004798f  mov     rcx, [rsp+21B0h+var_2160]
0x180047994  jmp     short loc_1800479A0
0x180047996  lea     rcx, [rsp+21B0h+var_2158]; void *
0x18004799b  mov     [rsp+21B0h+var_2160], rcx
0x1800479a0  test    rcx, rcx
0x1800479a3  jnz     short loc_1800479B1
0x1800479a5  lea     rcx, [rsp+21B0h+var_2160]
0x1800479aa  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800479af  jmp     short loc_180047950
0x1800479b1  mov     r8, rsi; Size
0x1800479b4  xor     edx, edx; Val
0x1800479b6  call    memset_0
0x1800479bb  xor     eax, eax
0x1800479bd  mov     r10d, eax
0x1800479c0  test    edi, edi
0x1800479c2  jle     short loc_1800479FA
0x1800479c4  mov     r8, [rsp+21B0h+var_2160]
0x1800479c9  mov     ecx, r10d
0x1800479cc  mov     r9d, r10d
0x1800479cf  shr     r9, 1
0x1800479d2  movzx   ecx, [rbp+rcx*2+20B0h+String1]; unsigned __int16
0x1800479d7  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x1800479dc  mov     edx, r10d
0x1800479df  mov     ecx, 4
0x1800479e4  and     edx, 1
0x1800479e7  inc     r10d
0x1800479ea  shl     edx, 2
0x1800479ed  sub     ecx, edx
0x1800479ef  shl     al, cl
0x1800479f1  or      [r9+r8], al
0x1800479f5  cmp     r10d, edi
0x1800479f8  jl      short loc_1800479C4
0x1800479fa  mov     rax, [rsp+21B0h+var_2160]
0x1800479ff  mov     r9d, 3; dwType
0x180047a05  mov     rcx, [r14]; hKey
0x180047a08  xor     r8d, r8d; Reserved
0x180047a0b  mov     [rsp+21B0h+cbData], esi; cbData
0x180047a0f  mov     rdx, r15; lpValueName
0x180047a12  mov     [rsp+21B0h+lpData], rax; lpData
0x180047a17  call    cs:__imp_RegSetValueExW
0x180047a1d  lea     rcx, [rsp+21B0h+var_2160]
0x180047a22  mov     ebx, eax
0x180047a24  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180047a29  xor     esi, esi
0x180047a2b  jmp     short loc_180047A69
0x180047a2d  lea     rax, [rbp+20B0h+String1]
0x180047a31  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180047a35  inc     rdi
0x180047a38  cmp     [rax+rdi*2], si
0x180047a3c  jnz     short loc_180047A35
0x180047a3e  mov     rcx, [r14]; hKey
0x180047a41  lea     eax, ds:2[rdi*2]
0x180047a48  mov     [rsp+21B0h+cbData], eax; cbData
0x180047a4c  mov     r9d, 1; dwType
0x180047a52  lea     rax, [rbp+20B0h+String1]
0x180047a56  xor     r8d, r8d; Reserved
0x180047a59  mov     rdx, r15; lpValueName
0x180047a5c  mov     [rsp+21B0h+lpData], rax; lpData
0x180047a61  call    cs:__imp_RegSetValueExW
0x180047a67  mov     ebx, eax
0x180047a69  test    ebx, ebx
0x180047a6b  jz      short loc_180047A76
0x180047a6d  mov     ecx, ebx; unsigned int
0x180047a6f  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180047a74  jmp     short loc_180047A8A
0x180047a76  mov     rdx, r13; unsigned __int16 *
0x180047a79  mov     rcx, r12; this
0x180047a7c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180047a81  test    eax, eax
0x180047a83  mov     ecx, esi
0x180047a85  cmovs   ecx, eax
0x180047a88  mov     eax, ecx
0x180047a8a  mov     rcx, [rbp+20B0h+var_50]
0x180047a91  xor     rcx, rsp; StackCookie
0x180047a94  call    __security_check_cookie
0x180047a99  add     rsp, 2178h
0x180047aa0  pop     r15
0x180047aa2  pop     r14
0x180047aa4  pop     r13
0x180047aa6  pop     r12
0x180047aa8  pop     rdi
0x180047aa9  pop     rsi
0x180047aaa  pop     rbx
0x180047aab  pop     rbp
0x180047aac  retn
```
