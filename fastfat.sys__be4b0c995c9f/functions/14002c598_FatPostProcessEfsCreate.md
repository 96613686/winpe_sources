# FatPostProcessEfsCreate

- ea: `0x14002c598`
- end: `0x14002c907`
- name: `FatPostProcessEfsCreate`
- size: `879`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14002a4b0`
- `0x1400438e0`

## callees

- `0x14000326c`
- `0x14002c598`
- `0x140039550`
- `0x14003d880`
- `0x1400465f4`
- `0x1400466c8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14002c6a6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002c786`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002c86d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005cb1c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002c6a6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002c786`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002c86d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005cb1c`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14002c8d7`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14005cb92`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14002c8d7`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14005cb92`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002c75f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002c8e7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005cba5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002c75f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002c8e7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005cba5`
- `ntoskrnl!IoRemoveShareAccess` at `0x14002c6da`
- `ntoskrnl!IoRemoveShareAccess` at `0x14002c6da`
- `ntoskrnl!IoCheckShareAccess` at `0x14002c73c`
- `ntoskrnl!IoCheckShareAccess` at `0x14002c73c`
- `ntoskrnl!KeSetEvent` at `0x14002c89a`
- `ntoskrnl!KeSetEvent` at `0x14002c8c4`
- `ntoskrnl!KeSetEvent` at `0x14005cb53`
- `ntoskrnl!KeSetEvent` at `0x14005cb7d`
- `ntoskrnl!KeSetEvent` at `0x14002c89a`
- `ntoskrnl!KeSetEvent` at `0x14002c8c4`
- `ntoskrnl!KeSetEvent` at `0x14005cb53`
- `ntoskrnl!KeSetEvent` at `0x14005cb7d`
- `ntoskrnl!IoCancelFileOpen` at `0x14002c82f`
- `ntoskrnl!IoCancelFileOpen` at `0x14002c82f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002c753`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002c7d6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002c7ff`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002c812`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002c8aa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005cb63`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002c753`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002c7d6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002c7ff`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002c812`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002c8aa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005cb63`

## pseudocode

```c
__int64 __fastcall FatPostProcessEfsCreate(__int64 a1, IRP *a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rdi
  NTSTATUS Callback; // r14d
  char v7; // bl
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  struct _FILE_OBJECT *FileObject; // r12
  __int64 v10; // r15
  BOOLEAN DeleteAccess; // bl
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // r9
  char IsIrpTopLevel; // r13
  __int64 v16; // r8
  __int64 v17; // r9
  char v18; // cl
  __int64 v20; // [rsp+48h] [rbp-50h] BYREF
  __int64 v21; // [rsp+50h] [rbp-48h] BYREF
  __int64 v22[8]; // [rsp+58h] [rbp-40h] BYREF
  int v24; // [rsp+B0h] [rbp+18h]
  int v25; // [rsp+B8h] [rbp+20h]

  v25 = a4;
  v24 = a3;
  v21 = 0;
  v5 = 0;
  v20 = 0;
  v22[0] = 0;
  Callback = 0;
  v7 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  if ( !FileObject )
    goto LABEL_18;
  if ( (unsigned int)FatDecodeFileObject(CurrentStackLocation->FileObject, &v21, &v20, v22) - 2 > 1
    || !*(_QWORD *)(a1 + 128) )
  {
    v5 = v20;
LABEL_18:
    IsIrpTopLevel = 0;
    goto LABEL_19;
  }
  v10 = v21;
  Callback = EfsPostCreateCallback(
               v24,
               *(_QWORD *)(v21 + 136),
               (_DWORD)a2,
               a2->Tail.Overlay.CurrentStackLocation->FileObject,
               v25,
               v21 + 160,
               a1 + 128);
  if ( Callback == -1073741790
    && (*(_DWORD *)(*(_QWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 8) + 24LL) & 0x2000000) != 0
    && a2->IoStatus.Information == 1 )
  {
    DeleteAccess = CurrentStackLocation->FileObject->DeleteAccess;
    KeEnterCriticalRegion();
    v5 = v20;
    FatAcquireExclusiveFcb(a1, v20, v12, v13);
    Callback = 0;
    IoRemoveShareAccess(CurrentStackLocation->FileObject, (PSHARE_ACCESS)(v5 + 200));
    CurrentStackLocation->FileObject->ReadAccess = 0;
    CurrentStackLocation->FileObject->WriteAccess = 0;
    CurrentStackLocation->FileObject->DeleteAccess = 0;
    CurrentStackLocation->FileObject->SharedRead = 0;
    CurrentStackLocation->FileObject->SharedWrite = 0;
    CurrentStackLocation->FileObject->SharedDelete = 0;
    *(_DWORD *)(*(_QWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 8) + 20LL) &= 0xFFFFFFD8;
    if ( DeleteAccess )
      Callback = IoCheckShareAccess(
                   0x10000u,
                   CurrentStackLocation->Parameters.Create.ShareAccess,
                   CurrentStackLocation->FileObject,
                   (PSHARE_ACCESS)(v5 + 200),
                   1u);
    ExReleaseResourceLite(*(PERESOURCE *)(v5 + 8));
    KeLeaveCriticalRegion();
  }
  else
  {
    v5 = v20;
  }
  v7 = 0;
  if ( Callback >= 0 )
    goto LABEL_18;
  KeEnterCriticalRegion();
  v7 = 1;
  IsIrpTopLevel = FatIsIrpTopLevel(a2);
  if ( (*(_DWORD *)(a1 + 136) & 5) == 0 )
  {
LABEL_16:
    *(_DWORD *)(a1 + 68) |= 0x40000u;
    IoCancelFileOpen(FileObject->Vpb->DeviceObject, FileObject);
    *(_DWORD *)(a1 + 68) &= ~0x40000u;
    v18 = 0;
    goto LABEL_20;
  }
  FatAcquireExclusiveVcb_Real(a1, v10, 0, v14);
  if ( *(_DWORD *)(v10 + 204) == 1 )
  {
    FatAcquireExclusiveFcb(a1, v5, v16, v17);
    *(_DWORD *)(v5 + 192) |= 1u;
    FileObject->DeletePending = 1;
    ExReleaseResourceLite(*(PERESOURCE *)(v5 + 8));
    ExReleaseResourceLite((PERESOURCE)(v10 + 520));
    goto LABEL_16;
  }
  ExReleaseResourceLite((PERESOURCE)(v10 + 520));
LABEL_19:
  v18 = 1;
LABEL_20:
  if ( (*(_DWORD *)(a1 + 136) & 5) != 0 )
  {
    if ( v5 && v18 )
    {
      if ( !v7 )
      {
        KeEnterCriticalRegion();
        v7 = 1;
      }
      FatAcquireExclusiveFcb(a1, v5, a3, a4);
      *(_DWORD *)(v5 + 192) &= ~0x100000u;
      KeSetEvent(&Event, 0, 0);
      ExReleaseResourceLite(*(PERESOURCE *)(v5 + 8));
    }
    else
    {
      KeSetEvent(&Event, 0, 0);
    }
  }
  if ( IsIrpTopLevel )
    IoSetTopLevelIrp(0);
  if ( v7 )
    KeLeaveCriticalRegion();
  return (unsigned int)Callback;
}

```

## disassembly

```asm
0x14002c598  mov     rax, rsp
0x14002c59b  mov     [rax+20h], r9d
0x14002c59f  mov     [rax+18h], r8
0x14002c5a3  mov     [rax+10h], rdx
0x14002c5a7  mov     [rax+8], rcx
0x14002c5ab  push    rbx
0x14002c5ac  push    rsi
0x14002c5ad  push    rdi
0x14002c5ae  push    r12
0x14002c5b0  push    r13
0x14002c5b2  push    r14
0x14002c5b4  push    r15
0x14002c5b6  sub     rsp, 60h
0x14002c5ba  mov     rsi, rcx
0x14002c5bd  mov     qword ptr [rax-48h], 0
0x14002c5c5  xor     edi, edi
0x14002c5c7  mov     [rax-50h], rdi
0x14002c5cb  mov     [rax-40h], rdi
0x14002c5cf  xor     r14d, r14d
0x14002c5d2  xor     bl, bl
0x14002c5d4  mov     [rax-58h], bl
0x14002c5d7  mov     [rax-56h], bl
0x14002c5da  mov     byte ptr [rax-57h], 1
0x14002c5de  mov     r13, [rdx+0B8h]
0x14002c5e5  mov     r12, [r13+30h]
0x14002c5e9  test    r12, r12
0x14002c5ec  jz      loc_14002C84D
0x14002c5f2  lea     r9, [rax-40h]
0x14002c5f6  lea     r8, [rax-50h]
0x14002c5fa  lea     rdx, [rax-48h]
0x14002c5fe  mov     rcx, r12
0x14002c601  call    FatDecodeFileObject
0x14002c606  add     eax, 0FFFFFFFEh
0x14002c609  cmp     eax, 1
0x14002c60c  ja      loc_14002C848
0x14002c612  lea     rcx, [rsi+80h]
0x14002c619  cmp     [rcx], r14
0x14002c61c  jz      loc_14002C848
0x14002c622  mov     r15, [rsp+98h+var_48]
0x14002c627  lea     rax, [r15+0A0h]
0x14002c62e  mov     rbx, [rsp+98h+Irp]
0x14002c636  mov     r9, [rbx+0B8h]
0x14002c63d  mov     [rsp+98h+var_68], rcx
0x14002c642  mov     [rsp+98h+var_70], rax
0x14002c647  mov     eax, [rsp+98h+arg_18]
0x14002c64e  mov     dword ptr [rsp+98h+Update], eax
0x14002c652  mov     r9, [r9+30h]
0x14002c656  mov     r8, rbx
0x14002c659  mov     rdx, [r15+88h]
0x14002c660  mov     rcx, [rsp+98h+arg_10]
0x14002c668  call    EfsPostCreateCallback
0x14002c66d  mov     r14d, eax
0x14002c670  mov     [rsp+98h+var_54], eax
0x14002c674  cmp     eax, 0C0000022h
0x14002c679  jnz     loc_14002C772
0x14002c67f  mov     rcx, [r13+8]
0x14002c683  mov     rdx, [rcx+8]
0x14002c687  test    dword ptr [rdx+18h], 2000000h
0x14002c68e  jz      loc_14002C772
0x14002c694  cmp     qword ptr [rbx+38h], 1
0x14002c699  jnz     loc_14002C772
0x14002c69f  mov     rax, [r13+30h]
0x14002c6a3  mov     bl, [rax+4Ch]
0x14002c6a6  call    cs:__imp_KeEnterCriticalRegion
0x14002c6ad  nop     dword ptr [rax+rax+00h]
0x14002c6b2  mov     [rsp+98h+var_58], 1
0x14002c6b7  mov     rdi, [rsp+98h+var_50]
0x14002c6bc  mov     rdx, rdi
0x14002c6bf  mov     rcx, rsi
0x14002c6c2  call    FatAcquireExclusiveFcb
0x14002c6c7  xor     r14d, r14d
0x14002c6ca  mov     [rsp+98h+var_54], r14d
0x14002c6cf  lea     rdx, [rdi+0C8h]; ShareAccess
0x14002c6d6  mov     rcx, [r13+30h]; FileObject
0x14002c6da  call    cs:__imp_IoRemoveShareAccess
0x14002c6e1  nop     dword ptr [rax+rax+00h]
0x14002c6e6  mov     rax, [r13+30h]
0x14002c6ea  xor     edx, edx
0x14002c6ec  mov     [rax+4Ah], dl
0x14002c6ef  mov     rax, [r13+30h]
0x14002c6f3  mov     [rax+4Bh], dl
0x14002c6f6  mov     rax, [r13+30h]
0x14002c6fa  mov     [rax+4Ch], dl
0x14002c6fd  mov     rax, [r13+30h]
0x14002c701  mov     [rax+4Dh], dl
0x14002c704  mov     rax, [r13+30h]
0x14002c708  mov     [rax+4Eh], dl
0x14002c70b  mov     rax, [r13+30h]
0x14002c70f  mov     [rax+4Fh], dl
0x14002c712  mov     rax, [r13+8]
0x14002c716  mov     rcx, [rax+8]
0x14002c71a  and     dword ptr [rcx+14h], 0FFFFFFD8h
0x14002c71e  test    bl, bl
0x14002c720  jz      short loc_14002C74F
0x14002c722  movzx   edx, word ptr [r13+1Ah]; DesiredShareAccess
0x14002c727  mov     [rsp+98h+Update], 1; Update
0x14002c72c  lea     r9, [rdi+0C8h]; ShareAccess
0x14002c733  mov     r8, [r13+30h]; FileObject
0x14002c737  mov     ecx, 10000h; DesiredAccess
0x14002c73c  call    cs:__imp_IoCheckShareAccess
0x14002c743  nop     dword ptr [rax+rax+00h]
0x14002c748  mov     r14d, eax
0x14002c74b  mov     [rsp+98h+var_54], eax
0x14002c74f  mov     rcx, [rdi+8]; Resource
0x14002c753  call    cs:__imp_ExReleaseResourceLite
0x14002c75a  nop     dword ptr [rax+rax+00h]
0x14002c75f  call    cs:__imp_KeLeaveCriticalRegion
0x14002c766  nop     dword ptr [rax+rax+00h]
0x14002c76b  mov     [rsp+98h+var_58], 0
0x14002c770  jmp     short loc_14002C777
0x14002c772  mov     rdi, [rsp+98h+var_50]
0x14002c777  xor     bl, bl
0x14002c779  mov     [rsp+98h+var_58], bl
0x14002c77d  test    r14d, r14d
0x14002c780  jns     loc_14002C84D
0x14002c786  call    cs:__imp_KeEnterCriticalRegion
0x14002c78d  nop     dword ptr [rax+rax+00h]
0x14002c792  mov     bl, 1
0x14002c794  mov     [rsp+98h+var_58], bl
0x14002c798  mov     rcx, [rsp+98h+Irp]; Irp
0x14002c7a0  call    FatIsIrpTopLevel
0x14002c7a5  mov     r13b, al
0x14002c7a8  mov     [rsp+98h+var_56], al
0x14002c7ac  mov     ecx, [rsi+88h]
0x14002c7b2  test    cl, 5
0x14002c7b5  jz      short loc_14002C81E
0x14002c7b7  xor     r8d, r8d
0x14002c7ba  mov     rdx, r15
0x14002c7bd  mov     rcx, rsi
0x14002c7c0  call    FatAcquireExclusiveVcb_Real
0x14002c7c5  cmp     dword ptr [r15+0CCh], 1
0x14002c7cd  jz      short loc_14002C7E4
0x14002c7cf  lea     rcx, [r15+208h]; Resource
0x14002c7d6  call    cs:__imp_ExReleaseResourceLite
0x14002c7dd  nop     dword ptr [rax+rax+00h]
0x14002c7e2  jmp     short loc_14002C852
0x14002c7e4  mov     rdx, rdi
0x14002c7e7  mov     rcx, rsi
0x14002c7ea  call    FatAcquireExclusiveFcb
0x14002c7ef  or      dword ptr [rdi+0C0h], 1
0x14002c7f6  mov     [r12+49h], bl
0x14002c7fb  mov     rcx, [rdi+8]; Resource
0x14002c7ff  call    cs:__imp_ExReleaseResourceLite
0x14002c806  nop     dword ptr [rax+rax+00h]
0x14002c80b  lea     rcx, [r15+208h]; Resource
0x14002c812  call    cs:__imp_ExReleaseResourceLite
0x14002c819  nop     dword ptr [rax+rax+00h]
0x14002c81e  bts     dword ptr [rsi+44h], 12h
0x14002c823  mov     rcx, [r12+10h]
0x14002c828  mov     rdx, r12; FileObject
0x14002c82b  mov     rcx, [rcx+8]; DeviceObject
0x14002c82f  call    cs:__imp_IoCancelFileOpen
0x14002c836  nop     dword ptr [rax+rax+00h]
0x14002c83b  btr     dword ptr [rsi+44h], 12h
0x14002c840  xor     cl, cl
0x14002c842  mov     [rsp+98h+var_57], cl
0x14002c846  jmp     short loc_14002C856
0x14002c848  mov     rdi, [rsp+98h+var_50]
0x14002c84d  mov     r13b, [rsp+98h+var_56]
0x14002c852  mov     cl, [rsp+98h+var_57]
0x14002c856  mov     eax, [rsi+88h]
0x14002c85c  test    al, 5
0x14002c85e  jz      short loc_14002C8D0
0x14002c860  test    rdi, rdi
0x14002c863  jz      short loc_14002C8B8
0x14002c865  test    cl, cl
0x14002c867  jz      short loc_14002C8B8
0x14002c869  test    bl, bl
0x14002c86b  jnz     short loc_14002C87B
0x14002c86d  call    cs:__imp_KeEnterCriticalRegion
0x14002c874  nop     dword ptr [rax+rax+00h]
0x14002c879  mov     bl, 1
0x14002c87b  mov     rdx, rdi
0x14002c87e  mov     rcx, rsi
0x14002c881  call    FatAcquireExclusiveFcb
0x14002c886  btr     dword ptr [rdi+0C0h], 14h
0x14002c88e  xor     r8d, r8d; Wait
0x14002c891  xor     edx, edx; Increment
0x14002c893  lea     rcx, Event; Event
0x14002c89a  call    cs:__imp_KeSetEvent
0x14002c8a1  nop     dword ptr [rax+rax+00h]
0x14002c8a6  mov     rcx, [rdi+8]; Resource
0x14002c8aa  call    cs:__imp_ExReleaseResourceLite
0x14002c8b1  nop     dword ptr [rax+rax+00h]
0x14002c8b6  jmp     short loc_14002C8D0
0x14002c8b8  xor     r8d, r8d; Wait
0x14002c8bb  xor     edx, edx; Increment
0x14002c8bd  lea     rcx, Event; Event
0x14002c8c4  call    cs:__imp_KeSetEvent
0x14002c8cb  nop     dword ptr [rax+rax+00h]
0x14002c8d0  test    r13b, r13b
0x14002c8d3  jz      short loc_14002C8E3
0x14002c8d5  xor     ecx, ecx; Irp
0x14002c8d7  call    cs:__imp_IoSetTopLevelIrp
0x14002c8de  nop     dword ptr [rax+rax+00h]
0x14002c8e3  test    bl, bl
0x14002c8e5  jz      short loc_14002C8F3
0x14002c8e7  call    cs:__imp_KeLeaveCriticalRegion
0x14002c8ee  nop     dword ptr [rax+rax+00h]
0x14002c8f3  mov     eax, r14d
0x14002c8f6  add     rsp, 60h
0x14002c8fa  pop     r15
0x14002c8fc  pop     r14
0x14002c8fe  pop     r13
0x14002c900  pop     r12
0x14002c902  pop     rdi
0x14002c903  pop     rsi
0x14002c904  pop     rbx
0x14002c905  retn
0x14005cae7  push    rbx
0x14005cae9  push    rbp
0x14005caea  push    rdi
0x14005caeb  sub     rsp, 40h
0x14005caef  mov     rbp, rdx
0x14005caf2  mov     rdi, [rbp+0A0h]
0x14005caf9  mov     eax, [rdi+88h]
0x14005caff  test    al, 5
0x14005cb01  jz      loc_14005CB8A
0x14005cb07  mov     rbx, [rbp+48h]
0x14005cb0b  test    rbx, rbx
0x14005cb0e  jz      short loc_14005CB71
0x14005cb10  cmp     byte ptr [rbp+41h], 0
0x14005cb14  jz      short loc_14005CB71
0x14005cb16  cmp     byte ptr [rbp+40h], 0
0x14005cb1a  jnz     short loc_14005CB2C
0x14005cb1c  call    cs:__imp_KeEnterCriticalRegion
0x14005cb23  nop     dword ptr [rax+rax+00h]
0x14005cb28  mov     byte ptr [rbp+40h], 1
0x14005cb2c  mov     rdx, rbx
0x14005cb2f  mov     rcx, rdi
0x14005cb32  call    FatAcquireExclusiveFcb
0x14005cb37  mov     eax, [rbx+0C0h]
0x14005cb3d  btr     eax, 14h
0x14005cb41  mov     [rbx+0C0h], eax
0x14005cb47  xor     r8d, r8d; Wait
0x14005cb4a  xor     edx, edx; Increment
0x14005cb4c  lea     rcx, Event; Event
0x14005cb53  call    cs:__imp_KeSetEvent
0x14005cb5a  nop     dword ptr [rax+rax+00h]
0x14005cb5f  mov     rcx, [rbx+8]; Resource
0x14005cb63  call    cs:__imp_ExReleaseResourceLite
0x14005cb6a  nop     dword ptr [rax+rax+00h]
0x14005cb6f  jmp     short loc_14005CB8A
0x14005cb71  xor     r8d, r8d; Wait
0x14005cb74  xor     edx, edx; Increment
0x14005cb76  lea     rcx, Event; Event
0x14005cb7d  call    cs:__imp_KeSetEvent
0x14005cb84  nop     dword ptr [rax+rax+00h]
0x14005cb89  nop
0x14005cb8a  cmp     byte ptr [rbp+42h], 0
0x14005cb8e  jz      short loc_14005CB9F
0x14005cb90  xor     ecx, ecx; Irp
0x14005cb92  call    cs:__imp_IoSetTopLevelIrp
0x14005cb99  nop     dword ptr [rax+rax+00h]
0x14005cb9e  nop
0x14005cb9f  cmp     byte ptr [rbp+40h], 0
0x14005cba3  jz      short loc_14005CBB2
0x14005cba5  call    cs:__imp_KeLeaveCriticalRegion
0x14005cbac  nop     dword ptr [rax+rax+00h]
0x14005cbb1  nop
0x14005cbb2  add     rsp, 40h
0x14005cbb6  pop     rdi
0x14005cbb7  pop     rbp
0x14005cbb8  pop     rbx
0x14005cbb9  retn
```
