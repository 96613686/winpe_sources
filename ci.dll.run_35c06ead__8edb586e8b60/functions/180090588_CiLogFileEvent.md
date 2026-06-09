# CiLogFileEvent

- ea: `0x180090588`
- end: `0x18009064d`
- name: `CiLogFileEvent`
- size: `197`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18005d4f0`
- `0x18008f2f4`
- `0x18008fa34`
- `0x1800904cc`
- `0x1800a4538`
- `0x1800dca3c`
- `0x1800e5228`

## callees

- `0x18002c0d0`
- `0x180090588`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x1800905b5`
- `ntoskrnl!EtwEventEnabled` at `0x1800905b5`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800905ff`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800905ff`
- `ntoskrnl!EtwWrite` at `0x180090628`
- `ntoskrnl!EtwWrite` at `0x180090628`

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
0x180090588  mov     [rsp+arg_0], rbx
0x18009058d  push    rdi
0x18009058e  sub     rsp, 60h
0x180090592  mov     rax, cs:__security_cookie
0x180090599  xor     rax, rsp
0x18009059c  mov     [rsp+68h+var_10], rax
0x1800905a1  mov     rdi, rcx
0x1800905a4  xor     eax, eax
0x1800905a6  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800905ad  mov     rbx, rdx
0x1800905b0  mov     [rsp+68h+var_38], ax
0x1800905b5  call    cs:__imp_EtwEventEnabled
0x1800905bc  nop     dword ptr [rax+rax+00h]
0x1800905c1  test    al, al
0x1800905c3  jnz     short loc_1800905C9
0x1800905c5  xor     eax, eax
0x1800905c7  jmp     short loc_180090634
0x1800905c9  movzx   ecx, word ptr [rdi]
0x1800905cc  movzx   eax, cx
0x1800905cf  mov     qword ptr [rsp+68h+var_30.Size], 2
0x1800905d8  shr     ax, 1
0x1800905db  mov     [rsp+68h+var_38], ax
0x1800905e0  lea     rax, [rsp+68h+var_38]
0x1800905e5  mov     [rsp+68h+var_30.Ptr], rax
0x1800905ea  mov     rax, [rdi+8]
0x1800905ee  mov     [rsp+68h+var_20], rax
0x1800905f3  mov     [rsp+68h+var_18], ecx
0x1800905f7  mov     [rsp+68h+var_14], 0
0x1800905ff  call    cs:__imp_IoGetActivityIdThread
0x180090606  nop     dword ptr [rax+rax+00h]
0x18009060b  lea     rcx, [rsp+68h+var_30]
0x180090610  mov     r9d, 2; UserDataCount
0x180090616  mov     [rsp+68h+UserData], rcx; UserData
0x18009061b  mov     r8, rax; ActivityId
0x18009061e  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x180090625  mov     rdx, rbx; EventDescriptor
0x180090628  call    cs:__imp_EtwWrite
0x18009062f  nop     dword ptr [rax+rax+00h]
0x180090634  mov     rcx, [rsp+68h+var_10]
0x180090639  xor     rcx, rsp; StackCookie
0x18009063c  call    __security_check_cookie
0x180090641  mov     rbx, [rsp+68h+arg_0]
0x180090646  add     rsp, 60h
0x18009064a  pop     rdi
0x18009064b  retn
```
