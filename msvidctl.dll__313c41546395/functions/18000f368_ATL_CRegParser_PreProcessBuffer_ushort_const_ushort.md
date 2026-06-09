# ATL::CRegParser::PreProcessBuffer(ushort const *,ushort * *)

- ea: `0x18000f368`
- end: `0x18000f58b`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEBGPEAPEAG@Z`
- size: `547`
- prototype: `int(ATL::CRegParser *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000dcf8`
- `0x1800125a8`

## callees

- `0x180004640`
- `0x180006b08`
- `0x18000e37c`
- `0x18000f368`
- `0x18000fa14`
- `0x18000fa64`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000f3db`
- `ole32!CoTaskMemAlloc` at `0x18000f3db`
- `ole32!CoTaskMemFree` at `0x18000f3ed`
- `ole32!CoTaskMemFree` at `0x18000f526`
- `ole32!CoTaskMemFree` at `0x18000f542`
- `ole32!CoTaskMemFree` at `0x18000f3ed`
- `ole32!CoTaskMemFree` at `0x18000f526`
- `ole32!CoTaskMemFree` at `0x18000f542`
- `KERNEL32!lstrcpynW` at `0x18000f471`
- `KERNEL32!lstrcpynW` at `0x18000f471`
- `USER32!CharNextW` at `0x18000f426`
- `USER32!CharNextW` at `0x18000f4cb`
- `USER32!CharNextW` at `0x18000f4ee`
- `USER32!CharNextW` at `0x18000f426`
- `USER32!CharNextW` at `0x18000f4cb`
- `USER32!CharNextW` at `0x18000f4ee`

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
  __int64 v17; // [rsp+20h] [rbp-39h] BYREF
  int v18; // [rsp+28h] [rbp-31h] BYREF
  int v19; // [rsp+2Ch] [rbp-2Dh]
  LPVOID pv; // [rsp+30h] [rbp-29h]
  __int64 v21; // [rsp+38h] [rbp-21h] BYREF
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
0x18000f368  mov     [rsp-8+arg_8], rbx
0x18000f36d  mov     [rsp-8+arg_18], rsi
0x18000f372  push    rbp
0x18000f373  push    rdi
0x18000f374  push    r12
0x18000f376  push    r14
0x18000f378  push    r15
0x18000f37a  lea     rbp, [rsp-37h]
0x18000f37f  sub     rsp, 90h
0x18000f386  mov     rax, cs:__security_cookie
0x18000f38d  xor     rax, rsp
0x18000f390  mov     [rbp+57h+var_30], rax
0x18000f394  xor     r15d, r15d
0x18000f397  mov     r14, r8
0x18000f39a  mov     [rbp+57h+var_90], r15
0x18000f39e  mov     rbx, rdx
0x18000f3a1  mov     rdi, rcx
0x18000f3a4  test    rdx, rdx
0x18000f3a7  jz      loc_18000F555
0x18000f3ad  test    r8, r8
0x18000f3b0  jz      loc_18000F555
0x18000f3b6  mov     [r8], r15
0x18000f3b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f3bd  mov     [rbp+57h+var_88], r15d
0x18000f3c1  inc     rax
0x18000f3c4  cmp     [rdx+rax*2], r15w
0x18000f3c9  jnz     short loc_18000F3C1
0x18000f3cb  lea     eax, ds:2[rax*2]
0x18000f3d2  movsxd  rcx, eax
0x18000f3d5  add     rcx, rcx; cb
0x18000f3d8  mov     [rbp+57h+var_84], eax
0x18000f3db  call    cs:__imp_CoTaskMemAlloc
0x18000f3e1  mov     [rbp+57h+pv], rax
0x18000f3e5  test    rax, rax
0x18000f3e8  jnz     short loc_18000F406
0x18000f3ea  mov     rcx, rax; pv
0x18000f3ed  call    cs:__imp_CoTaskMemFree
0x18000f3f3  lea     rcx, [rbp+57h+var_90]
0x18000f3f7  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x18000f3fc  mov     eax, 8007000Eh
0x18000f401  jmp     loc_18000F563
0x18000f406  mov     [rdi], rbx
0x18000f409  mov     r12d, 25h ; '%'
0x18000f40f  cmp     [rbx], r15w
0x18000f413  jz      loc_18000F50D
0x18000f419  cmp     [rbx], r12w
0x18000f41d  jnz     loc_18000F4DB
0x18000f423  mov     rcx, rbx; lpsz
0x18000f426  call    cs:__imp_CharNextW
0x18000f42c  mov     [rdi], rax
0x18000f42f  cmp     [rax], r12w
0x18000f433  jnz     short loc_18000F43D
0x18000f435  mov     rdx, rax
0x18000f438  jmp     loc_18000F4DE
0x18000f43d  mov     edx, r12d; unsigned __int16
0x18000f440  mov     rcx, rax; lpsz
0x18000f443  call    ?StrChrW@CRegParser@ATL@@KAPEBGPEBGG@Z; ATL::CRegParser::StrChrW(ushort const *,ushort)
0x18000f448  mov     rsi, rax
0x18000f44b  test    rax, rax
0x18000f44e  jz      loc_18000F506
0x18000f454  mov     r8, rax
0x18000f457  sub     r8, [rdi]
0x18000f45a  sar     r8, 1
0x18000f45d  cmp     r8d, 1Fh
0x18000f461  jg      loc_18000F4FF
0x18000f467  mov     rdx, [rdi]; lpString2
0x18000f46a  lea     rcx, [rbp+57h+String1]; lpString1
0x18000f46e  inc     r8d; iMaxLength
0x18000f471  call    cs:__imp_lstrcpynW
0x18000f477  mov     rcx, [rdi+8]; this
0x18000f47b  lea     rdx, [rbp+57h+String1]; unsigned __int16 *
0x18000f47f  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x18000f484  mov     rbx, rax
0x18000f487  test    rax, rax
0x18000f48a  jz      short loc_18000F506
0x18000f48c  mov     [rbp+57h+var_78], r15
0x18000f490  cmp     [rbx], r15w
0x18000f494  jz      short loc_18000F4B1
0x18000f496  mov     rdx, rbx; unsigned __int16 *
0x18000f499  lea     rcx, [rbp+57h+var_88]; this
0x18000f49d  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEBG@Z; ATL::CRegParser::CParseBuffer::AddChar(ushort const *)
0x18000f4a2  test    eax, eax
0x18000f4a4  jz      short loc_18000F4AC
0x18000f4a6  add     rbx, 2
0x18000f4aa  jmp     short loc_18000F490
0x18000f4ac  mov     ebx, r15d
0x18000f4af  jmp     short loc_18000F4B6
0x18000f4b1  mov     ebx, 1
0x18000f4b6  lea     rcx, [rbp+57h+var_78]
0x18000f4ba  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x18000f4bf  test    ebx, ebx
0x18000f4c1  jz      short loc_18000F51D
0x18000f4c3  mov     rax, [rdi]
0x18000f4c6  jmp     short loc_18000F4D4
0x18000f4c8  mov     rcx, rax; lpsz
0x18000f4cb  call    cs:__imp_CharNextW
0x18000f4d1  mov     [rdi], rax
0x18000f4d4  cmp     rax, rsi
0x18000f4d7  jnz     short loc_18000F4C8
0x18000f4d9  jmp     short loc_18000F4EB
0x18000f4db  mov     rdx, rbx; unsigned __int16 *
0x18000f4de  lea     rcx, [rbp+57h+var_88]; this
0x18000f4e2  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEBG@Z; ATL::CRegParser::CParseBuffer::AddChar(ushort const *)
0x18000f4e7  test    eax, eax
0x18000f4e9  jz      short loc_18000F51D
0x18000f4eb  mov     rcx, [rdi]; lpsz
0x18000f4ee  call    cs:__imp_CharNextW
0x18000f4f4  mov     rbx, rax
0x18000f4f7  mov     [rdi], rax
0x18000f4fa  jmp     loc_18000F40F
0x18000f4ff  mov     ebx, 80004005h
0x18000f504  jmp     short loc_18000F522
0x18000f506  mov     ebx, 80020009h
0x18000f50b  jmp     short loc_18000F522
0x18000f50d  mov     rdx, rbx; unsigned __int16 *
0x18000f510  lea     rcx, [rbp+57h+var_88]; this
0x18000f514  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEBG@Z; ATL::CRegParser::CParseBuffer::AddChar(ushort const *)
0x18000f519  test    eax, eax
0x18000f51b  jnz     short loc_18000F539
0x18000f51d  mov     ebx, 8007000Eh
0x18000f522  mov     rcx, [rbp+57h+pv]; pv
0x18000f526  call    cs:__imp_CoTaskMemFree
0x18000f52c  lea     rcx, [rbp+57h+var_90]
0x18000f530  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x18000f535  mov     eax, ebx
0x18000f537  jmp     short loc_18000F563
0x18000f539  mov     rax, [rbp+57h+pv]
0x18000f53d  xor     ecx, ecx; pv
0x18000f53f  mov     [r14], rax
0x18000f542  call    cs:__imp_CoTaskMemFree
0x18000f548  lea     rcx, [rbp+57h+var_90]
0x18000f54c  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x18000f551  xor     eax, eax
0x18000f553  jmp     short loc_18000F563
0x18000f555  lea     rcx, [rbp+57h+var_90]
0x18000f559  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x18000f55e  mov     eax, 80004003h
0x18000f563  mov     rcx, [rbp+57h+var_30]
0x18000f567  xor     rcx, rsp; StackCookie
0x18000f56a  call    __security_check_cookie
0x18000f56f  lea     r11, [rsp+0B0h+var_20]
0x18000f577  mov     rbx, [r11+38h]
0x18000f57b  mov     rsi, [r11+48h]
0x18000f57f  mov     rsp, r11
0x18000f582  pop     r15
0x18000f584  pop     r14
0x18000f586  pop     r12
0x18000f588  pop     rdi
0x18000f589  pop     rbp
0x18000f58a  retn
```
