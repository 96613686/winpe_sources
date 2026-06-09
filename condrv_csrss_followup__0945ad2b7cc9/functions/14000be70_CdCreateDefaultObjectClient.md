# CdCreateDefaultObjectClient

- ea: `0x14000be70`
- end: `0x14000c0dd`
- name: `CdCreateDefaultObjectClient`
- size: `621`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000ac50`
- `0x14000bb50`
- `0x14000bce0`
- `0x14000be70`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000bfc2`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c059`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c0a5`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c0b4`
- `ntoskrnl!ObfDereferenceObject` at `0x14000bfc2`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c059`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c0a5`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c0b4`
- `ntoskrnl!ObfReferenceObject` at `0x14000bf38`
- `ntoskrnl!ObfReferenceObject` at `0x14000c027`
- `ntoskrnl!ObfReferenceObject` at `0x14000bf38`
- `ntoskrnl!ObfReferenceObject` at `0x14000c027`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000bf07`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000bf07`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000bf19`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000bf19`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000bf4a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c03e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000bf4a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c03e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bf56`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c04a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bf56`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c04a`
- `ntoskrnl!PsIsSystemProcess` at `0x14000bf90`
- `ntoskrnl!PsIsSystemProcess` at `0x14000bf90`
- `ntoskrnl!IofCompleteRequest` at `0x14000bfe2`
- `ntoskrnl!IofCompleteRequest` at `0x14000c07a`
- `ntoskrnl!IofCompleteRequest` at `0x14000bfe2`
- `ntoskrnl!IofCompleteRequest` at `0x14000c07a`

## pseudocode

```c
__int64 __fastcall CdCreateDefaultObjectClient(PIRP Irp, int a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  __int64 v3; // r14
  __int64 RequestorProcess; // r9
  _QWORD *p_Type; // rdi
  __int64 v7; // rbp
  void *v8; // r15
  __int64 Client; // rax
  __int64 v10; // r13
  unsigned int v12; // ebx
  __int64 v13; // [rsp+60h] [rbp+8h] BYREF
  int v14; // [rsp+68h] [rbp+10h]
  PVOID Object; // [rsp+70h] [rbp+18h] BYREF

  v14 = a2;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v3 = 0;
  v13 = 0;
  RequestorProcess = CdpGetRequestorProcess();
  if ( !RequestorProcess )
  {
    v12 = -1073741813;
    goto LABEL_17;
  }
  if ( (*(_DWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 16) & 0xFFEDFE40) != 0 )
  {
    v12 = -1073741790;
    goto LABEL_17;
  }
  p_Type = &CurrentStackLocation->FileObject->RelatedFileObject->Type;
  Object = p_Type;
  if ( p_Type && p_Type[1] == CdDeviceObject && (v7 = p_Type[3]) != 0 && *(__int64 **)v7 == CdServerType )
  {
    ObfReferenceObject(p_Type);
  }
  else
  {
    if ( (int)CdGetProcessConnection(&Object, &v13, Irp, RequestorProcess) < 0 )
    {
      v12 = -1073741816;
      goto LABEL_17;
    }
    v3 = v13;
    p_Type = Object;
    v7 = *(_QWORD *)(v13 + 24);
  }
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(v7 + 40, 0);
  v8 = *(void **)(v7 + 192);
  if ( !v8 )
  {
    ExReleasePushLockSharedEx(v7 + 40, 0);
    KeLeaveCriticalRegion();
    ObfDereferenceObject(p_Type);
    v12 = -1073741436;
LABEL_17:
    Irp->IoStatus.Status = v12;
    Irp->IoStatus.Information = 0;
    IofCompleteRequest(Irp, 0);
    return v12;
  }
  ObfReferenceObject(*(PVOID *)(v7 + 192));
  ExReleasePushLockSharedEx(v7 + 40, 0);
  KeLeaveCriticalRegion();
  Client = CdpAllocateClient();
  v10 = Client;
  if ( !Client )
  {
    ObfDereferenceObject(p_Type);
    ObfDereferenceObject(v8);
    v12 = -1073741670;
    goto LABEL_17;
  }
  *(_QWORD *)(Client + 8) = 0;
  *(_DWORD *)(Client + 16) = v14;
  *(_QWORD *)(Client + 24) = v8;
  if ( v3 )
  {
    if ( (unsigned __int8)PsIsSystemProcess(*(_QWORD *)(v3 + 32)) )
    {
      *(_DWORD *)(v10 + 32) = 1;
      *(_QWORD *)(v10 + 8) = v7;
      _InterlockedIncrement64((volatile signed __int64 *)(v7 + 24));
    }
  }
  CurrentStackLocation->FileObject->FsContext = (PVOID)v10;
  CurrentStackLocation->FileObject->FsContext2 = v8;
  CurrentStackLocation->FileObject->Flags |= 0x10000000u;
  ObfDereferenceObject(p_Type);
  Irp->IoStatus.Status = 0;
  Irp->IoStatus.Information = 0;
  IofCompleteRequest(Irp, 0);
  return 0;
}

```

## disassembly

```asm
0x14000be70  mov     [rsp+arg_18], rbx
0x14000be75  mov     [rsp+arg_8], edx
0x14000be79  push    rbp
0x14000be7a  push    rsi
0x14000be7b  push    rdi
0x14000be7c  push    r12
0x14000be7e  push    r13
0x14000be80  push    r14
0x14000be82  push    r15
0x14000be84  sub     rsp, 20h
0x14000be88  mov     rbx, [rcx+0B8h]
0x14000be8f  xor     r14d, r14d
0x14000be92  mov     [rsp+58h+arg_0], r14
0x14000be97  mov     rsi, rcx
0x14000be9a  call    CdpGetRequestorProcess
0x14000be9f  mov     r9, rax
0x14000bea2  test    rax, rax
0x14000bea5  jz      loc_14000C08D
0x14000beab  mov     rax, [rbx+8]
0x14000beaf  test    dword ptr [rax+10h], 0FFEDFE40h
0x14000beb6  jnz     loc_14000C09B
0x14000bebc  mov     rax, [rbx+30h]
0x14000bec0  mov     rdi, [rax+40h]
0x14000bec4  mov     [rsp+58h+Object], rdi
0x14000bec9  test    rdi, rdi
0x14000becc  jz      short loc_14000BEDF
0x14000bece  mov     rax, cs:CdDeviceObject
0x14000bed5  cmp     [rdi+8], rax
0x14000bed9  jz      loc_14000C006
0x14000bedf  mov     r8, rsi
0x14000bee2  lea     rdx, [rsp+58h+arg_0]
0x14000bee7  lea     rcx, [rsp+58h+Object]
0x14000beec  call    CdGetProcessConnection
0x14000bef1  test    eax, eax
0x14000bef3  js      loc_14000C094
0x14000bef9  mov     r14, [rsp+58h+arg_0]
0x14000befe  mov     rdi, [rsp+58h+Object]
0x14000bf03  mov     rbp, [r14+18h]
0x14000bf07  call    cs:__imp_KeEnterCriticalRegion
0x14000bf0e  nop     dword ptr [rax+rax+00h]
0x14000bf13  xor     edx, edx
0x14000bf15  lea     rcx, [rbp+28h]
0x14000bf19  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000bf20  nop     dword ptr [rax+rax+00h]
0x14000bf25  mov     r15, [rbp+0C0h]
0x14000bf2c  test    r15, r15
0x14000bf2f  jz      loc_14000C038
0x14000bf35  mov     rcx, r15; Object
0x14000bf38  call    cs:__imp_ObfReferenceObject
0x14000bf3f  nop     dword ptr [rax+rax+00h]
0x14000bf44  xor     edx, edx
0x14000bf46  lea     rcx, [rbp+28h]
0x14000bf4a  call    cs:__imp_ExReleasePushLockSharedEx
0x14000bf51  nop     dword ptr [rax+rax+00h]
0x14000bf56  call    cs:__imp_KeLeaveCriticalRegion
0x14000bf5d  nop     dword ptr [rax+rax+00h]
0x14000bf62  call    CdpAllocateClient
0x14000bf67  mov     r13, rax
0x14000bf6a  test    rax, rax
0x14000bf6d  jz      loc_14000C0A2
0x14000bf73  mov     qword ptr [rax+8], 0
0x14000bf7b  mov     eax, [rsp+58h+arg_8]
0x14000bf7f  mov     [r13+10h], eax
0x14000bf83  mov     [r13+18h], r15
0x14000bf87  test    r14, r14
0x14000bf8a  jz      short loc_14000BFA4
0x14000bf8c  mov     rcx, [r14+20h]
0x14000bf90  call    cs:__imp_PsIsSystemProcess
0x14000bf97  nop     dword ptr [rax+rax+00h]
0x14000bf9c  test    al, al
0x14000bf9e  jnz     loc_14000C0C7
0x14000bfa4  mov     rax, [rbx+30h]
0x14000bfa8  mov     rcx, rdi; Object
0x14000bfab  mov     [rax+18h], r13
0x14000bfaf  mov     rax, [rbx+30h]
0x14000bfb3  mov     [rax+20h], r15
0x14000bfb7  mov     rax, [rbx+30h]
0x14000bfbb  or      dword ptr [rax+50h], 10000000h
0x14000bfc2  call    cs:__imp_ObfDereferenceObject
0x14000bfc9  nop     dword ptr [rax+rax+00h]
0x14000bfce  xor     edx, edx; PriorityBoost
0x14000bfd0  mov     dword ptr [rsi+30h], 0
0x14000bfd7  mov     rcx, rsi; Irp
0x14000bfda  mov     qword ptr [rsi+38h], 0
0x14000bfe2  call    cs:__imp_IofCompleteRequest
0x14000bfe9  nop     dword ptr [rax+rax+00h]
0x14000bfee  xor     eax, eax
0x14000bff0  mov     rbx, [rsp+58h+arg_18]
0x14000bff5  add     rsp, 20h
0x14000bff9  pop     r15
0x14000bffb  pop     r14
0x14000bffd  pop     r13
0x14000bfff  pop     r12
0x14000c001  pop     rdi
0x14000c002  pop     rsi
0x14000c003  pop     rbp
0x14000c004  retn
0x14000c006  mov     rbp, [rdi+18h]
0x14000c00a  test    rbp, rbp
0x14000c00d  jz      loc_14000BEDF
0x14000c013  lea     rax, CdServerType
0x14000c01a  cmp     [rbp+0], rax
0x14000c01e  jnz     loc_14000BEDF
0x14000c024  mov     rcx, rdi; Object
0x14000c027  call    cs:__imp_ObfReferenceObject
0x14000c02e  nop     dword ptr [rax+rax+00h]
0x14000c033  jmp     loc_14000BF07
0x14000c038  xor     edx, edx
0x14000c03a  lea     rcx, [rbp+28h]
0x14000c03e  call    cs:__imp_ExReleasePushLockSharedEx
0x14000c045  nop     dword ptr [rax+rax+00h]
0x14000c04a  call    cs:__imp_KeLeaveCriticalRegion
0x14000c051  nop     dword ptr [rax+rax+00h]
0x14000c056  mov     rcx, rdi; Object
0x14000c059  call    cs:__imp_ObfDereferenceObject
0x14000c060  nop     dword ptr [rax+rax+00h]
0x14000c065  mov     ebx, 0C0000184h
0x14000c06a  xor     edx, edx; PriorityBoost
0x14000c06c  mov     [rsi+30h], ebx
0x14000c06f  mov     rcx, rsi; Irp
0x14000c072  mov     qword ptr [rsi+38h], 0
0x14000c07a  call    cs:__imp_IofCompleteRequest
0x14000c081  nop     dword ptr [rax+rax+00h]
0x14000c086  mov     eax, ebx
0x14000c088  jmp     loc_14000BFF0
0x14000c08d  mov     ebx, 0C000000Bh
0x14000c092  jmp     short loc_14000C06A
0x14000c094  mov     ebx, 0C0000008h
0x14000c099  jmp     short loc_14000C06A
0x14000c09b  mov     ebx, 0C0000022h
0x14000c0a0  jmp     short loc_14000C06A
0x14000c0a2  mov     rcx, rdi; Object
0x14000c0a5  call    cs:__imp_ObfDereferenceObject
0x14000c0ac  nop     dword ptr [rax+rax+00h]
0x14000c0b1  mov     rcx, r15; Object
0x14000c0b4  call    cs:__imp_ObfDereferenceObject
0x14000c0bb  nop     dword ptr [rax+rax+00h]
0x14000c0c0  mov     ebx, 0C000009Ah
0x14000c0c5  jmp     short loc_14000C06A
0x14000c0c7  mov     dword ptr [r13+20h], 1
0x14000c0cf  mov     [r13+8], rbp
0x14000c0d3  lock inc qword ptr [rbp+18h]
0x14000c0d8  jmp     loc_14000BFA4
```
