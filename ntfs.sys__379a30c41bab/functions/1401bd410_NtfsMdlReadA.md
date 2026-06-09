# NtfsMdlReadA

- ea: `0x1401bd410`
- end: `0x1401bd97c`
- name: `NtfsMdlReadA`
- size: `1388`
- prototype: `__int64 __usercall@<rax>(PFILE_OBJECT FileObject@<rcx>, PLARGE_INTEGER FileOffset@<rdx>, ULONG Length@<r8d>, PMDL *, PIO_STATUS_BLOCK)`
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
- `0x1400592c0`
- `0x140059740`
- `0x1401bd410`
- `0x1401be3e8`
- `0x1401be96c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401bd4ec`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401bd4ec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401bd7a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401bd7a9`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401bd68d`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401bd771`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401bd68d`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401bd771`
- `ntoskrnl!FsRtlIncrementCcFastMdlReadWait` at `0x1401bd550`
- `ntoskrnl!FsRtlIncrementCcFastMdlReadWait` at `0x1401bd550`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401bd625`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401bd947`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401bd625`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401bd947`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bd5c6`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bd913`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bd5c6`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bd913`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402aebd2`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402aebfc`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402aebd2`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402aebfc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401bd793`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401bd793`
- `ntoskrnl!CcMdlRead` at `0x1401bd6bc`
- `ntoskrnl!CcMdlRead` at `0x1401bd807`
- `ntoskrnl!CcMdlRead` at `0x1401bd6bc`
- `ntoskrnl!CcMdlRead` at `0x1401bd807`

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
  __int64 TopLevelContext; // rax
  char v10; // di
  LONGLONG QuadPart; // r12
  _WORD *v12; // rsi
  __int64 v13; // rax
  __int64 v14; // r14
  __int64 v15; // r8
  __int64 v16; // r8
  __int64 v17; // rax
  char v18; // r13
  LONGLONG v19; // rbx
  int *i; // rdx
  int *v21; // rax
  _WORD *v22; // r12
  _WORD *v23; // r9
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
  char v35; // [rsp+30h] [rbp-2F8h] BYREF
  char v36; // [rsp+31h] [rbp-2F7h]
  LONGLONG v37; // [rsp+38h] [rbp-2F0h]
  ULONG Lengtha; // [rsp+40h] [rbp-2E8h]
  _WORD *FsContext; // [rsp+48h] [rbp-2E0h]
  _QWORD *v40; // [rsp+50h] [rbp-2D8h]
  ULONG v41; // [rsp+58h] [rbp-2D0h]
  PLARGE_INTEGER FileOffseta; // [rsp+60h] [rbp-2C8h]
  _BYTE *v43; // [rsp+68h] [rbp-2C0h] BYREF
  __int64 v44; // [rsp+70h] [rbp-2B8h]
  PFILE_OBJECT FileObjecta; // [rsp+78h] [rbp-2B0h]
  PMDL *MdlChain; // [rsp+80h] [rbp-2A8h]
  PVOID FsContext2; // [rsp+88h] [rbp-2A0h]
  _WORD *v48; // [rsp+90h] [rbp-298h]
  _QWORD *v49; // [rsp+98h] [rbp-290h]
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
    v12 = FsContext;
    v48 = FsContext;
    FsContext2 = FileObject->FsContext2;
    KeEnterCriticalRegion();
    memset(v50, 0, 0x228u);
    NtfsInitializeIrpContextInternal(0, 1, 1, (__int64 *)&v43);
    v40 = v12 + 92;
    v13 = *(_QWORD *)(*((_QWORD *)v12 + 23) + 96LL);
    v14 = (__int64)v43;
    *((_QWORD *)v43 + 13) = v13;
    if ( v13 && (*(_DWORD *)(v13 + 24) & 0x20000) != 0 )
      *(_QWORD *)(v14 + 16) |= 0x100000uLL;
    else
      *(_QWORD *)(v14 + 16) &= ~0x100000uLL;
    FsRtlIncrementCcFastMdlReadWait();
    if ( !*((_QWORD *)v12 + 2) )
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
    v17 = *((_QWORD *)v12 + 66);
    if ( v17 && (*(_DWORD *)(*(_QWORD *)(v17 + 64) + 4LL) & 1) != 0
      || FileObject->SectionObjectPointer != (PSECTION_OBJECT_POINTERS)(*((_QWORD *)v12 + 36) + 16LL) )
    {
      goto LABEL_43;
    }
    v18 = 0;
    v44 = v6;
    v19 = QuadPart + v6;
    if ( v19 <= *((_QWORD *)v12 + 5) )
      goto LABEL_13;
    for ( i = (int *)(v12 + 80); ; i = v21 )
    {
      FsRtlAcquireHeaderMutex(v12 + 60, i, v16);
      v18 = 1;
LABEL_13:
      v21 = (int *)(v12 + 80);
      v22 = v12 + 80;
      v23 = v12 + 60;
      if ( v18 )
      {
        v26 = *((_QWORD *)v12 + 5);
      }
      else
      {
        LOBYTE(v16) = 0;
        for ( j = *v21; ; j = 1 )
        {
          LODWORD(v37) = j;
          if ( (j & 1) != 0 )
          {
            FsRtlAcquireHeaderMutex(v23, v12 + 80, v16);
            LOBYTE(v16) = 1;
            j = v37;
            v23 = v12 + 60;
          }
          v37 = *((_QWORD *)v12 + 5);
          v25 = v12 + 80;
          if ( (_BYTE)v16 )
            break;
          _InterlockedOr(v34, 0);
          if ( j == *v25 )
            goto LABEL_21;
        }
        FsRtlReleaseHeaderMutex(v23, v25);
LABEL_21:
        v26 = v37;
        v21 = (int *)(v12 + 80);
      }
      if ( v19 <= v26 )
        break;
      if ( v18 )
      {
        NtfsGetIoAtEof(v14, (_DWORD)v12, FileOffseta->QuadPart, v44, 1, (__int64)&v35);
        v22 = v12 + 80;
        break;
      }
    }
    if ( v18 )
      FsRtlReleaseHeaderMutex(v12 + 60, v22);
    v27 = FileObjecta;
    if ( !FileObjecta->PrivateCacheMap
      || (v28 = *((_BYTE *)v12 + 5)) == 0
      || (v29 = FileOffseta, v28 == 2) && !(unsigned __int8)NtfsFastIoCheckIfPossibleInternal(v14, FileObjecta, v41, 1) )
    {
LABEL_43:
      v10 = 0;
LABEL_44:
      v32 = v12;
      goto LABEL_31;
    }
    v30 = *((_QWORD *)v12 + 4);
    if ( v19 > v30 )
    {
      if ( v29->QuadPart >= v30 )
      {
        IoStatus->Status = -1073741807;
        IoStatus->Information = 0;
        goto LABEL_44;
      }
      v31 = *((_DWORD *)v12 + 8) - v29->LowPart;
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
      v12 = (_WORD *)*v40;
    ExReleaseResourceLite(*((PERESOURCE *)v12 + 14));
    goto LABEL_34;
  }
  return 0;
}

```

## disassembly

```asm
0x1401bd410  push    rbx
0x1401bd412  push    rsi
0x1401bd413  push    rdi
0x1401bd414  push    r12
0x1401bd416  push    r13
0x1401bd418  push    r14
0x1401bd41a  push    r15
0x1401bd41c  sub     rsp, 2F0h
0x1401bd423  mov     rax, cs:__security_cookie
0x1401bd42a  xor     rax, rsp
0x1401bd42d  mov     [rsp+328h+var_48], rax
0x1401bd435  mov     [rsp+328h+var_2D0], r9d
0x1401bd43a  mov     ebx, r8d
0x1401bd43d  mov     [rsp+328h+Length], ebx
0x1401bd441  mov     rsi, rdx
0x1401bd444  mov     [rsp+328h+FileOffset], rdx
0x1401bd449  mov     r13, rcx
0x1401bd44c  mov     [rsp+328h+FileObject], rcx
0x1401bd451  mov     r15, [rsp+328h+arg_28]
0x1401bd459  mov     r14, [rsp+328h+arg_20]
0x1401bd461  mov     [rsp+328h+MdlChain], r14
0x1401bd469  xor     r12d, r12d
0x1401bd46c  mov     [rsp+328h+var_2F8], r12b
0x1401bd471  lea     rcx, [rsp+328h+var_2F8]
0x1401bd476  call    NtfsGetTopLevelContextEx
0x1401bd47b  mov     r8b, [rsp+328h+var_2F8]
0x1401bd480  test    rax, rax
0x1401bd483  jnz     loc_1401BD882
0x1401bd489  mov     edi, 1
0x1401bd48e  test    ebx, ebx
0x1401bd490  jz      loc_1401BD8DD
0x1401bd496  test    rax, rax
0x1401bd499  jnz     loc_1401BD7DC
0x1401bd49f  mov     [rsp+328h+var_2F8], r12b
0x1401bd4a4  mov     r14d, 228h
0x1401bd4aa  mov     r8d, r14d; Size
0x1401bd4ad  xor     edx, edx; Val
0x1401bd4af  lea     rcx, [rsp+328h+var_278]; void *
0x1401bd4b7  call    memset
0x1401bd4bc  lea     rax, [rsp+328h+var_278]
0x1401bd4c4  mov     [rsp+328h+var_2C0], rax
0x1401bd4c9  mov     r12, [rsi]
0x1401bd4cc  mov     rax, [r13+18h]
0x1401bd4d0  mov     [rsp+328h+var_2E0], rax
0x1401bd4d5  mov     rsi, rax
0x1401bd4d8  mov     [rsp+328h+var_298], rax
0x1401bd4e0  mov     rax, [r13+20h]
0x1401bd4e4  mov     [rsp+328h+var_2A0], rax
0x1401bd4ec  call    cs:__imp_KeEnterCriticalRegion
0x1401bd4f3  nop     dword ptr [rax+rax+00h]
0x1401bd4f8  mov     r8d, r14d; Size
0x1401bd4fb  xor     edx, edx; Val
0x1401bd4fd  lea     rcx, [rsp+328h+var_278]; void *
0x1401bd505  call    memset
0x1401bd50a  lea     r9, [rsp+328h+var_2C0]
0x1401bd50f  mov     r8b, dil
0x1401bd512  mov     dl, dil
0x1401bd515  xor     ecx, ecx; Irp
0x1401bd517  call    NtfsInitializeIrpContextInternal
0x1401bd51c  lea     rax, [rsi+0B8h]
0x1401bd523  mov     [rsp+328h+var_2D8], rax
0x1401bd528  mov     rax, [rax]
0x1401bd52b  mov     rax, [rax+60h]
0x1401bd52f  mov     r14, [rsp+328h+var_2C0]
0x1401bd534  mov     [r14+68h], rax
0x1401bd538  test    rax, rax
0x1401bd53b  jz      short loc_1401BD54A
0x1401bd53d  test    dword ptr [rax+18h], 20000h
0x1401bd544  jnz     loc_1401BD8F1
0x1401bd54a  btr     qword ptr [r14+10h], 14h
0x1401bd550  call    cs:__imp_FsRtlIncrementCcFastMdlReadWait
0x1401bd557  nop     dword ptr [rax+rax+00h]
0x1401bd55c  cmp     qword ptr [rsi+10h], 0
0x1401bd561  jz      loc_1401BD8E9
0x1401bd567  mov     rax, [rsp+328h+var_2D8]
0x1401bd56c  mov     [rsp+328h+var_290], rax
0x1401bd574  xor     r9d, r9d
0x1401bd577  mov     r8b, dil
0x1401bd57a  mov     rdx, rsi
0x1401bd57d  mov     rcx, r14
0x1401bd580  call    NtfsAcquirePagingShared
0x1401bd585  mov     rax, [rsi+210h]
0x1401bd58c  test    rax, rax
0x1401bd58f  jnz     loc_1401BD8FC
0x1401bd595  mov     rax, [rsi+120h]
0x1401bd59c  add     rax, 10h
0x1401bd5a0  cmp     [r13+28h], rax
0x1401bd5a4  jnz     loc_1401BD8A8
0x1401bd5aa  xor     r13b, r13b
0x1401bd5ad  mov     [rsp+328h+var_2B8], rbx
0x1401bd5b2  add     rbx, r12
0x1401bd5b5  cmp     rbx, [rsi+28h]
0x1401bd5b9  jle     short loc_1401BD5D5
0x1401bd5bb  lea     rdx, [rsi+0A0h]
0x1401bd5c2  lea     rcx, [rsi+78h]
0x1401bd5c6  call    cs:__imp_FsRtlAcquireHeaderMutex
0x1401bd5cd  nop     dword ptr [rax+rax+00h]
0x1401bd5d2  mov     r13b, dil
0x1401bd5d5  lea     rax, [rsi+0A0h]
0x1401bd5dc  mov     r12, rax
0x1401bd5df  lea     r9, [rsi+78h]
0x1401bd5e3  test    r13b, r13b
0x1401bd5e6  jnz     loc_1401BD89F
0x1401bd5ec  mov     r8b, r13b
0x1401bd5ef  mov     ecx, [rax]
0x1401bd5f1  mov     dword ptr [rsp+328h+var_2F0], ecx
0x1401bd5f5  test    dil, cl
0x1401bd5f8  jnz     loc_1401BD90D
0x1401bd5fe  mov     rax, [rsi+28h]
0x1401bd602  mov     [rsp+328h+var_2F0], rax
0x1401bd607  lea     rdx, [rsi+0A0h]
0x1401bd60e  test    r8b, r8b
0x1401bd611  jnz     short loc_1401BD622
0x1401bd613  lock or [rsp+328h+var_328], 0
0x1401bd618  mov     eax, [rdx]
0x1401bd61a  cmp     ecx, eax
0x1401bd61c  jz      short loc_1401BD631
0x1401bd61e  mov     ecx, edi
0x1401bd620  jmp     short loc_1401BD5F1
0x1401bd622  mov     rcx, r9
0x1401bd625  call    cs:__imp_FsRtlReleaseHeaderMutex
0x1401bd62c  nop     dword ptr [rax+rax+00h]
0x1401bd631  mov     rcx, [rsp+328h+var_2F0]
0x1401bd636  lea     rax, [rsi+0A0h]
0x1401bd63d  cmp     rbx, rcx
0x1401bd640  jg      loc_1401BD92F
0x1401bd646  test    r13b, r13b
0x1401bd649  jnz     loc_1401BD940
0x1401bd64f  mov     r13, [rsp+328h+FileObject]
0x1401bd654  cmp     qword ptr [r13+30h], 0
0x1401bd659  jz      loc_1401BD8A8
0x1401bd65f  mov     al, [rsi+5]
0x1401bd662  test    al, al
0x1401bd664  jz      loc_1401BD8A8
0x1401bd66a  mov     r12, [rsp+328h+FileOffset]
0x1401bd66f  cmp     al, 2
0x1401bd671  jz      loc_1401BD8B3
0x1401bd677  mov     rax, [rsi+20h]
0x1401bd67b  cmp     rbx, rax
0x1401bd67e  jg      loc_1401BD958
0x1401bd684  mov     ebx, [rsp+328h+Length]
0x1401bd688  mov     ecx, 4; Irp
0x1401bd68d  call    cs:__imp_IoSetTopLevelIrp
0x1401bd694  nop     dword ptr [rax+rax+00h]
0x1401bd699  nop
0x1401bd69a  mov     dword ptr [r15], 0
0x1401bd6a1  mov     [rsp+328h+var_2F7], 0
0x1401bd6a6  mov     [rsp+328h+IoStatus], r15; IoStatus
0x1401bd6ab  mov     r9, [rsp+328h+MdlChain]; MdlChain
0x1401bd6b3  mov     r8d, ebx; Length
0x1401bd6b6  mov     rdx, r12; FileOffset
0x1401bd6b9  mov     rcx, r13; FileObject
0x1401bd6bc  call    cs:__imp_CcMdlRead
0x1401bd6c3  nop     dword ptr [rax+rax+00h]
0x1401bd6c8  mov     [rsp+328h+var_2F7], dil
0x1401bd6cd  mov     r8, [rsp+328h+var_2A0]
0x1401bd6d5  mov     rax, [rsp+328h+var_2D8]
0x1401bd6da  mov     rdx, [rax]
0x1401bd6dd  mov     rcx, r13
0x1401bd6e0  call    NtfsUpdateFileTimestampsForAccess
0x1401bd6e5  mov     rbx, [rsp+328h+var_2E0]
0x1401bd6ea  jmp     loc_1401BD76F
0x1401bd6ef  mov     edx, eax
0x1401bd6f1  mov     cl, cs:NtfsStatusDebugFlags
0x1401bd6f7  test    cl, cl
0x1401bd6f9  jz      short loc_1401BD74A
0x1401bd6fb  test    eax, eax
0x1401bd6fd  jz      short loc_1401BD74A
0x1401bd6ff  cmp     eax, 126h
0x1401bd704  jz      short loc_1401BD74A
0x1401bd706  lea     ecx, [rax-12Ah]
0x1401bd70c  cmp     ecx, 1
0x1401bd70f  jbe     short loc_1401BD74A
0x1401bd711  cmp     eax, 0FFFFFFEDh
0x1401bd714  jnb     short loc_1401BD74A
0x1401bd716  cmp     eax, 0C00000D8h
0x1401bd71b  jz      short loc_1401BD74A
0x1401bd71d  cmp     eax, 0C0000016h
0x1401bd722  jz      short loc_1401BD74A
0x1401bd724  cmp     eax, 0C0000011h
0x1401bd729  jz      short loc_1401BD74A
0x1401bd72b  add     eax, 7FFFFFFBh
0x1401bd730  cmp     eax, 1
0x1401bd733  jbe     short loc_1401BD74A
0x1401bd735  cmp     edx, 103h
0x1401bd73b  jz      short loc_1401BD74A
0x1401bd73d  xor     ecx, ecx
0x1401bd73f  mov     r8d, 3B0539h
0x1401bd745  call    NtfsStatusTraceAndDebugInternal
0x1401bd74a  xor     dil, dil
0x1401bd74d  mov     [rsp+328h+var_2F7], dil
0x1401bd752  mov     rsi, [rsp+328h+var_298]
0x1401bd75a  mov     r14, [rsp+328h+var_2C0]
0x1401bd75f  mov     rax, [rsp+328h+var_290]
0x1401bd767  mov     [rsp+328h+var_2D8], rax
0x1401bd76c  mov     rbx, rsi
0x1401bd76f  xor     ecx, ecx; Irp
0x1401bd771  call    cs:__imp_IoSetTopLevelIrp
0x1401bd778  nop     dword ptr [rax+rax+00h]
0x1401bd77d  mov     eax, 702h
0x1401bd782  cmp     ax, [rbx]
0x1401bd785  jz      short loc_1401BD78F
0x1401bd787  mov     rax, [rsp+328h+var_2D8]
0x1401bd78c  mov     rsi, [rax]
0x1401bd78f  mov     rcx, [rsi+70h]; Resource
0x1401bd793  call    cs:__imp_ExReleaseResourceLite
0x1401bd79a  nop     dword ptr [rax+rax+00h]
0x1401bd79f  xor     edx, edx
0x1401bd7a1  mov     rcx, r14
0x1401bd7a4  call    NtfsCleanupIrpContext
0x1401bd7a9  call    cs:__imp_KeLeaveCriticalRegion
0x1401bd7b0  nop     dword ptr [rax+rax+00h]
0x1401bd7b5  mov     al, dil
0x1401bd7b8  mov     rcx, [rsp+328h+var_48]
0x1401bd7c0  xor     rcx, rsp; StackCookie
0x1401bd7c3  call    __security_check_cookie
0x1401bd7c8  add     rsp, 2F0h
0x1401bd7cf  pop     r15
0x1401bd7d1  pop     r14
0x1401bd7d3  pop     r13
0x1401bd7d5  pop     r12
0x1401bd7d7  pop     rdi
0x1401bd7d8  pop     rsi
0x1401bd7d9  pop     rbx
0x1401bd7da  retn
0x1401bd7dc  test    r8b, r8b
0x1401bd7df  jz      loc_1401BD49F
0x1401bd7e5  mov     rax, [rax+20h]
0x1401bd7e9  test    dword ptr [rax+0Ch], 4000000h
0x1401bd7f0  jz      loc_1401BD49F
0x1401bd7f6  mov     [rsp+328h+IoStatus], r15; IoStatus
0x1401bd7fb  mov     r9, r14; MdlChain
0x1401bd7fe  mov     r8d, ebx; Length
0x1401bd801  mov     rdx, rsi; FileOffset
0x1401bd804  mov     rcx, r13; FileObject
0x1401bd807  call    cs:__imp_CcMdlRead
0x1401bd80e  nop     dword ptr [rax+rax+00h]
0x1401bd813  mov     [rsp+328h+var_2F7], dil
0x1401bd818  jmp     short loc_1401BD7B5
0x1401bd81a  mov     edx, eax
0x1401bd81c  mov     cl, cs:NtfsStatusDebugFlags
0x1401bd822  test    cl, cl
0x1401bd824  jz      short loc_1401BD875
0x1401bd826  test    eax, eax
0x1401bd828  jz      short loc_1401BD875
0x1401bd82a  cmp     eax, 126h
0x1401bd82f  jz      short loc_1401BD875
0x1401bd831  lea     ecx, [rax-12Ah]
0x1401bd837  cmp     ecx, 1
0x1401bd83a  jbe     short loc_1401BD875
0x1401bd83c  cmp     eax, 0FFFFFFEDh
0x1401bd83f  jnb     short loc_1401BD875
0x1401bd841  cmp     eax, 0C00000D8h
0x1401bd846  jz      short loc_1401BD875
0x1401bd848  cmp     eax, 0C0000016h
0x1401bd84d  jz      short loc_1401BD875
0x1401bd84f  cmp     eax, 0C0000011h
0x1401bd854  jz      short loc_1401BD875
0x1401bd856  add     eax, 7FFFFFFBh
0x1401bd85b  cmp     eax, 1
0x1401bd85e  jbe     short loc_1401BD875
0x1401bd860  cmp     edx, 103h
0x1401bd866  jz      short loc_1401BD875
0x1401bd868  xor     ecx, ecx
0x1401bd86a  mov     r8d, 3B045Fh
0x1401bd870  call    NtfsStatusTraceAndDebugInternal
0x1401bd875  xor     dil, dil
0x1401bd878  mov     [rsp+328h+var_2F7], dil
0x1401bd87d  jmp     loc_1401BD7B5
0x1401bd882  test    r8b, r8b
0x1401bd885  jz      short loc_1401BD898
0x1401bd887  mov     rcx, [rax+20h]
0x1401bd88b  test    dword ptr [rcx+0Ch], 4000000h
0x1401bd892  jnz     loc_1401BD489
0x1401bd898  xor     al, al
0x1401bd89a  jmp     loc_1401BD7B8
0x1401bd89f  mov     rcx, [rsi+28h]
0x1401bd8a3  jmp     loc_1401BD63D
0x1401bd8a8  xor     dil, dil
0x1401bd8ab  mov     rbx, rsi
0x1401bd8ae  jmp     loc_1401BD77D
0x1401bd8b3  mov     byte ptr [rsp+328h+var_300], dil
0x1401bd8b8  mov     eax, [rsp+328h+var_2D0]
0x1401bd8bc  mov     dword ptr [rsp+328h+IoStatus], eax
0x1401bd8c0  mov     r9d, [rsp+328h+Length]
0x1401bd8c5  mov     r8, r12
0x1401bd8c8  mov     rdx, r13
0x1401bd8cb  mov     rcx, r14
0x1401bd8ce  call    NtfsFastIoCheckIfPossibleInternal
0x1401bd8d3  test    al, al
0x1401bd8d5  jnz     loc_1401BD677
0x1401bd8db  jmp     short loc_1401BD8A8
0x1401bd8dd  mov     [r15], r12d
0x1401bd8e0  mov     [r15+8], r12
0x1401bd8e4  jmp     loc_1401BD7B5
0x1401bd8e9  xor     dil, dil
0x1401bd8ec  jmp     loc_1401BD79F
0x1401bd8f1  bts     qword ptr [r14+10h], 14h
0x1401bd8f7  jmp     loc_1401BD550
0x1401bd8fc  mov     rax, [rax+40h]
  ... truncated ...
```
