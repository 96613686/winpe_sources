# ATL::CRegParser::PreProcessBuffer(ushort const *,ushort * *)

- ea: `0x180013b74`
- end: `0x180013df7`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEBGPEAPEAG@Z`
- size: `643`
- prototype: `int(ATL::CRegParser *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001418c`

## callees

- `0x18000b2d8`
- `0x18001153c`
- `0x180013b74`
- `0x180014d34`
- `0x180014d84`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013bf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013dad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013bf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013c5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013d8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013dad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013be7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013be7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180013c33`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180013cf8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180013d1b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180013c33`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180013cf8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180013d1b`
- `KERNEL32!lstrcpynW` at `0x180013c9a`
- `KERNEL32!lstrcpynW` at `0x180013c9a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(ATL::CRegParser *this, const unsigned __int16 *a2, LPVOID *a3)
{
  const WCHAR *v4; // rbx
  __int64 v6; // rax
  const unsigned __int16 *v8; // rax
  const unsigned __int16 *v9; // rax
  const unsigned __int16 *v10; // rsi
  __int64 v11; // r8
  const unsigned __int16 *v12; // rbx
  int v13; // ebx
  const WCHAR *i; // rax
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-39h] BYREF
  int v17; // [rsp+24h] [rbp-35h]
  LPVOID pv; // [rsp+28h] [rbp-31h]
  _QWORD *v19; // [rsp+30h] [rbp-29h] BYREF
  _QWORD *v20; // [rsp+38h] [rbp-21h] BYREF
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
0x180013b74  mov     [rsp-8+arg_8], rbx
0x180013b79  mov     [rsp-8+arg_18], rsi
0x180013b7e  push    rbp
0x180013b7f  push    rdi
0x180013b80  push    r12
0x180013b82  push    r14
0x180013b84  push    r15
0x180013b86  lea     rbp, [rsp-37h]
0x180013b8b  sub     rsp, 90h
0x180013b92  mov     rax, cs:__security_cookie
0x180013b99  xor     rax, rsp
0x180013b9c  mov     [rbp+57h+var_30], rax
0x180013ba0  mov     r14, r8
0x180013ba3  mov     rbx, rdx
0x180013ba6  mov     rdi, rcx
0x180013ba9  xor     r15d, r15d
0x180013bac  mov     [rbp+57h+var_80], r15
0x180013bb0  test    rdx, rdx
0x180013bb3  jz      loc_180013DC1
0x180013bb9  test    r8, r8
0x180013bbc  jz      loc_180013DC1
0x180013bc2  mov     [r8], r15
0x180013bc5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013bc9  inc     rax
0x180013bcc  cmp     [rdx+rax*2], r15w
0x180013bd1  jnz     short loc_180013BC9
0x180013bd3  lea     eax, ds:2[rax*2]
0x180013bda  mov     [rbp+57h+var_90], r15d
0x180013bde  mov     [rbp+57h+var_8C], eax
0x180013be1  movsxd  rcx, eax
0x180013be4  add     rcx, rcx; cb
0x180013be7  call    cs:__imp_CoTaskMemAlloc
0x180013bed  mov     [rbp+57h+pv], rax
0x180013bf1  test    rax, rax
0x180013bf4  jnz     short loc_180013C13
0x180013bf6  mov     rcx, rax; pv
0x180013bf9  call    cs:__imp_CoTaskMemFree
0x180013bff  nop
0x180013c00  lea     rcx, [rbp+57h+var_80]
0x180013c04  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180013c09  mov     eax, 8007000Eh
0x180013c0e  jmp     loc_180013DCF
0x180013c13  mov     [rdi], rbx
0x180013c16  mov     r12d, 25h ; '%'
0x180013c1c  cmp     [rbx], r15w
0x180013c20  jz      loc_180013D77
0x180013c26  cmp     [rbx], r12w
0x180013c2a  jnz     loc_180013D08
0x180013c30  mov     rcx, rbx; lpsz
0x180013c33  call    cs:__imp_CharNextW
0x180013c39  mov     [rdi], rax
0x180013c3c  cmp     [rax], r12w
0x180013c40  jnz     short loc_180013C66
0x180013c42  mov     rdx, rax; unsigned __int16 *
0x180013c45  lea     rcx, [rbp+57h+var_90]; this
0x180013c49  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEBG@Z; ATL::CRegParser::CParseBuffer::AddChar(ushort const *)
0x180013c4e  test    eax, eax
0x180013c50  jnz     loc_180013D18
0x180013c56  mov     rcx, [rbp+57h+pv]; pv
0x180013c5a  call    cs:__imp_CoTaskMemFree
0x180013c60  nop
0x180013c61  jmp     loc_180013D92
0x180013c66  mov     edx, r12d; unsigned __int16
0x180013c69  mov     rcx, rax; lpsz
0x180013c6c  call    ?StrChrW@CRegParser@ATL@@KAPEBGPEBGG@Z; ATL::CRegParser::StrChrW(ushort const *,ushort)
0x180013c71  mov     rsi, rax
0x180013c74  test    rax, rax
0x180013c77  jz      loc_180013D58
0x180013c7d  mov     r8, rax
0x180013c80  sub     r8, [rdi]
0x180013c83  sar     r8, 1
0x180013c86  cmp     r8d, 1Fh
0x180013c8a  jg      loc_180013D46
0x180013c90  inc     r8d; iMaxLength
0x180013c93  mov     rdx, [rdi]; lpString2
0x180013c96  lea     rcx, [rbp+57h+String1]; lpString1
0x180013c9a  call    cs:__imp_lstrcpynW
0x180013ca0  lea     rdx, [rbp+57h+String1]; unsigned __int16 *
0x180013ca4  mov     rcx, [rdi+8]; this
0x180013ca8  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x180013cad  mov     rbx, rax
0x180013cb0  test    rax, rax
0x180013cb3  jz      loc_180013D39
0x180013cb9  mov     [rbp+57h+var_78], r15
0x180013cbd  cmp     [rbx], r15w
0x180013cc1  jz      short loc_180013CDE
0x180013cc3  mov     rdx, rbx; unsigned __int16 *
0x180013cc6  lea     rcx, [rbp+57h+var_90]; this
0x180013cca  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEBG@Z; ATL::CRegParser::CParseBuffer::AddChar(ushort const *)
0x180013ccf  test    eax, eax
0x180013cd1  jz      short loc_180013CD9
0x180013cd3  add     rbx, 2
0x180013cd7  jmp     short loc_180013CBD
0x180013cd9  mov     ebx, r15d
0x180013cdc  jmp     short loc_180013CE3
0x180013cde  mov     ebx, 1
0x180013ce3  lea     rcx, [rbp+57h+var_78]
0x180013ce7  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180013cec  test    ebx, ebx
0x180013cee  jz      short loc_180013D2C
0x180013cf0  mov     rax, [rdi]
0x180013cf3  jmp     short loc_180013D01
0x180013cf5  mov     rcx, rax; lpsz
0x180013cf8  call    cs:__imp_CharNextW
0x180013cfe  mov     [rdi], rax
0x180013d01  cmp     rax, rsi
0x180013d04  jnz     short loc_180013CF5
0x180013d06  jmp     short loc_180013D18
0x180013d08  mov     rdx, rbx; unsigned __int16 *
0x180013d0b  lea     rcx, [rbp+57h+var_90]; this
0x180013d0f  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEBG@Z; ATL::CRegParser::CParseBuffer::AddChar(ushort const *)
0x180013d14  test    eax, eax
0x180013d16  jz      short loc_180013D6A
0x180013d18  mov     rcx, [rdi]; lpsz
0x180013d1b  call    cs:__imp_CharNextW
0x180013d21  mov     rbx, rax
0x180013d24  mov     [rdi], rax
0x180013d27  jmp     loc_180013C1C
0x180013d2c  mov     rcx, [rbp+57h+pv]; pv
0x180013d30  call    cs:__imp_CoTaskMemFree
0x180013d36  nop
0x180013d37  jmp     short loc_180013D92
0x180013d39  mov     rcx, [rbp+57h+pv]; pv
0x180013d3d  call    cs:__imp_CoTaskMemFree
0x180013d43  nop
0x180013d44  jmp     short loc_180013D63
0x180013d46  mov     rcx, [rbp+57h+pv]; pv
0x180013d4a  call    cs:__imp_CoTaskMemFree
0x180013d50  nop
0x180013d51  mov     ebx, 80004005h
0x180013d56  jmp     short loc_180013D97
0x180013d58  mov     rcx, [rbp+57h+pv]; pv
0x180013d5c  call    cs:__imp_CoTaskMemFree
0x180013d62  nop
0x180013d63  mov     ebx, 80020009h
0x180013d68  jmp     short loc_180013D97
0x180013d6a  mov     rcx, [rbp+57h+pv]; pv
0x180013d6e  call    cs:__imp_CoTaskMemFree
0x180013d74  nop
0x180013d75  jmp     short loc_180013D92
0x180013d77  mov     rdx, rbx; unsigned __int16 *
0x180013d7a  lea     rcx, [rbp+57h+var_90]; this
0x180013d7e  call    ?AddChar@CParseBuffer@CRegParser@ATL@@QEAAHPEBG@Z; ATL::CRegParser::CParseBuffer::AddChar(ushort const *)
0x180013d83  test    eax, eax
0x180013d85  jnz     short loc_180013DA4
0x180013d87  mov     rcx, [rbp+57h+pv]; pv
0x180013d8b  call    cs:__imp_CoTaskMemFree
0x180013d91  nop
0x180013d92  mov     ebx, 8007000Eh
0x180013d97  lea     rcx, [rbp+57h+var_80]
0x180013d9b  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180013da0  mov     eax, ebx
0x180013da2  jmp     short loc_180013DCF
0x180013da4  mov     rax, [rbp+57h+pv]
0x180013da8  mov     [r14], rax
0x180013dab  xor     ecx, ecx; pv
0x180013dad  call    cs:__imp_CoTaskMemFree
0x180013db3  nop
0x180013db4  lea     rcx, [rbp+57h+var_80]
0x180013db8  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180013dbd  xor     eax, eax
0x180013dbf  jmp     short loc_180013DCF
0x180013dc1  lea     rcx, [rbp+57h+var_80]
0x180013dc5  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180013dca  mov     eax, 80004003h
0x180013dcf  mov     rcx, [rbp+57h+var_30]
0x180013dd3  xor     rcx, rsp; StackCookie
0x180013dd6  call    __security_check_cookie
0x180013ddb  lea     r11, [rsp+0B0h+var_20]
0x180013de3  mov     rbx, [r11+38h]
0x180013de7  mov     rsi, [r11+48h]
0x180013deb  mov     rsp, r11
0x180013dee  pop     r15
0x180013df0  pop     r14
0x180013df2  pop     r12
0x180013df4  pop     rdi
0x180013df5  pop     rbp
0x180013df6  retn
```
