# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800046ec`
- end: `0x180004cc0`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `HRESULT __fastcall(LPCWSTR *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800062ac`

## callees

- `0x1800046ec`
- `0x180004cc8`
- `0x180004e1c`
- `0x180005688`
- `0x180005860`
- `0x180005944`
- `0x18001f652`
- `0x18001f690`
- `0x18001f750`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180004975`
- `ADVAPI32!RegSetValueExW` at `0x180004a0d`
- `ADVAPI32!RegSetValueExW` at `0x180004c0e`
- `ADVAPI32!RegSetValueExW` at `0x180004975`
- `ADVAPI32!RegSetValueExW` at `0x180004a0d`
- `ADVAPI32!RegSetValueExW` at `0x180004c0e`
- `KERNEL32!lstrcmpiW` at `0x18000477d`
- `KERNEL32!lstrcmpiW` at `0x18000477d`
- `USER32!CharNextW` at `0x1800048ec`
- `USER32!CharNextW` at `0x180004908`
- `USER32!CharNextW` at `0x180004c90`
- `USER32!CharNextW` at `0x1800048ec`
- `USER32!CharNextW` at `0x180004908`
- `USER32!CharNextW` at `0x180004c90`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800049d5`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800049d5`

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
  OLECHAR String1[4096]; // [rsp+2B0h] [rbp-2048h] BYREF

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
0x1800046ec  push    rbx
0x1800046ee  push    rsi
0x1800046ef  push    rdi
0x1800046f0  push    r12
0x1800046f2  push    r13
0x1800046f4  push    r14
0x1800046f6  push    r15
0x1800046f8  mov     eax, 22C0h
0x1800046fd  call    _alloca_probe
0x180004702  sub     rsp, rax
0x180004705  mov     rax, cs:__security_cookie
0x18000470c  xor     rax, rsp
0x18000470f  mov     [rsp+22F8h+var_48], rax
0x180004717  mov     r14, r8
0x18000471a  mov     [rsp+22F8h+lpValueName], r8
0x18000471f  mov     r12, rdx
0x180004722  mov     [rsp+22F8h+var_2288], rdx
0x180004727  mov     r15, rcx
0x18000472a  mov     [rsp+22F8h+var_22C0], rcx
0x18000472f  mov     qword ptr [rsp+22F8h+Data], rdx
0x180004734  mov     [rsp+22F8h+var_22A8], rcx
0x180004739  mov     [rsp+22F8h+var_2278], rdx
0x180004741  mov     [rsp+22F8h+var_2298], r8
0x180004746  mov     [rsp+22F8h+var_2270], r9
0x18000474e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180004756  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000475b  xor     ebx, ebx
0x18000475d  test    eax, eax
0x18000475f  js      short loc_180004793
0x180004761  mov     edi, ebx
0x180004763  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000476a  movsxd  rsi, edi
0x18000476d  add     rsi, rsi
0x180004770  mov     rdx, [r13+rsi*8+0]; lpString2
0x180004775  lea     rcx, [rsp+22F8h+String1]; lpString1
0x18000477d  call    cs:__imp_lstrcmpiW
0x180004783  test    eax, eax
0x180004785  jz      short loc_1800047B6
0x180004787  inc     edi
0x180004789  cmp     edi, 4
0x18000478c  jb      short loc_18000476A
0x18000478e  mov     eax, 80020009h
0x180004793  mov     rcx, [rsp+22F8h+var_48]
0x18000479b  xor     rcx, rsp; StackCookie
0x18000479e  call    __security_check_cookie
0x1800047a3  add     rsp, 22C0h
0x1800047aa  pop     r15
0x1800047ac  pop     r14
0x1800047ae  pop     r13
0x1800047b0  pop     r12
0x1800047b2  pop     rdi
0x1800047b3  pop     rsi
0x1800047b4  pop     rbx
0x1800047b5  retn
0x1800047b6  movzx   edi, word ptr [r13+rsi*8+8]
0x1800047bc  mov     esi, 13h
0x1800047c1  mov     rdx, [r15]
0x1800047c4  movzx   ecx, word ptr [rdx]
0x1800047c7  sub     ecx, 9
0x1800047ca  jz      loc_180004C8D
0x1800047d0  sub     ecx, 1
0x1800047d3  jz      loc_180004C8D
0x1800047d9  sub     ecx, 3
0x1800047dc  jz      loc_180004C8D
0x1800047e2  cmp     ecx, esi
0x1800047e4  jz      loc_180004C8D
0x1800047ea  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1800047f2  mov     rcx, r15; this
0x1800047f5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800047fa  test    eax, eax
0x1800047fc  js      short loc_180004793
0x1800047fe  mov     r13d, 8
0x180004804  cmp     di, r13w
0x180004808  jz      loc_180004C3E
0x18000480e  cmp     di, 11h
0x180004812  jz      loc_180004A17
0x180004818  cmp     di, si
0x18000481b  jz      loc_1800049BF
0x180004821  mov     eax, 4008h
0x180004826  cmp     di, ax
0x180004829  jnz     loc_180004C71
0x18000482f  lea     rcx, [rsp+22F8h+String1]
0x180004837  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000483b  mov     rax, rsi
0x18000483e  inc     rax
0x180004841  cmp     [rcx+rax*2], bx
0x180004845  jnz     short loc_18000483E
0x180004847  add     eax, 2
0x18000484a  mov     [rsp+22F8h+var_2158], rbx
0x180004852  test    eax, eax
0x180004854  jz      short loc_18000488F
0x180004856  movsxd  rcx, eax
0x180004859  xor     edx, edx
0x18000485b  mov     rax, rsi
0x18000485e  div     rcx
0x180004861  cmp     rax, 2
0x180004865  jb      loc_180004C9E
0x18000486b  lea     rdx, [rcx+rcx]
0x18000486f  cmp     rdx, 100h
0x180004876  jbe     short loc_18000488F
0x180004878  lea     rcx, [rsp+22F8h+var_2158]
0x180004880  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180004885  mov     rdi, [rsp+22F8h+var_2158]
0x18000488d  jmp     short loc_18000489F
0x18000488f  lea     rdi, [rsp+22F8h+var_2150]
0x180004897  mov     [rsp+22F8h+var_2158], rdi
0x18000489f  mov     r13, [rsp+22F8h+lpValueName]
0x1800048a4  jmp     short loc_1800048C8
0x1800048a6  xor     ebx, ebx
0x1800048a8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800048ac  mov     rdi, [rsp+22F8h+var_2158]
0x1800048b4  mov     r12, qword ptr [rsp+22F8h+Data]
0x1800048b9  mov     rax, [rsp+22F8h+var_22A8]
0x1800048be  mov     [rsp+22F8h+var_22C0], rax
0x1800048c3  mov     r13, [rsp+22F8h+var_2298]
0x1800048c8  test    rdi, rdi
0x1800048cb  jz      loc_180004987
0x1800048d1  lea     r14, [rsp+22F8h+String1]
0x1800048d9  cmp     [rsp+22F8h+String1], bx
0x1800048e1  jz      short loc_180004924
0x1800048e3  mov     r15d, 30h ; '0'
0x1800048e9  mov     rcx, r14; lpsz
0x1800048ec  call    cs:__imp_CharNextW
0x1800048f2  movzx   ecx, word ptr [r14]
0x1800048f6  cmp     cx, 5Ch ; '\'
0x1800048fa  jnz     short loc_180004913
0x1800048fc  cmp     [rax], r15w
0x180004900  jnz     short loc_180004913
0x180004902  mov     [rdi], bx
0x180004905  mov     rcx, rax; lpsz
0x180004908  call    cs:__imp_CharNextW
0x18000490e  mov     r14, rax
0x180004911  jmp     short loc_18000491A
0x180004913  mov     [rdi], cx
0x180004916  add     r14, 2
0x18000491a  add     rdi, 2
0x18000491e  cmp     [r14], bx
0x180004922  jnz     short loc_1800048E9
0x180004924  mov     dword ptr [rdi], 0
0x18000492a  mov     r8, [rsp+22F8h+var_2158]
0x180004932  test    r8, r8
0x180004935  jz      loc_180004CA9
0x18000493b  mov     r10d, ebx
0x18000493e  mov     r9, r8
0x180004941  mov     rcx, rsi
0x180004944  inc     rcx
0x180004947  cmp     [r9+rcx*2], bx
0x18000494c  jnz     short loc_180004944
0x18000494e  inc     ecx
0x180004950  lea     r9, [r9+rcx*2]
0x180004954  lea     r10d, [r10+rcx*2]
0x180004958  cmp     ecx, 1
0x18000495b  jnz     short loc_180004941
0x18000495d  mov     [rsp+22F8h+cbData], r10d; cbData
0x180004962  mov     [rsp+22F8h+lpData], r8; lpData
0x180004967  lea     r9d, [rcx+6]; dwType
0x18000496b  xor     r8d, r8d; Reserved
0x18000496e  mov     rdx, r13; lpValueName
0x180004971  mov     rcx, [r12]; hKey
0x180004975  call    cs:__imp_RegSetValueExW
0x18000497b  mov     esi, eax
0x18000497d  mov     rdi, [rsp+22F8h+var_2158]
0x180004985  jmp     short loc_18000498C
0x180004987  mov     esi, 0Eh
0x18000498c  lea     rax, [rsp+22F8h+var_2150]
0x180004994  cmp     rdi, rax
0x180004997  jz      short loc_1800049A6
0x180004999  lea     rcx, [rsp+22F8h+var_2158]
0x1800049a1  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800049a6  mov     r15, [rsp+22F8h+var_22C0]
0x1800049ab  test    esi, esi
0x1800049ad  jz      loc_180004C71
0x1800049b3  mov     ecx, esi; unsigned int
0x1800049b5  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800049ba  jmp     loc_180004793
0x1800049bf  mov     [rsp+22F8h+pulOut], ebx
0x1800049c3  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x1800049c8  xor     r8d, r8d; dwFlags
0x1800049cb  xor     edx, edx; lcid
0x1800049cd  lea     rcx, [rsp+22F8h+String1]; strIn
0x1800049d5  call    cs:__imp_VarUI4FromStr
0x1800049db  test    eax, eax
0x1800049dd  js      loc_180004793
0x1800049e3  mov     eax, [rsp+22F8h+pulOut]
0x1800049e7  mov     dword ptr [rsp+22F8h+Data], eax
0x1800049eb  mov     [rsp+22F8h+cbData], 4; cbData
0x1800049f3  lea     rax, [rsp+22F8h+Data]
0x1800049f8  mov     r9d, 4; dwType
0x1800049fe  mov     [rsp+22F8h+lpData], rax; lpData
0x180004a03  xor     r8d, r8d; Reserved
0x180004a06  mov     rdx, r14; lpValueName
0x180004a09  mov     rcx, [r12]; hKey
0x180004a0d  call    cs:__imp_RegSetValueExW
0x180004a13  mov     esi, eax
0x180004a15  jmp     short loc_1800049AB
0x180004a17  lea     rax, [rsp+22F8h+String1]
0x180004a1f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180004a23  mov     r14, rsi
0x180004a26  inc     r14
0x180004a29  cmp     [rax+r14*2], bx
0x180004a2e  jnz     short loc_180004A26
0x180004a30  mov     dword ptr [rsp+22F8h+Data], r14d
0x180004a35  test    r14b, 1
0x180004a39  jnz     loc_180004AF3
0x180004a3f  mov     eax, r14d
0x180004a42  cdq
0x180004a43  sub     eax, edx
0x180004a45  sar     eax, 1
0x180004a47  movsxd  r12, eax
0x180004a4a  mov     [rsp+22F8h+var_2268], rbx
0x180004a52  mov     rdi, r12
0x180004a55  mov     [rsp+22F8h+var_2280], r12
0x180004a5a  test    eax, eax
0x180004a5c  jz      short loc_180004A93
0x180004a5e  xor     edx, edx
0x180004a60  mov     rax, rsi
0x180004a63  div     rdi
0x180004a66  cmp     rax, 1
0x180004a6a  jb      loc_180004CB4
0x180004a70  cmp     rdi, 100h
0x180004a77  jbe     short loc_180004A93
0x180004a79  mov     rdx, rdi
0x180004a7c  lea     rcx, [rsp+22F8h+var_2268]
0x180004a84  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180004a89  mov     rcx, [rsp+22F8h+var_2268]
0x180004a91  jmp     short loc_180004AA3
0x180004a93  lea     rcx, [rsp+22F8h+var_2260]
0x180004a9b  mov     [rsp+22F8h+var_2268], rcx
0x180004aa3  mov     rsi, [rsp+22F8h+var_2288]
0x180004aa8  jmp     short loc_180004AE1
0x180004aaa  xor     ebx, ebx
0x180004aac  lea     r13d, [rbx+8]
0x180004ab0  mov     r14d, dword ptr [rsp+22F8h+Data]
0x180004ab5  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180004abd  mov     rdi, [rsp+22F8h+var_2280]
0x180004ac2  mov     rax, [rsp+22F8h+var_22A8]
0x180004ac7  mov     [rsp+22F8h+var_22C0], rax
0x180004acc  mov     rsi, [rsp+22F8h+var_2278]
0x180004ad4  mov     rax, [rsp+22F8h+var_2298]
0x180004ad9  mov     [rsp+22F8h+lpValueName], rax
0x180004ade  mov     r12d, edi
0x180004ae1  test    rcx, rcx
0x180004ae4  jnz     short loc_180004AFD
0x180004ae6  lea     rcx, [rsp+22F8h+var_2268]
0x180004aee  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004af3  mov     eax, 80004005h
0x180004af8  jmp     loc_180004793
0x180004afd  mov     r8, rdi; Size
0x180004b00  xor     edx, edx; Val
0x180004b02  call    memset_0
0x180004b07  mov     r10d, ebx
0x180004b0a  test    r14d, r14d
0x180004b0d  jle     loc_180004BEB
0x180004b13  mov     r15d, 30h ; '0'
0x180004b19  mov     eax, r10d
0x180004b1c  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180004b24  cmp     edx, 61h ; 'a'
0x180004b27  ja      short loc_180004B96
0x180004b29  jz      loc_180004BB6
0x180004b2f  cmp     edx, 38h ; '8'
0x180004b32  ja      short loc_180004B68
0x180004b34  jz      short loc_180004B60
0x180004b36  mov     ecx, edx
0x180004b38  sub     ecx, r15d
0x180004b3b  jz      short loc_180004B60
0x180004b3d  sub     ecx, 1
0x180004b40  jz      short loc_180004B60
0x180004b42  sub     ecx, 1
0x180004b45  jz      short loc_180004B60
0x180004b47  sub     ecx, 1
0x180004b4a  jz      short loc_180004B60
0x180004b4c  sub     ecx, 1
0x180004b4f  jz      short loc_180004B60
0x180004b51  sub     ecx, 1
0x180004b54  jz      short loc_180004B60
0x180004b56  sub     ecx, 1
0x180004b59  jz      short loc_180004B60
0x180004b5b  cmp     ecx, 1
0x180004b5e  jnz     short loc_180004BB1
0x180004b60  mov     r9d, edx
0x180004b63  sub     r9d, r15d
0x180004b66  jmp     short loc_180004BBA
0x180004b68  mov     r9d, edx
0x180004b6b  mov     ecx, edx
0x180004b6d  sub     ecx, 39h ; '9'
0x180004b70  jz      short loc_180004B60
0x180004b72  sub     ecx, r13d
0x180004b75  jz      short loc_180004B90
0x180004b77  sub     ecx, 1
0x180004b7a  jz      short loc_180004B90
0x180004b7c  sub     ecx, 1
0x180004b7f  jz      short loc_180004B90
0x180004b81  sub     ecx, 1
0x180004b84  jz      short loc_180004B90
0x180004b86  sub     ecx, 1
0x180004b89  jz      short loc_180004B90
0x180004b8b  cmp     ecx, 1
0x180004b8e  jnz     short loc_180004BB1
0x180004b90  add     r9d, 0FFFFFFC9h
0x180004b94  jmp     short loc_180004BBA
  ... truncated ...
```
