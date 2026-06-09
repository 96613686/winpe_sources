# FreeAepServiceEntry(_AEP_SERVICE_ENTRY *)

- ea: `0x180006208`
- end: `0x18000631a`
- name: `?FreeAepServiceEntry@@YAXPEAU_AEP_SERVICE_ENTRY@@@Z`
- size: `274`
- prototype: `void __fastcall(struct _AEP_SERVICE_ENTRY *lpMem)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000759c`
- `0x1800154b4`

## callees

- `0x180006208`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800062f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800062f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000622b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000627d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000629b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000622b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000627d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000629b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006239`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000628b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006305`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006239`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000628b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006305`

## pseudocode

```c
void __fastcall FreeAepServiceEntry(struct _RTL_CRITICAL_SECTION *lpMem)
{
  HANDLE OwningThread; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE *p_LockSemaphore; // rsi
  ULONG_PTR *p_SpinCount; // r14
  __int64 i; // r15
  _QWORD *v7; // rbp
  __int64 v8; // rbx
  void *v9; // r12
  HANDLE v10; // rax
  void *v11; // r12
  HANDLE v12; // rax
  void *v13; // rbx
  HANDLE v14; // rax
  HANDLE v15; // rax

  if ( lpMem )
  {
    OwningThread = lpMem->OwningThread;
    if ( OwningThread )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, OwningThread);
      lpMem->OwningThread = 0;
    }
    p_LockSemaphore = &lpMem->LockSemaphore;
    if ( lpMem != (struct _RTL_CRITICAL_SECTION *)-24LL )
    {
      p_SpinCount = &lpMem->SpinCount;
      if ( lpMem != (struct _RTL_CRITICAL_SECTION *)-32LL )
      {
        for ( i = 0; (unsigned int)i < *(_DWORD *)p_LockSemaphore; *(_OWORD *)&v7[v8 + 4] = 0 )
        {
          v7 = (_QWORD *)*p_SpinCount;
          v8 = 6 * i;
          v9 = *(void **)(*p_SpinCount + 48 * i + 24);
          if ( v9 )
          {
            v10 = GetProcessHeap();
            HeapFree(v10, 0, v9);
          }
          v11 = (void *)v7[6 * i + 5];
          if ( v11 )
          {
            v12 = GetProcessHeap();
            HeapFree(v12, 0, v11);
          }
          i = (unsigned int)(i + 1);
          *(_OWORD *)&v7[v8] = 0;
          *(_OWORD *)&v7[v8 + 2] = 0;
        }
        v13 = (void *)*p_SpinCount;
        v14 = GetProcessHeap();
        HeapFree(v14, 0, v13);
        *(_DWORD *)p_LockSemaphore = 0;
        *p_SpinCount = 0;
      }
    }
    DeleteCriticalSection(lpMem + 1);
    v15 = GetProcessHeap();
    HeapFree(v15, 0, lpMem);
  }
}

```

## disassembly

```asm
0x180006208  test    rcx, rcx
0x18000620b  jz      locret_180006319
0x180006211  push    rbx
0x180006212  push    rbp
0x180006213  push    rsi
0x180006214  push    rdi
0x180006215  push    r12
0x180006217  push    r14
0x180006219  push    r15
0x18000621b  sub     rsp, 20h
0x18000621f  mov     rbx, [rcx+10h]
0x180006223  mov     rdi, rcx
0x180006226  test    rbx, rbx
0x180006229  jz      short loc_180006247
0x18000622b  call    cs:__imp_GetProcessHeap
0x180006231  mov     r8, rbx; lpMem
0x180006234  xor     edx, edx; dwFlags
0x180006236  mov     rcx, rax; hHeap
0x180006239  call    cs:__imp_HeapFree
0x18000623f  mov     qword ptr [rdi+10h], 0
0x180006247  lea     rsi, [rdi+18h]
0x18000624b  test    rsi, rsi
0x18000624e  jz      loc_1800062ED
0x180006254  lea     r14, [rdi+20h]
0x180006258  test    r14, r14
0x18000625b  jz      loc_1800062ED
0x180006261  xor     r15d, r15d
0x180006264  cmp     [rsi], r15d
0x180006267  jbe     short loc_1800062C9
0x180006269  mov     rbp, [r14]
0x18000626c  lea     rbx, [r15+r15*2]
0x180006270  add     rbx, rbx
0x180006273  mov     r12, [rbp+rbx*8+18h]
0x180006278  test    r12, r12
0x18000627b  jz      short loc_180006291
0x18000627d  call    cs:__imp_GetProcessHeap
0x180006283  mov     r8, r12; lpMem
0x180006286  xor     edx, edx; dwFlags
0x180006288  mov     rcx, rax; hHeap
0x18000628b  call    cs:__imp_HeapFree
0x180006291  mov     r12, [rbp+rbx*8+28h]
0x180006296  test    r12, r12
0x180006299  jz      short loc_1800062AF
0x18000629b  call    cs:__imp_GetProcessHeap
0x1800062a1  mov     r8, r12; lpMem
0x1800062a4  xor     edx, edx; dwFlags
0x1800062a6  mov     rcx, rax; hHeap
0x1800062a9  call    cs:__imp_HeapFree
0x1800062af  xorps   xmm0, xmm0
0x1800062b2  inc     r15d
0x1800062b5  movups  xmmword ptr [rbp+rbx*8+0], xmm0
0x1800062ba  movups  xmmword ptr [rbp+rbx*8+10h], xmm0
0x1800062bf  movups  xmmword ptr [rbp+rbx*8+20h], xmm0
0x1800062c4  cmp     r15d, [rsi]
0x1800062c7  jb      short loc_180006269
0x1800062c9  mov     rbx, [r14]
0x1800062cc  call    cs:__imp_GetProcessHeap
0x1800062d2  mov     r8, rbx; lpMem
0x1800062d5  xor     edx, edx; dwFlags
0x1800062d7  mov     rcx, rax; hHeap
0x1800062da  call    cs:__imp_HeapFree
0x1800062e0  mov     dword ptr [rsi], 0
0x1800062e6  mov     qword ptr [r14], 0
0x1800062ed  lea     rcx, [rdi+28h]; lpCriticalSection
0x1800062f1  call    cs:__imp_DeleteCriticalSection
0x1800062f7  call    cs:__imp_GetProcessHeap
0x1800062fd  mov     r8, rdi; lpMem
0x180006300  xor     edx, edx; dwFlags
0x180006302  mov     rcx, rax; hHeap
0x180006305  call    cs:__imp_HeapFree
0x18000630b  add     rsp, 20h
0x18000630f  pop     r15
0x180006311  pop     r14
0x180006313  pop     r12
0x180006315  pop     rdi
0x180006316  pop     rsi
0x180006317  pop     rbp
0x180006318  pop     rbx
0x180006319  retn
```
