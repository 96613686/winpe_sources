# CleanupDatabase

- ea: `0x18004ff20`
- end: `0x1800503c1`
- name: `CleanupDatabase`
- size: `1185`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180051a00`

## callees

- `0x18000282c`
- `0x180003228`
- `0x180003c90`
- `0x18000c770`
- `0x18001c63c`
- `0x180024720`
- `0x180024960`
- `0x1800250e8`
- `0x180028b08`
- `0x18002e2b4`
- `0x18002e9f4`
- `0x18004f7fc`
- `0x18004ff20`
- `0x1800503c8`
- `0x180051620`
- `0x1800516fc`
- `0x1800626dc`
- `0x18008f1c0`
- `0x18008f6d8`
- `0x1800cdac0`

## import_xrefs

- `msvcrt!_ltoa` at `0x180050250`
- `msvcrt!_ltoa` at `0x180050269`
- `msvcrt!_ltoa` at `0x180050250`
- `msvcrt!_ltoa` at `0x180050269`
- `KERNEL32!SetThreadPriority` at `0x18004ffa7`
- `KERNEL32!SetThreadPriority` at `0x1800502fd`
- `KERNEL32!SetThreadPriority` at `0x18004ffa7`
- `KERNEL32!SetThreadPriority` at `0x1800502fd`
- `KERNEL32!GetCurrentThread` at `0x18004ff92`
- `KERNEL32!GetCurrentThread` at `0x18004ff92`
- `KERNEL32!LocalFree` at `0x1800502dd`
- `KERNEL32!LocalFree` at `0x1800502ec`
- `KERNEL32!LocalFree` at `0x1800502dd`
- `KERNEL32!LocalFree` at `0x1800502ec`

## pseudocode

```c
__int64 __fastcall CleanupDatabase(FILETIME *a1, int a2)
{
  HANDLE CurrentThread; // r12
  int String; // eax
  __int64 v6; // rcx
  __int64 v7; // r8
  unsigned int v8; // ebx
  unsigned int v9; // r14d
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r8
  unsigned int v13; // eax
  unsigned int v14; // ebx
  unsigned int v15; // eax
  unsigned int v16; // ebx
  unsigned int v17; // edi
  unsigned int v18; // r15d
  char *v19; // r13
  __int64 v20; // rsi
  __int64 v21; // rcx
  __int64 v22; // rsi
  unsigned int v23; // r15d
  int *v24; // rdi
  int v25; // eax
  unsigned int v26; // eax
  __int64 v27; // rcx
  void *v28; // rcx
  unsigned int v30; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v31; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  char v33[16]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v34[3]; // [rsp+60h] [rbp-A0h] BYREF
  char Buffer[8]; // [rsp+78h] [rbp-88h] BYREF

  v31 = 0;
  v30 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids);
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, -1);
  v32 = *(_QWORD *)a1 - 10000000LL * (unsigned int)DhcpLeaseExtension;
  String = GetString(1087);
  DhcpUpdateAuditLog(24, String, 0, 0, 0, 0);
  if ( *(_DWORD *)&isDhcpFailoverTestEnv && (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v6, &ScavengerStart, v7, 1, v33);
  v8 = CleanupIpDatabase(a1, (FILETIME *)&v32, a2, &v31, &v30);
  LogScavengeStats(v31, v30);
  v9 = 0;
  if ( v8 )
    v9 = v8;
  v10 = CleanupMCastDatabase(a1, (const FILETIME *)&v32, a2, &v31, &v30);
  if ( v10 )
    v9 = v10;
  LogScavengeStats(v31, v30);
  if ( *(_DWORD *)&isDhcpFailoverTestEnv && (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v11, &ScavengerEnd, v12, 1, v33);
  v13 = DhcpBackupConfiguration(DhcpGlobalBackupConfigFileName);
  v14 = v13;
  if ( v13 )
  {
    DhcpServerEventLog(1017, 1, v13);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, v14);
    v9 = v14;
  }
  v15 = DhcpBackupDatabase(DhcpGlobalOemJetBackupPath);
  v16 = v15;
  if ( v15 )
  {
    DhcpServerEventLog(1016, 1, v15);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, v16);
    v9 = v16;
  }
  AuditIPAddressUsage();
  RwLockAcquireForRead(&DhcpGlobalReadWriteLock);
  if ( DhcpGlobalThisServer )
  {
    v17 = DhcpGlobalThisServer == (LPVOID)-16LL ? 0 : *((_DWORD *)DhcpGlobalThisServer + 4);
    if ( v17 )
    {
      v18 = 0;
      v19 = (char *)DhcpGlobalThisServer + 16;
      v20 = 0;
      do
      {
        v21 = 0;
        if ( v19 )
        {
          v21 = *(_QWORD *)(*((_QWORD *)v19 + 1) + 8 * v20);
          if ( (unsigned int)(v20 + 1) < *(_DWORD *)v19 )
            v20 = (unsigned int)(v20 + 1);
        }
        if ( (unsigned int)DhcpSubnetGetPolicyMibCount(v21) )
          break;
        ++v18;
      }
      while ( v18 < v17 );
    }
  }
  RwLockRelease(&DhcpGlobalReadWriteLock);
  *(_QWORD *)Buffer = 0;
  if ( !(unsigned int)QueryMCastMibInfo(Buffer) )
  {
    v22 = *(_QWORD *)Buffer;
    v23 = 0;
    if ( *(_DWORD *)(*(_QWORD *)Buffer + 40LL) )
    {
      v24 = (int *)(*(_QWORD *)(*(_QWORD *)Buffer + 48LL) + 20LL);
      do
      {
        v25 = *(v24 - 1);
        if ( v25 || *v24 )
        {
          v26 = 100 * v25 / (unsigned int)(*v24 + v25);
          if ( v26 > DhcpGlobalAlertPercentage && *v24 < (unsigned int)DhcpGlobalAlertCount )
          {
            _ltoa(v26, Buffer, 10);
            _ltoa(*v24, v33, 10);
            v34[0] = DhcpUnicodeToOem(*(PCWSTR *)(v24 - 3));
            v34[1] = Buffer;
            v34[2] = v33;
            DhcpReportEventA(v27, 1020, 2, 3, 0, v34, 0);
          }
        }
        ++v23;
        v24 += 8;
      }
      while ( v23 < *(_DWORD *)(v22 + 40) );
    }
    v28 = *(void **)(v22 + 48);
    if ( v28 )
      LocalFree(v28);
    LocalFree((HLOCAL)v22);
  }
  SetThreadPriority(CurrentThread, 0);
  if ( (v16 || (v16 = v9) != 0) && v16 != 259 )
  {
    DhcpServerEventLog(1010, 1, v16);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids, v16);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_f0e25f423f3133668f92132b43c41a83_Traceguids);
  }
  return v9;
}

```

## disassembly

```asm
0x18004ff20  mov     [rsp-8+arg_10], rbx
0x18004ff25  push    rbp
0x18004ff26  push    rsi
0x18004ff27  push    rdi
0x18004ff28  push    r12
0x18004ff2a  push    r13
0x18004ff2c  push    r14
0x18004ff2e  push    r15
0x18004ff30  lea     rbp, [rsp-90h]
0x18004ff38  sub     rsp, 190h
0x18004ff3f  mov     rax, cs:__security_cookie
0x18004ff46  xor     rax, rsp
0x18004ff49  mov     [rbp+0C0h+var_40], rax
0x18004ff50  xor     r13d, r13d
0x18004ff53  mov     esi, edx
0x18004ff55  mov     [rsp+1C0h+var_17C], r13d
0x18004ff5a  mov     rdi, rcx
0x18004ff5d  mov     [rsp+1C0h+var_180], r13d
0x18004ff62  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ff69  lea     rax, WPP_GLOBAL_Control
0x18004ff70  cmp     rcx, rax
0x18004ff73  jz      short loc_18004FF92
0x18004ff75  test    dword ptr [rcx+1Ch], 8000h
0x18004ff7c  jz      short loc_18004FF92
0x18004ff7e  mov     rcx, [rcx+10h]
0x18004ff82  lea     edx, [r13+1Ah]
0x18004ff86  lea     r8, WPP_f0e25f423f3133668f92132b43c41a83_Traceguids
0x18004ff8d  call    WPP_SF_
0x18004ff92  call    cs:__imp_GetCurrentThread
0x18004ff99  nop     dword ptr [rax+rax+00h]
0x18004ff9e  mov     rcx, rax; hThread
0x18004ffa1  or      edx, 0FFFFFFFFh; nPriority
0x18004ffa4  mov     r12, rax
0x18004ffa7  call    cs:__imp_SetThreadPriority
0x18004ffae  nop     dword ptr [rax+rax+00h]
0x18004ffb3  mov     ecx, cs:DhcpLeaseExtension
0x18004ffb9  imul    rdx, rcx, 989680h
0x18004ffc0  mov     rcx, [rdi]
0x18004ffc3  sub     rcx, rdx
0x18004ffc6  mov     [rsp+1C0h+var_178], rcx
0x18004ffcb  mov     ecx, 43Fh
0x18004ffd0  call    GetString
0x18004ffd5  xor     r9d, r9d
0x18004ffd8  mov     [rsp+1C0h+var_198], r13
0x18004ffdd  mov     rdx, rax
0x18004ffe0  mov     dword ptr [rsp+1C0h+var_1A0], r13d
0x18004ffe5  xor     r8d, r8d
0x18004ffe8  lea     ecx, [r9+18h]
0x18004ffec  call    DhcpUpdateAuditLog
0x18004fff1  cmp     cs:isDhcpFailoverTestEnv, r13d
0x18004fff8  mov     r15d, 1
0x18004fffe  jz      short loc_180050022
0x180050000  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, r15b
0x180050007  jz      short loc_180050022
0x180050009  lea     rax, [rsp+1C0h+var_170]
0x18005000e  mov     r9d, r15d
0x180050011  lea     rdx, ScavengerStart
0x180050018  mov     [rsp+1C0h+var_1A0], rax
0x18005001d  call    McGenEventWrite_EventWriteTransfer
0x180050022  lea     rax, [rsp+1C0h+var_180]
0x180050027  mov     r8d, esi
0x18005002a  lea     r9, [rsp+1C0h+var_17C]
0x18005002f  mov     [rsp+1C0h+var_1A0], rax
0x180050034  lea     rdx, [rsp+1C0h+var_178]
0x180050039  mov     rcx, rdi
0x18005003c  call    CleanupIpDatabase
0x180050041  mov     edx, [rsp+1C0h+var_180]
0x180050045  mov     ebx, eax
0x180050047  mov     ecx, [rsp+1C0h+var_17C]
0x18005004b  call    LogScavengeStats
0x180050050  lea     rax, [rsp+1C0h+var_180]
0x180050055  test    ebx, ebx
0x180050057  mov     r14d, r13d
0x18005005a  mov     [rsp+1C0h+var_1A0], rax
0x18005005f  lea     r9, [rsp+1C0h+var_17C]
0x180050064  mov     r8d, esi
0x180050067  lea     rdx, [rsp+1C0h+var_178]
0x18005006c  mov     rcx, rdi
0x18005006f  cmovnz  r14d, ebx
0x180050073  call    CleanupMCastDatabase
0x180050078  mov     edx, [rsp+1C0h+var_180]
0x18005007c  test    eax, eax
0x18005007e  mov     ecx, [rsp+1C0h+var_17C]
0x180050082  cmovnz  r14d, eax
0x180050086  call    LogScavengeStats
0x18005008b  cmp     cs:isDhcpFailoverTestEnv, r13d
0x180050092  jz      short loc_1800500B6
0x180050094  test    cs:Microsoft_Windows_DHCP_ServerEnableBits, r15b
0x18005009b  jz      short loc_1800500B6
0x18005009d  lea     rax, [rsp+1C0h+var_170]
0x1800500a2  mov     r9d, r15d
0x1800500a5  lea     rdx, ScavengerEnd
0x1800500ac  mov     [rsp+1C0h+var_1A0], rax
0x1800500b1  call    McGenEventWrite_EventWriteTransfer
0x1800500b6  mov     rcx, cs:DhcpGlobalBackupConfigFileName; lpFileName
0x1800500bd  call    DhcpBackupConfiguration
0x1800500c2  mov     ebx, eax
0x1800500c4  test    eax, eax
0x1800500c6  jz      short loc_18005010E
0x1800500c8  mov     r8d, eax
0x1800500cb  mov     edx, r15d
0x1800500ce  mov     ecx, 3F9h
0x1800500d3  call    DhcpServerEventLog
0x1800500d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800500df  lea     rdi, WPP_GLOBAL_Control
0x1800500e6  cmp     rcx, rdi
0x1800500e9  jz      short loc_180050109
0x1800500eb  test    byte ptr [rcx+1Ch], 10h
0x1800500ef  jz      short loc_180050109
0x1800500f1  mov     rcx, [rcx+10h]
0x1800500f5  lea     r8, WPP_f0e25f423f3133668f92132b43c41a83_Traceguids
0x1800500fc  mov     edx, 1Bh
0x180050101  mov     r9d, ebx
0x180050104  call    WPP_SF_D
0x180050109  mov     r14d, ebx
0x18005010c  jmp     short loc_180050115
0x18005010e  lea     rdi, WPP_GLOBAL_Control
0x180050115  mov     rcx, cs:DhcpGlobalOemJetBackupPath
0x18005011c  call    DhcpBackupDatabase
0x180050121  mov     ebx, eax
0x180050123  test    eax, eax
0x180050125  jz      short loc_180050164
0x180050127  mov     r8d, eax
0x18005012a  mov     edx, r15d
0x18005012d  mov     ecx, 3F8h
0x180050132  call    DhcpServerEventLog
0x180050137  mov     rcx, cs:WPP_GLOBAL_Control
0x18005013e  cmp     rcx, rdi
0x180050141  jz      short loc_180050161
0x180050143  test    byte ptr [rcx+1Ch], 10h
0x180050147  jz      short loc_180050161
0x180050149  mov     rcx, [rcx+10h]
0x18005014d  lea     r8, WPP_f0e25f423f3133668f92132b43c41a83_Traceguids
0x180050154  mov     edx, 1Ch
0x180050159  mov     r9d, ebx
0x18005015c  call    WPP_SF_D
0x180050161  mov     r14d, ebx
0x180050164  call    AuditIPAddressUsage
0x180050169  lea     rcx, DhcpGlobalReadWriteLock
0x180050170  call    RwLockAcquireForRead
0x180050175  mov     rax, cs:DhcpGlobalThisServer
0x18005017c  test    rax, rax
0x18005017f  jz      short loc_1800501CF
0x180050181  lea     rdi, [rax+10h]
0x180050185  test    rdi, rdi
0x180050188  jnz     short loc_18005018F
0x18005018a  mov     edi, r13d
0x18005018d  jmp     short loc_180050191
0x18005018f  mov     edi, [rdi]
0x180050191  test    edi, edi
0x180050193  jz      short loc_1800501CF
0x180050195  xor     r15d, r15d
0x180050198  lea     r13, [rax+10h]
0x18005019c  test    edi, edi
0x18005019e  jz      short loc_1800501CC
0x1800501a0  xor     esi, esi
0x1800501a2  xor     ecx, ecx
0x1800501a4  test    r13, r13
0x1800501a7  jz      short loc_1800501BB
0x1800501a9  mov     rax, [r13+8]
0x1800501ad  mov     rcx, [rax+rsi*8]
0x1800501b1  lea     eax, [rsi+1]
0x1800501b4  cmp     eax, [r13+0]
0x1800501b8  cmovb   esi, eax
0x1800501bb  call    DhcpSubnetGetPolicyMibCount
0x1800501c0  test    eax, eax
0x1800501c2  jnz     short loc_1800501CC
0x1800501c4  inc     r15d
0x1800501c7  cmp     r15d, edi
0x1800501ca  jb      short loc_1800501A2
0x1800501cc  xor     r13d, r13d
0x1800501cf  lea     rcx, DhcpGlobalReadWriteLock
0x1800501d6  call    RwLockRelease
0x1800501db  lea     rcx, [rsp+1C0h+Buffer]
0x1800501e0  mov     qword ptr [rsp+1C0h+Buffer], r13
0x1800501e5  call    QueryMCastMibInfo
0x1800501ea  test    eax, eax
0x1800501ec  jnz     loc_1800502F8
0x1800501f2  mov     rsi, qword ptr [rsp+1C0h+Buffer]
0x1800501f7  mov     r15d, r13d
0x1800501fa  mov     rdi, [rsi+30h]
0x1800501fe  cmp     [rsi+28h], r13d
0x180050202  jbe     loc_1800502D4
0x180050208  add     rdi, 14h
0x18005020c  mov     eax, [rdi-4]
0x18005020f  test    eax, eax
0x180050211  jnz     short loc_18005021C
0x180050213  cmp     [rdi], r13d
0x180050216  jz      loc_1800502C3
0x18005021c  mov     r8d, [rdi]
0x18005021f  xor     edx, edx
0x180050221  lea     ecx, [r8+rax]
0x180050225  imul    eax, 64h ; 'd'
0x180050228  div     ecx
0x18005022a  cmp     eax, cs:DhcpGlobalAlertPercentage
0x180050230  jbe     loc_1800502C3
0x180050236  cmp     r8d, cs:DhcpGlobalAlertCount
0x18005023d  jnb     loc_1800502C3
0x180050243  mov     r8d, 0Ah; Radix
0x180050249  lea     rdx, [rsp+1C0h+Buffer]; Buffer
0x18005024e  mov     ecx, eax; Value
0x180050250  call    cs:__imp__ltoa
0x180050257  nop     dword ptr [rax+rax+00h]
0x18005025c  mov     ecx, [rdi]; Value
0x18005025e  lea     rdx, [rsp+1C0h+var_170]; Buffer
0x180050263  mov     r8d, 0Ah; Radix
0x180050269  call    cs:__imp__ltoa
0x180050270  nop     dword ptr [rax+rax+00h]
0x180050275  mov     rcx, [rdi-0Ch]; SourceString
0x180050279  lea     rdx, [rbp+0C0h+var_140]
0x18005027d  call    DhcpUnicodeToOem
0x180050282  mov     [rsp+1C0h+var_160], rax
0x180050287  mov     r9d, 3
0x18005028d  lea     rax, [rsp+1C0h+Buffer]
0x180050292  mov     [rsp+1C0h+var_190], r13
0x180050297  mov     [rsp+1C0h+var_158], rax
0x18005029c  mov     edx, 3FCh
0x1800502a1  lea     rax, [rsp+1C0h+var_170]
0x1800502a6  mov     [rsp+1C0h+var_150], rax
0x1800502ab  lea     r8d, [r9-1]
0x1800502af  lea     rax, [rsp+1C0h+var_160]
0x1800502b4  mov     [rsp+1C0h+var_198], rax
0x1800502b9  mov     dword ptr [rsp+1C0h+var_1A0], r13d
0x1800502be  call    DhcpReportEventA
0x1800502c3  inc     r15d
0x1800502c6  add     rdi, 20h ; ' '
0x1800502ca  cmp     r15d, [rsi+28h]
0x1800502ce  jb      loc_18005020C
0x1800502d4  mov     rcx, [rsi+30h]; hMem
0x1800502d8  test    rcx, rcx
0x1800502db  jz      short loc_1800502E9
0x1800502dd  call    cs:__imp_LocalFree
0x1800502e4  nop     dword ptr [rax+rax+00h]
0x1800502e9  mov     rcx, rsi; hMem
0x1800502ec  call    cs:__imp_LocalFree
0x1800502f3  nop     dword ptr [rax+rax+00h]
0x1800502f8  xor     edx, edx; nPriority
0x1800502fa  mov     rcx, r12; hThread
0x1800502fd  call    cs:__imp_SetThreadPriority
0x180050304  nop     dword ptr [rax+rax+00h]
0x180050309  test    ebx, ebx
0x18005030b  jnz     short loc_180050315
0x18005030d  mov     ebx, r14d
0x180050310  test    r14d, r14d
0x180050313  jz      short loc_180050362
0x180050315  cmp     ebx, 103h
0x18005031b  jz      short loc_180050362
0x18005031d  mov     r8d, ebx
0x180050320  mov     edx, 1
0x180050325  mov     ecx, 3F2h
0x18005032a  call    DhcpServerEventLog
0x18005032f  mov     rcx, cs:WPP_GLOBAL_Control
0x180050336  lea     rax, WPP_GLOBAL_Control
0x18005033d  cmp     rcx, rax
0x180050340  jz      short loc_180050393
0x180050342  test    byte ptr [rcx+1Ch], 10h
0x180050346  jz      short loc_180050393
0x180050348  mov     rcx, [rcx+10h]
0x18005034c  lea     r8, WPP_f0e25f423f3133668f92132b43c41a83_Traceguids
0x180050353  mov     edx, 1Dh
0x180050358  mov     r9d, ebx
0x18005035b  call    WPP_SF_D
0x180050360  jmp     short loc_180050393
0x180050362  mov     rcx, cs:WPP_GLOBAL_Control
0x180050369  lea     rax, WPP_GLOBAL_Control
0x180050370  cmp     rcx, rax
0x180050373  jz      short loc_180050393
0x180050375  test    dword ptr [rcx+1Ch], 8000h
0x18005037c  jz      short loc_180050393
0x18005037e  mov     rcx, [rcx+10h]
0x180050382  lea     r8, WPP_f0e25f423f3133668f92132b43c41a83_Traceguids
0x180050389  mov     edx, 1Eh
0x18005038e  call    WPP_SF_
0x180050393  mov     eax, r14d
0x180050396  mov     rcx, [rbp+0C0h+var_40]
0x18005039d  xor     rcx, rsp; StackCookie
0x1800503a0  call    __security_check_cookie
0x1800503a5  mov     rbx, [rsp+1C0h+arg_10]
0x1800503ad  add     rsp, 190h
0x1800503b4  pop     r15
0x1800503b6  pop     r14
0x1800503b8  pop     r13
0x1800503ba  pop     r12
0x1800503bc  pop     rdi
0x1800503bd  pop     rsi
0x1800503be  pop     rbp
0x1800503bf  retn
```
