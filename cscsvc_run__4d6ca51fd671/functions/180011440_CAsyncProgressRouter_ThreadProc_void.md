# CAsyncProgressRouter::_ThreadProc(void *)

- ea: `0x180011440`
- end: `0x1800116fc`
- name: `?_ThreadProc@CAsyncProgressRouter@@CAKPEAX@Z`
- size: `700`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update`

## callees

- `0x18000c3f0`
- `0x18000f5d4`
- `0x180011440`
- `0x18001b150`
- `0x18001b4e0`
- `0x180035908`
- `0x180036394`
- `0x180039610`
- `0x18003c460`
- `0x180063574`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011688`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800116cb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800116cb`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800115f7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800115f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800115b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011620`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800115b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011620`
- `USER32!PeekMessageW` at `0x180011527`
- `USER32!PeekMessageW` at `0x180011527`
- `USER32!DispatchMessageW` at `0x180011510`
- `USER32!DispatchMessageW` at `0x180011510`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x1800114d6`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x1800114d6`
- `USER32!TranslateMessage` at `0x180011506`
- `USER32!TranslateMessage` at `0x180011506`

## pseudocode

```c
__int64 __fastcall CAsyncProgressRouter::_ThreadProc(PVOID Parameter)
{
  HMODULE v2; // r14
  int v3; // esi
  int v4; // r15d
  DWORD v5; // edi
  unsigned int *v6; // rdi
  const unsigned __int16 *ConstBuffer; // rax
  __int64 v8; // r10
  unsigned int v9; // edx
  DWORD TickCount; // eax
  bool v11; // zf
  __int64 v12; // rcx
  DWORD v13; // eax
  DWORD LastError; // eax
  int v16; // [rsp+30h] [rbp-29h] BYREF
  int v17; // [rsp+34h] [rbp-25h] BYREF
  struct CAsyncProgressRouter::QUEUE_ENTRY *v18; // [rsp+38h] [rbp-21h] BYREF
  MSG Msg; // [rsp+40h] [rbp-19h] BYREF
  HANDLE pHandles[3]; // [rsp+70h] [rbp+17h] BYREF

  if ( (int)CscService_TaskBegin(0) >= 0 )
  {
    v2 = 0;
    if ( Parameter )
    {
      v2 = (HMODULE)*((_QWORD *)Parameter + 9);
      pHandles[0] = *((HANDLE *)Parameter + 8);
      pHandles[1] = *((HANDLE *)Parameter + 7);
      pHandles[2] = *((HANDLE *)Parameter + 4);
      *((_QWORD *)Parameter + 9) = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            v3 = 0;
            v4 = 0;
            do
            {
              v5 = MsgWaitForMultipleObjectsEx(3u, pHandles, 0x3E8u, 0x1CFFu, 4u);
              if ( v5 != 3 )
                break;
              memset(&Msg, 0, sizeof(Msg));
              while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
              {
                if ( Msg.message == 18 )
                {
                  v3 = 1;
                  v4 = 1;
                }
                else
                {
                  TranslateMessage(&Msg);
                  DispatchMessageW(&Msg);
                }
              }
            }
            while ( !v3 );
            if ( v4 )
            {
LABEL_34:
              CRefCounted::ReleaseReference((CRefCounted *)Parameter);
              goto LABEL_35;
            }
            if ( v5 == -1 )
            {
              if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                LastError = GetLastError();
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  104,
                  WPP_7967f24143133d59f1b33f7a742017bc_Traceguids,
                  LastError);
              }
              goto LABEL_34;
            }
            if ( !v5 )
            {
              if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids);
              }
              goto LABEL_34;
            }
            if ( v5 != 1 )
              break;
            v18 = 0;
            if ( (unsigned int)CAsyncProgressRouter::_RemoveEntryFromProgressInfoQueue(
                                 (CAsyncProgressRouter *)Parameter,
                                 &v18) )
            {
              v6 = (unsigned int *)v18;
              v16 = 0;
              ConstBuffer = CPath::_GetConstBuffer((struct CAsyncProgressRouter::QUEUE_ENTRY *)((char *)v18 + 16));
              if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, _QWORD, unsigned int *, int *))(*(_QWORD *)v8 + 56LL))(
                     v8,
                     ConstBuffer,
                     v6[148],
                     v6 + 150,
                     &v16) >= 0 )
              {
                TickCount = GetTickCount();
                v11 = v16 == 2;
                *((_DWORD *)Parameter + 211) = TickCount;
                if ( v11 )
                  *((_DWORD *)Parameter + 6) = 1;
              }
              if ( v6 )
                CAsyncProgressRouter::QUEUE_ENTRY::`scalar deleting destructor'(
                  (CAsyncProgressRouter::QUEUE_ENTRY *)v6,
                  v9);
            }
          }
          if ( v5 != 258 )
            break;
LABEL_25:
          v12 = *((_QWORD *)Parameter + 2);
          v17 = 0;
          if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 32LL))(v12, &v17) >= 0 )
          {
            v13 = GetTickCount();
            v11 = v17 == 0;
            *((_DWORD *)Parameter + 211) = v13;
            if ( !v11 )
              *((_DWORD *)Parameter + 6) = 1;
          }
        }
        if ( v5 == 2 )
        {
          ResetEvent(*((HANDLE *)Parameter + 4));
          goto LABEL_25;
        }
      }
    }
LABEL_35:
    CInvSemaphore::Decrement((CInvSemaphore *)&g_invsemTasksInProgress);
    if ( v2 )
      FreeLibraryAndExitThread(v2, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180011440  mov     [rsp-8+arg_8], rbx
0x180011445  mov     [rsp-8+arg_10], rsi
0x18001144a  push    rbp
0x18001144b  push    rdi
0x18001144c  push    r13
0x18001144e  push    r14
0x180011450  push    r15
0x180011452  lea     rbp, [rsp-37h]
0x180011457  sub     rsp, 90h
0x18001145e  mov     rax, cs:__security_cookie
0x180011465  xor     rax, rsp
0x180011468  mov     [rbp+57h+var_28], rax
0x18001146c  mov     rbx, rcx
0x18001146f  xor     ecx, ecx; int
0x180011471  call    ?CscService_TaskBegin@@YAJH@Z; CscService_TaskBegin(int)
0x180011476  test    eax, eax
0x180011478  js      loc_1800116D2
0x18001147e  xor     r14d, r14d
0x180011481  test    rbx, rbx
0x180011484  jz      loc_1800116B5
0x18001148a  mov     rax, [rbx+40h]
0x18001148e  mov     r13d, 1
0x180011494  mov     r14, [rbx+48h]
0x180011498  mov     [rbp+57h+pHandles], rax
0x18001149c  mov     rax, [rbx+38h]
0x1800114a0  mov     [rbp+57h+var_38], rax
0x1800114a4  mov     rax, [rbx+20h]
0x1800114a8  mov     [rbp+57h+var_30], rax
0x1800114ac  mov     qword ptr [rbx+48h], 0
0x1800114b4  xor     esi, esi
0x1800114b6  xor     r15d, r15d
0x1800114b9  mov     r9d, 1CFFh; dwWakeMask
0x1800114bf  mov     [rsp+0B0h+dwFlags], 4; dwFlags
0x1800114c7  mov     r8d, 3E8h; dwMilliseconds
0x1800114cd  lea     rdx, [rbp+57h+pHandles]; pHandles
0x1800114d1  mov     ecx, 3; nCount
0x1800114d6  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x1800114dc  mov     edi, eax
0x1800114de  cmp     eax, 3
0x1800114e1  jnz     short loc_180011535
0x1800114e3  xorps   xmm0, xmm0
0x1800114e6  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x1800114ea  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x1800114ee  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x1800114f2  jmp     short loc_180011516
0x1800114f4  cmp     [rbp+57h+Msg.message], 12h
0x1800114f8  jnz     short loc_180011502
0x1800114fa  mov     esi, r13d
0x1800114fd  mov     r15d, r13d
0x180011500  jmp     short loc_180011516
0x180011502  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180011506  call    cs:__imp_TranslateMessage
0x18001150c  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180011510  call    cs:__imp_DispatchMessageW
0x180011516  xor     r9d, r9d; wMsgFilterMax
0x180011519  mov     [rsp+0B0h+dwFlags], r13d; wRemoveMsg
0x18001151e  xor     r8d, r8d; wMsgFilterMin
0x180011521  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180011525  xor     edx, edx; hWnd
0x180011527  call    cs:__imp_PeekMessageW
0x18001152d  test    eax, eax
0x18001152f  jnz     short loc_1800114F4
0x180011531  test    esi, esi
0x180011533  jz      short loc_1800114B9
0x180011535  test    r15d, r15d
0x180011538  jnz     loc_1800116AD
0x18001153e  cmp     edi, 0FFFFFFFFh
0x180011541  jz      loc_18001166F
0x180011547  test    edi, edi
0x180011549  jz      loc_18001163F
0x18001154f  cmp     edi, r13d
0x180011552  jnz     loc_1800115E2
0x180011558  lea     rdx, [rbp+57h+var_78]; struct CAsyncProgressRouter::QUEUE_ENTRY **
0x18001155c  mov     [rbp+57h+var_78], 0
0x180011564  mov     rcx, rbx; this
0x180011567  call    ?_RemoveEntryFromProgressInfoQueue@CAsyncProgressRouter@@AEAAHPEAPEAVQUEUE_ENTRY@1@@Z; CAsyncProgressRouter::_RemoveEntryFromProgressInfoQueue(CAsyncProgressRouter::QUEUE_ENTRY * *)
0x18001156c  test    eax, eax
0x18001156e  jz      loc_1800114B4
0x180011574  mov     rdi, [rbp+57h+var_78]
0x180011578  mov     r10, [rbx+10h]
0x18001157c  mov     [rbp+57h+var_80], r15d
0x180011580  lea     rcx, [rdi+10h]; this
0x180011584  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x180011589  mov     rcx, [r10]
0x18001158c  lea     r9, [rdi+258h]
0x180011593  mov     r8d, [rdi+250h]
0x18001159a  mov     rdx, rax
0x18001159d  mov     rax, [rcx+38h]
0x1800115a1  lea     rcx, [rbp+57h+var_80]
0x1800115a5  mov     qword ptr [rsp+0B0h+dwFlags], rcx
0x1800115aa  mov     rcx, r10
0x1800115ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115b2  test    eax, eax
0x1800115b4  js      short loc_1800115CC
0x1800115b6  call    cs:__imp_GetTickCount
0x1800115bc  cmp     [rbp+57h+var_80], 2
0x1800115c0  mov     [rbx+34Ch], eax
0x1800115c6  jnz     short loc_1800115CC
0x1800115c8  mov     [rbx+18h], r13d
0x1800115cc  test    rdi, rdi
0x1800115cf  jz      loc_1800114B4
0x1800115d5  mov     rcx, rdi; this
0x1800115d8  call    ??_GQUEUE_ENTRY@CAsyncProgressRouter@@QEAAPEAXI@Z; CAsyncProgressRouter::QUEUE_ENTRY::`scalar deleting destructor'(uint)
0x1800115dd  jmp     loc_1800114B4
0x1800115e2  cmp     edi, 102h
0x1800115e8  jz      short loc_1800115FD
0x1800115ea  cmp     edi, 2
0x1800115ed  jnz     loc_1800114B4
0x1800115f3  mov     rcx, [rbx+20h]; hEvent
0x1800115f7  call    cs:__imp_ResetEvent
0x1800115fd  mov     rcx, [rbx+10h]
0x180011601  lea     rdx, [rbp+57h+var_7C]
0x180011605  mov     [rbp+57h+var_7C], 0
0x18001160c  mov     rax, [rcx]
0x18001160f  mov     rax, [rax+20h]
0x180011613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011618  test    eax, eax
0x18001161a  js      loc_1800114B4
0x180011620  call    cs:__imp_GetTickCount
0x180011626  cmp     [rbp+57h+var_7C], 0
0x18001162a  mov     [rbx+34Ch], eax
0x180011630  jz      loc_1800114B4
0x180011636  mov     [rbx+18h], r13d
0x18001163a  jmp     loc_1800114B4
0x18001163f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011646  lea     rax, WPP_GLOBAL_Control
0x18001164d  cmp     rcx, rax
0x180011650  jz      short loc_1800116AD
0x180011652  test    byte ptr [rcx+1Ch], 2
0x180011656  jz      short loc_1800116AD
0x180011658  mov     rcx, [rcx+10h]
0x18001165c  lea     r8, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids
0x180011663  mov     edx, 69h ; 'i'
0x180011668  call    WPP_SF_
0x18001166d  jmp     short loc_1800116AD
0x18001166f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011676  lea     rax, WPP_GLOBAL_Control
0x18001167d  cmp     rcx, rax
0x180011680  jz      short loc_1800116AD
0x180011682  test    byte ptr [rcx+1Ch], 2
0x180011686  jz      short loc_1800116AD
0x180011688  call    cs:__imp_GetLastError
0x18001168e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011695  lea     r8, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids
0x18001169c  mov     edx, 68h ; 'h'
0x1800116a1  mov     r9d, eax
0x1800116a4  mov     rcx, [rcx+10h]
0x1800116a8  call    WPP_SF_d
0x1800116ad  mov     rcx, rbx; this
0x1800116b0  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x1800116b5  lea     rcx, ?g_invsemTasksInProgress@@3VCInvSemaphore@@A; this
0x1800116bc  call    ?Decrement@CInvSemaphore@@QEAAXXZ; CInvSemaphore::Decrement(void)
0x1800116c1  test    r14, r14
0x1800116c4  jz      short loc_1800116D2
0x1800116c6  xor     edx, edx; dwExitCode
0x1800116c8  mov     rcx, r14; hLibModule
0x1800116cb  call    cs:__imp_FreeLibraryAndExitThread
0x1800116d1  int     3; Trap to Debugger
0x1800116d2  xor     eax, eax
0x1800116d4  mov     rcx, [rbp+57h+var_28]
0x1800116d8  xor     rcx, rsp; StackCookie
0x1800116db  call    __security_check_cookie
0x1800116e0  lea     r11, [rsp+0B0h+var_20]
0x1800116e8  mov     rbx, [r11+38h]
0x1800116ec  mov     rsi, [r11+40h]
0x1800116f0  mov     rsp, r11
0x1800116f3  pop     r15
0x1800116f5  pop     r14
0x1800116f7  pop     r13
0x1800116f9  pop     rdi
0x1800116fa  pop     rbp
0x1800116fb  retn
```
