# VctDisconnectAndDereferenceEndpoint

- ea: `0x140038158`
- end: `0x140038224`
- name: `VctDisconnectAndDereferenceEndpoint`
- size: `204`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `5`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140002270`
- `0x14002d150`
- `0x140031940`
- `0x140038770`
- `0x14003fbb0`

## callees

- `0x1400125e0`
- `0x140013470`
- `0x1400215b0`
- `0x140038158`
- `0x1400383d0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14003819b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003819b`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003818a`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003818a`
- `rdbss!RxGetRDBSSProcess` at `0x14003817b`
- `rdbss!RxGetRDBSSProcess` at `0x14003817b`
- `rdbss!RxDispatchToWorkerThread` at `0x140038200`
- `rdbss!RxDispatchToWorkerThread` at `0x140038200`

## pseudocode

```c
void __fastcall VctDisconnectAndDereferenceEndpoint(PRDBSS_DEVICE_OBJECT *pContext, char a2)
{
  struct _KPROCESS *RDBSSProcess; // rbx

  if ( (unsigned int)VctSetEndpointState((__int64)pContext, 1, a2) == 1 )
    goto LABEL_10;
  RDBSSProcess = RxGetRDBSSProcess();
  if ( IoGetCurrentProcess() == RDBSSProcess && !KeGetCurrentIrql() )
  {
    VctDisconnectAndDereferenceEndpointWorker(pContext);
    return;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 31, &WPP_39c16dc859303064795977fd63584161_Traceguids, pContext);
  }
  if ( RxDispatchToWorkerThread(pContext[3], BackgroundWorkQueue, VctDisconnectAndDereferenceEndpointWorker, pContext) < 0 )
LABEL_10:
    VctDereferenceEndpoint(pContext);
}

```

## disassembly

```asm
0x140038158  mov     [rsp+arg_0], rbx
0x14003815d  push    rdi
0x14003815e  sub     rsp, 20h
0x140038162  mov     r8b, dl
0x140038165  mov     rdi, rcx
0x140038168  mov     edx, 1
0x14003816d  call    VctSetEndpointState
0x140038172  cmp     eax, 1
0x140038175  jz      loc_140038210
0x14003817b  call    cs:__imp_RxGetRDBSSProcess
0x140038182  nop     dword ptr [rax+rax+00h]
0x140038187  mov     rbx, rax
0x14003818a  call    cs:__imp_IoGetCurrentProcess
0x140038191  nop     dword ptr [rax+rax+00h]
0x140038196  cmp     rax, rbx
0x140038199  jnz     short loc_1400381B5
0x14003819b  call    cs:__imp_KeGetCurrentIrql
0x1400381a2  nop     dword ptr [rax+rax+00h]
0x1400381a7  test    al, al
0x1400381a9  jnz     short loc_1400381B5
0x1400381ab  mov     rcx, rdi; Context
0x1400381ae  call    VctDisconnectAndDereferenceEndpointWorker
0x1400381b3  jmp     short loc_140038218
0x1400381b5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400381bc  lea     rax, WPP_GLOBAL_Control
0x1400381c3  cmp     rcx, rax
0x1400381c6  jz      short loc_1400381ED
0x1400381c8  mov     eax, [rcx+2Ch]
0x1400381cb  test    al, 4
0x1400381cd  jz      short loc_1400381ED
0x1400381cf  cmp     byte ptr [rcx+29h], 4
0x1400381d3  jb      short loc_1400381ED
0x1400381d5  mov     rcx, [rcx+18h]
0x1400381d9  lea     r8, WPP_39c16dc859303064795977fd63584161_Traceguids
0x1400381e0  mov     edx, 1Fh
0x1400381e5  mov     r9, rdi
0x1400381e8  call    WPP_SF_q
0x1400381ed  mov     rcx, [rdi+18h]; pMRxDeviceObject
0x1400381f1  lea     r8, VctDisconnectAndDereferenceEndpointWorker; Routine
0x1400381f8  mov     r9, rdi; pContext
0x1400381fb  mov     edx, 4; WorkQueueType
0x140038200  call    cs:__imp_RxDispatchToWorkerThread
0x140038207  nop     dword ptr [rax+rax+00h]
0x14003820c  test    eax, eax
0x14003820e  jns     short loc_140038218
0x140038210  mov     rcx, rdi; pContext
0x140038213  call    VctDereferenceEndpoint
0x140038218  mov     rbx, [rsp+28h+arg_0]
0x14003821d  add     rsp, 20h
0x140038221  pop     rdi
0x140038222  retn
```
