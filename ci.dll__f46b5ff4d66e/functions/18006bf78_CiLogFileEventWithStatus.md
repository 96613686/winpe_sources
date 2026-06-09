# CiLogFileEventWithStatus

- ea: `0x18006bf78`
- end: `0x18006c058`
- name: `CiLogFileEventWithStatus`
- size: `224`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18005cee8`
- `0x18009ce68`

## callees

- `0x18002bef0`
- `0x18006bf78`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006bfb2`
- `ntoskrnl!EtwEventEnabled` at `0x18006bfb2`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006c005`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006c005`
- `ntoskrnl!EtwWrite` at `0x18006c02d`
- `ntoskrnl!EtwWrite` at `0x18006c02d`

## pseudocode

```c
NTSTATUS __fastcall CiLogFileEventWithStatus(unsigned __int16 *a1, int a2, const EVENT_DESCRIPTOR *a3)
{
  __int64 v6; // rcx
  unsigned __int16 v7; // ax
  const GUID *ActivityIdThread; // rax
  __int16 v9; // [rsp+30h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-38h] BYREF
  __int64 v11; // [rsp+48h] [rbp-28h]
  int v12; // [rsp+50h] [rbp-20h]
  int v13; // [rsp+54h] [rbp-1Ch]
  int *v14; // [rsp+58h] [rbp-18h]
  __int64 v15; // [rsp+60h] [rbp-10h]
  int v16; // [rsp+88h] [rbp+18h] BYREF

  v16 = a2;
  v9 = 0;
  if ( !EtwEventEnabled(g_EtwEventHandle, a3) )
    return 0;
  v6 = *a1;
  v7 = *a1;
  *(_QWORD *)&UserData.Size = 2;
  v9 = v7 >> 1;
  UserData.Ptr = (ULONGLONG)&v9;
  v11 = *((_QWORD *)a1 + 1);
  v14 = &v16;
  v12 = v6;
  v13 = 0;
  v15 = 4;
  ActivityIdThread = (const GUID *)IoGetActivityIdThread(v6);
  return EtwWrite(g_EtwEventHandle, a3, ActivityIdThread, 3u, &UserData);
}

```

## disassembly

```asm
0x18006bf78  mov     [rsp-8+arg_0], rbx
0x18006bf7d  mov     [rsp-8+arg_18], rdi
0x18006bf82  mov     [rsp-8+arg_8], edx
0x18006bf86  push    rbp
0x18006bf87  mov     rbp, rsp
0x18006bf8a  sub     rsp, 70h
0x18006bf8e  mov     rax, cs:__security_cookie
0x18006bf95  xor     rax, rsp
0x18006bf98  mov     [rbp+var_8], rax
0x18006bf9c  mov     rdi, rcx
0x18006bf9f  xor     eax, eax
0x18006bfa1  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006bfa8  mov     rdx, r8; EventDescriptor
0x18006bfab  mov     [rbp+var_40], ax
0x18006bfaf  mov     rbx, r8
0x18006bfb2  call    cs:__imp_EtwEventEnabled
0x18006bfb9  nop     dword ptr [rax+rax+00h]
0x18006bfbe  test    al, al
0x18006bfc0  jnz     short loc_18006BFC6
0x18006bfc2  xor     eax, eax
0x18006bfc4  jmp     short loc_18006C039
0x18006bfc6  movzx   ecx, word ptr [rdi]
0x18006bfc9  movzx   eax, cx
0x18006bfcc  mov     qword ptr [rbp+var_38.Size], 2
0x18006bfd4  shr     ax, 1
0x18006bfd7  mov     [rbp+var_40], ax
0x18006bfdb  lea     rax, [rbp+var_40]
0x18006bfdf  mov     [rbp+var_38.Ptr], rax
0x18006bfe3  mov     rax, [rdi+8]
0x18006bfe7  mov     [rbp+var_28], rax
0x18006bfeb  lea     rax, [rbp+arg_8]
0x18006bfef  mov     [rbp+var_18], rax
0x18006bff3  mov     [rbp+var_20], ecx
0x18006bff6  mov     [rbp+var_1C], 0
0x18006bffd  mov     [rbp+var_10], 4
0x18006c005  call    cs:__imp_IoGetActivityIdThread
0x18006c00c  nop     dword ptr [rax+rax+00h]
0x18006c011  lea     rcx, [rbp+var_38]
0x18006c015  mov     r9d, 3; UserDataCount
0x18006c01b  mov     [rsp+70h+UserData], rcx; UserData
0x18006c020  mov     r8, rax; ActivityId
0x18006c023  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006c02a  mov     rdx, rbx; EventDescriptor
0x18006c02d  call    cs:__imp_EtwWrite
0x18006c034  nop     dword ptr [rax+rax+00h]
0x18006c039  mov     rcx, [rbp+var_8]
0x18006c03d  xor     rcx, rsp; StackCookie
0x18006c040  call    __security_check_cookie
0x18006c045  lea     r11, [rsp+70h+var_s0]
0x18006c04a  mov     rbx, [r11+10h]
0x18006c04e  mov     rdi, [r11+28h]
0x18006c052  mov     rsp, r11
0x18006c055  pop     rbp
0x18006c056  retn
```
