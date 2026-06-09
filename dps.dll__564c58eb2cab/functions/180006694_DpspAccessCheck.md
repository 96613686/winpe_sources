# DpspAccessCheck

- ea: `0x180006694`
- end: `0x1800067b2`
- name: `DpspAccessCheck`
- size: `286`
- prototype: `__int64 __fastcall(HANDLE ClientToken, PSECURITY_DESCRIPTOR pSecurityDescriptor, DWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002510`
- `0x180002a08`

## callees

- `0x180006694`
- `0x180009090`
- `0x180009fb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006740`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006740`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006784`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800066f9`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800066f9`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180006731`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180006731`

## string_xrefs

- `0x180006769`: `DpspAccessCheck`

## pseudocode

```c
__int64 __fastcall DpspAccessCheck(HANDLE ClientToken, PSECURITY_DESCRIPTOR pSecurityDescriptor, DWORD a3)
{
  signed int LastError; // eax
  signed int v6; // ebx
  signed int v7; // eax
  DWORD AccessMask[4]; // [rsp+40h] [rbp-9h] BYREF
  WINBOOL AccessStatus; // [rsp+50h] [rbp+7h] BYREF
  DWORD GrantedAccess; // [rsp+54h] [rbp+Bh] BYREF
  DWORD PrivilegeSetLength; // [rsp+58h] [rbp+Fh] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+60h] [rbp+17h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+70h] [rbp+27h] BYREF

  AccessMask[0] = a3;
  GrantedAccess = 0;
  AccessStatus = 0;
  PrivilegeSetLength = 20;
  GenericMapping.GenericRead = 1179785;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  GenericMapping.GenericWrite = 1179926;
  GenericMapping.GenericExecute = 1179808;
  GenericMapping.GenericAll = 2032127;
  MapGenericMask(AccessMask, &GenericMapping);
  if ( AccessCheck(
         pSecurityDescriptor,
         ClientToken,
         AccessMask[0],
         &GenericMapping,
         &PrivilegeSet,
         &PrivilegeSetLength,
         &GrantedAccess,
         &AccessStatus) )
  {
    goto LABEL_6;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_6:
    if ( AccessStatus )
    {
      return 0;
    }
    else
    {
      v7 = GetLastError();
      v6 = v7;
      if ( v7 > 0 )
        return (unsigned __int16)v7 | 0x80070000;
    }
  }
  else
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
      (int)L"DpspAccessCheck",
      1683,
      (int)L"Error = %d",
      v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006694  push    rbp
0x180006696  push    rbx
0x180006697  push    rdi
0x180006698  lea     rbp, [rsp-47h]
0x18000669d  sub     rsp, 90h
0x1800066a4  mov     rax, cs:__security_cookie
0x1800066ab  xor     rax, rsp
0x1800066ae  mov     [rbp+57h+var_18], rax
0x1800066b2  xor     eax, eax
0x1800066b4  mov     [rbp+57h+AccessMask], r8d
0x1800066b8  mov     rdi, rdx
0x1800066bb  mov     [rbp+57h+var_30.Privilege.Attributes], eax
0x1800066be  mov     rbx, rcx
0x1800066c1  mov     [rbp+57h+var_4C], eax
0x1800066c4  xorps   xmm0, xmm0
0x1800066c7  mov     [rbp+57h+var_50], eax
0x1800066ca  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x1800066ce  mov     [rbp+57h+var_48], 14h
0x1800066d5  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x1800066d9  mov     [rbp+57h+GenericMapping.GenericRead], 120089h
0x1800066e0  movups  xmmword ptr [rbp+57h+var_30.PrivilegeCount], xmm0
0x1800066e4  mov     [rbp+57h+GenericMapping.GenericWrite], 120116h
0x1800066eb  mov     [rbp+57h+GenericMapping.GenericExecute], 1200A0h
0x1800066f2  mov     [rbp+57h+GenericMapping.GenericAll], 1F01FFh
0x1800066f9  call    cs:__imp_MapGenericMask
0x1800066ff  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x180006703  lea     rax, [rbp+57h+var_50]
0x180006707  mov     [rsp+0A0h+AccessStatus], rax; AccessStatus
0x18000670c  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x180006710  lea     rax, [rbp+57h+var_4C]
0x180006714  mov     rdx, rbx; ClientToken
0x180006717  mov     [rsp+0A0h+GrantedAccess], rax; GrantedAccess
0x18000671c  mov     rcx, rdi; pSecurityDescriptor
0x18000671f  lea     rax, [rbp+57h+var_48]
0x180006723  mov     [rsp+0A0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180006728  lea     rax, [rbp+57h+var_30]
0x18000672c  mov     [rsp+0A0h+PrivilegeSet], rax; PrivilegeSet
0x180006731  call    cs:__imp_AccessCheck
0x180006737  mov     edi, 80070000h
0x18000673c  test    eax, eax
0x18000673e  jnz     short loc_18000677E
0x180006740  call    cs:__imp_GetLastError
0x180006746  mov     ebx, eax
0x180006748  test    eax, eax
0x18000674a  jle     short loc_180006751
0x18000674c  movzx   ebx, ax
0x18000674f  or      ebx, edi
0x180006751  test    ebx, ebx
0x180006753  jns     short loc_18000677E
0x180006755  movzx   eax, bx
0x180006758  lea     r9, aErrorD; "Error = %d"
0x18000675f  mov     r8d, 693h; int
0x180006765  mov     dword ptr [rsp+0A0h+PrivilegeSet], eax; Args
0x180006769  lea     rdx, aDpspaccesschec; "DpspAccessCheck"
0x180006770  lea     rcx, aClientcoreBase_11; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180006777  call    WdipTraceError
0x18000677c  jmp     short loc_180006799
0x18000677e  cmp     [rbp+57h+var_50], 0
0x180006782  jnz     short loc_180006797
0x180006784  call    cs:__imp_GetLastError
0x18000678a  mov     ebx, eax
0x18000678c  test    eax, eax
0x18000678e  jle     short loc_180006799
0x180006790  movzx   ebx, ax
0x180006793  or      ebx, edi
0x180006795  jmp     short loc_180006799
0x180006797  xor     ebx, ebx
0x180006799  mov     eax, ebx
0x18000679b  mov     rcx, [rbp+57h+var_18]
0x18000679f  xor     rcx, rsp; StackCookie
0x1800067a2  call    __security_check_cookie
0x1800067a7  add     rsp, 90h
0x1800067ae  pop     rdi
0x1800067af  pop     rbx
0x1800067b0  pop     rbp
0x1800067b1  retn
```
