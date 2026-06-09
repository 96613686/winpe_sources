# TeredoGetPreviousAddressState

- ea: `0x18002ace0`
- end: `0x18002b1dc`
- name: `TeredoGetPreviousAddressState`
- size: `1276`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x1800147fc`

## callees

- `0x18000d7b0`
- `0x1800165b8`
- `0x180016ab0`
- `0x1800190e0`
- `0x18001e1d8`
- `0x18002ace0`
- `0x18002b1e4`
- `0x18002b36c`
- `0x18002b46c`
- `0x18002b4dc`
- `0x18002b824`
- `0x18002cb1c`
- `0x18003e858`
- `0x18004b630`
- `0x18004c1c8`
- `0x18005bb7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002af5d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002af5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b108`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b108`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ae1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ae1b`
- `ntdll!RtlIpv6StringToAddressW` at `0x18002afd0`
- `ntdll!RtlIpv6StringToAddressW` at `0x18002afd0`
- `ntdll!RtlIpv6AddressToStringW` at `0x18002ae75`
- `ntdll!RtlIpv6AddressToStringW` at `0x18002ae75`
- `WS2_32!__imp_htons` at `0x18002b003`
- `WS2_32!__imp_htons` at `0x18002b003`
- `WS2_32!__imp_ntohs` at `0x18002b01a`
- `WS2_32!__imp_ntohs` at `0x18002b01a`

## string_xrefs

- `0x18002ae50`: `Open key %s Status = %d`
- `0x18002b02a`: `Client port from registry: %x`
- `0x18002b050`: `Address created on: %I64u`
- `0x18002afe1`: `Address retrieved from registry:`
- `0x18002b0f2`: `NAT Type cached: %d`
- `0x18002ae37`: `Unable to open key %s. Error %u`

## pseudocode

```c
__int64 __fastcall TeredoGetPreviousAddressState(__int64 a1, __int64 a2)
{
  __int64 v4; // r13
  unsigned int v5; // eax
  unsigned int v6; // ebx
  __int64 MaximumAddressLifetime; // r14
  unsigned int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // r9
  WCHAR *v12; // r8
  __int64 v13; // rbx
  _WORD *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  bool v17; // zf
  _WORD *v18; // rcx
  __int64 v19; // rdx
  BYTE *v20; // rax
  _WORD *v21; // rcx
  BYTE *v22; // rcx
  _WORD *v23; // rcx
  BYTE *v24; // rax
  BYTE *v25; // rcx
  u_short Integer; // ax
  u_short v27; // ax
  u_short v28; // ax
  __int64 UlongLong; // r15
  __int64 v30; // rbx
  unsigned int Integer2; // eax
  BYTE *v32; // rax
  int v33; // edx
  int v34; // ecx
  unsigned __int8 *v35; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct in6_addr Addr; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Data[72]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v43[144]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR S[72]; // [rsp+180h] [rbp+80h] BYREF
  WCHAR SubKey[256]; // [rsp+210h] [rbp+110h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v4 = a1 + 10104;
  memset_0(S, 0, 0x82u);
  memset_0(Data, 0, 0x82u);
  memset_0(v43, 0, 0x82u);
  *(_DWORD *)(a1 + 19356) = 7;
  Addr = 0;
  EventWrite0(0x100000, L"Resolving default gateway...");
  v5 = TeredoResolveDefaultGateway(v4, *(_QWORD *)(a2 + 32) + 4LL);
  v6 = v5;
  if ( v5 )
  {
    EventWriteError0(0x100000, L"Failed to resolve default gateway. Error (%d)", v5);
    return v6;
  }
  MaximumAddressLifetime = TeredoGetMaximumAddressLifetime();
  EventWrite0(0x100000, L"Maximum address lifetime is %I64u", MaximumAddressLifetime);
  if ( MaximumAddressLifetime )
  {
    GetGatewayKeyName(SubKey);
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2001Fu, &hKey);
    v10 = v9;
    if ( v9 )
      EventWrite0(0x100000, L"Unable to open key %s. Error %u", SubKey, v9);
    EventWrite0(0x100000, L"Open key %s Status = %d", SubKey, v10);
    if ( !v10 )
    {
      RtlIpv6AddressToStringW(&in6addr_teredoinitiallinklocaladdress, S);
      v11 = 2147483646;
      v12 = S;
      v13 = 65;
      v14 = v43;
      v15 = 2147483646;
      v16 = 65;
      do
      {
        if ( !v15 )
          break;
        if ( !*v12 )
          break;
        *v14++ = *v12++;
        --v15;
        --v16;
      }
      while ( v16 );
      v17 = v16 == 0;
      v18 = v14 - 1;
      v19 = 65;
      if ( !v17 )
        v18 = v14;
      v20 = (BYTE *)Data;
      *v18 = 0;
      v21 = v43;
      do
      {
        if ( !v11 )
          break;
        if ( !*v21 )
          break;
        *(_WORD *)v20 = *v21++;
        v20 += 2;
        --v11;
        --v19;
      }
      while ( v19 );
      Type = 0;
      v22 = v20 - 2;
      if ( v19 )
        v22 = v20;
      *(_WORD *)v22 = 0;
      memset_0(Data, 0, 0x82u);
      if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL
        || (cbData[0] = 128, RegQueryValueExW(hKey, L"TeredoAddress", 0, &Type, (LPBYTE)Data, cbData))
        || Type != 1
        || !Data[0] )
      {
        v23 = v43;
        v24 = (BYTE *)Data;
        do
        {
          if ( !*v23 )
            break;
          *(_WORD *)v24 = *v23++;
          v24 += 2;
          --v13;
        }
        while ( v13 );
        v25 = v24 - 2;
        if ( v13 )
          v25 = v24;
        *(_WORD *)v25 = 0;
      }
      else
      {
        Data[(unsigned __int64)cbData[0] >> 1] = 0;
      }
      *(_QWORD *)cbData = 0;
      RtlIpv6StringToAddressW(Data, (PCWSTR *)cbData, &Addr);
      TeredoTraceAddress(L"Address retrieved from registry:", &Addr);
      Integer = GetInteger(hKey, L"ClientLocalPort", 0);
      v27 = htons(Integer);
      *(_WORD *)(v4 + 2662) = v27;
      v28 = ntohs(v27);
      EventWrite0(0x100000, L"Client port from registry: %x", v28);
      UlongLong = GetUlongLong(hKey, L"AddressCreationTimestamp", 0);
      EventWrite0(0x100000, L"Address created on: %I64u", UlongLong);
      v30 = GetUlongLong(hKey, L"NatDetectionTimestamp", 0);
      EventWrite0(0x100000, L"NAT detected on: %I64u", v30);
      *(_DWORD *)(a1 + 19368) = GetInteger(hKey, L"UseOldUPnPBehavior", 0) == 2;
      EventWrite0(0x100000, L"UPnP fallback state: %d");
      if ( !(unsigned int)TeredoNatTypeDetectionRequired(v30, UlongLong) )
      {
        Integer2 = GetInteger2(hKey, L"NatType", 7);
        *(_DWORD *)(a1 + 19356) = Integer2;
        EventWrite0(0x100000, L"NAT Type cached: %d", Integer2);
      }
      RegCloseKey(hKey);
      v32 = (BYTE *)Data;
      do
      {
        v33 = *(unsigned __int16 *)&v32[v43 - (_BYTE *)Data];
        v34 = *(unsigned __int16 *)v32 - v33;
        if ( v34 )
          break;
        v32 += 2;
      }
      while ( v33 );
      if ( v34
        && UlongLong
        && (unsigned int)TeredoVerifyPreviousStateAddress(a1, Data, UlongLong, MaximumAddressLifetime, a2) )
      {
        return 0;
      }
    }
  }
  else
  {
    EventWriteError0(0x100000, L"Invalid maximum address lifetime. Returning.");
  }
  if ( (unsigned int)TeredoVerifyAndAssignServerAddress(*(_QWORD *)(a2 + 32) + 4LL, v4) )
  {
    v35 = *(unsigned __int8 **)(a2 + 32);
    LODWORD(lpcbData) = v35[7];
    LODWORD(phkResult) = v35[6];
    EventWriteError0(0x100000, L"Resolved server address %d.%d.%d.%d is invalid", v35[4], v35[5], phkResult, lpcbData);
    return 487;
  }
  TeredoGenerateNewAddress(a1);
  return 0;
}

```

## disassembly

```asm
0x18002ace0  mov     [rsp-8+arg_10], rbx
0x18002ace5  push    rbp
0x18002ace6  push    rsi
0x18002ace7  push    rdi
0x18002ace8  push    r12
0x18002acea  push    r13
0x18002acec  push    r14
0x18002acee  push    r15
0x18002acf0  lea     rbp, [rsp-320h]
0x18002acf8  sub     rsp, 420h
0x18002acff  mov     rax, cs:__security_cookie
0x18002ad06  xor     rax, rsp
0x18002ad09  mov     [rbp+350h+var_40], rax
0x18002ad10  mov     rsi, rdx
0x18002ad13  mov     [rsp+450h+hKey], 0FFFFFFFFFFFFFFFFh
0x18002ad1c  mov     rdi, rcx
0x18002ad1f  lea     r13, [rcx+2778h]
0x18002ad26  mov     ebx, 82h
0x18002ad2b  lea     rcx, [rbp+350h+S]; void *
0x18002ad32  mov     r8d, ebx; Size
0x18002ad35  xor     edx, edx; Val
0x18002ad37  call    memset_0
0x18002ad3c  mov     r8d, ebx; Size
0x18002ad3f  lea     rcx, [rsp+450h+Data]; void *
0x18002ad44  xor     edx, edx; Val
0x18002ad46  call    memset_0
0x18002ad4b  mov     r8d, ebx; Size
0x18002ad4e  lea     rcx, [rbp+350h+var_360]; void *
0x18002ad52  xor     edx, edx; Val
0x18002ad54  call    memset_0
0x18002ad59  xorps   xmm0, xmm0
0x18002ad5c  mov     dword ptr [rdi+4B9Ch], 7
0x18002ad66  mov     r15d, 100000h
0x18002ad6c  lea     rdx, aResolvingDefau; "Resolving default gateway..."
0x18002ad73  mov     ecx, r15d
0x18002ad76  movups  xmmword ptr [rsp+450h+Addr.u], xmm0
0x18002ad7b  call    EventWrite0
0x18002ad80  mov     rdx, [rsi+20h]
0x18002ad84  mov     rcx, r13
0x18002ad87  add     rdx, 4
0x18002ad8b  call    TeredoResolveDefaultGateway
0x18002ad90  xor     r12d, r12d
0x18002ad93  mov     ebx, eax
0x18002ad95  test    eax, eax
0x18002ad97  jz      short loc_18002ADB2
0x18002ad99  mov     r8d, eax
0x18002ad9c  lea     rdx, aFailedToResolv; "Failed to resolve default gateway. Erro"...
0x18002ada3  mov     ecx, r15d
0x18002ada6  call    EventWriteError0
0x18002adab  mov     eax, ebx
0x18002adad  jmp     loc_18002B1B1
0x18002adb2  call    TeredoGetMaximumAddressLifetime
0x18002adb7  mov     r8, rax
0x18002adba  lea     rdx, aMaximumAddress; "Maximum address lifetime is %I64u"
0x18002adc1  mov     ecx, r15d
0x18002adc4  mov     r14, rax
0x18002adc7  call    EventWrite0
0x18002adcc  test    r14, r14
0x18002adcf  jnz     short loc_18002ADE5
0x18002add1  lea     rdx, aInvalidMaximum; "Invalid maximum address lifetime. Retur"...
0x18002add8  mov     ecx, r15d
0x18002addb  call    EventWriteError0
0x18002ade0  jmp     loc_18002B15F
0x18002ade5  lea     rcx, [rbp+350h+SubKey]
0x18002adec  call    GetGatewayKeyName
0x18002adf1  lea     rax, [rsp+450h+hKey]
0x18002adf6  mov     [rsp+450h+hKey], 0FFFFFFFFFFFFFFFFh
0x18002adff  mov     r9d, 2001Fh; samDesired
0x18002ae05  mov     [rsp+450h+phkResult], rax; phkResult
0x18002ae0a  xor     r8d, r8d; ulOptions
0x18002ae0d  lea     rdx, [rbp+350h+SubKey]; lpSubKey
0x18002ae14  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ae1b  call    cs:__imp_RegOpenKeyExW
0x18002ae22  nop     dword ptr [rax+rax+00h]
0x18002ae27  mov     ebx, eax
0x18002ae29  test    eax, eax
0x18002ae2b  jz      short loc_18002AE46
0x18002ae2d  mov     r9d, eax
0x18002ae30  lea     r8, [rbp+350h+SubKey]
0x18002ae37  lea     rdx, aUnableToOpenKe; "Unable to open key %s. Error %u"
0x18002ae3e  mov     ecx, r15d
0x18002ae41  call    EventWrite0
0x18002ae46  mov     r9d, ebx
0x18002ae49  lea     r8, [rbp+350h+SubKey]
0x18002ae50  lea     rdx, aOpenKeySStatus; "Open key %s Status = %d"
0x18002ae57  mov     ecx, r15d
0x18002ae5a  call    EventWrite0
0x18002ae5f  test    ebx, ebx
0x18002ae61  jnz     loc_18002B15F
0x18002ae67  lea     rdx, [rbp+350h+S]; S
0x18002ae6e  lea     rcx, in6addr_teredoinitiallinklocaladdress; Addr
0x18002ae75  call    cs:__imp_RtlIpv6AddressToStringW
0x18002ae7c  nop     dword ptr [rax+rax+00h]
0x18002ae81  mov     r9d, 7FFFFFFEh
0x18002ae87  lea     r8, [rbp+350h+S]
0x18002ae8e  mov     ebx, 41h ; 'A'
0x18002ae93  lea     rax, [rbp+350h+var_360]
0x18002ae97  mov     ecx, r9d
0x18002ae9a  mov     edx, ebx
0x18002ae9c  test    rcx, rcx
0x18002ae9f  jz      short loc_18002AEC0
0x18002aea1  movzx   r10d, word ptr [r8]
0x18002aea5  test    r10w, r10w
0x18002aea9  jz      short loc_18002AEC0
0x18002aeab  mov     [rax], r10w
0x18002aeaf  add     r8, 2
0x18002aeb3  add     rax, 2
0x18002aeb7  dec     rcx
0x18002aeba  sub     rdx, 1
0x18002aebe  jnz     short loc_18002AE9C
0x18002aec0  test    rdx, rdx
0x18002aec3  lea     rcx, [rax-2]
0x18002aec7  mov     rdx, rbx
0x18002aeca  cmovnz  rcx, rax
0x18002aece  lea     rax, [rsp+450h+Data]
0x18002aed3  mov     [rcx], r12w
0x18002aed7  lea     rcx, [rbp+350h+var_360]
0x18002aedb  test    r9, r9
0x18002aede  jz      short loc_18002AEFF
0x18002aee0  movzx   r8d, word ptr [rcx]
0x18002aee4  test    r8w, r8w
0x18002aee8  jz      short loc_18002AEFF
0x18002aeea  mov     [rax], r8w
0x18002aeee  add     rcx, 2
0x18002aef2  add     rax, 2
0x18002aef6  dec     r9
0x18002aef9  sub     rdx, 1
0x18002aefd  jnz     short loc_18002AEDB
0x18002aeff  test    rdx, rdx
0x18002af02  mov     [rsp+450h+Type], r12d
0x18002af07  lea     rcx, [rax-2]
0x18002af0b  mov     r8d, 82h; Size
0x18002af11  cmovnz  rcx, rax
0x18002af15  xor     edx, edx; Val
0x18002af17  mov     [rcx], r12w
0x18002af1b  lea     rcx, [rsp+450h+Data]; void *
0x18002af20  call    memset_0
0x18002af25  cmp     [rsp+450h+hKey], 0FFFFFFFFFFFFFFFFh
0x18002af2b  jz      short loc_18002AF8B
0x18002af2d  mov     rcx, [rsp+450h+hKey]; hKey
0x18002af32  lea     rax, [rsp+450h+cbData]
0x18002af37  mov     [rsp+450h+lpcbData], rax; lpcbData
0x18002af3c  lea     r9, [rsp+450h+Type]; lpType
0x18002af41  lea     rax, [rsp+450h+Data]
0x18002af46  mov     [rsp+450h+cbData], 80h
0x18002af4e  xor     r8d, r8d; lpReserved
0x18002af51  mov     [rsp+450h+phkResult], rax; lpData
0x18002af56  lea     rdx, aTeredoaddress; "TeredoAddress"
0x18002af5d  call    cs:__imp_RegQueryValueExW
0x18002af64  nop     dword ptr [rax+rax+00h]
0x18002af69  test    eax, eax
0x18002af6b  jnz     short loc_18002AF8B
0x18002af6d  cmp     [rsp+450h+Type], 1
0x18002af72  jnz     short loc_18002AF8B
0x18002af74  cmp     [rsp+450h+Data], r12w
0x18002af7a  jz      short loc_18002AF8B
0x18002af7c  mov     ecx, [rsp+450h+cbData]
0x18002af80  shr     rcx, 1
0x18002af83  mov     [rsp+rcx*2+450h+Data], r12w
0x18002af89  jmp     short loc_18002AFBC
0x18002af8b  lea     rcx, [rbp+350h+var_360]
0x18002af8f  lea     rax, [rsp+450h+Data]
0x18002af94  movzx   edx, word ptr [rcx]
0x18002af97  test    dx, dx
0x18002af9a  jz      short loc_18002AFAD
0x18002af9c  mov     [rax], dx
0x18002af9f  add     rcx, 2
0x18002afa3  add     rax, 2
0x18002afa7  sub     rbx, 1
0x18002afab  jnz     short loc_18002AF94
0x18002afad  test    rbx, rbx
0x18002afb0  lea     rcx, [rax-2]
0x18002afb4  cmovnz  rcx, rax
0x18002afb8  mov     [rcx], r12w
0x18002afbc  lea     r8, [rsp+450h+Addr]; Addr
0x18002afc1  mov     qword ptr [rsp+450h+cbData], r12
0x18002afc6  lea     rdx, [rsp+450h+cbData]; Terminator
0x18002afcb  lea     rcx, [rsp+450h+Data]; S
0x18002afd0  call    cs:__imp_RtlIpv6StringToAddressW
0x18002afd7  nop     dword ptr [rax+rax+00h]
0x18002afdc  lea     rdx, [rsp+450h+Addr]
0x18002afe1  lea     rcx, aAddressRetriev; "Address retrieved from registry:"
0x18002afe8  call    TeredoTraceAddress
0x18002afed  mov     rcx, [rsp+450h+hKey]
0x18002aff2  lea     rdx, aClientlocalpor; "ClientLocalPort"
0x18002aff9  xor     r8d, r8d
0x18002affc  call    GetInteger
0x18002b001  mov     ecx, eax; hostshort
0x18002b003  call    cs:__imp_htons
0x18002b00a  nop     dword ptr [rax+rax+00h]
0x18002b00f  movzx   ecx, ax; netshort
0x18002b012  mov     [r13+0A66h], ax
0x18002b01a  call    cs:__imp_ntohs
0x18002b021  nop     dword ptr [rax+rax+00h]
0x18002b026  movzx   r8d, ax
0x18002b02a  lea     rdx, aClientPortFrom; "Client port from registry: %x"
0x18002b031  mov     ecx, r15d
0x18002b034  call    EventWrite0
0x18002b039  mov     rcx, [rsp+450h+hKey]
0x18002b03e  lea     rdx, aAddresscreatio; "AddressCreationTimestamp"
0x18002b045  xor     r8d, r8d
0x18002b048  call    GetUlongLong
0x18002b04d  mov     r8, rax
0x18002b050  lea     rdx, aAddressCreated; "Address created on: %I64u"
0x18002b057  mov     ecx, 100000h
0x18002b05c  mov     r15, rax
0x18002b05f  call    EventWrite0
0x18002b064  mov     rcx, [rsp+450h+hKey]
0x18002b069  lea     rdx, aNatdetectionti; "NatDetectionTimestamp"
0x18002b070  xor     r8d, r8d
0x18002b073  call    GetUlongLong
0x18002b078  mov     r8, rax
0x18002b07b  lea     rdx, aNatDetectedOnI; "NAT detected on: %I64u"
0x18002b082  mov     ecx, 100000h
0x18002b087  mov     rbx, rax
0x18002b08a  call    EventWrite0
0x18002b08f  mov     rcx, [rsp+450h+hKey]
0x18002b094  lea     rdx, aUseoldupnpbeha; "UseOldUPnPBehavior"
0x18002b09b  xor     r8d, r8d
0x18002b09e  call    GetInteger
0x18002b0a3  mov     r8d, r12d
0x18002b0a6  lea     rdx, aUpnpFallbackSt; "UPnP fallback state: %d"
0x18002b0ad  cmp     eax, 2
0x18002b0b0  mov     ecx, 100000h
0x18002b0b5  setz    r8b
0x18002b0b9  mov     [rdi+4BA8h], r8d
0x18002b0c0  call    EventWrite0
0x18002b0c5  mov     rdx, r15
0x18002b0c8  mov     rcx, rbx
0x18002b0cb  call    TeredoNatTypeDetectionRequired
0x18002b0d0  test    eax, eax
0x18002b0d2  jnz     short loc_18002B103
0x18002b0d4  mov     rcx, [rsp+450h+hKey]
0x18002b0d9  lea     r8d, [rax+7]
0x18002b0dd  lea     rdx, aNattype; "NatType"
0x18002b0e4  call    GetInteger2
0x18002b0e9  mov     r8d, eax
0x18002b0ec  mov     [rdi+4B9Ch], eax
0x18002b0f2  lea     rdx, aNatTypeCachedD; "NAT Type cached: %d"
0x18002b0f9  mov     ecx, 100000h
0x18002b0fe  call    EventWrite0
0x18002b103  mov     rcx, [rsp+450h+hKey]; hKey
0x18002b108  call    cs:__imp_RegCloseKey
0x18002b10f  nop     dword ptr [rax+rax+00h]
0x18002b114  lea     rax, [rsp+450h+Data]
0x18002b119  lea     r8, [rbp+350h+var_360]
0x18002b11d  sub     r8, rax
0x18002b120  movzx   ecx, word ptr [rax]
0x18002b123  movzx   edx, word ptr [rax+r8]
0x18002b128  sub     ecx, edx
0x18002b12a  jnz     short loc_18002B134
0x18002b12c  add     rax, 2
0x18002b130  test    edx, edx
0x18002b132  jnz     short loc_18002B120
0x18002b134  test    ecx, ecx
0x18002b136  jz      short loc_18002B159
0x18002b138  test    r15, r15
0x18002b13b  jz      short loc_18002B159
0x18002b13d  mov     r9, r14
0x18002b140  mov     [rsp+450h+phkResult], rsi
0x18002b145  mov     r8, r15
0x18002b148  lea     rdx, [rsp+450h+Data]
0x18002b14d  mov     rcx, rdi
0x18002b150  call    TeredoVerifyPreviousStateAddress
0x18002b155  test    eax, eax
0x18002b157  jnz     short loc_18002B1AF
0x18002b159  mov     r15d, 100000h
0x18002b15f  mov     rcx, [rsi+20h]
0x18002b163  mov     rdx, r13
0x18002b166  add     rcx, 4
0x18002b16a  call    TeredoVerifyAndAssignServerAddress
0x18002b16f  test    eax, eax
0x18002b171  jz      short loc_18002B1A7
0x18002b173  mov     rax, [rsi+20h]
0x18002b177  movzx   ecx, byte ptr [rax+7]
0x18002b17b  movzx   edx, byte ptr [rax+6]
0x18002b17f  movzx   r9d, byte ptr [rax+5]
0x18002b184  movzx   r8d, byte ptr [rax+4]
0x18002b189  mov     dword ptr [rsp+450h+lpcbData], ecx
0x18002b18d  mov     ecx, r15d
0x18002b190  mov     dword ptr [rsp+450h+phkResult], edx
0x18002b194  lea     rdx, aResolvedServer; "Resolved server address %d.%d.%d.%d is "...
0x18002b19b  call    EventWriteError0
0x18002b1a0  mov     eax, 1E7h
0x18002b1a5  jmp     short loc_18002B1B1
0x18002b1a7  mov     rcx, rdi
0x18002b1aa  call    TeredoGenerateNewAddress
0x18002b1af  xor     eax, eax
0x18002b1b1  mov     rcx, [rbp+350h+var_40]
0x18002b1b8  xor     rcx, rsp; StackCookie
0x18002b1bb  call    __security_check_cookie
0x18002b1c0  mov     rbx, [rsp+450h+arg_10]
0x18002b1c8  add     rsp, 420h
0x18002b1cf  pop     r15
0x18002b1d1  pop     r14
0x18002b1d3  pop     r13
0x18002b1d5  pop     r12
0x18002b1d7  pop     rdi
0x18002b1d8  pop     rsi
0x18002b1d9  pop     rbp
  ... truncated ...
```
