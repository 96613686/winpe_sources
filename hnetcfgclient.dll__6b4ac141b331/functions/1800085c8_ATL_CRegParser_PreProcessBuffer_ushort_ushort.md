# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800085c8`
- end: `0x18000882c`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `612`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008aac`

## callees

- `0x180006688`
- `0x1800073b8`
- `0x180007594`
- `0x18000823c`
- `0x1800085c8`
- `0x18000979c`
- `0x18002d200`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180008702`
- `msvcrt!wcsncpy_s` at `0x180008702`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008763`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008763`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000871a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000871a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008698`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800087a7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800087bd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008698`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800087a7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800087bd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000873b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000873b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000864f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000864f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000866a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800087f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000866a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800087f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(const wchar_t **this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  _WORD *v9; // rax
  LPWSTR v11; // rax
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // ebx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rsi
  __int64 v16; // rcx
  errno_t v17; // eax
  const wchar_t *v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // r12
  const wchar_t *v20; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  int v24; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v26; // rcx
  _DWORD v27[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  _QWORD *v29; // [rsp+30h] [rbp-39h] BYREF
  wchar_t Destination[32]; // [rsp+40h] [rbp-29h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  if ( v7 < 100 )
    v7 = 1000;
  v27[0] = 0;
  v27[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = CoTaskMemAlloc((unsigned int)v8);
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_18:
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v12, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v11 = CharNextW(v4);
    *this = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_18;
    }
    v14 = ATL::CRegParser::StrChrW(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_39;
    v16 = v14 - *this;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_41;
    }
    v17 = wcsncpy_s(Destination, 0x20u, *this, (int)v16);
    ATL::AtlCrtErrorCheck(v17);
    v18 = this[1];
    v19 = (struct _RTL_CRITICAL_SECTION *)(v18 + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
    v20 = v18 + 4;
    for ( i = 0; (signed int)i < *((_DWORD *)v20 + 4); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v20 + 8LL * (int)i), Destination) )
      {
        if ( i != -1 )
        {
          v22 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                              v20,
                                              i);
          goto LABEL_29;
        }
        break;
      }
    }
    v22 = 0;
LABEL_29:
    LeaveCriticalSection(v19);
    if ( !v22 )
    {
LABEL_39:
      v13 = -2147352567;
      goto LABEL_41;
    }
    v29 = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v29);
    if ( !v24 )
    {
LABEL_19:
      v13 = -2147024882;
      goto LABEL_41;
    }
    for ( j = *this; j != v15; *this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*this);
    *this = v4;
  }
  v13 = 0;
  v26 = (unsigned __int16 *)pv;
  pv = 0;
  *a3 = v26;
LABEL_41:
  CoTaskMemFree(pv);
  return v13;
}

```

## disassembly

```asm
0x1800085c8  mov     [rsp-8+arg_8], rbx
0x1800085cd  push    rbp
0x1800085ce  push    rsi
0x1800085cf  push    rdi
0x1800085d0  push    r12
0x1800085d2  push    r13
0x1800085d4  push    r14
0x1800085d6  push    r15
0x1800085d8  lea     rbp, [rsp-27h]
0x1800085dd  sub     rsp, 90h
0x1800085e4  mov     rax, cs:__security_cookie
0x1800085eb  xor     rax, rsp
0x1800085ee  mov     [rbp+57h+var_40], rax
0x1800085f2  mov     r15, r8
0x1800085f5  mov     rbx, rdx
0x1800085f8  mov     rdi, rcx
0x1800085fb  xor     r13d, r13d
0x1800085fe  test    rdx, rdx
0x180008601  jz      loc_180008800
0x180008607  test    r8, r8
0x18000860a  jz      loc_180008800
0x180008610  mov     [r8], r13
0x180008613  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008617  inc     rax
0x18000861a  cmp     [rdx+rax*2], r13w
0x18000861f  jnz     short loc_180008617
0x180008621  add     eax, eax
0x180008623  mov     ecx, 3E8h
0x180008628  cmp     eax, 64h ; 'd'
0x18000862b  cmovl   eax, ecx
0x18000862e  mov     [rbp+57h+var_A0], r13d
0x180008632  mov     [rbp+57h+var_9C], eax
0x180008635  mov     ecx, eax
0x180008637  add     rcx, rcx
0x18000863a  mov     eax, 0FFFFFFFFh
0x18000863f  cmp     rcx, rax
0x180008642  jbe     short loc_18000864D
0x180008644  mov     rax, r13
0x180008647  mov     [rbp+57h+pv], r13
0x18000864b  jmp     short loc_180008662
0x18000864d  mov     ecx, ecx; cb
0x18000864f  call    cs:__imp_CoTaskMemAlloc
0x180008655  mov     [rbp+57h+pv], rax
0x180008659  test    rax, rax
0x18000865c  jz      short loc_180008662
0x18000865e  mov     [rax], r13w
0x180008662  test    rax, rax
0x180008665  jnz     short loc_18000867A
0x180008667  mov     rcx, rax; pv
0x18000866a  call    cs:__imp_CoTaskMemFree
0x180008670  mov     eax, 8007000Eh
0x180008675  jmp     loc_180008805
0x18000867a  mov     [rdi], rbx
0x18000867d  mov     esi, 25h ; '%'
0x180008682  cmp     [rbx], r13w
0x180008686  jz      loc_1800087E4
0x18000868c  cmp     [rbx], si
0x18000868f  jnz     loc_1800087CE
0x180008695  mov     rcx, rbx; lpsz
0x180008698  call    cs:__imp_CharNextW
0x18000869e  mov     [rdi], rax
0x1800086a1  cmp     [rax], si
0x1800086a4  jnz     short loc_1800086CA
0x1800086a6  mov     rdx, rax; unsigned __int16 *
0x1800086a9  mov     r8d, 1; int
0x1800086af  lea     rcx, [rbp+57h+var_A0]; this
0x1800086b3  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800086b8  test    eax, eax
0x1800086ba  jnz     loc_1800087BA
0x1800086c0  mov     ebx, 8007000Eh
0x1800086c5  jmp     loc_1800087F2
0x1800086ca  mov     edx, esi; unsigned __int16
0x1800086cc  mov     rcx, rax; lpsz
0x1800086cf  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800086d4  mov     rsi, rax
0x1800086d7  test    rax, rax
0x1800086da  jz      loc_1800087DD
0x1800086e0  mov     rcx, rax
0x1800086e3  sub     rcx, [rdi]
0x1800086e6  sar     rcx, 1
0x1800086e9  cmp     rcx, 1Fh
0x1800086ed  jg      loc_1800087D6
0x1800086f3  movsxd  r9, ecx; MaxCount
0x1800086f6  mov     r8, [rdi]; Source
0x1800086f9  mov     edx, 20h ; ' '; SizeInWords
0x1800086fe  lea     rcx, [rbp+57h+Destination]; Destination
0x180008702  call    cs:__imp_wcsncpy_s
0x180008708  mov     ecx, eax; int
0x18000870a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000870f  mov     rbx, [rdi+8]
0x180008713  lea     r12, [rbx+20h]
0x180008717  mov     rcx, r12; lpCriticalSection
0x18000871a  call    cs:__imp_EnterCriticalSection
0x180008720  lea     r14, [rbx+8]
0x180008724  mov     ebx, r13d
0x180008727  cmp     ebx, [r14+10h]
0x18000872b  jge     short loc_18000875D
0x18000872d  movsxd  rax, ebx
0x180008730  mov     rcx, [r14]
0x180008733  lea     rdx, [rbp+57h+Destination]; lpString2
0x180008737  mov     rcx, [rcx+rax*8]; lpString1
0x18000873b  call    cs:__imp_lstrcmpiW
0x180008741  test    eax, eax
0x180008743  jz      short loc_180008749
0x180008745  inc     ebx
0x180008747  jmp     short loc_180008727
0x180008749  cmp     ebx, 0FFFFFFFFh
0x18000874c  jz      short loc_18000875D
0x18000874e  mov     edx, ebx
0x180008750  mov     rcx, r14
0x180008753  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180008758  mov     rbx, [rax]
0x18000875b  jmp     short loc_180008760
0x18000875d  mov     rbx, r13
0x180008760  mov     rcx, r12; lpCriticalSection
0x180008763  call    cs:__imp_LeaveCriticalSection
0x180008769  test    rbx, rbx
0x18000876c  jz      short loc_1800087DD
0x18000876e  mov     [rbp+57h+var_90], r13
0x180008772  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008776  inc     r8; int
0x180008779  cmp     [rbx+r8*2], r13w
0x18000877e  jnz     short loc_180008776
0x180008780  mov     rdx, rbx; unsigned __int16 *
0x180008783  lea     rcx, [rbp+57h+var_A0]; this
0x180008787  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000878c  mov     ebx, eax
0x18000878e  lea     rcx, [rbp+57h+var_90]
0x180008792  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180008797  test    ebx, ebx
0x180008799  jz      loc_1800086C0
0x18000879f  mov     rax, [rdi]
0x1800087a2  jmp     short loc_1800087B0
0x1800087a4  mov     rcx, rax; lpsz
0x1800087a7  call    cs:__imp_CharNextW
0x1800087ad  mov     [rdi], rax
0x1800087b0  cmp     rax, rsi
0x1800087b3  jnz     short loc_1800087A4
0x1800087b5  mov     esi, 25h ; '%'
0x1800087ba  mov     rcx, [rdi]; lpsz
0x1800087bd  call    cs:__imp_CharNextW
0x1800087c3  mov     rbx, rax
0x1800087c6  mov     [rdi], rax
0x1800087c9  jmp     loc_180008682
0x1800087ce  mov     rdx, rbx
0x1800087d1  jmp     loc_1800086A9
0x1800087d6  mov     ebx, 80004005h
0x1800087db  jmp     short loc_1800087F2
0x1800087dd  mov     ebx, 80020009h
0x1800087e2  jmp     short loc_1800087F2
0x1800087e4  mov     ebx, r13d
0x1800087e7  mov     rcx, [rbp+57h+pv]
0x1800087eb  mov     [rbp+57h+pv], r13
0x1800087ef  mov     [r15], rcx
0x1800087f2  mov     rcx, [rbp+57h+pv]; pv
0x1800087f6  call    cs:__imp_CoTaskMemFree
0x1800087fc  mov     eax, ebx
0x1800087fe  jmp     short loc_180008805
0x180008800  mov     eax, 80004003h
0x180008805  mov     rcx, [rbp+57h+var_40]
0x180008809  xor     rcx, rsp; StackCookie
0x18000880c  call    __security_check_cookie
0x180008811  mov     rbx, [rsp+0C0h+arg_8]
0x180008819  add     rsp, 90h
0x180008820  pop     r15
0x180008822  pop     r14
0x180008824  pop     r13
0x180008826  pop     r12
0x180008828  pop     rdi
0x180008829  pop     rsi
0x18000882a  pop     rbp
0x18000882b  retn
```
