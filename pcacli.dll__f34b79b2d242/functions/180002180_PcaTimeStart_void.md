# PcaTimeStart(void)

- ea: `0x180002180`
- end: `0x180002208`
- name: `?PcaTimeStart@@YA_KXZ`
- size: `136`
- prototype: `unsigned __int64(void)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001870`
- `0x180001bd0`
- `0x1800082c0`
- `0x180008480`

## callees

- `0x180002180`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000219c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000219c`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadTimes` at `0x1800021be`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadTimes` at `0x1800021be`

## pseudocode

```c
unsigned __int64 PcaTimeStart(void)
{
  HANDLE CurrentThread; // rax
  struct _FILETIME UserTime; // [rsp+40h] [rbp+8h] BYREF
  struct _FILETIME KernelTime; // [rsp+48h] [rbp+10h] BYREF
  struct _FILETIME ExitTime; // [rsp+50h] [rbp+18h] BYREF
  _FILETIME CreationTime; // [rsp+58h] [rbp+20h] BYREF

  UserTime = 0;
  KernelTime = 0;
  CreationTime = 0;
  ExitTime = 0;
  CurrentThread = GetCurrentThread();
  if ( GetThreadTimes(CurrentThread, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
    return (*(_QWORD *)&KernelTime + *(_QWORD *)&UserTime) / 0x2710uLL;
  else
    return 0;
}

```

## disassembly

```asm
0x180002180  push    rbx
0x180002182  sub     rsp, 30h
0x180002186  xor     ebx, ebx
0x180002188  mov     qword ptr [rsp+38h+UserTime.dwLowDateTime], rbx
0x18000218d  mov     qword ptr [rsp+38h+KernelTime.dwLowDateTime], rbx
0x180002192  mov     qword ptr [rsp+38h+CreationTime.dwLowDateTime], rbx
0x180002197  mov     qword ptr [rsp+38h+ExitTime.dwLowDateTime], rbx
0x18000219c  call    cs:__imp_GetCurrentThread
0x1800021a2  mov     rcx, rax; hThread
0x1800021a5  lea     r9, [rsp+38h+KernelTime]; lpKernelTime
0x1800021aa  lea     rax, [rsp+38h+UserTime]
0x1800021af  lea     r8, [rsp+38h+ExitTime]; lpExitTime
0x1800021b4  mov     [rsp+38h+lpUserTime], rax; lpUserTime
0x1800021b9  lea     rdx, [rsp+38h+CreationTime]; lpCreationTime
0x1800021be  call    cs:__imp_GetThreadTimes
0x1800021c4  test    eax, eax
0x1800021c6  jz      short loc_180002203
0x1800021c8  mov     eax, [rsp+38h+UserTime.dwLowDateTime]
0x1800021cc  mov     edx, [rsp+38h+UserTime.dwHighDateTime]
0x1800021d0  mov     ecx, [rsp+38h+KernelTime.dwHighDateTime]
0x1800021d4  shl     rdx, 20h
0x1800021d8  or      rdx, rax
0x1800021db  shl     rcx, 20h
0x1800021df  mov     eax, [rsp+38h+KernelTime.dwLowDateTime]
0x1800021e3  or      rcx, rax
0x1800021e6  mov     rax, 346DC5D63886594Bh
0x1800021f0  add     rdx, rcx
0x1800021f3  mul     rdx
0x1800021f6  shr     rdx, 0Bh
0x1800021fa  mov     rax, rdx
0x1800021fd  add     rsp, 30h
0x180002201  pop     rbx
0x180002202  retn
0x180002203  mov     rax, rbx
0x180002206  jmp     short loc_1800021FD
```
