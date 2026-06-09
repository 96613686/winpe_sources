# ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)

- ea: `0x18000bd2c`
- end: `0x18000c300`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z`
- size: `1492`
- prototype: `HRESULT __fastcall(LPCWSTR *this, HKEY *, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000efac`

## callees

- `0x1800024a0`
- `0x180003320`
- `0x18000bd2c`
- `0x18000c308`
- `0x18000c41c`
- `0x18000c434`
- `0x18000c974`
- `0x18000e33c`
- `0x180015650`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000c015`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000c015`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000bf2c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000bf48`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000c2d0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000bf2c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000bf48`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000c2d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bfb5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c04d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c24e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bfb5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c04d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c24e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000bdbd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000bdbd`

## pseudocode

```c
HRESULT __fastcall ATL::CRegParser::AddValue(LPCWSTR *this, HKEY *a2, const wchar_t *a3, wchar_t *a4)
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
  wchar_t *v44; // [rsp+88h] [rbp-2270h]
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
              ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, 2LL * v12);
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
            ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap(&lpData);
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
          ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&v45, v26);
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
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap(&v45);
        return -2147467259;
      }
      memset_0(v27, 0, v26);
      v29 = 0;
      if ( (int)v24 <= 0 )
      {
LABEL_88:
        v21 = RegSetValueExW(*v28, lpValueName, 0, 3u, v45, v25);
        if ( v45 != v46 )
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap(&v45);
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
0x18000bd2c  push    rbx
0x18000bd2e  push    rsi
0x18000bd2f  push    rdi
0x18000bd30  push    r12
0x18000bd32  push    r13
0x18000bd34  push    r14
0x18000bd36  push    r15
0x18000bd38  mov     eax, 22C0h
0x18000bd3d  call    _alloca_probe
0x18000bd42  sub     rsp, rax
0x18000bd45  mov     rax, cs:__security_cookie
0x18000bd4c  xor     rax, rsp
0x18000bd4f  mov     [rsp+22F8h+var_48], rax
0x18000bd57  mov     r14, r8
0x18000bd5a  mov     [rsp+22F8h+lpValueName], r8
0x18000bd5f  mov     r12, rdx
0x18000bd62  mov     [rsp+22F8h+var_2288], rdx
0x18000bd67  mov     r15, rcx
0x18000bd6a  mov     [rsp+22F8h+var_22C0], rcx
0x18000bd6f  mov     qword ptr [rsp+22F8h+Data], rdx
0x18000bd74  mov     [rsp+22F8h+var_22A8], rcx
0x18000bd79  mov     [rsp+22F8h+var_2278], rdx
0x18000bd81  mov     [rsp+22F8h+var_2298], r8
0x18000bd86  mov     [rsp+22F8h+var_2270], r9
0x18000bd8e  lea     rdx, [rsp+22F8h+String1]; wchar_t *
0x18000bd96  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000bd9b  xor     ebx, ebx
0x18000bd9d  test    eax, eax
0x18000bd9f  js      short loc_18000BDD3
0x18000bda1  mov     edi, ebx
0x18000bda3  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEB_WAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::map
0x18000bdaa  movsxd  rsi, edi
0x18000bdad  add     rsi, rsi
0x18000bdb0  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000bdb5  lea     rcx, [rsp+22F8h+String1]; lpString1
0x18000bdbd  call    cs:__imp_lstrcmpiW
0x18000bdc3  test    eax, eax
0x18000bdc5  jz      short loc_18000BDF6
0x18000bdc7  inc     edi
0x18000bdc9  cmp     edi, 4
0x18000bdcc  jb      short loc_18000BDAA
0x18000bdce  mov     eax, 80020009h
0x18000bdd3  mov     rcx, [rsp+22F8h+var_48]
0x18000bddb  xor     rcx, rsp; StackCookie
0x18000bdde  call    __security_check_cookie
0x18000bde3  add     rsp, 22C0h
0x18000bdea  pop     r15
0x18000bdec  pop     r14
0x18000bdee  pop     r13
0x18000bdf0  pop     r12
0x18000bdf2  pop     rdi
0x18000bdf3  pop     rsi
0x18000bdf4  pop     rbx
0x18000bdf5  retn
0x18000bdf6  movzx   edi, word ptr [r13+rsi*8+8]
0x18000bdfc  mov     esi, 13h
0x18000be01  mov     rdx, [r15]
0x18000be04  movzx   ecx, word ptr [rdx]
0x18000be07  sub     ecx, 9
0x18000be0a  jz      loc_18000C2CD
0x18000be10  sub     ecx, 1
0x18000be13  jz      loc_18000C2CD
0x18000be19  sub     ecx, 3
0x18000be1c  jz      loc_18000C2CD
0x18000be22  cmp     ecx, esi
0x18000be24  jz      loc_18000C2CD
0x18000be2a  lea     rdx, [rsp+22F8h+String1]; wchar_t *
0x18000be32  mov     rcx, r15; this
0x18000be35  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000be3a  test    eax, eax
0x18000be3c  js      short loc_18000BDD3
0x18000be3e  mov     r13d, 8
0x18000be44  cmp     di, r13w
0x18000be48  jz      loc_18000C27E
0x18000be4e  cmp     di, 11h
0x18000be52  jz      loc_18000C057
0x18000be58  cmp     di, si
0x18000be5b  jz      loc_18000BFFF
0x18000be61  mov     eax, 4008h
0x18000be66  cmp     di, ax
0x18000be69  jnz     loc_18000C2B1
0x18000be6f  lea     rcx, [rsp+22F8h+String1]
0x18000be77  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000be7b  mov     rax, rsi
0x18000be7e  inc     rax
0x18000be81  cmp     [rcx+rax*2], bx
0x18000be85  jnz     short loc_18000BE7E
0x18000be87  add     eax, 2
0x18000be8a  mov     [rsp+22F8h+var_2158], rbx
0x18000be92  test    eax, eax
0x18000be94  jz      short loc_18000BECF
0x18000be96  movsxd  rcx, eax
0x18000be99  xor     edx, edx
0x18000be9b  mov     rax, rsi
0x18000be9e  div     rcx
0x18000bea1  cmp     rax, 2
0x18000bea5  jb      loc_18000C2DE
0x18000beab  lea     rdx, [rcx+rcx]
0x18000beaf  cmp     rdx, 100h
0x18000beb6  jbe     short loc_18000BECF
0x18000beb8  lea     rcx, [rsp+22F8h+var_2158]
0x18000bec0  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000bec5  mov     rdi, [rsp+22F8h+var_2158]
0x18000becd  jmp     short loc_18000BEDF
0x18000becf  lea     rdi, [rsp+22F8h+var_2150]
0x18000bed7  mov     [rsp+22F8h+var_2158], rdi
0x18000bedf  mov     r13, [rsp+22F8h+lpValueName]
0x18000bee4  jmp     short loc_18000BF08
0x18000bee6  xor     ebx, ebx
0x18000bee8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000beec  mov     rdi, [rsp+22F8h+var_2158]
0x18000bef4  mov     r12, qword ptr [rsp+22F8h+Data]
0x18000bef9  mov     rax, [rsp+22F8h+var_22A8]
0x18000befe  mov     [rsp+22F8h+var_22C0], rax
0x18000bf03  mov     r13, [rsp+22F8h+var_2298]
0x18000bf08  test    rdi, rdi
0x18000bf0b  jz      loc_18000BFC7
0x18000bf11  lea     r14, [rsp+22F8h+String1]
0x18000bf19  cmp     [rsp+22F8h+String1], bx
0x18000bf21  jz      short loc_18000BF64
0x18000bf23  mov     r15d, 30h ; '0'
0x18000bf29  mov     rcx, r14; lpsz
0x18000bf2c  call    cs:__imp_CharNextW
0x18000bf32  movzx   ecx, word ptr [r14]
0x18000bf36  cmp     cx, 5Ch ; '\'
0x18000bf3a  jnz     short loc_18000BF53
0x18000bf3c  cmp     [rax], r15w
0x18000bf40  jnz     short loc_18000BF53
0x18000bf42  mov     [rdi], bx
0x18000bf45  mov     rcx, rax; lpsz
0x18000bf48  call    cs:__imp_CharNextW
0x18000bf4e  mov     r14, rax
0x18000bf51  jmp     short loc_18000BF5A
0x18000bf53  mov     [rdi], cx
0x18000bf56  add     r14, 2
0x18000bf5a  add     rdi, 2
0x18000bf5e  cmp     [r14], bx
0x18000bf62  jnz     short loc_18000BF29
0x18000bf64  mov     dword ptr [rdi], 0
0x18000bf6a  mov     r8, [rsp+22F8h+var_2158]
0x18000bf72  test    r8, r8
0x18000bf75  jz      loc_18000C2E9
0x18000bf7b  mov     r10d, ebx
0x18000bf7e  mov     r9, r8
0x18000bf81  mov     rcx, rsi
0x18000bf84  inc     rcx
0x18000bf87  cmp     [r9+rcx*2], bx
0x18000bf8c  jnz     short loc_18000BF84
0x18000bf8e  inc     ecx
0x18000bf90  lea     r9, [r9+rcx*2]
0x18000bf94  lea     r10d, [r10+rcx*2]
0x18000bf98  cmp     ecx, 1
0x18000bf9b  jnz     short loc_18000BF81
0x18000bf9d  mov     [rsp+22F8h+cbData], r10d; cbData
0x18000bfa2  mov     [rsp+22F8h+lpData], r8; lpData
0x18000bfa7  lea     r9d, [rcx+6]; dwType
0x18000bfab  xor     r8d, r8d; Reserved
0x18000bfae  mov     rdx, r13; lpValueName
0x18000bfb1  mov     rcx, [r12]; hKey
0x18000bfb5  call    cs:__imp_RegSetValueExW
0x18000bfbb  mov     esi, eax
0x18000bfbd  mov     rdi, [rsp+22F8h+var_2158]
0x18000bfc5  jmp     short loc_18000BFCC
0x18000bfc7  mov     esi, 0Eh
0x18000bfcc  lea     rax, [rsp+22F8h+var_2150]
0x18000bfd4  cmp     rdi, rax
0x18000bfd7  jz      short loc_18000BFE6
0x18000bfd9  lea     rcx, [rsp+22F8h+var_2158]
0x18000bfe1  call    ?FreeHeap@?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::FreeHeap(void)
0x18000bfe6  mov     r15, [rsp+22F8h+var_22C0]
0x18000bfeb  test    esi, esi
0x18000bfed  jz      loc_18000C2B1
0x18000bff3  mov     ecx, esi; unsigned int
0x18000bff5  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000bffa  jmp     loc_18000BDD3
0x18000bfff  mov     [rsp+22F8h+pulOut], ebx
0x18000c003  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x18000c008  xor     r8d, r8d; dwFlags
0x18000c00b  xor     edx, edx; lcid
0x18000c00d  lea     rcx, [rsp+22F8h+String1]; strIn
0x18000c015  call    cs:__imp_VarUI4FromStr
0x18000c01b  test    eax, eax
0x18000c01d  js      loc_18000BDD3
0x18000c023  mov     eax, [rsp+22F8h+pulOut]
0x18000c027  mov     dword ptr [rsp+22F8h+Data], eax
0x18000c02b  mov     [rsp+22F8h+cbData], 4; cbData
0x18000c033  lea     rax, [rsp+22F8h+Data]
0x18000c038  mov     r9d, 4; dwType
0x18000c03e  mov     [rsp+22F8h+lpData], rax; lpData
0x18000c043  xor     r8d, r8d; Reserved
0x18000c046  mov     rdx, r14; lpValueName
0x18000c049  mov     rcx, [r12]; hKey
0x18000c04d  call    cs:__imp_RegSetValueExW
0x18000c053  mov     esi, eax
0x18000c055  jmp     short loc_18000BFEB
0x18000c057  lea     rax, [rsp+22F8h+String1]
0x18000c05f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000c063  mov     r14, rsi
0x18000c066  inc     r14
0x18000c069  cmp     [rax+r14*2], bx
0x18000c06e  jnz     short loc_18000C066
0x18000c070  mov     dword ptr [rsp+22F8h+Data], r14d
0x18000c075  test    r14b, 1
0x18000c079  jnz     loc_18000C133
0x18000c07f  mov     eax, r14d
0x18000c082  cdq
0x18000c083  sub     eax, edx
0x18000c085  sar     eax, 1
0x18000c087  movsxd  r12, eax
0x18000c08a  mov     [rsp+22F8h+var_2268], rbx
0x18000c092  mov     rdi, r12
0x18000c095  mov     [rsp+22F8h+var_2280], r12
0x18000c09a  test    eax, eax
0x18000c09c  jz      short loc_18000C0D3
0x18000c09e  xor     edx, edx
0x18000c0a0  mov     rax, rsi
0x18000c0a3  div     rdi
0x18000c0a6  cmp     rax, 1
0x18000c0aa  jb      loc_18000C2F4
0x18000c0b0  cmp     rdi, 100h
0x18000c0b7  jbe     short loc_18000C0D3
0x18000c0b9  mov     rdx, rdi
0x18000c0bc  lea     rcx, [rsp+22F8h+var_2268]
0x18000c0c4  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000c0c9  mov     rcx, [rsp+22F8h+var_2268]
0x18000c0d1  jmp     short loc_18000C0E3
0x18000c0d3  lea     rcx, [rsp+22F8h+var_2260]
0x18000c0db  mov     [rsp+22F8h+var_2268], rcx
0x18000c0e3  mov     rsi, [rsp+22F8h+var_2288]
0x18000c0e8  jmp     short loc_18000C121
0x18000c0ea  xor     ebx, ebx
0x18000c0ec  lea     r13d, [rbx+8]
0x18000c0f0  mov     r14d, dword ptr [rsp+22F8h+Data]
0x18000c0f5  mov     rcx, [rsp+22F8h+var_2268]; void *
0x18000c0fd  mov     rdi, [rsp+22F8h+var_2280]
0x18000c102  mov     rax, [rsp+22F8h+var_22A8]
0x18000c107  mov     [rsp+22F8h+var_22C0], rax
0x18000c10c  mov     rsi, [rsp+22F8h+var_2278]
0x18000c114  mov     rax, [rsp+22F8h+var_2298]
0x18000c119  mov     [rsp+22F8h+lpValueName], rax
0x18000c11e  mov     r12d, edi
0x18000c121  test    rcx, rcx
0x18000c124  jnz     short loc_18000C13D
0x18000c126  lea     rcx, [rsp+22F8h+var_2268]
0x18000c12e  call    ?FreeHeap@?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::FreeHeap(void)
0x18000c133  mov     eax, 80004005h
0x18000c138  jmp     loc_18000BDD3
0x18000c13d  mov     r8, rdi; Size
0x18000c140  xor     edx, edx; Val
0x18000c142  call    memset_0
0x18000c147  mov     r10d, ebx
0x18000c14a  test    r14d, r14d
0x18000c14d  jle     loc_18000C22B
0x18000c153  mov     r15d, 30h ; '0'
0x18000c159  mov     eax, r10d
0x18000c15c  movzx   edx, [rsp+rax*2+22F8h+String1]
0x18000c164  cmp     edx, 61h ; 'a'
0x18000c167  ja      short loc_18000C1D6
0x18000c169  jz      loc_18000C1F6
0x18000c16f  cmp     edx, 38h ; '8'
0x18000c172  ja      short loc_18000C1A8
0x18000c174  jz      short loc_18000C1A0
0x18000c176  mov     ecx, edx
0x18000c178  sub     ecx, r15d
0x18000c17b  jz      short loc_18000C1A0
0x18000c17d  sub     ecx, 1
0x18000c180  jz      short loc_18000C1A0
0x18000c182  sub     ecx, 1
0x18000c185  jz      short loc_18000C1A0
0x18000c187  sub     ecx, 1
0x18000c18a  jz      short loc_18000C1A0
0x18000c18c  sub     ecx, 1
0x18000c18f  jz      short loc_18000C1A0
0x18000c191  sub     ecx, 1
0x18000c194  jz      short loc_18000C1A0
0x18000c196  sub     ecx, 1
0x18000c199  jz      short loc_18000C1A0
0x18000c19b  cmp     ecx, 1
0x18000c19e  jnz     short loc_18000C1F1
0x18000c1a0  mov     r9d, edx
0x18000c1a3  sub     r9d, r15d
0x18000c1a6  jmp     short loc_18000C1FA
0x18000c1a8  mov     r9d, edx
0x18000c1ab  mov     ecx, edx
0x18000c1ad  sub     ecx, 39h ; '9'
0x18000c1b0  jz      short loc_18000C1A0
0x18000c1b2  sub     ecx, r13d
0x18000c1b5  jz      short loc_18000C1D0
0x18000c1b7  sub     ecx, 1
0x18000c1ba  jz      short loc_18000C1D0
0x18000c1bc  sub     ecx, 1
0x18000c1bf  jz      short loc_18000C1D0
0x18000c1c1  sub     ecx, 1
0x18000c1c4  jz      short loc_18000C1D0
0x18000c1c6  sub     ecx, 1
0x18000c1c9  jz      short loc_18000C1D0
0x18000c1cb  cmp     ecx, 1
0x18000c1ce  jnz     short loc_18000C1F1
0x18000c1d0  add     r9d, 0FFFFFFC9h
0x18000c1d4  jmp     short loc_18000C1FA
  ... truncated ...
```
