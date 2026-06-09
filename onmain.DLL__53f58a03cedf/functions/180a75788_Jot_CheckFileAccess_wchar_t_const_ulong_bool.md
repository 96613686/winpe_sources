# Jot::CheckFileAccess(wchar_t const *,ulong,bool *)

- ea: `0x180a75788`
- end: `0x180a75a77`
- name: `?CheckFileAccess@Jot@@YAJPEB_WKPEA_N@Z`
- size: `751`
- prototype: `__int64 __fastcall(Jot *__hidden this, const wchar_t *, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180a733f0`

## callees

- `0x18002e484`
- `0x18004e790`
- `0x1802e5170`
- `0x180a75788`
- `0x180a75bfc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180a75878`
- `KERNEL32!CloseHandle` at `0x180a75901`
- `KERNEL32!CloseHandle` at `0x180a75a3a`
- `KERNEL32!CloseHandle` at `0x180a75a48`
- `KERNEL32!CloseHandle` at `0x180a75878`
- `KERNEL32!CloseHandle` at `0x180a75901`
- `KERNEL32!CloseHandle` at `0x180a75a3a`
- `KERNEL32!CloseHandle` at `0x180a75a48`
- `KERNEL32!GetLastError` at `0x180a757cb`
- `KERNEL32!GetLastError` at `0x180a75849`
- `KERNEL32!GetLastError` at `0x180a758d6`
- `KERNEL32!GetLastError` at `0x180a75935`
- `KERNEL32!GetLastError` at `0x180a759d9`
- `KERNEL32!GetLastError` at `0x180a757cb`
- `KERNEL32!GetLastError` at `0x180a75849`
- `KERNEL32!GetLastError` at `0x180a758d6`
- `KERNEL32!GetLastError` at `0x180a75935`
- `KERNEL32!GetLastError` at `0x180a759d9`
- `KERNEL32!GetCurrentThread` at `0x180a75883`
- `KERNEL32!GetCurrentThread` at `0x180a75883`
- `ADVAPI32!GetFileSecurityW` at `0x180a7583f`
- `ADVAPI32!GetFileSecurityW` at `0x180a7583f`
- `ADVAPI32!OpenThreadToken` at `0x180a758bb`
- `ADVAPI32!OpenThreadToken` at `0x180a7592b`
- `ADVAPI32!OpenThreadToken` at `0x180a758bb`
- `ADVAPI32!OpenThreadToken` at `0x180a7592b`
- `ADVAPI32!ImpersonateSelf` at `0x180a758cc`
- `ADVAPI32!ImpersonateSelf` at `0x180a758cc`
- `ADVAPI32!RevertToSelf` at `0x180a7594a`
- `ADVAPI32!RevertToSelf` at `0x180a759f3`
- `ADVAPI32!RevertToSelf` at `0x180a75a1a`
- `ADVAPI32!RevertToSelf` at `0x180a7594a`
- `ADVAPI32!RevertToSelf` at `0x180a759f3`
- `ADVAPI32!RevertToSelf` at `0x180a75a1a`
- `ADVAPI32!MapGenericMask` at `0x180a75986`
- `ADVAPI32!MapGenericMask` at `0x180a75986`
- `ADVAPI32!AccessCheck` at `0x180a759cf`
- `ADVAPI32!AccessCheck` at `0x180a759cf`

## pseudocode

```c
__int64 __fastcall Jot::CheckFileAccess(Jot *this, const wchar_t *a2, _BYTE *a3, bool *a4)
{
  signed int LastError; // eax
  unsigned int v7; // edi
  void *v9; // rbx
  char v10; // di
  signed int v11; // eax
  HANDLE v12; // rcx
  HANDLE CurrentThread; // rax
  signed int v14; // eax
  HANDLE v15; // rcx
  bool v16; // cc
  signed int v17; // eax
  signed int v18; // esi
  signed int v19; // eax
  signed int v20; // esi
  char *v21; // rcx
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  DWORD AccessMask; // [rsp+48h] [rbp-B8h] BYREF
  BOOL AccessStatus; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD nLengthNeeded; // [rsp+50h] [rbp-B0h] BYREF
  DWORD GrantedAccess; // [rsp+54h] [rbp-ACh] BYREF
  DWORD PrivilegeSetLength; // [rsp+58h] [rbp-A8h] BYREF
  void *v28; // [rsp+60h] [rbp-A0h] BYREF
  GENERIC_MAPPING GenericMapping; // [rsp+68h] [rbp-98h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+78h] [rbp-88h] BYREF
  _BYTE pSecurityDescriptor[65584]; // [rsp+90h] [rbp-70h] BYREF

  if ( !Jot::DoesSupportACLs(this, a2) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = -2147467259;
    if ( LastError < 0 )
      return (unsigned int)LastError;
    return v7;
  }
  PrivilegeSetLength = 20;
  v9 = 0;
  PrivilegeSet.Privilege[0].Attributes = 0;
  GrantedAccess = 0;
  *a3 = 0;
  v28 = 0;
  hObject = 0;
  nLengthNeeded = 0;
  AccessMask = 0x10000;
  *(_OWORD *)&PrivilegeSet.PrivilegeCount = 0;
  v10 = 0;
  if ( !GetFileSecurityW((LPCWSTR)this, 7u, pSecurityDescriptor, 0x10028u, &nLengthNeeded)
    || (CurrentThread = GetCurrentThread()) != 0
    && (Ofc::CHANDLEOwner::Assign((Ofc::CHANDLEOwner *)&v28, CurrentThread), v9 = v28, v28 == (void *)-1LL) )
  {
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    v12 = hObject;
    v7 = -2147467259;
    if ( v11 < 0 )
      v7 = v11;
    if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return v7;
LABEL_13:
    CloseHandle(v12);
    return v7;
  }
  if ( !OpenThreadToken(v9, 0xF01FFu, 1, &hObject) )
  {
    if ( !ImpersonateSelf(SecurityImpersonation) )
    {
      v14 = GetLastError();
      if ( v14 > 0 )
        v14 = (unsigned __int16)v14 | 0x80070000;
      v7 = -2147467259;
      if ( v14 < 0 )
        v7 = v14;
LABEL_22:
      v15 = hObject;
      v16 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_23:
      if ( v16 )
        CloseHandle(v15);
      if ( !v9 )
        return v7;
      v12 = v9;
      goto LABEL_13;
    }
    v10 = 1;
    if ( !OpenThreadToken(v9, 0xF01FFu, 1, &hObject) )
    {
      v17 = GetLastError();
      v18 = v17;
      if ( v17 > 0 )
        v18 = (unsigned __int16)v17 | 0x80070000;
      RevertToSelf();
      v7 = -2147467259;
      if ( v18 < 0 )
        v7 = v18;
      goto LABEL_22;
    }
  }
  GenericMapping.GenericRead = 1179785;
  GenericMapping.GenericWrite = 1179926;
  GenericMapping.GenericExecute = 1179808;
  GenericMapping.GenericAll = 2032127;
  MapGenericMask(&AccessMask, &GenericMapping);
  AccessStatus = 0;
  if ( !AccessCheck(
          pSecurityDescriptor,
          hObject,
          AccessMask,
          &GenericMapping,
          &PrivilegeSet,
          &PrivilegeSetLength,
          &GrantedAccess,
          &AccessStatus) )
  {
    v19 = GetLastError();
    v20 = v19;
    if ( v19 > 0 )
      v20 = (unsigned __int16)v19 | 0x80070000;
    if ( v10 )
      RevertToSelf();
    v15 = hObject;
    v7 = -2147467259;
    if ( v20 < 0 )
      v7 = v20;
    v16 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
    goto LABEL_23;
  }
  if ( v10 )
    RevertToSelf();
  v21 = (char *)hObject;
  *a3 = AccessStatus;
  if ( (unsigned __int64)(v21 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v21);
  if ( v9 )
    CloseHandle(v9);
  return 0;
}

```

## disassembly

```asm
0x180a75788  mov     [rsp-8+arg_8], rbx
0x180a7578d  mov     [rsp-8+arg_18], rsi
0x180a75792  push    rbp
0x180a75793  push    rdi
0x180a75794  push    r14
0x180a75796  lea     rbp, [rsp-0FFD0h]
0x180a7579e  mov     eax, 100D0h
0x180a757a3  call    _alloca_probe
0x180a757a8  sub     rsp, rax
0x180a757ab  mov     rax, cs:__security_cookie
0x180a757b2  xor     rax, rsp
0x180a757b5  mov     [rbp+0FFE0h+var_20], rax
0x180a757bc  mov     r14, r8
0x180a757bf  mov     rsi, rcx
0x180a757c2  call    ?DoesSupportACLs@Jot@@YA_NPEB_W@Z; Jot::DoesSupportACLs(wchar_t const *)
0x180a757c7  test    al, al
0x180a757c9  jnz     short loc_180A757EE
0x180a757cb  call    cs:__imp_GetLastError
0x180a757d1  test    eax, eax
0x180a757d3  jle     short loc_180A757DD
0x180a757d5  movzx   eax, ax
0x180a757d8  or      eax, 80070000h
0x180a757dd  test    eax, eax
0x180a757df  mov     edi, 80004005h
0x180a757e4  cmovs   edi, eax
0x180a757e7  mov     eax, edi
0x180a757e9  jmp     loc_180A75A50
0x180a757ee  xor     eax, eax
0x180a757f0  mov     [rsp+100E0h+var_10088], 14h
0x180a757f8  xor     ebx, ebx
0x180a757fa  mov     [rbp+0FFE0h+PrivilegeSet.Privilege.Attributes], eax
0x180a757fd  mov     [rsp+100E0h+var_1008C], eax
0x180a75801  lea     r8, [rbp+0FFE0h+pSecurityDescriptor]; pSecurityDescriptor
0x180a75805  mov     [r14], al
0x180a75808  xorps   xmm0, xmm0
0x180a7580b  lea     rax, [rsp+100E0h+nLengthNeeded]
0x180a75810  mov     [rsp+100E0h+var_10080], rbx
0x180a75815  lea     edx, [rbx+7]; RequestedInformation
0x180a75818  mov     [rsp+100E0h+hObject], rbx
0x180a7581d  mov     r9d, 10028h; nLength
0x180a75823  mov     [rsp+100E0h+nLengthNeeded], ebx
0x180a75827  mov     rcx, rsi; lpFileName
0x180a7582a  mov     [rsp+100E0h+AccessMask], 10000h
0x180a75832  movups  xmmword ptr [rsp+100E0h+PrivilegeSet.PrivilegeCount], xmm0
0x180a75837  xor     dil, dil
0x180a7583a  mov     [rsp+100E0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180a7583f  call    cs:__imp_GetFileSecurityW
0x180a75845  test    eax, eax
0x180a75847  jnz     short loc_180A75883
0x180a75849  call    cs:__imp_GetLastError
0x180a7584f  test    eax, eax
0x180a75851  jle     short loc_180A7585B
0x180a75853  movzx   eax, ax
0x180a75856  or      eax, 80070000h
0x180a7585b  mov     rcx, [rsp+100E0h+hObject]; hObject
0x180a75860  test    eax, eax
0x180a75862  mov     edi, 80004005h
0x180a75867  cmovs   edi, eax
0x180a7586a  lea     rax, [rcx-1]
0x180a7586e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180a75872  ja      loc_180A757E7
0x180a75878  call    cs:__imp_CloseHandle
0x180a7587e  jmp     loc_180A757E7
0x180a75883  call    cs:__imp_GetCurrentThread
0x180a75889  test    rax, rax
0x180a7588c  jz      short loc_180A758A6
0x180a7588e  mov     rdx, rax; void *
0x180a75891  lea     rcx, [rsp+100E0h+var_10080]; this
0x180a75896  call    ?Assign@CHANDLEOwner@Ofc@@AEAAXPEAX@Z; Ofc::CHANDLEOwner::Assign(void *)
0x180a7589b  mov     rbx, [rsp+100E0h+var_10080]
0x180a758a0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180a758a4  jz      short loc_180A75849
0x180a758a6  mov     esi, 1
0x180a758ab  lea     r9, [rsp+100E0h+hObject]; TokenHandle
0x180a758b0  mov     r8d, esi; OpenAsSelf
0x180a758b3  mov     edx, 0F01FFh; DesiredAccess
0x180a758b8  mov     rcx, rbx; ThreadHandle
0x180a758bb  call    cs:__imp_OpenThreadToken
0x180a758c1  test    eax, eax
0x180a758c3  jnz     loc_180A7595C
0x180a758c9  lea     ecx, [rsi+1]; ImpersonationLevel
0x180a758cc  call    cs:__imp_ImpersonateSelf
0x180a758d2  test    eax, eax
0x180a758d4  jnz     short loc_180A75918
0x180a758d6  call    cs:__imp_GetLastError
0x180a758dc  test    eax, eax
0x180a758de  jle     short loc_180A758E8
0x180a758e0  movzx   eax, ax
0x180a758e3  or      eax, 80070000h
0x180a758e8  test    eax, eax
0x180a758ea  mov     edi, 80004005h
0x180a758ef  cmovs   edi, eax
0x180a758f2  mov     rcx, [rsp+100E0h+hObject]; hObject
0x180a758f7  lea     rax, [rcx-1]
0x180a758fb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180a758ff  ja      short loc_180A75907
0x180a75901  call    cs:__imp_CloseHandle
0x180a75907  test    rbx, rbx
0x180a7590a  jz      loc_180A757E7
0x180a75910  mov     rcx, rbx
0x180a75913  jmp     loc_180A75878
0x180a75918  lea     r9, [rsp+100E0h+hObject]; TokenHandle
0x180a7591d  mov     r8d, esi; OpenAsSelf
0x180a75920  mov     edx, 0F01FFh; DesiredAccess
0x180a75925  mov     rcx, rbx; ThreadHandle
0x180a75928  mov     dil, sil
0x180a7592b  call    cs:__imp_OpenThreadToken
0x180a75931  test    eax, eax
0x180a75933  jnz     short loc_180A7595C
0x180a75935  call    cs:__imp_GetLastError
0x180a7593b  mov     esi, eax
0x180a7593d  test    eax, eax
0x180a7593f  jle     short loc_180A7594A
0x180a75941  movzx   esi, ax
0x180a75944  or      esi, 80070000h
0x180a7594a  call    cs:__imp_RevertToSelf
0x180a75950  test    esi, esi
0x180a75952  mov     edi, 80004005h
0x180a75957  cmovs   edi, esi
0x180a7595a  jmp     short loc_180A758F2
0x180a7595c  lea     rdx, [rsp+100E0h+GenericMapping]; GenericMapping
0x180a75961  mov     [rsp+100E0h+GenericMapping.GenericRead], 120089h
0x180a75969  lea     rcx, [rsp+100E0h+AccessMask]; AccessMask
0x180a7596e  mov     [rsp+100E0h+GenericMapping.GenericWrite], 120116h
0x180a75976  mov     [rsp+100E0h+GenericMapping.GenericExecute], 1200A0h
0x180a7597e  mov     [rsp+100E0h+GenericMapping.GenericAll], 1F01FFh
0x180a75986  call    cs:__imp_MapGenericMask
0x180a7598c  mov     r8d, [rsp+100E0h+AccessMask]; DesiredAccess
0x180a75991  lea     rax, [rsp+100E0h+var_10094]
0x180a75996  mov     rdx, [rsp+100E0h+hObject]; ClientToken
0x180a7599b  lea     r9, [rsp+100E0h+GenericMapping]; GenericMapping
0x180a759a0  mov     [rsp+100E0h+AccessStatus], rax; AccessStatus
0x180a759a5  lea     rcx, [rbp+0FFE0h+pSecurityDescriptor]; pSecurityDescriptor
0x180a759a9  lea     rax, [rsp+100E0h+var_1008C]
0x180a759ae  mov     [rsp+100E0h+var_10094], 0
0x180a759b6  mov     [rsp+100E0h+GrantedAccess], rax; GrantedAccess
0x180a759bb  lea     rax, [rsp+100E0h+var_10088]
0x180a759c0  mov     [rsp+100E0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180a759c5  lea     rax, [rsp+100E0h+PrivilegeSet]
0x180a759ca  mov     [rsp+100E0h+lpnLengthNeeded], rax; PrivilegeSet
0x180a759cf  call    cs:__imp_AccessCheck
0x180a759d5  test    eax, eax
0x180a759d7  jnz     short loc_180A75A15
0x180a759d9  call    cs:__imp_GetLastError
0x180a759df  mov     esi, eax
0x180a759e1  test    eax, eax
0x180a759e3  jle     short loc_180A759EE
0x180a759e5  movzx   esi, ax
0x180a759e8  or      esi, 80070000h
0x180a759ee  test    dil, dil
0x180a759f1  jz      short loc_180A759F9
0x180a759f3  call    cs:__imp_RevertToSelf
0x180a759f9  mov     rcx, [rsp+100E0h+hObject]
0x180a759fe  test    esi, esi
0x180a75a00  mov     edi, 80004005h
0x180a75a05  cmovs   edi, esi
0x180a75a08  lea     rdx, [rcx-1]
0x180a75a0c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180a75a10  jmp     loc_180A758FF
0x180a75a15  test    dil, dil
0x180a75a18  jz      short loc_180A75A20
0x180a75a1a  call    cs:__imp_RevertToSelf
0x180a75a20  cmp     [rsp+100E0h+var_10094], 0
0x180a75a25  mov     rcx, [rsp+100E0h+hObject]; hObject
0x180a75a2a  setnz   al
0x180a75a2d  mov     [r14], al
0x180a75a30  lea     rax, [rcx-1]
0x180a75a34  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180a75a38  ja      short loc_180A75A40
0x180a75a3a  call    cs:__imp_CloseHandle
0x180a75a40  test    rbx, rbx
0x180a75a43  jz      short loc_180A75A4E
0x180a75a45  mov     rcx, rbx; hObject
0x180a75a48  call    cs:__imp_CloseHandle
0x180a75a4e  xor     eax, eax
0x180a75a50  mov     rcx, [rbp+0FFE0h+var_20]
0x180a75a57  xor     rcx, rsp; StackCookie
0x180a75a5a  call    __security_check_cookie
0x180a75a5f  lea     r11, [rsp+100E0h+var_10]
0x180a75a67  mov     rbx, [r11+28h]
0x180a75a6b  mov     rsi, [r11+38h]
0x180a75a6f  mov     rsp, r11
0x180a75a72  pop     r14
0x180a75a74  pop     rdi
0x180a75a75  pop     rbp
0x180a75a76  retn
```
