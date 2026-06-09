# InternetHost::QueryCustomPolicy(_GUID const &,uchar * *,ulong *,uchar *,ulong,ulong)

- ea: `0x1006b140`
- end: `0x1006b37a`
- name: `?QueryCustomPolicy@InternetHost@@UAGJABU_GUID@@PAPAEPAKPAEKK@Z`
- size: `570`
- prototype: `HRESULT __stdcall(InternetHost *this, const _GUID *guidKey, unsigned __int8 **ppPolicy, unsigned int *pcbPolicy, unsigned __int8 *pContext, unsigned int cbContext, unsigned int dwReserved)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1003fba3`
- `0x10040c44`
- `0x100508cd`
- `0x10057d31`
- `0x10067bc0`
- `0x1006b140`
- `0x1006b510`
- `0x100e8473`
- `0x100e8804`
- `0x1012fac4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1006b32e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1006b32e`

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
0x1006b140  mov     edi, edi
0x1006b142  push    ebp
0x1006b143  mov     ebp, esp
0x1006b145  sub     esp, 48h
0x1006b148  mov     eax, ___security_cookie
0x1006b14d  xor     eax, ebp
0x1006b14f  mov     [ebp+var_4], eax
0x1006b152  mov     eax, [ebp+pContext]
0x1006b155  mov     ecx, [ebp+guidKey]
0x1006b158  push    ebx
0x1006b159  mov     ebx, [ebp+ppPolicy]
0x1006b15c  mov     dword ptr [ebp+pUnk.Data4+4], eax
0x1006b15f  mov     eax, [ebp+this]
0x1006b162  push    esi
0x1006b163  mov     [ebp+var_2C], eax
0x1006b166  mov     esi, 80004005h
0x1006b16b  add     eax, 8
0x1006b16e  mov     dword ptr [ebp+pUnk.Data4], ecx
0x1006b171  push    edi
0x1006b172  mov     edi, [ebp+pcbPolicy]
0x1006b175  mov     ecx, eax; this
0x1006b177  mov     [ebp+pUnk.Data1], ebx
0x1006b17a  mov     dword ptr [ebp+pUnk.Data2], edi
0x1006b17d  mov     [ebp+pSecMgr._p], 0
0x1006b184  mov     [ebp+pHostSecMgr._p], 0
0x1006b18b  mov     [ebp+var_48], eax
0x1006b18e  call    ?getHostSecurityManager@SecurityInfo@@QBEPAUIInternetHostSecurityManager@@XZ; SecurityInfo::getHostSecurityManager(void)
0x1006b193  mov     edx, eax; pref
0x1006b195  lea     ecx, [ebp+pHostSecMgr]; ppref
0x1006b198  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1006b19d  mov     eax, [ebp+pHostSecMgr._p]
0x1006b1a0  test    eax, eax
0x1006b1a2  jz      short loc_1006B1DB
0x1006b1a4  push    [ebp+dwReserved]
0x1006b1a7  mov     ecx, [eax]
0x1006b1a9  push    [ebp+cbContext]
0x1006b1ac  push    dword ptr [ebp+pUnk.Data4+4]
0x1006b1af  mov     esi, [ecx+14h]
0x1006b1b2  mov     ecx, esi; this
0x1006b1b4  push    edi
0x1006b1b5  push    ebx
0x1006b1b6  push    dword ptr [ebp+pUnk.Data4]
0x1006b1b9  push    eax
0x1006b1ba  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006b1c0  call    esi
0x1006b1c2  mov     esi, eax
0x1006b1c4  lea     ecx, [ebp+pHostSecMgr]; ppref
0x1006b1c7  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1006b1cc  lea     ecx, [ebp+pSecMgr]; ppref
0x1006b1cf  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1006b1d4  mov     eax, esi
0x1006b1d6  jmp     loc_1006B369
0x1006b1db  test    ebx, ebx
0x1006b1dd  jz      loc_1006B354
0x1006b1e3  test    edi, edi
0x1006b1e5  jz      loc_1006B354
0x1006b1eb  mov     eax, [ebp+var_48]
0x1006b1ee  xor     ecx, ecx
0x1006b1f0  mov     [ebx], ecx
0x1006b1f2  mov     [edi], ecx
0x1006b1f4  push    3
0x1006b1f6  mov     eax, [eax]
0x1006b1f8  pop     ebx
0x1006b1f9  sub     eax, ecx
0x1006b1fb  jz      loc_1006B323
0x1006b201  sub     eax, 1
0x1006b204  jnz     loc_1006B32C
0x1006b20a  mov     ecx, dword ptr [ebp+pUnk.Data4+4]
0x1006b20d  lea     ebx, [ebp+rgbContext]
0x1006b210  test    ecx, ecx
0x1006b212  push    20h ; ' '
0x1006b214  pop     eax
0x1006b215  cmovnz  eax, [ebp+cbContext]
0x1006b219  cmovnz  ebx, ecx
0x1006b21c  mov     ecx, [ebp+var_2C]
0x1006b21f  mov     dword ptr [ebp+pUnk.Data4+4], eax
0x1006b222  add     ecx, 10h; this
0x1006b225  lea     eax, [ebp+pSecMgr]
0x1006b228  push    eax; pptr
0x1006b229  call    ?HrGetPointer@?$_gitpointer@UIStorageFile@Storage@Windows@@$1?_GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea@@3U__s_GUID@@B@@QBEJPAPAUIStorageFile@Storage@Windows@@@Z; _gitpointer<Windows::Storage::IStorageFile,&__s_GUID const _GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea>::HrGetPointer(Windows::Storage::IStorageFile * *)
0x1006b22e  mov     esi, eax
0x1006b230  test    esi, esi
0x1006b232  js      short loc_1006B260
0x1006b234  mov     ecx, [ebp+pSecMgr._p]
0x1006b237  push    [ebp+dwReserved]
0x1006b23a  push    dword ptr [ebp+pUnk.Data4+4]
0x1006b23d  mov     eax, [ecx]
0x1006b23f  push    ebx
0x1006b240  push    edi
0x1006b241  push    [ebp+pUnk.Data1]; pUnk
0x1006b244  mov     esi, [eax+20h]
0x1006b247  mov     eax, [ebp+var_2C]
0x1006b24a  push    dword ptr [ebp+pUnk.Data4]
0x1006b24d  mov     eax, [eax+0Ch]
0x1006b250  push    dword ptr [eax+0Ch]
0x1006b253  push    ecx
0x1006b254  mov     ecx, esi; this
0x1006b256  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1006b25c  call    esi
0x1006b25e  mov     esi, eax
0x1006b260  cmp     esi, 800C0011h
0x1006b266  jz      short loc_1006B274
0x1006b268  cmp     esi, 80070490h
0x1006b26e  jnz     Cleanup_0
0x1006b274  mov     ecx, dword ptr [ebp+pUnk.Data4]; rguid1
0x1006b277  mov     edx, offset _GUID_CUSTOM_CONFIRMOBJECTSAFETY; rguid2
0x1006b27c  call    ?IsEqualGUID@@YGHABU_GUID@@0@Z; IsEqualGUID(_GUID const &,_GUID const &)
0x1006b281  test    eax, eax
0x1006b283  jz      loc_1006B329
0x1006b289  cmp     dword ptr [ebp+pUnk.Data4+4], 18h
0x1006b28d  jz      short loc_1006B299
0x1006b28f  mov     esi, 80070057h
0x1006b294  jmp     Cleanup_0
0x1006b299  cmp     dword ptr [ebx+10h], 0
0x1006b29d  jz      Cleanup_0
0x1006b2a3  mov     ecx, [ebp+var_2C]; this
0x1006b2a6  lea     eax, [ebp+fAllow]
0x1006b2a9  push    eax; pfAllow
0x1006b2aa  push    1203h; dwAction
0x1006b2af  call    ?IsAllowableAction@InternetHost@@IAEJKPA_N@Z; InternetHost::IsAllowableAction(ulong,bool *)
0x1006b2b4  mov     esi, eax
0x1006b2b6  test    esi, esi
0x1006b2b8  js      Cleanup_0
0x1006b2be  cmp     [ebp+fAllow], 0
0x1006b2c2  jz      short loc_1006B2C8
0x1006b2c4  xor     ebx, ebx
0x1006b2c6  jmp     short loc_1006B31F
0x1006b2c8  cmp     dword ptr [ebx+14h], 0
0x1006b2cc  jz      short loc_1006B2F1
0x1006b2ce  cmp     dword ptr [ebx+14h], 1
0x1006b2d2  jnz     short loc_1006B31C
0x1006b2d4  push    dword ptr [ebx+10h]; IUnknown *
0x1006b2d7  mov     esi, ebx
0x1006b2d9  sub     esp, 10h
0x1006b2dc  mov     edi, esp
0x1006b2de  push    ecx; clsid
0x1006b2df  mov     ecx, [ebp+var_2C]; this
0x1006b2e2  movsd
0x1006b2e3  push    0; sOperation
0x1006b2e5  movsd
0x1006b2e6  movsd
0x1006b2e7  movsd
0x1006b2e8  call    ?CheckSafety@InternetHost@@IAE_NW4SAFETYOPERATION@@ABU_GUID@@U3@PAUIUnknown@@@Z; InternetHost::CheckSafety(SAFETYOPERATION,_GUID const &,_GUID,IUnknown *)
0x1006b2ed  test    al, al
0x1006b2ef  jz      short loc_1006B319
0x1006b2f1  push    dword ptr [ebx+10h]; IUnknown *
0x1006b2f4  mov     esi, ebx
0x1006b2f6  sub     esp, 10h
0x1006b2f9  mov     edi, esp
0x1006b2fb  push    ecx; clsid
0x1006b2fc  mov     ecx, [ebp+var_2C]; this
0x1006b2ff  movsd
0x1006b300  push    1; sOperation
0x1006b302  movsd
0x1006b303  movsd
0x1006b304  movsd
0x1006b305  call    ?CheckSafety@InternetHost@@IAE_NW4SAFETYOPERATION@@ABU_GUID@@U3@PAUIUnknown@@@Z; InternetHost::CheckSafety(SAFETYOPERATION,_GUID const &,_GUID,IUnknown *)
0x1006b30a  mov     edi, dword ptr [ebp+pUnk.Data2]
0x1006b30d  xor     ecx, ecx
0x1006b30f  push    3
0x1006b311  test    al, al
0x1006b313  pop     ebx
0x1006b314  cmovnz  ebx, ecx
0x1006b317  jmp     short loc_1006B31F
0x1006b319  mov     edi, dword ptr [ebp+pUnk.Data2]
0x1006b31c  push    3
0x1006b31e  pop     ebx
0x1006b31f  xor     esi, esi
0x1006b321  jmp     short loc_1006B32C
0x1006b323  mov     ebx, ecx
0x1006b325  mov     esi, ecx
0x1006b327  jmp     short loc_1006B32C
0x1006b329  push    3
0x1006b32b  pop     ebx
0x1006b32c  push    4; cb
0x1006b32e  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1006b334  mov     ecx, [ebp+pUnk.Data1]
0x1006b337  mov     [ecx], eax
0x1006b339  test    eax, eax
0x1006b33b  jz      short loc_1006B34A
0x1006b33d  mov     [eax], ebx
0x1006b33f  mov     dword ptr [edi], 4
0x1006b345  jmp     Cleanup_0
0x1006b34a  mov     esi, 8007000Eh
0x1006b34f  jmp     Cleanup_0
0x1006b354  lea     ecx, [ebp+pHostSecMgr]; ppref
0x1006b357  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1006b35c  lea     ecx, [ebp+pSecMgr]; ppref
0x1006b35f  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1006b364  mov     eax, 80004003h
0x1006b369  mov     ecx, [ebp+var_4]
0x1006b36c  pop     edi
0x1006b36d  pop     esi
0x1006b36e  xor     ecx, ebp; cookie
0x1006b370  pop     ebx
0x1006b371  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1006b376  leave
0x1006b377  retn    1Ch
```
