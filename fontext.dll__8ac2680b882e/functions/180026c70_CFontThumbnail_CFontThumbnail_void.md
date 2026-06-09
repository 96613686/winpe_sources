# CFontThumbnail::~CFontThumbnail(void)

- ea: `0x180026c70`
- end: `0x180026cc5`
- name: `??1CFontThumbnail@@AEAA@XZ`
- size: `85`
- prototype: `void __fastcall(CFontThumbnail *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027020`

## callees

- `0x180026c70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026cb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026cb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026ca4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026ca4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026c92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026c92`

## pseudocode

```c
void __fastcall CFontThumbnail::~CFontThumbnail(CFontThumbnail *this)
{
  void *v2; // rbx
  HANDLE ProcessHeap; // rax

  *(_QWORD *)this = &CFontThumbnail::`vftable'{for `IExtractImage'};
  *((_QWORD *)this + 1) = &CFontThumbnail::`vftable'{for `IInitializeWithFile'};
  CoTaskMemFree(*((LPVOID *)this + 4));
  v2 = (void *)*((_QWORD *)this + 138);
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  _InterlockedDecrement(&g_cRefCount);
}

```

## disassembly

```asm
0x180026c70  push    rbx
0x180026c72  sub     rsp, 20h
0x180026c76  lea     rax, ??_7CFontThumbnail@@6BIExtractImage@@@; const CFontThumbnail::`vftable'{for `IExtractImage'}
0x180026c7d  mov     rbx, rcx
0x180026c80  mov     [rcx], rax
0x180026c83  lea     rax, ??_7CFontThumbnail@@6BIInitializeWithFile@@@; const CFontThumbnail::`vftable'{for `IInitializeWithFile'}
0x180026c8a  mov     [rcx+8], rax
0x180026c8e  mov     rcx, [rcx+20h]; pv
0x180026c92  call    cs:__imp_CoTaskMemFree
0x180026c98  mov     rbx, [rbx+450h]
0x180026c9f  test    rbx, rbx
0x180026ca2  jz      short loc_180026CB8
0x180026ca4  call    cs:__imp_GetProcessHeap
0x180026caa  mov     r8, rbx; lpMem
0x180026cad  xor     edx, edx; dwFlags
0x180026caf  mov     rcx, rax; hHeap
0x180026cb2  call    cs:__imp_HeapFree
0x180026cb8  lock dec cs:?g_cRefCount@@3JA; long g_cRefCount
0x180026cbf  add     rsp, 20h
0x180026cc3  pop     rbx
0x180026cc4  retn
```
