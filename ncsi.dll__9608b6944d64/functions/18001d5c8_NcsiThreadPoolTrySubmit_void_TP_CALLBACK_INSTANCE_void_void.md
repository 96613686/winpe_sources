# NcsiThreadPoolTrySubmit(void (*)(_TP_CALLBACK_INSTANCE *,void *),void *)

- ea: `0x18001d5c8`
- end: `0x18001d62c`
- name: `?NcsiThreadPoolTrySubmit@@YAHP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z1@Z`
- size: `100`
- prototype: `__int64 __fastcall(PTP_SIMPLE_CALLBACK pfns, PVOID pv)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x18001645c`
- `0x18001ba34`
- `0x18001d110`
- `0x18001d444`
- `0x180021d28`
- `0x180037ac4`
- `0x18003a500`
- `0x18003d050`
- `0x18004d3c0`
- `0x18005e2e4`
- `0x1800646d8`
- `0x180065c3c`
- `0x180068854`
- `0x18006d04c`

## callees

- `0x18001d5c8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001d5fb`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001d5fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d60a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d60a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d5df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d5df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d624`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d624`

## pseudocode

```c
__int64 __fastcall NcsiThreadPoolTrySubmit(PTP_SIMPLE_CALLBACK pfns, PVOID pv)
{
  unsigned int v4; // ebx

  EnterCriticalSection(&stru_18009D4B8);
  if ( byte_18009DAA0 )
  {
    v4 = TrySubmitThreadpoolCallback(pfns, pv, pcbe);
  }
  else
  {
    v4 = 0;
    SetLastError(0x45Bu);
  }
  LeaveCriticalSection(&stru_18009D4B8);
  return v4;
}

```

## disassembly

```asm
0x18001d5c8  mov     [rsp+arg_10], rbx
0x18001d5cd  push    rdi
0x18001d5ce  sub     rsp, 20h
0x18001d5d2  mov     rbx, rcx
0x18001d5d5  mov     rdi, rdx
0x18001d5d8  lea     rcx, stru_18009D4B8; lpCriticalSection
0x18001d5df  call    cs:__imp_EnterCriticalSection
0x18001d5e5  cmp     cs:byte_18009DAA0, 0
0x18001d5ec  jz      short loc_18001D61D
0x18001d5ee  mov     r8, cs:pcbe; pcbe
0x18001d5f5  mov     rdx, rdi; pv
0x18001d5f8  mov     rcx, rbx; pfns
0x18001d5fb  call    cs:__imp_TrySubmitThreadpoolCallback
0x18001d601  mov     ebx, eax
0x18001d603  lea     rcx, stru_18009D4B8; lpCriticalSection
0x18001d60a  call    cs:__imp_LeaveCriticalSection
0x18001d610  mov     eax, ebx
0x18001d612  mov     rbx, [rsp+28h+arg_10]
0x18001d617  add     rsp, 20h
0x18001d61b  pop     rdi
0x18001d61c  retn
0x18001d61d  xor     ebx, ebx
0x18001d61f  mov     ecx, 45Bh; dwErrCode
0x18001d624  call    cs:__imp_SetLastError
0x18001d62a  jmp     short loc_18001D603
```
