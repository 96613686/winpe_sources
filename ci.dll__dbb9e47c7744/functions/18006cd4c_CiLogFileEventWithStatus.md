# CiLogFileEventWithStatus

- ea: `0x18006cd4c`
- end: `0x18006ce2c`
- name: `CiLogFileEventWithStatus`
- size: `224`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18005d550`
- `0x18009e498`

## callees

- `0x18002bf20`
- `0x18006cd4c`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006cd86`
- `ntoskrnl!EtwEventEnabled` at `0x18006cd86`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006cdd9`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006cdd9`
- `ntoskrnl!EtwWrite` at `0x18006ce01`
- `ntoskrnl!EtwWrite` at `0x18006ce01`

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
0x18006cd4c  mov     [rsp-8+arg_0], rbx
0x18006cd51  mov     [rsp-8+arg_18], rdi
0x18006cd56  mov     [rsp-8+arg_8], edx
0x18006cd5a  push    rbp
0x18006cd5b  mov     rbp, rsp
0x18006cd5e  sub     rsp, 70h
0x18006cd62  mov     rax, cs:__security_cookie
0x18006cd69  xor     rax, rsp
0x18006cd6c  mov     [rbp+var_8], rax
0x18006cd70  mov     rdi, rcx
0x18006cd73  xor     eax, eax
0x18006cd75  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006cd7c  mov     rdx, r8; EventDescriptor
0x18006cd7f  mov     [rbp+var_40], ax
0x18006cd83  mov     rbx, r8
0x18006cd86  call    cs:__imp_EtwEventEnabled
0x18006cd8d  nop     dword ptr [rax+rax+00h]
0x18006cd92  test    al, al
0x18006cd94  jnz     short loc_18006CD9A
0x18006cd96  xor     eax, eax
0x18006cd98  jmp     short loc_18006CE0D
0x18006cd9a  movzx   ecx, word ptr [rdi]
0x18006cd9d  movzx   eax, cx
0x18006cda0  mov     qword ptr [rbp+var_38.Size], 2
0x18006cda8  shr     ax, 1
0x18006cdab  mov     [rbp+var_40], ax
0x18006cdaf  lea     rax, [rbp+var_40]
0x18006cdb3  mov     [rbp+var_38.Ptr], rax
0x18006cdb7  mov     rax, [rdi+8]
0x18006cdbb  mov     [rbp+var_28], rax
0x18006cdbf  lea     rax, [rbp+arg_8]
0x18006cdc3  mov     [rbp+var_18], rax
0x18006cdc7  mov     [rbp+var_20], ecx
0x18006cdca  mov     [rbp+var_1C], 0
0x18006cdd1  mov     [rbp+var_10], 4
0x18006cdd9  call    cs:__imp_IoGetActivityIdThread
0x18006cde0  nop     dword ptr [rax+rax+00h]
0x18006cde5  lea     rcx, [rbp+var_38]
0x18006cde9  mov     r9d, 3; UserDataCount
0x18006cdef  mov     [rsp+70h+UserData], rcx; UserData
0x18006cdf4  mov     r8, rax; ActivityId
0x18006cdf7  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006cdfe  mov     rdx, rbx; EventDescriptor
0x18006ce01  call    cs:__imp_EtwWrite
0x18006ce08  nop     dword ptr [rax+rax+00h]
0x18006ce0d  mov     rcx, [rbp+var_8]
0x18006ce11  xor     rcx, rsp; StackCookie
0x18006ce14  call    __security_check_cookie
0x18006ce19  lea     r11, [rsp+70h+var_s0]
0x18006ce1e  mov     rbx, [r11+10h]
0x18006ce22  mov     rdi, [r11+28h]
0x18006ce26  mov     rsp, r11
0x18006ce29  pop     rbp
0x18006ce2a  retn
```
