# CClfsMarshallingContext::AllocateIocbNaked(CLogIocb * *)

- ea: `0x18000e750`
- end: `0x18000e8dd`
- name: `?AllocateIocbNaked@CClfsMarshallingContext@@AEAAKPEAPEAVCLogIocb@@@Z`
- size: `397`
- prototype: `unsigned int __fastcall(CClfsMarshallingContext *__hidden this, struct CLogIocb **)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e004`
- `0x18000e534`
- `0x18000fa24`
- `0x18000fcdc`
- `0x180010bdc`
- `0x1800135a4`

## callees

- `0x18000df4c`
- `0x18000e750`
- `0x18001125c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e7a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e7a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e8a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e8a8`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000e766`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000e766`

## pseudocode

```c
__int64 __fastcall CClfsMarshallingContext::AllocateIocbNaked(CClfsMarshallingContext *this, struct CLogIocb **a2)
{
  volatile signed __int32 *v2; // rdi
  struct CLogIocb *v5; // rax
  unsigned int v6; // esi
  HANDLE v7; // rcx
  char *v8; // rax
  void *v9; // r9
  CLogIocb *v10; // rdi
  void *v12; // [rsp+30h] [rbp-38h]

  v2 = (volatile signed __int32 *)((char *)this + 16);
  v5 = (struct CLogIocb *)InterlockedPopEntrySList((PSLIST_HEADER)this + 1);
  if ( v5 )
  {
    _InterlockedDecrement(v2 + 4);
    v6 = 0;
    _InterlockedIncrement(v2 + 6);
    *a2 = v5;
    return v6;
  }
  v7 = g_hHeap;
  *a2 = 0;
  v8 = (char *)HeapAlloc(v7, 8u, 0xE0u);
  if ( v8 )
  {
    *((_DWORD *)v8 + 6) = 0;
    *((_WORD *)v8 + 14) = 0;
    *((_QWORD *)v8 + 8) = 0;
    *((_QWORD *)v8 + 9) = 0;
    *((_QWORD *)v8 + 10) = 0;
    *((_QWORD *)v8 + 13) = 0;
    *((_QWORD *)v8 + 14) = 0;
    *((_QWORD *)v8 + 15) = 0;
    *((_DWORD *)v8 + 32) = 0;
    *((CLFS_LSN *)v8 + 17) = CLFS_LSN_INVALID;
    *((CLFS_LSN *)v8 + 18) = CLFS_LSN_INVALID;
    *((CLFS_LSN *)v8 + 19) = CLFS_LSN_NULL;
    *((CLFS_LSN *)v8 + 20) = CLFS_LSN_NULL;
    *((CLFS_LSN *)v8 + 22) = CLFS_LSN_NULL;
    *((CLFS_LSN *)v8 + 23) = CLFS_LSN_INVALID;
    *((_QWORD *)v8 + 24) = 0;
    *((_QWORD *)v8 + 25) = 0;
    *((_QWORD *)v8 + 26) = 0;
    *((_QWORD *)v8 + 27) = 0;
    *((_OWORD *)v8 + 2) = 0;
    *((_OWORD *)v8 + 3) = 0;
    *(_OWORD *)(v8 + 88) = 0;
    *(_OWORD *)v8 = 0;
    *a2 = (struct CLogIocb *)v8;
    v6 = CLogIocb::Initialize(
           (CLogIocb *)v8,
           this,
           (unsigned int)v8,
           v9,
           *((void *(**)(unsigned int, void *))this + 9),
           *((void (**)(void *, void *))this + 10),
           v12);
    if ( v6 )
    {
      v10 = *a2;
      if ( *a2 )
      {
        CLogIocb::~CLogIocb(*a2);
        if ( !HeapFree(g_hHeap, 0, v10) )
          GetLastError();
      }
      *a2 = 0;
    }
    return v6;
  }
  *a2 = 0;
  return 1450;
}

```

## disassembly

```asm
0x18000e750  push    rbx
0x18000e752  push    rbp
0x18000e753  push    rsi
0x18000e754  push    rdi
0x18000e755  sub     rsp, 48h
0x18000e759  lea     rdi, [rcx+10h]
0x18000e75d  mov     rsi, rcx
0x18000e760  mov     rcx, rdi; ListHead
0x18000e763  mov     rbx, rdx
0x18000e766  call    cs:__imp_InterlockedPopEntrySList
0x18000e76d  nop     dword ptr [rax+rax+00h]
0x18000e772  xor     ebp, ebp
0x18000e774  test    rax, rax
0x18000e777  jz      short loc_18000E78B
0x18000e779  lock dec dword ptr [rdi+10h]
0x18000e77d  mov     esi, ebp
0x18000e77f  lock inc dword ptr [rdi+18h]
0x18000e783  mov     [rbx], rax
0x18000e786  jmp     loc_18000E8C7
0x18000e78b  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x18000e792  mov     edx, 8; dwFlags
0x18000e797  mov     r8d, 0E0h; dwBytes
0x18000e79d  mov     [rbx], rax
0x18000e7a0  call    cs:__imp_HeapAlloc
0x18000e7a7  nop     dword ptr [rax+rax+00h]
0x18000e7ac  mov     r8, rax; unsigned int
0x18000e7af  test    rax, rax
0x18000e7b2  jz      loc_18000E8CB
0x18000e7b8  mov     [rax+18h], ebp
0x18000e7bb  xorps   xmm0, xmm0
0x18000e7be  mov     [rax+1Ch], bp
0x18000e7c2  xorps   xmm1, xmm1
0x18000e7c5  mov     [rax+40h], rbp
0x18000e7c9  mov     rdx, rsi; struct CClfsMarshallingContext *
0x18000e7cc  mov     [rax+48h], rbp
0x18000e7d0  mov     rcx, r8; this
0x18000e7d3  mov     [rax+50h], rbp
0x18000e7d7  mov     [rax+68h], rbp
0x18000e7db  mov     [rax+70h], rbp
0x18000e7df  mov     [rax+78h], rbp
0x18000e7e3  mov     [rax+80h], ebp
0x18000e7e9  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18000e7f0  mov     [r8+88h], rax
0x18000e7f7  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18000e7fe  mov     [r8+90h], rax
0x18000e805  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x18000e80c  mov     [r8+98h], rax
0x18000e813  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x18000e81a  mov     [r8+0A0h], rax
0x18000e821  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x18000e828  mov     [r8+0B0h], rax
0x18000e82f  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18000e836  mov     [r8+0B8h], rax
0x18000e83d  mov     [r8+0C0h], rbp
0x18000e844  mov     [r8+0C8h], rbp
0x18000e84b  mov     [r8+0D0h], rbp
0x18000e852  mov     [r8+0D8h], rbp
0x18000e859  movups  xmmword ptr [r8+20h], xmm0
0x18000e85e  movups  xmmword ptr [r8+30h], xmm0
0x18000e863  movups  xmmword ptr [r8+58h], xmm0
0x18000e868  movups  xmmword ptr [r8], xmm1
0x18000e86c  mov     [rbx], r8
0x18000e86f  mov     rax, [rsi+50h]
0x18000e873  mov     [rsp+68h+var_40], rax; void (*)(void *, void *)
0x18000e878  mov     rax, [rsi+48h]
0x18000e87c  mov     [rsp+68h+var_48], rax; void *(*)(unsigned int, void *)
0x18000e881  call    ?Initialize@CLogIocb@@QEAAKQEAVCClfsMarshallingContext@@KPEAXP6APEAXK1@ZP6AX11@Z1@Z; CLogIocb::Initialize(CClfsMarshallingContext * const,ulong,void *,void * (*)(ulong,void *),void (*)(void *,void *),void *)
0x18000e886  mov     esi, eax
0x18000e888  test    eax, eax
0x18000e88a  jz      short loc_18000E8C7
0x18000e88c  mov     rdi, [rbx]
0x18000e88f  test    rdi, rdi
0x18000e892  jz      short loc_18000E8C4
0x18000e894  mov     rcx, rdi; this
0x18000e897  call    ??1CLogIocb@@QEAA@XZ; CLogIocb::~CLogIocb(void)
0x18000e89c  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x18000e8a3  mov     r8, rdi; lpMem
0x18000e8a6  xor     edx, edx; dwFlags
0x18000e8a8  call    cs:__imp_HeapFree
0x18000e8af  nop     dword ptr [rax+rax+00h]
0x18000e8b4  test    eax, eax
0x18000e8b6  jnz     short loc_18000E8C4
0x18000e8b8  call    cs:__imp_GetLastError
0x18000e8bf  nop     dword ptr [rax+rax+00h]
0x18000e8c4  mov     [rbx], rbp
0x18000e8c7  mov     eax, esi
0x18000e8c9  jmp     short loc_18000E8D3
0x18000e8cb  mov     [rbx], rbp
0x18000e8ce  mov     eax, 5AAh
0x18000e8d3  add     rsp, 48h
0x18000e8d7  pop     rdi
0x18000e8d8  pop     rsi
0x18000e8d9  pop     rbp
0x18000e8da  pop     rbx
0x18000e8db  retn
```
