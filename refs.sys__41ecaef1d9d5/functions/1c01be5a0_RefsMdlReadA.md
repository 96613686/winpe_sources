# RefsMdlReadA

- ea: `0x1c01be5a0`
- end: `0x1c01be921`
- name: `RefsMdlReadA`
- size: `897`
- prototype: `__int64 __usercall@<rax>(PFILE_OBJECT FileObject@<rcx>, __int64, PIO_STATUS_BLOCK)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x1c0005768`
- `0x1c000f480`
- `0x1c000f770`
- `0x1c0014110`
- `0x1c005c580`
- `0x1c005c650`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c006af80`
- `0x1c00a0534`
- `0x1c01be5a0`
- `0x1c01c1b80`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c01be8a6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01be8a6`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01be6f1`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01be6f1`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01be739`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01be739`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c01be905`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c01be905`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c01be5ff`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c01be5ff`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c01be81e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c01be86f`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c01be81e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c01be86f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c01be654`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c01be654`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c01be8be`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c01be8be`
- `ntoskrnl!CcMdlRead` at `0x1c01be847`
- `ntoskrnl!CcMdlRead` at `0x1c01be847`
- `ntoskrnl!FsRtlIncrementCcFastMdlReadWait` at `0x1c01be694`
- `ntoskrnl!FsRtlIncrementCcFastMdlReadWait` at `0x1c01be694`

## pseudocode

```c
char __fastcall RefsMdlReadA(
        PFILE_OBJECT FileObject,
        union _LARGE_INTEGER *a2,
        unsigned int a3,
        int a4,
        PMDL *a5,
        PIO_STATUS_BLOCK IoStatus)
{
  __int64 v6; // r12
  char v9; // r14
  LONGLONG v11; // rbx
  PVOID v12; // rsi
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  LONGLONG v20; // rax
  bool v21; // cc
  union _LARGE_INTEGER *v22; // rbx
  _BYTE v23[7]; // [rsp+31h] [rbp-167h] BYREF
  _BYTE *v24; // [rsp+38h] [rbp-160h] BYREF
  PLARGE_INTEGER FileOffset; // [rsp+40h] [rbp-158h]
  int v26; // [rsp+48h] [rbp-150h]
  PMDL *MdlChain; // [rsp+50h] [rbp-148h]
  PVOID FsContext; // [rsp+58h] [rbp-140h]
  _BYTE v29[256]; // [rsp+60h] [rbp-138h] BYREF

  v26 = a4;
  v6 = a3;
  FileOffset = a2;
  MdlChain = a5;
  v23[0] = 0;
  v9 = 1;
  if ( IoGetTopLevelIrp() )
    return 0;
  if ( (_DWORD)v6 )
  {
    memset(v29, 0, sizeof(v29));
    v24 = v29;
    v11 = a2->QuadPart + v6;
    FsContext = FileObject->FsContext;
    v12 = FsContext;
    KeEnterCriticalRegion();
    LOBYTE(v13) = 1;
    LOBYTE(v14) = 1;
    RefsInitializeIrpContext(0, v14, v13, &v24);
    v15 = *(_QWORD *)(*((_QWORD *)v12 + 15) + 88LL);
    *((_QWORD *)v24 + 8) = v15;
    if ( *(_DWORD *)(v15 + 468) || (FsRtlIncrementCcFastMdlReadWait(), !*((_QWORD *)v12 + 2)) )
    {
      v9 = 0;
LABEL_34:
      RefsCleanupIrpContext(v24, 0);
      KeLeaveCriticalRegion();
      return v9;
    }
    LOBYTE(v17) = 1;
    RefsAcquirePagingResourceShared(v16, v12, v17);
    if ( !FileObject->PrivateCacheMap
      || !*((_BYTE *)v12 + 5)
      || FileObject->SectionObjectPointer != (PSECTION_OBJECT_POINTERS)(*((_QWORD *)v12 + 30) + 8LL)
      || !(unsigned __int8)RefsIsFileOpen(*((_QWORD *)v12 + 15), v18, v19) )
    {
      v9 = 0;
LABEL_31:
      if ( *(_WORD *)v12 != 2050 )
        v12 = (PVOID)*((_QWORD *)v12 + 15);
      ExReleaseResourceLite(*((PERESOURCE *)v12 + 13));
      goto LABEL_34;
    }
    ExAcquireFastMutex(*((PFAST_MUTEX *)v12 + 6));
    _InterlockedAdd((volatile signed __int32 *)v12 + 39, 1u);
    if ( v11 > *((_QWORD *)v12 + 4) )
      RefsGetIoAtEof((_DWORD)v24, (_DWORD)v12, FileOffset->QuadPart, v6, (__int64)v23);
    _InterlockedAdd((volatile signed __int32 *)v12 + 39, 1u);
    ExReleaseFastMutex(*((PFAST_MUTEX *)v12 + 6));
    if ( *((_BYTE *)v12 + 5) != 2
      || (unsigned __int8)RefsFastIoCheckIfPossibleInternal(v24, FileObject, FileOffset, (unsigned int)v6, v26, 1) )
    {
      v20 = *((_QWORD *)v12 + 4);
      v21 = v11 <= v20;
      v22 = FileOffset;
      if ( !v21 )
      {
        if ( FileOffset->QuadPart >= v20 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              11,
              WPP_93e8087fdfc930c957e27c1f01eb03c6_Traceguids,
              3221225489LL);
          }
          if ( RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741807);
          IoStatus->Status = -1073741807;
          IoStatus->Information = 0;
          v9 = 1;
          goto LABEL_28;
        }
        LODWORD(v6) = v20 - FileOffset->LowPart;
        RefsReleaseEofLock(v24, v12);
        v23[0] = 0;
      }
      IoSetTopLevelIrp((PIRP)4);
      IoStatus->Status = 0;
      CcMdlRead(FileObject, v22, v6, MdlChain, IoStatus);
      FileObject->Flags |= 0x80000u;
      IoSetTopLevelIrp(0);
    }
    else
    {
      v9 = 0;
    }
LABEL_28:
    if ( v23[0] )
      RefsReleaseEofLock(v24, v12);
    goto LABEL_31;
  }
  IoStatus->Status = 0;
  IoStatus->Information = 0;
  return v9;
}

```

## disassembly

```asm
0x1c01be5a0  mov     [rsp+arg_18], rbx
0x1c01be5a5  push    rsi
0x1c01be5a6  push    r12
0x1c01be5a8  push    r13
0x1c01be5aa  push    r14
0x1c01be5ac  push    r15
0x1c01be5ae  sub     rsp, 170h
0x1c01be5b5  mov     rax, cs:__security_cookie
0x1c01be5bc  xor     rax, rsp
0x1c01be5bf  mov     [rsp+198h+var_38], rax
0x1c01be5c7  mov     [rsp+198h+var_150], r9d
0x1c01be5cc  mov     r12d, r8d
0x1c01be5cf  mov     rsi, rdx
0x1c01be5d2  mov     [rsp+198h+FileOffset], rdx
0x1c01be5d7  mov     r13, rcx
0x1c01be5da  mov     rax, [rsp+198h+arg_20]
0x1c01be5e2  mov     [rsp+198h+MdlChain], rax
0x1c01be5e7  mov     r15, [rsp+198h+arg_28]
0x1c01be5ef  mov     [rsp+198h+var_167], 0
0x1c01be5f4  mov     r14d, 1
0x1c01be5fa  mov     [rsp+198h+var_168], r14b
0x1c01be5ff  call    cs:__imp_IoGetTopLevelIrp
0x1c01be606  nop     dword ptr [rax+rax+00h]
0x1c01be60b  test    rax, rax
0x1c01be60e  jz      short loc_1C01BE617
0x1c01be610  xor     al, al
0x1c01be612  jmp     loc_1C01BE8CD
0x1c01be617  test    r12d, r12d
0x1c01be61a  jnz     short loc_1C01BE629
0x1c01be61c  and     [r15], r12d
0x1c01be61f  and     qword ptr [r15+8], 0
0x1c01be624  jmp     loc_1C01BE8CA
0x1c01be629  xor     edx, edx; Val
0x1c01be62b  mov     r8d, 100h; Size
0x1c01be631  lea     rcx, [rsp+198h+var_138]; void *
0x1c01be636  call    memset
0x1c01be63b  lea     rax, [rsp+198h+var_138]
0x1c01be640  mov     [rsp+198h+var_160], rax
0x1c01be645  mov     rbx, r12
0x1c01be648  add     rbx, [rsi]
0x1c01be64b  mov     rsi, [r13+18h]
0x1c01be64f  mov     [rsp+198h+var_140], rsi
0x1c01be654  call    cs:__imp_KeEnterCriticalRegion
0x1c01be65b  nop     dword ptr [rax+rax+00h]
0x1c01be660  lea     r9, [rsp+198h+var_160]
0x1c01be665  mov     r8b, r14b
0x1c01be668  mov     dl, r14b
0x1c01be66b  xor     ecx, ecx
0x1c01be66d  call    RefsInitializeIrpContext
0x1c01be672  mov     rax, [rsi+78h]
0x1c01be676  mov     rcx, [rax+58h]
0x1c01be67a  mov     rax, [rsp+198h+var_160]
0x1c01be67f  mov     [rax+40h], rcx
0x1c01be683  cmp     dword ptr [rcx+1D4h], 0
0x1c01be68a  jbe     short loc_1C01BE694
0x1c01be68c  xor     r14b, r14b
0x1c01be68f  jmp     loc_1C01BE8B2
0x1c01be694  call    cs:__imp_FsRtlIncrementCcFastMdlReadWait
0x1c01be69b  nop     dword ptr [rax+rax+00h]
0x1c01be6a0  cmp     qword ptr [rsi+10h], 0
0x1c01be6a5  jz      short loc_1C01BE68C
0x1c01be6a7  mov     r8b, r14b
0x1c01be6aa  mov     rdx, rsi
0x1c01be6ad  call    RefsAcquirePagingResourceShared
0x1c01be6b2  cmp     qword ptr [r13+30h], 0
0x1c01be6b7  jz      loc_1C01BE891
0x1c01be6bd  cmp     byte ptr [rsi+5], 0
0x1c01be6c1  jz      loc_1C01BE891
0x1c01be6c7  mov     rax, [rsi+0F0h]
0x1c01be6ce  add     rax, 8
0x1c01be6d2  cmp     [r13+28h], rax
0x1c01be6d6  jnz     loc_1C01BE891
0x1c01be6dc  mov     rcx, [rsi+78h]
0x1c01be6e0  call    RefsIsFileOpen
0x1c01be6e5  test    al, al
0x1c01be6e7  jz      loc_1C01BE891
0x1c01be6ed  mov     rcx, [rsi+30h]; FastMutex
0x1c01be6f1  call    cs:__imp_ExAcquireFastMutex
0x1c01be6f8  nop     dword ptr [rax+rax+00h]
0x1c01be6fd  lock add [rsi+9Ch], r14d
0x1c01be705  cmp     rbx, [rsi+20h]
0x1c01be709  jle     short loc_1C01BE72D
0x1c01be70b  lea     rax, [rsp+198h+var_167]
0x1c01be710  mov     [rsp+198h+IoStatus], rax
0x1c01be715  mov     r9d, r12d
0x1c01be718  mov     r8, [rsp+198h+FileOffset]
0x1c01be71d  mov     r8, [r8]
0x1c01be720  mov     rdx, rsi
0x1c01be723  mov     rcx, [rsp+198h+var_160]
0x1c01be728  call    RefsGetIoAtEof
0x1c01be72d  lock add [rsi+9Ch], r14d
0x1c01be735  mov     rcx, [rsi+30h]; FastMutex
0x1c01be739  call    cs:__imp_ExReleaseFastMutex
0x1c01be740  nop     dword ptr [rax+rax+00h]
0x1c01be745  cmp     byte ptr [rsi+5], 2
0x1c01be749  jnz     short loc_1C01BE779
0x1c01be74b  mov     [rsp+198h+var_170], r14b
0x1c01be750  mov     eax, [rsp+198h+var_150]
0x1c01be754  mov     dword ptr [rsp+198h+IoStatus], eax
0x1c01be758  mov     r9d, r12d
0x1c01be75b  mov     r8, [rsp+198h+FileOffset]
0x1c01be760  mov     rdx, r13
0x1c01be763  mov     rcx, [rsp+198h+var_160]
0x1c01be768  call    RefsFastIoCheckIfPossibleInternal
0x1c01be76d  test    al, al
0x1c01be76f  jnz     short loc_1C01BE779
0x1c01be771  xor     r14b, r14b
0x1c01be774  jmp     loc_1C01BE87B
0x1c01be779  mov     rax, [rsi+20h]
0x1c01be77d  cmp     rbx, rax
0x1c01be780  mov     rbx, [rsp+198h+FileOffset]
0x1c01be785  jle     loc_1C01BE819
0x1c01be78b  cmp     [rbx], rax
0x1c01be78e  jl      short loc_1C01BE801
0x1c01be790  lea     rax, WPP_GLOBAL_Control
0x1c01be797  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01be79e  cmp     rcx, rax
0x1c01be7a1  jz      short loc_1C01BE7CD
0x1c01be7a3  test    dword ptr [rcx+2Ch], 100h
0x1c01be7aa  jz      short loc_1C01BE7CD
0x1c01be7ac  cmp     byte ptr [rcx+29h], 4
0x1c01be7b0  jb      short loc_1C01BE7CD
0x1c01be7b2  mov     edx, 0Bh
0x1c01be7b7  mov     r9d, 0C0000011h
0x1c01be7bd  lea     r8, WPP_93e8087fdfc930c957e27c1f01eb03c6_Traceguids
0x1c01be7c4  mov     rcx, [rcx+18h]
0x1c01be7c8  call    WPP_SF_D
0x1c01be7cd  mov     al, cs:RefsStatusDebugEnabled
0x1c01be7d3  test    al, al
0x1c01be7d5  jz      short loc_1C01BE7EE
0x1c01be7d7  mov     r8d, 474h
0x1c01be7dd  lea     rdx, aFstiosupC; "FstIoSup.c"
0x1c01be7e4  mov     ecx, 0C0000011h; Status
0x1c01be7e9  call    RefsStatusDebug
0x1c01be7ee  mov     dword ptr [r15], 0C0000011h
0x1c01be7f5  and     qword ptr [r15+8], 0
0x1c01be7fa  mov     r14b, [rsp+198h+var_168]
0x1c01be7ff  jmp     short loc_1C01BE87B
0x1c01be801  mov     r12d, eax
0x1c01be804  sub     r12d, [rbx]
0x1c01be807  mov     rdx, rsi
0x1c01be80a  mov     rcx, [rsp+198h+var_160]
0x1c01be80f  call    RefsReleaseEofLock
0x1c01be814  mov     [rsp+198h+var_167], 0
0x1c01be819  mov     ecx, 4; Irp
0x1c01be81e  call    cs:__imp_IoSetTopLevelIrp
0x1c01be825  nop     dword ptr [rax+rax+00h]
0x1c01be82a  nop
0x1c01be82b  and     dword ptr [r15], 0
0x1c01be82f  mov     [rsp+198h+var_168], 0
0x1c01be834  mov     [rsp+198h+IoStatus], r15; IoStatus
0x1c01be839  mov     r9, [rsp+198h+MdlChain]; MdlChain
0x1c01be83e  mov     r8d, r12d; Length
0x1c01be841  mov     rdx, rbx; FileOffset
0x1c01be844  mov     rcx, r13; FileObject
0x1c01be847  call    cs:__imp_CcMdlRead
0x1c01be84e  nop     dword ptr [rax+rax+00h]
0x1c01be853  mov     [rsp+198h+var_168], r14b
0x1c01be858  bts     dword ptr [r13+50h], 13h
0x1c01be85e  jmp     short loc_1C01BE86D
0x1c01be860  xor     r14b, r14b
0x1c01be863  mov     [rsp+198h+var_168], r14b
0x1c01be868  mov     rsi, [rsp+198h+var_140]
0x1c01be86d  xor     ecx, ecx; Irp
0x1c01be86f  call    cs:__imp_IoSetTopLevelIrp
0x1c01be876  nop     dword ptr [rax+rax+00h]
0x1c01be87b  cmp     [rsp+198h+var_167], 0
0x1c01be880  jz      short loc_1C01BE894
0x1c01be882  mov     rdx, rsi
0x1c01be885  mov     rcx, [rsp+198h+var_160]
0x1c01be88a  call    RefsReleaseEofLock
0x1c01be88f  jmp     short loc_1C01BE894
0x1c01be891  xor     r14b, r14b
0x1c01be894  mov     eax, 802h
0x1c01be899  cmp     ax, [rsi]
0x1c01be89c  jz      short loc_1C01BE8A2
0x1c01be89e  mov     rsi, [rsi+78h]
0x1c01be8a2  mov     rcx, [rsi+68h]; Resource
0x1c01be8a6  call    cs:__imp_ExReleaseResourceLite
0x1c01be8ad  nop     dword ptr [rax+rax+00h]
0x1c01be8b2  xor     edx, edx
0x1c01be8b4  mov     rcx, [rsp+198h+var_160]
0x1c01be8b9  call    RefsCleanupIrpContext
0x1c01be8be  call    cs:__imp_KeLeaveCriticalRegion
0x1c01be8c5  nop     dword ptr [rax+rax+00h]
0x1c01be8ca  mov     al, r14b
0x1c01be8cd  mov     rcx, [rsp+198h+var_38]
0x1c01be8d5  xor     rcx, rsp; StackCookie
0x1c01be8d8  call    __security_check_cookie
0x1c01be8dd  mov     rbx, [rsp+198h+arg_18]
0x1c01be8e5  add     rsp, 170h
0x1c01be8ec  pop     r15
0x1c01be8ee  pop     r14
0x1c01be8f0  pop     r13
0x1c01be8f2  pop     r12
0x1c01be8f4  pop     rsi
0x1c01be8f5  retn
0x1c01be8f7  push    rbp
0x1c01be8f9  sub     rsp, 30h
0x1c01be8fd  mov     rbp, rdx
0x1c01be900  mov     rax, [rcx]
0x1c01be903  mov     ecx, [rax]; Exception
0x1c01be905  call    cs:__imp_FsRtlIsNtstatusExpected
0x1c01be90c  nop     dword ptr [rax+rax+00h]
0x1c01be911  xor     ecx, ecx
0x1c01be913  test    al, al
0x1c01be915  setnz   cl
0x1c01be918  mov     eax, ecx
0x1c01be91a  add     rsp, 30h
0x1c01be91e  pop     rbp
0x1c01be91f  retn
```
