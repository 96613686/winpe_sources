# CiLogPolicyEvent

- ea: `0x18006d284`
- end: `0x18006d3c6`
- name: `CiLogPolicyEvent`
- size: `322`
- prototype: `__int64 __fastcall(int, int, int, int, char, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180064af0`
- `0x1800ab5fc`
- `0x1800b4f38`

## callees

- `0x18002c0d0`
- `0x18006d284`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006d2cd`
- `ntoskrnl!EtwEventEnabled` at `0x18006d2cd`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006d372`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006d372`
- `ntoskrnl!EtwWrite` at `0x18006d39a`
- `ntoskrnl!EtwWrite` at `0x18006d39a`

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
0x18006d284  mov     rax, rsp
0x18006d287  mov     [rax+8], rbx
0x18006d28b  mov     [rax+20h], r9b
0x18006d28f  mov     [rax+18h], r8b
0x18006d293  push    rbp
0x18006d294  push    rsi
0x18006d295  push    rdi
0x18006d296  lea     rbp, [rax-4Fh]
0x18006d29a  sub     rsp, 0C0h
0x18006d2a1  mov     rax, cs:__security_cookie
0x18006d2a8  xor     rax, rsp
0x18006d2ab  mov     [rbp+47h+var_20], rax
0x18006d2af  mov     rbx, [rbp+47h+EventDescriptor]
0x18006d2b3  xor     eax, eax
0x18006d2b5  mov     rdi, rdx
0x18006d2b8  mov     [rbp+47h+var_A0], ax
0x18006d2bc  mov     rsi, rcx
0x18006d2bf  mov     [rbp+47h+var_9C], ax
0x18006d2c3  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d2ca  mov     rdx, rbx; EventDescriptor
0x18006d2cd  call    cs:__imp_EtwEventEnabled
0x18006d2d4  nop     dword ptr [rax+rax+00h]
0x18006d2d9  test    al, al
0x18006d2db  jnz     short loc_18006D2E4
0x18006d2dd  xor     eax, eax
0x18006d2df  jmp     loc_18006D3A6
0x18006d2e4  movzx   ecx, word ptr [rsi]
0x18006d2e7  movzx   edx, word ptr [rdi]
0x18006d2ea  movzx   eax, cx
0x18006d2ed  shr     ax, 1
0x18006d2f0  mov     [rbp+47h+var_A0], ax
0x18006d2f4  movzx   eax, dx
0x18006d2f7  shr     ax, 1
0x18006d2fa  mov     [rbp+47h+var_9C], ax
0x18006d2fe  lea     rax, [rbp+47h+var_A0]
0x18006d302  mov     [rbp+47h+UserData.Ptr], rax
0x18006d306  mov     rax, [rsi+8]
0x18006d30a  mov     [rbp+47h+var_80], rax
0x18006d30e  lea     rax, [rbp+47h+var_9C]
0x18006d312  mov     [rbp+47h+var_70], rax
0x18006d316  mov     rax, [rdi+8]
0x18006d31a  mov     [rbp+47h+var_60], rax
0x18006d31e  lea     rax, [rbp+47h+arg_10]
0x18006d322  mov     [rbp+47h+var_50], rax
0x18006d326  lea     rax, [rbp+47h+arg_18]
0x18006d32a  mov     [rbp+47h+var_40], rax
0x18006d32e  lea     rax, [rbp+47h+arg_20]
0x18006d332  mov     [rbp+47h+var_30], rax
0x18006d336  mov     qword ptr [rbp+47h+UserData.Size], 2
0x18006d33e  mov     [rbp+47h+var_78], ecx
0x18006d341  mov     [rbp+47h+var_74], 0
0x18006d348  mov     [rbp+47h+var_68], 2
0x18006d350  mov     [rbp+47h+var_58], edx
0x18006d353  mov     [rbp+47h+var_54], 0
0x18006d35a  mov     [rbp+47h+var_48], 1
0x18006d362  mov     [rbp+47h+var_38], 1
0x18006d36a  mov     [rbp+47h+var_28], 4
0x18006d372  call    cs:__imp_IoGetActivityIdThread
0x18006d379  nop     dword ptr [rax+rax+00h]
0x18006d37e  lea     rcx, [rbp+47h+UserData]
0x18006d382  mov     r9d, 7; UserDataCount
0x18006d388  mov     [rsp+20h], rcx; UserData
0x18006d38d  mov     r8, rax; ActivityId
0x18006d390  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d397  mov     rdx, rbx; EventDescriptor
0x18006d39a  call    cs:__imp_EtwWrite
0x18006d3a1  nop     dword ptr [rax+rax+00h]
0x18006d3a6  mov     rcx, [rbp+47h+var_20]
0x18006d3aa  xor     rcx, rsp; StackCookie
0x18006d3ad  call    __security_check_cookie
0x18006d3b2  mov     rbx, [rsp+0D0h+arg_0]
0x18006d3ba  add     rsp, 0C0h
0x18006d3c1  pop     rdi
0x18006d3c2  pop     rsi
0x18006d3c3  pop     rbp
0x18006d3c4  retn
```
