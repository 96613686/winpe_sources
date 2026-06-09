# DefClockClose

- ea: `0x180036d00`
- end: `0x180036dec`
- name: `DefClockClose`
- size: `236`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800088b0`
- `0x18000b7bc`
- `0x18000ef80`
- `0x18000fc1c`
- `0x180011ba0`
- `0x180036d00`
- `0x180058de0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x180036dcd`
- `ntoskrnl!IofCompleteRequest` at `0x180036dcd`
- `ntoskrnl!ExFreePoolWithTag` at `0x180036db7`
- `ntoskrnl!ExFreePoolWithTag` at `0x180036db7`

## pseudocode

```c
__int64 __fastcall DefClockClose(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  IRP *v3; // rdi
  KSOBJECT_HEADER *FsContext; // rbx

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
    FsContext = (KSOBJECT_HEADER *)CurrentStackLocation->FileObject->FsContext;
    KsSetPowerDispatch(*FsContext, 0, 0);
    KsFreeEventList(
      CurrentStackLocation->FileObject,
      (PLIST_ENTRY)((char *)FsContext[1] + 40),
      KSEVENTS_SPINLOCK,
      (char *)FsContext[1] + 56);
    DefClockKillTimer(FsContext[1], 0);
    DecrementReferenceCount(FsContext[1]);
    KsFreeObjectHeader(*FsContext);
    ExFreePoolWithTag(FsContext, 0);
  }
  v3->IoStatus.Status = 0;
  IofCompleteRequest(v3, 0);
  return 0;
}

```

## disassembly

```asm
0x180036d00  mov     [rsp+arg_0], rbx
0x180036d05  mov     [rsp+arg_8], rsi
0x180036d0a  push    rdi
0x180036d0b  sub     rsp, 30h
0x180036d0f  mov     rsi, [rdx+0B8h]
0x180036d16  mov     rdi, rdx
0x180036d19  cmp     byte ptr [rsi], 12h
0x180036d1c  jnz     short loc_180036D66
0x180036d1e  lea     rax, WPP_RECORDER_INITIALIZED
0x180036d25  xor     ebx, ebx
0x180036d27  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180036d2e  jz      loc_180036DC5
0x180036d34  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d3b  cmp     [rcx+48h], bx
0x180036d3f  jz      loc_180036DC5
0x180036d45  mov     rcx, [rcx+40h]
0x180036d49  lea     rax, WPP_e56f0e3698b9347efe064150fe3dace1_Traceguids
0x180036d50  lea     r9d, [rbx+0Ah]
0x180036d54  mov     [rsp+38h+var_18], rax
0x180036d59  lea     r8d, [rbx+1]
0x180036d5d  mov     dl, 5
0x180036d5f  call    WPP_RECORDER_SF_
0x180036d64  jmp     short loc_180036DC5
0x180036d66  mov     rax, [rsi+30h]
0x180036d6a  xor     r8d, r8d; PowerContext
0x180036d6d  xor     edx, edx; PowerDispatch
0x180036d6f  mov     rbx, [rax+18h]
0x180036d73  mov     rcx, [rbx]; Header
0x180036d76  call    KsSetPowerDispatch
0x180036d7b  mov     rdx, [rbx+8]
0x180036d7f  mov     r8d, 1; EventsFlags
0x180036d85  mov     rcx, [rsi+30h]; FileObject
0x180036d89  lea     r9, [rdx+38h]; EventsLock
0x180036d8d  add     rdx, 28h ; '('; EventsList
0x180036d91  call    KsFreeEventList
0x180036d96  mov     rcx, [rbx+8]
0x180036d9a  xor     edx, edx
0x180036d9c  call    DefClockKillTimer
0x180036da1  mov     rcx, [rbx+8]; P
0x180036da5  call    DecrementReferenceCount
0x180036daa  mov     rcx, [rbx]; Header
0x180036dad  call    KsFreeObjectHeader
0x180036db2  xor     edx, edx; Tag
0x180036db4  mov     rcx, rbx; P
0x180036db7  call    cs:__imp_ExFreePoolWithTag
0x180036dbe  nop     dword ptr [rax+rax+00h]
0x180036dc3  xor     ebx, ebx
0x180036dc5  xor     edx, edx; PriorityBoost
0x180036dc7  mov     [rdi+30h], ebx
0x180036dca  mov     rcx, rdi; Irp
0x180036dcd  call    cs:__imp_IofCompleteRequest
0x180036dd4  nop     dword ptr [rax+rax+00h]
0x180036dd9  mov     rbx, [rsp+38h+arg_0]
0x180036dde  xor     eax, eax
0x180036de0  mov     rsi, [rsp+38h+arg_8]
0x180036de5  add     rsp, 30h
0x180036de9  pop     rdi
0x180036dea  retn
```
