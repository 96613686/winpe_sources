# CTreeLock::IsLockedByCurrentThread(void)

- ea: `0x1800533a0`
- end: `0x18005343a`
- name: `?IsLockedByCurrentThread@CTreeLock@@QEBA_NXZ`
- size: `154`
- prototype: `bool __fastcall(CTreeLock *__hidden this)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x1800210e4`
- `0x180047480`
- `0x180051770`
- `0x1800517e0`
- `0x180051840`
- `0x1800522a0`
- `0x180053750`
- `0x180053a30`
- `0x18018a110`

## callees

- `0x180050270`
- `0x1800533a0`
- `0x180202804`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800533c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800533c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800533d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800533d8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800533fc`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800533fc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800533b9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800533b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800533a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800533a9`

## pseudocode

```c
bool __fastcall CTreeLock::IsLockedByCurrentThread(CTreeLock *this)
{
  int v1; // ebx
  _DWORD *Value; // rbx
  HANDLE ProcessHeap; // rax
  CThreadContext *v4; // rax
  CThreadContext *v5; // rax

  v1 = *((_DWORD *)this + 2);
  if ( GetCurrentThreadId() == v1 )
    return 1;
  Value = TlsGetValue(CThreadContext::s_dwTlsIndex);
  if ( !Value )
  {
    ProcessHeap = GetProcessHeap();
    v4 = (CThreadContext *)HeapAlloc(ProcessHeap, 0, 0x1C0u);
    if ( !v4 || (v5 = CThreadContext::CThreadContext(v4), (Value = v5) == 0) )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0x28u, 0);
      return 0;
    }
    TlsSetValue(CThreadContext::s_dwTlsIndex, v5);
  }
  return Value[10] != 0;
}

```

## disassembly

```asm
0x1800533a0  push    rbx
0x1800533a2  sub     rsp, 30h
0x1800533a6  mov     ebx, [rcx+8]
0x1800533a9  call    cs:__imp_GetCurrentThreadId
0x1800533af  cmp     eax, ebx
0x1800533b1  jz      short loc_180053408
0x1800533b3  mov     ecx, cs:?s_dwTlsIndex@CThreadContext@@0KA; dwTlsIndex
0x1800533b9  call    cs:__imp_TlsGetValue
0x1800533bf  mov     rbx, rax
0x1800533c2  test    rax, rax
0x1800533c5  jnz     short loc_180053402
0x1800533c7  call    cs:__imp_GetProcessHeap
0x1800533cd  xor     edx, edx; dwFlags
0x1800533cf  mov     r8d, 1C0h; dwBytes
0x1800533d5  mov     rcx, rax; hHeap
0x1800533d8  call    cs:__imp_HeapAlloc
0x1800533de  test    rax, rax
0x1800533e1  jz      short loc_18005340C
0x1800533e3  mov     rcx, rax; this
0x1800533e6  call    ??0CThreadContext@@AEAA@XZ; CThreadContext::CThreadContext(void)
0x1800533eb  mov     rbx, rax
0x1800533ee  test    rax, rax
0x1800533f1  jz      short loc_18005340C
0x1800533f3  mov     ecx, cs:?s_dwTlsIndex@CThreadContext@@0KA; dwTlsIndex
0x1800533f9  mov     rdx, rax; lpTlsValue
0x1800533fc  call    cs:__imp_TlsSetValue
0x180053402  cmp     dword ptr [rbx+28h], 0
0x180053406  jbe     short loc_180053432
0x180053408  mov     al, 1
0x18005340a  jmp     short loc_180053434
0x18005340c  mov     [rsp+38h+var_10], 0; void *
0x180053415  mov     r9d, 8007000Eh; int
0x18005341b  xor     r8d, r8d; unsigned int
0x18005341e  mov     [rsp+38h+var_18], 28h ; '('; unsigned int
0x180053426  xor     edx, edx; int *
0x180053428  mov     ecx, 14h; unsigned int
0x18005342d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180053432  xor     al, al
0x180053434  add     rsp, 30h
0x180053438  pop     rbx
0x180053439  retn
```
