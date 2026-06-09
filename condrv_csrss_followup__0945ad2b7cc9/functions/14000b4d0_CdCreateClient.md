# CdCreateClient

- ea: `0x14000b4d0`
- end: `0x14000b80f`
- name: `CdCreateClient`
- size: `831`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x14000a5e0`
- `0x14000ac50`
- `0x14000afd0`
- `0x14000b4d0`
- `0x14000bb50`
- `0x14000bb80`
- `0x14000bc70`
- `0x14000bce0`
- `0x14000bd30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000b530`
- `ntoskrnl!ExAllocatePool2` at `0x14000b530`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b74f`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b7f7`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b74f`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b7f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b79d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b79d`
- `ntoskrnl!ObfReferenceObject` at `0x14000b68e`
- `ntoskrnl!ObfReferenceObject` at `0x14000b68e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b56d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b56d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000b58b`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000b58b`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000b5a8`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000b5a8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b5b4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b5b4`
- `ntoskrnl!PsIsSystemProcess` at `0x14000b6a6`
- `ntoskrnl!PsIsSystemProcess` at `0x14000b6a6`
- `ntoskrnl!IoAllocateMdl` at `0x14000b615`
- `ntoskrnl!IoAllocateMdl` at `0x14000b615`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000b630`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000b630`
- `ntoskrnl!IofCompleteRequest` at `0x14000b7ba`
- `ntoskrnl!IofCompleteRequest` at `0x14000b7ba`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x14000b72d`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x14000b72d`

## pseudocode

```c
__int64 __fastcall CdCreateClient(PIRP Irp, unsigned int a2)
{
  struct _UNICODE_STRING *v2; // r15
  _DWORD *v4; // r13
  struct _MDL *v5; // r14
  __int64 RequestorProcess; // rbx
  _DWORD *Pool2; // rsi
  NTSTATUS ProcessConnection; // ebx
  _QWORD *v9; // rbp
  __int64 v10; // rcx
  void *v11; // r12
  int ShareAccess; // eax
  struct _MDL *Mdl; // rax
  __int64 Client; // rax
  struct _IO_STACK_LOCATION *v15; // rax
  struct _IO_STACK_LOCATION *v16; // rcx
  __int64 v17; // rax
  struct _LIST_ENTRY *v18; // rdx
  struct _MDL *v20; // [rsp+30h] [rbp-48h] BYREF
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+80h] [rbp+8h]
  PVOID Object; // [rsp+90h] [rbp+18h] BYREF
  _QWORD *v23; // [rsp+98h] [rbp+20h] BYREF

  v2 = (struct _UNICODE_STRING *)a2;
  v23 = 0;
  v20 = 0;
  v4 = 0;
  Object = 0;
  v5 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  RequestorProcess = CdpGetRequestorProcess(Irp);
  if ( RequestorProcess )
  {
    Pool2 = (_DWORD *)ExAllocatePool2(65, 24, 1665360963);
    if ( Pool2 )
    {
      ProcessConnection = CdGetProcessConnection(&Object, &v23, Irp, RequestorProcess);
      if ( ProcessConnection >= 0 )
      {
        KeEnterCriticalRegion();
        v9 = v23;
        ExAcquirePushLockSharedEx(v23[3] + 40LL, 0);
        v10 = v9[3];
        v11 = *(void **)(v10 + 192);
        ExReleasePushLockSharedEx(v10 + 40, 0);
        KeLeaveCriticalRegion();
        if ( !v11 )
        {
          ProcessConnection = -1073741436;
          goto LABEL_16;
        }
        Pool2[2] = (_DWORD)v2;
        if ( (_DWORD)v2 == 3 )
          ShareAccess = CurrentStackLocation->Parameters.Create.ShareAccess;
        else
          ShareAccess = 3;
        Pool2[3] = ShareAccess;
        ProcessConnection = CdpConvertClientDesiredAccess(
                              Pool2 + 4,
                              *(unsigned int *)(CurrentStackLocation->Parameters.WMI.ProviderId + 16));
        if ( ProcessConnection < 0 )
          goto LABEL_16;
        Mdl = IoAllocateMdl(Pool2 + 2, 0xCu, 0, 1u, 0);
        v5 = Mdl;
        if ( !Mdl )
          goto LABEL_27;
        MmBuildMdlForNonPagedPool(Mdl);
        ProcessConnection = CdAllocateMdlForEaBufferItem(&v20, Irp, qword_140004220);
        if ( ProcessConnection < 0 )
          goto LABEL_16;
        v5->Next = v20;
        Client = CdpAllocateClient();
        v4 = (_DWORD *)Client;
        if ( Client )
        {
          *(_QWORD *)Pool2 = Client;
          *(_QWORD *)(Client + 8) = v9[3];
          _InterlockedIncrement64((volatile signed __int64 *)(v9[3] + 24LL));
          *(_QWORD *)(Client + 24) = v11;
          ObfReferenceObject(v11);
          v4[8] = 2;
          if ( (unsigned __int8)PsIsSystemProcess(v9[4]) )
            v4[8] |= 1u;
          CurrentStackLocation->FileObject->FsContext = v4;
          CurrentStackLocation->FileObject->FsContext2 = v11;
          CurrentStackLocation->FileObject->Flags |= 0x10000000u;
          v15 = Irp->Tail.Overlay.CurrentStackLocation;
          v15[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&CdpCompleteClientCreation;
          v15[-1].Context = Pool2;
          v15[-1].Control = -32;
          v16 = Irp->Tail.Overlay.CurrentStackLocation;
          v17 = v9[3] + 64LL;
          v18 = (struct _LIST_ENTRY *)v9[5];
          *(_WORD *)&v16[-1].MajorFunction = 783;
          v16[-1].Parameters.WMI.ProviderId = v17;
          v16[-1].Parameters.QueryDirectory.FileName = v2;
          v16[-1].Parameters.Read.ByteOffset.QuadPart = (LONGLONG)v5;
          v16[-1].Parameters.CreatePipe.Parameters = 0;
          Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = v18;
          ZwAllocateLocallyUniqueId((PLUID)&Irp->Tail.CompletionKey + 2);
          ProcessConnection = CdAddIoToPipe((__int64)Irp);
          if ( ProcessConnection >= 0 )
          {
            ObfDereferenceObject(Object);
            return 259;
          }
        }
        else
        {
LABEL_27:
          ProcessConnection = -1073741670;
        }
      }
    }
    else
    {
      ProcessConnection = -1073741670;
    }
  }
  else
  {
    Pool2 = 0;
    ProcessConnection = -1073741813;
  }
LABEL_16:
  CdFreeMdlChain(v5);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  if ( v4 )
    CdpFreeClient(v4);
  Irp->IoStatus.Status = ProcessConnection;
  Irp->IoStatus.Information = 0;
  IofCompleteRequest(Irp, 0);
  return (unsigned int)ProcessConnection;
}

```

## disassembly

```asm
0x14000b4d0  mov     rax, rsp
0x14000b4d3  mov     [rax+10h], rbx
0x14000b4d7  push    rbp
0x14000b4d8  push    rsi
0x14000b4d9  push    rdi
0x14000b4da  push    r12
0x14000b4dc  push    r13
0x14000b4de  push    r14
0x14000b4e0  push    r15
0x14000b4e2  sub     rsp, 40h
0x14000b4e6  xor     ebp, ebp
0x14000b4e8  mov     r15d, edx
0x14000b4eb  mov     [rax+20h], rbp
0x14000b4ef  mov     rdi, rcx
0x14000b4f2  mov     [rax-48h], rbp
0x14000b4f6  mov     r13d, ebp
0x14000b4f9  mov     [rax+18h], rbp
0x14000b4fd  mov     r14d, ebp
0x14000b500  mov     rax, [rcx+0B8h]
0x14000b507  mov     [rsp+78h+arg_0], rax
0x14000b50f  call    CdpGetRequestorProcess
0x14000b514  mov     rbx, rax
0x14000b517  test    rax, rax
0x14000b51a  jz      loc_14000B7DC
0x14000b520  mov     edx, 18h
0x14000b525  mov     ecx, 41h ; 'A'
0x14000b52a  mov     r8d, 63436443h
0x14000b530  call    cs:__imp_ExAllocatePool2
0x14000b537  nop     dword ptr [rax+rax+00h]
0x14000b53c  mov     rsi, rax
0x14000b53f  test    rax, rax
0x14000b542  jz      loc_14000B779
0x14000b548  mov     r9, rbx
0x14000b54b  lea     rdx, [rsp+78h+arg_18]
0x14000b553  mov     r8, rdi
0x14000b556  lea     rcx, [rsp+78h+Object]
0x14000b55e  call    CdGetProcessConnection
0x14000b563  mov     ebx, eax
0x14000b565  test    eax, eax
0x14000b567  js      loc_14000B77E
0x14000b56d  call    cs:__imp_KeEnterCriticalRegion
0x14000b574  nop     dword ptr [rax+rax+00h]
0x14000b579  mov     rbp, [rsp+78h+arg_18]
0x14000b581  xor     edx, edx
0x14000b583  mov     rcx, [rbp+18h]
0x14000b587  add     rcx, 28h ; '('
0x14000b58b  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000b592  nop     dword ptr [rax+rax+00h]
0x14000b597  mov     rcx, [rbp+18h]
0x14000b59b  xor     edx, edx
0x14000b59d  mov     r12, [rcx+0C0h]
0x14000b5a4  add     rcx, 28h ; '('
0x14000b5a8  call    cs:__imp_ExReleasePushLockSharedEx
0x14000b5af  nop     dword ptr [rax+rax+00h]
0x14000b5b4  call    cs:__imp_KeLeaveCriticalRegion
0x14000b5bb  nop     dword ptr [rax+rax+00h]
0x14000b5c0  test    r12, r12
0x14000b5c3  jz      loc_14000B7CA
0x14000b5c9  mov     rdx, [rsp+78h+arg_0]
0x14000b5d1  mov     [rsi+8], r15d
0x14000b5d5  cmp     r15d, 3
0x14000b5d9  jz      loc_14000B7D3
0x14000b5df  mov     eax, 3
0x14000b5e4  mov     [rsi+0Ch], eax
0x14000b5e7  lea     rcx, [rsi+10h]
0x14000b5eb  mov     rdx, [rdx+8]
0x14000b5ef  mov     edx, [rdx+10h]
0x14000b5f2  call    CdpConvertClientDesiredAccess
0x14000b5f7  mov     ebx, eax
0x14000b5f9  test    eax, eax
0x14000b5fb  js      loc_14000B7CF
0x14000b601  mov     r9b, 1; ChargeQuota
0x14000b604  mov     [rsp+78h+Irp], r13; Irp
0x14000b609  xor     r8d, r8d; SecondaryBuffer
0x14000b60c  lea     rcx, [rsi+8]; VirtualAddress
0x14000b610  mov     edx, 0Ch; Length
0x14000b615  call    cs:__imp_IoAllocateMdl
0x14000b61c  nop     dword ptr [rax+rax+00h]
0x14000b621  mov     r14, rax
0x14000b624  test    rax, rax
0x14000b627  jz      loc_14000B7F0
0x14000b62d  mov     rcx, rax; MemoryDescriptorList
0x14000b630  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14000b637  nop     dword ptr [rax+rax+00h]
0x14000b63c  lea     r8, qword_140004220
0x14000b643  mov     rdx, rdi
0x14000b646  lea     rcx, [rsp+78h+var_48]
0x14000b64b  call    CdAllocateMdlForEaBufferItem
0x14000b650  mov     ebx, eax
0x14000b652  test    eax, eax
0x14000b654  js      loc_14000B7CF
0x14000b65a  mov     rax, [rsp+78h+var_48]
0x14000b65f  mov     [r14], rax
0x14000b662  call    CdpAllocateClient
0x14000b667  mov     r13, rax
0x14000b66a  test    rax, rax
0x14000b66d  jz      loc_14000B7F0
0x14000b673  mov     [rsi], rax
0x14000b676  mov     rax, [rbp+18h]
0x14000b67a  mov     [r13+8], rax
0x14000b67e  mov     rax, [rbp+18h]
0x14000b682  lock inc qword ptr [rax+18h]
0x14000b687  mov     rcx, r12; Object
0x14000b68a  mov     [r13+18h], r12
0x14000b68e  call    cs:__imp_ObfReferenceObject
0x14000b695  nop     dword ptr [rax+rax+00h]
0x14000b69a  mov     dword ptr [r13+20h], 2
0x14000b6a2  mov     rcx, [rbp+20h]
0x14000b6a6  call    cs:__imp_PsIsSystemProcess
0x14000b6ad  nop     dword ptr [rax+rax+00h]
0x14000b6b2  test    al, al
0x14000b6b4  jnz     loc_14000B7E6
0x14000b6ba  mov     rcx, [rsp+78h+arg_0]
0x14000b6c2  mov     rax, [rcx+30h]
0x14000b6c6  mov     [rax+18h], r13
0x14000b6ca  mov     rax, [rcx+30h]
0x14000b6ce  mov     [rax+20h], r12
0x14000b6d2  mov     rax, [rcx+30h]
0x14000b6d6  lea     rcx, CdpCompleteClientCreation
0x14000b6dd  or      dword ptr [rax+50h], 10000000h
0x14000b6e4  mov     rax, [rdi+0B8h]
0x14000b6eb  mov     [rax-10h], rcx
0x14000b6ef  mov     [rax-8], rsi
0x14000b6f3  mov     byte ptr [rax-45h], 0E0h
0x14000b6f7  mov     rax, [rbp+18h]
0x14000b6fb  mov     rcx, [rdi+0B8h]
0x14000b702  add     rax, 40h ; '@'
0x14000b706  mov     rdx, [rbp+28h]
0x14000b70a  xor     ebp, ebp
0x14000b70c  mov     word ptr [rcx-48h], 30Fh
0x14000b712  mov     [rcx-40h], rax
0x14000b716  mov     [rcx-38h], r15
0x14000b71a  mov     [rcx-30h], r14
0x14000b71e  mov     [rcx-28h], rbp
0x14000b722  lea     rcx, [rdi+88h]; Luid
0x14000b729  mov     [rdi+78h], rdx
0x14000b72d  call    cs:__imp_ZwAllocateLocallyUniqueId
0x14000b734  nop     dword ptr [rax+rax+00h]
0x14000b739  mov     rcx, rdi
0x14000b73c  call    CdAddIoToPipe
0x14000b741  mov     ebx, eax
0x14000b743  test    eax, eax
0x14000b745  js      short loc_14000B77E
0x14000b747  mov     rcx, [rsp+78h+Object]; Object
0x14000b74f  call    cs:__imp_ObfDereferenceObject
0x14000b756  nop     dword ptr [rax+rax+00h]
0x14000b75b  mov     eax, 103h
0x14000b760  mov     rbx, [rsp+78h+arg_8]
0x14000b768  add     rsp, 40h
0x14000b76c  pop     r15
0x14000b76e  pop     r14
0x14000b770  pop     r13
0x14000b772  pop     r12
0x14000b774  pop     rdi
0x14000b775  pop     rsi
0x14000b776  pop     rbp
0x14000b777  retn
0x14000b779  mov     ebx, 0C000009Ah
0x14000b77e  mov     rcx, r14; Mdl
0x14000b781  call    CdFreeMdlChain
0x14000b786  mov     rcx, [rsp+78h+Object]; Object
0x14000b78e  test    rcx, rcx
0x14000b791  jnz     short loc_14000B7F7
0x14000b793  test    rsi, rsi
0x14000b796  jz      short loc_14000B7A9
0x14000b798  xor     edx, edx; Tag
0x14000b79a  mov     rcx, rsi; P
0x14000b79d  call    cs:__imp_ExFreePoolWithTag
0x14000b7a4  nop     dword ptr [rax+rax+00h]
0x14000b7a9  test    r13, r13
0x14000b7ac  jnz     short loc_14000B805
0x14000b7ae  xor     edx, edx; PriorityBoost
0x14000b7b0  mov     [rdi+30h], ebx
0x14000b7b3  mov     rcx, rdi; Irp
0x14000b7b6  mov     [rdi+38h], rbp
0x14000b7ba  call    cs:__imp_IofCompleteRequest
0x14000b7c1  nop     dword ptr [rax+rax+00h]
0x14000b7c6  mov     eax, ebx
0x14000b7c8  jmp     short loc_14000B760
0x14000b7ca  mov     ebx, 0C0000184h
0x14000b7cf  xor     ebp, ebp
0x14000b7d1  jmp     short loc_14000B77E
0x14000b7d3  movzx   eax, word ptr [rdx+1Ah]
0x14000b7d7  jmp     loc_14000B5E4
0x14000b7dc  mov     rsi, rbp
0x14000b7df  mov     ebx, 0C000000Bh
0x14000b7e4  jmp     short loc_14000B77E
0x14000b7e6  or      dword ptr [r13+20h], 1
0x14000b7eb  jmp     loc_14000B6BA
0x14000b7f0  mov     ebx, 0C000009Ah
0x14000b7f5  jmp     short loc_14000B7CF
0x14000b7f7  call    cs:__imp_ObfDereferenceObject
0x14000b7fe  nop     dword ptr [rax+rax+00h]
0x14000b803  jmp     short loc_14000B793
0x14000b805  mov     rcx, r13; P
0x14000b808  call    CdpFreeClient
0x14000b80d  jmp     short loc_14000B7AE
```
