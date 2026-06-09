# URLMONRequest::send(tagVARIANT)

- ea: `0x1013a000`
- end: `0x1013a1f9`
- name: `?send@URLMONRequest@@UAEJUtagVARIANT@@@Z`
- size: `505`
- prototype: `HRESULT __thiscall(URLMONRequest *this, tagVARIANT varBody)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x10067b20`
- `0x1006cb2c`
- `0x10135df8`
- `0x10136d56`
- `0x1013770b`
- `0x10138711`
- `0x1013a000`
- `0x1013c810`
- `0x1013c981`
- `0x10180006`
- `0x10180652`

## import_xrefs

- `WININET!InternetSetOptionW` at `0x1013a085`
- `WININET!InternetSetOptionW` at `0x1013a085`
- `urlmon!CoInternetGetSession` at `0x1013a0b6`
- `urlmon!CoInternetGetSession` at `0x1013a0b6`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1013a0cb`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1013a0cb`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x1013a123`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x1013a123`

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
  if ( (byte_10185760[0] & 8) != 0 )
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
  if ( (byte_10185760[16 * (Session >> 31)] & 8) != 0 )
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
0x1013a000  mov     edi, edi
0x1013a002  push    ebp
0x1013a003  mov     ebp, esp
0x1013a005  sub     esp, 0Ch
0x1013a008  push    ebx
0x1013a009  push    esi
0x1013a00a  push    edi
0x1013a00b  mov     ebx, this
0x1013a00d  mov     [ebp+pIInternetSession], 0
0x1013a014  mov     [ebp+pIBindCtx], 0
0x1013a01b  test    byte_10185760, 8; __annotation("TMF:",
0x1013a022  jz      short loc_1013A03C
0x1013a024  movzx   eax, word ptr [ebp+varBody.___u0]
0x1013a028  mov     this, 403h; LevelKeyword
0x1013a02d  push    eax; _a2
0x1013a02e  push    ebx; _a1
0x1013a02f  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013a034  push    38h ; '8'
0x1013a036  pop     edx; id
0x1013a037  call    _WPP_SF_qd@20; WPP_SF_qd(x,x,x,x,x)
0x1013a03c  call    _IsCreateBindCtxPresent@0; IsCreateBindCtxPresent()
0x1013a041  test    al, al
0x1013a043  jnz     short loc_1013A04F
0x1013a045  mov     eax, 80004001h
0x1013a04a  jmp     loc_1013A1F2
0x1013a04f  mov     eax, [ebx]
0x1013a051  mov     esi, [eax+7Ch]
0x1013a054  mov     this, esi; this
0x1013a056  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013a05c  mov     this, ebx
0x1013a05e  call    esi
0x1013a060  xor     esi, esi
0x1013a062  cmp     [ebx+60h], esi
0x1013a065  jz      short loc_1013A08B
0x1013a067  cmp     byte ptr [ebx+0Ah], 0
0x1013a06b  jnz     loc_1013A15F
0x1013a071  cmp     [ebx+168h], esi
0x1013a077  jnz     loc_1013A15F
0x1013a07d  push    esi; dwBufferLength
0x1013a07e  push    esi; lpBuffer
0x1013a07f  push    8Eh; dwOption
0x1013a084  push    esi; varBody
0x1013a085  call    ds:__imp__InternetSetOptionW@16; InternetSetOptionW(x,x,x,x)
0x1013a08b  mov     eax, [ebx+64h]
0x1013a08e  lea     esi, [ebp+varBody]
0x1013a091  sub     esp, 10h
0x1013a094  mov     [ebp+var_C], eax
0x1013a097  mov     edi, esp
0x1013a099  mov     this, ebx; this
0x1013a09b  movsd
0x1013a09c  movsd
0x1013a09d  movsd
0x1013a09e  movsd
0x1013a09f  call    ?send@URLRequest@@UAEJUtagVARIANT@@@Z; URLRequest::send(tagVARIANT)
0x1013a0a4  mov     edi, eax
0x1013a0a6  test    edi, edi
0x1013a0a8  js      CleanUp_521
0x1013a0ae  xor     esi, esi
0x1013a0b0  lea     eax, [ebp+pIInternetSession]
0x1013a0b3  push    esi; dwReserved
0x1013a0b4  push    eax; ppIInternetSession
0x1013a0b5  push    esi; dwSessionMode
0x1013a0b6  call    ds:__imp__CoInternetGetSession@12; CoInternetGetSession(x,x,x)
0x1013a0bc  mov     edi, eax
0x1013a0be  test    edi, edi
0x1013a0c0  js      CleanUp_521
0x1013a0c6  lea     eax, [ebp+pIBindCtx]
0x1013a0c9  push    eax; ppbc
0x1013a0ca  push    esi; reserved
0x1013a0cb  call    ds:__imp__CreateBindCtx@8; CreateBindCtx(x,x)
0x1013a0d1  mov     edi, eax
0x1013a0d3  test    edi, edi
0x1013a0d5  js      CleanUp_521
0x1013a0db  mov     this, [ebp+pIInternetSession]
0x1013a0de  mov     edx, 100h
0x1013a0e3  cmp     [ebp+var_C], 0
0x1013a0e7  mov     eax, [this]
0x1013a0e9  mov     esi, [eax+1Ch]
0x1013a0ec  mov     eax, 20000h
0x1013a0f1  cmovz   eax, edx
0x1013a0f4  push    eax
0x1013a0f5  lea     eax, [ebx+68h]
0x1013a0f8  push    eax
0x1013a0f9  push    0
0x1013a0fb  push    0
0x1013a0fd  push    dword ptr [ebx+38h]
0x1013a100  push    [ebp+pIBindCtx]
0x1013a103  push    this
0x1013a104  mov     this, esi; this
0x1013a106  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013a10c  call    esi
0x1013a10e  mov     edi, eax
0x1013a110  test    edi, edi
0x1013a112  js      short CleanUp_521
0x1013a114  lea     eax, [ebx+6Ch]
0x1013a117  xor     esi, esi
0x1013a119  push    eax; ppURI
0x1013a11a  push    esi; dwReserved
0x1013a11b  push    2B84h; dwFlags
0x1013a120  push    dword ptr [ebx+38h]; pwzURI
0x1013a123  call    ds:__imp__CreateUri@16; CreateUri(x,x,x,x)
0x1013a129  mov     edi, eax
0x1013a12b  test    edi, edi
0x1013a12d  js      short CleanUp_521
0x1013a12f  mov     this, ebx; this
0x1013a131  call    ?_ApplySettingToProtocol@URLMONRequest@@IAEJXZ; URLMONRequest::_ApplySettingToProtocol(void)
0x1013a136  mov     edi, eax
0x1013a138  test    edi, edi
0x1013a13a  js      short CleanUp_521
0x1013a13c  push    esi; fForceCallback
0x1013a13d  push    2; eState
0x1013a13f  mov     this, ebx; this
0x1013a141  call    ?setState@URLRequest@@IAEXW4State@@H@Z; URLRequest::setState(State,int)
0x1013a146  cmp     byte ptr [ebx+8], 0
0x1013a14a  jz      short loc_1013A16D
0x1013a14c  cmp     [ebx+60h], esi
0x1013a14f  jz      short loc_1013A16D
0x1013a151  mov     this, ebx; this
0x1013a153  cmp     [ebx+64h], esi
0x1013a156  jz      short loc_1013A166
0x1013a158  call    ?_MtaAsyncCallUrlMonStart@URLMONRequest@@IAEJXZ; URLMONRequest::_MtaAsyncCallUrlMonStart(void)
0x1013a15d  jmp     short loc_1013A174
0x1013a15f  mov     edi, 80004004h
0x1013a164  jmp     short CleanUp_521
0x1013a166  call    ?_StaAsyncCallUrlMonStart@URLMONRequest@@IAEJXZ; URLMONRequest::_StaAsyncCallUrlMonStart(void)
0x1013a16b  jmp     short loc_1013A174
0x1013a16d  mov     this, ebx; this
0x1013a16f  call    ?_CallUrlMonStart@URLMONRequest@@IAEJXZ; URLMONRequest::_CallUrlMonStart(void)
0x1013a174  mov     edi, eax
0x1013a176  mov     this, [ebp+pIInternetSession]
0x1013a179  test    this, this
0x1013a17b  jz      short loc_1013A194
0x1013a17d  mov     eax, [this]
0x1013a17f  push    this
0x1013a180  mov     esi, [eax+8]
0x1013a183  mov     this, esi; this
0x1013a185  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013a18b  call    esi
0x1013a18d  mov     [ebp+pIInternetSession], 0
0x1013a194  mov     this, [ebp+pIBindCtx]
0x1013a197  test    this, this
0x1013a199  jz      short loc_1013A1B2
0x1013a19b  mov     eax, [this]
0x1013a19d  push    this
0x1013a19e  mov     esi, [eax+8]
0x1013a1a1  mov     this, esi; this
0x1013a1a3  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013a1a9  call    esi
0x1013a1ab  mov     [ebp+pIBindCtx], 0
0x1013a1b2  mov     eax, [ebx]
0x1013a1b4  mov     esi, [eax+80h]
0x1013a1ba  mov     this, esi; this
0x1013a1bc  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013a1c2  mov     this, ebx
0x1013a1c4  call    esi
0x1013a1c6  mov     this, edi; __annotation("TMF:",
0x1013a1c8  sar     this, 1Fh
0x1013a1cb  mov     eax, this
0x1013a1cd  shl     eax, 4
0x1013a1d0  test    byte_10185760[eax], 8
0x1013a1d7  jz      short loc_1013A1F0
0x1013a1d9  push    edi; _a1
0x1013a1da  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013a1df  add     this, 2
0x1013a1e2  shl     this, 9
0x1013a1e5  push    39h ; '9'
0x1013a1e7  or      this, 3; LevelKeyword
0x1013a1ea  pop     edx; id
0x1013a1eb  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x1013a1f0  mov     eax, edi
0x1013a1f2  pop     edi
0x1013a1f3  pop     esi
0x1013a1f4  pop     ebx
0x1013a1f5  leave
0x1013a1f6  retn    10h
```
