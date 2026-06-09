# CdCommonLockControl

- ea: `0x1400156c0`
- end: `0x14001583d`
- name: `CdCommonLockControl`
- size: `381`
- prototype: `__int64 __fastcall(PVOID Context, PIRP Irp)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140001240`
- `0x140002250`

## callees

- `0x140001160`
- `0x1400156c0`
- `0x140018790`
- `0x14001a2a0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140015792`
- `ntoskrnl!ExAcquireFastMutex` at `0x140015792`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001580e`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001580e`
- `ntoskrnl!FsRtlCheckOplock` at `0x140015720`
- `ntoskrnl!FsRtlCheckOplock` at `0x140015720`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1400157bd`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1400157bd`
- `ntoskrnl!FsRtlProcessFileLock` at `0x140015764`
- `ntoskrnl!FsRtlProcessFileLock` at `0x140015764`

## pseudocode

```c
NTSTATUS __fastcall CdCommonLockControl(PVOID Context, PIRP Irp)
{
  PFILE_OBJECT FileObject; // rbx
  NTSTATUS result; // eax
  __int64 FsContext; // rbx
  NTSTATUS v7; // eax
  struct _KTHREAD *CurrentThread; // rsi
  NTSTATUS v9; // ebp
  __int64 v10; // rax
  char v11; // si
  __int64 v12; // rax
  bool v13; // zf
  struct _FAST_MUTEX *v14; // rcx

  FileObject = Irp->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( ((__int64)FileObject->FsContext2 & 7) == 4 )
  {
    FsContext = (__int64)FileObject->FsContext;
    result = FsRtlCheckOplock((POPLOCK)(FsContext + 88), Irp, Context, CdOplockComplete, 0);
    if ( !result )
    {
      CdVerifyFcbOperation(Context, FsContext);
      if ( !*(_QWORD *)(FsContext + 472) )
        CdCreateFileLock((__int64)Context, FsContext, 1);
      v7 = FsRtlProcessFileLock(*(PFILE_LOCK *)(FsContext + 472), Irp, 0);
      CurrentThread = KeGetCurrentThread();
      v9 = v7;
      if ( CurrentThread != *(struct _KTHREAD **)(FsContext + 184) )
      {
        ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(FsContext + 200) + 136LL));
        *(_QWORD *)(FsContext + 184) = CurrentThread;
      }
      v10 = *(_QWORD *)(FsContext + 120);
      v11 = 2;
      ++*(_DWORD *)(FsContext + 192);
      if ( *(_DWORD *)(v10 + 52) == 2 && FsRtlOplockIsFastIoPossible((POPLOCK)(FsContext + 88)) )
      {
        v12 = *(_QWORD *)(FsContext + 472);
        if ( !v12 || !*(_BYTE *)(v12 + 16) )
          v11 = 1;
      }
      else
      {
        v11 = 0;
      }
      v13 = (*(_DWORD *)(FsContext + 192))-- == 1;
      *(_BYTE *)(FsContext + 5) = v11;
      if ( v13 )
      {
        v14 = (struct _FAST_MUTEX *)(*(_QWORD *)(FsContext + 200) + 136LL);
        *(_QWORD *)(FsContext + 184) = 0;
        ExReleaseFastMutex(v14);
      }
      CdCompleteRequest(Context, 0, v9);
      return v9;
    }
  }
  else
  {
    CdCompleteRequest(Context, Irp, -1073741811);
    return -1073741811;
  }
  return result;
}

```

## disassembly

```asm
0x1400156c0  mov     [rsp+arg_0], rbx
0x1400156c5  mov     [rsp+arg_10], rbp
0x1400156ca  push    rsi
0x1400156cb  push    rdi
0x1400156cc  push    r14
0x1400156ce  sub     rsp, 30h
0x1400156d2  mov     rax, [rdx+0B8h]
0x1400156d9  mov     rdi, rcx
0x1400156dc  mov     rsi, rdx
0x1400156df  mov     rbx, [rax+30h]
0x1400156e3  mov     ecx, [rbx+20h]
0x1400156e6  and     ecx, 7
0x1400156e9  cmp     ecx, 4
0x1400156ec  jz      short loc_140015705
0x1400156ee  mov     ebx, 0C000000Dh
0x1400156f3  mov     rcx, rdi
0x1400156f6  mov     r8d, ebx
0x1400156f9  call    CdCompleteRequest
0x1400156fe  mov     eax, ebx
0x140015700  jmp     loc_140015829
0x140015705  mov     rbx, [rbx+18h]
0x140015709  lea     r9, CdOplockComplete; CompletionRoutine
0x140015710  mov     r8, rdi; Context
0x140015713  mov     [rsp+48h+PostIrpRoutine], 0; PostIrpRoutine
0x14001571c  lea     rcx, [rbx+58h]; Oplock
0x140015720  call    cs:__imp_FsRtlCheckOplock
0x140015727  nop     dword ptr [rax+rax+00h]
0x14001572c  test    eax, eax
0x14001572e  jnz     loc_140015829
0x140015734  mov     rdx, rbx
0x140015737  mov     rcx, rdi
0x14001573a  call    CdVerifyFcbOperation
0x14001573f  cmp     qword ptr [rbx+1D8h], 0
0x140015747  jnz     short loc_140015757
0x140015749  mov     r8b, 1
0x14001574c  mov     rdx, rbx
0x14001574f  mov     rcx, rdi
0x140015752  call    CdCreateFileLock
0x140015757  mov     rcx, [rbx+1D8h]; FileLock
0x14001575e  xor     r8d, r8d; Context
0x140015761  mov     rdx, rsi; Irp
0x140015764  call    cs:__imp_FsRtlProcessFileLock
0x14001576b  nop     dword ptr [rax+rax+00h]
0x140015770  mov     rsi, gs:188h
0x140015779  mov     ebp, eax
0x14001577b  cmp     rsi, [rbx+0B8h]
0x140015782  jz      short loc_1400157A5
0x140015784  mov     rcx, [rbx+0C8h]
0x14001578b  add     rcx, 88h; FastMutex
0x140015792  call    cs:__imp_ExAcquireFastMutex
0x140015799  nop     dword ptr [rax+rax+00h]
0x14001579e  mov     [rbx+0B8h], rsi
0x1400157a5  mov     rax, [rbx+78h]
0x1400157a9  mov     esi, 2
0x1400157ae  inc     dword ptr [rbx+0C0h]
0x1400157b4  cmp     [rax+34h], esi
0x1400157b7  jnz     short loc_1400157E6
0x1400157b9  lea     rcx, [rbx+58h]; Oplock
0x1400157bd  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x1400157c4  nop     dword ptr [rax+rax+00h]
0x1400157c9  test    al, al
0x1400157cb  jz      short loc_1400157E6
0x1400157cd  mov     rax, [rbx+1D8h]
0x1400157d4  test    rax, rax
0x1400157d7  jz      short loc_1400157DF
0x1400157d9  cmp     byte ptr [rax+10h], 0
0x1400157dd  jnz     short loc_1400157E8
0x1400157df  mov     esi, 1
0x1400157e4  jmp     short loc_1400157E8
0x1400157e6  xor     esi, esi
0x1400157e8  add     dword ptr [rbx+0C0h], 0FFFFFFFFh
0x1400157ef  mov     [rbx+5], sil
0x1400157f3  jnz     short loc_14001581A
0x1400157f5  mov     rcx, [rbx+0C8h]
0x1400157fc  add     rcx, 88h; FastMutex
0x140015803  mov     qword ptr [rbx+0B8h], 0
0x14001580e  call    cs:__imp_ExReleaseFastMutex
0x140015815  nop     dword ptr [rax+rax+00h]
0x14001581a  mov     r8d, ebp
0x14001581d  xor     edx, edx
0x14001581f  mov     rcx, rdi
0x140015822  call    CdCompleteRequest
0x140015827  mov     eax, ebp
0x140015829  mov     rbx, [rsp+48h+arg_0]
0x14001582e  mov     rbp, [rsp+48h+arg_10]
0x140015833  add     rsp, 30h
0x140015837  pop     r14
0x140015839  pop     rdi
0x14001583a  pop     rsi
0x14001583b  retn
```
