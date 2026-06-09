# MemProtectHeap::~MemProtectHeap(void)

- ea: `0x1803f118c`
- end: `0x1803f124d`
- name: `??1MemProtectHeap@@QEAA@XZ`
- size: `193`
- prototype: `void __fastcall(MemProtectHeap *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1804948c0`

## callees

- `0x18026c294`
- `0x180396ee0`
- `0x1803f118c`
- `0x1803f1254`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1803f11af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1803f11af`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1803f121e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1803f122f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1803f121e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1803f122f`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1803f11dc`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1803f11dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803f11f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803f11f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MemProtectHeap::~MemProtectHeap(MemProtectHeap *this)
{
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  if ( !*((_DWORD *)this + 13) && !*((_BYTE *)this + 86) )
    Memory::Recycler::ShutdownThread((MemProtectHeap *)((char *)this + 560));
  *((_BYTE *)this + 372) = 1;
  TlsFree(*(_DWORD *)this);
  if ( *((_DWORD *)this + 13) == 2 )
    CloseHandle(*((HANDLE *)this + 9));
  Memory::Recycler::~Recycler((MemProtectHeap *)((char *)this + 560));
  Memory::IdleDecommitPageAllocator::~IdleDecommitPageAllocator((MemProtectHeap *)((char *)this + 240));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
}

```

## disassembly

```asm
0x1803f118c  mov     rax, rsp
0x1803f118f  mov     [rax+8], rcx
0x1803f1193  push    rdi
0x1803f1194  sub     rsp, 30h
0x1803f1198  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x1803f11a0  mov     [rax+10h], rbx
0x1803f11a4  mov     [rax+18h], rsi
0x1803f11a8  mov     rbx, rcx
0x1803f11ab  lea     rcx, [rcx+60h]; lpCriticalSection
0x1803f11af  call    cs:__imp_EnterCriticalSection
0x1803f11b6  nop     dword ptr [rax+rax+00h]
0x1803f11bb  cmp     dword ptr [rbx+34h], 0
0x1803f11bf  jnz     short loc_1803F11D3
0x1803f11c1  cmp     byte ptr [rbx+56h], 0
0x1803f11c5  jnz     short loc_1803F11D3
0x1803f11c7  lea     rcx, [rbx+230h]; this
0x1803f11ce  call    ?ShutdownThread@Recycler@Memory@@QEAAXXZ; Memory::Recycler::ShutdownThread(void)
0x1803f11d3  mov     byte ptr [rbx+174h], 1
0x1803f11da  mov     ecx, [rbx]; dwTlsIndex
0x1803f11dc  call    cs:__imp_TlsFree
0x1803f11e3  nop     dword ptr [rax+rax+00h]
0x1803f11e8  cmp     dword ptr [rbx+34h], 2
0x1803f11ec  jnz     short loc_1803F11FE
0x1803f11ee  mov     rcx, [rbx+48h]; hObject
0x1803f11f2  call    cs:__imp_CloseHandle
0x1803f11f9  nop     dword ptr [rax+rax+00h]
0x1803f11fe  lea     rcx, [rbx+230h]; this
0x1803f1205  call    ??1Recycler@Memory@@QEAA@XZ; Memory::Recycler::~Recycler(void)
0x1803f120a  lea     rcx, [rbx+0F0h]; this
0x1803f1211  call    ??1IdleDecommitPageAllocator@Memory@@QEAA@XZ; Memory::IdleDecommitPageAllocator::~IdleDecommitPageAllocator(void)
0x1803f1216  nop
0x1803f1217  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x1803f121e  call    cs:__imp_DeleteCriticalSection
0x1803f1225  nop     dword ptr [rax+rax+00h]
0x1803f122a  nop
0x1803f122b  lea     rcx, [rbx+60h]; lpCriticalSection
0x1803f122f  call    cs:__imp_DeleteCriticalSection
0x1803f1236  nop     dword ptr [rax+rax+00h]
0x1803f123b  nop
0x1803f123c  mov     rbx, [rsp+38h+arg_8]
0x1803f1241  mov     rsi, [rsp+38h+arg_10]
0x1803f1246  add     rsp, 30h
0x1803f124a  pop     rdi
0x1803f124b  retn
```
