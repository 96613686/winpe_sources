# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180007df8`
- end: `0x180008060`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `616`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800082ac`

## callees

- `0x180004e8c`
- `0x180005de0`
- `0x180005fbc`
- `0x1800073ac`
- `0x180007df8`
- `0x180009420`
- `0x180039740`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180007f32`
- `msvcrt!wcsncpy_s` at `0x180007f32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007f93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007f93`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007f4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007f4a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007ec8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007fd7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007fed`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007ec8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007fd7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007fed`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007f6b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007f6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000802a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000802a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007e7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007e7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(const wchar_t **this, unsigned __int16 *a2, unsigned __int16 **a3)
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
  unsigned __int16 *v26; // rcx
  __int64 v27; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v29; // [rsp+30h] [rbp-39h] BYREF
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
  *this = v4;
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
    *this = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_18;
    }
    v14 = ATL::CRegParser::StrChrW(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_39;
    v16 = v14 - *this;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_41;
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
    for ( j = *this; j != v15; *this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*this);
    *this = v4;
  }
  v13 = 0;
  v26 = (unsigned __int16 *)pv;
  pv = 0;
  v27 = 0;
  *a3 = v26;
LABEL_41:
  CoTaskMemFree(pv);
  return v13;
}

```

## disassembly

```asm
0x180007df8  mov     [rsp-8+arg_8], rbx
0x180007dfd  push    rbp
0x180007dfe  push    rsi
0x180007dff  push    rdi
0x180007e00  push    r12
0x180007e02  push    r13
0x180007e04  push    r14
0x180007e06  push    r15
0x180007e08  lea     rbp, [rsp-27h]
0x180007e0d  sub     rsp, 90h
0x180007e14  mov     rax, cs:__security_cookie
0x180007e1b  xor     rax, rsp
0x180007e1e  mov     [rbp+57h+var_40], rax
0x180007e22  mov     r15, r8
0x180007e25  mov     rbx, rdx
0x180007e28  mov     rdi, rcx
0x180007e2b  xor     r13d, r13d
0x180007e2e  test    rdx, rdx
0x180007e31  jz      loc_180008034
0x180007e37  test    r8, r8
0x180007e3a  jz      loc_180008034
0x180007e40  mov     [r8], r13
0x180007e43  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007e47  inc     rax
0x180007e4a  cmp     [rdx+rax*2], r13w
0x180007e4f  jnz     short loc_180007E47
0x180007e51  add     eax, eax
0x180007e53  mov     ecx, 3E8h
0x180007e58  cmp     eax, 64h ; 'd'
0x180007e5b  cmovl   eax, ecx
0x180007e5e  mov     dword ptr [rbp+57h+var_A0], r13d
0x180007e62  mov     dword ptr [rbp+57h+var_A0+4], eax
0x180007e65  mov     ecx, eax
0x180007e67  add     rcx, rcx
0x180007e6a  mov     eax, 0FFFFFFFFh
0x180007e6f  cmp     rcx, rax
0x180007e72  jbe     short loc_180007E7D
0x180007e74  mov     rax, r13
0x180007e77  mov     [rbp+57h+pv], r13
0x180007e7b  jmp     short loc_180007E92
0x180007e7d  mov     ecx, ecx; cb
0x180007e7f  call    cs:__imp_CoTaskMemAlloc
0x180007e85  mov     [rbp+57h+pv], rax
0x180007e89  test    rax, rax
0x180007e8c  jz      short loc_180007E92
0x180007e8e  mov     [rax], r13w
0x180007e92  test    rax, rax
0x180007e95  jnz     short loc_180007EAA
0x180007e97  mov     rcx, rax; pv
0x180007e9a  call    cs:__imp_CoTaskMemFree
0x180007ea0  mov     eax, 8007000Eh
0x180007ea5  jmp     loc_180008039
0x180007eaa  mov     [rdi], rbx
0x180007ead  mov     esi, 25h ; '%'
0x180007eb2  cmp     [rbx], r13w
0x180007eb6  jz      loc_180008014
0x180007ebc  cmp     [rbx], si
0x180007ebf  jnz     loc_180007FFE
0x180007ec5  mov     rcx, rbx; lpsz
0x180007ec8  call    cs:__imp_CharNextW
0x180007ece  mov     [rdi], rax
0x180007ed1  cmp     [rax], si
0x180007ed4  jnz     short loc_180007EFA
0x180007ed6  mov     rdx, rax; unsigned __int16 *
0x180007ed9  mov     r8d, 1; int
0x180007edf  lea     rcx, [rbp+57h+var_A0]; this
0x180007ee3  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180007ee8  test    eax, eax
0x180007eea  jnz     loc_180007FEA
0x180007ef0  mov     ebx, 8007000Eh
0x180007ef5  jmp     loc_180008026
0x180007efa  mov     edx, esi; unsigned __int16
0x180007efc  mov     rcx, rax; lpsz
0x180007eff  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180007f04  mov     rsi, rax
0x180007f07  test    rax, rax
0x180007f0a  jz      loc_18000800D
0x180007f10  mov     rcx, rax
0x180007f13  sub     rcx, [rdi]
0x180007f16  sar     rcx, 1
0x180007f19  cmp     rcx, 1Fh
0x180007f1d  jg      loc_180008006
0x180007f23  movsxd  r9, ecx; MaxCount
0x180007f26  mov     r8, [rdi]; Source
0x180007f29  mov     edx, 20h ; ' '; SizeInWords
0x180007f2e  lea     rcx, [rbp+57h+Destination]; Destination
0x180007f32  call    cs:__imp_wcsncpy_s
0x180007f38  mov     ecx, eax; int
0x180007f3a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180007f3f  mov     rbx, [rdi+8]
0x180007f43  lea     r12, [rbx+20h]
0x180007f47  mov     rcx, r12; lpCriticalSection
0x180007f4a  call    cs:__imp_EnterCriticalSection
0x180007f50  lea     r14, [rbx+8]
0x180007f54  mov     ebx, r13d
0x180007f57  cmp     ebx, [r14+10h]
0x180007f5b  jge     short loc_180007F8D
0x180007f5d  movsxd  rax, ebx
0x180007f60  mov     rcx, [r14]
0x180007f63  lea     rdx, [rbp+57h+Destination]; lpString2
0x180007f67  mov     rcx, [rcx+rax*8]; lpString1
0x180007f6b  call    cs:__imp_lstrcmpiW
0x180007f71  test    eax, eax
0x180007f73  jz      short loc_180007F79
0x180007f75  inc     ebx
0x180007f77  jmp     short loc_180007F57
0x180007f79  cmp     ebx, 0FFFFFFFFh
0x180007f7c  jz      short loc_180007F8D
0x180007f7e  mov     edx, ebx
0x180007f80  mov     rcx, r14
0x180007f83  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180007f88  mov     rbx, [rax]
0x180007f8b  jmp     short loc_180007F90
0x180007f8d  mov     rbx, r13
0x180007f90  mov     rcx, r12; lpCriticalSection
0x180007f93  call    cs:__imp_LeaveCriticalSection
0x180007f99  test    rbx, rbx
0x180007f9c  jz      short loc_18000800D
0x180007f9e  mov     [rbp+57h+var_90], r13
0x180007fa2  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007fa6  inc     r8; int
0x180007fa9  cmp     [rbx+r8*2], r13w
0x180007fae  jnz     short loc_180007FA6
0x180007fb0  mov     rdx, rbx; unsigned __int16 *
0x180007fb3  lea     rcx, [rbp+57h+var_A0]; this
0x180007fb7  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180007fbc  mov     ebx, eax
0x180007fbe  lea     rcx, [rbp+57h+var_90]
0x180007fc2  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180007fc7  test    ebx, ebx
0x180007fc9  jz      loc_180007EF0
0x180007fcf  mov     rax, [rdi]
0x180007fd2  jmp     short loc_180007FE0
0x180007fd4  mov     rcx, rax; lpsz
0x180007fd7  call    cs:__imp_CharNextW
0x180007fdd  mov     [rdi], rax
0x180007fe0  cmp     rax, rsi
0x180007fe3  jnz     short loc_180007FD4
0x180007fe5  mov     esi, 25h ; '%'
0x180007fea  mov     rcx, [rdi]; lpsz
0x180007fed  call    cs:__imp_CharNextW
0x180007ff3  mov     rbx, rax
0x180007ff6  mov     [rdi], rax
0x180007ff9  jmp     loc_180007EB2
0x180007ffe  mov     rdx, rbx
0x180008001  jmp     loc_180007ED9
0x180008006  mov     ebx, 80004005h
0x18000800b  jmp     short loc_180008026
0x18000800d  mov     ebx, 80020009h
0x180008012  jmp     short loc_180008026
0x180008014  mov     ebx, r13d
0x180008017  mov     rcx, [rbp+57h+pv]
0x18000801b  mov     [rbp+57h+pv], r13
0x18000801f  mov     [rbp+57h+var_A0], r13
0x180008023  mov     [r15], rcx
0x180008026  mov     rcx, [rbp+57h+pv]; pv
0x18000802a  call    cs:__imp_CoTaskMemFree
0x180008030  mov     eax, ebx
0x180008032  jmp     short loc_180008039
0x180008034  mov     eax, 80004003h
0x180008039  mov     rcx, [rbp+57h+var_40]
0x18000803d  xor     rcx, rsp; StackCookie
0x180008040  call    __security_check_cookie
0x180008045  mov     rbx, [rsp+0C0h+arg_8]
0x18000804d  add     rsp, 90h
0x180008054  pop     r15
0x180008056  pop     r14
0x180008058  pop     r13
0x18000805a  pop     r12
0x18000805c  pop     rdi
0x18000805d  pop     rsi
0x18000805e  pop     rbp
0x18000805f  retn
```
