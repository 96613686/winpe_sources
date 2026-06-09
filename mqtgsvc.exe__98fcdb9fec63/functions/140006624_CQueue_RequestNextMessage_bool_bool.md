# CQueue::RequestNextMessage(bool,bool)

- ea: `0x140006624`
- end: `0x140006957`
- name: `?RequestNextMessage@CQueue@@QEAAJ_N0@Z`
- size: `819`
- prototype: `__int64 __fastcall(CQueue *this, char, char)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400062c8`
- `0x140009b68`
- `0x140009f80`

## callees

- `0x140002e34`
- `0x140003720`
- `0x140003d08`
- `0x140004538`
- `0x140006624`
- `0x140007554`
- `0x140007594`
- `0x14000761c`
- `0x14000ed18`
- `0x14001c9a0`

## import_xrefs

- `KERNEL32!Sleep` at `0x14000686c`
- `KERNEL32!Sleep` at `0x14000686c`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140006885`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140006885`
- `KERNEL32!GetLastError` at `0x1400068ad`
- `KERNEL32!GetLastError` at `0x1400068ad`
- `mqrt!MQReceiveMessage` at `0x1400067c6`
- `mqrt!MQReceiveMessage` at `0x1400067c6`
- `mqrt!MQCreateCursor` at `0x140006674`
- `mqrt!MQCreateCursor` at `0x140006674`

## pseudocode

```c
__int64 __fastcall CQueue::RequestNextMessage(CQueue *this, char a2, char a3)
{
  HRESULT v5; // ebx
  DWORD v6; // r14d
  void *v7; // rcx
  CReadWriteLock *v8; // rax
  void *v9; // rcx
  CReadWriteLock *v12; // [rsp+98h] [rbp+20h] BYREF

  v5 = 0;
  v6 = -2147483647;
  if ( a2 == 1 )
  {
    v12 = (CQueue *)((char *)this + 176);
    CReadWriteLock::LockRead((CQueue *)((char *)this + 176));
    v5 = -1072820736;
    v7 = (void *)*((_QWORD *)this + 3);
    if ( v7 )
      v5 = MQCreateCursor(v7, (PHANDLE)this + 6);
    CSR::~CSR(&v12);
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        ((void (__usercall *)(TRACEHANDLE@<rcx>, char))WPP_SF_Sd)(*((_QWORD *)WPP_GLOBAL_Control + 2), v5);
    }
    else
    {
      v6 = 0x80000000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Sq(*((_QWORD *)WPP_GLOBAL_Control + 2), *((_QWORD *)this + 6));
    }
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( v5 >= 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)this + 2);
      if ( *((_QWORD *)this + 18) )
      {
        if ( !a3 )
          v6 = 0x80000000;
      }
      else
      {
        v8 = (CReadWriteLock *)MmAllocate(0x628u);
        v12 = v8;
        if ( v8 )
          v8 = CMsgProperties::CMsgProperties(v8, *((_DWORD *)this + 34));
        *((_QWORD *)this + 18) = v8;
      }
      while ( 1 )
      {
        while ( 1 )
        {
          v12 = (CQueue *)((char *)this + 176);
          CReadWriteLock::LockRead((CQueue *)((char *)this + 176));
          v5 = -1072820736;
          v9 = (void *)*((_QWORD *)this + 3);
          if ( v9 )
            v5 = MQReceiveMessage(
                   v9,
                   0xFFFFFFFF,
                   v6,
                   *((MQMSGPROPS **)this + 18),
                   (LPOVERLAPPED)this + 2,
                   0,
                   *((HANDLE *)this + 6),
                   0);
          CSR::~CSR(&v12);
          if ( v5 == -1072824309 )
            goto LABEL_38;
          if ( v5 != -1072824294 )
            break;
          CMsgProperties::ReAllocMsgBody(*((CMsgProperties **)this + 18));
          v6 = 0x80000000;
        }
        if ( v5 != -1072824291 )
          break;
        v6 = -2147483647;
      }
      if ( v5 == -1072824234 || v5 == -1072824230 )
      {
LABEL_38:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          ((void (__usercall *)(TRACEHANDLE@<rcx>, char))WPP_SF_Sd)(*((_QWORD *)WPP_GLOBAL_Control + 2), v5);
        goto LABEL_41;
      }
      if ( !v5 || v5 == 1074659334 )
        return 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        ((void (__usercall *)(TRACEHANDLE@<rcx>, char))WPP_SF_Sd)(*((_QWORD *)WPP_GLOBAL_Control + 2), v5);
      Sleep(0x7D0u);
      if ( !PostQueuedCompletionStatus(**((HANDLE **)this + 7), 0, 0xBBBBBBBB, (LPOVERLAPPED)this + 2) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          GetLastError();
          ((void (__fastcall *)(_QWORD, __int64, const GUID *))WPP_SF_d)(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            &WPP_81c52ba4630d30a3481546cc16d5e3ae_Traceguids);
        }
LABEL_41:
        CReference::Release(this);
      }
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_81c52ba4630d30a3481546cc16d5e3ae_Traceguids);
      Sleep(0x7D0u);
      if ( !PostQueuedCompletionStatus(**((HANDLE **)this + 7), 0, 0xBBBBBBBB, (LPOVERLAPPED)this + 2) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          GetLastError();
          ((void (__fastcall *)(_QWORD, __int64, const GUID *))WPP_SF_d)(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            &WPP_81c52ba4630d30a3481546cc16d5e3ae_Traceguids);
        }
        CReference::Release(this);
      }
      v5 = -1072824281;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_14000693E);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140006624  mov     rax, rsp
0x140006627  mov     [rax+8], rcx
0x14000662b  push    rbx
0x14000662c  push    rsi
0x14000662d  push    rdi
0x14000662e  push    r12
0x140006630  push    r13
0x140006632  push    r14
0x140006634  push    r15
0x140006636  sub     rsp, 40h
0x14000663a  mov     r13b, r8b
0x14000663d  mov     rdi, rcx
0x140006640  xor     ebx, ebx
0x140006642  mov     r14d, 80000001h
0x140006648  cmp     dl, 1
0x14000664b  jnz     loc_140006719
0x140006651  add     rcx, 0B0h; this
0x140006658  mov     [rax+20h], rcx
0x14000665c  call    ?LockRead@CReadWriteLock@@QEAAXXZ; CReadWriteLock::LockRead(void)
0x140006661  nop
0x140006662  mov     ebx, 0C00E0E00h
0x140006667  mov     rcx, [rdi+18h]; hQueue
0x14000666b  test    rcx, rcx
0x14000666e  jz      short loc_14000667C
0x140006670  lea     rdx, [rdi+30h]; phCursor
0x140006674  call    cs:__imp_MQCreateCursor
0x14000667a  mov     ebx, eax
0x14000667c  lea     rcx, [rsp+78h+arg_18]; this
0x140006684  call    ??1CSR@@QEAA@XZ; CSR::~CSR(void)
0x140006689  test    ebx, ebx
0x14000668b  js      short loc_1400066D4
0x14000668d  mov     r12d, 80000000h
0x140006693  mov     r14d, r12d
0x140006696  lea     r15, WPP_GLOBAL_Control
0x14000669d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400066a4  cmp     rcx, r15
0x1400066a7  jz      short loc_140006726
0x1400066a9  test    byte ptr [rcx+1Ch], 4
0x1400066ad  jz      short loc_140006726
0x1400066af  mov     rdx, [rdi+30h]
0x1400066b3  mov     rax, [rdi+60h]
0x1400066b7  test    rax, rax
0x1400066ba  jz      short loc_1400066C1
0x1400066bc  mov     r9, [rax]
0x1400066bf  jmp     short loc_1400066C4
0x1400066c1  xor     r9d, r9d
0x1400066c4  mov     [rsp+78h+lpOverlapped], rdx; char
0x1400066c9  mov     rcx, [rcx+10h]; LoggerHandle
0x1400066cd  call    WPP_SF_Sq
0x1400066d2  jmp     short loc_140006726
0x1400066d4  lea     r15, WPP_GLOBAL_Control
0x1400066db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400066e2  cmp     rcx, r15
0x1400066e5  jz      short loc_140006720
0x1400066e7  test    byte ptr [rcx+1Ch], 1
0x1400066eb  jz      short loc_140006720
0x1400066ed  mov     rax, [rdi+60h]
0x1400066f1  test    rax, rax
0x1400066f4  jz      short loc_1400066FB
0x1400066f6  mov     r9, [rax]
0x1400066f9  jmp     short loc_1400066FE
0x1400066fb  xor     r9d, r9d
0x1400066fe  mov     edx, 0Ch
0x140006703  mov     dword ptr [rsp+78h+lpOverlapped], ebx; char
0x140006707  lea     r8, WPP_81c52ba4630d30a3481546cc16d5e3ae_Traceguids
0x14000670e  mov     rcx, [rcx+10h]; LoggerHandle
0x140006712  call    WPP_SF_Sd
0x140006717  jmp     short loc_140006720
0x140006719  lea     r15, WPP_GLOBAL_Control
0x140006720  mov     r12d, 80000000h
0x140006726  test    ebx, ebx
0x140006728  js      loc_14000693C
0x14000672e  lock inc dword ptr [rdi+8]
0x140006732  cmp     qword ptr [rdi+90h], 0
0x14000673a  jnz     short loc_14000676B
0x14000673c  mov     ecx, 628h; unsigned __int64
0x140006741  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x140006746  mov     [rsp+78h+arg_18], rax
0x14000674e  test    rax, rax
0x140006751  jz      short loc_140006762
0x140006753  mov     edx, [rdi+88h]; unsigned int
0x140006759  mov     rcx, rax; this
0x14000675c  call    ??0CMsgProperties@@QEAA@K@Z; CMsgProperties::CMsgProperties(ulong)
0x140006761  nop
0x140006762  mov     [rdi+90h], rax
0x140006769  jmp     short loc_140006772
0x14000676b  test    r13b, r13b
0x14000676e  cmovz   r14d, r12d
0x140006772  lea     rcx, [rdi+0B0h]; this
0x140006779  mov     [rsp+78h+arg_18], rcx
0x140006781  call    ?LockRead@CReadWriteLock@@QEAAXXZ; CReadWriteLock::LockRead(void)
0x140006786  nop
0x140006787  mov     ebx, 0C00E0E00h
0x14000678c  mov     rcx, [rdi+18h]; hSource
0x140006790  test    rcx, rcx
0x140006793  jz      short loc_1400067CE
0x140006795  lea     rdx, [rdi+40h]
0x140006799  mov     [rsp+78h+pTransaction], 0; pTransaction
0x1400067a2  mov     rax, [rdi+30h]
0x1400067a6  mov     [rsp+78h+hCursor], rax; hCursor
0x1400067ab  mov     [rsp+78h+fnReceiveCallback], 0; fnReceiveCallback
0x1400067b4  mov     [rsp+78h+lpOverlapped], rdx; lpOverlapped
0x1400067b9  mov     r9, [rdi+90h]; pMessageProps
0x1400067c0  mov     r8d, r14d; dwAction
0x1400067c3  or      edx, 0FFFFFFFFh; dwTimeout
0x1400067c6  call    cs:__imp_MQReceiveMessage
0x1400067cc  mov     ebx, eax
0x1400067ce  lea     rcx, [rsp+78h+arg_18]; this
0x1400067d6  call    ??1CSR@@QEAA@XZ; CSR::~CSR(void)
0x1400067db  cmp     ebx, 0C00E000Bh
0x1400067e1  jz      loc_1400068F7
0x1400067e7  cmp     ebx, 0C00E001Ah
0x1400067ed  jz      loc_1400068E3
0x1400067f3  cmp     ebx, 0C00E001Dh
0x1400067f9  jz      loc_1400068D8
0x1400067ff  cmp     ebx, 0C00E0056h
0x140006805  jz      loc_1400068F7
0x14000680b  cmp     ebx, 0C00E005Ah
0x140006811  jz      loc_1400068F7
0x140006817  test    ebx, ebx
0x140006819  jz      loc_1400068D4
0x14000681f  cmp     ebx, 400E0006h
0x140006825  jz      loc_1400068D4
0x14000682b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006832  cmp     rcx, r15
0x140006835  jz      short loc_140006867
0x140006837  test    byte ptr [rcx+1Ch], 1
0x14000683b  jz      short loc_140006867
0x14000683d  mov     rax, [rdi+60h]
0x140006841  test    rax, rax
0x140006844  jz      short loc_14000684B
0x140006846  mov     r9, [rax]
0x140006849  jmp     short loc_14000684E
0x14000684b  xor     r9d, r9d
0x14000684e  mov     edx, 0Eh
0x140006853  mov     dword ptr [rsp+78h+lpOverlapped], ebx; char
0x140006857  lea     r8, WPP_81c52ba4630d30a3481546cc16d5e3ae_Traceguids
0x14000685e  mov     rcx, [rcx+10h]; LoggerHandle
0x140006862  call    WPP_SF_Sd
0x140006867  mov     ecx, 7D0h; dwMilliseconds
0x14000686c  call    cs:__imp_Sleep
0x140006872  lea     r9, [rdi+40h]; lpOverlapped
0x140006876  mov     rcx, [rdi+38h]
0x14000687a  xor     edx, edx; dwNumberOfBytesTransferred
0x14000687c  mov     r8d, 0BBBBBBBBh; dwCompletionKey
0x140006882  mov     rcx, [rcx]; CompletionPort
0x140006885  call    cs:__imp_PostQueuedCompletionStatus
0x14000688b  test    eax, eax
0x14000688d  jnz     loc_14000693C
0x140006893  mov     rax, cs:WPP_GLOBAL_Control
0x14000689a  cmp     rax, r15
0x14000689d  jz      loc_140006933
0x1400068a3  test    byte ptr [rax+1Ch], 1
0x1400068a7  jz      loc_140006933
0x1400068ad  call    cs:__imp_GetLastError
0x1400068b3  mov     edx, 0Fh
0x1400068b8  mov     r9d, eax
0x1400068bb  lea     r8, WPP_81c52ba4630d30a3481546cc16d5e3ae_Traceguids
0x1400068c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400068c9  mov     rcx, [rcx+10h]
0x1400068cd  call    WPP_SF_d
0x1400068d2  jmp     short loc_140006933
0x1400068d4  xor     ebx, ebx
0x1400068d6  jmp     short loc_14000693C
0x1400068d8  mov     r14d, 80000001h
0x1400068de  jmp     loc_140006772
0x1400068e3  mov     rcx, [rdi+90h]; this
0x1400068ea  call    ?ReAllocMsgBody@CMsgProperties@@QEAA_NXZ; CMsgProperties::ReAllocMsgBody(void)
0x1400068ef  mov     r14d, r12d
0x1400068f2  jmp     loc_140006772
0x1400068f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400068fe  cmp     rcx, r15
0x140006901  jz      short loc_140006933
0x140006903  test    byte ptr [rcx+1Ch], 1
0x140006907  jz      short loc_140006933
0x140006909  mov     rax, [rdi+60h]
0x14000690d  test    rax, rax
0x140006910  jz      short loc_140006917
0x140006912  mov     r9, [rax]
0x140006915  jmp     short loc_14000691A
0x140006917  xor     r9d, r9d
0x14000691a  mov     edx, 0Dh
0x14000691f  mov     dword ptr [rsp+78h+lpOverlapped], ebx; char
0x140006923  lea     r8, WPP_81c52ba4630d30a3481546cc16d5e3ae_Traceguids
0x14000692a  mov     rcx, [rcx+10h]; LoggerHandle
0x14000692e  call    WPP_SF_Sd
0x140006933  mov     rcx, rdi; this
0x140006936  call    ?Release@CReference@@QEBAXXZ; CReference::Release(void)
0x14000693b  nop
0x14000693c  jmp     short loc_140006945
0x14000693e  mov     ebx, [rsp+78h+arg_8]
0x140006945  mov     eax, ebx
0x140006947  add     rsp, 40h
0x14000694b  pop     r15
0x14000694d  pop     r14
0x14000694f  pop     r13
0x140006951  pop     r12
0x140006953  pop     rdi
0x140006954  pop     rsi
0x140006955  pop     rbx
0x140006956  retn
```
