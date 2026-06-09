# URLMONRequest::send(tagVARIANT)

- ea: `0x180093030`
- end: `0x1800932c0`
- name: `?send@URLMONRequest@@UEAAJUtagVARIANT@@@Z`
- size: `656`
- prototype: `HRESULT __fastcall(URLMONRequest *this, tagVARIANT varBody)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18008c600`
- `0x180093030`
- `0x1800932d0`
- `0x18009a624`
- `0x18009aca8`
- `0x1800ce2fc`
- `0x18015a638`
- `0x18015be10`
- `0x180189008`
- `0x180189994`
- `0x18018c010`

## import_xrefs

- `WININET!InternetSetOptionW` at `0x1800930dc`
- `WININET!InternetSetOptionW` at `0x1800930dc`
- `urlmon!CoInternetGetSession` at `0x18009312e`
- `urlmon!CoInternetGetSession` at `0x18009312e`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x18009314a`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x18009314a`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x1800931ad`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x1800931ad`

## pseudocode

```c
__int64 __fastcall URLMONRequest::send(URLMONRequest *this, tagVARIANT *varBody)
{
  IRecordInfo *pRecInfo; // xmm1_8
  int v6; // esi
  unsigned int v7; // esi
  int Session; // edi
  HRESULT v9; // eax
  tagVARIANT v10; // [rsp+40h] [rbp-20h] BYREF
  IInternetSession *pIInternetSession; // [rsp+90h] [rbp+30h] BYREF
  IBindCtx *pIBindCtx; // [rsp+98h] [rbp+38h] BYREF

  pIInternetSession = 0;
  pIBindCtx = 0;
  if ( (xmmword_1801FAD20 & 8) != 0 )
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
    goto $CleanUp_106;
  }
  Session = -2147467260;
$CleanUp_106:
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
0x180093030  mov     [rsp-18h+arg_0], rbx
0x180093035  mov     [rsp-18h+arg_8], rsi
0x18009303a  push    rbp
0x18009303b  push    rdi
0x18009303c  push    r15
0x18009303e  mov     rbp, rsp
0x180093041  sub     rsp, 60h
0x180093045  mov     rdi, varBody
0x180093048  mov     [rbp+pIInternetSession], 0
0x180093050  mov     rbx, this
0x180093053  mov     [rbp+pIBindCtx], 0
0x18009305b  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x180093062  jz      short loc_180093084
0x180093064  movzx   eax, word ptr [varBody]
0x180093067  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18009306e  mov     edx, 38h ; '8'; id
0x180093073  mov     [rsp+60h+_a2], eax; _a2
0x180093077  mov     ecx, 403h; LevelKeyword
0x18009307c  mov     r9, rbx; _a1
0x18009307f  call    WPP_SF_qd
0x180093084  call    IsCreateBindCtxPresent
0x180093089  test    al, al
0x18009308b  jnz     short loc_180093097
0x18009308d  mov     eax, 80004001h
0x180093092  jmp     loc_1800932AA
0x180093097  mov     rax, [rbx]
0x18009309a  mov     this, rbx
0x18009309d  mov     rax, [rax+0F8h]
0x1800930a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800930a9  cmp     dword ptr [rbx+0A8h], 0
0x1800930b0  mov     r15d, 2
0x1800930b6  jz      short loc_1800930E8
0x1800930b8  cmp     byte ptr [rbx+0Eh], 0
0x1800930bc  jnz     loc_1800931FD
0x1800930c2  cmp     dword ptr [rbx+260h], 0
0x1800930c9  jnz     loc_1800931FD
0x1800930cf  xor     r9d, r9d; dwBufferLength
0x1800930d2  xor     r8d, r8d; lpBuffer
0x1800930d5  mov     edx, 8Eh; dwOption
0x1800930da  xor     ecx, ecx; hInternet
0x1800930dc  call    cs:__imp_InternetSetOptionW
0x1800930e3  nop     dword ptr [rax+rax+00h]
0x1800930e8  mov     eax, [rbx+0B0h]
0x1800930ee  lea     varBody, [rbp+var_20]
0x1800930f2  movups  xmm0, xmmword ptr [rdi]
0x1800930f5  neg     eax
0x1800930f7  mov     this, rbx
0x1800930fa  movsd   xmm1, qword ptr [rdi+10h]
0x1800930ff  sbb     esi, esi
0x180093101  movaps  [rbp+var_20], xmm0
0x180093105  and     esi, 1FF00h
0x18009310b  movsd   [rbp+var_10], xmm1
0x180093110  add     esi, 100h
0x180093116  call    ?send@URLRequest@@UEAAJUtagVARIANT@@@Z; URLRequest::send(tagVARIANT)
0x18009311b  mov     edi, eax
0x18009311d  test    eax, eax
0x18009311f  js      $CleanUp_106
0x180093125  xor     r8d, r8d; dwReserved
0x180093128  lea     varBody, [rbp+pIInternetSession]; ppIInternetSession
0x18009312c  xor     ecx, ecx; dwSessionMode
0x18009312e  call    cs:__imp_CoInternetGetSession
0x180093135  nop     dword ptr [rax+rax+00h]
0x18009313a  mov     edi, eax
0x18009313c  test    eax, eax
0x18009313e  js      $CleanUp_106
0x180093144  lea     varBody, [rbp+pIBindCtx]; ppbc
0x180093148  xor     ecx, ecx; reserved
0x18009314a  call    cs:__imp_CreateBindCtx
0x180093151  nop     dword ptr [rax+rax+00h]
0x180093156  mov     edi, eax
0x180093158  test    eax, eax
0x18009315a  js      $CleanUp_106
0x180093160  mov     this, [rbp+pIInternetSession]
0x180093164  lea     varBody, [rbx+0B8h]
0x18009316b  mov     r8, [rbx+60h]
0x18009316f  xor     r9d, r9d
0x180093172  mov     [rsp+60h+var_30], esi
0x180093176  mov     [rsp+60h+var_38], varBody
0x18009317b  mov     rax, [this]
0x18009317e  mov     varBody, [rbp+pIBindCtx]
0x180093182  mov     qword ptr [rsp+60h+_a2], 0
0x18009318b  mov     rax, [rax+38h]
0x18009318f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093194  mov     edi, eax
0x180093196  test    eax, eax
0x180093198  js      short $CleanUp_106
0x18009319a  mov     this, [rbx+60h]; pwzURI
0x18009319e  lea     r9, [rbx+0C0h]; ppURI
0x1800931a5  xor     r8d, r8d; dwReserved
0x1800931a8  mov     edx, 2B84h; dwFlags
0x1800931ad  call    cs:__imp_CreateUri
0x1800931b4  nop     dword ptr [rax+rax+00h]
0x1800931b9  mov     edi, eax
0x1800931bb  test    eax, eax
0x1800931bd  js      short $CleanUp_106
0x1800931bf  mov     this, rbx; this
0x1800931c2  call    ?_ApplySettingToProtocol@URLMONRequest@@IEAAJXZ; URLMONRequest::_ApplySettingToProtocol(void)
0x1800931c7  mov     edi, eax
0x1800931c9  test    eax, eax
0x1800931cb  js      short $CleanUp_106
0x1800931cd  xor     r8d, r8d; fForceCallback
0x1800931d0  mov     edx, r15d; eState
0x1800931d3  mov     this, rbx; this
0x1800931d6  call    ?setState@URLRequest@@IEAAXW4State@@H@Z; URLRequest::setState(State,int)
0x1800931db  cmp     byte ptr [rbx+0Ch], 0
0x1800931df  jz      short loc_18009320B
0x1800931e1  cmp     dword ptr [rbx+0A8h], 0
0x1800931e8  jz      short loc_18009320B
0x1800931ea  cmp     dword ptr [rbx+0B0h], 0
0x1800931f1  mov     this, rbx; this
0x1800931f4  jz      short loc_180093204
0x1800931f6  call    ?_MtaAsyncCallUrlMonStart@URLMONRequest@@IEAAJXZ; URLMONRequest::_MtaAsyncCallUrlMonStart(void)
0x1800931fb  jmp     short loc_180093213
0x1800931fd  mov     edi, 80004004h
0x180093202  jmp     short $CleanUp_106
0x180093204  call    ?_StaAsyncCallUrlMonStart@URLMONRequest@@IEAAJXZ; URLMONRequest::_StaAsyncCallUrlMonStart(void)
0x180093209  jmp     short loc_180093213
0x18009320b  mov     this, rbx; this
0x18009320e  call    ?_CallUrlMonStart@URLMONRequest@@IEAAJXZ; URLMONRequest::_CallUrlMonStart(void)
0x180093213  mov     edi, eax
0x180093215  mov     this, [rbp+pIInternetSession]
0x180093219  test    this, this
0x18009321c  jz      short loc_180093232
0x18009321e  mov     rax, [this]
0x180093221  mov     rax, [rax+10h]
0x180093225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009322a  mov     [rbp+pIInternetSession], 0
0x180093232  mov     this, [rbp+pIBindCtx]
0x180093236  test    this, this
0x180093239  jz      short loc_18009324F
0x18009323b  mov     rax, [this]
0x18009323e  mov     rax, [rax+10h]
0x180093242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093247  mov     [rbp+pIBindCtx], 0
0x18009324f  mov     rax, [rbx]
0x180093252  mov     this, rbx
0x180093255  mov     rax, [rax+100h]
0x18009325c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093261  mov     r9d, edi; __annotation("TMF:",
0x180093264  sar     r9d, 1Fh
0x180093268  lea     eax, ds:4[r9*2]
0x180093270  movsxd  this, eax
0x180093273  lea     rax, g_rgFastWppLevelEnabledFlags
0x18009327a  test    byte ptr [rax+this*8], 8
0x18009327e  jz      short loc_1800932A8
0x180093280  add     r9w, r15w
0x180093284  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18009328b  movzx   ecx, r9w
0x18009328f  mov     eax, 200h
0x180093294  imul    ecx, eax
0x180093297  mov     edx, 39h ; '9'; id
0x18009329c  mov     r9d, edi; _a1
0x18009329f  or      cx, 3; LevelKeyword
0x1800932a3  call    WPP_SF_d
0x1800932a8  mov     eax, edi
0x1800932aa  lea     r11, [rsp+60h+var_s0]
0x1800932af  mov     rbx, [r11+20h]
0x1800932b3  mov     rsi, [r11+28h]
0x1800932b7  mov     rsp, r11
0x1800932ba  pop     r15
0x1800932bc  pop     rdi
0x1800932bd  pop     rbp
0x1800932be  retn
```
