# MupCreate

- ea: `0x14001a3c0`
- end: `0x14001a7aa`
- name: `MupCreate`
- size: `1002`
- prototype: `__int64 __fastcall(__int64, IRP *, int)`
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
- `0x140019598`
- `0x14001a128`
- `0x14001a3c0`
- `0x14001a920`
- `0x14001bae0`
- `0x14001bb80`
- `0x14001bbb0`
- `0x14001cbd0`

## import_xrefs

- `ntoskrnl!FsRtlInsertPerFileObjectContext` at `0x14001a599`
- `ntoskrnl!FsRtlInsertPerFileObjectContext` at `0x14001a599`
- `ntoskrnl!IofCompleteRequest` at `0x14001a72f`
- `ntoskrnl!IofCompleteRequest` at `0x14001a72f`

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
0x14001a3c0  mov     rax, rsp
0x14001a3c3  push    rbx
0x14001a3c4  push    rsi
0x14001a3c5  push    rdi
0x14001a3c6  push    r12
0x14001a3c8  push    r13
0x14001a3ca  push    r14
0x14001a3cc  push    r15
0x14001a3ce  sub     rsp, 40h
0x14001a3d2  mov     rsi, rdx
0x14001a3d5  xor     edi, edi
0x14001a3d7  mov     [rax+18h], rdi
0x14001a3db  mov     r13, [rdx+0B8h]
0x14001a3e2  mov     r10, [r13+30h]
0x14001a3e6  mov     [rsp+78h+var_40], r10
0x14001a3eb  mov     [rax-48h], edi
0x14001a3ee  mov     ebx, edi
0x14001a3f0  mov     [rax+10h], rbx
0x14001a3f4  mov     r15d, edi
0x14001a3f7  mov     [rax+20h], rdi
0x14001a3fb  xor     r12b, r12b
0x14001a3fe  lea     rax, WPP_GLOBAL_Control
0x14001a405  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a40c  cmp     rcx, rax
0x14001a40f  jz      short loc_14001A41E
0x14001a411  test    dword ptr [rcx+2Ch], 2000000h
0x14001a418  jnz     loc_14001A65D
0x14001a41e  mov     rax, [rsi+0B8h]
0x14001a425  mov     r14, [rax+30h]
0x14001a429  cmp     word ptr [r14+58h], 0
0x14001a42f  jz      loc_14001A67E
0x14001a435  mov     edi, 0C0000016h
0x14001a43a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a441  lea     rax, WPP_GLOBAL_Control
0x14001a448  cmp     rcx, rax
0x14001a44b  jz      short loc_14001A45A
0x14001a44d  mov     eax, [rcx+2Ch]
0x14001a450  bt      eax, 1Ah
0x14001a454  jb      loc_14001A6A8
0x14001a45a  mov     dword ptr [rsp+78h+var_48], edi
0x14001a45e  cmp     edi, 0C0000016h
0x14001a464  jnz     loc_14001A5F9
0x14001a46a  mov     rcx, [rsi+0B8h]
0x14001a471  mov     rcx, [rcx+30h]
0x14001a475  call    MupGetSiloFromFileObject
0x14001a47a  mov     rcx, rax
0x14001a47d  lea     rdx, [rsp+78h+arg_10]
0x14001a485  call    MupGetContainerContextFromSilo
0x14001a48a  mov     edi, eax
0x14001a48c  mov     dword ptr [rsp+78h+var_48], eax
0x14001a490  test    eax, eax
0x14001a492  jnz     loc_14001A5FC
0x14001a498  mov     r10, [rsp+78h+var_40]
0x14001a49d  cmp     qword ptr [r10+40h], 0
0x14001a4a2  jnz     loc_14001A5D8
0x14001a4a8  mov     edi, 0C0000016h
0x14001a4ad  mov     dword ptr [rsp+78h+var_48], edi
0x14001a4b1  cmp     [r13+0], al
0x14001a4b5  jnz     short loc_14001A4E7
0x14001a4b7  cmp     [rsp+78h+arg_10], 0
0x14001a4c0  setnz   r8b
0x14001a4c4  lea     rdx, [rsp+78h+BugCheckParameter4]
0x14001a4cc  mov     rcx, r10
0x14001a4cf  call    MupiCheckForMailslotRequest
0x14001a4d4  mov     edi, eax
0x14001a4d6  mov     dword ptr [rsp+78h+var_48], eax
0x14001a4da  mov     rbx, [rsp+78h+BugCheckParameter4]
0x14001a4e2  mov     r10, [rsp+78h+var_40]
0x14001a4e7  cmp     edi, 0C0000016h
0x14001a4ed  jnz     loc_14001A608
0x14001a4f3  cmp     [rsp+78h+arg_10], 0
0x14001a4fc  setnz   dl
0x14001a4ff  lea     r8, [rsp+78h+BugCheckParameter4]
0x14001a507  mov     rcx, r10
0x14001a50a  call    MupiCreateWithAbsolutePath
0x14001a50f  mov     dword ptr [rsp+78h+var_48], eax
0x14001a513  mov     rbx, [rsp+78h+BugCheckParameter4]
0x14001a51b  mov     edi, eax
0x14001a51d  test    edi, edi
0x14001a51f  jnz     loc_14001A5FC
0x14001a525  mov     rax, [rbx+0F8h]
0x14001a52c  test    rax, rax
0x14001a52f  jz      short loc_14001A53C
0x14001a531  mov     ecx, [rax+58h]
0x14001a534  test    ecx, ecx
0x14001a536  jnz     loc_14001A61C
0x14001a53c  xor     edi, edi
0x14001a53e  mov     dword ptr [rsp+78h+var_48], edi
0x14001a542  test    edi, edi
0x14001a544  jnz     loc_14001A5FC
0x14001a54a  lea     rax, [rsp+78h+P]
0x14001a552  mov     [rsp+78h+var_58], rax; __int64
0x14001a557  xor     r9d, r9d
0x14001a55a  mov     r8, rsi
0x14001a55d  mov     rdx, [rsp+78h+arg_10]
0x14001a565  mov     rcx, rbx; BugCheckParameter4
0x14001a568  call    MupCreateIrpContext
0x14001a56d  mov     edi, eax
0x14001a56f  mov     dword ptr [rsp+78h+var_48], eax
0x14001a573  test    eax, eax
0x14001a575  jnz     loc_14001A653
0x14001a57b  mov     rax, cs:MupDeviceObject
0x14001a582  mov     [rbx+18h], rax
0x14001a586  mov     qword ptr [rbx+20h], 0
0x14001a58e  lea     rdx, [rbx+8]; Ptr
0x14001a592  mov     rcx, [rbx+90h]; FileObject
0x14001a599  call    cs:__imp_FsRtlInsertPerFileObjectContext
0x14001a5a0  nop     dword ptr [rax+rax+00h]
0x14001a5a5  mov     edi, eax
0x14001a5a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a5ae  lea     r14, WPP_GLOBAL_Control
0x14001a5b5  cmp     rcx, r14
0x14001a5b8  jz      short loc_14001A5C7
0x14001a5ba  mov     eax, [rcx+2Ch]
0x14001a5bd  bt      eax, 1Ah
0x14001a5c1  jb      loc_14001A6E8
0x14001a5c7  mov     dword ptr [rsp+78h+var_48], edi
0x14001a5cb  mov     r15, [rsp+78h+P]
0x14001a5d3  jmp     loc_14001A70E
0x14001a5d8  cmp     [rsp+78h+arg_10], 0
0x14001a5e1  setnz   dl
0x14001a5e4  lea     r8, [rsp+78h+BugCheckParameter4]
0x14001a5ec  mov     rcx, r10
0x14001a5ef  call    MupiCreateWithRelativePath
0x14001a5f4  jmp     loc_14001A50F
0x14001a5f9  mov     r12b, 1
0x14001a5fc  lea     r14, WPP_GLOBAL_Control
0x14001a603  jmp     loc_14001A70E
0x14001a608  test    edi, edi
0x14001a60a  jz      loc_14001A51D
0x14001a610  lea     r14, WPP_GLOBAL_Control
0x14001a617  jmp     loc_14001A70E
0x14001a61c  mov     rax, [rbx+0A8h]
0x14001a623  test    rax, rax
0x14001a626  jnz     loc_14001A6CE
0x14001a62c  mov     rax, [rbx+0B8h]
0x14001a633  test    rax, rax
0x14001a636  jz      loc_14001A53C
0x14001a63c  mov     eax, [rax+6Ch]
0x14001a63f  not     eax
0x14001a641  test    ecx, eax
0x14001a643  jz      loc_14001A53C
0x14001a649  mov     edi, 0C0000201h
0x14001a64e  jmp     loc_14001A53E
0x14001a653  mov     r15, [rsp+78h+P]
0x14001a65b  jmp     short loc_14001A5FC
0x14001a65d  lea     r9, [r10+58h]
0x14001a661  mov     edx, 0Ah
0x14001a666  mov     [rsp+78h+var_50], rsi
0x14001a66b  mov     [rsp+78h+var_58], r10
0x14001a670  mov     rcx, [rcx+18h]
0x14001a674  call    WPP_SF_Zqq
0x14001a679  jmp     loc_14001A41E
0x14001a67e  mov     rcx, [r14+40h]
0x14001a682  lea     rax, g_MupAdvancedFcbHeader
0x14001a689  test    rcx, rcx
0x14001a68c  jz      short loc_14001A698
0x14001a68e  cmp     [rcx+18h], rax
0x14001a692  jnz     loc_14001A435
0x14001a698  mov     [r14+18h], rax
0x14001a69c  mov     cl, 1
0x14001a69e  call    MupiUpdateMupDeviceOpenCount
0x14001a6a3  jmp     loc_14001A43A
0x14001a6a8  mov     edx, 1Ch
0x14001a6ad  mov     dword ptr [rsp+78h+var_50], edi
0x14001a6b1  mov     [rsp+78h+var_58], rsi
0x14001a6b6  mov     r9, r14
0x14001a6b9  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001a6c0  mov     rcx, [rcx+18h]
0x14001a6c4  call    WPP_SF_qqD
0x14001a6c9  jmp     loc_14001A45A
0x14001a6ce  mov     eax, [rax+98h]
0x14001a6d4  not     eax
0x14001a6d6  test    ecx, eax
0x14001a6d8  jz      loc_14001A62C
0x14001a6de  mov     edi, 0C0000201h
0x14001a6e3  jmp     loc_14001A53E
0x14001a6e8  mov     edx, 0Ch
0x14001a6ed  mov     [rsp+78h+var_58], rbx
0x14001a6f2  mov     r9, [rbx+90h]
0x14001a6f9  lea     r8, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids
0x14001a700  mov     rcx, [rcx+18h]
0x14001a704  call    WPP_SF_qq
0x14001a709  jmp     loc_14001A5C7
0x14001a70e  test    edi, edi
0x14001a710  jnz     short loc_14001A763
0x14001a712  test    r12b, r12b
0x14001a715  jnz     short loc_14001A727
0x14001a717  test    edi, edi
0x14001a719  jnz     short loc_14001A727
0x14001a71b  mov     rcx, r15; P
0x14001a71e  call    MupStateMachine
0x14001a723  mov     edi, eax
0x14001a725  jmp     short loc_14001A73B
0x14001a727  mov     [rsi+30h], edi
0x14001a72a  mov     dl, 2; PriorityBoost
0x14001a72c  mov     rcx, rsi; Irp
0x14001a72f  call    cs:__imp_IofCompleteRequest
0x14001a736  nop     dword ptr [rax+rax+00h]
0x14001a73b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a742  cmp     rcx, r14
0x14001a745  jz      short loc_14001A750
0x14001a747  test    dword ptr [rcx+2Ch], 2000000h
0x14001a74e  jnz     short loc_14001A781
0x14001a750  mov     eax, edi
0x14001a752  add     rsp, 40h
0x14001a756  pop     r15
0x14001a758  pop     r14
0x14001a75a  pop     r13
0x14001a75c  pop     r12
0x14001a75e  pop     rdi
0x14001a75f  pop     rsi
0x14001a760  pop     rbx
0x14001a761  retn
0x14001a763  test    rbx, rbx
0x14001a766  jnz     short loc_14001A777
0x14001a768  test    r15, r15
0x14001a76b  jz      short loc_14001A712
0x14001a76d  mov     rcx, r15; P
0x14001a770  call    MupReleaseIrpContext
0x14001a775  jmp     short loc_14001A712
0x14001a777  mov     rcx, rbx; P
0x14001a77a  call    MupReleaseFileContext
0x14001a77f  jmp     short loc_14001A768
0x14001a781  mov     rax, [rsp+78h+var_40]
0x14001a786  lea     r9, [rax+58h]
0x14001a78a  mov     edx, 0Bh
0x14001a78f  mov     dword ptr [rsp+78h+var_50], edi
0x14001a793  mov     [rsp+78h+var_58], rax
0x14001a798  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001a79f  mov     rcx, [rcx+18h]
0x14001a7a3  call    WPP_SF_ZqD
0x14001a7a8  jmp     short loc_14001A750
0x14001f530  push    rbp
0x14001f532  sub     rsp, 30h
0x14001f536  mov     rbp, rdx
0x14001f539  cmp     dword ptr [rbp+30h], 0
0x14001f53d  jnz     short loc_14001F546
0x14001f53f  movzx   eax, cl
0x14001f542  test    cl, cl
0x14001f544  jz      short loc_14001F56A
0x14001f546  mov     rcx, [rbp+88h]; P
0x14001f54d  test    rcx, rcx
0x14001f550  jz      short loc_14001F558
0x14001f552  call    MupReleaseFileContext
0x14001f557  nop
0x14001f558  mov     rcx, [rbp+98h]; P
0x14001f55f  test    rcx, rcx
0x14001f562  jz      short loc_14001F56A
0x14001f564  call    MupReleaseIrpContext
0x14001f569  nop
0x14001f56a  add     rsp, 30h
0x14001f56e  pop     rbp
0x14001f56f  retn
```
