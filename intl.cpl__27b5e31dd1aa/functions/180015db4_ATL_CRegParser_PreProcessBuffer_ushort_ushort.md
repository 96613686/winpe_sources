# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180015db4`
- end: `0x180015fd7`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `547`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001614c`

## callees

- `0x180013378`
- `0x180013dcc`
- `0x180014010`
- `0x180015db4`
- `0x18001710c`
- `0x180017164`
- `0x18002a150`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180015ee0`
- `msvcrt!wcsncpy_s` at `0x180015ee0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015e5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015f8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015e5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015f8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015e40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015e40`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015e90`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015f38`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015f61`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015e90`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015f38`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180015f61`

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
  errno_t v18; // eax
  const unsigned __int16 *v19; // rax
  __int64 v20; // r8
  int v21; // ebx
  const WCHAR *i; // rax
  unsigned int v23; // ebx
  _DWORD v24[2]; // [rsp+20h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-31h]
  __int64 v26; // [rsp+30h] [rbp-29h] BYREF
  wchar_t Destination[32]; // [rsp+40h] [rbp-19h] BYREF

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
  v24[0] = 0;
  v24[1] = v7;
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
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v14, 1) )
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
  v18 = wcsncpy_s(Destination, 0x20u, *(const wchar_t **)this, (int)v17);
  ATL::AtlCrtErrorCheck(v18);
  v19 = ATL::CRegObject::StrFromMap(*((ATL::CRegObject **)this + 1), Destination);
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
  v21 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v19, v20);
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
0x180015db4  mov     [rsp-8+arg_8], rbx
0x180015db9  mov     [rsp-8+arg_18], rsi
0x180015dbe  push    rbp
0x180015dbf  push    rdi
0x180015dc0  push    r12
0x180015dc2  push    r14
0x180015dc4  push    r15
0x180015dc6  lea     rbp, [rsp-37h]
0x180015dcb  sub     rsp, 90h
0x180015dd2  mov     rax, cs:__security_cookie
0x180015dd9  xor     rax, rsp
0x180015ddc  mov     [rbp+57h+var_30], rax
0x180015de0  mov     r14, r8
0x180015de3  mov     rbx, rdx
0x180015de6  mov     rdi, rcx
0x180015de9  xor     r15d, r15d
0x180015dec  test    rdx, rdx
0x180015def  jz      loc_180015FAA
0x180015df5  test    r8, r8
0x180015df8  jz      loc_180015FAA
0x180015dfe  mov     [r8], r15
0x180015e01  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015e05  inc     rax
0x180015e08  cmp     [rdx+rax*2], r15w
0x180015e0d  jnz     short loc_180015E05
0x180015e0f  add     eax, eax
0x180015e11  mov     ecx, 3E8h
0x180015e16  cmp     eax, 64h ; 'd'
0x180015e19  cmovl   eax, ecx
0x180015e1c  mov     [rbp+57h+var_90], r15d
0x180015e20  mov     [rbp+57h+var_8C], eax
0x180015e23  mov     ecx, eax
0x180015e25  add     rcx, rcx
0x180015e28  mov     eax, 0FFFFFFFFh
0x180015e2d  cmp     rcx, rax
0x180015e30  jbe     short loc_180015E3E
0x180015e32  mov     rax, r15
0x180015e35  mov     rdx, r15
0x180015e38  mov     [rbp+57h+pv], rdx
0x180015e3c  jmp     short loc_180015E56
0x180015e3e  mov     ecx, ecx; cb
0x180015e40  call    cs:__imp_CoTaskMemAlloc
0x180015e46  mov     rdx, rax
0x180015e49  mov     [rbp+57h+pv], rax
0x180015e4d  test    rax, rax
0x180015e50  jz      short loc_180015E56
0x180015e52  mov     [rax], r15w
0x180015e56  test    rax, rax
0x180015e59  jnz     short loc_180015E6E
0x180015e5b  mov     rcx, rax; pv
0x180015e5e  call    cs:__imp_CoTaskMemFree
0x180015e64  mov     eax, 8007000Eh
0x180015e69  jmp     loc_180015FAF
0x180015e6e  mov     [rdi], rbx
0x180015e71  movzx   eax, word ptr [rbx]
0x180015e74  test    ax, ax
0x180015e77  jz      loc_180015F7D
0x180015e7d  mov     r12d, 25h ; '%'
0x180015e83  cmp     ax, r12w
0x180015e87  jnz     loc_180015F48
0x180015e8d  mov     rcx, rbx; lpsz
0x180015e90  call    cs:__imp_CharNextW
0x180015e96  mov     [rdi], rax
0x180015e99  cmp     [rax], r12w
0x180015e9d  jnz     short loc_180015EA7
0x180015e9f  mov     rdx, rax
0x180015ea2  jmp     loc_180015F4B
0x180015ea7  mov     edx, r12d; unsigned __int16
0x180015eaa  mov     rcx, rax; lpsz
0x180015ead  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180015eb2  mov     rsi, rax
0x180015eb5  test    rax, rax
0x180015eb8  jz      loc_180015F9C
0x180015ebe  mov     rcx, rax
0x180015ec1  sub     rcx, [rdi]
0x180015ec4  sar     rcx, 1
0x180015ec7  cmp     rcx, 1Fh
0x180015ecb  jg      loc_180015F95
0x180015ed1  movsxd  r9, ecx; MaxCount
0x180015ed4  mov     r8, [rdi]; Source
0x180015ed7  mov     edx, 20h ; ' '; SizeInWords
0x180015edc  lea     rcx, [rbp+57h+Destination]; Destination
0x180015ee0  call    cs:__imp_wcsncpy_s
0x180015ee6  mov     ecx, eax; int
0x180015ee8  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180015eed  lea     rdx, [rbp+57h+Destination]; unsigned __int16 *
0x180015ef1  mov     rcx, [rdi+8]; this
0x180015ef5  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x180015efa  test    rax, rax
0x180015efd  jz      loc_180015F9C
0x180015f03  mov     [rbp+57h+var_80], r15
0x180015f07  or      r8, 0FFFFFFFFFFFFFFFFh
0x180015f0b  inc     r8; int
0x180015f0e  cmp     [rax+r8*2], r15w
0x180015f13  jnz     short loc_180015F0B
0x180015f15  mov     rdx, rax; unsigned __int16 *
0x180015f18  lea     rcx, [rbp+57h+var_90]; this
0x180015f1c  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180015f21  mov     ebx, eax
0x180015f23  lea     rcx, [rbp+57h+var_80]
0x180015f27  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180015f2c  test    ebx, ebx
0x180015f2e  jz      short loc_180015FA3
0x180015f30  mov     rax, [rdi]
0x180015f33  jmp     short loc_180015F41
0x180015f35  mov     rcx, rax; lpsz
0x180015f38  call    cs:__imp_CharNextW
0x180015f3e  mov     [rdi], rax
0x180015f41  cmp     rax, rsi
0x180015f44  jnz     short loc_180015F35
0x180015f46  jmp     short loc_180015F5E
0x180015f48  mov     rdx, rbx; unsigned __int16 *
0x180015f4b  mov     r8d, 1; int
0x180015f51  lea     rcx, [rbp+57h+var_90]; this
0x180015f55  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180015f5a  test    eax, eax
0x180015f5c  jz      short loc_180015FA3
0x180015f5e  mov     rcx, [rdi]; lpsz
0x180015f61  call    cs:__imp_CharNextW
0x180015f67  mov     rbx, rax
0x180015f6a  mov     [rdi], rax
0x180015f6d  movzx   eax, word ptr [rax]
0x180015f70  test    ax, ax
0x180015f73  jnz     loc_180015E83
0x180015f79  mov     rdx, [rbp+57h+pv]
0x180015f7d  mov     ebx, r15d
0x180015f80  mov     [rbp+57h+pv], r15
0x180015f84  mov     [r14], rdx
0x180015f87  mov     rcx, [rbp+57h+pv]; pv
0x180015f8b  call    cs:__imp_CoTaskMemFree
0x180015f91  mov     eax, ebx
0x180015f93  jmp     short loc_180015FAF
0x180015f95  mov     ebx, 80004005h
0x180015f9a  jmp     short loc_180015F87
0x180015f9c  mov     ebx, 80020009h
0x180015fa1  jmp     short loc_180015F87
0x180015fa3  mov     ebx, 8007000Eh
0x180015fa8  jmp     short loc_180015F87
0x180015faa  mov     eax, 80004003h
0x180015faf  mov     rcx, [rbp+57h+var_30]
0x180015fb3  xor     rcx, rsp; StackCookie
0x180015fb6  call    __security_check_cookie
0x180015fbb  lea     r11, [rsp+0B0h+var_20]
0x180015fc3  mov     rbx, [r11+38h]
0x180015fc7  mov     rsi, [r11+48h]
0x180015fcb  mov     rsp, r11
0x180015fce  pop     r15
0x180015fd0  pop     r14
0x180015fd2  pop     r12
0x180015fd4  pop     rdi
0x180015fd5  pop     rbp
0x180015fd6  retn
```
