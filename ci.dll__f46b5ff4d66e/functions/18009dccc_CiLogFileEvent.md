# CiLogFileEvent

- ea: `0x18009dccc`
- end: `0x18009dd91`
- name: `CiLogFileEvent`
- size: `197`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18005cee8`
- `0x18009ca38`
- `0x18009d178`
- `0x18009dc10`
- `0x1800a2a68`
- `0x1800db63c`
- `0x1800e4cb8`

## callees

- `0x18002bef0`
- `0x18009dccc`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18009dcf9`
- `ntoskrnl!EtwEventEnabled` at `0x18009dcf9`
- `ntoskrnl!IoGetActivityIdThread` at `0x18009dd43`
- `ntoskrnl!IoGetActivityIdThread` at `0x18009dd43`
- `ntoskrnl!EtwWrite` at `0x18009dd6c`
- `ntoskrnl!EtwWrite` at `0x18009dd6c`

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
0x18009dccc  mov     [rsp+arg_0], rbx
0x18009dcd1  push    rdi
0x18009dcd2  sub     rsp, 60h
0x18009dcd6  mov     rax, cs:__security_cookie
0x18009dcdd  xor     rax, rsp
0x18009dce0  mov     [rsp+68h+var_10], rax
0x18009dce5  mov     rdi, rcx
0x18009dce8  xor     eax, eax
0x18009dcea  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18009dcf1  mov     rbx, rdx
0x18009dcf4  mov     [rsp+68h+var_38], ax
0x18009dcf9  call    cs:__imp_EtwEventEnabled
0x18009dd00  nop     dword ptr [rax+rax+00h]
0x18009dd05  test    al, al
0x18009dd07  jnz     short loc_18009DD0D
0x18009dd09  xor     eax, eax
0x18009dd0b  jmp     short loc_18009DD78
0x18009dd0d  movzx   ecx, word ptr [rdi]
0x18009dd10  movzx   eax, cx
0x18009dd13  mov     qword ptr [rsp+68h+var_30.Size], 2
0x18009dd1c  shr     ax, 1
0x18009dd1f  mov     [rsp+68h+var_38], ax
0x18009dd24  lea     rax, [rsp+68h+var_38]
0x18009dd29  mov     [rsp+68h+var_30.Ptr], rax
0x18009dd2e  mov     rax, [rdi+8]
0x18009dd32  mov     [rsp+68h+var_20], rax
0x18009dd37  mov     [rsp+68h+var_18], ecx
0x18009dd3b  mov     [rsp+68h+var_14], 0
0x18009dd43  call    cs:__imp_IoGetActivityIdThread
0x18009dd4a  nop     dword ptr [rax+rax+00h]
0x18009dd4f  lea     rcx, [rsp+68h+var_30]
0x18009dd54  mov     r9d, 2; UserDataCount
0x18009dd5a  mov     [rsp+68h+UserData], rcx; UserData
0x18009dd5f  mov     r8, rax; ActivityId
0x18009dd62  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18009dd69  mov     rdx, rbx; EventDescriptor
0x18009dd6c  call    cs:__imp_EtwWrite
0x18009dd73  nop     dword ptr [rax+rax+00h]
0x18009dd78  mov     rcx, [rsp+68h+var_10]
0x18009dd7d  xor     rcx, rsp; StackCookie
0x18009dd80  call    __security_check_cookie
0x18009dd85  mov     rbx, [rsp+68h+arg_0]
0x18009dd8a  add     rsp, 60h
0x18009dd8e  pop     rdi
0x18009dd8f  retn
```
