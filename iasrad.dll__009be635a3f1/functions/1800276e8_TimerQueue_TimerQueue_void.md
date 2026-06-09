# TimerQueue::~TimerQueue(void)

- ea: `0x1800276e8`
- end: `0x180027723`
- name: `??1TimerQueue@@QEAA@XZ`
- size: `59`
- prototype: `void __fastcall(TimerQueue *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180020fdc`

## callees

- `0x1800276c4`
- `0x1800278d8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002771c`
- `KERNEL32!CloseHandle` at `0x180027703`
- `KERNEL32!CloseHandle` at `0x18002770d`
- `KERNEL32!CloseHandle` at `0x180027703`
- `KERNEL32!CloseHandle` at `0x18002770d`

## pseudocode

```c
void __fastcall TimerQueue::~TimerQueue(TimerQueue *this)
{
  TimerQueue::cancelAllTimers(this);
  std::_Tree<std::_Tmap_traits<unsigned __int64,Timer *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Timer *>>,1>>::~_Tree<std::_Tmap_traits<unsigned __int64,Timer *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Timer *>>,1>>((char *)this + 64);
  CloseHandle(*((HANDLE *)this + 7));
  CloseHandle(*((HANDLE *)this + 6));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x1800276e8  push    rbx
0x1800276ea  sub     rsp, 20h
0x1800276ee  mov     rbx, rcx
0x1800276f1  call    ?cancelAllTimers@TimerQueue@@QEAAXXZ; TimerQueue::cancelAllTimers(void)
0x1800276f6  lea     rcx, [rbx+40h]
0x1800276fa  call    ??1?$_Tree@V?$_Tmap_traits@_KPEAVTimer@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAVTimer@@@std@@@3@$00@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<unsigned __int64,Timer *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Timer *>>,1>>::~_Tree<std::_Tmap_traits<unsigned __int64,Timer *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Timer *>>,1>>(void)
0x1800276ff  mov     rcx, [rbx+38h]; hObject
0x180027703  call    cs:__imp_CloseHandle
0x180027709  mov     rcx, [rbx+30h]; hObject
0x18002770d  call    cs:__imp_CloseHandle
0x180027713  lea     rcx, [rbx+8]
0x180027717  add     rsp, 20h
0x18002771b  pop     rbx
0x18002771c  jmp     cs:__imp_DeleteCriticalSection
```
