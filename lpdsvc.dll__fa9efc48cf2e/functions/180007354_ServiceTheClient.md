# ServiceTheClient

- ea: `0x180007354`
- end: `0x1800076f8`
- name: `ServiceTheClient`
- size: `932`
- prototype: `__int64 __fastcall(char *hMem)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task`

## callers

- `0x180007810`

## callees

- `0x180002e7c`
- `0x180002ea4`
- `0x180002fb4`
- `0x180003480`
- `0x180003d4c`
- `0x1800043d0`
- `0x18000453c`
- `0x180004b14`
- `0x180006014`
- `0x1800063b4`
- `0x1800064e4`
- `0x180007354`
- `0x180007700`
- `0x180008d44`
- `0x180008eb8`
- `0x18000920c`
- `0x1800099a8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180007365`
- `KERNEL32!GetCurrentThreadId` at `0x180007365`

## pseudocode

```c
__int64 __fastcall ServiceTheClient(char *hMem)
{
  DWORD CurrentThreadId; // esi
  bool v3; // zf
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rdx
  char v7; // dl
  LPCSTR v9; // [rsp+20h] [rbp-48h] BYREF
  __int64 v10; // [rsp+28h] [rbp-40h]

  CurrentThreadId = GetCurrentThreadId();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_29826dfb2f8839e6e8539e32ef026641_Traceguids);
  v3 = fShuttingDownGLB == 0;
  *((_DWORD *)hMem + 6) = 1;
  *((_DWORD *)hMem + 4) = CurrentThreadId;
  *((_QWORD *)hMem + 12) = -1;
  if ( !v3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_29826dfb2f8839e6e8539e32ef026641_Traceguids,
        CurrentThreadId);
    goto LABEL_62;
  }
  GetClientInfo(hMem);
  GetServerInfo(hMem);
  if ( (unsigned int)GetCmdFromClient((__int64)hMem) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_62;
    v5 = 18;
LABEL_61:
    WPP_SF_(v4[2], v5, WPP_29826dfb2f8839e6e8539e32ef026641_Traceguids);
LABEL_62:
    ReplyToClient((__int64)hMem, 1);
    goto LABEL_63;
  }
  if ( !(unsigned int)ParseQueueName(hMem) )
  {
    v10 = 0;
    v9 = hMem + 120;
    LpdReportEvent(0xC0000FA8, 1u, &v9, 0);
    *((_DWORD *)hMem + 6) = 0;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_62;
    v5 = 19;
    goto LABEL_61;
  }
  if ( **((_BYTE **)hMem + 4) == 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_29826dfb2f8839e6e8539e32ef026641_Traceguids);
    v3 = fAllowPrintResumeGLB == 0;
    *((_WORD *)hMem + 10) = 1;
    v7 = v3 || (unsigned int)ResumePrinting((__int64)hMem) != 0;
    goto LABEL_55;
  }
  if ( **((_BYTE **)hMem + 4) == 2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_29826dfb2f8839e6e8539e32ef026641_Traceguids);
    *((_WORD *)hMem + 10) = 2;
    ProcessJob((__int64)hMem);
    CleanupConn(hMem);
    if ( *((_WORD *)hMem + 10) == 10 )
      goto LABEL_56;
    AbortThisJob(hMem);
    if ( *((_DWORD *)hMem + 6) )
    {
      v10 = 0;
      v9 = hMem + 120;
      LpdReportEvent(0xC0000FAA, 1u, &v9, 0);
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v6 = 21;
      goto LABEL_29;
    }
    goto LABEL_57;
  }
  if ( **((_BYTE **)hMem + 4) != 3 && **((_BYTE **)hMem + 4) != 4 )
  {
    if ( **((_BYTE **)hMem + 4) != 5 )
    {
LABEL_56:
      v4 = WPP_GLOBAL_Control;
      goto LABEL_57;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_29826dfb2f8839e6e8539e32ef026641_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
    if ( !fJobRemovalEnabledGLB )
      goto LABEL_57;
    *((_WORD *)hMem + 10) = 5;
    if ( (unsigned int)ParseQueueRequest(hMem, 1) )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v6 = 26;
LABEL_29:
        WPP_SF_(v4[2], v6, WPP_29826dfb2f8839e6e8539e32ef026641_Traceguids);
        goto LABEL_56;
      }
      goto LABEL_57;
    }
    if ( (unsigned int)RemoveJobs((__int64)hMem) )
      goto LABEL_56;
    v7 = 0;
LABEL_55:
    ReplyToClient((__int64)hMem, v7);
    goto LABEL_56;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_29826dfb2f8839e6e8539e32ef026641_Traceguids);
  *((_WORD *)hMem + 10) = 4;
  if ( !(unsigned int)ParseQueueRequest(hMem, 0) )
  {
    SendQueueStatus((__int64)hMem);
    goto LABEL_56;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v6 = 24;
    goto LABEL_29;
  }
LABEL_57:
  if ( *((_WORD *)hMem + 10) != 10 )
  {
    if ( v4 == &WPP_GLOBAL_Control || (*((_BYTE *)v4 + 28) & 8) == 0 )
      goto LABEL_62;
    v5 = 27;
    goto LABEL_61;
  }
LABEL_63:
  TerminateConnection(hMem);
  return 0;
}

```

## disassembly

```asm
0x180007354  push    rbx
0x180007356  push    rsi
0x180007357  push    rdi
0x180007358  push    r12
0x18000735a  push    r14
0x18000735c  push    r15
0x18000735e  sub     rsp, 38h
0x180007362  mov     rbx, rcx
0x180007365  call    cs:__imp_GetCurrentThreadId
0x18000736b  mov     esi, eax
0x18000736d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007374  lea     r14, WPP_GLOBAL_Control
0x18000737b  lea     r15, WPP_29826dfb2f8839e6e8539e32ef026641_Traceguids
0x180007382  mov     r12d, 1
0x180007388  cmp     rcx, r14
0x18000738b  jz      short loc_1800073A4
0x18000738d  test    [rcx+1Ch], r12b
0x180007391  jz      short loc_1800073A4
0x180007393  mov     rcx, [rcx+10h]
0x180007397  lea     edx, [r12+0Fh]
0x18000739c  mov     r8, r15
0x18000739f  call    WPP_SF_
0x1800073a4  cmp     cs:fShuttingDownGLB, 0
0x1800073ab  mov     [rbx+18h], r12d
0x1800073af  mov     [rbx+10h], esi
0x1800073b2  mov     qword ptr [rbx+60h], 0FFFFFFFFFFFFFFFFh
0x1800073ba  jz      short loc_1800073F2
0x1800073bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073c3  cmp     rcx, r14
0x1800073c6  jz      loc_1800076D5
0x1800073cc  mov     edi, 2
0x1800073d1  test    [rcx+1Ch], dil
0x1800073d5  jz      loc_1800076D5
0x1800073db  mov     rcx, [rcx+10h]
0x1800073df  lea     edx, [rdi+0Fh]
0x1800073e2  mov     r9d, esi
0x1800073e5  mov     r8, r15
0x1800073e8  call    WPP_SF_d
0x1800073ed  jmp     loc_1800076D5
0x1800073f2  mov     rcx, rbx
0x1800073f5  call    GetClientInfo
0x1800073fa  mov     rcx, rbx
0x1800073fd  call    GetServerInfo
0x180007402  mov     rcx, rbx
0x180007405  call    GetCmdFromClient
0x18000740a  test    eax, eax
0x18000740c  jz      short loc_180007432
0x18000740e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007415  cmp     rcx, r14
0x180007418  jz      loc_1800076D5
0x18000741e  test    byte ptr [rcx+1Ch], 8
0x180007422  jz      loc_1800076D5
0x180007428  mov     edx, 12h
0x18000742d  jmp     loc_1800076C9
0x180007432  mov     rcx, rbx
0x180007435  call    ParseQueueName
0x18000743a  test    eax, eax
0x18000743c  jnz     short loc_180007490
0x18000743e  lea     rax, [rbx+78h]
0x180007442  mov     [rsp+68h+var_40], 0
0x18000744b  mov     edx, r12d
0x18000744e  mov     [rsp+68h+var_48], rax
0x180007453  xor     r9d, r9d
0x180007456  lea     r8, [rsp+68h+var_48]
0x18000745b  mov     ecx, 0C0000FA8h; dwEventID
0x180007460  call    LpdReportEvent
0x180007465  mov     dword ptr [rbx+18h], 0
0x18000746c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007473  cmp     rcx, r14
0x180007476  jz      loc_1800076D5
0x18000747c  test    byte ptr [rcx+1Ch], 8
0x180007480  jz      loc_1800076D5
0x180007486  mov     edx, 13h
0x18000748b  jmp     loc_1800076C9
0x180007490  mov     rax, [rbx+20h]
0x180007494  movsx   ecx, byte ptr [rax]
0x180007497  sub     ecx, r12d
0x18000749a  jz      loc_18000765B
0x1800074a0  sub     ecx, r12d
0x1800074a3  jz      loc_1800075C5
0x1800074a9  sub     ecx, r12d
0x1800074ac  jz      loc_18000755A
0x1800074b2  sub     ecx, r12d
0x1800074b5  jz      loc_18000755A
0x1800074bb  cmp     ecx, r12d
0x1800074be  jnz     loc_1800076AB
0x1800074c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074cb  cmp     rcx, r14
0x1800074ce  jz      short loc_1800074F1
0x1800074d0  mov     edi, 2
0x1800074d5  test    [rcx+1Ch], dil
0x1800074d9  jz      short loc_1800074F1
0x1800074db  mov     rcx, [rcx+10h]
0x1800074df  lea     edx, [rdi+17h]
0x1800074e2  mov     r8, r15
0x1800074e5  call    WPP_SF_
0x1800074ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074f1  cmp     cs:fJobRemovalEnabledGLB, 0
0x1800074f8  jz      loc_1800076B2
0x1800074fe  mov     edx, r12d
0x180007501  mov     word ptr [rbx+14h], 5
0x180007507  mov     rcx, rbx
0x18000750a  call    ParseQueueRequest
0x18000750f  test    eax, eax
0x180007511  jz      short loc_180007543
0x180007513  mov     rcx, cs:WPP_GLOBAL_Control
0x18000751a  cmp     rcx, r14
0x18000751d  jz      loc_1800076B2
0x180007523  test    byte ptr [rcx+1Ch], 8
0x180007527  jz      loc_1800076B2
0x18000752d  mov     edx, 1Ah
0x180007532  mov     rcx, [rcx+10h]
0x180007536  mov     r8, r15
0x180007539  call    WPP_SF_
0x18000753e  jmp     loc_1800076AB
0x180007543  mov     rcx, rbx
0x180007546  call    RemoveJobs
0x18000754b  test    eax, eax
0x18000754d  jnz     loc_1800076AB
0x180007553  xor     edx, edx
0x180007555  jmp     loc_1800076A3
0x18000755a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007561  cmp     rcx, r14
0x180007564  jz      short loc_180007580
0x180007566  mov     edi, 2
0x18000756b  test    [rcx+1Ch], dil
0x18000756f  jz      short loc_180007580
0x180007571  mov     rcx, [rcx+10h]
0x180007575  lea     edx, [rdi+15h]
0x180007578  mov     r8, r15
0x18000757b  call    WPP_SF_
0x180007580  xor     edx, edx
0x180007582  mov     word ptr [rbx+14h], 4
0x180007588  mov     rcx, rbx
0x18000758b  call    ParseQueueRequest
0x180007590  test    eax, eax
0x180007592  jz      short loc_1800075B8
0x180007594  mov     rcx, cs:WPP_GLOBAL_Control
0x18000759b  cmp     rcx, r14
0x18000759e  jz      loc_1800076B2
0x1800075a4  test    byte ptr [rcx+1Ch], 8
0x1800075a8  jz      loc_1800076B2
0x1800075ae  mov     edx, 18h
0x1800075b3  jmp     loc_180007532
0x1800075b8  mov     rcx, rbx
0x1800075bb  call    SendQueueStatus
0x1800075c0  jmp     loc_1800076AB
0x1800075c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075cc  mov     edi, 2
0x1800075d1  cmp     rcx, r14
0x1800075d4  jz      short loc_1800075EB
0x1800075d6  test    [rcx+1Ch], dil
0x1800075da  jz      short loc_1800075EB
0x1800075dc  mov     rcx, [rcx+10h]
0x1800075e0  lea     edx, [rdi+12h]
0x1800075e3  mov     r8, r15
0x1800075e6  call    WPP_SF_
0x1800075eb  mov     rcx, rbx
0x1800075ee  mov     [rbx+14h], di
0x1800075f2  call    ProcessJob
0x1800075f7  mov     rcx, rbx
0x1800075fa  call    CleanupConn
0x1800075ff  cmp     word ptr [rbx+14h], 0Ah
0x180007604  jz      loc_1800076AB
0x18000760a  mov     rcx, rbx
0x18000760d  call    AbortThisJob
0x180007612  cmp     dword ptr [rbx+18h], 0
0x180007616  jz      short loc_18000763F
0x180007618  lea     rax, [rbx+78h]
0x18000761c  mov     [rsp+68h+var_40], 0
0x180007625  mov     edx, r12d
0x180007628  mov     [rsp+68h+var_48], rax
0x18000762d  xor     r9d, r9d
0x180007630  lea     r8, [rsp+68h+var_48]
0x180007635  mov     ecx, 0C0000FAAh; dwEventID
0x18000763a  call    LpdReportEvent
0x18000763f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007646  cmp     rcx, r14
0x180007649  jz      short loc_1800076B2
0x18000764b  test    byte ptr [rcx+1Ch], 8
0x18000764f  jz      short loc_1800076B2
0x180007651  mov     edx, 15h
0x180007656  jmp     loc_180007532
0x18000765b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007662  cmp     rcx, r14
0x180007665  jz      short loc_180007681
0x180007667  mov     edi, 2
0x18000766c  test    [rcx+1Ch], dil
0x180007670  jz      short loc_180007681
0x180007672  mov     rcx, [rcx+10h]
0x180007676  lea     edx, [rdi+14h]
0x180007679  mov     r8, r15
0x18000767c  call    WPP_SF_
0x180007681  cmp     cs:fAllowPrintResumeGLB, 0
0x180007688  mov     [rbx+14h], r12w
0x18000768d  jz      short loc_1800076A0
0x18000768f  mov     rcx, rbx
0x180007692  call    ResumePrinting
0x180007697  xor     edx, edx
0x180007699  test    eax, eax
0x18000769b  setnz   dl
0x18000769e  jmp     short loc_1800076A3
0x1800076a0  mov     edx, r12d
0x1800076a3  mov     rcx, rbx
0x1800076a6  call    ReplyToClient
0x1800076ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076b2  cmp     word ptr [rbx+14h], 0Ah
0x1800076b7  jz      short loc_1800076E0
0x1800076b9  cmp     rcx, r14
0x1800076bc  jz      short loc_1800076D5
0x1800076be  test    byte ptr [rcx+1Ch], 8
0x1800076c2  jz      short loc_1800076D5
0x1800076c4  mov     edx, 1Bh
0x1800076c9  mov     rcx, [rcx+10h]
0x1800076cd  mov     r8, r15
0x1800076d0  call    WPP_SF_
0x1800076d5  mov     edx, r12d
0x1800076d8  mov     rcx, rbx
0x1800076db  call    ReplyToClient
0x1800076e0  mov     rcx, rbx; hMem
0x1800076e3  call    TerminateConnection
0x1800076e8  xor     eax, eax
0x1800076ea  add     rsp, 38h
0x1800076ee  pop     r15
0x1800076f0  pop     r14
0x1800076f2  pop     r12
0x1800076f4  pop     rdi
0x1800076f5  pop     rsi
0x1800076f6  pop     rbx
0x1800076f7  retn
```
