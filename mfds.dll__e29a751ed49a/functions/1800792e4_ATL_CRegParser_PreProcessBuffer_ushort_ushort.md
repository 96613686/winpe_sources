# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800792e4`
- end: `0x18007957f`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `667`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007976c`

## callees

- `0x180029314`
- `0x180074160`
- `0x180076b00`
- `0x18007769c`
- `0x180078f54`
- `0x1800792e4`
- `0x18007a8dc`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180079332`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800794b1`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180079332`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800794b1`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180079426`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180079426`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079499`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079499`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180079444`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180079444`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079367`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079542`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079367`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079542`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007937f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007937f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800793b6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800794e7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180079503`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800793b6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800794e7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180079503`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007946b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007946b`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(ATL::CRegParser *this, unsigned __int16 *a2, LPVOID *a3)
{
  LPWSTR v4; // rbx
  int v6; // eax
  unsigned __int64 v7; // rcx
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
  const wchar_t *v21; // rbx
  int v22; // eax
  int v23; // ebx
  const WCHAR *j; // rax
  __int64 v25; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v27; // [rsp+30h] [rbp-39h] BYREF
  WCHAR String2[32]; // [rsp+40h] [rbp-29h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  LODWORD(v25) = 0;
  v6 = 2 * wcslen(a2);
  if ( v6 < 100 )
    v6 = 1000;
  HIDWORD(v25) = v6;
  v7 = 2LL * (unsigned int)v6;
  if ( v7 > 0xFFFFFFFF )
  {
    v8 = 0;
LABEL_7:
    CoTaskMemFree(v8);
    return 2147942414LL;
  }
  v8 = CoTaskMemAlloc((unsigned int)v7);
  pv = v8;
  if ( !v8 )
    goto LABEL_7;
  *v8 = 0;
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v11 = v4;
LABEL_14:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v25, v11, 1) )
        goto LABEL_15;
      goto LABEL_30;
    }
    v10 = CharNextW(v4);
    *(_QWORD *)this = v10;
    if ( *v10 == 37 )
    {
      v11 = v10;
      goto LABEL_14;
    }
    v13 = ATL::CRegParser::StrChrW(v10, 0x25u);
    v14 = v13;
    if ( !v13 )
      goto LABEL_33;
    v15 = ((__int64)v13 - *(_QWORD *)this) >> 1;
    if ( v15 > 31 )
    {
      v12 = -2147467259;
      goto LABEL_35;
    }
    v16 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v15, v25);
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
          v21 = *(const wchar_t **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                     v19,
                                     i);
          goto LABEL_25;
        }
        break;
      }
    }
    v21 = 0;
LABEL_25:
    LeaveCriticalSection(v18);
    if ( !v21 )
    {
LABEL_33:
      v12 = -2147352567;
      goto LABEL_35;
    }
    v27 = 0;
    v22 = wcslen(v21);
    v23 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v25, v21, v22);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v27);
    if ( !v23 )
    {
LABEL_15:
      v12 = -2147024882;
      goto LABEL_35;
    }
    for ( j = *(const WCHAR **)this; j != v14; *(_QWORD *)this = j )
      j = CharNextW(j);
LABEL_30:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
  }
  v12 = 0;
  *a3 = pv;
  pv = 0;
LABEL_35:
  CoTaskMemFree(pv);
  return v12;
}

```

## disassembly

```asm
0x1800792e4  mov     [rsp-8+arg_18], rbx
0x1800792e9  push    rbp
0x1800792ea  push    rsi
0x1800792eb  push    rdi
0x1800792ec  push    r12
0x1800792ee  push    r13
0x1800792f0  push    r14
0x1800792f2  push    r15
0x1800792f4  lea     rbp, [rsp-27h]
0x1800792f9  sub     rsp, 90h
0x180079300  mov     rax, cs:__security_cookie
0x180079307  xor     rax, rsp
0x18007930a  mov     [rbp+57h+var_40], rax
0x18007930e  xor     r13d, r13d
0x180079311  mov     r15, r8
0x180079314  mov     rbx, rdx
0x180079317  mov     rdi, rcx
0x18007931a  test    rdx, rdx
0x18007931d  jz      loc_180079552
0x180079323  test    r8, r8
0x180079326  jz      loc_180079552
0x18007932c  mov     rcx, rdx; String
0x18007932f  mov     [r8], r13
0x180079332  call    cs:__imp_wcslen
0x180079339  nop     dword ptr [rax+rax+00h]
0x18007933e  mov     ecx, 3E8h
0x180079343  mov     [rbp+57h+var_A0], r13d
0x180079347  add     eax, eax
0x180079349  cmp     eax, 64h ; 'd'
0x18007934c  cmovl   eax, ecx
0x18007934f  mov     ecx, eax
0x180079351  mov     [rbp+57h+var_9C], eax
0x180079354  add     rcx, rcx
0x180079357  mov     eax, 0FFFFFFFFh
0x18007935c  cmp     rcx, rax
0x18007935f  jbe     short loc_18007937D
0x180079361  mov     eax, r13d
0x180079364  mov     rcx, rax; pv
0x180079367  call    cs:__imp_CoTaskMemFree
0x18007936e  nop     dword ptr [rax+rax+00h]
0x180079373  mov     eax, 8007000Eh
0x180079378  jmp     loc_180079557
0x18007937d  mov     ecx, ecx; cb
0x18007937f  call    cs:__imp_CoTaskMemAlloc
0x180079386  nop     dword ptr [rax+rax+00h]
0x18007938b  mov     [rbp+57h+pv], rax
0x18007938f  test    rax, rax
0x180079392  jz      short loc_180079364
0x180079394  mov     [rax], r13w
0x180079398  mov     esi, 25h ; '%'
0x18007939d  mov     [rdi], rbx
0x1800793a0  cmp     [rbx], r13w
0x1800793a4  jz      loc_180079530
0x1800793aa  cmp     [rbx], si
0x1800793ad  jnz     loc_18007951A
0x1800793b3  mov     rcx, rbx; lpsz
0x1800793b6  call    cs:__imp_CharNextW
0x1800793bd  nop     dword ptr [rax+rax+00h]
0x1800793c2  mov     [rdi], rax
0x1800793c5  cmp     [rax], si
0x1800793c8  jnz     short loc_1800793EE
0x1800793ca  mov     rdx, rax; unsigned __int16 *
0x1800793cd  mov     r8d, 1; int
0x1800793d3  lea     rcx, [rbp+57h+var_A0]; this
0x1800793d7  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800793dc  test    eax, eax
0x1800793de  jnz     loc_180079500
0x1800793e4  mov     ebx, 8007000Eh
0x1800793e9  jmp     loc_18007953E
0x1800793ee  mov     edx, esi; unsigned __int16
0x1800793f0  mov     rcx, rax; lpsz
0x1800793f3  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800793f8  mov     rsi, rax
0x1800793fb  test    rax, rax
0x1800793fe  jz      loc_180079529
0x180079404  mov     rcx, rax
0x180079407  sub     rcx, [rdi]
0x18007940a  sar     rcx, 1
0x18007940d  cmp     rcx, 1Fh
0x180079411  jg      loc_180079522
0x180079417  mov     r8, [rdi]
0x18007941a  mov     edx, 20h ; ' '
0x18007941f  movsxd  r9, ecx
0x180079422  lea     rcx, [rbp+57h+String2]
0x180079426  call    cs:__imp__o_wcsncpy_s
0x18007942d  nop     dword ptr [rax+rax+00h]
0x180079432  mov     ecx, eax; int
0x180079434  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180079439  mov     rbx, [rdi+8]
0x18007943d  lea     r12, [rbx+20h]
0x180079441  mov     rcx, r12; lpCriticalSection
0x180079444  call    cs:__imp_EnterCriticalSection
0x18007944b  nop     dword ptr [rax+rax+00h]
0x180079450  lea     r14, [rbx+8]
0x180079454  mov     ebx, r13d
0x180079457  cmp     ebx, [r14+10h]
0x18007945b  jge     short loc_180079493
0x18007945d  mov     rcx, [r14]
0x180079460  lea     rdx, [rbp+57h+String2]; lpString2
0x180079464  movsxd  rax, ebx
0x180079467  mov     rcx, [rcx+rax*8]; lpString1
0x18007946b  call    cs:__imp_lstrcmpiW
0x180079472  nop     dword ptr [rax+rax+00h]
0x180079477  test    eax, eax
0x180079479  jz      short loc_18007947F
0x18007947b  inc     ebx
0x18007947d  jmp     short loc_180079457
0x18007947f  cmp     ebx, 0FFFFFFFFh
0x180079482  jz      short loc_180079493
0x180079484  mov     edx, ebx
0x180079486  mov     rcx, r14
0x180079489  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18007948e  mov     rbx, [rax]
0x180079491  jmp     short loc_180079496
0x180079493  mov     rbx, r13
0x180079496  mov     rcx, r12; lpCriticalSection
0x180079499  call    cs:__imp_LeaveCriticalSection
0x1800794a0  nop     dword ptr [rax+rax+00h]
0x1800794a5  test    rbx, rbx
0x1800794a8  jz      short loc_180079529
0x1800794aa  mov     rcx, rbx; String
0x1800794ad  mov     [rbp+57h+var_90], r13
0x1800794b1  call    cs:__imp_wcslen
0x1800794b8  nop     dword ptr [rax+rax+00h]
0x1800794bd  mov     rdx, rbx; unsigned __int16 *
0x1800794c0  lea     rcx, [rbp+57h+var_A0]; this
0x1800794c4  mov     r8, rax; int
0x1800794c7  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800794cc  lea     rcx, [rbp+57h+var_90]
0x1800794d0  mov     ebx, eax
0x1800794d2  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800794d7  test    ebx, ebx
0x1800794d9  jz      loc_1800793E4
0x1800794df  mov     rax, [rdi]
0x1800794e2  jmp     short loc_1800794F6
0x1800794e4  mov     rcx, rax; lpsz
0x1800794e7  call    cs:__imp_CharNextW
0x1800794ee  nop     dword ptr [rax+rax+00h]
0x1800794f3  mov     [rdi], rax
0x1800794f6  cmp     rax, rsi
0x1800794f9  jnz     short loc_1800794E4
0x1800794fb  mov     esi, 25h ; '%'
0x180079500  mov     rcx, [rdi]; lpsz
0x180079503  call    cs:__imp_CharNextW
0x18007950a  nop     dword ptr [rax+rax+00h]
0x18007950f  mov     rbx, rax
0x180079512  mov     [rdi], rax
0x180079515  jmp     loc_1800793A0
0x18007951a  mov     rdx, rbx
0x18007951d  jmp     loc_1800793CD
0x180079522  mov     ebx, 80004005h
0x180079527  jmp     short loc_18007953E
0x180079529  mov     ebx, 80020009h
0x18007952e  jmp     short loc_18007953E
0x180079530  mov     rcx, [rbp+57h+pv]
0x180079534  mov     ebx, r13d
0x180079537  mov     [r15], rcx
0x18007953a  mov     [rbp+57h+pv], r13
0x18007953e  mov     rcx, [rbp+57h+pv]; pv
0x180079542  call    cs:__imp_CoTaskMemFree
0x180079549  nop     dword ptr [rax+rax+00h]
0x18007954e  mov     eax, ebx
0x180079550  jmp     short loc_180079557
0x180079552  mov     eax, 80004003h
0x180079557  mov     rcx, [rbp+57h+var_40]
0x18007955b  xor     rcx, rsp; StackCookie
0x18007955e  call    __security_check_cookie
0x180079563  mov     rbx, [rsp+0C0h+arg_18]
0x18007956b  add     rsp, 90h
0x180079572  pop     r15
0x180079574  pop     r14
0x180079576  pop     r13
0x180079578  pop     r12
0x18007957a  pop     rdi
0x18007957b  pop     rsi
0x18007957c  pop     rbp
0x18007957d  retn
```
