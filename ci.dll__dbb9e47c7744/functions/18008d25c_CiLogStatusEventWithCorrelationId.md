# CiLogStatusEventWithCorrelationId

- ea: `0x18008d25c`
- end: `0x18008d303`
- name: `CiLogStatusEventWithCorrelationId`
- size: `167`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180058120`
- `0x18005e6d0`
- `0x180061984`
- `0x18008c5d0`
- `0x18008cc10`
- `0x1800e5980`
- `0x1800e5a50`

## callees

- `0x18002bf20`
- `0x18008d25c`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18008d286`
- `ntoskrnl!EtwEventEnabled` at `0x18008d286`
- `ntoskrnl!IoGetActivityIdThread` at `0x18008d2ae`
- `ntoskrnl!IoGetActivityIdThread` at `0x18008d2ae`
- `ntoskrnl!EtwWrite` at `0x18008d2da`
- `ntoskrnl!EtwWrite` at `0x18008d2da`

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
0x18008d25c  mov     [rsp+arg_18], rbx
0x18008d261  mov     [rsp+arg_0], ecx
0x18008d265  push    rdi
0x18008d266  sub     rsp, 50h
0x18008d26a  mov     rax, cs:__security_cookie
0x18008d271  xor     rax, rsp
0x18008d274  mov     [rsp+58h+var_18], rax
0x18008d279  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18008d280  mov     rbx, r8
0x18008d283  mov     rdi, rdx
0x18008d286  call    cs:__imp_EtwEventEnabled
0x18008d28d  nop     dword ptr [rax+rax+00h]
0x18008d292  test    al, al
0x18008d294  jz      short loc_18008D2FF
0x18008d296  mov     qword ptr [rsp+58h+var_28.Size], 4
0x18008d29f  lea     rax, [rsp+58h+arg_0]
0x18008d2a4  mov     [rsp+58h+var_28.Ptr], rax
0x18008d2a9  test    rbx, rbx
0x18008d2ac  jnz     short loc_18008D2BD
0x18008d2ae  call    cs:__imp_IoGetActivityIdThread
0x18008d2b5  nop     dword ptr [rax+rax+00h]
0x18008d2ba  mov     rbx, rax
0x18008d2bd  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18008d2c4  lea     rax, [rsp+58h+var_28]
0x18008d2c9  mov     r9d, 1; UserDataCount
0x18008d2cf  mov     [rsp+58h+UserData], rax; UserData
0x18008d2d4  mov     r8, rbx; ActivityId
0x18008d2d7  mov     rdx, rdi; EventDescriptor
0x18008d2da  call    cs:__imp_EtwWrite
0x18008d2e1  nop     dword ptr [rax+rax+00h]
0x18008d2e6  mov     rcx, [rsp+58h+var_18]
0x18008d2eb  xor     rcx, rsp; StackCookie
0x18008d2ee  call    __security_check_cookie
0x18008d2f3  mov     rbx, [rsp+58h+arg_18]
0x18008d2f8  add     rsp, 50h
0x18008d2fc  pop     rdi
0x18008d2fd  retn
0x18008d2ff  xor     eax, eax
0x18008d301  jmp     short loc_18008D2E6
```
