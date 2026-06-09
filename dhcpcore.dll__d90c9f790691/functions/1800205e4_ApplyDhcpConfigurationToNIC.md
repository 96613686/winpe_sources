# ApplyDhcpConfigurationToNIC

- ea: `0x1800205e4`
- end: `0x18002072d`
- name: `ApplyDhcpConfigurationToNIC`
- size: `329`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `5`
- callee_count: `17`
- tags: `registry_config, installer_update`

## callers

- `0x180021128`
- `0x180024488`
- `0x18002fedc`
- `0x180030b4c`
- `0x1800327f0`

## callees

- `0x18000b28c`
- `0x18000c7dc`
- `0x18000cc70`
- `0x18000cf2c`
- `0x180015fec`
- `0x180016a30`
- `0x180017e68`
- `0x1800205e4`
- `0x1800232e8`
- `0x180024de8`
- `0x180036bb8`
- `0x18003da30`
- `0x18003de84`
- `0x18003e228`
- `0x180040fd8`
- `0x18004d958`
- `0x18004d9a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800206ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800206ee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800206dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800206dd`

## pseudocode

```c
__int64 __fastcall ApplyDhcpConfigurationToNIC(__int64 a1, __int64 a2, int a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // esi
  int v9; // [rsp+70h] [rbp+18h] BYREF

  v9 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_Jl(a1, 60, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, *(_QWORD *)(a1 + 24), a3);
  DhcpSetAllRegistryParameters(a1, *(unsigned int *)(a1 + 128));
  if ( !a3 )
    ForceNetbtRegistryRead(*(_QWORD *)(a1 + 56));
  NetBTNotifyRegChanges(*(_QWORD *)(a1 + 56));
  if ( a3 )
  {
    v6 = 0;
    UnplumbAddress(a1);
  }
  else
  {
    DhcpRefreshLifetime(a1);
    RecordAddressPlumbedEndEvent(a1);
    v6 = 16;
  }
  v7 = DhcpApplyRouting(a1, a2, &v9);
  if ( v7 || a3 && (v6 |= 0xCu, (v7 = InitializeInterface(a1, v6)) != 0) )
  {
    if ( !*(_DWORD *)(a1 + 776) )
    {
      if ( g_fVelocityStaticRouteCleanup )
      {
        DhcpDeleteGateways_New(a1);
        AcquireSRWLockExclusive((PSRWLOCK)(a1 + 672));
        DhcpClearAllOptions(a1);
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 672));
      }
      else
      {
        DhcpDeleteGatewaysAndStaticRoutes(a1);
      }
    }
  }
  else
  {
    DhcpNotifyDNS(a1, v6);
    if ( v9 )
    {
      RetrieveHwAddressesForGateways(a1);
      UpdateRegistryforReachableGateway(a1);
    }
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_qD(1028, 61, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, *(_QWORD *)(a1 + 24), v7);
  return v7;
}

```

## disassembly

```asm
0x1800205e4  push    rbx
0x1800205e6  push    rbp
0x1800205e7  push    rsi
0x1800205e8  push    rdi
0x1800205e9  sub     rsp, 38h
0x1800205ed  mov     ebp, r8d
0x1800205f0  mov     [rsp+58h+arg_10], 0
0x1800205f8  mov     rsi, rdx
0x1800205fb  mov     rdi, rcx
0x1800205fe  test    byte ptr cs:xmmword_1800616A0, 10h
0x180020605  jz      short loc_180020621
0x180020607  mov     r9, [rcx+18h]
0x18002060b  mov     edx, 3Ch ; '<'
0x180020610  mov     [rsp+58h+var_38], r8d
0x180020615  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x18002061c  call    WPP_SF_Jl
0x180020621  mov     edx, [rdi+80h]
0x180020627  mov     rcx, rdi
0x18002062a  call    DhcpSetAllRegistryParameters
0x18002062f  test    ebp, ebp
0x180020631  jnz     short loc_18002063C
0x180020633  mov     rcx, [rdi+38h]
0x180020637  call    ForceNetbtRegistryRead
0x18002063c  mov     rcx, [rdi+38h]
0x180020640  call    NetBTNotifyRegChanges
0x180020645  mov     rcx, rdi
0x180020648  test    ebp, ebp
0x18002064a  jz      short loc_180020655
0x18002064c  xor     ebx, ebx
0x18002064e  call    UnplumbAddress
0x180020653  jmp     short loc_180020667
0x180020655  call    DhcpRefreshLifetime
0x18002065a  mov     rcx, rdi
0x18002065d  call    RecordAddressPlumbedEndEvent
0x180020662  mov     ebx, 10h
0x180020667  lea     r8, [rsp+58h+arg_10]
0x18002066c  mov     rdx, rsi
0x18002066f  mov     rcx, rdi
0x180020672  call    DhcpApplyRouting
0x180020677  mov     esi, eax
0x180020679  test    eax, eax
0x18002067b  jnz     short loc_1800206B9
0x18002067d  test    ebp, ebp
0x18002067f  jz      short loc_180020694
0x180020681  or      ebx, 0Ch
0x180020684  mov     rcx, rdi
0x180020687  mov     edx, ebx
0x180020689  call    InitializeInterface
0x18002068e  mov     esi, eax
0x180020690  test    eax, eax
0x180020692  jnz     short loc_1800206B9
0x180020694  mov     edx, ebx
0x180020696  mov     rcx, rdi
0x180020699  call    DhcpNotifyDNS
0x18002069e  cmp     [rsp+58h+arg_10], 0
0x1800206a3  jz      short loc_1800206FB
0x1800206a5  mov     rcx, rdi
0x1800206a8  call    RetrieveHwAddressesForGateways
0x1800206ad  mov     rcx, rdi
0x1800206b0  call    UpdateRegistryforReachableGateway
0x1800206b5  test    esi, esi
0x1800206b7  jz      short loc_1800206FB
0x1800206b9  mov     eax, [rdi+308h]
0x1800206bf  test    eax, eax
0x1800206c1  jnz     short loc_1800206FB
0x1800206c3  cmp     cs:g_fVelocityStaticRouteCleanup, eax
0x1800206c9  mov     rcx, rdi
0x1800206cc  jz      short loc_1800206F6
0x1800206ce  call    DhcpDeleteGateways_New
0x1800206d3  lea     rbx, [rdi+2A0h]
0x1800206da  mov     rcx, rbx; SRWLock
0x1800206dd  call    cs:__imp_AcquireSRWLockExclusive
0x1800206e3  mov     rcx, rdi
0x1800206e6  call    DhcpClearAllOptions
0x1800206eb  mov     rcx, rbx; SRWLock
0x1800206ee  call    cs:__imp_ReleaseSRWLockExclusive
0x1800206f4  jmp     short loc_1800206FB
0x1800206f6  call    DhcpDeleteGatewaysAndStaticRoutes
0x1800206fb  test    byte ptr cs:xmmword_1800616A0, 10h
0x180020702  jz      short loc_180020722
0x180020704  mov     r9, [rdi+18h]
0x180020708  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x18002070f  mov     edx, 3Dh ; '='
0x180020714  mov     [rsp+58h+var_38], esi
0x180020718  mov     ecx, 404h
0x18002071d  call    WPP_SF_qD
0x180020722  mov     eax, esi
0x180020724  add     rsp, 38h
0x180020728  pop     rdi
0x180020729  pop     rsi
0x18002072a  pop     rbp
0x18002072b  pop     rbx
0x18002072c  retn
```
