# _DllInstanceInit

- ea: `0x180005630`
- end: `0x180005676`
- name: `_DllInstanceInit`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800053f0`

## callees

- `0x180005630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000563e`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000563e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005665`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005665`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000564b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000564b`

## pseudocode

```c
__int64 __fastcall DllInstanceInit(HMODULE a1, int a2)
{
  if ( a2 == 1 )
  {
    DisableThreadLibraryCalls(a1);
    InitializeCriticalSection(&CritSec);
    hModuleInstance = a1;
  }
  else if ( !a2 )
  {
    DeleteCriticalSection(&CritSec);
  }
  return 1;
}

```

## disassembly

```asm
0x180005630  push    rbx
0x180005632  sub     rsp, 20h
0x180005636  mov     rbx, rcx
0x180005639  cmp     edx, 1
0x18000563c  jnz     short loc_18000565A
0x18000563e  call    cs:__imp_DisableThreadLibraryCalls
0x180005644  lea     rcx, CritSec; lpCriticalSection
0x18000564b  call    cs:__imp_InitializeCriticalSection
0x180005651  mov     cs:hModuleInstance, rbx
0x180005658  jmp     short loc_18000566B
0x18000565a  test    edx, edx
0x18000565c  jnz     short loc_18000566B
0x18000565e  lea     rcx, CritSec; lpCriticalSection
0x180005665  call    cs:__imp_DeleteCriticalSection
0x18000566b  mov     eax, 1
0x180005670  add     rsp, 20h
0x180005674  pop     rbx
0x180005675  retn
```
