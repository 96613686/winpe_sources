# MupCreate

- ea: `0x14001a370`
- end: `0x14001a75a`
- name: `MupCreate`
- size: `1002`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001070`
- `0x140001880`
- `0x1400025ac`
- `0x140002700`
- `0x1400029b0`
- `0x140002c28`
- `0x140002dcc`
- `0x140019548`
- `0x14001a0d8`
- `0x14001a370`
- `0x14001a8d0`
- `0x14001ba90`
- `0x14001bb30`
- `0x14001bb60`
- `0x14001cb80`

## import_xrefs

- `ntoskrnl!FsRtlInsertPerFileObjectContext` at `0x14001a549`
- `ntoskrnl!FsRtlInsertPerFileObjectContext` at `0x14001a549`
- `ntoskrnl!IofCompleteRequest` at `0x14001a6df`
- `ntoskrnl!IofCompleteRequest` at `0x14001a6df`

## pseudocode

```c
__int64 __fastcall MupCreate(__int64 a1, IRP *a2, int a3)
{
  unsigned int ContainerContextFromSilo; // edi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  PFILE_OBJECT FileObject; // r10
  ULONG_PTR v7; // rbx
  PVOID v8; // r15
  char v9; // r12
  PFILE_OBJECT v10; // r14
  __int64 SiloFromFileObject; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  PFILE_OBJECT v14; // r10
  unsigned int v15; // eax
  __int64 v16; // rax
  int v17; // ecx
  __int64 v18; // rax
  __int64 v19; // rax
  struct _FILE_OBJECT *RelatedFileObject; // rcx
  __int64 v22; // [rsp+28h] [rbp-50h]
  __int64 v23; // [rsp+30h] [rbp-48h]
  PFILE_OBJECT v24; // [rsp+38h] [rbp-40h]
  ULONG_PTR BugCheckParameter4; // [rsp+88h] [rbp+10h] BYREF
  __int64 v26; // [rsp+90h] [rbp+18h] BYREF
  PVOID P; // [rsp+98h] [rbp+20h] BYREF

  ContainerContextFromSilo = 0;
  v26 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  v24 = FileObject;
  v7 = 0;
  BugCheckParameter4 = 0;
  v8 = 0;
  P = 0;
  v9 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
  {
    WPP_SF_Zqq(WPP_GLOBAL_Control->AttachedDevice, 10, a3, (_DWORD)FileObject + 88, (char)FileObject, a2, 0);
  }
  v10 = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( v10->FileName.Length
    || (RelatedFileObject = v10->RelatedFileObject) != 0 && RelatedFileObject->FsContext != &g_MupAdvancedFcbHeader )
  {
    ContainerContextFromSilo = -1073741802;
  }
  else
  {
    v10->FsContext = &g_MupAdvancedFcbHeader;
    LOBYTE(RelatedFileObject) = 1;
    MupiUpdateMupDeviceOpenCount(RelatedFileObject);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_qqD(
      WPP_GLOBAL_Control->AttachedDevice,
      28,
      WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids,
      v10,
      a2,
      ContainerContextFromSilo);
  }
  LODWORD(v23) = ContainerContextFromSilo;
  if ( ContainerContextFromSilo != -1073741802 )
  {
    v9 = 1;
    goto LABEL_42;
  }
  SiloFromFileObject = MupGetSiloFromFileObject(a2->Tail.Overlay.CurrentStackLocation->FileObject);
  ContainerContextFromSilo = MupGetContainerContextFromSilo(SiloFromFileObject, &v26);
  LODWORD(v23) = ContainerContextFromSilo;
  if ( ContainerContextFromSilo )
    goto LABEL_42;
  v14 = v24;
  if ( v24->RelatedFileObject )
  {
    LOBYTE(v12) = v26 != 0;
    v15 = MupiCreateWithRelativePath(v24, v12, &BugCheckParameter4);
    goto LABEL_16;
  }
  ContainerContextFromSilo = -1073741802;
  LODWORD(v23) = -1073741802;
  if ( !CurrentStackLocation->MajorFunction )
  {
    LOBYTE(v13) = v26 != 0;
    ContainerContextFromSilo = MupiCheckForMailslotRequest(v24, &BugCheckParameter4, v13);
    LODWORD(v23) = ContainerContextFromSilo;
    v7 = BugCheckParameter4;
    v14 = v24;
  }
  if ( ContainerContextFromSilo == -1073741802 )
  {
    LOBYTE(v12) = v26 != 0;
    v15 = MupiCreateWithAbsolutePath(v14, v12, &BugCheckParameter4);
LABEL_16:
    LODWORD(v23) = v15;
    v7 = BugCheckParameter4;
    ContainerContextFromSilo = v15;
    goto LABEL_17;
  }
  if ( ContainerContextFromSilo )
    goto LABEL_42;
LABEL_17:
  if ( ContainerContextFromSilo )
    goto LABEL_42;
  v16 = *(_QWORD *)(v7 + 248);
  if ( !v16 )
    goto LABEL_20;
  v17 = *(_DWORD *)(v16 + 88);
  if ( !v17 )
    goto LABEL_20;
  v18 = *(_QWORD *)(v7 + 168);
  if ( v18 && (~*(_DWORD *)(v18 + 152) & v17) != 0 )
  {
    ContainerContextFromSilo = -1073741311;
  }
  else
  {
    v19 = *(_QWORD *)(v7 + 184);
    if ( !v19 || (~*(_DWORD *)(v19 + 108) & v17) == 0 )
    {
LABEL_20:
      ContainerContextFromSilo = 0;
      goto LABEL_21;
    }
    ContainerContextFromSilo = -1073741311;
  }
LABEL_21:
  LODWORD(v23) = ContainerContextFromSilo;
  if ( !ContainerContextFromSilo )
  {
    ContainerContextFromSilo = MupCreateIrpContext(v7, (__int64)&P);
    LODWORD(v23) = ContainerContextFromSilo;
    if ( ContainerContextFromSilo )
    {
      v8 = P;
    }
    else
    {
      *(_QWORD *)(v7 + 24) = MupDeviceObject;
      *(_QWORD *)(v7 + 32) = 0;
      ContainerContextFromSilo = FsRtlInsertPerFileObjectContext(
                                   *(PFILE_OBJECT *)(v7 + 144),
                                   (PFSRTL_PER_FILEOBJECT_CONTEXT)(v7 + 8));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
      {
        WPP_SF_qq(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids,
          *(_QWORD *)(v7 + 144),
          v7);
      }
      LODWORD(v23) = ContainerContextFromSilo;
      v8 = P;
    }
  }
LABEL_42:
  if ( ContainerContextFromSilo )
  {
    if ( v7 )
      MupReleaseFileContext((PVOID)v7);
    if ( v8 )
      MupReleaseIrpContext(v8);
  }
  if ( v9 || ContainerContextFromSilo )
  {
    a2->IoStatus.Status = ContainerContextFromSilo;
    IofCompleteRequest(a2, 2);
  }
  else
  {
    ContainerContextFromSilo = MupStateMachine(v8);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
  {
    LODWORD(v22) = ContainerContextFromSilo;
    WPP_SF_ZqD(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      (unsigned int)WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids,
      (_DWORD)v24 + 88,
      (char)v24,
      v22,
      v23);
  }
  return ContainerContextFromSilo;
}

```

## disassembly

```asm
0x14001a370  mov     rax, rsp
0x14001a373  push    rbx
0x14001a374  push    rsi
0x14001a375  push    rdi
0x14001a376  push    r12
0x14001a378  push    r13
0x14001a37a  push    r14
0x14001a37c  push    r15
0x14001a37e  sub     rsp, 40h
0x14001a382  mov     rsi, rdx
0x14001a385  xor     edi, edi
0x14001a387  mov     [rax+18h], rdi
0x14001a38b  mov     r13, [rdx+0B8h]
0x14001a392  mov     r10, [r13+30h]
0x14001a396  mov     [rsp+78h+var_40], r10
0x14001a39b  mov     [rax-48h], edi
0x14001a39e  mov     ebx, edi
0x14001a3a0  mov     [rax+10h], rbx
0x14001a3a4  mov     r15d, edi
0x14001a3a7  mov     [rax+20h], rdi
0x14001a3ab  xor     r12b, r12b
0x14001a3ae  lea     rax, WPP_GLOBAL_Control
0x14001a3b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a3bc  cmp     rcx, rax
0x14001a3bf  jz      short loc_14001A3CE
0x14001a3c1  test    dword ptr [rcx+2Ch], 2000000h
0x14001a3c8  jnz     loc_14001A60D
0x14001a3ce  mov     rax, [rsi+0B8h]
0x14001a3d5  mov     r14, [rax+30h]
0x14001a3d9  cmp     word ptr [r14+58h], 0
0x14001a3df  jz      loc_14001A62E
0x14001a3e5  mov     edi, 0C0000016h
0x14001a3ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a3f1  lea     rax, WPP_GLOBAL_Control
0x14001a3f8  cmp     rcx, rax
0x14001a3fb  jz      short loc_14001A40A
0x14001a3fd  mov     eax, [rcx+2Ch]
0x14001a400  bt      eax, 1Ah
0x14001a404  jb      loc_14001A658
0x14001a40a  mov     dword ptr [rsp+78h+var_48], edi
0x14001a40e  cmp     edi, 0C0000016h
0x14001a414  jnz     loc_14001A5A9
0x14001a41a  mov     rcx, [rsi+0B8h]
0x14001a421  mov     rcx, [rcx+30h]
0x14001a425  call    MupGetSiloFromFileObject
0x14001a42a  mov     rcx, rax
0x14001a42d  lea     rdx, [rsp+78h+arg_10]
0x14001a435  call    MupGetContainerContextFromSilo
0x14001a43a  mov     edi, eax
0x14001a43c  mov     dword ptr [rsp+78h+var_48], eax
0x14001a440  test    eax, eax
0x14001a442  jnz     loc_14001A5AC
0x14001a448  mov     r10, [rsp+78h+var_40]
0x14001a44d  cmp     qword ptr [r10+40h], 0
0x14001a452  jnz     loc_14001A588
0x14001a458  mov     edi, 0C0000016h
0x14001a45d  mov     dword ptr [rsp+78h+var_48], edi
0x14001a461  cmp     [r13+0], al
0x14001a465  jnz     short loc_14001A497
0x14001a467  cmp     [rsp+78h+arg_10], 0
0x14001a470  setnz   r8b
0x14001a474  lea     rdx, [rsp+78h+BugCheckParameter4]
0x14001a47c  mov     rcx, r10
0x14001a47f  call    MupiCheckForMailslotRequest
0x14001a484  mov     edi, eax
0x14001a486  mov     dword ptr [rsp+78h+var_48], eax
0x14001a48a  mov     rbx, [rsp+78h+BugCheckParameter4]
0x14001a492  mov     r10, [rsp+78h+var_40]
0x14001a497  cmp     edi, 0C0000016h
0x14001a49d  jnz     loc_14001A5B8
0x14001a4a3  cmp     [rsp+78h+arg_10], 0
0x14001a4ac  setnz   dl
0x14001a4af  lea     r8, [rsp+78h+BugCheckParameter4]
0x14001a4b7  mov     rcx, r10
0x14001a4ba  call    MupiCreateWithAbsolutePath
0x14001a4bf  mov     dword ptr [rsp+78h+var_48], eax
0x14001a4c3  mov     rbx, [rsp+78h+BugCheckParameter4]
0x14001a4cb  mov     edi, eax
0x14001a4cd  test    edi, edi
0x14001a4cf  jnz     loc_14001A5AC
0x14001a4d5  mov     rax, [rbx+0F8h]
0x14001a4dc  test    rax, rax
0x14001a4df  jz      short loc_14001A4EC
0x14001a4e1  mov     ecx, [rax+58h]
0x14001a4e4  test    ecx, ecx
0x14001a4e6  jnz     loc_14001A5CC
0x14001a4ec  xor     edi, edi
0x14001a4ee  mov     dword ptr [rsp+78h+var_48], edi
0x14001a4f2  test    edi, edi
0x14001a4f4  jnz     loc_14001A5AC
0x14001a4fa  lea     rax, [rsp+78h+P]
0x14001a502  mov     [rsp+78h+var_58], rax; __int64
0x14001a507  xor     r9d, r9d
0x14001a50a  mov     r8, rsi
0x14001a50d  mov     rdx, [rsp+78h+arg_10]
0x14001a515  mov     rcx, rbx; BugCheckParameter4
0x14001a518  call    MupCreateIrpContext
0x14001a51d  mov     edi, eax
0x14001a51f  mov     dword ptr [rsp+78h+var_48], eax
0x14001a523  test    eax, eax
0x14001a525  jnz     loc_14001A603
0x14001a52b  mov     rax, cs:MupDeviceObject
0x14001a532  mov     [rbx+18h], rax
0x14001a536  mov     qword ptr [rbx+20h], 0
0x14001a53e  lea     rdx, [rbx+8]; Ptr
0x14001a542  mov     rcx, [rbx+90h]; FileObject
0x14001a549  call    cs:__imp_FsRtlInsertPerFileObjectContext
0x14001a550  nop     dword ptr [rax+rax+00h]
0x14001a555  mov     edi, eax
0x14001a557  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a55e  lea     r14, WPP_GLOBAL_Control
0x14001a565  cmp     rcx, r14
0x14001a568  jz      short loc_14001A577
0x14001a56a  mov     eax, [rcx+2Ch]
0x14001a56d  bt      eax, 1Ah
0x14001a571  jb      loc_14001A698
0x14001a577  mov     dword ptr [rsp+78h+var_48], edi
0x14001a57b  mov     r15, [rsp+78h+P]
0x14001a583  jmp     loc_14001A6BE
0x14001a588  cmp     [rsp+78h+arg_10], 0
0x14001a591  setnz   dl
0x14001a594  lea     r8, [rsp+78h+BugCheckParameter4]
0x14001a59c  mov     rcx, r10
0x14001a59f  call    MupiCreateWithRelativePath
0x14001a5a4  jmp     loc_14001A4BF
0x14001a5a9  mov     r12b, 1
0x14001a5ac  lea     r14, WPP_GLOBAL_Control
0x14001a5b3  jmp     loc_14001A6BE
0x14001a5b8  test    edi, edi
0x14001a5ba  jz      loc_14001A4CD
0x14001a5c0  lea     r14, WPP_GLOBAL_Control
0x14001a5c7  jmp     loc_14001A6BE
0x14001a5cc  mov     rax, [rbx+0A8h]
0x14001a5d3  test    rax, rax
0x14001a5d6  jnz     loc_14001A67E
0x14001a5dc  mov     rax, [rbx+0B8h]
0x14001a5e3  test    rax, rax
0x14001a5e6  jz      loc_14001A4EC
0x14001a5ec  mov     eax, [rax+6Ch]
0x14001a5ef  not     eax
0x14001a5f1  test    ecx, eax
0x14001a5f3  jz      loc_14001A4EC
0x14001a5f9  mov     edi, 0C0000201h
0x14001a5fe  jmp     loc_14001A4EE
0x14001a603  mov     r15, [rsp+78h+P]
0x14001a60b  jmp     short loc_14001A5AC
0x14001a60d  lea     r9, [r10+58h]
0x14001a611  mov     edx, 0Ah
0x14001a616  mov     [rsp+78h+var_50], rsi
0x14001a61b  mov     [rsp+78h+var_58], r10
0x14001a620  mov     rcx, [rcx+18h]
0x14001a624  call    WPP_SF_Zqq
0x14001a629  jmp     loc_14001A3CE
0x14001a62e  mov     rcx, [r14+40h]
0x14001a632  lea     rax, g_MupAdvancedFcbHeader
0x14001a639  test    rcx, rcx
0x14001a63c  jz      short loc_14001A648
0x14001a63e  cmp     [rcx+18h], rax
0x14001a642  jnz     loc_14001A3E5
0x14001a648  mov     [r14+18h], rax
0x14001a64c  mov     cl, 1
0x14001a64e  call    MupiUpdateMupDeviceOpenCount
0x14001a653  jmp     loc_14001A3EA
0x14001a658  mov     edx, 1Ch
0x14001a65d  mov     dword ptr [rsp+78h+var_50], edi
0x14001a661  mov     [rsp+78h+var_58], rsi
0x14001a666  mov     r9, r14
0x14001a669  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001a670  mov     rcx, [rcx+18h]
0x14001a674  call    WPP_SF_qqD
0x14001a679  jmp     loc_14001A40A
0x14001a67e  mov     eax, [rax+98h]
0x14001a684  not     eax
0x14001a686  test    ecx, eax
0x14001a688  jz      loc_14001A5DC
0x14001a68e  mov     edi, 0C0000201h
0x14001a693  jmp     loc_14001A4EE
0x14001a698  mov     edx, 0Ch
0x14001a69d  mov     [rsp+78h+var_58], rbx
0x14001a6a2  mov     r9, [rbx+90h]
0x14001a6a9  lea     r8, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids
0x14001a6b0  mov     rcx, [rcx+18h]
0x14001a6b4  call    WPP_SF_qq
0x14001a6b9  jmp     loc_14001A577
0x14001a6be  test    edi, edi
0x14001a6c0  jnz     short loc_14001A713
0x14001a6c2  test    r12b, r12b
0x14001a6c5  jnz     short loc_14001A6D7
0x14001a6c7  test    edi, edi
0x14001a6c9  jnz     short loc_14001A6D7
0x14001a6cb  mov     rcx, r15; P
0x14001a6ce  call    MupStateMachine
0x14001a6d3  mov     edi, eax
0x14001a6d5  jmp     short loc_14001A6EB
0x14001a6d7  mov     [rsi+30h], edi
0x14001a6da  mov     dl, 2; PriorityBoost
0x14001a6dc  mov     rcx, rsi; Irp
0x14001a6df  call    cs:__imp_IofCompleteRequest
0x14001a6e6  nop     dword ptr [rax+rax+00h]
0x14001a6eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a6f2  cmp     rcx, r14
0x14001a6f5  jz      short loc_14001A700
0x14001a6f7  test    dword ptr [rcx+2Ch], 2000000h
0x14001a6fe  jnz     short loc_14001A731
0x14001a700  mov     eax, edi
0x14001a702  add     rsp, 40h
0x14001a706  pop     r15
0x14001a708  pop     r14
0x14001a70a  pop     r13
0x14001a70c  pop     r12
0x14001a70e  pop     rdi
0x14001a70f  pop     rsi
0x14001a710  pop     rbx
0x14001a711  retn
0x14001a713  test    rbx, rbx
0x14001a716  jnz     short loc_14001A727
0x14001a718  test    r15, r15
0x14001a71b  jz      short loc_14001A6C2
0x14001a71d  mov     rcx, r15; P
0x14001a720  call    MupReleaseIrpContext
0x14001a725  jmp     short loc_14001A6C2
0x14001a727  mov     rcx, rbx; P
0x14001a72a  call    MupReleaseFileContext
0x14001a72f  jmp     short loc_14001A718
0x14001a731  mov     rax, [rsp+78h+var_40]
0x14001a736  lea     r9, [rax+58h]
0x14001a73a  mov     edx, 0Bh
0x14001a73f  mov     dword ptr [rsp+78h+var_50], edi
0x14001a743  mov     [rsp+78h+var_58], rax
0x14001a748  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001a74f  mov     rcx, [rcx+18h]
0x14001a753  call    WPP_SF_ZqD
0x14001a758  jmp     short loc_14001A700
0x14001f4e0  push    rbp
0x14001f4e2  sub     rsp, 30h
0x14001f4e6  mov     rbp, rdx
0x14001f4e9  cmp     dword ptr [rbp+30h], 0
0x14001f4ed  jnz     short loc_14001F4F6
0x14001f4ef  movzx   eax, cl
0x14001f4f2  test    cl, cl
0x14001f4f4  jz      short loc_14001F51A
0x14001f4f6  mov     rcx, [rbp+88h]; P
0x14001f4fd  test    rcx, rcx
0x14001f500  jz      short loc_14001F508
0x14001f502  call    MupReleaseFileContext
0x14001f507  nop
0x14001f508  mov     rcx, [rbp+98h]; P
0x14001f50f  test    rcx, rcx
0x14001f512  jz      short loc_14001F51A
0x14001f514  call    MupReleaseIrpContext
0x14001f519  nop
0x14001f51a  add     rsp, 30h
0x14001f51e  pop     rbp
0x14001f51f  retn
```
