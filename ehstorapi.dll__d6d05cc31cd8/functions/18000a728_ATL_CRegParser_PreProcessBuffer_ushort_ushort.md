# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000a728`
- end: `0x18000a995`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `621`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ab0c`

## callees

- `0x180002210`
- `0x180008b90`
- `0x180008bf4`
- `0x180009758`
- `0x18000a3bc`
- `0x18000a728`
- `0x18000b5f4`
- `0x18000c4f0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000a86b`
- `msvcrt!wcsncpy_s` at `0x18000a86b`
- `USER32!CharNextW` at `0x18000a801`
- `USER32!CharNextW` at `0x18000a910`
- `USER32!CharNextW` at `0x18000a926`
- `USER32!CharNextW` at `0x18000a801`
- `USER32!CharNextW` at `0x18000a910`
- `USER32!CharNextW` at `0x18000a926`
- `KERNEL32!EnterCriticalSection` at `0x18000a883`
- `KERNEL32!EnterCriticalSection` at `0x18000a883`
- `KERNEL32!lstrcmpiW` at `0x18000a8a4`
- `KERNEL32!lstrcmpiW` at `0x18000a8a4`
- `KERNEL32!LeaveCriticalSection` at `0x18000a8cc`
- `KERNEL32!LeaveCriticalSection` at `0x18000a8cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a7b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a7b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a7d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a95f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a7d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a95f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(const wchar_t **this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rdx
  __int64 v7; // rdx
  _WORD *v8; // rax
  LPWSTR v10; // rax
  const unsigned __int16 *v11; // rdx
  unsigned int v12; // ebx
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rsi
  __int64 v15; // rcx
  errno_t v16; // eax
  const wchar_t *v17; // rbx
  struct _RTL_CRITICAL_SECTION *v18; // r12
  const wchar_t *v19; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v21; // rbx
  __int64 v22; // r8
  int v23; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v25; // rcx
  SIZE_T cb; // [rsp+20h] [rbp-49h] BYREF
  _DWORD v27[2]; // [rsp+28h] [rbp-41h] BYREF
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
  v27[0] = 0;
  v27[1] = v7;
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
  *this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v11 = v4;
LABEL_18:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v11, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v10 = CharNextW(v4);
    *this = v10;
    if ( *v10 == 37 )
    {
      v11 = v10;
      goto LABEL_18;
    }
    v13 = ATL::CRegParser::StrChrW(v10, 0x25u);
    v14 = v13;
    if ( !v13 )
      goto LABEL_39;
    v15 = v13 - *this;
    if ( v15 > 31 )
    {
      v12 = -2147467259;
      goto LABEL_41;
    }
    v16 = wcsncpy_s(Destination, 0x20u, *this, (int)v15);
    ATL::AtlCrtErrorCheck(v16);
    v17 = this[1];
    v18 = (struct _RTL_CRITICAL_SECTION *)(v17 + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 16));
    v19 = v17 + 4;
    for ( i = 0; (signed int)i < *((_DWORD *)v19 + 4); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v19 + 8LL * (int)i), Destination) )
      {
        if ( i != -1 )
        {
          v21 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                              v19,
                                              i);
          goto LABEL_29;
        }
        break;
      }
    }
    v21 = 0;
LABEL_29:
    LeaveCriticalSection(v18);
    if ( !v21 )
    {
LABEL_39:
      v12 = -2147352567;
      goto LABEL_41;
    }
    cb = 0;
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    v23 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v21, v22);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&cb);
    if ( !v23 )
    {
LABEL_19:
      v12 = -2147024882;
      goto LABEL_41;
    }
    for ( j = *this; j != v14; *this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*this);
    *this = v4;
  }
  v12 = 0;
  v25 = (unsigned __int16 *)pv;
  pv = 0;
  *a3 = v25;
LABEL_41:
  CoTaskMemFree(pv);
  return v12;
}

```

## disassembly

```asm
0x18000a728  mov     [rsp-8+arg_8], rbx
0x18000a72d  push    rbp
0x18000a72e  push    rsi
0x18000a72f  push    rdi
0x18000a730  push    r12
0x18000a732  push    r13
0x18000a734  push    r14
0x18000a736  push    r15
0x18000a738  lea     rbp, [rsp-27h]
0x18000a73d  sub     rsp, 90h
0x18000a744  mov     rax, cs:__security_cookie
0x18000a74b  xor     rax, rsp
0x18000a74e  mov     [rbp+57h+var_40], rax
0x18000a752  mov     r15, r8
0x18000a755  mov     rbx, rdx
0x18000a758  mov     rdi, rcx
0x18000a75b  xor     r13d, r13d
0x18000a75e  test    rdx, rdx
0x18000a761  jz      loc_18000A969
0x18000a767  test    r8, r8
0x18000a76a  jz      loc_18000A969
0x18000a770  mov     [r8], r13
0x18000a773  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000a777  inc     rdx
0x18000a77a  cmp     [rbx+rdx*2], r13w
0x18000a77f  jnz     short loc_18000A777
0x18000a781  add     edx, edx
0x18000a783  mov     eax, 3E8h
0x18000a788  cmp     edx, 64h ; 'd'
0x18000a78b  cmovl   edx, eax
0x18000a78e  mov     [rbp+57h+var_98], r13d
0x18000a792  mov     [rbp+57h+var_94], edx
0x18000a795  mov     dword ptr [rbp+57h+cb], r13d
0x18000a799  mov     r8d, 2
0x18000a79f  lea     rcx, [rbp+57h+cb]
0x18000a7a3  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x18000a7a8  test    eax, eax
0x18000a7aa  jns     short loc_18000A7B5
0x18000a7ac  mov     rax, r13
0x18000a7af  mov     [rbp+57h+pv], r13
0x18000a7b3  jmp     short loc_18000A7CB
0x18000a7b5  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x18000a7b8  call    cs:__imp_CoTaskMemAlloc
0x18000a7be  mov     [rbp+57h+pv], rax
0x18000a7c2  test    rax, rax
0x18000a7c5  jz      short loc_18000A7CB
0x18000a7c7  mov     [rax], r13w
0x18000a7cb  test    rax, rax
0x18000a7ce  jnz     short loc_18000A7E3
0x18000a7d0  mov     rcx, rax; pv
0x18000a7d3  call    cs:__imp_CoTaskMemFree
0x18000a7d9  mov     eax, 8007000Eh
0x18000a7de  jmp     loc_18000A96E
0x18000a7e3  mov     [rdi], rbx
0x18000a7e6  mov     esi, 25h ; '%'
0x18000a7eb  cmp     [rbx], r13w
0x18000a7ef  jz      loc_18000A94D
0x18000a7f5  cmp     [rbx], si
0x18000a7f8  jnz     loc_18000A937
0x18000a7fe  mov     rcx, rbx; lpsz
0x18000a801  call    cs:__imp_CharNextW
0x18000a807  mov     [rdi], rax
0x18000a80a  cmp     [rax], si
0x18000a80d  jnz     short loc_18000A833
0x18000a80f  mov     rdx, rax; unsigned __int16 *
0x18000a812  mov     r8d, 1; int
0x18000a818  lea     rcx, [rbp+57h+var_98]; this
0x18000a81c  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000a821  test    eax, eax
0x18000a823  jnz     loc_18000A923
0x18000a829  mov     ebx, 8007000Eh
0x18000a82e  jmp     loc_18000A95B
0x18000a833  mov     edx, esi; unsigned __int16
0x18000a835  mov     rcx, rax; lpsz
0x18000a838  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000a83d  mov     rsi, rax
0x18000a840  test    rax, rax
0x18000a843  jz      loc_18000A946
0x18000a849  mov     rcx, rax
0x18000a84c  sub     rcx, [rdi]
0x18000a84f  sar     rcx, 1
0x18000a852  cmp     rcx, 1Fh
0x18000a856  jg      loc_18000A93F
0x18000a85c  movsxd  r9, ecx; MaxCount
0x18000a85f  mov     r8, [rdi]; Source
0x18000a862  mov     edx, 20h ; ' '; SizeInWords
0x18000a867  lea     rcx, [rbp+57h+Destination]; Destination
0x18000a86b  call    cs:__imp_wcsncpy_s
0x18000a871  mov     ecx, eax; int
0x18000a873  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000a878  mov     rbx, [rdi+8]
0x18000a87c  lea     r12, [rbx+20h]
0x18000a880  mov     rcx, r12; lpCriticalSection
0x18000a883  call    cs:__imp_EnterCriticalSection
0x18000a889  lea     r14, [rbx+8]
0x18000a88d  mov     ebx, r13d
0x18000a890  cmp     ebx, [r14+10h]
0x18000a894  jge     short loc_18000A8C6
0x18000a896  movsxd  rax, ebx
0x18000a899  mov     rcx, [r14]
0x18000a89c  lea     rdx, [rbp+57h+Destination]; lpString2
0x18000a8a0  mov     rcx, [rcx+rax*8]; lpString1
0x18000a8a4  call    cs:__imp_lstrcmpiW
0x18000a8aa  test    eax, eax
0x18000a8ac  jz      short loc_18000A8B2
0x18000a8ae  inc     ebx
0x18000a8b0  jmp     short loc_18000A890
0x18000a8b2  cmp     ebx, 0FFFFFFFFh
0x18000a8b5  jz      short loc_18000A8C6
0x18000a8b7  mov     edx, ebx
0x18000a8b9  mov     rcx, r14
0x18000a8bc  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18000a8c1  mov     rbx, [rax]
0x18000a8c4  jmp     short loc_18000A8C9
0x18000a8c6  mov     rbx, r13
0x18000a8c9  mov     rcx, r12; lpCriticalSection
0x18000a8cc  call    cs:__imp_LeaveCriticalSection
0x18000a8d2  test    rbx, rbx
0x18000a8d5  jz      short loc_18000A946
0x18000a8d7  mov     [rbp+57h+cb], r13
0x18000a8db  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000a8df  inc     r8; int
0x18000a8e2  cmp     [rbx+r8*2], r13w
0x18000a8e7  jnz     short loc_18000A8DF
0x18000a8e9  mov     rdx, rbx; unsigned __int16 *
0x18000a8ec  lea     rcx, [rbp+57h+var_98]; this
0x18000a8f0  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000a8f5  mov     ebx, eax
0x18000a8f7  lea     rcx, [rbp+57h+cb]
0x18000a8fb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000a900  test    ebx, ebx
0x18000a902  jz      loc_18000A829
0x18000a908  mov     rax, [rdi]
0x18000a90b  jmp     short loc_18000A919
0x18000a90d  mov     rcx, rax; lpsz
0x18000a910  call    cs:__imp_CharNextW
0x18000a916  mov     [rdi], rax
0x18000a919  cmp     rax, rsi
0x18000a91c  jnz     short loc_18000A90D
0x18000a91e  mov     esi, 25h ; '%'
0x18000a923  mov     rcx, [rdi]; lpsz
0x18000a926  call    cs:__imp_CharNextW
0x18000a92c  mov     rbx, rax
0x18000a92f  mov     [rdi], rax
0x18000a932  jmp     loc_18000A7EB
0x18000a937  mov     rdx, rbx
0x18000a93a  jmp     loc_18000A812
0x18000a93f  mov     ebx, 80004005h
0x18000a944  jmp     short loc_18000A95B
0x18000a946  mov     ebx, 80020009h
0x18000a94b  jmp     short loc_18000A95B
0x18000a94d  mov     ebx, r13d
0x18000a950  mov     rcx, [rbp+57h+pv]
0x18000a954  mov     [rbp+57h+pv], r13
0x18000a958  mov     [r15], rcx
0x18000a95b  mov     rcx, [rbp+57h+pv]; pv
0x18000a95f  call    cs:__imp_CoTaskMemFree
0x18000a965  mov     eax, ebx
0x18000a967  jmp     short loc_18000A96E
0x18000a969  mov     eax, 80004003h
0x18000a96e  mov     rcx, [rbp+57h+var_40]
0x18000a972  xor     rcx, rsp; StackCookie
0x18000a975  call    __security_check_cookie
0x18000a97a  mov     rbx, [rsp+0C0h+arg_8]
0x18000a982  add     rsp, 90h
0x18000a989  pop     r15
0x18000a98b  pop     r14
0x18000a98d  pop     r13
0x18000a98f  pop     r12
0x18000a991  pop     rdi
0x18000a992  pop     rsi
0x18000a993  pop     rbp
0x18000a994  retn
```
