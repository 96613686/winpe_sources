# URLMONStream::deferedOpen(IMoniker *,IBindCtx *)

- ea: `0x1013eae0`
- end: `0x1013eca5`
- name: `?deferedOpen@URLMONStream@@UAEJPAUIMoniker@@PAUIBindCtx@@@Z`
- size: `453`
- prototype: `HRESULT __thiscall(URLMONStream *this, IMoniker *pMoniker, IBindCtx *lpbc)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1003fba3`
- `0x10040c44`
- `0x10067bc0`
- `0x10130f2b`
- `0x10130f3f`
- `0x1013d356`
- `0x1013eae0`

## import_xrefs

- `urlmon!RegisterBindStatusCallback` at `0x1013ebfc`
- `urlmon!RegisterBindStatusCallback` at `0x1013ebfc`
- `urlmon!RevokeBindStatusCallback` at `0x1013eb70`
- `urlmon!RevokeBindStatusCallback` at `0x1013eb70`
- `urlmon!CreateURLMonikerEx` at `0x1013ec1d`
- `urlmon!CreateURLMonikerEx` at `0x1013ec1d`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1013eb4e`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1013eb4e`

## pseudocode

```c
HRESULT __thiscall URLMONStream::deferedOpen(URLMONStream *this, IMoniker *pMoniker, IBindCtx *lpbc)
{
  wchar_t *resolvedURL; // ecx
  HRESULT result; // eax
  HRESULT BindCtx; // edi
  HRESULT ulStatus; // eax
  IMoniker *v8; // ecx
  IStream *v9; // edx
  IStream *pStream; // [esp+8h] [ebp-Ch] BYREF
  IMoniker *pmk; // [esp+Ch] [ebp-8h] BYREF
  _reference<IBindCtx> pbc; // [esp+10h] [ebp-4h] BYREF

  pmk = 0;
  resolvedURL = this->_resolvedURL;
  pStream = 0;
  result = URL::IsSafeScheme(resolvedURL);
  if ( result < 0 )
    return result;
  result = URL::accessAllowed(this->_fSecure, this->_pSecMgr._p, this->_resolvedURL, 0, this->_secureBaseURL, 0);
  if ( result < 0 )
    return result;
  if ( this->_fDTD && URLStream::OpenPreloadResource(this, this->_resolvedURL) >= 0 )
    return 0;
  pbc._p = 0;
  if ( lpbc )
  {
    assign(&pbc._p, lpbc);
  }
  else
  {
    BindCtx = CreateBindCtx(0, &pbc._p);
    if ( BindCtx < 0 )
      goto LABEL_8;
  }
  assign(&this->_pbs._p, 0);
  assign(&this->_pbc._p, pbc._p);
  BindCtx = RegisterBindStatusCallback(pbc._p, this != 0 ? &this->IBindStatusCallback : 0, &this->_pbs._p, 0);
  if ( BindCtx >= 0 )
  {
    if ( pMoniker )
    {
      pmk = pMoniker;
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IMoniker *))pMoniker->AddRef)(
        pMoniker->AddRef,
        pMoniker);
    }
    else
    {
      BindCtx = CreateURLMonikerEx(0, this->_resolvedURL, &pmk, 1u);
      if ( BindCtx < 0 )
        goto LABEL_8;
    }
    v8 = pmk;
    this->_ulStatus = -2147483638;
    BindCtx = ((int (__thiscall *)(HRESULT (__stdcall *)(IMoniker *, IBindCtx *, IMoniker *, const _GUID *, void **), IMoniker *, IBindCtx *, _DWORD, GUID *, IStream **))v8->BindToStorage)(
                v8->BindToStorage,
                v8,
                pbc._p,
                0,
                &IID_IStream,
                &pStream);
    if ( BindCtx >= 0 )
    {
      v9 = pStream;
      BindCtx = 0;
      if ( pStream )
      {
        if ( !this->_pStream._p )
        {
          assign(&this->_pStream._p, pStream);
          v9 = pStream;
        }
        ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IStream *))v9->Release)(v9->Release, v9);
      }
      goto LABEL_10;
    }
  }
LABEL_8:
  if ( this->_pbc._p )
  {
    RevokeBindStatusCallback(this->_pbc._p, this != 0 ? &this->IBindStatusCallback : 0);
    assign(&this->_pbc._p, 0);
  }
LABEL_10:
  ulStatus = this->_ulStatus;
  if ( ulStatus != -2147483638 && ulStatus < 0 )
    BindCtx = this->_ulStatus;
  if ( BindCtx == -2146697211 )
    BindCtx = -2146697210;
  if ( pmk )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IMoniker *))pmk->Release)(pmk->Release, pmk);
    pmk = 0;
  }
  release(&pbc._p);
  return BindCtx;
}

```

## disassembly

```asm
0x1013eae0  mov     edi, edi
0x1013eae2  push    ebp
0x1013eae3  mov     ebp, esp
0x1013eae5  sub     esp, 0Ch
0x1013eae8  push    ebx
0x1013eae9  mov     ebx, this
0x1013eaeb  push    esi
0x1013eaec  xor     esi, esi
0x1013eaee  mov     [ebp+pmk], esi
0x1013eaf1  mov     this, [ebx+0Ch]; pwszUrl
0x1013eaf4  mov     [ebp+pStream], esi
0x1013eaf7  call    ?IsSafeScheme@URL@@SGJPBG@Z; URL::IsSafeScheme(ushort const *)
0x1013eafc  test    eax, eax
0x1013eafe  js      loc_1013EBC5
0x1013eb04  mov     cl, [ebx+20h]; fSecure
0x1013eb07  mov     edx, [ebx+8]; pSecMgr
0x1013eb0a  push    esi; fZoneRelaxed
0x1013eb0b  push    dword ptr [ebx+18h]; pwszSecureUrl
0x1013eb0e  push    esi; pwszBaseUrl
0x1013eb0f  push    dword ptr [ebx+0Ch]; pwszReqUrl
0x1013eb12  call    ?accessAllowed@URL@@SGJ_NPAUIInternetSecurityManager@@PBG220@Z; URL::accessAllowed(bool,IInternetSecurityManager *,ushort const *,ushort const *,ushort const *,bool)
0x1013eb17  test    eax, eax
0x1013eb19  js      loc_1013EBC5
0x1013eb1f  cmp     byte ptr [ebx+74h], 0
0x1013eb23  jz      short loc_1013EB3A
0x1013eb25  push    dword ptr [ebx+0Ch]; _resolvedURL
0x1013eb28  mov     this, ebx; this
0x1013eb2a  call    ?OpenPreloadResource@URLStream@@IAEJPBG@Z; URLStream::OpenPreloadResource(ushort const *)
0x1013eb2f  test    eax, eax
0x1013eb31  js      short loc_1013EB3A
0x1013eb33  xor     eax, eax
0x1013eb35  jmp     loc_1013EBC5
0x1013eb3a  mov     edx, [ebp+lpbc]; pref
0x1013eb3d  mov     [ebp+pbc._p], esi
0x1013eb40  push    edi
0x1013eb41  test    edx, edx
0x1013eb43  jnz     loc_1013EBCB
0x1013eb49  lea     eax, [ebp+pbc]
0x1013eb4c  push    eax; ppbc
0x1013eb4d  push    esi; reserved
0x1013eb4e  call    ds:__imp__CreateBindCtx@8; CreateBindCtx(x,x)
0x1013eb54  mov     edi, eax
0x1013eb56  test    edi, edi
0x1013eb58  jns     short loc_1013EBD3
0x1013eb5a  lea     esi, [ebx+60h]
0x1013eb5d  cmp     dword ptr [esi], 0
0x1013eb60  jz      short loc_1013EB7F
0x1013eb62  mov     edx, ebx
0x1013eb64  lea     eax, [ebx+54h]
0x1013eb67  neg     edx
0x1013eb69  sbb     edx, edx
0x1013eb6b  and     edx, eax
0x1013eb6d  push    edx; pBSCb
0x1013eb6e  push    dword ptr [esi]; pBC
0x1013eb70  call    ds:__imp__RevokeBindStatusCallback@8; RevokeBindStatusCallback(x,x)
0x1013eb76  xor     edx, edx; pref
0x1013eb78  mov     this, esi; ppref
0x1013eb7a  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1013eb7f  mov     eax, [ebx+50h]
0x1013eb82  cmp     eax, 8000000Ah
0x1013eb87  jz      short loc_1013EB8E
0x1013eb89  test    eax, eax
0x1013eb8b  cmovs   edi, eax
0x1013eb8e  mov     this, [ebp+pmk]
0x1013eb91  cmp     edi, 800C0005h
0x1013eb97  mov     eax, 800C0006h
0x1013eb9c  cmovz   edi, eax
0x1013eb9f  test    this, this
0x1013eba1  jz      short loc_1013EBBA
0x1013eba3  mov     eax, [this]
0x1013eba5  push    this
0x1013eba6  mov     esi, [eax+8]
0x1013eba9  mov     this, esi; this
0x1013ebab  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013ebb1  call    esi
0x1013ebb3  mov     [ebp+pmk], 0
0x1013ebba  lea     this, [ebp+pbc]; ppref
0x1013ebbd  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1013ebc2  mov     eax, edi
0x1013ebc4  pop     edi
0x1013ebc5  pop     esi
0x1013ebc6  pop     ebx
0x1013ebc7  leave
0x1013ebc8  retn    8
0x1013ebcb  lea     this, [ebp+pbc]; ppref
0x1013ebce  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1013ebd3  lea     esi, [ebx+64h]
0x1013ebd6  xor     edx, edx; pref
0x1013ebd8  mov     this, esi; ppref
0x1013ebda  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1013ebdf  mov     edx, [ebp+pbc._p]; pref
0x1013ebe2  lea     this, [ebx+60h]; ppref
0x1013ebe5  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1013ebea  mov     this, ebx
0x1013ebec  lea     eax, [ebx+54h]
0x1013ebef  neg     this
0x1013ebf1  push    0; dwReserved
0x1013ebf3  sbb     this, this
0x1013ebf5  push    esi; ppBSCBPrev
0x1013ebf6  and     this, eax
0x1013ebf8  push    this; pBSCb
0x1013ebf9  push    [ebp+pbc._p]; pBC
0x1013ebfc  call    ds:__imp__RegisterBindStatusCallback@16; RegisterBindStatusCallback(x,x,x,x)
0x1013ec02  mov     edi, eax
0x1013ec04  test    edi, edi
0x1013ec06  js      loc_1013EB5A
0x1013ec0c  mov     this, [ebp+pMoniker]
0x1013ec0f  test    this, this
0x1013ec11  jnz     short loc_1013EC2F
0x1013ec13  push    1; dwFlags
0x1013ec15  lea     eax, [ebp+pmk]
0x1013ec18  push    eax; ppmk
0x1013ec19  push    dword ptr [ebx+0Ch]; szURL
0x1013ec1c  push    this; pMkCtx
0x1013ec1d  call    ds:__imp__CreateURLMonikerEx@16; CreateURLMonikerEx(x,x,x,x)
0x1013ec23  mov     edi, eax
0x1013ec25  test    edi, edi
0x1013ec27  js      loc_1013EB5A
0x1013ec2d  jmp     short loc_1013EC42
0x1013ec2f  mov     [ebp+pmk], this
0x1013ec32  mov     eax, [this]
0x1013ec34  push    this
0x1013ec35  mov     esi, [eax+4]
0x1013ec38  mov     this, esi; this
0x1013ec3a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013ec40  call    esi
0x1013ec42  mov     this, [ebp+pmk]
0x1013ec45  mov     dword ptr [ebx+50h], 8000000Ah
0x1013ec4c  mov     eax, [this]
0x1013ec4e  mov     esi, [eax+24h]
0x1013ec51  lea     eax, [ebp+pStream]
0x1013ec54  push    eax
0x1013ec55  push    offset _IID_IStream
0x1013ec5a  push    0
0x1013ec5c  push    [ebp+pbc._p]
0x1013ec5f  push    this
0x1013ec60  mov     this, esi; this
0x1013ec62  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013ec68  call    esi
0x1013ec6a  mov     edi, eax
0x1013ec6c  test    edi, edi
0x1013ec6e  js      loc_1013EB5A
0x1013ec74  mov     edx, [ebp+pStream]; pref
0x1013ec77  xor     edi, edi
0x1013ec79  test    edx, edx
0x1013ec7b  jz      loc_1013EB7F
0x1013ec81  lea     this, [ebx+24h]; ppref
0x1013ec84  cmp     [this], edi
0x1013ec86  jnz     short loc_1013EC90
0x1013ec88  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1013ec8d  mov     edx, [ebp+pStream]
0x1013ec90  mov     eax, [edx]
0x1013ec92  push    edx
0x1013ec93  mov     esi, [eax+8]
0x1013ec96  mov     this, esi; this
0x1013ec98  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013ec9e  call    esi
0x1013eca0  jmp     loc_1013EB7F
```
