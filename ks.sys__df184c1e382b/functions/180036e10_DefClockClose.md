# DefClockClose

- ea: `0x180036e10`
- end: `0x180036efc`
- name: `DefClockClose`
- size: `236`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800088b0`
- `0x18000b7bc`
- `0x18000f670`
- `0x18000fc30`
- `0x180012440`
- `0x180036e10`
- `0x180058f80`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x180036edd`
- `ntoskrnl!IofCompleteRequest` at `0x180036edd`
- `ntoskrnl!ExFreePoolWithTag` at `0x180036ec7`
- `ntoskrnl!ExFreePoolWithTag` at `0x180036ec7`

## pseudocode

```c
__int64 __fastcall DefClockClose(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  IRP *v3; // rdi
  PVOID FsContext; // rbx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v3 = a2;
  if ( CurrentStackLocation->MajorFunction == 18 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        10,
        (__int64)WPP_e56f0e3698b9347efe064150fe3dace1_Traceguids);
    }
  }
  else
  {
    FsContext = CurrentStackLocation->FileObject->FsContext;
    KsSetPowerDispatch(*(KSOBJECT_HEADER *)FsContext, 0, 0);
    KsFreeEventList(
      CurrentStackLocation->FileObject,
      (PLIST_ENTRY)(*((_QWORD *)FsContext + 1) + 40LL),
      KSEVENTS_SPINLOCK,
      (PVOID)(*((_QWORD *)FsContext + 1) + 56LL));
    DefClockKillTimer(*((_QWORD *)FsContext + 1), 0);
    DecrementReferenceCount(*((KSPIN_LOCK **)FsContext + 1));
    KsFreeObjectHeader(*(KSOBJECT_HEADER *)FsContext);
    ExFreePoolWithTag(FsContext, 0);
  }
  v3->IoStatus.Status = 0;
  IofCompleteRequest(v3, 0);
  return 0;
}

```

## disassembly

```asm
0x180036e10  mov     [rsp+arg_0], rbx
0x180036e15  mov     [rsp+arg_8], rsi
0x180036e1a  push    rdi
0x180036e1b  sub     rsp, 30h
0x180036e1f  mov     rsi, [rdx+0B8h]
0x180036e26  mov     rdi, rdx
0x180036e29  cmp     byte ptr [rsi], 12h
0x180036e2c  jnz     short loc_180036E76
0x180036e2e  lea     rax, WPP_RECORDER_INITIALIZED
0x180036e35  xor     ebx, ebx
0x180036e37  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180036e3e  jz      loc_180036ED5
0x180036e44  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e4b  cmp     [rcx+48h], bx
0x180036e4f  jz      loc_180036ED5
0x180036e55  mov     rcx, [rcx+40h]
0x180036e59  lea     rax, WPP_e56f0e3698b9347efe064150fe3dace1_Traceguids
0x180036e60  lea     r9d, [rbx+0Ah]
0x180036e64  mov     [rsp+38h+var_18], rax
0x180036e69  lea     r8d, [rbx+1]
0x180036e6d  mov     dl, 5
0x180036e6f  call    WPP_RECORDER_SF_
0x180036e74  jmp     short loc_180036ED5
0x180036e76  mov     rax, [rsi+30h]
0x180036e7a  xor     r8d, r8d; PowerContext
0x180036e7d  xor     edx, edx; PowerDispatch
0x180036e7f  mov     rbx, [rax+18h]
0x180036e83  mov     rcx, [rbx]; Header
0x180036e86  call    KsSetPowerDispatch
0x180036e8b  mov     rdx, [rbx+8]
0x180036e8f  mov     r8d, 1; EventsFlags
0x180036e95  mov     rcx, [rsi+30h]; FileObject
0x180036e99  lea     r9, [rdx+38h]; EventsLock
0x180036e9d  add     rdx, 28h ; '('; EventsList
0x180036ea1  call    KsFreeEventList
0x180036ea6  mov     rcx, [rbx+8]
0x180036eaa  xor     edx, edx
0x180036eac  call    DefClockKillTimer
0x180036eb1  mov     rcx, [rbx+8]; P
0x180036eb5  call    DecrementReferenceCount
0x180036eba  mov     rcx, [rbx]; Header
0x180036ebd  call    KsFreeObjectHeader
0x180036ec2  xor     edx, edx; Tag
0x180036ec4  mov     rcx, rbx; P
0x180036ec7  call    cs:__imp_ExFreePoolWithTag
0x180036ece  nop     dword ptr [rax+rax+00h]
0x180036ed3  xor     ebx, ebx
0x180036ed5  xor     edx, edx; PriorityBoost
0x180036ed7  mov     [rdi+30h], ebx
0x180036eda  mov     rcx, rdi; Irp
0x180036edd  call    cs:__imp_IofCompleteRequest
0x180036ee4  nop     dword ptr [rax+rax+00h]
0x180036ee9  mov     rbx, [rsp+38h+arg_0]
0x180036eee  xor     eax, eax
0x180036ef0  mov     rsi, [rsp+38h+arg_8]
0x180036ef5  add     rsp, 30h
0x180036ef9  pop     rdi
0x180036efa  retn
```
