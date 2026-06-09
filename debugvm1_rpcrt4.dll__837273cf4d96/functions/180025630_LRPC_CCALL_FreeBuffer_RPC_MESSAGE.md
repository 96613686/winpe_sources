# LRPC_CCALL::FreeBuffer(_RPC_MESSAGE *)

- ea: `0x180025630`
- end: `0x180025a71`
- name: `?FreeBuffer@LRPC_CCALL@@UEAAXPEAU_RPC_MESSAGE@@@Z`
- size: `1089`
- prototype: `void __fastcall(LRPC_CCALL *__hidden this, struct _RPC_MESSAGE *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180023ca0`
- `0x180025630`
- `0x180025c00`
- `0x180025c90`
- `0x180026ca0`
- `0x180026d10`
- `0x180027220`
- `0x1800274e0`
- `0x18002b7c0`
- `0x18004b70c`
- `0x1800944d4`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `KERNELBASE!Sleep` at `0x180025915`
- `KERNELBASE!Sleep` at `0x180025915`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800259c5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800259c5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180025998`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180025998`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800259ab`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800259ab`

## pseudocode

```c
void __fastcall LRPC_CCALL::FreeBuffer(LRPC_CCALL *this, struct _RPC_MESSAGE *a2)
{
  unsigned __int64 ReservedForNtRpc; // rbx
  signed __int64 v5; // rbp
  signed __int64 v6; // rdi
  __int64 v7; // rax
  unsigned int v8; // edx
  BCACHE *v9; // rcx
  unsigned int v10; // ebx
  struct _PORT_MESSAGE *v11; // rdi
  unsigned int v12; // r10d
  unsigned __int64 HeaderSize; // r9
  int v14; // r10d
  int v15; // r11d
  int v16; // r11d
  unsigned __int64 v17; // rax
  unsigned int v18; // eax
  void *v19; // rdx
  void *v20; // rdx
  void *v21; // rdx
  void *v22; // rdx
  union _LARGE_INTEGER *v23; // [rsp+38h] [rbp-70h]
  int v24; // [rsp+40h] [rbp-68h] BYREF
  int v25; // [rsp+44h] [rbp-64h]
  _QWORD v26[7]; // [rsp+48h] [rbp-60h]

  if ( !(*(unsigned int (__fastcall **)(LRPC_CCALL *))(*(_QWORD *)this + 288LL))(this)
    || !*(_DWORD *)(*((_QWORD *)this + 74) + 8LL) )
  {
    if ( (*((_DWORD *)this + 72) & 0x800) != 0
      && (!(*(unsigned int (__fastcall **)(LRPC_CCALL *))(*(_QWORD *)this + 288LL))(this)
       || !*(_DWORD *)(*((_QWORD *)this + 74) + 8LL)) )
    {
      ReservedForNtRpc = (unsigned __int64)NtCurrentTeb()->ReservedForNtRpc;
      if ( ReservedForNtRpc )
      {
        ReservedForNtRpc ^= 0xABABABABDEDEDEDEuLL;
        if ( *(HANDLE *)(ReservedForNtRpc + 16) != NtCurrentTeb()->ClientId.UniqueThread )
          __fastfail(0x1Eu);
      }
      v5 = *((_QWORD *)this + 104);
      do
      {
        v6 = *(_QWORD *)(ReservedForNtRpc + 72);
        if ( (LRPC_CCALL *)(v6 & 0xFFFFFFFFFFFFFFFCuLL) != this )
        {
          RpcpReportFatalError(21, this);
          __debugbreak();
        }
        while ( (*(_QWORD *)(ReservedForNtRpc + 72) & 1) != 0 )
          Sleep(0xAu);
      }
      while ( v6 != _InterlockedCompareExchange64((volatile signed __int64 *)(ReservedForNtRpc + 72), v5, v6) );
      v7 = *((_QWORD *)this + 105);
      *((_QWORD *)this + 104) = 0;
      if ( v7 )
      {
        _InterlockedOr((volatile signed __int32 *)this + 72, 0x10000u);
        if ( *((_QWORD *)this + 105) )
        {
          ResetEvent(*(HANDLE *)(ReservedForNtRpc + 24));
          DeleteTimerQueueTimer(0, *((HANDLE *)this + 105), *(HANDLE *)(ReservedForNtRpc + 24));
          _InterlockedAnd((volatile signed __int32 *)this + 72, 0xFFFEFFFF);
          WaitForSingleObject(*(HANDLE *)(ReservedForNtRpc + 24), 0xFFFFFFFF);
        }
        else
        {
          _InterlockedAnd((volatile signed __int32 *)this + 72, 0xFFFEFFFF);
        }
      }
    }
    v8 = 3;
    if ( *((int *)this + 67) < 3 )
      v8 = 0;
    LRPC_SYSTEM_HANDLE_DATA::CleanupSystemHandles((LRPC_CCALL *)((char *)this + 616), v8);
    if ( *((int *)this + 67) < 3 )
    {
      if ( (*((_DWORD *)this + 72) & 2) != 0 && *((int *)this + 66) < 10 )
        LRPC_BASE_CCALL::CancelCall(this);
      if ( *((_DWORD *)this + 67) == 2 )
      {
        v21 = (void *)*((_QWORD *)this + 63);
        if ( v21 )
          BCACHE::Free(v9, v21);
        *((_QWORD *)this + 63) = 0;
        if ( *((_QWORD *)this + 64) )
        {
          if ( (*((_DWORD *)this + 72) & 0x10) != 0 )
          {
            v22 = (void *)*((_QWORD *)this + 64);
            if ( v22 )
              BCACHE::Free(v9, v22);
            *((_QWORD *)this + 64) = 0;
            _InterlockedAnd((volatile signed __int32 *)this + 72, 0xFFFFFFEF);
          }
          else
          {
            LRPC_BASE_CCALL::FreeAlpcSectionAndView(this, 1);
          }
        }
      }
      goto LABEL_32;
    }
    if ( !*((_QWORD *)this + 63) )
    {
LABEL_32:
      (*(void (__fastcall **)(LRPC_CCALL *))(*(_QWORD *)this + 32LL))(this);
      return;
    }
    v10 = 0;
    if ( *((_QWORD *)this + 68) )
    {
      if ( (*((_DWORD *)this + 72) & 0x4000) != 0 )
      {
        v20 = (void *)*((_QWORD *)this + 68);
        if ( v20 )
        {
          BCACHE::Free(v9, v20);
          *((_QWORD *)this + 68) = 0;
          goto LABEL_16;
        }
      }
      else
      {
        v10 = 0x40000000;
      }
      *((_QWORD *)this + 68) = 0;
    }
LABEL_16:
    if ( *((_DWORD *)this + 152) )
    {
      v10 |= 0x10000000u;
      *((_DWORD *)this + 152) = 0;
    }
    if ( v10 )
    {
      v11 = (struct _PORT_MESSAGE *)*((_QWORD *)this + 69);
      v12 = v10 & 0xEFFFFFFF;
      if ( (v10 & 0x10000000) == 0 )
        v12 = v10;
      HeaderSize = RpcpAlpcpGetHeaderSize(v12);
      v16 = v15 & 0x40000000;
      v17 = 40;
      if ( !v16 )
        v17 = 8;
      if ( HeaderSize > v17 )
      {
        v14 = v24;
      }
      else
      {
        v24 = v14;
        v25 = 0;
      }
      if ( v16 )
      {
        v18 = RpcpAlpcpGetHeaderSize(v14 & 0x80000000);
        *(int *)((char *)&v24 + v18) = 0x10000;
        *(_QWORD *)((char *)v26 + v18) = 0;
        *(_QWORD *)((char *)&v26[1] + v18) = 0;
        *(_QWORD *)((char *)&v26[2] + v18) = 0;
        v25 |= 0x40000000u;
      }
      LRPC_CASSOCIATION::AlpcSendWaitReceivePort(
        *((LRPC_CASSOCIATION **)this + 35),
        0,
        v11,
        (struct _ALPC_MESSAGE_ATTRIBUTES *)&v24,
        0,
        0,
        0,
        v23);
      if ( dword_1800F9624 )
        LogEventToEtw(0x4Cu, 0x40u, (__int64)v11, v10, 0);
    }
    v19 = (void *)*((_QWORD *)this + 69);
    if ( v19 )
      BCACHE::Free(v9, v19);
    *((_QWORD *)this + 69) = 0;
    *((_QWORD *)this + 63) = 0;
    goto LABEL_32;
  }
  REFERENCED_OBJECT::AddReference(this);
  LRPC_BASE_CCALL::FreeBuffer(this, a2);
  *((_DWORD *)this + 67) = 0;
}

```

## disassembly

```asm
0x180025630  mov     [rsp+arg_10], rbx
0x180025635  push    rsi
0x180025636  push    rdi
0x180025637  push    r14
0x180025639  sub     rsp, 90h
0x180025640  mov     rax, cs:__security_cookie
0x180025647  xor     rax, rsp
0x18002564a  mov     [rsp+0A8h+var_28], rax
0x180025652  mov     rax, [rcx]
0x180025655  mov     rdi, rdx
0x180025658  mov     rsi, rcx
0x18002565b  mov     rax, [rax+120h]
0x180025662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025667  test    eax, eax
0x180025669  jnz     loc_1800258C0
0x18002566f  mov     eax, [rsi+120h]
0x180025675  xor     r14d, r14d
0x180025678  mov     [rsp+0A8h+arg_8], rbp
0x180025680  bt      eax, 0Bh
0x180025684  jnb     loc_180025732
0x18002568a  mov     rax, [rsi]
0x18002568d  mov     rcx, rsi
0x180025690  mov     rax, [rax+120h]
0x180025697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002569c  test    eax, eax
0x18002569e  jnz     loc_18002597E
0x1800256a4  mov     rbx, gs:30h
0x1800256ad  mov     rbx, [rbx+1698h]
0x1800256b4  test    rbx, rbx
0x1800256b7  jz      short loc_1800256DD
0x1800256b9  mov     rax, 0ABABABABDEDEDEDEh
0x1800256c3  xor     rbx, rax
0x1800256c6  mov     rax, gs:30h
0x1800256cf  mov     rcx, [rax+48h]
0x1800256d3  cmp     [rbx+10h], rcx
0x1800256d7  jnz     loc_1800258B9
0x1800256dd  mov     rbp, [rsi+340h]
0x1800256e4  nop     dword ptr [rax+00h]
0x1800256e8  nop     dword ptr [rax+rax+00000000h]
0x1800256f0  mov     rdi, [rbx+48h]
0x1800256f4  mov     rax, rdi
0x1800256f7  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800256fb  cmp     rax, rsi
0x1800256fe  jnz     loc_1800258AB
0x180025704  mov     rax, [rbx+48h]
0x180025708  test    al, 1
0x18002570a  jnz     loc_180025910
0x180025710  mov     rax, rdi
0x180025713  lock cmpxchg [rbx+48h], rbp
0x180025719  jnz     short loc_1800256F0
0x18002571b  mov     rax, [rsi+348h]
0x180025722  mov     [rsi+340h], r14
0x180025729  test    rax, rax
0x18002572c  jnz     loc_180025957
0x180025732  mov     edx, 3
0x180025737  lea     rcx, [rsi+268h]; this
0x18002573e  cmp     [rsi+10Ch], edx
0x180025744  cmovl   edx, r14d; unsigned int
0x180025748  call    ?CleanupSystemHandles@LRPC_SYSTEM_HANDLE_DATA@@QEAAHK@Z; LRPC_SYSTEM_HANDLE_DATA::CleanupSystemHandles(ulong)
0x18002574d  cmp     dword ptr [rsi+10Ch], 3
0x180025754  jl      loc_1800259D0
0x18002575a  cmp     [rsi+1F8h], r14
0x180025761  jz      loc_180025870
0x180025767  mov     ebx, r14d
0x18002576a  cmp     [rsi+220h], rbx
0x180025771  jnz     loc_1800258F0
0x180025777  cmp     [rsi+260h], r14d
0x18002577e  jnz     loc_18002592A
0x180025784  test    ebx, ebx
0x180025786  jz      loc_180025851
0x18002578c  mov     rdi, [rsi+228h]
0x180025793  mov     r10d, ebx
0x180025796  btr     r10d, 1Ch
0x18002579b  mov     r11d, ebx
0x18002579e  bt      ebx, 1Ch
0x1800257a2  cmovnb  r10d, ebx
0x1800257a6  mov     ecx, r10d; unsigned int
0x1800257a9  call    ?RpcpAlpcpGetHeaderSize@@YAKK@Z; RpcpAlpcpGetHeaderSize(ulong)
0x1800257ae  mov     r9d, eax
0x1800257b1  and     r11d, 40000000h
0x1800257b8  mov     eax, 28h ; '('
0x1800257bd  mov     ecx, 8
0x1800257c2  cmovz   eax, ecx
0x1800257c5  cmp     r9, rax
0x1800257c8  ja      loc_180025A4D
0x1800257ce  mov     [rsp+0A8h+var_68], r10d
0x1800257d3  mov     [rsp+0A8h+var_64], r14d
0x1800257d8  test    r11d, r11d
0x1800257db  jz      short loc_18002580F
0x1800257dd  and     r10d, 80000000h
0x1800257e4  mov     ecx, r10d; unsigned int
0x1800257e7  call    ?RpcpAlpcpGetHeaderSize@@YAKK@Z; RpcpAlpcpGetHeaderSize(ulong)
0x1800257ec  mov     r9d, eax
0x1800257ef  mov     [rsp+r9+0A8h+var_68], 10000h
0x1800257f8  mov     [rsp+r9+0A8h+var_60], r14
0x1800257fd  mov     [rsp+r9+0A8h+var_58], r14
0x180025802  mov     [rsp+r9+0A8h+var_50], r14
0x180025807  or      [rsp+0A8h+var_64], 40000000h
0x18002580f  mov     rcx, [rsi+118h]; this
0x180025816  lea     r9, [rsp+0A8h+var_68]; struct _ALPC_MESSAGE_ATTRIBUTES *
0x18002581b  mov     [rsp+0A8h+var_78], r14; struct _ALPC_MESSAGE_ATTRIBUTES *
0x180025820  mov     r8, rdi; struct _PORT_MESSAGE *
0x180025823  mov     [rsp+0A8h+var_80], r14; unsigned __int64 *
0x180025828  xor     edx, edx; unsigned int
0x18002582a  mov     [rsp+0A8h+var_88], r14; struct _PORT_MESSAGE *
0x18002582f  call    ?AlpcSendWaitReceivePort@LRPC_CASSOCIATION@@QEAAJKPEAU_PORT_MESSAGE@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@0PEA_K1PEAT_LARGE_INTEGER@@@Z; LRPC_CASSOCIATION::AlpcSendWaitReceivePort(ulong,_PORT_MESSAGE *,_ALPC_MESSAGE_ATTRIBUTES *,_PORT_MESSAGE *,unsigned __int64 *,_ALPC_MESSAGE_ATTRIBUTES *,_LARGE_INTEGER *)
0x180025834  cmp     cs:dword_1800F9624, r14d
0x18002583b  jz      short loc_180025851
0x18002583d  mov     r9d, ebx; __int64
0x180025840  mov     r8, rdi; __int64
0x180025843  mov     dl, 40h ; '@'; unsigned __int8
0x180025845  mov     [rsp+0A8h+var_88], r14; __int64
0x18002584a  mov     cl, 4Ch ; 'L'; unsigned __int8
0x18002584c  call    ?LogEventToEtw@@YAXEE_J00@Z; LogEventToEtw(uchar,uchar,__int64,__int64,__int64)
0x180025851  mov     rdx, [rsi+228h]; void *
0x180025858  test    rdx, rdx
0x18002585b  jz      short loc_180025862
0x18002585d  call    ?Free@BCACHE@@QEAAXPEAX@Z; BCACHE::Free(void *)
0x180025862  mov     [rsi+228h], r14
0x180025869  mov     [rsi+1F8h], r14
0x180025870  mov     rax, [rsi]
0x180025873  mov     rcx, rsi
0x180025876  mov     rax, [rax+20h]
0x18002587a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002587f  mov     rbp, [rsp+0A8h+arg_8]
0x180025887  mov     rcx, [rsp+0A8h+var_28]
0x18002588f  xor     rcx, rsp; StackCookie
0x180025892  call    __security_check_cookie
0x180025897  mov     rbx, [rsp+0A8h+arg_10]
0x18002589f  add     rsp, 90h
0x1800258a6  pop     r14
0x1800258a8  pop     rdi
0x1800258a9  pop     rsi
0x1800258aa  retn
0x1800258ab  mov     rdx, rsi
0x1800258ae  mov     ecx, 15h
0x1800258b3  call    RpcpReportFatalError
0x1800258b8  int     3; Trap to Debugger
0x1800258b9  mov     ecx, 1Eh
0x1800258be  int     29h; Win8: RtlFailFast(ecx)
0x1800258c0  mov     rax, [rsi+250h]
0x1800258c7  cmp     dword ptr [rax+8], 0
0x1800258cb  jbe     loc_18002566F
0x1800258d1  mov     rcx, rsi; this
0x1800258d4  call    ?AddReference@REFERENCED_OBJECT@@QEAAHXZ; REFERENCED_OBJECT::AddReference(void)
0x1800258d9  mov     rdx, rdi; struct _RPC_MESSAGE *
0x1800258dc  mov     rcx, rsi; this
0x1800258df  call    ?FreeBuffer@LRPC_BASE_CCALL@@UEAAXPEAU_RPC_MESSAGE@@@Z; LRPC_BASE_CCALL::FreeBuffer(_RPC_MESSAGE *)
0x1800258e4  xor     r14d, r14d
0x1800258e7  mov     [rsi+10Ch], r14d
0x1800258ee  jmp     short loc_180025887
0x1800258f0  mov     eax, [rsi+120h]
0x1800258f6  bt      eax, 0Eh
0x1800258fa  jb      short loc_18002593A
0x1800258fc  mov     ebx, 40000000h
0x180025901  mov     [rsi+220h], r14
0x180025908  jmp     loc_180025777
0x180025910  mov     ecx, 0Ah; dwMilliseconds
0x180025915  call    cs:__imp_Sleep
0x18002591b  mov     rcx, [rbx+48h]
0x18002591f  test    cl, 1
0x180025922  jz      loc_180025710
0x180025928  jmp     short loc_180025910
0x18002592a  bts     ebx, 1Ch
0x18002592e  mov     [rsi+260h], r14d
0x180025935  jmp     loc_180025784
0x18002593a  mov     rdx, [rsi+220h]; void *
0x180025941  test    rdx, rdx
0x180025944  jz      short loc_180025901
0x180025946  call    ?Free@BCACHE@@QEAAXPEAX@Z; BCACHE::Free(void *)
0x18002594b  mov     [rsi+220h], r14
0x180025952  jmp     loc_180025777
0x180025957  lock or dword ptr [rsi+120h], 10000h
0x180025962  mov     rax, [rsi+348h]
0x180025969  test    rax, rax
0x18002596c  jnz     short loc_180025994
0x18002596e  lock and dword ptr [rsi+120h], 0FFFEFFFFh
0x180025979  jmp     loc_180025732
0x18002597e  mov     rax, [rsi+250h]
0x180025985  cmp     [rax+8], r14d
0x180025989  jz      loc_1800256A4
0x18002598f  jmp     loc_180025732
0x180025994  mov     rcx, [rbx+18h]; hEvent
0x180025998  call    cs:__imp_ResetEvent
0x18002599e  mov     r8, [rbx+18h]; CompletionEvent
0x1800259a2  xor     ecx, ecx; TimerQueue
0x1800259a4  mov     rdx, [rsi+348h]; Timer
0x1800259ab  call    cs:__imp_DeleteTimerQueueTimer
0x1800259b1  lock and dword ptr [rsi+120h], 0FFFEFFFFh
0x1800259bc  mov     rcx, [rbx+18h]; hHandle
0x1800259c0  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800259c5  call    cs:__imp_WaitForSingleObject
0x1800259cb  jmp     loc_180025732
0x1800259d0  mov     eax, [rsi+120h]
0x1800259d6  test    al, 2
0x1800259d8  jnz     short loc_180025A57
0x1800259da  cmp     dword ptr [rsi+10Ch], 2
0x1800259e1  jnz     loc_180025870
0x1800259e7  mov     rdx, [rsi+1F8h]; void *
0x1800259ee  test    rdx, rdx
0x1800259f1  jz      short loc_1800259F8
0x1800259f3  call    ?Free@BCACHE@@QEAAXPEAX@Z; BCACHE::Free(void *)
0x1800259f8  mov     [rsi+1F8h], r14
0x1800259ff  cmp     [rsi+200h], r14
0x180025a06  jz      loc_180025870
0x180025a0c  mov     eax, [rsi+120h]
0x180025a12  test    al, 10h
0x180025a14  jnz     short loc_180025A28
0x180025a16  mov     edx, 1; int
0x180025a1b  mov     rcx, rsi; this
0x180025a1e  call    ?FreeAlpcSectionAndView@LRPC_BASE_CCALL@@IEAAXH@Z; LRPC_BASE_CCALL::FreeAlpcSectionAndView(int)
0x180025a23  jmp     loc_180025870
0x180025a28  mov     rdx, [rsi+200h]; void *
0x180025a2f  test    rdx, rdx
0x180025a32  jz      short loc_180025A39
0x180025a34  call    ?Free@BCACHE@@QEAAXPEAX@Z; BCACHE::Free(void *)
0x180025a39  mov     [rsi+200h], r14
0x180025a40  lock and dword ptr [rsi+120h], 0FFFFFFEFh
0x180025a48  jmp     loc_180025870
0x180025a4d  mov     r10d, [rsp+0A8h+var_68]
0x180025a52  jmp     loc_1800257D8
0x180025a57  cmp     dword ptr [rsi+108h], 0Ah
0x180025a5e  jge     loc_1800259DA
0x180025a64  mov     rcx, rsi; this
0x180025a67  call    ?CancelCall@LRPC_BASE_CCALL@@IEAAXXZ; LRPC_BASE_CCALL::CancelCall(void)
0x180025a6c  jmp     loc_1800259DA
```
