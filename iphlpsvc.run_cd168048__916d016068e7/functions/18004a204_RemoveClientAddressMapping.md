# RemoveClientAddressMapping

- ea: `0x18004a204`
- end: `0x18004a40f`
- name: `RemoveClientAddressMapping`
- size: `523`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180049730`
- `0x180049998`
- `0x180049bc8`
- `0x180063eb4`

## callees

- `0x180004c54`
- `0x18000d7b0`
- `0x18004a204`
- `0x18004a418`
- `0x18004b630`
- `0x18004c1c8`
- `0x180061694`
- `0x1800646b8`
- `0x18006478c`
- `0x180066630`
- `0x1800666f4`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringW` at `0x18004a248`
- `ntdll!RtlIpv6AddressToStringW` at `0x18004a2f1`
- `ntdll!RtlIpv6AddressToStringW` at `0x18004a248`
- `ntdll!RtlIpv6AddressToStringW` at `0x18004a2f1`
- `ntdll!RtlRemoveEntryHashTable` at `0x18004a2b2`
- `ntdll!RtlRemoveEntryHashTable` at `0x18004a2cf`
- `ntdll!RtlRemoveEntryHashTable` at `0x18004a2b2`
- `ntdll!RtlRemoveEntryHashTable` at `0x18004a2cf`

## string_xrefs

- `0x18004a33b`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x18004a25d`: `%s: RemoveClientAddressMapping: Deleting the mapping entry for %s`

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
0x18004a204  push    rbx
0x18004a206  push    rbp
0x18004a207  push    rsi
0x18004a208  push    rdi
0x18004a209  sub     rsp, 168h
0x18004a210  mov     rax, cs:__security_cookie
0x18004a217  xor     rax, rsp
0x18004a21a  mov     [rsp+188h+var_38], rax
0x18004a222  mov     rbx, [rcx+28h]
0x18004a226  mov     rsi, rcx
0x18004a229  xor     edx, edx; Val
0x18004a22b  lea     rcx, [rsp+188h+S]; void *
0x18004a230  mov     r8d, 82h; Size
0x18004a236  mov     rdi, [rbx+28h]
0x18004a23a  call    memset_0
0x18004a23f  lea     rdx, [rsp+188h+S]; S
0x18004a244  lea     rcx, [rsi+18h]; Addr
0x18004a248  call    cs:__imp_RtlIpv6AddressToStringW
0x18004a24f  nop     dword ptr [rax+rax+00h]
0x18004a254  mov     rax, [rbx+28h]
0x18004a258  lea     r9, [rsp+188h+S]
0x18004a25d  lea     rdx, aSRemoveclienta; "%s: RemoveClientAddressMapping: Deletin"...
0x18004a264  mov     ecx, 10000000h
0x18004a269  mov     r8, [rax+120h]
0x18004a270  add     r8, 38h ; '8'
0x18004a274  call    EventWrite0
0x18004a279  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18004a280  jz      short loc_18004A29E
0x18004a282  mov     r8, [rdi+120h]
0x18004a289  lea     r9, [rsp+188h+S]
0x18004a28e  add     r8, 38h ; '8'
0x18004a292  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_REMOVE_CLIENT_ADDRESS_MAPPING
0x18004a299  call    McTemplateU0zz_EventWriteTransfer
0x18004a29e  mov     eax, [rsi+10h]
0x18004a2a1  xor     r8d, r8d
0x18004a2a4  mov     rdx, rsi
0x18004a2a7  bt      rax, 1Eh
0x18004a2ac  jb      short loc_18004A2C8
0x18004a2ae  lea     rcx, [rdi+68h]
0x18004a2b2  call    cs:__imp_RtlRemoveEntryHashTable
0x18004a2b9  nop     dword ptr [rax+rax+00h]
0x18004a2be  mov     rcx, rbx
0x18004a2c1  call    IpTlsUpdatePerfCountersForClient
0x18004a2c6  jmp     short loc_18004A2DB
0x18004a2c8  lea     rcx, [rdi+0B8h]
0x18004a2cf  call    cs:__imp_RtlRemoveEntryHashTable
0x18004a2d6  nop     dword ptr [rax+rax+00h]
0x18004a2db  xor     eax, eax
0x18004a2dd  lea     rdx, [rsp+188h+var_C8]; S
0x18004a2e5  lea     rcx, [rsi+18h]; Addr
0x18004a2e9  mov     [rsp+188h+var_C8], ax
0x18004a2f1  call    cs:__imp_RtlIpv6AddressToStringW
0x18004a2f8  nop     dword ptr [rax+rax+00h]
0x18004a2fd  test    cs:Microsoft_Windows_IphlpsvcEnableBits, 4
0x18004a304  jz      short loc_18004A334
0x18004a306  cmp     qword ptr [rbx+70h], 0
0x18004a30b  lea     rax, [rsp+188h+var_C8]
0x18004a313  lea     r8, aUnknown; "Unknown"
0x18004a31a  mov     [rsp+188h+var_168], rax
0x18004a31f  cmovnz  r8, [rbx+70h]
0x18004a324  lea     r9, [rbx+7Ch]
0x18004a328  lea     rdx, EVENT_IPHLPSVC_IPHTTPS_CLIENT_DISCONNECTED
0x18004a32f  call    McTemplateU0zzz_EventWriteTransfer
0x18004a334  mov     r8, [rdi+120h]
0x18004a33b  lea     rbp, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18004a342  add     r8, 38h ; '8'
0x18004a346  mov     dword ptr [rsp+188h+var_160], 296h
0x18004a34e  mov     r9, rdi
0x18004a351  mov     [rsp+188h+var_168], rbp
0x18004a356  lea     rdx, aSDereferenceSe; "(%s: Dereference Server interface(%p) %"...
0x18004a35d  mov     ecx, 20000000h
0x18004a362  call    EventWrite0
0x18004a367  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18004a36e  jz      short loc_18004A38A
0x18004a370  mov     r9, rbp
0x18004a373  mov     dword ptr [rsp+188h+var_168], 296h
0x18004a37b  mov     r8, rdi
0x18004a37e  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_INTERFACE_DEREFERENCE
0x18004a385  call    McTemplateU0psq_EventWriteTransfer
0x18004a38a  mov     rcx, rdi
0x18004a38d  call    DereferenceServerInterfaceEx
0x18004a392  mov     rax, [rbx+28h]
0x18004a396  lea     rdx, aSDereferenceCl; "(%s: Dereference client context (%p) %S"...
0x18004a39d  mov     edi, 297h
0x18004a3a2  mov     r9, rbx
0x18004a3a5  mov     dword ptr [rsp+188h+var_160], edi
0x18004a3a9  mov     ecx, 20000000h
0x18004a3ae  mov     [rsp+188h+var_168], rbp
0x18004a3b3  mov     r8, [rax+120h]
0x18004a3ba  add     r8, 38h ; '8'
0x18004a3be  call    EventWrite0
0x18004a3c3  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18004a3ca  jz      short loc_18004A3E2
0x18004a3cc  mov     r9, rbp
0x18004a3cf  mov     dword ptr [rsp+188h+var_168], edi
0x18004a3d3  mov     r8, rbx
0x18004a3d6  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE
0x18004a3dd  call    McTemplateU0psq_EventWriteTransfer
0x18004a3e2  mov     rcx, rbx
0x18004a3e5  call    DereferenceClientContextEx
0x18004a3ea  mov     rcx, rsi
0x18004a3ed  call    FREE
0x18004a3f2  mov     rcx, [rsp+188h+var_38]
0x18004a3fa  xor     rcx, rsp; StackCookie
0x18004a3fd  call    __security_check_cookie
0x18004a402  add     rsp, 168h
0x18004a409  pop     rdi
0x18004a40a  pop     rsi
0x18004a40b  pop     rbp
0x18004a40c  pop     rbx
0x18004a40d  retn
```
