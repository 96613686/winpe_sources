# CIOPort::ProcessItems(CThreadState *)

- ea: `0x180116ea0`
- end: `0x18011712a`
- name: `?ProcessItems@CIOPort@@IEAA?AW4eThreadNextStep@@PEAUCThreadState@@@Z`
- size: `650`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1801176a0`

## callees

- `0x1800264b4`
- `0x180107770`
- `0x180114a60`
- `0x180114be0`
- `0x1801155ac`
- `0x1801156f0`
- `0x180116ea0`
- `0x18011712c`
- `0x1801179cc`
- `0x180146090`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180116f4f`
- `KERNEL32!GetLastError` at `0x180116f4f`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180116f3e`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180116f3e`

## pseudocode

```c
__int64 __fastcall CIOPort::ProcessItems(__int64 a1, struct CThreadState *a2)
{
  struct TpStateVerifier *v4; // r8
  DWORD dwMilliseconds; // edx
  __int64 v6; // rcx
  unsigned int v7; // eax
  signed int v8; // eax
  __int64 v9; // rcx
  BOOL QueuedCompletionStatus; // ebx
  DWORD v11; // esi
  struct TpStateVerifier *v12; // r8
  LPOVERLAPPED v13; // rdx
  int v14; // ebx
  unsigned int v15; // eax
  unsigned int v16; // ebx
  void *v17; // rbx
  int v18; // eax
  DWORD NumberOfBytesTransferred; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int64 CompletionKey; // [rsp+68h] [rbp+10h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+70h] [rbp+18h] BYREF
  void *v23; // [rsp+78h] [rbp+20h] BYREF

  if ( CThreadManager::GetThreadState(*(CThreadManager **)(a1 + 8)) != a2 )
    MsoShipAssertTagProc(507553820);
  do
  {
    while ( 1 )
    {
      while ( 1 )
      {
        dwMilliseconds = -1;
        v6 = *(_QWORD *)(a1 + 16);
        v7 = ((unsigned int)v6 >> 19) & 0x7FF;
        if ( (int)v6 < 0 && v7 )
          --v7;
        v8 = v7 - (((unsigned int)v6 >> 12) & 0x7F) - 4;
        if ( v8 > 0 )
        {
          if ( (unsigned int)v8 > 4 && CIOPort::FThreadExpired((CThreadManager **)a1, a2, v4) )
            return 0;
          dwMilliseconds = 6000;
        }
        NumberOfBytesTransferred = 0;
        CompletionKey = 0;
        Overlapped = 0;
        QueuedCompletionStatus = GetQueuedCompletionStatus(
                                   *(HANDLE *)(a1 + 128),
                                   &NumberOfBytesTransferred,
                                   &CompletionKey,
                                   &Overlapped,
                                   dwMilliseconds);
        v11 = QueuedCompletionStatus ? 0 : GetLastError();
        v12 = (struct TpStateVerifier *)CompletionKey;
        LOBYTE(v9) = CompletionKey >= 4;
        v13 = Overlapped;
        if ( QueuedCompletionStatus || Overlapped )
          break;
        if ( (Microsoft_Office_ThreadpoolEnableBits & 0x20) != 0 )
        {
          McTemplateU0qq_EventWriteTransfer(v9, TPPortPacketReceivedFailure, CompletionKey, NumberOfBytesTransferred);
          v12 = (struct TpStateVerifier *)CompletionKey;
        }
        if ( v12 )
          MsoShipAssertTagProc(507553813);
        if ( v11 != 258 )
          MsoShipAssertTagProc(507553812);
        if ( CIOPort::FThreadExpired((CThreadManager **)a1, a2, v12) )
          return 0;
      }
      if ( CompletionKey < 4 )
        break;
      if ( !Overlapped )
      {
        MsoShipAssertTagProc(507553809);
        v12 = (struct TpStateVerifier *)CompletionKey;
        v13 = Overlapped;
      }
      if ( (Microsoft_Office_ThreadpoolEnableBits & 0x10) != 0 )
      {
        McTemplateU0qq_EventWriteTransfer(v9, TPPortPacketReceivedIO, v12, NumberOfBytesTransferred);
        v12 = (struct TpStateVerifier *)CompletionKey;
        v13 = Overlapped;
      }
      v14 = CIOPort::ProcessPortCallback(a1, v13, v12, NumberOfBytesTransferred, v11, a2);
      if ( CThreadManager::GetThreadState(*(CThreadManager **)(a1 + 8)) != a2 )
        MsoShipAssertTagProc(507553805);
      if ( v14 != 1 )
      {
        if ( !v14 )
          return 0;
        while ( 1 )
        {
LABEL_37:
          v23 = 0;
          CTpQueue::FPop((CTpQueue *)(a1 + 144), &v23);
          v17 = v23;
          if ( v23 )
          {
            (*(void (__fastcall **)(void *, struct CThreadState *))(*(_QWORD *)v23 + 240LL))(v23, a2);
            if ( CThreadManager::GetThreadState(*(CThreadManager **)(a1 + 8)) != a2 )
              MsoShipAssertTagProc(507553792);
            (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
          }
          v18 = CIOPort::AfterCallback(a1, a2);
          if ( v18 == 1 )
            break;
          if ( !v18 )
            return 0;
        }
      }
    }
    if ( (Microsoft_Office_ThreadpoolEnableBits & 0x10) != 0 )
    {
      McTemplateU0qq_EventWriteTransfer(v9, TPPortPacketReceivedWorker, CompletionKey, NumberOfBytesTransferred);
      v12 = (struct TpStateVerifier *)CompletionKey;
      v13 = Overlapped;
    }
    v15 = CIOPort::BeforeProcessingWorker(a1, v13, v12, a2);
    v16 = v15;
  }
  while ( v15 == 1 );
  if ( v15 == 2 )
    goto LABEL_37;
  if ( v15 && v15 != 3 )
    MsoShipAssertTagProc(507553798);
  return v16;
}

```

## disassembly

```asm
0x180116ea0  push    rbx
0x180116ea2  push    rbp
0x180116ea3  push    rsi
0x180116ea4  push    rdi
0x180116ea5  push    r14
0x180116ea7  sub     rsp, 30h
0x180116eab  mov     rbp, rdx
0x180116eae  mov     rdi, rcx
0x180116eb1  mov     rcx, [rcx+8]; this
0x180116eb5  call    ?GetThreadState@CThreadManager@@QEBAPEAUCThreadState@@XZ; CThreadManager::GetThreadState(void)
0x180116eba  cmp     rax, rbp
0x180116ebd  jz      short loc_180116EC9
0x180116ebf  mov     ecx, 1E40A81Ch
0x180116ec4  call    MsoShipAssertTagProc
0x180116ec9  xor     r14d, r14d
0x180116ecc  mov     edx, 0FFFFFFFFh
0x180116ed1  mov     rcx, [rdi+10h]
0x180116ed5  mov     eax, ecx
0x180116ed7  shr     eax, 13h
0x180116eda  and     eax, 7FFh
0x180116edf  test    ecx, ecx
0x180116ee1  jns     short loc_180116EE9
0x180116ee3  test    eax, eax
0x180116ee5  jz      short loc_180116EE9
0x180116ee7  dec     eax
0x180116ee9  shr     ecx, 0Ch
0x180116eec  and     ecx, 7Fh
0x180116eef  sub     eax, ecx
0x180116ef1  sub     eax, 4
0x180116ef4  test    eax, eax
0x180116ef6  jle     short loc_180116F15
0x180116ef8  cmp     eax, 4
0x180116efb  jbe     short loc_180116F10
0x180116efd  mov     rdx, rbp; struct CThreadState *
0x180116f00  mov     rcx, rdi; this
0x180116f03  call    ?FThreadExpired@CIOPort@@IEAA_NPEAUCThreadState@@PEAVTpStateVerifier@@@Z; CIOPort::FThreadExpired(CThreadState *,TpStateVerifier *)
0x180116f08  test    al, al
0x180116f0a  jnz     loc_180117106
0x180116f10  mov     edx, 1770h
0x180116f15  mov     [rsp+58h+NumberOfBytesTransferred], r14d
0x180116f1a  mov     [rsp+58h+CompletionKey], r14
0x180116f1f  mov     [rsp+58h+Overlapped], r14
0x180116f24  mov     [rsp+58h+dwMilliseconds], edx; dwMilliseconds
0x180116f28  lea     r9, [rsp+58h+Overlapped]; lpOverlapped
0x180116f2d  lea     r8, [rsp+58h+CompletionKey]; lpCompletionKey
0x180116f32  lea     rdx, [rsp+58h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180116f37  mov     rcx, [rdi+80h]; CompletionPort
0x180116f3e  call    cs:__imp_GetQueuedCompletionStatus
0x180116f44  mov     ebx, eax
0x180116f46  test    eax, eax
0x180116f48  jz      short loc_180116F4F
0x180116f4a  mov     esi, r14d
0x180116f4d  jmp     short loc_180116F57
0x180116f4f  call    cs:__imp_GetLastError
0x180116f55  mov     esi, eax
0x180116f57  mov     r8, [rsp+58h+CompletionKey]
0x180116f5c  cmp     r8, 4
0x180116f60  setnb   cl
0x180116f63  mov     rdx, [rsp+58h+Overlapped]
0x180116f68  test    ebx, ebx
0x180116f6a  jnz     short loc_180116FC9
0x180116f6c  test    rdx, rdx
0x180116f6f  jnz     short loc_180116FC9
0x180116f71  test    cs:Microsoft_Office_ThreadpoolEnableBits, 20h
0x180116f78  jz      short loc_180116F90
0x180116f7a  mov     r9d, [rsp+58h+NumberOfBytesTransferred]
0x180116f7f  lea     rdx, TPPortPacketReceivedFailure
0x180116f86  call    McTemplateU0qq_EventWriteTransfer
0x180116f8b  mov     r8, [rsp+58h+CompletionKey]
0x180116f90  test    r8, r8
0x180116f93  jz      short loc_180116F9F
0x180116f95  mov     ecx, 1E40A815h
0x180116f9a  call    MsoShipAssertTagProc
0x180116f9f  cmp     esi, 102h
0x180116fa5  jz      short loc_180116FB1
0x180116fa7  mov     ecx, 1E40A814h
0x180116fac  call    MsoShipAssertTagProc
0x180116fb1  mov     rdx, rbp; struct CThreadState *
0x180116fb4  mov     rcx, rdi; this
0x180116fb7  call    ?FThreadExpired@CIOPort@@IEAA_NPEAUCThreadState@@PEAVTpStateVerifier@@@Z; CIOPort::FThreadExpired(CThreadState *,TpStateVerifier *)
0x180116fbc  test    al, al
0x180116fbe  jz      loc_180116ECC
0x180116fc4  jmp     loc_180117106
0x180116fc9  test    cl, cl
0x180116fcb  jz      loc_180117051
0x180116fd1  test    rdx, rdx
0x180116fd4  jnz     short loc_180116FEA
0x180116fd6  mov     ecx, 1E40A811h
0x180116fdb  call    MsoShipAssertTagProc
0x180116fe0  mov     r8, [rsp+58h+CompletionKey]
0x180116fe5  mov     rdx, [rsp+58h+Overlapped]
0x180116fea  test    cs:Microsoft_Office_ThreadpoolEnableBits, 10h
0x180116ff1  jz      short loc_18011700E
0x180116ff3  mov     r9d, [rsp+58h+NumberOfBytesTransferred]
0x180116ff8  lea     rdx, TPPortPacketReceivedIO
0x180116fff  call    McTemplateU0qq_EventWriteTransfer
0x180117004  mov     r8, [rsp+58h+CompletionKey]
0x180117009  mov     rdx, [rsp+58h+Overlapped]
0x18011700e  mov     [rsp+58h+var_30], rbp
0x180117013  mov     [rsp+58h+dwMilliseconds], esi
0x180117017  mov     r9d, [rsp+58h+NumberOfBytesTransferred]
0x18011701c  mov     rcx, rdi
0x18011701f  call    ?ProcessPortCallback@CIOPort@@IEAA?AW4eThreadNextStep@@PEAU_OVERLAPPED@@_KKKPEAUCThreadState@@@Z; CIOPort::ProcessPortCallback(_OVERLAPPED *,unsigned __int64,ulong,ulong,CThreadState *)
0x180117024  mov     ebx, eax
0x180117026  mov     rcx, [rdi+8]; this
0x18011702a  call    ?GetThreadState@CThreadManager@@QEBAPEAUCThreadState@@XZ; CThreadManager::GetThreadState(void)
0x18011702f  cmp     rax, rbp
0x180117032  jz      short loc_18011703E
0x180117034  mov     ecx, 1E40A80Dh
0x180117039  call    MsoShipAssertTagProc
0x18011703e  cmp     ebx, 1
0x180117041  jz      loc_180116ECC
0x180117047  test    ebx, ebx
0x180117049  jz      loc_180117106
0x18011704f  jmp     short loc_180117090
0x180117051  test    cs:Microsoft_Office_ThreadpoolEnableBits, 10h
0x180117058  jz      short loc_180117075
0x18011705a  mov     r9d, [rsp+58h+NumberOfBytesTransferred]
0x18011705f  lea     rdx, TPPortPacketReceivedWorker
0x180117066  call    McTemplateU0qq_EventWriteTransfer
0x18011706b  mov     r8, [rsp+58h+CompletionKey]
0x180117070  mov     rdx, [rsp+58h+Overlapped]
0x180117075  mov     r9, rbp
0x180117078  mov     rcx, rdi
0x18011707b  call    ?BeforeProcessingWorker@CIOPort@@IEAA?AW4eThreadNextStep@@PEAU_OVERLAPPED@@_KPEAUCThreadState@@@Z; CIOPort::BeforeProcessingWorker(_OVERLAPPED *,unsigned __int64,CThreadState *)
0x180117080  mov     ebx, eax
0x180117082  cmp     eax, 1
0x180117085  jz      loc_180116ECC
0x18011708b  cmp     eax, 2
0x18011708e  jnz     short loc_18011710A
0x180117090  mov     [rsp+58h+arg_18], r14
0x180117095  lea     rdx, [rsp+58h+arg_18]; void **
0x18011709a  lea     rcx, [rdi+90h]; this
0x1801170a1  call    ?FPop@CTpQueue@@QEAA_NPEAPEAX@Z; CTpQueue::FPop(void * *)
0x1801170a6  mov     rbx, [rsp+58h+arg_18]
0x1801170ab  test    rbx, rbx
0x1801170ae  jz      short loc_1801170EE
0x1801170b0  mov     rax, [rbx]
0x1801170b3  mov     rdx, rbp
0x1801170b6  mov     rcx, rbx
0x1801170b9  mov     rax, [rax+0F0h]
0x1801170c0  call    cs:__guard_dispatch_icall_fptr
0x1801170c6  mov     rcx, [rdi+8]; this
0x1801170ca  call    ?GetThreadState@CThreadManager@@QEBAPEAUCThreadState@@XZ; CThreadManager::GetThreadState(void)
0x1801170cf  cmp     rax, rbp
0x1801170d2  jz      short loc_1801170DE
0x1801170d4  mov     ecx, 1E40A800h
0x1801170d9  call    MsoShipAssertTagProc
0x1801170de  mov     rax, [rbx]
0x1801170e1  mov     rcx, rbx
0x1801170e4  mov     rax, [rax+10h]
0x1801170e8  call    cs:__guard_dispatch_icall_fptr
0x1801170ee  mov     rdx, rbp
0x1801170f1  mov     rcx, rdi
0x1801170f4  call    ?AfterCallback@CIOPort@@IEAA?AW4eThreadNextStep@@PEAUCThreadState@@@Z; CIOPort::AfterCallback(CThreadState *)
0x1801170f9  cmp     eax, 1
0x1801170fc  jz      loc_180116ECC
0x180117102  test    eax, eax
0x180117104  jnz     short loc_180117090
0x180117106  xor     eax, eax
0x180117108  jmp     short loc_18011711F
0x18011710a  test    ebx, ebx
0x18011710c  jz      short loc_18011711D
0x18011710e  cmp     ebx, 3
0x180117111  jz      short loc_18011711D
0x180117113  mov     ecx, 1E40A806h
0x180117118  call    MsoShipAssertTagProc
0x18011711d  mov     eax, ebx
0x18011711f  add     rsp, 30h
0x180117123  pop     r14
0x180117125  pop     rdi
0x180117126  pop     rsi
0x180117127  pop     rbp
0x180117128  pop     rbx
0x180117129  retn
```
