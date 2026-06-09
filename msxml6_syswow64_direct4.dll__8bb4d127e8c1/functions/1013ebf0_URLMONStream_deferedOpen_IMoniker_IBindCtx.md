# URLMONStream::deferedOpen(IMoniker *,IBindCtx *)

- ea: `0x1013ebf0`
- end: `0x1013edb5`
- name: `?deferedOpen@URLMONStream@@UAEJPAUIMoniker@@PAUIBindCtx@@@Z`
- size: `453`
- prototype: `HRESULT __thiscall(URLMONStream *this, IMoniker *pMoniker, IBindCtx *lpbc)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1003fb13`
- `0x10040bb4`
- `0x10067b20`
- `0x1013103b`
- `0x1013104f`
- `0x1013d466`
- `0x1013ebf0`

## import_xrefs

- `urlmon!RegisterBindStatusCallback` at `0x1013ed0c`
- `urlmon!RegisterBindStatusCallback` at `0x1013ed0c`
- `urlmon!RevokeBindStatusCallback` at `0x1013ec80`
- `urlmon!RevokeBindStatusCallback` at `0x1013ec80`
- `urlmon!CreateURLMonikerEx` at `0x1013ed2d`
- `urlmon!CreateURLMonikerEx` at `0x1013ed2d`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1013ec5e`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1013ec5e`

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
0x1013ebf0  mov     edi, edi
0x1013ebf2  push    ebp
0x1013ebf3  mov     ebp, esp
0x1013ebf5  sub     esp, 0Ch
0x1013ebf8  push    ebx
0x1013ebf9  mov     ebx, this
0x1013ebfb  push    esi
0x1013ebfc  xor     esi, esi
0x1013ebfe  mov     [ebp+pmk], esi
0x1013ec01  mov     this, [ebx+0Ch]; pwszUrl
0x1013ec04  mov     [ebp+pStream], esi
0x1013ec07  call    ?IsSafeScheme@URL@@SGJPBG@Z; URL::IsSafeScheme(ushort const *)
0x1013ec0c  test    eax, eax
0x1013ec0e  js      loc_1013ECD5
0x1013ec14  mov     cl, [ebx+20h]; fSecure
0x1013ec17  mov     edx, [ebx+8]; pSecMgr
0x1013ec1a  push    esi; fZoneRelaxed
0x1013ec1b  push    dword ptr [ebx+18h]; pwszSecureUrl
0x1013ec1e  push    esi; pwszBaseUrl
0x1013ec1f  push    dword ptr [ebx+0Ch]; pwszReqUrl
0x1013ec22  call    ?accessAllowed@URL@@SGJ_NPAUIInternetSecurityManager@@PBG220@Z; URL::accessAllowed(bool,IInternetSecurityManager *,ushort const *,ushort const *,ushort const *,bool)
0x1013ec27  test    eax, eax
0x1013ec29  js      loc_1013ECD5
0x1013ec2f  cmp     byte ptr [ebx+74h], 0
0x1013ec33  jz      short loc_1013EC4A
0x1013ec35  push    dword ptr [ebx+0Ch]; _resolvedURL
0x1013ec38  mov     this, ebx; this
0x1013ec3a  call    ?OpenPreloadResource@URLStream@@IAEJPBG@Z; URLStream::OpenPreloadResource(ushort const *)
0x1013ec3f  test    eax, eax
0x1013ec41  js      short loc_1013EC4A
0x1013ec43  xor     eax, eax
0x1013ec45  jmp     loc_1013ECD5
0x1013ec4a  mov     edx, [ebp+lpbc]; pref
0x1013ec4d  mov     [ebp+pbc._p], esi
0x1013ec50  push    edi
0x1013ec51  test    edx, edx
0x1013ec53  jnz     loc_1013ECDB
0x1013ec59  lea     eax, [ebp+pbc]
0x1013ec5c  push    eax; ppbc
0x1013ec5d  push    esi; reserved
0x1013ec5e  call    ds:__imp__CreateBindCtx@8; CreateBindCtx(x,x)
0x1013ec64  mov     edi, eax
0x1013ec66  test    edi, edi
0x1013ec68  jns     short loc_1013ECE3
0x1013ec6a  lea     esi, [ebx+60h]
0x1013ec6d  cmp     dword ptr [esi], 0
0x1013ec70  jz      short loc_1013EC8F
0x1013ec72  mov     edx, ebx
0x1013ec74  lea     eax, [ebx+54h]
0x1013ec77  neg     edx
0x1013ec79  sbb     edx, edx
0x1013ec7b  and     edx, eax
0x1013ec7d  push    edx; pBSCb
0x1013ec7e  push    dword ptr [esi]; pBC
0x1013ec80  call    ds:__imp__RevokeBindStatusCallback@8; RevokeBindStatusCallback(x,x)
0x1013ec86  xor     edx, edx; pref
0x1013ec88  mov     this, esi; ppref
0x1013ec8a  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1013ec8f  mov     eax, [ebx+50h]
0x1013ec92  cmp     eax, 8000000Ah
0x1013ec97  jz      short loc_1013EC9E
0x1013ec99  test    eax, eax
0x1013ec9b  cmovs   edi, eax
0x1013ec9e  mov     this, [ebp+pmk]
0x1013eca1  cmp     edi, 800C0005h
0x1013eca7  mov     eax, 800C0006h
0x1013ecac  cmovz   edi, eax
0x1013ecaf  test    this, this
0x1013ecb1  jz      short loc_1013ECCA
0x1013ecb3  mov     eax, [this]
0x1013ecb5  push    this
0x1013ecb6  mov     esi, [eax+8]
0x1013ecb9  mov     this, esi; this
0x1013ecbb  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013ecc1  call    esi
0x1013ecc3  mov     [ebp+pmk], 0
0x1013ecca  lea     this, [ebp+pbc]; ppref
0x1013eccd  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1013ecd2  mov     eax, edi
0x1013ecd4  pop     edi
0x1013ecd5  pop     esi
0x1013ecd6  pop     ebx
0x1013ecd7  leave
0x1013ecd8  retn    8
0x1013ecdb  lea     this, [ebp+pbc]; ppref
0x1013ecde  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1013ece3  lea     esi, [ebx+64h]
0x1013ece6  xor     edx, edx; pref
0x1013ece8  mov     this, esi; ppref
0x1013ecea  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1013ecef  mov     edx, [ebp+pbc._p]; pref
0x1013ecf2  lea     this, [ebx+60h]; ppref
0x1013ecf5  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1013ecfa  mov     this, ebx
0x1013ecfc  lea     eax, [ebx+54h]
0x1013ecff  neg     this
0x1013ed01  push    0; dwReserved
0x1013ed03  sbb     this, this
0x1013ed05  push    esi; ppBSCBPrev
0x1013ed06  and     this, eax
0x1013ed08  push    this; pBSCb
0x1013ed09  push    [ebp+pbc._p]; pBC
0x1013ed0c  call    ds:__imp__RegisterBindStatusCallback@16; RegisterBindStatusCallback(x,x,x,x)
0x1013ed12  mov     edi, eax
0x1013ed14  test    edi, edi
0x1013ed16  js      loc_1013EC6A
0x1013ed1c  mov     this, [ebp+pMoniker]
0x1013ed1f  test    this, this
0x1013ed21  jnz     short loc_1013ED3F
0x1013ed23  push    1; dwFlags
0x1013ed25  lea     eax, [ebp+pmk]
0x1013ed28  push    eax; ppmk
0x1013ed29  push    dword ptr [ebx+0Ch]; szURL
0x1013ed2c  push    this; pMkCtx
0x1013ed2d  call    ds:__imp__CreateURLMonikerEx@16; CreateURLMonikerEx(x,x,x,x)
0x1013ed33  mov     edi, eax
0x1013ed35  test    edi, edi
0x1013ed37  js      loc_1013EC6A
0x1013ed3d  jmp     short loc_1013ED52
0x1013ed3f  mov     [ebp+pmk], this
0x1013ed42  mov     eax, [this]
0x1013ed44  push    this
0x1013ed45  mov     esi, [eax+4]
0x1013ed48  mov     this, esi; this
0x1013ed4a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013ed50  call    esi
0x1013ed52  mov     this, [ebp+pmk]
0x1013ed55  mov     dword ptr [ebx+50h], 8000000Ah
0x1013ed5c  mov     eax, [this]
0x1013ed5e  mov     esi, [eax+24h]
0x1013ed61  lea     eax, [ebp+pStream]
0x1013ed64  push    eax
0x1013ed65  push    offset _IID_IStream
0x1013ed6a  push    0
0x1013ed6c  push    [ebp+pbc._p]
0x1013ed6f  push    this
0x1013ed70  mov     this, esi; this
0x1013ed72  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013ed78  call    esi
0x1013ed7a  mov     edi, eax
0x1013ed7c  test    edi, edi
0x1013ed7e  js      loc_1013EC6A
0x1013ed84  mov     edx, [ebp+pStream]; pref
0x1013ed87  xor     edi, edi
0x1013ed89  test    edx, edx
0x1013ed8b  jz      loc_1013EC8F
0x1013ed91  lea     this, [ebx+24h]; ppref
0x1013ed94  cmp     [this], edi
0x1013ed96  jnz     short loc_1013EDA0
0x1013ed98  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1013ed9d  mov     edx, [ebp+pStream]
0x1013eda0  mov     eax, [edx]
0x1013eda2  push    edx
0x1013eda3  mov     esi, [eax+8]
0x1013eda6  mov     this, esi; this
0x1013eda8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013edae  call    esi
0x1013edb0  jmp     loc_1013EC8F
```
