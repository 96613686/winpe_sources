# URLMONRequest::send(tagVARIANT)

- ea: `0x180093060`
- end: `0x1800932d7`
- name: `?send@URLMONRequest@@UEAAJUtagVARIANT@@@Z`
- size: `631`
- prototype: `__int64 __fastcall(URLMONRequest *this, tagVARIANT *varBody)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18008c0ec`
- `0x180093060`
- `0x1800932e0`
- `0x180099820`
- `0x180099f24`
- `0x1800cc9ac`
- `0x180156f88`
- `0x18015870c`
- `0x180185008`
- `0x180185988`
- `0x180188010`

## import_xrefs

- `WININET!InternetSetOptionW` at `0x18009310c`
- `WININET!InternetSetOptionW` at `0x18009310c`
- `urlmon!CoInternetGetSession` at `0x180093158`
- `urlmon!CoInternetGetSession` at `0x180093158`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x18009316e`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x18009316e`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x1800931cb`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x1800931cb`

## pseudocode

```c
__int64 __fastcall URLMONRequest::send(URLMONRequest *this, tagVARIANT *varBody)
{
  IRecordInfo *pRecInfo; // xmm1_8
  int v6; // esi
  unsigned int v7; // esi
  HRESULT Session; // edi
  HRESULT v9; // eax
  tagVARIANT v10; // [rsp+40h] [rbp-20h] BYREF
  IInternetSession *pIInternetSession; // [rsp+90h] [rbp+30h] BYREF
  IBindCtx *pIBindCtx; // [rsp+98h] [rbp+38h] BYREF

  pIInternetSession = 0;
  pIBindCtx = 0;
  if ( (xmmword_1801F6C20 & 8) != 0 )
    WPP_SF_qd(0x403u, 0x38u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, this, varBody->vt);
  if ( !IsCreateBindCtxPresent() )
    return 2147500033LL;
  this->Lock(this);
  if ( !this->_fDisableLegacyFeatures )
    goto LABEL_9;
  if ( !this->_fAborted && !this->_fAbortPending )
  {
    InternetSetOptionW(0, 0x8Eu, 0, 0);
LABEL_9:
    pRecInfo = varBody->pRecInfo;
    v6 = -(this->_fMta != 0);
    v10.0 = varBody->0;
    v10.pRecInfo = pRecInfo;
    v7 = (v6 & 0x1FF00) + 256;
    Session = URLRequest::send(this, &v10);
    if ( Session >= 0 )
    {
      Session = CoInternetGetSession(0, &pIInternetSession, 0);
      if ( Session >= 0 )
      {
        Session = CreateBindCtx(0, &pIBindCtx);
        if ( Session >= 0 )
        {
          Session = pIInternetSession->CreateBinding(
                      pIInternetSession,
                      pIBindCtx,
                      this->_pwszTargetUrl,
                      0,
                      0,
                      &this->_pIInternetProtocol,
                      v7);
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
                    v9 = URLMONRequest::_MtaAsyncCallUrlMonStart(this);
                  else
                    v9 = URLMONRequest::_StaAsyncCallUrlMonStart(this);
                }
                else
                {
                  v9 = URLMONRequest::_CallUrlMonStart(this);
                }
                Session = v9;
              }
            }
          }
        }
      }
    }
    goto $CleanUp_108;
  }
  Session = -2147467260;
$CleanUp_108:
  if ( pIInternetSession )
  {
    pIInternetSession->Release(pIInternetSession);
    pIInternetSession = 0;
  }
  if ( pIBindCtx )
  {
    pIBindCtx->Release(pIBindCtx);
    pIBindCtx = 0;
  }
  this->Unlock(this);
  if ( (g_rgFastWppLevelEnabledFlags[2 * (Session >> 31) + 4].rgbFlags[0] & 8) != 0 )
    WPP_SF_d(
      (((unsigned __int16)(Session >> 31) + 2) << 9) | 3,
      0x39u,
      WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids,
      Session);
  return (unsigned int)Session;
}

```

## disassembly

```asm
0x180093060  mov     [rsp-18h+arg_0], rbx
0x180093065  mov     [rsp-18h+arg_8], rsi
0x18009306a  push    rbp
0x18009306b  push    rdi
0x18009306c  push    r15
0x18009306e  mov     rbp, rsp
0x180093071  sub     rsp, 60h
0x180093075  mov     rdi, varBody
0x180093078  mov     [rbp+pIInternetSession], 0
0x180093080  mov     rbx, this
0x180093083  mov     [rbp+pIBindCtx], 0
0x18009308b  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x180093092  jz      short loc_1800930B4
0x180093094  movzx   eax, word ptr [varBody]
0x180093097  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18009309e  mov     edx, 38h ; '8'; id
0x1800930a3  mov     [rsp+60h+_a2], eax; _a2
0x1800930a7  mov     ecx, 403h; LevelKeyword
0x1800930ac  mov     r9, rbx; _a1
0x1800930af  call    WPP_SF_qd
0x1800930b4  call    IsCreateBindCtxPresent
0x1800930b9  test    al, al
0x1800930bb  jnz     short loc_1800930C7
0x1800930bd  mov     eax, 80004001h
0x1800930c2  jmp     loc_1800932C2
0x1800930c7  mov     rax, [rbx]
0x1800930ca  mov     this, rbx
0x1800930cd  mov     rax, [rax+0F8h]
0x1800930d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800930d9  cmp     dword ptr [rbx+0A8h], 0
0x1800930e0  mov     r15d, 2
0x1800930e6  jz      short loc_180093112
0x1800930e8  cmp     byte ptr [rbx+0Eh], 0
0x1800930ec  jnz     loc_180093215
0x1800930f2  cmp     dword ptr [rbx+260h], 0
0x1800930f9  jnz     loc_180093215
0x1800930ff  xor     r9d, r9d; dwBufferLength
0x180093102  xor     r8d, r8d; lpBuffer
0x180093105  mov     edx, 8Eh; dwOption
0x18009310a  xor     ecx, ecx; hInternet
0x18009310c  call    cs:__imp_InternetSetOptionW
0x180093112  mov     eax, [rbx+0B0h]
0x180093118  lea     varBody, [rbp+var_20]
0x18009311c  movups  xmm0, xmmword ptr [rdi]
0x18009311f  neg     eax
0x180093121  mov     this, rbx
0x180093124  movsd   xmm1, qword ptr [rdi+10h]
0x180093129  sbb     esi, esi
0x18009312b  movaps  [rbp+var_20], xmm0
0x18009312f  and     esi, 1FF00h
0x180093135  movsd   [rbp+var_10], xmm1
0x18009313a  add     esi, 100h
0x180093140  call    ?send@URLRequest@@UEAAJUtagVARIANT@@@Z; URLRequest::send(tagVARIANT)
0x180093145  mov     edi, eax
0x180093147  test    eax, eax
0x180093149  js      $CleanUp_108
0x18009314f  xor     r8d, r8d; dwReserved
0x180093152  lea     varBody, [rbp+pIInternetSession]; ppIInternetSession
0x180093156  xor     ecx, ecx; dwSessionMode
0x180093158  call    cs:__imp_CoInternetGetSession
0x18009315e  mov     edi, eax
0x180093160  test    eax, eax
0x180093162  js      $CleanUp_108
0x180093168  lea     varBody, [rbp+pIBindCtx]; ppbc
0x18009316c  xor     ecx, ecx; reserved
0x18009316e  call    cs:__imp_CreateBindCtx
0x180093174  mov     edi, eax
0x180093176  test    eax, eax
0x180093178  js      $CleanUp_108
0x18009317e  mov     this, [rbp+pIInternetSession]
0x180093182  lea     varBody, [rbx+0B8h]
0x180093189  mov     r8, [rbx+60h]
0x18009318d  xor     r9d, r9d
0x180093190  mov     [rsp+60h+var_30], esi
0x180093194  mov     [rsp+60h+var_38], varBody
0x180093199  mov     rax, [this]
0x18009319c  mov     varBody, [rbp+pIBindCtx]
0x1800931a0  mov     qword ptr [rsp+60h+_a2], 0
0x1800931a9  mov     rax, [rax+38h]
0x1800931ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800931b2  mov     edi, eax
0x1800931b4  test    eax, eax
0x1800931b6  js      short $CleanUp_108
0x1800931b8  mov     this, [rbx+60h]; pwzURI
0x1800931bc  lea     r9, [rbx+0C0h]; ppURI
0x1800931c3  xor     r8d, r8d; dwReserved
0x1800931c6  mov     edx, 2B84h; dwFlags
0x1800931cb  call    cs:__imp_CreateUri
0x1800931d1  mov     edi, eax
0x1800931d3  test    eax, eax
0x1800931d5  js      short $CleanUp_108
0x1800931d7  mov     this, rbx; this
0x1800931da  call    ?_ApplySettingToProtocol@URLMONRequest@@IEAAJXZ; URLMONRequest::_ApplySettingToProtocol(void)
0x1800931df  mov     edi, eax
0x1800931e1  test    eax, eax
0x1800931e3  js      short $CleanUp_108
0x1800931e5  xor     r8d, r8d; fForceCallback
0x1800931e8  mov     edx, r15d; eState
0x1800931eb  mov     this, rbx; this
0x1800931ee  call    ?setState@URLRequest@@IEAAXW4State@@H@Z; URLRequest::setState(State,int)
0x1800931f3  cmp     byte ptr [rbx+0Ch], 0
0x1800931f7  jz      short loc_180093223
0x1800931f9  cmp     dword ptr [rbx+0A8h], 0
0x180093200  jz      short loc_180093223
0x180093202  cmp     dword ptr [rbx+0B0h], 0
0x180093209  mov     this, rbx; this
0x18009320c  jz      short loc_18009321C
0x18009320e  call    ?_MtaAsyncCallUrlMonStart@URLMONRequest@@IEAAJXZ; URLMONRequest::_MtaAsyncCallUrlMonStart(void)
0x180093213  jmp     short loc_18009322B
0x180093215  mov     edi, 80004004h
0x18009321a  jmp     short $CleanUp_108
0x18009321c  call    ?_StaAsyncCallUrlMonStart@URLMONRequest@@IEAAJXZ; URLMONRequest::_StaAsyncCallUrlMonStart(void)
0x180093221  jmp     short loc_18009322B
0x180093223  mov     this, rbx; this
0x180093226  call    ?_CallUrlMonStart@URLMONRequest@@IEAAJXZ; URLMONRequest::_CallUrlMonStart(void)
0x18009322b  mov     edi, eax
0x18009322d  mov     this, [rbp+pIInternetSession]
0x180093231  test    this, this
0x180093234  jz      short loc_18009324A
0x180093236  mov     rax, [this]
0x180093239  mov     rax, [rax+10h]
0x18009323d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093242  mov     [rbp+pIInternetSession], 0
0x18009324a  mov     this, [rbp+pIBindCtx]
0x18009324e  test    this, this
0x180093251  jz      short loc_180093267
0x180093253  mov     rax, [this]
0x180093256  mov     rax, [rax+10h]
0x18009325a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009325f  mov     [rbp+pIBindCtx], 0
0x180093267  mov     rax, [rbx]
0x18009326a  mov     this, rbx
0x18009326d  mov     rax, [rax+100h]
0x180093274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093279  mov     r9d, edi; __annotation("TMF:",
0x18009327c  sar     r9d, 1Fh
0x180093280  lea     eax, ds:4[r9*2]
0x180093288  movsxd  this, eax
0x18009328b  lea     rax, g_rgFastWppLevelEnabledFlags
0x180093292  test    byte ptr [rax+this*8], 8
0x180093296  jz      short loc_1800932C0
0x180093298  add     r9w, r15w
0x18009329c  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1800932a3  movzx   ecx, r9w
0x1800932a7  mov     eax, 200h
0x1800932ac  imul    ecx, eax
0x1800932af  mov     edx, 39h ; '9'; id
0x1800932b4  mov     r9d, edi; _a1
0x1800932b7  or      cx, 3; LevelKeyword
0x1800932bb  call    WPP_SF_d
0x1800932c0  mov     eax, edi
0x1800932c2  lea     r11, [rsp+60h+var_s0]
0x1800932c7  mov     rbx, [r11+20h]
0x1800932cb  mov     rsi, [r11+28h]
0x1800932cf  mov     rsp, r11
0x1800932d2  pop     r15
0x1800932d4  pop     rdi
0x1800932d5  pop     rbp
0x1800932d6  retn
```
