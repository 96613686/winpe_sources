# RemoveClientAddressMapping

- ea: `0x18004a1c4`
- end: `0x18004a3cf`
- name: `RemoveClientAddressMapping`
- size: `523`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800496f0`
- `0x180049958`
- `0x180049b88`
- `0x180063ed4`

## callees

- `0x180004c64`
- `0x18000d7c0`
- `0x18004a1c4`
- `0x18004a3d8`
- `0x18004b5f0`
- `0x18004c188`
- `0x1800616b4`
- `0x1800646d8`
- `0x1800647ac`
- `0x180066650`
- `0x180066714`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringW` at `0x18004a208`
- `ntdll!RtlIpv6AddressToStringW` at `0x18004a2b1`
- `ntdll!RtlIpv6AddressToStringW` at `0x18004a208`
- `ntdll!RtlIpv6AddressToStringW` at `0x18004a2b1`
- `ntdll!RtlRemoveEntryHashTable` at `0x18004a272`
- `ntdll!RtlRemoveEntryHashTable` at `0x18004a28f`
- `ntdll!RtlRemoveEntryHashTable` at `0x18004a272`
- `ntdll!RtlRemoveEntryHashTable` at `0x18004a28f`

## string_xrefs

- `0x18004a2fb`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x18004a21d`: `%s: RemoveClientAddressMapping: Deleting the mapping entry for %s`

## pseudocode

```c
__int64 __fastcall RemoveClientAddressMapping(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v3; // rdi
  __int64 v4; // rcx
  int v5; // ecx
  const wchar_t *v6; // r8
  int v7; // ecx
  int v8; // ecx
  int v10; // [rsp+28h] [rbp-160h]
  __int64 v11; // [rsp+28h] [rbp-160h]
  WCHAR S[72]; // [rsp+30h] [rbp-158h] BYREF
  WCHAR v13[72]; // [rsp+C0h] [rbp-C8h] BYREF

  v1 = *(_QWORD *)(a1 + 40);
  v3 = *(_QWORD *)(v1 + 40);
  memset_0(S, 0, 0x82u);
  RtlIpv6AddressToStringW((const struct in6_addr *)(a1 + 24), S);
  EventWrite0(
    0x10000000,
    L"%s: RemoveClientAddressMapping: Deleting the mapping entry for %s",
    *(_QWORD *)(*(_QWORD *)(v1 + 40) + 288LL) + 56LL,
    S);
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
    McTemplateU0zz_EventWriteTransfer(
      v4,
      EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_REMOVE_CLIENT_ADDRESS_MAPPING,
      *(_QWORD *)(v3 + 288) + 56LL,
      S);
  if ( (*(_DWORD *)(a1 + 16) & 0x40000000) != 0 )
  {
    RtlRemoveEntryHashTable(v3 + 184, a1, 0);
  }
  else
  {
    RtlRemoveEntryHashTable(v3 + 104, a1, 0);
    IpTlsUpdatePerfCountersForClient(v1);
  }
  v13[0] = 0;
  RtlIpv6AddressToStringW((const struct in6_addr *)(a1 + 24), v13);
  if ( (Microsoft_Windows_IphlpsvcEnableBits & 4) != 0 )
  {
    v6 = L"Unknown";
    if ( *(_QWORD *)(v1 + 112) )
      v6 = *(const wchar_t **)(v1 + 112);
    McTemplateU0zzz_EventWriteTransfer(
      v5,
      (unsigned int)EVENT_IPHLPSVC_IPHTTPS_CLIENT_DISCONNECTED,
      (_DWORD)v6,
      v1 + 124,
      (__int64)v13);
  }
  v10 = 662;
  EventWrite0(
    0x20000000,
    L"(%s: Dereference Server interface(%p) %S:%d",
    *(_QWORD *)(v3 + 288) + 56LL,
    v3,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
    v10);
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      v7,
      (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_DEREFERENCE,
      v3,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      150);
  DereferenceServerInterfaceEx(v3);
  LODWORD(v11) = 663;
  EventWrite0(
    0x20000000,
    L"(%s: Dereference client context (%p) %S:%d",
    *(_QWORD *)(*(_QWORD *)(v1 + 40) + 288LL) + 56LL,
    v1,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
    v11);
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
    McTemplateU0psq_EventWriteTransfer(
      v8,
      (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE,
      v1,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      151);
  DereferenceClientContextEx(v1);
  return FREE(a1);
}

```

## disassembly

```asm
0x18004a1c4  push    rbx
0x18004a1c6  push    rbp
0x18004a1c7  push    rsi
0x18004a1c8  push    rdi
0x18004a1c9  sub     rsp, 168h
0x18004a1d0  mov     rax, cs:__security_cookie
0x18004a1d7  xor     rax, rsp
0x18004a1da  mov     [rsp+188h+var_38], rax
0x18004a1e2  mov     rbx, [rcx+28h]
0x18004a1e6  mov     rsi, rcx
0x18004a1e9  xor     edx, edx; Val
0x18004a1eb  lea     rcx, [rsp+188h+S]; void *
0x18004a1f0  mov     r8d, 82h; Size
0x18004a1f6  mov     rdi, [rbx+28h]
0x18004a1fa  call    memset_0
0x18004a1ff  lea     rdx, [rsp+188h+S]; S
0x18004a204  lea     rcx, [rsi+18h]; Addr
0x18004a208  call    cs:__imp_RtlIpv6AddressToStringW
0x18004a20f  nop     dword ptr [rax+rax+00h]
0x18004a214  mov     rax, [rbx+28h]
0x18004a218  lea     r9, [rsp+188h+S]
0x18004a21d  lea     rdx, aSRemoveclienta; "%s: RemoveClientAddressMapping: Deletin"...
0x18004a224  mov     ecx, 10000000h
0x18004a229  mov     r8, [rax+120h]
0x18004a230  add     r8, 38h ; '8'
0x18004a234  call    EventWrite0
0x18004a239  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18004a240  jz      short loc_18004A25E
0x18004a242  mov     r8, [rdi+120h]
0x18004a249  lea     r9, [rsp+188h+S]
0x18004a24e  add     r8, 38h ; '8'
0x18004a252  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_REMOVE_CLIENT_ADDRESS_MAPPING
0x18004a259  call    McTemplateU0zz_EventWriteTransfer
0x18004a25e  mov     eax, [rsi+10h]
0x18004a261  xor     r8d, r8d
0x18004a264  mov     rdx, rsi
0x18004a267  bt      rax, 1Eh
0x18004a26c  jb      short loc_18004A288
0x18004a26e  lea     rcx, [rdi+68h]
0x18004a272  call    cs:__imp_RtlRemoveEntryHashTable
0x18004a279  nop     dword ptr [rax+rax+00h]
0x18004a27e  mov     rcx, rbx
0x18004a281  call    IpTlsUpdatePerfCountersForClient
0x18004a286  jmp     short loc_18004A29B
0x18004a288  lea     rcx, [rdi+0B8h]
0x18004a28f  call    cs:__imp_RtlRemoveEntryHashTable
0x18004a296  nop     dword ptr [rax+rax+00h]
0x18004a29b  xor     eax, eax
0x18004a29d  lea     rdx, [rsp+188h+var_C8]; S
0x18004a2a5  lea     rcx, [rsi+18h]; Addr
0x18004a2a9  mov     [rsp+188h+var_C8], ax
0x18004a2b1  call    cs:__imp_RtlIpv6AddressToStringW
0x18004a2b8  nop     dword ptr [rax+rax+00h]
0x18004a2bd  test    cs:Microsoft_Windows_IphlpsvcEnableBits, 4
0x18004a2c4  jz      short loc_18004A2F4
0x18004a2c6  cmp     qword ptr [rbx+70h], 0
0x18004a2cb  lea     rax, [rsp+188h+var_C8]
0x18004a2d3  lea     r8, aUnknown; "Unknown"
0x18004a2da  mov     [rsp+188h+var_168], rax
0x18004a2df  cmovnz  r8, [rbx+70h]
0x18004a2e4  lea     r9, [rbx+7Ch]
0x18004a2e8  lea     rdx, EVENT_IPHLPSVC_IPHTTPS_CLIENT_DISCONNECTED
0x18004a2ef  call    McTemplateU0zzz_EventWriteTransfer
0x18004a2f4  mov     r8, [rdi+120h]
0x18004a2fb  lea     rbp, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18004a302  add     r8, 38h ; '8'
0x18004a306  mov     dword ptr [rsp+188h+var_160], 296h
0x18004a30e  mov     r9, rdi
0x18004a311  mov     [rsp+188h+var_168], rbp
0x18004a316  lea     rdx, aSDereferenceSe; "(%s: Dereference Server interface(%p) %"...
0x18004a31d  mov     ecx, 20000000h
0x18004a322  call    EventWrite0
0x18004a327  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18004a32e  jz      short loc_18004A34A
0x18004a330  mov     r9, rbp
0x18004a333  mov     dword ptr [rsp+188h+var_168], 296h
0x18004a33b  mov     r8, rdi
0x18004a33e  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_DEREFERENCE
0x18004a345  call    McTemplateU0psq_EventWriteTransfer
0x18004a34a  mov     rcx, rdi
0x18004a34d  call    DereferenceServerInterfaceEx
0x18004a352  mov     rax, [rbx+28h]
0x18004a356  lea     rdx, aSDereferenceCl; "(%s: Dereference client context (%p) %S"...
0x18004a35d  mov     edi, 297h
0x18004a362  mov     r9, rbx
0x18004a365  mov     dword ptr [rsp+188h+var_160], edi
0x18004a369  mov     ecx, 20000000h
0x18004a36e  mov     [rsp+188h+var_168], rbp
0x18004a373  mov     r8, [rax+120h]
0x18004a37a  add     r8, 38h ; '8'
0x18004a37e  call    EventWrite0
0x18004a383  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18004a38a  jz      short loc_18004A3A2
0x18004a38c  mov     r9, rbp
0x18004a38f  mov     dword ptr [rsp+188h+var_168], edi
0x18004a393  mov     r8, rbx
0x18004a396  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE
0x18004a39d  call    McTemplateU0psq_EventWriteTransfer
0x18004a3a2  mov     rcx, rbx
0x18004a3a5  call    DereferenceClientContextEx
0x18004a3aa  mov     rcx, rsi
0x18004a3ad  call    FREE
0x18004a3b2  mov     rcx, [rsp+188h+var_38]
0x18004a3ba  xor     rcx, rsp; StackCookie
0x18004a3bd  call    __security_check_cookie
0x18004a3c2  add     rsp, 168h
0x18004a3c9  pop     rdi
0x18004a3ca  pop     rsi
0x18004a3cb  pop     rbp
0x18004a3cc  pop     rbx
0x18004a3cd  retn
```
