# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180002d44`
- end: `0x180003240`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1276`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800049dc`

## callees

- `0x180002d44`
- `0x180003248`
- `0x1800034a8`
- `0x18000397c`
- `0x180003e24`
- `0x180004060`
- `0x180006002`
- `0x180006030`
- `0x1800060c0`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x180002fad`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180002fad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002f6a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002fe3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003185`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002f6a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002fe3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003185`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002e0d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002edd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002ef9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002e0d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002edd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002ef9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180002dbd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180002dbd`

## pseudocode

```c
HRESULT __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v5; // r15
  const WCHAR *v6; // r14
  HRESULT result; // eax
  int v9; // ebx
  __int16 v10; // bx
  __int64 v11; // rax
  unsigned __int64 v12; // rcx
  BYTE *v13; // rbx
  WCHAR *v14; // rsi
  const WCHAR *v15; // rax
  DWORD cbData; // r10d
  BYTE *v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rcx
  LSTATUS v20; // eax
  LSTATUS v21; // edi
  LSTATUS v22; // eax
  __int64 v23; // rsi
  size_t v24; // rbx
  BYTE *v25; // rcx
  int v26; // r10d
  unsigned int v27; // r9d
  char v28; // r9
  unsigned __int64 v29; // r8
  char v30; // r9
  __int64 v31; // rdi
  int Token; // eax
  int v33; // ecx
  ULONG pulOut[2]; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE *v36; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v37[264]; // [rsp+48h] [rbp-B8h] BYREF
  BYTE *lpData; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v39[264]; // [rsp+158h] [rbp+58h] BYREF
  OLECHAR String1[4096]; // [rsp+260h] [rbp+160h] BYREF

  *(_QWORD *)Data = a4;
  *(_QWORD *)pulOut = a3;
  v5 = a4;
  v6 = a3;
  result = ATL::CRegParser::NextToken(this, String1);
  if ( result < 0 )
    return result;
  v9 = 0;
  while ( lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
  {
    if ( (unsigned int)++v9 >= 4 )
      return -2147352567;
  }
  v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
  while ( **(_WORD **)this == 9 || **(_WORD **)this == 10 || **(_WORD **)this == 13 || **(_WORD **)this == 32 )
    *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
  result = ATL::CRegParser::NextToken(this, String1);
  if ( result < 0 )
    return result;
  if ( v10 == 8 )
  {
    v31 = -1;
    do
      ++v31;
    while ( String1[v31] );
    v22 = RegSetValueExW(*a2, v6, 0, 1u, (const BYTE *)String1, 2 * v31 + 2);
    goto LABEL_43;
  }
  if ( v10 == 17 )
  {
    v23 = -1;
    do
      ++v23;
    while ( String1[v23] );
    if ( (v23 & 1) != 0 )
      return -2147467259;
    v36 = 0;
    v24 = (int)v23 / 2;
    if ( !((int)v23 / 2) )
      goto LABEL_51;
    if ( !(0xFFFFFFFFFFFFFFFFuLL / v24) )
      ATL::AtlThrowImpl(-2147024809);
    if ( v24 > 0x100 )
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v36, v24);
      v25 = v36;
    }
    else
    {
LABEL_51:
      v25 = v37;
      v36 = v37;
    }
    if ( !v25 )
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v36);
      return -2147467259;
    }
    memset_0(v25, 0, v24);
    v26 = 0;
    if ( (int)v23 <= 0 )
      goto LABEL_83;
    while ( 1 )
    {
      v27 = String1[v26];
      if ( v27 > 0x61 )
      {
        if ( v27 == 98 || v27 == 99 || v27 == 100 || v27 - 101 < 2 )
        {
LABEL_80:
          v28 = v27 - 87;
          goto LABEL_81;
        }
LABEL_79:
        v28 = 0;
        goto LABEL_81;
      }
      if ( v27 == 97 )
        goto LABEL_80;
      if ( v27 <= 0x38 )
        break;
      if ( v27 == 57 )
        goto LABEL_67;
      if ( v27 != 65 && v27 != 66 && v27 != 67 && v27 != 68 && v27 - 69 > 1 )
        goto LABEL_79;
      v28 = v27 - 55;
LABEL_81:
      v29 = (unsigned __int64)(unsigned int)v26 >> 1;
      v30 = v28 << (4 - 4 * (v26++ & 1));
      v36[v29] |= v30;
      if ( v26 >= (int)v23 )
      {
        v6 = *(const WCHAR **)pulOut;
LABEL_83:
        v21 = RegSetValueExW(*a2, v6, 0, 3u, v36, (int)v23 / 2);
        if ( v36 != v37 )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v36);
        v5 = *(unsigned __int16 **)Data;
LABEL_86:
        if ( v21 )
          return ATL::AtlHresultFromWin32(v21);
LABEL_91:
        Token = ATL::CRegParser::NextToken(this, v5);
        v33 = 0;
        if ( Token < 0 )
          return Token;
        return v33;
      }
    }
    if ( v27 != 56 && v27 != 48 && v27 != 49 && v27 != 50 && v27 != 51 && v27 != 52 && v27 != 53 && v27 - 54 > 1 )
      goto LABEL_79;
LABEL_67:
    v28 = v27 - 48;
    goto LABEL_81;
  }
  if ( v10 != 19 )
  {
    if ( v10 == 16392 )
    {
      lpData = 0;
      v11 = -1;
      do
        ++v11;
      while ( String1[v11] );
      v12 = (int)v11 + 2;
      if ( (_DWORD)v11 == -2 )
        goto LABEL_23;
      if ( 0xFFFFFFFFFFFFFFFFuLL / v12 < 2 )
        ATL::AtlThrowImpl(-2147024809);
      if ( 2 * v12 <= 0x100 )
      {
LABEL_23:
        v13 = v39;
        lpData = v39;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, 2 * v12);
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
          v6 = *(const WCHAR **)pulOut;
          v5 = *(unsigned __int16 **)Data;
        }
        *(_DWORD *)v13 = 0;
        if ( !lpData )
          ATL::AtlThrowImpl(-2147467259);
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
        v20 = RegSetValueExW(*a2, v6, 0, 7u, lpData, cbData);
        v13 = lpData;
        v21 = v20;
      }
      else
      {
        v21 = 14;
      }
      if ( v13 != v39 )
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&lpData);
      goto LABEL_86;
    }
    goto LABEL_91;
  }
  pulOut[0] = 0;
  result = VarUI4FromStr(String1, 0, 0, pulOut);
  if ( result >= 0 )
  {
    *(_DWORD *)Data = pulOut[0];
    v22 = RegSetValueExW(*a2, v6, 0, 4u, Data, 4u);
LABEL_43:
    v21 = v22;
    goto LABEL_86;
  }
  return result;
}

```

## disassembly

```asm
0x180002d44  push    rbp
0x180002d46  push    rbx
0x180002d47  push    rsi
0x180002d48  push    rdi
0x180002d49  push    r12
0x180002d4b  push    r13
0x180002d4d  push    r14
0x180002d4f  push    r15
0x180002d51  lea     rbp, [rsp-2178h]
0x180002d59  mov     eax, 2278h
0x180002d5e  call    _alloca_probe
0x180002d63  sub     rsp, rax
0x180002d66  mov     rax, cs:__security_cookie
0x180002d6d  xor     rax, rsp
0x180002d70  mov     [rbp+21B0h+var_50], rax
0x180002d77  mov     r13, rdx
0x180002d7a  mov     qword ptr [rsp+22B0h+Data], r9
0x180002d7f  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x180002d86  mov     qword ptr [rsp+22B0h+pulOut], r8
0x180002d8b  mov     r15, r9
0x180002d8e  mov     r14, r8
0x180002d91  mov     r12, rcx
0x180002d94  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180002d99  xor     esi, esi
0x180002d9b  test    eax, eax
0x180002d9d  js      loc_1800031FC
0x180002da3  mov     ebx, esi
0x180002da5  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180002dac  movsxd  rdi, ebx
0x180002daf  lea     rcx, [rbp+21B0h+String1]; lpString1
0x180002db6  add     rdi, rdi
0x180002db9  mov     rdx, [rax+rdi*8]; lpString2
0x180002dbd  call    cs:__imp_lstrcmpiW
0x180002dc3  test    eax, eax
0x180002dc5  jz      short loc_180002DDF
0x180002dc7  inc     ebx
0x180002dc9  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180002dd0  cmp     ebx, 4
0x180002dd3  jb      short loc_180002DAC
0x180002dd5  mov     eax, 80020009h
0x180002dda  jmp     loc_1800031FC
0x180002ddf  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180002de6  movzx   ebx, word ptr [rbx+rdi*8+8]
0x180002deb  mov     edi, 13h
0x180002df0  mov     rdx, [r12]
0x180002df4  movzx   ecx, word ptr [rdx]
0x180002df7  sub     ecx, 9
0x180002dfa  jz      short loc_180002E0A
0x180002dfc  sub     ecx, 1
0x180002dff  jz      short loc_180002E0A
0x180002e01  sub     ecx, 3
0x180002e04  jz      short loc_180002E0A
0x180002e06  cmp     ecx, edi
0x180002e08  jnz     short loc_180002E19
0x180002e0a  mov     rcx, rdx; lpsz
0x180002e0d  call    cs:__imp_CharNextW
0x180002e13  mov     [r12], rax
0x180002e17  jmp     short loc_180002DF0
0x180002e19  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x180002e20  mov     rcx, r12; this
0x180002e23  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180002e28  test    eax, eax
0x180002e2a  js      loc_1800031FC
0x180002e30  mov     eax, 8
0x180002e35  cmp     bx, ax
0x180002e38  jz      loc_1800031B7
0x180002e3e  cmp     bx, 11h
0x180002e42  jz      loc_180002FF0
0x180002e48  cmp     bx, di
0x180002e4b  jz      loc_180002F98
0x180002e51  mov     eax, 4008h
0x180002e56  cmp     bx, ax
0x180002e59  jnz     loc_1800031E8
0x180002e5f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180002e63  mov     [rbp+21B0h+var_2160], rsi
0x180002e67  mov     rax, rdi
0x180002e6a  lea     rcx, [rbp+21B0h+String1]
0x180002e71  inc     rax
0x180002e74  cmp     [rcx+rax*2], si
0x180002e78  jnz     short loc_180002E71
0x180002e7a  add     eax, 2
0x180002e7d  movsxd  rcx, eax
0x180002e80  jz      short loc_180002EB0
0x180002e82  xor     edx, edx
0x180002e84  mov     rax, rdi
0x180002e87  div     rcx
0x180002e8a  cmp     rax, 2
0x180002e8e  jb      loc_18000322A
0x180002e94  lea     rdx, [rcx+rcx]
0x180002e98  cmp     rdx, 100h
0x180002e9f  jbe     short loc_180002EB0
0x180002ea1  lea     rcx, [rbp+21B0h+var_2160]
0x180002ea5  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180002eaa  mov     rbx, [rbp+21B0h+var_2160]
0x180002eae  jmp     short loc_180002EB8
0x180002eb0  lea     rbx, [rbp+21B0h+var_2158]
0x180002eb4  mov     [rbp+21B0h+var_2160], rbx
0x180002eb8  test    rbx, rbx
0x180002ebb  jz      loc_180002F78
0x180002ec1  xor     eax, eax
0x180002ec3  lea     rsi, [rbp+21B0h+String1]
0x180002eca  cmp     [rbp+21B0h+String1], ax
0x180002ed1  jz      short loc_180002F1F
0x180002ed3  lea     r14d, [rax+30h]
0x180002ed7  xor     r15d, r15d
0x180002eda  mov     rcx, rsi; lpsz
0x180002edd  call    cs:__imp_CharNextW
0x180002ee3  movzx   ecx, word ptr [rsi]
0x180002ee6  cmp     cx, 5Ch ; '\'
0x180002eea  jnz     short loc_180002F04
0x180002eec  cmp     [rax], r14w
0x180002ef0  jnz     short loc_180002F04
0x180002ef2  mov     rcx, rax; lpsz
0x180002ef5  mov     [rbx], r15w
0x180002ef9  call    cs:__imp_CharNextW
0x180002eff  mov     rsi, rax
0x180002f02  jmp     short loc_180002F0B
0x180002f04  mov     [rbx], cx
0x180002f07  add     rsi, 2
0x180002f0b  add     rbx, 2
0x180002f0f  cmp     [rsi], r15w
0x180002f13  jnz     short loc_180002EDA
0x180002f15  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x180002f1a  mov     r15, qword ptr [rsp+22B0h+Data]
0x180002f1f  xor     esi, esi
0x180002f21  mov     [rbx], esi
0x180002f23  mov     r8, [rbp+21B0h+var_2160]
0x180002f27  test    r8, r8
0x180002f2a  jz      loc_180003235
0x180002f30  mov     r10d, esi
0x180002f33  mov     r9, r8
0x180002f36  mov     rcx, rdi
0x180002f39  inc     rcx
0x180002f3c  cmp     [r9+rcx*2], si
0x180002f41  jnz     short loc_180002F39
0x180002f43  inc     ecx
0x180002f45  lea     r9, [r9+rcx*2]
0x180002f49  lea     r10d, [r10+rcx*2]
0x180002f4d  cmp     ecx, 1
0x180002f50  jnz     short loc_180002F36
0x180002f52  mov     [rsp+22B0h+cbData], r10d; cbData
0x180002f57  lea     r9d, [rcx+6]; dwType
0x180002f5b  mov     rcx, [r13+0]; hKey
0x180002f5f  mov     rdx, r14; lpValueName
0x180002f62  mov     [rsp+22B0h+lpData], r8; lpData
0x180002f67  xor     r8d, r8d; Reserved
0x180002f6a  call    cs:__imp_RegSetValueExW
0x180002f70  mov     rbx, [rbp+21B0h+var_2160]
0x180002f74  mov     edi, eax
0x180002f76  jmp     short loc_180002F7D
0x180002f78  mov     edi, 0Eh
0x180002f7d  lea     rax, [rbp+21B0h+var_2158]
0x180002f81  cmp     rbx, rax
0x180002f84  jz      loc_1800031AA
0x180002f8a  lea     rcx, [rbp+21B0h+var_2160]
0x180002f8e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180002f93  jmp     loc_1800031AA
0x180002f98  lea     r9, [rsp+22B0h+pulOut]; pulOut
0x180002f9d  mov     [rsp+22B0h+pulOut], esi
0x180002fa1  xor     r8d, r8d; dwFlags
0x180002fa4  lea     rcx, [rbp+21B0h+String1]; strIn
0x180002fab  xor     edx, edx; lcid
0x180002fad  call    cs:__imp_VarUI4FromStr
0x180002fb3  test    eax, eax
0x180002fb5  js      loc_1800031FC
0x180002fbb  mov     eax, [rsp+22B0h+pulOut]
0x180002fbf  mov     ecx, 4
0x180002fc4  mov     dword ptr [rsp+22B0h+Data], eax
0x180002fc8  mov     r9d, ecx; dwType
0x180002fcb  mov     [rsp+22B0h+cbData], ecx; cbData
0x180002fcf  lea     rax, [rsp+22B0h+Data]
0x180002fd4  mov     rcx, [r13+0]; hKey
0x180002fd8  xor     r8d, r8d; Reserved
0x180002fdb  mov     rdx, r14; lpValueName
0x180002fde  mov     [rsp+22B0h+lpData], rax; lpData
0x180002fe3  call    cs:__imp_RegSetValueExW
0x180002fe9  mov     edi, eax
0x180002feb  jmp     loc_1800031AA
0x180002ff0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180002ff4  lea     rax, [rbp+21B0h+String1]
0x180002ffb  mov     rsi, rdi
0x180002ffe  xor     ecx, ecx
0x180003000  inc     rsi
0x180003003  cmp     [rax+rsi*2], cx
0x180003007  jnz     short loc_180003000
0x180003009  test    sil, 1
0x18000300d  jnz     short loc_18000306D
0x18000300f  mov     eax, esi
0x180003011  mov     [rsp+22B0h+var_2270], rcx
0x180003016  cdq
0x180003017  sub     eax, edx
0x180003019  sar     eax, 1
0x18000301b  movsxd  r15, eax
0x18000301e  mov     rbx, r15
0x180003021  jz      short loc_180003052
0x180003023  xor     edx, edx
0x180003025  mov     rax, rdi
0x180003028  div     rbx
0x18000302b  cmp     rax, 1
0x18000302f  jb      loc_18000321F
0x180003035  cmp     rbx, 100h
0x18000303c  jbe     short loc_180003052
0x18000303e  mov     rdx, rbx
0x180003041  lea     rcx, [rsp+22B0h+var_2270]
0x180003046  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000304b  mov     rcx, [rsp+22B0h+var_2270]
0x180003050  jmp     short loc_18000305C
0x180003052  lea     rcx, [rsp+22B0h+var_2268]; void *
0x180003057  mov     [rsp+22B0h+var_2270], rcx
0x18000305c  xor     edi, edi
0x18000305e  test    rcx, rcx
0x180003061  jnz     short loc_180003077
0x180003063  lea     rcx, [rsp+22B0h+var_2270]
0x180003068  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000306d  mov     eax, 80004005h
0x180003072  jmp     loc_1800031FC
0x180003077  mov     r8, rbx; Size
0x18000307a  xor     edx, edx; Val
0x18000307c  call    memset_0
0x180003081  mov     r10d, edi
0x180003084  test    esi, esi
0x180003086  jle     loc_180003166
0x18000308c  mov     r14d, 30h ; '0'
0x180003092  mov     eax, r10d
0x180003095  movzx   r9d, [rbp+rax*2+21B0h+String1]
0x18000309e  cmp     r9d, 61h ; 'a'
0x1800030a2  ja      short loc_18000310E
0x1800030a4  jz      loc_18000312F
0x1800030aa  cmp     r9d, 38h ; '8'
0x1800030ae  ja      short loc_1800030E2
0x1800030b0  jz      short loc_1800030DD
0x1800030b2  mov     ecx, r9d
0x1800030b5  sub     ecx, r14d
0x1800030b8  jz      short loc_1800030DD
0x1800030ba  sub     ecx, 1
0x1800030bd  jz      short loc_1800030DD
0x1800030bf  sub     ecx, 1
0x1800030c2  jz      short loc_1800030DD
0x1800030c4  sub     ecx, 1
0x1800030c7  jz      short loc_1800030DD
0x1800030c9  sub     ecx, 1
0x1800030cc  jz      short loc_1800030DD
0x1800030ce  sub     ecx, 1
0x1800030d1  jz      short loc_1800030DD
0x1800030d3  sub     ecx, 1
0x1800030d6  jz      short loc_1800030DD
0x1800030d8  cmp     ecx, 1
0x1800030db  jnz     short loc_18000312A
0x1800030dd  sub     r9b, r14b
0x1800030e0  jmp     short loc_180003133
0x1800030e2  mov     ecx, r9d
0x1800030e5  sub     ecx, 39h ; '9'
0x1800030e8  jz      short loc_1800030DD
0x1800030ea  sub     ecx, 8
0x1800030ed  jz      short loc_180003108
0x1800030ef  sub     ecx, 1
0x1800030f2  jz      short loc_180003108
0x1800030f4  sub     ecx, 1
0x1800030f7  jz      short loc_180003108
0x1800030f9  sub     ecx, 1
0x1800030fc  jz      short loc_180003108
0x1800030fe  sub     ecx, 1
0x180003101  jz      short loc_180003108
0x180003103  cmp     ecx, 1
0x180003106  jnz     short loc_18000312A
0x180003108  sub     r9b, 37h ; '7'
0x18000310c  jmp     short loc_180003133
0x18000310e  mov     ecx, r9d
0x180003111  sub     ecx, 62h ; 'b'
0x180003114  jz      short loc_18000312F
0x180003116  sub     ecx, 1
0x180003119  jz      short loc_18000312F
0x18000311b  sub     ecx, 1
0x18000311e  jz      short loc_18000312F
0x180003120  sub     ecx, 1
0x180003123  jz      short loc_18000312F
0x180003125  cmp     ecx, 1
0x180003128  jz      short loc_18000312F
0x18000312a  mov     r9b, dil
0x18000312d  jmp     short loc_180003133
0x18000312f  sub     r9b, 57h ; 'W'
0x180003133  mov     rdx, [rsp+22B0h+var_2270]
0x180003138  mov     eax, r10d
0x18000313b  and     eax, 1
0x18000313e  mov     r8d, r10d
0x180003141  shl     eax, 2
0x180003144  mov     ecx, 4
0x180003149  shr     r8, 1
0x18000314c  sub     ecx, eax
0x18000314e  shl     r9b, cl
0x180003151  inc     r10d
0x180003154  or      [r8+rdx], r9b
0x180003158  cmp     r10d, esi
0x18000315b  jl      loc_180003092
0x180003161  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x180003166  mov     rax, [rsp+22B0h+var_2270]
0x18000316b  mov     r9d, 3; dwType
0x180003171  mov     rcx, [r13+0]; hKey
0x180003175  xor     r8d, r8d; Reserved
0x180003178  mov     [rsp+22B0h+cbData], r15d; cbData
  ... truncated ...
```
