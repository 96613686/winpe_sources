# CLock::ReadLock(ulong)

- ea: `0x1800037a0`
- end: `0x1800038b3`
- name: `?ReadLock@CLock@@QEAAHK@Z`
- size: `275`
- prototype: `__int64 __fastcall(CLock *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800032a0`
- `0x180022620`
- `0x180031270`

## callees

- `0x1800037a0`
- `0x1800038c0`
- `0x18001e1cc`
- `0x180027724`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000388b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000388b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180003811`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180003811`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003827`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003837`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003827`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003837`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003817`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003817`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLock::ReadLock(CLock *this)
{
  DWORD CurrentThreadId; // ebp
  CLock *v3; // rcx
  unsigned int v4; // r8d
  char v5; // al
  int v6; // ecx
  __int64 v7; // rax
  unsigned int v9; // esi

  GetCurrentThreadId();
  CurrentThreadId = GetCurrentThreadId();
  if ( !CriticalSection::acquire_write((CLock *)((char *)this + 16)) )
    return 1;
  GetCurrentThreadId();
  if ( *(_DWORD *)this && (v9 = CLock::WaitFor(v3, *((void **)this + 15), v4)) != 0 )
  {
    CriticalSection::release((CLock *)((char *)this + 16));
    return v9;
  }
  else
  {
    GetCurrentThreadId();
    v5 = CriticalSection::acquire_write((CLock *)((char *)this + 64));
    v6 = *((_DWORD *)this + 1);
    if ( v5 )
    {
      *((_DWORD *)this + 1) = v6 + 1;
      v7 = *((unsigned int *)this + 33);
      if ( (unsigned int)v7 < 0x10 )
      {
        *((_DWORD *)this + v7 + 34) = CurrentThreadId;
        ++*((_DWORD *)this + 33);
      }
      ResetEvent(*((HANDLE *)this + 14));
      GetCurrentThreadId();
      if ( *((_BYTE *)this + 104) )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
      if ( *((_BYTE *)this + 56) )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      return 0;
    }
    else if ( v6 || (*((_DWORD *)this + 33) = 0, SetEvent(*((HANDLE *)this + 14))) )
    {
      CriticalSection::release((CLock *)((char *)this + 16));
      return 1;
    }
    else
    {
      CriticalSection::release((CLock *)((char *)this + 16));
      return 2;
    }
  }
}

```

## disassembly

```asm
0x1800037a0  push    rbx
0x1800037a2  push    rbp
0x1800037a3  push    rsi
0x1800037a4  push    rdi
0x1800037a5  sub     rsp, 38h
0x1800037a9  mov     rbx, rcx
0x1800037ac  call    cs:__imp_GetCurrentThreadId
0x1800037b2  call    cs:__imp_GetCurrentThreadId
0x1800037b8  mov     ebp, eax
0x1800037ba  lea     rdi, [rbx+10h]
0x1800037be  mov     [rsp+58h+var_38], rdi
0x1800037c3  mov     rcx, rdi; this
0x1800037c6  call    ?acquire_write@CriticalSection@@QEAA_NXZ; CriticalSection::acquire_write(void)
0x1800037cb  mov     [rsp+58h+var_30], al
0x1800037cf  test    al, al
0x1800037d1  jz      loc_180003857
0x1800037d7  call    cs:__imp_GetCurrentThreadId
0x1800037dd  cmp     dword ptr [rbx], 0
0x1800037e0  jnz     short loc_18000385E
0x1800037e2  call    cs:__imp_GetCurrentThreadId
0x1800037e8  lea     rcx, [rbx+40h]; this
0x1800037ec  call    ?acquire_write@CriticalSection@@QEAA_NXZ; CriticalSection::acquire_write(void)
0x1800037f1  mov     ecx, [rbx+4]
0x1800037f4  test    al, al
0x1800037f6  jz      loc_18000387D
0x1800037fc  lea     eax, [rcx+1]
0x1800037ff  mov     [rbx+4], eax
0x180003802  mov     eax, [rbx+84h]
0x180003808  cmp     eax, 10h
0x18000380b  jb      short loc_180003848
0x18000380d  mov     rcx, [rbx+70h]; hEvent
0x180003811  call    cs:__imp_ResetEvent
0x180003817  call    cs:__imp_GetCurrentThreadId
0x18000381d  cmp     byte ptr [rbx+68h], 0
0x180003821  jz      short loc_18000382E
0x180003823  lea     rcx, [rbx+40h]; lpCriticalSection
0x180003827  call    cs:__imp_LeaveCriticalSection
0x18000382d  nop
0x18000382e  cmp     byte ptr [rdi+28h], 0
0x180003832  jz      short loc_18000383D
0x180003834  mov     rcx, rdi; lpCriticalSection
0x180003837  call    cs:__imp_LeaveCriticalSection
0x18000383d  xor     eax, eax
0x18000383f  add     rsp, 38h
0x180003843  pop     rdi
0x180003844  pop     rsi
0x180003845  pop     rbp
0x180003846  pop     rbx
0x180003847  retn
0x180003848  mov     [rbx+rax*4+88h], ebp
0x18000384f  inc     dword ptr [rbx+84h]
0x180003855  jmp     short loc_18000380D
0x180003857  mov     eax, 1
0x18000385c  jmp     short loc_18000383F
0x18000385e  mov     rdx, [rbx+78h]; void *
0x180003862  call    ?WaitFor@CLock@@IEAAHPEAXK@Z; CLock::WaitFor(void *,ulong)
0x180003867  mov     esi, eax
0x180003869  test    eax, eax
0x18000386b  jz      loc_1800037E2
0x180003871  mov     rcx, rdi; this
0x180003874  call    ?release@CriticalSection@@QEAA_NXZ; CriticalSection::release(void)
0x180003879  mov     eax, esi
0x18000387b  jmp     short loc_18000383F
0x18000387d  test    ecx, ecx
0x18000387f  jnz     short loc_1800038A4
0x180003881  mov     [rbx+84h], ecx
0x180003887  mov     rcx, [rbx+70h]; hEvent
0x18000388b  call    cs:__imp_SetEvent
0x180003891  test    eax, eax
0x180003893  jnz     short loc_1800038A4
0x180003895  mov     rcx, rdi; this
0x180003898  call    ?release@CriticalSection@@QEAA_NXZ; CriticalSection::release(void)
0x18000389d  mov     eax, 2
0x1800038a2  jmp     short loc_18000383F
0x1800038a4  mov     rcx, rdi; this
0x1800038a7  call    ?release@CriticalSection@@QEAA_NXZ; CriticalSection::release(void)
0x1800038ac  mov     eax, 1
0x1800038b1  jmp     short loc_18000383F
```
