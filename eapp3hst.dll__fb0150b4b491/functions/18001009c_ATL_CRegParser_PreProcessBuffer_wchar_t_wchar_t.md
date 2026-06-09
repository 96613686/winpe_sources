# ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)

- ea: `0x18001009c`
- end: `0x180010300`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z`
- size: `612`
- prototype: `int(ATL::CRegParser *__hidden this, wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001043c`

## callees

- `0x1800017a0`
- `0x18000ee68`
- `0x18000f898`
- `0x18000fa74`
- `0x18000fdec`
- `0x18001009c`
- `0x180010e60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800101d6`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800101d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800101ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800101ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010237`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010237`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001016c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001027b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010291`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001016c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001027b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010291`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001020f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001020f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001013e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800102ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001013e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800102ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(ATL::CRegParser *this, wchar_t *a2, wchar_t **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  _WORD *v9; // rax
  LPWSTR v11; // rax
  const wchar_t *v12; // rdx
  unsigned int v13; // ebx
  wchar_t *v14; // rax
  wchar_t *v15; // rsi
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // r12
  __int64 v20; // r14
  unsigned int i; // ebx
  const wchar_t *v22; // rbx
  __int64 v23; // r8
  int v24; // ebx
  const WCHAR *j; // rax
  wchar_t *v26; // rcx
  __int64 v27; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v29; // [rsp+30h] [rbp-39h] BYREF
  WCHAR String2[32]; // [rsp+40h] [rbp-29h] BYREF

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
  LODWORD(v27) = 0;
  HIDWORD(v27) = v7;
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
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_18:
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v27, v12, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v11 = CharNextW(v4);
    *(_QWORD *)this = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_18;
    }
    v14 = ATL::CRegParser::StrChrW(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_39;
    v16 = ((__int64)v14 - *(_QWORD *)this) >> 1;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_41;
    }
    v17 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v16, v27);
    ATL::AtlCrtErrorCheck(v17);
    v18 = *((_QWORD *)this + 1);
    v19 = (struct _RTL_CRITICAL_SECTION *)(v18 + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 32));
    v20 = v18 + 8;
    for ( i = 0; (signed int)i < *(_DWORD *)(v20 + 16); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v20 + 8LL * (int)i), String2) )
      {
        if ( i != -1 )
        {
          v22 = *(const wchar_t **)ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
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
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v27, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v29);
    if ( !v24 )
    {
LABEL_19:
      v13 = -2147024882;
      goto LABEL_41;
    }
    for ( j = *(const WCHAR **)this; j != v15; *(_QWORD *)this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
  }
  v13 = 0;
  v26 = (wchar_t *)pv;
  pv = 0;
  *a3 = v26;
LABEL_41:
  CoTaskMemFree(pv);
  return v13;
}

```

## disassembly

```asm
0x18001009c  mov     [rsp-8+arg_8], rbx
0x1800100a1  push    rbp
0x1800100a2  push    rsi
0x1800100a3  push    rdi
0x1800100a4  push    r12
0x1800100a6  push    r13
0x1800100a8  push    r14
0x1800100aa  push    r15
0x1800100ac  lea     rbp, [rsp-27h]
0x1800100b1  sub     rsp, 90h
0x1800100b8  mov     rax, cs:__security_cookie
0x1800100bf  xor     rax, rsp
0x1800100c2  mov     [rbp+57h+var_40], rax
0x1800100c6  mov     r15, r8
0x1800100c9  mov     rbx, rdx
0x1800100cc  mov     rdi, rcx
0x1800100cf  xor     r13d, r13d
0x1800100d2  test    rdx, rdx
0x1800100d5  jz      loc_1800102D4
0x1800100db  test    r8, r8
0x1800100de  jz      loc_1800102D4
0x1800100e4  mov     [r8], r13
0x1800100e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800100eb  inc     rax
0x1800100ee  cmp     [rdx+rax*2], r13w
0x1800100f3  jnz     short loc_1800100EB
0x1800100f5  add     eax, eax
0x1800100f7  mov     ecx, 3E8h
0x1800100fc  cmp     eax, 64h ; 'd'
0x1800100ff  cmovl   eax, ecx
0x180010102  mov     [rbp+57h+var_A0], r13d
0x180010106  mov     [rbp+57h+var_9C], eax
0x180010109  mov     ecx, eax
0x18001010b  add     rcx, rcx
0x18001010e  mov     eax, 0FFFFFFFFh
0x180010113  cmp     rcx, rax
0x180010116  jbe     short loc_180010121
0x180010118  mov     rax, r13
0x18001011b  mov     [rbp+57h+pv], r13
0x18001011f  jmp     short loc_180010136
0x180010121  mov     ecx, ecx; cb
0x180010123  call    cs:__imp_CoTaskMemAlloc
0x180010129  mov     [rbp+57h+pv], rax
0x18001012d  test    rax, rax
0x180010130  jz      short loc_180010136
0x180010132  mov     [rax], r13w
0x180010136  test    rax, rax
0x180010139  jnz     short loc_18001014E
0x18001013b  mov     rcx, rax; pv
0x18001013e  call    cs:__imp_CoTaskMemFree
0x180010144  mov     eax, 8007000Eh
0x180010149  jmp     loc_1800102D9
0x18001014e  mov     [rdi], rbx
0x180010151  mov     esi, 25h ; '%'
0x180010156  cmp     [rbx], r13w
0x18001015a  jz      loc_1800102B8
0x180010160  cmp     [rbx], si
0x180010163  jnz     loc_1800102A2
0x180010169  mov     rcx, rbx; lpsz
0x18001016c  call    cs:__imp_CharNextW
0x180010172  mov     [rdi], rax
0x180010175  cmp     [rax], si
0x180010178  jnz     short loc_18001019E
0x18001017a  mov     rdx, rax; wchar_t *
0x18001017d  mov     r8d, 1; int
0x180010183  lea     rcx, [rbp+57h+var_A0]; this
0x180010187  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x18001018c  test    eax, eax
0x18001018e  jnz     loc_18001028E
0x180010194  mov     ebx, 8007000Eh
0x180010199  jmp     loc_1800102C6
0x18001019e  mov     edx, esi; wchar_t
0x1800101a0  mov     rcx, rax; lpsz
0x1800101a3  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x1800101a8  mov     rsi, rax
0x1800101ab  test    rax, rax
0x1800101ae  jz      loc_1800102B1
0x1800101b4  mov     rcx, rax
0x1800101b7  sub     rcx, [rdi]
0x1800101ba  sar     rcx, 1
0x1800101bd  cmp     rcx, 1Fh
0x1800101c1  jg      loc_1800102AA
0x1800101c7  movsxd  r9, ecx
0x1800101ca  mov     r8, [rdi]
0x1800101cd  mov     edx, 20h ; ' '
0x1800101d2  lea     rcx, [rbp+57h+String2]
0x1800101d6  call    cs:__imp__o_wcsncpy_s
0x1800101dc  mov     ecx, eax; int
0x1800101de  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800101e3  mov     rbx, [rdi+8]
0x1800101e7  lea     r12, [rbx+20h]
0x1800101eb  mov     rcx, r12; lpCriticalSection
0x1800101ee  call    cs:__imp_EnterCriticalSection
0x1800101f4  lea     r14, [rbx+8]
0x1800101f8  mov     ebx, r13d
0x1800101fb  cmp     ebx, [r14+10h]
0x1800101ff  jge     short loc_180010231
0x180010201  movsxd  rax, ebx
0x180010204  mov     rcx, [r14]
0x180010207  lea     rdx, [rbp+57h+String2]; lpString2
0x18001020b  mov     rcx, [rcx+rax*8]; lpString1
0x18001020f  call    cs:__imp_lstrcmpiW
0x180010215  test    eax, eax
0x180010217  jz      short loc_18001021D
0x180010219  inc     ebx
0x18001021b  jmp     short loc_1800101FB
0x18001021d  cmp     ebx, 0FFFFFFFFh
0x180010220  jz      short loc_180010231
0x180010222  mov     edx, ebx
0x180010224  mov     rcx, r14
0x180010227  call    ?GetValueAt@?$CSimpleMap@PEA_WPEA_WVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEA_WH@Z; ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18001022c  mov     rbx, [rax]
0x18001022f  jmp     short loc_180010234
0x180010231  mov     rbx, r13
0x180010234  mov     rcx, r12; lpCriticalSection
0x180010237  call    cs:__imp_LeaveCriticalSection
0x18001023d  test    rbx, rbx
0x180010240  jz      short loc_1800102B1
0x180010242  mov     [rbp+57h+var_90], r13
0x180010246  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001024a  inc     r8; int
0x18001024d  cmp     [rbx+r8*2], r13w
0x180010252  jnz     short loc_18001024A
0x180010254  mov     rdx, rbx; wchar_t *
0x180010257  lea     rcx, [rbp+57h+var_A0]; this
0x18001025b  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x180010260  mov     ebx, eax
0x180010262  lea     rcx, [rbp+57h+var_90]
0x180010266  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001026b  test    ebx, ebx
0x18001026d  jz      loc_180010194
0x180010273  mov     rax, [rdi]
0x180010276  jmp     short loc_180010284
0x180010278  mov     rcx, rax; lpsz
0x18001027b  call    cs:__imp_CharNextW
0x180010281  mov     [rdi], rax
0x180010284  cmp     rax, rsi
0x180010287  jnz     short loc_180010278
0x180010289  mov     esi, 25h ; '%'
0x18001028e  mov     rcx, [rdi]; lpsz
0x180010291  call    cs:__imp_CharNextW
0x180010297  mov     rbx, rax
0x18001029a  mov     [rdi], rax
0x18001029d  jmp     loc_180010156
0x1800102a2  mov     rdx, rbx
0x1800102a5  jmp     loc_18001017D
0x1800102aa  mov     ebx, 80004005h
0x1800102af  jmp     short loc_1800102C6
0x1800102b1  mov     ebx, 80020009h
0x1800102b6  jmp     short loc_1800102C6
0x1800102b8  mov     ebx, r13d
0x1800102bb  mov     rcx, [rbp+57h+pv]
0x1800102bf  mov     [rbp+57h+pv], r13
0x1800102c3  mov     [r15], rcx
0x1800102c6  mov     rcx, [rbp+57h+pv]; pv
0x1800102ca  call    cs:__imp_CoTaskMemFree
0x1800102d0  mov     eax, ebx
0x1800102d2  jmp     short loc_1800102D9
0x1800102d4  mov     eax, 80004003h
0x1800102d9  mov     rcx, [rbp+57h+var_40]
0x1800102dd  xor     rcx, rsp; StackCookie
0x1800102e0  call    __security_check_cookie
0x1800102e5  mov     rbx, [rsp+0C0h+arg_8]
0x1800102ed  add     rsp, 90h
0x1800102f4  pop     r15
0x1800102f6  pop     r14
0x1800102f8  pop     r13
0x1800102fa  pop     r12
0x1800102fc  pop     rdi
0x1800102fd  pop     rsi
0x1800102fe  pop     rbp
0x1800102ff  retn
```
