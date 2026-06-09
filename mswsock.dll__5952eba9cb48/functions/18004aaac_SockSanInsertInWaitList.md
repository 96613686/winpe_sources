# SockSanInsertInWaitList

- ea: `0x18004aaac`
- end: `0x18004abc9`
- name: `SockSanInsertInWaitList`
- size: `285`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180044f0c`
- `0x18004e7fc`

## callees

- `0x1800052a0`
- `0x18004aaac`

## import_xrefs

- `ntdll!NtCreateEvent` at `0x18004ab41`
- `ntdll!NtCreateEvent` at `0x18004ab41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004abad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004abad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004aac6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004aac6`

## pseudocode

```c
__int64 __fastcall SockSanInsertInWaitList(__int64 a1, int *a2)
{
  int v4; // ebx
  void **v5; // rcx
  NTSTATUS Event; // eax
  unsigned int v7; // ebp
  _QWORD *v8; // rax

  EnterCriticalSection(&ConnCritSec);
  v4 = 0;
  if ( (int)SockSanNumWaitEvents > 0 )
  {
    do
    {
      if ( !ConnectData[v4 + 64] )
        break;
      ++v4;
    }
    while ( v4 < (int)SockSanNumWaitEvents );
    if ( v4 >= 64 )
    {
      v4 = SockSanNextIdx % 64;
      ++SockSanNextIdx;
    }
  }
  v5 = &ConnectData[v4];
  if ( !*v5 )
  {
    Event = NtCreateEvent(v5, 0x1F0003u, 0, SynchronizationEvent, 0);
    if ( Event < 0 )
    {
      v7 = NtStatusToSocketError((unsigned int)Event);
      goto LABEL_13;
    }
    ++SockSanNumWaitEvents;
  }
  v7 = 0;
  *(_DWORD *)(a1 + 172) = v4;
  *(_QWORD *)(a1 + 944) = 0;
  *(_QWORD *)(a1 + 936) = ConnectData[v4 + 64];
  v8 = ConnectData[v4 + 64];
  if ( v8 )
    v8[118] = a1;
  ConnectData[v4 + 64] = (HANDLE)a1;
  _InterlockedIncrement(*(volatile signed __int32 **)(a1 + 8));
  *a2 = v4;
LABEL_13:
  LeaveCriticalSection(&ConnCritSec);
  return v7;
}

```

## disassembly

```asm
0x18004aaac  push    rbx
0x18004aaae  push    rbp
0x18004aaaf  push    rsi
0x18004aab0  push    rdi
0x18004aab1  push    r13
0x18004aab3  push    r14
0x18004aab5  sub     rsp, 38h
0x18004aab9  mov     rdi, rcx
0x18004aabc  mov     r14, rdx
0x18004aabf  lea     rcx, ConnCritSec; lpCriticalSection
0x18004aac6  call    cs:__imp_EnterCriticalSection
0x18004aacd  nop     dword ptr [rax+rax+00h]
0x18004aad2  mov     ecx, cs:SockSanNumWaitEvents
0x18004aad8  lea     r13, ConnectData
0x18004aadf  xor     ebx, ebx
0x18004aae1  test    ecx, ecx
0x18004aae3  jle     short loc_18004AB1A
0x18004aae5  movsxd  rax, ebx
0x18004aae8  cmp     qword ptr [r13+rax*8+200h], 0
0x18004aaf1  jz      short loc_18004AAF9
0x18004aaf3  inc     ebx
0x18004aaf5  cmp     ebx, ecx
0x18004aaf7  jl      short loc_18004AAE5
0x18004aaf9  mov     r8d, 40h ; '@'
0x18004aaff  cmp     ebx, r8d
0x18004ab02  jl      short loc_18004AB1A
0x18004ab04  mov     ecx, cs:SockSanNextIdx
0x18004ab0a  mov     eax, ecx
0x18004ab0c  cdq
0x18004ab0d  idiv    r8d
0x18004ab10  inc     ecx
0x18004ab12  mov     ebx, edx
0x18004ab14  mov     cs:SockSanNextIdx, ecx
0x18004ab1a  movsxd  rsi, ebx
0x18004ab1d  lea     rcx, ds:0[rsi*8]
0x18004ab25  add     rcx, r13; EventHandle
0x18004ab28  cmp     qword ptr [rcx], 0
0x18004ab2c  jnz     short loc_18004AB62
0x18004ab2e  mov     r9d, 1; EventType
0x18004ab34  mov     [rsp+68h+InitialState], 0; InitialState
0x18004ab39  xor     r8d, r8d; ObjectAttributes
0x18004ab3c  mov     edx, 1F0003h; DesiredAccess
0x18004ab41  call    cs:__imp_NtCreateEvent
0x18004ab48  nop     dword ptr [rax+rax+00h]
0x18004ab4d  test    eax, eax
0x18004ab4f  jns     short loc_18004AB5C
0x18004ab51  mov     ecx, eax
0x18004ab53  call    NtStatusToSocketError
0x18004ab58  mov     ebp, eax
0x18004ab5a  jmp     short loc_18004ABA6
0x18004ab5c  inc     cs:SockSanNumWaitEvents
0x18004ab62  xor     ebp, ebp
0x18004ab64  mov     [rdi+0ACh], ebx
0x18004ab6a  mov     [rdi+3B0h], rbp
0x18004ab71  mov     rax, [r13+rsi*8+200h]
0x18004ab79  mov     [rdi+3A8h], rax
0x18004ab80  mov     rax, [r13+rsi*8+200h]
0x18004ab88  test    rax, rax
0x18004ab8b  jz      short loc_18004AB94
0x18004ab8d  mov     [rax+3B0h], rdi
0x18004ab94  mov     [r13+rsi*8+200h], rdi
0x18004ab9c  mov     rax, [rdi+8]
0x18004aba0  lock inc dword ptr [rax]
0x18004aba3  mov     [r14], ebx
0x18004aba6  lea     rcx, ConnCritSec; lpCriticalSection
0x18004abad  call    cs:__imp_LeaveCriticalSection
0x18004abb4  nop     dword ptr [rax+rax+00h]
0x18004abb9  mov     eax, ebp
0x18004abbb  add     rsp, 38h
0x18004abbf  pop     r14
0x18004abc1  pop     r13
0x18004abc3  pop     rdi
0x18004abc4  pop     rsi
0x18004abc5  pop     rbp
0x18004abc6  pop     rbx
0x18004abc7  retn
```
