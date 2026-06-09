# RefsFsdWrite(_VOLUME_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400a4ff0`
- end: `0x1400a5691`
- name: `?RefsFsdWrite@@YAJPEAU_VOLUME_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `1697`
- prototype: `int(struct _VOLUME_DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000ab80`
- `0x140039fb0`
- `0x14003a520`
- `0x14003ec10`
- `0x140041a40`
- `0x140041b40`
- `0x14008dbd0`
- `0x14008f8b0`
- `0x1400a4ff0`
- `0x1400a648c`
- `0x1400a7f90`
- `0x1400ca788`
- `0x1400ea204`
- `0x1400fac08`
- `0x1400fac44`
- `0x1401e9ce0`
- `0x14032aa00`
- `0x1403389e4`
- `0x140338ee4`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x1400a512f`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400a512f`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400a5270`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400a5270`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a5246`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a53e8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a5246`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a53e8`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1400a540c`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1400a540c`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400a5653`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400a5653`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a565f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a565f`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1400a51df`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1400a51df`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400a552a`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400a5624`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400a552a`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400a5624`
- `ntoskrnl!CcErrorCallbackRoutine` at `0x1400a554e`
- `ntoskrnl!CcErrorCallbackRoutine` at `0x1400a554e`
- `ntoskrnl!IoWithinStackLimits` at `0x1400a5146`
- `ntoskrnl!IoWithinStackLimits` at `0x1400a5146`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a54fc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a54fc`
- `HAL!KeQueryPerformanceCounter` at `0x1400a52a6`
- `HAL!KeQueryPerformanceCounter` at `0x1400a52a6`

## string_xrefs

- `0x1400a50a8`: `write.c`
- `0x1400a5328`: `write.c`
- `0x1400a53c0`: `write.c`

## pseudocode

```c
__int64 __fastcall RefsFsdWrite(struct _VOLUME_DEVICE_OBJECT *a1, struct _IRP *a2)
{
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *p_CurrentStackLocation; // r14
  PFILE_OBJECT FileObject; // rcx
  char v6; // si
  struct _SCB *FsContext; // r13
  bool v8; // r12
  ULONG_PTR TopLevelIrp; // r15
  bool v10; // cl
  __int64 v11; // rax
  void *v12; // rsp
  char *NPagedPerProcessorLookaside; // r12
  bool v14; // si
  char v15; // al
  int Status; // esi
  bool v17; // r8
  int v18; // eax
  unsigned __int8 v19; // bl
  int v20; // edx
  unsigned int v21; // eax
  char v22; // [rsp+10h] [rbp-680h] BYREF
  char v23; // [rsp+690h] [rbp+0h]
  char v24; // [rsp+691h] [rbp+1h]
  NTSTATUS v25; // [rsp+694h] [rbp+4h]
  int v26; // [rsp+698h] [rbp+8h]
  struct REFS_IO_CONTEXT *v27; // [rsp+6A0h] [rbp+10h]
  __int64 v28; // [rsp+6A8h] [rbp+18h] BYREF
  struct _IRP_CONTEXT *v29; // [rsp+6B0h] [rbp+20h]
  __int128 v30; // [rsp+6B8h] [rbp+28h] BYREF
  __int64 v31; // [rsp+6C8h] [rbp+38h]
  int v32; // [rsp+6D0h] [rbp+40h]
  _QWORD v33[5]; // [rsp+6D8h] [rbp+48h] BYREF
  __int128 v34; // [rsp+700h] [rbp+70h] BYREF

  v33[1] = a2;
  v30 = 0;
  v31 = 0;
  v28 = 0;
  v34 = 0;
  v33[0] = 0;
  p_CurrentStackLocation = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&a2->Tail.Overlay.CurrentStackLocation;
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( (FileObject->Flags & 0x20000000) != 0 )
  {
    RefsCompleteRequest(0, a2, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids, 0);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(0, 0, "write.c", 0xD7u);
    return 0;
  }
  v6 = 0;
  v23 = 0;
  v24 = 0;
  FsContext = (struct _SCB *)FileObject->FsContext;
  v33[3] = FsContext;
  if ( FsContext )
  {
    if ( ((*(_QWORD *)(*((_QWORD *)FsContext + 17) + 8LL) & 4) != 0
       || (*(_QWORD *)(*((_QWORD *)FsContext + 17) + 8LL) & 0x8000LL) != 0)
      && ((*(_QWORD *)(*((_QWORD *)FsContext + 17) + 8LL) & 4) != 0 && (*((_DWORD *)FsContext + 38) & 0x10) != 0
       || *(struct _SCB **)(*((_QWORD *)FsContext + 18) + 40LL) == FsContext) )
    {
      v6 = 1;
    }
    v23 = v6;
    v24 = v6;
  }
  v8 = 0;
  TopLevelIrp = (ULONG_PTR)IoGetTopLevelIrp();
  if ( IoWithinStackLimits(TopLevelIrp, 0x18u) && (TopLevelIrp & 3) == 0 )
    v8 = *(_DWORD *)(TopLevelIrp + 4) == 1397140410;
  v10 = 1;
  if ( TopLevelIrp )
  {
    if ( TopLevelIrp > 0xFFFF )
    {
      if ( v8 )
      {
        v11 = *(_QWORD *)(TopLevelIrp + 16);
        if ( !v11 || (*(_DWORD *)(v11 + 4) & 0x200) == 0 )
          goto LABEL_31;
      }
      v10 = TopLevelIrp != 2147483650;
    }
    else
    {
      v10 = 0;
    }
  }
  DWORD1(v30) = 0;
  *((_QWORD *)&v30 + 1) = TopLevelIrp;
  v31 = 0;
  LOBYTE(v30) = v10;
  if ( v8 )
  {
    BYTE1(v30) = 1;
    BYTE2(v30) = *(_BYTE *)(TopLevelIrp + 2);
  }
  else
  {
    *(_WORD *)((char *)&v30 + 1) = 0;
  }
  TopLevelIrp = (ULONG_PTR)&v30;
LABEL_31:
  if ( v6 )
  {
    if ( (*(_BYTE *)(*((_QWORD *)FsContext + 17) + 8LL) & 1) != 0 )
    {
      RefsCompleteRequest(0, a2, -1073741533);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids, 3221225763LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741533, 0, "write.c", 0x12Bu);
      return 3221225763LL;
    }
    NPagedPerProcessorLookaside = 0;
    v29 = 0;
    v27 = 0;
    KeEnterCriticalRegion();
  }
  else
  {
    if ( IoIsOperationSynchronous(a2) && (a2->Flags & 2) != 0 )
    {
      v12 = alloca(1664);
      NPagedPerProcessorLookaside = &v22;
      v14 = 1;
    }
    else
    {
      v14 = 0;
      NPagedPerProcessorLookaside = (char *)RefsAllocateNPagedPerProcessorLookaside(RefsIrpAndIoContextLookasideList);
      if ( !NPagedPerProcessorLookaside )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            11,
            WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids,
            3221225626LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741670, 0, "write.c", 0xFFu);
        RefsCompleteRequest(0, a2, -1073741670);
        return 3221225626LL;
      }
    }
    RefsInitializeIrpAndIoContext(a2, (struct IRP_AND_IO_CONTEXT *)NPagedPerProcessorLookaside, v14);
    v29 = (struct _IRP_CONTEXT *)NPagedPerProcessorLookaside;
    v27 = (struct REFS_IO_CONTEXT *)(NPagedPerProcessorLookaside + 800);
    v15 = NPagedPerProcessorLookaside[41];
    if ( (v15 & 2) != 0 && (v15 & 4) == 0 )
      a2->MdlAddress = 0;
    KeEnterCriticalRegion();
    if ( !*(_QWORD *)(TopLevelIrp + 16) )
    {
      *(_DWORD *)(TopLevelIrp + 4) = 1397140410;
      *(_QWORD *)(TopLevelIrp + 16) = NPagedPerProcessorLookaside;
      *((_QWORD *)NPagedPerProcessorLookaside + 1) |= 0x100000uLL;
      IoSetTopLevelIrp((PIRP)TopLevelIrp);
    }
    *((_QWORD *)NPagedPerProcessorLookaside + 13) = *(_QWORD *)(TopLevelIrp + 16);
    if ( FsContext && *(_BYTE *)(*((_QWORD *)FsContext + 18) + 10496LL) )
      *((LARGE_INTEGER *)NPagedPerProcessorLookaside + 86) = KeQueryPerformanceCounter(0);
  }
  v33[4] = p_CurrentStackLocation;
  v33[2] = TopLevelIrp;
  Status = 0;
  v26 = 0;
  v32 = IoPropagateActivityIdToThread(a2, &v34, v33);
  v18 = 0;
  while ( !v23 )
  {
    if ( v18 )
      RefsInitializeIoContext((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside, v27, v17, (a2->Flags & 2) != 0);
    if ( Status == -1073741432 )
    {
      RefsCheckpointForLogFileFull((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside);
    }
    else if ( Status == 871 )
    {
      p_CurrentStackLocation->CurrentStackLocation->Control &= ~1u;
      v25 = KeWaitForSingleObject((char *)v27 + 8, Executive, 0, 0, 0);
      Status = a2->IoStatus.Status;
      v25 = Status;
      if ( Status < 0 )
      {
        RefsCompleteRequest((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside, a2, Status);
        goto LABEL_96;
      }
    }
    else if ( (unsigned __int8)CcIsCacheManagerCallbackNeeded((unsigned int)Status) )
    {
      LODWORD(v28) = 8;
      HIDWORD(v28) = Status;
      CcErrorCallbackRoutine(&v28);
    }
    if ( NPagedPerProcessorLookaside )
      RefsPreRequestProcessingExtend((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside, v20);
    if ( (NPagedPerProcessorLookaside[41] & 4) != 0 )
    {
      v21 = RefsCompleteMdl((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside, a2);
    }
    else if ( (a2->Flags & 2) != 0 )
    {
      v21 = RefsCommonIoOnNewStack((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside, v27, a2);
    }
    else
    {
      v21 = RefsCommonWrite((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside, v27, a2);
    }
    Status = v21;
    v25 = v21;
    if ( v21
      && (v21 == -1073741608
       || v21 == -1073741432
       || v21 == -1073741400
       || v21 == 871
       || (unsigned __int8)CcIsCacheManagerCallbackNeeded(v21)) )
    {
      v18 = ++v26;
      if ( (__int128 *)TopLevelIrp == &v30 )
        continue;
    }
    goto LABEL_96;
  }
  if ( (__int128 *)TopLevelIrp == &v30 )
    v19 = 0;
  else
    v19 = RefsSetTopLevelWithoutIrpContext((struct _TOP_LEVEL_CONTEXT *)TopLevelIrp);
  RefsPagingFileIo(a2, FsContext);
  if ( v19 )
    RefsRestoreTopLevelIrpWithoutContext();
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
  {
    Status = 259;
  }
  else
  {
    Status = 259;
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids, 259);
  }
  v25 = 259;
LABEL_96:
  if ( v32 >= 0 )
    IoClearActivityIdThread(v33[0]);
  KeLeaveCriticalRegion();
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400a4ff0  push    rbp
0x1400a4ff2  push    rbx
0x1400a4ff3  push    rsi
0x1400a4ff4  push    rdi
0x1400a4ff5  push    r12
0x1400a4ff7  push    r13
0x1400a4ff9  push    r14
0x1400a4ffb  push    r15
0x1400a4ffd  sub     rsp, 0C8h
0x1400a5004  lea     rbp, [rsp+30h]
0x1400a5009  mov     rax, cs:__security_cookie
0x1400a5010  xor     rax, rbp
0x1400a5013  mov     [rbp+0D0h+var_50], rax
0x1400a501a  mov     rdi, rdx
0x1400a501d  mov     [rbp+0D0h+var_80], rdx
0x1400a5021  xorps   xmm0, xmm0
0x1400a5024  xor     eax, eax
0x1400a5026  movups  [rbp+0D0h+var_A8], xmm0
0x1400a502a  mov     [rbp+0D0h+var_98], rax
0x1400a502e  xor     ebx, ebx
0x1400a5030  mov     [rbp+0D0h+var_B8], rbx
0x1400a5034  movups  [rbp+0D0h+var_60], xmm0
0x1400a5038  mov     [rbp+0D0h+var_88], rbx
0x1400a503c  lea     r14, [rdx+0B8h]
0x1400a5043  mov     rax, [r14]
0x1400a5046  mov     rcx, [rax+30h]
0x1400a504a  mov     eax, [rcx+50h]
0x1400a504d  bt      eax, 1Dh
0x1400a5051  jnb     short loc_1400A50BF
0x1400a5053  xor     r8d, r8d; Status
0x1400a5056  xor     ecx, ecx; struct _IRP_CONTEXT *
0x1400a5058  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1400a505d  lea     rax, WPP_GLOBAL_Control
0x1400a5064  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a506b  cmp     rcx, rax
0x1400a506e  jz      short loc_1400A5097
0x1400a5070  test    dword ptr [rcx+2Ch], 100h
0x1400a5077  jz      short loc_1400A5097
0x1400a5079  cmp     byte ptr [rcx+29h], 5
0x1400a507d  jb      short loc_1400A5097
0x1400a507f  mov     edx, 0Ah
0x1400a5084  xor     r9d, r9d
0x1400a5087  lea     r8, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids
0x1400a508e  mov     rcx, [rcx+18h]
0x1400a5092  call    WPP_SF_d
0x1400a5097  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400a509e  test    al, al
0x1400a50a0  jz      short loc_1400A50B8
0x1400a50a2  mov     r9d, 0D7h; unsigned int
0x1400a50a8  lea     r8, aWriteC; "write.c"
0x1400a50af  xor     edx, edx; struct _IRP_CONTEXT *
0x1400a50b1  xor     ecx, ecx; Status
0x1400a50b3  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1400a50b8  xor     eax, eax
0x1400a50ba  jmp     loc_1400A566D
0x1400a50bf  xor     sil, sil
0x1400a50c2  mov     [rbp+0D0h+var_D0], sil
0x1400a50c6  mov     [rbp+0D0h+var_CF], sil
0x1400a50ca  mov     r13, [rcx+18h]
0x1400a50ce  mov     [rbp+0D0h+var_70], r13
0x1400a50d2  test    r13, r13
0x1400a50d5  jz      short loc_1400A512C
0x1400a50d7  mov     rax, [r13+88h]
0x1400a50de  mov     rcx, [rax+8]
0x1400a50e2  test    cl, 4
0x1400a50e5  jnz     short loc_1400A50F9
0x1400a50e7  mov     rax, [r13+88h]
0x1400a50ee  mov     rcx, [rax+8]
0x1400a50f2  bt      rcx, 0Fh
0x1400a50f7  jnb     short loc_1400A5124
0x1400a50f9  mov     rax, [r13+88h]
0x1400a5100  mov     rcx, [rax+8]
0x1400a5104  test    cl, 4
0x1400a5107  jz      short loc_1400A5114
0x1400a5109  mov     eax, [r13+98h]
0x1400a5110  test    al, 10h
0x1400a5112  jnz     short loc_1400A5121
0x1400a5114  mov     rax, [r13+90h]
0x1400a511b  cmp     [rax+28h], r13
0x1400a511f  jnz     short loc_1400A5124
0x1400a5121  mov     sil, 1
0x1400a5124  mov     [rbp+0D0h+var_D0], sil
0x1400a5128  mov     [rbp+0D0h+var_CF], sil
0x1400a512c  xor     r12b, r12b
0x1400a512f  call    cs:__imp_IoGetTopLevelIrp
0x1400a5136  nop     dword ptr [rax+rax+00h]
0x1400a513b  mov     r15, rax
0x1400a513e  mov     edx, 18h; RegionSize
0x1400a5143  mov     rcx, rax; RegionStart
0x1400a5146  call    cs:__imp_IoWithinStackLimits
0x1400a514d  nop     dword ptr [rax+rax+00h]
0x1400a5152  test    eax, eax
0x1400a5154  jz      short loc_1400A5171
0x1400a5156  test    r15b, 3
0x1400a515a  jnz     short loc_1400A5171
0x1400a515c  movzx   r12d, r12b
0x1400a5160  mov     eax, 1
0x1400a5165  cmp     dword ptr [r15+4], 5346ABBAh
0x1400a516d  cmovz   r12d, eax
0x1400a5171  mov     cl, 1
0x1400a5173  test    r15, r15
0x1400a5176  jz      short loc_1400A51AA
0x1400a5178  cmp     r15, 0FFFFh
0x1400a517f  ja      short loc_1400A5185
0x1400a5181  xor     cl, cl
0x1400a5183  jmp     short loc_1400A51AA
0x1400a5185  test    r12b, r12b
0x1400a5188  jz      short loc_1400A519C
0x1400a518a  mov     rax, [r15+10h]
0x1400a518e  test    rax, rax
0x1400a5191  jz      short loc_1400A51D3
0x1400a5193  test    dword ptr [rax+4], 200h
0x1400a519a  jz      short loc_1400A51D3
0x1400a519c  movzx   ecx, cl
0x1400a519f  mov     eax, 80000002h
0x1400a51a4  cmp     r15, rax
0x1400a51a7  cmovz   ecx, ebx
0x1400a51aa  mov     dword ptr [rbp+0D0h+var_A8+4], ebx
0x1400a51ad  mov     qword ptr [rbp+0D0h+var_A8+8], r15
0x1400a51b1  mov     [rbp+0D0h+var_98], rbx
0x1400a51b5  mov     byte ptr [rbp+0D0h+var_A8], cl
0x1400a51b8  test    r12b, r12b
0x1400a51bb  jz      short loc_1400A51CB
0x1400a51bd  mov     byte ptr [rbp+0D0h+var_A8+1], 1
0x1400a51c1  movzx   eax, byte ptr [r15+2]
0x1400a51c6  mov     byte ptr [rbp+0D0h+var_A8+2], al
0x1400a51c9  jmp     short loc_1400A51CF
0x1400a51cb  mov     word ptr [rbp+0D0h+var_A8+1], bx
0x1400a51cf  lea     r15, [rbp+0D0h+var_A8]
0x1400a51d3  test    sil, sil
0x1400a51d6  jnz     loc_1400A5355
0x1400a51dc  mov     rcx, rdi; Irp
0x1400a51df  call    cs:__imp_IoIsOperationSynchronous
0x1400a51e6  nop     dword ptr [rax+rax+00h]
0x1400a51eb  test    al, al
0x1400a51ed  jz      loc_1400A52BF
0x1400a51f3  mov     eax, [rdi+10h]
0x1400a51f6  test    al, 2
0x1400a51f8  jz      loc_1400A52BF
0x1400a51fe  mov     eax, [rsp+100h+var_100]
0x1400a5201  mov     eax, 680h
0x1400a5206  sub     rsp, rax
0x1400a5209  lea     r12, [rsp+780h+var_750]
0x1400a520e  mov     eax, [r12]
0x1400a5212  mov     sil, 1
0x1400a5215  movzx   r8d, sil; bool
0x1400a5219  mov     rdx, r12; struct IRP_AND_IO_CONTEXT *
0x1400a521c  mov     rcx, rdi; Irp
0x1400a521f  call    ?RefsInitializeIrpAndIoContext@@YAXPEAU_IRP@@PEAUIRP_AND_IO_CONTEXT@@_N@Z; RefsInitializeIrpAndIoContext(_IRP *,IRP_AND_IO_CONTEXT *,bool)
0x1400a5224  mov     [rbp+0D0h+var_B0], r12
0x1400a5228  lea     rax, [r12+320h]
0x1400a5230  mov     [rbp+0D0h+var_C0], rax
0x1400a5234  movzx   eax, byte ptr [r12+29h]
0x1400a523a  test    al, 2
0x1400a523c  jz      short loc_1400A5246
0x1400a523e  test    al, 4
0x1400a5240  jnz     short loc_1400A5246
0x1400a5242  mov     [rdi+8], rbx
0x1400a5246  call    cs:__imp_KeEnterCriticalRegion
0x1400a524d  nop     dword ptr [rax+rax+00h]
0x1400a5252  cmp     [r15+10h], rbx
0x1400a5256  jnz     short loc_1400A527C
0x1400a5258  mov     dword ptr [r15+4], 5346ABBAh
0x1400a5260  mov     [r15+10h], r12
0x1400a5264  or      qword ptr [r12+8], 100000h
0x1400a526d  mov     rcx, r15; Irp
0x1400a5270  call    cs:__imp_IoSetTopLevelIrp
0x1400a5277  nop     dword ptr [rax+rax+00h]
0x1400a527c  mov     rax, [r15+10h]
0x1400a5280  mov     [r12+68h], rax
0x1400a5285  test    r13, r13
0x1400a5288  jz      loc_1400A53F4
0x1400a528e  mov     rax, [r13+90h]
0x1400a5295  movzx   ecx, byte ptr [rax+2900h]
0x1400a529c  test    cl, cl
0x1400a529e  jz      loc_1400A53F4
0x1400a52a4  xor     ecx, ecx; PerformanceFrequency
0x1400a52a6  call    cs:__imp_KeQueryPerformanceCounter
0x1400a52ad  nop     dword ptr [rax+rax+00h]
0x1400a52b2  mov     [r12+2B0h], rax
0x1400a52ba  jmp     loc_1400A53F4
0x1400a52bf  xor     sil, sil
0x1400a52c2  mov     rcx, cs:?RefsIrpAndIoContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; struct _NPAGED_LOOKASIDE_LIST *
0x1400a52c9  call    ?RefsAllocateNPagedPerProcessorLookaside@@YAPEAXPEAU_NPAGED_LOOKASIDE_LIST@@@Z; RefsAllocateNPagedPerProcessorLookaside(_NPAGED_LOOKASIDE_LIST *)
0x1400a52ce  mov     r12, rax
0x1400a52d1  test    rax, rax
0x1400a52d4  jnz     loc_1400A5215
0x1400a52da  lea     rax, WPP_GLOBAL_Control
0x1400a52e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a52e8  cmp     rcx, rax
0x1400a52eb  jz      short loc_1400A5317
0x1400a52ed  test    dword ptr [rcx+2Ch], 100h
0x1400a52f4  jz      short loc_1400A5317
0x1400a52f6  cmp     byte ptr [rcx+29h], 4
0x1400a52fa  jb      short loc_1400A5317
0x1400a52fc  mov     edx, 0Bh
0x1400a5301  mov     r9d, 0C000009Ah
0x1400a5307  lea     r8, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids
0x1400a530e  mov     rcx, [rcx+18h]
0x1400a5312  call    WPP_SF_d
0x1400a5317  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400a531e  test    al, al
0x1400a5320  jz      short loc_1400A533B
0x1400a5322  mov     r9d, 0FFh; unsigned int
0x1400a5328  lea     r8, aWriteC; "write.c"
0x1400a532f  xor     edx, edx; struct _IRP_CONTEXT *
0x1400a5331  mov     ecx, 0C000009Ah; Status
0x1400a5336  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1400a533b  mov     r8d, 0C000009Ah; Status
0x1400a5341  mov     rdx, rdi; Irp
0x1400a5344  xor     ecx, ecx; struct _IRP_CONTEXT *
0x1400a5346  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1400a534b  mov     eax, 0C000009Ah
0x1400a5350  jmp     loc_1400A566D
0x1400a5355  mov     rax, [r13+88h]
0x1400a535c  test    byte ptr [rax+8], 1
0x1400a5360  jz      short loc_1400A53DD
0x1400a5362  mov     r8d, 0C0000123h; Status
0x1400a5368  mov     rdx, rdi; Irp
0x1400a536b  xor     ecx, ecx; struct _IRP_CONTEXT *
0x1400a536d  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1400a5372  lea     rax, WPP_GLOBAL_Control
0x1400a5379  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5380  cmp     rcx, rax
0x1400a5383  jz      short loc_1400A53AF
0x1400a5385  test    dword ptr [rcx+2Ch], 100h
0x1400a538c  jz      short loc_1400A53AF
0x1400a538e  cmp     byte ptr [rcx+29h], 4
0x1400a5392  jb      short loc_1400A53AF
0x1400a5394  mov     edx, 0Ch
0x1400a5399  mov     r9d, 0C0000123h
0x1400a539f  lea     r8, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids
0x1400a53a6  mov     rcx, [rcx+18h]
0x1400a53aa  call    WPP_SF_d
0x1400a53af  movzx   ecx, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400a53b6  test    cl, cl
0x1400a53b8  jz      short loc_1400A53D3
0x1400a53ba  mov     r9d, 12Bh; unsigned int
0x1400a53c0  lea     r8, aWriteC; "write.c"
0x1400a53c7  xor     edx, edx; struct _IRP_CONTEXT *
0x1400a53c9  mov     ecx, 0C0000123h; Status
0x1400a53ce  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1400a53d3  mov     eax, 0C0000123h
0x1400a53d8  jmp     loc_1400A566D
0x1400a53dd  mov     r12, rbx
0x1400a53e0  mov     [rbp+0D0h+var_B0], rbx
0x1400a53e4  mov     [rbp+0D0h+var_C0], rbx
0x1400a53e8  call    cs:__imp_KeEnterCriticalRegion
0x1400a53ef  nop     dword ptr [rax+rax+00h]
0x1400a53f4  mov     [rbp+0D0h+var_68], r14
0x1400a53f8  mov     [rbp+0D0h+var_78], r15
0x1400a53fc  mov     esi, ebx
0x1400a53fe  mov     [rbp+0D0h+var_C8], ebx
0x1400a5401  lea     r8, [rbp+0D0h+var_88]
0x1400a5405  lea     rdx, [rbp+0D0h+var_60]
0x1400a5409  mov     rcx, rdi
0x1400a540c  call    cs:__imp_IoPropagateActivityIdToThread
0x1400a5413  nop     dword ptr [rax+rax+00h]
0x1400a5418  mov     [rbp+0D0h+var_90], eax
0x1400a541b  mov     eax, ebx
0x1400a541d  cmp     [rbp+0D0h+var_D0], 0
0x1400a5421  jz      loc_1400A54A8
0x1400a5427  lea     rax, [rbp+0D0h+var_A8]
0x1400a542b  cmp     r15, rax
0x1400a542e  jz      short loc_1400A543D
0x1400a5430  mov     rcx, r15; struct _TOP_LEVEL_CONTEXT *
0x1400a5433  call    ?RefsSetTopLevelWithoutIrpContext@@YAEPEAU_TOP_LEVEL_CONTEXT@@@Z; RefsSetTopLevelWithoutIrpContext(_TOP_LEVEL_CONTEXT *)
0x1400a5438  movzx   ebx, al
0x1400a543b  jmp     short loc_1400A543F
0x1400a543d  xor     bl, bl
0x1400a543f  mov     rdx, r13; struct _SCB *
0x1400a5442  mov     rcx, rdi; Irp
0x1400a5445  call    ?RefsPagingFileIo@@YAXPEAU_IRP@@PEAU_SCB@@@Z; RefsPagingFileIo(_IRP *,_SCB *)
0x1400a544a  test    bl, bl
0x1400a544c  jz      short loc_1400A5453
0x1400a544e  call    ?RefsRestoreTopLevelIrpWithoutContext@@YAXXZ; RefsRestoreTopLevelIrpWithoutContext(void)
0x1400a5453  lea     rax, WPP_GLOBAL_Control
0x1400a545a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5461  cmp     rcx, rax
0x1400a5464  jz      short loc_1400A5494
0x1400a5466  test    dword ptr [rcx+2Ch], 100h
0x1400a546d  jz      short loc_1400A5494
0x1400a546f  cmp     byte ptr [rcx+29h], 5
0x1400a5473  jb      short loc_1400A5494
0x1400a5475  mov     edx, 0Dh
0x1400a547a  mov     esi, 103h
0x1400a547f  mov     r9d, esi
0x1400a5482  lea     r8, WPP_07f6fe4c040b3e18d4debf0891266445_Traceguids
0x1400a5489  mov     rcx, [rcx+18h]
0x1400a548d  call    WPP_SF_d
0x1400a5492  jmp     short loc_1400A5499
0x1400a5494  mov     esi, 103h
0x1400a5499  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400a54a0  mov     [rbp+0D0h+var_CC], esi
0x1400a54a3  jmp     loc_1400A5649
0x1400a54a8  test    eax, eax
0x1400a54aa  jz      short loc_1400A54C3
0x1400a54ac  mov     r9d, [rdi+10h]
0x1400a54b0  shr     r9d, 1
0x1400a54b3  and     r9b, 1; bool
  ... truncated ...
```
