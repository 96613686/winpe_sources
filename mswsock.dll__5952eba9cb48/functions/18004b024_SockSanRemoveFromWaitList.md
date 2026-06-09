# SockSanRemoveFromWaitList

- ea: `0x18004b024`
- end: `0x18004b095`
- name: `SockSanRemoveFromWaitList`
- size: `113`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180044800`
- `0x180044f0c`
- `0x180046790`
- `0x18004bf20`
- `0x18004e7fc`

## callees

- `0x18004b024`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004b06c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004b06c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b089`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b03b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b03b`

## pseudocode

```c
void __fastcall SockSanRemoveFromWaitList(__int64 a1, int a2)
{
  __int64 v3; // rdi

  v3 = a2;
  EnterCriticalSection(&ConnCritSec);
  if ( *(int *)(a1 + 172) <= 64 )
  {
    *(_BYTE *)(a1 + 802) |= 2u;
    *(_DWORD *)(a1 + 172) = 65;
    SetEvent(ConnectData[v3]);
  }
  LeaveCriticalSection(&ConnCritSec);
}

```

## disassembly

```asm
0x18004b024  mov     [rsp+arg_0], rbx
0x18004b029  push    rdi
0x18004b02a  sub     rsp, 20h
0x18004b02e  mov     rbx, rcx
0x18004b031  movsxd  rdi, edx
0x18004b034  lea     rcx, ConnCritSec; lpCriticalSection
0x18004b03b  call    cs:__imp_EnterCriticalSection
0x18004b042  nop     dword ptr [rax+rax+00h]
0x18004b047  cmp     dword ptr [rbx+0ACh], 40h ; '@'
0x18004b04e  jg      short loc_18004B078
0x18004b050  or      byte ptr [rbx+322h], 2
0x18004b057  lea     rax, ConnectData
0x18004b05e  mov     dword ptr [rbx+0ACh], 41h ; 'A'
0x18004b068  mov     rcx, [rax+rdi*8]; hEvent
0x18004b06c  call    cs:__imp_SetEvent
0x18004b073  nop     dword ptr [rax+rax+00h]
0x18004b078  lea     rcx, ConnCritSec
0x18004b07f  mov     rbx, [rsp+28h+arg_0]
0x18004b084  add     rsp, 20h
0x18004b088  pop     rdi
0x18004b089  jmp     cs:__imp_LeaveCriticalSection
```
