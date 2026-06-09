# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800030ac`
- end: `0x180003680`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180004c68`

## callees

- `0x1800030ac`
- `0x180003688`
- `0x1800037dc`
- `0x180004048`
- `0x180004220`
- `0x180004304`
- `0x180011302`
- `0x180011340`
- `0x180011400`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x180003395`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180003395`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800032ac`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800032c8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003650`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800032ac`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800032c8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003650`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003335`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800033cd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800035ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003335`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800033cd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800035ce`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000313d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000313d`

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
0x1800030ac  push    rbx
0x1800030ae  push    rsi
0x1800030af  push    rdi
0x1800030b0  push    r12
0x1800030b2  push    r13
0x1800030b4  push    r14
0x1800030b6  push    r15
0x1800030b8  mov     eax, 22C0h
0x1800030bd  call    _alloca_probe
0x1800030c2  sub     rsp, rax
0x1800030c5  mov     rax, cs:__security_cookie
0x1800030cc  xor     rax, rsp
0x1800030cf  mov     [rsp+22F8h+var_48], rax
0x1800030d7  mov     r14, r8
0x1800030da  mov     [rsp+22F8h+lpValueName], r8
0x1800030df  mov     r12, rdx
0x1800030e2  mov     [rsp+22F8h+var_2288], rdx
0x1800030e7  mov     r15, rcx
0x1800030ea  mov     [rsp+22F8h+var_22C0], rcx
0x1800030ef  mov     qword ptr [rsp+22F8h+Data], rdx
0x1800030f4  mov     [rsp+22F8h+var_22A8], rcx
0x1800030f9  mov     [rsp+22F8h+var_2278], rdx
0x180003101  mov     [rsp+22F8h+var_2298], r8
0x180003106  mov     [rsp+22F8h+var_2270], r9
0x18000310e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180003116  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000311b  xor     ebx, ebx
0x18000311d  test    eax, eax
0x18000311f  js      short loc_180003153
0x180003121  mov     edi, ebx
0x180003123  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000312a  movsxd  rsi, edi
0x18000312d  add     rsi, rsi
0x180003130  mov     rdx, [r13+rsi*8+0]; lpString2
0x180003135  lea     rcx, [rsp+22F8h+String1]; lpString1
0x18000313d  call    cs:__imp_lstrcmpiW
0x180003143  test    eax, eax
0x180003145  jz      short loc_180003176
0x180003147  inc     edi
0x180003149  cmp     edi, 4
0x18000314c  jb      short loc_18000312A
0x18000314e  mov     eax, 80020009h
0x180003153  mov     rcx, [rsp+22F8h+var_48]
0x18000315b  xor     rcx, rsp; StackCookie
0x18000315e  call    __security_check_cookie
0x180003163  add     rsp, 22C0h
0x18000316a  pop     r15
0x18000316c  pop     r14
0x18000316e  pop     r13
0x180003170  pop     r12
0x180003172  pop     rdi
0x180003173  pop     rsi
0x180003174  pop     rbx
0x180003175  retn
0x180003176  movzx   edi, word ptr [r13+rsi*8+8]
0x18000317c  mov     esi, 13h
0x180003181  mov     rdx, [r15]
0x180003184  movzx   ecx, word ptr [rdx]
0x180003187  sub     ecx, 9
0x18000318a  jz      loc_18000364D
0x180003190  sub     ecx, 1
0x180003193  jz      loc_18000364D
0x180003199  sub     ecx, 3
0x18000319c  jz      loc_18000364D
0x1800031a2  cmp     ecx, esi
0x1800031a4  jz      loc_18000364D
0x1800031aa  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1800031b2  mov     rcx, r15; this
0x1800031b5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800031ba  test    eax, eax
0x1800031bc  js      short loc_180003153
0x1800031be  mov     r13d, 8
0x1800031c4  cmp     di, r13w
0x1800031c8  jz      loc_1800035FE
0x1800031ce  cmp     di, 11h
0x1800031d2  jz      loc_1800033D7
0x1800031d8  cmp     di, si
0x1800031db  jz      loc_18000337F
0x1800031e1  mov     eax, 4008h
0x1800031e6  cmp     di, ax
0x1800031e9  jnz     loc_180003631
0x1800031ef  lea     rcx, [rsp+22F8h+String1]
0x1800031f7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800031fb  mov     rax, rsi
0x1800031fe  inc     rax
0x180003201  cmp     [rcx+rax*2], bx
0x180003205  jnz     short loc_1800031FE
0x180003207  add     eax, 2
0x18000320a  mov     [rsp+22F8h+var_2158], rbx
0x180003212  test    eax, eax
0x180003214  jz      short loc_18000324F
0x180003216  movsxd  rcx, eax
0x180003219  xor     edx, edx
0x18000321b  mov     rax, rsi
0x18000321e  div     rcx
0x180003221  cmp     rax, 2
0x180003225  jb      loc_18000365E
0x18000322b  lea     rdx, [rcx+rcx]
0x18000322f  cmp     rdx, 100h
0x180003236  jbe     short loc_18000324F
0x180003238  lea     rcx, [rsp+22F8h+var_2158]
0x180003240  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180003245  mov     rdi, [rsp+22F8h+var_2158]
0x18000324d  jmp     short loc_18000325F
0x18000324f  lea     rdi, [rsp+22F8h+var_2150]
0x180003257  mov     [rsp+22F8h+var_2158], rdi
0x18000325f  mov     r13, [rsp+22F8h+lpValueName]
0x180003264  jmp     short loc_180003288
0x180003266  xor     ebx, ebx
0x180003268  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000326c  mov     rdi, [rsp+22F8h+var_2158]
0x180003274  mov     r12, qword ptr [rsp+22F8h+Data]
0x180003279  mov     rax, [rsp+22F8h+var_22A8]
0x18000327e  mov     [rsp+22F8h+var_22C0], rax
0x180003283  mov     r13, [rsp+22F8h+var_2298]
0x180003288  test    rdi, rdi
0x18000328b  jz      loc_180003347
0x180003291  lea     r14, [rsp+22F8h+String1]
0x180003299  cmp     [rsp+22F8h+String1], bx
0x1800032a1  jz      short loc_1800032E4
0x1800032a3  mov     r15d, 30h ; '0'
0x1800032a9  mov     rcx, r14; lpsz
0x1800032ac  call    cs:__imp_CharNextW
0x1800032b2  movzx   ecx, word ptr [r14]
0x1800032b6  cmp     cx, 5Ch ; '\'
0x1800032ba  jnz     short loc_1800032D3
0x1800032bc  cmp     [rax], r15w
0x1800032c0  jnz     short loc_1800032D3
0x1800032c2  mov     [rdi], bx
0x1800032c5  mov     rcx, rax; lpsz
0x1800032c8  call    cs:__imp_CharNextW
0x1800032ce  mov     r14, rax
0x1800032d1  jmp     short loc_1800032DA
0x1800032d3  mov     [rdi], cx
0x1800032d6  add     r14, 2
0x1800032da  add     rdi, 2
0x1800032de  cmp     [r14], bx
0x1800032e2  jnz     short loc_1800032A9
0x1800032e4  mov     dword ptr [rdi], 0
0x1800032ea  mov     r8, [rsp+22F8h+var_2158]
0x1800032f2  test    r8, r8
0x1800032f5  jz      loc_180003669
0x1800032fb  mov     r10d, ebx
0x1800032fe  mov     r9, r8
0x180003301  mov     rcx, rsi
0x180003304  inc     rcx
0x180003307  cmp     [r9+rcx*2], bx
0x18000330c  jnz     short loc_180003304
0x18000330e  inc     ecx
0x180003310  lea     r9, [r9+rcx*2]
0x180003314  lea     r10d, [r10+rcx*2]
0x180003318  cmp     ecx, 1
0x18000331b  jnz     short loc_180003301
0x18000331d  mov     [rsp+22F8h+cbData], r10d; cbData
0x180003322  mov     [rsp+22F8h+lpData], r8; lpData
0x180003327  lea     r9d, [rcx+6]; dwType
0x18000332b  xor     r8d, r8d; Reserved
0x18000332e  mov     rdx, r13; lpValueName
0x180003331  mov     rcx, [r12]; hKey
0x180003335  call    cs:__imp_RegSetValueExW
0x18000333b  mov     esi, eax
0x18000333d  mov     rdi, [rsp+22F8h+var_2158]
0x180003345  jmp     short loc_18000334C
0x180003347  mov     esi, 0Eh
0x18000334c  lea     rax, [rsp+22F8h+var_2150]
0x180003354  cmp     rdi, rax
0x180003357  jz      short loc_180003366
0x180003359  lea     rcx, [rsp+22F8h+var_2158]
0x180003361  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180003366  mov     r15, [rsp+22F8h+var_22C0]
0x18000336b  test    esi, esi
0x18000336d  jz      loc_180003631
0x180003373  mov     ecx, esi; unsigned int
0x180003375  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000337a  jmp     loc_180003153
0x18000337f  mov     [rsp+22F8h+pulOut], ebx
0x180003383  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x180003388  xor     r8d, r8d; dwFlags
0x18000338b  xor     edx, edx; lcid
0x18000338d  lea     rcx, [rsp+22F8h+String1]; strIn
0x180003395  call    cs:__imp_VarUI4FromStr
0x18000339b  test    eax, eax
0x18000339d  js      loc_180003153
0x1800033a3  mov     eax, [rsp+22F8h+pulOut]
0x1800033a7  mov     dword ptr [rsp+22F8h+Data], eax
0x1800033ab  mov     [rsp+22F8h+cbData], 4; cbData
0x1800033b3  lea     rax, [rsp+22F8h+Data]
0x1800033b8  mov     r9d, 4; dwType
0x1800033be  mov     [rsp+22F8h+lpData], rax; lpData
0x1800033c3  xor     r8d, r8d; Reserved
0x1800033c6  mov     rdx, r14; lpValueName
0x1800033c9  mov     rcx, [r12]; hKey
0x1800033cd  call    cs:__imp_RegSetValueExW
0x1800033d3  mov     esi, eax
0x1800033d5  jmp     short loc_18000336B
0x1800033d7  lea     rax, [rsp+22F8h+String1]
0x1800033df  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800033e3  mov     r14, rsi
0x1800033e6  inc     r14
0x1800033e9  cmp     [rax+r14*2], bx
0x1800033ee  jnz     short loc_1800033E6
0x1800033f0  mov     dword ptr [rsp+22F8h+Data], r14d
0x1800033f5  test    r14b, 1
0x1800033f9  jnz     loc_1800034B3
0x1800033ff  mov     eax, r14d
0x180003402  cdq
0x180003403  sub     eax, edx
0x180003405  sar     eax, 1
0x180003407  movsxd  r12, eax
0x18000340a  mov     [rsp+22F8h+var_2268], rbx
0x180003412  mov     rdi, r12
0x180003415  mov     [rsp+22F8h+var_2280], r12
0x18000341a  test    eax, eax
0x18000341c  jz      short loc_180003453
0x18000341e  xor     edx, edx
0x180003420  mov     rax, rsi
0x180003423  div     rdi
0x180003426  cmp     rax, 1
0x18000342a  jb      loc_180003674
0x180003430  cmp     rdi, 100h
0x180003437  jbe     short loc_180003453
0x180003439  mov     rdx, rdi
0x18000343c  lea     rcx, [rsp+22F8h+var_2268]
0x180003444  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180003449  mov     rcx, [rsp+22F8h+var_2268]
0x180003451  jmp     short loc_180003463
0x180003453  lea     rcx, [rsp+22F8h+var_2260]
0x18000345b  mov     [rsp+22F8h+var_2268], rcx
0x180003463  mov     rsi, [rsp+22F8h+var_2288]
0x180003468  jmp     short loc_1800034A1
0x18000346a  xor     ebx, ebx
0x18000346c  lea     r13d, [rbx+8]
0x180003470  mov     r14d, dword ptr [rsp+22F8h+Data]
0x180003475  mov     rcx, [rsp+22F8h+var_2268]; void *
0x18000347d  mov     rdi, [rsp+22F8h+var_2280]
0x180003482  mov     rax, [rsp+22F8h+var_22A8]
0x180003487  mov     [rsp+22F8h+var_22C0], rax
0x18000348c  mov     rsi, [rsp+22F8h+var_2278]
0x180003494  mov     rax, [rsp+22F8h+var_2298]
0x180003499  mov     [rsp+22F8h+lpValueName], rax
0x18000349e  mov     r12d, edi
0x1800034a1  test    rcx, rcx
0x1800034a4  jnz     short loc_1800034BD
0x1800034a6  lea     rcx, [rsp+22F8h+var_2268]
0x1800034ae  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800034b3  mov     eax, 80004005h
0x1800034b8  jmp     loc_180003153
0x1800034bd  mov     r8, rdi; Size
0x1800034c0  xor     edx, edx; Val
0x1800034c2  call    memset_0
0x1800034c7  mov     r10d, ebx
0x1800034ca  test    r14d, r14d
0x1800034cd  jle     loc_1800035AB
0x1800034d3  mov     r15d, 30h ; '0'
0x1800034d9  mov     eax, r10d
0x1800034dc  movzx   edx, [rsp+rax*2+22F8h+String1]
0x1800034e4  cmp     edx, 61h ; 'a'
0x1800034e7  ja      short loc_180003556
0x1800034e9  jz      loc_180003576
0x1800034ef  cmp     edx, 38h ; '8'
0x1800034f2  ja      short loc_180003528
0x1800034f4  jz      short loc_180003520
0x1800034f6  mov     ecx, edx
0x1800034f8  sub     ecx, r15d
0x1800034fb  jz      short loc_180003520
0x1800034fd  sub     ecx, 1
0x180003500  jz      short loc_180003520
0x180003502  sub     ecx, 1
0x180003505  jz      short loc_180003520
0x180003507  sub     ecx, 1
0x18000350a  jz      short loc_180003520
0x18000350c  sub     ecx, 1
0x18000350f  jz      short loc_180003520
0x180003511  sub     ecx, 1
0x180003514  jz      short loc_180003520
0x180003516  sub     ecx, 1
0x180003519  jz      short loc_180003520
0x18000351b  cmp     ecx, 1
0x18000351e  jnz     short loc_180003571
0x180003520  mov     r9d, edx
0x180003523  sub     r9d, r15d
0x180003526  jmp     short loc_18000357A
0x180003528  mov     r9d, edx
0x18000352b  mov     ecx, edx
0x18000352d  sub     ecx, 39h ; '9'
0x180003530  jz      short loc_180003520
0x180003532  sub     ecx, r13d
0x180003535  jz      short loc_180003550
0x180003537  sub     ecx, 1
0x18000353a  jz      short loc_180003550
0x18000353c  sub     ecx, 1
0x18000353f  jz      short loc_180003550
0x180003541  sub     ecx, 1
0x180003544  jz      short loc_180003550
0x180003546  sub     ecx, 1
0x180003549  jz      short loc_180003550
0x18000354b  cmp     ecx, 1
0x18000354e  jnz     short loc_180003571
0x180003550  add     r9d, 0FFFFFFC9h
0x180003554  jmp     short loc_18000357A
  ... truncated ...
```
