# CGhostThread::~CGhostThread(void)

- ea: `0x180008314`
- end: `0x18000838b`
- name: `??1CGhostThread@@UEAA@XZ`
- size: `119`
- prototype: `void __fastcall(CGhostThread *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800083a0`

## callees

- `0x1800033c0`
- `0x180005a58`
- `0x180008314`
- `0x180009f50`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008357`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008357`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008330`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008366`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008330`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008366`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x18000833f`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x18000833f`

## pseudocode

```c
void __fastcall CGhostThread::~CGhostThread(CGhostThread *this)
{
  void *v2; // rcx
  HDESK v3; // rcx
  void *v4; // r8
  void *v5; // rcx

  *(_QWORD *)this = &CGhostThread::`vftable';
  v2 = (void *)*((_QWORD *)this + 12);
  if ( v2 )
    CloseHandle(v2);
  v3 = (HDESK)*((_QWORD *)this + 10);
  if ( v3 )
    CloseDesktop(v3);
  v4 = (void *)*((_QWORD *)this + 9);
  if ( v4 )
    HeapFree(g_hProcessHeap, 0, v4);
  v5 = (void *)*((_QWORD *)this + 8);
  if ( v5 )
    CloseHandle(v5);
  CDynamicCountedObjectArray::~CDynamicCountedObjectArray((CGhostThread *)((char *)this + 112));
  CLock::~CLock((LPCRITICAL_SECTION)((char *)this + 16));
  CCountedObject::~CCountedObject(this);
}

```

## disassembly

```asm
0x180008314  push    rbx
0x180008316  sub     rsp, 20h
0x18000831a  lea     rax, ??_7CGhostThread@@6B@; const CGhostThread::`vftable'
0x180008321  mov     rbx, rcx
0x180008324  mov     [rcx], rax
0x180008327  mov     rcx, [rcx+60h]; hObject
0x18000832b  test    rcx, rcx
0x18000832e  jz      short loc_180008336
0x180008330  call    cs:__imp_CloseHandle
0x180008336  mov     rcx, [rbx+50h]; hDesktop
0x18000833a  test    rcx, rcx
0x18000833d  jz      short loc_180008345
0x18000833f  call    cs:__imp_CloseDesktop
0x180008345  mov     r8, [rbx+48h]; lpMem
0x180008349  test    r8, r8
0x18000834c  jz      short loc_18000835D
0x18000834e  mov     rcx, cs:g_hProcessHeap; hHeap
0x180008355  xor     edx, edx; dwFlags
0x180008357  call    cs:__imp_HeapFree
0x18000835d  mov     rcx, [rbx+40h]; hObject
0x180008361  test    rcx, rcx
0x180008364  jz      short loc_18000836C
0x180008366  call    cs:__imp_CloseHandle
0x18000836c  lea     rcx, [rbx+70h]; this
0x180008370  call    ??1CDynamicCountedObjectArray@@UEAA@XZ; CDynamicCountedObjectArray::~CDynamicCountedObjectArray(void)
0x180008375  lea     rcx, [rbx+10h]; lpCriticalSection
0x180008379  call    ??1CLock@@QEAA@XZ; CLock::~CLock(void)
0x18000837e  mov     rcx, rbx; this
0x180008381  add     rsp, 20h
0x180008385  pop     rbx
0x180008386  jmp     ??1CCountedObject@@MEAA@XZ; CCountedObject::~CCountedObject(void)
```
