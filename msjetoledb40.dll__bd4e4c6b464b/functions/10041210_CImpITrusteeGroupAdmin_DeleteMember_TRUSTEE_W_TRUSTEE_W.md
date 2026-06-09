# CImpITrusteeGroupAdmin::DeleteMember(_TRUSTEE_W *,_TRUSTEE_W *)

- ea: `0x10041210`
- end: `0x10041399`
- name: `?DeleteMember@CImpITrusteeGroupAdmin@@UAGJPAU_TRUSTEE_W@@0@Z`
- size: `393`
- prototype: `int(CImpITrusteeGroupAdmin *__hidden this, struct _TRUSTEE_W *, struct _TRUSTEE_W *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1000ba90`
- `0x1001bdc0`
- `0x1001c380`
- `0x10041210`
- `0x10043840`
- `0x10044090`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1004137d`
- `KERNEL32!LeaveCriticalSection` at `0x1004137d`
- `KERNEL32!EnterCriticalSection` at `0x10041258`
- `KERNEL32!EnterCriticalSection` at `0x10041258`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10041245`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10041245`
- `msjet40!__imp__JetRemoveMember@12` at `0x100412f8`
- `msjet40!__imp__JetRemoveMember@12` at `0x100412f8`

## pseudocode

```c
int __stdcall CImpITrusteeGroupAdmin::DeleteMember(
        CImpITrusteeGroupAdmin *this,
        struct _TRUSTEE_W *a2,
        struct _TRUSTEE_W *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // esi
  CSecuritySession *TrusteeType; // ecx
  int v5; // edi
  CImpITrusteeGroupAdmin *v6; // ebx
  signed int v7; // eax
  const struct _GUID *v9; // [esp+0h] [ebp-24h]
  const struct _GUID *v10; // [esp+4h] [ebp-20h]
  int v11[4]; // [esp+14h] [ebp-10h] BYREF

  v11[0] = 0;
  SetErrorInfo(0, 0);
  v3 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 100);
  EnterCriticalSection(v3);
  v11[3] = 0;
  if ( !a2 || !a3 )
  {
    v5 = -2147024809;
    goto LABEL_28;
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
    goto LABEL_28;
  }
  if ( a2->TrusteeType == TRUSTEE_IS_GROUP )
  {
    v5 = CSecuritySession::CheckForSecuritySesid((CSecuritySession *)(*((_DWORD *)this + 2) + 64), v11);
    if ( v5 < 0 )
    {
      v7 = v11[0];
      v6 = this;
      goto LABEL_22;
    }
    v6 = this;
    v7 = JetRemoveMember(*(_DWORD *)(*((_DWORD *)this + 2) + 68), a2->ptstrName, a3->ptstrName);
    if ( v7 > -1809 )
    {
      if ( v7 != -1802 )
      {
        if ( !v7 )
          goto LABEL_24;
LABEL_19:
        v5 = -2147467259;
LABEL_22:
        if ( v7 )
        {
          CExtError::SendJetErrortoOLEAuto(
            v5,
            *(char **)(*((_DWORD *)v6 + 2) + 68),
            v7,
            (int)&IID_ITrusteeGroupAdmin,
            (int)v9,
            v10);
          goto LABEL_29;
        }
LABEL_24:
        if ( v5 >= 0 )
          goto LABEL_29;
        goto LABEL_28;
      }
    }
    else if ( v7 != -1809 )
    {
      switch ( v7 )
      {
        case -1907:
        case -1904:
          goto LABEL_20;
        case -1903:
          v5 = -2147217813;
          break;
        default:
          goto LABEL_19;
      }
      goto LABEL_22;
    }
LABEL_20:
    v5 = -2147217911;
    goto LABEL_22;
  }
  v5 = -2147217812;
LABEL_28:
  CExtError::SendHRtoOLEAuto((int)&IID_ITrusteeGroupAdmin, 0, v9, (int)v10);
LABEL_29:
  if ( v3 )
    LeaveCriticalSection(v3);
  return v5;
}

```

## disassembly

```asm
0x10041210  mov     edi, edi
0x10041212  push    ebp
0x10041213  mov     ebp, esp
0x10041215  push    0FFFFFFFFh
0x10041217  push    offset ?Abort@CImpITransactionLocal@@UAGJPAUBOID@@HH@Z_SEH
0x1004121c  mov     eax, large fs:0
0x10041222  push    eax
0x10041223  sub     esp, 8
0x10041226  push    ebx
0x10041227  push    esi
0x10041228  push    edi; int
0x10041229  mov     eax, ___security_cookie
0x1004122e  xor     eax, ebp
0x10041230  push    eax; struct _GUID *
0x10041231  lea     eax, [ebp+var_C]
0x10041234  mov     large fs:0, eax
0x1004123a  push    0; perrinfo
0x1004123c  push    0; dwReserved
0x1004123e  mov     [ebp+var_10], 0
0x10041245  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1004124b  mov     edi, [ebp+this]
0x1004124e  mov     esi, [edi+8]
0x10041251  add     esi, 64h ; 'd'
0x10041254  push    esi; lpCriticalSection
0x10041255  mov     [ebp+var_14], esi
0x10041258  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1004125e  mov     ebx, [ebp+arg_4]
0x10041261  mov     [ebp+var_4], 0
0x10041268  test    ebx, ebx
0x1004126a  jz      loc_10041365
0x10041270  mov     eax, [ebp+arg_8]
0x10041273  test    eax, eax
0x10041275  jz      loc_10041365
0x1004127b  cmp     dword ptr [ebx], 0
0x1004127e  jnz     loc_1004135E
0x10041284  cmp     dword ptr [ebx+4], 0
0x10041288  jnz     loc_1004135E
0x1004128e  mov     ecx, [ebx+0Ch]; this
0x10041291  cmp     ecx, 1
0x10041294  jz      short loc_1004129F
0x10041296  cmp     ecx, 2
0x10041299  jnz     loc_1004135E
0x1004129f  cmp     dword ptr [ebx+8], 1
0x100412a3  jnz     loc_1004135E
0x100412a9  cmp     dword ptr [ebx+10h], 0
0x100412ad  jz      loc_1004135E
0x100412b3  push    eax; struct _TRUSTEE_W *
0x100412b4  call    ?fIsValidTrusteeForm@CSecuritySession@@QBEHPAU_TRUSTEE_W@@@Z; CSecuritySession::fIsValidTrusteeForm(_TRUSTEE_W *)
0x100412b9  test    eax, eax
0x100412bb  jz      loc_1004135E
0x100412c1  cmp     dword ptr [ebx+0Ch], 2
0x100412c5  jz      short loc_100412D1
0x100412c7  mov     edi, 80040E6Ch
0x100412cc  jmp     loc_1004136A
0x100412d1  mov     ecx, [edi+8]
0x100412d4  lea     eax, [ebp+var_10]
0x100412d7  add     ecx, 40h ; '@'; this
0x100412da  push    eax; int *
0x100412db  call    ?CheckForSecuritySesid@CSecuritySession@@QAEJAAJ@Z; CSecuritySession::CheckForSecuritySesid(long &)
0x100412e0  mov     edi, eax
0x100412e2  test    edi, edi
0x100412e4  js      short loc_10041339
0x100412e6  mov     eax, [ebp+arg_8]
0x100412e9  push    dword ptr [eax+10h]
0x100412ec  push    dword ptr [ebx+10h]
0x100412ef  mov     ebx, [ebp+this]
0x100412f2  mov     ecx, [ebx+8]
0x100412f5  push    dword ptr [ecx+44h]
0x100412f8  call    ds:__imp__JetRemoveMember@12; JetRemoveMember(x,x,x)
0x100412fe  cmp     eax, 0FFFFF8EFh
0x10041303  jg      short loc_10041320
0x10041305  jz      short loc_10041332; jumptable 10041312 cases -1907,-1904
0x10041307  lea     ecx, [eax+773h]; switch 5 cases
0x1004130d  cmp     ecx, 4
0x10041310  ja      short def_10041312; jumptable 10041312 default case, cases -1906,-1905
0x10041312  jmp     ds:jpt_10041312[ecx*4]; switch jump
0x10041319  mov     edi, 80040E6Bh; jumptable 10041312 case -1903
0x1004131e  jmp     short loc_1004133F
0x10041320  cmp     eax, 0FFFFF8F6h
0x10041325  jz      short loc_10041332; jumptable 10041312 cases -1907,-1904
0x10041327  test    eax, eax
0x10041329  jz      short loc_10041358
0x1004132b  mov     edi, 80004005h; jumptable 10041312 default case, cases -1906,-1905
0x10041330  jmp     short loc_1004133F
0x10041332  mov     edi, 80040E09h; jumptable 10041312 cases -1907,-1904
0x10041337  jmp     short loc_1004133F
0x10041339  mov     eax, [ebp+var_10]
0x1004133c  mov     ebx, [ebp+this]
0x1004133f  test    eax, eax
0x10041341  jz      short loc_10041358
0x10041343  mov     ecx, [ebx+8]
0x10041346  mov     edx, edi
0x10041348  push    offset _IID_ITrusteeGroupAdmin; int
0x1004134d  push    eax; unsigned int
0x1004134e  mov     ecx, [ecx+44h]
0x10041351  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10041356  jmp     short loc_10041378
0x10041358  test    edi, edi
0x1004135a  jns     short loc_10041378
0x1004135c  jmp     short loc_1004136A
0x1004135e  mov     edi, 80040E6Ah
0x10041363  jmp     short loc_1004136A
0x10041365  mov     edi, 80070057h
0x1004136a  push    0; int
0x1004136c  push    offset _IID_ITrusteeGroupAdmin; int
0x10041371  mov     edx, edi
0x10041373  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10041378  test    esi, esi
0x1004137a  jz      short loc_10041383
0x1004137c  push    esi; lpCriticalSection
0x1004137d  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10041383  mov     eax, edi
0x10041385  mov     ecx, [ebp+var_C]
0x10041388  mov     large fs:0, ecx
0x1004138f  pop     ecx
0x10041390  pop     edi
0x10041391  pop     esi
0x10041392  pop     ebx
0x10041393  mov     esp, ebp
0x10041395  pop     ebp
0x10041396  retn    0Ch
0x1004dde0  lea     ecx, [ebp+var_14]; this
0x1004dde3  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dded  nop
0x1004ddee  nop
0x1004ddef  mov     edx, [esp-4+arg_4]
0x1004ddf3  lea     eax, [edx+0Ch]
0x1004ddf6  mov     ecx, [edx-18h]
0x1004ddf9  xor     ecx, eax; StackCookie
0x1004ddfb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004de00  mov     eax, offset stru_1004F3D8
0x1004de05  jmp     ___CxxFrameHandler3
```
