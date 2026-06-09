# NOTIFICATION_THREAD::AddMonitor(CONFIG_MONITOR *)

- ea: `0x180050b70`
- end: `0x180050c3b`
- name: `?AddMonitor@NOTIFICATION_THREAD@@QEAAJPEAUCONFIG_MONITOR@@@Z`
- size: `203`
- prototype: `int(NOTIFICATION_THREAD *__hidden this, struct CONFIG_MONITOR *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800159b4`
- `0x18004ff30`

## callees

- `0x18001c20c`
- `0x180050b70`
- `0x180051190`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050be8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050be8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180050bcb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180050bcb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180050b99`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180050b99`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180050bdd`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180050bdd`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180050b85`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180050b85`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180050c0d`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180050c0d`

## pseudocode

```c
__int64 __fastcall NOTIFICATION_THREAD::AddMonitor(NOTIFICATION_THREAD *this, struct CONFIG_MONITOR *a2)
{
  void *v4; // rcx
  NOTIFICATION_THREAD **v5; // rdx
  signed int DirectoryChanges; // ebx
  NOTIFICATION_THREAD *v7; // rcx
  signed int LastError; // eax

  CReaderWriterLock3::WriteLock((struct CONFIG_MONITOR *)((char *)a2 + 88));
  v4 = (void *)*((_QWORD *)a2 + 3);
  if ( v4 == (void *)-1LL )
  {
    AcquireSRWLockExclusive((PSRWLOCK)this + 1);
    v5 = (NOTIFICATION_THREAD **)*((_QWORD *)this + 3);
    if ( *v5 != (NOTIFICATION_THREAD *)((char *)this + 16) )
      __fastfail(3u);
    DirectoryChanges = 0;
    *((_QWORD *)a2 + 12) = (char *)this + 16;
    *((_QWORD *)a2 + 13) = v5;
    *v5 = (struct CONFIG_MONITOR *)((char *)a2 + 96);
    *((_QWORD *)this + 3) = (char *)a2 + 96;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 1);
    goto LABEL_12;
  }
  if ( CreateIoCompletionPort(v4, *((HANDLE *)this + 6), 0, 0) )
  {
    DirectoryChanges = NOTIFICATION_THREAD::ReadDirectoryChanges(v7, a2);
    if ( DirectoryChanges >= 0 )
    {
LABEL_12:
      *((_DWORD *)a2 + 20) = 0;
      _InterlockedIncrement((volatile signed __int32 *)this + 15);
      goto LABEL_10;
    }
    goto LABEL_9;
  }
  LastError = GetLastError();
  DirectoryChanges = LastError;
  if ( LastError > 0 )
    DirectoryChanges = (unsigned __int16)LastError | 0x80070000;
  if ( DirectoryChanges < 0 )
LABEL_9:
    NOTIFICATION_THREAD::CloseHandles(a2);
LABEL_10:
  CReaderWriterLock3::WriteUnlock((struct CONFIG_MONITOR *)((char *)a2 + 88));
  return (unsigned int)DirectoryChanges;
}

```

## disassembly

```asm
0x180050b70  push    rbx
0x180050b72  push    rbp
0x180050b73  push    rsi
0x180050b74  push    rdi
0x180050b75  push    r14
0x180050b77  sub     rsp, 20h
0x180050b7b  mov     rsi, rcx
0x180050b7e  mov     rdi, rdx
0x180050b81  lea     rcx, [rdx+58h]
0x180050b85  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180050b8b  mov     rcx, [rdi+18h]; FileHandle
0x180050b8f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180050b93  jnz     short loc_180050BD3
0x180050b95  lea     rcx, [rsi+8]; SRWLock
0x180050b99  call    cs:__imp_AcquireSRWLockExclusive
0x180050b9f  lea     rcx, [rsi+10h]
0x180050ba3  mov     rdx, [rcx+8]
0x180050ba7  cmp     [rdx], rcx
0x180050baa  jz      short loc_180050BB3
0x180050bac  mov     ecx, 3
0x180050bb1  int     29h; Win8: RtlFailFast(ecx)
0x180050bb3  lea     rax, [rdi+60h]
0x180050bb7  xor     ebx, ebx
0x180050bb9  mov     [rax], rcx
0x180050bbc  mov     [rax+8], rdx
0x180050bc0  mov     [rdx], rax
0x180050bc3  mov     [rcx+8], rax
0x180050bc7  lea     rcx, [rsi+8]; SRWLock
0x180050bcb  call    cs:__imp_ReleaseSRWLockExclusive
0x180050bd1  jmp     short loc_180050C2E
0x180050bd3  mov     rdx, [rsi+30h]; ExistingCompletionPort
0x180050bd7  xor     r9d, r9d; NumberOfConcurrentThreads
0x180050bda  xor     r8d, r8d; CompletionKey
0x180050bdd  call    cs:__imp_CreateIoCompletionPort
0x180050be3  test    rax, rax
0x180050be6  jnz     short loc_180050C20
0x180050be8  call    cs:__imp_GetLastError
0x180050bee  mov     ebx, eax
0x180050bf0  test    eax, eax
0x180050bf2  jle     short loc_180050BFD
0x180050bf4  movzx   ebx, ax
0x180050bf7  or      ebx, 80070000h
0x180050bfd  test    ebx, ebx
0x180050bff  jns     short loc_180050C09
0x180050c01  mov     rcx, rdi; struct CONFIG_MONITOR *
0x180050c04  call    ?CloseHandles@NOTIFICATION_THREAD@@CAXPEAUCONFIG_MONITOR@@@Z; NOTIFICATION_THREAD::CloseHandles(CONFIG_MONITOR *)
0x180050c09  lea     rcx, [rdi+58h]
0x180050c0d  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180050c13  mov     eax, ebx
0x180050c15  add     rsp, 20h
0x180050c19  pop     r14
0x180050c1b  pop     rdi
0x180050c1c  pop     rsi
0x180050c1d  pop     rbp
0x180050c1e  pop     rbx
0x180050c1f  retn
0x180050c20  mov     rdx, rdi; struct CONFIG_MONITOR *
0x180050c23  call    ?ReadDirectoryChanges@NOTIFICATION_THREAD@@AEAAJPEAUCONFIG_MONITOR@@@Z; NOTIFICATION_THREAD::ReadDirectoryChanges(CONFIG_MONITOR *)
0x180050c28  mov     ebx, eax
0x180050c2a  test    eax, eax
0x180050c2c  js      short loc_180050C01
0x180050c2e  mov     dword ptr [rdi+50h], 0
0x180050c35  lock inc dword ptr [rsi+3Ch]
0x180050c39  jmp     short loc_180050C09
```
