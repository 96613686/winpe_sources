# TeredoGetPreviousAddressState

- ea: `0x18002acf0`
- end: `0x18002b1ec`
- name: `TeredoGetPreviousAddressState`
- size: `1276`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x18001480c`

## callees

- `0x18000d7c0`
- `0x1800165c8`
- `0x180016ac0`
- `0x1800190f0`
- `0x18001e1e8`
- `0x18002acf0`
- `0x18002b1f4`
- `0x18002b37c`
- `0x18002b47c`
- `0x18002b4ec`
- `0x18002b834`
- `0x18002cb2c`
- `0x18003e818`
- `0x18004b5f0`
- `0x18004c188`
- `0x18005bb9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002af6d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002af6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b118`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b118`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ae2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ae2b`
- `ntdll!RtlIpv6StringToAddressW` at `0x18002afe0`
- `ntdll!RtlIpv6StringToAddressW` at `0x18002afe0`
- `ntdll!RtlIpv6AddressToStringW` at `0x18002ae85`
- `ntdll!RtlIpv6AddressToStringW` at `0x18002ae85`
- `WS2_32!__imp_htons` at `0x18002b013`
- `WS2_32!__imp_htons` at `0x18002b013`
- `WS2_32!__imp_ntohs` at `0x18002b02a`
- `WS2_32!__imp_ntohs` at `0x18002b02a`

## string_xrefs

- `0x18002ae60`: `Open key %s Status = %d`
- `0x18002b03a`: `Client port from registry: %x`
- `0x18002b060`: `Address created on: %I64u`
- `0x18002aff1`: `Address retrieved from registry:`
- `0x18002b102`: `NAT Type cached: %d`
- `0x18002ae47`: `Unable to open key %s. Error %u`

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
0x18002acf0  mov     [rsp-8+arg_10], rbx
0x18002acf5  push    rbp
0x18002acf6  push    rsi
0x18002acf7  push    rdi
0x18002acf8  push    r12
0x18002acfa  push    r13
0x18002acfc  push    r14
0x18002acfe  push    r15
0x18002ad00  lea     rbp, [rsp-320h]
0x18002ad08  sub     rsp, 420h
0x18002ad0f  mov     rax, cs:__security_cookie
0x18002ad16  xor     rax, rsp
0x18002ad19  mov     [rbp+350h+var_40], rax
0x18002ad20  mov     rsi, rdx
0x18002ad23  mov     [rsp+450h+hKey], 0FFFFFFFFFFFFFFFFh
0x18002ad2c  mov     rdi, rcx
0x18002ad2f  lea     r13, [rcx+2778h]
0x18002ad36  mov     ebx, 82h
0x18002ad3b  lea     rcx, [rbp+350h+S]; void *
0x18002ad42  mov     r8d, ebx; Size
0x18002ad45  xor     edx, edx; Val
0x18002ad47  call    memset_0
0x18002ad4c  mov     r8d, ebx; Size
0x18002ad4f  lea     rcx, [rsp+450h+Data]; void *
0x18002ad54  xor     edx, edx; Val
0x18002ad56  call    memset_0
0x18002ad5b  mov     r8d, ebx; Size
0x18002ad5e  lea     rcx, [rbp+350h+var_360]; void *
0x18002ad62  xor     edx, edx; Val
0x18002ad64  call    memset_0
0x18002ad69  xorps   xmm0, xmm0
0x18002ad6c  mov     dword ptr [rdi+4B9Ch], 7
0x18002ad76  mov     r15d, 100000h
0x18002ad7c  lea     rdx, aResolvingDefau; "Resolving default gateway..."
0x18002ad83  mov     ecx, r15d
0x18002ad86  movups  xmmword ptr [rsp+450h+Addr.u], xmm0
0x18002ad8b  call    EventWrite0
0x18002ad90  mov     rdx, [rsi+20h]
0x18002ad94  mov     rcx, r13
0x18002ad97  add     rdx, 4
0x18002ad9b  call    TeredoResolveDefaultGateway
0x18002ada0  xor     r12d, r12d
0x18002ada3  mov     ebx, eax
0x18002ada5  test    eax, eax
0x18002ada7  jz      short loc_18002ADC2
0x18002ada9  mov     r8d, eax
0x18002adac  lea     rdx, aFailedToResolv; "Failed to resolve default gateway. Erro"...
0x18002adb3  mov     ecx, r15d
0x18002adb6  call    EventWriteError0
0x18002adbb  mov     eax, ebx
0x18002adbd  jmp     loc_18002B1C1
0x18002adc2  call    TeredoGetMaximumAddressLifetime
0x18002adc7  mov     r8, rax
0x18002adca  lea     rdx, aMaximumAddress; "Maximum address lifetime is %I64u"
0x18002add1  mov     ecx, r15d
0x18002add4  mov     r14, rax
0x18002add7  call    EventWrite0
0x18002addc  test    r14, r14
0x18002addf  jnz     short loc_18002ADF5
0x18002ade1  lea     rdx, aInvalidMaximum; "Invalid maximum address lifetime. Retur"...
0x18002ade8  mov     ecx, r15d
0x18002adeb  call    EventWriteError0
0x18002adf0  jmp     loc_18002B16F
0x18002adf5  lea     rcx, [rbp+350h+SubKey]
0x18002adfc  call    GetGatewayKeyName
0x18002ae01  lea     rax, [rsp+450h+hKey]
0x18002ae06  mov     [rsp+450h+hKey], 0FFFFFFFFFFFFFFFFh
0x18002ae0f  mov     r9d, 2001Fh; samDesired
0x18002ae15  mov     [rsp+450h+phkResult], rax; phkResult
0x18002ae1a  xor     r8d, r8d; ulOptions
0x18002ae1d  lea     rdx, [rbp+350h+SubKey]; lpSubKey
0x18002ae24  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ae2b  call    cs:__imp_RegOpenKeyExW
0x18002ae32  nop     dword ptr [rax+rax+00h]
0x18002ae37  mov     ebx, eax
0x18002ae39  test    eax, eax
0x18002ae3b  jz      short loc_18002AE56
0x18002ae3d  mov     r9d, eax
0x18002ae40  lea     r8, [rbp+350h+SubKey]
0x18002ae47  lea     rdx, aUnableToOpenKe; "Unable to open key %s. Error %u"
0x18002ae4e  mov     ecx, r15d
0x18002ae51  call    EventWrite0
0x18002ae56  mov     r9d, ebx
0x18002ae59  lea     r8, [rbp+350h+SubKey]
0x18002ae60  lea     rdx, aOpenKeySStatus; "Open key %s Status = %d"
0x18002ae67  mov     ecx, r15d
0x18002ae6a  call    EventWrite0
0x18002ae6f  test    ebx, ebx
0x18002ae71  jnz     loc_18002B16F
0x18002ae77  lea     rdx, [rbp+350h+S]; S
0x18002ae7e  lea     rcx, in6addr_teredoinitiallinklocaladdress; Addr
0x18002ae85  call    cs:__imp_RtlIpv6AddressToStringW
0x18002ae8c  nop     dword ptr [rax+rax+00h]
0x18002ae91  mov     r9d, 7FFFFFFEh
0x18002ae97  lea     r8, [rbp+350h+S]
0x18002ae9e  mov     ebx, 41h ; 'A'
0x18002aea3  lea     rax, [rbp+350h+var_360]
0x18002aea7  mov     ecx, r9d
0x18002aeaa  mov     edx, ebx
0x18002aeac  test    rcx, rcx
0x18002aeaf  jz      short loc_18002AED0
0x18002aeb1  movzx   r10d, word ptr [r8]
0x18002aeb5  test    r10w, r10w
0x18002aeb9  jz      short loc_18002AED0
0x18002aebb  mov     [rax], r10w
0x18002aebf  add     r8, 2
0x18002aec3  add     rax, 2
0x18002aec7  dec     rcx
0x18002aeca  sub     rdx, 1
0x18002aece  jnz     short loc_18002AEAC
0x18002aed0  test    rdx, rdx
0x18002aed3  lea     rcx, [rax-2]
0x18002aed7  mov     rdx, rbx
0x18002aeda  cmovnz  rcx, rax
0x18002aede  lea     rax, [rsp+450h+Data]
0x18002aee3  mov     [rcx], r12w
0x18002aee7  lea     rcx, [rbp+350h+var_360]
0x18002aeeb  test    r9, r9
0x18002aeee  jz      short loc_18002AF0F
0x18002aef0  movzx   r8d, word ptr [rcx]
0x18002aef4  test    r8w, r8w
0x18002aef8  jz      short loc_18002AF0F
0x18002aefa  mov     [rax], r8w
0x18002aefe  add     rcx, 2
0x18002af02  add     rax, 2
0x18002af06  dec     r9
0x18002af09  sub     rdx, 1
0x18002af0d  jnz     short loc_18002AEEB
0x18002af0f  test    rdx, rdx
0x18002af12  mov     [rsp+450h+Type], r12d
0x18002af17  lea     rcx, [rax-2]
0x18002af1b  mov     r8d, 82h; Size
0x18002af21  cmovnz  rcx, rax
0x18002af25  xor     edx, edx; Val
0x18002af27  mov     [rcx], r12w
0x18002af2b  lea     rcx, [rsp+450h+Data]; void *
0x18002af30  call    memset_0
0x18002af35  cmp     [rsp+450h+hKey], 0FFFFFFFFFFFFFFFFh
0x18002af3b  jz      short loc_18002AF9B
0x18002af3d  mov     rcx, [rsp+450h+hKey]; hKey
0x18002af42  lea     rax, [rsp+450h+cbData]
0x18002af47  mov     [rsp+450h+lpcbData], rax; lpcbData
0x18002af4c  lea     r9, [rsp+450h+Type]; lpType
0x18002af51  lea     rax, [rsp+450h+Data]
0x18002af56  mov     [rsp+450h+cbData], 80h
0x18002af5e  xor     r8d, r8d; lpReserved
0x18002af61  mov     [rsp+450h+phkResult], rax; lpData
0x18002af66  lea     rdx, aTeredoaddress; "TeredoAddress"
0x18002af6d  call    cs:__imp_RegQueryValueExW
0x18002af74  nop     dword ptr [rax+rax+00h]
0x18002af79  test    eax, eax
0x18002af7b  jnz     short loc_18002AF9B
0x18002af7d  cmp     [rsp+450h+Type], 1
0x18002af82  jnz     short loc_18002AF9B
0x18002af84  cmp     [rsp+450h+Data], r12w
0x18002af8a  jz      short loc_18002AF9B
0x18002af8c  mov     ecx, [rsp+450h+cbData]
0x18002af90  shr     rcx, 1
0x18002af93  mov     [rsp+rcx*2+450h+Data], r12w
0x18002af99  jmp     short loc_18002AFCC
0x18002af9b  lea     rcx, [rbp+350h+var_360]
0x18002af9f  lea     rax, [rsp+450h+Data]
0x18002afa4  movzx   edx, word ptr [rcx]
0x18002afa7  test    dx, dx
0x18002afaa  jz      short loc_18002AFBD
0x18002afac  mov     [rax], dx
0x18002afaf  add     rcx, 2
0x18002afb3  add     rax, 2
0x18002afb7  sub     rbx, 1
0x18002afbb  jnz     short loc_18002AFA4
0x18002afbd  test    rbx, rbx
0x18002afc0  lea     rcx, [rax-2]
0x18002afc4  cmovnz  rcx, rax
0x18002afc8  mov     [rcx], r12w
0x18002afcc  lea     r8, [rsp+450h+Addr]; Addr
0x18002afd1  mov     qword ptr [rsp+450h+cbData], r12
0x18002afd6  lea     rdx, [rsp+450h+cbData]; Terminator
0x18002afdb  lea     rcx, [rsp+450h+Data]; S
0x18002afe0  call    cs:__imp_RtlIpv6StringToAddressW
0x18002afe7  nop     dword ptr [rax+rax+00h]
0x18002afec  lea     rdx, [rsp+450h+Addr]
0x18002aff1  lea     rcx, aAddressRetriev; "Address retrieved from registry:"
0x18002aff8  call    TeredoTraceAddress
0x18002affd  mov     rcx, [rsp+450h+hKey]
0x18002b002  lea     rdx, aClientlocalpor; "ClientLocalPort"
0x18002b009  xor     r8d, r8d
0x18002b00c  call    GetInteger
0x18002b011  mov     ecx, eax; hostshort
0x18002b013  call    cs:__imp_htons
0x18002b01a  nop     dword ptr [rax+rax+00h]
0x18002b01f  movzx   ecx, ax; netshort
0x18002b022  mov     [r13+0A66h], ax
0x18002b02a  call    cs:__imp_ntohs
0x18002b031  nop     dword ptr [rax+rax+00h]
0x18002b036  movzx   r8d, ax
0x18002b03a  lea     rdx, aClientPortFrom; "Client port from registry: %x"
0x18002b041  mov     ecx, r15d
0x18002b044  call    EventWrite0
0x18002b049  mov     rcx, [rsp+450h+hKey]
0x18002b04e  lea     rdx, aAddresscreatio; "AddressCreationTimestamp"
0x18002b055  xor     r8d, r8d
0x18002b058  call    GetUlongLong
0x18002b05d  mov     r8, rax
0x18002b060  lea     rdx, aAddressCreated; "Address created on: %I64u"
0x18002b067  mov     ecx, 100000h
0x18002b06c  mov     r15, rax
0x18002b06f  call    EventWrite0
0x18002b074  mov     rcx, [rsp+450h+hKey]
0x18002b079  lea     rdx, aNatdetectionti; "NatDetectionTimestamp"
0x18002b080  xor     r8d, r8d
0x18002b083  call    GetUlongLong
0x18002b088  mov     r8, rax
0x18002b08b  lea     rdx, aNatDetectedOnI; "NAT detected on: %I64u"
0x18002b092  mov     ecx, 100000h
0x18002b097  mov     rbx, rax
0x18002b09a  call    EventWrite0
0x18002b09f  mov     rcx, [rsp+450h+hKey]
0x18002b0a4  lea     rdx, aUseoldupnpbeha; "UseOldUPnPBehavior"
0x18002b0ab  xor     r8d, r8d
0x18002b0ae  call    GetInteger
0x18002b0b3  mov     r8d, r12d
0x18002b0b6  lea     rdx, aUpnpFallbackSt; "UPnP fallback state: %d"
0x18002b0bd  cmp     eax, 2
0x18002b0c0  mov     ecx, 100000h
0x18002b0c5  setz    r8b
0x18002b0c9  mov     [rdi+4BA8h], r8d
0x18002b0d0  call    EventWrite0
0x18002b0d5  mov     rdx, r15
0x18002b0d8  mov     rcx, rbx
0x18002b0db  call    TeredoNatTypeDetectionRequired
0x18002b0e0  test    eax, eax
0x18002b0e2  jnz     short loc_18002B113
0x18002b0e4  mov     rcx, [rsp+450h+hKey]
0x18002b0e9  lea     r8d, [rax+7]
0x18002b0ed  lea     rdx, aNattype; "NatType"
0x18002b0f4  call    GetInteger2
0x18002b0f9  mov     r8d, eax
0x18002b0fc  mov     [rdi+4B9Ch], eax
0x18002b102  lea     rdx, aNatTypeCachedD; "NAT Type cached: %d"
0x18002b109  mov     ecx, 100000h
0x18002b10e  call    EventWrite0
0x18002b113  mov     rcx, [rsp+450h+hKey]; hKey
0x18002b118  call    cs:__imp_RegCloseKey
0x18002b11f  nop     dword ptr [rax+rax+00h]
0x18002b124  lea     rax, [rsp+450h+Data]
0x18002b129  lea     r8, [rbp+350h+var_360]
0x18002b12d  sub     r8, rax
0x18002b130  movzx   ecx, word ptr [rax]
0x18002b133  movzx   edx, word ptr [rax+r8]
0x18002b138  sub     ecx, edx
0x18002b13a  jnz     short loc_18002B144
0x18002b13c  add     rax, 2
0x18002b140  test    edx, edx
0x18002b142  jnz     short loc_18002B130
0x18002b144  test    ecx, ecx
0x18002b146  jz      short loc_18002B169
0x18002b148  test    r15, r15
0x18002b14b  jz      short loc_18002B169
0x18002b14d  mov     r9, r14
0x18002b150  mov     [rsp+450h+phkResult], rsi
0x18002b155  mov     r8, r15
0x18002b158  lea     rdx, [rsp+450h+Data]
0x18002b15d  mov     rcx, rdi
0x18002b160  call    TeredoVerifyPreviousStateAddress
0x18002b165  test    eax, eax
0x18002b167  jnz     short loc_18002B1BF
0x18002b169  mov     r15d, 100000h
0x18002b16f  mov     rcx, [rsi+20h]
0x18002b173  mov     rdx, r13
0x18002b176  add     rcx, 4
0x18002b17a  call    TeredoVerifyAndAssignServerAddress
0x18002b17f  test    eax, eax
0x18002b181  jz      short loc_18002B1B7
0x18002b183  mov     rax, [rsi+20h]
0x18002b187  movzx   ecx, byte ptr [rax+7]
0x18002b18b  movzx   edx, byte ptr [rax+6]
0x18002b18f  movzx   r9d, byte ptr [rax+5]
0x18002b194  movzx   r8d, byte ptr [rax+4]
0x18002b199  mov     dword ptr [rsp+450h+lpcbData], ecx
0x18002b19d  mov     ecx, r15d
0x18002b1a0  mov     dword ptr [rsp+450h+phkResult], edx
0x18002b1a4  lea     rdx, aResolvedServer; "Resolved server address %d.%d.%d.%d is "...
0x18002b1ab  call    EventWriteError0
0x18002b1b0  mov     eax, 1E7h
0x18002b1b5  jmp     short loc_18002B1C1
0x18002b1b7  mov     rcx, rdi
0x18002b1ba  call    TeredoGenerateNewAddress
0x18002b1bf  xor     eax, eax
0x18002b1c1  mov     rcx, [rbp+350h+var_40]
0x18002b1c8  xor     rcx, rsp; StackCookie
0x18002b1cb  call    __security_check_cookie
0x18002b1d0  mov     rbx, [rsp+450h+arg_10]
0x18002b1d8  add     rsp, 420h
0x18002b1df  pop     r15
0x18002b1e1  pop     r14
0x18002b1e3  pop     r13
0x18002b1e5  pop     r12
0x18002b1e7  pop     rdi
0x18002b1e8  pop     rsi
0x18002b1e9  pop     rbp
  ... truncated ...
```
