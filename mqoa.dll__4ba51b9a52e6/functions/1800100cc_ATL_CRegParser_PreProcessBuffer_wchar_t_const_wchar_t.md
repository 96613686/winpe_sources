# ATL::CRegParser::PreProcessBuffer(wchar_t const *,wchar_t * *)

- ea: `0x1800100cc`
- end: `0x18001034f`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEB_WPEAPEA_W@Z`
- size: `643`
- prototype: `int(ATL::CRegParser *__hidden this, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180011168`

## callees

- `0x18000aa00`
- `0x18000bb24`
- `0x1800100cc`
- `0x180012534`
- `0x180012584`
- `0x1800273b0`

## import_xrefs

- `KERNEL32!lstrcpynW` at `0x1800101f2`
- `KERNEL32!lstrcpynW` at `0x1800101f2`
- `USER32!CharNextW` at `0x18001018b`
- `USER32!CharNextW` at `0x180010250`
- `USER32!CharNextW` at `0x180010273`
- `USER32!CharNextW` at `0x18001018b`
- `USER32!CharNextW` at `0x180010250`
- `USER32!CharNextW` at `0x180010273`
- `ole32!CoTaskMemAlloc` at `0x18001013f`
- `ole32!CoTaskMemAlloc` at `0x18001013f`
- `ole32!CoTaskMemFree` at `0x180010151`
- `ole32!CoTaskMemFree` at `0x1800101b2`
- `ole32!CoTaskMemFree` at `0x180010288`
- `ole32!CoTaskMemFree` at `0x180010295`
- `ole32!CoTaskMemFree` at `0x1800102a2`
- `ole32!CoTaskMemFree` at `0x1800102b4`
- `ole32!CoTaskMemFree` at `0x1800102c6`
- `ole32!CoTaskMemFree` at `0x1800102e3`
- `ole32!CoTaskMemFree` at `0x180010305`
- `ole32!CoTaskMemFree` at `0x180010151`
- `ole32!CoTaskMemFree` at `0x1800101b2`
- `ole32!CoTaskMemFree` at `0x180010288`
- `ole32!CoTaskMemFree` at `0x180010295`
- `ole32!CoTaskMemFree` at `0x1800102a2`
- `ole32!CoTaskMemFree` at `0x1800102b4`
- `ole32!CoTaskMemFree` at `0x1800102c6`
- `ole32!CoTaskMemFree` at `0x1800102e3`
- `ole32!CoTaskMemFree` at `0x180010305`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(ATL::CRegParser *this, const wchar_t *a2, LPVOID *a3)
{
  const WCHAR *v4; // rbx
  __int64 v6; // rax
  const wchar_t *v8; // rax
  const wchar_t *v9; // rax
  const WCHAR *v10; // rsi
  __int64 v11; // r8
  const wchar_t *v12; // rbx
  int v13; // ebx
  const WCHAR *i; // rax
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-39h] BYREF
  int v17; // [rsp+24h] [rbp-35h]
  LPVOID pv; // [rsp+28h] [rbp-31h]
  __int64 v19; // [rsp+30h] [rbp-29h] BYREF
  __int64 v20; // [rsp+38h] [rbp-21h] BYREF
  WCHAR String1[32]; // [rsp+40h] [rbp-19h] BYREF

  v4 = a2;
  v19 = 0;
  if ( a2 && a3 )
  {
    *a3 = 0;
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    v16 = 0;
    v17 = 2 * v6 + 2;
    pv = CoTaskMemAlloc(2LL * v17);
    if ( pv )
    {
      *(_QWORD *)this = v4;
      while ( *v4 )
      {
        if ( *v4 == 37 )
        {
          v8 = CharNextW(v4);
          *(_QWORD *)this = v8;
          if ( *v8 == 37 )
          {
            if ( !(unsigned int)ATL::CRegParser::CParseBuffer::AddChar((ATL::CRegParser::CParseBuffer *)&v16, v8) )
              goto LABEL_35;
          }
          else
          {
            v9 = ATL::CRegParser::StrChrW(v8, 0x25u);
            v10 = v9;
            if ( !v9 )
              goto LABEL_32;
            v11 = ((__int64)v9 - *(_QWORD *)this) >> 1;
            if ( (int)v11 > 31 )
            {
              CoTaskMemFree(pv);
              v15 = -2147467259;
LABEL_36:
              ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v19);
              return v15;
            }
            lstrcpynW(String1, *(LPCWSTR *)this, v11 + 1);
            v12 = ATL::CRegObject::StrFromMap(*((ATL::CRegObject **)this + 1), String1);
            if ( !v12 )
            {
LABEL_32:
              CoTaskMemFree(pv);
              v15 = -2147352567;
              goto LABEL_36;
            }
            v20 = 0;
            while ( *v12 )
            {
              if ( !(unsigned int)ATL::CRegParser::CParseBuffer::AddChar((ATL::CRegParser::CParseBuffer *)&v16, v12) )
              {
                v13 = 0;
                goto LABEL_22;
              }
              ++v12;
            }
            v13 = 1;
LABEL_22:
            ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v20);
            if ( !v13 )
              goto LABEL_35;
            for ( i = *(const WCHAR **)this; i != v10; *(_QWORD *)this = i )
              i = CharNextW(i);
          }
        }
        else if ( !(unsigned int)ATL::CRegParser::CParseBuffer::AddChar((ATL::CRegParser::CParseBuffer *)&v16, v4) )
        {
          goto LABEL_35;
        }
        v4 = CharNextW(*(LPCWSTR *)this);
        *(_QWORD *)this = v4;
      }
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::AddChar((ATL::CRegParser::CParseBuffer *)&v16, v4) )
      {
LABEL_35:
        CoTaskMemFree(pv);
        v15 = -2147024882;
        goto LABEL_36;
      }
      *a3 = pv;
      CoTaskMemFree(0);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v19);
      return 0;
    }
    else
    {
      CoTaskMemFree(0);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v19);
      return 2147942414LL;
    }
  }
  else
  {
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v19);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800100cc  mov     [rsp-8+arg_8], rbx
0x1800100d1  mov     [rsp-8+arg_18], rsi
0x1800100d6  push    rbp
0x1800100d7  push    rdi
0x1800100d8  push    r12
0x1800100da  push    r14
0x1800100dc  push    r15
0x1800100de  lea     rbp, [rsp-37h]
0x1800100e3  sub     rsp, 90h
0x1800100ea  mov     rax, cs:__security_cookie
0x1800100f1  xor     rax, rsp
0x1800100f4  mov     [rbp+57h+var_30], rax
0x1800100f8  mov     r14, r8
0x1800100fb  mov     rbx, rdx
0x1800100fe  mov     rdi, rcx
0x180010101  xor     r15d, r15d
0x180010104  mov     [rbp+57h+var_80], r15
0x180010108  test    rdx, rdx
0x18001010b  jz      loc_180010319
0x180010111  test    r8, r8
0x180010114  jz      loc_180010319
0x18001011a  mov     [r8], r15
0x18001011d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010121  inc     rax
0x180010124  cmp     [rdx+rax*2], r15w
0x180010129  jnz     short loc_180010121
0x18001012b  lea     eax, ds:2[rax*2]
0x180010132  mov     [rbp+57h+var_90], r15d
0x180010136  mov     [rbp+57h+var_8C], eax
0x180010139  movsxd  rcx, eax
0x18001013c  add     rcx, rcx; cb
0x18001013f  call    cs:__imp_CoTaskMemAlloc
0x180010145  mov     [rbp+57h+pv], rax
0x180010149  test    rax, rax
0x18001014c  jnz     short loc_18001016B
0x18001014e  mov     rcx, rax; pv
0x180010151  call    cs:__imp_CoTaskMemFree
0x180010157  nop
0x180010158  lea     rcx, [rbp+57h+var_80]
0x18001015c  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180010161  mov     eax, 8007000Eh
0x180010166  jmp     loc_180010327
0x18001016b  mov     [rdi], rbx
0x18001016e  mov     r12d, 25h ; '%'
0x180010174  cmp     [rbx], r15w
0x180010178  jz      loc_1800102CF
0x18001017e  cmp     [rbx], r12w
0x180010182  jnz     loc_180010260
0x180010188  mov     rcx, rbx; lpsz
0x18001018b  call    cs:__imp_CharNextW
0x180010191  mov     [rdi], rax
0x180010194  cmp     [rax], r12w
0x180010198  jnz     short loc_1800101BE
0x18001019a  mov     rdx, rax; wchar_t *
0x18001019d  lea     rcx, [rbp+57h+var_90]; this
0x1800101a1  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEB_W@Z; ATL::CRegParser::CParseBuffer::AddChar(wchar_t const *)
0x1800101a6  test    eax, eax
0x1800101a8  jnz     loc_180010270
0x1800101ae  mov     rcx, [rbp+57h+pv]; pv
0x1800101b2  call    cs:__imp_CoTaskMemFree
0x1800101b8  nop
0x1800101b9  jmp     loc_1800102EA
0x1800101be  mov     edx, r12d; wchar_t
0x1800101c1  mov     rcx, rax; lpsz
0x1800101c4  call    ?StrChrW@CRegParser@ATL@@KAPEB_WPEB_W_W@Z; ATL::CRegParser::StrChrW(wchar_t const *,wchar_t)
0x1800101c9  mov     rsi, rax
0x1800101cc  test    rax, rax
0x1800101cf  jz      loc_1800102B0
0x1800101d5  mov     r8, rax
0x1800101d8  sub     r8, [rdi]
0x1800101db  sar     r8, 1
0x1800101de  cmp     r8d, 1Fh
0x1800101e2  jg      loc_18001029E
0x1800101e8  inc     r8d; iMaxLength
0x1800101eb  mov     rdx, [rdi]; lpString2
0x1800101ee  lea     rcx, [rbp+57h+String1]; lpString1
0x1800101f2  call    cs:__imp_lstrcpynW
0x1800101f8  lea     rdx, [rbp+57h+String1]; wchar_t *
0x1800101fc  mov     rcx, [rdi+8]; this
0x180010200  call    ?StrFromMap@CRegObject@ATL@@QEAAPEB_WPEA_W@Z; ATL::CRegObject::StrFromMap(wchar_t *)
0x180010205  mov     rbx, rax
0x180010208  test    rax, rax
0x18001020b  jz      loc_180010291
0x180010211  mov     [rbp+57h+var_78], r15
0x180010215  cmp     [rbx], r15w
0x180010219  jz      short loc_180010236
0x18001021b  mov     rdx, rbx; wchar_t *
0x18001021e  lea     rcx, [rbp+57h+var_90]; this
0x180010222  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEB_W@Z; ATL::CRegParser::CParseBuffer::AddChar(wchar_t const *)
0x180010227  test    eax, eax
0x180010229  jz      short loc_180010231
0x18001022b  add     rbx, 2
0x18001022f  jmp     short loc_180010215
0x180010231  mov     ebx, r15d
0x180010234  jmp     short loc_18001023B
0x180010236  mov     ebx, 1
0x18001023b  lea     rcx, [rbp+57h+var_78]
0x18001023f  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180010244  test    ebx, ebx
0x180010246  jz      short loc_180010284
0x180010248  mov     rax, [rdi]
0x18001024b  jmp     short loc_180010259
0x18001024d  mov     rcx, rax; lpsz
0x180010250  call    cs:__imp_CharNextW
0x180010256  mov     [rdi], rax
0x180010259  cmp     rax, rsi
0x18001025c  jnz     short loc_18001024D
0x18001025e  jmp     short loc_180010270
0x180010260  mov     rdx, rbx; wchar_t *
0x180010263  lea     rcx, [rbp+57h+var_90]; this
0x180010267  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEB_W@Z; ATL::CRegParser::CParseBuffer::AddChar(wchar_t const *)
0x18001026c  test    eax, eax
0x18001026e  jz      short loc_1800102C2
0x180010270  mov     rcx, [rdi]; lpsz
0x180010273  call    cs:__imp_CharNextW
0x180010279  mov     rbx, rax
0x18001027c  mov     [rdi], rax
0x18001027f  jmp     loc_180010174
0x180010284  mov     rcx, [rbp+57h+pv]; pv
0x180010288  call    cs:__imp_CoTaskMemFree
0x18001028e  nop
0x18001028f  jmp     short loc_1800102EA
0x180010291  mov     rcx, [rbp+57h+pv]; pv
0x180010295  call    cs:__imp_CoTaskMemFree
0x18001029b  nop
0x18001029c  jmp     short loc_1800102BB
0x18001029e  mov     rcx, [rbp+57h+pv]; pv
0x1800102a2  call    cs:__imp_CoTaskMemFree
0x1800102a8  nop
0x1800102a9  mov     ebx, 80004005h
0x1800102ae  jmp     short loc_1800102EF
0x1800102b0  mov     rcx, [rbp+57h+pv]; pv
0x1800102b4  call    cs:__imp_CoTaskMemFree
0x1800102ba  nop
0x1800102bb  mov     ebx, 80020009h
0x1800102c0  jmp     short loc_1800102EF
0x1800102c2  mov     rcx, [rbp+57h+pv]; pv
0x1800102c6  call    cs:__imp_CoTaskMemFree
0x1800102cc  nop
0x1800102cd  jmp     short loc_1800102EA
0x1800102cf  mov     rdx, rbx; wchar_t *
0x1800102d2  lea     rcx, [rbp+57h+var_90]; this
0x1800102d6  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEB_W@Z; ATL::CRegParser::CParseBuffer::AddChar(wchar_t const *)
0x1800102db  test    eax, eax
0x1800102dd  jnz     short loc_1800102FC
0x1800102df  mov     rcx, [rbp+57h+pv]; pv
0x1800102e3  call    cs:__imp_CoTaskMemFree
0x1800102e9  nop
0x1800102ea  mov     ebx, 8007000Eh
0x1800102ef  lea     rcx, [rbp+57h+var_80]
0x1800102f3  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x1800102f8  mov     eax, ebx
0x1800102fa  jmp     short loc_180010327
0x1800102fc  mov     rax, [rbp+57h+pv]
0x180010300  mov     [r14], rax
0x180010303  xor     ecx, ecx; pv
0x180010305  call    cs:__imp_CoTaskMemFree
0x18001030b  nop
0x18001030c  lea     rcx, [rbp+57h+var_80]
0x180010310  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180010315  xor     eax, eax
0x180010317  jmp     short loc_180010327
0x180010319  lea     rcx, [rbp+57h+var_80]
0x18001031d  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180010322  mov     eax, 80004003h
0x180010327  mov     rcx, [rbp+57h+var_30]
0x18001032b  xor     rcx, rsp; StackCookie
0x18001032e  call    __security_check_cookie
0x180010333  lea     r11, [rsp+0B0h+var_20]
0x18001033b  mov     rbx, [r11+38h]
0x18001033f  mov     rsi, [r11+48h]
0x180010343  mov     rsp, r11
0x180010346  pop     r15
0x180010348  pop     r14
0x18001034a  pop     r12
0x18001034c  pop     rdi
0x18001034d  pop     rbp
0x18001034e  retn
```
