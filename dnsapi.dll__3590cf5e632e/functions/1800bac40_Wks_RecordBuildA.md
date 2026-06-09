# Wks_RecordBuildA

- ea: `0x1800bac40`
- end: `0x1800badd0`
- name: `Wks_RecordBuildA`
- size: `400`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x18000df9c`
- `0x1800121d8`
- `0x18006635c`
- `0x180075cbc`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800bac40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bacdf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bada1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bacdf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bada1`
- `WS2_32!__imp_inet_addr` at `0x1800bad30`
- `WS2_32!__imp_inet_addr` at `0x1800bad30`
- `WS2_32!__imp_getprotobyname` at `0x1800bacfb`
- `WS2_32!__imp_getprotobyname` at `0x1800bacfb`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bad93`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bad93`
- `WS2_32!__imp_WSAStartup` at `0x1800baccd`
- `WS2_32!__imp_WSAStartup` at `0x1800baccd`
- `WS2_32!__imp_WSACleanup` at `0x1800bad0a`
- `WS2_32!__imp_WSACleanup` at `0x1800bad0a`

## pseudocode

```c
__int64 __fastcall Wks_RecordBuildA(unsigned int a1, const char **a2)
{
  unsigned int v4; // edi
  DWORD Error; // ecx
  size_t v6; // rsi
  unsigned int v7; // ecx
  __int64 v8; // rax
  __int64 Record; // rbx
  DWORD v10; // eax
  struct protoent *v11; // rbp
  unsigned int v12; // eax
  struct WSAData WSAData; // [rsp+20h] [rbp-1E8h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  v4 = 3;
  if ( a1 < 3 )
  {
    Error = 13;
LABEL_16:
    SetLastError(Error);
    return 0;
  }
  LODWORD(v6) = 0;
  v7 = 2;
  do
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v7][v8] );
    ++v7;
    v6 = (unsigned int)(v8 + v6 + 1);
  }
  while ( v7 < a1 );
  Record = Dns_AllocateRecord((unsigned int)(v6 + 6));
  if ( !Record )
    return 0;
  v10 = WSAStartup(0x202u, &WSAData);
  if ( v10 )
  {
    SetLastError(v10);
    Dns_RecordFree((LPVOID)Record);
    return 0;
  }
  v11 = getprotobyname(*a2);
  WSACleanup();
  if ( !v11 || v11->p_proto >= 255 )
  {
    Dns_RecordFree((LPVOID)Record);
    Error = WSAGetLastError();
    goto LABEL_16;
  }
  *(_BYTE *)(Record + 36) = v11->p_proto;
  v12 = inet_addr(a2[1]);
  *(_BYTE *)(Record + 37) = v6;
  *(_DWORD *)(Record + 32) = v12;
  StringCchCopyA((STRSAFE_LPSTR)(Record + 38), v6, a2[2]);
  if ( a1 > 3 )
  {
    do
    {
      StringCchCatA((STRSAFE_LPSTR)(Record + 38), v6, " ");
      StringCchCatA((STRSAFE_LPSTR)(Record + 38), v6, a2[v4++]);
    }
    while ( v4 < a1 );
  }
  return Record;
}

```

## disassembly

```asm
0x1800bac40  push    rbx
0x1800bac42  push    rbp
0x1800bac43  push    rsi
0x1800bac44  push    rdi
0x1800bac45  push    r14
0x1800bac47  push    r15
0x1800bac49  sub     rsp, 1D8h
0x1800bac50  mov     rax, cs:__security_cookie
0x1800bac57  xor     rax, rsp
0x1800bac5a  mov     [rsp+208h+var_48], rax
0x1800bac62  mov     r14, rdx
0x1800bac65  mov     r15d, ecx
0x1800bac68  xor     edx, edx; Val
0x1800bac6a  lea     rcx, [rsp+208h+WSAData]; void *
0x1800bac6f  mov     r8d, 198h; Size
0x1800bac75  call    memset_0
0x1800bac7a  mov     edi, 3
0x1800bac7f  cmp     r15d, edi
0x1800bac82  jnb     short loc_1800BAC8C
0x1800bac84  lea     ecx, [rdi+0Ah]
0x1800bac87  jmp     loc_1800BADA1
0x1800bac8c  xor     esi, esi
0x1800bac8e  lea     ecx, [rsi+2]
0x1800bac91  mov     eax, ecx
0x1800bac93  mov     rdx, [r14+rax*8]
0x1800bac97  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bac9b  inc     rax
0x1800bac9e  cmp     byte ptr [rdx+rax], 0
0x1800baca2  jnz     short loc_1800BAC9B
0x1800baca4  inc     esi
0x1800baca6  inc     ecx
0x1800baca8  add     esi, eax
0x1800bacaa  cmp     ecx, r15d
0x1800bacad  jb      short loc_1800BAC91
0x1800bacaf  lea     ecx, [rsi+6]
0x1800bacb2  call    Dns_AllocateRecord
0x1800bacb7  mov     rbx, rax
0x1800bacba  test    rax, rax
0x1800bacbd  jz      loc_1800BADAD
0x1800bacc3  mov     ecx, 202h; wVersionRequested
0x1800bacc8  lea     rdx, [rsp+208h+WSAData]; lpWSAData
0x1800baccd  call    cs:__imp_WSAStartup
0x1800bacd4  nop     dword ptr [rax+rax+00h]
0x1800bacd9  test    eax, eax
0x1800bacdb  jz      short loc_1800BACF8
0x1800bacdd  mov     ecx, eax; dwErrCode
0x1800bacdf  call    cs:__imp_SetLastError
0x1800bace6  nop     dword ptr [rax+rax+00h]
0x1800baceb  mov     rcx, rbx; lpMem
0x1800bacee  call    Dns_RecordFree
0x1800bacf3  jmp     loc_1800BADAD
0x1800bacf8  mov     rcx, [r14]; name
0x1800bacfb  call    cs:__imp_getprotobyname
0x1800bad02  nop     dword ptr [rax+rax+00h]
0x1800bad07  mov     rbp, rax
0x1800bad0a  call    cs:__imp_WSACleanup
0x1800bad11  nop     dword ptr [rax+rax+00h]
0x1800bad16  test    rbp, rbp
0x1800bad19  jz      short loc_1800BAD8B
0x1800bad1b  mov     eax, 0FFh
0x1800bad20  cmp     [rbp+10h], ax
0x1800bad24  jge     short loc_1800BAD8B
0x1800bad26  mov     al, [rbp+10h]
0x1800bad29  mov     [rbx+24h], al
0x1800bad2c  mov     rcx, [r14+8]; cp
0x1800bad30  call    cs:__imp_inet_addr
0x1800bad37  nop     dword ptr [rax+rax+00h]
0x1800bad3c  mov     [rbx+25h], sil
0x1800bad40  lea     rbp, [rbx+26h]
0x1800bad44  mov     [rbx+20h], eax
0x1800bad47  mov     rdx, rsi; cchDest
0x1800bad4a  mov     r8, [r14+10h]; pszSrc
0x1800bad4e  mov     rcx, rbp; pszDest
0x1800bad51  call    StringCchCopyA
0x1800bad56  cmp     r15d, edi
0x1800bad59  jbe     short loc_1800BAD86
0x1800bad5b  lea     r8, asc_1800F7F74; " "
0x1800bad62  mov     rdx, rsi; cchDest
0x1800bad65  mov     rcx, rbp; pszDest
0x1800bad68  call    StringCchCatA
0x1800bad6d  mov     r8d, edi
0x1800bad70  mov     rdx, rsi; cchDest
0x1800bad73  mov     rcx, rbp; pszDest
0x1800bad76  mov     r8, [r14+r8*8]; pszSrc
0x1800bad7a  call    StringCchCatA
0x1800bad7f  inc     edi
0x1800bad81  cmp     edi, r15d
0x1800bad84  jb      short loc_1800BAD5B
0x1800bad86  mov     rax, rbx
0x1800bad89  jmp     short loc_1800BADAF
0x1800bad8b  mov     rcx, rbx; lpMem
0x1800bad8e  call    Dns_RecordFree
0x1800bad93  call    cs:__imp_WSAGetLastError
0x1800bad9a  nop     dword ptr [rax+rax+00h]
0x1800bad9f  mov     ecx, eax; dwErrCode
0x1800bada1  call    cs:__imp_SetLastError
0x1800bada8  nop     dword ptr [rax+rax+00h]
0x1800badad  xor     eax, eax
0x1800badaf  mov     rcx, [rsp+208h+var_48]
0x1800badb7  xor     rcx, rsp; StackCookie
0x1800badba  call    __security_check_cookie
0x1800badbf  add     rsp, 1D8h
0x1800badc6  pop     r15
0x1800badc8  pop     r14
0x1800badca  pop     rdi
0x1800badcb  pop     rsi
0x1800badcc  pop     rbp
0x1800badcd  pop     rbx
0x1800badce  retn
```
