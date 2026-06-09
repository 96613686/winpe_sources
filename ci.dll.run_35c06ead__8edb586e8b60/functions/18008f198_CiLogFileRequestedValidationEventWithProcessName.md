# CiLogFileRequestedValidationEventWithProcessName

- ea: `0x18008f198`
- end: `0x18008f2ca`
- name: `CiLogFileRequestedValidationEventWithProcessName`
- size: `306`
- prototype: `__int64 __fastcall(int, int, int, int, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18008f0d0`
- `0x1800e5228`

## callees

- `0x18002c0d0`
- `0x18008f198`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18008f1e1`
- `ntoskrnl!EtwEventEnabled` at `0x18008f1e1`
- `ntoskrnl!IoGetActivityIdThread` at `0x18008f276`
- `ntoskrnl!IoGetActivityIdThread` at `0x18008f276`
- `ntoskrnl!EtwWrite` at `0x18008f29e`
- `ntoskrnl!EtwWrite` at `0x18008f29e`

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
0x18008f198  mov     rax, rsp
0x18008f19b  mov     [rax+8], rbx
0x18008f19f  mov     [rax+20h], r9b
0x18008f1a3  mov     [rax+18h], r8d
0x18008f1a7  push    rbp
0x18008f1a8  push    rsi
0x18008f1a9  push    rdi
0x18008f1aa  lea     rbp, [rax-57h]
0x18008f1ae  sub     rsp, 0B0h
0x18008f1b5  mov     rax, cs:__security_cookie
0x18008f1bc  xor     rax, rsp
0x18008f1bf  mov     [rbp+4Fh+var_20], rax
0x18008f1c3  mov     rbx, [rbp+4Fh+EventDescriptor]
0x18008f1c7  xor     eax, eax
0x18008f1c9  mov     rdi, rdx
0x18008f1cc  mov     [rbp+4Fh+var_90], ax
0x18008f1d0  mov     rsi, rcx
0x18008f1d3  mov     [rbp+4Fh+var_8C], ax
0x18008f1d7  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18008f1de  mov     rdx, rbx; EventDescriptor
0x18008f1e1  call    cs:__imp_EtwEventEnabled
0x18008f1e8  nop     dword ptr [rax+rax+00h]
0x18008f1ed  test    al, al
0x18008f1ef  jnz     short loc_18008F1F8
0x18008f1f1  xor     eax, eax
0x18008f1f3  jmp     loc_18008F2AA
0x18008f1f8  movzx   ecx, word ptr [rsi]
0x18008f1fb  movzx   eax, cx
0x18008f1fe  mov     [rbp+4Fh+var_68], ecx
0x18008f201  movzx   ecx, word ptr [rdi]
0x18008f204  shr     ax, 1
0x18008f207  mov     [rbp+4Fh+var_90], ax
0x18008f20b  lea     rax, [rbp+4Fh+var_90]
0x18008f20f  mov     [rbp+4Fh+UserData.Ptr], rax
0x18008f213  mov     rax, [rsi+8]
0x18008f217  mov     [rbp+4Fh+var_70], rax
0x18008f21b  lea     rax, [rbp+4Fh+arg_10]
0x18008f21f  mov     [rbp+4Fh+var_60], rax
0x18008f223  lea     rax, [rbp+4Fh+arg_18]
0x18008f227  mov     [rbp+4Fh+var_50], rax
0x18008f22b  movzx   eax, cx
0x18008f22e  shr     ax, 1
0x18008f231  mov     [rbp+4Fh+var_8C], ax
0x18008f235  lea     rax, [rbp+4Fh+var_8C]
0x18008f239  mov     [rbp+4Fh+var_40], rax
0x18008f23d  mov     rax, [rdi+8]
0x18008f241  mov     [rbp+4Fh+var_30], rax
0x18008f245  mov     qword ptr [rbp+4Fh+UserData.Size], 2
0x18008f24d  mov     [rbp+4Fh+var_64], 0
0x18008f254  mov     [rbp+4Fh+var_58], 4
0x18008f25c  mov     [rbp+4Fh+var_48], 1
0x18008f264  mov     [rbp+4Fh+var_38], 2
0x18008f26c  mov     [rbp+4Fh+var_28], ecx
0x18008f26f  mov     [rbp+4Fh+var_24], 0
0x18008f276  call    cs:__imp_IoGetActivityIdThread
0x18008f27d  nop     dword ptr [rax+rax+00h]
0x18008f282  lea     rcx, [rbp+4Fh+UserData]
0x18008f286  mov     r9d, 6; UserDataCount
0x18008f28c  mov     [rsp+20h], rcx; UserData
0x18008f291  mov     r8, rax; ActivityId
0x18008f294  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18008f29b  mov     rdx, rbx; EventDescriptor
0x18008f29e  call    cs:__imp_EtwWrite
0x18008f2a5  nop     dword ptr [rax+rax+00h]
0x18008f2aa  mov     rcx, [rbp+4Fh+var_20]
0x18008f2ae  xor     rcx, rsp; StackCookie
0x18008f2b1  call    __security_check_cookie
0x18008f2b6  mov     rbx, [rsp+0C0h+arg_0]
0x18008f2be  add     rsp, 0B0h
0x18008f2c5  pop     rdi
0x18008f2c6  pop     rsi
0x18008f2c7  pop     rbp
0x18008f2c8  retn
```
