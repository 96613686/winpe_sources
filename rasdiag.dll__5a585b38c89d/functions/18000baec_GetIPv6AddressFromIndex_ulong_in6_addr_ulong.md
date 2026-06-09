# GetIPv6AddressFromIndex(ulong,in6_addr *,ulong *)

- ea: `0x18000baec`
- end: `0x18000bd14`
- name: `?GetIPv6AddressFromIndex@@YAKKPEAUin6_addr@@PEAK@Z`
- size: `552`
- prototype: `__int64 __fastcall(int, struct in6_addr *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c310`

## callees

- `0x18000baec`
- `0x18000ca8c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000bb6d`
- `KERNEL32!LocalFree` at `0x18000bcf4`
- `KERNEL32!LocalFree` at `0x18000bb6d`
- `KERNEL32!LocalFree` at `0x18000bcf4`
- `KERNEL32!LocalAlloc` at `0x18000bb22`
- `KERNEL32!LocalAlloc` at `0x18000bb22`
- `KERNEL32!GetLastError` at `0x18000bbeb`
- `KERNEL32!GetLastError` at `0x18000bbeb`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18000bb57`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18000bb9c`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18000bb57`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18000bb9c`

## string_xrefs

- `0x18000bc87`: `Trying to find Link Local Address`
- `0x18000bcdd`: `FindLinkLocalIpv6Address failed with error %d`

## pseudocode

```c
__int64 __fastcall GetIPv6AddressFromIndex(int a1, struct in6_addr *a2, unsigned int *a3)
{
  unsigned int v6; // r14d
  IP_ADAPTER_ADDRESSES_LH *v7; // rbx
  IP_ADAPTER_ADDRESSES_LH *v8; // rsi
  ULONG AdaptersAddresses; // edi
  PIP_ADAPTER_UNICAST_ADDRESS_LH FirstUnicastAddress; // rcx
  _WORD *p_sa_family; // rax
  _WORD *v12; // rax
  LPSOCKADDR lpSockaddr; // rax
  ULONG uBytes[6]; // [rsp+30h] [rbp-18h] BYREF

  uBytes[0] = 0;
  v6 = 0;
  while ( 1 )
  {
    AdaptersAddresses = GetAdaptersAddresses(0x17u, 0xC6u, 0, 0, uBytes);
    RasDiagTrace("Querying GetAdaptersAddresses for the required buffer size. Buffer size required: %d", uBytes[0]);
    if ( AdaptersAddresses != 111 )
    {
      RasDiagTrace(
        "GetAdaptersAddresses call to query buffer size returns %d instead of ERROR_BUFFER_OVERFLOW",
        AdaptersAddresses);
      v7 = 0;
      v8 = 0;
      goto LABEL_7;
    }
    v7 = (IP_ADAPTER_ADDRESSES_LH *)LocalAlloc(0x40u, uBytes[0]);
    v8 = v7;
    if ( !v7 )
      break;
    AdaptersAddresses = GetAdaptersAddresses(0x17u, 0xC6u, 0, v7, uBytes);
    if ( AdaptersAddresses == 111 )
    {
      LocalFree(v7);
      v7 = 0;
      ++v6;
      uBytes[0] = 0;
      if ( v6 <= 5 )
        continue;
    }
    v8 = v7;
    goto LABEL_7;
  }
  AdaptersAddresses = GetLastError();
  RasDiagTrace("Unable to allocate memory for the GetAdaptersAddresses buffer: %d", AdaptersAddresses);
LABEL_7:
  if ( AdaptersAddresses )
  {
    RasDiagTrace("GetAdaptersAddresses fails with %d\n", AdaptersAddresses);
  }
  else if ( v7 )
  {
    while ( v7->ConnectionType != NET_IF_CONNECTION_DEDICATED
         || v7->OperStatus != IfOperStatusUp
         || v7->Ipv6IfIndex != a1 )
    {
      v7 = v7->Next;
      AdaptersAddresses = 1168;
      if ( !v7 )
        goto LABEL_29;
    }
    FirstUnicastAddress = v7->FirstUnicastAddress;
    if ( FirstUnicastAddress )
    {
      do
      {
        p_sa_family = &FirstUnicastAddress->Address.lpSockaddr->sa_family;
        if ( *p_sa_family == 23 && p_sa_family[4] != 0x80FE )
          break;
        FirstUnicastAddress = FirstUnicastAddress->Next;
      }
      while ( FirstUnicastAddress );
      if ( FirstUnicastAddress )
        goto LABEL_27;
    }
    RasDiagTrace("FindGlobalIpv6Address failed with error %d", 1168);
    RasDiagTrace("Trying to find Link Local Address");
    FirstUnicastAddress = v7->FirstUnicastAddress;
    if ( !FirstUnicastAddress )
      goto LABEL_28;
    do
    {
      v12 = &FirstUnicastAddress->Address.lpSockaddr->sa_family;
      if ( *v12 == 23 && v12[4] == 0x80FE )
        break;
      FirstUnicastAddress = FirstUnicastAddress->Next;
    }
    while ( FirstUnicastAddress );
    if ( FirstUnicastAddress )
    {
LABEL_27:
      lpSockaddr = FirstUnicastAddress->Address.lpSockaddr;
      *a3 = 128;
      AdaptersAddresses = 0;
      *a2 = *(struct in6_addr *)&lpSockaddr->sa_data[6];
    }
    else
    {
LABEL_28:
      AdaptersAddresses = 1168;
      RasDiagTrace("FindLinkLocalIpv6Address failed with error %d", 1168);
    }
  }
LABEL_29:
  if ( v8 )
    LocalFree(v8);
  return AdaptersAddresses;
}

```

## disassembly

```asm
0x18000baec  push    rbp
0x18000baee  push    rbx
0x18000baef  push    rsi
0x18000baf0  push    rdi
0x18000baf1  push    r12
0x18000baf3  push    r13
0x18000baf5  push    r14
0x18000baf7  push    r15
0x18000baf9  mov     rbp, rsp
0x18000bafc  sub     rsp, 48h
0x18000bb00  mov     r13, rdx
0x18000bb03  mov     [rbp+uBytes], 0
0x18000bb0a  mov     edx, 0C6h
0x18000bb0f  mov     r12, r8
0x18000bb12  mov     r15d, ecx
0x18000bb15  xor     r14d, r14d
0x18000bb18  jmp     short loc_18000BB89
0x18000bb1a  mov     edx, [rbp+uBytes]; uBytes
0x18000bb1d  mov     ecx, 40h ; '@'; uFlags
0x18000bb22  call    cs:__imp_LocalAlloc
0x18000bb29  nop     dword ptr [rax+rax+00h]
0x18000bb2e  mov     rbx, rax
0x18000bb31  mov     rsi, rax
0x18000bb34  test    rax, rax
0x18000bb37  jz      loc_18000BBEB
0x18000bb3d  xor     r8d, r8d; Reserved
0x18000bb40  lea     rax, [rbp+uBytes]
0x18000bb44  mov     esi, 0C6h
0x18000bb49  mov     [rsp+48h+SizePointer], rax; SizePointer
0x18000bb4e  mov     r9, rbx; AdapterAddresses
0x18000bb51  mov     edx, esi; Flags
0x18000bb53  lea     ecx, [r8+17h]; Family
0x18000bb57  call    cs:__imp_GetAdaptersAddresses
0x18000bb5e  nop     dword ptr [rax+rax+00h]
0x18000bb63  mov     edi, eax
0x18000bb65  cmp     eax, 6Fh ; 'o'
0x18000bb68  jnz     short loc_18000BBE6
0x18000bb6a  mov     rcx, rbx; hMem
0x18000bb6d  call    cs:__imp_LocalFree
0x18000bb74  nop     dword ptr [rax+rax+00h]
0x18000bb79  xor     ebx, ebx
0x18000bb7b  inc     r14d
0x18000bb7e  mov     [rbp+uBytes], ebx
0x18000bb81  cmp     r14d, 5
0x18000bb85  ja      short loc_18000BBE6
0x18000bb87  mov     edx, esi; Flags
0x18000bb89  xor     r9d, r9d; AdapterAddresses
0x18000bb8c  lea     rax, [rbp+uBytes]
0x18000bb90  xor     r8d, r8d; Reserved
0x18000bb93  mov     [rsp+48h+SizePointer], rax; SizePointer
0x18000bb98  lea     ecx, [r9+17h]; Family
0x18000bb9c  call    cs:__imp_GetAdaptersAddresses
0x18000bba3  nop     dword ptr [rax+rax+00h]
0x18000bba8  mov     edx, [rbp+uBytes]
0x18000bbab  lea     rcx, aQueryingGetada; "Querying GetAdaptersAddresses for the r"...
0x18000bbb2  mov     edi, eax
0x18000bbb4  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000bbb9  cmp     edi, 6Fh ; 'o'
0x18000bbbc  jz      loc_18000BB1A
0x18000bbc2  mov     edx, edi
0x18000bbc4  lea     rcx, aGetadaptersadd_0; "GetAdaptersAddresses call to query buff"...
0x18000bbcb  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000bbd0  xor     ebx, ebx
0x18000bbd2  xor     esi, esi
0x18000bbd4  test    edi, edi
0x18000bbd6  jz      short loc_18000BC09
0x18000bbd8  mov     edx, edi
0x18000bbda  lea     rcx, aGetadaptersadd; "GetAdaptersAddresses fails with %d\n"
0x18000bbe1  jmp     loc_18000BCE7
0x18000bbe6  mov     rsi, rbx
0x18000bbe9  jmp     short loc_18000BBD4
0x18000bbeb  call    cs:__imp_GetLastError
0x18000bbf2  nop     dword ptr [rax+rax+00h]
0x18000bbf7  mov     edx, eax
0x18000bbf9  lea     rcx, aUnableToAlloca; "Unable to allocate memory for the GetAd"...
0x18000bc00  mov     edi, eax
0x18000bc02  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000bc07  jmp     short loc_18000BBD4
0x18000bc09  test    rbx, rbx
0x18000bc0c  jz      loc_18000BCEC
0x18000bc12  mov     r14d, 490h
0x18000bc18  cmp     dword ptr [rbx+10Ch], 1
0x18000bc1f  jnz     short loc_18000BC2D
0x18000bc21  cmp     dword ptr [rbx+68h], 1
0x18000bc25  jnz     short loc_18000BC2D
0x18000bc27  cmp     [rbx+6Ch], r15d
0x18000bc2b  jz      short loc_18000BC3E
0x18000bc2d  mov     rbx, [rbx+8]
0x18000bc31  mov     edi, r14d
0x18000bc34  test    rbx, rbx
0x18000bc37  jnz     short loc_18000BC18
0x18000bc39  jmp     loc_18000BCEC
0x18000bc3e  mov     rcx, [rbx+18h]
0x18000bc42  mov     edi, 80h
0x18000bc47  mov     [rbp+arg_18], 80FEh
0x18000bc4d  lea     r15d, [rdi-69h]
0x18000bc51  test    rcx, rcx
0x18000bc54  jz      short loc_18000BC78
0x18000bc56  mov     rax, [rcx+10h]
0x18000bc5a  cmp     [rax], r15w
0x18000bc5e  jnz     short loc_18000BC6A
0x18000bc60  movzx   eax, word ptr [rax+8]
0x18000bc64  cmp     ax, [rbp+arg_18]
0x18000bc68  jnz     short loc_18000BC73
0x18000bc6a  mov     rcx, [rcx+8]
0x18000bc6e  test    rcx, rcx
0x18000bc71  jnz     short loc_18000BC56
0x18000bc73  test    rcx, rcx
0x18000bc76  jnz     short loc_18000BCC4
0x18000bc78  mov     edx, r14d
0x18000bc7b  lea     rcx, aFindglobalipv6; "FindGlobalIpv6Address failed with error"...
0x18000bc82  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000bc87  lea     rcx, aTryingToFindLi; "Trying to find Link Local Address"
0x18000bc8e  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000bc93  mov     rcx, [rbx+18h]
0x18000bc97  mov     [rbp+arg_18], 80FEh
0x18000bc9d  test    rcx, rcx
0x18000bca0  jz      short loc_18000BCDA
0x18000bca2  mov     rax, [rcx+10h]
0x18000bca6  cmp     [rax], r15w
0x18000bcaa  jnz     short loc_18000BCB6
0x18000bcac  movzx   eax, word ptr [rax+8]
0x18000bcb0  cmp     ax, [rbp+arg_18]
0x18000bcb4  jz      short loc_18000BCBF
0x18000bcb6  mov     rcx, [rcx+8]
0x18000bcba  test    rcx, rcx
0x18000bcbd  jnz     short loc_18000BCA2
0x18000bcbf  test    rcx, rcx
0x18000bcc2  jz      short loc_18000BCDA
0x18000bcc4  mov     rax, [rcx+10h]
0x18000bcc8  mov     [r12], edi
0x18000bccc  xor     edi, edi
0x18000bcce  movups  xmm0, xmmword ptr [rax+8]
0x18000bcd2  movdqu  xmmword ptr [r13+0], xmm0
0x18000bcd8  jmp     short loc_18000BCEC
0x18000bcda  mov     edi, r14d
0x18000bcdd  lea     rcx, aFindlinklocali; "FindLinkLocalIpv6Address failed with er"...
0x18000bce4  mov     edx, r14d
0x18000bce7  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000bcec  test    rsi, rsi
0x18000bcef  jz      short loc_18000BD00
0x18000bcf1  mov     rcx, rsi; hMem
0x18000bcf4  call    cs:__imp_LocalFree
0x18000bcfb  nop     dword ptr [rax+rax+00h]
0x18000bd00  mov     eax, edi
0x18000bd02  add     rsp, 48h
0x18000bd06  pop     r15
0x18000bd08  pop     r14
0x18000bd0a  pop     r13
0x18000bd0c  pop     r12
0x18000bd0e  pop     rdi
0x18000bd0f  pop     rsi
0x18000bd10  pop     rbx
0x18000bd11  pop     rbp
0x18000bd12  retn
```
