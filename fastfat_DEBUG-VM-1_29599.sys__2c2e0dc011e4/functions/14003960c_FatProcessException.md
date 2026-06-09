# FatProcessException

- ea: `0x14003960c`
- end: `0x140039ad0`
- name: `FatProcessException`
- size: `1220`
- prototype: `__int64 __fastcall(PVOID Entry, PIRP Irp)`
- caller_count: `21`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140006030`
- `0x140007530`
- `0x140025a90`
- `0x1400260d0`
- `0x14002a4b0`
- `0x14002d3f0`
- `0x14002ea00`
- `0x1400345b0`
- `0x14003816c`
- `0x14003a550`
- `0x14003a610`
- `0x14003e9d0`
- `0x14003f2c0`
- `0x1400438e0`
- `0x140044460`
- `0x140045130`
- `0x140046500`
- `0x140046fb0`
- `0x140049d44`
- `0x14004a8f0`
- `0x14004a9b0`

## callees

- `0x140005288`
- `0x140006dbc`
- `0x140007408`
- `0x14002486c`
- `0x140038eb4`
- `0x14003960c`
- `0x14003d880`
- `0x1400465f4`
- `0x1400466c8`
- `0x1400483bc`
- `0x140049d44`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400397d2`
- `ntoskrnl!KeSetEvent` at `0x1400397fc`
- `ntoskrnl!KeSetEvent` at `0x1400397d2`
- `ntoskrnl!KeSetEvent` at `0x1400397fc`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140039815`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140039815`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400398be`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400398be`
- `ntoskrnl!CcMdlWriteAbort` at `0x140039686`
- `ntoskrnl!CcMdlWriteAbort` at `0x140039686`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400396c2`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400396c2`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140039987`
- `ntoskrnl!IoGetDeviceToVerify` at `0x1400399b9`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140039a44`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140039a61`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140039987`
- `ntoskrnl!IoGetDeviceToVerify` at `0x1400399b9`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140039a44`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140039a61`
- `ntoskrnl!IoSetDeviceToVerify` at `0x14003999f`
- `ntoskrnl!IoSetDeviceToVerify` at `0x1400399d0`
- `ntoskrnl!IoSetDeviceToVerify` at `0x140039ab2`
- `ntoskrnl!IoSetDeviceToVerify` at `0x14003999f`
- `ntoskrnl!IoSetDeviceToVerify` at `0x1400399d0`
- `ntoskrnl!IoSetDeviceToVerify` at `0x140039ab2`
- `ntoskrnl!IoRaiseHardError` at `0x140039aa1`
- `ntoskrnl!IoRaiseHardError` at `0x140039aa1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400397e2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140039967`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400397e2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140039967`

## pseudocode

```c
__int64 __fastcall FatProcessException(_DWORD *Entry, struct _MDL *Irp, __int64 a3, __int64 a4)
{
  unsigned int v4; // ebx
  PIRP v5; // r15
  __int64 v6; // rdi
  __int64 result; // rax
  NTSTATUS v8; // esi
  _BYTE *v9; // r12
  __int64 v10; // r8
  __int64 v11; // r9
  PFILE_OBJECT FileObject; // rcx
  __int64 v13; // r13
  int v14; // ecx
  __int64 v15; // rbx
  int v16; // r12d
  PDEVICE_OBJECT DeviceObject; // rcx
  PDEVICE_OBJECT DeviceToVerify; // rbx
  __int64 v19; // rax
  struct _DEVICE_OBJECT *v20; // r8
  PFILE_OBJECT v21; // rcx
  struct _VPB *Vpb; // r12
  struct _KTHREAD *Thread; // rbx
  __int64 v24; // rax
  struct _DEVICE_OBJECT *v25; // r8
  int v26; // [rsp+20h] [rbp-58h]
  __int64 v27; // [rsp+28h] [rbp-50h] BYREF
  _QWORD v28[9]; // [rsp+30h] [rbp-48h] BYREF
  char *v29; // [rsp+98h] [rbp+20h] BYREF

  v4 = a3;
  v5 = (PIRP)Irp;
  v6 = (__int64)Entry;
  if ( !Entry )
    goto LABEL_2;
  v8 = Entry[18];
  Entry[18] = 0;
  v9 = Entry + 16;
  v29 = (char *)(Entry + 16);
  if ( *((_BYTE *)Entry + 64) == 4 && (*((_BYTE *)Entry + 65) & 6) == 6 )
  {
    Irp = *(struct _MDL **)&Irp->Size;
    if ( Irp )
    {
      CcMdlWriteAbort(v5->Tail.Overlay.CurrentStackLocation->FileObject, Irp);
      v5->MdlAddress = 0;
    }
  }
  v26 = *(_DWORD *)(v6 + 68);
  *(_DWORD *)(v6 + 68) = v26 | 8;
  FatUnpinRepinnedBcbs(v6, Irp, a3, a4);
  *(_DWORD *)(v6 + 68) = v26;
  if ( (v26 & 0x10) == 0 && (v8 == -2147483626 && KeAreAllApcsDisabled() || v8 == -1073741608) )
    v8 = FatFsdPostRequest((PVOID)v6, v5);
  result = 259;
  if ( v8 != 259 )
  {
    v5->IoStatus.Status = v8;
    if ( (byte_140017D4D & 2) != 0 && !*v9 && (*(_DWORD *)(v6 + 68) & 0x8000) != 0 )
    {
      FileObject = v5->Tail.Overlay.CurrentStackLocation->FileObject;
      if ( FileObject )
      {
        v27 = 0;
        v28[0] = 0;
        v29 = 0;
        FatDecodeFileObject(FileObject, &v29, &v27, v28);
        v13 = v27;
        if ( v27 )
        {
          FatAcquireExclusiveFcb(v6, v27);
          *(_DWORD *)(v13 + 192) &= ~0x100000u;
          KeSetEvent(&Event, 0, 0);
          ExReleaseResourceLite(*(PERESOURCE *)(v13 + 8));
        }
        else
        {
          KeSetEvent(&Event, 0, 0);
        }
      }
    }
    v14 = *(_DWORD *)(v6 + 68);
    if ( (v14 & 0x10) != 0 )
    {
      if ( IoGetTopLevelIrp() == (PIRP)2 && v8 == -2147483626 )
        v8 = -1073741740;
LABEL_24:
      FatCompleteRequest_Real((PVOID)v6, v5, (unsigned int)v8, v11);
      return (unsigned int)v8;
    }
    if ( (unsigned int)(v8 + 1073741662) <= 1 || v8 == -1073741643 || (unsigned int)(v8 + 1073741806) <= 2 )
    {
      if ( v8 != -2147483626 )
      {
        if ( (v14 & 0x20) == 0 )
        {
          v21 = v5->Tail.Overlay.CurrentStackLocation->FileObject;
          if ( v21 )
            Vpb = v21->Vpb;
          else
            Vpb = 0;
          Thread = v5->Tail.Overlay.Thread;
          if ( !IoGetDeviceToVerify(Thread) )
          {
            Thread = KeGetCurrentThread();
            IoGetDeviceToVerify(Thread);
          }
          v24 = *(_QWORD *)(v6 + 56);
          v25 = v24 ? *(struct _DEVICE_OBJECT **)(*(_QWORD *)(v24 + 192) + 16LL) : *(struct _DEVICE_OBJECT **)(v6 + 48);
          if ( v25 )
          {
            v5->Tail.Overlay.CurrentStackLocation->Control |= 1u;
            IoRaiseHardError(v5, Vpb, v25);
            IoSetDeviceToVerify(Thread, 0);
            FatDeleteIrpContext_Real((PVOID)v6);
            return 259;
          }
        }
        goto LABEL_24;
      }
    }
    else if ( v8 != -2147483626 )
    {
      v15 = *(_QWORD *)(v6 + 56);
      v29 = (char *)v15;
      if ( v15 )
      {
        v16 = 1;
        DeviceObject = v5->Tail.Overlay.CurrentStackLocation->DeviceObject;
        if ( DeviceObject != (PDEVICE_OBJECT)qword_140017CC8
          && DeviceObject != (PDEVICE_OBJECT)qword_140017CD0
          && v8 < 0
          && !FsRtlIsTotalDeviceFailure(v8) )
        {
          v16 = 2;
        }
        if ( (*(_DWORD *)(v6 + 68) & 0x20) == 0
          && (v16 == 2
           || v8 == -1073741566
           || v8 == -1073741774
           || (unsigned int)(v8 + 1073741742) <= 1
           || (unsigned int)(v8 + 2147483629) <= 1) )
        {
          _InterlockedOr((volatile signed __int32 *)(v15 + 200), 0x10u);
          *(_DWORD *)(v6 + 68) |= 2u;
          LOBYTE(v10) = 1;
          FatAcquireExclusiveVcb_Real(v6, v15, v10);
          if ( *(_DWORD *)(v15 + 204) == 1 )
            FatMarkVolume(v6, v15, v16);
          ExReleaseResourceLite((PERESOURCE)(v15 + 520));
        }
      }
      goto LABEL_24;
    }
    DeviceToVerify = IoGetDeviceToVerify(v5->Tail.Overlay.Thread);
    IoSetDeviceToVerify(v5->Tail.Overlay.Thread, 0);
    if ( !DeviceToVerify )
    {
      IoGetDeviceToVerify(KeGetCurrentThread());
      IoSetDeviceToVerify(KeGetCurrentThread(), 0);
    }
    v19 = *(_QWORD *)(v6 + 56);
    if ( v19 )
      v20 = *(struct _DEVICE_OBJECT **)(*(_QWORD *)(v19 + 192) + 16LL);
    else
      v20 = *(struct _DEVICE_OBJECT **)(v6 + 48);
    Irp = (struct _MDL *)v5;
    Entry = (_DWORD *)v6;
    if ( !v20 )
    {
      v4 = -1073741437;
      a3 = 3221225859LL;
LABEL_2:
      FatCompleteRequest_Real(Entry, (PIRP)Irp, a3, a4);
      return v4;
    }
    return FatPerformVerify((PVOID)v6, v5, v20);
  }
  return result;
}

```

## disassembly

```asm
0x14003960c  mov     [rsp+arg_8], rdx
0x140039611  mov     [rsp+arg_0], rcx
0x140039616  push    rbx
0x140039617  push    rsi
0x140039618  push    rdi
0x140039619  push    r12
0x14003961b  push    r13
0x14003961d  push    r15
0x14003961f  sub     rsp, 48h
0x140039623  mov     ebx, r8d
0x140039626  mov     r15, rdx
0x140039629  mov     rdi, rcx
0x14003962c  test    rcx, rcx
0x14003962f  jnz     short loc_14003963D
0x140039631  call    FatCompleteRequest_Real
0x140039636  mov     eax, ebx
0x140039638  jmp     loc_140039841
0x14003963d  mov     [rsp+78h+var_58], 0
0x140039645  mov     esi, [rcx+48h]
0x140039648  mov     [rsp+78h+arg_10], esi
0x14003964f  mov     dword ptr [rcx+48h], 0
0x140039656  lea     r12, [rcx+40h]
0x14003965a  mov     [rsp+78h+arg_18], r12
0x140039662  cmp     byte ptr [r12], 4
0x140039667  jnz     short loc_14003969A
0x140039669  mov     al, [rcx+41h]
0x14003966c  and     al, 6
0x14003966e  cmp     al, 6
0x140039670  jnz     short loc_14003969A
0x140039672  mov     rdx, [rdx+8]; MdlChain
0x140039676  test    rdx, rdx
0x140039679  jz      short loc_14003969A
0x14003967b  mov     rcx, [r15+0B8h]
0x140039682  mov     rcx, [rcx+30h]; FileObject
0x140039686  call    cs:__imp_CcMdlWriteAbort
0x14003968d  nop     dword ptr [rax+rax+00h]
0x140039692  mov     qword ptr [r15+8], 0
0x14003969a  mov     ebx, [rdi+44h]
0x14003969d  mov     [rsp+78h+var_58], ebx
0x1400396a1  mov     eax, ebx
0x1400396a3  or      eax, 8
0x1400396a6  mov     [rdi+44h], eax
0x1400396a9  mov     rcx, rdi
0x1400396ac  call    FatUnpinRepinnedBcbs
0x1400396b1  mov     [rdi+44h], ebx
0x1400396b4  test    bl, 10h
0x1400396b7  mov     ebx, 80000016h
0x1400396bc  jnz     short loc_1400396EE
0x1400396be  cmp     esi, ebx
0x1400396c0  jnz     short loc_1400396D2
0x1400396c2  call    cs:__imp_KeAreAllApcsDisabled
0x1400396c9  nop     dword ptr [rax+rax+00h]
0x1400396ce  test    al, al
0x1400396d0  jnz     short loc_1400396DA
0x1400396d2  cmp     esi, 0C00000D8h
0x1400396d8  jnz     short loc_1400396EE
0x1400396da  mov     rdx, r15; Context2
0x1400396dd  mov     rcx, rdi; Context1
0x1400396e0  call    FatFsdPostRequest
0x1400396e5  mov     esi, eax
0x1400396e7  mov     [rsp+78h+arg_10], eax
0x1400396ee  jmp     short loc_140039725
0x1400396f0  mov     rdi, [rsp+78h+arg_0]
0x1400396f8  mov     esi, [rdi+48h]
0x1400396fb  mov     [rsp+78h+arg_10], esi
0x140039702  mov     dword ptr [rdi+48h], 0
0x140039709  mov     eax, [rsp+78h+var_58]
0x14003970d  mov     [rdi+44h], eax
0x140039710  mov     ebx, 80000016h
0x140039715  mov     r15, [rsp+78h+arg_8]
0x14003971d  mov     r12, [rsp+78h+arg_18]
0x140039725  mov     eax, 103h
0x14003972a  cmp     esi, eax
0x14003972c  jz      loc_140039841
0x140039732  mov     [r15+30h], esi
0x140039736  mov     edx, 2
0x14003973b  test    cs:byte_140017D4D, dl
0x140039741  jz      loc_14003980D
0x140039747  cmp     byte ptr [r12], 0
0x14003974c  jnz     loc_14003980D
0x140039752  test    dword ptr [rdi+44h], 8000h
0x140039759  jz      loc_14003980D
0x14003975f  mov     rax, [r15+0B8h]
0x140039766  mov     rcx, [rax+30h]
0x14003976a  test    rcx, rcx
0x14003976d  jz      loc_14003980D
0x140039773  mov     [rsp+78h+var_50], 0
0x14003977c  mov     [rsp+78h+var_48], 0
0x140039785  mov     [rsp+78h+arg_18], 0
0x140039791  lea     r9, [rsp+78h+var_48]
0x140039796  lea     r8, [rsp+78h+var_50]
0x14003979b  lea     rdx, [rsp+78h+arg_18]
0x1400397a3  call    FatDecodeFileObject
0x1400397a8  mov     r13, [rsp+78h+var_50]
0x1400397ad  test    r13, r13
0x1400397b0  jz      short loc_1400397F0
0x1400397b2  mov     rdx, r13
0x1400397b5  mov     rcx, rdi
0x1400397b8  call    FatAcquireExclusiveFcb
0x1400397bd  btr     dword ptr [r13+0C0h], 14h
0x1400397c6  xor     r8d, r8d; Wait
0x1400397c9  xor     edx, edx; Increment
0x1400397cb  lea     rcx, Event; Event
0x1400397d2  call    cs:__imp_KeSetEvent
0x1400397d9  nop     dword ptr [rax+rax+00h]
0x1400397de  mov     rcx, [r13+8]; Resource
0x1400397e2  call    cs:__imp_ExReleaseResourceLite
0x1400397e9  nop     dword ptr [rax+rax+00h]
0x1400397ee  jmp     short loc_140039808
0x1400397f0  xor     r8d, r8d; Wait
0x1400397f3  xor     edx, edx; Increment
0x1400397f5  lea     rcx, Event; Event
0x1400397fc  call    cs:__imp_KeSetEvent
0x140039803  nop     dword ptr [rax+rax+00h]
0x140039808  mov     edx, 2
0x14003980d  mov     ecx, [rdi+44h]
0x140039810  test    cl, 10h
0x140039813  jz      short loc_140039850
0x140039815  call    cs:__imp_IoGetTopLevelIrp
0x14003981c  nop     dword ptr [rax+rax+00h]
0x140039821  cmp     rax, 2
0x140039825  jnz     short loc_140039831
0x140039827  mov     eax, 0C0000054h
0x14003982c  cmp     esi, ebx
0x14003982e  cmovz   esi, eax
0x140039831  mov     r8d, esi
0x140039834  mov     rdx, r15; Irp
0x140039837  mov     rcx, rdi; Entry
0x14003983a  call    FatCompleteRequest_Real
0x14003983f  mov     eax, esi
0x140039841  add     rsp, 48h
0x140039845  pop     r15
0x140039847  pop     r13
0x140039849  pop     r12
0x14003984b  pop     rdi
0x14003984c  pop     rsi
0x14003984d  pop     rbx
0x14003984e  retn
0x140039850  lea     eax, [rsi+3FFFFF5Eh]
0x140039856  mov     r13d, 1
0x14003985c  cmp     eax, r13d
0x14003985f  jbe     loc_140039978
0x140039865  cmp     esi, 0C00000B5h
0x14003986b  jz      loc_140039978
0x140039871  lea     eax, [rsi+3FFFFFEEh]
0x140039877  cmp     eax, edx
0x140039879  jbe     loc_140039978
0x14003987f  cmp     esi, ebx
0x140039881  jz      loc_140039980
0x140039887  mov     rbx, [rdi+38h]
0x14003988b  mov     [rsp+78h+arg_18], rbx
0x140039893  test    rbx, rbx
0x140039896  jz      short loc_140039831
0x140039898  mov     r12d, r13d
0x14003989b  mov     rax, [r15+0B8h]
0x1400398a2  mov     rcx, [rax+28h]
0x1400398a6  cmp     rcx, cs:qword_140017CC8
0x1400398ad  jz      short loc_1400398D4
0x1400398af  cmp     rcx, cs:qword_140017CD0
0x1400398b6  jz      short loc_1400398D4
0x1400398b8  test    esi, esi
0x1400398ba  jns     short loc_1400398D4
0x1400398bc  mov     ecx, esi; Status
0x1400398be  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x1400398c5  nop     dword ptr [rax+rax+00h]
0x1400398ca  test    al, al
0x1400398cc  lea     edx, [r13+1]
0x1400398d0  cmovz   r12d, edx
0x1400398d4  mov     eax, [rdi+44h]
0x1400398d7  test    al, 20h
0x1400398d9  jnz     loc_140039831
0x1400398df  cmp     r12d, edx
0x1400398e2  jz      short loc_14003990E
0x1400398e4  cmp     esi, 0C0000102h
0x1400398ea  jz      short loc_14003990E
0x1400398ec  cmp     esi, 0C0000032h
0x1400398f2  jz      short loc_14003990E
0x1400398f4  lea     eax, [rsi+3FFFFFAEh]
0x1400398fa  cmp     eax, r13d
0x1400398fd  jbe     short loc_14003990E
0x1400398ff  lea     eax, [rsi+7FFFFFEDh]
0x140039905  cmp     eax, r13d
0x140039908  ja      loc_140039831
0x14003990e  lock or dword ptr [rbx+0C8h], 10h
0x140039916  or      [rdi+44h], edx
0x140039919  mov     r8b, r13b
0x14003991c  mov     rdx, rbx
0x14003991f  mov     rcx, rdi
0x140039922  call    FatAcquireExclusiveVcb_Real
0x140039927  nop
0x140039928  cmp     [rbx+0CCh], r13d
0x14003992f  jnz     short loc_14003993F
0x140039931  mov     r8d, r12d
0x140039934  mov     rdx, rbx
0x140039937  mov     rcx, rdi
0x14003993a  call    FatMarkVolume
0x14003993f  jmp     short loc_140039960
0x140039941  mov     esi, [rsp+78h+arg_10]
0x140039948  mov     r15, [rsp+78h+arg_8]
0x140039950  mov     rdi, [rsp+78h+arg_0]
0x140039958  mov     rbx, [rsp+78h+arg_18]
0x140039960  lea     rcx, [rbx+208h]; Resource
0x140039967  call    cs:__imp_ExReleaseResourceLite
0x14003996e  nop     dword ptr [rax+rax+00h]
0x140039973  jmp     loc_140039831
0x140039978  cmp     esi, ebx
0x14003997a  jnz     loc_140039A18
0x140039980  mov     rcx, [r15+98h]; Thread
0x140039987  call    cs:__imp_IoGetDeviceToVerify
0x14003998e  nop     dword ptr [rax+rax+00h]
0x140039993  mov     rbx, rax
0x140039996  xor     edx, edx; DeviceObject
0x140039998  mov     rcx, [r15+98h]; Thread
0x14003999f  call    cs:__imp_IoSetDeviceToVerify
0x1400399a6  nop     dword ptr [rax+rax+00h]
0x1400399ab  test    rbx, rbx
0x1400399ae  jnz     short loc_1400399DC
0x1400399b0  mov     rcx, gs:188h; Thread
0x1400399b9  call    cs:__imp_IoGetDeviceToVerify
0x1400399c0  nop     dword ptr [rax+rax+00h]
0x1400399c5  mov     rcx, gs:188h; Thread
0x1400399ce  xor     edx, edx; DeviceObject
0x1400399d0  call    cs:__imp_IoSetDeviceToVerify
0x1400399d7  nop     dword ptr [rax+rax+00h]
0x1400399dc  mov     rax, [rdi+38h]
0x1400399e0  test    rax, rax
0x1400399e3  jz      short loc_1400399F2
0x1400399e5  mov     rax, [rax+0C0h]
0x1400399ec  mov     r8, [rax+10h]
0x1400399f0  jmp     short loc_1400399F6
0x1400399f2  mov     r8, [rdi+30h]; DeviceObject
0x1400399f6  mov     rdx, r15; Irp
0x1400399f9  mov     rcx, rdi; Entry
0x1400399fc  test    r8, r8
0x1400399ff  jnz     short loc_140039A0E
0x140039a01  mov     ebx, 0C0000183h
0x140039a06  mov     r8d, ebx
0x140039a09  jmp     loc_140039631
0x140039a0e  call    FatPerformVerify
0x140039a13  jmp     loc_140039841
0x140039a18  test    cl, 20h
0x140039a1b  jnz     loc_140039831
0x140039a21  mov     rax, [r15+0B8h]
0x140039a28  mov     rcx, [rax+30h]
0x140039a2c  test    rcx, rcx
0x140039a2f  jz      short loc_140039A37
0x140039a31  mov     r12, [rcx+10h]
0x140039a35  jmp     short loc_140039A3A
0x140039a37  xor     r12d, r12d
0x140039a3a  mov     rbx, [r15+98h]
0x140039a41  mov     rcx, rbx; Thread
0x140039a44  call    cs:__imp_IoGetDeviceToVerify
0x140039a4b  nop     dword ptr [rax+rax+00h]
0x140039a50  test    rax, rax
0x140039a53  jnz     short loc_140039A6D
0x140039a55  mov     rbx, gs:188h
0x140039a5e  mov     rcx, rbx; Thread
0x140039a61  call    cs:__imp_IoGetDeviceToVerify
0x140039a68  nop     dword ptr [rax+rax+00h]
0x140039a6d  mov     rax, [rdi+38h]
0x140039a71  test    rax, rax
0x140039a74  jz      short loc_140039A83
0x140039a76  mov     rax, [rax+0C0h]
0x140039a7d  mov     r8, [rax+10h]
0x140039a81  jmp     short loc_140039A87
0x140039a83  mov     r8, [rdi+30h]; RealDeviceObject
0x140039a87  test    r8, r8
0x140039a8a  jz      loc_140039831
0x140039a90  mov     rax, [r15+0B8h]
0x140039a97  or      [rax+3], r13b
0x140039a9b  mov     rdx, r12; Vpb
0x140039a9e  mov     rcx, r15; Irp
0x140039aa1  call    cs:__imp_IoRaiseHardError
0x140039aa8  nop     dword ptr [rax+rax+00h]
0x140039aad  xor     edx, edx; DeviceObject
0x140039aaf  mov     rcx, rbx; Thread
0x140039ab2  call    cs:__imp_IoSetDeviceToVerify
0x140039ab9  nop     dword ptr [rax+rax+00h]
0x140039abe  mov     rcx, rdi; Entry
0x140039ac1  call    FatDeleteIrpContext_Real
0x140039ac6  mov     eax, 103h
0x140039acb  jmp     loc_140039841
0x14005e2a3  push    rbp
0x14005e2a5  sub     rsp, 20h
0x14005e2a9  mov     rbp, rdx
0x14005e2ac  mov     rdx, rcx
0x14005e2af  mov     rcx, [rbp+80h]
0x14005e2b6  call    FatExceptionFilter
0x14005e2bb  nop
0x14005e2bc  add     rsp, 20h
0x14005e2c0  pop     rbp
0x14005e2c1  retn
0x14005e2c3  push    rbp
0x14005e2c5  sub     rsp, 20h
0x14005e2c9  mov     rbp, rdx
0x14005e2cc  mov     rdx, rcx
0x14005e2cf  mov     rcx, [rbp+80h]
0x14005e2d6  call    FatExceptionFilter
0x14005e2db  nop
0x14005e2dc  add     rsp, 20h
  ... truncated ...
```
