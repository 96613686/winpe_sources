# CStartupAppCheck::_StartWatching(void)

- ea: `0x180008550`
- end: `0x1800085a7`
- name: `?_StartWatching@CStartupAppCheck@@AEAAJXZ`
- size: `87`
- prototype: `__int64 __fastcall(CStartupAppCheck *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180004b10`
- `0x180008820`

## callees

- `0x180008550`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180008560`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180008560`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180008588`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180008588`

## pseudocode

```c
LSTATUS __fastcall CStartupAppCheck::_StartWatching(CStartupAppCheck *this)
{
  LSTATUS result; // eax

  ResetEvent(*((HANDLE *)this + 29));
  result = RegNotifyChangeKeyValue(*((HKEY *)this + 28), 0, 4u, *((HANDLE *)this + 29), 1);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180008550  push    rbx
0x180008552  sub     rsp, 30h
0x180008556  mov     rbx, rcx
0x180008559  mov     rcx, [rcx+0E8h]; hEvent
0x180008560  call    cs:__imp_ResetEvent
0x180008567  nop     dword ptr [rax+rax+00h]
0x18000856c  mov     r9, [rbx+0E8h]; hEvent
0x180008573  xor     edx, edx; bWatchSubtree
0x180008575  mov     rcx, [rbx+0E0h]; hKey
0x18000857c  mov     [rsp+38h+fAsynchronous], 1; fAsynchronous
0x180008584  lea     r8d, [rdx+4]; dwNotifyFilter
0x180008588  call    cs:__imp_RegNotifyChangeKeyValue
0x18000858f  nop     dword ptr [rax+rax+00h]
0x180008594  test    eax, eax
0x180008596  jle     short loc_1800085A0
0x180008598  movzx   eax, ax
0x18000859b  or      eax, 80070000h
0x1800085a0  add     rsp, 30h
0x1800085a4  pop     rbx
0x1800085a5  retn
```
