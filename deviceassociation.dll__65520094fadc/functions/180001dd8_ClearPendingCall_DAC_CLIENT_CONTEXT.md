# ClearPendingCall(_DAC_CLIENT_CONTEXT *)

- ea: `0x180001dd8`
- end: `0x180001e13`
- name: `?ClearPendingCall@@YAXPEAU_DAC_CLIENT_CONTEXT@@@Z`
- size: `59`
- prototype: `void __fastcall(struct _DAC_CLIENT_CONTEXT *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d38`
- `0x180008b40`
- `0x180008fc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001e0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001de9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001de9`

## pseudocode

```c
void __fastcall ClearPendingCall(struct _DAC_CLIENT_CONTEXT *a1)
{
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 16));
  *((_DWORD *)a1 + 16) = 0;
  *((_QWORD *)a1 + 9) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 16));
}

```

## disassembly

```asm
0x180001dd8  mov     [rsp+arg_0], rbx
0x180001ddd  push    rdi
0x180001dde  sub     rsp, 20h
0x180001de2  mov     rdi, rcx
0x180001de5  add     rcx, 10h; lpCriticalSection
0x180001de9  call    cs:__imp_EnterCriticalSection
0x180001def  lea     rcx, [rdi+10h]
0x180001df3  mov     dword ptr [rdi+40h], 0
0x180001dfa  mov     qword ptr [rdi+48h], 0
0x180001e02  mov     rbx, [rsp+28h+arg_0]
0x180001e07  add     rsp, 20h
0x180001e0b  pop     rdi
0x180001e0c  jmp     cs:__imp_LeaveCriticalSection
```
