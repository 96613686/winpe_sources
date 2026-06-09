# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x140034c7c`
- end: `0x140035271`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1525`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140035738`

## callees

- `0x140001020`
- `0x140001040`
- `0x1400020d0`
- `0x140033ab0`
- `0x1400344ac`
- `0x1400344d0`
- `0x140034c7c`
- `0x140035584`
- `0x140035594`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140034f1e`
- `ADVAPI32!RegSetValueExW` at `0x140035181`
- `ADVAPI32!RegSetValueExW` at `0x1400351e6`
- `ADVAPI32!RegSetValueExW` at `0x140034f1e`
- `ADVAPI32!RegSetValueExW` at `0x140035181`
- `ADVAPI32!RegSetValueExW` at `0x1400351e6`
- `KERNEL32!lstrcmpiW` at `0x140034cf7`
- `KERNEL32!lstrcmpiW` at `0x140034d15`
- `KERNEL32!lstrcmpiW` at `0x140034d35`
- `KERNEL32!lstrcmpiW` at `0x140034d53`
- `KERNEL32!lstrcmpiW` at `0x140034cf7`
- `KERNEL32!lstrcmpiW` at `0x140034d15`
- `KERNEL32!lstrcmpiW` at `0x140034d35`
- `KERNEL32!lstrcmpiW` at `0x140034d53`
- `USER32!CharNextW` at `0x140034e95`
- `USER32!CharNextW` at `0x140034eb1`
- `USER32!CharNextW` at `0x14003521a`
- `USER32!CharNextW` at `0x140034e95`
- `USER32!CharNextW` at `0x140034eb1`
- `USER32!CharNextW` at `0x14003521a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x140034f6a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x140034f6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  HRESULT result; // eax
  int v8; // edi
  __int64 v9; // rax
  int v10; // eax
  BYTE *v11; // rdi
  HKEY *v12; // r12
  WCHAR *i; // r14
  const WCHAR *v14; // rax
  LSTATUS v15; // esi
  DWORD cbData; // r9d
  BYTE *v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rcx
  LSTATUS v20; // eax
  __int64 v21; // rdi
  size_t v22; // r14
  BYTE *v23; // rcx
  HKEY *v24; // rsi
  int v25; // r9d
  __int64 v26; // r8
  unsigned int v27; // edx
  char v28; // dl
  __int64 v29; // rsi
  ULONG pulOut; // [rsp+30h] [rbp-22B8h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-22B0h] BYREF
  LPCWSTR lpValueName; // [rsp+40h] [rbp-22A8h]
  HKEY *v33; // [rsp+48h] [rbp-22A0h]
  ATL::CRegParser *v34; // [rsp+50h] [rbp-2298h]
  HKEY *v35; // [rsp+58h] [rbp-2290h]
  const unsigned __int16 *v36; // [rsp+60h] [rbp-2288h]
  size_t v37; // [rsp+70h] [rbp-2278h]
  unsigned __int16 *v38; // [rsp+78h] [rbp-2270h]
  BYTE *v39; // [rsp+80h] [rbp-2268h] BYREF
  _BYTE v40[264]; // [rsp+88h] [rbp-2260h] BYREF
  BYTE *lpData; // [rsp+190h] [rbp-2158h] BYREF
  _BYTE v42[264]; // [rsp+198h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+2A0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v33 = a2;
  v34 = this;
  v35 = a2;
  v36 = a3;
  v38 = a4;
  result = ATL::CRegParser::NextToken(this, String1);
  _mm_lfence();
  if ( result >= 0 )
  {
    if ( !lstrcmpiW(String1, L"S") )
    {
      v8 = 8;
      goto LABEL_10;
    }
    if ( !lstrcmpiW(String1, L"M") )
    {
      v8 = 16392;
      goto LABEL_10;
    }
    if ( !lstrcmpiW(String1, L"D") )
    {
      v8 = 19;
      goto LABEL_10;
    }
    if ( !lstrcmpiW(String1, L"B") )
    {
      v8 = 17;
LABEL_10:
      _mm_lfence();
      while ( **(_WORD **)this == 9 || **(_WORD **)this == 10 || **(_WORD **)this == 13 || **(_WORD **)this == 32 )
        *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
      result = ATL::CRegParser::NextToken(this, String1);
      if ( result < 0 )
        goto LABEL_16;
      if ( v8 == 8 )
      {
        v29 = -1;
        do
          ++v29;
        while ( String1[v29] );
        v20 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)String1, 2 * v29 + 2);
        goto LABEL_90;
      }
      if ( v8 != 17 )
      {
        if ( v8 != 19 )
        {
          v9 = -1;
          do
            ++v9;
          while ( String1[v9] );
          v10 = v9 + 2;
          lpData = 0;
          if ( !v10 )
            goto LABEL_26;
          if ( 0xFFFFFFFFFFFFFFFFuLL / v10 < 2 )
          {
            _mm_lfence();
            ATL::AtlThrowImpl(-2147024362);
          }
          if ( (unsigned __int64)(2LL * v10) > 0x100 )
          {
            _mm_lfence();
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, 2LL * v10);
            v11 = lpData;
          }
          else
          {
LABEL_26:
            v11 = v42;
            lpData = v42;
          }
          v12 = v33;
          if ( v11 )
          {
            for ( i = String1; *i; v11 += 2 )
            {
              v14 = CharNextW(i);
              if ( *i == 92 && *v14 == 48 )
              {
                *(_WORD *)v11 = 0;
                i = CharNextW(v14);
              }
              else
              {
                *(_WORD *)v11 = *i++;
              }
            }
            *(_DWORD *)v11 = 0;
            v11 = lpData;
            if ( lpData )
            {
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
              v15 = RegSetValueExW(*v12, lpValueName, 0, 7u, lpData, cbData);
              v11 = lpData;
            }
            else
            {
              v15 = 13;
            }
          }
          else
          {
            v15 = 14;
          }
          if ( v11 != v42 )
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&lpData);
          goto LABEL_91;
        }
        result = VarUI4FromStr(String1, 0, 0, &pulOut);
        if ( result < 0 )
          goto LABEL_16;
        *(_DWORD *)Data = pulOut;
        v20 = RegSetValueExW(*a2, a3, 0, 4u, Data, 4u);
LABEL_90:
        v15 = v20;
        goto LABEL_91;
      }
      v21 = -1;
      do
        ++v21;
      while ( String1[v21] );
      *(_DWORD *)Data = v21;
      if ( (v21 & 1) != 0 )
        return -2147467259;
      pulOut = (int)v21 / 2;
      v39 = 0;
      v22 = (int)v21 / 2;
      v37 = v22;
      if ( !((int)v21 / 2) )
        goto LABEL_53;
      if ( !(0xFFFFFFFFFFFFFFFFuLL / v22) )
      {
        _mm_lfence();
        ATL::AtlThrowImpl(-2147024362);
      }
      if ( v22 > 0x100 )
      {
        _mm_lfence();
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v39, v22);
        v23 = v39;
      }
      else
      {
LABEL_53:
        v23 = v40;
        v39 = v40;
      }
      v24 = v33;
      if ( !v23 )
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v39);
        return -2147467259;
      }
      memset_0(v23, 0, v22);
      v25 = 0;
      if ( (int)v21 <= 0 )
      {
LABEL_85:
        v15 = RegSetValueExW(*v24, lpValueName, 0, 3u, v39, (int)v21 / 2);
        if ( v39 != v40 )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v39);
LABEL_91:
        if ( v15 )
          return ATL::AtlHresultFromWin32(v15);
        _mm_lfence();
        result = ATL::CRegParser::NextToken(this, v38);
        if ( result >= 0 )
          return 0;
LABEL_16:
        _mm_lfence();
        return result;
      }
      v26 = 0;
      while ( 1 )
      {
        v27 = String1[v26];
        if ( v27 > 0x61 )
        {
          if ( v27 == 98 || v27 == 99 || v27 == 100 || v27 - 101 < 2 )
          {
LABEL_83:
            v28 = v27 - 87;
            goto LABEL_84;
          }
LABEL_82:
          v28 = 0;
          goto LABEL_84;
        }
        if ( v27 == 97 )
          goto LABEL_83;
        if ( v27 <= 0x38 )
          break;
        if ( v27 == 57 )
          goto LABEL_70;
        if ( v27 != 65 && v27 != 66 && v27 != 67 && v27 != 68 && v27 - 69 > 1 )
          goto LABEL_82;
        v28 = v27 - 55;
LABEL_84:
        v39[v25 / 2] |= v28 << (4 - 4 * (v25 & 1));
        ++v25;
        if ( ++v26 >= (int)v21 )
          goto LABEL_85;
      }
      if ( v27 != 56 && v27 != 48 && v27 != 49 && v27 != 50 && v27 != 51 && v27 != 52 && v27 != 53 && v27 - 54 > 1 )
        goto LABEL_82;
LABEL_70:
      v28 = v27 - 48;
      goto LABEL_84;
    }
    return -2147352567;
  }
  return result;
}

```

## disassembly

```asm
0x140034c7c  push    rbx
0x140034c7e  push    rsi
0x140034c7f  push    rdi
0x140034c80  push    r12
0x140034c82  push    r13
0x140034c84  push    r14
0x140034c86  push    r15
0x140034c88  mov     eax, 22B0h
0x140034c8d  call    _alloca_probe
0x140034c92  sub     rsp, rax
0x140034c95  mov     rax, cs:__security_cookie
0x140034c9c  xor     rax, rsp
0x140034c9f  mov     [rsp+22E8h+var_48], rax
0x140034ca7  mov     r14, r8
0x140034caa  mov     [rsp+22E8h+lpValueName], r8
0x140034caf  mov     r15, rdx
0x140034cb2  mov     [rsp+22E8h+var_22A0], rdx
0x140034cb7  mov     r13, rcx
0x140034cba  mov     [rsp+22E8h+var_2298], rcx
0x140034cbf  mov     [rsp+22E8h+var_2290], rdx
0x140034cc4  mov     [rsp+22E8h+var_2288], r8
0x140034cc9  mov     [rsp+22E8h+var_2270], r9
0x140034cce  lea     rdx, [rsp+22E8h+String1]; unsigned __int16 *
0x140034cd6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140034cdb  xor     ebx, ebx
0x140034cdd  lfence
0x140034ce0  test    eax, eax
0x140034ce2  js      loc_14003522E
0x140034ce8  lea     rdx, aS_0; "S"
0x140034cef  lea     rcx, [rsp+22E8h+String1]; lpString1
0x140034cf7  call    cs:__imp_lstrcmpiW
0x140034cfd  test    eax, eax
0x140034cff  jnz     short loc_140034D06
0x140034d01  lea     edi, [rbx+8]
0x140034d04  jmp     short loc_140034D64
0x140034d06  lea     rdx, aM_0; "M"
0x140034d0d  lea     rcx, [rsp+22E8h+String1]; lpString1
0x140034d15  call    cs:__imp_lstrcmpiW
0x140034d1b  test    eax, eax
0x140034d1d  jnz     short loc_140034D26
0x140034d1f  mov     edi, 4008h
0x140034d24  jmp     short loc_140034D64
0x140034d26  lea     rdx, aD_0; "D"
0x140034d2d  lea     rcx, [rsp+22E8h+String1]; lpString1
0x140034d35  call    cs:__imp_lstrcmpiW
0x140034d3b  test    eax, eax
0x140034d3d  jnz     short loc_140034D44
0x140034d3f  lea     edi, [rax+13h]
0x140034d42  jmp     short loc_140034D64
0x140034d44  lea     rdx, aB; "B"
0x140034d4b  lea     rcx, [rsp+22E8h+String1]; lpString1
0x140034d53  call    cs:__imp_lstrcmpiW
0x140034d59  test    eax, eax
0x140034d5b  jnz     loc_140035229
0x140034d61  lea     edi, [rax+11h]
0x140034d64  lfence
0x140034d67  mov     rdx, [r13+0]
0x140034d6b  movzx   ecx, word ptr [rdx]
0x140034d6e  sub     ecx, 9
0x140034d71  jz      loc_140035217
0x140034d77  sub     ecx, 1
0x140034d7a  jz      loc_140035217
0x140034d80  sub     ecx, 3
0x140034d83  jz      loc_140035217
0x140034d89  cmp     ecx, 13h
0x140034d8c  jz      loc_140035217
0x140034d92  lea     rdx, [rsp+22E8h+String1]; unsigned __int16 *
0x140034d9a  mov     rcx, r13; this
0x140034d9d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140034da2  test    eax, eax
0x140034da4  jns     short loc_140034DAE
0x140034da6  lfence
0x140034da9  jmp     loc_14003522E
0x140034dae  cmp     edi, 8
0x140034db1  jz      loc_1400351AA
0x140034db7  cmp     edi, 11h
0x140034dba  jz      loc_140034F98
0x140034dc0  cmp     edi, 13h
0x140034dc3  jz      loc_140034F58
0x140034dc9  cmp     edi, 4008h
0x140034dcf  jnz     loc_1400351FB
0x140034dd5  lea     rcx, [rsp+22E8h+String1]
0x140034ddd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140034de1  mov     rax, rsi
0x140034de4  inc     rax
0x140034de7  cmp     [rcx+rax*2], bx
0x140034deb  jnz     short loc_140034DE4
0x140034ded  add     eax, 2
0x140034df0  mov     [rsp+22E8h+var_2158], rbx
0x140034df8  movsxd  rcx, eax
0x140034dfb  test    eax, eax
0x140034dfd  jz      short loc_140034E38
0x140034dff  xor     edx, edx
0x140034e01  mov     rax, rsi
0x140034e04  div     rcx
0x140034e07  cmp     rax, 2
0x140034e0b  jb      loc_140035251
0x140034e11  lea     rdx, [rcx+rcx]
0x140034e15  cmp     rdx, 100h
0x140034e1c  jbe     short loc_140034E38
0x140034e1e  lfence
0x140034e21  lea     rcx, [rsp+22E8h+var_2158]
0x140034e29  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140034e2e  mov     rdi, [rsp+22E8h+var_2158]
0x140034e36  jmp     short loc_140034E48
0x140034e38  lea     rdi, [rsp+22E8h+var_2150]
0x140034e40  mov     [rsp+22E8h+var_2158], rdi
0x140034e48  mov     r12, [rsp+22E8h+var_22A0]
0x140034e4d  jmp     short loc_140034E71
0x140034e4f  xor     ebx, ebx
0x140034e51  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140034e55  mov     rdi, [rsp+22E8h+var_2158]
0x140034e5d  mov     r13, [rsp+22E8h+var_2298]
0x140034e62  mov     r12, [rsp+22E8h+var_2290]
0x140034e67  mov     rax, [rsp+22E8h+var_2288]
0x140034e6c  mov     [rsp+22E8h+lpValueName], rax
0x140034e71  test    rdi, rdi
0x140034e74  jz      loc_140034F30
0x140034e7a  lea     r14, [rsp+22E8h+String1]
0x140034e82  cmp     [rsp+22E8h+String1], bx
0x140034e8a  jz      short loc_140034ECD
0x140034e8c  mov     r15d, 30h ; '0'
0x140034e92  mov     rcx, r14; lpsz
0x140034e95  call    cs:__imp_CharNextW
0x140034e9b  movzx   ecx, word ptr [r14]
0x140034e9f  cmp     cx, 5Ch ; '\'
0x140034ea3  jnz     short loc_140034EBC
0x140034ea5  cmp     [rax], r15w
0x140034ea9  jnz     short loc_140034EBC
0x140034eab  mov     [rdi], bx
0x140034eae  mov     rcx, rax; lpsz
0x140034eb1  call    cs:__imp_CharNextW
0x140034eb7  mov     r14, rax
0x140034eba  jmp     short loc_140034EC3
0x140034ebc  mov     [rdi], cx
0x140034ebf  add     r14, 2
0x140034ec3  add     rdi, 2
0x140034ec7  cmp     [r14], bx
0x140034ecb  jnz     short loc_140034E92
0x140034ecd  and     dword ptr [rdi], 0
0x140034ed0  mov     rdi, [rsp+22E8h+var_2158]
0x140034ed8  test    rdi, rdi
0x140034edb  jnz     short loc_140034EE2
0x140034edd  lea     esi, [rdi+0Dh]
0x140034ee0  jmp     short loc_140034F35
0x140034ee2  mov     r9d, ebx
0x140034ee5  mov     r8, rdi
0x140034ee8  mov     rcx, rsi
0x140034eeb  inc     rcx
0x140034eee  cmp     [r8+rcx*2], bx
0x140034ef3  jnz     short loc_140034EEB
0x140034ef5  inc     ecx
0x140034ef7  lea     r8, [r8+rcx*2]
0x140034efb  lea     r9d, [r9+rcx*2]
0x140034eff  cmp     ecx, 1
0x140034f02  jnz     short loc_140034EE8
0x140034f04  mov     [rsp+22E8h+cbData], r9d; cbData
0x140034f09  mov     [rsp+22E8h+lpData], rdi; lpData
0x140034f0e  lea     r9d, [rcx+6]; dwType
0x140034f12  xor     r8d, r8d; Reserved
0x140034f15  mov     rdx, [rsp+22E8h+lpValueName]; lpValueName
0x140034f1a  mov     rcx, [r12]; hKey
0x140034f1e  call    cs:__imp_RegSetValueExW
0x140034f24  mov     esi, eax
0x140034f26  mov     rdi, [rsp+22E8h+var_2158]
0x140034f2e  jmp     short loc_140034F35
0x140034f30  mov     esi, 0Eh
0x140034f35  lea     rax, [rsp+22E8h+var_2150]
0x140034f3d  cmp     rdi, rax
0x140034f40  jz      loc_1400351EE
0x140034f46  lea     rcx, [rsp+22E8h+var_2158]
0x140034f4e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x140034f53  jmp     loc_1400351EE
0x140034f58  lea     r9, [rsp+22E8h+pulOut]; pulOut
0x140034f5d  xor     r8d, r8d; dwFlags
0x140034f60  xor     edx, edx; lcid
0x140034f62  lea     rcx, [rsp+22E8h+String1]; strIn
0x140034f6a  call    cs:__imp_VarUI4FromStr
0x140034f70  test    eax, eax
0x140034f72  js      loc_140034DA6
0x140034f78  mov     eax, [rsp+22E8h+pulOut]
0x140034f7c  mov     dword ptr [rsp+22E8h+Data], eax
0x140034f80  mov     [rsp+22E8h+cbData], 4
0x140034f88  lea     rax, [rsp+22E8h+Data]
0x140034f8d  mov     r9d, 4
0x140034f93  jmp     loc_1400351D8
0x140034f98  lea     rax, [rsp+22E8h+String1]
0x140034fa0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140034fa4  mov     rdi, rsi
0x140034fa7  inc     rdi
0x140034faa  cmp     [rax+rdi*2], bx
0x140034fae  jnz     short loc_140034FA7
0x140034fb0  mov     dword ptr [rsp+22E8h+Data], edi
0x140034fb4  test    dil, 1
0x140034fb8  jnz     loc_14003506E
0x140034fbe  mov     eax, edi
0x140034fc0  cdq
0x140034fc1  sub     eax, edx
0x140034fc3  sar     eax, 1
0x140034fc5  movsxd  r12, eax
0x140034fc8  mov     [rsp+22E8h+pulOut], r12d
0x140034fcd  mov     [rsp+22E8h+var_2268], rbx
0x140034fd5  mov     r14, r12
0x140034fd8  mov     [rsp+22E8h+var_2278], r12
0x140034fdd  test    eax, eax
0x140034fdf  jz      short loc_140035019
0x140034fe1  xor     edx, edx
0x140034fe3  mov     rax, rsi
0x140034fe6  div     r14
0x140034fe9  cmp     rax, 1
0x140034fed  jb      loc_140035263
0x140034ff3  cmp     r14, 100h
0x140034ffa  jbe     short loc_140035019
0x140034ffc  lfence
0x140034fff  mov     rdx, r14
0x140035002  lea     rcx, [rsp+22E8h+var_2268]
0x14003500a  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x14003500f  mov     rcx, [rsp+22E8h+var_2268]
0x140035017  jmp     short loc_140035029
0x140035019  lea     rcx, [rsp+22E8h+var_2260]
0x140035021  mov     [rsp+22E8h+var_2268], rcx
0x140035029  mov     rsi, [rsp+22E8h+var_22A0]
0x14003502e  jmp     short loc_14003505C
0x140035030  xor     ebx, ebx
0x140035032  mov     edi, dword ptr [rsp+22E8h+Data]
0x140035036  mov     r12d, [rsp+22E8h+pulOut]
0x14003503b  mov     rcx, [rsp+22E8h+var_2268]; void *
0x140035043  mov     r14, [rsp+22E8h+var_2278]
0x140035048  mov     r13, [rsp+22E8h+var_2298]
0x14003504d  mov     rsi, [rsp+22E8h+var_2290]
0x140035052  mov     rax, [rsp+22E8h+var_2288]
0x140035057  mov     [rsp+22E8h+lpValueName], rax
0x14003505c  test    rcx, rcx
0x14003505f  jnz     short loc_140035078
0x140035061  lea     rcx, [rsp+22E8h+var_2268]
0x140035069  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x14003506e  mov     eax, 80004005h
0x140035073  jmp     loc_14003522E
0x140035078  mov     r8, r14; Size
0x14003507b  xor     edx, edx; Val
0x14003507d  call    memset_0
0x140035082  mov     r9d, ebx
0x140035085  movsxd  r11, edi
0x140035088  test    edi, edi
0x14003508a  jle     loc_14003515E
0x140035090  mov     r8, rbx
0x140035093  mov     r15d, 30h ; '0'
0x140035099  mov     eax, r9d
0x14003509c  cdq
0x14003509d  sub     eax, edx
0x14003509f  sar     eax, 1
0x1400350a1  movsxd  r10, eax
0x1400350a4  add     r10, [rsp+22E8h+var_2268]
0x1400350ac  movzx   edx, [rsp+r8*2+22E8h+String1]
0x1400350b5  mov     ecx, edx
0x1400350b7  cmp     edx, 61h ; 'a'
0x1400350ba  ja      short loc_14003511A
0x1400350bc  jz      short loc_140035137
0x1400350be  cmp     edx, 38h ; '8'
0x1400350c1  ja      short loc_1400350F2
0x1400350c3  jz      short loc_1400350ED
0x1400350c5  sub     ecx, r15d
0x1400350c8  jz      short loc_1400350ED
0x1400350ca  sub     ecx, 1
0x1400350cd  jz      short loc_1400350ED
0x1400350cf  sub     ecx, 1
0x1400350d2  jz      short loc_1400350ED
0x1400350d4  sub     ecx, 1
0x1400350d7  jz      short loc_1400350ED
0x1400350d9  sub     ecx, 1
0x1400350dc  jz      short loc_1400350ED
0x1400350de  sub     ecx, 1
0x1400350e1  jz      short loc_1400350ED
0x1400350e3  sub     ecx, 1
0x1400350e6  jz      short loc_1400350ED
0x1400350e8  cmp     ecx, 1
0x1400350eb  jnz     short loc_140035133
0x1400350ed  sub     dl, r15b
0x1400350f0  jmp     short loc_14003513A
0x1400350f2  sub     ecx, 39h ; '9'
0x1400350f5  jz      short loc_1400350ED
0x1400350f7  sub     ecx, 8
0x1400350fa  jz      short loc_140035115
0x1400350fc  sub     ecx, 1
0x1400350ff  jz      short loc_140035115
0x140035101  sub     ecx, 1
0x140035104  jz      short loc_140035115
0x140035106  sub     ecx, 1
0x140035109  jz      short loc_140035115
0x14003510b  sub     ecx, 1
0x14003510e  jz      short loc_140035115
0x140035110  cmp     ecx, 1
0x140035113  jnz     short loc_140035133
0x140035115  sub     dl, 37h ; '7'
0x140035118  jmp     short loc_14003513A
0x14003511a  sub     ecx, 62h ; 'b'
0x14003511d  jz      short loc_140035137
0x14003511f  sub     ecx, 1
0x140035122  jz      short loc_140035137
0x140035124  sub     ecx, 1
  ... truncated ...
```
