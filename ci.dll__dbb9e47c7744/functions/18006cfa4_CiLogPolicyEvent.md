# CiLogPolicyEvent

- ea: `0x18006cfa4`
- end: `0x18006d0e6`
- name: `CiLogPolicyEvent`
- size: `322`
- prototype: `__int64 __fastcall(int, int, int, int, char, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180064980`
- `0x1800ac2ac`
- `0x1800b5098`

## callees

- `0x18002bf20`
- `0x18006cfa4`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006cfed`
- `ntoskrnl!EtwEventEnabled` at `0x18006cfed`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006d092`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006d092`
- `ntoskrnl!EtwWrite` at `0x18006d0ba`
- `ntoskrnl!EtwWrite` at `0x18006d0ba`

## pseudocode

```c
NTSTATUS __fastcall CiLogPolicyEvent(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        char a3,
        char a4,
        char a5,
        PCEVENT_DESCRIPTOR EventDescriptor)
{
  const EVENT_DESCRIPTOR *v6; // rbx
  int v10; // ecx
  int v11; // edx
  const GUID *ActivityIdThread; // rax
  __int16 v13; // [rsp+38h] [rbp-59h] BYREF
  __int16 v14; // [rsp+3Ch] [rbp-55h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-49h] BYREF
  __int64 v16; // [rsp+58h] [rbp-39h]
  int v17; // [rsp+60h] [rbp-31h]
  int v18; // [rsp+64h] [rbp-2Dh]
  __int16 *v19; // [rsp+68h] [rbp-29h]
  __int64 v20; // [rsp+70h] [rbp-21h]
  __int64 v21; // [rsp+78h] [rbp-19h]
  int v22; // [rsp+80h] [rbp-11h]
  int v23; // [rsp+84h] [rbp-Dh]
  char *v24; // [rsp+88h] [rbp-9h]
  __int64 v25; // [rsp+90h] [rbp-1h]
  char *v26; // [rsp+98h] [rbp+7h]
  __int64 v27; // [rsp+A0h] [rbp+Fh]
  char *v28; // [rsp+A8h] [rbp+17h]
  __int64 v29; // [rsp+B0h] [rbp+1Fh]
  char v30; // [rsp+F8h] [rbp+67h] BYREF
  char v31; // [rsp+100h] [rbp+6Fh] BYREF

  v31 = a4;
  v30 = a3;
  v6 = EventDescriptor;
  v13 = 0;
  v14 = 0;
  if ( !EtwEventEnabled(g_EtwEventHandle, EventDescriptor) )
    return 0;
  v10 = *a1;
  v11 = *a2;
  v13 = *a1 >> 1;
  v14 = (unsigned __int16)v11 >> 1;
  UserData.Ptr = (ULONGLONG)&v13;
  v16 = *((_QWORD *)a1 + 1);
  v19 = &v14;
  v21 = *((_QWORD *)a2 + 1);
  v24 = &v30;
  v26 = &v31;
  v28 = &a5;
  *(_QWORD *)&UserData.Size = 2;
  v17 = v10;
  v18 = 0;
  v20 = 2;
  v22 = v11;
  v23 = 0;
  v25 = 1;
  v27 = 1;
  v29 = 4;
  ActivityIdThread = (const GUID *)IoGetActivityIdThread();
  return EtwWrite(g_EtwEventHandle, v6, ActivityIdThread, 7u, &UserData);
}

```

## disassembly

```asm
0x18006cfa4  mov     rax, rsp
0x18006cfa7  mov     [rax+8], rbx
0x18006cfab  mov     [rax+20h], r9b
0x18006cfaf  mov     [rax+18h], r8b
0x18006cfb3  push    rbp
0x18006cfb4  push    rsi
0x18006cfb5  push    rdi
0x18006cfb6  lea     rbp, [rax-4Fh]
0x18006cfba  sub     rsp, 0C0h
0x18006cfc1  mov     rax, cs:__security_cookie
0x18006cfc8  xor     rax, rsp
0x18006cfcb  mov     [rbp+47h+var_20], rax
0x18006cfcf  mov     rbx, [rbp+47h+EventDescriptor]
0x18006cfd3  xor     eax, eax
0x18006cfd5  mov     rdi, rdx
0x18006cfd8  mov     [rbp+47h+var_A0], ax
0x18006cfdc  mov     rsi, rcx
0x18006cfdf  mov     [rbp+47h+var_9C], ax
0x18006cfe3  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006cfea  mov     rdx, rbx; EventDescriptor
0x18006cfed  call    cs:__imp_EtwEventEnabled
0x18006cff4  nop     dword ptr [rax+rax+00h]
0x18006cff9  test    al, al
0x18006cffb  jnz     short loc_18006D004
0x18006cffd  xor     eax, eax
0x18006cfff  jmp     loc_18006D0C6
0x18006d004  movzx   ecx, word ptr [rsi]
0x18006d007  movzx   edx, word ptr [rdi]
0x18006d00a  movzx   eax, cx
0x18006d00d  shr     ax, 1
0x18006d010  mov     [rbp+47h+var_A0], ax
0x18006d014  movzx   eax, dx
0x18006d017  shr     ax, 1
0x18006d01a  mov     [rbp+47h+var_9C], ax
0x18006d01e  lea     rax, [rbp+47h+var_A0]
0x18006d022  mov     [rbp+47h+UserData.Ptr], rax
0x18006d026  mov     rax, [rsi+8]
0x18006d02a  mov     [rbp+47h+var_80], rax
0x18006d02e  lea     rax, [rbp+47h+var_9C]
0x18006d032  mov     [rbp+47h+var_70], rax
0x18006d036  mov     rax, [rdi+8]
0x18006d03a  mov     [rbp+47h+var_60], rax
0x18006d03e  lea     rax, [rbp+47h+arg_10]
0x18006d042  mov     [rbp+47h+var_50], rax
0x18006d046  lea     rax, [rbp+47h+arg_18]
0x18006d04a  mov     [rbp+47h+var_40], rax
0x18006d04e  lea     rax, [rbp+47h+arg_20]
0x18006d052  mov     [rbp+47h+var_30], rax
0x18006d056  mov     qword ptr [rbp+47h+UserData.Size], 2
0x18006d05e  mov     [rbp+47h+var_78], ecx
0x18006d061  mov     [rbp+47h+var_74], 0
0x18006d068  mov     [rbp+47h+var_68], 2
0x18006d070  mov     [rbp+47h+var_58], edx
0x18006d073  mov     [rbp+47h+var_54], 0
0x18006d07a  mov     [rbp+47h+var_48], 1
0x18006d082  mov     [rbp+47h+var_38], 1
0x18006d08a  mov     [rbp+47h+var_28], 4
0x18006d092  call    cs:__imp_IoGetActivityIdThread
0x18006d099  nop     dword ptr [rax+rax+00h]
0x18006d09e  lea     rcx, [rbp+47h+UserData]
0x18006d0a2  mov     r9d, 7; UserDataCount
0x18006d0a8  mov     [rsp+20h], rcx; UserData
0x18006d0ad  mov     r8, rax; ActivityId
0x18006d0b0  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d0b7  mov     rdx, rbx; EventDescriptor
0x18006d0ba  call    cs:__imp_EtwWrite
0x18006d0c1  nop     dword ptr [rax+rax+00h]
0x18006d0c6  mov     rcx, [rbp+47h+var_20]
0x18006d0ca  xor     rcx, rsp; StackCookie
0x18006d0cd  call    __security_check_cookie
0x18006d0d2  mov     rbx, [rsp+0D0h+arg_0]
0x18006d0da  add     rsp, 0C0h
0x18006d0e1  pop     rdi
0x18006d0e2  pop     rsi
0x18006d0e3  pop     rbp
0x18006d0e4  retn
```
