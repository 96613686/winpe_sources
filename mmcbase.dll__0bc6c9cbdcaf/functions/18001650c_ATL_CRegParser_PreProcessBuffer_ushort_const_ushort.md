# ATL::CRegParser::PreProcessBuffer(ushort const *,ushort * *)

- ea: `0x18001650c`
- end: `0x18001672f`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEBGPEAPEAG@Z`
- size: `547`
- prototype: `int(ATL::CRegParser *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001684c`

## callees

- `0x180008d08`
- `0x180015428`
- `0x18001650c`
- `0x180016ad0`
- `0x180016b20`
- `0x18001b550`

## import_xrefs

- `USER32!CharNextW` at `0x1800165ca`
- `USER32!CharNextW` at `0x18001666f`
- `USER32!CharNextW` at `0x180016692`
- `USER32!CharNextW` at `0x1800165ca`
- `USER32!CharNextW` at `0x18001666f`
- `USER32!CharNextW` at `0x180016692`
- `KERNEL32!lstrcpynW` at `0x180016615`
- `KERNEL32!lstrcpynW` at `0x180016615`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016591`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800166ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800166e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016591`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800166ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800166e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001657f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001657f`

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
0x18001650c  mov     [rsp-8+arg_8], rbx
0x180016511  mov     [rsp-8+arg_18], rsi
0x180016516  push    rbp
0x180016517  push    rdi
0x180016518  push    r12
0x18001651a  push    r14
0x18001651c  push    r15
0x18001651e  lea     rbp, [rsp-37h]
0x180016523  sub     rsp, 90h
0x18001652a  mov     rax, cs:__security_cookie
0x180016531  xor     rax, rsp
0x180016534  mov     [rbp+57h+var_30], rax
0x180016538  xor     r15d, r15d
0x18001653b  mov     r14, r8
0x18001653e  mov     [rbp+57h+var_90], r15
0x180016542  mov     rbx, rdx
0x180016545  mov     rdi, rcx
0x180016548  test    rdx, rdx
0x18001654b  jz      loc_1800166F9
0x180016551  test    r8, r8
0x180016554  jz      loc_1800166F9
0x18001655a  mov     [r8], r15
0x18001655d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016561  mov     [rbp+57h+var_88], r15d
0x180016565  inc     rax
0x180016568  cmp     [rdx+rax*2], r15w
0x18001656d  jnz     short loc_180016565
0x18001656f  lea     eax, ds:2[rax*2]
0x180016576  movsxd  rcx, eax
0x180016579  add     rcx, rcx; cb
0x18001657c  mov     [rbp+57h+var_84], eax
0x18001657f  call    cs:__imp_CoTaskMemAlloc
0x180016585  mov     [rbp+57h+pv], rax
0x180016589  test    rax, rax
0x18001658c  jnz     short loc_1800165AA
0x18001658e  mov     rcx, rax; pv
0x180016591  call    cs:__imp_CoTaskMemFree
0x180016597  lea     rcx, [rbp+57h+var_90]
0x18001659b  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x1800165a0  mov     eax, 8007000Eh
0x1800165a5  jmp     loc_180016707
0x1800165aa  mov     [rdi], rbx
0x1800165ad  mov     r12d, 25h ; '%'
0x1800165b3  cmp     [rbx], r15w
0x1800165b7  jz      loc_1800166B1
0x1800165bd  cmp     [rbx], r12w
0x1800165c1  jnz     loc_18001667F
0x1800165c7  mov     rcx, rbx; lpsz
0x1800165ca  call    cs:__imp_CharNextW
0x1800165d0  mov     [rdi], rax
0x1800165d3  cmp     [rax], r12w
0x1800165d7  jnz     short loc_1800165E1
0x1800165d9  mov     rdx, rax
0x1800165dc  jmp     loc_180016682
0x1800165e1  mov     edx, r12d; unsigned __int16
0x1800165e4  mov     rcx, rax; lpsz
0x1800165e7  call    ?StrChrW@CRegParser@ATL@@KAPEBGPEBGG@Z; ATL::CRegParser::StrChrW(ushort const *,ushort)
0x1800165ec  mov     rsi, rax
0x1800165ef  test    rax, rax
0x1800165f2  jz      loc_1800166AA
0x1800165f8  mov     r8, rax
0x1800165fb  sub     r8, [rdi]
0x1800165fe  sar     r8, 1
0x180016601  cmp     r8d, 1Fh
0x180016605  jg      loc_1800166A3
0x18001660b  mov     rdx, [rdi]; lpString2
0x18001660e  lea     rcx, [rbp+57h+String1]; lpString1
0x180016612  inc     r8d; iMaxLength
0x180016615  call    cs:__imp_lstrcpynW
0x18001661b  mov     rcx, [rdi+8]; this
0x18001661f  lea     rdx, [rbp+57h+String1]; unsigned __int16 *
0x180016623  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x180016628  mov     rbx, rax
0x18001662b  test    rax, rax
0x18001662e  jz      short loc_1800166AA
0x180016630  mov     [rbp+57h+var_78], r15
0x180016634  cmp     [rbx], r15w
0x180016638  jz      short loc_180016655
0x18001663a  mov     rdx, rbx; unsigned __int16 *
0x18001663d  lea     rcx, [rbp+57h+var_88]; this
0x180016641  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEBG@Z; ATL::CRegParser::CParseBuffer::AddChar(ushort const *)
0x180016646  test    eax, eax
0x180016648  jz      short loc_180016650
0x18001664a  add     rbx, 2
0x18001664e  jmp     short loc_180016634
0x180016650  mov     ebx, r15d
0x180016653  jmp     short loc_18001665A
0x180016655  mov     ebx, 1
0x18001665a  lea     rcx, [rbp+57h+var_78]
0x18001665e  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180016663  test    ebx, ebx
0x180016665  jz      short loc_1800166C1
0x180016667  mov     rax, [rdi]
0x18001666a  jmp     short loc_180016678
0x18001666c  mov     rcx, rax; lpsz
0x18001666f  call    cs:__imp_CharNextW
0x180016675  mov     [rdi], rax
0x180016678  cmp     rax, rsi
0x18001667b  jnz     short loc_18001666C
0x18001667d  jmp     short loc_18001668F
0x18001667f  mov     rdx, rbx; unsigned __int16 *
0x180016682  lea     rcx, [rbp+57h+var_88]; this
0x180016686  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEBG@Z; ATL::CRegParser::CParseBuffer::AddChar(ushort const *)
0x18001668b  test    eax, eax
0x18001668d  jz      short loc_1800166C1
0x18001668f  mov     rcx, [rdi]; lpsz
0x180016692  call    cs:__imp_CharNextW
0x180016698  mov     rbx, rax
0x18001669b  mov     [rdi], rax
0x18001669e  jmp     loc_1800165B3
0x1800166a3  mov     ebx, 80004005h
0x1800166a8  jmp     short loc_1800166C6
0x1800166aa  mov     ebx, 80020009h
0x1800166af  jmp     short loc_1800166C6
0x1800166b1  mov     rdx, rbx; unsigned __int16 *
0x1800166b4  lea     rcx, [rbp+57h+var_88]; this
0x1800166b8  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEBG@Z; ATL::CRegParser::CParseBuffer::AddChar(ushort const *)
0x1800166bd  test    eax, eax
0x1800166bf  jnz     short loc_1800166DD
0x1800166c1  mov     ebx, 8007000Eh
0x1800166c6  mov     rcx, [rbp+57h+pv]; pv
0x1800166ca  call    cs:__imp_CoTaskMemFree
0x1800166d0  lea     rcx, [rbp+57h+var_90]
0x1800166d4  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x1800166d9  mov     eax, ebx
0x1800166db  jmp     short loc_180016707
0x1800166dd  mov     rax, [rbp+57h+pv]
0x1800166e1  xor     ecx, ecx; pv
0x1800166e3  mov     [r14], rax
0x1800166e6  call    cs:__imp_CoTaskMemFree
0x1800166ec  lea     rcx, [rbp+57h+var_90]
0x1800166f0  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x1800166f5  xor     eax, eax
0x1800166f7  jmp     short loc_180016707
0x1800166f9  lea     rcx, [rbp+57h+var_90]
0x1800166fd  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180016702  mov     eax, 80004003h
0x180016707  mov     rcx, [rbp+57h+var_30]
0x18001670b  xor     rcx, rsp; StackCookie
0x18001670e  call    __security_check_cookie
0x180016713  lea     r11, [rsp+0B0h+var_20]
0x18001671b  mov     rbx, [r11+38h]
0x18001671f  mov     rsi, [r11+48h]
0x180016723  mov     rsp, r11
0x180016726  pop     r15
0x180016728  pop     r14
0x18001672a  pop     r12
0x18001672c  pop     rdi
0x18001672d  pop     rbp
0x18001672e  retn
```
