# URLMONRequest::get_responseStreamVARIANT(tagVARIANT *)

- ea: `0x10139220`
- end: `0x101393af`
- name: `?get_responseStreamVARIANT@URLMONRequest@@UAEJPAUtagVARIANT@@@Z`
- size: `399`
- prototype: `HRESULT __thiscall(URLMONRequest *this, tagVARIANT *pvarBody)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x10067bc0`
- `0x10139220`
- `0x10180006`
- `0x10180854`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x101392d1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x101392d1`
- `OLEAUT32!__imp__VariantInit@4` at `0x1013927a`
- `OLEAUT32!__imp__VariantInit@4` at `0x1013927a`

## pseudocode

```c
HRESULT __thiscall URLMONRequest::get_responseStreamVARIANT(URLMONRequest *this, tagVARIANT *pvarBody)
{
  tagVARIANT *v3; // esi
  HRESULT v4; // edi
  HRESULT (__stdcall *CopyTo)(IStream *, IStream *, _ULARGE_INTEGER, _ULARGE_INTEGER *, _ULARGE_INTEGER *); // ecx
  IStream *pStm; // [esp+18h] [ebp-4h] BYREF

  pStm = 0;
  if ( (byte_101857A0[0] & 8) != 0 )
    WPP_SF_qq(0x403u, 0x84u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, this, pvarBody);
  this->Lock(this);
  v3 = pvarBody;
  if ( !pvarBody )
  {
    v4 = -2147024809;
    goto CleanUp_511;
  }
  VariantInit(pvarBody);
  if ( this->_eState < SENDING || (v4 = 0, this->_fUserAbort) )
  {
    v4 = -1072954817;
    goto CleanUp_511;
  }
  if ( this->_eState < RESPONSE )
  {
    v4 = -2147483638;
    goto CleanUp_511;
  }
  if ( this->_fStreamBeforeComplete || this->_pstrmCustom )
  {
    v4 = -2147019873;
    goto CleanUp_511;
  }
  if ( this->_pstrmResponse )
  {
    v4 = CreateStreamOnHGlobal(0, 1, &pStm);
    if ( v4 < 0 )
      goto CleanUp_511;
    CopyTo = this->_pstrmResponse->CopyTo;
    v4 = ((int (__thiscall *)(HRESULT (__stdcall *)(IStream *, IStream *, _ULARGE_INTEGER, _ULARGE_INTEGER *, _ULARGE_INTEGER *), IStream *, IStream *, int, int, _DWORD, _DWORD))CopyTo)(
           CopyTo,
           this->_pstrmResponse,
           pStm,
           -1,
           -1,
           0,
           0);
    if ( v4 < 0 )
      goto CleanUp_511;
    v3 = pvarBody;
    pvarBody->vt = 13;
    pvarBody->decVal.Lo32 = (unsigned int)pStm;
    pStm = 0;
  }
  if ( (byte_101857A0[0] & 8) != 0 )
    WPP_SF_q(0x403u, 0x85u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v3->lVal);
CleanUp_511:
  this->Unlock(this);
  if ( pStm )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IStream *))pStm->Release)(pStm->Release, pStm);
    pStm = 0;
  }
  if ( (byte_101857A0[16 * (v4 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v4 >> 31) + 2) << 9) | 3, 0x86u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x10139220  mov     edi, edi
0x10139222  push    ebp
0x10139223  mov     ebp, esp
0x10139225  and     esp, 0FFFFFFF8h
0x10139228  push    this
0x10139229  push    ebx
0x1013922a  push    esi
0x1013922b  push    edi
0x1013922c  mov     ebx, this
0x1013922e  mov     [esp+10h+pStm], 0
0x10139236  test    byte_101857A0, 8; __annotation("TMF:",
0x1013923d  jz      short loc_10139257
0x1013923f  push    [ebp+pvarBody]; _a2
0x10139242  mov     edx, 84h; id
0x10139247  mov     this, 403h; LevelKeyword
0x1013924c  push    ebx; _a1
0x1013924d  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10139252  call    _WPP_SF_qq@20; WPP_SF_qq(x,x,x,x,x)
0x10139257  mov     eax, [ebx]
0x10139259  mov     esi, [eax+7Ch]
0x1013925c  mov     this, esi; this
0x1013925e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139264  mov     this, ebx
0x10139266  call    esi
0x10139268  mov     esi, [ebp+pvarBody]
0x1013926b  test    esi, esi
0x1013926d  jnz     short loc_10139279
0x1013926f  mov     edi, 80070057h
0x10139274  jmp     CleanUp_511
0x10139279  push    esi; pvarg
0x1013927a  call    ds:__imp__VariantInit@4; VariantInit(x)
0x10139280  cmp     dword ptr [ebx+50h], 2
0x10139284  jl      loc_1013933F
0x1013928a  xor     this, this
0x1013928c  mov     edi, this
0x1013928e  cmp     [ebx+0Ch], this
0x10139291  jnz     loc_1013933F
0x10139297  cmp     dword ptr [ebx+50h], 5
0x1013929b  jge     short loc_101392A7
0x1013929d  mov     edi, 8000000Ah
0x101392a2  jmp     CleanUp_511
0x101392a7  cmp     [ebx+0E3h], cl
0x101392ad  jz      short loc_101392B9
0x101392af  mov     edi, 8007139Fh
0x101392b4  jmp     CleanUp_511
0x101392b9  cmp     [ebx+0D4h], this
0x101392bf  jnz     short loc_101392AF
0x101392c1  cmp     [ebx+0CCh], this
0x101392c7  jz      short loc_1013931D
0x101392c9  lea     eax, [esp+10h+pStm]
0x101392cd  push    eax; ppstm
0x101392ce  push    1; fDeleteOnRelease
0x101392d0  push    this; hGlobal
0x101392d1  call    ds:__imp__CreateStreamOnHGlobal@12; CreateStreamOnHGlobal(x,x,x)
0x101392d7  mov     edi, eax
0x101392d9  test    edi, edi
0x101392db  js      short CleanUp_511
0x101392dd  mov     this, [ebx+0CCh]
0x101392e3  push    0
0x101392e5  push    0
0x101392e7  push    0FFFFFFFFh
0x101392e9  mov     eax, [this]
0x101392eb  push    0FFFFFFFFh
0x101392ed  push    [esp+20h+pStm]
0x101392f1  mov     esi, [eax+1Ch]
0x101392f4  push    this
0x101392f5  mov     this, esi; this
0x101392f7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101392fd  call    esi
0x101392ff  mov     edi, eax
0x10139301  test    edi, edi
0x10139303  js      short CleanUp_511
0x10139305  mov     esi, [ebp+pvarBody]
0x10139308  push    0Dh
0x1013930a  pop     eax
0x1013930b  mov     [esi], ax
0x1013930e  mov     eax, [esp+10h+pStm]
0x10139312  mov     [esi+8], eax
0x10139315  mov     [esp+10h+pStm], 0
0x1013931d  test    byte_101857A0, 8; __annotation("TMF:",
0x10139324  jz      short CleanUp_511
0x10139326  push    dword ptr [esi+8]; _a1
0x10139329  mov     edx, 85h; id
0x1013932e  mov     this, 403h; LevelKeyword
0x10139333  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10139338  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x1013933d  jmp     short CleanUp_511
0x1013933f  mov     edi, 0C00C023Fh
0x10139344  mov     eax, [ebx]
0x10139346  mov     esi, [eax+80h]
0x1013934c  mov     this, esi; this
0x1013934e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139354  mov     this, ebx
0x10139356  call    esi
0x10139358  mov     this, [esp+10h+pStm]
0x1013935c  test    this, this
0x1013935e  jz      short loc_10139378
0x10139360  mov     eax, [this]
0x10139362  push    this
0x10139363  mov     esi, [eax+8]
0x10139366  mov     this, esi; this
0x10139368  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013936e  call    esi
0x10139370  mov     [esp+10h+pStm], 0
0x10139378  mov     this, edi; __annotation("TMF:",
0x1013937a  sar     this, 1Fh
0x1013937d  mov     eax, this
0x1013937f  shl     eax, 4
0x10139382  test    byte_101857A0[eax], 8
0x10139389  jz      short loc_101393A4
0x1013938b  add     this, 2
0x1013938e  mov     edx, 86h; id
0x10139393  push    edi; _a1
0x10139394  shl     this, 9
0x10139397  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013939c  or      this, 3; LevelKeyword
0x1013939f  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x101393a4  mov     eax, edi
0x101393a6  pop     edi
0x101393a7  pop     esi
0x101393a8  pop     ebx
0x101393a9  mov     esp, ebp
0x101393ab  pop     ebp
0x101393ac  retn    4
```
