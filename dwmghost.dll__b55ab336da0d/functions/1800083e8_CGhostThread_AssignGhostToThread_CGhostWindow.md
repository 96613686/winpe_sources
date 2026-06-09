# CGhostThread::AssignGhostToThread(CGhostWindow *)

- ea: `0x1800083e8`
- end: `0x1800084c2`
- name: `?AssignGhostToThread@CGhostThread@@QEAAHPEAVCGhostWindow@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(CGhostThread *this, struct CGhostWindow *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180007e64`

## callees

- `0x180005bf4`
- `0x180005cb8`
- `0x180005d34`
- `0x1800061fc`
- `0x180006bac`
- `0x1800083e8`
- `0x180008558`
- `0x1800087f0`
- `0x180009f60`
- `0x180009f70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008455`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800084ad`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008455`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800084ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000848a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000848a`

## pseudocode

```c
__int64 __fastcall CGhostThread::AssignGhostToThread(CGhostThread *this, struct CGhostWindow *a2)
{
  unsigned int v4; // esi
  int v5; // r14d
  int State; // eax
  CDynamicCountedObjectArray *v7; // rcx
  int v8; // ebx
  CGhostWindow *v9; // rcx

  v4 = 0;
  v5 = 0;
  CLock::Acquire((LPCRITICAL_SECTION)((char *)this + 16));
  State = CGhostThread::GetState(this);
  if ( State == 1 )
  {
    v5 = 1;
  }
  else if ( State != 2 )
  {
    goto LABEL_10;
  }
  if ( CDynamicArray::GetCount((CGhostThread *)((char *)this + 112)) < 0x32
    && !(unsigned int)CDynamicCountedObjectArray::Find(v7, a2) )
  {
    if ( CDynamicCountedObjectArray::Add((CGhostThread *)((char *)this + 112), a2) )
    {
      SetEvent(*((HANDLE *)this + 8));
      v4 = 1;
      if ( v5 )
        CGhostThread::CreateWorkerThread(this);
    }
  }
LABEL_10:
  CLock::Release((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v4 )
  {
    if ( (unsigned int)CGhostThread::GetState(this) == 2 )
    {
      v8 = *((_DWORD *)this + 26);
      if ( GetCurrentThreadId() == v8
        && !(unsigned int)CGhostWindow::GetState(a2)
        && !(unsigned int)CGhostWindow::CreateGhostWindow(v9) )
      {
        SetEvent(*((HANDLE *)this + 8));
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800083e8  push    rbx
0x1800083ea  push    rbp
0x1800083eb  push    rsi
0x1800083ec  push    rdi
0x1800083ed  push    r14
0x1800083ef  push    r15
0x1800083f1  sub     rsp, 28h
0x1800083f5  mov     rdi, rcx
0x1800083f8  mov     rbp, rdx
0x1800083fb  add     rcx, 10h; lpCriticalSection
0x1800083ff  xor     esi, esi
0x180008401  xor     r14d, r14d
0x180008404  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x180008409  mov     rcx, rdi
0x18000840c  call    ?GetState@CGhostThread@@AEAA?AW4tagGHOSTTHREADSTATE@@XZ; CGhostThread::GetState(void)
0x180008411  mov     ecx, eax
0x180008413  sub     ecx, 1
0x180008416  jz      short loc_18000841F
0x180008418  cmp     ecx, 1
0x18000841b  jz      short loc_180008425
0x18000841d  jmp     short loc_18000846D
0x18000841f  mov     r14d, 1
0x180008425  lea     rbx, [rdi+70h]
0x180008429  mov     rcx, rbx; this
0x18000842c  call    ?GetCount@CDynamicArray@@QEBAKXZ; CDynamicArray::GetCount(void)
0x180008431  cmp     eax, 32h ; '2'
0x180008434  jnb     short loc_18000846D
0x180008436  mov     rdx, rbp; struct CCountedObject *
0x180008439  call    ?Find@CDynamicCountedObjectArray@@QEBAHPEBVCCountedObject@@@Z; CDynamicCountedObjectArray::Find(CCountedObject const *)
0x18000843e  test    eax, eax
0x180008440  jnz     short loc_18000846D
0x180008442  mov     rdx, rbp; struct CCountedObject *
0x180008445  mov     rcx, rbx; this
0x180008448  call    ?Add@CDynamicCountedObjectArray@@QEAAHPEAVCCountedObject@@@Z; CDynamicCountedObjectArray::Add(CCountedObject *)
0x18000844d  test    eax, eax
0x18000844f  jz      short loc_18000846D
0x180008451  mov     rcx, [rdi+40h]; hEvent
0x180008455  call    cs:__imp_SetEvent
0x18000845b  mov     esi, 1
0x180008460  test    r14d, r14d
0x180008463  jz      short loc_18000846D
0x180008465  mov     rcx, rdi; this
0x180008468  call    ?CreateWorkerThread@CGhostThread@@AEAAHXZ; CGhostThread::CreateWorkerThread(void)
0x18000846d  lea     rcx, [rdi+10h]; lpCriticalSection
0x180008471  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x180008476  test    esi, esi
0x180008478  jz      short loc_1800084B3
0x18000847a  mov     rcx, rdi
0x18000847d  call    ?GetState@CGhostThread@@AEAA?AW4tagGHOSTTHREADSTATE@@XZ; CGhostThread::GetState(void)
0x180008482  cmp     eax, 2
0x180008485  jnz     short loc_1800084B3
0x180008487  mov     ebx, [rdi+68h]
0x18000848a  call    cs:__imp_GetCurrentThreadId
0x180008490  cmp     eax, ebx
0x180008492  jnz     short loc_1800084B3
0x180008494  mov     rcx, rbp
0x180008497  call    ?GetState@CGhostWindow@@QEBA?AW4GHOSTSTATE@@XZ; CGhostWindow::GetState(void)
0x18000849c  test    eax, eax
0x18000849e  jnz     short loc_1800084B3
0x1800084a0  call    ?CreateGhostWindow@CGhostWindow@@QEAAHXZ; CGhostWindow::CreateGhostWindow(void)
0x1800084a5  test    eax, eax
0x1800084a7  jnz     short loc_1800084B3
0x1800084a9  mov     rcx, [rdi+40h]; hEvent
0x1800084ad  call    cs:__imp_SetEvent
0x1800084b3  mov     eax, esi
0x1800084b5  add     rsp, 28h
0x1800084b9  pop     r15
0x1800084bb  pop     r14
0x1800084bd  pop     rdi
0x1800084be  pop     rsi
0x1800084bf  pop     rbp
0x1800084c0  pop     rbx
0x1800084c1  retn
```
