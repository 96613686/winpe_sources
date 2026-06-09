# FillProtocolInfo2FromKeyName

- ea: `0x180031b4c`
- end: `0x180031e6e`
- name: `FillProtocolInfo2FromKeyName`
- size: `802`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, HKEY hKey, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180030cdc`

## callees

- `0x180022bd2`
- `0x180031b4c`
- `0x1800327a8`
- `0x180034cbc`
- `0x1800356f8`
- `0x180037195`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180031e52`
- `ntdll!RtlFreeHeap` at `0x180031e52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031e35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031e35`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031bc7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031bc7`

## string_xrefs

- `0x180031bd9`: `Failed to open protocol`
- `0x180031bf4`: `ServiceFlags`
- `0x180031c06`: `Failed to read the service flags value`
- `0x180031c29`: `Failed to read the provider flags value`
- `0x180031c4c`: `Failed to read the version value`
- `0x180031c6f`: `Failed to read the address family value`
- `0x180031c95`: `Failed to read the max socket address length value`
- `0x180031cbb`: `Failed to read the min socket address length value`
- `0x180031ce1`: `Failed to read the socket type value`
- `0x180031cf5`: `Protocol`
- `0x180031d07`: `Failed to read the protocol value`
- `0x180031d1b`: `ProtocolMaxOffset`
- `0x180031d2d`: `Failed to read the protocol max offset value`
- `0x180031d53`: `Failed to read the network byte order value`
- `0x180031d79`: `Failed to read the message size value`
- `0x180031d8d`: `szProtocol`
- `0x180031d9f`: `Failed to read the protocol string value`

## pseudocode

```c
__int64 __fastcall FillProtocolInfo2FromKeyName(LPCWSTR lpSubKey, HKEY hKey, char *a3)
{
  _WORD *v6; // r14
  unsigned int v7; // eax
  unsigned int v8; // ebx
  const wchar_t *v9; // rdx
  unsigned int String; // eax
  __int64 v11; // r8
  HKEY hKeya; // [rsp+30h] [rbp-48h] BYREF
  int v14; // [rsp+38h] [rbp-40h] BYREF
  int v15; // [rsp+3Ch] [rbp-3Ch] BYREF
  int v16; // [rsp+40h] [rbp-38h] BYREF
  int v17; // [rsp+44h] [rbp-34h] BYREF
  int v18; // [rsp+48h] [rbp-30h] BYREF
  int v19; // [rsp+4Ch] [rbp-2Ch] BYREF
  int v20; // [rsp+50h] [rbp-28h] BYREF
  int v21; // [rsp+54h] [rbp-24h] BYREF
  int v22; // [rsp+58h] [rbp-20h] BYREF
  int v23; // [rsp+5Ch] [rbp-1Ch] BYREF
  void *Src; // [rsp+60h] [rbp-18h]
  int v25; // [rsp+C8h] [rbp+50h] BYREF

  hKeya = 0;
  v25 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v6 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  Src = 0;
  memset_0(a3, 0, 0x274u);
  v7 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &hKeya);
  v8 = v7;
  if ( v7 )
  {
    v9 = L"Failed to open protocol";
LABEL_3:
    LogError(v7, v9);
    goto LABEL_31;
  }
  v7 = ReadDword(hKeya, L"ServiceFlags", &v25);
  v8 = v7;
  if ( v7 )
  {
    v9 = L"Failed to read the service flags value";
    goto LABEL_3;
  }
  v7 = ReadDword(hKeya, L"ProviderFlags", &v14);
  v8 = v7;
  if ( v7 )
  {
    v9 = L"Failed to read the provider flags value";
    goto LABEL_3;
  }
  v7 = ReadDword(hKeya, L"Version", &v15);
  v8 = v7;
  if ( v7 )
  {
    v9 = L"Failed to read the version value";
    goto LABEL_3;
  }
  v7 = ReadDword(hKeya, L"AddressFamily", &v16);
  v8 = v7;
  if ( v7 )
  {
    v9 = L"Failed to read the address family value";
    goto LABEL_3;
  }
  v7 = ReadDword(hKeya, L"MaxSockAddrLength", &v17);
  v8 = v7;
  if ( v7 )
  {
    v9 = L"Failed to read the max socket address length value";
    goto LABEL_3;
  }
  v7 = ReadDword(hKeya, L"MinSockAddrLength", &v18);
  v8 = v7;
  if ( v7 )
  {
    v9 = L"Failed to read the min socket address length value";
    goto LABEL_3;
  }
  v7 = ReadDword(hKeya, L"SocketType", &v19);
  v8 = v7;
  if ( v7 )
  {
    v9 = L"Failed to read the socket type value";
    goto LABEL_3;
  }
  v7 = ReadDword(hKeya, L"Protocol", &v20);
  v8 = v7;
  if ( v7 )
  {
    v9 = L"Failed to read the protocol value";
    goto LABEL_3;
  }
  v7 = ReadDword(hKeya, L"ProtocolMaxOffset", &v21);
  v8 = v7;
  if ( v7 )
  {
    v9 = L"Failed to read the protocol max offset value";
    goto LABEL_3;
  }
  v7 = ReadDword(hKeya, L"ByteOrder", &v22);
  v8 = v7;
  if ( v7 )
  {
    v9 = L"Failed to read the network byte order value";
    goto LABEL_3;
  }
  v7 = ReadDword(hKeya, L"MessageSize", &v23);
  v8 = v7;
  if ( v7 )
  {
    v9 = L"Failed to read the message size value";
    goto LABEL_3;
  }
  String = ReadString(hKeya, L"szProtocol");
  v8 = String;
  if ( String )
  {
    LogError(String, L"Failed to read the protocol string value");
    v6 = Src;
  }
  else
  {
    v11 = -1;
    v6 = Src;
    *(_DWORD *)a3 = v25;
    *((_DWORD *)a3 + 4) = v14;
    *((_DWORD *)a3 + 18) = v15;
    *((_DWORD *)a3 + 19) = v16;
    *((_DWORD *)a3 + 20) = v17;
    *((_DWORD *)a3 + 21) = v18;
    *((_DWORD *)a3 + 22) = v19;
    *((_DWORD *)a3 + 23) = v20;
    *((_DWORD *)a3 + 24) = v21;
    *((_DWORD *)a3 + 25) = v22;
    *((_DWORD *)a3 + 27) = v23;
    do
      ++v11;
    while ( v6[v11] );
    memcpy_0(a3 + 116, v6, 2 * v11);
    *((_DWORD *)a3 + 26) = 0;
    *(_QWORD *)(a3 + 4) = 0;
    *((_DWORD *)a3 + 3) = 0;
    *((_DWORD *)a3 + 10) = 1;
    *((_DWORD *)a3 + 28) = 0;
  }
LABEL_31:
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v6 )
    RtlFreeHeap(SockPrivateHeap, 0, v6);
  return v8;
}

```

## disassembly

```asm
0x180031b4c  push    rbp
0x180031b4e  push    rbx
0x180031b4f  push    rsi
0x180031b50  push    rdi
0x180031b51  push    r14
0x180031b53  push    r15
0x180031b55  mov     rbp, rsp
0x180031b58  sub     rsp, 78h
0x180031b5c  xor     r15d, r15d
0x180031b5f  mov     rsi, r8
0x180031b62  mov     rdi, rdx
0x180031b65  mov     [rbp+hKey], r15
0x180031b69  mov     rbx, rcx
0x180031b6c  mov     [rbp+arg_18], r15d
0x180031b70  mov     rcx, rsi; void *
0x180031b73  mov     [rbp+var_40], r15d
0x180031b77  xor     edx, edx; Val
0x180031b79  mov     [rbp+var_3C], r15d
0x180031b7d  mov     r8d, 274h; Size
0x180031b83  mov     [rbp+var_38], r15d
0x180031b87  mov     [rbp+var_34], r15d
0x180031b8b  mov     r14d, r15d
0x180031b8e  mov     [rbp+var_30], r15d
0x180031b92  mov     [rbp+var_2C], r15d
0x180031b96  mov     [rbp+var_28], r15d
0x180031b9a  mov     [rbp+var_24], r15d
0x180031b9e  mov     [rbp+var_20], r15d
0x180031ba2  mov     [rbp+var_1C], r15d
0x180031ba6  mov     [rbp+Src], r15
0x180031baa  call    memset_0
0x180031baf  lea     rax, [rbp+hKey]
0x180031bb3  mov     r9d, 20019h; samDesired
0x180031bb9  xor     r8d, r8d; ulOptions
0x180031bbc  mov     [rsp+78h+phkResult], rax; phkResult
0x180031bc1  mov     rdx, rbx; lpSubKey
0x180031bc4  mov     rcx, rdi; hKey
0x180031bc7  call    cs:__imp_RegOpenKeyExW
0x180031bce  nop     dword ptr [rax+rax+00h]
0x180031bd3  mov     ebx, eax
0x180031bd5  test    eax, eax
0x180031bd7  jz      short loc_180031BEC
0x180031bd9  lea     rdx, aFailedToOpenPr; "Failed to open protocol"
0x180031be0  mov     ecx, eax
0x180031be2  call    LogError
0x180031be7  jmp     loc_180031E2C
0x180031bec  mov     rcx, [rbp+hKey]
0x180031bf0  lea     r8, [rbp+arg_18]
0x180031bf4  lea     rdx, aServiceflags; "ServiceFlags"
0x180031bfb  call    ReadDword
0x180031c00  mov     ebx, eax
0x180031c02  test    eax, eax
0x180031c04  jz      short loc_180031C0F
0x180031c06  lea     rdx, aFailedToReadTh_10; "Failed to read the service flags value"
0x180031c0d  jmp     short loc_180031BE0
0x180031c0f  mov     rcx, [rbp+hKey]
0x180031c13  lea     r8, [rbp+var_40]
0x180031c17  lea     rdx, aProviderflags; "ProviderFlags"
0x180031c1e  call    ReadDword
0x180031c23  mov     ebx, eax
0x180031c25  test    eax, eax
0x180031c27  jz      short loc_180031C32
0x180031c29  lea     rdx, aFailedToReadTh_8; "Failed to read the provider flags value"
0x180031c30  jmp     short loc_180031BE0
0x180031c32  mov     rcx, [rbp+hKey]
0x180031c36  lea     r8, [rbp+var_3C]
0x180031c3a  lea     rdx, aVersion; "Version"
0x180031c41  call    ReadDword
0x180031c46  mov     ebx, eax
0x180031c48  test    eax, eax
0x180031c4a  jz      short loc_180031C55
0x180031c4c  lea     rdx, aFailedToReadTh_3; "Failed to read the version value"
0x180031c53  jmp     short loc_180031BE0
0x180031c55  mov     rcx, [rbp+hKey]
0x180031c59  lea     r8, [rbp+var_38]
0x180031c5d  lea     rdx, aAddressfamily; "AddressFamily"
0x180031c64  call    ReadDword
0x180031c69  mov     ebx, eax
0x180031c6b  test    eax, eax
0x180031c6d  jz      short loc_180031C7B
0x180031c6f  lea     rdx, aFailedToReadTh_12; "Failed to read the address family value"
0x180031c76  jmp     loc_180031BE0
0x180031c7b  mov     rcx, [rbp+hKey]
0x180031c7f  lea     r8, [rbp+var_34]
0x180031c83  lea     rdx, aMaxsockaddrlen; "MaxSockAddrLength"
0x180031c8a  call    ReadDword
0x180031c8f  mov     ebx, eax
0x180031c91  test    eax, eax
0x180031c93  jz      short loc_180031CA1
0x180031c95  lea     rdx, aFailedToReadTh_13; "Failed to read the max socket address l"...
0x180031c9c  jmp     loc_180031BE0
0x180031ca1  mov     rcx, [rbp+hKey]
0x180031ca5  lea     r8, [rbp+var_30]
0x180031ca9  lea     rdx, aMinsockaddrlen_0; "MinSockAddrLength"
0x180031cb0  call    ReadDword
0x180031cb5  mov     ebx, eax
0x180031cb7  test    eax, eax
0x180031cb9  jz      short loc_180031CC7
0x180031cbb  lea     rdx, aFailedToReadTh_7; "Failed to read the min socket address l"...
0x180031cc2  jmp     loc_180031BE0
0x180031cc7  mov     rcx, [rbp+hKey]
0x180031ccb  lea     r8, [rbp+var_2C]
0x180031ccf  lea     rdx, aSockettype; "SocketType"
0x180031cd6  call    ReadDword
0x180031cdb  mov     ebx, eax
0x180031cdd  test    eax, eax
0x180031cdf  jz      short loc_180031CED
0x180031ce1  lea     rdx, aFailedToReadTh_0; "Failed to read the socket type value"
0x180031ce8  jmp     loc_180031BE0
0x180031ced  mov     rcx, [rbp+hKey]
0x180031cf1  lea     r8, [rbp+var_28]
0x180031cf5  lea     rdx, aProtocol; "Protocol"
0x180031cfc  call    ReadDword
0x180031d01  mov     ebx, eax
0x180031d03  test    eax, eax
0x180031d05  jz      short loc_180031D13
0x180031d07  lea     rdx, aFailedToReadTh_9; "Failed to read the protocol value"
0x180031d0e  jmp     loc_180031BE0
0x180031d13  mov     rcx, [rbp+hKey]
0x180031d17  lea     r8, [rbp+var_24]
0x180031d1b  lea     rdx, aProtocolmaxoff; "ProtocolMaxOffset"
0x180031d22  call    ReadDword
0x180031d27  mov     ebx, eax
0x180031d29  test    eax, eax
0x180031d2b  jz      short loc_180031D39
0x180031d2d  lea     rdx, aFailedToReadTh_5; "Failed to read the protocol max offset "...
0x180031d34  jmp     loc_180031BE0
0x180031d39  mov     rcx, [rbp+hKey]
0x180031d3d  lea     r8, [rbp+var_20]
0x180031d41  lea     rdx, aByteorder; "ByteOrder"
0x180031d48  call    ReadDword
0x180031d4d  mov     ebx, eax
0x180031d4f  test    eax, eax
0x180031d51  jz      short loc_180031D5F
0x180031d53  lea     rdx, aFailedToReadTh_2; "Failed to read the network byte order v"...
0x180031d5a  jmp     loc_180031BE0
0x180031d5f  mov     rcx, [rbp+hKey]
0x180031d63  lea     r8, [rbp+var_1C]
0x180031d67  lea     rdx, aMessagesize; "MessageSize"
0x180031d6e  call    ReadDword
0x180031d73  mov     ebx, eax
0x180031d75  test    eax, eax
0x180031d77  jz      short loc_180031D85
0x180031d79  lea     rdx, aFailedToReadTh; "Failed to read the message size value"
0x180031d80  jmp     loc_180031BE0
0x180031d85  mov     rcx, [rbp+hKey]; hKey
0x180031d89  lea     r8, [rbp+Src]
0x180031d8d  lea     rdx, aSzprotocol; "szProtocol"
0x180031d94  call    ReadString
0x180031d99  mov     ebx, eax
0x180031d9b  test    eax, eax
0x180031d9d  jz      short loc_180031DB3
0x180031d9f  lea     rdx, aFailedToReadTh_1; "Failed to read the protocol string valu"...
0x180031da6  mov     ecx, eax
0x180031da8  call    LogError
0x180031dad  mov     r14, [rbp+Src]
0x180031db1  jmp     short loc_180031E2C
0x180031db3  mov     eax, [rbp+arg_18]
0x180031db6  or      r8, 0FFFFFFFFFFFFFFFFh
0x180031dba  mov     r14, [rbp+Src]
0x180031dbe  mov     [rsi], eax
0x180031dc0  mov     eax, [rbp+var_40]
0x180031dc3  mov     [rsi+10h], eax
0x180031dc6  mov     eax, [rbp+var_3C]
0x180031dc9  mov     [rsi+48h], eax
0x180031dcc  mov     eax, [rbp+var_38]
0x180031dcf  mov     [rsi+4Ch], eax
0x180031dd2  mov     eax, [rbp+var_34]
0x180031dd5  mov     [rsi+50h], eax
0x180031dd8  mov     eax, [rbp+var_30]
0x180031ddb  mov     [rsi+54h], eax
0x180031dde  mov     eax, [rbp+var_2C]
0x180031de1  mov     [rsi+58h], eax
0x180031de4  mov     eax, [rbp+var_28]
0x180031de7  mov     [rsi+5Ch], eax
0x180031dea  mov     eax, [rbp+var_24]
0x180031ded  mov     [rsi+60h], eax
0x180031df0  mov     eax, [rbp+var_20]
0x180031df3  mov     [rsi+64h], eax
0x180031df6  mov     eax, [rbp+var_1C]
0x180031df9  mov     [rsi+6Ch], eax
0x180031dfc  inc     r8
0x180031dff  cmp     [r14+r8*2], r15w
0x180031e04  jnz     short loc_180031DFC
0x180031e06  add     r8, r8; Size
0x180031e09  lea     rcx, [rsi+74h]; void *
0x180031e0d  mov     rdx, r14; Src
0x180031e10  call    memcpy_0
0x180031e15  mov     [rsi+68h], r15d
0x180031e19  mov     [rsi+4], r15
0x180031e1d  mov     [rsi+0Ch], r15d
0x180031e21  mov     dword ptr [rsi+28h], 1
0x180031e28  mov     [rsi+70h], r15d
0x180031e2c  mov     rcx, [rbp+hKey]; hKey
0x180031e30  test    rcx, rcx
0x180031e33  jz      short loc_180031E41
0x180031e35  call    cs:__imp_RegCloseKey
0x180031e3c  nop     dword ptr [rax+rax+00h]
0x180031e41  test    r14, r14
0x180031e44  jz      short loc_180031E5E
0x180031e46  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180031e4d  mov     r8, r14; P
0x180031e50  xor     edx, edx; Flags
0x180031e52  call    cs:__imp_RtlFreeHeap
0x180031e59  nop     dword ptr [rax+rax+00h]
0x180031e5e  mov     eax, ebx
0x180031e60  add     rsp, 78h
0x180031e64  pop     r15
0x180031e66  pop     r14
0x180031e68  pop     rdi
0x180031e69  pop     rsi
0x180031e6a  pop     rbx
0x180031e6b  pop     rbp
0x180031e6c  retn
```
