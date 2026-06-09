# HidpPdoPowerUpPoCompletion

- ea: `0x1800101a0`
- end: `0x1800101fa`
- name: `HidpPdoPowerUpPoCompletion`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800101a0`
- `0x180010830`
- `0x180011738`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1800101e7`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1800101e7`

## pseudocode

```c
void __fastcall HidpPdoPowerUpPoCompletion(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a4 + 464), 0xFFFFFFFF) == 1 )
  {
    HidpFdoUpdatePdosInStableState(a4, 1);
    HIDSM_AddEvent((PVOID)(a4 + 704));
  }
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a4 + 640), (PVOID)0x50444954, 0x20u);
}

```

## disassembly

```asm
0x1800101a0  push    rbx
0x1800101a2  sub     rsp, 20h
0x1800101a6  mov     rbx, r9
0x1800101a9  or      eax, 0FFFFFFFFh
0x1800101ac  lock xadd [r9+1D0h], eax
0x1800101b5  cmp     eax, 1
0x1800101b8  jnz     short loc_1800101D5
0x1800101ba  mov     dl, al
0x1800101bc  mov     rcx, rbx
0x1800101bf  call    HidpFdoUpdatePdosInStableState
0x1800101c4  lea     rcx, [rbx+2C0h]; Context
0x1800101cb  mov     edx, 7F6h
0x1800101d0  call    HIDSM_AddEvent
0x1800101d5  lea     rcx, [rbx+280h]; RemoveLock
0x1800101dc  mov     edx, 50444954h; Tag
0x1800101e1  mov     r8d, 20h ; ' '; RemlockSize
0x1800101e7  call    cs:__imp_IoReleaseRemoveLockEx
0x1800101ee  nop     dword ptr [rax+rax+00h]
0x1800101f3  add     rsp, 20h
0x1800101f7  pop     rbx
0x1800101f8  retn
```
