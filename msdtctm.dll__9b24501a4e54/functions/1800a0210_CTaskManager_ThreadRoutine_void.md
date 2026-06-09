# CTaskManager::ThreadRoutine(void *)

- ea: `0x1800a0210`
- end: `0x1800a0454`
- name: `?ThreadRoutine@CTaskManager@@SAKPEAX@Z`
- size: `580`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180074a40`
- `0x18009dd1c`
- `0x18009deb0`
- `0x18009e0e8`
- `0x18009e708`
- `0x1800a0210`
- `0x1800a0540`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800a029f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800a029f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0354`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0399`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a03a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a042d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0354`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0399`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a03a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a042d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a031e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a037c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a03fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a031e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a037c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a03fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a033c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a033c`
- `msvcrt!_endthreadex` at `0x1800a035c`
- `msvcrt!_endthreadex` at `0x1800a035c`

## string_xrefs

- `0x1800a02dc`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTaskManager::ThreadRoutine(_QWORD *Parameter)
{
  __int16 v2; // bx
  DWORD v3; // eax
  DWORD v4; // edi
  struct IWorkerTask *v6; // rsi
  int v7; // eax
  int v8; // eax
  CXaOpenState *MyXaOpenState; // rbx
  __int64 v10; // r14
  CXaOpenState *v11; // r14
  struct IWorkerTask *v12; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v13[5]; // [rsp+38h] [rbp-48h] BYREF
  HANDLE Handles[2]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v15; // [rsp+70h] [rbp-10h]

  v12 = 0;
  v13[1] = &UTStaticList2Iterator<CResourceInterface *>::`vftable';
  v13[4] = Parameter + 6;
  v13[3] = 0;
  v13[2] = Parameter[8];
  *(_OWORD *)Handles = *(_OWORD *)&CTaskManager::m_rghPendingWorkEvents;
  v15 = Parameter[1];
LABEL_2:
  v2 = 2;
  do
  {
    while ( 1 )
    {
      v3 = WaitForMultipleObjectsEx(3u, Handles, 0, 0xFFFFFFFF, 0);
      v4 = v3;
      if ( !v3 )
      {
        while ( 1 )
        {
LABEL_16:
          if ( v4 )
          {
            v7 = CTaskManager::DequeueClose(Parameter + 2, &v12);
            v6 = v12;
          }
          else
          {
            v13[0] = 0;
            v6 = 0;
            v12 = 0;
            EnterCriticalSection(&stru_180153898);
            if ( (unsigned int)UTStaticList<CAscCall *>::RemoveFirst(&CTaskManager::m_queueOfWorkerTasks, v13) )
            {
              LeaveCriticalSection(&stru_180153898);
              v6 = *(struct IWorkerTask **)(v13[0] + 8LL);
              v12 = v6;
              (*(void (__fastcall **)(struct IWorkerTask *))(*(_QWORD *)v6 + 16LL))(v6);
              v7 = 1;
            }
            else
            {
              LeaveCriticalSection(&stru_180153898);
              v7 = 0;
            }
          }
          if ( !v7 )
            break;
          if ( (*(__int64 (__fastcall **)(struct IWorkerTask *))(*(_QWORD *)v6 + 24LL))(v6) )
          {
            EnterCriticalSection(&stru_180153898);
            v8 = (*(__int64 (__fastcall **)(struct IWorkerTask *))(*(_QWORD *)v6 + 32LL))(v6);
            MyXaOpenState = CTaskManager::GetMyXaOpenState(v8);
            v10 = -(__int64)((unsigned int)CXaOpenState::IsOperationNecessary(MyXaOpenState, v6) != 0);
            LeaveCriticalSection(&stru_180153898);
            v11 = (CXaOpenState *)((unsigned __int64)MyXaOpenState & v10);
            if ( v11 )
              CXaOpenState::DoOperation(v11);
          }
          (**(void (__fastcall ***)(struct IWorkerTask *))v6)(v6);
        }
        goto LABEL_2;
      }
      if ( v3 != 1 )
        break;
      EnterCriticalSection(&stru_180153898);
      if ( !--CTaskManager::m_cbThreadPool )
      {
        do
        {
          CloseHandle(&CTaskManager::m_rghPendingWorkEvents);
          --v2;
        }
        while ( v2 );
        v2 = 2;
      }
      LeaveCriticalSection(&stru_180153898);
      _endthreadex(0);
    }
    if ( v3 == 2 )
      goto LABEL_16;
  }
  while ( v3 == 128 || v3 == 129 || v3 == 130 );
  if ( v3 != -1 )
    XA_TRACE_FATAL(0xC000110F, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 363);
  return 1;
}

```

## disassembly

```asm
0x1800a0210  mov     [rsp-28h+arg_8], rbx
0x1800a0215  mov     [rsp-28h+arg_10], rsi
0x1800a021a  push    rbp
0x1800a021b  push    rdi
0x1800a021c  push    r13
0x1800a021e  push    r14
0x1800a0220  push    r15
0x1800a0222  mov     rbp, rsp
0x1800a0225  sub     rsp, 80h
0x1800a022c  mov     rax, cs:__security_cookie
0x1800a0233  xor     rax, rsp
0x1800a0236  mov     [rbp+var_8], rax
0x1800a023a  mov     r15, rcx
0x1800a023d  mov     [rbp+var_50], 0
0x1800a0245  lea     rax, ??_7?$UTStaticList2Iterator@PEAVCResourceInterface@@@@6B@; const UTStaticList2Iterator<CResourceInterface *>::`vftable'
0x1800a024c  mov     [rbp+var_40], rax
0x1800a0250  lea     rax, [rcx+30h]
0x1800a0254  mov     [rbp+var_28], rax
0x1800a0258  mov     [rbp+var_30], 0
0x1800a0260  mov     rax, [rax+10h]
0x1800a0264  mov     [rbp+var_38], rax
0x1800a0268  movups  xmm0, cs:?m_rghPendingWorkEvents@CTaskManager@@0PAPEAXA; void * near * CTaskManager::m_rghPendingWorkEvents
0x1800a026f  movdqu  xmmword ptr [rbp+Handles], xmm0
0x1800a0274  mov     rax, [rcx+8]
0x1800a0278  mov     [rbp+var_10], rax
0x1800a027c  lea     r13, stru_180153898
0x1800a0283  mov     ebx, 2
0x1800a0288  mov     [rsp+80h+bAlertable], 0; bAlertable
0x1800a0290  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800a0294  xor     r8d, r8d; bWaitAll
0x1800a0297  lea     rdx, [rbp+Handles]; lpHandles
0x1800a029b  lea     ecx, [r8+3]; nCount
0x1800a029f  call    cs:__imp_WaitForMultipleObjectsEx
0x1800a02a5  mov     edi, eax
0x1800a02a7  test    eax, eax
0x1800a02a9  jz      loc_1800A0367
0x1800a02af  cmp     eax, 1
0x1800a02b2  jz      short loc_1800A031B
0x1800a02b4  cmp     eax, ebx
0x1800a02b6  jz      loc_1800A0367
0x1800a02bc  cmp     eax, 80h
0x1800a02c1  jz      short loc_1800A0288
0x1800a02c3  cmp     eax, 81h
0x1800a02c8  jz      short loc_1800A0288
0x1800a02ca  cmp     eax, 82h
0x1800a02cf  jz      short loc_1800A0288
0x1800a02d1  cmp     eax, 0FFFFFFFFh
0x1800a02d4  jz      short loc_1800A02EE
0x1800a02d6  mov     r8d, 16Bh; int
0x1800a02dc  lea     rdx, aComComplusDtcD_81; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x1800a02e3  mov     ecx, 0C000110Fh; unsigned int
0x1800a02e8  call    ?XA_TRACE_FATAL@@YAXKPEADH@Z; XA_TRACE_FATAL(ulong,char *,int)
0x1800a02ed  nop
0x1800a02ee  mov     eax, 1
0x1800a02f3  mov     rcx, [rbp+var_8]
0x1800a02f7  xor     rcx, rsp; StackCookie
0x1800a02fa  call    __security_check_cookie
0x1800a02ff  lea     r11, [rsp+80h+var_s0]
0x1800a0307  mov     rbx, [r11+38h]
0x1800a030b  mov     rsi, [r11+40h]
0x1800a030f  mov     rsp, r11
0x1800a0312  pop     r15
0x1800a0314  pop     r14
0x1800a0316  pop     r13
0x1800a0318  pop     rdi
0x1800a0319  pop     rbp
0x1800a031a  retn
0x1800a031b  mov     rcx, r13; lpCriticalSection
0x1800a031e  call    cs:__imp_EnterCriticalSection
0x1800a0324  mov     eax, cs:?m_cbThreadPool@CTaskManager@@0KA; ulong CTaskManager::m_cbThreadPool
0x1800a032a  add     eax, 0FFFFFFFFh
0x1800a032d  mov     cs:?m_cbThreadPool@CTaskManager@@0KA, eax; ulong CTaskManager::m_cbThreadPool
0x1800a0333  jnz     short loc_1800A0351
0x1800a0335  lea     rcx, ?m_rghPendingWorkEvents@CTaskManager@@0PAPEAXA; hObject
0x1800a033c  call    cs:__imp_CloseHandle
0x1800a0342  mov     eax, 0FFFFh
0x1800a0347  add     bx, ax
0x1800a034a  jnz     short loc_1800A0335
0x1800a034c  mov     ebx, 2
0x1800a0351  mov     rcx, r13; lpCriticalSection
0x1800a0354  call    cs:__imp_LeaveCriticalSection
0x1800a035a  xor     ecx, ecx; ReturnCode
0x1800a035c  call    cs:__imp__endthreadex
0x1800a0362  jmp     loc_1800A0288
0x1800a0367  test    edi, edi
0x1800a0369  jnz     short loc_1800A03CB
0x1800a036b  mov     [rbp+var_48], 0
0x1800a0373  xor     esi, esi
0x1800a0375  mov     [rbp+var_50], rsi
0x1800a0379  mov     rcx, r13; lpCriticalSection
0x1800a037c  call    cs:__imp_EnterCriticalSection
0x1800a0382  lea     rdx, [rbp+var_48]
0x1800a0386  lea     rcx, ?m_queueOfWorkerTasks@CTaskManager@@0V?$UTStaticList@PEAVCWorkerTask@@@@A; UTStaticList<CWorkerTask *> CTaskManager::m_queueOfWorkerTasks
0x1800a038d  call    ?RemoveFirst@?$UTStaticList@PEAVCAscCall@@@@UEAAHPEAPEAV?$UTLink@PEAVCAscCall@@@@@Z; UTStaticList<CAscCall *>::RemoveFirst(UTLink<CAscCall *> * *)
0x1800a0392  mov     rcx, r13; lpCriticalSection
0x1800a0395  test    eax, eax
0x1800a0397  jnz     short loc_1800A03A3
0x1800a0399  call    cs:__imp_LeaveCriticalSection
0x1800a039f  xor     eax, eax
0x1800a03a1  jmp     short loc_1800A03DC
0x1800a03a3  call    cs:__imp_LeaveCriticalSection
0x1800a03a9  mov     rax, [rbp+var_48]
0x1800a03ad  mov     rsi, [rax+8]
0x1800a03b1  mov     [rbp+var_50], rsi
0x1800a03b5  mov     rax, [rsi]
0x1800a03b8  mov     rcx, rsi
0x1800a03bb  mov     rax, [rax+10h]
0x1800a03bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a03c4  mov     eax, 1
0x1800a03c9  jmp     short loc_1800A03DC
0x1800a03cb  lea     rcx, [r15+10h]
0x1800a03cf  lea     rdx, [rbp+var_50]
0x1800a03d3  call    ?DequeueClose@CTaskManager@@SAHPEAV?$UTStaticList@PEAVCWorkerTask@@@@PEAPEAUIWorkerTask@@@Z; CTaskManager::DequeueClose(UTStaticList<CWorkerTask *> *,IWorkerTask * *)
0x1800a03d8  mov     rsi, [rbp+var_50]
0x1800a03dc  test    eax, eax
0x1800a03de  jz      loc_1800A0283
0x1800a03e4  mov     rax, [rsi]
0x1800a03e7  mov     rcx, rsi
0x1800a03ea  mov     rax, [rax+18h]
0x1800a03ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a03f3  test    rax, rax
0x1800a03f6  jz      short loc_1800A0440
0x1800a03f8  mov     rcx, r13; lpCriticalSection
0x1800a03fb  call    cs:__imp_EnterCriticalSection
0x1800a0401  mov     rax, [rsi]
0x1800a0404  mov     rcx, rsi
0x1800a0407  mov     rax, [rax+20h]
0x1800a040b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0410  mov     ecx, eax; unsigned int
0x1800a0412  call    ?GetMyXaOpenState@CTaskManager@@SAPEAVCXaOpenState@@I@Z; CTaskManager::GetMyXaOpenState(uint)
0x1800a0417  mov     rbx, rax
0x1800a041a  mov     rdx, rsi; struct IWorkerTask *
0x1800a041d  mov     rcx, rax; this
0x1800a0420  call    ?IsOperationNecessary@CXaOpenState@@QEAAHPEAUIWorkerTask@@@Z; CXaOpenState::IsOperationNecessary(IWorkerTask *)
0x1800a0425  neg     eax
0x1800a0427  sbb     r14, r14
0x1800a042a  mov     rcx, r13; lpCriticalSection
0x1800a042d  call    cs:__imp_LeaveCriticalSection
0x1800a0433  and     r14, rbx
0x1800a0436  jz      short loc_1800A0440
0x1800a0438  mov     rcx, r14; this
0x1800a043b  call    ?DoOperation@CXaOpenState@@QEAAXXZ; CXaOpenState::DoOperation(void)
0x1800a0440  mov     rax, [rsi]
0x1800a0443  mov     rcx, rsi
0x1800a0446  mov     rax, [rax]
0x1800a0449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a044e  jmp     loc_1800A0367
```
