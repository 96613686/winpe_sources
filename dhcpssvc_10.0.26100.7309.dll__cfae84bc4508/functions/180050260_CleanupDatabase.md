# CleanupDatabase

- ea: `0x180050260`
- end: `0x180050701`
- name: `CleanupDatabase`
- size: `1185`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180051cfc`

## callees

- `0x180002854`
- `0x18000323c`
- `0x180003c9c`
- `0x18000d0c8`
- `0x18001d098`
- `0x1800251e4`
- `0x180025424`
- `0x180025b98`
- `0x18002955c`
- `0x18002ec9c`
- `0x18002f420`
- `0x18004fb4c`
- `0x180050260`
- `0x180050708`
- `0x180051920`
- `0x1800519fc`
- `0x180062964`
- `0x18008f044`
- `0x18008f540`
- `0x1800cc9e0`

## import_xrefs

- `msvcrt!_ltoa` at `0x180050590`
- `msvcrt!_ltoa` at `0x1800505a9`
- `msvcrt!_ltoa` at `0x180050590`
- `msvcrt!_ltoa` at `0x1800505a9`
- `KERNEL32!SetThreadPriority` at `0x1800502e7`
- `KERNEL32!SetThreadPriority` at `0x18005063d`
- `KERNEL32!SetThreadPriority` at `0x1800502e7`
- `KERNEL32!SetThreadPriority` at `0x18005063d`
- `KERNEL32!GetCurrentThread` at `0x1800502d2`
- `KERNEL32!GetCurrentThread` at `0x1800502d2`
- `KERNEL32!LocalFree` at `0x18005061d`
- `KERNEL32!LocalFree` at `0x18005062c`
- `KERNEL32!LocalFree` at `0x18005061d`
- `KERNEL32!LocalFree` at `0x18005062c`

## pseudocode

```c
__int64 __fastcall CleanupDatabase(FILETIME *a1, int a2)
{
  HANDLE CurrentThread; // r12
  __int64 v5; // rdx
  __int64 v6; // r8
  int String; // eax
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned int v10; // ebx
  unsigned int v11; // r14d
  unsigned int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // r8
  unsigned int v15; // eax
  unsigned int v16; // ebx
  unsigned int v17; // eax
  unsigned int v18; // ebx
  unsigned int v19; // esi
  unsigned int v20; // r15d
  char *v21; // r13
  __int64 v22; // rdi
  __int64 v23; // rcx
  __int64 v24; // rsi
  unsigned int v25; // r15d
  int *v26; // rdi
  int v27; // eax
  unsigned int v28; // eax
  __int64 v29; // rcx
  void *v30; // rcx
  unsigned int v32; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v33; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v34; // [rsp+48h] [rbp-B8h] BYREF
  char v35[16]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h]
  char *v37; // [rsp+68h] [rbp-98h]
  char *v38; // [rsp+70h] [rbp-90h]
  char Buffer[8]; // [rsp+78h] [rbp-88h] BYREF

  v33 = 0;
  v32 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids);
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, -1);
  v5 = 10000000LL * (unsigned int)DhcpLeaseExtension;
  v34 = *(_QWORD *)a1 - v5;
  String = GetString(1087, v5, v6);
  DhcpUpdateAuditLog(24, String, 0, 0, 0, 0);
  if ( *(_DWORD *)&isDhcpFailoverTestEnv && (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v8, &ScavengerStart, v9, 1, v35);
  v10 = CleanupIpDatabase(a1, (FILETIME *)&v34, a2, &v33, &v32);
  LogScavengeStats(v33, v32);
  v11 = 0;
  if ( v10 )
    v11 = v10;
  v12 = CleanupMCastDatabase(a1, (const FILETIME *)&v34, a2, &v33, &v32);
  if ( v12 )
    v11 = v12;
  LogScavengeStats(v33, v32);
  if ( *(_DWORD *)&isDhcpFailoverTestEnv && (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v13, &ScavengerEnd, v14, 1, v35);
  v15 = DhcpBackupConfiguration(DhcpGlobalBackupConfigFileName);
  v16 = v15;
  if ( v15 )
  {
    DhcpServerEventLog(1017, 1, v15);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, v16);
    v11 = v16;
  }
  v17 = DhcpBackupDatabase(DhcpGlobalOemJetBackupPath);
  v18 = v17;
  if ( v17 )
  {
    DhcpServerEventLog(1016, 1, v17);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, v18);
    v11 = v18;
  }
  AuditIPAddressUsage();
  RwLockAcquireForRead(&DhcpGlobalReadWriteLock);
  if ( DhcpGlobalThisServer )
  {
    v19 = DhcpGlobalThisServer == (LPVOID)-16LL ? 0 : *((_DWORD *)DhcpGlobalThisServer + 4);
    if ( v19 )
    {
      v20 = 0;
      v21 = (char *)DhcpGlobalThisServer + 16;
      v22 = 0;
      do
      {
        v23 = 0;
        if ( v21 )
        {
          v23 = *(_QWORD *)(*((_QWORD *)v21 + 1) + 8 * v22);
          if ( (unsigned int)(v22 + 1) < *(_DWORD *)v21 )
            v22 = (unsigned int)(v22 + 1);
        }
        if ( (unsigned int)DhcpSubnetGetPolicyMibCount(v23) )
          break;
        ++v20;
      }
      while ( v20 < v19 );
    }
  }
  RwLockRelease(&DhcpGlobalReadWriteLock);
  *(_QWORD *)Buffer = 0;
  if ( !(unsigned int)QueryMCastMibInfo(Buffer) )
  {
    v24 = *(_QWORD *)Buffer;
    v25 = 0;
    if ( *(_DWORD *)(*(_QWORD *)Buffer + 40LL) )
    {
      v26 = (int *)(*(_QWORD *)(*(_QWORD *)Buffer + 48LL) + 20LL);
      do
      {
        v27 = *(v26 - 1);
        if ( v27 || *v26 )
        {
          v28 = 100 * v27 / (unsigned int)(v27 + *v26);
          if ( v28 > DhcpGlobalAlertPercentage && *v26 < (unsigned int)DhcpGlobalAlertCount )
          {
            _ltoa(v28, Buffer, 10);
            _ltoa(*v26, v35, 10);
            v36 = DhcpUnicodeToOem(*(PCWSTR *)(v26 - 3));
            v37 = Buffer;
            v38 = v35;
            DhcpReportEventA(v29, 1020, 2);
          }
        }
        ++v25;
        v26 += 8;
      }
      while ( v25 < *(_DWORD *)(v24 + 40) );
    }
    v30 = *(void **)(v24 + 48);
    if ( v30 )
      LocalFree(v30);
    LocalFree((HLOCAL)v24);
  }
  SetThreadPriority(CurrentThread, 0);
  if ( (v18 || (v18 = v11) != 0) && v18 != 259 )
  {
    DhcpServerEventLog(1010, 1, v18);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, v18);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids);
  }
  return v11;
}

```

## disassembly

```asm
0x180050260  mov     [rsp-8+arg_10], rbx
0x180050265  push    rbp
0x180050266  push    rsi
0x180050267  push    rdi
0x180050268  push    r12
0x18005026a  push    r13
0x18005026c  push    r14
0x18005026e  push    r15
0x180050270  lea     rbp, [rsp-90h]
0x180050278  sub     rsp, 190h
0x18005027f  mov     rax, cs:__security_cookie
0x180050286  xor     rax, rsp
0x180050289  mov     [rbp+0C0h+var_40], rax
0x180050290  xor     r13d, r13d
0x180050293  mov     esi, edx
0x180050295  mov     [rsp+1C0h+var_17C], r13d
0x18005029a  mov     rdi, rcx
0x18005029d  mov     [rsp+1C0h+var_180], r13d
0x1800502a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800502a9  lea     rax, WPP_GLOBAL_Control
0x1800502b0  cmp     rcx, rax
0x1800502b3  jz      short loc_1800502D2
0x1800502b5  test    dword ptr [rcx+1Ch], 8000h
0x1800502bc  jz      short loc_1800502D2
0x1800502be  mov     rcx, [rcx+10h]
0x1800502c2  lea     edx, [r13+1Ah]
0x1800502c6  lea     r8, WPP_f0e25f423f3133668f92132b43c41a83_Traceguids
0x1800502cd  call    WPP_SF_
0x1800502d2  call    cs:__imp_GetCurrentThread
0x1800502d9  nop     dword ptr [rax+rax+00h]
0x1800502de  mov     rcx, rax; hThread
0x1800502e1  or      edx, 0FFFFFFFFh; nPriority
0x1800502e4  mov     r12, rax
0x1800502e7  call    cs:__imp_SetThreadPriority
0x1800502ee  nop     dword ptr [rax+rax+00h]
0x1800502f3  mov     ecx, cs:DhcpLeaseExtension
0x1800502f9  imul    rdx, rcx, 989680h
0x180050300  mov     rcx, [rdi]
0x180050303  sub     rcx, rdx
0x180050306  mov     [rsp+1C0h+var_178], rcx
0x18005030b  mov     ecx, 43Fh
0x180050310  call    GetString
0x180050315  xor     r9d, r9d
0x180050318  mov     [rsp+1C0h+var_198], r13
0x18005031d  mov     rdx, rax
0x180050320  mov     dword ptr [rsp+1C0h+var_1A0], r13d
0x180050325  xor     r8d, r8d
0x180050328  lea     ecx, [r9+18h]
0x18005032c  call    DhcpUpdateAuditLog
0x180050331  cmp     cs:isDhcpFailoverTestEnv, r13d
0x180050338  mov     r15d, 1
0x18005033e  jz      short loc_180050362
0x180050340  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, r15b
0x180050347  jz      short loc_180050362
0x180050349  lea     rax, [rsp+1C0h+var_170]
0x18005034e  mov     r9d, r15d
0x180050351  lea     rdx, ScavengerStart
0x180050358  mov     [rsp+1C0h+var_1A0], rax
0x18005035d  call    McGenEventWrite_EventWriteTransfer
0x180050362  lea     rax, [rsp+1C0h+var_180]
0x180050367  mov     r8d, esi
0x18005036a  lea     r9, [rsp+1C0h+var_17C]
0x18005036f  mov     [rsp+1C0h+var_1A0], rax
0x180050374  lea     rdx, [rsp+1C0h+var_178]
0x180050379  mov     rcx, rdi
0x18005037c  call    CleanupIpDatabase
0x180050381  mov     edx, [rsp+1C0h+var_180]
0x180050385  mov     ebx, eax
0x180050387  mov     ecx, [rsp+1C0h+var_17C]
0x18005038b  call    LogScavengeStats
0x180050390  lea     rax, [rsp+1C0h+var_180]
0x180050395  test    ebx, ebx
0x180050397  mov     r14d, r13d
0x18005039a  mov     [rsp+1C0h+var_1A0], rax
0x18005039f  lea     r9, [rsp+1C0h+var_17C]
0x1800503a4  mov     r8d, esi
0x1800503a7  lea     rdx, [rsp+1C0h+var_178]
0x1800503ac  mov     rcx, rdi
0x1800503af  cmovnz  r14d, ebx
0x1800503b3  call    CleanupMCastDatabase
0x1800503b8  mov     edx, [rsp+1C0h+var_180]
0x1800503bc  test    eax, eax
0x1800503be  mov     ecx, [rsp+1C0h+var_17C]
0x1800503c2  cmovnz  r14d, eax
0x1800503c6  call    LogScavengeStats
0x1800503cb  cmp     cs:isDhcpFailoverTestEnv, r13d
0x1800503d2  jz      short loc_1800503F6
0x1800503d4  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, r15b
0x1800503db  jz      short loc_1800503F6
0x1800503dd  lea     rax, [rsp+1C0h+var_170]
0x1800503e2  mov     r9d, r15d
0x1800503e5  lea     rdx, ScavengerEnd
0x1800503ec  mov     [rsp+1C0h+var_1A0], rax
0x1800503f1  call    McGenEventWrite_EventWriteTransfer
0x1800503f6  mov     rcx, cs:DhcpGlobalBackupConfigFileName; lpFileName
0x1800503fd  call    DhcpBackupConfiguration
0x180050402  mov     ebx, eax
0x180050404  test    eax, eax
0x180050406  jz      short loc_18005044E
0x180050408  mov     r8d, eax
0x18005040b  mov     edx, r15d
0x18005040e  mov     ecx, 3F9h
0x180050413  call    DhcpServerEventLog
0x180050418  mov     rcx, cs:WPP_GLOBAL_Control
0x18005041f  lea     rdi, WPP_GLOBAL_Control
0x180050426  cmp     rcx, rdi
0x180050429  jz      short loc_180050449
0x18005042b  test    byte ptr [rcx+1Ch], 10h
0x18005042f  jz      short loc_180050449
0x180050431  mov     rcx, [rcx+10h]
0x180050435  lea     r8, WPP_f0e25f423f3133668f92132b43c41a83_Traceguids
0x18005043c  mov     edx, 1Bh
0x180050441  mov     r9d, ebx
0x180050444  call    WPP_SF_D
0x180050449  mov     r14d, ebx
0x18005044c  jmp     short loc_180050455
0x18005044e  lea     rdi, WPP_GLOBAL_Control
0x180050455  mov     rcx, cs:DhcpGlobalOemJetBackupPath
0x18005045c  call    DhcpBackupDatabase
0x180050461  mov     ebx, eax
0x180050463  test    eax, eax
0x180050465  jz      short loc_1800504A4
0x180050467  mov     r8d, eax
0x18005046a  mov     edx, r15d
0x18005046d  mov     ecx, 3F8h
0x180050472  call    DhcpServerEventLog
0x180050477  mov     rcx, cs:WPP_GLOBAL_Control
0x18005047e  cmp     rcx, rdi
0x180050481  jz      short loc_1800504A1
0x180050483  test    byte ptr [rcx+1Ch], 10h
0x180050487  jz      short loc_1800504A1
0x180050489  mov     rcx, [rcx+10h]
0x18005048d  lea     r8, WPP_f0e25f423f3133668f92132b43c41a83_Traceguids
0x180050494  mov     edx, 1Ch
0x180050499  mov     r9d, ebx
0x18005049c  call    WPP_SF_D
0x1800504a1  mov     r14d, ebx
0x1800504a4  call    AuditIPAddressUsage
0x1800504a9  lea     rcx, DhcpGlobalReadWriteLock
0x1800504b0  call    RwLockAcquireForRead
0x1800504b5  mov     rax, cs:DhcpGlobalThisServer
0x1800504bc  test    rax, rax
0x1800504bf  jz      short loc_18005050F
0x1800504c1  lea     rsi, [rax+10h]
0x1800504c5  test    rsi, rsi
0x1800504c8  jnz     short loc_1800504CF
0x1800504ca  mov     esi, r13d
0x1800504cd  jmp     short loc_1800504D1
0x1800504cf  mov     esi, [rsi]
0x1800504d1  test    esi, esi
0x1800504d3  jz      short loc_18005050F
0x1800504d5  xor     r15d, r15d
0x1800504d8  lea     r13, [rax+10h]
0x1800504dc  test    esi, esi
0x1800504de  jz      short loc_18005050C
0x1800504e0  xor     edi, edi
0x1800504e2  xor     ecx, ecx
0x1800504e4  test    r13, r13
0x1800504e7  jz      short loc_1800504FB
0x1800504e9  mov     rax, [r13+8]
0x1800504ed  mov     rcx, [rax+rdi*8]
0x1800504f1  lea     eax, [rdi+1]
0x1800504f4  cmp     eax, [r13+0]
0x1800504f8  cmovb   edi, eax
0x1800504fb  call    DhcpSubnetGetPolicyMibCount
0x180050500  test    eax, eax
0x180050502  jnz     short loc_18005050C
0x180050504  inc     r15d
0x180050507  cmp     r15d, esi
0x18005050a  jb      short loc_1800504E2
0x18005050c  xor     r13d, r13d
0x18005050f  lea     rcx, DhcpGlobalReadWriteLock
0x180050516  call    RwLockRelease
0x18005051b  lea     rcx, [rsp+1C0h+Buffer]
0x180050520  mov     qword ptr [rsp+1C0h+Buffer], r13
0x180050525  call    QueryMCastMibInfo
0x18005052a  test    eax, eax
0x18005052c  jnz     loc_180050638
0x180050532  mov     rsi, qword ptr [rsp+1C0h+Buffer]
0x180050537  mov     r15d, r13d
0x18005053a  mov     rdi, [rsi+30h]
0x18005053e  cmp     [rsi+28h], r13d
0x180050542  jbe     loc_180050614
0x180050548  add     rdi, 14h
0x18005054c  mov     eax, [rdi-4]
0x18005054f  test    eax, eax
0x180050551  jnz     short loc_18005055C
0x180050553  cmp     [rdi], r13d
0x180050556  jz      loc_180050603
0x18005055c  mov     r8d, [rdi]
0x18005055f  xor     edx, edx
0x180050561  lea     ecx, [rax+r8]
0x180050565  imul    eax, 64h ; 'd'
0x180050568  div     ecx
0x18005056a  cmp     eax, cs:DhcpGlobalAlertPercentage
0x180050570  jbe     loc_180050603
0x180050576  cmp     r8d, cs:DhcpGlobalAlertCount
0x18005057d  jnb     loc_180050603
0x180050583  mov     r8d, 0Ah; Radix
0x180050589  lea     rdx, [rsp+1C0h+Buffer]; Buffer
0x18005058e  mov     ecx, eax; Value
0x180050590  call    cs:__imp__ltoa
0x180050597  nop     dword ptr [rax+rax+00h]
0x18005059c  mov     ecx, [rdi]; Value
0x18005059e  lea     rdx, [rsp+1C0h+var_170]; Buffer
0x1800505a3  mov     r8d, 0Ah; Radix
0x1800505a9  call    cs:__imp__ltoa
0x1800505b0  nop     dword ptr [rax+rax+00h]
0x1800505b5  mov     rcx, [rdi-0Ch]; SourceString
0x1800505b9  lea     rdx, [rbp+0C0h+var_140]
0x1800505bd  call    DhcpUnicodeToOem
0x1800505c2  mov     [rsp+1C0h+var_160], rax
0x1800505c7  mov     r9d, 3
0x1800505cd  lea     rax, [rsp+1C0h+Buffer]
0x1800505d2  mov     [rsp+1C0h+var_190], r13
0x1800505d7  mov     [rsp+1C0h+var_158], rax
0x1800505dc  mov     edx, 3FCh
0x1800505e1  lea     rax, [rsp+1C0h+var_170]
0x1800505e6  mov     [rsp+1C0h+var_150], rax
0x1800505eb  lea     r8d, [r9-1]
0x1800505ef  lea     rax, [rsp+1C0h+var_160]
0x1800505f4  mov     [rsp+1C0h+var_198], rax
0x1800505f9  mov     dword ptr [rsp+1C0h+var_1A0], r13d
0x1800505fe  call    DhcpReportEventA
0x180050603  inc     r15d
0x180050606  add     rdi, 20h ; ' '
0x18005060a  cmp     r15d, [rsi+28h]
0x18005060e  jb      loc_18005054C
0x180050614  mov     rcx, [rsi+30h]; hMem
0x180050618  test    rcx, rcx
0x18005061b  jz      short loc_180050629
0x18005061d  call    cs:__imp_LocalFree
0x180050624  nop     dword ptr [rax+rax+00h]
0x180050629  mov     rcx, rsi; hMem
0x18005062c  call    cs:__imp_LocalFree
0x180050633  nop     dword ptr [rax+rax+00h]
0x180050638  xor     edx, edx; nPriority
0x18005063a  mov     rcx, r12; hThread
0x18005063d  call    cs:__imp_SetThreadPriority
0x180050644  nop     dword ptr [rax+rax+00h]
0x180050649  test    ebx, ebx
0x18005064b  jnz     short loc_180050655
0x18005064d  mov     ebx, r14d
0x180050650  test    r14d, r14d
0x180050653  jz      short loc_1800506A2
0x180050655  cmp     ebx, 103h
0x18005065b  jz      short loc_1800506A2
0x18005065d  mov     r8d, ebx
0x180050660  mov     edx, 1
0x180050665  mov     ecx, 3F2h
0x18005066a  call    DhcpServerEventLog
0x18005066f  mov     rcx, cs:WPP_GLOBAL_Control
0x180050676  lea     rax, WPP_GLOBAL_Control
0x18005067d  cmp     rcx, rax
0x180050680  jz      short loc_1800506D3
0x180050682  test    byte ptr [rcx+1Ch], 10h
0x180050686  jz      short loc_1800506D3
0x180050688  mov     rcx, [rcx+10h]
0x18005068c  lea     r8, WPP_f0e25f423f3133668f92132b43c41a83_Traceguids
0x180050693  mov     edx, 1Dh
0x180050698  mov     r9d, ebx
0x18005069b  call    WPP_SF_D
0x1800506a0  jmp     short loc_1800506D3
0x1800506a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800506a9  lea     rax, WPP_GLOBAL_Control
0x1800506b0  cmp     rcx, rax
0x1800506b3  jz      short loc_1800506D3
0x1800506b5  test    dword ptr [rcx+1Ch], 8000h
0x1800506bc  jz      short loc_1800506D3
0x1800506be  mov     rcx, [rcx+10h]
0x1800506c2  lea     r8, WPP_f0e25f423f3133668f92132b43c41a83_Traceguids
0x1800506c9  mov     edx, 1Eh
0x1800506ce  call    WPP_SF_
0x1800506d3  mov     eax, r14d
0x1800506d6  mov     rcx, [rbp+0C0h+var_40]
0x1800506dd  xor     rcx, rsp; StackCookie
0x1800506e0  call    __security_check_cookie
0x1800506e5  mov     rbx, [rsp+1C0h+arg_10]
0x1800506ed  add     rsp, 190h
0x1800506f4  pop     r15
0x1800506f6  pop     r14
0x1800506f8  pop     r13
0x1800506fa  pop     r12
0x1800506fc  pop     rdi
0x1800506fd  pop     rsi
0x1800506fe  pop     rbp
0x1800506ff  retn
```
