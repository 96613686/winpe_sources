# CGhostThread::DoGhostThreadStuff(void)

- ea: `0x1800086b8`
- end: `0x1800087ea`
- name: `?DoGhostThreadStuff@CGhostThread@@AEAAHXZ`
- size: `306`
- prototype: `__int64 __fastcall(CGhostThread *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180008970`

## callees

- `0x1800059f4`
- `0x180005bf4`
- `0x180005d04`
- `0x180005d34`
- `0x1800061fc`
- `0x180006494`
- `0x180006bac`
- `0x1800086b8`
- `0x180009f60`
- `0x180009f70`
- `0x18000a844`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800087ac`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800087ac`

## pseudocode

```c
__int64 __fastcall CGhostThread::DoGhostThreadStuff(CGhostThread *this)
{
  unsigned int v2; // r14d
  CDynamicCountedObjectArray *v3; // rax
  CDynamicCountedObjectArray *v4; // rbx
  unsigned int Count; // edi
  struct CCountedObject *v6; // rax
  struct CCountedObject *v7; // rdx
  int State; // ecx
  int v9; // ecx
  unsigned int i; // edi
  HWND *v11; // rax

  v2 = 0;
  CLock::Acquire((LPCRITICAL_SECTION)((char *)this + 16));
  if ( *((_DWORD *)this + 14) == 2 && (v3 = (CDynamicCountedObjectArray *)operator new(0x20u)) != 0 )
  {
    v4 = CDynamicCountedObjectArray::CDynamicCountedObjectArray(v3);
    if ( v4 )
    {
      Count = CDynamicArray::GetCount((CGhostThread *)((char *)this + 112));
      while ( Count )
      {
        v6 = CDynamicCountedObjectArray::Get((CGhostThread *)((char *)this + 112), --Count);
        State = CGhostWindow::GetState(v6);
        if ( !State )
        {
          CDynamicCountedObjectArray::Add(v4, v7);
          continue;
        }
        v9 = State - 3;
        if ( v9 )
        {
          if ( v9 == 1 )
            goto LABEL_10;
        }
        else if ( CGhostWindow::DestroyGhostWindow((HWND *)v7) )
        {
LABEL_10:
          (*(void (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 14) + 16LL))((char *)this + 112, Count);
          v2 = 1;
        }
      }
    }
  }
  else
  {
    v4 = 0;
  }
  CLock::Release((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v4 )
  {
    for ( i = CDynamicArray::GetCount(v4);
          i;
          (*(void (__fastcall **)(CDynamicCountedObjectArray *, _QWORD))(*(_QWORD *)v4 + 16LL))(v4, i) )
    {
      v11 = (HWND *)CDynamicCountedObjectArray::Get(v4, --i);
      if ( (unsigned int)CGhostWindow::CreateGhostWindow(v11) )
        v2 = 1;
      else
        SetEvent(*((HANDLE *)this + 8));
    }
    (**(void (__fastcall ***)(CDynamicCountedObjectArray *, __int64))v4)(v4, 1);
  }
  return v2;
}

```

## disassembly

```asm
0x1800086b8  push    rbx
0x1800086ba  push    rbp
0x1800086bb  push    rsi
0x1800086bc  push    rdi
0x1800086bd  push    r14
0x1800086bf  push    r15
0x1800086c1  sub     rsp, 28h
0x1800086c5  mov     rbp, rcx
0x1800086c8  xor     r14d, r14d
0x1800086cb  add     rcx, 10h; lpCriticalSection
0x1800086cf  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x1800086d4  cmp     dword ptr [rbp+38h], 2
0x1800086d8  jnz     loc_18000876A
0x1800086de  lea     ecx, [r14+20h]; unsigned __int64
0x1800086e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800086e7  test    rax, rax
0x1800086ea  jz      short loc_18000876A
0x1800086ec  mov     rcx, rax; this
0x1800086ef  call    ??0CDynamicCountedObjectArray@@QEAA@XZ; CDynamicCountedObjectArray::CDynamicCountedObjectArray(void)
0x1800086f4  mov     rbx, rax
0x1800086f7  test    rax, rax
0x1800086fa  jz      short loc_18000876C
0x1800086fc  lea     rsi, [rbp+70h]
0x180008700  mov     rcx, rsi; this
0x180008703  call    ?GetCount@CDynamicArray@@QEBAKXZ; CDynamicArray::GetCount(void)
0x180008708  mov     edi, eax
0x18000870a  test    eax, eax
0x18000870c  jz      short loc_18000876C
0x18000870e  dec     edi
0x180008710  mov     rcx, rsi; this
0x180008713  mov     edx, edi; unsigned int
0x180008715  call    ?Get@CDynamicCountedObjectArray@@QEAAPEAVCCountedObject@@K@Z; CDynamicCountedObjectArray::Get(ulong)
0x18000871a  mov     rcx, rax
0x18000871d  mov     rdx, rax
0x180008720  call    ?GetState@CGhostWindow@@QEBA?AW4GHOSTSTATE@@XZ; CGhostWindow::GetState(void)
0x180008725  mov     ecx, eax
0x180008727  test    eax, eax
0x180008729  jz      short loc_18000875C
0x18000872b  sub     ecx, 3
0x18000872e  jz      short loc_180008737
0x180008730  cmp     ecx, 1
0x180008733  jnz     short loc_180008764
0x180008735  jmp     short loc_180008743
0x180008737  mov     rcx, rdx; this
0x18000873a  call    ?DestroyGhostWindow@CGhostWindow@@QEAAHXZ; CGhostWindow::DestroyGhostWindow(void)
0x18000873f  test    eax, eax
0x180008741  jz      short loc_180008764
0x180008743  mov     rax, [rsi]
0x180008746  mov     edx, edi
0x180008748  mov     rcx, rsi
0x18000874b  mov     rax, [rax+10h]
0x18000874f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008754  mov     r14d, 1
0x18000875a  jmp     short loc_180008764
0x18000875c  mov     rcx, rbx; this
0x18000875f  call    ?Add@CDynamicCountedObjectArray@@QEAAHPEAVCCountedObject@@@Z; CDynamicCountedObjectArray::Add(CCountedObject *)
0x180008764  test    edi, edi
0x180008766  jnz     short loc_18000870E
0x180008768  jmp     short loc_18000876C
0x18000876a  xor     ebx, ebx
0x18000876c  lea     rcx, [rbp+10h]; lpCriticalSection
0x180008770  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x180008775  test    rbx, rbx
0x180008778  jz      short loc_1800087DA
0x18000877a  mov     rcx, rbx; this
0x18000877d  call    ?GetCount@CDynamicArray@@QEBAKXZ; CDynamicArray::GetCount(void)
0x180008782  mov     edi, eax
0x180008784  test    eax, eax
0x180008786  jz      short loc_1800087C7
0x180008788  dec     edi
0x18000878a  mov     rcx, rbx; this
0x18000878d  mov     edx, edi; unsigned int
0x18000878f  call    ?Get@CDynamicCountedObjectArray@@QEAAPEAVCCountedObject@@K@Z; CDynamicCountedObjectArray::Get(ulong)
0x180008794  mov     rcx, rax; this
0x180008797  call    ?CreateGhostWindow@CGhostWindow@@QEAAHXZ; CGhostWindow::CreateGhostWindow(void)
0x18000879c  test    eax, eax
0x18000879e  jz      short loc_1800087A8
0x1800087a0  mov     r14d, 1
0x1800087a6  jmp     short loc_1800087B2
0x1800087a8  mov     rcx, [rbp+40h]; hEvent
0x1800087ac  call    cs:__imp_SetEvent
0x1800087b2  mov     rax, [rbx]
0x1800087b5  mov     edx, edi
0x1800087b7  mov     rcx, rbx
0x1800087ba  mov     rax, [rax+10h]
0x1800087be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087c3  test    edi, edi
0x1800087c5  jnz     short loc_180008788
0x1800087c7  mov     r8, [rbx]
0x1800087ca  mov     edx, 1
0x1800087cf  mov     rcx, rbx
0x1800087d2  mov     rax, [r8]
0x1800087d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087da  mov     eax, r14d
0x1800087dd  add     rsp, 28h
0x1800087e1  pop     r15
0x1800087e3  pop     r14
0x1800087e5  pop     rdi
0x1800087e6  pop     rsi
0x1800087e7  pop     rbp
0x1800087e8  pop     rbx
0x1800087e9  retn
```
