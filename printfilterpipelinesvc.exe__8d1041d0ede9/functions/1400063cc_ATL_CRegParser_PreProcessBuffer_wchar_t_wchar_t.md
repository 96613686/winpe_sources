# ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)

- ea: `0x1400063cc`
- end: `0x140006630`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z`
- size: `612`
- prototype: `int(ATL::CRegParser *__hidden this, wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400067cc`

## callees

- `0x140002070`
- `0x140004528`
- `0x140005110`
- `0x1400052a0`
- `0x140005c7c`
- `0x1400063cc`
- `0x140007584`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x14000653f`
- `KERNEL32!lstrcmpiW` at `0x14000653f`
- `KERNEL32!LeaveCriticalSection` at `0x140006567`
- `KERNEL32!LeaveCriticalSection` at `0x140006567`
- `KERNEL32!EnterCriticalSection` at `0x14000651e`
- `KERNEL32!EnterCriticalSection` at `0x14000651e`
- `USER32!CharNextW` at `0x14000649c`
- `USER32!CharNextW` at `0x1400065ab`
- `USER32!CharNextW` at `0x1400065c1`
- `USER32!CharNextW` at `0x14000649c`
- `USER32!CharNextW` at `0x1400065ab`
- `USER32!CharNextW` at `0x1400065c1`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140006506`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140006506`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140006453`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140006453`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000646e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400065fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000646e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400065fa`

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
0x1400063cc  mov     [rsp-8+arg_8], rbx
0x1400063d1  push    rbp
0x1400063d2  push    rsi
0x1400063d3  push    rdi
0x1400063d4  push    r12
0x1400063d6  push    r13
0x1400063d8  push    r14
0x1400063da  push    r15
0x1400063dc  lea     rbp, [rsp-27h]
0x1400063e1  sub     rsp, 90h
0x1400063e8  mov     rax, cs:__security_cookie
0x1400063ef  xor     rax, rsp
0x1400063f2  mov     [rbp+57h+var_40], rax
0x1400063f6  mov     r15, r8
0x1400063f9  mov     rbx, rdx
0x1400063fc  mov     rdi, rcx
0x1400063ff  xor     r13d, r13d
0x140006402  test    rdx, rdx
0x140006405  jz      loc_140006604
0x14000640b  test    r8, r8
0x14000640e  jz      loc_140006604
0x140006414  mov     [r8], r13
0x140006417  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000641b  inc     rax
0x14000641e  cmp     [rdx+rax*2], r13w
0x140006423  jnz     short loc_14000641B
0x140006425  add     eax, eax
0x140006427  mov     ecx, 3E8h
0x14000642c  cmp     eax, 64h ; 'd'
0x14000642f  cmovl   eax, ecx
0x140006432  mov     [rbp+57h+var_A0], r13d
0x140006436  mov     [rbp+57h+var_9C], eax
0x140006439  mov     ecx, eax
0x14000643b  add     rcx, rcx
0x14000643e  mov     eax, 0FFFFFFFFh
0x140006443  cmp     rcx, rax
0x140006446  jbe     short loc_140006451
0x140006448  mov     rax, r13
0x14000644b  mov     [rbp+57h+pv], r13
0x14000644f  jmp     short loc_140006466
0x140006451  mov     ecx, ecx; cb
0x140006453  call    cs:__imp_CoTaskMemAlloc
0x140006459  mov     [rbp+57h+pv], rax
0x14000645d  test    rax, rax
0x140006460  jz      short loc_140006466
0x140006462  mov     [rax], r13w
0x140006466  test    rax, rax
0x140006469  jnz     short loc_14000647E
0x14000646b  mov     rcx, rax; pv
0x14000646e  call    cs:__imp_CoTaskMemFree
0x140006474  mov     eax, 8007000Eh
0x140006479  jmp     loc_140006609
0x14000647e  mov     [rdi], rbx
0x140006481  mov     esi, 25h ; '%'
0x140006486  cmp     [rbx], r13w
0x14000648a  jz      loc_1400065E8
0x140006490  cmp     [rbx], si
0x140006493  jnz     loc_1400065D2
0x140006499  mov     rcx, rbx; lpsz
0x14000649c  call    cs:__imp_CharNextW
0x1400064a2  mov     [rdi], rax
0x1400064a5  cmp     [rax], si
0x1400064a8  jnz     short loc_1400064CE
0x1400064aa  mov     rdx, rax; wchar_t *
0x1400064ad  mov     r8d, 1; int
0x1400064b3  lea     rcx, [rbp+57h+var_A0]; this
0x1400064b7  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x1400064bc  test    eax, eax
0x1400064be  jnz     loc_1400065BE
0x1400064c4  mov     ebx, 8007000Eh
0x1400064c9  jmp     loc_1400065F6
0x1400064ce  mov     edx, esi; wchar_t
0x1400064d0  mov     rcx, rax; lpsz
0x1400064d3  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x1400064d8  mov     rsi, rax
0x1400064db  test    rax, rax
0x1400064de  jz      loc_1400065E1
0x1400064e4  mov     rcx, rax
0x1400064e7  sub     rcx, [rdi]
0x1400064ea  sar     rcx, 1
0x1400064ed  cmp     rcx, 1Fh
0x1400064f1  jg      loc_1400065DA
0x1400064f7  movsxd  r9, ecx
0x1400064fa  mov     r8, [rdi]
0x1400064fd  mov     edx, 20h ; ' '
0x140006502  lea     rcx, [rbp+57h+String2]
0x140006506  call    cs:__imp__o_wcsncpy_s
0x14000650c  mov     ecx, eax; int
0x14000650e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x140006513  mov     rbx, [rdi+8]
0x140006517  lea     r12, [rbx+20h]
0x14000651b  mov     rcx, r12; lpCriticalSection
0x14000651e  call    cs:__imp_EnterCriticalSection
0x140006524  lea     r14, [rbx+8]
0x140006528  mov     ebx, r13d
0x14000652b  cmp     ebx, [r14+10h]
0x14000652f  jge     short loc_140006561
0x140006531  movsxd  rax, ebx
0x140006534  mov     rcx, [r14]
0x140006537  lea     rdx, [rbp+57h+String2]; lpString2
0x14000653b  mov     rcx, [rcx+rax*8]; lpString1
0x14000653f  call    cs:__imp_lstrcmpiW
0x140006545  test    eax, eax
0x140006547  jz      short loc_14000654D
0x140006549  inc     ebx
0x14000654b  jmp     short loc_14000652B
0x14000654d  cmp     ebx, 0FFFFFFFFh
0x140006550  jz      short loc_140006561
0x140006552  mov     edx, ebx
0x140006554  mov     rcx, r14
0x140006557  call    ?GetValueAt@?$CSimpleMap@PEA_WPEA_WVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEA_WH@Z; ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x14000655c  mov     rbx, [rax]
0x14000655f  jmp     short loc_140006564
0x140006561  mov     rbx, r13
0x140006564  mov     rcx, r12; lpCriticalSection
0x140006567  call    cs:__imp_LeaveCriticalSection
0x14000656d  test    rbx, rbx
0x140006570  jz      short loc_1400065E1
0x140006572  mov     [rbp+57h+var_90], r13
0x140006576  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000657a  inc     r8; int
0x14000657d  cmp     [rbx+r8*2], r13w
0x140006582  jnz     short loc_14000657A
0x140006584  mov     rdx, rbx; wchar_t *
0x140006587  lea     rcx, [rbp+57h+var_A0]; this
0x14000658b  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x140006590  mov     ebx, eax
0x140006592  lea     rcx, [rbp+57h+var_90]
0x140006596  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x14000659b  test    ebx, ebx
0x14000659d  jz      loc_1400064C4
0x1400065a3  mov     rax, [rdi]
0x1400065a6  jmp     short loc_1400065B4
0x1400065a8  mov     rcx, rax; lpsz
0x1400065ab  call    cs:__imp_CharNextW
0x1400065b1  mov     [rdi], rax
0x1400065b4  cmp     rax, rsi
0x1400065b7  jnz     short loc_1400065A8
0x1400065b9  mov     esi, 25h ; '%'
0x1400065be  mov     rcx, [rdi]; lpsz
0x1400065c1  call    cs:__imp_CharNextW
0x1400065c7  mov     rbx, rax
0x1400065ca  mov     [rdi], rax
0x1400065cd  jmp     loc_140006486
0x1400065d2  mov     rdx, rbx
0x1400065d5  jmp     loc_1400064AD
0x1400065da  mov     ebx, 80004005h
0x1400065df  jmp     short loc_1400065F6
0x1400065e1  mov     ebx, 80020009h
0x1400065e6  jmp     short loc_1400065F6
0x1400065e8  mov     ebx, r13d
0x1400065eb  mov     rcx, [rbp+57h+pv]
0x1400065ef  mov     [rbp+57h+pv], r13
0x1400065f3  mov     [r15], rcx
0x1400065f6  mov     rcx, [rbp+57h+pv]; pv
0x1400065fa  call    cs:__imp_CoTaskMemFree
0x140006600  mov     eax, ebx
0x140006602  jmp     short loc_140006609
0x140006604  mov     eax, 80004003h
0x140006609  mov     rcx, [rbp+57h+var_40]
0x14000660d  xor     rcx, rsp; StackCookie
0x140006610  call    __security_check_cookie
0x140006615  mov     rbx, [rsp+0C0h+arg_8]
0x14000661d  add     rsp, 90h
0x140006624  pop     r15
0x140006626  pop     r14
0x140006628  pop     r13
0x14000662a  pop     r12
0x14000662c  pop     rdi
0x14000662d  pop     rsi
0x14000662e  pop     rbp
0x14000662f  retn
```
