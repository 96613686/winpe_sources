# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1401941ec`
- end: `0x140194496`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `682`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1401954b0`

## callees

- `0x14010e160`
- `0x14013e874`
- `0x140156ed4`
- `0x1401672c0`
- `0x1401674ec`
- `0x14017a4ec`
- `0x1401941ec`
- `0x14019ffb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140194341`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140194341`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14019435f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14019435f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401943b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1401943b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14019429d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140194459`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14019429d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140194459`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14019427c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14019427c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140194386`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140194386`
- `USER32!CharNextW` at `0x1401942d1`
- `USER32!CharNextW` at `0x1401943fe`
- `USER32!CharNextW` at `0x14019441a`
- `USER32!CharNextW` at `0x1401942d1`
- `USER32!CharNextW` at `0x1401943fe`
- `USER32!CharNextW` at `0x14019441a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
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
  int v16; // eax
  __int64 v17; // rbx
  struct _RTL_CRITICAL_SECTION *v18; // r12
  __int64 v19; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v21; // rbx
  __int64 v22; // r8
  int v23; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v25; // rcx
  SIZE_T cb; // [rsp+20h] [rbp-49h] BYREF
  _DWORD v27[2]; // [rsp+28h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-39h]
  WCHAR String2[32]; // [rsp+40h] [rbp-29h] BYREF

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
  *(_QWORD *)this = v4;
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
    *(_QWORD *)this = v10;
    if ( *v10 == 37 )
    {
      v11 = v10;
      goto LABEL_18;
    }
    v13 = ATL::CRegParser::StrChrW(v10, 0x25u);
    v14 = v13;
    if ( !v13 )
      goto LABEL_39;
    v15 = ((__int64)v13 - *(_QWORD *)this) >> 1;
    if ( v15 > 31 )
    {
      v12 = -2147467259;
      goto LABEL_41;
    }
    v16 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v15);
    ATL::AtlCrtErrorCheck(v16);
    v17 = *((_QWORD *)this + 1);
    v18 = (struct _RTL_CRITICAL_SECTION *)(v17 + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 32));
    v19 = v17 + 8;
    for ( i = 0; (signed int)i < *(_DWORD *)(v19 + 16); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v19 + 8LL * (int)i), String2) )
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
    for ( j = *(const WCHAR **)this; j != v14; *(_QWORD *)this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
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
0x1401941ec  mov     [rsp-8+arg_8], rbx
0x1401941f1  push    rbp
0x1401941f2  push    rsi
0x1401941f3  push    rdi
0x1401941f4  push    r12
0x1401941f6  push    r13
0x1401941f8  push    r14
0x1401941fa  push    r15
0x1401941fc  lea     rbp, [rsp-27h]
0x140194201  sub     rsp, 90h
0x140194208  mov     rax, cs:__security_cookie
0x14019420f  xor     rax, rsp
0x140194212  mov     [rbp+57h+var_40], rax
0x140194216  mov     r15, r8
0x140194219  mov     rbx, rdx
0x14019421c  mov     rdi, rcx
0x14019421f  xor     r13d, r13d
0x140194222  test    rdx, rdx
0x140194225  jz      loc_140194469
0x14019422b  test    r8, r8
0x14019422e  jz      loc_140194469
0x140194234  mov     [r8], r13
0x140194237  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14019423b  inc     rdx
0x14019423e  cmp     [rbx+rdx*2], r13w
0x140194243  jnz     short loc_14019423B
0x140194245  add     edx, edx
0x140194247  mov     eax, 3E8h
0x14019424c  cmp     edx, 64h ; 'd'
0x14019424f  cmovl   edx, eax
0x140194252  mov     [rbp+57h+var_98], r13d
0x140194256  mov     [rbp+57h+var_94], edx
0x140194259  mov     dword ptr [rbp+57h+cb], r13d
0x14019425d  mov     r8d, 2
0x140194263  lea     rcx, [rbp+57h+cb]
0x140194267  call    ??$AtlMultiply@K@ATL@@YAJPEAKKK@Z; ATL::AtlMultiply<ulong>(ulong *,ulong,ulong)
0x14019426c  test    eax, eax
0x14019426e  jns     short loc_140194279
0x140194270  mov     rax, r13
0x140194273  mov     [rbp+57h+pv], r13
0x140194277  jmp     short loc_140194295
0x140194279  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x14019427c  call    cs:__imp_CoTaskMemAlloc
0x140194283  nop     dword ptr [rax+rax+00h]
0x140194288  mov     [rbp+57h+pv], rax
0x14019428c  test    rax, rax
0x14019428f  jz      short loc_140194295
0x140194291  mov     [rax], r13w
0x140194295  test    rax, rax
0x140194298  jnz     short loc_1401942B3
0x14019429a  mov     rcx, rax; pv
0x14019429d  call    cs:__imp_CoTaskMemFree
0x1401942a4  nop     dword ptr [rax+rax+00h]
0x1401942a9  mov     eax, 8007000Eh
0x1401942ae  jmp     loc_14019446E
0x1401942b3  mov     [rdi], rbx
0x1401942b6  mov     esi, 25h ; '%'
0x1401942bb  cmp     [rbx], r13w
0x1401942bf  jz      loc_140194447
0x1401942c5  cmp     [rbx], si
0x1401942c8  jnz     loc_140194431
0x1401942ce  mov     rcx, rbx; lpsz
0x1401942d1  call    cs:__imp_CharNextW
0x1401942d8  nop     dword ptr [rax+rax+00h]
0x1401942dd  mov     [rdi], rax
0x1401942e0  cmp     [rax], si
0x1401942e3  jnz     short loc_140194309
0x1401942e5  mov     rdx, rax; unsigned __int16 *
0x1401942e8  mov     r8d, 1; int
0x1401942ee  lea     rcx, [rbp+57h+var_98]; this
0x1401942f2  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1401942f7  test    eax, eax
0x1401942f9  jnz     loc_140194417
0x1401942ff  mov     ebx, 8007000Eh
0x140194304  jmp     loc_140194455
0x140194309  mov     edx, esi; unsigned __int16
0x14019430b  mov     rcx, rax; lpsz
0x14019430e  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x140194313  mov     rsi, rax
0x140194316  test    rax, rax
0x140194319  jz      loc_140194440
0x14019431f  mov     rcx, rax
0x140194322  sub     rcx, [rdi]
0x140194325  sar     rcx, 1
0x140194328  cmp     rcx, 1Fh
0x14019432c  jg      loc_140194439
0x140194332  movsxd  r9, ecx
0x140194335  mov     r8, [rdi]
0x140194338  mov     edx, 20h ; ' '
0x14019433d  lea     rcx, [rbp+57h+String2]
0x140194341  call    cs:__imp__o_wcsncpy_s
0x140194348  nop     dword ptr [rax+rax+00h]
0x14019434d  mov     ecx, eax; int
0x14019434f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x140194354  mov     rbx, [rdi+8]
0x140194358  lea     r12, [rbx+20h]
0x14019435c  mov     rcx, r12; lpCriticalSection
0x14019435f  call    cs:__imp_EnterCriticalSection
0x140194366  nop     dword ptr [rax+rax+00h]
0x14019436b  lea     r14, [rbx+8]
0x14019436f  mov     ebx, r13d
0x140194372  cmp     ebx, [r14+10h]
0x140194376  jge     short loc_1401943AE
0x140194378  movsxd  rax, ebx
0x14019437b  mov     rcx, [r14]
0x14019437e  lea     rdx, [rbp+57h+String2]; lpString2
0x140194382  mov     rcx, [rcx+rax*8]; lpString1
0x140194386  call    cs:__imp_lstrcmpiW
0x14019438d  nop     dword ptr [rax+rax+00h]
0x140194392  test    eax, eax
0x140194394  jz      short loc_14019439A
0x140194396  inc     ebx
0x140194398  jmp     short loc_140194372
0x14019439a  cmp     ebx, 0FFFFFFFFh
0x14019439d  jz      short loc_1401943AE
0x14019439f  mov     edx, ebx
0x1401943a1  mov     rcx, r14
0x1401943a4  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x1401943a9  mov     rbx, [rax]
0x1401943ac  jmp     short loc_1401943B1
0x1401943ae  mov     rbx, r13
0x1401943b1  mov     rcx, r12; lpCriticalSection
0x1401943b4  call    cs:__imp_LeaveCriticalSection
0x1401943bb  nop     dword ptr [rax+rax+00h]
0x1401943c0  test    rbx, rbx
0x1401943c3  jz      short loc_140194440
0x1401943c5  mov     [rbp+57h+cb], r13
0x1401943c9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1401943cd  inc     r8; int
0x1401943d0  cmp     [rbx+r8*2], r13w
0x1401943d5  jnz     short loc_1401943CD
0x1401943d7  mov     rdx, rbx; unsigned __int16 *
0x1401943da  lea     rcx, [rbp+57h+var_98]; this
0x1401943de  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1401943e3  mov     ebx, eax
0x1401943e5  lea     rcx, [rbp+57h+cb]
0x1401943e9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1401943ee  test    ebx, ebx
0x1401943f0  jz      loc_1401942FF
0x1401943f6  mov     rax, [rdi]
0x1401943f9  jmp     short loc_14019440D
0x1401943fb  mov     rcx, rax; lpsz
0x1401943fe  call    cs:__imp_CharNextW
0x140194405  nop     dword ptr [rax+rax+00h]
0x14019440a  mov     [rdi], rax
0x14019440d  cmp     rax, rsi
0x140194410  jnz     short loc_1401943FB
0x140194412  mov     esi, 25h ; '%'
0x140194417  mov     rcx, [rdi]; lpsz
0x14019441a  call    cs:__imp_CharNextW
0x140194421  nop     dword ptr [rax+rax+00h]
0x140194426  mov     rbx, rax
0x140194429  mov     [rdi], rax
0x14019442c  jmp     loc_1401942BB
0x140194431  mov     rdx, rbx
0x140194434  jmp     loc_1401942E8
0x140194439  mov     ebx, 80004005h
0x14019443e  jmp     short loc_140194455
0x140194440  mov     ebx, 80020009h
0x140194445  jmp     short loc_140194455
0x140194447  mov     ebx, r13d
0x14019444a  mov     rcx, [rbp+57h+pv]
0x14019444e  mov     [rbp+57h+pv], r13
0x140194452  mov     [r15], rcx
0x140194455  mov     rcx, [rbp+57h+pv]; pv
0x140194459  call    cs:__imp_CoTaskMemFree
0x140194460  nop     dword ptr [rax+rax+00h]
0x140194465  mov     eax, ebx
0x140194467  jmp     short loc_14019446E
0x140194469  mov     eax, 80004003h
0x14019446e  mov     rcx, [rbp+57h+var_40]
0x140194472  xor     rcx, rsp; StackCookie
0x140194475  call    __security_check_cookie
0x14019447a  mov     rbx, [rsp+0C0h+arg_8]
0x140194482  add     rsp, 90h
0x140194489  pop     r15
0x14019448b  pop     r14
0x14019448d  pop     r13
0x14019448f  pop     r12
0x140194491  pop     rdi
0x140194492  pop     rsi
0x140194493  pop     rbp
0x140194494  retn
```
