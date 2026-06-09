# KpsCancelTimeoutTimer(_KPS_IO *)

- ea: `0x18001e494`
- end: `0x18001e51a`
- name: `?KpsCancelTimeoutTimer@@YAXPEAU_KPS_IO@@@Z`
- size: `134`
- prototype: `void __fastcall(struct _KPS_IO *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180020750`
- `0x1800225d0`

## callees

- `0x18001e494`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18001e4ec`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18001e4ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWaitEx` at `0x18001e4b0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWaitEx` at `0x18001e4b0`
- `ntdll!RtlLeaveCriticalSection` at `0x18001e4d4`
- `ntdll!RtlLeaveCriticalSection` at `0x18001e4d4`
- `ntdll!RtlEnterCriticalSection` at `0x18001e4fb`
- `ntdll!RtlEnterCriticalSection` at `0x18001e4fb`

## pseudocode

```c
void __fastcall KpsCancelTimeoutTimer(struct _KPS_IO *a1)
{
  if ( !SetThreadpoolWaitEx(*((PTP_WAIT *)a1 + 41), 0, 0, 0) )
  {
    *((_DWORD *)a1 + 84) = 3;
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 288));
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)a1 + 41), 1);
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 288));
  }
  *((_DWORD *)a1 + 84) = 0;
}

```

## disassembly

```asm
0x18001e494  mov     [rsp+arg_0], rbx
0x18001e499  push    rdi
0x18001e49a  sub     rsp, 20h
0x18001e49e  mov     rdi, rcx
0x18001e4a1  xor     r9d, r9d; Reserved
0x18001e4a4  mov     rcx, [rcx+148h]; pwa
0x18001e4ab  xor     r8d, r8d; pftTimeout
0x18001e4ae  xor     edx, edx; h
0x18001e4b0  call    cs:__imp_SetThreadpoolWaitEx
0x18001e4b7  nop     dword ptr [rax+rax+00h]
0x18001e4bc  test    eax, eax
0x18001e4be  jnz     short loc_18001E507
0x18001e4c0  lea     rbx, [rdi+120h]
0x18001e4c7  mov     dword ptr [rdi+150h], 3
0x18001e4d1  mov     rcx, rbx; CriticalSection
0x18001e4d4  call    cs:__imp_RtlLeaveCriticalSection
0x18001e4db  nop     dword ptr [rax+rax+00h]
0x18001e4e0  mov     rcx, [rdi+148h]; pwa
0x18001e4e7  mov     edx, 1; fCancelPendingCallbacks
0x18001e4ec  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18001e4f3  nop     dword ptr [rax+rax+00h]
0x18001e4f8  mov     rcx, rbx; CriticalSection
0x18001e4fb  call    cs:__imp_RtlEnterCriticalSection
0x18001e502  nop     dword ptr [rax+rax+00h]
0x18001e507  and     dword ptr [rdi+150h], 0
0x18001e50e  mov     rbx, [rsp+28h+arg_0]
0x18001e513  add     rsp, 20h
0x18001e517  pop     rdi
0x18001e518  retn
```
