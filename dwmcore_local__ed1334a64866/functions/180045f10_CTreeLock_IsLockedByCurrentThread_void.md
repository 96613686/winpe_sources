# CTreeLock::IsLockedByCurrentThread(void)

- ea: `0x180045f10`
- end: `0x180045faa`
- name: `?IsLockedByCurrentThread@CTreeLock@@QEBA_NXZ`
- size: `154`
- prototype: `bool __fastcall(CTreeLock *__hidden this)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180011ca4`
- `0x180036600`
- `0x1800442e0`
- `0x180044350`
- `0x1800443b0`
- `0x180044e10`
- `0x1800462c0`
- `0x1800465a0`
- `0x180188820`

## callees

- `0x180042de0`
- `0x180045f10`
- `0x1802027e4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045f37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045f37`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045f48`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045f48`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180045f6c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180045f6c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045f29`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045f29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045f19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045f19`

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
0x180045f10  push    rbx
0x180045f12  sub     rsp, 30h
0x180045f16  mov     ebx, [rcx+8]
0x180045f19  call    cs:__imp_GetCurrentThreadId
0x180045f1f  cmp     eax, ebx
0x180045f21  jz      short loc_180045F78
0x180045f23  mov     ecx, cs:?s_dwTlsIndex@CThreadContext@@0KA; dwTlsIndex
0x180045f29  call    cs:__imp_TlsGetValue
0x180045f2f  mov     rbx, rax
0x180045f32  test    rax, rax
0x180045f35  jnz     short loc_180045F72
0x180045f37  call    cs:__imp_GetProcessHeap
0x180045f3d  xor     edx, edx; dwFlags
0x180045f3f  mov     r8d, 1C0h; dwBytes
0x180045f45  mov     rcx, rax; hHeap
0x180045f48  call    cs:__imp_HeapAlloc
0x180045f4e  test    rax, rax
0x180045f51  jz      short loc_180045F7C
0x180045f53  mov     rcx, rax; this
0x180045f56  call    ??0CThreadContext@@AEAA@XZ; CThreadContext::CThreadContext(void)
0x180045f5b  mov     rbx, rax
0x180045f5e  test    rax, rax
0x180045f61  jz      short loc_180045F7C
0x180045f63  mov     ecx, cs:?s_dwTlsIndex@CThreadContext@@0KA; dwTlsIndex
0x180045f69  mov     rdx, rax; lpTlsValue
0x180045f6c  call    cs:__imp_TlsSetValue
0x180045f72  cmp     dword ptr [rbx+28h], 0
0x180045f76  jbe     short loc_180045FA2
0x180045f78  mov     al, 1
0x180045f7a  jmp     short loc_180045FA4
0x180045f7c  mov     [rsp+38h+var_10], 0; void *
0x180045f85  mov     r9d, 8007000Eh; int
0x180045f8b  xor     r8d, r8d; unsigned int
0x180045f8e  mov     [rsp+38h+var_18], 28h ; '('; unsigned int
0x180045f96  xor     edx, edx; int *
0x180045f98  mov     ecx, 14h; unsigned int
0x180045f9d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180045fa2  xor     al, al
0x180045fa4  add     rsp, 30h
0x180045fa8  pop     rbx
0x180045fa9  retn
```
