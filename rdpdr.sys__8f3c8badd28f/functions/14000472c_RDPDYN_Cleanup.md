# RDPDYN_Cleanup

- ea: `0x14000472c`
- end: `0x140004874`
- name: `RDPDYN_Cleanup`
- size: `328`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002b930`

## callees

- `0x140001d60`
- `0x14000324c`
- `0x14000327c`
- `0x14000472c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000480d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000480d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400047ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004840`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400047ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004840`
- `ntoskrnl!IofCompleteRequest` at `0x1400047fa`
- `ntoskrnl!IofCompleteRequest` at `0x140004858`
- `ntoskrnl!IofCompleteRequest` at `0x1400047fa`
- `ntoskrnl!IofCompleteRequest` at `0x140004858`

## pseudocode

```c
__int64 __fastcall RDPDYN_Cleanup(__int64 a1, IRP *a2)
{
  PFILE_OBJECT FileObject; // rcx
  unsigned int *FsContext; // rsi
  KSPIN_LOCK *Lock; // rcx
  __int64 v6; // r14
  KIRQL v7; // bp
  __int64 v8; // rax
  IRP *v9; // rbx

  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( FileObject )
  {
    FsContext = (unsigned int *)FileObject->FsContext;
    if ( FsContext )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids, *FsContext);
      Lock = (KSPIN_LOCK *)WPP_MAIN_CB.DeviceQueue.Lock;
      if ( WPP_MAIN_CB.DeviceQueue.Lock )
      {
        while ( 1 )
        {
          v7 = KeAcquireSpinLockRaiseToDpc(Lock);
          v8 = RDPEVNTLIST_DequeueRequest((struct tagSESSIONLIST *)WPP_MAIN_CB.DeviceQueue.Lock);
          v9 = (IRP *)v8;
          if ( !v8 )
            break;
          v6 = _InterlockedExchange64((volatile __int64 *)(v8 + 104), 0);
          KeReleaseSpinLock((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock, v7);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids);
          if ( v6 )
          {
            v9->IoStatus.Status = -1073741536;
            v9->IoStatus.Information = 0;
            IofCompleteRequest(v9, 0);
          }
          Lock = (KSPIN_LOCK *)WPP_MAIN_CB.DeviceQueue.Lock;
        }
        KeReleaseSpinLock((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock, v7);
      }
    }
  }
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x14000472c  push    rbx
0x14000472e  push    rbp
0x14000472f  push    rsi
0x140004730  push    rdi
0x140004731  push    r14
0x140004733  push    r15
0x140004735  sub     rsp, 28h
0x140004739  mov     rax, [rdx+0B8h]
0x140004740  mov     rdi, rdx
0x140004743  mov     rcx, [rax+30h]
0x140004747  test    rcx, rcx
0x14000474a  jz      loc_14000484C
0x140004750  mov     rsi, [rcx+18h]
0x140004754  test    rsi, rsi
0x140004757  jz      loc_14000484C
0x14000475d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004764  lea     r15, WPP_GLOBAL_Control
0x14000476b  cmp     rcx, r15
0x14000476e  jz      short loc_14000478E
0x140004770  cmp     byte ptr [rcx+29h], 4
0x140004774  jb      short loc_14000478E
0x140004776  mov     r9d, [rsi]
0x140004779  lea     r8, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids
0x140004780  mov     rcx, [rcx+18h]
0x140004784  mov     edx, 12h
0x140004789  call    WPP_SF_d
0x14000478e  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock
0x140004795  test    rcx, rcx
0x140004798  jz      loc_14000484C
0x14000479e  jmp     short loc_14000480D
0x1400047a0  xor     r14d, r14d
0x1400047a3  xchg    r14, [rbx+68h]
0x1400047a7  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x1400047ae  call    cs:__imp_KeReleaseSpinLock
0x1400047b5  nop     dword ptr [rax+rax+00h]
0x1400047ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400047c1  cmp     rcx, r15
0x1400047c4  jz      short loc_1400047E1
0x1400047c6  cmp     byte ptr [rcx+29h], 4
0x1400047ca  jb      short loc_1400047E1
0x1400047cc  mov     rcx, [rcx+18h]
0x1400047d0  lea     r8, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids
0x1400047d7  mov     edx, 13h
0x1400047dc  call    WPP_SF_
0x1400047e1  test    r14, r14
0x1400047e4  jz      short loc_140004806
0x1400047e6  xor     edx, edx; PriorityBoost
0x1400047e8  mov     dword ptr [rbx+30h], 0C0000120h
0x1400047ef  mov     rcx, rbx; Irp
0x1400047f2  mov     qword ptr [rbx+38h], 0
0x1400047fa  call    cs:__imp_IofCompleteRequest
0x140004801  nop     dword ptr [rax+rax+00h]
0x140004806  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x14000480d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004814  nop     dword ptr [rax+rax+00h]
0x140004819  mov     edx, [rsi]
0x14000481b  mov     bpl, al
0x14000481e  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; struct tagSESSIONLIST *
0x140004825  call    RDPEVNTLIST_DequeueRequest
0x14000482a  mov     rbx, rax
0x14000482d  mov     dl, bpl; NewIrql
0x140004830  test    rax, rax
0x140004833  jnz     loc_1400047A0
0x140004839  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x140004840  call    cs:__imp_KeReleaseSpinLock
0x140004847  nop     dword ptr [rax+rax+00h]
0x14000484c  xor     edx, edx; PriorityBoost
0x14000484e  mov     dword ptr [rdi+30h], 0
0x140004855  mov     rcx, rdi; Irp
0x140004858  call    cs:__imp_IofCompleteRequest
0x14000485f  nop     dword ptr [rax+rax+00h]
0x140004864  xor     eax, eax
0x140004866  add     rsp, 28h
0x14000486a  pop     r15
0x14000486c  pop     r14
0x14000486e  pop     rdi
0x14000486f  pop     rsi
0x140004870  pop     rbp
0x140004871  pop     rbx
0x140004872  retn
```
