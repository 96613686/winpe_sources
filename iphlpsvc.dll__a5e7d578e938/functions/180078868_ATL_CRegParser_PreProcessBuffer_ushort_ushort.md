# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180078868`
- end: `0x180078b05`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `669`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180078c5c`

## callees

- `0x18004b5f0`
- `0x180077554`
- `0x180077ff8`
- `0x180078134`
- `0x18007859c`
- `0x180078658`
- `0x180078868`
- `0x180079818`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800789b5`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800789b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078a21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078a21`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180078945`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180078a6c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180078a88`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180078945`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180078a6c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180078a88`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800789f3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800789f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078910`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078ac7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078910`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078ac7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800788ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800788ef`

## pseudocode

```c
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
    ATL::CComSafeDeleteCriticalSection::Lock((struct _RTL_CRITICAL_SECTION *)(v18 + 32));
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
0x180078868  mov     [rsp-8+arg_8], rbx
0x18007886d  push    rbp
0x18007886e  push    rsi
0x18007886f  push    rdi
0x180078870  push    r12
0x180078872  push    r13
0x180078874  push    r14
0x180078876  push    r15
0x180078878  lea     rbp, [rsp-27h]
0x18007887d  sub     rsp, 90h
0x180078884  mov     rax, cs:__security_cookie
0x18007888b  xor     rax, rsp
0x18007888e  mov     [rbp+57h+var_40], rax
0x180078892  mov     r15, r8
0x180078895  mov     rbx, rdx
0x180078898  mov     rdi, rcx
0x18007889b  xor     r13d, r13d
0x18007889e  test    rdx, rdx
0x1800788a1  jz      loc_180078AD8
0x1800788a7  test    r8, r8
0x1800788aa  jz      loc_180078AD8
0x1800788b0  mov     [r8], r13
0x1800788b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800788b7  inc     rax
0x1800788ba  cmp     [rdx+rax*2], r13w
0x1800788bf  jnz     short loc_1800788B7
0x1800788c1  add     eax, eax
0x1800788c3  mov     ecx, 3E8h
0x1800788c8  cmp     eax, 64h ; 'd'
0x1800788cb  cmovl   eax, ecx
0x1800788ce  mov     [rbp+57h+var_A0], r13d
0x1800788d2  mov     [rbp+57h+var_9C], eax
0x1800788d5  mov     ecx, eax
0x1800788d7  add     rcx, rcx
0x1800788da  mov     eax, 0FFFFFFFFh
0x1800788df  cmp     rcx, rax
0x1800788e2  jbe     short loc_1800788ED
0x1800788e4  mov     rax, r13
0x1800788e7  mov     [rbp+57h+pv], r13
0x1800788eb  jmp     short loc_180078908
0x1800788ed  mov     ecx, ecx; cb
0x1800788ef  call    cs:__imp_CoTaskMemAlloc
0x1800788f6  nop     dword ptr [rax+rax+00h]
0x1800788fb  mov     [rbp+57h+pv], rax
0x1800788ff  test    rax, rax
0x180078902  jz      short loc_180078908
0x180078904  mov     [rax], r13w
0x180078908  test    rax, rax
0x18007890b  jnz     short loc_180078927
0x18007890d  mov     rcx, rax; pv
0x180078910  call    cs:__imp_CoTaskMemFree
0x180078917  nop     dword ptr [rax+rax+00h]
0x18007891c  nop
0x18007891d  mov     eax, 8007000Eh
0x180078922  jmp     loc_180078ADD
0x180078927  mov     [rdi], rbx
0x18007892a  mov     esi, 25h ; '%'
0x18007892f  cmp     [rbx], r13w
0x180078933  jz      loc_180078AB5
0x180078939  cmp     [rbx], si
0x18007893c  jnz     loc_180078A9F
0x180078942  mov     rcx, rbx; lpsz
0x180078945  call    cs:__imp_CharNextW
0x18007894c  nop     dword ptr [rax+rax+00h]
0x180078951  mov     [rdi], rax
0x180078954  cmp     [rax], si
0x180078957  jnz     short loc_18007897D
0x180078959  mov     rdx, rax; unsigned __int16 *
0x18007895c  mov     r8d, 1; int
0x180078962  lea     rcx, [rbp+57h+var_A0]; this
0x180078966  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18007896b  test    eax, eax
0x18007896d  jnz     loc_180078A85
0x180078973  mov     ebx, 8007000Eh
0x180078978  jmp     loc_180078AC3
0x18007897d  mov     edx, esi; unsigned __int16
0x18007897f  mov     rcx, rax; lpsz
0x180078982  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180078987  mov     rsi, rax
0x18007898a  test    rax, rax
0x18007898d  jz      loc_180078AAE
0x180078993  mov     rcx, rax
0x180078996  sub     rcx, [rdi]
0x180078999  sar     rcx, 1
0x18007899c  cmp     rcx, 1Fh
0x1800789a0  jg      loc_180078AA7
0x1800789a6  movsxd  r9, ecx
0x1800789a9  mov     r8, [rdi]
0x1800789ac  mov     edx, 20h ; ' '
0x1800789b1  lea     rcx, [rbp+57h+String2]
0x1800789b5  call    cs:__imp__o_wcsncpy_s
0x1800789bc  nop     dword ptr [rax+rax+00h]
0x1800789c1  mov     ecx, eax; int
0x1800789c3  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800789c8  mov     rbx, [rdi+8]
0x1800789cc  lea     r12, [rbx+20h]
0x1800789d0  mov     rcx, r12; this
0x1800789d3  call    ?Lock@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Lock(void)
0x1800789d8  lea     r14, [rbx+8]
0x1800789dc  mov     ebx, r13d
0x1800789df  cmp     ebx, [r14+10h]
0x1800789e3  jge     short loc_180078A1B
0x1800789e5  movsxd  rax, ebx
0x1800789e8  mov     rcx, [r14]
0x1800789eb  lea     rdx, [rbp+57h+String2]; lpString2
0x1800789ef  mov     rcx, [rcx+rax*8]; lpString1
0x1800789f3  call    cs:__imp_lstrcmpiW
0x1800789fa  nop     dword ptr [rax+rax+00h]
0x1800789ff  test    eax, eax
0x180078a01  jz      short loc_180078A07
0x180078a03  inc     ebx
0x180078a05  jmp     short loc_1800789DF
0x180078a07  cmp     ebx, 0FFFFFFFFh
0x180078a0a  jz      short loc_180078A1B
0x180078a0c  mov     edx, ebx
0x180078a0e  mov     rcx, r14
0x180078a11  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180078a16  mov     rbx, [rax]
0x180078a19  jmp     short loc_180078A1E
0x180078a1b  mov     rbx, r13
0x180078a1e  mov     rcx, r12; lpCriticalSection
0x180078a21  call    cs:__imp_LeaveCriticalSection
0x180078a28  nop     dword ptr [rax+rax+00h]
0x180078a2d  nop
0x180078a2e  test    rbx, rbx
0x180078a31  jz      short loc_180078AAE
0x180078a33  mov     [rbp+57h+var_90], r13
0x180078a37  or      r8, 0FFFFFFFFFFFFFFFFh
0x180078a3b  inc     r8; int
0x180078a3e  cmp     [rbx+r8*2], r13w
0x180078a43  jnz     short loc_180078A3B
0x180078a45  mov     rdx, rbx; unsigned __int16 *
0x180078a48  lea     rcx, [rbp+57h+var_A0]; this
0x180078a4c  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180078a51  mov     ebx, eax
0x180078a53  lea     rcx, [rbp+57h+var_90]
0x180078a57  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180078a5c  test    ebx, ebx
0x180078a5e  jz      loc_180078973
0x180078a64  mov     rax, [rdi]
0x180078a67  jmp     short loc_180078A7B
0x180078a69  mov     rcx, rax; lpsz
0x180078a6c  call    cs:__imp_CharNextW
0x180078a73  nop     dword ptr [rax+rax+00h]
0x180078a78  mov     [rdi], rax
0x180078a7b  cmp     rax, rsi
0x180078a7e  jnz     short loc_180078A69
0x180078a80  mov     esi, 25h ; '%'
0x180078a85  mov     rcx, [rdi]; lpsz
0x180078a88  call    cs:__imp_CharNextW
0x180078a8f  nop     dword ptr [rax+rax+00h]
0x180078a94  mov     rbx, rax
0x180078a97  mov     [rdi], rax
0x180078a9a  jmp     loc_18007892F
0x180078a9f  mov     rdx, rbx
0x180078aa2  jmp     loc_18007895C
0x180078aa7  mov     ebx, 80004005h
0x180078aac  jmp     short loc_180078AC3
0x180078aae  mov     ebx, 80020009h
0x180078ab3  jmp     short loc_180078AC3
0x180078ab5  mov     ebx, r13d
0x180078ab8  mov     rcx, [rbp+57h+pv]
0x180078abc  mov     [rbp+57h+pv], r13
0x180078ac0  mov     [r15], rcx
0x180078ac3  mov     rcx, [rbp+57h+pv]; pv
0x180078ac7  call    cs:__imp_CoTaskMemFree
0x180078ace  nop     dword ptr [rax+rax+00h]
0x180078ad3  nop
0x180078ad4  mov     eax, ebx
0x180078ad6  jmp     short loc_180078ADD
0x180078ad8  mov     eax, 80004003h
0x180078add  mov     rcx, [rbp+57h+var_40]
0x180078ae1  xor     rcx, rsp; StackCookie
0x180078ae4  call    __security_check_cookie
0x180078ae9  mov     rbx, [rsp+0C0h+arg_8]
0x180078af1  add     rsp, 90h
0x180078af8  pop     r15
0x180078afa  pop     r14
0x180078afc  pop     r13
0x180078afe  pop     r12
0x180078b00  pop     rdi
0x180078b01  pop     rsi
0x180078b02  pop     rbp
0x180078b03  retn
```
