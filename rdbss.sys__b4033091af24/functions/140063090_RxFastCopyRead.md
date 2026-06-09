# RxFastCopyRead

- ea: `0x140063090`
- end: `0x1400635b1`
- name: `RxFastCopyRead`
- size: `1313`
- prototype: `__int64 __usercall@<rax>(PFILE_OBJECT FileObject@<rcx>, PLARGE_INTEGER FileOffset@<rdx>, int, PVOID, PIO_STATUS_BLOCK, __int64, PIRP Irp)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x140062e70`

## callees

- `0x140003410`
- `0x1400037e0`
- `0x140008f60`
- `0x140009ea0`
- `0x14000e770`
- `0x14001d0dc`
- `0x140025d00`
- `0x140063090`

## import_xrefs

- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14007b02e`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14007b02e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140063288`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14006337c`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140063288`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14006337c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400633a7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400633a7`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400631ba`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140063525`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400631ba`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140063525`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400631ec`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400631ec`
- `ntoskrnl!CcSetAdditionalCacheAttributes` at `0x14006344e`
- `ntoskrnl!CcSetAdditionalCacheAttributes` at `0x14006344e`
- `ntoskrnl!CcFastCopyRead` at `0x1400632d1`
- `ntoskrnl!CcFastCopyRead` at `0x1400632d1`
- `ntoskrnl!CcCopyRead` at `0x140063323`
- `ntoskrnl!CcCopyRead` at `0x140063323`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400633c5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400633c5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140063125`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140063125`

## pseudocode

```c
__int64 __fastcall RxFastCopyRead(
        PFILE_OBJECT FileObject,
        PLARGE_INTEGER FileOffset,
        __int64 a3,
        BOOLEAN a4,
        int a5,
        PVOID Buffer,
        PIO_STATUS_BLOCK IoStatus,
        __int64 a8,
        PIRP Irp)
{
  PVOID FsContext; // rdi
  char v13; // r12
  enum _RX_BLOCK_CONDITION *RxContext; // r14
  LONGLONG v15; // rbx
  struct _ERESOURCE *v16; // rcx
  char v17; // al
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  LONGLONG v19; // rax
  BOOLEAN v20; // bl
  int v21; // eax
  PIO_STATUS_BLOCK v22; // r15
  char v23; // si
  char v24; // r15
  int v25; // r13d
  __int64 v27; // r9
  __int64 v28; // [rsp+60h] [rbp-48h]
  ULONG PageCount[2]; // [rsp+68h] [rbp-40h]
  unsigned __int64 PageCounta; // [rsp+68h] [rbp-40h]
  ULONG Length; // [rsp+C0h] [rbp+18h]

  Length = a3;
  FsContext = 0;
  v28 = FileOffset->LowPart & 0xFFF;
  v13 = 0;
  RxContext = 0;
  if ( !(_DWORD)a3 )
  {
    IoStatus->Status = 0;
    IoStatus->Information = 0;
    v20 = 1;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    goto LABEL_24;
  }
  if ( FileOffset->QuadPart < 0 )
  {
    v20 = 0;
    v23 = 0;
    v25 = 162;
    v24 = 0;
    goto LABEL_24;
  }
  *(_QWORD *)PageCount = (unsigned int)a3;
  v15 = (unsigned int)a3 + FileOffset->QuadPart;
  if ( v15 <= 0 )
  {
    v20 = 0;
    v23 = 0;
    v25 = 180;
    v24 = 0;
    goto LABEL_24;
  }
  FsContext = FileObject->FsContext;
  if ( (*((_DWORD *)FsContext + 39) & 0x2000000) != 0 )
  {
    v20 = 0;
    v23 = 0;
    v25 = 194;
    v24 = 0;
    goto LABEL_24;
  }
  KeEnterCriticalRegion();
  if ( *((_QWORD *)FsContext + 16) )
  {
    LOBYTE(a8) = 0;
    if ( a4 )
    {
      RxContext = (enum _RX_BLOCK_CONDITION *)RxCreateRxContext(
                                                0,
                                                *(PRDBSS_DEVICE_OBJECT *)(*(_QWORD *)(*((_QWORD *)FsContext + 15) + 32LL)
                                                                        + 48LL),
                                                2u);
      if ( !RxContext )
      {
        v20 = 0;
        v23 = 0;
        v25 = 226;
        v24 = 1;
        goto LABEL_24;
      }
    }
    v13 = RxWaitForStableLViewOnFcbAndAcquireRundown(RxContext, (PMRX_FCB)FsContext, (__int64)&a8);
    if ( !v13 && !(_BYTE)a8 )
    {
      v20 = 0;
      v23 = 0;
      v25 = 241;
      v24 = 1;
      goto LABEL_24;
    }
  }
  v16 = (struct _ERESOURCE *)*((_QWORD *)FsContext + 1);
  if ( a4 )
  {
    ExAcquireResourceSharedLite(v16, 1u);
  }
  else if ( !ExAcquireResourceSharedLite(v16, 0) )
  {
    v20 = 0;
    v23 = 0;
    v25 = 265;
    v24 = 1;
    goto LABEL_24;
  }
  LOBYTE(a8) = 1;
  if ( !FileObject->PrivateCacheMap || (v17 = *((_BYTE *)FsContext + 5)) == 0 )
  {
    v25 = 282;
LABEL_48:
    v23 = a8;
    v24 = a8;
    v20 = 0;
    goto LABEL_24;
  }
  if ( v17 == 2 )
  {
    RelatedDeviceObject = IoGetRelatedDeviceObject(FileObject);
    if ( !((unsigned __int8 (__fastcall *)(PFILE_OBJECT, PLARGE_INTEGER, _QWORD, _QWORD, int, char, PIO_STATUS_BLOCK, PDEVICE_OBJECT))RelatedDeviceObject->DriverObject->FastIoDispatch->FastIoCheckIfPossible)(
            FileObject,
            FileOffset,
            Length,
            a4,
            a5,
            1,
            IoStatus,
            RelatedDeviceObject) )
    {
      v25 = 327;
      goto LABEL_48;
    }
  }
  v19 = *((_QWORD *)FsContext + 4);
  if ( v15 > v19 )
  {
    if ( FileOffset->QuadPart >= v19 )
    {
      IoStatus->Status = -1073741807;
      IoStatus->Information = 0;
      v20 = 1;
      v25 = 343;
      v23 = 1;
      v24 = 1;
      goto LABEL_24;
    }
    Length = v19 - FileOffset->QuadPart;
  }
  v20 = 1;
  PageCounta = (unsigned __int64)(*(_QWORD *)PageCount + v28 + 4095) >> 12;
  v21 = *((_DWORD *)FsContext + 39);
  if ( (v21 & 0x100) != 0 && (v21 & 0x8000000) == 0 && FileOffset->QuadPart >= 4096 )
  {
    CcSetAdditionalCacheAttributes(FileObject, 0, 0);
    *((_DWORD *)FsContext + 39) &= ~0x100u;
  }
  IoSetTopLevelIrp(Irp);
  if ( !a4 || *((_DWORD *)FsContext + 9) | HIDWORD(v15) )
  {
    v20 = CcCopyRead(FileObject, FileOffset, Length, a4, Buffer, IoStatus);
    v22 = IoStatus;
  }
  else
  {
    v22 = IoStatus;
    CcFastCopyRead(FileObject, FileOffset->LowPart, Length, PageCounta, Buffer, IoStatus);
  }
  _InterlockedOr((volatile signed __int32 *)&FileObject->Flags, 0x80000u);
  if ( v20 )
    FileObject->CurrentByteOffset.QuadPart = FileOffset->QuadPart + v22->Information;
  v23 = a8;
  v24 = a8;
  v25 = 0;
  IoSetTopLevelIrp(0);
LABEL_24:
  if ( v13 )
  {
    if ( RxContext )
      RxReleaseLViewRundown(RxContext);
    else
      RxReleaseRundownDerefView(FsContext);
  }
  if ( v23 )
    ExReleaseResourceLite(*((PERESOURCE *)FsContext + 1));
  if ( RxContext )
    RxDereferenceAndDeleteRxContext_Real((PRX_CONTEXT)RxContext);
  if ( v24 )
    KeLeaveCriticalRegion();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v27 = 78;
    if ( v20 )
      v27 = 89;
    WPP_SF_cd(WPP_GLOBAL_Control->AttachedDevice, FileOffset, a3, v27, v25);
  }
  return v20;
}

```

## disassembly

```asm
0x140063090  mov     [rsp+arg_0], rbx
0x140063095  mov     [rsp+arg_18], rsi
0x14006309a  mov     [rsp+Length], r8d
0x14006309f  push    rdi
0x1400630a0  push    r12
0x1400630a2  push    r13
0x1400630a4  push    r14
0x1400630a6  push    r15
0x1400630a8  sub     rsp, 80h
0x1400630af  movzx   r15d, r9b
0x1400630b3  mov     r13, rdx
0x1400630b6  mov     rsi, rcx
0x1400630b9  xor     edi, edi
0x1400630bb  mov     eax, [rdx]
0x1400630bd  and     eax, 0FFFh
0x1400630c2  mov     [rsp+0A8h+var_48], rax
0x1400630c7  xor     r12b, r12b
0x1400630ca  mov     [rsp+0A8h+var_58], r12b
0x1400630cf  xor     ecx, ecx
0x1400630d1  mov     [rsp+0A8h+var_54], ecx
0x1400630d5  xor     r14d, r14d
0x1400630d8  mov     [rsp+0A8h+var_50], r14
0x1400630dd  test    r8d, r8d
0x1400630e0  jz      loc_140063410
0x1400630e6  mov     rax, [rdx]
0x1400630e9  test    rax, rax
0x1400630ec  js      loc_140063552
0x1400630f2  mov     ecx, r8d
0x1400630f5  mov     qword ptr [rsp+0A8h+PageCount], rcx
0x1400630fa  lea     rbx, [rcx+rax]
0x1400630fe  mov     [rsp+0A8h+var_38], rbx
0x140063103  test    rbx, rbx
0x140063106  jle     loc_140063565
0x14006310c  mov     rdi, [rsi+18h]
0x140063110  mov     [rsp+0A8h+var_30], rdi
0x140063115  test    dword ptr [rdi+9Ch], 2000000h
0x14006311f  jnz     loc_140063499
0x140063125  call    cs:__imp_KeEnterCriticalRegion
0x14006312c  nop     dword ptr [rax+rax+00h]
0x140063131  mov     [rsp+0A8h+arg_8], 1
0x140063139  cmp     [rdi+80h], r14
0x140063140  jz      short loc_1400631AB
0x140063142  mov     byte ptr [rsp+0A8h+arg_38], r12b
0x14006314a  test    r15b, r15b
0x14006314d  jz      short loc_14006317C
0x14006314f  mov     rax, [rdi+78h]
0x140063153  mov     rdx, [rax+20h]
0x140063157  mov     r8d, 2; InitialContextFlags
0x14006315d  mov     rdx, [rdx+30h]; RxDeviceObject
0x140063161  xor     ecx, ecx; Irp
0x140063163  call    RxCreateRxContext
0x140063168  mov     r14, rax
0x14006316b  mov     [rsp+0A8h+var_50], rax
0x140063170  test    rax, rax
0x140063173  jz      loc_140063469
0x140063179  test    r15b, r15b
0x14006317c  setz    r8b
0x140063180  lea     rax, [rsp+0A8h+arg_38]
0x140063188  mov     [rsp+0A8h+Buffer], rax; __int64
0x14006318d  xor     r9d, r9d
0x140063190  mov     rdx, rdi; MrxFcb
0x140063193  mov     rcx, r14; Condition
0x140063196  call    RxWaitForStableLViewOnFcbAndAcquireRundown
0x14006319b  movzx   r12d, al
0x14006319f  mov     [rsp+0A8h+var_58], al
0x1400631a3  test    al, al
0x1400631a5  jz      loc_1400634AC
0x1400631ab  mov     rcx, [rdi+8]; Resource
0x1400631af  test    r15b, r15b
0x1400631b2  jz      loc_140063523
0x1400631b8  mov     dl, 1; Wait
0x1400631ba  call    cs:__imp_ExAcquireResourceSharedLite
0x1400631c1  nop     dword ptr [rax+rax+00h]
0x1400631c6  mov     byte ptr [rsp+0A8h+arg_38], 1
0x1400631ce  cmp     qword ptr [rsi+30h], 0
0x1400631d3  jz      loc_1400634E0
0x1400631d9  movzx   eax, byte ptr [rdi+5]
0x1400631dd  test    al, al
0x1400631df  jz      loc_1400634E0
0x1400631e5  cmp     al, 2
0x1400631e7  jnz     short loc_140063248
0x1400631e9  mov     rcx, rsi; FileObject
0x1400631ec  call    cs:__imp_IoGetRelatedDeviceObject
0x1400631f3  nop     dword ptr [rax+rax+00h]
0x1400631f8  mov     rcx, [rax+8]
0x1400631fc  mov     rdx, [rcx+50h]
0x140063200  mov     r10, [rdx+8]
0x140063204  mov     [rsp+0A8h+var_70], rax
0x140063209  mov     rax, [rsp+0A8h+arg_30]
0x140063211  mov     [rsp+0A8h+var_78], rax
0x140063216  mov     byte ptr [rsp+0A8h+IoStatus], 1
0x14006321b  mov     ecx, [rsp+0A8h+arg_20]
0x140063222  mov     dword ptr [rsp+0A8h+Buffer], ecx
0x140063226  movzx   r9d, r15b
0x14006322a  mov     r8d, [rsp+0A8h+Length]
0x140063232  mov     rdx, r13
0x140063235  mov     rcx, rsi
0x140063238  mov     rax, r10
0x14006323b  call    _guard_dispatch_icall
0x140063240  test    al, al
0x140063242  jz      loc_140063578
0x140063248  mov     rax, [rdi+20h]
0x14006324c  cmp     rbx, rax
0x14006324f  jg      loc_140063482
0x140063255  mov     bl, 1
0x140063257  mov     rax, [rsp+0A8h+var_48]
0x14006325c  add     rax, 0FFFh
0x140063262  add     rax, qword ptr [rsp+0A8h+PageCount]
0x140063267  shr     rax, 0Ch
0x14006326b  mov     qword ptr [rsp+0A8h+PageCount], rax
0x140063270  mov     eax, [rdi+9Ch]
0x140063276  bt      eax, 8
0x14006327a  jb      loc_14006342E
0x140063280  mov     rcx, [rsp+0A8h+Irp]; Irp
0x140063288  call    cs:__imp_IoSetTopLevelIrp
0x14006328f  nop     dword ptr [rax+rax+00h]
0x140063294  nop
0x140063295  test    r15b, r15b
0x140063298  jz      short loc_1400632F7
0x14006329a  mov     eax, dword ptr [rsp+0A8h+var_38+4]
0x14006329e  or      eax, [rdi+24h]
0x1400632a1  jnz     short loc_1400632F7
0x1400632a3  mov     r15, [rsp+0A8h+arg_30]
0x1400632ab  mov     [rsp+0A8h+IoStatus], r15; IoStatus
0x1400632b0  mov     rax, [rsp+0A8h+arg_28]
0x1400632b8  mov     [rsp+0A8h+Buffer], rax; Buffer
0x1400632bd  mov     r9d, [rsp+0A8h+PageCount]; PageCount
0x1400632c2  mov     r8d, [rsp+0A8h+Length]; Length
0x1400632ca  mov     edx, [r13+0]; FileOffset
0x1400632ce  mov     rcx, rsi; FileObject
0x1400632d1  call    cs:__imp_CcFastCopyRead
0x1400632d8  nop     dword ptr [rax+rax+00h]
0x1400632dd  lock or dword ptr [rsi+50h], 80000h
0x1400632e5  test    bl, bl
0x1400632e7  jz      short loc_140063340
0x1400632e9  mov     rcx, [r15+8]
0x1400632ed  add     rcx, [r13+0]
0x1400632f1  mov     [rsi+68h], rcx
0x1400632f5  jmp     short loc_140063340
0x1400632f7  mov     rax, [rsp+0A8h+arg_30]
0x1400632ff  mov     [rsp+0A8h+IoStatus], rax; IoStatus
0x140063304  mov     rax, [rsp+0A8h+arg_28]
0x14006330c  mov     [rsp+0A8h+Buffer], rax; Buffer
0x140063311  movzx   r9d, r15b; Wait
0x140063315  mov     r8d, [rsp+0A8h+Length]; Length
0x14006331d  mov     rdx, r13; FileOffset
0x140063320  mov     rcx, rsi; FileObject
0x140063323  call    cs:__imp_CcCopyRead
0x14006332a  nop     dword ptr [rax+rax+00h]
0x14006332f  movzx   ebx, al
0x140063332  mov     [rsp+0A8h+var_57], al
0x140063336  mov     r15, [rsp+0A8h+arg_30]
0x14006333e  jmp     short loc_1400632DD
0x140063340  movzx   esi, byte ptr [rsp+0A8h+arg_38]
0x140063348  movzx   r15d, sil
0x14006334c  mov     r13d, [rsp+0A8h+var_54]
0x140063351  jmp     short loc_14006337A
0x140063353  xor     bl, bl
0x140063355  mov     [rsp+0A8h+var_57], bl
0x140063359  mov     rdi, [rsp+0A8h+var_30]
0x14006335e  movzx   r12d, [rsp+0A8h+var_58]
0x140063364  movzx   esi, byte ptr [rsp+0A8h+arg_38]
0x14006336c  movzx   r15d, sil
0x140063370  mov     r13d, [rsp+0A8h+var_54]
0x140063375  mov     r14, [rsp+0A8h+var_50]
0x14006337a  xor     ecx, ecx; Irp
0x14006337c  call    cs:__imp_IoSetTopLevelIrp
0x140063383  nop     dword ptr [rax+rax+00h]
0x140063388  test    r12b, r12b
0x14006338b  jz      short loc_14006339E
0x14006338d  test    r14, r14
0x140063390  jz      loc_1400634D3
0x140063396  mov     rcx, r14
0x140063399  call    RxReleaseLViewRundown
0x14006339e  test    sil, sil
0x1400633a1  jz      short loc_1400633B3
0x1400633a3  mov     rcx, [rdi+8]; Resource
0x1400633a7  call    cs:__imp_ExReleaseResourceLite
0x1400633ae  nop     dword ptr [rax+rax+00h]
0x1400633b3  test    r14, r14
0x1400633b6  jz      short loc_1400633C0
0x1400633b8  mov     rcx, r14; RxContext
0x1400633bb  call    RxDereferenceAndDeleteRxContext_Real
0x1400633c0  test    r15b, r15b
0x1400633c3  jz      short loc_1400633D1
0x1400633c5  call    cs:__imp_KeLeaveCriticalRegion
0x1400633cc  nop     dword ptr [rax+rax+00h]
0x1400633d1  lea     rax, WPP_GLOBAL_Control
0x1400633d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400633df  cmp     rcx, rax
0x1400633e2  jz      short loc_1400633EF
0x1400633e4  mov     eax, [rcx+2Ch]
0x1400633e7  test    al, 10h
0x1400633e9  jnz     loc_140063583
0x1400633ef  movzx   eax, bl
0x1400633f2  lea     r11, [rsp+0A8h+var_28]
0x1400633fa  mov     rbx, [r11+30h]
0x1400633fe  mov     rsi, [r11+48h]
0x140063402  mov     rsp, r11
0x140063405  pop     r15
0x140063407  pop     r14
0x140063409  pop     r13
0x14006340b  pop     r12
0x14006340d  pop     rdi
0x14006340e  retn
0x140063410  mov     rax, [rsp+0A8h+arg_30]
0x140063418  mov     [rax], ecx
0x14006341a  mov     [rax+8], rcx
0x14006341e  mov     bl, 1
0x140063420  xor     sil, sil
0x140063423  xor     r15b, r15b
0x140063426  mov     r13d, ecx
0x140063429  jmp     loc_140063388
0x14006342e  bt      eax, 1Bh
0x140063432  jb      loc_140063280
0x140063438  cmp     qword ptr [r13+0], 1000h
0x140063440  jl      loc_140063280
0x140063446  xor     r8d, r8d; DisableWriteBehind
0x140063449  xor     edx, edx; DisableReadAhead
0x14006344b  mov     rcx, rsi; FileObject
0x14006344e  call    cs:__imp_CcSetAdditionalCacheAttributes
0x140063455  nop     dword ptr [rax+rax+00h]
0x14006345a  and     dword ptr [rdi+9Ch], 0FFFFFEFFh
0x140063464  jmp     loc_140063280
0x140063469  xor     bl, bl
0x14006346b  xor     sil, sil
0x14006346e  mov     r13d, 0E2h
0x140063474  movzx   r15d, [rsp+0A8h+arg_8]
0x14006347d  jmp     loc_140063388
0x140063482  mov     rcx, [r13+0]
0x140063486  cmp     rcx, rax
0x140063489  jge     short loc_1400634F9
0x14006348b  sub     eax, ecx
0x14006348d  mov     [rsp+0A8h+Length], eax
0x140063494  jmp     loc_140063255
0x140063499  xor     bl, bl
0x14006349b  xor     sil, sil
0x14006349e  mov     r13d, 0C2h
0x1400634a4  xor     r15b, r15b
0x1400634a7  jmp     loc_140063388
0x1400634ac  cmp     byte ptr [rsp+0A8h+arg_38], 0
0x1400634b4  jnz     loc_1400631AB
0x1400634ba  xor     bl, bl
0x1400634bc  xor     sil, sil
0x1400634bf  mov     r13d, 0F1h
0x1400634c5  movzx   r15d, [rsp+0A8h+arg_8]
0x1400634ce  jmp     loc_140063388
0x1400634d3  mov     rcx, rdi
0x1400634d6  call    RxReleaseRundownDerefView
0x1400634db  jmp     loc_14006339E
0x1400634e0  mov     r13d, 11Ah
0x1400634e6  movzx   esi, byte ptr [rsp+0A8h+arg_38]
0x1400634ee  movzx   r15d, sil
0x1400634f2  xor     bl, bl
0x1400634f4  jmp     loc_140063388
0x1400634f9  mov     rax, [rsp+0A8h+arg_30]
0x140063501  mov     dword ptr [rax], 0C0000011h
0x140063507  mov     qword ptr [rax+8], 0
0x14006350f  mov     bl, 1
0x140063511  mov     r13d, 157h
0x140063517  movzx   esi, bl
0x14006351a  movzx   r15d, bl
0x14006351e  jmp     loc_140063388
0x140063523  xor     edx, edx; Wait
0x140063525  call    cs:__imp_ExAcquireResourceSharedLite
0x14006352c  nop     dword ptr [rax+rax+00h]
0x140063531  test    al, al
0x140063533  jnz     loc_1400631C6
0x140063539  xor     bl, bl
0x14006353b  xor     sil, sil
0x14006353e  mov     r13d, 109h
0x140063544  movzx   r15d, [rsp+0A8h+arg_8]
0x14006354d  jmp     loc_140063388
0x140063552  xor     bl, bl
0x140063554  xor     sil, sil
0x140063557  mov     r13d, 0A2h
0x14006355d  xor     r15b, r15b
0x140063560  jmp     loc_140063388
0x140063565  xor     bl, bl
0x140063567  xor     sil, sil
0x14006356a  mov     r13d, 0B4h
0x140063570  xor     r15b, r15b
0x140063573  jmp     loc_140063388
0x140063578  mov     r13d, 147h
0x14006357e  jmp     loc_1400634E6
0x140063583  cmp     byte ptr [rcx+29h], 2
0x140063587  jb      loc_1400633EF
0x14006358d  mov     eax, 59h ; 'Y'
0x140063592  mov     r9d, 4Eh ; 'N'
0x140063598  test    bl, bl
0x14006359a  cmovnz  r9d, eax
0x14006359e  mov     dword ptr [rsp+0A8h+Buffer], r13d
0x1400635a3  mov     rcx, [rcx+18h]
0x1400635a7  call    WPP_SF_cd
0x1400635ac  jmp     loc_1400633EF
0x14007b020  push    rbp
0x14007b022  sub     rsp, 50h
0x14007b026  mov     rbp, rdx
0x14007b029  mov     rcx, [rcx]
0x14007b02c  mov     ecx, [rcx]; Exception
  ... truncated ...
```
