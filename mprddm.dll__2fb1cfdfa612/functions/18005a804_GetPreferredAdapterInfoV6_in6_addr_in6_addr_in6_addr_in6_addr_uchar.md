# GetPreferredAdapterInfoV6(in6_addr *,in6_addr *,in6_addr *,in6_addr *,uchar *)

- ea: `0x18005a804`
- end: `0x18005aad6`
- name: `?GetPreferredAdapterInfoV6@@YAKPEAUin6_addr@@000PEAE@Z`
- size: `722`
- prototype: `unsigned int __usercall@<eax>(struct in6_addr *@<rcx>, struct in6_addr *@<rdx>, struct in6_addr *@<r8>, struct in6_addr *@<r9>, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180056090`
- `0x18005aca0`
- `0x18005af38`

## callees

- `0x18005a63c`
- `0x18005a804`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18005a8d4`
- `KERNEL32!LocalFree` at `0x18005aaa4`
- `KERNEL32!LocalFree` at `0x18005a8d4`
- `KERNEL32!LocalFree` at `0x18005aaa4`
- `KERNEL32!CompareStringA` at `0x18005aa0c`
- `KERNEL32!CompareStringA` at `0x18005aa0c`
- `KERNEL32!GetLastError` at `0x18005a91a`
- `KERNEL32!GetLastError` at `0x18005a91a`
- `KERNEL32!LocalAlloc` at `0x18005a89e`
- `KERNEL32!LocalAlloc` at `0x18005a89e`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18005a8c4`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18005a903`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18005a8c4`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18005a903`

## pseudocode

```c
__int64 __fastcall GetPreferredAdapterInfoV6(
        struct in6_addr *a1,
        struct in6_addr *a2,
        struct in6_addr *a3,
        struct in6_addr *a4,
        unsigned __int8 *a5)
{
  unsigned int v7; // r14d
  __int64 v9; // rsi
  ULONG AdaptersAddresses; // edi
  __int64 v11; // rbx
  __int64 v12; // r14
  __int64 v13; // rax
  struct in6_addr *SizePointer; // [rsp+20h] [rbp-E0h]
  SIZE_T uBytes; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 *v17; // [rsp+38h] [rbp-C8h]
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  char v19[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v17 = a5;
  v7 = 0;
  v18 = 0;
  LODWORD(uBytes) = 0;
  v9 = -1;
  memset_0(v19, 0, sizeof(v19));
  if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800C9740 + 1),
      L"GetPreferredAdapterInfoV6");
  while ( 1 )
  {
    AdaptersAddresses = GetAdaptersAddresses(0x17u, 0x86u, 0, 0, (PULONG)&uBytes);
    if ( AdaptersAddresses != 111 )
      break;
    v9 = (__int64)LocalAlloc(0x40u, (unsigned int)uBytes);
    if ( !v9 )
    {
      AdaptersAddresses = GetLastError();
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v18) = 0;
        FormatRRASErrorString(
          &v18,
          L"Unable to allocate memory for the GetAdaptersAddresses buffer: %d",
          AdaptersAddresses);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v18);
      }
      break;
    }
    AdaptersAddresses = GetAdaptersAddresses(0x17u, 0x86u, 0, (PIP_ADAPTER_ADDRESSES)v9, (PULONG)&uBytes);
    if ( AdaptersAddresses != 111 )
    {
      v11 = v9;
LABEL_10:
      v9 = v11;
      goto LABEL_14;
    }
    LocalFree((HLOCAL)v9);
    v11 = 0;
    ++v7;
    LODWORD(uBytes) = 0;
    if ( v7 > 3 )
      goto LABEL_10;
    v9 = 0;
  }
  v11 = 0;
LABEL_14:
  if ( AdaptersAddresses )
  {
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v18) = 0;
      FormatRRASErrorString(&v18, L"GetAdaptersAddresses fails with %d\n", AdaptersAddresses);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v18);
    }
  }
  else
  {
    v12 = 0;
    while ( v11 )
    {
      if ( ((*(_DWORD *)(v11 + 268) - 1) & 0xFFFFFFFD) == 0 && *(_DWORD *)(v11 + 104) == 1 )
      {
        v13 = v11;
        if ( v12 )
          v13 = v12;
        v12 = v13;
        if ( !dword_1800C995C || CompareStringA(0x7Fu, 1u, String1, -1, *(PCNZCH *)(v11 + 16), -1) == 2 )
          goto LABEL_29;
      }
      v11 = *(_QWORD *)(v11 + 8);
    }
    if ( !dword_1800C995C || !v12 )
    {
      AdaptersAddresses = 1168;
      goto LABEL_33;
    }
    v11 = v12;
LABEL_29:
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v18) = 0;
      FormatRRASErrorString(&v18, L"Selecting %d as the preferred adapter", *(unsigned int *)(v11 + 4));
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v18);
    }
    GetAdapterAddressInfoV6((struct _IP_ADAPTER_ADDRESSES_LH *)v11, a1, a3, a4, SizePointer, v17);
  }
LABEL_33:
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    LocalFree((HLOCAL)v9);
  return AdaptersAddresses;
}

```

## disassembly

```asm
0x18005a804  mov     [rsp-8+arg_8], rbx
0x18005a809  push    rbp
0x18005a80a  push    rsi
0x18005a80b  push    rdi
0x18005a80c  push    r12
0x18005a80e  push    r13
0x18005a810  push    r14
0x18005a812  push    r15
0x18005a814  lea     rbp, [rsp-750h]
0x18005a81c  sub     rsp, 850h
0x18005a823  mov     rax, cs:__security_cookie
0x18005a82a  xor     rax, rsp
0x18005a82d  mov     [rbp+780h+var_40], rax
0x18005a834  mov     rax, [rbp+780h+arg_20]
0x18005a83b  mov     r12, r8
0x18005a83e  mov     [rsp+880h+var_848], rax
0x18005a843  mov     r15, rcx
0x18005a846  xor     eax, eax
0x18005a848  lea     rcx, [rsp+880h+var_83C]; void *
0x18005a84d  xor     r14d, r14d
0x18005a850  mov     [rsp+880h+var_840], eax
0x18005a854  xor     edx, edx; Val
0x18005a856  mov     dword ptr [rsp+880h+uBytes], r14d
0x18005a85b  mov     r8d, 7FCh; Size
0x18005a861  mov     r13, r9
0x18005a864  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18005a868  call    memset_0
0x18005a86d  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18005a874  test    rdx, rdx
0x18005a877  jz      short loc_18005A8EB
0x18005a879  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005a880  lea     r8, aGetpreferredad_0; "GetPreferredAdapterInfoV6"
0x18005a887  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005a88e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a893  jmp     short loc_18005A8EB
0x18005a895  mov     edx, dword ptr [rsp+880h+uBytes]; uBytes
0x18005a899  mov     ecx, 40h ; '@'; uFlags
0x18005a89e  call    cs:__imp_LocalAlloc
0x18005a8a4  mov     rsi, rax
0x18005a8a7  test    rax, rax
0x18005a8aa  jz      short loc_18005A91A
0x18005a8ac  mov     edx, 86h; Flags
0x18005a8b1  lea     rax, [rsp+880h+uBytes]
0x18005a8b6  mov     r9, rsi; AdapterAddresses
0x18005a8b9  mov     [rsp+880h+SizePointer], rax; SizePointer
0x18005a8be  xor     r8d, r8d; Reserved
0x18005a8c1  lea     ecx, [rdx-6Fh]; Family
0x18005a8c4  call    cs:__imp_GetAdaptersAddresses
0x18005a8ca  mov     edi, eax
0x18005a8cc  cmp     eax, 6Fh ; 'o'
0x18005a8cf  jnz     short loc_18005A912
0x18005a8d1  mov     rcx, rsi; hMem
0x18005a8d4  call    cs:__imp_LocalFree
0x18005a8da  xor     ebx, ebx
0x18005a8dc  inc     r14d
0x18005a8df  mov     dword ptr [rsp+880h+uBytes], ebx
0x18005a8e3  cmp     r14d, 3
0x18005a8e7  ja      short loc_18005A915
0x18005a8e9  xor     esi, esi
0x18005a8eb  mov     edx, 86h; Flags
0x18005a8f0  lea     rax, [rsp+880h+uBytes]
0x18005a8f5  xor     r9d, r9d; AdapterAddresses
0x18005a8f8  mov     [rsp+880h+SizePointer], rax; SizePointer
0x18005a8fd  xor     r8d, r8d; Reserved
0x18005a900  lea     ecx, [rdx-6Fh]; Family
0x18005a903  call    cs:__imp_GetAdaptersAddresses
0x18005a909  mov     edi, eax
0x18005a90b  cmp     eax, 6Fh ; 'o'
0x18005a90e  jz      short loc_18005A895
0x18005a910  jmp     short loc_18005A966
0x18005a912  mov     rbx, rsi
0x18005a915  mov     rsi, rbx
0x18005a918  jmp     short loc_18005A968
0x18005a91a  call    cs:__imp_GetLastError
0x18005a920  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18005a928  mov     edi, eax
0x18005a92a  jz      short loc_18005A966
0x18005a92c  xor     eax, eax
0x18005a92e  lea     rdx, aUnableToAlloca; "Unable to allocate memory for the GetAd"...
0x18005a935  mov     r8d, edi
0x18005a938  mov     word ptr [rsp+880h+var_840], ax
0x18005a93d  lea     rcx, [rsp+880h+var_840]
0x18005a942  call    FormatRRASErrorString
0x18005a947  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005a94e  lea     r8, [rsp+880h+var_840]
0x18005a953  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005a95a  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005a961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a966  xor     ebx, ebx
0x18005a968  test    edi, edi
0x18005a96a  jz      short loc_18005A9B9
0x18005a96c  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18005a974  jz      loc_18005AA97
0x18005a97a  xor     eax, eax
0x18005a97c  lea     rdx, aGetadaptersadd_0; "GetAdaptersAddresses fails with %d\n"
0x18005a983  mov     r8d, edi
0x18005a986  mov     word ptr [rsp+880h+var_840], ax
0x18005a98b  lea     rcx, [rsp+880h+var_840]
0x18005a990  call    FormatRRASErrorString
0x18005a995  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005a99c  lea     r8, [rsp+880h+var_840]
0x18005a9a1  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005a9a8  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005a9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a9b4  jmp     loc_18005AA97
0x18005a9b9  xor     r14d, r14d
0x18005a9bc  jmp     short loc_18005AA1B
0x18005a9be  mov     eax, [rbx+10Ch]
0x18005a9c4  dec     eax
0x18005a9c6  test    eax, 0FFFFFFFDh
0x18005a9cb  jnz     short loc_18005AA17
0x18005a9cd  cmp     dword ptr [rbx+68h], 1
0x18005a9d1  jnz     short loc_18005AA17
0x18005a9d3  test    r14, r14
0x18005a9d6  mov     rax, rbx
0x18005a9d9  cmovnz  rax, r14
0x18005a9dd  cmp     cs:dword_1800C995C, 0
0x18005a9e4  mov     r14, rax
0x18005a9e7  jz      short loc_18005AA30
0x18005a9e9  mov     rax, [rbx+10h]
0x18005a9ed  lea     r8, String1; lpString1
0x18005a9f4  or      r9d, 0FFFFFFFFh; cchCount1
0x18005a9f8  mov     [rsp+880h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005aa00  mov     [rsp+880h+SizePointer], rax; struct in6_addr *
0x18005aa05  lea     edx, [r9+2]; dwCmpFlags
0x18005aa09  lea     ecx, [rdx+7Eh]; Locale
0x18005aa0c  call    cs:__imp_CompareStringA
0x18005aa12  cmp     eax, 2
0x18005aa15  jz      short loc_18005AA30
0x18005aa17  mov     rbx, [rbx+8]
0x18005aa1b  test    rbx, rbx
0x18005aa1e  jnz     short loc_18005A9BE
0x18005aa20  cmp     cs:dword_1800C995C, ebx
0x18005aa26  jz      short loc_18005AA92
0x18005aa28  test    r14, r14
0x18005aa2b  jz      short loc_18005AA92
0x18005aa2d  mov     rbx, r14
0x18005aa30  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18005aa38  jz      short loc_18005AA75
0x18005aa3a  xor     eax, eax
0x18005aa3c  lea     rdx, aSelectingDAsTh; "Selecting %d as the preferred adapter"
0x18005aa43  mov     word ptr [rsp+880h+var_840], ax
0x18005aa48  lea     rcx, [rsp+880h+var_840]
0x18005aa4d  mov     r8d, [rbx+4]
0x18005aa51  call    FormatRRASErrorString
0x18005aa56  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005aa5d  lea     r8, [rsp+880h+var_840]
0x18005aa62  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005aa69  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005aa70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aa75  mov     rax, [rsp+880h+var_848]
0x18005aa7a  mov     r9, r13; struct in6_addr *
0x18005aa7d  mov     r8, r12; struct in6_addr *
0x18005aa80  mov     qword ptr [rsp+880h+cchCount2], rax; unsigned __int8 *
0x18005aa85  mov     rdx, r15; struct in6_addr *
0x18005aa88  mov     rcx, rbx; struct _IP_ADAPTER_ADDRESSES_LH *
0x18005aa8b  call    ?GetAdapterAddressInfoV6@@YAKPEAU_IP_ADAPTER_ADDRESSES_LH@@PEAUin6_addr@@111PEAE@Z; GetAdapterAddressInfoV6(_IP_ADAPTER_ADDRESSES_LH *,in6_addr *,in6_addr *,in6_addr *,in6_addr *,uchar *)
0x18005aa90  jmp     short loc_18005AA97
0x18005aa92  mov     edi, 490h
0x18005aa97  lea     rax, [rsi-1]
0x18005aa9b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005aa9f  ja      short loc_18005AAAA
0x18005aaa1  mov     rcx, rsi; hMem
0x18005aaa4  call    cs:__imp_LocalFree
0x18005aaaa  mov     eax, edi
0x18005aaac  mov     rcx, [rbp+780h+var_40]
0x18005aab3  xor     rcx, rsp; StackCookie
0x18005aab6  call    __security_check_cookie
0x18005aabb  mov     rbx, [rsp+880h+arg_8]
0x18005aac3  add     rsp, 850h
0x18005aaca  pop     r15
0x18005aacc  pop     r14
0x18005aace  pop     r13
0x18005aad0  pop     r12
0x18005aad2  pop     rdi
0x18005aad3  pop     rsi
0x18005aad4  pop     rbp
0x18005aad5  retn
```
