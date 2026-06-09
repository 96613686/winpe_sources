# ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)

- ea: `0x18000f7e0`
- end: `0x18000fa44`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z`
- size: `612`
- prototype: `int(ATL::CRegParser *__hidden this, wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000fb7c`

## callees

- `0x180002a90`
- `0x18000e43c`
- `0x18000ee58`
- `0x18000eff4`
- `0x18000f50c`
- `0x18000f7e0`
- `0x1800105a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000f91a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000f91a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f932`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f932`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f97b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f97b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f8b0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f9bf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f9d5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f8b0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f9bf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f9d5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f953`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f953`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f867`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f867`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fa0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fa0e`

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
0x18000f7e0  mov     [rsp-8+arg_8], rbx
0x18000f7e5  push    rbp
0x18000f7e6  push    rsi
0x18000f7e7  push    rdi
0x18000f7e8  push    r12
0x18000f7ea  push    r13
0x18000f7ec  push    r14
0x18000f7ee  push    r15
0x18000f7f0  lea     rbp, [rsp-27h]
0x18000f7f5  sub     rsp, 90h
0x18000f7fc  mov     rax, cs:__security_cookie
0x18000f803  xor     rax, rsp
0x18000f806  mov     [rbp+57h+var_40], rax
0x18000f80a  mov     r15, r8
0x18000f80d  mov     rbx, rdx
0x18000f810  mov     rdi, rcx
0x18000f813  xor     r13d, r13d
0x18000f816  test    rdx, rdx
0x18000f819  jz      loc_18000FA18
0x18000f81f  test    r8, r8
0x18000f822  jz      loc_18000FA18
0x18000f828  mov     [r8], r13
0x18000f82b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f82f  inc     rax
0x18000f832  cmp     [rdx+rax*2], r13w
0x18000f837  jnz     short loc_18000F82F
0x18000f839  add     eax, eax
0x18000f83b  mov     ecx, 3E8h
0x18000f840  cmp     eax, 64h ; 'd'
0x18000f843  cmovl   eax, ecx
0x18000f846  mov     [rbp+57h+var_A0], r13d
0x18000f84a  mov     [rbp+57h+var_9C], eax
0x18000f84d  mov     ecx, eax
0x18000f84f  add     rcx, rcx
0x18000f852  mov     eax, 0FFFFFFFFh
0x18000f857  cmp     rcx, rax
0x18000f85a  jbe     short loc_18000F865
0x18000f85c  mov     rax, r13
0x18000f85f  mov     [rbp+57h+pv], r13
0x18000f863  jmp     short loc_18000F87A
0x18000f865  mov     ecx, ecx; cb
0x18000f867  call    cs:__imp_CoTaskMemAlloc
0x18000f86d  mov     [rbp+57h+pv], rax
0x18000f871  test    rax, rax
0x18000f874  jz      short loc_18000F87A
0x18000f876  mov     [rax], r13w
0x18000f87a  test    rax, rax
0x18000f87d  jnz     short loc_18000F892
0x18000f87f  mov     rcx, rax; pv
0x18000f882  call    cs:__imp_CoTaskMemFree
0x18000f888  mov     eax, 8007000Eh
0x18000f88d  jmp     loc_18000FA1D
0x18000f892  mov     [rdi], rbx
0x18000f895  mov     esi, 25h ; '%'
0x18000f89a  cmp     [rbx], r13w
0x18000f89e  jz      loc_18000F9FC
0x18000f8a4  cmp     [rbx], si
0x18000f8a7  jnz     loc_18000F9E6
0x18000f8ad  mov     rcx, rbx; lpsz
0x18000f8b0  call    cs:__imp_CharNextW
0x18000f8b6  mov     [rdi], rax
0x18000f8b9  cmp     [rax], si
0x18000f8bc  jnz     short loc_18000F8E2
0x18000f8be  mov     rdx, rax; wchar_t *
0x18000f8c1  mov     r8d, 1; int
0x18000f8c7  lea     rcx, [rbp+57h+var_A0]; this
0x18000f8cb  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x18000f8d0  test    eax, eax
0x18000f8d2  jnz     loc_18000F9D2
0x18000f8d8  mov     ebx, 8007000Eh
0x18000f8dd  jmp     loc_18000FA0A
0x18000f8e2  mov     edx, esi; wchar_t
0x18000f8e4  mov     rcx, rax; lpsz
0x18000f8e7  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x18000f8ec  mov     rsi, rax
0x18000f8ef  test    rax, rax
0x18000f8f2  jz      loc_18000F9F5
0x18000f8f8  mov     rcx, rax
0x18000f8fb  sub     rcx, [rdi]
0x18000f8fe  sar     rcx, 1
0x18000f901  cmp     rcx, 1Fh
0x18000f905  jg      loc_18000F9EE
0x18000f90b  movsxd  r9, ecx
0x18000f90e  mov     r8, [rdi]
0x18000f911  mov     edx, 20h ; ' '
0x18000f916  lea     rcx, [rbp+57h+String2]
0x18000f91a  call    cs:__imp__o_wcsncpy_s
0x18000f920  mov     ecx, eax; int
0x18000f922  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000f927  mov     rbx, [rdi+8]
0x18000f92b  lea     r12, [rbx+20h]
0x18000f92f  mov     rcx, r12; lpCriticalSection
0x18000f932  call    cs:__imp_EnterCriticalSection
0x18000f938  lea     r14, [rbx+8]
0x18000f93c  mov     ebx, r13d
0x18000f93f  cmp     ebx, [r14+10h]
0x18000f943  jge     short loc_18000F975
0x18000f945  movsxd  rax, ebx
0x18000f948  mov     rcx, [r14]
0x18000f94b  lea     rdx, [rbp+57h+String2]; lpString2
0x18000f94f  mov     rcx, [rcx+rax*8]; lpString1
0x18000f953  call    cs:__imp_lstrcmpiW
0x18000f959  test    eax, eax
0x18000f95b  jz      short loc_18000F961
0x18000f95d  inc     ebx
0x18000f95f  jmp     short loc_18000F93F
0x18000f961  cmp     ebx, 0FFFFFFFFh
0x18000f964  jz      short loc_18000F975
0x18000f966  mov     edx, ebx
0x18000f968  mov     rcx, r14
0x18000f96b  call    ?GetValueAt@?$CSimpleMap@PEA_WPEA_WVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEA_WH@Z; ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18000f970  mov     rbx, [rax]
0x18000f973  jmp     short loc_18000F978
0x18000f975  mov     rbx, r13
0x18000f978  mov     rcx, r12; lpCriticalSection
0x18000f97b  call    cs:__imp_LeaveCriticalSection
0x18000f981  test    rbx, rbx
0x18000f984  jz      short loc_18000F9F5
0x18000f986  mov     [rbp+57h+var_90], r13
0x18000f98a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000f98e  inc     r8; int
0x18000f991  cmp     [rbx+r8*2], r13w
0x18000f996  jnz     short loc_18000F98E
0x18000f998  mov     rdx, rbx; wchar_t *
0x18000f99b  lea     rcx, [rbp+57h+var_A0]; this
0x18000f99f  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x18000f9a4  mov     ebx, eax
0x18000f9a6  lea     rcx, [rbp+57h+var_90]
0x18000f9aa  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000f9af  test    ebx, ebx
0x18000f9b1  jz      loc_18000F8D8
0x18000f9b7  mov     rax, [rdi]
0x18000f9ba  jmp     short loc_18000F9C8
0x18000f9bc  mov     rcx, rax; lpsz
0x18000f9bf  call    cs:__imp_CharNextW
0x18000f9c5  mov     [rdi], rax
0x18000f9c8  cmp     rax, rsi
0x18000f9cb  jnz     short loc_18000F9BC
0x18000f9cd  mov     esi, 25h ; '%'
0x18000f9d2  mov     rcx, [rdi]; lpsz
0x18000f9d5  call    cs:__imp_CharNextW
0x18000f9db  mov     rbx, rax
0x18000f9de  mov     [rdi], rax
0x18000f9e1  jmp     loc_18000F89A
0x18000f9e6  mov     rdx, rbx
0x18000f9e9  jmp     loc_18000F8C1
0x18000f9ee  mov     ebx, 80004005h
0x18000f9f3  jmp     short loc_18000FA0A
0x18000f9f5  mov     ebx, 80020009h
0x18000f9fa  jmp     short loc_18000FA0A
0x18000f9fc  mov     ebx, r13d
0x18000f9ff  mov     rcx, [rbp+57h+pv]
0x18000fa03  mov     [rbp+57h+pv], r13
0x18000fa07  mov     [r15], rcx
0x18000fa0a  mov     rcx, [rbp+57h+pv]; pv
0x18000fa0e  call    cs:__imp_CoTaskMemFree
0x18000fa14  mov     eax, ebx
0x18000fa16  jmp     short loc_18000FA1D
0x18000fa18  mov     eax, 80004003h
0x18000fa1d  mov     rcx, [rbp+57h+var_40]
0x18000fa21  xor     rcx, rsp; StackCookie
0x18000fa24  call    __security_check_cookie
0x18000fa29  mov     rbx, [rsp+0C0h+arg_8]
0x18000fa31  add     rsp, 90h
0x18000fa38  pop     r15
0x18000fa3a  pop     r14
0x18000fa3c  pop     r13
0x18000fa3e  pop     r12
0x18000fa40  pop     rdi
0x18000fa41  pop     rsi
0x18000fa42  pop     rbp
0x18000fa43  retn
```
