# CdFastUnlockAll

- ea: `0x140015a50`
- end: `0x140015be6`
- name: `CdFastUnlockAll`
- size: `406`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject, PEPROCESS ProcessId)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callees

- `0x140015a50`
- `0x140018790`
- `0x14001a2a0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140015b46`
- `ntoskrnl!ExAcquireFastMutex` at `0x140015b46`
- `ntoskrnl!ExReleaseFastMutex` at `0x140015bc5`
- `ntoskrnl!ExReleaseFastMutex` at `0x140015bc5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015aba`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015aba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015bd2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001bd65`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015bd2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001bd65`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x140015b18`
- `ntoskrnl!FsRtlFastUnlockAll` at `0x140015b18`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140015acb`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140015b71`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140015acb`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140015b71`

## pseudocode

```c
char __fastcall CdFastUnlockAll(PFILE_OBJECT FileObject, PEPROCESS ProcessId, __int64 a3)
{
  char result; // al
  PVOID FsContext; // rbx
  char v8; // di
  struct _KTHREAD *CurrentThread; // rsi
  char v10; // si
  __int64 v11; // rax

  *(_QWORD *)(a3 + 8) = 0;
  if ( ((__int64)FileObject->FsContext2 & 7) != 4 )
  {
    *(_DWORD *)a3 = -1073741811;
    return 1;
  }
  FsContext = FileObject->FsContext;
  result = CdVerifyFcbOperation(0, FsContext);
  if ( result )
  {
    if ( !*((_QWORD *)FsContext + 59) )
    {
      *(_DWORD *)a3 = -1073741698;
      return 1;
    }
    v8 = 0;
    KeEnterCriticalRegion();
    if ( FsRtlOplockIsFastIoPossible((POPLOCK)FsContext + 11)
      && (*((_QWORD *)FsContext + 59) || CdCreateFileLock(0, (__int64)FsContext, 0)) )
    {
      v8 = 1;
      *(_DWORD *)a3 = FsRtlFastUnlockAll(*((PFILE_LOCK *)FsContext + 59), FileObject, ProcessId, 0);
      CurrentThread = KeGetCurrentThread();
      if ( CurrentThread != *((struct _KTHREAD **)FsContext + 23) )
      {
        ExAcquireFastMutex((PFAST_MUTEX)(*((_QWORD *)FsContext + 25) + 136LL));
        *((_QWORD *)FsContext + 23) = CurrentThread;
      }
      ++*((_DWORD *)FsContext + 48);
      v10 = 2;
      if ( *(_DWORD *)(*((_QWORD *)FsContext + 15) + 52LL) == 2 && FsRtlOplockIsFastIoPossible((POPLOCK)FsContext + 11) )
      {
        v11 = *((_QWORD *)FsContext + 59);
        if ( !v11 || !*(_BYTE *)(v11 + 16) )
          v10 = 1;
      }
      else
      {
        v10 = 0;
      }
      *((_BYTE *)FsContext + 5) = v10;
      if ( (*((_DWORD *)FsContext + 48))-- == 1 )
      {
        *((_QWORD *)FsContext + 23) = 0;
        ExReleaseFastMutex((PFAST_MUTEX)(*((_QWORD *)FsContext + 25) + 136LL));
      }
    }
    KeLeaveCriticalRegion();
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x140015a50  push    rbx
0x140015a52  push    rsi
0x140015a53  push    rdi
0x140015a54  push    r12
0x140015a56  push    r14
0x140015a58  push    r15
0x140015a5a  sub     rsp, 38h
0x140015a5e  mov     rsi, r8
0x140015a61  mov     r12, rdx
0x140015a64  mov     r14, rcx
0x140015a67  mov     qword ptr [r8+8], 0
0x140015a6f  mov     eax, [rcx+20h]
0x140015a72  and     al, 7
0x140015a74  cmp     al, 4
0x140015a76  jz      short loc_140015A93
0x140015a78  mov     dword ptr [r8], 0C000000Dh
0x140015a7f  mov     eax, 1
0x140015a84  add     rsp, 38h
0x140015a88  pop     r15
0x140015a8a  pop     r14
0x140015a8c  pop     r12
0x140015a8e  pop     rdi
0x140015a8f  pop     rsi
0x140015a90  pop     rbx
0x140015a91  retn
0x140015a93  mov     rbx, [rcx+18h]
0x140015a97  mov     rdx, rbx
0x140015a9a  xor     ecx, ecx
0x140015a9c  call    CdVerifyFcbOperation
0x140015aa1  test    al, al
0x140015aa3  jz      short loc_140015A84
0x140015aa5  cmp     qword ptr [rbx+1D8h], 0
0x140015aad  jnz     short loc_140015AB7
0x140015aaf  mov     dword ptr [rsi], 0C000007Eh
0x140015ab5  jmp     short loc_140015A7F
0x140015ab7  xor     dil, dil
0x140015aba  call    cs:__imp_KeEnterCriticalRegion
0x140015ac1  nop     dword ptr [rax+rax+00h]
0x140015ac6  nop
0x140015ac7  lea     rcx, [rbx+58h]; Oplock
0x140015acb  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x140015ad2  nop     dword ptr [rax+rax+00h]
0x140015ad7  test    al, al
0x140015ad9  jz      loc_140015BD2
0x140015adf  cmp     qword ptr [rbx+1D8h], 0
0x140015ae7  jnz     short loc_140015AFE
0x140015ae9  xor     r8d, r8d
0x140015aec  mov     rdx, rbx
0x140015aef  xor     ecx, ecx
0x140015af1  call    CdCreateFileLock
0x140015af6  test    al, al
0x140015af8  jz      loc_140015BD2
0x140015afe  mov     edi, 1
0x140015b03  mov     [rsp+68h+var_48], dil
0x140015b08  xor     r9d, r9d; Context
0x140015b0b  mov     r8, r12; ProcessId
0x140015b0e  mov     rdx, r14; FileObject
0x140015b11  mov     rcx, [rbx+1D8h]; FileLock
0x140015b18  call    cs:__imp_FsRtlFastUnlockAll
0x140015b1f  nop     dword ptr [rax+rax+00h]
0x140015b24  mov     [rsi], eax
0x140015b26  mov     rsi, gs:188h
0x140015b2f  cmp     rsi, [rbx+0B8h]
0x140015b36  jz      short loc_140015B59
0x140015b38  mov     rcx, [rbx+0C8h]
0x140015b3f  add     rcx, 88h; FastMutex
0x140015b46  call    cs:__imp_ExAcquireFastMutex
0x140015b4d  nop     dword ptr [rax+rax+00h]
0x140015b52  mov     [rbx+0B8h], rsi
0x140015b59  add     [rbx+0C0h], edi
0x140015b5f  mov     rax, [rbx+78h]
0x140015b63  mov     esi, 2
0x140015b68  cmp     [rax+34h], esi
0x140015b6b  jnz     short loc_140015B97
0x140015b6d  lea     rcx, [rbx+58h]; Oplock
0x140015b71  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x140015b78  nop     dword ptr [rax+rax+00h]
0x140015b7d  test    al, al
0x140015b7f  jz      short loc_140015B97
0x140015b81  mov     rax, [rbx+1D8h]
0x140015b88  test    rax, rax
0x140015b8b  jz      short loc_140015B93
0x140015b8d  cmp     byte ptr [rax+10h], 0
0x140015b91  jnz     short loc_140015B99
0x140015b93  mov     esi, edi
0x140015b95  jmp     short loc_140015B99
0x140015b97  xor     esi, esi
0x140015b99  mov     [rbx+5], sil
0x140015b9d  add     dword ptr [rbx+0C0h], 0FFFFFFFFh
0x140015ba4  mov     eax, [rbx+0C0h]
0x140015baa  jnz     short loc_140015BD2
0x140015bac  mov     qword ptr [rbx+0B8h], 0
0x140015bb7  mov     rcx, [rbx+0C8h]
0x140015bbe  add     rcx, 88h; FastMutex
0x140015bc5  call    cs:__imp_ExReleaseFastMutex
0x140015bcc  nop     dword ptr [rax+rax+00h]
0x140015bd1  nop
0x140015bd2  call    cs:__imp_KeLeaveCriticalRegion
0x140015bd9  nop     dword ptr [rax+rax+00h]
0x140015bde  mov     al, dil
0x140015be1  jmp     loc_140015A84
0x14001bd5c  push    rbp
0x14001bd5e  sub     rsp, 20h
0x14001bd62  mov     rbp, rdx
0x14001bd65  call    cs:__imp_KeLeaveCriticalRegion
0x14001bd6c  nop     dword ptr [rax+rax+00h]
0x14001bd71  nop
0x14001bd72  add     rsp, 20h
0x14001bd76  pop     rbp
0x14001bd77  retn
```
