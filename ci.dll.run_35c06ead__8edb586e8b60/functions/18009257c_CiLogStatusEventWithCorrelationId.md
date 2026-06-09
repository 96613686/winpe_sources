# CiLogStatusEventWithCorrelationId

- ea: `0x18009257c`
- end: `0x180092623`
- name: `CiLogStatusEventWithCorrelationId`
- size: `167`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180058048`
- `0x18005e670`
- `0x180061ae8`
- `0x180091f30`
- `0x180092a80`
- `0x1800e5f00`
- `0x1800e5fd0`

## callees

- `0x18002c0d0`
- `0x18009257c`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x1800925a6`
- `ntoskrnl!EtwEventEnabled` at `0x1800925a6`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800925ce`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800925ce`
- `ntoskrnl!EtwWrite` at `0x1800925fa`
- `ntoskrnl!EtwWrite` at `0x1800925fa`

## pseudocode

```c
NTSTATUS __fastcall CiLogStatusEventWithCorrelationId(int a1, const EVENT_DESCRIPTOR *a2, const GUID *ActivityIdThread)
{
  __int64 v5; // rcx
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+60h] [rbp+8h] BYREF

  v8 = a1;
  if ( !EtwEventEnabled(g_EtwEventHandle, a2) )
    return 0;
  *(_QWORD *)&UserData.Size = 4;
  UserData.Ptr = (ULONGLONG)&v8;
  if ( !ActivityIdThread )
    ActivityIdThread = (const GUID *)IoGetActivityIdThread(v5);
  return EtwWrite(g_EtwEventHandle, a2, ActivityIdThread, 1u, &UserData);
}

```

## disassembly

```asm
0x18009257c  mov     [rsp+arg_18], rbx
0x180092581  mov     [rsp+arg_0], ecx
0x180092585  push    rdi
0x180092586  sub     rsp, 50h
0x18009258a  mov     rax, cs:__security_cookie
0x180092591  xor     rax, rsp
0x180092594  mov     [rsp+58h+var_18], rax
0x180092599  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800925a0  mov     rbx, r8
0x1800925a3  mov     rdi, rdx
0x1800925a6  call    cs:__imp_EtwEventEnabled
0x1800925ad  nop     dword ptr [rax+rax+00h]
0x1800925b2  test    al, al
0x1800925b4  jz      short loc_18009261F
0x1800925b6  mov     qword ptr [rsp+58h+var_28.Size], 4
0x1800925bf  lea     rax, [rsp+58h+arg_0]
0x1800925c4  mov     [rsp+58h+var_28.Ptr], rax
0x1800925c9  test    rbx, rbx
0x1800925cc  jnz     short loc_1800925DD
0x1800925ce  call    cs:__imp_IoGetActivityIdThread
0x1800925d5  nop     dword ptr [rax+rax+00h]
0x1800925da  mov     rbx, rax
0x1800925dd  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800925e4  lea     rax, [rsp+58h+var_28]
0x1800925e9  mov     r9d, 1; UserDataCount
0x1800925ef  mov     [rsp+58h+UserData], rax; UserData
0x1800925f4  mov     r8, rbx; ActivityId
0x1800925f7  mov     rdx, rdi; EventDescriptor
0x1800925fa  call    cs:__imp_EtwWrite
0x180092601  nop     dword ptr [rax+rax+00h]
0x180092606  mov     rcx, [rsp+58h+var_18]
0x18009260b  xor     rcx, rsp; StackCookie
0x18009260e  call    __security_check_cookie
0x180092613  mov     rbx, [rsp+58h+arg_18]
0x180092618  add     rsp, 50h
0x18009261c  pop     rdi
0x18009261d  retn
0x18009261f  xor     eax, eax
0x180092621  jmp     short loc_180092606
```
