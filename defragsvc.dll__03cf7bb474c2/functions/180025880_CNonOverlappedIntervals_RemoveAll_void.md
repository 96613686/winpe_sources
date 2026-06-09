# CNonOverlappedIntervals::RemoveAll(void)

- ea: `0x180025880`
- end: `0x1800258e2`
- name: `?RemoveAll@CNonOverlappedIntervals@@UEAAJXZ`
- size: `98`
- prototype: `__int64 __fastcall(CNonOverlappedIntervals *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180025880`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800258d0`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800258d0`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800258c2`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800258c2`

## pseudocode

```c
__int64 __fastcall CNonOverlappedIntervals::RemoveAll(CNonOverlappedIntervals *this)
{
  void *v2; // rcx

  (**((void (__fastcall ***)(char *))this + 9))((char *)this + 72);
  (**((void (__fastcall ***)(char *))this + 13))((char *)this + 104);
  v2 = (void *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  if ( v2 )
  {
    HeapDestroy(v2);
    *((_QWORD *)this + 8) = HeapCreate(1u, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180025880  push    rbx
0x180025882  sub     rsp, 20h
0x180025886  mov     rbx, rcx
0x180025889  add     rcx, 48h ; 'H'
0x18002588d  mov     rax, [rcx]
0x180025890  mov     rax, [rax]
0x180025893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025898  lea     rcx, [rbx+68h]
0x18002589c  mov     rax, [rcx]
0x18002589f  mov     rax, [rax]
0x1800258a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258a7  mov     rcx, [rbx+40h]; hHeap
0x1800258ab  xor     eax, eax
0x1800258ad  mov     [rbx+30h], rax
0x1800258b1  mov     [rbx+18h], rax
0x1800258b5  mov     [rbx+20h], rax
0x1800258b9  mov     [rbx+28h], rax
0x1800258bd  test    rcx, rcx
0x1800258c0  jz      short loc_1800258DA
0x1800258c2  call    cs:__imp_HeapDestroy
0x1800258c8  xor     edx, edx; dwInitialSize
0x1800258ca  xor     r8d, r8d; dwMaximumSize
0x1800258cd  lea     ecx, [rdx+1]; flOptions
0x1800258d0  call    cs:__imp_HeapCreate
0x1800258d6  mov     [rbx+40h], rax
0x1800258da  xor     eax, eax
0x1800258dc  add     rsp, 20h
0x1800258e0  pop     rbx
0x1800258e1  retn
```
