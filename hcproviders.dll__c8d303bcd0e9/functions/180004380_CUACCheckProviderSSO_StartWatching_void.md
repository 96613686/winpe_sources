# CUACCheckProviderSSO::_StartWatching(void)

- ea: `0x180004380`
- end: `0x1800043ce`
- name: `?_StartWatching@CUACCheckProviderSSO@@AEAAJXZ`
- size: `78`
- prototype: `__int64 __fastcall(CUACCheckProviderSSO *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180003570`
- `0x180004340`

## callees

- `0x180004380`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000438d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000438d`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800043af`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800043af`

## pseudocode

```c
LSTATUS __fastcall CUACCheckProviderSSO::_StartWatching(CUACCheckProviderSSO *this)
{
  LSTATUS result; // eax

  ResetEvent(*((HANDLE *)this + 3));
  result = RegNotifyChangeKeyValue(*((HKEY *)this + 4), 0, 4u, *((HANDLE *)this + 3), 1);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180004380  push    rbx
0x180004382  sub     rsp, 30h
0x180004386  mov     rbx, rcx
0x180004389  mov     rcx, [rcx+18h]; hEvent
0x18000438d  call    cs:__imp_ResetEvent
0x180004394  nop     dword ptr [rax+rax+00h]
0x180004399  mov     r9, [rbx+18h]; hEvent
0x18000439d  xor     edx, edx; bWatchSubtree
0x18000439f  mov     rcx, [rbx+20h]; hKey
0x1800043a3  mov     [rsp+38h+fAsynchronous], 1; fAsynchronous
0x1800043ab  lea     r8d, [rdx+4]; dwNotifyFilter
0x1800043af  call    cs:__imp_RegNotifyChangeKeyValue
0x1800043b6  nop     dword ptr [rax+rax+00h]
0x1800043bb  test    eax, eax
0x1800043bd  jle     short loc_1800043C7
0x1800043bf  movzx   eax, ax
0x1800043c2  or      eax, 80070000h
0x1800043c7  add     rsp, 30h
0x1800043cb  pop     rbx
0x1800043cc  retn
```
