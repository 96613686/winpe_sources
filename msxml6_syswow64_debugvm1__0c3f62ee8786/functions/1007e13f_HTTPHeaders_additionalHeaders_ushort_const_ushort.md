# HTTPHeaders::additionalHeaders(ushort const *,ushort * *)

- ea: `0x1007e13f`
- end: `0x1007e2bf`
- name: `?additionalHeaders@HTTPHeaders@@QAEJPBGPAPAG@Z`
- size: `384`
- prototype: `HRESULT __thiscall(HTTPHeaders *this, const wchar_t *pwszHeaders, wchar_t **ppwszAdditionalHeaders)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x10133a39`

## callees

- `0x10040d36`
- `0x1004118e`
- `0x1006c080`
- `0x10076046`
- `0x100779c5`
- `0x10077a1b`
- `0x1007dd1a`
- `0x1007dd99`
- `0x1007dde3`
- `0x1007de00`
- `0x1007de2c`
- `0x1007e111`
- `0x1007e13f`
- `0x1007e323`
- `0x1007e433`
- `0x1007e596`
- `0x1007eceb`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1007e244`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1007e244`

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
0x1007e13f  push    58h
0x1007e141  push    offset stru_10174578
0x1007e146  call    __SEH_prolog4
0x1007e14b  mov     edx, this
0x1007e14d  mov     [ebp+cch], edx
0x1007e150  xor     edi, edi
0x1007e152  mov     esi, edi
0x1007e154  lea     this, [ebp+haCurrentHeaders]; this
0x1007e157  call    ??0HTTPHeaders@@QAE@XZ; HTTPHeaders::HTTPHeaders(void)
0x1007e15c  lea     this, [ebp+csHeaders]; this
0x1007e15f  call    ??0xstrings@@QAE@XZ; xstrings::xstrings(void)
0x1007e164  mov     ebx, [edx+0Ch]
0x1007e167  test    ebx, ebx
0x1007e169  jz      CleanUp_53
0x1007e16f  mov     [ebp+ms_exc.registration.TryLevel], edi
0x1007e172  push    edi; fAppendValues
0x1007e173  push    edi; fResponse
0x1007e174  push    [ebp+pwszHeaders]; pwszNewHeaders
0x1007e177  lea     this, [ebp+haCurrentHeaders]; this
0x1007e17a  call    ?setAll@HTTPHeaders@@QAEJPBG_N1@Z; HTTPHeaders::setAll(ushort const *,bool,bool)
0x1007e17f  mov     esi, ebx
0x1007e181  shl     esi, 2
0x1007e184  mov     [ebp+csHeaders._cchTotal], edi
0x1007e187  mov     this, [ebp+csHeaders._xss._data]; pData
0x1007e18a  test    this, this
0x1007e18c  jz      short loc_1007E193
0x1007e18e  call    ?_free@xstrings@@SGXPAVxstring@@@Z; xstrings::_free(xstring *)
0x1007e193  mov     this, esi; cch
0x1007e195  call    ??$new_array_ne@Vxstring@@@@YGPAVxstring@@J@Z; new_array_ne<xstring>(long)
0x1007e19a  mov     [ebp+csHeaders._xss._data], eax
0x1007e19d  mov     [ebp+csHeaders._xss._allocated], esi
0x1007e1a0  mov     [ebp+csHeaders._xss._length], edi
0x1007e1a3  mov     esi, edi
0x1007e1a5  push    2
0x1007e1a7  pop     edi
0x1007e1a8  mov     [ebp+i], esi
0x1007e1ab  cmp     esi, ebx
0x1007e1ad  jge     short loc_1007E211
0x1007e1af  imul    edi, esi, 14h
0x1007e1b2  mov     eax, [ebp+cch]
0x1007e1b5  add     edi, [eax+10h]
0x1007e1b8  push    dword ptr [edi+4]; cchH
0x1007e1bb  push    dword ptr [edi]; pwszH
0x1007e1bd  lea     this, [ebp+haCurrentHeaders]; this
0x1007e1c0  call    ?find@HTTPHeaders@@IAEHPBGH@Z; HTTPHeaders::find(ushort const *,int)
0x1007e1c5  cmp     eax, 0FFFFFFFFh
0x1007e1c8  jnz     short loc_1007E20B
0x1007e1ca  push    this; xstring::xinit
0x1007e1cb  push    dword ptr [edi+4]; cch
0x1007e1ce  push    dword ptr [edi]; pwch
0x1007e1d0  lea     this, [ebp+csHeaders]; this
0x1007e1d3  call    ?append@xstrings@@QAEXPBGIW4xinit@xstring@@@Z; xstrings::append(ushort const *,uint,xstring::xinit)
0x1007e1d8  push    this; xstring::xinit
0x1007e1d9  push    2; cch
0x1007e1db  push    offset pwch; ": "
0x1007e1e0  lea     this, [ebp+csHeaders]; this
0x1007e1e3  call    ?append@xstrings@@QAEXPBGIW4xinit@xstring@@@Z; xstrings::append(ushort const *,uint,xstring::xinit)
0x1007e1e8  push    this; xstring::xinit
0x1007e1e9  push    dword ptr [edi+0Ch]; cch
0x1007e1ec  push    dword ptr [edi+8]; pwch
0x1007e1ef  lea     this, [ebp+csHeaders]; this
0x1007e1f2  call    ?append@xstrings@@QAEXPBGIW4xinit@xstring@@@Z; xstrings::append(ushort const *,uint,xstring::xinit)
0x1007e1f7  push    this; xstring::xinit
0x1007e1f8  push    2
0x1007e1fa  pop     edi
0x1007e1fb  push    edi; cch
0x1007e1fc  push    offset asc_1001D924; "\r\n"
0x1007e201  lea     this, [ebp+csHeaders]; this
0x1007e204  call    ?append@xstrings@@QAEXPBGIW4xinit@xstring@@@Z; xstrings::append(ushort const *,uint,xstring::xinit)
0x1007e209  jmp     short loc_1007E20E
0x1007e20b  push    2
0x1007e20d  pop     edi
0x1007e20e  inc     esi
0x1007e20f  jmp     short loc_1007E1A8
0x1007e211  lea     eax, [ebp+cch]
0x1007e214  push    eax; pulResult
0x1007e215  xor     edx, edx
0x1007e217  inc     edx; ulAddend
0x1007e218  mov     this, [ebp+csHeaders._cchTotal]; ulAugend
0x1007e21b  call    ?SizeTAdd@@YGJIIPAI@Z; SizeTAdd(uint,uint,uint *)
0x1007e220  mov     esi, eax
0x1007e222  mov     [ebp+hr], esi
0x1007e225  test    esi, esi
0x1007e227  js      short loc_1007E294
0x1007e229  mov     eax, [ebp+cch]
0x1007e22c  mul     edi
0x1007e22e  push    edx
0x1007e22f  push    eax; ullOperand
0x1007e230  lea     this, [ebp+cb]; puResult
0x1007e233  call    ?ULongLongToUInt@@YGJ_KPAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1007e238  mov     esi, eax
0x1007e23a  mov     [ebp+hr], esi
0x1007e23d  test    esi, esi
0x1007e23f  js      short loc_1007E294
0x1007e241  push    [ebp+cb]; cb
0x1007e244  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1007e24a  mov     this, [ebp+ppwszAdditionalHeaders]
0x1007e24d  mov     [this], eax
0x1007e24f  test    eax, eax
0x1007e251  jz      short loc_1007E294
0x1007e253  push    [ebp+cch]; ul
0x1007e256  push    eax; pwch
0x1007e257  lea     this, [ebp+csHeaders]; this
0x1007e25a  call    ?copyTo@xstrings@@QBEXPAGI@Z; xstrings::copyTo(ushort *,uint)
0x1007e25f  jmp     short loc_1007E294
0x1007e261  mov     this, [ebp+ms_exc.exc_ptr]; ep
0x1007e264  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x1007e269  retn
0x1007e26a  mov     esp, [ebp+ms_exc.old_esp]
0x1007e26d  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x1007e272  mov     this, __tls_index
0x1007e278  mov     eax, large fs:2Ch
0x1007e27e  mov     eax, [eax+this*4]
0x1007e281  mov     eax, [eax+4]
0x1007e287  mov     this, [eax+8]; e
0x1007e28a  call    ?setErrorInfoAndGetHR@_dispatchImpl@@SGJPAVException@@@Z; _dispatchImpl::setErrorInfoAndGetHR(Exception *)
0x1007e28f  mov     esi, eax
0x1007e291  mov     [ebp+hr], esi
0x1007e294  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1007e29b  lea     this, [ebp+csHeaders]; this
0x1007e29e  call    ??1xstrings@@QAE@XZ; xstrings::~xstrings(void)
0x1007e2a3  lea     this, [ebp+haCurrentHeaders]; this
0x1007e2a6  call    ??1HTTPHeaders@@UAE@XZ; HTTPHeaders::~HTTPHeaders(void)
0x1007e2ab  mov     eax, esi
0x1007e2ad  mov     this, [ebp+ms_exc.registration.Next]
0x1007e2b0  mov     large fs:0, this
0x1007e2b7  pop     this
0x1007e2b8  pop     edi
0x1007e2b9  pop     esi
0x1007e2ba  pop     ebx
0x1007e2bb  leave
0x1007e2bc  retn    8
```
