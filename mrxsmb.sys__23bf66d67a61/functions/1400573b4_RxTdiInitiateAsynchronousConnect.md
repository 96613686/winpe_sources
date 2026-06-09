# RxTdiInitiateAsynchronousConnect

- ea: `0x1400573b4`
- end: `0x1400578e2`
- name: `RxTdiInitiateAsynchronousConnect`
- size: `1326`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001cda0`

## callees

- `0x140020f50`
- `0x140028ed4`
- `0x1400370a0`
- `0x14003838c`
- `0x14003e14c`
- `0x14004a910`
- `0x1400572b4`
- `0x1400573b4`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140057829`
- `ntoskrnl!ObfDereferenceObject` at `0x140057829`
- `ntoskrnl!ExAllocatePool2` at `0x14005742f`
- `ntoskrnl!ExAllocatePool2` at `0x14005742f`
- `ntoskrnl!IofCallDriver` at `0x14005772b`
- `ntoskrnl!IofCallDriver` at `0x14005772b`
- `ntoskrnl!ZwCreateFile` at `0x14005757c`
- `ntoskrnl!ZwCreateFile` at `0x14005757c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400575e8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400575e8`
- `ntoskrnl!ZwClose` at `0x140057843`
- `ntoskrnl!ZwClose` at `0x140057843`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005748a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400574a0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005748a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400574a0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140057464`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140057464`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400574f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057592`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005780d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400578a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400574f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057592`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005780d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400578a2`
- `rdbss!RxCeFreeIrp` at `0x1400577e6`
- `rdbss!RxCeFreeIrp` at `0x1400577e6`
- `rdbss!RxCeAllocateIrp` at `0x1400575b2`
- `rdbss!RxCeAllocateIrp` at `0x1400575b2`

## pseudocode

```c
__int64 __fastcall RxTdiInitiateAsynchronousConnect(__int64 a1)
{
  void **v1; // r14
  NTSTATUS v3; // edi
  _DWORD *Pool2; // rax
  char *v5; // r14
  void *v6; // rcx
  void **v7; // r13
  PVOID v8; // rbx
  HANDLE *v9; // r12
  __int64 v10; // rcx
  IRP *Irp; // r15
  PFILE_OBJECT *v12; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v14; // rcx
  __int64 v15; // rcx
  struct _IO_STACK_LOCATION *v16; // rax
  struct _IO_STACK_LOCATION *v17; // rdx
  UNICODE_STRING *v18; // rcx
  struct _IO_STACK_LOCATION *v19; // rax
  NTSTATUS v20; // eax
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  void *v23; // rcx
  void *v24; // rcx
  void *v25; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-9h] BYREF
  ULONG EaLength; // [rsp+E0h] [rbp+67h] BYREF
  void **v30; // [rsp+E8h] [rbp+6Fh] BYREF
  PVOID P; // [rsp+F0h] [rbp+77h] BYREF

  v1 = *(void ***)(a1 + 216);
  v30 = v1;
  memset(&ObjectAttributes, 0, 44);
  P = 0;
  EaLength = 0;
  IoStatusBlock = 0;
  v1[13] = (void *)-1LL;
  v1[14] = 0;
  if ( *(_QWORD *)(a1 + 248) == -1 )
  {
    v3 = -1073741536;
LABEL_50:
    *(_DWORD *)(a1 + 16) = v3;
    *(_DWORD *)(a1 + 20) = 0;
    return (unsigned int)v3;
  }
  Pool2 = (_DWORD *)ExAllocatePool2(66, 4, 1665366098);
  *(_QWORD *)(a1 + 256) = Pool2;
  if ( !Pool2 )
  {
    v3 = -1073741670;
    goto LABEL_50;
  }
  *Pool2 = 1;
  v5 = (char *)v1[4];
  ExAcquirePushLockExclusiveEx(v5 + 64, 0);
  if ( *((_QWORD *)v5 + 14) == -1 )
  {
    v3 = RxTdiInitializeTransportAddress((PRXCE_ADDRESS)v5);
    if ( v3 < 0 )
    {
      ExReleasePushLockExclusiveEx(v5 + 64, 0);
      goto LABEL_50;
    }
  }
  ExReleasePushLockExclusiveEx(v5 + 64, 0);
  v3 = BuildEaBuffer(17, "ConnectionContext", 8, &v30, &P, &EaLength);
  if ( v3 < 0 )
  {
    v6 = *(void **)(a1 + 256);
    if ( v6 )
    {
      ExFreePoolWithTag(v6, 0x63437852u);
      *(_QWORD *)(a1 + 256) = 0;
    }
    goto LABEL_50;
  }
  v7 = v30;
  v8 = P;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = (HANDLE)*((_QWORD *)v5 + 10);
  v9 = v30 + 13;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)RelativeName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = ZwCreateFile(v30 + 13, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 3u, 0, P, EaLength);
  ExFreePoolWithTag(v8, 0x64437852u);
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids,
        (unsigned int)v3);
    }
    v25 = *(void **)(a1 + 256);
    if ( v25 )
    {
      ExFreePoolWithTag(v25, 0x63437852u);
      *(_QWORD *)(a1 + 256) = 0;
    }
    goto LABEL_50;
  }
  v10 = *((_QWORD *)v5 + 9);
  LOBYTE(v10) = *(_BYTE *)(v10 + 76);
  Irp = (IRP *)RxCeAllocateIrp(v10, 0, 0);
  if ( !Irp )
  {
    v3 = -1073741670;
    goto LABEL_38;
  }
  v12 = (PFILE_OBJECT *)(v7 + 14);
  v3 = ObReferenceObjectByHandle(*v9, 0, 0, 0, v7 + 14, 0);
  if ( v3 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_35;
    }
    v22 = 18;
LABEL_34:
    WPP_SF_d(v21->AttachedDevice, v22, WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids, (unsigned int)v3);
    goto LABEL_35;
  }
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].CompletionRoutine = 0;
  CurrentStackLocation[-1].Context = 0;
  CurrentStackLocation[-1].Control = 0;
  v14 = Irp->Tail.Overlay.CurrentStackLocation;
  *(_WORD *)&v14[-1].MajorFunction = 271;
  v14[-1].DeviceObject = (PDEVICE_OBJECT)*((_QWORD *)v5 + 9);
  v14[-1].FileObject = *v12;
  v14[-1].Parameters.WMI.ProviderId = *((_QWORD *)v5 + 14);
  v3 = RxCeSubmitTdiRequest(*((PDEVICE_OBJECT *)v5 + 9), Irp);
  if ( v3 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_35;
    }
    v22 = 17;
    goto LABEL_34;
  }
  v3 = RxTdiSetTlEndpointOptions(v15, *((_QWORD *)v5 + 9), *v12, *(_QWORD *)(*(_QWORD *)(a1 + 8) + 120LL));
  if ( v3 >= 0 )
  {
    v16 = Irp->Tail.Overlay.CurrentStackLocation;
    v16[-1].CompletionRoutine = 0;
    v16[-1].Context = 0;
    v16[-1].Control = 0;
    v17 = Irp->Tail.Overlay.CurrentStackLocation;
    *(_WORD *)&v17[-1].MajorFunction = 783;
    v17[-1].DeviceObject = (PDEVICE_OBJECT)*((_QWORD *)v5 + 9);
    v17[-1].FileObject = *v12;
    v18 = *(UNICODE_STRING **)(*(_QWORD *)(a1 + 8) + 120LL);
    v17[-1].Parameters.CreatePipe.Parameters = (PNAMED_PIPE_CREATE_PARAMETERS)&ConnectionTimeOut;
    v17[-1].Parameters.QueryDirectory.FileName = v18;
    v17[-1].Parameters.Read.ByteOffset.QuadPart = 0;
    v19 = Irp->Tail.Overlay.CurrentStackLocation;
    v19[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&RxTdiAsynchronousConnectCompletion;
    v19[-1].Context = (PVOID)a1;
    v19[-1].Control = -32;
    _InterlockedExchange64((volatile __int64 *)(a1 + 248), (__int64)Irp);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqZ(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        (unsigned int)WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids,
        (_DWORD)Irp,
        *(_QWORD *)(a1 + 8),
        (__int64)(v5 + 32));
    }
    v20 = IofCallDriver(*((PDEVICE_OBJECT *)v5 + 9), Irp);
    if ( v20 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids, Irp, v20);
    }
    v3 = 259;
  }
LABEL_35:
  if ( v3 != 259 )
  {
    RxCeFreeIrp(Irp);
LABEL_38:
    v23 = *(void **)(a1 + 256);
    if ( v23 )
    {
      ExFreePoolWithTag(v23, 0x63437852u);
      *(_QWORD *)(a1 + 256) = 0;
    }
    v24 = v7[14];
    if ( v24 )
    {
      ObfDereferenceObject(v24);
      v7[14] = 0;
    }
    if ( *v9 != (HANDLE)-1LL )
    {
      ZwClose(*v9);
      *v9 = (HANDLE)-1LL;
    }
    goto LABEL_50;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400573b4  mov     [rsp-8+arg_18], rbx
0x1400573b9  push    rbp
0x1400573ba  push    rsi
0x1400573bb  push    rdi
0x1400573bc  push    r12
0x1400573be  push    r13
0x1400573c0  push    r14
0x1400573c2  push    r15
0x1400573c4  lea     rbp, [rsp-27h]
0x1400573c9  sub     rsp, 0A0h
0x1400573d0  mov     r14, [rcx+0D8h]
0x1400573d7  xorps   xmm0, xmm0
0x1400573da  xor     r15d, r15d
0x1400573dd  mov     [rbp+57h+arg_8], r14
0x1400573e1  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400573e5  xor     eax, eax
0x1400573e7  mov     rsi, rcx
0x1400573ea  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400573ee  mov     [rbp+57h+P], r15
0x1400573f2  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1400573f6  mov     [rbp+57h+arg_0], r15d
0x1400573fa  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400573fe  mov     qword ptr [r14+68h], 0FFFFFFFFFFFFFFFFh
0x140057406  mov     [r14+70h], r15
0x14005740a  cmp     qword ptr [rcx+0F8h], 0FFFFFFFFFFFFFFFFh
0x140057412  jnz     short loc_14005741E
0x140057414  mov     edi, 0C0000120h
0x140057419  jmp     loc_1400578BD
0x14005741e  mov     edx, 4
0x140057423  mov     r12d, 63437852h
0x140057429  mov     r8d, r12d
0x14005742c  lea     ecx, [rdx+3Eh]
0x14005742f  call    cs:__imp_ExAllocatePool2
0x140057436  nop     dword ptr [rax+rax+00h]
0x14005743b  mov     [rsi+100h], rax
0x140057442  test    rax, rax
0x140057445  jnz     short loc_140057451
0x140057447  mov     edi, 0C000009Ah
0x14005744c  jmp     loc_1400578BD
0x140057451  mov     dword ptr [rax], 1
0x140057457  xor     edx, edx
0x140057459  mov     r14, [r14+20h]
0x14005745d  lea     rbx, [r14+40h]
0x140057461  mov     rcx, rbx
0x140057464  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005746b  nop     dword ptr [rax+rax+00h]
0x140057470  cmp     qword ptr [r14+70h], 0FFFFFFFFFFFFFFFFh
0x140057475  jnz     short loc_14005749B
0x140057477  mov     rcx, r14; pAddress
0x14005747a  call    RxTdiInitializeTransportAddress
0x14005747f  mov     edi, eax
0x140057481  test    eax, eax
0x140057483  jns     short loc_14005749B
0x140057485  xor     edx, edx
0x140057487  mov     rcx, rbx
0x14005748a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140057491  nop     dword ptr [rax+rax+00h]
0x140057496  jmp     loc_1400578BD
0x14005749b  xor     edx, edx
0x14005749d  mov     rcx, rbx
0x1400574a0  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400574a7  nop     dword ptr [rax+rax+00h]
0x1400574ac  mov     r8d, 8
0x1400574b2  lea     rax, [rbp+57h+arg_0]
0x1400574b6  mov     qword ptr [rsp+0D0h+FileAttributes], rax
0x1400574bb  lea     r9, [rbp+57h+arg_8]
0x1400574bf  lea     rax, [rbp+57h+P]
0x1400574c3  lea     rdx, aConnectioncont; "ConnectionContext"
0x1400574ca  mov     [rsp+0D0h+AllocationSize], rax
0x1400574cf  lea     ecx, [r8+9]
0x1400574d3  call    BuildEaBuffer
0x1400574d8  mov     edi, eax
0x1400574da  test    eax, eax
0x1400574dc  jns     short loc_140057509
0x1400574de  mov     rcx, [rsi+100h]; P
0x1400574e5  test    rcx, rcx
0x1400574e8  jz      loc_1400578BD
0x1400574ee  mov     edx, r12d; Tag
0x1400574f1  call    cs:__imp_ExFreePoolWithTag
0x1400574f8  nop     dword ptr [rax+rax+00h]
0x1400574fd  mov     [rsi+100h], r15
0x140057504  jmp     loc_1400578BD
0x140057509  mov     r13, [rbp+57h+arg_8]
0x14005750d  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140057511  mov     rbx, [rbp+57h+P]
0x140057515  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140057519  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140057520  xorps   xmm0, xmm0
0x140057523  mov     rax, [r14+50h]
0x140057527  mov     edx, 0C0100000h; DesiredAccess
0x14005752c  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140057530  lea     r12, [r13+68h]
0x140057534  lea     rax, RelativeName
0x14005753b  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x140057542  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140057546  mov     rcx, r12; FileHandle
0x140057549  mov     eax, [rbp+57h+arg_0]
0x14005754c  mov     [rsp+0D0h+EaLength], eax; EaLength
0x140057550  mov     [rsp+0D0h+EaBuffer], rbx; EaBuffer
0x140057555  mov     [rsp+0D0h+CreateOptions], r15d; CreateOptions
0x14005755a  mov     [rsp+0D0h+CreateDisposition], 3; CreateDisposition
0x140057562  mov     [rsp+0D0h+ShareAccess], 1; ShareAccess
0x14005756a  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x140057572  mov     [rsp+0D0h+AllocationSize], r15; AllocationSize
0x140057577  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14005757c  call    cs:__imp_ZwCreateFile
0x140057583  nop     dword ptr [rax+rax+00h]
0x140057588  mov     edx, 64437852h; Tag
0x14005758d  mov     rcx, rbx; P
0x140057590  mov     edi, eax
0x140057592  call    cs:__imp_ExFreePoolWithTag
0x140057599  nop     dword ptr [rax+rax+00h]
0x14005759e  test    edi, edi
0x1400575a0  js      loc_140057859
0x1400575a6  mov     rcx, [r14+48h]
0x1400575aa  xor     r8d, r8d
0x1400575ad  xor     edx, edx
0x1400575af  mov     cl, [rcx+4Ch]
0x1400575b2  call    cs:__imp_RxCeAllocateIrp
0x1400575b9  nop     dword ptr [rax+rax+00h]
0x1400575be  mov     r15, rax
0x1400575c1  test    rax, rax
0x1400575c4  jz      loc_1400577F4
0x1400575ca  mov     rcx, [r12]; Handle
0x1400575ce  lea     rbx, [r13+70h]
0x1400575d2  mov     qword ptr [rsp+0D0h+FileAttributes], 0; HandleInformation
0x1400575db  xor     r9d, r9d; AccessMode
0x1400575de  xor     r8d, r8d; ObjectType
0x1400575e1  mov     [rsp+0D0h+AllocationSize], rbx; Object
0x1400575e6  xor     edx, edx; DesiredAccess
0x1400575e8  call    cs:__imp_ObReferenceObjectByHandle
0x1400575ef  nop     dword ptr [rax+rax+00h]
0x1400575f4  xor     ecx, ecx
0x1400575f6  mov     edi, eax
0x1400575f8  test    eax, eax
0x1400575fa  js      loc_14005779F
0x140057600  mov     rax, [r15+0B8h]
0x140057607  mov     rdx, r15; Irp
0x14005760a  mov     [rax-10h], rcx
0x14005760e  mov     [rax-8], rcx
0x140057612  mov     [rax-45h], cl
0x140057615  mov     rcx, [r15+0B8h]
0x14005761c  mov     word ptr [rcx-48h], 10Fh
0x140057622  mov     rax, [r14+48h]
0x140057626  mov     [rcx-20h], rax
0x14005762a  mov     rax, [rbx]
0x14005762d  mov     [rcx-18h], rax
0x140057631  mov     rax, [r14+70h]
0x140057635  mov     [rcx-40h], rax
0x140057639  mov     rcx, [r14+48h]; DeviceObject
0x14005763d  call    RxCeSubmitTdiRequest
0x140057642  mov     edi, eax
0x140057644  test    eax, eax
0x140057646  js      loc_140057778
0x14005764c  mov     r9, [rsi+8]
0x140057650  mov     r8, [rbx]
0x140057653  mov     rdx, [r14+48h]
0x140057657  mov     r9, [r9+78h]
0x14005765b  call    RxTdiSetTlEndpointOptions
0x140057660  xor     r8d, r8d
0x140057663  mov     edi, eax
0x140057665  test    eax, eax
0x140057667  js      loc_1400577D7
0x14005766d  mov     rax, [r15+0B8h]
0x140057674  mov     [rax-10h], r8
0x140057678  mov     [rax-8], r8
0x14005767c  mov     [rax-45h], r8b
0x140057680  mov     rdx, [r15+0B8h]
0x140057687  mov     word ptr [rdx-48h], 30Fh
0x14005768d  mov     rax, [r14+48h]
0x140057691  mov     [rdx-20h], rax
0x140057695  mov     rax, [rbx]
0x140057698  mov     [rdx-18h], rax
0x14005769c  mov     rax, [rsi+8]
0x1400576a0  mov     rcx, [rax+78h]
0x1400576a4  lea     rax, ConnectionTimeOut
0x1400576ab  mov     [rdx-28h], rax
0x1400576af  mov     [rdx-38h], rcx
0x1400576b3  lea     rcx, RxTdiAsynchronousConnectCompletion
0x1400576ba  mov     [rdx-30h], r8
0x1400576be  mov     rax, [r15+0B8h]
0x1400576c5  mov     [rax-10h], rcx
0x1400576c9  mov     [rax-8], rsi
0x1400576cd  mov     byte ptr [rax-45h], 0E0h
0x1400576d1  mov     rax, r15
0x1400576d4  xchg    rax, [rsi+0F8h]
0x1400576db  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400576e2  lea     rbx, WPP_GLOBAL_Control
0x1400576e9  cmp     rcx, rbx
0x1400576ec  jz      short loc_140057724
0x1400576ee  mov     eax, [rcx+2Ch]
0x1400576f1  test    al, 4
0x1400576f3  jz      short loc_140057724
0x1400576f5  cmp     byte ptr [rcx+29h], 2
0x1400576f9  jb      short loc_140057724
0x1400576fb  mov     rcx, [rcx+18h]
0x1400576ff  lea     rax, [r14+20h]
0x140057703  mov     qword ptr [rsp+0D0h+FileAttributes], rax
0x140057708  lea     edx, [r8+0Fh]
0x14005770c  mov     rax, [rsi+8]
0x140057710  lea     r8, WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids
0x140057717  mov     r9, r15
0x14005771a  mov     [rsp+0D0h+AllocationSize], rax
0x14005771f  call    WPP_SF_qqZ
0x140057724  mov     rcx, [r14+48h]; DeviceObject
0x140057728  mov     rdx, r15; Irp
0x14005772b  call    cs:__imp_IofCallDriver
0x140057732  nop     dword ptr [rax+rax+00h]
0x140057737  test    eax, eax
0x140057739  jns     short loc_140057771
0x14005773b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140057742  cmp     rcx, rbx
0x140057745  jz      short loc_140057771
0x140057747  mov     edx, [rcx+2Ch]
0x14005774a  test    dl, 1
0x14005774d  jz      short loc_140057771
0x14005774f  cmp     byte ptr [rcx+29h], 1
0x140057753  jb      short loc_140057771
0x140057755  mov     rcx, [rcx+18h]
0x140057759  lea     r8, WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids
0x140057760  mov     edx, 10h
0x140057765  mov     dword ptr [rsp+0D0h+AllocationSize], eax
0x140057769  mov     r9, r15
0x14005776c  call    WPP_SF_qD
0x140057771  mov     edi, 103h
0x140057776  jmp     short loc_1400577D7
0x140057778  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005777f  lea     rbx, WPP_GLOBAL_Control
0x140057786  cmp     rcx, rbx
0x140057789  jz      short loc_1400577D7
0x14005778b  mov     eax, [rcx+2Ch]
0x14005778e  test    al, 4
0x140057790  jz      short loc_1400577D7
0x140057792  cmp     byte ptr [rcx+29h], 1
0x140057796  jb      short loc_1400577D7
0x140057798  mov     edx, 11h
0x14005779d  jmp     short loc_1400577C4
0x14005779f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400577a6  lea     rbx, WPP_GLOBAL_Control
0x1400577ad  cmp     rcx, rbx
0x1400577b0  jz      short loc_1400577D7
0x1400577b2  mov     eax, [rcx+2Ch]
0x1400577b5  test    al, 4
0x1400577b7  jz      short loc_1400577D7
0x1400577b9  cmp     byte ptr [rcx+29h], 1
0x1400577bd  jb      short loc_1400577D7
0x1400577bf  mov     edx, 12h
0x1400577c4  mov     rcx, [rcx+18h]
0x1400577c8  lea     r8, WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids
0x1400577cf  mov     r9d, edi
0x1400577d2  call    WPP_SF_d
0x1400577d7  cmp     edi, 103h
0x1400577dd  jz      loc_1400578C4
0x1400577e3  mov     rcx, r15; pIrp
0x1400577e6  call    cs:__imp_RxCeFreeIrp
0x1400577ed  nop     dword ptr [rax+rax+00h]
0x1400577f2  jmp     short loc_1400577F9
0x1400577f4  mov     edi, 0C000009Ah
0x1400577f9  mov     rcx, [rsi+100h]; P
0x140057800  xor     r15d, r15d
0x140057803  test    rcx, rcx
0x140057806  jz      short loc_140057820
0x140057808  mov     edx, 63437852h; Tag
0x14005780d  call    cs:__imp_ExFreePoolWithTag
0x140057814  nop     dword ptr [rax+rax+00h]
0x140057819  mov     [rsi+100h], r15
0x140057820  mov     rcx, [r13+70h]; Object
0x140057824  test    rcx, rcx
0x140057827  jz      short loc_140057839
0x140057829  call    cs:__imp_ObfDereferenceObject
0x140057830  nop     dword ptr [rax+rax+00h]
0x140057835  mov     [r13+70h], r15
0x140057839  mov     rcx, [r12]; Handle
0x14005783d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140057841  jz      short loc_1400578B5
0x140057843  call    cs:__imp_ZwClose
0x14005784a  nop     dword ptr [rax+rax+00h]
0x14005784f  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x140057857  jmp     short loc_1400578B5
0x140057859  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140057860  lea     rbx, WPP_GLOBAL_Control
0x140057867  cmp     rcx, rbx
0x14005786a  jz      short loc_140057891
0x14005786c  mov     eax, [rcx+2Ch]
0x14005786f  test    al, 4
0x140057871  jz      short loc_140057891
0x140057873  cmp     byte ptr [rcx+29h], 1
0x140057877  jb      short loc_140057891
0x140057879  mov     rcx, [rcx+18h]
0x14005787d  lea     r8, WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids
0x140057884  mov     edx, 13h
0x140057889  mov     r9d, edi
0x14005788c  call    WPP_SF_d
0x140057891  mov     rcx, [rsi+100h]; P
0x140057898  test    rcx, rcx
0x14005789b  jz      short loc_1400578B5
0x14005789d  mov     edx, 63437852h; Tag
0x1400578a2  call    cs:__imp_ExFreePoolWithTag
0x1400578a9  nop     dword ptr [rax+rax+00h]
0x1400578ae  mov     [rsi+100h], r15
  ... truncated ...
```
