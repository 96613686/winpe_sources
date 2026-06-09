# CFICache::GetFontEMSquare(short)

- ea: `0x180055b34`
- end: `0x180055c2a`
- name: `?GetFontEMSquare@CFICache@@SAGF@Z`
- size: `246`
- prototype: `unsigned __int16 __fastcall(__int16)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ea0c`
- `0x18000f800`
- `0x180012a58`
- `0x180045018`
- `0x18005682c`

## callees

- `0x180055b34`
- `0x180057560`
- `0x18005912c`
- `0x18005921c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180055bf2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180055bf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180055b79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180055bfe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180055b79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180055bfe`

## pseudocode

```c
__int16 __fastcall CFICache::GetFontEMSquare(__int16 a1)
{
  __int64 v1; // rbx
  int v2; // edi
  _DWORD *LockTelemetry; // rax
  __int16 v4; // bx
  __int16 result; // ax
  RTL_SRWLOCK *Lock; // rax
  __int64 v7; // rax
  int v8; // [rsp+30h] [rbp+8h] BYREF

  v1 = a1;
  if ( a1 < 0 || a1 >= CFICache::_cFontInfo + 70 )
    return 0;
  if ( a1 < 70 )
  {
    result = qword_1802E29D8[6 * a1];
    if ( !result )
      return 2048;
  }
  else
  {
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
    v4 = *((_WORD *)CFICache::_pFontInfo + 28 * v1 - 1940);
    CWriteLock::~CWriteLock((CWriteLock *)&v8);
    if ( v4 )
      return v4;
    else
      return 2048;
  }
  return result;
}

```

## disassembly

```asm
0x180055b34  mov     [rsp+arg_8], rbx
0x180055b39  mov     [rsp+arg_10], rsi
0x180055b3e  push    rdi
0x180055b3f  sub     rsp, 20h
0x180055b43  movsx   rbx, cx
0x180055b47  xor     esi, esi
0x180055b49  test    bx, bx
0x180055b4c  js      loc_180055C26
0x180055b52  movsx   edx, cs:?_cFontInfo@CFICache@@0FA; short CFICache::_cFontInfo
0x180055b59  lea     ecx, [rsi+46h]
0x180055b5c  add     edx, ecx
0x180055b5e  cmp     ebx, edx
0x180055b60  jge     loc_180055C26
0x180055b66  cmp     bx, cx
0x180055b69  jl      short loc_180055BC8
0x180055b6b  mov     edi, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x180055b71  mov     [rsp+28h+arg_0], esi
0x180055b75  test    edi, edi
0x180055b77  jz      short loc_180055BE8
0x180055b79  call    cs:__imp_GetCurrentThreadId
0x180055b80  nop     dword ptr [rax+rax+00h]
0x180055b85  cmp     edi, eax
0x180055b87  jnz     short loc_180055BE8
0x180055b89  xor     ecx, ecx
0x180055b8b  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180055b90  inc     dword ptr [rax]
0x180055b92  mov     rax, cs:?_pFontInfo@CFICache@@0PEAUFONTINFOEX@@EA; FONTINFOEX * CFICache::_pFontInfo
0x180055b99  imul    rcx, rbx, 38h ; '8'
0x180055b9d  movzx   ebx, word ptr [rcx+rax-0F28h]
0x180055ba5  lea     rcx, [rsp+28h+arg_0]; this
0x180055baa  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x180055baf  test    bx, bx
0x180055bb2  jz      short loc_180055C1F
0x180055bb4  movzx   eax, bx
0x180055bb7  mov     rbx, [rsp+28h+arg_8]
0x180055bbc  mov     rsi, [rsp+28h+arg_10]
0x180055bc1  add     rsp, 20h
0x180055bc5  pop     rdi
0x180055bc6  retn
0x180055bc8  lea     rcx, [rbx+rbx*2]
0x180055bcc  add     rcx, rcx
0x180055bcf  lea     rax, qword_1802E29D8
0x180055bd6  movzx   eax, word ptr [rax+rcx*8]
0x180055bda  mov     ecx, 800h
0x180055bdf  test    ax, ax
0x180055be2  cmovz   ax, cx
0x180055be6  jmp     short loc_180055BB7
0x180055be8  xor     ecx, ecx
0x180055bea  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x180055bef  mov     rcx, rax; SRWLock
0x180055bf2  call    cs:__imp_AcquireSRWLockExclusive
0x180055bf9  nop     dword ptr [rax+rax+00h]
0x180055bfe  call    cs:__imp_GetCurrentThreadId
0x180055c05  nop     dword ptr [rax+rax+00h]
0x180055c0a  xor     ecx, ecx
0x180055c0c  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x180055c12  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180055c17  inc     dword ptr [rax+4]
0x180055c1a  jmp     loc_180055B92
0x180055c1f  mov     eax, 800h
0x180055c24  jmp     short loc_180055BB7
0x180055c26  mov     eax, esi
0x180055c28  jmp     short loc_180055BB7
```
