# GetDomainControllerNameByToken(void *,ushort *,ulong *,int,int)

- ea: `0x18002658c`
- end: `0x180026776`
- name: `?GetDomainControllerNameByToken@@YAHPEAXPEAGPEAKHH@Z`
- size: `490`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *, unsigned int *, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002629c`

## callees

- `0x180003080`
- `0x180007f10`
- `0x18001d810`
- `0x18002658c`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800265fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002667f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800265fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002667f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800266ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026762`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800266ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026762`
- `logoncli!DsGetDcNameW` at `0x1800266f8`
- `logoncli!DsGetDcNameW` at `0x1800266f8`
- `netutils!NetApiBufferFree` at `0x18002674a`
- `netutils!NetApiBufferFree` at `0x18002674a`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002666f`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002666f`

## string_xrefs

- `0x18002660d`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180026691`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`

## pseudocode

```c
__int64 __fastcall GetDomainControllerNameByToken(void *a1, unsigned __int16 *a2, unsigned int *a3, int a4, int a5)
{
  DWORD LastError; // eax
  DWORD v10; // eax
  unsigned int v11; // r15d
  DWORD DcNameW; // eax
  PDOMAIN_CONTROLLER_INFOW v13; // rdi
  LPWSTR DomainControllerName; // rdx
  __int64 v15; // rax
  unsigned int v16; // esi
  PSID Sid; // [rsp+30h] [rbp-D0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR ReferencedDomainName[16]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF

  cchName = 257;
  Sid = 0;
  cchReferencedDomainName = 16;
  peUse = 0;
  DomainControllerInfo = 0;
  if ( !a2 || !a3 )
    return 0;
  if ( !(unsigned int)GetTokenUserSid(a1, &Sid) )
  {
    LastError = GetLastError();
    DebugTraceError(
      LastError,
      "GetLastError()",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp",
      685);
    return 0;
  }
  if ( !LookupAccountSidLocalW(Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v10 = GetLastError();
    DebugTraceError(v10, "GetLastError()", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 702);
    LocalFree(Sid);
    return 0;
  }
  v11 = 0;
  DcNameW = DsGetDcNameW(
              0,
              ReferencedDomainName,
              0,
              0,
              (a4 != 0) | (a5 != 0 ? 1073811472 : -2147414000),
              &DomainControllerInfo);
  v13 = DomainControllerInfo;
  if ( !DcNameW )
  {
    DomainControllerName = DomainControllerInfo->DomainControllerName;
    if ( DomainControllerInfo->DomainControllerName )
    {
      v15 = -1;
      do
        ++v15;
      while ( DomainControllerName[v15] );
      v16 = v15 + 1;
      if ( *a3 >= (int)v15 + 1 )
      {
        memcpy_0(a2, DomainControllerName, 2LL * v16);
        v11 = 1;
      }
      *a3 = v16;
    }
  }
  if ( v13 )
    NetApiBufferFree(v13);
  if ( Sid )
    LocalFree(Sid);
  return v11;
}

```

## disassembly

```asm
0x18002658c  push    rbp
0x18002658e  push    rsi
0x18002658f  push    rdi
0x180026590  push    r12
0x180026592  push    r13
0x180026594  push    r14
0x180026596  push    r15
0x180026598  lea     rbp, [rsp-190h]
0x1800265a0  sub     rsp, 290h
0x1800265a7  mov     rax, cs:__security_cookie
0x1800265ae  xor     rax, rsp
0x1800265b1  mov     [rbp+1C0h+var_40], rax
0x1800265b8  xor     r13d, r13d
0x1800265bb  mov     [rsp+2C0h+cchName], 101h
0x1800265c3  mov     [rsp+2C0h+Sid], r13
0x1800265c8  mov     edi, r9d
0x1800265cb  mov     [rsp+2C0h+var_284], 10h
0x1800265d3  mov     r14, r8
0x1800265d6  mov     [rsp+2C0h+var_288], r13d
0x1800265db  mov     r12, rdx
0x1800265de  mov     [rsp+2C0h+DomainControllerInfo], r13
0x1800265e3  test    rdx, rdx
0x1800265e6  jz      short loc_180026622
0x1800265e8  test    r8, r8
0x1800265eb  jz      short loc_180026622
0x1800265ed  lea     rdx, [rsp+2C0h+Sid]
0x1800265f2  call    GetTokenUserSid
0x1800265f7  test    eax, eax
0x1800265f9  jnz     short loc_180026647
0x1800265fb  call    cs:__imp_GetLastError
0x180026602  nop     dword ptr [rax+rax+00h]
0x180026607  mov     r9d, 2ADh
0x18002660d  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180026614  mov     ecx, eax
0x180026616  lea     rdx, aGetlasterror; "GetLastError()"
0x18002661d  call    DebugTraceError
0x180026622  xor     eax, eax
0x180026624  mov     rcx, [rbp+1C0h+var_40]
0x18002662b  xor     rcx, rsp; StackCookie
0x18002662e  call    __security_check_cookie
0x180026633  add     rsp, 290h
0x18002663a  pop     r15
0x18002663c  pop     r14
0x18002663e  pop     r13
0x180026640  pop     r12
0x180026642  pop     rdi
0x180026643  pop     rsi
0x180026644  pop     rbp
0x180026645  retn
0x180026647  mov     rcx, [rsp+2C0h+Sid]; Sid
0x18002664c  lea     rax, [rsp+2C0h+var_288]
0x180026651  mov     [rsp+2C0h+peUse], rax; peUse
0x180026656  lea     r9, [rsp+2C0h+ReferencedDomainName]; ReferencedDomainName
0x18002665b  lea     rax, [rsp+2C0h+var_284]
0x180026660  lea     r8, [rsp+2C0h+cchName]; cchName
0x180026665  mov     [rsp+2C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18002666a  lea     rdx, [rsp+2C0h+Name]; Name
0x18002666f  call    cs:__imp_LookupAccountSidLocalW
0x180026676  nop     dword ptr [rax+rax+00h]
0x18002667b  test    eax, eax
0x18002667d  jnz     short loc_1800266BC
0x18002667f  call    cs:__imp_GetLastError
0x180026686  nop     dword ptr [rax+rax+00h]
0x18002668b  mov     r9d, 2BEh
0x180026691  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180026698  mov     ecx, eax
0x18002669a  lea     rdx, aGetlasterror; "GetLastError()"
0x1800266a1  call    DebugTraceError
0x1800266a6  mov     rcx, [rsp+2C0h+Sid]; hMem
0x1800266ab  call    cs:__imp_LocalFree
0x1800266b2  nop     dword ptr [rax+rax+00h]
0x1800266b7  jmp     loc_180026622
0x1800266bc  neg     [rbp+1C0h+arg_20]
0x1800266c2  lea     rdx, [rsp+2C0h+ReferencedDomainName]; DomainName
0x1800266c7  mov     eax, r13d
0x1800266ca  mov     r15d, r13d
0x1800266cd  sbb     ecx, ecx
0x1800266cf  and     ecx, 0C0000000h
0x1800266d5  add     ecx, 80011010h
0x1800266db  test    edi, edi
0x1800266dd  setnz   al
0x1800266e0  xor     r9d, r9d; SiteName
0x1800266e3  or      ecx, eax
0x1800266e5  xor     r8d, r8d; DomainGuid
0x1800266e8  lea     rax, [rsp+2C0h+DomainControllerInfo]
0x1800266ed  mov     [rsp+2C0h+peUse], rax; DomainControllerInfo
0x1800266f2  mov     dword ptr [rsp+2C0h+cchReferencedDomainName], ecx; Flags
0x1800266f6  xor     ecx, ecx; ComputerName
0x1800266f8  call    cs:__imp_DsGetDcNameW
0x1800266ff  nop     dword ptr [rax+rax+00h]
0x180026704  mov     rdi, [rsp+2C0h+DomainControllerInfo]
0x180026709  test    eax, eax
0x18002670b  jnz     short loc_180026742
0x18002670d  mov     rdx, [rdi]; Src
0x180026710  test    rdx, rdx
0x180026713  jz      short loc_180026742
0x180026715  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026719  inc     rax
0x18002671c  cmp     [rdx+rax*2], r13w
0x180026721  jnz     short loc_180026719
0x180026723  lea     esi, [rax+1]
0x180026726  cmp     [r14], esi
0x180026729  jb      short loc_18002673F
0x18002672b  mov     r8d, esi
0x18002672e  mov     rcx, r12; void *
0x180026731  add     r8, r8; Size
0x180026734  call    memcpy_0
0x180026739  mov     r15d, 1
0x18002673f  mov     [r14], esi
0x180026742  test    rdi, rdi
0x180026745  jz      short loc_180026756
0x180026747  mov     rcx, rdi; Buffer
0x18002674a  call    cs:__imp_NetApiBufferFree
0x180026751  nop     dword ptr [rax+rax+00h]
0x180026756  cmp     [rsp+2C0h+Sid], r13
0x18002675b  jz      short loc_18002676E
0x18002675d  mov     rcx, [rsp+2C0h+Sid]; hMem
0x180026762  call    cs:__imp_LocalFree
0x180026769  nop     dword ptr [rax+rax+00h]
0x18002676e  mov     eax, r15d
0x180026771  jmp     loc_180026624
```
