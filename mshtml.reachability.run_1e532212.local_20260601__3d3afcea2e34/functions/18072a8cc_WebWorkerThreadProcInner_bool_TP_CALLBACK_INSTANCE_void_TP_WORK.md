# WebWorkerThreadProcInner(bool,_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18072a8cc`
- end: `0x18072ab40`
- name: `?WebWorkerThreadProcInner@@YAX_NPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `628`
- prototype: `void __fastcall(bool, struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)`
- caller_count: `2`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180f48750`
- `0x180f487a0`

## callees

- `0x18015c6ac`
- `0x1801605c4`
- `0x180267cc4`
- `0x1802dd850`
- `0x180595040`
- `0x1806f64b8`
- `0x18072a8cc`
- `0x1807c4584`
- `0x180f483e0`
- `0x180f486a0`
- `0x180f487ec`
- `0x180f4d6a8`
- `0x180f4dba0`
- `0x180f4dc6c`
- `0x180f4e260`
- `0x180f4ec40`
- `0x180f4f48c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18072aaa1`
- `KERNEL32!GetLastError` at `0x18072aaa1`
- `USER32!TranslateMessage` at `0x18072aad8`
- `USER32!TranslateMessage` at `0x18072aad8`
- `USER32!DispatchMessageW` at `0x18072aae8`
- `USER32!DispatchMessageW` at `0x18072aae8`
- `USER32!PeekMessageW` at `0x18072ab08`
- `USER32!PeekMessageW` at `0x18072ab08`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18072a8f9`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18072a90d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18072a91f`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18072a92f`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18072aa1e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18072a8f9`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18072a90d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18072a91f`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18072a92f`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18072aa1e`

## pseudocode

```c
void __fastcall WebWorkerThreadProcInner(char a1, struct _TP_CALLBACK_INSTANCE *a2, char *a3, struct _TP_WORK *a4)
{
  __int128 v5; // xmm6
  unsigned int v6; // edx
  unsigned int v7; // edx
  HWND WorkerWindow; // rsi
  int v9; // ecx
  CWorkerGlobalScope *v10; // rbx
  struct CWorkerGlobalScope *v11; // rcx
  int v12; // ecx
  struct _GUID v13; // [rsp+48h] [rbp-49h] BYREF
  __int128 v14; // [rsp+58h] [rbp-39h] BYREF
  char v15; // [rsp+68h] [rbp-29h]
  int v16; // [rsp+6Ch] [rbp-25h]
  _BYTE v17[20]; // [rsp+70h] [rbp-21h] BYREF
  int v18; // [rsp+84h] [rbp-Dh]
  MSG Msg; // [rsp+88h] [rbp-9h] BYREF

  v5 = *(_OWORD *)(a3 + 68);
  v14 = *(_OWORD *)GlobalThreadState();
  v15 = *((_BYTE *)GlobalThreadState() + 16);
  *(_OWORD *)GlobalThreadState() = v5;
  v16 = 1;
  *((_BYTE *)GlobalThreadState() + 16) = 1;
  if ( (unsigned int)_AddRefThreadState() )
  {
    WorkerStartStruct::`scalar deleting destructor'((WorkerStartStruct *)a3, v6);
  }
  else
  {
    WorkerWindow = CreateWorkerWindow();
    if ( WorkerWindow )
    {
      *(_QWORD *)&v13.Data1 = 0;
      if ( (unsigned int)CWorkerGlobalScope::Create((struct CWorkerGlobalScope **)&v13) )
      {
        GetLastError();
      }
      else
      {
        v10 = *(CWorkerGlobalScope **)&v13.Data1;
        if ( (Microsoft_IEEnableBits & 0x2000) != 0 )
          McTemplateU0pqppz_EventWriteTransfer(
            v9,
            (unsigned int)MSHTML_WEBWORKER_START,
            *((_QWORD *)a3 + 7),
            *((_DWORD *)a3 + 16),
            0,
            v13.Data1,
            *(_QWORD *)a3);
        if ( (unsigned int)CWorkerGlobalScope::InitScope(v10, WorkerWindow, (struct WorkerStartStruct *)a3)
          || (unsigned int)CWorkerGlobalScope::DownloadAndExecuteScript(v10, *(const unsigned __int16 **)a3, 0) )
        {
          CWorkerGlobalScope::CloseScope(v10, 1);
        }
        else
        {
          ThreadUserInputIdSetter::Unset((ThreadUserInputIdSetter *)&v14);
          v11 = v10;
          if ( a1 )
          {
            while ( WaitForTaskInAsta(v11) )
            {
              CWorkerGlobalScope::ProcessPendingTasks(v10);
              v11 = v10;
            }
          }
          else
          {
            while ( WaitForTaskInSta(v11) )
            {
              CWorkerGlobalScope::ProcessPendingTasks(v10);
              v11 = v10;
            }
          }
          v17[16] = 0;
          v13 = *(struct _GUID *)((char *)GlobalThreadState() + 20);
          ThreadUserInputIdSetter::Set((ThreadUserInputIdSetter *)v17, &v13);
          v18 = 3;
          ThreadUserInputIdSetter::Unset((ThreadUserInputIdSetter *)v17);
        }
        CWorkerGlobalScope::CleanupScope(v10);
        CMarkup::Release(v10);
        if ( (Microsoft_IEEnableBits & 0x2000) != 0 )
          McTemplateU0pqppz_EventWriteTransfer(
            v12,
            (unsigned int)MSHTML_WEBWORKER_STOP,
            *((_QWORD *)a3 + 7),
            *((_DWORD *)a3 + 16),
            0,
            (char)v10,
            *(_QWORD *)a3);
      }
    }
    WorkerStartStruct::`scalar deleting destructor'((WorkerStartStruct *)a3, v7);
    _DecrementObjectCount();
    memset(&Msg, 0, sizeof(Msg));
    while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
    {
      if ( Msg.message == 32770 )
      {
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
      }
    }
  }
  ThreadUserInputIdSetter::Unset((ThreadUserInputIdSetter *)&v14);
}

```

## disassembly

```asm
0x18072a8cc  mov     rax, rsp
0x18072a8cf  mov     [rax+20h], r9
0x18072a8d3  mov     [rax+18h], r8
0x18072a8d7  mov     [rax+10h], rdx
0x18072a8db  mov     [rax+8], cl
0x18072a8de  push    rbp
0x18072a8df  push    rbx
0x18072a8e0  push    rsi
0x18072a8e1  push    rdi
0x18072a8e2  lea     rbp, [rax-5Fh]
0x18072a8e6  sub     rsp, 0C8h
0x18072a8ed  mov     rdi, [rbp+57h+arg_10]
0x18072a8f1  movaps  xmmword ptr [rax-38h], xmm6
0x18072a8f5  movups  xmm6, xmmword ptr [rdi+44h]
0x18072a8f9  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18072a900  nop     dword ptr [rax+rax+00h]
0x18072a905  movups  xmm0, xmmword ptr [rax]
0x18072a908  movdqu  [rbp+57h+var_90], xmm0
0x18072a90d  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18072a914  nop     dword ptr [rax+rax+00h]
0x18072a919  mov     cl, [rax+10h]
0x18072a91c  mov     [rbp+57h+var_80], cl
0x18072a91f  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18072a926  nop     dword ptr [rax+rax+00h]
0x18072a92b  movdqu  xmmword ptr [rax], xmm6
0x18072a92f  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18072a936  nop     dword ptr [rax+rax+00h]
0x18072a93b  mov     [rbp+57h+var_7C], 1
0x18072a942  mov     byte ptr [rax+10h], 1
0x18072a946  call    ?_AddRefThreadState@@YAJXZ; _AddRefThreadState(void)
0x18072a94b  test    eax, eax
0x18072a94d  jnz     loc_18072AB1A
0x18072a953  call    ?CreateWorkerWindow@@YAPEAUHWND__@@XZ; CreateWorkerWindow(void)
0x18072a958  mov     rsi, rax
0x18072a95b  test    rax, rax
0x18072a95e  jz      loc_18072AAAD
0x18072a964  lea     rcx, [rbp+57h+var_A0]; struct CWorkerGlobalScope **
0x18072a968  mov     qword ptr [rbp+57h+var_A0.Data1], 0
0x18072a970  call    ?Create@CWorkerGlobalScope@@SAJPEAPEAV1@@Z; CWorkerGlobalScope::Create(CWorkerGlobalScope * *)
0x18072a975  test    eax, eax
0x18072a977  jnz     loc_18072AAA1
0x18072a97d  test    byte ptr cs:Microsoft_IEEnableBits+1, 20h
0x18072a984  mov     rbx, qword ptr [rbp+57h+var_A0.Data1]
0x18072a988  jz      short loc_18072A9B4
0x18072a98a  mov     rax, [rdi]
0x18072a98d  lea     rdx, MSHTML_WEBWORKER_START
0x18072a994  mov     r9d, [rdi+40h]
0x18072a998  mov     r8, [rdi+38h]
0x18072a99c  mov     [rsp+30h], rax
0x18072a9a1  mov     [rsp+0E0h+var_B8], rbx
0x18072a9a6  mov     qword ptr [rsp+0E0h+wRemoveMsg], 0
0x18072a9af  call    McTemplateU0pqppz_EventWriteTransfer
0x18072a9b4  mov     r8, rdi; struct WorkerStartStruct *
0x18072a9b7  mov     rdx, rsi; HWND
0x18072a9ba  mov     rcx, rbx; this
0x18072a9bd  call    ?InitScope@CWorkerGlobalScope@@QEAAJPEAUHWND__@@PEAUWorkerStartStruct@@@Z; CWorkerGlobalScope::InitScope(HWND__ *,WorkerStartStruct *)
0x18072a9c2  test    eax, eax
0x18072a9c4  jnz     loc_18072AA52
0x18072a9ca  mov     rdx, [rdi]; unsigned __int16 *
0x18072a9cd  xor     r8d, r8d; bool
0x18072a9d0  mov     rcx, rbx; this
0x18072a9d3  call    ?DownloadAndExecuteScript@CWorkerGlobalScope@@QEAAJPEBG_N@Z; CWorkerGlobalScope::DownloadAndExecuteScript(ushort const *,bool)
0x18072a9d8  test    eax, eax
0x18072a9da  jnz     short loc_18072AA52
0x18072a9dc  lea     rcx, [rbp+57h+var_90]; this
0x18072a9e0  call    ?Unset@ThreadUserInputIdSetter@@QEAAXXZ; ThreadUserInputIdSetter::Unset(void)
0x18072a9e5  cmp     [rbp+57h+arg_0], 0
0x18072a9e9  mov     rcx, rbx
0x18072a9ec  jz      short loc_18072A9FB
0x18072a9ee  jmp     short loc_18072AA11
0x18072a9f0  mov     rcx, rbx; this
0x18072a9f3  call    ?ProcessPendingTasks@CWorkerGlobalScope@@QEAAXXZ; CWorkerGlobalScope::ProcessPendingTasks(void)
0x18072a9f8  mov     rcx, rbx; this
0x18072a9fb  call    ?WaitForTaskInSta@@YA_NPEAVCWorkerGlobalScope@@@Z; WaitForTaskInSta(CWorkerGlobalScope *)
0x18072aa00  test    al, al
0x18072aa02  jnz     short loc_18072A9F0
0x18072aa04  jmp     short loc_18072AA1A
0x18072aa06  mov     rcx, rbx; this
0x18072aa09  call    ?ProcessPendingTasks@CWorkerGlobalScope@@QEAAXXZ; CWorkerGlobalScope::ProcessPendingTasks(void)
0x18072aa0e  mov     rcx, rbx; this
0x18072aa11  call    ?WaitForTaskInAsta@@YA_NPEAVCWorkerGlobalScope@@@Z; WaitForTaskInAsta(CWorkerGlobalScope *)
0x18072aa16  test    al, al
0x18072aa18  jnz     short loc_18072AA06
0x18072aa1a  mov     [rbp+57h+var_68], 0
0x18072aa1e  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18072aa25  nop     dword ptr [rax+rax+00h]
0x18072aa2a  lea     rdx, [rbp+57h+var_A0]; struct _GUID
0x18072aa2e  lea     rcx, [rbp+57h+var_78]; this
0x18072aa32  movups  xmm0, xmmword ptr [rax+14h]
0x18072aa36  movdqu  xmmword ptr [rbp+57h+var_A0.Data1], xmm0
0x18072aa3b  call    ?Set@ThreadUserInputIdSetter@@QEAAXU_GUID@@@Z; ThreadUserInputIdSetter::Set(_GUID)
0x18072aa40  lea     rcx, [rbp+57h+var_78]; this
0x18072aa44  mov     [rbp+57h+var_64], 3
0x18072aa4b  call    ?Unset@ThreadUserInputIdSetter@@QEAAXXZ; ThreadUserInputIdSetter::Unset(void)
0x18072aa50  jmp     short loc_18072AA5C
0x18072aa52  mov     dl, 1; bool
0x18072aa54  mov     rcx, rbx; this
0x18072aa57  call    ?CloseScope@CWorkerGlobalScope@@QEAAX_N@Z; CWorkerGlobalScope::CloseScope(bool)
0x18072aa5c  mov     rcx, rbx; this
0x18072aa5f  call    ?CleanupScope@CWorkerGlobalScope@@QEAAXXZ; CWorkerGlobalScope::CleanupScope(void)
0x18072aa64  mov     rcx, rbx; this
0x18072aa67  call    ?Release@CMarkup@@UEAAKXZ; CMarkup::Release(void)
0x18072aa6c  test    byte ptr cs:Microsoft_IEEnableBits+1, 20h
0x18072aa73  jz      short loc_18072AAAD
0x18072aa75  mov     rax, [rdi]
0x18072aa78  lea     rdx, MSHTML_WEBWORKER_STOP
0x18072aa7f  mov     r9d, [rdi+40h]
0x18072aa83  mov     r8, [rdi+38h]
0x18072aa87  mov     [rsp+30h], rax
0x18072aa8c  mov     [rsp+0E0h+var_B8], rbx
0x18072aa91  mov     qword ptr [rsp+0E0h+wRemoveMsg], 0
0x18072aa9a  call    McTemplateU0pqppz_EventWriteTransfer
0x18072aa9f  jmp     short loc_18072AAAD
0x18072aaa1  call    cs:__imp_GetLastError
0x18072aaa8  nop     dword ptr [rax+rax+00h]
0x18072aaad  mov     rcx, rdi; this
0x18072aab0  call    ??_GWorkerStartStruct@@QEAAPEAXI@Z; WorkerStartStruct::`scalar deleting destructor'(uint)
0x18072aab5  call    ?_DecrementObjectCount@@YAXXZ; _DecrementObjectCount(void)
0x18072aaba  xorps   xmm0, xmm0
0x18072aabd  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x18072aac1  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x18072aac5  movups  xmmword ptr [rbp+17h], xmm0
0x18072aac9  jmp     short loc_18072AAF4
0x18072aacb  cmp     [rbp+57h+Msg.message], 8002h
0x18072aad2  jnz     short loc_18072AAF4
0x18072aad4  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18072aad8  call    cs:__imp_TranslateMessage
0x18072aadf  nop     dword ptr [rax+rax+00h]
0x18072aae4  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18072aae8  call    cs:__imp_DispatchMessageW
0x18072aaef  nop     dword ptr [rax+rax+00h]
0x18072aaf4  xor     r9d, r9d; wMsgFilterMax
0x18072aaf7  mov     [rsp+0E0h+wRemoveMsg], 1; wRemoveMsg
0x18072aaff  xor     r8d, r8d; wMsgFilterMin
0x18072ab02  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18072ab06  xor     edx, edx; hWnd
0x18072ab08  call    cs:__imp_PeekMessageW
0x18072ab0f  nop     dword ptr [rax+rax+00h]
0x18072ab14  test    eax, eax
0x18072ab16  jnz     short loc_18072AACB
0x18072ab18  jmp     short loc_18072AB22
0x18072ab1a  mov     rcx, rdi; this
0x18072ab1d  call    ??_GWorkerStartStruct@@QEAAPEAXI@Z; WorkerStartStruct::`scalar deleting destructor'(uint)
0x18072ab22  lea     rcx, [rbp+57h+var_90]; this
0x18072ab26  call    ?Unset@ThreadUserInputIdSetter@@QEAAXXZ; ThreadUserInputIdSetter::Unset(void)
0x18072ab2b  movaps  xmm6, xmmword ptr [rsp+0B0h]
0x18072ab33  add     rsp, 0C8h
0x18072ab3a  pop     rdi
0x18072ab3b  pop     rsi
0x18072ab3c  pop     rbx
0x18072ab3d  pop     rbp
0x18072ab3e  retn
```
