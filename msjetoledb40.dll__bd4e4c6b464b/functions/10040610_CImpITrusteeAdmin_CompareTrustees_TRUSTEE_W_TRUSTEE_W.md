# CImpITrusteeAdmin::CompareTrustees(_TRUSTEE_W *,_TRUSTEE_W *)

- ea: `0x10040610`
- end: `0x100407cf`
- name: `?CompareTrustees@CImpITrusteeAdmin@@UAGJPAU_TRUSTEE_W@@0@Z`
- size: `447`
- prototype: `int(CImpITrusteeAdmin *__hidden this, struct _TRUSTEE_W *, struct _TRUSTEE_W *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1000ba90`
- `0x1001bdc0`
- `0x1001c380`
- `0x10040610`
- `0x10043840`
- `0x100438f0`
- `0x10043f20`
- `0x10044090`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1004075e`
- `msvcrt!_wcsicmp` at `0x1004075e`
- `KERNEL32!LeaveCriticalSection` at `0x100407b3`
- `KERNEL32!LeaveCriticalSection` at `0x100407b3`
- `KERNEL32!EnterCriticalSection` at `0x1004065f`
- `KERNEL32!EnterCriticalSection` at `0x1004065f`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1004064c`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1004064c`

## pseudocode

```c
int __stdcall CImpITrusteeAdmin::CompareTrustees(CImpITrusteeAdmin *this, struct _TRUSTEE_W *a2, struct _TRUSTEE_W *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // esi
  CSecuritySession *TrusteeType; // ecx
  int v5; // edi
  const wchar_t *ptstrName; // edx
  LPWCH v7; // eax
  CImpITrusteeAdmin *v8; // ebx
  const struct _GUID *v10; // [esp+0h] [ebp-28h]
  const struct _GUID *v11; // [esp+4h] [ebp-24h]
  int v12; // [esp+14h] [ebp-14h] BYREF
  unsigned int v13[4]; // [esp+18h] [ebp-10h] BYREF

  v13[0] = 0;
  v12 = 0;
  SetErrorInfo(0, 0);
  v3 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 100);
  EnterCriticalSection(v3);
  v13[3] = 0;
  if ( !a2 || !a3 )
  {
    v5 = -2147024809;
    goto LABEL_29;
  }
  if ( a2->pMultipleTrustee
    || a2->MultipleTrusteeOperation
    || (TrusteeType = (CSecuritySession *)a2->TrusteeType, TrusteeType != (CSecuritySession *)1)
    && TrusteeType != (CSecuritySession *)2
    || a2->TrusteeForm != TRUSTEE_IS_NAME
    || !a2->ptstrName
    || !CSecuritySession::fIsValidTrusteeForm(TrusteeType, a3) )
  {
    v5 = -2147217814;
LABEL_29:
    CExtError::SendHRtoOLEAuto(v5, (__int128 *)&IID_ITrusteeAdmin, 0, v10, (int)v11);
    goto LABEL_30;
  }
  v5 = CSecuritySession::CheckForSecuritySesid((CSecuritySession *)(*((_DWORD *)this + 2) + 64), (int *)v13);
  if ( v5 < 0 )
    goto LABEL_18;
  v5 = CSecuritySession::CheckForSecurityDbid((CSecuritySession *)(*((_DWORD *)this + 2) + 64), (int *)v13, &v12);
  if ( v5 < 0 )
    goto LABEL_18;
  v5 = CSecuritySession::fTrusteeExistsInDataSource((CSecuritySession *)(*((_DWORD *)this + 2) + 64), a2, (int *)v13);
  if ( v5 < 0 )
    goto LABEL_18;
  if ( a2->pMultipleTrustee == a3->pMultipleTrustee
    && a2->MultipleTrusteeOperation == a3->MultipleTrusteeOperation
    && a2->TrusteeForm == a3->TrusteeForm )
  {
    ptstrName = a2->ptstrName;
    v7 = a3->ptstrName;
    if ( ptstrName )
    {
      if ( v7 && !__wcsicmp(ptstrName, a3->ptstrName) )
        goto LABEL_18;
    }
    else if ( !v7 )
    {
LABEL_18:
      v8 = this;
      goto LABEL_19;
    }
  }
  v8 = this;
  v5 = CSecuritySession::fTrusteeExistsInDataSource((CSecuritySession *)(*((_DWORD *)this + 2) + 64), a3, (int *)v13);
  if ( v5 >= 0 )
    v5 = 1;
LABEL_19:
  if ( v13[0] )
  {
    CExtError::SendJetErrortoOLEAuto(
      v5,
      *(char **)(*((_DWORD *)v8 + 2) + 68),
      v13[0],
      (int)&IID_ITrusteeAdmin,
      (int)v10,
      v11);
    goto LABEL_30;
  }
  if ( v5 < 0 )
    goto LABEL_29;
LABEL_30:
  if ( v3 )
    LeaveCriticalSection(v3);
  return v5;
}

```

## disassembly

```asm
0x10040610  mov     edi, edi
0x10040612  push    ebp
0x10040613  mov     ebp, esp
0x10040615  push    0FFFFFFFFh
0x10040617  push    offset ?DropColumn@CImpITableDef@@UAGJPAUtagDBID@@0@Z_SEH
0x1004061c  mov     eax, large fs:0
0x10040622  push    eax
0x10040623  sub     esp, 0Ch
0x10040626  push    ebx
0x10040627  push    esi
0x10040628  push    edi; int
0x10040629  mov     eax, ___security_cookie
0x1004062e  xor     eax, ebp
0x10040630  push    eax; struct _GUID *
0x10040631  lea     eax, [ebp+var_C]
0x10040634  mov     large fs:0, eax
0x1004063a  push    0; perrinfo
0x1004063c  push    0; dwReserved
0x1004063e  mov     [ebp+var_10], 0
0x10040645  mov     [ebp+var_14], 0
0x1004064c  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10040652  mov     edi, [ebp+this]
0x10040655  mov     esi, [edi+8]
0x10040658  add     esi, 64h ; 'd'
0x1004065b  push    esi; lpCriticalSection
0x1004065c  mov     [ebp+var_18], esi
0x1004065f  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10040665  mov     ebx, [ebp+arg_4]
0x10040668  mov     [ebp+var_4], 0
0x1004066f  test    ebx, ebx
0x10040671  jz      loc_1004079B
0x10040677  mov     eax, [ebp+arg_8]
0x1004067a  test    eax, eax
0x1004067c  jz      loc_1004079B
0x10040682  cmp     dword ptr [ebx], 0
0x10040685  jnz     loc_10040794
0x1004068b  cmp     dword ptr [ebx+4], 0
0x1004068f  jnz     loc_10040794
0x10040695  mov     ecx, [ebx+0Ch]; this
0x10040698  cmp     ecx, 1
0x1004069b  jz      short loc_100406A6
0x1004069d  cmp     ecx, 2
0x100406a0  jnz     loc_10040794
0x100406a6  cmp     dword ptr [ebx+8], 1
0x100406aa  jnz     loc_10040794
0x100406b0  cmp     dword ptr [ebx+10h], 0
0x100406b4  jz      loc_10040794
0x100406ba  push    eax; struct _TRUSTEE_W *
0x100406bb  call    ?fIsValidTrusteeForm@CSecuritySession@@QBEHPAU_TRUSTEE_W@@@Z; CSecuritySession::fIsValidTrusteeForm(_TRUSTEE_W *)
0x100406c0  test    eax, eax
0x100406c2  jz      loc_10040794
0x100406c8  mov     ecx, [edi+8]
0x100406cb  lea     eax, [ebp+var_10]
0x100406ce  add     ecx, 40h ; '@'; this
0x100406d1  push    eax; int *
0x100406d2  call    ?CheckForSecuritySesid@CSecuritySession@@QAEJAAJ@Z; CSecuritySession::CheckForSecuritySesid(long &)
0x100406d7  mov     edi, eax
0x100406d9  test    edi, edi
0x100406db  js      short loc_10040739
0x100406dd  mov     ecx, [ebp+this]
0x100406e0  lea     eax, [ebp+var_14]
0x100406e3  push    eax; int *
0x100406e4  lea     eax, [ebp+var_10]
0x100406e7  push    eax; int *
0x100406e8  mov     ecx, [ecx+8]
0x100406eb  add     ecx, 40h ; '@'; this
0x100406ee  call    ?CheckForSecurityDbid@CSecuritySession@@QAEJAAJAAH@Z; CSecuritySession::CheckForSecurityDbid(long &,int &)
0x100406f3  mov     edi, eax
0x100406f5  test    edi, edi
0x100406f7  js      short loc_10040739
0x100406f9  mov     eax, [ebp+this]
0x100406fc  mov     ecx, [eax+8]
0x100406ff  lea     eax, [ebp+var_10]
0x10040702  push    eax; int *
0x10040703  add     ecx, 40h ; '@'; this
0x10040706  push    ebx; struct _TRUSTEE_W *
0x10040707  call    ?fTrusteeExistsInDataSource@CSecuritySession@@QAEJPAU_TRUSTEE_W@@AAJ@Z; CSecuritySession::fTrusteeExistsInDataSource(_TRUSTEE_W *,long &)
0x1004070c  mov     edi, eax
0x1004070e  test    edi, edi
0x10040710  js      short loc_10040739
0x10040712  mov     ecx, [ebp+arg_8]
0x10040715  mov     eax, [ebx]
0x10040717  cmp     eax, [ecx]
0x10040719  jnz     short loc_1004076B
0x1004071b  mov     eax, [ebx+4]
0x1004071e  cmp     eax, [ecx+4]
0x10040721  jnz     short loc_1004076B
0x10040723  mov     eax, [ebx+8]
0x10040726  cmp     eax, [ecx+8]
0x10040729  jnz     short loc_1004076B
0x1004072b  mov     edx, [ebx+10h]
0x1004072e  mov     eax, [ecx+10h]
0x10040731  test    edx, edx
0x10040733  jnz     short loc_10040758
0x10040735  test    eax, eax
0x10040737  jnz     short loc_1004076B
0x10040739  mov     ebx, [ebp+this]
0x1004073c  mov     eax, [ebp+var_10]
0x1004073f  test    eax, eax
0x10040741  jz      short loc_1004078E
0x10040743  mov     ecx, [ebx+8]
0x10040746  mov     edx, edi
0x10040748  push    offset _IID_ITrusteeAdmin; int
0x1004074d  push    eax; unsigned int
0x1004074e  mov     ecx, [ecx+44h]
0x10040751  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10040756  jmp     short loc_100407AE
0x10040758  test    eax, eax
0x1004075a  jz      short loc_1004076B
0x1004075c  push    eax; String2
0x1004075d  push    edx; String1
0x1004075e  call    ds:__imp___wcsicmp
0x10040764  add     esp, 8
0x10040767  test    eax, eax
0x10040769  jz      short loc_10040739
0x1004076b  mov     ebx, [ebp+this]
0x1004076e  lea     eax, [ebp+var_10]
0x10040771  push    eax; int *
0x10040772  mov     eax, [ebp+arg_8]
0x10040775  push    eax; struct _TRUSTEE_W *
0x10040776  mov     ecx, [ebx+8]
0x10040779  add     ecx, 40h ; '@'; this
0x1004077c  call    ?fTrusteeExistsInDataSource@CSecuritySession@@QAEJPAU_TRUSTEE_W@@AAJ@Z; CSecuritySession::fTrusteeExistsInDataSource(_TRUSTEE_W *,long &)
0x10040781  mov     edi, eax
0x10040783  test    edi, edi
0x10040785  js      short loc_1004073C
0x10040787  mov     edi, 1
0x1004078c  jmp     short loc_1004073C
0x1004078e  test    edi, edi
0x10040790  jns     short loc_100407AE
0x10040792  jmp     short loc_100407A0
0x10040794  mov     edi, 80040E6Ah
0x10040799  jmp     short loc_100407A0
0x1004079b  mov     edi, 80070057h
0x100407a0  push    0; int
0x100407a2  push    offset _IID_ITrusteeAdmin; int
0x100407a7  mov     edx, edi
0x100407a9  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x100407ae  test    esi, esi
0x100407b0  jz      short loc_100407B9
0x100407b2  push    esi; lpCriticalSection
0x100407b3  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100407b9  mov     eax, edi
0x100407bb  mov     ecx, [ebp+var_C]
0x100407be  mov     large fs:0, ecx
0x100407c5  pop     ecx
0x100407c6  pop     edi
0x100407c7  pop     esi
0x100407c8  pop     ebx
0x100407c9  mov     esp, ebp
0x100407cb  pop     ebp
0x100407cc  retn    0Ch
0x1004dd50  lea     ecx, [ebp+var_18]; this
0x1004dd53  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dd5d  nop
0x1004dd5e  nop
0x1004dd5f  mov     edx, [esp-4+arg_4]
0x1004dd63  lea     eax, [edx+0Ch]
0x1004dd66  mov     ecx, [edx-1Ch]
0x1004dd69  xor     ecx, eax; StackCookie
0x1004dd6b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004dd70  mov     eax, offset stru_1004F354
0x1004dd75  jmp     ___CxxFrameHandler3
```
