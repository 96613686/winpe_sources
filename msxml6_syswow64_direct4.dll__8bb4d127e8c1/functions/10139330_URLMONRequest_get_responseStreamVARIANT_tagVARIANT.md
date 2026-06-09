# URLMONRequest::get_responseStreamVARIANT(tagVARIANT *)

- ea: `0x10139330`
- end: `0x101394bf`
- name: `?get_responseStreamVARIANT@URLMONRequest@@UAEJPAUtagVARIANT@@@Z`
- size: `399`
- prototype: `HRESULT __thiscall(URLMONRequest *this, tagVARIANT *pvarBody)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x10067b20`
- `0x10139330`
- `0x10180006`
- `0x10180854`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x101393e1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x101393e1`
- `OLEAUT32!__imp__VariantInit@4` at `0x1013938a`
- `OLEAUT32!__imp__VariantInit@4` at `0x1013938a`

## pseudocode

```c
HRESULT __thiscall URLMONRequest::get_responseStreamVARIANT(URLMONRequest *this, tagVARIANT *pvarBody)
{
  tagVARIANT *v3; // esi
  HRESULT v4; // edi
  HRESULT (__stdcall *CopyTo)(IStream *, IStream *, _ULARGE_INTEGER, _ULARGE_INTEGER *, _ULARGE_INTEGER *); // ecx
  IStream *pStm; // [esp+18h] [ebp-4h] BYREF

  pStm = 0;
  if ( (byte_10185760[0] & 8) != 0 )
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
  if ( (byte_10185760[0] & 8) != 0 )
    WPP_SF_q(0x403u, 0x85u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v3->lVal);
CleanUp_511:
  this->Unlock(this);
  if ( pStm )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IStream *))pStm->Release)(pStm->Release, pStm);
    pStm = 0;
  }
  if ( (byte_10185760[16 * (v4 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v4 >> 31) + 2) << 9) | 3, 0x86u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x10139330  mov     edi, edi
0x10139332  push    ebp
0x10139333  mov     ebp, esp
0x10139335  and     esp, 0FFFFFFF8h
0x10139338  push    this
0x10139339  push    ebx
0x1013933a  push    esi
0x1013933b  push    edi
0x1013933c  mov     ebx, this
0x1013933e  mov     [esp+10h+pStm], 0
0x10139346  test    byte_10185760, 8; __annotation("TMF:",
0x1013934d  jz      short loc_10139367
0x1013934f  push    [ebp+pvarBody]; _a2
0x10139352  mov     edx, 84h; id
0x10139357  mov     this, 403h; LevelKeyword
0x1013935c  push    ebx; _a1
0x1013935d  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10139362  call    _WPP_SF_qq@20; WPP_SF_qq(x,x,x,x,x)
0x10139367  mov     eax, [ebx]
0x10139369  mov     esi, [eax+7Ch]
0x1013936c  mov     this, esi; this
0x1013936e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139374  mov     this, ebx
0x10139376  call    esi
0x10139378  mov     esi, [ebp+pvarBody]
0x1013937b  test    esi, esi
0x1013937d  jnz     short loc_10139389
0x1013937f  mov     edi, 80070057h
0x10139384  jmp     CleanUp_511
0x10139389  push    esi; pvarg
0x1013938a  call    ds:__imp__VariantInit@4; VariantInit(x)
0x10139390  cmp     dword ptr [ebx+50h], 2
0x10139394  jl      loc_1013944F
0x1013939a  xor     this, this
0x1013939c  mov     edi, this
0x1013939e  cmp     [ebx+0Ch], this
0x101393a1  jnz     loc_1013944F
0x101393a7  cmp     dword ptr [ebx+50h], 5
0x101393ab  jge     short loc_101393B7
0x101393ad  mov     edi, 8000000Ah
0x101393b2  jmp     CleanUp_511
0x101393b7  cmp     [ebx+0E3h], cl
0x101393bd  jz      short loc_101393C9
0x101393bf  mov     edi, 8007139Fh
0x101393c4  jmp     CleanUp_511
0x101393c9  cmp     [ebx+0D4h], this
0x101393cf  jnz     short loc_101393BF
0x101393d1  cmp     [ebx+0CCh], this
0x101393d7  jz      short loc_1013942D
0x101393d9  lea     eax, [esp+10h+pStm]
0x101393dd  push    eax; ppstm
0x101393de  push    1; fDeleteOnRelease
0x101393e0  push    this; hGlobal
0x101393e1  call    ds:__imp__CreateStreamOnHGlobal@12; CreateStreamOnHGlobal(x,x,x)
0x101393e7  mov     edi, eax
0x101393e9  test    edi, edi
0x101393eb  js      short CleanUp_511
0x101393ed  mov     this, [ebx+0CCh]
0x101393f3  push    0
0x101393f5  push    0
0x101393f7  push    0FFFFFFFFh
0x101393f9  mov     eax, [this]
0x101393fb  push    0FFFFFFFFh
0x101393fd  push    [esp+20h+pStm]
0x10139401  mov     esi, [eax+1Ch]
0x10139404  push    this
0x10139405  mov     this, esi; this
0x10139407  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013940d  call    esi
0x1013940f  mov     edi, eax
0x10139411  test    edi, edi
0x10139413  js      short CleanUp_511
0x10139415  mov     esi, [ebp+pvarBody]
0x10139418  push    0Dh
0x1013941a  pop     eax
0x1013941b  mov     [esi], ax
0x1013941e  mov     eax, [esp+10h+pStm]
0x10139422  mov     [esi+8], eax
0x10139425  mov     [esp+10h+pStm], 0
0x1013942d  test    byte_10185760, 8; __annotation("TMF:",
0x10139434  jz      short CleanUp_511
0x10139436  push    dword ptr [esi+8]; _a1
0x10139439  mov     edx, 85h; id
0x1013943e  mov     this, 403h; LevelKeyword
0x10139443  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10139448  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x1013944d  jmp     short CleanUp_511
0x1013944f  mov     edi, 0C00C023Fh
0x10139454  mov     eax, [ebx]
0x10139456  mov     esi, [eax+80h]
0x1013945c  mov     this, esi; this
0x1013945e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139464  mov     this, ebx
0x10139466  call    esi
0x10139468  mov     this, [esp+10h+pStm]
0x1013946c  test    this, this
0x1013946e  jz      short loc_10139488
0x10139470  mov     eax, [this]
0x10139472  push    this
0x10139473  mov     esi, [eax+8]
0x10139476  mov     this, esi; this
0x10139478  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013947e  call    esi
0x10139480  mov     [esp+10h+pStm], 0
0x10139488  mov     this, edi; __annotation("TMF:",
0x1013948a  sar     this, 1Fh
0x1013948d  mov     eax, this
0x1013948f  shl     eax, 4
0x10139492  test    byte_10185760[eax], 8
0x10139499  jz      short loc_101394B4
0x1013949b  add     this, 2
0x1013949e  mov     edx, 86h; id
0x101394a3  push    edi; _a1
0x101394a4  shl     this, 9
0x101394a7  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101394ac  or      this, 3; LevelKeyword
0x101394af  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x101394b4  mov     eax, edi
0x101394b6  pop     edi
0x101394b7  pop     esi
0x101394b8  pop     ebx
0x101394b9  mov     esp, ebp
0x101394bb  pop     ebp
0x101394bc  retn    4
```
