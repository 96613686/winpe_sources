# DefAllocatorClose

- ea: `0x180033800`
- end: `0x180033914`
- name: `DefAllocatorClose`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800088b0`
- `0x18000b7bc`
- `0x180019c60`
- `0x180033800`
- `0x180058de0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1800338b5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800338b5`
- `ntoskrnl!IofCompleteRequest` at `0x1800338f5`
- `ntoskrnl!IofCompleteRequest` at `0x1800338f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800338e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800338e1`

## pseudocode

```c
__int64 __fastcall DefAllocatorClose(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  IRP *v3; // rsi
  struct _FILE_OBJECT *FileObject; // rcx
  char *FsContext; // rdi

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
        (__int64)WPP_619c925f2402301ff602733fd3c6e2ba_Traceguids);
    }
  }
  else
  {
    FileObject = CurrentStackLocation->FileObject;
    FsContext = (char *)FileObject->FsContext;
    KsFreeEventList(FileObject, (PLIST_ENTRY)(FsContext + 24), KSEVENTS_SPINLOCK, FsContext + 16);
    *((_DWORD *)FsContext + 53) = 1;
    if ( *((_QWORD *)FsContext + 16) || *((_DWORD *)FsContext + 52) )
      KeWaitForSingleObject(FsContext + 184, Executive, 0, 0, 0);
    (*((void (__fastcall **)(_QWORD))FsContext + 21))(*((_QWORD *)FsContext + 22));
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
0x180033800  mov     [rsp+arg_0], rbx
0x180033805  mov     [rsp+arg_8], rsi
0x18003380a  push    rdi
0x18003380b  sub     rsp, 30h
0x18003380f  mov     rcx, [rdx+0B8h]
0x180033816  mov     rsi, rdx
0x180033819  cmp     byte ptr [rcx], 12h
0x18003381c  jnz     short loc_180033869
0x18003381e  lea     rax, WPP_RECORDER_INITIALIZED
0x180033825  xor     ebx, ebx
0x180033827  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003382e  jz      loc_1800338ED
0x180033834  mov     rcx, cs:WPP_GLOBAL_Control
0x18003383b  cmp     [rcx+48h], bx
0x18003383f  jz      loc_1800338ED
0x180033845  mov     rcx, [rcx+40h]
0x180033849  lea     rax, WPP_619c925f2402301ff602733fd3c6e2ba_Traceguids
0x180033850  lea     r9d, [rbx+0Ah]
0x180033854  mov     [rsp+38h+Timeout], rax
0x180033859  lea     r8d, [rbx+1]
0x18003385d  mov     dl, 5
0x18003385f  call    WPP_RECORDER_SF_
0x180033864  jmp     loc_1800338ED
0x180033869  mov     rcx, [rcx+30h]; FileObject
0x18003386d  mov     r8d, 1; EventsFlags
0x180033873  mov     rdi, [rcx+18h]
0x180033877  lea     r9, [rdi+10h]; EventsLock
0x18003387b  lea     rdx, [rdi+18h]; EventsList
0x18003387f  call    KsFreeEventList
0x180033884  xor     ebx, ebx
0x180033886  mov     dword ptr [rdi+0D4h], 1
0x180033890  cmp     [rdi+80h], rbx
0x180033897  jnz     short loc_1800338A1
0x180033899  cmp     [rdi+0D0h], ebx
0x18003389f  jz      short loc_1800338C1
0x1800338a1  lea     rcx, [rdi+0B8h]; Object
0x1800338a8  mov     [rsp+38h+Timeout], rbx; Timeout
0x1800338ad  xor     r9d, r9d; Alertable
0x1800338b0  xor     r8d, r8d; WaitMode
0x1800338b3  xor     edx, edx; WaitReason
0x1800338b5  call    cs:__imp_KeWaitForSingleObject
0x1800338bc  nop     dword ptr [rax+rax+00h]
0x1800338c1  mov     rax, [rdi+0A8h]
0x1800338c8  mov     rcx, [rdi+0B0h]
0x1800338cf  call    _guard_dispatch_icall
0x1800338d4  mov     rcx, [rdi]; Header
0x1800338d7  call    KsFreeObjectHeader
0x1800338dc  xor     edx, edx; Tag
0x1800338de  mov     rcx, rdi; P
0x1800338e1  call    cs:__imp_ExFreePoolWithTag
0x1800338e8  nop     dword ptr [rax+rax+00h]
0x1800338ed  xor     edx, edx; PriorityBoost
0x1800338ef  mov     [rsi+30h], ebx
0x1800338f2  mov     rcx, rsi; Irp
0x1800338f5  call    cs:__imp_IofCompleteRequest
0x1800338fc  nop     dword ptr [rax+rax+00h]
0x180033901  mov     rbx, [rsp+38h+arg_0]
0x180033906  xor     eax, eax
0x180033908  mov     rsi, [rsp+38h+arg_8]
0x18003390d  add     rsp, 30h
0x180033911  pop     rdi
0x180033912  retn
```
