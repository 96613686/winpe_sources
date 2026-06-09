# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1400025a4`
- end: `0x140002aa0`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1276`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1400042ec`

## callees

- `0x140001d83`
- `0x1400025a4`
- `0x140002aa8`
- `0x140002bfc`
- `0x140002c14`
- `0x1400030d4`
- `0x140003910`
- `0x1400065f0`
- `0x140006680`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1400027ca`
- `ADVAPI32!RegSetValueExW` at `0x140002843`
- `ADVAPI32!RegSetValueExW` at `0x1400029e5`
- `ADVAPI32!RegSetValueExW` at `0x1400027ca`
- `ADVAPI32!RegSetValueExW` at `0x140002843`
- `ADVAPI32!RegSetValueExW` at `0x1400029e5`
- `KERNEL32!lstrcmpiW` at `0x14000261d`
- `KERNEL32!lstrcmpiW` at `0x14000261d`
- `USER32!CharNextW` at `0x14000266d`
- `USER32!CharNextW` at `0x14000273d`
- `USER32!CharNextW` at `0x140002759`
- `USER32!CharNextW` at `0x14000266d`
- `USER32!CharNextW` at `0x14000273d`
- `USER32!CharNextW` at `0x140002759`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x14000280d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x14000280d`

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
0x1400025a4  push    rbp
0x1400025a6  push    rbx
0x1400025a7  push    rsi
0x1400025a8  push    rdi
0x1400025a9  push    r12
0x1400025ab  push    r13
0x1400025ad  push    r14
0x1400025af  push    r15
0x1400025b1  lea     rbp, [rsp-2178h]
0x1400025b9  mov     eax, 2278h
0x1400025be  call    _alloca_probe
0x1400025c3  sub     rsp, rax
0x1400025c6  mov     rax, cs:__security_cookie
0x1400025cd  xor     rax, rsp
0x1400025d0  mov     [rbp+21B0h+var_50], rax
0x1400025d7  mov     r13, rdx
0x1400025da  mov     qword ptr [rsp+22B0h+Data], r9
0x1400025df  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x1400025e6  mov     qword ptr [rsp+22B0h+pulOut], r8
0x1400025eb  mov     r15, r9
0x1400025ee  mov     r14, r8
0x1400025f1  mov     r12, rcx
0x1400025f4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400025f9  xor     esi, esi
0x1400025fb  test    eax, eax
0x1400025fd  js      loc_140002A5C
0x140002603  mov     ebx, esi
0x140002605  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x14000260c  movsxd  rdi, ebx
0x14000260f  lea     rcx, [rbp+21B0h+String1]; lpString1
0x140002616  add     rdi, rdi
0x140002619  mov     rdx, [rax+rdi*8]; lpString2
0x14000261d  call    cs:__imp_lstrcmpiW
0x140002623  test    eax, eax
0x140002625  jz      short loc_14000263F
0x140002627  inc     ebx
0x140002629  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x140002630  cmp     ebx, 4
0x140002633  jb      short loc_14000260C
0x140002635  mov     eax, 80020009h
0x14000263a  jmp     loc_140002A5C
0x14000263f  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x140002646  movzx   ebx, word ptr [rbx+rdi*8+8]
0x14000264b  mov     edi, 13h
0x140002650  mov     rdx, [r12]
0x140002654  movzx   ecx, word ptr [rdx]
0x140002657  sub     ecx, 9
0x14000265a  jz      short loc_14000266A
0x14000265c  sub     ecx, 1
0x14000265f  jz      short loc_14000266A
0x140002661  sub     ecx, 3
0x140002664  jz      short loc_14000266A
0x140002666  cmp     ecx, edi
0x140002668  jnz     short loc_140002679
0x14000266a  mov     rcx, rdx; lpsz
0x14000266d  call    cs:__imp_CharNextW
0x140002673  mov     [r12], rax
0x140002677  jmp     short loc_140002650
0x140002679  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x140002680  mov     rcx, r12; this
0x140002683  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140002688  test    eax, eax
0x14000268a  js      loc_140002A5C
0x140002690  mov     eax, 8
0x140002695  cmp     bx, ax
0x140002698  jz      loc_140002A17
0x14000269e  cmp     bx, 11h
0x1400026a2  jz      loc_140002850
0x1400026a8  cmp     bx, di
0x1400026ab  jz      loc_1400027F8
0x1400026b1  mov     eax, 4008h
0x1400026b6  cmp     bx, ax
0x1400026b9  jnz     loc_140002A48
0x1400026bf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400026c3  mov     [rbp+21B0h+var_2160], rsi
0x1400026c7  mov     rax, rdi
0x1400026ca  lea     rcx, [rbp+21B0h+String1]
0x1400026d1  inc     rax
0x1400026d4  cmp     [rcx+rax*2], si
0x1400026d8  jnz     short loc_1400026D1
0x1400026da  add     eax, 2
0x1400026dd  movsxd  rcx, eax
0x1400026e0  jz      short loc_140002710
0x1400026e2  xor     edx, edx
0x1400026e4  mov     rax, rdi
0x1400026e7  div     rcx
0x1400026ea  cmp     rax, 2
0x1400026ee  jb      loc_140002A8A
0x1400026f4  lea     rdx, [rcx+rcx]
0x1400026f8  cmp     rdx, 100h
0x1400026ff  jbe     short loc_140002710
0x140002701  lea     rcx, [rbp+21B0h+var_2160]
0x140002705  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x14000270a  mov     rbx, [rbp+21B0h+var_2160]
0x14000270e  jmp     short loc_140002718
0x140002710  lea     rbx, [rbp+21B0h+var_2158]
0x140002714  mov     [rbp+21B0h+var_2160], rbx
0x140002718  test    rbx, rbx
0x14000271b  jz      loc_1400027D8
0x140002721  xor     eax, eax
0x140002723  lea     rsi, [rbp+21B0h+String1]
0x14000272a  cmp     [rbp+21B0h+String1], ax
0x140002731  jz      short loc_14000277F
0x140002733  lea     r14d, [rax+30h]
0x140002737  xor     r15d, r15d
0x14000273a  mov     rcx, rsi; lpsz
0x14000273d  call    cs:__imp_CharNextW
0x140002743  movzx   ecx, word ptr [rsi]
0x140002746  cmp     cx, 5Ch ; '\'
0x14000274a  jnz     short loc_140002764
0x14000274c  cmp     [rax], r14w
0x140002750  jnz     short loc_140002764
0x140002752  mov     rcx, rax; lpsz
0x140002755  mov     [rbx], r15w
0x140002759  call    cs:__imp_CharNextW
0x14000275f  mov     rsi, rax
0x140002762  jmp     short loc_14000276B
0x140002764  mov     [rbx], cx
0x140002767  add     rsi, 2
0x14000276b  add     rbx, 2
0x14000276f  cmp     [rsi], r15w
0x140002773  jnz     short loc_14000273A
0x140002775  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x14000277a  mov     r15, qword ptr [rsp+22B0h+Data]
0x14000277f  xor     esi, esi
0x140002781  mov     [rbx], esi
0x140002783  mov     r8, [rbp+21B0h+var_2160]
0x140002787  test    r8, r8
0x14000278a  jz      loc_140002A95
0x140002790  mov     r10d, esi
0x140002793  mov     r9, r8
0x140002796  mov     rcx, rdi
0x140002799  inc     rcx
0x14000279c  cmp     [r9+rcx*2], si
0x1400027a1  jnz     short loc_140002799
0x1400027a3  inc     ecx
0x1400027a5  lea     r9, [r9+rcx*2]
0x1400027a9  lea     r10d, [r10+rcx*2]
0x1400027ad  cmp     ecx, 1
0x1400027b0  jnz     short loc_140002796
0x1400027b2  mov     [rsp+22B0h+cbData], r10d; cbData
0x1400027b7  lea     r9d, [rcx+6]; dwType
0x1400027bb  mov     rcx, [r13+0]; hKey
0x1400027bf  mov     rdx, r14; lpValueName
0x1400027c2  mov     [rsp+22B0h+lpData], r8; lpData
0x1400027c7  xor     r8d, r8d; Reserved
0x1400027ca  call    cs:__imp_RegSetValueExW
0x1400027d0  mov     rbx, [rbp+21B0h+var_2160]
0x1400027d4  mov     edi, eax
0x1400027d6  jmp     short loc_1400027DD
0x1400027d8  mov     edi, 0Eh
0x1400027dd  lea     rax, [rbp+21B0h+var_2158]
0x1400027e1  cmp     rbx, rax
0x1400027e4  jz      loc_140002A0A
0x1400027ea  lea     rcx, [rbp+21B0h+var_2160]
0x1400027ee  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1400027f3  jmp     loc_140002A0A
0x1400027f8  lea     r9, [rsp+22B0h+pulOut]; pulOut
0x1400027fd  mov     [rsp+22B0h+pulOut], esi
0x140002801  xor     r8d, r8d; dwFlags
0x140002804  lea     rcx, [rbp+21B0h+String1]; strIn
0x14000280b  xor     edx, edx; lcid
0x14000280d  call    cs:__imp_VarUI4FromStr
0x140002813  test    eax, eax
0x140002815  js      loc_140002A5C
0x14000281b  mov     eax, [rsp+22B0h+pulOut]
0x14000281f  mov     ecx, 4
0x140002824  mov     dword ptr [rsp+22B0h+Data], eax
0x140002828  mov     r9d, ecx; dwType
0x14000282b  mov     [rsp+22B0h+cbData], ecx; cbData
0x14000282f  lea     rax, [rsp+22B0h+Data]
0x140002834  mov     rcx, [r13+0]; hKey
0x140002838  xor     r8d, r8d; Reserved
0x14000283b  mov     rdx, r14; lpValueName
0x14000283e  mov     [rsp+22B0h+lpData], rax; lpData
0x140002843  call    cs:__imp_RegSetValueExW
0x140002849  mov     edi, eax
0x14000284b  jmp     loc_140002A0A
0x140002850  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140002854  lea     rax, [rbp+21B0h+String1]
0x14000285b  mov     rsi, rdi
0x14000285e  xor     ecx, ecx
0x140002860  inc     rsi
0x140002863  cmp     [rax+rsi*2], cx
0x140002867  jnz     short loc_140002860
0x140002869  test    sil, 1
0x14000286d  jnz     short loc_1400028CD
0x14000286f  mov     eax, esi
0x140002871  mov     [rsp+22B0h+var_2270], rcx
0x140002876  cdq
0x140002877  sub     eax, edx
0x140002879  sar     eax, 1
0x14000287b  movsxd  r15, eax
0x14000287e  mov     rbx, r15
0x140002881  jz      short loc_1400028B2
0x140002883  xor     edx, edx
0x140002885  mov     rax, rdi
0x140002888  div     rbx
0x14000288b  cmp     rax, 1
0x14000288f  jb      loc_140002A7F
0x140002895  cmp     rbx, 100h
0x14000289c  jbe     short loc_1400028B2
0x14000289e  mov     rdx, rbx
0x1400028a1  lea     rcx, [rsp+22B0h+var_2270]
0x1400028a6  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1400028ab  mov     rcx, [rsp+22B0h+var_2270]
0x1400028b0  jmp     short loc_1400028BC
0x1400028b2  lea     rcx, [rsp+22B0h+var_2268]; void *
0x1400028b7  mov     [rsp+22B0h+var_2270], rcx
0x1400028bc  xor     edi, edi
0x1400028be  test    rcx, rcx
0x1400028c1  jnz     short loc_1400028D7
0x1400028c3  lea     rcx, [rsp+22B0h+var_2270]
0x1400028c8  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1400028cd  mov     eax, 80004005h
0x1400028d2  jmp     loc_140002A5C
0x1400028d7  mov     r8, rbx; Size
0x1400028da  xor     edx, edx; Val
0x1400028dc  call    memset_0
0x1400028e1  mov     r10d, edi
0x1400028e4  test    esi, esi
0x1400028e6  jle     loc_1400029C6
0x1400028ec  mov     r14d, 30h ; '0'
0x1400028f2  mov     eax, r10d
0x1400028f5  movzx   r9d, [rbp+rax*2+21B0h+String1]
0x1400028fe  cmp     r9d, 61h ; 'a'
0x140002902  ja      short loc_14000296E
0x140002904  jz      loc_14000298F
0x14000290a  cmp     r9d, 38h ; '8'
0x14000290e  ja      short loc_140002942
0x140002910  jz      short loc_14000293D
0x140002912  mov     ecx, r9d
0x140002915  sub     ecx, r14d
0x140002918  jz      short loc_14000293D
0x14000291a  sub     ecx, 1
0x14000291d  jz      short loc_14000293D
0x14000291f  sub     ecx, 1
0x140002922  jz      short loc_14000293D
0x140002924  sub     ecx, 1
0x140002927  jz      short loc_14000293D
0x140002929  sub     ecx, 1
0x14000292c  jz      short loc_14000293D
0x14000292e  sub     ecx, 1
0x140002931  jz      short loc_14000293D
0x140002933  sub     ecx, 1
0x140002936  jz      short loc_14000293D
0x140002938  cmp     ecx, 1
0x14000293b  jnz     short loc_14000298A
0x14000293d  sub     r9b, r14b
0x140002940  jmp     short loc_140002993
0x140002942  mov     ecx, r9d
0x140002945  sub     ecx, 39h ; '9'
0x140002948  jz      short loc_14000293D
0x14000294a  sub     ecx, 8
0x14000294d  jz      short loc_140002968
0x14000294f  sub     ecx, 1
0x140002952  jz      short loc_140002968
0x140002954  sub     ecx, 1
0x140002957  jz      short loc_140002968
0x140002959  sub     ecx, 1
0x14000295c  jz      short loc_140002968
0x14000295e  sub     ecx, 1
0x140002961  jz      short loc_140002968
0x140002963  cmp     ecx, 1
0x140002966  jnz     short loc_14000298A
0x140002968  sub     r9b, 37h ; '7'
0x14000296c  jmp     short loc_140002993
0x14000296e  mov     ecx, r9d
0x140002971  sub     ecx, 62h ; 'b'
0x140002974  jz      short loc_14000298F
0x140002976  sub     ecx, 1
0x140002979  jz      short loc_14000298F
0x14000297b  sub     ecx, 1
0x14000297e  jz      short loc_14000298F
0x140002980  sub     ecx, 1
0x140002983  jz      short loc_14000298F
0x140002985  cmp     ecx, 1
0x140002988  jz      short loc_14000298F
0x14000298a  mov     r9b, dil
0x14000298d  jmp     short loc_140002993
0x14000298f  sub     r9b, 57h ; 'W'
0x140002993  mov     rdx, [rsp+22B0h+var_2270]
0x140002998  mov     eax, r10d
0x14000299b  and     eax, 1
0x14000299e  mov     r8d, r10d
0x1400029a1  shl     eax, 2
0x1400029a4  mov     ecx, 4
0x1400029a9  shr     r8, 1
0x1400029ac  sub     ecx, eax
0x1400029ae  shl     r9b, cl
0x1400029b1  inc     r10d
0x1400029b4  or      [r8+rdx], r9b
0x1400029b8  cmp     r10d, esi
0x1400029bb  jl      loc_1400028F2
0x1400029c1  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x1400029c6  mov     rax, [rsp+22B0h+var_2270]
0x1400029cb  mov     r9d, 3; dwType
0x1400029d1  mov     rcx, [r13+0]; hKey
0x1400029d5  xor     r8d, r8d; Reserved
0x1400029d8  mov     [rsp+22B0h+cbData], r15d; cbData
  ... truncated ...
```
