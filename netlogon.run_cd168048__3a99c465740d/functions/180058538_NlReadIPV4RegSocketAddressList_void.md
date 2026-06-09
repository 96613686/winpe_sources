# NlReadIPV4RegSocketAddressList(void)

- ea: `0x180058538`
- end: `0x18005881c`
- name: `?NlReadIPV4RegSocketAddressList@@YAXXZ`
- size: `740`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800599a4`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x180024f38`
- `0x180058538`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800585ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800585ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800587f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800587f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800585a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058621`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800585a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058621`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058802`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058802`
- `ntdll!RtlLeaveCriticalSection` at `0x1800587cc`
- `ntdll!RtlLeaveCriticalSection` at `0x1800587cc`
- `ntdll!RtlEnterCriticalSection` at `0x18005877c`
- `ntdll!RtlEnterCriticalSection` at `0x18005877c`

## string_xrefs

- `0x180058547`: `SYSTEM\CurrentControlSet\Services\Netlogon\Private`
- `0x180058569`: `Cannot NlOpenNetlogonKey to get socket address list.\n`
- `0x1800585cf`: `NlReadRegSocketAddressList: SocketAddressSize too large: %d bytes\n`
- `0x180058745`: `NlReadRegSocketAddressList: Unaligned for ULONG dereference: SocketAddress->lpSockaddr (%p) or SocketAddress->iSockaddrLength (%d)\n`
- `0x180058798`: `onecore\ds\netapi\svcdlls\logonsrv\server\srvsess.cxx`

## pseudocode

```c
void NlReadIPV4RegSocketAddressList(void)
{
  HKEY v0; // rdi
  unsigned int v1; // eax
  BYTE *v2; // rbx
  DWORD v3; // ecx
  unsigned __int64 v4; // rax
  __int64 i; // r8
  unsigned __int64 v6; // rdx
  __int64 v7; // r9
  BYTE *v8; // rax
  char *v9; // r9
  bool v10; // zf
  DWORD v11; // eax
  LPBYTE lpData; // [rsp+20h] [rbp-10h]
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  DWORD Type; // [rsp+58h] [rbp+28h] BYREF

  cbData = 0;
  Type = 0;
  v0 = NlOpenNetlogonKey("SYSTEM\\CurrentControlSet\\Services\\Netlogon\\Private");
  if ( !v0 )
  {
    NlPrintRoutine(0x100u, L"Cannot NlOpenNetlogonKey to get socket address list.\n");
    return;
  }
  cbData = 0;
  v1 = RegQueryValueExW(v0, L"SocketAddressList", 0, &Type, 0, &cbData);
  if ( v1 )
  {
    v2 = 0;
    if ( v1 != 234 )
      goto LABEL_9;
  }
  if ( cbData <= 0x32000 )
  {
    v2 = (BYTE *)LocalAlloc(0, cbData);
    if ( !v2 )
      goto LABEL_42;
    v1 = RegQueryValueExW(v0, L"SocketAddressList", 0, &Type, v2, &cbData);
    if ( !v1 )
    {
      if ( Type != 3 )
      {
        NlPrintRoutine(0x100u, L"SocketAddressList isn't REG_BINARY %ld.\n");
        goto LABEL_41;
      }
      v3 = cbData;
      if ( cbData < 8 )
      {
        NlPrintRoutine(0x100u, L"SocketAddressList is too small %ld.\n");
        goto LABEL_41;
      }
      v4 = 16LL * *(unsigned int *)v2;
      if ( v4 > 0xFFFFFFFF )
      {
        NlPrintRoutine(0x100u, L"SocketAddressList size is too big, and its address count is %ld.\n");
        goto LABEL_41;
      }
      if ( (unsigned int)v4 > (unsigned __int64)cbData - 8 )
      {
        NlPrintRoutine(0x100u, L"SocketAddressList size wrong %ld %Id.\n");
        goto LABEL_41;
      }
      for ( i = 0; (int)i < *(_DWORD *)v2; i = (unsigned int)(i + 1) )
      {
        v6 = *(_QWORD *)&v2[16 * (int)i + 8];
        if ( v6 >= v3 || (v7 = *(int *)&v2[16 * (int)i + 16], (unsigned int)v7 >= v3) || v6 + v7 > v3 )
        {
          LODWORD(lpData) = *(_DWORD *)&v2[16 * (int)i + 16];
          NlPrintRoutine(0x100u, L"SocketAddressEntry bad %ld %p %ld.\n", i, *(_QWORD *)&v2[16 * (int)i + 8], lpData);
          goto LABEL_38;
        }
        if ( (v6 & 3) != 0 || (v7 & 3) != 0 )
        {
          NlPrintRoutine(
            0x100u,
            L"NlReadRegSocketAddressList: Unaligned for ULONG dereference: SocketAddress->lpSockaddr (%p) or SocketAddress"
             "->iSockaddrLength (%d)\n",
            *(_QWORD *)&v2[16 * (int)i + 8]);
          goto LABEL_38;
        }
        v8 = &v2[v6];
        *(_QWORD *)&v2[16 * (int)i + 8] = &v2[v6];
        if ( !(_DWORD)v7 || !v8 || *(_WORD *)v8 != 2 || !*((_DWORD *)v8 + 1) )
        {
          NlPrintRoutine(0x100u, L"SocketAddressEntry bogus.\n");
          goto LABEL_38;
        }
        v3 = cbData;
      }
      RtlEnterCriticalSection(&NlGlobalTransportCritSect);
      if ( NlGlobalWinsockPnpAddresses )
        NlAssertFailed(
          "NlGlobalWinsockPnpAddresses == NULL",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\srvsess.cxx",
          0x37Au,
          v9);
      v10 = cbData == 8;
      v11 = cbData - 8;
      cbData -= 8;
      if ( !v10 )
      {
        NlGlobalWinsockPnpAddresses = v2;
        v2 = 0;
      }
      NlGlobalWinsockPnpAddressSize = v11;
      RtlLeaveCriticalSection(&NlGlobalTransportCritSect);
LABEL_38:
      if ( !v2 )
        goto LABEL_42;
LABEL_41:
      LocalFree(v2);
      goto LABEL_42;
    }
LABEL_9:
    if ( v1 != 2 )
      NlPrintRoutine(0x100u, L"Cannot RegQueryValueExW to get socket address list. %ld\n", v1);
    goto LABEL_38;
  }
  NlPrintRoutine(0x100u, L"NlReadRegSocketAddressList: SocketAddressSize too large: %d bytes\n", cbData);
LABEL_42:
  RegCloseKey(v0);
}

```

## disassembly

```asm
0x180058538  mov     [rsp-18h+arg_18], rbx
0x18005853d  push    rbp
0x18005853e  push    rsi
0x18005853f  push    rdi
0x180058540  mov     rbp, rsp
0x180058543  sub     rsp, 30h
0x180058547  lea     rcx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x18005854e  mov     [rbp+cbData], 0
0x180058555  mov     [rbp+Type], 0
0x18005855c  call    ?NlOpenNetlogonKey@@YAPEAUHKEY__@@PEAD@Z; NlOpenNetlogonKey(char *)
0x180058561  mov     rdi, rax
0x180058564  test    rax, rax
0x180058567  jnz     short loc_18005857F
0x180058569  lea     rdx, aCannotNlopenne_1; "Cannot NlOpenNetlogonKey to get socket "...
0x180058570  mov     ecx, 100h; unsigned int
0x180058575  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005857a  jmp     loc_18005880E
0x18005857f  lea     rax, [rbp+cbData]
0x180058583  mov     [rbp+cbData], 0
0x18005858a  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18005858f  lea     r9, [rbp+Type]; lpType
0x180058593  xor     r8d, r8d; lpReserved
0x180058596  mov     [rsp+30h+lpData], 0; lpData
0x18005859f  lea     rdx, aSocketaddressl_1; "SocketAddressList"
0x1800585a6  mov     rcx, rdi; hKey
0x1800585a9  call    cs:__imp_RegQueryValueExW
0x1800585b0  nop     dword ptr [rax+rax+00h]
0x1800585b5  test    eax, eax
0x1800585b7  jz      short loc_1800585C2
0x1800585b9  xor     ebx, ebx
0x1800585bb  cmp     eax, 0EAh
0x1800585c0  jnz     short loc_180058631
0x1800585c2  mov     eax, [rbp+cbData]
0x1800585c5  cmp     eax, 32000h
0x1800585ca  jbe     short loc_1800585E5
0x1800585cc  mov     r8d, eax
0x1800585cf  lea     rdx, aNlreadregsocke; "NlReadRegSocketAddressList: SocketAddre"...
0x1800585d6  mov     ecx, 100h; unsigned int
0x1800585db  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800585e0  jmp     loc_1800587FF
0x1800585e5  mov     rdx, rax; uBytes
0x1800585e8  xor     ecx, ecx; uFlags
0x1800585ea  call    cs:__imp_LocalAlloc
0x1800585f1  nop     dword ptr [rax+rax+00h]
0x1800585f6  mov     rbx, rax
0x1800585f9  test    rax, rax
0x1800585fc  jz      loc_1800587FF
0x180058602  lea     rax, [rbp+cbData]
0x180058606  xor     r8d, r8d; lpReserved
0x180058609  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18005860e  lea     r9, [rbp+Type]; lpType
0x180058612  lea     rdx, aSocketaddressl_1; "SocketAddressList"
0x180058619  mov     [rsp+30h+lpData], rbx; lpData
0x18005861e  mov     rcx, rdi; hKey
0x180058621  call    cs:__imp_RegQueryValueExW
0x180058628  nop     dword ptr [rax+rax+00h]
0x18005862d  test    eax, eax
0x18005862f  jz      short loc_180058659
0x180058631  mov     r10d, 2
0x180058637  cmp     eax, r10d
0x18005863a  jz      loc_1800587D8
0x180058640  mov     r8d, eax
0x180058643  lea     rdx, aCannotRegquery_0; "Cannot RegQueryValueExW to get socket a"...
0x18005864a  mov     ecx, 100h; unsigned int
0x18005864f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180058654  jmp     loc_1800587D8
0x180058659  mov     r8d, [rbp+Type]
0x18005865d  cmp     r8d, 3
0x180058661  jz      short loc_18005866F
0x180058663  lea     rdx, aSocketaddressl_2; "SocketAddressList isn't REG_BINARY %ld."...
0x18005866a  jmp     loc_1800587E6
0x18005866f  mov     ecx, [rbp+cbData]
0x180058672  cmp     ecx, 8
0x180058675  jnb     short loc_180058686
0x180058677  mov     r8d, ecx
0x18005867a  lea     rdx, aSocketaddressl_3; "SocketAddressList is too small %ld.\n"
0x180058681  jmp     loc_1800587E6
0x180058686  mov     r8d, [rbx]
0x180058689  mov     edx, 0FFFFFFFFh
0x18005868e  mov     eax, r8d
0x180058691  shl     rax, 4
0x180058695  cmp     rax, rdx
0x180058698  ja      loc_1800587DF
0x18005869e  mov     r8d, eax
0x1800586a1  lea     r9, [rcx-8]
0x1800586a5  cmp     r8, r9
0x1800586a8  jbe     short loc_1800586C0
0x1800586aa  lea     rdx, aSocketaddressl; "SocketAddressList size wrong %ld %Id.\n"
0x1800586b1  mov     ecx, 100h; unsigned int
0x1800586b6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800586bb  jmp     loc_1800587F0
0x1800586c0  xor     r8d, r8d
0x1800586c3  lea     r10d, [r8+2]
0x1800586c7  cmp     r8d, [rbx]
0x1800586ca  jge     loc_180058775
0x1800586d0  movsxd  r11, r8d
0x1800586d3  add     r11, r11
0x1800586d6  mov     esi, ecx
0x1800586d8  mov     rdx, [rbx+r11*8+8]
0x1800586dd  cmp     rdx, rsi
0x1800586e0  jnb     short loc_180058756
0x1800586e2  movsxd  r9, dword ptr [rbx+r11*8+10h]
0x1800586e7  cmp     r9d, ecx
0x1800586ea  jnb     short loc_180058756
0x1800586ec  lea     rax, [rdx+r9]
0x1800586f0  cmp     rax, rsi
0x1800586f3  ja      short loc_180058756
0x1800586f5  test    dl, 3
0x1800586f8  jnz     short loc_18005873D
0x1800586fa  test    r9b, 3
0x1800586fe  jnz     short loc_18005873D
0x180058700  lea     rax, [rdx+rbx]
0x180058704  mov     [rbx+r11*8+8], rax
0x180058709  test    r9d, r9d
0x18005870c  jz      short loc_180058727
0x18005870e  test    rax, rax
0x180058711  jz      short loc_180058727
0x180058713  cmp     [rax], r10w
0x180058717  jnz     short loc_180058727
0x180058719  cmp     dword ptr [rax+4], 0
0x18005871d  jz      short loc_180058727
0x18005871f  mov     ecx, [rbp+cbData]
0x180058722  inc     r8d
0x180058725  jmp     short loc_1800586C7
0x180058727  lea     rdx, aSocketaddresse_0; "SocketAddressEntry bogus.\n"
0x18005872e  mov     ecx, 100h; unsigned int
0x180058733  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180058738  jmp     loc_1800587D8
0x18005873d  mov     r8, rdx
0x180058740  mov     ecx, 100h; unsigned int
0x180058745  lea     rdx, aNlreadregsocke_0; "NlReadRegSocketAddressList: Unaligned f"...
0x18005874c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180058751  jmp     loc_1800587D8
0x180058756  mov     eax, [rbx+r11*8+10h]
0x18005875b  mov     r9, rdx
0x18005875e  lea     rdx, aSocketaddresse; "SocketAddressEntry bad %ld %p %ld.\n"
0x180058765  mov     dword ptr [rsp+30h+lpData], eax
0x180058769  mov     ecx, 100h; unsigned int
0x18005876e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180058773  jmp     short loc_1800587D8
0x180058775  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18005877c  call    cs:__imp_RtlEnterCriticalSection
0x180058783  nop     dword ptr [rax+rax+00h]
0x180058788  cmp     cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, 0; _SOCKET_ADDRESS_LIST * NlGlobalWinsockPnpAddresses
0x180058790  jz      short loc_1800587AB
0x180058792  mov     r8d, 37Ah; unsigned int
0x180058798  lea     rdx, aOnecoreDsNetap_2; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18005879f  lea     rcx, aNlglobalwinsoc; "NlGlobalWinsockPnpAddresses == NULL"
0x1800587a6  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800587ab  mov     eax, [rbp+cbData]
0x1800587ae  add     eax, 0FFFFFFF8h
0x1800587b1  mov     [rbp+cbData], eax
0x1800587b4  jz      short loc_1800587BF
0x1800587b6  mov     cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, rbx; _SOCKET_ADDRESS_LIST * NlGlobalWinsockPnpAddresses
0x1800587bd  xor     ebx, ebx
0x1800587bf  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800587c6  mov     cs:?NlGlobalWinsockPnpAddressSize@@3KA, eax; ulong NlGlobalWinsockPnpAddressSize
0x1800587cc  call    cs:__imp_RtlLeaveCriticalSection
0x1800587d3  nop     dword ptr [rax+rax+00h]
0x1800587d8  test    rbx, rbx
0x1800587db  jz      short loc_1800587FF
0x1800587dd  jmp     short loc_1800587F0
0x1800587df  lea     rdx, aSocketaddressl_0; "SocketAddressList size is too big, and "...
0x1800587e6  mov     ecx, 100h; unsigned int
0x1800587eb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800587f0  mov     rcx, rbx; hMem
0x1800587f3  call    cs:__imp_LocalFree
0x1800587fa  nop     dword ptr [rax+rax+00h]
0x1800587ff  mov     rcx, rdi; hKey
0x180058802  call    cs:__imp_RegCloseKey
0x180058809  nop     dword ptr [rax+rax+00h]
0x18005880e  mov     rbx, [rsp+30h+arg_18]
0x180058813  add     rsp, 30h
0x180058817  pop     rdi
0x180058818  pop     rsi
0x180058819  pop     rbp
0x18005881a  retn
```
