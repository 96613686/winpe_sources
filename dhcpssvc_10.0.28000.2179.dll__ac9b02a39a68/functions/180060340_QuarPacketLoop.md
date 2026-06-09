# QuarPacketLoop

- ea: `0x180060340`
- end: `0x180060895`
- name: `QuarPacketLoop`
- size: `1365`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000282c`
- `0x180003228`
- `0x18000492c`
- `0x180006234`
- `0x180021fd4`
- `0x1800250e8`
- `0x1800540c4`
- `0x18005de78`
- `0x18005e5f8`
- `0x18005e930`
- `0x18005eba8`
- `0x18005ebe8`
- `0x18005f7cc`
- `0x180060340`
- `0x180061d30`
- `0x18008f094`
- `0x180098658`
- `0x1800cf010`

## import_xrefs

- `KERNEL32!GetQueuedCompletionStatus` at `0x1800603f3`
- `KERNEL32!GetQueuedCompletionStatus` at `0x1800603f3`
- `KERNEL32!SwitchToThread` at `0x180060491`
- `KERNEL32!SwitchToThread` at `0x180060491`
- `KERNEL32!GetLastError` at `0x180060403`
- `KERNEL32!GetLastError` at `0x180060403`
- `KERNEL32!EnterCriticalSection` at `0x1800604dc`
- `KERNEL32!EnterCriticalSection` at `0x180060548`
- `KERNEL32!EnterCriticalSection` at `0x1800606c2`
- `KERNEL32!EnterCriticalSection` at `0x1800604dc`
- `KERNEL32!EnterCriticalSection` at `0x180060548`
- `KERNEL32!EnterCriticalSection` at `0x1800606c2`
- `KERNEL32!LeaveCriticalSection` at `0x1800604f7`
- `KERNEL32!LeaveCriticalSection` at `0x1800605e3`
- `KERNEL32!LeaveCriticalSection` at `0x180060884`
- `KERNEL32!LeaveCriticalSection` at `0x1800604f7`
- `KERNEL32!LeaveCriticalSection` at `0x1800605e3`
- `KERNEL32!LeaveCriticalSection` at `0x180060884`
- `KERNEL32!LeaveCriticalSection` at `0x1800cdf1b`
- `KERNEL32!LeaveCriticalSection` at `0x1800cdf3d`
- `KERNEL32!LeaveCriticalSection` at `0x1800cdf5f`

## pseudocode

```c
void __fastcall QuarPacketLoop(PVOID Parameter)
{
  _QWORD *v1; // rcx
  int v2; // edi
  unsigned int v3; // ebx
  DWORD LastError; // eax
  _DWORD *AQuarDecisionPacket; // r15
  int v6; // edx
  __int64 *v7; // rdi
  __int64 *i; // rax
  __int64 *v9; // rcx
  __int64 **v10; // rax
  unsigned int v11; // eax
  int String; // eax
  __int64 v13; // rbx
  int v14; // r9d
  __int64 **v15; // rax
  __int64 v16; // rcx
  LPOVERLAPPED Overlapped; // [rsp+60h] [rbp-38h] BYREF
  __int64 NumberOfBytesTransferred; // [rsp+A0h] [rbp+8h] BYREF
  __int64 *v19; // [rsp+A8h] [rbp+10h]
  unsigned __int64 CompletionKey; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v21; // [rsp+B8h] [rbp+20h] BYREF

  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0 )
    goto LABEL_5;
  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids);
  while ( 1 )
  {
    while ( 1 )
    {
      v1 = WPP_GLOBAL_Control;
LABEL_5:
      LODWORD(NumberOfBytesTransferred) = 0;
      CompletionKey = 0;
      Overlapped = 0;
      if ( !CompletionPort )
      {
        v2 = 1;
        v3 = 87;
        goto LABEL_16;
      }
      v2 = 0;
      if ( DhcpGlobalServiceStopping )
        goto LABEL_13;
      _InterlockedIncrement(&dword_1800FD15C);
      if ( GetQueuedCompletionStatus(
             CompletionPort,
             (LPDWORD)&NumberOfBytesTransferred,
             &CompletionKey,
             &Overlapped,
             0xFFFFFFFF) )
      {
        _InterlockedIncrement(&dword_1800FD154);
        _InterlockedDecrement(&dword_1800FD178);
        if ( CompletionKey == 1 )
        {
LABEL_13:
          v2 = 1;
          DhcpNotifyQuarThreadsQuit();
        }
        v3 = 0;
LABEL_15:
        v1 = WPP_GLOBAL_Control;
        goto LABEL_16;
      }
      LastError = GetLastError();
      v3 = LastError;
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, LastError);
        goto LABEL_15;
      }
LABEL_16:
      if ( !v3 )
        break;
      if ( v1 != &WPP_GLOBAL_Control && (*((_DWORD *)v1 + 7) & 0x8000000) != 0 )
        WPP_SF_D(v1[2], 84, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, v3);
      SwitchToThread();
    }
    if ( v2 )
      break;
    EnterCriticalSection(&QuarDecisionCritSection);
    AQuarDecisionPacket = (_DWORD *)GetAQuarDecisionPacket();
    LeaveCriticalSection(&QuarDecisionCritSection);
    if ( AQuarDecisionPacket )
    {
      _InterlockedDecrement(&DhcpGlobalNumPacketsInQuarDecisionQueue);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids,
          AQuarDecisionPacket);
      }
      EnterCriticalSection(&PacketCritSection);
      v6 = AQuarDecisionPacket[4];
      v7 = 0;
      v19 = 0;
      for ( i = *(__int64 **)QuarPacketWaitingQ; (__int64 *)QuarPacketWaitingQ != i; i = (__int64 *)*i )
      {
        if ( v6 == *((_DWORD *)i + 77) )
        {
          v19 = i;
          v7 = i;
          break;
        }
      }
      LODWORD(NumberOfBytesTransferred) = v7 == 0 ? 2 : 0;
      if ( (v7 == 0 ? 2 : 0) == 0 && v7 )
      {
        v9 = (__int64 *)*v7;
        v10 = (__int64 **)v7[1];
        if ( *(__int64 **)(*v7 + 8) != v7 || *v10 != v7 )
          __fastfail(3u);
        *v10 = v9;
        v9[1] = (__int64)v10;
        v7[1] = (__int64)v7;
        *v7 = (__int64)v7;
        _InterlockedDecrement(&DhcpGlobalNumPacketsInQuarWaitingQueue);
      }
      LeaveCriticalSection(&PacketCritSection);
      if ( v7 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, v7);
        }
        *((_DWORD *)v7 + 78) = AQuarDecisionPacket[5];
        v7[40] = (__int64)AQuarDecisionPacket;
        MemArrayFree(v7 + 30, MemFree);
        if ( *((_DWORD *)v7 + 78) == 1 )
        {
          v11 = AssembleQuarantineUserClass(v7);
          if ( v11 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, v11);
            }
          }
        }
        EnterCriticalSection(&PacketCritSection);
        if ( AQuarDecisionPacket[5] == 2 )
        {
          NumberOfBytesTransferred = 0;
          v21 = 0;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
          {
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              90,
              &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids,
              (unsigned int)AQuarDecisionPacket[4]);
          }
          DeleteHashQ(v7);
          if ( *((_DWORD *)v7 + 76)
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
          {
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              91,
              &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids,
              (unsigned int)dword_1801575EC);
          }
          if ( qword_1801577D0 )
            qword_1801577D0(v7 + 11, v7 + 13, 12, *((unsigned int *)v7 + 29), v7, v7[37]);
          DhcpDetermineHostName(v7 + 11, v7 + 41, 0, &v21);
          String = GetString(1204);
          v13 = v21;
          DhcpUpdateAuditLogQuar(
            33,
            String,
            0,
            v14,
            *((_DWORD *)v7 + 148),
            v21,
            0,
            *((_DWORD *)v7 + 9),
            2,
            0,
            v7[69],
            *((_DWORD *)v7 + 140));
          if ( v13 )
            DhcpFreeMemory(v13);
          UnlockAndFreePacket(v7, 0);
        }
        else
        {
          *((_BYTE *)v7 + 73) = 6;
          v15 = (__int64 **)QuarPacketReadyQ;
          v16 = *(_QWORD *)QuarPacketReadyQ;
          if ( *(_QWORD *)(*(_QWORD *)QuarPacketReadyQ + 8LL) != QuarPacketReadyQ )
            __fastfail(3u);
          *v7 = v16;
          v7[1] = (__int64)v15;
          *(_QWORD *)(v16 + 8) = v7;
          *v15 = v7;
          _InterlockedIncrement(&DhcpGlobalNumPacketsInQuarReadyQueue);
          NotifyProcessingLoop();
        }
        LeaveCriticalSection(&PacketCritSection);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            86,
            &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids,
            (unsigned int)AQuarDecisionPacket[4]);
        FreeQuarDecisionPacket(AQuarDecisionPacket);
      }
    }
  }
  if ( v1 != &WPP_GLOBAL_Control && (*((_DWORD *)v1 + 7) & 0x8000000) != 0 )
    WPP_SF_(v1[2], 92, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids);
}

```

## disassembly

```asm
0x180060340  push    rbx
0x180060342  push    rdi
0x180060343  push    r12
0x180060345  push    r15
0x180060347  sub     rsp, 78h
0x18006034b  lea     r12, WPP_GLOBAL_Control
0x180060352  mov     rcx, cs:WPP_GLOBAL_Control
0x180060359  cmp     rcx, r12
0x18006035c  jz      short loc_180060383
0x18006035e  test    dword ptr [rcx+1Ch], 8000000h
0x180060365  jz      short loc_180060383
0x180060367  mov     edx, 53h ; 'S'
0x18006036c  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180060373  mov     rcx, [rcx+10h]
0x180060377  call    WPP_SF_
0x18006037c  mov     rcx, cs:WPP_GLOBAL_Control
0x180060383  mov     dword ptr [rsp+98h+NumberOfBytesTransferred], 0
0x18006038e  mov     [rsp+98h+CompletionKey], 0
0x18006039a  mov     [rsp+98h+Overlapped], 0
0x1800603a3  cmp     cs:CompletionPort, 0
0x1800603ab  jnz     short loc_1800603BA
0x1800603ad  mov     edi, 1
0x1800603b2  lea     ebx, [rdi+56h]
0x1800603b5  jmp     loc_180060467
0x1800603ba  xor     edi, edi
0x1800603bc  cmp     cs:DhcpGlobalServiceStopping, edi
0x1800603c2  jnz     loc_180060454
0x1800603c8  lock inc cs:dword_1800FD15C
0x1800603cf  mov     [rsp+98h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x1800603d7  lea     r9, [rsp+98h+Overlapped]; lpOverlapped
0x1800603dc  lea     r8, [rsp+98h+CompletionKey]; lpCompletionKey
0x1800603e4  lea     rdx, [rsp+98h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800603ec  mov     rcx, cs:CompletionPort; CompletionPort
0x1800603f3  call    cs:__imp_GetQueuedCompletionStatus
0x1800603fa  nop     dword ptr [rax+rax+00h]
0x1800603ff  test    eax, eax
0x180060401  jnz     short loc_18006043B
0x180060403  call    cs:__imp_GetLastError
0x18006040a  nop     dword ptr [rax+rax+00h]
0x18006040f  mov     ebx, eax
0x180060411  mov     rcx, cs:WPP_GLOBAL_Control
0x180060418  cmp     rcx, r12
0x18006041b  jz      short loc_180060467
0x18006041d  test    byte ptr [rcx+1Ch], 10h
0x180060421  jz      short loc_180060467
0x180060423  lea     edx, [rdi+4Dh]
0x180060426  mov     r9d, eax
0x180060429  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180060430  mov     rcx, [rcx+10h]
0x180060434  call    WPP_SF_D
0x180060439  jmp     short loc_180060460
0x18006043b  lock inc cs:dword_1800FD154
0x180060442  lock dec cs:dword_1800FD178
0x180060449  cmp     [rsp+98h+CompletionKey], 1
0x180060452  jnz     short loc_18006045E
0x180060454  mov     edi, 1
0x180060459  call    DhcpNotifyQuarThreadsQuit
0x18006045e  xor     ebx, ebx
0x180060460  mov     rcx, cs:WPP_GLOBAL_Control
0x180060467  test    ebx, ebx
0x180060469  jz      short loc_1800604A2
0x18006046b  cmp     rcx, r12
0x18006046e  jz      short loc_180060491
0x180060470  test    dword ptr [rcx+1Ch], 8000000h
0x180060477  jz      short loc_180060491
0x180060479  mov     edx, 54h ; 'T'
0x18006047e  mov     r9d, ebx
0x180060481  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180060488  mov     rcx, [rcx+10h]
0x18006048c  call    WPP_SF_D
0x180060491  call    cs:__imp_SwitchToThread
0x180060498  nop     dword ptr [rax+rax+00h]
0x18006049d  jmp     loc_18006037C
0x1800604a2  test    edi, edi
0x1800604a4  jz      short loc_1800604D5
0x1800604a6  cmp     rcx, r12
0x1800604a9  jz      short loc_1800604C9
0x1800604ab  test    dword ptr [rcx+1Ch], 8000000h
0x1800604b2  jz      short loc_1800604C9
0x1800604b4  mov     edx, 5Ch ; '\'
0x1800604b9  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x1800604c0  mov     rcx, [rcx+10h]
0x1800604c4  call    WPP_SF_
0x1800604c9  add     rsp, 78h
0x1800604cd  pop     r15
0x1800604cf  pop     r12
0x1800604d1  pop     rdi
0x1800604d2  pop     rbx
0x1800604d3  retn
0x1800604d5  lea     rcx, QuarDecisionCritSection; lpCriticalSection
0x1800604dc  call    cs:__imp_EnterCriticalSection
0x1800604e3  nop     dword ptr [rax+rax+00h]
0x1800604e8  call    GetAQuarDecisionPacket
0x1800604ed  mov     r15, rax
0x1800604f0  lea     rcx, QuarDecisionCritSection; lpCriticalSection
0x1800604f7  call    cs:__imp_LeaveCriticalSection
0x1800604fe  nop     dword ptr [rax+rax+00h]
0x180060503  test    r15, r15
0x180060506  jz      loc_18006037C
0x18006050c  lock dec cs:DhcpGlobalNumPacketsInQuarDecisionQueue
0x180060513  mov     rcx, cs:WPP_GLOBAL_Control
0x18006051a  cmp     rcx, r12
0x18006051d  jz      short loc_180060541
0x18006051f  test    dword ptr [rcx+1Ch], 8000000h
0x180060526  jz      short loc_180060541
0x180060528  mov     edx, 55h ; 'U'
0x18006052d  mov     r9, r15
0x180060530  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180060537  mov     rcx, [rcx+10h]
0x18006053b  call    WPP_SF_q
0x180060540  nop
0x180060541  lea     rcx, PacketCritSection; lpCriticalSection
0x180060548  call    cs:__imp_EnterCriticalSection
0x18006054f  nop     dword ptr [rax+rax+00h]
0x180060554  lea     r8, [rsp+98h+arg_8]
0x18006055c  mov     edx, [r15+10h]
0x180060560  xor     edi, edi
0x180060562  mov     [rsp+98h+arg_8], rdi
0x18006056a  mov     rcx, cs:QuarPacketWaitingQ
0x180060571  mov     rax, [rcx]
0x180060574  cmp     rcx, rax
0x180060577  jz      short loc_18006058C
0x180060579  cmp     edx, [rax+134h]
0x18006057f  jnz     short loc_1800605D0
0x180060581  mov     [r8], rax
0x180060584  mov     rdi, [rsp+98h+arg_8]
0x18006058c  mov     rax, rdi
0x18006058f  neg     rax
0x180060592  sbb     ecx, ecx
0x180060594  not     ecx
0x180060596  and     ecx, 2
0x180060599  mov     dword ptr [rsp+98h+NumberOfBytesTransferred], ecx
0x1800605a0  jnz     short loc_1800605DC
0x1800605a2  test    rdi, rdi
0x1800605a5  jz      short loc_1800605DC
0x1800605a7  mov     rcx, [rdi]
0x1800605aa  mov     rax, [rdi+8]
0x1800605ae  cmp     [rcx+8], rdi
0x1800605b2  jnz     short loc_1800605D5
0x1800605b4  cmp     [rax], rdi
0x1800605b7  jnz     short loc_1800605D5
0x1800605b9  mov     [rax], rcx
0x1800605bc  mov     [rcx+8], rax
0x1800605c0  mov     [rdi+8], rdi
0x1800605c4  mov     [rdi], rdi
0x1800605c7  lock dec cs:DhcpGlobalNumPacketsInQuarWaitingQueue
0x1800605ce  jmp     short loc_1800605DC
0x1800605d0  mov     rax, [rax]
0x1800605d3  jmp     short loc_180060574
0x1800605d5  mov     ecx, 3
0x1800605da  int     29h; Win8: RtlFailFast(ecx)
0x1800605dc  lea     rcx, PacketCritSection; lpCriticalSection
0x1800605e3  call    cs:__imp_LeaveCriticalSection
0x1800605ea  nop     dword ptr [rax+rax+00h]
0x1800605ef  test    rdi, rdi
0x1800605f2  jnz     short loc_18006062A
0x1800605f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800605fb  cmp     rcx, r12
0x1800605fe  jz      short loc_18006061D
0x180060600  test    byte ptr [rcx+1Ch], 10h
0x180060604  jz      short loc_18006061D
0x180060606  lea     edx, [rdi+56h]
0x180060609  mov     r9d, [r15+10h]
0x18006060d  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180060614  mov     rcx, [rcx+10h]
0x180060618  call    WPP_SF_D
0x18006061d  mov     rcx, r15; lpMem
0x180060620  call    FreeQuarDecisionPacket
0x180060625  jmp     loc_18006037C
0x18006062a  mov     rcx, cs:WPP_GLOBAL_Control
0x180060631  cmp     rcx, r12
0x180060634  jz      short loc_180060657
0x180060636  test    dword ptr [rcx+1Ch], 8000000h
0x18006063d  jz      short loc_180060657
0x18006063f  mov     edx, 57h ; 'W'
0x180060644  mov     r9, rdi
0x180060647  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x18006064e  mov     rcx, [rcx+10h]
0x180060652  call    WPP_SF_q
0x180060657  mov     eax, [r15+14h]
0x18006065b  mov     [rdi+138h], eax
0x180060661  mov     [rdi+140h], r15
0x180060668  lea     rcx, [rdi+0F0h]
0x18006066f  lea     rdx, MemFree
0x180060676  call    MemArrayFree
0x18006067b  cmp     dword ptr [rdi+138h], 1
0x180060682  jnz     short loc_1800606BB
0x180060684  mov     rcx, rdi
0x180060687  call    AssembleQuarantineUserClass
0x18006068c  test    eax, eax
0x18006068e  jz      short loc_1800606BB
0x180060690  mov     rcx, cs:WPP_GLOBAL_Control
0x180060697  cmp     rcx, r12
0x18006069a  jz      short loc_1800606BB
0x18006069c  test    byte ptr [rcx+1Ch], 10h
0x1800606a0  jz      short loc_1800606BB
0x1800606a2  mov     edx, 59h ; 'Y'
0x1800606a7  mov     r9d, eax
0x1800606aa  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x1800606b1  mov     rcx, [rcx+10h]
0x1800606b5  call    WPP_SF_D
0x1800606ba  nop
0x1800606bb  lea     rcx, PacketCritSection; lpCriticalSection
0x1800606c2  call    cs:__imp_EnterCriticalSection
0x1800606c9  nop     dword ptr [rax+rax+00h]
0x1800606ce  cmp     dword ptr [r15+14h], 2
0x1800606d3  jnz     loc_180060847
0x1800606d9  xor     ebx, ebx
0x1800606db  mov     [rsp+98h+NumberOfBytesTransferred], rbx
0x1800606e3  mov     [rsp+98h+arg_18], rbx
0x1800606eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800606f2  cmp     rcx, r12
0x1800606f5  jz      short loc_180060717
0x1800606f7  test    dword ptr [rcx+1Ch], 4000h
0x1800606fe  jz      short loc_180060717
0x180060700  lea     edx, [rbx+5Ah]
0x180060703  mov     r9d, [r15+10h]
0x180060707  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x18006070e  mov     rcx, [rcx+10h]
0x180060712  call    WPP_SF_D
0x180060717  mov     rcx, rdi
0x18006071a  call    DeleteHashQ
0x18006071f  cmp     [rdi+130h], ebx
0x180060725  jz      short loc_180060759
0x180060727  mov     rcx, cs:WPP_GLOBAL_Control
0x18006072e  cmp     rcx, r12
0x180060731  jz      short loc_180060759
0x180060733  test    dword ptr [rcx+1Ch], 20000000h
0x18006073a  jz      short loc_180060759
0x18006073c  mov     edx, 5Bh ; '['
0x180060741  mov     r9d, cs:dword_1801575EC
0x180060748  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x18006074f  mov     rcx, [rcx+10h]
0x180060753  call    WPP_SF_D
0x180060758  nop
0x180060759  mov     rax, cs:qword_1801577D0
0x180060760  test    rax, rax
0x180060763  jz      short loc_18006078D
0x180060765  lea     rdx, [rdi+68h]
0x180060769  lea     rcx, [rdi+58h]
0x18006076d  mov     r8, [rdi+128h]
0x180060774  mov     [rsp+98h+var_70], r8
0x180060779  mov     qword ptr [rsp+98h+dwMilliseconds], rdi
0x18006077e  mov     r9d, [rdi+74h]
0x180060782  mov     r8d, 0Ch
0x180060788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006078d  jmp     short loc_1800607AD
0x18006078f  mov     ecx, eax
0x180060791  call    DhcpCalloutLogAV
0x180060796  lea     r12, WPP_GLOBAL_Control
0x18006079d  mov     rdi, [rsp+98h+arg_8]
0x1800607a5  mov     rbx, [rsp+98h+NumberOfBytesTransferred]
0x1800607ad  lea     rdx, [rdi+148h]
0x1800607b4  lea     rcx, [rdi+58h]
0x1800607b8  lea     r9, [rsp+98h+arg_18]
0x1800607c0  xor     r8d, r8d
0x1800607c3  call    DhcpDetermineHostName
0x1800607c8  lea     r9, [rdi+29h]
0x1800607cc  mov     ecx, 4B4h
0x1800607d1  call    GetString
0x1800607d6  mov     rdx, rax
0x1800607d9  mov     eax, [rdi+230h]
0x1800607df  mov     [rsp+98h+var_40], eax
0x1800607e3  mov     rax, [rdi+228h]
0x1800607ea  mov     [rsp+98h+var_48], rax
0x1800607ef  mov     [rsp+98h+var_50], rbx
0x1800607f4  mov     [rsp+98h+var_58], 2
0x1800607fc  mov     eax, [rdi+24h]
0x1800607ff  mov     [rsp+98h+var_60], eax
0x180060803  mov     [rsp+98h+var_68], 0
0x18006080b  mov     rbx, [rsp+98h+arg_18]
0x180060813  mov     [rsp+98h+var_70], rbx
0x180060818  mov     eax, [rdi+250h]
0x18006081e  mov     [rsp+98h+dwMilliseconds], eax
0x180060822  xor     r8d, r8d
0x180060825  lea     ecx, [r8+21h]
0x180060829  call    DhcpUpdateAuditLogQuar
0x18006082e  test    rbx, rbx
0x180060831  jz      short loc_18006083B
0x180060833  mov     rcx, rbx
0x180060836  call    DhcpFreeMemory
0x18006083b  xor     edx, edx
0x18006083d  mov     rcx, rdi
0x180060840  call    UnlockAndFreePacket
0x180060845  jmp     short loc_18006087D
0x180060847  mov     byte ptr [rdi+49h], 6
0x18006084b  mov     rax, cs:QuarPacketReadyQ
0x180060852  mov     rcx, [rax]
0x180060855  cmp     [rcx+8], rax
0x180060859  jz      short loc_180060862
0x18006085b  mov     ecx, 3
0x180060860  int     29h; Win8: RtlFailFast(ecx)
0x180060862  mov     [rdi], rcx
0x180060865  mov     [rdi+8], rax
0x180060869  mov     [rcx+8], rdi
0x18006086d  mov     [rax], rdi
0x180060870  lock inc cs:DhcpGlobalNumPacketsInQuarReadyQueue
0x180060877  call    NotifyProcessingLoop
0x18006087c  nop
0x18006087d  lea     rcx, PacketCritSection; lpCriticalSection
  ... truncated ...
```
