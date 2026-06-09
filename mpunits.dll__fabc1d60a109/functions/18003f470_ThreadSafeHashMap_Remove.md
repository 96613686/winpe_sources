# ThreadSafeHashMap_Remove

- ea: `0x18003f470`
- end: `0x18003f56d`
- name: `ThreadSafeHashMap_Remove`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18003deb0`

## callees

- `0x18003f470`
- `0x180042ecc`
- `0x180043120`
- `0x1800431f0`
- `0x180043d40`
- `0x1800443d4`
- `0x180044464`
- `0x18004449c`
- `0x1800444f4`
- `0x18004462c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f487`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f53c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f487`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f53c`

## pseudocode

```c
__int64 __fastcall ThreadSafeHashMap_Remove(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 v5; // rbx
  __int64 v6; // rbp
  unsigned int v7; // ebx
  __int64 *v8; // rsi

  v3 = a1 + 48;
  if ( *(_QWORD *)(a1 + 88) != GetCurrentThreadId() && (unsigned int)_Pump_BeginDeferringHelper(v3) )
    _Pump_BeginDeferring(v3);
  v5 = HashMap_Find(a1, a2);
  if ( v5 )
  {
    v6 = a1 + 96;
    if ( !(unsigned int)TryAcquireWrite(v6) )
      QueueAcquireWrite(v6);
    if ( _InterlockedExchange64((volatile __int64 *)(v5 + 16), 2) == 1 )
    {
      Pump_Queue(v3, v5 + 8);
      v7 = 0;
    }
    else
    {
      v7 = 6;
    }
    ReadWriteLock_ReleaseWrite(v6);
  }
  else
  {
    v8 = *(__int64 **)(a1 + 64);
    v7 = 6;
    while ( v8 )
    {
      if ( (*(unsigned int (__fastcall **)(__int64 *, __int64))(a1 + 112))(v8 - 1, a2) )
      {
        if ( !_InterlockedCompareExchange64(v8 + 1, 3, 0) )
          v7 = 0;
        break;
      }
      v8 = (__int64 *)*v8;
    }
  }
  if ( *(_QWORD *)(v3 + 40) != GetCurrentThreadId() && (unsigned int)_Pump_EndDeferringHelper(v3) )
    _Pump_EndDeferring(v3);
  return v7;
}

```

## disassembly

```asm
0x18003f470  push    rbx
0x18003f472  push    rbp
0x18003f473  push    rsi
0x18003f474  push    rdi
0x18003f475  push    r14
0x18003f477  push    r15
0x18003f479  sub     rsp, 28h
0x18003f47d  mov     r15, rdx
0x18003f480  lea     rdi, [rcx+30h]
0x18003f484  mov     rbp, rcx
0x18003f487  call    cs:__imp_GetCurrentThreadId
0x18003f48d  mov     eax, eax
0x18003f48f  cmp     [rdi+28h], rax
0x18003f493  jz      short loc_18003F4A9
0x18003f495  mov     rcx, rdi
0x18003f498  call    __Pump_BeginDeferringHelper
0x18003f49d  test    eax, eax
0x18003f49f  jz      short loc_18003F4A9
0x18003f4a1  mov     rcx, rdi
0x18003f4a4  call    __Pump_BeginDeferring
0x18003f4a9  mov     rdx, r15
0x18003f4ac  mov     rcx, rbp
0x18003f4af  call    HashMap_Find
0x18003f4b4  mov     rbx, rax
0x18003f4b7  test    rax, rax
0x18003f4ba  jz      short loc_18003F502
0x18003f4bc  add     rbp, 60h ; '`'
0x18003f4c0  mov     rcx, rbp
0x18003f4c3  call    TryAcquireWrite
0x18003f4c8  test    eax, eax
0x18003f4ca  jnz     short loc_18003F4D4
0x18003f4cc  mov     rcx, rbp
0x18003f4cf  call    QueueAcquireWrite
0x18003f4d4  mov     eax, 2
0x18003f4d9  xchg    rax, [rbx+10h]
0x18003f4dd  cmp     rax, 1
0x18003f4e1  jnz     short loc_18003F4F3
0x18003f4e3  lea     rdx, [rbx+8]
0x18003f4e7  mov     rcx, rdi
0x18003f4ea  call    Pump_Queue
0x18003f4ef  xor     ebx, ebx
0x18003f4f1  jmp     short loc_18003F4F8
0x18003f4f3  mov     ebx, 6
0x18003f4f8  mov     rcx, rbp
0x18003f4fb  call    ReadWriteLock_ReleaseWrite
0x18003f500  jmp     short loc_18003F53C
0x18003f502  mov     rsi, [rbp+40h]
0x18003f506  mov     ebx, 6
0x18003f50b  jmp     short loc_18003F524
0x18003f50d  mov     rax, [rbp+70h]
0x18003f511  lea     rcx, [rsi-8]
0x18003f515  mov     rdx, r15
0x18003f518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f51d  test    eax, eax
0x18003f51f  jnz     short loc_18003F52B
0x18003f521  mov     rsi, [rsi]
0x18003f524  test    rsi, rsi
0x18003f527  jnz     short loc_18003F50D
0x18003f529  jmp     short loc_18003F53C
0x18003f52b  mov     ecx, 3
0x18003f530  xor     eax, eax
0x18003f532  lock cmpxchg [rsi+8], rcx
0x18003f538  jnz     short loc_18003F53C
0x18003f53a  xor     ebx, ebx
0x18003f53c  call    cs:__imp_GetCurrentThreadId
0x18003f542  mov     edx, eax
0x18003f544  cmp     [rdi+28h], rdx
0x18003f548  jz      short loc_18003F55E
0x18003f54a  mov     rcx, rdi
0x18003f54d  call    __Pump_EndDeferringHelper
0x18003f552  test    eax, eax
0x18003f554  jz      short loc_18003F55E
0x18003f556  mov     rcx, rdi
0x18003f559  call    __Pump_EndDeferring
0x18003f55e  mov     eax, ebx
0x18003f560  add     rsp, 28h
0x18003f564  pop     r15
0x18003f566  pop     r14
0x18003f568  pop     rdi
0x18003f569  pop     rsi
0x18003f56a  pop     rbp
0x18003f56b  pop     rbx
0x18003f56c  retn
```
