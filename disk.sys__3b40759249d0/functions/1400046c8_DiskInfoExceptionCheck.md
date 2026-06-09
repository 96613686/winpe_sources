# DiskInfoExceptionCheck

- ea: `0x1400046c8`
- end: `0x140004c96`
- name: `DiskInfoExceptionCheck`
- size: `1486`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140011ee0`

## callees

- `0x140004078`
- `0x1400046c8`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1400048f0`
- `ntoskrnl!IoFreeIrp` at `0x140004a32`
- `ntoskrnl!IoFreeIrp` at `0x140004ba7`
- `ntoskrnl!IoFreeIrp` at `0x1400048f0`
- `ntoskrnl!IoFreeIrp` at `0x140004a32`
- `ntoskrnl!IoFreeIrp` at `0x140004ba7`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140004a80`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140004a80`
- `ntoskrnl!IoAllocateMdl` at `0x1400049d0`
- `ntoskrnl!IoAllocateMdl` at `0x1400049d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004774`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400047db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400047ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004850`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004861`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004872`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004901`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004912`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004923`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004a01`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004a12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004a23`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004b76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004b87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004b98`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004774`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400047db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400047ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004850`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004861`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004872`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004901`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004912`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004923`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004a01`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004a12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004a23`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004b76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004b87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004b98`
- `ntoskrnl!IofCallDriver` at `0x140004c75`
- `ntoskrnl!IofCallDriver` at `0x140004c75`
- `ntoskrnl!IoAllocateIrp` at `0x140004837`
- `ntoskrnl!IoAllocateIrp` at `0x140004837`
- `ntoskrnl!ExAllocatePool2` at `0x1400046ea`
- `ntoskrnl!ExAllocatePool2` at `0x14000475b`
- `ntoskrnl!ExAllocatePool2` at `0x1400047c2`
- `ntoskrnl!ExAllocatePool2` at `0x1400046ea`
- `ntoskrnl!ExAllocatePool2` at `0x14000475b`
- `ntoskrnl!ExAllocatePool2` at `0x1400047c2`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140004abf`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140004abf`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x1400048e1`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x1400049f0`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x140004b65`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x1400048e1`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x1400049f0`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x140004b65`
- `CLASSPNP!ClassAcquireRemoveLockEx` at `0x1400048c6`
- `CLASSPNP!ClassAcquireRemoveLockEx` at `0x1400048c6`

## pseudocode

```c
__int64 __fastcall DiskInfoExceptionCheck(__int64 a1)
{
  void *Pool2; // rbp
  PDEVICE_OBJECT v3; // rcx
  __int64 v4; // rdx
  unsigned int v5; // ecx
  unsigned int v6; // r15d
  _WORD *v7; // rbx
  void *v8; // r14
  PIRP v9; // rax
  IRP *Irp; // rdi
  struct _IO_STACK_LOCATION *v12; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v14; // rax
  struct _MDL *Mdl; // rax
  int v16; // eax
  _BYTE *v17; // rdx
  int v18; // eax
  char v19; // cl

  Pool2 = (void *)ExAllocatePool2(72, 192, 1095000915);
  if ( !Pool2 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      return 3221225626LL;
    }
    v4 = 24;
LABEL_34:
    WPP_SF_(v3->AttachedDevice, v4, WPP_a9711c54c416383df697b4e008bb3725_Traceguids);
    return 3221225626LL;
  }
  v5 = 184;
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 528) + 30LL) != 1 )
    v5 = 88;
  v6 = v5;
  v7 = (_WORD *)ExAllocatePool2(64, v5, 1396990803);
  if ( !v7 )
  {
    ExFreePoolWithTag(Pool2, 0);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      return 3221225626LL;
    }
    v4 = 25;
    goto LABEL_34;
  }
  v8 = (void *)ExAllocatePool2(72, 18, 927163219);
  if ( !v8 )
  {
    ExFreePoolWithTag(v7, 0);
    ExFreePoolWithTag(Pool2, 0);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      return 3221225626LL;
    }
    v4 = 26;
    goto LABEL_34;
  }
  v9 = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(a1 + 16) + 76LL) + 1, 0);
  Irp = v9;
  if ( !v9 )
  {
    ExFreePoolWithTag(v8, 0);
    ExFreePoolWithTag(v7, 0);
    ExFreePoolWithTag(Pool2, 0);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      return 3221225626LL;
    }
    v4 = 27;
    goto LABEL_34;
  }
  if ( ClassAcquireRemoveLockEx(*(PDEVICE_OBJECT *)(a1 + 8), v9, "minkernel\\storage\\disk\\diskwmi.c", 0x7D4u) )
  {
    ClassReleaseRemoveLock(*(PDEVICE_OBJECT *)(a1 + 8), Irp);
    IoFreeIrp(Irp);
    ExFreePoolWithTag(v8, 0);
    ExFreePoolWithTag(v7, 0);
    ExFreePoolWithTag(Pool2, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_a9711c54c416383df697b4e008bb3725_Traceguids);
    }
    return 3221225664LL;
  }
  v12 = --Irp->Tail.Overlay.CurrentStackLocation;
  --Irp->CurrentLocation;
  v12->DeviceObject = *(PDEVICE_OBJECT *)(a1 + 8);
  v12->Parameters.CreatePipe.Parameters = (PNAMED_PIPE_CREATE_PARAMETERS)4;
  v12->Parameters.Read.ByteOffset.QuadPart = (LONGLONG)v8;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].MajorFunction = 15;
  CurrentStackLocation[-1].Parameters.WMI.ProviderId = (ULONG_PTR)v7;
  v14 = Irp->Tail.Overlay.CurrentStackLocation;
  v14[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)DiskInfoExceptionComplete;
  v14[-1].Context = v7;
  v14[-1].Control = -32;
  Mdl = IoAllocateMdl(Pool2, 0xC0u, 0, 0, Irp);
  Irp->MdlAddress = Mdl;
  if ( !Mdl )
  {
    ClassReleaseRemoveLock(*(PDEVICE_OBJECT *)(a1 + 8), Irp);
    ExFreePoolWithTag(v7, 0);
    ExFreePoolWithTag(Pool2, 0);
    ExFreePoolWithTag(v8, 0);
    IoFreeIrp(Irp);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      return 3221225626LL;
    }
    v4 = 29;
    goto LABEL_34;
  }
  MmBuildMdlForNonPagedPool(Mdl);
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 528) + 30LL) != 1 )
  {
    *v7 = 88;
    v17 = v7 + 36;
    *((_BYTE *)v7 + 2) = 0;
    *((_BYTE *)v7 + 11) = 18;
    *((_QWORD *)v7 + 4) = v8;
    *((_DWORD *)v7 + 5) = *(_DWORD *)(a1 + 584);
    *((_DWORD *)v7 + 4) = 192;
    *((_QWORD *)v7 + 3) = Pool2;
    v18 = *(_DWORD *)(a1 + 592) | 0x148;
    v7[4] = 8447;
    *((_DWORD *)v7 + 3) = v18;
    *((_QWORD *)v7 + 6) = Irp;
    *((_BYTE *)v7 + 10) = 6;
    goto LABEL_45;
  }
  *v7 = 8;
  *((_BYTE *)v7 + 2) = 40;
  *((_DWORD *)v7 + 2) = 1397899864;
  *((_DWORD *)v7 + 3) = 1;
  *((_DWORD *)v7 + 4) = v6;
  *((_DWORD *)v7 + 5) = 0;
  v7[18] = IoGetIoPriorityHint(Irp);
  *((_DWORD *)v7 + 13) = 128;
  *((_DWORD *)v7 + 14) = 1;
  *((_DWORD *)v7 + 10) = *(_DWORD *)(a1 + 584);
  *((_DWORD *)v7 + 15) = 192;
  *((_QWORD *)v7 + 8) = Pool2;
  v16 = *(_DWORD *)(a1 + 592) | 0x148;
  *((_DWORD *)v7 + 8) = 255;
  *((_DWORD *)v7 + 6) = v16;
  v7[19] = 32;
  *((_QWORD *)v7 + 10) = Irp;
  v7[64] = 1;
  *((_DWORD *)v7 + 33) = 4;
  *((_DWORD *)v7 + 30) = 144;
  if ( *((_DWORD *)v7 + 4) >= 0xB8u )
  {
    *((_DWORD *)v7 + 36) = 64;
    v17 = v7 + 84;
    *((_DWORD *)v7 + 37) = 32;
    *(_WORD *)((char *)v7 + 153) = 1554;
    *((_QWORD *)v7 + 20) = v8;
LABEL_45:
    v19 = *(_BYTE *)(*(_QWORD *)(a1 + 1152) + 38LL);
    v17[2] = v17[2] & 0xC0 | 0x1C;
    if ( v19 )
    {
      *v17 = 90;
      v17[8] = -64;
      *((_BYTE *)v7 + 10) = 10;
    }
    else
    {
      *v17 = 26;
      v17[4] = -64;
    }
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 16), Irp);
    return 259;
  }
  ClassReleaseRemoveLock(*(PDEVICE_OBJECT *)(a1 + 8), Irp);
  ExFreePoolWithTag(v7, 0);
  ExFreePoolWithTag(Pool2, 0);
  ExFreePoolWithTag(v8, 0);
  IoFreeIrp(Irp);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_a9711c54c416383df697b4e008bb3725_Traceguids);
  }
  return 3221225701LL;
}

```

## disassembly

```asm
0x1400046c8  push    rbx
0x1400046ca  push    rbp
0x1400046cb  push    rsi
0x1400046cc  push    rdi
0x1400046cd  push    r13
0x1400046cf  push    r14
0x1400046d1  push    r15
0x1400046d3  sub     rsp, 30h
0x1400046d7  mov     edx, 0C0h
0x1400046dc  mov     rsi, rcx
0x1400046df  mov     r8d, 41446353h
0x1400046e5  lea     edi, [rdx-78h]
0x1400046e8  mov     ecx, edi
0x1400046ea  call    cs:__imp_ExAllocatePool2
0x1400046f1  nop     dword ptr [rax+rax+00h]
0x1400046f6  mov     rbp, rax
0x1400046f9  test    rax, rax
0x1400046fc  jnz     short loc_140004732
0x1400046fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140004705  lea     rax, WPP_GLOBAL_Control
0x14000470c  cmp     rcx, rax
0x14000470f  jz      loc_140004A73
0x140004715  mov     eax, [rcx+2Ch]
0x140004718  test    al, 40h
0x14000471a  jz      loc_140004A73
0x140004720  cmp     byte ptr [rcx+29h], 3
0x140004724  jb      loc_140004A73
0x14000472a  lea     edx, [rdi-30h]
0x14000472d  jmp     loc_140004A63
0x140004732  mov     rax, [rsi+210h]
0x140004739  mov     ecx, 0B8h
0x14000473e  mov     r8d, 53446353h
0x140004744  lea     edx, [rcx-60h]
0x140004747  lea     r13d, [rdx-57h]
0x14000474b  cmp     [rax+1Eh], r13b
0x14000474f  cmovnz  ecx, edx
0x140004752  mov     r15d, ecx
0x140004755  mov     edx, ecx
0x140004757  lea     ecx, [r13+3Fh]
0x14000475b  call    cs:__imp_ExAllocatePool2
0x140004762  nop     dword ptr [rax+rax+00h]
0x140004767  mov     rbx, rax
0x14000476a  test    rax, rax
0x14000476d  jnz     short loc_1400047B4
0x14000476f  xor     edx, edx; Tag
0x140004771  mov     rcx, rbp; P
0x140004774  call    cs:__imp_ExFreePoolWithTag
0x14000477b  nop     dword ptr [rax+rax+00h]
0x140004780  mov     rcx, cs:WPP_GLOBAL_Control
0x140004787  lea     rax, WPP_GLOBAL_Control
0x14000478e  cmp     rcx, rax
0x140004791  jz      loc_140004A73
0x140004797  mov     eax, [rcx+2Ch]
0x14000479a  test    al, 40h
0x14000479c  jz      loc_140004A73
0x1400047a2  cmp     byte ptr [rcx+29h], 3
0x1400047a6  jb      loc_140004A73
0x1400047ac  lea     edx, [rbx+19h]
0x1400047af  jmp     loc_140004A63
0x1400047b4  mov     edx, 12h
0x1400047b9  mov     r8d, 37436353h
0x1400047bf  mov     rcx, rdi
0x1400047c2  call    cs:__imp_ExAllocatePool2
0x1400047c9  nop     dword ptr [rax+rax+00h]
0x1400047ce  xor     edx, edx; ChargeQuota
0x1400047d0  mov     r14, rax
0x1400047d3  test    rax, rax
0x1400047d6  jnz     short loc_14000482D
0x1400047d8  mov     rcx, rbx; P
0x1400047db  call    cs:__imp_ExFreePoolWithTag
0x1400047e2  nop     dword ptr [rax+rax+00h]
0x1400047e7  xor     edx, edx; Tag
0x1400047e9  mov     rcx, rbp; P
0x1400047ec  call    cs:__imp_ExFreePoolWithTag
0x1400047f3  nop     dword ptr [rax+rax+00h]
0x1400047f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400047ff  lea     rax, WPP_GLOBAL_Control
0x140004806  cmp     rcx, rax
0x140004809  jz      loc_140004A73
0x14000480f  mov     eax, [rcx+2Ch]
0x140004812  test    al, 40h
0x140004814  jz      loc_140004A73
0x14000481a  cmp     byte ptr [rcx+29h], 3
0x14000481e  jb      loc_140004A73
0x140004824  lea     edx, [r14+1Ah]
0x140004828  jmp     loc_140004A63
0x14000482d  mov     rax, [rsi+10h]
0x140004831  mov     cl, [rax+4Ch]
0x140004834  add     cl, r13b; StackSize
0x140004837  call    cs:__imp_IoAllocateIrp
0x14000483e  nop     dword ptr [rax+rax+00h]
0x140004843  mov     rdi, rax
0x140004846  test    rax, rax
0x140004849  jnz     short loc_1400048B2
0x14000484b  xor     edx, edx; Tag
0x14000484d  mov     rcx, r14; P
0x140004850  call    cs:__imp_ExFreePoolWithTag
0x140004857  nop     dword ptr [rax+rax+00h]
0x14000485c  xor     edx, edx; Tag
0x14000485e  mov     rcx, rbx; P
0x140004861  call    cs:__imp_ExFreePoolWithTag
0x140004868  nop     dword ptr [rax+rax+00h]
0x14000486d  xor     edx, edx; Tag
0x14000486f  mov     rcx, rbp; P
0x140004872  call    cs:__imp_ExFreePoolWithTag
0x140004879  nop     dword ptr [rax+rax+00h]
0x14000487e  mov     rcx, cs:WPP_GLOBAL_Control
0x140004885  lea     rax, WPP_GLOBAL_Control
0x14000488c  cmp     rcx, rax
0x14000488f  jz      loc_140004A73
0x140004895  mov     eax, [rcx+2Ch]
0x140004898  test    al, 40h
0x14000489a  jz      loc_140004A73
0x1400048a0  cmp     byte ptr [rcx+29h], 3
0x1400048a4  jb      loc_140004A73
0x1400048aa  lea     edx, [rdi+1Bh]
0x1400048ad  jmp     loc_140004A63
0x1400048b2  mov     rcx, [rsi+8]; DeviceObject
0x1400048b6  lea     r8, aMinkernelStora_0; "minkernel\\storage\\disk\\diskwmi.c"
0x1400048bd  mov     r9d, 7D4h; Line
0x1400048c3  mov     rdx, rdi; Tag
0x1400048c6  call    cs:__imp_ClassAcquireRemoveLockEx
0x1400048cd  nop     dword ptr [rax+rax+00h]
0x1400048d2  test    eax, eax
0x1400048d4  jz      loc_14000496E
0x1400048da  mov     rcx, [rsi+8]; DeviceObject
0x1400048de  mov     rdx, rdi; Tag
0x1400048e1  call    cs:__imp_ClassReleaseRemoveLock
0x1400048e8  nop     dword ptr [rax+rax+00h]
0x1400048ed  mov     rcx, rdi; Irp
0x1400048f0  call    cs:__imp_IoFreeIrp
0x1400048f7  nop     dword ptr [rax+rax+00h]
0x1400048fc  xor     edx, edx; Tag
0x1400048fe  mov     rcx, r14; P
0x140004901  call    cs:__imp_ExFreePoolWithTag
0x140004908  nop     dword ptr [rax+rax+00h]
0x14000490d  xor     edx, edx; Tag
0x14000490f  mov     rcx, rbx; P
0x140004912  call    cs:__imp_ExFreePoolWithTag
0x140004919  nop     dword ptr [rax+rax+00h]
0x14000491e  xor     edx, edx; Tag
0x140004920  mov     rcx, rbp; P
0x140004923  call    cs:__imp_ExFreePoolWithTag
0x14000492a  nop     dword ptr [rax+rax+00h]
0x14000492f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004936  lea     rax, WPP_GLOBAL_Control
0x14000493d  cmp     rcx, rax
0x140004940  jz      short loc_140004964
0x140004942  mov     eax, [rcx+2Ch]
0x140004945  test    al, 40h
0x140004947  jz      short loc_140004964
0x140004949  cmp     byte ptr [rcx+29h], 3
0x14000494d  jb      short loc_140004964
0x14000494f  mov     rcx, [rcx+18h]
0x140004953  lea     r8, WPP_a9711c54c416383df697b4e008bb3725_Traceguids
0x14000495a  mov     edx, 1Ch
0x14000495f  call    WPP_SF_
0x140004964  mov     eax, 0C00000C0h
0x140004969  jmp     loc_140004C86
0x14000496e  add     qword ptr [rdi+0B8h], 0FFFFFFFFFFFFFFB8h
0x140004976  xor     r9d, r9d; ChargeQuota
0x140004979  mov     rcx, [rdi+0B8h]
0x140004980  xor     r8d, r8d; SecondaryBuffer
0x140004983  dec     byte ptr [rdi+43h]
0x140004986  mov     edx, 0C0h; Length
0x14000498b  mov     rax, [rsi+8]
0x14000498f  mov     [rsp+68h+Irp], rdi; Irp
0x140004994  mov     [rcx+28h], rax
0x140004998  mov     qword ptr [rcx+20h], 4
0x1400049a0  mov     [rcx+18h], r14
0x1400049a4  lea     rcx, DiskInfoExceptionComplete
0x1400049ab  mov     rax, [rdi+0B8h]
0x1400049b2  mov     byte ptr [rax-48h], 0Fh
0x1400049b6  mov     [rax-40h], rbx
0x1400049ba  mov     rax, [rdi+0B8h]
0x1400049c1  mov     [rax-10h], rcx
0x1400049c5  mov     rcx, rbp; VirtualAddress
0x1400049c8  mov     [rax-8], rbx
0x1400049cc  mov     byte ptr [rax-45h], 0E0h
0x1400049d0  call    cs:__imp_IoAllocateMdl
0x1400049d7  nop     dword ptr [rax+rax+00h]
0x1400049dc  mov     [rdi+8], rax
0x1400049e0  test    rax, rax
0x1400049e3  jnz     loc_140004A7D
0x1400049e9  mov     rcx, [rsi+8]; DeviceObject
0x1400049ed  mov     rdx, rdi; Tag
0x1400049f0  call    cs:__imp_ClassReleaseRemoveLock
0x1400049f7  nop     dword ptr [rax+rax+00h]
0x1400049fc  xor     edx, edx; Tag
0x1400049fe  mov     rcx, rbx; P
0x140004a01  call    cs:__imp_ExFreePoolWithTag
0x140004a08  nop     dword ptr [rax+rax+00h]
0x140004a0d  xor     edx, edx; Tag
0x140004a0f  mov     rcx, rbp; P
0x140004a12  call    cs:__imp_ExFreePoolWithTag
0x140004a19  nop     dword ptr [rax+rax+00h]
0x140004a1e  xor     edx, edx; Tag
0x140004a20  mov     rcx, r14; P
0x140004a23  call    cs:__imp_ExFreePoolWithTag
0x140004a2a  nop     dword ptr [rax+rax+00h]
0x140004a2f  mov     rcx, rdi; Irp
0x140004a32  call    cs:__imp_IoFreeIrp
0x140004a39  nop     dword ptr [rax+rax+00h]
0x140004a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140004a45  lea     rax, WPP_GLOBAL_Control
0x140004a4c  cmp     rcx, rax
0x140004a4f  jz      short loc_140004A73
0x140004a51  mov     eax, [rcx+2Ch]
0x140004a54  test    al, 40h
0x140004a56  jz      short loc_140004A73
0x140004a58  cmp     byte ptr [rcx+29h], 3
0x140004a5c  jb      short loc_140004A73
0x140004a5e  mov     edx, 1Dh
0x140004a63  mov     rcx, [rcx+18h]
0x140004a67  lea     r8, WPP_a9711c54c416383df697b4e008bb3725_Traceguids
0x140004a6e  call    WPP_SF_
0x140004a73  mov     eax, 0C000009Ah
0x140004a78  jmp     loc_140004C86
0x140004a7d  mov     rcx, rax; MemoryDescriptorList
0x140004a80  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140004a87  nop     dword ptr [rax+rax+00h]
0x140004a8c  mov     rax, [rsi+210h]
0x140004a93  cmp     [rax+1Eh], r13b
0x140004a97  jnz     loc_140004BF2
0x140004a9d  mov     rcx, rdi; Irp
0x140004aa0  mov     word ptr [rbx], 8
0x140004aa5  mov     byte ptr [rbx+2], 28h ; '('
0x140004aa9  mov     dword ptr [rbx+8], 53524258h
0x140004ab0  mov     [rbx+0Ch], r13d
0x140004ab4  mov     [rbx+10h], r15d
0x140004ab8  mov     dword ptr [rbx+14h], 0
0x140004abf  call    cs:__imp_IoGetIoPriorityHint
0x140004ac6  nop     dword ptr [rax+rax+00h]
0x140004acb  mov     [rbx+24h], ax
0x140004acf  mov     dword ptr [rbx+34h], 80h
0x140004ad6  mov     [rbx+38h], r13d
0x140004ada  mov     eax, [rsi+248h]
0x140004ae0  mov     [rbx+28h], eax
0x140004ae3  mov     dword ptr [rbx+3Ch], 0C0h
0x140004aea  mov     [rbx+40h], rbp
0x140004aee  mov     eax, [rsi+250h]
0x140004af4  or      eax, 148h
0x140004af9  mov     dword ptr [rbx+20h], 0FFh
0x140004b00  mov     [rbx+18h], eax
0x140004b03  mov     eax, 20h ; ' '
0x140004b08  mov     [rbx+26h], ax
0x140004b0c  mov     [rbx+50h], rdi
0x140004b10  mov     [rbx+80h], r13w
0x140004b18  mov     dword ptr [rbx+84h], 4
0x140004b22  mov     dword ptr [rbx+78h], 90h
0x140004b29  cmp     dword ptr [rbx+10h], 0B8h
0x140004b30  jb      short loc_140004B5E
0x140004b32  mov     dword ptr [rbx+90h], 40h ; '@'
0x140004b3c  lea     rdx, [rbx+0A8h]
0x140004b43  mov     [rbx+94h], eax
0x140004b49  mov     word ptr [rbx+99h], 612h
0x140004b52  mov     [rbx+0A0h], r14
0x140004b59  jmp     loc_140004C37
0x140004b5e  mov     rcx, [rsi+8]; DeviceObject
0x140004b62  mov     rdx, rdi; Tag
0x140004b65  call    cs:__imp_ClassReleaseRemoveLock
0x140004b6c  nop     dword ptr [rax+rax+00h]
0x140004b71  xor     edx, edx; Tag
0x140004b73  mov     rcx, rbx; P
0x140004b76  call    cs:__imp_ExFreePoolWithTag
0x140004b7d  nop     dword ptr [rax+rax+00h]
0x140004b82  xor     edx, edx; Tag
0x140004b84  mov     rcx, rbp; P
0x140004b87  call    cs:__imp_ExFreePoolWithTag
0x140004b8e  nop     dword ptr [rax+rax+00h]
0x140004b93  xor     edx, edx; Tag
0x140004b95  mov     rcx, r14; P
0x140004b98  call    cs:__imp_ExFreePoolWithTag
0x140004b9f  nop     dword ptr [rax+rax+00h]
0x140004ba4  mov     rcx, rdi; Irp
0x140004ba7  call    cs:__imp_IoFreeIrp
0x140004bae  nop     dword ptr [rax+rax+00h]
0x140004bb3  mov     rcx, cs:WPP_GLOBAL_Control
0x140004bba  lea     rax, WPP_GLOBAL_Control
0x140004bc1  cmp     rcx, rax
0x140004bc4  jz      short loc_140004BE8
0x140004bc6  mov     eax, [rcx+2Ch]
0x140004bc9  test    al, 40h
0x140004bcb  jz      short loc_140004BE8
0x140004bcd  cmp     byte ptr [rcx+29h], 3
0x140004bd1  jb      short loc_140004BE8
0x140004bd3  mov     rcx, [rcx+18h]
0x140004bd7  lea     r8, WPP_a9711c54c416383df697b4e008bb3725_Traceguids
0x140004bde  mov     edx, 1Eh
0x140004be3  call    WPP_SF_
0x140004be8  mov     eax, 0C00000E5h
0x140004bed  jmp     loc_140004C86
0x140004bf2  mov     word ptr [rbx], 58h ; 'X'
0x140004bf7  lea     rdx, [rbx+48h]
0x140004bfb  mov     byte ptr [rbx+2], 0
0x140004bff  mov     byte ptr [rbx+0Bh], 12h
0x140004c03  mov     [rbx+20h], r14
0x140004c07  mov     eax, [rsi+248h]
0x140004c0d  mov     [rbx+14h], eax
0x140004c10  mov     dword ptr [rbx+10h], 0C0h
  ... truncated ...
```
