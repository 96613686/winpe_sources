# CGhostProcess::UnfrostSiblings(void)

- ea: `0x180009944`
- end: `0x1800099cb`
- name: `?UnfrostSiblings@CGhostProcess@@QEAAHXZ`
- size: `135`
- prototype: `__int64 __fastcall(CGhostProcess *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180007190`
- `0x1800091e0`
- `0x18000a020`

## callees

- `0x180005d04`
- `0x180005d34`
- `0x180006494`
- `0x180009944`
- `0x180009f60`
- `0x180009f70`
- `0x18000c010`

## pseudocode

```c
_BOOL8 __fastcall CGhostProcess::UnfrostSiblings(CGhostProcess *this)
{
  unsigned int Count; // esi
  HWND *v3; // rax

  CLock::Acquire((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !*((_DWORD *)this + 16) && !*((_DWORD *)this + 30) && *((_DWORD *)this + 17) )
  {
    *((_DWORD *)this + 17) = 0;
    Count = CDynamicArray::GetCount((CGhostProcess *)((char *)this + 72));
    do
    {
      if ( !Count )
        break;
      v3 = (HWND *)CDynamicCountedObjectArray::Get((CGhostProcess *)((char *)this + 72), --Count);
      CGhostWindow::DestroyGhostWindow(v3);
      (*(void (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72, Count);
    }
    while ( !*((_DWORD *)this + 17) );
  }
  CLock::Release((LPCRITICAL_SECTION)((char *)this + 16));
  return *((_DWORD *)this + 17) == 0;
}

```

## disassembly

```asm
0x180009944  push    rbx
0x180009946  push    rsi
0x180009947  push    rdi
0x180009948  push    r14
0x18000994a  sub     rsp, 28h
0x18000994e  mov     rbx, rcx
0x180009951  add     rcx, 10h; lpCriticalSection
0x180009955  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x18000995a  cmp     dword ptr [rbx+40h], 0
0x18000995e  jnz     short loc_1800099B0
0x180009960  cmp     dword ptr [rbx+78h], 0
0x180009964  jnz     short loc_1800099B0
0x180009966  cmp     dword ptr [rbx+44h], 0
0x18000996a  jz      short loc_1800099B0
0x18000996c  lea     r14, [rbx+48h]
0x180009970  mov     dword ptr [rbx+44h], 0
0x180009977  mov     rcx, r14; this
0x18000997a  call    ?GetCount@CDynamicArray@@QEBAKXZ; CDynamicArray::GetCount(void)
0x18000997f  mov     esi, eax
0x180009981  test    esi, esi
0x180009983  jz      short loc_1800099B0
0x180009985  dec     esi
0x180009987  mov     rcx, r14; this
0x18000998a  mov     edx, esi; unsigned int
0x18000998c  call    ?Get@CDynamicCountedObjectArray@@QEAAPEAVCCountedObject@@K@Z; CDynamicCountedObjectArray::Get(ulong)
0x180009991  mov     rcx, rax; this
0x180009994  call    ?DestroyGhostWindow@CGhostWindow@@QEAAHXZ; CGhostWindow::DestroyGhostWindow(void)
0x180009999  mov     rdx, [r14]
0x18000999c  mov     rcx, r14
0x18000999f  mov     rax, [rdx+10h]
0x1800099a3  mov     edx, esi
0x1800099a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099aa  cmp     dword ptr [rbx+44h], 0
0x1800099ae  jz      short loc_180009981
0x1800099b0  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800099b4  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x1800099b9  xor     eax, eax
0x1800099bb  cmp     [rbx+44h], eax
0x1800099be  setz    al
0x1800099c1  add     rsp, 28h
0x1800099c5  pop     r14
0x1800099c7  pop     rdi
0x1800099c8  pop     rsi
0x1800099c9  pop     rbx
0x1800099ca  retn
```
