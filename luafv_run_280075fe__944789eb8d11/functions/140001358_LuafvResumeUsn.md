# LuafvResumeUsn

- ea: `0x140001358`
- end: `0x14000142d`
- name: `LuafvResumeUsn`
- size: `213`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400164a0`
- `0x140021cb0`
- `0x140022d50`

## callees

- `0x140001358`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000141f`
- `ntoskrnl!KeSetEvent` at `0x14000141f`
- `ntoskrnl!KeClearEvent` at `0x140001407`
- `ntoskrnl!KeClearEvent` at `0x140001407`
- `FLTMGR!FltReleaseContext` at `0x1400013cb`
- `FLTMGR!FltReleaseContext` at `0x1400013cb`
- `FLTMGR!FltGetInstanceContext` at `0x14000137f`
- `FLTMGR!FltGetInstanceContext` at `0x14000137f`
- `FLTMGR!FltReleasePushLockEx` at `0x1400013ba`
- `FLTMGR!FltReleasePushLockEx` at `0x1400013ba`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400013a0`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400013a0`

## pseudocode

```c
NTSTATUS __fastcall LuafvResumeUsn(__int64 a1)
{
  NTSTATUS result; // eax
  char *v3; // rbx
  char *v4; // rdi
  PFLT_CONTEXT Context; // [rsp+30h] [rbp+8h] BYREF

  Context = 0;
  result = FltGetInstanceContext(*(PFLT_INSTANCE *)(*(_QWORD *)(a1 + 16) + 16LL), &Context);
  if ( result >= 0 )
  {
    v3 = (char *)Context;
    v4 = (char *)Context + 264;
    FltAcquirePushLockExclusiveEx((char *)Context + 264, 0);
    if ( *((_DWORD *)v3 + 208) == 3 && *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL) == *((_QWORD *)v3 + 10) )
    {
      *((_QWORD *)v3 + 10) = 0;
      KeClearEvent((PRKEVENT)(v3 + 184));
      KeSetEvent((PRKEVENT)(v3 + 184), 0, 0);
    }
    FltReleasePushLockEx(v4, 0);
    FltReleaseContext(Context);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140001358  mov     rax, rsp
0x14000135b  mov     [rax+10h], rbx
0x14000135f  mov     [rax+18h], rsi
0x140001363  push    rdi
0x140001364  sub     rsp, 20h
0x140001368  mov     rsi, rcx
0x14000136b  mov     qword ptr [rax+8], 0
0x140001373  mov     rcx, [rcx+10h]
0x140001377  lea     rdx, [rax+8]; Context
0x14000137b  mov     rcx, [rcx+10h]; Instance
0x14000137f  call    cs:__imp_FltGetInstanceContext
0x140001386  nop     dword ptr [rax+rax+00h]
0x14000138b  test    eax, eax
0x14000138d  js      short loc_1400013D9
0x14000138f  mov     rbx, [rsp+28h+Context]
0x140001394  xor     edx, edx
0x140001396  lea     rdi, [rbx+108h]
0x14000139d  mov     rcx, rdi
0x1400013a0  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400013a7  nop     dword ptr [rax+rax+00h]
0x1400013ac  cmp     dword ptr [rbx+340h], 3
0x1400013b3  jz      short loc_1400013EA
0x1400013b5  xor     edx, edx
0x1400013b7  mov     rcx, rdi
0x1400013ba  call    cs:__imp_FltReleasePushLockEx
0x1400013c1  nop     dword ptr [rax+rax+00h]
0x1400013c6  mov     rcx, [rsp+28h+Context]; Context
0x1400013cb  call    cs:__imp_FltReleaseContext
0x1400013d2  nop     dword ptr [rax+rax+00h]
0x1400013d7  xor     eax, eax
0x1400013d9  mov     rbx, [rsp+28h+arg_8]
0x1400013de  mov     rsi, [rsp+28h+arg_10]
0x1400013e3  add     rsp, 20h
0x1400013e7  pop     rdi
0x1400013e8  retn
0x1400013ea  mov     rdx, [rsi+10h]
0x1400013ee  mov     rax, [rbx+50h]
0x1400013f2  cmp     [rdx+8], rax
0x1400013f6  jnz     short loc_1400013B5
0x1400013f8  lea     rcx, [rbx+0B8h]; Event
0x1400013ff  mov     qword ptr [rbx+50h], 0
0x140001407  call    cs:__imp_KeClearEvent
0x14000140e  nop     dword ptr [rax+rax+00h]
0x140001413  xor     r8d, r8d; Wait
0x140001416  lea     rcx, [rbx+0B8h]; Event
0x14000141d  xor     edx, edx; Increment
0x14000141f  call    cs:__imp_KeSetEvent
0x140001426  nop     dword ptr [rax+rax+00h]
0x14000142b  jmp     short loc_1400013B5
```
