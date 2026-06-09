# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800037ac`
- end: `0x180003d80`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `HRESULT __fastcall(LPCWSTR *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000566c`

## callees

- `0x18000278c`
- `0x1800037ac`
- `0x180003d88`
- `0x180003eb8`
- `0x1800049e8`
- `0x180004ba0`
- `0x18000ab2e`
- `0x18000ab60`
- `0x18000ac20`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180003a35`
- `ADVAPI32!RegSetValueExW` at `0x180003acd`
- `ADVAPI32!RegSetValueExW` at `0x180003cce`
- `ADVAPI32!RegSetValueExW` at `0x180003a35`
- `ADVAPI32!RegSetValueExW` at `0x180003acd`
- `ADVAPI32!RegSetValueExW` at `0x180003cce`
- `KERNEL32!lstrcmpiW` at `0x18000383d`
- `KERNEL32!lstrcmpiW` at `0x18000383d`
- `USER32!CharNextW` at `0x1800039ac`
- `USER32!CharNextW` at `0x1800039c8`
- `USER32!CharNextW` at `0x180003d50`
- `USER32!CharNextW` at `0x1800039ac`
- `USER32!CharNextW` at `0x1800039c8`
- `USER32!CharNextW` at `0x180003d50`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180003a95`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180003a95`

## pseudocode

```c
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
              ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData);
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
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v45);
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
0x1800037ac  push    rbx
0x1800037ae  push    rsi
0x1800037af  push    rdi
0x1800037b0  push    r12
0x1800037b2  push    r13
0x1800037b4  push    r14
0x1800037b6  push    r15
0x1800037b8  mov     eax, 22C0h
0x1800037bd  call    _alloca_probe
0x1800037c2  sub     rsp, rax
0x1800037c5  mov     rax, cs:__security_cookie
0x1800037cc  xor     rax, rsp
0x1800037cf  mov     [rsp+22F8h+var_48], rax
0x1800037d7  mov     r14, r8
0x1800037da  mov     [rsp+22F8h+lpValueName], r8
0x1800037df  mov     r12, rdx
0x1800037e2  mov     [rsp+22F8h+var_2288], rdx
0x1800037e7  mov     r15, rcx
0x1800037ea  mov     [rsp+22F8h+var_22C0], rcx
0x1800037ef  mov     qword ptr [rsp+22F8h+Data], rdx
0x1800037f4  mov     [rsp+22F8h+var_22A8], rcx
0x1800037f9  mov     [rsp+22F8h+var_2278], rdx
0x180003801  mov     [rsp+22F8h+var_2298], r8
0x180003806  mov     [rsp+22F8h+var_2270], r9
0x18000380e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180003816  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000381b  xor     ebx, ebx
0x18000381d  test    eax, eax
0x18000381f  js      short loc_180003853
0x180003821  mov     edi, ebx
0x180003823  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000382a  movsxd  rsi, edi
0x18000382d  add     rsi, rsi
0x180003830  mov     rdx, [r13+rsi*8+0]; lpString2
0x180003835  lea     rcx, [rsp+22F8h+String1]; lpString1
0x18000383d  call    cs:__imp_lstrcmpiW
0x180003843  test    eax, eax
0x180003845  jz      short loc_180003876
0x180003847  inc     edi
0x180003849  cmp     edi, 4
0x18000384c  jb      short loc_18000382A
0x18000384e  mov     eax, 80020009h
0x180003853  mov     rcx, [rsp+22F8h+var_48]
0x18000385b  xor     rcx, rsp; StackCookie
0x18000385e  call    __security_check_cookie
0x180003863  add     rsp, 22C0h
0x18000386a  pop     r15
0x18000386c  pop     r14
0x18000386e  pop     r13
0x180003870  pop     r12
0x180003872  pop     rdi
0x180003873  pop     rsi
0x180003874  pop     rbx
0x180003875  retn
0x180003876  movzx   edi, word ptr [r13+rsi*8+8]
0x18000387c  mov     esi, 13h
0x180003881  mov     rdx, [r15]
0x180003884  movzx   ecx, word ptr [rdx]
0x180003887  sub     ecx, 9
0x18000388a  jz      loc_180003D4D
0x180003890  sub     ecx, 1
0x180003893  jz      loc_180003D4D
0x180003899  sub     ecx, 3
0x18000389c  jz      loc_180003D4D
0x1800038a2  cmp     ecx, esi
0x1800038a4  jz      loc_180003D4D
0x1800038aa  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1800038b2  mov     rcx, r15; this
0x1800038b5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800038ba  test    eax, eax
0x1800038bc  js      short loc_180003853
0x1800038be  mov     r13d, 8
0x1800038c4  cmp     di, r13w
0x1800038c8  jz      loc_180003CFE
0x1800038ce  cmp     di, 11h
0x1800038d2  jz      loc_180003AD7
0x1800038d8  cmp     di, si
0x1800038db  jz      loc_180003A7F
0x1800038e1  mov     eax, 4008h
0x1800038e6  cmp     di, ax
0x1800038e9  jnz     loc_180003D31
0x1800038ef  lea     rcx, [rsp+22F8h+String1]
0x1800038f7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800038fb  mov     rax, rsi
0x1800038fe  inc     rax
0x180003901  cmp     [rcx+rax*2], bx
0x180003905  jnz     short loc_1800038FE
0x180003907  add     eax, 2
0x18000390a  mov     [rsp+22F8h+var_2158], rbx
0x180003912  test    eax, eax
0x180003914  jz      short loc_18000394F
0x180003916  movsxd  rcx, eax
0x180003919  xor     edx, edx
0x18000391b  mov     rax, rsi
0x18000391e  div     rcx
0x180003921  cmp     rax, 2
0x180003925  jb      loc_180003D5E
0x18000392b  lea     rdx, [rcx+rcx]
0x18000392f  cmp     rdx, 100h
0x180003936  jbe     short loc_18000394F
0x180003938  lea     rcx, [rsp+22F8h+var_2158]
0x180003940  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180003945  mov     rdi, [rsp+22F8h+var_2158]
0x18000394d  jmp     short loc_18000395F
0x18000394f  lea     rdi, [rsp+22F8h+var_2150]
0x180003957  mov     [rsp+22F8h+var_2158], rdi
0x18000395f  mov     r13, [rsp+22F8h+lpValueName]
0x180003964  jmp     short loc_180003988
0x180003966  xor     ebx, ebx
0x180003968  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000396c  mov     rdi, [rsp+22F8h+var_2158]
0x180003974  mov     r12, qword ptr [rsp+22F8h+Data]
0x180003979  mov     rax, [rsp+22F8h+var_22A8]
0x18000397e  mov     [rsp+22F8h+var_22C0], rax
0x180003983  mov     r13, [rsp+22F8h+var_2298]
0x180003988  test    rdi, rdi
0x18000398b  jz      loc_180003A47
0x180003991  lea     r14, [rsp+22F8h+String1]
0x180003999  cmp     [rsp+22F8h+String1], bx
0x1800039a1  jz      short loc_1800039E4
0x1800039a3  mov     r15d, 30h ; '0'
0x1800039a9  mov     rcx, r14; lpsz
0x1800039ac  call    cs:__imp_CharNextW
0x1800039b2  movzx   ecx, word ptr [r14]
0x1800039b6  cmp     cx, 5Ch ; '\'
0x1800039ba  jnz     short loc_1800039D3
0x1800039bc  cmp     [rax], r15w
0x1800039c0  jnz     short loc_1800039D3
0x1800039c2  mov     [rdi], bx
0x1800039c5  mov     rcx, rax; lpsz
0x1800039c8  call    cs:__imp_CharNextW
0x1800039ce  mov     r14, rax
0x1800039d1  jmp     short loc_1800039DA
0x1800039d3  mov     [rdi], cx
0x1800039d6  add     r14, 2
0x1800039da  add     rdi, 2
0x1800039de  cmp     [r14], bx
0x1800039e2  jnz     short loc_1800039A9
0x1800039e4  mov     dword ptr [rdi], 0
0x1800039ea  mov     r8, [rsp+22F8h+var_2158]
0x1800039f2  test    r8, r8
0x1800039f5  jz      loc_180003D69
0x1800039fb  mov     r10d, ebx
0x1800039fe  mov     r9, r8
0x180003a01  mov     rcx, rsi
0x180003a04  inc     rcx
0x180003a07  cmp     [r9+rcx*2], bx
0x180003a0c  jnz     short loc_180003A04
0x180003a0e  inc     ecx
0x180003a10  lea     r9, [r9+rcx*2]
0x180003a14  lea     r10d, [r10+rcx*2]
0x180003a18  cmp     ecx, 1
0x180003a1b  jnz     short loc_180003A01
0x180003a1d  mov     [rsp+22F8h+cbData], r10d; cbData
0x180003a22  mov     [rsp+22F8h+lpData], r8; lpData
0x180003a27  lea     r9d, [rcx+6]; dwType
0x180003a2b  xor     r8d, r8d; Reserved
0x180003a2e  mov     rdx, r13; lpValueName
0x180003a31  mov     rcx, [r12]; hKey
0x180003a35  call    cs:__imp_RegSetValueExW
0x180003a3b  mov     esi, eax
0x180003a3d  mov     rdi, [rsp+22F8h+var_2158]
0x180003a45  jmp     short loc_180003A4C
0x180003a47  mov     esi, 0Eh
0x180003a4c  lea     rax, [rsp+22F8h+var_2150]
0x180003a54  cmp     rdi, rax
0x180003a57  jz      short loc_180003A66
0x180003a59  lea     rcx, [rsp+22F8h+var_2158]
0x180003a61  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180003a66  mov     r15, [rsp+22F8h+var_22C0]
0x180003a6b  test    esi, esi
0x180003a6d  jz      loc_180003D31
0x180003a73  mov     ecx, esi; unsigned int
0x180003a75  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180003a7a  jmp     loc_180003853
0x180003a7f  mov     [rsp+22F8h+pulOut], ebx
0x180003a83  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x180003a88  xor     r8d, r8d; dwFlags
0x180003a8b  xor     edx, edx; lcid
0x180003a8d  lea     rcx, [rsp+22F8h+String1]; strIn
0x180003a95  call    cs:__imp_VarUI4FromStr
0x180003a9b  test    eax, eax
0x180003a9d  js      loc_180003853
0x180003aa3  mov     eax, [rsp+22F8h+pulOut]
0x180003aa7  mov     dword ptr [rsp+22F8h+Data], eax
0x180003aab  mov     [rsp+22F8h+cbData], 4; cbData
0x180003ab3  lea     rax, [rsp+22F8h+Data]
0x180003ab8  mov     r9d, 4; dwType
0x180003abe  mov     [rsp+22F8h+lpData], rax; lpData
0x180003ac3  xor     r8d, r8d; Reserved
0x180003ac6  mov     rdx, r14; lpValueName
0x180003ac9  mov     rcx, [r12]; hKey
0x180003acd  call    cs:__imp_RegSetValueExW
0x180003ad3  mov     esi, eax
0x180003ad5  jmp     short loc_180003A6B
0x180003ad7  lea     rax, [rsp+22F8h+String1]
0x180003adf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003ae3  mov     r14, rsi
0x180003ae6  inc     r14
0x180003ae9  cmp     [rax+r14*2], bx
0x180003aee  jnz     short loc_180003AE6
0x180003af0  mov     dword ptr [rsp+22F8h+Data], r14d
0x180003af5  test    r14b, 1
0x180003af9  jnz     loc_180003BB3
0x180003aff  mov     eax, r14d
0x180003b02  cdq
0x180003b03  sub     eax, edx
0x180003b05  sar     eax, 1
0x180003b07  movsxd  r12, eax
0x180003b0a  mov     [rsp+22F8h+var_2268], rbx
0x180003b12  mov     rdi, r12
0x180003b15  mov     [rsp+22F8h+var_2280], r12
0x180003b1a  test    eax, eax
0x180003b1c  jz      short loc_180003B53
0x180003b1e  xor     edx, edx
0x180003b20  mov     rax, rsi
0x180003b23  div     rdi
0x180003b26  cmp     rax, 1
0x180003b2a  jb      loc_180003D74
0x180003b30  cmp     rdi, 100h
0x180003b37  jbe     short loc_180003B53
0x180003b39  mov     rdx, rdi
0x180003b3c  lea     rcx, [rsp+22F8h+var_2268]
0x180003b44  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180003b49  mov     rcx, [rsp+22F8h+var_2268]
0x180003b51  jmp     short loc_180003B63
0x180003b53  lea     rcx, [rsp+22F8h+var_2260]
0x180003b5b  mov     [rsp+22F8h+var_2268], rcx
0x180003b63  mov     rsi, [rsp+22F8h+var_2288]
0x180003b68  jmp     short loc_180003BA1
0x180003b6a  xor     ebx, ebx
0x180003b6c  lea     r13d, [rbx+8]
0x180003b70  mov     r14d, dword ptr [rsp+22F8h+Data]
0x180003b75  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180003b7d  mov     rdi, [rsp+22F8h+var_2280]
0x180003b82  mov     rax, [rsp+22F8h+var_22A8]
0x180003b87  mov     [rsp+22F8h+var_22C0], rax
0x180003b8c  mov     rsi, [rsp+22F8h+var_2278]
0x180003b94  mov     rax, [rsp+22F8h+var_2298]
0x180003b99  mov     [rsp+22F8h+lpValueName], rax
0x180003b9e  mov     r12d, edi
0x180003ba1  test    rcx, rcx
0x180003ba4  jnz     short loc_180003BBD
0x180003ba6  lea     rcx, [rsp+22F8h+var_2268]
0x180003bae  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180003bb3  mov     eax, 80004005h
0x180003bb8  jmp     loc_180003853
0x180003bbd  mov     r8, rdi; Size
0x180003bc0  xor     edx, edx; Val
0x180003bc2  call    memset_0
0x180003bc7  mov     r10d, ebx
0x180003bca  test    r14d, r14d
0x180003bcd  jle     loc_180003CAB
0x180003bd3  mov     r15d, 30h ; '0'
0x180003bd9  mov     eax, r10d
0x180003bdc  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180003be4  cmp     edx, 61h ; 'a'
0x180003be7  ja      short loc_180003C56
0x180003be9  jz      loc_180003C76
0x180003bef  cmp     edx, 38h ; '8'
0x180003bf2  ja      short loc_180003C28
0x180003bf4  jz      short loc_180003C20
0x180003bf6  mov     ecx, edx
0x180003bf8  sub     ecx, r15d
0x180003bfb  jz      short loc_180003C20
0x180003bfd  sub     ecx, 1
0x180003c00  jz      short loc_180003C20
0x180003c02  sub     ecx, 1
0x180003c05  jz      short loc_180003C20
0x180003c07  sub     ecx, 1
0x180003c0a  jz      short loc_180003C20
0x180003c0c  sub     ecx, 1
0x180003c0f  jz      short loc_180003C20
0x180003c11  sub     ecx, 1
0x180003c14  jz      short loc_180003C20
0x180003c16  sub     ecx, 1
0x180003c19  jz      short loc_180003C20
0x180003c1b  cmp     ecx, 1
0x180003c1e  jnz     short loc_180003C71
0x180003c20  mov     r9d, edx
0x180003c23  sub     r9d, r15d
0x180003c26  jmp     short loc_180003C7A
0x180003c28  mov     r9d, edx
0x180003c2b  mov     ecx, edx
0x180003c2d  sub     ecx, 39h ; '9'
0x180003c30  jz      short loc_180003C20
0x180003c32  sub     ecx, r13d
0x180003c35  jz      short loc_180003C50
0x180003c37  sub     ecx, 1
0x180003c3a  jz      short loc_180003C50
0x180003c3c  sub     ecx, 1
0x180003c3f  jz      short loc_180003C50
0x180003c41  sub     ecx, 1
0x180003c44  jz      short loc_180003C50
0x180003c46  sub     ecx, 1
0x180003c49  jz      short loc_180003C50
0x180003c4b  cmp     ecx, 1
0x180003c4e  jnz     short loc_180003C71
0x180003c50  add     r9d, 0FFFFFFC9h
0x180003c54  jmp     short loc_180003C7A
  ... truncated ...
```
