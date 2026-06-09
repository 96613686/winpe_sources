# FreeAepContainerEntry(_AEP_CONTAINER_ENTRY *)

- ea: `0x180035f14`
- end: `0x180035fab`
- name: `?FreeAepContainerEntry@@YAXPEAU_AEP_CONTAINER_ENTRY@@@Z`
- size: `151`
- prototype: `void __fastcall(struct _AEP_CONTAINER_ENTRY *lpMem)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800154b4`
- `0x1800359c0`
- `0x180050884`

## callees

- `0x180016f70`
- `0x180035f14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035f7f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035f7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035f33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035f85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035f33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035f85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035f41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035f93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035f41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035f93`

## pseudocode

```c
void __fastcall FreeAepContainerEntry(struct _RTL_CRITICAL_SECTION *lpMem)
{
  HANDLE OwningThread; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE *p_LockSemaphore; // rbx
  struct _AEP_ENTRY *v5; // rax
  _QWORD *v6; // rcx
  HANDLE v7; // rax

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
    while ( 1 )
    {
      v5 = (struct _AEP_ENTRY *)*p_LockSemaphore;
      if ( *((HANDLE **)*p_LockSemaphore + 1) != p_LockSemaphore
        || (v6 = *(_QWORD **)v5, *(struct _AEP_ENTRY **)(*(_QWORD *)v5 + 8LL) != v5) )
      {
        __fastfail(3u);
      }
      *p_LockSemaphore = v6;
      v6[1] = p_LockSemaphore;
      if ( v5 == (struct _AEP_ENTRY *)p_LockSemaphore )
        break;
      FreeAepEntry(v5);
    }
    DeleteCriticalSection(lpMem + 1);
    v7 = GetProcessHeap();
    HeapFree(v7, 0, lpMem);
  }
}

```

## disassembly

```asm
0x180035f14  test    rcx, rcx
0x180035f17  jz      locret_180035FA3
0x180035f1d  mov     [rsp+arg_0], rbx
0x180035f22  push    rdi
0x180035f23  sub     rsp, 20h
0x180035f27  mov     rbx, [rcx+10h]
0x180035f2b  mov     rdi, rcx
0x180035f2e  test    rbx, rbx
0x180035f31  jz      short loc_180035F4F
0x180035f33  call    cs:__imp_GetProcessHeap
0x180035f39  mov     r8, rbx; lpMem
0x180035f3c  xor     edx, edx; dwFlags
0x180035f3e  mov     rcx, rax; hHeap
0x180035f41  call    cs:__imp_HeapFree
0x180035f47  mov     qword ptr [rdi+10h], 0
0x180035f4f  lea     rbx, [rdi+18h]
0x180035f53  jmp     short loc_180035F5D
0x180035f55  mov     rcx, rax; lpMem
0x180035f58  call    ?FreeAepEntry@@YAXPEAU_AEP_ENTRY@@@Z; FreeAepEntry(_AEP_ENTRY *)
0x180035f5d  mov     rax, [rbx]
0x180035f60  cmp     [rax+8], rbx
0x180035f64  jnz     short loc_180035FA4
0x180035f66  mov     rcx, [rax]
0x180035f69  cmp     [rcx+8], rax
0x180035f6d  jnz     short loc_180035FA4
0x180035f6f  mov     [rbx], rcx
0x180035f72  mov     [rcx+8], rbx
0x180035f76  cmp     rax, rbx
0x180035f79  jnz     short loc_180035F55
0x180035f7b  lea     rcx, [rdi+28h]; lpCriticalSection
0x180035f7f  call    cs:__imp_DeleteCriticalSection
0x180035f85  call    cs:__imp_GetProcessHeap
0x180035f8b  mov     r8, rdi; lpMem
0x180035f8e  xor     edx, edx; dwFlags
0x180035f90  mov     rcx, rax; hHeap
0x180035f93  call    cs:__imp_HeapFree
0x180035f99  mov     rbx, [rsp+28h+arg_0]
0x180035f9e  add     rsp, 20h
0x180035fa2  pop     rdi
0x180035fa3  retn
0x180035fa4  mov     ecx, 3
0x180035fa9  int     29h; Win8: RtlFailFast(ecx)
```
