# CCancelRpc::ShutDownCancelThread(void)

- ea: `0x180016140`
- end: `0x180016184`
- name: `?ShutDownCancelThread@CCancelRpc@@QEAAXXZ`
- size: `68`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004850`

## callees

- `0x18000b95c`
- `0x180016140`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18001616d`
- `KERNEL32!SetEvent` at `0x18001616d`
- `KERNEL32!LeaveCriticalSection` at `0x180016160`
- `KERNEL32!LeaveCriticalSection` at `0x180016177`
- `KERNEL32!LeaveCriticalSection` at `0x180016160`
- `KERNEL32!LeaveCriticalSection` at `0x180016177`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CCancelRpc::ShutDownCancelThread(CCriticalSection *lpCriticalSection)
{
  CCriticalSection::Lock(lpCriticalSection);
  if ( (int)--*((_DWORD *)lpCriticalSection + 31) <= 0 )
    SetEvent(*((HANDLE *)lpCriticalSection + 12));
  LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
}

```

## disassembly

```asm
0x180016140  push    rbx
0x180016142  sub     rsp, 20h
0x180016146  mov     rbx, rcx
0x180016149  mov     [rsp+28h+arg_0], rcx
0x18001614e  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180016153  nop
0x180016154  dec     dword ptr [rbx+7Ch]
0x180016157  cmp     dword ptr [rbx+7Ch], 0
0x18001615b  jle     short loc_180016169
0x18001615d  mov     rcx, rbx; lpCriticalSection
0x180016160  call    cs:__imp_LeaveCriticalSection
0x180016166  nop
0x180016167  jmp     short loc_18001617E
0x180016169  mov     rcx, [rbx+60h]; hEvent
0x18001616d  call    cs:__imp_SetEvent
0x180016173  nop
0x180016174  mov     rcx, rbx; lpCriticalSection
0x180016177  call    cs:__imp_LeaveCriticalSection
0x18001617d  nop
0x18001617e  add     rsp, 20h
0x180016182  pop     rbx
0x180016183  retn
```
