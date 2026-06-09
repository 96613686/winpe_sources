# RefsCopyReadA

- ea: `0x1c01bdb10`
- end: `0x1c01bdefa`
- name: `RefsCopyReadA`
- size: `1002`
- prototype: `__int64 __usercall@<rax>(PFILE_OBJECT FileObject@<rcx>, PLARGE_INTEGER FileOffset@<rdx>, ULONG Length@<r8d>, int, __int64, PIO_STATUS_BLOCK)`
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
- `0x1c01bdb10`
- `0x1c01c1b80`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c01bde67`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01bde67`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01bdc85`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01bdc85`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01bdcc7`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01bdcc7`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c01bdede`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c01bdede`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c01bdb68`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c01bdb68`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c01bddd0`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c01bde38`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c01bddd0`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c01bde38`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c01bdbc9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c01bdbc9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c01bde90`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c01bde90`
- `ntoskrnl!CcCopyRead` at `0x1c01bddfe`
- `ntoskrnl!CcCopyRead` at `0x1c01bddfe`
- `ntoskrnl!FsRtlIncrementCcFastReadWait` at `0x1c01bdc0c`
- `ntoskrnl!FsRtlIncrementCcFastReadWait` at `0x1c01bdc0c`
- `ntoskrnl!FsRtlIncrementCcFastReadNoWait` at `0x1c01bdc1a`
- `ntoskrnl!FsRtlIncrementCcFastReadNoWait` at `0x1c01bdc1a`
- `ntoskrnl!FsRtlIncrementCcFastReadResourceMiss` at `0x1c01bde75`
- `ntoskrnl!FsRtlIncrementCcFastReadResourceMiss` at `0x1c01bde75`
- `ntoskrnl!FsRtlIncrementCcFastReadNotPossible` at `0x1c01bdd00`
- `ntoskrnl!FsRtlIncrementCcFastReadNotPossible` at `0x1c01bde46`
- `ntoskrnl!FsRtlIncrementCcFastReadNotPossible` at `0x1c01bdd00`
- `ntoskrnl!FsRtlIncrementCcFastReadNotPossible` at `0x1c01bde46`

## pseudocode

```c
BOOLEAN __fastcall RefsCopyReadA(
        PFILE_OBJECT FileObject,
        PLARGE_INTEGER FileOffset,
        ULONG Length,
        BOOLEAN a4,
        int a5,
        void *a6,
        PIO_STATUS_BLOCK IoStatus)
{
  __int64 v7; // r12
  BOOLEAN v10; // si
  LONGLONG v11; // rbx
  PVOID v12; // rdi
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  LONGLONG v20; // rax
  _BYTE v23[6]; // [rsp+32h] [rbp-166h] BYREF
  _BYTE *v24; // [rsp+38h] [rbp-160h] BYREF
  PVOID Buffer; // [rsp+40h] [rbp-158h]
  PVOID FsContext; // [rsp+48h] [rbp-150h]
  _BYTE v27[256]; // [rsp+50h] [rbp-148h] BYREF

  v7 = Length;
  Buffer = a6;
  v10 = 1;
  v23[0] = 0;
  if ( !IoGetTopLevelIrp() )
  {
    if ( !(_DWORD)v7 )
    {
      IoStatus->Status = 0;
      IoStatus->Information = 0;
      return v10;
    }
    memset(v27, 0, sizeof(v27));
    v24 = v27;
    if ( 0x7FFFFFFFFFFFFFFFLL - FileOffset->QuadPart >= v7 )
    {
      v11 = v7 + FileOffset->QuadPart;
      FsContext = FileObject->FsContext;
      v12 = FsContext;
      KeEnterCriticalRegion();
      LOBYTE(v13) = 1;
      LOBYTE(v14) = 1;
      RefsInitializeIrpContext(0, v14, v13, &v24);
      v15 = *(_QWORD *)(*((_QWORD *)v12 + 15) + 88LL);
      *((_QWORD *)v24 + 8) = v15;
      if ( !*(_DWORD *)(v15 + 468) )
      {
        if ( a4 )
          FsRtlIncrementCcFastReadWait();
        else
          FsRtlIncrementCcFastReadNoWait();
        if ( *((_QWORD *)v12 + 2) )
        {
          LOBYTE(v17) = a4;
          if ( (unsigned __int8)RefsAcquirePagingResourceShared(v16, v12, v17) )
          {
            if ( FileObject->PrivateCacheMap && *((_BYTE *)v12 + 5) )
            {
              if ( (unsigned __int8)RefsIsFileOpen(*((_QWORD *)v12 + 15), v18, v19)
                && FileObject->SectionObjectPointer == (PSECTION_OBJECT_POINTERS)(*((_QWORD *)v12 + 30) + 8LL) )
              {
                ExAcquireFastMutex(*((PFAST_MUTEX *)v12 + 6));
                _InterlockedAdd((volatile signed __int32 *)v12 + 39, 1u);
                if ( v11 > *((_QWORD *)v12 + 4) )
                  RefsGetIoAtEof((_DWORD)v24, (_DWORD)v12, FileOffset->QuadPart, v7, (__int64)v23);
                _InterlockedAdd((volatile signed __int32 *)v12 + 39, 1u);
                ExReleaseFastMutex(*((PFAST_MUTEX *)v12 + 6));
                if ( *((_BYTE *)v12 + 5) == 2
                  && !(unsigned __int8)RefsFastIoCheckIfPossibleInternal(
                                         v24,
                                         FileObject,
                                         FileOffset,
                                         (unsigned int)v7,
                                         a5,
                                         1) )
                {
                  FsRtlIncrementCcFastReadNotPossible();
                  v10 = 0;
LABEL_28:
                  if ( v23[0] )
                    RefsReleaseEofLock(v24, v12);
                  goto LABEL_36;
                }
                v20 = *((_QWORD *)v12 + 4);
                if ( v11 > v20 )
                {
                  if ( FileOffset->QuadPart >= v20 )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    {
                      WPP_SF_D(
                        WPP_GLOBAL_Control->AttachedDevice,
                        10,
                        WPP_93e8087fdfc930c957e27c1f01eb03c6_Traceguids,
                        3221225489LL);
                    }
                    if ( RefsStatusDebugEnabled )
                      RefsStatusDebug(-1073741807);
                    IoStatus->Status = -1073741807;
                    IoStatus->Information = 0;
                    v10 = 1;
                    goto LABEL_28;
                  }
                  LODWORD(v7) = v20 - FileOffset->LowPart;
                  RefsReleaseEofLock(v24, v12);
                }
                IoSetTopLevelIrp((PIRP)4);
                IoStatus->Status = 0;
                v10 = CcCopyRead(FileObject, FileOffset, v7, a4, Buffer, IoStatus);
                FileObject->Flags |= 0x80000u;
                if ( v10 )
                  FileObject->CurrentByteOffset.QuadPart = FileOffset->QuadPart + IoStatus->Information;
                IoSetTopLevelIrp(0);
                goto LABEL_36;
              }
            }
            else
            {
              FsRtlIncrementCcFastReadNotPossible();
            }
            v10 = 0;
LABEL_36:
            if ( *(_WORD *)v12 != 2050 )
              v12 = (PVOID)*((_QWORD *)v12 + 15);
            ExReleaseResourceLite(*((PERESOURCE *)v12 + 13));
            goto LABEL_41;
          }
        }
        FsRtlIncrementCcFastReadResourceMiss();
      }
      v10 = 0;
LABEL_41:
      RefsCleanupIrpContext(v24, 0);
      KeLeaveCriticalRegion();
      return v10;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1c01bdb10  push    rbx
0x1c01bdb12  push    rsi
0x1c01bdb13  push    rdi
0x1c01bdb14  push    r12
0x1c01bdb16  push    r13
0x1c01bdb18  push    r14
0x1c01bdb1a  push    r15
0x1c01bdb1c  sub     rsp, 160h
0x1c01bdb23  mov     rax, cs:__security_cookie
0x1c01bdb2a  xor     rax, rsp
0x1c01bdb2d  mov     [rsp+198h+var_48], rax
0x1c01bdb35  mov     [rsp+198h+Wait], r9b
0x1c01bdb3a  mov     r12d, r8d
0x1c01bdb3d  mov     r13, rdx
0x1c01bdb40  mov     r15, rcx
0x1c01bdb43  mov     rax, [rsp+198h+arg_28]
0x1c01bdb4b  mov     [rsp+198h+var_158], rax
0x1c01bdb50  mov     r14, [rsp+198h+arg_30]
0x1c01bdb58  mov     esi, 1
0x1c01bdb5d  mov     [rsp+198h+var_167], sil
0x1c01bdb62  xor     ebx, ebx
0x1c01bdb64  mov     [rsp+198h+var_166], bl
0x1c01bdb68  call    cs:__imp_IoGetTopLevelIrp
0x1c01bdb6f  nop     dword ptr [rax+rax+00h]
0x1c01bdb74  test    rax, rax
0x1c01bdb77  jnz     loc_1C01BDEAA
0x1c01bdb7d  test    r12d, r12d
0x1c01bdb80  jz      loc_1C01BDE9E
0x1c01bdb86  xor     edx, edx; Val
0x1c01bdb88  mov     r8d, 100h; Size
0x1c01bdb8e  lea     rcx, [rsp+198h+var_148]; void *
0x1c01bdb93  call    memset
0x1c01bdb98  lea     rax, [rsp+198h+var_148]
0x1c01bdb9d  mov     [rsp+198h+var_160], rax
0x1c01bdba2  mov     rcx, [r13+0]
0x1c01bdba6  mov     rax, 7FFFFFFFFFFFFFFFh
0x1c01bdbb0  sub     rax, rcx
0x1c01bdbb3  cmp     rax, r12
0x1c01bdbb6  jl      loc_1C01BDEAA
0x1c01bdbbc  lea     rbx, [r12+rcx]
0x1c01bdbc0  mov     rdi, [r15+18h]
0x1c01bdbc4  mov     [rsp+198h+var_150], rdi
0x1c01bdbc9  call    cs:__imp_KeEnterCriticalRegion
0x1c01bdbd0  nop     dword ptr [rax+rax+00h]
0x1c01bdbd5  lea     r9, [rsp+198h+var_160]
0x1c01bdbda  mov     r8b, sil
0x1c01bdbdd  mov     dl, sil
0x1c01bdbe0  xor     ecx, ecx
0x1c01bdbe2  call    RefsInitializeIrpContext
0x1c01bdbe7  mov     rax, [rdi+78h]
0x1c01bdbeb  mov     rcx, [rax+58h]
0x1c01bdbef  mov     rax, [rsp+198h+var_160]
0x1c01bdbf4  mov     [rax+40h], rcx
0x1c01bdbf8  cmp     dword ptr [rcx+1D4h], 0
0x1c01bdbff  ja      loc_1C01BDE81
0x1c01bdc05  cmp     [rsp+198h+Wait], 0
0x1c01bdc0a  jz      short loc_1C01BDC1A
0x1c01bdc0c  call    cs:__imp_FsRtlIncrementCcFastReadWait
0x1c01bdc13  nop     dword ptr [rax+rax+00h]
0x1c01bdc18  jmp     short loc_1C01BDC26
0x1c01bdc1a  call    cs:__imp_FsRtlIncrementCcFastReadNoWait
0x1c01bdc21  nop     dword ptr [rax+rax+00h]
0x1c01bdc26  cmp     qword ptr [rdi+10h], 0
0x1c01bdc2b  jz      loc_1C01BDE75
0x1c01bdc31  mov     r8b, [rsp+198h+Wait]
0x1c01bdc36  mov     rdx, rdi
0x1c01bdc39  call    RefsAcquirePagingResourceShared
0x1c01bdc3e  test    al, al
0x1c01bdc40  jz      loc_1C01BDE75
0x1c01bdc46  cmp     qword ptr [r15+30h], 0
0x1c01bdc4b  jz      loc_1C01BDE46
0x1c01bdc51  cmp     byte ptr [rdi+5], 0
0x1c01bdc55  jz      loc_1C01BDE46
0x1c01bdc5b  mov     rcx, [rdi+78h]
0x1c01bdc5f  call    RefsIsFileOpen
0x1c01bdc64  test    al, al
0x1c01bdc66  jz      loc_1C01BDE52
0x1c01bdc6c  mov     rax, [rdi+0F0h]
0x1c01bdc73  add     rax, 8
0x1c01bdc77  cmp     [r15+28h], rax
0x1c01bdc7b  jnz     loc_1C01BDE52
0x1c01bdc81  mov     rcx, [rdi+30h]; FastMutex
0x1c01bdc85  call    cs:__imp_ExAcquireFastMutex
0x1c01bdc8c  nop     dword ptr [rax+rax+00h]
0x1c01bdc91  lock add [rdi+9Ch], esi
0x1c01bdc98  cmp     rbx, [rdi+20h]
0x1c01bdc9c  jle     short loc_1C01BDCBC
0x1c01bdc9e  lea     rax, [rsp+198h+var_166]
0x1c01bdca3  mov     [rsp+198h+Buffer], rax
0x1c01bdca8  mov     r9d, r12d
0x1c01bdcab  mov     r8, [r13+0]
0x1c01bdcaf  mov     rdx, rdi
0x1c01bdcb2  mov     rcx, [rsp+198h+var_160]
0x1c01bdcb7  call    RefsGetIoAtEof
0x1c01bdcbc  lock add [rdi+9Ch], esi
0x1c01bdcc3  mov     rcx, [rdi+30h]; FastMutex
0x1c01bdcc7  call    cs:__imp_ExReleaseFastMutex
0x1c01bdcce  nop     dword ptr [rax+rax+00h]
0x1c01bdcd3  cmp     byte ptr [rdi+5], 2
0x1c01bdcd7  jnz     short loc_1C01BDD14
0x1c01bdcd9  mov     byte ptr [rsp+198h+IoStatus], sil
0x1c01bdcde  mov     eax, [rsp+198h+arg_20]
0x1c01bdce5  mov     dword ptr [rsp+198h+Buffer], eax
0x1c01bdce9  mov     r9d, r12d
0x1c01bdcec  mov     r8, r13
0x1c01bdcef  mov     rdx, r15
0x1c01bdcf2  mov     rcx, [rsp+198h+var_160]
0x1c01bdcf7  call    RefsFastIoCheckIfPossibleInternal
0x1c01bdcfc  test    al, al
0x1c01bdcfe  jnz     short loc_1C01BDD14
0x1c01bdd00  call    cs:__imp_FsRtlIncrementCcFastReadNotPossible
0x1c01bdd07  nop     dword ptr [rax+rax+00h]
0x1c01bdd0c  xor     sil, sil
0x1c01bdd0f  jmp     loc_1C01BDD9A
0x1c01bdd14  mov     rax, [rdi+20h]
0x1c01bdd18  cmp     rbx, rax
0x1c01bdd1b  jle     loc_1C01BDDCB
0x1c01bdd21  cmp     [r13+0], rax
0x1c01bdd25  jl      loc_1C01BDDB7
0x1c01bdd2b  lea     rax, WPP_GLOBAL_Control
0x1c01bdd32  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01bdd39  cmp     rcx, rax
0x1c01bdd3c  jz      short loc_1C01BDD68
0x1c01bdd3e  test    dword ptr [rcx+2Ch], 100h
0x1c01bdd45  jz      short loc_1C01BDD68
0x1c01bdd47  cmp     byte ptr [rcx+29h], 4
0x1c01bdd4b  jb      short loc_1C01BDD68
0x1c01bdd4d  mov     edx, 0Ah
0x1c01bdd52  mov     r9d, 0C0000011h
0x1c01bdd58  lea     r8, WPP_93e8087fdfc930c957e27c1f01eb03c6_Traceguids
0x1c01bdd5f  mov     rcx, [rcx+18h]
0x1c01bdd63  call    WPP_SF_D
0x1c01bdd68  mov     al, cs:RefsStatusDebugEnabled
0x1c01bdd6e  test    al, al
0x1c01bdd70  jz      short loc_1C01BDD89
0x1c01bdd72  mov     r8d, 120h
0x1c01bdd78  lea     rdx, aFstiosupC; "FstIoSup.c"
0x1c01bdd7f  mov     ecx, 0C0000011h; Status
0x1c01bdd84  call    RefsStatusDebug
0x1c01bdd89  mov     dword ptr [r14], 0C0000011h
0x1c01bdd90  and     qword ptr [r14+8], 0
0x1c01bdd95  mov     sil, [rsp+198h+var_167]
0x1c01bdd9a  cmp     [rsp+198h+var_166], 0
0x1c01bdd9f  jz      loc_1C01BDE55
0x1c01bdda5  mov     rdx, rdi
0x1c01bdda8  mov     rcx, [rsp+198h+var_160]
0x1c01bddad  call    RefsReleaseEofLock
0x1c01bddb2  jmp     loc_1C01BDE55
0x1c01bddb7  mov     r12d, eax
0x1c01bddba  sub     r12d, [r13+0]
0x1c01bddbe  mov     rdx, rdi
0x1c01bddc1  mov     rcx, [rsp+198h+var_160]
0x1c01bddc6  call    RefsReleaseEofLock
0x1c01bddcb  mov     ecx, 4; Irp
0x1c01bddd0  call    cs:__imp_IoSetTopLevelIrp
0x1c01bddd7  nop     dword ptr [rax+rax+00h]
0x1c01bdddc  nop
0x1c01bdddd  and     dword ptr [r14], 0
0x1c01bdde1  mov     [rsp+198h+IoStatus], r14; IoStatus
0x1c01bdde6  mov     rax, [rsp+198h+var_158]
0x1c01bddeb  mov     [rsp+198h+Buffer], rax; Buffer
0x1c01bddf0  mov     r9b, [rsp+198h+Wait]; Wait
0x1c01bddf5  mov     r8d, r12d; Length
0x1c01bddf8  mov     rdx, r13; FileOffset
0x1c01bddfb  mov     rcx, r15; FileObject
0x1c01bddfe  call    cs:__imp_CcCopyRead
0x1c01bde05  nop     dword ptr [rax+rax+00h]
0x1c01bde0a  mov     sil, al
0x1c01bde0d  mov     [rsp+198h+var_167], al
0x1c01bde11  bts     dword ptr [r15+50h], 13h
0x1c01bde17  test    al, al
0x1c01bde19  jz      short loc_1C01BDE27
0x1c01bde1b  mov     rcx, [r14+8]
0x1c01bde1f  add     rcx, [r13+0]
0x1c01bde23  mov     [r15+68h], rcx
0x1c01bde27  jmp     short loc_1C01BDE36
0x1c01bde29  xor     sil, sil
0x1c01bde2c  mov     [rsp+198h+var_167], sil
0x1c01bde31  mov     rdi, [rsp+198h+var_150]
0x1c01bde36  xor     ecx, ecx; Irp
0x1c01bde38  call    cs:__imp_IoSetTopLevelIrp
0x1c01bde3f  nop     dword ptr [rax+rax+00h]
0x1c01bde44  jmp     short loc_1C01BDE55
0x1c01bde46  call    cs:__imp_FsRtlIncrementCcFastReadNotPossible
0x1c01bde4d  nop     dword ptr [rax+rax+00h]
0x1c01bde52  xor     sil, sil
0x1c01bde55  mov     eax, 802h
0x1c01bde5a  cmp     ax, [rdi]
0x1c01bde5d  jz      short loc_1C01BDE63
0x1c01bde5f  mov     rdi, [rdi+78h]
0x1c01bde63  mov     rcx, [rdi+68h]; Resource
0x1c01bde67  call    cs:__imp_ExReleaseResourceLite
0x1c01bde6e  nop     dword ptr [rax+rax+00h]
0x1c01bde73  jmp     short loc_1C01BDE84
0x1c01bde75  call    cs:__imp_FsRtlIncrementCcFastReadResourceMiss
0x1c01bde7c  nop     dword ptr [rax+rax+00h]
0x1c01bde81  xor     sil, sil
0x1c01bde84  xor     edx, edx
0x1c01bde86  mov     rcx, [rsp+198h+var_160]
0x1c01bde8b  call    RefsCleanupIrpContext
0x1c01bde90  call    cs:__imp_KeLeaveCriticalRegion
0x1c01bde97  nop     dword ptr [rax+rax+00h]
0x1c01bde9c  jmp     short loc_1C01BDEA5
0x1c01bde9e  mov     [r14], ebx
0x1c01bdea1  mov     [r14+8], rbx
0x1c01bdea5  mov     al, sil
0x1c01bdea8  jmp     short loc_1C01BDEAC
0x1c01bdeaa  xor     al, al
0x1c01bdeac  mov     rcx, [rsp+198h+var_48]
0x1c01bdeb4  xor     rcx, rsp; StackCookie
0x1c01bdeb7  call    __security_check_cookie
0x1c01bdebc  add     rsp, 160h
0x1c01bdec3  pop     r15
0x1c01bdec5  pop     r14
0x1c01bdec7  pop     r13
0x1c01bdec9  pop     r12
0x1c01bdecb  pop     rdi
0x1c01bdecc  pop     rsi
0x1c01bdecd  pop     rbx
0x1c01bdece  retn
0x1c01bded0  push    rbp
0x1c01bded2  sub     rsp, 30h
0x1c01bded6  mov     rbp, rdx
0x1c01bded9  mov     rax, [rcx]
0x1c01bdedc  mov     ecx, [rax]; Exception
0x1c01bdede  call    cs:__imp_FsRtlIsNtstatusExpected
0x1c01bdee5  nop     dword ptr [rax+rax+00h]
0x1c01bdeea  xor     ecx, ecx
0x1c01bdeec  test    al, al
0x1c01bdeee  setnz   cl
0x1c01bdef1  mov     eax, ecx
0x1c01bdef3  add     rsp, 30h
0x1c01bdef7  pop     rbp
0x1c01bdef8  retn
```
