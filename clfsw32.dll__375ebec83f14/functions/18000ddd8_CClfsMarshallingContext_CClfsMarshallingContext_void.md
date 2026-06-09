# CClfsMarshallingContext::~CClfsMarshallingContext(void)

- ea: `0x18000ddd8`
- end: `0x18000df43`
- name: `??1CClfsMarshallingContext@@QEAA@XZ`
- size: `363`
- prototype: `void __fastcall(CClfsMarshallingContext *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180013058`

## callees

- `0x18000ddd8`
- `0x18000df4c`
- `0x1800135a4`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000df1e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000df1e`
- `ntdll!RtlDeleteCriticalSection` at `0x18000de0e`
- `ntdll!RtlDeleteCriticalSection` at `0x18000de21`
- `ntdll!RtlDeleteCriticalSection` at `0x18000df06`
- `ntdll!RtlDeleteCriticalSection` at `0x18000de0e`
- `ntdll!RtlDeleteCriticalSection` at `0x18000de21`
- `ntdll!RtlDeleteCriticalSection` at `0x18000df06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ded8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ded8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dec8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dec8`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x18000de64`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x18000de64`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedFlushSList` at `0x18000de8c`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedFlushSList` at `0x18000de8c`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedFlushSList` at `0x18000df37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000de2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000de2d`

## pseudocode

```c
void __fastcall CClfsMarshallingContext::~CClfsMarshallingContext(CClfsMarshallingContext *this)
{
  char *v2; // rcx
  void *v3; // rcx
  PSLIST_ENTRY v4; // r14
  CLogIocb *v5; // rbx
  void *v6; // rcx
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF

  v7 = -(*((_QWORD *)this + 23) + *((_QWORD *)this + 24));
  if ( v7 < 0 )
    CClfsMarshallingContext::ReserveLogSpace(this, &v7);
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 328));
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 288));
  GetCurrentProcessId();
  v2 = (char *)*((_QWORD *)this + 6);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 6) = -1;
  }
  v3 = (void *)*((_QWORD *)this + 8);
  if ( v3 )
  {
    if ( !HeapDestroy(v3) )
      GetLastError();
    *((_QWORD *)this + 8) = 0;
  }
  v4 = InterlockedFlushSList((PSLIST_HEADER)this + 1);
  _InterlockedAdd((volatile signed __int32 *)this + 10, *((_DWORD *)this + 8));
  *((_DWORD *)this + 8) = 0;
  while ( v4 )
  {
    v5 = (CLogIocb *)v4;
    v4 = v4->Next;
    CLogIocb::~CLogIocb(v5);
    if ( !HeapFree(g_hHeap, 0, v5) )
      GetLastError();
  }
  *((_QWORD *)this + 7) = -1;
  *((_DWORD *)this + 24) = -1;
  *(_QWORD *)this = 0;
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 248));
  v6 = (void *)*((_QWORD *)this + 30);
  if ( v6 )
    operator delete[](v6);
  InterlockedFlushSList((PSLIST_HEADER)this + 1);
}

```

## disassembly

```asm
0x18000ddd8  push    rbx
0x18000ddda  push    rsi
0x18000dddb  push    rdi
0x18000dddc  push    r14
0x18000ddde  sub     rsp, 28h
0x18000dde2  mov     rax, [rcx+0C0h]
0x18000dde9  mov     rdi, rcx
0x18000ddec  add     rax, [rcx+0B8h]
0x18000ddf3  neg     rax
0x18000ddf6  mov     [rsp+48h+arg_0], rax
0x18000ddfb  jns     short loc_18000DE07
0x18000ddfd  lea     rdx, [rsp+48h+arg_0]; __int64 *
0x18000de02  call    ?ReserveLogSpace@CClfsMarshallingContext@@QEAAKAEB_J@Z; CClfsMarshallingContext::ReserveLogSpace(__int64 const &)
0x18000de07  lea     rcx, [rdi+148h]; CriticalSection
0x18000de0e  call    cs:__imp_RtlDeleteCriticalSection
0x18000de15  nop     dword ptr [rax+rax+00h]
0x18000de1a  lea     rcx, [rdi+120h]; CriticalSection
0x18000de21  call    cs:__imp_RtlDeleteCriticalSection
0x18000de28  nop     dword ptr [rax+rax+00h]
0x18000de2d  call    cs:__imp_GetCurrentProcessId
0x18000de34  nop     dword ptr [rax+rax+00h]
0x18000de39  mov     rcx, [rdi+30h]; hObject
0x18000de3d  lea     rax, [rcx-1]
0x18000de41  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000de45  ja      short loc_18000DE5B
0x18000de47  call    cs:__imp_CloseHandle
0x18000de4e  nop     dword ptr [rax+rax+00h]
0x18000de53  mov     qword ptr [rdi+30h], 0FFFFFFFFFFFFFFFFh
0x18000de5b  mov     rcx, [rdi+40h]; hHeap
0x18000de5f  test    rcx, rcx
0x18000de62  jz      short loc_18000DE88
0x18000de64  call    cs:__imp_HeapDestroy
0x18000de6b  nop     dword ptr [rax+rax+00h]
0x18000de70  test    eax, eax
0x18000de72  jnz     short loc_18000DE80
0x18000de74  call    cs:__imp_GetLastError
0x18000de7b  nop     dword ptr [rax+rax+00h]
0x18000de80  mov     qword ptr [rdi+40h], 0
0x18000de88  lea     rcx, [rdi+10h]; ListHead
0x18000de8c  call    cs:__imp_InterlockedFlushSList
0x18000de93  nop     dword ptr [rax+rax+00h]
0x18000de98  mov     ecx, [rdi+20h]
0x18000de9b  mov     r14, rax
0x18000de9e  lock add [rdi+28h], ecx
0x18000dea2  mov     dword ptr [rdi+20h], 0
0x18000dea9  test    rax, rax
0x18000deac  jz      short loc_18000DEE9
0x18000deae  mov     rbx, r14
0x18000deb1  mov     r14, [r14]
0x18000deb4  mov     rcx, rbx; this
0x18000deb7  call    ??1CLogIocb@@QEAA@XZ; CLogIocb::~CLogIocb(void)
0x18000debc  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x18000dec3  mov     r8, rbx; lpMem
0x18000dec6  xor     edx, edx; dwFlags
0x18000dec8  call    cs:__imp_HeapFree
0x18000decf  nop     dword ptr [rax+rax+00h]
0x18000ded4  test    eax, eax
0x18000ded6  jnz     short loc_18000DEE4
0x18000ded8  call    cs:__imp_GetLastError
0x18000dedf  nop     dword ptr [rax+rax+00h]
0x18000dee4  test    r14, r14
0x18000dee7  jnz     short loc_18000DEAE
0x18000dee9  lea     rcx, [rdi+0F8h]; CriticalSection
0x18000def0  mov     qword ptr [rdi+38h], 0FFFFFFFFFFFFFFFFh
0x18000def8  mov     dword ptr [rdi+60h], 0FFFFFFFFh
0x18000deff  mov     qword ptr [rdi], 0
0x18000df06  call    cs:__imp_RtlDeleteCriticalSection
0x18000df0d  nop     dword ptr [rax+rax+00h]
0x18000df12  mov     rcx, [rdi+0F0h]
0x18000df19  test    rcx, rcx
0x18000df1c  jz      short loc_18000DF2A
0x18000df1e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000df25  nop     dword ptr [rax+rax+00h]
0x18000df2a  lea     rcx, [rdi+10h]
0x18000df2e  add     rsp, 28h
0x18000df32  pop     r14
0x18000df34  pop     rdi
0x18000df35  pop     rsi
0x18000df36  pop     rbx
0x18000df37  jmp     cs:__imp_InterlockedFlushSList
```
