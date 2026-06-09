# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180013670`
- end: `0x180013911`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `673`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001441c`

## callees

- `0x180008de0`
- `0x18000e784`
- `0x1800108c0`
- `0x180010aa0`
- `0x18001328c`
- `0x180013670`
- `0x180015134`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800137bc`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800137bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800137da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800137da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001382f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001382f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001374c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180013879`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180013895`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001374c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180013879`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180013895`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180013801`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180013801`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013718`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800138d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013718`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800138d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800136f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800136f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
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
  int v17; // eax
  __int64 v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // r12
  __int64 v20; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  int v24; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v26; // rcx
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
0x180013670  mov     [rsp-8+arg_8], rbx
0x180013675  push    rbp
0x180013676  push    rsi
0x180013677  push    rdi
0x180013678  push    r12
0x18001367a  push    r13
0x18001367c  push    r14
0x18001367e  push    r15
0x180013680  lea     rbp, [rsp-27h]
0x180013685  sub     rsp, 90h
0x18001368c  mov     rax, cs:__security_cookie
0x180013693  xor     rax, rsp
0x180013696  mov     [rbp+57h+var_40], rax
0x18001369a  mov     r15, r8
0x18001369d  mov     rbx, rdx
0x1800136a0  mov     rdi, rcx
0x1800136a3  xor     r13d, r13d
0x1800136a6  test    rdx, rdx
0x1800136a9  jz      loc_1800138E4
0x1800136af  test    r8, r8
0x1800136b2  jz      loc_1800138E4
0x1800136b8  mov     [r8], r13
0x1800136bb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800136bf  inc     rax
0x1800136c2  cmp     [rdx+rax*2], r13w
0x1800136c7  jnz     short loc_1800136BF
0x1800136c9  add     eax, eax
0x1800136cb  mov     ecx, 3E8h
0x1800136d0  cmp     eax, 64h ; 'd'
0x1800136d3  cmovl   eax, ecx
0x1800136d6  mov     [rbp+57h+var_A0], r13d
0x1800136da  mov     [rbp+57h+var_9C], eax
0x1800136dd  mov     ecx, eax
0x1800136df  add     rcx, rcx
0x1800136e2  mov     eax, 0FFFFFFFFh
0x1800136e7  cmp     rcx, rax
0x1800136ea  jbe     short loc_1800136F5
0x1800136ec  mov     rax, r13
0x1800136ef  mov     [rbp+57h+pv], r13
0x1800136f3  jmp     short loc_180013710
0x1800136f5  mov     ecx, ecx; cb
0x1800136f7  call    cs:__imp_CoTaskMemAlloc
0x1800136fe  nop     dword ptr [rax+rax+00h]
0x180013703  mov     [rbp+57h+pv], rax
0x180013707  test    rax, rax
0x18001370a  jz      short loc_180013710
0x18001370c  mov     [rax], r13w
0x180013710  test    rax, rax
0x180013713  jnz     short loc_18001372E
0x180013715  mov     rcx, rax; pv
0x180013718  call    cs:__imp_CoTaskMemFree
0x18001371f  nop     dword ptr [rax+rax+00h]
0x180013724  mov     eax, 8007000Eh
0x180013729  jmp     loc_1800138E9
0x18001372e  mov     [rdi], rbx
0x180013731  mov     esi, 25h ; '%'
0x180013736  cmp     [rbx], r13w
0x18001373a  jz      loc_1800138C2
0x180013740  cmp     [rbx], si
0x180013743  jnz     loc_1800138AC
0x180013749  mov     rcx, rbx; lpsz
0x18001374c  call    cs:__imp_CharNextW
0x180013753  nop     dword ptr [rax+rax+00h]
0x180013758  mov     [rdi], rax
0x18001375b  cmp     [rax], si
0x18001375e  jnz     short loc_180013784
0x180013760  mov     rdx, rax; unsigned __int16 *
0x180013763  mov     r8d, 1; int
0x180013769  lea     rcx, [rbp+57h+var_A0]; this
0x18001376d  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180013772  test    eax, eax
0x180013774  jnz     loc_180013892
0x18001377a  mov     ebx, 8007000Eh
0x18001377f  jmp     loc_1800138D0
0x180013784  mov     edx, esi; unsigned __int16
0x180013786  mov     rcx, rax; lpsz
0x180013789  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001378e  mov     rsi, rax
0x180013791  test    rax, rax
0x180013794  jz      loc_1800138BB
0x18001379a  mov     rcx, rax
0x18001379d  sub     rcx, [rdi]
0x1800137a0  sar     rcx, 1
0x1800137a3  cmp     rcx, 1Fh
0x1800137a7  jg      loc_1800138B4
0x1800137ad  movsxd  r9, ecx
0x1800137b0  mov     r8, [rdi]
0x1800137b3  mov     edx, 20h ; ' '
0x1800137b8  lea     rcx, [rbp+57h+String2]
0x1800137bc  call    cs:__imp__o_wcsncpy_s
0x1800137c3  nop     dword ptr [rax+rax+00h]
0x1800137c8  mov     ecx, eax; int
0x1800137ca  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800137cf  mov     rbx, [rdi+8]
0x1800137d3  lea     r12, [rbx+20h]
0x1800137d7  mov     rcx, r12; lpCriticalSection
0x1800137da  call    cs:__imp_EnterCriticalSection
0x1800137e1  nop     dword ptr [rax+rax+00h]
0x1800137e6  lea     r14, [rbx+8]
0x1800137ea  mov     ebx, r13d
0x1800137ed  cmp     ebx, [r14+10h]
0x1800137f1  jge     short loc_180013829
0x1800137f3  movsxd  rax, ebx
0x1800137f6  mov     rcx, [r14]
0x1800137f9  lea     rdx, [rbp+57h+String2]; lpString2
0x1800137fd  mov     rcx, [rcx+rax*8]; lpString1
0x180013801  call    cs:__imp_lstrcmpiW
0x180013808  nop     dword ptr [rax+rax+00h]
0x18001380d  test    eax, eax
0x18001380f  jz      short loc_180013815
0x180013811  inc     ebx
0x180013813  jmp     short loc_1800137ED
0x180013815  cmp     ebx, 0FFFFFFFFh
0x180013818  jz      short loc_180013829
0x18001381a  mov     edx, ebx
0x18001381c  mov     rcx, r14
0x18001381f  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180013824  mov     rbx, [rax]
0x180013827  jmp     short loc_18001382C
0x180013829  mov     rbx, r13
0x18001382c  mov     rcx, r12; lpCriticalSection
0x18001382f  call    cs:__imp_LeaveCriticalSection
0x180013836  nop     dword ptr [rax+rax+00h]
0x18001383b  test    rbx, rbx
0x18001383e  jz      short loc_1800138BB
0x180013840  mov     [rbp+57h+var_90], r13
0x180013844  or      r8, 0FFFFFFFFFFFFFFFFh
0x180013848  inc     r8; int
0x18001384b  cmp     [rbx+r8*2], r13w
0x180013850  jnz     short loc_180013848
0x180013852  mov     rdx, rbx; unsigned __int16 *
0x180013855  lea     rcx, [rbp+57h+var_A0]; this
0x180013859  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18001385e  mov     ebx, eax
0x180013860  lea     rcx, [rbp+57h+var_90]
0x180013864  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180013869  test    ebx, ebx
0x18001386b  jz      loc_18001377A
0x180013871  mov     rax, [rdi]
0x180013874  jmp     short loc_180013888
0x180013876  mov     rcx, rax; lpsz
0x180013879  call    cs:__imp_CharNextW
0x180013880  nop     dword ptr [rax+rax+00h]
0x180013885  mov     [rdi], rax
0x180013888  cmp     rax, rsi
0x18001388b  jnz     short loc_180013876
0x18001388d  mov     esi, 25h ; '%'
0x180013892  mov     rcx, [rdi]; lpsz
0x180013895  call    cs:__imp_CharNextW
0x18001389c  nop     dword ptr [rax+rax+00h]
0x1800138a1  mov     rbx, rax
0x1800138a4  mov     [rdi], rax
0x1800138a7  jmp     loc_180013736
0x1800138ac  mov     rdx, rbx
0x1800138af  jmp     loc_180013763
0x1800138b4  mov     ebx, 80004005h
0x1800138b9  jmp     short loc_1800138D0
0x1800138bb  mov     ebx, 80020009h
0x1800138c0  jmp     short loc_1800138D0
0x1800138c2  mov     ebx, r13d
0x1800138c5  mov     rcx, [rbp+57h+pv]
0x1800138c9  mov     [rbp+57h+pv], r13
0x1800138cd  mov     [r15], rcx
0x1800138d0  mov     rcx, [rbp+57h+pv]; pv
0x1800138d4  call    cs:__imp_CoTaskMemFree
0x1800138db  nop     dword ptr [rax+rax+00h]
0x1800138e0  mov     eax, ebx
0x1800138e2  jmp     short loc_1800138E9
0x1800138e4  mov     eax, 80004003h
0x1800138e9  mov     rcx, [rbp+57h+var_40]
0x1800138ed  xor     rcx, rsp; StackCookie
0x1800138f0  call    __security_check_cookie
0x1800138f5  mov     rbx, [rsp+0C0h+arg_8]
0x1800138fd  add     rsp, 90h
0x180013904  pop     r15
0x180013906  pop     r14
0x180013908  pop     r13
0x18001390a  pop     r12
0x18001390c  pop     rdi
0x18001390d  pop     rsi
0x18001390e  pop     rbp
0x18001390f  retn
```
