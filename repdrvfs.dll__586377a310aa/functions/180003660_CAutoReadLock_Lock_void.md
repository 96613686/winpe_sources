# CAutoReadLock::Lock(void)

- ea: `0x180003660`
- end: `0x180003799`
- name: `?Lock@CAutoReadLock@@QEAA_NXZ`
- size: `313`
- prototype: `bool __fastcall(CAutoReadLock *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180002af0`
- `0x1800038f0`
- `0x180003bc0`

## callees

- `0x180003660`
- `0x1800038c0`
- `0x18001e1cc`
- `0x180027724`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000376e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000376e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800036e5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800036e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800036fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000370b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800036fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000370b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000367b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003681`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000367b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003681`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall CAutoReadLock::Lock(CAutoReadLock *this)
{
  __int64 v2; // rdi
  DWORD CurrentThreadId; // r14d
  CLock *v4; // rcx
  unsigned int v5; // r8d
  char v6; // al
  int v7; // ecx
  __int64 v8; // rax
  int v9; // ebp
  BOOL v10; // eax

  if ( *((_DWORD *)this + 2) )
  {
    LOBYTE(v10) = 0;
  }
  else
  {
    v2 = *(_QWORD *)this;
    GetCurrentThreadId();
    CurrentThreadId = GetCurrentThreadId();
    if ( CriticalSection::acquire_write((CriticalSection *)(v2 + 16)) )
    {
      GetCurrentThreadId();
      if ( *(_DWORD *)v2 && (v9 = CLock::WaitFor(v4, *(void **)(v2 + 120), v5)) != 0 )
      {
        CriticalSection::release((CriticalSection *)(v2 + 16));
      }
      else
      {
        GetCurrentThreadId();
        v6 = CriticalSection::acquire_write((CriticalSection *)(v2 + 64));
        v7 = *(_DWORD *)(v2 + 4);
        if ( v6 )
        {
          *(_DWORD *)(v2 + 4) = v7 + 1;
          v8 = *(unsigned int *)(v2 + 132);
          if ( (unsigned int)v8 < 0x10 )
          {
            *(_DWORD *)(v2 + 4 * v8 + 136) = CurrentThreadId;
            ++*(_DWORD *)(v2 + 132);
          }
          ResetEvent(*(HANDLE *)(v2 + 112));
          GetCurrentThreadId();
          if ( *(_BYTE *)(v2 + 104) )
            LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 64));
          if ( *(_BYTE *)(v2 + 56) )
            LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 16));
          v9 = 0;
        }
        else if ( v7 || (*(_DWORD *)(v2 + 132) = 0, SetEvent(*(HANDLE *)(v2 + 112))) )
        {
          CriticalSection::release((CriticalSection *)(v2 + 16));
          v9 = 1;
        }
        else
        {
          CriticalSection::release((CriticalSection *)(v2 + 16));
          v9 = 2;
        }
      }
    }
    else
    {
      v9 = 1;
    }
    v10 = v9 == 0;
    *((_DWORD *)this + 2) = v10;
  }
  return v10;
}

```

## disassembly

```asm
0x180003660  push    rbx
0x180003662  push    rbp
0x180003663  push    rsi
0x180003664  push    rdi
0x180003665  push    r14
0x180003667  sub     rsp, 30h
0x18000366b  mov     rbx, rcx
0x18000366e  cmp     dword ptr [rcx+8], 0
0x180003672  jnz     loc_180003728
0x180003678  mov     rdi, [rcx]
0x18000367b  call    cs:__imp_GetCurrentThreadId
0x180003681  call    cs:__imp_GetCurrentThreadId
0x180003687  mov     r14d, eax
0x18000368a  lea     rsi, [rdi+10h]
0x18000368e  mov     [rsp+58h+var_38], rsi
0x180003693  mov     rcx, rsi; this
0x180003696  call    ?acquire_write@CriticalSection@@QEAA_NXZ; CriticalSection::acquire_write(void)
0x18000369b  mov     [rsp+58h+var_30], al
0x18000369f  test    al, al
0x1800036a1  jz      loc_18000373C
0x1800036a7  call    cs:__imp_GetCurrentThreadId
0x1800036ad  cmp     dword ptr [rdi], 0
0x1800036b0  jnz     loc_180003743
0x1800036b6  call    cs:__imp_GetCurrentThreadId
0x1800036bc  lea     rcx, [rdi+40h]; this
0x1800036c0  call    ?acquire_write@CriticalSection@@QEAA_NXZ; CriticalSection::acquire_write(void)
0x1800036c5  mov     ecx, [rdi+4]
0x1800036c8  test    al, al
0x1800036ca  jz      loc_180003760
0x1800036d0  lea     eax, [rcx+1]
0x1800036d3  mov     [rdi+4], eax
0x1800036d6  mov     eax, [rdi+84h]
0x1800036dc  cmp     eax, 10h
0x1800036df  jb      short loc_18000372C
0x1800036e1  mov     rcx, [rdi+70h]; hEvent
0x1800036e5  call    cs:__imp_ResetEvent
0x1800036eb  call    cs:__imp_GetCurrentThreadId
0x1800036f1  cmp     byte ptr [rdi+68h], 0
0x1800036f5  jz      short loc_180003702
0x1800036f7  lea     rcx, [rdi+40h]; lpCriticalSection
0x1800036fb  call    cs:__imp_LeaveCriticalSection
0x180003701  nop
0x180003702  cmp     byte ptr [rsi+28h], 0
0x180003706  jz      short loc_180003711
0x180003708  mov     rcx, rsi; lpCriticalSection
0x18000370b  call    cs:__imp_LeaveCriticalSection
0x180003711  xor     ebp, ebp
0x180003713  xor     eax, eax
0x180003715  test    ebp, ebp
0x180003717  setz    al
0x18000371a  mov     [rbx+8], eax
0x18000371d  add     rsp, 30h
0x180003721  pop     r14
0x180003723  pop     rdi
0x180003724  pop     rsi
0x180003725  pop     rbp
0x180003726  pop     rbx
0x180003727  retn
0x180003728  xor     al, al
0x18000372a  jmp     short loc_18000371D
0x18000372c  mov     [rdi+rax*4+88h], r14d
0x180003734  inc     dword ptr [rdi+84h]
0x18000373a  jmp     short loc_1800036E1
0x18000373c  mov     ebp, 1
0x180003741  jmp     short loc_180003713
0x180003743  mov     rdx, [rdi+78h]; void *
0x180003747  call    ?WaitFor@CLock@@IEAAHPEAXK@Z; CLock::WaitFor(void *,ulong)
0x18000374c  mov     ebp, eax
0x18000374e  test    eax, eax
0x180003750  jz      loc_1800036B6
0x180003756  mov     rcx, rsi; this
0x180003759  call    ?release@CriticalSection@@QEAA_NXZ; CriticalSection::release(void)
0x18000375e  jmp     short loc_180003713
0x180003760  test    ecx, ecx
0x180003762  jnz     short loc_180003787
0x180003764  mov     [rdi+84h], ecx
0x18000376a  mov     rcx, [rdi+70h]; hEvent
0x18000376e  call    cs:__imp_SetEvent
0x180003774  test    eax, eax
0x180003776  jnz     short loc_180003787
0x180003778  mov     rcx, rsi; this
0x18000377b  call    ?release@CriticalSection@@QEAA_NXZ; CriticalSection::release(void)
0x180003780  mov     ebp, 2
0x180003785  jmp     short loc_180003713
0x180003787  mov     rcx, rsi; this
0x18000378a  call    ?release@CriticalSection@@QEAA_NXZ; CriticalSection::release(void)
0x18000378f  mov     ebp, 1
0x180003794  jmp     loc_180003713
```
