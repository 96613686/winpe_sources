# ShowNT5SecurityDescriptor

- ea: `0x18007d434`
- end: `0x18007d8bc`
- name: `ShowNT5SecurityDescriptor`
- size: `1160`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007c700`

## callees

- `0x180004d91`
- `0x18000d1f0`
- `0x18000f35c`
- `0x18000f7e4`
- `0x1800129cc`
- `0x18002c4dc`
- `0x18002c6c8`
- `0x18007d11c`
- `0x18007d434`
- `0x18007d8c4`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorSacl` at `0x18007d7a5`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x18007d7a5`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18007d44c`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18007d44c`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18007d6ec`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18007d6ec`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18007d472`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18007d472`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x18007d575`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x18007d575`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x18007d627`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x18007d627`
- `KERNEL32!GetLastError` at `0x18007d47c`
- `KERNEL32!GetLastError` at `0x18007d57f`
- `KERNEL32!GetLastError` at `0x18007d631`
- `KERNEL32!GetLastError` at `0x18007d6f6`
- `KERNEL32!GetLastError` at `0x18007d7af`
- `KERNEL32!GetLastError` at `0x18007d47c`
- `KERNEL32!GetLastError` at `0x18007d57f`
- `KERNEL32!GetLastError` at `0x18007d631`
- `KERNEL32!GetLastError` at `0x18007d6f6`
- `KERNEL32!GetLastError` at `0x18007d7af`

## pseudocode

```c
void __fastcall ShowNT5SecurityDescriptor(PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  DWORD LastError; // eax
  unsigned int v3; // esi
  PVOID *v4; // rcx
  DWORD v5; // eax
  unsigned int v6; // esi
  DWORD v7; // eax
  unsigned int v8; // esi
  DWORD v9; // eax
  unsigned int v10; // esi
  DWORD v11; // eax
  unsigned int v12; // esi
  PSID pOwner; // [rsp+30h] [rbp-38h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-30h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+40h] [rbp-28h] BYREF
  WORD pControl; // [rsp+90h] [rbp+28h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+98h] [rbp+30h] BYREF
  WINBOOL bDaclPresent; // [rsp+A0h] [rbp+38h] BYREF
  DWORD dwRevision; // [rsp+A8h] [rbp+40h] BYREF

  if ( !pSecurityDescriptor || !IsValidSecurityDescriptor(pSecurityDescriptor) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 37, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids);
    LogIllegalPoint((wchar_t *)L"dumpauthzutl", 0x5FDu);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, 0x53Au);
    throw (bad_win32_error *)pExceptionObject;
  }
  dwRevision = 0;
  pControl = 0;
  if ( !GetSecurityDescriptorControl(pSecurityDescriptor, &pControl, &dwRevision) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 38, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids, LastError);
    if ( v3 )
      LogMsgNTStatus(v3, (wchar_t *)L"dumpauthzutl", 0x5FEu);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v3);
    throw (bad_win32_error *)pExceptionObject;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 39, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 268) & 4) != 0 )
      WPP_SF_Dd(v4[32], 40, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids, pControl, dwRevision);
  }
  pOwner = 0;
  bOwnerDefaulted = 0;
  if ( !GetSecurityDescriptorOwner(pSecurityDescriptor, &pOwner, &bOwnerDefaulted) )
  {
    v5 = GetLastError();
    v6 = v5;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 41, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids, v5);
    if ( v6 )
      LogMsgNTStatus(v6, (wchar_t *)L"dumpauthzutl", 0x5FFu);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v6);
    throw (bad_win32_error *)pExceptionObject;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 42, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids);
  ShowOGandSID(pOwner);
  if ( !GetSecurityDescriptorGroup(pSecurityDescriptor, &pOwner, &bOwnerDefaulted) )
  {
    v7 = GetLastError();
    v8 = v7;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 43, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids, v7);
    if ( v8 )
      LogMsgNTStatus(v8, (wchar_t *)L"dumpauthzutl", 0x600u);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v8);
    throw (bad_win32_error *)pExceptionObject;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 44, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids);
  ShowOGandSID(pOwner);
  bDaclPresent = 0;
  pDacl = 0;
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bOwnerDefaulted) )
  {
    v9 = GetLastError();
    v10 = v9;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 45, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids, v9);
    if ( v10 )
      LogMsgNTStatus(v10, (wchar_t *)L"dumpauthzutl", 0x601u);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v10);
    throw (bad_win32_error *)pExceptionObject;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 46, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids);
  PrintAcl(bDaclPresent, bOwnerDefaulted, pDacl);
  if ( !GetSecurityDescriptorSacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bOwnerDefaulted) )
  {
    v11 = GetLastError();
    v12 = v11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 47, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids, v11);
    if ( v12 )
      LogMsgNTStatus(v12, (wchar_t *)L"dumpauthzutl", 0x602u);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v12);
    throw (bad_win32_error *)pExceptionObject;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 48, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids);
  PrintAcl(bDaclPresent, bOwnerDefaulted, pDacl);
}

```

## disassembly

```asm
0x18007d434  push    rbp
0x18007d436  push    rbx
0x18007d437  push    rsi
0x18007d438  push    rdi
0x18007d439  mov     rbp, rsp
0x18007d43c  sub     rsp, 68h
0x18007d440  mov     rsi, rcx
0x18007d443  test    rcx, rcx
0x18007d446  jz      loc_18007D858
0x18007d44c  call    cs:__imp_IsValidSecurityDescriptor
0x18007d452  test    eax, eax
0x18007d454  jz      loc_18007D858
0x18007d45a  xor     eax, eax
0x18007d45c  mov     [rbp+dwRevision], 0
0x18007d463  lea     r8, [rbp+dwRevision]; lpdwRevision
0x18007d467  mov     [rbp+pControl], ax
0x18007d46b  lea     rdx, [rbp+pControl]; pControl
0x18007d46f  mov     rcx, rsi; pSecurityDescriptor
0x18007d472  call    cs:__imp_GetSecurityDescriptorControl
0x18007d478  test    eax, eax
0x18007d47a  jnz     short loc_18007D4EF
0x18007d47c  call    cs:__imp_GetLastError
0x18007d482  mov     esi, eax
0x18007d484  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d48b  lea     rbx, WPP_GLOBAL_Control
0x18007d492  cmp     rcx, rbx
0x18007d495  jz      short loc_18007D4BB
0x18007d497  test    byte ptr [rcx+10Ch], 1
0x18007d49e  jz      short loc_18007D4BB
0x18007d4a0  mov     rcx, [rcx+100h]
0x18007d4a7  lea     r8, WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids
0x18007d4ae  mov     edx, 26h ; '&'
0x18007d4b3  mov     r9d, eax
0x18007d4b6  call    WPP_SF_d
0x18007d4bb  test    esi, esi
0x18007d4bd  jz      short loc_18007D4D3
0x18007d4bf  mov     r8d, 5FEh; unsigned __int16
0x18007d4c5  lea     rdx, aDumpauthzutl; "dumpauthzutl"
0x18007d4cc  mov     ecx, esi; int
0x18007d4ce  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18007d4d3  mov     edx, esi; unsigned int
0x18007d4d5  lea     rcx, [rbp+pExceptionObject]; this
0x18007d4d9  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18007d4de  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18007d4e5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18007d4e9  call    _CxxThrowException_0
0x18007d4ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d4f6  lea     rbx, WPP_GLOBAL_Control
0x18007d4fd  lea     rdi, WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids
0x18007d504  cmp     rcx, rbx
0x18007d507  jz      short loc_18007D55B
0x18007d509  test    byte ptr [rcx+10Ch], 4
0x18007d510  jz      short loc_18007D52D
0x18007d512  mov     rcx, [rcx+100h]
0x18007d519  mov     edx, 27h ; '''
0x18007d51e  mov     r8, rdi
0x18007d521  call    WPP_SF_
0x18007d526  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d52d  cmp     rcx, rbx
0x18007d530  jz      short loc_18007D55B
0x18007d532  test    byte ptr [rcx+10Ch], 4
0x18007d539  jz      short loc_18007D55B
0x18007d53b  mov     eax, [rbp+dwRevision]
0x18007d53e  mov     edx, 28h ; '('
0x18007d543  movzx   r9d, [rbp+pControl]
0x18007d548  mov     r8, rdi
0x18007d54b  mov     rcx, [rcx+100h]
0x18007d552  mov     [rsp+68h+var_48], eax
0x18007d556  call    WPP_SF_Dd
0x18007d55b  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x18007d55f  mov     [rbp+pOwner], 0
0x18007d567  lea     rdx, [rbp+pOwner]; pOwner
0x18007d56b  mov     [rbp+bOwnerDefaulted], 0
0x18007d572  mov     rcx, rsi; pSecurityDescriptor
0x18007d575  call    cs:__imp_GetSecurityDescriptorOwner
0x18007d57b  test    eax, eax
0x18007d57d  jnz     short loc_18007D5E7
0x18007d57f  call    cs:__imp_GetLastError
0x18007d585  mov     esi, eax
0x18007d587  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d58e  cmp     rcx, rbx
0x18007d591  jz      short loc_18007D5B3
0x18007d593  test    byte ptr [rcx+10Ch], 1
0x18007d59a  jz      short loc_18007D5B3
0x18007d59c  mov     rcx, [rcx+100h]
0x18007d5a3  mov     edx, 29h ; ')'
0x18007d5a8  mov     r9d, eax
0x18007d5ab  mov     r8, rdi
0x18007d5ae  call    WPP_SF_d
0x18007d5b3  test    esi, esi
0x18007d5b5  jz      short loc_18007D5CB
0x18007d5b7  mov     r8d, 5FFh; unsigned __int16
0x18007d5bd  lea     rdx, aDumpauthzutl; "dumpauthzutl"
0x18007d5c4  mov     ecx, esi; int
0x18007d5c6  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18007d5cb  mov     edx, esi; unsigned int
0x18007d5cd  lea     rcx, [rbp+pExceptionObject]; this
0x18007d5d1  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18007d5d6  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18007d5dd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18007d5e1  call    _CxxThrowException_0
0x18007d5e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d5ee  cmp     rcx, rbx
0x18007d5f1  jz      short loc_18007D610
0x18007d5f3  test    byte ptr [rcx+10Ch], 4
0x18007d5fa  jz      short loc_18007D610
0x18007d5fc  mov     rcx, [rcx+100h]
0x18007d603  mov     edx, 2Ah ; '*'
0x18007d608  mov     r8, rdi
0x18007d60b  call    WPP_SF_
0x18007d610  mov     edx, [rbp+bOwnerDefaulted]
0x18007d613  mov     rcx, [rbp+pOwner]; Sid
0x18007d617  call    ShowOGandSID
0x18007d61c  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x18007d620  mov     rcx, rsi; pSecurityDescriptor
0x18007d623  lea     rdx, [rbp+pOwner]; pGroup
0x18007d627  call    cs:__imp_GetSecurityDescriptorGroup
0x18007d62d  test    eax, eax
0x18007d62f  jnz     short loc_18007D699
0x18007d631  call    cs:__imp_GetLastError
0x18007d637  mov     esi, eax
0x18007d639  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d640  cmp     rcx, rbx
0x18007d643  jz      short loc_18007D665
0x18007d645  test    byte ptr [rcx+10Ch], 1
0x18007d64c  jz      short loc_18007D665
0x18007d64e  mov     rcx, [rcx+100h]
0x18007d655  mov     edx, 2Bh ; '+'
0x18007d65a  mov     r9d, eax
0x18007d65d  mov     r8, rdi
0x18007d660  call    WPP_SF_d
0x18007d665  test    esi, esi
0x18007d667  jz      short loc_18007D67D
0x18007d669  mov     r8d, 600h; unsigned __int16
0x18007d66f  lea     rdx, aDumpauthzutl; "dumpauthzutl"
0x18007d676  mov     ecx, esi; int
0x18007d678  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18007d67d  mov     edx, esi; unsigned int
0x18007d67f  lea     rcx, [rbp+pExceptionObject]; this
0x18007d683  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18007d688  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18007d68f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18007d693  call    _CxxThrowException_0
0x18007d699  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d6a0  cmp     rcx, rbx
0x18007d6a3  jz      short loc_18007D6C2
0x18007d6a5  test    byte ptr [rcx+10Ch], 4
0x18007d6ac  jz      short loc_18007D6C2
0x18007d6ae  mov     rcx, [rcx+100h]
0x18007d6b5  mov     edx, 2Ch ; ','
0x18007d6ba  mov     r8, rdi
0x18007d6bd  call    WPP_SF_
0x18007d6c2  mov     edx, [rbp+bOwnerDefaulted]
0x18007d6c5  mov     rcx, [rbp+pOwner]; Sid
0x18007d6c9  call    ShowOGandSID
0x18007d6ce  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x18007d6d2  mov     [rbp+bDaclPresent], 0
0x18007d6d9  lea     r8, [rbp+pDacl]; pDacl
0x18007d6dd  mov     [rbp+pDacl], 0
0x18007d6e5  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18007d6e9  mov     rcx, rsi; pSecurityDescriptor
0x18007d6ec  call    cs:__imp_GetSecurityDescriptorDacl
0x18007d6f2  test    eax, eax
0x18007d6f4  jnz     short loc_18007D75E
0x18007d6f6  call    cs:__imp_GetLastError
0x18007d6fc  mov     esi, eax
0x18007d6fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d705  cmp     rcx, rbx
0x18007d708  jz      short loc_18007D72A
0x18007d70a  test    byte ptr [rcx+10Ch], 1
0x18007d711  jz      short loc_18007D72A
0x18007d713  mov     rcx, [rcx+100h]
0x18007d71a  mov     edx, 2Dh ; '-'
0x18007d71f  mov     r9d, eax
0x18007d722  mov     r8, rdi
0x18007d725  call    WPP_SF_d
0x18007d72a  test    esi, esi
0x18007d72c  jz      short loc_18007D742
0x18007d72e  mov     r8d, 601h; unsigned __int16
0x18007d734  lea     rdx, aDumpauthzutl; "dumpauthzutl"
0x18007d73b  mov     ecx, esi; int
0x18007d73d  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18007d742  mov     edx, esi; unsigned int
0x18007d744  lea     rcx, [rbp+pExceptionObject]; this
0x18007d748  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18007d74d  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18007d754  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18007d758  call    _CxxThrowException_0
0x18007d75e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d765  cmp     rcx, rbx
0x18007d768  jz      short loc_18007D787
0x18007d76a  test    byte ptr [rcx+10Ch], 4
0x18007d771  jz      short loc_18007D787
0x18007d773  mov     rcx, [rcx+100h]
0x18007d77a  mov     edx, 2Eh ; '.'
0x18007d77f  mov     r8, rdi
0x18007d782  call    WPP_SF_
0x18007d787  mov     r8, [rbp+pDacl]; struct _ACL *
0x18007d78b  mov     edx, [rbp+bOwnerDefaulted]; int
0x18007d78e  mov     ecx, [rbp+bDaclPresent]; int
0x18007d791  call    ?PrintAcl@@YAXHHPEAU_ACL@@@Z; PrintAcl(int,int,_ACL *)
0x18007d796  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x18007d79a  mov     rcx, rsi; pSecurityDescriptor
0x18007d79d  lea     r8, [rbp+pDacl]; pSacl
0x18007d7a1  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x18007d7a5  call    cs:__imp_GetSecurityDescriptorSacl
0x18007d7ab  test    eax, eax
0x18007d7ad  jnz     short loc_18007D817
0x18007d7af  call    cs:__imp_GetLastError
0x18007d7b5  mov     esi, eax
0x18007d7b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d7be  cmp     rcx, rbx
0x18007d7c1  jz      short loc_18007D7E3
0x18007d7c3  test    byte ptr [rcx+10Ch], 1
0x18007d7ca  jz      short loc_18007D7E3
0x18007d7cc  mov     rcx, [rcx+100h]
0x18007d7d3  mov     edx, 2Fh ; '/'
0x18007d7d8  mov     r9d, eax
0x18007d7db  mov     r8, rdi
0x18007d7de  call    WPP_SF_d
0x18007d7e3  test    esi, esi
0x18007d7e5  jz      short loc_18007D7FB
0x18007d7e7  mov     r8d, 602h; unsigned __int16
0x18007d7ed  lea     rdx, aDumpauthzutl; "dumpauthzutl"
0x18007d7f4  mov     ecx, esi; int
0x18007d7f6  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18007d7fb  mov     edx, esi; unsigned int
0x18007d7fd  lea     rcx, [rbp+pExceptionObject]; this
0x18007d801  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18007d806  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18007d80d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18007d811  call    _CxxThrowException_0
0x18007d817  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d81e  cmp     rcx, rbx
0x18007d821  jz      short loc_18007D840
0x18007d823  test    byte ptr [rcx+10Ch], 4
0x18007d82a  jz      short loc_18007D840
0x18007d82c  mov     rcx, [rcx+100h]
0x18007d833  mov     edx, 30h ; '0'
0x18007d838  mov     r8, rdi
0x18007d83b  call    WPP_SF_
0x18007d840  mov     r8, [rbp+pDacl]; struct _ACL *
0x18007d844  mov     edx, [rbp+bOwnerDefaulted]; int
0x18007d847  mov     ecx, [rbp+bDaclPresent]; int
0x18007d84a  call    ?PrintAcl@@YAXHHPEAU_ACL@@@Z; PrintAcl(int,int,_ACL *)
0x18007d84f  add     rsp, 68h
0x18007d853  pop     rdi
0x18007d854  pop     rsi
0x18007d855  pop     rbx
0x18007d856  pop     rbp
0x18007d857  retn
0x18007d858  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d85f  lea     rbx, WPP_GLOBAL_Control
0x18007d866  cmp     rcx, rbx
0x18007d869  jz      short loc_18007D88C
0x18007d86b  test    byte ptr [rcx+10Ch], 1
0x18007d872  jz      short loc_18007D88C
0x18007d874  mov     rcx, [rcx+100h]
0x18007d87b  lea     r8, WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids
0x18007d882  mov     edx, 25h ; '%'
0x18007d887  call    WPP_SF_
0x18007d88c  mov     edx, 5FDh; unsigned __int16
0x18007d891  lea     rcx, aDumpauthzutl; "dumpauthzutl"
0x18007d898  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x18007d89d  mov     edx, 53Ah; unsigned int
0x18007d8a2  lea     rcx, [rbp+pExceptionObject]; this
0x18007d8a6  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18007d8ab  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18007d8b2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18007d8b6  call    _CxxThrowException_0
```
