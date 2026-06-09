# CLock::WriteLock(ulong)

- ea: `0x18001d258`
- end: `0x18001d32d`
- name: `?WriteLock@CLock@@QEAAHK@Z`
- size: `213`
- prototype: `__int64 __fastcall(CLock *__hidden this, unsigned int)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c950`
- `0x18001cc50`
- `0x180026248`
- `0x1800313b0`
- `0x18003b450`
- `0x18003d1c0`

## callees

- `0x1800038c0`
- `0x18001d258`
- `0x18001e1cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d29a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d29a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d2bb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d2bb`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001d2df`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001d2e9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001d2df`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001d2e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d264`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d28d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d2a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d2c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d2ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d313`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d264`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d28d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d2a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d2c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d2ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d313`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLock::WriteLock(HANDLE *this)
{
  DWORD v3; // eax
  unsigned int v4; // ebx

  GetCurrentThreadId();
  if ( !CriticalSection::acquire_write((CriticalSection *)(this + 2)) )
    return 1;
  GetCurrentThreadId();
  v3 = WaitForSingleObject(this[14], 0xFFFFFFFF);
  if ( v3 )
  {
    v4 = 1;
    if ( v3 != 258 )
      v4 = 2;
    GetCurrentThreadId();
  }
  else
  {
    GetCurrentThreadId();
    if ( CriticalSection::acquire_write((CriticalSection *)(this + 8)) )
    {
      *((_DWORD *)this + 32) = GetCurrentThreadId();
      ++*(_DWORD *)this;
      ResetEvent(this[14]);
      ResetEvent(this[15]);
      GetCurrentThreadId();
      CriticalSection::release((CriticalSection *)(this + 8));
      v4 = 0;
    }
    else
    {
      SetEvent(this[14]);
      v4 = 1;
    }
  }
  CriticalSection::release((CriticalSection *)(this + 2));
  return v4;
}

```

## disassembly

```asm
0x18001d258  push    rbx
0x18001d25a  push    rbp
0x18001d25b  push    rsi
0x18001d25c  push    rdi
0x18001d25d  sub     rsp, 38h
0x18001d261  mov     rdi, rcx
0x18001d264  call    cs:__imp_GetCurrentThreadId
0x18001d26a  lea     rsi, [rdi+10h]
0x18001d26e  mov     [rsp+58h+var_38], rsi
0x18001d273  mov     rcx, rsi; this
0x18001d276  call    ?acquire_write@CriticalSection@@QEAA_NXZ; CriticalSection::acquire_write(void)
0x18001d27b  mov     [rsp+58h+var_30], al
0x18001d27f  test    al, al
0x18001d281  jnz     short loc_18001D28D
0x18001d283  mov     eax, 1
0x18001d288  jmp     loc_18001D324
0x18001d28d  call    cs:__imp_GetCurrentThreadId
0x18001d293  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001d296  mov     rcx, [rdi+70h]; hHandle
0x18001d29a  call    cs:__imp_WaitForSingleObject
0x18001d2a0  test    eax, eax
0x18001d2a2  jnz     short loc_18001D302
0x18001d2a4  call    cs:__imp_GetCurrentThreadId
0x18001d2aa  lea     rcx, [rdi+40h]; this
0x18001d2ae  call    ?acquire_write@CriticalSection@@QEAA_NXZ; CriticalSection::acquire_write(void)
0x18001d2b3  test    al, al
0x18001d2b5  jnz     short loc_18001D2C8
0x18001d2b7  mov     rcx, [rdi+70h]; hEvent
0x18001d2bb  call    cs:__imp_SetEvent
0x18001d2c1  mov     ebx, 1
0x18001d2c6  jmp     short loc_18001D31A
0x18001d2c8  call    cs:__imp_GetCurrentThreadId
0x18001d2ce  mov     [rdi+80h], eax
0x18001d2d4  mov     ebx, 1
0x18001d2d9  add     [rdi], ebx
0x18001d2db  mov     rcx, [rdi+70h]; hEvent
0x18001d2df  call    cs:__imp_ResetEvent
0x18001d2e5  mov     rcx, [rdi+78h]; hEvent
0x18001d2e9  call    cs:__imp_ResetEvent
0x18001d2ef  call    cs:__imp_GetCurrentThreadId
0x18001d2f5  lea     rcx, [rdi+40h]; this
0x18001d2f9  call    ?release@CriticalSection@@QEAA_NXZ; CriticalSection::release(void)
0x18001d2fe  xor     ebx, ebx
0x18001d300  jmp     short loc_18001D31A
0x18001d302  cmp     eax, 102h
0x18001d307  mov     ebx, 1
0x18001d30c  jz      short loc_18001D313
0x18001d30e  mov     ebx, 2
0x18001d313  call    cs:__imp_GetCurrentThreadId
0x18001d319  nop
0x18001d31a  mov     rcx, rsi; this
0x18001d31d  call    ?release@CriticalSection@@QEAA_NXZ; CriticalSection::release(void)
0x18001d322  mov     eax, ebx
0x18001d324  add     rsp, 38h
0x18001d328  pop     rdi
0x18001d329  pop     rsi
0x18001d32a  pop     rbp
0x18001d32b  pop     rbx
0x18001d32c  retn
```
