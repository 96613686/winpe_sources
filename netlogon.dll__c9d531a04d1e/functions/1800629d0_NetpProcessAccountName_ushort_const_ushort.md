# NetpProcessAccountName(ushort const *,ushort * *)

- ea: `0x1800629d0`
- end: `0x180062bb1`
- name: `?NetpProcessAccountName@@YAJPEBGPEAPEAG@Z`
- size: `481`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPVOID *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180060fa4`
- `0x180062d04`
- `0x180062ee0`

## callees

- `0x180007278`
- `0x1800629d0`
- `0x180083180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180062a46`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180062b7c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180062a46`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180062b7c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180062a58`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180062a84`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180062a58`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180062a84`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180062a25`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180062a25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062b85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062b97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062b85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062b97`
- `ntdll!RtlEqualDomainName` at `0x180062aee`
- `ntdll!RtlEqualDomainName` at `0x180062aee`
- `ntdll!RtlInitUnicodeString` at `0x180062ad8`
- `ntdll!RtlInitUnicodeString` at `0x180062ad8`
- `netutils!NetApiBufferAllocate` at `0x180062b60`
- `netutils!NetApiBufferAllocate` at `0x180062b60`
- `netutils!NetpIsComputerNameValid` at `0x180062aa5`
- `netutils!NetpIsComputerNameValid` at `0x180062aa5`

## string_xrefs

- `0x180062a63`: `Netr*ServiceAccount APIs do not support UPN style names\n`
- `0x180062ab2`: `Account name %s is not valid as a service account\n`
- `0x180062b24`: `If a domain name is provided, it must equal this computer's current domain name\n`
- `0x180062b3f`: `Managed service account names cannot exceed 15 characters\n`

## pseudocode

```c
__int64 __fastcall NetpProcessAccountName(const unsigned __int16 *a1, LPVOID *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // r14
  wchar_t *v8; // rax
  wchar_t *v9; // rbp
  signed int v10; // ebx
  wchar_t *v11; // rax
  wchar_t *v12; // rsi
  const WCHAR *v13; // r14
  unsigned int v14; // r14d
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF

  if ( !a1 )
    return 3221225570LL;
  if ( !a2 )
    return 3221225485LL;
  v4 = -1;
  *a2 = 0;
  v5 = -1;
  do
    ++v5;
  while ( a1[v5] );
  v6 = (unsigned int)(v5 + 1);
  v7 = (unsigned int)v6;
  v8 = (wchar_t *)LocalAlloc(0, 2 * v6);
  v9 = v8;
  if ( !v8 )
    return 3221225626LL;
  _o_wcscpy_s(v8, v7);
  if ( wcsrchr(v9, 0x40u) )
  {
    NlPrintRoutine(0x40u, L"Netr*ServiceAccount APIs do not support UPN style names\n");
LABEL_11:
    v10 = -1073741726;
    goto LABEL_29;
  }
  v11 = wcsrchr(v9, 0x5Cu);
  if ( v11 )
  {
    *v11 = 0;
    v12 = v11 + 1;
    v13 = v9;
  }
  else
  {
    v13 = 0;
    v12 = v9;
  }
  if ( !(unsigned int)NetpIsComputerNameValid(v12) )
  {
    NlPrintRoutine(0x40u, L"Account name %s is not valid as a service account\n", v12);
    goto LABEL_11;
  }
  if ( v13 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, v13);
    if ( !RtlEqualDomainName(&DestinationString, (PUNICODE_STRING)((char *)NlGlobalDomainInfo + 56))
      && !(unsigned int)NlEqualDnsNameU(&DestinationString, (struct _UNICODE_STRING *)NlGlobalDomainInfo + 8)
      && (DestinationString.Length != 2 || *DestinationString.Buffer != 46) )
    {
      NlPrintRoutine(0x40u, L"If a domain name is provided, it must equal this computer's current domain name\n");
      goto LABEL_11;
    }
  }
  do
    ++v4;
  while ( v12[v4] );
  if ( (unsigned int)v4 <= 0xF )
  {
    v14 = v4 + 1;
    v10 = NetApiBufferAllocate(2 * (v4 + 1), a2);
    if ( v10 )
      v10 = -1073741801;
    else
      _o_wcscpy_s(*a2, v14);
  }
  else
  {
    NlPrintRoutine(0x40u, L"Managed service account names cannot exceed 15 characters\n");
    v10 = -1073741562;
  }
LABEL_29:
  LocalFree(v9);
  if ( v10 < 0 )
  {
    if ( *a2 )
    {
      LocalFree(*a2);
      *a2 = 0;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800629d0  push    rbx
0x1800629d2  push    rbp
0x1800629d3  push    rsi
0x1800629d4  push    rdi
0x1800629d5  push    r12
0x1800629d7  push    r14
0x1800629d9  push    r15
0x1800629db  sub     rsp, 30h
0x1800629df  xor     r15d, r15d
0x1800629e2  mov     rdi, rdx
0x1800629e5  mov     rsi, rcx
0x1800629e8  test    rcx, rcx
0x1800629eb  jnz     short loc_1800629F7
0x1800629ed  mov     eax, 0C0000062h
0x1800629f2  jmp     loc_180062BA2
0x1800629f7  test    rdi, rdi
0x1800629fa  jnz     short loc_180062A06
0x1800629fc  mov     eax, 0C000000Dh
0x180062a01  jmp     loc_180062BA2
0x180062a06  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180062a0a  mov     [rdx], r15
0x180062a0d  mov     rax, rbx
0x180062a10  inc     rax
0x180062a13  cmp     [rcx+rax*2], r15w
0x180062a18  jnz     short loc_180062A10
0x180062a1a  inc     eax
0x180062a1c  xor     ecx, ecx; uFlags
0x180062a1e  mov     r14d, eax
0x180062a21  lea     rdx, [rax+rax]; uBytes
0x180062a25  call    cs:__imp_LocalAlloc
0x180062a2b  mov     rbp, rax
0x180062a2e  test    rax, rax
0x180062a31  jnz     short loc_180062A3D
0x180062a33  mov     eax, 0C000009Ah
0x180062a38  jmp     loc_180062BA2
0x180062a3d  mov     r8, rsi
0x180062a40  mov     rdx, r14
0x180062a43  mov     rcx, rbp
0x180062a46  call    cs:__imp__o_wcscpy_s
0x180062a4c  mov     r12d, 40h ; '@'
0x180062a52  mov     rcx, rbp; Str
0x180062a55  mov     edx, r12d; Ch
0x180062a58  call    cs:__imp_wcsrchr
0x180062a5e  test    rax, rax
0x180062a61  jz      short loc_180062A7C
0x180062a63  lea     rdx, aNetrServiceacc; "Netr*ServiceAccount APIs do not support"...
0x180062a6a  mov     ecx, r12d; unsigned int
0x180062a6d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180062a72  mov     ebx, 0C0000062h
0x180062a77  jmp     loc_180062B82
0x180062a7c  mov     edx, 5Ch ; '\'; Ch
0x180062a81  mov     rcx, rbp; Str
0x180062a84  call    cs:__imp_wcsrchr
0x180062a8a  test    rax, rax
0x180062a8d  jz      short loc_180062A9C
0x180062a8f  mov     [rax], r15w
0x180062a93  lea     rsi, [rax+2]
0x180062a97  mov     r14, rbp
0x180062a9a  jmp     short loc_180062AA2
0x180062a9c  mov     r14, r15
0x180062a9f  mov     rsi, rbp
0x180062aa2  mov     rcx, rsi
0x180062aa5  call    cs:__imp_NetpIsComputerNameValid
0x180062aab  test    eax, eax
0x180062aad  jnz     short loc_180062AC3
0x180062aaf  mov     r8, rsi
0x180062ab2  lea     rdx, aAccountNameSIs; "Account name %s is not valid as a servi"...
0x180062ab9  mov     ecx, r12d; unsigned int
0x180062abc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180062ac1  jmp     short loc_180062A72
0x180062ac3  test    r14, r14
0x180062ac6  jz      short loc_180062B30
0x180062ac8  xorps   xmm0, xmm0
0x180062acb  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180062ad0  mov     rdx, r14; SourceString
0x180062ad3  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180062ad8  call    cs:__imp_RtlInitUnicodeString
0x180062ade  mov     rdx, cs:?NlGlobalDomainInfo@@3PEAU_DOMAIN_INFO@@EA; _DOMAIN_INFO * NlGlobalDomainInfo
0x180062ae5  lea     rcx, [rsp+68h+DestinationString]; DomainName1
0x180062aea  add     rdx, 38h ; '8'; DomainName2
0x180062aee  call    cs:__imp_RtlEqualDomainName
0x180062af4  test    al, al
0x180062af6  jnz     short loc_180062B30
0x180062af8  mov     rdx, cs:?NlGlobalDomainInfo@@3PEAU_DOMAIN_INFO@@EA; _DOMAIN_INFO * NlGlobalDomainInfo
0x180062aff  lea     rcx, [rsp+68h+DestinationString]; struct _UNICODE_STRING *
0x180062b04  sub     rdx, 0FFFFFFFFFFFFFF80h; struct _UNICODE_STRING *
0x180062b08  call    ?NlEqualDnsNameU@@YAHPEAU_UNICODE_STRING@@0@Z; NlEqualDnsNameU(_UNICODE_STRING *,_UNICODE_STRING *)
0x180062b0d  test    eax, eax
0x180062b0f  jnz     short loc_180062B30
0x180062b11  cmp     [rsp+68h+DestinationString.Length], 2
0x180062b17  jnz     short loc_180062B24
0x180062b19  mov     rax, [rsp+68h+DestinationString.Buffer]
0x180062b1e  cmp     word ptr [rax], 2Eh ; '.'
0x180062b22  jz      short loc_180062B30
0x180062b24  lea     rdx, aIfADomainNameI; "If a domain name is provided, it must e"...
0x180062b2b  jmp     loc_180062A6A
0x180062b30  inc     rbx
0x180062b33  cmp     [rsi+rbx*2], r15w
0x180062b38  jnz     short loc_180062B30
0x180062b3a  cmp     ebx, 0Fh
0x180062b3d  jbe     short loc_180062B55
0x180062b3f  lea     rdx, aManagedService; "Managed service account names cannot ex"...
0x180062b46  mov     ecx, r12d; unsigned int
0x180062b49  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180062b4e  mov     ebx, 0C0000106h
0x180062b53  jmp     short loc_180062B82
0x180062b55  lea     r14d, [rbx+1]
0x180062b59  mov     rdx, rdi; Buffer
0x180062b5c  lea     ecx, [r14+r14]; ByteCount
0x180062b60  call    cs:__imp_NetApiBufferAllocate
0x180062b66  mov     ebx, eax
0x180062b68  test    eax, eax
0x180062b6a  jz      short loc_180062B73
0x180062b6c  mov     ebx, 0C0000017h
0x180062b71  jmp     short loc_180062B82
0x180062b73  mov     rcx, [rdi]
0x180062b76  mov     r8, rsi
0x180062b79  mov     edx, r14d
0x180062b7c  call    cs:__imp__o_wcscpy_s
0x180062b82  mov     rcx, rbp; hMem
0x180062b85  call    cs:__imp_LocalFree
0x180062b8b  test    ebx, ebx
0x180062b8d  jns     short loc_180062BA0
0x180062b8f  mov     rcx, [rdi]; hMem
0x180062b92  test    rcx, rcx
0x180062b95  jz      short loc_180062BA0
0x180062b97  call    cs:__imp_LocalFree
0x180062b9d  mov     [rdi], r15
0x180062ba0  mov     eax, ebx
0x180062ba2  add     rsp, 30h
0x180062ba6  pop     r15
0x180062ba8  pop     r14
0x180062baa  pop     r12
0x180062bac  pop     rdi
0x180062bad  pop     rsi
0x180062bae  pop     rbp
0x180062baf  pop     rbx
0x180062bb0  retn
```
