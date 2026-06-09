# HTTPHeaders::additionalHeaders(ushort const *,ushort * *)

- ea: `0x1800dc1a0`
- end: `0x1800dc402`
- name: `?additionalHeaders@HTTPHeaders@@QEAAJPEBGPEAPEAG@Z`
- size: `610`
- prototype: `HRESULT __fastcall(HTTPHeaders *this, const wchar_t *pwszHeaders, wchar_t **ppwszAdditionalHeaders)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009e160`

## callees

- `0x18005d2c4`
- `0x18006ac44`
- `0x180084fa4`
- `0x18009402c`
- `0x18009fefc`
- `0x1800a3c08`
- `0x1800c6074`
- `0x1800dbfb4`
- `0x1800dc03c`
- `0x1800dc064`
- `0x1800dc158`
- `0x1800dc1a0`
- `0x1800dc408`
- `0x1800dc8bc`
- `0x18017c1d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dc310`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dc310`

## pseudocode

```c
__int64 __fastcall HTTPHeaders::additionalHeaders(
        HTTPHeaders *this,
        const wchar_t *pwszHeaders,
        wchar_t **ppwszAdditionalHeaders)
{
  signed int v5; // esi
  const wchar_t *v6; // rdx
  int length; // edi
  int v8; // ebx
  unsigned __int64 v9; // r12
  __int64 v10; // rsi
  HTTPHeader *data; // r14
  xstring::xinit v12; // r9d
  xstring::xinit v13; // r9d
  xstring::xinit v14; // r9d
  xstring::xinit v15; // r9d
  wchar_t *v16; // rax
  wchar_t *v17; // r15
  unsigned __int64 v18; // r12
  unsigned __int64 v19; // r13
  unsigned __int64 i; // r14
  unsigned __int64 cch; // rax
  unsigned __int64 v22; // rdi
  xstrings csHeaders; // [rsp+30h] [rbp-B8h] BYREF
  wchar_t *v25; // [rsp+58h] [rbp-90h]
  unsigned __int64 v26; // [rsp+60h] [rbp-88h]
  HTTPHeaders haCurrentHeaders; // [rsp+70h] [rbp-78h] BYREF
  unsigned __int64 cb; // [rsp+F0h] [rbp+8h] BYREF

  v5 = 0;
  HTTPHeaders::HTTPHeaders(&haCurrentHeaders);
  xstrings::xstrings(&csHeaders);
  cb = 0;
  length = this->_headers._length;
  if ( length )
  {
    HTTPHeaders::setAll(&haCurrentHeaders, v6, 0, 0);
    csHeaders._cchTotal = 0;
    if ( csHeaders._xss._data )
      xstrings::_free(csHeaders._xss._data);
    csHeaders._xss._data = new_array_ne<xstring>(4 * length);
    csHeaders._xss._allocated = 4 * length;
    csHeaders._xss._length = 0;
    v8 = 0;
    v9 = -1;
    while ( v8 < length )
    {
      v10 = v8;
      data = this->_headers._data;
      if ( HTTPHeaders::find(&haCurrentHeaders, data[v10]._pwszHeader, data[v10]._cchHeader) == -1 )
      {
        xstrings::append(&csHeaders, data[v10]._pwszHeader, data[v10]._cchHeader, v12);
        xstrings::append(&csHeaders, L": ", 2u, v13);
        xstrings::append(&csHeaders, data[v10]._pwszValue, data[v10]._cchValue, v14);
        xstrings::append(&csHeaders, L"\r\n", 2u, v15);
      }
      ++v8;
    }
    if ( csHeaders._cchTotal + 1 >= csHeaders._cchTotal )
      v9 = csHeaders._cchTotal + 1;
    v5 = csHeaders._cchTotal + 1 < csHeaders._cchTotal ? 0x80070216 : 0;
    if ( csHeaders._cchTotal + 1 >= csHeaders._cchTotal )
    {
      v5 = ULongLongMult(v9, 2u, &cb);
      if ( v5 >= 0 )
      {
        v16 = (wchar_t *)CoTaskMemAlloc(cb);
        v17 = v16;
        *ppwszAdditionalHeaders = v16;
        if ( v16 )
        {
          v25 = v16;
          v18 = v9 - 1;
          v19 = csHeaders._xss._length;
          for ( i = 0; ; ++i )
          {
            v26 = i;
            if ( i >= v19 || !v18 )
              break;
            cch = csHeaders._xss._data[i]._cch;
            if ( cch )
            {
              v22 = v18;
              if ( cch < v18 )
                v22 = csHeaders._xss._data[i]._cch;
              memcpy_0(v17, csHeaders._xss._data[i]._pwch, 2 * v22);
              v18 -= v22;
              v17 += v22;
              v25 = v17;
            }
          }
          *v17 = 0;
        }
      }
    }
  }
  xstrings::~xstrings(&csHeaders);
  HTTPHeaders::~HTTPHeaders(&haCurrentHeaders);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800dc1a0  mov     [rsp+arg_8], rbx
0x1800dc1a5  mov     [rsp+arg_10], rsi
0x1800dc1aa  push    rdi
0x1800dc1ab  push    r12
0x1800dc1ad  push    r13
0x1800dc1af  push    r14
0x1800dc1b1  push    r15
0x1800dc1b3  sub     rsp, 0C0h
0x1800dc1ba  mov     r13, ppwszAdditionalHeaders
0x1800dc1bd  mov     r15, this
0x1800dc1c0  xor     esi, esi
0x1800dc1c2  lea     this, [rsp+0E8h+haCurrentHeaders]; this
0x1800dc1c7  call    ??0HTTPHeaders@@QEAA@XZ; HTTPHeaders::HTTPHeaders(void)
0x1800dc1cc  lea     this, [rsp+0E8h+csHeaders]; this
0x1800dc1d1  call    ??0xstrings@@QEAA@XZ; xstrings::xstrings(void)
0x1800dc1d6  mov     [rsp+0E8h+cb], rsi
0x1800dc1de  mov     edi, [r15+18h]
0x1800dc1e2  test    edi, edi
0x1800dc1e4  jz      $CleanUp_187
0x1800dc1ea  xor     r9d, r9d; fAppendValues
0x1800dc1ed  xor     r8d, r8d; fResponse
0x1800dc1f0  lea     this, [rsp+0E8h+haCurrentHeaders]; this
0x1800dc1f5  call    ?setAll@HTTPHeaders@@QEAAJPEBG_N1@Z; HTTPHeaders::setAll(ushort const *,bool,bool)
0x1800dc1fa  lea     eax, ds:0[rdi*4]
0x1800dc201  movsxd  rbx, eax
0x1800dc204  mov     [rsp+0E8h+csHeaders._cchTotal], rsi
0x1800dc209  mov     this, [rsp+0E8h+csHeaders._xss._data]; pData
0x1800dc20e  test    this, this
0x1800dc211  jz      short loc_1800DC218
0x1800dc213  call    ?_free@xstrings@@SAXPEAVxstring@@@Z; xstrings::_free(xstring *)
0x1800dc218  mov     this, rbx; cch
0x1800dc21b  call    ??$new_array_ne@Vxstring@@@@YAPEAVxstring@@_J@Z; new_array_ne<xstring>(__int64)
0x1800dc220  mov     [rsp+0E8h+csHeaders._xss._data], rax
0x1800dc225  mov     [rsp+0E8h+csHeaders._xss._allocated], rbx
0x1800dc22a  mov     [rsp+0E8h+csHeaders._xss._length], 0
0x1800dc233  xor     ebx, ebx
0x1800dc235  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800dc239  mov     [rsp+0E8h+i], ebx
0x1800dc23d  cmp     ebx, edi
0x1800dc23f  jge     short loc_1800DC2C0
0x1800dc241  movsxd  rsi, ebx
0x1800dc244  shl     rsi, 5
0x1800dc248  mov     r14, [r15+20h]
0x1800dc24c  mov     r8d, [rsi+r14+8]; cchH
0x1800dc251  mov     pwszHeaders, [rsi+r14]; pwszH
0x1800dc255  lea     this, [rsp+0E8h+haCurrentHeaders]; this
0x1800dc25a  call    ?find@HTTPHeaders@@IEAAHPEBGH@Z; HTTPHeaders::find(ushort const *,int)
0x1800dc25f  cmp     eax, r12d
0x1800dc262  jnz     short loc_1800DC2B9
0x1800dc264  movsxd  ppwszAdditionalHeaders, dword ptr [rsi+r14+8]; cch
0x1800dc269  mov     pwszHeaders, [rsi+r14]; pwch
0x1800dc26d  lea     this, [rsp+0E8h+csHeaders]; this
0x1800dc272  call    ?append@xstrings@@QEAAXPEBG_KW4xinit@xstring@@@Z; xstrings::append(ushort const *,unsigned __int64,xstring::xinit)
0x1800dc277  mov     r8d, 2; cch
0x1800dc27d  lea     pwszHeaders, pwch; ": "
0x1800dc284  lea     this, [rsp+0E8h+csHeaders]; this
0x1800dc289  call    ?append@xstrings@@QEAAXPEBG_KW4xinit@xstring@@@Z; xstrings::append(ushort const *,unsigned __int64,xstring::xinit)
0x1800dc28e  movsxd  ppwszAdditionalHeaders, dword ptr [rsi+r14+18h]; cch
0x1800dc293  mov     pwszHeaders, [rsi+r14+10h]; pwch
0x1800dc298  lea     this, [rsp+0E8h+csHeaders]; this
0x1800dc29d  call    ?append@xstrings@@QEAAXPEBG_KW4xinit@xstring@@@Z; xstrings::append(ushort const *,unsigned __int64,xstring::xinit)
0x1800dc2a2  mov     r8d, 2; cch
0x1800dc2a8  lea     pwszHeaders, asc_1801CCB80; "\r\n"
0x1800dc2af  lea     this, [rsp+0E8h+csHeaders]; this
0x1800dc2b4  call    ?append@xstrings@@QEAAXPEBG_KW4xinit@xstring@@@Z; xstrings::append(ushort const *,unsigned __int64,xstring::xinit)
0x1800dc2b9  inc     ebx
0x1800dc2bb  jmp     loc_1800DC239
0x1800dc2c0  mov     this, [rsp+0E8h+csHeaders._cchTotal]
0x1800dc2c5  lea     rax, [this+1]
0x1800dc2c9  cmp     rax, this
0x1800dc2cc  cmovnb  r12, rax
0x1800dc2d0  sbb     esi, esi
0x1800dc2d2  and     esi, 80070216h
0x1800dc2d8  mov     [rsp+0E8h+hr], esi
0x1800dc2dc  cmp     rax, this
0x1800dc2df  jb      $CleanUp_187
0x1800dc2e5  lea     ppwszAdditionalHeaders, [rsp+0E8h+cb]; pullResult
0x1800dc2ed  mov     edx, 2; ullMultiplier
0x1800dc2f2  mov     this, r12; ullMultiplicand
0x1800dc2f5  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800dc2fa  mov     esi, eax
0x1800dc2fc  mov     [rsp+0E8h+hr], eax
0x1800dc300  test    eax, eax
0x1800dc302  js      $CleanUp_187
0x1800dc308  mov     this, [rsp+0E8h+cb]; cb
0x1800dc310  call    cs:__imp_CoTaskMemAlloc
0x1800dc317  nop     dword ptr [rax+rax+00h]
0x1800dc31c  mov     r15, rax
0x1800dc31f  mov     [r13+0], rax
0x1800dc323  test    rax, rax
0x1800dc326  jz      short loc_1800DC39C
0x1800dc328  mov     [rsp+0E8h+var_C0], r12
0x1800dc32d  mov     [rsp+0E8h+var_90], rax
0x1800dc332  dec     r12
0x1800dc335  mov     [rsp+0E8h+var_C0], r12
0x1800dc33a  mov     r13, [rsp+0E8h+csHeaders._xss._length]
0x1800dc33f  xor     r14d, r14d
0x1800dc342  mov     [rsp+0E8h+var_88], r14
0x1800dc347  cmp     r14, r13
0x1800dc34a  jnb     short loc_1800DC396
0x1800dc34c  test    r12, r12
0x1800dc34f  jz      short loc_1800DC396
0x1800dc351  lea     pwszHeaders, [r14+r14*2]
0x1800dc355  mov     this, [rsp+0E8h+csHeaders._xss._data]
0x1800dc35a  mov     rax, [this+pwszHeaders*8+8]
0x1800dc35f  test    rax, rax
0x1800dc362  jz      short loc_1800DC391
0x1800dc364  mov     rdi, r12
0x1800dc367  cmp     rax, r12
0x1800dc36a  cmovb   rdi, rax
0x1800dc36e  lea     rbx, [rdi+rdi]
0x1800dc372  mov     ppwszAdditionalHeaders, rbx; Size
0x1800dc375  mov     pwszHeaders, [this+pwszHeaders*8]; Src
0x1800dc379  mov     this, r15; void *
0x1800dc37c  call    memcpy_0
0x1800dc381  sub     r12, rdi
0x1800dc384  mov     [rsp+0E8h+var_C0], r12
0x1800dc389  add     r15, rbx
0x1800dc38c  mov     [rsp+0E8h+var_90], r15
0x1800dc391  inc     r14
0x1800dc394  jmp     short loc_1800DC342
0x1800dc396  xor     eax, eax
0x1800dc398  mov     [r15], ax
0x1800dc39c  jmp     short $CleanUp_187
0x1800dc39e  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x1800dc3a3  mov     ecx, cs:_tls_index
0x1800dc3a9  mov     rax, gs:58h
0x1800dc3b2  mov     edx, 8
0x1800dc3b7  mov     rax, [rax+this*8]
0x1800dc3bb  mov     this, [rax+pwszHeaders]
0x1800dc3bf  mov     this, [this+8]; e
0x1800dc3c3  call    ?setErrorInfoAndGetHR@_dispatchImpl@@SAJPEAVException@@@Z; _dispatchImpl::setErrorInfoAndGetHR(Exception *)
0x1800dc3c8  mov     esi, eax
0x1800dc3ca  mov     [rsp+0E8h+hr], eax
0x1800dc3ce  lea     this, [rsp+0E8h+csHeaders]; this
0x1800dc3d3  call    ??1xstrings@@QEAA@XZ; xstrings::~xstrings(void)
0x1800dc3d8  lea     this, [rsp+0E8h+haCurrentHeaders]; this
0x1800dc3dd  call    ??1HTTPHeaders@@UEAA@XZ; HTTPHeaders::~HTTPHeaders(void)
0x1800dc3e2  mov     eax, esi
0x1800dc3e4  lea     r11, [rsp+0E8h+var_28]
0x1800dc3ec  mov     rbx, [r11+38h]
0x1800dc3f0  mov     rsi, [r11+40h]
0x1800dc3f4  mov     rsp, r11
0x1800dc3f7  pop     r15
0x1800dc3f9  pop     r14
0x1800dc3fb  pop     r13
0x1800dc3fd  pop     r12
0x1800dc3ff  pop     rdi
0x1800dc400  retn
0x18018197e  push    rbp
0x180181980  sub     rsp, 20h
0x180181984  mov     rbp, rdx
0x180181987  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z
0x18018198c  nop
0x18018198d  add     rsp, 20h
0x180181991  pop     rbp
0x180181992  retn
```
