# SocketBrokerContext::~SocketBrokerContext(void)

- ea: `0x180026164`
- end: `0x1800261ab`
- name: `??1SocketBrokerContext@@QEAA@XZ`
- size: `71`
- prototype: `void __fastcall(SocketBrokerContext *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001ebc`

## callees

- `0x180003ed0`
- `0x180017804`
- `0x180026164`
- `0x18002666c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002619e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002619e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026194`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026194`

## pseudocode

```c
void __fastcall SocketBrokerContext::~SocketBrokerContext(SocketBrokerContext *this)
{
  void *v2; // rcx

  SocketBrokerContext::CleanupSockets(this);
  SocketBrokerContext::DeletePushEnableContext(this);
  VpnFree(*((LPVOID *)this + 6));
  *((_QWORD *)this + 6) = 0;
  v2 = (void *)*((_QWORD *)this + 7);
  if ( v2 )
    CloseHandle(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
}

```

## disassembly

```asm
0x180026164  push    rbx
0x180026166  sub     rsp, 20h
0x18002616a  mov     rbx, rcx
0x18002616d  call    ?CleanupSockets@SocketBrokerContext@@QEAAXXZ; SocketBrokerContext::CleanupSockets(void)
0x180026172  mov     rcx, rbx; this
0x180026175  call    ?DeletePushEnableContext@SocketBrokerContext@@AEAAKXZ; SocketBrokerContext::DeletePushEnableContext(void)
0x18002617a  mov     rcx, [rbx+30h]; lpMem
0x18002617e  call    VpnFree
0x180026183  mov     qword ptr [rbx+30h], 0
0x18002618b  mov     rcx, [rbx+38h]; hObject
0x18002618f  test    rcx, rcx
0x180026192  jz      short loc_18002619A
0x180026194  call    cs:__imp_CloseHandle
0x18002619a  lea     rcx, [rbx+40h]; lpCriticalSection
0x18002619e  call    cs:__imp_DeleteCriticalSection
0x1800261a4  nop
0x1800261a5  add     rsp, 20h
0x1800261a9  pop     rbx
0x1800261aa  retn
```
