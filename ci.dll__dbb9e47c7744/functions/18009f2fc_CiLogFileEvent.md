# CiLogFileEvent

- ea: `0x18009f2fc`
- end: `0x18009f3c1`
- name: `CiLogFileEvent`
- size: `197`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18005d550`
- `0x18009e068`
- `0x18009e7a8`
- `0x18009f240`
- `0x1800a4098`
- `0x1800dca2c`
- `0x1800e4ca8`

## callees

- `0x18002bf20`
- `0x18009f2fc`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18009f329`
- `ntoskrnl!EtwEventEnabled` at `0x18009f329`
- `ntoskrnl!IoGetActivityIdThread` at `0x18009f373`
- `ntoskrnl!IoGetActivityIdThread` at `0x18009f373`
- `ntoskrnl!EtwWrite` at `0x18009f39c`
- `ntoskrnl!EtwWrite` at `0x18009f39c`

## pseudocode

```c
NTSTATUS __fastcall CiLogFileEvent(unsigned __int16 *a1, const EVENT_DESCRIPTOR *a2)
{
  __int64 v5; // rcx
  unsigned __int16 v6; // ax
  const GUID *ActivityIdThread; // rax
  __int16 v8; // [rsp+30h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-30h] BYREF
  __int64 v10; // [rsp+48h] [rbp-20h]
  int v11; // [rsp+50h] [rbp-18h]
  int v12; // [rsp+54h] [rbp-14h]

  v8 = 0;
  if ( !EtwEventEnabled(g_EtwEventHandle, a2) )
    return 0;
  v5 = *a1;
  v6 = *a1;
  *(_QWORD *)&UserData.Size = 2;
  v8 = v6 >> 1;
  UserData.Ptr = (ULONGLONG)&v8;
  v10 = *((_QWORD *)a1 + 1);
  v11 = v5;
  v12 = 0;
  ActivityIdThread = (const GUID *)IoGetActivityIdThread(v5);
  return EtwWrite(g_EtwEventHandle, a2, ActivityIdThread, 2u, &UserData);
}

```

## disassembly

```asm
0x18009f2fc  mov     [rsp+arg_0], rbx
0x18009f301  push    rdi
0x18009f302  sub     rsp, 60h
0x18009f306  mov     rax, cs:__security_cookie
0x18009f30d  xor     rax, rsp
0x18009f310  mov     [rsp+68h+var_10], rax
0x18009f315  mov     rdi, rcx
0x18009f318  xor     eax, eax
0x18009f31a  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18009f321  mov     rbx, rdx
0x18009f324  mov     [rsp+68h+var_38], ax
0x18009f329  call    cs:__imp_EtwEventEnabled
0x18009f330  nop     dword ptr [rax+rax+00h]
0x18009f335  test    al, al
0x18009f337  jnz     short loc_18009F33D
0x18009f339  xor     eax, eax
0x18009f33b  jmp     short loc_18009F3A8
0x18009f33d  movzx   ecx, word ptr [rdi]
0x18009f340  movzx   eax, cx
0x18009f343  mov     qword ptr [rsp+68h+var_30.Size], 2
0x18009f34c  shr     ax, 1
0x18009f34f  mov     [rsp+68h+var_38], ax
0x18009f354  lea     rax, [rsp+68h+var_38]
0x18009f359  mov     [rsp+68h+var_30.Ptr], rax
0x18009f35e  mov     rax, [rdi+8]
0x18009f362  mov     [rsp+68h+var_20], rax
0x18009f367  mov     [rsp+68h+var_18], ecx
0x18009f36b  mov     [rsp+68h+var_14], 0
0x18009f373  call    cs:__imp_IoGetActivityIdThread
0x18009f37a  nop     dword ptr [rax+rax+00h]
0x18009f37f  lea     rcx, [rsp+68h+var_30]
0x18009f384  mov     r9d, 2; UserDataCount
0x18009f38a  mov     [rsp+68h+UserData], rcx; UserData
0x18009f38f  mov     r8, rax; ActivityId
0x18009f392  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18009f399  mov     rdx, rbx; EventDescriptor
0x18009f39c  call    cs:__imp_EtwWrite
0x18009f3a3  nop     dword ptr [rax+rax+00h]
0x18009f3a8  mov     rcx, [rsp+68h+var_10]
0x18009f3ad  xor     rcx, rsp; StackCookie
0x18009f3b0  call    __security_check_cookie
0x18009f3b5  mov     rbx, [rsp+68h+arg_0]
0x18009f3ba  add     rsp, 60h
0x18009f3be  pop     rdi
0x18009f3bf  retn
```
