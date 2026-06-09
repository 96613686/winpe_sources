# CiLogStatusEventWithCorrelationId

- ea: `0x18008bc2c`
- end: `0x18008bcd3`
- name: `CiLogStatusEventWithCorrelationId`
- size: `167`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180057408`
- `0x18005dfd0`
- `0x180061140`
- `0x18008afa0`
- `0x18008b5e0`
- `0x1800e5510`
- `0x1800e55e0`

## callees

- `0x18002bef0`
- `0x18008bc2c`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18008bc56`
- `ntoskrnl!EtwEventEnabled` at `0x18008bc56`
- `ntoskrnl!IoGetActivityIdThread` at `0x18008bc7e`
- `ntoskrnl!IoGetActivityIdThread` at `0x18008bc7e`
- `ntoskrnl!EtwWrite` at `0x18008bcaa`
- `ntoskrnl!EtwWrite` at `0x18008bcaa`

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
0x18008bc2c  mov     [rsp+arg_18], rbx
0x18008bc31  mov     [rsp+arg_0], ecx
0x18008bc35  push    rdi
0x18008bc36  sub     rsp, 50h
0x18008bc3a  mov     rax, cs:__security_cookie
0x18008bc41  xor     rax, rsp
0x18008bc44  mov     [rsp+58h+var_18], rax
0x18008bc49  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18008bc50  mov     rbx, r8
0x18008bc53  mov     rdi, rdx
0x18008bc56  call    cs:__imp_EtwEventEnabled
0x18008bc5d  nop     dword ptr [rax+rax+00h]
0x18008bc62  test    al, al
0x18008bc64  jz      short loc_18008BCCF
0x18008bc66  mov     qword ptr [rsp+58h+var_28.Size], 4
0x18008bc6f  lea     rax, [rsp+58h+arg_0]
0x18008bc74  mov     [rsp+58h+var_28.Ptr], rax
0x18008bc79  test    rbx, rbx
0x18008bc7c  jnz     short loc_18008BC8D
0x18008bc7e  call    cs:__imp_IoGetActivityIdThread
0x18008bc85  nop     dword ptr [rax+rax+00h]
0x18008bc8a  mov     rbx, rax
0x18008bc8d  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18008bc94  lea     rax, [rsp+58h+var_28]
0x18008bc99  mov     r9d, 1; UserDataCount
0x18008bc9f  mov     [rsp+58h+UserData], rax; UserData
0x18008bca4  mov     r8, rbx; ActivityId
0x18008bca7  mov     rdx, rdi; EventDescriptor
0x18008bcaa  call    cs:__imp_EtwWrite
0x18008bcb1  nop     dword ptr [rax+rax+00h]
0x18008bcb6  mov     rcx, [rsp+58h+var_18]
0x18008bcbb  xor     rcx, rsp; StackCookie
0x18008bcbe  call    __security_check_cookie
0x18008bcc3  mov     rbx, [rsp+58h+arg_18]
0x18008bcc8  add     rsp, 50h
0x18008bccc  pop     rdi
0x18008bccd  retn
0x18008bccf  xor     eax, eax
0x18008bcd1  jmp     short loc_18008BCB6
```
