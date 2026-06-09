# UTSemReadWriteES::GetReadWaiterSemaphore(void)

- ea: `0x180029130`
- end: `0x1800291a3`
- name: `?GetReadWaiterSemaphore@UTSemReadWriteES@@AEAAPEAXXZ`
- size: `115`
- prototype: `void *__fastcall(UTSemReadWriteES *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d15c`
- `0x18000e1f0`
- `0x18001f340`

## callees

- `0x180009034`
- `0x180029130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002915d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18002915d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029193`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029193`

## string_xrefs

- `0x18002917b`: `com\complus\src\events\shared\utsem.cpp`
- `0x180029174`: `CreateSemaphore`

## pseudocode

```c
void *__fastcall UTSemReadWriteES::GetReadWaiterSemaphore(UTSemReadWriteES *this)
{
  HANDLE Semaphore; // rax

  if ( !*((_QWORD *)this + 1) )
  {
    Semaphore = CreateSemaphoreExW(0, 0, 0x7FFFFFFF, 0, 0, 0x1F0003u);
    if ( Semaphore )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 1, (signed __int64)Semaphore, 0) )
        CloseHandle(Semaphore);
    }
    else
    {
      InternalError_Win32(L"com\\complus\\src\\events\\shared\\utsem.cpp", 0x242u, 0x10u, L"CreateSemaphore");
    }
  }
  return (void *)*((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x180029130  push    rbx
0x180029132  sub     rsp, 30h
0x180029136  cmp     qword ptr [rcx+8], 0
0x18002913b  mov     rbx, rcx
0x18002913e  jnz     short loc_180029199
0x180029140  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180029148  xor     r9d, r9d; lpName
0x18002914b  xor     edx, edx; lInitialCount
0x18002914d  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180029155  xor     ecx, ecx; lpSemaphoreAttributes
0x180029157  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18002915d  call    cs:__imp_CreateSemaphoreExW
0x180029163  mov     rcx, rax; hObject
0x180029166  test    rax, rax
0x180029169  jnz     short loc_180029189
0x18002916b  lea     r8d, [rax+10h]; unsigned __int16
0x18002916f  mov     edx, 242h; unsigned int
0x180029174  lea     r9, aCreatesemaphor; "CreateSemaphore"
0x18002917b  lea     rcx, aComComplusSrcE_23; "com\\complus\\src\\events\\shared\\utse"...
0x180029182  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x180029187  jmp     short loc_180029199
0x180029189  xor     eax, eax
0x18002918b  lock cmpxchg [rbx+8], rcx
0x180029191  jz      short loc_180029199
0x180029193  call    cs:__imp_CloseHandle
0x180029199  mov     rax, [rbx+8]
0x18002919d  add     rsp, 30h
0x1800291a1  pop     rbx
0x1800291a2  retn
```
