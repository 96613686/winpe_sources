# SmbCeContinueExchange

- ea: `0x1400276f0`
- end: `0x1400277d7`
- name: `SmbCeContinueExchange`
- size: `231`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000f8a0`
- `0x1400312b0`

## callees

- `0x14000c720`
- `0x14000fae0`
- `0x1400276f0`
- `0x14003e14c`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140027718`
- `ntoskrnl!KeGetCurrentIrql` at `0x140027718`
- `rdbss!RxDispatchToWorkerThread` at `0x14002775e`
- `rdbss!RxDispatchToWorkerThread` at `0x14002775e`

## pseudocode

```c
__int64 __fastcall SmbCeContinueExchange(PVOID Context)
{
  NTSTATUS v1; // edi
  __int64 v3; // rdi
  unsigned int v4; // eax

  v1 = 0;
  if ( *(_QWORD *)(*((_QWORD *)Context + 29) + 48LL) )
  {
    v3 = *((_QWORD *)Context + 12);
    _InterlockedIncrement((volatile signed __int32 *)Context + 9);
    if ( KeGetCurrentIrql() >= 2u || *(_DWORD *)(*(_QWORD *)(v3 + 392) + 320LL) == 4 )
    {
      v1 = RxDispatchToWorkerThread(
             *(PRDBSS_DEVICE_OBJECT *)(*((_QWORD *)Context + 9) + 24LL),
             NormalWorkQueue,
             SmbCepContinueExchangeWorker,
             Context);
      if ( v1 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            25,
            WPP_d39beb3e593835eae73483c3886eb046_Traceguids,
            Context,
            v1);
        }
        SmbCeUpdateExchangeStatus(Context, (unsigned int)v1);
        _InterlockedDecrement((volatile signed __int32 *)Context + 9);
      }
    }
    else
    {
      SmbCepContinueExchangeWorker(Context);
      return v4;
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1400276f0  mov     [rsp+arg_8], rbx
0x1400276f5  push    rdi
0x1400276f6  sub     rsp, 30h
0x1400276fa  mov     rax, [rcx+0E8h]
0x140027701  xor     edi, edi
0x140027703  mov     rbx, rcx
0x140027706  cmp     [rax+30h], rdi
0x14002770a  jz      loc_1400277C9
0x140027710  mov     rdi, [rcx+60h]
0x140027714  lock inc dword ptr [rcx+24h]
0x140027718  call    cs:__imp_KeGetCurrentIrql
0x14002771f  nop     dword ptr [rax+rax+00h]
0x140027724  cmp     al, 2
0x140027726  jnb     short loc_140027747
0x140027728  mov     rax, [rdi+188h]
0x14002772f  cmp     dword ptr [rax+140h], 4
0x140027736  jz      short loc_140027747
0x140027738  mov     rcx, rbx; Context
0x14002773b  call    SmbCepContinueExchangeWorker
0x140027740  mov     edi, eax
0x140027742  jmp     loc_1400277C9
0x140027747  mov     rcx, [rbx+48h]
0x14002774b  lea     r8, SmbCepContinueExchangeWorker; Routine
0x140027752  mov     r9, rbx; pContext
0x140027755  mov     edx, 3; WorkQueueType
0x14002775a  mov     rcx, [rcx+18h]; pMRxDeviceObject
0x14002775e  call    cs:__imp_RxDispatchToWorkerThread
0x140027765  nop     dword ptr [rax+rax+00h]
0x14002776a  mov     edi, eax
0x14002776c  test    eax, eax
0x14002776e  jns     short loc_1400277C9
0x140027770  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140027777  lea     rax, WPP_GLOBAL_Control
0x14002777e  cmp     rcx, rax
0x140027781  jz      short loc_1400277AC
0x140027783  mov     eax, [rcx+2Ch]
0x140027786  test    al, 1
0x140027788  jz      short loc_1400277AC
0x14002778a  cmp     byte ptr [rcx+29h], 1
0x14002778e  jb      short loc_1400277AC
0x140027790  mov     rcx, [rcx+18h]
0x140027794  lea     r8, WPP_d39beb3e593835eae73483c3886eb046_Traceguids
0x14002779b  mov     edx, 19h
0x1400277a0  mov     [rsp+38h+var_18], edi
0x1400277a4  mov     r9, rbx
0x1400277a7  call    WPP_SF_qD
0x1400277ac  mov     dword ptr [rsp+38h+arg_0], edi
0x1400277b0  mov     rcx, rbx
0x1400277b3  mov     dword ptr [rsp+38h+arg_0+4], 0
0x1400277bb  mov     rdx, [rsp+38h+arg_0]
0x1400277c0  call    SmbCeUpdateExchangeStatus
0x1400277c5  lock dec dword ptr [rbx+24h]
0x1400277c9  mov     rbx, [rsp+38h+arg_8]
0x1400277ce  mov     eax, edi
0x1400277d0  add     rsp, 30h
0x1400277d4  pop     rdi
0x1400277d5  retn
```
