# CTriggerMonitorPool::GetAdminTask(void)

- ea: `0x14000b69c`
- end: `0x14000b6e9`
- name: `?GetAdminTask@CTriggerMonitorPool@@AEAAJXZ`
- size: `77`
- prototype: `__int64 __fastcall(CTriggerMonitorPool *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14000c490`
- `0x14000c850`

## callees

- `0x140006458`
- `0x14000b69c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14000b6d0`
- `KERNEL32!LeaveCriticalSection` at `0x14000b6d0`

## pseudocode

```c
__int64 __fastcall CTriggerMonitorPool::GetAdminTask(CTriggerMonitorPool *this)
{
  unsigned int v2; // esi

  CCriticalSection::Lock((CTriggerMonitorPool *)((char *)this + 96));
  v2 = *((_DWORD *)this + 34);
  if ( v2 == 1 )
    *((_DWORD *)this + 34) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  return v2;
}

```

## disassembly

```asm
0x14000b69c  mov     [rsp+arg_0], rbx
0x14000b6a1  mov     [rsp+arg_8], rsi
0x14000b6a6  push    rdi
0x14000b6a7  sub     rsp, 20h
0x14000b6ab  mov     rbx, rcx
0x14000b6ae  add     rcx, 60h ; '`'; this
0x14000b6b2  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x14000b6b7  mov     esi, [rbx+88h]
0x14000b6bd  cmp     esi, 1
0x14000b6c0  jnz     short loc_14000B6CC
0x14000b6c2  mov     dword ptr [rbx+88h], 0
0x14000b6cc  lea     rcx, [rbx+60h]; lpCriticalSection
0x14000b6d0  call    cs:__imp_LeaveCriticalSection
0x14000b6d6  nop
0x14000b6d7  mov     eax, esi
0x14000b6d9  mov     rbx, [rsp+28h+arg_0]
0x14000b6de  mov     rsi, [rsp+28h+arg_8]
0x14000b6e3  add     rsp, 20h
0x14000b6e7  pop     rdi
0x14000b6e8  retn
```
