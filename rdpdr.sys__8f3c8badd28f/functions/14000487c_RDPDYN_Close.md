# RDPDYN_Close

- ea: `0x14000487c`
- end: `0x1400049af`
- name: `RDPDYN_Close`
- size: `307`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002b930`

## callees

- `0x140001d60`
- `0x140001e30`
- `0x14000324c`
- `0x14000487c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000492b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000492b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400048cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000495e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400048cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000495e`
- `ntoskrnl!IofCompleteRequest` at `0x140004918`
- `ntoskrnl!IofCompleteRequest` at `0x140004993`
- `ntoskrnl!IofCompleteRequest` at `0x140004918`
- `ntoskrnl!IofCompleteRequest` at `0x140004993`

## pseudocode

```c
__int64 __fastcall RDPDYN_Close(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  PFILE_OBJECT FileObject; // rsi
  PVOID FsContext; // rsi
  KSPIN_LOCK *Lock; // rcx
  __int64 v7; // r14
  KIRQL v8; // bp
  __int64 v9; // rax
  IRP *v10; // rbx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  if ( FileObject )
  {
    FsContext = FileObject->FsContext;
    if ( FsContext )
    {
      Lock = (KSPIN_LOCK *)WPP_MAIN_CB.DeviceQueue.Lock;
      if ( WPP_MAIN_CB.DeviceQueue.Lock )
      {
        while ( 1 )
        {
          v8 = KeAcquireSpinLockRaiseToDpc(Lock);
          v9 = RDPEVNTLIST_DequeueRequest((struct tagSESSIONLIST *)WPP_MAIN_CB.DeviceQueue.Lock);
          v10 = (IRP *)v9;
          if ( !v9 )
            break;
          v7 = _InterlockedExchange64((volatile __int64 *)(v9 + 104), 0);
          KeReleaseSpinLock((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock, v8);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids);
          if ( v7 )
          {
            v10->IoStatus.Status = -1073741823;
            IofCompleteRequest(v10, 0);
          }
          Lock = (KSPIN_LOCK *)WPP_MAIN_CB.DeviceQueue.Lock;
        }
        KeReleaseSpinLock((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock, v8);
      }
      operator delete(FsContext);
      CurrentStackLocation->FileObject->FsContext = 0;
    }
  }
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 0);
  return 3221225760LL;
}

```

## disassembly

```asm
0x14000487c  push    rbx
0x14000487e  push    rbp
0x14000487f  push    rsi
0x140004880  push    rdi
0x140004881  push    r14
0x140004883  push    r15
0x140004885  sub     rsp, 28h
0x140004889  mov     r15, [rdx+0B8h]
0x140004890  mov     rdi, rdx
0x140004893  mov     rsi, [r15+30h]
0x140004897  test    rsi, rsi
0x14000489a  jz      loc_14000497E
0x1400048a0  mov     rsi, [rsi+18h]
0x1400048a4  test    rsi, rsi
0x1400048a7  jz      loc_14000497E
0x1400048ad  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock
0x1400048b4  test    rcx, rcx
0x1400048b7  jz      loc_14000496A
0x1400048bd  jmp     short loc_14000492B
0x1400048bf  xor     r14d, r14d
0x1400048c2  xchg    r14, [rbx+68h]
0x1400048c6  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x1400048cd  call    cs:__imp_KeReleaseSpinLock
0x1400048d4  nop     dword ptr [rax+rax+00h]
0x1400048d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400048e0  lea     rax, WPP_GLOBAL_Control
0x1400048e7  cmp     rcx, rax
0x1400048ea  jz      short loc_140004907
0x1400048ec  cmp     byte ptr [rcx+29h], 4
0x1400048f0  jb      short loc_140004907
0x1400048f2  mov     rcx, [rcx+18h]
0x1400048f6  lea     r8, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids
0x1400048fd  mov     edx, 11h
0x140004902  call    WPP_SF_
0x140004907  test    r14, r14
0x14000490a  jz      short loc_140004924
0x14000490c  xor     edx, edx; PriorityBoost
0x14000490e  mov     dword ptr [rbx+30h], 0C0000001h
0x140004915  mov     rcx, rbx; Irp
0x140004918  call    cs:__imp_IofCompleteRequest
0x14000491f  nop     dword ptr [rax+rax+00h]
0x140004924  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x14000492b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004932  nop     dword ptr [rax+rax+00h]
0x140004937  mov     edx, [rsi]
0x140004939  mov     bpl, al
0x14000493c  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; struct tagSESSIONLIST *
0x140004943  call    RDPEVNTLIST_DequeueRequest
0x140004948  mov     rbx, rax
0x14000494b  mov     dl, bpl; NewIrql
0x14000494e  test    rax, rax
0x140004951  jnz     loc_1400048BF
0x140004957  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x14000495e  call    cs:__imp_KeReleaseSpinLock
0x140004965  nop     dword ptr [rax+rax+00h]
0x14000496a  mov     rcx, rsi; void *
0x14000496d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004972  mov     rax, [r15+30h]
0x140004976  mov     qword ptr [rax+18h], 0
0x14000497e  mov     ebx, 0C0000120h
0x140004983  mov     qword ptr [rdi+38h], 0
0x14000498b  xor     edx, edx; PriorityBoost
0x14000498d  mov     [rdi+30h], ebx
0x140004990  mov     rcx, rdi; Irp
0x140004993  call    cs:__imp_IofCompleteRequest
0x14000499a  nop     dword ptr [rax+rax+00h]
0x14000499f  mov     eax, ebx
0x1400049a1  add     rsp, 28h
0x1400049a5  pop     r15
0x1400049a7  pop     r14
0x1400049a9  pop     rdi
0x1400049aa  pop     rsi
0x1400049ab  pop     rbp
0x1400049ac  pop     rbx
0x1400049ad  retn
```
