# DSS_PreShutdownHandler(void)

- ea: `0x180008360`
- end: `0x1800083b5`
- name: `?DSS_PreShutdownHandler@@YAKXZ`
- size: `85`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180008360`
- `0x1800083c0`
- `0x18000bbb8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180008390`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180008390`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180008399`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180008399`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000837f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000837f`

## pseudocode

```c
__int64 DSS_PreShutdownHandler(void)
{
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v1; // rbx

  SvcFrameworkUpdateServiceStatus(3u, 0, 0);
  ThreadpoolWork = CreateThreadpoolWork(DSS_PreShutdownHandler_Worker, 0, 0);
  v1 = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    SubmitThreadpoolWork(ThreadpoolWork);
    CloseThreadpoolWork(v1);
  }
  else
  {
    DSS_PreShutdownHandler_Worker(0, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180008360  push    rbx
0x180008362  sub     rsp, 20h
0x180008366  xor     edx, edx; unsigned int
0x180008368  xor     r8d, r8d; unsigned int
0x18000836b  lea     ecx, [rdx+3]; unsigned int
0x18000836e  call    ?SvcFrameworkUpdateServiceStatus@@YAJKKK@Z; SvcFrameworkUpdateServiceStatus(ulong,ulong,ulong)
0x180008373  xor     r8d, r8d; pcbe
0x180008376  lea     rcx, ?DSS_PreShutdownHandler_Worker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000837d  xor     edx, edx; pv
0x18000837f  call    cs:__imp_CreateThreadpoolWork
0x180008385  mov     rbx, rax
0x180008388  test    rax, rax
0x18000838b  jz      short loc_1800083A1
0x18000838d  mov     rcx, rax; pwk
0x180008390  call    cs:__imp_SubmitThreadpoolWork
0x180008396  mov     rcx, rbx; pwk
0x180008399  call    cs:__imp_CloseThreadpoolWork
0x18000839f  jmp     short loc_1800083AD
0x1800083a1  xor     r8d, r8d; Work
0x1800083a4  xor     edx, edx; Context
0x1800083a6  xor     ecx, ecx; Instance
0x1800083a8  call    ?DSS_PreShutdownHandler_Worker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; DSS_PreShutdownHandler_Worker(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x1800083ad  xor     eax, eax
0x1800083af  add     rsp, 20h
0x1800083b3  pop     rbx
0x1800083b4  retn
```
