# NlReadIPV4RegSocketAddressList(void)

- ea: `0x180054a4c`
- end: `0x180054d02`
- name: `?NlReadIPV4RegSocketAddressList@@YAXXZ`
- size: `694`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180055c9c`

## callees

- `0x180007278`
- `0x18000d710`
- `0x180023eb0`
- `0x180054a4c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180054af8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180054af8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054ce6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054ce6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180054abd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180054b29`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180054abd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180054b29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054cef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054cef`
- `ntdll!RtlLeaveCriticalSection` at `0x180054cc5`
- `ntdll!RtlLeaveCriticalSection` at `0x180054cc5`
- `ntdll!RtlEnterCriticalSection` at `0x180054c7b`
- `ntdll!RtlEnterCriticalSection` at `0x180054c7b`

## string_xrefs

- `0x180054a5b`: `SYSTEM\CurrentControlSet\Services\Netlogon\Private`
- `0x180054a7d`: `Cannot NlOpenNetlogonKey to get socket address list.\n`
- `0x180054add`: `NlReadRegSocketAddressList: SocketAddressSize too large: %d bytes\n`
- `0x180054c47`: `NlReadRegSocketAddressList: Unaligned for ULONG dereference: SocketAddress->lpSockaddr (%p) or SocketAddress->iSockaddrLength (%d)\n`
- `0x180054c91`: `onecore\ds\netapi\svcdlls\logonsrv\server\srvsess.cxx`

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
          890,
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
0x180054a4c  mov     [rsp-18h+arg_18], rbx
0x180054a51  push    rbp
0x180054a52  push    rsi
0x180054a53  push    rdi
0x180054a54  mov     rbp, rsp
0x180054a57  sub     rsp, 30h
0x180054a5b  lea     rcx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x180054a62  mov     [rbp+cbData], 0
0x180054a69  mov     [rbp+Type], 0
0x180054a70  call    ?NlOpenNetlogonKey@@YAPEAUHKEY__@@PEAD@Z; NlOpenNetlogonKey(char *)
0x180054a75  mov     rdi, rax
0x180054a78  test    rax, rax
0x180054a7b  jnz     short loc_180054A93
0x180054a7d  lea     rdx, aCannotNlopenne_1; "Cannot NlOpenNetlogonKey to get socket "...
0x180054a84  mov     ecx, 100h; unsigned int
0x180054a89  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054a8e  jmp     loc_180054CF5
0x180054a93  lea     rax, [rbp+cbData]
0x180054a97  mov     [rbp+cbData], 0
0x180054a9e  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180054aa3  lea     r9, [rbp+Type]; lpType
0x180054aa7  xor     r8d, r8d; lpReserved
0x180054aaa  mov     [rsp+30h+lpData], 0; lpData
0x180054ab3  lea     rdx, aSocketaddressl_1; "SocketAddressList"
0x180054aba  mov     rcx, rdi; hKey
0x180054abd  call    cs:__imp_RegQueryValueExW
0x180054ac3  test    eax, eax
0x180054ac5  jz      short loc_180054AD0
0x180054ac7  xor     ebx, ebx
0x180054ac9  cmp     eax, 0EAh
0x180054ace  jnz     short loc_180054B33
0x180054ad0  mov     eax, [rbp+cbData]
0x180054ad3  cmp     eax, 32000h
0x180054ad8  jbe     short loc_180054AF3
0x180054ada  mov     r8d, eax
0x180054add  lea     rdx, aNlreadregsocke; "NlReadRegSocketAddressList: SocketAddre"...
0x180054ae4  mov     ecx, 100h; unsigned int
0x180054ae9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054aee  jmp     loc_180054CEC
0x180054af3  mov     rdx, rax; uBytes
0x180054af6  xor     ecx, ecx; uFlags
0x180054af8  call    cs:__imp_LocalAlloc
0x180054afe  mov     rbx, rax
0x180054b01  test    rax, rax
0x180054b04  jz      loc_180054CEC
0x180054b0a  lea     rax, [rbp+cbData]
0x180054b0e  xor     r8d, r8d; lpReserved
0x180054b11  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180054b16  lea     r9, [rbp+Type]; lpType
0x180054b1a  lea     rdx, aSocketaddressl_1; "SocketAddressList"
0x180054b21  mov     [rsp+30h+lpData], rbx; lpData
0x180054b26  mov     rcx, rdi; hKey
0x180054b29  call    cs:__imp_RegQueryValueExW
0x180054b2f  test    eax, eax
0x180054b31  jz      short loc_180054B5B
0x180054b33  mov     r10d, 2
0x180054b39  cmp     eax, r10d
0x180054b3c  jz      loc_180054CCB
0x180054b42  mov     r8d, eax
0x180054b45  lea     rdx, aCannotRegquery_0; "Cannot RegQueryValueExW to get socket a"...
0x180054b4c  mov     ecx, 100h; unsigned int
0x180054b51  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054b56  jmp     loc_180054CCB
0x180054b5b  mov     r8d, [rbp+Type]
0x180054b5f  cmp     r8d, 3
0x180054b63  jz      short loc_180054B71
0x180054b65  lea     rdx, aSocketaddressl_2; "SocketAddressList isn't REG_BINARY %ld."...
0x180054b6c  jmp     loc_180054CD9
0x180054b71  mov     ecx, [rbp+cbData]
0x180054b74  cmp     ecx, 8
0x180054b77  jnb     short loc_180054B88
0x180054b79  mov     r8d, ecx
0x180054b7c  lea     rdx, aSocketaddressl_3; "SocketAddressList is too small %ld.\n"
0x180054b83  jmp     loc_180054CD9
0x180054b88  mov     r8d, [rbx]
0x180054b8b  mov     edx, 0FFFFFFFFh
0x180054b90  mov     eax, r8d
0x180054b93  shl     rax, 4
0x180054b97  cmp     rax, rdx
0x180054b9a  ja      loc_180054CD2
0x180054ba0  mov     r8d, eax
0x180054ba3  lea     r9, [rcx-8]
0x180054ba7  cmp     r8, r9
0x180054baa  jbe     short loc_180054BC2
0x180054bac  lea     rdx, aSocketaddressl; "SocketAddressList size wrong %ld %Id.\n"
0x180054bb3  mov     ecx, 100h; unsigned int
0x180054bb8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054bbd  jmp     loc_180054CE3
0x180054bc2  xor     r8d, r8d
0x180054bc5  lea     r10d, [r8+2]
0x180054bc9  cmp     r8d, [rbx]
0x180054bcc  jge     loc_180054C74
0x180054bd2  movsxd  r11, r8d
0x180054bd5  add     r11, r11
0x180054bd8  mov     esi, ecx
0x180054bda  mov     rdx, [rbx+r11*8+8]
0x180054bdf  cmp     rdx, rsi
0x180054be2  jnb     short loc_180054C55
0x180054be4  movsxd  r9, dword ptr [rbx+r11*8+10h]
0x180054be9  cmp     r9d, ecx
0x180054bec  jnb     short loc_180054C55
0x180054bee  lea     rax, [rdx+r9]
0x180054bf2  cmp     rax, rsi
0x180054bf5  ja      short loc_180054C55
0x180054bf7  test    dl, 3
0x180054bfa  jnz     short loc_180054C3F
0x180054bfc  test    r9b, 3
0x180054c00  jnz     short loc_180054C3F
0x180054c02  lea     rax, [rdx+rbx]
0x180054c06  mov     [rbx+r11*8+8], rax
0x180054c0b  test    r9d, r9d
0x180054c0e  jz      short loc_180054C29
0x180054c10  test    rax, rax
0x180054c13  jz      short loc_180054C29
0x180054c15  cmp     [rax], r10w
0x180054c19  jnz     short loc_180054C29
0x180054c1b  cmp     dword ptr [rax+4], 0
0x180054c1f  jz      short loc_180054C29
0x180054c21  mov     ecx, [rbp+cbData]
0x180054c24  inc     r8d
0x180054c27  jmp     short loc_180054BC9
0x180054c29  lea     rdx, aSocketaddresse_0; "SocketAddressEntry bogus.\n"
0x180054c30  mov     ecx, 100h; unsigned int
0x180054c35  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054c3a  jmp     loc_180054CCB
0x180054c3f  mov     r8, rdx
0x180054c42  mov     ecx, 100h; unsigned int
0x180054c47  lea     rdx, aNlreadregsocke_0; "NlReadRegSocketAddressList: Unaligned f"...
0x180054c4e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054c53  jmp     short loc_180054CCB
0x180054c55  mov     eax, [rbx+r11*8+10h]
0x180054c5a  mov     r9, rdx
0x180054c5d  lea     rdx, aSocketaddresse; "SocketAddressEntry bad %ld %p %ld.\n"
0x180054c64  mov     dword ptr [rsp+30h+lpData], eax
0x180054c68  mov     ecx, 100h; unsigned int
0x180054c6d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054c72  jmp     short loc_180054CCB
0x180054c74  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180054c7b  call    cs:__imp_RtlEnterCriticalSection
0x180054c81  cmp     cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, 0; _SOCKET_ADDRESS_LIST * NlGlobalWinsockPnpAddresses
0x180054c89  jz      short loc_180054CA4
0x180054c8b  mov     r8d, 37Ah; unsigned int
0x180054c91  lea     rdx, aOnecoreDsNetap_2; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180054c98  lea     rcx, aNlglobalwinsoc; "NlGlobalWinsockPnpAddresses == NULL"
0x180054c9f  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180054ca4  mov     eax, [rbp+cbData]
0x180054ca7  add     eax, 0FFFFFFF8h
0x180054caa  mov     [rbp+cbData], eax
0x180054cad  jz      short loc_180054CB8
0x180054caf  mov     cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, rbx; _SOCKET_ADDRESS_LIST * NlGlobalWinsockPnpAddresses
0x180054cb6  xor     ebx, ebx
0x180054cb8  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180054cbf  mov     cs:?NlGlobalWinsockPnpAddressSize@@3KA, eax; ulong NlGlobalWinsockPnpAddressSize
0x180054cc5  call    cs:__imp_RtlLeaveCriticalSection
0x180054ccb  test    rbx, rbx
0x180054cce  jz      short loc_180054CEC
0x180054cd0  jmp     short loc_180054CE3
0x180054cd2  lea     rdx, aSocketaddressl_0; "SocketAddressList size is too big, and "...
0x180054cd9  mov     ecx, 100h; unsigned int
0x180054cde  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054ce3  mov     rcx, rbx; hMem
0x180054ce6  call    cs:__imp_LocalFree
0x180054cec  mov     rcx, rdi; hKey
0x180054cef  call    cs:__imp_RegCloseKey
0x180054cf5  mov     rbx, [rsp+30h+arg_18]
0x180054cfa  add     rsp, 30h
0x180054cfe  pop     rdi
0x180054cff  pop     rsi
0x180054d00  pop     rbp
0x180054d01  retn
```
