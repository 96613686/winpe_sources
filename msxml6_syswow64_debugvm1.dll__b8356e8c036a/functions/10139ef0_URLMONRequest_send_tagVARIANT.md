# URLMONRequest::send(tagVARIANT)

- ea: `0x10139ef0`
- end: `0x1013a0e9`
- name: `?send@URLMONRequest@@UAEJUtagVARIANT@@@Z`
- size: `505`
- prototype: `HRESULT __thiscall(URLMONRequest *this, tagVARIANT varBody)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x10067bc0`
- `0x1006cbbc`
- `0x10135ce8`
- `0x10136c46`
- `0x101375fb`
- `0x10138601`
- `0x10139ef0`
- `0x1013c700`
- `0x1013c871`
- `0x10180006`
- `0x10180652`

## import_xrefs

- `WININET!InternetSetOptionW` at `0x10139f75`
- `WININET!InternetSetOptionW` at `0x10139f75`
- `urlmon!CoInternetGetSession` at `0x10139fa6`
- `urlmon!CoInternetGetSession` at `0x10139fa6`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x10139fbb`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x10139fbb`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x1013a013`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x1013a013`

## pseudocode

```c
HRESULT __thiscall URLMONRequest::send(URLMONRequest *this, tagVARIANT varBody)
{
  HRESULT Session; // edi
  int v5; // eax
  HRESULT v6; // eax
  int fMta; // [esp+Ch] [ebp-Ch]
  IBindCtx *pIBindCtx; // [esp+10h] [ebp-8h] BYREF
  IInternetSession *pIInternetSession; // [esp+14h] [ebp-4h] BYREF

  pIInternetSession = 0;
  pIBindCtx = 0;
  if ( (byte_101857A0[0] & 8) != 0 )
    WPP_SF_qd(0x403u, 0x38u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, this, varBody.vt);
  if ( !IsCreateBindCtxPresent() )
    return -2147467263;
  this->Lock(this);
  if ( !this->_fDisableLegacyFeatures )
    goto LABEL_9;
  if ( !this->_fAborted && !this->_fAbortPending )
  {
    InternetSetOptionW(0, 0x8Eu, 0, 0);
LABEL_9:
    fMta = this->_fMta;
    Session = URLRequest::send(this, varBody);
    if ( Session >= 0 )
    {
      Session = CoInternetGetSession(0, &pIInternetSession, 0);
      if ( Session >= 0 )
      {
        Session = CreateBindCtx(0, &pIBindCtx);
        if ( Session >= 0 )
        {
          v5 = 0x20000;
          if ( !fMta )
            v5 = 256;
          Session = ((int (__thiscall *)(HRESULT (__stdcall *)(IInternetSession *, IBindCtx *, const wchar_t *, IUnknown *, IUnknown **, IInternetProtocol **, unsigned int), IInternetSession *, IBindCtx *, wchar_t *, _DWORD, _DWORD, IInternetProtocol **, int))pIInternetSession->CreateBinding)(
                      pIInternetSession->CreateBinding,
                      pIInternetSession,
                      pIBindCtx,
                      this->_pwszTargetUrl,
                      0,
                      0,
                      &this->_pIInternetProtocol,
                      v5);
          if ( Session >= 0 )
          {
            Session = CreateUri(this->_pwszTargetUrl, 0x2B84u, 0, &this->_pUri);
            if ( Session >= 0 )
            {
              Session = URLMONRequest::_ApplySettingToProtocol(this);
              if ( Session >= 0 )
              {
                URLRequest::setState(this, SENDING, 0);
                if ( this->_fASync && this->_fDisableLegacyFeatures )
                {
                  if ( this->_fMta )
                    v6 = URLMONRequest::_MtaAsyncCallUrlMonStart(this);
                  else
                    v6 = URLMONRequest::_StaAsyncCallUrlMonStart(this);
                }
                else
                {
                  v6 = URLMONRequest::_CallUrlMonStart(this);
                }
                Session = v6;
              }
            }
          }
        }
      }
    }
    goto CleanUp_521;
  }
  Session = -2147467260;
CleanUp_521:
  if ( pIInternetSession )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IInternetSession *))pIInternetSession->Release)(
      pIInternetSession->Release,
      pIInternetSession);
    pIInternetSession = 0;
  }
  if ( pIBindCtx )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IBindCtx *))pIBindCtx->Release)(
      pIBindCtx->Release,
      pIBindCtx);
    pIBindCtx = 0;
  }
  this->Unlock(this);
  if ( (byte_101857A0[16 * (Session >> 31)] & 8) != 0 )
    WPP_SF_q(
      (((unsigned __int16)(Session >> 31) + 2) << 9) | 3,
      0x39u,
      WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids,
      Session);
  return Session;
}

```

## disassembly

```asm
0x10139ef0  mov     edi, edi
0x10139ef2  push    ebp
0x10139ef3  mov     ebp, esp
0x10139ef5  sub     esp, 0Ch
0x10139ef8  push    ebx
0x10139ef9  push    esi
0x10139efa  push    edi
0x10139efb  mov     ebx, this
0x10139efd  mov     [ebp+pIInternetSession], 0
0x10139f04  mov     [ebp+pIBindCtx], 0
0x10139f0b  test    byte_101857A0, 8; __annotation("TMF:",
0x10139f12  jz      short loc_10139F2C
0x10139f14  movzx   eax, word ptr [ebp+varBody.___u0]
0x10139f18  mov     this, 403h; LevelKeyword
0x10139f1d  push    eax; _a2
0x10139f1e  push    ebx; _a1
0x10139f1f  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10139f24  push    38h ; '8'
0x10139f26  pop     edx; id
0x10139f27  call    _WPP_SF_qd@20; WPP_SF_qd(x,x,x,x,x)
0x10139f2c  call    _IsCreateBindCtxPresent@0; IsCreateBindCtxPresent()
0x10139f31  test    al, al
0x10139f33  jnz     short loc_10139F3F
0x10139f35  mov     eax, 80004001h
0x10139f3a  jmp     loc_1013A0E2
0x10139f3f  mov     eax, [ebx]
0x10139f41  mov     esi, [eax+7Ch]
0x10139f44  mov     this, esi; this
0x10139f46  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139f4c  mov     this, ebx
0x10139f4e  call    esi
0x10139f50  xor     esi, esi
0x10139f52  cmp     [ebx+60h], esi
0x10139f55  jz      short loc_10139F7B
0x10139f57  cmp     byte ptr [ebx+0Ah], 0
0x10139f5b  jnz     loc_1013A04F
0x10139f61  cmp     [ebx+168h], esi
0x10139f67  jnz     loc_1013A04F
0x10139f6d  push    esi; dwBufferLength
0x10139f6e  push    esi; lpBuffer
0x10139f6f  push    8Eh; dwOption
0x10139f74  push    esi; varBody
0x10139f75  call    ds:__imp__InternetSetOptionW@16; InternetSetOptionW(x,x,x,x)
0x10139f7b  mov     eax, [ebx+64h]
0x10139f7e  lea     esi, [ebp+varBody]
0x10139f81  sub     esp, 10h
0x10139f84  mov     [ebp+var_C], eax
0x10139f87  mov     edi, esp
0x10139f89  mov     this, ebx; this
0x10139f8b  movsd
0x10139f8c  movsd
0x10139f8d  movsd
0x10139f8e  movsd
0x10139f8f  call    ?send@URLRequest@@UAEJUtagVARIANT@@@Z; URLRequest::send(tagVARIANT)
0x10139f94  mov     edi, eax
0x10139f96  test    edi, edi
0x10139f98  js      CleanUp_521
0x10139f9e  xor     esi, esi
0x10139fa0  lea     eax, [ebp+pIInternetSession]
0x10139fa3  push    esi; dwReserved
0x10139fa4  push    eax; ppIInternetSession
0x10139fa5  push    esi; dwSessionMode
0x10139fa6  call    ds:__imp__CoInternetGetSession@12; CoInternetGetSession(x,x,x)
0x10139fac  mov     edi, eax
0x10139fae  test    edi, edi
0x10139fb0  js      CleanUp_521
0x10139fb6  lea     eax, [ebp+pIBindCtx]
0x10139fb9  push    eax; ppbc
0x10139fba  push    esi; reserved
0x10139fbb  call    ds:__imp__CreateBindCtx@8; CreateBindCtx(x,x)
0x10139fc1  mov     edi, eax
0x10139fc3  test    edi, edi
0x10139fc5  js      CleanUp_521
0x10139fcb  mov     this, [ebp+pIInternetSession]
0x10139fce  mov     edx, 100h
0x10139fd3  cmp     [ebp+var_C], 0
0x10139fd7  mov     eax, [this]
0x10139fd9  mov     esi, [eax+1Ch]
0x10139fdc  mov     eax, 20000h
0x10139fe1  cmovz   eax, edx
0x10139fe4  push    eax
0x10139fe5  lea     eax, [ebx+68h]
0x10139fe8  push    eax
0x10139fe9  push    0
0x10139feb  push    0
0x10139fed  push    dword ptr [ebx+38h]
0x10139ff0  push    [ebp+pIBindCtx]
0x10139ff3  push    this
0x10139ff4  mov     this, esi; this
0x10139ff6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139ffc  call    esi
0x10139ffe  mov     edi, eax
0x1013a000  test    edi, edi
0x1013a002  js      short CleanUp_521
0x1013a004  lea     eax, [ebx+6Ch]
0x1013a007  xor     esi, esi
0x1013a009  push    eax; ppURI
0x1013a00a  push    esi; dwReserved
0x1013a00b  push    2B84h; dwFlags
0x1013a010  push    dword ptr [ebx+38h]; pwzURI
0x1013a013  call    ds:__imp__CreateUri@16; CreateUri(x,x,x,x)
0x1013a019  mov     edi, eax
0x1013a01b  test    edi, edi
0x1013a01d  js      short CleanUp_521
0x1013a01f  mov     this, ebx; this
0x1013a021  call    ?_ApplySettingToProtocol@URLMONRequest@@IAEJXZ; URLMONRequest::_ApplySettingToProtocol(void)
0x1013a026  mov     edi, eax
0x1013a028  test    edi, edi
0x1013a02a  js      short CleanUp_521
0x1013a02c  push    esi; fForceCallback
0x1013a02d  push    2; eState
0x1013a02f  mov     this, ebx; this
0x1013a031  call    ?setState@URLRequest@@IAEXW4State@@H@Z; URLRequest::setState(State,int)
0x1013a036  cmp     byte ptr [ebx+8], 0
0x1013a03a  jz      short loc_1013A05D
0x1013a03c  cmp     [ebx+60h], esi
0x1013a03f  jz      short loc_1013A05D
0x1013a041  mov     this, ebx; this
0x1013a043  cmp     [ebx+64h], esi
0x1013a046  jz      short loc_1013A056
0x1013a048  call    ?_MtaAsyncCallUrlMonStart@URLMONRequest@@IAEJXZ; URLMONRequest::_MtaAsyncCallUrlMonStart(void)
0x1013a04d  jmp     short loc_1013A064
0x1013a04f  mov     edi, 80004004h
0x1013a054  jmp     short CleanUp_521
0x1013a056  call    ?_StaAsyncCallUrlMonStart@URLMONRequest@@IAEJXZ; URLMONRequest::_StaAsyncCallUrlMonStart(void)
0x1013a05b  jmp     short loc_1013A064
0x1013a05d  mov     this, ebx; this
0x1013a05f  call    ?_CallUrlMonStart@URLMONRequest@@IAEJXZ; URLMONRequest::_CallUrlMonStart(void)
0x1013a064  mov     edi, eax
0x1013a066  mov     this, [ebp+pIInternetSession]
0x1013a069  test    this, this
0x1013a06b  jz      short loc_1013A084
0x1013a06d  mov     eax, [this]
0x1013a06f  push    this
0x1013a070  mov     esi, [eax+8]
0x1013a073  mov     this, esi; this
0x1013a075  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013a07b  call    esi
0x1013a07d  mov     [ebp+pIInternetSession], 0
0x1013a084  mov     this, [ebp+pIBindCtx]
0x1013a087  test    this, this
0x1013a089  jz      short loc_1013A0A2
0x1013a08b  mov     eax, [this]
0x1013a08d  push    this
0x1013a08e  mov     esi, [eax+8]
0x1013a091  mov     this, esi; this
0x1013a093  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013a099  call    esi
0x1013a09b  mov     [ebp+pIBindCtx], 0
0x1013a0a2  mov     eax, [ebx]
0x1013a0a4  mov     esi, [eax+80h]
0x1013a0aa  mov     this, esi; this
0x1013a0ac  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013a0b2  mov     this, ebx
0x1013a0b4  call    esi
0x1013a0b6  mov     this, edi; __annotation("TMF:",
0x1013a0b8  sar     this, 1Fh
0x1013a0bb  mov     eax, this
0x1013a0bd  shl     eax, 4
0x1013a0c0  test    byte_101857A0[eax], 8
0x1013a0c7  jz      short loc_1013A0E0
0x1013a0c9  push    edi; _a1
0x1013a0ca  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013a0cf  add     this, 2
0x1013a0d2  shl     this, 9
0x1013a0d5  push    39h ; '9'
0x1013a0d7  or      this, 3; LevelKeyword
0x1013a0da  pop     edx; id
0x1013a0db  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x1013a0e0  mov     eax, edi
0x1013a0e2  pop     edi
0x1013a0e3  pop     esi
0x1013a0e4  pop     ebx
0x1013a0e5  leave
0x1013a0e6  retn    10h
```
