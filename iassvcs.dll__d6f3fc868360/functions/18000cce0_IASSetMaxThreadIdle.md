# IASSetMaxThreadIdle

- ea: `0x18000cce0`
- end: `0x18000cd43`
- name: `IASSetMaxThreadIdle`
- size: `99`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000cce0`

## import_xrefs

- `KERNEL32!TryEnterCriticalSection` at `0x18000cd04`
- `KERNEL32!TryEnterCriticalSection` at `0x18000cd04`
- `KERNEL32!SwitchToThread` at `0x18000ccf7`
- `KERNEL32!SwitchToThread` at `0x18000ccf7`
- `KERNEL32!EnterCriticalSection` at `0x18000cd17`
- `KERNEL32!EnterCriticalSection` at `0x18000cd17`
- `KERNEL32!LeaveCriticalSection` at `0x18000cd30`
- `KERNEL32!LeaveCriticalSection` at `0x18000cd30`

## pseudocode

```c
__int64 __fastcall IASSetMaxThreadIdle(int a1)
{
  int v2; // ebx
  unsigned int v3; // ebx

  v2 = 0;
  while ( !TryEnterCriticalSection(&dispatcher) )
  {
    if ( ++v2 >= 100 )
    {
      EnterCriticalSection(&dispatcher);
      break;
    }
    SwitchToThread();
  }
  v3 = dword_180024F24;
  dword_180024F24 = a1;
  LeaveCriticalSection(&dispatcher);
  return v3;
}

```

## disassembly

```asm
0x18000cce0  mov     [rsp+arg_0], rbx
0x18000cce5  push    rdi
0x18000cce6  sub     rsp, 20h
0x18000ccea  mov     edi, ecx
0x18000ccec  xor     ebx, ebx
0x18000ccee  jmp     short loc_18000CCFD
0x18000ccf0  inc     ebx
0x18000ccf2  cmp     ebx, 64h ; 'd'
0x18000ccf5  jge     short loc_18000CD10
0x18000ccf7  call    cs:__imp_SwitchToThread
0x18000ccfd  lea     rcx, ?dispatcher@@3VDispatcher@@A; lpCriticalSection
0x18000cd04  call    cs:__imp_TryEnterCriticalSection
0x18000cd0a  test    eax, eax
0x18000cd0c  jz      short loc_18000CCF0
0x18000cd0e  jmp     short loc_18000CD1D
0x18000cd10  lea     rcx, ?dispatcher@@3VDispatcher@@A; lpCriticalSection
0x18000cd17  call    cs:__imp_EnterCriticalSection
0x18000cd1d  mov     ebx, cs:dword_180024F24
0x18000cd23  lea     rcx, ?dispatcher@@3VDispatcher@@A; lpCriticalSection
0x18000cd2a  mov     cs:dword_180024F24, edi
0x18000cd30  call    cs:__imp_LeaveCriticalSection
0x18000cd36  mov     eax, ebx
0x18000cd38  mov     rbx, [rsp+28h+arg_0]
0x18000cd3d  add     rsp, 20h
0x18000cd41  pop     rdi
0x18000cd42  retn
```
