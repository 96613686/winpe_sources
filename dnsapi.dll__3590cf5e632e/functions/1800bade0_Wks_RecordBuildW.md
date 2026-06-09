# Wks_RecordBuildW

- ea: `0x1800bade0`
- end: `0x1800bb00b`
- name: `Wks_RecordBuildW`
- size: `555`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation`

## callees

- `0x18000df9c`
- `0x180011d40`
- `0x1800121d8`
- `0x18002b050`
- `0x18005c18c`
- `0x18006635c`
- `0x180075cbc`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800bade0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bae8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bafd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bae8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bafd8`
- `WS2_32!__imp_getprotobyname` at `0x1800baec6`
- `WS2_32!__imp_getprotobyname` at `0x1800baec6`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bafbb`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bafbb`
- `WS2_32!__imp_WSAStartup` at `0x1800bae7c`
- `WS2_32!__imp_WSAStartup` at `0x1800bae7c`
- `WS2_32!__imp_WSACleanup` at `0x1800bafa2`
- `WS2_32!__imp_WSACleanup` at `0x1800bafa2`

## pseudocode

```c
struct in_addr *__fastcall Wks_RecordBuildW(unsigned int a1, __int64 a2)
{
  DWORD Error; // ecx
  unsigned int v5; // esi
  unsigned int v6; // ecx
  __int64 v7; // rax
  struct in_addr *Record; // rbx
  DWORD v9; // eax
  const char *v10; // rax
  char *v11; // rbp
  struct protoent *v12; // rdi
  __int64 v13; // rdi
  const char *v14; // rax
  size_t v15; // r12
  char *v16; // r10
  char *i; // rcx
  const char *v18; // rax
  const char *v19; // rsi
  struct WSAData WSAData; // [rsp+20h] [rbp-1F8h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  if ( a1 < 3 )
    goto LABEL_2;
  v5 = 0;
  v6 = 2;
  do
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(*(_QWORD *)(a2 + 8LL * v6) + 2 * v7) );
    ++v6;
    v5 += v7 + 1;
  }
  while ( v6 < a1 );
  Record = (struct in_addr *)Dns_AllocateRecord(v5 + 6);
  if ( !Record )
    return 0;
  v9 = WSAStartup(0x202u, &WSAData);
  if ( v9 )
  {
    SetLastError(v9);
    Dns_RecordFree(Record);
    return 0;
  }
  v10 = (const char *)Dns_StringCopyAllocate(*(_QWORD *)a2, 0, 1, 2);
  v11 = (char *)v10;
  if ( !v10 )
    goto LABEL_22;
  v12 = getprotobyname(v10);
  DnsApiFree(v11);
  if ( !v12 || v12->p_proto >= 255 )
  {
    Dns_RecordFree(Record);
    Error = WSAGetLastError();
    goto LABEL_23;
  }
  Record[9].S_un.S_un_b.s_b1 = v12->p_proto;
  if ( !(unsigned int)Dns_Ip4StringToAddress_W(Record + 8, *(PCWSTR *)(a2 + 8)) )
  {
    Dns_RecordFree(Record);
LABEL_2:
    Error = 13;
LABEL_23:
    SetLastError(Error);
    return 0;
  }
  Record[9].S_un.S_un_b.s_b2 = v5;
  LODWORD(v13) = 2;
  v14 = (const char *)Dns_StringCopyAllocate(*(_QWORD *)(a2 + 16), 0, 1, 2);
  if ( !v14 )
  {
LABEL_22:
    Dns_RecordFree(Record);
    Error = 14;
    goto LABEL_23;
  }
  v15 = v5;
  StringCchCopyA((STRSAFE_LPSTR)&Record[9].S_un.S_un_b.s_b3, v5, v14);
  for ( i = v16; ; i = (char *)v19 )
  {
    DnsApiFree(i);
    v13 = (unsigned int)(v13 + 1);
    if ( (unsigned int)v13 >= a1 )
      break;
    StringCchCatA((STRSAFE_LPSTR)&Record[9].S_un.S_un_b.s_b3, v15, " ");
    v18 = (const char *)Dns_StringCopyAllocate(*(_QWORD *)(a2 + 8 * v13), 0, 1, 2);
    v19 = v18;
    if ( !v18 )
      goto LABEL_22;
    StringCchCatA((STRSAFE_LPSTR)&Record[9].S_un.S_un_b.s_b3, v15, v18);
  }
  WSACleanup();
  return Record;
}

```

## disassembly

```asm
0x1800bade0  push    rbx
0x1800bade2  push    rbp
0x1800bade3  push    rsi
0x1800bade4  push    rdi
0x1800bade5  push    r12
0x1800bade7  push    r13
0x1800bade9  push    r14
0x1800badeb  push    r15
0x1800baded  sub     rsp, 1D8h
0x1800badf4  mov     rax, cs:__security_cookie
0x1800badfb  xor     rax, rsp
0x1800badfe  mov     [rsp+218h+var_58], rax
0x1800bae06  mov     r14, rdx
0x1800bae09  mov     r15d, ecx
0x1800bae0c  xor     edx, edx; Val
0x1800bae0e  lea     rcx, [rsp+218h+WSAData]; void *
0x1800bae13  mov     r8d, 198h; Size
0x1800bae19  call    memset_0
0x1800bae1e  cmp     r15d, 3
0x1800bae22  jnb     short loc_1800BAE2E
0x1800bae24  mov     ecx, 0Dh
0x1800bae29  jmp     loc_1800BAFD8
0x1800bae2e  xor     r13d, r13d
0x1800bae31  mov     esi, r13d
0x1800bae34  lea     edi, [r13+2]
0x1800bae38  mov     ecx, edi
0x1800bae3a  lea     r12d, [r13+1]
0x1800bae3e  mov     eax, ecx
0x1800bae40  mov     rdx, [r14+rax*8]
0x1800bae44  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bae48  inc     rax
0x1800bae4b  cmp     [rdx+rax*2], r13w
0x1800bae50  jnz     short loc_1800BAE48
0x1800bae52  inc     esi
0x1800bae54  add     ecx, r12d
0x1800bae57  add     esi, eax
0x1800bae59  cmp     ecx, r15d
0x1800bae5c  jb      short loc_1800BAE3E
0x1800bae5e  lea     ecx, [rsi+6]
0x1800bae61  call    Dns_AllocateRecord
0x1800bae66  mov     rbx, rax
0x1800bae69  test    rax, rax
0x1800bae6c  jz      loc_1800BAFE4
0x1800bae72  mov     ecx, 202h; wVersionRequested
0x1800bae77  lea     rdx, [rsp+218h+WSAData]; lpWSAData
0x1800bae7c  call    cs:__imp_WSAStartup
0x1800bae83  nop     dword ptr [rax+rax+00h]
0x1800bae88  test    eax, eax
0x1800bae8a  jz      short loc_1800BAEA7
0x1800bae8c  mov     ecx, eax; dwErrCode
0x1800bae8e  call    cs:__imp_SetLastError
0x1800bae95  nop     dword ptr [rax+rax+00h]
0x1800bae9a  mov     rcx, rbx; lpMem
0x1800bae9d  call    Dns_RecordFree
0x1800baea2  jmp     loc_1800BAFE4
0x1800baea7  mov     rcx, [r14]
0x1800baeaa  mov     r9d, edi
0x1800baead  mov     r8d, r12d
0x1800baeb0  xor     edx, edx
0x1800baeb2  call    Dns_StringCopyAllocate
0x1800baeb7  mov     rbp, rax
0x1800baeba  test    rax, rax
0x1800baebd  jz      loc_1800BAFCB
0x1800baec3  mov     rcx, rax; name
0x1800baec6  call    cs:__imp_getprotobyname
0x1800baecd  nop     dword ptr [rax+rax+00h]
0x1800baed2  mov     rcx, rbp; lpMem
0x1800baed5  mov     rdi, rax
0x1800baed8  call    DnsApiFree
0x1800baedd  test    rdi, rdi
0x1800baee0  jz      loc_1800BAFB3
0x1800baee6  mov     eax, 0FFh
0x1800baeeb  cmp     [rdi+10h], ax
0x1800baeef  jge     loc_1800BAFB3
0x1800baef5  mov     al, [rdi+10h]
0x1800baef8  lea     rcx, [rbx+20h]; Addr
0x1800baefc  mov     [rbx+24h], al
0x1800baeff  mov     rdx, [r14+8]; S
0x1800baf03  call    Dns_Ip4StringToAddress_W
0x1800baf08  test    eax, eax
0x1800baf0a  jnz     short loc_1800BAF19
0x1800baf0c  mov     rcx, rbx; lpMem
0x1800baf0f  call    Dns_RecordFree
0x1800baf14  jmp     loc_1800BAE24
0x1800baf19  mov     [rbx+25h], sil
0x1800baf1d  mov     edi, 2
0x1800baf22  mov     rcx, [r14+10h]
0x1800baf26  mov     r9d, edi
0x1800baf29  mov     r8d, r12d
0x1800baf2c  xor     edx, edx
0x1800baf2e  call    Dns_StringCopyAllocate
0x1800baf33  mov     r10, rax
0x1800baf36  test    rax, rax
0x1800baf39  jz      loc_1800BAFCB
0x1800baf3f  lea     rbp, [rbx+26h]
0x1800baf43  mov     edx, esi; cchDest
0x1800baf45  mov     rcx, rbp; pszDest
0x1800baf48  mov     r12d, esi
0x1800baf4b  mov     r8, rax; pszSrc
0x1800baf4e  call    StringCchCopyA
0x1800baf53  mov     rcx, r10; lpMem
0x1800baf56  call    DnsApiFree
0x1800baf5b  inc     edi
0x1800baf5d  cmp     edi, r15d
0x1800baf60  jnb     short loc_1800BAFA2
0x1800baf62  lea     r8, asc_1800F7F74; " "
0x1800baf69  mov     rdx, r12; cchDest
0x1800baf6c  mov     rcx, rbp; pszDest
0x1800baf6f  call    StringCchCatA
0x1800baf74  mov     rcx, [r14+rdi*8]
0x1800baf78  xor     edx, edx
0x1800baf7a  lea     r9d, [rdx+2]
0x1800baf7e  lea     r8d, [rdx+1]
0x1800baf82  call    Dns_StringCopyAllocate
0x1800baf87  mov     rsi, rax
0x1800baf8a  test    rax, rax
0x1800baf8d  jz      short loc_1800BAFCB
0x1800baf8f  mov     r8, rax; pszSrc
0x1800baf92  mov     rdx, r12; cchDest
0x1800baf95  mov     rcx, rbp; pszDest
0x1800baf98  call    StringCchCatA
0x1800baf9d  mov     rcx, rsi
0x1800bafa0  jmp     short loc_1800BAF56
0x1800bafa2  call    cs:__imp_WSACleanup
0x1800bafa9  nop     dword ptr [rax+rax+00h]
0x1800bafae  mov     rax, rbx
0x1800bafb1  jmp     short loc_1800BAFE6
0x1800bafb3  mov     rcx, rbx; lpMem
0x1800bafb6  call    Dns_RecordFree
0x1800bafbb  call    cs:__imp_WSAGetLastError
0x1800bafc2  nop     dword ptr [rax+rax+00h]
0x1800bafc7  mov     ecx, eax
0x1800bafc9  jmp     short loc_1800BAFD8
0x1800bafcb  mov     rcx, rbx; lpMem
0x1800bafce  call    Dns_RecordFree
0x1800bafd3  mov     ecx, 0Eh; dwErrCode
0x1800bafd8  call    cs:__imp_SetLastError
0x1800bafdf  nop     dword ptr [rax+rax+00h]
0x1800bafe4  xor     eax, eax
0x1800bafe6  mov     rcx, [rsp+218h+var_58]
0x1800bafee  xor     rcx, rsp; StackCookie
0x1800baff1  call    __security_check_cookie
0x1800baff6  add     rsp, 1D8h
0x1800baffd  pop     r15
0x1800bafff  pop     r14
0x1800bb001  pop     r13
0x1800bb003  pop     r12
0x1800bb005  pop     rdi
0x1800bb006  pop     rsi
0x1800bb007  pop     rbp
0x1800bb008  pop     rbx
0x1800bb009  retn
```
