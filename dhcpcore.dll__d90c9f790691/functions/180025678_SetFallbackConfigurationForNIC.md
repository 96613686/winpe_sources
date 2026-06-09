# SetFallbackConfigurationForNIC

- ea: `0x180025678`
- end: `0x1800258f5`
- name: `SetFallbackConfigurationForNIC`
- size: `637`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026bec`
- `0x18002f670`

## callees

- `0x180003a8c`
- `0x180009090`
- `0x18000b650`
- `0x180010430`
- `0x180015fec`
- `0x180016a30`
- `0x18001d826`
- `0x1800221a8`
- `0x1800232e8`
- `0x180025678`
- `0x18003df94`
- `0x18003e2f4`
- `0x180041110`
- `0x18004d1a0`
- `0x18004d310`
- `0x18004d4c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800257e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002587b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800257e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002587b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800256ee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025864`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800256ee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025864`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180025775`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180025775`

## pseudocode

```c
__int64 __fastcall SetFallbackConfigurationForNIC(__int64 a1)
{
  char v2; // r14
  __int64 v3; // r15
  int v4; // r12d
  unsigned int v5; // eax
  int v6; // r13d
  unsigned int v7; // edi
  ULONGLONG TickCount64; // rax
  int v9; // ecx
  __int128 v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[256]; // [rsp+40h] [rbp-C0h] BYREF
  int v13; // [rsp+150h] [rbp+50h] BYREF
  int v14; // [rsp+158h] [rbp+58h] BYREF

  v11 = 0;
  memset_0(v12, 0, 0xC8u);
  v2 = 0;
  v3 = 0;
  v4 = 0;
  v13 = 0;
  v14 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_q(1028, 76, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, *(_QWORD *)(a1 + 24));
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 672));
  v5 = DhcpCopyFallbackOptions(a1, &v13, &v14);
  v6 = v13;
  v7 = v5;
  if ( !v5 )
  {
    if ( *(_QWORD *)(a1 + 736) )
    {
      v4 = *(_DWORD *)(a1 + 744);
      v3 = *(_QWORD *)(a1 + 736);
      *(_DWORD *)(a1 + 744) = v5;
      v2 = 1;
      *(_QWORD *)(a1 + 736) = 0;
    }
    *((_QWORD *)&v11 + 1) = &v11;
    *(_QWORD *)&v11 = &v11;
    DhcpGetExpiredOptions(a1 + 696, &v11);
    DhcpDestroyOptionsList((unsigned int **)&v11);
    *(_DWORD *)(a1 + 796) = 2;
    TickCount64 = GetTickCount64();
    *(_DWORD *)(a1 + 124) = v14;
    *(_DWORD *)(a1 + 120) = v6;
    *(_DWORD *)(a1 + 440) = 0;
    *(_QWORD *)(a1 + 472) = 0x7FFFFFFFFFFFFFFFLL;
    *(_QWORD *)(a1 + 448) = TickCount64 / 0x3E8;
    *(_QWORD *)(a1 + 456) = TickCount64 / 0x3E8;
    *(_QWORD *)(a1 + 464) = TickCount64 / 0x3E8;
    DhcpSetAllRegistryParameters(a1, -1);
  }
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 672));
  if ( v7
    || (v7 = UnplumbAddress(a1)) != 0
    || (v7 = InitializeInterface(a1, 15)) != 0
    || (DhcpLoadCachedRoutes(a1, (__int64)v12), (v7 = DhcpNotifyDNSAndClients(a1, v12, 15)) != 0) )
  {
    DhcpUninitializeInterface(a1, 1);
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 78, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v7);
  }
  if ( v2 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 672));
    *(_QWORD *)(a1 + 736) = v3;
    *(_DWORD *)(a1 + 744) = v4;
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 672));
  }
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_SD(1025, 77, (unsigned int)WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, *(_QWORD *)(a1 + 56), v7);
  if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
    McTemplateU0qqq_EtwEventWriteTransfer(v9, (unsigned int)FallBackConfig, *(_DWORD *)(a1 + 48), v6, v7);
  TraceLogErrorv4(a1, v7, 65);
  return v7;
}

```

## disassembly

```asm
0x180025678  mov     [rsp-8+arg_10], rbx
0x18002567d  push    rbp
0x18002567e  push    rsi
0x18002567f  push    rdi
0x180025680  push    r12
0x180025682  push    r13
0x180025684  push    r14
0x180025686  push    r15
0x180025688  lea     rbp, [rsp-10h]
0x18002568d  sub     rsp, 110h
0x180025694  mov     rbx, rcx
0x180025697  xorps   xmm0, xmm0
0x18002569a  lea     rcx, [rsp+140h+var_100]; void *
0x18002569f  xor     edx, edx; Val
0x1800256a1  mov     r8d, 0C8h; Size
0x1800256a7  movups  [rsp+140h+var_110], xmm0
0x1800256ac  call    memset_0
0x1800256b1  xor     r14b, r14b
0x1800256b4  xor     r15d, r15d
0x1800256b7  xor     r12d, r12d
0x1800256ba  mov     [rbp+40h+arg_0], r12d
0x1800256be  mov     [rbp+40h+arg_8], r12d
0x1800256c2  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800256c9  jz      short loc_1800256E4
0x1800256cb  mov     r9, [rbx+18h]
0x1800256cf  lea     edx, [r15+4Ch]
0x1800256d3  mov     ecx, 404h
0x1800256d8  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x1800256df  call    WPP_SF_q
0x1800256e4  lea     rsi, [rbx+2A0h]
0x1800256eb  mov     rcx, rsi; SRWLock
0x1800256ee  call    cs:__imp_AcquireSRWLockExclusive
0x1800256f4  lea     r8, [rbp+40h+arg_8]
0x1800256f8  mov     rcx, rbx
0x1800256fb  lea     rdx, [rbp+40h+arg_0]
0x1800256ff  call    DhcpCopyFallbackOptions
0x180025704  mov     r13d, [rbp+40h+arg_0]
0x180025708  mov     edi, eax
0x18002570a  test    eax, eax
0x18002570c  jnz     loc_1800257DD
0x180025712  mov     rax, [rbx+2E0h]
0x180025719  test    rax, rax
0x18002571c  jz      short loc_18002573C
0x18002571e  mov     r12d, [rbx+2E8h]
0x180025725  mov     r15, rax
0x180025728  mov     [rbx+2E8h], edi
0x18002572e  mov     r14b, 1
0x180025731  mov     qword ptr [rbx+2E0h], 0
0x18002573c  lea     rax, [rsp+140h+var_110]
0x180025741  mov     qword ptr [rsp+140h+var_110+8], rax
0x180025746  lea     rcx, [rbx+2B8h]
0x18002574d  lea     rax, [rsp+140h+var_110]
0x180025752  lea     rdx, [rsp+140h+var_110]
0x180025757  mov     qword ptr [rsp+140h+var_110], rax
0x18002575c  call    DhcpGetExpiredOptions
0x180025761  lea     rcx, [rsp+140h+var_110]
0x180025766  call    DhcpDestroyOptionsList
0x18002576b  mov     dword ptr [rbx+31Ch], 2
0x180025775  call    cs:__imp_GetTickCount64
0x18002577b  mov     ecx, [rbp+40h+arg_8]
0x18002577e  mov     r8, rax
0x180025781  mov     [rbx+7Ch], ecx
0x180025784  mov     rax, 624DD2F1A9FBE77h
0x18002578e  mul     r8
0x180025791  mov     rax, 7FFFFFFFFFFFFFFFh
0x18002579b  mov     [rbx+78h], r13d
0x18002579f  sub     r8, rdx
0x1800257a2  mov     dword ptr [rbx+1B8h], 0
0x1800257ac  shr     r8, 1
0x1800257af  mov     rcx, rbx
0x1800257b2  add     r8, rdx
0x1800257b5  mov     [rbx+1D8h], rax
0x1800257bc  shr     r8, 9
0x1800257c0  or      edx, 0FFFFFFFFh
0x1800257c3  mov     [rbx+1C0h], r8
0x1800257ca  mov     [rbx+1C8h], r8
0x1800257d1  mov     [rbx+1D0h], r8
0x1800257d8  call    DhcpSetAllRegistryParameters
0x1800257dd  mov     rcx, rsi; SRWLock
0x1800257e0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800257e6  test    edi, edi
0x1800257e8  jnz     short loc_18002582D
0x1800257ea  mov     rcx, rbx
0x1800257ed  call    UnplumbAddress
0x1800257f2  mov     edi, eax
0x1800257f4  test    eax, eax
0x1800257f6  jnz     short loc_18002582D
0x1800257f8  lea     edx, [rax+0Fh]
0x1800257fb  mov     rcx, rbx
0x1800257fe  call    InitializeInterface
0x180025803  mov     edi, eax
0x180025805  test    eax, eax
0x180025807  jnz     short loc_18002582D
0x180025809  lea     rdx, [rsp+140h+var_100]
0x18002580e  mov     rcx, rbx
0x180025811  call    DhcpLoadCachedRoutes
0x180025816  lea     r8d, [rdi+0Fh]
0x18002581a  mov     rcx, rbx
0x18002581d  lea     rdx, [rsp+140h+var_100]
0x180025822  call    DhcpNotifyDNSAndClients
0x180025827  mov     edi, eax
0x180025829  test    eax, eax
0x18002582b  jz      short loc_18002585C
0x18002582d  mov     edx, 1
0x180025832  mov     rcx, rbx
0x180025835  call    DhcpUninitializeInterface
0x18002583a  test    byte ptr cs:xmmword_1800616A0, 2
0x180025841  jz      short loc_18002585C
0x180025843  mov     edx, 4Eh ; 'N'
0x180025848  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x18002584f  mov     ecx, 401h
0x180025854  mov     r9d, edi
0x180025857  call    WPP_SF_D
0x18002585c  test    r14b, r14b
0x18002585f  jz      short loc_180025881
0x180025861  mov     rcx, rsi; SRWLock
0x180025864  call    cs:__imp_AcquireSRWLockExclusive
0x18002586a  mov     rcx, rsi; SRWLock
0x18002586d  mov     [rbx+2E0h], r15
0x180025874  mov     [rbx+2E8h], r12d
0x18002587b  call    cs:__imp_ReleaseSRWLockExclusive
0x180025881  test    byte ptr cs:xmmword_1800616A0, 2
0x180025888  jz      short loc_1800258A8
0x18002588a  mov     r9, [rbx+38h]
0x18002588e  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180025895  mov     edx, 4Dh ; 'M'
0x18002589a  mov     [rsp+140h+var_120], edi
0x18002589e  mov     ecx, 401h
0x1800258a3  call    WPP_SF_SD
0x1800258a8  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x1800258af  jz      short loc_1800258C8
0x1800258b1  mov     r8d, [rbx+30h]
0x1800258b5  lea     rdx, FallBackConfig
0x1800258bc  mov     r9d, r13d
0x1800258bf  mov     [rsp+140h+var_120], edi
0x1800258c3  call    McTemplateU0qqq_EtwEventWriteTransfer
0x1800258c8  mov     r8d, 41h ; 'A'
0x1800258ce  mov     edx, edi
0x1800258d0  mov     rcx, rbx
0x1800258d3  call    TraceLogErrorv4
0x1800258d8  mov     rbx, [rsp+140h+arg_10]
0x1800258e0  mov     eax, edi
0x1800258e2  add     rsp, 110h
0x1800258e9  pop     r15
0x1800258eb  pop     r14
0x1800258ed  pop     r13
0x1800258ef  pop     r12
0x1800258f1  pop     rdi
0x1800258f2  pop     rsi
0x1800258f3  pop     rbp
0x1800258f4  retn
```
