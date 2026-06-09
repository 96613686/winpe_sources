# GetPreferredAdapterInfoV6(in6_addr *,in6_addr *,in6_addr *,in6_addr *,uchar *)

- ea: `0x18005c7ac`
- end: `0x18005cac3`
- name: `?GetPreferredAdapterInfoV6@@YAKPEAUin6_addr@@000PEAE@Z`
- size: `791`
- prototype: `unsigned int __usercall@<eax>(struct in6_addr *@<rcx>, struct in6_addr *@<rdx>, struct in6_addr *@<r8>, struct in6_addr *@<r9>, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180057e90`
- `0x18005ccac`
- `0x18005cff4`

## callees

- `0x18005c5c4`
- `0x18005c7ac`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18005c89d`
- `KERNEL32!LocalFree` at `0x18005ca8a`
- `KERNEL32!LocalFree` at `0x18005c89d`
- `KERNEL32!LocalFree` at `0x18005ca8a`
- `KERNEL32!CompareStringA` at `0x18005c9eb`
- `KERNEL32!CompareStringA` at `0x18005c9eb`
- `KERNEL32!GetLastError` at `0x18005c948`
- `KERNEL32!GetLastError` at `0x18005c948`
- `KERNEL32!LocalAlloc` at `0x18005c850`
- `KERNEL32!LocalAlloc` at `0x18005c850`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18005c883`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18005c8d6`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18005c883`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18005c8d6`

## pseudocode

```c
__int64 __fastcall GetPreferredAdapterInfoV6(
        struct in6_addr *a1,
        struct in6_addr *a2,
        struct in6_addr *a3,
        struct in6_addr *a4,
        unsigned __int8 *a5)
{
  IP_ADAPTER_ADDRESSES_LH *v7; // rbx
  IP_ADAPTER_ADDRESSES_LH *v8; // r14
  __int64 v9; // rsi
  unsigned int i; // r15d
  IP_ADAPTER_ADDRESSES_LH *v11; // rax
  ULONG AdaptersAddresses; // edi
  DWORD LastError; // eax
  IP_ADAPTER_ADDRESSES_LH *v14; // rax
  struct in6_addr *SizePointer; // [rsp+20h] [rbp-E0h]
  SIZE_T uBytes; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 *v18; // [rsp+38h] [rbp-C8h]
  struct in6_addr *v19; // [rsp+40h] [rbp-C0h]
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  char v21[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v18 = a5;
  v7 = 0;
  v19 = a4;
  LODWORD(uBytes) = 0;
  v20 = 0;
  v8 = 0;
  v9 = -1;
  memset_0(v21, 0, sizeof(v21));
  if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800D0740 + 1),
      L"GetPreferredAdapterInfoV6");
  for ( i = 1; ; ++i )
  {
    AdaptersAddresses = GetAdaptersAddresses(0x17u, 0x86u, 0, 0, (PULONG)&uBytes);
    if ( AdaptersAddresses != 111 )
      break;
    v11 = (IP_ADAPTER_ADDRESSES_LH *)LocalAlloc(0x40u, (unsigned int)uBytes);
    v9 = (__int64)v11;
    if ( !v11 )
    {
      LastError = GetLastError();
      AdaptersAddresses = LastError;
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, L"Unable to allocate memory for the GetAdaptersAddresses buffer: %d", LastError);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v20);
      }
      break;
    }
    v7 = v11;
    AdaptersAddresses = GetAdaptersAddresses(0x17u, 0x86u, 0, v11, (PULONG)&uBytes);
    if ( AdaptersAddresses != 111 || (LocalFree(v7), v7 = 0, LODWORD(uBytes) = 0, i > 3) )
    {
      v9 = (__int64)v7;
      break;
    }
    v9 = 0;
  }
  if ( AdaptersAddresses )
  {
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v20) = 0;
      FormatRRASErrorString(&v20, L"GetAdaptersAddresses fails with %d\n", AdaptersAddresses);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v20);
    }
  }
  else
  {
    while ( v7 )
    {
      if ( ((v7->ConnectionType - 1) & 0xFFFFFFFD) == 0 && v7->OperStatus == IfOperStatusUp )
      {
        v14 = v7;
        if ( v8 )
          v14 = v8;
        v8 = v14;
        if ( !dword_1800D095C || CompareStringA(0x7Fu, 1u, String1, -1, v7->AdapterName, -1) == 2 )
          goto LABEL_26;
      }
      v7 = v7->Next;
    }
    if ( !dword_1800D095C || !v8 )
    {
      AdaptersAddresses = 1168;
      goto LABEL_30;
    }
    v7 = v8;
LABEL_26:
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v20) = 0;
      FormatRRASErrorString(&v20, L"Selecting %d as the preferred adapter", v7->IfIndex);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v20);
    }
    GetAdapterAddressInfoV6(v7, a1, a3, v19, SizePointer, v18);
  }
LABEL_30:
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    LocalFree((HLOCAL)v9);
  return AdaptersAddresses;
}

```

## disassembly

```asm
0x18005c7ac  mov     [rsp-8+arg_8], rbx
0x18005c7b1  push    rbp
0x18005c7b2  push    rsi
0x18005c7b3  push    rdi
0x18005c7b4  push    r12
0x18005c7b6  push    r13
0x18005c7b8  push    r14
0x18005c7ba  push    r15
0x18005c7bc  lea     rbp, [rsp-760h]
0x18005c7c4  sub     rsp, 860h
0x18005c7cb  mov     rax, cs:__security_cookie
0x18005c7d2  xor     rax, rsp
0x18005c7d5  mov     [rbp+790h+var_40], rax
0x18005c7dc  mov     rax, [rbp+790h+arg_20]
0x18005c7e3  mov     r13, r8
0x18005c7e6  mov     r12, rcx
0x18005c7e9  mov     [rsp+890h+var_858], rax
0x18005c7ee  xor     ebx, ebx
0x18005c7f0  mov     [rsp+890h+var_850], r9
0x18005c7f5  and     dword ptr [rsp+890h+uBytes], ebx
0x18005c7f9  lea     rcx, [rsp+890h+var_83C]; void *
0x18005c7fe  and     [rsp+890h+var_840], ebx
0x18005c802  mov     r8d, 7FCh; Size
0x18005c808  xor     edx, edx; Val
0x18005c80a  xor     r14d, r14d
0x18005c80d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18005c811  call    memset_0
0x18005c816  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18005c81d  test    rdx, rdx
0x18005c820  jz      short loc_18005C83C
0x18005c822  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005c829  lea     r8, aGetpreferredad_0; "GetPreferredAdapterInfoV6"
0x18005c830  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005c837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c83c  mov     r15d, 1
0x18005c842  xor     r9d, r9d
0x18005c845  jmp     short loc_18005C8C1
0x18005c847  mov     edx, dword ptr [rsp+890h+uBytes]; uBytes
0x18005c84b  mov     ecx, 40h ; '@'; uFlags
0x18005c850  call    cs:__imp_LocalAlloc
0x18005c857  nop     dword ptr [rax+rax+00h]
0x18005c85c  mov     rsi, rax
0x18005c85f  test    rax, rax
0x18005c862  jz      loc_18005C948
0x18005c868  mov     rbx, rax
0x18005c86b  mov     edx, 86h; Flags
0x18005c870  lea     rax, [rsp+890h+uBytes]
0x18005c875  mov     r9, rbx; AdapterAddresses
0x18005c878  xor     r8d, r8d; Reserved
0x18005c87b  mov     [rsp+890h+SizePointer], rax; SizePointer
0x18005c880  lea     ecx, [rdx-6Fh]; Family
0x18005c883  call    cs:__imp_GetAdaptersAddresses
0x18005c88a  nop     dword ptr [rax+rax+00h]
0x18005c88f  mov     edi, eax
0x18005c891  cmp     eax, 6Fh ; 'o'
0x18005c894  jnz     loc_18005C943
0x18005c89a  mov     rcx, rbx; hMem
0x18005c89d  call    cs:__imp_LocalFree
0x18005c8a4  nop     dword ptr [rax+rax+00h]
0x18005c8a9  xor     ebx, ebx
0x18005c8ab  and     dword ptr [rsp+890h+uBytes], ebx
0x18005c8af  cmp     r15d, 3
0x18005c8b3  ja      loc_18005C943
0x18005c8b9  mov     esi, ebx
0x18005c8bb  inc     r15d
0x18005c8be  mov     r9d, ebx; AdapterAddresses
0x18005c8c1  mov     edx, 86h; Flags
0x18005c8c6  lea     rax, [rsp+890h+uBytes]
0x18005c8cb  xor     r8d, r8d; Reserved
0x18005c8ce  mov     [rsp+890h+SizePointer], rax; SizePointer
0x18005c8d3  lea     ecx, [rdx-6Fh]; Family
0x18005c8d6  call    cs:__imp_GetAdaptersAddresses
0x18005c8dd  nop     dword ptr [rax+rax+00h]
0x18005c8e2  mov     edi, eax
0x18005c8e4  cmp     eax, 6Fh ; 'o'
0x18005c8e7  jz      loc_18005C847
0x18005c8ed  xor     r15d, r15d
0x18005c8f0  test    edi, edi
0x18005c8f2  jz      loc_18005CA00
0x18005c8f8  cmp     qword ptr cs:xmmword_1800D0740, r15
0x18005c8ff  jz      loc_18005CA7D
0x18005c905  mov     r8d, edi
0x18005c908  mov     word ptr [rsp+890h+var_840], r15w
0x18005c90e  lea     rdx, aGetadaptersadd_0; "GetAdaptersAddresses fails with %d\n"
0x18005c915  lea     rcx, [rsp+890h+var_840]
0x18005c91a  call    FormatRRASErrorString
0x18005c91f  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005c926  lea     r8, [rsp+890h+var_840]
0x18005c92b  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005c932  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005c939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c93e  jmp     loc_18005CA7D
0x18005c943  mov     rsi, rbx
0x18005c946  jmp     short loc_18005C8ED
0x18005c948  call    cs:__imp_GetLastError
0x18005c94f  nop     dword ptr [rax+rax+00h]
0x18005c954  xor     r15d, r15d
0x18005c957  mov     edi, eax
0x18005c959  cmp     qword ptr cs:xmmword_1800D0740, r15
0x18005c960  jz      short loc_18005C8F0
0x18005c962  mov     r8d, eax
0x18005c965  mov     word ptr [rsp+890h+var_840], r15w
0x18005c96b  lea     rdx, aUnableToAlloca; "Unable to allocate memory for the GetAd"...
0x18005c972  lea     rcx, [rsp+890h+var_840]
0x18005c977  call    FormatRRASErrorString
0x18005c97c  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005c983  lea     r8, [rsp+890h+var_840]
0x18005c988  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005c98f  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005c996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c99b  jmp     loc_18005C8F0
0x18005c9a0  mov     eax, [rbx+10Ch]
0x18005c9a6  dec     eax
0x18005c9a8  test    eax, 0FFFFFFFDh
0x18005c9ad  jnz     short loc_18005C9FC
0x18005c9af  cmp     dword ptr [rbx+68h], 1
0x18005c9b3  jnz     short loc_18005C9FC
0x18005c9b5  test    r14, r14
0x18005c9b8  mov     rax, rbx
0x18005c9bb  cmovnz  rax, r14
0x18005c9bf  cmp     cs:dword_1800D095C, r15d
0x18005c9c6  mov     r14, rax
0x18005c9c9  jz      short loc_18005CA16
0x18005c9cb  mov     rax, [rbx+10h]
0x18005c9cf  lea     r8, String1; lpString1
0x18005c9d6  or      dword ptr [rsp+890h+var_868], 0FFFFFFFFh
0x18005c9db  or      r9d, 0FFFFFFFFh; cchCount1
0x18005c9df  mov     [rsp+890h+SizePointer], rax; struct in6_addr *
0x18005c9e4  lea     edx, [r9+2]; dwCmpFlags
0x18005c9e8  lea     ecx, [rdx+7Eh]; Locale
0x18005c9eb  call    cs:__imp_CompareStringA
0x18005c9f2  nop     dword ptr [rax+rax+00h]
0x18005c9f7  cmp     eax, 2
0x18005c9fa  jz      short loc_18005CA16
0x18005c9fc  mov     rbx, [rbx+8]
0x18005ca00  test    rbx, rbx
0x18005ca03  jnz     short loc_18005C9A0
0x18005ca05  cmp     cs:dword_1800D095C, r15d
0x18005ca0c  jz      short loc_18005CA78
0x18005ca0e  test    r14, r14
0x18005ca11  jz      short loc_18005CA78
0x18005ca13  mov     rbx, r14
0x18005ca16  cmp     qword ptr cs:xmmword_1800D0740, r15
0x18005ca1d  jz      short loc_18005CA59
0x18005ca1f  mov     word ptr [rsp+890h+var_840], r15w
0x18005ca25  lea     rdx, aSelectingDAsTh; "Selecting %d as the preferred adapter"
0x18005ca2c  mov     r8d, [rbx+4]
0x18005ca30  lea     rcx, [rsp+890h+var_840]
0x18005ca35  call    FormatRRASErrorString
0x18005ca3a  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005ca41  lea     r8, [rsp+890h+var_840]
0x18005ca46  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005ca4d  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005ca54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca59  mov     rax, [rsp+890h+var_858]
0x18005ca5e  mov     r8, r13; struct in6_addr *
0x18005ca61  mov     r9, [rsp+890h+var_850]; struct in6_addr *
0x18005ca66  mov     rdx, r12; struct in6_addr *
0x18005ca69  mov     rcx, rbx; struct _IP_ADAPTER_ADDRESSES_LH *
0x18005ca6c  mov     [rsp+890h+var_868], rax; unsigned __int8 *
0x18005ca71  call    ?GetAdapterAddressInfoV6@@YAKPEAU_IP_ADAPTER_ADDRESSES_LH@@PEAUin6_addr@@111PEAE@Z; GetAdapterAddressInfoV6(_IP_ADAPTER_ADDRESSES_LH *,in6_addr *,in6_addr *,in6_addr *,in6_addr *,uchar *)
0x18005ca76  jmp     short loc_18005CA7D
0x18005ca78  mov     edi, 490h
0x18005ca7d  lea     rax, [rsi-1]
0x18005ca81  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005ca85  ja      short loc_18005CA96
0x18005ca87  mov     rcx, rsi; hMem
0x18005ca8a  call    cs:__imp_LocalFree
0x18005ca91  nop     dword ptr [rax+rax+00h]
0x18005ca96  mov     eax, edi
0x18005ca98  mov     rcx, [rbp+790h+var_40]
0x18005ca9f  xor     rcx, rsp; StackCookie
0x18005caa2  call    __security_check_cookie
0x18005caa7  mov     rbx, [rsp+890h+arg_8]
0x18005caaf  add     rsp, 860h
0x18005cab6  pop     r15
0x18005cab8  pop     r14
0x18005caba  pop     r13
0x18005cabc  pop     r12
0x18005cabe  pop     rdi
0x18005cabf  pop     rsi
0x18005cac0  pop     rbp
0x18005cac1  retn
```
