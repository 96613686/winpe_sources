# InternetHost::CheckSafety(SAFETYOPERATION,_GUID const &,_GUID,IUnknown *)

- ea: `0x100e8473`
- end: `0x100e8614`
- name: `?CheckSafety@InternetHost@@IAE_NW4SAFETYOPERATION@@ABU_GUID@@U3@PAUIUnknown@@@Z`
- size: `417`
- prototype: `bool __thiscall(InternetHost *this, SAFETYOPERATION sOperation, const _GUID *clsid, _GUID pUnk, IUnknown *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1006b140`

## callees

- `0x10067bc0`
- `0x1006b510`
- `0x1007615e`
- `0x100e8473`
- `0x100e8804`

## import_xrefs

- `urlmon!CompatFlagsFromClsid` at `0x100e84f1`
- `urlmon!CompatFlagsFromClsid` at `0x100e84f1`

## pseudocode

```c
bool __thiscall InternetHost::CheckSafety(
        InternetHost *this,
        SAFETYOPERATION sOperation,
        const _GUID *clsid,
        _GUID pUnk,
        IUnknown *pUnka)
{
  bool v5; // bl
  int v6; // edi
  IObjectSafety *v7; // ecx
  ICatInformation **v9; // [esp+0h] [ebp-58h]
  GUID catid; // [esp+Ch] [ebp-4Ch]
  unsigned int dwMiscStatus; // [esp+20h] [ebp-38h] BYREF
  InternetHost *v12; // [esp+24h] [ebp-34h]
  unsigned int dwCompat; // [esp+28h] [ebp-30h] BYREF
  IObjectSafety *pOSafe; // [esp+2Ch] [ebp-2Ch] BYREF
  bool fSafe; // [esp+33h] [ebp-25h] BYREF
  _GUID clsida; // [esp+34h] [ebp-24h] BYREF
  _GUID rgcatid[1]; // [esp+44h] [ebp-14h] BYREF

  v12 = this;
  clsida = pUnk;
  v5 = 0;
  fSafe = 0;
  dwCompat = 0;
  dwMiscStatus = 0;
  pOSafe = 0;
  catid = GUID_NULL;
  v6 = 0;
  if ( sOperation )
  {
    if ( sOperation == SAFETY_SCRIPT )
    {
      catid = CATID_SafeForScripting;
      v6 = 1;
    }
  }
  else
  {
    catid = CATID_SafeForInitializing;
    v6 = 2;
  }
  if ( CompatFlagsFromClsid(&clsida, &dwCompat, &dwMiscStatus) >= 0 && (dwCompat & 0x400) == 0 )
  {
    if ( (dwCompat & 2) != 0 )
    {
Confirm:
      InternetHost::IsAllowableAction(v12, 0x1204u, &fSafe);
LABEL_15:
      v5 = fSafe;
      goto Cleanup_16;
    }
    if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IUnknown *, GUID *, IObjectSafety **))pUnka->QueryInterface)(
           pUnka->QueryInterface,
           pUnka,
           &IID_IObjectSafety,
           &pOSafe) >= 0
      && (v7 = pOSafe) != 0 )
    {
      if ( sOperation == SAFETY_SCRIPT )
      {
        if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IObjectSafety *, const _GUID *, unsigned int, unsigned int), IObjectSafety *, GUID *, int, int))pOSafe->SetInterfaceSafetyOptions)(
               pOSafe->SetInterfaceSafetyOptions,
               pOSafe,
               &IID_IDispatchEx,
               v6,
               v6) >= 0 )
        {
LABEL_22:
          InternetHost::IsAllowableAction(v12, 0x1405u, &fSafe);
          goto LABEL_15;
        }
        v7 = pOSafe;
      }
      if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IObjectSafety *, const _GUID *, unsigned int, unsigned int), IObjectSafety *, GUID *, int, int))v7->SetInterfaceSafetyOptions)(
             v7->SetInterfaceSafetyOptions,
             v7,
             &IID_IDispatch,
             v6,
             v6) < 0 )
        goto Confirm;
    }
    else
    {
      if ( CreateCatalogInformation(v9) < 0 )
        goto Cleanup_16;
      rgcatid[0] = catid;
      if ( ((int (__thiscall *)(HRESULT (__stdcall *)(ICatInformation *, const _GUID *, unsigned int, const _GUID *, unsigned int, const _GUID *), ICatInformation *, _GUID *, int, _GUID *, _DWORD, _DWORD))g_pCatInfo->IsClassOfCategories)(
             g_pCatInfo->IsClassOfCategories,
             g_pCatInfo,
             &clsida,
             1,
             rgcatid,
             0,
             0) )
      {
        goto Confirm;
      }
    }
    if ( sOperation == SAFETY_SCRIPT )
      goto LABEL_22;
    v5 = 1;
  }
Cleanup_16:
  if ( pOSafe )
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IObjectSafety *))pOSafe->Release)(
      pOSafe->Release,
      pOSafe);
  return v5;
}

```

## disassembly

```asm
0x100e8473  mov     edi, edi
0x100e8475  push    ebp
0x100e8476  mov     ebp, esp
0x100e8478  sub     esp, 4Ch
0x100e847b  mov     eax, ___security_cookie
0x100e8480  xor     eax, ebp
0x100e8482  mov     [ebp+var_4], eax
0x100e8485  push    ebx
0x100e8486  push    esi
0x100e8487  push    edi; ppUnk
0x100e8488  lea     esi, [ebp+arg_8]
0x100e848b  mov     eax, [ebp+pUnk]
0x100e848e  lea     edi, [ebp+clsid]
0x100e8491  mov     [ebp+var_34], this
0x100e8494  movsd
0x100e8495  xor     this, this
0x100e8497  mov     [ebp+var_3C], eax
0x100e849a  mov     bl, cl
0x100e849c  mov     eax, [ebp+sOperation]
0x100e849f  mov     [ebp+fSafe], bl
0x100e84a2  movsd
0x100e84a3  mov     [ebp+dwCompat], this
0x100e84a6  mov     [ebp+dwMiscStatus], this
0x100e84a9  mov     [ebp+pOSafe], this
0x100e84ac  movsd
0x100e84ad  movsd
0x100e84ae  lea     edi, [ebp+catid]
0x100e84b1  mov     esi, offset _GUID_NULL
0x100e84b6  movsd
0x100e84b7  movsd
0x100e84b8  movsd
0x100e84b9  movsd
0x100e84ba  mov     edi, this
0x100e84bc  sub     eax, this
0x100e84be  jz      short loc_100E84D6
0x100e84c0  sub     eax, 1
0x100e84c3  jnz     short loc_100E84E5
0x100e84c5  mov     esi, offset _CATID_SafeForScripting
0x100e84ca  lea     edi, [ebp+catid]
0x100e84cd  movsd
0x100e84ce  movsd
0x100e84cf  movsd
0x100e84d0  movsd
0x100e84d1  xor     edi, edi
0x100e84d3  inc     edi
0x100e84d4  jmp     short loc_100E84E5
0x100e84d6  mov     esi, offset _CATID_SafeForInitializing
0x100e84db  lea     edi, [ebp+catid]
0x100e84de  push    2
0x100e84e0  movsd
0x100e84e1  movsd
0x100e84e2  movsd
0x100e84e3  movsd
0x100e84e4  pop     edi
0x100e84e5  lea     eax, [ebp+dwMiscStatus]
0x100e84e8  push    eax; pdwMiscStatusFlags
0x100e84e9  lea     eax, [ebp+dwCompat]
0x100e84ec  push    eax; pdwCompatFlags
0x100e84ed  lea     eax, [ebp+clsid]
0x100e84f0  push    eax; pclsid
0x100e84f1  call    ds:__imp__CompatFlagsFromClsid@12; CompatFlagsFromClsid(x,x,x)
0x100e84f7  test    eax, eax
0x100e84f9  js      Cleanup_16
0x100e84ff  test    [ebp+dwCompat], 400h
0x100e8506  jnz     Cleanup_16
0x100e850c  test    byte ptr [ebp+dwCompat], 2
0x100e8510  jnz     short Confirm
0x100e8512  mov     this, [ebp+var_3C]
0x100e8515  mov     eax, [this]
0x100e8517  mov     esi, [eax]
0x100e8519  lea     eax, [ebp+pOSafe]
0x100e851c  push    eax
0x100e851d  push    offset _IID_IObjectSafety
0x100e8522  push    this
0x100e8523  mov     this, esi; this
0x100e8525  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e852b  call    esi
0x100e852d  test    eax, eax
0x100e852f  js      loc_100E85C1
0x100e8535  mov     this, [ebp+pOSafe]
0x100e8538  test    this, this
0x100e853a  jz      loc_100E85C1
0x100e8540  cmp     [ebp+sOperation], 1
0x100e8544  jnz     short loc_100E8568
0x100e8546  mov     eax, [this]
0x100e8548  push    edi
0x100e8549  push    edi
0x100e854a  push    offset _IID_IDispatchEx
0x100e854f  mov     esi, [eax+10h]
0x100e8552  push    this
0x100e8553  mov     this, esi; this
0x100e8555  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e855b  call    esi
0x100e855d  test    eax, eax
0x100e855f  jns     loc_100E8602
0x100e8565  mov     this, [ebp+pOSafe]
0x100e8568  mov     eax, [this]
0x100e856a  push    edi
0x100e856b  push    edi
0x100e856c  push    offset _IID_IDispatch
0x100e8571  mov     esi, [eax+10h]
0x100e8574  push    this
0x100e8575  mov     this, esi; this
0x100e8577  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e857d  call    esi
0x100e857f  test    eax, eax
0x100e8581  jns     short EnsureSafeForScripting
0x100e8583  lea     eax, [ebp+fSafe]
0x100e8586  push    eax; pfAllow
0x100e8587  push    1204h; dwAction
0x100e858c  mov     this, [ebp+var_34]; this
0x100e858f  call    ?IsAllowableAction@InternetHost@@IAEJKPA_N@Z; InternetHost::IsAllowableAction(ulong,bool *)
0x100e8594  mov     bl, [ebp+fSafe]
0x100e8597  mov     edx, [ebp+pOSafe]
0x100e859a  test    edx, edx
0x100e859c  jz      short loc_100E85AE
0x100e859e  mov     this, [edx]
0x100e85a0  push    edx
0x100e85a1  mov     esi, [this+8]
0x100e85a4  mov     this, esi; this
0x100e85a6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e85ac  call    esi
0x100e85ae  mov     this, [ebp+var_4]
0x100e85b1  mov     al, bl
0x100e85b3  pop     edi
0x100e85b4  pop     esi
0x100e85b5  xor     this, ebp; cookie
0x100e85b7  pop     ebx
0x100e85b8  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100e85bd  leave
0x100e85be  retn    1Ch
0x100e85c1  call    ?CreateCatalogInformation@@YGJPAPAUICatInformation@@@Z; CreateCatalogInformation(ICatInformation * *)
0x100e85c6  test    eax, eax
0x100e85c8  js      short Cleanup_16
0x100e85ca  mov     this, ?g_pCatInfo@@3PAUICatInformation@@A; ICatInformation * g_pCatInfo
0x100e85d0  lea     esi, [ebp+catid]
0x100e85d3  lea     edi, [ebp+rgcatid]
0x100e85d6  movsd
0x100e85d7  push    0
0x100e85d9  push    0
0x100e85db  movsd
0x100e85dc  movsd
0x100e85dd  movsd
0x100e85de  mov     eax, [this]
0x100e85e0  mov     esi, [eax+18h]
0x100e85e3  lea     eax, [ebp+rgcatid]
0x100e85e6  push    eax
0x100e85e7  push    1
0x100e85e9  lea     eax, [ebp+clsid]
0x100e85ec  push    eax
0x100e85ed  push    this
0x100e85ee  mov     this, esi; this
0x100e85f0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e85f6  call    esi
0x100e85f8  test    eax, eax
0x100e85fa  jnz     short Confirm
0x100e85fc  cmp     [ebp+sOperation], 1
0x100e8600  jnz     short loc_100E8610
0x100e8602  lea     eax, [ebp+fSafe]
0x100e8605  push    eax
0x100e8606  push    1405h
0x100e860b  jmp     loc_100E858C
0x100e8610  mov     bl, 1
0x100e8612  jmp     short Cleanup_16
```
