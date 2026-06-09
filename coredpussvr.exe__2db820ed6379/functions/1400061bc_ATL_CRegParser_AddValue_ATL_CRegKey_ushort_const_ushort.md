# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1400061bc`
- end: `0x1400067c1`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1541`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140007a88`

## callees

- `0x140001500`
- `0x14000215c`
- `0x1400061bc`
- `0x1400067c8`
- `0x140006928`
- `0x140006940`
- `0x140006e04`
- `0x140006f40`
- `0x140009030`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400063c3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400063e5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000678b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400063c3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400063e5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000678b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140006458`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400064fc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140006703`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140006458`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400064fc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140006703`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14000624d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14000624d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1400064be`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1400064be`

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
0x1400061bc  push    rbx
0x1400061be  push    rsi
0x1400061bf  push    rdi
0x1400061c0  push    r12
0x1400061c2  push    r13
0x1400061c4  push    r14
0x1400061c6  push    r15
0x1400061c8  mov     eax, 22C0h
0x1400061cd  call    _alloca_probe
0x1400061d2  sub     rsp, rax
0x1400061d5  mov     rax, cs:__security_cookie
0x1400061dc  xor     rax, rsp
0x1400061df  mov     [rsp+22F8h+var_48], rax
0x1400061e7  mov     r14, r8
0x1400061ea  mov     [rsp+22F8h+lpValueName], r8
0x1400061ef  mov     r12, rdx
0x1400061f2  mov     [rsp+22F8h+var_2288], rdx
0x1400061f7  mov     r15, rcx
0x1400061fa  mov     [rsp+22F8h+var_22C0], rcx
0x1400061ff  mov     qword ptr [rsp+22F8h+Data], rdx
0x140006204  mov     [rsp+22F8h+var_22A8], rcx
0x140006209  mov     [rsp+22F8h+var_2278], rdx
0x140006211  mov     [rsp+22F8h+var_2298], r8
0x140006216  mov     [rsp+22F8h+var_2270], r9
0x14000621e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x140006226  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000622b  xor     ebx, ebx
0x14000622d  test    eax, eax
0x14000622f  js      short loc_140006269
0x140006231  mov     edi, ebx
0x140006233  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x14000623a  movsxd  rsi, edi
0x14000623d  add     rsi, rsi
0x140006240  mov     rdx, [r13+rsi*8+0]; lpString2
0x140006245  lea     rcx, [rsp+22F8h+String1]; lpString1
0x14000624d  call    cs:__imp_lstrcmpiW
0x140006254  nop     dword ptr [rax+rax+00h]
0x140006259  test    eax, eax
0x14000625b  jz      short loc_14000628D
0x14000625d  inc     edi
0x14000625f  cmp     edi, 4
0x140006262  jb      short loc_14000623A
0x140006264  mov     eax, 80020009h
0x140006269  mov     rcx, [rsp+22F8h+var_48]
0x140006271  xor     rcx, rsp; StackCookie
0x140006274  call    __security_check_cookie
0x140006279  add     rsp, 22C0h
0x140006280  pop     r15
0x140006282  pop     r14
0x140006284  pop     r13
0x140006286  pop     r12
0x140006288  pop     rdi
0x140006289  pop     rsi
0x14000628a  pop     rbx
0x14000628b  retn
0x14000628d  movzx   edi, word ptr [r13+rsi*8+8]
0x140006293  mov     esi, 13h
0x140006298  mov     rdx, [r15]
0x14000629b  movzx   ecx, word ptr [rdx]
0x14000629e  sub     ecx, 9
0x1400062a1  jz      loc_140006788
0x1400062a7  sub     ecx, 1
0x1400062aa  jz      loc_140006788
0x1400062b0  sub     ecx, 3
0x1400062b3  jz      loc_140006788
0x1400062b9  cmp     ecx, esi
0x1400062bb  jz      loc_140006788
0x1400062c1  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1400062c9  mov     rcx, r15; this
0x1400062cc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400062d1  test    eax, eax
0x1400062d3  js      short loc_140006269
0x1400062d5  mov     r13d, 8
0x1400062db  cmp     di, r13w
0x1400062df  jz      loc_140006739
0x1400062e5  cmp     di, 11h
0x1400062e9  jz      loc_14000650C
0x1400062ef  cmp     di, si
0x1400062f2  jz      loc_1400064A8
0x1400062f8  mov     eax, 4008h
0x1400062fd  cmp     di, ax
0x140006300  jnz     loc_14000676C
0x140006306  lea     rcx, [rsp+22F8h+String1]
0x14000630e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140006312  mov     rax, rsi
0x140006315  inc     rax
0x140006318  cmp     [rcx+rax*2], bx
0x14000631c  jnz     short loc_140006315
0x14000631e  add     eax, 2
0x140006321  mov     [rsp+22F8h+var_2158], rbx
0x140006329  test    eax, eax
0x14000632b  jz      short loc_140006366
0x14000632d  movsxd  rcx, eax
0x140006330  xor     edx, edx
0x140006332  mov     rax, rsi
0x140006335  div     rcx
0x140006338  cmp     rax, 2
0x14000633c  jb      loc_14000679F
0x140006342  lea     rdx, [rcx+rcx]
0x140006346  cmp     rdx, 100h
0x14000634d  jbe     short loc_140006366
0x14000634f  lea     rcx, [rsp+22F8h+var_2158]
0x140006357  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x14000635c  mov     rdi, [rsp+22F8h+var_2158]
0x140006364  jmp     short loc_140006376
0x140006366  lea     rdi, [rsp+22F8h+var_2150]
0x14000636e  mov     [rsp+22F8h+var_2158], rdi
0x140006376  mov     r13, [rsp+22F8h+lpValueName]
0x14000637b  jmp     short loc_14000639F
0x14000637d  xor     ebx, ebx
0x14000637f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140006383  mov     rdi, [rsp+22F8h+var_2158]
0x14000638b  mov     r12, qword ptr [rsp+22F8h+Data]
0x140006390  mov     rax, [rsp+22F8h+var_22A8]
0x140006395  mov     [rsp+22F8h+var_22C0], rax
0x14000639a  mov     r13, [rsp+22F8h+var_2298]
0x14000639f  test    rdi, rdi
0x1400063a2  jz      loc_140006470
0x1400063a8  lea     r14, [rsp+22F8h+String1]
0x1400063b0  cmp     [rsp+22F8h+String1], bx
0x1400063b8  jz      short loc_140006407
0x1400063ba  mov     r15d, 30h ; '0'
0x1400063c0  mov     rcx, r14; lpsz
0x1400063c3  call    cs:__imp_CharNextW
0x1400063ca  nop     dword ptr [rax+rax+00h]
0x1400063cf  movzx   ecx, word ptr [r14]
0x1400063d3  cmp     cx, 5Ch ; '\'
0x1400063d7  jnz     short loc_1400063F6
0x1400063d9  cmp     [rax], r15w
0x1400063dd  jnz     short loc_1400063F6
0x1400063df  mov     [rdi], bx
0x1400063e2  mov     rcx, rax; lpsz
0x1400063e5  call    cs:__imp_CharNextW
0x1400063ec  nop     dword ptr [rax+rax+00h]
0x1400063f1  mov     r14, rax
0x1400063f4  jmp     short loc_1400063FD
0x1400063f6  mov     [rdi], cx
0x1400063f9  add     r14, 2
0x1400063fd  add     rdi, 2
0x140006401  cmp     [r14], bx
0x140006405  jnz     short loc_1400063C0
0x140006407  mov     dword ptr [rdi], 0
0x14000640d  mov     r8, [rsp+22F8h+var_2158]
0x140006415  test    r8, r8
0x140006418  jz      loc_1400067AA
0x14000641e  mov     r10d, ebx
0x140006421  mov     r9, r8
0x140006424  mov     rcx, rsi
0x140006427  inc     rcx
0x14000642a  cmp     [r9+rcx*2], bx
0x14000642f  jnz     short loc_140006427
0x140006431  inc     ecx
0x140006433  lea     r9, [r9+rcx*2]
0x140006437  lea     r10d, [r10+rcx*2]
0x14000643b  cmp     ecx, 1
0x14000643e  jnz     short loc_140006424
0x140006440  mov     [rsp+22F8h+cbData], r10d; cbData
0x140006445  mov     [rsp+22F8h+lpData], r8; lpData
0x14000644a  lea     r9d, [rcx+6]; dwType
0x14000644e  xor     r8d, r8d; Reserved
0x140006451  mov     rdx, r13; lpValueName
0x140006454  mov     rcx, [r12]; hKey
0x140006458  call    cs:__imp_RegSetValueExW
0x14000645f  nop     dword ptr [rax+rax+00h]
0x140006464  mov     esi, eax
0x140006466  mov     rdi, [rsp+22F8h+var_2158]
0x14000646e  jmp     short loc_140006475
0x140006470  mov     esi, 0Eh
0x140006475  lea     rax, [rsp+22F8h+var_2150]
0x14000647d  cmp     rdi, rax
0x140006480  jz      short loc_14000648F
0x140006482  lea     rcx, [rsp+22F8h+var_2158]
0x14000648a  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x14000648f  mov     r15, [rsp+22F8h+var_22C0]
0x140006494  test    esi, esi
0x140006496  jz      loc_14000676C
0x14000649c  mov     ecx, esi; unsigned int
0x14000649e  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1400064a3  jmp     loc_140006269
0x1400064a8  mov     [rsp+22F8h+pulOut], ebx
0x1400064ac  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x1400064b1  xor     r8d, r8d; dwFlags
0x1400064b4  xor     edx, edx; lcid
0x1400064b6  lea     rcx, [rsp+22F8h+String1]; strIn
0x1400064be  call    cs:__imp_VarUI4FromStr
0x1400064c5  nop     dword ptr [rax+rax+00h]
0x1400064ca  test    eax, eax
0x1400064cc  js      loc_140006269
0x1400064d2  mov     eax, [rsp+22F8h+pulOut]
0x1400064d6  mov     dword ptr [rsp+22F8h+Data], eax
0x1400064da  mov     [rsp+22F8h+cbData], 4; cbData
0x1400064e2  lea     rax, [rsp+22F8h+Data]
0x1400064e7  mov     r9d, 4; dwType
0x1400064ed  mov     [rsp+22F8h+lpData], rax; lpData
0x1400064f2  xor     r8d, r8d; Reserved
0x1400064f5  mov     rdx, r14; lpValueName
0x1400064f8  mov     rcx, [r12]; hKey
0x1400064fc  call    cs:__imp_RegSetValueExW
0x140006503  nop     dword ptr [rax+rax+00h]
0x140006508  mov     esi, eax
0x14000650a  jmp     short loc_140006494
0x14000650c  lea     rax, [rsp+22F8h+String1]
0x140006514  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140006518  mov     r14, rsi
0x14000651b  inc     r14
0x14000651e  cmp     [rax+r14*2], bx
0x140006523  jnz     short loc_14000651B
0x140006525  mov     dword ptr [rsp+22F8h+Data], r14d
0x14000652a  test    r14b, 1
0x14000652e  jnz     loc_1400065E8
0x140006534  mov     eax, r14d
0x140006537  cdq
0x140006538  sub     eax, edx
0x14000653a  sar     eax, 1
0x14000653c  movsxd  r12, eax
0x14000653f  mov     [rsp+22F8h+var_2268], rbx
0x140006547  mov     rdi, r12
0x14000654a  mov     [rsp+22F8h+var_2280], r12
0x14000654f  test    eax, eax
0x140006551  jz      short loc_140006588
0x140006553  xor     edx, edx
0x140006555  mov     rax, rsi
0x140006558  div     rdi
0x14000655b  cmp     rax, 1
0x14000655f  jb      loc_1400067B5
0x140006565  cmp     rdi, 100h
0x14000656c  jbe     short loc_140006588
0x14000656e  mov     rdx, rdi
0x140006571  lea     rcx, [rsp+22F8h+var_2268]
0x140006579  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x14000657e  mov     rcx, [rsp+22F8h+var_2268]
0x140006586  jmp     short loc_140006598
0x140006588  lea     rcx, [rsp+22F8h+var_2260]
0x140006590  mov     [rsp+22F8h+var_2268], rcx
0x140006598  mov     rsi, [rsp+22F8h+var_2288]
0x14000659d  jmp     short loc_1400065D6
0x14000659f  xor     ebx, ebx
0x1400065a1  lea     r13d, [rbx+8]
0x1400065a5  mov     r14d, dword ptr [rsp+22F8h+Data]
0x1400065aa  mov     rcx, [rsp+22F8h+var_2268]; void *
0x1400065b2  mov     rdi, [rsp+22F8h+var_2280]
0x1400065b7  mov     rax, [rsp+22F8h+var_22A8]
0x1400065bc  mov     [rsp+22F8h+var_22C0], rax
0x1400065c1  mov     rsi, [rsp+22F8h+var_2278]
0x1400065c9  mov     rax, [rsp+22F8h+var_2298]
0x1400065ce  mov     [rsp+22F8h+lpValueName], rax
0x1400065d3  mov     r12d, edi
0x1400065d6  test    rcx, rcx
0x1400065d9  jnz     short loc_1400065F2
0x1400065db  lea     rcx, [rsp+22F8h+var_2268]
0x1400065e3  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1400065e8  mov     eax, 80004005h
0x1400065ed  jmp     loc_140006269
0x1400065f2  mov     r8, rdi; Size
0x1400065f5  xor     edx, edx; Val
0x1400065f7  call    memset_0
0x1400065fc  mov     r10d, ebx
0x1400065ff  test    r14d, r14d
0x140006602  jle     loc_1400066E0
0x140006608  mov     r15d, 30h ; '0'
0x14000660e  mov     eax, r10d
0x140006611  movzx   edx, [rsp+rax*2+22F8h+String1]
0x140006619  cmp     edx, 61h ; 'a'
0x14000661c  ja      short loc_14000668B
0x14000661e  jz      loc_1400066AB
0x140006624  cmp     edx, 38h ; '8'
0x140006627  ja      short loc_14000665D
0x140006629  jz      short loc_140006655
0x14000662b  mov     ecx, edx
0x14000662d  sub     ecx, r15d
0x140006630  jz      short loc_140006655
0x140006632  sub     ecx, 1
0x140006635  jz      short loc_140006655
0x140006637  sub     ecx, 1
0x14000663a  jz      short loc_140006655
0x14000663c  sub     ecx, 1
0x14000663f  jz      short loc_140006655
0x140006641  sub     ecx, 1
0x140006644  jz      short loc_140006655
0x140006646  sub     ecx, 1
0x140006649  jz      short loc_140006655
0x14000664b  sub     ecx, 1
0x14000664e  jz      short loc_140006655
0x140006650  cmp     ecx, 1
0x140006653  jnz     short loc_1400066A6
0x140006655  mov     r9d, edx
0x140006658  sub     r9d, r15d
0x14000665b  jmp     short loc_1400066AF
0x14000665d  mov     r9d, edx
0x140006660  mov     ecx, edx
0x140006662  sub     ecx, 39h ; '9'
0x140006665  jz      short loc_140006655
0x140006667  sub     ecx, r13d
0x14000666a  jz      short loc_140006685
0x14000666c  sub     ecx, 1
0x14000666f  jz      short loc_140006685
0x140006671  sub     ecx, 1
0x140006674  jz      short loc_140006685
0x140006676  sub     ecx, 1
0x140006679  jz      short loc_140006685
  ... truncated ...
```
