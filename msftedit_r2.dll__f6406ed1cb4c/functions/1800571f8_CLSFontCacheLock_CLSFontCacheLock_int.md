# CLSFontCacheLock::CLSFontCacheLock(int)

- ea: `0x1800571f8`
- end: `0x1800572c7`
- name: `??0CLSFontCacheLock@@QEAA@H@Z`
- size: `207`
- prototype: `CLSFontCacheLock *__fastcall(CLSFontCacheLock *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800dd21c`
- `0x1800de2e8`

## callees

- `0x1800571f8`
- `0x180057560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180057280`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180057280`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005721c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005728c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005721c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005728c`

## pseudocode

```c
CLSFontCacheLock *__fastcall CLSFontCacheLock::CLSFontCacheLock(CLSFontCacheLock *this, int a2)
{
  int v2; // edi
  struct LOCK_TELEMETRY near **v5; // rax
  int v6; // eax
  RTL_SRWLOCK *Lock; // rax
  DWORD CurrentThreadId; // eax
  bool v10; // cc
  __int64 v11; // rcx
  __int64 v12; // rcx

  v2 = (int)CLockSharedData::LockOwner;
  *(_DWORD *)this = 0;
  if ( v2 && v2 == GetCurrentThreadId() )
  {
    if ( *(_DWORD *)this > 3u )
      v5 = 0;
    else
      v5 = &CLockSharedData::LockTelemetry + 2 * *(int *)this;
    ++*(_DWORD *)v5;
  }
  else
  {
    Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(*(unsigned int *)this);
    AcquireSRWLockExclusive(Lock);
    CurrentThreadId = GetCurrentThreadId();
    v10 = *(_DWORD *)this <= 3u;
    v11 = *(int *)this;
    *((_DWORD *)&CLockSharedData::LockOwner + v11) = CurrentThreadId;
    if ( v10 )
      v12 = (__int64)&dword_1802E474C[4 * v11];
    else
      v12 = 4;
    ++*(_DWORD *)v12;
  }
  ++CLSLock::_cOLSBusy;
  *((_BYTE *)this + 4) = 1;
  v6 = a2 != 0;
  g_cFCLock += v6;
  *((_DWORD *)this + 2) = v6;
  return this;
}

```

## disassembly

```asm
0x1800571f8  mov     [rsp+arg_0], rbx
0x1800571fd  mov     [rsp+arg_8], rsi
0x180057202  push    rdi
0x180057203  sub     rsp, 20h
0x180057207  mov     edi, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x18005720d  mov     esi, edx
0x18005720f  mov     dword ptr [rcx], 0
0x180057215  mov     rbx, rcx
0x180057218  test    edi, edi
0x18005721a  jz      short loc_180057276
0x18005721c  call    cs:__imp_GetCurrentThreadId
0x180057223  nop     dword ptr [rax+rax+00h]
0x180057228  cmp     edi, eax
0x18005722a  jnz     short loc_180057276
0x18005722c  cmp     dword ptr [rbx], 3
0x18005722f  ja      loc_1800572BC
0x180057235  movsxd  rax, dword ptr [rbx]
0x180057238  lea     rcx, ?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x18005723f  shl     rax, 4
0x180057243  add     rax, rcx
0x180057246  inc     dword ptr [rax]
0x180057248  inc     cs:?_cOLSBusy@CLSLock@@1HA; int CLSLock::_cOLSBusy
0x18005724e  xor     eax, eax
0x180057250  test    esi, esi
0x180057252  mov     byte ptr [rbx+4], 1
0x180057256  mov     rsi, [rsp+28h+arg_8]
0x18005725b  setnz   al
0x18005725e  add     cs:?g_cFCLock@@3JA, eax; long g_cFCLock
0x180057264  mov     [rbx+8], eax
0x180057267  mov     rax, rbx
0x18005726a  mov     rbx, [rsp+28h+arg_0]
0x18005726f  add     rsp, 20h
0x180057273  pop     rdi
0x180057274  retn
0x180057276  mov     ecx, [rbx]
0x180057278  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x18005727d  mov     rcx, rax; SRWLock
0x180057280  call    cs:__imp_AcquireSRWLockExclusive
0x180057287  nop     dword ptr [rax+rax+00h]
0x18005728c  call    cs:__imp_GetCurrentThreadId
0x180057293  nop     dword ptr [rax+rax+00h]
0x180057298  cmp     dword ptr [rbx], 3
0x18005729b  lea     rdx, ?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x1800572a2  movsxd  rcx, dword ptr [rbx]
0x1800572a5  mov     [rdx+rcx*4], eax
0x1800572a8  ja      short loc_1800572C0
0x1800572aa  shl     rcx, 4
0x1800572ae  lea     rax, dword_1802E474C
0x1800572b5  add     rcx, rax
0x1800572b8  inc     dword ptr [rcx]
0x1800572ba  jmp     short loc_180057248
0x1800572bc  xor     eax, eax
0x1800572be  jmp     short loc_180057246
0x1800572c0  mov     ecx, 4
0x1800572c5  jmp     short loc_1800572B8
```
