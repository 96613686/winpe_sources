# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800270cc`
- end: `0x180027317`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `587`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18002744c`

## callees

- `0x180005cec`
- `0x18002589c`
- `0x180025934`
- `0x180026228`
- `0x180026e1c`
- `0x1800270cc`
- `0x180027f10`
- `0x180081750`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800271f7`
- `msvcrt!wcsncpy_s` at `0x1800271f7`
- `USER32!CharNextW` at `0x1800271a7`
- `USER32!CharNextW` at `0x180027280`
- `USER32!CharNextW` at `0x1800272a9`
- `USER32!CharNextW` at `0x1800271a7`
- `USER32!CharNextW` at `0x180027280`
- `USER32!CharNextW` at `0x1800272a9`
- `ole32!CoTaskMemFree` at `0x180027177`
- `ole32!CoTaskMemFree` at `0x1800272e1`
- `ole32!CoTaskMemFree` at `0x180027177`
- `ole32!CoTaskMemFree` at `0x1800272e1`
- `ole32!CoTaskMemAlloc` at `0x18002715c`
- `ole32!CoTaskMemAlloc` at `0x18002715c`
- `KERNEL32!lstrcmpiW` at `0x180027224`
- `KERNEL32!lstrcmpiW` at `0x180027224`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rdx
  __int64 v7; // rdx
  _WORD *v8; // rax
  LPWSTR v10; // rax
  const unsigned __int16 *v11; // rdx
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rsi
  __int64 v14; // rcx
  errno_t v15; // eax
  LPCWSTR v16; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v18; // rdx
  __int64 v19; // r8
  int v20; // ebx
  const WCHAR *j; // rax
  unsigned int v22; // ebx
  unsigned __int16 *v23; // rcx
  SIZE_T cb; // [rsp+20h] [rbp-49h] BYREF
  _DWORD v25[2]; // [rsp+28h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-39h]
  wchar_t Destination[32]; // [rsp+40h] [rbp-29h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( v4[v6] );
  v7 = (unsigned int)(2 * v6);
  if ( (int)v7 < 100 )
    v7 = 1000;
  v25[0] = 0;
  v25[1] = v7;
  LODWORD(cb) = 0;
  if ( (int)ATL::AtlMultiply<unsigned long>(&cb, v7, 2) >= 0 )
  {
    v8 = CoTaskMemAlloc((unsigned int)cb);
    pv = v8;
    if ( v8 )
      *v8 = 0;
  }
  else
  {
    v8 = 0;
    pv = 0;
  }
  if ( !v8 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  for ( *this = v4; ; *this = v4 )
  {
    if ( !*v4 )
    {
      v22 = 0;
      v23 = (unsigned __int16 *)pv;
      pv = 0;
      *a3 = v23;
      goto LABEL_40;
    }
    if ( *v4 == 37 )
      break;
    v11 = v4;
LABEL_34:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v11, 1) )
    {
LABEL_38:
      v22 = -2147024882;
      goto LABEL_40;
    }
LABEL_35:
    v4 = CharNextW(*this);
  }
  v10 = CharNextW(v4);
  *this = v10;
  if ( *v10 == 37 )
  {
    v11 = v10;
    goto LABEL_34;
  }
  v12 = ATL::CRegParser::StrChrW(v10, 0x25u);
  v13 = v12;
  if ( v12 )
  {
    v14 = v12 - *this;
    if ( v14 > 31 )
    {
      v22 = -2147467259;
      goto LABEL_40;
    }
    v15 = wcsncpy_s(Destination, 0x20u, *this, (int)v14);
    ATL::AtlCrtErrorCheck(v15);
    v16 = this[1];
    for ( i = 0; (signed int)i < *((_DWORD *)v16 + 6); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v16 + 1) + 8LL * (int)i), Destination) )
      {
        if ( i == -1 )
          break;
        v18 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                            v16 + 4,
                                            i);
        if ( !v18 )
          break;
        cb = 0;
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        v20 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v18, v19);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&cb);
        if ( v20 )
        {
          for ( j = *this; j != v13; *this = j )
            j = CharNextW(j);
          goto LABEL_35;
        }
        goto LABEL_38;
      }
    }
  }
  v22 = -2147352567;
LABEL_40:
  CoTaskMemFree(pv);
  return v22;
}

```

## disassembly

```asm
0x1800270cc  mov     [rsp-8+arg_8], rbx
0x1800270d1  push    rbp
0x1800270d2  push    rsi
0x1800270d3  push    rdi
0x1800270d4  push    r12
0x1800270d6  push    r13
0x1800270d8  push    r14
0x1800270da  push    r15
0x1800270dc  lea     rbp, [rsp-27h]
0x1800270e1  sub     rsp, 90h
0x1800270e8  mov     rax, cs:__security_cookie
0x1800270ef  xor     rax, rsp
0x1800270f2  mov     [rbp+57h+var_40], rax
0x1800270f6  mov     r15, r8
0x1800270f9  mov     rbx, rdx
0x1800270fc  mov     rdi, rcx
0x1800270ff  xor     r12d, r12d
0x180027102  test    rdx, rdx
0x180027105  jz      loc_1800272EB
0x18002710b  test    r8, r8
0x18002710e  jz      loc_1800272EB
0x180027114  mov     [r8], r12
0x180027117  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002711b  inc     rdx
0x18002711e  cmp     [rbx+rdx*2], r12w
0x180027123  jnz     short loc_18002711B
0x180027125  add     edx, edx
0x180027127  mov     eax, 3E8h
0x18002712c  cmp     edx, 64h ; 'd'
0x18002712f  cmovl   edx, eax
0x180027132  mov     [rbp+57h+var_98], r12d
0x180027136  mov     [rbp+57h+var_94], edx
0x180027139  mov     dword ptr [rbp+57h+cb], r12d
0x18002713d  mov     r8d, 2
0x180027143  lea     rcx, [rbp+57h+cb]
0x180027147  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x18002714c  test    eax, eax
0x18002714e  jns     short loc_180027159
0x180027150  mov     rax, r12
0x180027153  mov     [rbp+57h+pv], r12
0x180027157  jmp     short loc_18002716F
0x180027159  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x18002715c  call    cs:__imp_CoTaskMemAlloc
0x180027162  mov     [rbp+57h+pv], rax
0x180027166  test    rax, rax
0x180027169  jz      short loc_18002716F
0x18002716b  mov     [rax], r12w
0x18002716f  test    rax, rax
0x180027172  jnz     short loc_180027187
0x180027174  mov     rcx, rax; pv
0x180027177  call    cs:__imp_CoTaskMemFree
0x18002717d  mov     eax, 8007000Eh
0x180027182  jmp     loc_1800272F0
0x180027187  mov     [rdi], rbx
0x18002718a  mov     r13d, 25h ; '%'
0x180027190  cmp     [rbx], r12w
0x180027194  jz      loc_1800272CF
0x18002719a  cmp     [rbx], r13w
0x18002719e  jnz     loc_180027290
0x1800271a4  mov     rcx, rbx; lpsz
0x1800271a7  call    cs:__imp_CharNextW
0x1800271ad  mov     [rdi], rax
0x1800271b0  cmp     [rax], r13w
0x1800271b4  jnz     short loc_1800271BE
0x1800271b6  mov     rdx, rax
0x1800271b9  jmp     loc_180027293
0x1800271be  mov     edx, r13d; unsigned __int16
0x1800271c1  mov     rcx, rax; lpsz
0x1800271c4  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800271c9  mov     rsi, rax
0x1800271cc  test    rax, rax
0x1800271cf  jz      loc_1800272C1
0x1800271d5  mov     rcx, rax
0x1800271d8  sub     rcx, [rdi]
0x1800271db  sar     rcx, 1
0x1800271de  cmp     rcx, 1Fh
0x1800271e2  jg      loc_1800272BA
0x1800271e8  movsxd  r9, ecx; MaxCount
0x1800271eb  mov     r8, [rdi]; Source
0x1800271ee  mov     edx, 20h ; ' '; SizeInWords
0x1800271f3  lea     rcx, [rbp+57h+Destination]; Destination
0x1800271f7  call    cs:__imp_wcsncpy_s
0x1800271fd  mov     ecx, eax; int
0x1800271ff  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180027204  mov     r14, [rdi+8]
0x180027208  mov     ebx, r12d
0x18002720b  cmp     ebx, [r14+18h]
0x18002720f  jge     loc_1800272C1
0x180027215  movsxd  rax, ebx
0x180027218  mov     rcx, [r14+8]
0x18002721c  lea     rdx, [rbp+57h+Destination]; lpString2
0x180027220  mov     rcx, [rcx+rax*8]; lpString1
0x180027224  call    cs:__imp_lstrcmpiW
0x18002722a  test    eax, eax
0x18002722c  jz      short loc_180027232
0x18002722e  inc     ebx
0x180027230  jmp     short loc_18002720B
0x180027232  cmp     ebx, 0FFFFFFFFh
0x180027235  jz      loc_1800272C1
0x18002723b  mov     edx, ebx
0x18002723d  lea     rcx, [r14+8]
0x180027241  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180027246  mov     rdx, [rax]; unsigned __int16 *
0x180027249  test    rdx, rdx
0x18002724c  jz      short loc_1800272C1
0x18002724e  mov     [rbp+57h+cb], r12
0x180027252  or      r8, 0FFFFFFFFFFFFFFFFh
0x180027256  inc     r8; int
0x180027259  cmp     [rdx+r8*2], r12w
0x18002725e  jnz     short loc_180027256
0x180027260  lea     rcx, [rbp+57h+var_98]; this
0x180027264  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180027269  mov     ebx, eax
0x18002726b  lea     rcx, [rbp+57h+cb]
0x18002726f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180027274  test    ebx, ebx
0x180027276  jz      short loc_1800272C8
0x180027278  mov     rax, [rdi]
0x18002727b  jmp     short loc_180027289
0x18002727d  mov     rcx, rax; lpsz
0x180027280  call    cs:__imp_CharNextW
0x180027286  mov     [rdi], rax
0x180027289  cmp     rax, rsi
0x18002728c  jnz     short loc_18002727D
0x18002728e  jmp     short loc_1800272A6
0x180027290  mov     rdx, rbx; unsigned __int16 *
0x180027293  mov     r8d, 1; int
0x180027299  lea     rcx, [rbp+57h+var_98]; this
0x18002729d  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800272a2  test    eax, eax
0x1800272a4  jz      short loc_1800272C8
0x1800272a6  mov     rcx, [rdi]; lpsz
0x1800272a9  call    cs:__imp_CharNextW
0x1800272af  mov     rbx, rax
0x1800272b2  mov     [rdi], rax
0x1800272b5  jmp     loc_180027190
0x1800272ba  mov     ebx, 80004005h
0x1800272bf  jmp     short loc_1800272DD
0x1800272c1  mov     ebx, 80020009h
0x1800272c6  jmp     short loc_1800272DD
0x1800272c8  mov     ebx, 8007000Eh
0x1800272cd  jmp     short loc_1800272DD
0x1800272cf  mov     ebx, r12d
0x1800272d2  mov     rcx, [rbp+57h+pv]
0x1800272d6  mov     [rbp+57h+pv], r12
0x1800272da  mov     [r15], rcx
0x1800272dd  mov     rcx, [rbp+57h+pv]; pv
0x1800272e1  call    cs:__imp_CoTaskMemFree
0x1800272e7  mov     eax, ebx
0x1800272e9  jmp     short loc_1800272F0
0x1800272eb  mov     eax, 80004003h
0x1800272f0  mov     rcx, [rbp+57h+var_40]
0x1800272f4  xor     rcx, rsp; StackCookie
0x1800272f7  call    __security_check_cookie
0x1800272fc  mov     rbx, [rsp+0C0h+arg_8]
0x180027304  add     rsp, 90h
0x18002730b  pop     r15
0x18002730d  pop     r14
0x18002730f  pop     r13
0x180027311  pop     r12
0x180027313  pop     rdi
0x180027314  pop     rsi
0x180027315  pop     rbp
0x180027316  retn
```
