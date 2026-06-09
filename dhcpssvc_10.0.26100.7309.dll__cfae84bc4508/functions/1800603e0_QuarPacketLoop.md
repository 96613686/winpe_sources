# QuarPacketLoop

- ea: `0x1800603e0`
- end: `0x180060954`
- name: `QuarPacketLoop`
- size: `1396`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180002854`
- `0x18000323c`
- `0x180004930`
- `0x180006250`
- `0x180022b28`
- `0x180025b98`
- `0x1800543a4`
- `0x18005e160`
- `0x18005e8c0`
- `0x18005ebf8`
- `0x18005ee6c`
- `0x18005eeac`
- `0x18005f8a4`
- `0x1800603e0`
- `0x180061fac`
- `0x18008ef1c`
- `0x1800983b4`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!GetQueuedCompletionStatus` at `0x180060499`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180060499`
- `KERNEL32!SwitchToThread` at `0x18006053c`
- `KERNEL32!SwitchToThread` at `0x18006053c`
- `KERNEL32!GetLastError` at `0x1800604a9`
- `KERNEL32!GetLastError` at `0x1800604a9`
- `KERNEL32!EnterCriticalSection` at `0x180060590`
- `KERNEL32!EnterCriticalSection` at `0x180060609`
- `KERNEL32!EnterCriticalSection` at `0x18006078d`
- `KERNEL32!EnterCriticalSection` at `0x180060590`
- `KERNEL32!EnterCriticalSection` at `0x180060609`
- `KERNEL32!EnterCriticalSection` at `0x18006078d`
- `KERNEL32!LeaveCriticalSection` at `0x1800605b3`
- `KERNEL32!LeaveCriticalSection` at `0x1800606a2`
- `KERNEL32!LeaveCriticalSection` at `0x180060943`
- `KERNEL32!LeaveCriticalSection` at `0x1800605b3`
- `KERNEL32!LeaveCriticalSection` at `0x1800606a2`
- `KERNEL32!LeaveCriticalSection` at `0x180060943`
- `KERNEL32!LeaveCriticalSection` at `0x1800cce9b`
- `KERNEL32!LeaveCriticalSection` at `0x1800ccebd`
- `KERNEL32!LeaveCriticalSection` at `0x1800ccedf`

## pseudocode

```c
void __fastcall QuarPacketLoop(PVOID Parameter)
{
  _QWORD *v1; // rcx
  unsigned int v2; // ebx
  DWORD LastError; // eax
  void *AQuarDecisionPacket; // rbx
  unsigned int *v5; // r13
  __int64 v6; // rdi
  __int64 i; // rax
  __int64 v8; // rcx
  _QWORD *v9; // rax
  _DWORD *v10; // rbx
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  int String; // eax
  wchar_t *v15; // rbx
  int v16; // r9d
  __int64 *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // [rsp+68h] [rbp-50h]
  unsigned __int64 CompletionKey; // [rsp+70h] [rbp-48h] BYREF
  wchar_t *v21; // [rsp+78h] [rbp-40h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+80h] [rbp-38h] BYREF
  int v23; // [rsp+C0h] [rbp+8h]
  DWORD NumberOfBytesTransferred; // [rsp+C8h] [rbp+10h] BYREF
  LPVOID lpMem; // [rsp+D8h] [rbp+20h]

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
      NumberOfBytesTransferred = 0;
      CompletionKey = 0;
      Overlapped = 0;
      if ( !CompletionPort )
      {
        v23 = 1;
        v2 = 87;
        goto LABEL_16;
      }
      v23 = 0;
      if ( DhcpGlobalServiceStopping )
        goto LABEL_13;
      _InterlockedIncrement(&dword_1800FB188);
      if ( GetQueuedCompletionStatus(CompletionPort, &NumberOfBytesTransferred, &CompletionKey, &Overlapped, 0xFFFFFFFF) )
      {
        _InterlockedIncrement(&dword_1800FB184);
        _InterlockedDecrement(&dword_1800FB1A8);
        if ( CompletionKey == 1 )
        {
LABEL_13:
          v23 = 1;
          DhcpNotifyQuarThreadsQuit();
        }
        v2 = 0;
LABEL_15:
        v1 = WPP_GLOBAL_Control;
        goto LABEL_16;
      }
      LastError = GetLastError();
      v2 = LastError;
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, LastError);
        goto LABEL_15;
      }
LABEL_16:
      if ( !v2 )
        break;
      if ( v1 != &WPP_GLOBAL_Control && (*((_DWORD *)v1 + 7) & 0x8000000) != 0 )
        WPP_SF_D(v1[2], 84, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, v2);
      SwitchToThread();
    }
    if ( v23 )
      break;
    EnterCriticalSection(&QuarDecisionCritSection);
    AQuarDecisionPacket = (void *)GetAQuarDecisionPacket();
    lpMem = AQuarDecisionPacket;
    LeaveCriticalSection(&QuarDecisionCritSection);
    if ( AQuarDecisionPacket )
    {
      _InterlockedDecrement(&DhcpGlobalNumPacketsInQuarDecisionQueue);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, lpMem);
      }
      EnterCriticalSection(&PacketCritSection);
      v5 = (unsigned int *)lpMem;
      v6 = 0;
      v19 = 0;
      for ( i = *(_QWORD *)QuarPacketWaitingQ; QuarPacketWaitingQ != i; i = *(_QWORD *)i )
      {
        if ( *((_DWORD *)lpMem + 4) == *(_DWORD *)(i + 308) )
        {
          v19 = i;
          v6 = i;
          break;
        }
      }
      if ( (v6 == 0 ? 2 : 0) == 0 && v6 )
      {
        v8 = *(_QWORD *)v6;
        v9 = *(_QWORD **)(v6 + 8);
        if ( *(_QWORD *)(*(_QWORD *)v6 + 8LL) != v6 || *v9 != v6 )
          __fastfail(3u);
        *v9 = v8;
        *(_QWORD *)(v8 + 8) = v9;
        *(_QWORD *)(v6 + 8) = v6;
        *(_QWORD *)v6 = v6;
        _InterlockedDecrement(&DhcpGlobalNumPacketsInQuarWaitingQueue);
        v6 = v19;
      }
      LeaveCriticalSection(&PacketCritSection);
      if ( v6 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, v6);
        }
        v10 = lpMem;
        *(_DWORD *)(v6 + 312) = *((_DWORD *)lpMem + 5);
        *(_QWORD *)(v6 + 320) = v10;
        MemArrayFree(v6 + 240, MemFree);
        if ( *(_DWORD *)(v6 + 312) == 1 )
        {
          v11 = AssembleQuarantineUserClass(v6);
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
        if ( v10[5] == 2 )
        {
          v21 = 0;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, v5[4]);
          }
          DeleteHashQ(v6);
          if ( *(_DWORD *)(v6 + 304)
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
          {
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              91,
              &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids,
              (unsigned int)dword_18015564C);
          }
          if ( qword_180155830 )
            qword_180155830(v6 + 88, v6 + 104, 12, *(unsigned int *)(v6 + 116), v6, *(_QWORD *)(v6 + 296));
          DhcpDetermineHostName(v6 + 88, v6 + 328, 0, &v21);
          String = GetString(1204, v12, v13);
          v15 = v21;
          DhcpUpdateAuditLogQuar(
            33,
            String,
            0,
            v16,
            *(_DWORD *)(v6 + 592),
            (__int64)v21,
            0,
            *(_DWORD *)(v6 + 36),
            2,
            0,
            *(_QWORD *)(v6 + 552),
            *(_DWORD *)(v6 + 560));
          if ( v15 )
            DhcpFreeMemory(v15);
          UnlockAndFreePacket(v6, 0);
        }
        else
        {
          *(_BYTE *)(v6 + 73) = 6;
          v17 = (__int64 *)QuarPacketReadyQ;
          v18 = *(_QWORD *)QuarPacketReadyQ;
          if ( *(_QWORD *)(*(_QWORD *)QuarPacketReadyQ + 8LL) != QuarPacketReadyQ )
            __fastfail(3u);
          *(_QWORD *)v6 = v18;
          *(_QWORD *)(v6 + 8) = v17;
          *(_QWORD *)(v18 + 8) = v6;
          *v17 = v6;
          _InterlockedIncrement(&DhcpGlobalNumPacketsInQuarReadyQueue);
          NotifyProcessingLoop();
        }
        LeaveCriticalSection(&PacketCritSection);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, v5[4]);
        FreeQuarDecisionPacket(lpMem);
      }
    }
  }
  if ( v1 != &WPP_GLOBAL_Control && (*((_DWORD *)v1 + 7) & 0x8000000) != 0 )
    WPP_SF_(v1[2], 92, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids);
}

```

## disassembly

```asm
0x1800603e0  push    rbx
0x1800603e2  push    rdi
0x1800603e3  push    r13
0x1800603e5  push    r15
0x1800603e7  sub     rsp, 98h
0x1800603ee  lea     r15, WPP_GLOBAL_Control
0x1800603f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800603fc  cmp     rcx, r15
0x1800603ff  jz      short loc_180060426
0x180060401  test    dword ptr [rcx+1Ch], 8000000h
0x180060408  jz      short loc_180060426
0x18006040a  mov     edx, 53h ; 'S'
0x18006040f  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180060416  mov     rcx, [rcx+10h]
0x18006041a  call    WPP_SF_
0x18006041f  mov     rcx, cs:WPP_GLOBAL_Control
0x180060426  and     [rsp+0B8h+NumberOfBytesTransferred], 0
0x18006042e  and     [rsp+0B8h+CompletionKey], 0
0x180060434  and     [rsp+0B8h+Overlapped], 0
0x18006043d  cmp     cs:CompletionPort, 0
0x180060445  jnz     short loc_18006045C
0x180060447  mov     dword ptr [rsp+0B8h+arg_0], 1
0x180060452  mov     ebx, 57h ; 'W'
0x180060457  jmp     loc_180060512
0x18006045c  and     dword ptr [rsp+0B8h+arg_0], 0
0x180060464  cmp     cs:DhcpGlobalServiceStopping, 0
0x18006046b  jnz     loc_1800604F9
0x180060471  lock inc cs:dword_1800FB188
0x180060478  or      dword ptr [rsp+0B8h+var_98], 0FFFFFFFFh
0x18006047d  lea     r9, [rsp+0B8h+Overlapped]; lpOverlapped
0x180060485  lea     r8, [rsp+0B8h+CompletionKey]; lpCompletionKey
0x18006048a  lea     rdx, [rsp+0B8h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180060492  mov     rcx, cs:CompletionPort; CompletionPort
0x180060499  call    cs:__imp_GetQueuedCompletionStatus
0x1800604a0  nop     dword ptr [rax+rax+00h]
0x1800604a5  test    eax, eax
0x1800604a7  jnz     short loc_1800604E3
0x1800604a9  call    cs:__imp_GetLastError
0x1800604b0  nop     dword ptr [rax+rax+00h]
0x1800604b5  mov     ebx, eax
0x1800604b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800604be  cmp     rcx, r15
0x1800604c1  jz      short loc_180060512
0x1800604c3  test    byte ptr [rcx+1Ch], 10h
0x1800604c7  jz      short loc_180060512
0x1800604c9  mov     edx, 4Dh ; 'M'
0x1800604ce  mov     r9d, eax
0x1800604d1  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x1800604d8  mov     rcx, [rcx+10h]
0x1800604dc  call    WPP_SF_D
0x1800604e1  jmp     short loc_18006050B
0x1800604e3  lock inc cs:dword_1800FB184
0x1800604ea  lock dec cs:dword_1800FB1A8
0x1800604f1  cmp     [rsp+0B8h+CompletionKey], 1
0x1800604f7  jnz     short loc_180060509
0x1800604f9  mov     dword ptr [rsp+0B8h+arg_0], 1
0x180060504  call    DhcpNotifyQuarThreadsQuit
0x180060509  xor     ebx, ebx
0x18006050b  mov     rcx, cs:WPP_GLOBAL_Control
0x180060512  test    ebx, ebx
0x180060514  jz      short loc_18006054D
0x180060516  cmp     rcx, r15
0x180060519  jz      short loc_18006053C
0x18006051b  test    dword ptr [rcx+1Ch], 8000000h
0x180060522  jz      short loc_18006053C
0x180060524  mov     edx, 54h ; 'T'
0x180060529  mov     r9d, ebx
0x18006052c  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180060533  mov     rcx, [rcx+10h]
0x180060537  call    WPP_SF_D
0x18006053c  call    cs:__imp_SwitchToThread
0x180060543  nop     dword ptr [rax+rax+00h]
0x180060548  jmp     loc_18006041F
0x18006054d  cmp     dword ptr [rsp+0B8h+arg_0], 0
0x180060555  jz      short loc_180060589
0x180060557  cmp     rcx, r15
0x18006055a  jz      short loc_18006057A
0x18006055c  test    dword ptr [rcx+1Ch], 8000000h
0x180060563  jz      short loc_18006057A
0x180060565  mov     edx, 5Ch ; '\'
0x18006056a  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180060571  mov     rcx, [rcx+10h]
0x180060575  call    WPP_SF_
0x18006057a  add     rsp, 98h
0x180060581  pop     r15
0x180060583  pop     r13
0x180060585  pop     rdi
0x180060586  pop     rbx
0x180060587  retn
0x180060589  lea     rcx, QuarDecisionCritSection; lpCriticalSection
0x180060590  call    cs:__imp_EnterCriticalSection
0x180060597  nop     dword ptr [rax+rax+00h]
0x18006059c  call    GetAQuarDecisionPacket
0x1800605a1  mov     rbx, rax
0x1800605a4  mov     [rsp+0B8h+lpMem], rax
0x1800605ac  lea     rcx, QuarDecisionCritSection; lpCriticalSection
0x1800605b3  call    cs:__imp_LeaveCriticalSection
0x1800605ba  nop     dword ptr [rax+rax+00h]
0x1800605bf  test    rbx, rbx
0x1800605c2  jz      loc_18006041F
0x1800605c8  lock dec cs:DhcpGlobalNumPacketsInQuarDecisionQueue
0x1800605cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800605d6  cmp     rcx, r15
0x1800605d9  jz      short loc_180060602
0x1800605db  test    dword ptr [rcx+1Ch], 8000000h
0x1800605e2  jz      short loc_180060602
0x1800605e4  mov     edx, 55h ; 'U'
0x1800605e9  mov     r9, [rsp+0B8h+lpMem]
0x1800605f1  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x1800605f8  mov     rcx, [rcx+10h]
0x1800605fc  call    WPP_SF_q
0x180060601  nop
0x180060602  lea     rcx, PacketCritSection; lpCriticalSection
0x180060609  call    cs:__imp_EnterCriticalSection
0x180060610  nop     dword ptr [rax+rax+00h]
0x180060615  lea     r8, [rsp+0B8h+var_50]
0x18006061a  mov     r13, [rsp+0B8h+lpMem]
0x180060622  mov     edx, [r13+10h]
0x180060626  xor     edi, edi
0x180060628  mov     [rsp+0B8h+var_50], rdi
0x18006062d  mov     rcx, cs:QuarPacketWaitingQ
0x180060634  mov     rax, [rcx]
0x180060637  cmp     rcx, rax
0x18006063a  jz      short loc_18006064C
0x18006063c  cmp     edx, [rax+134h]
0x180060642  jnz     short loc_18006068F
0x180060644  mov     [r8], rax
0x180060647  mov     rdi, [rsp+0B8h+var_50]
0x18006064c  mov     rax, rdi
0x18006064f  neg     rax
0x180060652  sbb     ecx, ecx
0x180060654  not     ecx
0x180060656  bt      ecx, 1
0x18006065a  jb      short loc_18006069B
0x18006065c  test    rdi, rdi
0x18006065f  jz      short loc_18006069B
0x180060661  mov     rcx, [rdi]
0x180060664  mov     rax, [rdi+8]
0x180060668  cmp     [rcx+8], rdi
0x18006066c  jnz     short loc_180060694
0x18006066e  cmp     [rax], rdi
0x180060671  jnz     short loc_180060694
0x180060673  mov     [rax], rcx
0x180060676  mov     [rcx+8], rax
0x18006067a  mov     [rdi+8], rdi
0x18006067e  mov     [rdi], rdi
0x180060681  lock dec cs:DhcpGlobalNumPacketsInQuarWaitingQueue
0x180060688  mov     rdi, [rsp+0B8h+var_50]
0x18006068d  jmp     short loc_18006069B
0x18006068f  mov     rax, [rax]
0x180060692  jmp     short loc_180060637
0x180060694  mov     ecx, 3
0x180060699  int     29h; Win8: RtlFailFast(ecx)
0x18006069b  lea     rcx, PacketCritSection; lpCriticalSection
0x1800606a2  call    cs:__imp_LeaveCriticalSection
0x1800606a9  nop     dword ptr [rax+rax+00h]
0x1800606ae  test    rdi, rdi
0x1800606b1  jnz     short loc_1800606EE
0x1800606b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800606ba  cmp     rcx, r15
0x1800606bd  jz      short loc_1800606DC
0x1800606bf  test    byte ptr [rcx+1Ch], 10h
0x1800606c3  jz      short loc_1800606DC
0x1800606c5  lea     edx, [rdi+56h]
0x1800606c8  mov     r9d, [r13+10h]
0x1800606cc  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x1800606d3  mov     rcx, [rcx+10h]
0x1800606d7  call    WPP_SF_D
0x1800606dc  mov     rcx, [rsp+0B8h+lpMem]; lpMem
0x1800606e4  call    FreeQuarDecisionPacket
0x1800606e9  jmp     loc_18006041F
0x1800606ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800606f5  cmp     rcx, r15
0x1800606f8  jz      short loc_18006071B
0x1800606fa  test    dword ptr [rcx+1Ch], 8000000h
0x180060701  jz      short loc_18006071B
0x180060703  mov     edx, 57h ; 'W'
0x180060708  mov     r9, rdi
0x18006070b  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180060712  mov     rcx, [rcx+10h]
0x180060716  call    WPP_SF_q
0x18006071b  mov     rbx, [rsp+0B8h+lpMem]
0x180060723  mov     eax, [rbx+14h]
0x180060726  mov     [rdi+138h], eax
0x18006072c  mov     [rdi+140h], rbx
0x180060733  lea     rcx, [rdi+0F0h]
0x18006073a  lea     rdx, MemFree
0x180060741  call    MemArrayFree
0x180060746  cmp     dword ptr [rdi+138h], 1
0x18006074d  jnz     short loc_180060786
0x18006074f  mov     rcx, rdi
0x180060752  call    AssembleQuarantineUserClass
0x180060757  test    eax, eax
0x180060759  jz      short loc_180060786
0x18006075b  mov     rcx, cs:WPP_GLOBAL_Control
0x180060762  cmp     rcx, r15
0x180060765  jz      short loc_180060786
0x180060767  test    byte ptr [rcx+1Ch], 10h
0x18006076b  jz      short loc_180060786
0x18006076d  mov     edx, 59h ; 'Y'
0x180060772  mov     r9d, eax
0x180060775  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x18006077c  mov     rcx, [rcx+10h]
0x180060780  call    WPP_SF_D
0x180060785  nop
0x180060786  lea     rcx, PacketCritSection; lpCriticalSection
0x18006078d  call    cs:__imp_EnterCriticalSection
0x180060794  nop     dword ptr [rax+rax+00h]
0x180060799  cmp     dword ptr [rbx+14h], 2
0x18006079d  jnz     loc_180060906
0x1800607a3  xor     ebx, ebx
0x1800607a5  mov     [rsp+0B8h+arg_0], rbx
0x1800607ad  and     [rsp+0B8h+var_40], rbx
0x1800607b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800607b9  cmp     rcx, r15
0x1800607bc  jz      short loc_1800607DE
0x1800607be  test    dword ptr [rcx+1Ch], 4000h
0x1800607c5  jz      short loc_1800607DE
0x1800607c7  lea     edx, [rbx+5Ah]
0x1800607ca  mov     r9d, [r13+10h]
0x1800607ce  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x1800607d5  mov     rcx, [rcx+10h]
0x1800607d9  call    WPP_SF_D
0x1800607de  mov     rcx, rdi
0x1800607e1  call    DeleteHashQ
0x1800607e6  cmp     [rdi+130h], ebx
0x1800607ec  jz      short loc_180060820
0x1800607ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800607f5  cmp     rcx, r15
0x1800607f8  jz      short loc_180060820
0x1800607fa  test    dword ptr [rcx+1Ch], 20000000h
0x180060801  jz      short loc_180060820
0x180060803  mov     edx, 5Bh ; '['
0x180060808  mov     r9d, cs:dword_18015564C
0x18006080f  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180060816  mov     rcx, [rcx+10h]
0x18006081a  call    WPP_SF_D
0x18006081f  nop
0x180060820  mov     rax, cs:qword_180155830
0x180060827  test    rax, rax
0x18006082a  jz      short loc_180060854
0x18006082c  lea     rdx, [rdi+68h]
0x180060830  lea     rcx, [rdi+58h]
0x180060834  mov     r8, [rdi+128h]
0x18006083b  mov     [rsp+0B8h+var_90], r8
0x180060840  mov     [rsp+0B8h+var_98], rdi
0x180060845  mov     r9d, [rdi+74h]
0x180060849  mov     r8d, 0Ch
0x18006084f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060854  jmp     short loc_180060875
0x180060856  mov     [rsp+0B8h+var_58], eax
0x18006085a  mov     ecx, eax
0x18006085c  call    DhcpCalloutLogAV
0x180060861  lea     r15, WPP_GLOBAL_Control
0x180060868  mov     rdi, [rsp+0B8h+var_50]
0x18006086d  mov     rbx, [rsp+0B8h+arg_0]
0x180060875  lea     rdx, [rdi+148h]
0x18006087c  lea     rcx, [rdi+58h]
0x180060880  lea     r9, [rsp+0B8h+var_40]
0x180060885  xor     r8d, r8d
0x180060888  call    DhcpDetermineHostName
0x18006088d  lea     r9, [rdi+29h]
0x180060891  mov     ecx, 4B4h
0x180060896  call    GetString
0x18006089b  mov     rdx, rax
0x18006089e  mov     eax, [rdi+230h]
0x1800608a4  mov     [rsp+0B8h+var_60], eax
0x1800608a8  mov     rax, [rdi+228h]
0x1800608af  mov     [rsp+0B8h+var_68], rax
0x1800608b4  mov     [rsp+0B8h+var_70], rbx
0x1800608b9  mov     [rsp+0B8h+var_78], 2
0x1800608c1  mov     eax, [rdi+24h]
0x1800608c4  mov     [rsp+0B8h+var_80], eax
0x1800608c8  and     [rsp+0B8h+var_88], 0
0x1800608cd  mov     rbx, [rsp+0B8h+var_40]
0x1800608d2  mov     [rsp+0B8h+var_90], rbx
0x1800608d7  mov     eax, [rdi+250h]
0x1800608dd  mov     dword ptr [rsp+0B8h+var_98], eax
0x1800608e1  xor     r8d, r8d
0x1800608e4  lea     ecx, [r8+21h]
0x1800608e8  call    DhcpUpdateAuditLogQuar
0x1800608ed  test    rbx, rbx
0x1800608f0  jz      short loc_1800608FA
0x1800608f2  mov     rcx, rbx
0x1800608f5  call    DhcpFreeMemory
0x1800608fa  xor     edx, edx
0x1800608fc  mov     rcx, rdi
0x1800608ff  call    UnlockAndFreePacket
0x180060904  jmp     short loc_18006093C
0x180060906  mov     byte ptr [rdi+49h], 6
0x18006090a  mov     rax, cs:QuarPacketReadyQ
0x180060911  mov     rcx, [rax]
0x180060914  cmp     [rcx+8], rax
0x180060918  jz      short loc_180060921
0x18006091a  mov     ecx, 3
0x18006091f  int     29h; Win8: RtlFailFast(ecx)
0x180060921  mov     [rdi], rcx
0x180060924  mov     [rdi+8], rax
0x180060928  mov     [rcx+8], rdi
0x18006092c  mov     [rax], rdi
  ... truncated ...
```
