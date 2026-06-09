# CImpITrusteeAdmin::DeleteTrustee(_TRUSTEE_W *)

- ea: `0x10040ab0`
- end: `0x10040c29`
- name: `?DeleteTrustee@CImpITrusteeAdmin@@UAGJPAU_TRUSTEE_W@@@Z`
- size: `377`
- prototype: `int(CImpITrusteeAdmin *__hidden this, struct _TRUSTEE_W *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1000ba90`
- `0x1001bdc0`
- `0x1001c380`
- `0x10040ab0`
- `0x10043840`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10040c0d`
- `KERNEL32!LeaveCriticalSection` at `0x10040c0d`
- `KERNEL32!EnterCriticalSection` at `0x10040af8`
- `KERNEL32!EnterCriticalSection` at `0x10040af8`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10040ae5`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10040ae5`
- `msjet40!__imp__JetDeleteGroup@8` at `0x10040b7f`
- `msjet40!__imp__JetDeleteGroup@8` at `0x10040b7f`
- `msjet40!__imp__JetDeleteUser@8` at `0x10040b77`
- `msjet40!__imp__JetDeleteUser@8` at `0x10040b77`

## pseudocode

```c
int __stdcall CImpITrusteeAdmin::DeleteTrustee(CImpITrusteeAdmin *this, struct _TRUSTEE_W *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // esi
  int v3; // edi
  TRUSTEE_TYPE TrusteeType; // eax
  signed int v5; // eax
  int v7; // [esp-8h] [ebp-2Ch]
  LPWCH ptstrName; // [esp-4h] [ebp-28h]
  const struct _GUID *v9; // [esp+0h] [ebp-24h]
  const struct _GUID *v10; // [esp+4h] [ebp-20h]
  int v11[4]; // [esp+14h] [ebp-10h] BYREF

  v11[0] = 0;
  SetErrorInfo(0, 0);
  v2 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 100);
  EnterCriticalSection(v2);
  v11[3] = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
LABEL_31:
    CExtError::SendHRtoOLEAuto((int)&IID_ITrusteeAdmin, 0, v9, (int)v10);
    goto LABEL_32;
  }
  if ( a2->pMultipleTrustee
    || a2->MultipleTrusteeOperation
    || (TrusteeType = a2->TrusteeType, TrusteeType != TRUSTEE_IS_USER) && TrusteeType != TRUSTEE_IS_GROUP
    || a2->TrusteeForm != TRUSTEE_IS_NAME
    || !a2->ptstrName )
  {
    v3 = -2147217814;
    goto LABEL_31;
  }
  v3 = CSecuritySession::CheckForSecuritySesid((CSecuritySession *)(*((_DWORD *)this + 2) + 64), v11);
  if ( v3 < 0 )
  {
    v5 = v11[0];
  }
  else
  {
    ptstrName = a2->ptstrName;
    v7 = *(_DWORD *)(*((_DWORD *)this + 2) + 68);
    if ( a2->TrusteeType == TRUSTEE_IS_USER )
      v5 = JetDeleteUser(v7, ptstrName);
    else
      v5 = JetDeleteGroup(v7, ptstrName);
    if ( v5 <= -1903 )
    {
      if ( v5 == -1903 )
      {
        v3 = -2147217813;
        goto LABEL_26;
      }
      if ( v5 == -1910 || v5 == -1907 || v5 == -1906 )
      {
LABEL_18:
        v3 = -2147217911;
        goto LABEL_26;
      }
      goto LABEL_24;
    }
    if ( v5 == -1809 || v5 == -1802 )
      goto LABEL_18;
    if ( !v5 )
      goto LABEL_32;
    if ( v5 < 0 )
LABEL_24:
      v3 = -2147467259;
  }
LABEL_26:
  if ( v5 )
  {
    CExtError::SendJetErrortoOLEAuto(
      v3,
      *(char **)(*((_DWORD *)this + 2) + 68),
      v5,
      (int)&IID_ITrusteeAdmin,
      (int)v9,
      v10);
    goto LABEL_32;
  }
  if ( v3 < 0 )
    goto LABEL_31;
LABEL_32:
  if ( v2 )
    LeaveCriticalSection(v2);
  return v3;
}

```

## disassembly

```asm
0x10040ab0  mov     edi, edi
0x10040ab2  push    ebp
0x10040ab3  mov     ebp, esp
0x10040ab5  push    0FFFFFFFFh
0x10040ab7  push    offset ?Abort@CImpITransactionLocal@@UAGJPAUBOID@@HH@Z_SEH
0x10040abc  mov     eax, large fs:0
0x10040ac2  push    eax
0x10040ac3  sub     esp, 8
0x10040ac6  push    ebx
0x10040ac7  push    esi
0x10040ac8  push    edi; int
0x10040ac9  mov     eax, ___security_cookie
0x10040ace  xor     eax, ebp
0x10040ad0  push    eax; struct _GUID *
0x10040ad1  lea     eax, [ebp+var_C]
0x10040ad4  mov     large fs:0, eax
0x10040ada  push    0; perrinfo
0x10040adc  push    0; dwReserved
0x10040ade  mov     [ebp+var_10], 0
0x10040ae5  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10040aeb  mov     edi, [ebp+this]
0x10040aee  mov     esi, [edi+8]
0x10040af1  add     esi, 64h ; 'd'
0x10040af4  push    esi; lpCriticalSection
0x10040af5  mov     [ebp+var_14], esi
0x10040af8  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10040afe  mov     ebx, [ebp+arg_4]
0x10040b01  mov     [ebp+var_4], 0
0x10040b08  test    ebx, ebx
0x10040b0a  jnz     short loc_10040B16
0x10040b0c  mov     edi, 80070057h
0x10040b11  jmp     loc_10040BFA
0x10040b16  cmp     dword ptr [ebx], 0
0x10040b19  jnz     loc_10040BF5
0x10040b1f  cmp     dword ptr [ebx+4], 0
0x10040b23  jnz     loc_10040BF5
0x10040b29  mov     eax, [ebx+0Ch]
0x10040b2c  cmp     eax, 1
0x10040b2f  jz      short loc_10040B3A
0x10040b31  cmp     eax, 2
0x10040b34  jnz     loc_10040BF5
0x10040b3a  cmp     dword ptr [ebx+8], 1
0x10040b3e  jnz     loc_10040BF5
0x10040b44  cmp     dword ptr [ebx+10h], 0
0x10040b48  jz      loc_10040BF5
0x10040b4e  mov     ecx, [edi+8]
0x10040b51  lea     eax, [ebp+var_10]
0x10040b54  add     ecx, 40h ; '@'; this
0x10040b57  push    eax; int *
0x10040b58  call    ?CheckForSecuritySesid@CSecuritySession@@QAEJAAJ@Z; CSecuritySession::CheckForSecuritySesid(long &)
0x10040b5d  mov     edi, eax
0x10040b5f  test    edi, edi
0x10040b61  js      short loc_10040BCC
0x10040b63  cmp     dword ptr [ebx+0Ch], 1
0x10040b67  mov     ecx, [ebp+this]
0x10040b6a  mov     eax, [ebx+10h]
0x10040b6d  push    eax
0x10040b6e  mov     ecx, [ecx+8]
0x10040b71  mov     ecx, [ecx+44h]
0x10040b74  push    ecx
0x10040b75  jnz     short loc_10040B7F
0x10040b77  call    ds:__imp__JetDeleteUser@8; JetDeleteUser(x,x)
0x10040b7d  jmp     short loc_10040B85
0x10040b7f  call    ds:__imp__JetDeleteGroup@8; JetDeleteGroup(x,x)
0x10040b85  cmp     eax, 0FFFFF891h
0x10040b8a  jg      short loc_10040BB1
0x10040b8c  jz      short loc_10040BAA
0x10040b8e  cmp     eax, 0FFFFF88Ah
0x10040b93  jz      short loc_10040BA3
0x10040b95  cmp     eax, 0FFFFF88Dh
0x10040b9a  jz      short loc_10040BA3
0x10040b9c  cmp     eax, 0FFFFF88Eh
0x10040ba1  jnz     short loc_10040BC5
0x10040ba3  mov     edi, 80040E09h
0x10040ba8  jmp     short loc_10040BCF
0x10040baa  mov     edi, 80040E6Bh
0x10040baf  jmp     short loc_10040BCF
0x10040bb1  cmp     eax, 0FFFFF8EFh
0x10040bb6  jz      short loc_10040BA3
0x10040bb8  cmp     eax, 0FFFFF8F6h
0x10040bbd  jz      short loc_10040BA3
0x10040bbf  test    eax, eax
0x10040bc1  jz      short loc_10040C08
0x10040bc3  jns     short loc_10040BCF
0x10040bc5  mov     edi, 80004005h
0x10040bca  jmp     short loc_10040BCF
0x10040bcc  mov     eax, [ebp+var_10]
0x10040bcf  mov     ecx, edi
0x10040bd1  test    eax, eax
0x10040bd3  jz      short loc_10040BED
0x10040bd5  push    offset _IID_ITrusteeAdmin; int
0x10040bda  push    eax; unsigned int
0x10040bdb  mov     eax, [ebp+this]
0x10040bde  mov     edx, edi
0x10040be0  mov     ecx, [eax+8]
0x10040be3  mov     ecx, [ecx+44h]
0x10040be6  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10040beb  jmp     short loc_10040C08
0x10040bed  mov     edi, ecx
0x10040bef  test    ecx, ecx
0x10040bf1  jns     short loc_10040C08
0x10040bf3  jmp     short loc_10040BFA
0x10040bf5  mov     edi, 80040E6Ah
0x10040bfa  push    0; int
0x10040bfc  push    offset _IID_ITrusteeAdmin; int
0x10040c01  mov     edx, edi
0x10040c03  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10040c08  test    esi, esi
0x10040c0a  jz      short loc_10040C13
0x10040c0c  push    esi; lpCriticalSection
0x10040c0d  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10040c13  mov     eax, edi
0x10040c15  mov     ecx, [ebp+var_C]
0x10040c18  mov     large fs:0, ecx
0x10040c1f  pop     ecx
0x10040c20  pop     edi
0x10040c21  pop     esi
0x10040c22  pop     ebx
0x10040c23  mov     esp, ebp
0x10040c25  pop     ebp
0x10040c26  retn    8
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
