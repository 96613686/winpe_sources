# DhcpUnplumbOldConfig

- ea: `0x180016458`
- end: `0x18001659d`
- name: `DhcpUnplumbOldConfig`
- size: `325`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024488`

## callees

- `0x180009108`
- `0x1800094f0`
- `0x1800095d8`
- `0x18000b28c`
- `0x18000b650`
- `0x180016458`
- `0x180016a30`
- `0x18003de84`
- `0x180040fd8`
- `0x18004a114`
- `0x18004d310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800164d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016506`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800164d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016506`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800164c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800164f3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800164c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800164f3`

## pseudocode

```c
__int64 __fastcall DhcpUnplumbOldConfig(__int64 a1)
{
  unsigned int v2; // edi
  __int64 v3; // rcx

  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_SJ(
      1025,
      55,
      (unsigned int)WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids,
      *(_QWORD *)(a1 + 56),
      *(_QWORD *)(a1 + 24));
  if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
    McTemplateU0z_EtwEventWriteTransfer(a1, UnplumbingStack, *(_QWORD *)(a1 + 56));
  TraceLogErrorv4(a1, 0, 57);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 672));
  *(_DWORD *)(a1 + 132) = *(_DWORD *)(a1 + 120);
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 672));
  if ( g_fVelocityStaticRouteCleanup )
  {
    DhcpDeleteGateways_New(a1);
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 672));
    v2 = DhcpClearAllOptions(a1);
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 672));
  }
  else
  {
    v2 = DhcpDeleteGatewaysAndStaticRoutes(a1);
  }
  if ( v2 || (v2 = UnplumbAddress(a1)) != 0 || (v2 = DhcpRegisterWithDns(a1, 1)) != 0 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_SD(1025, 56, (unsigned int)WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, *(_QWORD *)(a1 + 56), v2);
    if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 4) != 0 )
      McTemplateU0qq_EtwEventWriteTransfer(v3, PlumbingError, *(unsigned int *)(a1 + 48), v2);
    TraceLogErrorv4(a1, v2, 51);
  }
  return 0;
}

```

## disassembly

```asm
0x180016458  mov     [rsp+arg_0], rbx
0x18001645d  mov     [rsp+arg_8], rsi
0x180016462  push    rdi
0x180016463  sub     rsp, 30h
0x180016467  mov     rbx, rcx
0x18001646a  test    byte ptr cs:xmmword_1800616A0, 2
0x180016471  jz      short loc_180016496
0x180016473  mov     rax, [rbx+18h]
0x180016477  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x18001647e  mov     r9, [rbx+38h]
0x180016482  mov     edx, 37h ; '7'
0x180016487  mov     ecx, 401h
0x18001648c  mov     [rsp+38h+var_18], rax
0x180016491  call    WPP_SF_SJ
0x180016496  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x18001649d  jz      short loc_1800164AF
0x18001649f  mov     r8, [rbx+38h]
0x1800164a3  lea     rdx, UnplumbingStack
0x1800164aa  call    McTemplateU0z_EtwEventWriteTransfer
0x1800164af  xor     edx, edx
0x1800164b1  mov     rcx, rbx
0x1800164b4  lea     r8d, [rdx+39h]
0x1800164b8  call    TraceLogErrorv4
0x1800164bd  lea     rsi, [rbx+2A0h]
0x1800164c4  mov     rcx, rsi; SRWLock
0x1800164c7  call    cs:__imp_AcquireSRWLockExclusive
0x1800164cd  mov     eax, [rbx+78h]
0x1800164d0  mov     rcx, rsi; SRWLock
0x1800164d3  mov     [rbx+84h], eax
0x1800164d9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800164df  cmp     cs:g_fVelocityStaticRouteCleanup, 0
0x1800164e6  mov     rcx, rbx
0x1800164e9  jz      short loc_18001650E
0x1800164eb  call    DhcpDeleteGateways_New
0x1800164f0  mov     rcx, rsi; SRWLock
0x1800164f3  call    cs:__imp_AcquireSRWLockExclusive
0x1800164f9  mov     rcx, rbx
0x1800164fc  call    DhcpClearAllOptions
0x180016501  mov     rcx, rsi; SRWLock
0x180016504  mov     edi, eax
0x180016506  call    cs:__imp_ReleaseSRWLockExclusive
0x18001650c  jmp     short loc_180016515
0x18001650e  call    DhcpDeleteGatewaysAndStaticRoutes
0x180016513  mov     edi, eax
0x180016515  test    edi, edi
0x180016517  jnz     short loc_180016538
0x180016519  mov     rcx, rbx
0x18001651c  call    UnplumbAddress
0x180016521  mov     edi, eax
0x180016523  test    eax, eax
0x180016525  jnz     short loc_180016538
0x180016527  lea     edx, [rax+1]
0x18001652a  mov     rcx, rbx
0x18001652d  call    DhcpRegisterWithDns
0x180016532  mov     edi, eax
0x180016534  test    eax, eax
0x180016536  jz      short loc_18001658B
0x180016538  test    byte ptr cs:xmmword_1800616A0, 2
0x18001653f  jz      short loc_18001655F
0x180016541  mov     r9, [rbx+38h]
0x180016545  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x18001654c  mov     edx, 38h ; '8'
0x180016551  mov     dword ptr [rsp+38h+var_18], edi
0x180016555  mov     ecx, 401h
0x18001655a  call    WPP_SF_SD
0x18001655f  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 4
0x180016566  jz      short loc_18001657B
0x180016568  mov     r8d, [rbx+30h]
0x18001656c  lea     rdx, PlumbingError
0x180016573  mov     r9d, edi
0x180016576  call    McTemplateU0qq_EtwEventWriteTransfer
0x18001657b  mov     r8d, 33h ; '3'
0x180016581  mov     edx, edi
0x180016583  mov     rcx, rbx
0x180016586  call    TraceLogErrorv4
0x18001658b  mov     rbx, [rsp+38h+arg_0]
0x180016590  xor     eax, eax
0x180016592  mov     rsi, [rsp+38h+arg_8]
0x180016597  add     rsp, 30h
0x18001659b  pop     rdi
0x18001659c  retn
```
