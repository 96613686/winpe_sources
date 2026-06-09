# HTTPHeaders::additionalHeaders(ushort const *,ushort * *)

- ea: `0x1007e17f`
- end: `0x1007e2ff`
- name: `?additionalHeaders@HTTPHeaders@@QAEJPBGPAPAG@Z`
- size: `384`
- prototype: `HRESULT __thiscall(HTTPHeaders *this, const wchar_t *pwszHeaders, wchar_t **ppwszAdditionalHeaders)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x10133b49`

## callees

- `0x10040ca6`
- `0x100410fe`
- `0x1006bff0`
- `0x10076076`
- `0x100779f5`
- `0x10077a4b`
- `0x1007dd5a`
- `0x1007ddd9`
- `0x1007de23`
- `0x1007de40`
- `0x1007de6c`
- `0x1007e151`
- `0x1007e17f`
- `0x1007e363`
- `0x1007e473`
- `0x1007e5d6`
- `0x1007ed2b`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1007e284`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1007e284`

## pseudocode

```c
HRESULT __thiscall HTTPHeaders::additionalHeaders(
        HTTPHeaders *this,
        const wchar_t *pwszHeaders,
        wchar_t **ppwszAdditionalHeaders)
{
  HRESULT v3; // esi
  int v4; // edx
  int v5; // ebx
  int j; // esi
  int v7; // edi
  xstring::xinit v8; // ecx
  xstring::xinit v9; // ecx
  xstring::xinit v10; // ecx
  xstring::xinit v11; // ecx
  wchar_t *v12; // eax
  HTTPHeaders haCurrentHeaders; // [esp+10h] [ebp-68h] BYREF
  xstrings csHeaders; // [esp+3Ch] [ebp-3Ch] BYREF
  unsigned int cb; // [esp+50h] [ebp-28h] BYREF
  int i; // [esp+54h] [ebp-24h]
  HRESULT hr; // [esp+58h] [ebp-20h]
  unsigned int cch; // [esp+5Ch] [ebp-1Ch] BYREF
  CPPEH_RECORD ms_exc; // [esp+60h] [ebp-18h]

  cch = (unsigned int)this;
  v3 = 0;
  HTTPHeaders::HTTPHeaders(&haCurrentHeaders);
  xstrings::xstrings(&csHeaders);
  v5 = *(_DWORD *)(v4 + 12);
  if ( v5 )
  {
    ms_exc.registration.TryLevel = 0;
    HTTPHeaders::setAll(&haCurrentHeaders, pwszHeaders, 0, 0);
    csHeaders._cchTotal = 0;
    if ( csHeaders._xss._data )
      xstrings::_free(csHeaders._xss._data);
    csHeaders._xss._data = new_array_ne<xstring>(4 * v5);
    csHeaders._xss._allocated = 4 * v5;
    csHeaders._xss._length = 0;
    for ( j = 0; ; ++j )
    {
      i = j;
      if ( j >= v5 )
        break;
      v7 = *(_DWORD *)(cch + 16) + 20 * j;
      if ( HTTPHeaders::find(&haCurrentHeaders, *(const wchar_t **)v7, *(_DWORD *)(v7 + 4)) == -1 )
      {
        xstrings::append(&csHeaders, *(const wchar_t **)v7, *(_DWORD *)(v7 + 4), v8);
        xstrings::append(&csHeaders, L": ", 2u, v9);
        xstrings::append(&csHeaders, *(const wchar_t **)(v7 + 8), *(_DWORD *)(v7 + 12), v10);
        xstrings::append(&csHeaders, L"\r\n", 2u, v11);
      }
    }
    v3 = SizeTAdd(csHeaders._cchTotal, 1u, &cch);
    hr = v3;
    if ( v3 >= 0 )
    {
      v3 = ULongLongToUInt(2LL * cch, &cb);
      hr = v3;
      if ( v3 >= 0 )
      {
        v12 = (wchar_t *)CoTaskMemAlloc(cb);
        *ppwszAdditionalHeaders = v12;
        if ( v12 )
          xstrings::copyTo(&csHeaders, v12, cch);
      }
    }
    ms_exc.registration.TryLevel = -2;
  }
  xstrings::~xstrings(&csHeaders);
  HTTPHeaders::~HTTPHeaders(&haCurrentHeaders);
  return v3;
}

```

## disassembly

```asm
0x1007e17f  push    58h
0x1007e181  push    offset stru_10174668
0x1007e186  call    __SEH_prolog4
0x1007e18b  mov     edx, this
0x1007e18d  mov     [ebp+cch], edx
0x1007e190  xor     edi, edi
0x1007e192  mov     esi, edi
0x1007e194  lea     this, [ebp+haCurrentHeaders]; this
0x1007e197  call    ??0HTTPHeaders@@QAE@XZ; HTTPHeaders::HTTPHeaders(void)
0x1007e19c  lea     this, [ebp+csHeaders]; this
0x1007e19f  call    ??0xstrings@@QAE@XZ; xstrings::xstrings(void)
0x1007e1a4  mov     ebx, [edx+0Ch]
0x1007e1a7  test    ebx, ebx
0x1007e1a9  jz      CleanUp_53
0x1007e1af  mov     [ebp+ms_exc.registration.TryLevel], edi
0x1007e1b2  push    edi; fAppendValues
0x1007e1b3  push    edi; fResponse
0x1007e1b4  push    [ebp+pwszHeaders]; pwszNewHeaders
0x1007e1b7  lea     this, [ebp+haCurrentHeaders]; this
0x1007e1ba  call    ?setAll@HTTPHeaders@@QAEJPBG_N1@Z; HTTPHeaders::setAll(ushort const *,bool,bool)
0x1007e1bf  mov     esi, ebx
0x1007e1c1  shl     esi, 2
0x1007e1c4  mov     [ebp+csHeaders._cchTotal], edi
0x1007e1c7  mov     this, [ebp+csHeaders._xss._data]; pData
0x1007e1ca  test    this, this
0x1007e1cc  jz      short loc_1007E1D3
0x1007e1ce  call    ?_free@xstrings@@SGXPAVxstring@@@Z; xstrings::_free(xstring *)
0x1007e1d3  mov     this, esi; cch
0x1007e1d5  call    ??$new_array_ne@Vxstring@@@@YGPAVxstring@@J@Z; new_array_ne<xstring>(long)
0x1007e1da  mov     [ebp+csHeaders._xss._data], eax
0x1007e1dd  mov     [ebp+csHeaders._xss._allocated], esi
0x1007e1e0  mov     [ebp+csHeaders._xss._length], edi
0x1007e1e3  mov     esi, edi
0x1007e1e5  push    2
0x1007e1e7  pop     edi
0x1007e1e8  mov     [ebp+i], esi
0x1007e1eb  cmp     esi, ebx
0x1007e1ed  jge     short loc_1007E251
0x1007e1ef  imul    edi, esi, 14h
0x1007e1f2  mov     eax, [ebp+cch]
0x1007e1f5  add     edi, [eax+10h]
0x1007e1f8  push    dword ptr [edi+4]; cchH
0x1007e1fb  push    dword ptr [edi]; pwszH
0x1007e1fd  lea     this, [ebp+haCurrentHeaders]; this
0x1007e200  call    ?find@HTTPHeaders@@IAEHPBGH@Z; HTTPHeaders::find(ushort const *,int)
0x1007e205  cmp     eax, 0FFFFFFFFh
0x1007e208  jnz     short loc_1007E24B
0x1007e20a  push    this; xstring::xinit
0x1007e20b  push    dword ptr [edi+4]; cch
0x1007e20e  push    dword ptr [edi]; pwch
0x1007e210  lea     this, [ebp+csHeaders]; this
0x1007e213  call    ?append@xstrings@@QAEXPBGIW4xinit@xstring@@@Z; xstrings::append(ushort const *,uint,xstring::xinit)
0x1007e218  push    this; xstring::xinit
0x1007e219  push    2; cch
0x1007e21b  push    offset pwch; ": "
0x1007e220  lea     this, [ebp+csHeaders]; this
0x1007e223  call    ?append@xstrings@@QAEXPBGIW4xinit@xstring@@@Z; xstrings::append(ushort const *,uint,xstring::xinit)
0x1007e228  push    this; xstring::xinit
0x1007e229  push    dword ptr [edi+0Ch]; cch
0x1007e22c  push    dword ptr [edi+8]; pwch
0x1007e22f  lea     this, [ebp+csHeaders]; this
0x1007e232  call    ?append@xstrings@@QAEXPBGIW4xinit@xstring@@@Z; xstrings::append(ushort const *,uint,xstring::xinit)
0x1007e237  push    this; xstring::xinit
0x1007e238  push    2
0x1007e23a  pop     edi
0x1007e23b  push    edi; cch
0x1007e23c  push    offset asc_1001D924; "\r\n"
0x1007e241  lea     this, [ebp+csHeaders]; this
0x1007e244  call    ?append@xstrings@@QAEXPBGIW4xinit@xstring@@@Z; xstrings::append(ushort const *,uint,xstring::xinit)
0x1007e249  jmp     short loc_1007E24E
0x1007e24b  push    2
0x1007e24d  pop     edi
0x1007e24e  inc     esi
0x1007e24f  jmp     short loc_1007E1E8
0x1007e251  lea     eax, [ebp+cch]
0x1007e254  push    eax; pulResult
0x1007e255  xor     edx, edx
0x1007e257  inc     edx; ulAddend
0x1007e258  mov     this, [ebp+csHeaders._cchTotal]; ulAugend
0x1007e25b  call    ?SizeTAdd@@YGJIIPAI@Z; SizeTAdd(uint,uint,uint *)
0x1007e260  mov     esi, eax
0x1007e262  mov     [ebp+hr], esi
0x1007e265  test    esi, esi
0x1007e267  js      short loc_1007E2D4
0x1007e269  mov     eax, [ebp+cch]
0x1007e26c  mul     edi
0x1007e26e  push    edx
0x1007e26f  push    eax; ullOperand
0x1007e270  lea     this, [ebp+cb]; puResult
0x1007e273  call    ?ULongLongToUInt@@YGJ_KPAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1007e278  mov     esi, eax
0x1007e27a  mov     [ebp+hr], esi
0x1007e27d  test    esi, esi
0x1007e27f  js      short loc_1007E2D4
0x1007e281  push    [ebp+cb]; cb
0x1007e284  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1007e28a  mov     this, [ebp+ppwszAdditionalHeaders]
0x1007e28d  mov     [this], eax
0x1007e28f  test    eax, eax
0x1007e291  jz      short loc_1007E2D4
0x1007e293  push    [ebp+cch]; ul
0x1007e296  push    eax; pwch
0x1007e297  lea     this, [ebp+csHeaders]; this
0x1007e29a  call    ?copyTo@xstrings@@QBEXPAGI@Z; xstrings::copyTo(ushort *,uint)
0x1007e29f  jmp     short loc_1007E2D4
0x1007e2a1  mov     this, [ebp+ms_exc.exc_ptr]; ep
0x1007e2a4  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x1007e2a9  retn
0x1007e2aa  mov     esp, [ebp+ms_exc.old_esp]
0x1007e2ad  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x1007e2b2  mov     this, __tls_index
0x1007e2b8  mov     eax, large fs:2Ch
0x1007e2be  mov     eax, [eax+this*4]
0x1007e2c1  mov     eax, [eax+4]
0x1007e2c7  mov     this, [eax+8]; e
0x1007e2ca  call    ?setErrorInfoAndGetHR@_dispatchImpl@@SGJPAVException@@@Z; _dispatchImpl::setErrorInfoAndGetHR(Exception *)
0x1007e2cf  mov     esi, eax
0x1007e2d1  mov     [ebp+hr], esi
0x1007e2d4  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1007e2db  lea     this, [ebp+csHeaders]; this
0x1007e2de  call    ??1xstrings@@QAE@XZ; xstrings::~xstrings(void)
0x1007e2e3  lea     this, [ebp+haCurrentHeaders]; this
0x1007e2e6  call    ??1HTTPHeaders@@UAE@XZ; HTTPHeaders::~HTTPHeaders(void)
0x1007e2eb  mov     eax, esi
0x1007e2ed  mov     this, [ebp+ms_exc.registration.Next]
0x1007e2f0  mov     large fs:0, this
0x1007e2f7  pop     this
0x1007e2f8  pop     edi
0x1007e2f9  pop     esi
0x1007e2fa  pop     ebx
0x1007e2fb  leave
0x1007e2fc  retn    8
```
