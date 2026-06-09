# PartitionOverlapIo(_PM_OVERLAP_TYPE,_PM_PATCH *,unsigned __int64,unsigned __int64,void *)

- ea: `0x14000b490`
- end: `0x14000b6fa`
- name: `?PartitionOverlapIo@@YAJW4_PM_OVERLAP_TYPE@@PEAU_PM_PATCH@@_K2PEAX@Z`
- size: `618`
- prototype: `__int64 __fastcall(int, __int64, ULONG, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000b490`
- `0x140010f20`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000b582`
- `ntoskrnl!IoFreeIrp` at `0x14000b582`
- `ntoskrnl!IoFreeMdl` at `0x14000b573`
- `ntoskrnl!IoFreeMdl` at `0x14000b573`
- `ntoskrnl!IoBuildPartialMdl` at `0x14000b5a0`
- `ntoskrnl!IoBuildPartialMdl` at `0x14000b5a0`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x14000b66e`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x14000b66e`
- `ntoskrnl!IoAllocateMdl` at `0x14000b550`
- `ntoskrnl!IoAllocateMdl` at `0x14000b550`
- `ntoskrnl!IoSetActivityIdIrp` at `0x14000b651`
- `ntoskrnl!IoSetActivityIdIrp` at `0x14000b651`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14000b639`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14000b639`
- `ntoskrnl!IoIsActivityTracingEnabled` at `0x14000b621`
- `ntoskrnl!IoIsActivityTracingEnabled` at `0x14000b621`
- `ntoskrnl!IoAllocateIrp` at `0x14000b50e`
- `ntoskrnl!IoAllocateIrp` at `0x14000b50e`

## pseudocode

```c
__int64 __fastcall PartitionOverlapIo(int a1, __int64 a2, ULONG a3, __int64 a4, _QWORD *a5)
{
  int v8; // ecx
  int v9; // ecx
  int v10; // ebx
  __int64 v11; // rsi
  __int64 v12; // rbp
  PIRP Irp; // rdi
  void *v14; // r14
  struct _MDL *Mdl; // rax
  struct _MDL *MdlAddress; // rcx
  struct _FILE_OBJECT *v17; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  struct _IO_STACK_LOCATION *v19; // rcx
  struct _LIST_ENTRY *v20; // rsi
  struct _LIST_ENTRY *Blink; // rcx
  __int128 v23; // [rsp+30h] [rbp-48h] BYREF

  v23 = 0;
  v8 = a1 - 1;
  if ( !v8 )
    return (unsigned int)-1073741811;
  v9 = v8 - 1;
  if ( v9 )
  {
    if ( v9 == 2 )
      return 0;
    return (unsigned int)-1073741811;
  }
  v11 = a5[1];
  v12 = *(_QWORD *)(v11 + 184);
  Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(*a5 + 8LL) + 76LL) + 1, 0);
  if ( !Irp )
    return (unsigned int)-1073741670;
  v14 = (void *)(a4
               + *(_QWORD *)(*(_QWORD *)(v11 + 8) + 32LL)
               + *(unsigned int *)(*(_QWORD *)(v11 + 8) + 44LL)
               - *(_QWORD *)(v12 + 24));
  Mdl = IoAllocateMdl(v14, a3, 0, 0, Irp);
  Irp->MdlAddress = Mdl;
  if ( !Mdl )
  {
    v10 = -1073741670;
LABEL_9:
    MdlAddress = Irp->MdlAddress;
    if ( MdlAddress )
      IoFreeMdl(MdlAddress);
    IoFreeIrp(Irp);
    return (unsigned int)v10;
  }
  IoBuildPartialMdl(*(PMDL *)(v11 + 8), Mdl, v14, a3);
  Irp->Flags |= *(_DWORD *)(v11 + 16) & 2;
  Irp->Tail.Overlay.Thread = *(PETHREAD *)(v11 + 152);
  v17 = *(struct _FILE_OBJECT **)(v11 + 192);
  --Irp->Tail.Overlay.CurrentStackLocation;
  --Irp->CurrentLocation;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Irp->Tail.Overlay.OriginalFileObject = v17;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)v12;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)(v12 + 16);
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(v12 + 32);
  CurrentStackLocation[-1].FileObject = *(PFILE_OBJECT *)(v12 + 48);
  CurrentStackLocation[-1].Control = 0;
  CurrentStackLocation[-1].Parameters.Read.Length = a3;
  CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart = a4 + *(_QWORD *)(a2 + 24) - *(_QWORD *)(a2 + 16);
  if ( (unsigned __int8)IoIsActivityTracingEnabled() && (int)IoGetActivityIdIrp(v11, &v23) >= 0 )
    IoSetActivityIdIrp(Irp, &v23);
  v10 = IoPropagateIrpExtensionEx(
          v11,
          Irp,
          a4 - CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart,
          0xFFFFFFFFLL);
  if ( v10 < 0 )
    goto LABEL_9;
  v19 = Irp->Tail.Overlay.CurrentStackLocation;
  v19[-1].Context = (PVOID)v11;
  v20 = (struct _LIST_ENTRY *)(v11 + 168);
  v19[-1].CompletionRoutine = PartitionChildIoCompletion;
  v19[-1].Control = -32;
  Blink = v20->Blink;
  if ( Blink->Flink != v20 )
    __fastfail(3u);
  Irp->Tail.Overlay.ListEntry.Flink = v20;
  Irp->Tail.Overlay.ListEntry.Blink = Blink;
  Blink->Flink = &Irp->Tail.Overlay.ListEntry;
  v20->Blink = &Irp->Tail.Overlay.ListEntry;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000b490  mov     [rsp+arg_0], rbx
0x14000b495  mov     [rsp+arg_8], rbp
0x14000b49a  push    rsi
0x14000b49b  push    rdi
0x14000b49c  push    r13
0x14000b49e  push    r14
0x14000b4a0  push    r15
0x14000b4a2  sub     rsp, 50h
0x14000b4a6  mov     rax, cs:__security_cookie
0x14000b4ad  xor     rax, rsp
0x14000b4b0  mov     [rsp+78h+var_38], rax
0x14000b4b5  xorps   xmm0, xmm0
0x14000b4b8  mov     rbx, r9
0x14000b4bb  mov     r9, [rsp+78h+arg_20]
0x14000b4c3  mov     r15, r8
0x14000b4c6  mov     r13, rdx
0x14000b4c9  movups  [rsp+78h+var_48], xmm0
0x14000b4ce  sub     ecx, 1
0x14000b4d1  jz      loc_14000B6CC
0x14000b4d7  sub     ecx, 1
0x14000b4da  jz      short loc_14000B4F5
0x14000b4dc  sub     ecx, 1
0x14000b4df  jz      loc_14000B6CC
0x14000b4e5  cmp     ecx, 1
0x14000b4e8  jnz     loc_14000B6CC
0x14000b4ee  xor     ebx, ebx
0x14000b4f0  jmp     loc_14000B6D1
0x14000b4f5  mov     rax, [r9]
0x14000b4f8  xor     edx, edx; ChargeQuota
0x14000b4fa  mov     rsi, [r9+8]
0x14000b4fe  mov     rcx, [rax+8]
0x14000b502  mov     rbp, [rsi+0B8h]
0x14000b509  mov     cl, [rcx+4Ch]
0x14000b50c  inc     cl; StackSize
0x14000b50e  call    cs:__imp_IoAllocateIrp
0x14000b515  nop     dword ptr [rax+rax+00h]
0x14000b51a  mov     rdi, rax
0x14000b51d  test    rax, rax
0x14000b520  jnz     short loc_14000B52C
0x14000b522  mov     ebx, 0C000009Ah
0x14000b527  jmp     loc_14000B6D1
0x14000b52c  mov     rax, [rsi+8]
0x14000b530  xor     r9d, r9d; ChargeQuota
0x14000b533  xor     r8d, r8d; SecondaryBuffer
0x14000b536  mov     [rsp+78h+Irp], rdi; Irp
0x14000b53b  mov     edx, r15d; Length
0x14000b53e  mov     r14d, [rax+2Ch]
0x14000b542  sub     r14, [rbp+18h]
0x14000b546  add     r14, [rax+20h]
0x14000b54a  add     r14, rbx
0x14000b54d  mov     rcx, r14; VirtualAddress
0x14000b550  call    cs:__imp_IoAllocateMdl
0x14000b557  nop     dword ptr [rax+rax+00h]
0x14000b55c  mov     [rdi+8], rax
0x14000b560  test    rax, rax
0x14000b563  jnz     short loc_14000B593
0x14000b565  mov     ebx, 0C000009Ah
0x14000b56a  mov     rcx, [rdi+8]; Mdl
0x14000b56e  test    rcx, rcx
0x14000b571  jz      short loc_14000B57F
0x14000b573  call    cs:__imp_IoFreeMdl
0x14000b57a  nop     dword ptr [rax+rax+00h]
0x14000b57f  mov     rcx, rdi; Irp
0x14000b582  call    cs:__imp_IoFreeIrp
0x14000b589  nop     dword ptr [rax+rax+00h]
0x14000b58e  jmp     loc_14000B6D1
0x14000b593  mov     rcx, [rsi+8]; SourceMdl
0x14000b597  mov     r9d, r15d; Length
0x14000b59a  mov     r8, r14; VirtualAddress
0x14000b59d  mov     rdx, rax; TargetMdl
0x14000b5a0  call    cs:__imp_IoBuildPartialMdl
0x14000b5a7  nop     dword ptr [rax+rax+00h]
0x14000b5ac  mov     eax, [rsi+10h]
0x14000b5af  and     eax, 2
0x14000b5b2  or      [rdi+10h], eax
0x14000b5b5  mov     rax, [rsi+98h]
0x14000b5bc  mov     [rdi+98h], rax
0x14000b5c3  mov     rax, [rsi+0C0h]
0x14000b5ca  add     qword ptr [rdi+0B8h], 0FFFFFFFFFFFFFFB8h
0x14000b5d2  dec     byte ptr [rdi+43h]
0x14000b5d5  mov     r14, [rdi+0B8h]
0x14000b5dc  mov     [rdi+0C0h], rax
0x14000b5e3  movups  xmm0, xmmword ptr [rbp+0]
0x14000b5e7  movups  xmmword ptr [r14-48h], xmm0
0x14000b5ec  movups  xmm1, xmmword ptr [rbp+10h]
0x14000b5f0  movups  xmmword ptr [r14-38h], xmm1
0x14000b5f5  movups  xmm0, xmmword ptr [rbp+20h]
0x14000b5f9  movups  xmmword ptr [r14-28h], xmm0
0x14000b5fe  movsd   xmm1, qword ptr [rbp+30h]
0x14000b603  movsd   qword ptr [r14-18h], xmm1
0x14000b609  mov     byte ptr [r14-45h], 0
0x14000b60e  mov     [r14-40h], r15d
0x14000b612  mov     rcx, [r13+18h]
0x14000b616  sub     rcx, [r13+10h]
0x14000b61a  add     rcx, rbx
0x14000b61d  mov     [r14-30h], rcx
0x14000b621  call    cs:__imp_IoIsActivityTracingEnabled
0x14000b628  nop     dword ptr [rax+rax+00h]
0x14000b62d  test    al, al
0x14000b62f  jz      short loc_14000B65D
0x14000b631  lea     rdx, [rsp+78h+var_48]
0x14000b636  mov     rcx, rsi
0x14000b639  call    cs:__imp_IoGetActivityIdIrp
0x14000b640  nop     dword ptr [rax+rax+00h]
0x14000b645  test    eax, eax
0x14000b647  js      short loc_14000B65D
0x14000b649  lea     rdx, [rsp+78h+var_48]
0x14000b64e  mov     rcx, rdi
0x14000b651  call    cs:__imp_IoSetActivityIdIrp
0x14000b658  nop     dword ptr [rax+rax+00h]
0x14000b65d  sub     rbx, [r14-30h]
0x14000b661  or      r9d, 0FFFFFFFFh
0x14000b665  mov     r8, rbx
0x14000b668  mov     rdx, rdi
0x14000b66b  mov     rcx, rsi
0x14000b66e  call    cs:__imp_IoPropagateIrpExtensionEx
0x14000b675  nop     dword ptr [rax+rax+00h]
0x14000b67a  mov     ebx, eax
0x14000b67c  test    eax, eax
0x14000b67e  js      loc_14000B56A
0x14000b684  mov     rcx, [rdi+0B8h]
0x14000b68b  lea     rax, ?PartitionChildIoCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; PartitionChildIoCompletion(_DEVICE_OBJECT *,_IRP *,void *)
0x14000b692  mov     [rcx-8], rsi
0x14000b696  add     rsi, 0A8h
0x14000b69d  mov     [rcx-10h], rax
0x14000b6a1  mov     byte ptr [rcx-45h], 0E0h
0x14000b6a5  mov     rcx, [rsi+8]
0x14000b6a9  cmp     [rcx], rsi
0x14000b6ac  jz      short loc_14000B6B5
0x14000b6ae  mov     ecx, 3
0x14000b6b3  int     29h; Win8: RtlFailFast(ecx)
0x14000b6b5  lea     rax, [rdi+0A8h]
0x14000b6bc  mov     [rax], rsi
0x14000b6bf  mov     [rax+8], rcx
0x14000b6c3  mov     [rcx], rax
0x14000b6c6  mov     [rsi+8], rax
0x14000b6ca  jmp     short loc_14000B6D1
0x14000b6cc  mov     ebx, 0C000000Dh
0x14000b6d1  mov     eax, ebx
0x14000b6d3  mov     rcx, [rsp+78h+var_38]
0x14000b6d8  xor     rcx, rsp; StackCookie
0x14000b6db  call    __security_check_cookie
0x14000b6e0  lea     r11, [rsp+78h+var_28]
0x14000b6e5  mov     rbx, [r11+30h]
0x14000b6e9  mov     rbp, [r11+38h]
0x14000b6ed  mov     rsp, r11
0x14000b6f0  pop     r15
0x14000b6f2  pop     r14
0x14000b6f4  pop     r13
0x14000b6f6  pop     rdi
0x14000b6f7  pop     rsi
0x14000b6f8  retn
```
