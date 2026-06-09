# GenerateDsrParameters

- ea: `0x18000945c`
- end: `0x180009658`
- name: `GenerateDsrParameters`
- size: `508`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009680`
- `0x180009740`

## callees

- `0x180008860`
- `0x18000945c`
- `0x180009868`
- `0x180051160`

## import_xrefs

- `msvcrt!wcsstr` at `0x18000953f`
- `msvcrt!wcsstr` at `0x18000953f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180009502`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800095ec`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180009502`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800095ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095af`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800095a5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800095a5`
- `logoncli!DsGetDcNameW` at `0x1800094d0`
- `logoncli!DsGetDcNameW` at `0x18000956f`
- `logoncli!DsGetDcNameW` at `0x1800094d0`
- `logoncli!DsGetDcNameW` at `0x18000956f`
- `netutils!NetApiBufferFree` at `0x18000962c`
- `netutils!NetApiBufferFree` at `0x18000962c`

## pseudocode

```c
__int64 __fastcall GenerateDsrParameters(wchar_t *a1, WCHAR *a2, wchar_t **a3, wchar_t **a4)
{
  __int64 v4; // rsi
  WCHAR *v7; // rdi
  DWORD DcNameW; // ebx
  __int64 v9; // rax
  __int64 v10; // rax
  size_t v11; // r14
  wchar_t *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // eax
  size_t v16; // rsi
  wchar_t *v17; // rax
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+30h] [rbp-40h] BYREF
  DWORD nSize; // [rsp+38h] [rbp-38h] BYREF
  WCHAR Buffer[16]; // [rsp+40h] [rbp-30h] BYREF

  *a3 = a2;
  v4 = -1;
  DomainControllerInfo = 0;
  *a4 = a1;
  v7 = a2;
  if ( !a1 )
    goto LABEL_5;
  DcNameW = 0;
  v9 = -1;
  do
    ++v9;
  while ( a1[v9] );
  if ( !v9 )
  {
LABEL_5:
    DcNameW = DsGetDcNameW(0, 0, 0, 0, 0x10u, &DomainControllerInfo);
    if ( DcNameW )
      goto LABEL_27;
    v10 = -1;
    do
      ++v10;
    while ( DomainControllerInfo->DomainName[v10] );
    v11 = 2 * v10 + 2;
    v12 = (wchar_t *)GlobalAlloc(0, (unsigned int)(2 * v10 + 2));
    *a4 = v12;
    if ( !v12 )
      goto LABEL_9;
    StringCbCopyW(v12, v11, DomainControllerInfo->DomainName);
  }
  if ( v7 && wcsstr(v7, L"\\") )
    goto LABEL_27;
  if ( !DomainControllerInfo )
  {
    DcNameW = DsGetDcNameW(0, 0, 0, 0, 0x10u, &DomainControllerInfo);
    if ( DcNameW )
      goto LABEL_27;
  }
  if ( !v7 )
    goto LABEL_19;
  v13 = -1;
  do
    ++v13;
  while ( v7[v13] );
  if ( !v13 )
  {
LABEL_19:
    nSize = 16;
    if ( !GetComputerNameW(Buffer, &nSize) )
    {
      DcNameW = GetLastError();
      goto LABEL_27;
    }
    v7 = Buffer;
  }
  v14 = -1;
  do
    ++v14;
  while ( v7[v14] );
  do
    ++v4;
  while ( DomainControllerInfo->DomainName[v4] );
  v15 = v14 + v4;
  v16 = 2 * (v14 + v4) + 4;
  v17 = (wchar_t *)GlobalAlloc(0, (unsigned int)(2 * v15 + 4));
  *a3 = v17;
  if ( !v17 )
  {
LABEL_9:
    DcNameW = 8;
    goto LABEL_27;
  }
  StringCbPrintfW(v17, v16, L"%s%s%s", DomainControllerInfo->DomainName, L"\\", v7);
LABEL_27:
  if ( DomainControllerInfo )
    NetApiBufferFree(DomainControllerInfo);
  return DcNameW;
}

```

## disassembly

```asm
0x18000945c  mov     [rsp-38h+arg_0], rbx
0x180009461  push    rbp
0x180009462  push    rsi
0x180009463  push    rdi
0x180009464  push    r12
0x180009466  push    r13
0x180009468  push    r14
0x18000946a  push    r15
0x18000946c  mov     rbp, rsp
0x18000946f  sub     rsp, 70h
0x180009473  mov     rax, cs:__security_cookie
0x18000947a  xor     rax, rsp
0x18000947d  mov     [rbp+var_10], rax
0x180009481  xor     r13d, r13d
0x180009484  mov     [r8], rdx
0x180009487  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000948b  mov     [rbp+var_40], r13
0x18000948f  mov     [r9], rcx
0x180009492  mov     r15, r9
0x180009495  mov     r12, r8
0x180009498  mov     rdi, rdx
0x18000949b  test    rcx, rcx
0x18000949e  jz      short loc_1800094B5
0x1800094a0  mov     ebx, r13d
0x1800094a3  mov     rax, rsi
0x1800094a6  inc     rax
0x1800094a9  cmp     [rcx+rax*2], r13w
0x1800094ae  jnz     short loc_1800094A6
0x1800094b0  test    rax, rax
0x1800094b3  jnz     short loc_18000952D
0x1800094b5  lea     rax, [rbp+var_40]
0x1800094b9  xor     r9d, r9d; SiteName
0x1800094bc  mov     [rsp+70h+DomainControllerInfo], rax; DomainControllerInfo
0x1800094c1  xor     r8d, r8d; DomainGuid
0x1800094c4  xor     edx, edx; DomainName
0x1800094c6  mov     [rsp+70h+Flags], 10h; Flags
0x1800094ce  xor     ecx, ecx; ComputerName
0x1800094d0  call    cs:__imp_DsGetDcNameW
0x1800094d6  mov     ebx, eax
0x1800094d8  test    eax, eax
0x1800094da  jnz     loc_180009623
0x1800094e0  mov     rcx, [rbp+var_40]
0x1800094e4  mov     rax, rsi
0x1800094e7  mov     rdx, [rcx+28h]
0x1800094eb  inc     rax
0x1800094ee  cmp     [rdx+rax*2], r13w
0x1800094f3  jnz     short loc_1800094EB
0x1800094f5  lea     r14, ds:2[rax*2]
0x1800094fd  xor     ecx, ecx; uFlags
0x1800094ff  mov     edx, r14d; dwBytes
0x180009502  call    cs:__imp_GlobalAlloc
0x180009508  mov     [r15], rax
0x18000950b  test    rax, rax
0x18000950e  jnz     short loc_18000951A
0x180009510  mov     ebx, 8
0x180009515  jmp     loc_180009623
0x18000951a  mov     r8, [rbp+var_40]
0x18000951e  mov     rdx, r14; cbDest
0x180009521  mov     rcx, rax; pszDest
0x180009524  mov     r8, [r8+28h]; pszSrc
0x180009528  call    StringCbCopyW
0x18000952d  lea     r14, SubStr; "\\"
0x180009534  test    rdi, rdi
0x180009537  jz      short loc_18000954E
0x180009539  mov     rdx, r14; SubStr
0x18000953c  mov     rcx, rdi; Str
0x18000953f  call    cs:__imp_wcsstr
0x180009545  test    rax, rax
0x180009548  jnz     loc_180009623
0x18000954e  cmp     [rbp+var_40], r13
0x180009552  jnz     short loc_18000957F
0x180009554  lea     rax, [rbp+var_40]
0x180009558  xor     r9d, r9d; SiteName
0x18000955b  mov     [rsp+70h+DomainControllerInfo], rax; DomainControllerInfo
0x180009560  xor     r8d, r8d; DomainGuid
0x180009563  xor     edx, edx; DomainName
0x180009565  mov     [rsp+70h+Flags], 10h; Flags
0x18000956d  xor     ecx, ecx; ComputerName
0x18000956f  call    cs:__imp_DsGetDcNameW
0x180009575  mov     ebx, eax
0x180009577  test    eax, eax
0x180009579  jnz     loc_180009623
0x18000957f  test    rdi, rdi
0x180009582  jz      short loc_180009596
0x180009584  mov     rax, rsi
0x180009587  inc     rax
0x18000958a  cmp     [rdi+rax*2], r13w
0x18000958f  jnz     short loc_180009587
0x180009591  test    rax, rax
0x180009594  jnz     short loc_1800095BD
0x180009596  lea     rdx, [rbp+nSize]; nSize
0x18000959a  mov     [rbp+nSize], 10h
0x1800095a1  lea     rcx, [rbp+Buffer]; lpBuffer
0x1800095a5  call    cs:__imp_GetComputerNameW
0x1800095ab  test    eax, eax
0x1800095ad  jnz     short loc_1800095B9
0x1800095af  call    cs:__imp_GetLastError
0x1800095b5  mov     ebx, eax
0x1800095b7  jmp     short loc_180009623
0x1800095b9  lea     rdi, [rbp+Buffer]
0x1800095bd  mov     rcx, rsi
0x1800095c0  inc     rcx
0x1800095c3  cmp     [rdi+rcx*2], r13w
0x1800095c8  jnz     short loc_1800095C0
0x1800095ca  mov     rax, [rbp+var_40]
0x1800095ce  mov     rdx, [rax+28h]
0x1800095d2  inc     rsi
0x1800095d5  cmp     [rdx+rsi*2], r13w
0x1800095da  jnz     short loc_1800095D2
0x1800095dc  lea     rax, [rcx+rsi]
0x1800095e0  xor     ecx, ecx; uFlags
0x1800095e2  lea     rsi, ds:4[rax*2]
0x1800095ea  mov     edx, esi; dwBytes
0x1800095ec  call    cs:__imp_GlobalAlloc
0x1800095f2  mov     [r12], rax
0x1800095f6  test    rax, rax
0x1800095f9  jz      loc_180009510
0x1800095ff  mov     r9, [rbp+var_40]
0x180009603  lea     r8, aSSS; "%s%s%s"
0x18000960a  mov     [rsp+70h+DomainControllerInfo], rdi
0x18000960f  mov     rdx, rsi; cbDest
0x180009612  mov     rcx, rax; pszDest
0x180009615  mov     qword ptr [rsp+70h+Flags], r14
0x18000961a  mov     r9, [r9+28h]
0x18000961e  call    StringCbPrintfW
0x180009623  mov     rcx, [rbp+var_40]; Buffer
0x180009627  test    rcx, rcx
0x18000962a  jz      short loc_180009632
0x18000962c  call    cs:__imp_NetApiBufferFree
0x180009632  mov     eax, ebx
0x180009634  mov     rcx, [rbp+var_10]
0x180009638  xor     rcx, rsp; StackCookie
0x18000963b  call    __security_check_cookie
0x180009640  mov     rbx, [rsp+70h+arg_0]
0x180009648  add     rsp, 70h
0x18000964c  pop     r15
0x18000964e  pop     r14
0x180009650  pop     r13
0x180009652  pop     r12
0x180009654  pop     rdi
0x180009655  pop     rsi
0x180009656  pop     rbp
0x180009657  retn
```
