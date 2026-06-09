# ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)

- ea: `0x18000fe68`
- end: `0x180010109`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z`
- size: `673`
- prototype: `int(ATL::CRegParser *__hidden this, wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001024c`

## callees

- `0x180002af0`
- `0x18000ea04`
- `0x18000f3b0`
- `0x18000f558`
- `0x18000fb5c`
- `0x18000fe68`
- `0x180010ce4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000ffb4`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000ffb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ffd2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ffd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010027`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010027`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000ff44`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010071`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001008d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000ff44`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010071`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001008d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000fff9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000fff9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000feef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000feef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ff10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800100cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ff10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800100cc`

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
0x18000fe68  mov     [rsp-8+arg_8], rbx
0x18000fe6d  push    rbp
0x18000fe6e  push    rsi
0x18000fe6f  push    rdi
0x18000fe70  push    r12
0x18000fe72  push    r13
0x18000fe74  push    r14
0x18000fe76  push    r15
0x18000fe78  lea     rbp, [rsp-27h]
0x18000fe7d  sub     rsp, 90h
0x18000fe84  mov     rax, cs:__security_cookie
0x18000fe8b  xor     rax, rsp
0x18000fe8e  mov     [rbp+57h+var_40], rax
0x18000fe92  mov     r15, r8
0x18000fe95  mov     rbx, rdx
0x18000fe98  mov     rdi, rcx
0x18000fe9b  xor     r13d, r13d
0x18000fe9e  test    rdx, rdx
0x18000fea1  jz      loc_1800100DC
0x18000fea7  test    r8, r8
0x18000feaa  jz      loc_1800100DC
0x18000feb0  mov     [r8], r13
0x18000feb3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000feb7  inc     rax
0x18000feba  cmp     [rdx+rax*2], r13w
0x18000febf  jnz     short loc_18000FEB7
0x18000fec1  add     eax, eax
0x18000fec3  mov     ecx, 3E8h
0x18000fec8  cmp     eax, 64h ; 'd'
0x18000fecb  cmovl   eax, ecx
0x18000fece  mov     [rbp+57h+var_A0], r13d
0x18000fed2  mov     [rbp+57h+var_9C], eax
0x18000fed5  mov     ecx, eax
0x18000fed7  add     rcx, rcx
0x18000feda  mov     eax, 0FFFFFFFFh
0x18000fedf  cmp     rcx, rax
0x18000fee2  jbe     short loc_18000FEED
0x18000fee4  mov     rax, r13
0x18000fee7  mov     [rbp+57h+pv], r13
0x18000feeb  jmp     short loc_18000FF08
0x18000feed  mov     ecx, ecx; cb
0x18000feef  call    cs:__imp_CoTaskMemAlloc
0x18000fef6  nop     dword ptr [rax+rax+00h]
0x18000fefb  mov     [rbp+57h+pv], rax
0x18000feff  test    rax, rax
0x18000ff02  jz      short loc_18000FF08
0x18000ff04  mov     [rax], r13w
0x18000ff08  test    rax, rax
0x18000ff0b  jnz     short loc_18000FF26
0x18000ff0d  mov     rcx, rax; pv
0x18000ff10  call    cs:__imp_CoTaskMemFree
0x18000ff17  nop     dword ptr [rax+rax+00h]
0x18000ff1c  mov     eax, 8007000Eh
0x18000ff21  jmp     loc_1800100E1
0x18000ff26  mov     [rdi], rbx
0x18000ff29  mov     esi, 25h ; '%'
0x18000ff2e  cmp     [rbx], r13w
0x18000ff32  jz      loc_1800100BA
0x18000ff38  cmp     [rbx], si
0x18000ff3b  jnz     loc_1800100A4
0x18000ff41  mov     rcx, rbx; lpsz
0x18000ff44  call    cs:__imp_CharNextW
0x18000ff4b  nop     dword ptr [rax+rax+00h]
0x18000ff50  mov     [rdi], rax
0x18000ff53  cmp     [rax], si
0x18000ff56  jnz     short loc_18000FF7C
0x18000ff58  mov     rdx, rax; wchar_t *
0x18000ff5b  mov     r8d, 1; int
0x18000ff61  lea     rcx, [rbp+57h+var_A0]; this
0x18000ff65  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x18000ff6a  test    eax, eax
0x18000ff6c  jnz     loc_18001008A
0x18000ff72  mov     ebx, 8007000Eh
0x18000ff77  jmp     loc_1800100C8
0x18000ff7c  mov     edx, esi; wchar_t
0x18000ff7e  mov     rcx, rax; lpsz
0x18000ff81  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x18000ff86  mov     rsi, rax
0x18000ff89  test    rax, rax
0x18000ff8c  jz      loc_1800100B3
0x18000ff92  mov     rcx, rax
0x18000ff95  sub     rcx, [rdi]
0x18000ff98  sar     rcx, 1
0x18000ff9b  cmp     rcx, 1Fh
0x18000ff9f  jg      loc_1800100AC
0x18000ffa5  movsxd  r9, ecx
0x18000ffa8  mov     r8, [rdi]
0x18000ffab  mov     edx, 20h ; ' '
0x18000ffb0  lea     rcx, [rbp+57h+String2]
0x18000ffb4  call    cs:__imp__o_wcsncpy_s
0x18000ffbb  nop     dword ptr [rax+rax+00h]
0x18000ffc0  mov     ecx, eax; int
0x18000ffc2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000ffc7  mov     rbx, [rdi+8]
0x18000ffcb  lea     r12, [rbx+20h]
0x18000ffcf  mov     rcx, r12; lpCriticalSection
0x18000ffd2  call    cs:__imp_EnterCriticalSection
0x18000ffd9  nop     dword ptr [rax+rax+00h]
0x18000ffde  lea     r14, [rbx+8]
0x18000ffe2  mov     ebx, r13d
0x18000ffe5  cmp     ebx, [r14+10h]
0x18000ffe9  jge     short loc_180010021
0x18000ffeb  movsxd  rax, ebx
0x18000ffee  mov     rcx, [r14]
0x18000fff1  lea     rdx, [rbp+57h+String2]; lpString2
0x18000fff5  mov     rcx, [rcx+rax*8]; lpString1
0x18000fff9  call    cs:__imp_lstrcmpiW
0x180010000  nop     dword ptr [rax+rax+00h]
0x180010005  test    eax, eax
0x180010007  jz      short loc_18001000D
0x180010009  inc     ebx
0x18001000b  jmp     short loc_18000FFE5
0x18001000d  cmp     ebx, 0FFFFFFFFh
0x180010010  jz      short loc_180010021
0x180010012  mov     edx, ebx
0x180010014  mov     rcx, r14
0x180010017  call    ?GetValueAt@?$CSimpleMap@PEA_WPEA_WVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEA_WH@Z; ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18001001c  mov     rbx, [rax]
0x18001001f  jmp     short loc_180010024
0x180010021  mov     rbx, r13
0x180010024  mov     rcx, r12; lpCriticalSection
0x180010027  call    cs:__imp_LeaveCriticalSection
0x18001002e  nop     dword ptr [rax+rax+00h]
0x180010033  test    rbx, rbx
0x180010036  jz      short loc_1800100B3
0x180010038  mov     [rbp+57h+var_90], r13
0x18001003c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010040  inc     r8; int
0x180010043  cmp     [rbx+r8*2], r13w
0x180010048  jnz     short loc_180010040
0x18001004a  mov     rdx, rbx; wchar_t *
0x18001004d  lea     rcx, [rbp+57h+var_A0]; this
0x180010051  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x180010056  mov     ebx, eax
0x180010058  lea     rcx, [rbp+57h+var_90]
0x18001005c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180010061  test    ebx, ebx
0x180010063  jz      loc_18000FF72
0x180010069  mov     rax, [rdi]
0x18001006c  jmp     short loc_180010080
0x18001006e  mov     rcx, rax; lpsz
0x180010071  call    cs:__imp_CharNextW
0x180010078  nop     dword ptr [rax+rax+00h]
0x18001007d  mov     [rdi], rax
0x180010080  cmp     rax, rsi
0x180010083  jnz     short loc_18001006E
0x180010085  mov     esi, 25h ; '%'
0x18001008a  mov     rcx, [rdi]; lpsz
0x18001008d  call    cs:__imp_CharNextW
0x180010094  nop     dword ptr [rax+rax+00h]
0x180010099  mov     rbx, rax
0x18001009c  mov     [rdi], rax
0x18001009f  jmp     loc_18000FF2E
0x1800100a4  mov     rdx, rbx
0x1800100a7  jmp     loc_18000FF5B
0x1800100ac  mov     ebx, 80004005h
0x1800100b1  jmp     short loc_1800100C8
0x1800100b3  mov     ebx, 80020009h
0x1800100b8  jmp     short loc_1800100C8
0x1800100ba  mov     ebx, r13d
0x1800100bd  mov     rcx, [rbp+57h+pv]
0x1800100c1  mov     [rbp+57h+pv], r13
0x1800100c5  mov     [r15], rcx
0x1800100c8  mov     rcx, [rbp+57h+pv]; pv
0x1800100cc  call    cs:__imp_CoTaskMemFree
0x1800100d3  nop     dword ptr [rax+rax+00h]
0x1800100d8  mov     eax, ebx
0x1800100da  jmp     short loc_1800100E1
0x1800100dc  mov     eax, 80004003h
0x1800100e1  mov     rcx, [rbp+57h+var_40]
0x1800100e5  xor     rcx, rsp; StackCookie
0x1800100e8  call    __security_check_cookie
0x1800100ed  mov     rbx, [rsp+0C0h+arg_8]
0x1800100f5  add     rsp, 90h
0x1800100fc  pop     r15
0x1800100fe  pop     r14
0x180010100  pop     r13
0x180010102  pop     r12
0x180010104  pop     rdi
0x180010105  pop     rsi
0x180010106  pop     rbp
0x180010107  retn
```
