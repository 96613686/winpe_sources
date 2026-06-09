# CiLogFileRequestedValidationEventWithProcessName

- ea: `0x1800a0258`
- end: `0x1800a038a`
- name: `CiLogFileRequestedValidationEventWithProcessName`
- size: `306`
- prototype: `__int64 __fastcall(int, int, int, int, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800a0190`
- `0x1800e4ca8`

## callees

- `0x18002bf20`
- `0x1800a0258`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x1800a02a1`
- `ntoskrnl!EtwEventEnabled` at `0x1800a02a1`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800a0336`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800a0336`
- `ntoskrnl!EtwWrite` at `0x1800a035e`
- `ntoskrnl!EtwWrite` at `0x1800a035e`

## pseudocode

```c
NTSTATUS __fastcall CiLogFileRequestedValidationEventWithProcessName(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        int a3,
        char a4,
        PCEVENT_DESCRIPTOR EventDescriptor)
{
  const EVENT_DESCRIPTOR *v5; // rbx
  unsigned __int16 v9; // ax
  int v10; // ecx
  const GUID *ActivityIdThread; // rax
  __int16 v12; // [rsp+38h] [rbp-41h] BYREF
  __int16 v13; // [rsp+3Ch] [rbp-3Dh] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-31h] BYREF
  __int64 v15; // [rsp+58h] [rbp-21h]
  int v16; // [rsp+60h] [rbp-19h]
  int v17; // [rsp+64h] [rbp-15h]
  int *v18; // [rsp+68h] [rbp-11h]
  __int64 v19; // [rsp+70h] [rbp-9h]
  char *v20; // [rsp+78h] [rbp-1h]
  __int64 v21; // [rsp+80h] [rbp+7h]
  __int16 *v22; // [rsp+88h] [rbp+Fh]
  __int64 v23; // [rsp+90h] [rbp+17h]
  __int64 v24; // [rsp+98h] [rbp+1Fh]
  int v25; // [rsp+A0h] [rbp+27h]
  int v26; // [rsp+A4h] [rbp+2Bh]
  int v27; // [rsp+E8h] [rbp+6Fh] BYREF
  char v28; // [rsp+F0h] [rbp+77h] BYREF

  v28 = a4;
  v27 = a3;
  v5 = EventDescriptor;
  v12 = 0;
  v13 = 0;
  if ( !EtwEventEnabled(g_EtwEventHandle, EventDescriptor) )
    return 0;
  v9 = *a1;
  v16 = *a1;
  v10 = *a2;
  v12 = v9 >> 1;
  UserData.Ptr = (ULONGLONG)&v12;
  v15 = *((_QWORD *)a1 + 1);
  v18 = &v27;
  v20 = &v28;
  v13 = (unsigned __int16)v10 >> 1;
  v22 = &v13;
  v24 = *((_QWORD *)a2 + 1);
  *(_QWORD *)&UserData.Size = 2;
  v17 = 0;
  v19 = 4;
  v21 = 1;
  v23 = 2;
  v25 = v10;
  v26 = 0;
  ActivityIdThread = (const GUID *)IoGetActivityIdThread();
  return EtwWrite(g_EtwEventHandle, v5, ActivityIdThread, 6u, &UserData);
}

```

## disassembly

```asm
0x1800a0258  mov     rax, rsp
0x1800a025b  mov     [rax+8], rbx
0x1800a025f  mov     [rax+20h], r9b
0x1800a0263  mov     [rax+18h], r8d
0x1800a0267  push    rbp
0x1800a0268  push    rsi
0x1800a0269  push    rdi
0x1800a026a  lea     rbp, [rax-57h]
0x1800a026e  sub     rsp, 0B0h
0x1800a0275  mov     rax, cs:__security_cookie
0x1800a027c  xor     rax, rsp
0x1800a027f  mov     [rbp+4Fh+var_20], rax
0x1800a0283  mov     rbx, [rbp+4Fh+EventDescriptor]
0x1800a0287  xor     eax, eax
0x1800a0289  mov     rdi, rdx
0x1800a028c  mov     [rbp+4Fh+var_90], ax
0x1800a0290  mov     rsi, rcx
0x1800a0293  mov     [rbp+4Fh+var_8C], ax
0x1800a0297  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800a029e  mov     rdx, rbx; EventDescriptor
0x1800a02a1  call    cs:__imp_EtwEventEnabled
0x1800a02a8  nop     dword ptr [rax+rax+00h]
0x1800a02ad  test    al, al
0x1800a02af  jnz     short loc_1800A02B8
0x1800a02b1  xor     eax, eax
0x1800a02b3  jmp     loc_1800A036A
0x1800a02b8  movzx   ecx, word ptr [rsi]
0x1800a02bb  movzx   eax, cx
0x1800a02be  mov     [rbp+4Fh+var_68], ecx
0x1800a02c1  movzx   ecx, word ptr [rdi]
0x1800a02c4  shr     ax, 1
0x1800a02c7  mov     [rbp+4Fh+var_90], ax
0x1800a02cb  lea     rax, [rbp+4Fh+var_90]
0x1800a02cf  mov     [rbp+4Fh+UserData.Ptr], rax
0x1800a02d3  mov     rax, [rsi+8]
0x1800a02d7  mov     [rbp+4Fh+var_70], rax
0x1800a02db  lea     rax, [rbp+4Fh+arg_10]
0x1800a02df  mov     [rbp+4Fh+var_60], rax
0x1800a02e3  lea     rax, [rbp+4Fh+arg_18]
0x1800a02e7  mov     [rbp+4Fh+var_50], rax
0x1800a02eb  movzx   eax, cx
0x1800a02ee  shr     ax, 1
0x1800a02f1  mov     [rbp+4Fh+var_8C], ax
0x1800a02f5  lea     rax, [rbp+4Fh+var_8C]
0x1800a02f9  mov     [rbp+4Fh+var_40], rax
0x1800a02fd  mov     rax, [rdi+8]
0x1800a0301  mov     [rbp+4Fh+var_30], rax
0x1800a0305  mov     qword ptr [rbp+4Fh+UserData.Size], 2
0x1800a030d  mov     [rbp+4Fh+var_64], 0
0x1800a0314  mov     [rbp+4Fh+var_58], 4
0x1800a031c  mov     [rbp+4Fh+var_48], 1
0x1800a0324  mov     [rbp+4Fh+var_38], 2
0x1800a032c  mov     [rbp+4Fh+var_28], ecx
0x1800a032f  mov     [rbp+4Fh+var_24], 0
0x1800a0336  call    cs:__imp_IoGetActivityIdThread
0x1800a033d  nop     dword ptr [rax+rax+00h]
0x1800a0342  lea     rcx, [rbp+4Fh+UserData]
0x1800a0346  mov     r9d, 6; UserDataCount
0x1800a034c  mov     [rsp+20h], rcx; UserData
0x1800a0351  mov     r8, rax; ActivityId
0x1800a0354  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800a035b  mov     rdx, rbx; EventDescriptor
0x1800a035e  call    cs:__imp_EtwWrite
0x1800a0365  nop     dword ptr [rax+rax+00h]
0x1800a036a  mov     rcx, [rbp+4Fh+var_20]
0x1800a036e  xor     rcx, rsp; StackCookie
0x1800a0371  call    __security_check_cookie
0x1800a0376  mov     rbx, [rsp+0C0h+arg_0]
0x1800a037e  add     rsp, 0B0h
0x1800a0385  pop     rdi
0x1800a0386  pop     rsi
0x1800a0387  pop     rbp
0x1800a0388  retn
```
