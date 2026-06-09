# CFICache::GetFontName(short)

- ea: `0x180034728`
- end: `0x180034812`
- name: `?GetFontName@CFICache@@SAPEBGF@Z`
- size: `234`
- prototype: `const unsigned __int16 *__fastcall(__int16)`
- caller_count: `31`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d5e8`
- `0x18000f800`
- `0x180011030`
- `0x18001b720`
- `0x180027500`
- `0x18003098c`
- `0x180032968`
- `0x180034640`
- `0x180044334`
- `0x1800448b4`
- `0x1800586d0`
- `0x18008ebf4`
- `0x18009c09c`
- `0x1800ab71c`
- `0x1800aca44`
- `0x1800ae144`
- `0x1800ae828`
- `0x1800b6598`
- `0x1800e20ac`
- `0x18011ab14`
- `0x180124200`
- `0x18012e9b8`
- `0x1801312dc`
- `0x18014853c`
- `0x1801504ac`
- `0x180157550`
- `0x180185d30`
- `0x180189d50`
- `0x1801a0640`
- `0x1801a0cd8`
- `0x18020983c`

## callees

- `0x180034728`
- `0x180057560`
- `0x18005912c`
- `0x18005921c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800347dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800347dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034767`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800347e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034767`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800347e8`

## pseudocode

```c
const unsigned __int16 *__fastcall CFICache::GetFontName(__int16 a1)
{
  __int64 v1; // rbx
  int v2; // edi
  _DWORD *LockTelemetry; // rax
  __int64 v4; // rbx
  RTL_SRWLOCK *Lock; // rax
  __int64 v7; // rax
  int v8; // [rsp+50h] [rbp+8h] BYREF

  v1 = a1;
  if ( a1 < 0 || a1 >= CFICache::_cFontInfo + 70 )
    return 0;
  if ( a1 < 70 )
    return (&off_1802809D0)[a1];
  v2 = (int)CLockSharedData::LockOwner;
  v8 = 0;
  if ( (_DWORD)CLockSharedData::LockOwner && v2 == GetCurrentThreadId() )
  {
    LockTelemetry = (_DWORD *)CLock::GetLockTelemetry(0);
    ++*LockTelemetry;
  }
  else
  {
    Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
    AcquireSRWLockExclusive(Lock);
    LODWORD(CLockSharedData::LockOwner) = GetCurrentThreadId();
    v7 = CLock::GetLockTelemetry(0);
    ++*(_DWORD *)(v7 + 4);
  }
  if ( (__int16)(v1 - 70) >= CFICache::_cFontInfo )
    v4 = 0;
  else
    v4 = *((_QWORD *)CFICache::_pFontInfo + 7 * v1 - 484);
  CWriteLock::~CWriteLock((CWriteLock *)&v8);
  return (const unsigned __int16 *)v4;
}

```

## disassembly

```asm
0x180034728  push    rbx
0x18003472a  push    rbp
0x18003472b  push    rsi
0x18003472c  push    rdi
0x18003472d  sub     rsp, 28h
0x180034731  movsx   rbx, cx
0x180034735  xor     esi, esi
0x180034737  test    bx, bx
0x18003473a  js      loc_18003480E
0x180034740  movsx   edx, cs:?_cFontInfo@CFICache@@0FA; short CFICache::_cFontInfo
0x180034747  lea     ebp, [rsi+46h]
0x18003474a  add     edx, ebp
0x18003474c  cmp     ebx, edx
0x18003474e  jge     loc_18003480E
0x180034754  cmp     bx, bp
0x180034757  jl      short loc_1800347C5
0x180034759  mov     edi, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x18003475f  mov     [rsp+48h+arg_0], esi
0x180034763  test    edi, edi
0x180034765  jz      short loc_1800347D2
0x180034767  call    cs:__imp_GetCurrentThreadId
0x18003476e  nop     dword ptr [rax+rax+00h]
0x180034773  cmp     edi, eax
0x180034775  jnz     short loc_1800347D2
0x180034777  xor     ecx, ecx
0x180034779  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x18003477e  inc     dword ptr [rax]
0x180034780  mov     edx, cs:?g_cFCLock@@3JA; long g_cFCLock
0x180034786  movzx   eax, bx
0x180034789  sub     ax, bp
0x18003478c  cmp     ax, cs:?_cFontInfo@CFICache@@0FA; short CFICache::_cFontInfo
0x180034793  jge     short loc_180034809
0x180034795  mov     rax, cs:?_pFontInfo@CFICache@@0PEAUFONTINFOEX@@EA; FONTINFOEX * CFICache::_pFontInfo
0x18003479c  imul    rcx, rbx, 38h ; '8'
0x1800347a0  mov     rbx, [rcx+rax-0F20h]
0x1800347a8  lea     rcx, [rsp+48h+arg_0]; this
0x1800347ad  mov     cs:?g_cFCLock@@3JA, edx; long g_cFCLock
0x1800347b3  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x1800347b8  mov     rax, rbx
0x1800347bb  add     rsp, 28h
0x1800347bf  pop     rdi
0x1800347c0  pop     rsi
0x1800347c1  pop     rbp
0x1800347c2  pop     rbx
0x1800347c3  retn
0x1800347c5  lea     rcx, off_1802809D0; "Arial"
0x1800347cc  mov     rax, [rcx+rbx*8]
0x1800347d0  jmp     short loc_1800347BB
0x1800347d2  xor     ecx, ecx
0x1800347d4  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x1800347d9  mov     rcx, rax; SRWLock
0x1800347dc  call    cs:__imp_AcquireSRWLockExclusive
0x1800347e3  nop     dword ptr [rax+rax+00h]
0x1800347e8  call    cs:__imp_GetCurrentThreadId
0x1800347ef  nop     dword ptr [rax+rax+00h]
0x1800347f4  xor     ecx, ecx
0x1800347f6  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x1800347fc  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180034801  inc     dword ptr [rax+4]
0x180034804  jmp     loc_180034780
0x180034809  mov     rbx, rsi
0x18003480c  jmp     short loc_1800347A8
0x18003480e  xor     eax, eax
0x180034810  jmp     short loc_1800347BB
```
