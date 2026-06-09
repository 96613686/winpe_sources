# ValidateAccountDomain

- ea: `0x18003318c`
- end: `0x1800334a6`
- name: `ValidateAccountDomain`
- size: `794`
- prototype: `__int64 __fastcall(wchar_t *Source, wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c010`

## callees

- `0x18003318c`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180033256`
- `msvcrt!wcscat_s` at `0x18003326d`
- `msvcrt!wcscat_s` at `0x180033256`
- `msvcrt!wcscat_s` at `0x18003326d`
- `msvcrt!wcscpy_s` at `0x18003323b`
- `msvcrt!wcscpy_s` at `0x18003323b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033296`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033296`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800332b5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800332b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033411`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800332c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033310`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800332c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033310`
- `RPCRT4!RpcImpersonateClient` at `0x18003327b`
- `RPCRT4!RpcImpersonateClient` at `0x18003327b`
- `RPCRT4!RpcRevertToSelf` at `0x18003346c`
- `RPCRT4!RpcRevertToSelf` at `0x18003346c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800333da`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800333da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033340`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033379`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033340`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033379`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033436`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003345b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033436`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003345b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003332b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033364`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033422`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033447`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003332b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033364`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033422`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033447`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180033300`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800333b9`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180033300`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800333b9`

## pseudocode

```c
__int64 __fastcall ValidateAccountDomain(wchar_t *Source, wchar_t *a2)
{
  int v4; // r15d
  WCHAR *ReferencedDomainName; // rsi
  void *v6; // rdi
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  DWORD v9; // ebx
  HANDLE ProcessHeap; // rax
  DWORD v11; // ebx
  HANDLE v12; // rax
  HANDLE v13; // rax
  HANDLE v14; // rax
  DWORD cbSid; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-BCh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v19; // [rsp+4Ch] [rbp-B4h] BYREF
  WINBOOL IsMember; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t Destination[280]; // [rsp+60h] [rbp-A0h] BYREF

  TokenHandle = (void *)-1LL;
  v4 = 0;
  memset_0(Destination, 0, 0x222u);
  cchReferencedDomainName = 0;
  ReferencedDomainName = 0;
  v19 = 0;
  v6 = 0;
  peUse = 0;
  IsMember = 0;
  cbSid = 0;
  if ( a2 && Source && *a2 && *Source )
  {
    wcscpy_s(Destination, 0x111u, a2);
    wcscat_s(Destination, 0x111u, L"\\");
    wcscat_s(Destination, 0x111u, Source);
    LastError = RpcImpersonateClient(0);
    if ( LastError )
      goto LABEL_18;
    v4 = 1;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      goto LABEL_7;
    if ( LookupAccountNameW(0, Destination, 0, &cbSid, 0, &cchReferencedDomainName, &peUse)
      || (LastError = GetLastError(), LastError == 122) )
    {
      v9 = cbSid;
      ProcessHeap = GetProcessHeap();
      v6 = HeapAlloc(ProcessHeap, 8u, v9);
      if ( !v6
        || (v19 = 2 * cchReferencedDomainName,
            v11 = 2 * cchReferencedDomainName,
            v12 = GetProcessHeap(),
            (ReferencedDomainName = (WCHAR *)HeapAlloc(v12, 8u, v11)) == 0)
        || !LookupAccountNameW(0, Destination, v6, &cbSid, ReferencedDomainName, &v19, &peUse)
        || !CheckTokenMembership(TokenHandle, v6, &IsMember) )
      {
LABEL_7:
        LastError = GetLastError();
        goto LABEL_18;
      }
      if ( IsMember )
        LastError = 0;
      else
        LastError = 5;
    }
  }
  else
  {
    LastError = 87;
  }
LABEL_18:
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  if ( v6 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v6);
  }
  if ( ReferencedDomainName )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, ReferencedDomainName);
  }
  if ( v4 )
    RpcRevertToSelf();
  return LastError;
}

```

## disassembly

```asm
0x18003318c  mov     [rsp-8+arg_10], rbx
0x180033191  mov     [rsp-8+arg_18], rsi
0x180033196  push    rbp
0x180033197  push    rdi
0x180033198  push    r12
0x18003319a  push    r14
0x18003319c  push    r15
0x18003319e  lea     rbp, [rsp-1A0h]
0x1800331a6  sub     rsp, 2A0h
0x1800331ad  mov     rax, cs:__security_cookie
0x1800331b4  xor     rax, rsp
0x1800331b7  mov     [rbp+1C0h+var_30], rax
0x1800331be  mov     r14, rdx
0x1800331c1  mov     [rsp+2C0h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800331ca  mov     rbx, rcx
0x1800331cd  xor     r12d, r12d
0x1800331d0  xor     edx, edx; Val
0x1800331d2  lea     rcx, [rsp+2C0h+Destination]; void *
0x1800331d7  mov     r8d, 222h; Size
0x1800331dd  mov     r15d, r12d
0x1800331e0  call    memset_0
0x1800331e5  mov     [rsp+2C0h+var_27C], r12d
0x1800331ea  mov     esi, r12d
0x1800331ed  mov     [rsp+2C0h+var_274], r12d
0x1800331f2  mov     edi, r12d
0x1800331f5  mov     [rsp+2C0h+var_278], r12d
0x1800331fa  mov     [rsp+2C0h+IsMember], r12d
0x1800331ff  mov     [rsp+2C0h+cbSid], r12d
0x180033204  test    r14, r14
0x180033207  jz      loc_180033401
0x18003320d  test    rbx, rbx
0x180033210  jz      loc_180033401
0x180033216  cmp     [r14], r12w
0x18003321a  jz      loc_180033401
0x180033220  cmp     [rbx], r12w
0x180033224  jz      loc_180033401
0x18003322a  mov     r8, r14; Source
0x18003322d  lea     rcx, [rsp+2C0h+Destination]; Destination
0x180033232  mov     r14d, 111h
0x180033238  mov     edx, r14d; SizeInWords
0x18003323b  call    cs:__imp_wcscpy_s
0x180033242  nop     dword ptr [rax+rax+00h]
0x180033247  lea     r8, Source; "\\"
0x18003324e  mov     edx, r14d; SizeInWords
0x180033251  lea     rcx, [rsp+2C0h+Destination]; Destination
0x180033256  call    cs:__imp_wcscat_s
0x18003325d  nop     dword ptr [rax+rax+00h]
0x180033262  mov     r8, rbx; Source
0x180033265  lea     rcx, [rsp+2C0h+Destination]; Destination
0x18003326a  mov     edx, r14d; SizeInWords
0x18003326d  call    cs:__imp_wcscat_s
0x180033274  nop     dword ptr [rax+rax+00h]
0x180033279  xor     ecx, ecx; BindingHandle
0x18003327b  call    cs:__imp_RpcImpersonateClient
0x180033282  nop     dword ptr [rax+rax+00h]
0x180033287  mov     ebx, eax
0x180033289  test    eax, eax
0x18003328b  jnz     loc_180033406
0x180033291  lea     r15d, [r12+1]
0x180033296  call    cs:__imp_GetCurrentThread
0x18003329d  nop     dword ptr [rax+rax+00h]
0x1800332a2  lea     r14d, [r12+8]
0x1800332a7  mov     r8d, r15d; OpenAsSelf
0x1800332aa  mov     rcx, rax; ThreadHandle
0x1800332ad  lea     r9, [rsp+2C0h+TokenHandle]; TokenHandle
0x1800332b2  mov     edx, r14d; DesiredAccess
0x1800332b5  call    cs:__imp_OpenThreadToken
0x1800332bc  nop     dword ptr [rax+rax+00h]
0x1800332c1  test    eax, eax
0x1800332c3  jnz     short loc_1800332D8
0x1800332c5  call    cs:__imp_GetLastError
0x1800332cc  nop     dword ptr [rax+rax+00h]
0x1800332d1  mov     ebx, eax
0x1800332d3  jmp     loc_180033406
0x1800332d8  lea     rax, [rsp+2C0h+var_278]
0x1800332dd  xor     r8d, r8d; Sid
0x1800332e0  mov     [rsp+2C0h+peUse], rax; peUse
0x1800332e5  lea     r9, [rsp+2C0h+cbSid]; cbSid
0x1800332ea  lea     rax, [rsp+2C0h+var_27C]
0x1800332ef  xor     ecx, ecx; lpSystemName
0x1800332f1  mov     [rsp+2C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800332f6  lea     rdx, [rsp+2C0h+Destination]; lpAccountName
0x1800332fb  mov     [rsp+2C0h+ReferencedDomainName], r12; ReferencedDomainName
0x180033300  call    cs:__imp_LookupAccountNameW
0x180033307  nop     dword ptr [rax+rax+00h]
0x18003330c  test    eax, eax
0x18003330e  jnz     short loc_180033327
0x180033310  call    cs:__imp_GetLastError
0x180033317  nop     dword ptr [rax+rax+00h]
0x18003331c  mov     ebx, eax
0x18003331e  cmp     eax, 7Ah ; 'z'
0x180033321  jnz     loc_180033406
0x180033327  mov     ebx, [rsp+2C0h+cbSid]
0x18003332b  call    cs:__imp_GetProcessHeap
0x180033332  nop     dword ptr [rax+rax+00h]
0x180033337  mov     r8d, ebx; dwBytes
0x18003333a  mov     edx, r14d; dwFlags
0x18003333d  mov     rcx, rax; hHeap
0x180033340  call    cs:__imp_HeapAlloc
0x180033347  nop     dword ptr [rax+rax+00h]
0x18003334c  mov     rdi, rax
0x18003334f  test    rax, rax
0x180033352  jz      loc_1800332C5
0x180033358  mov     eax, [rsp+2C0h+var_27C]
0x18003335c  add     eax, eax
0x18003335e  mov     [rsp+2C0h+var_274], eax
0x180033362  mov     ebx, eax
0x180033364  call    cs:__imp_GetProcessHeap
0x18003336b  nop     dword ptr [rax+rax+00h]
0x180033370  mov     r8d, ebx; dwBytes
0x180033373  mov     edx, r14d; dwFlags
0x180033376  mov     rcx, rax; hHeap
0x180033379  call    cs:__imp_HeapAlloc
0x180033380  nop     dword ptr [rax+rax+00h]
0x180033385  mov     rsi, rax
0x180033388  test    rax, rax
0x18003338b  jz      loc_1800332C5
0x180033391  lea     rax, [rsp+2C0h+var_278]
0x180033396  mov     r8, rdi; Sid
0x180033399  mov     [rsp+2C0h+peUse], rax; peUse
0x18003339e  lea     r9, [rsp+2C0h+cbSid]; cbSid
0x1800333a3  lea     rax, [rsp+2C0h+var_274]
0x1800333a8  xor     ecx, ecx; lpSystemName
0x1800333aa  mov     [rsp+2C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800333af  lea     rdx, [rsp+2C0h+Destination]; lpAccountName
0x1800333b4  mov     [rsp+2C0h+ReferencedDomainName], rsi; ReferencedDomainName
0x1800333b9  call    cs:__imp_LookupAccountNameW
0x1800333c0  nop     dword ptr [rax+rax+00h]
0x1800333c5  test    eax, eax
0x1800333c7  jz      loc_1800332C5
0x1800333cd  mov     rcx, [rsp+2C0h+TokenHandle]; TokenHandle
0x1800333d2  lea     r8, [rsp+2C0h+IsMember]; IsMember
0x1800333d7  mov     rdx, rdi; SidToCheck
0x1800333da  call    cs:__imp_CheckTokenMembership
0x1800333e1  nop     dword ptr [rax+rax+00h]
0x1800333e6  test    eax, eax
0x1800333e8  jz      loc_1800332C5
0x1800333ee  cmp     [rsp+2C0h+IsMember], r12d
0x1800333f3  jnz     short loc_1800333FC
0x1800333f5  mov     ebx, 5
0x1800333fa  jmp     short loc_180033406
0x1800333fc  mov     ebx, r12d
0x1800333ff  jmp     short loc_180033406
0x180033401  mov     ebx, 57h ; 'W'
0x180033406  mov     rcx, [rsp+2C0h+TokenHandle]; hObject
0x18003340b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003340f  jz      short loc_18003341D
0x180033411  call    cs:__imp_CloseHandle
0x180033418  nop     dword ptr [rax+rax+00h]
0x18003341d  test    rdi, rdi
0x180033420  jz      short loc_180033442
0x180033422  call    cs:__imp_GetProcessHeap
0x180033429  nop     dword ptr [rax+rax+00h]
0x18003342e  mov     r8, rdi; lpMem
0x180033431  xor     edx, edx; dwFlags
0x180033433  mov     rcx, rax; hHeap
0x180033436  call    cs:__imp_HeapFree
0x18003343d  nop     dword ptr [rax+rax+00h]
0x180033442  test    rsi, rsi
0x180033445  jz      short loc_180033467
0x180033447  call    cs:__imp_GetProcessHeap
0x18003344e  nop     dword ptr [rax+rax+00h]
0x180033453  mov     r8, rsi; lpMem
0x180033456  xor     edx, edx; dwFlags
0x180033458  mov     rcx, rax; hHeap
0x18003345b  call    cs:__imp_HeapFree
0x180033462  nop     dword ptr [rax+rax+00h]
0x180033467  test    r15d, r15d
0x18003346a  jz      short loc_180033478
0x18003346c  call    cs:__imp_RpcRevertToSelf
0x180033473  nop     dword ptr [rax+rax+00h]
0x180033478  mov     eax, ebx
0x18003347a  mov     rcx, [rbp+1C0h+var_30]
0x180033481  xor     rcx, rsp; StackCookie
0x180033484  call    __security_check_cookie
0x180033489  lea     r11, [rsp+2C0h+var_20]
0x180033491  mov     rbx, [r11+40h]
0x180033495  mov     rsi, [r11+48h]
0x180033499  mov     rsp, r11
0x18003349c  pop     r15
0x18003349e  pop     r14
0x1800334a0  pop     r12
0x1800334a2  pop     rdi
0x1800334a3  pop     rbp
0x1800334a4  retn
```
