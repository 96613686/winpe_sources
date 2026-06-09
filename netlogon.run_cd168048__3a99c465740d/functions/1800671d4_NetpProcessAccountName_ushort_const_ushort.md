# NetpProcessAccountName(ushort const *,ushort * *)

- ea: `0x1800671d4`
- end: `0x1800673f8`
- name: `?NetpProcessAccountName@@YAJPEBGPEAPEAG@Z`
- size: `548`
- prototype: `int(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180065520`
- `0x180067558`
- `0x180067760`

## callees

- `0x180007518`
- `0x1800671d4`
- `0x180089328`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180067250`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800673b0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180067250`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800673b0`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180067268`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006729a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180067268`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006729a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180067229`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180067229`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800673bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800673d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800673bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800673d7`
- `ntdll!RtlEqualDomainName` at `0x180067316`
- `ntdll!RtlEqualDomainName` at `0x180067316`
- `ntdll!RtlInitUnicodeString` at `0x1800672fa`
- `ntdll!RtlInitUnicodeString` at `0x1800672fa`
- `netutils!NetApiBufferAllocate` at `0x18006738e`
- `netutils!NetApiBufferAllocate` at `0x18006738e`
- `netutils!NetpIsComputerNameValid` at `0x1800672c1`
- `netutils!NetpIsComputerNameValid` at `0x1800672c1`

## string_xrefs

- `0x180067279`: `Netr*ServiceAccount APIs do not support UPN style names\n`
- `0x1800672d4`: `Account name %s is not valid as a service account\n`
- `0x180067352`: `If a domain name is provided, it must equal this computer's current domain name\n`
- `0x18006736d`: `Managed service account names cannot exceed 15 characters\n`

## pseudocode

```c
__int64 __fastcall NetpProcessAccountName(const unsigned __int16 *a1, LPVOID *a2)
{
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // r14
  wchar_t *v9; // rax
  wchar_t *v10; // rbp
  signed int v11; // ebx
  wchar_t *v12; // rax
  wchar_t *v13; // rsi
  const WCHAR *v14; // r14
  unsigned int v15; // r14d
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF

  if ( !a1 )
    return 3221225570LL;
  if ( !a2 )
    return 3221225485LL;
  v5 = -1;
  *a2 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a1[v6] );
  v7 = (unsigned int)(v6 + 1);
  v8 = (unsigned int)v7;
  v9 = (wchar_t *)LocalAlloc(0, 2 * v7);
  v10 = v9;
  if ( !v9 )
    return 3221225626LL;
  _o_wcscpy_s(v9, v8, a1);
  if ( wcsrchr(v10, 0x40u) )
  {
    NlPrintRoutine(0x40u, L"Netr*ServiceAccount APIs do not support UPN style names\n");
LABEL_11:
    v11 = -1073741726;
    goto LABEL_29;
  }
  v12 = wcsrchr(v10, 0x5Cu);
  if ( v12 )
  {
    *v12 = 0;
    v13 = v12 + 1;
    v14 = v10;
  }
  else
  {
    v14 = 0;
    v13 = v10;
  }
  if ( !(unsigned int)NetpIsComputerNameValid(v13) )
  {
    NlPrintRoutine(0x40u, L"Account name %s is not valid as a service account\n", v13);
    goto LABEL_11;
  }
  if ( v14 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, v14);
    if ( !RtlEqualDomainName(&DestinationString, (PUNICODE_STRING)((char *)NlGlobalDomainInfo + 56))
      && !(unsigned int)NlEqualDnsNameU(&DestinationString, (struct _UNICODE_STRING *)NlGlobalDomainInfo + 8)
      && (DestinationString.Length != 2 || *DestinationString.Buffer != 46) )
    {
      NlPrintRoutine(0x40u, L"If a domain name is provided, it must equal this computer's current domain name\n");
      goto LABEL_11;
    }
  }
  do
    ++v5;
  while ( v13[v5] );
  if ( (unsigned int)v5 <= 0xF )
  {
    v15 = v5 + 1;
    v11 = NetApiBufferAllocate(2 * (v5 + 1), a2);
    if ( v11 )
      v11 = -1073741801;
    else
      _o_wcscpy_s(*a2, v15, v13);
  }
  else
  {
    NlPrintRoutine(0x40u, L"Managed service account names cannot exceed 15 characters\n");
    v11 = -1073741562;
  }
LABEL_29:
  LocalFree(v10);
  if ( v11 < 0 )
  {
    if ( *a2 )
    {
      LocalFree(*a2);
      *a2 = 0;
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800671d4  push    rbx
0x1800671d6  push    rbp
0x1800671d7  push    rsi
0x1800671d8  push    rdi
0x1800671d9  push    r12
0x1800671db  push    r14
0x1800671dd  push    r15
0x1800671df  sub     rsp, 30h
0x1800671e3  xor     r15d, r15d
0x1800671e6  mov     rdi, rdx
0x1800671e9  mov     rsi, rcx
0x1800671ec  test    rcx, rcx
0x1800671ef  jnz     short loc_1800671FB
0x1800671f1  mov     eax, 0C0000062h
0x1800671f6  jmp     loc_1800673E8
0x1800671fb  test    rdi, rdi
0x1800671fe  jnz     short loc_18006720A
0x180067200  mov     eax, 0C000000Dh
0x180067205  jmp     loc_1800673E8
0x18006720a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18006720e  mov     [rdx], r15
0x180067211  mov     rax, rbx
0x180067214  inc     rax
0x180067217  cmp     [rcx+rax*2], r15w
0x18006721c  jnz     short loc_180067214
0x18006721e  inc     eax
0x180067220  xor     ecx, ecx; uFlags
0x180067222  mov     r14d, eax
0x180067225  lea     rdx, [rax+rax]; uBytes
0x180067229  call    cs:__imp_LocalAlloc
0x180067230  nop     dword ptr [rax+rax+00h]
0x180067235  mov     rbp, rax
0x180067238  test    rax, rax
0x18006723b  jnz     short loc_180067247
0x18006723d  mov     eax, 0C000009Ah
0x180067242  jmp     loc_1800673E8
0x180067247  mov     r8, rsi
0x18006724a  mov     rdx, r14
0x18006724d  mov     rcx, rbp
0x180067250  call    cs:__imp__o_wcscpy_s
0x180067257  nop     dword ptr [rax+rax+00h]
0x18006725c  mov     r12d, 40h ; '@'
0x180067262  mov     rcx, rbp; Str
0x180067265  mov     edx, r12d; Ch
0x180067268  call    cs:__imp_wcsrchr
0x18006726f  nop     dword ptr [rax+rax+00h]
0x180067274  test    rax, rax
0x180067277  jz      short loc_180067292
0x180067279  lea     rdx, aNetrServiceacc; "Netr*ServiceAccount APIs do not support"...
0x180067280  mov     ecx, r12d; unsigned int
0x180067283  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180067288  mov     ebx, 0C0000062h
0x18006728d  jmp     loc_1800673BC
0x180067292  mov     edx, 5Ch ; '\'; Ch
0x180067297  mov     rcx, rbp; Str
0x18006729a  call    cs:__imp_wcsrchr
0x1800672a1  nop     dword ptr [rax+rax+00h]
0x1800672a6  test    rax, rax
0x1800672a9  jz      short loc_1800672B8
0x1800672ab  mov     [rax], r15w
0x1800672af  lea     rsi, [rax+2]
0x1800672b3  mov     r14, rbp
0x1800672b6  jmp     short loc_1800672BE
0x1800672b8  mov     r14, r15
0x1800672bb  mov     rsi, rbp
0x1800672be  mov     rcx, rsi
0x1800672c1  call    cs:__imp_NetpIsComputerNameValid
0x1800672c8  nop     dword ptr [rax+rax+00h]
0x1800672cd  test    eax, eax
0x1800672cf  jnz     short loc_1800672E5
0x1800672d1  mov     r8, rsi
0x1800672d4  lea     rdx, aAccountNameSIs; "Account name %s is not valid as a servi"...
0x1800672db  mov     ecx, r12d; unsigned int
0x1800672de  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800672e3  jmp     short loc_180067288
0x1800672e5  test    r14, r14
0x1800672e8  jz      short loc_18006735E
0x1800672ea  xorps   xmm0, xmm0
0x1800672ed  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800672f2  mov     rdx, r14; SourceString
0x1800672f5  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1800672fa  call    cs:__imp_RtlInitUnicodeString
0x180067301  nop     dword ptr [rax+rax+00h]
0x180067306  mov     rdx, cs:?NlGlobalDomainInfo@@3PEAU_DOMAIN_INFO@@EA; _DOMAIN_INFO * NlGlobalDomainInfo
0x18006730d  lea     rcx, [rsp+68h+DestinationString]; DomainName1
0x180067312  add     rdx, 38h ; '8'; DomainName2
0x180067316  call    cs:__imp_RtlEqualDomainName
0x18006731d  nop     dword ptr [rax+rax+00h]
0x180067322  test    al, al
0x180067324  jnz     short loc_18006735E
0x180067326  mov     rdx, cs:?NlGlobalDomainInfo@@3PEAU_DOMAIN_INFO@@EA; _DOMAIN_INFO * NlGlobalDomainInfo
0x18006732d  lea     rcx, [rsp+68h+DestinationString]; struct _UNICODE_STRING *
0x180067332  sub     rdx, 0FFFFFFFFFFFFFF80h; struct _UNICODE_STRING *
0x180067336  call    ?NlEqualDnsNameU@@YAHPEAU_UNICODE_STRING@@0@Z; NlEqualDnsNameU(_UNICODE_STRING *,_UNICODE_STRING *)
0x18006733b  test    eax, eax
0x18006733d  jnz     short loc_18006735E
0x18006733f  cmp     [rsp+68h+DestinationString.Length], 2
0x180067345  jnz     short loc_180067352
0x180067347  mov     rax, [rsp+68h+DestinationString.Buffer]
0x18006734c  cmp     word ptr [rax], 2Eh ; '.'
0x180067350  jz      short loc_18006735E
0x180067352  lea     rdx, aIfADomainNameI; "If a domain name is provided, it must e"...
0x180067359  jmp     loc_180067280
0x18006735e  inc     rbx
0x180067361  cmp     [rsi+rbx*2], r15w
0x180067366  jnz     short loc_18006735E
0x180067368  cmp     ebx, 0Fh
0x18006736b  jbe     short loc_180067383
0x18006736d  lea     rdx, aManagedService; "Managed service account names cannot ex"...
0x180067374  mov     ecx, r12d; unsigned int
0x180067377  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006737c  mov     ebx, 0C0000106h
0x180067381  jmp     short loc_1800673BC
0x180067383  lea     r14d, [rbx+1]
0x180067387  mov     rdx, rdi; Buffer
0x18006738a  lea     ecx, [r14+r14]; ByteCount
0x18006738e  call    cs:__imp_NetApiBufferAllocate
0x180067395  nop     dword ptr [rax+rax+00h]
0x18006739a  mov     ebx, eax
0x18006739c  test    eax, eax
0x18006739e  jz      short loc_1800673A7
0x1800673a0  mov     ebx, 0C0000017h
0x1800673a5  jmp     short loc_1800673BC
0x1800673a7  mov     rcx, [rdi]
0x1800673aa  mov     r8, rsi
0x1800673ad  mov     edx, r14d
0x1800673b0  call    cs:__imp__o_wcscpy_s
0x1800673b7  nop     dword ptr [rax+rax+00h]
0x1800673bc  mov     rcx, rbp; hMem
0x1800673bf  call    cs:__imp_LocalFree
0x1800673c6  nop     dword ptr [rax+rax+00h]
0x1800673cb  test    ebx, ebx
0x1800673cd  jns     short loc_1800673E6
0x1800673cf  mov     rcx, [rdi]; hMem
0x1800673d2  test    rcx, rcx
0x1800673d5  jz      short loc_1800673E6
0x1800673d7  call    cs:__imp_LocalFree
0x1800673de  nop     dword ptr [rax+rax+00h]
0x1800673e3  mov     [rdi], r15
0x1800673e6  mov     eax, ebx
0x1800673e8  add     rsp, 30h
0x1800673ec  pop     r15
0x1800673ee  pop     r14
0x1800673f0  pop     r12
0x1800673f2  pop     rdi
0x1800673f3  pop     rsi
0x1800673f4  pop     rbp
0x1800673f5  pop     rbx
0x1800673f6  retn
```
