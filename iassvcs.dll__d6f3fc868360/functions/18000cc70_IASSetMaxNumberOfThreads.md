# IASSetMaxNumberOfThreads

- ea: `0x18000cc70`
- end: `0x18000ccd3`
- name: `IASSetMaxNumberOfThreads`
- size: `99`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000cc70`

## import_xrefs

- `KERNEL32!TryEnterCriticalSection` at `0x18000cc94`
- `KERNEL32!TryEnterCriticalSection` at `0x18000cc94`
- `KERNEL32!SwitchToThread` at `0x18000cc87`
- `KERNEL32!SwitchToThread` at `0x18000cc87`
- `KERNEL32!EnterCriticalSection` at `0x18000cca7`
- `KERNEL32!EnterCriticalSection` at `0x18000cca7`
- `KERNEL32!LeaveCriticalSection` at `0x18000ccc0`
- `KERNEL32!LeaveCriticalSection` at `0x18000ccc0`

## pseudocode

```c
__int64 __fastcall IASSetMaxNumberOfThreads(int a1)
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
  v3 = HIDWORD(qword_180024F18);
  HIDWORD(qword_180024F18) = a1;
  LeaveCriticalSection(&dispatcher);
  return v3;
}

```

## disassembly

```asm
0x18000cc70  mov     [rsp+arg_0], rbx
0x18000cc75  push    rdi
0x18000cc76  sub     rsp, 20h
0x18000cc7a  mov     edi, ecx
0x18000cc7c  xor     ebx, ebx
0x18000cc7e  jmp     short loc_18000CC8D
0x18000cc80  inc     ebx
0x18000cc82  cmp     ebx, 64h ; 'd'
0x18000cc85  jge     short loc_18000CCA0
0x18000cc87  call    cs:__imp_SwitchToThread
0x18000cc8d  lea     rcx, ?dispatcher@@3VDispatcher@@A; lpCriticalSection
0x18000cc94  call    cs:__imp_TryEnterCriticalSection
0x18000cc9a  test    eax, eax
0x18000cc9c  jz      short loc_18000CC80
0x18000cc9e  jmp     short loc_18000CCAD
0x18000cca0  lea     rcx, ?dispatcher@@3VDispatcher@@A; lpCriticalSection
0x18000cca7  call    cs:__imp_EnterCriticalSection
0x18000ccad  mov     ebx, dword ptr cs:qword_180024F18+4
0x18000ccb3  lea     rcx, ?dispatcher@@3VDispatcher@@A; lpCriticalSection
0x18000ccba  mov     dword ptr cs:qword_180024F18+4, edi
0x18000ccc0  call    cs:__imp_LeaveCriticalSection
0x18000ccc6  mov     eax, ebx
0x18000ccc8  mov     rbx, [rsp+28h+arg_0]
0x18000cccd  add     rsp, 20h
0x18000ccd1  pop     rdi
0x18000ccd2  retn
```
