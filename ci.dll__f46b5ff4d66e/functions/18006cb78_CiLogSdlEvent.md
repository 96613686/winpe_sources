# CiLogSdlEvent

- ea: `0x18006cb78`
- end: `0x18006cca2`
- name: `CiLogSdlEvent`
- size: `298`
- prototype: `__int64 __fastcall(int, int, int, int, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180064160`

## callees

- `0x18002bef0`
- `0x18006cb78`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006cbc0`
- `ntoskrnl!EtwEventEnabled` at `0x18006cbc0`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006cc55`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006cc55`
- `ntoskrnl!EtwWrite` at `0x18006cc7d`
- `ntoskrnl!EtwWrite` at `0x18006cc7d`

## pseudocode

```c
NTSTATUS __fastcall CiLogSdlEvent(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        __int64 a3,
        int a4,
        PCEVENT_DESCRIPTOR EventDescriptor)
{
  const EVENT_DESCRIPTOR *v5; // rbx
  int v9; // ecx
  int v10; // edx
  const GUID *ActivityIdThread; // rax
  __int16 v12; // [rsp+30h] [rbp-51h] BYREF
  __int16 v13; // [rsp+34h] [rbp-4Dh] BYREF
  int v14; // [rsp+38h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-41h] BYREF
  __int64 v16; // [rsp+50h] [rbp-31h]
  int v17; // [rsp+58h] [rbp-29h]
  int v18; // [rsp+5Ch] [rbp-25h]
  __int16 *v19; // [rsp+60h] [rbp-21h]
  __int64 v20; // [rsp+68h] [rbp-19h]
  __int64 v21; // [rsp+70h] [rbp-11h]
  int v22; // [rsp+78h] [rbp-9h]
  int v23; // [rsp+7Ch] [rbp-5h]
  int *v24; // [rsp+80h] [rbp-1h]
  __int64 v25; // [rsp+88h] [rbp+7h]
  int *v26; // [rsp+90h] [rbp+Fh]
  __int64 v27; // [rsp+98h] [rbp+17h]
  int v28; // [rsp+F8h] [rbp+77h] BYREF

  v28 = a4;
  v5 = EventDescriptor;
  v14 = 1;
  v12 = 0;
  v13 = 0;
  if ( !EtwEventEnabled(g_EtwEventHandle, EventDescriptor) )
    return 0;
  v9 = *a1;
  v10 = *a2;
  v12 = *a1 >> 1;
  v13 = (unsigned __int16)v10 >> 1;
  UserData.Ptr = (ULONGLONG)&v12;
  v16 = *((_QWORD *)a1 + 1);
  v19 = &v13;
  v21 = *((_QWORD *)a2 + 1);
  v24 = &v14;
  v26 = &v28;
  *(_QWORD *)&UserData.Size = 2;
  v17 = v9;
  v18 = 0;
  v20 = 2;
  v22 = v10;
  v23 = 0;
  v25 = 1;
  v27 = 4;
  ActivityIdThread = (const GUID *)IoGetActivityIdThread();
  return EtwWrite(g_EtwEventHandle, v5, ActivityIdThread, 6u, &UserData);
}

```

## disassembly

```asm
0x18006cb78  mov     [rsp-8+arg_18], r9d
0x18006cb7d  push    rbp
0x18006cb7e  push    rbx
0x18006cb7f  push    rsi
0x18006cb80  push    rdi
0x18006cb81  lea     rbp, [rsp-37h]
0x18006cb86  sub     rsp, 0B8h
0x18006cb8d  mov     rax, cs:__security_cookie
0x18006cb94  xor     rax, rsp
0x18006cb97  mov     [rbp+4Fh+var_30], rax
0x18006cb9b  mov     rbx, [rbp+4Fh+EventDescriptor]
0x18006cb9f  xor     eax, eax
0x18006cba1  mov     rdi, rdx
0x18006cba4  mov     [rbp+4Fh+var_98], 1
0x18006cbab  mov     rsi, rcx
0x18006cbae  mov     [rbp+4Fh+var_A0], ax
0x18006cbb2  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006cbb9  mov     rdx, rbx; EventDescriptor
0x18006cbbc  mov     [rbp+4Fh+var_9C], ax
0x18006cbc0  call    cs:__imp_EtwEventEnabled
0x18006cbc7  nop     dword ptr [rax+rax+00h]
0x18006cbcc  test    al, al
0x18006cbce  jnz     short loc_18006CBD7
0x18006cbd0  xor     eax, eax
0x18006cbd2  jmp     loc_18006CC89
0x18006cbd7  movzx   ecx, word ptr [rsi]
0x18006cbda  movzx   edx, word ptr [rdi]
0x18006cbdd  movzx   eax, cx
0x18006cbe0  shr     ax, 1
0x18006cbe3  mov     [rbp+4Fh+var_A0], ax
0x18006cbe7  movzx   eax, dx
0x18006cbea  shr     ax, 1
0x18006cbed  mov     [rbp+4Fh+var_9C], ax
0x18006cbf1  lea     rax, [rbp+4Fh+var_A0]
0x18006cbf5  mov     [rbp+4Fh+var_90.Ptr], rax
0x18006cbf9  mov     rax, [rsi+8]
0x18006cbfd  mov     [rbp+4Fh+var_80], rax
0x18006cc01  lea     rax, [rbp+4Fh+var_9C]
0x18006cc05  mov     [rbp+4Fh+var_70], rax
0x18006cc09  mov     rax, [rdi+8]
0x18006cc0d  mov     [rbp+4Fh+var_60], rax
0x18006cc11  lea     rax, [rbp+4Fh+var_98]
0x18006cc15  mov     [rbp+4Fh+var_50], rax
0x18006cc19  lea     rax, [rbp+4Fh+arg_18]
0x18006cc1d  mov     [rbp+4Fh+var_40], rax
0x18006cc21  mov     qword ptr [rbp+4Fh+var_90.Size], 2
0x18006cc29  mov     [rbp+4Fh+var_78], ecx
0x18006cc2c  mov     [rbp+4Fh+var_74], 0
0x18006cc33  mov     [rbp+4Fh+var_68], 2
0x18006cc3b  mov     [rbp+4Fh+var_58], edx
0x18006cc3e  mov     [rbp+4Fh+var_54], 0
0x18006cc45  mov     [rbp+4Fh+var_48], 1
0x18006cc4d  mov     [rbp+4Fh+var_38], 4
0x18006cc55  call    cs:__imp_IoGetActivityIdThread
0x18006cc5c  nop     dword ptr [rax+rax+00h]
0x18006cc61  lea     rcx, [rbp+4Fh+var_90]
0x18006cc65  mov     r9d, 6; UserDataCount
0x18006cc6b  mov     [rsp+0D0h+UserData], rcx; UserData
0x18006cc70  mov     r8, rax; ActivityId
0x18006cc73  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006cc7a  mov     rdx, rbx; EventDescriptor
0x18006cc7d  call    cs:__imp_EtwWrite
0x18006cc84  nop     dword ptr [rax+rax+00h]
0x18006cc89  mov     rcx, [rbp+4Fh+var_30]
0x18006cc8d  xor     rcx, rsp; StackCookie
0x18006cc90  call    __security_check_cookie
0x18006cc95  add     rsp, 0B8h
0x18006cc9c  pop     rdi
0x18006cc9d  pop     rsi
0x18006cc9e  pop     rbx
0x18006cc9f  pop     rbp
0x18006cca0  retn
```
