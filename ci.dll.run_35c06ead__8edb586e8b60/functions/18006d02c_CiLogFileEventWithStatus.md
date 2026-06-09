# CiLogFileEventWithStatus

- ea: `0x18006d02c`
- end: `0x18006d10c`
- name: `CiLogFileEventWithStatus`
- size: `224`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18005d4f0`
- `0x18008f724`

## callees

- `0x18002c0d0`
- `0x18006d02c`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006d066`
- `ntoskrnl!EtwEventEnabled` at `0x18006d066`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006d0b9`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006d0b9`
- `ntoskrnl!EtwWrite` at `0x18006d0e1`
- `ntoskrnl!EtwWrite` at `0x18006d0e1`

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
0x18006d02c  mov     [rsp-8+arg_0], rbx
0x18006d031  mov     [rsp-8+arg_18], rdi
0x18006d036  mov     [rsp-8+arg_8], edx
0x18006d03a  push    rbp
0x18006d03b  mov     rbp, rsp
0x18006d03e  sub     rsp, 70h
0x18006d042  mov     rax, cs:__security_cookie
0x18006d049  xor     rax, rsp
0x18006d04c  mov     [rbp+var_8], rax
0x18006d050  mov     rdi, rcx
0x18006d053  xor     eax, eax
0x18006d055  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d05c  mov     rdx, r8; EventDescriptor
0x18006d05f  mov     [rbp+var_40], ax
0x18006d063  mov     rbx, r8
0x18006d066  call    cs:__imp_EtwEventEnabled
0x18006d06d  nop     dword ptr [rax+rax+00h]
0x18006d072  test    al, al
0x18006d074  jnz     short loc_18006D07A
0x18006d076  xor     eax, eax
0x18006d078  jmp     short loc_18006D0ED
0x18006d07a  movzx   ecx, word ptr [rdi]
0x18006d07d  movzx   eax, cx
0x18006d080  mov     qword ptr [rbp+var_38.Size], 2
0x18006d088  shr     ax, 1
0x18006d08b  mov     [rbp+var_40], ax
0x18006d08f  lea     rax, [rbp+var_40]
0x18006d093  mov     [rbp+var_38.Ptr], rax
0x18006d097  mov     rax, [rdi+8]
0x18006d09b  mov     [rbp+var_28], rax
0x18006d09f  lea     rax, [rbp+arg_8]
0x18006d0a3  mov     [rbp+var_18], rax
0x18006d0a7  mov     [rbp+var_20], ecx
0x18006d0aa  mov     [rbp+var_1C], 0
0x18006d0b1  mov     [rbp+var_10], 4
0x18006d0b9  call    cs:__imp_IoGetActivityIdThread
0x18006d0c0  nop     dword ptr [rax+rax+00h]
0x18006d0c5  lea     rcx, [rbp+var_38]
0x18006d0c9  mov     r9d, 3; UserDataCount
0x18006d0cf  mov     [rsp+70h+UserData], rcx; UserData
0x18006d0d4  mov     r8, rax; ActivityId
0x18006d0d7  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d0de  mov     rdx, rbx; EventDescriptor
0x18006d0e1  call    cs:__imp_EtwWrite
0x18006d0e8  nop     dword ptr [rax+rax+00h]
0x18006d0ed  mov     rcx, [rbp+var_8]
0x18006d0f1  xor     rcx, rsp; StackCookie
0x18006d0f4  call    __security_check_cookie
0x18006d0f9  lea     r11, [rsp+70h+var_s0]
0x18006d0fe  mov     rbx, [r11+10h]
0x18006d102  mov     rdi, [r11+28h]
0x18006d106  mov     rsp, r11
0x18006d109  pop     rbp
0x18006d10a  retn
```
