# CQueue::~CQueue(void)

- ea: `0x18001db14`
- end: `0x18001dbea`
- name: `??1CQueue@@MEAA@XZ`
- size: `214`
- prototype: `void __fastcall(CQueue *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001dcb0`

## callees

- `0x18000f430`
- `0x18001da78`
- `0x18001db14`
- `0x180033de8`

## import_xrefs

- `msvcrt!free` at `0x18001db32`
- `msvcrt!free` at `0x18001db3d`
- `msvcrt!free` at `0x18001db4b`
- `msvcrt!free` at `0x18001db59`
- `msvcrt!free` at `0x18001dbd3`
- `msvcrt!free` at `0x18001db32`
- `msvcrt!free` at `0x18001db3d`
- `msvcrt!free` at `0x18001db4b`
- `msvcrt!free` at `0x18001db59`
- `msvcrt!free` at `0x18001dbd3`
- `ADVAPI32!PerfDeleteInstance` at `0x18001db91`
- `ADVAPI32!PerfDeleteInstance` at `0x18001db91`
- `KERNEL32!DeleteCriticalSection` at `0x18001dbb3`
- `KERNEL32!DeleteCriticalSection` at `0x18001dbbe`
- `KERNEL32!DeleteCriticalSection` at `0x18001dbb3`
- `KERNEL32!DeleteCriticalSection` at `0x18001dbbe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CQueue::~CQueue(CQueue *this)
{
  CPerf *v2; // rcx
  struct _PERF_COUNTERSET_INSTANCE *v3; // rdx

  *(_QWORD *)this = &CQueue::`vftable';
  *((_DWORD *)this + 13) = 0;
  free(*((void **)this + 3));
  free(*((void **)this + 4));
  free(*((void **)this + 21));
  free(*((void **)this + 22));
  CPerf::RemoveInstance(v2, (wchar_t *)L"MSMQ Queue", *((void **)this + 29));
  *((_QWORD *)this + 29) = 0;
  v3 = (struct _PERF_COUNTERSET_INSTANCE *)*((_QWORD *)this + 30);
  if ( v3 )
  {
    PerfDeleteInstance(msmq, v3);
    *((_QWORD *)this + 30) = 0;
  }
  CircularBuffer<ConnectionStateRecord>::~CircularBuffer<ConnectionStateRecord>((char *)this + 248);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  SafeRelease<CSockTransport>(*((_QWORD *)this + 8));
  free(*((void **)this + 7));
  *(_QWORD *)this = &CBaseQueue::`vftable';
}

```

## disassembly

```asm
0x18001db14  push    rbx
0x18001db16  sub     rsp, 20h
0x18001db1a  mov     rbx, rcx
0x18001db1d  lea     rax, ??_7CQueue@@6B@; const CQueue::`vftable'
0x18001db24  mov     [rcx], rax
0x18001db27  mov     dword ptr [rcx+34h], 0
0x18001db2e  mov     rcx, [rcx+18h]; Block
0x18001db32  call    cs:__imp_free
0x18001db38  nop
0x18001db39  mov     rcx, [rbx+20h]; Block
0x18001db3d  call    cs:__imp_free
0x18001db43  nop
0x18001db44  mov     rcx, [rbx+0A8h]; Block
0x18001db4b  call    cs:__imp_free
0x18001db51  nop
0x18001db52  mov     rcx, [rbx+0B0h]; Block
0x18001db59  call    cs:__imp_free
0x18001db5f  nop
0x18001db60  mov     r8, [rbx+0E8h]; void *
0x18001db67  lea     rdx, aMsmqQueue; "MSMQ Queue"
0x18001db6e  call    ?RemoveInstance@CPerf@@QEAAHPEA_WPEAX@Z; CPerf::RemoveInstance(wchar_t *,void *)
0x18001db73  mov     qword ptr [rbx+0E8h], 0
0x18001db7e  mov     rdx, [rbx+0F0h]; InstanceBlock
0x18001db85  test    rdx, rdx
0x18001db88  jz      short loc_18001DBA2
0x18001db8a  mov     rcx, cs:msmq; Provider
0x18001db91  call    cs:__imp_PerfDeleteInstance
0x18001db97  mov     qword ptr [rbx+0F0h], 0
0x18001dba2  lea     rcx, [rbx+0F8h]
0x18001dba9  call    ??1?$CircularBuffer@VConnectionStateRecord@@@@QEAA@XZ; CircularBuffer<ConnectionStateRecord>::~CircularBuffer<ConnectionStateRecord>(void)
0x18001dbae  nop
0x18001dbaf  lea     rcx, [rbx+70h]; lpCriticalSection
0x18001dbb3  call    cs:__imp_DeleteCriticalSection
0x18001dbb9  nop
0x18001dbba  lea     rcx, [rbx+48h]; lpCriticalSection
0x18001dbbe  call    cs:__imp_DeleteCriticalSection
0x18001dbc4  nop
0x18001dbc5  mov     rcx, [rbx+40h]
0x18001dbc9  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x18001dbce  nop
0x18001dbcf  mov     rcx, [rbx+38h]; Block
0x18001dbd3  call    cs:__imp_free
0x18001dbd9  nop
0x18001dbda  lea     rax, ??_7CBaseQueue@@6B@; const CBaseQueue::`vftable'
0x18001dbe1  mov     [rbx], rax
0x18001dbe4  add     rsp, 20h
0x18001dbe8  pop     rbx
0x18001dbe9  retn
```
