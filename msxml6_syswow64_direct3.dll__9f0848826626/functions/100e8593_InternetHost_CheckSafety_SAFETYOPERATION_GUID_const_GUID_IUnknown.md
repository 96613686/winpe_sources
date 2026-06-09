# InternetHost::CheckSafety(SAFETYOPERATION,_GUID const &,_GUID,IUnknown *)

- ea: `0x100e8593`
- end: `0x100e8734`
- name: `?CheckSafety@InternetHost@@IAE_NW4SAFETYOPERATION@@ABU_GUID@@U3@PAUIUnknown@@@Z`
- size: `417`
- prototype: `bool __thiscall(InternetHost *this, SAFETYOPERATION sOperation, const _GUID *clsid, _GUID pUnk, IUnknown *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1006b0a0`

## callees

- `0x10067b20`
- `0x1006b470`
- `0x1007618e`
- `0x100e8593`
- `0x100e8924`

## import_xrefs

- `urlmon!CompatFlagsFromClsid` at `0x100e8611`
- `urlmon!CompatFlagsFromClsid` at `0x100e8611`

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
0x100e8593  mov     edi, edi
0x100e8595  push    ebp
0x100e8596  mov     ebp, esp
0x100e8598  sub     esp, 4Ch
0x100e859b  mov     eax, ___security_cookie
0x100e85a0  xor     eax, ebp
0x100e85a2  mov     [ebp+var_4], eax
0x100e85a5  push    ebx
0x100e85a6  push    esi
0x100e85a7  push    edi; ppUnk
0x100e85a8  lea     esi, [ebp+arg_8]
0x100e85ab  mov     eax, [ebp+pUnk]
0x100e85ae  lea     edi, [ebp+clsid]
0x100e85b1  mov     [ebp+var_34], this
0x100e85b4  movsd
0x100e85b5  xor     this, this
0x100e85b7  mov     [ebp+var_3C], eax
0x100e85ba  mov     bl, cl
0x100e85bc  mov     eax, [ebp+sOperation]
0x100e85bf  mov     [ebp+fSafe], bl
0x100e85c2  movsd
0x100e85c3  mov     [ebp+dwCompat], this
0x100e85c6  mov     [ebp+dwMiscStatus], this
0x100e85c9  mov     [ebp+pOSafe], this
0x100e85cc  movsd
0x100e85cd  movsd
0x100e85ce  lea     edi, [ebp+catid]
0x100e85d1  mov     esi, offset _GUID_NULL
0x100e85d6  movsd
0x100e85d7  movsd
0x100e85d8  movsd
0x100e85d9  movsd
0x100e85da  mov     edi, this
0x100e85dc  sub     eax, this
0x100e85de  jz      short loc_100E85F6
0x100e85e0  sub     eax, 1
0x100e85e3  jnz     short loc_100E8605
0x100e85e5  mov     esi, offset _CATID_SafeForScripting
0x100e85ea  lea     edi, [ebp+catid]
0x100e85ed  movsd
0x100e85ee  movsd
0x100e85ef  movsd
0x100e85f0  movsd
0x100e85f1  xor     edi, edi
0x100e85f3  inc     edi
0x100e85f4  jmp     short loc_100E8605
0x100e85f6  mov     esi, offset _CATID_SafeForInitializing
0x100e85fb  lea     edi, [ebp+catid]
0x100e85fe  push    2
0x100e8600  movsd
0x100e8601  movsd
0x100e8602  movsd
0x100e8603  movsd
0x100e8604  pop     edi
0x100e8605  lea     eax, [ebp+dwMiscStatus]
0x100e8608  push    eax; pdwMiscStatusFlags
0x100e8609  lea     eax, [ebp+dwCompat]
0x100e860c  push    eax; pdwCompatFlags
0x100e860d  lea     eax, [ebp+clsid]
0x100e8610  push    eax; pclsid
0x100e8611  call    ds:__imp__CompatFlagsFromClsid@12; CompatFlagsFromClsid(x,x,x)
0x100e8617  test    eax, eax
0x100e8619  js      Cleanup_16
0x100e861f  test    [ebp+dwCompat], 400h
0x100e8626  jnz     Cleanup_16
0x100e862c  test    byte ptr [ebp+dwCompat], 2
0x100e8630  jnz     short Confirm
0x100e8632  mov     this, [ebp+var_3C]
0x100e8635  mov     eax, [this]
0x100e8637  mov     esi, [eax]
0x100e8639  lea     eax, [ebp+pOSafe]
0x100e863c  push    eax
0x100e863d  push    offset _IID_IObjectSafety
0x100e8642  push    this
0x100e8643  mov     this, esi; this
0x100e8645  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e864b  call    esi
0x100e864d  test    eax, eax
0x100e864f  js      loc_100E86E1
0x100e8655  mov     this, [ebp+pOSafe]
0x100e8658  test    this, this
0x100e865a  jz      loc_100E86E1
0x100e8660  cmp     [ebp+sOperation], 1
0x100e8664  jnz     short loc_100E8688
0x100e8666  mov     eax, [this]
0x100e8668  push    edi
0x100e8669  push    edi
0x100e866a  push    offset _IID_IDispatchEx
0x100e866f  mov     esi, [eax+10h]
0x100e8672  push    this
0x100e8673  mov     this, esi; this
0x100e8675  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e867b  call    esi
0x100e867d  test    eax, eax
0x100e867f  jns     loc_100E8722
0x100e8685  mov     this, [ebp+pOSafe]
0x100e8688  mov     eax, [this]
0x100e868a  push    edi
0x100e868b  push    edi
0x100e868c  push    offset _IID_IDispatch
0x100e8691  mov     esi, [eax+10h]
0x100e8694  push    this
0x100e8695  mov     this, esi; this
0x100e8697  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e869d  call    esi
0x100e869f  test    eax, eax
0x100e86a1  jns     short EnsureSafeForScripting
0x100e86a3  lea     eax, [ebp+fSafe]
0x100e86a6  push    eax; pfAllow
0x100e86a7  push    1204h; dwAction
0x100e86ac  mov     this, [ebp+var_34]; this
0x100e86af  call    ?IsAllowableAction@InternetHost@@IAEJKPA_N@Z; InternetHost::IsAllowableAction(ulong,bool *)
0x100e86b4  mov     bl, [ebp+fSafe]
0x100e86b7  mov     edx, [ebp+pOSafe]
0x100e86ba  test    edx, edx
0x100e86bc  jz      short loc_100E86CE
0x100e86be  mov     this, [edx]
0x100e86c0  push    edx
0x100e86c1  mov     esi, [this+8]
0x100e86c4  mov     this, esi; this
0x100e86c6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e86cc  call    esi
0x100e86ce  mov     this, [ebp+var_4]
0x100e86d1  mov     al, bl
0x100e86d3  pop     edi
0x100e86d4  pop     esi
0x100e86d5  xor     this, ebp; cookie
0x100e86d7  pop     ebx
0x100e86d8  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100e86dd  leave
0x100e86de  retn    1Ch
0x100e86e1  call    ?CreateCatalogInformation@@YGJPAPAUICatInformation@@@Z; CreateCatalogInformation(ICatInformation * *)
0x100e86e6  test    eax, eax
0x100e86e8  js      short Cleanup_16
0x100e86ea  mov     this, ?g_pCatInfo@@3PAUICatInformation@@A; ICatInformation * g_pCatInfo
0x100e86f0  lea     esi, [ebp+catid]
0x100e86f3  lea     edi, [ebp+rgcatid]
0x100e86f6  movsd
0x100e86f7  push    0
0x100e86f9  push    0
0x100e86fb  movsd
0x100e86fc  movsd
0x100e86fd  movsd
0x100e86fe  mov     eax, [this]
0x100e8700  mov     esi, [eax+18h]
0x100e8703  lea     eax, [ebp+rgcatid]
0x100e8706  push    eax
0x100e8707  push    1
0x100e8709  lea     eax, [ebp+clsid]
0x100e870c  push    eax
0x100e870d  push    this
0x100e870e  mov     this, esi; this
0x100e8710  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e8716  call    esi
0x100e8718  test    eax, eax
0x100e871a  jnz     short Confirm
0x100e871c  cmp     [ebp+sOperation], 1
0x100e8720  jnz     short loc_100E8730
0x100e8722  lea     eax, [ebp+fSafe]
0x100e8725  push    eax
0x100e8726  push    1405h
0x100e872b  jmp     loc_100E86AC
0x100e8730  mov     bl, 1
0x100e8732  jmp     short Cleanup_16
```
