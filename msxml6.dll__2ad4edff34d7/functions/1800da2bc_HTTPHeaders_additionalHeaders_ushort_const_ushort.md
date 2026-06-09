# HTTPHeaders::additionalHeaders(ushort const *,ushort * *)

- ea: `0x1800da2bc`
- end: `0x1800da517`
- name: `?additionalHeaders@HTTPHeaders@@QEAAJPEBGPEAPEAG@Z`
- size: `603`
- prototype: `__int64 __fastcall(HTTPHeaders *this, const wchar_t *pwszHeaders, wchar_t **ppwszAdditionalHeaders)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009d924`

## callees

- `0x18002b064`
- `0x18005ac64`
- `0x18006443c`
- `0x180086880`
- `0x18009f718`
- `0x1800a3e04`
- `0x1800c491c`
- `0x1800da0d0`
- `0x1800da158`
- `0x1800da180`
- `0x1800da274`
- `0x1800da2bc`
- `0x1800da520`
- `0x1800da9d0`
- `0x180178528`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800da42c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800da42c`

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
0x1800da2bc  mov     [rsp+arg_8], rbx
0x1800da2c1  mov     [rsp+arg_10], rsi
0x1800da2c6  push    rdi
0x1800da2c7  push    r12
0x1800da2c9  push    r13
0x1800da2cb  push    r14
0x1800da2cd  push    r15
0x1800da2cf  sub     rsp, 0C0h
0x1800da2d6  mov     r13, ppwszAdditionalHeaders
0x1800da2d9  mov     r15, this
0x1800da2dc  xor     esi, esi
0x1800da2de  lea     this, [rsp+0E8h+haCurrentHeaders]; this
0x1800da2e3  call    ??0HTTPHeaders@@QEAA@XZ; HTTPHeaders::HTTPHeaders(void)
0x1800da2e8  lea     this, [rsp+0E8h+csHeaders]; this
0x1800da2ed  call    ??0xstrings@@QEAA@XZ; xstrings::xstrings(void)
0x1800da2f2  mov     [rsp+0E8h+cb], rsi
0x1800da2fa  mov     edi, [r15+18h]
0x1800da2fe  test    edi, edi
0x1800da300  jz      $CleanUp_187
0x1800da306  xor     r9d, r9d; fAppendValues
0x1800da309  xor     r8d, r8d; fResponse
0x1800da30c  lea     this, [rsp+0E8h+haCurrentHeaders]; this
0x1800da311  call    ?setAll@HTTPHeaders@@QEAAJPEBG_N1@Z; HTTPHeaders::setAll(ushort const *,bool,bool)
0x1800da316  lea     eax, ds:0[rdi*4]
0x1800da31d  movsxd  rbx, eax
0x1800da320  mov     [rsp+0E8h+csHeaders._cchTotal], rsi
0x1800da325  mov     this, [rsp+0E8h+csHeaders._xss._data]; pData
0x1800da32a  test    this, this
0x1800da32d  jz      short loc_1800DA334
0x1800da32f  call    ?_free@xstrings@@SAXPEAVxstring@@@Z; xstrings::_free(xstring *)
0x1800da334  mov     this, rbx; cch
0x1800da337  call    ??$new_array_ne@Vxstring@@@@YAPEAVxstring@@_J@Z; new_array_ne<xstring>(__int64)
0x1800da33c  mov     [rsp+0E8h+csHeaders._xss._data], rax
0x1800da341  mov     [rsp+0E8h+csHeaders._xss._allocated], rbx
0x1800da346  mov     [rsp+0E8h+csHeaders._xss._length], 0
0x1800da34f  xor     ebx, ebx
0x1800da351  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800da355  mov     [rsp+0E8h+i], ebx
0x1800da359  cmp     ebx, edi
0x1800da35b  jge     short loc_1800DA3DC
0x1800da35d  movsxd  rsi, ebx
0x1800da360  shl     rsi, 5
0x1800da364  mov     r14, [r15+20h]
0x1800da368  mov     r8d, [rsi+r14+8]; cchH
0x1800da36d  mov     pwszHeaders, [rsi+r14]; pwszH
0x1800da371  lea     this, [rsp+0E8h+haCurrentHeaders]; this
0x1800da376  call    ?find@HTTPHeaders@@IEAAHPEBGH@Z; HTTPHeaders::find(ushort const *,int)
0x1800da37b  cmp     eax, r12d
0x1800da37e  jnz     short loc_1800DA3D5
0x1800da380  movsxd  ppwszAdditionalHeaders, dword ptr [rsi+r14+8]; cch
0x1800da385  mov     pwszHeaders, [rsi+r14]; pwch
0x1800da389  lea     this, [rsp+0E8h+csHeaders]; this
0x1800da38e  call    ?append@xstrings@@QEAAXPEBG_KW4xinit@xstring@@@Z; xstrings::append(ushort const *,unsigned __int64,xstring::xinit)
0x1800da393  mov     r8d, 2; cch
0x1800da399  lea     pwszHeaders, pwch; ": "
0x1800da3a0  lea     this, [rsp+0E8h+csHeaders]; this
0x1800da3a5  call    ?append@xstrings@@QEAAXPEBG_KW4xinit@xstring@@@Z; xstrings::append(ushort const *,unsigned __int64,xstring::xinit)
0x1800da3aa  movsxd  ppwszAdditionalHeaders, dword ptr [rsi+r14+18h]; cch
0x1800da3af  mov     pwszHeaders, [rsi+r14+10h]; pwch
0x1800da3b4  lea     this, [rsp+0E8h+csHeaders]; this
0x1800da3b9  call    ?append@xstrings@@QEAAXPEBG_KW4xinit@xstring@@@Z; xstrings::append(ushort const *,unsigned __int64,xstring::xinit)
0x1800da3be  mov     r8d, 2; cch
0x1800da3c4  lea     pwszHeaders, asc_1801C8B80; "\r\n"
0x1800da3cb  lea     this, [rsp+0E8h+csHeaders]; this
0x1800da3d0  call    ?append@xstrings@@QEAAXPEBG_KW4xinit@xstring@@@Z; xstrings::append(ushort const *,unsigned __int64,xstring::xinit)
0x1800da3d5  inc     ebx
0x1800da3d7  jmp     loc_1800DA355
0x1800da3dc  mov     this, [rsp+0E8h+csHeaders._cchTotal]
0x1800da3e1  lea     rax, [this+1]
0x1800da3e5  cmp     rax, this
0x1800da3e8  cmovnb  r12, rax
0x1800da3ec  sbb     esi, esi
0x1800da3ee  and     esi, 80070216h
0x1800da3f4  mov     [rsp+0E8h+hr], esi
0x1800da3f8  cmp     rax, this
0x1800da3fb  jb      $CleanUp_187
0x1800da401  lea     ppwszAdditionalHeaders, [rsp+0E8h+cb]; pullResult
0x1800da409  mov     edx, 2; ullMultiplier
0x1800da40e  mov     this, r12; ullMultiplicand
0x1800da411  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800da416  mov     esi, eax
0x1800da418  mov     [rsp+0E8h+hr], eax
0x1800da41c  test    eax, eax
0x1800da41e  js      $CleanUp_187
0x1800da424  mov     this, [rsp+0E8h+cb]; cb
0x1800da42c  call    cs:__imp_CoTaskMemAlloc
0x1800da432  mov     r15, rax
0x1800da435  mov     [r13+0], rax
0x1800da439  test    rax, rax
0x1800da43c  jz      short loc_1800DA4B2
0x1800da43e  mov     [rsp+0E8h+var_C0], r12
0x1800da443  mov     [rsp+0E8h+var_90], rax
0x1800da448  dec     r12
0x1800da44b  mov     [rsp+0E8h+var_C0], r12
0x1800da450  mov     r13, [rsp+0E8h+csHeaders._xss._length]
0x1800da455  xor     r14d, r14d
0x1800da458  mov     [rsp+0E8h+var_88], r14
0x1800da45d  cmp     r14, r13
0x1800da460  jnb     short loc_1800DA4AC
0x1800da462  test    r12, r12
0x1800da465  jz      short loc_1800DA4AC
0x1800da467  lea     pwszHeaders, [r14+r14*2]
0x1800da46b  mov     this, [rsp+0E8h+csHeaders._xss._data]
0x1800da470  mov     rax, [this+pwszHeaders*8+8]
0x1800da475  test    rax, rax
0x1800da478  jz      short loc_1800DA4A7
0x1800da47a  mov     rdi, r12
0x1800da47d  cmp     rax, r12
0x1800da480  cmovb   rdi, rax
0x1800da484  lea     rbx, [rdi+rdi]
0x1800da488  mov     ppwszAdditionalHeaders, rbx; Size
0x1800da48b  mov     pwszHeaders, [this+pwszHeaders*8]; Src
0x1800da48f  mov     this, r15; void *
0x1800da492  call    memcpy_0
0x1800da497  sub     r12, rdi
0x1800da49a  mov     [rsp+0E8h+var_C0], r12
0x1800da49f  add     r15, rbx
0x1800da4a2  mov     [rsp+0E8h+var_90], r15
0x1800da4a7  inc     r14
0x1800da4aa  jmp     short loc_1800DA458
0x1800da4ac  xor     eax, eax
0x1800da4ae  mov     [r15], ax
0x1800da4b2  jmp     short $CleanUp_187
0x1800da4b4  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x1800da4b9  mov     ecx, cs:_tls_index
0x1800da4bf  mov     rax, gs:58h
0x1800da4c8  mov     edx, 8
0x1800da4cd  mov     rax, [rax+this*8]
0x1800da4d1  mov     this, [rax+pwszHeaders]
0x1800da4d5  mov     this, [this+8]; e
0x1800da4d9  call    ?setErrorInfoAndGetHR@_dispatchImpl@@SAJPEAVException@@@Z; _dispatchImpl::setErrorInfoAndGetHR(Exception *)
0x1800da4de  mov     esi, eax
0x1800da4e0  mov     [rsp+0E8h+hr], eax
0x1800da4e4  lea     this, [rsp+0E8h+csHeaders]; this
0x1800da4e9  call    ??1xstrings@@QEAA@XZ; xstrings::~xstrings(void)
0x1800da4ee  lea     this, [rsp+0E8h+haCurrentHeaders]; this
0x1800da4f3  call    ??1HTTPHeaders@@UEAA@XZ; HTTPHeaders::~HTTPHeaders(void)
0x1800da4f8  mov     eax, esi
0x1800da4fa  lea     r11, [rsp+0E8h+var_28]
0x1800da502  mov     rbx, [r11+38h]
0x1800da506  mov     rsi, [r11+40h]
0x1800da50a  mov     rsp, r11
0x1800da50d  pop     r15
0x1800da50f  pop     r14
0x1800da511  pop     r13
0x1800da513  pop     r12
0x1800da515  pop     rdi
0x1800da516  retn
0x18017de3a  push    rbp
0x18017de3c  sub     rsp, 20h
0x18017de40  mov     rbp, rdx
0x18017de43  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z
0x18017de48  nop
0x18017de49  add     rsp, 20h
0x18017de4d  pop     rbp
0x18017de4e  retn
```
