# ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)

- ea: `0x180019e88`
- end: `0x18001a0ec`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z`
- size: `612`
- prototype: `int(ATL::CRegParser *__hidden this, wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a418`

## callees

- `0x18000fcd0`
- `0x180016634`
- `0x1800173b8`
- `0x18001760c`
- `0x18001992c`
- `0x180019e88`
- `0x18001b99c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180019fc2`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180019fc2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019fda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019fda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a023`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a023`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019f2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a0b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019f2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a0b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019f0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019f0f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019f58`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001a067`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001a07d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019f58`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001a067`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001a07d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180019ffb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180019ffb`

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
  _QWORD *v29; // [rsp+30h] [rbp-39h] BYREF
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
0x180019e88  mov     [rsp-8+arg_8], rbx
0x180019e8d  push    rbp
0x180019e8e  push    rsi
0x180019e8f  push    rdi
0x180019e90  push    r12
0x180019e92  push    r13
0x180019e94  push    r14
0x180019e96  push    r15
0x180019e98  lea     rbp, [rsp-27h]
0x180019e9d  sub     rsp, 90h
0x180019ea4  mov     rax, cs:__security_cookie
0x180019eab  xor     rax, rsp
0x180019eae  mov     [rbp+57h+var_40], rax
0x180019eb2  mov     r15, r8
0x180019eb5  mov     rbx, rdx
0x180019eb8  mov     rdi, rcx
0x180019ebb  xor     r13d, r13d
0x180019ebe  test    rdx, rdx
0x180019ec1  jz      loc_18001A0C0
0x180019ec7  test    r8, r8
0x180019eca  jz      loc_18001A0C0
0x180019ed0  mov     [r8], r13
0x180019ed3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019ed7  inc     rax
0x180019eda  cmp     [rdx+rax*2], r13w
0x180019edf  jnz     short loc_180019ED7
0x180019ee1  add     eax, eax
0x180019ee3  mov     ecx, 3E8h
0x180019ee8  cmp     eax, 64h ; 'd'
0x180019eeb  cmovl   eax, ecx
0x180019eee  mov     [rbp+57h+var_A0], r13d
0x180019ef2  mov     [rbp+57h+var_9C], eax
0x180019ef5  mov     ecx, eax
0x180019ef7  add     rcx, rcx
0x180019efa  mov     eax, 0FFFFFFFFh
0x180019eff  cmp     rcx, rax
0x180019f02  jbe     short loc_180019F0D
0x180019f04  mov     rax, r13
0x180019f07  mov     [rbp+57h+pv], r13
0x180019f0b  jmp     short loc_180019F22
0x180019f0d  mov     ecx, ecx; cb
0x180019f0f  call    cs:__imp_CoTaskMemAlloc
0x180019f15  mov     [rbp+57h+pv], rax
0x180019f19  test    rax, rax
0x180019f1c  jz      short loc_180019F22
0x180019f1e  mov     [rax], r13w
0x180019f22  test    rax, rax
0x180019f25  jnz     short loc_180019F3A
0x180019f27  mov     rcx, rax; pv
0x180019f2a  call    cs:__imp_CoTaskMemFree
0x180019f30  mov     eax, 8007000Eh
0x180019f35  jmp     loc_18001A0C5
0x180019f3a  mov     [rdi], rbx
0x180019f3d  mov     esi, 25h ; '%'
0x180019f42  cmp     [rbx], r13w
0x180019f46  jz      loc_18001A0A4
0x180019f4c  cmp     [rbx], si
0x180019f4f  jnz     loc_18001A08E
0x180019f55  mov     rcx, rbx; lpsz
0x180019f58  call    cs:__imp_CharNextW
0x180019f5e  mov     [rdi], rax
0x180019f61  cmp     [rax], si
0x180019f64  jnz     short loc_180019F8A
0x180019f66  mov     rdx, rax; wchar_t *
0x180019f69  mov     r8d, 1; int
0x180019f6f  lea     rcx, [rbp+57h+var_A0]; this
0x180019f73  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x180019f78  test    eax, eax
0x180019f7a  jnz     loc_18001A07A
0x180019f80  mov     ebx, 8007000Eh
0x180019f85  jmp     loc_18001A0B2
0x180019f8a  mov     edx, esi; wchar_t
0x180019f8c  mov     rcx, rax; lpsz
0x180019f8f  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x180019f94  mov     rsi, rax
0x180019f97  test    rax, rax
0x180019f9a  jz      loc_18001A09D
0x180019fa0  mov     rcx, rax
0x180019fa3  sub     rcx, [rdi]
0x180019fa6  sar     rcx, 1
0x180019fa9  cmp     rcx, 1Fh
0x180019fad  jg      loc_18001A096
0x180019fb3  movsxd  r9, ecx
0x180019fb6  mov     r8, [rdi]
0x180019fb9  mov     edx, 20h ; ' '
0x180019fbe  lea     rcx, [rbp+57h+String2]
0x180019fc2  call    cs:__imp__o_wcsncpy_s
0x180019fc8  mov     ecx, eax; int
0x180019fca  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180019fcf  mov     rbx, [rdi+8]
0x180019fd3  lea     r12, [rbx+20h]
0x180019fd7  mov     rcx, r12; lpCriticalSection
0x180019fda  call    cs:__imp_EnterCriticalSection
0x180019fe0  lea     r14, [rbx+8]
0x180019fe4  mov     ebx, r13d
0x180019fe7  cmp     ebx, [r14+10h]
0x180019feb  jge     short loc_18001A01D
0x180019fed  movsxd  rax, ebx
0x180019ff0  mov     rcx, [r14]
0x180019ff3  lea     rdx, [rbp+57h+String2]; lpString2
0x180019ff7  mov     rcx, [rcx+rax*8]; lpString1
0x180019ffb  call    cs:__imp_lstrcmpiW
0x18001a001  test    eax, eax
0x18001a003  jz      short loc_18001A009
0x18001a005  inc     ebx
0x18001a007  jmp     short loc_180019FE7
0x18001a009  cmp     ebx, 0FFFFFFFFh
0x18001a00c  jz      short loc_18001A01D
0x18001a00e  mov     edx, ebx
0x18001a010  mov     rcx, r14
0x18001a013  call    ?GetValueAt@?$CSimpleMap@PEA_WPEA_WVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEA_WH@Z; ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18001a018  mov     rbx, [rax]
0x18001a01b  jmp     short loc_18001A020
0x18001a01d  mov     rbx, r13
0x18001a020  mov     rcx, r12; lpCriticalSection
0x18001a023  call    cs:__imp_LeaveCriticalSection
0x18001a029  test    rbx, rbx
0x18001a02c  jz      short loc_18001A09D
0x18001a02e  mov     [rbp+57h+var_90], r13
0x18001a032  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001a036  inc     r8; int
0x18001a039  cmp     [rbx+r8*2], r13w
0x18001a03e  jnz     short loc_18001A036
0x18001a040  mov     rdx, rbx; wchar_t *
0x18001a043  lea     rcx, [rbp+57h+var_A0]; this
0x18001a047  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x18001a04c  mov     ebx, eax
0x18001a04e  lea     rcx, [rbp+57h+var_90]
0x18001a052  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a057  test    ebx, ebx
0x18001a059  jz      loc_180019F80
0x18001a05f  mov     rax, [rdi]
0x18001a062  jmp     short loc_18001A070
0x18001a064  mov     rcx, rax; lpsz
0x18001a067  call    cs:__imp_CharNextW
0x18001a06d  mov     [rdi], rax
0x18001a070  cmp     rax, rsi
0x18001a073  jnz     short loc_18001A064
0x18001a075  mov     esi, 25h ; '%'
0x18001a07a  mov     rcx, [rdi]; lpsz
0x18001a07d  call    cs:__imp_CharNextW
0x18001a083  mov     rbx, rax
0x18001a086  mov     [rdi], rax
0x18001a089  jmp     loc_180019F42
0x18001a08e  mov     rdx, rbx
0x18001a091  jmp     loc_180019F69
0x18001a096  mov     ebx, 80004005h
0x18001a09b  jmp     short loc_18001A0B2
0x18001a09d  mov     ebx, 80020009h
0x18001a0a2  jmp     short loc_18001A0B2
0x18001a0a4  mov     ebx, r13d
0x18001a0a7  mov     rcx, [rbp+57h+pv]
0x18001a0ab  mov     [rbp+57h+pv], r13
0x18001a0af  mov     [r15], rcx
0x18001a0b2  mov     rcx, [rbp+57h+pv]; pv
0x18001a0b6  call    cs:__imp_CoTaskMemFree
0x18001a0bc  mov     eax, ebx
0x18001a0be  jmp     short loc_18001A0C5
0x18001a0c0  mov     eax, 80004003h
0x18001a0c5  mov     rcx, [rbp+57h+var_40]
0x18001a0c9  xor     rcx, rsp; StackCookie
0x18001a0cc  call    __security_check_cookie
0x18001a0d1  mov     rbx, [rsp+0C0h+arg_8]
0x18001a0d9  add     rsp, 90h
0x18001a0e0  pop     r15
0x18001a0e2  pop     r14
0x18001a0e4  pop     r13
0x18001a0e6  pop     r12
0x18001a0e8  pop     rdi
0x18001a0e9  pop     rsi
0x18001a0ea  pop     rbp
0x18001a0eb  retn
```
