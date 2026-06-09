# ThreadPool::StartTask(WorkerTask *)

- ea: `0x18002bcd8`
- end: `0x18002bdc7`
- name: `?StartTask@ThreadPool@@QEAAXPEAVWorkerTask@@@Z`
- size: `239`
- prototype: `void __fastcall(ThreadPool *__hidden this, struct WorkerTask *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180026b78`

## callees

- `0x18002bcd8`
- `0x180034fd4`
- `0x1800351e8`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18002bd96`
- `KERNEL32!SetEvent` at `0x18002bd96`
- `KERNEL32!CreateEventW` at `0x18002bd40`
- `KERNEL32!CreateEventW` at `0x18002bd40`
- `KERNEL32!CreateThread` at `0x18002bd6c`
- `KERNEL32!CreateThread` at `0x18002bd6c`

## pseudocode

```c
void __fastcall ThreadPool::StartTask(ThreadPool *this, struct WorkerTask *a2)
{
  unsigned int v4; // ecx
  __int64 v5; // r8
  __int64 v6; // r9
  char *v7; // rbx
  __int64 v8; // rax
  HANDLE EventW; // rax
  HANDLE v10; // rax
  __int64 v11; // rax
  void *v12; // rcx
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  v4 = 0;
  v5 = *((unsigned int *)this + 1);
  if ( !(_DWORD)v5 )
    goto LABEL_6;
  while ( 1 )
  {
    v6 = 56LL * v4;
    if ( !*(_QWORD *)((char *)this + v6 + 32) )
      break;
    if ( ++v4 >= (unsigned int)v5 )
      goto LABEL_6;
  }
  v7 = (char *)this + v6 + 8;
  if ( !v7 )
  {
LABEL_6:
    v7 = 0;
    if ( (unsigned int)v5 < *(_DWORD *)this )
    {
      v8 = (unsigned int)(v5 + 1);
      *((_DWORD *)this + 1) = v8;
      v7 = (char *)this + 56 * v5 + 8;
      *((_QWORD *)v7 + 6) = v8;
      EventW = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)v7 + 1) = EventW;
      if ( !EventW || (v10 = CreateThread(0, 0, WorkerThreadProc, v7, 0, &ThreadId), (*(_QWORD *)v7 = v10) == 0) )
        ThrowLastError();
    }
    if ( !v7 )
      ThrowHR(-2147418113);
  }
  v11 = *((_QWORD *)this + 113);
  v12 = (void *)*((_QWORD *)v7 + 1);
  *((_DWORD *)v7 + 8) = 0;
  *((_QWORD *)v7 + 5) = v11;
  *((_QWORD *)v7 + 3) = a2;
  if ( !SetEvent(v12) )
    ThrowLastError();
}

```

## disassembly

```asm
0x18002bcd8  mov     [rsp+arg_8], rbx
0x18002bcdd  mov     [rsp+arg_10], rsi
0x18002bce2  push    rdi
0x18002bce3  sub     rsp, 30h
0x18002bce7  mov     rdi, rcx
0x18002bcea  mov     rsi, rdx
0x18002bced  xor     ecx, ecx
0x18002bcef  mov     r8d, [rdi+4]
0x18002bcf3  lea     edx, [rcx+1]; bManualReset
0x18002bcf6  test    r8d, r8d
0x18002bcf9  jz      short loc_18002BD1B
0x18002bcfb  mov     eax, ecx
0x18002bcfd  imul    r9, rax, 38h ; '8'
0x18002bd01  cmp     qword ptr [r9+rdi+20h], 0
0x18002bd07  jz      short loc_18002BD12
0x18002bd09  add     ecx, edx
0x18002bd0b  cmp     ecx, r8d
0x18002bd0e  jb      short loc_18002BCFB
0x18002bd10  jmp     short loc_18002BD1B
0x18002bd12  lea     rbx, [rdi+8]
0x18002bd16  add     rbx, r9
0x18002bd19  jnz     short loc_18002BD7F
0x18002bd1b  xor     ebx, ebx
0x18002bd1d  cmp     r8d, [rdi]
0x18002bd20  jnb     short loc_18002BD7A
0x18002bd22  imul    rcx, r8, 38h ; '8'
0x18002bd26  lea     eax, [r8+1]
0x18002bd2a  xor     r9d, r9d; lpName
0x18002bd2d  mov     [rdi+4], eax
0x18002bd30  lea     rbx, [rdi+8]
0x18002bd34  add     rbx, rcx
0x18002bd37  xor     r8d, r8d; bInitialState
0x18002bd3a  xor     ecx, ecx; lpEventAttributes
0x18002bd3c  mov     [rbx+30h], rax
0x18002bd40  call    cs:__imp_CreateEventW
0x18002bd46  mov     [rbx+8], rax
0x18002bd4a  test    rax, rax
0x18002bd4d  jz      short loc_18002BDB0
0x18002bd4f  lea     rax, [rsp+38h+ThreadId]
0x18002bd54  mov     r9, rbx; lpParameter
0x18002bd57  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18002bd5c  lea     r8, ?WorkerThreadProc@@YAKPEAX@Z; lpStartAddress
0x18002bd63  and     [rsp+38h+var_18], 0
0x18002bd68  xor     edx, edx; dwStackSize
0x18002bd6a  xor     ecx, ecx; lpThreadAttributes
0x18002bd6c  call    cs:__imp_CreateThread
0x18002bd72  mov     [rbx], rax
0x18002bd75  test    rax, rax
0x18002bd78  jz      short loc_18002BDB0
0x18002bd7a  test    rbx, rbx
0x18002bd7d  jz      short loc_18002BDB6
0x18002bd7f  mov     rax, [rdi+388h]
0x18002bd86  mov     rcx, [rbx+8]; hEvent
0x18002bd8a  and     dword ptr [rbx+20h], 0
0x18002bd8e  mov     [rbx+28h], rax
0x18002bd92  mov     [rbx+18h], rsi
0x18002bd96  call    cs:__imp_SetEvent
0x18002bd9c  test    eax, eax
0x18002bd9e  jz      short loc_18002BDC1
0x18002bda0  mov     rbx, [rsp+38h+arg_8]
0x18002bda5  mov     rsi, [rsp+38h+arg_10]
0x18002bdaa  add     rsp, 30h
0x18002bdae  pop     rdi
0x18002bdaf  retn
0x18002bdb0  call    ?ThrowLastError@@YAXXZ; ThrowLastError(void)
0x18002bdb6  mov     ecx, 8000FFFFh; int
0x18002bdbb  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002bdc1  call    ?ThrowLastError@@YAXXZ; ThrowLastError(void)
```
