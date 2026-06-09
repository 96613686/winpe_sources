# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18005733c`
- end: `0x18005758e`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `594`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800577e4`

## callees

- `0x180051f30`
- `0x180054104`
- `0x180054c10`
- `0x180054d50`
- `0x18005733c`
- `0x180058c94`
- `0x180058cf4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18005747a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18005747a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180057424`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800574dc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18005750b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180057424`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800574dc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18005750b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800573ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005753b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800573ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005753b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800573c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800573c8`

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
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdx
  WCHAR v12; // ax
  LPWSTR v13; // rax
  const unsigned __int16 *v14; // rdx
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rsi
  __int64 v17; // rcx
  int v18; // eax
  const unsigned __int16 *v19; // rax
  __int64 v20; // r8
  int v21; // ebx
  const WCHAR *i; // rax
  unsigned int v23; // ebx
  __int64 v24; // [rsp+20h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-31h]
  __int64 v26; // [rsp+30h] [rbp-29h] BYREF
  unsigned __int16 v27[32]; // [rsp+40h] [rbp-19h] BYREF

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
  LODWORD(v24) = 0;
  HIDWORD(v24) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)v8);
    v10 = v9;
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    v10 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_31:
    v23 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_32;
  }
  while ( v12 != 37 )
  {
    v14 = v4;
LABEL_28:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v24, v14, 1) )
      goto LABEL_35;
LABEL_29:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v10 = (unsigned __int16 *)pv;
      goto LABEL_31;
    }
  }
  v13 = CharNextW(v4);
  *(_QWORD *)this = v13;
  if ( *v13 == 37 )
  {
    v14 = v13;
    goto LABEL_28;
  }
  v15 = ATL::CRegParser::StrChrW(v13, 0x25u);
  v16 = v15;
  if ( !v15 )
    goto LABEL_34;
  v17 = ((__int64)v15 - *(_QWORD *)this) >> 1;
  if ( v17 > 31 )
  {
    v23 = -2147467259;
    goto LABEL_32;
  }
  v18 = _o_wcsncpy_s(v27, 32, *(_QWORD *)this, (int)v17, v24);
  ATL::AtlCrtErrorCheck(v18);
  v19 = ATL::CRegObject::StrFromMap(*((ATL::CRegObject **)this + 1), v27);
  if ( !v19 )
  {
LABEL_34:
    v23 = -2147352567;
    goto LABEL_32;
  }
  v26 = 0;
  v20 = -1;
  do
    ++v20;
  while ( v19[v20] );
  v21 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v24, v19, v20);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v26);
  if ( v21 )
  {
    for ( i = *(const WCHAR **)this; i != v16; *(_QWORD *)this = i )
      i = CharNextW(i);
    goto LABEL_29;
  }
LABEL_35:
  v23 = -2147024882;
LABEL_32:
  CoTaskMemFree(pv);
  return v23;
}

```

## disassembly

```asm
0x18005733c  mov     [rsp-8+arg_8], rbx
0x180057341  mov     [rsp-8+arg_18], rsi
0x180057346  push    rbp
0x180057347  push    rdi
0x180057348  push    r12
0x18005734a  push    r14
0x18005734c  push    r15
0x18005734e  lea     rbp, [rsp-37h]
0x180057353  sub     rsp, 90h
0x18005735a  mov     rax, cs:__security_cookie
0x180057361  xor     rax, rsp
0x180057364  mov     [rbp+57h+var_30], rax
0x180057368  mov     r14, r8
0x18005736b  mov     rbx, rdx
0x18005736e  mov     rdi, rcx
0x180057371  xor     r15d, r15d
0x180057374  test    rdx, rdx
0x180057377  jz      loc_180057560
0x18005737d  test    r8, r8
0x180057380  jz      loc_180057560
0x180057386  mov     [r8], r15
0x180057389  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005738d  inc     rax
0x180057390  cmp     [rdx+rax*2], r15w
0x180057395  jnz     short loc_18005738D
0x180057397  add     eax, eax
0x180057399  mov     ecx, 3E8h
0x18005739e  cmp     eax, 64h ; 'd'
0x1800573a1  cmovl   eax, ecx
0x1800573a4  mov     [rbp+57h+var_90], r15d
0x1800573a8  mov     [rbp+57h+var_8C], eax
0x1800573ab  mov     ecx, eax
0x1800573ad  add     rcx, rcx
0x1800573b0  mov     eax, 0FFFFFFFFh
0x1800573b5  cmp     rcx, rax
0x1800573b8  jbe     short loc_1800573C6
0x1800573ba  mov     rax, r15
0x1800573bd  mov     rdx, r15
0x1800573c0  mov     [rbp+57h+pv], rdx
0x1800573c4  jmp     short loc_1800573E4
0x1800573c6  mov     ecx, ecx; cb
0x1800573c8  call    cs:__imp_CoTaskMemAlloc
0x1800573cf  nop     dword ptr [rax+rax+00h]
0x1800573d4  mov     rdx, rax
0x1800573d7  mov     [rbp+57h+pv], rax
0x1800573db  test    rax, rax
0x1800573de  jz      short loc_1800573E4
0x1800573e0  mov     [rax], r15w
0x1800573e4  test    rax, rax
0x1800573e7  jnz     short loc_180057402
0x1800573e9  mov     rcx, rax; pv
0x1800573ec  call    cs:__imp_CoTaskMemFree
0x1800573f3  nop     dword ptr [rax+rax+00h]
0x1800573f8  mov     eax, 8007000Eh
0x1800573fd  jmp     loc_180057565
0x180057402  mov     [rdi], rbx
0x180057405  movzx   eax, word ptr [rbx]
0x180057408  test    ax, ax
0x18005740b  jz      loc_18005752D
0x180057411  mov     r12d, 25h ; '%'
0x180057417  cmp     ax, r12w
0x18005741b  jnz     loc_1800574F2
0x180057421  mov     rcx, rbx; lpsz
0x180057424  call    cs:__imp_CharNextW
0x18005742b  nop     dword ptr [rax+rax+00h]
0x180057430  mov     [rdi], rax
0x180057433  cmp     [rax], r12w
0x180057437  jnz     short loc_180057441
0x180057439  mov     rdx, rax
0x18005743c  jmp     loc_1800574F5
0x180057441  mov     edx, r12d; unsigned __int16
0x180057444  mov     rcx, rax; lpsz
0x180057447  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18005744c  mov     rsi, rax
0x18005744f  test    rax, rax
0x180057452  jz      loc_180057552
0x180057458  mov     rcx, rax
0x18005745b  sub     rcx, [rdi]
0x18005745e  sar     rcx, 1
0x180057461  cmp     rcx, 1Fh
0x180057465  jg      loc_18005754B
0x18005746b  movsxd  r9, ecx
0x18005746e  mov     r8, [rdi]
0x180057471  mov     edx, 20h ; ' '
0x180057476  lea     rcx, [rbp+57h+var_70]
0x18005747a  call    cs:__imp__o_wcsncpy_s
0x180057481  nop     dword ptr [rax+rax+00h]
0x180057486  mov     ecx, eax; int
0x180057488  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18005748d  lea     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x180057491  mov     rcx, [rdi+8]; this
0x180057495  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x18005749a  test    rax, rax
0x18005749d  jz      loc_180057552
0x1800574a3  mov     [rbp+57h+var_80], r15
0x1800574a7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800574ab  inc     r8; int
0x1800574ae  cmp     [rax+r8*2], r15w
0x1800574b3  jnz     short loc_1800574AB
0x1800574b5  mov     rdx, rax; unsigned __int16 *
0x1800574b8  lea     rcx, [rbp+57h+var_90]; this
0x1800574bc  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800574c1  mov     ebx, eax
0x1800574c3  lea     rcx, [rbp+57h+var_80]
0x1800574c7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800574cc  test    ebx, ebx
0x1800574ce  jz      loc_180057559
0x1800574d4  mov     rax, [rdi]
0x1800574d7  jmp     short loc_1800574EB
0x1800574d9  mov     rcx, rax; lpsz
0x1800574dc  call    cs:__imp_CharNextW
0x1800574e3  nop     dword ptr [rax+rax+00h]
0x1800574e8  mov     [rdi], rax
0x1800574eb  cmp     rax, rsi
0x1800574ee  jnz     short loc_1800574D9
0x1800574f0  jmp     short loc_180057508
0x1800574f2  mov     rdx, rbx; unsigned __int16 *
0x1800574f5  mov     r8d, 1; int
0x1800574fb  lea     rcx, [rbp+57h+var_90]; this
0x1800574ff  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180057504  test    eax, eax
0x180057506  jz      short loc_180057559
0x180057508  mov     rcx, [rdi]; lpsz
0x18005750b  call    cs:__imp_CharNextW
0x180057512  nop     dword ptr [rax+rax+00h]
0x180057517  mov     rbx, rax
0x18005751a  mov     [rdi], rax
0x18005751d  movzx   eax, word ptr [rax]
0x180057520  test    ax, ax
0x180057523  jnz     loc_180057417
0x180057529  mov     rdx, [rbp+57h+pv]
0x18005752d  mov     ebx, r15d
0x180057530  mov     [rbp+57h+pv], r15
0x180057534  mov     [r14], rdx
0x180057537  mov     rcx, [rbp+57h+pv]; pv
0x18005753b  call    cs:__imp_CoTaskMemFree
0x180057542  nop     dword ptr [rax+rax+00h]
0x180057547  mov     eax, ebx
0x180057549  jmp     short loc_180057565
0x18005754b  mov     ebx, 80004005h
0x180057550  jmp     short loc_180057537
0x180057552  mov     ebx, 80020009h
0x180057557  jmp     short loc_180057537
0x180057559  mov     ebx, 8007000Eh
0x18005755e  jmp     short loc_180057537
0x180057560  mov     eax, 80004003h
0x180057565  mov     rcx, [rbp+57h+var_30]
0x180057569  xor     rcx, rsp; StackCookie
0x18005756c  call    __security_check_cookie
0x180057571  lea     r11, [rsp+0B0h+var_20]
0x180057579  mov     rbx, [r11+38h]
0x18005757d  mov     rsi, [r11+48h]
0x180057581  mov     rsp, r11
0x180057584  pop     r15
0x180057586  pop     r14
0x180057588  pop     r12
0x18005758a  pop     rdi
0x18005758b  pop     rbp
0x18005758c  retn
```
