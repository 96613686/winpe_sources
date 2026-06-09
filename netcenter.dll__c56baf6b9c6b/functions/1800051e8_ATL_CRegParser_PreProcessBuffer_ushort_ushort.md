# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800051e8`
- end: `0x18000544c`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `612`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800055ec`

## callees

- `0x180002270`
- `0x180003ee8`
- `0x1800049d8`
- `0x180004aa0`
- `0x180004efc`
- `0x1800051e8`
- `0x180006040`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180005322`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180005322`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000533a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000533a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005383`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005383`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000528a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005416`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000528a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005416`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000526f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000526f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800052b8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800053c7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800053dd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800052b8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800053c7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800053dd`
- `KERNEL32!lstrcmpiW` at `0x18000535b`
- `KERNEL32!lstrcmpiW` at `0x18000535b`

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
0x1800051e8  mov     [rsp-8+arg_8], rbx
0x1800051ed  push    rbp
0x1800051ee  push    rsi
0x1800051ef  push    rdi
0x1800051f0  push    r12
0x1800051f2  push    r13
0x1800051f4  push    r14
0x1800051f6  push    r15
0x1800051f8  lea     rbp, [rsp-27h]
0x1800051fd  sub     rsp, 90h
0x180005204  mov     rax, cs:__security_cookie
0x18000520b  xor     rax, rsp
0x18000520e  mov     [rbp+57h+var_40], rax
0x180005212  mov     r15, r8
0x180005215  mov     rbx, rdx
0x180005218  mov     rdi, rcx
0x18000521b  xor     r13d, r13d
0x18000521e  test    rdx, rdx
0x180005221  jz      loc_180005420
0x180005227  test    r8, r8
0x18000522a  jz      loc_180005420
0x180005230  mov     [r8], r13
0x180005233  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005237  inc     rax
0x18000523a  cmp     [rdx+rax*2], r13w
0x18000523f  jnz     short loc_180005237
0x180005241  add     eax, eax
0x180005243  mov     ecx, 3E8h
0x180005248  cmp     eax, 64h ; 'd'
0x18000524b  cmovl   eax, ecx
0x18000524e  mov     [rbp+57h+var_A0], r13d
0x180005252  mov     [rbp+57h+var_9C], eax
0x180005255  mov     ecx, eax
0x180005257  add     rcx, rcx
0x18000525a  mov     eax, 0FFFFFFFFh
0x18000525f  cmp     rcx, rax
0x180005262  jbe     short loc_18000526D
0x180005264  mov     rax, r13
0x180005267  mov     [rbp+57h+pv], r13
0x18000526b  jmp     short loc_180005282
0x18000526d  mov     ecx, ecx; cb
0x18000526f  call    cs:__imp_CoTaskMemAlloc
0x180005275  mov     [rbp+57h+pv], rax
0x180005279  test    rax, rax
0x18000527c  jz      short loc_180005282
0x18000527e  mov     [rax], r13w
0x180005282  test    rax, rax
0x180005285  jnz     short loc_18000529A
0x180005287  mov     rcx, rax; pv
0x18000528a  call    cs:__imp_CoTaskMemFree
0x180005290  mov     eax, 8007000Eh
0x180005295  jmp     loc_180005425
0x18000529a  mov     [rdi], rbx
0x18000529d  mov     esi, 25h ; '%'
0x1800052a2  cmp     [rbx], r13w
0x1800052a6  jz      loc_180005404
0x1800052ac  cmp     [rbx], si
0x1800052af  jnz     loc_1800053EE
0x1800052b5  mov     rcx, rbx; lpsz
0x1800052b8  call    cs:__imp_CharNextW
0x1800052be  mov     [rdi], rax
0x1800052c1  cmp     [rax], si
0x1800052c4  jnz     short loc_1800052EA
0x1800052c6  mov     rdx, rax; unsigned __int16 *
0x1800052c9  mov     r8d, 1; int
0x1800052cf  lea     rcx, [rbp+57h+var_A0]; this
0x1800052d3  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800052d8  test    eax, eax
0x1800052da  jnz     loc_1800053DA
0x1800052e0  mov     ebx, 8007000Eh
0x1800052e5  jmp     loc_180005412
0x1800052ea  mov     edx, esi; unsigned __int16
0x1800052ec  mov     rcx, rax; lpsz
0x1800052ef  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800052f4  mov     rsi, rax
0x1800052f7  test    rax, rax
0x1800052fa  jz      loc_1800053FD
0x180005300  mov     rcx, rax
0x180005303  sub     rcx, [rdi]
0x180005306  sar     rcx, 1
0x180005309  cmp     rcx, 1Fh
0x18000530d  jg      loc_1800053F6
0x180005313  movsxd  r9, ecx
0x180005316  mov     r8, [rdi]
0x180005319  mov     edx, 20h ; ' '
0x18000531e  lea     rcx, [rbp+57h+String2]
0x180005322  call    cs:__imp__o_wcsncpy_s
0x180005328  mov     ecx, eax; int
0x18000532a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000532f  mov     rbx, [rdi+8]
0x180005333  lea     r12, [rbx+20h]
0x180005337  mov     rcx, r12; lpCriticalSection
0x18000533a  call    cs:__imp_EnterCriticalSection
0x180005340  lea     r14, [rbx+8]
0x180005344  mov     ebx, r13d
0x180005347  cmp     ebx, [r14+10h]
0x18000534b  jge     short loc_18000537D
0x18000534d  movsxd  rax, ebx
0x180005350  mov     rcx, [r14]
0x180005353  lea     rdx, [rbp+57h+String2]; lpString2
0x180005357  mov     rcx, [rcx+rax*8]; lpString1
0x18000535b  call    cs:__imp_lstrcmpiW
0x180005361  test    eax, eax
0x180005363  jz      short loc_180005369
0x180005365  inc     ebx
0x180005367  jmp     short loc_180005347
0x180005369  cmp     ebx, 0FFFFFFFFh
0x18000536c  jz      short loc_18000537D
0x18000536e  mov     edx, ebx
0x180005370  mov     rcx, r14
0x180005373  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180005378  mov     rbx, [rax]
0x18000537b  jmp     short loc_180005380
0x18000537d  mov     rbx, r13
0x180005380  mov     rcx, r12; lpCriticalSection
0x180005383  call    cs:__imp_LeaveCriticalSection
0x180005389  test    rbx, rbx
0x18000538c  jz      short loc_1800053FD
0x18000538e  mov     [rbp+57h+var_90], r13
0x180005392  or      r8, 0FFFFFFFFFFFFFFFFh
0x180005396  inc     r8; int
0x180005399  cmp     [rbx+r8*2], r13w
0x18000539e  jnz     short loc_180005396
0x1800053a0  mov     rdx, rbx; unsigned __int16 *
0x1800053a3  lea     rcx, [rbp+57h+var_A0]; this
0x1800053a7  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800053ac  mov     ebx, eax
0x1800053ae  lea     rcx, [rbp+57h+var_90]
0x1800053b2  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800053b7  test    ebx, ebx
0x1800053b9  jz      loc_1800052E0
0x1800053bf  mov     rax, [rdi]
0x1800053c2  jmp     short loc_1800053D0
0x1800053c4  mov     rcx, rax; lpsz
0x1800053c7  call    cs:__imp_CharNextW
0x1800053cd  mov     [rdi], rax
0x1800053d0  cmp     rax, rsi
0x1800053d3  jnz     short loc_1800053C4
0x1800053d5  mov     esi, 25h ; '%'
0x1800053da  mov     rcx, [rdi]; lpsz
0x1800053dd  call    cs:__imp_CharNextW
0x1800053e3  mov     rbx, rax
0x1800053e6  mov     [rdi], rax
0x1800053e9  jmp     loc_1800052A2
0x1800053ee  mov     rdx, rbx
0x1800053f1  jmp     loc_1800052C9
0x1800053f6  mov     ebx, 80004005h
0x1800053fb  jmp     short loc_180005412
0x1800053fd  mov     ebx, 80020009h
0x180005402  jmp     short loc_180005412
0x180005404  mov     ebx, r13d
0x180005407  mov     rcx, [rbp+57h+pv]
0x18000540b  mov     [rbp+57h+pv], r13
0x18000540f  mov     [r15], rcx
0x180005412  mov     rcx, [rbp+57h+pv]; pv
0x180005416  call    cs:__imp_CoTaskMemFree
0x18000541c  mov     eax, ebx
0x18000541e  jmp     short loc_180005425
0x180005420  mov     eax, 80004003h
0x180005425  mov     rcx, [rbp+57h+var_40]
0x180005429  xor     rcx, rsp; StackCookie
0x18000542c  call    __security_check_cookie
0x180005431  mov     rbx, [rsp+0C0h+arg_8]
0x180005439  add     rsp, 90h
0x180005440  pop     r15
0x180005442  pop     r14
0x180005444  pop     r13
0x180005446  pop     r12
0x180005448  pop     rdi
0x180005449  pop     rsi
0x18000544a  pop     rbp
0x18000544b  retn
```
