# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180019b28`
- end: `0x180019d8c`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `612`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a3cc`

## callees

- `0x180001e80`
- `0x180016bd0`
- `0x180017c88`
- `0x180017ebc`
- `0x180019604`
- `0x180019b28`
- `0x18001b604`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180019c62`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180019c62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019cc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019cc3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019c7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019c7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019bca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019d56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019bca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019d56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019baf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019baf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019bf8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019d07`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019d1d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019bf8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019d07`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180019d1d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180019c9b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180019c9b`

## pseudocode

```c
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
0x180019b28  mov     [rsp-8+arg_8], rbx
0x180019b2d  push    rbp
0x180019b2e  push    rsi
0x180019b2f  push    rdi
0x180019b30  push    r12
0x180019b32  push    r13
0x180019b34  push    r14
0x180019b36  push    r15
0x180019b38  lea     rbp, [rsp-27h]
0x180019b3d  sub     rsp, 90h
0x180019b44  mov     rax, cs:__security_cookie
0x180019b4b  xor     rax, rsp
0x180019b4e  mov     [rbp+57h+var_40], rax
0x180019b52  mov     r15, r8
0x180019b55  mov     rbx, rdx
0x180019b58  mov     rdi, rcx
0x180019b5b  xor     r13d, r13d
0x180019b5e  test    rdx, rdx
0x180019b61  jz      loc_180019D60
0x180019b67  test    r8, r8
0x180019b6a  jz      loc_180019D60
0x180019b70  mov     [r8], r13
0x180019b73  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019b77  inc     rax
0x180019b7a  cmp     [rdx+rax*2], r13w
0x180019b7f  jnz     short loc_180019B77
0x180019b81  add     eax, eax
0x180019b83  mov     ecx, 3E8h
0x180019b88  cmp     eax, 64h ; 'd'
0x180019b8b  cmovl   eax, ecx
0x180019b8e  mov     [rbp+57h+var_A0], r13d
0x180019b92  mov     [rbp+57h+var_9C], eax
0x180019b95  mov     ecx, eax
0x180019b97  add     rcx, rcx
0x180019b9a  mov     eax, 0FFFFFFFFh
0x180019b9f  cmp     rcx, rax
0x180019ba2  jbe     short loc_180019BAD
0x180019ba4  mov     rax, r13
0x180019ba7  mov     [rbp+57h+pv], r13
0x180019bab  jmp     short loc_180019BC2
0x180019bad  mov     ecx, ecx; cb
0x180019baf  call    cs:__imp_CoTaskMemAlloc
0x180019bb5  mov     [rbp+57h+pv], rax
0x180019bb9  test    rax, rax
0x180019bbc  jz      short loc_180019BC2
0x180019bbe  mov     [rax], r13w
0x180019bc2  test    rax, rax
0x180019bc5  jnz     short loc_180019BDA
0x180019bc7  mov     rcx, rax; pv
0x180019bca  call    cs:__imp_CoTaskMemFree
0x180019bd0  mov     eax, 8007000Eh
0x180019bd5  jmp     loc_180019D65
0x180019bda  mov     [rdi], rbx
0x180019bdd  mov     esi, 25h ; '%'
0x180019be2  cmp     [rbx], r13w
0x180019be6  jz      loc_180019D44
0x180019bec  cmp     [rbx], si
0x180019bef  jnz     loc_180019D2E
0x180019bf5  mov     rcx, rbx; lpsz
0x180019bf8  call    cs:__imp_CharNextW
0x180019bfe  mov     [rdi], rax
0x180019c01  cmp     [rax], si
0x180019c04  jnz     short loc_180019C2A
0x180019c06  mov     rdx, rax; unsigned __int16 *
0x180019c09  mov     r8d, 1; int
0x180019c0f  lea     rcx, [rbp+57h+var_A0]; this
0x180019c13  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180019c18  test    eax, eax
0x180019c1a  jnz     loc_180019D1A
0x180019c20  mov     ebx, 8007000Eh
0x180019c25  jmp     loc_180019D52
0x180019c2a  mov     edx, esi; unsigned __int16
0x180019c2c  mov     rcx, rax; lpsz
0x180019c2f  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180019c34  mov     rsi, rax
0x180019c37  test    rax, rax
0x180019c3a  jz      loc_180019D3D
0x180019c40  mov     rcx, rax
0x180019c43  sub     rcx, [rdi]
0x180019c46  sar     rcx, 1
0x180019c49  cmp     rcx, 1Fh
0x180019c4d  jg      loc_180019D36
0x180019c53  movsxd  r9, ecx
0x180019c56  mov     r8, [rdi]
0x180019c59  mov     edx, 20h ; ' '
0x180019c5e  lea     rcx, [rbp+57h+String2]
0x180019c62  call    cs:__imp__o_wcsncpy_s
0x180019c68  mov     ecx, eax; int
0x180019c6a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180019c6f  mov     rbx, [rdi+8]
0x180019c73  lea     r12, [rbx+20h]
0x180019c77  mov     rcx, r12; lpCriticalSection
0x180019c7a  call    cs:__imp_EnterCriticalSection
0x180019c80  lea     r14, [rbx+8]
0x180019c84  mov     ebx, r13d
0x180019c87  cmp     ebx, [r14+10h]
0x180019c8b  jge     short loc_180019CBD
0x180019c8d  movsxd  rax, ebx
0x180019c90  mov     rcx, [r14]
0x180019c93  lea     rdx, [rbp+57h+String2]; lpString2
0x180019c97  mov     rcx, [rcx+rax*8]; lpString1
0x180019c9b  call    cs:__imp_lstrcmpiW
0x180019ca1  test    eax, eax
0x180019ca3  jz      short loc_180019CA9
0x180019ca5  inc     ebx
0x180019ca7  jmp     short loc_180019C87
0x180019ca9  cmp     ebx, 0FFFFFFFFh
0x180019cac  jz      short loc_180019CBD
0x180019cae  mov     edx, ebx
0x180019cb0  mov     rcx, r14
0x180019cb3  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180019cb8  mov     rbx, [rax]
0x180019cbb  jmp     short loc_180019CC0
0x180019cbd  mov     rbx, r13
0x180019cc0  mov     rcx, r12; lpCriticalSection
0x180019cc3  call    cs:__imp_LeaveCriticalSection
0x180019cc9  test    rbx, rbx
0x180019ccc  jz      short loc_180019D3D
0x180019cce  mov     [rbp+57h+var_90], r13
0x180019cd2  or      r8, 0FFFFFFFFFFFFFFFFh
0x180019cd6  inc     r8; int
0x180019cd9  cmp     [rbx+r8*2], r13w
0x180019cde  jnz     short loc_180019CD6
0x180019ce0  mov     rdx, rbx; unsigned __int16 *
0x180019ce3  lea     rcx, [rbp+57h+var_A0]; this
0x180019ce7  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180019cec  mov     ebx, eax
0x180019cee  lea     rcx, [rbp+57h+var_90]
0x180019cf2  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180019cf7  test    ebx, ebx
0x180019cf9  jz      loc_180019C20
0x180019cff  mov     rax, [rdi]
0x180019d02  jmp     short loc_180019D10
0x180019d04  mov     rcx, rax; lpsz
0x180019d07  call    cs:__imp_CharNextW
0x180019d0d  mov     [rdi], rax
0x180019d10  cmp     rax, rsi
0x180019d13  jnz     short loc_180019D04
0x180019d15  mov     esi, 25h ; '%'
0x180019d1a  mov     rcx, [rdi]; lpsz
0x180019d1d  call    cs:__imp_CharNextW
0x180019d23  mov     rbx, rax
0x180019d26  mov     [rdi], rax
0x180019d29  jmp     loc_180019BE2
0x180019d2e  mov     rdx, rbx
0x180019d31  jmp     loc_180019C09
0x180019d36  mov     ebx, 80004005h
0x180019d3b  jmp     short loc_180019D52
0x180019d3d  mov     ebx, 80020009h
0x180019d42  jmp     short loc_180019D52
0x180019d44  mov     ebx, r13d
0x180019d47  mov     rcx, [rbp+57h+pv]
0x180019d4b  mov     [rbp+57h+pv], r13
0x180019d4f  mov     [r15], rcx
0x180019d52  mov     rcx, [rbp+57h+pv]; pv
0x180019d56  call    cs:__imp_CoTaskMemFree
0x180019d5c  mov     eax, ebx
0x180019d5e  jmp     short loc_180019D65
0x180019d60  mov     eax, 80004003h
0x180019d65  mov     rcx, [rbp+57h+var_40]
0x180019d69  xor     rcx, rsp; StackCookie
0x180019d6c  call    __security_check_cookie
0x180019d71  mov     rbx, [rsp+0C0h+arg_8]
0x180019d79  add     rsp, 90h
0x180019d80  pop     r15
0x180019d82  pop     r14
0x180019d84  pop     r13
0x180019d86  pop     r12
0x180019d88  pop     rdi
0x180019d89  pop     rsi
0x180019d8a  pop     rbp
0x180019d8b  retn
```
