# CEffectCompilationTask::Cancel_RenderThread(void)

- ea: `0x180242388`
- end: `0x1802423d2`
- name: `?Cancel_RenderThread@CEffectCompilationTask@@AEAAXXZ`
- size: `74`
- prototype: `void __fastcall(CEffectCompilationTask *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18021de34`
- `0x1802344e8`

## callees

- `0x1801a09a0`
- `0x180242388`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1802423a9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1802423a9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18024239f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18024239f`

## pseudocode

```c
void __fastcall CEffectCompilationTask::Cancel_RenderThread(CEffectCompilationTask *this)
{
  struct _TP_WORK *v2; // rcx
  CEffectCompilationService *v3; // rcx

  v2 = (struct _TP_WORK *)*((_QWORD *)this + 8);
  if ( v2 )
  {
    WaitForThreadpoolWorkCallbacks(v2, 1);
    CloseThreadpoolWork(*((PTP_WORK *)this + 8));
    *((_QWORD *)this + 8) = 0;
  }
  v3 = (CEffectCompilationService *)*((_QWORD *)this + 2);
  *((_DWORD *)this + 18) = 1;
  CEffectCompilationService::OnTaskCompleted_AnyThread(v3, this, 1);
}

```

## disassembly

```asm
0x180242388  push    rbx
0x18024238a  sub     rsp, 20h
0x18024238e  mov     rbx, rcx
0x180242391  mov     rcx, [rcx+40h]; pwk
0x180242395  test    rcx, rcx
0x180242398  jz      short loc_1802423B7
0x18024239a  mov     edx, 1; fCancelPendingCallbacks
0x18024239f  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1802423a5  mov     rcx, [rbx+40h]; pwk
0x1802423a9  call    cs:__imp_CloseThreadpoolWork
0x1802423af  mov     qword ptr [rbx+40h], 0
0x1802423b7  mov     rcx, [rbx+10h]; this
0x1802423bb  mov     r8b, 1; bool
0x1802423be  mov     rdx, rbx; struct CEffectCompilationTask *
0x1802423c1  mov     dword ptr [rbx+48h], 1
0x1802423c8  add     rsp, 20h
0x1802423cc  pop     rbx
0x1802423cd  jmp     ?OnTaskCompleted_AnyThread@CEffectCompilationService@@AEAAXPEAVCEffectCompilationTask@@_N@Z; CEffectCompilationService::OnTaskCompleted_AnyThread(CEffectCompilationTask *,bool)
```
