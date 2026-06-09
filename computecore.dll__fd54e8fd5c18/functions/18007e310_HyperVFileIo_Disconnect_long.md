# HyperVFileIo::Disconnect(long)

- ea: `0x18007e310`
- end: `0x18007e395`
- name: `?Disconnect@HyperVFileIo@@UEAAXJ@Z`
- size: `133`
- prototype: `void __fastcall(HyperVFileIo *__hidden this, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180080794`
- `0x180081720`
- `0x18008ff70`

## callees

- `0x18007e1d8`
- `0x18007e310`
- `0x18007ef40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007e352`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007e352`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e35a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e35a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007e32b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007e32b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007e331`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007e331`

## pseudocode

```c
void __fastcall HyperVFileIo::Disconnect(HyperVFileIo *this, int a2)
{
  char *v2; // rbx
  const unsigned __int16 *v5; // rdx
  struct _GUID v6; // [rsp+20h] [rbp-18h] BYREF

  v2 = (char *)this + 24;
  AcquireSRWLockExclusive((PSRWLOCK)this + 3);
  *((_DWORD *)v2 + 2) = GetCurrentThreadId();
  HyperVFileIo::CloseInternal(this);
  if ( *((_DWORD *)v2 + 2) )
  {
    *((_DWORD *)v2 + 2) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v2);
  }
  else
  {
    ReleaseSRWLockShared((PSRWLOCK)v2);
  }
  v5 = (const unsigned __int16 *)((char *)this + 40);
  if ( *((_QWORD *)this + 8) > 7u )
    v5 = *(const unsigned __int16 **)v5;
  v6 = *(struct _GUID *)((char *)this + 8);
  HyperVStorageTrace::HyperVFileIo_Disconnect(&v6, v5, a2);
}

```

## disassembly

```asm
0x18007e310  mov     [rsp+arg_0], rbx
0x18007e315  mov     [rsp+arg_8], rsi
0x18007e31a  push    rdi
0x18007e31b  sub     rsp, 30h
0x18007e31f  lea     rbx, [rcx+18h]
0x18007e323  mov     rdi, rcx
0x18007e326  mov     rcx, rbx; SRWLock
0x18007e329  mov     esi, edx
0x18007e32b  call    cs:__imp_AcquireSRWLockExclusive
0x18007e331  call    cs:__imp_GetCurrentThreadId
0x18007e337  mov     rcx, rdi; this
0x18007e33a  mov     [rbx+8], eax
0x18007e33d  call    ?CloseInternal@HyperVFileIo@@AEAAXXZ; HyperVFileIo::CloseInternal(void)
0x18007e342  cmp     dword ptr [rbx+8], 0
0x18007e346  mov     rcx, rbx; SRWLock
0x18007e349  jz      short loc_18007E35A
0x18007e34b  mov     dword ptr [rbx+8], 0
0x18007e352  call    cs:__imp_ReleaseSRWLockExclusive
0x18007e358  jmp     short loc_18007E360
0x18007e35a  call    cs:__imp_ReleaseSRWLockShared
0x18007e360  lea     rdx, [rdi+28h]
0x18007e364  cmp     qword ptr [rdx+18h], 7
0x18007e369  jbe     short loc_18007E36E
0x18007e36b  mov     rdx, [rdx]; unsigned __int16 *
0x18007e36e  movups  xmm0, xmmword ptr [rdi+8]
0x18007e372  mov     r8d, esi; int
0x18007e375  lea     rcx, [rsp+38h+var_18]; struct _GUID
0x18007e37a  movdqu  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x18007e380  call    ?HyperVFileIo_Disconnect@HyperVStorageTrace@@SAXU_GUID@@PEBGJ@Z; HyperVStorageTrace::HyperVFileIo_Disconnect(_GUID,ushort const *,long)
0x18007e385  mov     rbx, [rsp+38h+arg_0]
0x18007e38a  mov     rsi, [rsp+38h+arg_8]
0x18007e38f  add     rsp, 30h
0x18007e393  pop     rdi
0x18007e394  retn
```
