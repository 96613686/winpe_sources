# InternetHost::QueryCustomPolicy(_GUID const &,uchar * *,ulong *,uchar *,ulong,ulong)

- ea: `0x1006b0a0`
- end: `0x1006b2da`
- name: `?QueryCustomPolicy@InternetHost@@UAGJABU_GUID@@PAPAEPAKPAEKK@Z`
- size: `570`
- prototype: `HRESULT __stdcall(InternetHost *this, const _GUID *guidKey, unsigned __int8 **ppPolicy, unsigned int *pcbPolicy, unsigned __int8 *pContext, unsigned int cbContext, unsigned int dwReserved)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1003fb13`
- `0x10040bb4`
- `0x1005083d`
- `0x10057ca1`
- `0x10067b20`
- `0x1006b0a0`
- `0x1006b470`
- `0x100e8593`
- `0x100e8924`
- `0x1012fbd4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1006b28e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1006b28e`

## pseudocode

```c
HRESULT __stdcall InternetHost::QueryCustomPolicy(
        InternetHost *this,
        const _GUID *guidKey,
        unsigned __int8 **ppPolicy,
        unsigned int *pcbPolicy,
        unsigned __int8 *pContext,
        unsigned int cbContext,
        unsigned int dwReserved)
{
  int Pointer; // esi
  unsigned int *v8; // edi
  HostSecurityMgrWrapper *HostSecurityManager; // eax
  int v11; // ebx
  unsigned __int8 *v12; // ebx
  unsigned int v13; // eax
  const _GUID *v14; // ecx
  bool v15; // al
  unsigned __int8 *v16; // eax
  SecurityInfo *v17; // [esp+Ch] [ebp-48h]
  unsigned int pUnk_12; // [esp+1Ch] [ebp-38h]
  _reference<IInternetSecurityManager> pSecMgr; // [esp+20h] [ebp-34h] BYREF
  _reference<IInternetHostSecurityManager> pHostSecMgr; // [esp+24h] [ebp-30h] BYREF
  InternetHost *v21; // [esp+28h] [ebp-2Ch]
  bool fAllow; // [esp+2Fh] [ebp-25h] BYREF
  unsigned __int8 rgbContext[32]; // [esp+30h] [ebp-24h] BYREF

  v21 = this;
  Pointer = -2147467259;
  v8 = pcbPolicy;
  pSecMgr._p = 0;
  pHostSecMgr._p = 0;
  v17 = &this->SecurityInfo;
  HostSecurityManager = SecurityInfo::getHostSecurityManager(&this->SecurityInfo);
  assign(&pHostSecMgr._p, HostSecurityManager);
  if ( pHostSecMgr._p )
  {
    Pointer = ((int (__thiscall *)(HRESULT (__stdcall *)(IInternetHostSecurityManager *, const _GUID *, unsigned __int8 **, unsigned int *, unsigned __int8 *, unsigned int, unsigned int), IInternetHostSecurityManager *, const _GUID *, unsigned __int8 **, unsigned int *, unsigned __int8 *, unsigned int, unsigned int))pHostSecMgr._p->QueryCustomPolicy)(
                pHostSecMgr._p->QueryCustomPolicy,
                pHostSecMgr._p,
                guidKey,
                ppPolicy,
                pcbPolicy,
                pContext,
                cbContext,
                dwReserved);
Cleanup_0:
    release(&pHostSecMgr._p);
    release(&pSecMgr._p);
    return Pointer;
  }
  if ( ppPolicy && pcbPolicy )
  {
    *ppPolicy = 0;
    *pcbPolicy = 0;
    v11 = 3;
    if ( v17->_securitySetting )
    {
      if ( v17->_securitySetting != CheckSecurity )
        goto LABEL_32;
      v12 = rgbContext;
      v13 = 32;
      if ( pContext )
      {
        v13 = cbContext;
        v12 = pContext;
      }
      pUnk_12 = v13;
      Pointer = _gitpointer<Windows::Storage::IStorageFile,&__s_GUID const _GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea>::HrGetPointer(
                  (_gitpointer<IUnknown,&IID_IUnknown> *)&v21->_pISecMgr,
                  &pSecMgr._p);
      if ( Pointer >= 0 )
        Pointer = ((int (__thiscall *)(HRESULT (__stdcall *)(IInternetSecurityManager *, const wchar_t *, const _GUID *, unsigned __int8 **, unsigned int *, unsigned __int8 *, unsigned int, unsigned int), IInternetSecurityManager *, const wchar_t *, const _GUID *, unsigned __int8 **, unsigned int *, unsigned __int8 *, unsigned int, unsigned int))pSecMgr._p->QueryCustomPolicy)(
                    pSecMgr._p->QueryCustomPolicy,
                    pSecMgr._p,
                    v21->_sSecureBaseURL._p->_pwsz,
                    guidKey,
                    ppPolicy,
                    pcbPolicy,
                    v12,
                    pUnk_12,
                    dwReserved);
      if ( Pointer != -2146697199 && Pointer != -2147023728 )
        goto Cleanup_0;
      if ( IsEqualGUID(guidKey, &GUID_CUSTOM_CONFIRMOBJECTSAFETY) )
      {
        if ( pUnk_12 != 24 )
        {
          Pointer = -2147024809;
          goto Cleanup_0;
        }
        if ( !*((_DWORD *)v12 + 4) )
          goto Cleanup_0;
        Pointer = InternetHost::IsAllowableAction(v21, 0x1203u, &fAllow);
        if ( Pointer < 0 )
          goto Cleanup_0;
        if ( fAllow )
        {
          v11 = 0;
LABEL_29:
          Pointer = 0;
          goto LABEL_32;
        }
        if ( *((_DWORD *)v12 + 5) )
        {
          if ( *((_DWORD *)v12 + 5) == 1 )
          {
            if ( InternetHost::CheckSafety(v21, SAFETY_INIT, v14, *(_GUID *)v12, *((IUnknown **)v12 + 4)) )
              goto LABEL_24;
            v8 = pcbPolicy;
          }
          v11 = 3;
          goto LABEL_29;
        }
LABEL_24:
        v15 = InternetHost::CheckSafety(v21, SAFETY_SCRIPT, v14, *(_GUID *)v12, *((IUnknown **)v12 + 4));
        v8 = pcbPolicy;
        v11 = 3;
        if ( v15 )
          v11 = 0;
        goto LABEL_29;
      }
      v11 = 3;
    }
    else
    {
      v11 = 0;
      Pointer = 0;
    }
LABEL_32:
    v16 = (unsigned __int8 *)CoTaskMemAlloc(4u);
    *ppPolicy = v16;
    if ( v16 )
    {
      *(_DWORD *)v16 = v11;
      *v8 = 4;
    }
    else
    {
      Pointer = -2147024882;
    }
    goto Cleanup_0;
  }
  release(&pHostSecMgr._p);
  release(&pSecMgr._p);
  return -2147467261;
}

```

## disassembly

```asm
0x1006b0a0  mov     edi, edi
0x1006b0a2  push    ebp
0x1006b0a3  mov     ebp, esp
0x1006b0a5  sub     esp, 48h
0x1006b0a8  mov     eax, ___security_cookie
0x1006b0ad  xor     eax, ebp
0x1006b0af  mov     [ebp+var_4], eax
0x1006b0b2  mov     eax, [ebp+pContext]
0x1006b0b5  mov     ecx, [ebp+guidKey]
0x1006b0b8  push    ebx
0x1006b0b9  mov     ebx, [ebp+ppPolicy]
0x1006b0bc  mov     dword ptr [ebp+pUnk.Data4+4], eax
0x1006b0bf  mov     eax, [ebp+this]
0x1006b0c2  push    esi
0x1006b0c3  mov     [ebp+var_2C], eax
0x1006b0c6  mov     esi, 80004005h
0x1006b0cb  add     eax, 8
0x1006b0ce  mov     dword ptr [ebp+pUnk.Data4], ecx
0x1006b0d1  push    edi
0x1006b0d2  mov     edi, [ebp+pcbPolicy]
0x1006b0d5  mov     ecx, eax; this
0x1006b0d7  mov     [ebp+pUnk.Data1], ebx
0x1006b0da  mov     dword ptr [ebp+pUnk.Data2], edi
0x1006b0dd  mov     [ebp+pSecMgr._p], 0
0x1006b0e4  mov     [ebp+pHostSecMgr._p], 0
0x1006b0eb  mov     [ebp+var_48], eax
0x1006b0ee  call    ?getHostSecurityManager@SecurityInfo@@QBEPAUIInternetHostSecurityManager@@XZ; SecurityInfo::getHostSecurityManager(void)
0x1006b0f3  mov     edx, eax; pref
0x1006b0f5  lea     ecx, [ebp+pHostSecMgr]; ppref
0x1006b0f8  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1006b0fd  mov     eax, [ebp+pHostSecMgr._p]
0x1006b100  test    eax, eax
0x1006b102  jz      short loc_1006B13B
0x1006b104  push    [ebp+dwReserved]
0x1006b107  mov     ecx, [eax]
0x1006b109  push    [ebp+cbContext]
0x1006b10c  push    dword ptr [ebp+pUnk.Data4+4]
0x1006b10f  mov     esi, [ecx+14h]
0x1006b112  mov     ecx, esi; this
0x1006b114  push    edi
0x1006b115  push    ebx
0x1006b116  push    dword ptr [ebp+pUnk.Data4]
0x1006b119  push    eax
0x1006b11a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006b120  call    esi
0x1006b122  mov     esi, eax
0x1006b124  lea     ecx, [ebp+pHostSecMgr]; ppref
0x1006b127  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1006b12c  lea     ecx, [ebp+pSecMgr]; ppref
0x1006b12f  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1006b134  mov     eax, esi
0x1006b136  jmp     loc_1006B2C9
0x1006b13b  test    ebx, ebx
0x1006b13d  jz      loc_1006B2B4
0x1006b143  test    edi, edi
0x1006b145  jz      loc_1006B2B4
0x1006b14b  mov     eax, [ebp+var_48]
0x1006b14e  xor     ecx, ecx
0x1006b150  mov     [ebx], ecx
0x1006b152  mov     [edi], ecx
0x1006b154  push    3
0x1006b156  mov     eax, [eax]
0x1006b158  pop     ebx
0x1006b159  sub     eax, ecx
0x1006b15b  jz      loc_1006B283
0x1006b161  sub     eax, 1
0x1006b164  jnz     loc_1006B28C
0x1006b16a  mov     ecx, dword ptr [ebp+pUnk.Data4+4]
0x1006b16d  lea     ebx, [ebp+rgbContext]
0x1006b170  test    ecx, ecx
0x1006b172  push    20h ; ' '
0x1006b174  pop     eax
0x1006b175  cmovnz  eax, [ebp+cbContext]
0x1006b179  cmovnz  ebx, ecx
0x1006b17c  mov     ecx, [ebp+var_2C]
0x1006b17f  mov     dword ptr [ebp+pUnk.Data4+4], eax
0x1006b182  add     ecx, 10h; this
0x1006b185  lea     eax, [ebp+pSecMgr]
0x1006b188  push    eax; pptr
0x1006b189  call    ?HrGetPointer@?$_gitpointer@UIStorageFile@Storage@Windows@@$1?_GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea@@3U__s_GUID@@B@@QBEJPAPAUIStorageFile@Storage@Windows@@@Z; _gitpointer<Windows::Storage::IStorageFile,&__s_GUID const _GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea>::HrGetPointer(Windows::Storage::IStorageFile * *)
0x1006b18e  mov     esi, eax
0x1006b190  test    esi, esi
0x1006b192  js      short loc_1006B1C0
0x1006b194  mov     ecx, [ebp+pSecMgr._p]
0x1006b197  push    [ebp+dwReserved]
0x1006b19a  push    dword ptr [ebp+pUnk.Data4+4]
0x1006b19d  mov     eax, [ecx]
0x1006b19f  push    ebx
0x1006b1a0  push    edi
0x1006b1a1  push    [ebp+pUnk.Data1]; pUnk
0x1006b1a4  mov     esi, [eax+20h]
0x1006b1a7  mov     eax, [ebp+var_2C]
0x1006b1aa  push    dword ptr [ebp+pUnk.Data4]
0x1006b1ad  mov     eax, [eax+0Ch]
0x1006b1b0  push    dword ptr [eax+0Ch]
0x1006b1b3  push    ecx
0x1006b1b4  mov     ecx, esi; this
0x1006b1b6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006b1bc  call    esi
0x1006b1be  mov     esi, eax
0x1006b1c0  cmp     esi, 800C0011h
0x1006b1c6  jz      short loc_1006B1D4
0x1006b1c8  cmp     esi, 80070490h
0x1006b1ce  jnz     Cleanup_0
0x1006b1d4  mov     ecx, dword ptr [ebp+pUnk.Data4]; rguid1
0x1006b1d7  mov     edx, offset _GUID_CUSTOM_CONFIRMOBJECTSAFETY; rguid2
0x1006b1dc  call    ?IsEqualGUID@@YGHABU_GUID@@0@Z; IsEqualGUID(_GUID const &,_GUID const &)
0x1006b1e1  test    eax, eax
0x1006b1e3  jz      loc_1006B289
0x1006b1e9  cmp     dword ptr [ebp+pUnk.Data4+4], 18h
0x1006b1ed  jz      short loc_1006B1F9
0x1006b1ef  mov     esi, 80070057h
0x1006b1f4  jmp     Cleanup_0
0x1006b1f9  cmp     dword ptr [ebx+10h], 0
0x1006b1fd  jz      Cleanup_0
0x1006b203  mov     ecx, [ebp+var_2C]; this
0x1006b206  lea     eax, [ebp+fAllow]
0x1006b209  push    eax; pfAllow
0x1006b20a  push    1203h; dwAction
0x1006b20f  call    ?IsAllowableAction@InternetHost@@IAEJKPA_N@Z; InternetHost::IsAllowableAction(ulong,bool *)
0x1006b214  mov     esi, eax
0x1006b216  test    esi, esi
0x1006b218  js      Cleanup_0
0x1006b21e  cmp     [ebp+fAllow], 0
0x1006b222  jz      short loc_1006B228
0x1006b224  xor     ebx, ebx
0x1006b226  jmp     short loc_1006B27F
0x1006b228  cmp     dword ptr [ebx+14h], 0
0x1006b22c  jz      short loc_1006B251
0x1006b22e  cmp     dword ptr [ebx+14h], 1
0x1006b232  jnz     short loc_1006B27C
0x1006b234  push    dword ptr [ebx+10h]; IUnknown *
0x1006b237  mov     esi, ebx
0x1006b239  sub     esp, 10h
0x1006b23c  mov     edi, esp
0x1006b23e  push    ecx; clsid
0x1006b23f  mov     ecx, [ebp+var_2C]; this
0x1006b242  movsd
0x1006b243  push    0; sOperation
0x1006b245  movsd
0x1006b246  movsd
0x1006b247  movsd
0x1006b248  call    ?CheckSafety@InternetHost@@IAE_NW4SAFETYOPERATION@@ABU_GUID@@U3@PAUIUnknown@@@Z; InternetHost::CheckSafety(SAFETYOPERATION,_GUID const &,_GUID,IUnknown *)
0x1006b24d  test    al, al
0x1006b24f  jz      short loc_1006B279
0x1006b251  push    dword ptr [ebx+10h]; IUnknown *
0x1006b254  mov     esi, ebx
0x1006b256  sub     esp, 10h
0x1006b259  mov     edi, esp
0x1006b25b  push    ecx; clsid
0x1006b25c  mov     ecx, [ebp+var_2C]; this
0x1006b25f  movsd
0x1006b260  push    1; sOperation
0x1006b262  movsd
0x1006b263  movsd
0x1006b264  movsd
0x1006b265  call    ?CheckSafety@InternetHost@@IAE_NW4SAFETYOPERATION@@ABU_GUID@@U3@PAUIUnknown@@@Z; InternetHost::CheckSafety(SAFETYOPERATION,_GUID const &,_GUID,IUnknown *)
0x1006b26a  mov     edi, dword ptr [ebp+pUnk.Data2]
0x1006b26d  xor     ecx, ecx
0x1006b26f  push    3
0x1006b271  test    al, al
0x1006b273  pop     ebx
0x1006b274  cmovnz  ebx, ecx
0x1006b277  jmp     short loc_1006B27F
0x1006b279  mov     edi, dword ptr [ebp+pUnk.Data2]
0x1006b27c  push    3
0x1006b27e  pop     ebx
0x1006b27f  xor     esi, esi
0x1006b281  jmp     short loc_1006B28C
0x1006b283  mov     ebx, ecx
0x1006b285  mov     esi, ecx
0x1006b287  jmp     short loc_1006B28C
0x1006b289  push    3
0x1006b28b  pop     ebx
0x1006b28c  push    4; cb
0x1006b28e  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1006b294  mov     ecx, [ebp+pUnk.Data1]
0x1006b297  mov     [ecx], eax
0x1006b299  test    eax, eax
0x1006b29b  jz      short loc_1006B2AA
0x1006b29d  mov     [eax], ebx
0x1006b29f  mov     dword ptr [edi], 4
0x1006b2a5  jmp     Cleanup_0
0x1006b2aa  mov     esi, 8007000Eh
0x1006b2af  jmp     Cleanup_0
0x1006b2b4  lea     ecx, [ebp+pHostSecMgr]; ppref
0x1006b2b7  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1006b2bc  lea     ecx, [ebp+pSecMgr]; ppref
0x1006b2bf  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1006b2c4  mov     eax, 80004003h
0x1006b2c9  mov     ecx, [ebp+var_4]
0x1006b2cc  pop     edi
0x1006b2cd  pop     esi
0x1006b2ce  xor     ecx, ebp; cookie
0x1006b2d0  pop     ebx
0x1006b2d1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1006b2d6  leave
0x1006b2d7  retn    1Ch
```
