# WebWorkerThreadProcInner(bool,_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180722c30`
- end: `0x180722e6d`
- name: `?WebWorkerThreadProcInner@@YAX_NPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `573`
- prototype: `void __fastcall(bool, struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)`
- caller_count: `2`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180f1fa30`
- `0x180f1fa80`

## callees

- `0x1800d28e0`
- `0x180364fa0`
- `0x1804e13b4`
- `0x1804e4964`
- `0x1805af914`
- `0x1806f0cd4`
- `0x180722c30`
- `0x1807b8c74`
- `0x180f1f720`
- `0x180f1f9a0`
- `0x180f1facc`
- `0x180f24408`
- `0x180f248c8`
- `0x180f2497c`
- `0x180f24f60`
- `0x180f25940`
- `0x180f2614c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180722de7`
- `KERNEL32!GetLastError` at `0x180722de7`
- `USER32!TranslateMessage` at `0x180722e18`
- `USER32!TranslateMessage` at `0x180722e18`
- `USER32!DispatchMessageW` at `0x180722e22`
- `USER32!DispatchMessageW` at `0x180722e22`
- `USER32!PeekMessageW` at `0x180722e3c`
- `USER32!PeekMessageW` at `0x180722e3c`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180722c5d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180722c6b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180722c77`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180722c81`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180722d6a`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180722c5d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180722c6b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180722c77`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180722c81`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180722d6a`

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
            (unsigned int)&MSHTML_WEBWORKER_START,
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
            (unsigned int)&MSHTML_WEBWORKER_STOP,
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
0x180722c30  mov     rax, rsp
0x180722c33  mov     [rax+20h], r9
0x180722c37  mov     [rax+18h], r8
0x180722c3b  mov     [rax+10h], rdx
0x180722c3f  mov     [rax+8], cl
0x180722c42  push    rbp
0x180722c43  push    rbx
0x180722c44  push    rsi
0x180722c45  push    rdi
0x180722c46  lea     rbp, [rax-5Fh]
0x180722c4a  sub     rsp, 0C8h
0x180722c51  mov     rdi, [rbp+57h+arg_10]
0x180722c55  movaps  xmmword ptr [rax-38h], xmm6
0x180722c59  movups  xmm6, xmmword ptr [rdi+44h]
0x180722c5d  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180722c63  movups  xmm0, xmmword ptr [rax]
0x180722c66  movdqu  [rbp+57h+var_90], xmm0
0x180722c6b  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180722c71  mov     cl, [rax+10h]
0x180722c74  mov     [rbp+57h+var_80], cl
0x180722c77  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180722c7d  movdqu  xmmword ptr [rax], xmm6
0x180722c81  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180722c87  mov     [rbp+57h+var_7C], 1
0x180722c8e  mov     byte ptr [rax+10h], 1
0x180722c92  call    ?_AddRefThreadState@@YAJXZ; _AddRefThreadState(void)
0x180722c97  test    eax, eax
0x180722c99  jnz     loc_180722E48
0x180722c9f  call    ?CreateWorkerWindow@@YAPEAUHWND__@@XZ; CreateWorkerWindow(void)
0x180722ca4  mov     rsi, rax
0x180722ca7  test    rax, rax
0x180722caa  jz      loc_180722DED
0x180722cb0  lea     rcx, [rbp+57h+var_A0]; struct CWorkerGlobalScope **
0x180722cb4  mov     qword ptr [rbp+57h+var_A0.Data1], 0
0x180722cbc  call    ?Create@CWorkerGlobalScope@@SAJPEAPEAV1@@Z; CWorkerGlobalScope::Create(CWorkerGlobalScope * *)
0x180722cc1  test    eax, eax
0x180722cc3  jnz     loc_180722DE7
0x180722cc9  test    byte ptr cs:Microsoft_IEEnableBits+1, 20h
0x180722cd0  mov     rbx, qword ptr [rbp+57h+var_A0.Data1]
0x180722cd4  jz      short loc_180722D00
0x180722cd6  mov     rax, [rdi]
0x180722cd9  lea     rdx, MSHTML_WEBWORKER_START
0x180722ce0  mov     r9d, [rdi+40h]
0x180722ce4  mov     r8, [rdi+38h]
0x180722ce8  mov     [rsp+30h], rax
0x180722ced  mov     [rsp+0E0h+var_B8], rbx
0x180722cf2  mov     qword ptr [rsp+0E0h+wRemoveMsg], 0
0x180722cfb  call    McTemplateU0pqppz_EventWriteTransfer
0x180722d00  mov     r8, rdi; struct WorkerStartStruct *
0x180722d03  mov     rdx, rsi; HWND
0x180722d06  mov     rcx, rbx; this
0x180722d09  call    ?InitScope@CWorkerGlobalScope@@QEAAJPEAUHWND__@@PEAUWorkerStartStruct@@@Z; CWorkerGlobalScope::InitScope(HWND__ *,WorkerStartStruct *)
0x180722d0e  test    eax, eax
0x180722d10  jnz     loc_180722D98
0x180722d16  mov     rdx, [rdi]; unsigned __int16 *
0x180722d19  xor     r8d, r8d; bool
0x180722d1c  mov     rcx, rbx; this
0x180722d1f  call    ?DownloadAndExecuteScript@CWorkerGlobalScope@@QEAAJPEBG_N@Z; CWorkerGlobalScope::DownloadAndExecuteScript(ushort const *,bool)
0x180722d24  test    eax, eax
0x180722d26  jnz     short loc_180722D98
0x180722d28  lea     rcx, [rbp+57h+var_90]; this
0x180722d2c  call    ?Unset@ThreadUserInputIdSetter@@QEAAXXZ; ThreadUserInputIdSetter::Unset(void)
0x180722d31  cmp     [rbp+57h+arg_0], 0
0x180722d35  mov     rcx, rbx
0x180722d38  jz      short loc_180722D47
0x180722d3a  jmp     short loc_180722D5D
0x180722d3c  mov     rcx, rbx; this
0x180722d3f  call    ?ProcessPendingTasks@CWorkerGlobalScope@@QEAAXXZ; CWorkerGlobalScope::ProcessPendingTasks(void)
0x180722d44  mov     rcx, rbx; this
0x180722d47  call    ?WaitForTaskInSta@@YA_NPEAVCWorkerGlobalScope@@@Z; WaitForTaskInSta(CWorkerGlobalScope *)
0x180722d4c  test    al, al
0x180722d4e  jnz     short loc_180722D3C
0x180722d50  jmp     short loc_180722D66
0x180722d52  mov     rcx, rbx; this
0x180722d55  call    ?ProcessPendingTasks@CWorkerGlobalScope@@QEAAXXZ; CWorkerGlobalScope::ProcessPendingTasks(void)
0x180722d5a  mov     rcx, rbx; this
0x180722d5d  call    ?WaitForTaskInAsta@@YA_NPEAVCWorkerGlobalScope@@@Z; WaitForTaskInAsta(CWorkerGlobalScope *)
0x180722d62  test    al, al
0x180722d64  jnz     short loc_180722D52
0x180722d66  mov     [rbp+57h+var_68], 0
0x180722d6a  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180722d70  lea     rdx, [rbp+57h+var_A0]; struct _GUID
0x180722d74  lea     rcx, [rbp+57h+var_78]; this
0x180722d78  movups  xmm0, xmmword ptr [rax+14h]
0x180722d7c  movdqu  xmmword ptr [rbp+57h+var_A0.Data1], xmm0
0x180722d81  call    ?Set@ThreadUserInputIdSetter@@QEAAXU_GUID@@@Z; ThreadUserInputIdSetter::Set(_GUID)
0x180722d86  lea     rcx, [rbp+57h+var_78]; this
0x180722d8a  mov     [rbp+57h+var_64], 3
0x180722d91  call    ?Unset@ThreadUserInputIdSetter@@QEAAXXZ; ThreadUserInputIdSetter::Unset(void)
0x180722d96  jmp     short loc_180722DA2
0x180722d98  mov     dl, 1; bool
0x180722d9a  mov     rcx, rbx; this
0x180722d9d  call    ?CloseScope@CWorkerGlobalScope@@QEAAX_N@Z; CWorkerGlobalScope::CloseScope(bool)
0x180722da2  mov     rcx, rbx; this
0x180722da5  call    ?CleanupScope@CWorkerGlobalScope@@QEAAXXZ; CWorkerGlobalScope::CleanupScope(void)
0x180722daa  mov     rcx, rbx; this
0x180722dad  call    ?Release@CMarkup@@UEAAKXZ; CMarkup::Release(void)
0x180722db2  test    byte ptr cs:Microsoft_IEEnableBits+1, 20h
0x180722db9  jz      short loc_180722DED
0x180722dbb  mov     rax, [rdi]
0x180722dbe  lea     rdx, MSHTML_WEBWORKER_STOP
0x180722dc5  mov     r9d, [rdi+40h]
0x180722dc9  mov     r8, [rdi+38h]
0x180722dcd  mov     [rsp+30h], rax
0x180722dd2  mov     [rsp+0E0h+var_B8], rbx
0x180722dd7  mov     qword ptr [rsp+0E0h+wRemoveMsg], 0
0x180722de0  call    McTemplateU0pqppz_EventWriteTransfer
0x180722de5  jmp     short loc_180722DED
0x180722de7  call    cs:__imp_GetLastError
0x180722ded  mov     rcx, rdi; this
0x180722df0  call    ??_GWorkerStartStruct@@QEAAPEAXI@Z; WorkerStartStruct::`scalar deleting destructor'(uint)
0x180722df5  call    ?_DecrementObjectCount@@YAXXZ; _DecrementObjectCount(void)
0x180722dfa  xorps   xmm0, xmm0
0x180722dfd  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x180722e01  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x180722e05  movups  xmmword ptr [rbp+17h], xmm0
0x180722e09  jmp     short loc_180722E28
0x180722e0b  cmp     [rbp+57h+Msg.message], 8002h
0x180722e12  jnz     short loc_180722E28
0x180722e14  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180722e18  call    cs:__imp_TranslateMessage
0x180722e1e  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180722e22  call    cs:__imp_DispatchMessageW
0x180722e28  xor     r9d, r9d; wMsgFilterMax
0x180722e2b  mov     [rsp+0E0h+wRemoveMsg], 1; wRemoveMsg
0x180722e33  xor     r8d, r8d; wMsgFilterMin
0x180722e36  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180722e3a  xor     edx, edx; hWnd
0x180722e3c  call    cs:__imp_PeekMessageW
0x180722e42  test    eax, eax
0x180722e44  jnz     short loc_180722E0B
0x180722e46  jmp     short loc_180722E50
0x180722e48  mov     rcx, rdi; this
0x180722e4b  call    ??_GWorkerStartStruct@@QEAAPEAXI@Z; WorkerStartStruct::`scalar deleting destructor'(uint)
0x180722e50  lea     rcx, [rbp+57h+var_90]; this
0x180722e54  call    ?Unset@ThreadUserInputIdSetter@@QEAAXXZ; ThreadUserInputIdSetter::Unset(void)
0x180722e59  movaps  xmm6, xmmword ptr [rsp+0B0h]
0x180722e61  add     rsp, 0C8h
0x180722e68  pop     rdi
0x180722e69  pop     rsi
0x180722e6a  pop     rbx
0x180722e6b  pop     rbp
0x180722e6c  retn
```
