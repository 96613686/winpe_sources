# NVNWorkerThread(void *)

- ea: `0x18000d090`
- end: `0x18000d0df`
- name: `?NVNWorkerThread@@YAKPEAX@Z`
- size: `79`
- prototype: `__int64 __fastcall(HANDLE *Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000d0b6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000d0b6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d09d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d0ca`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d09d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d0ca`

## pseudocode

```c
__int64 __fastcall NVNWorkerThread(HANDLE *Parameter)
{
  do
    SetEvent(Parameter[7]);
  while ( WaitForSingleObjectEx(Parameter[1], 0xFFFFFFFF, 1) );
  SetEvent(Parameter[7]);
  return 0;
}

```

## disassembly

```asm
0x18000d090  push    rbx
0x18000d092  sub     rsp, 20h
0x18000d096  mov     rbx, rcx
0x18000d099  mov     rcx, [rbx+38h]; hEvent
0x18000d09d  call    cs:__imp_SetEvent
0x18000d0a4  nop     dword ptr [rax+rax+00h]
0x18000d0a9  mov     rcx, [rbx+8]; hHandle
0x18000d0ad  mov     r8d, 1; bAlertable
0x18000d0b3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d0b6  call    cs:__imp_WaitForSingleObjectEx
0x18000d0bd  nop     dword ptr [rax+rax+00h]
0x18000d0c2  test    eax, eax
0x18000d0c4  jnz     short loc_18000D099
0x18000d0c6  mov     rcx, [rbx+38h]; hEvent
0x18000d0ca  call    cs:__imp_SetEvent
0x18000d0d1  nop     dword ptr [rax+rax+00h]
0x18000d0d6  xor     eax, eax
0x18000d0d8  add     rsp, 20h
0x18000d0dc  pop     rbx
0x18000d0dd  retn
```
