# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000615c`
- end: `0x180006761`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1541`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180009108`

## callees

- `0x18000615c`
- `0x180006768`
- `0x1800068d4`
- `0x1800068ec`
- `0x1800070b4`
- `0x180008514`
- `0x180013686`
- `0x1800136b0`
- `0x180013770`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x1800061ed`
- `KERNEL32!lstrcmpiW` at `0x1800061ed`
- `USER32!CharNextW` at `0x180006363`
- `USER32!CharNextW` at `0x180006385`
- `USER32!CharNextW` at `0x18000672b`
- `USER32!CharNextW` at `0x180006363`
- `USER32!CharNextW` at `0x180006385`
- `USER32!CharNextW` at `0x18000672b`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000645e`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000645e`
- `ADVAPI32!RegSetValueExW` at `0x1800063f8`
- `ADVAPI32!RegSetValueExW` at `0x18000649c`
- `ADVAPI32!RegSetValueExW` at `0x1800066a3`
- `ADVAPI32!RegSetValueExW` at `0x1800063f8`
- `ADVAPI32!RegSetValueExW` at `0x18000649c`
- `ADVAPI32!RegSetValueExW` at `0x1800066a3`

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
0x18000615c  push    rbx
0x18000615e  push    rsi
0x18000615f  push    rdi
0x180006160  push    r12
0x180006162  push    r13
0x180006164  push    r14
0x180006166  push    r15
0x180006168  mov     eax, 22C0h
0x18000616d  call    _alloca_probe
0x180006172  sub     rsp, rax
0x180006175  mov     rax, cs:__security_cookie
0x18000617c  xor     rax, rsp
0x18000617f  mov     [rsp+22F8h+var_48], rax
0x180006187  mov     r14, r8
0x18000618a  mov     [rsp+22F8h+lpValueName], r8
0x18000618f  mov     r12, rdx
0x180006192  mov     [rsp+22F8h+var_2288], rdx
0x180006197  mov     r15, rcx
0x18000619a  mov     [rsp+22F8h+var_22C0], rcx
0x18000619f  mov     qword ptr [rsp+22F8h+Data], rdx
0x1800061a4  mov     [rsp+22F8h+var_22A8], rcx
0x1800061a9  mov     [rsp+22F8h+var_2278], rdx
0x1800061b1  mov     [rsp+22F8h+var_2298], r8
0x1800061b6  mov     [rsp+22F8h+var_2270], r9
0x1800061be  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1800061c6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800061cb  xor     ebx, ebx
0x1800061cd  test    eax, eax
0x1800061cf  js      short loc_180006209
0x1800061d1  mov     edi, ebx
0x1800061d3  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800061da  movsxd  rsi, edi
0x1800061dd  add     rsi, rsi
0x1800061e0  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800061e5  lea     rcx, [rsp+22F8h+String1]; lpString1
0x1800061ed  call    cs:__imp_lstrcmpiW
0x1800061f4  nop     dword ptr [rax+rax+00h]
0x1800061f9  test    eax, eax
0x1800061fb  jz      short loc_18000622D
0x1800061fd  inc     edi
0x1800061ff  cmp     edi, 4
0x180006202  jb      short loc_1800061DA
0x180006204  mov     eax, 80020009h
0x180006209  mov     rcx, [rsp+22F8h+var_48]
0x180006211  xor     rcx, rsp; StackCookie
0x180006214  call    __security_check_cookie
0x180006219  add     rsp, 22C0h
0x180006220  pop     r15
0x180006222  pop     r14
0x180006224  pop     r13
0x180006226  pop     r12
0x180006228  pop     rdi
0x180006229  pop     rsi
0x18000622a  pop     rbx
0x18000622b  retn
0x18000622d  movzx   edi, word ptr [r13+rsi*8+8]
0x180006233  mov     esi, 13h
0x180006238  mov     rdx, [r15]
0x18000623b  movzx   ecx, word ptr [rdx]
0x18000623e  sub     ecx, 9
0x180006241  jz      loc_180006728
0x180006247  sub     ecx, 1
0x18000624a  jz      loc_180006728
0x180006250  sub     ecx, 3
0x180006253  jz      loc_180006728
0x180006259  cmp     ecx, esi
0x18000625b  jz      loc_180006728
0x180006261  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180006269  mov     rcx, r15; this
0x18000626c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006271  test    eax, eax
0x180006273  js      short loc_180006209
0x180006275  mov     r13d, 8
0x18000627b  cmp     di, r13w
0x18000627f  jz      loc_1800066D9
0x180006285  cmp     di, 11h
0x180006289  jz      loc_1800064AC
0x18000628f  cmp     di, si
0x180006292  jz      loc_180006448
0x180006298  mov     eax, 4008h
0x18000629d  cmp     di, ax
0x1800062a0  jnz     loc_18000670C
0x1800062a6  lea     rcx, [rsp+22F8h+String1]
0x1800062ae  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800062b2  mov     rax, rsi
0x1800062b5  inc     rax
0x1800062b8  cmp     [rcx+rax*2], bx
0x1800062bc  jnz     short loc_1800062B5
0x1800062be  add     eax, 2
0x1800062c1  mov     [rsp+22F8h+var_2158], rbx
0x1800062c9  test    eax, eax
0x1800062cb  jz      short loc_180006306
0x1800062cd  movsxd  rcx, eax
0x1800062d0  xor     edx, edx
0x1800062d2  mov     rax, rsi
0x1800062d5  div     rcx
0x1800062d8  cmp     rax, 2
0x1800062dc  jb      loc_18000673F
0x1800062e2  lea     rdx, [rcx+rcx]
0x1800062e6  cmp     rdx, 100h
0x1800062ed  jbe     short loc_180006306
0x1800062ef  lea     rcx, [rsp+22F8h+var_2158]
0x1800062f7  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800062fc  mov     rdi, [rsp+22F8h+var_2158]
0x180006304  jmp     short loc_180006316
0x180006306  lea     rdi, [rsp+22F8h+var_2150]
0x18000630e  mov     [rsp+22F8h+var_2158], rdi
0x180006316  mov     r13, [rsp+22F8h+lpValueName]
0x18000631b  jmp     short loc_18000633F
0x18000631d  xor     ebx, ebx
0x18000631f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006323  mov     rdi, [rsp+22F8h+var_2158]
0x18000632b  mov     r12, qword ptr [rsp+22F8h+Data]
0x180006330  mov     rax, [rsp+22F8h+var_22A8]
0x180006335  mov     [rsp+22F8h+var_22C0], rax
0x18000633a  mov     r13, [rsp+22F8h+var_2298]
0x18000633f  test    rdi, rdi
0x180006342  jz      loc_180006410
0x180006348  lea     r14, [rsp+22F8h+String1]
0x180006350  cmp     [rsp+22F8h+String1], bx
0x180006358  jz      short loc_1800063A7
0x18000635a  mov     r15d, 30h ; '0'
0x180006360  mov     rcx, r14; lpsz
0x180006363  call    cs:__imp_CharNextW
0x18000636a  nop     dword ptr [rax+rax+00h]
0x18000636f  movzx   ecx, word ptr [r14]
0x180006373  cmp     cx, 5Ch ; '\'
0x180006377  jnz     short loc_180006396
0x180006379  cmp     [rax], r15w
0x18000637d  jnz     short loc_180006396
0x18000637f  mov     [rdi], bx
0x180006382  mov     rcx, rax; lpsz
0x180006385  call    cs:__imp_CharNextW
0x18000638c  nop     dword ptr [rax+rax+00h]
0x180006391  mov     r14, rax
0x180006394  jmp     short loc_18000639D
0x180006396  mov     [rdi], cx
0x180006399  add     r14, 2
0x18000639d  add     rdi, 2
0x1800063a1  cmp     [r14], bx
0x1800063a5  jnz     short loc_180006360
0x1800063a7  mov     dword ptr [rdi], 0
0x1800063ad  mov     r8, [rsp+22F8h+var_2158]
0x1800063b5  test    r8, r8
0x1800063b8  jz      loc_18000674A
0x1800063be  mov     r10d, ebx
0x1800063c1  mov     r9, r8
0x1800063c4  mov     rcx, rsi
0x1800063c7  inc     rcx
0x1800063ca  cmp     [r9+rcx*2], bx
0x1800063cf  jnz     short loc_1800063C7
0x1800063d1  inc     ecx
0x1800063d3  lea     r9, [r9+rcx*2]
0x1800063d7  lea     r10d, [r10+rcx*2]
0x1800063db  cmp     ecx, 1
0x1800063de  jnz     short loc_1800063C4
0x1800063e0  mov     [rsp+22F8h+cbData], r10d; cbData
0x1800063e5  mov     [rsp+22F8h+lpData], r8; lpData
0x1800063ea  lea     r9d, [rcx+6]; dwType
0x1800063ee  xor     r8d, r8d; Reserved
0x1800063f1  mov     rdx, r13; lpValueName
0x1800063f4  mov     rcx, [r12]; hKey
0x1800063f8  call    cs:__imp_RegSetValueExW
0x1800063ff  nop     dword ptr [rax+rax+00h]
0x180006404  mov     esi, eax
0x180006406  mov     rdi, [rsp+22F8h+var_2158]
0x18000640e  jmp     short loc_180006415
0x180006410  mov     esi, 0Eh
0x180006415  lea     rax, [rsp+22F8h+var_2150]
0x18000641d  cmp     rdi, rax
0x180006420  jz      short loc_18000642F
0x180006422  lea     rcx, [rsp+22F8h+var_2158]
0x18000642a  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000642f  mov     r15, [rsp+22F8h+var_22C0]
0x180006434  test    esi, esi
0x180006436  jz      loc_18000670C
0x18000643c  mov     ecx, esi; unsigned int
0x18000643e  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180006443  jmp     loc_180006209
0x180006448  mov     [rsp+22F8h+pulOut], ebx
0x18000644c  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x180006451  xor     r8d, r8d; dwFlags
0x180006454  xor     edx, edx; lcid
0x180006456  lea     rcx, [rsp+22F8h+String1]; strIn
0x18000645e  call    cs:__imp_VarUI4FromStr
0x180006465  nop     dword ptr [rax+rax+00h]
0x18000646a  test    eax, eax
0x18000646c  js      loc_180006209
0x180006472  mov     eax, [rsp+22F8h+pulOut]
0x180006476  mov     dword ptr [rsp+22F8h+Data], eax
0x18000647a  mov     [rsp+22F8h+cbData], 4; cbData
0x180006482  lea     rax, [rsp+22F8h+Data]
0x180006487  mov     r9d, 4; dwType
0x18000648d  mov     [rsp+22F8h+lpData], rax; lpData
0x180006492  xor     r8d, r8d; Reserved
0x180006495  mov     rdx, r14; lpValueName
0x180006498  mov     rcx, [r12]; hKey
0x18000649c  call    cs:__imp_RegSetValueExW
0x1800064a3  nop     dword ptr [rax+rax+00h]
0x1800064a8  mov     esi, eax
0x1800064aa  jmp     short loc_180006434
0x1800064ac  lea     rax, [rsp+22F8h+String1]
0x1800064b4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800064b8  mov     r14, rsi
0x1800064bb  inc     r14
0x1800064be  cmp     [rax+r14*2], bx
0x1800064c3  jnz     short loc_1800064BB
0x1800064c5  mov     dword ptr [rsp+22F8h+Data], r14d
0x1800064ca  test    r14b, 1
0x1800064ce  jnz     loc_180006588
0x1800064d4  mov     eax, r14d
0x1800064d7  cdq
0x1800064d8  sub     eax, edx
0x1800064da  sar     eax, 1
0x1800064dc  movsxd  r12, eax
0x1800064df  mov     [rsp+22F8h+var_2268], rbx
0x1800064e7  mov     rdi, r12
0x1800064ea  mov     [rsp+22F8h+var_2280], r12
0x1800064ef  test    eax, eax
0x1800064f1  jz      short loc_180006528
0x1800064f3  xor     edx, edx
0x1800064f5  mov     rax, rsi
0x1800064f8  div     rdi
0x1800064fb  cmp     rax, 1
0x1800064ff  jb      loc_180006755
0x180006505  cmp     rdi, 100h
0x18000650c  jbe     short loc_180006528
0x18000650e  mov     rdx, rdi
0x180006511  lea     rcx, [rsp+22F8h+var_2268]
0x180006519  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000651e  mov     rcx, [rsp+22F8h+var_2268]
0x180006526  jmp     short loc_180006538
0x180006528  lea     rcx, [rsp+22F8h+var_2260]
0x180006530  mov     [rsp+22F8h+var_2268], rcx
0x180006538  mov     rsi, [rsp+22F8h+var_2288]
0x18000653d  jmp     short loc_180006576
0x18000653f  xor     ebx, ebx
0x180006541  lea     r13d, [rbx+8]
0x180006545  mov     r14d, dword ptr [rsp+22F8h+Data]
0x18000654a  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180006552  mov     rdi, [rsp+22F8h+var_2280]
0x180006557  mov     rax, [rsp+22F8h+var_22A8]
0x18000655c  mov     [rsp+22F8h+var_22C0], rax
0x180006561  mov     rsi, [rsp+22F8h+var_2278]
0x180006569  mov     rax, [rsp+22F8h+var_2298]
0x18000656e  mov     [rsp+22F8h+lpValueName], rax
0x180006573  mov     r12d, edi
0x180006576  test    rcx, rcx
0x180006579  jnz     short loc_180006592
0x18000657b  lea     rcx, [rsp+22F8h+var_2268]
0x180006583  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180006588  mov     eax, 80004005h
0x18000658d  jmp     loc_180006209
0x180006592  mov     r8, rdi; Size
0x180006595  xor     edx, edx; Val
0x180006597  call    memset_0
0x18000659c  mov     r10d, ebx
0x18000659f  test    r14d, r14d
0x1800065a2  jle     loc_180006680
0x1800065a8  mov     r15d, 30h ; '0'
0x1800065ae  mov     eax, r10d
0x1800065b1  movzx   edx, [rsp+rax*2+22F8h+String1]
0x1800065b9  cmp     edx, 61h ; 'a'
0x1800065bc  ja      short loc_18000662B
0x1800065be  jz      loc_18000664B
0x1800065c4  cmp     edx, 38h ; '8'
0x1800065c7  ja      short loc_1800065FD
0x1800065c9  jz      short loc_1800065F5
0x1800065cb  mov     ecx, edx
0x1800065cd  sub     ecx, r15d
0x1800065d0  jz      short loc_1800065F5
0x1800065d2  sub     ecx, 1
0x1800065d5  jz      short loc_1800065F5
0x1800065d7  sub     ecx, 1
0x1800065da  jz      short loc_1800065F5
0x1800065dc  sub     ecx, 1
0x1800065df  jz      short loc_1800065F5
0x1800065e1  sub     ecx, 1
0x1800065e4  jz      short loc_1800065F5
0x1800065e6  sub     ecx, 1
0x1800065e9  jz      short loc_1800065F5
0x1800065eb  sub     ecx, 1
0x1800065ee  jz      short loc_1800065F5
0x1800065f0  cmp     ecx, 1
0x1800065f3  jnz     short loc_180006646
0x1800065f5  mov     r9d, edx
0x1800065f8  sub     r9d, r15d
0x1800065fb  jmp     short loc_18000664F
0x1800065fd  mov     r9d, edx
0x180006600  mov     ecx, edx
0x180006602  sub     ecx, 39h ; '9'
0x180006605  jz      short loc_1800065F5
0x180006607  sub     ecx, r13d
0x18000660a  jz      short loc_180006625
0x18000660c  sub     ecx, 1
0x18000660f  jz      short loc_180006625
0x180006611  sub     ecx, 1
0x180006614  jz      short loc_180006625
0x180006616  sub     ecx, 1
0x180006619  jz      short loc_180006625
  ... truncated ...
```
