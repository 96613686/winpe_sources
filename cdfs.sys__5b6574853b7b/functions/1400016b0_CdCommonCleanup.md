# CdCommonCleanup

- ea: `0x1400016b0`
- end: `0x140001ac0`
- name: `CdCommonCleanup`
- size: `1040`
- prototype: `__int64 __fastcall(PVOID Context, PIRP Irp)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140001240`
- `0x140002250`

## callees

- `0x140001160`
- `0x1400016b0`
- `0x1400024e0`
- `0x14000287c`
- `0x14000bcf8`
- `0x14000ecd4`
- `0x140013a3c`
- `0x1400181a4`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140001895`
- `ntoskrnl!ExAcquireFastMutex` at `0x140001949`
- `ntoskrnl!ExAcquireFastMutex` at `0x140001895`
- `ntoskrnl!ExAcquireFastMutex` at `0x140001949`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000190f`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400019dd`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000190f`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400019dd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000173f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001790`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001a0b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001a80`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001a93`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000385e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400038a4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400038b8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000173f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001790`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001a0b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001a80`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001a93`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000385e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400038a4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400038b8`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140001869`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140001869`
- `ntoskrnl!KeBugCheckEx` at `0x140001807`
- `ntoskrnl!KeBugCheckEx` at `0x140001807`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000176f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140001a44`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000176f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140001a44`
- `ntoskrnl!FsRtlNotifyCleanup` at `0x140001933`
- `ntoskrnl!FsRtlNotifyCleanup` at `0x140001933`
- `ntoskrnl!FsRtlCheckOplock` at `0x14000181d`
- `ntoskrnl!FsRtlCheckOplock` at `0x14000181d`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x140001855`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x140001855`
- `ntoskrnl!IoGetRequestorProcess` at `0x14000183d`
- `ntoskrnl!IoGetRequestorProcess` at `0x14000183d`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1400018bc`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1400018bc`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140001992`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140001992`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400019c3`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400019c3`
- `ntoskrnl!IoRemoveShareAccess` at `0x1400019f3`
- `ntoskrnl!IoRemoveShareAccess` at `0x1400019f3`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140001a26`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140003879`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140001a26`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140003879`

## pseudocode

```c
__int64 __fastcall CdCommonCleanup(PVOID Context, PIRP Irp)
{
  PFILE_OBJECT FileObject; // r15
  int v5; // eax
  char v6; // r10
  ULONG_PTR v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // rsi
  char v10; // r12
  __int64 v11; // rcx
  __int64 v12; // r8
  FILE_LOCK *v13; // rbx
  struct _KPROCESS *RequestorProcess; // rax
  struct _KTHREAD *CurrentThread; // rbx
  __int64 v16; // rax
  bool v18; // bl
  char v20; // [rsp+30h] [rbp-58h]
  KIRQL Irql; // [rsp+90h] [rbp+8h] BYREF
  PVOID FsContext; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v23; // [rsp+A8h] [rbp+20h] BYREF

  v23 = 0;
  FsContext = 0;
  Irql = 0;
  if ( *((_QWORD *)Context + 2) )
  {
    FileObject = Irp->Tail.Overlay.CurrentStackLocation->FileObject;
    v5 = CdDecodeFileObject(Context, FileObject, &v23, &FsContext);
    v7 = v5;
    if ( v5 > 1 )
    {
      v20 = v6;
      v8 = v23;
      v9 = *(_QWORD *)(v23 + 120);
      CdAcquireResource(Context, *(_QWORD *)(v23 + 8), 0, 0);
      FileObject->Flags |= 0x4000u;
      ExReleaseResourceLite(*(PERESOURCE *)(v8 + 8));
      v10 = 2;
      if ( (_DWORD)v7 == 2 )
      {
        v11 = *((unsigned int *)FsContext + 1);
        if ( (v11 & 0x10) != 0 )
        {
          ExAcquireResourceExclusiveLite(&Resource, 1u);
          LOBYTE(v12) = 1;
          CdCheckForDismount(Context, v9, v12);
          ExReleaseResourceLite(&Resource);
        }
        else if ( (FileObject->Flags & 0x1000) != 0 )
        {
          CdHijackIrpAndFlushDevice(v11, Irp, *(_QWORD *)(v9 + 16));
          CdMarkDevForVerifyIfVcbMounted(v9);
        }
      }
      CdAcquireResource(Context, *(_QWORD *)(v8 + 200) + 32LL, 0, 0);
      if ( (_DWORD)v7 != 2 )
      {
        if ( (_DWORD)v7 == 3 )
        {
          FsRtlNotifyCleanup(*(PNOTIFY_SYNC *)(v9 + 400), (PLIST_ENTRY)(v9 + 408), FsContext);
        }
        else
        {
          if ( (_DWORD)v7 != 4 )
            KeBugCheckEx(0x26u, 0x6010Fu, v7, 0, 0);
          FsRtlCheckOplock((POPLOCK)(v8 + 88), Irp, Context, 0, 0);
          if ( *(_QWORD *)(v8 + 472) )
          {
            v13 = *(FILE_LOCK **)(v8 + 472);
            RequestorProcess = IoGetRequestorProcess(Irp);
            FsRtlFastUnlockAll(v13, FileObject, RequestorProcess, 0);
          }
          CcUninitializeCacheMap(FileObject, 0, 0);
          CurrentThread = KeGetCurrentThread();
          if ( CurrentThread != *(struct _KTHREAD **)(v8 + 184) )
          {
            ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v8 + 200) + 136LL));
            *(_QWORD *)(v8 + 184) = CurrentThread;
          }
          ++*(_DWORD *)(v8 + 192);
          if ( *(_DWORD *)(*(_QWORD *)(v8 + 120) + 52LL) == 2 && FsRtlOplockIsFastIoPossible((POPLOCK)(v8 + 88)) )
          {
            v16 = *(_QWORD *)(v8 + 472);
            if ( !v16 || !*(_BYTE *)(v16 + 16) )
              v10 = 1;
          }
          else
          {
            v10 = 0;
          }
          *(_BYTE *)(v8 + 5) = v10;
          if ( (*(_DWORD *)(v8 + 192))-- == 1 )
          {
            *(_QWORD *)(v8 + 184) = 0;
            ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(v8 + 200) + 136LL));
          }
        }
      }
      ExAcquireFastMutex((PFAST_MUTEX)(v9 + 336));
      *(_QWORD *)(v9 + 392) = KeGetCurrentThread();
      --*(_DWORD *)(v8 + 160);
      --*(_DWORD *)(*(_QWORD *)(v8 + 120) + 56LL);
      v18 = !*(_DWORD *)(v9 + 56) && !*(_DWORD *)(v9 + 52);
      if ( FileObject == *(PFILE_OBJECT *)(v9 + 24) )
      {
        IoAcquireVpbSpinLock(&Irql);
        *(_WORD *)(*(_QWORD *)(v9 + 8) + 4LL) &= ~2u;
        *(_DWORD *)(v9 + 48) &= ~0x10u;
        *(_QWORD *)(v9 + 24) = 0;
        v20 = 1;
        IoReleaseVpbSpinLock(Irql);
      }
      *(_QWORD *)(v9 + 392) = 0;
      ExReleaseFastMutex((PFAST_MUTEX)(v9 + 336));
      IoRemoveShareAccess(FileObject, (PSHARE_ACCESS)(v8 + 208));
      ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v8 + 200) + 32LL));
      if ( v20 )
        FsRtlNotifyVolumeEvent(FileObject, 5u);
      if ( v18 )
      {
        ExAcquireResourceExclusiveLite(&Resource, 1u);
        CdAcquireResource(Context, v9 + 128, 0, 0);
        CdPurgeVolume((__int64)Context, v9, 0);
        ExReleaseResourceLite((PERESOURCE)(v9 + 128));
        ExReleaseResourceLite(&Resource);
      }
    }
  }
  CdCompleteRequest(Context, Irp, 0);
  return 0;
}

```

## disassembly

```asm
0x1400016b0  mov     r11, rsp
0x1400016b3  push    rbx
0x1400016b4  push    rsi
0x1400016b5  push    rdi
0x1400016b6  push    r12
0x1400016b8  push    r13
0x1400016ba  push    r14
0x1400016bc  push    r15
0x1400016be  sub     rsp, 50h
0x1400016c2  mov     r13, rdx
0x1400016c5  mov     r14, rcx
0x1400016c8  xor     r10d, r10d
0x1400016cb  mov     [r11+20h], r10
0x1400016cf  mov     [r11+18h], r10
0x1400016d3  mov     [r11+8], r10b
0x1400016d7  cmp     [rcx+10h], r10
0x1400016db  jz      loc_140001A9F
0x1400016e1  mov     rax, [rdx+0B8h]
0x1400016e8  mov     r15, [rax+30h]
0x1400016ec  lea     r9, [r11+18h]
0x1400016f0  lea     r8, [r11+20h]
0x1400016f4  mov     rdx, r15
0x1400016f7  call    CdDecodeFileObject
0x1400016fc  movsxd  rbx, eax
0x1400016ff  cmp     ebx, 1
0x140001702  jle     loc_140001A9F
0x140001708  mov     [rsp+88h+var_48], r15
0x14000170d  mov     [rsp+88h+var_58], r10b
0x140001712  mov     rdi, [rsp+88h+arg_18]
0x14000171a  mov     rsi, [rdi+78h]
0x14000171e  mov     [rsp+88h+var_50], rsi
0x140001723  xor     r9d, r9d
0x140001726  xor     r8d, r8d
0x140001729  mov     rdx, [rdi+8]
0x14000172d  mov     rcx, r14
0x140001730  call    CdAcquireResource
0x140001735  bts     dword ptr [r15+50h], 0Eh
0x14000173b  mov     rcx, [rdi+8]; Resource
0x14000173f  call    cs:__imp_ExReleaseResourceLite
0x140001746  nop     dword ptr [rax+rax+00h]
0x14000174b  mov     r12d, 2
0x140001751  cmp     ebx, r12d
0x140001754  jnz     short loc_1400017BC
0x140001756  mov     rax, [rsp+88h+FsContext]
0x14000175e  mov     ecx, [rax+4]
0x140001761  test    cl, 10h
0x140001764  jz      short loc_14000179E
0x140001766  mov     dl, 1; Wait
0x140001768  lea     rcx, Resource; Resource
0x14000176f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140001776  nop     dword ptr [rax+rax+00h]
0x14000177b  mov     r8b, 1
0x14000177e  mov     rdx, rsi
0x140001781  mov     rcx, r14
0x140001784  call    CdCheckForDismount
0x140001789  lea     rcx, Resource; Resource
0x140001790  call    cs:__imp_ExReleaseResourceLite
0x140001797  nop     dword ptr [rax+rax+00h]
0x14000179c  jmp     short loc_1400017BC
0x14000179e  test    dword ptr [r15+50h], 1000h
0x1400017a6  jz      short loc_1400017BC
0x1400017a8  mov     r8, [rsi+10h]
0x1400017ac  mov     rdx, r13
0x1400017af  call    CdHijackIrpAndFlushDevice
0x1400017b4  mov     rcx, rsi
0x1400017b7  call    CdMarkDevForVerifyIfVcbMounted
0x1400017bc  mov     rdx, [rdi+0C8h]
0x1400017c3  add     rdx, 20h ; ' '
0x1400017c7  xor     r9d, r9d
0x1400017ca  xor     r8d, r8d
0x1400017cd  mov     rcx, r14
0x1400017d0  call    CdAcquireResource
0x1400017d5  nop
0x1400017d6  mov     ecx, ebx
0x1400017d8  sub     ecx, r12d
0x1400017db  jz      loc_14000193F
0x1400017e1  sub     ecx, 1
0x1400017e4  jz      loc_14000191D
0x1400017ea  mov     [rsp+88h+BugCheckParameter4], 0; PostIrpRoutine
0x1400017f3  xor     r9d, r9d; CompletionRoutine
0x1400017f6  cmp     ecx, 1
0x1400017f9  jz      short loc_140001813
0x1400017fb  mov     r8, rbx; BugCheckParameter2
0x1400017fe  mov     edx, 6010Fh; BugCheckParameter1
0x140001803  lea     ecx, [r9+26h]; BugCheckCode
0x140001807  call    cs:__imp_KeBugCheckEx
0x140001813  lea     rcx, [rdi+58h]; Oplock
0x140001817  mov     r8, r14; Context
0x14000181a  mov     rdx, r13; Irp
0x14000181d  call    cs:__imp_FsRtlCheckOplock
0x140001824  nop     dword ptr [rax+rax+00h]
0x140001829  cmp     qword ptr [rdi+1D8h], 0
0x140001831  jz      short loc_140001861
0x140001833  mov     rbx, [rdi+1D8h]
0x14000183a  mov     rcx, r13; Irp
0x14000183d  call    cs:__imp_IoGetRequestorProcess
0x140001844  nop     dword ptr [rax+rax+00h]
0x140001849  mov     r8, rax; ProcessId
0x14000184c  xor     r9d, r9d; Context
0x14000184f  mov     rdx, r15; FileObject
0x140001852  mov     rcx, rbx; FileLock
0x140001855  call    cs:__imp_FsRtlFastUnlockAll
0x14000185c  nop     dword ptr [rax+rax+00h]
0x140001861  xor     r8d, r8d; UninitializeEvent
0x140001864  xor     edx, edx; TruncateSize
0x140001866  mov     rcx, r15; FileObject
0x140001869  call    cs:__imp_CcUninitializeCacheMap
0x140001870  nop     dword ptr [rax+rax+00h]
0x140001875  mov     rbx, gs:188h
0x14000187e  cmp     rbx, [rdi+0B8h]
0x140001885  jz      short loc_1400018A8
0x140001887  mov     rcx, [rdi+0C8h]
0x14000188e  add     rcx, 88h; FastMutex
0x140001895  call    cs:__imp_ExAcquireFastMutex
0x14000189c  nop     dword ptr [rax+rax+00h]
0x1400018a1  mov     [rdi+0B8h], rbx
0x1400018a8  inc     dword ptr [rdi+0C0h]
0x1400018ae  mov     rax, [rdi+78h]
0x1400018b2  cmp     [rax+34h], r12d
0x1400018b6  jnz     short loc_1400018E6
0x1400018b8  lea     rcx, [rdi+58h]; Oplock
0x1400018bc  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x1400018c3  nop     dword ptr [rax+rax+00h]
0x1400018c8  test    al, al
0x1400018ca  jz      short loc_1400018E6
0x1400018cc  mov     rax, [rdi+1D8h]
0x1400018d3  test    rax, rax
0x1400018d6  jz      short loc_1400018DE
0x1400018d8  cmp     byte ptr [rax+10h], 0
0x1400018dc  jnz     short loc_1400018E9
0x1400018de  mov     r12d, 1
0x1400018e4  jmp     short loc_1400018E9
0x1400018e6  xor     r12d, r12d
0x1400018e9  mov     [rdi+5], r12b
0x1400018ed  add     dword ptr [rdi+0C0h], 0FFFFFFFFh
0x1400018f4  jnz     short loc_14000193F
0x1400018f6  mov     qword ptr [rdi+0B8h], 0
0x140001901  mov     rcx, [rdi+0C8h]
0x140001908  add     rcx, 88h; FastMutex
0x14000190f  call    cs:__imp_ExReleaseFastMutex
0x140001916  nop     dword ptr [rax+rax+00h]
0x14000191b  jmp     short loc_14000193F
0x14000191d  lea     rdx, [rsi+198h]; NotifyList
0x140001924  mov     r8, [rsp+88h+FsContext]; FsContext
0x14000192c  mov     rcx, [rsi+190h]; NotifySync
0x140001933  call    cs:__imp_FsRtlNotifyCleanup
0x14000193a  nop     dword ptr [rax+rax+00h]
0x14000193f  lea     r12, [rsi+150h]
0x140001946  mov     rcx, r12; FastMutex
0x140001949  call    cs:__imp_ExAcquireFastMutex
0x140001950  nop     dword ptr [rax+rax+00h]
0x140001955  mov     rax, gs:188h
0x14000195e  mov     [rsi+188h], rax
0x140001965  dec     dword ptr [rdi+0A0h]
0x14000196b  mov     rax, [rdi+78h]
0x14000196f  dec     dword ptr [rax+38h]
0x140001972  cmp     dword ptr [rsi+38h], 0
0x140001976  jnz     short loc_140001982
0x140001978  cmp     dword ptr [rsi+34h], 0
0x14000197c  jnz     short loc_140001982
0x14000197e  mov     bl, 1
0x140001980  jmp     short loc_140001984
0x140001982  xor     bl, bl
0x140001984  cmp     r15, [rsi+18h]
0x140001988  jnz     short loc_1400019CF
0x14000198a  lea     rcx, [rsp+88h+Irql]; Irql
0x140001992  call    cs:__imp_IoAcquireVpbSpinLock
0x140001999  nop     dword ptr [rax+rax+00h]
0x14000199e  mov     rax, [rsi+8]
0x1400019a2  mov     ecx, 0FFFDh
0x1400019a7  and     [rax+4], cx
0x1400019ab  and     dword ptr [rsi+30h], 0FFFFFFEFh
0x1400019af  mov     qword ptr [rsi+18h], 0
0x1400019b7  mov     [rsp+88h+var_58], 1
0x1400019bc  mov     cl, [rsp+88h+Irql]; Irql
0x1400019c3  call    cs:__imp_IoReleaseVpbSpinLock
0x1400019ca  nop     dword ptr [rax+rax+00h]
0x1400019cf  mov     qword ptr [rsi+188h], 0
0x1400019da  mov     rcx, r12; FastMutex
0x1400019dd  call    cs:__imp_ExReleaseFastMutex
0x1400019e4  nop     dword ptr [rax+rax+00h]
0x1400019e9  lea     rdx, [rdi+0D0h]; ShareAccess
0x1400019f0  mov     rcx, r15; FileObject
0x1400019f3  call    cs:__imp_IoRemoveShareAccess
0x1400019fa  nop     dword ptr [rax+rax+00h]
0x1400019ff  nop
0x140001a00  mov     rcx, [rdi+0C8h]
0x140001a07  add     rcx, 20h ; ' '; Resource
0x140001a0b  call    cs:__imp_ExReleaseResourceLite
0x140001a12  nop     dword ptr [rax+rax+00h]
0x140001a17  cmp     [rsp+88h+var_58], 0
0x140001a1c  jz      short loc_140001A32
0x140001a1e  mov     edx, 5; EventCode
0x140001a23  mov     rcx, r15; FileObject
0x140001a26  call    cs:__imp_FsRtlNotifyVolumeEvent
0x140001a2d  nop     dword ptr [rax+rax+00h]
0x140001a32  test    bl, bl
0x140001a34  jz      short loc_140001A9F
0x140001a36  mov     [rsp+88h+var_57], 0
0x140001a3b  mov     dl, 1; Wait
0x140001a3d  lea     rcx, Resource; Resource
0x140001a44  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140001a4b  nop     dword ptr [rax+rax+00h]
0x140001a50  nop
0x140001a51  lea     rbx, [rsi+80h]
0x140001a58  xor     r9d, r9d
0x140001a5b  xor     r8d, r8d
0x140001a5e  mov     rdx, rbx
0x140001a61  mov     rcx, r14
0x140001a64  call    CdAcquireResource
0x140001a69  mov     [rsp+88h+var_57], 1
0x140001a6e  xor     r8d, r8d
0x140001a71  mov     rdx, rsi
0x140001a74  mov     rcx, r14
0x140001a77  call    CdPurgeVolume
0x140001a7c  nop
0x140001a7d  mov     rcx, rbx; Resource
0x140001a80  call    cs:__imp_ExReleaseResourceLite
0x140001a87  nop     dword ptr [rax+rax+00h]
0x140001a8c  lea     rcx, Resource; Resource
0x140001a93  call    cs:__imp_ExReleaseResourceLite
0x140001a9a  nop     dword ptr [rax+rax+00h]
0x140001a9f  xor     r8d, r8d
0x140001aa2  mov     rdx, r13
0x140001aa5  mov     rcx, r14
0x140001aa8  call    CdCompleteRequest
0x140001aad  xor     eax, eax
0x140001aaf  add     rsp, 50h
0x140001ab3  pop     r15
0x140001ab5  pop     r14
0x140001ab7  pop     r13
0x140001ab9  pop     r12
0x140001abb  pop     rdi
0x140001abc  pop     rsi
0x140001abd  pop     rbx
0x140001abe  retn
0x140003843  push    rbp
0x140003845  sub     rsp, 30h
0x140003849  mov     rbp, rdx
0x14000384c  mov     rax, [rbp+0A8h]
0x140003853  mov     rcx, [rax+0C8h]
0x14000385a  add     rcx, 20h ; ' '; Resource
0x14000385e  call    cs:__imp_ExReleaseResourceLite
0x140003865  nop     dword ptr [rax+rax+00h]
0x14000386a  cmp     byte ptr [rbp+30h], 0
0x14000386e  jz      short loc_140003886
0x140003870  mov     edx, 5; EventCode
0x140003875  mov     rcx, [rbp+40h]; FileObject
0x140003879  call    cs:__imp_FsRtlNotifyVolumeEvent
0x140003880  nop     dword ptr [rax+rax+00h]
0x140003885  nop
0x140003886  add     rsp, 30h
0x14000388a  pop     rbp
0x14000388b  retn
0x14000388d  push    rbp
0x14000388f  sub     rsp, 30h
0x140003893  mov     rbp, rdx
0x140003896  cmp     byte ptr [rbp+31h], 0
0x14000389a  jz      short loc_1400038B1
0x14000389c  mov     rcx, [rbp+38h]
0x1400038a0  sub     rcx, 0FFFFFFFFFFFFFF80h; Resource
0x1400038a4  call    cs:__imp_ExReleaseResourceLite
0x1400038ab  nop     dword ptr [rax+rax+00h]
0x1400038b0  nop
0x1400038b1  lea     rcx, Resource; Resource
0x1400038b8  call    cs:__imp_ExReleaseResourceLite
0x1400038bf  nop     dword ptr [rax+rax+00h]
0x1400038c4  nop
0x1400038c5  add     rsp, 30h
0x1400038c9  pop     rbp
0x1400038ca  retn
```
