# CUploadJob::OnRetryJob(void)

- ea: `0x180041c30`
- end: `0x180041eb2`
- name: `?OnRetryJob@CUploadJob@@UEAAXXZ`
- size: `642`
- prototype: `void __fastcall(CUploadJob *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18002cc00`
- `0x180034760`
- `0x1800383a8`
- `0x180039ef0`
- `0x180041c30`
- `0x180041ec0`
- `0x180067284`
- `0x180076d90`
- `0x18009d024`
- `0x1800ab7fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041c9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041cf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041c9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041cf0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180041ddd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180041ddd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180041e1d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180041e1d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041c98`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041dd1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041c98`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041dd1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180041e83`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180041e83`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180041ea0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180041ea0`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180041cdd`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180041cdd`

## pseudocode

```c
void __fastcall CUploadJob::OnRetryJob(CUploadJob *this)
{
  CJobManager *v1; // rbx
  void *CancelEvent; // rax
  bool v4; // dl
  EVENT_LOG *v5; // rcx
  __int64 v6; // rdx
  DWORD v7; // eax
  int v8; // eax
  CJobManager *v9; // rcx
  CJobManager *v10; // rdi
  _QWORD *Value; // rax
  _QWORD *v12; // rbx
  __int64 v13; // rax
  void *v14; // rcx
  HANDLE Handles[7]; // [rsp+20h] [rbp-38h] BYREF

  v1 = g_Manager;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
  CancelEvent = TaskScheduler::GetCancelEvent((CJobManager *)((char *)v1 + 520));
  if ( !CancelEvent )
  {
    WaitForSingleObject(*((HANDLE *)v1 + 70), 0xFFFFFFFF);
    *((_DWORD *)v1 + 144) = GetCurrentThreadId();
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      v6 = 31;
LABEL_13:
      WPP_SF_(*((_QWORD *)v5 + 2), v6, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
      goto LABEL_14;
    }
    goto LABEL_14;
  }
  Handles[1] = *((HANDLE *)v1 + 70);
  Handles[0] = CancelEvent;
  v7 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
  if ( v7 )
  {
    if ( v7 == 1 )
    {
      *((_DWORD *)v1 + 144) = GetCurrentThreadId();
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        v6 = 33;
        goto LABEL_13;
      }
    }
LABEL_14:
    v8 = *((_DWORD *)this + 141);
    if ( v8 == 5 )
    {
      CJob::SetState((CUploadJob *)((char *)this - 96), BG_JOB_STATE_QUEUED);
      CJobManager::AppendOnline(v9, (CUploadJob *)((char *)this - 96));
      CJob::UpdateModificationTime((char *)this - 96, 2);
    }
    else if ( (unsigned int)(v8 - 7) <= 1 )
    {
      *((_BYTE *)this + 1460) = 1;
      CJobManager::AppendOnline(v5, (CUploadJob *)((char *)this - 96));
    }
    TaskScheduler::CompleteWorkItem((CJobManager *)((char *)g_Manager + 520), v4);
    CJobManager::ScheduleAnotherGroup(g_Manager);
    TaskScheduler::UnlockWriter((CJobManager *)((char *)g_Manager + 520));
    return;
  }
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
  v10 = g_Manager;
  WaitForSingleObject(*((HANDLE *)g_Manager + 67), 0xFFFFFFFF);
  Value = TlsGetValue(*((_DWORD *)v10 + 143));
  v12 = Value;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids, Value);
  if ( v12 )
  {
    TlsSetValue(*((_DWORD *)v10 + 143), 0);
    v13 = v12[9] + 56LL;
    v12[11] = 0;
    if ( v12[3] == v13 && v12[3] )
    {
      *(_QWORD *)v12[2] = v12[1];
      *(_QWORD *)(v12[1] + 8LL) = v12[2];
      --*(_QWORD *)(v12[3] + 24LL);
      v12[1] = v12 + 1;
      v12[2] = v12 + 1;
      v12[3] = 0;
    }
    v14 = (void *)v12[7];
    v12[9] = 0;
    *((_DWORD *)v12 + 20) = 5;
    SetEvent(v14);
    v12[6] = 0;
    v12[7] = 0;
  }
  ReleaseMutex(*((HANDLE *)v10 + 67));
}

```

## disassembly

```asm
0x180041c30  push    rbx
0x180041c32  push    rbp
0x180041c33  push    rdi
0x180041c34  push    r14
0x180041c36  push    r15
0x180041c38  sub     rsp, 30h
0x180041c3c  mov     rbx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x180041c43  mov     rdi, rcx
0x180041c46  mov     rcx, cs:WPP_GLOBAL_Control
0x180041c4d  lea     r15, WPP_GLOBAL_Control
0x180041c54  lea     rbp, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x180041c5b  mov     r14d, 100h
0x180041c61  cmp     rcx, r15
0x180041c64  jz      short loc_180041C7D
0x180041c66  test    [rcx+1Ch], r14d
0x180041c6a  jz      short loc_180041C7D
0x180041c6c  mov     rcx, [rcx+10h]
0x180041c70  mov     edx, 1Eh
0x180041c75  mov     r8, rbp
0x180041c78  call    WPP_SF_
0x180041c7d  lea     rcx, [rbx+208h]; this
0x180041c84  call    ?GetCancelEvent@TaskScheduler@@QEAAPEAXXZ; TaskScheduler::GetCancelEvent(void)
0x180041c89  mov     rcx, [rbx+230h]; hHandle
0x180041c90  test    rax, rax
0x180041c93  jnz     short loc_180041CC3
0x180041c95  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180041c98  call    cs:__imp_WaitForSingleObject
0x180041c9e  call    cs:__imp_GetCurrentThreadId
0x180041ca4  mov     [rbx+240h], eax
0x180041caa  mov     rcx, cs:WPP_GLOBAL_Control
0x180041cb1  cmp     rcx, r15
0x180041cb4  jz      short loc_180041D1F
0x180041cb6  test    [rcx+1Ch], r14d
0x180041cba  jz      short loc_180041D1F
0x180041cbc  mov     edx, 1Fh
0x180041cc1  jmp     short loc_180041D13
0x180041cc3  xor     r8d, r8d; bWaitAll
0x180041cc6  mov     [rsp+58h+var_30], rcx
0x180041ccb  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180041ccf  mov     [rsp+58h+Handles], rax
0x180041cd4  lea     rdx, [rsp+58h+Handles]; lpHandles
0x180041cd9  lea     ecx, [r8+2]; nCount
0x180041cdd  call    cs:__imp_WaitForMultipleObjects
0x180041ce3  test    eax, eax
0x180041ce5  jz      loc_180041D9D
0x180041ceb  cmp     eax, 1
0x180041cee  jnz     short loc_180041D1F
0x180041cf0  call    cs:__imp_GetCurrentThreadId
0x180041cf6  mov     [rbx+240h], eax
0x180041cfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180041d03  cmp     rcx, r15
0x180041d06  jz      short loc_180041D1F
0x180041d08  test    [rcx+1Ch], r14d
0x180041d0c  jz      short loc_180041D1F
0x180041d0e  mov     edx, 21h ; '!'
0x180041d13  mov     rcx, [rcx+10h]
0x180041d17  mov     r8, rbp
0x180041d1a  call    WPP_SF_
0x180041d1f  lea     rbx, [rdi-60h]
0x180041d23  mov     eax, [rbx+294h]
0x180041d29  cmp     eax, 5
0x180041d2c  jnz     short loc_180041D4F
0x180041d2e  xor     edx, edx; enum BG_JOB_STATE
0x180041d30  mov     rcx, rbx; this
0x180041d33  call    ?SetState@CJob@@IEAAXW4BG_JOB_STATE@@@Z; CJob::SetState(BG_JOB_STATE)
0x180041d38  mov     rdx, rbx; struct CJob *
0x180041d3b  call    ?AppendOnline@CJobManager@@QEAAXPEAVCJob@@@Z; CJobManager::AppendOnline(CJob *)
0x180041d40  mov     edx, 2
0x180041d45  mov     rcx, rbx
0x180041d48  call    ?UpdateModificationTime@CJob@@QEAAXW4UpdateBehavior@1@@Z; CJob::UpdateModificationTime(CJob::UpdateBehavior)
0x180041d4d  jmp     short loc_180041D66
0x180041d4f  add     eax, 0FFFFFFF9h
0x180041d52  cmp     eax, 1
0x180041d55  ja      short loc_180041D66
0x180041d57  mov     rdx, rbx; struct CJob *
0x180041d5a  mov     byte ptr [rdi+5B4h], 1
0x180041d61  call    ?AppendOnline@CJobManager@@QEAAXPEAVCJob@@@Z; CJobManager::AppendOnline(CJob *)
0x180041d66  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x180041d6d  add     rcx, 208h; this
0x180041d74  call    ?CompleteWorkItem@TaskScheduler@@AEAAX_N@Z; TaskScheduler::CompleteWorkItem(bool)
0x180041d79  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; this
0x180041d80  call    ?ScheduleAnotherGroup@CJobManager@@QEAAXXZ; CJobManager::ScheduleAnotherGroup(void)
0x180041d85  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x180041d8c  add     rcx, 208h; this
0x180041d93  call    ?UnlockWriter@TaskScheduler@@QEAAXXZ; TaskScheduler::UnlockWriter(void)
0x180041d98  jmp     loc_180041EA6
0x180041d9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180041da4  cmp     rcx, r15
0x180041da7  jz      short loc_180041DC0
0x180041da9  test    [rcx+1Ch], r14d
0x180041dad  jz      short loc_180041DC0
0x180041daf  mov     rcx, [rcx+10h]
0x180041db3  mov     edx, 20h ; ' '
0x180041db8  mov     r8, rbp
0x180041dbb  call    WPP_SF_
0x180041dc0  mov     rdi, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x180041dc7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180041dca  mov     rcx, [rdi+218h]; hHandle
0x180041dd1  call    cs:__imp_WaitForSingleObject
0x180041dd7  mov     ecx, [rdi+23Ch]; dwTlsIndex
0x180041ddd  call    cs:__imp_TlsGetValue
0x180041de3  mov     rbx, rax
0x180041de6  mov     rcx, cs:WPP_GLOBAL_Control
0x180041ded  cmp     rcx, r15
0x180041df0  jz      short loc_180041E0C
0x180041df2  test    byte ptr [rcx+1Ch], 80h
0x180041df6  jz      short loc_180041E0C
0x180041df8  mov     rcx, [rcx+10h]
0x180041dfc  mov     edx, 0Eh
0x180041e01  mov     r9, rax
0x180041e04  mov     r8, rbp
0x180041e07  call    WPP_SF_q
0x180041e0c  test    rbx, rbx
0x180041e0f  jz      loc_180041E99
0x180041e15  mov     ecx, [rdi+23Ch]; dwTlsIndex
0x180041e1b  xor     edx, edx; lpTlsValue
0x180041e1d  call    cs:__imp_TlsSetValue
0x180041e23  mov     rax, [rbx+48h]
0x180041e27  add     rax, 38h ; '8'
0x180041e2b  mov     qword ptr [rbx+58h], 0
0x180041e33  cmp     [rbx+18h], rax
0x180041e37  jnz     short loc_180041E70
0x180041e39  lea     rdx, [rbx+8]
0x180041e3d  cmp     qword ptr [rdx+10h], 0
0x180041e42  jz      short loc_180041E70
0x180041e44  mov     rcx, [rdx+8]
0x180041e48  mov     rax, [rdx]
0x180041e4b  mov     [rcx], rax
0x180041e4e  mov     rax, [rdx+8]
0x180041e52  mov     rcx, [rdx]
0x180041e55  mov     [rcx+8], rax
0x180041e59  mov     rax, [rdx+10h]
0x180041e5d  dec     qword ptr [rax+18h]
0x180041e61  mov     [rdx], rdx
0x180041e64  mov     [rdx+8], rdx
0x180041e68  mov     qword ptr [rdx+10h], 0
0x180041e70  mov     rcx, [rbx+38h]; hEvent
0x180041e74  mov     qword ptr [rbx+48h], 0
0x180041e7c  mov     dword ptr [rbx+50h], 5
0x180041e83  call    cs:__imp_SetEvent
0x180041e89  mov     qword ptr [rbx+30h], 0
0x180041e91  mov     qword ptr [rbx+38h], 0
0x180041e99  mov     rcx, [rdi+218h]; hMutex
0x180041ea0  call    cs:__imp_ReleaseMutex
0x180041ea6  add     rsp, 30h
0x180041eaa  pop     r15
0x180041eac  pop     r14
0x180041eae  pop     rdi
0x180041eaf  pop     rbp
0x180041eb0  pop     rbx
0x180041eb1  retn
```
