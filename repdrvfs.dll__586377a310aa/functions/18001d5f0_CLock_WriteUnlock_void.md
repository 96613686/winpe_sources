# CLock::WriteUnlock(void)

- ea: `0x18001d5f0`
- end: `0x18001d6a7`
- name: `?WriteUnlock@CLock@@QEAAHXZ`
- size: `183`
- prototype: `__int64 __fastcall(CLock *__hidden this)`
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x18001c038`
- `0x18001c070`
- `0x18001c950`
- `0x18001cc50`
- `0x180031180`
- `0x1800313b0`
- `0x1800324f0`
- `0x18003d1c0`
- `0x180047300`
- `0x18004737f`

## callees

- `0x180002f4c`
- `0x1800038c0`
- `0x18001d5f0`
- `0x18001e1cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d65e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d66c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d65e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d66c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d602`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d654`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d602`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d654`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d628`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d628`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLock::WriteUnlock(CLock *this)
{
  CriticalSection *v2; // rdi
  char v3; // bl
  bool v4; // sf
  CriticalSection *v6; // [rsp+20h] [rbp-18h] BYREF
  char v7; // [rsp+28h] [rbp-10h]

  GetCurrentThreadId();
  v2 = (CLock *)((char *)this + 64);
  v6 = (CLock *)((char *)this + 64);
  v3 = CriticalSection::acquire_write((CLock *)((char *)this + 64));
  v7 = v3;
  if ( !v3 )
  {
    do
    {
      Sleep(0x14u);
      LockGuard<CriticalSection,wminothrow_t>::acquire(&v6);
      v3 = v7;
    }
    while ( !v7 );
    v2 = v6;
  }
  v4 = --*(_DWORD *)this < 0;
  *((_DWORD *)this + 32) = 0;
  if ( !v4 && (GetCurrentThreadId(), SetEvent(*((HANDLE *)this + 15))) && SetEvent(*((HANDLE *)this + 14)) )
  {
    if ( v3 )
      CriticalSection::release(v2);
    return 0;
  }
  else
  {
    if ( v3 )
      CriticalSection::release(v2);
    return 2;
  }
}

```

## disassembly

```asm
0x18001d5f0  mov     [rsp+arg_8], rbx
0x18001d5f5  mov     [rsp+arg_10], rsi
0x18001d5fa  push    rdi
0x18001d5fb  sub     rsp, 30h
0x18001d5ff  mov     rsi, rcx
0x18001d602  call    cs:__imp_GetCurrentThreadId
0x18001d608  lea     rdi, [rsi+40h]
0x18001d60c  mov     [rsp+38h+var_18], rdi
0x18001d611  mov     rcx, rdi; this
0x18001d614  call    ?acquire_write@CriticalSection@@QEAA_NXZ; CriticalSection::acquire_write(void)
0x18001d619  mov     bl, al
0x18001d61b  mov     [rsp+38h+var_10], al
0x18001d61f  test    al, al
0x18001d621  jnz     short loc_18001D645
0x18001d623  mov     ecx, 14h; dwMilliseconds
0x18001d628  call    cs:__imp_Sleep
0x18001d62e  lea     rcx, [rsp+38h+var_18]
0x18001d633  call    ?acquire@?$LockGuard@VCriticalSection@@Uwminothrow_t@@@@QEAA_NXZ; LockGuard<CriticalSection,wminothrow_t>::acquire(void)
0x18001d638  mov     bl, [rsp+38h+var_10]
0x18001d63c  test    bl, bl
0x18001d63e  jz      short loc_18001D623
0x18001d640  mov     rdi, [rsp+38h+var_18]
0x18001d645  sub     dword ptr [rsi], 1
0x18001d648  mov     dword ptr [rsi+80h], 0
0x18001d652  js      short loc_18001D676
0x18001d654  call    cs:__imp_GetCurrentThreadId
0x18001d65a  mov     rcx, [rsi+78h]; hEvent
0x18001d65e  call    cs:__imp_SetEvent
0x18001d664  test    eax, eax
0x18001d666  jz      short loc_18001D676
0x18001d668  mov     rcx, [rsi+70h]; hEvent
0x18001d66c  call    cs:__imp_SetEvent
0x18001d672  test    eax, eax
0x18001d674  jnz     short loc_18001D689
0x18001d676  test    bl, bl
0x18001d678  jz      short loc_18001D682
0x18001d67a  mov     rcx, rdi; this
0x18001d67d  call    ?release@CriticalSection@@QEAA_NXZ; CriticalSection::release(void)
0x18001d682  mov     eax, 2
0x18001d687  jmp     short loc_18001D697
0x18001d689  test    bl, bl
0x18001d68b  jz      short loc_18001D695
0x18001d68d  mov     rcx, rdi; this
0x18001d690  call    ?release@CriticalSection@@QEAA_NXZ; CriticalSection::release(void)
0x18001d695  xor     eax, eax
0x18001d697  mov     rbx, [rsp+38h+arg_8]
0x18001d69c  mov     rsi, [rsp+38h+arg_10]
0x18001d6a1  add     rsp, 30h
0x18001d6a5  pop     rdi
0x18001d6a6  retn
```
