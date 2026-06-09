# ATL::CRegParser::PreProcessBuffer(ushort const *,ushort * *)

- ea: `0x180016a44`
- end: `0x180016c67`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEBGPEAPEAG@Z`
- size: `547`
- prototype: `int(ATL::CRegParser *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016f5c`

## callees

- `0x18000fb64`
- `0x180014e90`
- `0x180016a44`
- `0x180017460`
- `0x1800174b0`
- `0x180055550`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180016b02`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180016ba7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180016bca`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180016b02`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180016ba7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180016bca`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcpynW` at `0x180016b4d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcpynW` at `0x180016b4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016ac9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016c02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016c1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016ac9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016c02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016c1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016ab7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016ab7`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(ATL::CRegParser *this, WCHAR *a2, LPVOID *a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  LPWSTR v8; // rax
  const unsigned __int16 *v9; // rdx
  const unsigned __int16 *v10; // rax
  const unsigned __int16 *v11; // rsi
  __int64 v12; // r8
  const unsigned __int16 *v13; // rbx
  int v14; // ebx
  const WCHAR *i; // rax
  unsigned int v16; // ebx
  _QWORD *v17; // [rsp+20h] [rbp-39h] BYREF
  int v18; // [rsp+28h] [rbp-31h] BYREF
  int v19; // [rsp+2Ch] [rbp-2Dh]
  LPVOID pv; // [rsp+30h] [rbp-29h]
  _QWORD *v21; // [rsp+38h] [rbp-21h] BYREF
  WCHAR String1[32]; // [rsp+40h] [rbp-19h] BYREF

  v17 = 0;
  v4 = a2;
  if ( !a2 || !a3 )
  {
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v17);
    return 2147500035LL;
  }
  *a3 = 0;
  v6 = -1;
  v18 = 0;
  do
    ++v6;
  while ( a2[v6] );
  v19 = 2 * v6 + 2;
  pv = CoTaskMemAlloc(2LL * v19);
  if ( !pv )
  {
    CoTaskMemFree(0);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v17);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v9 = v4;
LABEL_27:
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::AddChar((ATL::CRegParser::CParseBuffer *)&v18, v9) )
        goto LABEL_32;
      goto LABEL_28;
    }
    v8 = CharNextW(v4);
    *(_QWORD *)this = v8;
    if ( *v8 == 37 )
    {
      v9 = v8;
      goto LABEL_27;
    }
    v10 = ATL::CRegParser::StrChrW(v8, 0x25u);
    v11 = v10;
    if ( !v10 )
      goto LABEL_30;
    v12 = ((__int64)v10 - *(_QWORD *)this) >> 1;
    if ( (int)v12 > 31 )
    {
      v16 = -2147467259;
LABEL_33:
      CoTaskMemFree(pv);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v17);
      return v16;
    }
    lstrcpynW(String1, *(LPCWSTR *)this, v12 + 1);
    v13 = ATL::CRegObject::StrFromMap(*((ATL::CRegObject **)this + 1), String1);
    if ( !v13 )
    {
LABEL_30:
      v16 = -2147352567;
      goto LABEL_33;
    }
    v21 = 0;
    while ( *v13 )
    {
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::AddChar((ATL::CRegParser::CParseBuffer *)&v18, v13) )
      {
        v14 = 0;
        goto LABEL_21;
      }
      ++v13;
    }
    v14 = 1;
LABEL_21:
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v21);
    if ( !v14 )
      goto LABEL_32;
    for ( i = *(const WCHAR **)this; i != v11; *(_QWORD *)this = i )
      i = CharNextW(i);
LABEL_28:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
  }
  if ( !(unsigned int)ATL::CRegParser::CParseBuffer::AddChar((ATL::CRegParser::CParseBuffer *)&v18, v4) )
  {
LABEL_32:
    v16 = -2147024882;
    goto LABEL_33;
  }
  *a3 = pv;
  CoTaskMemFree(0);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v17);
  return 0;
}

```

## disassembly

```asm
0x180016a44  mov     [rsp-8+arg_8], rbx
0x180016a49  mov     [rsp-8+arg_18], rsi
0x180016a4e  push    rbp
0x180016a4f  push    rdi
0x180016a50  push    r12
0x180016a52  push    r14
0x180016a54  push    r15
0x180016a56  lea     rbp, [rsp-37h]
0x180016a5b  sub     rsp, 90h
0x180016a62  mov     rax, cs:__security_cookie
0x180016a69  xor     rax, rsp
0x180016a6c  mov     [rbp+57h+var_30], rax
0x180016a70  xor     r15d, r15d
0x180016a73  mov     r14, r8
0x180016a76  mov     [rbp+57h+var_90], r15
0x180016a7a  mov     rbx, rdx
0x180016a7d  mov     rdi, rcx
0x180016a80  test    rdx, rdx
0x180016a83  jz      loc_180016C31
0x180016a89  test    r8, r8
0x180016a8c  jz      loc_180016C31
0x180016a92  mov     [r8], r15
0x180016a95  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016a99  mov     [rbp+57h+var_88], r15d
0x180016a9d  inc     rax
0x180016aa0  cmp     [rdx+rax*2], r15w
0x180016aa5  jnz     short loc_180016A9D
0x180016aa7  lea     eax, ds:2[rax*2]
0x180016aae  movsxd  rcx, eax
0x180016ab1  add     rcx, rcx; cb
0x180016ab4  mov     [rbp+57h+var_84], eax
0x180016ab7  call    cs:__imp_CoTaskMemAlloc
0x180016abd  mov     [rbp+57h+pv], rax
0x180016ac1  test    rax, rax
0x180016ac4  jnz     short loc_180016AE2
0x180016ac6  mov     rcx, rax; pv
0x180016ac9  call    cs:__imp_CoTaskMemFree
0x180016acf  lea     rcx, [rbp+57h+var_90]
0x180016ad3  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180016ad8  mov     eax, 8007000Eh
0x180016add  jmp     loc_180016C3F
0x180016ae2  mov     [rdi], rbx
0x180016ae5  mov     r12d, 25h ; '%'
0x180016aeb  cmp     [rbx], r15w
0x180016aef  jz      loc_180016BE9
0x180016af5  cmp     [rbx], r12w
0x180016af9  jnz     loc_180016BB7
0x180016aff  mov     rcx, rbx; lpsz
0x180016b02  call    cs:__imp_CharNextW
0x180016b08  mov     [rdi], rax
0x180016b0b  cmp     [rax], r12w
0x180016b0f  jnz     short loc_180016B19
0x180016b11  mov     rdx, rax
0x180016b14  jmp     loc_180016BBA
0x180016b19  mov     edx, r12d; unsigned __int16
0x180016b1c  mov     rcx, rax; lpsz
0x180016b1f  call    ?StrChrW@CRegParser@ATL@@KAPEBGPEBGG@Z; ATL::CRegParser::StrChrW(ushort const *,ushort)
0x180016b24  mov     rsi, rax
0x180016b27  test    rax, rax
0x180016b2a  jz      loc_180016BE2
0x180016b30  mov     r8, rax
0x180016b33  sub     r8, [rdi]
0x180016b36  sar     r8, 1
0x180016b39  cmp     r8d, 1Fh
0x180016b3d  jg      loc_180016BDB
0x180016b43  mov     rdx, [rdi]; lpString2
0x180016b46  lea     rcx, [rbp+57h+String1]; lpString1
0x180016b4a  inc     r8d; iMaxLength
0x180016b4d  call    cs:__imp_lstrcpynW
0x180016b53  mov     rcx, [rdi+8]; this
0x180016b57  lea     rdx, [rbp+57h+String1]; unsigned __int16 *
0x180016b5b  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x180016b60  mov     rbx, rax
0x180016b63  test    rax, rax
0x180016b66  jz      short loc_180016BE2
0x180016b68  mov     [rbp+57h+var_78], r15
0x180016b6c  cmp     [rbx], r15w
0x180016b70  jz      short loc_180016B8D
0x180016b72  mov     rdx, rbx; unsigned __int16 *
0x180016b75  lea     rcx, [rbp+57h+var_88]; this
0x180016b79  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEBG@Z; ATL::CRegParser::CParseBuffer::AddChar(ushort const *)
0x180016b7e  test    eax, eax
0x180016b80  jz      short loc_180016B88
0x180016b82  add     rbx, 2
0x180016b86  jmp     short loc_180016B6C
0x180016b88  mov     ebx, r15d
0x180016b8b  jmp     short loc_180016B92
0x180016b8d  mov     ebx, 1
0x180016b92  lea     rcx, [rbp+57h+var_78]
0x180016b96  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180016b9b  test    ebx, ebx
0x180016b9d  jz      short loc_180016BF9
0x180016b9f  mov     rax, [rdi]
0x180016ba2  jmp     short loc_180016BB0
0x180016ba4  mov     rcx, rax; lpsz
0x180016ba7  call    cs:__imp_CharNextW
0x180016bad  mov     [rdi], rax
0x180016bb0  cmp     rax, rsi
0x180016bb3  jnz     short loc_180016BA4
0x180016bb5  jmp     short loc_180016BC7
0x180016bb7  mov     rdx, rbx; unsigned __int16 *
0x180016bba  lea     rcx, [rbp+57h+var_88]; this
0x180016bbe  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEBG@Z; ATL::CRegParser::CParseBuffer::AddChar(ushort const *)
0x180016bc3  test    eax, eax
0x180016bc5  jz      short loc_180016BF9
0x180016bc7  mov     rcx, [rdi]; lpsz
0x180016bca  call    cs:__imp_CharNextW
0x180016bd0  mov     rbx, rax
0x180016bd3  mov     [rdi], rax
0x180016bd6  jmp     loc_180016AEB
0x180016bdb  mov     ebx, 80004005h
0x180016be0  jmp     short loc_180016BFE
0x180016be2  mov     ebx, 80020009h
0x180016be7  jmp     short loc_180016BFE
0x180016be9  mov     rdx, rbx; unsigned __int16 *
0x180016bec  lea     rcx, [rbp+57h+var_88]; this
0x180016bf0  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEBG@Z; ATL::CRegParser::CParseBuffer::AddChar(ushort const *)
0x180016bf5  test    eax, eax
0x180016bf7  jnz     short loc_180016C15
0x180016bf9  mov     ebx, 8007000Eh
0x180016bfe  mov     rcx, [rbp+57h+pv]; pv
0x180016c02  call    cs:__imp_CoTaskMemFree
0x180016c08  lea     rcx, [rbp+57h+var_90]
0x180016c0c  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180016c11  mov     eax, ebx
0x180016c13  jmp     short loc_180016C3F
0x180016c15  mov     rax, [rbp+57h+pv]
0x180016c19  xor     ecx, ecx; pv
0x180016c1b  mov     [r14], rax
0x180016c1e  call    cs:__imp_CoTaskMemFree
0x180016c24  lea     rcx, [rbp+57h+var_90]
0x180016c28  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180016c2d  xor     eax, eax
0x180016c2f  jmp     short loc_180016C3F
0x180016c31  lea     rcx, [rbp+57h+var_90]
0x180016c35  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180016c3a  mov     eax, 80004003h
0x180016c3f  mov     rcx, [rbp+57h+var_30]
0x180016c43  xor     rcx, rsp; StackCookie
0x180016c46  call    __security_check_cookie
0x180016c4b  lea     r11, [rsp+0B0h+var_20]
0x180016c53  mov     rbx, [r11+38h]
0x180016c57  mov     rsi, [r11+48h]
0x180016c5b  mov     rsp, r11
0x180016c5e  pop     r15
0x180016c60  pop     r14
0x180016c62  pop     r12
0x180016c64  pop     rdi
0x180016c65  pop     rbp
0x180016c66  retn
```
