# ReadParameters

- ea: `0x14004abd4`
- end: `0x14004b257`
- name: `ReadParameters`
- size: `1667`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400493c4`

## callees

- `0x14001be88`
- `0x14001bea8`
- `0x14004aaf4`
- `0x14004abd4`
- `0x14004b260`
- `0x14004b48c`

## string_xrefs

- `0x14004ae1a`: `CachePerAdapterEnabled`
- `0x14004ae7a`: `MultipleCacheFlags`
- `0x14004aca3`: `InboundDgramNameCacheTimeout`
- `0x14004b010`: `CacheRemoteNameOnDgramReceive`
- `0x14004aeee`: `SmbDisableNetbiosNameCacheLookup`
- `0x14004ad14`: `MaxNumNameCache`
- `0x14004ac42`: `CacheTimeout`

## pseudocode

```c
__int64 __fastcall ReadParameters(__int64 a1, void *a2)
{
  unsigned int SingleParameter; // eax
  char v5; // al
  char v6; // al
  char v7; // al
  char v8; // al
  int v9; // eax
  __int16 v10; // cx
  int v11; // eax
  int v12; // esi
  int v13; // r8d
  int v14; // esi
  __int64 result; // rax
  int v16; // esi

  ReadParameters2();
  *(_WORD *)(a1 + 490) = NbtReadSingleParameter(a2);
  SingleParameter = NbtReadSingleParameter(a2);
  *(_DWORD *)(a1 + 588) = SingleParameter;
  if ( SingleParameter > 0x7D0 )
    *(_DWORD *)(a1 + 588) = 2000;
  *(_DWORD *)(a1 + 440) = NbtReadSingleParameter(a2);
  *(_DWORD *)(a1 + 468) = NbtReadSingleParameter(a2);
  *(_DWORD *)(a1 + 452) = NbtReadSingleParameter(a2);
  IsDomainController();
  *(_DWORD *)(a1 + 448) = NbtReadSingleParameter(a2);
  *(_DWORD *)(a1 + 444) = (MEMORY[0xFFFFF78000000014] >> 8) & 0x1FFFF;
  *(_DWORD *)(a1 + 460) = NbtReadSingleParameter(a2);
  *(_WORD *)(a1 + 410) = NbtReadSingleParameter(a2);
  *(_DWORD *)(a1 + 380) = NbtReadSingleParameter(a2);
  *(_WORD *)(a1 + 408) = NbtReadSingleParameter(a2);
  *(_DWORD *)(a1 + 384) = NbtReadSingleParameter(a2);
  *(_DWORD *)(a1 + 472) = NbtReadSingleParameter(a2);
  *(_BYTE *)(a1 + 562) = NbtReadSingleParameter(a2);
  *(_BYTE *)(a1 + 561) = NbtReadSingleParameter(a2);
  *(_BYTE *)(a1 + 567) = NbtReadSingleParameter(a2);
  v5 = NbtReadSingleParameter(a2);
  *(_BYTE *)(a1 + 403) = v5;
  if ( v5 )
    v6 = NbtReadSingleParameter(a2);
  else
    v6 = 0;
  *(_BYTE *)(a1 + 404) = v6;
  *(_BYTE *)(a1 + 405) = NbtReadSingleParameter(a2);
  *(_BYTE *)(a1 + 406) = 0;
  *(_BYTE *)(a1 + 402) = NbtReadSingleParameter(a2);
  v7 = NbtReadSingleParameter(a2);
  *(_BYTE *)(a1 + 566) = v7;
  if ( v7 )
  {
    *(_BYTE *)(a1 + 563) = 1;
    v8 = 0;
  }
  else
  {
    *(_BYTE *)(a1 + 563) = NbtReadSingleParameter(a2);
    v8 = NbtReadSingleParameter(a2);
  }
  *(_BYTE *)(a1 + 568) = v8;
  *(_BYTE *)(a1 + 564) = NbtReadSingleParameter(a2);
  *(_BYTE *)(a1 + 565) = NbtReadSingleParameter(a2);
  *(_DWORD *)(a1 + 520) = NbtReadSingleParameter(a2);
  *(_DWORD *)(a1 + 516) = NbtReadSingleParameter(a2);
  *(_BYTE *)(a1 + 570) = NbtReadSingleParameter(a2);
  *(_DWORD *)(a1 + 464) = NbtReadSingleParameter(a2);
  *(_DWORD *)(a1 + 592) = NbtReadSingleParameter(a2);
  *(_DWORD *)(a1 + 596) = NbtReadSingleParameter(a2);
  *(_DWORD *)(a1 + 600) = NbtReadSingleParameter(a2);
  *(_BYTE *)(a1 + 785) = NbtReadSingleParameter(a2);
  *(_BYTE *)(a1 + 793) = NbtReadSingleParameter(a2);
  *(_DWORD *)(a1 + 744) = NbtReadSingleParameter(a2);
  if ( *(_DWORD *)(a1 + 592) > 0x9C40u )
    *(_DWORD *)(a1 + 592) = 40000;
  if ( *(_DWORD *)(a1 + 596) > 0x14u )
    *(_DWORD *)(a1 + 596) = 20;
  v9 = NbtReadSingleParameter(a2);
  v10 = 72;
  if ( v9 != 9 )
    v10 = 64;
  *(_WORD *)(a1 + 584) = v10;
  *(_BYTE *)(a1 + 569) = NbtReadSingleParameter(a2);
  v11 = NbtReadSingleParameter(a2);
  if ( (unsigned int)(v11 - 1) <= 0x2E )
  {
    NodeType |= 0x10u;
    RegistryNodeType |= 0x10u;
    dword_14003967C = v11;
  }
  v12 = NbtReadSingleParameter(a2);
  if ( (unsigned __int16)NbtGetProductType() == 1 )
  {
    v13 = 32;
    dword_1400394B4 = 32;
  }
  else
  {
    v13 = 256;
    dword_1400394B4 = 256;
  }
  if ( (NodeType & 0x10) != 0 )
    dword_1400394B4 = 2 * v13;
  dword_1400394B4 = NbtReadSingleParameter(a2);
  dword_1400396A4 = dword_1400394B4 + 2;
  v14 = v12 - 1;
  if ( !v14 )
    goto LABEL_20;
  v16 = v14 - 1;
  if ( !v16 )
  {
    *(_DWORD *)(a1 + 368) = 6553620;
    *(_DWORD *)(a1 + 372) = 8388864;
    *(_DWORD *)(a1 + 206) = 65537000;
    goto LABEL_22;
  }
  if ( v16 == 1 )
  {
    *(_DWORD *)(a1 + 368) = 0xFFFFFF;
    *(_DWORD *)(a1 + 372) = 16711936;
  }
  else
  {
LABEL_20:
    *(_DWORD *)(a1 + 368) = 655370;
    *(_DWORD *)(a1 + 372) = 1048832;
  }
  *(_DWORD *)(a1 + 206) = -1;
LABEL_22:
  ReadLmHostFile(a1);
  result = NbtReadSingleParameter(a2);
  *(_BYTE *)(a1 + 792) = result;
  return result;
}

```

## disassembly

```asm
0x14004abd4  push    rbx
0x14004abd6  push    rbp
0x14004abd7  push    rsi
0x14004abd8  push    rdi
0x14004abd9  push    r12
0x14004abdb  push    r13
0x14004abdd  push    r14
0x14004abdf  push    r15
0x14004abe1  sub     rsp, 28h
0x14004abe5  mov     rdi, rdx
0x14004abe8  mov     rbx, rcx
0x14004abeb  call    ReadParameters2
0x14004abf0  xor     r9d, r9d
0x14004abf3  lea     rdx, aNameserverport; "NameServerPort"
0x14004abfa  mov     r8d, 89h
0x14004ac00  mov     rcx, rdi; KeyHandle
0x14004ac03  call    NbtReadSingleParameter
0x14004ac08  mov     r14d, 3E8h
0x14004ac0e  mov     [rbx+1EAh], ax
0x14004ac15  mov     r9d, r14d
0x14004ac18  lea     rdx, aMaxpreloadentr; "MaxPreloadEntries"
0x14004ac1f  mov     r8d, r14d
0x14004ac22  mov     rcx, rdi; KeyHandle
0x14004ac25  call    NbtReadSingleParameter
0x14004ac2a  mov     ebp, 7D0h
0x14004ac2f  mov     [rbx+24Ch], eax
0x14004ac35  cmp     eax, ebp
0x14004ac37  ja      loc_14004B19F
0x14004ac3d  mov     esi, 0EA60h
0x14004ac42  lea     rdx, aCachetimeout; "CacheTimeout"
0x14004ac49  mov     r9d, esi
0x14004ac4c  mov     r8d, 57E40h
0x14004ac52  mov     rcx, rdi; KeyHandle
0x14004ac55  call    NbtReadSingleParameter
0x14004ac5a  mov     r8d, 0EA600h
0x14004ac60  mov     [rbx+1B8h], eax
0x14004ac66  mov     r9d, r8d
0x14004ac69  lea     rdx, aInitialrefresh; "InitialRefreshT.O."
0x14004ac70  mov     rcx, rdi; KeyHandle
0x14004ac73  call    NbtReadSingleParameter
0x14004ac78  xor     r9d, r9d
0x14004ac7b  mov     [rbx+1D4h], eax
0x14004ac81  mov     r8d, 1499700h
0x14004ac87  lea     rdx, aMinimumrefresh; "MinimumRefreshSleepTime"
0x14004ac8e  mov     rcx, rdi; KeyHandle
0x14004ac91  call    NbtReadSingleParameter
0x14004ac96  mov     [rbx+1C4h], eax
0x14004ac9c  call    IsDomainController
0x14004aca1  neg     eax
0x14004aca3  lea     rdx, aInbounddgramna; "InboundDgramNameCacheTimeout"
0x14004acaa  mov     r9d, ebp
0x14004acad  mov     rcx, rdi; KeyHandle
0x14004acb0  sbb     r8d, r8d
0x14004acb3  and     r8d, 32C8h
0x14004acba  add     r8d, ebp
0x14004acbd  call    NbtReadSingleParameter
0x14004acc2  mov     [rbx+1C0h], eax
0x14004acc8  mov     rax, 0FFFFF78000000014h
0x14004acd2  mov     rax, [rax]
0x14004acd5  mov     ecx, [rbx+1C0h]
0x14004acdb  shr     eax, 8
0x14004acde  and     eax, 1FFFFh
0x14004ace3  mov     [rbx+1BCh], eax
0x14004ace9  mov     eax, 66666667h
0x14004acee  imul    ecx
0x14004acf0  mov     r9d, edx
0x14004acf3  sar     r9d, 3
0x14004acf7  mov     eax, r9d
0x14004acfa  shr     eax, 1Fh
0x14004acfd  add     r9d, eax
0x14004ad00  mov     eax, 55555556h
0x14004ad05  imul    ecx
0x14004ad07  mov     rcx, rdi; KeyHandle
0x14004ad0a  mov     r8d, edx
0x14004ad0d  shr     r8d, 1Fh
0x14004ad11  add     r8d, edx
0x14004ad14  lea     rdx, aMaxnumnamecach; "MaxNumNameCache"
0x14004ad1b  call    NbtReadSingleParameter
0x14004ad20  mov     ebp, 1
0x14004ad25  mov     [rbx+1CCh], eax
0x14004ad2b  mov     r9d, ebp
0x14004ad2e  lea     rdx, aBcastnamequery; "BcastNameQueryCount"
0x14004ad35  mov     rcx, rdi; KeyHandle
0x14004ad38  lea     r15d, [rbp+2]
0x14004ad3c  mov     r8d, r15d
0x14004ad3f  call    NbtReadSingleParameter
0x14004ad44  lea     r13d, [rbp+63h]
0x14004ad48  mov     [rbx+19Ah], ax
0x14004ad4f  mov     r9d, r13d
0x14004ad52  lea     rdx, aBcastquerytime; "BcastQueryTimeout"
0x14004ad59  mov     r8d, 2EEh
0x14004ad5f  mov     rcx, rdi; KeyHandle
0x14004ad62  call    NbtReadSingleParameter
0x14004ad67  mov     r9d, ebp
0x14004ad6a  mov     [rbx+17Ch], eax
0x14004ad70  mov     r8d, r15d
0x14004ad73  lea     rdx, aNamesrvqueryco; "NameSrvQueryCount"
0x14004ad7a  mov     rcx, rdi; KeyHandle
0x14004ad7d  call    NbtReadSingleParameter
0x14004ad82  mov     r9d, r13d
0x14004ad85  mov     [rbx+198h], ax
0x14004ad8c  mov     r8d, 5DCh
0x14004ad92  lea     rdx, aNamesrvqueryti; "NameSrvQueryTimeout"
0x14004ad99  mov     rcx, rdi; KeyHandle
0x14004ad9c  call    NbtReadSingleParameter
0x14004ada1  mov     [rbx+180h], eax
0x14004ada7  lea     rdx, aSessionkeepali; "SessionKeepAlive"
0x14004adae  mov     r9d, esi
0x14004adb1  or      r8d, 0FFFFFFFFh
0x14004adb5  mov     rcx, rdi; KeyHandle
0x14004adb8  call    NbtReadSingleParameter
0x14004adbd  xor     r9d, r9d
0x14004adc0  mov     [rbx+1D8h], eax
0x14004adc6  xor     r8d, r8d
0x14004adc9  lea     rdx, aRandomadapter; "RandomAdapter"
0x14004add0  mov     rcx, rdi; KeyHandle
0x14004add3  call    NbtReadSingleParameter
0x14004add8  xor     r9d, r9d
0x14004addb  mov     [rbx+232h], al
0x14004ade1  xor     r8d, r8d
0x14004ade4  lea     rdx, aSingleresponse; "SingleResponse"
0x14004adeb  mov     rcx, rdi; KeyHandle
0x14004adee  call    NbtReadSingleParameter
0x14004adf3  xor     r9d, r9d
0x14004adf6  mov     [rbx+231h], al
0x14004adfc  xor     r8d, r8d
0x14004adff  lea     rdx, aNonamereleaseo; "NoNameReleaseOnDemand"
0x14004ae06  mov     rcx, rdi; KeyHandle
0x14004ae09  call    NbtReadSingleParameter
0x14004ae0e  xor     r9d, r9d
0x14004ae11  mov     [rbx+237h], al
0x14004ae17  mov     r8d, ebp
0x14004ae1a  lea     rdx, aCacheperadapte; "CachePerAdapterEnabled"
0x14004ae21  mov     rcx, rdi; KeyHandle
0x14004ae24  call    NbtReadSingleParameter
0x14004ae29  mov     [rbx+193h], al
0x14004ae2f  test    al, al
0x14004ae31  jz      loc_14004B1AA
0x14004ae37  xor     r9d, r9d
0x14004ae3a  lea     rdx, aConnectonreque; "ConnectOnRequestedInterfaceOnly"
0x14004ae41  xor     r8d, r8d
0x14004ae44  mov     rcx, rdi; KeyHandle
0x14004ae47  call    NbtReadSingleParameter
0x14004ae4c  xor     r9d, r9d
0x14004ae4f  mov     [rbx+194h], al
0x14004ae55  xor     r8d, r8d
0x14004ae58  lea     rdx, aSenddgramonreq; "SendDgramOnRequestedInterfaceOnly"
0x14004ae5f  mov     rcx, rdi; KeyHandle
0x14004ae62  call    NbtReadSingleParameter
0x14004ae67  xor     r9d, r9d
0x14004ae6a  mov     [rbx+195h], al
0x14004ae70  xor     r8d, r8d
0x14004ae73  mov     byte ptr [rbx+196h], 0
0x14004ae7a  lea     rdx, aMultiplecachef; "MultipleCacheFlags"
0x14004ae81  mov     rcx, rdi; KeyHandle
0x14004ae84  call    NbtReadSingleParameter
0x14004ae89  xor     r9d, r9d
0x14004ae8c  mov     [rbx+192h], al
0x14004ae92  xor     r8d, r8d
0x14004ae95  lea     rdx, aUsednsonlyforn; "UseDnsOnlyForNameResolutions"
0x14004ae9c  mov     rcx, rdi; KeyHandle
0x14004ae9f  call    NbtReadSingleParameter
0x14004aea4  mov     [rbx+236h], al
0x14004aeaa  test    al, al
0x14004aeac  jnz     loc_14004B1B1
0x14004aeb2  xor     r9d, r9d
0x14004aeb5  lea     rdx, aEnabledns; "EnableDns"
0x14004aebc  mov     r8d, ebp
0x14004aebf  mov     rcx, rdi; KeyHandle
0x14004aec2  call    NbtReadSingleParameter
0x14004aec7  xor     r9d, r9d
0x14004aeca  mov     [rbx+233h], al
0x14004aed0  xor     r8d, r8d
0x14004aed3  lea     rdx, aTryallnameserv; "TryAllNameServers"
0x14004aeda  mov     rcx, rdi; KeyHandle
0x14004aedd  call    NbtReadSingleParameter
0x14004aee2  xor     r9d, r9d
0x14004aee5  mov     [rbx+238h], al
0x14004aeeb  mov     r8d, ebp
0x14004aeee  lea     rdx, aSmbdisablenetb; "SmbDisableNetbiosNameCacheLookup"
0x14004aef5  mov     rcx, rdi; KeyHandle
0x14004aef8  call    NbtReadSingleParameter
0x14004aefd  mov     r9d, ebp
0x14004af00  mov     [rbx+234h], al
0x14004af06  mov     r8d, ebp
0x14004af09  lea     rdx, aTryallipaddrs; "TryAllIpAddrs"
0x14004af10  mov     rcx, rdi; KeyHandle
0x14004af13  call    NbtReadSingleParameter
0x14004af18  mov     r9d, r14d
0x14004af1b  mov     [rbx+235h], al
0x14004af21  mov     r8d, 1770h
0x14004af27  lea     rdx, aLmhoststimeout; "LmhostsTimeout"
0x14004af2e  mov     rcx, rdi; KeyHandle
0x14004af31  call    NbtReadSingleParameter
0x14004af36  mov     r8d, 20000h
0x14004af3c  mov     [rbx+208h], eax
0x14004af42  mov     r9d, r8d
0x14004af45  lea     rdx, aMaxdgrambuffer; "MaxDgramBuffering"
0x14004af4c  mov     rcx, rdi; KeyHandle
0x14004af4f  call    NbtReadSingleParameter
0x14004af54  xor     r9d, r9d
0x14004af57  mov     [rbx+204h], eax
0x14004af5d  xor     r8d, r8d
0x14004af60  lea     rdx, aEnableproxyreg; "EnableProxyRegCheck"
0x14004af67  mov     rcx, rdi; KeyHandle
0x14004af6a  call    NbtReadSingleParameter
0x14004af6f  mov     r9d, r14d
0x14004af72  mov     [rbx+23Ah], al
0x14004af78  mov     r8d, 3A98h
0x14004af7e  lea     rdx, aWinsdowntimeou; "WinsDownTimeout"
0x14004af85  mov     rcx, rdi; KeyHandle
0x14004af88  call    NbtReadSingleParameter
0x14004af8d  mov     r9d, 2
0x14004af93  mov     [rbx+1D0h], eax
0x14004af99  mov     r8d, r14d
0x14004af9c  lea     rdx, aMaxconnbacklog; "MaxConnBacklog"
0x14004afa3  mov     rcx, rdi; KeyHandle
0x14004afa6  call    NbtReadSingleParameter
0x14004afab  mov     r9d, r15d
0x14004afae  mov     [rbx+250h], eax
0x14004afb4  mov     r8d, r15d
0x14004afb7  lea     rdx, aBacklogincreme; "BacklogIncrement"
0x14004afbe  mov     rcx, rdi; KeyHandle
0x14004afc1  call    NbtReadSingleParameter
0x14004afc6  mov     r12d, 14h
0x14004afcc  mov     [rbx+254h], eax
0x14004afd2  mov     r9d, r12d
0x14004afd5  lea     rdx, aMinfreelowerco; "MinFreeLowerConnections"
0x14004afdc  mov     rcx, rdi; KeyHandle
0x14004afdf  lea     r8d, [r12+1Eh]
0x14004afe4  call    NbtReadSingleParameter
0x14004afe9  xor     r9d, r9d
0x14004afec  mov     [rbx+258h], eax
0x14004aff2  mov     r8d, ebp
0x14004aff5  lea     rdx, aBreakonassert; "BreakOnAssert"
0x14004affc  mov     rcx, rdi; KeyHandle
0x14004afff  call    NbtReadSingleParameter
0x14004b004  xor     r9d, r9d
0x14004b007  mov     [rbx+311h], al
0x14004b00d  xor     r8d, r8d
0x14004b010  lea     rdx, aCacheremotenam; "CacheRemoteNameOnDgramReceive"
0x14004b017  mov     rcx, rdi; KeyHandle
0x14004b01a  call    NbtReadSingleParameter
0x14004b01f  xor     r9d, r9d
0x14004b022  mov     [rbx+319h], al
0x14004b028  lea     r8d, [r12+37h]
0x14004b02d  mov     rcx, rdi; KeyHandle
0x14004b030  lea     rdx, aDhcpprocessing; "DhcpProcessingDelay"
0x14004b037  call    NbtReadSingleParameter
0x14004b03c  mov     [rbx+2E8h], eax
0x14004b042  mov     eax, 9C40h
0x14004b047  cmp     [rbx+250h], eax
0x14004b04d  ja      loc_14004B1BF
0x14004b053  cmp     [rbx+254h], r12d
0x14004b05a  ja      loc_14004B1CA
0x14004b060  mov     esi, 8
0x14004b065  lea     rdx, aRefreshopcode; "RefreshOpCode"
0x14004b06c  mov     r9d, esi
0x14004b06f  mov     r8d, esi
0x14004b072  mov     rcx, rdi; KeyHandle
0x14004b075  call    NbtReadSingleParameter
0x14004b07a  cmp     eax, 9
0x14004b07d  lea     ecx, [rsi+40h]
0x14004b080  lea     edx, [rsi+38h]
0x14004b083  mov     r8d, ebp
0x14004b086  cmovnz  cx, dx
0x14004b08a  xor     r9d, r9d
0x14004b08d  mov     [rbx+248h], cx
0x14004b094  lea     rdx, aEnablelmhosts; "EnableLmhosts"
0x14004b09b  mov     rcx, rdi; KeyHandle
0x14004b09e  call    NbtReadSingleParameter
0x14004b0a3  xor     r9d, r9d
0x14004b0a6  mov     [rbx+239h], al
0x14004b0ac  xor     r8d, r8d
0x14004b0af  lea     rdx, aEnableproxy; "EnableProxy"
0x14004b0b6  mov     rcx, rdi; KeyHandle
0x14004b0b9  call    NbtReadSingleParameter
0x14004b0be  lea     ebp, [rsi+8]
0x14004b0c1  lea     ecx, [rax-1]
0x14004b0c4  cmp     ecx, 2Eh ; '.'
0x14004b0c7  jbe     loc_14004B1D6
0x14004b0cd  movzx   r8d, cs:NodeType
0x14004b0d5  lea     rdx, aSizeSmallMediu; "Size/Small/Medium/Large"
0x14004b0dc  and     r8d, ebp
0x14004b0df  mov     rcx, rdi; KeyHandle
0x14004b0e2  or      r8d, esi
0x14004b0e5  shr     r8d, 3
0x14004b0e9  mov     r9d, r8d
0x14004b0ec  call    NbtReadSingleParameter
0x14004b0f1  mov     esi, eax
0x14004b0f3  call    NbtGetProductType
0x14004b0f8  mov     r15d, 100h
0x14004b0fe  cmp     ax, 1
0x14004b102  jnz     loc_14004B1EF
0x14004b108  mov     r8d, 20h ; ' '
0x14004b10e  mov     cs:dword_1400394B4, r8d
0x14004b115  test    byte ptr cs:NodeType, bpl
0x14004b11c  jnz     loc_14004B1FE
0x14004b122  mov     r9d, ebp
0x14004b125  lea     rdx, aPendingnameque; "PendingNameQueriesCount"
  ... truncated ...
```
