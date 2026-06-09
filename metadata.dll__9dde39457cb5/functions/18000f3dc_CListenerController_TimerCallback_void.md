# CListenerController::TimerCallback(void)

- ea: `0x18000f3dc`
- end: `0x18000f45e`
- name: `?TimerCallback@CListenerController@@AEAAJXZ`
- size: `130`
- prototype: `__int64 __fastcall(CListenerController *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f470`

## callees

- `0x18000eea0`
- `0x18000f128`
- `0x18000f3dc`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000f3ff`
- `KERNEL32!EnterCriticalSection` at `0x18000f3ff`
- `IisRTL!RemoveWorkItem` at `0x18000f438`
- `IisRTL!RemoveWorkItem` at `0x18000f438`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f429`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f429`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f412`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f412`

## pseudocode

```c
__int64 __fastcall CListenerController::TimerCallback(CListenerController *this)
{
  int v2; // ebx
  int v4; // [rsp+20h] [rbp-18h] BYREF
  char *v5; // [rsp+28h] [rbp-10h]

  v2 = 1;
  v4 = 1;
  v5 = (char *)this + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( *((_DWORD *)this + 2) == 3 )
  {
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
    v2 = CListenerController::Start(this);
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
    if ( v2 >= 0 )
    {
      if ( !v2 )
      {
        RemoveWorkItem(*((_DWORD *)this + 22));
        *((_DWORD *)this + 22) = 0;
      }
      v2 = 0;
    }
  }
  CLock::~CLock((CLock *)&v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000f3dc  mov     [rsp+arg_0], rbx
0x18000f3e1  push    rdi
0x18000f3e2  sub     rsp, 30h
0x18000f3e6  mov     rdi, rcx
0x18000f3e9  mov     ebx, 1
0x18000f3ee  add     rcx, 10h
0x18000f3f2  mov     [rsp+38h+var_18], ebx
0x18000f3f6  mov     [rsp+38h+var_10], rcx
0x18000f3fb  add     rcx, 8; lpCriticalSection
0x18000f3ff  call    cs:__imp_EnterCriticalSection
0x18000f405  cmp     dword ptr [rdi+8], 3
0x18000f409  jnz     short loc_18000F447
0x18000f40b  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18000f412  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000f418  mov     rcx, rdi; this
0x18000f41b  call    ?Start@CListenerController@@QEAAJXZ; CListenerController::Start(void)
0x18000f420  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18000f427  mov     ebx, eax
0x18000f429  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000f42f  test    ebx, ebx
0x18000f431  js      short loc_18000F447
0x18000f433  jnz     short loc_18000F445
0x18000f435  mov     ecx, [rdi+58h]
0x18000f438  call    cs:__imp_?RemoveWorkItem@@YAHK@Z; RemoveWorkItem(ulong)
0x18000f43e  mov     dword ptr [rdi+58h], 0
0x18000f445  xor     ebx, ebx
0x18000f447  lea     rcx, [rsp+38h+var_18]; this
0x18000f44c  call    ??1CLock@@QEAA@XZ; CLock::~CLock(void)
0x18000f451  mov     eax, ebx
0x18000f453  mov     rbx, [rsp+38h+arg_0]
0x18000f458  add     rsp, 30h
0x18000f45c  pop     rdi
0x18000f45d  retn
```
