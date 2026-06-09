# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000366c`
- end: `0x180003c40`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000521c`

## callees

- `0x180001f90`
- `0x180002a40`
- `0x18000366c`
- `0x180003c48`
- `0x180003e98`
- `0x180003eb0`
- `0x180004494`
- `0x1800047e0`
- `0x180012350`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000386c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003888`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003c10`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000386c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003888`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003c10`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180003955`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180003955`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800038f5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000398d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003b8e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800038f5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000398d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003b8e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800036fd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800036fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall ATL::CRegParser::AddValue(LPCWSTR *this, HKEY *a2, const unsigned __int16 *a3, unsigned __int16 *a4)
{
  HKEY *v5; // r12
  LPCWSTR *v6; // r15
  HRESULT result; // eax
  int v8; // ebx
  int v9; // edi
  __int16 v10; // di
  __int64 v11; // rax
  int v12; // eax
  BYTE *v13; // rdi
  const WCHAR *v14; // r13
  WCHAR *i; // r14
  const WCHAR *v16; // rax
  DWORD v17; // r10d
  BYTE *v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rcx
  LSTATUS v21; // esi
  const BYTE *v22; // rax
  DWORD v23; // r9d
  __int64 v24; // r14
  DWORD v25; // r12d
  size_t v26; // rdi
  BYTE *v27; // rcx
  HKEY *v28; // rsi
  unsigned int v29; // r10d
  unsigned int v30; // edx
  char v31; // r9
  __int64 v32; // rsi
  int Token; // eax
  DWORD cbData; // [rsp+28h] [rbp-22D0h]
  ULONG pulOut; // [rsp+30h] [rbp-22C8h] BYREF
  ATL::CRegParser *v36; // [rsp+38h] [rbp-22C0h]
  BYTE Data[8]; // [rsp+40h] [rbp-22B8h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-22B0h]
  ATL::CRegParser *v39; // [rsp+50h] [rbp-22A8h]
  const WCHAR *v40; // [rsp+60h] [rbp-2298h]
  struct ATL::CRegKey *v41; // [rsp+70h] [rbp-2288h]
  size_t v42; // [rsp+78h] [rbp-2280h]
  struct ATL::CRegKey *v43; // [rsp+80h] [rbp-2278h]
  unsigned __int16 *v44; // [rsp+88h] [rbp-2270h]
  BYTE *v45; // [rsp+90h] [rbp-2268h] BYREF
  _BYTE v46[264]; // [rsp+98h] [rbp-2260h] BYREF
  BYTE *lpData; // [rsp+1A0h] [rbp-2158h] BYREF
  _BYTE v48[264]; // [rsp+1A8h] [rbp-2150h] BYREF
  WCHAR String1[4096]; // [rsp+2B0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v5 = a2;
  v41 = (struct ATL::CRegKey *)a2;
  v6 = this;
  v36 = (ATL::CRegParser *)this;
  *(_QWORD *)Data = a2;
  v39 = (ATL::CRegParser *)this;
  v43 = (struct ATL::CRegKey *)a2;
  v40 = a3;
  v44 = a4;
  result = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
  v8 = 0;
  if ( result >= 0 )
  {
    v9 = 0;
    while ( lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
    {
      if ( (unsigned int)++v9 >= 4 )
        return -2147352567;
    }
    v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
    while ( **v6 == 9 || **v6 == 10 || **v6 == 13 || **v6 == 32 )
      *v6 = CharNextW(*v6);
    result = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, String1);
    if ( result >= 0 )
    {
      if ( v10 == 8 )
      {
        v32 = -1;
        do
          ++v32;
        while ( String1[v32] );
        cbData = 2 * v32 + 2;
        v22 = (const BYTE *)String1;
        v23 = 1;
        goto LABEL_47;
      }
      if ( v10 != 17 )
      {
        if ( v10 != 19 )
        {
          if ( v10 != 16392 )
          {
LABEL_93:
            Token = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, v44);
            if ( Token < 0 )
              return Token;
            return v8;
          }
          v11 = -1;
          do
            ++v11;
          while ( String1[v11] );
          v12 = v11 + 2;
          lpData = 0;
          try
          {
            if ( !v12 )
              goto LABEL_24;
            if ( 0xFFFFFFFFFFFFFFFFuLL / v12 < 2 )
              ATL::AtlThrowImpl(-2147024809);
            if ( (unsigned __int64)(2LL * v12) > 0x100 )
            {
              ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, 2LL * v12);
              v13 = lpData;
            }
            else
            {
LABEL_24:
              v13 = v48;
              lpData = v48;
            }
          }
          catch ( ... )
          {
            v8 = 0;
            v13 = lpData;
            v5 = *(HKEY **)Data;
            v36 = v39;
            v14 = v40;
            goto LABEL_26;
          }
          v14 = lpValueName;
LABEL_26:
          if ( v13 )
          {
            for ( i = String1; *i; v13 += 2 )
            {
              v16 = CharNextW(i);
              if ( *i == 92 && *v16 == 48 )
              {
                *(_WORD *)v13 = 0;
                i = CharNextW(v16);
              }
              else
              {
                *(_WORD *)v13 = *i++;
              }
            }
            *(_DWORD *)v13 = 0;
            if ( !lpData )
              ATL::AtlThrowImpl(-2147467259);
            v17 = 0;
            v18 = lpData;
            do
            {
              v19 = -1;
              do
                ++v19;
              while ( *(_WORD *)&v18[2 * v19] );
              v20 = (unsigned int)(v19 + 1);
              v18 += 2 * v20;
              v17 += 2 * v20;
            }
            while ( (_DWORD)v20 != 1 );
            v21 = RegSetValueExW(*v5, v14, 0, 7u, lpData, v17);
            v13 = lpData;
          }
          else
          {
            v21 = 14;
          }
          if ( v13 != v48 )
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&lpData);
          goto LABEL_42;
        }
        pulOut = 0;
        result = VarUI4FromStr(String1, 0, 0, &pulOut);
        if ( result < 0 )
          return result;
        *(_DWORD *)Data = pulOut;
        cbData = 4;
        v22 = Data;
        v23 = 4;
LABEL_47:
        v21 = RegSetValueExW(*v5, a3, 0, v23, v22, cbData);
LABEL_43:
        if ( v21 )
          return ATL::AtlHresultFromWin32(v21);
        goto LABEL_93;
      }
      v24 = -1;
      do
        ++v24;
      while ( String1[v24] );
      *(_DWORD *)Data = v24;
      if ( (v24 & 1) != 0 )
        return -2147467259;
      try
      {
        v25 = (int)v24 / 2;
        v45 = 0;
        v26 = (int)v24 / 2;
        v42 = v26;
        if ( !((int)v24 / 2) )
          goto LABEL_56;
        if ( !(0xFFFFFFFFFFFFFFFFuLL / v26) )
          ATL::AtlThrowImpl(-2147024809);
        if ( v26 > 0x100 )
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v45, v26);
          v27 = v45;
        }
        else
        {
LABEL_56:
          v27 = v46;
          v45 = v46;
        }
        v28 = (HKEY *)v41;
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v24) = *(_DWORD *)Data;
        v27 = v45;
        v26 = v42;
        v36 = v39;
        v28 = (HKEY *)v43;
        lpValueName = v40;
        v25 = v42;
      }
      if ( !v27 )
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v45);
        return -2147467259;
      }
      memset_0(v27, 0, v26);
      v29 = 0;
      if ( (int)v24 <= 0 )
      {
LABEL_88:
        v21 = RegSetValueExW(*v28, lpValueName, 0, 3u, v45, v25);
        if ( v45 != v46 )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v45);
LABEL_42:
        v6 = (LPCWSTR *)v36;
        goto LABEL_43;
      }
      while ( 1 )
      {
        v30 = String1[v29];
        if ( v30 > 0x61 )
        {
          if ( v30 == 98 || v30 == 99 || v30 == 100 || v30 - 101 < 2 )
          {
LABEL_86:
            v31 = v30 - 87;
            goto LABEL_87;
          }
LABEL_85:
          v31 = 0;
          goto LABEL_87;
        }
        if ( v30 == 97 )
          goto LABEL_86;
        if ( v30 <= 0x38 )
          break;
        if ( v30 == 57 )
          goto LABEL_73;
        if ( v30 != 65 && v30 != 66 && v30 != 67 && v30 != 68 && v30 - 69 > 1 )
          goto LABEL_85;
        v31 = v30 - 55;
LABEL_87:
        v45[(unsigned __int64)v29 >> 1] |= v31 << (4 - 4 * (v29 & 1));
        if ( (int)++v29 >= (int)v24 )
          goto LABEL_88;
      }
      if ( v30 != 56 && v30 != 48 && v30 != 49 && v30 != 50 && v30 != 51 && v30 != 52 && v30 != 53 && v30 - 54 > 1 )
        goto LABEL_85;
LABEL_73:
      v31 = v30 - 48;
      goto LABEL_87;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000366c  push    rbx
0x18000366e  push    rsi
0x18000366f  push    rdi
0x180003670  push    r12
0x180003672  push    r13
0x180003674  push    r14
0x180003676  push    r15
0x180003678  mov     eax, 22C0h
0x18000367d  call    _alloca_probe
0x180003682  sub     rsp, rax
0x180003685  mov     rax, cs:__security_cookie
0x18000368c  xor     rax, rsp
0x18000368f  mov     [rsp+22F8h+var_48], rax
0x180003697  mov     r14, r8
0x18000369a  mov     [rsp+22F8h+lpValueName], r8
0x18000369f  mov     r12, rdx
0x1800036a2  mov     [rsp+22F8h+var_2288], rdx
0x1800036a7  mov     r15, rcx
0x1800036aa  mov     [rsp+22F8h+var_22C0], rcx
0x1800036af  mov     qword ptr [rsp+22F8h+Data], rdx
0x1800036b4  mov     [rsp+22F8h+var_22A8], rcx
0x1800036b9  mov     [rsp+22F8h+var_2278], rdx
0x1800036c1  mov     [rsp+22F8h+var_2298], r8
0x1800036c6  mov     [rsp+22F8h+var_2270], r9
0x1800036ce  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1800036d6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800036db  xor     ebx, ebx
0x1800036dd  test    eax, eax
0x1800036df  js      short loc_180003713
0x1800036e1  mov     edi, ebx
0x1800036e3  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800036ea  movsxd  rsi, edi
0x1800036ed  add     rsi, rsi
0x1800036f0  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800036f5  lea     rcx, [rsp+22F8h+String1]; lpString1
0x1800036fd  call    cs:__imp_lstrcmpiW
0x180003703  test    eax, eax
0x180003705  jz      short loc_180003736
0x180003707  inc     edi
0x180003709  cmp     edi, 4
0x18000370c  jb      short loc_1800036EA
0x18000370e  mov     eax, 80020009h
0x180003713  mov     rcx, [rsp+22F8h+var_48]
0x18000371b  xor     rcx, rsp; StackCookie
0x18000371e  call    __security_check_cookie
0x180003723  add     rsp, 22C0h
0x18000372a  pop     r15
0x18000372c  pop     r14
0x18000372e  pop     r13
0x180003730  pop     r12
0x180003732  pop     rdi
0x180003733  pop     rsi
0x180003734  pop     rbx
0x180003735  retn
0x180003736  movzx   edi, word ptr [r13+rsi*8+8]
0x18000373c  mov     esi, 13h
0x180003741  mov     rdx, [r15]
0x180003744  movzx   ecx, word ptr [rdx]
0x180003747  sub     ecx, 9
0x18000374a  jz      loc_180003C0D
0x180003750  sub     ecx, 1
0x180003753  jz      loc_180003C0D
0x180003759  sub     ecx, 3
0x18000375c  jz      loc_180003C0D
0x180003762  cmp     ecx, esi
0x180003764  jz      loc_180003C0D
0x18000376a  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180003772  mov     rcx, r15; this
0x180003775  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000377a  test    eax, eax
0x18000377c  js      short loc_180003713
0x18000377e  mov     r13d, 8
0x180003784  cmp     di, r13w
0x180003788  jz      loc_180003BBE
0x18000378e  cmp     di, 11h
0x180003792  jz      loc_180003997
0x180003798  cmp     di, si
0x18000379b  jz      loc_18000393F
0x1800037a1  mov     eax, 4008h
0x1800037a6  cmp     di, ax
0x1800037a9  jnz     loc_180003BF1
0x1800037af  lea     rcx, [rsp+22F8h+String1]
0x1800037b7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800037bb  mov     rax, rsi
0x1800037be  inc     rax
0x1800037c1  cmp     [rcx+rax*2], bx
0x1800037c5  jnz     short loc_1800037BE
0x1800037c7  add     eax, 2
0x1800037ca  mov     [rsp+22F8h+var_2158], rbx
0x1800037d2  test    eax, eax
0x1800037d4  jz      short loc_18000380F
0x1800037d6  movsxd  rcx, eax
0x1800037d9  xor     edx, edx
0x1800037db  mov     rax, rsi
0x1800037de  div     rcx
0x1800037e1  cmp     rax, 2
0x1800037e5  jb      loc_180003C1E
0x1800037eb  lea     rdx, [rcx+rcx]
0x1800037ef  cmp     rdx, 100h
0x1800037f6  jbe     short loc_18000380F
0x1800037f8  lea     rcx, [rsp+22F8h+var_2158]
0x180003800  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180003805  mov     rdi, [rsp+22F8h+var_2158]
0x18000380d  jmp     short loc_18000381F
0x18000380f  lea     rdi, [rsp+22F8h+var_2150]
0x180003817  mov     [rsp+22F8h+var_2158], rdi
0x18000381f  mov     r13, [rsp+22F8h+lpValueName]
0x180003824  jmp     short loc_180003848
0x180003826  xor     ebx, ebx
0x180003828  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000382c  mov     rdi, [rsp+22F8h+var_2158]
0x180003834  mov     r12, qword ptr [rsp+22F8h+Data]
0x180003839  mov     rax, [rsp+22F8h+var_22A8]
0x18000383e  mov     [rsp+22F8h+var_22C0], rax
0x180003843  mov     r13, [rsp+22F8h+var_2298]
0x180003848  test    rdi, rdi
0x18000384b  jz      loc_180003907
0x180003851  lea     r14, [rsp+22F8h+String1]
0x180003859  cmp     [rsp+22F8h+String1], bx
0x180003861  jz      short loc_1800038A4
0x180003863  mov     r15d, 30h ; '0'
0x180003869  mov     rcx, r14; lpsz
0x18000386c  call    cs:__imp_CharNextW
0x180003872  movzx   ecx, word ptr [r14]
0x180003876  cmp     cx, 5Ch ; '\'
0x18000387a  jnz     short loc_180003893
0x18000387c  cmp     [rax], r15w
0x180003880  jnz     short loc_180003893
0x180003882  mov     [rdi], bx
0x180003885  mov     rcx, rax; lpsz
0x180003888  call    cs:__imp_CharNextW
0x18000388e  mov     r14, rax
0x180003891  jmp     short loc_18000389A
0x180003893  mov     [rdi], cx
0x180003896  add     r14, 2
0x18000389a  add     rdi, 2
0x18000389e  cmp     [r14], bx
0x1800038a2  jnz     short loc_180003869
0x1800038a4  mov     dword ptr [rdi], 0
0x1800038aa  mov     r8, [rsp+22F8h+var_2158]
0x1800038b2  test    r8, r8
0x1800038b5  jz      loc_180003C29
0x1800038bb  mov     r10d, ebx
0x1800038be  mov     r9, r8
0x1800038c1  mov     rcx, rsi
0x1800038c4  inc     rcx
0x1800038c7  cmp     [r9+rcx*2], bx
0x1800038cc  jnz     short loc_1800038C4
0x1800038ce  inc     ecx
0x1800038d0  lea     r9, [r9+rcx*2]
0x1800038d4  lea     r10d, [r10+rcx*2]
0x1800038d8  cmp     ecx, 1
0x1800038db  jnz     short loc_1800038C1
0x1800038dd  mov     [rsp+22F8h+cbData], r10d; cbData
0x1800038e2  mov     [rsp+22F8h+lpData], r8; lpData
0x1800038e7  lea     r9d, [rcx+6]; dwType
0x1800038eb  xor     r8d, r8d; Reserved
0x1800038ee  mov     rdx, r13; lpValueName
0x1800038f1  mov     rcx, [r12]; hKey
0x1800038f5  call    cs:__imp_RegSetValueExW
0x1800038fb  mov     esi, eax
0x1800038fd  mov     rdi, [rsp+22F8h+var_2158]
0x180003905  jmp     short loc_18000390C
0x180003907  mov     esi, 0Eh
0x18000390c  lea     rax, [rsp+22F8h+var_2150]
0x180003914  cmp     rdi, rax
0x180003917  jz      short loc_180003926
0x180003919  lea     rcx, [rsp+22F8h+var_2158]
0x180003921  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180003926  mov     r15, [rsp+22F8h+var_22C0]
0x18000392b  test    esi, esi
0x18000392d  jz      loc_180003BF1
0x180003933  mov     ecx, esi; unsigned int
0x180003935  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000393a  jmp     loc_180003713
0x18000393f  mov     [rsp+22F8h+pulOut], ebx
0x180003943  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x180003948  xor     r8d, r8d; dwFlags
0x18000394b  xor     edx, edx; lcid
0x18000394d  lea     rcx, [rsp+22F8h+String1]; strIn
0x180003955  call    cs:__imp_VarUI4FromStr
0x18000395b  test    eax, eax
0x18000395d  js      loc_180003713
0x180003963  mov     eax, [rsp+22F8h+pulOut]
0x180003967  mov     dword ptr [rsp+22F8h+Data], eax
0x18000396b  mov     [rsp+22F8h+cbData], 4; cbData
0x180003973  lea     rax, [rsp+22F8h+Data]
0x180003978  mov     r9d, 4; dwType
0x18000397e  mov     [rsp+22F8h+lpData], rax; lpData
0x180003983  xor     r8d, r8d; Reserved
0x180003986  mov     rdx, r14; lpValueName
0x180003989  mov     rcx, [r12]; hKey
0x18000398d  call    cs:__imp_RegSetValueExW
0x180003993  mov     esi, eax
0x180003995  jmp     short loc_18000392B
0x180003997  lea     rax, [rsp+22F8h+String1]
0x18000399f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800039a3  mov     r14, rsi
0x1800039a6  inc     r14
0x1800039a9  cmp     [rax+r14*2], bx
0x1800039ae  jnz     short loc_1800039A6
0x1800039b0  mov     dword ptr [rsp+22F8h+Data], r14d
0x1800039b5  test    r14b, 1
0x1800039b9  jnz     loc_180003A73
0x1800039bf  mov     eax, r14d
0x1800039c2  cdq
0x1800039c3  sub     eax, edx
0x1800039c5  sar     eax, 1
0x1800039c7  movsxd  r12, eax
0x1800039ca  mov     [rsp+22F8h+var_2268], rbx
0x1800039d2  mov     rdi, r12
0x1800039d5  mov     [rsp+22F8h+var_2280], r12
0x1800039da  test    eax, eax
0x1800039dc  jz      short loc_180003A13
0x1800039de  xor     edx, edx
0x1800039e0  mov     rax, rsi
0x1800039e3  div     rdi
0x1800039e6  cmp     rax, 1
0x1800039ea  jb      loc_180003C34
0x1800039f0  cmp     rdi, 100h
0x1800039f7  jbe     short loc_180003A13
0x1800039f9  mov     rdx, rdi
0x1800039fc  lea     rcx, [rsp+22F8h+var_2268]
0x180003a04  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180003a09  mov     rcx, [rsp+22F8h+var_2268]
0x180003a11  jmp     short loc_180003A23
0x180003a13  lea     rcx, [rsp+22F8h+var_2260]
0x180003a1b  mov     [rsp+22F8h+var_2268], rcx
0x180003a23  mov     rsi, [rsp+22F8h+var_2288]
0x180003a28  jmp     short loc_180003A61
0x180003a2a  xor     ebx, ebx
0x180003a2c  lea     r13d, [rbx+8]
0x180003a30  mov     r14d, dword ptr [rsp+22F8h+Data]
0x180003a35  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180003a3d  mov     rdi, [rsp+22F8h+var_2280]
0x180003a42  mov     rax, [rsp+22F8h+var_22A8]
0x180003a47  mov     [rsp+22F8h+var_22C0], rax
0x180003a4c  mov     rsi, [rsp+22F8h+var_2278]
0x180003a54  mov     rax, [rsp+22F8h+var_2298]
0x180003a59  mov     [rsp+22F8h+lpValueName], rax
0x180003a5e  mov     r12d, edi
0x180003a61  test    rcx, rcx
0x180003a64  jnz     short loc_180003A7D
0x180003a66  lea     rcx, [rsp+22F8h+var_2268]
0x180003a6e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180003a73  mov     eax, 80004005h
0x180003a78  jmp     loc_180003713
0x180003a7d  mov     r8, rdi; Size
0x180003a80  xor     edx, edx; Val
0x180003a82  call    memset_0
0x180003a87  mov     r10d, ebx
0x180003a8a  test    r14d, r14d
0x180003a8d  jle     loc_180003B6B
0x180003a93  mov     r15d, 30h ; '0'
0x180003a99  mov     eax, r10d
0x180003a9c  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180003aa4  cmp     edx, 61h ; 'a'
0x180003aa7  ja      short loc_180003B16
0x180003aa9  jz      loc_180003B36
0x180003aaf  cmp     edx, 38h ; '8'
0x180003ab2  ja      short loc_180003AE8
0x180003ab4  jz      short loc_180003AE0
0x180003ab6  mov     ecx, edx
0x180003ab8  sub     ecx, r15d
0x180003abb  jz      short loc_180003AE0
0x180003abd  sub     ecx, 1
0x180003ac0  jz      short loc_180003AE0
0x180003ac2  sub     ecx, 1
0x180003ac5  jz      short loc_180003AE0
0x180003ac7  sub     ecx, 1
0x180003aca  jz      short loc_180003AE0
0x180003acc  sub     ecx, 1
0x180003acf  jz      short loc_180003AE0
0x180003ad1  sub     ecx, 1
0x180003ad4  jz      short loc_180003AE0
0x180003ad6  sub     ecx, 1
0x180003ad9  jz      short loc_180003AE0
0x180003adb  cmp     ecx, 1
0x180003ade  jnz     short loc_180003B31
0x180003ae0  mov     r9d, edx
0x180003ae3  sub     r9d, r15d
0x180003ae6  jmp     short loc_180003B3A
0x180003ae8  mov     r9d, edx
0x180003aeb  mov     ecx, edx
0x180003aed  sub     ecx, 39h ; '9'
0x180003af0  jz      short loc_180003AE0
0x180003af2  sub     ecx, r13d
0x180003af5  jz      short loc_180003B10
0x180003af7  sub     ecx, 1
0x180003afa  jz      short loc_180003B10
0x180003afc  sub     ecx, 1
0x180003aff  jz      short loc_180003B10
0x180003b01  sub     ecx, 1
0x180003b04  jz      short loc_180003B10
0x180003b06  sub     ecx, 1
0x180003b09  jz      short loc_180003B10
0x180003b0b  cmp     ecx, 1
0x180003b0e  jnz     short loc_180003B31
0x180003b10  add     r9d, 0FFFFFFC9h
0x180003b14  jmp     short loc_180003B3A
  ... truncated ...
```
