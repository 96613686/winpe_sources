# FatNotifyChangeDirectory

- ea: `0x14002ebb4`
- end: `0x14002ed14`
- name: `FatNotifyChangeDirectory`
- size: `352`
- prototype: `__int64 __fastcall(PVOID Entry, PIRP Irp)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14002e9ac`

## callees

- `0x140007408`
- `0x14002ebb4`
- `0x140038eb4`
- `0x14003d880`
- `0x140044bac`
- `0x1400465f4`
- `0x14004a1d4`

## import_xrefs

- `ntoskrnl!FsRtlNotifyFullChangeDirectory` at `0x14002ecdc`
- `ntoskrnl!FsRtlNotifyFullChangeDirectory` at `0x14002ecdc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002ecf1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ce91`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002ecf1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ce91`
- `ntoskrnl!ExRaiseStatus` at `0x14002ec85`
- `ntoskrnl!ExRaiseStatus` at `0x14002ec85`

## pseudocode

```c
__int64 __fastcall FatNotifyChangeDirectory(_DWORD *Entry, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  __int64 v5; // r8
  __int64 v6; // r9
  ULONG CompletionFilter; // r15d
  BOOLEAN WatchTree; // r14
  __int64 v10; // rdi
  __int64 v11; // r9
  __int64 v12; // [rsp+98h] [rbp+10h] BYREF
  __int64 v13; // [rsp+A0h] [rbp+18h] BYREF
  PVOID FsContext; // [rsp+A8h] [rbp+20h] BYREF

  v13 = 0;
  v12 = 0;
  FsContext = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Entry[17] |= 2u;
  if ( (unsigned int)FatDecodeFileObject(CurrentStackLocation->FileObject, &v13, &v12, &FsContext) == 3 )
  {
    CompletionFilter = CurrentStackLocation->Parameters.Create.Options;
    WatchTree = CurrentStackLocation->Flags & 1;
    v10 = v12;
    if ( (unsigned __int8)FatAcquireExclusiveFcb(Entry, v12, v5, v6) )
    {
      FatVerifyFcb(Entry, v10);
      FatSetFullFileNameInFcb((int)Entry);
      if ( (*(_DWORD *)(v10 + 192) & 1) != 0 )
      {
        Entry[18] = -1073741738;
        ExRaiseStatus(-1073741738);
      }
      FsRtlNotifyFullChangeDirectory(
        *(PNOTIFY_SYNC *)(v13 + 816),
        (PLIST_ENTRY)(v13 + 800),
        FsContext,
        (PSTRING)(v10 + 528),
        WatchTree,
        0,
        CompletionFilter,
        Irp,
        0,
        0);
      ExReleaseResourceLite(*(PERESOURCE *)(v10 + 8));
      FatCompleteRequest_Real(Entry, 0, 0, v11);
      return 259;
    }
    else
    {
      return FatFsdPostRequest(Entry, Irp);
    }
  }
  else
  {
    FatCompleteRequest_Real(Entry, Irp, 3221225485LL, v6);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14002ebb4  mov     rax, rsp
0x14002ebb7  mov     [rax+8], rcx
0x14002ebbb  push    rbx
0x14002ebbc  push    rsi
0x14002ebbd  push    rdi
0x14002ebbe  push    r14
0x14002ebc0  push    r15
0x14002ebc2  sub     rsp, 60h
0x14002ebc6  mov     rsi, rdx
0x14002ebc9  mov     rbx, rcx
0x14002ebcc  mov     qword ptr [rax+18h], 0
0x14002ebd4  mov     qword ptr [rax+10h], 0
0x14002ebdc  mov     qword ptr [rax+20h], 0
0x14002ebe4  mov     rdi, [rdx+0B8h]
0x14002ebeb  or      dword ptr [rcx+44h], 2
0x14002ebef  lea     r9, [rax+20h]
0x14002ebf3  lea     r8, [rax+10h]
0x14002ebf7  lea     rdx, [rax+18h]
0x14002ebfb  mov     rcx, [rdi+30h]
0x14002ebff  call    FatDecodeFileObject
0x14002ec04  mov     rcx, rbx; Entry
0x14002ec07  cmp     eax, 3
0x14002ec0a  jz      short loc_14002EC2B
0x14002ec0c  mov     edi, 0C000000Dh
0x14002ec11  mov     r8d, edi
0x14002ec14  mov     rdx, rsi; Irp
0x14002ec17  call    FatCompleteRequest_Real
0x14002ec1c  mov     eax, edi
0x14002ec1e  add     rsp, 60h
0x14002ec22  pop     r15
0x14002ec24  pop     r14
0x14002ec26  pop     rdi
0x14002ec27  pop     rsi
0x14002ec28  pop     rbx
0x14002ec29  retn
0x14002ec2b  mov     [rsp+88h+var_38], 0
0x14002ec30  mov     r15d, [rdi+10h]
0x14002ec34  mov     r14b, [rdi+2]
0x14002ec38  and     r14b, 1
0x14002ec3c  mov     rdi, [rsp+88h+arg_8]
0x14002ec44  mov     rdx, rdi
0x14002ec47  call    FatAcquireExclusiveFcb
0x14002ec4c  test    al, al
0x14002ec4e  jnz     short loc_14002EC5D
0x14002ec50  mov     rdx, rsi; Context2
0x14002ec53  mov     rcx, rbx; Context1
0x14002ec56  call    FatFsdPostRequest
0x14002ec5b  jmp     short loc_14002EC1E
0x14002ec5d  mov     rdx, rdi
0x14002ec60  mov     rcx, rbx
0x14002ec63  call    FatVerifyFcb
0x14002ec68  mov     rdx, rdi
0x14002ec6b  mov     rcx, rbx; int
0x14002ec6e  call    FatSetFullFileNameInFcb
0x14002ec73  mov     eax, [rdi+0C0h]
0x14002ec79  test    al, 1
0x14002ec7b  jz      short loc_14002EC91
0x14002ec7d  mov     ecx, 0C0000056h; Status
0x14002ec82  mov     [rbx+48h], ecx
0x14002ec85  call    cs:__imp_ExRaiseStatus
0x14002ec91  lea     r9, [rdi+210h]; FullDirectoryName
0x14002ec98  mov     rcx, [rsp+88h+arg_10]
0x14002eca0  lea     rdx, [rcx+320h]; NotifyList
0x14002eca7  mov     [rsp+88h+SubjectContext], 0; SubjectContext
0x14002ecb0  mov     [rsp+88h+TraverseCallback], 0; TraverseCallback
0x14002ecb9  mov     [rsp+88h+NotifyIrp], rsi; NotifyIrp
0x14002ecbe  mov     [rsp+88h+CompletionFilter], r15d; CompletionFilter
0x14002ecc3  mov     [rsp+88h+IgnoreBuffer], 0; IgnoreBuffer
0x14002ecc8  mov     [rsp+88h+WatchTree], r14b; WatchTree
0x14002eccd  mov     r8, [rsp+88h+FsContext]; FsContext
0x14002ecd5  mov     rcx, [rcx+330h]; NotifySync
0x14002ecdc  call    cs:__imp_FsRtlNotifyFullChangeDirectory
0x14002ece3  nop     dword ptr [rax+rax+00h]
0x14002ece8  mov     [rsp+88h+var_38], 1
0x14002eced  mov     rcx, [rdi+8]; Resource
0x14002ecf1  call    cs:__imp_ExReleaseResourceLite
0x14002ecf8  nop     dword ptr [rax+rax+00h]
0x14002ecfd  xor     r8d, r8d
0x14002ed00  xor     edx, edx; Irp
0x14002ed02  mov     rcx, rbx; Entry
0x14002ed05  call    FatCompleteRequest_Real
0x14002ed0a  mov     eax, 103h
0x14002ed0f  jmp     loc_14002EC1E
0x14005ce7d  push    rbp
0x14005ce7f  sub     rsp, 50h
0x14005ce83  mov     rbp, rdx
0x14005ce86  mov     rcx, [rbp+98h]
0x14005ce8d  mov     rcx, [rcx+8]; Resource
0x14005ce91  call    cs:__imp_ExReleaseResourceLite
0x14005ce98  nop     dword ptr [rax+rax+00h]
0x14005ce9d  cmp     byte ptr [rbp+50h], 0
0x14005cea1  jz      short loc_14005CEB5
0x14005cea3  xor     r8d, r8d
0x14005cea6  xor     edx, edx; Irp
0x14005cea8  mov     rcx, [rbp+90h]; Entry
0x14005ceaf  call    FatCompleteRequest_Real
0x14005ceb4  nop
0x14005ceb5  add     rsp, 50h
0x14005ceb9  pop     rbp
0x14005ceba  retn
```
