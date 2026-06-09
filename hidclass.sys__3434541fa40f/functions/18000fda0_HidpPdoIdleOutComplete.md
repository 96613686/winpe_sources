# HidpPdoIdleOutComplete

- ea: `0x18000fda0`
- end: `0x18000fdf0`
- name: `HidpPdoIdleOutComplete`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000fda0`
- `0x180010830`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18000fddd`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18000fddd`

## pseudocode

```c
void __fastcall HidpPdoIdleOutComplete(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a4 + 464), 0xFFFFFFFF) == 1 )
    HIDSM_AddEvent((PVOID)(a4 + 704));
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a4 + 640), (PVOID)0x50444954, 0x20u);
}

```

## disassembly

```asm
0x18000fda0  push    rbx
0x18000fda2  sub     rsp, 20h
0x18000fda6  mov     rbx, r9
0x18000fda9  or      eax, 0FFFFFFFFh
0x18000fdac  lock xadd [r9+1D0h], eax
0x18000fdb5  cmp     eax, 1
0x18000fdb8  jnz     short loc_18000FDCB
0x18000fdba  lea     rcx, [r9+2C0h]; Context
0x18000fdc1  mov     edx, 7E2h
0x18000fdc6  call    HIDSM_AddEvent
0x18000fdcb  lea     rcx, [rbx+280h]; RemoveLock
0x18000fdd2  mov     edx, 50444954h; Tag
0x18000fdd7  mov     r8d, 20h ; ' '; RemlockSize
0x18000fddd  call    cs:__imp_IoReleaseRemoveLockEx
0x18000fde4  nop     dword ptr [rax+rax+00h]
0x18000fde9  add     rsp, 20h
0x18000fded  pop     rbx
0x18000fdee  retn
```
