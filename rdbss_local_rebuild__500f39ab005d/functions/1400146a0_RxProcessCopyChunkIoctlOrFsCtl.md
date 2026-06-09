# RxProcessCopyChunkIoctlOrFsCtl

- ea: `0x1400146a0`
- end: `0x140014ac6`
- name: `RxProcessCopyChunkIoctlOrFsCtl`
- size: `1062`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP Irp)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140045410`
- `0x140065fa0`

## callees

- `0x140009b80`
- `0x140013d10`
- `0x1400146a0`
- `0x14001e040`
- `0x14001e0d0`
- `0x140025d80`
- `0x140057660`
- `0x140067ad0`
- `0x140069970`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140014809`
- `ntoskrnl!ExAllocatePool2` at `0x140014809`
- `ntoskrnl!CcSetFileSizes` at `0x1400149e5`
- `ntoskrnl!CcSetFileSizes` at `0x1400149e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014a96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014a96`

## pseudocode

```c
__int64 __fastcall RxProcessCopyChunkIoctlOrFsCtl(PRX_CONTEXT RxContext, PIRP Irp, __int64 a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r9
  struct _FILE_OBJECT *FileObject; // rdi
  unsigned int *v7; // rbx
  char v8; // r15
  __int64 FsContext; // rsi
  __int16 v10; // ax
  int v11; // r14d
  NTSTATUS v12; // eax
  struct _IRP *v13; // rax
  __int64 p_ThreadListEntry; // r11
  __int64 i; // r10
  __int64 v16; // rcx
  int RdbssDbgExtension; // eax
  unsigned int *Pool2; // rax
  NTSTATUS v19; // eax
  signed __int64 v20; // r13
  const CHAR *v21; // r9
  signed __int64 v22; // rax
  signed __int64 *v23; // r15
  signed __int64 v24; // r8
  signed __int64 v25; // rax
  __int64 v26; // rcx
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // rax
  _QWORD *SharedCacheMap; // rdx
  struct _IRP *FileName; // [rsp+20h] [rbp-88h]
  ULONG FileNamea; // [rsp+20h] [rbp-88h]
  ULONG SerialNumber[2]; // [rsp+28h] [rbp-80h] BYREF
  LIST_ENTRY *v33; // [rsp+30h] [rbp-78h]
  unsigned int *v34; // [rsp+38h] [rbp-70h]
  __int64 v35; // [rsp+40h] [rbp-68h]
  __int64 v36; // [rsp+48h] [rbp-60h]
  ULONG LineNumber[2]; // [rsp+50h] [rbp-58h]
  PSECTION_OBJECT_POINTERS *p_SectionObjectPointer; // [rsp+58h] [rbp-50h]
  _QWORD *v39; // [rsp+60h] [rbp-48h]
  size_t *v40; // [rsp+68h] [rbp-40h]
  char v41; // [rsp+B8h] [rbp+10h]
  __int64 v42; // [rsp+B8h] [rbp+10h]
  char v43; // [rsp+C0h] [rbp+18h]
  ULONG Size; // [rsp+C8h] [rbp+20h]
  size_t Sizea; // [rsp+C8h] [rbp+20h]

  v43 = a3;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  v7 = 0;
  v34 = 0;
  v8 = 0;
  *(_QWORD *)SerialNumber = 0;
  if ( !FileObject )
  {
    FsContext = 0;
LABEL_43:
    v11 = -1073741808;
    goto LABEL_44;
  }
  FsContext = (__int64)FileObject->FsContext;
  v35 = FsContext;
  v10 = *(_WORD *)FsContext;
  if ( *(_WORD *)FsContext == 0xEC23 && FileObject->FsContext2 )
    goto LABEL_43;
  if ( v10 == -5087 )
  {
    v11 = -1073741790;
    goto LABEL_44;
  }
  LOBYTE(a3) = 34;
  if ( v10 != -5086 )
    goto LABEL_43;
  v41 = 0;
  FileName = Irp->AssociatedIrp.MasterIrp;
  Size = CurrentStackLocation->Parameters.Create.Options;
  if ( (int)ValidateCopyChunkParameters(FileName, Size) < 0 )
  {
LABEL_23:
    RxInitializeLowIoContext(RxContext, (v43 != 0) + 6, (PLOWIO_CONTEXT)((char *)&RxContext->9 + 120));
    v19 = RxLowIoSubmit(RxContext, Irp, (PFCB)FsContext, RxLowIoFsCtlShellCompletion);
    v11 = v19;
    v8 = 0;
    if ( v19 != 259 && RxContext->InformationToReturn >= 0xC && v19 != -1073741811 )
    {
      _InterlockedOr8((volatile signed __int8 *)(FsContext + 256), 1u);
      FileObject->Flags |= 0x1000u;
      if ( v41 )
      {
        v11 = ComputeFinalCopyChunkDestinationEndingVbo(
                v7 + 8,
                v7[6],
                RxContext->Create.TransportName.Buffer,
                SerialNumber);
        if ( v11 >= 0 )
        {
          v20 = *(_QWORD *)SerialNumber;
          if ( *(_QWORD *)SerialNumber )
          {
            _RxAcquireFcb((PFCB)FsContext, 0, 1u, 0, (PCSTR)FileName, SerialNumber[0]);
            v39 = (_QWORD *)(FsContext + 32);
            v22 = *(_QWORD *)(FsContext + 32);
            v42 = v22;
            FileNamea = v22;
            v23 = (signed __int64 *)(FsContext + 24);
            v36 = FsContext + 24;
            v33 = *(LIST_ENTRY **)(FsContext + 24);
            *(_QWORD *)LineNumber = v33;
            v40 = (size_t *)(FsContext + 40);
            v24 = *(_QWORD *)(FsContext + 40);
            Sizea = v24;
            *(_QWORD *)SerialNumber = v24;
            if ( v20 > v24 )
              *(_QWORD *)(FsContext + 40) = v20;
            if ( v20 > v22 )
            {
              FileObject->Flags |= 0x2000u;
              v25 = *v23;
              if ( v20 > *v23 )
              {
                *v23 = v20;
                v25 = v20;
              }
              *(_QWORD *)(FsContext + 32) = v20;
              if ( v20 > v25 )
              {
                v26 = *(unsigned int *)(*(_QWORD *)(FsContext + 120) + 104LL);
                *v23 = -v26 & (v26 + v20);
              }
            }
            p_SectionObjectPointer = &FileObject->SectionObjectPointer;
            SectionObjectPointer = FileObject->SectionObjectPointer;
            if ( SectionObjectPointer )
            {
              if ( SectionObjectPointer->SharedCacheMap )
              {
                CcSetFileSizes(FileObject, (PCC_FILE_SIZES)(FsContext + 24));
                v24 = (signed __int64)v33;
                if ( v11 )
                {
                  *v39 = v42;
                  *v23 = v24;
                  *v40 = Sizea;
                  SharedCacheMap = FileObject->SectionObjectPointer->SharedCacheMap;
                  if ( SharedCacheMap )
                    SharedCacheMap[1] = v42;
                }
              }
            }
            _RxReleaseFcb(0, (PMRX_FCB)FsContext, (unsigned __int8)v24, v21, FileNamea);
            v8 = 0;
          }
        }
      }
    }
    goto LABEL_44;
  }
  v12 = _RxAcquireFcb((PFCB)FsContext, RxContext, 1u, 0, (PCSTR)FileName, SerialNumber[0]);
  v11 = v12;
  if ( v12 < 0 )
  {
    if ( v12 == -1073741739 )
      BYTE3(RxContext->RealDevice) = 1;
    goto LABEL_44;
  }
  v8 = 1;
  v13 = FileName;
  p_ThreadListEntry = (__int64)&FileName->ThreadListEntry;
  v33 = &FileName->ThreadListEntry;
  a3 = 0;
  CurrentStackLocation = (struct _IO_STACK_LOCATION *)(unsigned int)FileName->AssociatedIrp.IrpCount;
  for ( i = 0; (unsigned int)i < (unsigned int)CurrentStackLocation; i = (unsigned int)(i + 1) )
  {
    v16 = *(unsigned int *)(p_ThreadListEntry + 24 * i + 16) + *(_QWORD *)(p_ThreadListEntry + 24 * i + 8);
    if ( a3 > v16 )
      v16 = a3;
    a3 = v16;
  }
  if ( a3 > *(_QWORD *)(FsContext + 40) )
  {
    RdbssDbgExtension = (int)RxContext->RdbssDbgExtension;
    if ( (RdbssDbgExtension & 2) == 0 )
    {
      BYTE3(RxContext->RealDevice) = 1;
      goto LABEL_44;
    }
    LODWORD(RxContext->RdbssDbgExtension) = RdbssDbgExtension & 0xFFFFEFFF;
    Pool2 = (unsigned int *)ExAllocatePool2(258, Size, 1934456914);
    v7 = Pool2;
    v34 = Pool2;
    if ( !Pool2 )
    {
      v11 = -1073741670;
      goto LABEL_44;
    }
    v41 = 1;
    memmove(Pool2, FileName, Size);
    v13 = FileName;
    p_ThreadListEntry = (__int64)v33;
  }
  v11 = FlushAndPurgeCacheForCopyChunk((__int64)RxContext, FsContext, p_ThreadListEntry, v13->AssociatedIrp.IrpCount);
  if ( v11 >= 0 )
  {
    _RxReleaseFcb(RxContext, (PMRX_FCB)FsContext, (unsigned __int8)a3, (PCSTR)CurrentStackLocation, (ULONG)FileName);
    goto LABEL_23;
  }
LABEL_44:
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  if ( v8 )
    _RxReleaseFcb(RxContext, (PMRX_FCB)FsContext, (unsigned __int8)a3, (PCSTR)CurrentStackLocation, (ULONG)FileName);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400146a0  mov     [rsp+arg_10], r8b
0x1400146a5  mov     [rsp+arg_0], rcx
0x1400146aa  push    rbx
0x1400146ab  push    rsi
0x1400146ac  push    rdi
0x1400146ad  push    r12
0x1400146af  push    r13
0x1400146b1  push    r14
0x1400146b3  push    r15
0x1400146b5  sub     rsp, 70h
0x1400146b9  mov     r13, rdx
0x1400146bc  mov     r12, rcx
0x1400146bf  mov     r9, [rdx+0B8h]
0x1400146c6  mov     rdi, [r9+30h]
0x1400146ca  xor     ebx, ebx
0x1400146cc  mov     [rsp+0A8h+var_70], rbx
0x1400146d1  xor     r15b, r15b
0x1400146d4  mov     qword ptr [rsp+0A8h+SerialNumber], rbx; SerialNumber
0x1400146d9  test    rdi, rdi
0x1400146dc  jz      loc_140014A6E
0x1400146e2  mov     rsi, [rdi+18h]
0x1400146e6  mov     [rsp+0A8h+var_68], rsi
0x1400146eb  movzx   eax, word ptr [rsi]
0x1400146ee  mov     ecx, 0EC23h
0x1400146f3  cmp     ax, cx
0x1400146f6  jnz     short loc_140014708
0x1400146f8  cmp     [rdi+20h], rbx
0x1400146fc  jz      short loc_140014708
0x1400146fe  mov     edx, 0EC28h
0x140014703  jmp     loc_140014A75
0x140014708  mov     ecx, 0EC21h
0x14001470d  cmp     ax, cx
0x140014710  jnz     short loc_14001471D
0x140014712  mov     r14d, 0C0000022h
0x140014718  jmp     loc_140014A8C
0x14001471d  movzx   edx, ax
0x140014720  mov     r8d, 0EC22h
0x140014726  cmp     ax, r8w
0x14001472a  jnz     loc_140014A7A
0x140014730  mov     byte ptr [rsp+0A8h+arg_8], bl
0x140014737  mov     rax, [r13+18h]
0x14001473b  mov     [rsp+0A8h+FileName], rax; FileName
0x140014740  mov     ecx, [r9+10h]
0x140014744  mov     dword ptr [rsp+0A8h+Size], ecx
0x14001474b  mov     edx, ecx
0x14001474d  mov     rcx, rax
0x140014750  call    ValidateCopyChunkParameters
0x140014755  test    eax, eax
0x140014757  js      loc_140014877
0x14001475d  xor     r9d, r9d; LineNumber
0x140014760  mov     r8d, 1; Mode
0x140014766  mov     rdx, r12; RxContext
0x140014769  mov     rcx, rsi; Fcb
0x14001476c  call    __RxAcquireFcb
0x140014771  mov     r14d, eax
0x140014774  test    eax, eax
0x140014776  jns     short loc_14001478E
0x140014778  cmp     eax, 0C0000055h
0x14001477d  jnz     loc_140014A8C
0x140014783  mov     byte ptr [r12+23h], 1
0x140014789  jmp     loc_140014A8C
0x14001478e  mov     r15b, 1
0x140014791  mov     rax, [rsp+0A8h+FileName]
0x140014796  lea     r11, [rax+20h]
0x14001479a  mov     [rsp+0A8h+var_78], r11
0x14001479f  xor     r8d, r8d
0x1400147a2  mov     r9d, [rax+18h]
0x1400147a6  xor     r10d, r10d
0x1400147a9  test    r9d, r9d
0x1400147ac  jz      short loc_1400147D1
0x1400147ae  lea     rcx, [r10+r10*2]
0x1400147b2  mov     edx, [r11+rcx*8+10h]
0x1400147b7  mov     rcx, [r11+rcx*8+8]
0x1400147bc  add     rcx, rdx
0x1400147bf  cmp     r8, rcx
0x1400147c2  cmovg   rcx, r8
0x1400147c6  mov     r8, rcx
0x1400147c9  inc     r10d
0x1400147cc  cmp     r10d, r9d
0x1400147cf  jb      short loc_1400147AE
0x1400147d1  cmp     r8, [rsi+28h]
0x1400147d5  jle     short loc_14001484F
0x1400147d7  mov     eax, [r12+78h]
0x1400147dc  test    al, 2
0x1400147de  jnz     short loc_1400147EA
0x1400147e0  mov     [r12+23h], r15b
0x1400147e5  jmp     loc_140014A8C
0x1400147ea  btr     eax, 0Ch
0x1400147ee  mov     [r12+78h], eax
0x1400147f3  mov     r14d, dword ptr [rsp+0A8h+Size]
0x1400147fb  mov     r8d, 734D7852h
0x140014801  mov     edx, r14d
0x140014804  mov     ecx, 102h
0x140014809  call    cs:__imp_ExAllocatePool2
0x140014810  nop     dword ptr [rax+rax+00h]
0x140014815  mov     rbx, rax
0x140014818  mov     [rsp+0A8h+var_70], rax
0x14001481d  test    rax, rax
0x140014820  jnz     short loc_14001482D
0x140014822  mov     r14d, 0C000009Ah
0x140014828  jmp     loc_140014A8C
0x14001482d  mov     byte ptr [rsp+0A8h+arg_8], r15b
0x140014835  mov     r8, r14; Size
0x140014838  mov     rdx, [rsp+0A8h+FileName]; Src
0x14001483d  mov     rcx, rax; void *
0x140014840  call    memmove
0x140014845  mov     rax, [rsp+0A8h+FileName]
0x14001484a  mov     r11, [rsp+0A8h+var_78]
0x14001484f  mov     r9d, [rax+18h]
0x140014853  mov     r8, r11
0x140014856  mov     rdx, rsi
0x140014859  mov     rcx, r12
0x14001485c  call    FlushAndPurgeCacheForCopyChunk
0x140014861  mov     r14d, eax
0x140014864  test    eax, eax
0x140014866  js      loc_140014A8C
0x14001486c  mov     rdx, rsi; MrxFcb
0x14001486f  mov     rcx, r12; RxContext
0x140014872  call    __RxReleaseFcb
0x140014877  lea     r8, [r12+208h]; LowIoContext
0x14001487f  xor     edx, edx
0x140014881  cmp     [rsp+0A8h+arg_10], dl
0x140014888  setnz   dl
0x14001488b  add     edx, 6; Operation
0x14001488e  mov     rcx, r12; RxContext
0x140014891  call    RxInitializeLowIoContext
0x140014896  lea     r9, RxLowIoFsCtlShellCompletion; CompletionRoutine
0x14001489d  mov     r8, rsi; Fcb
0x1400148a0  mov     rdx, r13; Irp
0x1400148a3  mov     rcx, r12; RxContext
0x1400148a6  call    RxLowIoSubmit
0x1400148ab  mov     r14d, eax
0x1400148ae  xor     r15b, r15b
0x1400148b1  cmp     eax, 103h
0x1400148b6  jz      loc_140014A8C
0x1400148bc  cmp     qword ptr [r12+0B8h], 0Ch
0x1400148c5  jb      loc_140014A8C
0x1400148cb  cmp     eax, 0C000000Dh
0x1400148d0  jz      loc_140014A8C
0x1400148d6  lock or byte ptr [rsi+100h], 1
0x1400148de  or      dword ptr [rdi+50h], 1000h
0x1400148e5  cmp     byte ptr [rsp+0A8h+arg_8], r15b
0x1400148ed  jz      loc_140014A8C
0x1400148f3  lea     rcx, [rbx+20h]
0x1400148f7  lea     r9, [rsp+0A8h+SerialNumber]
0x1400148fc  mov     r8, [r12+230h]
0x140014904  mov     edx, [rbx+18h]
0x140014907  call    ComputeFinalCopyChunkDestinationEndingVbo
0x14001490c  mov     r14d, eax
0x14001490f  test    eax, eax
0x140014911  js      loc_140014A8C
0x140014917  mov     r13, qword ptr [rsp+0A8h+SerialNumber]
0x14001491c  test    r13, r13
0x14001491f  jz      loc_140014A8C
0x140014925  xor     r9d, r9d; LineNumber
0x140014928  xor     edx, edx; RxContext
0x14001492a  mov     r8d, 1; Mode
0x140014930  mov     rcx, rsi; Fcb
0x140014933  call    __RxAcquireFcb
0x140014938  lea     rdx, [rsi+20h]
0x14001493c  mov     [rsp+0A8h+var_48], rdx
0x140014941  mov     rax, [rdx]
0x140014944  mov     [rsp+0A8h+arg_8], rax
0x14001494c  mov     [rsp+0A8h+FileName], rax
0x140014951  lea     r15, [rsi+18h]
0x140014955  mov     [rsp+0A8h+var_60], r15
0x14001495a  mov     rcx, [r15]
0x14001495d  mov     [rsp+0A8h+var_78], rcx
0x140014962  mov     qword ptr [rsp+0A8h+LineNumber], rcx
0x140014967  lea     rcx, [rsi+28h]
0x14001496b  mov     [rsp+0A8h+var_40], rcx
0x140014970  mov     r8, [rcx]
0x140014973  mov     [rsp+0A8h+Size], r8
0x14001497b  mov     qword ptr [rsp+0A8h+SerialNumber], r8
0x140014980  cmp     r13, r8
0x140014983  jle     short loc_140014988
0x140014985  mov     [rcx], r13
0x140014988  cmp     r13, rax
0x14001498b  jle     short loc_1400149BE
0x14001498d  or      dword ptr [rdi+50h], 2000h
0x140014994  mov     rax, [r15]
0x140014997  cmp     r13, rax
0x14001499a  jle     short loc_1400149A2
0x14001499c  mov     [r15], r13
0x14001499f  mov     rax, r13
0x1400149a2  mov     [rdx], r13
0x1400149a5  cmp     r13, rax
0x1400149a8  jle     short loc_1400149BE
0x1400149aa  mov     rax, [rsi+78h]
0x1400149ae  mov     ecx, [rax+68h]
0x1400149b1  lea     rax, [rcx+r13]
0x1400149b5  neg     rcx
0x1400149b8  and     rax, rcx
0x1400149bb  mov     [r15], rax
0x1400149be  lea     r13, [rdi+28h]
0x1400149c2  mov     [rsp+0A8h+var_50], r13
0x1400149c7  mov     rax, [r13+0]
0x1400149cb  test    rax, rax
0x1400149ce  jz      loc_140014A5F
0x1400149d4  cmp     qword ptr [rax+8], 0
0x1400149d9  jz      loc_140014A5F
0x1400149df  mov     rdx, r15; FileSizes
0x1400149e2  mov     rcx, rdi; FileObject
0x1400149e5  call    cs:__imp_CcSetFileSizes
0x1400149ec  nop     dword ptr [rax+rax+00h]
0x1400149f1  mov     rcx, [rsp+0A8h+arg_8]
0x1400149f9  mov     rdx, [rsp+0A8h+Size]
0x140014a01  mov     r8, [rsp+0A8h+var_78]
0x140014a06  jmp     short loc_140014A36
0x140014a08  mov     r14d, eax
0x140014a0b  mov     r12, [rsp+0A8h+arg_0]
0x140014a13  mov     rsi, [rsp+0A8h+var_68]
0x140014a18  mov     rbx, [rsp+0A8h+var_70]
0x140014a1d  mov     rdx, qword ptr [rsp+0A8h+SerialNumber]
0x140014a22  mov     rcx, [rsp+0A8h+FileName]
0x140014a27  mov     r15, [rsp+0A8h+var_60]
0x140014a2c  mov     r8, qword ptr [rsp+0A8h+LineNumber]; LineNumber
0x140014a31  mov     r13, [rsp+0A8h+var_50]
0x140014a36  test    r14d, r14d
0x140014a39  jz      short loc_140014A5F
0x140014a3b  mov     rax, [rsp+0A8h+var_48]
0x140014a40  mov     [rax], rcx
0x140014a43  mov     [r15], r8
0x140014a46  mov     rax, [rsp+0A8h+var_40]
0x140014a4b  mov     [rax], rdx
0x140014a4e  mov     rax, [r13+0]
0x140014a52  mov     rdx, [rax+8]
0x140014a56  test    rdx, rdx
0x140014a59  jz      short loc_140014A5F
0x140014a5b  mov     [rdx+8], rcx
0x140014a5f  mov     rdx, rsi; MrxFcb
0x140014a62  xor     ecx, ecx; RxContext
0x140014a64  call    __RxReleaseFcb
0x140014a69  xor     r15b, r15b
0x140014a6c  jmp     short loc_140014A8C
0x140014a6e  xor     esi, esi
0x140014a70  mov     edx, 0EC20h
0x140014a75  mov     ecx, 0EC21h
0x140014a7a  mov     eax, 0C0000010h
0x140014a7f  mov     r14d, 0C0000022h
0x140014a85  cmp     dx, cx
0x140014a88  cmovnz  r14d, eax
0x140014a8c  test    rbx, rbx
0x140014a8f  jz      short loc_140014AA2
0x140014a91  xor     edx, edx; Tag
0x140014a93  mov     rcx, rbx; P
0x140014a96  call    cs:__imp_ExFreePoolWithTag
0x140014a9d  nop     dword ptr [rax+rax+00h]
0x140014aa2  test    r15b, r15b
0x140014aa5  jz      short loc_140014AB2
0x140014aa7  mov     rdx, rsi; MrxFcb
0x140014aaa  mov     rcx, r12; RxContext
0x140014aad  call    __RxReleaseFcb
0x140014ab2  mov     eax, r14d
0x140014ab5  add     rsp, 70h
0x140014ab9  pop     r15
0x140014abb  pop     r14
0x140014abd  pop     r13
0x140014abf  pop     r12
0x140014ac1  pop     rdi
0x140014ac2  pop     rsi
0x140014ac3  pop     rbx
0x140014ac4  retn
```
