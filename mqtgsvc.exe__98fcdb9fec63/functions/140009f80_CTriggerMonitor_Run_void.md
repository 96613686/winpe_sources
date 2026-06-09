# CTriggerMonitor::Run(void)

- ea: `0x140009f80`
- end: `0x14000a3a1`
- name: `?Run@CTriggerMonitor@@EEAA_NXZ`
- size: `1057`
- prototype: `bool __fastcall(CTriggerMonitor *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003720`
- `0x14000393c`
- `0x140005b38`
- `0x140006418`
- `0x140006624`
- `0x14000752c`
- `0x140007554`
- `0x140007594`
- `0x140009854`
- `0x140009b68`
- `0x140009f80`
- `0x14000a5bc`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x140009fff`
- `KERNEL32!GetTickCount` at `0x140009fff`
- `KERNEL32!GetLastError` at `0x14000a081`
- `KERNEL32!GetLastError` at `0x14000a081`
- `KERNEL32!WaitForSingleObject` at `0x14000a064`
- `KERNEL32!WaitForSingleObject` at `0x14000a064`
- `KERNEL32!GetQueuedCompletionStatus` at `0x14000a04e`
- `KERNEL32!GetQueuedCompletionStatus` at `0x14000a04e`

## pseudocode

```c
bool __fastcall CTriggerMonitor::Run(CTriggerMonitor *this)
{
  int v2; // edi
  bool v3; // r14
  BOOL QueuedCompletionStatus; // ebx
  LPOVERLAPPED v5; // rbx
  int Internal; // eax
  DWORD NumberOfBytesTransferred; // [rsp+70h] [rbp+38h] BYREF
  unsigned __int64 CompletionKey; // [rsp+78h] [rbp+40h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+80h] [rbp+48h] BYREF
  LPOVERLAPPED v11; // [rsp+88h] [rbp+50h]

  v2 = 0;
  NumberOfBytesTransferred = 0;
  CompletionKey = 0;
  v3 = 0;
  Overlapped = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_1833f040ae3e358d840c1ed912348424_Traceguids);
  while ( *((_BYTE *)this + 72) )
  {
    if ( v2 < 0 )
      return v2 >= 0;
    CompletionKey = 0;
    _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)this + 13) + 160LL), 1u);
    if ( !v3 )
      *((_DWORD *)this + 24) = GetTickCount();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_1833f040ae3e358d840c1ed912348424_Traceguids);
    QueuedCompletionStatus = GetQueuedCompletionStatus(
                               **((HANDLE **)this + 11),
                               &NumberOfBytesTransferred,
                               &CompletionKey,
                               &Overlapped,
                               0x1D4C0u);
    if ( WaitForSingleObject(g_hServicePaused, 0xFFFFFFFF) == -1
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_1833f040ae3e358d840c1ed912348424_Traceguids);
    }
    v3 = CompletionKey == 2863311530 || !Overlapped;
    CTriggerMonitor::MonitorExitingWaitState(this, v3);
    if ( QueuedCompletionStatus )
    {
      if ( CompletionKey != 2863311530 )
      {
        v5 = Overlapped - 2;
        v11 = Overlapped - 2;
        if ( CompletionKey == 3149642683 )
        {
          if ( CQueue::IsTriggerExist((CQueue *)&Overlapped[-2]) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
            CQueue::RequestNextMessage((CQueue *)v5, 0, 1);
          }
        }
        else if ( CQueue::IsTriggerExist((CQueue *)&Overlapped[-2]) )
        {
          CTriggerMonitor::ProcessReceivedMsgEvent(this, (struct CQueue *)v5);
        }
        goto LABEL_66;
      }
    }
    else if ( Overlapped )
    {
      Internal = Overlapped->Internal;
      if ( LODWORD(Overlapped->Internal) == -2147024890 )
        goto LABEL_61;
      switch ( Internal )
      {
        case -1073741536:
          v5 = Overlapped - 2;
          v11 = Overlapped - 2;
          if ( CQueue::IsTriggerExist((CQueue *)&Overlapped[-2]) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
            CQueue::RequestNextMessage((CQueue *)v5, 0, 0);
          }
          break;
        case -1072824313:
          goto LABEL_61;
        case -1072824294:
          v5 = Overlapped - 2;
          v11 = Overlapped - 2;
          if ( CQueue::IsTriggerExist((CQueue *)&Overlapped[-2]) )
          {
            CMsgProperties::ReAllocMsgBody((CMsgProperties *)v5[4].Pointer);
            CQueue::RequestNextMessage((CQueue *)v5, 0, 0);
          }
          break;
        case -1072824291:
          v5 = Overlapped - 2;
          v11 = Overlapped - 2;
          if ( CQueue::IsTriggerExist((CQueue *)&Overlapped[-2]) )
            CQueue::RequestNextMessage((CQueue *)v5, 0, 1);
          break;
        case -1072824245:
          goto LABEL_61;
        case -1072824230:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_q(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              WPP_1833f040ae3e358d840c1ed912348424_Traceguids,
              Overlapped->Internal);
          continue;
        case -1072824215:
LABEL_61:
          v5 = Overlapped - 2;
          v11 = Overlapped - 2;
          if ( Overlapped != (LPOVERLAPPED)64 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), Internal);
            BYTE1(v5[1].InternalHigh) = 1;
            HIDWORD(v5[1].InternalHigh) = 0;
          }
          break;
        default:
          v2 = Overlapped->Internal;
          v5 = Overlapped - 2;
          v11 = Overlapped - 2;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), Internal);
          if ( CQueue::IsTriggerExist((CQueue *)v5) )
            CQueue::RequestNextMessage((CQueue *)v5, 0, 0);
          break;
      }
LABEL_66:
      SafeRelease<CQueue>((CReference *)v5);
    }
  }
  return v2 >= 0;
}

```

## disassembly

```asm
0x140009f80  push    rbp
0x140009f82  push    rbx
0x140009f83  push    rsi
0x140009f84  push    rdi
0x140009f85  push    r13
0x140009f87  push    r14
0x140009f89  mov     rbp, rsp
0x140009f8c  sub     rsp, 38h
0x140009f90  mov     rsi, rcx
0x140009f93  xor     edi, edi
0x140009f95  mov     [rbp+NumberOfBytesTransferred], edi
0x140009f98  mov     [rbp+CompletionKey], rdi
0x140009f9c  xor     r14b, r14b
0x140009f9f  mov     [rbp+Overlapped], rdi
0x140009fa3  lea     r13, WPP_GLOBAL_Control
0x140009faa  mov     rcx, cs:WPP_GLOBAL_Control
0x140009fb1  cmp     rcx, r13
0x140009fb4  jz      short loc_140009FCF
0x140009fb6  test    byte ptr [rcx+1Ch], 4
0x140009fba  jz      short loc_140009FCF
0x140009fbc  lea     edx, [rdi+0Bh]
0x140009fbf  lea     r8, WPP_1833f040ae3e358d840c1ed912348424_Traceguids
0x140009fc6  mov     rcx, [rcx+10h]
0x140009fca  call    WPP_SF_
0x140009fcf  cmp     [rsi+48h], dil
0x140009fd3  jz      loc_14000A38A
0x140009fd9  test    edi, edi
0x140009fdb  js      loc_14000A38A
0x140009fe1  mov     [rbp+CompletionKey], 0
0x140009fe9  mov     rax, [rsi+68h]
0x140009fed  mov     ebx, 1
0x140009ff2  lock xadd [rax+0A0h], ebx
0x140009ffa  test    r14b, r14b
0x140009ffd  jnz     short loc_14000A008
0x140009fff  call    cs:__imp_GetTickCount
0x14000a005  mov     [rsi+60h], eax
0x14000a008  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a00f  cmp     rcx, r13
0x14000a012  jz      short loc_14000A033
0x14000a014  test    byte ptr [rcx+1Ch], 4
0x14000a018  jz      short loc_14000A033
0x14000a01a  mov     edx, 13h
0x14000a01f  lea     r9d, [rbx+1]
0x14000a023  lea     r8, WPP_1833f040ae3e358d840c1ed912348424_Traceguids
0x14000a02a  mov     rcx, [rcx+10h]
0x14000a02e  call    WPP_SF_d
0x14000a033  mov     rcx, [rsi+58h]
0x14000a037  mov     [rsp+38h+dwMilliseconds], 1D4C0h; dwMilliseconds
0x14000a03f  lea     r9, [rbp+Overlapped]; lpOverlapped
0x14000a043  lea     r8, [rbp+CompletionKey]; lpCompletionKey
0x14000a047  lea     rdx, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x14000a04b  mov     rcx, [rcx]; CompletionPort
0x14000a04e  call    cs:__imp_GetQueuedCompletionStatus
0x14000a054  mov     ebx, eax
0x14000a056  or      r14d, 0FFFFFFFFh
0x14000a05a  mov     edx, r14d; dwMilliseconds
0x14000a05d  mov     rcx, cs:?g_hServicePaused@@3VCHandle@@A; hHandle
0x14000a064  call    cs:__imp_WaitForSingleObject
0x14000a06a  cmp     eax, r14d
0x14000a06d  jnz     short loc_14000A0A6
0x14000a06f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a076  cmp     rcx, r13
0x14000a079  jz      short loc_14000A0A6
0x14000a07b  test    byte ptr [rcx+1Ch], 4
0x14000a07f  jz      short loc_14000A0A6
0x14000a081  call    cs:__imp_GetLastError
0x14000a087  mov     edx, 0Ch
0x14000a08c  mov     r9d, eax
0x14000a08f  lea     r8, WPP_1833f040ae3e358d840c1ed912348424_Traceguids
0x14000a096  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a09d  mov     rcx, [rcx+10h]
0x14000a0a1  call    WPP_SF_d
0x14000a0a6  mov     eax, 0AAAAAAAAh
0x14000a0ab  cmp     [rbp+CompletionKey], rax
0x14000a0af  jz      short loc_14000A0BD
0x14000a0b1  cmp     [rbp+Overlapped], 0
0x14000a0b6  jz      short loc_14000A0BD
0x14000a0b8  xor     r14b, r14b
0x14000a0bb  jmp     short loc_14000A0C0
0x14000a0bd  mov     r14b, 1
0x14000a0c0  mov     dl, r14b; bool
0x14000a0c3  mov     rcx, rsi; this
0x14000a0c6  call    ?MonitorExitingWaitState@CTriggerMonitor@@AEAAX_N@Z; CTriggerMonitor::MonitorExitingWaitState(bool)
0x14000a0cb  cmp     ebx, 1
0x14000a0ce  jnz     loc_14000A16E
0x14000a0d4  mov     eax, 0AAAAAAAAh
0x14000a0d9  cmp     [rbp+CompletionKey], rax
0x14000a0dd  jz      loc_14000A380
0x14000a0e3  mov     eax, 0BBBBBBBBh
0x14000a0e8  mov     rbx, [rbp+Overlapped]
0x14000a0ec  add     rbx, 0FFFFFFFFFFFFFFC0h
0x14000a0f0  mov     [rbp+arg_18], rbx
0x14000a0f4  cmp     [rbp+CompletionKey], rax
0x14000a0f8  jz      short loc_14000A117
0x14000a0fa  mov     rcx, rbx; this
0x14000a0fd  call    ?IsTriggerExist@CQueue@@QEAA_NXZ; CQueue::IsTriggerExist(void)
0x14000a102  test    al, al
0x14000a104  jz      short loc_14000A112
0x14000a106  mov     rdx, rbx; struct CQueue *
0x14000a109  mov     rcx, rsi; this
0x14000a10c  call    ?ProcessReceivedMsgEvent@CTriggerMonitor@@AEAAXPEAVCQueue@@@Z; CTriggerMonitor::ProcessReceivedMsgEvent(CQueue *)
0x14000a111  nop
0x14000a112  jmp     loc_14000A378
0x14000a117  mov     rcx, rbx; this
0x14000a11a  call    ?IsTriggerExist@CQueue@@QEAA_NXZ; CQueue::IsTriggerExist(void)
0x14000a11f  test    al, al
0x14000a121  jz      short loc_14000A169
0x14000a123  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a12a  cmp     rcx, r13
0x14000a12d  jz      short loc_14000A15B
0x14000a12f  test    byte ptr [rcx+1Ch], 4
0x14000a133  jz      short loc_14000A15B
0x14000a135  mov     rax, [rbx+60h]
0x14000a139  test    rax, rax
0x14000a13c  jz      short loc_14000A143
0x14000a13e  mov     r9, [rax]
0x14000a141  jmp     short loc_14000A146
0x14000a143  xor     r9d, r9d
0x14000a146  mov     edx, 0Dh
0x14000a14b  lea     r8, WPP_1833f040ae3e358d840c1ed912348424_Traceguids
0x14000a152  mov     rcx, [rcx+10h]; LoggerHandle
0x14000a156  call    WPP_SF_S
0x14000a15b  mov     r8b, 1; bool
0x14000a15e  xor     edx, edx; bool
0x14000a160  mov     rcx, rbx; this
0x14000a163  call    ?RequestNextMessage@CQueue@@QEAAJ_N0@Z; CQueue::RequestNextMessage(bool,bool)
0x14000a168  nop
0x14000a169  jmp     loc_14000A378
0x14000a16e  mov     rcx, [rbp+Overlapped]
0x14000a172  test    rcx, rcx
0x14000a175  jz      loc_14000A380
0x14000a17b  mov     eax, [rcx]
0x14000a17d  cmp     eax, 80070006h
0x14000a182  jz      loc_14000A324
0x14000a188  cmp     eax, 0C0000120h
0x14000a18d  jz      loc_14000A2C8
0x14000a193  cmp     eax, 0C00E0007h
0x14000a198  jz      loc_14000A324
0x14000a19e  cmp     eax, 0C00E001Ah
0x14000a1a3  jz      loc_14000A295
0x14000a1a9  cmp     eax, 0C00E001Dh
0x14000a1ae  jz      loc_14000A26E
0x14000a1b4  cmp     eax, 0C00E004Bh
0x14000a1b9  jz      loc_14000A324
0x14000a1bf  cmp     eax, 0C00E005Ah
0x14000a1c4  jz      short loc_14000A237
0x14000a1c6  cmp     eax, 0C00E0069h
0x14000a1cb  jz      loc_14000A324
0x14000a1d1  mov     edi, eax
0x14000a1d3  lea     rbx, [rcx-40h]
0x14000a1d7  mov     [rbp+arg_18], rbx
0x14000a1db  mov     r10, cs:WPP_GLOBAL_Control
0x14000a1e2  cmp     r10, r13
0x14000a1e5  jz      short loc_14000A218
0x14000a1e7  test    byte ptr [r10+1Ch], 1
0x14000a1ec  jz      short loc_14000A218
0x14000a1ee  mov     rcx, [rbx+60h]
0x14000a1f2  test    rcx, rcx
0x14000a1f5  jz      short loc_14000A1FC
0x14000a1f7  mov     r9, [rcx]
0x14000a1fa  jmp     short loc_14000A1FF
0x14000a1fc  xor     r9d, r9d
0x14000a1ff  mov     edx, 11h
0x14000a204  mov     [rsp+38h+dwMilliseconds], eax; char
0x14000a208  lea     r8, WPP_1833f040ae3e358d840c1ed912348424_Traceguids
0x14000a20f  mov     rcx, [r10+10h]; LoggerHandle
0x14000a213  call    WPP_SF_Sd
0x14000a218  mov     rcx, rbx; this
0x14000a21b  call    ?IsTriggerExist@CQueue@@QEAA_NXZ; CQueue::IsTriggerExist(void)
0x14000a220  test    al, al
0x14000a222  jz      short loc_14000A232
0x14000a224  xor     r8d, r8d; bool
0x14000a227  xor     edx, edx; bool
0x14000a229  mov     rcx, rbx; this
0x14000a22c  call    ?RequestNextMessage@CQueue@@QEAAJ_N0@Z; CQueue::RequestNextMessage(bool,bool)
0x14000a231  nop
0x14000a232  jmp     loc_14000A378
0x14000a237  mov     rax, cs:WPP_GLOBAL_Control
0x14000a23e  cmp     rax, r13
0x14000a241  jz      loc_14000A380
0x14000a247  test    byte ptr [rax+1Ch], 4
0x14000a24b  jz      loc_14000A380
0x14000a251  mov     edx, 0Eh
0x14000a256  mov     r9, [rcx]
0x14000a259  lea     r8, WPP_1833f040ae3e358d840c1ed912348424_Traceguids
0x14000a260  mov     rcx, [rax+10h]
0x14000a264  call    WPP_SF_q
0x14000a269  jmp     loc_14000A380
0x14000a26e  lea     rbx, [rcx-40h]
0x14000a272  mov     [rbp+arg_18], rbx
0x14000a276  mov     rcx, rbx; this
0x14000a279  call    ?IsTriggerExist@CQueue@@QEAA_NXZ; CQueue::IsTriggerExist(void)
0x14000a27e  test    al, al
0x14000a280  jz      short loc_14000A290
0x14000a282  mov     r8b, 1; bool
0x14000a285  xor     edx, edx; bool
0x14000a287  mov     rcx, rbx; this
0x14000a28a  call    ?RequestNextMessage@CQueue@@QEAAJ_N0@Z; CQueue::RequestNextMessage(bool,bool)
0x14000a28f  nop
0x14000a290  jmp     loc_14000A378
0x14000a295  lea     rbx, [rcx-40h]
0x14000a299  mov     [rbp+arg_18], rbx
0x14000a29d  mov     rcx, rbx; this
0x14000a2a0  call    ?IsTriggerExist@CQueue@@QEAA_NXZ; CQueue::IsTriggerExist(void)
0x14000a2a5  test    al, al
0x14000a2a7  jz      short loc_14000A2C3
0x14000a2a9  mov     rcx, [rbx+90h]; this
0x14000a2b0  call    ?ReAllocMsgBody@CMsgProperties@@QEAA_NXZ; CMsgProperties::ReAllocMsgBody(void)
0x14000a2b5  xor     r8d, r8d; bool
0x14000a2b8  xor     edx, edx; bool
0x14000a2ba  mov     rcx, rbx; this
0x14000a2bd  call    ?RequestNextMessage@CQueue@@QEAAJ_N0@Z; CQueue::RequestNextMessage(bool,bool)
0x14000a2c2  nop
0x14000a2c3  jmp     loc_14000A378
0x14000a2c8  lea     rbx, [rcx-40h]
0x14000a2cc  mov     [rbp+arg_18], rbx
0x14000a2d0  mov     rcx, rbx; this
0x14000a2d3  call    ?IsTriggerExist@CQueue@@QEAA_NXZ; CQueue::IsTriggerExist(void)
0x14000a2d8  test    al, al
0x14000a2da  jz      short loc_14000A322
0x14000a2dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a2e3  cmp     rcx, r13
0x14000a2e6  jz      short loc_14000A314
0x14000a2e8  test    byte ptr [rcx+1Ch], 4
0x14000a2ec  jz      short loc_14000A314
0x14000a2ee  mov     rax, [rbx+60h]
0x14000a2f2  test    rax, rax
0x14000a2f5  jz      short loc_14000A2FC
0x14000a2f7  mov     r9, [rax]
0x14000a2fa  jmp     short loc_14000A2FF
0x14000a2fc  xor     r9d, r9d
0x14000a2ff  mov     edx, 0Fh
0x14000a304  lea     r8, WPP_1833f040ae3e358d840c1ed912348424_Traceguids
0x14000a30b  mov     rcx, [rcx+10h]; LoggerHandle
0x14000a30f  call    WPP_SF_S
0x14000a314  xor     r8d, r8d; bool
0x14000a317  xor     edx, edx; bool
0x14000a319  mov     rcx, rbx; this
0x14000a31c  call    ?RequestNextMessage@CQueue@@QEAAJ_N0@Z; CQueue::RequestNextMessage(bool,bool)
0x14000a321  nop
0x14000a322  jmp     short loc_14000A378
0x14000a324  lea     rbx, [rcx-40h]
0x14000a328  mov     [rbp+arg_18], rbx
0x14000a32c  test    rbx, rbx
0x14000a32f  jz      short loc_14000A378
0x14000a331  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a338  cmp     rcx, r13
0x14000a33b  jz      short loc_14000A36D
0x14000a33d  test    byte ptr [rcx+1Ch], 4
0x14000a341  jz      short loc_14000A36D
0x14000a343  mov     rdx, [rbx+60h]
0x14000a347  test    rdx, rdx
0x14000a34a  jz      short loc_14000A351
0x14000a34c  mov     r9, [rdx]
0x14000a34f  jmp     short loc_14000A354
0x14000a351  xor     r9d, r9d
0x14000a354  mov     edx, 10h
0x14000a359  mov     [rsp+38h+dwMilliseconds], eax; char
0x14000a35d  lea     r8, WPP_1833f040ae3e358d840c1ed912348424_Traceguids
0x14000a364  mov     rcx, [rcx+10h]; LoggerHandle
0x14000a368  call    WPP_SF_Sd
0x14000a36d  mov     byte ptr [rbx+29h], 1
0x14000a371  mov     dword ptr [rbx+2Ch], 0
0x14000a378  mov     rcx, rbx
0x14000a37b  call    ??$SafeRelease@VCQueue@@@@YAXPEAVCQueue@@@Z; SafeRelease<CQueue>(CQueue *)
0x14000a380  cmp     byte ptr [rsi+48h], 0
0x14000a384  jnz     loc_140009FD9
0x14000a38a  shr     edi, 1Fh
0x14000a38d  xor     dil, 1
0x14000a391  mov     al, dil
0x14000a394  add     rsp, 38h
0x14000a398  pop     r14
0x14000a39a  pop     r13
0x14000a39c  pop     rdi
0x14000a39d  pop     rsi
0x14000a39e  pop     rbx
0x14000a39f  pop     rbp
0x14000a3a0  retn
```
