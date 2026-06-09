# NtfsMdlReadA

- ea: `0x1401bd3c0`
- end: `0x1401bd92c`
- name: `NtfsMdlReadA`
- size: `1388`
- prototype: `char __fastcall(PFILE_OBJECT FileObject, PLARGE_INTEGER FileOffset, ULONG Length, ULONG, PMDL *, PIO_STATUS_BLOCK IoStatus)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update`

## callees

- `0x140007ea0`
- `0x140008740`
- `0x140009af0`
- `0x140017030`
- `0x14001cd10`
- `0x1400290d0`
- `0x140059250`
- `0x1400596c0`
- `0x1401bd3c0`
- `0x1401be398`
- `0x1401be91c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401bd49c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401bd49c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401bd759`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401bd759`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401bd63d`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401bd721`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401bd63d`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401bd721`
- `ntoskrnl!FsRtlIncrementCcFastMdlReadWait` at `0x1401bd500`
- `ntoskrnl!FsRtlIncrementCcFastMdlReadWait` at `0x1401bd500`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401bd5d5`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401bd8f7`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401bd5d5`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401bd8f7`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bd576`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bd8c3`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bd576`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bd8c3`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402aeb82`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402aebac`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402aeb82`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402aebac`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401bd743`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401bd743`
- `ntoskrnl!CcMdlRead` at `0x1401bd66c`
- `ntoskrnl!CcMdlRead` at `0x1401bd7b7`
- `ntoskrnl!CcMdlRead` at `0x1401bd66c`
- `ntoskrnl!CcMdlRead` at `0x1401bd7b7`

## pseudocode

```c
char __fastcall NtfsMdlReadA(
        PFILE_OBJECT FileObject,
        PLARGE_INTEGER FileOffset,
        ULONG Length,
        ULONG a4,
        PMDL *a5,
        PIO_STATUS_BLOCK IoStatus)
{
  __int64 v6; // rbx
  ULONG_PTR TopLevelContext; // rax
  char v10; // di
  LONGLONG QuadPart; // r12
  __int64 v12; // rsi
  __int64 v13; // rax
  __int64 v14; // r14
  __int64 v15; // r8
  __int64 v16; // rax
  char v17; // r13
  LONGLONG v18; // rbx
  int *i; // rdx
  int *v20; // rax
  __int64 v21; // r12
  __int64 v22; // r9
  char v23; // r8
  int j; // ecx
  _DWORD *v25; // rdx
  LONGLONG v26; // rcx
  struct _FILE_OBJECT *v27; // r13
  char v28; // al
  PLARGE_INTEGER v29; // r12
  LONGLONG v30; // rax
  int v31; // ebx
  _WORD *v32; // rbx
  signed __int32 v34[8]; // [rsp+0h] [rbp-328h] BYREF
  bool v35; // [rsp+30h] [rbp-2F8h] BYREF
  char v36; // [rsp+31h] [rbp-2F7h]
  LONGLONG v37; // [rsp+38h] [rbp-2F0h]
  ULONG Lengtha; // [rsp+40h] [rbp-2E8h]
  _WORD *FsContext; // [rsp+48h] [rbp-2E0h]
  __int64 *v40; // [rsp+50h] [rbp-2D8h]
  ULONG v41; // [rsp+58h] [rbp-2D0h]
  PLARGE_INTEGER FileOffseta; // [rsp+60h] [rbp-2C8h]
  _BYTE *v43; // [rsp+68h] [rbp-2C0h] BYREF
  __int64 v44; // [rsp+70h] [rbp-2B8h]
  PFILE_OBJECT FileObjecta; // [rsp+78h] [rbp-2B0h]
  PMDL *MdlChain; // [rsp+80h] [rbp-2A8h]
  PVOID FsContext2; // [rsp+88h] [rbp-2A0h]
  _WORD *v48; // [rsp+90h] [rbp-298h]
  __int64 *v49; // [rsp+98h] [rbp-290h]
  _BYTE v50[560]; // [rsp+B0h] [rbp-278h] BYREF

  v41 = a4;
  v6 = Length;
  Lengtha = Length;
  FileOffseta = FileOffset;
  FileObjecta = FileObject;
  MdlChain = a5;
  v35 = 0;
  TopLevelContext = NtfsGetTopLevelContextEx(&v35);
  if ( !TopLevelContext || v35 && (*(_DWORD *)(*(_QWORD *)(TopLevelContext + 32) + 12LL) & 0x4000000) != 0 )
  {
    v10 = 1;
    if ( !(_DWORD)v6 )
    {
      IoStatus->Status = 0;
      IoStatus->Information = 0;
      return v10;
    }
    if ( TopLevelContext && v35 && (*(_DWORD *)(*(_QWORD *)(TopLevelContext + 32) + 12LL) & 0x4000000) != 0 )
    {
      CcMdlRead(FileObject, FileOffset, v6, a5, IoStatus);
      v36 = 1;
      return v10;
    }
    v35 = 0;
    memset(v50, 0, 0x228u);
    v43 = v50;
    QuadPart = FileOffset->QuadPart;
    FsContext = FileObject->FsContext;
    v12 = (__int64)FsContext;
    v48 = FsContext;
    FsContext2 = FileObject->FsContext2;
    KeEnterCriticalRegion();
    memset(v50, 0, 0x228u);
    NtfsInitializeIrpContextInternal(0, 1, 1, (__int64 *)&v43);
    v40 = (__int64 *)(v12 + 184);
    v13 = *(_QWORD *)(*(_QWORD *)(v12 + 184) + 96LL);
    v14 = (__int64)v43;
    *((_QWORD *)v43 + 13) = v13;
    if ( v13 && (*(_DWORD *)(v13 + 24) & 0x20000) != 0 )
      *(_QWORD *)(v14 + 16) |= 0x100000uLL;
    else
      *(_QWORD *)(v14 + 16) &= ~0x100000uLL;
    FsRtlIncrementCcFastMdlReadWait();
    if ( !*(_QWORD *)(v12 + 16) )
    {
      v10 = 0;
LABEL_34:
      NtfsCleanupIrpContext(v14, 0, v15);
      KeLeaveCriticalRegion();
      return v10;
    }
    v49 = v40;
    LOBYTE(v15) = 1;
    NtfsAcquirePagingShared(v14, v12, v15, 0);
    v16 = *(_QWORD *)(v12 + 528);
    if ( v16 && (*(_DWORD *)(*(_QWORD *)(v16 + 64) + 4LL) & 1) != 0
      || FileObject->SectionObjectPointer != (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v12 + 288) + 16LL) )
    {
      goto LABEL_43;
    }
    v17 = 0;
    v44 = v6;
    v18 = QuadPart + v6;
    if ( v18 <= *(_QWORD *)(v12 + 40) )
      goto LABEL_13;
    for ( i = (int *)(v12 + 160); ; i = v20 )
    {
      FsRtlAcquireHeaderMutex(v12 + 120, i);
      v17 = 1;
LABEL_13:
      v20 = (int *)(v12 + 160);
      v21 = v12 + 160;
      v22 = v12 + 120;
      if ( v17 )
      {
        v26 = *(_QWORD *)(v12 + 40);
      }
      else
      {
        v23 = 0;
        for ( j = *v20; ; j = 1 )
        {
          LODWORD(v37) = j;
          if ( (j & 1) != 0 )
          {
            FsRtlAcquireHeaderMutex(v22, v12 + 160);
            v23 = 1;
            j = v37;
            v22 = v12 + 120;
          }
          v37 = *(_QWORD *)(v12 + 40);
          v25 = (_DWORD *)(v12 + 160);
          if ( v23 )
            break;
          _InterlockedOr(v34, 0);
          if ( j == *v25 )
            goto LABEL_21;
        }
        FsRtlReleaseHeaderMutex(v22, v25);
LABEL_21:
        v26 = v37;
        v20 = (int *)(v12 + 160);
      }
      if ( v18 <= v26 )
        break;
      if ( v17 )
      {
        NtfsGetIoAtEof(v14, v12, FileOffseta->QuadPart, v44, 1, &v35);
        v21 = v12 + 160;
        break;
      }
    }
    if ( v17 )
      FsRtlReleaseHeaderMutex(v12 + 120, v21);
    v27 = FileObjecta;
    if ( !FileObjecta->PrivateCacheMap
      || (v28 = *(_BYTE *)(v12 + 5)) == 0
      || (v29 = FileOffseta, v28 == 2)
      && !NtfsFastIoCheckIfPossibleInternal(v14, FileObjecta, FileOffseta, Lengtha, v41, 1) )
    {
LABEL_43:
      v10 = 0;
LABEL_44:
      v32 = (_WORD *)v12;
      goto LABEL_31;
    }
    v30 = *(_QWORD *)(v12 + 32);
    if ( v18 > v30 )
    {
      if ( v29->QuadPart >= v30 )
      {
        IoStatus->Status = -1073741807;
        IoStatus->Information = 0;
        goto LABEL_44;
      }
      v31 = *(_DWORD *)(v12 + 32) - v29->LowPart;
    }
    else
    {
      v31 = Lengtha;
    }
    IoSetTopLevelIrp((PIRP)4);
    IoStatus->Status = 0;
    v36 = 0;
    CcMdlRead(v27, v29, v31, MdlChain, IoStatus);
    v36 = 1;
    NtfsUpdateFileTimestampsForAccess(v27, *v40, FsContext2);
    v32 = FsContext;
    IoSetTopLevelIrp(0);
LABEL_31:
    if ( *v32 != 1794 )
      v12 = *v40;
    ExReleaseResourceLite(*(PERESOURCE *)(v12 + 112));
    goto LABEL_34;
  }
  return 0;
}

```

## disassembly

```asm
0x1401bd3c0  push    rbx
0x1401bd3c2  push    rsi
0x1401bd3c3  push    rdi
0x1401bd3c4  push    r12
0x1401bd3c6  push    r13
0x1401bd3c8  push    r14
0x1401bd3ca  push    r15
0x1401bd3cc  sub     rsp, 2F0h
0x1401bd3d3  mov     rax, cs:__security_cookie
0x1401bd3da  xor     rax, rsp
0x1401bd3dd  mov     [rsp+328h+var_48], rax
0x1401bd3e5  mov     [rsp+328h+var_2D0], r9d
0x1401bd3ea  mov     ebx, r8d
0x1401bd3ed  mov     [rsp+328h+Length], ebx
0x1401bd3f1  mov     rsi, rdx
0x1401bd3f4  mov     [rsp+328h+FileOffset], rdx
0x1401bd3f9  mov     r13, rcx
0x1401bd3fc  mov     [rsp+328h+FileObject], rcx
0x1401bd401  mov     r15, [rsp+328h+arg_28]
0x1401bd409  mov     r14, [rsp+328h+arg_20]
0x1401bd411  mov     [rsp+328h+MdlChain], r14
0x1401bd419  xor     r12d, r12d
0x1401bd41c  mov     [rsp+328h+var_2F8], r12b
0x1401bd421  lea     rcx, [rsp+328h+var_2F8]
0x1401bd426  call    NtfsGetTopLevelContextEx
0x1401bd42b  mov     r8b, [rsp+328h+var_2F8]
0x1401bd430  test    rax, rax
0x1401bd433  jnz     loc_1401BD832
0x1401bd439  mov     edi, 1
0x1401bd43e  test    ebx, ebx
0x1401bd440  jz      loc_1401BD88D
0x1401bd446  test    rax, rax
0x1401bd449  jnz     loc_1401BD78C
0x1401bd44f  mov     [rsp+328h+var_2F8], r12b
0x1401bd454  mov     r14d, 228h
0x1401bd45a  mov     r8d, r14d; Size
0x1401bd45d  xor     edx, edx; Val
0x1401bd45f  lea     rcx, [rsp+328h+var_278]; void *
0x1401bd467  call    memset
0x1401bd46c  lea     rax, [rsp+328h+var_278]
0x1401bd474  mov     [rsp+328h+var_2C0], rax
0x1401bd479  mov     r12, [rsi]
0x1401bd47c  mov     rax, [r13+18h]
0x1401bd480  mov     [rsp+328h+var_2E0], rax
0x1401bd485  mov     rsi, rax
0x1401bd488  mov     [rsp+328h+var_298], rax
0x1401bd490  mov     rax, [r13+20h]
0x1401bd494  mov     [rsp+328h+var_2A0], rax
0x1401bd49c  call    cs:__imp_KeEnterCriticalRegion
0x1401bd4a3  nop     dword ptr [rax+rax+00h]
0x1401bd4a8  mov     r8d, r14d; Size
0x1401bd4ab  xor     edx, edx; Val
0x1401bd4ad  lea     rcx, [rsp+328h+var_278]; void *
0x1401bd4b5  call    memset
0x1401bd4ba  lea     r9, [rsp+328h+var_2C0]
0x1401bd4bf  mov     r8b, dil
0x1401bd4c2  mov     dl, dil
0x1401bd4c5  xor     ecx, ecx; Irp
0x1401bd4c7  call    NtfsInitializeIrpContextInternal
0x1401bd4cc  lea     rax, [rsi+0B8h]
0x1401bd4d3  mov     [rsp+328h+var_2D8], rax
0x1401bd4d8  mov     rax, [rax]
0x1401bd4db  mov     rax, [rax+60h]
0x1401bd4df  mov     r14, [rsp+328h+var_2C0]
0x1401bd4e4  mov     [r14+68h], rax
0x1401bd4e8  test    rax, rax
0x1401bd4eb  jz      short loc_1401BD4FA
0x1401bd4ed  test    dword ptr [rax+18h], 20000h
0x1401bd4f4  jnz     loc_1401BD8A1
0x1401bd4fa  btr     qword ptr [r14+10h], 14h
0x1401bd500  call    cs:__imp_FsRtlIncrementCcFastMdlReadWait
0x1401bd507  nop     dword ptr [rax+rax+00h]
0x1401bd50c  cmp     qword ptr [rsi+10h], 0
0x1401bd511  jz      loc_1401BD899
0x1401bd517  mov     rax, [rsp+328h+var_2D8]
0x1401bd51c  mov     [rsp+328h+var_290], rax
0x1401bd524  xor     r9d, r9d
0x1401bd527  mov     r8b, dil
0x1401bd52a  mov     rdx, rsi
0x1401bd52d  mov     rcx, r14
0x1401bd530  call    NtfsAcquirePagingShared
0x1401bd535  mov     rax, [rsi+210h]
0x1401bd53c  test    rax, rax
0x1401bd53f  jnz     loc_1401BD8AC
0x1401bd545  mov     rax, [rsi+120h]
0x1401bd54c  add     rax, 10h
0x1401bd550  cmp     [r13+28h], rax
0x1401bd554  jnz     loc_1401BD858
0x1401bd55a  xor     r13b, r13b
0x1401bd55d  mov     [rsp+328h+var_2B8], rbx
0x1401bd562  add     rbx, r12
0x1401bd565  cmp     rbx, [rsi+28h]
0x1401bd569  jle     short loc_1401BD585
0x1401bd56b  lea     rdx, [rsi+0A0h]
0x1401bd572  lea     rcx, [rsi+78h]
0x1401bd576  call    cs:__imp_FsRtlAcquireHeaderMutex
0x1401bd57d  nop     dword ptr [rax+rax+00h]
0x1401bd582  mov     r13b, dil
0x1401bd585  lea     rax, [rsi+0A0h]
0x1401bd58c  mov     r12, rax
0x1401bd58f  lea     r9, [rsi+78h]
0x1401bd593  test    r13b, r13b
0x1401bd596  jnz     loc_1401BD84F
0x1401bd59c  mov     r8b, r13b
0x1401bd59f  mov     ecx, [rax]
0x1401bd5a1  mov     dword ptr [rsp+328h+var_2F0], ecx
0x1401bd5a5  test    dil, cl
0x1401bd5a8  jnz     loc_1401BD8BD
0x1401bd5ae  mov     rax, [rsi+28h]
0x1401bd5b2  mov     [rsp+328h+var_2F0], rax
0x1401bd5b7  lea     rdx, [rsi+0A0h]
0x1401bd5be  test    r8b, r8b
0x1401bd5c1  jnz     short loc_1401BD5D2
0x1401bd5c3  lock or [rsp+328h+var_328], 0
0x1401bd5c8  mov     eax, [rdx]
0x1401bd5ca  cmp     ecx, eax
0x1401bd5cc  jz      short loc_1401BD5E1
0x1401bd5ce  mov     ecx, edi
0x1401bd5d0  jmp     short loc_1401BD5A1
0x1401bd5d2  mov     rcx, r9
0x1401bd5d5  call    cs:__imp_FsRtlReleaseHeaderMutex
0x1401bd5dc  nop     dword ptr [rax+rax+00h]
0x1401bd5e1  mov     rcx, [rsp+328h+var_2F0]
0x1401bd5e6  lea     rax, [rsi+0A0h]
0x1401bd5ed  cmp     rbx, rcx
0x1401bd5f0  jg      loc_1401BD8DF
0x1401bd5f6  test    r13b, r13b
0x1401bd5f9  jnz     loc_1401BD8F0
0x1401bd5ff  mov     r13, [rsp+328h+FileObject]
0x1401bd604  cmp     qword ptr [r13+30h], 0
0x1401bd609  jz      loc_1401BD858
0x1401bd60f  mov     al, [rsi+5]
0x1401bd612  test    al, al
0x1401bd614  jz      loc_1401BD858
0x1401bd61a  mov     r12, [rsp+328h+FileOffset]
0x1401bd61f  cmp     al, 2
0x1401bd621  jz      loc_1401BD863
0x1401bd627  mov     rax, [rsi+20h]
0x1401bd62b  cmp     rbx, rax
0x1401bd62e  jg      loc_1401BD908
0x1401bd634  mov     ebx, [rsp+328h+Length]
0x1401bd638  mov     ecx, 4; Irp
0x1401bd63d  call    cs:__imp_IoSetTopLevelIrp
0x1401bd644  nop     dword ptr [rax+rax+00h]
0x1401bd649  nop
0x1401bd64a  mov     dword ptr [r15], 0
0x1401bd651  mov     [rsp+328h+var_2F7], 0
0x1401bd656  mov     [rsp+328h+IoStatus], r15; IoStatus
0x1401bd65b  mov     r9, [rsp+328h+MdlChain]; MdlChain
0x1401bd663  mov     r8d, ebx; Length
0x1401bd666  mov     rdx, r12; FileOffset
0x1401bd669  mov     rcx, r13; FileObject
0x1401bd66c  call    cs:__imp_CcMdlRead
0x1401bd673  nop     dword ptr [rax+rax+00h]
0x1401bd678  mov     [rsp+328h+var_2F7], dil
0x1401bd67d  mov     r8, [rsp+328h+var_2A0]
0x1401bd685  mov     rax, [rsp+328h+var_2D8]
0x1401bd68a  mov     rdx, [rax]
0x1401bd68d  mov     rcx, r13
0x1401bd690  call    NtfsUpdateFileTimestampsForAccess
0x1401bd695  mov     rbx, [rsp+328h+var_2E0]
0x1401bd69a  jmp     loc_1401BD71F
0x1401bd69f  mov     edx, eax
0x1401bd6a1  mov     cl, cs:NtfsStatusDebugFlags
0x1401bd6a7  test    cl, cl
0x1401bd6a9  jz      short loc_1401BD6FA
0x1401bd6ab  test    eax, eax
0x1401bd6ad  jz      short loc_1401BD6FA
0x1401bd6af  cmp     eax, 126h
0x1401bd6b4  jz      short loc_1401BD6FA
0x1401bd6b6  lea     ecx, [rax-12Ah]
0x1401bd6bc  cmp     ecx, 1
0x1401bd6bf  jbe     short loc_1401BD6FA
0x1401bd6c1  cmp     eax, 0FFFFFFEDh
0x1401bd6c4  jnb     short loc_1401BD6FA
0x1401bd6c6  cmp     eax, 0C00000D8h
0x1401bd6cb  jz      short loc_1401BD6FA
0x1401bd6cd  cmp     eax, 0C0000016h
0x1401bd6d2  jz      short loc_1401BD6FA
0x1401bd6d4  cmp     eax, 0C0000011h
0x1401bd6d9  jz      short loc_1401BD6FA
0x1401bd6db  add     eax, 7FFFFFFBh
0x1401bd6e0  cmp     eax, 1
0x1401bd6e3  jbe     short loc_1401BD6FA
0x1401bd6e5  cmp     edx, 103h
0x1401bd6eb  jz      short loc_1401BD6FA
0x1401bd6ed  xor     ecx, ecx
0x1401bd6ef  mov     r8d, 3B0539h
0x1401bd6f5  call    NtfsStatusTraceAndDebugInternal
0x1401bd6fa  xor     dil, dil
0x1401bd6fd  mov     [rsp+328h+var_2F7], dil
0x1401bd702  mov     rsi, [rsp+328h+var_298]
0x1401bd70a  mov     r14, [rsp+328h+var_2C0]
0x1401bd70f  mov     rax, [rsp+328h+var_290]
0x1401bd717  mov     [rsp+328h+var_2D8], rax
0x1401bd71c  mov     rbx, rsi
0x1401bd71f  xor     ecx, ecx; Irp
0x1401bd721  call    cs:__imp_IoSetTopLevelIrp
0x1401bd728  nop     dword ptr [rax+rax+00h]
0x1401bd72d  mov     eax, 702h
0x1401bd732  cmp     ax, [rbx]
0x1401bd735  jz      short loc_1401BD73F
0x1401bd737  mov     rax, [rsp+328h+var_2D8]
0x1401bd73c  mov     rsi, [rax]
0x1401bd73f  mov     rcx, [rsi+70h]; Resource
0x1401bd743  call    cs:__imp_ExReleaseResourceLite
0x1401bd74a  nop     dword ptr [rax+rax+00h]
0x1401bd74f  xor     edx, edx
0x1401bd751  mov     rcx, r14
0x1401bd754  call    NtfsCleanupIrpContext
0x1401bd759  call    cs:__imp_KeLeaveCriticalRegion
0x1401bd760  nop     dword ptr [rax+rax+00h]
0x1401bd765  mov     al, dil
0x1401bd768  mov     rcx, [rsp+328h+var_48]
0x1401bd770  xor     rcx, rsp; StackCookie
0x1401bd773  call    __security_check_cookie
0x1401bd778  add     rsp, 2F0h
0x1401bd77f  pop     r15
0x1401bd781  pop     r14
0x1401bd783  pop     r13
0x1401bd785  pop     r12
0x1401bd787  pop     rdi
0x1401bd788  pop     rsi
0x1401bd789  pop     rbx
0x1401bd78a  retn
0x1401bd78c  test    r8b, r8b
0x1401bd78f  jz      loc_1401BD44F
0x1401bd795  mov     rax, [rax+20h]
0x1401bd799  test    dword ptr [rax+0Ch], 4000000h
0x1401bd7a0  jz      loc_1401BD44F
0x1401bd7a6  mov     [rsp+328h+IoStatus], r15; IoStatus
0x1401bd7ab  mov     r9, r14; MdlChain
0x1401bd7ae  mov     r8d, ebx; Length
0x1401bd7b1  mov     rdx, rsi; FileOffset
0x1401bd7b4  mov     rcx, r13; FileObject
0x1401bd7b7  call    cs:__imp_CcMdlRead
0x1401bd7be  nop     dword ptr [rax+rax+00h]
0x1401bd7c3  mov     [rsp+328h+var_2F7], dil
0x1401bd7c8  jmp     short loc_1401BD765
0x1401bd7ca  mov     edx, eax
0x1401bd7cc  mov     cl, cs:NtfsStatusDebugFlags
0x1401bd7d2  test    cl, cl
0x1401bd7d4  jz      short loc_1401BD825
0x1401bd7d6  test    eax, eax
0x1401bd7d8  jz      short loc_1401BD825
0x1401bd7da  cmp     eax, 126h
0x1401bd7df  jz      short loc_1401BD825
0x1401bd7e1  lea     ecx, [rax-12Ah]
0x1401bd7e7  cmp     ecx, 1
0x1401bd7ea  jbe     short loc_1401BD825
0x1401bd7ec  cmp     eax, 0FFFFFFEDh
0x1401bd7ef  jnb     short loc_1401BD825
0x1401bd7f1  cmp     eax, 0C00000D8h
0x1401bd7f6  jz      short loc_1401BD825
0x1401bd7f8  cmp     eax, 0C0000016h
0x1401bd7fd  jz      short loc_1401BD825
0x1401bd7ff  cmp     eax, 0C0000011h
0x1401bd804  jz      short loc_1401BD825
0x1401bd806  add     eax, 7FFFFFFBh
0x1401bd80b  cmp     eax, 1
0x1401bd80e  jbe     short loc_1401BD825
0x1401bd810  cmp     edx, 103h
0x1401bd816  jz      short loc_1401BD825
0x1401bd818  xor     ecx, ecx
0x1401bd81a  mov     r8d, 3B045Fh
0x1401bd820  call    NtfsStatusTraceAndDebugInternal
0x1401bd825  xor     dil, dil
0x1401bd828  mov     [rsp+328h+var_2F7], dil
0x1401bd82d  jmp     loc_1401BD765
0x1401bd832  test    r8b, r8b
0x1401bd835  jz      short loc_1401BD848
0x1401bd837  mov     rcx, [rax+20h]
0x1401bd83b  test    dword ptr [rcx+0Ch], 4000000h
0x1401bd842  jnz     loc_1401BD439
0x1401bd848  xor     al, al
0x1401bd84a  jmp     loc_1401BD768
0x1401bd84f  mov     rcx, [rsi+28h]
0x1401bd853  jmp     loc_1401BD5ED
0x1401bd858  xor     dil, dil
0x1401bd85b  mov     rbx, rsi
0x1401bd85e  jmp     loc_1401BD72D
0x1401bd863  mov     byte ptr [rsp+328h+var_300], dil
0x1401bd868  mov     eax, [rsp+328h+var_2D0]
0x1401bd86c  mov     dword ptr [rsp+328h+IoStatus], eax
0x1401bd870  mov     r9d, [rsp+328h+Length]
0x1401bd875  mov     r8, r12
0x1401bd878  mov     rdx, r13
0x1401bd87b  mov     rcx, r14
0x1401bd87e  call    NtfsFastIoCheckIfPossibleInternal
0x1401bd883  test    al, al
0x1401bd885  jnz     loc_1401BD627
0x1401bd88b  jmp     short loc_1401BD858
0x1401bd88d  mov     [r15], r12d
0x1401bd890  mov     [r15+8], r12
0x1401bd894  jmp     loc_1401BD765
0x1401bd899  xor     dil, dil
0x1401bd89c  jmp     loc_1401BD74F
0x1401bd8a1  bts     qword ptr [r14+10h], 14h
0x1401bd8a7  jmp     loc_1401BD500
0x1401bd8ac  mov     rax, [rax+40h]
  ... truncated ...
```
