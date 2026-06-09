# _DllInstanceInit

- ea: `0x180002590`
- end: `0x1800025f3`
- name: `_DllInstanceInit`
- size: `99`
- prototype: `__int64 __fastcall(HMODULE hLibModule)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002280`

## callees

- `0x180002590`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800025c2`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800025c2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800025a5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800025b2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800025a5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800025b2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800025d5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800025e2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800025d5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800025e2`

## pseudocode

```c
__int64 __fastcall DllInstanceInit(HMODULE hLibModule, int a2)
{
  if ( a2 == 1 )
  {
    InitializeCriticalSection(&CritSec);
    InitializeCriticalSection(&SeqCritSec);
    hInstance = hLibModule;
    DisableThreadLibraryCalls(hLibModule);
  }
  else if ( !a2 )
  {
    DeleteCriticalSection(&CritSec);
    DeleteCriticalSection(&SeqCritSec);
  }
  return 1;
}

```

## disassembly

```asm
0x180002590  push    rbx
0x180002592  sub     rsp, 20h
0x180002596  mov     rbx, rcx
0x180002599  cmp     edx, 1
0x18000259c  jnz     short loc_1800025CA
0x18000259e  lea     rcx, CritSec; lpCriticalSection
0x1800025a5  call    cs:__imp_InitializeCriticalSection
0x1800025ab  lea     rcx, SeqCritSec; lpCriticalSection
0x1800025b2  call    cs:__imp_InitializeCriticalSection
0x1800025b8  mov     rcx, rbx; hLibModule
0x1800025bb  mov     cs:hInstance, rbx
0x1800025c2  call    cs:__imp_DisableThreadLibraryCalls
0x1800025c8  jmp     short loc_1800025E8
0x1800025ca  test    edx, edx
0x1800025cc  jnz     short loc_1800025E8
0x1800025ce  lea     rcx, CritSec; lpCriticalSection
0x1800025d5  call    cs:__imp_DeleteCriticalSection
0x1800025db  lea     rcx, SeqCritSec; lpCriticalSection
0x1800025e2  call    cs:__imp_DeleteCriticalSection
0x1800025e8  mov     eax, 1
0x1800025ed  add     rsp, 20h
0x1800025f1  pop     rbx
0x1800025f2  retn
```
