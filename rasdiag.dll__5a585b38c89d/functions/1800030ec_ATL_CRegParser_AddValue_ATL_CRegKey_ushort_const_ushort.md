# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800030ec`
- end: `0x1800036f1`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1541`
- prototype: `HRESULT __fastcall(LPCWSTR *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180004ef8`

## callees

- `0x1800030ec`
- `0x1800036f8`
- `0x180003864`
- `0x18000418c`
- `0x1800043bc`
- `0x1800044c4`
- `0x18000ded2`
- `0x18000df10`
- `0x18000dfd0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18000317d`
- `KERNEL32!lstrcmpiW` at `0x18000317d`
- `ADVAPI32!RegSetValueExW` at `0x180003388`
- `ADVAPI32!RegSetValueExW` at `0x18000342c`
- `ADVAPI32!RegSetValueExW` at `0x180003633`
- `ADVAPI32!RegSetValueExW` at `0x180003388`
- `ADVAPI32!RegSetValueExW` at `0x18000342c`
- `ADVAPI32!RegSetValueExW` at `0x180003633`
- `USER32!CharNextW` at `0x1800032f3`
- `USER32!CharNextW` at `0x180003315`
- `USER32!CharNextW` at `0x1800036bb`
- `USER32!CharNextW` at `0x1800032f3`
- `USER32!CharNextW` at `0x180003315`
- `USER32!CharNextW` at `0x1800036bb`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800033ee`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800033ee`

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
0x1800030ec  push    rbx
0x1800030ee  push    rsi
0x1800030ef  push    rdi
0x1800030f0  push    r12
0x1800030f2  push    r13
0x1800030f4  push    r14
0x1800030f6  push    r15
0x1800030f8  mov     eax, 22C0h
0x1800030fd  call    _alloca_probe
0x180003102  sub     rsp, rax
0x180003105  mov     rax, cs:__security_cookie
0x18000310c  xor     rax, rsp
0x18000310f  mov     [rsp+22F8h+var_48], rax
0x180003117  mov     r14, r8
0x18000311a  mov     [rsp+22F8h+lpValueName], r8
0x18000311f  mov     r12, rdx
0x180003122  mov     [rsp+22F8h+var_2288], rdx
0x180003127  mov     r15, rcx
0x18000312a  mov     [rsp+22F8h+var_22C0], rcx
0x18000312f  mov     qword ptr [rsp+22F8h+Data], rdx
0x180003134  mov     [rsp+22F8h+var_22A8], rcx
0x180003139  mov     [rsp+22F8h+var_2278], rdx
0x180003141  mov     [rsp+22F8h+var_2298], r8
0x180003146  mov     [rsp+22F8h+var_2270], r9
0x18000314e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180003156  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000315b  xor     ebx, ebx
0x18000315d  test    eax, eax
0x18000315f  js      short loc_180003199
0x180003161  mov     edi, ebx
0x180003163  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000316a  movsxd  rsi, edi
0x18000316d  add     rsi, rsi
0x180003170  mov     rdx, [r13+rsi*8+0]; lpString2
0x180003175  lea     rcx, [rsp+22F8h+String1]; lpString1
0x18000317d  call    cs:__imp_lstrcmpiW
0x180003184  nop     dword ptr [rax+rax+00h]
0x180003189  test    eax, eax
0x18000318b  jz      short loc_1800031BD
0x18000318d  inc     edi
0x18000318f  cmp     edi, 4
0x180003192  jb      short loc_18000316A
0x180003194  mov     eax, 80020009h
0x180003199  mov     rcx, [rsp+22F8h+var_48]
0x1800031a1  xor     rcx, rsp; StackCookie
0x1800031a4  call    __security_check_cookie
0x1800031a9  add     rsp, 22C0h
0x1800031b0  pop     r15
0x1800031b2  pop     r14
0x1800031b4  pop     r13
0x1800031b6  pop     r12
0x1800031b8  pop     rdi
0x1800031b9  pop     rsi
0x1800031ba  pop     rbx
0x1800031bb  retn
0x1800031bd  movzx   edi, word ptr [r13+rsi*8+8]
0x1800031c3  mov     esi, 13h
0x1800031c8  mov     rdx, [r15]
0x1800031cb  movzx   ecx, word ptr [rdx]
0x1800031ce  sub     ecx, 9
0x1800031d1  jz      loc_1800036B8
0x1800031d7  sub     ecx, 1
0x1800031da  jz      loc_1800036B8
0x1800031e0  sub     ecx, 3
0x1800031e3  jz      loc_1800036B8
0x1800031e9  cmp     ecx, esi
0x1800031eb  jz      loc_1800036B8
0x1800031f1  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1800031f9  mov     rcx, r15; this
0x1800031fc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003201  test    eax, eax
0x180003203  js      short loc_180003199
0x180003205  mov     r13d, 8
0x18000320b  cmp     di, r13w
0x18000320f  jz      loc_180003669
0x180003215  cmp     di, 11h
0x180003219  jz      loc_18000343C
0x18000321f  cmp     di, si
0x180003222  jz      loc_1800033D8
0x180003228  mov     eax, 4008h
0x18000322d  cmp     di, ax
0x180003230  jnz     loc_18000369C
0x180003236  lea     rcx, [rsp+22F8h+String1]
0x18000323e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003242  mov     rax, rsi
0x180003245  inc     rax
0x180003248  cmp     [rcx+rax*2], bx
0x18000324c  jnz     short loc_180003245
0x18000324e  add     eax, 2
0x180003251  mov     [rsp+22F8h+var_2158], rbx
0x180003259  test    eax, eax
0x18000325b  jz      short loc_180003296
0x18000325d  movsxd  rcx, eax
0x180003260  xor     edx, edx
0x180003262  mov     rax, rsi
0x180003265  div     rcx
0x180003268  cmp     rax, 2
0x18000326c  jb      loc_1800036CF
0x180003272  lea     rdx, [rcx+rcx]
0x180003276  cmp     rdx, 100h
0x18000327d  jbe     short loc_180003296
0x18000327f  lea     rcx, [rsp+22F8h+var_2158]
0x180003287  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000328c  mov     rdi, [rsp+22F8h+var_2158]
0x180003294  jmp     short loc_1800032A6
0x180003296  lea     rdi, [rsp+22F8h+var_2150]
0x18000329e  mov     [rsp+22F8h+var_2158], rdi
0x1800032a6  mov     r13, [rsp+22F8h+lpValueName]
0x1800032ab  jmp     short loc_1800032CF
0x1800032ad  xor     ebx, ebx
0x1800032af  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800032b3  mov     rdi, [rsp+22F8h+var_2158]
0x1800032bb  mov     r12, qword ptr [rsp+22F8h+Data]
0x1800032c0  mov     rax, [rsp+22F8h+var_22A8]
0x1800032c5  mov     [rsp+22F8h+var_22C0], rax
0x1800032ca  mov     r13, [rsp+22F8h+var_2298]
0x1800032cf  test    rdi, rdi
0x1800032d2  jz      loc_1800033A0
0x1800032d8  lea     r14, [rsp+22F8h+String1]
0x1800032e0  cmp     [rsp+22F8h+String1], bx
0x1800032e8  jz      short loc_180003337
0x1800032ea  mov     r15d, 30h ; '0'
0x1800032f0  mov     rcx, r14; lpsz
0x1800032f3  call    cs:__imp_CharNextW
0x1800032fa  nop     dword ptr [rax+rax+00h]
0x1800032ff  movzx   ecx, word ptr [r14]
0x180003303  cmp     cx, 5Ch ; '\'
0x180003307  jnz     short loc_180003326
0x180003309  cmp     [rax], r15w
0x18000330d  jnz     short loc_180003326
0x18000330f  mov     [rdi], bx
0x180003312  mov     rcx, rax; lpsz
0x180003315  call    cs:__imp_CharNextW
0x18000331c  nop     dword ptr [rax+rax+00h]
0x180003321  mov     r14, rax
0x180003324  jmp     short loc_18000332D
0x180003326  mov     [rdi], cx
0x180003329  add     r14, 2
0x18000332d  add     rdi, 2
0x180003331  cmp     [r14], bx
0x180003335  jnz     short loc_1800032F0
0x180003337  mov     dword ptr [rdi], 0
0x18000333d  mov     r8, [rsp+22F8h+var_2158]
0x180003345  test    r8, r8
0x180003348  jz      loc_1800036DA
0x18000334e  mov     r10d, ebx
0x180003351  mov     r9, r8
0x180003354  mov     rcx, rsi
0x180003357  inc     rcx
0x18000335a  cmp     [r9+rcx*2], bx
0x18000335f  jnz     short loc_180003357
0x180003361  inc     ecx
0x180003363  lea     r9, [r9+rcx*2]
0x180003367  lea     r10d, [r10+rcx*2]
0x18000336b  cmp     ecx, 1
0x18000336e  jnz     short loc_180003354
0x180003370  mov     [rsp+22F8h+cbData], r10d; cbData
0x180003375  mov     [rsp+22F8h+lpData], r8; lpData
0x18000337a  lea     r9d, [rcx+6]; dwType
0x18000337e  xor     r8d, r8d; Reserved
0x180003381  mov     rdx, r13; lpValueName
0x180003384  mov     rcx, [r12]; hKey
0x180003388  call    cs:__imp_RegSetValueExW
0x18000338f  nop     dword ptr [rax+rax+00h]
0x180003394  mov     esi, eax
0x180003396  mov     rdi, [rsp+22F8h+var_2158]
0x18000339e  jmp     short loc_1800033A5
0x1800033a0  mov     esi, 0Eh
0x1800033a5  lea     rax, [rsp+22F8h+var_2150]
0x1800033ad  cmp     rdi, rax
0x1800033b0  jz      short loc_1800033BF
0x1800033b2  lea     rcx, [rsp+22F8h+var_2158]
0x1800033ba  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800033bf  mov     r15, [rsp+22F8h+var_22C0]
0x1800033c4  test    esi, esi
0x1800033c6  jz      loc_18000369C
0x1800033cc  mov     ecx, esi; unsigned int
0x1800033ce  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800033d3  jmp     loc_180003199
0x1800033d8  mov     [rsp+22F8h+pulOut], ebx
0x1800033dc  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x1800033e1  xor     r8d, r8d; dwFlags
0x1800033e4  xor     edx, edx; lcid
0x1800033e6  lea     rcx, [rsp+22F8h+String1]; strIn
0x1800033ee  call    cs:__imp_VarUI4FromStr
0x1800033f5  nop     dword ptr [rax+rax+00h]
0x1800033fa  test    eax, eax
0x1800033fc  js      loc_180003199
0x180003402  mov     eax, [rsp+22F8h+pulOut]
0x180003406  mov     dword ptr [rsp+22F8h+Data], eax
0x18000340a  mov     [rsp+22F8h+cbData], 4; cbData
0x180003412  lea     rax, [rsp+22F8h+Data]
0x180003417  mov     r9d, 4; dwType
0x18000341d  mov     [rsp+22F8h+lpData], rax; lpData
0x180003422  xor     r8d, r8d; Reserved
0x180003425  mov     rdx, r14; lpValueName
0x180003428  mov     rcx, [r12]; hKey
0x18000342c  call    cs:__imp_RegSetValueExW
0x180003433  nop     dword ptr [rax+rax+00h]
0x180003438  mov     esi, eax
0x18000343a  jmp     short loc_1800033C4
0x18000343c  lea     rax, [rsp+22F8h+String1]
0x180003444  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003448  mov     r14, rsi
0x18000344b  inc     r14
0x18000344e  cmp     [rax+r14*2], bx
0x180003453  jnz     short loc_18000344B
0x180003455  mov     dword ptr [rsp+22F8h+Data], r14d
0x18000345a  test    r14b, 1
0x18000345e  jnz     loc_180003518
0x180003464  mov     eax, r14d
0x180003467  cdq
0x180003468  sub     eax, edx
0x18000346a  sar     eax, 1
0x18000346c  movsxd  r12, eax
0x18000346f  mov     [rsp+22F8h+var_2268], rbx
0x180003477  mov     rdi, r12
0x18000347a  mov     [rsp+22F8h+var_2280], r12
0x18000347f  test    eax, eax
0x180003481  jz      short loc_1800034B8
0x180003483  xor     edx, edx
0x180003485  mov     rax, rsi
0x180003488  div     rdi
0x18000348b  cmp     rax, 1
0x18000348f  jb      loc_1800036E5
0x180003495  cmp     rdi, 100h
0x18000349c  jbe     short loc_1800034B8
0x18000349e  mov     rdx, rdi
0x1800034a1  lea     rcx, [rsp+22F8h+var_2268]
0x1800034a9  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800034ae  mov     rcx, [rsp+22F8h+var_2268]
0x1800034b6  jmp     short loc_1800034C8
0x1800034b8  lea     rcx, [rsp+22F8h+var_2260]
0x1800034c0  mov     [rsp+22F8h+var_2268], rcx
0x1800034c8  mov     rsi, [rsp+22F8h+var_2288]
0x1800034cd  jmp     short loc_180003506
0x1800034cf  xor     ebx, ebx
0x1800034d1  lea     r13d, [rbx+8]
0x1800034d5  mov     r14d, dword ptr [rsp+22F8h+Data]
0x1800034da  mov     rcx, [rsp+22F8h+var_2268]; void *
0x1800034e2  mov     rdi, [rsp+22F8h+var_2280]
0x1800034e7  mov     rax, [rsp+22F8h+var_22A8]
0x1800034ec  mov     [rsp+22F8h+var_22C0], rax
0x1800034f1  mov     rsi, [rsp+22F8h+var_2278]
0x1800034f9  mov     rax, [rsp+22F8h+var_2298]
0x1800034fe  mov     [rsp+22F8h+lpValueName], rax
0x180003503  mov     r12d, edi
0x180003506  test    rcx, rcx
0x180003509  jnz     short loc_180003522
0x18000350b  lea     rcx, [rsp+22F8h+var_2268]
0x180003513  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180003518  mov     eax, 80004005h
0x18000351d  jmp     loc_180003199
0x180003522  mov     r8, rdi; Size
0x180003525  xor     edx, edx; Val
0x180003527  call    memset_0
0x18000352c  mov     r10d, ebx
0x18000352f  test    r14d, r14d
0x180003532  jle     loc_180003610
0x180003538  mov     r15d, 30h ; '0'
0x18000353e  mov     eax, r10d
0x180003541  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180003549  cmp     edx, 61h ; 'a'
0x18000354c  ja      short loc_1800035BB
0x18000354e  jz      loc_1800035DB
0x180003554  cmp     edx, 38h ; '8'
0x180003557  ja      short loc_18000358D
0x180003559  jz      short loc_180003585
0x18000355b  mov     ecx, edx
0x18000355d  sub     ecx, r15d
0x180003560  jz      short loc_180003585
0x180003562  sub     ecx, 1
0x180003565  jz      short loc_180003585
0x180003567  sub     ecx, 1
0x18000356a  jz      short loc_180003585
0x18000356c  sub     ecx, 1
0x18000356f  jz      short loc_180003585
0x180003571  sub     ecx, 1
0x180003574  jz      short loc_180003585
0x180003576  sub     ecx, 1
0x180003579  jz      short loc_180003585
0x18000357b  sub     ecx, 1
0x18000357e  jz      short loc_180003585
0x180003580  cmp     ecx, 1
0x180003583  jnz     short loc_1800035D6
0x180003585  mov     r9d, edx
0x180003588  sub     r9d, r15d
0x18000358b  jmp     short loc_1800035DF
0x18000358d  mov     r9d, edx
0x180003590  mov     ecx, edx
0x180003592  sub     ecx, 39h ; '9'
0x180003595  jz      short loc_180003585
0x180003597  sub     ecx, r13d
0x18000359a  jz      short loc_1800035B5
0x18000359c  sub     ecx, 1
0x18000359f  jz      short loc_1800035B5
0x1800035a1  sub     ecx, 1
0x1800035a4  jz      short loc_1800035B5
0x1800035a6  sub     ecx, 1
0x1800035a9  jz      short loc_1800035B5
  ... truncated ...
```
