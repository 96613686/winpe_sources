# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180012918`
- end: `0x180012b83`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `619`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800148d4`

## callees

- `0x180001710`
- `0x1800071a0`
- `0x18000a818`
- `0x18000a938`
- `0x180011454`
- `0x180012918`
- `0x180017510`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180012a59`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180012a59`
- `KERNEL32!lstrcmpiW` at `0x180012a92`
- `KERNEL32!lstrcmpiW` at `0x180012a92`
- `KERNEL32!LeaveCriticalSection` at `0x180012aba`
- `KERNEL32!LeaveCriticalSection` at `0x180012aba`
- `KERNEL32!EnterCriticalSection` at `0x180012a71`
- `KERNEL32!EnterCriticalSection` at `0x180012a71`
- `USER32!CharNextW` at `0x1800129ef`
- `USER32!CharNextW` at `0x180012afe`
- `USER32!CharNextW` at `0x180012b14`
- `USER32!CharNextW` at `0x1800129ef`
- `USER32!CharNextW` at `0x180012afe`
- `USER32!CharNextW` at `0x180012b14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800129a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800129a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800129c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012b4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800129c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012b4d`

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
  LPVOID pv[2]; // [rsp+20h] [rbp-49h] BYREF
  _QWORD *v28; // [rsp+30h] [rbp-39h] BYREF
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
  *(_OWORD *)pv = 0;
  if ( v7 < 100 )
    v7 = 1000;
  LODWORD(pv[0]) = 0;
  HIDWORD(pv[0]) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = CoTaskMemAlloc((unsigned int)v8);
    pv[1] = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    pv[1] = 0;
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
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)pv, v12, 1) )
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
    v17 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v16, pv[0]);
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
    v28 = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)pv, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v28);
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
  v26 = (unsigned __int16 *)pv[1];
  pv[1] = 0;
  *a3 = v26;
LABEL_41:
  CoTaskMemFree(pv[1]);
  return v13;
}

```

## disassembly

```asm
0x180012918  mov     [rsp-8+arg_8], rbx
0x18001291d  push    rbp
0x18001291e  push    rsi
0x18001291f  push    rdi
0x180012920  push    r12
0x180012922  push    r13
0x180012924  push    r14
0x180012926  push    r15
0x180012928  lea     rbp, [rsp-27h]
0x18001292d  sub     rsp, 90h
0x180012934  mov     rax, cs:__security_cookie
0x18001293b  xor     rax, rsp
0x18001293e  mov     [rbp+57h+var_40], rax
0x180012942  mov     r15, r8
0x180012945  mov     rbx, rdx
0x180012948  mov     rdi, rcx
0x18001294b  xor     r13d, r13d
0x18001294e  test    rdx, rdx
0x180012951  jz      loc_180012B57
0x180012957  test    r8, r8
0x18001295a  jz      loc_180012B57
0x180012960  mov     [r8], r13
0x180012963  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012967  inc     rax
0x18001296a  cmp     [rdx+rax*2], r13w
0x18001296f  jnz     short loc_180012967
0x180012971  add     eax, eax
0x180012973  xorps   xmm0, xmm0
0x180012976  movups  xmmword ptr [rbp+57h+pv], xmm0
0x18001297a  mov     ecx, 3E8h
0x18001297f  cmp     eax, 64h ; 'd'
0x180012982  cmovl   eax, ecx
0x180012985  mov     dword ptr [rbp+57h+pv], r13d
0x180012989  mov     dword ptr [rbp+57h+pv+4], eax
0x18001298c  mov     ecx, eax
0x18001298e  add     rcx, rcx
0x180012991  mov     eax, 0FFFFFFFFh
0x180012996  cmp     rcx, rax
0x180012999  jbe     short loc_1800129A4
0x18001299b  mov     rax, r13
0x18001299e  mov     [rbp+57h+pv+8], r13
0x1800129a2  jmp     short loc_1800129B9
0x1800129a4  mov     ecx, ecx; cb
0x1800129a6  call    cs:__imp_CoTaskMemAlloc
0x1800129ac  mov     [rbp+57h+pv+8], rax
0x1800129b0  test    rax, rax
0x1800129b3  jz      short loc_1800129B9
0x1800129b5  mov     [rax], r13w
0x1800129b9  test    rax, rax
0x1800129bc  jnz     short loc_1800129D1
0x1800129be  mov     rcx, rax; pv
0x1800129c1  call    cs:__imp_CoTaskMemFree
0x1800129c7  mov     eax, 8007000Eh
0x1800129cc  jmp     loc_180012B5C
0x1800129d1  mov     [rdi], rbx
0x1800129d4  mov     esi, 25h ; '%'
0x1800129d9  cmp     [rbx], r13w
0x1800129dd  jz      loc_180012B3B
0x1800129e3  cmp     [rbx], si
0x1800129e6  jnz     loc_180012B25
0x1800129ec  mov     rcx, rbx; lpsz
0x1800129ef  call    cs:__imp_CharNextW
0x1800129f5  mov     [rdi], rax
0x1800129f8  cmp     [rax], si
0x1800129fb  jnz     short loc_180012A21
0x1800129fd  mov     rdx, rax; unsigned __int16 *
0x180012a00  mov     r8d, 1; int
0x180012a06  lea     rcx, [rbp+57h+pv]; this
0x180012a0a  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180012a0f  test    eax, eax
0x180012a11  jnz     loc_180012B11
0x180012a17  mov     ebx, 8007000Eh
0x180012a1c  jmp     loc_180012B49
0x180012a21  mov     edx, esi; unsigned __int16
0x180012a23  mov     rcx, rax; lpsz
0x180012a26  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180012a2b  mov     rsi, rax
0x180012a2e  test    rax, rax
0x180012a31  jz      loc_180012B34
0x180012a37  mov     rcx, rax
0x180012a3a  sub     rcx, [rdi]
0x180012a3d  sar     rcx, 1
0x180012a40  cmp     rcx, 1Fh
0x180012a44  jg      loc_180012B2D
0x180012a4a  movsxd  r9, ecx
0x180012a4d  mov     r8, [rdi]
0x180012a50  mov     edx, 20h ; ' '
0x180012a55  lea     rcx, [rbp+57h+String2]
0x180012a59  call    cs:__imp__o_wcsncpy_s
0x180012a5f  mov     ecx, eax; int
0x180012a61  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180012a66  mov     rbx, [rdi+8]
0x180012a6a  lea     r12, [rbx+20h]
0x180012a6e  mov     rcx, r12; lpCriticalSection
0x180012a71  call    cs:__imp_EnterCriticalSection
0x180012a77  lea     r14, [rbx+8]
0x180012a7b  mov     ebx, r13d
0x180012a7e  cmp     ebx, [r14+10h]
0x180012a82  jge     short loc_180012AB4
0x180012a84  movsxd  rax, ebx
0x180012a87  mov     rcx, [r14]
0x180012a8a  lea     rdx, [rbp+57h+String2]; lpString2
0x180012a8e  mov     rcx, [rcx+rax*8]; lpString1
0x180012a92  call    cs:__imp_lstrcmpiW
0x180012a98  test    eax, eax
0x180012a9a  jz      short loc_180012AA0
0x180012a9c  inc     ebx
0x180012a9e  jmp     short loc_180012A7E
0x180012aa0  cmp     ebx, 0FFFFFFFFh
0x180012aa3  jz      short loc_180012AB4
0x180012aa5  mov     edx, ebx
0x180012aa7  mov     rcx, r14
0x180012aaa  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180012aaf  mov     rbx, [rax]
0x180012ab2  jmp     short loc_180012AB7
0x180012ab4  mov     rbx, r13
0x180012ab7  mov     rcx, r12; lpCriticalSection
0x180012aba  call    cs:__imp_LeaveCriticalSection
0x180012ac0  test    rbx, rbx
0x180012ac3  jz      short loc_180012B34
0x180012ac5  mov     [rbp+57h+var_90], r13
0x180012ac9  or      r8, 0FFFFFFFFFFFFFFFFh
0x180012acd  inc     r8; int
0x180012ad0  cmp     [rbx+r8*2], r13w
0x180012ad5  jnz     short loc_180012ACD
0x180012ad7  mov     rdx, rbx; unsigned __int16 *
0x180012ada  lea     rcx, [rbp+57h+pv]; this
0x180012ade  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180012ae3  mov     ebx, eax
0x180012ae5  lea     rcx, [rbp+57h+var_90]
0x180012ae9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180012aee  test    ebx, ebx
0x180012af0  jz      loc_180012A17
0x180012af6  mov     rax, [rdi]
0x180012af9  jmp     short loc_180012B07
0x180012afb  mov     rcx, rax; lpsz
0x180012afe  call    cs:__imp_CharNextW
0x180012b04  mov     [rdi], rax
0x180012b07  cmp     rax, rsi
0x180012b0a  jnz     short loc_180012AFB
0x180012b0c  mov     esi, 25h ; '%'
0x180012b11  mov     rcx, [rdi]; lpsz
0x180012b14  call    cs:__imp_CharNextW
0x180012b1a  mov     rbx, rax
0x180012b1d  mov     [rdi], rax
0x180012b20  jmp     loc_1800129D9
0x180012b25  mov     rdx, rbx
0x180012b28  jmp     loc_180012A00
0x180012b2d  mov     ebx, 80004005h
0x180012b32  jmp     short loc_180012B49
0x180012b34  mov     ebx, 80020009h
0x180012b39  jmp     short loc_180012B49
0x180012b3b  mov     ebx, r13d
0x180012b3e  mov     rcx, [rbp+57h+pv+8]
0x180012b42  mov     [rbp+57h+pv+8], r13
0x180012b46  mov     [r15], rcx
0x180012b49  mov     rcx, [rbp+57h+pv+8]; pv
0x180012b4d  call    cs:__imp_CoTaskMemFree
0x180012b53  mov     eax, ebx
0x180012b55  jmp     short loc_180012B5C
0x180012b57  mov     eax, 80004003h
0x180012b5c  mov     rcx, [rbp+57h+var_40]
0x180012b60  xor     rcx, rsp; StackCookie
0x180012b63  call    __security_check_cookie
0x180012b68  mov     rbx, [rsp+0C0h+arg_8]
0x180012b70  add     rsp, 90h
0x180012b77  pop     r15
0x180012b79  pop     r14
0x180012b7b  pop     r13
0x180012b7d  pop     r12
0x180012b7f  pop     rdi
0x180012b80  pop     rsi
0x180012b81  pop     rbp
0x180012b82  retn
```
