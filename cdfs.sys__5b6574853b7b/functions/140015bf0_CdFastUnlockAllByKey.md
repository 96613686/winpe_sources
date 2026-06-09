# CdFastUnlockAllByKey

- ea: `0x140015bf0`
- end: `0x140015da7`
- name: `CdFastUnlockAllByKey`
- size: `439`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject, PEPROCESS ProcessId, ULONG Key)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callees

- `0x140015bf0`
- `0x140018790`
- `0x14001a2a0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140015d07`
- `ntoskrnl!ExAcquireFastMutex` at `0x140015d07`
- `ntoskrnl!ExReleaseFastMutex` at `0x140015d86`
- `ntoskrnl!ExReleaseFastMutex` at `0x140015d86`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015c72`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015c72`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015d93`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001bd88`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015d93`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001bd88`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140015c83`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140015d32`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140015c83`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140015d32`
- `ntoskrnl!FsRtlFastUnlockAllByKey` at `0x140015cd9`
- `ntoskrnl!FsRtlFastUnlockAllByKey` at `0x140015cd9`

## pseudocode

```c
char __fastcall CdFastUnlockAllByKey(PFILE_OBJECT FileObject, PEPROCESS ProcessId, ULONG Key, __int64 a4)
{
  char result; // al
  PVOID FsContext; // rbx
  char v10; // di
  struct _KTHREAD *CurrentThread; // rsi
  char v12; // si
  __int64 v13; // rax

  *(_QWORD *)(a4 + 8) = 0;
  if ( ((__int64)FileObject->FsContext2 & 7) != 4 )
  {
    *(_DWORD *)a4 = -1073741811;
    return 1;
  }
  FsContext = FileObject->FsContext;
  result = CdVerifyFcbOperation(0, FsContext);
  if ( result )
  {
    if ( !*((_QWORD *)FsContext + 59) )
    {
      *(_DWORD *)a4 = -1073741698;
      return 1;
    }
    v10 = 0;
    KeEnterCriticalRegion();
    if ( FsRtlOplockIsFastIoPossible((POPLOCK)FsContext + 11)
      && (*((_QWORD *)FsContext + 59) || CdCreateFileLock(0, (__int64)FsContext, 0)) )
    {
      v10 = 1;
      *(_DWORD *)a4 = FsRtlFastUnlockAllByKey(*((PFILE_LOCK *)FsContext + 59), FileObject, ProcessId, Key, 0);
      CurrentThread = KeGetCurrentThread();
      if ( CurrentThread != *((struct _KTHREAD **)FsContext + 23) )
      {
        ExAcquireFastMutex((PFAST_MUTEX)(*((_QWORD *)FsContext + 25) + 136LL));
        *((_QWORD *)FsContext + 23) = CurrentThread;
      }
      ++*((_DWORD *)FsContext + 48);
      v12 = 2;
      if ( *(_DWORD *)(*((_QWORD *)FsContext + 15) + 52LL) == 2 && FsRtlOplockIsFastIoPossible((POPLOCK)FsContext + 11) )
      {
        v13 = *((_QWORD *)FsContext + 59);
        if ( !v13 || !*(_BYTE *)(v13 + 16) )
          v12 = 1;
      }
      else
      {
        v12 = 0;
      }
      *((_BYTE *)FsContext + 5) = v12;
      if ( (*((_DWORD *)FsContext + 48))-- == 1 )
      {
        *((_QWORD *)FsContext + 23) = 0;
        ExReleaseFastMutex((PFAST_MUTEX)(*((_QWORD *)FsContext + 25) + 136LL));
      }
    }
    KeLeaveCriticalRegion();
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x140015bf0  mov     [rsp+arg_8], rbx
0x140015bf5  mov     [rsp+arg_10], rsi
0x140015bfa  push    rdi
0x140015bfb  push    r12
0x140015bfd  push    r13
0x140015bff  push    r14
0x140015c01  push    r15
0x140015c03  sub     rsp, 40h
0x140015c07  mov     rsi, r9
0x140015c0a  mov     r12d, r8d
0x140015c0d  mov     r13, rdx
0x140015c10  mov     r14, rcx
0x140015c13  mov     qword ptr [r9+8], 0
0x140015c1b  mov     eax, [rcx+20h]
0x140015c1e  and     al, 7
0x140015c20  cmp     al, 4
0x140015c22  jz      short loc_140015C4B
0x140015c24  mov     dword ptr [r9], 0C000000Dh
0x140015c2b  mov     eax, 1
0x140015c30  lea     r11, [rsp+68h+var_28]
0x140015c35  mov     rbx, [r11+38h]
0x140015c39  mov     rsi, [r11+40h]
0x140015c3d  mov     rsp, r11
0x140015c40  pop     r15
0x140015c42  pop     r14
0x140015c44  pop     r13
0x140015c46  pop     r12
0x140015c48  pop     rdi
0x140015c49  retn
0x140015c4b  mov     rbx, [rcx+18h]
0x140015c4f  mov     rdx, rbx
0x140015c52  xor     ecx, ecx
0x140015c54  call    CdVerifyFcbOperation
0x140015c59  test    al, al
0x140015c5b  jz      short loc_140015C30
0x140015c5d  cmp     qword ptr [rbx+1D8h], 0
0x140015c65  jnz     short loc_140015C6F
0x140015c67  mov     dword ptr [rsi], 0C000007Eh
0x140015c6d  jmp     short loc_140015C2B
0x140015c6f  xor     dil, dil
0x140015c72  call    cs:__imp_KeEnterCriticalRegion
0x140015c79  nop     dword ptr [rax+rax+00h]
0x140015c7e  nop
0x140015c7f  lea     rcx, [rbx+58h]; Oplock
0x140015c83  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x140015c8a  nop     dword ptr [rax+rax+00h]
0x140015c8f  test    al, al
0x140015c91  jz      loc_140015D93
0x140015c97  cmp     qword ptr [rbx+1D8h], 0
0x140015c9f  jnz     short loc_140015CB6
0x140015ca1  xor     r8d, r8d
0x140015ca4  mov     rdx, rbx
0x140015ca7  xor     ecx, ecx
0x140015ca9  call    CdCreateFileLock
0x140015cae  test    al, al
0x140015cb0  jz      loc_140015D93
0x140015cb6  mov     edi, 1
0x140015cbb  mov     [rsp+68h+var_38], dil
0x140015cc0  mov     [rsp+68h+Context], 0; Context
0x140015cc9  mov     r9d, r12d; Key
0x140015ccc  mov     r8, r13; ProcessId
0x140015ccf  mov     rdx, r14; FileObject
0x140015cd2  mov     rcx, [rbx+1D8h]; FileLock
0x140015cd9  call    cs:__imp_FsRtlFastUnlockAllByKey
0x140015ce0  nop     dword ptr [rax+rax+00h]
0x140015ce5  mov     [rsi], eax
0x140015ce7  mov     rsi, gs:188h
0x140015cf0  cmp     rsi, [rbx+0B8h]
0x140015cf7  jz      short loc_140015D1A
0x140015cf9  mov     rcx, [rbx+0C8h]
0x140015d00  add     rcx, 88h; FastMutex
0x140015d07  call    cs:__imp_ExAcquireFastMutex
0x140015d0e  nop     dword ptr [rax+rax+00h]
0x140015d13  mov     [rbx+0B8h], rsi
0x140015d1a  add     [rbx+0C0h], edi
0x140015d20  mov     rax, [rbx+78h]
0x140015d24  mov     esi, 2
0x140015d29  cmp     [rax+34h], esi
0x140015d2c  jnz     short loc_140015D58
0x140015d2e  lea     rcx, [rbx+58h]; Oplock
0x140015d32  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x140015d39  nop     dword ptr [rax+rax+00h]
0x140015d3e  test    al, al
0x140015d40  jz      short loc_140015D58
0x140015d42  mov     rax, [rbx+1D8h]
0x140015d49  test    rax, rax
0x140015d4c  jz      short loc_140015D54
0x140015d4e  cmp     byte ptr [rax+10h], 0
0x140015d52  jnz     short loc_140015D5A
0x140015d54  mov     esi, edi
0x140015d56  jmp     short loc_140015D5A
0x140015d58  xor     esi, esi
0x140015d5a  mov     [rbx+5], sil
0x140015d5e  add     dword ptr [rbx+0C0h], 0FFFFFFFFh
0x140015d65  mov     eax, [rbx+0C0h]
0x140015d6b  jnz     short loc_140015D93
0x140015d6d  mov     qword ptr [rbx+0B8h], 0
0x140015d78  mov     rcx, [rbx+0C8h]
0x140015d7f  add     rcx, 88h; FastMutex
0x140015d86  call    cs:__imp_ExReleaseFastMutex
0x140015d8d  nop     dword ptr [rax+rax+00h]
0x140015d92  nop
0x140015d93  call    cs:__imp_KeLeaveCriticalRegion
0x140015d9a  nop     dword ptr [rax+rax+00h]
0x140015d9f  mov     al, dil
0x140015da2  jmp     loc_140015C30
0x14001bd7f  push    rbp
0x14001bd81  sub     rsp, 30h
0x14001bd85  mov     rbp, rdx
0x14001bd88  call    cs:__imp_KeLeaveCriticalRegion
0x14001bd8f  nop     dword ptr [rax+rax+00h]
0x14001bd94  nop
0x14001bd95  add     rsp, 30h
0x14001bd99  pop     rbp
0x14001bd9a  retn
```
