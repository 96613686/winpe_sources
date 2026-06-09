# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18002468c`
- end: `0x1800248f2`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `614`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024a2c`

## callees

- `0x18001d8e0`
- `0x1800234bc`
- `0x180023f28`
- `0x180024068`
- `0x1800243fc`
- `0x18002468c`
- `0x180025458`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800247c6`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800247c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800247de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800247de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024828`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024828`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024713`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024713`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002472e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800248bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002472e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800248bc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002475c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002486d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180024883`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002475c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002486d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180024883`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180024800`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180024800`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v27, v12, 1) )
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
0x18002468c  mov     [rsp-8+arg_8], rbx
0x180024691  push    rbp
0x180024692  push    rsi
0x180024693  push    rdi
0x180024694  push    r12
0x180024696  push    r13
0x180024698  push    r14
0x18002469a  push    r15
0x18002469c  lea     rbp, [rsp-27h]
0x1800246a1  sub     rsp, 90h
0x1800246a8  mov     rax, cs:__security_cookie
0x1800246af  xor     rax, rsp
0x1800246b2  mov     [rbp+57h+var_40], rax
0x1800246b6  mov     r15, r8
0x1800246b9  mov     rbx, rdx
0x1800246bc  mov     rdi, rcx
0x1800246bf  xor     r13d, r13d
0x1800246c2  test    rdx, rdx
0x1800246c5  jz      loc_1800248C6
0x1800246cb  test    r8, r8
0x1800246ce  jz      loc_1800248C6
0x1800246d4  mov     [r8], r13
0x1800246d7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800246db  inc     rax
0x1800246de  cmp     [rdx+rax*2], r13w
0x1800246e3  jnz     short loc_1800246DB
0x1800246e5  add     eax, eax
0x1800246e7  mov     ecx, 3E8h
0x1800246ec  cmp     eax, 64h ; 'd'
0x1800246ef  cmovl   eax, ecx
0x1800246f2  mov     [rbp+57h+var_A0], r13d
0x1800246f6  mov     [rbp+57h+var_9C], eax
0x1800246f9  mov     ecx, eax
0x1800246fb  add     rcx, rcx
0x1800246fe  mov     eax, 0FFFFFFFFh
0x180024703  cmp     rcx, rax
0x180024706  jbe     short loc_180024711
0x180024708  mov     rax, r13
0x18002470b  mov     [rbp+57h+pv], r13
0x18002470f  jmp     short loc_180024726
0x180024711  mov     ecx, ecx; cb
0x180024713  call    cs:__imp_CoTaskMemAlloc
0x180024719  mov     [rbp+57h+pv], rax
0x18002471d  test    rax, rax
0x180024720  jz      short loc_180024726
0x180024722  mov     [rax], r13w
0x180024726  test    rax, rax
0x180024729  jnz     short loc_18002473E
0x18002472b  mov     rcx, rax; pv
0x18002472e  call    cs:__imp_CoTaskMemFree
0x180024734  mov     eax, 8007000Eh
0x180024739  jmp     loc_1800248CB
0x18002473e  mov     [rdi], rbx
0x180024741  mov     esi, 25h ; '%'
0x180024746  cmp     [rbx], r13w
0x18002474a  jz      loc_1800248AA
0x180024750  cmp     [rbx], si
0x180024753  jnz     loc_180024894
0x180024759  mov     rcx, rbx; lpsz
0x18002475c  call    cs:__imp_CharNextW
0x180024762  mov     [rdi], rax
0x180024765  cmp     [rax], si
0x180024768  jnz     short loc_18002478E
0x18002476a  mov     rdx, rax; unsigned __int16 *
0x18002476d  mov     r8d, 1; int
0x180024773  lea     rcx, [rbp+57h+var_A0]; this
0x180024777  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18002477c  test    eax, eax
0x18002477e  jnz     loc_180024880
0x180024784  mov     ebx, 8007000Eh
0x180024789  jmp     loc_1800248B8
0x18002478e  mov     edx, esi; unsigned __int16
0x180024790  mov     rcx, rax; lpsz
0x180024793  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180024798  mov     rsi, rax
0x18002479b  test    rax, rax
0x18002479e  jz      loc_1800248A3
0x1800247a4  mov     rcx, rax
0x1800247a7  sub     rcx, [rdi]
0x1800247aa  sar     rcx, 1
0x1800247ad  cmp     rcx, 1Fh
0x1800247b1  jg      loc_18002489C
0x1800247b7  movsxd  r9, ecx
0x1800247ba  mov     r8, [rdi]
0x1800247bd  mov     edx, 20h ; ' '
0x1800247c2  lea     rcx, [rbp+57h+String2]
0x1800247c6  call    cs:__imp__o_wcsncpy_s
0x1800247cc  mov     ecx, eax; int
0x1800247ce  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800247d3  mov     rbx, [rdi+8]
0x1800247d7  lea     r12, [rbx+20h]
0x1800247db  mov     rcx, r12; lpCriticalSection
0x1800247de  call    cs:__imp_EnterCriticalSection
0x1800247e4  nop
0x1800247e5  lea     r14, [rbx+8]
0x1800247e9  mov     ebx, r13d
0x1800247ec  cmp     ebx, [r14+10h]
0x1800247f0  jge     short loc_180024822
0x1800247f2  movsxd  rax, ebx
0x1800247f5  mov     rcx, [r14]
0x1800247f8  lea     rdx, [rbp+57h+String2]; lpString2
0x1800247fc  mov     rcx, [rcx+rax*8]; lpString1
0x180024800  call    cs:__imp_lstrcmpiW
0x180024806  test    eax, eax
0x180024808  jz      short loc_18002480E
0x18002480a  inc     ebx
0x18002480c  jmp     short loc_1800247EC
0x18002480e  cmp     ebx, 0FFFFFFFFh
0x180024811  jz      short loc_180024822
0x180024813  mov     edx, ebx
0x180024815  mov     rcx, r14
0x180024818  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18002481d  mov     rbx, [rax]
0x180024820  jmp     short loc_180024825
0x180024822  mov     rbx, r13
0x180024825  mov     rcx, r12; lpCriticalSection
0x180024828  call    cs:__imp_LeaveCriticalSection
0x18002482e  nop
0x18002482f  test    rbx, rbx
0x180024832  jz      short loc_1800248A3
0x180024834  mov     [rbp+57h+var_90], r13
0x180024838  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002483c  inc     r8; int
0x18002483f  cmp     [rbx+r8*2], r13w
0x180024844  jnz     short loc_18002483C
0x180024846  mov     rdx, rbx; unsigned __int16 *
0x180024849  lea     rcx, [rbp+57h+var_A0]; this
0x18002484d  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180024852  mov     ebx, eax
0x180024854  lea     rcx, [rbp+57h+var_90]
0x180024858  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002485d  test    ebx, ebx
0x18002485f  jz      loc_180024784
0x180024865  mov     rax, [rdi]
0x180024868  jmp     short loc_180024876
0x18002486a  mov     rcx, rax; lpsz
0x18002486d  call    cs:__imp_CharNextW
0x180024873  mov     [rdi], rax
0x180024876  cmp     rax, rsi
0x180024879  jnz     short loc_18002486A
0x18002487b  mov     esi, 25h ; '%'
0x180024880  mov     rcx, [rdi]; lpsz
0x180024883  call    cs:__imp_CharNextW
0x180024889  mov     rbx, rax
0x18002488c  mov     [rdi], rax
0x18002488f  jmp     loc_180024746
0x180024894  mov     rdx, rbx
0x180024897  jmp     loc_18002476D
0x18002489c  mov     ebx, 80004005h
0x1800248a1  jmp     short loc_1800248B8
0x1800248a3  mov     ebx, 80020009h
0x1800248a8  jmp     short loc_1800248B8
0x1800248aa  mov     ebx, r13d
0x1800248ad  mov     rcx, [rbp+57h+pv]
0x1800248b1  mov     [rbp+57h+pv], r13
0x1800248b5  mov     [r15], rcx
0x1800248b8  mov     rcx, [rbp+57h+pv]; pv
0x1800248bc  call    cs:__imp_CoTaskMemFree
0x1800248c2  mov     eax, ebx
0x1800248c4  jmp     short loc_1800248CB
0x1800248c6  mov     eax, 80004003h
0x1800248cb  mov     rcx, [rbp+57h+var_40]
0x1800248cf  xor     rcx, rsp; StackCookie
0x1800248d2  call    __security_check_cookie
0x1800248d7  mov     rbx, [rsp+0C0h+arg_8]
0x1800248df  add     rsp, 90h
0x1800248e6  pop     r15
0x1800248e8  pop     r14
0x1800248ea  pop     r13
0x1800248ec  pop     r12
0x1800248ee  pop     rdi
0x1800248ef  pop     rsi
0x1800248f0  pop     rbp
0x1800248f1  retn
```
