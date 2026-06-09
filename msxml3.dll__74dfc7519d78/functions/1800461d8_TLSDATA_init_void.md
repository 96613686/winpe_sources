# TLSDATA::init(void)

- ea: `0x1800461d8`
- end: `0x1800462b6`
- name: `?init@TLSDATA@@QEAAXXZ`
- size: `222`
- prototype: `void __fastcall(TLSDATA *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800461b4`
- `0x18005fe60`

## callees

- `0x1800461d8`
- `0x18004b488`
- `0x180102cde`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046282`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046282`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046242`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046242`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800461f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180046202`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800461f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180046202`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800461f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800461f9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004622c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004622c`

## pseudocode

```c
void __fastcall TLSDATA::init(TLSDATA *this)
{
  HANDLE *v1; // r14
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v5; // rax
  DWORD CurrentThreadId; // eax
  bool v7; // zf
  HANDLE v8; // rcx
  void *v9; // rax
  void *v10; // rbx

  v1 = (HANDLE *)((char *)this + 32);
  *((_QWORD *)this + 4) = 0;
  CurrentProcess = GetCurrentProcess();
  CurrentThread = GetCurrentThread();
  v5 = GetCurrentProcess();
  if ( !DuplicateHandle(v5, CurrentThread, CurrentProcess, v1, 0x4Au, 0, 0) )
  {
    *v1 = 0;
    failure_tracing::record();
  }
  CurrentThreadId = GetCurrentThreadId();
  v7 = *((_BYTE *)this + 128) == 0;
  *((_DWORD *)this + 31) = CurrentThreadId;
  if ( !v7 )
  {
    _InterlockedDecrement(&g_lTLSDATACountFree);
    *((_BYTE *)this + 128) = 0;
  }
  v8 = g_hProcessHeap;
  *((_QWORD *)this + 1) = this;
  *((_QWORD *)this + 3) = this;
  *((_BYTE *)this + 120) = 0;
  v9 = HeapAlloc(v8, 8u, 0xD70u);
  v10 = v9;
  if ( v9 )
    memset_0(v9, 0, 0xD70u);
  else
    v10 = 0;
  *((_QWORD *)this + 14) = v10;
  *((_DWORD *)this + 19) = 1;
}

```

## disassembly

```asm
0x1800461d8  push    rbx
0x1800461da  push    rsi
0x1800461db  push    rdi
0x1800461dc  push    r14
0x1800461de  sub     rsp, 48h
0x1800461e2  lea     r14, [rcx+20h]
0x1800461e6  mov     rsi, rcx
0x1800461e9  mov     qword ptr [r14], 0
0x1800461f0  call    cs:__imp_GetCurrentProcess
0x1800461f6  mov     rdi, rax
0x1800461f9  call    cs:__imp_GetCurrentThread
0x1800461ff  mov     rbx, rax
0x180046202  call    cs:__imp_GetCurrentProcess
0x180046208  mov     [rsp+68h+dwOptions], 0; dwOptions
0x180046210  mov     r9, r14; lpTargetHandle
0x180046213  mov     rcx, rax; hSourceProcessHandle
0x180046216  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x18004621e  mov     r8, rdi; hTargetProcessHandle
0x180046221  mov     [rsp+68h+dwDesiredAccess], 4Ah ; 'J'; dwDesiredAccess
0x180046229  mov     rdx, rbx; hSourceHandle
0x18004622c  call    cs:__imp_DuplicateHandle
0x180046232  test    eax, eax
0x180046234  jnz     short loc_180046242
0x180046236  mov     qword ptr [r14], 0
0x18004623d  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x180046242  call    cs:__imp_GetCurrentThreadId
0x180046248  cmp     byte ptr [rsi+80h], 0
0x18004624f  mov     [rsi+7Ch], eax
0x180046252  jz      short loc_180046262
0x180046254  lock dec cs:?g_lTLSDATACountFree@@3JA; long g_lTLSDATACountFree
0x18004625b  mov     byte ptr [rsi+80h], 0
0x180046262  mov     rcx, cs:g_hProcessHeap; hHeap
0x180046269  mov     edi, 0D70h
0x18004626e  mov     r8d, edi; dwBytes
0x180046271  mov     [rsi+8], rsi
0x180046275  mov     edx, 8; dwFlags
0x18004627a  mov     [rsi+18h], rsi
0x18004627e  mov     byte ptr [rsi+78h], 0
0x180046282  call    cs:__imp_HeapAlloc
0x180046288  mov     rbx, rax
0x18004628b  test    rax, rax
0x18004628e  jz      short loc_18004629F
0x180046290  mov     r8d, edi; Size
0x180046293  xor     edx, edx; Val
0x180046295  mov     rcx, rax; void *
0x180046298  call    memset_0
0x18004629d  jmp     short loc_1800462A1
0x18004629f  xor     ebx, ebx
0x1800462a1  mov     [rsi+70h], rbx
0x1800462a5  mov     dword ptr [rsi+4Ch], 1
0x1800462ac  add     rsp, 48h
0x1800462b0  pop     r14
0x1800462b2  pop     rdi
0x1800462b3  pop     rsi
0x1800462b4  pop     rbx
0x1800462b5  retn
```
