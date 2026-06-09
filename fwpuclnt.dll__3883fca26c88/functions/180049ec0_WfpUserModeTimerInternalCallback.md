# WfpUserModeTimerInternalCallback

- ea: `0x180049ec0`
- end: `0x180049f32`
- name: `WfpUserModeTimerInternalCallback`
- size: `114`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180049ec0`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049ef6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049ef6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049ed1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049ed1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180049f0a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180049f0a`

## pseudocode

```c
void __fastcall WfpUserModeTimerInternalCallback(
        PTP_CALLBACK_INSTANCE Instance,
        LPCRITICAL_SECTION *Context,
        PTP_TIMER Timer)
{
  char v4; // di

  EnterCriticalSection(Context[4]);
  if ( *((_DWORD *)Context + 6) == 2 )
  {
    v4 = 0;
  }
  else
  {
    v4 = 1;
    *((_DWORD *)Context + 6) = 3;
  }
  LeaveCriticalSection(Context[4]);
  if ( v4 )
  {
    CloseThreadpoolTimer((PTP_TIMER)*Context);
    ((void (__fastcall *)(LPCRITICAL_SECTION *, LPCRITICAL_SECTION))Context[1])(Context, Context[2]);
  }
}

```

## disassembly

```asm
0x180049ec0  mov     [rsp+arg_0], rbx
0x180049ec5  push    rdi
0x180049ec6  sub     rsp, 20h
0x180049eca  mov     rcx, [rdx+20h]; lpCriticalSection
0x180049ece  mov     rbx, rdx
0x180049ed1  call    cs:__imp_EnterCriticalSection
0x180049ed8  nop     dword ptr [rax+rax+00h]
0x180049edd  cmp     dword ptr [rbx+18h], 2
0x180049ee1  jnz     short loc_180049EE8
0x180049ee3  xor     dil, dil
0x180049ee6  jmp     short loc_180049EF2
0x180049ee8  mov     dil, 1
0x180049eeb  mov     dword ptr [rbx+18h], 3
0x180049ef2  mov     rcx, [rbx+20h]; lpCriticalSection
0x180049ef6  call    cs:__imp_LeaveCriticalSection
0x180049efd  nop     dword ptr [rax+rax+00h]
0x180049f02  test    dil, dil
0x180049f05  jz      short loc_180049F26
0x180049f07  mov     rcx, [rbx]; pti
0x180049f0a  call    cs:__imp_CloseThreadpoolTimer
0x180049f11  nop     dword ptr [rax+rax+00h]
0x180049f16  mov     rdx, [rbx+10h]
0x180049f1a  mov     rcx, rbx
0x180049f1d  mov     rax, [rbx+8]
0x180049f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f26  mov     rbx, [rsp+28h+arg_0]
0x180049f2b  add     rsp, 20h
0x180049f2f  pop     rdi
0x180049f30  retn
```
