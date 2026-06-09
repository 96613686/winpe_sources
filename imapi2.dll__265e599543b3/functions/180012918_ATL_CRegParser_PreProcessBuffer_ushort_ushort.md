# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180012918`
- end: `0x180012b71`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `601`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180012e28`

## callees

- `0x180011024`
- `0x1800119fc`
- `0x180011ac4`
- `0x18001203c`
- `0x180012918`
- `0x180013a3c`
- `0x180049880`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180012a47`
- `msvcrt!wcsncpy_s` at `0x180012a47`
- `USER32!CharNextW` at `0x1800129dd`
- `USER32!CharNextW` at `0x180012aec`
- `USER32!CharNextW` at `0x180012b02`
- `USER32!CharNextW` at `0x1800129dd`
- `USER32!CharNextW` at `0x180012aec`
- `USER32!CharNextW` at `0x180012b02`
- `ole32!CoTaskMemFree` at `0x18001299a`
- `ole32!CoTaskMemFree` at `0x180012b3b`
- `ole32!CoTaskMemFree` at `0x18001299a`
- `ole32!CoTaskMemFree` at `0x180012b3b`
- `ole32!CoTaskMemAlloc` at `0x1800129ac`
- `ole32!CoTaskMemAlloc` at `0x1800129ac`
- `KERNEL32!EnterCriticalSection` at `0x180012a5f`
- `KERNEL32!EnterCriticalSection` at `0x180012a5f`
- `KERNEL32!LeaveCriticalSection` at `0x180012aa8`
- `KERNEL32!LeaveCriticalSection` at `0x180012aa8`
- `KERNEL32!lstrcmpiW` at `0x180012a80`
- `KERNEL32!lstrcmpiW` at `0x180012a80`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(const wchar_t **this, unsigned __int16 *a2, LPVOID *a3)
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
  errno_t v17; // eax
  const wchar_t *v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // r12
  const wchar_t *v20; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  int v24; // ebx
  const WCHAR *j; // rax
  _DWORD v26[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v28; // [rsp+30h] [rbp-39h] BYREF
  wchar_t Destination[32]; // [rsp+40h] [rbp-29h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  v26[0] = 0;
  if ( v7 < 100 )
    v7 = 1000;
  v26[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 > 0xFFFFFFFF )
  {
    v9 = 0;
LABEL_9:
    CoTaskMemFree(v9);
    return 2147942414LL;
  }
  v9 = CoTaskMemAlloc((unsigned int)v8);
  pv = v9;
  if ( !v9 )
    goto LABEL_9;
  *v9 = 0;
  *this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_16:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v12, 1) )
        goto LABEL_17;
      goto LABEL_34;
    }
    v11 = CharNextW(v4);
    *this = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_16;
    }
    v14 = ATL::CRegParser::StrChrW(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_37;
    v16 = v14 - *this;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_39;
    }
    v17 = wcsncpy_s(Destination, 0x20u, *this, (int)v16);
    ATL::AtlCrtErrorCheck(v17);
    v18 = this[1];
    v19 = (struct _RTL_CRITICAL_SECTION *)(v18 + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
    v20 = v18 + 4;
    for ( i = 0; (signed int)i < *((_DWORD *)v20 + 4); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v20 + 8LL * (int)i), Destination) )
      {
        if ( i != -1 )
        {
          v22 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                              v20,
                                              i);
          goto LABEL_27;
        }
        break;
      }
    }
    v22 = 0;
LABEL_27:
    LeaveCriticalSection(v19);
    if ( !v22 )
    {
LABEL_37:
      v13 = -2147352567;
      goto LABEL_39;
    }
    v28 = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v28);
    if ( !v24 )
    {
LABEL_17:
      v13 = -2147024882;
      goto LABEL_39;
    }
    for ( j = *this; j != v15; *this = j )
      j = CharNextW(j);
LABEL_34:
    v4 = CharNextW(*this);
    *this = v4;
  }
  v13 = 0;
  *a3 = pv;
  pv = 0;
LABEL_39:
  CoTaskMemFree(pv);
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
0x180012942  xor     r13d, r13d
0x180012945  mov     r15, r8
0x180012948  mov     rbx, rdx
0x18001294b  mov     rdi, rcx
0x18001294e  test    rdx, rdx
0x180012951  jz      loc_180012B45
0x180012957  test    r8, r8
0x18001295a  jz      loc_180012B45
0x180012960  mov     [r8], r13
0x180012963  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012967  inc     rax
0x18001296a  cmp     [rdx+rax*2], r13w
0x18001296f  jnz     short loc_180012967
0x180012971  add     eax, eax
0x180012973  mov     [rbp+57h+var_A0], r13d
0x180012977  cmp     eax, 64h ; 'd'
0x18001297a  mov     ecx, 3E8h
0x18001297f  cmovl   eax, ecx
0x180012982  mov     ecx, eax
0x180012984  mov     [rbp+57h+var_9C], eax
0x180012987  add     rcx, rcx
0x18001298a  mov     eax, 0FFFFFFFFh
0x18001298f  cmp     rcx, rax
0x180012992  jbe     short loc_1800129AA
0x180012994  mov     rax, r13
0x180012997  mov     rcx, rax; pv
0x18001299a  call    cs:__imp_CoTaskMemFree
0x1800129a0  mov     eax, 8007000Eh
0x1800129a5  jmp     loc_180012B4A
0x1800129aa  mov     ecx, ecx; cb
0x1800129ac  call    cs:__imp_CoTaskMemAlloc
0x1800129b2  mov     [rbp+57h+pv], rax
0x1800129b6  test    rax, rax
0x1800129b9  jz      short loc_180012997
0x1800129bb  mov     [rax], r13w
0x1800129bf  mov     esi, 25h ; '%'
0x1800129c4  mov     [rdi], rbx
0x1800129c7  cmp     [rbx], r13w
0x1800129cb  jz      loc_180012B29
0x1800129d1  cmp     [rbx], si
0x1800129d4  jnz     loc_180012B13
0x1800129da  mov     rcx, rbx; lpsz
0x1800129dd  call    cs:__imp_CharNextW
0x1800129e3  mov     [rdi], rax
0x1800129e6  cmp     [rax], si
0x1800129e9  jnz     short loc_180012A0F
0x1800129eb  mov     rdx, rax; unsigned __int16 *
0x1800129ee  mov     r8d, 1; int
0x1800129f4  lea     rcx, [rbp+57h+var_A0]; this
0x1800129f8  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800129fd  test    eax, eax
0x1800129ff  jnz     loc_180012AFF
0x180012a05  mov     ebx, 8007000Eh
0x180012a0a  jmp     loc_180012B37
0x180012a0f  mov     edx, esi; unsigned __int16
0x180012a11  mov     rcx, rax; lpsz
0x180012a14  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180012a19  mov     rsi, rax
0x180012a1c  test    rax, rax
0x180012a1f  jz      loc_180012B22
0x180012a25  mov     rcx, rax
0x180012a28  sub     rcx, [rdi]
0x180012a2b  sar     rcx, 1
0x180012a2e  cmp     rcx, 1Fh
0x180012a32  jg      loc_180012B1B
0x180012a38  mov     r8, [rdi]; Source
0x180012a3b  mov     edx, 20h ; ' '; SizeInWords
0x180012a40  movsxd  r9, ecx; MaxCount
0x180012a43  lea     rcx, [rbp+57h+Destination]; Destination
0x180012a47  call    cs:__imp_wcsncpy_s
0x180012a4d  mov     ecx, eax; int
0x180012a4f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180012a54  mov     rbx, [rdi+8]
0x180012a58  lea     r12, [rbx+20h]
0x180012a5c  mov     rcx, r12; lpCriticalSection
0x180012a5f  call    cs:__imp_EnterCriticalSection
0x180012a65  lea     r14, [rbx+8]
0x180012a69  mov     ebx, r13d
0x180012a6c  cmp     ebx, [r14+10h]
0x180012a70  jge     short loc_180012AA2
0x180012a72  mov     rcx, [r14]
0x180012a75  lea     rdx, [rbp+57h+Destination]; lpString2
0x180012a79  movsxd  rax, ebx
0x180012a7c  mov     rcx, [rcx+rax*8]; lpString1
0x180012a80  call    cs:__imp_lstrcmpiW
0x180012a86  test    eax, eax
0x180012a88  jz      short loc_180012A8E
0x180012a8a  inc     ebx
0x180012a8c  jmp     short loc_180012A6C
0x180012a8e  cmp     ebx, 0FFFFFFFFh
0x180012a91  jz      short loc_180012AA2
0x180012a93  mov     edx, ebx
0x180012a95  mov     rcx, r14
0x180012a98  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180012a9d  mov     rbx, [rax]
0x180012aa0  jmp     short loc_180012AA5
0x180012aa2  mov     rbx, r13
0x180012aa5  mov     rcx, r12; lpCriticalSection
0x180012aa8  call    cs:__imp_LeaveCriticalSection
0x180012aae  test    rbx, rbx
0x180012ab1  jz      short loc_180012B22
0x180012ab3  mov     [rbp+57h+var_90], r13
0x180012ab7  or      r8, 0FFFFFFFFFFFFFFFFh
0x180012abb  inc     r8; int
0x180012abe  cmp     [rbx+r8*2], r13w
0x180012ac3  jnz     short loc_180012ABB
0x180012ac5  mov     rdx, rbx; unsigned __int16 *
0x180012ac8  lea     rcx, [rbp+57h+var_A0]; this
0x180012acc  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180012ad1  lea     rcx, [rbp+57h+var_90]
0x180012ad5  mov     ebx, eax
0x180012ad7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180012adc  test    ebx, ebx
0x180012ade  jz      loc_180012A05
0x180012ae4  mov     rax, [rdi]
0x180012ae7  jmp     short loc_180012AF5
0x180012ae9  mov     rcx, rax; lpsz
0x180012aec  call    cs:__imp_CharNextW
0x180012af2  mov     [rdi], rax
0x180012af5  cmp     rax, rsi
0x180012af8  jnz     short loc_180012AE9
0x180012afa  mov     esi, 25h ; '%'
0x180012aff  mov     rcx, [rdi]; lpsz
0x180012b02  call    cs:__imp_CharNextW
0x180012b08  mov     rbx, rax
0x180012b0b  mov     [rdi], rax
0x180012b0e  jmp     loc_1800129C7
0x180012b13  mov     rdx, rbx
0x180012b16  jmp     loc_1800129EE
0x180012b1b  mov     ebx, 80004005h
0x180012b20  jmp     short loc_180012B37
0x180012b22  mov     ebx, 80020009h
0x180012b27  jmp     short loc_180012B37
0x180012b29  mov     rcx, [rbp+57h+pv]
0x180012b2d  mov     ebx, r13d
0x180012b30  mov     [r15], rcx
0x180012b33  mov     [rbp+57h+pv], r13
0x180012b37  mov     rcx, [rbp+57h+pv]; pv
0x180012b3b  call    cs:__imp_CoTaskMemFree
0x180012b41  mov     eax, ebx
0x180012b43  jmp     short loc_180012B4A
0x180012b45  mov     eax, 80004003h
0x180012b4a  mov     rcx, [rbp+57h+var_40]
0x180012b4e  xor     rcx, rsp; StackCookie
0x180012b51  call    __security_check_cookie
0x180012b56  mov     rbx, [rsp+0C0h+arg_8]
0x180012b5e  add     rsp, 90h
0x180012b65  pop     r15
0x180012b67  pop     r14
0x180012b69  pop     r13
0x180012b6b  pop     r12
0x180012b6d  pop     rdi
0x180012b6e  pop     rsi
0x180012b6f  pop     rbp
0x180012b70  retn
```
