# CGhostThread::CleanupAllGhosts(int)

- ea: `0x1800084c8`
- end: `0x18000854f`
- name: `?CleanupAllGhosts@CGhostThread@@AEAAHH@Z`
- size: `135`
- prototype: `__int64 __fastcall(CGhostThread *__hidden this, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008558`
- `0x180008c10`

## callees

- `0x180005d04`
- `0x180005d34`
- `0x180006494`
- `0x180006bac`
- `0x1800084c8`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CGhostThread::CleanupAllGhosts(CGhostThread *this, int a2)
{
  CDynamicCountedObjectArray *v2; // rsi
  unsigned int v4; // edi
  unsigned int Count; // ebx
  struct CCountedObject *v6; // rax
  HWND *v7; // rdx
  int State; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx

  v2 = (CGhostThread *)((char *)this + 112);
  v4 = 1;
  Count = CDynamicArray::GetCount((CGhostThread *)((char *)this + 112));
  while ( Count )
  {
    v6 = CDynamicCountedObjectArray::Get(v2, --Count);
    State = CGhostWindow::GetState(v6);
    if ( State && (v9 = State - 1) != 0 && (v10 = v9 - 1) != 0 && (v11 = v10 - 1) != 0 )
    {
      if ( v11 == 1 )
        goto LABEL_11;
    }
    else
    {
      if ( CGhostWindow::DestroyGhostWindow(v7) )
        goto LABEL_11;
      v4 = 0;
    }
    if ( a2 )
LABEL_11:
      (*(void (__fastcall **)(CDynamicCountedObjectArray *, _QWORD))(*(_QWORD *)v2 + 16LL))(v2, Count);
  }
  return v4;
}

```

## disassembly

```asm
0x1800084c8  push    rbx
0x1800084ca  push    rbp
0x1800084cb  push    rsi
0x1800084cc  push    rdi
0x1800084cd  sub     rsp, 28h
0x1800084d1  lea     rsi, [rcx+70h]
0x1800084d5  mov     ebp, edx
0x1800084d7  mov     rcx, rsi; this
0x1800084da  mov     edi, 1
0x1800084df  call    ?GetCount@CDynamicArray@@QEBAKXZ; CDynamicArray::GetCount(void)
0x1800084e4  mov     ebx, eax
0x1800084e6  test    eax, eax
0x1800084e8  jz      short loc_180008544
0x1800084ea  dec     ebx
0x1800084ec  mov     rcx, rsi; this
0x1800084ef  mov     edx, ebx; unsigned int
0x1800084f1  call    ?Get@CDynamicCountedObjectArray@@QEAAPEAVCCountedObject@@K@Z; CDynamicCountedObjectArray::Get(ulong)
0x1800084f6  mov     rcx, rax
0x1800084f9  mov     rdx, rax
0x1800084fc  call    ?GetState@CGhostWindow@@QEBA?AW4GHOSTSTATE@@XZ; CGhostWindow::GetState(void)
0x180008501  mov     ecx, eax
0x180008503  test    eax, eax
0x180008505  jz      short loc_18000851D
0x180008507  sub     ecx, 1
0x18000850a  jz      short loc_18000851D
0x18000850c  sub     ecx, 1
0x18000850f  jz      short loc_18000851D
0x180008511  sub     ecx, 1
0x180008514  jz      short loc_18000851D
0x180008516  cmp     ecx, 1
0x180008519  jz      short loc_18000852F
0x18000851b  jmp     short loc_18000852B
0x18000851d  mov     rcx, rdx; this
0x180008520  call    ?DestroyGhostWindow@CGhostWindow@@QEAAHXZ; CGhostWindow::DestroyGhostWindow(void)
0x180008525  test    eax, eax
0x180008527  jnz     short loc_18000852F
0x180008529  xor     edi, edi
0x18000852b  test    ebp, ebp
0x18000852d  jz      short loc_180008540
0x18000852f  mov     rcx, [rsi]
0x180008532  mov     edx, ebx
0x180008534  mov     rax, [rcx+10h]
0x180008538  mov     rcx, rsi
0x18000853b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008540  test    ebx, ebx
0x180008542  jnz     short loc_1800084EA
0x180008544  mov     eax, edi
0x180008546  add     rsp, 28h
0x18000854a  pop     rdi
0x18000854b  pop     rsi
0x18000854c  pop     rbp
0x18000854d  pop     rbx
0x18000854e  retn
```
